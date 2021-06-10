---
title: 사용자의 다른 전자 메일 별칭 추가
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
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: '비즈니스용 계정과 연결된 전자 메일 별칭이라는 전자 메일 주소를 두 개 이상 사용할 Microsoft 365 방법을 알아보습니다. '
ms.openlocfilehash: ec5bc69a42c5183413f11649b7d7ec6baaf40b01
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572108"
---
# <a name="add-another-email-alias-for-a-user"></a><span data-ttu-id="085c6-103">사용자의 다른 전자 메일 별칭 추가</span><span class="sxs-lookup"><span data-stu-id="085c6-103">Add another email alias for a user</span></span>
  
<span data-ttu-id="085c6-104">이 문서는 비즈니스 Microsoft 365 관리자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="085c6-104">This article is for Microsoft 365 administrators who have business subscriptions.</span></span> <span data-ttu-id="085c6-105">가정용 사용자용이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="085c6-105">It's not for home users.</span></span>
  
<span data-ttu-id="085c6-106">기본 전자 메일 Microsoft 365 계정이 만들어지기 전 사용자가 할당한 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="085c6-106">A primary email address in Microsoft 365 is usually the email address a user was assigned when their account was created.</span></span> <span data-ttu-id="085c6-107">사용자가 다른 사람에게 전자 메일을 보내면 전자 메일 앱의  *보낸 사람*  필드에 일반적으로 사용자의 기본 전자 메일 주소가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="085c6-107">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span></span> <span data-ttu-id="085c6-108">또한 비즈니스용 계정용 전자 메일 주소와 연결된 전자 메일 Microsoft 365 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="085c6-108">They can also have more than one email address associated with their Microsoft 365 for business account.</span></span> <span data-ttu-id="085c6-109">이러한 추가 주소를 별칭이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="085c6-109">These additional addresses are called aliases.</span></span> 
  
<span data-ttu-id="085c6-110">예를 들어 Jenna의 전자 메일 주소는 jenna@contosoco.com 있지만 일부 사람들이 해당 이름으로 jen@contosoco.com 전자 메일을 받기를 원합니다.</span><span class="sxs-lookup"><span data-stu-id="085c6-110">For example, let's say Jenna has the email address jenna@contosoco.com, but she also wants to receive email at jen@contosoco.com because some people refer to her by that name.</span></span> <span data-ttu-id="085c6-111">두 전자 메일 주소가 모두 Jenna의 받은 편지함으로 이동될 수 있도록 별칭을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="085c6-111">You can create aliases for her so that both email addresses go to Jenna's inbox.</span></span>
  
<span data-ttu-id="085c6-p104">사용자는 최대 400의 별칭을 만들 수 있습니다. 추가 요금이나 라이선스는 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="085c6-p104">You can create up to 400 aliases for a user. No additional fees or licenses are required.</span></span>
  
