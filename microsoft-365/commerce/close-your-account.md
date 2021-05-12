---
title: '계정 사용 중지 '
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- fwlink 2133922 to Delete subscription heading
- commerce_subscription
search.appverid: MET150
description: Microsoft에서 계정을 닫는 방법을 알아보하세요.
ms.date: 04/02/2021
ms.openlocfilehash: 767a82088500bc24c0d4755a2dafd40742fc796c
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2021
ms.locfileid: "52331769"
---
# <a name="close-your-account"></a><span data-ttu-id="c5d3c-103">계정 사용 중지 </span><span class="sxs-lookup"><span data-stu-id="c5d3c-103">Close your account</span></span>

<span data-ttu-id="c5d3c-104">Microsoft 계정을 폐쇄하면 계정과 관련된 모든 정보가 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5d3c-104">When you close your account with Microsoft, all information related to your account is deleted.</span></span> <span data-ttu-id="c5d3c-105">이 정보에는 구독, 라이선스, 지불 방법, 사용자 및 사용자 데이터가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5d3c-105">This information includes subscriptions, licenses, payment methods, users, and user data.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="c5d3c-106">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="c5d3c-106">Before you begin</span></span>

<span data-ttu-id="c5d3c-107">이 프로세스를 시작하기 전에 보존하려는 데이터를 백업하세요.</span><span class="sxs-lookup"><span data-stu-id="c5d3c-107">Before you start this process, make sure to back up any data that you want to preserve.</span></span>

<span data-ttu-id="c5d3c-108">이 문서의 작업을 수행하려면 전역 관리자 또는 청구 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d3c-108">You must be a Global or Billing admin to do the tasks in this article.</span></span> <span data-ttu-id="c5d3c-109">자세한 내용은 [관리자 역할 정보](../admin/add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5d3c-109">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="step-1-delete-users"></a><span data-ttu-id="c5d3c-110">1단계: 사용자 삭제</span><span class="sxs-lookup"><span data-stu-id="c5d3c-110">Step 1: Delete users</span></span>

<span data-ttu-id="c5d3c-111">전역 관리자 한 명을 제외한 모든 사용자를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d3c-111">Delete all users except for one global administrator.</span></span> <span data-ttu-id="c5d3c-112">전역 관리자가 계정을 닫는 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d3c-112">The global administrator completes the steps to close the account.</span></span> <span data-ttu-id="c5d3c-113">이 프로세스가 끝나면 디렉터리를 삭제하려면 먼저 다른 모든 사용자를 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d3c-113">Before you can delete the directory at the end of this process, you must delete all other users.</span></span>

<span data-ttu-id="c5d3c-114">사용자가 사내에서 동기화되는 경우 먼저 동기화를 해제한 다음 Azure Portal 또는 Azure PowerShell cmdlet을 사용하여 클라우드 디렉터리의 사용자를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d3c-114">If users are synchronized from on-premises, first turn off sync, then delete the users in the cloud directory by using the Azure portal or Azure PowerShell cmdlets.</span></span>

