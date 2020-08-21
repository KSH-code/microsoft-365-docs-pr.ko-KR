---
title: 기본 연결 필터 정책 구성
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6ae78c12-7bbe-44fa-ab13-c3768387d0e3
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 관리자는 전자 메일 서버의 전자 메일을 허용하거나 차단하도록 EOP(Exchange Online Protection)에서 연결 필터링을 구성하는 방법에 대해 자세히 알아봅니다.
ms.openlocfilehash: 45213ff36c7efc76a83a2c520e0369211ffecf53
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827848"
---
# <a name="configure-connection-filtering"></a>연결 필터링 구성

Exchange Online 사서함이 있는 Microsoft 365 고객 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 고객인 경우 EOP의 연결 필터링(구체적으로는 기본 연결 필터 정책)을 사용하여 IP 주소로 좋은 원본 전자 메일 서버나 잘못된 원본 전자 메일 서버를 식별합니다. 기본 연결 필터 정책의 주요 구성 요소는 다음과 같습니다.

- **IP 허용 목록:** IP 주소 또는 IP 주소 범위로 지정한 원본 전자 메일 서버에서 들어오는 모든 메시지에 대한 스팸 필터링을 건너뜁니다. 이러한 원본에서 보낸 메시지에 스팸 필터링이 계속 발생할 수 있는 시나리오는 IP 허용 목록의 원본에서 보낸 메시지가 [여전히 이](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) 항목의 뒷부분에서 필터링되는 시나리오를 참조하십시오. IP 허용 목록이 전체 수신 허용 - 보낸 사람 전략에 맞게 적용될 지도에 대한 자세한 내용은 [EOP에서 수신 허용 - 보낸 사람 목록 만들기를 참조하세요.](create-safe-sender-lists-in-office-365.md)

- **IP 차단 목록:** IP 주소 또는 IP 주소 범위로 지정한 원본 전자 메일 서버에서 들어오는 메시지를 모두 차단합니다. 들어오는 메시지는 거부되고 스팸으로 표시되지 않은 것으로 표시되며 추가 필터링은 수행되지 않습니다. IP 차단 목록이 수신 거부 전략에 맞게 적용될 방식에 대한 자세한 내용은 [EOP에서 차단할 보낸 사람 목록 만들기를 참조하세요.](create-block-sender-lists-in-office-365.md)

- **수신 허용**목록: *수신 허용 목록은* Microsoft 데이터 센터의 동적 허용 목록으로서 고객의 구성이 필요하지 않습니다. Microsoft는 구독에서 다양한 타사 목록으로 신뢰할 수 있는 전자 메일 원본을 식별하고 있습니다. 수신 허용 목록을 사용하여 사용하거나 사용하지 않도록 설정할 수 있습니다. 수신 허용 목록에는 원본 전자 메일 서버를 구성할 수 없습니다. 수신 허용 목록에 있는 전자 메일 서버에서 받는 메시지에 대해 스팸 필터링을 건너뜁니다.

이 항목에서는 보안 & 준수 센터 또는 PowerShell(Exchange Online 사서함을 사용하는 Microsoft 365 조직의 Exchange Online PowerShell, Exchange Online 사서함이 없는 조직의 경우 독립 실행형 EOP PowerShell)에서 기본 연결 필터 정책을 구성하는 방법에 대해 설명합니다. EOP에서 연결 필터링을 사용하는 방법에 대한 자세한 내용은 스팸 방지 보호 [기능을 참조하십시오.](anti-spam-protection.md)

