---
title: 청구 프로필 관리
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
ms.custom: ''
search.appverid:
- MET150
description: 청구 프로필에서 송장을 지 원하는 방법을 알아봅니다.
keywords: 청구 프로필, 송장, 요금, 관리 비용
ms.openlocfilehash: 4b46709cf877ea8689f72b66d5ac357272e4737d
ms.sourcegitcommit: 7713e777731025c165e9e936198609503ade5665
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/20/2019
ms.locfileid: "38753547"
---
# <a name="manage-billing-profiles"></a><span data-ttu-id="e0de4-104">청구 프로필 관리</span><span class="sxs-lookup"><span data-stu-id="e0de4-104">Manage billing profiles</span></span>
<span data-ttu-id="e0de4-105">Microsoft의 제품 및 서비스를 구입한 상용 고객의 경우 대금 청구 프로필을 사용 하 여 송장에 포함 되는 항목을 사용자 지정 하 고 청구서 비용을 지불 하는 방법을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0de4-105">For commercial customers who buy products and services from Microsoft, billing profiles let you customize what items are included on your invoice, and how you pay your invoices.</span></span>

<span data-ttu-id="e0de4-106">대금 청구 프로필에는 다음 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0de4-106">Billing profiles include the following information:</span></span>

- <span data-ttu-id="e0de4-107">청구 계정 프로필과 관련 된 **계정** &ndash; 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e0de4-107">**Billing account** &ndash; Name of the billing account the profile is related to</span></span>
- <span data-ttu-id="e0de4-108">**결제 방법** &ndash; 크레딧 또는 직불 카드, 은행 계좌, 확인 또는 전선 전송</span><span class="sxs-lookup"><span data-stu-id="e0de4-108">**Payment methods** &ndash; Credit or debit cards, bank accounts, check, or wire transfer</span></span>
- <span data-ttu-id="e0de4-109">**연락처 정보** &ndash; 청구 주소 및 연락처 이름</span><span class="sxs-lookup"><span data-stu-id="e0de4-109">**Contact information** &ndash; Billing address and a contact name</span></span>
- <span data-ttu-id="e0de4-110">**송장 설정** &ndash; 대금 청구 계정의 국가, 선택적 PO 번호 및 청구서를 전자 메일 첨부 파일로 수신 하는 옵션을 기준으로 통화</span><span class="sxs-lookup"><span data-stu-id="e0de4-110">**Invoice settings** &ndash; Currency based on the country of the billing account, an optional PO number, and the option to receive invoices as email attachments</span></span>
- <span data-ttu-id="e0de4-111">**사용 권한** &ndash; 권한 프로필을 변경 하거나, 청구서를 지불 하거나, 대금 청구 프로필에서 결제 방법을 사용 하 여 구매를 수행할 수 있도록 하는 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0de4-111">**Permissions** &ndash; Permissions that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchases</span></span>

<span data-ttu-id="e0de4-112">청구 프로필을 사용 하 여 구매를 제어 하 고 송장을 사용자 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0de4-112">Use billing profiles to control your purchases and customize your invoice.</span></span> <span data-ttu-id="e0de4-113">대금 청구 프로필과 함께 구매한 제품에 대해 월별 송장이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0de4-113">A monthly invoice is generated for the products bought with the billing profile.</span></span> <span data-ttu-id="e0de4-114">구매 주문 번호 및 전자 메일 송장 기본 설정 업데이트와 같은 송장을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0de4-114">You can customize the invoice such as update the purchase order number and email invoice preference.</span></span>

<span data-ttu-id="e0de4-115">최초 구매 중에 청구 계정에 대 한 대금 청구 프로필이 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="e0de4-115">A billing profile is automatically created for your billing account during your first purchase.</span></span> <span data-ttu-id="e0de4-116"><a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">청구 프로필</a> 페이지에서 청구 프로필을 만들어 추가 송장을 더 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0de4-116">You can create billing profiles on the <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Billing profiles</a> page to set up more invoices.</span></span> <span data-ttu-id="e0de4-117">예를 들어 조직의 각 부서에 대해 구매를 수행 하는 경우 다른 대금 청구 프로필을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0de4-117">For example, you can use different billing profiles when you make purchases for each department in your organization.</span></span> <span data-ttu-id="e0de4-118">다음 청구 날짜에는 각 대금 청구 프로필에 대 한 송장을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0de4-118">On your next billing date, you'll receive an invoice for each billing profile.</span></span>

## <a name="billing-profile-roles"></a><span data-ttu-id="e0de4-119">청구 프로필 역할</span><span class="sxs-lookup"><span data-stu-id="e0de4-119">Billing profile roles</span></span>

<span data-ttu-id="e0de4-120">청구 프로필에 대 한 역할에는 구매를 제어 하 고 송장을 보고 관리할 수 있는 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0de4-120">Roles on billing profiles have permissions to control purchases, and view and manage invoices.</span></span> <span data-ttu-id="e0de4-121">조직의 조달 팀 구성원과 같이 송장을 추적, 구성 및 지불 하는 사용자에 게 이러한 역할을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0de4-121">Assign these roles to users who track, organize, and pay invoices, like members of the procurement team in your organization.</span></span>

