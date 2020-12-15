---
title: 청구 프로필 이해
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsBillingProfiles
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- Commerce
search.appverid:
- MET150
description: 청구 프로필에서 송장을 지원하는 방법을 알아보세요.
ms.openlocfilehash: 708096b624caa9c23a40df4842ccfce856db048d
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/14/2020
ms.locfileid: "49667780"
---
# <a name="understand-billing-profiles"></a><span data-ttu-id="8cedb-103">청구 프로필 이해</span><span class="sxs-lookup"><span data-stu-id="8cedb-103">Understand billing profiles</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="8cedb-104">관리 센터가 변경되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cedb-104">The admin center is changing.</span></span> <span data-ttu-id="8cedb-105">사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8cedb-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="8cedb-106">Microsoft에서 제품 및 서비스를 구입하는 상용 고객의 경우 청구 프로필을 통해 송장에 포함된 항목과 송장 결제 방법을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cedb-106">For commercial customers who buy products and services from Microsoft, billing profiles let you customize what items are included on your invoice, and how you pay your invoices.</span></span>

<span data-ttu-id="8cedb-107">청구 프로필에는 다음 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cedb-107">Billing profiles include the following information:</span></span>

- <span data-ttu-id="8cedb-108">**청구 계정** &ndash; 프로필과 관련된 청구 계정의 이름</span><span class="sxs-lookup"><span data-stu-id="8cedb-108">**Billing account** &ndash; Name of the billing account the profile is related to</span></span>
- <span data-ttu-id="8cedb-109">**결제 방법** &ndash; 신용 카드 또는 직불 카드, 은행 계좌, 수표 또는 전신 송금</span><span class="sxs-lookup"><span data-stu-id="8cedb-109">**Payment methods** &ndash; Credit or debit cards, bank accounts, check, or wire transfer</span></span>
- <span data-ttu-id="8cedb-110">**연락처 정보** &ndash; 청구 주소 및 연락처 이름</span><span class="sxs-lookup"><span data-stu-id="8cedb-110">**Contact information** &ndash; Billing address and a contact name</span></span>
- <span data-ttu-id="8cedb-111">**송장 설정** &ndash; 청구 계정의 국가, 선택적 PO 번호 및 전자 메일 첨부 파일로 송장을 받는 옵션에 기반한 통화</span><span class="sxs-lookup"><span data-stu-id="8cedb-111">**Invoice settings** &ndash; Currency based on the country of the billing account, an optional PO number, and the option to receive invoices as email attachments</span></span>
- <span data-ttu-id="8cedb-112">**사용 권한** &ndash; 청구 프로필을 변경하거나, 청구서를 결제하거나, 청구 프로필에서 결제 방법을 사용하여 구매할 수 있는 권한</span><span class="sxs-lookup"><span data-stu-id="8cedb-112">**Permissions** &ndash; Permissions that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchases</span></span>

<span data-ttu-id="8cedb-113">청구 프로필을 사용하여 구매를 제어하고 송장을 사용자 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8cedb-113">Use billing profiles to control your purchases and customize your invoice.</span></span> <span data-ttu-id="8cedb-114">청구 프로필을 사용하여 구입한 제품에 대해 월별 송장이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cedb-114">A monthly invoice is generated for the products bought with the billing profile.</span></span> <span data-ttu-id="8cedb-115">구매 주문 번호 및 전자 메일 송장 기본 설정 업데이트와 같은 송장을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cedb-115">You can customize the invoice such as update the purchase order number and email invoice preference.</span></span>

<span data-ttu-id="8cedb-116">첫 구매 중에 청구 계정에 대한 청구 프로필이 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="8cedb-116">A billing profile is automatically created for your billing account during your first purchase.</span></span> <span data-ttu-id="8cedb-117">청구 프로필 페이지에서 청구 프로필을 만들어 더 많은 송장을 설정할 수 있습니다. <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank"></a></span><span class="sxs-lookup"><span data-stu-id="8cedb-117">You can create billing profiles on the <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Billing profiles</a> page to set up more invoices.</span></span> <span data-ttu-id="8cedb-118">예를 들어 조직의 각 부서에 대해 구매할 때 다른 청구 프로필을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cedb-118">For example, you can use different billing profiles when you make purchases for each department in your organization.</span></span> <span data-ttu-id="8cedb-119">다음 청구 날짜에 각 청구 프로필에 대한 송장을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cedb-119">On your next billing date, you'll receive an invoice for each billing profile.</span></span>

## <a name="billing-profile-roles"></a><span data-ttu-id="8cedb-120">청구 프로필 역할</span><span class="sxs-lookup"><span data-stu-id="8cedb-120">Billing profile roles</span></span>

<span data-ttu-id="8cedb-121">청구 프로필의 역할에는 구매를 제어하고 송장을 보고 관리할 수 있는 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cedb-121">Roles on billing profiles have permissions to control purchases, and view and manage invoices.</span></span> <span data-ttu-id="8cedb-122">조직의 조달 팀 구성원과 같은 송장을 추적, 구성 및 결제하는 사용자에게 이러한 역할을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="8cedb-122">Assign these roles to users who track, organize, and pay invoices, like members of the procurement team in your organization.</span></span>

