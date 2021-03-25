---
title: 디바이스 타임라인의 기술
description: 끝점용 Microsoft Defender의 장치 타임라인 이해
keywords: 장치 타임라인, 끝점, MITRE, MITRE ATT&CK, 기술, 전략
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6b080c209292c8cac1aa64d748926734f4be964c
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185470"
---
# <a name="techniques-in-the-device-timeline"></a><span data-ttu-id="2648f-104">디바이스 타임라인의 기술</span><span class="sxs-lookup"><span data-stu-id="2648f-104">Techniques in the device timeline</span></span>


<span data-ttu-id="2648f-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="2648f-105">**Applies to:**</span></span>
- [<span data-ttu-id="2648f-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2648f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


<span data-ttu-id="2648f-107">특정 디바이스에서 발생된 이벤트를 분석하여 조사에서 더 많은 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2648f-107">You can gain more insight in an investigation by analyzing the events that happened on a specific device.</span></span> <span data-ttu-id="2648f-108">먼저 장치 목록 에서 관심 있는 장치를 [선택합니다.](machines-view-overview.md)</span><span class="sxs-lookup"><span data-stu-id="2648f-108">First, select the device of interest from the [Devices list](machines-view-overview.md).</span></span> <span data-ttu-id="2648f-109">디바이스 페이지에서 시간 표시 막대  탭을 선택하여 디바이스에서 발생한 모든 이벤트를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2648f-109">On the device page, you can select the **Timeline** tab to view all the events that occurred on the device.</span></span>

## <a name="understand-techniques-in-the-timeline"></a><span data-ttu-id="2648f-110">타임라인의 기술 이해</span><span class="sxs-lookup"><span data-stu-id="2648f-110">Understand techniques in the timeline</span></span>

>[!IMPORTANT]
><span data-ttu-id="2648f-111">일부 정보는 상업적으로 출시되기 전에 상당수 수정될 수 있는 공개 미리 보기의 미리 보기 제품 기능과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2648f-111">Some information relates to a prereleased product feature in public preview which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="2648f-112">Microsoft는 여기에서 제공하는 정보와 관련하여 명시적이거나 묵시적인 어떠한 보증도 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2648f-112">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="2648f-113">끝점용 Microsoft Defender에서 **Techniques은** 이벤트 타임라인의 추가 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="2648f-113">In Microsoft Defender for Endpoint, **Techniques** are an additional data type in the event timeline.</span></span> <span data-ttu-id="2648f-114">기술은 [MITRE ATT](https://attack.mitre.org/) 및 CK 기술 또는 하위&관련된 활동에 대한 더 많은 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2648f-114">Techniques provide more insight on activities associated with [MITRE ATT&CK](https://attack.mitre.org/) techniques or sub-techniques.</span></span> 

<span data-ttu-id="2648f-115">이 기능은 분석가가 디바이스에서 관찰된 활동을 이해하는 데 도움을 주어 조사 환경을 간소화합니다.</span><span class="sxs-lookup"><span data-stu-id="2648f-115">This feature simplifies the investigation experience by helping analysts understand the activities that were observed on a device.</span></span> <span data-ttu-id="2648f-116">분석가가 추가 조사를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2648f-116">Analysts can then decide to investigate further.</span></span>

<span data-ttu-id="2648f-117">공개 미리 보기의 경우 기본적으로 기술을 사용할 수 있으며 디바이스의 타임라인이 표시되어 있는 경우 이벤트와 함께 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2648f-117">For public preview, Techniques are available by default and shown together with events when a device's timeline is viewed.</span></span> 

![디바이스 타임라인 스크린샷의 기술](images/device-timeline-2.png)

<span data-ttu-id="2648f-119">기술은 굵은 텍스트로 강조 표시하고 왼쪽에 파란색 아이콘과 함께 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2648f-119">Techniques are highlighted in bold text and appear with a blue icon on the left.</span></span> <span data-ttu-id="2648f-120">해당 MITRE ATT&CK ID 및 기술 이름도 추가 정보 아래에 태그로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2648f-120">The corresponding MITRE ATT&CK ID and technique name also appear as tags under Additional information.</span></span> 

<span data-ttu-id="2648f-121">기술에 대해 검색 및 내보내기 옵션도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2648f-121">Search and Export options are also available for Techniques.</span></span>

## <a name="investigate-using-the-side-pane"></a><span data-ttu-id="2648f-122">왼쪽 창을 사용하여 조사</span><span class="sxs-lookup"><span data-stu-id="2648f-122">Investigate using the side pane</span></span>

<span data-ttu-id="2648f-123">기술을 선택하여 해당 왼쪽 창을 여는 방법을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2648f-123">Select a Technique to open its corresponding side pane.</span></span> <span data-ttu-id="2648f-124">여기에서 관련 ATT 및 CK 기술, 전략 및 설명과 같은&정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2648f-124">Here you can see additional information and insights like related ATT&CK techniques, tactics, and descriptions.</span></span> 

<span data-ttu-id="2648f-125">특정 *공격* 기술을 선택하여 관련 ATT&CK 기술 페이지를 열어 자세한 정보를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2648f-125">Select the specific *Attack technique* to open the related ATT&CK technique page where you can find more information about it.</span></span>

<span data-ttu-id="2648f-126">오른쪽에 파란색 아이콘이 표시될 때 엔터티의 세부 정보를 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2648f-126">You can copy an entity's details when you see a blue icon on the right.</span></span> <span data-ttu-id="2648f-127">예를 들어 관련 파일의 SHA1을 복사하려면 파란색 페이지 아이콘을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2648f-127">For instance, to copy a related file's SHA1, select the blue page icon.</span></span>

![엔터티 세부 정보 복사](images/techniques-side-pane-clickable.png)

<span data-ttu-id="2648f-129">명령줄에 대해 동일한 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2648f-129">You can do the same for command lines.</span></span>

![명령줄 복사](images/techniques-side-pane-command.png)


## <a name="investigate-related-events"></a><span data-ttu-id="2648f-131">관련 이벤트 조사</span><span class="sxs-lookup"><span data-stu-id="2648f-131">Investigate related events</span></span>

<span data-ttu-id="2648f-132">고급 [헌팅을](advanced-hunting-overview.md) 사용하여 선택한 기술과 관련된 이벤트를 찾으하려면 관련 이벤트 **헌트 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2648f-132">To use [advanced hunting](advanced-hunting-overview.md) to find events related to the selected Technique, select **Hunt for related events**.</span></span> <span data-ttu-id="2648f-133">이렇게 하면 기술과 관련된 이벤트를 찾기 위한 쿼리가 있는 고급 헌팅 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2648f-133">This leads to the advanced hunting page with a query to find events related to the Technique.</span></span>

![관련 이벤트 헌트](images/techniques-hunt-for-related-events.png)

>[!NOTE]
><span data-ttu-id="2648f-135">기술 쪽  창의 관련 이벤트 헌트 단추를 사용하여 쿼리하면 식별된 기술과 관련된 모든 이벤트가 표시되지만 쿼리 결과에는 기술 자체가 포함되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2648f-135">Querying using the **Hunt for related events** button from a Technique side pane displays all the events related to the identified technique but does not include the Technique itself in the query results.</span></span>


## <a name="customize-your-device-timeline"></a><span data-ttu-id="2648f-136">장치 타임라인 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="2648f-136">Customize your device timeline</span></span>

<span data-ttu-id="2648f-137">디바이스 타임라인의 오른쪽 위에 있는 날짜 범위를 선택하면 타임라인의 이벤트 및 기술 수를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2648f-137">On the upper right-hand side of the device timeline, you can choose a date range to limit the number of events and techniques in the timeline.</span></span> 

<span data-ttu-id="2648f-138">노출할 열을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2648f-138">You can customize which columns to expose.</span></span> <span data-ttu-id="2648f-139">또한 데이터 형식 또는 이벤트 그룹별로 플래그가 지정된 이벤트를 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2648f-139">You can also filter for flagged events by data type or by event group.</span></span>

### <a name="choose-columns-to-expose"></a><span data-ttu-id="2648f-140">노출할 열 선택</span><span class="sxs-lookup"><span data-stu-id="2648f-140">Choose columns to expose</span></span>
<span data-ttu-id="2648f-141">열 선택 단추를 선택하여 시간 표시 막대에 노출할 열을 **선택할 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2648f-141">You can choose which columns to expose in the timeline by selecting the **Choose columns** button.</span></span>

![열 사용자 지정](images/filter-customize-columns.png)

<span data-ttu-id="2648f-143">이 목록에서 포함할 정보를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2648f-143">From there you can select which information set to include.</span></span>

### <a name="filter-to-view-techniques-or-events-only"></a><span data-ttu-id="2648f-144">기술 또는 이벤트만 보기 위해 필터링</span><span class="sxs-lookup"><span data-stu-id="2648f-144">Filter to view techniques or events only</span></span>

<span data-ttu-id="2648f-145">이벤트 또는 기술만 표시하려면  장치 타임라인에서 필터를 선택하고 볼 기본 설정 데이터 형식을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2648f-145">To view only either events or techniques, select **Filters** from the device timeline and choose your preferred Data type to view.</span></span>

![필터 스크린샷](images/device-timeline-filters.png)



## <a name="see-also"></a><span data-ttu-id="2648f-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2648f-147">See also</span></span>
- [<span data-ttu-id="2648f-148">장치 목록 보기 및 구성</span><span class="sxs-lookup"><span data-stu-id="2648f-148">View and organize the Devices list</span></span>](machines-view-overview.md)
- [<span data-ttu-id="2648f-149">끝점용 Microsoft Defender 장치 타임라인 이벤트 플래그</span><span class="sxs-lookup"><span data-stu-id="2648f-149">Microsoft Defender for Endpoint device timeline event flags</span></span>](device-timeline-event-flag.md) 


 