<span data-ttu-id="c5d3c-115">사용자를 삭제하려면 사용자 관리 관리자: 하나 이상의 사용자 [삭제를 참조하세요.](../admin/add-users/delete-a-user.md#user-management-admin-delete-one-or-more-users-from-office-365)</span><span class="sxs-lookup"><span data-stu-id="c5d3c-115">To delete users, see [User management admin: Delete one or more users](../admin/add-users/delete-a-user.md#user-management-admin-delete-one-or-more-users-from-office-365).</span></span>

<span data-ttu-id="c5d3c-116">[Remove-MsolUser](/powershell/module/msonline/remove-msoluser) PowerShell cmdlet을 사용하여 사용자를 대량으로 삭제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5d3c-116">You can also use the [Remove-MsolUser](/powershell/module/msonline/remove-msoluser) PowerShell cmdlet to delete users in bulk.</span></span>

<span data-ttu-id="c5d3c-117">조직에서 Microsoft Azure AD(Azure Active Directory)와 동기화하는 Active Directory를 사용하는 경우 대신 Active Directory에서 사용자 계정을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d3c-117">If your organization uses Active Directory that synchronizes with Microsoft Azure Active Directory (Azure AD), delete the user account from Active Directory, instead.</span></span> <span data-ttu-id="c5d3c-118">자세한 내용은 Azure Active Directory에서 사용자 대량 [삭제를 참조하세요.](/azure/active-directory/users-groups-roles/users-bulk-delete)</span><span class="sxs-lookup"><span data-stu-id="c5d3c-118">For instructions, see [Bulk delete users in Azure Active Directory](/azure/active-directory/users-groups-roles/users-bulk-delete).</span></span>

## <a name="step-2-cancel-all-active-subscriptions"></a><span data-ttu-id="c5d3c-119">2단계: 활성 구독 모두 취소</span><span class="sxs-lookup"><span data-stu-id="c5d3c-119">Step 2: Cancel all active subscriptions</span></span>

1. <span data-ttu-id="c5d3c-120">관리 센터에서 **빌링** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">제품</a>페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d3c-120">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="c5d3c-121">제품 **탭에서** 활성 구독을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5d3c-121">On the **Products** tab, find an active subscription.</span></span> <span data-ttu-id="c5d3c-122">**추가 작업**(점 3개)을 선택한 다음 **구독 취소** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d3c-122">Select **More actions** (three dots), then select **Cancel subscription**.</span></span>
3. <span data-ttu-id="c5d3c-123">**구독 취소** 창에서 취소 이유를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d3c-123">In the **Cancel subscription** pane, choose a reason why you're canceling.</span></span> <span data-ttu-id="c5d3c-124">원하는 경우, 피드백을 제공하세요.</span><span class="sxs-lookup"><span data-stu-id="c5d3c-124">Optionally, provide any feedback.</span></span>
4. <span data-ttu-id="c5d3c-125">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d3c-125">Select **Save**.</span></span>
5. <span data-ttu-id="c5d3c-126">활성 구독을 모두 취소하려면 1~4단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d3c-126">Repeat steps 1 through 4 to cancel all active subscriptions.</span></span>

## <a name="step-3-delete-all-disabled-subscriptions"></a><span data-ttu-id="c5d3c-127">3단계: 사용하지 않도록 설정한 모든 구독 삭제</span><span class="sxs-lookup"><span data-stu-id="c5d3c-127">Step 3: Delete all disabled subscriptions</span></span>

1. <span data-ttu-id="c5d3c-128">관리 센터에서 **빌링** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">제품</a>페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d3c-128">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="c5d3c-129">제품 **탭에서** 비활성화된 구독을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d3c-129">On the **Products** tab, select a disabled subscription.</span></span>
3. <span data-ttu-id="c5d3c-130">구독 세부 정보 페이지의 구독 및 결제 설정 **섹션에서** 구독 **삭제를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c5d3c-130">On the subscription details page, in the **Subscription and payment settings** section, select **Delete subscription**.</span></span>
4. <span data-ttu-id="c5d3c-131">구독 **삭제 창에서** 구독 **삭제를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c5d3c-131">In the **Delete subscription** pane, select **Delete subscription**.</span></span>
5. <span data-ttu-id="c5d3c-132">구독 **삭제 대화** 상자에서 예를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c5d3c-132">In the **Delete subscription** dialog box, select **Yes**.</span></span>
6. <span data-ttu-id="c5d3c-133">사용하지 않도록 설정한 각 구독에 대해 모든 구독이 삭제될 때까지 3-5단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d3c-133">For each disabled subscription, repeat steps 3 through 5 until all subscriptions are deleted.</span></span>

> [!NOTE]
> <span data-ttu-id="c5d3c-134">사용하지 않도록 설정한 구독을 즉시 삭제할 수 없는 경우 고객 [지원에 문의하세요.](../business-video/get-help-support.md)</span><span class="sxs-lookup"><span data-stu-id="c5d3c-134">If you're unable to immediately delete a disabled subscription, [contact support](../business-video/get-help-support.md).</span></span>

## <a name="step-4-disable-multi-factor-authentication"></a><span data-ttu-id="c5d3c-135">4단계: 다단계 인증 사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="c5d3c-135">Step 4: Disable multi-factor authentication</span></span>

1. <span data-ttu-id="c5d3c-136">전역 관리자 계정으로 관리 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d3c-136">Sign in to the admin center with a Global administrator account.</span></span> <span data-ttu-id="c5d3c-137">역할이 있는지 확인하려면 [조직에서 관리자 역할 확인을 참조하세요.](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization)</span><span class="sxs-lookup"><span data-stu-id="c5d3c-137">To verify what roles you have, see [Check admin roles in your organization](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization).</span></span>
2. <span data-ttu-id="c5d3c-138">사용자 활성 **사용자**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">페이지로</a> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d3c-138">Go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
3. <span data-ttu-id="c5d3c-139">다단계 **인증 을 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="c5d3c-139">Choose **Multi-factor authentication**.</span></span>
4. <span data-ttu-id="c5d3c-140">다단계 인증 페이지에서 현재 사용 중인 전역 관리자 계정을 제외한 모든 계정을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d3c-140">On the multi-factor authentication page, disable all accounts except for the global admin account that you're currently using.</span></span>

<span data-ttu-id="c5d3c-141">PowerShell을 사용하여 여러 사용자에 대해 [다단계 인증을](/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell)사용하지 않도록 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5d3c-141">You can also [use PowerShell to disable multi-factor authentication for multiple users](/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell).</span></span>


## <a name="step-5-delete-the-directory-in-azure-active-directory"></a><span data-ttu-id="c5d3c-142">5단계: Azure Active Directory에서 디렉터리 삭제</span><span class="sxs-lookup"><span data-stu-id="c5d3c-142">Step 5: Delete the directory in Azure Active Directory</span></span>

1. <span data-ttu-id="c5d3c-143">전역 관리자 계정으로 <a href="https://aad.portal.azure.com/" target="_blank">Azure AD</a> 관리 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d3c-143">Sign in to the <a href="https://aad.portal.azure.com/" target="_blank">Azure AD admin center</a> with a Global administrator account.</span></span>
2. <span data-ttu-id="c5d3c-144">**Azure Active Directory** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d3c-144">Select **Azure Active Directory**.</span></span>
3. <span data-ttu-id="c5d3c-145">삭제할 조직으로 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d3c-145">Switch to the organization that you want to delete.</span></span>
4. <span data-ttu-id="c5d3c-146">**테넌트 삭제를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c5d3c-146">Select **Delete tenant**.</span></span>
5. <span data-ttu-id="c5d3c-147">조직에서 하나 이상의 검사에 실패하면 검사를 통과하는 방법에 대한 추가 정보 링크가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5d3c-147">If your organization fails one or more checks, you see a link to more information on how to pass the checks.</span></span> <span data-ttu-id="c5d3c-148">모든 검사를 통과한 후 삭제를 **선택하여** 프로세스를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d3c-148">After you pass all checks, select **Delete** to complete the process.</span></span>

<span data-ttu-id="c5d3c-149">이 마지막 단계를 완료하면 Microsoft 계정이 닫히고 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5d3c-149">After you complete this final step, your account with Microsoft is closed and deleted.</span></span>
