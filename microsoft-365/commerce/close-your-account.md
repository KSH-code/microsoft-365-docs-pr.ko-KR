---
title: '계정 사용 중지 '
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: ''
search.appverid:
- MET150
description: Microsoft에서 계정을 닫는 방법을 알아봅니다.
ms.openlocfilehash: e41d11502b0c0f738cc23405c387bd5fca1cb0fe
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "44141281"
---
# <a name="close-your-account"></a><span data-ttu-id="70559-103">계정 사용 중지 </span><span class="sxs-lookup"><span data-stu-id="70559-103">Close your account</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="70559-104">관리 센터가 변경 되는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="70559-104">The admin center is changing.</span></span> <span data-ttu-id="70559-105">환경이 여기에 나와 있는 세부 정보와 일치 하지 않으면 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="70559-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="70559-106">Microsoft 계정을 폐쇄하면 계정과 관련된 모든 정보가 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="70559-106">When you close your account with Microsoft, all information related to your account is deleted.</span></span> <span data-ttu-id="70559-107">이 정보에는 구독, 라이선스, 지불 방법, 사용자 및 사용자 데이터가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="70559-107">This information includes subscriptions, licenses, payment methods, users, and user data.</span></span> <span data-ttu-id="70559-108">이 프로세스를 시작 하기 전에 보존 하려는 모든 데이터를 백업 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70559-108">Before you start this process, make sure to backup any data that you want to preserve.</span></span>

## <a name="step-1-delete-users"></a><span data-ttu-id="70559-109">1 단계: 사용자 삭제</span><span class="sxs-lookup"><span data-stu-id="70559-109">Step 1: Delete users</span></span>

<span data-ttu-id="70559-110">계정을 닫는 단계를 완료 한 전역 관리자를 제외한 모든 사용자를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="70559-110">Delete all users except for one global administrator who completes the steps to close the account.</span></span> <span data-ttu-id="70559-111">이 프로세스가 완료 될 때 디렉터리를 삭제 하려면 먼저 다른 모든 사용자를 삭제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70559-111">Before you can delete the directory at the end of this process, you must delete all other users.</span></span>

<span data-ttu-id="70559-112">사용자가 온-프레미스 로부터 동기화 되 면 먼저 동기화를 해제 한 다음 Azure portal 또는 Azure PowerShell cmdlet을 사용 하 여 클라우드 디렉터리의 사용자를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="70559-112">If users are synchronized from on-premises, first turn off sync, then delete the users in the cloud directory by using the Azure portal or Azure PowerShell cmdlets.</span></span>

<span data-ttu-id="70559-113">사용자를 삭제 하려면 <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">사용자 관리 관리자: 하나 이상의 사용자 삭제</a>를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="70559-113">To delete users, see <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">User management admin: Delete one or more users</a>.</span></span>

<span data-ttu-id="70559-114"><a href="https://go.microsoft.com/fwlink/?linkid=842230">Get-msoluser</a> PowerShell cmdlet을 사용 하 여 사용자를 대량으로 삭제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70559-114">You can also use the <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> PowerShell cmdlet to delete users in bulk.</span></span>

<span data-ttu-id="70559-115">조직에서 Azure AD와 동기화 되는 Active Directory를 사용 하는 경우 대신 Active Directory에서 사용자 계정을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="70559-115">If your organization uses Active Directory that synchronizes with Azure AD, delete the user account from Active Directory, instead.</span></span> <span data-ttu-id="70559-116">자세한 내용은 <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">Azure Active Directory에서 사용자 대량 삭제</a>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="70559-116">For instructions, see <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">Bulk delete users in Azure Active Directory</a>.</span></span>

## <a name="step-2-cancel-all-active-subscriptions"></a><span data-ttu-id="70559-117">2 단계: 모든 활성 구독 취소</span><span class="sxs-lookup"><span data-stu-id="70559-117">Step 2: Cancel all active subscriptions</span></span>

1. <span data-ttu-id="70559-118">관리 센터에서<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">제품</a> **청구** > 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="70559-118">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

2. <span data-ttu-id="70559-119">구독 목록이 **표** 보기에 있는 경우 오른쪽에서 **카드**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="70559-119">If the subscriptions list is in **Table** view, on the right, select **Cards**.</span></span>

3. <span data-ttu-id="70559-120">활성 구독을 찾고 **& 작업 설정** 섹션에서 **구독 취소**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="70559-120">Find an active subscription, and in the **Settings & Actions** section, select **Cancel subscription**.</span></span>

4. <span data-ttu-id="70559-121">화면의 지시에 따라 프로세스를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="70559-121">Follow the prompts to finish the process.</span></span>

