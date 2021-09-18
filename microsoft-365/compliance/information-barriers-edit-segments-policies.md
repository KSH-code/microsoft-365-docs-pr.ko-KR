---
title: 정보 장벽 정책 관리
description: 정보 장벽에 대한 정책을 편집하거나 제거하는 방법을 학습합니다.
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
f1.keywords:
- NOCSH
ms.openlocfilehash: dff13dd6c4011ec73a1976bce0af69b607e391b0
ms.sourcegitcommit: 7e7effd8ef4ffe75cdee7bb8517fec8608e4c230
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/18/2021
ms.locfileid: "59444058"
---
# <a name="manage-information-barrier-policies"></a>정보 장벽 정책 관리

정보 장벽 정책을 [정의한](information-barriers-policies.md)후 문제 해결의 일부로 또는 정기적인 유지 관리로 해당 정책이나 사용자 세그먼트를 변경해야 할 수 있습니다. [](/office365/troubleshoot/information-barriers/information-barriers-troubleshooting)

## <a name="what-do-you-want-to-do"></a>무슨 작업을 하고 싶으십니까?

|**작업**|**설명**|
|:---------|:--------------|
| [사용자 계정 특성 편집](#edit-user-account-attributes) | 세그먼트를 정의하는 데 Azure Active Directory 특성을 입력합니다.<br/>사용자가 포함되어야 하는 세그먼트에 포함되지 않은 경우 사용자 계정 특성을 편집하여 사용자가 있는 세그먼트를 변경하거나, 다른 특성을 사용하여 세그먼트를 정의할 수 있습니다. |
| [세그먼트 편집](#edit-a-segment) | 세그먼트의 정의 방법을 변경하려는 경우 세그먼트를 편집합니다. <br/>예를 들어 Department를 사용하여 원래 세그먼트를 정의한 다음 *MemberOf와* 같은 다른 특성을 *사용하려는 경우를* 예로 들 수 있습니다. |
| [정책 편집](#edit-a-policy) | 정책의 작동 방법을 변경하려는 경우 정보 장벽 정책을 편집합니다.<br/>예를 들어 두 세그먼트 간의 통신을 차단하는 대신 특정 세그먼트 간에만 통신이 발생하도록 허용할 수 있습니다. |
| [정책을 비활성 상태로 설정](#set-a-policy-to-inactive-status) |정책을 변경하거나 정책을 적용하지 못하게 하려는 경우 정책을 비활성 상태로 설정 |
| [정책 제거](#remove-a-policy) | 더 이상 특정 정책을 적용하지 필요가 없는 경우 정보 장벽 정책을 제거합니다. |
| [정책 응용 프로그램 중지](#stop-a-policy-application) | 정보 장벽 정책을 적용하는 프로세스를 중지하려는 경우 이 작업을 수행하세요.<br/> 정책 응용 프로그램을 중지하는 것은 즉각적인 것이 아니며 사용자에게 이미 적용된 정책을 실행 취소하지 않습니다. |
| [정보 장벽을 위한 정책 정의](information-barriers-policies.md) | 이러한 정책이 아직 설정되지 않은 경우 정보 장벽 정책을 정의하고 특정 사용자 그룹 간의 통신을 제한하거나 제한해야 합니다. |
| [정보 장벽 문제 해결](/office365/troubleshoot/information-barriers/information-barriers-troubleshooting) | 정보 장벽으로 예기치 않은 문제가 발생할 경우 이 문서를 참조하세요. |

> [!IMPORTANT]
> 이 문서에 설명된 작업을 수행하려면 다음 중 하나와 같은 적절한 역할을 할당해야 합니다.<br/>- Microsoft 365 Enterprise 전역 관리자<br/>- 전역 관리자<br/>- 준수 관리자<br/>- IB 준수 관리(새로운 역할입니다!)<br><br>정보 장벽의 선행 준비에 대한 자세한 내용은 [Prerequisites (for information barrier policies)을 참조하십시오.](information-barriers-policies.md#prerequisites)<br><br> 보안 및 준수 센터 [PowerShell에 & 합니다.](/powershell/exchange/connect-to-scc-powershell)

## <a name="edit-user-account-attributes"></a>사용자 계정 특성 편집

다음 절차에 따라 사용자를 분할하는 데 사용되는 특성을 편집합니다. 예를 들어 Department 특성을 사용하는 경우 하나 이상의 사용자 계정에 현재 Department에 대해 나열된 값이 없는 경우 부서 정보를 포함하도록 해당 사용자 계정을 편집해야 합니다. 사용자 계정 특성은 정보 장벽 정책을 할당할 수 있도록 세그먼트를 정의하는 데 사용됩니다.

1. 특성 값 및 할당된 세그먼트와 같은 특정 사용자 계정에 대한 세부 정보를 확인하려면 Identity 매개 변수와 **함께 Get-InformationBarrierRecipientStatus** cmdlet을 사용합니다.

    |**다중값 속성 구문 표에서 선택하는 구문은 cmdlet에 대한 매개 변수 값으로 지정됩니다. 예를 들어 다음 명령을 통해 다중값 속성에 여러 값을 추가할 수 있습니다.**|**예**|
    |:---------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> 이름, 별칭, 고유 이름, 정식 도메인 이름, 전자 메일 주소 또는 GUID와 같이 각 사용자를 고유하게 식별하는 모든 값을 사용할 수 있습니다. <p> (단일 사용자에 대해 이 cmdlet을 사용할 수도 있습니다. `Get-InformationBarrierRecipientStatus -Identity <value>` ) |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> 이 예제에서는 2개의 사용자 계정인 Office 365 *meganb* 및 *Alex의 alexw를* *참조합니다.* |

2. 사용자 계정 프로필에 대해 편집할 특성을 결정하십시오. 자세한 내용은 정보 장벽 [정책에 대한 특성을 참조하세요.](information-barriers-attributes.md) 

3. 이전 단계에서 선택한 특성의 값을 포함하도록 하나 이상의 사용자 계정을 편집합니다. 이 작업을 수행하기 위해 다음 절차 중 하나를 사용 합니다.

    - 단일 계정을 편집하려면 [를](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)사용하여 사용자 프로필 정보 추가 또는 Azure Active Directory.

    - 여러 계정을 편집하거나 PowerShell을 사용하여 단일 계정을 편집하려면 [PowerShell을](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md)사용하여 사용자 계정 속성 Office 365 참조하세요.

## <a name="edit-a-segment"></a>세그먼트 편집

다음 절차에 따라 사용자 세그먼트의 정의를 편집합니다. 예를 들어 세그먼트의 이름을 변경하거나 세그먼트에 포함되는 대상을 확인하는 데 사용되는 필터를 변경할 수 있습니다.

1. 모든 기존 세그먼트를 보시고 **Get-OrganizationSegment** cmdlet을 사용 합니다.

    구문: `Get-OrganizationSegment`

    세그먼트 유형, 해당 UserGroupFilter 값, 이를 만들거나 마지막으로 수정한 사람, GUID 등 각 세그먼트 및 세부 정보 목록이 표시됩니다.

    > [!TIP]
    > 나중에 참조할 수 있도록 세그먼트 목록을 인쇄하거나 저장합니다. 예를 들어 세그먼트를 편집하려는 경우 해당 이름을 알거나 값을 식별해야 합니다(Identity 매개 변수와 함께 사용됩니다).

2. 세그먼트를 편집하려면 **Set-OrganizationSegment** cmdlet을 **Identity** 매개 변수 및 관련 세부 정보와 함께 사용합니다.

    |**다중값 속성 구문 표에서 선택하는 구문은 cmdlet에 대한 매개 변수 값으로 지정됩니다. 예를 들어 다음 명령을 통해 다중값 속성에 여러 값을 추가할 수 있습니다.**|**예**|
    |:---------|:----------|
    | `Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"` |`Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'HRDept'"` <p> 이 예제에서는 *GUID가 c96e0837-c232-4a8a-841e-ef45787d8fcd인* 세그먼트의 경우 부서 이름을 "HRDept"로 업데이트했습니다. |

조직에 대한 세그먼트 편집을 마치면 정보 장벽 [](information-barriers-policies.md#part-2-define-information-barrier-policies) 정책을 정의하거나 [편집할](#edit-a-policy) 수 있습니다.

## <a name="edit-a-policy"></a>정책 편집

1. 현재 정보 장벽 정책 목록을 보기 위해 **Get-InformationBarrierPolicy** cmdlet을 사용하세요.

    구문: `Get-InformationBarrierPolicy`

    결과 목록에서 변경할 정책을 식별합니다. 정책의 GUID 및 이름을 메모합니다.

2. **Set-InformationBarrierPolicy** cmdlet을 **Identity** 매개 변수와 함께 사용하여 변경 내용을 지정합니다.

    예: 리서치 세그먼트가  영업 및 마케팅 세그먼트와 통신하는 것을 차단하기 위해 정책이 정의되어 있는 *경우를 가정해* 보겠습니다.  정책은 다음 cmdlet을 사용하여 정의했습니다. `New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales","Marketing"`

    리서치 부문의 사용자가 HR  세그먼트의 사용자와만 통신할 수 있도록 변경하려는 *경우를 가정해* 가정해 5000명을 추가합니다. 이 변경을 위해 다음 cmdlet을 사용 합니다. `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`

    이 예제에서는 "SegmentsBlocked"를 "SegmentsAllowed"로 변경하고 *HR 세그먼트를 지정했습니다.*

3. 정책 편집을 마치면 변경 내용을 적용해야 합니다. (정보 [장벽 정책 적용을](information-barriers-policies.md#part-3-apply-information-barrier-policies)참조하세요.)

## <a name="set-a-policy-to-inactive-status"></a>정책을 비활성 상태로 설정

1. 현재 정보 장벽 정책 목록을 보기 위해 **Get-InformationBarrierPolicy** cmdlet을 사용하세요.

    구문: `Get-InformationBarrierPolicy`

    결과 목록에서 변경하거나 제거할 정책을 식별합니다. 정책의 GUID 및 이름을 메모합니다.

2. 정책의 상태를 비활성으로 설정하기 위해 Identity 매개 변수와 **함께 Set-InformationBarrierPolicy** cmdlet을 사용하며 State 매개 변수를 비활성으로 설정하십시오.

    |**다중값 속성 구문 표에서 선택하는 구문은 cmdlet에 대한 매개 변수 값으로 지정됩니다. 예를 들어 다음 명령을 통해 다중값 속성에 여러 값을 추가할 수 있습니다.**|**예**|
    |:---------|:----------|
    | `Set-InformationBarrierPolicy -Identity GUID -State Inactive` | `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c9377247 -State Inactive` <p> 이 예에서는 GUID가 *43c37853-ea10-4b90-a23d-ab8c9377247인* 정보 장벽 정책을 비활성 상태로 설정했습니다. |

3. 변경 내용을 적용하기 위해 **Start-InformationBarrierPoliciesApplication** cmdlet을 사용하세요.

    구문: `Start-InformationBarrierPoliciesApplication`

    조직에 대한 변경 내용은 사용자에 따라 적용됩니다. 조직 규모가 큰 경우 이 프로세스를 완료하는 데 24시간 이상이 걸릴 수 있습니다. 일반적으로 사용자 계정 5,000개가 처리되는 데 1시간 정도 소요됩니다.

이때 하나 이상의 정보 장벽 정책이 비활성 상태로 설정됩니다. 여기에서 다음 작업을 수행할 수 있습니다.

- 그대로 유지(비활성 상태로 설정된 정책은 사용자에게 영향을 미치지 않습니다.
- [정책 편집](#edit-a-policy) 
- [정책 제거](#remove-a-policy)

## <a name="remove-a-policy"></a>정책 제거

1. 현재 정보 장벽 정책 목록을 보기 위해 **Get-InformationBarrierPolicy** cmdlet을 사용하세요.

    구문: `Get-InformationBarrierPolicy`

    결과 목록에서 제거할 정책을 식별합니다. 정책의 GUID 및 이름을 메모합니다. 정책이 비활성 상태로 설정되어 있는지 확인

2. **Remove-InformationBarrierPolicy** cmdlet을 Identity 매개 변수와 함께 사용합니다.

    |**다중값 속성 구문 표에서 선택하는 구문은 cmdlet에 대한 매개 변수 값으로 지정됩니다. 예를 들어 다음 명령을 통해 다중값 속성에 여러 값을 추가할 수 있습니다.**|**예**|
    |:---------|:----------|
    | `Remove-InformationBarrierPolicy -Identity GUID` | `Remove-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471` <p> 이 예에서는 GUID가 *43c37853-ea10-4b90-a23d-ab8c93772471인* 정책을 제거합니다. |

    메시지가 표시되면 변경을 확인 합니다.

3. 제거할 각 정책에 대해 1-2단계를 반복합니다.

4. 정책 제거가 완료되면 변경 내용을 적용합니다. 이 작업을 수행하기 위해 **Start-InformationBarrierPoliciesApplication** cmdlet을 사용하세요.

    구문: `Start-InformationBarrierPoliciesApplication`

    조직에 대한 변경 내용은 사용자에 따라 적용됩니다. 조직 규모가 큰 경우 이 프로세스를 완료하는 데 24시간 이상이 걸릴 수 있습니다.

## <a name="stop-a-policy-application"></a>정책 응용 프로그램 중지

정보 장벽 정책 적용을 시작한 후 해당 정책이 적용되지 못하게 하려는 경우 다음 절차를 사용합니다. 프로세스를 시작하는 데 약 30~35분이 걸립니다.

1. 최신 정보 장벽 정책 응용 프로그램의 상태를 확인하기 위해 **Get-InformationBarrierPoliciesApplicationStatus** cmdlet을 사용하세요.

    구문: `Get-InformationBarrierPoliciesApplicationStatus`

    응용 프로그램의 GUID를 참고하십시오.

2. **Stop-InformationBarrierPoliciesApplication** cmdlet을 Identity 매개 변수와 함께 사용합니다.

    |**다중값 속성 구문 표에서 선택하는 구문은 cmdlet에 대한 매개 변수 값으로 지정됩니다. 예를 들어 다음 명령을 통해 다중값 속성에 여러 값을 추가할 수 있습니다.**|**예**|
    |:---------|:----------|
    | `Stop-InformationBarrierPoliciesApplication -Identity GUID` | `Stop-InformationBarrierPoliciesApplication -Identity 46237888-12ca-42e3-a541-3fcb7b5231d1` <p> 이 예에서는 정보 장벽 정책이 적용되지 않습니다. |

## <a name="resources"></a>리소스

- [정보 장벽 개요 보기](information-barriers.md)
- [정보 장벽을 위한 정책 정의](information-barriers-policies.md)
- [정보 장벽에 대해 자세히 Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams)
- [온라인에서 정보 장벽에 대해 SharePoint 정보](/sharepoint/information-barriers)
- [정보 장벽에 대해 자세히 OneDrive](/onedrive/information-barriers)
- [정보 장벽 정책의 속성](information-barriers-attributes.md)
- [정보 장벽 문제 해결](/office365/troubleshoot/information-barriers/information-barriers-troubleshooting)