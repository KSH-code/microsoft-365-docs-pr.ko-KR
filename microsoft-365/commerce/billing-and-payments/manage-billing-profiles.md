---
title: 청구 프로필 이해하기
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
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
- commerce_billing
- AdminTemplateSet
search.appverid: MET150
description: 청구 프로필에서 송장을 지원하는 방법을 알아보세요.
ms.date: 04/02/2021
ms.openlocfilehash: ecea09a9ceea12fa92b92eac3e5a7595b2510042
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394632"
---
# <a name="understand-billing-profiles"></a><span data-ttu-id="3a32b-103">청구 프로필 이해하기</span><span class="sxs-lookup"><span data-stu-id="3a32b-103">Understand billing profiles</span></span>

<span data-ttu-id="3a32b-104">청구 프로필에는 결제 방법, 청구 정보 및 기타 송장 설정(예: 구매 주문 번호 및 전자 메일 송장 기본 설정)이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a32b-104">A billing profile contains a payment method, Bill-to information, and other invoice settings, such as purchase order number and email invoice preference.</span></span> <span data-ttu-id="3a32b-105">청구 프로필을 사용하여 Microsoft에서 구입한 제품에 대한 비용을 지불합니다.</span><span class="sxs-lookup"><span data-stu-id="3a32b-105">You use a billing profile to pay for the products that you buy from Microsoft.</span></span> <span data-ttu-id="3a32b-106">사용자가 셀프 서비스 구매를 하면 청구 프로필이 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="3a32b-106">A billing profile is automatically created when a user makes a self-service purchase.</span></span> <span data-ttu-id="3a32b-107">각 청구 프로필은 별도로 송장됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a32b-107">Each billing profile is invoiced separately.</span></span>

> [!NOTE]
>
> <span data-ttu-id="3a32b-108">대금 청구 프로필은 Microsoft.com 제품 및 서비스를 구입하는 고객은 청구  프로필을 사용할 수 Microsoft 365 관리 센터.</span><span class="sxs-lookup"><span data-stu-id="3a32b-108">Billing profiles are not available to customers who buy products and services from Microsoft.com or on the **Purchase services** page of the Microsoft 365 admin center.</span></span>

## <a name="what-are-billing-profile-roles"></a><span data-ttu-id="3a32b-109">청구 프로필 역할이란?</span><span class="sxs-lookup"><span data-stu-id="3a32b-109">What are billing profile roles?</span></span>

<span data-ttu-id="3a32b-110">청구 프로필의 역할에는 구매를 제어하고 송장을 보고 관리할 수 있는 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a32b-110">Roles on billing profiles have permissions to control purchases, and view and manage invoices.</span></span> <span data-ttu-id="3a32b-111">송장을 추적, 구성 및 결제하는 사용자에게 이러한 역할을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="3a32b-111">Assign these roles to users who track, organize, and pay invoices.</span></span> <span data-ttu-id="3a32b-112">예를 들어 조직의 조달 팀 구성원.</span><span class="sxs-lookup"><span data-stu-id="3a32b-112">For example, members of the procurement team in your organization.</span></span>

| <span data-ttu-id="3a32b-113">역할</span><span class="sxs-lookup"><span data-stu-id="3a32b-113">Role</span></span>                         | <span data-ttu-id="3a32b-114">설명</span><span class="sxs-lookup"><span data-stu-id="3a32b-114">Description</span></span>                                                                      |
|----------------------------- |--------------------------------------------------------------------------------- |
| <span data-ttu-id="3a32b-115">청구 프로필 소유자</span><span class="sxs-lookup"><span data-stu-id="3a32b-115">Billing profile owner</span></span>        | <span data-ttu-id="3a32b-116">청구 프로필에 대한 모든 정보 관리</span><span class="sxs-lookup"><span data-stu-id="3a32b-116">Manage everything for a billing profile</span></span>                                          |
| <span data-ttu-id="3a32b-117">청구 프로필 참가자</span><span class="sxs-lookup"><span data-stu-id="3a32b-117">Billing profile contributor</span></span>  | <span data-ttu-id="3a32b-118">청구 프로필의 사용 권한을 제외한 모든 정보 관리</span><span class="sxs-lookup"><span data-stu-id="3a32b-118">Manage everything except permissions in a billing profile</span></span>                        |
| <span data-ttu-id="3a32b-119">청구 프로필 판독기</span><span class="sxs-lookup"><span data-stu-id="3a32b-119">Billing profile reader</span></span>       | <span data-ttu-id="3a32b-120">청구 프로필의 모든 내용을 읽기 전용으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a32b-120">Read-only view of everything in a billing profile</span></span>                                |
| <span data-ttu-id="3a32b-121">송장 관리자</span><span class="sxs-lookup"><span data-stu-id="3a32b-121">Invoice manager</span></span>              | <span data-ttu-id="3a32b-122">청구서 보기 및 결제 및 청구 프로필의 모든 내용을 읽기 전용으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a32b-122">View and pay bills, and has a read-only view of everything in a billing profile</span></span>  |

## <a name="view-my-billing-profiles"></a><span data-ttu-id="3a32b-123">내 청구 프로필 보기</span><span class="sxs-lookup"><span data-stu-id="3a32b-123">View my billing profiles</span></span>

> [!NOTE]
>
> <span data-ttu-id="3a32b-124">다음 단계를 수행하고 청구 프로필 목록이 비어 있는 경우 대금 청구 프로필이 없는 것이고 이 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3a32b-124">If you follow these steps and the billing profiles list is empty, it means that you don’t have a billing profile, and can’t use this feature.</span></span>

