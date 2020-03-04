---
title: 관리자 (셀프 서비스 구입) 관리
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
- commerce
search.appverid:
- MET150
description: 관리자는 조직의 사용자가 만든 셀프 서비스 구매를 관리 하는 방법을 확인할 수 있습니다.
ms.openlocfilehash: ab0e98963e1274925fcf678307907a93eafc9663
ms.sourcegitcommit: 9c335d110e0b499501edc8a31b987641819118a1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2020
ms.locfileid: "42409633"
---
# <a name="manage-self-service-purchases-admin"></a><span data-ttu-id="2da6b-103">셀프 서비스 구매(관리자) 관리</span><span class="sxs-lookup"><span data-stu-id="2da6b-103">Manage self-service purchases (Admin)</span></span>

<span data-ttu-id="2da6b-104">관리자는 조직의 사용자가 만든 셀프 서비스 구매를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2da6b-104">As an admin, you can see self-service purchases made by people in your organization.</span></span> <span data-ttu-id="2da6b-105">제품, 구매자 이름, 구독 구입, 만료 날짜, 구입 가격 및 할당 된 사용자를 각 셀프 서비스 구매에 대해 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2da6b-105">You can see the product, purchaser name, subscriptions purchased, expiry date, purchase price, and assigned users for each self-service purchase.</span></span> <span data-ttu-id="2da6b-106">조직에 필요한 경우 PowerShell을 통해 제품별로 셀프 서비스 구매를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2da6b-106">If required for your organization, you can turn off self-service purchasing on a per product basis via PowerShell.</span></span> <span data-ttu-id="2da6b-107">셀프 서비스 구매 나 중앙을 통해 구매한 제품에 대해 동일한 데이터 관리 및 액세스 정책을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da6b-107">You have the same data management and access policies over products bought through self-service purchase or centrally.</span></span>

<span data-ttu-id="2da6b-108">조직의 사용자가 셀프 서비스 구매를 수행할 수 있는지 여부를 제어할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2da6b-108">You can also control whether users in your organization can make self-service purchases.</span></span> <span data-ttu-id="2da6b-109">자세한 내용은 [Use AllowSelfServicePurchase for The MSCommerce PowerShell module](allowselfservicepurchase-powershell.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2da6b-109">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="view-self-service-subscriptions"></a><span data-ttu-id="2da6b-110">셀프 서비스 구독 보기</span><span class="sxs-lookup"><span data-stu-id="2da6b-110">View self-service subscriptions</span></span>

1. <span data-ttu-id="2da6b-111">관리 센터에서 **청구** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">제품 & 서비스</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da6b-111">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Products & services</a> page.</span></span>

2. <span data-ttu-id="2da6b-112">**결과 구체화**옆의 **계정 유형** 드롭다운에서 **셀프 서비스**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da6b-112">Next to **Refine results**, from the **Account type** drop-down, choose **Self-service**.</span></span>

3. <span data-ttu-id="2da6b-113">구독에 대 한 세부 정보를 보려면 목록에서 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da6b-113">To view more details about a subscription, choose one from the list.</span></span>

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a><span data-ttu-id="2da6b-114">셀프 서비스 구매 구독 라이선스를 가진 사용자 보기</span><span class="sxs-lookup"><span data-stu-id="2da6b-114">View who has licenses for a self-service purchase subscription</span></span>

1. <span data-ttu-id="2da6b-115">관리 센터에서 **청구** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">라이선스</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da6b-115">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

2. <span data-ttu-id="2da6b-116">필터 아이콘을 선택한 다음 **셀프 서비스**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da6b-116">Choose the filter icon, then choose **Self-service**.</span></span>

3. <span data-ttu-id="2da6b-117">사용자에 게 할당 된 라이선스를 볼 제품을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da6b-117">Select a product to see licenses assigned to people.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2da6b-118">제품에 대 한 구매를 여러 개 사용 하는 경우 해당 제품이 한 번만 나열 되며 **사용 가능한 수량** 열에 해당 제품에 대해 구매한 모든 구독의 합계가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2da6b-118">If there are multiple purchases for a product, that product is only listed once, and the **Available quantity** column shows the total of all subscriptions bought for that product.</span></span>

4. <span data-ttu-id="2da6b-119">**사용자** 목록은 셀프 서비스 구매를 수행한 사용자 이름별로 그룹화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2da6b-119">The **Users** list is grouped by the names of people who made self-service purchases.</span></span>

5. <span data-ttu-id="2da6b-120">이러한 구독에 대 한 라이선스가 있는 사용자 목록을 내보내려면 내보낼 구독을 선택 하 고 **사용자 내보내기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da6b-120">To export a list of users with licenses for these subscriptions, choose the subscriptions that you want to export, then choose **Export users**.</span></span>

## <a name="disable-or-enable-self-service-purchases"></a><span data-ttu-id="2da6b-121">셀프 서비스 구매 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="2da6b-121">Disable or enable self-service purchases</span></span>

