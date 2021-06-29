---
title: 1단계 - 직원이 로그인하지 못하게 Microsoft 365
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: 이전 직원의 로그인을 차단하고 Microsoft 365 차단합니다.
ms.openlocfilehash: 58b65a0a886460e8be01635c857433773cfc9059
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177120"
---
# <a name="step-1---prevent-a-former-employee-from-logging-in-and-block-access-to-microsoft-365-services"></a><span data-ttu-id="be9e8-103">1단계 - 이전 직원이 로그인하지 못하게 방지하고 Microsoft 365 액세스 차단</span><span class="sxs-lookup"><span data-stu-id="be9e8-103">Step 1 - Prevent a former employee from logging in and block access to Microsoft 365 services</span></span>

<span data-ttu-id="be9e8-104">사용자의 로그인 액세스를 즉시 차단해야 하는 경우 암호를 다시 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be9e8-104">If you need to immediately prevent a user's sign-in access, you should reset their password.</span></span> <span data-ttu-id="be9e8-105">이 단계에서는 사용자의 로그인을 강제로 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="be9e8-105">In this step, force a sign out of the user from Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="be9e8-106">다른 관리자에 대한 로그인을 시작하려면 전역 관리자로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be9e8-106">You need to be a global administrator to initiate sign-out for other administrators.</span></span> <span data-ttu-id="be9e8-107">관리자가 아닌 사용자의 경우 사용자 관리자 또는 헬프데스크 관리자 사용자를 사용하여 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be9e8-107">For non administrator users, you can use a User Administrator or a Helpdesk Administrator user to perform this action.</span></span> [<span data-ttu-id="be9e8-108">관리자 역할에 대해 자세히 알아보시고</span><span class="sxs-lookup"><span data-stu-id="be9e8-108">Learn more about the Admin Roles</span></span>](about-admin-roles.md)

