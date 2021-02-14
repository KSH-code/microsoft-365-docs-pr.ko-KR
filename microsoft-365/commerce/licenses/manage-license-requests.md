---
title: 라이선스 요청 관리
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- commerce
ms.custom: MACBillingLicensesRequests
search.appverid:
- MET150
description: Microsoft 365 비즈니스 에디션 구독에 대한 사용자의 라이선스 요청을 검토하고 승인하거나 거부하는 방법을 자세히 알아보습니다.
ms.date: 08/07/2020
ms.openlocfilehash: cbcdc5550d404278832cc702560ac55f6ace8a44
ms.sourcegitcommit: 9550298946f8accb90cd59be7b46b71d4bf4f8cc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2020
ms.locfileid: "46597661"
---
# <a name="manage-license-requests"></a><span data-ttu-id="be881-103">라이선스 요청 관리</span><span class="sxs-lookup"><span data-stu-id="be881-103">Manage license requests</span></span>

> [!NOTE]
> <span data-ttu-id="be881-104">이 문서의 정보는 셀프 서비스 구매 제품에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="be881-104">The information in this article only applies to self-service purchased products.</span></span> <span data-ttu-id="be881-105">자세한 내용은 셀프 서비스 [구매 FAQ를 참조합니다.](../subscriptions/self-service-purchase-faq.md)</span><span class="sxs-lookup"><span data-stu-id="be881-105">To learn more, see [Self-service purchase FAQ](../subscriptions/self-service-purchase-faq.md).</span></span>

<span data-ttu-id="be881-106">조직에서 셀프 서비스 구매를 사용하지 않도록 설정한 경우 라이선스 요청을 사용하여 사용자의 라이선스 요청 프로세스를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be881-106">If you disable self-service purchases in your organization, you can use licenses requests to manage the license request process for your users.</span></span> <span data-ttu-id="be881-107">사용자가 차단한 제품에 대해 셀프 서비스 구매를 할 때 라이선스 요청을 관리자에게 제출할 수 있습니다. 요청을 할 때 제품에 대한 라이선스도 필요한 다른 사용자의 이름을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be881-107">When a user tries to make a self-service purchase for a product that you’ve blocked, they can submit a request for a license to you, the admin. When they make a request, they can add the names of other users who also need licenses for the product.</span></span>

> [!NOTE]
> <span data-ttu-id="be881-108">사용자가 셀프 서비스 구매를 하지 못하게 차단하면 Microsoft는 마케팅 전자 메일을 보내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="be881-108">If you block users from making self-service purchases, Microsoft doesn’t send them marketing emails.</span></span> <span data-ttu-id="be881-109">또한 제품의 평가판을 사용하는 경우 구입하라는 메시지가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="be881-109">Also, if they’re using a trial version of a product, they don’t see prompts to buy it.</span></span> <span data-ttu-id="be881-110">자세한 내용은 셀프 서비스 구매 [관리(관리자)를 참조하세요.](../subscriptions/manage-self-service-purchases-admins.md)</span><span class="sxs-lookup"><span data-stu-id="be881-110">To learn more, see [Manage self-service purchases (Admin)](../subscriptions/manage-self-service-purchases-admins.md).</span></span>

<span data-ttu-id="be881-111">라이선스 요청을 보고 관리하기 위해  관리자는 라이선스 페이지의 요청 **탭을** 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="be881-111">To see and manage license requests, admin uses the **Requests** tab on the **Licensing** page.</span></span> <span data-ttu-id="be881-112">이 목록에는 요청된 제품의 이름, 라이선스를 요청하는 사람의 이름, 요청한 날짜 및 요청 상태가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="be881-112">The list shows the name of the product that is requested, name of the person requesting a license, date requested, and status of the request.</span></span> <span data-ttu-id="be881-113">관리자는 목록을 필터링하여 보류 중 또는 완료된 요청을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be881-113">Admins can filter the list to show requests that are pending or completed.</span></span> <span data-ttu-id="be881-114">요청은 30일 동안 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="be881-114">Requests are held for 30 days.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="be881-115">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="be881-115">Before you begin</span></span>

