---
title: 사서함 감사 관리
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: aaca8987-5b62-458b-9882-c28476a66918
ms.custom: seo-marvel-apr2020
description: 사서함 감사 로깅은 기본적으로 Microsoft 365 사서함 감사 또는 사서함 감사라고도 합니다. 즉, 사서함 소유자, 대리인 및 관리자가 수행한 특정 작업이 사서함 감사 로그에 자동으로 기록되며, 사서함에서 수행되는 작업을 검색할 수 있습니다.
ms.openlocfilehash: 4487defd4c971b5decda3442739730adcafac453
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60207310"
---
# <a name="manage-mailbox-auditing"></a>사서함 감사 관리

2019년 1월부터 Microsoft는 기본적으로 모든 조직에 대해 사서함 감사 로깅을 켜고 있습니다. 즉, 사서함 소유자, 대리인 및 관리자가 수행한 특정 작업이 자동으로 기록되며 사서함 감사 로그에서 해당 사서함 감사 레코드를 검색할 때 해당 사서함 감사 레코드를 사용할 수 있습니다. 사서함 감사를 기본적으로 설정하기 전에 조직의 모든 사용자 사서함에 대해 수동으로 사용하도록 설정해야 했습니다.

기본적으로 사서함 감사의 몇 가지 이점은 다음과 같습니다.

- 감사는 새 사서함을 만들 때 자동으로 사용하도록 설정됩니다. 새 사용자에 대해 수동으로 사용하도록 설정할 필요는 없습니다.
- 감사되는 사서함 작업은 관리할 필요가 없습니다. 미리 정의한 사서함 작업 집합은 각 로그온 유형(관리자, 대리인 및 소유자)에 대해 기본적으로 감사됩니다.
- Microsoft에서 새 사서함 작업을 릴리스하면 해당 작업이 기본적으로 감사되는 사서함 작업 목록에 자동으로 추가될 수 있습니다(해당 라이선스가 있는 사용자에 따라). 즉, 사서함에 대한 새 작업 추가를 모니터링할 필요가 없습니다.
- 조직 전체에서 일관된 사서함 감사 정책이 있습니다(모든 사서함에 대해 동일한 작업을 감사하기 때문에).

