---
title: 정보 장벽 정책 정의
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/08/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
localization_priority: None
description: Microsoft Teams에서 정보 장벽에 대한 정책을 정의하는 방법을 배워야 합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ed4c9caba59eee9f01bdb1db3bafba91bac78437
ms.sourcegitcommit: d859ea36152c227699c1786ef08cda5805ecf7db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49604228"
---
# <a name="define-information-barrier-policies"></a>정보 장벽 정책 정의

정보 장벽을 사용하여 특정 사용자 세그먼트가 서로 통신하지 못하도록 설계된 정책을 정의하거나 특정 세그먼트가 특정 세그먼트와만 통신할 수 있도록 허용할 수 있습니다. 정보 장벽 정책은 조직이 관련 산업 표준 및 규정을 준수하고 잠재적인 이해 상충을 방지하는 데 도움이 될 수 있습니다. 자세한 내용은 정보 [장벽을 참조하세요.](information-barriers.md) 

이 문서에서는 정보 장벽 정책을 계획, 정의, 구현 및 관리하는 방법을 설명합니다. 여러 단계가 관련이 있으며 작업 흐름은 여러 부분으로 나뉘어 있습니다. 정보 장벽 정책 [prerequisites](#prerequisites) 정의(또는 편집)를 시작하기 전에 선행 작업 및 전체 프로세스를 읽어야 합니다.

> [!TIP]
> 이 문서에는 정보 장벽 [정책을](#example-contosos-departments-segments-and-policies) 계획하고 정의하는 데 도움이 되는 예제 시나리오 및 다운로드 가능한 [Excel](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx) 통합 문서가 포함되어 있습니다.

## <a name="concepts-of-information-barrier-policies"></a>정보 장벽 정책의 개념

정보 장벽에 대한 정책을 정의하면 사용자 계정 특성, 세그먼트, "차단" 및/또는 "허용" 정책 및 정책 응용 프로그램을 사용할 수 있습니다.

- 사용자 계정 특성은 Azure Active Directory(또는 Exchange Online)에서 정의됩니다. 이러한 특성에는 부서, 직위, 위치, 팀 이름 및 기타 작업 프로필 세부 정보가 포함됩니다. 

- 세그먼트는 선택한 사용자 계정 특성을 사용하여 보안 & 준수 센터에 정의된 **사용자 집합입니다.** 지원되는 [특성 목록을 참조하세요.](information-barriers-attributes.md) 

- 정보 장벽 정책은 통신 제한 또는 제한을 결정합니다. 정보 장벽 정책을 정의할 때 다음 두 가지 유형의 정책 중 선택할 수 있습니다.
    - "차단" 정책은 한 세그먼트가 다른 세그먼트와 통신하지 못하게 합니다.
    - "허용" 정책을 사용하면 한 세그먼트가 다른 특정 세그먼트와만 통신할 수 있습니다.

- 정책 응용 프로그램은 모든 정보 장벽 정책이 정의되고 조직에 적용할 준비가 된 후에 수행됩니다.

## <a name="the-work-flow-at-a-glance"></a>워크플로 한 눈에 보기

|단계    |관련 항목  |
|---------|---------|
|[선행 준비를 충족하는지 확인](#prerequisites)     |- 필요한 라이선스 및 사용 권한이 있는지 [확인](information-barriers.md#required-licenses-and-permissions)<br/>- 디렉터리에 사용자 분할을 위한 데이터가 포함되어 있는지 확인<br/>- Microsoft Teams에 대해 범위가 지정한 디렉터리 검색 사용<br/>- 감사 로깅이 켜져 있는지 확인<br/>- Exchange 주소부 정책이 없는지 확인<br/>- PowerShell 사용(예제 제공)<br/>- Microsoft Teams에 대한 관리자 동의 제공(단계 포함)          |
|[1부: 조직에서 사용자 구분](#part-1-segment-users)     |- 필요한 정책 결정<br/>- 정의할 세그먼트 목록 만들기<br/>- 사용할 특성 식별<br/>- 정책 필터 측면에서 세그먼트 정의        |
|[2부: 정보 장벽 정책 정의](#part-2-define-information-barrier-policies)     |- 정책 정의(아직 적용되지 않습니다)<br/>- 두 가지 종류(차단 또는 허용) 중 선택 |
|[3부: 정보 장벽 정책 적용](#part-3-apply-information-barrier-policies)     |- 정책을 활성 상태로 설정<br/>- 정책 응용 프로그램 실행<br/>- 정책 상태 보기         |
|(필요한 경우) [세그먼트 또는 정책 편집](information-barriers-edit-segments-policies.md)    |- 세그먼트 편집<br/>- 정책 편집 또는 제거<br/>- 정책 응용 프로그램 다시 실행<br/>- 정책 상태 보기         |
|(필요한 경우) [문제 해결](information-barriers-troubleshooting.md)|- 작업이 예상대로 작동하지 않는 경우 작업 수행|

## <a name="prerequisites"></a>필수 구성 요소

필요한 라이선스 [및](information-barriers.md#required-licenses-and-permissions)사용 권한 외에 다음 요구 사항을 충족하는지 확인합니다. 
     
- 디렉터리 데이터 - 조직의 구조가 디렉터리 데이터에 반영해야 합니다. 이렇게하려면 그룹 구성원 자격, 부서 이름 등의 사용자 계정 특성이 Azure Active Directory(또는 Exchange Online)에 올바르게 채워야 합니다. 자세한 내용은 다음 리소스를 참조하세요.
  - [정보 장벽 정책의 속성](information-barriers-attributes.md)
  - [Azure Active Directory를 사용하여 사용자의 프로필 정보 추가 또는 업데이트](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)
  - [Office 365 PowerShell를 사용 하 여 사용자 계정 속성 구성](https://docs.microsoft.com/microsoft-365/enterprise/configure-user-account-properties-with-microsoft-365-powershell)

- 범위 디렉터리 검색 - 조직의 첫 번째 정보 장벽 정책을 정의하기 전에 [Microsoft Teams에서 범위가 지정한 디렉터리](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)검색을 사용하도록 설정해야 합니다. 정보 장벽 정책을 설정하거나 정의하기 전에 범위가 지정한 디렉터리 검색을 사용하도록 설정한 후 24시간 이상 기다릴 수 있습니다.

- EXO 라이선스 - 대상 사용자에게 EXO 라이선스가 할당된 경우 IB 정책이 적용됩니다.

- 감사 로깅 - 정책 응용 프로그램의 상태를 확인하려면 감사 로깅을 설정해야 합니다. 세그먼트 또는 정책을 정의하기 전에 이 작업을 수행 하는 것이 좋습니다. 자세한 내용은 감사 로그 검색 설정 [또는 해제를 참조합니다.](turn-audit-log-search-on-or-off.md)

- 주소부 정책 없음 - 정보 장벽 정책을 정의하고 적용하기 전에 Exchange 주소부 정책이 없는지 확인하십시오. 정보 장벽은 주소부 정책을 기반으로 하지만 두 가지 유형의 정책은 호환되지 않습니다. 이러한 정책이 있는 경우 먼저 주소부 정책을 [제거해야](https://docs.microsoft.com/exchange/address-books/address-book-policies/remove-an-address-book-policy) 합니다. 정보 장벽 정책을 사용하도록 설정하고 계층적 주소 예약을 사용하도록 설정하면 *_정보_* 장벽 세그먼트에 포함되지 않은 [hierarchical address book](https://docs.microsoft.com/exchange/address-books/hierarchical-address-books/hierarchical-address-books) 모든 사용자 *는 Exchange Online의 계층적 주소 책을 볼 수 있습니다.

- PowerShell - 현재 정보 장벽 정책은 PowerShell cmdlet을 사용하여 Office 365 보안 & 준수 센터에서 정의되고 관리됩니다. 이 문서에는 몇 가지 예제가 제공된 것이지만 PowerShell cmdlet 및 매개 변수에 익숙해야 합니다. Azure PowerShell 모듈도 필요합니다.
    - [보안 및 준수 센터 PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)
    - [Azure PowerShell 모듈 설치](https://docs.microsoft.com/powershell/azure/install-az-ps?view=azps-2.3.2)

- Microsoft Teams의 정보 장벽에 대한 관리자 동의 - 정책이 적용될 때 정보 장벽은 사용자가 아니어도 채팅 세션에서 제거될 수 있습니다. 이렇게 하면 조직이 정책 및 규정을 준수하도록 할 수 있습니다. 다음 절차에 따라 Microsoft Teams에서 정보 장벽 정책이 예상대로 작동하도록 합니다. 

   1. 다음 PowerShell cmdlet을 실행합니다.

      ```powershell
      Connect-AzureAD 
      $appId="bcf62038-e005-436d-b970-2a472f8c1982" 
      $sp=Get-AzADServicePrincipal -ServicePrincipalName $appId
      if ($sp -eq $null) { New-AzADServicePrincipal -ApplicationId $appId }
      Start-Process  "https://login.microsoftonline.com/common/adminconsent?client_id=$appId"
      ```

   2. 메시지가 표시될 때 Office 365에 대한 직장 또는 학교 계정을 사용하여 로그인합니다.

   3. _ *Permissions requested** 대화 상자에서 정보를 검토한 다음 수락을 **선택합니다.**

모든 선행 구성이 충족될 경우 다음 섹션으로 진행합니다.

> [!TIP]
> 이 문서에는 계획을 준비하는 데 도움이 되는 예제 시나리오가 포함되어 있습니다. [Contoso의 부서,](#example-contosos-departments-segments-and-policies)세그먼트 및 정책을 참조합니다.<p>또한 다운로드 가능한 Excel 통합 문서는 세그먼트 및 정책을 계획 및 정의하고 PowerShell cmdlet을 만드는 데 도움이 됩니다. [통합 문서 다운로드](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx) 

## <a name="part-1-segment-users"></a>1부: 사용자 구분

이 단계에서는 필요한 정보 장벽 정책을 결정하고 정의할 세그먼트 목록을 만들어 세그먼트를 정의합니다.

### <a name="determine-what-policies-are-needed"></a>필요한 정책 결정

법률 및 산업 규정을 고려할 때 정보 장벽 정책이 필요한 조직 내의 그룹은 누구인가요? 목록을 만들어야 합니다. 다른 그룹과 통신하지 못하게 해야 하는 그룹이 있나요? 하나 또는 두 개의 다른 그룹과만 통신할 수 있는 그룹이 있나요? 다음 두 그룹 중 하나에 속하는 정책에 대해 생각해 보아야 합니다.
- "차단" 정책은 한 그룹이 다른 그룹과 통신하지 못하게 합니다.
- "허용" 정책을 사용하면 그룹이 다른 특정 그룹과만 통신할 수 있습니다.

초기 그룹 및 정책 목록이 있는 경우 필요한 세그먼트를 식별합니다. 

### <a name="identify-segments"></a>세그먼트 식별

초기 정책 목록 외에 조직의 세그먼트 목록을 만들어야 합니다. 정보 장벽 정책에 포함될 사용자는 세그먼트에 속해야 합니다. 사용자가 하나의 세그먼트에만 있을 수 있는 경우 세그먼트를 신중하게 계획합니다. 각 세그먼트에는 하나의 정보 장벽 정책만 적용할 수 있습니다.

> [!IMPORTANT]
> 사용자는 하나의 세그먼트에만 있을 수 있습니다.

세그먼트를 정의하는 데 사용할 조직의 디렉터리 데이터의 특성을 확인합니다. Department, *Department* *MemberOf* 또는 지원되는 특성을 사용할 수 있습니다. 사용자에 대해 선택한 특성의 값이 있는지 확인 [정보 장벽에 대해 지원되는 특성 목록을 참조하세요.](information-barriers-attributes.md)

> [!IMPORTANT]
> **다음 섹션을 진행하기** 전에 디렉터리 데이터에 세그먼트를 정의하는 데 사용할 수 있는 특성 값이 있는지 확인합니다. 디렉터리 데이터에 사용하려는 특성 값이 없는 경우 정보 장벽을 계속하기 전에 해당 정보를 포함하도록 사용자 계정을 업데이트해야 합니다. 이에 대한 도움이 필요한 경우 다음 리소스를 참조합니다.<br/>- [Office 365 PowerShell을 사용하여 사용자 계정 속성 구성](https://docs.microsoft.com/microsoft-365/enterprise/configure-user-account-properties-with-microsoft-365-powershell)<br/>- [Azure Active Directory를 사용하여 사용자의 프로필 정보 추가 또는 업데이트](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

### <a name="define-segments-using-powershell"></a>PowerShell을 사용하여 세그먼트 정의

세그먼트 정의는 사용자에게 영향을 주지 않습니다. 정보 장벽 정책을 정의한 다음 적용하기 위한 단계만 설정하면 됩니다.

1. 사용하려는 특성에 해당하는 **UserGroupFilter** 매개 변수와 함께 **New-OrganizationSegment** cmdlet을 사용합니다. [attribute](information-barriers-attributes.md)

    |구문   |예제  |
    |---------|---------|
    |`New-OrganizationSegment -Name "segmentname" -UserGroupFilter "attribute -eq 'attributevalue'"`     |`New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` <p>이 예에서 *HR이라는* 세그먼트는 Department 특성의 *값인 HR을* *사용하여 정의됩니다.* cmdlet의 **-eq** 부분은 "같음"을 참조합니다. 또는 **-ne를** 사용하여 "같지 않은"을 의미할 수 있습니다. 세그먼트 [정의에서 "같음" 및 "같지 않은" 사용](#using-equals-and-not-equals-in-segment-definitions)참조        |

    각 cmdlet을 실행하면 새 세그먼트에 대한 세부 정보 목록이 표시됩니다. 세부 정보에는 세그먼트 유형, 세그먼트를 만들거나 마지막으로 수정한 사람 등이 포함됩니다. 

2. 정의할 각 세그먼트에 대해 이 프로세스를 반복합니다.

    > [!IMPORTANT]
    > **세그먼트가 겹치지 않는지 확인** 정보 장벽의 영향을 받는 각 사용자는 하나의 세그먼트에 속해야 합니다. 사용자가 둘 이상의 세그먼트에 속하지 말아야 합니다. (이 [문서에서 Contoso의 정의된](#contosos-defined-segments) 세그먼트를 참조하세요.)


세그먼트를 정의한 후 정보 장벽 정책을 [정의합니다.](#part-2-define-information-barrier-policies)

### <a name="using-equals-and-not-equals-in-segment-definitions"></a>세그먼트 정의에서 "같음" 및 "같지 않은" 사용

다음 예제에서는 "Department equals HR"으로 세그먼트를 정의합니다. 

|예제  |
|---------|
|`New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` <p>이 예제에서 세그먼트 정의에는 **-eq로** 지칭된 "equals" 매개 변수가 포함되어 있습니다. 
  |

다음 표와 같이 **-ne로** 표시된 "같지 않은" 매개 변수를 사용하여 세그먼트를 정의할 수도 있습니다.

|구문  |예제  |
|---------|---------|
|`New-OrganizationSegment -Name "NotSales" -UserGroupFilter "Department -ne 'Sales'"`   | <p>이 예제에서는 Sales에 없는 모든 사람을 포함하는 *NotSales라는* 세그먼트를 *정의했습니다.* cmdlet의 **-ne** 부분은 "같지 않습니다."를 참조합니다.  |

"같음" 또는 "같지 않은" 매개 변수를 사용하여 세그먼트를 정의하는 것 외에도 "같음" 및 "같지 않은" 매개 변수를 모두 사용하여 세그먼트를 정의할 수 있습니다. 논리 AND 및 OR 연산자를 사용하여 복잡한 그룹 *AND* *필터를 정의할 수도* 있습니다.


|구문    |예제  |
|---------|---------|
|`New-OrganizationSegment -Name "LocalFTE" -UserGroupFilter "Location -eq 'Local'" -and "Position -ne 'Temporary'"` |<p>이 예제에서는 로컬에 있으며 해당 위치가 Temporary로 나열되지 않는 사람이 포함된 *LocalFTE라는* 세그먼트를 *정의했습니다.*    |
 |`New-OrganizationSegment -Name "Segment1" -UserGroupFilter "MemberOf -eq 'group1@contoso.com'' -and MemberOf -ne 'group3@contoso.com'"`|  <p>이 예제에서는 *Segment1이라는* 세그먼트를 정의하여 세그먼트의 구성원이 아닌 group1@contoso.com 구성원인 group3@contoso.com.
|`New-OrganizationSegment -Name "Segment2" -UserGroupFilter "MemberOf -eq 'group2@contoso.com' -or MemberOf -ne 'group3@contoso.com'"` | 이 예제에서는 *Segment2라는* 세그먼트를 정의하여 세그먼트의 구성원이 아닌 group2@contoso.com 구성원인 group3@contoso.com.
|`New-OrganizationSegment -Name "Segment1and2" -UserGroupFilter "(MemberOf -eq 'group1@contoso.com' -or MemberOf -eq 'group2@contoso.com') -and MemberOf -ne 'group3@contoso.com'"`|  이 예제에서는 *Segment1and2라는* 세그먼트를 정의하여 세그먼트의 구성원이 아닌 group1@contoso.com group2@contoso.com 구성원을 group3@contoso.com.


> [!TIP]
> 가능한 경우 "-eq" 또는 "-ne"가 포함된 세그먼트 정의를 사용합니다. 복잡한 세그먼트 정의를 정의하지 않습니다.

## <a name="part-2-define-information-barrier-policies"></a>2부: 정보 장벽 정책 정의

특정 세그먼트 간의 통신을 차단할지 또는 특정 세그먼트로 통신을 제한해야 하는지 여부를 결정합니다. 이상적으로는 최소 수의 정책을 사용하여 조직이 법률 및 산업 요구 사항을 준수하는지 확인합니다.

사용자 세그먼트 목록과 정의할 정보 장벽 정책을 사용하여 시나리오를 선택한 다음 단계를 수행합니다. 

- [시나리오 1: 세그먼트 간 통신 차단](#scenario-1-block-communications-between-segments)
- [시나리오 2: 세그먼트가 다른 세그먼트와만 통신하도록 허용](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment)

> [!IMPORTANT]
> 정책을 정의할 때 세그먼트에 정책을 두 개 이상 **할당하지 않습니다.** 예를 들어 Sales라는 세그먼트에 대해 하나의 정책을 정의하는 경우 *Sales에* 대한 추가 정책을 정의하지 *않습니다.*<p>또한 정보 장벽 정책을 정의할 때 정책을 적용할 준비가 될 때까지 해당 정책을 비활성 상태로 설정해야 합니다. 정책 정의(또는 편집)는 해당 정책을 활성 상태로 설정한 다음 적용할 때까지 사용자에게 영향을 주지 않습니다.

(이 [문서에서는 Contoso의](#contosos-information-barrier-policies) 정보 장벽 정책 예제를 참조하세요.)

### <a name="scenario-1-block-communications-between-segments"></a>시나리오 1: 세그먼트 간 통신 차단

세그먼트가 서로 통신하는 것을 차단하려는 경우 각 방향에 대해 하나씩 두 가지 정책을 정의합니다. 각 정책은 단방으로만 통신을 차단합니다.

예를 들어 세그먼트 A와 세그먼트 B 간의 통신을 차단하려는 경우를 가정해 보겠습니다. 이 경우 세그먼트 A가 세그먼트 B와 통신하지 못하게 하는 하나의 정책을 정의한 다음 세그먼트 B가 세그먼트 A와 통신하지 못하게 하는 두 번째 정책을 정의합니다.

1. 첫 번째 차단 정책을 정의하기 위해 **SegmentsBlocked** 매개 변수와 함께 **New-InformationBarrierPolicy** cmdlet을 사용합니다. 

    |구문  |예제  |
    |---------|---------|
    |`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsBlocked "segment2name"`     |`New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p>    이 예제에서는 Sales라는 세그먼트에 대해 *Sales-Research라는* 정책을 *정의했습니다.* 이 정책을 활성화하고 적용하면 Sales의 사용자가 *Research라는* 세그먼트의 사용자와 통신할 수 *없습니다.*         |

2. 두 번째 차단 세그먼트를 정의하기 위해 **SegmentsBlocked** 매개 변수와 함께 **New-InformationBarrierPolicy** cmdlet을 다시 사용합니다. 이번에는 세그먼트가 반대로 설정됩니다.

    |예제  |
    |---------|
    |`New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` <p>    이 예에서는 Research가 Sales와 통신하지 *Research* 못하게 하는 *Research-Sales라는* 정책을 *정의했습니다.*     |

2. 다음 중 하나를 진행합니다.

   - (필요한 경우) [세그먼트가 다른 세그먼트와만](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment) 통신할 수 있도록 하는 정책 정의 
   - (모든 정책을 정의한 후) [정보 장벽 정책 적용](#part-3-apply-information-barrier-policies)

### <a name="scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment"></a>시나리오 2: 세그먼트가 다른 세그먼트와만 통신하도록 허용

1. 한 세그먼트가 다른 세그먼트와만 통신하도록 허용하기 위해 **SegmentsAllowed** 매개 변수와 함께 **New-InformationBarrierPolicy** cmdlet을 사용합니다. 

    |구문  |예제  |
    |---------|---------|
    |`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name","segment1name"`     |`New-InformationBarrierPolicy -Name "Manufacturing-HR" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR","Manufacturing" -State Inactive` <p>    이 예제에서는 Manufacturing이라는 세그먼트에 *대해 Manufacturing-HR이라는* 정책을 *정의했습니다.* 이 정책을 활성화하고 적용하면 *Manufacturing* 제조업의 사용자가 *HR이라는* 세그먼트의 사용자와만 통신할 수 있습니다. 이 경우 *제조는* *HR에* 참여하지 않는 사용자와 통신할 수 없습니다.         |

    **필요한 경우 다음 예제와 같이 이 cmdlet을 사용하여 여러 세그먼트를 지정할 수 있습니다.**

    |구문  |예제  |
    |---------|---------|
    |`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name", "segment3name","segment1name"`     |`New-InformationBarrierPolicy -Name "Research-HRManufacturing" -AssignedSegment "Research" -SegmentsAllowed "HR","Manufacturing","Research" -State Inactive` <p>이 예제에서는 Research 세그먼트가 *HR* 및 제조와만 통신할 수 있도록 하는 정책을 *정의했습니다.* *Research*        |

    특정 세그먼트가 다른 특정 세그먼트와만 통신할 수 있도록 정의하려는 각 정책에 대해 이 단계를 반복합니다.

2. 다음 중 하나를 진행합니다.

   - (필요한 경우) [세그먼트 간 통신을](#scenario-1-block-communications-between-segments) 차단하는 정책 정의 
   - (모든 정책을 정의한 후) [정보 장벽 정책 적용](#part-3-apply-information-barrier-policies)

## <a name="part-3-apply-information-barrier-policies"></a>3부: 정보 장벽 정책 적용

정보 장벽 정책은 활성 상태로 설정한 다음 정책을 적용하기 전까지는 적용되지 않습니다.

1. **Get-InformationBarrierPolicy** cmdlet을 사용하여 정의된 정책 목록을 볼 수 있습니다. 각 정책의 상태 및 ID(GUID)를 메모합니다.

    구문: `Get-InformationBarrierPolicy`

2. 정책을 활성 상태로 설정하기 위해 **Identity** 매개 변수와 함께 **Set-InformationBarrierPolicy** cmdlet을 사용하며 State 매개 변수를 **Active로** **설정하십시오.** 

    |구문  |예제  |
    |---------|---------|
    |`Set-InformationBarrierPolicy -Identity GUID -State Active`     |`Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -State Active` <p>    이 예에서는 *GUID가 43c37853-ea10-4b90-a23d-ab8c93772471인* 정보 장벽 정책을 활성 상태로 설정했습니다.   |

    각 정책에 적절하게 이 단계를 반복합니다.

3. 정보 장벽 정책을 활성 상태로 설정한 후 보안 및 준수 센터에서 **Start-InformationBarrierPoliciesApplication** cmdlet을 & 합니다.

    구문: `Start-InformationBarrierPoliciesApplication`

    실행한 후 시스템에서 정책 적용을 시작하는 데 `Start-InformationBarrierPoliciesApplication` 30분을 허용합니다. 시스템은 사용자에 따라 정책 사용자를 적용합니다. 일반적으로 시스템은 시간당 약 5,000개 사용자 계정을 처리합니다.

## <a name="view-status-of-user-accounts-segments-policies-or-policy-application"></a>사용자 계정, 세그먼트, 정책 또는 정책 응용 프로그램의 상태 보기

PowerShell을 사용하면 다음 표에 나열된 사용자 계정, 세그먼트, 정책 및 정책 응용 프로그램의 상태를 볼 수 있습니다.

|이 보기  |실행할 작업  |
|---------|---------|
|사용자 계정     |Identity 매개 변수와 함께 **Get-InformationBarrierRecipientStatus** cmdlet을 사용합니다. <p>구문: `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p>이름, 별칭, 고유 이름, 정식 도메인 이름, 전자 메일 주소 또는 GUID와 같이 각 사용자를 고유하게 식별하는 모든 값을 사용할 수 있습니다. <p>예: `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p>이 예에서는 Office 365의 두 사용자 계정인 *Meganb과* *Alex의 alexw를* *참조합니다.* *Megan* <p>단일 사용자에 대해 이 cmdlet을 사용할 수도 `Get-InformationBarrierRecipientStatus -Identity <value>` 있습니다. <p>이 cmdlet은 특성 값 및 적용되는 정보 장벽 정책과 같은 사용자에 대한 정보를 반환합니다.|
|세그먼트     |**Get-OrganizationSegment** cmdlet을 사용 합니다.<p>구문: `Get-OrganizationSegment` <p>그러면 조직에 대해 정의된 모든 세그먼트 목록이 표시됩니다.         |
|정보 장벽 정책     |**Get-InformationBarrierPolicy** cmdlet을 사용하세요. <p> 구문: `Get-InformationBarrierPolicy` <p>그러면 정의된 정보 장벽 정책 목록과 해당 상태가 표시됩니다.       |
|최신 정보 장벽 정책 응용 프로그램     | **Get-InformationBarrierPoliciesApplicationStatus** cmdlet을 사용하세요. <p>구문: `Get-InformationBarrierPoliciesApplicationStatus`<p>    그러면 정책 응용 프로그램이 완료, 실패 또는 진행 중인지 여부에 대한 정보가 표시됩니다.       |
|모든 정보 장벽 정책 응용 프로그램|`Get-InformationBarrierPoliciesApplicationStatus -All` 사용<p>그러면 정책 응용 프로그램이 완료, 실패 또는 진행 중인지 여부에 대한 정보가 표시됩니다.|

<!-- IN the " The most recent information barrier policy application, add link to troubleshooting topic -->

## <a name="what-if-i-need-to-remove-or-change-policies"></a>정책을 제거하거나 변경해야 하는 경우 어떻게 하나요?

리소스는 정보 장벽 정책을 관리하는 데 도움이 됩니다.

- 정보 장벽에 문제가 있는 경우 정보 [장벽 문제 해결을 참조하세요.](information-barriers-troubleshooting.md)

- 정책이 적용되지 못하게 중지하는 경우 정책 응용 [프로그램 중지를 참조합니다.](information-barriers-edit-segments-policies.md#stop-a-policy-application)

- 정보 장벽 정책을 제거하려면 정책 [제거를 참조하세요.](information-barriers-edit-segments-policies.md#remove-a-policy)

- 세그먼트 또는 정책을 변경하려면 정보 장벽 정책 [편집(또는 제거)을 참조하세요.](information-barriers-edit-segments-policies.md)

## <a name="example-contosos-departments-segments-and-policies"></a>예: Contoso의 부서, 세그먼트 및 정책

조직에서 세그먼트 및 정책을 정의하는 방법에 대해 설명하는 다음 예제를 고려해 봐야 합니다.

### <a name="contosos-departments-and-plan"></a>Contoso의 부서 및 계획

Contoso에는 HR, 영업, 마케팅, 리서치 및 제조의 다섯 부서가 있습니다. 산업 규정을 준수하기 위해 일부 부서의 사용자가 다음 표에 나와 있는 다른 부서와 의사소통할 수 없습니다.

|세그먼트  |대화할 수 있습니다.  |대화할 수 없습니다.  |
|---------|---------|---------|
|HR     |모든 사람         |(제한 없음)         |
|판매     |HR, 마케팅, 제조         |리서치         |
|마케팅     |모든 사람         |(제한 없음)         |
|리서치     |HR, 마케팅, 제조        |판매     |
|제조 |HR, 마케팅 |HR 또는 마케팅 외의 모든 사람 |

Contoso의 계획에는 다음과 같은 세 가지 정보 장벽 정책이 포함되어 있습니다.

1. 판매가 리서치와 통신하지 못하도록 설계된 정책(및 리서치가 판매와 통신하지 못하도록 하는 다른 정책)
2. 제조가 HR 및 마케팅과만 통신할 수 있도록 디자인된 정책 

HR 또는 마케팅에 대한 정책을 정의할 필요는 없습니다.

### <a name="contosos-defined-segments"></a>Contoso의 정의된 세그먼트

Contoso는 다음과 같이 Azure Active Directory의 Department 특성을 사용하여 세그먼트를 정의합니다.

|부서  |세그먼트 정의  |
|---------|---------|
|HR     | `New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"`        |
|판매     | `New-OrganizationSegment -Name "Sales" -UserGroupFilter "Department -eq 'Sales'"`        |
|마케팅     | `New-OrganizationSegment -Name "Marketing" -UserGroupFilter "Department -eq 'Marketing'"`        |
|리서치     | `New-OrganizationSegment -Name "Research" -UserGroupFilter "Department -eq 'Research'"`        |
|제조     | `New-OrganizationSegment -Name "Manufacturing" -UserGroupFilter "Department -eq 'Manufacturing'"`        |

세그먼트가 정의되어 있는 경우 Contoso는 계속 정책을 정의합니다. 

### <a name="contosos-information-barrier-policies"></a>Contoso의 정보 장벽 정책

Contoso는 다음 표에 설명된 세 가지 정책에 대해 정의합니다.

|정책  |정책 정의  |
|---------|---------|
|정책 1: 판매가 리서치와 통신하지 못하게 방지     | `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p> 이 예에서는 정보 장벽 정책을 *Sales-Research라고 합니다.* 해당 정책을 활성화하고 적용하면 판매 부문에 있는 사용자가 리서치 부문의 사용자와 통신하지 못하게 할 수 있습니다. 이 정책은 단방형 정책입니다. 리서치가 Sales와 통신하는 것을 방지하지 않습니다. 이 경우 정책 2가 필요합니다.      |
|정책 2: 연구가 판매와 통신하지 못하게 방지     | `New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` <p> 이 예에서는 정보 장벽 정책을 *Research-Sales라고 합니다.* 해당 정책을 활성화하고 적용하면 리서치 세그먼트에 있는 사용자가 판매 세그먼트의 사용자와 통신하지 못하게 할 수 있습니다.       |
|정책 3: 제조가 HR 및 마케팅과만 통신하도록 허용     | `New-InformationBarrierPolicy -Name "Manufacturing-HRMarketing" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR","Marketing","Manufacturing" -State Inactive` <p>이 경우 정보 장벽 정책을 *Manufacturing-HRMarketing이라고 합니다.* 해당 정책이 활성화되고 적용된 경우 제조는 HR 및 마케팅과만 통신할 수 있습니다. HR 및 마케팅은 다른 세그먼트와의 통신이 제한되지 않습니다. |

세그먼트 및 정책이 정의되어 있는 경우 Contoso는 **Start-InformationBarrierPoliciesApplication** cmdlet을 실행하여 정책을 적용합니다. 

이 경우 Contoso는 법률 및 산업 요구 사항을 준수합니다.

## <a name="related-articles"></a>관련 문서

- [정보 장벽 개요 보기](information-barriers.md)

- [Microsoft Teams의 정보 장벽](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)
