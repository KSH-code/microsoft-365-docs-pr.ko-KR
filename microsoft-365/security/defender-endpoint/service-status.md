---
title: Microsoft Defender ATP 서비스 상태 확인
description: Microsoft Defender ATP 서비스 상태 확인, 서비스에 문제가 발생하는지 확인하고 해결된 이전 문제를 검토합니다.
keywords: 대시보드, 서비스, 문제, 서비스 상태, 현재 상태, 상태 기록, 영향 요약, 예비 근본 원인, 해결, 해결 시간, 예상 해결 시간
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 45782fcce51e15adf61757d836d313d229558571
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072916"
---
# <a name="check-the-microsoft-defender-for-endpoint-service-health"></a><span data-ttu-id="86080-104">Microsoft Defender에서 끝점 서비스 상태 확인</span><span class="sxs-lookup"><span data-stu-id="86080-104">Check the Microsoft Defender for Endpoint service health</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="86080-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="86080-105">**Applies to:**</span></span>
- [<span data-ttu-id="86080-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="86080-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)



><span data-ttu-id="86080-107">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="86080-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="86080-108">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="86080-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-servicestatus-abovefoldlink)

<span data-ttu-id="86080-109">**서비스 상태는** Endpoint용 Defender 서비스의 현재 상태에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="86080-109">**Service health** provides information on the current status of the Defender for Endpoint service.</span></span> <span data-ttu-id="86080-110">서비스 상태 또는 현재 문제가 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86080-110">You'll be able to verify that the service health is healthy or if there are current issues.</span></span> <span data-ttu-id="86080-111">문제가 있는 경우 문제가 검색된 시간, 예비 근본 원인, 예상 해결 시간 등의 정보가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86080-111">If there are issues, you'll see information such as when the issue was detected, what the preliminary root cause is, and the expected resolution time.</span></span>

<span data-ttu-id="86080-112">또한 해결된 이전 문제에 대한 정보와 문제가 해결된 날짜 및 시간 등의 세부 정보도 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86080-112">You'll also see information on historical issues that have been resolved and details such as the date and time when the issue was resolved.</span></span> <span data-ttu-id="86080-113">서비스에 문제가 없는 경우 정상 상태가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86080-113">When there are no issues on the service, you'll see a healthy status.</span></span>

<span data-ttu-id="86080-114">보안 작업 대시보드에서 타일을 클릭하거나 탐색 창에서 서비스 상태 메뉴를  선택하여 서비스 상태의 세부 정보를 볼 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="86080-114">You can view details on the service health by clicking the tile from the **Security operations dashboard** or selecting the **Service health** menu from the navigation pane.</span></span>

<span data-ttu-id="86080-115">서비스 **상태** 세부 정보 페이지에는 다음 탭이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86080-115">The **Service health** details page has the following tabs:</span></span>

- <span data-ttu-id="86080-116">**현재 상태**</span><span class="sxs-lookup"><span data-stu-id="86080-116">**Current status**</span></span>
- <span data-ttu-id="86080-117">**상태 기록**</span><span class="sxs-lookup"><span data-stu-id="86080-117">**Status history**</span></span>

## <a name="current-status"></a><span data-ttu-id="86080-118">현재 상태</span><span class="sxs-lookup"><span data-stu-id="86080-118">Current status</span></span>
<span data-ttu-id="86080-119">현재 **상태 탭에는** Endpoint 서비스용 Defender의 현재 상태가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86080-119">The **Current status** tab shows the current state of the Defender for Endpoint service.</span></span> <span data-ttu-id="86080-120">서비스가 원활하게 실행되는 경우 서비스 상태는 정상으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86080-120">When the service is running smoothly a healthy service health is shown.</span></span> <span data-ttu-id="86080-121">문제가 있는 경우 문제에 대한 더 나은 정보를 얻을 수 있도록 다음과 같은 서비스 세부 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86080-121">If there are issues seen, the following service details are shown to help you gain better insight about the issue:</span></span>

- <span data-ttu-id="86080-122">문제가 검색된 날짜 및 시간</span><span class="sxs-lookup"><span data-stu-id="86080-122">Date and time for when the issue was detected</span></span>
- <span data-ttu-id="86080-123">문제의 간단한 설명</span><span class="sxs-lookup"><span data-stu-id="86080-123">A short description of the issue</span></span>
- <span data-ttu-id="86080-124">업데이트 시간</span><span class="sxs-lookup"><span data-stu-id="86080-124">Update time</span></span>
- <span data-ttu-id="86080-125">영향 요약</span><span class="sxs-lookup"><span data-stu-id="86080-125">Summary of impact</span></span>
- <span data-ttu-id="86080-126">예비 근본 원인</span><span class="sxs-lookup"><span data-stu-id="86080-126">Preliminary root cause</span></span>
- <span data-ttu-id="86080-127">다음 단계</span><span class="sxs-lookup"><span data-stu-id="86080-127">Next steps</span></span>
- <span data-ttu-id="86080-128">예상 해결 시간</span><span class="sxs-lookup"><span data-stu-id="86080-128">Expected resolution time</span></span>

<span data-ttu-id="86080-129">문제가 해결되면 문제 진행률에 대한 업데이트가 페이지에 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="86080-129">Updates on the progress of an issue are reflected on the page as the issue gets resolved.</span></span> <span data-ttu-id="86080-130">업데이트된 예상 해결 시간 또는 다음 단계와 같은 정보에 대한 업데이트가 표시될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="86080-130">You'll see updates on information such as an updated estimate resolution time or next steps.</span></span>

<span data-ttu-id="86080-131">문제가 해결되면 상태 기록 탭에 **기록됩니다.**</span><span class="sxs-lookup"><span data-stu-id="86080-131">When an issue is resolved, it gets recorded in the **Status history** tab.</span></span>

## <a name="status-history"></a><span data-ttu-id="86080-132">상태 기록</span><span class="sxs-lookup"><span data-stu-id="86080-132">Status history</span></span>
<span data-ttu-id="86080-133">상태 **기록 탭에는** 표시 및 해결된 모든 이전 문제가 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="86080-133">The **Status history** tab reflects all the historical issues that were seen and resolved.</span></span> <span data-ttu-id="86080-134">해결된 문제에 대한 세부 정보와 해결되는 동안 포함된 다른 정보가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86080-134">You'll see details of the resolved issues along with the other information that were included while it was being resolved.</span></span>

### <a name="related-topic"></a><span data-ttu-id="86080-135">관련 항목</span><span class="sxs-lookup"><span data-stu-id="86080-135">Related topic</span></span>
- [<span data-ttu-id="86080-136">보안 작업 대시보드 보기</span><span class="sxs-lookup"><span data-stu-id="86080-136">View the Security operations dashboard</span></span>](security-operations-dashboard.md)
