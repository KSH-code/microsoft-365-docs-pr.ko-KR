---
title: Microsoft 준수 점수 설정
f1.keywords:
- NOCSH
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
description: 위험 평가를 간소화 하 고 자동화 하는 데 도움이 되는 Microsoft 준수 점수를 설정 하 고 시작 하는 방법을 알아봅니다.
ms.openlocfilehash: 7a0030ed417e21484717b6edf12406d2f5e760e5
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140863"
---
# <a name="microsoft-compliance-score-preview-setup"></a><span data-ttu-id="ac430-103">Microsoft 준수 점수 (미리 보기) 설치</span><span class="sxs-lookup"><span data-stu-id="ac430-103">Microsoft Compliance Score (preview) setup</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ac430-104">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="ac430-104">Before you begin</span></span>

<span data-ttu-id="ac430-105">조직의 Microsoft 365 전역 관리자는 준수 점수에 액세스 하는 첫 번째 사용자가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac430-105">The Microsoft 365 global administrator for your organization will likely be the first user to access Compliance Score.</span></span> <span data-ttu-id="ac430-106">먼저 규정 준수 점수를 검색할 때 전역 관리자 로그인 및 아래에 설명 된 대로 사용자 권한을 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ac430-106">We recommend the global admin sign-in and set user permissions as outlined below when visiting Compliance Score for the first time.</span></span>

## <a name="sign-in"></a><span data-ttu-id="ac430-107">로그인</span><span class="sxs-lookup"><span data-stu-id="ac430-107">Sign in</span></span>

