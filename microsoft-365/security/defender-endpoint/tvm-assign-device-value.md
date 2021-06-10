---
title: 장치 값 할당 - 위협 및 취약성 관리
description: 자산 우선 순위를 차별화하는 데 도움이 될 수 있도록 장치에 낮은 값, 보통 또는 높은 값을 할당하는 방법을 배워야 합니다.
keywords: Microsoft Defender for Endpoint 장치 값, 위협 및 취약성 관리 값, 높은 값 장치, 장치 값 노출 점수
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ca6c88b08b331eb65035387a9c070d0914b1651d
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935200"
---
# <a name="assign-device-value---threat-and-vulnerability-management"></a><span data-ttu-id="a3c14-104">장치 값 할당 - 위협 및 취약성 관리</span><span class="sxs-lookup"><span data-stu-id="a3c14-104">Assign device value - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a3c14-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="a3c14-105">**Applies to:**</span></span>

- [<span data-ttu-id="a3c14-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a3c14-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="a3c14-107">위협 및 취약성 관리</span><span class="sxs-lookup"><span data-stu-id="a3c14-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="a3c14-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a3c14-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a3c14-109">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="a3c14-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a3c14-110">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="a3c14-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="a3c14-111">디바이스의 값을 정의하면 자산 우선 순위를 차별화하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3c14-111">Defining a device’s value helps you differentiate between asset priorities.</span></span> <span data-ttu-id="a3c14-112">디바이스 값은 노출 점수 계산에 개별 자산의 위험 위협 및 취약성 관리 통합하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3c14-112">The device value is used to incorporate the risk appetite of an individual asset into the threat and vulnerability management exposure score calculation.</span></span> <span data-ttu-id="a3c14-113">"높은 값"으로 할당된 장치는 더 많은 가중치를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3c14-113">Devices assigned as “high value” will receive more weight.</span></span>

<span data-ttu-id="a3c14-114">설정 장치 값 [API 를 사용할 수 있습니다.](set-device-value.md)</span><span class="sxs-lookup"><span data-stu-id="a3c14-114">You can also use the [set device value API](set-device-value.md).</span></span>

<span data-ttu-id="a3c14-115">디바이스 값 옵션:</span><span class="sxs-lookup"><span data-stu-id="a3c14-115">Device value options:</span></span>

- <span data-ttu-id="a3c14-116">낮음</span><span class="sxs-lookup"><span data-stu-id="a3c14-116">Low</span></span>
- <span data-ttu-id="a3c14-117">보통(기본값)</span><span class="sxs-lookup"><span data-stu-id="a3c14-117">Normal (Default)</span></span>
- <span data-ttu-id="a3c14-118">높음</span><span class="sxs-lookup"><span data-stu-id="a3c14-118">High</span></span>

<span data-ttu-id="a3c14-119">높은 값을 할당해야 하는 장치의 예:</span><span class="sxs-lookup"><span data-stu-id="a3c14-119">Examples of devices that should be assigned a high value:</span></span>

- <span data-ttu-id="a3c14-120">도메인 컨트롤러, Active Directory</span><span class="sxs-lookup"><span data-stu-id="a3c14-120">Domain controllers, Active Directory</span></span>
- <span data-ttu-id="a3c14-121">인터넷 연결 장치</span><span class="sxs-lookup"><span data-stu-id="a3c14-121">Internet facing devices</span></span>
- <span data-ttu-id="a3c14-122">VIP 장치</span><span class="sxs-lookup"><span data-stu-id="a3c14-122">VIP devices</span></span>
- <span data-ttu-id="a3c14-123">내부/외부 프로덕션 서비스를 호스팅하는 장치</span><span class="sxs-lookup"><span data-stu-id="a3c14-123">Devices hosting internal/external production services</span></span>

## <a name="choose-device-value"></a><span data-ttu-id="a3c14-124">장치 값 선택</span><span class="sxs-lookup"><span data-stu-id="a3c14-124">Choose device value</span></span>

1. <span data-ttu-id="a3c14-125">장치 페이지로 이동하는 것이 장치 인벤토리에서 가장 쉬운 장소입니다.</span><span class="sxs-lookup"><span data-stu-id="a3c14-125">Navigate to any device page, the easiest place is from the device inventory.</span></span>

2. <span data-ttu-id="a3c14-126">페이지 **위쪽의** 작업 표시줄 옆에 있는 세 점에서 장치 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a3c14-126">Select **Device value** from three dots next to the actions bar at the top of the page.</span></span>

    ![장치 값 드롭다운의 예입니다.](images/tvm-device-value-dropdown.png)

3. <span data-ttu-id="a3c14-128">플라이아웃은 현재 디바이스 값 및 의미와 함께 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3c14-128">A flyout will appear with the current device value and what it means.</span></span> <span data-ttu-id="a3c14-129">디바이스의 값을 검토하고 장치에 가장 적합한 값을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="a3c14-129">Review the value of the device and choose the one that best fits your device.</span></span>
<span data-ttu-id="a3c14-130">![장치 값 플라이아웃의 예입니다.](images/tvm-device-value-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="a3c14-130">![Example of the device value flyout.](images/tvm-device-value-flyout.png)</span></span>

## <a name="how-device-value-impacts-your-exposure-score"></a><span data-ttu-id="a3c14-131">디바이스 값이 노출 점수에 미치는 영향</span><span class="sxs-lookup"><span data-stu-id="a3c14-131">How device value impacts your exposure score</span></span>

<span data-ttu-id="a3c14-132">노출 점수는 모든 디바이스에서 가중 평균입니다.</span><span class="sxs-lookup"><span data-stu-id="a3c14-132">The exposure score is a weighted average across all devices.</span></span> <span data-ttu-id="a3c14-133">장치 그룹이 있는 경우 장치 그룹으로 점수를 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3c14-133">If you have device groups, you can also filter the score by device group.</span></span>

- <span data-ttu-id="a3c14-134">일반 디바이스의 가중치 1</span><span class="sxs-lookup"><span data-stu-id="a3c14-134">Normal devices have a weight of 1</span></span>
- <span data-ttu-id="a3c14-135">낮은 값 디바이스의 가중치가 0.75입니다.</span><span class="sxs-lookup"><span data-stu-id="a3c14-135">Low value devices have a weight of 0.75</span></span>
- <span data-ttu-id="a3c14-136">값이 높은 디바이스는 NumberOfAssets /10의 가중치를 가중치로 가중치가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3c14-136">High value devices have a weight of NumberOfAssets / 10.</span></span>
    - <span data-ttu-id="a3c14-137">디바이스가 100개인 경우 각 고가치 디바이스의 가중치가 10(100/10)입니다.</span><span class="sxs-lookup"><span data-stu-id="a3c14-137">If you have 100 devices, each high value device will have a weight of 10 (100/10)</span></span>

## <a name="related-topics"></a><span data-ttu-id="a3c14-138">관련 항목</span><span class="sxs-lookup"><span data-stu-id="a3c14-138">Related topics</span></span>

- [<span data-ttu-id="a3c14-139">위협 및 취약성 관리 개요</span><span class="sxs-lookup"><span data-stu-id="a3c14-139">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="a3c14-140">노출 점수</span><span class="sxs-lookup"><span data-stu-id="a3c14-140">Exposure Score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="a3c14-141">API</span><span class="sxs-lookup"><span data-stu-id="a3c14-141">APIs</span></span>](next-gen-threat-and-vuln-mgt.md#apis)