> [!NOTE]
>
> - 기본적으로 사서함 감사 릴리스에 대해 기억해야 할 중요한 점은 사서함 감사를 관리하기 위해 아무 작업도 할 필요가 없습니다. 그러나 자세한 내용을 알아보기 위해 기본 설정에서 사서함 감사를 사용자 지정하거나 모두 해제하려면 이 문서가 도움이 될 수 있습니다.
> - 기본적으로 E5 사용자에 대한 사서함 감사 이벤트만 감사 로그 검색에서 Microsoft 365 규정 준수 센터 또는 Office 365 관리 활동 API를 통해 사용할 수 있습니다. 자세한 내용은 이 문서의 [추가 정보](#more-information) 섹션을 참조하십시오.

## <a name="verify-mailbox-auditing-on-by-default-is-turned-on"></a>사서함 감사 기본 사용이 켜져 있는지 확인

조직에 대해 사서함 감사가 기본적으로 설정되어 있는지 확인하기 위해 [PowerShell에서 Exchange Online 실행합니다.](/powershell/exchange/connect-to-exchange-online-powershell)

```PowerShell
Get-OrganizationConfig | Format-List AuditDisabled
```

False **값은** 기본적으로 사서함 감사가 조직에 대해 사용하도록 설정되어 있는 경우를 나타냅니다. 이 설정은 기본적으로 조직 값이 특정 사서함에 대한 사서함 감사 설정을 에 정의합니다. 예를 들어 사서함에 대해 사서함 감사를 사용하지 않도록 설정한 *경우(AuditEnabled* 속성이 **사서함의 경우 False임)** 기본적으로 사서함 감사가 조직에 대해 사용하도록 설정되어 있기 때문에 사서함에 대한 기본 사서함 작업이 계속 감사됩니다.

특정 사서함에 대해 사서함 감사를 사용하지 않도록 설정하기 위해 사서함 소유자 및 사서함에 대한 액세스 권한을 위임된 다른 사용자에 대해 사서함 감사 우회를 구성합니다. 자세한 내용은 이 문서의 사서함 감사 [로깅](#bypass-mailbox-audit-logging) 무시 섹션을 참조하십시오.

> [!NOTE]
> 조직에 대해 기본적으로 사서함 감사가 설정되어 있는 경우 영향을 받는 사서함의 *AuditEnabled* 속성은 **False에서 True로** 변경되지 **않습니다.** 즉, 기본적으로 설정되는 사서함 감사는 사서함의 *AuditEnabled* 속성을 무시합니다.

## <a name="supported-mailbox-types"></a>지원되는 사서함 유형

다음 표에는 기본적으로 사서함 감사에서 현재 지원되는 사서함 유형이 표시됩니다.

<br>

****

|사서함 유형|지원|
|---|:---:|
|사용자 사서함|![확인 표시입니다.](../media/checkmark.png)|
|공유 사서함|![확인 표시입니다.](../media/checkmark.png)|
|Microsoft 365 그룹 사서함|![확인 표시입니다.](../media/checkmark.png)|
|리소스 사서함||
|공용 폴더 사서함||
|

## <a name="logon-types-and-mailbox-actions"></a>로그온 유형 및 사서함 작업

로그온 유형 사서함에 대해 감사된 작업을 수행한 사용자를 분류합니다. 다음 목록에는 사서함 감사 로깅에 사용되는 로그온 유형이 설명되어 있습니다.

- **소유자:** 사서함 소유자(사서함과 연결된 계정)
- **대리자**:
  - 다른 사서함에 대한 SendAs, SendOnBehalf 또는 FullAccess 권한이 할당된 사용자입니다.
  - 사용자의 사서함에 대한 FullAccess 권한이 할당된 관리자입니다.
- **관리자**:
  - 사서함은 다음 Microsoft eDiscovery 도구 중 하나를 사용하여 검색됩니다.
    - 준수 센터의 콘텐츠 검색
    - eDiscovery 또는 Advanced eDiscovery 센터에 있습니다.
    - In-Place eDiscovery를 Exchange Online.
  - MAPI 편집기에서 사서함에 Microsoft Exchange Server 액세스합니다.

### <a name="mailbox-actions-for-user-mailboxes-and-shared-mailboxes"></a>사용자 사서함 및 공유 사서함에 대한 사서함 작업

다음 표에서는 사용자 사서함 및 공유 사서함에 대한 사서함 감사 로깅에서 사용할 수 있는 사서함 작업에 대해 설명되어 있습니다.

- 확인 표시(![확인 표시입니다.](../media/checkmark.png))는 로그온 유형에 대해 사서함 작업을 기록할 수 있습니다(모든 로그온 유형에 대해 일부 작업을 사용할 수 있는 것은 아 아함).
- 확인 표시 다음에 추가()는 사서함 작업이 로그온 유형에 대해 기본적으로 기록되어 있는 <sup>\*</sup> 것입니다.
- 사서함에 대한 모든 액세스 권한이 있는 관리자는 대리인으로 간주됩니다.

<br>

****

|사서함 작업|설명|관리자|대리인|소유자|
|---|---|:---:|:---:|:---:|
|**AddFolderPermissions**|이 값은 사서함 작업으로 수락되어도 **이미 UpdateFolderPermissions** 동작에 포함되어 있으며 별도로 감사되지 않습니다. 즉, 이 값을 사용하지 않습니다.||||
|**ApplyRecord**|항목에 레코드로 레이블이 지정됩니다.|![확인 표시입니다.](../media/checkmark.png)<sup>\*</sup>|![확인 표시입니다.](../media/checkmark.png)<sup>\*</sup>|![확인 표시입니다.](../media/checkmark.png)<sup>\*</sup>|
|**복사**|메시지가 다른 폴더에 복사되었습니다.|![확인 표시입니다.](../media/checkmark.png)|||
|**만들기**|항목이 사서함의 일정, 연락처, 메모 또는 작업 폴더에 만들어졌습니다(예: 새 모임 요청이 만들어지기). 메시지 작성, 보내기 또는 받기는 감사되지 않습니다. 사서함 폴더 만들기도 감사되지 않습니다.|![확인 표시입니다.](../media/checkmark.png)<sup>\*</sup>|![확인 표시입니다.](../media/checkmark.png)<sup>\*</sup>|![확인 표시입니다.](../media/checkmark.png)|
|**FolderBind**|사서함 폴더에 액세스했습니다. 관리자 또는 대리인이 사서함을 열 때에도 작업이 기록됩니다.<br/><br/> **참고:** 대리인이 수행한 폴더 바인딩 작업에 대한 감사 레코드가 통합됩니다. 24시간 내에 개별 폴더 액세스에 대해 하나의 감사 레코드가 생성됩니다.|![확인 표시입니다.](../media/checkmark.png)|![확인 표시입니다.](../media/checkmark.png)||
|**HardDelete**|메시지가 복구 가능한 항목 폴더에서 제거되었습니다.|![확인 표시입니다.](../media/checkmark.png)<sup>\*</sup>|![확인 표시입니다.](../media/checkmark.png)<sup>\*</sup>|![확인 표시입니다.](../media/checkmark.png)<sup>\*</sup>|
|**MailboxLogin**|사용자가 사서함에 로그인한 경우|||![확인 표시](../media/checkmark.png)|
|**MailItemsAccessed**|**참고:** 이 값은 E5 또는 E5 준수 추가 기능 구독 사용자만 사용할 수 있습니다. 자세한 내용은 [Set up Advanced Audit in Microsoft 365.](set-up-advanced-audit.md) <p> 메일 데이터는 메일 프로토콜 및 클라이언트에서 액세스합니다.|![확인 표시입니다.](../media/checkmark.png)<sup>\*</sup>|![확인 표시입니다.](../media/checkmark.png)<sup>\*</sup>|![확인 표시](../media/checkmark.png)<sup>\*</sup>|
|**MessageBind**|**참고:** 이 값은 E3 사용자(E5 또는 E5 준수 추가 기능 구독이 없는 사용자)에만 사용할 수 있습니다. <p> 미리 보기 창에서 메시지를 보거나 관리자가 연 경우|![확인 표시](../media/checkmark.png)|||
|**ModifyFolderPermissions**|이 값은 사서함 작업으로 수락되어도 **이미 UpdateFolderPermissions** 동작에 포함되어 있으며 별도로 감사되지 않습니다. 즉, 이 값을 사용하지 않습니다.||||
|**이동**|메시지가 다른 폴더로 이동했습니다.|![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|
|**MoveToDeletedItems**|메시지가 삭제되어 지운 편지함 폴더로 이동되었습니다.|![확인 표시입니다.](../media/checkmark.png)<sup>\*</sup>|![확인 표시입니다.](../media/checkmark.png)<sup>\*</sup>|![확인 표시](../media/checkmark.png)<sup>\*</sup>|
|**RecordDelete**|레코드로 레이블이 지정되는 항목이 소프트 삭제되었습니다(복구 가능한 항목 폴더로 이동). 레코드로 레이블이 붙은 항목은 영구적으로 삭제할 수 없습니다(복구 가능한 항목 폴더에서 제거).|![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|
|**RemoveFolderPermissions**|이 값은 사서함 작업으로 수락되어도 **이미 UpdateFolderPermissions** 동작에 포함되어 있으며 별도로 감사되지 않습니다. 즉, 이 값을 사용하지 않습니다.||||
|**SearchQueryInitiated**|**참고:** 이 값은 E5 또는 E5 준수 추가 기능 구독 사용자만 사용할 수 있습니다. 자세한 내용은 [Set up Advanced Audit in Microsoft 365.](set-up-advanced-audit.md) <p> 개인은 Outlook(Windows, Mac, iOS, Android 또는 웹용 Outlook) 또는 메일 앱을 사용하여 사서함에서 Windows 10 검색할 수 있습니다.|||![확인 표시](../media/checkmark.png)|
|**보내기**|**참고:** 이 값은 E5 또는 E5 준수 추가 기능 구독 사용자만 사용할 수 있습니다. 자세한 내용은 [Set up Advanced Audit in Microsoft 365.](set-up-advanced-audit.md) <p> 사용자는 전자 메일 메시지를 보내거나 전자 메일 메시지에 답장하거나 전자 메일 메시지를 전달합니다.|![확인 표시입니다.](../media/checkmark.png)<sup>\*</sup>||![확인 표시](../media/checkmark.png)<sup>\*</sup>|
|**SendAs**|메시지가 SendAs 권한을 사용하여 전송되었습니다. 즉 사서함 소유자가 보낸 것처럼 보이도록 하여 다른 사용자가 메시지를 보냈습니다.|![확인 표시입니다.](../media/checkmark.png)<sup>\*</sup>|![확인 표시](../media/checkmark.png)<sup>\*</sup>||
|**SendOnBehalf**|메시지가 SendOnBehalf 권한을 사용하여 전송되었습니다. 즉 다른 사용자가 사서함 소유자 대신에 메시지를 보냈습니다. 받는 사람은 메시지를 대신 보낸 사용자와 해당 메시지를 실제로 보낸 사용자를 메시지에서 확인할 수 있습니다.|![확인 표시입니다.](../media/checkmark.png)<sup>\*</sup>|![확인 표시](../media/checkmark.png)<sup>\*</sup>||
|**SoftDelete**|메시지가 지운 편지함 폴더에서 삭제되어가 영구적으로 삭제되었습니다. 소프트 삭제된 항목이 복구 가능한 항목 폴더로 이동됩니다.|![확인 표시입니다.](../media/checkmark.png)<sup>\*</sup>|![확인 표시입니다.](../media/checkmark.png)<sup>\*</sup>|![확인 표시](../media/checkmark.png)<sup>\*</sup>|
|**업데이트**|메시지 또는 해당 속성이 변경되었습니다.|![확인 표시입니다.](../media/checkmark.png)<sup>\*</sup>|![확인 표시입니다.](../media/checkmark.png)<sup>\*</sup>|![확인 표시](../media/checkmark.png)<sup>\*</sup>|
|**UpdateCalendarDelegation**|일정 위임이 사서함에 할당된 경우 일정 위임 기능을 사용하여 같은 조직의 다른 사용자가 사서함 소유자의 일정을 관리할 수 있습니다.|![확인 표시입니다.](../media/checkmark.png)<sup>\*</sup>||![확인 표시](../media/checkmark.png)<sup>\*</sup>|
|**UpdateComplianceTag**|다른 보존 레이블이 메일 항목에 적용됩니다(항목에 보존 레이블을 하나만 할당할 수 있습니다).|![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|
|**UpdateFolderPermissions**|폴더 권한이 변경되었습니다. 폴더 사용 권한은 사서함의 폴더와 해당 폴더에 있는 메시지에 액세스할 수 있는 조직의 사용자를 제어합니다.|![확인 표시입니다.](../media/checkmark.png)<sup>\*</sup>|![확인 표시입니다.](../media/checkmark.png)<sup>\*</sup>|![확인 표시](../media/checkmark.png)<sup>\*</sup>|
|**UpdateInboxRules**|받은 편지함 규칙이 추가, 제거 또는 변경되었습니다. 받은 편지함 규칙은 지정된 조건에 따라 사용자의 받은 편지함에서 메시지를 처리하고 규칙 조건이 충족될 때 지정된 폴더로 메시지를 이동하거나 메시지를 삭제하는 등의 작업을 수행하기 위해 사용됩니다.|![확인 표시입니다.](../media/checkmark.png)<sup>\*</sup>|![확인 표시](../media/checkmark.png)<sup>\*</sup>|![확인 표시](../media/checkmark.png)<sup>\*</sup>|
|

> [!IMPORTANT]
> 조직에서 기본적으로 사서함 감사를 사용하도록 설정하기 전에 로그온 유형에 대해 감사하도록 사서함 작업을 사용자 지정한 경우 사용자 지정된 설정은 사서함에 보존되고 이 섹션에 설명된 기본 사서함 작업으로 덮어 사용되지 않습니다.  감사 사서함 작업을 기본값으로 되감기(어떤 경우든 수행할 수 있습니다)를 복원하는 경우 이 문서 의 부분에 있는 기본 사서함 작업 복원 섹션을 참조하십시오. [](#restore-the-default-mailbox-actions)

### <a name="mailbox-actions-for-microsoft-365-group-mailboxes"></a>그룹 사서함에 Microsoft 365 사서함 작업

기본적으로 사서함 감사를 수행하면 사서함 감사 로깅이 Microsoft 365 그룹 사서함으로 이동되지만 로깅되는 항목은 사용자 지정할 수 없습니다(로그온 유형에 대해 기록되는 사서함 작업은 추가하거나 제거할 수 없습니다).

다음 표에서는 각 로그온 유형에 대해 Microsoft 365 사서함에 기본적으로 기록되는 사서함 작업에 대해 설명하고 있습니다.

그룹 사서함에 대한 모든 액세스 권한이 Microsoft 365 관리자는 대리인으로 간주됩니다.

<br>

****

|사서함 작업|설명|관리자|대리인|소유자|
|---|---|:---:|:---:|:---:|
|**만들기**|일정 항목 만들기 메시지 작성, 보내기 또는 받기는 감사되지 않습니다.|![확인 표시](../media/checkmark.png)<sup>\*</sup>|![확인 표시](../media/checkmark.png)<sup>\*</sup>||
|**HardDelete**|메시지가 복구 가능한 항목 폴더에서 제거되었습니다.|![확인 표시입니다.](../media/checkmark.png)<sup>\*</sup>|![확인 표시](../media/checkmark.png)<sup>\*</sup>|![확인 표시](../media/checkmark.png)<sup>\*</sup>|
|**MoveToDeletedItems**|메시지가 삭제되어 지운 편지함 폴더로 이동되었습니다.|![확인 표시입니다.](../media/checkmark.png)<sup>\*</sup>|![확인 표시](../media/checkmark.png)<sup>\*</sup>|![확인 표시](../media/checkmark.png)<sup>\*</sup>|
|**SendAs**|SendAs 권한을 사용하여 메시지가 전송되었습니다.|![확인 표시](../media/checkmark.png)<sup>\*</sup>|![확인 표시](../media/checkmark.png)<sup>\*</sup>||
|**SendOnBehalf**|SendOnBehalf 권한을 사용하여 메시지가 전송되었습니다.|![확인 표시](../media/checkmark.png)<sup>\*</sup>|![확인 표시](../media/checkmark.png)<sup>\*</sup>||
|**SoftDelete**|메시지가 지운 편지함 폴더에서 삭제되어가 영구적으로 삭제되었습니다. 소프트 삭제된 항목이 복구 가능한 항목 폴더로 이동됩니다.|![확인 표시입니다.](../media/checkmark.png)<sup>\*</sup>|![확인 표시](../media/checkmark.png)<sup>\*</sup>|![확인 표시](../media/checkmark.png)<sup>\*</sup>|
|**업데이트**|메시지 또는 해당 속성이 변경된 경우|![확인 표시입니다.](../media/checkmark.png)<sup>\*</sup>|![확인 표시](../media/checkmark.png)<sup>\*</sup>|![확인 표시](../media/checkmark.png)<sup>\*</sup>|
|

### <a name="verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type"></a>각 로그온 유형에 대해 기본 사서함 작업이 기록되고 있는지 확인

기본적으로 사서함 감사는 모든 사서함에 새 *DefaultAuditSet* 속성을 추가합니다. 이 속성의 값은 기본 사서함 작업(Microsoft에서 관리)이 사서함에 대해 감사되고 있는지 여부를 나타냅니다.

사용자 사서함 또는 공유 사서함의 값을 표시하기 위해 사서함의 이름, 별칭, 전자 메일 주소 또는 사용자 계정 \<MailboxIdentity\> 이름(사용자 이름)으로 바꾸고 PowerShell에서 Exchange Online 실행합니다.

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Format-List DefaultAuditSet
```

그룹 사서함에 값을 Microsoft 365 공유 사서함의 이름, 별칭 또는 전자 메일 주소로 바꾸고 \<MailboxIdentity\> PowerShell에서 Exchange Online 실행합니다.

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> -GroupMailbox | Format-List DefaultAuditSet
```

값은 `Admin, Delegate, Owner` 다음을 나타냅니다.

- 세 가지 로그온 유형 모두에 대한 기본 사서함 작업이 감사됩니다. 이 값은 그룹 사서함에 Microsoft 365 있습니다.
- 관리자가 *사용자 사서함* 또는 공유 사서함의 로그온 유형에 대해 감사된 사서함 작업을 변경하지 않았습니다. 이 상태는 조직에서 사서함 감사를 기본적으로 처음 설정한 후의 기본 상태입니다.

**관리자가 Set-Mailbox** cmdlet에서 *AuditAdmin,* *AuditDelegate* 또는 *AuditOwner* 매개 변수를 사용하여 로그온 유형에 대해 감사되는 사서함 작업을 변경한 경우 속성 값이 다릅니다.

예를 들어 사용자 사서함 또는 공유 사서함의 `Owner` *DefaultAuditSet* 속성 값은 다음을 나타냅니다.

- 사서함 소유자에 대한 기본 사서함 작업이 감사됩니다.
- 및 로그온 유형에 대해 감사된 사서함 작업이 기본 `Delegate` `Admin` 작업에서 변경됩니다.

*DefaultAuditSet* 속성의 값을 비워 두면 사용자 사서함이나 공유 사서함에서 세 가지 로그온 유형에 대한 사서함 작업이 모두 변경된 것입니다.

자세한 내용은 이 문서의 [기본적으로](#change-or-restore-mailbox-actions-logged-by-default) 기록되는 사서함 작업 변경 또는 복원 섹션을 참조하십시오.

### <a name="display-the-mailbox-actions-that-are-being-logged-on-mailboxes"></a>사서함에 로그온하는 사서함 작업 표시

현재 사용자 사서함 또는 공유 사서함에 로그온 중인 사서함 작업을 확인한 후 사서함의 이름, 별칭, 전자 메일 주소 또는 사용자 계정 이름(사용자 이름)으로 바꾸고 Exchange Online PowerShell에서 다음 명령 중 \<MailboxIdentity\> 하나 이상을 실행합니다.

> [!NOTE]
> 그룹 사서함에 대한 다음 `-GroupMailbox` **Get-Mailbox** 명령에 Microsoft 365 수 있는 경우 반환되는 값을 믿지 않습니다. Microsoft 365 그룹 사서함에 대해 감사되는 기본 및 정적 사서함 작업은 이 문서 앞부분의 Microsoft 365 [그룹](#mailbox-actions-for-microsoft-365-group-mailboxes) 사서함에 대한 사서함 작업 섹션에 설명되어 있습니다.

#### <a name="owner-actions"></a>소유자 작업

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditOwner
```

#### <a name="delegate-actions"></a>위임 작업

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditDelegate
```

#### <a name="admin-actions"></a>관리자 작업

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditAdmin
```

## <a name="change-or-restore-mailbox-actions-logged-by-default"></a>기본적으로 로깅되는 사서함 작업 변경 또는 복원

앞서 설명한 것 처럼 기본적으로 사서함 감사를 사용할 수 있는 주요 이점 중 하나는 감사되는 사서함 작업을 관리할 필요가 없습니다. Microsoft는 이 작업을 자동으로 수행하며, 기본적으로 감사할 새 사서함 작업이 릴리스될 때 자동으로 추가됩니다.

그러나 조직에서 사용자 사서함 및 공유 사서함에 대해 다른 사서함 작업 집합을 감사해야 할 수 있습니다. 이 섹션의 절차에서는 각 로그온 유형에 대해 감사되는 사서함 작업을 변경하는 방법과 Microsoft에서 관리하는 기본 작업으로 되돌아가는 방법을 설명합니다.

> [!IMPORTANT]
> 다음 절차에 따라 사용자 사서함 또는 공유 사서함에 기록되는 사서함 작업을 사용자 지정하는 경우 Microsoft에서 릴리스한 새 기본 사서함 작업은 해당 사서함에 대해 자동으로 감사되지 않습니다. 사용자 지정된 작업 목록에 새 사서함 작업을 수동으로 추가해야 합니다.

### <a name="change-the-mailbox-actions-to-audit"></a>사서함 작업을 감사로 변경

**Set-Mailbox** cmdlet에서 *AuditAdmin,* *AuditDelegate* 또는 *AuditOwner* 매개 변수를 사용하여 사용자 사서함 및 공유 사서함에 대해 감사되는 사서함 작업을 변경할 수 있습니다(Microsoft 365 그룹 사서함에 대해 감사된 작업은 사용자 지정할 수 없습니다).

다음 두 가지 방법을 사용하여 사서함 작업을 지정할 수 있습니다.

- *다음* 구문을 사용하여 기존 사서함 작업을 대체(덮어 덮어) `action1,action2,...actionN` 합니다.
- *또는 구문을* 사용하여 다른 기존 값에 영향을 주지 않고 사서함 작업을 추가하거나 `@{Add="action1","action2",..."actionN"}` `@{Remove="action1","action2",..."actionN"}` 제거합니다.

이 예에서는 SoftDelete 및 HardDelete로 기본 작업을 덮어어 "Gabriela Laureano"라는 사서함에 대한 관리자 사서함 작업을 변경합니다.

```PowerShell
Set-Mailbox -Identity "Gabriela Laureano" -AuditAdmin HardDelete,SoftDelete
```

이 예에서는 사서함 서버의 사서함에 MailboxLogin 소유자 작업을 laura@contoso.onmicrosoft.com.

```PowerShell
Set-Mailbox -Identity laura@contoso.onmicrosoft.com -AuditOwner @{Add="MailboxLogin"}
```

이 예에서는 팀 토론 사서함에 대한 MoveToDeletedItems 대리인 작업을 제거합니다.

```PowerShell
Set-Mailbox -Identity "Team Discussion" -AuditDelegate @{Remove="MoveToDeletedItems"}
```

사용하는 방법에 관계없이 사용자 사서함 또는 공유 사서함에 대해 감사되는 사서함 작업을 사용자 지정하면 다음과 같은 결과가 나타납니다.

- 사용자 지정한 로그온 유형의 경우 감사된 사서함 작업은 Microsoft에서 더 이상 관리되지 않습니다.
- 사용자 지정한 로그온 유형은 앞서 설명한 사서함의 *DefaultAuditSet* 속성 값에 더 이상 [표시되지 않습니다.](#verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type)

### <a name="restore-the-default-mailbox-actions"></a>기본 사서함 작업 복원

> [!NOTE]
> 다음 절차는 Microsoft 365 그룹 사서함에는 적용되지 않습니다(여기에 설명된 기본 작업으로 [제한).](#mailbox-actions-for-microsoft-365-group-mailboxes)

사용자 사서함 또는 공유 사서함에서 감사되는 사서함 작업을 사용자 지정한 경우 다음 구문을 사용하여 하나 또는 모든 로그온 유형에 대한 기본 사서함 작업을 복원할 수 있습니다.

```PowerShell
Set-Mailbox -Identity <MailboxIdentity> -DefaultAuditSet <Admin | Delegate | Owner>
```

*여러 DefaultAuditSet* 값을 각기 콤보로 구분하여 지정할 수 있습니다.

이 예에서는 사서함 서버의 모든 로그온 유형에 대해 감사되는 기본 사서함 작업을 mark@contoso.onmicrosoft.com.

```PowerShell
Set-Mailbox -Identity mark@contoso.onmicrosoft.com -DefaultAuditSet Admin,Delegate,Owner
```

이 예에서는 사서함 서버의 관리자 로그온 유형에 대한 기본 감사된 사서함 작업을 chris@contoso.onmicrosoft.com 대리인 및 소유자 로그온 유형에 대해 사용자 지정된 감사된 사서함 작업을 그대로 떠날 수 있습니다.

```PowerShell
Set-Mailbox -Identity chris@contoso.onmicrosoft.com -DefaultAuditSet Admin
```

로그온 유형에 대해 기본 감사 사서함 작업을 복원하면 다음과 같은 결과가 나타납니다.

- 현재 사서함 작업 목록은 로그온 유형에 대한 기본 사서함 작업으로 대체됩니다.
- Microsoft에서 릴리스한 모든 새 사서함 작업은 로그온 유형에 대한 감사된 작업 목록에 자동으로 추가됩니다.
- 사서함의 *DefaultAuditSet* 속성 값은 복원된 로그온 유형을 포함하기 위해 업데이트됩니다.

## <a name="turn-off-mailbox-auditing-on-by-default-for-your-organization"></a>조직에 대해 사서함 감사를 기본적으로 끄기

PowerShell에서 다음 명령을 실행하여 전체 조직에 대해 기본적으로 사서함 감사를 Exchange Online 있습니다.

```PowerShell
Set-OrganizationConfig -AuditDisabled $true
```

기본적으로 사서함 감사를 끄면 다음과 같은 결과가 표시됩니다.

- 조직에서 사서함 감사를 사용할 수 없습니다.
- 기본적으로 사서함 감사를 사용하지 않도록 설정한 시간부터 사서함에서 감사를 사용하도록 설정한 경우에도 사서함 작업이 감사되지 않습니다(사서함의 *AuditEnabled* 속성이 **True임).**
- 새 사서함에 대해 사서함 감사를 사용하도록 설정하지 않은 경우 새 사서함이나 기존 사서함의 *AuditEnabled* 속성을 **True로** 설정하면 무시됩니다.
- **Set-MailboxAuditBypassAssociation cmdlet을** 사용하여 구성한 사서함 감사 우회 연결 설정은 무시됩니다.
- 기존 사서함 감사 레코드는 레코드에 대한 감사 로그 보존 기간이 만료될 때까지 보존됩니다.

### <a name="turn-on-mailbox-auditing-on-by-default"></a>기본적으로 사서함 감사 켜기

조직에 대한 사서함 감사를 다시 설정하기 위해 PowerShell에서 Exchange Online 실행합니다.

```PowerShell
Set-OrganizationConfig -AuditDisabled $false
```

## <a name="bypass-mailbox-audit-logging"></a>사서함 감사 로깅 우회

현재 조직의 사서함 감사 기본 사용이 켜져 있으면 특정 사서함에 대한 사서함 감사를 사용하지 않도록 설정할 수 없습니다. 예를 들어 *AuditEnabled* 사서함 속성을 **False로** 설정하면 무시됩니다.

그러나 Exchange Online PowerShell에서 **Set-MailboxAuditBypassAssociation** cmdlet을 사용하여 작업이 수행되는 위치와 관계없이 지정된 사용자의 모든 사서함 작업이 기록되지 않도록 할 수 있습니다.  예제:

- 무시된 사용자가 수행한 사서함 소유자 작업은 기록되지 않습니다.
- 다른 사용자의 사서함(공유 사서함 포함)에서 무시된 사용자가 수행한 위임 작업은 기록되지 않습니다.
- 무시된 사용자가 수행한 관리 작업은 기록되지 않습니다.

특정 사용자에 대한 사서함 감사 로깅을 무시하기 위해 사용자의 이름, 전자 메일 주소, 별칭 또는 사용자 계정 이름(사용자 이름)으로 바꾸고 다음 명령을 \<MailboxIdentity\> 실행합니다.

```PowerShell
Set-MailboxAuditBypassAssociation -Identity <MailboxIdentity> -AuditByPassEnabled $true
```

지정된 사용자에 대해 감사가 우회되었는지 확인하려면 다음 명령을 실행합니다.

```PowerShell
Get-MailboxAuditBypassAssociation -Identity <MailboxIdentity> | Format-List AuditByPassEnabled
```

True **값으로** 설정하면 사용자에 대해 사서함 감사 로깅이 무시됩니다.

## <a name="more-information"></a>추가 정보

- 기본적으로 사서함 감사 로그온은 모든 조직에 대해 사용하도록 설정되어 있습니다. 그러나 E5 라이선스가 있는 사용자만 사서함 감사 로그 검색에서 Microsoft 365 규정 준수 센터 또는 Office 365 관리 활동 [API를](/office/office-365-management-api/office-365-management-activity-api-reference) 통해 **반환됩니다.** [](search-the-audit-log-in-security-and-compliance.md)

  E5 라이선스가 없는 사용자의 사서함 감사 로그 항목을 검색하려면 다음을 할 수 있습니다.

  - 개별 사서함에 대해 사서함 감사를 수동으로 사용하도록 설정(명령을 `Set-Mailbox -Identity <MailboxIdentity> -AuditEnabled $true` 실행합니다.) 이렇게 한 후 감사 로그 검색을 사용하여 Microsoft 365 규정 준수 센터 관리 활동 API를 통해 Office 365 수 있습니다.

    > [!NOTE]
    > 사서함 감사가 이미 사서함에서 사용하도록 설정된 것으로 보이지만 검색에서 결과가 반환되지 않았다면 _AuditEnabled_ 매개 변수의 값을 로 변경한 다음 로 `$false` 다시 `$true` 변경합니다.

  - PowerShell에서 다음 cmdlet을 Exchange Online 있습니다.
    - [Search-MailboxAuditLog](/powershell/module/exchange/search-mailboxauditlog) - 특정 사용자에 대한 사서함 감사 로그를 검색합니다.
    - [New-MailboxAuditLogSearch](/powershell/module/exchange/new-mailboxauditlogsearch) - 특정 사용자에 대한 사서함 감사 로그를 검색하고 지정된 받는 사람에게 전자 메일을 통해 결과를 전송하도록 합니다.

  - EAC(Exchange 관리 센터)를 사용하여 Exchange Online 작업을 수행할 수 있습니다.
    - [사서함 감사 로그 내보내기](/Exchange/security-and-compliance/exchange-auditing-reports/export-mailbox-audit-logs)
    - [비소유자 사서함 액세스 보고서 실행](/Exchange/security-and-compliance/exchange-auditing-reports/non-owner-mailbox-access-report)

- 기본적으로 사서함 감사 로그 레코드는 삭제되기 90일 동안 보존됩니다. PowerShell의 **Set-Mailbox** cmdlet에서 *AuditLogAgeLimit* 매개 변수를 사용하여 감사 로그 레코드의 Exchange Online 있습니다. 그러나 이 값을 늘리면 감사 로그에서 90일보다 오래된 이벤트를 검색할 수 없습니다.

  사용 시간 제한을 늘리는 경우 Exchange Online PowerShell에서 [Search-MailboxAuditLog](/powershell/module/exchange/search-mailboxauditlog) cmdlet을 사용하여 사용자의 사서함 감사 로그에서 90일이 지난 레코드를 검색해야 합니다.

- 기본적으로 조직에 대해 사서함 감사를 설정하기 전에 사서함의 *AuditLogAgeLimit* 속성을 변경한 경우 사서함의 기존 감사 로그 사용 시간 제한은 변경되지 않습니다. 즉, 기본적으로 설정되는 사서함 감사는 사서함 감사 레코드의 현재 사용 시간 제한에 영향을 주지 않습니다.

- 그룹 사서함의 *AuditLogAgeLimit* Microsoft 365 Set-Mailbox 명령에 스위치를 `-GroupMailbox` **포함해야** 합니다.

- 사서함 감사 로그 레코드는 각 사용자 사서함의 복구 가능한 항목 폴더에 있는 하위 *폴더(Audits)에* 저장됩니다. 사서함 감사 레코드 및 복구 가능한 항목 폴더에 대해 다음에 유의하십시오.

  - 사서함 감사 레코드는 기본적으로 30GB(경고 할당량은 20GB)인 복구 가능한 항목 폴더의 저장소 할당량에 대해 계산됩니다. 저장소 할당량은 다음 경우 자동으로 100GB(90GB 경고 할당량 사용)로 증가합니다.
    - 사서함에 보류가 적용됩니다.
    - 사서함은 준수 센터의 보존 정책에 할당됩니다.

  - 사서함 감사 레코드는 복구 가능한 항목 폴더의 폴더 [제한에 계산됩니다.](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#mailbox-folder-limits) 감사 하위폴더에 최대 300만 개 항목(감사 레코드)을 저장할 수 있습니다.

    > [!NOTE]
    > 기본적으로 사서함 감사가 저장소 할당량 또는 복구 가능한 항목 폴더의 폴더 제한에 영향을 줄 가능성은 낮습니다.

    - PowerShell에서 Exchange Online 명령을 실행하여 복구 가능한 항목 폴더의 감사 하위 폴더에 있는 항목의 크기와 수를 표시할 수 있습니다.

      ```PowerShell
      Get-MailboxFolderStatistics -Identity <MailboxIdentity> -FolderScope RecoverableItems | Where-Object {$_.Name -eq 'Audits'} | Format-List FolderPath,FolderSize,ItemsInFolder
      ```

    - 복구 가능한 항목 폴더의 감사 로그 레코드에 직접 액세스할 수 없습니다. 대신 **Search-MailboxAuditLog** cmdlet을 사용하거나 감사 로그를 검색하여 사서함 감사 레코드를 찾아 볼 수 있습니다.

- 사서함이 보류 중이거나 준수 센터의 보존 정책에 할당된 경우 감사 로그 레코드는 사서함의 *AuditLogAgeLimit* 속성(기본적으로 90일)으로 정의된 기간 동안 계속 보존됩니다. 보류된 사서함에 대해 감사 로그 레코드를 더 오래 유지하려면 *사서함의 AuditLogAgeLimit* 값을 증가해야 합니다.

- 다중 지리적 환경에서는 지역 횡단 사서함 감사가 지원되지 않습니다. 예를 들어 사용자가 다른 지리적 위치에서 공유 사서함에 액세스할 수 있는 권한을 할당받더라도 그 사용자가 수행한 사서함 작업이 공유 사서함의 사서함 감사 로그에 기록되지 않습니다.
