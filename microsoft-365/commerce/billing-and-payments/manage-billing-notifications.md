---
title: 청구 알림 및 송장 첨부 파일 관리
f1.keywords:
- CSH
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
ms.custom:
- okr_SMB
- AdminSurgePortfolio
- commerce
search.appverid:
- MET150
description: 청구 알림 전자 메일 및 송장 첨부 파일을 받는 사람 관리 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: f0811c5d027d042b5114c9e05c698dab1e08763b
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "50515230"
---
# <a name="manage-billing-notifications-and-invoice-attachments"></a><span data-ttu-id="5bcfa-103">청구 알림 및 송장 첨부 파일 관리</span><span class="sxs-lookup"><span data-stu-id="5bcfa-103">Manage billing notifications and invoice attachments</span></span>

<span data-ttu-id="5bcfa-104">청구 **알림 페이지에서는** 조직의 청구 알림 전자 메일을 받는 사람도 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-104">The **Billing notifications** page lets you manage who receives billing notification emails for your organization.</span></span> <span data-ttu-id="5bcfa-105">이 페이지에서는 조직의 송장을 전자 메일 첨부 파일로 받는 [옵션도 제공합니다.](#receive-your-organizations-invoices-as-email-attachments)</span><span class="sxs-lookup"><span data-stu-id="5bcfa-105">The page also provides the option to [receive your organization's invoices as email attachments](#receive-your-organizations-invoices-as-email-attachments).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="5bcfa-106">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="5bcfa-106">Before you begin</span></span>

<span data-ttu-id="5bcfa-107">이 문서에 설명된 단계를 수행하려면 전역 관리자 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-107">You must be a Global admin to do the steps described in this article.</span></span> <span data-ttu-id="5bcfa-108">대금 청구 관리자는 아래 섹션에 설명된 일부 변경을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-108">Billing admins can make some of these changes, as noted in the sections below.</span></span> <span data-ttu-id="5bcfa-109">자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-109">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="change-the-language-you-receive-email-in"></a><span data-ttu-id="5bcfa-110">전자 메일을 받는 언어 변경</span><span class="sxs-lookup"><span data-stu-id="5bcfa-110">Change the language you receive email in</span></span>

> [!NOTE]
> <span data-ttu-id="5bcfa-111">청구 관리자는 이 섹션의 단계를 수행 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-111">Billing admins can also do the steps in this section.</span></span>

<span data-ttu-id="5bcfa-112">청구 알림 전자 메일은 조직의 기본 설정 언어로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-112">Billing notification emails are sent in your organization’s preferred language.</span></span> <span data-ttu-id="5bcfa-113">기본 언어를 변경하기 위해 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-113">To change the preferred language, use the following steps.</span></span>

1. <span data-ttu-id="5bcfa-114">Microsoft 365 관리 센터에서 청구 청구 알림  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">페이지로</a> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-114">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="5bcfa-115">청구 **알림 설정 섹션에서** 알림 설정 **편집을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5bcfa-115">In the **Billing notification settings** section, select **Edit notification settings**.</span></span>
3. <span data-ttu-id="5bcfa-116">청구 **알림 설정** 창의 기본  설정에서 사용할 언어를 선택한 다음 저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5bcfa-116">In the **Billing notification settings** pane, under **Preferred language** select the language you want to use, then select **Save**.</span></span>

## <a name="change-who-receives-billing-notifications"></a><span data-ttu-id="5bcfa-117">청구 알림을 받는 사용자 변경</span><span class="sxs-lookup"><span data-stu-id="5bcfa-117">Change who receives billing notifications</span></span>

<span data-ttu-id="5bcfa-118">조직의 청구 알림은 모든 전역 및 대금 청구 관리자의 기본 및 대체 전자 메일 주소로 전송됩니다. 전역 또는 대금 청구 관리자 역할이 있는 사용자를 변경하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-118">Your organization's billing notifications are sent to the primary and alternate email address of every Global and Billing admin. To change which users have the Global or Billing admin role, use the following steps.</span></span>

### <a name="assign-admin-roles-by-using-the-billing-notifications-page"></a><span data-ttu-id="5bcfa-119">청구 알림 페이지를 사용하여 관리자 역할 할당</span><span class="sxs-lookup"><span data-stu-id="5bcfa-119">Assign admin roles by using the Billing notifications page</span></span>

