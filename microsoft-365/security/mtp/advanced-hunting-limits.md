---
title: Microsoft 365 Defender의 고급 구하기 할당량 및 사용 현황 매개 변수
description: 고급 구하기 서비스의 응답성을 유지 하는 다양 한 할당량 및 사용 매개 변수 (서비스 제한) 이해
keywords: 고급 구하기, 위협 검색, 사이버 위협 사냥, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 스키마, kusto, CPU 제한, 쿼리 제한, 리소스, 최대 결과, 할당량, 매개 변수, 할당
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
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: bab63d9e5939f87f6a1edbf62d256b82552e4fe9
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847371"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a><span data-ttu-id="ad69e-104">고급 구하기 할당량 및 사용 현황 매개 변수</span><span class="sxs-lookup"><span data-stu-id="ad69e-104">Advanced hunting quotas and usage parameters</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ad69e-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="ad69e-105">**Applies to:**</span></span>
- <span data-ttu-id="ad69e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ad69e-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="ad69e-107">서비스의 성능과 응답성을 유지 하기 위해 고급 사냥은 다양 한 할당량 및 사용 현황 매개 변수 ("서비스 제한"이 라고도 함)를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad69e-107">To keep the service performant and responsive, advanced hunting sets various quotas and usage parameters (also known as "service limits").</span></span> <span data-ttu-id="ad69e-108">이러한 할당량 및 매개 변수는 수동으로 실행 되는 쿼리와 [사용자 지정 검색 규칙](custom-detection-rules.md)에 따라 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad69e-108">These quotas and parameters apply to queries run manually and by [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="ad69e-109">정기적으로 여러 쿼리를 실행 하는 고객은 소비를 추적 하 고, 중단을 최소화 하기 위한 [최적화 모범 사례를 적용](advanced-hunting-best-practices.md) 해야 합니다</span><span class="sxs-lookup"><span data-stu-id="ad69e-109">Customers who run multiple queries regularly should track consumption and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruptions.</span></span>

<span data-ttu-id="ad69e-110">기존 할당량과 사용 매개 변수를 이해 하려면 다음 표를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ad69e-110">Refer to the following table to understand existing quotas and usage parameters.</span></span>

| <span data-ttu-id="ad69e-111">Quota 또는 parameter</span><span class="sxs-lookup"><span data-stu-id="ad69e-111">Quota or parameter</span></span> | <span data-ttu-id="ad69e-112">크기</span><span class="sxs-lookup"><span data-stu-id="ad69e-112">Size</span></span> | <span data-ttu-id="ad69e-113">새로 고침 주기</span><span class="sxs-lookup"><span data-stu-id="ad69e-113">Refresh cycle</span></span> | <span data-ttu-id="ad69e-114">설명</span><span class="sxs-lookup"><span data-stu-id="ad69e-114">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="ad69e-115">데이터 범위</span><span class="sxs-lookup"><span data-stu-id="ad69e-115">Data range</span></span> | <span data-ttu-id="ad69e-116">30일</span><span class="sxs-lookup"><span data-stu-id="ad69e-116">30 days</span></span> | <span data-ttu-id="ad69e-117">모든 쿼리</span><span class="sxs-lookup"><span data-stu-id="ad69e-117">Every query</span></span> | <span data-ttu-id="ad69e-118">각 쿼리는 최근 30 일까지 데이터를 조회할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad69e-118">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="ad69e-119">결과 집합</span><span class="sxs-lookup"><span data-stu-id="ad69e-119">Result set</span></span> | <span data-ttu-id="ad69e-120">1만 행</span><span class="sxs-lookup"><span data-stu-id="ad69e-120">10,000 rows</span></span> | <span data-ttu-id="ad69e-121">모든 쿼리</span><span class="sxs-lookup"><span data-stu-id="ad69e-121">Every query</span></span> | <span data-ttu-id="ad69e-122">각 쿼리는 최대 1만 개의 레코드를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad69e-122">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="ad69e-123">대기</span><span class="sxs-lookup"><span data-stu-id="ad69e-123">Timeout</span></span> | <span data-ttu-id="ad69e-124">10분</span><span class="sxs-lookup"><span data-stu-id="ad69e-124">10 minutes</span></span> | <span data-ttu-id="ad69e-125">모든 쿼리</span><span class="sxs-lookup"><span data-stu-id="ad69e-125">Every query</span></span> | <span data-ttu-id="ad69e-126">각 쿼리를 최대 10 분까지 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad69e-126">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="ad69e-127">10 분 이내에 완료 되지 않으면 서비스에서 오류를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad69e-127">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="ad69e-128">CPU 리소스</span><span class="sxs-lookup"><span data-stu-id="ad69e-128">CPU resources</span></span> | <span data-ttu-id="ad69e-129">테 넌 트 크기 기반</span><span class="sxs-lookup"><span data-stu-id="ad69e-129">Based on tenant size</span></span> | <span data-ttu-id="ad69e-130">-1 시간 후 15 분 마다</span><span class="sxs-lookup"><span data-stu-id="ad69e-130">- On the hour and then every 15 minutes</span></span><br><span data-ttu-id="ad69e-131">-매일 자정 12 시</span><span class="sxs-lookup"><span data-stu-id="ad69e-131">- Daily at 12 midnight</span></span> | <span data-ttu-id="ad69e-132">이 서비스는 매일 및 15 분의 할당량을 개별적으로 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad69e-132">The service enforces the daily and the 15-minute quota separately.</span></span> <span data-ttu-id="ad69e-133">각 할당량에 대해 쿼리를 실행 하 고 테 넌 트가 할당 된 리소스의 10%를 초과 하는 경우 [portal에서 오류를 표시](advanced-hunting-errors.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad69e-133">For each quota, the [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="ad69e-134">다음 매일 또는 15 분 주기로 인해 테 넌 트가 다음 시간까지 100%에 도달 하면 쿼리가 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad69e-134">Queries are blocked if the tenant has reached 100% until after the next daily or 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="ad69e-135">별도의 할당량 및 매개 변수 집합은 API를 통해 수행 되는 고급 구하기 쿼리에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad69e-135">A separate set of quotas and parameters apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="ad69e-136">고급 구하기 Api에 대 한 정보</span><span class="sxs-lookup"><span data-stu-id="ad69e-136">Read about advanced hunting APIs</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

## <a name="related-topics"></a><span data-ttu-id="ad69e-137">관련 항목</span><span class="sxs-lookup"><span data-stu-id="ad69e-137">Related topics</span></span>

- [<span data-ttu-id="ad69e-138">고급 구하기 모범 사례</span><span class="sxs-lookup"><span data-stu-id="ad69e-138">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="ad69e-139">고급 구하기 오류 처리</span><span class="sxs-lookup"><span data-stu-id="ad69e-139">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="ad69e-140">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="ad69e-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ad69e-141">사용자 지정 검색 개요</span><span class="sxs-lookup"><span data-stu-id="ad69e-141">Custom detections overview</span></span>](custom-detections-overview.md)