1. <span data-ttu-id="ac430-108">[Microsoft 365 준수 센터로](https://compliance.microsoft.com/) 이동 하 여 microsoft 365 전역 관리자 계정으로 **로그인** 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac430-108">Go to the [Microsoft 365 compliance center](https://compliance.microsoft.com/) and **sign in** with your Microsoft 365 global admin account.</span></span>
2. <span data-ttu-id="ac430-109">왼쪽 탐색 창에서 **규정 준수 점수** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac430-109">Select **Compliance Score** on the left navigation pane.</span></span> <span data-ttu-id="ac430-110">그런 다음 [준수 점수 대시보드를 점수와 함께](#understand-the-compliance-score-dashboard)확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac430-110">You should then see your [Compliance Score dashboard with your score](#understand-the-compliance-score-dashboard).</span></span>

<span data-ttu-id="ac430-111">액세스 준수 점수에 대 한 직접 링크는 [https://compliance.microsoft.com/compliancescore](https://compliance.microsoft.com/compliancescore)다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ac430-111">The direct link to access Compliance Score is: [https://compliance.microsoft.com/compliancescore](https://compliance.microsoft.com/compliancescore).</span></span>

## <a name="set-user-permissions-and-assign-roles"></a><span data-ttu-id="ac430-112">사용자 권한 설정 및 역할 할당</span><span class="sxs-lookup"><span data-stu-id="ac430-112">Set user permissions and assign roles</span></span>

<span data-ttu-id="ac430-113">규정 준수 점수에는 RBAC (역할 기반 액세스 제어) 권한 모델이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac430-113">Compliance Score uses a role-based access control (RBAC) permission model.</span></span> <span data-ttu-id="ac430-114">역할이 할당 된 사용자만 준수 점수에 액세스할 수 있으며, 각 사용자가 허용한 작업은 역할 유형에 따라 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac430-114">Only users who are assigned a role may access Compliance Score, and the actions allowed by each user are restricted by role type.</span></span>

### <a name="where-to-set-permissions"></a><span data-ttu-id="ac430-115">사용 권한을 설정 하는 위치</span><span class="sxs-lookup"><span data-stu-id="ac430-115">Where to set permissions</span></span>

<span data-ttu-id="ac430-116">조직의 전역 관리자는 azure [Active Directory (AZURE AD)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal) 또는 [준수 관리자](compliance-manager-overview.md#permissions)에서 사용자 권한을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac430-116">The global admin for your organization can set user permissions in [Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal) or in [Compliance Manager](compliance-manager-overview.md#permissions).</span></span> <span data-ttu-id="ac430-117">이러한 위치 중 하나에서 역할이 설정 되 면 사용자는 준수 관리자와 준수 점수에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac430-117">Once roles are set in either of these locations, users can access Compliance Score as well as Compliance Manager.</span></span>

### <a name="role-types"></a><span data-ttu-id="ac430-118">역할 유형</span><span class="sxs-lookup"><span data-stu-id="ac430-118">Role types</span></span>

<span data-ttu-id="ac430-119">아래 표에는 각 [AZURE AD 역할이](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) 기존 준수 관리자 역할 및 각 역할에서 허용 하는 기능에 매핑되는 방식이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac430-119">The table below shows how each [Azure AD role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) maps to existing Compliance Manger roles, and the functions allowed by each role.</span></span> <span data-ttu-id="ac430-120">준수 점수에 액세스 하려면 사용자에 게 최소한 Azure AD 전역 독자 역할이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac430-120">Users will need at least the Azure AD global reader role to access Compliance Score.</span></span>


| <span data-ttu-id="ac430-121">사용자는 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac430-121">User can:</span></span> | <span data-ttu-id="ac430-122">Azure AD 역할</span><span class="sxs-lookup"><span data-stu-id="ac430-122">Azure AD role</span></span> | <span data-ttu-id="ac430-123">준수 관리자 역할</span><span class="sxs-lookup"><span data-stu-id="ac430-123">Compliance Manager role</span></span> | 
| :------------- | :-------------: | :------------: |
| <span data-ttu-id="ac430-124">**데이터를 읽을 수는 있지만 편집 하지 않음**</span><span class="sxs-lookup"><span data-stu-id="ac430-124">**Read but not edit data**</span></span>| <span data-ttu-id="ac430-125">Azure AD 전역 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="ac430-125">Azure AD global reader</span></span>  | <span data-ttu-id="ac430-126">Azure AD 전역 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="ac430-126">Azure AD global reader</span></span> | 
| <span data-ttu-id="ac430-127">**데이터를 읽을 수는 있지만 편집 하지 않음**</span><span class="sxs-lookup"><span data-stu-id="ac430-127">**Read but not edit data**</span></span>| <span data-ttu-id="ac430-128">보안 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="ac430-128">Security reader</span></span> | <span data-ttu-id="ac430-129">준수 관리자 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="ac430-129">Compliance Manager reader</span></span>  | 
| <span data-ttu-id="ac430-130">**데이터 편집**</span><span class="sxs-lookup"><span data-stu-id="ac430-130">**Edit data**</span></span>| <span data-ttu-id="ac430-131">준수 관리자</span><span class="sxs-lookup"><span data-stu-id="ac430-131">Compliance administrator</span></span> | <span data-ttu-id="ac430-132">준수 관리자 참가자</span><span class="sxs-lookup"><span data-stu-id="ac430-132">Compliance Manager contributor</span></span> | 
| <span data-ttu-id="ac430-133">**테스트 결과 편집**</span><span class="sxs-lookup"><span data-stu-id="ac430-133">**Edit test results**</span></span>| <span data-ttu-id="ac430-134">준수 관리자</span><span class="sxs-lookup"><span data-stu-id="ac430-134">Compliance administrator</span></span> | <span data-ttu-id="ac430-135">준수 관리자 평가자</span><span class="sxs-lookup"><span data-stu-id="ac430-135">Compliance Manager assessor</span></span> | 
| <span data-ttu-id="ac430-136">**평가, 서식 파일 및 테 넌 트 데이터 관리**</span><span class="sxs-lookup"><span data-stu-id="ac430-136">**Manage assessments, and template and tenant data**</span></span>| <span data-ttu-id="ac430-137">준수 관리자</span><span class="sxs-lookup"><span data-stu-id="ac430-137">Compliance administrator</span></span><br><span data-ttu-id="ac430-138">규정 준수 데이터 관리자</span><span class="sxs-lookup"><span data-stu-id="ac430-138">Compliance data administrator</span></span><br><span data-ttu-id="ac430-139">보안 관리자</span><span class="sxs-lookup"><span data-stu-id="ac430-139">Security administrator</span></span> | <span data-ttu-id="ac430-140">준수 관리자 관리자</span><span class="sxs-lookup"><span data-stu-id="ac430-140">Compliance Manager administrator</span></span> | 
| <span data-ttu-id="ac430-141">**사용자 할당**</span><span class="sxs-lookup"><span data-stu-id="ac430-141">**Assign users**</span></span>| <span data-ttu-id="ac430-142">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="ac430-142">Global administrator</span></span> | <span data-ttu-id="ac430-143">포털 관리자</span><span class="sxs-lookup"><span data-stu-id="ac430-143">Portal admin</span></span> | 

> [!NOTE]
> <span data-ttu-id="ac430-144">규정 준수 점수에서 준수 관리자로 이동 하 여 작업을 완료 하면 (예: 평가 관리) 브라우저가 새 탭을 열고 대화 상자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac430-144">When you go from Compliance Score to Compliance Manager to complete a task (for example, to manage assessments), your browser will open a new tab and a dialog box appears.</span></span> <span data-ttu-id="ac430-145">머리글이 "이미 Microsoft 클라우드 서비스 고객" 인 최상위 섹션에서</span><span class="sxs-lookup"><span data-stu-id="ac430-145">In the top section with the header, "Already a Microsoft cloud services customer?</span></span> <span data-ttu-id="ac430-146">계정에 로그인 하 고 " **로그인** 하 여 액세스 준수 관리자를 선택 합니다. 자격 증명을 다시 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ac430-146">Sign in to your account," select **Sign In** to access Compliance Manager; you will not need to re-enter your credentials.</span></span>

## <a name="configure-automatic-secure-score-updates"></a><span data-ttu-id="ac430-147">자동 보안 점수 업데이트 구성</span><span class="sxs-lookup"><span data-stu-id="ac430-147">Configure automatic Secure Score updates</span></span>

<span data-ttu-id="ac430-148">기본적으로 모든 새 테 넌 트에는 [보안 점수](../security/mtp/microsoft-secure-score.md) 자동 업데이트가 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac430-148">By default, all new tenants have [Secure Score](../security/mtp/microsoft-secure-score.md) automatic updates turned on.</span></span> <span data-ttu-id="ac430-149">보안 점수를 통해 모니터링 되는 모든 작업에서는 준수 점수가 같은 작업에 대 한 상태를 자동으로 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac430-149">All actions that are monitored by Secure Score will automatically update the status for the same action in Compliance Score.</span></span>

<span data-ttu-id="ac430-150">전역 관리자는이 설정을 관리 하 여 모든 작업에 대해 자동 업데이트를 해제 하거나 작업에 대 한 업데이트를 개별적으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac430-150">Your global administrator can manage this setting to turn off automatic updates for all actions, or set updates for actions individually.</span></span>

<span data-ttu-id="ac430-151">공개 미리 보기 중에 보안 점수 업데이트를 관리 하려면 Microsoft Service Trust Portal (준수 관리자가 있는 경우)로 이동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac430-151">During public preview, you'll need to go to the Microsoft Service Trust Portal (where Compliance Manger is located) to manage Secure Score updates.</span></span>

<span data-ttu-id="ac430-152">자동 보안 점수 업데이트를 관리 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac430-152">To manage automatic Secure Score updates, follow these steps:</span></span>

1. <span data-ttu-id="ac430-153">전역 관리자 계정을 사용 하 여 [서비스 신뢰 포털](https://servicetrust.microsoft.com) 에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac430-153">Sign in to the [Service Trust Portal](https://servicetrust.microsoft.com) with your global administrator account.</span></span>

2. <span data-ttu-id="ac430-154">서비스 보안 포털의 위쪽 메뉴 모음에 있는 **자세히**에서 **관리자** 를 선택 하 고 **설정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac430-154">On the Service Trust Portal top menu bar, under **More**, select **Admin** and then choose **Settings**.</span></span>

3. <span data-ttu-id="ac430-155">**보안 점수** 탭에서 **모든 동작에 대해 켤**해당 단추를 선택 하 고, **모든 작업**을 해제 하거나, 작업별 **로 설정 합니다.**</span><span class="sxs-lookup"><span data-stu-id="ac430-155">In the **Secure Score** tab, select the corresponding button to either **turn on for all actions**, **turn off for all actions**, or **set per action.**</span></span>

<span data-ttu-id="ac430-156">작업별 설정을 선택 하 **는** 경우 다음과 같은 추가 단계를 수행 하 여 개별 작업에 대 한 보안 점수 업데이트를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac430-156">If you choose **set per action,** take these additional steps to turn on Secure Score updates for individual actions:</span></span>

4. <span data-ttu-id="ac430-157">최상위 메뉴에서 **준수 관리자** 를 선택 합니다 (레거시 제품인 "준수 관리자 (클래식)"는 선택 하지 않음).</span><span class="sxs-lookup"><span data-stu-id="ac430-157">Select **Compliance Manager** from the top menu (do not select "Compliance Manager (classic)," which is a legacy product).</span></span>

5. <span data-ttu-id="ac430-158">화면의 오른쪽 위 모서리에 있는 **테 넌 트 관리** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac430-158">Select **Tenant Management** in the upper-right corner of your screen.</span></span>

6. <span data-ttu-id="ac430-159">**고객 작업** 창의 해당 하는 **작업** 열에서 줄임표 (**...**)를 사용 하 여 원하는 작업을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ac430-159">On the **Customer Actions** pane, find your intended action with an ellipsis (**...**) under the **Affected Actions** column.</span></span> <span data-ttu-id="ac430-160">줄임표 (...)를 클릭 하 고 편집을 선택 **합니다.**</span><span class="sxs-lookup"><span data-stu-id="ac430-160">Click on the ellipses and select **Edit.**</span></span>

7. <span data-ttu-id="ac430-161">**보안 점수 연속 업데이트** 전환 스위치를 설정으로 전환 **합니다.**</span><span class="sxs-lookup"><span data-stu-id="ac430-161">Switch the **Secure Score continuous update** toggle switch to **On.**</span></span>

8. <span data-ttu-id="ac430-162">**저장을 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="ac430-162">Select **Save.**</span></span> <span data-ttu-id="ac430-163">이제 해당 작업에 대 한 보안 점수 지속적인 모니터링이 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac430-163">Secure Score continuous monitoring is now turned on for that action.</span></span>

<span data-ttu-id="ac430-164">**참고:** 전역 관리자만 모든 작업에 대해 자동 업데이트를 설정 하거나 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac430-164">**Note:** Only the global administrator can turn on or off automatic updates for all actions.</span></span> <span data-ttu-id="ac430-165">준수 관리자 관리자는 개별 작업에 대해 자동 업데이트를 설정할 수 있지만 모든 작업에 대해 전역적으로 수행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ac430-165">The Compliance Manager administrator can turn on automatic updates for individual actions, but not for all actions globally.</span></span>

<span data-ttu-id="ac430-166">[보안 점수 업데이트 관리](compliance-manager-release-notes.md#secure-score)에 대 한 자세한 내용을 읽으십시오.</span><span class="sxs-lookup"><span data-stu-id="ac430-166">Read more about [managing Secure Score updates](compliance-manager-release-notes.md#secure-score).</span></span>

## <a name="understand-the-compliance-score-dashboard"></a><span data-ttu-id="ac430-167">준수 점수 대시보드 이해</span><span class="sxs-lookup"><span data-stu-id="ac430-167">Understand the Compliance Score dashboard</span></span>

<span data-ttu-id="ac430-168">준수 점수 대시보드는 현재 준수 상태를 한눈에 파악할 수 있도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ac430-168">The Compliance Score dashboard is designed to provide you an at-a-glance view of your current compliance posture.</span></span>

<span data-ttu-id="ac430-169">![준수 점수-대시보드](../media/compliance-score-dashboard.png "준수 점수 대시보드")</span><span class="sxs-lookup"><span data-stu-id="ac430-169">![Compliance Score - dashboard](../media/compliance-score-dashboard.png "Compliance Score dashboard")</span></span>

### <a name="overall-compliance-score"></a><span data-ttu-id="ac430-170">전반적인 준수 점수</span><span class="sxs-lookup"><span data-stu-id="ac430-170">Overall compliance score</span></span>

<span data-ttu-id="ac430-171">준수 점수는 맨 위에 있는 아주 명확 하 게 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac430-171">Your compliance score is featured prominently at the top.</span></span> <span data-ttu-id="ac430-172">주요 데이터 보호 표준 및 규정을 해결 하는 향상 작업을 완료 하는 데 필요한 점수를 기반으로 하는 백분율을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ac430-172">It shows a percentage based on points achievable for completing improvement actions that address key data protection standards and regulations.</span></span>

<span data-ttu-id="ac430-173">처음으로 준수 점수가 제공 되는 경우 초기 점수는 기본 제공 되는 Microsoft 365 데이터 보호 기준을 기반으로 하며, 일반적인 업계 규정 및 표준을 포함 하는 컨트롤 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="ac430-173">When you come to Compliance Score for the first time, your initial score is based on the built-in Microsoft 365 data protection baseline—a set of controls that includes common industry regulations and standards.</span></span> <span data-ttu-id="ac430-174">규정 준수 점수가 기존 Microsoft 365 솔루션의 시스템을 검사 하기 때문에 조직에서 현재 사용 하 고 있는 개인 정보 및 보안 설정을 기반으로 준수 상태를 초기에 평가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac430-174">Because Compliance Score scans your system of existing Microsoft 365 solutions, it gives an initial assessment of your compliance posture based on privacy and security settings currently enabled by your organization.</span></span>

<span data-ttu-id="ac430-175">조직과 관련 된 평가를 추가 하면 점수가 더 많이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac430-175">As you add assessments that are relevant to your organization, your score becomes even more meaningful.</span></span> <span data-ttu-id="ac430-176">[점수를 계산 하는 방법](compliance-score-methodology.md)에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="ac430-176">Learn more about [how your score is calculated](compliance-score-methodology.md).</span></span>

### <a name="key-improvement-actions"></a><span data-ttu-id="ac430-177">주요 개선 작업</span><span class="sxs-lookup"><span data-stu-id="ac430-177">Key improvement actions</span></span>

<span data-ttu-id="ac430-178">이 섹션에서는 전체 준수 점수에 가장 큰 긍정적인 영향을 줄 수 있는 주요 향상 작업을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac430-178">This section lists the top improvement actions you can take right now to make the largest positive impact on your overall compliance score.</span></span>

### <a name="solutions-that-affect-your-score"></a><span data-ttu-id="ac430-179">점수에 영향을 주는 솔루션</span><span class="sxs-lookup"><span data-stu-id="ac430-179">Solutions that affect your score</span></span>

<span data-ttu-id="ac430-180">이 섹션에서는 점수에 긍정적인 영향을 줄 수 있는 작업을 포함 하는 솔루션 및 각 솔루션에서 해결 되지 않은 개선 작업 수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ac430-180">This section shows solutions containing actions with the greatest opportunity to positively impact your score, and the number of outstanding improvement actions in each solution.</span></span>

### <a name="compliance-score-breakdown"></a><span data-ttu-id="ac430-181">규정 준수 점수 분석</span><span class="sxs-lookup"><span data-stu-id="ac430-181">Compliance Score breakdown</span></span>

<span data-ttu-id="ac430-182">이 섹션에서는 다음과 같은 두 가지 방법으로 점수에 대 한 자세한 내용을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac430-182">This section gives you a more detailed view of your score in two different ways:</span></span>

- <span data-ttu-id="ac430-183">**범주**: "정보 보호" 또는 "장치 관리"와 같은 데이터 보호 범주 내의 전체 점수 비율을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac430-183">**Categories**: shows the percentage of your overall score within data protection categories, such as "protect information" or "manage devices."</span></span>
- <span data-ttu-id="ac430-184">**평가**: GDPR 또는 NIST 800-53와 같은 특정 준수 및 데이터 보호 표준, 규정 또는 법규에 대 한 평가 관리에서 진행률을 관리할 비율을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ac430-184">**Assessments**: shows the percentage of your progress in managing assessments for particular compliance and data protection standards, regulations, or laws, such as GDPR or NIST 800-53.</span></span>

### <a name="filtering-your-dashboard-view"></a><span data-ttu-id="ac430-185">대시보드 보기 필터링</span><span class="sxs-lookup"><span data-stu-id="ac430-185">Filtering your dashboard view</span></span>

<span data-ttu-id="ac430-186">대시보드 보기를 필터링 하 여 특정 규정과 표준, 솔루션, 작업 유형, [설정 하는 평가 그룹](working-with-compliance-manager.md#groups)또는 데이터 보호 범주와 관련 된 항목만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac430-186">You can filter your dashboard view to see only the items related to particular regulations and standards, solutions, type of action, [groups of assessments you set up](working-with-compliance-manager.md#groups), or data protection categories.</span></span> <span data-ttu-id="ac430-187">이 방식으로 보기를 필터링 하면 대시보드의 점수가 필터링 되며, 필터 조건을 기준으로 하 여 총 가능한 점수를 얻은 점의 수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ac430-187">Filtering your view in this way will also filter the score on your dashboard, showing how many points you've achieved out of total possible points based on your filter criteria.</span></span>

<span data-ttu-id="ac430-188">필터를 적용 하려면</span><span class="sxs-lookup"><span data-stu-id="ac430-188">To apply filters:</span></span>

1. <span data-ttu-id="ac430-189">대시보드의 오른쪽 위에 있는 **필터** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac430-189">Select **Filter** on the upper-right side of the dashboard.</span></span>
2. <span data-ttu-id="ac430-190">**필터** 플라이 아웃 창에서 필터 조건을 선택한 다음 **적용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac430-190">Select your filter criteria from the **Filters** flyout pane, then select **Apply**.</span></span>

<span data-ttu-id="ac430-191">필터를 적용 한 후 점수가 실시간으로 조정 되는 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac430-191">After you apply a filter, you'll see your score adjusted in real time.</span></span> <span data-ttu-id="ac430-192">준수 점수 비율 및 분석 정보 및 개선 작업 및 솔루션은 필터 기준에 포함 된 데이터에만 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="ac430-192">The compliance score percentage and breakdown information, and the improvement actions and solutions, now only pertain to data covered by your filter criteria.</span></span> <span data-ttu-id="ac430-193">규정 준수 점수를 로그 아웃 하는 경우 필터링 된 보기는 다시 로그인 할 때 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac430-193">If you sign out of Compliance Score, your filtered view remains when you sign back in.</span></span>

<span data-ttu-id="ac430-194">필터를 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="ac430-194">To remove filters:</span></span>

- <span data-ttu-id="ac430-195">준수 점수 위의 **적용 된 필터** 제목에서 제거할 개별 필터 옆에 있는 **X** 를 선택 합니다. 사용자나</span><span class="sxs-lookup"><span data-stu-id="ac430-195">At the **Applied filters** heading above your compliance score, select the **X** next to the individual filter you want to remove; or</span></span>
- <span data-ttu-id="ac430-196">대시보드의 오른쪽 위에 있는 **필터** 를 선택 하 고 **필터 지우기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac430-196">Select **Filter** on the upper-right side of your dashboard, then select **Clear filters**.</span></span>

## <a name="next-step"></a><span data-ttu-id="ac430-197">다음 단계</span><span class="sxs-lookup"><span data-stu-id="ac430-197">Next step</span></span>

<span data-ttu-id="ac430-198">[규정 준수 점수 관련 작업](working-with-compliance-score.md) 을 방문 하 여 점수 개선을 위한 작업을 수행 하는 방법에 대 한 워크플로를 파악할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac430-198">Visit [Working with Compliance Score](working-with-compliance-score.md) to understand the workflow of how to take actions to improve your score.</span></span>