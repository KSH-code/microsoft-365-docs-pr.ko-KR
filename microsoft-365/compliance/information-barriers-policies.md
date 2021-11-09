---
title: 정보 장벽 시작
description: 정보 장벽을 시작하는 방법을 배워야 합니다.
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
ms.localizationpriority: ''
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ec745f46790ee6d230266f010a9311e1cebb12cc
ms.sourcegitcommit: 6d470e37b2a1c40c7f31c2365ae654a3c35d7674
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60834105"
---
# <a name="get-started-with-information-barriers"></a>정보 장벽 시작

정보 장벽을 사용하여 특정 사용자 세그먼트가 서로 통신하지 못하게 하거나 특정 세그먼트가 특정 다른 세그먼트와만 통신할 수 있도록 설계된 정책을 정의할 수 있습니다. 정보 장벽 정책은 조직이 관련 산업 표준 및 규정을 준수하고 잠재적인 이해 관계 충돌을 방지하는 데 도움이 될 수 있습니다. 자세한 내용은 [정보 장벽에 대한 자세한 정보를 참조하세요.](information-barriers.md)

이 문서에서는 정보 장벽 정책을 구성하는 방법에 대해 설명하고 있습니다. 여러 단계가 관련이 있으므로 정보 장벽 정책 구성을 시작하기 전에 전체 프로세스를 검토해야 합니다.