| <span data-ttu-id="8cedb-123">역할</span><span class="sxs-lookup"><span data-stu-id="8cedb-123">Role</span></span>                          | <span data-ttu-id="8cedb-124">설명</span><span class="sxs-lookup"><span data-stu-id="8cedb-124">Description</span></span>                                                                       |
|-----------------------------  |---------------------------------------------------------------------------------  |
| <span data-ttu-id="8cedb-125">청구 프로필 소유자</span><span class="sxs-lookup"><span data-stu-id="8cedb-125">Billing profile owner</span></span>         | <span data-ttu-id="8cedb-126">청구 프로필에 대한 모든 관리</span><span class="sxs-lookup"><span data-stu-id="8cedb-126">Manage everything for a billing profile</span></span>                                           |
| <span data-ttu-id="8cedb-127">청구 프로필 참가자</span><span class="sxs-lookup"><span data-stu-id="8cedb-127">Billing profile contributor</span></span>   | <span data-ttu-id="8cedb-128">청구 프로필의 사용 권한을 제외한 모든 관리</span><span class="sxs-lookup"><span data-stu-id="8cedb-128">Manage everything except permissions in a billing profile</span></span>                         |
| <span data-ttu-id="8cedb-129">청구 프로필 판독기</span><span class="sxs-lookup"><span data-stu-id="8cedb-129">Billing profile reader</span></span>        | <span data-ttu-id="8cedb-130">청구 프로필의 모든 내용을 읽기 전용으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cedb-130">Read-only view of everything in a billing profile</span></span>                                 |
| <span data-ttu-id="8cedb-131">송장 관리자</span><span class="sxs-lookup"><span data-stu-id="8cedb-131">Invoice manager</span></span>               | <span data-ttu-id="8cedb-132">청구서 보기 및 결제, 청구 프로필의 모든 내용을 읽기 전용 보기</span><span class="sxs-lookup"><span data-stu-id="8cedb-132">View and pay bills, and has a read-only view of everything in a billing profile</span></span>   |

## <a name="view-billing-profiles"></a><span data-ttu-id="8cedb-133">청구 프로필 보기</span><span class="sxs-lookup"><span data-stu-id="8cedb-133">View billing profiles</span></span>

1. <span data-ttu-id="8cedb-134">관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">청구서 및 결제</a> 페이지로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="8cedb-134">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>

2. <span data-ttu-id="8cedb-135">청구 **프로필을 선택한** 다음 목록에서 청구 프로필을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8cedb-135">Choose **Billing profiles**, and then choose a billing profile from the list.</span></span>

    - <span data-ttu-id="8cedb-136">개요 **탭에서** 청구 프로필 세부 정보를 편집하고 전자 메일로 송장 보내기를 설정하거나 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cedb-136">On the **Overview** tab, you can edit billing profile details, and turn on or off sending an invoice by email.</span></span>

    - <span data-ttu-id="8cedb-137">사용 권한 **탭에서** 사용자에게 송장 결제 역할을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cedb-137">On the **Permissions** tab, you can assign roles to users to pay invoices.</span></span>

    - <span data-ttu-id="8cedb-138">Azure 신용 **잔액** 탭에서 Azure 고객은 해당 청구 프로필에서 사용하는 Azure 크레딧에 대한 거래 잔액 기록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cedb-138">On the **Azure credit balance** tab, Azure customers can see transaction balance history for the Azure credits used by that billing profile.</span></span>

    - <span data-ttu-id="8cedb-139">Azure **크레딧** 탭에서 Azure 고객은 해당 청구 프로필과 연결된 Azure 크레딧 목록과 만료 날짜를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cedb-139">On the **Azure credits** tab, Azure customers can see a list of Azure credits associated with that billing profile, and their expiration dates.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8cedb-140">Azure 크레딧이 없는 경우 **Azure** 크레딧 잔액 또는 Azure 크레딧 **탭이 표시되지** 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8cedb-140">If you don't have any Azure credits, you won't see the **Azure credit balance** or **Azure credits** tabs.</span></span>

## <a name="need-help-contact-support"></a><span data-ttu-id="8cedb-141">도움이 필요하신가요?</span><span class="sxs-lookup"><span data-stu-id="8cedb-141">Need help?</span></span> <span data-ttu-id="8cedb-142">고객 지원에 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="8cedb-142">Contact support.</span></span>

<span data-ttu-id="8cedb-143">질문이 있는 경우 또는 Azure 요금에 대한 도움이 필요한 경우 Azure 지원으로 <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">지원 요청을 만드하세요.</a></span><span class="sxs-lookup"><span data-stu-id="8cedb-143">If you have questions or need help with your Azure charges, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">create a support request with Azure support</a>.</span></span>

<span data-ttu-id="8cedb-144">Microsoft 365 관리 센터에서 청구 프로필에 대한 질문이나 도움이 필요한 경우 비즈니스 제품에 대한 지원에 [문의하세요.](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)</span><span class="sxs-lookup"><span data-stu-id="8cedb-144">If you have questions or need help with your billing profile in Microsoft 365 admin center, [contact support for business products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>
