---
title: 7단계 - 이전 직원의 사용자 계정 삭제
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
description: 다음 단계에 따라 이전 직원의 사용자 계정을 삭제합니다.
ms.openlocfilehash: 735821c9c4d6edf3d23fa3535ed9fa6b3d294b8c
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782384"
---
# <a name="step-7---delete-a-former-employees-user-account"></a><span data-ttu-id="83d78-103">7단계 - 이전 직원의 사용자 계정 삭제</span><span class="sxs-lookup"><span data-stu-id="83d78-103">Step 7 - Delete a former employee's user account</span></span>

<span data-ttu-id="83d78-104">이전 직원의 모든 사용자 데이터에 액세스하여 저장한 후에는 이전 직원의 계정을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83d78-104">After you've saved and accessed all the former employee's user data, you can delete the former employee's account.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="83d78-p101">전자 메일 전달을 설정했거나 공유 사서함으로 변환한 경우 계정을 삭제하지 마세요. 전달 또는 공유 사서함의 기준 위치가 되는 계정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="83d78-p101">Don't delete the account if you've set up email forwarding or converted it to a shared mailbox. Both need the account to anchor the forwarding or shared mailbox.</span></span>

1. <span data-ttu-id="83d78-107">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="83d78-107">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="83d78-108">삭제할 직원의 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="83d78-108">Select the name of the employee that you want to delete.</span></span>
3. <span data-ttu-id="83d78-109">사용자 이름에서 사용자 **삭제 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="83d78-109">Under the user's name, select **Delete user**.</span></span> <span data-ttu-id="83d78-110">이 사용자에 대해 원하는 옵션을 선택한 다음 사용자 삭제 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="83d78-110">Choose the options you want for this user, and then select **Delete user**.</span></span> <span data-ttu-id="83d78-111">이 사용자의 전자 메일 및 OneDrive 다른 사용자에게 이미 액세스 권한을 부여한 경우 여기에서 다시 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="83d78-111">If you've already given another user access to this user's email and OneDrive, you don't have to do it again here.</span></span>

<span data-ttu-id="83d78-p103">사용자를 삭제하면 해당 계정은 약 30일간 비활성 상태가 됩니다. 이 기간에 계정을 복원하지 않으면 영구적으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="83d78-p103">When you delete a user, the account becomes inactive for approximately 30 days. You have until then to restore the account before it is permanently deleted.</span></span>

## <a name="watch-delete-a-former-employees-user-account"></a><span data-ttu-id="83d78-114">감시: 이전 직원의 사용자 계정 삭제</span><span class="sxs-lookup"><span data-stu-id="83d78-114">Watch: Delete a former employee's user account</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR]

<span data-ttu-id="83d78-115">이 비디오가 도움이 된 경우에는 [소규모 비즈니스와 Microsoft 365를 처음 사용하는 사용자를 위한 완전한 교육 시리즈](../../business-video/index.yml)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="83d78-115">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](../../business-video/index.yml).</span></span>

## <a name="does-your-organization-use-active-directory"></a><span data-ttu-id="83d78-116">조직에서 Active Directory를 사용하나요?</span><span class="sxs-lookup"><span data-stu-id="83d78-116">Does your organization use Active Directory?</span></span>

<span data-ttu-id="83d78-117">조직에서 사용자 계정을 로컬 Active Directory Microsoft 365 사용자 계정을 동기화하는 경우 로컬 Active Directory 서비스에서 해당 사용자 계정을 삭제하고 복원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83d78-117">If your organization synchronizes user accounts to Microsoft 365 from a local Active Directory environment, you must delete and restore those user accounts in your local Active Directory service.</span></span> <span data-ttu-id="83d78-118">Office 365에서는 해당 사용자 계정을 삭제하거나 복원할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="83d78-118">You can't delete or restore them in Office 365.</span></span>

<span data-ttu-id="83d78-119">Active Directory에서 사용자 계정을 삭제 및 복원하는 방법에 대한 자세한 내용은 사용자 계정 [삭제를 참조하세요.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="83d78-119">To learn how to delete and restore user account in Active Directory, see [Delete a User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)).</span></span>
  
<span data-ttu-id="83d78-120">사용 중이면 Azure Active Directory [Remove-MsolUser](/powershell/module/msonline/remove-msoluser) PowerShell cmdlet을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="83d78-120">If you're using Azure Active Directory, see the [Remove-MsolUser](/powershell/module/msonline/remove-msoluser) PowerShell cmdlet.</span></span>
  
## <a name="what-you-need-to-know-about-terminating-an-employees-email-session"></a><span data-ttu-id="83d78-121">직원의 전자 메일 세션 종료에 대해 알아야 할 사항</span><span class="sxs-lookup"><span data-stu-id="83d78-121">What you need to know about terminating an employee's email session</span></span>

