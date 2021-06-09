---
title: 예약 페이지에 사용자 정의 및 필수 질문 추가
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: fd6b7587-5055-4bcd-83a4-13bd4929bfff
description: 고객이 온라인으로 약속을 예약할 때 고객에게 질문을 해야 하는 경우 예약 페이지에 사용자 지정 질문과 필요한 질문을 추가할 수 있습니다.
ms.openlocfilehash: ebbb07857fd8bb196f769dfb7e71ad25a85dfd54
ms.sourcegitcommit: 41fd71ec7175ea3b94f5d3ea1ae2c8fb8dc84227
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/09/2020
ms.locfileid: "47419993"
---
# <a name="add-custom-and-required-questions-to-the-booking-page"></a><span data-ttu-id="cbf6f-103">예약 페이지에 사용자 정의 및 필수 질문 추가</span><span class="sxs-lookup"><span data-stu-id="cbf6f-103">Add custom and required questions to the booking page</span></span>

<span data-ttu-id="cbf6f-104">예약을 사용하면 고객이 약속을 예약할 때 고객에게 질문할 수 있는 질문을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-104">Bookings lets you create questions to ask your customers when they are booking appointments.</span></span> <span data-ttu-id="cbf6f-105">또한 필요한 질문을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-105">It also lets you choose which questions are required.</span></span>

<span data-ttu-id="cbf6f-106">각 서비스에는 서로 다른 질문 집합이 있을 수 있도록 질문을 서비스에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-106">You associate the questions with a service, so each service can have a different set of questions.</span></span> <span data-ttu-id="cbf6f-107">예를 들어 헤어 스타일 목록은 헤어 컬러 약속을 예약하는 고객에게 알려진 분모가 있는 경우 표백이나 색조를 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-107">For example, a hair stylist may ask customers who are booking a hair coloring appointment if they have any known allergies to bleaches or tints.</span></span> <span data-ttu-id="cbf6f-108">이렇게 하면 고객과 고객이 약속을 위해 도착할 때 시간을 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-108">This allows you and your customers to save time when they arrive for their appointment.</span></span>

<span data-ttu-id="cbf6f-109">고객은 예약 페이지에서 약속을 만들 때 사용자 지정 질문을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-109">The customers will see the custom questions when they are creating their appointment on the booking page.</span></span> <span data-ttu-id="cbf6f-110">Bookings 일정에서 새 예약을 만들거나 기존 약속을 볼 때 직원은 사용자 지정 질문을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-110">Staff will see the custom questions when they create a new booking from the Bookings calendar or when viewing an existing appointment.</span></span> <span data-ttu-id="cbf6f-111">Bookings는 모든 서비스에 대해 동일한 질문을 다시 만들지 않는 마스터 목록에 모든 질문을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-111">Bookings saves all of your questions to a master list so that you don't have to re-create the same questions for every service.</span></span> <span data-ttu-id="cbf6f-112">질문이 필요한지 또는 선택 사항인지 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-112">You can also choose whether questions are required or optional.</span></span>

> [!NOTE]
> <span data-ttu-id="cbf6f-113">고객의 질문에 대한 대답은 예약 일정에서 약속을 볼 때 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-113">The customer's answers to the questions can be seen when you look at their appointment in the booking calendar.</span></span>

<span data-ttu-id="cbf6f-114">예약 페이지를 개인 설정하고 사용자 지정하는 방법에 대한 자세한 내용은 예약 페이지 사용자 [지정을 참조하세요.](customize-booking-page.md)</span><span class="sxs-lookup"><span data-stu-id="cbf6f-114">For more information about how to personalize and customize your booking page, see [Customize your booking page](customize-booking-page.md).</span></span>

## <a name="add-custom-questions-to-your-services"></a><span data-ttu-id="cbf6f-115">서비스에 사용자 지정 질문 추가</span><span class="sxs-lookup"><span data-stu-id="cbf6f-115">Add custom questions to your services</span></span>

