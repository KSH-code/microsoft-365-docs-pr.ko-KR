---
title: Bookings에서 서비스 제품 정의
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 4a1c391e-524f-48e0-bef8-185df3a9634b
description: 서비스 이름, 설명, 위치, 기간 및 가격을 비롯한 서비스 제품 정보를 입력하기 위한 지침입니다. 서비스를 제공할 자격이 있는 직원에 태그를 지정할 수도 있습니다.
ms.openlocfilehash: 095188546c01149a793a478a3cbd5ac9fbeb5524
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962540"
---
# <a name="define-your-service-offerings-in-bookings"></a><span data-ttu-id="50d52-104">Bookings에서 서비스 제품 정의</span><span class="sxs-lookup"><span data-stu-id="50d52-104">Define your service offerings in Bookings</span></span>

<span data-ttu-id="50d52-105">Microsoft Bookings에서 서비스 서비스를 정의할 때 서비스 이름, 설명, 위치(대면 또는 온라인 모임 포함 여부 선택), 기간, 고객 및 직원에 대한 기본 미리 알림, 서비스에 대한 내부 메모 및 가격을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-105">When you define your service offerings in Microsoft Bookings, you set, a service name, description, location (choose whether you want to meet in person or have an online meeting), duration, default reminders to customers and staff, internal notes about the service, and pricing.</span></span> <span data-ttu-id="50d52-106">서비스를 제공할 자격이 있는 직원에 태그를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-106">You can also tag the employees who are qualified to provide the service.</span></span> <span data-ttu-id="50d52-107">그런 다음 고객이 약속을 예약하기 위해 비즈니스 웹 사이트로 들어오면 사용 가능한 약속 유형을 정확히 확인하여 서비스를 제공할 사람을 선택하고 서비스 비용을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-107">Then, when customers come to your business web site to book an appointment, they can see exactly what types of appointments are available, choose the person they want to provide the service, and how much their service will cost.</span></span>

<span data-ttu-id="50d52-108">다른 사람이 예약 페이지를 통해 서비스를 예약할 때 보내는 전자 메일 확인 및 미리 알림에 사용자 지정 정보 및 URL을 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-108">You can also add customized information and URLs to the email confirmation and reminders that you send when someone books a service through your booking page.</span></span>

## <a name="create-the-service-details"></a><span data-ttu-id="50d52-109">서비스 세부 정보 만들기</span><span class="sxs-lookup"><span data-stu-id="50d52-109">Create the service details</span></span>

