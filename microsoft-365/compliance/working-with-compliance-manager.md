---
title: Microsoft 준수 관리자 사용 (미리 보기)
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 준수 관리자는 Microsoft Service Trust Portal의 무료 워크플로 기반 위험 평가 도구입니다. 준수 관리자를 사용 하면 Microsoft 클라우드 서비스와 관련 된 규정 준수 활동을 추적, 할당 및 확인할 수 있습니다.
ms.openlocfilehash: c50122f390809e145af621ed6341d02ae9c3b8cf
ms.sourcegitcommit: fb3815ee186b2b3ec790ee32a9d7b1628d623b0b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "39202359"
---
# <a name="work-with-microsoft-compliance-manager-preview"></a><span data-ttu-id="d6d2a-104">Microsoft 준수 관리자 사용 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="d6d2a-104">Work with Microsoft Compliance Manager (Preview)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d6d2a-105">Microsoft 준수 관리자는 데이터 보호 및 규정 준수를 개선 하기 위한 준수 기간 및 권장 사항에 대 한 요약을 제공 하는 대시보드 및 관리 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-105">Microsoft Compliance Manager is a dashboard and management tool that provides a summary of your data protection and compliance stature and recommendations to improve data protection and compliance.</span></span> <span data-ttu-id="d6d2a-106">준수 관리자에 제공 되는 고객 작업은 권장 사항입니다. 구현 하기 전에 해당 규정 환경에서 이러한 권장 사항의 효과를 평가 하는 것이 조직에 게 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-106">The customer actions provided in Compliance Manager are recommendations; it is up to your organization to evaluate the effectiveness of these recommendations in their respective regulatory environment prior to implementation.</span></span> <span data-ttu-id="d6d2a-107">준수 관리자에 게 제공 되는 권장 사항은 준수 보장으로 해석 되어서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-107">Recommendations found in Compliance Manager should not be interpreted as a guarantee of compliance.</span></span>

## <a name="access-compliance-manager"></a><span data-ttu-id="d6d2a-108">액세스 준수 관리자</span><span class="sxs-lookup"><span data-stu-id="d6d2a-108">Access Compliance Manager</span></span>

<span data-ttu-id="d6d2a-p103">Service Trust Portal에서 준수 관리자에 액세스할 수 있습니다. Microsoft 계정이 나 Azure Active Directory 조직 계정을 가진 사용자라면 누구나 준수 관리자에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-p103">You access Compliance Manager from the Service Trust Portal. Anyone with a Microsoft account or Azure Active Directory organizational account can access Compliance Manager.</span></span>
  
