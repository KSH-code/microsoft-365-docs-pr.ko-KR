---
title: '계정 사용 중지 '
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom:
- AdminSurgePortfolio
- fwlink 2133922 to Delete subscription heading
search.appverid:
- MET150
description: Microsoft에서 계정을 닫는 방법을 배워야 합니다.
ms.openlocfilehash: bdcf4408ddc9c198fab1d68b4c096fad9059b975
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376320"
---
# <a name="close-your-account"></a><span data-ttu-id="b852e-103">계정 사용 중지 </span><span class="sxs-lookup"><span data-stu-id="b852e-103">Close your account</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="b852e-104">관리 센터가 변경되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b852e-104">The admin center is changing.</span></span> <span data-ttu-id="b852e-105">사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b852e-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="b852e-106">Microsoft 계정을 폐쇄하면 계정과 관련된 모든 정보가 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="b852e-106">When you close your account with Microsoft, all information related to your account is deleted.</span></span> <span data-ttu-id="b852e-107">이 정보에는 구독, 라이선스, 지불 방법, 사용자 및 사용자 데이터가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b852e-107">This information includes subscriptions, licenses, payment methods, users, and user data.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b852e-108">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="b852e-108">Before you begin</span></span>

<span data-ttu-id="b852e-109">이 프로세스를 시작하기 전에 보존하려는 데이터를 백업하세요.</span><span class="sxs-lookup"><span data-stu-id="b852e-109">Before you start this process, make sure to back up any data that you want to preserve.</span></span>

<span data-ttu-id="b852e-110">이 문서의 작업을 수행하려면 전역 관리자 또는 대금 청구 관리자 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b852e-110">You must be a Global or Billing admin to do the tasks in this article.</span></span> <span data-ttu-id="b852e-111">자세한 내용은 [관리자 역할 정보](../admin/add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b852e-111">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="step-1-delete-users"></a><span data-ttu-id="b852e-112">1단계: 사용자 삭제</span><span class="sxs-lookup"><span data-stu-id="b852e-112">Step 1: Delete users</span></span>

<span data-ttu-id="b852e-113">전역 관리자 한 명을 제외한 모든 사용자를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="b852e-113">Delete all users except for one global administrator.</span></span> <span data-ttu-id="b852e-114">전역 관리자가 계정을 닫는 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="b852e-114">The global administrator completes the steps to close the account.</span></span> <span data-ttu-id="b852e-115">이 프로세스가 끝나면 디렉터리를 삭제하려면 먼저 다른 모든 사용자를 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b852e-115">Before you can delete the directory at the end of this process, you must delete all other users.</span></span>

<span data-ttu-id="b852e-116">사용자가 오프-프레미스에서 동기화되는 경우 먼저 동기화를 해제한 다음 Azure Portal 또는 Azure PowerShell cmdlet을 사용하여 클라우드 디렉터리의 사용자를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="b852e-116">If users are synchronized from on-premises, first turn off sync, then delete the users in the cloud directory by using the Azure portal or Azure PowerShell cmdlets.</span></span>

<span data-ttu-id="b852e-117">사용자를 삭제하려면 사용자 관리 <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">관리자: 하나 이상의 사용자 삭제를 참조하세요.</a></span><span class="sxs-lookup"><span data-stu-id="b852e-117">To delete users, see <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">User management admin: Delete one or more users</a>.</span></span>

<span data-ttu-id="b852e-118"><a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> PowerShell cmdlet을 사용하여 사용자를 대량으로 삭제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b852e-118">You can also use the <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> PowerShell cmdlet to delete users in bulk.</span></span>

<span data-ttu-id="b852e-119">조직에서 Microsoft Azure AD(Azure Active Directory)와 동기화되는 Active Directory를 사용하는 경우 대신 Active Directory에서 사용자 계정을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="b852e-119">If your organization uses Active Directory that synchronizes with Microsoft Azure Active Directory (Azure AD), delete the user account from Active Directory, instead.</span></span> <span data-ttu-id="b852e-120">자세한 내용은 <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">Azure Active Directory에서 사용자 일괄 삭제를 참조하세요.</a></span><span class="sxs-lookup"><span data-stu-id="b852e-120">For instructions, see <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">Bulk delete users in Azure Active Directory</a>.</span></span>

## <a name="step-2-cancel-all-active-subscriptions"></a><span data-ttu-id="b852e-121">2단계: 활성 구독 모두 취소</span><span class="sxs-lookup"><span data-stu-id="b852e-121">Step 2: Cancel all active subscriptions</span></span>

1. <span data-ttu-id="b852e-122">관리 센터에서 **빌링** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">제품</a>페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b852e-122">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="b852e-123">제품 **탭에서** 활성 구독을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b852e-123">On the **Products** tab, find an active subscription.</span></span> <span data-ttu-id="b852e-124">**추가 작업**(점 3개)을 선택한 다음 **구독 취소** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b852e-124">Select **More actions** (three dots), then select **Cancel subscription**.</span></span>
3. <span data-ttu-id="b852e-125">**구독 취소** 창에서 취소 이유를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b852e-125">In the **Cancel subscription** pane, choose a reason why you're canceling.</span></span> <span data-ttu-id="b852e-126">원하는 경우, 피드백을 제공하세요.</span><span class="sxs-lookup"><span data-stu-id="b852e-126">Optionally, provide any feedback.</span></span>
4. <span data-ttu-id="b852e-127">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b852e-127">Select **Save**.</span></span>
5. <span data-ttu-id="b852e-128">활성 구독을 모두 취소하려면 1~4단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="b852e-128">Repeat steps 1 through 4 to cancel all active subscriptions.</span></span>

