---
title: 끝점 검색 및 응답 기능 개요
ms.reviewer: ''
description: 끝점용 Microsoft Defender의 엔드포인트 감지 및 응답 기능에 대해 자세히 알아보시고
keywords: 끝점용 Microsoft Defender, 엔드포인트 감지 및 대응, 대응, 탐지, 사이버 보안, 보호
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
ms.openlocfilehash: b00bef611a3e4b33bf15a5366b09a96f68d4c1a2
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933520"
---
# <a name="overview-of-endpoint-detection-and-response"></a><span data-ttu-id="366d6-104">끝점 검색 및 응답 개요</span><span class="sxs-lookup"><span data-stu-id="366d6-104">Overview of endpoint detection and response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="366d6-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="366d6-105">**Applies to:**</span></span>
- [<span data-ttu-id="366d6-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="366d6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="366d6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="366d6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="366d6-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="366d6-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="366d6-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="366d6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="366d6-110">Endpoint 끝점 감지 및 응답 기능에 대한 Defender는 거의 실시간으로 실행 가능한 고급 공격 감지를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="366d6-110">Defender for Endpoint endpoint detection and response capabilities provide advanced attack detections that are near real-time and actionable.</span></span> <span data-ttu-id="366d6-111">보안 분석가는 알림에 효과적으로 우선 순위를 지정하고, 침해의 전체 범위에 대한 가시성을 확보하고 위협을 수정하기 위한 대응 조치를 취할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="366d6-111">Security analysts can prioritize alerts effectively, gain visibility into the full scope of a breach, and take response actions to remediate threats.</span></span>

<span data-ttu-id="366d6-112">위협이 탐지되면 분석가가 조사할 수 있도록 시스템에서 경고가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="366d6-112">When a threat is detected, alerts are created in the system for an analyst to investigate.</span></span> <span data-ttu-id="366d6-113">동일한 공격 기법 혹은 동일한 공격자에 기인한 경고는 _인시던트_ 라는 엔터티로 집계됩니다.</span><span class="sxs-lookup"><span data-stu-id="366d6-113">Alerts with the same attack techniques or attributed to the same attacker are aggregated into an entity called an _incident_.</span></span> <span data-ttu-id="366d6-114">이처럼 경고를 집계하면 분석가가 위협을 손쉽게 일괄적으로 조사하고 이에 대응할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="366d6-114">Aggregating alerts in this manner makes it easy for analysts to collectively investigate and respond to threats.</span></span>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4o1j5]

<span data-ttu-id="366d6-115">"위반 가정" 마음가림에 따라 엔드포인트용 Defender는 행동적 사이버 원격 분석도 지속적으로 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="366d6-115">Inspired by the "assume breach" mindset, Defender for Endpoint continuously collects behavioral cyber telemetry.</span></span> <span data-ttu-id="366d6-116">여기에는 프로세스 정보, 네트워크 활동, 커널 및 메모리 관리자에 대한 심도있는 광학, 사용자 로그인 활동, 레지스트리와 파일 시스템 변경 등이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="366d6-116">This includes process information, network activities, deep optics into the kernel and memory manager, user login activities, registry and file system changes, and others.</span></span> <span data-ttu-id="366d6-117">이 정보는 6개월간 저장이 되어 분석가가 공격의 시작 시점으로 돌아가볼 수 있게 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="366d6-117">The information is stored for six months, enabling an analyst to travel back in time to the start of an attack.</span></span> <span data-ttu-id="366d6-118">그런 다음 분석가는 다양한 벡터를 통해 다양한 보기로 회전하고 조사를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="366d6-118">The analyst can then pivot in various views and approach an investigation through multiple vectors.</span></span>

<span data-ttu-id="366d6-119">대응 기능은 사용자가 영향을 받는 엔터티에 대처하여 위협을 즉시 수정할 수 있도록 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="366d6-119">The response capabilities give you the power to promptly remediate threats by acting on the affected entities.</span></span>


## <a name="related-topics"></a><span data-ttu-id="366d6-120">관련 항목</span><span class="sxs-lookup"><span data-stu-id="366d6-120">Related topics</span></span>
- [<span data-ttu-id="366d6-121">보안 운영 대시보드</span><span class="sxs-lookup"><span data-stu-id="366d6-121">Security operations dashboard</span></span>](security-operations-dashboard.md)
- [<span data-ttu-id="366d6-122">인시던트 큐</span><span class="sxs-lookup"><span data-stu-id="366d6-122">Incidents queue</span></span>](view-incidents-queue.md)
- [<span data-ttu-id="366d6-123">경고 큐</span><span class="sxs-lookup"><span data-stu-id="366d6-123">Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="366d6-124">장치 목록</span><span class="sxs-lookup"><span data-stu-id="366d6-124">Devices list</span></span>](machines-view-overview.md)

