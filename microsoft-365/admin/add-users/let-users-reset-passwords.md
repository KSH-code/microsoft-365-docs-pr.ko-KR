---
title: Office 365에서 사용자가 암호를 직접 재설정할 수 있도록 지원
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
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: 셀프 서비스 암호 재설정 도구를 사용 하 여 암호를 다시 설정 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 666d3843f7917cf9bd5718c0ce29f87f93d6effe
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211898"
---
# <a name="let-users-reset-their-own-passwords"></a><span data-ttu-id="fe39a-103">사용자가 암호를 직접 재설정할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="fe39a-103">Let users reset their own passwords</span></span>

<span data-ttu-id="fe39a-104">사용자가 자신의 암호를 재설정해달라고 요청하는 일이 과도하게 많나요?</span><span class="sxs-lookup"><span data-stu-id="fe39a-104">Getting crushed with people asking you to reset their passwords?</span></span> <span data-ttu-id="fe39a-105">Microsoft 365 관리자는 사용자가 [셀프 서비스 암호 다시 설정 도구](https://go.microsoft.com/fwlink/p/?LinkId=522677) 를 사용 하 여 암호를 다시 설정할 필요가 없도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe39a-105">As the Microsoft 365 admin, you can let people use the [self-service password reset tool](https://go.microsoft.com/fwlink/p/?LinkId=522677) so you don't have to reset passwords for them.</span></span> <span data-ttu-id="fe39a-106">관리자의 업무를 덜 수 있습니다!</span><span class="sxs-lookup"><span data-stu-id="fe39a-106">Less work for you!</span></span> 
  
<span data-ttu-id="fe39a-107">알아야 할 몇 가지 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fe39a-107">Here are a few things you need to know:</span></span>
  
- <span data-ttu-id="fe39a-p102">모든 Office 365 비즈니스, 교육 또는 비영리 기관용 요금제에서는 클라우드 사용자에 대한 셀프 서비스 암호 재설정을 **무료** 로 제공합니다. 이 기능은 Office 365 평가판에서는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fe39a-p102">You get self-service password reset for cloud users **free** with any Office 365 business, education, or nonprofit paid plan. It doesn't work with Office 365 trial.</span></span> 
    
- <span data-ttu-id="fe39a-p103">Azure를 사용합니다. 이러한 단계를 수행할 때 자동으로 Azure의 이 기능을 **무료** 로 이용할 수 있습니다. 다른 Azure 기능을 사용하지 않으면 셀프 서비스 암호 재설정을 사용하는 비용이 부과되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fe39a-p103">It uses Azure. You'll automatically get this feature in Azure for **free** when you do these steps. It won't cost you anything to turn on self-service password reset if you don't use other Azure features.</span></span> 
    
- <span data-ttu-id="fe39a-113">**온-프레미스 Active Directory를 사용**하는 경우 위의 두 지점이 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fe39a-113">**If you're using an on-premises Active Directory**, the above two points don't apply.</span></span> <span data-ttu-id="fe39a-114">대신이를 설정할 수는 있지만 **AZURE AD Premium에 대 한 유료 구독을 사용 해야**합니다.</span><span class="sxs-lookup"><span data-stu-id="fe39a-114">Rather, you can set this up but **it requires a paid subscription to Azure AD Premium**.</span></span> 

<span data-ttu-id="fe39a-115">사용자가 자신의 암호를 다시 설정 하도록 허용 하는 방법에 대 한 짧은 비디오를 시청 하세요.</span><span class="sxs-lookup"><span data-stu-id="fe39a-115">Watch a short video about letting users reset their own passwords.</span></span> <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S] 

<span data-ttu-id="fe39a-116">이 비디오가 도움이 된 경우에는 [소규모 비즈니스 및 Microsoft 365를 처음 사용하는 사용자들을 위한 완전한 교육 시리즈](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fe39a-116">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="let-people-reset-their-own-passwords"></a><span data-ttu-id="fe39a-117">사용자가 자신의 암호를 다시 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe39a-117">Let people reset their own passwords</span></span> 

<span data-ttu-id="fe39a-118">다음 단계에서는 비즈니스의 모든 사용자에 대해 셀프 서비스 암호 재설정을 켭니다.</span><span class="sxs-lookup"><span data-stu-id="fe39a-118">These steps turn on self-service password reset for everyone in your business.</span></span>
  
::: moniker range="o365-worldwide"
1.  <span data-ttu-id="fe39a-119">관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">보안 & 개인 정보</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe39a-119">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Security & privacy</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="fe39a-120"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">관리 센터</a>에서 **설정** \> \*\* &amp; 보안 개인 정보\*\* 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe39a-120">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="fe39a-121"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">관리 센터</a>에서 **설정** \> \*\* &amp; 보안 개인 정보\*\* 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe39a-121">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

   
2. <span data-ttu-id="fe39a-122">**사용자가 자신의 암호를 다시 설정 하도록 허용**에서 **Azure AD 관리 센터**에 대 한 링크를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe39a-122">Under **Let your people reset their own passwords**, select the link for the **Azure AD admin center**.</span></span> <span data-ttu-id="fe39a-123">Azure를 무료로 이용할 수 있습니다!</span><span class="sxs-lookup"><span data-stu-id="fe39a-123">You'll get Azure for free!</span></span>
  
3. <span data-ttu-id="fe39a-124">왼쪽 탐색 창에서 **사용자** 를 선택 하 고 **암호 다시 설정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe39a-124">Select **Users** in the left navigation, and then select **Password reset**.</span></span>
  
4. <span data-ttu-id="fe39a-125">속성 페이지에서 **모두** 를 선택 하 여 회사의 모든 사용자에 대해 사용 하도록 설정 하 고 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe39a-125">On the Properties page, select **All** to enable it for everyone in your business, and then select **Save**.</span></span>
  
5. <span data-ttu-id="fe39a-126">사용자가 Office 365에 로그인하면 나중에 암호를 재설정할 때 사용할 수 있는 추가 연락처 정보를 입력하라는 메시지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="fe39a-126">When your users sign in to Office 365, they will be prompted to enter additional contact information that will help them reset their password in the future.</span></span>

## <a name="related-articles"></a><span data-ttu-id="fe39a-127">관련 문서</span><span class="sxs-lookup"><span data-stu-id="fe39a-127">Related articles</span></span>

[<span data-ttu-id="fe39a-128">조직의 암호 만료 정책 설정</span><span class="sxs-lookup"><span data-stu-id="fe39a-128">Set the password expiration policy for your organization</span></span>](../manage/set-password-expiration-policy.md)
  
[<span data-ttu-id="fe39a-129">개별 사용자 암호가 만료되지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="fe39a-129">Set an individual user's password to never expire</span></span>](set-password-to-never-expire.md)

[<span data-ttu-id="fe39a-130">Microsoft 365 Business 교육 비디오</span><span class="sxs-lookup"><span data-stu-id="fe39a-130">Microsoft 365 Business training videos</span></span>](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
