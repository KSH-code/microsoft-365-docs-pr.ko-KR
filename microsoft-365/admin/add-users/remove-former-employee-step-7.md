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
ms.openlocfilehash: 0afa9b112919d2668d7553ac5bcf08e664bc1749
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244237"
---
# <a name="step-7---delete-a-former-employees-user-account"></a><span data-ttu-id="f91c9-103">7단계 - 이전 직원의 사용자 계정 삭제</span><span class="sxs-lookup"><span data-stu-id="f91c9-103">Step 7 - Delete a former employee's user account</span></span>

<span data-ttu-id="f91c9-104">이전 직원의 모든 사용자 데이터에 액세스하여 저장한 후에는 이전 직원의 계정을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f91c9-104">After you've saved and accessed all the former employee's user data, you can delete the former employee's account.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f91c9-p101">전자 메일 전달을 설정했거나 공유 사서함으로 변환한 경우 계정을 삭제하지 마세요. 전달 또는 공유 사서함의 기준 위치가 되는 계정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f91c9-p101">Don't delete the account if you've set up email forwarding or converted it to a shared mailbox. Both need the account to anchor the forwarding or shared mailbox.</span></span>

1. <span data-ttu-id="f91c9-107">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f91c9-107">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="f91c9-108">삭제할 직원의 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f91c9-108">Select the name of the employee that you want to delete.</span></span>
3. <span data-ttu-id="f91c9-109">사용자 이름에서 사용자 **삭제 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f91c9-109">Under the user's name, select **Delete user**.</span></span> <span data-ttu-id="f91c9-110">이 사용자에 대해 원하는 옵션을 선택한 다음 사용자 삭제 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f91c9-110">Choose the options you want for this user, and then select **Delete user**.</span></span> <span data-ttu-id="f91c9-111">이 사용자의 전자 메일 및 OneDrive 다른 사용자에게 이미 액세스 권한을 부여한 경우 여기에서 다시 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f91c9-111">If you've already given another user access to this user's email and OneDrive, you don't have to do it again here.</span></span>

<span data-ttu-id="f91c9-p103">사용자를 삭제하면 해당 계정은 약 30일간 비활성 상태가 됩니다. 이 기간에 계정을 복원하지 않으면 영구적으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="f91c9-p103">When you delete a user, the account becomes inactive for approximately 30 days. You have until then to restore the account before it is permanently deleted.</span></span>
  
## <a name="does-your-organization-use-active-directory"></a><span data-ttu-id="f91c9-114">조직에서 Active Directory를 사용하나요?</span><span class="sxs-lookup"><span data-stu-id="f91c9-114">Does your organization use Active Directory?</span></span>

<span data-ttu-id="f91c9-115">조직에서 사용자 계정을 로컬 Active Directory Microsoft 365 사용자 계정을 동기화하는 경우 로컬 Active Directory 서비스에서 해당 사용자 계정을 삭제하고 복원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f91c9-115">If your organization synchronizes user accounts to Microsoft 365 from a local Active Directory environment, you must delete and restore those user accounts in your local Active Directory service.</span></span> <span data-ttu-id="f91c9-116">Office 365에서는 해당 사용자 계정을 삭제하거나 복원할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f91c9-116">You can't delete or restore them in Office 365.</span></span>

<span data-ttu-id="f91c9-117">Active Directory에서 사용자 계정을 삭제 및 복원하는 방법에 대한 자세한 내용은 사용자 계정 [삭제를 참조하세요.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="f91c9-117">To learn how to delete and restore user account in Active Directory, see [Delete a User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)).</span></span>
  
