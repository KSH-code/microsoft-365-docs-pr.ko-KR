---
title: Microsoft Bookings에서 버퍼 시간 설정
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
ms.localizationpriority: medium
ms.assetid: 271f43e4-b8f7-4d63-8059-b5747679bb7e
description: Microsoft Bookings에서 약속 전후에 버퍼 시간을 설정하여 장비 정리 또는 초기화 시간을 허용합니다.
ms.openlocfilehash: c3d07be3c858eca5f6e9a672581b386625f5dd80
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60164047"
---
# <a name="set-buffer-time-in-microsoft-bookings"></a>Microsoft Bookings에서 버퍼 시간 설정

일부 약속은 고객과 만나기 전이나 후에 방 및 장비를 설정, 정리 또는 초기화하는 데 시간이 필요할 수 있습니다. 또는 고객 약속 사이를 이동하는 경우 고객과 팀이 고객이 기다리지 않고 약속을 이행할 수 있도록 보장하는 데 시간이 필요할 수 있습니다.

약속이 시작되기 전이나 약속이 종료된 후 또는 직원에게 다음 약속을 준비하는 데 필요한 추가 시간을 제공하려면 버퍼 시간을 설정할 수 있습니다.

## <a name="set-buffer-time-defaults"></a>버퍼 시간 기본값 설정

버퍼 시간 기본값은 Bookings의 서비스 세부 정보 페이지에서 설정됩니다.  이 페이지에 설정된 모든 서비스 기본값과 마찬가지로 특정 고객의 요구를 충족하기 위해 특정 예약에 대해 이러한 기본값을 편집할 수 있습니다.

버퍼 시간 설정은 서비스 세부  정보 페이지의 기본 기간 선택기 바로 아래에 **있습니다.** 특정 서비스에 대해 설정하려면 먼저 버퍼 시간 토글을 선택하여 버퍼 시간 설정을 사용하도록 설정해야 합니다. 이렇게 하면 다음과 같이 각 예약 전후에 보유할 기본 시간을 선택할 수 있는 **Before** 및 **After** 드롭다운이 표시됩니다.

   ![버퍼 시간이 사용하도록 설정된 Bookings 이미지입니다.](../media/bookings-buffertime.png)

## <a name="buffer-time-and-appointment-timing"></a>버퍼 시간 및 약속 타이밍

고객이 만나야 하는 시기에 대한 혼동을 방지하기 위해 Bookings는 일정과 관련 직원에게 전자 메일 확인 및 미리 알림에 버퍼 시간 및 실제 약속 시간(고객이 만나게 될 것으로 예상되는 시간)을 보여줍니다. 예를 들어 다음은 Bookings에서 약속 전 버퍼 시간이 15분인 고객의 약속에 대한 내용입니다.

이벤트 자체(아래 이미지의 왼쪽)는 버퍼 시간의 밝은 음영과 실제 고객 약속의 어두운 음영을 보여 둡니다. 약속 설명선(이벤트를 선택할 때 열리며)은 특히 Katie Jordan과의 약속이 오전 9시에서 10:00AM까지라고 구체적으로 설명하고 약속 전 버퍼 시간이 15분, 약속 후 0분을 포함합니다. 직원에 대한 확인 및 미리 알림은 고객이 9:00AM에서 10:00AM 약속 시간을 참조하는 확인 및 미리 알림만 받을 때 특정 버퍼 및 약속 시간을 비슷하게 참조합니다.

   ![버퍼 시간이 표시된 Bookings 약속 콜아웃 이미지](../media/bookings-buffertime-callout.png)

## <a name="buffer-time-and-availability"></a>버퍼 시간 및 가용성

고객이 직접 볼 수 없는 경우 설정한 버퍼 시간을 변경할 수 없습니다. 그러나 버퍼 시간을 사용하여 전체 서비스 기간을 계산하기 때문에 고객은 버퍼와 정기 약속 시간 모두에 예약된 사용자 및 관련 직원을 볼 수 있습니다. 또한 고객은 약속과 해당 버퍼 시간 모두에 충분한 시간이 있는 경우 사용자와 직원의 가용성만 볼 수 있습니다.

예를 들어 약속 전 버퍼 시간이 15분인 1시간 약속에는 최소 1시간 15분의 사용 가능한 시간 블록이 필요합니다. 따라서 이 서비스의 약속은 일정에서 75분 분의 시간 블록을 채우며 충돌 없이 예약할 수 있는 시간은 75분입니다.