1. <span data-ttu-id="50d52-110">서비스 관리 [페이지로 이동하여](https://outlook.office.com/bookings/services) 서비스 **추가 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="50d52-110">Go to the [Manage services page](https://outlook.office.com/bookings/services) and select **Add a service**.</span></span>

2. <span data-ttu-id="50d52-111">**서비스 이름:** 서비스의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-111">**Service name**: enter the name of your service.</span></span> <span data-ttu-id="50d52-112">일정 페이지의 드롭다운 메뉴에 나타나는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-112">This is the name that will appear in the drop-down menu on the Calendar page.</span></span> <span data-ttu-id="50d52-113">이 이름은 모든 사용자가 일정 페이지에서 약속을 수동으로 추가할 때도 나타나며 셀프 서비스 페이지에 타일로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-113">This name will also appear when anyone manually adds an appointment on the Calendar page, and it will appear as a tile on the Self-service page.</span></span>

3. <span data-ttu-id="50d52-114">**설명:** 입력하는 설명은 셀프 서비스 페이지에서 정보 아이콘을 클릭할 때 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-114">**Description**: The description you enter is what will appear when a user clicks the information icon on the Self-service page.</span></span>

4. <span data-ttu-id="50d52-115">**기본 위치:** 이 위치는 직원과 고객 모두의 확인 및 미리 알림 전자 메일에 표시되고 예약을 위해 만든 일정 이벤트에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-115">**Default location**: This location is what will be displayed on confirmation and reminder emails for both staff and customers, and it will be displayed on the calendar event created for the booking.</span></span>

5. <span data-ttu-id="50d52-116">**온라인 모임** 추가: 이 설정은 직원 구성원의 기본 클라이언트로 구성한 약속에 따라 Teams 또는 Skype 약속에 대해 온라인 모임을 사용 또는 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-116">**Add online meeting**: This setting enables or disables online meetings for each appointment, either via Teams or Skype, depending on which one you configure as the default client for the staff member.</span></span>

    - <span data-ttu-id="50d52-117">사용:</span><span class="sxs-lookup"><span data-stu-id="50d52-117">Enabled:</span></span>

        - <span data-ttu-id="50d52-118">예약에 고유한 Teams 또는 Skype 모임에 대한 링크가 전화 접속 정보와 함께 직원과 고객 일정의 일정 이벤트에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-118">A link to a Teams or Skype meeting, unique to the booking, will be added to the calendar event on both the staff's and the customers' calendars, along with dial-in information.</span></span>
        - <span data-ttu-id="50d52-119">다음 예와 같이 모임 참가 링크가 모든 확인 및 미리 알림 전자 메일에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-119">The link to join the meeting will be added to all confirmation and reminder emails, as shown in the following example:</span></span>

        :::image type="content" source="media/bookings-teams-meeting-link.jpg" alt-text="Bookings에서 Teams 모임에 참가하기 위한 링크의 예":::

        > [!NOTE]
        > <span data-ttu-id="50d52-121">Teams 모임은 Teams 모바일 앱, Teams 데스크톱 앱, 웹 브라우저 또는 전화 접속을 통해 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-121">Teams meetings can be joined via the Teams mobile app, the Teams desktop app, in a Web browser, or via the phone dial-in.</span></span> <span data-ttu-id="50d52-122">가상 약속을 Teams 최상의 환경을 위해 테넌트의 기본 온라인 모임 서비스로 사용하도록 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-122">We strongly recommend enabling Teams as the default online meeting service for your tenant, for the best experience booking virtual appointments.</span></span>

    - <span data-ttu-id="50d52-123">사용 안 하게:</span><span class="sxs-lookup"><span data-stu-id="50d52-123">Disabled:</span></span>
        - <span data-ttu-id="50d52-124">약속에는 모임 옵션이 포함되지 않을 뿐만 아니라 온라인 모임 추가를 사용하도록 설정한 경우 표시되는 모든 모임 관련 **필드가** 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-124">Appointments will not contain a meeting option, and all of the meeting-related fields that appear when **Add online meeting** is enabled will not be shown.</span></span>

6. <span data-ttu-id="50d52-125">**기본 기간:** 모든 모임이 예약되는 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-125">**Default duration**: This is how long all meetings will be booked for.</span></span> <span data-ttu-id="50d52-126">시간은 예약 중에 선택된 시작 시간부터 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-126">The time is blocked beginning from the start time, which is selected during booking.</span></span> <span data-ttu-id="50d52-127">전체 약속 시간은 직원의 일정에서 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-127">The full appointment time will be blocked on the staff's calendars.</span></span>

7. <span data-ttu-id="50d52-128">**고객이 예약할** 수 없는 버퍼 시간: 이 설정을 사용하도록 설정하면 약속을 예약할 때마다 직원의 일정에 추가 시간을 더할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-128">**Buffer time your customer can’t book**: Enabling this setting allows for the addition of extra time to the staff’s calendar every time an appointment is booked.</span></span>

    <span data-ttu-id="50d52-129">시간은 직원의 일정에 차단된 후 약속이 있는/약속이 있는 정보에 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-129">The time will be blocked on the staff’s calendar and impact free/busy information.</span></span> <span data-ttu-id="50d52-130">즉, 약속이 오후 3시에 끝나고 10분의 버퍼 시간이 모임 종료에 추가된 경우 직원의 일정은 오후 3시 10분까지 약속이 없는 다른 일정으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-130">This means if an appointment ends at 3:00 pm and 10 minutes of buffer time has been added to the end of the meeting, the staff’s calendar will show as busy and non-bookable until 3:10pm.</span></span> <span data-ttu-id="50d52-131">이 기능은 환자 차트를 검토하는 의사나 관련 계정 정보를 준비하는 재무 고문과 같이 직원이 모임을 준비하기 전에 시간이 필요한 경우 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-131">This can be useful if your staff needs time before a meeting to prepare, such as a doctor reviewing a patient’s chart, or a financial advisor preparing relevant account information.</span></span> <span data-ttu-id="50d52-132">누군가가 다른 위치로 이동해야 하는 경우와 같이 모임 후에도 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-132">It can also be useful after a meeting, such as when someone needs time to travel to another location.</span></span>

8. <span data-ttu-id="50d52-133">**고객이 예약을** 관리하도록 합니다. 이 설정은 Bookings 웹앱의 일정 탭을 통해 예약이 예약된 경우 고객이 예약을 수정하거나 취소할 수 있는지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-133">**Let the customer manage their booking**: This setting determines whether or notthe customer can modify or cancel their booking, provided it was booked through the Calendar tab on the Bookings Web app.</span></span>

    - <span data-ttu-id="50d52-134">사용:</span><span class="sxs-lookup"><span data-stu-id="50d52-134">Enabled:</span></span>

        <span data-ttu-id="50d52-135">고객 **확인** 전자 메일에 예약 관리 단추가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-135">The **Manage Booking** button appears on the customer confirmation email.</span></span> <span data-ttu-id="50d52-136">고객이 이 단추를 선택하면 다음 세 가지 옵션이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-136">When this button is selected by the customer, three options appear:</span></span>
        - <span data-ttu-id="50d52-137">**Reschedule** 이 옵션을 선택하면 사용자는 서비스별 Self-Service 페이지로 이동하여 원래 예약에서 동일한 서비스 및 동일한 직원 구성원에 대한 새 시간 및/또는 날짜를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-137">**Reschedule** Selecting this option brings the user to a service-specific Self-Service page, where they can select a new time and/or date for the same service and same staff member from the original booking.</span></span> <span data-ttu-id="50d52-138">원래 직원 구성원은 기본적으로 다시 예약된 예약에 연결되어 있는 경우에도 직원 구성원을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-138">Note that even though the original staff member is attached to the rescheduled booking by default, the user does have the option of changing the staff member as well.</span></span>
        - <span data-ttu-id="50d52-139">**예약 취소** 그러면 예약이 취소되고 직원의 일정에서 예약이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-139">**Cancel booking** This cancels the booking and removes it from the staff's calendar.</span></span>
        - <span data-ttu-id="50d52-140">**새 예약** 이 옵션을 사용하면 새 예약을 예약할 Self-Service 모든 서비스 및 직원이 나열된 Self-Service 페이지로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-140">**New booking** This option brings the user to the Self-Service page with all services and staff listed, for scheduling a new booking.</span></span>

        :::image type="content" source="media/bookings-manage-booking-button.jpg" alt-text="Bookings의 예약 관리 단추":::

        <span data-ttu-id="50d52-142">고객이 앱 페이지에 액세스하는 데 편한 경우 이 설정을 사용하도록 설정한 Self-Service 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-142">We only recommend leaving this setting enabled if you are comfortable with customers accessing the Self-Service page.</span></span>

    - <span data-ttu-id="50d52-143">사용 안 하게:</span><span class="sxs-lookup"><span data-stu-id="50d52-143">Disabled:</span></span>

        <span data-ttu-id="50d52-144">예약 웹앱의 일정 탭을 통해 예약할 때 예약을 다시 예약하거나 취소할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-144">The user will have no ability to reschedule or cancel their booking when they book through the Calendar tab on the Bookings Web app.</span></span> <span data-ttu-id="50d52-145">그러나 Self-Service 페이지를 통해 예약할 경우 이 설정을  사용하지 않도록 설정한 경우에도 고객은 예약 관리 단추와 모든 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-145">When booking through the Self-Service page, however, customers will still have the **Manage Booking** button and all of its options, even when this setting is disabled.</span></span>

        <span data-ttu-id="50d52-146">웹 페이지로의 액세스를 제한하려는 경우 이 설정을 Self-Service 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-146">We recommend disabling this setting if you want to limit access to the Self-Service page.</span></span> <span data-ttu-id="50d52-147">또한 고객이 사무실에 전화하거나 지원 센터에 전자 메일을 보내거나 전화를 걸거나 다른 방법을 통해 예약을 변경하는 방법을 고객에게 알리는 확인 및 미리 알림 전자 메일에 텍스트를 추가하는 것이 제안됩니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-147">Additionally, we suggest adding text to your confirmation and reminder emails that tells your customers how to make changes to their booking through other means, such as by calling the office or emailing the help desk.</span></span>

9. <span data-ttu-id="50d52-148">**이벤트당 최대 참석자 수** 이 설정을 사용하면 여러 사용자가 동일한 약속 시간 및 동일한 직원(예: 피트니스 강의)을 예약할 수 있는 기능을 필요로 하는 서비스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-148">**Maximum attendees per event** This setting allows you to create services that require the ability for multiple people to book the same appointment time and the same staff (such as a fitness class).</span></span> <span data-ttu-id="50d52-149">선택한 서비스, 직원 및 시간의 약속 시간 슬롯은 지정된 최대 참석자 수에 도달할 때까지 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-149">The appointment time slot for the selected service, staff, and time will be available to book until the maximum number of attendees, specified by you, has been reached.</span></span> <span data-ttu-id="50d52-150">현재 약속 용량 및 참석자도 Bookings 웹앱의 일정 탭에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-150">Current appointment capacity and attendees can be viewed in the Calendar tab in the Bookings Web app.</span></span>

    :::image type="content" source="media/bookings-maximum-attendees.jpg" alt-text="Bookings에서 최대 참석자 수를 설정하는 예제":::

10. <span data-ttu-id="50d52-152">**기본 가격**  이 가격은 Self-Service 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-152">**Default price**  This is the price that will display on the Self-Service page.</span></span> <span data-ttu-id="50d52-153">가격을 **설정하지 않은** 경우 가격이나 가격에 대한 참조가 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-153">If **Price not set** is selected, then no price or reference to cost or pricing will appear.</span></span>

11. <span data-ttu-id="50d52-154">**참고** 이 필드는 예약된 직원의 예약 이벤트와 Bookings 웹앱의 일정 탭에 나타나는 이벤트에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-154">**Notes** This field appears in the booking event for booked staff, as well as on the event that appears on the Calendar tab in the Bookings web app.</span></span>

12. <span data-ttu-id="50d52-155">**사용자 정의 필드** 이 섹션에서는 고객이 성공적으로 예약하기 위해 답변해야 하는 경우 질문을 추가하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-155">**Custom Fields** This section allows questions to be added, or removed, if the customer needs to answer any in order to successfully book.</span></span>

    - <span data-ttu-id="50d52-156">고객 전자 메일, 전화 번호, 주소 및 메모는 이동식 필드가 아닌 필드이지만  각 필드 옆에 있는 필수를 선택을 선택하지 않은 경우 선택 사항으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-156">Customer email, phone number, address, and notes are non-removable fields, but you can make them optional by deselecting **Required** beside each field.</span></span>

    - <span data-ttu-id="50d52-157">질문 추가 를 선택하여 여러 선택 또는 텍스트 응답 질문을 **추가할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="50d52-157">You can add a multiple choice or text-response question by selecting **Add a question**.</span></span>

        <span data-ttu-id="50d52-158">사용자 정의 필드는 특정 약속을 예약할 때마다 필요한 정보를 수집할 때 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-158">Custom fields can be useful when collecting information that is needed every time the specific appointment is booked.</span></span> <span data-ttu-id="50d52-159">예로는 대학 방문 전 보험 업체, 대출 상담을 위한 대출 유형, 교육 관련 전공 연구 또는 후보자 면접을 위한 신입사원 ID가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-159">Examples include insurance provider prior to a clinic visit, loan type for loan consultations, major of study for academic advising, or applicant ID for candidate interviews.</span></span>

13. <span data-ttu-id="50d52-160">**미리 알림 및 확인** 두 유형의 전자 메일은 모두 지정된 기간에 고객, 직원 구성원 또는 둘 다에게 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-160">**Reminders and Confirmations** Both types of emails are sent out to customers, staff members, or both, at a specified time period before the appointment.</span></span> <span data-ttu-id="50d52-161">기본 설정에 따라 각 약속에 대해 여러 메시지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-161">Multiple messages can be created for each appointment, according to your preference.</span></span>

    - <span data-ttu-id="50d52-162">기본 확인 및 미리 알림 전자 메일에는 고객/클라이언트 이름, 직원 구성원 이름, 예약된 서비스 또는 약속 시간, 약속 시간 등 약속에 대한 기본 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-162">The default confirmation and reminder emails include basic information about the appointment, such as the customer/client name, staff member's name, the service or appointment booked, and the time of the appointment.</span></span> <span data-ttu-id="50d52-163">온라인 모임의 경우 참가 링크도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-163">For online meetings, a link to join will also be included.</span></span> <span data-ttu-id="50d52-164">이 설정을 사용하도록 설정한 경우(8단계에서 설명한 대로) 예약 관리 기능을 포함될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-164">The ability to manage the booking can also be included, if this setting is enabled (as described above in step 8).</span></span>

        :::image type="content" source="media/bookings-remind-confirm.jpg" alt-text="Bookings의 확인 전자 메일":::

    - <span data-ttu-id="50d52-166">원하는 추가 텍스트(예: 예약에 대한 정보 또는 고객이 약속을 위해 가져와야 하는 텍스트)를 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-166">Optionally, you can include any additional text you would like here, such as information about rescheduling or what customers should bring for the appointment.</span></span> <span data-ttu-id="50d52-167">다음은 전자 메일 확인에 대한 추가 정보 필드에 있는 원래 확인 전자 메일에 추가된 사용자 지정 **텍스트의 예입니다.**</span><span class="sxs-lookup"><span data-stu-id="50d52-167">The following is an example of customized text added to the original confirmation email, seen in the **Additional information for Email Confirmation** field:</span></span>

        :::image type="content" source="media/bookings-additional-info.jpg" alt-text="Bookings 전자 메일의 추가 정보":::

14. <span data-ttu-id="50d52-169">**고객에 대해 문자 메시지 알림 사용** 선택한 SMS 메시지가 고객에게 전송되지만 옵트인(opt in)하는 경우만 고객에게 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-169">**Enable text message notifications for your customer** If selected, SMS messages are sent to the customer, but only if they opt-in.</span></span>

    - <span data-ttu-id="50d52-170">수동 예약 및 예약 페이지의 옵트인 Self-Service:</span><span class="sxs-lookup"><span data-stu-id="50d52-170">Opt-in box on the manual booking and Self-Service Page:</span></span>

        :::image type="content" source="media/bookings-opt-In-boc.jpg" alt-text="Bookings의 옵트인 상자":::

    - <span data-ttu-id="50d52-172">문자 메시지 알림은 다음과 같이 표시됩니다(SMS 알림은 현재 북미에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-172">Text message notifications will look like the following (note that SMS notifications are currently only available in North America):</span></span>

        :::image type="content" source="media/bookings-text-notifications.jpg" alt-text="Bookings의 텍스트 알림":::

15. <span data-ttu-id="50d52-174">**게시 옵션** 이 서비스를 예약 가능으로 Self-Service 또는 Bookings 웹앱의 일정 탭에서만 서비스를 예약할 수 있도록 할지 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-174">**Publishing options** Choose whether to have this service appear as bookable on the Self-Service page, or to make the service bookable only on the Calendar tab within the Bookings Web app.</span></span>

16. <span data-ttu-id="50d52-175">**Scheduling Policy** 이 설정은 약속 시간을 보는 방법과 예약을 만들거나 취소할 수 있는 기간을 결정하는 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-175">**Scheduling Policy** This setting determines how appointment times are viewed, and the time period in which bookings can be made or cancelled.</span></span>

17. <span data-ttu-id="50d52-176">**전자 메일 알림** 조직 직원과 고객 또는 클라이언트에게 전자 메일을 보낼 때를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-176">**Email notifications** Sets when emails are sent to organization staff and to customers or clients.</span></span>

18. <span data-ttu-id="50d52-177">**직원** 이 확인란을 선택하면 고객 또는 클라이언트가 약속에 대한 특정 직원 구성원을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-177">**Staff** Selecting this checkbox allows customers or clients to choose a specific staff member for their appointment.</span></span>

    - <span data-ttu-id="50d52-178">사용:</span><span class="sxs-lookup"><span data-stu-id="50d52-178">Enabled:</span></span>

        <span data-ttu-id="50d52-179">고객은 예약 페이지에서 예약할 때 약속에 할당된 모든 직원 Self-Service 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-179">Customers can choose from all staff assigned to the appointment when booking on the Self-Service page.</span></span> <span data-ttu-id="50d52-180">모든 사용자 옵션을  선택하면 Bookings에서 임의로 약속에 할당할 수 있는 직원 구성원을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-180">Selecting the option of **Anyone** will make Bookings choose an available staff member at random to assign to the appointment.</span></span>

    - <span data-ttu-id="50d52-181">사용 안 하게:</span><span class="sxs-lookup"><span data-stu-id="50d52-181">Disabled:</span></span>

        <span data-ttu-id="50d52-182">Self-Service 페이지를 통해 예약하는 고객은 서비스 및 시간 및 날짜를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-182">Customers booking via the Self-Service page can select a service and a time and date.</span></span> <span data-ttu-id="50d52-183">사용 가능한 직원은 임의로 예약됩니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-183">The available staff will be booked at random.</span></span> <span data-ttu-id="50d52-184">Bookings 웹앱의 일정 탭을 통해 예약할 경우 특정 직원을 계속 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-184">Note that specific staff can still be selected when booked through the Calendar tab in the Bookings Web app.</span></span>

19. <span data-ttu-id="50d52-185">**가용성** 다음 옵션에 따라 서비스를 예약할 수 있는 경우가 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-185">**Availability** The following options determine when the service can be booked:</span></span>

    - <span data-ttu-id="50d52-186">**직원이 무료인 경우 예약 가능** 이 서비스는 추가 시간 제한 없이 직원이 업무 시간 내에 무료인 경우를 기준으로 가용성을 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-186">**Bookable when staff are free** The service maintains availability based on when staff are free within business hours, with no extra time restrictions.</span></span>

    - <span data-ttu-id="50d52-187">**사용자 지정 시간(매주 재발)** 이 서비스에는 업무 시간 또는 직원 시간으로 제한하는 것 외에 추가로 제한될 수 있는 가용성 계층이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-187">**Custom hours (recurring weekly)** The service has an added layer of availability that can be further restricted (in addition to restricting by business hours or with staff hours).</span></span> <span data-ttu-id="50d52-188">서비스를 특정 시기에만 제공하거나 수행할 수 있는 경우 이 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-188">Use this option when your service can only be provided or performed at a specific time.</span></span>

    - <span data-ttu-id="50d52-189">**날짜 범위에 대해 다른 가용성 설정** 이 설정은 특정 시점의 가용성에 영향을 주며, 이 경우 일정한 기준이 아닌 경우에 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-189">**Set different availability for a date range** This setting impacts availability at a specific point in time, instead of a recurring basis.</span></span> <span data-ttu-id="50d52-190">예를 들어 서비스에 필요한 컴퓨터의 서비스가 일시적으로 제공되고 사용할 수 없는 경우나 휴일에 조직을 닫을 때 이 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-190">For example, this could be used when a machine that is needed for the service is temporarily being serviced and unavailable, or when an organization is closed for a holiday.</span></span>

20. <span data-ttu-id="50d52-191">**직원 할당** 해당 특정 서비스에 대해 예약할 수 있는 직원(직원 탭에 직원 구성원을 추가한 경우)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-191">**Assign Staff** Select the staff (provided you have added staff members to the Staff tab) who will be bookable for that specific service.</span></span> <span data-ttu-id="50d52-192">개별 직원을 선택하지 않은 경우 모든 직원이 서비스에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="50d52-192">Selecting no individual staff will result in all staff being assigned to the service.</span></span>