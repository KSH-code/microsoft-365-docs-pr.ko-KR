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
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: 6ae78c12-7bbe-44fa-ab13-c3768387d0e3
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 관리자는 전자 메일 서버에서 전자 메일을 허용하거나 차단하도록 EOP(Exchange Online Protection)에서 연결 필터링을 구성하는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5b59e7a5ed37cb4694ae72759815b46b1248c09f
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60209000"
---
# <a name="configure-connection-filtering"></a>연결 필터링 구성

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)


Microsoft 365 사서함이 있는 Microsoft 365 고객 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(독립 실행형 Exchange Online Protection) 고객인 경우 EOP의 연결 필터링(특히 기본 연결 필터 정책)을 사용하여 양호하거나 잘못된 원본을 식별합니다 Exchange Online. IP 주소로 전자 메일 서버 기본 연결 필터 정책의 주요 구성 요소는 다음과 같습니다.

- **IP 허용 목록: IP** 주소 또는 IP 주소 범위로 지정한 원본 전자 메일 서버에서 들어오는 모든 메시지에 대해 스팸 필터링을 건너뜁습니다. 이러한 원본의 메시지에서 스팸 필터링이 계속 발생할 수 있는 시나리오는 이 문서 의 부분에 있는 [IP](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) 허용 목록의 원본에서 보낸 메시지가 여전히 필터링되는 시나리오 섹션을 참조하세요. IP 허용 목록이 전반적인 수신 허용 - 보낸 사람 전략에 적합한 방법에 대한 자세한 내용은 EOP에서 수신 허용 - 보낸 사람 목록 [만들기를 참조하세요.](create-safe-sender-lists-in-office-365.md)

- **IP 차단 목록:** IP 주소 또는 IP 주소 범위로 지정한 원본 전자 메일 서버에서 들어오는 모든 메시지를 차단합니다. 들어오는 메시지는 거부되어 스팸으로 표시되지 않습니다. 추가 필터링이 일어나지 않습니다. IP 차단 목록이 전체 수신 차단된 보낸 사람 전략에 적합한 방법에 대한 자세한 내용은 EOP에서 차단 보낸 사람 목록 [만들기를 참조하세요.](create-block-sender-lists-in-office-365.md)

- **금고 목록:** *안전한* 목록은 고객 구성이 필요 없는 Microsoft 데이터 센터의 동적 허용 목록입니다. Microsoft는 구독에서 다양한 타사 목록으로의 이러한 신뢰할 수 있는 전자 메일 원본을 식별합니다. 안전한 목록의 사용을 활성화 또는 비활성화합니다. 수신 확인 목록에 원본 전자 메일 서버를 구성할 수 없습니다. 스팸 필터링은 수신 확인 목록의 전자 메일 서버에서 들어오는 메시지에서 건너뜁니다.

이 문서에서는 Microsoft 365 Microsoft 365 Defender 포털 또는 PowerShell(Exchange Online PowerShell for Microsoft 365 조직에 사서함이 있는 조직용 PowerShell)에서 기본 연결 필터 정책을 구성하는 Exchange Online. 사서함이 없는 조직의 독립 실행형 EOP PowerShell Exchange Online) EOP에서 연결 필터링을 사용하는 방법에 대한 자세한 내용은 스팸 방지 보호를 [참조하세요.](anti-spam-protection.md)

