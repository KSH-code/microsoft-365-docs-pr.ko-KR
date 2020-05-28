---
title: 사용자가 암호를 직접 재설정할 수 있도록 허용
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: 셀프 서비스 암호 재설정 도구를 사용 하 여 암호를 다시 설정 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 5c30d1da20998fb7e9681431173070ba57e1b090
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387036"
---
# <a name="let-users-reset-their-own-passwords"></a><span data-ttu-id="5131e-103">사용자가 암호를 직접 재설정할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="5131e-103">Let users reset their own passwords</span></span>

<span data-ttu-id="5131e-104">사용자가 자신의 암호를 재설정해달라고 요청하는 일이 과도하게 많나요?</span><span class="sxs-lookup"><span data-stu-id="5131e-104">Getting crushed with people asking you to reset their passwords?</span></span> <span data-ttu-id="5131e-105">Microsoft 365 관리자는 사용자가 [셀프 서비스 암호 다시 설정 도구](https://go.microsoft.com/fwlink/p/?LinkId=522677) 를 사용 하 여 암호를 다시 설정할 필요가 없도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5131e-105">As the Microsoft 365 admin, you can let people use the [self-service password reset tool](https://go.microsoft.com/fwlink/p/?LinkId=522677) so you don't have to reset passwords for them.</span></span> <span data-ttu-id="5131e-106">관리자의 업무를 덜 수 있습니다!</span><span class="sxs-lookup"><span data-stu-id="5131e-106">Less work for you!</span></span> 
  
<span data-ttu-id="5131e-107">알아야 할 몇 가지 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5131e-107">Here are a few things you need to know:</span></span>
  
- <span data-ttu-id="5131e-108">Microsoft 365 비즈니스, 교육 또는 비영리 유료 요금제를 사용 하 여 클라우드 사용자에 대 한 셀프 서비스 암호 재설정을 **사용할** 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5131e-108">You get self-service password reset for cloud users **free** with any Microsoft 365 business, education, or nonprofit paid plan.</span></span> <span data-ttu-id="5131e-109">Microsoft 365 평가판에서는 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5131e-109">It doesn't work with Microsoft 365 trial.</span></span> 
    
- <span data-ttu-id="5131e-p103">Azure를 사용합니다. 이러한 단계를 수행할 때 자동으로 Azure의 이 기능을 **무료** 로 이용할 수 있습니다. 다른 Azure 기능을 사용하지 않으면 셀프 서비스 암호 재설정을 사용하는 비용이 부과되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5131e-p103">It uses Azure. You'll automatically get this feature in Azure for **free** when you do these steps. It won't cost you anything to turn on self-service password reset if you don't use other Azure features.</span></span> 
    
- <span data-ttu-id="5131e-113">**온-프레미스 Active Directory를 사용**하는 경우 위의 두 지점이 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5131e-113">**If you're using an on-premises Active Directory**, the above two points don't apply.</span></span> <span data-ttu-id="5131e-114">대신이를 설정할 수는 있지만 **AZURE AD Premium에 대 한 유료 구독을 사용 해야**합니다.</span><span class="sxs-lookup"><span data-stu-id="5131e-114">Rather, you can set this up but **it requires a paid subscription to Azure AD Premium**.</span></span> 

<span data-ttu-id="5131e-115">사용자가 자신의 암호를 다시 설정 하도록 허용 하는 방법에 대 한 짧은 비디오를 시청 하세요.</span><span class="sxs-lookup"><span data-stu-id="5131e-115">Watch a short video about letting users reset their own passwords.</span></span> <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S] 

<span data-ttu-id="5131e-116">이 비디오가 도움이 된 경우에는 [소규모 비즈니스 및 Microsoft 365를 처음 사용하는 사용자들을 위한 완전한 교육 시리즈](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5131e-116">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="let-people-reset-their-own-passwords"></a><span data-ttu-id="5131e-117">사용자가 자신의 암호를 다시 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5131e-117">Let people reset their own passwords</span></span> 

<span data-ttu-id="5131e-118">다음 단계에서는 비즈니스의 모든 사용자에 대해 셀프 서비스 암호 재설정을 켭니다.</span><span class="sxs-lookup"><span data-stu-id="5131e-118">These steps turn on self-service password reset for everyone in your business.</span></span>
  
::: moniker range="o365-worldwide"
1. <span data-ttu-id="5131e-119">관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">설정</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="5131e-119">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Settings</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="5131e-120"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">관리 센터</a>에서 **설정** \> **보안 &amp; 개인 정보** 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="5131e-120">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="5131e-121"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">관리 센터</a>에서 **설정** \> **설정** \> **보안 &amp; 개인 정보** 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="5131e-121">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Settings** \>**Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

   
2. <span data-ttu-id="5131e-122">설정 페이지 맨 위에서 **보안 & 개인 정보**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5131e-122">At the top of the Settings page select **Security & Privacy**.</span></span>
  
3. <span data-ttu-id="5131e-123">**셀프 서비스 암호 재설정**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5131e-123">Select **Self Service Password Reset**.</span></span>
  
4. <span data-ttu-id="5131e-124">속성 페이지에서 **모두** 를 선택 하 여 회사의 모든 사용자에 대해 사용 하도록 설정 하 고 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5131e-124">On the Properties page, select **All** to enable it for everyone in your business, and then select **Save**.</span></span>
  
5. <span data-ttu-id="5131e-125">사용자가 로그인 하면 나중에 암호를 다시 설정 하는 데 도움이 되는 추가 연락처 정보를 입력 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5131e-125">When your users sign in, they will be prompted to enter additional contact information that will help them reset their password in the future.</span></span>

## <a name="related-articles"></a><span data-ttu-id="5131e-126">관련 문서</span><span class="sxs-lookup"><span data-stu-id="5131e-126">Related articles</span></span>

[<span data-ttu-id="5131e-127">조직의 암호 만료 정책 설정</span><span class="sxs-lookup"><span data-stu-id="5131e-127">Set the password expiration policy for your organization</span></span>](../manage/set-password-expiration-policy.md)
  
[<span data-ttu-id="5131e-128">개별 사용자 암호가 만료되지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="5131e-128">Set an individual user's password to never expire</span></span>](set-password-to-never-expire.md)

[<span data-ttu-id="5131e-129">Microsoft 365 Business 교육 비디오</span><span class="sxs-lookup"><span data-stu-id="5131e-129">Microsoft 365 Business training videos</span></span>](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