1. <span data-ttu-id="3a32b-125">관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">청구서 및 결제</a> 페이지로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="3a32b-125">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>
2. <span data-ttu-id="3a32b-126">청구 프로필 **탭을 선택한** 다음 목록에서 청구 프로필을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3a32b-126">Select the **Billing profile** tab, then select a billing profile from the list.</span></span>

<span data-ttu-id="3a32b-127">각 청구 프로필에는 다음 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a32b-127">Each billing profile includes the following information:</span></span>

- <span data-ttu-id="3a32b-128">**청구 프로필 이름 및 상태** &ndash; 청구 프로필의 고유 이름 및 구매를 위해 청구 프로필이 활성 상태인지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3a32b-128">**Billing profile name and status** &ndash; The unique name of the billing profile, and whether the billing profile is active or disabled for purchasing.</span></span>
- <span data-ttu-id="3a32b-129">**송장 설정** &ndash; 청구 계정 국가를 기반으로 하는 통화, 송장 빈도 및 날짜에 대한 정보, 전자 메일 첨부 파일로 송장을 받는 옵션 및 PO 번호 필드(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="3a32b-129">**Invoice settings** &ndash; Currency based on the country of the billing account, information about invoice frequency and date, the option to receive invoices as email attachments, and an optional PO number field</span></span>
- <span data-ttu-id="3a32b-130">**결제 방법** &ndash; 프로필의 기본 및 백업 결제 방법(있는 경우)을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="3a32b-130">**Payment methods** &ndash; Shows the primary and backup payment method, if any, for the profile</span></span>
- <span data-ttu-id="3a32b-131">**청구 계정** &ndash; 프로필과 관련된 청구 계정의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3a32b-131">**Billing account** &ndash; Name of the billing account the profile is related to.</span></span> <span data-ttu-id="3a32b-132">청구 계정에 대한 자세한 내용은 청구 계정 [이해를 참조하세요.](../manage-billing-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="3a32b-132">For more information about billing accounts, see [Understand billing accounts](../manage-billing-accounts.md).</span></span>
- <span data-ttu-id="3a32b-133">**연락처 정보** &ndash; 대금 청구 주소 및 연락처 이름 및 전자 메일 주소</span><span class="sxs-lookup"><span data-stu-id="3a32b-133">**Contact information** &ndash; Billing address and contact name and email address</span></span>
- <span data-ttu-id="3a32b-134">**청구 프로필 역할** &ndash; 해당 프로필에 대해 작업을 할 청구 프로필 역할 중 하나에 할당된 사용자 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="3a32b-134">**Billing profile roles** &ndash; A list of people who are assigned one of the billing profile roles to do things for that profile.</span></span> <span data-ttu-id="3a32b-135">예를 들어 청구서 지불, PO 번호 추가 또는 구매에 사용되는 결제 방법을 대체할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a32b-135">For example, pay bills, add a PO number, or replace the payment method that is used to make purchases.</span></span>

> [!NOTE]
>
> <span data-ttu-id="3a32b-136">조직의 사용자에게만 청구 프로필 역할을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a32b-136">You can only assign billing profile roles to users in your organization.</span></span>

## <a name="need-help-contact-support"></a><span data-ttu-id="3a32b-137">도움이 필요하신가요?</span><span class="sxs-lookup"><span data-stu-id="3a32b-137">Need help?</span></span> <span data-ttu-id="3a32b-138">지원 센터 문의</span><span class="sxs-lookup"><span data-stu-id="3a32b-138">Contact support</span></span>

<span data-ttu-id="3a32b-139">질문이 있는 경우 또는 Azure 요금에 대한 도움이 필요한 경우 Azure 지원으로 지원 <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">요청을 만드하세요.</a></span><span class="sxs-lookup"><span data-stu-id="3a32b-139">If you have questions or need help with your Azure charges, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">create a support request with Azure support</a>.</span></span>

<span data-ttu-id="3a32b-140">2016년 8월 2일부로 문의하거나 청구 프로필에 대한 도움이 Microsoft 365 관리 센터 [문의하세요.](../../business-video/get-help-support.md)</span><span class="sxs-lookup"><span data-stu-id="3a32b-140">If you have questions or need help with your billing profile in Microsoft 365 admin center, [contact support](../../business-video/get-help-support.md).</span></span>

## <a name="related-content"></a><span data-ttu-id="3a32b-141">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="3a32b-141">Related content</span></span>

<span data-ttu-id="3a32b-142">[청구 프로필을 사용하여](pay-for-subscription-billing-profile.md) 구독 비용을 결제하는 방법(문서)</span><span class="sxs-lookup"><span data-stu-id="3a32b-142">[How to pay for your subscription with a billing profile](pay-for-subscription-billing-profile.md) (article)</span></span>\
<span data-ttu-id="3a32b-143">[청구 계정](../manage-billing-accounts.md) 이해(문서)</span><span class="sxs-lookup"><span data-stu-id="3a32b-143">[Understand billing accounts](../manage-billing-accounts.md) (article)</span></span>\
<span data-ttu-id="3a32b-144">[결제 방법](manage-payment-methods.md) 관리(문서)</span><span class="sxs-lookup"><span data-stu-id="3a32b-144">[Manage payment methods](manage-payment-methods.md) (article)</span></span>