<span data-ttu-id="be881-116">이 문서의 작업을 수행하려면 전역 관리자 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be881-116">You must be a Global admin to perform the tasks in this article.</span></span> <span data-ttu-id="be881-117">자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="be881-117">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="use-your-own-request-process"></a><span data-ttu-id="be881-118">자체 요청 프로세스 사용</span><span class="sxs-lookup"><span data-stu-id="be881-118">Use your own request process</span></span>

<span data-ttu-id="be881-119">조직에 자체 요청 프로세스가 있는 경우 대신 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be881-119">If your organization has its own request process, you can use it instead.</span></span> <span data-ttu-id="be881-120">사용자가 라이선스를 요청할 때 표시되는 메시지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be881-120">You create a message that is displayed to users when they request a license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="be881-121">자체 요청 프로세스를 사용하는 경우 요청 탭에 요청이 **표시되지** 않습니다. 메시지를 추가하기 전의 기존 요청은 승인하거나 거부할 때까지 계속 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="be881-121">If you use your own request process, no requests are displayed on the **Requests** tab. Existing requests from before you added your message continue to appear until you approve or decline them.</span></span>

1. <span data-ttu-id="be881-122">관리 센터에서 청구 라이선스 페이지로 이동한 다음 요청  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank"></a> **탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="be881-122">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="be881-123">대신 **기존 요청 프로세스 사용 선택.**</span><span class="sxs-lookup"><span data-stu-id="be881-123">Select **Use your existing request process instead**.</span></span>
3. <span data-ttu-id="be881-124">오른쪽 창의 메시지 상자에 사용자가 라이선스를 요청할 때 사용자에게 표시하게 할 메시지를 입력합니다. </span><span class="sxs-lookup"><span data-stu-id="be881-124">In the right pane, in the **Message** box, type the message you want users to see when they request a license.</span></span> <span data-ttu-id="be881-125">조직 정책 또는 기타 설명서에 대한 링크도 포함하려면 설명서 링크(선택 **사항)** 텍스트 상자에 URL을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="be881-125">If you want to also include a link to your organizations policy or other documentation, enter the URL in the **Link to documentation (optional)** text box.</span></span>
4. <span data-ttu-id="be881-126">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="be881-126">Select **Save**.</span></span>

<span data-ttu-id="be881-127">요청 목록으로 **돌아오면** 자체 라이선스 요청 프로세스를 사용 중이신 메시지가 **표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="be881-127">When you return to the **Requests** list, you see the message **You’re using your own license request process**.</span></span> <span data-ttu-id="be881-128">사용자에게 전송된 메시지를 변경하려면 대신 기존 요청 **프로세스 사용을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="be881-128">To make changes to the message that is sent to users, select **Use your existing request process instead**.</span></span>

## <a name="stop-using-your-own-request-process"></a><span data-ttu-id="be881-129">자체 요청 프로세스 사용 중지</span><span class="sxs-lookup"><span data-stu-id="be881-129">Stop using your own request process</span></span>

1. <span data-ttu-id="be881-130">관리 센터에서 청구 라이선스 페이지로 이동한 다음 요청  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank"></a> **탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="be881-130">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="be881-131">대신 **기존 요청 프로세스 사용 선택.**</span><span class="sxs-lookup"><span data-stu-id="be881-131">Select **Use your existing request process instead**.</span></span>
3. <span data-ttu-id="be881-132">오른쪽 창에서 조직의 요청 프로세스 사용 확인란의 **선택을** 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="be881-132">In the right pane, clear the **Use my organization’s request process** check box.</span></span>
4. <span data-ttu-id="be881-133">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="be881-133">Select **Save**.</span></span>

