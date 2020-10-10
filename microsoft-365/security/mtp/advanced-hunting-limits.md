---
title: Microsoft Threat Protection의 고급 구하기 제한
description: Advanced 사냥 서비스의 응답성을 유지 하는 다양 한 서비스 제한 이해
keywords: 고급 구하기, 위협 검색, 사이버 위협 사냥, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 스키마, kusto, CPU 제한, 쿼리 제한, 리소스, 최대 결과
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: ad21b4241d7cbbcc85639a0a10b47971e5fcebcb
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412697"
---
# <a name="advanced-hunting-service-limits"></a><span data-ttu-id="03b1b-104">고급 구하기 서비스 제한</span><span class="sxs-lookup"><span data-stu-id="03b1b-104">Advanced hunting service limits</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="03b1b-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="03b1b-105">**Applies to:**</span></span>
- <span data-ttu-id="03b1b-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="03b1b-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="03b1b-107">서비스의 성능과 응답성을 유지 하기 위해 고급 구하기에서는 수동으로 실행 되는 쿼리와 [사용자 지정 검색 규칙](custom-detection-rules.md)에 따라 다양 한 제한이 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03b1b-107">To keep the service performant and responsive, advanced hunting sets various limits for queries run manually and by [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="03b1b-108">이러한 제한을 이해 하려면 다음 표를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="03b1b-108">Refer to the following table to understand these limits.</span></span>

| <span data-ttu-id="03b1b-109">Limit</span><span class="sxs-lookup"><span data-stu-id="03b1b-109">Limit</span></span> | <span data-ttu-id="03b1b-110">크기</span><span class="sxs-lookup"><span data-stu-id="03b1b-110">Size</span></span> | <span data-ttu-id="03b1b-111">새로 고침 주기</span><span class="sxs-lookup"><span data-stu-id="03b1b-111">Refresh cycle</span></span> | <span data-ttu-id="03b1b-112">설명</span><span class="sxs-lookup"><span data-stu-id="03b1b-112">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="03b1b-113">데이터 범위</span><span class="sxs-lookup"><span data-stu-id="03b1b-113">Data range</span></span> | <span data-ttu-id="03b1b-114">30일</span><span class="sxs-lookup"><span data-stu-id="03b1b-114">30 days</span></span> | <span data-ttu-id="03b1b-115">모든 쿼리</span><span class="sxs-lookup"><span data-stu-id="03b1b-115">Every query</span></span> | <span data-ttu-id="03b1b-116">각 쿼리는 최근 30 일까지 데이터를 조회할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03b1b-116">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="03b1b-117">결과 집합</span><span class="sxs-lookup"><span data-stu-id="03b1b-117">Result set</span></span> | <span data-ttu-id="03b1b-118">1만 행</span><span class="sxs-lookup"><span data-stu-id="03b1b-118">10,000 rows</span></span> | <span data-ttu-id="03b1b-119">모든 쿼리</span><span class="sxs-lookup"><span data-stu-id="03b1b-119">Every query</span></span> | <span data-ttu-id="03b1b-120">각 쿼리는 최대 1만 개의 레코드를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03b1b-120">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="03b1b-121">대기</span><span class="sxs-lookup"><span data-stu-id="03b1b-121">Timeout</span></span> | <span data-ttu-id="03b1b-122">10분</span><span class="sxs-lookup"><span data-stu-id="03b1b-122">10 minutes</span></span> | <span data-ttu-id="03b1b-123">모든 쿼리</span><span class="sxs-lookup"><span data-stu-id="03b1b-123">Every query</span></span> | <span data-ttu-id="03b1b-124">각 쿼리를 최대 10 분까지 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03b1b-124">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="03b1b-125">10 분 이내에 완료 되지 않으면 서비스에서 오류를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="03b1b-125">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="03b1b-126">CPU 리소스</span><span class="sxs-lookup"><span data-stu-id="03b1b-126">CPU resources</span></span> | <span data-ttu-id="03b1b-127">테 넌 트 크기 기반</span><span class="sxs-lookup"><span data-stu-id="03b1b-127">Based on tenant size</span></span> | <span data-ttu-id="03b1b-128">-1 시간 후 15 분 마다</span><span class="sxs-lookup"><span data-stu-id="03b1b-128">- On the hour and then every 15 minutes</span></span><br><span data-ttu-id="03b1b-129">-매일 자정 12 시</span><span class="sxs-lookup"><span data-stu-id="03b1b-129">- Daily at 12 midnight</span></span> | <span data-ttu-id="03b1b-130">서비스는 매일 및 15 분 제한을 개별적으로 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="03b1b-130">The service enforces the daily and the 15-minute limit separately.</span></span> <span data-ttu-id="03b1b-131">각 제한에 대해 쿼리를 실행 하 고 테 넌 트에서 할당 된 리소스의 10%를 초과 하 여 사용 하는 경우에는 [포털에 오류가 표시 됩니다](advanced-hunting-errors.md) .</span><span class="sxs-lookup"><span data-stu-id="03b1b-131">For each limit, the [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="03b1b-132">다음 매일 또는 15 분 주기로 인해 테 넌 트가 다음 시간까지 100%에 도달 하면 쿼리가 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03b1b-132">Queries are blocked if the tenant has reached 100% until after the next daily or 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="03b1b-133">별도의 제한 집합은 API를 통해 수행 되는 고급 구하기 쿼리에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03b1b-133">A separate set of limits apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="03b1b-134">고급 구하기 Api에 대 한 정보</span><span class="sxs-lookup"><span data-stu-id="03b1b-134">Read about advanced hunting APIs</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

<span data-ttu-id="03b1b-135">정기적으로 여러 쿼리를 실행 하는 고객은 사용을 추적 하 고 [최적화 모범 사례를 적용](advanced-hunting-best-practices.md) 하 여 이러한 제한을 초과 하지 못하도록 하는 장애를 최소화 합니다.</span><span class="sxs-lookup"><span data-stu-id="03b1b-135">Customers who run multiple queries regularly should track consumption and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruption resulting from exceeding these limits.</span></span>

## <a name="related-topics"></a><span data-ttu-id="03b1b-136">관련 항목</span><span class="sxs-lookup"><span data-stu-id="03b1b-136">Related topics</span></span>

- [<span data-ttu-id="03b1b-137">고급 구하기 모범 사례</span><span class="sxs-lookup"><span data-stu-id="03b1b-137">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="03b1b-138">고급 구하기 오류 처리</span><span class="sxs-lookup"><span data-stu-id="03b1b-138">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="03b1b-139">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="03b1b-139">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="03b1b-140">사용자 지정 검색 개요</span><span class="sxs-lookup"><span data-stu-id="03b1b-140">Custom detections overview</span></span>](custom-detections-overview.md)
