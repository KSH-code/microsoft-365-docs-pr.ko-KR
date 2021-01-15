---
title: Microsoft 준수 관리자 시작
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-compliancemanager
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 준수 관리자 사용자 권한 및 역할을 설정하고 작업의 자동화된 테스트를 구성합니다. 사용자 기록을 관리하고 대시보드 보기를 필터링합니다.
ms.openlocfilehash: e130fc3438fc8b4674b752e25fc473ee0dd55ae4
ms.sourcegitcommit: df58fd8ebe14ca98fc1be84dbfb9c29ef7ab1d62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2021
ms.locfileid: "49870913"
---
# <a name="get-started-with-compliance-manager"></a><span data-ttu-id="cd347-104">규정 준수 관리자 시작</span><span class="sxs-lookup"><span data-stu-id="cd347-104">Get started with Compliance Manager</span></span>

<span data-ttu-id="cd347-105">**이 문서에서:** 이 문서는 준수 관리자를 설정하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-105">**In this article:** This article helps you set up Compliance Manager.</span></span> <span data-ttu-id="cd347-106">준수 **관리자에 액세스하고,** 역할 **및** 사용 권한을 설정하고, 개선 작업의 자동 테스트를 구성하는 **방법을 배워야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="cd347-106">Learn how to **access** Compliance Manager, **set roles and permissions**, and configure **automatic testing of improvement actions**.</span></span> <span data-ttu-id="cd347-107">준수 **관리자** 대시보드를 진행하고 개선 작업 페이지, 솔루션 페이지, 평가 페이지 및 평가 템플릿 페이지와 같은 기본 페이지를 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-107">Walk through **your Compliance Manager dashboard** and understand the main pages: the improvement actions page, the solutions page, the assessments page, and the assessment templates page.</span></span>

## <a name="who-can-access-compliance-manager"></a><span data-ttu-id="cd347-108">준수 관리자에 액세스할 수 있는 사용자</span><span class="sxs-lookup"><span data-stu-id="cd347-108">Who can access Compliance Manager</span></span>

