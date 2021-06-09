---
title: 예약 정책 설정
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 4b2c84ec-64d3-4027-af4c-40f69e7b37c9
description: 비즈니스에 대한 계획 정책을 설정하는 방법을 배워야 합니다. 예약 정책에는 약속의 길이뿐만 아니라 허용되는 잠재 고객 및 취소 시간도 포함됩니다.
ms.openlocfilehash: 82cc9a66e82665040a1f0d08635cae10cd413d4b
ms.sourcegitcommit: 41fd71ec7175ea3b94f5d3ea1ae2c8fb8dc84227
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/09/2020
ms.locfileid: "47419923"
---
# <a name="set-your-scheduling-policies"></a><span data-ttu-id="59d0d-104">예약 정책 설정</span><span class="sxs-lookup"><span data-stu-id="59d0d-104">Set your scheduling policies</span></span>

<span data-ttu-id="59d0d-105">모든 약속이 동일하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="59d0d-105">Not all appointments are the same.</span></span> <span data-ttu-id="59d0d-106">일부는 몇 분 정도 걸릴 수 있는 반면 다른 일부는 몇 시간 이상 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59d0d-106">Some take only a few minutes, while others can take hours or more.</span></span> <span data-ttu-id="59d0d-107">Microsoft Bookings에서 예약 페이지에서는 비즈니스에 대한 예약 정책을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59d0d-107">In Microsoft Bookings, the booking page is where you set the scheduling policies for your business.</span></span> <span data-ttu-id="59d0d-108">예약 정책에는 약속의 길이, 허용 가능한 잠재 고객 및 취소 시간, 예약 변경에 대한 자동 알림이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="59d0d-108">Scheduling policies include the length of appointments, acceptable lead and cancellation times, and automatic notifications of booking changes.</span></span> <span data-ttu-id="59d0d-109">서비스 페이지 내의 각 서비스에 대해 추가 사용자 지정을 추가할 수 있으며 해당 서비스에만 적용되는 추가 기간 설정 및 정책을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59d0d-109">Additional customization can be added for each service within the Services page, with additional duration settings and policies that apply only to that service.</span></span>

<span data-ttu-id="59d0d-110">여기서 설정하는 정책은 최상위 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="59d0d-110">The policies you set here are the top-level policies.</span></span> <span data-ttu-id="59d0d-111">서비스 기준에 따라 수정하기로 선택하지 않는 한 제공한 모든 서비스에 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="59d0d-111">They are automatically applied to all the services you offer unless you choose to modify them on a per-service basis.</span></span> <span data-ttu-id="59d0d-112">예를 들어 초기 컨설팅과 같은 대부분의 서비스의 경우 취소에 대한 1일 알림이 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="59d0d-112">For example, let's say that for most services, such as initial consultations, one-day notice for cancellations is acceptable.</span></span> <span data-ttu-id="59d0d-113">하지만 시설 예약 또는 수수료가 필요한 서비스(예: 교대 수업)의 경우 3일 알림이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59d0d-113">But for those services that require facility reservations or fees, such as golf lessons, you might require three days' notice.</span></span> <span data-ttu-id="59d0d-114">서비스 페이지에서 이 서비스 수준 정책을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59d0d-114">You can set this service-level policy on the Services page.</span></span> <span data-ttu-id="59d0d-115">자세한 [내용은 서비스 제품 정의를](define-service-offerings.md) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="59d0d-115">See [Define your service offerings](define-service-offerings.md) for instructions.</span></span>

## <a name="types-of-scheduling-policies"></a><span data-ttu-id="59d0d-116">정책의 유형</span><span class="sxs-lookup"><span data-stu-id="59d0d-116">Types of scheduling policies</span></span>

<span data-ttu-id="59d0d-117">이 표에서는 예약 페이지에서 사용할 수 있는 다양한 예약 정책에 대해 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59d0d-117">This table explains the various scheduling policies available on the booking page.</span></span>

