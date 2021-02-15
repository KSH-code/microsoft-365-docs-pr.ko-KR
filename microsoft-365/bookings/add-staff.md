---
title: Bookings에 직원 추가
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 298c529b-407b-4a2b-b2c5-6e77a9d1f07f
description: 이 페이지를 사용하여 직원 목록을 만들고 이름, 전화 번호 및 전자 메일 주소와 같은 직원 구성원 세부 정보를 관리할 수 있습니다.
ms.openlocfilehash: 11d62cc34522de21e63b8bdf6e7e15729ac73dc1
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/09/2020
ms.locfileid: "48399196"
---
# <a name="add-staff-to-bookings"></a>Bookings에 직원 추가

Bookings의 직원 페이지에서는 직원 목록을 만들고 이름, 전화 번호 및 전자 메일 주소와 같은 직원 구성원 세부 정보를 관리할 수 있습니다. 여기에서 각 직원 구성원에 대한 작업 시간을 설정할 수 있습니다.

## <a name="add-staff"></a>직원 추가

Bookings는 Microsoft 365의 기능지만 모든 직원에게 Microsoft 365 계정이 필요한 것은 아닙니다. 모든 직원은 예약을 받고 변경 내용을 예약할 수 있도록 유효한 전자 메일 주소가 있어야 합니다.

이 비디오를 시청하거나 아래 단계에 따라 직원을 추가하세요.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWuVka]

1. 직원 관리 [페이지로 이동하여](https://outlook.office.com/bookings/staff) 직원 **추가 선택**

2. 직원 **추가 단추를** 선택합니다.

3. 조직 내에서 직원을 추가할 때 사용자  추가 필드에 이름을 입력하고 드롭다운 메뉴에 표시될 때 해당 이름을 선택합니다. 다른 필드는 자동으로 채워집니다.

    직원 구성원이 추가된 후 이름 옆에 있는 **x를** 선택하고 사용자 추가 필드를 편집하여 모든 Bookings 통신에 나타나는 이름을 편집할 **수** 있습니다. 직원 구성원이 Adele Vance를 "Dr. Vance, MD"로 나열하는 등 고객에게 특정 직위 또는 이름을 표시하도록 하도록 하는 경우 유용할 수 있습니다.

4. 조직 외부의 직원을 추가하려면 전자 메일 및 기타 정보를 수동으로 입력합니다.

    > [!NOTE]
    > 테넌트 외부의 직원은 Bookings와 공유하지 못합니다.

5. 각 직원 구성원에 대해 관리자, 뷰어 또는 게스트 역할을 선택합니다.
    - **관리자는** 모든 설정을 편집하고, 직원을 추가 및 제거하고, 예약을 생성, 편집 또는 삭제할 수 있습니다.
    - **보기 권한을 통해** 일정의 모든 예약을 볼 수 있지만 수정하거나 삭제할 수 없습니다. 설정에 대한 읽기 전용 액세스 권한이 있습니다.
    - **게스트를** 예약에 할당할 수 있지만 예약 사서함을 열 수 없습니다.

6. 직원 **전자 메일을 사용하도록** 할당된 예약을 만들거나 변경할 때 전자 메일을 통해 모든 직원에게 알릴 수 있습니다. 다음은 전자 메일의 예입니다.

    :::image type="content" source="media/bookings-notify-all-email.jpg" alt-text="Bookings의 알림 전자 메일":::

7. **Office 365** 일정에서 이벤트를 선택하면 직원의 일정에서 약속이 있는/약속이 있는 정보가 Bookings를 통해 예약 서비스의 가용성에 영향을 미치게 하려는 경우 가용성에 영향을 미치게 됩니다.

    예를 들어 직원 구성원이 수요일에 오후 3시로 예정된 팀 모임 또는 개인 약속을 가지면 Bookings는 해당 시간 슬롯에 예약할 수 없음으로 직원 구성원을 표시합니다. 이 시간은 아래 예제와 같이 Bookings 달력 보기에서 약속이 있는 시간 또는 미정으로 표시됩니다.

    :::image type="content" source="media/bookings-busy-tentative-view.jpg" alt-text="Bookings 일정 보기":::

> [!IMPORTANT]
> 이중 예약을 방지하고 직원 구성원의 가용성을 최적화하기 위해 이 설정을 설정(기본적으로 켜져 있습니다)으로 두는 것이 좋습니다.

8. 비즈니스 **정보 페이지의** 업무 시간 섹션에서 설정한 업무 시간 내에만 직원 구성원의 모든 예약 가능 시간을 설정하려면 업무 시간을 선택합니다. 

    이 상자를 선택을 하여 직원에게 예약할 수 있는 시간을 추가로 제한하는 사용자 지정 시간을 부여할 수 있습니다. 이 정보는 직원 구성원이 사이트 화요일과 수요일에만 있을 수 있으며, 아침에는 한 유형의 약속과 다른 유형의 약속을 전담하는 시나리오에 유용합니다.

    > [!NOTE]
    > 서비스에 직원 구성원을 할당할 때 직원 페이지에 추가한 처음 31명 직원 구성원만 표시됩니다.
