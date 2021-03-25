---
title: 끝점 검색 및 응답 기능 개요
ms.reviewer: ''
description: Microsoft Defender ATP의 엔드포인트 감지 및 응답 기능에 대해 자세히 알아보시고
keywords: ''
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 858ea0f8d46ac2489dd6ef5c10caf2ce0879e4fb
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076519"
---
# <a name="overview-of-endpoint-detection-and-response"></a><span data-ttu-id="e86f5-103">끝점 검색 및 응답 개요</span><span class="sxs-lookup"><span data-stu-id="e86f5-103">Overview of endpoint detection and response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e86f5-104">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="e86f5-104">**Applies to:**</span></span>
- [<span data-ttu-id="e86f5-105">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e86f5-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="e86f5-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e86f5-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e86f5-107">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="e86f5-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e86f5-108">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="e86f5-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="e86f5-109">Endpoint 끝점 감지 및 응답 기능에 대한 Defender는 거의 실시간으로 실행 가능한 고급 공격 감지를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e86f5-109">Defender for Endpoint endpoint detection and response capabilities provide advanced attack detections that are near real-time and actionable.</span></span> <span data-ttu-id="e86f5-110">보안 분석가는 알림에 효과적으로 우선 순위를 지정하고, 침해의 전체 범위에 대한 가시성을 확보하고 위협을 수정하기 위한 대응 조치를 취할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e86f5-110">Security analysts can prioritize alerts effectively, gain visibility into the full scope of a breach, and take response actions to remediate threats.</span></span>

<span data-ttu-id="e86f5-111">위협이 탐지되면 분석가가 조사할 수 있도록 시스템에서 경고가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="e86f5-111">When a threat is detected, alerts are created in the system for an analyst to investigate.</span></span> <span data-ttu-id="e86f5-112">동일한 공격 기법 혹은 동일한 공격자에 기인한 경고는 _인시던트_ 라는 엔터티로 집계됩니다.</span><span class="sxs-lookup"><span data-stu-id="e86f5-112">Alerts with the same attack techniques or attributed to the same attacker are aggregated into an entity called an _incident_.</span></span> <span data-ttu-id="e86f5-113">이처럼 경고를 집계하면 분석가가 위협을 손쉽게 일괄적으로 조사하고 이에 대응할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e86f5-113">Aggregating alerts in this manner makes it easy for analysts to collectively investigate and respond to threats.</span></span>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4o1j5]

<span data-ttu-id="e86f5-114">"위반 가정" 마음가림에 따라 엔드포인트용 Defender는 행동적 사이버 원격 분석도 지속적으로 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="e86f5-114">Inspired by the "assume breach" mindset, Defender for Endpoint continuously collects behavioral cyber telemetry.</span></span> <span data-ttu-id="e86f5-115">여기에는 프로세스 정보, 네트워크 활동, 커널 및 메모리 관리자에 대한 심도있는 광학, 사용자 로그인 활동, 레지스트리와 파일 시스템 변경 등이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e86f5-115">This includes process information, network activities, deep optics into the kernel and memory manager, user login activities, registry and file system changes, and others.</span></span> <span data-ttu-id="e86f5-116">이 정보는 6개월간 저장이 되어 분석가가 공격의 시작 시점으로 돌아가볼 수 있게 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="e86f5-116">The information is stored for six months, enabling an analyst to travel back in time to the start of an attack.</span></span> <span data-ttu-id="e86f5-117">그런 다음 분석가는 다양한 벡터를 통해 다양한 보기로 회전하고 조사를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e86f5-117">The analyst can then pivot in various views and approach an investigation through multiple vectors.</span></span>

<span data-ttu-id="e86f5-118">대응 기능은 사용자가 영향을 받는 엔터티에 대처하여 위협을 즉시 수정할 수 있도록 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="e86f5-118">The response capabilities give you the power to promptly remediate threats by acting on the affected entities.</span></span>


## <a name="related-topics"></a><span data-ttu-id="e86f5-119">관련 항목</span><span class="sxs-lookup"><span data-stu-id="e86f5-119">Related topics</span></span>
- [<span data-ttu-id="e86f5-120">보안 운영 대시보드</span><span class="sxs-lookup"><span data-stu-id="e86f5-120">Security operations dashboard</span></span>](security-operations-dashboard.md)
- [<span data-ttu-id="e86f5-121">인시던트 큐</span><span class="sxs-lookup"><span data-stu-id="e86f5-121">Incidents queue</span></span>](view-incidents-queue.md)
- [<span data-ttu-id="e86f5-122">경고 큐</span><span class="sxs-lookup"><span data-stu-id="e86f5-122">Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="e86f5-123">장치 목록</span><span class="sxs-lookup"><span data-stu-id="e86f5-123">Devices list</span></span>](machines-view-overview.md)

