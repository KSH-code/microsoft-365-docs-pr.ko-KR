---
title: Microsoft Defender ATP의 고급 헌팅 제한
description: 고급 헌팅 서비스를 응답하도록 유지하는 다양한 서비스 제한 이해
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, mdatp, microsoft defender atp, wdatp, 검색, 쿼리, 원격 분석, schema, kusto, CPU 제한, 쿼리 제한, 리소스, 최대 결과
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 127ebc8c0eaba433710bc272a2cf602e7c9a9730
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075983"
---
# <a name="advanced-hunting-service-limits"></a><span data-ttu-id="2ca82-104">고급 헌팅 서비스 제한</span><span class="sxs-lookup"><span data-stu-id="2ca82-104">Advanced hunting service limits</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2ca82-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="2ca82-105">**Applies to:**</span></span>
- [<span data-ttu-id="2ca82-106">엔드포인트용 Defender</span><span class="sxs-lookup"><span data-stu-id="2ca82-106">Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="2ca82-107">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="2ca82-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2ca82-108">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="2ca82-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

<span data-ttu-id="2ca82-109">서비스 성능이 뛰어난 응답성을 유지하기 위해 고급 헌팅은 사용자 지정 검색 규칙에 따라 수동으로 실행되는 쿼리에 대한 다양한 [제한을 설정합니다.](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="2ca82-109">To keep the service performant and responsive, advanced hunting sets various limits for queries run manually and by [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="2ca82-110">이러한 제한을 이해하기 위해 다음 표를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="2ca82-110">Refer to the following table to understand these limits.</span></span>

| <span data-ttu-id="2ca82-111">제한</span><span class="sxs-lookup"><span data-stu-id="2ca82-111">Limit</span></span> | <span data-ttu-id="2ca82-112">Size</span><span class="sxs-lookup"><span data-stu-id="2ca82-112">Size</span></span> | <span data-ttu-id="2ca82-113">새로 고침 주기</span><span class="sxs-lookup"><span data-stu-id="2ca82-113">Refresh cycle</span></span> | <span data-ttu-id="2ca82-114">설명</span><span class="sxs-lookup"><span data-stu-id="2ca82-114">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="2ca82-115">데이터 범위</span><span class="sxs-lookup"><span data-stu-id="2ca82-115">Data range</span></span> | <span data-ttu-id="2ca82-116">30일</span><span class="sxs-lookup"><span data-stu-id="2ca82-116">30 days</span></span> | <span data-ttu-id="2ca82-117">모든 쿼리</span><span class="sxs-lookup"><span data-stu-id="2ca82-117">Every query</span></span> | <span data-ttu-id="2ca82-118">각 쿼리는 최대 30일 동안의 데이터를 조회할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ca82-118">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="2ca82-119">결과 집합</span><span class="sxs-lookup"><span data-stu-id="2ca82-119">Result set</span></span> | <span data-ttu-id="2ca82-120">행 10,000개</span><span class="sxs-lookup"><span data-stu-id="2ca82-120">10,000 rows</span></span> | <span data-ttu-id="2ca82-121">모든 쿼리</span><span class="sxs-lookup"><span data-stu-id="2ca82-121">Every query</span></span> | <span data-ttu-id="2ca82-122">각 쿼리는 최대 10,000개 레코드를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ca82-122">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="2ca82-123">시간 제한</span><span class="sxs-lookup"><span data-stu-id="2ca82-123">Timeout</span></span> | <span data-ttu-id="2ca82-124">10분</span><span class="sxs-lookup"><span data-stu-id="2ca82-124">10 minutes</span></span> | <span data-ttu-id="2ca82-125">모든 쿼리</span><span class="sxs-lookup"><span data-stu-id="2ca82-125">Every query</span></span> | <span data-ttu-id="2ca82-126">각 쿼리는 최대 10분 동안 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ca82-126">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="2ca82-127">10분 내에 완료되지 않은 경우 서비스에 오류가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ca82-127">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="2ca82-128">CPU 리소스</span><span class="sxs-lookup"><span data-stu-id="2ca82-128">CPU resources</span></span> | <span data-ttu-id="2ca82-129">테넌트 크기 기반</span><span class="sxs-lookup"><span data-stu-id="2ca82-129">Based on tenant size</span></span> | <span data-ttu-id="2ca82-130">- 시간 및 15분마다</span><span class="sxs-lookup"><span data-stu-id="2ca82-130">- On the hour and then every 15 minutes</span></span><br><span data-ttu-id="2ca82-131">- 매일 자정 12시</span><span class="sxs-lookup"><span data-stu-id="2ca82-131">- Daily at 12 midnight</span></span> | <span data-ttu-id="2ca82-132">이 서비스는 일별 및 15분 제한을 별도로 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="2ca82-132">The service enforces the daily and the 15-minute limit separately.</span></span> <span data-ttu-id="2ca82-133">각 제한에 [](advanced-hunting-errors.md) 대해 포털은 쿼리가 실행될 때마다 테넌트가 할당된 리소스의 10% 이상을 소비할 때마다 오류를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2ca82-133">For each limit, the [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="2ca82-134">테넌트가 매일 또는 15분 주기가 끝날 때까지 100%에 도달하면 쿼리가 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ca82-134">Queries are blocked if the tenant has reached 100% until after the next daily or 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="2ca82-135">API를 통해 수행되는 고급 헌팅 쿼리에는 별도의 제한 집합이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ca82-135">A separate set of limits apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="2ca82-136">고급 헌팅 API에 대한 읽기</span><span class="sxs-lookup"><span data-stu-id="2ca82-136">Read about advanced hunting APIs</span></span>](run-advanced-query-api.md)

<span data-ttu-id="2ca82-137">여러 쿼리를 정기적으로 실행하는 고객은 [](advanced-hunting-best-practices.md) 사용량을 추적하고 최적화 모범 사례를 적용하여 이러한 제한을 초과하여 발생하는 중단을 최소화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ca82-137">Customers who run multiple queries regularly should track consumption and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruption resulting from exceeding these limits.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2ca82-138">관련 항목</span><span class="sxs-lookup"><span data-stu-id="2ca82-138">Related topics</span></span>

- [<span data-ttu-id="2ca82-139">고급 헌팅 모범 사례</span><span class="sxs-lookup"><span data-stu-id="2ca82-139">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="2ca82-140">고급 헌팅 오류 처리</span><span class="sxs-lookup"><span data-stu-id="2ca82-140">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="2ca82-141">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="2ca82-141">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2ca82-142">사용자 지정 검색 규칙</span><span class="sxs-lookup"><span data-stu-id="2ca82-142">Custom detections rules</span></span>](custom-detection-rules.md)
