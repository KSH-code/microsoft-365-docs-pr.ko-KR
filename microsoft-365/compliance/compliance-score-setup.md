---
title: Microsoft 준수 점수 (미리 보기) 설치
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
ms.openlocfilehash: f7a501d0ede0d7635e20581774ce51a599dde65b
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016193"
---
# <a name="compliance-score-preview-setup"></a><span data-ttu-id="6219d-103">준수 점수 (미리 보기) 설정</span><span class="sxs-lookup"><span data-stu-id="6219d-103">Compliance Score (preview) setup</span></span>

<span data-ttu-id="6219d-104">**이 문서의 내용** 준수 점수에 **액세스** 하 고, **역할 및 사용 권한을**설정 하 고, **자동 보안 점수 업데이트**를 구성 하는 방법을 이해 합니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-104">**In this article:** Understand how to **access** Compliance Score, set **roles and permissions**, and configure **automatic Secure Score updates**.</span></span> <span data-ttu-id="6219d-105">이 문서에서는 또한 **대시보드**, 개선 작업 페이지, 솔루션 페이지 및 평가 페이지와 같은 주요 준수 점수 페이지에 대해서도 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-105">This article also explains the main Compliance Score pages: **your dashboard**, the improvement actions page, the solutions page, and the assessments page.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="6219d-106">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="6219d-106">Before you begin</span></span>

<span data-ttu-id="6219d-107">조직의 Microsoft 365 전역 관리자는 준수 점수에 액세스 하는 첫 번째 사용자가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-107">The Microsoft 365 global administrator for your organization will likely be the first user to access Compliance Score.</span></span> <span data-ttu-id="6219d-108">다음에 규정 준수 점수를 처음 방문할 때 전역 관리자 로그인 및 아래에 설명 된 대로 사용자 권한을 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-108">We recommend the global admin sign in and set user permissions as outlined below when visiting Compliance Score for the first time.</span></span>

## <a name="sign-in"></a><span data-ttu-id="6219d-109">로그인</span><span class="sxs-lookup"><span data-stu-id="6219d-109">Sign in</span></span>

