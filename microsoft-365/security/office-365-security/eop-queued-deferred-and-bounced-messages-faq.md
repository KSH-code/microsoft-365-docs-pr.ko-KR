---
title: EOP 대기, 지연 및 반송 메시지 FAQ
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
ms.custom:
- seo-marvel-apr2020
description: EOP (Exchange Online Protection) 필터링 프로세스 중에 대기, 지연 또는 반송 된 메시지에 대 한 일반적인 질문에 대 한 대답을 확인할 수 있습니다.
ms.openlocfilehash: 38e72a04e855862c621bd2b170c11407e0d22af3
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "44206595"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a>EOP 대기, 지연 및 반송 메시지 FAQ

이 항목에서는 EOP (Exchange Online Protection) 필터링 프로세스 중에 대기, 지연 또는 반송 된 메시지에 대 한 질문과 대답을 제공 합니다.

## <a name="why-is-mail-queuing"></a>메일이 큐에서 대기하는 이유는 무엇인가요?

서비스에서 배달을 위해 받는 사람에 연결할 수 없는 경우 메시지가 큐에 대기하거나 지연됩니다. 받는 사람 네트워크에서 500 계열 오류가 반환되는 경우에는 메시지가 지연되지 않습니다.

## <a name="how-does-a-message-become-deferred"></a>메시지는 어떤 방식으로 지연되나요?

받는 사람 서버에 연결할 수 없고 받는 사람의 서버에서 연결 시간 초과, 연결 거부 또는 400 계열 오류와 같은 "일시적인 오류"를 반환하는 경우 메시지가 보류됩니다. 500 계열 오류와 같은 영구 오류가 발생한 경우에는 메시지가 보낸 사람에게 반환됩니다.

## <a name="how-long-does-a-message-remain-in-deferral-and-what-is-the-retry-interval"></a>메시지가 지연 상태로 유지되는 기간 및 다시 시도 간격은 어떻게 되나요?

지연 상태의 메시지는 큐의 1 일 동안 유지 됩니다. 메시지 다시 시도는 받는 사람의 메일 시스템에서 다시 수신된 오류를 기반으로 합니다. 처음 몇 개의 deferrals은 15 분 이내 이며 이후 다시 시도 (앞으로 1 ~ 6 일 이상 경과 함)가 경과 하는 간격을 최대 60 분까지 증가 시킵니다. 간격 기간 확장은 동적으로 큐 크기 및 내부 메시지 우선 순위와 같은 여러 가지 변수를 고려 하 여 수행 됩니다. 기본적으로 시작 하는 데 15 분 (이 하)이 소요 되며, 다음 몇 시간 동안 간격으로 확장 하 여 최대 60 분까지 진행 합니다.

## <a name="after-your-email-server-is-restored-how-are-queued-messages-distributed"></a>전자 메일 서버가 복원된 경우 큐에 있는 메시지는 어떻게 배포되나요?

전자 메일 서버가 복원된 후 큐에 있는 모든 메시지는 받은 순서 및 서버를 사용할 수 없어 큐에 추가된 순서대로 자동으로 처리됩니다.
