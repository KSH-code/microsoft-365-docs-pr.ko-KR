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
ms.openlocfilehash: 5b9720492429a6a46be8f2701315ccd5b92e1bf6
ms.sourcegitcommit: c41e3f48451e2d7b45901faee21b1e1d19a16688
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2021
ms.locfileid: "58823880"
---
# <a name="define-your-service-offerings-in-bookings"></a>Bookings에서 서비스 제품 정의

Microsoft Bookings에서 서비스 서비스를 정의할 때 서비스 이름, 설명, 위치(대면 또는 온라인 모임 포함 여부 선택), 기간, 고객 및 직원에 대한 기본 미리 알림, 서비스에 대한 내부 메모 및 가격을 설정할 수 있습니다. 서비스를 제공할 자격이 있는 직원에 태그를 지정할 수도 있습니다. 그런 다음 고객이 약속을 예약하기 위해 비즈니스 웹 사이트로 들어오면 사용 가능한 약속 유형을 정확히 확인하여 서비스를 제공할 사람을 선택하고 서비스 비용을 선택할 수 있습니다.

다른 사람이 예약 페이지를 통해 서비스를 예약할 때 보내는 전자 메일 확인 및 미리 알림에 사용자 지정 정보 및 URL을 추가할 수도 있습니다.

## <a name="create-the-service-details"></a>서비스 세부 정보 만들기

1. 다음 Microsoft 365 앱 시작 프로그램을 선택한 다음 **Bookings 를 선택합니다.**