1. <span data-ttu-id="5bcfa-120">관리 센터에서 **청구** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">대금 청구 알림</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-120">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="5bcfa-121">청구 알림을 받는 관리자 **섹션의** 설명 텍스트에서 청구  관리자 또는 전역 관리자 링크를 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="5bcfa-121">In the **Admins receiving billing notifications** section, select the **Billing administrator** or **Global administrator** link in the description text.</span></span>
3. <span data-ttu-id="5bcfa-122">오른쪽 창의 할당된 관리자 **탭에서** 추가를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5bcfa-122">In the right pane, on the **Assigned admins** tab, select **Add**.</span></span>
4. <span data-ttu-id="5bcfa-123">관리자 **추가 창에서** 사용자의 표시 이름 또는 사용자 이름을 입력한 다음 제안 목록에서 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-123">In the **Add admins** pane, type the user’s display name or username, and then select the user from the list of suggestions.</span></span>
5. <span data-ttu-id="5bcfa-124">완료될 때까지 여러 사용자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-124">Add multiple users until you’re done.</span></span>
6. <span data-ttu-id="5bcfa-125">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-125">Select **Save**.</span></span> <span data-ttu-id="5bcfa-126">사용자가 할당된 관리자 목록에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-126">The user is added to the list of assigned admins.</span></span>

### <a name="remove-admin-roles-by-using-the-billing-notifications-page"></a><span data-ttu-id="5bcfa-127">청구 알림 페이지를 사용하여 관리자 역할 제거</span><span class="sxs-lookup"><span data-stu-id="5bcfa-127">Remove admin roles by using the Billing notifications page</span></span>

1. <span data-ttu-id="5bcfa-128">관리 센터에서 **청구** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">대금 청구 알림</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-128">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="5bcfa-129">청구 알림을 받는 관리자 **섹션의** 설명 텍스트에서 청구  관리자 또는 전역 관리자 링크를 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="5bcfa-129">In the **Admins receiving billing notifications** section, select the **Billing administrator** or **Global administrator** link in the description text.</span></span>
3. <span data-ttu-id="5bcfa-130">오른쪽 창의 할당된 관리자 **탭에서** 역할에서 제거할 사용자를 선택하고 제거를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5bcfa-130">In the right pane, on the **Assigned admins** tab, select the users to remove from the role, and then select **Remove**.</span></span>
4. <span data-ttu-id="5bcfa-131">확인 상자에서 제거를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5bcfa-131">In the confirmation box, select **Remove**.</span></span> <span data-ttu-id="5bcfa-132">사용자가 할당된 관리자 목록에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-132">The user is removed from the list of assigned admins.</span></span>

## <a name="change-the-email-addresses-for-admins"></a><span data-ttu-id="5bcfa-133">관리자의 전자 메일 주소 변경</span><span class="sxs-lookup"><span data-stu-id="5bcfa-133">Change the email addresses for admins</span></span>

<span data-ttu-id="5bcfa-134">조직에 있는 다른 관리자의 기본 및 대체 전자 메일 주소를 변경하려면 다음 단계를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-134">To change the primary and alternate email address of other admins in your organization, use the following steps.</span></span>

> [!NOTE]
> <span data-ttu-id="5bcfa-135">대금 청구 관리자는 자신의 기본 및 대체 전자 메일 주소를 변경할 수 있지만 다른 관리자의 경우 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-135">Billing admins can change their own primary and alternate email addresses, but not for other admins.</span></span>

1. <span data-ttu-id="5bcfa-136">관리 센터에서 **청구** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">대금 청구 알림</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-136">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="5bcfa-137">청구 알림을 받는 관리자 **섹션에서** 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-137">In the **Admins receiving billing notifications** section, select a name.</span></span>
3. <span data-ttu-id="5bcfa-138">오른쪽 창에서 기본 및 대체 전자 메일 주소를 필요한 경우 추가하거나 업데이트한 다음 저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5bcfa-138">In the right pane, add or update the primary and alternate email address as needed, then select **Save**.</span></span>

## <a name="change-your-organizations-contact-email"></a><span data-ttu-id="5bcfa-139">조직의 연락처 전자 메일 변경</span><span class="sxs-lookup"><span data-stu-id="5bcfa-139">Change your organization's contact email</span></span>

