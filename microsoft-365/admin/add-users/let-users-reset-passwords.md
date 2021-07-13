---
title: 사용자가 암호를 직접 재설정할 수 있도록 허용
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
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: 셀프 서비스 암호 재설정 도구를 사용하여 사용자가 암호를 직접 재설정할 수 있도록 하는 정책을 설정하는 방법을 배워야 합니다.
ms.openlocfilehash: ac6d7f16cb35cec757340a94c262c3541bea927a
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394318"
---
# <a name="let-users-reset-their-own-passwords"></a><span data-ttu-id="e0bc5-103">사용자가 암호를 직접 재설정할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="e0bc5-103">Let users reset their own passwords</span></span>

<span data-ttu-id="e0bc5-104">관리자는 Microsoft 365 셀프 서비스 암호 재설정 도구를 [](https://go.microsoft.com/fwlink/p/?LinkId=522677) 사용할 수 있도록 하여 암호를 다시 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0bc5-104">As the Microsoft 365 admin, you can let people use the [self-service password reset tool](https://go.microsoft.com/fwlink/p/?LinkId=522677) so you don't have to reset passwords for them.</span></span> <span data-ttu-id="e0bc5-105">관리자의 업무를 덜 수 있습니다!</span><span class="sxs-lookup"><span data-stu-id="e0bc5-105">Less work for you!</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="e0bc5-106">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="e0bc5-106">Before you begin</span></span>
  
- <span data-ttu-id="e0bc5-107">클라우드 사용자에 대해 비즈니스,  교육 또는 비영리 Microsoft 365 셀프 서비스 암호 재설정을 무료로 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0bc5-107">You get self-service password reset for cloud users **free** with any Microsoft 365 business, education, or nonprofit paid plan.</span></span> <span data-ttu-id="e0bc5-108">평가판에서는 작동하지 Microsoft 365 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e0bc5-108">It doesn't work with Microsoft 365 trial.</span></span>

- <span data-ttu-id="e0bc5-p103">Azure를 사용합니다. 이러한 단계를 수행할 때 자동으로 Azure의 이 기능을 **무료** 로 이용할 수 있습니다. 다른 Azure 기능을 사용하지 않으면 셀프 서비스 암호 재설정을 사용하는 비용이 부과되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e0bc5-p103">It uses Azure. You'll automatically get this feature in Azure for **free** when you do these steps. It won't cost you anything to turn on self-service password reset if you don't use other Azure features.</span></span>

- <span data-ttu-id="e0bc5-112">**If you're using an on-premises Active Directory**, the above two points don't apply.</span><span class="sxs-lookup"><span data-stu-id="e0bc5-112">**If you're using an on-premises Active Directory**, the above two points don't apply.</span></span> <span data-ttu-id="e0bc5-113">대신 를 설정할 수 있지만 를 설치하려면 유료 **구독이 Azure AD Premium.**</span><span class="sxs-lookup"><span data-stu-id="e0bc5-113">Rather, you can set this up but **it requires a paid subscription to Azure AD Premium**.</span></span>

<span data-ttu-id="e0bc5-114">회사, 학교 또는 비영리용 암호 만료 정책을 설정하는 사용자를 위한 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="e0bc5-114">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="e0bc5-115">이 단계를 완료하려면 Microsoft 365 관리자 계정으로 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0bc5-115">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> [<span data-ttu-id="e0bc5-116">관리자 계정이란?</span><span class="sxs-lookup"><span data-stu-id="e0bc5-116">What's an admin account?</span></span>](../../business-video/admin-center-overview.md)

<span data-ttu-id="e0bc5-117">이러한 단계를 [수행하려면](about-admin-roles.md) 전역 관리자 또는 암호 관리자 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0bc5-117">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

## <a name="watch-let-users-reset-their-own-passwords"></a><span data-ttu-id="e0bc5-118">감시: 사용자가 암호를 직접 재설정할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0bc5-118">Watch: Let users reset their own passwords</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

<span data-ttu-id="e0bc5-119">이 비디오가 도움이 된 경우에는 [소규모 비즈니스와 Microsoft 365를 처음 사용하는 사용자를 위한 전체 교육 시리즈](../../business-video/index.yml)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e0bc5-119">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](../../business-video/index.yml).</span></span>

## <a name="steps-let-people-reset-their-own-passwords"></a><span data-ttu-id="e0bc5-120">단계: 사용자가 암호를 직접 재설정할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0bc5-120">Steps: Let people reset their own passwords</span></span>

<span data-ttu-id="e0bc5-121">다음 단계에서는 비즈니스의 모든 사용자에 대해 셀프 서비스 암호 재설정을 켭니다.</span><span class="sxs-lookup"><span data-stu-id="e0bc5-121">These steps turn on self-service password reset for everyone in your business.</span></span>

1. <span data-ttu-id="e0bc5-122">관리 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">센터에서</a>관리 설정   >  **페이지로** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="e0bc5-122">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>, go to the **Settings** > **Org settings** page.</span></span>

2. <span data-ttu-id="e0bc5-123">At the top of the **Org settings** page, select the **Security & Privacy** tab.</span><span class="sxs-lookup"><span data-stu-id="e0bc5-123">At the top of the **Org settings** page, select the **Security & Privacy** tab.</span></span>
  
3. <span data-ttu-id="e0bc5-124">셀프 **서비스 암호 재설정 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e0bc5-124">Select **Self-service Password Reset**.</span></span>

4. <span data-ttu-id="e0bc5-125">셀프 **서비스 암호 재설정에서** Azure Portal로 이동을 선택하여 셀프 서비스 암호 **재설정을 켜기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e0bc5-125">Under **Self-service password reset**, select **Go to the Azure portal to turn on self-service password reset**.</span></span>

5. <span data-ttu-id="e0bc5-126">왼쪽 탐색 창에서 사용자 를 선택한 다음 사용자 창에서 | **모든 사용자** 페이지에서 암호 재설정 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e0bc5-126">In the left navigation pane, select **Users**, and then, on the **Users | All users** page, select **Password reset**.</span></span>
  
6. <span data-ttu-id="e0bc5-127">속성 **페이지에서** 모두를  선택하여 비즈니스의 모든 사용자에 대해 사용하도록 설정한 다음 저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e0bc5-127">On the **Properties** page, select **All** to enable it for everyone in your business, and then select **Save**.</span></span>
  
7. <span data-ttu-id="e0bc5-128">사용자가 로그인하면 향후 암호를 다시 설정하는 데 도움이 되는 추가 연락처 정보를 입력하라는 메시지가 표시될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e0bc5-128">When your users sign in, they will be prompted to enter additional contact information that will help them reset their password in the future.</span></span>

## <a name="related-content"></a><span data-ttu-id="e0bc5-129">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="e0bc5-129">Related content</span></span>

<span data-ttu-id="e0bc5-130">[조직의 암호 만료 정책](../manage/set-password-expiration-policy.md) 설정(문서)</span><span class="sxs-lookup"><span data-stu-id="e0bc5-130">[Set the password expiration policy for your organization](../manage/set-password-expiration-policy.md) (article)</span></span>\
<span data-ttu-id="e0bc5-131">[개별 사용자의 암호를 만료 기한 없음으로 설정](set-password-to-never-expire.md)(문서)</span><span class="sxs-lookup"><span data-stu-id="e0bc5-131">[Set an individual user's password to never expire](set-password-to-never-expire.md) (article)</span></span>\
<span data-ttu-id="e0bc5-132">[Microsoft 365 비즈니스 교육 비디오(링크](../../business-video/index.yml) 페이지)</span><span class="sxs-lookup"><span data-stu-id="e0bc5-132">[Microsoft 365 Business training videos](../../business-video/index.yml) (link page)</span></span>