5. <span data-ttu-id="70559-122">1 ~ 4 단계를 반복 하 여 모든 활성 구독을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="70559-122">Repeat steps 1 through 4 to cancel all active subscriptions.</span></span>

## <a name="step-3-delete-all-disabled-subscriptions"></a><span data-ttu-id="70559-123">3 단계: 사용 하지 않는 구독 모두 삭제</span><span class="sxs-lookup"><span data-stu-id="70559-123">Step 3: Delete all disabled subscriptions</span></span>

1. <span data-ttu-id="70559-124">관리 센터에서<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">제품</a> **청구** > 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="70559-124">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

2. <span data-ttu-id="70559-125">구독 목록이 **표** 보기에 있는 경우 오른쪽에서 **카드**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="70559-125">If the subscriptions list is in **Table** view, on the right, select **Cards**.</span></span>

3. <span data-ttu-id="70559-126">**구독 상태**옆에서 **사용 안 함을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="70559-126">Next to **Subscription status**, select **Disabled**.</span></span>

4. <span data-ttu-id="70559-127">사용 하지 않도록 설정 된 구독을 찾은 다음, **& 동작** 섹션에서 **삭제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="70559-127">Find a disabled subscription, and in the **Settings & Actions** section, select **Delete**.</span></span>

5. <span data-ttu-id="70559-128">**구독 삭제** 대화 상자에서 **영향** 확인 확인란을 선택 하 고 **구독 삭제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="70559-128">In the **Delete subscription** dialog box, select the **I understand the impact** check box, then select **Delete subscription**.</span></span>

6. <span data-ttu-id="70559-129">사용 하지 않도록 설정 된 각 구독에 대해 4 ~ 5 단계를 반복 하 여 모든 구독을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="70559-129">For each disabled subscription, repeat steps 4 and 5 until all subscriptions have been deleted.</span></span>

## <a name="step-4-disable-multi-factor-authentication"></a><span data-ttu-id="70559-130">4 단계: 다단계 인증 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="70559-130">Step 4: Disable multi-factor authentication</span></span>

1. <span data-ttu-id="70559-131">관리 센터에서 **사용자** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="70559-131">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="70559-132">**다단계 인증**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="70559-132">Choose **Multi-factor authentication**.</span></span>

3. <span data-ttu-id="70559-133">Multi-factor authentication 페이지에서 현재 사용 중인 전역 관리자 계정을 제외한 모든 계정을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="70559-133">On the multi-factor authentication page, disable all accounts except for the global admin account that you're currently using.</span></span>

<span data-ttu-id="70559-134">또한 <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">PowerShell을 사용 하 여 여러 사용자에 대해 multi-factor authentication을 사용 하지 않도록 설정할</a>수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70559-134">You can also <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">use PowerShell to disable multi-factor authentication for multiple users</a>.</span></span>

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a><span data-ttu-id="70559-135">5 단계: Azure Active Directory에서 디렉터리 삭제</span><span class="sxs-lookup"><span data-stu-id="70559-135">Step 5: Delete the directory in Azure Active Directory</span></span>

1. <span data-ttu-id="70559-136">전역 관리자 계정을 사용 하 여 <a href="https://aad.portal.azure.com/" target="_blank">AZURE AD 관리 센터</a> 에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="70559-136">Sign in to the <a href="https://aad.portal.azure.com/" target="_blank">Azure AD admin center</a> with a Global Administrator account.</span></span>

2. <span data-ttu-id="70559-137">**Azure Active Directory**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="70559-137">Select **Azure Active Directory**.</span></span>

3. <span data-ttu-id="70559-138">삭제 하려는 디렉터리로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="70559-138">Switch to the directory you want to delete.</span></span>

4. <span data-ttu-id="70559-139">**디렉터리 삭제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="70559-139">Select **Delete directory**.</span></span>

5. <span data-ttu-id="70559-140">디렉터리에서 하나 이상의 검사가 실패 하면 검사 통과 방법에 대 한 자세한 내용을 확인할 수 있는 링크가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70559-140">If your directory fails one or more checks, you see a link to more information on how to pass the checks.</span></span> <span data-ttu-id="70559-141">모든 검사를 통과 한 후에 **삭제** 를 선택 하 여 프로세스를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="70559-141">After you pass all checks, select **Delete** to complete the process.</span></span>

<span data-ttu-id="70559-142">마지막 단계를 완료 한 후에는 Microsoft의 계정을 닫고 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="70559-142">After you complete this final step, your account with Microsoft is closed and deleted.</span></span>
