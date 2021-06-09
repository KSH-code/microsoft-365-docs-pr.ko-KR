---
title: Microsoft Bookings에서 버퍼 시간 설정
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 271f43e4-b8f7-4d63-8059-b5747679bb7e
description: Microsoft Bookings에서 약속 전후에 버퍼 시간을 설정하여 장비 정리 또는 초기화 시간을 허용합니다.
ms.openlocfilehash: 882ab0340fe56976429ed8294f2fa386b801941f
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962350"
---
# <a name="set-buffer-time-in-microsoft-bookings"></a><span data-ttu-id="a244e-103">Microsoft Bookings에서 버퍼 시간 설정</span><span class="sxs-lookup"><span data-stu-id="a244e-103">Set buffer time in Microsoft Bookings</span></span>

<span data-ttu-id="a244e-104">일부 약속은 고객과 만나기 전이나 후에 방 및 장비를 설정, 정리 또는 초기화하는 데 시간이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a244e-104">Some of your appointments might require time before or after you meet with your customer to set up, clean up, or reset your room and equipment.</span></span> <span data-ttu-id="a244e-105">또는 고객 약속 사이를 이동하는 경우 고객과 팀이 고객이 기다리지 않고 약속을 이행할 수 있도록 보장하는 데 시간이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a244e-105">Or if you’re on the road between customer appointments, you may need time to ensure you and your team can travel between appointments without making the customer wait.</span></span>

<span data-ttu-id="a244e-106">약속이 시작되기 전이나 약속이 종료된 후 또는 직원에게 다음 약속을 준비하는 데 필요한 추가 시간을 제공하려면 버퍼 시간을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a244e-106">You can set buffer time before appointments start, after appointments end, or both to give staff the extra time they need to prepare for their next appointment.</span></span>

## <a name="set-buffer-time-defaults"></a><span data-ttu-id="a244e-107">버퍼 시간 기본값 설정</span><span class="sxs-lookup"><span data-stu-id="a244e-107">Set buffer time defaults</span></span>

<span data-ttu-id="a244e-108">버퍼 시간 기본값은 Bookings의 서비스 세부 정보 페이지에서 설정됩니다. </span><span class="sxs-lookup"><span data-stu-id="a244e-108">Buffer time defaults are set on the **Service details** page in Bookings.</span></span> <span data-ttu-id="a244e-109">이 페이지에 설정된 모든 서비스 기본값과 마찬가지로 특정 고객의 요구를 충족하기 위해 특정 예약에 대해 이러한 기본값을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a244e-109">Like all service defaults set on this page, these defaults can be edited by you for a specific booking to meet specific customer needs.</span></span>

<span data-ttu-id="a244e-110">버퍼 시간 설정은 서비스 세부  정보 페이지의 기본 기간 선택기 바로 아래에 **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="a244e-110">The buffer time setting can be found just below the **Default duration** pickers on the **Service details** page.</span></span> <span data-ttu-id="a244e-111">특정 서비스에 대해 설정하려면 먼저 버퍼 시간 토글을 선택하여 버퍼 시간 설정을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a244e-111">Before it can be set for a given service, you must enable the buffer time setting by selecting the buffer time toggle.</span></span> <span data-ttu-id="a244e-112">이렇게 하면 다음과 같이 각 예약 전후에 보유할 기본 시간을 선택할 수 있는 **Before** 및 **After** 드롭다운이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a244e-112">This causes the **Before** and **After** drop-downs to appear, which are used to pick the default amount of time to hold before and after each booking, as shown here:</span></span>

   ![버퍼 시간이 사용하도록 설정된 Bookings 이미지](../media/bookings-buffertime.png)

## <a name="buffer-time-and-appointment-timing"></a><span data-ttu-id="a244e-114">버퍼 시간 및 약속 타이밍</span><span class="sxs-lookup"><span data-stu-id="a244e-114">Buffer time and appointment timing</span></span>