<span data-ttu-id="5bcfa-140">전역 관리자 및 대금 청구 관리자 외에 조직의 연락처 전자 메일 주소로 청구 알림을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-140">In addition to your Global and Billing admins, we send billing notifications to your organization's contact email address.</span></span> <span data-ttu-id="5bcfa-141">전자 메일 주소를 변경하기 위해 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-141">To change the email address, use the following steps.</span></span>

1. <span data-ttu-id="5bcfa-142">관리 센터에서 **청구** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">대금 청구 알림</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-142">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="5bcfa-143">청구 알림을 받는 조직 **연락처에서** 조직 연락처를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-143">Under **Organization contact receiving billing notifications**, select the organization contact.</span></span>
3. <span data-ttu-id="5bcfa-144">오른쪽 창에 사용할 전자 메일 주소를 입력한 다음 저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5bcfa-144">In the right pane, type the email address that you want to use, then select **Save**.</span></span>

## <a name="receive-your-organizations-invoices-as-email-attachments"></a><span data-ttu-id="5bcfa-145">전자 메일 첨부 파일로 조직의 송장 받기</span><span class="sxs-lookup"><span data-stu-id="5bcfa-145">Receive your organization's invoices as email attachments</span></span>

> [!NOTE]
> <span data-ttu-id="5bcfa-146">청구 관리자는 이 섹션의 단계를 수행 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-146">Billing admins can also do the steps in this section.</span></span>

<span data-ttu-id="5bcfa-147">새 송장이 준비되면 조직의 송장 복사본을 PDF 파일로 송장 알림 전자 메일에 첨부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-147">You can have a copy of your organization's invoice attached as a PDF file to invoice notification emails when a new invoice is ready.</span></span> <span data-ttu-id="5bcfa-148">다음 단계에 따라 송장을 첨부 파일로 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-148">Use the following steps to receive invoices as attachments.</span></span>

1. <span data-ttu-id="5bcfa-149">관리 센터에서 **청구** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">대금 청구 알림</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-149">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="5bcfa-150">청구 **알림 설정에서** 알림 **설정 편집을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5bcfa-150">Under **Billing notification settings**, select **Edit notification settings**.</span></span>
3. <span data-ttu-id="5bcfa-151">청구 **알림 설정 창의** 송장 전자 메일에 **PDF** 첨부에서 확인란을 선택한 다음 저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5bcfa-151">In the **Billing notification settings** pane, under **Attach a PDF to your invoice emails**, check the checkbox, then select **Save**.</span></span>

<span data-ttu-id="5bcfa-152">To stop receiving the invoice attachment at any time, follow the steps above and clear the **Attach a PDF to your invoice emails** in step 3.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-152">To stop receiving the invoice attachment at any time, follow the steps above and clear the **Attach a PDF to your invoice  emails** checkbox in step 3.</span></span>

## <a name="what-if-i-have-a-billing-profile"></a><span data-ttu-id="5bcfa-153">청구 프로필이 있는 경우 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="5bcfa-153">What if I have a billing profile?</span></span>

<span data-ttu-id="5bcfa-154">청구 프로필이 있는 경우 이 문서에 설명된 일부 단계는 일부 구독과 약간 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-154">If you have a billing profile, some of the steps described in this article might be slightly different for some of your subscriptions.</span></span> <span data-ttu-id="5bcfa-155">이 섹션에서는 이러한 차이점에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-155">This section describes those differences.</span></span> [<span data-ttu-id="5bcfa-156">청구 프로필이 있는 경우 어떻게 알 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="5bcfa-156">How do I know if I have a billing profile?</span></span>](manage-billing-profiles.md)

### <a name="who-receives-billing-notifications"></a><span data-ttu-id="5bcfa-157">청구 알림을 받는 사람</span><span class="sxs-lookup"><span data-stu-id="5bcfa-157">Who receives Billing notifications?</span></span>

<span data-ttu-id="5bcfa-158">청구 알림 전자 메일은 다음 역할 중 하나에 할당된 사용자의 기본 및 대체 전자 메일 주소로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-158">Billing notification emails are sent to the primary and alternate email addresses for users who are assigned one of the following roles:</span></span>

- <span data-ttu-id="5bcfa-159">청구 프로필 소유자</span><span class="sxs-lookup"><span data-stu-id="5bcfa-159">Billing profile owner</span></span>
- <span data-ttu-id="5bcfa-160">청구 프로필 참가자</span><span class="sxs-lookup"><span data-stu-id="5bcfa-160">Billing profile contributor</span></span>
- <span data-ttu-id="5bcfa-161">송장 관리자</span><span class="sxs-lookup"><span data-stu-id="5bcfa-161">Invoice manager</span></span>

