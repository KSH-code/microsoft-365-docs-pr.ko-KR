---
title: 정보 장벽 특성
description: 이 문서는 정보 장벽 세그먼트를 정의하는 Azure Active Directory 사용자 계정 특성에 대한 참조입니다.
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
ms.localizationpriority: ''
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 33143e85bf17a707ade6dd0d6d0c66886fd85373
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60179154"
---
# <a name="information-barriers-attributes"></a>정보 장벽 특성

사용자 세그먼트화에 Azure Active Directory 특성을 사용할 수 있습니다. 세그먼트가 정의되고 나면 이러한 세그먼트를 정보 장벽 정책에 대한 필터로 사용할 수 있습니다. 예를 들어 **Department를** 사용하여 조직 내의 부서별로 사용자 세그먼트를 정의할 수 있습니다(한 번의 직원이 두 부서에 동시에 작업하지 않을 경우).

이 문서에서는 정보 장벽이 있는 특성을 사용하는 방법을 설명하고 사용할 수 있는 특성 목록을 제공합니다. 정보 장벽에 대한 자세한 내용은 다음 리소스를 참조하세요.

- [정보 장벽](information-barriers.md)
- [정보 장벽에 대한 정책을 Microsoft Teams](information-barriers-policies.md)
- [정보 장벽 정책 편집(또는 제거) ](information-barriers-edit-segments-policies.md)

## <a name="how-to-use-attributes-in-information-barrier-policies"></a>정보 장벽 정책에서 특성을 사용하는 방법

이 문서에 나열된 특성을 사용하여 사용자 세그먼트를 정의하거나 편집할 수 있습니다. 정의된 세그먼트는 정보 장벽 정책에서 매개 변수(UserGroupFilter 값이라고도 합니다.)  [](information-barriers-policies.md)

1. 세그먼트를 정의하는 데 사용할 특성을 결정해야 합니다. (이 [문서의 참조](#reference) 섹션을 참조하세요.)

2. 사용자 계정에 1단계에서 선택한 특성에 대해 값이 채워진지 확인 사용자 계정 세부 정보를 보고 필요한 경우 사용자 계정을 편집하여 특성 값을 포함합니다. 

    - 여러 계정을 편집하거나 PowerShell을 사용하여 단일 계정을 편집하려면 [PowerShell을](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md)사용하여 사용자 계정 속성 Office 365 참조하세요.

    - 단일 계정을 편집하려면 [를](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)사용하여 사용자 프로필 정보 추가 또는 Azure Active Directory.

3. [다음 예제와 유사한 PowerShell을](information-barriers-policies.md#define-segments-using-powershell)사용하여 세그먼트를 정의합니다.

    |**예**|**Cmdlet**|
    |:----------|:---------|
    | Department 특성을 사용하여 Segment1이라는 세그먼트 정의 | `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "Department -eq 'Department1'"` |
    | MemberOf 특성을 사용하여 SegmentA라는 세그먼트를 정의합니다(이 특성에 "BlueGroup"과 같은 그룹 이름이 포함된 경우) | `New-OrganizationSegment -Name "SegmentA" -UserGroupFilter "MemberOf -eq 'BlueGroup'"` |
    | ExtensionAttribute1을 사용하여 DayTraders라는 세그먼트를 정의합니다.(이 특성에 "DayTrader"와 같은 직위가 포함되어 있는 경우) | `New-OrganizationSegment -Name "DayTraders" -UserGroupFilter "ExtensionAttribute1 -eq 'DayTrader'"` |

    > [!TIP]
    > 세그먼트를 정의할 때 모든 세그먼트에 동일한 특성을 사용 합니다. 예를 들어 Department를 사용하여 일부 세그먼트를 정의하는 경우 *Department를* 사용하여 모든 세그먼트를 *정의합니다.* Department를 사용하여 일부 세그먼트를 정의하고 MemberOf를 사용하는 세그먼트는 *정의하지 않습니다.*  세그먼트가 겹치지 않는지 확인 각 사용자를 정확히 하나의 세그먼트에 할당해야 합니다.

## <a name="reference"></a>참조

다음 표에는 정보 장벽에 사용할 수 있는 특성이 나열됩니다.

|**Azure Active Directory <br/> 이름(LDAP 표시 이름)**|**Exchange 이름**|
|:---------------------------------------------------------------|:-------------------------|
| Co | Co |
| Company | Company |
| 부서 | 부서 |
| ExtensionAttribute1 | CustomAttribute1 |
| ExtensionAttribute2 | CustomAttribute2 |
| ExtensionAttribute3 | CustomAttribute3 |
| ExtensionAttribute4 | CustomAttribute4 |
| ExtensionAttribute5 | CustomAttribute5 |
| ExtensionAttribute6 | CustomAttribute6 |
| ExtensionAttribute7 | CustomAttribute7 |
| ExtensionAttribute8 | CustomAttribute8 |
| ExtensionAttribute9 | CustomAttribute9 |
| ExtensionAttribute10 | CustomAttribute10 |
| ExtensionAttribute11 | CustomAttribute11 |
| ExtensionAttribute12 | CustomAttribute12 |
| ExtensionAttribute13 | CustomAttribute13 |
| ExtensionAttribute14 | CustomAttribute14 |
| ExtensionAttribute15 | CustomAttribute15 |
| MSExchExtensionCustomAttribute1 | ExtensionCustomAttribute1 |
| MSExchExtensionCustomAttribute2 | ExtensionCustomAttribute2 |
| MSExchExtensionCustomAttribute3 | ExtensionCustomAttribute3 |
| MSExchExtensionCustomAttribute4 | ExtensionCustomAttribute4 |
| MSExchExtensionCustomAttribute5 | ExtensionCustomAttribute5 |
| MailNickname | 별칭 |
| PhysicalDeliveryOfficeName | Office |
| PostalCode | PostalCode |
| ProxyAddresses | EmailAddresses |
| StreetAddress | StreetAddress |
| TargetAddress | ExternalEmailAddress |
| UsageLocation | UsageLocation |
| UserPrincipalName | UserPrincipalName |
| 메일 | WindowsEmailAddress |
| 설명 | 설명 |
| MemberOf | MemberOfGroup |

## <a name="resources"></a>리소스

- [정보 장벽에 대한 정책을 Microsoft Teams](information-barriers-policies.md)
- [정보 장벽 문제 해결](/office365/troubleshoot/information-barriers/information-barriers-troubleshooting)
- [정보 장벽](information-barriers.md)