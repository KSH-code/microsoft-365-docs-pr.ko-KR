---
title: 끝점용 Microsoft Defender 장치 타임라인 이벤트 플래그
description: Microsoft Defender for Endpoint 장치 타임라인 이벤트 플래그를 사용하여
keywords: Endpoint 장치 타임라인에 대한 Defender, 이벤트 플래그
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a34efc171d3bb3aa1fcf33e0f56700149885ac2e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165156"
---
# <a name="microsoft-defender-for-endpoint-device-timeline-event-flags"></a><span data-ttu-id="2b1e5-104">끝점용 Microsoft Defender 장치 타임라인 이벤트 플래그</span><span class="sxs-lookup"><span data-stu-id="2b1e5-104">Microsoft Defender for Endpoint device timeline event flags</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2b1e5-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="2b1e5-105">**Applies to:**</span></span>
- [<span data-ttu-id="2b1e5-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2b1e5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2b1e5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2b1e5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="2b1e5-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="2b1e5-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2b1e5-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="2b1e5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="2b1e5-110">Endpoint 장치 타임라인에 대한 Defender의 이벤트 플래그는 잠재적인 공격을 조사할 때 특정 이벤트를 필터링하고 구성하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b1e5-110">Event flags in the Defender for Endpoint device timeline help you filter and organize specific events when you're  investigate potential attacks.</span></span>

<span data-ttu-id="2b1e5-111">Endpoint 장치 타임라인에 대한 Defender는 장치에서 관찰된 이벤트 및 관련 경고를 시간 표시 막대로 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2b1e5-111">The Defender for Endpoint device timeline provides a chronological view of the events and associated alerts observed on a device.</span></span> <span data-ttu-id="2b1e5-112">이 이벤트 목록은 디바이스에서 관찰된 모든 이벤트, 파일 및 IP 주소를 전체 표시하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2b1e5-112">This list of events provides full visibility into any events, files, and IP addresses observed on the device.</span></span> <span data-ttu-id="2b1e5-113">목록이 긴 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b1e5-113">The list can sometimes be lengthy.</span></span> <span data-ttu-id="2b1e5-114">디바이스 타임라인 이벤트 플래그는 관련이 있을 수 있는 이벤트를 추적하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b1e5-114">Device timeline event flags help you track events that could be related.</span></span> 

<span data-ttu-id="2b1e5-115">장치 타임라인을 거치고 나면 플래그가 지정한 특정 이벤트를 정렬, 필터링 및 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b1e5-115">After you've gone through a device timeline, you can sort, filter, and export the specific events that you flagged.</span></span>

<span data-ttu-id="2b1e5-116">디바이스 타임라인을 탐색하는 동안 특정 이벤트를 검색하고 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b1e5-116">While navigating the device timeline, you can search and filter for specific events.</span></span> <span data-ttu-id="2b1e5-117">다음을 통해 이벤트 플래그를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b1e5-117">You can set event flags by:</span></span> 

- <span data-ttu-id="2b1e5-118">가장 중요한 이벤트 강조 표시</span><span class="sxs-lookup"><span data-stu-id="2b1e5-118">Highlighting the most important events</span></span> 
- <span data-ttu-id="2b1e5-119">심층적으로 진행해야 하는 이벤트 표시</span><span class="sxs-lookup"><span data-stu-id="2b1e5-119">Marking events that requires deep dive</span></span> 
- <span data-ttu-id="2b1e5-120">위반 일정을 깔끔하게 구축</span><span class="sxs-lookup"><span data-stu-id="2b1e5-120">Building a clean breach timeline</span></span>



## <a name="flag-an-event"></a><span data-ttu-id="2b1e5-121">이벤트 플래그 지정</span><span class="sxs-lookup"><span data-stu-id="2b1e5-121">Flag an event</span></span>
1. <span data-ttu-id="2b1e5-122">플래그를 지정하려는 이벤트 찾기</span><span class="sxs-lookup"><span data-stu-id="2b1e5-122">Find the event that you want to flag</span></span>
2. <span data-ttu-id="2b1e5-123">플래그 열에서 플래그 아이콘을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2b1e5-123">Click the flag icon in the Flag column.</span></span> 
<span data-ttu-id="2b1e5-124">![장치 타임라인 플래그의 이미지](images/device-flags.png)</span><span class="sxs-lookup"><span data-stu-id="2b1e5-124">![Image of device timeline flag](images/device-flags.png)</span></span>

## <a name="view-flagged-events"></a><span data-ttu-id="2b1e5-125">플래그가 지정한 이벤트 보기</span><span class="sxs-lookup"><span data-stu-id="2b1e5-125">View flagged events</span></span>  
1. <span data-ttu-id="2b1e5-126">시간 표시 막대 필터 **섹션에서** **Flagged 이벤트를 사용하도록 설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="2b1e5-126">In the timeline **Filters** section, enable **Flagged events**.</span></span>
2. <span data-ttu-id="2b1e5-127">**적용** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2b1e5-127">Click **Apply**.</span></span> <span data-ttu-id="2b1e5-128">플래그가 지정한 이벤트만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b1e5-128">Only flagged events are displayed.</span></span>
<span data-ttu-id="2b1e5-129">시간 표시줄을 클릭하여 추가 필터를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b1e5-129">You can apply additional filters by clicking on the time bar.</span></span> <span data-ttu-id="2b1e5-130">이 이벤트는 플래그가 지정된 이벤트 이전의 이벤트만 보여 주게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b1e5-130">This will only show events prior to the flagged event.</span></span>  
<span data-ttu-id="2b1e5-131">![필터가 설정되어 있는 장치 타임라인 플래그의 이미지](images/device-flag-filter.png)</span><span class="sxs-lookup"><span data-stu-id="2b1e5-131">![Image of device timeline flag with filter on](images/device-flag-filter.png)</span></span>
