---
title: 동적 Recurring 모임을 모임에 대한 모임을 주관합니다.
ms.author: sarichardson
author: sallyri
manager: serdars
audience: Admin
ms.topic: article
ms.service: scheduler
ms.reviewer: strettin
ms.localizationpriority: medium
description: 사용자는 동적 재발 모임을 보다 자세히 학습할 수 있습니다.
ms.openlocfilehash: d4f99b336088e7c565c741a8f631e4fefbada68f
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2021
ms.locfileid: "60701392"
---
# <a name="scheduling-dynamic-recurring-meetings"></a>동적 Recurring 모임을 모임에 대한 모임을 주관합니다.

스케줄러의 동적 모임은 사용자의 사용 중 일정을 해결합니다. 스케줄러가 관리하는 재발하는 모임은 모임의 기존 재발 모임과 다르게 Outlook. 일정을 열어 두고 참석자와의 충돌을 최소화하기 위해 스케줄러는 한 번씩 모임을 예약합니다.

예를 들어 Cortana "매일 30분의 포커스 시간 예약"을 요청하면 처음에는 일정에서 사용 가능한 다음 날짜에 대해 30분의 약속이 생성됩니다.  약속 시간이 지나면 스케줄러가 다음 날짜에 다른 인스턴스를 예약합니다. 원래 시간 슬롯을 현재 사용할 수 없는 경우 스케줄러는 가용성에 따라 시간을 조정합니다.

초대를 하는 모임에도 동일한 이적을 적용할 수 있습니다. 요청에 참석자 포함을 요청하고 "2주에 Cortana 모임 예약"을 요청할 수 있습니다. 첫 번째 및 각 후속 모임은 조직 내의 모든 참석자에 대한 현재 사용 가능 여부에 따라 동적으로 예약됩니다. 사용자 또는 참석자는 다음 날짜에 사용할 수 없거나 사무실을 비워 두면 모임 시간이 모든 사용자가 사용할 수 있는 시기에 자동으로 조정되며, 새로 예약된 날짜에 따라 후속 모임 인스턴스에 대해 원하는 일정이 보존됩니다.

## <a name="booking-with-attendees-outside-your-organization"></a>조직 외부의 참석자와 예약

조직 외부의 참석자와의 모임을 계획할 때 가상 도우미는 첫 번째 모임에 대한 외부 참석자 시간 옵션을 전송합니다. 향후 모든 모임은 이끌이 및 내부 참석자 가용성에 따라 자동으로 예약됩니다.

스케줄러는 매일, 매주 및 월별 간격을 지원합니다.

## <a name="examples-of-how-to-request-recurring-meetings"></a>재발 모임을 요청하는 방법의 예

다음은 전자 메일을 보내 모임을 예약하는 방법에 대한 몇 Cortana 예입니다.

- "Cortana 2주마다 모임을 예약합니다."
- "리뷰를 위해 월별 30분 예약"
- "Cortana 매주 화요일에 만나는 데 30분 정도 걸립니다."
- "Cortana, 매주 금요일 오후 3시 30분에 예약"

## <a name="changing-recurring-frequency"></a>재발 빈도 변경

스케줄러에서 관리하는 모든 재발 모임 또는 비회원 모임의 빈도를 변경할 수 있습니다. 모임 스레드에서 Cortana 확인 전자 메일의 메시지에 회신하고 다음 Cortana.

- "매월 한 번으로 변경합니다."
- "Cortana 모임을 쌍으로 만들어야 합니다."

## <a name="cancelling-recurring-meetings"></a>Recurring Meetings 취소

최신 확인 Cortana 회신하고 "모임 취소"를 요청하여 예약된 인스턴스를 취소할 수 있습니다. 그러나 스케줄러는 동일한 빈도로 향후 모임을 계속 예약합니다. 또는 Scheduler에 다음 인스턴스를 원하는 날짜 또는 시간으로 다시 예약할 수도 있습니다. 전체 Recurring 계열을 취소할 경우 "이 시리즈 취소"로 응답하면 향후 인스턴스가 예약되지 않습니다.

## <a name="recurring-meeting-limitations"></a>Recurring Meeting Limitations

스케줄러가 이해하고 지원할 수 있는 재발 유형에는 몇 가지 기술적 제한이 있습니다.

- 같은 간격 내의 여러 번의 발생은 지원되지 않습니다(예: "일주일에 두 번").
- 재발에 대한 종료 날짜는 지원되지 않습니다(예: "매일 12월 20일까지"). 이전 모임이 완료될 때 각 모임이 예약되어 있는 경우 "이 모임 시리즈 취소"를 Cortana 메시지에 회신하기만하면 됩니다.
- 스케줄러는 현재 90일보다 큰 재발 주파수를 지원하지 않습니다.