<span data-ttu-id="cd347-109">준수 관리자는 Office 365 및 Microsoft 365 라이선스가 있는 조직과 미국 GCC(정부 커뮤니티 클라우드) 보통 및 GCC High 고객에게 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-109">Compliance Manager is available to organizations with Office 365 and Microsoft 365 licenses, and to US Government Community Cloud (GCC) Moderate and GCC High customers.</span></span> <span data-ttu-id="cd347-110">평가 가용성 및 관리 기능은 사용권 계약에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-110">Assessment availability and management capabilities depend on your licensing agreement.</span></span>  <span data-ttu-id="cd347-111">[서비스 설명 세부 정보 보기.](https://go.microsoft.com/fwlink/?linkid=2132371)</span><span class="sxs-lookup"><span data-stu-id="cd347-111">[View service description details](https://go.microsoft.com/fwlink/?linkid=2132371).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="cd347-112">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="cd347-112">Before you begin</span></span>

<span data-ttu-id="cd347-113">조직의 Microsoft 365 전역 관리자는 준수 관리자에 처음 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-113">The Microsoft 365 global administrator for your organization will likely be the first user to access Compliance Manager.</span></span> <span data-ttu-id="cd347-114">규정 준수 관리자를 처음 방문할 때 전역 관리자 로그인 및 사용자 권한을 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-114">We recommend the global admin sign in and set user permissions as outlined below when visiting Compliance Manager for the first time.</span></span>

## <a name="sign-in"></a><span data-ttu-id="cd347-115">로그인</span><span class="sxs-lookup"><span data-stu-id="cd347-115">Sign in</span></span>

1. <span data-ttu-id="cd347-116">[Microsoft 365](https://compliance.microsoft.com/) 규정 준수  센터로 이동하여 Microsoft 365 전역 관리자 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-116">Go to the [Microsoft 365 compliance center](https://compliance.microsoft.com/) and **sign in** with your Microsoft 365 global administrator account.</span></span>
2. <span data-ttu-id="cd347-117">왼쪽 **탐색 창에서** 준수 관리자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-117">Select **Compliance Manager** on the left navigation pane.</span></span> <span data-ttu-id="cd347-118">준수 관리자 [대시보드에 도착합니다.](#understand-the-compliance-manager-dashboard)</span><span class="sxs-lookup"><span data-stu-id="cd347-118">You'll arrive at your [Compliance Manager dashboard](#understand-the-compliance-manager-dashboard).</span></span>

<span data-ttu-id="cd347-119">준수 관리자에 액세스하기 위한 직접 링크는 [https://compliance.microsoft.com/compliancemanager](https://compliance.microsoft.com/compliancemanager) .</span><span class="sxs-lookup"><span data-stu-id="cd347-119">The direct link to access Compliance Manager is [https://compliance.microsoft.com/compliancemanager](https://compliance.microsoft.com/compliancemanager).</span></span>

## <a name="set-user-permissions-and-assign-roles"></a><span data-ttu-id="cd347-120">사용자 권한 설정 및 역할 할당</span><span class="sxs-lookup"><span data-stu-id="cd347-120">Set user permissions and assign roles</span></span>

<span data-ttu-id="cd347-121">준수 관리자는 RBAC(역할 기반 액세스 제어) 사용 권한 모델을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-121">Compliance Manager uses a role-based access control (RBAC) permission model.</span></span> <span data-ttu-id="cd347-122">역할이 할당된 사용자만 준수 관리자에 액세스할 수 있으며 각 사용자가 허용하는 작업은 역할 유형에 따라 [제한됩니다.](#role-types)</span><span class="sxs-lookup"><span data-stu-id="cd347-122">Only users who are assigned a role may access Compliance Manager, and the actions allowed by each user are restricted by [role type](#role-types).</span></span>

### <a name="where-to-set-permissions"></a><span data-ttu-id="cd347-123">사용 권한을 설정하는 위치</span><span class="sxs-lookup"><span data-stu-id="cd347-123">Where to set permissions</span></span>

<span data-ttu-id="cd347-124">조직에 대한 전역 관리자 역할을 보유하는 사용자는 COmpliance Manager에 대한 사용자 권한을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-124">The person holding the global admin role for your organization can set user permissions for COmpliance Manager.</span></span> <span data-ttu-id="cd347-125">사용 권한은 Office 365 보안 및 준수 & Azure AD(Azure Active Directory)에서 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-125">Permissions can be set in the Office 365 Security & Compliance center as well as in Azure Active Directory (Azure AD).</span></span>

> [!NOTE]
> <span data-ttu-id="cd347-126">GCC(미국 정부 커뮤니티) 높은 환경의 고객은 Azure AD에서 준수 관리자에 대한 사용자 권한 및 역할만 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-126">Customers in US Government Community (GCC) High environments can only set user permissions and roles for Compliance Manager in Azure AD.</span></span> <span data-ttu-id="cd347-127">Azure AD 지침 및 역할 유형 정의는 아래를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cd347-127">See below for Azure AD instructions and role type definitions.</span></span>

<span data-ttu-id="cd347-128">Office 365 보안 및 준수 센터에서 사용 권한을 설정하고 역할을 할당하려면 & 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="cd347-128">To set permissions and assign roles in the Office 365 Security & Compliance center, follow the steps below:</span></span>

1. <span data-ttu-id="cd347-129">[Office 365](https://protection.office.com/) 보안 및 준수 & **이동하고** 왼쪽 탐색에서 사용 권한을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-129">Go to the [Office 365 Security & Compliance Center](https://protection.office.com/) and select **Permissions** on the left navigation.</span></span>

2. <span data-ttu-id="cd347-130">하나 이상의 사용자를 추가할 역할 그룹을 찾고 그룹 이름 왼쪽에 있는 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-130">Find the role group to which you want to add one or more users, and check the box to the left of the group name.</span></span> <span data-ttu-id="cd347-131">(아래의 역할 및 [관련 함수 목록을 참조하세요.](#role-types)</span><span class="sxs-lookup"><span data-stu-id="cd347-131">(See the [list of roles and related functions below](#role-types).</span></span> <span data-ttu-id="cd347-132">역할 그룹 이름은 역할 이름과 모방됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-132">The role group names mimic the role name.)</span></span>

3. <span data-ttu-id="cd347-133">해당 그룹의 플라이아웃 창에서  구성원 헤더에서 **편집을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-133">On the flyout pane for that group, select **Edit** under the **Members** header.</span></span>

4. <span data-ttu-id="cd347-134">구성원 **선택**.</span><span class="sxs-lookup"><span data-stu-id="cd347-134">Select **Choose members**.</span></span> <span data-ttu-id="cd347-135">다른 플라이아웃 창이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-135">Another flyout window will appear.</span></span>

5. <span data-ttu-id="cd347-136">**+추가를 선택하여** 그룹에 추가할 사용자를 하나 이상 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-136">Select **+ Add** to choose one or more users to add to the group.</span></span>

6. <span data-ttu-id="cd347-137">추가할 이름 옆의 확인란을 선택한 다음 아래쪽에 있는 추가 단추를 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="cd347-137">Select the checkbox next to the names you want to add, then select the **Add** button at the bottom.</span></span>

7. <span data-ttu-id="cd347-138">사용자 할당을 완료한 후 완료를 선택한 다음 **저장을** 선택한 다음 **닫습니다.**</span><span class="sxs-lookup"><span data-stu-id="cd347-138">When you’re done assigning users, select **Done**, then select **Save**, then **Close**.</span></span>

##### <a name="more-about-the-office-365-security--compliance-center"></a><span data-ttu-id="cd347-139">Office 365 보안 및 준수 & 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="cd347-139">More about the Office 365 Security & Compliance Center</span></span>

<span data-ttu-id="cd347-140">Office 365 보안 및 준수 센터의 사용 [권한에 & 자세히 알아보습니다.](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)</span><span class="sxs-lookup"><span data-stu-id="cd347-140">Learn more about [permissions in the Office 365 Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>

<span data-ttu-id="cd347-141">Office 365 보안 및 준수 센터에 액세스할 수 없는 경우 또는 Microsoft Service Trust Portal에서 준수 관리자의 클래식 버전에 액세스해야 하는 경우 Service Trust Portal의 관리 설정은 역할을 할당하는 다른 방법을 제공합니다(지침[보기).](meet-data-protection-and-regulatory-reqs-using-microsoft-cloud.md#assigning-compliance-manager-roles-to-users)</span><span class="sxs-lookup"><span data-stu-id="cd347-141">If you don't have access to the Office 365 Security and Compliance Center, or if you need to access the classic version of Compliance Manager in the Microsoft Service Trust Portal,  the Admin settings in the Service Trust Portal provides another way to assign roles ([view instructions](meet-data-protection-and-regulatory-reqs-using-microsoft-cloud.md#assigning-compliance-manager-roles-to-users)).</span></span> <span data-ttu-id="cd347-142">이러한 역할은 기능이 더 제한적입니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-142">Be aware that such roles are more limited in their functionality.</span></span>

##### <a name="more-about-azure-ad"></a><span data-ttu-id="cd347-143">Azure AD에 대한 자세한 내용은</span><span class="sxs-lookup"><span data-stu-id="cd347-143">More about Azure AD</span></span>

<span data-ttu-id="cd347-144">Azure AD에서 역할을 할당하고 사용 권한을 설정하려면 Azure Active Directory를 사용하여 사용자에게 관리자 및 비 관리자 역할 [할당을 참조하세요.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="cd347-144">To assign roles and set permissions in Azure AD, see [Assign administrator and non-administrator roles to users with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).</span></span>

<span data-ttu-id="cd347-145">Office 365 또는 Microsoft 365 구독이 없는 Azure AD ID가 있는 사용자는 Microsoft 365 규정 준수 센터에서 준수 관리자에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-145">Users with Azure AD identities who don't have Office 365 or Microsoft 365 subscriptions won't be able to access Compliance Manager in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="cd347-146">준수 관리자에 액세스하는 데 도움이 필요하면 에지 관리자에게 [cmresearch@microsoft.com.](mailto:cmresearch@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="cd347-146">To seek assistance in accessing Compliance Manager, contact [cmresearch@microsoft.com](mailto:cmresearch@microsoft.com).</span></span>

### <a name="role-types"></a><span data-ttu-id="cd347-147">역할 유형</span><span class="sxs-lookup"><span data-stu-id="cd347-147">Role types</span></span>

<span data-ttu-id="cd347-148">아래 표에는 준수 관리자의 각 역할에서 허용되는 기능이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-148">The table below shows the functions allowed by each role in Compliance Manager.</span></span> <span data-ttu-id="cd347-149">또한 이 표에는 각 [Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) 역할이 준수 관리자 역할에 매핑된 방식도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-149">The table also shows how each [Azure AD role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) maps to Compliance Manager roles.</span></span> <span data-ttu-id="cd347-150">준수 관리자에 액세스하려면 사용자에게 적어도 준수 관리자 읽기 관리자 역할 또는 Azure AD 전역 읽기 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-150">Users will need at least the Compliance Manager reader role, or Azure AD global reader role, to access Compliance Manager.</span></span>


| <span data-ttu-id="cd347-151">사용자는 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-151">User can:</span></span> | <span data-ttu-id="cd347-152">준수 관리자 역할</span><span class="sxs-lookup"><span data-stu-id="cd347-152">Compliance Manager role</span></span> | <span data-ttu-id="cd347-153">Azure AD 역할</span><span class="sxs-lookup"><span data-stu-id="cd347-153">Azure AD role</span></span> | 
| :------------- | :-------------: | :------------: |
| <span data-ttu-id="cd347-154">**데이터를 읽지만 편집하지는 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="cd347-154">**Read but not edit data**</span></span>| <span data-ttu-id="cd347-155">준수 관리자의 독자</span><span class="sxs-lookup"><span data-stu-id="cd347-155">Compliance Manager Reader</span></span>  | <span data-ttu-id="cd347-156">Azure AD Global Reader, 보안 읽기</span><span class="sxs-lookup"><span data-stu-id="cd347-156">Azure AD Global reader, Security reader</span></span> | 
| <span data-ttu-id="cd347-157">**데이터 편집**</span><span class="sxs-lookup"><span data-stu-id="cd347-157">**Edit data**</span></span>| <span data-ttu-id="cd347-158">준수 관리자 기여</span><span class="sxs-lookup"><span data-stu-id="cd347-158">Compliance Manager Contribution</span></span> | <span data-ttu-id="cd347-159">준수 관리자</span><span class="sxs-lookup"><span data-stu-id="cd347-159">Compliance Administrator</span></span> | 
| <span data-ttu-id="cd347-160">**테스트 결과 편집**</span><span class="sxs-lookup"><span data-stu-id="cd347-160">**Edit test results**</span></span>| <span data-ttu-id="cd347-161">준수 관리자 평가</span><span class="sxs-lookup"><span data-stu-id="cd347-161">Compliance Manager Assessment</span></span> | <span data-ttu-id="cd347-162">준수 관리자</span><span class="sxs-lookup"><span data-stu-id="cd347-162">Compliance Administrator</span></span> | 
| <span data-ttu-id="cd347-163">**평가 및 서식 파일 및 테넌트 데이터 관리**</span><span class="sxs-lookup"><span data-stu-id="cd347-163">**Manage assessments, and template and tenant data**</span></span>| <span data-ttu-id="cd347-164">준수 관리자 관리</span><span class="sxs-lookup"><span data-stu-id="cd347-164">Compliance Manager Administration</span></span> | <span data-ttu-id="cd347-165">준수 관리자, 준수 데이터 관리자, 보안 관리자</span><span class="sxs-lookup"><span data-stu-id="cd347-165">Compliance Administrator, Compliance Data Administrator, Security Administrator</span></span>  | 
| <span data-ttu-id="cd347-166">**사용자 할당**</span><span class="sxs-lookup"><span data-stu-id="cd347-166">**Assign users**</span></span>| <span data-ttu-id="cd347-167">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="cd347-167">Global Administrator</span></span> | <span data-ttu-id="cd347-168">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="cd347-168">Global Administrator</span></span> | 

## <a name="settings-for-automated-testing-and-user-history"></a><span data-ttu-id="cd347-169">자동화된 테스트 및 사용자 기록 설정</span><span class="sxs-lookup"><span data-stu-id="cd347-169">Settings for automated testing and user history</span></span>

<span data-ttu-id="cd347-170">Microsoft 365 규정 준수 센터의 준수 관리자 설정을 사용하여 개선 작업의 자동 테스트를 활성화 및 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-170">The Compliance Manager settings in the Microsoft 365 compliance center allow you to enable and disable automatic testing of improvement actions.</span></span> <span data-ttu-id="cd347-171">또한 이 설정을 사용하면 개선 작업과 관련된 사용자 데이터를 관리할 수 있습니다.(개선 작업을 다른 사용자에게 다시 재배치하는 기능 포함).</span><span class="sxs-lookup"><span data-stu-id="cd347-171">The settings also allow you to manage the data of users associated to improvement actions, including the ability to reassign improvement actions to a different user.</span></span>  <span data-ttu-id="cd347-172">전역 관리자 또는 준수 관리자 관리자 역할이 있는 사용자만 준수 관리자 설정에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-172">Only people with a global administrator or Compliance Manager Administrator role can access the Compliance Manager settings.</span></span>

> [!NOTE]
> <span data-ttu-id="cd347-173">이러한 환경에서는 보안 점수가 제공되지 않는 GCC High 환경에서는 자동화된 테스트 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-173">The automated testing feature is not available to customers in GCC High environments because Secure Score isn't available in these environments.</span></span> <span data-ttu-id="cd347-174">GCC High 고객은 개선 작업을 수동으로 구현하고 테스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-174">GCC High customers will need to manually implement and test their improvement actions.</span></span>

### <a name="set-up-automated-testing"></a><span data-ttu-id="cd347-175">자동화된 테스트 설정</span><span class="sxs-lookup"><span data-stu-id="cd347-175">Set up automated testing</span></span>

<span data-ttu-id="cd347-176">준수 관리자의 일부 개선 작업도 Microsoft 보안 점수에 의해 [모니터링됩니다.](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)</span><span class="sxs-lookup"><span data-stu-id="cd347-176">Some improvement actions in Compliance Manager are also monitored by [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).</span></span> <span data-ttu-id="cd347-177">공동으로 모니터링되는 작업의 자동화된 테스트를 설정할 수 있습니다. 즉, 보안 점수에서 작업을 테스트하고 업데이트하면 해당 결과가 준수 관리자의 동일한 작업과 동기화되고 준수 점수에 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-177">You can set up automated testing of actions that are jointly monitored, which means that when an action is tested and updated in Secure Score, those results synch with the same actions in Compliance Manager and count toward your compliance score.</span></span>

<span data-ttu-id="cd347-178">자동 테스트는 준수 관리자를 새로 추가한 조직에 대해 기본적으로 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-178">Automatic testing is turned on by default for organizations new to Compliance Manager.</span></span> <span data-ttu-id="cd347-179">Microsoft 365 또는 Office 365를 처음 배포할 때 보안 점수가 데이터를 완전히 수집하고 준수 점수에 팩터하는 데 약 7일이 소요됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-179">When you first deploy Microsoft 365 or Office 365, it takes approximately seven days for Secure Score to fully collect data and factor it into your compliance score.</span></span>  <span data-ttu-id="cd347-180">자동화된 테스트가 켜져 있는 경우 작업의 테스트 날짜는 업데이트되지 않지만 테스트 상태가 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-180">When automated testing is turned on, the action’s test date won’t be updated, but its test status will update.</span></span> <span data-ttu-id="cd347-181">새 평가를 만들면 Microsoft 제어 점수와 보안 점수 통합이 자동으로 점수에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-181">When new assessments are created, scores automatically include Microsoft control scores and Secure Score integration.</span></span>

<span data-ttu-id="cd347-182">조직의 전역 관리자는 자동화된 테스트에 대한 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-182">The global administrator for your organization can change the settings for automated testing at any time.</span></span> <span data-ttu-id="cd347-183">일반적인 개선 작업에 대한 자동화된 테스트를 해제하거나 개별 작업에 대해 끄면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-183">You can turn off automated testing for common improvement actions, or turn it on for individual actions.</span></span> <span data-ttu-id="cd347-184">아래의 지침에 따라 자동화된 테스트 설정을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-184">Follow the instructions below to change your automated testing settings.</span></span>

#### <a name="to-manage-your-automated-testing-settings"></a><span data-ttu-id="cd347-185">자동화된 테스트 설정을 관리하려면</span><span class="sxs-lookup"><span data-stu-id="cd347-185">To manage your automated testing settings:</span></span>

1. <span data-ttu-id="cd347-186">Microsoft  [365](https://compliance.microsoft.com/)규정 준수 센터의 어디에서나 왼쪽 탐색에서 설정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-186">Select **Settings** on the left navigation from anywhere in the [Microsoft 365 compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="cd347-187">설정 페이지에서 준수 **관리자를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="cd347-187">On the settings page, select **Compliance Manager**.</span></span>

3. <span data-ttu-id="cd347-188">왼쪽 **탐색에서** 자동화된 테스트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-188">Select **Automated testing** from the left navigation.</span></span>

4. <span data-ttu-id="cd347-189">적용 가능한 단추를 선택하여 모든 개선 작업에 대해 자동 테스트를 켜거나, 모든 작업에 대해 끄거나, 개별 작업으로 끄십시오.</span><span class="sxs-lookup"><span data-stu-id="cd347-189">Select the applicable button to turn on automatic testing for all improvement actions, turn it off for all actions, or turn on by individual action.</span></span>

5. <span data-ttu-id="cd347-190">개선 **작업당** 켜기 기능을 선택하면 선택할 수 있는 모든 개선 작업이 목록에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-190">If you select **Turn on per improvement action**, a list will show all the available improvement actions to choose from.</span></span>  <span data-ttu-id="cd347-191">자동으로 테스트할 작업 옆의 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-191">Check the box next to any action you want automatically tested.</span></span>

6. <span data-ttu-id="cd347-192">**저장을** 선택하여 설정을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-192">Select **Save** to save your settings.</span></span> <span data-ttu-id="cd347-193">선택이 저장된 화면 맨 위에 확인 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-193">You’ll receive a confirmation message at the top of your screen that your selection was saved.</span></span> <span data-ttu-id="cd347-194">실패 알림이 수신된 경우 다시 시도하세요.</span><span class="sxs-lookup"><span data-stu-id="cd347-194">If you receive a failure notice, try again.</span></span>

<span data-ttu-id="cd347-195">**참고:** 전역 관리자만 모든 작업에 대한 자동 업데이트를 설정하거나 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-195">**Note:** Only the global administrator can turn on or off automatic updates for all actions.</span></span> <span data-ttu-id="cd347-196">준수 관리자 관리자는 개별 작업에 대해 자동 업데이트를 켜지만 전역적으로 모든 작업에 대한 업데이트를 하도록 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-196">The Compliance Manager Administrator can turn on automatic updates for individual actions, but not for all actions globally.</span></span>

### <a name="manage-user-history"></a><span data-ttu-id="cd347-197">사용자 기록 관리</span><span class="sxs-lookup"><span data-stu-id="cd347-197">Manage user history</span></span>

<span data-ttu-id="cd347-198">사용자 **기록 관리 설정을** 사용하면 준수 관리자에서 개선 작업을 수행한 사용자를 빠르게 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-198">The **Manage user history** settings help you quickly identify which users have worked with improvement actions in Compliance Manager.</span></span> <span data-ttu-id="cd347-199">개선 작업과 관련된 식별 가능한 사용자 데이터에는 수행된 구현 및 테스트 작업, 업로드한 문서 및 사용자가 입력한 메모가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-199">The identifiable user data associated with improvement actions includes any implementation and testing work done, documents they uploaded, and any notes they entered.</span></span> <span data-ttu-id="cd347-200">조직의 자체 규정 준수 요구에 대해 이러한 유형의 데이터를 이해하고 검색해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-200">Understanding and retrieving this type of data may be necessary for your organization’s own compliance needs.</span></span>

<span data-ttu-id="cd347-201">또한 사용자 기록 설정을 통해 한 사용자에서 다른 사용자로 모든 개선 작업을 다시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-201">The user history settings also allow you to reassign all improvement actions from one user to another.</span></span>

<span data-ttu-id="cd347-202">**사용자 기록 설정을 찾으면 다음을 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="cd347-202">**To find the user history settings:**</span></span>

1. <span data-ttu-id="cd347-203">[Microsoft 365](https://compliance.microsoft.com/)규정 준수 센터의 어디에서나 왼쪽 탐색에서 설정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-203">Select Settings on the left navigation from anywhere in the [Microsoft 365 compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="cd347-204">설정 페이지에서 준수 **관리자를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="cd347-204">On the settings page, select **Compliance Manager**.</span></span>

3. <span data-ttu-id="cd347-205">왼쪽 **탐색에서 사용자** 기록 관리를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-205">Select **Manage user history** from the left navigation.</span></span>

<span data-ttu-id="cd347-206">사용자 **기록 관리 페이지에는** 개선 작업이 할당된 전자 메일 주소로 된 모든 사용자 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-206">The **manage user history** page shows a list of all users by email address who are assigned to an improvement action.</span></span> <span data-ttu-id="cd347-207">검색 **단추를** 사용하여 전자 메일 주소를 입력하여 특정 사용자를 빠르게 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-207">Use the **Search** button to quickly find a specific user by typing in their email address.</span></span>

<span data-ttu-id="cd347-208">각 사용자의 전자 메일 주소 오른쪽에  있는 드롭다운 선택 메뉴에서는 보고서를 내보내거나 개선 작업을 다시 재배치하거나 기록을 삭제하는 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-208">To the right of each user’s email address, the **Select** drop-down menu provides options to  export a report, reassign improvement actions, or delete history.</span></span> <span data-ttu-id="cd347-209">각 옵션에 대한 자세한 내용은 아래 각 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cd347-209">See each section below for details about each option.</span></span>

#### <a name="export-a-report-of-user-history-data"></a><span data-ttu-id="cd347-210">사용자 기록 데이터 보고서 내보내기</span><span class="sxs-lookup"><span data-stu-id="cd347-210">Export a report of user history data</span></span>

<span data-ttu-id="cd347-211">사용자에게 현재 할당된 개선 작업 목록이 포함된 Excel 파일을 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-211">You can export an Excel file containing a list of improvement actions currently assigned to a user.</span></span>  <span data-ttu-id="cd347-212">이 보고서에는 해당 사용자가 업로드한 증거 파일도 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-212">The report also lists any evidence files uploaded by that user.</span></span> <span data-ttu-id="cd347-213">이 정보는 열기 개선 작업을 다시할 때 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-213">This information can help you reassign open improvement actions.</span></span>

<span data-ttu-id="cd347-214">보고서에는 작성 날짜의 개선 작업 상태가 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-214">The report reflects the improvement action’s status as of its creation date.</span></span> <span data-ttu-id="cd347-215">해당 상태 또는 배정에 대한 모든 이전 변경 내용에 대한 기록 보고서는 아니며 개선 작업 페이지에서 보고서를 내보내는 방법에 [대해 자세히 알아보십시오.](compliance-manager-improvement-actions.md#export-a-report)</span><span class="sxs-lookup"><span data-stu-id="cd347-215">It’s not a historical report of all previous changes to its status or assignment (learn how to [export a report from your improvement actions page](compliance-manager-improvement-actions.md#export-a-report)).</span></span>

<span data-ttu-id="cd347-216">**아래 단계에 따라 사용자에 따라 보고서를 내보낼 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="cd347-216">**Follow the steps below to export a report by user:**</span></span>

1. <span data-ttu-id="cd347-217">Microsoft  [365](https://compliance.microsoft.com/)규정 준수 센터의 어디에서나 왼쪽 탐색에서 설정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-217">Select **Settings** on the left navigation from anywhere in the [Microsoft 365 compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="cd347-218">설정 페이지에서 준수 **관리자를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="cd347-218">On the settings page, select **Compliance Manager**.</span></span>

3. <span data-ttu-id="cd347-219">왼쪽 **탐색에서** 사용자 기록 관리를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-219">Select **Manage user history** from the navigation at left.</span></span>

4. <span data-ttu-id="cd347-220">목록 전자 메일 주소를 검색하거나 검색을 선택하고  사용자의 전자 메일 주소를 입력하여 원하는 사용자를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-220">Find your intended user by searching the list email addresses, or by selecting **Search** and entering the user’s email address.</span></span>

5. <span data-ttu-id="cd347-221">Select **drop-down** menu, choose **Export report**.</span><span class="sxs-lookup"><span data-stu-id="cd347-221">From the **Select** drop-down menu, choose **Export report**.</span></span>

6. <span data-ttu-id="cd347-222">보고서의 Excel 파일이 생성되는 경우 해당 파일을 열고 로컬 컴퓨터로 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-222">Once the Excel file of your report is generated, you can open it and save it to your local machine.</span></span>

#### <a name="reassign-improvement-actions-to-another-user"></a><span data-ttu-id="cd347-223">다른 사용자에게 개선 작업 재할당</span><span class="sxs-lookup"><span data-stu-id="cd347-223">Reassign improvement actions to another user</span></span>

<span data-ttu-id="cd347-224">개선 작업을 한 사용자에서 다른 사용자로 다시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-224">You can reassign improvement actions from one user to another.</span></span> <span data-ttu-id="cd347-225">작업을 다시 지정해도 문서 업로드 기록은 변경되지 않지만 원래 문서를 업로드한 사용자의 이름이 개선 작업 내에 더 이상 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-225">When you reassign an action, the document upload history doesn't change, but the name of the user who originally uploaded the documentation no longer appears within the improvement action.</span></span>

<span data-ttu-id="cd347-226">**아래 단계에 따라 개선 작업을 다른 사용자에게 다시 재배치합니다.**</span><span class="sxs-lookup"><span data-stu-id="cd347-226">**Follow the steps below to reassign improvement actions to another user:**</span></span>

1. <span data-ttu-id="cd347-227">Microsoft  [365](https://compliance.microsoft.com/)규정 준수 센터의 어디에서나 왼쪽 탐색에서 설정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-227">Select **Settings** on the left navigation from anywhere in the [Microsoft 365 compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="cd347-228">설정 페이지에서 준수 **관리자를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="cd347-228">On the settings page, select **Compliance Manager**.</span></span>

3. <span data-ttu-id="cd347-229">왼쪽 **탐색에서** 사용자 기록 관리를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-229">Select **Manage user history** from the navigation at left.</span></span>

4. <span data-ttu-id="cd347-230">목록 전자 메일 주소를 검색하거나 검색을 선택하고  해당 사용자의 전자 메일 주소를 입력하여 사용자를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-230">Find a user by searching the list email addresses, or by selecting **Search** and entering that user’s email address.</span></span>

5. <span data-ttu-id="cd347-231">드롭다운  선택 메뉴에서 개선 작업 다시 재할당을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="cd347-231">From the **Select** drop-down menu, choose **Reassign improvement actions**.</span></span> <span data-ttu-id="cd347-232">**재할당 개선** 작업 플라이아웃 창이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-232">The **Reassign improvement actions** flyout pane will appear.</span></span>

6. <span data-ttu-id="cd347-233">사용자 **검색 필드에** 개선 작업을 할당할 사용자의 이름 또는 전자 메일 주소를 *입력합니다.*</span><span class="sxs-lookup"><span data-stu-id="cd347-233">In the **Search users** field, enter the name or email address of the user you want assign the improvement actions *to*.</span></span>

7. <span data-ttu-id="cd347-234">개선 작업에서 의도한 사용자의 이름이 할당되는 경우 사용자를 선택한 다음 작업 **할당을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="cd347-234">When you see the name of your intended user under **Improvement actions will be assigned to**, select the user, then select **Assign actions**.</span></span>

8. <span data-ttu-id="cd347-235">재할당이 완료되면 플라이아웃 창에 이전 사용자의 모든 개선 작업이 새 사용자에게 다시 재할당된 것임이 확인 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-235">When the reassignment is complete, you’ll see a confirmation message in the flyout pane confirming that all improvement actions from the previous user have been reassigned to the new user.</span></span> <span data-ttu-id="cd347-236">재할당 실패 알림을 받으면 창을 닫고 다시 시도하십시오.</span><span class="sxs-lookup"><span data-stu-id="cd347-236">If you receive a reassignment failure notice, close the window and try again.</span></span> <span data-ttu-id="cd347-237">플라이아웃 창을 닫고 완료를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="cd347-237">To close the flyout pane, select **Done**.</span></span>

<span data-ttu-id="cd347-238">새 담당자는 개선 작업에 할당된 전자 메일을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-238">The new assignee receives an email that they've been assigned to an improvement action.</span></span> <span data-ttu-id="cd347-239">전자 메일에는 개선 작업의 세부 정보 페이지에 대한 직접 링크가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-239">The email contains a direct link into the improvement action's details page.</span></span>
 
 > [!NOTE]
> <span data-ttu-id="cd347-240">보류 중인 업데이트가 있는 작업을 다시 재배치하는 경우 재할당 후 업데이트가 수락되면 재할당 전자 메일의 작업으로 직접 연결되는 링크가 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-240">If you reassign an action that has a pending update, the direct link to the action in the reassignment email will break if the update is accepted after reassignment.</span></span> <span data-ttu-id="cd347-241">업데이트가 수락된 후 사용자에게 작업을 다시 할당하여 이 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-241">You can fix this by re-assigning the action to the user after the update is accepted.</span></span> <span data-ttu-id="cd347-242">개선 [작업의 업데이트에 대해 자세히 알아보습니다.](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions)</span><span class="sxs-lookup"><span data-stu-id="cd347-242">Learn more about [updates to improvement actions](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions).</span></span>

#### <a name="delete-user-history"></a><span data-ttu-id="cd347-243">사용자 기록 삭제</span><span class="sxs-lookup"><span data-stu-id="cd347-243">Delete user history</span></span>

<span data-ttu-id="cd347-244">사용자 기록을 삭제하면 사용자 기록을 개선 작업의 소유자로 제거하고 준수 관리자의 다른 모든 필드에서 해당 이름을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-244">Deleting a user’s history will remove them as an owner of improvement actions, and will remove their name from all other fields in Compliance Manager.</span></span> <span data-ttu-id="cd347-245">사용자 기록을 삭제하면 새 사용자가 할당될 때까지 소유한  개선 작업이 할당된 값으로 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-245">When you delete a user’s history, the improvement actions they owned will not display an **Assigned to** value until a new user is assigned.</span></span> <span data-ttu-id="cd347-246">개선 작업으로 업로드된 모든 문서에는 삭제된 사용자의 이름 대신 사용자가 제거된 것으로 표시됩니다. </span><span class="sxs-lookup"><span data-stu-id="cd347-246">Any documents uploaded to the improvement action will show **User removed** in place of the deleted user’s name.</span></span> <span data-ttu-id="cd347-247">사용자 기록 삭제는 영구적입니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-247">Deleting user history is permanent.</span></span>

<span data-ttu-id="cd347-248">사용자 기록을 삭제하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="cd347-248">To delete a user’s history, follow the steps below:</span></span>

1. <span data-ttu-id="cd347-249">Microsoft  [365](https://compliance.microsoft.com/)규정 준수 센터의 어디에서나 왼쪽 탐색에서 설정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-249">Select **Settings** on the left navigation from anywhere in the [Microsoft 365 compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="cd347-250">설정 페이지에서 준수 **관리자를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="cd347-250">On the settings page, select **Compliance Manager**.</span></span>

3. <span data-ttu-id="cd347-251">왼쪽 **탐색에서** 사용자 기록 관리를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-251">Select **Manage user history** from the navigation at left.</span></span>

4. <span data-ttu-id="cd347-252">목록 전자 메일 주소를 검색하거나 검색을 선택하고  해당 사용자의 전자 메일 주소를 입력하여 사용자를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-252">Find a user by searching the list email addresses, or by selecting **Search** and entering that user’s email address.</span></span>

5. <span data-ttu-id="cd347-253">드롭다운  선택 메뉴에서 기록 **삭제를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="cd347-253">From the **Select** drop-down menu, choose **Delete history**.</span></span>

6. <span data-ttu-id="cd347-254">사용자 기록의 영구 삭제를 확인하는 창이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-254">A window appears asking you to confirm the permanent deletion of the user’s history.</span></span> <span data-ttu-id="cd347-255">삭제를 계속하려면 기록 **삭제를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="cd347-255">To continue with deletion, select **Delete history**.</span></span> <span data-ttu-id="cd347-256">기록을 삭제하지 않고 그대로 두시하려면 취소를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="cd347-256">To leave without deleting the history, select **Cancel**.</span></span>

7. <span data-ttu-id="cd347-257">사용자 기록 관리 페이지에  사용자의 기록이 삭제된 확인 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-257">You’ll arrive back at the **Manage user history** page with a confirmation message at the top that the history for the user was deleted.</span></span>

## <a name="understand-the-compliance-manager-dashboard"></a><span data-ttu-id="cd347-258">준수 관리자 대시보드 이해</span><span class="sxs-lookup"><span data-stu-id="cd347-258">Understand the Compliance Manager dashboard</span></span>

<span data-ttu-id="cd347-259">준수 관리자 대시보드는 현재 규정 준수 입장을 한눈에 볼 수 있도록 고안된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-259">The Compliance Manager dashboard is designed to provide you an at-a-glance view of your current compliance posture.</span></span>

<span data-ttu-id="cd347-260">![준수 관리자 - 대시보드](../media/compliance-manager-dashboard.png "준수 관리자 대시보드")</span><span class="sxs-lookup"><span data-stu-id="cd347-260">![Compliance Manager - dashboard](../media/compliance-manager-dashboard.png "Compliance Manager dashboard")</span></span>

### <a name="overall-compliance-score"></a><span data-ttu-id="cd347-261">전반적인 준수 점수</span><span class="sxs-lookup"><span data-stu-id="cd347-261">Overall compliance score</span></span>

<span data-ttu-id="cd347-262">준수 점수가 맨 위에 두드러게 추천됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-262">Your compliance score is featured prominently at the top.</span></span> <span data-ttu-id="cd347-263">이 백분율은 주요 데이터 보호 표준 및 규정을 충족하는 개선 작업을 완료하기 위해 달성 가능한 포인트를 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-263">It shows a percentage based on points achievable for completing improvement actions that address key data protection standards and regulations.</span></span> <span data-ttu-id="cd347-264">Microsoft에서 [관리되는 Microsoft](compliance-manager-assessments.md#microsoft-actions-tab)작업의 점수도 준수 점수에 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-264">Points from [Microsoft actions](compliance-manager-assessments.md#microsoft-actions-tab), which are managed my Microsoft, also count toward your compliance score.</span></span>

<span data-ttu-id="cd347-265">처음으로 준수 관리자에 오면 초기 점수는 [Microsoft 365](compliance-manager-assessments.md#data-protection-baseline-default-assessment)데이터 보호 기준을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-265">When you come to Compliance Manager for the first time, your initial score is based on the [Microsoft 365 data protection baseline](compliance-manager-assessments.md#data-protection-baseline-default-assessment).</span></span> <span data-ttu-id="cd347-266">모든 조직에서 사용할 수 있는 이 기준 평가는 일반적인 산업 규정 및 표준을 포함하는 제어 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-266">This baseline assessment, which is available to all organizations, is a set of controls that includes common industry regulations and standards.</span></span> <span data-ttu-id="cd347-267">준수 관리자는 기존 Microsoft 365 솔루션을 검사하고 현재 개인 정보 및 보안 설정에 따라 초기 평가를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-267">Compliance Manager scans your existing Microsoft 365 solutions and gives you an initial assessment based on your current privacy and security settings.</span></span> <span data-ttu-id="cd347-268">조직과 관련된 평가를 추가하면 점수가 더 의미가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-268">As you add assessments that are relevant to your organization, your score becomes more meaningful for you.</span></span>

<span data-ttu-id="cd347-269">**자세한 내용은 다음을** 통해 준수 [점수를 계산하는 방법을 이해합니다.](compliance-score-calculation.md)</span><span class="sxs-lookup"><span data-stu-id="cd347-269">**Learn more:** [Understand how your compliance score is calculated](compliance-score-calculation.md).</span></span>

### <a name="key-improvement-actions"></a><span data-ttu-id="cd347-270">주요 개선 작업</span><span class="sxs-lookup"><span data-stu-id="cd347-270">Key improvement actions</span></span>

<span data-ttu-id="cd347-271">이 섹션에는 전반적인 준수 점수에 가장 큰 긍정적인 영향을 미치기 위해 지금 수행할 수 있는 가장 큰 개선 작업이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-271">This section lists the top improvement actions you can take right now to make the largest positive impact on your overall compliance score.</span></span> <span data-ttu-id="cd347-272">개선 **작업 페이지로 이동하려면** 모든 개선 작업 보기를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-272">Select **View all improvement actions** to go to your improvement actions page.</span></span>

### <a name="solutions-that-affect-your-score"></a><span data-ttu-id="cd347-273">점수에 영향을 주는 솔루션</span><span class="sxs-lookup"><span data-stu-id="cd347-273">Solutions that affect your score</span></span>

<span data-ttu-id="cd347-274">이 섹션에서는 점수에 긍정적인 영향을 줄 수 있는 개선 작업이 포함된 솔루션과 해당 솔루션의 미해결 개선 작업 수에 대해 중점적으로 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-274">This section highlights solutions containing improvement actions that can positively impact your score, and the number of outstanding improvement actions in those solutions.</span></span> <span data-ttu-id="cd347-275">솔루션 **페이지를 방문하려면** 모든 솔루션 보기를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-275">Select **View all solutions** to visit your solutions page.</span></span>

### <a name="compliance-score-breakdown"></a><span data-ttu-id="cd347-276">준수 점수 분석</span><span class="sxs-lookup"><span data-stu-id="cd347-276">Compliance score breakdown</span></span>

<span data-ttu-id="cd347-277">이 섹션에서는 다음 두 가지 방법으로 점수에 대한 자세한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-277">This section gives you a more detailed view of your score in two different ways:</span></span>

- <span data-ttu-id="cd347-278">**범주**: "정보 보호" 또는 "장치 관리"처럼 데이터 보호 범주 내에서 전체 점수의 백분율을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-278">**Categories**: shows the percentage of your overall score within data protection categories, such as "protect information" or "manage devices."</span></span>
- <span data-ttu-id="cd347-279">**평가**: GDPR 또는 NIST 800-53과 같은 특정 준수 및 데이터 보호 표준, 규정 또는 법률에 대한 평가를 관리하는 진행률의 백분율을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-279">**Assessments**: shows the percentage of your progress in managing assessments for particular compliance and data protection standards, regulations, or laws, such as GDPR or NIST 800-53.</span></span>

### <a name="filtering-your-dashboard-view"></a><span data-ttu-id="cd347-280">대시보드 보기 필터링</span><span class="sxs-lookup"><span data-stu-id="cd347-280">Filtering your dashboard view</span></span>

<span data-ttu-id="cd347-281">대시보드 보기를 필터링하여 특정 규정 및 표준, 솔루션, 작업 유형, 평가 그룹 또는 데이터 보호 범주와 관련된 항목만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-281">You can filter your dashboard view to see only the items related to particular regulations and standards, solutions, type of action, assessment groups, or data protection categories.</span></span> <span data-ttu-id="cd347-282">이러한 방식으로 보기를 필터링하면 대시보드에서 점수를 필터링하여 필터 조건에 따라 가능한 총 점수에서 달성한 점수 수를 보여 주게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-282">Filtering your view in this way will also filter the score on your dashboard, showing how many points you've achieved out of total possible points based on your filter criteria.</span></span>

<span data-ttu-id="cd347-283">필터를 적용하는 경우:</span><span class="sxs-lookup"><span data-stu-id="cd347-283">To apply filters:</span></span>

1. <span data-ttu-id="cd347-284">**대시보드의** 오른쪽 위에 있는 필터를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-284">Select **Filter** on the upper-right side of the dashboard.</span></span>
2. <span data-ttu-id="cd347-285">필터 플라이아웃  창에서 필터 조건을 선택한 다음 적용을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="cd347-285">Select your filter criteria from the **Filters** flyout pane, then select **Apply**.</span></span>

<span data-ttu-id="cd347-286">필터를 적용하면 실시간으로 점수가 조정된 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-286">After you apply a filter, you’ll see your score adjusted in real time.</span></span> <span data-ttu-id="cd347-287">준수 점수 백분율 및 분석 정보, 개선 작업 및 솔루션은 이제 필터 조건에서 다루는 데이터에만 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-287">The compliance score percentage and breakdown information, and the improvement actions and solutions, now only pertain to data covered by your filter criteria.</span></span> <span data-ttu-id="cd347-288">준수 관리자에서 로그인하면 다시 로그인할 때 필터링된 보기가 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-288">If you sign out of Compliance Manager, your filtered view remains when you sign back in.</span></span>

<span data-ttu-id="cd347-289">필터를 제거하려면</span><span class="sxs-lookup"><span data-stu-id="cd347-289">To remove filters:</span></span>

- <span data-ttu-id="cd347-290">준수 **점수** 위에 있는 적용된 필터에서 제거할 개별 필터 옆에 있는 **X를** 선택합니다. 또는</span><span class="sxs-lookup"><span data-stu-id="cd347-290">At the **Applied filters** heading above your compliance score, select the **X** next to the individual filter you want to remove; or</span></span>
- <span data-ttu-id="cd347-291">대시보드의 **오른쪽** 위에 있는 필터를 선택한 다음  필터 플라이아웃 창에서 필터 지우기를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="cd347-291">Select **Filter** on the upper-right side of your dashboard, then on the **Filters** flyout pane, select **Clear filters**.</span></span>

## <a name="improvement-actions-page"></a><span data-ttu-id="cd347-292">개선 작업 페이지</span><span class="sxs-lookup"><span data-stu-id="cd347-292">Improvement actions page</span></span>

<span data-ttu-id="cd347-293">[개선 작업은](compliance-manager-improvement-actions.md) 조직에서 관리하는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-293">[Improvement actions](compliance-manager-improvement-actions.md) are actions managed by your organization.</span></span> <span data-ttu-id="cd347-294">개선 작업을 수행하면 규정 준수 활동을 중앙 집중화하고 데이터 보호 규정 및 표준을 준수하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-294">Working with improvement actions helps to centralize your compliance activities and align with data protection regulations and standards.</span></span> <span data-ttu-id="cd347-295">각 개선 작업은 자세한 구현 지침과 적절한 솔루션으로 안내하는 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-295">Each improvement action gives detailed implementation guidance and a link to launch you into the appropriate solution.</span></span> <span data-ttu-id="cd347-296">개선 작업을 조직의 사용자에게 할당하여 구현 및 테스트 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-296">Improvement actions can be assigned to users in your organization to perform implementation and testing work.</span></span> <span data-ttu-id="cd347-297">개선 작업 내에 문서, 메모 및 상태 업데이트를 기록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-297">You can also store documentation, notes, and record status updates within the improvement action.</span></span>

### <a name="view-your-improvement-actions"></a><span data-ttu-id="cd347-298">개선 작업 보기</span><span class="sxs-lookup"><span data-stu-id="cd347-298">View your improvement actions</span></span>

<span data-ttu-id="cd347-299">준수 관리자 대시보드에는 주요 개선 **작업이 표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="cd347-299">The Compliance Manager dashboard shows your **key improvement actions.**</span></span> <span data-ttu-id="cd347-300">모든 개선 작업을 확인하려면 대시보드에서 개선 작업 탭을 선택하여 개선 작업 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-300">To view all of your improvement actions, select the Improvement actions tab on your dashboard, which brings you to your improvement actions page.</span></span> <span data-ttu-id="cd347-301">대시보드의 주요 개선 작업 목록 아래에 있는 모든 개선 작업 보기를 선택하여 개선 작업 페이지로 이동하는 것을 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-301">You can also select View all improvement actions underneath the list of key improvement actions on your dashboard to get to your improvement actions page.</span></span>

<span data-ttu-id="cd347-302">개선 작업 페이지에는 조직에서 관리하는 모든 개선 작업이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-302">The improvement actions page shows all of the improvement actions that are managed by your organization.</span></span> <span data-ttu-id="cd347-303">Microsoft에서 관리하는 작업은 각 평가 내에서 볼 [수 있습니다(Microsoft](compliance-manager-assessments.md#microsoft-actions-tab)작업에 대한 자세한 설명).</span><span class="sxs-lookup"><span data-stu-id="cd347-303">Actions that are managed by Microsoft can be viewed within each assessment (learn more about [Microsoft actions](compliance-manager-assessments.md#microsoft-actions-tab)).</span></span>

<span data-ttu-id="cd347-304">개선 작업 페이지에 긴 작업 목록이 있는 경우 보기를 필터링하는 것이 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-304">If you have a long list of actions on your improvement actions page, it may be helpful to filter your view.</span></span> <span data-ttu-id="cd347-305">작업 **목록의** 오른쪽 위 모서리에 있는 필터를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-305">Select **Filter** at the upper-right corner of the actions list.</span></span> <span data-ttu-id="cd347-306">필터 **플라이아웃** 창이 나타나면 규정 및 표준, 솔루션 및 그룹에 따라 조건을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-306">When the **Filters** flyout pane appears, select your criteria based on regulations and standards, solution, and group.</span></span> <span data-ttu-id="cd347-307">오른쪽 위 모서리에서 **그룹을** 선택하여 보기를 사용자 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-307">You can also customize your view by selecting **Group** in the upper-right corner.</span></span> <span data-ttu-id="cd347-308">드롭다운 메뉴에서 그룹, 솔루션, 범주, 작업 유형 또는 상태를 표시하려면 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-308">From the drop-down menu, select to view by group, solution, category, action type, or status.</span></span>

<span data-ttu-id="cd347-309">이 페이지의 기본 보기에는 테스트 상태가 Passed인 개선 작업이 **표시되지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="cd347-309">The default view for this page does not show improvement actions with a test status of **Passed**.</span></span> <span data-ttu-id="cd347-310">테스트를 통과한 작업을 표시하기 위해  필터 플라이아웃 창에서 통과된 상자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-310">To view actions that have passed testing, check the **Passed** box in the Filters flyout pane.</span></span> <span data-ttu-id="cd347-311">테스트 상태가 통과된 작업만 **점수에** 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-311">Only actions with a test status of **Passed** count toward your score.</span></span> <span data-ttu-id="cd347-312">일부 작업의 경우 보류 중인 업데이트 **레이블이 표시될 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="cd347-312">Some actions may show a **pending update label.**</span></span> <span data-ttu-id="cd347-313">개선 [작업의 업데이트에 대해 자세히 알아보습니다.](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions)</span><span class="sxs-lookup"><span data-stu-id="cd347-313">Learn more about [updates to improvement actions](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions).</span></span>

<span data-ttu-id="cd347-314">개선 작업 페이지에는 각 개선 작업에 대한 다음 데이터 포인트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-314">The improvement actions page shows the following data points for each improvement action:</span></span>

- <span data-ttu-id="cd347-315">**달성한 점수:** 작업을 완료하여 사용 가능한 총 점수 수</span><span class="sxs-lookup"><span data-stu-id="cd347-315">**Points achieved**: the number of points achieved out of the total available by completing the action</span></span>
- <span data-ttu-id="cd347-316">**규정:** 작업과 관련한 규정 또는 표준</span><span class="sxs-lookup"><span data-stu-id="cd347-316">**Regulations**: the regulations or standards pertaining to the action</span></span>
- <span data-ttu-id="cd347-317">**Group**: 작업을 할당한 그룹</span><span class="sxs-lookup"><span data-stu-id="cd347-317">**Group**: the group to which you assigned the action</span></span>
- <span data-ttu-id="cd347-318">**해결** 방법 : 작업을 수행할 수 있는 솔루션</span><span class="sxs-lookup"><span data-stu-id="cd347-318">**Solutions**: the solution where you can go to perform the action</span></span>
- <span data-ttu-id="cd347-319">**평가:** 작업이 포함된 평가</span><span class="sxs-lookup"><span data-stu-id="cd347-319">**Assessments**: the assessments that contain the action</span></span>
- <span data-ttu-id="cd347-320">**범주:** 관련 데이터 보호 범주(예: 정보 보호, 장치 관리 등)</span><span class="sxs-lookup"><span data-stu-id="cd347-320">**Categories**: the related data protection category (such as, protect information, manage devices, etc.)</span></span>
- <span data-ttu-id="cd347-321">**테스트 상태:**</span><span class="sxs-lookup"><span data-stu-id="cd347-321">**Test status**:</span></span>
    - <span data-ttu-id="cd347-322">**없음** - 상태 업데이트가 기록되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-322">**None** – no status update recorded</span></span>
    - <span data-ttu-id="cd347-323">**평가되지** 않습니다. 테스트가 시작되지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="cd347-323">**Not assessed** - testing hasn't started</span></span>
    - <span data-ttu-id="cd347-324">**통과 -** 구현 성공적으로 테스트</span><span class="sxs-lookup"><span data-stu-id="cd347-324">**Passed** - implementation successfully tested</span></span>
    - <span data-ttu-id="cd347-325">**실패한 낮은 위험** - 테스트 실패, 낮은 위험</span><span class="sxs-lookup"><span data-stu-id="cd347-325">**Failed low risk** - testing failed, low risk</span></span>
    - <span data-ttu-id="cd347-326">**실패한 중간 위험** - 테스트 실패, 중간 위험</span><span class="sxs-lookup"><span data-stu-id="cd347-326">**Failed medium risk** - testing failed, medium risk</span></span>
    - <span data-ttu-id="cd347-327">**실패한 고위험** - 테스트 실패, 높은 위험</span><span class="sxs-lookup"><span data-stu-id="cd347-327">**Failed high risk** - testing failed, high risk</span></span>
    - <span data-ttu-id="cd347-328">**범위를 벗어날** 수 있습니다. 작업이 평가 범위에 있지 않은 경우 점수에 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-328">**Out of scope** – the action is not in scope for the assessment and doesn't impact your score</span></span>
    - <span data-ttu-id="cd347-329">**검색할** 작업 - 수동 테스트의 경우 작업이 구현되어 있지만 테스트되지 않았다고 나타냅니다. 자동화된 테스트의 경우 작업이 자동화 결과를 기다리는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-329">**To be detected** - for manual test, indicates an action has been implemented but not tested; for automated test, indicates an action is waiting for automation result</span></span>
    - <span data-ttu-id="cd347-330">**검색할 수** 없습니다. 자동화된 상태를 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-330">**Could not be detected** - automated status can't be determined</span></span>
    - <span data-ttu-id="cd347-331">**부분적으로 테스트** – 부분 점수를 수여하는 자동 점수 매기기</span><span class="sxs-lookup"><span data-stu-id="cd347-331">**Partially tested** – automated scoring that awards partial points</span></span>

<span data-ttu-id="cd347-332">**자세한 내용은** 개선 작업 할당 및 수행 [방법을 참조합니다.](compliance-manager-improvement-actions.md)</span><span class="sxs-lookup"><span data-stu-id="cd347-332">**Learn more:** [See how to assign and perform work on improvement actions](compliance-manager-improvement-actions.md).</span></span>

## <a name="solutions-page"></a><span data-ttu-id="cd347-333">솔루션 페이지</span><span class="sxs-lookup"><span data-stu-id="cd347-333">Solutions page</span></span>

<span data-ttu-id="cd347-334">솔루션 페이지에는 솔루션별로 구성한 획득한 점과 잠재적 점수의 공유가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-334">The solutions page shows the share of earned and potential points as organized by solution.</span></span> <span data-ttu-id="cd347-335">이 보기에서 남은 점과 개선 작업을 확인하면 더 즉각적인 주의가 필요한 솔루션을 이해하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-335">Viewing your remaining points and improvement actions from this view helps you understand which solutions need more immediate attention.</span></span>

<span data-ttu-id="cd347-336">준수 관리자 대시보드에서 솔루션  탭을 선택하여 솔루션 페이지를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-336">Find the solutions page by selecting the **Solutions** tab on your Compliance Manager dashboard.</span></span> <span data-ttu-id="cd347-337">대시보드의 **오른쪽** 위 섹션에서  점수에 영향을 주는 솔루션 아래의 모든 솔루션 보기를 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-337">You can also select **View all solutions** underneath **Solutions that affect your score** in the upper-right section of your dashboard.</span></span>

### <a name="filtering-your-solutions-view"></a><span data-ttu-id="cd347-338">솔루션 보기 필터링</span><span class="sxs-lookup"><span data-stu-id="cd347-338">Filtering your solutions view</span></span>

<span data-ttu-id="cd347-339">솔루션 보기를 필터링하는 방법:</span><span class="sxs-lookup"><span data-stu-id="cd347-339">To filter your view of solutions:</span></span>

1. <span data-ttu-id="cd347-340">평가 **목록의** 왼쪽 위 모서리에 있는 필터를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-340">Select **Filter** at the top-left corner of your assessments list.</span></span>
2. <span data-ttu-id="cd347-341">필터 **플라이아웃** 창에서 원하는 기준(표준 및 규정, 솔루션, 작업 유형, 준수 관리자 그룹, 범주) 옆에 확인 표시</span><span class="sxs-lookup"><span data-stu-id="cd347-341">On the **Filters** flyout pane, place a check next to the desired criteria (standards and regulations, solution, action type, Compliance Manager group, category).</span></span>
3. <span data-ttu-id="cd347-342">적용 **단추를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-342">Select the **Apply** button.</span></span> <span data-ttu-id="cd347-343">필터 창이 닫히고 필터링된 보기가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-343">The filter pane will close and you’ll see your filtered view.</span></span>

<span data-ttu-id="cd347-344">평가 목록 위의 그룹 드롭다운 메뉴에서 그룹화 유형을 선택하여 보기를 수정하여  그룹, 제품 또는 규정별로 평가를 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-344">You can also modify your view to see assessments by group, product, or regulation by selecting the type of grouping from the **Group** drop-down menu above your assessments list.</span></span>

### <a name="taking-action-from-the-solution-page"></a><span data-ttu-id="cd347-345">솔루션 페이지에서 작업 수행</span><span class="sxs-lookup"><span data-stu-id="cd347-345">Taking action from the solution page</span></span>

<span data-ttu-id="cd347-346">솔루션 페이지에 개선 작업과 연결된 조직의 솔루션이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-346">The solutions page displays your organization’s solutions that are connected to improvement actions.</span></span> <span data-ttu-id="cd347-347">이 표에는 전체 점수에 대한 각 솔루션의 기여도, 해당 솔루션 내에서 달성할 수 있는 점수 및 가능한 점수, 점수가 증가할 수 있는 해당 솔루션에서 그룹화한 나머지 개선 작업 수가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-347">The table lists each solution’s contribution to your overall score, the points achieved and possible within that solution, and the remaining number of improvement actions grouped in that solution that can increase your score.</span></span>

<span data-ttu-id="cd347-348">이 화면에서 작업을 수행 하는 방법에는 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-348">There are two ways you can take action from this screen:</span></span>

1. <span data-ttu-id="cd347-349">원하는 솔루션의 행에서 나머지  작업 열 아래에서 하이퍼링크된 번호를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-349">On the row of your intended solution, under the **Remaining actions** column, select the hyperlinked number.</span></span> <span data-ttu-id="cd347-350">해당 솔루션에 대해 미확인 개선 작업을 보여 주며 개선 작업 화면의 필터링된 보기가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-350">You’ll see a filtered view of the improvement actions screen showing untested improvement actions for that solution.</span></span>

2. <span data-ttu-id="cd347-351">원하는 솔루션의 행에서 솔루션  열 열에서 **열기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="cd347-351">On the row of your intended solution, under the **Open solution** column, select **Open**.</span></span> <span data-ttu-id="cd347-352">Microsoft 365 및 Office 365 보안 및 규정 준수 센터에서 권장 조치를 취할 수 있는 솔루션 또는 위치가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-352">You’ll see the solution or location in the Microsoft 365 and Office 365 security and compliance centers where you can take the recommended action.</span></span>

## <a name="assessments-page"></a><span data-ttu-id="cd347-353">평가 페이지</span><span class="sxs-lookup"><span data-stu-id="cd347-353">Assessments page</span></span>

<span data-ttu-id="cd347-354">평가 페이지에는 조직에 [](compliance-manager-assessments.md) 대해 설정한 모든 평가가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-354">The assessments page lists all the [assessments](compliance-manager-assessments.md) you set up for your organization.</span></span> <span data-ttu-id="cd347-355">준수 점수 디노이터는 추적된 모든 평가에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-355">Your compliance score denominator is determined by all your tracked assessments.</span></span> <span data-ttu-id="cd347-356">평가를 더 추가하면 개선 작업 페이지에 더 많은 개선 작업이 나열되어 준수 점수 디노이터가 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-356">As you add more assessments, you'll see more improvement actions listed on your improvement actions page, and your compliance score denominator increases.</span></span>

<span data-ttu-id="cd347-357">평가 페이지에는 각 평가에 대한 주요 정보가 요약됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-357">The assessments page summarizes key information about each assessment:</span></span>

- <span data-ttu-id="cd347-358">**평가**: 평가 이름</span><span class="sxs-lookup"><span data-stu-id="cd347-358">**Assessment**: name of the assessment</span></span>
- <span data-ttu-id="cd347-359">**Status**:</span><span class="sxs-lookup"><span data-stu-id="cd347-359">**Status**:</span></span>
    - <span data-ttu-id="cd347-360">**complete** - 모든 컨트롤의 상태가 "전달"되거나 하나 이상의 컨트롤이 전달된 후 나머지는 "범위를 벗어났습니다."입니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-360">**Complete** -  all controls have a status of “passed,” or at least one is passed and the rest are “out of scope”</span></span>
    - <span data-ttu-id="cd347-361">**불완전** - 하나 이상의 컨트롤 상태가 "실패" 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-361">**Incomplete** – at least one control has a status of “failed"</span></span>
    - <span data-ttu-id="cd347-362">**없음** - 모든 컨트롤이 테스트되지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="cd347-362">**None** - all controls have have not been tested</span></span>
    - <span data-ttu-id="cd347-363">**진행 중** - 개선 작업의 상태가 "진행 중", "부분 크레딧" 또는 "확인되지 않습니다."를 비롯한 다른 상태가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-363">**In progress** - improvement actions have any other status, including “in progress,” “partial credit,” or “undetected</span></span>
- <span data-ttu-id="cd347-364">**평가 진행률**: 성공적으로 테스트된 컨트롤 수로 측정된 완료까지 수행된 작업의 백분율</span><span class="sxs-lookup"><span data-stu-id="cd347-364">**Assessment progress**: the percentage of the work done toward completion, as measured by the number of controls successfully tested</span></span>
- <span data-ttu-id="cd347-365">**개선 작업:** 컨트롤 구현을 충족하기 위한 완료된 작업 수</span><span class="sxs-lookup"><span data-stu-id="cd347-365">**Your improvement actions**: the number of completed actions to satisfy implementation of your controls</span></span>
- <span data-ttu-id="cd347-366">**Microsoft 작업:** Microsoft 컨트롤 구현을 충족하기 위한 완료된 작업 수</span><span class="sxs-lookup"><span data-stu-id="cd347-366">**Microsoft actions**: the number of completed actions to satisfy implementation of Microsoft controls</span></span>
- <span data-ttu-id="cd347-367">**Group**: 평가가 속한 그룹의 이름</span><span class="sxs-lookup"><span data-stu-id="cd347-367">**Group**: name of the group the assessment belongs to</span></span>
- <span data-ttu-id="cd347-368">**제품**: 연결된 Microsoft 365 서비스</span><span class="sxs-lookup"><span data-stu-id="cd347-368">**Product**: associated Microsoft 365 service</span></span>
- <span data-ttu-id="cd347-369">**규정**: 평가에 적용되는 규정 표준, 정책 또는 법률</span><span class="sxs-lookup"><span data-stu-id="cd347-369">**Regulation**: the regulatory standard, policy, or law that applies to the assessment</span></span>

### <a name="filtering-your-assessments-view"></a><span data-ttu-id="cd347-370">평가 보기 필터링</span><span class="sxs-lookup"><span data-stu-id="cd347-370">Filtering your assessments view</span></span>

<span data-ttu-id="cd347-371">평가 보기를 필터링하기 위해 다음을 수행하십시오.</span><span class="sxs-lookup"><span data-stu-id="cd347-371">To filter you view of assessments:</span></span>

1. <span data-ttu-id="cd347-372">평가 **목록의** 왼쪽 위 모서리에 있는 필터를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-372">Select **Filter** at the top-left corner of your assessments list.</span></span>
2. <span data-ttu-id="cd347-373">필터 **플라이아웃** 창에서 원하는 조건을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-373">On the **Filters** flyout pane, check your desired criteria.</span></span>
3. <span data-ttu-id="cd347-374">적용 **단추를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-374">Select the **Apply** button.</span></span> <span data-ttu-id="cd347-375">필터 창이 닫히고 필터링된 보기가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-375">The filter pane will close and you will see your filtered view.</span></span>

<span data-ttu-id="cd347-376">평가 목록 위의 그룹 드롭다운 메뉴에서 그룹화 유형을 선택하여 보기를 수정하여  그룹, 제품 또는 규정별로 평가를 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-376">You can also modify your view to see assessments by group, product, or regulation by selecting the type of grouping from the **Group** drop-down menu above your assessments list.</span></span>

### <a name="default-assessment"></a><span data-ttu-id="cd347-377">기본 평가</span><span class="sxs-lookup"><span data-stu-id="cd347-377">Default assessment</span></span>

<span data-ttu-id="cd347-378">기본적으로 평가 페이지에 데이터 [](compliance-manager-assessments.md#data-protection-baseline-default-assessment) 보호 기준 평가가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-378">By default, you'll see the [Data Protection Baseline](compliance-manager-assessments.md#data-protection-baseline-default-assessment) assessment on the assessments page.</span></span> <span data-ttu-id="cd347-379">준수 관리자는 평가를 작성하기 위해 미리 작성된 [여러](compliance-manager-templates-list.md) 템플릿도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-379">Compliance Manager also provides several pre-built [templates](compliance-manager-templates-list.md) for building assessments.</span></span>

## <a name="assessment-templates-page"></a><span data-ttu-id="cd347-380">평가 템플릿 페이지</span><span class="sxs-lookup"><span data-stu-id="cd347-380">Assessment templates page</span></span>

<span data-ttu-id="cd347-381">템플릿은 준수 관리자에서 평가를 만들기 위한 프레임워크입니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-381">A template is a framework for creating an assessment in Compliance Manager.</span></span> <span data-ttu-id="cd347-382">평가 템플릿 페이지에 서식 파일 및 주요 세부 정보 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-382">The assessment templates page displays a list of templates and key details.</span></span> <span data-ttu-id="cd347-383">이 목록에는 준수 관리자가 제공한 서식 파일과 조직에서 수정하거나 만든 모든 템플릿이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-383">The list includes templates provided by Compliance Manager as well as any templates your organization has modified or created.</span></span> <span data-ttu-id="cd347-384">필터를 적용하여 인증, 제품 범위, 국가, 산업 및 템플릿을 만든 사람에 따라 템플릿을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-384">You can apply filters to find a template based on certification, product scope, country, industry, and who created it.</span></span>

<span data-ttu-id="cd347-385">해당 행에서 템플릿을 선택하여 템플릿에 대한 설명과 인증, 범위 및 컨트롤 세부 정보에 대한 추가 정보가 포함된 세부 정보 페이지를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-385">Select a template from its row to bring up its details page, which contains a description of the template and further information about certification, scope, and controls details.</span></span> <span data-ttu-id="cd347-386">이 페이지에서 적절한 단추를 선택하여 평가를 만들거나 서식 파일을 Excel로 내보내거나 서식 파일을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd347-386">From this page you can select the appropriate buttons to create an assessment, export the template data to Excel, or modify the template.</span></span>

<span data-ttu-id="cd347-387">**자세한 내용은 평가** [템플릿을 사용하는 방법을 읽어 읽습니다.](compliance-manager-templates.md)</span><span class="sxs-lookup"><span data-stu-id="cd347-387">**Learn more:** [Read how to work with assessment templates](compliance-manager-templates.md).</span></span>

## <a name="next-step"></a><span data-ttu-id="cd347-388">다음 단계</span><span class="sxs-lookup"><span data-stu-id="cd347-388">Next step</span></span>
<span data-ttu-id="cd347-389">평가를 설정하여 준수 [관리자를 사용자 지정합니다.](compliance-manager-assessments.md)</span><span class="sxs-lookup"><span data-stu-id="cd347-389">Customize Compliance Manager by [setting up assessments](compliance-manager-assessments.md).</span></span>
