---
title: EOP 대기, 지연 및 반송 메시지 FAQ
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
ms.custom:
- seo-marvel-apr2020
description: EOP(Exchange Online Protection) 필터링 프로세스 중에 대기, 지연 또는 반송된 메시지에 대한 가장 일반적인 질문에 대한 대답을 찾아보세요.
ms.openlocfilehash: 76fe08f3a83321b6c0549dae5f1382ead5f0b3ae
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827752"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a><span data-ttu-id="03eea-103">EOP 대기, 지연 및 반송 메시지 FAQ</span><span class="sxs-lookup"><span data-stu-id="03eea-103">EOP queued, deferred, and bounced messages FAQ</span></span>

<span data-ttu-id="03eea-104">이 항목에서는 EOP(Exchange Online Protection) 필터링 프로세스 중에 대기, 지연 또는 반송된 메시지에 대한 질문과 대답을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="03eea-104">This topic provides answers to frequently asked questions about messages that have been queued, deferred, or bounced during the Exchange Online Protection (EOP) filtering process.</span></span>

## <a name="why-is-mail-queuing"></a><span data-ttu-id="03eea-105">메일이 큐에서 대기하는 이유는 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="03eea-105">Why is mail queuing?</span></span>

<span data-ttu-id="03eea-106">서비스에서 배달을 위해 받는 사람에 연결할 수 없는 경우 메시지가 큐에 대기하거나 지연됩니다.</span><span class="sxs-lookup"><span data-stu-id="03eea-106">Messages are queued or deferred if the service is unable to make a connection to the recipient server for delivery.</span></span> <span data-ttu-id="03eea-107">받는 사람 네트워크에서 500 계열 오류가 반환되는 경우에는 메시지가 지연되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="03eea-107">It will not defer messages if a 500-series error is returned from the recipient network.</span></span>

## <a name="how-does-a-message-become-deferred"></a><span data-ttu-id="03eea-108">메시지는 어떤 방식으로 지연되나요?</span><span class="sxs-lookup"><span data-stu-id="03eea-108">How does a message become deferred?</span></span>

<span data-ttu-id="03eea-109">받는 사람 서버에 연결할 수 없고 받는 사람의 서버에서 연결 시간 초과, 연결 거부 또는 400 계열 오류와 같은 "일시적인 오류"를 반환하는 경우 메시지가 보류됩니다.</span><span class="sxs-lookup"><span data-stu-id="03eea-109">Messages will be held when a connection to the recipient server cannot be made and the recipient's server is returning a "temporary failure" such as a connection time-out, connection refused, or a 400-series error.</span></span> <span data-ttu-id="03eea-110">500 계열 오류와 같은 영구 오류가 발생한 경우에는 메시지가 보낸 사람에게 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="03eea-110">If there is a permanent failure, such as a 500-series error, then the message will be returned to the sender.</span></span>

## <a name="how-long-does-a-message-remain-in-deferral-and-what-is-the-retry-interval"></a><span data-ttu-id="03eea-111">메시지가 지연 상태로 유지되는 기간 및 다시 시도 간격은 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="03eea-111">How long does a message remain in deferral and what is the retry interval?</span></span>

<span data-ttu-id="03eea-112">지연 메시지는 대기열에 1일까지 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="03eea-112">Messages in deferral will remain in our queues for 1 day.</span></span> <span data-ttu-id="03eea-113">메시지 다시 시도는 받는 사람의 메일 시스템에서 다시 수신된 오류를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="03eea-113">Message retry attempts are based on the error we get back from the recipient's mail system.</span></span> <span data-ttu-id="03eea-114">처음 몇 분이 지나면 지연되는 시간이 15분 이내이고 다음 번에 다시 시도(3/252년 정도+3/32/2회)하여 간격이 여러 번 다시 시도하는 최대 60분까지 늘어나는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="03eea-114">The first few deferrals are 15 minutes or less, with subsequent retries (over the next half dozen or so) increasing the interval over multiple retries to a max of 60 minutes.</span></span> <span data-ttu-id="03eea-115">기간 확장은 동적이며, 큐 크기 및 내부 메시지 우선 순위와 같은 여러 변수를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="03eea-115">The interval duration expansion is dynamic, taking into consideration multiple variables like queue sizes and internal message priority.</span></span> <span data-ttu-id="03eea-116">기본적으로 시작하는 데는 15분 이하인 후 다음 몇 시간에서 60min까지 확장되는 것이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="03eea-116">In basic, it's 15 minutes (or less) to start, then expanding from there over the next few hours to 60 mins max.</span></span>

## <a name="after-your-email-server-is-restored-how-are-queued-messages-distributed"></a><span data-ttu-id="03eea-117">전자 메일 서버가 복원된 경우 큐에 있는 메시지는 어떻게 배포되나요?</span><span class="sxs-lookup"><span data-stu-id="03eea-117">After your email server is restored, how are queued messages distributed?</span></span>

<span data-ttu-id="03eea-118">전자 메일 서버가 복원된 후 큐에 있는 모든 메시지는 받은 순서 및 서버를 사용할 수 없어 큐에 추가된 순서대로 자동으로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="03eea-118">After your email server is restored, all queued messages are automatically processed in the order in which they were received and queued when the server became unavailable.</span></span>
