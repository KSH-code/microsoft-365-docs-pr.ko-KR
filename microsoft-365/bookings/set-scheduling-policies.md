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
description: 비즈니스에 대한 계획 정책을 설정하는 방법을 배워야 합니다. 예약 정책에는 약속의 길이뿐만 아니라 허용 가능한 잠재 고객 및 취소 시간도 포함됩니다.
ms.openlocfilehash: 82cc9a66e82665040a1f0d08635cae10cd413d4b
ms.sourcegitcommit: 41fd71ec7175ea3b94f5d3ea1ae2c8fb8dc84227
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/09/2020
ms.locfileid: "47419923"
---
# <a name="set-your-scheduling-policies"></a>예약 정책 설정

모든 약속이 동일하지는 않습니다. 일부는 몇 분 정도 걸릴 수 있는 반면 다른 일부는 몇 시간 이상 걸릴 수 있습니다. Microsoft Bookings에서 예약 페이지는 비즈니스에 대한 예약 정책을 설정하는 위치입니다. 예약 정책에는 약속의 길이, 허용 가능한 잠재 고객 및 취소 시간, 예약 변경에 대한 자동 알림이 포함됩니다. 서비스 페이지 내의 각 서비스에 대해 추가 사용자 지정을 추가할 수 있으며 해당 서비스에만 적용되는 추가 기간 설정 및 정책이 있습니다.

여기서 설정하는 정책은 최상위 정책입니다. 서비스 기준에 따라 수정하기로 선택하지 않는 한 제공한 모든 서비스에 자동으로 적용됩니다. 예를 들어 초기 컨설팅과 같은 대부분의 서비스의 경우 취소에 대한 1일 알림이 허용됩니다. 하지만 시설 예약 또는 요금(예: 수업 수업)이 필요한 서비스의 경우 3일 알림이 필요할 수 있습니다. 서비스 페이지에서 이 서비스 수준 정책을 설정할 수 있습니다. 지침은 [서비스 제품 정의를](define-service-offerings.md) 참조하세요.

## <a name="types-of-scheduling-policies"></a>정책의 유형

이 표에서는 예약 페이지에서 사용할 수 있는 다양한 예약 정책에 대해 설명하고 있습니다.

| 정책 | 설명 |
|---|---|
| 시간 증분 | 약속 간격을 결정합니다. 시간 증가를 5분에서 4시간으로 설정할 수 있습니다. 사용자 지정된 시간 증분을 직접 설정할 수도 있습니다. 예를 들어 15분 간격은 고객이 8:00, 8:15, 8:30 등에서 60분 약속을 예약할 수 있다는 의미입니다. 반대로, 60분 간격은 약속이 시간에서만 사용 가능을 나타냅니다. 서비스 기간을 설정하는 경우 서비스 제품 [정의를 참조합니다.](define-service-offerings.md) |
| 리드 타임(시간) | 예약된 약속에 따라 직원 계획을 수립할 수 있으므로 특정 일에 서비스를 위해 얼마나 많은 고객을 유치하는지 미리 알아야 합니다. 에지 타임 정책을 사용하면 고객이 약속을 예약하거나 취소해야 하는 시간을 미리 지정할 수 있습니다. |
| 최대 일 수 미리 | 고객이 약속을 미리 예약할 수 있는 거리를 제한하려는 경우 이 설정이 바로 사용자에 대한 설정입니다. 최대 365일 이상을 설정할 수 있습니다. |
| 예약을 만들거나 변경할 때 알림 | 고객이 약속을 예약하거나 기존 약속을 변경할 때 전자 메일을 받으시고 싶은 경우 이 옵션을 선택합니다. 전자 메일은 비즈니스 정보 페이지에 지정된 사서함으로 이동합니다. 자세한 [내용은 비즈니스 정보 입력을](enter-business-information.md) 참조하세요. |

## <a name="set-your-policies"></a>정책 설정

1. Microsoft 365에서 앱 시작 프로그램을 선택한 다음 Bookings를 선택합니다.

1. 탐색 창에서 예약 **페이지를 선택합니다.**

1. Select your policies under the **Scheduling policy** section.

1. 저장 **및 게시를 선택합니다.**

## <a name="publish-the-booking-page"></a>예약 페이지 게시

예약 페이지를 게시할 준비가 되면 저장 및 **게시를 선택합니다.** 자세한 [내용은 예약 페이지 사용자 지정](customize-booking-page.md) 및 게시를 참조하세요.
