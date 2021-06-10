---
title: Microsoft 365 Defender의 고급 헌팅 할당량 및 사용 매개 변수
description: 고급 헌팅 서비스를 응답하도록 유지하는 다양한 할당량 및 사용 매개 변수(서비스 제한) 이해
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 365 Defender, microsoft 365, m365, 검색, 쿼리, 원격 분석, schema, kusto, CPU 제한, 쿼리 제한, 리소스, 최대 결과, 할당량, 매개 변수, 할당량
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
ms.openlocfilehash: d7563a8299bbe7d543b065bb25eeb3bc90a854b9
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245603"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a><span data-ttu-id="457a5-104">고급 헌팅 할당량 및 사용 매개 변수</span><span class="sxs-lookup"><span data-stu-id="457a5-104">Advanced hunting quotas and usage parameters</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="457a5-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="457a5-105">**Applies to:**</span></span>
- <span data-ttu-id="457a5-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="457a5-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="457a5-107">서비스 성능을 유지하기 위해 고급 헌팅은 다양한 할당량 및 사용 매개 변수("서비스 제한"이라고도 알려)를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="457a5-107">To keep the service performant and responsive, advanced hunting sets various quotas and usage parameters (also known as "service limits").</span></span> <span data-ttu-id="457a5-108">이러한 할당량 및 매개 변수는 수동으로 실행된 쿼리 및 사용자 지정 검색 규칙을 사용하여 실행된 쿼리에 별도로 [적용됩니다.](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="457a5-108">These quotas and parameters apply separately to queries run manually and to queries run using [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="457a5-109">여러 쿼리를 정기적으로 실행하는 고객은 이러한 제한을 [](advanced-hunting-best-practices.md) 염두에 두고 최적화 모범 사례를 적용하여 중단을 최소화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="457a5-109">Customers who run multiple queries regularly should be mindful of these limits and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruptions.</span></span>

<span data-ttu-id="457a5-110">기존 할당량 및 사용 매개 변수를 이해하기 위해 다음 표를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="457a5-110">Refer to the following table to understand existing quotas and usage parameters.</span></span>

| <span data-ttu-id="457a5-111">할당량 또는 매개 변수</span><span class="sxs-lookup"><span data-stu-id="457a5-111">Quota or parameter</span></span> | <span data-ttu-id="457a5-112">Size</span><span class="sxs-lookup"><span data-stu-id="457a5-112">Size</span></span> | <span data-ttu-id="457a5-113">새로 고침 주기</span><span class="sxs-lookup"><span data-stu-id="457a5-113">Refresh cycle</span></span> | <span data-ttu-id="457a5-114">설명</span><span class="sxs-lookup"><span data-stu-id="457a5-114">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="457a5-115">데이터 범위</span><span class="sxs-lookup"><span data-stu-id="457a5-115">Data range</span></span> | <span data-ttu-id="457a5-116">30일</span><span class="sxs-lookup"><span data-stu-id="457a5-116">30 days</span></span> | <span data-ttu-id="457a5-117">모든 쿼리</span><span class="sxs-lookup"><span data-stu-id="457a5-117">Every query</span></span> | <span data-ttu-id="457a5-118">각 쿼리는 최대 30일 동안의 데이터를 조회할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="457a5-118">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="457a5-119">결과 집합</span><span class="sxs-lookup"><span data-stu-id="457a5-119">Result set</span></span> | <span data-ttu-id="457a5-120">행 10,000개</span><span class="sxs-lookup"><span data-stu-id="457a5-120">10,000 rows</span></span> | <span data-ttu-id="457a5-121">모든 쿼리</span><span class="sxs-lookup"><span data-stu-id="457a5-121">Every query</span></span> | <span data-ttu-id="457a5-122">각 쿼리는 최대 10,000개 레코드를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="457a5-122">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="457a5-123">시간 제한</span><span class="sxs-lookup"><span data-stu-id="457a5-123">Timeout</span></span> | <span data-ttu-id="457a5-124">10분</span><span class="sxs-lookup"><span data-stu-id="457a5-124">10 minutes</span></span> | <span data-ttu-id="457a5-125">모든 쿼리</span><span class="sxs-lookup"><span data-stu-id="457a5-125">Every query</span></span> | <span data-ttu-id="457a5-126">각 쿼리는 최대 10분 동안 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="457a5-126">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="457a5-127">10분 내에 완료되지 않은 경우 서비스에 오류가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="457a5-127">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="457a5-128">CPU 리소스</span><span class="sxs-lookup"><span data-stu-id="457a5-128">CPU resources</span></span> | <span data-ttu-id="457a5-129">테넌트 크기 기반</span><span class="sxs-lookup"><span data-stu-id="457a5-129">Based on tenant size</span></span> | <span data-ttu-id="457a5-130">15분마다</span><span class="sxs-lookup"><span data-stu-id="457a5-130">Every 15 minutes</span></span> | <span data-ttu-id="457a5-131">[쿼리가](advanced-hunting-errors.md) 실행될 때마다 테넌트가 할당된 리소스의 10% 이상을 소비할 때마다 포털에 오류가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="457a5-131">The [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="457a5-132">다음 15분 주기 후에 테넌트가 100%에 도달하면 쿼리가 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="457a5-132">Queries are blocked if the tenant has reached 100% until after the next 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="457a5-133">별도의 할당량 및 매개 변수 집합은 API를 통해 수행되는 고급 헌팅 쿼리에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="457a5-133">A separate set of quotas and parameters apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="457a5-134">고급 헌팅 API에 대한 읽기</span><span class="sxs-lookup"><span data-stu-id="457a5-134">Read about advanced hunting APIs</span></span>](./api-advanced-hunting.md)

## <a name="related-topics"></a><span data-ttu-id="457a5-135">관련 항목</span><span class="sxs-lookup"><span data-stu-id="457a5-135">Related topics</span></span>

- [<span data-ttu-id="457a5-136">고급 헌팅 모범 사례</span><span class="sxs-lookup"><span data-stu-id="457a5-136">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="457a5-137">고급 헌팅 오류 처리</span><span class="sxs-lookup"><span data-stu-id="457a5-137">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="457a5-138">지능형 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="457a5-138">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="457a5-139">사용자 지정 검색 개요</span><span class="sxs-lookup"><span data-stu-id="457a5-139">Custom detections overview</span></span>](custom-detections-overview.md)