> [!TIP]
> 이 문서에는 정보 장벽 [정책을](#example-scenario-contosos-departments-segments-and-policies) 계획하고 정의하는 데 도움이 되는 예제 시나리오가 포함되어 있습니다.

## <a name="concepts"></a>개념

정보 장벽에 대한 정책을 정의하면 사용자 계정 특성, 세그먼트, '차단' 및/또는 '허용' 정책 및 정책 응용 프로그램을 사용할 수 있습니다.

- 사용자 계정 특성은 Azure Active Directory(또는 Exchange Online)에서 정의합니다. 이러한 특성에는 부서, 직위, 위치, 팀 이름 및 기타 직무 프로필 세부 정보가 포함됩니다.
- 세그먼트는 선택한 사용자 계정 특성을 사용하여 Microsoft 365 규정 준수 센터 사용자 **집합입니다.** ([지원되는 특성 목록](information-barriers-attributes.md)을 참조)
- 정보 장벽 정책은 통신 한도 또는 제한을 결정합니다. 정보 장벽 정책을 정의할 경우, 두 가지 정책 중에서 선택할 수 있습니다.
  - *차단* 정책은 하나의 세그먼트가 다른 세그먼트와 통신할 수 없도록 차단합니다.
  - *허용* 정책은 하나의 세그먼트가 특정한 다른 세그먼트와만 통신하도록 허용합니다.
- 정책 적용은 모든 정보 장벽 정책이 정의되고 조직에 적용할 준비가 된 후에 이루어집니다.

## <a name="configuration-at-a-glance"></a>구성 한눈에 보기

| **단계** | **관련 항목** |
|:------|:----------------|
| **1단계:** 선행 단계를 [충족하는지 확인](#step-1-make-sure-prerequisites-are-met) | - 필요한 라이선스 및 사용 [권한이 있는지 확인](information-barriers.md#required-licenses-and-permissions)<br/>- 디렉터리에 사용자 분할에 대한 데이터가 포함되어 있는지 확인<br/>- 사용자에 대해 범위가 지정 된 디렉터리 검색을 Microsoft Teams<br/>- 감사 로깅이 켜져 있는지 확인<br/>- 주소 Exchange 정책이 없는지 확인<br/>- PowerShell 사용(예제 제공)<br/>- 사용자에 대한 관리자 동의 Microsoft Teams(단계 포함) |
| **2단계:** [조직에서 사용자 세그먼트화](#step-2-segment-users-in-your-organization) | - 필요한 정책 결정<br/>- 정의할 세그먼트 목록 만들기<br/>- 사용할 특성 식별<br/>- 정책 필터 측면에서 세그먼트 정의 |
| **3단계:** [정보 장벽 정책 정의](#step-3-define-information-barrier-policies) | - 정책 정의(아직 적용되지 않습니다)<br/>- 두 가지 종류(차단 또는 허용) 중 선택 |
| **4단계:** [정보 장벽 정책 적용](#step-4-apply-information-barrier-policies) | - 정책을 활성 상태로 설정<br/>- 정책 응용 프로그램 실행<br/>- 정책 상태 보기 |
| **5단계:** 사용자 및 사용자에 대한 정보 SharePoint [OneDrive 구성(선택 사항)](#step-5-configuration-for-information-barriers-on-sharepoint-and-onedrive) | - 사용자 및 사용자에 대한 정보 장벽 SharePoint OneDrive |
| **6단계:** [정보 장벽 모드(선택 사항)](#step-6-information-barriers-modes-preview) | - 해당하는 경우 정보 장벽 모드 업데이트 |

## <a name="step-1-make-sure-prerequisites-are-met"></a>1단계: 선행 단계를 충족하는지 확인

필요한 라이선스 [및](information-barriers.md#required-licenses-and-permissions)사용 권한 외에도 정보 장벽을 구성하기 전에 다음 요구 사항을 충족해야 합니다.

- **디렉터리 데이터:** 조직의 구조가 디렉터리 데이터에 반영해야 합니다. 이 작업을 수행하려면 그룹 구성원 자격, 부서 이름 등의 사용자 계정 특성이 Azure Active Directory(또는 Exchange Online) 채워야 합니다. 자세한 내용은 다음 리소스를 참조하세요.
  - [정보 장벽 정책의 속성](information-barriers-attributes.md)
  - [사용자 프로필 정보를 사용하여 사용자 프로필 정보 추가 또는 Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)
  - [Office 365 PowerShell를 사용 하 여 사용자 계정 속성 구성](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md)

- **범위 디렉터리 검색:** 조직의 첫 번째 정보 장벽 정책을 정의하기 전에 에서 범위가 지정한 디렉터리 검색을 [사용하도록 Microsoft Teams.](/MicrosoftTeams/teams-scoped-directory-search) 정보 장벽 정책을 설정하거나 정의하기 전에 범위가 지정한 디렉터리 검색을 사용하도록 설정한 후 24시간 이상 기다릴 수 있습니다.

- **Exchange Online 라이선스:** 정보 장벽 정책은 대상 사용자에게 라이선스가 할당된 Exchange Online 적용됩니다.

- **감사 로깅이** 사용하도록 설정되어 있는지 확인: 정책 응용 프로그램의 상태를 확인하려면 감사 로깅을 설정해야 합니다. 감사는 기본적으로 Microsoft 365 사용하도록 설정되어 있습니다. 일부 조직에서는 특정 이유로 감사를 사용하지 않도록 설정한 경우도 있습니다. 조직에서 감사를 사용하지 않도록 설정한 경우 다른 관리자가 감사 기능을 해제한 것일 수 있습니다. 이 단계를 완료할 때 감사를 다시 설정하는 것이 좋습니다. 자세한 내용은 [감사 로그 검색 설정 및 해제](turn-audit-log-search-on-or-off.md)를 참조하세요.

- **주소장 정책** 없음: 정보 장벽 정책을 정의하고 적용하기 전에 주소 Exchange 정책이 적용되어 있는지 확인하지 않습니다. 정보 장벽은 주소록 정책을 기반으로 하지만 두 종류의 정책은 호환되지 않습니다. 이러한 정책이 있는 경우 먼저 주소부 정책을 [제거해야](/exchange/address-books/address-book-policies/remove-an-address-book-policy) 합니다. 정보 장벽 정책을 사용하도록 설정하고 계층적 주소 예약을 사용하도록 **** 설정하면 정보 장벽 세그먼트에 포함되지 [](/exchange/address-books/hierarchical-address-books/hierarchical-address-books) 않은 모든 사용자에게는 온라인 Exchange 표시됩니다.

- **PowerShell을** 사용하여 관리: 현재 정보 장벽 정책은 보안 및 준수 센터 PowerShell에서 정의되고 & 관리됩니다. 이 문서에서는 몇 가지 예제를 제공하겠지만 PowerShell cmdlet 및 매개 변수에 익숙해야 합니다. PowerShell 모듈에 Azure Active Directory 필요합니다.
  - [보안 및 준수 센터 PowerShell에 연결](/powershell/exchange/connect-to-scc-powershell)
  - [설치 Azure Active Directory PowerShell을 Graph](/powershell/azure/active-directory/install-adv2)

- Microsoft Teams 정보 장벽에 대한 관리자 **동의:** IB 정책이 설정되어 있는 경우 그룹(즉, 그룹을 기반으로 하는 Teams 채널)에서 IB가 아닌 사용자를 제거할 수 있습니다. 이 구성은 조직이 정책 및 규정을 준수하는지 보장하는 데 도움이 됩니다. 다음 절차에 따라 정보 장벽 정책이 해당 정책에서 예상대로 작동하도록 Microsoft Teams.

   1. Prerequisite: [Azure Active Directory PowerShell for Graph.](/powershell/azure/active-directory/install-adv2)

   1. 다음 PowerShell cmdlet을 실행합니다.

      ```powershell
      Connect-AzureAD -Tenant "<yourtenantdomain.com>"  //for example: Connect-AzureAD -Tenant "Contoso.onmicrosoft.com"
      $appId="bcf62038-e005-436d-b970-2a472f8c1982" 
      $sp=Get-AzureADServicePrincipal -Filter "appid eq '$($appid)'"
      if ($sp -eq $null) { New-AzureADServicePrincipal -AppId $appId }
      Start-Process  "https://login.microsoftonline.com/common/adminconsent?client_id=$appId"
      ```

   1. 메시지가 표시될 때 사용자 계정으로 직장 또는 학교 계정을 사용하여 Office 365.

   1. 요청한 **사용** 권한 대화 상자에서 정보를 검토한 다음 수락을 **선택합니다.** 앱에서 요청한 사용 권한은 아래에 제공됩니다.

      > [!div class="mx-imgBorder"]
      > ![이미지.](https://user-images.githubusercontent.com/8932063/107690955-b1772300-6c5f-11eb-9527-4235de860b27.png)

모든 선행 단계를 충족하면 다음 단계로 진행합니다.

> [!TIP]
> 이 문서에는 계획을 준비하는 데 도움이 되는 예제 시나리오가 포함되어 있습니다. [Contoso의 부서, 세그먼트](#example-scenario-contosos-departments-segments-and-policies)및 정책을 참조합니다.

## <a name="step-2-segment-users-in-your-organization"></a>2단계: 조직에서 사용자 구분

이 단계에서는 필요한 정보 장벽 정책을 결정하고 정의할 세그먼트 목록을 만들어 세그먼트를 정의합니다.

### <a name="determine-what-policies-are-needed"></a>필요한 정책 결정

법률 및 산업 규정을 고려할 때 정보 장벽 정책이 필요한 조직 내의 그룹은 누구인가요? 목록을 만들 수 있습니다. 다른 그룹과의 통신을 차단해야 하는 그룹이 있나요? 하나 또는 두 개의 다른 그룹과만 통신할 수 있도록 허용해야 하는 그룹이 있나요? 다음 두 그룹 중 하나에 속하는 정책에 대해 생각해 보아야 합니다.

- "차단" 정책은 한 그룹이 다른 그룹과 통신하지 못하게 합니다.
- "허용" 정책을 사용하면 그룹이 다른 특정 그룹과만 통신할 수 있습니다.

초기 그룹 및 정책 목록이 있는 경우 필요한 세그먼트를 식별합니다.

### <a name="identify-segments"></a>세그먼트 식별

초기 정책 목록 외에 조직의 세그먼트 목록을 만들어야 합니다. 정보 장벽 정책에 포함될 사용자는 세그먼트에 속해야 합니다. 사용자가 하나의 세그먼트에만 있을 수 있도록 세그먼트를 신중하게 계획합니다. 각 세그먼트에는 하나의 정보 장벽 정책만 적용할 수 있습니다.

> [!IMPORTANT]
> 사용자는 하나의 세그먼트에만 있을 수 있습니다.

세그먼트를 정의하는 데 사용할 조직의 디렉터리 데이터의 특성을 확인합니다. *Department,* *MemberOf* 또는 지원되는 특성을 사용할 수 있습니다. 사용자에 대해 선택한 특성에 값이 있는지 확인 [정보 장벽에 대해 지원되는 특성 목록을 참조하세요.](information-barriers-attributes.md)

> [!IMPORTANT]
> **다음 섹션을 진행하기 전에** 디렉터리 데이터에 세그먼트를 정의하는 데 사용할 수 있는 특성 값이 있는지 확인합니다. 디렉터리 데이터에 사용하려는 특성 값이 없는 경우 정보 장벽을 계속하기 전에 해당 정보를 포함하도록 사용자 계정을 업데이트해야 합니다. 이에 대한 도움이 필요한 경우 다음 리소스를 참조합니다.<br/>- [PowerShell을 사용하여 사용자 계정 Office 365 구성](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md)<br/>- [사용자 프로필 정보를 사용하여 사용자 프로필 정보 추가 또는 Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

### <a name="define-segments-using-powershell"></a>PowerShell을 사용하여 세그먼트 정의

세그먼트 정의는 사용자에게 영향을 주지 않습니다. 정보 장벽 정책을 정의한 다음 적용할 단계만 설정하면 됩니다.

1. 사용할 특성에 해당하는 **UserGroupFilter** 매개 변수와 함께 **New-OrganizationSegment** cmdlet을 사용합니다. [](information-barriers-attributes.md)

    | 구문 | 예제 |
    |:---------|:----------|
    | `New-OrganizationSegment -Name "segmentname" -UserGroupFilter "attribute -eq 'attributevalue'"` |`New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` <p>이 예에서 *HR이라는* 세그먼트는 Department 특성의 *값인 HR을* *사용하여 정의됩니다.* cmdlet의 **-eq** 부분은 "같음"을 참조합니다. 또는 **-ne를 사용하여 "not** equals"를 의미할 수 있습니다. 세그먼트 [정의에서 "같음" 및 "같지 않은" 사용을 참조합니다.](#using-equals-and-not-equals-in-segment-definitions) |

    각 cmdlet을 실행하면 새 세그먼트에 대한 세부 정보 목록이 표시됩니다. 세부 정보에는 세그먼트 유형, 세그먼트를 만들거나 마지막으로 수정한 사람 등이 포함됩니다. 

2. 정의할 각 세그먼트에 대해 이 프로세스를 반복합니다.

    > [!IMPORTANT]
    > **세그먼트가 겹치지 않는지 확인** 정보 장벽의 영향을 받는 각 사용자는 하나의 세그먼트에 속해야 합니다. 사용자가 둘 이상의 세그먼트에 속하지 않습니다. (이 [문서의 예제: Contoso의 정의된](#contosos-defined-segments) 세그먼트를 참조하세요.)

세그먼트를 정의한 후 정보 장벽 [정책 정의로 진행합니다.](#step-3-define-information-barrier-policies)

### <a name="using-equals-and-not-equals-in-segment-definitions"></a>세그먼트 정의에 "같음" 및 "같지 않은" 사용

다음 예제에서는 "Department가 HR과 같음"을 정의합니다. 

| 예제 | 참고 |
|:----------|:-------|
|`New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` | 이 예제에서 세그먼트 정의에는 **-eq로** 지칭된 "equals" 매개 변수가 포함되어 있습니다. |

다음 표와 같이 **-ne로** 표시된 "같지 않은" 매개 변수를 사용하여 세그먼트를 정의할 수도 있습니다.

| 구문 | 예제 |
|:---------|:----------|
| `New-OrganizationSegment -Name "NotSales" -UserGroupFilter "Department -ne 'Sales'"` | 이 예제에서는 Sales에 없는 모든 사람을 포함하는 *NotSales라는* 세그먼트를 *정의했습니다.* cmdlet의 **-ne** 부분은 "같지 않습니다."를 참조합니다. |

"같음" 또는 "같지 않은" 매개 변수를 사용하여 세그먼트를 정의하는 것 외에도 "같음" 및 "같지 않은" 매개 변수를 모두 사용하여 세그먼트를 정의할 수 있습니다. 논리 AND 및 OR 연산자를 사용하여 복잡한 *그룹* *필터를 정의할 수도* 있습니다.

| 구문 | 예제 |
|:---------|:----------|
| `New-OrganizationSegment -Name "LocalFTE" -UserGroupFilter "Location -eq 'Local'" -and "Position -ne 'Temporary'"` | 이 예제에서는 로컬에 있으며 해당 위치가 임시로 나열되지 않는 사람이 포함된 *LocalFTE라는* 세그먼트를 *정의했습니다.* |
| `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "MemberOf -eq 'group1@contoso.com'' -and MemberOf -ne 'group3@contoso.com'"`| 이 예제에서는 *Segment1이라는* 세그먼트를 정의하여 이 세그먼트의 구성원이 아닌 group1@contoso.com 구성원인 group3@contoso.com. |
| `New-OrganizationSegment -Name "Segment2" -UserGroupFilter "MemberOf -eq 'group2@contoso.com' -or MemberOf -ne 'group3@contoso.com'"` | 이 예제에서는 *Segment2라는* 세그먼트를 정의하여 이 세그먼트의 구성원이 아닌 group2@contoso.com 구성원인 group3@contoso.com. |
| `New-OrganizationSegment -Name "Segment1and2" -UserGroupFilter "(MemberOf -eq 'group1@contoso.com' -or MemberOf -eq 'group2@contoso.com') -and MemberOf -ne 'group3@contoso.com'"`| 이 예제에서는 Group1@contoso.com 및 group2@contoso.com 구성원이 아닌 사용자 구성원을 포함하는 *Segment1and2라는* 세그먼트를 group3@contoso.com. |

> [!TIP]
> 가능한 경우 "-eq" 또는 "-ne"가 포함된 세그먼트 정의를 사용합니다. 복잡한 세그먼트 정의를 정의하지 않습니다.

## <a name="step-3-define-information-barrier-policies"></a>3단계: 정보 장벽 정책 정의

특정 세그먼트 간의 통신을 방지할지 또는 특정 세그먼트로 통신을 제한해야 하는지 여부를 결정해야 합니다. 조직이 법률 및 산업 요구 사항을 준수하는지 보장하기 위해 최소 수의 정책을 사용하는 것이 가장 이상적입니다.

정의할 사용자 세그먼트 및 정보 장벽 정책 목록을 사용하여 시나리오를 선택한 다음 단계를 수행합니다.

- [시나리오 1: 세그먼트 간의 통신 차단](#scenario-1-block-communications-between-segments)
- [시나리오 2: 세그먼트가 다른 세그먼트와만 통신하도록 허용](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment)

> [!IMPORTANT]
> 정책을 정의할 때 세그먼트에 정책을 두 개 이상 **할당하지 않는지 확인** 예를 들어 Sales라는 세그먼트에 대해 하나의 정책을 정의하는 경우 *Sales에* 대한 추가 정책을 정의하지 *않습니다.*<p> 또한 정보 장벽 정책을 정의할 때 정책을 적용할 준비가 될 때까지 해당 정책을 비활성 상태로 설정해야 합니다. 정책을 정의(또는 편집) 정책은 해당 정책을 활성 상태로 설정한 다음 적용해야 사용자에게 영향을 주지 않습니다.

(이 문서의 [예: Contoso의 정보](#contosos-information-barrier-policies) 장벽 정책 참조)

### <a name="scenario-1-block-communications-between-segments"></a>시나리오 1: 세그먼트 간의 통신 차단

세그먼트가 서로 통신하는 것을 차단하려는 경우 각 방향에 대해 하나씩 두 정책을 정의합니다. 각 정책은 한 방향으로만 통신을 차단합니다.

예를 들어 세그먼트 A와 세그먼트 B 간의 통신을 차단하려는 경우를 가정해 보겠습니다. 이 경우 세그먼트 A가 세그먼트 B와 통신하지 못하게 하는 하나의 정책을 정의한 다음 세그먼트 B가 세그먼트 A와 통신하지 못하게 하는 두 번째 정책을 정의합니다.

1. 첫 번째 차단 정책을 정의하기 위해 **SegmentsBlocked** 매개 변수와 함께 **New-InformationBarrierPolicy** cmdlet을 사용합니다.

    | 구문 | 예제 |
    |:--------|:----------|
    | `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsBlocked "segment2name"` | `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p> 이 예제에서는 Sales라는 세그먼트에 대해 *Sales-Research라는* 정책을 *정의했습니다.* 이 정책을 활성화하고 적용하면 Sales의 사용자가 *Research라는* 세그먼트의 사용자와 통신할 수 *없습니다.* |

2. 두 번째 차단 세그먼트를 정의하기 위해 세그먼트가 반대인 **SegmentsBlocked** 매개 변수와 함께 **New-InformationBarrierPolicy** cmdlet을 다시 사용합니다.

    | 예제 | 참고 |
    |:----------|:-------|
    |`New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` | 이 예에서는 *Research-Sales라는* 정책을 정의하여 *Research가 Sales와* 통신하지 못하게 *합니다.* |

3. 다음 작업 중 하나를 진행합니다.

   - (필요한 경우) [세그먼트가 다른 세그먼트와만](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment) 통신할 수 있도록 하는 정책 정의 
   - (모든 정책을 정의한 후) [정보 장벽 정책 적용](#step-4-apply-information-barrier-policies)

### <a name="scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment"></a>시나리오 2: 세그먼트가 다른 세그먼트와만 통신하도록 허용

1. 한 세그먼트가 다른 세그먼트와만 통신할 수 있도록 허용하기 위해 **SegmentsAllowed** 매개 변수와 함께 **New-InformationBarrierPolicy** cmdlet을 사용합니다.

    | 구문 | 예제 |
    |:----------|:----------|
    | `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name","segment1name"` | `New-InformationBarrierPolicy -Name "Manufacturing-HR" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR","Manufacturing" -State Inactive` <p> 이 예에서는 Manufacturing이라는 세그먼트에 대해 *Manufacturing-HR이라는* 정책을 *정의했습니다.* 이 정책을 활성화하고 적용하면 *제조업* 사용자가 *HR이라는* 세그먼트의 사용자와만 통신할 수 있습니다. (이 경우 *제조는* HR에 참여하지 않는 사용자와 *통신할 수 없습니다.)* |

    **필요한 경우 다음 예제와 같이 이 cmdlet을 사용하여 여러 세그먼트를 지정할 수 있습니다.**

    | 구문 | 예제 |
    |:---------|:----------|
    | `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name", "segment3name","segment1name"` | `New-InformationBarrierPolicy -Name "Research-HRManufacturing" -AssignedSegment "Research" -SegmentsAllowed "HR","Manufacturing","Research" -State Inactive` <p> 이 예제에서는 리서치 세그먼트가  *HR* 및 제조와만 통신할 수 있도록 하는 정책을 *정의했습니다.* |

    특정 세그먼트가 다른 특정 세그먼트와만 통신할 수 있도록 정의하려는 각 정책에 대해 이 단계를 반복합니다.

2. 다음 작업 중 하나를 진행합니다.

   - (필요한 경우) [세그먼트 간 통신을 차단하는 정책 정의](#scenario-1-block-communications-between-segments) 
   - (모든 정책을 정의한 후) [정보 장벽 정책 적용](#step-4-apply-information-barrier-policies)

## <a name="step-4-apply-information-barrier-policies"></a>4단계: 정보 장벽 정책 적용

정보 장벽 정책은 활성 상태로 설정한 다음 정책을 적용하기 전까지는 적용되지 않습니다.

1. **Get-InformationBarrierPolicy** cmdlet을 사용하여 정의된 정책 목록을 볼 수 있습니다. 각 정책의 상태 및 ID(GUID)를 메모합니다.

    구문: `Get-InformationBarrierPolicy`

2. 정책을 활성 상태로 설정하기 위해 **Identity** 매개 변수와 **함께 Set-InformationBarrierPolicy** cmdlet을 사용하고 State 매개 변수를 **Active로** **설정하십시오.** 

    | 구문 | 예제 |
    |:---------|:----------|
    | `Set-InformationBarrierPolicy -Identity GUID -State Active` | `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -State Active` <p> 이 예에서는 *GUID가 43c37853-ea10-4b90-a23d-ab8c93772471인* 정보 장벽 정책을 활성 상태로 설정했습니다. |

    각 정책에 따라 이 단계를 반복합니다.

3. 정보 장벽 정책을 활성 상태로 설정한 후 보안 및 준수 센터에서 **Start-InformationBarrierPoliciesApplication** cmdlet을 & 합니다.

    구문: `Start-InformationBarrierPoliciesApplication`

    를 실행한 후 시스템이 정책 적용을 시작할 수 있도록 `Start-InformationBarrierPoliciesApplication` 30분을 허용합니다. 시스템은 사용자에 따라 정책 사용자를 적용합니다. 시스템은 시간당 약 5,000개 사용자 계정을 처리합니다.

### <a name="view-status-of-user-accounts-segments-policies-or-policy-application"></a>사용자 계정, 세그먼트, 정책 또는 정책 응용 프로그램의 상태 보기

PowerShell을 사용하면 다음 표에 나와 있는 사용자 계정, 세그먼트, 정책 및 정책 응용 프로그램의 상태를 볼 수 있습니다.

| 이 정보를 보기 위해 | 이 작업 수행 |
|:---------------|:----------|
| 사용자 계정 | Identity 매개 변수와 함께 **Get-InformationBarrierRecipientStatus** cmdlet을 사용합니다. <p> 구문: `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> 이름, 별칭, 고유 이름, 정식 도메인 이름, 전자 메일 주소 또는 GUID와 같이 각 사용자를 고유하게 식별하는 모든 값을 사용할 수 있습니다. <p> 예: `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> 이 예제에서는 2개의 사용자 계정인 Office 365 *meganb* 및 *Alex의 alexw를* *참조합니다.* <p> (단일 사용자에 대해 이 cmdlet을 사용할 수도 있습니다. `Get-InformationBarrierRecipientStatus -Identity <value>` ) <p> 이 cmdlet은 특성 값 및 적용되는 모든 정보 장벽 정책과 같은 사용자에 대한 정보를 반환합니다.|
| 세그먼트 | **Get-OrganizationSegment** cmdlet을 사용 합니다.<p> 구문: `Get-OrganizationSegment` <p> 이 cmdlet은 조직에 대해 정의된 모든 세그먼트의 목록을 표시합니다. |
| 정보 장벽 정책 | **Get-InformationBarrierPolicy** cmdlet을 사용하세요. <p> 구문: `Get-InformationBarrierPolicy` <p> 이 cmdlet은 정의된 정보 장벽 정책 목록과 해당 상태를 표시합니다. |
| 최신 정보 장벽 정책 응용 프로그램 | **Get-InformationBarrierPoliciesApplicationStatus** cmdlet을 사용하세요. <p> 구문: `Get-InformationBarrierPoliciesApplicationStatus`<p> 이 cmdlet은 정책 응용 프로그램이 완료, 실패 또는 진행 중인지 여부에 대한 정보를 표시합니다. |
| 모든 정보 장벽 정책 응용 프로그램|`Get-InformationBarrierPoliciesApplicationStatus -All`을(를) 사용하세요.<p> 이 cmdlet은 정책 응용 프로그램이 완료, 실패 또는 진행 중인지 여부에 대한 정보를 표시합니다.|

<!-- IN the " The most recent information barrier policy application, add link to troubleshooting topic -->

### <a name="what-if-i-need-to-remove-or-change-policies"></a>정책을 제거하거나 변경해야 하는 경우 어떻게 하나요?

리소스는 정보 장벽 정책을 관리하는 데 도움이 됩니다.

- 정보 장벽에 문제가 있는 경우 정보 장벽 [문제 해결을 참조하세요.](/office365/troubleshoot/information-barriers/information-barriers-troubleshooting)
- 정책이 적용되지 못하게 중지하는 경우 정책 응용 프로그램 [중지를 참조합니다.](information-barriers-edit-segments-policies.md#stop-a-policy-application)
- 정보 장벽 정책을 제거하려면 [정책 제거를 참조하세요.](information-barriers-edit-segments-policies.md#remove-a-policy)
- 세그먼트 또는 정책을 변경하려면 정보 장벽 정책 [편집(또는 제거)을 참조하세요.](information-barriers-edit-segments-policies.md)

## <a name="step-5-configuration-for-information-barriers-on-sharepoint-and-onedrive"></a>5단계: 사용자 및 사용자에 대한 정보 장벽 SharePoint OneDrive

사용자 및 사용자에 대한 정보 장벽을 SharePoint OneDrive 이러한 서비스에서 정보 장벽을 사용하도록 설정해야 합니다. 또한 사용자에 대한 정보 장벽을 구성하는 경우 이러한 서비스에 대한 정보 장벽을 설정해야 Microsoft Teams. Microsoft Teams 팀을 만들면 SharePoint 사이트가 자동으로 만들어지며 파일 환경을 Microsoft Teams 사이트와 연결됩니다. 이 사이트 및 파일에는 기본적으로 정보 장벽 정책이 SharePoint 않습니다.

사용자 및 사용자 SharePoint OneDrive 장벽을 사용하도록 설정하려면 다음 문서와 함께 정보 장벽 사용 [문서의](/sharepoint/information-barriers) 지침 및 SharePoint 따릅니다.

## <a name="step-6-information-barriers-modes-preview"></a>6단계: 정보 장벽 모드(미리 보기)

모드를 사용하면 리소스의 IB 모드를 기반으로 Microsoft 365 리소스에 대한 액세스, 공유 및 구성원 자격을 강화할 수 있습니다. 모드는 Microsoft 365, Microsoft Teams, OneDrive 및 SharePoint 사이트에서 지원되며 새 IB 구성 또는 기존 IB 구성에서 자동으로 사용하도록 설정됩니다.

다음 IB 모드는 모든 리소스에서 Microsoft 365 있습니다.

| **Mode** | **설명** | **예** |
|:-----|:------------|:--------|
| **열기** | IB 정책 또는 세그먼트가 Microsoft 365 없습니다. 모든 사람을 리소스의 구성원으로 초대할 수 있습니다. | 조직에서 소나기 이벤트를 위해 만든 팀 사이트입니다. |
| **소유자 중재** | IB 정책은 Microsoft 365 소유자의 IB 정책에 따라 결정됩니다. 자원 소유자는 IB 정책에 따라 자원에 사용자를 초대할 수 있습니다. 이 모드는 회사에서 소유자가 중재하는 비호화 세그먼트 사용자 간 공동 작업을 허용하려는 경우 유용합니다. 자원 소유자만 IB 정책에 따라 새 구성원을 추가할 수 있습니다. | HR의 VP는 영업 및 리서치 VP와 공동 작업을 하고자 합니다. IB SharePoint 소유자 중재로 설정되어 판매  및 리서치 세그먼트 사용자를 동일한 사이트에 추가하는 새 사이트입니다. 적절한 구성원이 리소스에 추가되도록 하는 것은 소유자의 책임입니다. |
| **암시적** | IB 정책 또는 Microsoft 365 리소스 구성원 IB 정책에서 상속됩니다. 소유자는 리소스의 기존 구성원과 호환되는 한 구성원을 추가할 수 있습니다. 이 모드는 사용자 지정에 대한 기본 IB Microsoft Teams. | 영업 부문 사용자는 조직에서 Microsoft Teams 다른 세그먼트와 공동 작업을 할 수 있는 팀을 만듭니다. |
| **Explicit** | Microsoft 365 리소스의 IB 정책은 리소스와 연결된 세그먼트에 따라 다를 수 있습니다. 자원 소유자 또는 SharePoint 관리자가 자원의 세그먼트를 관리할 수 있습니다.  | 판매 세그먼트 구성원만 만든 사이트는 판매 세그먼트를 사이트에 연결하여 공동 작업할 수 있습니다.   |

정보 장벽 모드 및 서비스 전체에서 구성하는 방법에 대한 자세한 내용은 다음 문서를 참조하세요.

- [정보 장벽 모드 및 Microsoft Teams](/microsoftteams/information-barriers-in-teams)
- [정보 장벽 모드 및 OneDrive](/onedrive/information-barriers)
- [정보 장벽 모드 및 SharePoint](/sharepoint/information-barriers)

## <a name="example-scenario-contosos-departments-segments-and-policies"></a>시나리오 예: Contoso의 부서, 세그먼트 및 정책

조직에서 세그먼트 및 정책 정의에 어떻게 접근할 수 있을지 결정하기 위해 다음 예제 시나리오를 고려합니다.

### <a name="contosos-departments-and-plan"></a>Contoso 부서 및 계획

Contoso에는 HR, 영업, 마케팅, 리서치 및 제조 부서의 5개 부서가 있습니다. 산업 규정을 준수하기 위해 다음 표에 나와 있는 일부 부서의 사용자가 다른 부서와 의사소통하지 않는 경우도 있습니다.

| 세그먼트 | 대화할 수 있는 경우 | 대화할 수 없는 경우 |
|:----------|:--------------|:-----------------|
| HR | 모든 사용자 | (제한 사항 없음) |
| 영업 | HR, 마케팅, 제조 | 리서치 |
| 마케팅 | 모든 사용자 | (제한 사항 없음) |
| 리서치 | HR, 마케팅, 제조 | 영업 |
| 제조 | HR, 마케팅 | HR 또는 마케팅 외의 모든 사람 |

이 구조의 경우 Contoso의 계획에는 다음과 같은 세 가지 정보 장벽 정책이 포함되어 있습니다.

1. 판매가 리서치와 통신하지 못하도록 설계된 정책(연구가 판매와 통신하지 못하도록 하는 다른 정책)

2. 제조가 HR 및 마케팅과만 통신할 수 있도록 설계된 정책입니다.

이 시나리오에서는 HR 또는 마케팅에 대한 정책을 정의할 필요가 없습니다.

### <a name="contosos-defined-segments"></a>Contoso의 정의된 세그먼트

Contoso는 다음과 같이 Azure Active Directory 부서의 Department 특성을 사용하여 세그먼트를 정의합니다.

| 부서 | 세그먼트 정의 |
|:-------------|:---------------------|
| HR | `New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` |
| 영업 | `New-OrganizationSegment -Name "Sales" -UserGroupFilter "Department -eq 'Sales'"` |
| 마케팅 | `New-OrganizationSegment -Name "Marketing" -UserGroupFilter "Department -eq 'Marketing'"` |
| 리서치 | `New-OrganizationSegment -Name "Research" -UserGroupFilter "Department -eq 'Research'"` |
| 제조 | `New-OrganizationSegment -Name "Manufacturing" -UserGroupFilter "Department -eq 'Manufacturing'"` |

Contoso는 정의된 세그먼트를 사용하여 정책을 정의합니다.

### <a name="contosos-information-barrier-policies"></a>Contoso의 정보 장벽 정책

Contoso는 다음 표에 설명된 3개의 정책을 정의합니다.

| 정책 | 정책 정의 |
|:---------|:--------------------|
| **정책 1: 판매가 리서치와 통신하지 못하게 방지** | `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p> 이 예제에서는 정보 장벽 정책을 *영업-리서치* 라고 합니다. 이 정책이 활성화되고 적용되면 판매 세그먼트에 있는 사용자가 리서치 세그먼트에 있는 사용자와 통신하지 못하게 하는 데 도움이 됩니다. 이 정책은 단방형 정책입니다. 리서치가 Sales와 통신하는 것을 방지하지는 않습니다. 따라서 정책 2가 필요합니다. |
| **정책 2: 리서치가 영업과 통신하지 못하게 방지** | `New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` <p> 이 예제에서는 정보 장벽 정책을 *리서치-영업* 이라고 합니다. 이 정책이 활성화되고 적용되면 리서치 세그먼트에 있는 사용자가 영업 세그먼트에 있는 사용자와 통신하지 못하게 하는 데 도움이 됩니다. |
| **정책 3: 제조가 HR 및 마케팅과만 통신하도록 허용** | `New-InformationBarrierPolicy -Name "Manufacturing-HRMarketing" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR","Marketing","Manufacturing" -State Inactive` <p> 이 경우 정보 장벽 정책은 *제조-HR마케팅* 이라고 합니다. 이 정책이 활성화되고 적용된 경우 제조는 HR 및 마케팅과만 통신할 수 있습니다. HR 및 마케팅은 다른 세그먼트와의 통신이 제한되지 않습니다. |

세그먼트 및 정책을 정의하면 Contoso는 **Start-InformationBarrierPoliciesApplication** cmdlet을 실행하여 정책을 적용합니다.

이 cmdlet이 완료되면 Contoso는 법률 및 산업 요구 사항을 준수합니다.

## <a name="resources"></a>리소스

- [정보 장벽 개요 보기](information-barriers.md)
- [정보 장벽에 대해 자세히 Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams)
- [온라인에서 정보 장벽에 대해 SharePoint 정보](/sharepoint/information-barriers)
- [정보 장벽에 대해 자세히 OneDrive](/onedrive/information-barriers)