> [!NOTE]
> IP 허용 목록, 수신 허용 목록 및 IP 차단 목록은 조직의 전자 메일을 허용하거나 차단하는 전체 전략의 일부입니다. 자세한 내용은 [수신이](create-safe-sender-lists-in-office-365.md) 가능한 보낸 사람 목록 만들기 및 수신이 차단된 보낸 [사람 목록 만들기를 참조하세요.](create-block-sender-lists-in-office-365.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- <https://security.microsoft.com>에서 Microsoft 365 Defender 포털을 엽니다. **스팸 방지 정책** 페이지로 직접 이동하려면 <https://security.microsoft.com/antispam>을(를) 사용합니다.

- Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요. 독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.

- 이 게시물의 절차를 수행하려면 먼저 **Exchange Online** 에서 사용 권한을 할당받아야 합니다.
  - 기본 연결 필터 정책을 수정하려면 조직 관리 또는  보안 관리자 역할 그룹의 **구성원이** 되어야 합니다.
  - 기본 연결 필터 정책에 대한 읽기 전용 액세스의 경우  전역 읽기 사용자 또는 보안 읽기 권한이 있는 역할 그룹의 **구성원이면** 됩니다.

  자세한 내용은 [Exchange Online의 사용 권한](/exchange/permissions-exo/permissions-exo)을 참조하세요.

  **참고**:

  - Microsoft 365 관리 센터의 해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 필요한 권한 _및_ Microsoft 365의 다른 기능에 대한 권한이 부여됩니다. 자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.
  - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리** 역할 그룹에도 기능에 대한 읽기 전용 권한을 부여합니다.

- 허용하거나 차단할 전자 메일 서버(보낸 사람)의 원본 IP 주소를 찾으면 메시지 헤더에서 연결 **IP(CIP)** 헤더 필드를 확인할 수 있습니다. 다양한 전자 메일 클라이언트에서 메시지 헤더를 확인하려면 에서 인터넷 메시지 [헤더 보기를 Outlook.](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c)

- IP 허용 목록이 IP 차단 목록보다 우선합니다(두 목록의 주소가 모두 차단되지 않습니다).

- IP 허용 목록 및 IP 차단 목록은 각각 하나의 IP 주소, IP 주소 범위 또는 CIDR(Classless InterDomain Routing) IP인 최대 1273 항목을 지원합니다.

## <a name="use-the-microsoft-365-defender-portal-to-modify-the-default-connection-filter-policy"></a>기본 Microsoft 365 Defender 포털을 사용하여 기본 연결 필터 정책 수정

1. Microsoft 365 Defender 포털의 **정책** 섹션에서 **전자 메일 및 공동 작업**\>**정책 및 규칙**\>**위협 정책**\>**스팸 방지** 로 이동합니다.

2. 스팸 **방지 정책 페이지의** 정책  이름을 클릭하여 목록에서 연결 필터 정책(기본값)을 선택합니다.

3. 정책 세부 정보 플라이아웃이 나타나면 다음 설정을 구성합니다.

   - **설명** 섹션: 이름 **및 설명 편집을 클릭합니다.** 나타나는 **이름 및** 설명 편집 플라이아웃에서 설명 상자에 선택적 설명 텍스트를 **입력합니다.**

     작업을 마쳤으면 **저장** 을 클릭합니다.

   - **연결 필터링 섹션:** 연결 **필터 정책 편집을 클릭합니다.** 플라이아웃이 나타나면 다음 설정을 구성합니다.

     - **항상 다음 IP 주소** 또는 주소 범위의 메시지를 허용합니다. IP 허용 목록입니다. 상자를 클릭하고 값을 입력한 다음 Enter를 누르거나 상자 아래에 표시되는 전체 값을 선택합니다. 유효한 값:
       - 단일 IP: 예: 192.168.1.1.
       - IP 범위: 예: 192.168.0.1-192.168.0.254.
       - CIDR IP: 예: 192.168.0.1/25. 유효한 서브넷 마스크 값은 /24에서 /32까지입니다. /1 ~ /23에 대한 스팸 필터링을 건너뛰기 위해 이 문서 의 부분에 있는 사용 가능한 범위 밖에 있는 [CIDR IP에](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) 대한 스팸 필터링 건너뛰기 섹션을 참조하세요.

       필요한 만큼 이 단계를 반복합니다. 기존 값을 제거하려면 제거를 클릭합니다. ![제거 아이콘.](../../media/m365-cc-sc-remove-selection-icon.png) 값 옆에 있습니다.

     IP 주소 또는 주소 범위를 추가하려면 상자를 클릭하고  추가 아이콘 ![ 추가를 입력합니다. ](../../media/ITPro-EAC-AddIcon.png) 항목을 제거하려면 **허용된 IP** 주소의 항목을 선택한 다음 제거 **를** ![ ](../../media/scc-remove-icon.png) 클릭합니다. 작업을 마쳤으면 **저장** 을 클릭합니다.

   - **항상 다음 IP 주소** 또는 주소 범위의 메시지를 차단합니다. IP 차단 목록입니다. 다음 IP 주소 또는 주소 범위의 메시지 항상 허용 설정에 설명된 바와 같이 상자에 단일 IP, IP 범위 또는 CIDR **IP를 입력합니다.**

   - **수신 가능 목록 켜기**: 수신 가능 목록을 사용하여 스팸 필터링을 건너뛰는 알려진 좋은 보낸 사람 식별을 사용하도록 설정하거나 사용하지 않도록 설정 안전한 목록을 사용하려면 확인란을 선택합니다.

   작업을 마쳤으면 **저장** 을 클릭합니다.

4. 정책 세부 정보 플라이아웃으로 돌아와 **닫기** 를 클릭합니다.

## <a name="use-the-microsoft-365-defender-portal-to-view-the-default-connection-filter-policy"></a>기본 Microsoft 365 Defender 포털을 사용하여 기본 연결 필터 정책 보기

1. Microsoft 365 Defender 포털의 **정책** 섹션에서 **전자 메일 및 공동 작업**\>**정책 및 규칙**\>**위협 정책**\>**스팸 방지** 로 이동합니다.

2. 스팸 **방지 정책 페이지에는** 정책 목록에 다음 속성이 표시됩니다.

   - **이름:** 이 값은 기본 연결 필터 정책에 대한 연결 필터 정책(기본값)입니다. 
   - **Status:** 이 값은 **기본** 연결 필터 정책에 대해 항상 설정되어 있습니다.
   - **우선** 순위: 기본 연결 필터 정책의 경우 **이** 값은 가장 낮습니다.
   - **Type**: 이 값은 기본 연결 필터 정책에 비어 있습니다.

3. 기본 연결 필터 정책을 선택하면 정책 설정이 플라이아웃에 표시됩니다.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-modify-the-default-connection-filter-policy"></a>PowerShell Exchange Online 독립 실행형 EOP PowerShell을 사용하여 기본 연결 필터 정책 수정

다음 구문을 사용합니다.

```powershell
Set-HostedConnectionFilterPolicy -Identity Default [-AdminDisplayName <"Optional Comment">] [-EnableSafeList <$true | $false>] [-IPAllowList <IPAddressOrRange1,IPAddressOrRange2...>] [-IPBlockList <IPAddressOrRange1,IPAddressOrRange2...>]
```

**참고**:

- 유효한 IP 주소 또는 주소 범위 값은 같습니다.
  - 단일 IP: 예: 192.168.1.1.
  - IP 범위: 예: 192.168.0.1-192.168.0.254.
  - CIDR IP: 예: 192.168.0.1/25. 유효한 네트워크 마스크 값은 /24 ~/32입니다.
- 지정한 *값으로* 기존 항목을 덮어치기 위해 다음 구문을 `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN` 사용합니다.
- 다른 *기존 항목에 영향을* 주지 않고 IP 주소 또는 주소 범위를 추가하거나 제거하려면 다음 구문을 `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}` 사용합니다. .
- IP 허용 목록 또는 IP 차단 목록을 비우기 위해 값을 `$null` 사용하세요.

이 예에서는 지정된 IP 주소 및 주소 범위를 사용하여 IP 허용 목록 및 IP 차단 목록을 구성합니다.

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList 192.168.1.10,192.168.1.23 -IPBlockList 10.10.10.0/25,172.17.17.0/24
```

이 예에서는 IP 허용 목록에서 지정된 IP 주소 및 주소 범위를 추가하고 제거합니다.

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList @{Add="192.168.2.10","192.169.3.0/24","192.168.4.1-192.168.4.5";Remove="192.168.1.10"}
```

구문과 매개 변수에 대한 자세한 내용은 [Set-HostedConnectionFilterPolicy를 참조하십시오.](/powershell/module/exchange/set-hostedconnectionfilterpolicy)

## <a name="how-do-you-know-this-worked"></a>작동 여부는 어떻게 확인하나요?

기본 연결 필터 정책이 성공적으로 수정되어 있는지 확인하기 위해 다음 단계를 수행합니다.

- Microsoft 365 Defender 포털에서 전자 메일 **&** 공동 작업 정책 & 규칙 위협 정책 스팸 방지 정책으로 이동하여 정책 이름을 클릭하여 목록에서 연결 필터 정책(기본값)을 선택하고 설정을 \>  \>  \>   \> 확인합니다. 

- PowerShell Exchange Online 독립 실행형 EOP PowerShell에서 다음 명령을 실행하고 설정을 확인합니다.

  ```powershell
  Get-HostedConnectionFilterPolicy -Identity Default
  ```

- IP 허용 목록의 항목에서 테스트 메시지를 전송합니다.

## <a name="additional-considerations-for-the-ip-allow-list"></a>IP 허용 목록에 대한 추가 고려 사항

다음 섹션에서는 IP 허용 목록을 구성할 때 알아야 할 추가 항목을 식별합니다.

### <a name="skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range"></a>사용 가능한 범위를 밖 CIDR IP에 대한 스팸 필터링 건너뛰기

이 문서의 앞부분에서 설명한 대로 IP 허용 목록에서 네트워크 마스크 /24 ~ /32가 있는 CIDR IP만 사용할 수 있습니다. /1에서 /23 범위의 원본 전자 메일 서버에서 보낸 메시지에 대해 스팸 필터링을 건너뛰기 위해 전송 규칙 Exchange 메일 흐름 규칙(전송 규칙)을 사용해야 합니다. 그러나 /1 ~ /23 CIDR IP 범위의 IP 주소가 Microsoft의 독점 또는 타사 차단 목록에 나타나는 경우 메시지가 차단될 것이기 때문에 가능한 경우 이 작업을 하지 않는 것이 좋습니다.

이제 잠재적인 문제를 완전히 인식했기 때문에 최소한 다음 설정을 사용하여 메일 흐름 규칙을 만들어 이러한 IP 주소의 메시지가 스팸 필터링을 건너뛰게 할 수 있습니다.

- 규칙 **조건:** 보낸 사람 IP 주소가 이러한 범위에 있는 경우 또는 정확히 일치하는 경우 이 규칙을 적용합니다(/1 ~ /23 네트워크 마스크를 사용하여 \>  \>  \> CIDR IP 입력).
- 규칙 작업: **메시지 속성 수정** \> **SCL(스팸 지수)** 스팸 필터링 무시를 \> **설정합니다.**

규칙을 감사하고, 규칙을 테스트하고, 특정 기간 동안 규칙을 활성화하는 등 기타 선택을 할 수 있습니다. 옵션을 적용하기 전에 규칙을 테스트하는 것이 좋습니다. 자세한 내용은 [Manage mail flow rules in Exchange Online.](/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules)

### <a name="skip-spam-filtering-on-selective-email-domains-from-the-same-source"></a>동일한 원본에서 선택적 전자 메일 도메인에 대한 스팸 필터링 건너뛰기

일반적으로 IP 허용 목록에 IP 주소 또는 주소 범위를 추가하면 해당 전자 메일 원본에서 들어오는 모든 메시지를 신뢰하게 됩니다. 그러나 해당 원본이 여러 도메인에서 전자 메일을 보내고 해당 도메인 중 일부에 대해 스팸 필터링을 건너뛰고 다른 도메인은 건너뛰고 싶은 경우에는 어떻게 하나요? IP 허용 목록만 사용하여 이 작업을 할 수 없지만 메일 흐름 규칙과 함께 IP 허용 목록을 사용할 수 있습니다.

예를 들어 원본 전자 메일 서버 192.168.1.25는 도메인 contoso.com, fabrikam.com 및 tailspintoys.com 에서 전자 메일을 보내지만 도메인의 보낸 사람이 보낸 메시지에 대한 스팸 필터링만 건너뛰 fabrikam.com. 이 작업을 수행하기 위해 다음 단계를 수행합니다.

1. IP 허용 목록에 192.168.1.25를 추가합니다.

2. 최소한 다음 설정을 사용하여 메일 흐름 규칙을 구성합니다.
   - 규칙 **조건:** 보낸 사람 IP 주소가 이러한 범위에 있는 경우 또는 \>  \>  \> 정확히 192.168.1.25(이전 단계에서 IP 허용 목록에 추가한 IP 주소 또는 주소 범위)가 정확히 일치하는 경우 이 규칙을 적용합니다.
   - 규칙 작업: **메시지 속성 수정** \> **SCL(스팸 지수)** \> **0을 지정합니다.**
   - 규칙 예외: **보낸** 사람 도메인이 fabrikam.com(스팸 필터링을 건너뛰는 도메인만 해당) \>  \>

### <a name="scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered"></a>IP 허용 목록의 원본에서 보낸 메시지가 여전히 필터링되는 시나리오

IP 허용 목록의 전자 메일 서버에서 보낸 메시지는 다음과 같은 시나리오에서 여전히 스팸 필터링이 적용될 수 있습니다.

- IP 허용 목록의 IP 주소는 Microsoft 365(이 테넌트 A를 호출)  테넌트의 모든 테넌트의 IP 기반 인바운드 커넥터와 Microsoft 데이터 센터의 동일한 *Active* Directory 포리스트에 있는 테넌트 A 및 EOP 서버에서도 구성됩니다.  이 시나리오에서는 **IPV:CAL이**  메시지의 스팸 [](anti-spam-message-headers.md) 방지 메시지 헤더에 추가되지만(메시지가 스팸 필터링을 무시한 경우) 여전히 스팸 필터링이 적용되어 있습니다.

- IP 허용 목록과 메시지를 처음 접하는 EOP 서버를 포함하는 테넌트는 모두 Microsoft 데이터 센터의 다른 *Active* Directory 포리스트에 있습니다. 이 시나리오에서는 **IPV:CAL이**  메시지 헤더에 추가되지 않습니다. 따라서 메시지에는 여전히 스팸 필터링이 적용되어 있습니다.

이러한 시나리오 중 하나에 해당되는 경우 최소한 다음 설정을 사용하여 메일 흐름 규칙을 만들어 문제가 있는 IP 주소의 메시지가 스팸 필터링을 건너뛰게 할 수 있습니다.

- 규칙 조건: **보낸** 사람 IP 주소가 이러한 범위에 있는 경우 또는 정확히 일치하는 경우(IP 주소 또는 주소) 이 \>  \>  \> 규칙을 적용합니다.
- 규칙 작업: **메시지 속성 수정** \> **SCL(스팸 지수)** 스팸 필터링 무시를 \> **설정합니다.**

## <a name="new-to-microsoft-365"></a>새 Microsoft 365?

****

![LinkedIn Learning용 짧은 아이콘.](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **새 Microsoft 365?** LinkedIn 관리자가 제공한 Microsoft 365 **및 IT** 프로를 위한 무료 비디오 과정을 Learning.
