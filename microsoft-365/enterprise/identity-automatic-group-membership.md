---
title: '15단계: 동적 그룹 구성원 설정'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 계정 특성에 따른 자동 그룹 구성원을 이해하고 구성합니다.
ms.openlocfilehash: 8619179bc4e3ce17d9201cafb88e1b1c48fc7f4f
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870235"
---
# <a name="step-15-set-up-dynamic-group-membership"></a><span data-ttu-id="4dca6-103">15단계: 동적 그룹 구성원 설정</span><span class="sxs-lookup"><span data-stu-id="4dca6-103">Step 15: Set up dynamic group membership</span></span>

<span data-ttu-id="4dca6-104">*이 단계는 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="4dca6-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="4dca6-p101">이 단계에서는 사용자 계정을 Azure AD 그룹의 구성원으로 자동으로 추가하거나 제거하는 일련의 규칙을 만듭니다. 이를 *동적 그룹 구성원*이라고 합니다. 규칙은 부서 또는 국가와 같은 사용자 계정 속성을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dca6-p101">In Step 12, you'll create a series of rules that automatically add or remove user accounts as members of an Azure AD group. This is known as *dynamic group membership*. The rules are based on user account attributes, such as Department or Country.</span></span>

<span data-ttu-id="4dca6-108">규칙이 적용되는 방식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4dca6-108">Here’s how the rules are applied:</span></span>

- <span data-ttu-id="4dca6-109">새 사용자 계정이 그룹에 대한 모든 규칙과 일치하는 경우 구성원이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4dca6-109">If a new user account matches all the rules for the group, it becomes a member.</span></span>
- <span data-ttu-id="4dca6-110">사용자가 그룹의 구성원이 아니지만 해당 속성이 그룹에 대한 모든 규칙과 일치하도록 변경되는 경우 해당 그룹의 구성원이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4dca6-110">If a user account isn’t a member of the group, but its attributes change so that it matches all the rules for the group, it becomes a member of that group.</span></span>
- <span data-ttu-id="4dca6-111">사용자 계정이 그룹에 대한 일부 규칙과 일치하지 않는 경우 그룹에 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4dca6-111">If a user account doesn’t match all the rules for the group, it isn’t added to the group.</span></span>
- <span data-ttu-id="4dca6-112">사용자가 그룹의 구성원이지만 해당 속성이 그룹에 대한 모든 규칙과 더 이상 일치하지 않도록 변경되는 경우 그룹의 구성원에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="4dca6-112">If a user account is a member of the group, but its attributes change so that it no longer matches all the rules for the group, it is removed as a member of the group.</span></span>

<span data-ttu-id="4dca6-p102">동적 구성원을 사용하려면 먼저 공통적인 사용자 계정 속성 집합이 있는 그룹 집합 확인해야 합니다. 예를 들어 Sales 부서의 모든 구성원은 “Sales”로 설정된 Department 사용자 계정 특성에 따라 Sales Azure AD 그룹에 속해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dca6-p102">To use dynamic membership, you must first determine the sets of groups that have a common set of user account attributes. For example, all members of the Sales department should be in the Sales Azure AD group, based on the user account attribute Department set to “Sales”.</span></span>

<span data-ttu-id="4dca6-115">[동적 Azure AD 그룹에 대한 규칙을 만들고 구성하는 지침](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4dca6-115">See the [instructions to create and configure the rules for a dynamic Azure AD group](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span></span>

<span data-ttu-id="4dca6-116">이 단계의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4dca6-116">The results of this step are:</span></span>

- <span data-ttu-id="4dca6-117">동적 구성원에 대해 구성할 수 있는 Azure AD 그룹 집합</span><span class="sxs-lookup"><span data-stu-id="4dca6-117">A set of Azure AD groups that can be configured for dynamic membership</span></span>
- <span data-ttu-id="4dca6-118">각 동적 그룹에 대한 규칙 집합</span><span class="sxs-lookup"><span data-stu-id="4dca6-118">A set of rules on each dynamic group</span></span>

|||
|:-------|:-----|
|![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="4dca6-120">테스트 랩 가이드: 라이선스 및 그룹 등록 자동화</span><span class="sxs-lookup"><span data-stu-id="4dca6-120">Test Lab Guide: Automate licenses and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="4dca6-121">중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-dyn-groups)을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4dca6-121">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-dyn-groups) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="4dca6-122">다음 단계</span><span class="sxs-lookup"><span data-stu-id="4dca6-122">Next step</span></span>

[<span data-ttu-id="4dca6-123">ID 인프라 종료 조건</span><span class="sxs-lookup"><span data-stu-id="4dca6-123">Identity exit criteria</span></span>](identity-exit-criteria.md)
