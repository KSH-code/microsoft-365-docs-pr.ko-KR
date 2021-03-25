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
localization_priority: Normal
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
ms.custom:
- seo-marvel-apr2020
description: EOP(Exchange Online Protection) 필터링 프로세스 중에 대기, 지연 또는 반송된 메시지에 대한 가장 일반적인 질문에 대한 답변을 찾아 묻습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c7b5ba595e9a6401efd1b733c9e5a11c8a966037
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206789"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a><span data-ttu-id="0d931-103">EOP 대기, 지연 및 반송 메시지 FAQ</span><span class="sxs-lookup"><span data-stu-id="0d931-103">EOP queued, deferred, and bounced messages FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0d931-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="0d931-104">**Applies to**</span></span>
- [<span data-ttu-id="0d931-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="0d931-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="0d931-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="0d931-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="0d931-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0d931-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="0d931-108">이 항목에서는 EOP(Exchange Online Protection) 필터링 프로세스 중에 대기, 지연 또는 반송된 메시지에 대한 질문과 대답을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0d931-108">This topic provides answers to frequently asked questions about messages that have been queued, deferred, or bounced during the Exchange Online Protection (EOP) filtering process.</span></span>

## <a name="why-is-mail-queuing"></a><span data-ttu-id="0d931-109">메일이 큐에서 대기하는 이유는 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="0d931-109">Why is mail queuing?</span></span>

<span data-ttu-id="0d931-110">서비스에서 배달을 위해 받는 사람에 연결할 수 없는 경우 메시지가 큐에 대기하거나 지연됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d931-110">Messages are queued or deferred if the service is unable to make a connection to the recipient server for delivery.</span></span> <span data-ttu-id="0d931-111">받는 사람 네트워크에서 500 계열 오류가 반환되는 경우에는 메시지가 지연되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d931-111">It will not defer messages if a 500-series error is returned from the recipient network.</span></span>

## <a name="how-does-a-message-become-deferred"></a><span data-ttu-id="0d931-112">메시지는 어떤 방식으로 지연되나요?</span><span class="sxs-lookup"><span data-stu-id="0d931-112">How does a message become deferred?</span></span>

<span data-ttu-id="0d931-113">받는 사람 서버에 연결할 수 없고 받는 사람의 서버에서 연결 시간 초과, 연결 거부 또는 400 계열 오류와 같은 "일시적인 오류"를 반환하는 경우 메시지가 보류됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d931-113">Messages will be held when a connection to the recipient server cannot be made and the recipient's server is returning a "temporary failure" such as a connection time-out, connection refused, or a 400-series error.</span></span> <span data-ttu-id="0d931-114">500 계열 오류와 같은 영구 오류가 발생한 경우에는 메시지가 보낸 사람에게 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d931-114">If there is a permanent failure, such as a 500-series error, then the message will be returned to the sender.</span></span>

## <a name="how-long-does-a-message-remain-in-deferral-and-what-is-the-retry-interval"></a><span data-ttu-id="0d931-115">메시지가 지연 상태로 유지되는 기간 및 다시 시도 간격은 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="0d931-115">How long does a message remain in deferral and what is the retry interval?</span></span>

<span data-ttu-id="0d931-116">지연 메시지는 1일 동안 큐에 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d931-116">Messages in deferral will remain in our queues for 1 day.</span></span> <span data-ttu-id="0d931-117">메시지 다시 시도는 받는 사람의 메일 시스템에서 다시 수신된 오류를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d931-117">Message retry attempts are based on the error we get back from the recipient's mail system.</span></span> <span data-ttu-id="0d931-118">처음 몇 개의 지연은 15분 이하로, 후속 다시시작(후반반 12분 이상)이 진행되어 여러 재시도 간격이 최대 60분까지 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="0d931-118">The first few deferrals are 15 minutes or less, with subsequent retries (over the next half dozen or so) increasing the interval over multiple retries to a max of 60 minutes.</span></span> <span data-ttu-id="0d931-119">간격 기간 확장은 큐 크기 및 내부 메시지 우선 순위와 같은 여러 변수를 고려하여 동적입니다.</span><span class="sxs-lookup"><span data-stu-id="0d931-119">The interval duration expansion is dynamic, taking into consideration multiple variables like queue sizes and internal message priority.</span></span> <span data-ttu-id="0d931-120">기본적으로 15분 이하로 시작한 다음 다음 몇 시간 동안 확장하여 최대 60분으로 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="0d931-120">In basic, it's 15 minutes (or less) to start, then expanding from there over the next few hours to 60 mins max.</span></span>

## <a name="after-your-email-server-is-restored-how-are-queued-messages-distributed"></a><span data-ttu-id="0d931-121">전자 메일 서버가 복원된 경우 큐에 있는 메시지는 어떻게 배포되나요?</span><span class="sxs-lookup"><span data-stu-id="0d931-121">After your email server is restored, how are queued messages distributed?</span></span>

<span data-ttu-id="0d931-122">전자 메일 서버가 복원된 후 큐에 있는 모든 메시지는 받은 순서 및 서버를 사용할 수 없어 큐에 추가된 순서대로 자동으로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d931-122">After your email server is restored, all queued messages are automatically processed in the order in which they were received and queued when the server became unavailable.</span></span>