| <span data-ttu-id="e0de4-122">역할</span><span class="sxs-lookup"><span data-stu-id="e0de4-122">Role</span></span>                          | <span data-ttu-id="e0de4-123">설명</span><span class="sxs-lookup"><span data-stu-id="e0de4-123">Description</span></span>                                                                       |
|-----------------------------  |---------------------------------------------------------------------------------  |
| <span data-ttu-id="e0de4-124">청구 프로필 소유자</span><span class="sxs-lookup"><span data-stu-id="e0de4-124">Billing profile owner</span></span>         | <span data-ttu-id="e0de4-125">청구 프로필에 대 한 모든 항목 관리</span><span class="sxs-lookup"><span data-stu-id="e0de4-125">Manage everything for a billing profile</span></span>                                           |
| <span data-ttu-id="e0de4-126">대금 청구 프로필 참가자</span><span class="sxs-lookup"><span data-stu-id="e0de4-126">Billing profile contributor</span></span>   | <span data-ttu-id="e0de4-127">청구 프로필의 사용 권한을 제외한 모든 항목 관리</span><span class="sxs-lookup"><span data-stu-id="e0de4-127">Manage everything except permissions in a billing profile</span></span>                         |
| <span data-ttu-id="e0de4-128">청구 프로필 독자</span><span class="sxs-lookup"><span data-stu-id="e0de4-128">Billing profile reader</span></span>        | <span data-ttu-id="e0de4-129">대금 청구 프로필의 모든 항목에 대 한 읽기 전용 보기</span><span class="sxs-lookup"><span data-stu-id="e0de4-129">Read-only view of everything in a billing profile</span></span>                                 |
| <span data-ttu-id="e0de4-130">송장 관리자</span><span class="sxs-lookup"><span data-stu-id="e0de4-130">Invoice manager</span></span>               | <span data-ttu-id="e0de4-131">청구 프로필의 모든 항목에 대 한 읽기 전용 보기 및 청구서 보기 및 지불</span><span class="sxs-lookup"><span data-stu-id="e0de4-131">View and pay bills, and has a read-only view of everything in a billing profile</span></span>   |

## <a name="view-billing-profiles"></a><span data-ttu-id="e0de4-132">청구 프로필 보기</span><span class="sxs-lookup"><span data-stu-id="e0de4-132">View billing profiles</span></span>

1. <span data-ttu-id="e0de4-133">관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848039" target="_blank">금액 & 지불</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0de4-133">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848039" target="_blank">Bills & payments</a> page.</span></span>

2. <span data-ttu-id="e0de4-134">**대금 청구**프로필을 선택한 다음 목록에서 대금 청구 프로필을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0de4-134">Choose **Billing profiles**, and then choose a billing profile from the list.</span></span>

    - <span data-ttu-id="e0de4-135">**개요** 탭에서 청구 프로필 세부 정보를 편집 하 고 전자 메일로 송장을 보내지 않거나 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0de4-135">On the **Overview** tab, you can edit billing profile details, and turn on or off sending an invoice by email.</span></span>

    - <span data-ttu-id="e0de4-136">**사용 권한** 탭에서 송장을 지불 하기 위해 사용자에 게 역할을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0de4-136">On the **Permissions** tab, you can assign roles to users to pay invoices.</span></span>

    - <span data-ttu-id="e0de4-137">Azure **구매 잔액** 탭에서 azure 고객은 해당 청구 프로필에 사용 되는 azure 제작진에 대 한 트랜잭션 균형 기록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0de4-137">On the **Azure credit balance** tab, Azure customers can see transaction balance history for the Azure credits used by that billing profile.</span></span>

    - <span data-ttu-id="e0de4-138">**Azure 사용** 가능 항목에서 azure 고객은 해당 청구 프로필에 연결 된 azure 제작진 목록과 만료 날짜를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0de4-138">On the **Azure credits** tab, Azure customers can see a list of Azure credits associated with that billing profile, and their expiration dates.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e0de4-139">Azure 크레딧이 없는 경우 **azure 크레딧 잔액** 또는 **azure 제작진** 탭이 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e0de4-139">If you don't have any Azure credits, you won't see the **Azure credit balance** or **Azure credits** tabs.</span></span>

## <a name="need-help-contact-support"></a><span data-ttu-id="e0de4-140">도움이 필요 하세요?</span><span class="sxs-lookup"><span data-stu-id="e0de4-140">Need help?</span></span> <span data-ttu-id="e0de4-141">고객 지원에 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="e0de4-141">Contact support.</span></span>

<span data-ttu-id="e0de4-142">Azure 청구에 대 한 질문이 있거나 도움이 필요한 경우 <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">azure 지원 서비스를 통해 지원 요청을 만듭니다</a>.</span><span class="sxs-lookup"><span data-stu-id="e0de4-142">If you have questions or need help with your Azure charges, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">create a support request with Azure support</a>.</span></span>

<span data-ttu-id="e0de4-143">Microsoft 365 관리 센터에서 청구 프로필에 대 한 질문이 있거나 도움이 필요한 경우 [비즈니스 제품 지원에 문의 하세요](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="e0de4-143">If you have questions or need help with your billing profile in Microsoft 365 admin center, [contact support for business products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>