> [!Tip]
> <span data-ttu-id="085c6-114">여러 사용자가 단일 전자 메일 주소(info@NodPublishers.com 또는 전자 메일 주소로 전송된 전자 메일을 sales@NodPublishers.com 사서함을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="085c6-114">If you want multiple people to manage email sent to a single email address like info@NodPublishers.com or sales@NodPublishers.com, create a shared mailbox.</span></span> <span data-ttu-id="085c6-115">자세한 내용은 공유 사서함 [만들기를 참조합니다.](create-a-shared-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="085c6-115">To learn more, see [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>
  
## <a name="add-email-aliases-to-a-user"></a><span data-ttu-id="085c6-116">사용자에게 전자 메일 별칭 추가</span><span class="sxs-lookup"><span data-stu-id="085c6-116">Add email aliases to a user</span></span>

<span data-ttu-id="085c6-117">이렇게하려면 관리자 [권한이](../add-users/about-admin-roles.md) 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="085c6-117">You must have [admin permissions](../add-users/about-admin-roles.md) to do this.</span></span> 

1. <span data-ttu-id="085c6-118">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="085c6-118">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="085c6-119">활성 **사용자 페이지에서** 사용자 이름 및 전자 메일 > **사용자를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="085c6-119">On the **Active Users** page, select the user > **Manage username and email**.</span></span> <span data-ttu-id="085c6-120">사용자에게 할당된 라이선스가 없는 경우 이 옵션이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="085c6-120">You won't see this option if the person doesn't have a license assigned to them.</span></span> 
    
3. <span data-ttu-id="085c6-121">**+ 별칭 추가를 선택하고** 사용자의 새 별칭을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="085c6-121">Select **+ Add an alias** and enter a new alias for the user.</span></span>   
    
    > [!Important] 
    > <span data-ttu-id="085c6-122">"매개 변수 이름 **'EmailAddresses와** 일치하는 매개 변수를 찾을 수 없습니다.'라는 오류 메시지가 표시될 경우 테넌트 또는 최근에 사용자 지정 도메인을 추가한 경우 사용자 지정 도메인 설정을 완료하는 데 시간이 더 오래 드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="085c6-122">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="085c6-123">설정 프로세스를 완료하는 데 최대 4시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="085c6-123">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="085c6-124">설정 프로세스가 완료될 때까지 기다린 후 다시 시도하세요.</span><span class="sxs-lookup"><span data-stu-id="085c6-124">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="085c6-125">문제가 계속되는 경우 고객 지원에 문의하면 전체 동기화를 수행해 드립니다.</span><span class="sxs-lookup"><span data-stu-id="085c6-125">If the problem persists, call Support and they will do a full sync for you.</span></span>
    
  
    > [!IMPORTANT]
    > <span data-ttu-id="085c6-126">GoDaddy 또는 다른 파트너로부터 구독을 구입한 경우 새 별칭을 기본으로 설정하려면 GoDaddy/파트너 관리 콘솔로 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="085c6-126">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="085c6-127">전자 메일 별칭은 드롭다운 목록의 도메인으로 끝나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="085c6-127">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="085c6-128">목록에 다른 도메인 이름을 추가하려면 [Add a domain to Microsoft 365.](../setup/add-domain.md)</span><span class="sxs-lookup"><span data-stu-id="085c6-128">To add another domain name to the list, see [Add a domain to Microsoft 365](../setup/add-domain.md).</span></span> 
  
     
5. <span data-ttu-id="085c6-129">완료되면 변경 내용 **저장 을 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="085c6-129">When you're done, choose **Save changes**.</span></span>
    
6. <span data-ttu-id="085c6-130">새 별칭이 전체적으로 채워지기까지 24시간 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="085c6-130">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span>
    
    <span data-ttu-id="085c6-131">이제 사용자에게 기본 주소와 별칭이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="085c6-131">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="085c6-132">예를 들어 Eliza Hoffman의 기본 주소인 Eliza@NodPublishers.com 및 별칭인 Sales@NodPublishers.com 메일은 모두 지민의 받은 편지함으로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="085c6-132">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="085c6-133">**사용자가 답장할 때 *From* 주소는 사용자의 클라이언트에 Outlook 않습니다. Outlook 웹에서 전자 메일이 수신된 별칭을 사용하게 됩니다(이를 ping-pong 원칙으로 지칭). Outlook 데스크톱에서 기본 전자 메일 별칭을 사용할 것입니다.**</span><span class="sxs-lookup"><span data-stu-id="085c6-133">**When the user replies, the *From* address will depend on her Outlook client. Outlook on the web will use the alias at which the email was received (we'll call this the ping-pong principle). Outlook desktop will use her primary email alias.**</span></span> <span data-ttu-id="085c6-134">예를 들어 메시지가 전자 메일로 전송된 Sales@NodPublishers.com 지민의 받은 편지함으로 도착하는 경우를 예로 들어 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="085c6-134">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="085c6-135">Eliza가 Outlook 데스크톱을 사용하여 메시지에 응답하면 기본 전자 메일 주소가 Eliza@NodPublishers.com 아닌 Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="085c6-135">When Eliza replies to the message using Outlook desktop, her primary email address will appear as Eliza@NodPublishers.com, not Sales@NodPublishers.com.</span></span>
    
## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a><span data-ttu-id="085c6-136">"매개 변수 이름 EmailAddresses와 일치하는 매개 변수를 찾을 수 없습니다."가 있나요?</span><span class="sxs-lookup"><span data-stu-id="085c6-136">Did you get "A parameter cannot be found that matches parameter name EmailAddresses"?</span></span>

<span data-ttu-id="085c6-137">"매개 변수 이름 **EmailAddresses와** 일치하는 매개 변수를 찾을 수 없습니다." 오류 메시지가 표시될 경우 테넌트 또는 최근에 사용자 지정 도메인을 추가한 경우 사용자 지정 도메인 설정이 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="085c6-137">If you get the error message "**A parameter cannot be found that matches parameter name EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="085c6-138">설정 프로세스를 완료하는 데 최대 4시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="085c6-138">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="085c6-139">설정 프로세스가 완료될 때까지 기다린 후 다시 시도하세요.</span><span class="sxs-lookup"><span data-stu-id="085c6-139">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="085c6-140">문제가 계속되는 경우 고객 지원에 문의하면 전체 동기화를 수행해 드립니다.</span><span class="sxs-lookup"><span data-stu-id="085c6-140">If the problem persists, call Support and they will do a full sync for you.</span></span>
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a><span data-ttu-id="085c6-141">GoDaddy 또는 다른 파트너로부터 구독을 구입했나요?</span><span class="sxs-lookup"><span data-stu-id="085c6-141">Did you purchase your subscription from GoDaddy or another Partner?</span></span>


<span data-ttu-id="085c6-142">GoDaddy 또는 다른 파트너로부터 구독을 구입한 경우 새 별칭을 기본으로 설정하려면 GoDaddy/파트너 관리 콘솔로 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="085c6-142">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span>

## <a name="sending-email-from-the-proxy-address-easily"></a><span data-ttu-id="085c6-143">프록시 주소에서 전자 메일 쉽게 보내기</span><span class="sxs-lookup"><span data-stu-id="085c6-143">Sending email from the proxy address easily</span></span>

<span data-ttu-id="085c6-144">새로운 기능은 2021년 4월에 출시되는 기능으로, 사용자가 웹에서 해당 기능을 사용할 때 별칭에서 Outlook 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="085c6-144">A new feature is rolling out in April 2021 that allows users to send from their aliases easily when using Outlook on the web.</span></span> <span data-ttu-id="085c6-145">이 기능이 테넌트 관리자가 cmdlet을 사용하는 테넌시로 롤아웃하면 테넌시 내의 사용자는 각 항목이 해당 Outlook 설정의 별칭에 해당하는 `Set-OrganizationConfig -SendFromAliasEnabled $true` 확인란 목록에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="085c6-145">When the feature rolls out to a tenancy where the tenant admin uses the `Set-OrganizationConfig -SendFromAliasEnabled $true` cmdlet, users within the tenancy will get access to a list of checkboxes where each entry corresponds to an alias in their Outlook settings.</span></span> <span data-ttu-id="085c6-146">별칭을 선택하면 작성 양식의 From 드롭다운에 별칭이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="085c6-146">Selecting an alias will make it appear in the From dropdown in the Compose form.</span></span>
  
## <a name="related-content"></a><span data-ttu-id="085c6-147">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="085c6-147">Related content</span></span>

<span data-ttu-id="085c6-148">[다른 주소에서 전자 메일 보내기(문서)](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e)</span><span class="sxs-lookup"><span data-stu-id="085c6-148">[Send email from a different address](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) (article)</span></span>

<span data-ttu-id="085c6-149">[사용자 이름 및 전자 메일 주소](../add-users/change-a-user-name-and-email-address.md) 변경(문서)</span><span class="sxs-lookup"><span data-stu-id="085c6-149">[Change a user name and email address](../add-users/change-a-user-name-and-email-address.md) (article)</span></span>

<span data-ttu-id="085c6-150">[Microsoft 365에서 전자 메일 전달 구성](configure-email-forwarding.md)(문서)</span><span class="sxs-lookup"><span data-stu-id="085c6-150">[Configure email forwarding in Microsoft 365](configure-email-forwarding.md) (article)</span></span>
