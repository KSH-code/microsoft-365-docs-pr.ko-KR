---
title: 상업용 고객을 위한 결제 서비스 지시어 2 및 강력한 고객 인증
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
ms.custom: ''
search.appverid:
- MET150
description: 결제를 처리 하려면 먼저 온라인 구매를 수행 하는 사용자의 id를 확인 하는 데 유럽 경제 분야의 31 개국 년 9 월 2019 14 일에 시작 하는 것이 필요 합니다.
keywords: 결제 서비스 지시어 2, 강력한 고객 인증, 다단계 인증
ms.openlocfilehash: 53de6ce3158760299a3ed2a7bc840919babf20bd
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42080395"
---
# <a name="payment-services-directive-2-and-strong-customer-authentication-for-commercial-customers"></a><span data-ttu-id="83422-104">상업용 고객을 위한 결제 서비스 지시어 2 및 강력한 고객 인증</span><span class="sxs-lookup"><span data-stu-id="83422-104">Payment Services Directive 2 and Strong Customer Authentication for commercial customers</span></span>

<span data-ttu-id="83422-105">결제를 처리 하려면 먼저 온라인 구매를 수행 하는 사용자의 id를 확인 하는 데 유럽 경제 분야의 31 개국 년 9 월 2019 14 일에 시작 하는 것이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="83422-105">Starting on September 14, 2019, banks in the 31 countries of the European Economic Area are required to verify the identity of the person making an online purchase before the payment can be processed.</span></span> <span data-ttu-id="83422-106">이 확인을 위해서는 온라인 구매를 안전 하 게 보호 하 고 보호할 수 있도록 다단계 인증이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="83422-106">This verification requires multi-factor authentication to help ensure your online purchases are secure and protected.</span></span> <span data-ttu-id="83422-107">이 확인 요구 사항에 대 한 날짜는 일부 국가에서 지연 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83422-107">The date for this verification requirement will be delayed for some countries.</span></span> 

<span data-ttu-id="83422-108">자세한 내용은 [결제 서비스 지시어 2 및 강력한 고객 인증에 대 한 MICROSOFT FAQ](https://support.microsoft.com/help/4517854/microsoft-account-open-banking-customer-authentication)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="83422-108">For more information, see [Microsoft FAQ about Payment Services Directive 2 and Strong Customer Authentication](https://support.microsoft.com/help/4517854/microsoft-account-open-banking-customer-authentication).</span></span>

## <a name="when-is-multi-factor-authentication-required"></a><span data-ttu-id="83422-109">Multi-factor authentication이 필요한 경우</span><span class="sxs-lookup"><span data-stu-id="83422-109">When is multi-factor authentication required?</span></span>

<span data-ttu-id="83422-110">현재 다단계 인증을 사용 하는이 지시어에 대 한 확인 요구 사항은 유럽 경제 분야의 31 개국에 있는 뱅크의 신용 카드를 사용 하는 고객 에게만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83422-110">Currently, verification requirements for this directive using multi-factor authentication only apply to customers using credit cards from banks in the 31 countries of the European Economic Area.</span></span> <span data-ttu-id="83422-111">때로는 사용자에 게 수행 된 작업으로 인해 메시지가 표시 되 고 기존 구독 또는 서비스와 관련 된 이벤트로 인해 메시지가 표시 되는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83422-111">Sometimes customers will be prompted because of an action that they took, and sometimes they are prompted because of events with their existing subscriptions or services.</span></span>

### <a name="customer-actions"></a><span data-ttu-id="83422-112">고객 작업</span><span class="sxs-lookup"><span data-stu-id="83422-112">Customer Actions</span></span>

<span data-ttu-id="83422-113">은행이 다단계 인증을 통해 확인을 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83422-113">Your bank may require verification through multi-factor authentication.</span></span> <span data-ttu-id="83422-114">몇 가지 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="83422-114">Some examples include:</span></span>
- <span data-ttu-id="83422-115">새 구독에 등록</span><span class="sxs-lookup"><span data-stu-id="83422-115">Signing up for a new subscription</span></span>
- <span data-ttu-id="83422-116">구독에 라이선스 추가</span><span class="sxs-lookup"><span data-stu-id="83422-116">Adding licenses to a subscription</span></span>
- <span data-ttu-id="83422-117">구독 또는 서비스 비용 지불에 사용 된 신용 카드 추가 또는 교체</span><span class="sxs-lookup"><span data-stu-id="83422-117">Adding or replacing the credit card used to pay for a subscription or service</span></span>
- <span data-ttu-id="83422-118">대금 청구 프로필에 신용 카드 추가 또는 교체</span><span class="sxs-lookup"><span data-stu-id="83422-118">Adding or replacing a credit card on a billing profile</span></span>
- <span data-ttu-id="83422-119">앱 구매</span><span class="sxs-lookup"><span data-stu-id="83422-119">Buying apps</span></span>

### <a name="subscription-lifecycle-events"></a><span data-ttu-id="83422-120">구독 수명 주기 이벤트</span><span class="sxs-lookup"><span data-stu-id="83422-120">Subscription lifecycle events</span></span>

<span data-ttu-id="83422-121">반복 상환 요금이 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83422-121">Charges for recurring payments might fail.</span></span> <span data-ttu-id="83422-122">이러한 경우에는 다음과 같은 지침이 포함 된 전자 메일을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83422-122">If they do, you’ll receive an email with instructions to follow.</span></span> <span data-ttu-id="83422-123">확인 요청에 응답 하 고 현재 결제를 수행 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83422-123">You’ll be prompted to respond to the verification request and make your current payment.</span></span>

## <a name="need-more-help"></a><span data-ttu-id="83422-124">추가 도움이 필요하세요?</span><span class="sxs-lookup"><span data-stu-id="83422-124">Need more help?</span></span>

<span data-ttu-id="83422-125">해당 금융 기관은 다음과 같은 시나리오에 가장 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="83422-125">Your financial institution is the best contact for these scenarios:</span></span>
- <span data-ttu-id="83422-126">확인 코드를 받지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="83422-126">You didn't receive a verification code.</span></span>  
- <span data-ttu-id="83422-127">확인 코드를 전송한 후에 확인 프로세스가 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83422-127">The verification process didn't work after you submitted the verification code.</span></span>
- <span data-ttu-id="83422-128">신용 카드의 대화 상대 정보가 올바른지는 확인 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83422-128">You're not sure if the contact info for your credit card is correct.</span></span>