## <a name="step-3-delete-all-disabled-subscriptions"></a><span data-ttu-id="b852e-129">3단계: 비활성화된 모든 구독 삭제</span><span class="sxs-lookup"><span data-stu-id="b852e-129">Step 3: Delete all disabled subscriptions</span></span>

1. <span data-ttu-id="b852e-130">관리 센터에서 **빌링** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">제품</a>페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b852e-130">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="b852e-131">제품 **탭에서** 비활성화된 구독을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b852e-131">On the **Products** tab, select a disabled subscription.</span></span>
3. <span data-ttu-id="b852e-132">구독 세부 정보 페이지의 구독 및 **결제** 설정 섹션에서 구독 **삭제를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b852e-132">On the subscription details page, in the **Subscription and payment settings** section, select **Delete subscription**.</span></span>
4. <span data-ttu-id="b852e-133">구독 **삭제 창에서** 구독 **삭제를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b852e-133">In the **Delete subscription** pane, select **Delete subscription**.</span></span>
5. <span data-ttu-id="b852e-134">구독 **삭제 대화** 상자에서 예를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b852e-134">In the **Delete subscription** dialog box, select **Yes**.</span></span>
6. <span data-ttu-id="b852e-135">사용하지 않도록 설정한 각 구독에 대해 모든 구독이 삭제될 때까지 3-5단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="b852e-135">For each disabled subscription, repeat steps 3 through 5 until all subscriptions are deleted.</span></span>

> [!NOTE]
> <span data-ttu-id="b852e-136">사용하지 않도록 설정한 구독을 즉시 삭제할 수 없는 경우 고객 지원에 <a href="https://go.microsoft.com/fwlink/p/?linkid=518322" target="_blank">문의하세요.</a></span><span class="sxs-lookup"><span data-stu-id="b852e-136">If you're unable to immediately delete a disabled subscription, <a href="https://go.microsoft.com/fwlink/p/?linkid=518322" target="_blank">contact support</a></span></span>

## <a name="step-4-disable-multi-factor-authentication"></a><span data-ttu-id="b852e-137">4단계: 다단계 인증 사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="b852e-137">Step 4: Disable multi-factor authentication</span></span>

1. <span data-ttu-id="b852e-138">전역 관리자 계정으로 관리 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="b852e-138">Sign in to the admin center with a Global administrator account.</span></span> <span data-ttu-id="b852e-139">역할이 있는지 확인하려면 조직에서 관리자 역할 [확인을 참조하세요.](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization)</span><span class="sxs-lookup"><span data-stu-id="b852e-139">To verify what roles you have, see [Check admin roles in your organization](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization).</span></span>
2. <span data-ttu-id="b852e-140">사용자 활성 사용자  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">페이지로</a> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b852e-140">Go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
3. <span data-ttu-id="b852e-141">다단계 **인증을 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="b852e-141">Choose **Multi-factor authentication**.</span></span>
4. <span data-ttu-id="b852e-142">다단계 인증 페이지에서 현재 사용 중인 전역 관리자 계정을 제외한 모든 계정을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b852e-142">On the multi-factor authentication page, disable all accounts except for the global admin account that you're currently using.</span></span>

<span data-ttu-id="b852e-143">PowerShell을 사용하여 여러 사용자에 대해 다단계 인증을 <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">사용하지 않도록 설정할 수도 있습니다.</a></span><span class="sxs-lookup"><span data-stu-id="b852e-143">You can also <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">use PowerShell to disable multi-factor authentication for multiple users</a>.</span></span>

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a><span data-ttu-id="b852e-144">5단계: Azure Active Directory에서 디렉터리 삭제</span><span class="sxs-lookup"><span data-stu-id="b852e-144">Step 5: Delete the directory in Azure Active Directory</span></span>

1. <span data-ttu-id="b852e-145">전역 관리자 계정으로 <a href="https://aad.portal.azure.com/" target="_blank">Azure AD</a> 관리 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="b852e-145">Sign in to the <a href="https://aad.portal.azure.com/" target="_blank">Azure AD admin center</a> with a Global administrator account.</span></span>
2. <span data-ttu-id="b852e-146">**Azure Active Directory** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b852e-146">Select **Azure Active Directory**.</span></span>
3. <span data-ttu-id="b852e-147">삭제할 조직으로 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="b852e-147">Switch to the organization that you want to delete.</span></span>
4. <span data-ttu-id="b852e-148">**테넌트 삭제를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b852e-148">Select **Delete tenant**.</span></span>
5. <span data-ttu-id="b852e-149">조직에서 하나 이상의 검사에 실패하면 검사를 통과하는 방법에 대한 추가 정보 링크가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b852e-149">If your organization fails one or more checks, you see a link to more information on how to pass the checks.</span></span> <span data-ttu-id="b852e-150">모든 검사를 통과한 후 **삭제를** 선택하여 프로세스를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="b852e-150">After you pass all checks, select **Delete** to complete the process.</span></span>

<span data-ttu-id="b852e-151">이 마지막 단계를 완료하면 Microsoft 계정이 닫히고 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="b852e-151">After you complete this final step, your account with Microsoft is closed and deleted.</span></span>