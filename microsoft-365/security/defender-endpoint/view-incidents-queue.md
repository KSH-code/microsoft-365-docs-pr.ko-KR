---
title: 인시던트 큐 보기 및 구성
ms.reviewer: ''
description: 인시던트 목록을 보고 필터를 적용하여 목록을 제한하고 보다 집중적인 보기를 얻을 수 있는 방법을 배워야 합니다.
keywords: 보기, 구성, 인시던트, 집계, 조사, 큐, ttp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f25189ac6550d9c3349e08f7e7ac685d4b8031fc
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071772"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-incidents-queue"></a><span data-ttu-id="9dd2d-104">끝점 인시던트에 대한 Microsoft Defender 큐 보기 및 구성</span><span class="sxs-lookup"><span data-stu-id="9dd2d-104">View and organize the Microsoft Defender for Endpoint Incidents queue</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9dd2d-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="9dd2d-105">**Applies to:**</span></span>
- [<span data-ttu-id="9dd2d-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="9dd2d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="9dd2d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9dd2d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="9dd2d-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="9dd2d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="9dd2d-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="9dd2d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

<span data-ttu-id="9dd2d-110">**인시던트 큐에는** 네트워크의 장치에서 플래그가 지정된 인시던트 모음이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dd2d-110">The **Incidents queue** shows a collection of incidents that were flagged from devices in your network.</span></span> <span data-ttu-id="9dd2d-111">이 기능은 사고 우선순위를 정하고 사이버 보안 반응 결정을 내리는 데 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9dd2d-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>

<span data-ttu-id="9dd2d-112">기본적으로 큐에는 지난 30일 동안의 인시던트가 표시되고, 가장 최근 인시던트가 목록 맨 위에 표시되어 가장 최근 인시던트가 먼저 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dd2d-112">By default, the queue displays incidents seen in the last 30 days, with the most recent incident showing at the top of the list, helping you see the most recent incidents first.</span></span>

<span data-ttu-id="9dd2d-113">인시던트 큐 보기를 사용자 지정하기 위해 선택할 수 있는 몇 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dd2d-113">There are several options you can choose from to customize the Incidents queue view.</span></span> 

<span data-ttu-id="9dd2d-114">위쪽 탐색에서 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dd2d-114">On the top navigation you can:</span></span>
- <span data-ttu-id="9dd2d-115">열을 추가 또는 제거하기 위해 열 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="9dd2d-115">Customize columns to add or remove columns</span></span> 
- <span data-ttu-id="9dd2d-116">페이지당 볼 항목 수 수정</span><span class="sxs-lookup"><span data-stu-id="9dd2d-116">Modify the number of items to view per page</span></span>
- <span data-ttu-id="9dd2d-117">페이지당 표시할 항목 선택</span><span class="sxs-lookup"><span data-stu-id="9dd2d-117">Select the items to show per page</span></span>
- <span data-ttu-id="9dd2d-118">할당할 인시던트 선택 일괄 처리</span><span class="sxs-lookup"><span data-stu-id="9dd2d-118">Batch-select the incidents to assign</span></span> 
- <span data-ttu-id="9dd2d-119">페이지 간 탐색</span><span class="sxs-lookup"><span data-stu-id="9dd2d-119">Navigate between pages</span></span>
- <span data-ttu-id="9dd2d-120">필터 적용</span><span class="sxs-lookup"><span data-stu-id="9dd2d-120">Apply filters</span></span>

![사고 큐의 이미지](images/atp-incident-queue.png)

## <a name="sort-and-filter-the-incidents-queue"></a><span data-ttu-id="9dd2d-122">인시던트 큐 정렬 및 필터링</span><span class="sxs-lookup"><span data-stu-id="9dd2d-122">Sort and filter the incidents queue</span></span>
<span data-ttu-id="9dd2d-123">다음 필터를 적용하여 인시던트 목록을 제한하고 보다 집중적인 보기를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dd2d-123">You can apply the following filters to limit the list of incidents and get a more focused view.</span></span>

### <a name="severity"></a><span data-ttu-id="9dd2d-124">심각도</span><span class="sxs-lookup"><span data-stu-id="9dd2d-124">Severity</span></span>

<span data-ttu-id="9dd2d-125">인시던트 심각도</span><span class="sxs-lookup"><span data-stu-id="9dd2d-125">Incident severity</span></span> | <span data-ttu-id="9dd2d-126">설명</span><span class="sxs-lookup"><span data-stu-id="9dd2d-126">Description</span></span>
:---|:---
<span data-ttu-id="9dd2d-127">높음</span><span class="sxs-lookup"><span data-stu-id="9dd2d-127">High</span></span> </br><span data-ttu-id="9dd2d-128">(빨강)</span><span class="sxs-lookup"><span data-stu-id="9dd2d-128">(Red)</span></span> | <span data-ttu-id="9dd2d-129">APT(고급 영구 위협)와 자주 관련된 위협.</span><span class="sxs-lookup"><span data-stu-id="9dd2d-129">Threats often associated with advanced persistent threats (APT).</span></span> <span data-ttu-id="9dd2d-130">이러한 인시던트는 장치에 노출될 수 있는 손상의 심각도로 인해 높은 위험을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9dd2d-130">These incidents indicate a high risk due to the severity of damage they can inflict on devices.</span></span>
<span data-ttu-id="9dd2d-131">보통</span><span class="sxs-lookup"><span data-stu-id="9dd2d-131">Medium</span></span> </br><span data-ttu-id="9dd2d-132">(주황색)</span><span class="sxs-lookup"><span data-stu-id="9dd2d-132">(Orange)</span></span> | <span data-ttu-id="9dd2d-133">일반적인 레지스트리 변경, 의심스러운 파일 실행, 공격 단계의 일반적인 관찰 동작 등 조직에서 거의 발견되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9dd2d-133">Threats rarely observed in the organization, such as anomalous registry change, execution of suspicious files, and observed behaviors typical of attack stages.</span></span>
<span data-ttu-id="9dd2d-134">낮음</span><span class="sxs-lookup"><span data-stu-id="9dd2d-134">Low</span></span> </br><span data-ttu-id="9dd2d-135">(노란색)</span><span class="sxs-lookup"><span data-stu-id="9dd2d-135">(Yellow)</span></span> | <span data-ttu-id="9dd2d-136">조직을 대상으로 하는 고급 위협을 나타낼 필요는 없는, 보급된 맬웨어 및 해킹 도구와 관련된 위협.</span><span class="sxs-lookup"><span data-stu-id="9dd2d-136">Threats associated with prevalent malware and hack-tools that do not necessarily indicate an advanced threat targeting the organization.</span></span>
<span data-ttu-id="9dd2d-137">정보</span><span class="sxs-lookup"><span data-stu-id="9dd2d-137">Informational</span></span> </br><span data-ttu-id="9dd2d-138">(회색)</span><span class="sxs-lookup"><span data-stu-id="9dd2d-138">(Grey)</span></span> | <span data-ttu-id="9dd2d-139">정보 인시던트는 네트워크에 해로운 것으로 간주되지는 않지만 추적하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9dd2d-139">Informational incidents might not be considered harmful to the network but might be good to keep track of.</span></span>

## <a name="assigned-to"></a><span data-ttu-id="9dd2d-140">할당된 사용자</span><span class="sxs-lookup"><span data-stu-id="9dd2d-140">Assigned to</span></span>
<span data-ttu-id="9dd2d-141">필터를 사용하여 특정 담당자에게 할당 된 목록이나 자신에게 할당된 목록을 선택할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="9dd2d-141">You can choose to filter the list by selecting assigned to anyone or ones that are assigned to you.</span></span>

### <a name="category"></a><span data-ttu-id="9dd2d-142">범주</span><span class="sxs-lookup"><span data-stu-id="9dd2d-142">Category</span></span>
<span data-ttu-id="9dd2d-143">인시던트는 사이버 보안 킬체인이 있는 단계에 대한 설명에 따라 분류됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dd2d-143">Incidents are categorized based on the description of the stage by which the cybersecurity kill chain is in.</span></span> <span data-ttu-id="9dd2d-144">이 보기는 위협 분석가가 컨텍스트에 따라 배포할 우선 순위, 긴급성 및 해당 응답 전략을 결정하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dd2d-144">This view helps the threat analyst to determine priority, urgency, and corresponding response strategy to deploy based on context.</span></span>

### <a name="status"></a><span data-ttu-id="9dd2d-145">상태</span><span class="sxs-lookup"><span data-stu-id="9dd2d-145">Status</span></span>
<span data-ttu-id="9dd2d-146">상태에 따라 표시 되는 사고의 목록을 제한하여 활성 또는 해결 완료 된 사고를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dd2d-146">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="9dd2d-147">데이터 민감도</span><span class="sxs-lookup"><span data-stu-id="9dd2d-147">Data sensitivity</span></span>
<span data-ttu-id="9dd2d-148">이 필터를 사용하여 민감도 레이블이 포함된 인시던트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dd2d-148">Use this filter to show incidents that contain sensitivity labels.</span></span>

## <a name="incident-naming"></a><span data-ttu-id="9dd2d-149">인시던트 이름</span><span class="sxs-lookup"><span data-stu-id="9dd2d-149">Incident naming</span></span>

<span data-ttu-id="9dd2d-150">인시던트의 범위를 한눈에 이해하기 위해 인시던트 이름은 영향을 받는 끝점 수, 영향을 받는 사용자, 검색 원본 또는 범주와 같은 경고 특성에 따라 자동으로 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dd2d-150">To understand the incident's scope at a glance, incident names are automatically generated based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span>

<span data-ttu-id="9dd2d-151">예: 여러 원본에서 보고한 여러 끝점의 다단계 *인시던트*</span><span class="sxs-lookup"><span data-stu-id="9dd2d-151">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="9dd2d-152">자동 인시던트 명명을 출시하기 전에 존재한 인시던트의 이름은 그대로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dd2d-152">Incidents that existed prior the rollout of automatic incident naming will retain their name.</span></span>


## <a name="see-also"></a><span data-ttu-id="9dd2d-153">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9dd2d-153">See also</span></span>
- [<span data-ttu-id="9dd2d-154">인시던트 큐</span><span class="sxs-lookup"><span data-stu-id="9dd2d-154">Incidents queue</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [<span data-ttu-id="9dd2d-155">인시던트 관리</span><span class="sxs-lookup"><span data-stu-id="9dd2d-155">Manage incidents</span></span>](manage-incidents.md)
- [<span data-ttu-id="9dd2d-156">사고 조사</span><span class="sxs-lookup"><span data-stu-id="9dd2d-156">Investigate incidents</span></span>](investigate-incidents.md)

