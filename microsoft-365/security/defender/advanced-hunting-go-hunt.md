---
title: 이동 헌트가 있는 엔터티에 대한 관련 정보 보기
description: 이동 헌트 도구를 사용하여 고급 헌팅을 사용하여 엔터티 또는 이벤트에 대한 관련 정보를 빠르게 쿼리하는 방법을 학습합니다.
keywords: 고급 헌팅, 인시던트, 피벗, 엔터티, 헌팅, 관련 이벤트, 위협 헌팅, 사이버 위협 헌팅, 검색, 쿼리, 원격 분석, Microsoft 365, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: a78f37d8c1fed1063095e25f19136f0362f17db7
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952659"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a><span data-ttu-id="49012-104">이동 헌트로 엔터티 또는 이벤트 정보를 빠르게 헌팅</span><span class="sxs-lookup"><span data-stu-id="49012-104">Quickly hunt for entity or event information with go hunt</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="49012-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="49012-105">**Applies to:**</span></span>
- <span data-ttu-id="49012-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="49012-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="49012-107">끝점용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="49012-107">Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="49012-108">이동 *헌트 작업을* 사용하면 강력한 쿼리 기반 고급 헌팅 기능을 사용하여 이벤트 및 다양한 엔터티 유형을 신속하게 조사할 [수](advanced-hunting-overview.md) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49012-108">With the *go hunt* action, you can quickly investigate events and various entity types using powerful query-based [advanced hunting](advanced-hunting-overview.md) capabilities.</span></span> <span data-ttu-id="49012-109">이 작업은 고급 헌팅 쿼리를 자동으로 실행하여 선택한 이벤트 또는 엔터티에 대한 관련 정보를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="49012-109">This action automatically runs an advanced hunting query to find relevant information about the selected event or entity.</span></span>

<span data-ttu-id="49012-110">이동 *헌트* 작업은 이벤트 또는 엔터티 세부 정보가 표시될 때마다 보안 센터의 다양한 섹션에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49012-110">The *go hunt* action is available in various sections of the security center whenever event or entity details are displayed.</span></span> <span data-ttu-id="49012-111">예를 들어 다음 섹션에서 *이동 헌트* 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49012-111">For example, you can use *go hunt* from the following sections:</span></span>

