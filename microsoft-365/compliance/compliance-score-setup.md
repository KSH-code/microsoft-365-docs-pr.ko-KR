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
description: 위험 평가를 간소화 하 고 자동화 하는 데 도움이 되는 Microsoft 규정 준수 점수에 대해 로그인 하 고 사용 권한을 설정 하 고 대시보드를 이해 하는 방법을 알아봅니다.
ms.openlocfilehash: 8233fb3174d822e4f71115cab2a1a174c1749810
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42078615"
---
# <a name="microsoft-compliance-score-preview-setup"></a><span data-ttu-id="4e648-103">Microsoft 준수 점수 (미리 보기) 설치</span><span class="sxs-lookup"><span data-stu-id="4e648-103">Microsoft Compliance Score (Preview) setup</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="4e648-104">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="4e648-104">Before you begin</span></span>

<span data-ttu-id="4e648-105">조직의 Microsoft 365 전역 관리자는 준수 점수에 액세스 하는 첫 번째 사용자가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e648-105">The Microsoft 365 global administrator for your organization will likely be the first user to access Compliance Score.</span></span> <span data-ttu-id="4e648-106">다음에 규정 준수 점수를 처음 방문할 때 전역 관리자 로그인 및 아래에 설명 된 대로 사용자 권한을 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4e648-106">We recommend the global admin sign in and set user permissions as outlined below when visiting Compliance Score for the first time.</span></span>

## <a name="sign-in"></a><span data-ttu-id="4e648-107">로그인</span><span class="sxs-lookup"><span data-stu-id="4e648-107">Sign in</span></span>

