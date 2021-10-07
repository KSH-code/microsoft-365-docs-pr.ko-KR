---
title: 고급 감사를 사용하여 손상된 계정 조사
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: MailItemsAccessed 사서함 감사 작업을 사용하여 손상된 사용자 계정에 대한 포렌식 조사를 수행합니다.
ms.openlocfilehash: eeb52058a9937b9ba59b53c7491ccf652cac5288
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60152973"
---
# <a name="use-advanced-audit-to-investigate-compromised-accounts"></a>고급 감사를 사용하여 손상된 계정 조사

손상된 사용자 계정은(*계정 인수* 라고도 함) 공격자가 사용자 계정의 액세스 권한을 얻어 사용자로 작업할 때의 공격 유형입니다. 가끔 이러한 유형의 공격은 공격자가 의도한 것 보다 더 많은 손상을 야기할 수 있습니다. 손상된 전자 메일 계정을 조사할 때 공격자의 실제 현재 상태를 추적하여 표시될 수 있는 것 보다 더 많은 전자 메일 데이터가 손상되었다고 가정해야 합니다. 전자 메일 메시지의 데이터 형식에 따라 중요 한 정보가 손상되었다고 가정하거나 중요한 정보가 노출되지 않은 것을 증명할 수 없는 경우 규제적 벌금을 내야합니다. 예를 들어, HIPAA 규제 조직은 환자의 건강 정보(PHI)가 노출되었다는 증거가 있는 경우 상당한 벌금을 내야합니다. 이 경우 공격자는 PHI에 관심을 가질 가능성이 적습니다. 그러나 조직은 달리 증명할 수 없는 경우 여전히 데이터 침해를 보고해야 합니다.

손상된 전자 메일 계정을 조사하는 데 도움을 주기 위해 당사는 이제 메일 프로토콜 및 클라이언트로 *MailItemsAccessed* 사서함 감사 작업으로 액세스를 감사하고 있습니다. 새로 감사된 이 작업은 조사자들이 전자 메일의 데이터 침해에 대해 더욱 잘 이해하도록 도움을 주고 손상될 수 있는 특정 메일 항목에 대한 손상 범위를 식별하는 데 도움이 됩니다. 이 새 감사 작업을 사용하는 목적은 특정 메일 데이터가 손상되지 않았음을 주장하는데 도움을 주는 포렌식 방어 능력입니다. 공격자가 메일의 특정 부분에 대한 액세스 권한을 얻게 되면 메일 항목을 실제로 읽은 것으로 표시되지 않은 경우에도 Exchange Online에서 해당 이벤트를 감사합니다.

## <a name="the-mailitemsaccessed-mailbox-auditing-action"></a>MailItemsAccessed 사서함 감사 작업