- <span data-ttu-id="49012-112">[인시던트 페이지에서](investigate-incidents.md#summary)인시던트와 관련된 사용자, 장치 및 기타 여러 엔터티에 대한 세부 정보를 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49012-112">In the [incident page](investigate-incidents.md#summary), you can review details about users, devices, and many other entities associated with an incident.</span></span> <span data-ttu-id="49012-113">엔터티를 선택하면 해당 엔터티에 대해 수행할 수 있는 다양한 작업뿐만 아니라 추가 정보도 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49012-113">As you select an entity, you get additional information as well as various actions you could take on that entity.</span></span> <span data-ttu-id="49012-114">아래 예에서는 사서함에 대한 세부 정보와 사서함에 대한 자세한 정보를 헌팅할 수 있는 옵션을 표시하는 사서함이 선택되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49012-114">In the example below, a mailbox is selected, showing details about the mailbox as well the option to hunt for more information about the mailbox.</span></span>

    ![이동 헌트 옵션이 있는 사서함 세부 정보를 보여주는 이미지](../../media/mtp-ah/go-hunt-email.png)

- <span data-ttu-id="49012-116">인시던트 페이지에서 증거 탭의 엔터티 목록에 액세스할 수도 있습니다. 이러한 엔터티 중 하나를 선택하면 해당 엔터티에 대한 정보를 빠르게 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49012-116">In the incident page, you can also access a list of entities under the evidence tab. Selecting one of those entities provides an option to quickly hunt for information about that entity.</span></span>

    ![증거 탭에서 이동 헌트 옵션이 있는 선택한 파일을 보여 주는 이미지](../../media/mtp-ah/go-hunt-evidence-file.png)


- <span data-ttu-id="49012-118">디바이스의 타임라인을 볼 때 타임라인에서 이벤트를 선택하여 해당 이벤트에 대한 추가 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49012-118">When viewing the timeline for a device, you can select an event in the timeline to view additional information about that event.</span></span> <span data-ttu-id="49012-119">이벤트를 선택하면 고급 헌팅에서 다른 관련 이벤트를 헌팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49012-119">Once an event is selected, you get the option to hunt for other relevant events in advanced hunting.</span></span>

    ![이동 헌트 옵션을 사용하여 이벤트 세부 정보를 보여주는 이미지](../../media/mtp-ah/go-hunt-event.png)

<span data-ttu-id="49012-121">이동 **헌트 또는** 헌트와 관련된 이벤트에 대한 헌트를 **선택하면** 엔터티 또는 이벤트를 선택 여부에 따라 다른 쿼리가 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="49012-121">Selecting **Go hunt** or **Hunt for related events** passes different queries, depending on whether you've selected an entity or an event.</span></span>

## <a name="query-for-entity-information"></a><span data-ttu-id="49012-122">엔터티 정보에 대한 쿼리</span><span class="sxs-lookup"><span data-stu-id="49012-122">Query for entity information</span></span>
<span data-ttu-id="49012-123">이동 *헌트에서* 사용자, 장치 또는 기타 엔터티 유형에 대한 정보를 쿼리할 때 쿼리는 해당 엔터티와 관련된 모든 이벤트에 대한 모든 관련 스마마 테이블을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="49012-123">When using *go hunt* to query for information about a user, device, or any other type of entity, the query checks all relevant schema tables for any events involving that entity.</span></span> <span data-ttu-id="49012-124">결과를 관리하기 위해 쿼리의 범위는 엔터티와 관련이 있으며 인시던트와 연관된 지난 30일 동안의 가장 빠른 활동과 같은 기간으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="49012-124">To keep the results manageable, the query is scoped to around the same time period as the earliest activity in the past 30 days that involves the entity and is associated with the incident.</span></span>

<span data-ttu-id="49012-125">다음은 장치에 대한 이동 헌트 쿼리의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="49012-125">Here is an example of the go hunt query for a device:</span></span>

```kusto
let selectedTimestamp = datetime(2020-06-02T02:06:47.1167157Z);
let deviceName = "fv-az770.example.com";
let deviceId = "device-guid";
search in (DeviceLogonEvents, DeviceProcessEvents, DeviceNetworkEvents, DeviceFileEvents, DeviceRegistryEvents, DeviceImageLoadEvents, DeviceEvents, DeviceImageLoadEvents, IdentityLogonEvents, IdentityQueryEvents)
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
and DeviceName == deviceName
// or RemoteDeviceName == deviceName
// or DeviceId == deviceId
| take 100
```
### <a name="supported-entity-types"></a><span data-ttu-id="49012-126">지원되는 엔터티 유형</span><span class="sxs-lookup"><span data-stu-id="49012-126">Supported entity types</span></span>
<span data-ttu-id="49012-127">다음 엔터티 유형을 선택한 후 *이동* 헌트 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49012-127">You can use *go hunt* after selecting any of these entity types:</span></span>

- <span data-ttu-id="49012-128">파일</span><span class="sxs-lookup"><span data-stu-id="49012-128">Files</span></span>
- <span data-ttu-id="49012-129">전자 메일</span><span class="sxs-lookup"><span data-stu-id="49012-129">Emails</span></span>
- <span data-ttu-id="49012-130">전자 메일 클러스터</span><span class="sxs-lookup"><span data-stu-id="49012-130">Email clusters</span></span>
- <span data-ttu-id="49012-131">사서함</span><span class="sxs-lookup"><span data-stu-id="49012-131">Mailboxes</span></span>
- <span data-ttu-id="49012-132">사용자</span><span class="sxs-lookup"><span data-stu-id="49012-132">Users</span></span>
- <span data-ttu-id="49012-133">디바이스</span><span class="sxs-lookup"><span data-stu-id="49012-133">Devices</span></span>
- <span data-ttu-id="49012-134">IP 주소</span><span class="sxs-lookup"><span data-stu-id="49012-134">IP addresses</span></span>
- <span data-ttu-id="49012-135">URL</span><span class="sxs-lookup"><span data-stu-id="49012-135">URLs</span></span>

## <a name="query-for-event-information"></a><span data-ttu-id="49012-136">이벤트 정보 쿼리</span><span class="sxs-lookup"><span data-stu-id="49012-136">Query for event information</span></span>
<span data-ttu-id="49012-137">이동 *헌트에서* 타임라인 이벤트에 대한 정보를 쿼리할 때 쿼리는 모든 관련 스마마 테이블에서 선택한 이벤트 시간의 다른 이벤트를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="49012-137">When using *go hunt* to query for information about a timeline event, the query checks all relevant schema tables for other events around the time of the selected event.</span></span> <span data-ttu-id="49012-138">예를 들어 다음 쿼리는 동일한 장치에서 같은 기간 동안 발생한 여러 가지 스마마 테이블의 이벤트를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="49012-138">For example, the following query lists events in various schema tables that occurred around the same time period on the same device:</span></span>

```kusto
// List relevant events 30 minutes before and after selected LogonAttempted event
let selectedEventTimestamp = datetime(2020-06-04T01:29:09.2496688Z);
search in (DeviceFileEvents, DeviceProcessEvents, DeviceEvents, DeviceRegistryEvents, DeviceNetworkEvents, DeviceImageLoadEvents, DeviceLogonEvents)
    Timestamp between ((selectedEventTimestamp - 30m) .. (selectedEventTimestamp + 30m))
    and DeviceId == "079ecf9c5798d249128817619606c1c47369eb3e"
| sort by Timestamp desc
| extend Relevance = iff(Timestamp == selectedEventTimestamp, "Selected event", iff(Timestamp < selectedEventTimestamp, "Earlier event", "Later event"))
| project-reorder Relevance
```

## <a name="adjust-the-query"></a><span data-ttu-id="49012-139">쿼리 조정</span><span class="sxs-lookup"><span data-stu-id="49012-139">Adjust the query</span></span>
<span data-ttu-id="49012-140">쿼리 언어에 대한 [지식이](advanced-hunting-query-language.md)있는 경우 쿼리를 기본 설정에 맞게 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49012-140">With some knowledge of the [query language](advanced-hunting-query-language.md), you can adjust the query to your preference.</span></span> <span data-ttu-id="49012-141">예를 들어 시간 창의 크기를 결정하는 이 줄을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49012-141">For example, you can adjust this line, which determines the size of the time window:</span></span>

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

<span data-ttu-id="49012-142">쿼리를 수정하여 보다 관련성 높은 결과를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49012-142">In addition to modifying the query to get more relevant results, you can also:</span></span>
- [<span data-ttu-id="49012-143">결과를 차트로 보기</span><span class="sxs-lookup"><span data-stu-id="49012-143">View the results as charts</span></span>](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [<span data-ttu-id="49012-144">사용자 지정 검색 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="49012-144">Create a custom detection rule</span></span>](custom-detection-rules.md)

>[!NOTE]
><span data-ttu-id="49012-145">이 문서의 일부 테이블은 끝점용 Microsoft Defender에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="49012-145">Some tables in this article might not be available in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="49012-146">[Defender를 Microsoft 365 더](m365d-enable.md) 많은 데이터 원본을 사용하여 위협을 헌팅합니다.</span><span class="sxs-lookup"><span data-stu-id="49012-146">[Turn on Microsoft 365 Defender](m365d-enable.md) to hunt for threats using more data sources.</span></span> <span data-ttu-id="49012-147">Endpoint용 Microsoft Defender에서 고급 헌팅 Microsoft 365 마이그레이션의 단계에 따라 [Endpoint용 Microsoft Defender에서](advanced-hunting-migrate-from-mde.md)고급 헌팅 워크플로를 Microsoft 365 Defender로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49012-147">You can move your advanced hunting workflows from Microsoft Defender for Endpoint to Microsoft 365 Defender by following the steps in [Migrate advanced hunting queries from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mde.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="49012-148">관련 항목</span><span class="sxs-lookup"><span data-stu-id="49012-148">Related topics</span></span>
- [<span data-ttu-id="49012-149">지능형 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="49012-149">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="49012-150">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="49012-150">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="49012-151">쿼리 결과로 작업</span><span class="sxs-lookup"><span data-stu-id="49012-151">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="49012-152">사용자 지정 검색 규칙</span><span class="sxs-lookup"><span data-stu-id="49012-152">Custom detection rules</span></span>](custom-detection-rules.md)