1. <span data-ttu-id="cbf6f-116">로그인하여 Microsoft 365 **예약으로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="cbf6f-116">Sign in to Microsoft 365 and go to **Bookings**.</span></span>

1. <span data-ttu-id="cbf6f-117">서비스로 **이동하여** 기존 서비스를 편집하거나 서비스 **추가 를 편집합니다.**</span><span class="sxs-lookup"><span data-stu-id="cbf6f-117">Go to **Services** and either edit an existing service or **Add a service**.</span></span>

1. <span data-ttu-id="cbf6f-118">아래로 스크롤하여 사용자 정의 **필드 섹션으로** 이동한 다음 수정을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="cbf6f-118">Scroll down to the **Custom fields** section, and then select **Modify**.</span></span>

   <span data-ttu-id="cbf6f-119">고객 전자 메일, 전화 번호, 고객 주소 및 고객 메모와 같은 몇 가지 기본 고객 정보 질문이 이미 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-119">We already added some basic customer information questions: Customer email, phone number, customer address, and customer notes.</span></span> <span data-ttu-id="cbf6f-120">처음 이 작업을 할 때 고객 정보 질문이 회색으로 강조 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-120">The first time you do this, the customer information questions are highlighted in gray.</span></span> <span data-ttu-id="cbf6f-121">즉, 사용자에게 이 질문이 표시될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-121">That means that the user will see this question.</span></span> <span data-ttu-id="cbf6f-122">질문을 선택하면 주변의 강조 상자가 사라지고 고객에게 해당 질문이 제공되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-122">If you select the question, the highlight box around it will disappear and your customer won't be asked that question.</span></span>

   <span data-ttu-id="cbf6f-123">이 예에서는 전화 번호와 고객 메모가 꺼져 있으며 두 가지 새로운 사용자 지정 질문을 만들어 묻습니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-123">In this example, phone number and customer notes have been turned off and we created two new custom questions to ask.</span></span>

   ![사용자 지정 질문 화면의 이미지](../media/bookings-questions-custom-fields.png)

1. <span data-ttu-id="cbf6f-125">질문을 요구하려면 필수 **확인란을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-125">To make the question required, select the **Required** checkbox.</span></span> <span data-ttu-id="cbf6f-126">고객은 필요한 질문에 답변할 때까지 예약을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-126">Your customer won't be able to complete the booking until they've answered the required questions.</span></span>

1. <span data-ttu-id="cbf6f-127">사용자 지정 질문을 만들하려면 패널 위쪽에서 질문 추가를 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="cbf6f-127">To create a custom question, select **Add a question** from the top of the panel.</span></span> <span data-ttu-id="cbf6f-128">질문을 작성한 다음 저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="cbf6f-128">Write your question, and then select **Save**.</span></span>

1. <span data-ttu-id="cbf6f-129">질문을 클릭하여 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-129">Click on the question to enable it.</span></span> <span data-ttu-id="cbf6f-130">강조 표시된 상자가 주변에 나타나며 질문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-130">A highlighted box appears around it and the question is enabled.</span></span>

1. <span data-ttu-id="cbf6f-131">페이지 **위쪽에서** 확인을 클릭한 다음 서비스 **저장 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="cbf6f-131">Click **Ok** at the top of the page, and then **Save the service**.</span></span>

<span data-ttu-id="cbf6f-132">예약을 사용하면 마스터 목록에 모든 사용자 지정 질문이 저장됩니다. 따라서 동일한 질문을 반복해서 입력하지 않고도 각 서비스에 질문을 쉽게 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-132">Bookings will save all of your custom questions in a master list so that you can easily add questions to each service without needing to repeatedly type the same questions.</span></span> <span data-ttu-id="cbf6f-133">예를 들어 다른 서비스를 열면 첫 번째 서비스에 대해 만든 질문이 사용자 정의 필드 섹션에 표시되지만 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-133">For example, if you open a different service, the question you created for the first service will show in the Custom fields section, but it wil be disabled.</span></span> <span data-ttu-id="cbf6f-134">강조 표시된 사각형이 표시되어 질문을 사용하도록 설정하려면 질문을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-134">Click the question so that a highlighted rectangle displays and the question is enabled.</span></span>