<span data-ttu-id="2da6b-122">조직의 사용자에 대해 셀프 서비스 구매를 사용 하지 않도록 설정 하거나 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2da6b-122">You can disable or enable self-service purchases for users in your organization.</span></span> <span data-ttu-id="2da6b-123">**MSCommerce** PowerShell 모듈에는 조직의 사용자가 셀프 서비스 구매를 수행할 수 있는지 여부 및 해당 제품에 **대 한 정책에 대** 한 **policyid** 매개 변수 값이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2da6b-123">The **MSCommerce** PowerShell module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases, and for which products.</span></span>

<span data-ttu-id="2da6b-124">**MSCommerce** PowerShell 모듈을 사용 하 여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2da6b-124">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="2da6b-125">제품이 사용 하거나 사용 하지 않도록 \*\*\*\* 설정 되었는지 여부 &mdash; 에 관계 없이 AllowSelfServicePurchase 매개 변수 값의 기본 상태를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da6b-125">View the default state of the **AllowSelfServicePurchase** parameter value &mdash; whether it's enabled or disabled by product</span></span>
- <span data-ttu-id="2da6b-126">해당 하는 제품 목록 및 셀프 서비스 구매가 사용 하도록 설정 되었는지 여부 확인</span><span class="sxs-lookup"><span data-stu-id="2da6b-126">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="2da6b-127">특정 제품에 대 한 현재 설정을 보거나 수정 하 여 사용 하거나 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="2da6b-127">View or modify the current setting for a specific product to either enable or disable it</span></span>

<span data-ttu-id="2da6b-128">자세한 내용은 [Use AllowSelfServicePurchase for The MSCommerce PowerShell module](allowselfservicepurchase-powershell.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2da6b-128">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="centralize-licenses-under-a-single-subscription"></a><span data-ttu-id="2da6b-129">단일 구독을 통해 라이선스 중앙 집중화</span><span class="sxs-lookup"><span data-stu-id="2da6b-129">Centralize licenses under a single subscription</span></span>

<span data-ttu-id="2da6b-130">기존 라이선스를 할당 하거나 셀프 서비스 구매에 할당 된 사용자에 대 한 기존 계약을 통해 추가 구독을 구매할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2da6b-130">You can assign existing licenses or purchase additional subscriptions through existing agreements for users assigned to self-service purchases.</span></span> <span data-ttu-id="2da6b-131">이러한 중앙에서 구매한 라이선스를 할당 한 후에는 purchasers에서 기존 구독을 취소 하도록 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2da6b-131">After you assign these centrally purchased licenses, you can request that purchasers cancel their existing subscriptions.</span></span>

1. <span data-ttu-id="2da6b-132">전역 관리자 또는 청구 관리자 계정을 사용 하 여 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">관리 센터</a> 에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da6b-132">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a> with your Global admin or Billing admin account.</span></span>

2. <span data-ttu-id="2da6b-133">**결제** > <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">구매 서비스</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da6b-133">Go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>

3. <span data-ttu-id="2da6b-134">구매할 제품을 찾아 선택한 다음 **구입**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da6b-134">Find and choose the product that you want to buy, then choose **Buy**.</span></span>

4. <span data-ttu-id="2da6b-135">나머지 단계를 완료 하 여 구매를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da6b-135">Complete the remaining steps to complete your purchase.</span></span>

5. <span data-ttu-id="2da6b-136">보기의 단계에 따라 [셀프 서비스를 구매한 구독에 대 한 라이선스를 가진](#view-who-has-licenses-for-a-self-service-purchase-subscription) 사용자 목록을 내보내 6 단계에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da6b-136">Follow the steps in [View who has licenses for a self-service purchased subscription](#view-who-has-licenses-for-a-self-service-purchase-subscription) to export a list of users to reference in step 6.</span></span>

6. <span data-ttu-id="2da6b-137">다른 구독에 라이선스가 있는 모든 사용자에 게 라이선스를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da6b-137">Assign licenses to everyone who has a license in the other subscription.</span></span> <span data-ttu-id="2da6b-138">전체 단계는 [사용자에 게 라이선스 할당](../../admin/manage/assign-licenses-to-users.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2da6b-138">For full steps, see [Assign licenses to users](../../admin/manage/assign-licenses-to-users.md).</span></span>

7. <span data-ttu-id="2da6b-139">셀프 서비스 구매 구독을 구매한 사용자에 게 문의 하 여 취소 하도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da6b-139">Contact the person who bought the self-service purchase subscription and ask them to cancel it.</span></span>

## <a name="need-help-contact-us"></a><span data-ttu-id="2da6b-140">도움이 필요하신가요?</span><span class="sxs-lookup"><span data-stu-id="2da6b-140">Need help?</span></span> <span data-ttu-id="2da6b-141">문의처.</span><span class="sxs-lookup"><span data-stu-id="2da6b-141">Contact us.</span></span>

<span data-ttu-id="2da6b-142">셀프 서비스 구매에 대 한 일반적인 질문은 [셀프 서비스 구매 FAQ](self-service-purchase-faq.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2da6b-142">For common questions about self-service purchases, see [Self-service purchases FAQ](self-service-purchase-faq.md).</span></span>

<span data-ttu-id="2da6b-143">궁금한 사항이 있거나 셀프 서비스 구매에 도움이 필요한 경우 [고객 지원에 문의 하세요](../../admin/contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="2da6b-143">If you have questions or need help with self-service purchases, [contact support](../../admin/contact-support-for-business-products.md).</span></span>