1. <span data-ttu-id="4e648-108">[Microsoft 365 준수 센터로](https://compliance.microsoft.com/) 이동 하 여 microsoft 365 전역 관리자 계정으로 **로그인** 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e648-108">Go to the [Microsoft 365 compliance center](https://compliance.microsoft.com/) and **sign in** with your Microsoft 365 global admin account.</span></span>
2. <span data-ttu-id="4e648-109">왼쪽 탐색 창에서 **규정 준수 점수** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e648-109">Select **Compliance Score** on the left navigation pane.</span></span> <span data-ttu-id="4e648-110">그런 다음 [준수 점수 대시보드를 점수와 함께](#understand-the-compliance-score-dashboard)확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e648-110">You should then see your [Compliance Score dashboard with your score](#understand-the-compliance-score-dashboard).</span></span>

## <a name="set-user-permissions-and-assign-roles"></a><span data-ttu-id="4e648-111">사용자 권한 설정 및 역할 할당</span><span class="sxs-lookup"><span data-stu-id="4e648-111">Set user permissions and assign roles</span></span>

<span data-ttu-id="4e648-112">규정 준수 점수에는 RBAC (역할 기반 액세스 제어) 권한 모델이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e648-112">Compliance Score uses a role-based access control (RBAC) permission model.</span></span> <span data-ttu-id="4e648-113">역할이 할당 된 사용자만 준수 점수에 액세스할 수 있으며, 각 사용자가 허용한 작업은 역할 유형에 따라 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e648-113">Only users who are assigned a role may access Compliance Score, and the actions allowed by each user are restricted by role type.</span></span>

### <a name="where-to-set-permissions"></a><span data-ttu-id="4e648-114">사용 권한을 설정 하는 위치</span><span class="sxs-lookup"><span data-stu-id="4e648-114">Where to set permissions</span></span>

<span data-ttu-id="4e648-115">조직의 전역 관리자는 Microsoft 365 준수 센터 또는 Azure Active Directory (Azure AD)에서 사용자 권한을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e648-115">The global admin for your organization can set user permissions in the Microsoft 365 compliance center or in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="4e648-116">이러한 위치 중 하나에서 역할이 설정 되 면 사용자는 준수 관리자 및 준수 점수에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e648-116">Once roles are set in either of these locations, users will be able to access Compliance Score (as well as  Compliance Manager).</span></span>

<span data-ttu-id="4e648-117">기존 준수 관리자 역할은 준수 점수로 전송 **되지** 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4e648-117">Note that existing Compliance Manger roles **do not** transfer over to Compliance Score.</span></span>  <span data-ttu-id="4e648-118">즉, 규정 준수 관리자에서 이전에 역할이 할당 된 경우 해당 역할은 준수 점수에 대 한 액세스 권한을 부여 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4e648-118">This means that if you were previously assigned a role in Compliance Manager, that role will not grant you access to Compliance Score.</span></span> <span data-ttu-id="4e648-119">전역 관리자는 준수 점수에 액세스할 수 있도록 Microsoft 365 준수 센터 또는 Azure AD에서 사용자에 대 한 사용 권한 및 역할을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e648-119">Your global admin will need to set permissions and a role for you in the Microsoft 365 compliance center or Azure AD so that you can access Compliance Score.</span></span>

### <a name="role-types"></a><span data-ttu-id="4e648-120">역할 유형</span><span class="sxs-lookup"><span data-stu-id="4e648-120">Role types</span></span>

<span data-ttu-id="4e648-121">아래 표에는 각 Microsoft 365 준수 센터 역할이 기존 준수 관리자 역할 및 각 역할에서 허용 하는 기능에 매핑되는 방식이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e648-121">The table below shows how each Microsoft 365 compliance center role maps to existing Compliance Manger roles, and the functions allowed by each role.</span></span>


| <span data-ttu-id="4e648-122">사용자는 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e648-122">User can:</span></span> | <span data-ttu-id="4e648-123">Microsoft 365 준수 센터 역할</span><span class="sxs-lookup"><span data-stu-id="4e648-123">Microsoft 365 compliance center role</span></span> | <span data-ttu-id="4e648-124">준수 관리자 역할</span><span class="sxs-lookup"><span data-stu-id="4e648-124">Compliance Manager role</span></span> | 
| :------------- | :-------------: | :------------: |
| <span data-ttu-id="4e648-125">**데이터를 읽을 수는 있지만 편집 하지 않음**</span><span class="sxs-lookup"><span data-stu-id="4e648-125">**Read but not edit data**</span></span>| <span data-ttu-id="4e648-126">Azure AD 전역 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="4e648-126">Azure AD global reader</span></span>  | <span data-ttu-id="4e648-127">Azure AD 전역 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="4e648-127">Azure AD global reader</span></span> | 
| <span data-ttu-id="4e648-128">**데이터를 읽을 수는 있지만 편집 하지 않음**</span><span class="sxs-lookup"><span data-stu-id="4e648-128">**Read but not edit data**</span></span>| <span data-ttu-id="4e648-129">보안 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="4e648-129">Security reader</span></span> | <span data-ttu-id="4e648-130">준수 관리자 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="4e648-130">Compliance Manager reader</span></span>  | 
| <span data-ttu-id="4e648-131">**데이터 편집**</span><span class="sxs-lookup"><span data-stu-id="4e648-131">**Edit data**</span></span>| <span data-ttu-id="4e648-132">준수 관리자</span><span class="sxs-lookup"><span data-stu-id="4e648-132">Compliance administrator</span></span> | <span data-ttu-id="4e648-133">준수 관리자 참가자</span><span class="sxs-lookup"><span data-stu-id="4e648-133">Compliance Manager contributor</span></span> | 
| <span data-ttu-id="4e648-134">**테스트 결과 편집**</span><span class="sxs-lookup"><span data-stu-id="4e648-134">**Edit test results**</span></span>| <span data-ttu-id="4e648-135">준수 관리자</span><span class="sxs-lookup"><span data-stu-id="4e648-135">Compliance administrator</span></span> | <span data-ttu-id="4e648-136">준수 관리자 평가자</span><span class="sxs-lookup"><span data-stu-id="4e648-136">Compliance Manager assessor</span></span> | 
| <span data-ttu-id="4e648-137">**평가, 서식 파일 및 테 넌 트 데이터 관리**</span><span class="sxs-lookup"><span data-stu-id="4e648-137">**Manage assessments, and template and tenant data**</span></span>| <span data-ttu-id="4e648-138">준수 관리자</span><span class="sxs-lookup"><span data-stu-id="4e648-138">Compliance administrator</span></span><br><span data-ttu-id="4e648-139">규정 준수 데이터 관리자</span><span class="sxs-lookup"><span data-stu-id="4e648-139">Compliance data administrator</span></span><br><span data-ttu-id="4e648-140">보안 관리자</span><span class="sxs-lookup"><span data-stu-id="4e648-140">Security administrator</span></span> | <span data-ttu-id="4e648-141">준수 관리자 관리자</span><span class="sxs-lookup"><span data-stu-id="4e648-141">Compliance Manager administrator</span></span> | 
| <span data-ttu-id="4e648-142">**사용자 할당**</span><span class="sxs-lookup"><span data-stu-id="4e648-142">**Assign users**</span></span>| <span data-ttu-id="4e648-143">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="4e648-143">Global administrator</span></span> | <span data-ttu-id="4e648-144">포털 관리자</span><span class="sxs-lookup"><span data-stu-id="4e648-144">Portal admin</span></span> | 

> [!NOTE]
> <span data-ttu-id="4e648-145">규정 준수 점수에서 준수 관리자로 이동 하 여 작업을 완료 하면 (예: 평가 관리) 브라우저가 새 탭을 열고 대화 상자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e648-145">When you go from Compliance Score to Compliance Manager to complete a task (for example, to manage assessments), your browser will open a new tab and a dialog box appears.</span></span> <span data-ttu-id="4e648-146">머리글이 "이미 Microsoft 클라우드 서비스 고객" 인 최상위 섹션에서</span><span class="sxs-lookup"><span data-stu-id="4e648-146">In the top section with the header, “Already a Microsoft cloud services customer?</span></span> <span data-ttu-id="4e648-147">계정에 로그인 하 고 " **로그인** 하 여 액세스 준수 관리자를 선택 합니다. 자격 증명을 다시 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4e648-147">Sign in to your account,” select **Sign In** to access Compliance Manager; you will not need to re-enter your credentials.</span></span>

### <a name="how-to-set-permissions-and-roles-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="4e648-148">Microsoft 365 준수 센터에서 사용 권한 및 역할을 설정 하는 방법</span><span class="sxs-lookup"><span data-stu-id="4e648-148">How to set permissions and roles in the Microsoft 365 compliance center</span></span>

<span data-ttu-id="4e648-149">Microsoft 365 준수 센터에서 사용 권한을 설정 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e648-149">To set permissions in the Microsoft 365 compliance center:</span></span>

1. <span data-ttu-id="4e648-150">[Microsoft 365 준수 센터로](https://compliance.microsoft.com) 이동 하 여 전역 관리자 계정으로 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e648-150">Go to the [Microsoft 365 compliance center](https://compliance.microsoft.com) and sign in with your global admin account.</span></span>
2. <span data-ttu-id="4e648-151">왼쪽 탐색 창에서 **사용 권한을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e648-151">Select **Permissions** on the left navigation pane.</span></span> <span data-ttu-id="4e648-152">여기에서 역할을 확인 하 고 사용 권한을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e648-152">From here, you can view roles and assign permissions.</span></span>

## <a name="configure-automatic-secure-score-updates"></a><span data-ttu-id="4e648-153">자동 보안 점수 업데이트 구성</span><span class="sxs-lookup"><span data-stu-id="4e648-153">Configure automatic Secure Score updates</span></span>

<span data-ttu-id="4e648-154">기본적으로 모든 새 테 넌 트에는 [보안 점수](../security/mtp/microsoft-secure-score.md) 자동 업데이트가 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e648-154">By default, all new tenants have [Secure Score](../security/mtp/microsoft-secure-score.md) automatic updates turned on.</span></span> <span data-ttu-id="4e648-155">즉, 보안 점수를 통해 모니터링 되는 모든 작업은 준수 점수에 있는 동일한 작업의 상태를 자동으로 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e648-155">This means that all actions that are monitored by Secure Score will automatically update the status for the same action in Compliance Score.</span></span>

<span data-ttu-id="4e648-156">전역 관리자는이 설정을 관리 하 여 모든 작업에 대해 자동 업데이트를 해제 하거나 작업에 대 한 업데이트를 개별적으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e648-156">Your global administrator can manage this setting to turn off automatic updates for all actions, or set updates for actions individually.</span></span>

<span data-ttu-id="4e648-157">공개 미리 보기 중에 보안 점수 업데이트를 관리 하려면 Microsoft Service Trust Portal (준수 관리자가 있는 경우)로 이동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e648-157">During public preview, you will need to go to the Microsoft Service Trust Portal (where Compliance Manger is located) to manage Secure Score updates.</span></span>

<span data-ttu-id="4e648-158">자동 보안 점수 업데이트를 관리 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e648-158">To manage automatic Secure Score updates, follow these steps:</span></span>

1. <span data-ttu-id="4e648-159">전역 관리자 계정을 사용 하 여 [서비스 신뢰 포털](https://servicetrust.microsoft.com) 에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e648-159">Sign in to the [Service Trust Portal](https://servicetrust.microsoft.com) with your global administrator account.</span></span>

2. <span data-ttu-id="4e648-160">서비스 보안 포털의 위쪽 메뉴 모음에 있는 **자세히**에서 **관리자** 를 선택 하 고 **설정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e648-160">On the Service Trust Portal top menu bar, under **More**, select **Admin** and then choose **Settings**.</span></span>

3. <span data-ttu-id="4e648-161">**보안 점수** 탭에서 **모든 동작에 대해 켤**해당 단추를 선택 하 고, **모든 작업**을 해제 하거나, 작업별 **로 설정 합니다.**</span><span class="sxs-lookup"><span data-stu-id="4e648-161">In the **Secure Score** tab, select the corresponding button to either **turn on for all actions**, **turn off for all actions**, or **set per action.**</span></span>

<span data-ttu-id="4e648-162">작업별 설정을 선택 하 **는** 경우 다음과 같은 추가 단계를 수행 하 여 개별 작업에 대 한 보안 점수 업데이트를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e648-162">If you choose **set per action,** take these additional steps to turn on Secure Score updates for individual actions:</span></span>

4. <span data-ttu-id="4e648-163">위쪽 메뉴에서 **준수 관리자** 를 선택 합니다 (참고: "준수 관리자 (클래식)"는 선택 하지 않음).</span><span class="sxs-lookup"><span data-stu-id="4e648-163">Select **Compliance Manager** from the top menu (note: do not select "Compliance Manager (classic)").</span></span>

5. <span data-ttu-id="4e648-164">화면의 오른쪽 위 모서리에 있는 **테 넌 트 관리** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e648-164">Select **Tenant Management** in the upper-right corner of your screen.</span></span>

6. <span data-ttu-id="4e648-165">**고객 작업** 창의 해당 하는 **작업** 열에서 줄임표 (**...**)를 사용 하 여 원하는 작업을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="4e648-165">On the **Customer Actions** pane, find your intended action with an ellipsis (**...**) under the **Affected Actions** column.</span></span> <span data-ttu-id="4e648-166">줄임표 (...)를 클릭 하 고 편집을 선택 **합니다.**</span><span class="sxs-lookup"><span data-stu-id="4e648-166">Click on the ellipses and select **Edit.**</span></span>

7. <span data-ttu-id="4e648-167">**보안 점수 연속 업데이트** 전환 스위치를 설정으로 전환 **합니다.**</span><span class="sxs-lookup"><span data-stu-id="4e648-167">Switch the **Secure Score continuous update** toggle switch to **On.**</span></span>

8. <span data-ttu-id="4e648-168">**저장을 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="4e648-168">Select **Save.**</span></span> <span data-ttu-id="4e648-169">이제 해당 작업에 대 한 보안 점수 지속적인 모니터링이 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e648-169">Secure Score continuous monitoring is now turned on for that action.</span></span>

<span data-ttu-id="4e648-170">**참고:** 전역 관리자만 모든 작업에 대해 자동 업데이트를 설정 하거나 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e648-170">**Note:** Only the global administrator can turn on or off automatic updates for all actions.</span></span> <span data-ttu-id="4e648-171">준수 관리자 관리자는 개별 작업에 대해 자동 업데이트를 설정할 수 있지만 모든 작업에 대해 전역적으로 수행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4e648-171">The Compliance Manager administrator can turn on automatic updates for individual actions, but not for all actions globally.</span></span>

<span data-ttu-id="4e648-172">[보안 점수 업데이트 관리](compliance-manager-release-notes.md#secure-score)에 대 한 자세한 내용을 읽으십시오.</span><span class="sxs-lookup"><span data-stu-id="4e648-172">Read more about [managing Secure Score updates](compliance-manager-release-notes.md#secure-score).</span></span>

## <a name="understand-the-compliance-score-dashboard"></a><span data-ttu-id="4e648-173">준수 점수 대시보드 이해</span><span class="sxs-lookup"><span data-stu-id="4e648-173">Understand the Compliance Score dashboard</span></span>

<span data-ttu-id="4e648-174">준수 점수 대시보드는 현재 준수 상태를 한눈에 파악할 수 있도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4e648-174">The Compliance Score dashboard is designed to provide you an at-a-glance view of your current compliance posture.</span></span>

<span data-ttu-id="4e648-175">![준수 점수-대시보드](../media/compliance-score-dashboard.png "준수 점수 대시보드")</span><span class="sxs-lookup"><span data-stu-id="4e648-175">![Compliance Score - dashboard](../media/compliance-score-dashboard.png "Compliance Score dashboard")</span></span>

### <a name="overall-compliance-score"></a><span data-ttu-id="4e648-176">전반적인 준수 점수</span><span class="sxs-lookup"><span data-stu-id="4e648-176">Overall compliance score</span></span>

<span data-ttu-id="4e648-177">주요 데이터 보호 표준 및 규정을 충족 하는 향상 된 작업을 완료 하는 데 필요한 점수를 기준으로 가장 중요 한 규정 준수 점수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4e648-177">Your compliance score, featured prominently at the top, shows a percentage based on points achievable for completing improvement actions addressing key data protection standards and regulations.</span></span>

<span data-ttu-id="4e648-178">처음으로 준수 점수가 제공 되는 경우 초기 점수는 기본 제공 되는 Microsoft 365 데이터 보호 기준을 기반으로 하며, 일반적인 업계 규정 및 표준을 포함 하는 컨트롤 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="4e648-178">When you come to Compliance Score for the first time, your initial score is based on the built-in Microsoft 365 data protection baseline—a set of controls that includes common industry regulations and standards.</span></span> <span data-ttu-id="4e648-179">규정 준수 점수가 기존 Microsoft 365 솔루션의 시스템을 검사 하기 때문에 조직에서 현재 사용 하 고 있는 개인 정보 및 보안 설정을 기반으로 준수 상태를 초기에 평가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e648-179">Because Compliance Score scans your system of existing Microsoft 365 solutions, it gives an initial assessment of your compliance posture based on privacy and security settings currently enabled by your organization.</span></span>

<span data-ttu-id="4e648-180">조직과 관련 된 평가를 추가 하면 점수가 더 많이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e648-180">As you add assessments that are relevant to your organization, your score becomes even more meaningful.</span></span> <span data-ttu-id="4e648-181">[점수를 계산 하는 방법](compliance-score-methodology.md)에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="4e648-181">Learn more about [how your score is calculated](compliance-score-methodology.md).</span></span>

### <a name="key-improvement-actions"></a><span data-ttu-id="4e648-182">주요 개선 작업</span><span class="sxs-lookup"><span data-stu-id="4e648-182">Key improvement actions</span></span>

<span data-ttu-id="4e648-183">이 섹션에서는 전체 준수 점수에 가장 큰 긍정적인 영향을 줄 수 있는 주요 향상 작업을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e648-183">This section lists the top improvement actions you can take right now to make the largest positive impact on your overall compliance score.</span></span> <span data-ttu-id="4e648-184">위험도가 높은 평가와 함께 완료 되지 않았거나 실패 한 작업이 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e648-184">It lists actions that are not completed or failed with the assessment with high risks.</span></span>

### <a name="solutions-that-affect-your-score"></a><span data-ttu-id="4e648-185">점수에 영향을 주는 솔루션</span><span class="sxs-lookup"><span data-stu-id="4e648-185">Solutions that affect your score</span></span>

<span data-ttu-id="4e648-186">이 섹션에서는 점수에 긍정적인 영향을 줄 수 있는 작업을 포함 하는 솔루션 및 각 솔루션에 포함 된 해결 되지 않은 향상 작업의 수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4e648-186">This section shows which solutions contain actions with the greatest opportunity to positively impact your score, and how many outstanding improvement actions you have in each solution.</span></span>

### <a name="compliance-score-breakdown"></a><span data-ttu-id="4e648-187">규정 준수 점수 분석</span><span class="sxs-lookup"><span data-stu-id="4e648-187">Compliance Score breakdown</span></span>

<span data-ttu-id="4e648-188">이 섹션에서는 다음과 같은 두 가지 방법으로 점수에 대 한 자세한 내용을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e648-188">This section gives you a more detailed view of your score in two different ways:</span></span>

- <span data-ttu-id="4e648-189">**범주**: "정보 보호" 또는 "장치 관리"와 같은 데이터 보호 범주 내의 전체 점수 비율을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e648-189">**Categories**: shows the percentage of your overall score within data protection categories, such as “protect information” or “manage devices.”</span></span>
- <span data-ttu-id="4e648-190">**평가**: GDPR 또는 NIST 800-53와 같은 특정 준수 및 데이터 보호 표준, 규정 또는 법규에 대 한 평가 관리에서 진행률을 관리할 비율을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4e648-190">**Assessments**: shows the percentage of your progress in managing assessments for particular compliance and data protection standards, regulations, or laws, such as GDPR or NIST 800-53.</span></span>

### <a name="filtering-your-dashboard-view"></a><span data-ttu-id="4e648-191">대시보드 보기 필터링</span><span class="sxs-lookup"><span data-stu-id="4e648-191">Filtering your dashboard view</span></span>

<span data-ttu-id="4e648-192">대시보드 보기를 필터링 하 여 특정 규정과 표준, 솔루션, 작업 유형, [설정 하는 평가 그룹](working-with-compliance-manager.md#groups)또는 데이터 보호 범주와 관련 된 항목만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e648-192">You can filter your dashboard view to see only the items related to particular regulations and standards, solutions, type of action, [groups of assessments you set up](working-with-compliance-manager.md#groups), or data protection categories.</span></span> <span data-ttu-id="4e648-193">이 방식으로 보기를 필터링 하면 대시보드의 점수가 필터링 되며, 필터 조건을 기준으로 하 여 총 가능한 점수를 얻은 점의 수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4e648-193">Filtering your view in this way will also filter the score on your dashboard, showing how many points you’ve achieved out of total possible points based on your filter criteria.</span></span>

<span data-ttu-id="4e648-194">필터를 적용 하려면</span><span class="sxs-lookup"><span data-stu-id="4e648-194">To apply filters:</span></span>

1. <span data-ttu-id="4e648-195">대시보드의 오른쪽 위에 있는 **필터** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e648-195">Select **Filter** on the upper-right side of the dashboard.</span></span>
2. <span data-ttu-id="4e648-196">플라이 아웃 **필터** 창에서 필터 조건을 선택한 다음 **적용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e648-196">Select your filter criteria from the flyout **Filters** pane, then select **Apply**.</span></span>

<span data-ttu-id="4e648-197">필터가 적용 되 면 점수가 실시간으로 조정 된 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e648-197">Once a filter is applied, you will see your score adjusted in real-time.</span></span> <span data-ttu-id="4e648-198">준수 점수 비율 및 분석 정보 및 개선 작업 및 솔루션은 필터 기준에 포함 된 데이터에만 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="4e648-198">The compliance score percentage and breakdown information, and the improvement actions and solutions, now only pertain to data covered by your filter criteria.</span></span> <span data-ttu-id="4e648-199">규정 준수 점수를 로그 아웃 하는 경우 필터링 된 보기는 다시 로그인 할 때 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e648-199">If you sign out of Compliance Score, your filtered view remains when you sign back in.</span></span>

<span data-ttu-id="4e648-200">필터를 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="4e648-200">To remove filters:</span></span>

- <span data-ttu-id="4e648-201">준수 점수 위의 **적용 된 필터** 제목에서 제거할 개별 필터 옆에 있는 **X** 를 선택 합니다. 사용자나</span><span class="sxs-lookup"><span data-stu-id="4e648-201">At the **Applied filters** heading above your compliance score, select the **X** next to the individual filter you want to remove; or</span></span>
- <span data-ttu-id="4e648-202">대시보드의 오른쪽 위에 있는 **필터** 를 선택 하 고 **필터 지우기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e648-202">Select **Filter** on the upper-right side of your dashboard, then select **Clear filters**.</span></span>

## <a name="next-step"></a><span data-ttu-id="4e648-203">다음 단계</span><span class="sxs-lookup"><span data-stu-id="4e648-203">Next step</span></span>

<span data-ttu-id="4e648-204">[규정 준수 점수 관련 작업](working-with-compliance-score.md) 을 방문 하 여 점수 개선을 위한 작업을 수행 하는 방법에 대 한 워크플로를 파악할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e648-204">Visit [Working with Compliance Score](working-with-compliance-score.md) to understand the workflow of how to take actions to improve your score.</span></span>
