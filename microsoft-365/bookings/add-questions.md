---
title: 예약 페이지에 사용자 지정 및 필수 질문 추가
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: fd6b7587-5055-4bcd-83a4-13bd4929bfff
description: 온라인으로 약속을 예약할 때 고객에 게 질문을 해야 하는 경우 예약 페이지에 사용자 지정 질문 및 필수 질문을 추가할 수 있습니다.
ms.openlocfilehash: ebbb07857fd8bb196f769dfb7e71ad25a85dfd54
ms.sourcegitcommit: 41fd71ec7175ea3b94f5d3ea1ae2c8fb8dc84227
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/09/2020
ms.locfileid: "47419993"
---
# <a name="add-custom-and-required-questions-to-the-booking-page"></a><span data-ttu-id="54b7d-103">예약 페이지에 사용자 지정 및 필수 질문 추가</span><span class="sxs-lookup"><span data-stu-id="54b7d-103">Add custom and required questions to the booking page</span></span>

<span data-ttu-id="54b7d-104">예약을 사용 하면 고객에 게 약속을 예약 하는 데 도움이 되는 질문을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54b7d-104">Bookings lets you create questions to ask your customers when they are booking appointments.</span></span> <span data-ttu-id="54b7d-105">또한 필요한 질문을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54b7d-105">It also lets you choose which questions are required.</span></span>

<span data-ttu-id="54b7d-106">서비스와 질문을 연결 하 여 각 서비스에 서로 다른 질문 집합이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54b7d-106">You associate the questions with a service, so each service can have a different set of questions.</span></span> <span data-ttu-id="54b7d-107">예를 들어 머리카락 stylist는 bleaches 또는 색조로 알려진 고 지 사항이 있는 경우 머리 색 약속을 예약 하는 고객에 게 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54b7d-107">For example, a hair stylist may ask customers who are booking a hair coloring appointment if they have any known allergies to bleaches or tints.</span></span> <span data-ttu-id="54b7d-108">이를 통해 고객은 약속에 대해 도착 한 시간을 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54b7d-108">This allows you and your customers to save time when they arrive for their appointment.</span></span>

<span data-ttu-id="54b7d-109">고객은 예약 페이지에서 약속을 만들 때 사용자 지정 질문을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54b7d-109">The customers will see the custom questions when they are creating their appointment on the booking page.</span></span> <span data-ttu-id="54b7d-110">직원은 예약 일정에서 새 예약을 만들거나 기존 약속을 볼 때 사용자 지정 질문을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54b7d-110">Staff will see the custom questions when they create a new booking from the Bookings calendar or when viewing an existing appointment.</span></span> <span data-ttu-id="54b7d-111">예약 모든 서비스에 대해 동일한 질문을 다시 만들 필요가 없도록 모든 질문을 마스터 목록에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="54b7d-111">Bookings saves all of your questions to a master list so that you don't have to re-create the same questions for every service.</span></span> <span data-ttu-id="54b7d-112">또한 질문이 필수 사항 인지 선택 사항임 여부도 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54b7d-112">You can also choose whether questions are required or optional.</span></span>

> [!NOTE]
> <span data-ttu-id="54b7d-113">예약 일정에서 약속을 볼 때 질문에 대 한 고객의 대답이 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54b7d-113">The customer's answers to the questions can be seen when you look at their appointment in the booking calendar.</span></span>

