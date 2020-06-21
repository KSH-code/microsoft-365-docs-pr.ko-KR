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
ms.openlocfilehash: 288613023ee61626bf12f7090ad0ff73139ef06d
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780592"
---
# <a name="let-users-reset-their-own-passwords"></a><span data-ttu-id="86c8c-103">사용자가 암호를 직접 재설정할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="86c8c-103">Let users reset their own passwords</span></span>

<span data-ttu-id="86c8c-104">사용자가 자신의 암호를 재설정해달라고 요청하는 일이 과도하게 많나요?</span><span class="sxs-lookup"><span data-stu-id="86c8c-104">Getting crushed with people asking you to reset their passwords?</span></span> <span data-ttu-id="86c8c-105">Microsoft 365 관리자는 사용자가 [셀프 서비스 암호 다시 설정 도구](https://go.microsoft.com/fwlink/p/?LinkId=522677) 를 사용 하 여 암호를 다시 설정할 필요가 없도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86c8c-105">As the Microsoft 365 admin, you can let people use the [self-service password reset tool](https://go.microsoft.com/fwlink/p/?LinkId=522677) so you don't have to reset passwords for them.</span></span> <span data-ttu-id="86c8c-106">관리자의 업무를 덜 수 있습니다!</span><span class="sxs-lookup"><span data-stu-id="86c8c-106">Less work for you!</span></span> 
  
<span data-ttu-id="86c8c-107">알아야 할 몇 가지 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="86c8c-107">Here are a few things you need to know:</span></span>
  
- <span data-ttu-id="86c8c-108">Microsoft 365 비즈니스, 교육 또는 비영리 유료 요금제를 사용 하 여 클라우드 사용자에 대 한 셀프 서비스 암호 재설정을 **사용할** 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86c8c-108">You get self-service password reset for cloud users **free** with any Microsoft 365 business, education, or nonprofit paid plan.</span></span> <span data-ttu-id="86c8c-109">Microsoft 365 평가판에서는 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="86c8c-109">It doesn't work with Microsoft 365 trial.</span></span>

- <span data-ttu-id="86c8c-110">It uses Azure.</span><span class="sxs-lookup"><span data-stu-id="86c8c-110">It uses Azure.</span></span> <span data-ttu-id="86c8c-111">You'll automatically get this feature in Azure for **free** when you do these steps.</span><span class="sxs-lookup"><span data-stu-id="86c8c-111">You'll automatically get this feature in Azure for **free** when you do these steps.</span></span> <span data-ttu-id="86c8c-112">It won't cost you anything to turn on self-service password reset if you don't use other Azure features.</span><span class="sxs-lookup"><span data-stu-id="86c8c-112">It won't cost you anything to turn on self-service password reset if you don't use other Azure features.</span></span>

- <span data-ttu-id="86c8c-113">**온-프레미스 Active Directory를 사용**하는 경우 위의 두 지점이 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="86c8c-113">**If you're using an on-premises Active Directory**, the above two points don't apply.</span></span> <span data-ttu-id="86c8c-114">대신이를 설정할 수는 있지만 **AZURE AD Premium에 대 한 유료 구독을 사용 해야**합니다.</span><span class="sxs-lookup"><span data-stu-id="86c8c-114">Rather, you can set this up but **it requires a paid subscription to Azure AD Premium**.</span></span>

<span data-ttu-id="86c8c-115">사용자가 자신의 암호를 다시 설정 하도록 허용 하는 방법에 대 한 짧은 비디오를 시청 하세요.</span><span class="sxs-lookup"><span data-stu-id="86c8c-115">Watch a short video about letting users reset their own passwords.</span></span> <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

<span data-ttu-id="86c8c-116">이 비디오가 도움이 된 경우에는 [소규모 비즈니스 및 Microsoft 365를 처음 사용하는 사용자들을 위한 완전한 교육 시리즈](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="86c8c-116">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="let-people-reset-their-own-passwords"></a><span data-ttu-id="86c8c-117">사용자가 자신의 암호를 다시 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86c8c-117">Let people reset their own passwords</span></span>

<span data-ttu-id="86c8c-118">다음 단계에서는 비즈니스의 모든 사용자에 대해 셀프 서비스 암호 재설정을 켭니다.</span><span class="sxs-lookup"><span data-stu-id="86c8c-118">These steps turn on self-service password reset for everyone in your business.</span></span>
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="86c8c-119"><a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">관리 센터</a>에서 조직 설정 **설정** > **Org settings** 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c8c-119">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>, go to the **Settings** > **Org settings** page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="86c8c-120"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">관리 센터</a>에서 **설정** \> **보안 &amp; 개인 정보** 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c8c-120">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="86c8c-121"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">관리 센터</a>에서 **설정** \> **설정** \> **보안 &amp; 개인 정보** 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c8c-121">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Settings** \>**Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

2. <span data-ttu-id="86c8c-122">**조직 설정** 페이지 맨 위에서 **보안 & 개인 정보 보호** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c8c-122">At the top of the **Org settings** page, select the **Security & Privacy** tab.</span></span>
  
3. <span data-ttu-id="86c8c-123">**셀프 서비스 암호 재설정**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c8c-123">Select **Self-service Password Reset**.</span></span>

4. <span data-ttu-id="86c8c-124">**셀프 서비스 암호 재설정**에서 **Azure portal로 이동을 선택 하 여 셀프 서비스 암호 재설정을 켭니다**.</span><span class="sxs-lookup"><span data-stu-id="86c8c-124">Under **Self-service password reset**, select **Go to the Azure portal to turn on self-service password reset**.</span></span>

5. <span data-ttu-id="86c8c-125">왼쪽 탐색 창에서 **사용자**를 선택 하 고 **사용자 | 모든 사용자** 페이지에서 **암호 재설정**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c8c-125">In the left navigation pane, select **Users**, and then, on the **Users | All users** page, select **Password reset**.</span></span>
  
6. <span data-ttu-id="86c8c-126">**속성** 페이지에서 **모두** 를 선택 하 여 회사의 모든 사용자에 대해 사용 하도록 설정 하 고 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c8c-126">On the **Properties** page, select **All** to enable it for everyone in your business, and then select **Save**.</span></span>
  
7. <span data-ttu-id="86c8c-127">사용자가 로그인 하면 나중에 암호를 다시 설정 하는 데 도움이 되는 추가 연락처 정보를 입력 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86c8c-127">When your users sign in, they will be prompted to enter additional contact information that will help them reset their password in the future.</span></span>

## <a name="related-articles"></a><span data-ttu-id="86c8c-128">관련 문서</span><span class="sxs-lookup"><span data-stu-id="86c8c-128">Related articles</span></span>

[<span data-ttu-id="86c8c-129">조직의 암호 만료 정책 설정</span><span class="sxs-lookup"><span data-stu-id="86c8c-129">Set the password expiration policy for your organization</span></span>](../manage/set-password-expiration-policy.md)
  
[<span data-ttu-id="86c8c-130">개별 사용자 암호가 만료되지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="86c8c-130">Set an individual user's password to never expire</span></span>](set-password-to-never-expire.md)

[<span data-ttu-id="86c8c-131">Microsoft 365 Business 교육 비디오</span><span class="sxs-lookup"><span data-stu-id="86c8c-131">Microsoft 365 Business training videos</span></span>](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