새로운 MailItemsAccessed 작업은 새로운 [고급 감사](advanced-audit.md) 기능의 일부입니다. [Exchange 사서함 감사](/office365/securitycompliance/enable-mailbox-auditing#mailbox-auditing-actions)의 일부이며, Office 365 혹은 Microsoft 365 E5 라이선스가 부여된 사용자나 Microsoft 365 E5 Compliance 추가 기능 구독이 있는 조직에 기본적으로 활성화되어 있습니다.

MailItemsAccessed 사서함 감사 작업은 POP, IMAP, MAPI, EWS, Exchange ActiveSync 및 REST와 같은 모든 메일 프로토콜을 포함합니다. 또한 *동기화* 및 *바인딩* 에 대한 두 가지 메일 액세스 유형을 다룹니다.

### <a name="auditing-sync-access"></a>동기화 액세스 감사

Windows 또는 Mac용 Outlook 클라이언트의 데스크톱 버전에서 사서함에 액세스하는 경우에만 동기화 작업이 기록됩니다. 동기화 작업 중에 일반적으로 이러한 클라이언트는 클라우드에서 많은 메일 항목의 집합을 로컬 컴퓨터로 다운로드합니다. 동기화 작업에 대한 감사 볼륨은 매우 큽니다. 따라서 동기화되는 각 메일 항목에 대한 감사 레코드를 생성하는 대신, 동기화된 항목이 포함된 메일 폴더에 대한 감사 이벤트를 생성합니다. 이는 동기화된 폴더의 *모든* 메일 항목이 손상되었다고 가정합니다. 액세스 형식은 감사 레코드의 OperationProperties 필드에 기록됩니다.

감사 레코드에 동기화 액세스 유형을 표시하는 예제는 [포렌식 조사를 위해 MailItemsAccessed 감사 레코드를 사용](#use-mailitemsaccessed-audit-records-for-forensic-investigations) 섹션의 2단계를 참조하세요.

### <a name="auditing-bind-access"></a>바인딩 액세스 감사

바인딩 작업은 전자 메일 메시지에 대한 개별 액세스입니다. 바인딩 액세스의 경우 개별 메시지의 InternetMessageId가 감사 레코드에 기록됩니다. MailItemsAccessed 감사 작업은 바인딩 작업을 레코드한 다음 하나의 감사 레코드로 집계합니다. 2분 간격 이내에 발생하는 모든 바인딩 작업은 AuditData 속성 내에 있는 폴더 필드의 단일 감사 레코드에 집계됩니다. 엑세스된 각 메시지는 InternetMessageId로 식별됩니다. 레코드에 집계된 바인딩 작업 수가 AuditData 속성의 OperationCount 필드에 표시됩니다.

감사 레코드에 바인딩 액세스 유형을 표시하는 예제는 [포렌식 조사를 위해 MailItemsAccessed 감사 레코드를 사용](#use-mailitemsaccessed-audit-records-for-forensic-investigations) 섹션의 4단계를 참조하세요.

### <a name="throttling-of-mailitemsaccessed-audit-records"></a>MailItemsAccessed 감사 레코드 제한

24시간 이내에 1,000개 이상의 MailItemsAccessed 감사 레코드가 생성되는 경우, Exchange Online에서 MailItemsAccessed 활동에 대한 감사 레코드 생성을 중단합니다. 사서함이 제한되면 사서함이 제한된 후 24시간 동안 MailItemsAccessed 활동이 기록되지 않습니다. 이 경우 해당 기간에 사서함이 손상될 가능성이 있습니다. MailItemsAccessed의 활동의 기록은 24시간 후에 다시 시작됩니다.

제한과 관련하여 유의해야 할 몇 가지 사항은 다음과 같습니다.

- Exchange Online의 모든 사서함의 1% 미만이 제한됩니다.
- 사서함이 제한되면 MailItemsAccessed 활동에 대한 감사 레코드만 감사되지 않습니다. 다른 사서함 감사 작업은 영향을 받지 않습니다.
- 사서함은 바인딩 작업에만 제한됩니다. 동기화 작업에 대한 감사 레코드는 제한되지 않습니다.
- 사서함이 제한된 경우에는 감사 로그에 기록되지 않은 MailItemsAccessed 활동이 있었다고 가정할 수 있습니다.

감사 레코드에 IsThrottled 속성을 표시하는 예제는 [포렌식 조사를 위해 MailItemsAccessed 감사 레코드를 사용](#use-mailitemsaccessed-audit-records-for-forensic-investigations) 섹션의 1단계를 참조하세요.

## <a name="use-mailitemsaccessed-audit-records-for-forensic-investigations"></a>포렌식 조사를 위해 MailItemsAccessed 감사 레코드 사용

사서함 감사는 전자 메일 메시지로의 액세스에 대한 감사 레코드를 생성하여 전자 메일 메시지가 손상되지 않았음을 확신할 수 있도록 합니다. 이러한 이유로 일부 데이터에 액세스했는지 확실하지 않은 경우 모든 메일 액세스 활동을 기록하여 액세스한 것으로 가정합니다.

포렌식 목적의 MailItemsAccessed 감사 레코드 사용은 일반적으로 데이터 침해가 해결되고 공격자가 제거된 후에 수행됩니다. 조사를 시작하려면 손상된 사서함 집합을 확인 하고, 공격자가 조직의 사서함에 액세스할 때의 시간 프레임을 확인해야 합니다. 그런 다음 [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)에서 **Search-UnifiedAuditLog** 혹은 **Search-MailboxAuditLog** cmdlet을 사용하여 데이터 위반에 해당하는 감사 레코드를 검색할 수 있습니다.

다음의 명령 중 하나를 실행하여 MailItemsAccessed 감사 레코드를 검색할 수 있습니다.

**통합 감사 로그**:

```powershell
Search-UnifiedAuditLog -StartDate 01/06/2020 -EndDate 01/20/2020 -UserIds <user1,user2> -Operations MailItemsAccessed -ResultSize 1000
```

**사서함 감사 로그**:

```powershell
Search-MailboxAuditLog -Identity <user> -StartDate 01/06/2020 -EndDate 01/20/2020 -Operations MailItemsAccessed -ResultSize 1000 -ShowDetails
```

> [!TIP]
> 이들 cmdlet의 기본 차이점은 **Search-UnifiedAuditLog** cmdlet를 사용하면 한 명 이상의 사용자가 수행한 활동에 대한 감사 레코드를 검색할 수 있다는 것입니다. 이는 *UserIds* 가 다중 값 매개 변수이기 때문입니다. **Search-MailboxAuditLog** cmdlet은 사서함 감사 로그에서 단일 사용자를 검색합니다.

다음은 MailItemsAccessed 감사 레코드를 사용 하여 손상된 사용자 공격을 조사하는 단계입니다. 각 단계는 **Search-UnifiedAuditLog** 혹은 **Search-MailboxAuditLog** cmdlet에 대한 명령 구문을 보여줍니다.

1. 사서함이 제한되었는지 확인합니다. 제한된 경우 일부 사서함 감사 레코드는 기록되지 않았을 수도 있음을 의미합니다. 어떤 감사 레코드의 "IsThrottled"가 "True"인 경우 레코드가 생성된 후 24시간 동안 사서함으로의 모든 액세스가 감사되지 않았으며 모든 메일 데이터가 손상되었다고 가정해야 합니다.

   사서함이 제한된 위치에서 MailItemsAccessed를 검색하려면 다음의 명령을 실행합니다.

   **통합 감사 로그**:

   ```powershell
   Search-UnifiedAuditLog -StartDate 01/06/2020 -EndDate 01/20/2020 -UserIds <user1,user2> -Operations MailItemsAccessed -ResultSize 1000 | Where {$_.AuditData -like '*"IsThrottled","Value":"True"*'} | FL
   ```

   **사서함 감사 로그**:

   ```powershell
   Search-MailboxAuditLog -StartDate 01/06/2020 -EndDate 01/20/2020 -Identity <user> -Operations MailItemsAccessed -ResultSize 10000 -ShowDetails | Where {$_.OperationProperties -like "*IsThrottled:True*"} | FL
   ```

2. 동기화 활동을 확인합니다. 공격자가 전자 메일 클라이언트를 사용하여 사서함에 메시지를 다운로드하면 컴퓨터의 인터넷 연결을 해제하고 서버와 상호 작용을 하지 않고도 로컬에서 메시지에 액세스할 수 있습니다. 이는 사서함 감사가 이러한 활동을 감사할 수 없음을 의미합니다.

   동기화 작업으로 메일 항목이 액세스된 위치에서 MailItemsAccessed를 검색하려면 다음의 명령을 실행합니다.

   **통합 감사 로그**:

   ```powershell
   Search-UnifiedAuditLog -StartDate 01/06/2020 -EndDate 02/20/2020 -UserIds <user1,user2> -Operations MailItemsAccessed -ResultSize 1000 | Where {$_.AuditData -like '*"MailAccessType","Value":"Sync"*'} | FL
   ```

   **사서함 감사 로그**:

   ```powershell
   Search-MailboxAuditLog -StartDate 01/06/2020 -EndDate 01/20/2020 -Identity <user> -Operations MailItemsAccessed -ResultSize 10000 -ShowDetails | Where {$_.OperationProperties -like "*MailAccessType:Sync*"} | FL
   ```

3. 동기화 활동을 확인하여 공격자가 사서함에 액세스하는 데 사용한 것과 동일한 컨텍스트로 발생한 활동이 있는지 확인합니다. 컨텍스트는 사서함에 액세스하는 데 사용되는 클라이언트 컴퓨터의 IP 주소 및 메일 프로토콜로 식별하고 구분합니다. 자세한 내용은 [다양한 감사 레코드의 액세스 컨텍스트 식별](#identifying-the-access-contexts-of-different-audit-records) 섹션을 참조하세요.

   아래 나열된 속성을 사용하여 조사합니다. 이들 속성은 AuditData 또는 OperationProperties 속성에 있습니다. 동기화가 침입자 활동과 동일한 컨텍스트로 발생하는 경우 공격자가 모든 메일 항목을 클라이언트로 동기화했다고 가정합니다. 이는 아마도 전체 사서함이 손상되었을 수도 있음을 의미합니다.

   <br>

   ****

   |속성|설명|
   |---|---|
   |ClientInfoString|프로토콜, 클라이언트(버전 포함)에 대해 설명합니다.|
   |ClientIPAddress|클라이언트 컴퓨터의 IP 주소입니다.|
   |SessionId|세션 ID는 동일한 계정에서(손상된 계정의 경우) 공격자 작업과 일상적 사용자의 활동 구분하는 데 도움이 됩니다.|
   |UserId|메시지를 읽는 사용자의 UPN입니다.|
   |

4. 바인딩 활동을 확인합니다. 2단계와 3단계를 수행한 후에는 공격자의 모든다른 전자 메일 메시지로의 액세스가 "바인딩” 값이 있는 MailAccessType 속성을 갖는 MailItemsAccessed 감사 레코드로 캡처될 것임을 확신할 수 있습니다.

   메일 항목이 바인딩 작업으로 액세스된 MailItemsAccessed 레코드를 검색하려면 다음의 명령을 실행합니다.

   **통합 감사 로그**:

   ```powershell
   Search-UnifiedAuditLog -StartDate 01/06/2020 -EndDate 01/20/2020 -UserIds <user1,user2> -Operations MailItemsAccessed -ResultSize 1000 | Where {$_.AuditData -like '*"MailAccessType","Value":"Bind"*'} | FL
   ```

   **사서함 감사 로그**:

   ```powershell
   Search-MailboxAuditLog -StartDate 01/06/2020 -EndDate 01/20/2020 -Identity <user> -Operations MailItemsAccessed -ResultSize 10000 -ShowDetails | Where {$_.OperationProperties -like "*MailAccessType:Bind*"} | FL
   ```

   액세스한 전자 메일 메시지는 인터넷 메시지 ID로 식별됩니다. 감사 레코드 중 다른 침입자 활동에 대한 감사 레코드와 동일한 컨텍스트를 포함하는 감사 레코드가 있는지를 확인할 수도 있습니다. 자세한 내용은 [다양한 감사 레코드의 액세스 컨텍스트 식별](#identifying-the-access-contexts-of-different-audit-records) 섹션을 참조하세요.

   다음과 같은 두 가지 방법으로 바인딩 작업에 감사 데이터를 사용할 수 있습니다.

   - 공격자가 InternetMessageId를 사용하여 액세스한 모든 전자 메일 메시지에 액세스를 하거나 수집을 하여 찾고 해당 메시지 가운데 중요한 정보가 포함되어 있는지 확인합니다.
   - InternetMessageId를 사용하여 잠재적으로 중요한 전자 메일 메시지 집합과 관련된 감사 레코드를 검색합니다. 이 방법은 적은 수의 메시지만 우려하는 경우에 유용합니다.

## <a name="filtering-of-duplicate-audit-records"></a>중복된 감사 레코드 필터링

한 시간 이내에 서로 발생하는 동일한 바인딩 작업에 대한 중복 감사 레코드는 감사 노이즈를 제거하기 위해 필터링됩니다. 동기화 작업은 1시간 간격으로도 필터링됩니다. 이 중복 제거 프로세스의 예외는 동일한 InternetMessageId에 대해 다음의 표에 설명된 속성이 다른 경우 발생합니다. 이러한 속성 중 하나가 중복 작업에서 다르면 새 감사 레코드가 생성됩니다. 이 프로세스는 다음 섹션에서 자세히 설명되어 있습니다.

<br>

****

|속성|설명|
|---|---|
|ClientIPAddress|클라이언트 컴퓨터의 IP 주소입니다.|
|ClientInfoString|클라이언트가 사서함에 액세스하는 데 사용한 클라이언트 프로토콜.|
|ParentFolder|액세스한 메일 항목의 전체 폴더 경로입니다.|
|Logon_type|작업을 수행한 사용자의 로그온 유형입니다. 로그온 유형 및 해당 열거형 값은 소유자(0), 관리자(1) 또는 대리자(2)입니다.|
|MailAccessType|액세스가 바인딩 혹은 동기화 작업인지의 여부입니다.|
|MailboxUPN|읽은 메시지가 있는 사서함의 UPN입니다.|
|사용자|메시지를 읽는 사용자의 UPN입니다.|
|SessionId|세션 ID는 공격자 작업과 일상적 사용자 활동을 같은 사서함에서 구별하는 데 도움이 됩니다(계정이 손상된 경우). 세션에 대한 자세한 내용은 [Exchange Online의 세션 내에서 공격자 활동 문맥화](https://techcommunity.microsoft.com/t5/exchange-team-blog/contextualizing-attacker-activity-within-sessions-in-exchange/ba-p/608801)를 참조하세요.|
|

## <a name="identifying-the-access-contexts-of-different-audit-records"></a>여러 감사 레코드의 액세스 컨텍스트 식별

일반적으로 공격자는 사서함 소유자가 사서함에 액세스하는 동시에 사서함에 액세스할 수 있습니다. 공격자와 사서함 소유자가 액세스하는 것을 구별하기 위해 액세스의 컨텍스트를 정의하는 감사 레코드 속성이 있습니다. 앞서 설명한 것처럼 이러한 속성의 값이 다를 경우 심지어 해당 작업이 집계 간격 내에 발생할 때도 별도의 감사 레코드가 생성됩니다. 다음의 예제에는 세 가지의 다양한 감사 레코드가 있습니다. 각 감사 레코드는 세션 ID와 ClientIPAddress 속성으로 구분됩니다. 액세스한 메시지도 식별됩니다.

<br>

****

|감사 레코드 1|감사 레코드 2|감사 레코드 3|
|---|---|---|
|ClientIPAddress **1**<br/>SessionId **2**|ClientIPAddress **2**<br/>SessionId **2**|ClientIPAddress **1**<br/>SessionId **3**|
|InternetMessageId **A**<br/>InternetMessageId **D**<br/>InternetMessageId **E**<br/>InternetMessageId **F**<br/>|InternetMessageId **A**<br/>InternetMessageId **C**|InternetMessageId **B**|
|

[이전 섹션](#filtering-of-duplicate-audit-records)의 테이블에 나열된 속성 중 하나라도 다르면 새 컨텍스트를 추적하는 별도의 감사 레코드가 생성됩니다. 액세스는 활동이 발생한 컨텍스트에 따라 별도의 감사 레코드로 정렬됩니다.

예를 들어, 다음의 스크린샷에 표시된 감사 레코드에서 EWSEditor와 OWA에서 동시에 메일에 액세스를 하지만, 액세스 활동은 액세스가 발생한 컨텍스트에 따라 다른 감사 레코드로 정렬됩니다. 이 경우 컨텍스트는 ClientInfoString 속성에 대 한 다양한 값으로 정의됩니다.

![컨텍스트에 기반한 다양한 감사 레코드.](../media/MailItemsAccessed4.png)

다음은 이전 스크린샷에 표시된 명령에 대한 구문입니다.

```powershell
Search-MailboxAuditLog -Identity admin -ShowDetails -Operations MailItemsAccessed -ResultSize 2000 | Select LastAccessed,Operation,AuditOperationsCountInAggregatedRecord,ClientInfoString
```