> [!NOTE]
> IP 허용 목록, 수신 허용 목록 및 IP 차단 목록은 전체적인 전략 중 하나로서 조직에서 전자 메일을 허용하거나 차단합니다. 자세한 내용은 수신 허용 - [보낸 사람 목록 만들기](create-safe-sender-lists-in-office-365.md) 및 [차단된 보낸 사람 목록 만들기를 참조하세요.](create-block-sender-lists-in-office-365.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- <https://protection.office.com/>에서 보안 및 준수 센터를 엽니다. **스팸 방지 설정** 페이지로 바로 이동하려면 <https://protection.office.com/antispam>을 사용하세요.

- Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요. 독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.

- 이 항목의 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다.

  - 기본 연결 필터 정책을 수정하려면 다음 역할 그룹 중 하나의 구성원이어야 합니다.

    - [보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **조직 관리** 또는 **보안 관리자**
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **조직 관리** 및 **예방 조치 관리**

  - 기본 연결 필터 정책에 대한 읽기 전용 액세스를 위해는 다음 역할 그룹 중 하나의 구성원이어야 합니다.

    - [보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **보안 읽기**
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리**

- 허용하거나 차단할 전자 메일 서버(보낸 사람)의 원본 IP 주소를 찾으려면 메시지 헤더에서**연결 IP(IP)** 헤더 필드를 확인하면 됩니다. 다양한 전자 메일 클라이언트에서 메시지 헤더를 보려면 [Outlook에서 인터넷 메시지 헤더를 확인하세요.](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c)

- IP 허용 목록은 IP 차단 목록보다 우선합니다(두 목록의 주소는 차단되지 않음).

- 각각 IP 허용 목록과 IP 차단 목록은 각각 최대 1,273개의 항목을 지원합니다. 여기서 항목이 단일 IP 주소, IP 주소 범위 또는 CIDR(Classless InterDomain Routing) IP입니다.

## <a name="use-the-security--compliance-center-to-modify-the-default-connection-filter-policy"></a>보안 그룹 & 센터를 사용하여 기본 연결 필터 정책 수정

1. 보안 센터에서 & 위협 관리 **정책 스팸** \> **방지로** \> **이동합니다.**

2. 스팸 방지 **설정 페이지에서 확장 아이콘을** 클릭한 **다음 편집 정책을** ![ 클릭하여 연결 필터 ](../../media/scc-expand-icon.png) 정책을 **확장합니다.**

3. 표시되는 **기본** 플라이아웃에서 다음 설정을 구성합니다.

   - **설명:** 선택적 설명 텍스트를 입력합니다.

   - **IP 허용 목록:** Click **Edit**. 표시되는 **IP 허용 목록** 플라이아웃에서 다음 구문을 사용하여 **주소 또는 주소 범위 상자에** IPV4 주소를 입력합니다.

     - 단일 IP: 예: 192.168.1.1.

     - IP 범위: 예: 192.168.0.1-192.168.0.254

     - CIDR IP: 예: 192.168.0.1/25. 유효한 네트워크 마스크 값은 /24-/32입니다. CIDR IP 마스크 값/1에서 /23까지 스팸 필터링을 건너뛰려면 이 항목의 [뒷부분에서 사용 가능한 범위 외부의 CIDR IP에](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) 대한 스팸 필터링 건너뛰기를 참조하세요.

     IP 주소 또는 주소 범위를 추가하려면 아이콘 **추가를** ![ ](../../media/ITPro-EAC-AddIcon.png) 클릭합니다. 항목을 제거하려면 허용되는 IP 주소에서 **항목을 선택한 다음** 제거를 **클릭합니다.** ![ ](../../media/scc-remove-icon.png) 작업을 마쳤으면 **저장**을 클릭합니다.

   - **IP 차단 목록:** 클릭 **.** 표시되는 **Address or address range** **IP 차단 목록 플라이아웃의** 이전에 IP 허용 목록 설정에 설명된 것과 같이 주소 나는 주소 범위 상자에 IP, IP 범위 또는 CIDR **IP를 하나 입력합니다.**

     IP 주소 또는 주소 범위를 추가하려면 아이콘 **추가를** ![ ](../../media/ITPro-EAC-AddIcon.png) 클릭합니다. 항목을 제거하려면 차단된 **IP 주소에서 항목을 선택한 다음** 제거를 **Remove** ![ ](../../media/scc-remove-icon.png) 클릭합니다. 작업을 마쳤으면 **저장**을 클릭합니다.

   - **수신 허용 목록 켜기**: 수신 허용 목록을 사용하여 스팸 필터링을 건너뛰는 알려진 올바른 보낸 사람을 식별하도록 설정하거나 사용하지 않도록 설정합니다.

4. 작업을 마쳤으면 **저장**을 클릭합니다.

## <a name="use-the-security--compliance-center-to-view-the-default-connection-filter-policy"></a>Security & 센터를 사용하여 기본 연결 필터 정책 확인

1. 보안 센터에서 & 위협 관리 **정책 스팸** \> **방지로** \> **이동합니다.**

2. 스팸 **방지 설정 페이지에서 연결** 필터 정책이라는 기본 정책 옆에 있는 **드롭다운을 클릭합니다.**

3. 이 정책 설정은 열리는 드롭다운에 표시됩니다.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-modify-the-default-connection-filter-policy"></a>Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell을 사용하여 기본 연결 필터 정책 수정

다음 구문을 사용합니다.

```powershell
Set-HostedConnectionFilterPolicy -Identity Default [-AdminDisplayName <"Optional Comment">] [-EnableSafeList <$true | $false>] [-IPAllowList <IPAddressOrRange1,IPAddressOrRange2...>] [-IPBlockList <IPAddressOrRange1,IPAddressOrRange2...>]
```

**참고:**

- 유효한 IP 주소 또는 주소 범위 값은 다음과 같습니다.

  - 단일 IP: 예: 192.168.1.1.

  - IP 범위: 예: 192.168.0.1-192.168.0.254

  - CIDR IP: 예: 192.168.0.1/25. 유효한 네트워크 마스크 값은 /24-/32입니다.

- 지정한 *값으로* 기존 항목을 덮어쓰려면 다음 구문을 `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN` 사용합니다.

- 기존의 *다른 항목에 영향을* 주지 않고 IP 주소 또는 주소 범위를 추가하거나 제거하려면 다음 구문을 사용합니다. `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}`

- IP 허용 목록 또는 IP 차단 목록을 비우려면 값을 `$null` 사용합니다.

다음 예에서는 지정된 IP 주소 및 주소 범위를 사용하여 IP 허용 목록과 IP 차단 목록을 구성합니다.

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList 192.168.1.10,192.168.1.23 -IPBlockList 10.10.10.0/25,172.17.17.0/24
```

이 예에서는 지정된 IP 주소 및 주소 범위를 IP 허용 목록에서 추가 및 제거합니다.

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList @{Add="192.168.2.10","192.169.3.0/24","192.168.4.1-192.168.4.5";Remove="192.168.1.10"}
```

구문과 매개 변수에 대한 자세한 내용은 [Set-HostedConnectionFilterPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/set-hostedconnectionfilterpolicy)

## <a name="how-do-you-know-this-worked"></a>작동 여부는 어떻게 확인하나요?

기본 연결 필터 정책이 수정되었는지 확인하려면 다음 단계를 수행합니다.

- 보안 감사 & 센터에서 위협 관리 **정책** 스팸 방지 \> **Policy** \> **정책인 도메인** 방지 \> **정책(항상 ON) 옆에**있는 드롭다운을 클릭하여 설정을 확인합니다.

- Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell에서 다음 명령을 실행하여 설정을 확인합니다.

  ```powershell
  Get-HostedConnectionFilterPolicy -Identity Default
  ```

- IP 허용 목록의 항목으로 테스트 메시지를 보냅니다.

## <a name="additional-considerations-for-the-ip-allow-list"></a>IP 허용 목록에 대한 추가 고려 사항

다음 섹션에서는 IP 허용 목록을 구성할 때 알아야 할 추가 항목을 식별합니다.

### <a name="skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range"></a>사용할 수 있는 범위 외부의 CIDR IP에 대한 스팸 필터링 건너뛰기

이 항목의 앞부분에서 설명한 것과 같이 네트워크 마스크 /24와 함께 IP 허용 목록의 CIDR IP만 사용할 수 있습니다. /1 -23 범위에 있는 원본 전자 메일 서버에서 보낸 메시지에 대해 스팸 필터링을 건너뛰려면 Exchange 메일 흐름 규칙(전송 규칙이라고도 함)을 사용해야 합니다. 그러나 Microsoft 전용 또는 타사 차단 목록에 /1에서 /23 CIDR IP 주소의 IP 주소가 표시되면 메시지는 차단되므로 가능한 경우에는 메시지가 차단되지 않습니다.

이제 잠재적인 문제를 완전히 인식하므로 다음 설정(최소)을 사용하여 메일 흐름 규칙을 만들고 이러한 IP 주소에서 보내는 메시지가 스팸 필터링을 건너뛰도록 할 수 있습니다.

- 규칙 조건: 보낸 사람 IP **주소가** 이러한 범위에 있거나 정확히 일치하는 경우 이 규칙을 \> **The sender** \> **IP address is in any of these ranges or exactly matches** \> 적용합니다(사용자가 /1-/23 네트워크 마스크와 함께 CIDR IP입력).

- 규칙 작업: **메시지 속성** \> **SCL(스팸 지수) 스팸** 필터링 \> **무시를 수행합니다.**

규칙을 감사하고 규칙을 테스트하고 특정 기간 동안 규칙을 활성화하는 등 다른 선택 항목을 지정할 수 있습니다. 옵션을 적용하기 전에 규칙을 테스트하는 것이 좋습니다. 자세한 내용은 [Exchange Online의 메일 흐름 규칙 관리를 참조하세요.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules)

### <a name="skip-spam-filtering-on-selective-email-domains-from-the-same-source"></a>동일한 원본에서 선택한 전자 메일 도메인에 대한 스팸 필터링 건너뛰기

일반적으로 IP 주소 또는 주소 범위를 IP 허용 목록에 추가하면 해당 전자 메일 원본에서 들어오는 모든 메시지를 신뢰하는 것입니다. 그러나 해당 원본이 여러 도메인에서 전자 메일을 보내고 해당 도메인 중 일부에 대한 스팸 필터링은 건너뛰려는 경우 해당 도메인 중 일부에 대한 스팸 필터링은 건너뛰려는 경우는? 이 작업에 IP 허용 목록만 사용할 수 없지만 메일 흐름 규칙과 함께 IP 허용 목록을 사용할 수 있습니다.

예를 들어 원본 전자 메일 서버 192.168.1.25에서 도메인 contoso.com, fabrikam.com 및 tailspintoys.com에서 전자 메일을 보내지만, 조직의 보낸 사람이 보낸 메시지에 대한 스팸 필터링만 fabrikam.com. 이렇게 하려면 다음 단계를 사용합니다.

1. IP 허용 목록에 192.168.1.25를 추가합니다.

2. 다음 설정을 사용하여 메일 흐름 규칙을 구성합니다(최소한).

   - 규칙 조건: **보낸 사람** IP 주소가 \> **The sender** \> **해당 범위에 있거나** \> 192.168.1.25(이전 단계에서 IP 허용 목록에 추가한 동일한 IP 주소 또는 주소 범위)에 해당하는 경우 이 규칙을 적용합니다.

   - 규칙 작업: **메시지 속성** \> **SCL(스팸 지수) 0을** \> **수정합니다.**

   - 규칙 예외: **보낸** \> **사람 도메인이** \> fabrikam.com(스팸 필터링을 건너뛰려는 도메인만 해당).

### <a name="scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered"></a>IP 허용 목록의 소스에서 보낸 메시지가 여전히 필터링되는 시나리오

다음 시나리오에서는 IP 허용 목록의 전자 메일 서버에서 보내는 메시지가 여전히 스팸 필터링의 적용을 받습니다.

- IP 허용 목록의 IP 주소도 Microsoft 365의 모든 테넌트의 온-프레미스, IP 기반 인바운드 커넥터(이 테넌트 A를 종종 회사에 전화) **및** 테넌트 A와 EOP 서버에서 구성되어 있습니다. 이 두 메시지는 Microsoft 데이터 센터의 *같은* Active Directory 포리스트에 있을 예정입니다. *any* 이 시나리오에서는 **IPV:CAL이** *is* 메시지의 스팸 방지 메시지 [헤더에](anti-spam-message-headers.md) 추가되었지만(메시지가 스팸 필터링을 무시한다는 것), 메시지에는 여전히 스팸 필터링이 적용됩니다.

- IP 허용 목록과 EOP 서버가 모두 포함된 테넌트가 Microsoft 데이터 센터의 *서로* 다른 Active Directory 포리스트에 있을 예정입니다. 이 **시나리오에서는 IPV:CAL이** *메시지* 헤더에 추가되지 않기므로 메시지에 여전히 스팸 필터링이 적용됩니다.

이러한 두 시나리오 중 하나가 발생하면 다음 설정(최소한) 메일 흐름 규칙을 만들 수 있습니다. 그 중 하나는 문제가 있는 IP 주소에서 보내는 메시지의 스팸 필터링을 건너뛰도록 할 수 있습니다.

- 규칙 조건: **보낸 사람 IP** \> **주소가 이러한** \> **범위에 있거나 정확히** 일치하는 \> 경우(IP 주소 또는 주소) 이 규칙을 적용합니다.

- 규칙 작업: **메시지 속성** \> **SCL(스팸 지수) 스팸** 필터링 \> **무시를 수행합니다.**

## <a name="new-to-microsoft-365"></a>Microsoft 365를 새로운 사항?

|<!-- a -->|
|---|
|![LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New의** 짧은 아이콘 LinkedIn Learning에서 **제공한 관리자**및 IT 전문가의 무료 비디오 과정을 확인해보세요.|
|
