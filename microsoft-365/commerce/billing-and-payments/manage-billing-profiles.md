---
title: 청구 프로필 관리
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsBillingProfiles
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: 청구 프로필에서 송장을 지 원하는 방법을 알아봅니다.
keywords: 청구 프로필, 송장, 요금, 관리 비용
ms.openlocfilehash: 2979909e3b916cc4bc8704f32a821b13fa6090e0
ms.sourcegitcommit: 956dd3f87adb4e6173517550a662c3bacc2d2d79
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44741705"
---
# <a name="manage-billing-profiles"></a><span data-ttu-id="b29a4-104">청구 프로필 관리</span><span class="sxs-lookup"><span data-stu-id="b29a4-104">Manage billing profiles</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="b29a4-105">관리 센터가 변경되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b29a4-105">The admin center is changing.</span></span> <span data-ttu-id="b29a4-106">사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b29a4-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="b29a4-107">Microsoft의 제품 및 서비스를 구입한 상용 고객의 경우 대금 청구 프로필을 사용 하 여 송장에 포함 되는 항목을 사용자 지정 하 고 청구서 비용을 지불 하는 방법을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b29a4-107">For commercial customers who buy products and services from Microsoft, billing profiles let you customize what items are included on your invoice, and how you pay your invoices.</span></span>

<span data-ttu-id="b29a4-108">대금 청구 프로필에는 다음 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b29a4-108">Billing profiles include the following information:</span></span>

- <span data-ttu-id="b29a4-109">**청구 계정** &ndash; 프로필과 관련 된 청구 계정의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b29a4-109">**Billing account** &ndash; Name of the billing account the profile is related to</span></span>
- <span data-ttu-id="b29a4-110">**결제 방법** &ndash; 신용 카드, 은행 계좌, 확인 또는 전선 전송</span><span class="sxs-lookup"><span data-stu-id="b29a4-110">**Payment methods** &ndash; Credit or debit cards, bank accounts, check, or wire transfer</span></span>
- <span data-ttu-id="b29a4-111">**연락처 정보** &ndash; 청구지 주소 및 연락처 이름</span><span class="sxs-lookup"><span data-stu-id="b29a4-111">**Contact information** &ndash; Billing address and a contact name</span></span>
- <span data-ttu-id="b29a4-112">**송장 설정** &ndash; 청구 계정의 국가, 선택적 PO 번호 및 청구서를 전자 메일 첨부 파일로 수신 하는 옵션에 따른 통화</span><span class="sxs-lookup"><span data-stu-id="b29a4-112">**Invoice settings** &ndash; Currency based on the country of the billing account, an optional PO number, and the option to receive invoices as email attachments</span></span>
- <span data-ttu-id="b29a4-113">**사용 권한** &ndash; 청구 프로필을 변경 하거나, 청구서를 지불 하거나, 대금 청구 프로필에서 결제 방법을 사용 하 여 구매를 수행할 수 있는 권한</span><span class="sxs-lookup"><span data-stu-id="b29a4-113">**Permissions** &ndash; Permissions that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchases</span></span>

<span data-ttu-id="b29a4-114">청구 프로필을 사용 하 여 구매를 제어 하 고 송장을 사용자 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b29a4-114">Use billing profiles to control your purchases and customize your invoice.</span></span> <span data-ttu-id="b29a4-115">대금 청구 프로필과 함께 구매한 제품에 대해 월별 송장이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b29a4-115">A monthly invoice is generated for the products bought with the billing profile.</span></span> <span data-ttu-id="b29a4-116">구매 주문 번호 및 전자 메일 송장 기본 설정 업데이트와 같은 송장을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b29a4-116">You can customize the invoice such as update the purchase order number and email invoice preference.</span></span>

<span data-ttu-id="b29a4-117">최초 구매 중에 청구 계정에 대 한 대금 청구 프로필이 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="b29a4-117">A billing profile is automatically created for your billing account during your first purchase.</span></span> <span data-ttu-id="b29a4-118"><a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">청구 프로필</a> 페이지에서 청구 프로필을 만들어 추가 송장을 더 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b29a4-118">You can create billing profiles on the <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Billing profiles</a> page to set up more invoices.</span></span> <span data-ttu-id="b29a4-119">예를 들어 조직의 각 부서에 대해 구매를 수행 하는 경우 다른 대금 청구 프로필을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b29a4-119">For example, you can use different billing profiles when you make purchases for each department in your organization.</span></span> <span data-ttu-id="b29a4-120">다음 청구 날짜에는 각 대금 청구 프로필에 대 한 송장을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b29a4-120">On your next billing date, you'll receive an invoice for each billing profile.</span></span>

## <a name="billing-profile-roles"></a><span data-ttu-id="b29a4-121">청구 프로필 역할</span><span class="sxs-lookup"><span data-stu-id="b29a4-121">Billing profile roles</span></span>

<span data-ttu-id="b29a4-122">청구 프로필에 대 한 역할에는 구매를 제어 하 고 송장을 보고 관리할 수 있는 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b29a4-122">Roles on billing profiles have permissions to control purchases, and view and manage invoices.</span></span> <span data-ttu-id="b29a4-123">조직의 조달 팀 구성원과 같이 송장을 추적, 구성 및 지불 하는 사용자에 게 이러한 역할을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b29a4-123">Assign these roles to users who track, organize, and pay invoices, like members of the procurement team in your organization.</span></span>