1. <span data-ttu-id="be9e8-109">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다..</span><span class="sxs-lookup"><span data-stu-id="be9e8-109">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="be9e8-110">사용자 이름 옆의 상자를 선택한 다음 암호 다시 설정을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="be9e8-110">Select the box next to the user's name, and then select **Reset password**.</span></span>
3. <span data-ttu-id="be9e8-111">새 암호를 입력한 다음 다시 설정을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="be9e8-111">Enter a new password, and then select **Reset**.</span></span> <span data-ttu-id="be9e8-112">(보내지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="be9e8-112">(Don't send it to them.)</span></span>
4. <span data-ttu-id="be9e8-113">사용자의 이름을 선택하여 속성 창으로 이동하고 계정 탭에서 모든 세션에서 **서명을 선택합니다.** </span><span class="sxs-lookup"><span data-stu-id="be9e8-113">Select the user's name to go to their properties pane, and on the **Account** tab, select **Sign out of all sessions**.</span></span>

<span data-ttu-id="be9e8-114">1시간 이내에 또는 현재 Microsoft 365 페이지에서 나면 다시 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="be9e8-114">Within an hour - or after they leave the current Microsoft 365 page they are on - they're prompted to sign in again.</span></span> <span data-ttu-id="be9e8-115">액세스 토큰은 한 시간 동안 양호하기 때문에 시간 표시 막대는 해당 토큰에 남아 있는 시간 및 현재 웹 페이지를 탐색하는지 여부에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="be9e8-115">An access token is good for an hour, so the timeline depends on how much time is left on that token, and whether they navigate out of their current webpage.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="be9e8-116">사용자가 사서함에 있는 웹용 Outlook 사서함을 클릭하는 것만이 즉시 시작되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be9e8-116">If the user is in Outlook on the web, just clicking around in their mailbox, they may not be kicked out immediately.</span></span> <span data-ttu-id="be9e8-117">다른 타일(예: OneDrive)을 선택하거나 브라우저를 새로 고치자마자 로그인이 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="be9e8-117">As soon as they select a different tile, such as OneDrive, or refresh their browser, the sign-out is initiated.</span></span>
  
<span data-ttu-id="be9e8-118">PowerShell을 사용하여 사용자를 즉시 로그인하기 위해 [Revoke-AzureADUserAllRefreshToken](/powershell/module/azuread/revoke-azureaduserallrefreshtoken) cmdlet을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="be9e8-118">To use PowerShell to sign out a user immediately, see the [Revoke-AzureADUserAllRefreshToken](/powershell/module/azuread/revoke-azureaduserallrefreshtoken) cmdlet.</span></span>
  
<span data-ttu-id="be9e8-119">전자 메일에서 다른 사람을 제거하는 데 걸리는 시간에 대한 자세한 내용은 [직원의 전자 메일 세션 종료에 대해 알아야 할 사항](remove-former-employee-step-7.md#what-you-need-to-know-about-terminating-an-employees-email-session)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="be9e8-119">For more information about how long it takes to get someone out of email, see [What you need to know about terminating an employee's email session](remove-former-employee-step-7.md#what-you-need-to-know-about-terminating-an-employees-email-session).</span></span>

## <a name="block-a-former-employees-access-to-microsoft-365-services"></a><span data-ttu-id="be9e8-120">이전 직원의 서비스 액세스 Microsoft 365 차단</span><span class="sxs-lookup"><span data-stu-id="be9e8-120">Block a former employee's access to Microsoft 365 services</span></span>

> [!IMPORTANT]
 > <span data-ttu-id="be9e8-121">계정을 차단하는 데 최대 24시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be9e8-121">Blocking an account can take up to 24 hours to take effect.</span></span> <span data-ttu-id="be9e8-122">사용자의 로그인 액세스를 즉시 차단해야 하는 경우 위의 단계를 수행하고 암호를 다시 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="be9e8-122">If you need to immediately prevent a user's sign-in access, follow the steps above and reset their password.</span></span>

1. <span data-ttu-id="be9e8-123">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다..</span><span class="sxs-lookup"><span data-stu-id="be9e8-123">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="be9e8-124">차단할 직원의 이름을 선택하고 사용자 이름에서 이 사용자 차단의 **기호를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="be9e8-124">Select the name of the employee that you want to block, and under the user's name, select the symbol for **Block this user**.</span></span>
3. <span data-ttu-id="be9e8-125">사용자가 로그인할 수 **없습니다.를** 선택한 다음 저장 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="be9e8-125">Select **Block the user from signing in**, and then select **Save**.</span></span>

## <a name="block-a-former-employees-access-to-email-exchange-online"></a><span data-ttu-id="be9e8-126">전자 메일(Exchange Online)에 대한 이전 직원의 액세스 차단</span><span class="sxs-lookup"><span data-stu-id="be9e8-126">Block a former employee's access to email (Exchange Online)</span></span>

<span data-ttu-id="be9e8-127">Microsoft 365 구독의 일부로 전자 메일이 있는 경우 Exchange 관리 센터에 로그인하고 다음 단계에 따라 이전 직원이 전자 메일에 액세스하지 못하게 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="be9e8-127">If you have email as part of your Microsoft 365 subscription, sign in to the Exchange admin center and follow these steps to block your former employee from accessing their email.</span></span>
  
1. <span data-ttu-id="be9e8-128"><a href="https://admin.exchange.microsoft.com/" target="_blank">Exchange 관리 센터</a>로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="be9e8-128">Go to the <a href="https://admin.exchange.microsoft.com/" target="_blank">Exchange admin center</a>.</span></span>
2. <span data-ttu-id="be9e8-129">Exchange 관리 센터에서 **받는 사람** \> **사서함** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="be9e8-129">In the Exchange admin center, navigate to **Recipients** \> **Mailboxes**.</span></span>
3. <span data-ttu-id="be9e8-130">사용자를 두 번 클릭하고 전자 메일 앱 아래의 전자 메일 **앱 설정** **관리로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="be9e8-130">Double-click the user and go to **Manage email apps settings** under **Email apps**.</span></span> <span data-ttu-id="be9e8-131">모든 **옵션에** 대해 슬라이더를 해제합니다. **모바일(Exchange ActiveSync)** **,** 웹용 Outlook , Outlook **데스크톱(MAPI)**, Exchange 웹 **서비스,** **POP3** 및 **IMAP**.</span><span class="sxs-lookup"><span data-stu-id="be9e8-131">Turn **Off** the slider for all the options; **Mobile (Exchange ActiveSync)**, **Outlook on the web**, **Outlook desktop (MAPI)**, **Exchange web services**, **POP3**, and **IMAP**.</span></span>
4. <span data-ttu-id="be9e8-132">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="be9e8-132">Select **Save**.</span></span>