| <span data-ttu-id="59d0d-118">정책</span><span class="sxs-lookup"><span data-stu-id="59d0d-118">Policy</span></span> | <span data-ttu-id="59d0d-119">설명</span><span class="sxs-lookup"><span data-stu-id="59d0d-119">Explanation</span></span> |
|---|---|
| <span data-ttu-id="59d0d-120">시간 증분</span><span class="sxs-lookup"><span data-stu-id="59d0d-120">Time increments</span></span> | <span data-ttu-id="59d0d-121">약속 사이의 간격을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="59d0d-121">Determines the intervals between appointments.</span></span> <span data-ttu-id="59d0d-122">시간 증가를 5분에서 4시간으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59d0d-122">You can set your time increments from 5 minutes to 4 hours.</span></span> <span data-ttu-id="59d0d-123">사용자 지정 시간 증분을 직접 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59d0d-123">You can also set your own customized time increments.</span></span> <span data-ttu-id="59d0d-124">예를 들어 15분 간격은 고객이 8:00, 8:15, 8:30으로 60분 약속을 예약할 수 있다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="59d0d-124">An interval of 15 minutes, for example, means a customer could schedule a 60-minute appointment at 8:00, 8:15, 8:30, and so on.</span></span> <span data-ttu-id="59d0d-125">반대로 60분 간격은 약속이 시간에서만 사용할 수 있도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="59d0d-125">Conversely, a 60-minute interval means that appointments are only available on the hour.</span></span> <span data-ttu-id="59d0d-126">서비스 기간을 설정하는 경우 [Define your service offerings을 참조합니다.](define-service-offerings.md)</span><span class="sxs-lookup"><span data-stu-id="59d0d-126">(To set service durations, see [Define your service offerings](define-service-offerings.md).)</span></span> |
| <span data-ttu-id="59d0d-127">리드 타임(시간)</span><span class="sxs-lookup"><span data-stu-id="59d0d-127">Lead time in hours</span></span> | <span data-ttu-id="59d0d-128">예약된 약속에 따라 직원 계획을 수립할 수 있으므로 특정 일자에 서비스를 위해 얼마나 많은 고객이 온지 미리 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59d0d-128">You build your staffing plan based on the appointments that are scheduled so it's important to know in advance how many customers are coming in for service on any particular day.</span></span> <span data-ttu-id="59d0d-129">에지 타임 정책을 사용하면 고객이 약속을 예약하거나 취소해야 하는 시간을 미리 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59d0d-129">The lead time policy enables you to specify the number of hours in advance that customers must book or cancel an appointment.</span></span> |
| <span data-ttu-id="59d0d-130">최대 일 사전</span><span class="sxs-lookup"><span data-stu-id="59d0d-130">Maximum days in advance</span></span> | <span data-ttu-id="59d0d-131">고객이 약속을 미리 예약할 수 있는 거리를 제한하려는 경우 이 설정이 바로 사용자에 대한 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="59d0d-131">If you want to limit how far in advance customers can book appointments, then this is the setting for you!</span></span> <span data-ttu-id="59d0d-132">최대 365일 이상을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59d0d-132">You can set the maximum for 365 days or more.</span></span> |
| <span data-ttu-id="59d0d-133">예약이 만들어지거나 변경될 때 알림</span><span class="sxs-lookup"><span data-stu-id="59d0d-133">Notify when a booking is created or changed</span></span> | <span data-ttu-id="59d0d-134">고객이 약속을 예약하거나 기존 약속을 변경할 때 전자 메일을 받으시고 싶으면 이 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="59d0d-134">Select this option when you want to receive an email any time a customer books an appointment or changes an existing one.</span></span> <span data-ttu-id="59d0d-135">전자 메일은 비즈니스 정보 페이지에 지정된 사서함으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="59d0d-135">The email will go to the mailbox specified on the Business information page.</span></span> <span data-ttu-id="59d0d-136">자세한 [내용은 비즈니스 정보 입력을](enter-business-information.md) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="59d0d-136">See [Enter your business information](enter-business-information.md) for details.</span></span> |

## <a name="set-your-policies"></a><span data-ttu-id="59d0d-137">정책 설정</span><span class="sxs-lookup"><span data-stu-id="59d0d-137">Set your policies</span></span>

1. <span data-ttu-id="59d0d-138">다음 Microsoft 365 시작 프로그램을 선택한 다음 Bookings를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="59d0d-138">In Microsoft 365, select the app launcher, and then select Bookings.</span></span>

1. <span data-ttu-id="59d0d-139">탐색 창에서 예약 **페이지를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="59d0d-139">In the navigation pane, select **Booking page**.</span></span>

1. <span data-ttu-id="59d0d-140">정책 설정 섹션에서 **정책을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="59d0d-140">Select your policies under the **Scheduling policy** section.</span></span>

1. <span data-ttu-id="59d0d-141">저장 **및 게시를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="59d0d-141">Select **Save and publish**.</span></span>

## <a name="publish-the-booking-page"></a><span data-ttu-id="59d0d-142">예약 페이지 게시</span><span class="sxs-lookup"><span data-stu-id="59d0d-142">Publish the booking page</span></span>

<span data-ttu-id="59d0d-143">예약 페이지를 게시할 준비가 되면 저장 및 **게시를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="59d0d-143">When you're ready to publish your booking page, select **Save and publish**.</span></span> <span data-ttu-id="59d0d-144">자세한 [내용은 예약 페이지 사용자 지정 및](customize-booking-page.md) 게시를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="59d0d-144">See [Customize and publish your booking page](customize-booking-page.md) for more information.</span></span>
