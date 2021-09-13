---
title: 정보 장벽 문제 해결
description: 이 문서를 정보 장벽 문제 해결에 대한 가이드로 사용하세요.
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
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: de415ba7b68df786ead038bb72465c445a86ba5a
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59191389"
---
# <a name="troubleshooting-information-barriers"></a>정보 장벽 문제 해결

[정보 장벽은](information-barriers.md) 조직이 법적 요구 사항 및 산업 규정을 준수하는 데 도움이 될 수 있습니다. 예를 들어 정보 장벽으로 특정 사용자 그룹 간의 통신을 제한하여 이해 상충이나 기타 문제를 방지할 수 있습니다. 정보 장벽을 설정하는 방법에 대한 자세한 내용은 정보 장벽에 대한 정책 [정의를 참조하세요.](information-barriers-policies.md)

정보 장벽이 발생하면 예기치 않은 문제가 발생할 경우 이러한 문제를 해결하기 위해 몇 가지 단계를 취할 수 있습니다. 이 문서를 가이드로 사용하세요.

> [!IMPORTANT]
> 이 문서에 설명된 작업을 수행하려면 다음 중 하나와 같은 적절한 역할을 할당해야 합니다.<br/>- Microsoft 365 Enterprise 전역 관리자<br/>- 전역 관리자<br/>- 준수 관리자<br/>- IB 준수 관리(새로운 역할입니다!)<p>정보 장벽의 선행 준비에 대한 자세한 내용은 [Prerequisites (for information barrier policies)을 참조하십시오.](information-barriers-policies.md#prerequisites)<p>보안 및 준수 [센터 PowerShell & 에 연결해야 합니다.](/powershell/exchange/connect-to-scc-powershell)

## <a name="issue-users-are-unexpectedly-blocked-from-communicating-with-others-in-microsoft-teams"></a>문제: 사용자가 예기치 않게 사용자의 다른 사용자와 통신하지 못하게 Microsoft Teams 

이 경우 다른 사용자와 통신하는 예기치 않은 문제를 보고하는 Microsoft Teams. 예를 들면 다음과 같습니다.

- 사용자가 검색을 했지만 검색할 수 없는 경우 해당 사용자의 다른 사용자를 Microsoft Teams.
- 사용자가 검색할 수 있지만 선택할 수 없는 경우 해당 사용자에 있는 다른 사용자를 Microsoft Teams.
- 사용자는 다른 사용자를 볼 수는 있지만 다른 사용자의 다른 사용자에게 메시지를 보낼 수는 Microsoft Teams.

### <a name="what-to-do"></a>수행할 작업

사용자가 정보 장벽 정책의 영향을 받는지 여부를 판단합니다. 정책 구성 방법에 따라 정보 장벽이 예상대로 작동할 수 있습니다. 또는 조직의 정책을 구체화해야 할 수 있습니다.

1. **Get-InformationBarrierRecipientStatus** cmdlet을 Identity 매개 변수와 함께 사용합니다. 

    |**다중값 속성 구문 표에서 선택하는 구문은 cmdlet에 대한 매개 변수 값으로 지정됩니다. 예를 들어 다음 명령을 통해 다중값 속성에 여러 값을 추가할 수 있습니다.**|**예**|
    |:---------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity` <p> 이름, 별칭, DN(고유 이름), 정식 DN, 전자 메일 주소 또는 GUID와 같이 각 받는 사람을 고유하게 식별하는 ID 값을 사용할 수 있습니다. |`Get-InformationBarrierRecipientStatus -Identity meganb` <p> 이 예제에서는 Identity 매개 변수에 별칭(*meganb)을* 사용합니다. 이 cmdlet은 사용자가 정보 장벽 정책의 영향을 받는지 여부를 나타내는 정보를 반환합니다. (*ExoPolicyId: \<GUID> .) |

    **사용자가 정보 장벽 정책에 포함되지 않은 경우 고객 지원에 문의하세요.** 그렇지 않은 경우 다음 단계로 진행합니다.

2. 정보 장벽 정책에 포함된 세그먼트를 찾아 하세요. 이 작업을 위해 Identity 매개 변수와 `Get-InformationBarrierPolicy` 함께 cmdlet을 사용합니다. 

    |**다중값 속성 구문 표에서 선택하는 구문은 cmdlet에 대한 매개 변수 값으로 지정됩니다. 예를 들어 다음 명령을 통해 다중값 속성에 여러 값을 추가할 수 있습니다.**|**예**|
    |:---------|:----------|
    | `Get-InformationBarrierPolicy` <p> 이전 단계에서 받은 정책 GUID(ExoPolicyId)와 같은 세부 정보를 ID 값으로 사용 합니다. | `Get-InformationBarrierPolicy -Identity b42c3d0f-49e9-4506-a0a5-bf2853b5df6f` <p> 이 예에서는 ExoPolicyId *b42c3d0f-49e9-4506-a0a5-bf2853b5df6f가* 있는 정보 장벽 정책에 대한 자세한 정보를 제공합니다. |

    cmdlet을 실행한 후 결과에서 **AssignedSegment,** **SegmentsAllowed** 및 **SegmentsBlocked 값을** 검색합니다.

    예를 들어 cmdlet을 실행한 후 결과 목록에서 `Get-InformationBarrierPolicy` 다음을 보했습니다.

    ```powershell
    AssignedSegment : Sales
    SegmentsAllowed : {}
    SegmentsBlocked : {Research}
    ```

    이 경우 정보 장벽 정책이 판매 및 연구 부문에 있는 사용자에 영향을 주는 것으로 볼 수 있습니다. 이 경우 Sales의 사용자가 리서치의 사용자와 통신할 수 없습니다.

    문제가 해결된 것 같은 경우 정보 장벽이 예상대로 작동하고 있습니다. 로그인하지 않은 경우에는 다음 단계를 진행합니다.

3. 세그먼트가 올바르게 정의되어 있는지 확인합니다. 이 작업을 위해 `Get-OrganizationSegment` cmdlet을 사용하여 결과 목록을 검토합니다.

    |**다중값 속성 구문 표에서 선택하는 구문은 cmdlet에 대한 매개 변수 값으로 지정됩니다. 예를 들어 다음 명령을 통해 다중값 속성에 여러 값을 추가할 수 있습니다.**|**예**|
    |:---------|:----------|
    | `Get-OrganizationSegment`<p> 이 cmdlet은 Identity 매개 변수와 함께 사용합니다. | `Get-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd` <p> 이 예제에서는 *GUID가 c96e0837-c232-4a8a-841e-ef45787d8fcd인* 세그먼트에 대한 정보를 받고 있습니다. |

    세그먼트에 대한 세부 정보를 검토합니다. 필요한 경우 [세그먼트를 편집한](information-barriers-edit-segments-policies.md#edit-a-segment)다음 `Start-InformationBarrierPoliciesApplication` cmdlet을 다시 사용하세요.

    정보 장벽 정책에 여전히 문제가 있는 경우 **고객 지원에 문의하세요.**

## <a name="issue-communications-are-allowed-between-users-who-should-be-blocked-in-microsoft-teams"></a>문제: 사용자 간에 통신이 허용 Microsoft Teams됩니다.

이 경우 정보 장벽이 정의, 활성 및 적용되어도 서로 통신하지 못하게 해야 하는 사람은 서로 채팅을 하여 서로 통화할 수 Microsoft Teams.

### <a name="what-to-do"></a>수행할 작업

해당 사용자가 정보 장벽 정책에 포함되어 있는지 확인 

1. Identity 매개 변수와 함께 **Get-InformationBarrierRecipientStatus** cmdlet을 사용합니다.

    |**구문** _|_ *예제**|
    |:----------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> 이름, 별칭, 고유 이름, 정식 도메인 이름, 전자 메일 주소 또는 GUID와 같이 각 사용자를 고유하게 식별하는 모든 값을 사용할 수 있습니다. |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> 이 예제에서는 2개의 사용자 계정인 Office 365 *meganb* 및 *Alex의 alexw를* *참조합니다.* |

    > [!TIP]
    > 단일 사용자에 대해 이 cmdlet을 사용할 수도 있습니다. `Get-InformationBarrierRecipientStatus -Identity <value>`

2. 결과를 검토합니다. **Get-InformationBarrierRecipientStatus** cmdlet은 특성 값 및 적용되는 모든 정보 장벽 정책과 같은 사용자에 대한 정보를 반환합니다.

    다음 표에 설명된 결과를 검토한 후 다음 단계를 수행합니다.

    |**결과**|**다음에 할 일**|
    |:----------|:------------------|
    | 선택한 사용자에 대한 세그먼트가 나열되지 않습니다. | 다음 중 하나를 수행합니다.<br/>- 사용자 프로필을 편집하여 기존 세그먼트에 사용자를 Azure Active Directory. PowerShell을 사용하여 사용자 계정 [Office 365 구성을 참조하세요.](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md)<br/>- 정보 장벽에 지원되는 특성을 사용하여 [세그먼트를 정의합니다.](information-barriers-attributes.md) 그런 다음 새 [정책을 정의하거나](information-barriers-policies.md#part-2-define-information-barrier-policies) 해당 세그먼트를 포함하기 위해 기존 정책을 편집합니다. [](information-barriers-edit-segments-policies.md#edit-a-policy) |
    | 세그먼트가 나열되지만 이러한 세그먼트에 정보 장벽 정책이 할당되지 않습니다. | 다음 중 하나를 수행합니다.<br/>- [해당 각 세그먼트에](information-barriers-policies.md#part-2-define-information-barrier-policies) 대한 새 정보 장벽 정책 정의 <br/>- [기존 정보 장벽 정책을 편집하여](information-barriers-edit-segments-policies.md#edit-a-policy) 올바른 세그먼트에 할당 |
    | 세그먼트가 나열되어 있으며 각각 정보 장벽 정책에 포함됩니다. | - `Get-InformationBarrierPolicy` cmdlet을 실행하여 정보 장벽 정책이 활성 상태인지 확인<br/>- `Get-InformationBarrierPoliciesApplicationStatus` cmdlet을 실행하여 정책이 적용되는지 확인<br/>- `Start-InformationBarrierPoliciesApplication` cmdlet을 실행하여 모든 활성 정보 장벽 정책을 적용합니다. |

## <a name="issue-i-need-to-remove-a-single-user-from-an-information-barrier-policy"></a>문제: 정보 장벽 정책에서 단일 사용자를 제거해야 합니다.

이 경우 정보 장벽 정책이 적용되어 한 개 이상의 사용자가 예기치 않게 다른 사용자와 통신하지 못하게 Microsoft Teams. 정보 장벽 정책을 모두 제거하는 대신 정보 장벽 정책에서 하나 이상의 개별 사용자를 제거할 수 있습니다.

### <a name="what-to-do"></a>수행할 작업

정보 장벽 정책은 사용자 세그먼트에 할당됩니다. 세그먼트는 사용자 계정 프로필의 특정 특성을 [사용하여 정의됩니다.](information-barriers-attributes.md) 단일 사용자에서 정책을 제거해야 하는 경우 사용자가 정보 장벽의 영향을 받는 세그먼트에 더 Azure Active Directory 사용자 프로필을 편집할 수 있습니다.

1. Identity 매개 변수와 함께 **Get-InformationBarrierRecipientStatus** cmdlet을 사용합니다. 이 cmdlet은 특성 값 및 적용되는 모든 정보 장벽 정책과 같은 사용자에 대한 정보를 반환합니다.

    |**다중값 속성 구문 표에서 선택하는 구문은 cmdlet에 대한 매개 변수 값으로 지정됩니다. 예를 들어 다음 명령을 통해 다중값 속성에 여러 값을 추가할 수 있습니다.**|**예**|
    |:---------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> 이름, 별칭, 고유 이름, 정식 도메인 이름, 전자 메일 주소 또는 GUID와 같이 각 사용자를 고유하게 식별하는 모든 값을 사용할 수 있습니다. | `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> 이 예제에서는 2개의 사용자 계정인 Office 365 *meganb* 및 *Alex의 alexw를* *참조합니다.*          |
    | `Get-InformationBarrierRecipientStatus -Identity <value>` <p> 이름, 별칭, 고유 이름, 정식 도메인 이름, 전자 메일 주소 또는 GUID와 같이 사용자를 고유하게 식별하는 모든 값을 사용할 수 있습니다.|`Get-InformationBarrierRecipientStatus -Identity jeanp`<p> 이 예제에서는 Office 365 *단일 계정을 참조합니다.* |

2. 결과를 검토하여 정보 장벽 정책이 할당되어 있으며 사용자가 속한 세그먼트를 검토합니다.

3. 정보 장벽의 영향을 받는 세그먼트에서 사용자를 제거하려면 에서 사용자 프로필 정보를 [Azure Active Directory.](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

4. FwdSync가 발생할 때까지 약 30분 정도 기다립니다. 또는 cmdlet을 실행하여 모든 활성 정보 `Start-InformationBarrierPoliciesApplication` 장벽 정책을 적용합니다.

## <a name="issue-the-information-barrier-application-process-is-taking-too-long"></a>문제: 정보 장벽 응용 프로그램 프로세스 시간이 너무 오래 늦습니다.

**Start-InformationBarrierPoliciesApplication** cmdlet을 실행한 후 프로세스를 완료하는 데 시간이 매우 오래입니다.

### <a name="what-to-do"></a>수행할 작업

정책 응용 프로그램 cmdlet을 실행하면 조직의 모든 계정에 대해 사용자에 의해 정보 장벽 정책이 적용되거나 제거됩니다. 사용자가 많은 경우 처리하는 데 시간이 걸릴 수 있습니다. 일반적으로 사용자 계정 5,000개가 처리되는 데 1시간 정도 소요됩니다.

1. **Get-InformationBarrierPoliciesApplicationStatus** cmdlet을 사용하여 최신 정책 응용 프로그램의 상태를 확인할 수 있습니다.

    |**최신 정책 응용 프로그램을 보시고**|**모든 정책 응용 프로그램의 상태를 확인**|
    |:---------------------------------------------|:---------------------------------------------|
    | `Get-InformationBarrierPoliciesApplicationStatus` | `Get-InformationBarrierPoliciesApplicationStatus -All $true` |

    그러면 정책 응용 프로그램이 완료, 실패 또는 진행 중인지 여부에 대한 정보가 표시됩니다.

2. 이전 단계의 결과에 따라 다음 단계 중 하나를 수행합니다.
  
    |**상태**|**다음 단계**|
    |:---------|:------------|
    | **시작되지 않습니다.** | **Start-InformationBarrierPoliciesApplication** cmdlet이 실행된 후 45분 이상이 지난 경우 감사 로그를 검토하여 정책 정의에 오류가 있는지 또는 응용 프로그램이 시작되지 않은 다른 이유가 없는지 검토합니다. |
    | **실패** | 응용 프로그램이 실패한 경우 감사 로그를 검토합니다. 세그먼트 및 정책도 검토합니다. 두 개 이상의 세그먼트에 할당된 사용자가 있나요? 세그먼트에 두 개 이상의 정치가 할당되어 있나요? 필요한 경우 [세그먼트를](information-barriers-edit-segments-policies.md#edit-a-segment) 편집하고 [](information-barriers-edit-segments-policies.md#edit-a-policy)정책을 편집한 다음 **Start-InformationBarrierPoliciesApplication** cmdlet을 다시 실행합니다. |
    | **진행 중** | 응용 프로그램이 아직 진행 중이면 완료할 시간을 더 허용합니다. 며칠이 지난 경우 감사 로그를 수집한 다음 지원에 문의합니다. |

## <a name="issue-information-barrier-policies-are-not-being-applied-at-all"></a>문제: 정보 장벽 정책이 적용되지 않습니다.

이 경우 세그먼트를 정의하고 정보 장벽 정책을 정의하고 해당 정책을 적용하려고 시도했습니다. 그러나 cmdlet을 실행하면 정책 응용 프로그램이 실패한 `Get-InformationBarrierPoliciesApplicationStatus` 것으로 볼 수 있습니다.

### <a name="what-to-do"></a>수행할 작업

조직에 주소 Exchange [정책이](/exchange/address-books/address-book-policies/address-book-policies) 없는지 확인 이러한 정책은 정보 장벽 정책이 적용되지 않도록 합니다.

1. 커넥트 [PowerShell을 Exchange Online 합니다.](/powershell/exchange/connect-to-exchange-online-powershell)

2. [Get-AddressBookPolicy](/powershell/module/exchange/get-addressbookpolicy) cmdlet을 실행하고 결과를 검토합니다.

    |**결과**|**다음 단계**|
    |:----------|:------------|
    | Exchange 정책이 나열됩니다. | [주소 책 정책 제거](/exchange/address-books/address-book-policies/remove-an-address-book-policy) |
    | 주소 책 정책이 없습니다. |감사 로그를 검토하여 정책 응용 프로그램이 실패하는 이유 확인 |

3. [사용자 계정, 세그먼트,](information-barriers-policies.md#view-status-of-user-accounts-segments-policies-or-policy-application)정책 또는 정책 응용 프로그램의 상태를 볼 수 있습니다.

## <a name="issue-information-barrier-policy-not-applied-to-all-designated-users"></a>문제: 지정된 모든 사용자에게 정보 장벽 정책이 적용되지 않습니다.

세그먼트를 정의하고 정보 장벽 정책을 정의하고 해당 정책을 적용하려고 시도한 후 정책이 일부 받는 사람에게 적용되고 있지만 다른 받는 사람에게는 적용되지 않을 수 있습니다.
`Get-InformationBarrierPoliciesApplicationStatus`cmdlet을 실행할 때 출력에서 이러한 텍스트를 검색합니다.

> ID: `<application guid>`
>
> 총 받는 사람: 81527
>
> 실패한 받는 사람: 2
>
> 실패 범주: 없음
>
> 상태: 완료

### <a name="what-to-do"></a>수행할 작업

1. 감사 로그에서 을 `<application guid>` 검색합니다. 이 PowerShell 코드를 복사하고 변수를 수정할 수 있습니다.

```powershell
$DetailedLogs = Search-UnifiedAuditLog -EndDate <yyyy-mm-ddThh:mm:ss>  -StartDate <yyyy-mm-ddThh:mm:ss> -RecordType InformationBarrierPolicyApplication -ResultSize 1000 |?{$_.AuditData.Contains(<application guid>)} 
```

2. 감사 로그에서 자세한 출력에서 및 필드 값을 `"UserId"` 확인할 수 `"ErrorDetails"` 있습니다. 이렇게 하면 실패 이유가 발생합니다. 이 PowerShell 코드를 복사하고 변수를 수정할 수 있습니다.

```powershell
   $DetailedLogs[1] |fl
```

예:

> "UserId": User1
>
>"ErrorDetails":"Status: IBPolicyConflict. 오류: IB 세그먼트 "segment id1" 및 IB 세그먼트 "segment id2"에 충돌이 있으며 받는 사람에게 할당할 수 없습니다.

3. 일반적으로 사용자가 두 개 이상의 세그먼트에 포함되어 있는 것을 발견합니다. 에서 값을 업데이트하여 이 문제를 `-UserGroupFilter` 해결할 수 `OrganizationSegments` 있습니다.

4. 다음 절차를 사용하여 정보 장벽 정책을 다시 적용합니다. [정보 장벽 정책](information-barriers-policies.md#part-3-apply-information-barrier-policies).

## <a name="resources"></a>리소스

- [정보 장벽에 대한 정책을 Microsoft Teams](information-barriers-policies.md)
- [정보 장벽](information-barriers.md)