<span data-ttu-id="a244e-115">고객이 만나야 하는 시기에 대한 혼동을 방지하기 위해 Bookings는 일정과 관련 직원에게 전자 메일 확인 및 미리 알림에 버퍼 시간 및 실제 약속 시간(고객이 만나게 될 것으로 예상되는 시간)을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="a244e-115">To avoid confusion about when customers expect to meet with you, Bookings shows buffer time and actual appointment time (the time your customers expect to meet with you) on your calendar, and in email confirmations and reminders to relevant staff.</span></span> <span data-ttu-id="a244e-116">예를 들어 다음은 Bookings에서 약속 전 버퍼 시간이 15분인 고객의 약속에 대한 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="a244e-116">For example, below is what you’d see in Bookings for an appointment with a customer that includes 15 minutes of pre-appointment buffer time.</span></span>

<span data-ttu-id="a244e-117">이벤트 자체(아래 이미지의 왼쪽)는 버퍼 시간의 밝은 음영과 실제 고객 약속의 어두운 음영을 보여 둡니다.</span><span class="sxs-lookup"><span data-stu-id="a244e-117">Note that the event itself (on the left in the image below) shows lighter shading for the buffer time and darker shading for the actual customer appointment.</span></span> <span data-ttu-id="a244e-118">약속 설명선(이벤트를 선택할 때 열리며)은 특히 Katie Jordan과의 약속이 오전 9시에서 10:00AM까지라고 구체적으로 설명하고 약속 전 버퍼 시간이 15분, 약속 후 0분을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="a244e-118">The appointment call-out (which is opened when you select the event) specifically states that the appointment is from 9:00AM to 10:00AM with Katie Jordan and includes 15 minutes of buffer time before the appointment and 0 minutes after the appointment.</span></span> <span data-ttu-id="a244e-119">직원에 대한 확인 및 미리 알림은 고객이 9:00AM에서 10:00AM 약속 시간을 참조하는 확인 및 미리 알림만 받을 때 특정 버퍼 및 약속 시간을 비슷하게 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="a244e-119">Confirmations and reminders to staff similarly reference specific buffer and appointment time while the customer would only get confirmations and reminders that reference a 9:00AM to 10:00AM appointment time.</span></span>

   ![버퍼 시간이 표시된 Bookings 약속 콜아웃 이미지](../media/bookings-buffertime-callout.png)

## <a name="buffer-time-and-availability"></a><span data-ttu-id="a244e-121">버퍼 시간 및 가용성</span><span class="sxs-lookup"><span data-stu-id="a244e-121">Buffer time and availability</span></span>

<span data-ttu-id="a244e-122">고객이 직접 볼 수 없는 경우 설정한 버퍼 시간을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a244e-122">Your customers don’t directly see and cannot change the buffer times you set.</span></span> <span data-ttu-id="a244e-123">그러나 버퍼 시간을 사용하여 전체 서비스 기간을 계산하기 때문에 고객은 버퍼와 정기 약속 시간 모두에 예약된 사용자 및 관련 직원을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a244e-123">However, because buffer time is used to calculate overall service duration, customers will see you and your relevant staff as booked during both buffer and regular appointment times.</span></span> <span data-ttu-id="a244e-124">또한 고객은 약속과 해당 버퍼 시간 모두에 충분한 시간이 있는 경우 사용자와 직원의 가용성만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a244e-124">Customers also only see availability for you and your staff if there is enough time for both the appointment and its buffer time.</span></span>

<span data-ttu-id="a244e-125">예를 들어 약속 전 버퍼 시간이 15분인 1시간 약속에는 최소 1시간 15분의 사용 가능한 시간 블록이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a244e-125">As an example, a one-hour appointment with a 15-minute pre-appointment buffer time requires an available time block of at least 1 hour and 15 minutes.</span></span> <span data-ttu-id="a244e-126">따라서 이 서비스의 약속은 일정에서 75분 분의 시간 블록을 채우며 충돌 없이 예약할 수 있는 시간은 75분입니다.</span><span class="sxs-lookup"><span data-stu-id="a244e-126">An appointment for this service would therefore fill a 75-minute block of time on your calendar and needs 75 minutes of availability to book without conflict.</span></span>