<span data-ttu-id="f91c9-118">사용 중이면 Azure Active Directory [Remove-MsolUser](https://go.microsoft.com/fwlink/?linkid=842230) PowerShell cmdlet을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="f91c9-118">If you're using Azure Active Directory, see the [Remove-MsolUser](https://go.microsoft.com/fwlink/?linkid=842230) PowerShell cmdlet.</span></span>
  
## <a name="what-you-need-to-know-about-terminating-an-employees-email-session"></a><span data-ttu-id="f91c9-119">직원의 전자 메일 세션 종료에 대해 알아야 할 사항</span><span class="sxs-lookup"><span data-stu-id="f91c9-119">What you need to know about terminating an employee's email session</span></span>

<span data-ttu-id="f91c9-120">다음은 전자 메일(Exchange)에서 직원을 제거하는 방법에 대한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="f91c9-120">Here's information about how to get an employee out of email (Exchange).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f91c9-121">**실행할 수 있는 작업**</span><span class="sxs-lookup"><span data-stu-id="f91c9-121">**What you can do**</span></span> <br/> |<span data-ttu-id="f91c9-122">**방법**</span><span class="sxs-lookup"><span data-stu-id="f91c9-122">**How you do it**</span></span> <br/> |
|<span data-ttu-id="f91c9-123">세션(예: 웹용 Outlook, Outlook, Exchange Active Sync 등) 종료 및 새 세션 열기</span><span class="sxs-lookup"><span data-stu-id="f91c9-123">Terminate a session (such as Outlook on the web, Outlook, Exchange active sync, etc.) and force to open a new session</span></span>  <br/> |<span data-ttu-id="f91c9-124">암호 재설정</span><span class="sxs-lookup"><span data-stu-id="f91c9-124">Reset password</span></span>  <br/> |
|<span data-ttu-id="f91c9-125">세션 종료 및 향후 세션에 대한 액세스 차단(모든 프로토콜에 대해)</span><span class="sxs-lookup"><span data-stu-id="f91c9-125">Terminate a session and block access to future sessions (for all protocols)</span></span>  <br/> |<span data-ttu-id="f91c9-126">계정을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f91c9-126">Disable the account.</span></span> <span data-ttu-id="f91c9-127">예를 들어(Exchange 관리 센터에서 또는 PowerShell 사용):</span><span class="sxs-lookup"><span data-stu-id="f91c9-127">For example, (in the Exchange admin center or using PowerShell):</span></span>  <br/>  `Set-Mailbox user@contoso.com -AccountDisabled:$true` <br/> |
|<span data-ttu-id="f91c9-128">특정 프로토콜(예: ActiveSync)에 대한 세션 종료</span><span class="sxs-lookup"><span data-stu-id="f91c9-128">Terminate the session for a particular protocol (such as ActiveSync)</span></span>  <br/> |<span data-ttu-id="f91c9-129">프로토콜을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f91c9-129">Disable the protocol.</span></span> <span data-ttu-id="f91c9-130">예를 들어(Exchange 관리 센터에서 또는 PowerShell 사용):</span><span class="sxs-lookup"><span data-stu-id="f91c9-130">For example, (in the Exchange admin center or using PowerShell):</span></span>  <br/>  `Set-CASMailbox user@contoso.com -ActiveSyncEnabled:$false` <br/> |

<span data-ttu-id="f91c9-131">위의 작업은 다음 세 곳에서 수행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f91c9-131">The above operations can be done in three places:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f91c9-132">**여기에서 세션을 종료하는 경우**</span><span class="sxs-lookup"><span data-stu-id="f91c9-132">**If you terminate the session here**</span></span> <br/> |<span data-ttu-id="f91c9-133">**소요 시간**</span><span class="sxs-lookup"><span data-stu-id="f91c9-133">**How long it takes**</span></span> <br/> |
|<span data-ttu-id="f91c9-134">Exchange 관리 센터에서 또는 PowerShell을 사용하는 경우</span><span class="sxs-lookup"><span data-stu-id="f91c9-134">In the Exchange admin center or using PowerShell</span></span>  <br/> |<span data-ttu-id="f91c9-135">30분 이내의 지연이 예상됨</span><span class="sxs-lookup"><span data-stu-id="f91c9-135">Expected delay is within 30 min</span></span>  <br/> |
|<span data-ttu-id="f91c9-136">Azure Active Directory 관리 센터에서</span><span class="sxs-lookup"><span data-stu-id="f91c9-136">In the Azure Active Directory admin center</span></span>  <br/> |<span data-ttu-id="f91c9-137">60분의 지연이 예상됨</span><span class="sxs-lookup"><span data-stu-id="f91c9-137">Expected delay is 60 min</span></span>  <br/> |
|<span data-ttu-id="f91c9-138">온-프레미스 환경에서</span><span class="sxs-lookup"><span data-stu-id="f91c9-138">In an on-premises environment</span></span>  <br/> |<span data-ttu-id="f91c9-139">3시간 이상의 지연이 예상됨</span><span class="sxs-lookup"><span data-stu-id="f91c9-139">Expected delay is 3 hours or more</span></span>  <br/> |

### <a name="how-to-get-fastest-response-for-account-termination"></a><span data-ttu-id="f91c9-140">계정 종료에 대해 가장 빠른 응답을 받는 방법</span><span class="sxs-lookup"><span data-stu-id="f91c9-140">How to get fastest response for account termination</span></span>

 <span data-ttu-id="f91c9-p107">**가장 빠름**: Exchange 관리 센터(PowerShell 사용) 또는 Azure Active Directory 관리 센터를 사용합니다. 온-프레미스 환경에서 DirSync를 통해 변경 내용을 동기화하는 데 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f91c9-p107">**Fastest**: Use the Exchange admin center (use PowerShell) or Azure Active Directory admin center. In an on-premises environment, it can take several hours to sync the change through DirSync.</span></span>
  
 <span data-ttu-id="f91c9-p108">**온 - 프레미스 및 Exchange Datacenter에 있는 사용자에게 가장 빠름**: Azure Active Directory 관리 센터/Exchange 관리 센터를 사용하여 세션을 종료하고 온 - 프레미스 환경에서도 변경합니다. 그렇지 않으면 Azure Active Directory 관리 센터/Exchange 관리 센터의 변경 사항이 DirSync에 의해 덮어 쓰여집니다.</span><span class="sxs-lookup"><span data-stu-id="f91c9-p108">**Fastest for a user with presence on-premises and in the Exchange Datacenter**: Terminate the session using Azure Active Directory admin center/Exchange admin center AND make the change in the on-premises environment as well. Otherwise, the change in Azure Active Directory admin center/Exchange admin center will be overwritten by DirSync.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="f91c9-145">관련 문서</span><span class="sxs-lookup"><span data-stu-id="f91c9-145">Related articles</span></span>

[<span data-ttu-id="f91c9-146">사용자 복원</span><span class="sxs-lookup"><span data-stu-id="f91c9-146">Restore a user</span></span>](restore-user.md)