<span data-ttu-id="cbf6f-135">이 예제에서는 첫 번째 서비스에 대해 추가된 질문을 이 서비스에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-135">In this example, you can see that the questions that were added for the first service are available for this service.</span></span> <span data-ttu-id="cbf6f-136">이 서비스에 대해 만든 질문은 모든 서비스에 대해 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-136">Any questions you create for this service will be available for all services.</span></span>

   ![여러 서비스에 대해 나타나는 질문 이미지](../media/bookings-questions-services.png)

<span data-ttu-id="cbf6f-138">예약 페이지가 이미 게시되어 있는 경우 다른 작업을 할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-138">If your booking page is already published, you don't need to do anything else.</span></span> <span data-ttu-id="cbf6f-139">고객은 다음에 예약할 때 질문을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-139">Customers will see the questions the next time they book with you.</span></span> <span data-ttu-id="cbf6f-140">예약 페이지가 아직 게시되지 않은 경우  웹의 Outlook 예약 페이지로 이동한 다음 저장 및 게시를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="cbf6f-140">If your booking page isn't published yet, go to the **booking page** from Outlook on the web, and then select **Save and publish**.</span></span>

> [!WARNING]
> <span data-ttu-id="cbf6f-141">마스터 목록에서 질문을 삭제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-141">You can also delete questions from the master list.</span></span> <span data-ttu-id="cbf6f-142">그러나 질문을 삭제하면 모든 서비스에서 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-142">However, if you delete a question it will be deleted from every service.</span></span> <span data-ttu-id="cbf6f-143">다른 서비스에 영향을 끼치지 않도록 선택하여 질문을 사용하지 않도록 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-143">We recommend that you disable the question by selecting it to ensure you do not impact any other services.</span></span> <span data-ttu-id="cbf6f-144">강조 표시된 직사각형으로 둘러싸인 질문이 사용되지 않는지 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-144">You can see that a question is disabled if it is not surrounded by a highlighted rectangle.</span></span>

## <a name="customer-experience"></a><span data-ttu-id="cbf6f-145">고객 경험</span><span class="sxs-lookup"><span data-stu-id="cbf6f-145">Customer experience</span></span>

<span data-ttu-id="cbf6f-146">고객이 약속을 예약하면 기본 고객 정보 질문이 세부 정보 추가 **섹션에** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-146">When your customers book an appointment with you, the basic customer information questions will show in the **Add your details** section.</span></span> <span data-ttu-id="cbf6f-147">추가하는 사용자 지정 질문은 추가 정보 제공 **섹션에 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="cbf6f-147">Any customized questions you add will be in the **Provide additional information** section.</span></span>

![질문이 활성화된 경우 고객에게 표시하는 이미지](../media/bookings-questions-customer.png)

## <a name="staff-experience"></a><span data-ttu-id="cbf6f-149">직원 환경</span><span class="sxs-lookup"><span data-stu-id="cbf6f-149">Staff experience</span></span>

<span data-ttu-id="cbf6f-150">고객이 약속을 예약하면 직원은 예약 일정에 대한 질문과 고객의 답변을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-150">When your customers book an appointment with you, your staff will see the questions and the customer's answers on the booking calendar.</span></span> <span data-ttu-id="cbf6f-151">이 확인을 위해 **Bookings Calendar(예약 일정)로** \> **이동한** 다음 약속을 여십시오.</span><span class="sxs-lookup"><span data-stu-id="cbf6f-151">To see it, go to **Bookings** \> **Calendar** and then open an appointment.</span></span>

![질문이 활성화된 경우 직원에게 표시하는 이미지](../media/bookings-questions-staff.png)
