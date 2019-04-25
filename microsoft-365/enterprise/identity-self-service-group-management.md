---
title: '6단계: 그룹을 사용하여 더 쉽게 관리하십시오.'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 02/25/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Azure AD(Microsoft Azure Active Directory) 셀프 서비스 그룹 관리를 이해하고 구성하십시오.
ms.openlocfilehash: 9400e99ced45370600d1d5dcee4388ddef4250fe
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283529"
---
# <a name="step-6-use-groups-for-easier-management"></a><span data-ttu-id="76e66-103">6단계: 그룹을 사용하여 더 쉽게 관리하십시오.</span><span class="sxs-lookup"><span data-stu-id="76e66-103">Step 6: Use groups for easier management</span></span>

<a name="identity-self-service-groups"></a>
## <a name="allow-users-to-create-and-manage-their-own-groups"></a><span data-ttu-id="76e66-104">사용자가 자신의 그룹을 만들고 관리하도록 허용하십시오.</span><span class="sxs-lookup"><span data-stu-id="76e66-104">Allow users to create and manage their own groups</span></span>

<span data-ttu-id="76e66-105">*이 단계는 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="76e66-105">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="76e66-106">이 부문에서 IT 관리자를 대신하여 그룹 소유자가 관리할 수 있는 Azure 액티브 디렉토리(Azure AD-Microsoft Azure Active Directory) 그룹을 식별할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="76e66-106">In this section, you'll identify Azure Active Directory (Azure AD) groups that can be managed by group owners instead of IT administrators.</span></span> <span data-ttu-id="76e66-107">*셀프 서비스 그룹 관리*로 알려진 기능은 관리역할이 할당되지 않은 그룹 소유자가 보안 그룹을 생성하고 관리할 수 있도록 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="76e66-107">In this step, you'll identify Azure Active Directory (AD) groups that can be managed by group owners instead of IT administrators. Known as *self-service group management*, this feature allows group owners who are not assigned an administrative role to create and manage security groups.</span></span> 

<span data-ttu-id="76e66-p102">사용자는 보안 그룹에서 구성원을 요청할 수 있으며, 이 요청은 IT 관리자가 아니라 그룹 소유자에게 전달됩니다. 이를 통해 그룹의 비즈니스 사용을 이해하고 해당 구성원을 관리할 수 있는 팀, 프로젝트 또는 비즈니스 소유자에게 일상적인 그룹 구성원 제어를 위임할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76e66-p102">Users can request membership in a security group and that request goes to the group owner, rather than an IT administrator. This allows the day-to-day control of group membership to be delegated to team, project, or business owners who understand the business use for the group and can manage its membership.</span></span>

>[!Note]
><span data-ttu-id="76e66-110">셀프 서비스 그룹 관리는 Azure AD(Microsoft Azure Active Directory) 보안 및 Microsoft Office 365 그룹에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76e66-110">Optional: Self-service group management is enabled for specific Azure AD security and Office 365 groups</span></span> <span data-ttu-id="76e66-111">온 프레미스 액티브 디렉토리 도메인 서비스(AD DS-Active Directory Domain Services)에서 동기화된 메일이 사용가능한 그룹, 배포 목록 또는 다른 그룹에서 사용이 불가능합니다.</span><span class="sxs-lookup"><span data-stu-id="76e66-111">Self-service group management is available only for Azure AD security and Office 365 groups. It is not available for mail-enabled groups, distribution lists, or any group that has been synchronized from your on-premises Windows Server Active Directory (AD).</span></span>
>