<span data-ttu-id="5bcfa-162">청구 프로필 역할 및 해당 역할을 관리하는 방법에 대한 자세한 내용은 Azure에서 Microsoft 고객 계약 관리 역할 이해를 [참조하세요.](https://docs.microsoft.com/azure/cost-management-billing/manage/understand-mca-roles)</span><span class="sxs-lookup"><span data-stu-id="5bcfa-162">To learn more about billing profile roles and how to manage them, see [Understand Microsoft Customer Agreement administrative roles in Azure](https://docs.microsoft.com/azure/cost-management-billing/manage/understand-mca-roles).</span></span>

<span data-ttu-id="5bcfa-163">조직의 청구 알림을 받는 사용자를 변경하기 위해 다음 단계에 따라 사용자에게 할당된 역할을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-163">To change who receives your organization’s billing notifications, use the following steps to change the roles assigned to users.</span></span>

1. <span data-ttu-id="5bcfa-164">관리 센터에서 청구 청구서 &   >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">페이지로</a> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-164">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>
2. <span data-ttu-id="5bcfa-165">청구 **프로필 탭에서** 청구 프로필을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-165">On the **Billing profile** tab, select a billing profile.</span></span>
3. <span data-ttu-id="5bcfa-166">청구 프로필 **역할 섹션에서** 청구 프로필 **소유자,** 청구 프로필 참가자 또는 송장 관리자에 대한 역할을 할당하거나 **제거합니다.**</span><span class="sxs-lookup"><span data-stu-id="5bcfa-166">In the **Billing profile roles** section, assign or remove roles for **Billing profile owner**, **Billing profile contributor**, or **Invoice manager**.</span></span>

### <a name="receive-invoices-as-email-attachments"></a><span data-ttu-id="5bcfa-167">전자 메일 첨부 파일로 송장 받기</span><span class="sxs-lookup"><span data-stu-id="5bcfa-167">Receive invoices as email attachments</span></span>

<span data-ttu-id="5bcfa-168">송장을 송장 알림의 첨부 파일로 받으세요. 다음 단계에 따라 특정 청구 프로필에 대해 이 설정을 켜세요.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-168">To receive your invoices as attachments to your invoice notifications, use the following steps to turn on this setting for a specific billing profile.</span></span>

1. <span data-ttu-id="5bcfa-169">관리 센터에서 청구 청구서 &   >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">페이지로</a> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-169">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>
2. <span data-ttu-id="5bcfa-170">청구 프로필 **탭을** 선택한 다음 목록에서 청구 프로필을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-170">Select the **Billing profiles** tab, then select a billing profile from the list.</span></span>
3. <span data-ttu-id="5bcfa-171">청구 프로필 세부 정보 페이지의 전자 메일 첨부 파일에서 송장 확인에서 토글을 켜기 로 **전환합니다.**</span><span class="sxs-lookup"><span data-stu-id="5bcfa-171">On the billing profile details page, under **Get invoices in email attachments**, switch the toggle to **On**.</span></span>

## <a name="related-content"></a><span data-ttu-id="5bcfa-172">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="5bcfa-172">Related content</span></span>

<span data-ttu-id="5bcfa-173">[청구서 또는 송장](view-your-bill-or-invoice.md) 보기(문서)</span><span class="sxs-lookup"><span data-stu-id="5bcfa-173">[View your bill or invoice](view-your-bill-or-invoice.md) (article)</span></span>\
<span data-ttu-id="5bcfa-174">[비즈니스용 Microsoft 365의](understand-your-invoice2.md) 청구서 또는 송장 이해(문서)</span><span class="sxs-lookup"><span data-stu-id="5bcfa-174">[Understand your bill or invoice for Microsoft 365 for business](understand-your-invoice2.md) (article)</span></span>\
<span data-ttu-id="5bcfa-175">[사용자 추가 및](../../admin/add-users/add-users.md) 동시에 라이선스 할당(문서)</span><span class="sxs-lookup"><span data-stu-id="5bcfa-175">[Add users and assign licenses at the same time](../../admin/add-users/add-users.md) (article)</span></span>