1. <span data-ttu-id="6219d-110">[Microsoft 365 준수 센터로](https://compliance.microsoft.com/) 이동 하 여 microsoft 365 전역 관리자 계정으로 **로그인** 합니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-110">Go to the [Microsoft 365 compliance center](https://compliance.microsoft.com/) and **sign in** with your Microsoft 365 global admin account.</span></span>
2. <span data-ttu-id="6219d-111">왼쪽 탐색 창에서 **규정 준수 점수** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-111">Select **Compliance Score** on the left navigation pane.</span></span> <span data-ttu-id="6219d-112">그런 다음 [준수 점수 대시보드를 점수와 함께](#understand-the-compliance-score-dashboard)확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-112">You should then see your [Compliance Score dashboard with your score](#understand-the-compliance-score-dashboard).</span></span>

<span data-ttu-id="6219d-113">액세스 준수 점수에 대 한 직접 링크는 [https://compliance.microsoft.com/compliancescore](https://compliance.microsoft.com/compliancescore) 입니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-113">The direct link to access Compliance Score is [https://compliance.microsoft.com/compliancescore](https://compliance.microsoft.com/compliancescore).</span></span>

## <a name="set-user-permissions-and-assign-roles"></a><span data-ttu-id="6219d-114">사용자 권한 설정 및 역할 할당</span><span class="sxs-lookup"><span data-stu-id="6219d-114">Set user permissions and assign roles</span></span>

<span data-ttu-id="6219d-115">규정 준수 점수에는 RBAC (역할 기반 액세스 제어) 권한 모델이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-115">Compliance Score uses a role-based access control (RBAC) permission model.</span></span> <span data-ttu-id="6219d-116">역할이 할당 된 사용자만 준수 점수에 액세스할 수 있으며, 각 사용자가 허용한 작업은 역할 유형에 따라 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-116">Only users who are assigned a role may access Compliance Score, and the actions allowed by each user are restricted by role type.</span></span>

### <a name="where-to-set-permissions"></a><span data-ttu-id="6219d-117">사용 권한을 설정 하는 위치</span><span class="sxs-lookup"><span data-stu-id="6219d-117">Where to set permissions</span></span>

<span data-ttu-id="6219d-118">조직에 대 한 전역 관리자 역할을 보유 하 고 있는 사용자는 azure [Active Directory (AZURE AD)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal) 또는 [준수 관리자](compliance-manager-overview.md#permissions)에서 사용자 권한을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-118">The person holding the global admin role for your organization can set user permissions in [Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal) or in [Compliance Manager](compliance-manager-overview.md#permissions).</span></span> <span data-ttu-id="6219d-119">이러한 위치 중 하나에서 역할이 설정 되 면 사용자는 준수 관리자와 준수 점수에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-119">Once roles are set in either of these locations, users can access Compliance Score as well as Compliance Manager.</span></span>

### <a name="role-types"></a><span data-ttu-id="6219d-120">역할 유형</span><span class="sxs-lookup"><span data-stu-id="6219d-120">Role types</span></span>

<span data-ttu-id="6219d-121">아래 표에는 각 [AZURE AD 역할이](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) 기존 준수 관리자 역할 및 각 역할에서 허용 하는 기능에 매핑되는 방식이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-121">The table below shows how each [Azure AD role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) maps to existing Compliance Manger roles, and the functions allowed by each role.</span></span> <span data-ttu-id="6219d-122">준수 점수에 액세스 하려면 사용자에 게 최소한 Azure AD 전역 독자 역할이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-122">Users will need at least the Azure AD global reader role to access Compliance Score.</span></span>


| <span data-ttu-id="6219d-123">사용자는 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-123">User can:</span></span> | <span data-ttu-id="6219d-124">Azure AD 역할</span><span class="sxs-lookup"><span data-stu-id="6219d-124">Azure AD role</span></span> | <span data-ttu-id="6219d-125">준수 관리자 역할</span><span class="sxs-lookup"><span data-stu-id="6219d-125">Compliance Manager role</span></span> | 
| :------------- | :-------------: | :------------: |
| <span data-ttu-id="6219d-126">**데이터를 읽을 수는 있지만 편집 하지 않음**</span><span class="sxs-lookup"><span data-stu-id="6219d-126">**Read but not edit data**</span></span>| <span data-ttu-id="6219d-127">Azure AD 전역 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="6219d-127">Azure AD global reader</span></span>  | <span data-ttu-id="6219d-128">Azure AD 전역 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="6219d-128">Azure AD global reader</span></span> | 
| <span data-ttu-id="6219d-129">**데이터를 읽을 수는 있지만 편집 하지 않음**</span><span class="sxs-lookup"><span data-stu-id="6219d-129">**Read but not edit data**</span></span>| <span data-ttu-id="6219d-130">보안 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="6219d-130">Security reader</span></span> | <span data-ttu-id="6219d-131">준수 관리자 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="6219d-131">Compliance Manager reader</span></span>  | 
| <span data-ttu-id="6219d-132">**데이터 편집**</span><span class="sxs-lookup"><span data-stu-id="6219d-132">**Edit data**</span></span>| <span data-ttu-id="6219d-133">준수 관리자</span><span class="sxs-lookup"><span data-stu-id="6219d-133">Compliance administrator</span></span> | <span data-ttu-id="6219d-134">준수 관리자 참가자</span><span class="sxs-lookup"><span data-stu-id="6219d-134">Compliance Manager contributor</span></span> | 
| <span data-ttu-id="6219d-135">**테스트 결과 편집**</span><span class="sxs-lookup"><span data-stu-id="6219d-135">**Edit test results**</span></span>| <span data-ttu-id="6219d-136">준수 관리자</span><span class="sxs-lookup"><span data-stu-id="6219d-136">Compliance administrator</span></span> | <span data-ttu-id="6219d-137">준수 관리자 평가자</span><span class="sxs-lookup"><span data-stu-id="6219d-137">Compliance Manager assessor</span></span> | 
| <span data-ttu-id="6219d-138">**평가, 서식 파일 및 테 넌 트 데이터 관리**</span><span class="sxs-lookup"><span data-stu-id="6219d-138">**Manage assessments, and template and tenant data**</span></span>| <span data-ttu-id="6219d-139">준수 관리자</span><span class="sxs-lookup"><span data-stu-id="6219d-139">Compliance administrator</span></span><br><span data-ttu-id="6219d-140">규정 준수 데이터 관리자</span><span class="sxs-lookup"><span data-stu-id="6219d-140">Compliance data administrator</span></span><br><span data-ttu-id="6219d-141">보안 관리자</span><span class="sxs-lookup"><span data-stu-id="6219d-141">Security administrator</span></span> | <span data-ttu-id="6219d-142">준수 관리자 관리자</span><span class="sxs-lookup"><span data-stu-id="6219d-142">Compliance Manager administrator</span></span> | 
| <span data-ttu-id="6219d-143">**사용자 할당**</span><span class="sxs-lookup"><span data-stu-id="6219d-143">**Assign users**</span></span>| <span data-ttu-id="6219d-144">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="6219d-144">Global administrator</span></span> | <span data-ttu-id="6219d-145">포털 관리자</span><span class="sxs-lookup"><span data-stu-id="6219d-145">Portal admin</span></span> | 

> [!NOTE]
> <span data-ttu-id="6219d-146">공개 미리 보기 중에 규정 준수 점수에서 준수 관리자로 이동 하면 브라우저가 새 탭을 열고 대화 상자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-146">When you go from Compliance Score to Compliance Manager to complete a task during public preview, your browser will open a new tab and a dialog box appears.</span></span> <span data-ttu-id="6219d-147">머리글이 "이미 Microsoft 클라우드 서비스 고객" 인 최상위 섹션에서</span><span class="sxs-lookup"><span data-stu-id="6219d-147">In the top section with the header, "Already a Microsoft cloud services customer?</span></span> <span data-ttu-id="6219d-148">계정에 로그인 하 고 " **로그인** 하 여 액세스 준수 관리자"를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-148">Sign in to your account," select **Sign In** to access Compliance Manager.</span></span> <span data-ttu-id="6219d-149">자격 증명을 다시 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-149">You won't need to re-enter your credentials.</span></span>

## <a name="configure-automatic-secure-score-updates"></a><span data-ttu-id="6219d-150">자동 보안 점수 업데이트 구성</span><span class="sxs-lookup"><span data-stu-id="6219d-150">Configure automatic Secure Score updates</span></span>

<span data-ttu-id="6219d-151">기본적으로 모든 새 테 넌 트에는 [보안 점수](../security/mtp/microsoft-secure-score-new.md) 자동 업데이트가 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-151">By default, all new tenants have [Secure Score](../security/mtp/microsoft-secure-score-new.md) automatic updates turned on.</span></span> <span data-ttu-id="6219d-152">보안 점수를 통해 모니터링 되는 모든 작업에서는 준수 점수가 같은 작업에 대 한 상태를 자동으로 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-152">All actions that are monitored by Secure Score will automatically update the status for the same action in Compliance Score.</span></span>

<span data-ttu-id="6219d-153">전역 관리자는이 설정을 관리 하 여 모든 작업에 대해 자동 업데이트를 해제 하거나 작업에 대 한 업데이트를 개별적으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-153">Your global administrator can manage this setting to turn off automatic updates for all actions, or set updates for actions individually.</span></span>

<span data-ttu-id="6219d-154">공개 미리 보기 중에 보안 점수 업데이트를 관리 하려면 Microsoft Service Trust Portal (준수 관리자가 있는 경우)로 이동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-154">During public preview, you'll need to go to the Microsoft Service Trust Portal (where Compliance Manger is located) to manage Secure Score updates.</span></span>

<span data-ttu-id="6219d-155">자동 보안 점수 업데이트를 관리 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-155">To manage automatic Secure Score updates, follow these steps:</span></span>

1. <span data-ttu-id="6219d-156">전역 관리자 계정을 사용 하 여 [서비스 신뢰 포털](https://servicetrust.microsoft.com) 에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-156">Sign in to the [Service Trust Portal](https://servicetrust.microsoft.com) with your global administrator account.</span></span>

2. <span data-ttu-id="6219d-157">서비스 보안 포털의 위쪽 메뉴 모음에 있는 **자세히**에서 **관리자** 를 선택 하 고 **설정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-157">On the Service Trust Portal top menu bar, under **More**, select **Admin** and then choose **Settings**.</span></span>

3. <span data-ttu-id="6219d-158">**보안 점수** 탭에서 **모든 동작에 대해 켤**해당 단추를 선택 하 고, **모든 작업**을 해제 하거나, 작업별 **로 설정 합니다.**</span><span class="sxs-lookup"><span data-stu-id="6219d-158">In the **Secure Score** tab, select the corresponding button to either **turn on for all actions**, **turn off for all actions**, or **set per action.**</span></span>

<span data-ttu-id="6219d-159">작업별 설정을 선택 하 **는** 경우 다음과 같은 추가 단계를 수행 하 여 개별 작업에 대 한 보안 점수 업데이트를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-159">If you choose **set per action,** take these additional steps to turn on Secure Score updates for individual actions:</span></span>

4. <span data-ttu-id="6219d-160">최상위 메뉴에서 **준수 관리자** 를 선택 합니다 ("준수 관리자 (클래식)"는 선택 하지 않음).</span><span class="sxs-lookup"><span data-stu-id="6219d-160">Select **Compliance Manager** from the top menu (do not select "Compliance Manager (classic),").</span></span>

5. <span data-ttu-id="6219d-161">화면의 오른쪽 위 모서리에 있는 **테 넌 트 관리** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-161">Select **Tenant Management** in the upper-right corner of your screen.</span></span>

6. <span data-ttu-id="6219d-162">**고객 작업** 창의 해당 하는 **작업** 열에서 줄임표 (**...**)를 사용 하 여 원하는 작업을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-162">On the **Customer Actions** pane, find your intended action with an ellipsis (**...**) under the **Affected Actions** column.</span></span> <span data-ttu-id="6219d-163">줄임표 (...)를 클릭 하 고 편집을 선택 **합니다.**</span><span class="sxs-lookup"><span data-stu-id="6219d-163">Click on the ellipses and select **Edit.**</span></span>

7. <span data-ttu-id="6219d-164">**보안 점수 연속 업데이트** 전환 스위치를 설정으로 전환 **합니다.**</span><span class="sxs-lookup"><span data-stu-id="6219d-164">Switch the **Secure Score continuous update** toggle switch to **On.**</span></span>

8. <span data-ttu-id="6219d-165">**저장을 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="6219d-165">Select **Save.**</span></span> <span data-ttu-id="6219d-166">이제 해당 작업에 대 한 보안 점수 지속적인 모니터링이 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-166">Secure Score continuous monitoring is now turned on for that action.</span></span>

<span data-ttu-id="6219d-167">**참고:** 전역 관리자만 모든 작업에 대해 자동 업데이트를 설정 하거나 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-167">**Note:** Only the global administrator can turn on or off automatic updates for all actions.</span></span> <span data-ttu-id="6219d-168">준수 관리자 관리자는 개별 작업에 대해 자동 업데이트를 설정할 수 있지만 모든 작업에 대해 전역적으로 수행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-168">The Compliance Manager administrator can turn on automatic updates for individual actions, but not for all actions globally.</span></span>

#### <a name="learn-more"></a><span data-ttu-id="6219d-169">자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="6219d-169">Learn more</span></span>

<span data-ttu-id="6219d-170">[보안 점수 업데이트 관리에 대해 자세히 알아봅니다](compliance-manager-release-notes.md#secure-score).</span><span class="sxs-lookup"><span data-stu-id="6219d-170">[Read about managing Secure Score updates](compliance-manager-release-notes.md#secure-score).</span></span>

## <a name="understand-the-compliance-score-dashboard"></a><span data-ttu-id="6219d-171">준수 점수 대시보드 이해</span><span class="sxs-lookup"><span data-stu-id="6219d-171">Understand the Compliance Score dashboard</span></span>

<span data-ttu-id="6219d-172">준수 점수 대시보드는 현재 준수 상태를 한눈에 파악할 수 있도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-172">The Compliance Score dashboard is designed to provide you an at-a-glance view of your current compliance posture.</span></span>

<span data-ttu-id="6219d-173">![준수 점수-대시보드](../media/compliance-score-dashboard.png "준수 점수 대시보드")</span><span class="sxs-lookup"><span data-stu-id="6219d-173">![Compliance Score - dashboard](../media/compliance-score-dashboard.png "Compliance Score dashboard")</span></span>

### <a name="overall-compliance-score"></a><span data-ttu-id="6219d-174">전반적인 준수 점수</span><span class="sxs-lookup"><span data-stu-id="6219d-174">Overall compliance score</span></span>

<span data-ttu-id="6219d-175">준수 점수는 맨 위에 있는 아주 명확 하 게 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-175">Your compliance score is featured prominently at the top.</span></span> <span data-ttu-id="6219d-176">주요 데이터 보호 표준 및 규정을 해결 하는 향상 작업을 완료 하는 데 필요한 점수를 기반으로 하는 백분율을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-176">It shows a percentage based on points achievable for completing improvement actions that address key data protection standards and regulations.</span></span>

<span data-ttu-id="6219d-177">처음으로 준수 점수가 제공 되는 경우 초기 점수는 기본 제공 되는 [Microsoft 365 데이터 보호 기준을](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)기반으로 하며, 일반적인 업계 규정 및 표준을 포함 하는 컨트롤 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-177">When you come to Compliance Score for the first time, your initial score is based on the built-in [Microsoft 365 data protection baseline](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)—a set of controls that includes common industry regulations and standards.</span></span> <span data-ttu-id="6219d-178">준수 점수가 기존 Microsoft 365 솔루션을 검색 하 고 현재 개인 정보 및 보안 설정에 따라 초기 평가를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-178">Compliance Score scans your existing Microsoft 365 solutions and gives you an initial assessment based on your current privacy and security settings.</span></span> <span data-ttu-id="6219d-179">조직과 관련 된 평가를 추가 하면 점수가 보다 중요 하 게 드러납니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-179">As you add assessments that are relevant to your organization, your score becomes more meaningful for you.</span></span>

#### <a name="learn-more"></a><span data-ttu-id="6219d-180">자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="6219d-180">Learn more</span></span>
<span data-ttu-id="6219d-181">[준수 점수가 계산 되는 방식을 이해](compliance-score-methodology.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-181">[Understand how your compliance score is calculated](compliance-score-methodology.md).</span></span>

### <a name="key-improvement-actions"></a><span data-ttu-id="6219d-182">주요 개선 작업</span><span class="sxs-lookup"><span data-stu-id="6219d-182">Key improvement actions</span></span>

<span data-ttu-id="6219d-183">이 섹션에서는 전체 준수 점수에 가장 큰 긍정적인 영향을 줄 수 있는 주요 향상 작업을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-183">This section lists the top improvement actions you can take right now to make the largest positive impact on your overall compliance score.</span></span>

### <a name="solutions-that-affect-your-score"></a><span data-ttu-id="6219d-184">점수에 영향을 주는 솔루션</span><span class="sxs-lookup"><span data-stu-id="6219d-184">Solutions that affect your score</span></span>

<span data-ttu-id="6219d-185">이 섹션에서는 점수에 긍정적인 영향을 줄 수 있는 작업을 포함 하는 솔루션 및 각 솔루션에서 해결 되지 않은 개선 작업 수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-185">This section shows solutions containing actions with the greatest opportunity to positively impact your score, and the number of outstanding improvement actions in each solution.</span></span>

### <a name="compliance-score-breakdown"></a><span data-ttu-id="6219d-186">규정 준수 점수 분석</span><span class="sxs-lookup"><span data-stu-id="6219d-186">Compliance Score breakdown</span></span>

<span data-ttu-id="6219d-187">이 섹션에서는 다음과 같은 두 가지 방법으로 점수에 대 한 자세한 내용을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-187">This section gives you a more detailed view of your score in two different ways:</span></span>

- <span data-ttu-id="6219d-188">**범주**: "정보 보호" 또는 "장치 관리"와 같은 데이터 보호 범주 내의 전체 점수 비율을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-188">**Categories**: shows the percentage of your overall score within data protection categories, such as "protect information" or "manage devices."</span></span>
- <span data-ttu-id="6219d-189">**평가**: GDPR 또는 NIST 800-53와 같은 특정 준수 및 데이터 보호 표준, 규정 또는 법규에 대 한 평가 관리에서 진행률을 관리할 비율을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-189">**Assessments**: shows the percentage of your progress in managing assessments for particular compliance and data protection standards, regulations, or laws, such as GDPR or NIST 800-53.</span></span>

### <a name="filtering-your-dashboard-view"></a><span data-ttu-id="6219d-190">대시보드 보기 필터링</span><span class="sxs-lookup"><span data-stu-id="6219d-190">Filtering your dashboard view</span></span>

<span data-ttu-id="6219d-191">대시보드 보기를 필터링 하 여 특정 규정과 표준, 솔루션, 작업 유형, 평가 그룹 또는 데이터 보호 범주와 관련 된 항목만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-191">You can filter your dashboard view to see only the items related to particular regulations and standards, solutions, type of action, assessment groups, or data protection categories.</span></span> <span data-ttu-id="6219d-192">이 방식으로 보기를 필터링 하면 대시보드의 점수가 필터링 되며, 필터 조건을 기준으로 하 여 총 가능한 점수를 얻은 점의 수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-192">Filtering your view in this way will also filter the score on your dashboard, showing how many points you've achieved out of total possible points based on your filter criteria.</span></span>

<span data-ttu-id="6219d-193">필터를 적용 하려면</span><span class="sxs-lookup"><span data-stu-id="6219d-193">To apply filters:</span></span>

1. <span data-ttu-id="6219d-194">대시보드의 오른쪽 위에 있는 **필터** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-194">Select **Filter** on the upper-right side of the dashboard.</span></span>
2. <span data-ttu-id="6219d-195">**필터** 플라이 아웃 창에서 필터 조건을 선택한 다음 **적용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-195">Select your filter criteria from the **Filters** flyout pane, then select **Apply**.</span></span>

<span data-ttu-id="6219d-196">필터를 적용 한 후 점수가 실시간으로 조정 되는 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-196">After you apply a filter, you'll see your score adjusted in real time.</span></span> <span data-ttu-id="6219d-197">준수 점수 비율 및 분석 정보 및 개선 작업 및 솔루션은 필터 기준에 포함 된 데이터에만 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-197">The compliance score percentage and breakdown information, and the improvement actions and solutions, now only pertain to data covered by your filter criteria.</span></span> <span data-ttu-id="6219d-198">규정 준수 점수를 로그 아웃 하는 경우 필터링 된 보기는 다시 로그인 할 때 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-198">If you sign out of Compliance Score, your filtered view remains when you sign back in.</span></span>

<span data-ttu-id="6219d-199">필터를 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="6219d-199">To remove filters:</span></span>

- <span data-ttu-id="6219d-200">준수 점수 위의 **적용 된 필터** 제목에서 제거할 개별 필터 옆에 있는 **X** 를 선택 합니다. 사용자나</span><span class="sxs-lookup"><span data-stu-id="6219d-200">At the **Applied filters** heading above your compliance score, select the **X** next to the individual filter you want to remove; or</span></span>
- <span data-ttu-id="6219d-201">대시보드의 오른쪽 위에 있는 **필터** 를 선택 하 고 **필터 지우기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-201">Select **Filter** on the upper-right side of your dashboard, then select **Clear filters**.</span></span>

## <a name="improvement-actions-page"></a><span data-ttu-id="6219d-202">개선 작업 페이지</span><span class="sxs-lookup"><span data-stu-id="6219d-202">Improvement actions page</span></span>

<span data-ttu-id="6219d-203">[향상 작업](compliance-score-improvement-actions.md) 을 통해 규정 준수 작업을 중앙 집중화 하 고 데이터 보호 규정 및 표준에 맞게 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-203">[Improvement actions](compliance-score-improvement-actions.md) centralize your compliance activities and help you align with data protection regulations and standards.</span></span> <span data-ttu-id="6219d-204">각 향상 작업에서는 적절 한 솔루션을 시작 하기 위한 링크 및 자세한 구현 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-204">Each improvement action gives detailed implementation guidance and a link to launch you into the appropriate solution.</span></span> <span data-ttu-id="6219d-205">조직의 사용자에 게 작업을 할당 하 여 구현 및 테스트 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-205">Actions can be assigned to users in your organization to perform implementation and testing work.</span></span> <span data-ttu-id="6219d-206">개선 작업 내에 설명서, 메모 및 레코드 상태 업데이트를 저장할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-206">You can also store documentation, notes, and record status updates within the improvement action.</span></span>

### <a name="view-your-improvement-actions"></a><span data-ttu-id="6219d-207">개선 작업 보기</span><span class="sxs-lookup"><span data-stu-id="6219d-207">View your improvement actions</span></span>

<span data-ttu-id="6219d-208">규정 준수 점수 대시보드에는 **주요 향상 작업**, 즉 가장 중요 한 문제를 해결 하는 가장 많은 지점을 제공 하는 작업이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-208">The Compliance Score dashboard shows your **key improvement actions**, which are the ones with the most available points that address the most important issues.</span></span>

<span data-ttu-id="6219d-209">모든 개선 작업을 보려면 대시보드에서 **개선 작업** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-209">To view all of your improvement actions, select the **Improvement actions** tab on your dashboard.</span></span> <span data-ttu-id="6219d-210">또는 대시보드의 주요 향상 작업 목록 아래에 있는 **모든 개선 작업 보기** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-210">Or, select **View all improvement actions** underneath the list of key improvement actions on your dashboard.</span></span>

<span data-ttu-id="6219d-211">작업 목록이 길면 보기를 필터링 하는 것이 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-211">If you have a long list of actions, it may be helpful to filter your view.</span></span> <span data-ttu-id="6219d-212">작업 목록의 오른쪽 위 모서리에서 **필터** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-212">Select **Filter** at the upper-right corner of the actions list.</span></span> <span data-ttu-id="6219d-213">**필터** 플라이 아웃 창이 나타나면 규정 및 표준, 솔루션, 그룹에 따라 기준을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-213">When the **Filters** flyout pane appears, select your criteria based on regulations and standards, solution, and group.</span></span> <span data-ttu-id="6219d-214">오른쪽 위 모서리에 있는 **그룹** 을 선택 하 여 보기를 사용자 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-214">You can also customize your view by selecting **Group** in the upper-right corner.</span></span> <span data-ttu-id="6219d-215">드롭다운 메뉴에서 그룹, 솔루션, 범주, 작업 유형 또는 상태별로 보기를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-215">From the drop-down menu, select to view by group, solution, category, action type, or status.</span></span>

<span data-ttu-id="6219d-216">이 페이지의 기본 보기에는 **통과**테스트 상태의 개선 작업이 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-216">The default view for this page does not show improvement actions with a test status of **Passed**.</span></span> <span data-ttu-id="6219d-217">테스트에 통과 한 작업을 보려면 필터 플라이 아웃 창에서 **통과** 상자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-217">To view actions that have passed testing, check the **Passed** box in the Filters flyout pane.</span></span> <span data-ttu-id="6219d-218">테스트 상태의 **합격** 한 작업만 점수에 대해 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-218">Only actions with a test status of **Passed** count toward your score.</span></span>

<span data-ttu-id="6219d-219">향상 작업 페이지에는 각 향상 작업에 대 한 다음과 같은 데이터 요소가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-219">The improvement actions page shows the following data points for each improvement action:</span></span>

- <span data-ttu-id="6219d-220">**점수 영향**: 작업 완료 시 전체 점수가 증가 하는 점수입니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-220">**Score impact**: the points by which your overall score will increase when completing the action</span></span>
- <span data-ttu-id="6219d-221">**규정**: 작업과 관련 된 규정 또는 표준</span><span class="sxs-lookup"><span data-stu-id="6219d-221">**Regulations**: the regulation or standard pertaining to the action</span></span>
- <span data-ttu-id="6219d-222">**그룹**: 작업을 할당 한 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-222">**Group**: the group to which you assigned the action</span></span>
- <span data-ttu-id="6219d-223">**해결**방법: 작업을 수행 하기 위해 이동할 수 있는 솔루션</span><span class="sxs-lookup"><span data-stu-id="6219d-223">**Solutions**: the solution where you can go to perform the action</span></span>
- <span data-ttu-id="6219d-224">**평가**: 작업이 상주 하는 평가 (특정 준수 목표를 충족 하도록 컨트롤을 구성)</span><span class="sxs-lookup"><span data-stu-id="6219d-224">**Assessments**: the assessment (which organizes controls to meet a certain compliance objective) in which the action resides</span></span>
- <span data-ttu-id="6219d-225">**범주**: 관련 된 데이터 보호 범주 (즉, 정보 보호, 장치 관리 등)</span><span class="sxs-lookup"><span data-stu-id="6219d-225">**Categories**: the related data protection category (such as, protect information, manage devices, etc.)</span></span>
- <span data-ttu-id="6219d-226">**테스트 상태**:</span><span class="sxs-lookup"><span data-stu-id="6219d-226">**Test status**:</span></span>
    - <span data-ttu-id="6219d-227">**없음** – 상태 업데이트가 기록 되지 않음</span><span class="sxs-lookup"><span data-stu-id="6219d-227">**None** – no status update recorded</span></span>
    - <span data-ttu-id="6219d-228">**평가 안** 됨-테스트가 시작 되지 않음</span><span class="sxs-lookup"><span data-stu-id="6219d-228">**Not assessed** - testing hasn't started</span></span>
    - <span data-ttu-id="6219d-229">**성공** -구현이 테스트 됨</span><span class="sxs-lookup"><span data-stu-id="6219d-229">**Passed** - implementation successfully tested</span></span>
    - <span data-ttu-id="6219d-230">**실패 한 낮은 위험** -테스트 실패, 낮은 위험</span><span class="sxs-lookup"><span data-stu-id="6219d-230">**Failed low risk** - testing failed, low risk</span></span>
    - <span data-ttu-id="6219d-231">**실패 한 중간 위험** -테스트 실패, 보통 위험</span><span class="sxs-lookup"><span data-stu-id="6219d-231">**Failed medium risk** - testing failed, medium risk</span></span>
    - <span data-ttu-id="6219d-232">**실패 한 높은 위험** -테스트 실패, 높은 위험</span><span class="sxs-lookup"><span data-stu-id="6219d-232">**Failed high risk** - testing failed, high risk</span></span>
    - <span data-ttu-id="6219d-233">**범위에 없음** -작업이 평가 범위에 없으며 점수에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-233">**Not in scope** – the action is not in scope for the assessment and doesn't impact your score</span></span>
    - <span data-ttu-id="6219d-234">**검색** 됨-수동 테스트의 경우 작업이 구현 되었지만 테스트 되지 않았음을 나타냅니다. 자동화 된 테스트의 경우 자동화 결과를 기다리는 작업이 실행 됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-234">**To be detected** - for manual test, indicates an action has been implemented but not tested; for automated test, indicates an action is waiting for automation result</span></span>
    - <span data-ttu-id="6219d-235">**검색할** 수 없음-자동화 상태를 확인할 수 없음</span><span class="sxs-lookup"><span data-stu-id="6219d-235">**Could not be detected** - automated status can't be determined</span></span>
    - <span data-ttu-id="6219d-236">**부분적으로 테스트** 됨-부분 점수가 수상 인 자동 점수 매기기</span><span class="sxs-lookup"><span data-stu-id="6219d-236">**Partially tested** – automated scoring that awards partial points</span></span>
- <span data-ttu-id="6219d-237">**획득 한 점수**: 가능한 최대 점수를 받은 포인트 수</span><span class="sxs-lookup"><span data-stu-id="6219d-237">**Points achieved**: number of points earned out of the maximum possible</span></span>

#### <a name="learn-more"></a><span data-ttu-id="6219d-238">자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="6219d-238">Learn more</span></span>
<span data-ttu-id="6219d-239">[향상 작업을 할당 하 고 작업을 수행 하는 방법을 참조](compliance-score-improvement-actions.md)하세요.</span><span class="sxs-lookup"><span data-stu-id="6219d-239">[See how to assign and perform work on improvement actions](compliance-score-improvement-actions.md).</span></span>

## <a name="solutions-page"></a><span data-ttu-id="6219d-240">솔루션 페이지</span><span class="sxs-lookup"><span data-stu-id="6219d-240">Solutions page</span></span>

<span data-ttu-id="6219d-241">솔루션 페이지에는 솔루션 별로 구성 된 획득 및 잠재 점수 공유가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-241">The solutions page shows the share of earned and potential points as organized by solution.</span></span> <span data-ttu-id="6219d-242">이 보기에서 남은 점과 향상 작업을 보면 즉각적인 주의가 필요한 솔루션을 파악할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-242">Viewing your remaining points and improvement actions from this view helps you understand which solutions need more immediate attention.</span></span>

<span data-ttu-id="6219d-243">준수 점수 대시보드에서 **솔루션** 탭을 선택 하 여 솔루션 페이지를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-243">Find the solutions page by selecting the **Solutions** tab on your Compliance Score dashboard.</span></span> <span data-ttu-id="6219d-244">대시보드의 오른쪽 위 섹션에서 **점수에 영향을 주는 솔루션** 아래의 **모든 솔루션 보기** 를 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-244">You can also select **View all solutions** underneath **Solutions that affect your score** in the upper-right section of your dashboard.</span></span>

### <a name="filtering-your-solutions-view"></a><span data-ttu-id="6219d-245">솔루션 보기 필터링</span><span class="sxs-lookup"><span data-stu-id="6219d-245">Filtering your solutions view</span></span>

<span data-ttu-id="6219d-246">솔루션 보기를 필터링 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-246">To filter your view of solutions:</span></span>

1. <span data-ttu-id="6219d-247">평가 목록의 왼쪽 위 모서리에서 **필터** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-247">Select **Filter** at the top-left corner of your assessments list.</span></span>
2. <span data-ttu-id="6219d-248">**필터** 플라이 아웃 창에서 원하는 조건 (표준 및 규정, 솔루션, 작업 유형, 준수 관리자 그룹, 범주) 옆에 확인을 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-248">On the **Filters** flyout pane, place a check next to the desired criteria (standards and regulations, solution, action type, Compliance Manager group, category).</span></span>
3. <span data-ttu-id="6219d-249">**적용** 단추를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-249">Select the **Apply** button.</span></span> <span data-ttu-id="6219d-250">필터 창이 닫히고 필터링 된 보기가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-250">The filter pane will close and you’ll see your filtered view.</span></span>

<span data-ttu-id="6219d-251">평가 목록 위의 **그룹** 드롭다운 메뉴에서 그룹화 유형을 선택 하 여 그룹, 제품 또는 규정 별로 평가를 확인 하도록 보기를 수정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-251">You can also modify your view to see assessments by group, product, or regulation by selecting the type of grouping from the **Group** drop-down menu above your assessments list.</span></span>

### <a name="taking-actions-from-the-solution-page"></a><span data-ttu-id="6219d-252">솔루션 페이지에서 작업 수행</span><span class="sxs-lookup"><span data-stu-id="6219d-252">Taking actions from the solution page</span></span>

<span data-ttu-id="6219d-253">솔루션 페이지에는 개선 작업에 연결 된 조직의 솔루션이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-253">The solutions page displays your organization’s solutions that are connected to improvement actions.</span></span> <span data-ttu-id="6219d-254">이 표에서는 각 솔루션의 전체 점수, 해당 솔루션 내에서 달성 하 고 가능한 점수 및 해당 솔루션에 그룹화 되어 있으며 점수를 높일 수 있는 남은 개선 작업 수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-254">The table lists each solution’s contribution to your overall score, the score-enhancing points achieved and possible within that solution, and the remaining number of improvement actions grouped in that solution that can increase your score.</span></span>

<span data-ttu-id="6219d-255">다음 두 가지 방법으로이 화면에서 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-255">There are two ways you can take action from this screen:</span></span>

1. <span data-ttu-id="6219d-256">원하는 솔루션의 행에서 **남은 작업** 열 아래에서 하이퍼링크 된 번호를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-256">On the row of your intended solution, under the **Remaining actions** column, select the hyperlinked number.</span></span> <span data-ttu-id="6219d-257">해당 솔루션에 대 한 테스트 되지 않은 개선 작업을 보여 주는 개선 작업 화면의 필터링 된 보기가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-257">You’ll see a filtered view of the improvement actions screen showing untested improvement actions for that solution.</span></span>

2. <span data-ttu-id="6219d-258">원하는 솔루션의 행에서 **솔루션 열기** 열 아래에 있는 **열기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-258">On the row of your intended solution, under the **Open solution** column, select **Open**.</span></span> <span data-ttu-id="6219d-259">Microsoft 365 및 Office 365 보안 및 준수 센터에서 권장 조치를 취할 수 있는 솔루션 또는 위치가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-259">You’ll see the solution or location in the Microsoft 365 and Office 365 security and compliance centers where you can take the recommended action.</span></span>

## <a name="assessments-page"></a><span data-ttu-id="6219d-260">평가 페이지</span><span class="sxs-lookup"><span data-stu-id="6219d-260">Assessments page</span></span>

<span data-ttu-id="6219d-261">평가 페이지에는 조직에 대해 설정한 모든 [평가가](compliance-score-assessments.md) 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-261">The assessments page lists all the [assessments](compliance-score-assessments.md) you set up for your organization.</span></span> <span data-ttu-id="6219d-262">준수 점수 분모는 추적 된 모든 평가에 따라 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-262">Your Compliance Score denominator is determined by all your tracked assessments.</span></span> <span data-ttu-id="6219d-263">더 많은 평가가 추가 되 고, 개선 작업 페이지에 더 많은 향상 작업이 발생 하며, 점수 분모가 더 높습니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-263">The more assessments you add, the more improvement actions you see on your improvement actions page, and the higher your score denominator is.</span></span>

<span data-ttu-id="6219d-264">이 페이지에서는 각 평가에 대 한 주요 정보를 요약 합니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-264">This page summarizes key information about each assessment:</span></span>

- <span data-ttu-id="6219d-265">**평가**: 평가의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-265">**Assessment**: name of the assessment</span></span>
- <span data-ttu-id="6219d-266">**상태**:</span><span class="sxs-lookup"><span data-stu-id="6219d-266">**Status**:</span></span>
    - <span data-ttu-id="6219d-267">**전체** -모든 컨트롤의 상태가 "통과" 이거나, 하나 이상 통과 되며 나머지는 "범위를 벗어남"입니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-267">**Complete** -  all controls have a status of “passed,” or at least one is passed and the rest are “out of scope”</span></span>
    - <span data-ttu-id="6219d-268">**불완전** 함-하나 이상의 컨트롤에 "failed" 상태인 컨트롤이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-268">**Incomplete** – at least one control has a status of “failed"</span></span>
    - <span data-ttu-id="6219d-269">**없음** -모든 컨트롤이 테스트 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-269">**None** - all controls have have not been tested</span></span>
    - <span data-ttu-id="6219d-270">**진행** 중인 개선 작업에는 "진행 중", "부분 신용" 또는 "감지 되지 않음"을 비롯 한 다른 상태가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-270">**In progress** - improvement actions have any other status, including “in progress,” “partial credit,” or “undetected</span></span>
- <span data-ttu-id="6219d-271">**평가 진행률**: 성공적으로 테스트를 거친 컨트롤 수로 측정 된 완료까지 작업의 완료율입니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-271">**Assessment progress**: the percentage of the work done toward completion, as measured by the number of controls successfully tested</span></span>
- <span data-ttu-id="6219d-272">**향상 작업**: 컨트롤 구현을 충족 하기 위해 완료 된 작업의 수</span><span class="sxs-lookup"><span data-stu-id="6219d-272">**Your improvement actions**: the number of completed actions to satisfy implementation of your controls</span></span>
- <span data-ttu-id="6219d-273">**Microsoft actions**: microsoft 컨트롤 구현을 충족 하기 위해 완료 된 작업 수</span><span class="sxs-lookup"><span data-stu-id="6219d-273">**Microsoft actions**: the number of completed actions to satisfy implementation of Microsoft controls</span></span>
- <span data-ttu-id="6219d-274">**그룹**: 평가가 속한 그룹의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-274">**Group**: name of the group the assessment belongs to</span></span>
- <span data-ttu-id="6219d-275">**제품**: 연결 된 Microsoft 365 서비스</span><span class="sxs-lookup"><span data-stu-id="6219d-275">**Product**: associated Microsoft 365 service</span></span>
- <span data-ttu-id="6219d-276">**규정**: 평가에 적용 되는 규정 표준, 정책 또는 법입니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-276">**Regulation**: the regulatory standard, policy, or law that applies to the assessment</span></span>

### <a name="filtering-your-assessments-view"></a><span data-ttu-id="6219d-277">평가 보기 필터링</span><span class="sxs-lookup"><span data-stu-id="6219d-277">Filtering your assessments view</span></span>

<span data-ttu-id="6219d-278">평가 보기를 필터링 하려면:</span><span class="sxs-lookup"><span data-stu-id="6219d-278">To filter you view of assessments:</span></span>

1. <span data-ttu-id="6219d-279">평가 목록의 왼쪽 위 모서리에서 **필터** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-279">Select **Filter** at the top-left corner of your assessments list.</span></span>
2. <span data-ttu-id="6219d-280">**필터** 플라이 아웃 창에서 원하는 기준을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-280">On the **Filters** flyout pane, check your desired criteria.</span></span>
3. <span data-ttu-id="6219d-281">적용 단추를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-281">Select the Apply button.</span></span> <span data-ttu-id="6219d-282">필터 창이 닫히고 필터링 된 보기가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-282">The filter pane will close and you will see your filtered view.</span></span>

<span data-ttu-id="6219d-283">평가 목록 위의 **그룹** 드롭다운 메뉴에서 그룹화 유형을 선택 하 여 그룹, 제품 또는 규정 별로 평가를 확인 하도록 보기를 수정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-283">You can also modify your view to see assessments by group, product, or regulation by selecting the type of grouping from the **Group** drop-down menu above your assessments list.</span></span>

### <a name="default-assessment"></a><span data-ttu-id="6219d-284">기본 평가</span><span class="sxs-lookup"><span data-stu-id="6219d-284">Default assessment</span></span>

<span data-ttu-id="6219d-285">기본적으로 평가 페이지에는 [Microsoft 365 데이터 보호 기준](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline) 평가가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-285">By default, you'll see the [Microsoft 365 data protection baseline](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline) assessment on the assessments page.</span></span> <span data-ttu-id="6219d-286">규정 준수 점수는 여러 [템플릿을](compliance-score-templates.md) 사용 하 여 평가를 작성할 수 있는 몇 가지 준비도 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-286">Compliance Score also provides several ready to use [templates](compliance-score-templates.md) from which to build assessments.</span></span>

## <a name="next-step"></a><span data-ttu-id="6219d-287">다음 단계</span><span class="sxs-lookup"><span data-stu-id="6219d-287">Next step</span></span>
<span data-ttu-id="6219d-288">[평가를 설정](compliance-score-assessments.md)하 여 준수 점수를 사용자 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6219d-288">Customize Compliance Score by [setting up assessments](compliance-score-assessments.md).</span></span>