2. 서비스 **설정**  ->  [관리 페이지로 이동하고](https://outlook.office.com/bookings/settings/services) 새 서비스 **추가 를 선택합니다.**

3. 기본 **세부 정보 페이지에서** 선택 사항을 추가합니다.

**서비스 이름:** 서비스의 이름을 입력합니다. 일정 페이지의 드롭다운 메뉴에 나타나는 이름입니다. 이 이름은 모든 사용자가 일정 페이지에서 약속을 수동으로 추가할 때도 나타나며 셀프 서비스 페이지에 타일로 표시됩니다.

**설명:** 입력하는 설명은 셀프 서비스 페이지에서 정보 아이콘을 클릭할 때 표시됩니다.

**기본 위치:** 이 위치는 직원과 고객 모두의 확인 및 미리 알림 전자 메일에 표시되고 예약을 위해 만든 일정 이벤트에 표시됩니다.

**온라인 모임** 추가: 이 설정은 직원 구성원의 기본 클라이언트로 구성한 약속에 따라 Teams 또는 Skype 약속에 대해 온라인 모임을 사용 또는 사용하지 않도록 설정합니다.

    - 사용:

        - 예약에 고유한 Teams 또는 Skype 모임에 대한 링크가 전화 접속 정보와 함께 직원과 고객 일정의 일정 이벤트에 추가됩니다.
        - 다음 예와 같이 모임 참가 링크가 모든 확인 및 미리 알림 전자 메일에 추가됩니다.

        :::image type="content" source="media/bookings-teams-meeting-link.jpg" alt-text="Bookings에서 모임에 참가하는 Teams 예입니다.":::

        > [!NOTE]
        > Teams 모임은 Teams 모바일 앱, Teams 데스크톱 앱, 웹 브라우저 또는 전화 접속을 통해 참가할 수 있습니다. 가상 약속을 Teams 최상의 환경을 위해 테넌트의 기본 온라인 모임 서비스로 사용하도록 설정하는 것이 좋습니다.

    - 사용 안 하게:
        - 약속에는 모임 옵션이 포함되지 않을 뿐만 아니라 온라인 모임 추가를 사용하도록 설정한 경우 표시되는 모든 모임 관련 **필드가** 나타나지 않습니다.

**기간:** 모든 모임이 예약되는 기간입니다. 시간은 예약 중에 선택된 시작 시간부터 차단됩니다. 전체 약속 시간은 직원의 일정에서 차단됩니다.

**버퍼 시간:** 이 설정을 사용하도록 설정하면 약속을 예약할 때마다 직원의 일정에 추가 시간을 더할 수 있습니다.

    The time will be blocked on the staff’s calendar and impact free/busy information. This means if an appointment ends at 3:00 pm and 10 minutes of buffer time has been added to the end of the meeting, the staff’s calendar will show as busy and non-bookable until 3:10pm. This can be useful if your staff needs time before a meeting to prepare, such as a doctor reviewing a patient’s chart, or a financial advisor preparing relevant account information. It can also be useful after a meeting, such as when someone needs time to travel to another location.

**가격이 설정되지 않습니다.**  가격표 페이지에 표시할 가격 옵션을 Self-Service 선택합니다. 가격을 **설정하지 않은** 경우 가격이나 가격에 대한 참조가 나타나지 않습니다.

**참고** 이 필드는 예약된 직원의 예약 이벤트와 Bookings 웹앱의 일정 탭에 나타나는 이벤트에 표시됩니다.

**이벤트당 최대 참석자 수** 이 설정을 사용하면 여러 사용자가 동일한 약속 시간 및 동일한 직원(예: 피트니스 강의)을 예약할 수 있는 기능을 필요로 하는 서비스를 만들 수 있습니다. 선택한 서비스, 직원 및 시간의 약속 시간 슬롯은 지정된 최대 참석자 수에 도달할 때까지 예약할 수 있습니다. 현재 약속 용량 및 참석자도 Bookings 웹앱의 일정 탭에서 볼 수 있습니다.

    :::image type="content" source="media/bookings-maximum-attendees.jpg" alt-text="Example of setting maximum attendees in Bookings":::

**고객이 예약을** 관리하도록 합니다. 이 설정은 Bookings 웹앱의 일정 탭을 통해 예약이 예약된 경우 고객이 예약을 수정하거나 취소할 수 있는지 여부를 결정하는 설정입니다.

    - 사용:

        고객 **확인** 전자 메일에 예약 관리 단추가 표시됩니다. 고객이 이 단추를 선택하면 다음 세 가지 옵션이 표시됩니다.
        - **Reschedule** 이 옵션을 선택하면 사용자는 서비스별 Self-Service 페이지로 이동하여 원래 예약에서 동일한 서비스 및 동일한 직원 구성원에 대한 새 시간 및/또는 날짜를 선택할 수 있습니다. 원래 직원 구성원은 기본적으로 다시 예약된 예약에 연결되어 있는 경우에도 직원 구성원을 변경할 수 있습니다.
        - **예약 취소** 그러면 예약이 취소되고 직원의 일정에서 예약이 제거됩니다.
        - **새 예약** 이 옵션을 사용하면 새 예약을 예약할 Self-Service 모든 서비스 및 직원이 나열된 Self-Service 페이지로 이동됩니다.

        :::image type="content" source="media/bookings-manage-booking-button.jpg" alt-text="Bookings의 예약 관리 단추입니다.":::

        고객이 앱 페이지에 액세스하는 데 편한 경우 이 설정을 사용하도록 설정한 Self-Service 좋습니다.

    - 사용 안 하게:

        예약 웹앱의 일정 탭을 통해 예약할 때 예약을 다시 예약하거나 취소할 수 없습니다. 그러나 Self-Service 페이지를 통해 예약할 경우 이 설정을  사용하지 않도록 설정한 경우에도 고객은 예약 관리 단추와 모든 옵션을 사용할 수 있습니다.

        웹 페이지로의 액세스를 제한하려는 경우 이 설정을 Self-Service 좋습니다. 또한 고객이 사무실에 전화하거나 지원 센터에 전자 메일을 보내거나 전화를 걸거나 다른 방법을 통해 예약을 변경하는 방법을 고객에게 알리는 확인 및 미리 알림 전자 메일에 텍스트를 추가하는 것이 제안됩니다.

4. 가용성 **옵션 페이지에서** 예약 페이지에서 직원의 일정 정책  및 가용성에 대해 선택한 옵션을 볼 수 있습니다. 자세한 내용은 [Set your scheduling policies 을 참조하십시오.](set-scheduling-policies.md)

    :::image type="content" source="media/bookings-maximum-attendees.jpg" alt-text="Bookings에서 최대 참석자 수를 설정하는 예제입니다.":::

10. **기본 가격**  이 가격은 Self-Service 표시됩니다. 가격을 **설정하지 않은** 경우 가격이나 가격에 대한 참조가 나타나지 않습니다.

11. **참고** 이 필드는 예약된 직원의 예약 이벤트와 Bookings 웹앱의 일정 탭에 나타나는 이벤트에 표시됩니다.

6. **사용자 정의 필드는** 특정 약속을 예약할 때마다 필요한 정보를 수집할 때 유용할 수 있습니다. 예로는 대학 방문 전 보험 업체, 대출 상담을 위한 대출 유형, 교육 관련 전공 연구 또는 후보자 면접을 위한 신입사원 ID가 있습니다. 이러한 필드는 고객이 사용자 및 직원과의 약속을 예약할 때 예약 페이지에 표시됩니다.

    - 고객 전자 메일, 전화 번호, 주소 및 메모는 이동식 필드가 아닌 필드이지만  각 필드 옆에 있는 필수를 선택을 선택하지 않은 경우 선택 사항으로 만들 수 있습니다.

7. 미리 **알림 및 확인 페이지에서** 보내는 미리 알림 및 알림을 설정할 수 있습니다. 약속 전에 지정된 시간 동안 고객, 직원 구성원 또는 둘 다에게 미리 알림 및 알림이 전송됩니다. 기본 설정에 따라 각 약속에 대해 여러 메시지를 만들 수 있습니다.

        :::image type="content" source="media/bookings-remind-confirm.jpg" alt-text="A confirmation email from Bookings.":::

    - 예약에 대한 정보나 고객이 약속을 위해 가져와야 하는 텍스트 등 원하는 추가 텍스트를 여기에 포함할 수 있습니다. 다음은 전자 메일 확인에 대한 추가 정보 필드에 있는 원래 확인 전자 메일에 추가된 사용자 지정 **텍스트의 예입니다.**

        :::image type="content" source="media/bookings-additional-info.jpg" alt-text="Bookings 전자 메일의 추가 정보입니다.":::

8. **고객에 대해 문자 메시지 알림 사용** 이 옵션을 선택하면 SMS 메시지가 고객에게 전송되지만 옵트인(opt in)하는 경우만 고객에게 전송됩니다.

    - 수동 예약 및 예약 페이지의 옵트인 Self-Service:

        :::image type="content" source="media/bookings-opt-In-boc.jpg" alt-text="Bookings의 옵트인 상자입니다.":::

    - 문자 메시지 알림은 다음과 같습니다(SMS 알림은 현재 북미에서만 사용할 수 있습니다).

        :::image type="content" source="media/bookings-text-notifications.jpg" alt-text="Bookings의 텍스트 알림입니다.":::

9. 기본 **설정 옵션은** 기본적으로 설정되어 있습니다. 고객이 특정 직원 구성원을 예약하는 방법을 사용자 지정하려는 경우 토글을 해제합니다.

10. **게시 옵션** 이 서비스를 예약 가능으로 Self-Service 또는 Bookings 웹앱의 일정 탭에서만 서비스를 예약할 수 있도록 할지 선택합니다.