## <a name="approve-or-deny-a-license-request"></a><span data-ttu-id="be881-134">라이선스 요청 승인 또는 거부</span><span class="sxs-lookup"><span data-stu-id="be881-134">Approve or deny a license request</span></span>

1. <span data-ttu-id="be881-135">관리 센터에서 청구 라이선스 페이지로 이동한 다음 요청  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank"></a> **탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="be881-135">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="be881-136">검토할 요청이 포함된 행을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="be881-136">Select the row that contains the request you want to review.</span></span> <span data-ttu-id="be881-137">오른쪽 창에는 제품에 대한 라이선스를 원하는 사용자에 대한 세부 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="be881-137">The right pane shows details about which users want licenses to the product.</span></span>
3. <span data-ttu-id="be881-138">전체 요청을 거부하려면 승인 안 함을 선택하고 **대화** 상자에서 승인 **안 함을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="be881-138">To deny the entire request, select **Don’t approve**, and in the dialog box, select **Don’t approve**.</span></span>
4. <span data-ttu-id="be881-139">일부 사용자를 요청을 거부하지만 다른 사용자를 승인하려면 제거할 사용자의 이름으로 X를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="be881-139">To deny some users for the request, but approve others, select the X by the name of the users that you want to remove.</span></span> <span data-ttu-id="be881-140">해당 이름은 Do **not assign to these users( Do not assign to these users)에서 이동됩니다.**</span><span class="sxs-lookup"><span data-stu-id="be881-140">Their names are moved under **Do not assign to these users**.</span></span>
5. <span data-ttu-id="be881-141">두 개 이상의 제품이 있는 경우 제품 선택에서 라이선스를 할당하는 데 사용할 제품을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="be881-141">If you have more than one product, under **Select a product**, select the one that you want to use to assign licenses for.</span></span>
6. <span data-ttu-id="be881-142">사용자가 특정 앱 및 서비스에 대한 액세스를 거부할 수 있도록 앱 및 서비스 켜기 또는 끄기 기능을 확장한 다음 제외하려는 앱 및 서비스에 대한 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="be881-142">To deny users access to certain app and services, expand **Turn apps and services on or off**, then clear the check boxes for the ones you want to exclude.</span></span>
7. <span data-ttu-id="be881-143">창 아래쪽의 텍스트 상자에 선택적 메시지를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="be881-143">At the bottom of the pane, type an optional message in the text box.</span></span>
8. <span data-ttu-id="be881-144">완료되면 승인을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="be881-144">When you’re finished, select **Approve**.</span></span> <span data-ttu-id="be881-145">오른쪽 창에는 요청의 세부 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="be881-145">The right pane shows the details of the request.</span></span>
9. <span data-ttu-id="be881-146">오른쪽 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="be881-146">Close the right pane.</span></span>
    <span data-ttu-id="be881-147">사용자는 요청이 승인 또는 거부되었습니다는 내용의 전자 메일을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="be881-147">Users receive an email that says their request was approved or denied.</span></span>

## <a name="related-content"></a><span data-ttu-id="be881-148">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="be881-148">Related content</span></span>

<span data-ttu-id="be881-149">[사용자에게 라이선스 할당(문서)\](../../admin/manage/assign-licenses-to-users.md)</span><span class="sxs-lookup"><span data-stu-id="be881-149">[Assign licenses to users](../../admin/manage/assign-licenses-to-users.md) (article)\</span></span>
<span data-ttu-id="be881-150">[사용자를 다른 구독으로](../subscriptions/move-users-different-subscription.md) 이동(문서)</span><span class="sxs-lookup"><span data-stu-id="be881-150">[Move users to a different subscription](../subscriptions/move-users-different-subscription.md) (article)</span></span>\
<span data-ttu-id="be881-151">[구독 라이선스 구입 또는](buy-licenses.md) 제거(문서)</span><span class="sxs-lookup"><span data-stu-id="be881-151">[Buy or remove subscription licenses](buy-licenses.md) (article)</span></span>