<span data-ttu-id="76e66-112">자세한 내용은 [셀프 서비스 관리에 대한 Azure AD(Microsoft Azure Active Directory) 그룹 구성 지침](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="76e66-112">For more information, see the [instructions to configure an Azure AD group for self-service management](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span></span>

<span data-ttu-id="76e66-113">중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-self-service-groups)을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76e66-113">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-self-service-groups) for this step.</span></span>

<a name="identity-dyn-groups"></a>
## <a name="set-up-dynamic-group-membership"></a><span data-ttu-id="76e66-114">동적 그룹 구성원 설정</span><span class="sxs-lookup"><span data-stu-id="76e66-114">Set up dynamic group membership</span></span>

<span data-ttu-id="76e66-115">*이 단계는 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="76e66-115">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="76e66-116">이 부문에서 Azure AD(Microsoft Azure Active Directory) 그룹의 구성원으로서 사용자 계정을 자동으로 추가하거나 제거할 수 있는 일련의 규칙을 생성할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="76e66-116">In this step, you'll create a series of rules that automatically add or remove user accounts as members of an Azure AD group. This is known as dynamic group membership. The rules are based on user account attributes, such as Department or Country.</span></span> <span data-ttu-id="76e66-117">이를 *동적 그룹 구성원*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="76e66-117">This is known as *dynamic group membership*.</span></span> <span data-ttu-id="76e66-118">이 규칙은 부서나 국가와 같은 사용자 계정 속성을 기반으로 하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76e66-118">The rules are based on user account attributes, such as Department or Country.</span></span>

<span data-ttu-id="76e66-119">규칙이 적용되는 방식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="76e66-119">Here’s how the rules are applied:</span></span>

- <span data-ttu-id="76e66-120">새 사용자 계정이 그룹에 대한 모든 규칙과 일치하는 경우 구성원이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76e66-120">If a new user account matches all the rules for the group, it becomes a member.</span></span>
- <span data-ttu-id="76e66-121">사용자가 그룹의 구성원이 아니지만 해당 속성이 그룹에 대한 모든 규칙과 일치하도록 변경되는 경우 해당 그룹의 구성원이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76e66-121">If a user account isn’t a member of the group, but its attributes change so that it matches all the rules for the group, it becomes a member of that group.</span></span>
- <span data-ttu-id="76e66-122">사용자 계정이 그룹에 대한 일부 규칙과 일치하지 않는 경우 그룹에 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76e66-122">If a user account doesn’t match all the rules for the group, it isn’t added to the group.</span></span>
- <span data-ttu-id="76e66-123">사용자가 그룹의 구성원이지만 해당 속성이 그룹에 대한 모든 규칙과 더 이상 일치하지 않도록 변경되는 경우 그룹의 구성원에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="76e66-123">If a user account is a member of the group, but its attributes change so that it no longer matches all the rules for the group, it is removed as a member of the group.</span></span>

<span data-ttu-id="76e66-p105">동적 구성원을 사용하려면 먼저 공통적인 사용자 계정 속성 집합이 있는 그룹 집합 확인해야 합니다. 예를 들어 Sales 부서의 모든 구성원은 “Sales”로 설정된 Department 사용자 계정 특성에 따라 Sales Azure AD 그룹에 속해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76e66-p105">To use dynamic membership, you must first determine the sets of groups that have a common set of user account attributes. For example, all members of the Sales department should be in the Sales Azure AD group, based on the user account attribute Department set to “Sales”.</span></span>

<span data-ttu-id="76e66-126">[동적 Azure AD 그룹에 대한 규칙을 만들고 구성하는 지침](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="76e66-126">See the [instructions to create and configure the rules for a dynamic Azure AD group](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span></span>

<span data-ttu-id="76e66-127">이 부문의 결과:</span><span class="sxs-lookup"><span data-stu-id="76e66-127">The results of this step are:</span></span>

- <span data-ttu-id="76e66-128">동적 구성원에 대해 구성할 수 있는 Azure AD 그룹 집합</span><span class="sxs-lookup"><span data-stu-id="76e66-128">A set of Azure AD groups that can be configured for dynamic membership</span></span>
- <span data-ttu-id="76e66-129">각 동적 그룹에 대한 규칙 집합</span><span class="sxs-lookup"><span data-stu-id="76e66-129">A set of rules on each dynamic group</span></span>

|||
|:-------|:-----|
|![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="76e66-131">테스트 랩 가이드: 라이선스 및 그룹 등록 자동화</span><span class="sxs-lookup"><span data-stu-id="76e66-131">Test Lab Guide: Automate licenses and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="76e66-132">중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-dyn-groups)을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76e66-132">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-dyn-groups) for this step.</span></span>

<a name="identity-group-license"></a>
## <a name="set-up-automatic-licensing"></a><span data-ttu-id="76e66-133">자동 라이선싱 설정</span><span class="sxs-lookup"><span data-stu-id="76e66-133">Set up automatic licensing</span></span>

<span data-ttu-id="76e66-134">*이 단계는 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="76e66-134">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="76e66-135">이 부문에서 그룹의 모든 구성원에게 일습의 구독 라이센스를 자동으로 할당하기 위해 Azure AD(Microsoft Azure Active Directory)의 보안 그룹을 구성할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="76e66-135">In this section, you'll configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group.</span></span> <span data-ttu-id="76e66-136">이를 *그룹 기반 라이센싱*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="76e66-136">This is known as *group-based licensing*.</span></span> <span data-ttu-id="76e66-137">사용자 계정이 그룹에 추가되거나 제거된다면 그룹 구독 라이센스는 사용자 게정에서 자동으로 할당되거나 제거될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="76e66-137">In this step, you'll configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group. This is known as group-based licensing. If a user account is added to or removed from the group, the licenses for the group’s subscriptions will be automatically assigned or removed from the user account.</span></span>

<span data-ttu-id="76e66-138">Microsoft 365 Enterprise의 경우 다음 두 라이선스를 모두 할당하도록 Azure AD 보안 그룹을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="76e66-138">For Microsoft 365 Enterprise, you'll configure Azure AD security groups to assign both of these licenses:</span></span>

- <span data-ttu-id="76e66-139">Office 365 Enterprise E3 또는 E5</span><span class="sxs-lookup"><span data-stu-id="76e66-139">Office 365 Enterprise E3 or E5</span></span>
- <span data-ttu-id="76e66-140">EMS(Enterprise Mobility + Security) E3 또는 E5</span><span class="sxs-lookup"><span data-stu-id="76e66-140">Enterprise Mobility + Security (EMS) E3 or E5</span></span>

<span data-ttu-id="76e66-p107">2단계에서 식별한 그룹을 사용하여 해당 그룹의 모든 사용자에게 Office 365 및 EMS 라이선스가 있어야 하는 계정 목록이 포함된 그룹을 찾습니다. 모든 그룹 구성원을 위한 라이선스가 충분한지 확인합니다. 라이선스가 부족하면 라이선스를 사용할 수 있을 때까지 새 사용자에게 라이선스가 할당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76e66-p107">Using the groups you identified in Step 2, look for groups that contain a list of accounts where all users in that group must have both Office 365 and EMS licenses. Make sure you have enough licenses for all the group members. If you run out of licenses, new users won’t be assigned licenses until licenses become available.</span></span>

>[!Note]
><span data-ttu-id="76e66-144">Azure B2B 계정이 포함된 그룹에 대해 *그룹 기반 라이선싱*을 구성해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76e66-144">You should not configure *group-based licensing* for groups that contain Azure business to business (B2B) accounts.</span></span>
>

<span data-ttu-id="76e66-145">추가 정보는 [Azure Active Directory의 그룹 기반 라이선싱 기본 사항](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="76e66-145">See additional information on [Group-based licensing basics in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span></span>

<span data-ttu-id="76e66-146">[Azure 보안 그룹에 대해 그룹 기반 라이선싱을 구성하는 단계](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="76e66-146">See the [steps to configure group-based licensing for an Azure security group](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span></span>

<span data-ttu-id="76e66-147">이 부문의 결과:</span><span class="sxs-lookup"><span data-stu-id="76e66-147">The results of this step are:</span></span>

- <span data-ttu-id="76e66-148">그룹 기반 라이선싱에 적합한 보안 그룹을 식별했습니다.</span><span class="sxs-lookup"><span data-stu-id="76e66-148">You've identified which security groups are appropriate for group-based licensing.</span></span>
- <span data-ttu-id="76e66-149">그룹 기반 라이선싱에 대해 이러한 그룹을 구성했습니다.</span><span class="sxs-lookup"><span data-stu-id="76e66-149">You've configured these groups for group-based licensing.</span></span>

|||
|:-------|:-----|
|![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="76e66-151">테스트 랩 가이드: 라이선스 및 그룹 등록 자동화</span><span class="sxs-lookup"><span data-stu-id="76e66-151">Test Lab Guide: Automate licenses and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="76e66-152">중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-group-license)을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76e66-152">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-group-license) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="76e66-153">다음 단계</span><span class="sxs-lookup"><span data-stu-id="76e66-153">Next step</span></span>

[<span data-ttu-id="76e66-154">ID 인프라 종료 조건</span><span class="sxs-lookup"><span data-stu-id="76e66-154">Identity infrastructure exit criteria</span></span>](identity-exit-criteria.md)
