---
title: 사용자를 개별적으로 또는 대량으로 Office 365에 추가
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_O365_Setup
- Adm_O365_TOC
ms.custom:
- MSStore_Link
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1970f7d6-03b5-442f-b385-5880b9c256ec
description: CSV 파일에서 동시에 한 번에 하나씩 Office 365에 사용자를 추가 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 708bce2cb5a2c1b6a621bffc3ce56a2744bb518d
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42245784"
---
# <a name="add-users-individually-or-in-bulk-to-office-365"></a><span data-ttu-id="f9ca4-103">사용자를 개별적으로 또는 대량으로 Office 365에 추가</span><span class="sxs-lookup"><span data-stu-id="f9ca4-103">Add users individually or in bulk to Office 365</span></span>

<span data-ttu-id="f9ca4-104">팀의 각 구성원은 먼저 사용자 계정이 있어야 [Office 365 비즈니스 에디션](https://go.microsoft.com/fwlink/?LinkID=519395)에 로그인하고 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-104">The people on your team each need a user account before they can sign in and access [Office 365 for business](https://go.microsoft.com/fwlink/?LinkID=519395).</span></span> <span data-ttu-id="f9ca4-105">사용자 계정을 추가 하는 가장 쉬운 방법은 Microsoft 365 관리 센터에서 한 번에 하나씩 추가 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-105">The easiest way to add user accounts is to add them one at a time in the Microsoft 365 admin center.</span></span> <span data-ttu-id="f9ca4-106">이 단계를 수행 하 고 나면 사용자에 게 Office 365 라이선스, 로그인 자격 증명 및 Office 365 사서함이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-106">After you do this step, your users will have Office 365 licenses, sign in credentials, and Office 365 mailboxes.</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="f9ca4-107">새로운 Microsoft 365 관리 센터를 사용하지 않는 경우 홈페이지 상단에 있는 **새 관리 센터 시도** 토글을 선택하여 켤 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-107">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="f9ca4-108"><a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 의 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-108">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="f9ca4-109">**사용자** > **활성 사용자**로 이동 하 여 **사용자 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-109">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
   
3. <span data-ttu-id="f9ca4-110">**기본 설정** 창에서 다음 정보를 입력 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-110">In the **Set up the basics** pane, fill in the following information, and then select **Next**.</span></span> 
  
- <span data-ttu-id="f9ca4-111">**이름** 첫 번째, 성, 표시 이름 및 사용자 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-111">**Name** Fill in first, last, display name, and username.</span></span> 
    
- <span data-ttu-id="f9ca4-112">**도메인** 예를 들어 사용자의 사용자 이름이 Jakob이고 도메인이 contoso.com인 경우 jakob@contoso.com을 입력하여 Office 365에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-112">**Domain** For example, if the user's username is Jakob, and his domain is contoso.com, he'll sign in to Office 365 by typing jakob@contoso.com.</span></span> 
    
- <span data-ttu-id="f9ca4-113">**암호 설정** 자동 생성 된 암호 사용을 선택 하거나 사용자에 대 한 강력한 암호를 직접 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-113">**Password settings** Choose to the use auto-generated password or create your own strong password for the user.</span></span> 
    
    - <span data-ttu-id="f9ca4-114">사용자는 90일이 지나면 암호를 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-114">They'll need to change their password after 90 days.</span></span> <span data-ttu-id="f9ca4-115">또는 **이 사용자가 처음 로그인 할 때 암호를 변경**하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-115">Or you can choose to **Require this user to change their password when they first sign in**.</span></span>
    
    - <span data-ttu-id="f9ca4-116">사용자가 추가 되 면 전자 메일로 암호를 보낼지 여부를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-116">Choose whether you want to  send the password in email when the user has been added.</span></span> 
    
4. <span data-ttu-id="f9ca4-117">**제품 라이선스 할당** 창에서 사용자에 대 한 적절 한 위치 및 라이선스를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-117">In the **Assign product licenses** pane, select the location and the appropriate license for the user.</span></span> <span data-ttu-id="f9ca4-118">사용 가능한 라이선스가 없어도 사용자를 추가하고 추가 라이선스를 구입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-118">If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span> <span data-ttu-id="f9ca4-119"> Select **Next**. </span><span class="sxs-lookup"><span data-stu-id="f9ca4-119">Select **Next**.</span></span>

5. <span data-ttu-id="f9ca4-120">**선택적 설정** 페이지에서이 사용자를 관리자로 설정 하려면 **역할** 을 확장 하 고 사용자에 대 한 추가 정보를 추가 하려면 **프로필 정보** 를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-120">In the **Optional settings** page, expand **Roles** if you want to make this user an admin, and expand **Profile info** if you want to add additional information about the user.</span></span> 

6. <span data-ttu-id="f9ca4-121">**다음**을 선택 하 고 새 사용자의 설정을 검토 하 고 원하는 대로 변경한 다음 **추가 완료**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-121">Select **Next**, review your new user's settings, make any changes you like, and then select **Finish adding**.</span></span> 

::: moniker-end


::: moniker range="o365-germany"

1. <span data-ttu-id="f9ca4-122"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> 의 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-122">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

2. <span data-ttu-id="f9ca4-123">**사용자** > **활성 사용자**로 이동 하 여 **사용자 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-123">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
   
  
   <span data-ttu-id="f9ca4-124">**새 사용자** 창에서 다음 정보를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-124">In the **New user** pane, fill in the following information.</span></span> <span data-ttu-id="f9ca4-125">완료 되 면 **추가** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-125">Select **Add** when you are done.</span></span> 
  
- <span data-ttu-id="f9ca4-126">**이름** 이름, 성, 표시 이름 및 사용자 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-126">**Name** Fill in first, last, display name, and user name.</span></span> 
    
- <span data-ttu-id="f9ca4-127">**도메인** 예를 들어 사용자의 사용자 이름이 Jakob이고 도메인이 contoso.com인 경우 jakob@contoso.com을 입력하여 Office 365에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-127">**Domain** For example, if the user's username is Jakob, and his domain is contoso.com, he'll sign in to Office 365 by typing jakob@contoso.com.</span></span> 
    
- <span data-ttu-id="f9ca4-128">**연락처 정보** 확장하여 휴대폰 번호, 주소 등을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-128">**Contact information** Expand to fill in a mobile phone number, address, and so on.</span></span> 
    
- <span data-ttu-id="f9ca4-129">**암호** 자동 생성된 암호를 사용하거나 확장하여 강력한 암호를 지정해 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-129">**Password** Use the auto-generated password or expand to specify a strong password for the user.</span></span> 
    
    <span data-ttu-id="f9ca4-p105">사용자는 90일이 지나면 암호를 변경해야 합니다. 또는 **사용자가 처음 로그인할 때 암호를 변경하도록 설정**할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-p105">They'll need to change their password after 90 days. Or you can choose to **Make this user change their password when they first sign in**.</span></span>
    
- <span data-ttu-id="f9ca4-132">**역할** 사용자를 관리자로 설정해야 하는 경우 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-132">**Roles** Expand if you need to make this user an admin.</span></span> 
    
- <span data-ttu-id="f9ca4-p106">**제품 라이선스** 이 섹션을 확장하여 적절한 라이선스를 선택합니다. 사용 가능한 라이선스가 없어도 사용자를 추가하고 추가 라이선스를 구입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-p106">**Product licenses** Expand this section and select the appropriate license. If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="f9ca4-135"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a> 의 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-135">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

2. <span data-ttu-id="f9ca4-136">**사용자** > **활성 사용자**로 이동 하 여 **사용자 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-136">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
   
  
   <span data-ttu-id="f9ca4-137">**새 사용자** 창에서 다음 정보를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-137">In the **New user** pane, fill in the following information.</span></span> <span data-ttu-id="f9ca4-138">완료 되 면 **추가** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-138">Select **Add** when you are done.</span></span> 
  
- <span data-ttu-id="f9ca4-139">**이름** 이름, 성, 표시 이름 및 사용자 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-139">**Name** Fill in first, last, display name, and user name.</span></span> 
    
- <span data-ttu-id="f9ca4-140">**도메인** 예를 들어 사용자의 사용자 이름이 Jakob이고 도메인이 contoso.com인 경우 jakob@contoso.com을 입력하여 Office 365에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-140">**Domain** For example, if the user's username is Jakob, and his domain is contoso.com, he'll sign in to Office 365 by typing jakob@contoso.com.</span></span> 
    
- <span data-ttu-id="f9ca4-141">**연락처 정보** 확장하여 휴대폰 번호, 주소 등을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-141">**Contact information** Expand to fill in a mobile phone number, address, and so on.</span></span> 
    
- <span data-ttu-id="f9ca4-142">**암호** 자동 생성된 암호를 사용하거나 확장하여 강력한 암호를 지정해 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-142">**Password** Use the auto-generated password or expand to specify a strong password for the user.</span></span> 
    
    <span data-ttu-id="f9ca4-p108">사용자는 90일이 지나면 암호를 변경해야 합니다. 또는 **사용자가 처음 로그인할 때 암호를 변경하도록 설정**할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-p108">They'll need to change their password after 90 days. Or you can choose to **Make this user change their password when they first sign in**.</span></span>
    
- <span data-ttu-id="f9ca4-145">**역할** 사용자를 관리자로 설정해야 하는 경우 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-145">**Roles** Expand if you need to make this user an admin.</span></span> 
    
- <span data-ttu-id="f9ca4-p109">**제품 라이선스** 이 섹션을 확장하여 적절한 라이선스를 선택합니다. 사용 가능한 라이선스가 없어도 사용자를 추가하고 추가 라이선스를 구입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-p109">**Product licenses** Expand this section and select the appropriate license. If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span> 

::: moniker-end 
  
<span data-ttu-id="f9ca4-148">사용자 추가를 마친 다음에는 Microsoft Online Services 팀으로부터 전자 메일 알림을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-148">After you add a user, you'll get an email notification from the Microsoft Online Services Team.</span></span> <span data-ttu-id="f9ca4-149">전자 메일에는 사용자가 Office 365에 로그인할 수 있도록 해당 사용자의 Office 365 사용자 ID와 암호가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-149">The email will contain the person's Office 365 user ID and password so they can sign in to Office 365.</span></span> <span data-ttu-id="f9ca4-150">관리자는 새 사용자에게 Office 365 로그인 정보를 알려 주어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-150">You need to tell your new user about their Office 365 sign in information.</span></span> <span data-ttu-id="f9ca4-151">새 암호를 전달하는 데 일반 프로세스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-151">Use your normal process for communicating new passwords.</span></span>

> [!NOTE]
><span data-ttu-id="f9ca4-152">메일 상자를 마이그레이션하여 사용자를 만드는 경우 라이선스를 할당 하 여 Office 365 사용자 계정을 정품 인증 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-152">If you create users by migrating mail boxes, you will need to activate Office 365 user accounts by assigning licenses.</span></span> <span data-ttu-id="f9ca4-153">사용자에 게 라이선스를 할당 하지 않으면 유예 기간이 30 일 후 해당 사서함이 사용 하지 않도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-153">If you don't assign a license to a user, their mailbox will be disabled after a grace period of 30 days.</span></span> <span data-ttu-id="f9ca4-154">Microsoft 365 관리 센터를 사용 하 여 [사용자에 게 라이선스를 할당](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) 하는 방법을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-154">See how to [assign licenses to users](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) using the Microsoft 365 admin center.</span></span>

### <a name="video-add-and-manage-users-in-the-admin-center"></a><span data-ttu-id="f9ca4-155">비디오: 관리 센터에서 사용자 추가 및 관리</span><span class="sxs-lookup"><span data-stu-id="f9ca4-155">Video: Add and manage users in the admin center</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfN?autoplay=false]
  
## <a name="next-steps"></a><span data-ttu-id="f9ca4-156">다음 단계</span><span class="sxs-lookup"><span data-stu-id="f9ca4-156">Next steps</span></span>

<span data-ttu-id="f9ca4-157">새로운 사용자가 [PC 또는 Mac의 Office](https://support.office.com/article/b9700090-ce64-4046-ab92-ce8488a7bc0f.aspx) 및 [Office 모바일 앱](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658.aspx)과 같은 기능을 설정할 수 있도록 [Employee quick start guide](https://support.office.com/article/7dabb6cb-0046-40b6-81fe-767e0b1f014f.aspx)(직원 빠른 시작 가이드)를 사용자와 공유하세요.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-157">Share the [Employee quick start guide](https://support.office.com/article/b9700090-ce64-4046-ab92-ce8488a7bc0f.aspx) with your new users to set things up, like [Office on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658.aspx) and [Office mobile apps](https://support.office.com/article/7dabb6cb-0046-40b6-81fe-767e0b1f014f.aspx).</span></span>
  
## <a name="need-help"></a><span data-ttu-id="f9ca4-158">도움이 필요 하세요?</span><span class="sxs-lookup"><span data-stu-id="f9ca4-158">Need help?</span></span>

<span data-ttu-id="f9ca4-159">[Office 365 for business Support에 문의 하세요](../contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="f9ca4-159">[Contact Office 365 for business support](../contact-support-for-business-products.md).</span></span>  

## <a name="have-hundreds-or-thousands-of-users-to-add"></a><span data-ttu-id="f9ca4-160">수백 또는 수천 명의 사용자를 추가해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="f9ca4-160">Have hundreds or thousands of users to add?</span></span>


<span data-ttu-id="f9ca4-161">동시에 여러 사용자를 추가하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-161">To add multiple users at the same time, follow these steps:</span></span>
  
- <span data-ttu-id="f9ca4-162">**스프레드시트를 사용 하 여 사용자를 대량으로 추가 합니다.**</span><span class="sxs-lookup"><span data-stu-id="f9ca4-162">**Use a spreadsheet to add people in bulk.**</span></span> <span data-ttu-id="f9ca4-163">동시 [에 여러 사용자 추가](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-163">See [Add several users at the same time](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time).</span></span>
    
- <span data-ttu-id="f9ca4-164">**계정 추가 및 라이선스 할당을 자동화 합니다.**</span><span class="sxs-lookup"><span data-stu-id="f9ca4-164">**Automate adding accounts and assigning licenses.**</span></span> <span data-ttu-id="f9ca4-165">[Office 365 PowerShell을 사용 하 여 사용자 계정 만들기를](https://docs.microsoft.com/office365/enterprise/powershell/create-user-accounts-with-office-365-powershell)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-165">See [Create user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/create-user-accounts-with-office-365-powershell).</span></span> <span data-ttu-id="f9ca4-166">Windows PowerShell cmdlet을 사용 하는 것이 이미 익숙한 경우이 방법을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-166">Choose this method if you're already familiar with using Windows PowerShell cmdlets.</span></span>
    
- <span data-ttu-id="f9ca4-167">**ActiveDirectory 사용**</span><span class="sxs-lookup"><span data-stu-id="f9ca4-167">**Using ActiveDirectory?**</span></span> <span data-ttu-id="f9ca4-168">[Office 365에 대 한 디렉터리 동기화를 설정](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization)합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-168">[Set up directory synchronization for Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization).</span></span> <span data-ttu-id="f9ca4-169">Office 365에서 Azure AD Connect 도구를 사용하여 Active Directory 사용자 계정 및 기타 Active Directory 개체를 복제합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-169">Use the Azure AD Connect tool to replicate Active Directory user accounts (and other Active Directory objects) in Office 365.</span></span> <span data-ttu-id="f9ca4-170">동기화하면 사용자 계정만 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-170">The sync only adds the user accounts.</span></span> <span data-ttu-id="f9ca4-171">동기화된 사용자에게 라이선스를 할당해야 전자 메일 및 기타 Office 앱을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-171">You will need to assign licenses to the synced users before they can use email and other Office apps.</span></span>
    
- <span data-ttu-id="f9ca4-172">**Exchange에서 마이그레이션 여부**</span><span class="sxs-lookup"><span data-stu-id="f9ca4-172">**Migrating from Exchange?**</span></span> <span data-ttu-id="f9ca4-173">[여러 전자 메일 계정을 Office 365로 마이그레이션하는 방법](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)</span><span class="sxs-lookup"><span data-stu-id="f9ca4-173">[Ways to migrate multiple email accounts to Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).</span></span> <span data-ttu-id="f9ca4-174">단독형, 미리 구성된 또는 하이브리드 Exchange 방법을 사용하여 여러 사서함을 Office 365로 마이그레이션하는 경우 마이그레이션의 일환으로 사용자가 자동으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-174">When you migrate multiple mailboxes to Office 365 by using either cutover, staged, or a hybrid Exchange method, you will add users automatically as part of the migration.</span></span> <span data-ttu-id="f9ca4-175">마이그레이션하면 사용자 계정만 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-175">The migration only adds the user accounts.</span></span> <span data-ttu-id="f9ca4-176">사용자에게 라이선스를 할당해야 전자 메일 및 기타 Office 앱을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca4-176">You will need assign licenses to the users before they can use email and other Office apps.</span></span>

## <a name="related-articles"></a><span data-ttu-id="f9ca4-177">관련 문서</span><span class="sxs-lookup"><span data-stu-id="f9ca4-177">Related articles</span></span>

[<span data-ttu-id="f9ca4-178">Office 365에 새 직원 추가</span><span class="sxs-lookup"><span data-stu-id="f9ca4-178">Add a new employee to Office 365</span></span>](add-new-employee.md)

[<span data-ttu-id="f9ca4-179">조직에서 사용자 삭제</span><span class="sxs-lookup"><span data-stu-id="f9ca4-179">Delete a user from your organization</span></span>](delete-a-user.md)

[<span data-ttu-id="f9ca4-180">Office 365에서 사용자 복원</span><span class="sxs-lookup"><span data-stu-id="f9ca4-180">Restore a user in Office 365</span></span>](restore-user.md)

[<span data-ttu-id="f9ca4-181">Office 365에 여러 사용자를 동시에 추가</span><span class="sxs-lookup"><span data-stu-id="f9ca4-181">Add several users at the same time to Office 365</span></span>](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time)