| <span data-ttu-id="b29a4-124">역할</span><span class="sxs-lookup"><span data-stu-id="b29a4-124">Role</span></span>                          | <span data-ttu-id="b29a4-125">설명</span><span class="sxs-lookup"><span data-stu-id="b29a4-125">Description</span></span>                                                                       |
|-----------------------------  |---------------------------------------------------------------------------------  |
| <span data-ttu-id="b29a4-126">청구 프로필 소유자</span><span class="sxs-lookup"><span data-stu-id="b29a4-126">Billing profile owner</span></span>         | <span data-ttu-id="b29a4-127">청구 프로필에 대 한 모든 항목 관리</span><span class="sxs-lookup"><span data-stu-id="b29a4-127">Manage everything for a billing profile</span></span>                                           |
| <span data-ttu-id="b29a4-128">대금 청구 프로필 참가자</span><span class="sxs-lookup"><span data-stu-id="b29a4-128">Billing profile contributor</span></span>   | <span data-ttu-id="b29a4-129">청구 프로필의 사용 권한을 제외한 모든 항목 관리</span><span class="sxs-lookup"><span data-stu-id="b29a4-129">Manage everything except permissions in a billing profile</span></span>                         |
| <span data-ttu-id="b29a4-130">청구 프로필 독자</span><span class="sxs-lookup"><span data-stu-id="b29a4-130">Billing profile reader</span></span>        | <span data-ttu-id="b29a4-131">대금 청구 프로필의 모든 항목에 대 한 읽기 전용 보기</span><span class="sxs-lookup"><span data-stu-id="b29a4-131">Read-only view of everything in a billing profile</span></span>                                 |
| <span data-ttu-id="b29a4-132">송장 관리자</span><span class="sxs-lookup"><span data-stu-id="b29a4-132">Invoice manager</span></span>               | <span data-ttu-id="b29a4-133">청구 프로필의 모든 항목에 대 한 읽기 전용 보기 및 청구서 보기 및 지불</span><span class="sxs-lookup"><span data-stu-id="b29a4-133">View and pay bills, and has a read-only view of everything in a billing profile</span></span>   |

## <a name="view-billing-profiles"></a><span data-ttu-id="b29a4-134">청구 프로필 보기</span><span class="sxs-lookup"><span data-stu-id="b29a4-134">View billing profiles</span></span>

1. <span data-ttu-id="b29a4-135">관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">청구서 및 결제</a> 페이지로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="b29a4-135">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>

2. <span data-ttu-id="b29a4-136">**대금 청구**프로필을 선택한 다음 목록에서 대금 청구 프로필을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b29a4-136">Choose **Billing profiles**, and then choose a billing profile from the list.</span></span>

    - <span data-ttu-id="b29a4-137">**개요** 탭에서 청구 프로필 세부 정보를 편집 하 고 전자 메일로 송장을 보내지 않거나 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b29a4-137">On the **Overview** tab, you can edit billing profile details, and turn on or off sending an invoice by email.</span></span>

    - <span data-ttu-id="b29a4-138">**사용 권한** 탭에서 송장을 지불 하기 위해 사용자에 게 역할을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b29a4-138">On the **Permissions** tab, you can assign roles to users to pay invoices.</span></span>

    - <span data-ttu-id="b29a4-139">Azure **구매 잔액** 탭에서 azure 고객은 해당 청구 프로필에 사용 되는 azure 제작진에 대 한 트랜잭션 균형 기록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b29a4-139">On the **Azure credit balance** tab, Azure customers can see transaction balance history for the Azure credits used by that billing profile.</span></span>

    - <span data-ttu-id="b29a4-140">**Azure 사용** 가능 항목에서 azure 고객은 해당 청구 프로필에 연결 된 azure 제작진 목록과 만료 날짜를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b29a4-140">On the **Azure credits** tab, Azure customers can see a list of Azure credits associated with that billing profile, and their expiration dates.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b29a4-141">Azure 크레딧이 없는 경우 **azure 크레딧 잔액** 또는 **azure 제작진** 탭이 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b29a4-141">If you don't have any Azure credits, you won't see the **Azure credit balance** or **Azure credits** tabs.</span></span>

## <a name="need-help-contact-support"></a><span data-ttu-id="b29a4-142">도움이 필요하신가요?</span><span class="sxs-lookup"><span data-stu-id="b29a4-142">Need help?</span></span> <span data-ttu-id="b29a4-143">고객 지원에 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="b29a4-143">Contact support.</span></span>

<span data-ttu-id="b29a4-144">Azure 청구에 대 한 질문이 있거나 도움이 필요한 경우 <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">azure 지원 서비스를 통해 지원 요청을 만듭니다</a>.</span><span class="sxs-lookup"><span data-stu-id="b29a4-144">If you have questions or need help with your Azure charges, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">create a support request with Azure support</a>.</span></span>

<span data-ttu-id="b29a4-145">Microsoft 365 관리 센터에서 청구 프로필에 대 한 질문이 있거나 도움이 필요한 경우 [비즈니스 제품 지원에 문의 하세요](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="b29a4-145">If you have questions or need help with your billing profile in Microsoft 365 admin center, [contact support for business products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>
