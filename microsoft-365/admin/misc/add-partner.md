---
title: 구독 관리자 파트너 추가, 변경, 삭제
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f86e8177-936e-491e-9024-44dea2b296ff
description: 구매 시 레코드의 파트너를 Microsoft 365 파트너를 변경하거나 구독에서 파트너를 삭제합니다.
ms.openlocfilehash: 78419dd6d1370475c0565c0ad072a7b54639ce43
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393862"
---
# <a name="add-change-or-delete-a-subscription-advisor-partner"></a><span data-ttu-id="15523-103">구독 관리자 파트너 추가, 변경, 삭제</span><span class="sxs-lookup"><span data-stu-id="15523-103">Add, change, or delete a subscription advisor partner</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="15523-104">이 문서는 중국의 Office 365 운영하는 21Vianet에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="15523-104">This article applies to Office 365 operated by 21Vianet in China.</span></span> <span data-ttu-id="15523-105">21Vianet 파트너가 21Vianet 파트너의 구독을 관리하도록 Office 365 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="15523-105">It is for organizations who want to allow a 21Vianet Partner to administer their Office 365 subscription for them.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

<span data-ttu-id="15523-106">구독 관리자 역할을 하는 Microsoft 공인 파트너는 구독을 설정하고 유지 관리하는 데 도움이 되는 판매, 지원, 기술 전문 지식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="15523-106">An authorized partner of Microsoft who serves as your subscription advisor provides the sales, support, and technical expertise you need to help you set up and maintain your subscription.</span></span> <span data-ttu-id="15523-107">구독 고문 파트너는 구독을 구매할 때 또는 다른 Microsoft 365 파트너로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15523-107">You can add a subscription advisor partner as a partner of record when you purchase Microsoft 365 or at another time.</span></span> <span data-ttu-id="15523-108">현재 파트너와 작업하고 있지 않은 경우 [Microsoft Pinpoint](https://pinpoint.microsoft.com) 웹 사이트에서 파트너를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15523-108">If you're not currently working with a partner, you can also find one on the [Microsoft Pinpoint](https://pinpoint.microsoft.com) website.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="15523-109">구독 관리자 역할을 하는 Microsoft 공인 파트너는 구독을 설정하고 유지 관리하는 데 도움이 되는 판매, 지원, 기술 전문 지식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="15523-109">An authorized partner of Microsoft who serves as your subscription advisor provides the sales, support, and technical expertise you need to help you set up and maintain your subscription.</span></span> <span data-ttu-id="15523-110">구독 관리자 파트너는 Office 365를 구입할 때 아니면 다른 때에 공식 파트너로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15523-110">You can add a subscription advisor partner as a partner of record when you purchase Office 365 or at another time.</span></span> <span data-ttu-id="15523-111">현재 파트너와 작업하고 있지 않은 경우 [Microsoft Pinpoint](https://pinpoint.microsoft.com) 웹 사이트에서 파트너를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15523-111">If you're not currently working with a partner, you can also find one on the [Microsoft Pinpoint](https://pinpoint.microsoft.com) website.</span></span>

::: moniker-end

## <a name="before-you-begin"></a><span data-ttu-id="15523-112">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="15523-112">Before you begin</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="15523-113">선택한 파트너는 사용하는 Microsoft 서비스 및 해당 서비스를 사용할 국가 또는 지역에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15523-113">The partner you choose depends on the Microsoft services you use and the country or region where you'll use those services.</span></span> <span data-ttu-id="15523-114">구독 파트너를 추가하거나 변경하려면 먼저 파트너에게 Microsoft 파트너 ID를 문의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="15523-114">If you are adding a partner, or changing the partner for your subscription, first you need to get the partner's Microsoft Partner ID by asking the partner for it.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="15523-p105">사용하는 Office 365 서비스와 이 서비스를 사용할 국가 또는 지역에 따라 선택할 수 있는 파트너가 달라집니다. 구독 파트너를 추가하거나 변경하려면 먼저 파트너에게 Microsoft 파트너 ID를 문의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="15523-p105">The partner you choose depends on the Office 365 services you use and the country or region where you'll use those services. If you are adding a partner, or changing the partner for your subscription, first you need to get the partner's Microsoft Partner ID by asking the partner for it.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="15523-117">조직의 관리자는 Office 365 만들기 또는 편집하고, 사용자 암호를 다시 설정하고, 사용자 라이선스를 관리하고, 도메인을 관리하고, 조직의 다른 사용자에게 관리자 권한을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15523-117">As an admin for Office 365, you can create or edit users, reset user passwords, manage user licenses, manage domains, and assign admin permissions to other users in your organization, among other things.</span></span> <span data-ttu-id="15523-118">그러나 다른 사용자가 이러한 관리 작업을 수행하게 하려는 경우 파트너 관계를 만들어 이 역할을 21Vianet의 공인 파트너에게 위임할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15523-118">However, if you want someone else to do these administrative tasks, you can delegate this role to an authorized partner of 21Vianet by creating a partner relationship.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="add-a-partner-at-the-time-of-purchase"></a><span data-ttu-id="15523-119">구입 시 파트너 추가</span><span class="sxs-lookup"><span data-stu-id="15523-119">Add a partner at the time of purchase</span></span>

1. <span data-ttu-id="15523-120">관리 센터에서 청구 구매  서비스 \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">**페이지로**</a> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="15523-120">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">**Purchase services**</a> page.</span></span>
2. <span data-ttu-id="15523-121">구매할 제품을 선택하고 구입을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="15523-121">Select the product that you want to purchase, and then select **Buy**.</span></span>
3. <span data-ttu-id="15523-122">새 파트너를 추가하려면 **주문에** 대한 도움이 필요하세요?를 확장하고 Microsoft 파트너로부터 지원 **요청 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="15523-122">To add a new partner, expand **Need help with your order?** and select **Get assistance from a Microsoft Partner**.</span></span><br>
<span data-ttu-id="15523-123">공급자 페이지의 단계에 따라 파트너를 검색하거나 파트너와 일치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15523-123">Follow the steps on the providers page to either search for, or to get matched with a partner.</span></span>
4. <span data-ttu-id="15523-124">이미 파트너가 있는 경우 체크 아웃 마법사의 두 번째 단계에서 오른쪽 창의 파트너 정보에서 추가를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="15523-124">If you already have a partner, in the second step of the checkout wizard, in the right pane, under Partner information, select **Add**.</span></span>
5. <span data-ttu-id="15523-p107">추가할 파트너의 Microsoft 파트너 ID를 입력합니다. 해당 파트너에게 문의하면 Microsoft 파트너 ID를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15523-p107">Type the Microsoft Partner ID for the partner you're adding. You can get the partner's Microsoft Partner ID by asking the partner for it.</span></span>
6. <span data-ttu-id="15523-127">마법사의 나머지 단계를 완료하여 구독 구입을 마칩니다.</span><span class="sxs-lookup"><span data-stu-id="15523-127">Complete the rest of the wizard to finish buying your subscriptions.</span></span>

::: moniker-end

::: moniker range="o365-germany"

## <a name="add-a-partner-at-the-time-of-purchase"></a><span data-ttu-id="15523-128">구입 시 파트너 추가</span><span class="sxs-lookup"><span data-stu-id="15523-128">Add a partner at the time of purchase</span></span>

1. <span data-ttu-id="15523-129">관리 [센터에서](https://go.microsoft.com/fwlink/p/?linkid=848041)청구 구매 서비스  \> **페이지로** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="15523-129">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=848041), go to the **Billing** \> **Purchase services**  page.</span></span>
2. <span data-ttu-id="15523-130">구매할 제품을 선택하고 구입을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="15523-130">Select the product that you want to purchase, and then select **Buy**.</span></span>
3. <span data-ttu-id="15523-131">새 파트너를 추가하려면 **주문에** 대한 도움이 필요하세요?를 확장하고 Microsoft 파트너로부터 지원 **요청 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="15523-131">To add a new partner, expand **Need help with your order?** and select **Get assistance from a Microsoft Partner**.</span></span><br>
<span data-ttu-id="15523-132">공급자 페이지의 단계에 따라 파트너를 검색하거나 파트너와 일치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15523-132">Follow the steps on the providers page to either search for, or to get matched with a partner.</span></span>
4. <span data-ttu-id="15523-133">이미 파트너가 있는 경우 체크 아웃 마법사의 두 번째 단계에서 오른쪽 창의 파트너 정보에서 추가를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="15523-133">If you already have a partner, in the second step of the checkout wizard, in the right pane, under Partner information, select **Add**.</span></span>
5. <span data-ttu-id="15523-p108">추가할 파트너의 Microsoft 파트너 ID를 입력합니다. 해당 파트너에게 문의하면 Microsoft 파트너 ID를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15523-p108">Type the Microsoft Partner ID for the partner you're adding. You can get the partner's Microsoft Partner ID by asking the partner for it.</span></span>
6. <span data-ttu-id="15523-136">마법사의 나머지 단계를 완료하여 구독 구입을 마칩니다.</span><span class="sxs-lookup"><span data-stu-id="15523-136">Complete the rest of the wizard to finish buying your subscriptions.</span></span>

::: moniker-end

## <a name="add-a-partner-to-an-existing-subscription"></a><span data-ttu-id="15523-137">기존 구독에 파트너 추가</span><span class="sxs-lookup"><span data-stu-id="15523-137">Add a partner to an existing subscription</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="15523-138">관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">내 상품</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="15523-138">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="15523-139">제품 **탭에서** 편집할 구독을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="15523-139">On the **Products** tab, select the subscription that you want to edit.</span></span>
3. <span data-ttu-id="15523-140">구독 세부 정보 페이지의 **파트너 정보에서** 파트너 네트워크 **ID 를 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="15523-140">On the subscription details page, under **Partner information**, type the **Partner Network ID**.</span></span> <span data-ttu-id="15523-141">파트너에게 요청하여 파트너의 Microsoft 파트너 네트워크 ID를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15523-141">You can get the partner's Microsoft Partner Network ID by asking the partner for it.</span></span>
4. <span data-ttu-id="15523-142">**추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="15523-142">Select **Add**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="15523-143">관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">구독</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="15523-143">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>
2. <span data-ttu-id="15523-144">구독이 두 개 이상 있는 경우 편집할 구독을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="15523-144">If you have more than one subscription, select the subscription that you want to edit.</span></span>
3. <span data-ttu-id="15523-145">오른쪽의 구독 비용에서 레코드 파트너 추가에서 세 점(추가 작업)> **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="15523-145">On the right, under the subscription cost, select the three dots (more actions) > **Add partner of record**.</span></span>
4. <span data-ttu-id="15523-p110">추가할 파트너의 Microsoft 파트너 ID를 입력하고 **ID 검사** 를 선택한 다음 **제출** 을 선택합니다. 해당 파트너에게 문의하면 Microsoft 파트너 ID를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15523-p110">Type the Microsoft Partner ID for the partner you're adding, select **Check ID**, and then **Submit**. You can get the partner's Microsoft Partner ID by asking the partner for it.</span></span>
5. <span data-ttu-id="15523-148">파트너 ID가 **구독** 페이지에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="15523-148">The partner ID displays on the **Subscriptions** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="15523-149">이 프로세스는 공인 파트너가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="15523-149">This process is initiated by your authorized partner.</span></span> <span data-ttu-id="15523-150">파트너가 파트너에게 레코드 파트너 역할을 할 수 있는 권한을 부여할지 묻는 전자 메일을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="15523-150">The partner sends you an email to ask you if you want to give them permission to act as a partner of record.</span></span>
  
<span data-ttu-id="15523-151">이 제안을 수락하는 경우</span><span class="sxs-lookup"><span data-stu-id="15523-151">To accept this offer</span></span>
  
1. <span data-ttu-id="15523-152">전자 메일에서 파트너의 약관을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="15523-152">Read the partner's terms in the email.</span></span>
2. <span data-ttu-id="15523-153">계약에 권한을 부여하려면 해당 링크(2016년 8월 1일)의 권한 부여 페이지로 Office 365.</span><span class="sxs-lookup"><span data-stu-id="15523-153">To authorize the agreement, select the link, which goes to an authorization page in Office 365.</span></span>
3. <span data-ttu-id="15523-154">파트너 **관계에서** **예를** 선택하여 파트너에게 위임된 관리자로 권한을 할당하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="15523-154">Under **Partner Relationships**, select **Yes** to authorize the partner to be your delegated admin, and then select **Next**.</span></span>
4. <span data-ttu-id="15523-155">파트너 관계에 대한 제안이 평가판 구독 또는 구매 제안과 함께 제공된 경우 평가판 또는 구독 계정을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="15523-155">If the offer for partner relationship came with a trial subscription or a purchase offer, create your trial or subscription account.</span></span>

::: moniker-end

## <a name="change-the-partner-for-a-subscription"></a><span data-ttu-id="15523-156">구독 파트너 변경</span><span class="sxs-lookup"><span data-stu-id="15523-156">Change the partner for a subscription</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="15523-157">관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">내 상품</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="15523-157">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="15523-158">관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">내 상품</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="15523-158">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Your products</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="15523-159">관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">내 상품</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="15523-159">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Your products</a> page.</span></span>
::: moniker-end
2. <span data-ttu-id="15523-160">구독 세부 정보 페이지의 **파트너 정보에서** 제거를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="15523-160">On the subscriptions details page, under **Partner information**, select **Remove**.</span></span>
3. <span data-ttu-id="15523-161">새 **파트너의 Microsoft 파트너** 네트워크 ID를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="15523-161">Type the **Microsoft Partner Network ID** for the new partner.</span></span> <span data-ttu-id="15523-162">파트너에게 요청하여 파트너의 Microsoft 파트너 ID를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15523-162">You can get the partner's Microsoft Partner ID by asking the partner for it.</span></span>
4. <span data-ttu-id="15523-163">**추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="15523-163">Select **Add**.</span></span>
  
## <a name="view-your-partner-relationships"></a><span data-ttu-id="15523-164">파트너 관계 보기</span><span class="sxs-lookup"><span data-stu-id="15523-164">View your partner relationships</span></span>

- <span data-ttu-id="15523-165">관리 센터에서 파트너 **관계** 설정  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2074649" target="_blank">이동합니다.</a></span><span class="sxs-lookup"><span data-stu-id="15523-165">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2074649" target="_blank">Partner relationships</a> page.</span></span> <span data-ttu-id="15523-166">파트너가 이 페이지에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="15523-166">Your partners are listed on this page.</span></span>

  <span data-ttu-id="15523-167">파트너가 없는 경우 "아무 것도 없습니다."라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="15523-167">If you don't have a partner, you'll see a message that says "There's nothing here."</span></span>
  
## <a name="delete-a-partner-from-a-subscription"></a><span data-ttu-id="15523-168">구독에서 파트너 삭제</span><span class="sxs-lookup"><span data-stu-id="15523-168">Delete a partner from a subscription</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="15523-169">관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">내 상품</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="15523-169">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="15523-170">관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">내 상품</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="15523-170">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Your products</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="15523-171">관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">내 상품</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="15523-171">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Your products</a> page.</span></span>
::: moniker-end
2. <span data-ttu-id="15523-172">제품 **탭에서** 편집할 구독을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="15523-172">On the **Products** tab, select the subscription that you want to edit.</span></span>
3. <span data-ttu-id="15523-173">구독 세부 정보 페이지의 **파트너 정보에서** 제거를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="15523-173">On the subscription details page, under **Partner information**, select **Remove**.</span></span>

## <a name="remove-a-reseller-relationship"></a><span data-ttu-id="15523-174">리셀러 관계 제거</span><span class="sxs-lookup"><span data-stu-id="15523-174">Remove a reseller relationship</span></span>

<span data-ttu-id="15523-175">대리점 관계를 스스로 제거할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="15523-175">You can't remove a reseller relationship yourself.</span></span>

::: moniker range="o365-worldwide"
  
<span data-ttu-id="15523-176">리셀러 관계를 제거하는 경우 **삭제** 옵션이 회색으로 표시되고 대리업체 파트너에게 다음 지침을 따르게 요청해야 합니다. [파트너와의](/partner-center/remove-a-relationship)리셀러 관계 제거.</span><span class="sxs-lookup"><span data-stu-id="15523-176">If you are removing a reseller relationship the **Delete** option is grayed out, and you will have to ask your reseller partner to follow these instructions: [Remove a reseller relationship with partner](/partner-center/remove-a-relationship).</span></span>

::: moniker-end

::: moniker range="o365-germany"
  
<span data-ttu-id="15523-177">리셀러 관계를 제거하는 경우 **삭제** 옵션이 회색으로 표시되고 대리업체 파트너에게 다음 지침을 따르게 요청해야 합니다. [파트너와의](/partner-center/remove-a-relationship)리셀러 관계 제거.</span><span class="sxs-lookup"><span data-stu-id="15523-177">If you are removing a reseller relationship the **Delete** option is grayed out, and you will have to ask your reseller partner to follow these instructions: [Remove a reseller relationship with partner](/partner-center/remove-a-relationship).</span></span>
  
::: moniker-end

::: moniker range="o365-21vianet"
  
<span data-ttu-id="15523-178">리셀러 파트너에게 다음 지침을 따르기 위해 요청해야 합니다. [파트너와의 리셀러](/partner-center/remove-a-relationship)관계 제거.</span><span class="sxs-lookup"><span data-stu-id="15523-178">You will have to ask your reseller partner to follow these instructions: [Remove a reseller relationship with partner](/partner-center/remove-a-relationship).</span></span>
  
::: moniker-end

## <a name="related-content"></a><span data-ttu-id="15523-179">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="15523-179">Related content</span></span>

<span data-ttu-id="15523-180">[파트너 Microsoft 365 대리업체](../manage/find-your-partner-or-reseller.md) 찾기(문서)</span><span class="sxs-lookup"><span data-stu-id="15523-180">[Find your Microsoft 365 partner or reseller](../manage/find-your-partner-or-reseller.md) (article)</span></span>\
<span data-ttu-id="15523-181">[비즈니스용 Microsoft 365 설정](../setup/plan-your-setup.md) 계획(문서)</span><span class="sxs-lookup"><span data-stu-id="15523-181">[Plan your setup of Microsoft 365 for business](../setup/plan-your-setup.md) (article)</span></span>