<span data-ttu-id="54b7d-114">예약 페이지를 개인 설정 하 고 사용자 지정 하는 방법에 대 한 자세한 내용은 [사용자 지정 예약 페이지](customize-booking-page.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="54b7d-114">For more information about how to personalize and customize your booking page, see [Customize your booking page](customize-booking-page.md).</span></span>

## <a name="add-custom-questions-to-your-services"></a><span data-ttu-id="54b7d-115">서비스에 사용자 지정 질문 추가</span><span class="sxs-lookup"><span data-stu-id="54b7d-115">Add custom questions to your services</span></span>

1. <span data-ttu-id="54b7d-116">Microsoft 365에 로그인 하 고 **예약**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="54b7d-116">Sign in to Microsoft 365 and go to **Bookings**.</span></span>

1. <span data-ttu-id="54b7d-117">**서비스로** 이동 하 고 기존 서비스를 편집 하거나 **서비스를 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="54b7d-117">Go to **Services** and either edit an existing service or **Add a service**.</span></span>

1. <span data-ttu-id="54b7d-118">아래로 스크롤하여 **사용자 정의 필드** 섹션으로 스크롤한 다음 **수정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="54b7d-118">Scroll down to the **Custom fields** section, and then select **Modify**.</span></span>

   <span data-ttu-id="54b7d-119">고객 전자 메일, 전화 번호, 고객 주소 및 고객 메모와 같은 기본 고객 정보 관련 질문이 이미 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="54b7d-119">We already added some basic customer information questions: Customer email, phone number, customer address, and customer notes.</span></span> <span data-ttu-id="54b7d-120">처음으로이 작업을 수행 하면 고객 정보 질문이 회색으로 강조 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54b7d-120">The first time you do this, the customer information questions are highlighted in gray.</span></span> <span data-ttu-id="54b7d-121">즉, 사용자가이 질문을 보게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54b7d-121">That means that the user will see this question.</span></span> <span data-ttu-id="54b7d-122">이 질문을 선택 하면 주변의 강조 상자가 사라지고 고객에 게 질문을 요청 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="54b7d-122">If you select the question, the highlight box around it will disappear and your customer won't be asked that question.</span></span>

   <span data-ttu-id="54b7d-123">이 예에서는 전화 번호 및 고객 정보가 꺼지고 새로운 사용자 지정 질문 두 가지를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="54b7d-123">In this example, phone number and customer notes have been turned off and we created two new custom questions to ask.</span></span>

   ![사용자 지정 질문 화면 이미지](../media/bookings-questions-custom-fields.png)

1. <span data-ttu-id="54b7d-125">필요한 질문을 만들려면 **필수** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="54b7d-125">To make the question required, select the **Required** checkbox.</span></span> <span data-ttu-id="54b7d-126">고객은 필요한 질문에 대 한 답을 얻을 때까지 예약을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="54b7d-126">Your customer won't be able to complete the booking until they've answered the required questions.</span></span>

1. <span data-ttu-id="54b7d-127">사용자 지정 질문을 만들려면 패널 위쪽에서 **질문 추가** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="54b7d-127">To create a custom question, select **Add a question** from the top of the panel.</span></span> <span data-ttu-id="54b7d-128">질문을 작성 한 다음 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="54b7d-128">Write your question, and then select **Save**.</span></span>

1. <span data-ttu-id="54b7d-129">질문을 클릭 하 여 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="54b7d-129">Click on the question to enable it.</span></span> <span data-ttu-id="54b7d-130">강조 된 상자가 표시 되 고 해당 질문이 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54b7d-130">A highlighted box appears around it and the question is enabled.</span></span>

1. <span data-ttu-id="54b7d-131">페이지 맨 위에 있는 **확인** 을 클릭 한 다음 **서비스를 저장**합니다.</span><span class="sxs-lookup"><span data-stu-id="54b7d-131">Click **Ok** at the top of the page, and then **Save the service**.</span></span>

<span data-ttu-id="54b7d-132">예약을 수행 하면 모든 사용자 지정 질문이 마스터 목록에 저장 되므로 같은 질문을 반복 해 서 입력 하지 않고도 각 서비스에 질문을 쉽게 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54b7d-132">Bookings will save all of your custom questions in a master list so that you can easily add questions to each service without needing to repeatedly type the same questions.</span></span> <span data-ttu-id="54b7d-133">예를 들어 다른 서비스를 여는 경우 첫 번째 서비스에 대해 만든 질문이 사용자 정의 필드 섹션에 표시 되지만 wil는 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54b7d-133">For example, if you open a different service, the question you created for the first service will show in the Custom fields section, but it wil be disabled.</span></span> <span data-ttu-id="54b7d-134">강조 표시 된 사각형이 표시 되 고 질문이 사용 하도록 설정 되도록 질문을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="54b7d-134">Click the question so that a highlighted rectangle displays and the question is enabled.</span></span>

<span data-ttu-id="54b7d-135">이 예에서는 첫 번째 서비스에 대해 추가 된 질문을이 서비스에 사용할 수 있음을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54b7d-135">In this example, you can see that the questions that were added for the first service are available for this service.</span></span> <span data-ttu-id="54b7d-136">이 서비스에 대해 만드는 모든 질문을 모든 서비스에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54b7d-136">Any questions you create for this service will be available for all services.</span></span>

   ![여러 서비스에 대해 표시 되는 질문 이미지](../media/bookings-questions-services.png)

<span data-ttu-id="54b7d-138">예약 페이지를 이미 게시 한 경우에는 다른 작업을 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="54b7d-138">If your booking page is already published, you don't need to do anything else.</span></span> <span data-ttu-id="54b7d-139">고객은 다음에 질문을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54b7d-139">Customers will see the questions the next time they book with you.</span></span> <span data-ttu-id="54b7d-140">예약 페이지가 아직 게시 되지 않은 경우 웹용 Outlook의 **예약 페이지로** 이동한 후 **저장 및 게시**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="54b7d-140">If your booking page isn't published yet, go to the **booking page** from Outlook on the web, and then select **Save and publish**.</span></span>

> [!WARNING]
> <span data-ttu-id="54b7d-141">마스터 목록에서 질문을 삭제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54b7d-141">You can also delete questions from the master list.</span></span> <span data-ttu-id="54b7d-142">그러나 질문을 삭제 하면 모든 서비스에서 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54b7d-142">However, if you delete a question it will be deleted from every service.</span></span> <span data-ttu-id="54b7d-143">다른 서비스에는 영향을 주지 않도록이 질문을 선택 하 여 사용 하지 않도록 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="54b7d-143">We recommend that you disable the question by selecting it to ensure you do not impact any other services.</span></span> <span data-ttu-id="54b7d-144">강조 표시 된 사각형으로 둘러싸여 있지 않으면 질문이 비활성화 된 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54b7d-144">You can see that a question is disabled if it is not surrounded by a highlighted rectangle.</span></span>

## <a name="customer-experience"></a><span data-ttu-id="54b7d-145">고객 환경</span><span class="sxs-lookup"><span data-stu-id="54b7d-145">Customer experience</span></span>

<span data-ttu-id="54b7d-146">고객이 약속을 사용 하는 경우 기본 고객 정보 궁금한 **사항이 세부 정보 추가** 섹션에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54b7d-146">When your customers book an appointment with you, the basic customer information questions will show in the **Add your details** section.</span></span> <span data-ttu-id="54b7d-147">추가 하는 모든 사용자 지정 질문은 **추가 정보 제공** 섹션에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54b7d-147">Any customized questions you add will be in the **Provide additional information** section.</span></span>

![질문이 사용 되는 경우 고객이 보게 되는 항목의 이미지](../media/bookings-questions-customer.png)

## <a name="staff-experience"></a><span data-ttu-id="54b7d-149">직원 환경</span><span class="sxs-lookup"><span data-stu-id="54b7d-149">Staff experience</span></span>

<span data-ttu-id="54b7d-150">고객이 약속을 사용 하는 경우 직원은 예약 일정에 대 한 질문과 대답을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54b7d-150">When your customers book an appointment with you, your staff will see the questions and the customer's answers on the booking calendar.</span></span> <span data-ttu-id="54b7d-151">이를 확인 하려면 **예약** \> **일정** 으로 이동한 다음 약속을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="54b7d-151">To see it, go to **Bookings** \> **Calendar** and then open an appointment.</span></span>

![질문이 사용 하도록 설정 된 경우 직원에 게 표시 되는 항목의 이미지](../media/bookings-questions-staff.png)