<span data-ttu-id="83d78-122">다음은 전자 메일(Exchange)에서 직원을 제거하는 방법에 대한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="83d78-122">Here's information about how to get an employee out of email (Exchange).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="83d78-123">**실행할 수 있는 작업**</span><span class="sxs-lookup"><span data-stu-id="83d78-123">**What you can do**</span></span> <br/> |<span data-ttu-id="83d78-124">**방법**</span><span class="sxs-lookup"><span data-stu-id="83d78-124">**How you do it**</span></span> <br/> |
|<span data-ttu-id="83d78-125">세션(예: 웹용 Outlook, Outlook, Exchange Active Sync 등) 종료 및 새 세션 열기</span><span class="sxs-lookup"><span data-stu-id="83d78-125">Terminate a session (such as Outlook on the web, Outlook, Exchange active sync, etc.) and force to open a new session</span></span>  <br/> |<span data-ttu-id="83d78-126">암호 재설정</span><span class="sxs-lookup"><span data-stu-id="83d78-126">Reset password</span></span>  <br/> |
|<span data-ttu-id="83d78-127">세션 종료 및 향후 세션에 대한 액세스 차단(모든 프로토콜에 대해)</span><span class="sxs-lookup"><span data-stu-id="83d78-127">Terminate a session and block access to future sessions (for all protocols)</span></span>  <br/> |<span data-ttu-id="83d78-128">계정을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="83d78-128">Disable the account.</span></span> <span data-ttu-id="83d78-129">예를 들어(Exchange 관리 센터에서 또는 PowerShell 사용):</span><span class="sxs-lookup"><span data-stu-id="83d78-129">For example, (in the Exchange admin center or using PowerShell):</span></span>  <br/>  `Set-Mailbox user@contoso.com -AccountDisabled:$true` <br/> |
|<span data-ttu-id="83d78-130">특정 프로토콜(예: ActiveSync)에 대한 세션 종료</span><span class="sxs-lookup"><span data-stu-id="83d78-130">Terminate the session for a particular protocol (such as ActiveSync)</span></span>  <br/> |<span data-ttu-id="83d78-131">프로토콜을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="83d78-131">Disable the protocol.</span></span> <span data-ttu-id="83d78-132">예를 들어(Exchange 관리 센터에서 또는 PowerShell 사용):</span><span class="sxs-lookup"><span data-stu-id="83d78-132">For example, (in the Exchange admin center or using PowerShell):</span></span>  <br/>  `Set-CASMailbox user@contoso.com -ActiveSyncEnabled:$false` <br/> |

<span data-ttu-id="83d78-133">위의 작업은 다음 세 곳에서 수행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83d78-133">The above operations can be done in three places:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="83d78-134">**여기에서 세션을 종료하는 경우**</span><span class="sxs-lookup"><span data-stu-id="83d78-134">**If you terminate the session here**</span></span> <br/> |<span data-ttu-id="83d78-135">**소요 시간**</span><span class="sxs-lookup"><span data-stu-id="83d78-135">**How long it takes**</span></span> <br/> |
|<span data-ttu-id="83d78-136">Exchange 관리 센터에서 또는 PowerShell을 사용하는 경우</span><span class="sxs-lookup"><span data-stu-id="83d78-136">In the Exchange admin center or using PowerShell</span></span>  <br/> |<span data-ttu-id="83d78-137">30분 이내의 지연이 예상됨</span><span class="sxs-lookup"><span data-stu-id="83d78-137">Expected delay is within 30 min</span></span>  <br/> |
|<span data-ttu-id="83d78-138">Azure Active Directory 관리 센터에서</span><span class="sxs-lookup"><span data-stu-id="83d78-138">In the Azure Active Directory admin center</span></span>  <br/> |<span data-ttu-id="83d78-139">60분의 지연이 예상됨</span><span class="sxs-lookup"><span data-stu-id="83d78-139">Expected delay is 60 min</span></span>  <br/> |
|<span data-ttu-id="83d78-140">온-프레미스 환경에서</span><span class="sxs-lookup"><span data-stu-id="83d78-140">In an on-premises environment</span></span>  <br/> |<span data-ttu-id="83d78-141">3시간 이상의 지연이 예상됨</span><span class="sxs-lookup"><span data-stu-id="83d78-141">Expected delay is 3 hours or more</span></span>  <br/> |

### <a name="how-to-get-fastest-response-for-account-termination"></a><span data-ttu-id="83d78-142">계정 종료에 대해 가장 빠른 응답을 받는 방법</span><span class="sxs-lookup"><span data-stu-id="83d78-142">How to get fastest response for account termination</span></span>

 <span data-ttu-id="83d78-p107">**가장 빠름**: Exchange 관리 센터(PowerShell 사용) 또는 Azure Active Directory 관리 센터를 사용합니다. 온-프레미스 환경에서 DirSync를 통해 변경 내용을 동기화하는 데 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83d78-p107">**Fastest**: Use the Exchange admin center (use PowerShell) or Azure Active Directory admin center. In an on-premises environment, it can take several hours to sync the change through DirSync.</span></span>
  
 <span data-ttu-id="83d78-p108">**온 - 프레미스 및 Exchange Datacenter에 있는 사용자에게 가장 빠름**: Azure Active Directory 관리 센터/Exchange 관리 센터를 사용하여 세션을 종료하고 온 - 프레미스 환경에서도 변경합니다. 그렇지 않으면 Azure Active Directory 관리 센터/Exchange 관리 센터의 변경 사항이 DirSync에 의해 덮어 쓰여집니다.</span><span class="sxs-lookup"><span data-stu-id="83d78-p108">**Fastest for a user with presence on-premises and in the Exchange Datacenter**: Terminate the session using Azure Active Directory admin center/Exchange admin center AND make the change in the on-premises environment as well. Otherwise, the change in Azure Active Directory admin center/Exchange admin center will be overwritten by DirSync.</span></span>
  
## <a name="related-content"></a><span data-ttu-id="83d78-147">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="83d78-147">Related content</span></span>

<span data-ttu-id="83d78-148">[사용자](restore-user.md) 복원(문서) / [암호 다시 설정(문서)](reset-passwords.md)</span><span class="sxs-lookup"><span data-stu-id="83d78-148">[Restore a user](restore-user.md) (article)/ [Reset passwords](reset-passwords.md) (article)</span></span>