1. <span data-ttu-id="d6d2a-111">[https://servicetrust.microsoft.com](https://servicetrust.microsoft.com/)으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-111">Go to [https://servicetrust.microsoft.com](https://servicetrust.microsoft.com/).</span></span>

2. <span data-ttu-id="d6d2a-112">Microsoft 서비스 계정으로 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-112">Sign in with your Microsoft service account.</span></span> <span data-ttu-id="d6d2a-113">Office 365, Microsoft 365 또는 Azure Active Directory (Azure AD) 사용자 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-113">This is your Office 365, Microsoft 365, or Azure Active Directory (Azure AD) user account.</span></span>

3. <span data-ttu-id="d6d2a-114">서비스 신뢰 포털에서 **준수 관리자**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-114">In the Service Trust Portal, select **Compliance Manager**.</span></span> <span data-ttu-id="d6d2a-115">다음은 준수 관리자의 미리 보기 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-115">This is the preview version of Compliance Manager.</span></span> <span data-ttu-id="d6d2a-116">**준수 관리자 (클래식)** 는 준수 관리자의 이전 버전에 대 한 링크입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-116">**Compliance Manager (Classic)** is the link to the previous version of Compliance Manager.</span></span>

4. <span data-ttu-id="d6d2a-117">비밀 유지 계약이 표시 되 면이를 읽고 계속 하려면 **동의** 함을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-117">When the Non-Disclosure Agreement is displayed, read it, and select **Agree** to continue.</span></span> <span data-ttu-id="d6d2a-118">한 번 동의 하 고 준수 관리자 대시보드가 표시 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-118">You must agree once, and then the Compliance Manager dashboard is displayed.</span></span>

<span data-ttu-id="d6d2a-119">시작 하기 위해 Office 365에 대 한 ISO/IEC 27001:2103 평가가 조직에 기본적으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-119">To get you started, an ISO/IEC 27001:2103 Assessment for Office 365 appears by default for your organization.</span></span>

## <a name="administration"></a><span data-ttu-id="d6d2a-120">관리</span><span class="sxs-lookup"><span data-stu-id="d6d2a-120">Administration</span></span>

<span data-ttu-id="d6d2a-121">전역 관리자만 사용할 수 있으며 전역 관리자 계정으로 로그인 한 경우에만 표시 되는 특정 관리 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-121">There are specific administrative functions that are only available to the global administrator and only visible when logged in with a global administrator account.</span></span> <span data-ttu-id="d6d2a-122">전역 관리자는 사용자 권한을 할당할 수 있으며 모든 작업에 대해 자동 보안 점수 업데이트를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-122">The global administrator can assign user permissions, and can turn on automatic Secure Score updates for all actions.</span></span>
  
### <a name="assigning-compliance-manager-roles-to-users"></a><span data-ttu-id="d6d2a-123">사용자에게 준수 관리자 역할 할당</span><span class="sxs-lookup"><span data-stu-id="d6d2a-123">Assigning Compliance Manager roles to users</span></span>

<span data-ttu-id="d6d2a-124">관리자가 다른 사용자에 게 준수 관리자 역할을 할당 하면 해당 사용자는 준수 관리자에서 데이터를 보고 역할에 따라 결정 된 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-124">Once the administrator assigns Compliance Manager roles to other users, those users can view data in Compliance Manager and perform actions determined by their role.</span></span> <span data-ttu-id="d6d2a-125">또한 관리자는 azure [Active Directory (AZURE AD)에서 사용자에 게 전역 독자 역할](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-reader)을 할당 하 여 준수 관리자에 게 읽기 전용 액세스 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-125">The administrator can also give read-only access to Compliance Manager by assigning the user the [Global Reader role in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-reader).</span></span>

<span data-ttu-id="d6d2a-126">각 준수 관리자 역할에는 약간 다른 사용 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-126">Each Compliance Manager role has slightly different permissions.</span></span> <span data-ttu-id="d6d2a-127">각 역할에 할당 된 사용 권한을 보고, 어떤 사용자가 역할을 하 고 있는지 확인 하 고, 서비스 트러스트 포털을 통해 해당 역할에서 사용자를 추가 하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-127">You can view the permissions assigned to each role, see which users are in which roles, and add or remove users from that role through the Service Trust Portal.</span></span> <span data-ttu-id="d6d2a-128">**관리** 메뉴 항목을 선택 하 고 보려는 **설정을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-128">Select the **Admin** menu item, and choose **Settings** to view.</span></span>
  
![STP 관리 메뉴: 선택한 설정](media/65a82b1b-d462-452f-988b-7e4263bd638e.png)
  
<span data-ttu-id="d6d2a-130">준수 관리자 역할에서 사용자를 추가하거나 제거하려면</span><span class="sxs-lookup"><span data-stu-id="d6d2a-130">To add or remove users from Compliance Manager roles.</span></span>
  
1. <span data-ttu-id="d6d2a-131">[https://servicetrust.microsoft.com](https://servicetrust.microsoft.com)으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-131">Go to [https://servicetrust.microsoft.com](https://servicetrust.microsoft.com).</span></span>

2. <span data-ttu-id="d6d2a-132">Azure Active Directory 전역 관리자 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-132">Sign in with your Azure Active Directory global administrator account.</span></span>

3. <span data-ttu-id="d6d2a-133">서비스 보안 포털의 위쪽 메뉴 모음에서 **관리자** 를 선택 하 고 **설정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-133">On the Service Trust Portal top menu bar, select **Admin** and then choose **Settings**.</span></span>

4. <span data-ttu-id="d6d2a-134">**역할 선택** 드롭다운 목록에서 관리 하려는 역할을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-134">In the **Select Role** drop-down list, select the role that you want to manage.</span></span>

5. <span data-ttu-id="d6d2a-135">각 역할에 추가된 사용자는 **역할 선택** 페이지에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-135">Users added to each role are listed on the **Select Role** page.</span></span>

6. <span data-ttu-id="d6d2a-136">이 역할에 사용자를 추가 하려면 **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-136">To add users to this role, select **Add**.</span></span> <span data-ttu-id="d6d2a-137">**사용자 추가** 대화 상자에서 사용자 필드를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-137">In the **Add Users** dialog, select the user field.</span></span> <span data-ttu-id="d6d2a-138">사용 가능한 사용자 목록을 스크롤하거나 사용자 이름을 입력 하 여 검색 용어에 따라 목록을 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-138">You can scroll through the list of available users or begin typing the user name to filter the list based on your search term.</span></span> <span data-ttu-id="d6d2a-139">해당 역할을 사용 하 여 프로 비전 된 **사용자 추가** 목록에 해당 계정을 추가할 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-139">Select the user to add that account to the **Add Users** list provisioned with that role.</span></span> <span data-ttu-id="d6d2a-140">여러 사용자를 동시에 추가 하려면 목록을 필터링 하는 사용자 이름을 입력 하기 시작한 다음 목록에 추가할 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-140">If you would like to add multiple users concurrently, begin typing a user name to filter the list, and then select the user to add to the list.</span></span> <span data-ttu-id="d6d2a-141">**저장** 을 선택 하 여 해당 사용자에 게 선택한 역할을 프로 비전 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-141">Select **Save** to provision the selected role to these users.</span></span> 

    ![준수 관리자-사용자 추가](media/compliance-manager-add-users.png)
  
7. <span data-ttu-id="d6d2a-143">이 역할에서 사용자를 제거 하려면 사용자를 선택 하 고 **삭제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-143">To remove users from this role, select the users and select **Delete**.</span></span>

    ![준수 관리자-사용자 삭제](media/compliance-manager-delete-users.png)

### <a name="controlling-automatic-secure-score-updates"></a><span data-ttu-id="d6d2a-145">자동 보안 점수 업데이트 제어</span><span class="sxs-lookup"><span data-stu-id="d6d2a-145">Controlling automatic Secure Score updates</span></span>

<span data-ttu-id="d6d2a-146">보안 점수 업데이트는 모든 작업에 대해 자동으로 설정 하거나, 모든 작업에 대해 해제 하거나, 개별 작업을 통해 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-146">Secure Score updates can be turned on automatically for all actions, can be turned off for all actions, or can be set by individual action.</span></span>

1. <span data-ttu-id="d6d2a-147">전역 관리자 계정을 사용 하 여 [서비스 신뢰 포털](https://servicetrust.microsoft.com) 에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-147">Sign in to the [Service Trust Portal](https://servicetrust.microsoft.com) with your global administrator account.</span></span>

2. <span data-ttu-id="d6d2a-148">서비스 보안 포털의 위쪽 메뉴 모음에서 **관리자** 를 선택 하 고 **설정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-148">On the Service Trust Portal top menu bar, select **Admin** and then choose **Settings**.</span></span>

4. <span data-ttu-id="d6d2a-149">**보안 점수** 탭에서 선택한 설정에 해당 하는 단추를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-149">In the **Secure Score** tab, select the appropriate button for you chosen setting.</span></span>

<span data-ttu-id="d6d2a-150">**참고:** 전역 관리자만 모든 작업에 대해 자동 업데이트를 설정 하거나 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-150">**Note:** Only the global administrator can turn on or off automatic updates for all actions.</span></span> <span data-ttu-id="d6d2a-151">준수 관리자 관리자는 개별 작업에 대해 자동 업데이트를 설정할 수 있지만 모든 작업에 대해 전역적으로 수행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-151">The Compliance Manager administrator can turn on automatic updates for individual actions, but not for all actions globally.</span></span>

## <a name="groups"></a><span data-ttu-id="d6d2a-152">그룹</span><span class="sxs-lookup"><span data-stu-id="d6d2a-152">Groups</span></span>

<span data-ttu-id="d6d2a-153">그룹을 사용 하면 평가를 논리적으로 구성 하 고, 동일 하거나 관련 된 고객 관리 컨트롤이 있는 평가 간에 일반 정보 및 워크플로 작업을 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-153">Groups allow you to logically organize Assessments and that share common information and workflow tasks between Assessments that have the same or related customer-managed controls.</span></span> <span data-ttu-id="d6d2a-154">조직 내의 연, 표준, 서비스, 팀, 부서 또는 기관 별로 평가를 그룹화 하 여 고객 관리 작업을 최소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-154">You can group Assessments by year, standard, service, team, division, or agencies within your organization to help minimize customer-managed Actions:</span></span>
  
- <span data-ttu-id="d6d2a-155">**FFIEC는 평가 2019**</span><span class="sxs-lookup"><span data-stu-id="d6d2a-155">**FFIEC IS Assessments 2019**</span></span>
  - <span data-ttu-id="d6d2a-156">Office 365 + FFIEC가</span><span class="sxs-lookup"><span data-stu-id="d6d2a-156">Office 365 + FFIEC IS</span></span>
  - <span data-ttu-id="d6d2a-157">Intune + FFIEC가</span><span class="sxs-lookup"><span data-stu-id="d6d2a-157">Intune + FFIEC IS</span></span>
- <span data-ttu-id="d6d2a-158">**데이터 보안 및 개인 정보 보호 평가**</span><span class="sxs-lookup"><span data-stu-id="d6d2a-158">**Data Security and Privacy Assessments**</span></span>
  - <span data-ttu-id="d6d2a-159">Office 365 + ISO 27001:2013</span><span class="sxs-lookup"><span data-stu-id="d6d2a-159">Office 365 + ISO 27001:2013</span></span>
  - <span data-ttu-id="d6d2a-160">Office 365 + ISO 27018:2014</span><span class="sxs-lookup"><span data-stu-id="d6d2a-160">Office 365 + ISO 27018:2014</span></span>

<span data-ttu-id="d6d2a-161">새 평가를 만들 때 평가를 위한 새 그룹을 만들거나 기존 그룹에 평가를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-161">When you create a new Assessment, you must create a new group for the Assessment or assign the Assessment to an existing group.</span></span> <span data-ttu-id="d6d2a-162">독립 실행형 엔터티로 그룹을 만들 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-162">Groups cannot be created as stand-alone entities.</span></span> <span data-ttu-id="d6d2a-163">새 평가를 추가 *하기 전에 먼저* 조직에 대 한 그룹화 전략을 결정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-163">It's recommended that you determine a grouping strategy for your organization *before* adding new assessments.</span></span> <span data-ttu-id="d6d2a-164">기본적으로 초기 평가를 위해 "기본 그룹" 이라는 그룹을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-164">By default, a Group named "Default Group" is available for your initial Assessments.</span></span> <span data-ttu-id="d6d2a-165">그룹에 보안 속성이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-165">Groups do not have any security properties.</span></span> <span data-ttu-id="d6d2a-166">모든 사용 권한은 평가와 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-166">All permissions are associated with Assessments.</span></span>

<span data-ttu-id="d6d2a-167">그룹으로 작업할 때는 다음 사항을 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-167">When you work with groups, remember:</span></span>
  
- <span data-ttu-id="d6d2a-168">같은 그룹 내의 서로 다른 평가에서 관련 평가 컨트롤은 완료 시 자동으로 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-168">Related assessment controls in different assessments within the same Group automatically update when completed.</span></span>
- <span data-ttu-id="d6d2a-169">새 그룹은 새로운 평가를 만들 때 기존 그룹에서 정보를 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-169">New groups can copy information from an existing group when you create a new Assessment.</span></span> <span data-ttu-id="d6d2a-170">복사 하는 그룹의 평가에서 고객 관리 되는 컨트롤의 구현 세부 정보 및 테스트 계획 및 관리 응답 필드에 추가 되는 모든 정보가 새 사용자의 동일한 (또는 관련) 고객 관리 컨트롤로 복사 됩니다. 평가.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-170">Any information added to the Implementation Details and Test Plan and Management Response fields of customer-managed controls from Assessments in the group that you're copying from are copied to the same (or related) customer-managed controls in the new Assessment.</span></span> <span data-ttu-id="d6d2a-171">기존 그룹에 새 평가를 추가 하는 경우 해당 그룹의 평가에 대 한 공통 정보가 새 평가로 복사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-171">If you're adding a new Assessment to an existing group, common information from Assessments in that group are copied to the new Assessment.</span></span>
- <span data-ttu-id="d6d2a-172">그룹 이름 ( *그룹 id*라고도 함)은 조직 내에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-172">Group names (also called *Group IDs*) must be unique within your organization.</span></span>
- <span data-ttu-id="d6d2a-173">그룹에는 동일한 인증/규정에 대 한 평가가 포함 될 수 있지만, 각 그룹에는 특정 클라우드 서비스/인증 쌍에 대 한 평가를 하나만 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-173">Groups can contain Assessments for the same certification/regulation, but each group can only contain one Assessment for a specific cloud service/certification pair.</span></span> <span data-ttu-id="d6d2a-174">예를 들어 그룹에는 Office 365 및 NIST CSF에 대 한 두 가지 평가를 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-174">For example, a group can't contain two Assessments for Office 365 and NIST CSF.</span></span> <span data-ttu-id="d6d2a-175">그룹은 각각에 대 한 해당 하는 인증/규정을 서로 다른 경우에만 동일한 클라우드 서비스에 대 한 여러 평가를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-175">A group can contain multiple Assessments for the same cloud service only if the corresponding certification/regulation for each one is different.</span></span>
- <span data-ttu-id="d6d2a-176">평가가 평가 그룹에 추가 되 면 그룹화를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-176">Once an assessment has been added to an assessment group, the grouping cannot be changed.</span></span> <span data-ttu-id="d6d2a-177">평가 그룹의 이름을 바꾸어 해당 그룹과 연결 된 모든 평가에 대 한 평가 그룹화의 이름을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-177">You can rename the assessment group, which changes the name of the assessment grouping for all the assessments associated with that group.</span></span> <span data-ttu-id="d6d2a-178">평가와 새 평가 그룹을 만들고 기존 평가에서 정보를 복사할 수 있으며, 이 경우 사실상 다른 평가 그룹에 해당 평가의 복제본이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-178">You can create an assessment and a new assessment group and copy information from an existing assessment, which effectively creates a duplicate of that assessment in a different assessment group.</span></span>
- <span data-ttu-id="d6d2a-179">보관 평가와 그룹 간의 관계를 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-179">Archiving an assessment breaks the relationship between that assessment and the group.</span></span> <span data-ttu-id="d6d2a-180">다른 관련 평가에 대한 추가 업데이트는 더 이상 보관된 평가에 반영되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-180">Any further updates to other related assessments are no longer reflected in the archived assessment.</span></span>

## <a name="tenant-management"></a><span data-ttu-id="d6d2a-181">테 넌 트 관리</span><span class="sxs-lookup"><span data-stu-id="d6d2a-181">Tenant Management</span></span>

<span data-ttu-id="d6d2a-182">준수 관리자 (미리 보기)에는 **테 넌 트 관리**라는 새 데이터 요소를 관리 하기 위한 새로운 인터페이스가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-182">Compliance Manager (Preview) includes a new interface for managing new data elements called **Tenant Management**.</span></span> <span data-ttu-id="d6d2a-183">이 인터페이스를 사용 하 여 테 넌 트 전체 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-183">This interface enables you to manage tenant-wide settings:</span></span>

- <span data-ttu-id="d6d2a-184">**차원:** 사용자 지정 필터 피벗을 만드는 데 사용할 수 있는 템플릿, 평가 및 작업 항목에 대 한 메타 데이터를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-184">**Dimensions:** View metadata for Templates, Assessments, and Action Items that allow you to create custom pivots for filters.</span></span>
- <span data-ttu-id="d6d2a-185">**소유자:** 각 작업 항목의 소유자를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-185">**Owners:** Specify an owner for each Action Item.</span></span>
- <span data-ttu-id="d6d2a-186">**고객 작업:** 준수 관리자 (미리 보기)에 포함 된 작업 항목의 전체 목록과 보안 점수와 통합 된 작업에 대 한 보안 점수 모니터링 사용/사용 안 함을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-186">**Customer Actions:** Manage the complete list of Actions Items included in Compliance Manager (Preview) and enable/disable Secure Score monitoring for Actions that are integrated with Secure Score.</span></span>

<span data-ttu-id="d6d2a-187">**테 넌 트 관리** 를 선택 하 여 관리 인터페이스를 열고 다음 단계를 수행 하 여 **차원**, **소유자**및 **고객 작업**을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-187">Select **Tenant Management** to open the management interface, and use the following steps to manage **Dimensions**, **Owners**, and **Customer Actions**.</span></span>

### <a name="dimensions"></a><span data-ttu-id="d6d2a-188">높이</span><span class="sxs-lookup"><span data-stu-id="d6d2a-188">Dimensions</span></span>

<span data-ttu-id="d6d2a-189">차원은 템플릿, 평가 또는 작업 항목에 대 한 정보를 제공 하는 메타 데이터 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-189">Dimensions are sets of metadata that provide information about a Template, an Assessment, or an Action Item.</span></span> <span data-ttu-id="d6d2a-190">차원은 차원 키가 속성을 나타내는 키 및 값의 개념을 사용 하 고, 차원 값은 속성의 유효한 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-190">Dimensions use the concept of Keys and Values, where the Dimension Key represents a property, and Dimension Value represents valid values for the property.</span></span> <span data-ttu-id="d6d2a-191">예를 들어 준수 관리자에서 다음 세 가지 유형의 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-191">For example, in Compliance Manager there are three types of Actions.</span></span> <span data-ttu-id="d6d2a-192">**설명서**, **운영**및 **기술**에 대 한 **작업 유형** 및 차원 값의 차원 키로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-192">They are defined by a Dimension Key of **Action Type** and Dimension Values of **Documentation**, **Operational**, and **Technical**.</span></span> <span data-ttu-id="d6d2a-193">기존 차원을 편집 하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-193">You can edit or delete existing Dimensions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d6d2a-194">새 차원을 추가할 수 있으며 이미 가져온 서식 파일에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-194">You can add new dimensions, and they can be assigned to Templates that you have already imported.</span></span> <span data-ttu-id="d6d2a-195">새로 만든 템플릿에 새 차원을 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-195">You can also add new dimensions to any new Templates you create.</span></span>

### <a name="owners"></a><span data-ttu-id="d6d2a-196">소유자</span><span class="sxs-lookup"><span data-stu-id="d6d2a-196">Owners</span></span>

<span data-ttu-id="d6d2a-197">소유자는 각 컨트롤에 대 한 책임 당사자를 식별 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-197">Owners are used to identify the responsible party for each control.</span></span> <span data-ttu-id="d6d2a-198">모든 기본 제공 컨트롤은 Microsoft, 고객 또는 둘 모두에 의해 소유 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-198">All built-in controls are owned by Microsoft, by customers, or by both.</span></span> <span data-ttu-id="d6d2a-199">소유자에 대해 사용자 지정 값을 만들어 조직 내에서 보다 세부적인 책임을 지정 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-199">You can create custom values for Owners that can be used to specify more granular responsibilities within your organization.</span></span> <span data-ttu-id="d6d2a-200">예를 들어 조직 내의 특정 그룹, 팀 또는 비즈니스 단위를 나타내는 소유자를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-200">For example, you could create Owners that represent specific groups, teams, or business units within your organization.</span></span>

#### <a name="add-an-owner"></a><span data-ttu-id="d6d2a-201">소유자 추가</span><span class="sxs-lookup"><span data-stu-id="d6d2a-201">Add an Owner</span></span>

1. <span data-ttu-id="d6d2a-202">**테 넌 트 관리** 를 열고 **소유자**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-202">Open **Tenant Management** and select **Owners**.</span></span>
2. <span data-ttu-id="d6d2a-203">**+ 소유자 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-203">Select **+ Add owner**.</span></span>
3. <span data-ttu-id="d6d2a-204">소유자의 이름과 설명을 입력 하 고 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-204">Provide a Name and Description for the Owner and select **Save**.</span></span> <span data-ttu-id="d6d2a-205">설명은 소유자 열에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-205">The description is displayed in the Owner column.</span></span>

#### <a name="edit-an-owner"></a><span data-ttu-id="d6d2a-206">소유자 편집</span><span class="sxs-lookup"><span data-stu-id="d6d2a-206">Edit an Owner</span></span>

<span data-ttu-id="d6d2a-207">소유자 이름은 편집할 수 없지만 소유자 열에 표시 되는 설명은 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-207">You can’t edit an Owner name, but you can modify the description that is displayed in the Owner column.</span></span>

1. <span data-ttu-id="d6d2a-208">**테 넌 트 관리** 를 열고 **소유자**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-208">Open **Tenant Management** and select **Owners**.</span></span>
2. <span data-ttu-id="d6d2a-209">편집할 소유자를 찾은 다음 옆에 있는 줄임표 (...)를 선택 하 고 **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-209">Locate the Owner you want to edit, select the ellipses (…) next to it, and select **Edit**.</span></span>
3. <span data-ttu-id="d6d2a-210">필요에 따라 설명을 수정 하 고 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-210">Modify the Description as needed and select **Save**.</span></span>

#### <a name="delete-an-owner"></a><span data-ttu-id="d6d2a-211">소유자 삭제</span><span class="sxs-lookup"><span data-stu-id="d6d2a-211">Delete an Owner</span></span>

1. <span data-ttu-id="d6d2a-212">**테 넌 트 관리** 를 열고 **소유자**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-212">Open **Tenant Management** and select **Owners**.</span></span>
2. <span data-ttu-id="d6d2a-213">삭제할 소유자를 찾고 옆에 있는 줄임표 (...)를 선택한 다음 **삭제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-213">Locate the Owner you want to delete, select the ellipses (…) next to it, and select **Delete**.</span></span>
3. <span data-ttu-id="d6d2a-214">확인 메시지가 표시 되 면 **삭제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-214">When the confirmation message appears, select **Delete**.</span></span>

### <a name="customer-actions"></a><span data-ttu-id="d6d2a-215">고객 작업</span><span class="sxs-lookup"><span data-stu-id="d6d2a-215">Customer Actions</span></span>

<span data-ttu-id="d6d2a-216">고객 작업 영역에는 준수 관리자 (미리 보기)의 모든 템플릿 및 평가에 대 한 모든 고객 작업이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-216">The Customer Actions area shows all the customer actions for all Templates and Assessments in Compliance Manager (Preview).</span></span>

<span data-ttu-id="d6d2a-217">![준수 관리자-사용자 추가](media/compliance-manager-customer-actions.png "준수 관리자 고객 작업")</span><span class="sxs-lookup"><span data-stu-id="d6d2a-217">![Compliance Manager — add users](media/compliance-manager-customer-actions.png "Compliance Manager Customer Actions")</span></span>

<span data-ttu-id="d6d2a-218">작업의 제목, 소유자, 범주, 적용 및 점수를 한눈에 확인 하 고 보안 점수와 통합 되어 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-218">At a glance, you can see an Action’s title, owner, category, enforcement, and score, and determine if it is integrated with Secure Score.</span></span> <span data-ttu-id="d6d2a-219">작업을 확장 하 고 **자세히 읽기** 를 선택 하 여 작업의 설명을 읽고 설명에 있는 링크에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-219">You can expand an Action and select **Read More** to read the Action’s description and access any links in the description.</span></span> <span data-ttu-id="d6d2a-220">또한이 인터페이스를 사용 하 여 동작 별로 보안 점수 통합을 사용 하거나 사용 하지 않도록 설정 하 고 사용자 지정 작업을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-220">You can also use this interface to enable and disable Secure Score integration on a per-action basis, and to add custom actions.</span></span> <span data-ttu-id="d6d2a-221">보안 점수 통합 기능을 가진 작업에는 줄임표 (...)가 있습니다 (사용자 지정 작업 옆에는 줄임표 (...))가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-221">Actions that have Secure Score integration capabilities have an ellipsis (…) next to them (note that custom actions also have an ellipsis next to them).</span></span>

#### <a name="enable-or-disable-secure-score-integration"></a><span data-ttu-id="d6d2a-222">보안 점수 통합 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="d6d2a-222">Enable or disable Secure Score integration</span></span>

1. <span data-ttu-id="d6d2a-223">수정할 작업의 줄임표 (...)를 선택 하 고 **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-223">Select the ellipses (…) for the Action you want to modify and select **Edit**.</span></span>
2. <span data-ttu-id="d6d2a-224">보안 점수를 통한 지속적인 모니터링을 사용 하거나 사용 하지 않도록 설정 하려면 안전한 점수 연속 업데이트에 대 한 스위치를 설정 또는 해제로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-224">Toggle the switch for Secure Score continuous update to On or Off to enable or disable continuous monitoring through Secure Score.</span></span>
3. <span data-ttu-id="d6d2a-225">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-225">Select **Save**.</span></span>

<span data-ttu-id="d6d2a-226">조직에서 Microsoft 365 또는 Office 365을 처음 배포할 때는 보안 점수가 약 7 일 정도 소요 되어 데이터를 완벽 하 게 수집 하 고 해당 점수를 파악 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-226">When organizations first deploy Microsoft 365 or Office 365, it takes approximately seven days for Secure Score to fully collect data and factor it into your score.</span></span> <span data-ttu-id="d6d2a-227">이 시간 동안에는 보안 점수 연속 업데이트 스위치를 **Off** 로 설정 하 고, 수동으로 작업을 수행 하도록 **설정 하면 점수를 받을 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-227">During that time, setting the Secure Score continuous update switch to **Off** and manually setting an action to **implemented** will count that action toward your score.</span></span> <span data-ttu-id="d6d2a-228">초기 7 일이 지나면 보안 점수 연속 업데이트를 다시 설정 하면 해당 시점부터의 지속적인 모니터링이 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-228">After the initial seven days, turning Secure Score continuous update back on will enable continuous monitoring from that point forward.</span></span>

<span data-ttu-id="d6d2a-229">보안 점수 통합에서 지원 되지 않는 모든 작업은 수동으로 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-229">Any actions that are not supported by Secure Score integration can be manually implemented.</span></span> <span data-ttu-id="d6d2a-230">수동 구현은 해당 작업 그룹의 점수를 발생 시키는 기능을 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-230">A manual implementation will factor into the score for that action's group.</span></span>

#### <a name="add-a-customer-action"></a><span data-ttu-id="d6d2a-231">고객 작업 추가</span><span class="sxs-lookup"><span data-stu-id="d6d2a-231">Add a customer action</span></span>

1. <span data-ttu-id="d6d2a-232">**+ Customer 추가 작업**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-232">Select **+ Add Customer Action**.</span></span>
2. <span data-ttu-id="d6d2a-233">**제목** 필드에 작업에 대 한 고유한 제목을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-233">Provide a unique title for the Action in the **Title** field.</span></span>
3. <span data-ttu-id="d6d2a-234">**최대 준수 점수** 필드에 작업에 대 한 준수 점수를 제공 합니다 (이 값은 1-99에서 숫자가 될 수 있음).</span><span class="sxs-lookup"><span data-stu-id="d6d2a-234">Provide a Compliance Score for the Action in the **Maximum Compliance Score** field (this can be any number from 1-99).</span></span>
4. <span data-ttu-id="d6d2a-235">**작업 유형** 드롭다운을 사용 하 여 추가 하려는 작업의 유형을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-235">Use the **Action Type** dropdown to specify the type of Action you are adding.</span></span> <span data-ttu-id="d6d2a-236">동작 유형이 없는 경우 작업 유형 차원 키에 값을 추가 하 여 해당 유형을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-236">If the Action Type does not exist, you can add it by adding the value to the Action Type dimension key.</span></span>
5. <span data-ttu-id="d6d2a-237">**차원** 드롭다운을 사용 하 여 작업에 대해 차원 키와 값을 지정 하거나 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-237">Use the **Dimensions** dropdown to specify or add dimension keys and values for the Action.</span></span>
6. <span data-ttu-id="d6d2a-238">**소유자** 드롭다운을 사용 하 여 작업의 소유자를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-238">Use the **Owner** dropdown to specify the owner for Action.</span></span>
7. <span data-ttu-id="d6d2a-239">작업 **+** 에 대 한 설명 및 설명 제목을 추가 하려면 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-239">Select **+** to add a description and description title for the Action.</span></span>
8. <span data-ttu-id="d6d2a-240">**X** 를 선택 하 여 설명 블레이드를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-240">Select the **X** to close the Description blade.</span></span>
9. <span data-ttu-id="d6d2a-241">**저장** 을 선택 하 여 고객 작업을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-241">Select **Save** to save the Customer Action.</span></span>

#### <a name="delete-a-customer-action"></a><span data-ttu-id="d6d2a-242">고객 작업 삭제</span><span class="sxs-lookup"><span data-stu-id="d6d2a-242">Delete a customer action</span></span>

1. <span data-ttu-id="d6d2a-243">수정할 작업의 줄임표 (...)를 선택 하 고 **삭제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-243">Select the ellipses (…) for the Action you want to modify and select **Delete**.</span></span>
2. <span data-ttu-id="d6d2a-244">확인 메시지가 표시 되 면 **삭제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-244">When the confirmation message appears, select **Delete**.</span></span>

## <a name="assessments"></a><span data-ttu-id="d6d2a-245">평가가</span><span class="sxs-lookup"><span data-stu-id="d6d2a-245">Assessments</span></span>

### <a name="add-an-assessment"></a><span data-ttu-id="d6d2a-246">평가 추가</span><span class="sxs-lookup"><span data-stu-id="d6d2a-246">Add an Assessment</span></span>
  
1. <span data-ttu-id="d6d2a-247">평가 대시보드에서 **+ 평가 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-247">In the Assessments dashboard, select **+ Add Assessment**.</span></span>

2. <span data-ttu-id="d6d2a-248">블레이드가 열리면 다음 정보를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-248">When the blade opens, enter the following information:</span></span>

    - <span data-ttu-id="d6d2a-249">**제목 (필수):** 평가의 제목 입력</span><span class="sxs-lookup"><span data-stu-id="d6d2a-249">**Title (required):** Enter a title for your Assessment</span></span>
    - <span data-ttu-id="d6d2a-250">**서식 파일을 선택 하세요 (필수).** 표준 또는 사용자 지정 서식 파일 선택</span><span class="sxs-lookup"><span data-stu-id="d6d2a-250">**Please select a template (required):** Select a standard or custom template</span></span>
    - <span data-ttu-id="d6d2a-251">**그룹을 선택 하거나 새 그룹을 추가 하세요 (필수).** 기존 그룹을 선택 하거나 새 그룹 추가를 선택 하 고 고유한 그룹 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-251">**Please select a group or add a new group (required):** Select an existing group or choose to add a new group, and provide a unique group name</span></span>
    - <span data-ttu-id="d6d2a-252">**기존 그룹에서 데이터를 복사 하 시겠습니까? (선택 사항):** 컨트롤을 전환 하 여 그룹 복사본을 사용 하도록 설정 하 고 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-252">**Would you like to copy the data from an existing group? (optional):** Toggle the control to enable group copy and then:</span></span>
        - <span data-ttu-id="d6d2a-253">**그룹을 선택 합니다 (선택 사항).** 그룹 복사본을 사용 하도록 설정 된 경우 복사할 그룹을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-253">**Select a group (optional):** If group copy is enabled, select the group to copy from</span></span>
            - <span data-ttu-id="d6d2a-254">**구현 세부 정보 (선택 사항):** 구현 세부 정보를 새 그룹으로 복사 하려면 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-254">**Implementation Details (optional):** Select to copy implementation details to the new group</span></span>
            - <span data-ttu-id="d6d2a-255">**테스트 계획 & 추가 정보 (선택 사항):** 테스트 계획 및 추가 정보 세부 정보를 새 그룹에 복사 하려면 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-255">**Test plan & additional information (optional):** Select to copy test plan and additional information details to the new group</span></span>
            - <span data-ttu-id="d6d2a-256">**문서 (선택 사항):** 문서를 새 그룹으로 복사 하려면 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-256">**Documents (optional):** Select to copy documents to the new group</span></span>

3. <span data-ttu-id="d6d2a-257">**저장** 을 선택 하 여 평가를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-257">Select **Save** to create the Assessment.</span></span>

 <span data-ttu-id="d6d2a-258">평가 대시보드에 새 평가가 나타나고 다음 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-258">The new Assessment appears on the Assessment dashboard and displays the following information:</span></span>

- <span data-ttu-id="d6d2a-259">평가의 제목입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-259">The title of the Assessment.</span></span>
- <span data-ttu-id="d6d2a-260">인증, 환경 및 평가에 적용 된 제품을 포함 하는 평가 차원입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-260">The dimensions of the Assessment, including certification, environment, and product applied to the Assessment.</span></span>
- <span data-ttu-id="d6d2a-261">만들어진 날짜 및 마지막으로 수정한 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-261">The date it was created and date when it was last modified.</span></span>
- <span data-ttu-id="d6d2a-262">평가 점수가 백분율로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-262">The Assessment Score shown as a percentage.</span></span> <span data-ttu-id="d6d2a-263">이 점수에는 Microsoft에서 관리 하는 컨트롤의 점수와 보안 점수가 자동으로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-263">This score automatically includes your scores from Microsoft-managed controls and from Secure Score.</span></span>
- <span data-ttu-id="d6d2a-264">평가 된 Microsoft 관리 및 고객 manged 컨트롤 수를 보여 주는 진행률 표시기입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-264">Progress indicators that show the number of assessed Microsoft-managed and customer-manged controls.</span></span>

### <a name="copying-information-from-existing-assessments"></a><span data-ttu-id="d6d2a-265">기존 평가의 정보 복사</span><span class="sxs-lookup"><span data-stu-id="d6d2a-265">Copying information from existing Assessments</span></span>

<span data-ttu-id="d6d2a-266">평가를 만들 때 기존 그룹에서 정보를 복사할 수 있는 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-266">When you create an Assessment, you have the option to copy information from an existing group.</span></span> <span data-ttu-id="d6d2a-267">이렇게 하면 복사 된 평가에 입력 한 정보를 새 평가의 동일한 컨트롤에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-267">This allows you to apply the information entered into the copied assessment to the same controls in the new Assessment.</span></span> <span data-ttu-id="d6d2a-268">예를 들어 조직에서 모든 FFIEC 관련 평가에 대 한 그룹을 사용 하는 경우 기존 평가에서 다음 정보를 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-268">For example, if you have a group for all FFIEC-related Assessments in your organization, you can copy the following information from existing assessments:</span></span>

- <span data-ttu-id="d6d2a-269">구현 세부 정보</span><span class="sxs-lookup"><span data-stu-id="d6d2a-269">Implementation Details</span></span>
- <span data-ttu-id="d6d2a-270">테스트 계획 & 추가 정보</span><span class="sxs-lookup"><span data-stu-id="d6d2a-270">Test Plan & Additional Information</span></span>
- <span data-ttu-id="d6d2a-271">문서</span><span class="sxs-lookup"><span data-stu-id="d6d2a-271">Documents</span></span>

#### <a name="copy-information-from-an-existing-assessment-to-a-new-assessment"></a><span data-ttu-id="d6d2a-272">기존 평가에서 새 평가로 정보를 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-272">Copy information from an existing Assessment to a new Assessment</span></span>
  
1. <span data-ttu-id="d6d2a-273">평가 대시보드에서 **+ 평가 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-273">In the Assessment dashboard, select **+ Add Assessment**.</span></span>
    
2. <span data-ttu-id="d6d2a-274">**평가 추가** 창에서 다음 정보를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-274">In the **Add an Assessment** window, complete the following information</span></span>

    - <span data-ttu-id="d6d2a-275">**제목 (필수):** 평가 제목을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-275">**Title (required):** Enter a title for your Assessment.</span></span>
    - <span data-ttu-id="d6d2a-276">**서식 파일을 선택 하세요 (필수).** 표준 또는 사용자 지정 서식 파일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-276">**Please select a template (required):** Select a standard or custom template.</span></span>
    - <span data-ttu-id="d6d2a-277">**그룹을 선택 하거나 새 그룹을 추가 하세요 (필수).** **새 그룹 추가** 를 선택 하 고 고유한 그룹 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-277">**Please select a group or add a new group (required):** Choose **Add a new group** and provide a unique group name.</span></span>
    - <span data-ttu-id="d6d2a-278">**기존 그룹에서 데이터를 복사 하 시겠습니까? (선택 사항):** 그룹 복사본을 사용 하도록 설정 하려면 컨트롤을 설정/해제 하 고 다음을 **선택 합니다 (선택 사항).** 그룹 복사가 사용 하도록 설정 된 경우 복사할 그룹을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-278">**Would you like to copy the data from an existing group? (optional):** Toggle the control to On to enable group copy and then: - **Select a group (optional):** If group copy is enabled, select the group to copy from.</span></span>
            <span data-ttu-id="d6d2a-279">- **구현 세부 정보 (선택 사항):** 구현 세부 정보를 새 그룹으로 복사 하려면 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-279">- **Implementation Details (optional):** Select to copy implementation details to the new group.</span></span>
            <span data-ttu-id="d6d2a-280">- **테스트 계획 & 추가 정보 (선택 사항):** 테스트 계획 및 추가 정보 세부 정보를 새 그룹에 복사 하려면 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-280">- **Test plan & additional information (optional):** Select to copy test plan and additional information details to the new group.</span></span>
            <span data-ttu-id="d6d2a-281">- **문서 (선택 사항):** 문서를 새 그룹으로 복사 하려면 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-281">- **Documents (optional):** Select to copy documents to the new group.</span></span>

3. <span data-ttu-id="d6d2a-282">**저장** 을 선택 하 여 평가를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-282">Select **Save** to create the Assessment.</span></span>

### <a name="view-an-assessment"></a><span data-ttu-id="d6d2a-283">평가 보기</span><span class="sxs-lookup"><span data-stu-id="d6d2a-283">View an Assessment</span></span>
  
1. <span data-ttu-id="d6d2a-284">평가 대시보드에서 평가 이름을 선택 하 여 열고 작업 항목 및 컨트롤 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-284">In the Assessments dashboard, select the assessment name to open it and view the Action Items and Controls Info.</span></span>

<span data-ttu-id="d6d2a-285">다음은 Office 365 및 ISO 27001에 대 한 평가의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-285">Here's an example of the Assessment for Office 365 and ISO 27001.</span></span> <span data-ttu-id="d6d2a-286">첫 번째 보기는 준수 관리자 (미리 보기)의 새 작업 항목 보기를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-286">The first view illustrates the new Action Items view in Compliance Manager (Preview).</span></span>

![준수 관리자 작업 항목 보기](media/compliance-manager-action-items.png)

<span data-ttu-id="d6d2a-288">작업은 사전순으로 나열 되며 각 작업에는 점수와 소유자가 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-288">The Actions are listed in alphabetical order, and each Action is assigned a score and an owner.</span></span> <span data-ttu-id="d6d2a-289">**자세히 읽기** 링크를 선택 하 여 각 작업의 세부 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-289">Select  the **Read More** link to read the details of each Action.</span></span> 

![준수 관리자 작업 항목 보기](media/compliance-manager-actions-read-more.png)

<span data-ttu-id="d6d2a-291">**검토** 링크를 선택 하 여 작업을 관리, 할당, 구현 및 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-291">Select the **Review** link to manage, assign, implement, and test the action.</span></span> <span data-ttu-id="d6d2a-292">예제 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-292">Below is an example Action.</span></span>

![준수 관리자 작업 보기](media/compliance-manager-action.png)

<span data-ttu-id="d6d2a-294">이전 버전의 준수 관리자에서 요구 사항을 구현 하기 위한 워크플로는 제어 수준에서 수행 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-294">In previous versions of Compliance Manager, the workflow for implementing requirements was performed at the Control level.</span></span> <span data-ttu-id="d6d2a-295">규정 준수 책임자는 컨트롤을 구현할 컨트롤을 다른 사람에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-295">A compliance officer would assign a control to someone to implement the control.</span></span> <span data-ttu-id="d6d2a-296">다음과 같은 두 가지 단점이 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-296">There were two drawbacks to this:</span></span>

- <span data-ttu-id="d6d2a-297">컨트롤에 여러 동작이 연결 되어 있고, 컨트롤이 할당 된 사용자가 컨트롤을 구현 하는 데 필요한 모든 작업을 완료 하지 못할 수도 있는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-297">Controls often had multiple actions associated with them, and the user to whom a control was assigned, might not be the right person to complete all actions that were required to implement the control</span></span>
- <span data-ttu-id="d6d2a-298">개별 작업을 단일 작업으로 결합 하면 준수 관리자 (미리 보기)에서 테 넌 트 구성 변경 내용을 자동으로 기록 하는 데 사용 되는 신호 및 원격 분석을 수집할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-298">Combining separate tasks into a single Action prevented the collection of the signals and telemetry that is used to automatically record tenant configuration changes in Compliance Manager (Preview).</span></span>

<span data-ttu-id="d6d2a-299">준수 관리자 (미리 보기)에서 워크플로 프로세스는 컨트롤 수준에서 작업 수준으로 이동 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-299">In Compliance Manager (Preview), the workflow process has moved from the Control level to the Action level.</span></span> <span data-ttu-id="d6d2a-300">작업을 검토할 때 작업 워크플로를 관리 하는 데 사용할 수 있는 필드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-300">When reviewing an Action, the following fields can be used to manage the Action workflow:</span></span>

- <span data-ttu-id="d6d2a-301">**사용자 할당:** 이 필드를 선택 하 여이 동작을 할당할 사용자를 선택 하거나 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-301">**Assign User:** Select this field to choose or enter the user to whom this Action should be assigned.</span></span> <span data-ttu-id="d6d2a-302">목록을 스크롤하거나 이름을 입력 하 여 찾은 다음 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-302">You can scroll through the list, or type a name to find it, and then select it.</span></span>
- <span data-ttu-id="d6d2a-303">**문서 관리:** 구현 증거를 Office 문서, 이미지 파일 및 스크린샷, PowerShell 출력을 CSV 또는 TXT로 업로드 하 고 Pdf로 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-303">**Manage Documents:** You can upload evidence of implementation in the form of Office documents, image files and screenshots, PowerShell output in CSV or TXT, and PDFs.</span></span>
- <span data-ttu-id="d6d2a-304">**구현 상태:** 작업의 현재 구현 상태를 나타내는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-304">**Implementation Status:** Used to indicate the Action’s current implementation status.</span></span> <span data-ttu-id="d6d2a-305">가능한 값은 범위에서 구현, 구현, 대체 구현, 계획 됨 및 그렇지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-305">Possible values are Not Implemented, Implemented, Alternative Implementation, Planned, and Not in Scope.</span></span>
- <span data-ttu-id="d6d2a-306">**구현 날짜:** 작업을 수행한 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-306">**Implementation Date:** The date on which the Action was taken.</span></span>
- <span data-ttu-id="d6d2a-307">**테스트 결과:** 구현 유효성 검사의 결과를 표시 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-307">**Test Result:** Used to indicate the results of implementation validation.</span></span> <span data-ttu-id="d6d2a-308">가능한 값은 평가, 성공, 실패-낮은 위험, 실패-보통 위험, 실패-높은 위험, 장애 되지 않음 및 범위에 속하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-308">Possible values are Not Assessed, Passed, Failed-Low Risk, Failed-Medium Risk, Failed-High Risk, and Not in Scope.</span></span>
- <span data-ttu-id="d6d2a-309">**테스트 날짜:** 유효성 검사가 발생 한 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-309">**Test Date:** The date on which validation occurred.</span></span>
- <span data-ttu-id="d6d2a-310">**구현 참고 사항:** 포함 하려는 메모와 함께 조직의 구현 세부 정보를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-310">**Implementation Notes:** Enter implementation details for your organization, along with any notes that you want to include.</span></span>
- <span data-ttu-id="d6d2a-311">**테스트 계획:** 포함 하려는 메모와 함께이 작업에 대 한 테스트 계획 세부 정보를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-311">**Test Plan:** Enter the test plan details for this action, along with any notes that you want to include.</span></span>
- <span data-ttu-id="d6d2a-312">**추가 정보:** 포함 하려는 메모와 함께이 작업에 대 한 추가 정보나 조직에서 구현 된 방식을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-312">**Additional Information:** Enter any additional information about this Action or how it was implemented in your organization, along with any notes you want to include.</span></span>

<span data-ttu-id="d6d2a-313">준수 관리자 (미리 보기)에는 이전 버전에서 찾은 컨트롤 기반 피벗도 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-313">Compliance Manager (Preview) also includes the control-based pivot found in previous versions.</span></span> <span data-ttu-id="d6d2a-314">**컨트롤 정보** 대시보드를 선택 하 여 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-314">Select the **Controls Info** dashboard to view it.</span></span> <span data-ttu-id="d6d2a-315">평가 및 템플릿 수준에서 컨트롤에 대 한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-315">You can view information for controls at the Assessment and Template level.</span></span> <span data-ttu-id="d6d2a-316">다음은 평가를 위한 컨트롤 정보 대시보드의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-316">Below is an example of the Controls Info dashboard for Assessments.</span></span>

![준수 관리자 컨트롤 정보 보기](media/compliance-manager-controls-info.png)

<span data-ttu-id="d6d2a-318">평가의 경우 컨트롤 정보 대시보드가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-318">For Assessments, the Controls Info dashboard displays:</span></span>

- <span data-ttu-id="d6d2a-319">**그룹** 드롭다운-보려는 그룹을 선택 합니다 (여러 그룹을 사용 하는 경우).</span><span class="sxs-lookup"><span data-stu-id="d6d2a-319">A **Group** dropdown to select which Group to view (when using multiple groups).</span></span>
- <span data-ttu-id="d6d2a-320">확인할 평가를 선택 하는 **평가** 드롭다운입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-320">An **Assessment** dropdown to select which Assessment to view.</span></span>
- <span data-ttu-id="d6d2a-321">다음을 포함 하 여 선택한 평가에 대 한 메타 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-321">Metadata about the selected Assessment, including:</span></span>
    - <span data-ttu-id="d6d2a-322">전체 컨트롤 수에 대 한 평가 컨트롤 수를 보여 주는 **평가 컨트롤** 의 진행률 표시기입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-322">A progress indicator for **Assessed Controls** showing the number of assessed controls over the total number of controls.</span></span>
    - <span data-ttu-id="d6d2a-323">평가에 대 한 현재 **준수 점수** 이며 백분율로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-323">The current **Compliance Score** for the Assessment, shown as a percentage.</span></span>
    - <span data-ttu-id="d6d2a-324">평가에 사용 되는 **인증** 및 **제품** 에 대 한 세부 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-324">Details about the **Certification** and **Product** used in the Assessment.</span></span>
    - <span data-ttu-id="d6d2a-325">평가의 현재 **상태** 및 마지막으로 **수정한** 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-325">The current **Status** of and last **Modified** date for the Assessment.</span></span>
- <span data-ttu-id="d6d2a-326">평가에 대 한 **범위 서비스의** 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-326">A list of **In Scope Services** for the Assessment.</span></span>
- <span data-ttu-id="d6d2a-327">고객 작업에 대 한 링크 및 Microsoft 구현 세부 정보를 포함 하는 컨트롤에 대 한 세부 정보 (컨트롤 패밀리가 그룹화 됨)</span><span class="sxs-lookup"><span data-stu-id="d6d2a-327">Details of the controls, grouped by Control Family, with links to customer actions and Microsoft implementation details:</span></span>
    - <span data-ttu-id="d6d2a-328">이 **작업** 을 수행 하면 일부 또는 모든 컨트롤의 요구 사항을 충족 하기 위해 수행할 수 있는 고객 작업이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-328">**Your Actions** displays the customer actions that you can perform to satisfy some or all the control’s requirements.</span></span> <span data-ttu-id="d6d2a-329">대부분의 컨트롤에는 여러 개의 동작이 연결 되어 있으며, 컨트롤에 연결 된 모든 동작이 여기에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-329">Many controls have multiple Actions associated with them, and all Actions associated with a control are displayed here.</span></span> <span data-ttu-id="d6d2a-330">여기에 나와 있는 작업은 Actions 대시보드에 나열 된 것과 같은 UI를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-330">The Actions here have the same UI as those listed in the Actions dashboard.</span></span>
    - <span data-ttu-id="d6d2a-331">**Microsoft Actions** 는 선택한 인증 컨트롤에 적용 되는 microsoft 내부 프레임 워크의 컨트롤 목록을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-331">**Microsoft Actions** displays the list of controls from Microsoft’s internal framework that apply to the selected certification control.</span></span> <span data-ttu-id="d6d2a-332">각 내부 컨트롤에 대해 아래와 같이 테스트 결과 및 테스트 날짜와 함께 Microsoft의 구현 및 테스트 세부 정보를 보려면 **구현** 됨을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-332">For each internal control, select **Implemented** to see Microsoft’s implementation and test details, along with the test result and test date, as shown below.</span></span>

![준수 관리자 Microsoft 작업 보기](media/compliance-manager-microsoft-action.png)

### <a name="export-an-assessment"></a><span data-ttu-id="d6d2a-334">평가 내보내기</span><span class="sxs-lookup"><span data-stu-id="d6d2a-334">Export an Assessment</span></span>

<span data-ttu-id="d6d2a-335">조직의 규정 준수 관계자 또는 외부 감사자 및 조정기에 대 한 Excel 파일에 대 한 평가를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-335">You can export an Assessment to an Excel file for compliance stakeholders in your organization or for external auditors and regulators.</span></span> <span data-ttu-id="d6d2a-336">보고서는 보고서가 만들어진 날짜 및 시간을 평가 하는 스냅숏입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-336">The report is a snapshot of the Assessment as of the date and time that the report is created.</span></span> <span data-ttu-id="d6d2a-337">이 보고서에는 평가, 컨트롤 구현 상태, 컨트롤 테스트 날짜 및 테스트 결과에 대 한 모든 Microsoft 및 고객 관리 컨트롤에 대 한 세부 정보 및 업로드 된 증거 문서에 대 한 링크를 제공 하는 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-337">The report contains the details for all Microsoft and customer-managed controls for the Assessment, control implementation status, control test date, test results, and provides links to uploaded evidence documents.</span></span> <span data-ttu-id="d6d2a-338">보관 된 평가는 업로드 한 문서에 대 한 링크를 보존 하지 않으므로 평가 보고서를 보관 하기 전에이를 내보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-338">You should export the Assessment report prior to archiving an assessment because archived assessments do not retain links to uploaded documents.</span></span>
  
### <a name="export-an-assessment-report"></a><span data-ttu-id="d6d2a-339">평가 보고서 내보내기</span><span class="sxs-lookup"><span data-stu-id="d6d2a-339">Export an Assessment report</span></span>
  
1. <span data-ttu-id="d6d2a-340">준수 관리자 대시보드에서 **컨트롤 정보** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-340">On the Compliance Manager dashboard, select **Controls Info** tab.</span></span>
2. <span data-ttu-id="d6d2a-341">내보내려는 평가의 드롭다운 메뉴에서 **그룹** 및 **평가** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-341">Select the **Group** and **Assessment** in the drop-down menus for the Assessment you want to export.</span></span>
3. <span data-ttu-id="d6d2a-342">**내보내기** 단추를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-342">Select the **Export** button.</span></span>

<span data-ttu-id="d6d2a-343">평가 보고서는 브라우저 세션에서 Excel 파일로 다운로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-343">The assessment report is downloaded as an Excel file in your browser session.</span></span> <span data-ttu-id="d6d2a-344">Excel 파일의 파일 이름은 기본적으로 평가의 제목에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-344">The files name for the Excel file defaults to the title of the Assessment.</span></span>

### <a name="hide-a-template-or-an-assessment"></a><span data-ttu-id="d6d2a-345">서식 파일 또는 평가 숨기기</span><span class="sxs-lookup"><span data-stu-id="d6d2a-345">Hide a Template or an Assessment</span></span>

<span data-ttu-id="d6d2a-346">템플릿이나 평가가 완료 되 고 더 이상 규정을 준수 하기 위해 필요 하지 않은 경우 보기에서 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-346">When you are finished with a Template or Assessment and no longer need it for compliance purposes, you can hide it from your view.</span></span> <span data-ttu-id="d6d2a-347">서식 파일 또는 평가를 숨기면 기본 보기에서 제거 되며이를 표시 하려면 **숨김 확인란 포함** 을 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-347">When a Template or Assessment is hidden, it is removed from the default view, and you must select **Include Hidden** checkbox to display it.</span></span>

<span data-ttu-id="d6d2a-348">![준수 관리자의 템플릿 보기 숨김](media/compliance-manager-hidden-template.png "준수 관리자 숨김 서식 파일")</span><span class="sxs-lookup"><span data-stu-id="d6d2a-348">![Compliance Manager Hidden Template View](media/compliance-manager-hidden-template.png "Compliance Manager hidden template")</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d6d2a-349">숨겨진 평가에서는 업로드 된 증거 문서에 대 한 링크를 유지 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-349">Hidden Assessments do not retain their links to uploaded evidence documents.</span></span> <span data-ttu-id="d6d2a-350">보고서의 증거 문서에 대 한 링크를 보존 하기 위해 숨기기 전에 평가를 내보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-350">It is highly recommended that you export the Assessment before hiding it to retain links to the evidence documents in the report.</span></span>
  
#### <a name="hiding-a-template"></a><span data-ttu-id="d6d2a-351">서식 파일 숨기기</span><span class="sxs-lookup"><span data-stu-id="d6d2a-351">Hiding a Template</span></span>

1. <span data-ttu-id="d6d2a-352">**서식 파일** 대시보드를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-352">Open the **Templates** dashboard.</span></span>
2. <span data-ttu-id="d6d2a-353">숨기려는 서식 파일을 찾은 다음 해당 행의 줄임표에서 **숨기기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-353">Locate the Template you want to hide and at the ellipses in its row, select **Hide**.</span></span>
3. <span data-ttu-id="d6d2a-354">확인 메시지가 표시 되 면 **숨기기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-354">When you see the confirmation message, select **Hide**.</span></span>

#### <a name="hide-an-assessment"></a><span data-ttu-id="d6d2a-355">평가 숨기기</span><span class="sxs-lookup"><span data-stu-id="d6d2a-355">Hide an Assessment</span></span>

1. <span data-ttu-id="d6d2a-356">**평가** 대시보드를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-356">Open the **Assessments** dashboard.</span></span>
2. <span data-ttu-id="d6d2a-357">숨기려는 평가가 포함 된 드롭다운 목록에서 **그룹** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-357">Select the **Group** from the dropdown that contains the Assessment you want to hide.</span></span>
3. <span data-ttu-id="d6d2a-358">숨기려는 평가를 찾고 타원에서 **숨기기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-358">Locate the Assessment you want to hide and at the ellipses, select **Hide**.</span></span>
4. <span data-ttu-id="d6d2a-359">확인 메시지가 표시 되 면 **숨기기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-359">When you see the confirmation message, select **Hide**.</span></span>

#### <a name="view-hidden-assessments"></a><span data-ttu-id="d6d2a-360">숨겨진 평가 보기</span><span class="sxs-lookup"><span data-stu-id="d6d2a-360">View hidden Assessments</span></span>
  
1. <span data-ttu-id="d6d2a-361">**평가** 대시보드 탭을 열고 **숨김 포함** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-361">Open the **Assessments** dashboard tab and select the **Include Hidden** checkbox.</span></span>
2. <span data-ttu-id="d6d2a-362">숨겨진 평가가 **숨겨진 평가** 섹션에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-362">The hidden assessments appear in the **Hidden Assessments** section.</span></span>

#### <a name="unhide-an-assessment"></a><span data-ttu-id="d6d2a-363">평가 숨기기 취소</span><span class="sxs-lookup"><span data-stu-id="d6d2a-363">Unhide an Assessment</span></span>

1. <span data-ttu-id="d6d2a-364">**평가** 탭에서 **숨김 확인란 포함** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-364">On the **Assessments** tab, select the **Include Hidden** checkbox.</span></span>
2. <span data-ttu-id="d6d2a-365">숨겨진 평가가 **숨겨진 평가** 섹션에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-365">The hidden assessments appear in the **Hidden Assessments** section.</span></span>
3. <span data-ttu-id="d6d2a-366">숨김을 취소할 평가를 찾고 타원에서 **숨기기 취소**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-366">Locate the Assessment you want to unhide and at the ellipses, select **Unhide**.</span></span>
4. <span data-ttu-id="d6d2a-367">확인 메시지가 표시 되 면 **숨기기 취소**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-367">When you see the confirmation message, select **Unhide**.</span></span>

## <a name="controls-and-actions"></a><span data-ttu-id="d6d2a-368">컨트롤 및 작업</span><span class="sxs-lookup"><span data-stu-id="d6d2a-368">Controls and Actions</span></span>

<span data-ttu-id="d6d2a-369">컨트롤 및 작업은 준수 관리자 (미리 보기)에서 사용 되는 기본 데이터 피벗입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-369">Controls and Actions are the primary data pivots used in Compliance Manager (Preview).</span></span> <span data-ttu-id="d6d2a-370">이전 버전의 준수 관리자에 있던 컨트롤 피벗은 동일한 제어 패밀리에서 Microsoft 및 고객 컨트롤을 표시 하도록 향상 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-370">The Control pivot, which existed in previous versions of Compliance Manager, has been enhanced to show the Microsoft and customer controls in the same control families.</span></span> <span data-ttu-id="d6d2a-371">이 통합 보기를 사용 하면 전체 공유 책임 모델을 각 컨트롤 별로 쉽게 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-371">This consolidated view makes it easier to see the complete shared responsibility model on a per-control basis.</span></span> <span data-ttu-id="d6d2a-372">Pivot Action은 준수 관리자의 새로운 기능 (미리 보기) 이며 Microsoft에서 권장 하는 모든 작업을 효율적으로 확인할 수 있도록 디자인 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-372">The Action pivot is new in Compliance Manager (Preview) and it is designed to provide a streamlined view of all of actions recommended by Microsoft.</span></span>

### <a name="controls"></a><span data-ttu-id="d6d2a-373">컨트롤</span><span class="sxs-lookup"><span data-stu-id="d6d2a-373">Controls</span></span>

<span data-ttu-id="d6d2a-374">컨트롤은 Controls Info 대시보드에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-374">Controls can be viewed from the Controls Info dashboard.</span></span> <span data-ttu-id="d6d2a-375">컨트롤은 표준, 인증, 규정 또는 프레임 워크의 요구 사항을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-375">Controls represent the requirements from a standard, certification, regulation, or framework.</span></span> <span data-ttu-id="d6d2a-376">이러한 요구 사항을 여러 표준, 규정 등으로 매핑하고,이를 작업에 연결 하려면 모든 항목이 컨트롤 프레임 워크 처럼 취급 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-376">To map these requirements across multiple standards, regulations, etc., and to associate them with Actions, everything is treated as if it were a control framework.</span></span> <span data-ttu-id="d6d2a-377">예를 들어 제어 프레임 워크와 같이 HIPAA와 같은 규정은 다음과 같이 섹션 별로 구분 되며 준수 관리자의 HIPAA 컨트롤은 아래와 같은 번호 매기기 체계를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-377">For example, like a control framework, regulations, such as HIPAA, have been broken down by section, and the HIPAA controls in Compliance Manager use the same numbering scheme as those sections, as shown below:</span></span>

![규정 준수 관리자 Microsoft 컨트롤 세부 정보](media/compliance-manager-control-details.png)

<span data-ttu-id="d6d2a-379">컨트롤에는 다음과 같은 세 가지 유형이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-379">There are three types of controls:</span></span>

1. <span data-ttu-id="d6d2a-380">**Microsoft 관리 컨트롤:** microsoft만 책임 지는 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-380">**Microsoft-managed controls:** these are controls for which only Microsoft has responsibility.</span></span> <span data-ttu-id="d6d2a-381">이러한 사용자는 box 서식 파일에 나타나며 Microsoft의 준수 관리자에 게 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-381">They appear in the in-box Templates and are added to Compliance Manager by Microsoft.</span></span>
2. <span data-ttu-id="d6d2a-382">**고객 관리 컨트롤:** 고객 에게만 책임을 지는 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-382">**Customer-managed controls:** these are controls for which only customers have responsibility.</span></span> <span data-ttu-id="d6d2a-383">이러한 사용자는 내 서식 파일에 나타나며 고객이 준수 관리자에 게 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-383">They appear in the in-box Templates and are added to Compliance Manager by customers.</span></span>
3. <span data-ttu-id="d6d2a-384">**공유 관리 컨트롤:** Microsoft와 고객 간에 책임을 공유 하는 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-384">**Shared management controls:** these are controls where responsibility is shared between Microsoft and the customer.</span></span> <span data-ttu-id="d6d2a-385">이러한 파일은 in box 템플릿에 나타나며 Microsoft의 준수 관리자에 게 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-385">These appear in the in-box Templates and are added to Compliance Manager by Microsoft.</span></span> <span data-ttu-id="d6d2a-386">고객은 Microsoft 관리 컨트롤을 편집 하거나 사용 하지 않도록 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-386">The customer can also edit or disable Microsoft-managed controls.</span></span>

### <a name="actions-items"></a><span data-ttu-id="d6d2a-387">작업 항목</span><span class="sxs-lookup"><span data-stu-id="d6d2a-387">Actions Items</span></span>

<span data-ttu-id="d6d2a-388">작업 항목은 표준 또는 규제 요구 사항을 구현 하는 데 권장 되는 작업 이거나 조직의 구현 요구 사항을 테스트, 확인 및 문서화 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-388">Actions Items are the recommended tasks for implementing the requirements of a standard or regulation, or to test, verify, and document your organization's implementation requirements.</span></span> <span data-ttu-id="d6d2a-389">작업은 하나 이상의 컨트롤과 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-389">Actions are associated with one or more Controls.</span></span> <span data-ttu-id="d6d2a-390">각 컨트롤에는 하나 이상의 동작이 연결 되어 있으며 각 작업을 하나 이상의 컨트롤에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-390">Each Control has one or more Action associated with it, and each Action can be associated with one or more Controls.</span></span> <span data-ttu-id="d6d2a-391">작업은 조직에서 할당 하 고 추적 하 고 유효성을 검사 하는 개체 이기 때문에 준수 관리자 (미리 보기)의 핵심 워크플로에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-391">Actions are part of the core workflow in Compliance Manager (Preview), as they are the objects that are assigned, tracked, and validated by your organization.</span></span>

#### <a name="assign-action-items"></a><span data-ttu-id="d6d2a-392">작업 항목 할당</span><span class="sxs-lookup"><span data-stu-id="d6d2a-392">Assign Action Items</span></span>
  
1. <span data-ttu-id="d6d2a-393">**작업 항목** 대시보드에서 작업을 할당 하려는 평가를 포함 하는 **그룹** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-393">On the **Action Items** dashboard, select the **Group** containing the Assessment(s) whose Action you want to assign.</span></span>
2. <span data-ttu-id="d6d2a-394">**평가** 드롭다운에서 작업을 할당 하려는 평가를 선택 하거나 드롭다운 목록에서 **모두** 를 선택 하 여 사용 가능한 모든 작업을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-394">In the **Assessment** dropdown, select the Assessment whose Action you want to assign, or select **All** from the dropdown to see all available Actions.</span></span>
3. <span data-ttu-id="d6d2a-395">할당 하려는 작업을 찾은 다음 **소유자** 열에서 **검토**, **구현** 또는 **테스트할**링크를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-395">Locate the Action you want to assign, and in the **Owner** column, select the link for **Review**, **Implemented** or **Test**.</span></span>
4. <span data-ttu-id="d6d2a-396">**사용자 지정** 필드를 선택 하면 조직의 사용자 목록이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-396">Select the **Assign User** field, and a list of users in your organization appear.</span></span> <span data-ttu-id="d6d2a-397">목록을 스크롤하여 사용자 이름에 입력 하 여 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-397">Scroll the list and select user or filter the list to select a user by typing in the user’s name.</span></span>
5. <span data-ttu-id="d6d2a-398">구현 메모 필드에 할당 된 사용자에 게 전달할 메모를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-398">In the Implementation Notes field, enter any notes you wish to convey to the assigned user.</span></span>
6. <span data-ttu-id="d6d2a-399">**저장** 을 선택 하 여 작업을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-399">Select **Save** to assign the Action.</span></span>

#### <a name="reassign-action-items"></a><span data-ttu-id="d6d2a-400">작업 항목 다시 할당</span><span class="sxs-lookup"><span data-stu-id="d6d2a-400">Reassign Action Items</span></span>

<span data-ttu-id="d6d2a-401">이 기능을 사용 하면 조직이 새 사용자에 게 작업을 다시 할당 하 여 사용자 계정에서 활성 또는 미해결 종속성을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-401">This function enables an organization to remove any active or outstanding dependencies on the user account by reassigning an Action to a new user.</span></span>

1. <span data-ttu-id="d6d2a-402">**작업 항목** 대시보드에서 작업을 다시 할당 하려는 평가가 포함 된 **그룹** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-402">On the **Action Items** dashboard, select the **Group** containing the Assessment(s) whose Action you want to reassign.</span></span>
2. <span data-ttu-id="d6d2a-403">**평가** 드롭다운에서 작업을 다시 할당 하려는 평가를 선택 하거나 드롭다운 목록에서 **모두** 를 선택 하 여 사용 가능한 모든 작업을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-403">In the **Assessment** dropdown, select the Assessment whose Action you want to reassign, or select **All** from the dropdown to see all available Actions.</span></span>
3. <span data-ttu-id="d6d2a-404">다시 할당 하려는 작업을 찾은 다음 **소유자** 열에서 **검토**, **구현**또는 **테스트할**링크를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-404">Locate the Action you want to reassign, and in the **Owner** column, select the link for **Review**, **Implemented**, or **Test**.</span></span>
4. <span data-ttu-id="d6d2a-405">**사용자 지정** 필드에서 기존 사용자를 삭제 하 고 사용자 목록에서 다른 사용자를 선택 하거나 목록을 필터링 하 여 사용자 이름에 입력 하 여 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-405">Delete the existing user from the **Assign User** field, and either choose a different user from the list of users or filter the list to select a user by typing in the user’s name.</span></span>
5. <span data-ttu-id="d6d2a-406">구현 메모 필드에 사용자에 게 전달할 메모를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-406">In the Implementation Notes field, enter any notes you wish to convey to the user.</span></span>
6. <span data-ttu-id="d6d2a-407">**저장** 을 선택 하 여 작업을 다시 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-407">Select **Save** to reassign the Action.</span></span>

## <a name="templates"></a><span data-ttu-id="d6d2a-408">템플릿</span><span class="sxs-lookup"><span data-stu-id="d6d2a-408">Templates</span></span>

<span data-ttu-id="d6d2a-409">템플릿은 제품 및 인증 (예: 표준, 규정, 제어 프레임 워크 등)과 관련 된 준수 관리자 (미리 보기)의 기본 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-409">A Template is the base object in Compliance Manager (Preview) that is associated with a Product and a Certification (for example, standard, regulation, control framework, etc.).</span></span> <span data-ttu-id="d6d2a-410">서식 파일 대시보드에서 템플릿을 보고 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-410">Templates can be viewed and added from the Templates dashboard.</span></span>

![준수 관리자 Microsoft 템플릿 대시보드](media/compliance-manager-template-dashboard.png)
 
<span data-ttu-id="d6d2a-412">이 대시보드에는 서식 파일에 연결 된 인증 및 제품과 함께 각 서식 파일이 표시 되며, 서식 파일을 만들고 마지막으로 수정한 날짜, 고객 및 Microsoft가 관리 하는 컨트롤의 수, 사용자의 최대 준수 점수가 서식 파일의 상태 (예: 승인 됨, 승인 보류 중, 가져옴)입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-412">The dashboard displays each Template, along with the Certification and Product associated with the Template, the dates on which the Template was created and last modified, the number of customer and Microsoft-managed controls, the maximum Compliance Score for the Template, and the status of the Template (for example, Approved, Pending Approval, Imported).</span></span>

<span data-ttu-id="d6d2a-413">기본적으로 제공 되는 서식 파일에는 기본적으로 제공 되는 분석 기능이 있지만 기본 제공 서식 파일을 기반으로 하는 추가 평가를 만들 수 있으며, 고유한 서식 파일을 가져오고이를 기반으로 사용자 지정 평가를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-413">The built-in Templates each have a built-in Assessment associated with them, but you can create additional Assessments based on built-in Templates, and you can import your own Templates, and create custom Assessments based off those.</span></span>

### <a name="create-a-template"></a><span data-ttu-id="d6d2a-414">서식 파일 만들기</span><span class="sxs-lookup"><span data-stu-id="d6d2a-414">Create a Template</span></span>

<span data-ttu-id="d6d2a-415">기존 서식 파일을 복사 하거나 사용자 지정 템플릿을 가져와서 서식 파일을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-415">You can create a Template by copying an existing Template or by importing a custom Template.</span></span> <span data-ttu-id="d6d2a-416">서식 파일 데이터에 사용 해야 하는 특정 형식 및 스키마가 있거나 준수 관리자로 가져오지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-416">There is a specific format and schema that must be used for Template data or it will not import into Compliance Manager.</span></span> <span data-ttu-id="d6d2a-417">올바른 스키마 및 예제 데이터를 포함 하는 파일을 여기에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-417">A file with the correct schema and sample data can be downloaded from here.</span></span>
<span data-ttu-id="d6d2a-418">각 사용자 지정 서식 파일은 다섯 개의 탭이 포함 된 별도의 Excel 통합 문서 (.xls 또는 .xlsx 형식)에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-418">Each custom Template should be in a separate Excel workbook (in .xls or .xlsx format) that contains five tabs:</span></span>

1. <span data-ttu-id="d6d2a-419">서식 파일-평가</span><span class="sxs-lookup"><span data-stu-id="d6d2a-419">Template-Assessment</span></span>
2. <span data-ttu-id="d6d2a-420">ControlFamily</span><span class="sxs-lookup"><span data-stu-id="d6d2a-420">ControlFamily</span></span>
3. <span data-ttu-id="d6d2a-421">작업</span><span class="sxs-lookup"><span data-stu-id="d6d2a-421">Actions</span></span>
4. <span data-ttu-id="d6d2a-422">소유권</span><span class="sxs-lookup"><span data-stu-id="d6d2a-422">Ownership</span></span>
5. <span data-ttu-id="d6d2a-423">높이</span><span class="sxs-lookup"><span data-stu-id="d6d2a-423">Dimensions</span></span>

<span data-ttu-id="d6d2a-424">각 탭에서 사용 되는 스키마는 아래에 자세히 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-424">The schema used within each tab is detailed below.</span></span>

#### <a name="template-assessment-tab"></a><span data-ttu-id="d6d2a-425">템플릿-평가 탭</span><span class="sxs-lookup"><span data-stu-id="d6d2a-425">Template-Assessment tab</span></span>

<span data-ttu-id="d6d2a-426">이 탭에는 단일 열이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-426">This tab has a single column:</span></span>

- <span data-ttu-id="d6d2a-427">**inScopeServices**: 서식 파일의 범위 내에 있는 제품 또는 서비스의 쉼표로 구분 된 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-427">**inScopeServices**: Comma-delimited list of products or services that are in-scope for the Template.</span></span>

#### <a name="controlfamily-tab"></a><span data-ttu-id="d6d2a-428">ControlFamily 탭</span><span class="sxs-lookup"><span data-stu-id="d6d2a-428">ControlFamily tab</span></span>

<span data-ttu-id="d6d2a-429">이 탭에는 동작 탭에 나열 된 작업에 매핑되는 컨트롤을 정의 하는 열 및 컨트롤 이름, 패밀리, 제목 및 설명과 같은 세부 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-429">This tab includes columns that define the controls that are mapped to the Actions listed on the Actions tab, and includes details like control name, family, title, and description.</span></span>  <span data-ttu-id="d6d2a-430">아래 나열 된 순서 대로 Excel 내에서 주문 해야 하는이 탭의 열은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-430">The columns for this tab, which must be ordered within Excel in the order listed below, are:</span></span> 

- <span data-ttu-id="d6d2a-431">**Controlname:** 인증/표준/규정의 제어 이름 등</span><span class="sxs-lookup"><span data-stu-id="d6d2a-431">**controlName:** Control name from certification/standard/regulation, etc.</span></span>
- <span data-ttu-id="d6d2a-432">**Controlfamily:** 인증/표준, 규정 등의 제어 패밀리</span><span class="sxs-lookup"><span data-stu-id="d6d2a-432">**controlFamily:** Control family from certification/standard, regulation, etc.</span></span>
- <span data-ttu-id="d6d2a-433">**컨트롤 제목:** 인증/표준/규제의 제어 제목 등</span><span class="sxs-lookup"><span data-stu-id="d6d2a-433">**controlTitle:** Control title from certification/standard/regulation, etc.</span></span>
- <span data-ttu-id="d6d2a-434">**Controldescription:** 인증/표준/규정 등의 제어 설명</span><span class="sxs-lookup"><span data-stu-id="d6d2a-434">**controlDescription:** Control description from certification/standard/regulation, etc.</span></span>
- <span data-ttu-id="d6d2a-435">**Controlversion:** 선택적 컨트롤 버전 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-435">**controlVersion:** Optional control version info.</span></span>  <span data-ttu-id="d6d2a-436">예: NIST 800-53의 경우 현재 값은 Rev 4 이므로 controlVersion은 4입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-436">Example: for NIST 800-53, the current value is Rev 4, so the controlVersion is 4.</span></span>  <span data-ttu-id="d6d2a-437">CSA CCM의 경우에는 3.0.1입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-437">For CSA CCM, it is 3.0.1.</span></span>
- <span data-ttu-id="d6d2a-438">**Isdisabled:** 컨트롤이 사용 하지 않도록 설정 되었는지 여부를 나타내려면 TRUE 또는 FALSE를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-438">**isDisabled:** Use TRUE or FALSE to indicate whether the control has been disabled.</span></span>
- <span data-ttu-id="d6d2a-439">**controlType:** CC를 사용 하 여 고객 관리 되는 컨트롤 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-439">**controlType:** Use CC to indicate these are customer-managed controls.</span></span>
- <span data-ttu-id="d6d2a-440">**controlComplianceScore:** 컨트롤에 할당 된 모든 작업의 점수를 합한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-440">**controlComplianceScore:** Sum of the score of all Actions assigned to the Control.</span></span>
- <span data-ttu-id="d6d2a-441">**Controlactiontitle:** 작업 탭에 나열 된이 컨트롤에 대 한 모든 actionTitles 더블 세미콜론으로 구분 된 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-441">**controlActionTitle:** Double semi-colon-delimited list of all actionTitles for this control as listed on the Actions tab.</span></span> 

#### <a name="actions-tab"></a><span data-ttu-id="d6d2a-442">동작 탭</span><span class="sxs-lookup"><span data-stu-id="d6d2a-442">Actions tab</span></span>

<span data-ttu-id="d6d2a-443">이 탭에는 개별 작업을 정의 하는 열과 작업 제목, 소유권 및 차원과 같은 세부 내용이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-443">This tab includes columns that define individual Actions, and it includes details like action title, ownership, and dimensions.</span></span> <span data-ttu-id="d6d2a-444">아래 나열 된 순서 대로 Excel 내에서 주문 해야 하는이 탭의 열은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-444">The columns for this tab, which must be ordered within Excel in the order listed below, are:</span></span> 

- <span data-ttu-id="d6d2a-445">**Actiontitle:** 작업의 제목입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-445">**actionTitle:** Title of the action.</span></span> <span data-ttu-id="d6d2a-446">각 제목은 고유 해야 하며 파스칼식 대/소문자를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-446">Each title must be unique, and we recommend using Pascal case.</span></span>
- <span data-ttu-id="d6d2a-447">**actionRelatedODVs:** Actiontitles 열에 나열 된 자식의 부모에 해당 하는 두 개의 actionTitles 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-447">**actionRelatedODVs:** Double semicolon-delimited list of actionTitles that are parents of the child listed in the actionTitle column.</span></span> <span data-ttu-id="d6d2a-448">부모/자식 관계에서 상위 항목은 상위 워터 마크를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-448">In a parent/child relationship, the parent represents the high watermark.</span></span> <span data-ttu-id="d6d2a-449">따라서 부모 작업을 완료 하면 모든 하위 작업도 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-449">Thus, if you complete a parent action, you also complete all child actions.</span></span> <span data-ttu-id="d6d2a-450">예를 들어 암호 길이와 같이 요구 사항이 유사 하지만 표준/규정에 따라 최소 15 자가 필요 하며, 하나는 최소 12 또는 10이 필요한 경우</span><span class="sxs-lookup"><span data-stu-id="d6d2a-450">For example, when you have similar requirements but different standard-defined values, such as password length, where one standard/regulation requires a minimum of 15 characters, and another requires a minimum of 12 or 10.</span></span> <span data-ttu-id="d6d2a-451">15는이 예제의 상위이 고, 최소 15 자를 구성 하는 경우 다른 평가에서 12 자 또는 10 자의 권장 작업도 충족 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-451">15 would be the parent in this example, and if you configure a minimum of 15 characters, you also satisfy the actions that recommend 12 or 10 characters in other assessments.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d6d2a-452">ActionRelatedODVs 열은 스키마에 대 한 필수 열입니다. 그러나 준수 관리자 (미리 보기)에서는 기능 (관련 작업)을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-452">The actionRelatedODVs column is a required column for the schema; however, the feature (related actions) is not available in Compliance Manager (Preview).</span></span>  <span data-ttu-id="d6d2a-453">이후 릴리스에서 추가 될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-453">It is scheduled to be added in a later release.</span></span>

- <span data-ttu-id="d6d2a-454">**Actiondimensionvalues:** 다음 형식을 사용 하 여 차원 탭에서 적용 가능한 차원에 대 한 두 개의 세미콜론으로 구분 된 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-454">**actionDimensionValues:** Double semicolon-delimited list of applicable dimensions from the Dimensions tab, using the following format:</span></span>

    ```Markdown
    Dimension Key::Dimension Value;;Dimension Key::Dimension Value.
    ```
    
    <span data-ttu-id="d6d2a-455">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-455">For example:</span></span>

    ```Markdown
    Product::Office 365;;Certification::NIST CSF
    ```

    <span data-ttu-id="d6d2a-456">사용자 지정 서식 파일에 사용 되는 모든 차원은 차원 대시보드에 이미 나열 되어 있더라도 가져오기 파일의 차원 탭에 나열 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-456">All Dimensions that are used in a custom Template must be listed on the Dimensions tab of the import file, even if they are already listed on the Dimensions dashboard.</span></span>
- <span data-ttu-id="d6d2a-457">**Actionscore:** 각 작업의 점수를 나타내는 숫자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-457">**actionScore:** Numeric value for each Action, which represents the score for that action.</span></span> <span data-ttu-id="d6d2a-458">각 작업의 목적과 적용을 기반으로 하는 기본 제공 평가에서 사용 하는 점수 매기기 모델을 따르는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-458">We recommend following the scoring model used by the built-in assessments, which is based on each Action’s purpose and enforcement.</span></span>
- <span data-ttu-id="d6d2a-459">**Actionownership 다음과 같이 나타납니다.** 세미콜론으로 구분 된 소유자 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-459">**actionOwnership:** Double semicolon-delimited list of Owners.</span></span> <span data-ttu-id="d6d2a-460">나열 된 모든 소유자는 소유권 탭에 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-460">All listed Owners must be included on the Ownership tab.</span></span>
- <span data-ttu-id="d6d2a-461">**Actiondescription:** 각각 고유 해야 하는 각 작업의 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-461">**actionDescription:** Text of each Action, which must be unique.</span></span> <span data-ttu-id="d6d2a-462">이 필드는 아래 설명 된 Markdown 언어를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-462">This field supports Markdown Language as described below.</span></span>

#### <a name="ownership-tab"></a><span data-ttu-id="d6d2a-463">소유권 탭</span><span class="sxs-lookup"><span data-stu-id="d6d2a-463">Ownership tab</span></span>

<span data-ttu-id="d6d2a-464">이 탭에는 각 작업의 소유자를 정의 하는 열이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-464">This tab includes columns that define owners for each action.</span></span>  <span data-ttu-id="d6d2a-465">아래 나열 된 순서 대로 Excel 내에서 주문 해야 하는이 탭의 열은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-465">The columns for this tab, which must be ordered within Excel in the order listed below, are:</span></span>

- <span data-ttu-id="d6d2a-466">**ownershipName:** 소유자/담당 파티의 고유 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-466">**ownershipName:** Unique name of owner/responsible party.</span></span>
- <span data-ttu-id="d6d2a-467">**소유자 정보 설명:** 소유자/담당 파티에 대 한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-467">**ownershipDescription:** Description of the owner/responsible party.</span></span>

#### <a name="dimensions-tab"></a><span data-ttu-id="d6d2a-468">차원 탭</span><span class="sxs-lookup"><span data-stu-id="d6d2a-468">Dimensions tab</span></span>

<span data-ttu-id="d6d2a-469">이 탭에는 작업과 연결할 수 있는 차원을 정의 하는 열이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-469">This tab includes columns that define the Dimensions that can be associated with an Action.</span></span>  <span data-ttu-id="d6d2a-470">아래 나열 된 순서 대로 Excel 내에서 주문 해야 하는이 탭의 열은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-470">The columns for this tab, which must be ordered within Excel in the order listed below, are:</span></span>

- <span data-ttu-id="d6d2a-471">**Dimensionkey:** 차원에 사용 되는 키 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-471">**dimensionKey:** List of Keys used for Dimensions.</span></span> <span data-ttu-id="d6d2a-472">예를 들면 제품, 인증 등이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-472">For example, Product, Certification, etc.</span></span>
- <span data-ttu-id="d6d2a-473">**Dimensionvalue:** 각 차원 키에 대 한 고유 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-473">**dimensionValue:** Unique value for each dimension key.</span></span> <span data-ttu-id="d6d2a-474">예를 들면 Office 365, Intune, Azure, 사용자 지정 제품 등이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-474">For example, Office 365, Intune, Azure, Custom Product, etc.</span></span>
- <span data-ttu-id="d6d2a-475">**Allowmultiselect:** 단일 차원 키에 대해 여러 차원 값을 선택할 수 있음을 나타내려면 TRUE 또는 FALSE를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-475">**allowMultiSelect:** Use TRUE or FALSE to indicate that multiple dimension values can be selected for a single dimension key.</span></span>

#### <a name="using-markdown-language-in-description-fields"></a><span data-ttu-id="d6d2a-476">설명 필드에 Markdown 언어 사용</span><span class="sxs-lookup"><span data-stu-id="d6d2a-476">Using Markdown Language in Description Fields</span></span>

<span data-ttu-id="d6d2a-477">서식 파일 및 평가에서는 일부 텍스트 요소 및 서식에 Markdown 언어 사용을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-477">Templates and Assessments support the use of Markdown language for some text elements and formatting.</span></span>  <span data-ttu-id="d6d2a-478">준수 관리자에서 사용 되는 Markdown 언어의 세 가지 서식 요소는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-478">There are three formatting elements of Markdown language that are used in Compliance Manager:</span></span>

- <span data-ttu-id="d6d2a-479">글머리 기호 및 번호 매기기 목록</span><span class="sxs-lookup"><span data-stu-id="d6d2a-479">Bullets and Numbered lists</span></span>
- <span data-ttu-id="d6d2a-480">하이퍼링크</span><span class="sxs-lookup"><span data-stu-id="d6d2a-480">Hyperlinks</span></span>
- <span data-ttu-id="d6d2a-481">굵은</span><span class="sxs-lookup"><span data-stu-id="d6d2a-481">Boldface</span></span>

<span data-ttu-id="d6d2a-482">글머리 기호는 Word 또는 Excel 글머리 기호 대신 별표로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-482">Bullets are represented as asterisks instead of Word or Excel bullets.</span></span> <span data-ttu-id="d6d2a-483">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-483">For example:</span></span>

```Markdown
* Item A
* Item B
* Item C
```

<span data-ttu-id="d6d2a-484">숫자는 숫자로 나타내지만 들여쓰기가 필요한 경우 공백을 사용 하 고, 각 하위 수준에는 숫자만 사용 합니다 (예: 문자 없음).</span><span class="sxs-lookup"><span data-stu-id="d6d2a-484">Numbers are represented as numbers, but with spaces for indentation (three spaces per level) and only numbers used for all sublevels (for example, no letters).</span></span>  <span data-ttu-id="d6d2a-485">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-485">For example:</span></span>
   1. <span data-ttu-id="d6d2a-486">항목 A</span><span class="sxs-lookup"><span data-stu-id="d6d2a-486">Item A</span></span>
   2. <span data-ttu-id="d6d2a-487">항목 B</span><span class="sxs-lookup"><span data-stu-id="d6d2a-487">Item B</span></span>
      1. <span data-ttu-id="d6d2a-488">하위 항목 A</span><span class="sxs-lookup"><span data-stu-id="d6d2a-488">Sub-item A</span></span>
      2. <span data-ttu-id="d6d2a-489">하위 항목 B</span><span class="sxs-lookup"><span data-stu-id="d6d2a-489">Sub-item B</span></span>
   3. <span data-ttu-id="d6d2a-490">항목 C</span><span class="sxs-lookup"><span data-stu-id="d6d2a-490">Item C</span></span>
   4. <span data-ttu-id="d6d2a-491">항목 D</span><span class="sxs-lookup"><span data-stu-id="d6d2a-491">Item D</span></span>
      1. <span data-ttu-id="d6d2a-492">하위 항목 A</span><span class="sxs-lookup"><span data-stu-id="d6d2a-492">Sub-item A</span></span>
      2. <span data-ttu-id="d6d2a-493">하위 항목 B</span><span class="sxs-lookup"><span data-stu-id="d6d2a-493">Sub-item B</span></span>
   5. <span data-ttu-id="d6d2a-494">항목 E</span><span class="sxs-lookup"><span data-stu-id="d6d2a-494">Item E</span></span>

<span data-ttu-id="d6d2a-495">하이퍼링크 텍스트를 대괄호로 묶고 닫는 대괄호 바로 다음에 하이퍼링크를 괄호로 묶어 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-495">Hyperlinks are constructed by placing brackets around the hyperlink text and the hyperlink itself in parentheses immediately next to the close bracket.</span></span>  <span data-ttu-id="d6d2a-496">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-496">For example:</span></span>

```Markdown
Click [here](https://www.microsoft.com) to go to Microsoft’s home page.
```
<span data-ttu-id="d6d2a-497">이 텍스트는 다음과 같이 렌더링 됩니다. [여기](https://www.microsoft.com) 를 클릭 하 여 Microsoft의 홈 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-497">This text renders as follows:  Click [here](https://www.microsoft.com) to go to Microsoft’s home page.</span></span>

<span data-ttu-id="d6d2a-498">위의 예제에 나와 있는 것 처럼 준수 관리자는 밑줄을 사용 하 여 Url을 렌더링 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-498">As shown in the above example, Compliance Manager does not render URLs with underlining.</span></span>

<span data-ttu-id="d6d2a-499">굵은 텍스트는 텍스트의 양쪽에 있는 두 개의 별표가 며 굵게 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-499">Boldface text is two asterisks on each side of the text to be bolded.</span></span>  <span data-ttu-id="d6d2a-500">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-500">For example:</span></span>

```Markdown
**This text will render in bold**
```
<span data-ttu-id="d6d2a-501">**이 텍스트는 굵게 렌더링 됩니다.**</span><span class="sxs-lookup"><span data-stu-id="d6d2a-501">**This text renders in bold**</span></span>

### <a name="create-a-template"></a><span data-ttu-id="d6d2a-502">서식 파일 만들기</span><span class="sxs-lookup"><span data-stu-id="d6d2a-502">Create a Template</span></span>

<span data-ttu-id="d6d2a-503">기존 서식 파일을 복사 하거나 Excel에서 서식 파일 데이터를 가져와 서식 파일을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-503">You can create a Template by copying an existing Template or by importing Template data from Excel.</span></span> <span data-ttu-id="d6d2a-504">Excel에서 데이터를 가져올 때 서식 파일에는 두 가지 준수 관리자 관리자가 데이터 (게시할 대상 및 승인할 항목)를 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-504">When importing data from Excel, the Template requires two different Compliance Manager Administrators to publish the data (one to publish, and one to approve).</span></span>

#### <a name="create-a-template-by-copying-an-existing-template"></a><span data-ttu-id="d6d2a-505">기존 서식 파일을 복사 하 여 서식 파일 만들기</span><span class="sxs-lookup"><span data-stu-id="d6d2a-505">Create a Template by copying an existing Template</span></span>

1. <span data-ttu-id="d6d2a-506">**서식 파일** 대시보드를 열고 **+ 서식 파일 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-506">Open the **Templates** dashboard and select **+ Add Template**.</span></span>
2. <span data-ttu-id="d6d2a-507">**서식 파일 이름 입력** 필드에 서식 파일의 고유 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-507">In the **Enter template name** field, provide a unique name for the Template.</span></span>
3. <span data-ttu-id="d6d2a-508">**기존 서식 파일에서 복사** 확인란을 선택 하 고 드롭다운 목록에서 복사 하려는 서식 파일을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-508">Check the **Copy from an existing template** checkbox and select the template you want to copy from the dropdown.</span></span>
4. <span data-ttu-id="d6d2a-509">필요한 경우 추가 차원을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-509">Optionally add any additional Dimensions.</span></span>
5. <span data-ttu-id="d6d2a-510">**대시보드에 추가를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-510">Select **Add to Dashboard**.</span></span>

#### <a name="create-a-template-by-importing-data"></a><span data-ttu-id="d6d2a-511">데이터를 가져와서 서식 파일 만들기</span><span class="sxs-lookup"><span data-stu-id="d6d2a-511">Create a Template by importing data</span></span>

1. <span data-ttu-id="d6d2a-512">**서식 파일** 대시보드를 열고 **+ 서식 파일 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-512">Open the **Templates** dashboard and select **+ Add Template**.</span></span>
2. <span data-ttu-id="d6d2a-513">**서식 파일 이름 입력** 필드에 서식 파일의 고유 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-513">In the **Enter template name** field, provide a unique name for the Template.</span></span>
3. <span data-ttu-id="d6d2a-514">사용 가능한 목록에서 차원을 하나 이상 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-514">Select at least one Dimension from the available list.</span></span>
4. <span data-ttu-id="d6d2a-515">**찾아보기를** 선택 하 여 가져올 파일의 위치를 탐색 하 고 선택 하 고 **열기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-515">Select **Browse** to navigate to the location of the import file, select it, and select **Open**.</span></span>
5. <span data-ttu-id="d6d2a-516">가져오기 파일의 유효성이 검사 되 고 검색 된 컨트롤 및 컨트롤 패밀리의 수가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-516">The import file will be validated and indicate the number of controls and control families that were detected.</span></span> <span data-ttu-id="d6d2a-517">오류가 있으면 오류 세부 정보가 포함 된 수정 된 버전의 가져오기 파일에 링크가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-517">If there are errors, a link will be provided to a modified version of the import file that includes error details.</span></span> <span data-ttu-id="d6d2a-518">데이터를 가져오기 전에 모든 오류를 해결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-518">All errors must be resolved before the data will be imported.</span></span>
6. <span data-ttu-id="d6d2a-519">데이터가 유효성 검사를 통과 하면 **대시보드에 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-519">Once the data passes validation, select **Add to Dashboard**.</span></span>
7. <span data-ttu-id="d6d2a-520">가져온 템플릿은 **템플릿** 대시보드에 나타나며 **가져온 템플릿이 가져오기**상태입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-520">The imported Template appears on the **Templates** dashboard and it has a status of **Imported**.</span></span> <span data-ttu-id="d6d2a-521">줄임표 (...)를 선택 하 고 **게시** 를 선택 하 여 서식 파일을 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-521">Select the ellipses (…) and select **Publish** to publish the Template.</span></span> <span data-ttu-id="d6d2a-522">확인 메시지가 표시 되 면 **게시**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-522">When the confirmation message appears, select **Publish**.</span></span> <span data-ttu-id="d6d2a-523">서식 파일 상태가 **보류 중 승인**으로 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-523">The Template status changes to **Pending Approval**.</span></span>
8. <span data-ttu-id="d6d2a-524">준수 관리자 관리자 역할을 가진 다른 사용자는 템플릿 대시보드의 템플릿을 승인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-524">Another user with the Compliance Manager Administrator role must approve the Template in the Templates dashboard.</span></span> <span data-ttu-id="d6d2a-525">줄임표 (...)를 선택 하 고 **승인을**선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-525">They must select the ellipses (…) and select **Approve**.</span></span> <span data-ttu-id="d6d2a-526">확인 메시지가 표시 되 면 **승인을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-526">When the confirmation message appears, select **Approve**.</span></span> <span data-ttu-id="d6d2a-527">이제 서식 파일을 사용할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-527">The Template is now ready for use.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d6d2a-528">서식 파일을 만들 때는 **제품** 및 **인증** 에 대 한 차원을 모두 포함 하 여 서식 파일이 준수 점수에 표시 되도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-528">When creating a template, you must include Dimensions for both **Product** and **Certification** to ensure your template displays in Compliance Score.</span></span>

### <a name="customize-a-template"></a><span data-ttu-id="d6d2a-529">서식 파일 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="d6d2a-529">Customize a Template</span></span>

<span data-ttu-id="d6d2a-530">사용자 지정 컨트롤을 추가 하 여 서식 파일을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-530">Templates can be customized through the additional of custom controls.</span></span> <span data-ttu-id="d6d2a-531">모든 사용자 지정 컨트롤은 고객 관리 컨트롤로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-531">All custom controls are considered customer-managed Controls.</span></span>

#### <a name="add-a-custom-control-to-a-template"></a><span data-ttu-id="d6d2a-532">서식 파일에 사용자 지정 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="d6d2a-532">Add a custom control to a Template</span></span>

1. <span data-ttu-id="d6d2a-533">수정할 **서식 파일** 을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-533">Open the **Template** you want to modify.</span></span>
2. <span data-ttu-id="d6d2a-534">**+** 사용자 지정 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-534">Select **+ Add** custom control.</span></span>
3. <span data-ttu-id="d6d2a-535">드롭다운 목록에서 **컨트롤 패밀리** 를 선택 하거나 새 컨트롤 패밀리가 없는 경우 해당 패밀리를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-535">Select a **Control Family** from the dropdown or enter a new control family if it does not exist.</span></span>
4. <span data-ttu-id="d6d2a-536">컨트롤 **id** 필드에 컨트롤의 고유 이름이 나 ID를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-536">Provide a unique name or ID for the control in the **Control ID** field.</span></span>
5. <span data-ttu-id="d6d2a-537">**제목** 필드에 컨트롤의 제목을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-537">Provide the control title in the **Title** field.</span></span>
6. <span data-ttu-id="d6d2a-538">**설명** 필드에 컨트롤에 대 한 요구 사항 및 기타 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-538">Provide the requirements and other information for the control in the **Description** field.</span></span>
7. <span data-ttu-id="d6d2a-539">**고객 작업 할당** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-539">Select **Assign Customer** Action.</span></span>
8. <span data-ttu-id="d6d2a-540">컨트롤에 할당 하려는 작업을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-540">Locate the Action(s) you want to assign to the control:</span></span>
    - <span data-ttu-id="d6d2a-541">차원에 대 한 **필터** 를 사용 하 여 작업에 할당 된 차원을 찾아서 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-541">Use **Filter by Dimension** to use dimensions assigned to the Action(s) to locate and list them.</span></span>
    - <span data-ttu-id="d6d2a-542">**소유자가 만든 필터** 를 사용 하 여 작업에 할당 된 소유자를 사용 하 여 찾아서 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-542">Use **Filter by Owner** to use the owner(s) assigned to the Action(s) to locate and list them.</span></span>
    - <span data-ttu-id="d6d2a-543">드롭다운 목록에서 **작업 유형을** 선택 하 여 유형별로 작업을 나열할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-543">Select an **Action Type** from the dropdown to list Actions by type.</span></span>
    - <span data-ttu-id="d6d2a-544">찾은 작업의 제목을 입력 하 여 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-544">Enter the title of the Action to locate and list it.</span></span>
9. <span data-ttu-id="d6d2a-545">8 단계에 나와 있는 조건을 사용 하 여 일치 하는 **작업** 목록이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-545">Using the criteria in Step 8, a list of **Matching Action(s)** will appear.</span></span> <span data-ttu-id="d6d2a-546">컨트롤에 할당 하려는 첫 번째 작업을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-546">Select the first Action you want to assign to the control.</span></span>
10. <span data-ttu-id="d6d2a-547">작업에 대 한 세부 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-547">The details of the Action appear.</span></span> <span data-ttu-id="d6d2a-548">사용 하려는 **설명을** 선택 하 고 **완료**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-548">Select the **Description** you want to use and select **Done**.</span></span>
11. <span data-ttu-id="d6d2a-549">할당 하려는 각 추가 작업에 대해 9-10 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-549">Repeat Steps 9 and 10 for each additional Action you want to assign.</span></span>
12. <span data-ttu-id="d6d2a-550">해당 하는 모든 작업이 선택 되었으면 **할당**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-550">When all applicable Actions have been selected, select **Assign**.</span></span>
13. <span data-ttu-id="d6d2a-551">**저장** 을 선택 하 여 새 컨트롤을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-551">Select **Save** to save the new control.</span></span>

> [!NOTE]
> <span data-ttu-id="d6d2a-552">서식 파일에 대 한 변경 내용은 기존 평가에 반영 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-552">Any changes made to a template will not be reflected in existing assessments.</span></span> <span data-ttu-id="d6d2a-553">변경 내용이 표시 되도록 먼저 서식 파일을 업데이트 한 다음 새 평가에 적용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-553">Template updates must be made first, and then applied to a new assessment, in order for the changes to be seen.</span></span>

### <a name="export-a-template-to-json"></a><span data-ttu-id="d6d2a-554">JSON으로 템플릿 내보내기</span><span class="sxs-lookup"><span data-stu-id="d6d2a-554">Export a Template to JSON</span></span>

<span data-ttu-id="d6d2a-555">준수 관리자 (미리 보기)에서는 JavaScript 개체 표기법 (JSON) 형식으로 템플릿을 내보낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-555">Compliance Manager (Preview) also supports exporting Templates to JavaScript Object Notation (JSON) format.</span></span> <span data-ttu-id="d6d2a-556">이를 통해 준수 관리자 데이터를 JSON을 지 원하는 다른 시스템과 교환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-556">This enables you to exchange Compliance Manager data with other systems that support JSON.</span></span>

## <a name="reports"></a><span data-ttu-id="d6d2a-557">보고서</span><span class="sxs-lookup"><span data-stu-id="d6d2a-557">Reports</span></span>

<span data-ttu-id="d6d2a-558">조직의 규정 준수 관계자 또는 외부 감사자 및 조정기에 대 한 Excel 파일에 대 한 평가를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-558">You can export an Assessment to an Excel file for compliance stakeholders in your organization or for external auditors and regulators.</span></span> <span data-ttu-id="d6d2a-559">이 보고서는 내보내기의 날짜 및 시간에 대 한 평가의 스냅샷입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-559">The report is a snapshot of the Assessment as of the date and time of the export.</span></span> <span data-ttu-id="d6d2a-560">이 보고서에는 평가, 컨트롤 구현 상태, 컨트롤 테스트 날짜, 테스트 결과 및 업로드 된 증거 문서에 대 한 링크에 대 한 Microsoft 및 고객 관리 컨트롤에 대 한 세부 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-560">The report contains the details for Microsoft and customer-managed controls for the Assessment, control implementation status, control test date, test results, and links to uploaded evidence documents.</span></span> <span data-ttu-id="d6d2a-561">보관 된 평가에서는 업로드 된 문서에 대 한 링크를 유지 하지 않으므로 평가를 보관 하기 전에 내보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-561">You should export Assessments before archiving them because archived Assessments do not retain links to uploaded documents.</span></span>

### <a name="export-an-assessment"></a><span data-ttu-id="d6d2a-562">평가 내보내기</span><span class="sxs-lookup"><span data-stu-id="d6d2a-562">Export an Assessment</span></span>

1. <span data-ttu-id="d6d2a-563">준수 관리자 대시보드에서 **컨트롤 정보** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-563">On the Compliance Manager dashboard, select **Controls Info** tab.</span></span>
2. <span data-ttu-id="d6d2a-564">내보내려는 평가의 드롭다운 메뉴에서 그룹 및 평가를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-564">Select the Group and Assessment in the dropdown menus for the Assessment you want to export.</span></span>
3. <span data-ttu-id="d6d2a-565">내보내기를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-565">Select Export.</span></span> <span data-ttu-id="d6d2a-566">평가 내보내기가 Excel 파일로 다운로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-566">The Assessment export is downloaded as an Excel file.</span></span>

![준수 관리자 평가 Excel 보고서](media/compliance-manager-assessment-report.png)

## <a name="permissions"></a><span data-ttu-id="d6d2a-568">사용 권한</span><span class="sxs-lookup"><span data-stu-id="d6d2a-568">Permissions</span></span>

<span data-ttu-id="d6d2a-569">다음 표에서는 각 준수 관리자 권한 및 사용자가 수행할 수 있는 작업에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-569">The following table describes each Compliance Manager permission and what it allows the user do.</span></span> <span data-ttu-id="d6d2a-570">또한이 표에서는 각 사용 권한에 할당 되는 역할을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-570">The table also indicates the role that each permission is assigned.</span></span>

||<span data-ttu-id="d6d2a-571">**Azure AD 전역 읽기 권한자**</span><span class="sxs-lookup"><span data-stu-id="d6d2a-571">**Azure AD Global Reader**</span></span>|<span data-ttu-id="d6d2a-572">**준수 관리자 읽기 권한자**</span><span class="sxs-lookup"><span data-stu-id="d6d2a-572">**Compliance Manager Reader**</span></span>|<span data-ttu-id="d6d2a-573">**준수 관리자 참가자**</span><span class="sxs-lookup"><span data-stu-id="d6d2a-573">**Compliance Manager Contributor**</span></span>|<span data-ttu-id="d6d2a-574">**준수 관리자 평가자**</span><span class="sxs-lookup"><span data-stu-id="d6d2a-574">**Compliance Manager Assessor**</span></span>|<span data-ttu-id="d6d2a-575">**준수 관리자의 관리자**</span><span class="sxs-lookup"><span data-stu-id="d6d2a-575">**Compliance Manager Administrator**</span></span>|<span data-ttu-id="d6d2a-576">**포털 관리자**</span><span class="sxs-lookup"><span data-stu-id="d6d2a-576">**Portal Admin**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d6d2a-577">**데이터 읽기:** 사용자는 서식 파일 데이터 및 테 넌 트 관리를 제외 하 고는 데이터를 읽을 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-577">**Read data:** Users can read but not edit data (except for Template data and Tenant Management).</span></span>  <br> | <span data-ttu-id="d6d2a-578">X</span><span class="sxs-lookup"><span data-stu-id="d6d2a-578">X</span></span> | <span data-ttu-id="d6d2a-579">X</span><span class="sxs-lookup"><span data-stu-id="d6d2a-579">X</span></span> | <span data-ttu-id="d6d2a-580">X</span><span class="sxs-lookup"><span data-stu-id="d6d2a-580">X</span></span> | <span data-ttu-id="d6d2a-581">X</span><span class="sxs-lookup"><span data-stu-id="d6d2a-581">X</span></span> | <span data-ttu-id="d6d2a-582">X</span><span class="sxs-lookup"><span data-stu-id="d6d2a-582">X</span></span>  | <span data-ttu-id="d6d2a-583">X</span><span class="sxs-lookup"><span data-stu-id="d6d2a-583">X</span></span> |
|<span data-ttu-id="d6d2a-584">**데이터 편집:** 사용자는 테스트 결과 및 테스트 날짜 필드를 제외한 모든 필드를 편집할 수 있습니다 (템플릿 데이터 및 테 넌 트 관리 제외).</span><span class="sxs-lookup"><span data-stu-id="d6d2a-584">**Edit data:** Users can edit all fields, except the Test Result and Test Date fields (except for Template data and Tenant Management).</span></span>  <br> ||| <span data-ttu-id="d6d2a-585">X</span><span class="sxs-lookup"><span data-stu-id="d6d2a-585">X</span></span> | <span data-ttu-id="d6d2a-586">X</span><span class="sxs-lookup"><span data-stu-id="d6d2a-586">X</span></span>  | <span data-ttu-id="d6d2a-587">X</span><span class="sxs-lookup"><span data-stu-id="d6d2a-587">X</span></span> | <span data-ttu-id="d6d2a-588">X</span><span class="sxs-lookup"><span data-stu-id="d6d2a-588">X</span></span> |
|<span data-ttu-id="d6d2a-589">**테스트 결과 편집:** 사용자는 테스트 결과 및 테스트 날짜 필드를 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-589">**Edit test results:** Users can edit the Test Result and Test Date fields.</span></span>  <br> |||| <span data-ttu-id="d6d2a-590">X</span><span class="sxs-lookup"><span data-stu-id="d6d2a-590">X</span></span> | <span data-ttu-id="d6d2a-591">X</span><span class="sxs-lookup"><span data-stu-id="d6d2a-591">X</span></span> | <span data-ttu-id="d6d2a-592">X</span><span class="sxs-lookup"><span data-stu-id="d6d2a-592">X</span></span> |
|<span data-ttu-id="d6d2a-593">**평가 관리:** 사용자는 평가를 만들고 보관 하 고 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-593">**Manage assessments:** Users can create, archive, and delete Assessments.</span></span>  <br> ||||| <span data-ttu-id="d6d2a-594">X</span><span class="sxs-lookup"><span data-stu-id="d6d2a-594">X</span></span> | <span data-ttu-id="d6d2a-595">X</span><span class="sxs-lookup"><span data-stu-id="d6d2a-595">X</span></span> |
|<span data-ttu-id="d6d2a-596">**마스터 데이터 관리:** 사용자는 템플릿 데이터 및 테 넌 트 관리 데이터를 보고, 편집 하 고, 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-596">**Manage master data:** Users can view, edit, and delete template data and tenant management data.</span></span>  <br> ||||| <span data-ttu-id="d6d2a-597">X</span><span class="sxs-lookup"><span data-stu-id="d6d2a-597">X</span></span> | <span data-ttu-id="d6d2a-598">X</span><span class="sxs-lookup"><span data-stu-id="d6d2a-598">X</span></span> |
|<span data-ttu-id="d6d2a-599">**사용자 관리:** 사용자는 조직의 다른 사용자를 독자, 참가자, 평가자 및 관리자 역할에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-599">**Manage users:** Users can add other users in their organization to the Reader, Contributor, Assessor, and Administrator roles.</span></span> <span data-ttu-id="d6d2a-600">조직에서 전역 관리자 역할이 있는 사용자만 포털 관리자 역할에서 사용자를 추가 하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2a-600">Only those users with the Global Administrator role in your organization can add or remove users from the Portal Admin role.</span></span>  <br> |||||| <span data-ttu-id="d6d2a-601">X</span><span class="sxs-lookup"><span data-stu-id="d6d2a-601">X</span></span> |
