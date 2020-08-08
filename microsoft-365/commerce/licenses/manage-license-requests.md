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
description: 비즈니스용 Microsoft 365 구독에 대 한 사용자의 라이선스 요청을 검토 하 고 승인 하거나 거부 하는 방법을 알아봅니다.
ms.date: 08/07/2020
ms.openlocfilehash: cbcdc5550d404278832cc702560ac55f6ace8a44
ms.sourcegitcommit: 9550298946f8accb90cd59be7b46b71d4bf4f8cc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2020
ms.locfileid: "46597661"
---
# <a name="manage-license-requests"></a><span data-ttu-id="850d9-103">라이선스 요청 관리</span><span class="sxs-lookup"><span data-stu-id="850d9-103">Manage license requests</span></span>

> [!NOTE]
> <span data-ttu-id="850d9-104">이 문서의 정보는 셀프 서비스 구매한 제품에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="850d9-104">The information in this article only applies to self-service purchased products.</span></span> <span data-ttu-id="850d9-105">자세한 내용은 [셀프 서비스 구매 FAQ](../subscriptions/self-service-purchase-faq.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="850d9-105">To learn more, see [Self-service purchase FAQ](../subscriptions/self-service-purchase-faq.md).</span></span>

<span data-ttu-id="850d9-106">조직에서 셀프 서비스 구매를 사용 하지 않도록 설정 하는 경우 라이선스 요청을 사용 하 여 사용자에 대 한 라이선스 요청 프로세스를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="850d9-106">If you disable self-service purchases in your organization, you can use licenses requests to manage the license request process for your users.</span></span> <span data-ttu-id="850d9-107">사용자가 차단 된 제품에 대 한 셀프 서비스 구매를 설정 하려고 하면 관리자에 게 라이선스에 대 한 요청을 제출할 수 있습니다. 요청을 수행할 때는 해당 제품에 대 한 라이선스가 필요한 다른 사용자의 이름을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="850d9-107">When a user tries to make a self-service purchase for a product that you’ve blocked, they can submit a request for a license to you, the admin. When they make a request, they can add the names of other users who also need licenses for the product.</span></span>

> [!NOTE]
> <span data-ttu-id="850d9-108">사용자가 셀프 서비스를 구매 하지 못하도록 차단 하면 Microsoft에서 마케팅 전자 메일이 전송 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="850d9-108">If you block users from making self-service purchases, Microsoft doesn’t send them marketing emails.</span></span> <span data-ttu-id="850d9-109">또한 제품 평가판을 사용 중인 경우에는 구입 하 라는 메시지가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="850d9-109">Also, if they’re using a trial version of a product, they don’t see prompts to buy it.</span></span> <span data-ttu-id="850d9-110">자세한 내용은 [Manage 셀프 서비스 구매 (관리자)](../subscriptions/manage-self-service-purchases-admins.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="850d9-110">To learn more, see [Manage self-service purchases (Admin)](../subscriptions/manage-self-service-purchases-admins.md).</span></span>

<span data-ttu-id="850d9-111">라이선스 요청을 확인 하 고 관리 하기 위해 관리자는 **라이선스** 페이지의 **요청** 탭을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="850d9-111">To see and manage license requests, admin uses the **Requests** tab on the **Licensing** page.</span></span> <span data-ttu-id="850d9-112">이 목록에는 요청 된 제품의 이름, 라이선스를 요청 하는 사용자의 이름, 요청 된 날짜 및 요청의 상태가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="850d9-112">The list shows the name of the product that is requested, name of the person requesting a license, date requested, and status of the request.</span></span> <span data-ttu-id="850d9-113">관리자가 목록을 필터링 하 여 보류 중이거나 완료 된 요청을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="850d9-113">Admins can filter the list to show requests that are pending or completed.</span></span> <span data-ttu-id="850d9-114">30 일간 요청이 보관 됩니다.</span><span class="sxs-lookup"><span data-stu-id="850d9-114">Requests are held for 30 days.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="850d9-115">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="850d9-115">Before you begin</span></span>

<span data-ttu-id="850d9-116">이 문서의 작업을 수행 하려면 전역 관리자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="850d9-116">You must be a Global admin to perform the tasks in this article.</span></span> <span data-ttu-id="850d9-117">자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="850d9-117">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="use-your-own-request-process"></a><span data-ttu-id="850d9-118">사용자의 요청 프로세스 사용</span><span class="sxs-lookup"><span data-stu-id="850d9-118">Use your own request process</span></span>

<span data-ttu-id="850d9-119">조직에서 자체 요청 프로세스를 사용 하는 경우에는이를 대신 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="850d9-119">If your organization has its own request process, you can use it instead.</span></span> <span data-ttu-id="850d9-120">사용자가 라이선스를 요청할 때 표시 되는 메시지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="850d9-120">You create a message that is displayed to users when they request a license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="850d9-121">자체 요청 프로세스를 사용 **하는 경우 요청 탭에** 요청이 표시 되지 않습니다. 메시지를 추가한 이전의 기존 요청은 승인 하거나 거절할 때까지 계속 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="850d9-121">If you use your own request process, no requests are displayed on the **Requests** tab. Existing requests from before you added your message continue to appear until you approve or decline them.</span></span>

1. <span data-ttu-id="850d9-122">관리 센터에서 **청구**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">라이선스</a> 페이지로 이동한 다음 **요청** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="850d9-122">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="850d9-123">**대신 기존 요청 프로세스 사용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="850d9-123">Select **Use your existing request process instead**.</span></span>
3. <span data-ttu-id="850d9-124">오른쪽 창의 **메시지** 상자에 사용자가 라이선스를 요청할 때 볼 수 있는 메시지를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="850d9-124">In the right pane, in the **Message** box, type the message you want users to see when they request a license.</span></span> <span data-ttu-id="850d9-125">조직 정책 또는 기타 설명서에 대 한 링크도 포함 하려면 **설명서 링크 (선택 사항)** 텍스트 상자에 URL을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="850d9-125">If you want to also include a link to your organizations policy or other documentation, enter the URL in the **Link to documentation (optional)** text box.</span></span>
4. <span data-ttu-id="850d9-126">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="850d9-126">Select **Save**.</span></span>

<span data-ttu-id="850d9-127">**요청** 목록으로 돌아가면 **사용자가 라이선스 요청 프로세스를 사용**하 고 있다는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="850d9-127">When you return to the **Requests** list, you see the message **You’re using your own license request process**.</span></span> <span data-ttu-id="850d9-128">사용자에 게 전송 되는 메시지를 변경 하려면 **대신 기존 요청 처리 사용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="850d9-128">To make changes to the message that is sent to users, select **Use your existing request process instead**.</span></span>

## <a name="stop-using-your-own-request-process"></a><span data-ttu-id="850d9-129">사용자의 요청 프로세스 사용 중지</span><span class="sxs-lookup"><span data-stu-id="850d9-129">Stop using your own request process</span></span>

1. <span data-ttu-id="850d9-130">관리 센터에서 **청구**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">라이선스</a> 페이지로 이동한 다음 **요청** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="850d9-130">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="850d9-131">**대신 기존 요청 프로세스 사용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="850d9-131">Select **Use your existing request process instead**.</span></span>
3. <span data-ttu-id="850d9-132">오른쪽 창에서 **내 조직의 요청 프로세스 사용** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="850d9-132">In the right pane, clear the **Use my organization’s request process** check box.</span></span>
4. <span data-ttu-id="850d9-133">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="850d9-133">Select **Save**.</span></span>

## <a name="approve-or-deny-a-license-request"></a><span data-ttu-id="850d9-134">라이선스 요청 승인 또는 거부</span><span class="sxs-lookup"><span data-stu-id="850d9-134">Approve or deny a license request</span></span>

1. <span data-ttu-id="850d9-135">관리 센터에서 **청구**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">라이선스</a> 페이지로 이동한 다음 **요청** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="850d9-135">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="850d9-136">검토할 요청이 포함 된 행을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="850d9-136">Select the row that contains the request you want to review.</span></span> <span data-ttu-id="850d9-137">오른쪽 창에 제품에 대 한 라이선스를 원하는 사용자에 대 한 세부 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="850d9-137">The right pane shows details about which users want licenses to the product.</span></span>
3. <span data-ttu-id="850d9-138">전체 요청을 거부 하려면 **승인 안 함을**선택 하 고 대화 상자에서 **승인 안 함을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="850d9-138">To deny the entire request, select **Don’t approve**, and in the dialog box, select **Don’t approve**.</span></span>
4. <span data-ttu-id="850d9-139">요청에 대 한 일부 사용자는 거부 하 고 나머지는 승인 하려면 제거할 사용자의 이름으로 X를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="850d9-139">To deny some users for the request, but approve others, select the X by the name of the users that you want to remove.</span></span> <span data-ttu-id="850d9-140">해당 이름은 **다음 사용자에 게 할당 안 함**아래에서 이동 됩니다.</span><span class="sxs-lookup"><span data-stu-id="850d9-140">Their names are moved under **Do not assign to these users**.</span></span>
5. <span data-ttu-id="850d9-141">제품이 둘 이상 있는 경우 **제품 선택**에서 라이선스를 할당 하는 데 사용할 항목을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="850d9-141">If you have more than one product, under **Select a product**, select the one that you want to use to assign licenses for.</span></span>
6. <span data-ttu-id="850d9-142">사용자에 게 특정 앱 및 서비스에 대 한 액세스를 거부 하려면 **앱 및 서비스 켜기/끄기를**확장 한 다음 제외 하려는 항목의 확인란을 선택 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="850d9-142">To deny users access to certain app and services, expand **Turn apps and services on or off**, then clear the check boxes for the ones you want to exclude.</span></span>
7. <span data-ttu-id="850d9-143">창의 아래쪽에 있는 텍스트 상자에 선택적 메시지를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="850d9-143">At the bottom of the pane, type an optional message in the text box.</span></span>
8. <span data-ttu-id="850d9-144">작업이 완료 되 면 **승인을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="850d9-144">When you’re finished, select **Approve**.</span></span> <span data-ttu-id="850d9-145">오른쪽 창에는 요청에 대 한 세부 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="850d9-145">The right pane shows the details of the request.</span></span>
9. <span data-ttu-id="850d9-146">오른쪽 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="850d9-146">Close the right pane.</span></span>
    <span data-ttu-id="850d9-147">사용자에 게 요청이 승인 또는 거부 되었음을 알리는 전자 메일이 수신 됩니다.</span><span class="sxs-lookup"><span data-stu-id="850d9-147">Users receive an email that says their request was approved or denied.</span></span>

## <a name="related-content"></a><span data-ttu-id="850d9-148">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="850d9-148">Related content</span></span>

<span data-ttu-id="850d9-149">[사용자에 게 라이선스 할당](../../admin/manage/assign-licenses-to-users.md) (문서) </span><span class="sxs-lookup"><span data-stu-id="850d9-149">[Assign licenses to users](../../admin/manage/assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="850d9-150">[사용자를 다른 구독으로 이동](../subscriptions/move-users-different-subscription.md) (문서) </span><span class="sxs-lookup"><span data-stu-id="850d9-150">[Move users to a different subscription](../subscriptions/move-users-different-subscription.md) (article)</span></span>\
<span data-ttu-id="850d9-151">[구독 라이선스 구입 또는 제거](buy-licenses.md) (문서)</span><span class="sxs-lookup"><span data-stu-id="850d9-151">[Buy or remove subscription licenses](buy-licenses.md) (article)</span></span>