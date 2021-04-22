---
title: Microsoft 365 Defender에 대한 고급 헌팅의 DeviceFromIP() 기능
description: DeviceFromIP() 함수를 사용하여 특정 IP 주소가 할당된 디바이스를 사용하는 방법을 학습
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 365 Defender, microsoft 365, m365, 검색, 쿼리, 원격 분석, schema reference, kusto, device, devicefromIP, function, enrichment
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
ms.openlocfilehash: 3ea951e35555721a989001b2a5235df5b89a8a55
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933184"
---
# <a name="devicefromip"></a><span data-ttu-id="1a7fd-104">DeviceFromIP()</span><span class="sxs-lookup"><span data-stu-id="1a7fd-104">DeviceFromIP()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1a7fd-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="1a7fd-105">**Applies to:**</span></span>
- <span data-ttu-id="1a7fd-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1a7fd-106">Microsoft 365 Defender</span></span>


[!INCLUDE [Prerelease information](../includes/prerelease.md)]


<span data-ttu-id="1a7fd-107">고급 헌팅 쿼리의 기능을 사용하여 지정된 시점에 특정 IP 주소에 할당된 장치 목록을 빠르게 얻을 `DeviceFromIP()` 수 있습니다. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="1a7fd-107">Use the `DeviceFromIP()` function in your [advanced hunting](advanced-hunting-overview.md) queries to quickly obtain the list of devices that have been assigned to a certain IP address at a given point in time.</span></span> 

<span data-ttu-id="1a7fd-108">이 함수는 다음 열이 있는 표를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1a7fd-108">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="1a7fd-109">열</span><span class="sxs-lookup"><span data-stu-id="1a7fd-109">Column</span></span> | <span data-ttu-id="1a7fd-110">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="1a7fd-110">Data type</span></span> | <span data-ttu-id="1a7fd-111">설명</span><span class="sxs-lookup"><span data-stu-id="1a7fd-111">Description</span></span> |
|------------|-------------|-------------|
| `IP` | <span data-ttu-id="1a7fd-112">문자열</span><span class="sxs-lookup"><span data-stu-id="1a7fd-112">string</span></span> | <span data-ttu-id="1a7fd-113">IP 주소</span><span class="sxs-lookup"><span data-stu-id="1a7fd-113">IP address</span></span>  |
| `DeviceId` | <span data-ttu-id="1a7fd-114">문자열</span><span class="sxs-lookup"><span data-stu-id="1a7fd-114">string</span></span> | <span data-ttu-id="1a7fd-115">서비스에서 디바이스의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="1a7fd-115">Unique identifier for the device in the service</span></span> |


## <a name="syntax"></a><span data-ttu-id="1a7fd-116">구문</span><span class="sxs-lookup"><span data-stu-id="1a7fd-116">Syntax</span></span>

```kusto
invoke DeviceFromIP()
```

## <a name="arguments"></a><span data-ttu-id="1a7fd-117">인수</span><span class="sxs-lookup"><span data-stu-id="1a7fd-117">Arguments</span></span>

<span data-ttu-id="1a7fd-118">이 함수는 쿼리의 일부로 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a7fd-118">This function is invoked as part of a query.</span></span>

- <span data-ttu-id="1a7fd-119">**x**-첫 번째 매개 변수는 일반적으로 이미 쿼리의 열입니다.</span><span class="sxs-lookup"><span data-stu-id="1a7fd-119">**x**—The first parameter is typically already a column in the query.</span></span> <span data-ttu-id="1a7fd-120">이 경우 이 열은 이라는 열로, 할당된 장치 목록을 보게 할 `IP` IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="1a7fd-120">In this case, it is the column named `IP`, the IP address for which you want to see a list of devices that have been assigned to it.</span></span> <span data-ttu-id="1a7fd-121">로컬 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="1a7fd-121">It should be a local IP address.</span></span> <span data-ttu-id="1a7fd-122">외부 IP 주소는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1a7fd-122">External IP addresses are not supported.</span></span>
- <span data-ttu-id="1a7fd-123">**y**-두 번째 선택적 매개 변수는 이며, 이 매개 변수는 특정 시간에서 가장 최근에 할당된 장치를 구하도록 `Timestamp` 함수에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="1a7fd-123">**y**—A second optional parameter is the `Timestamp`, which instructs the function to obtain the most recent assigned devices from a specific time.</span></span> <span data-ttu-id="1a7fd-124">이 함수를 지정하지 않으면 사용 가능한 최신 레코드가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a7fd-124">If not specified, the function returns the latest available records.</span></span>

## <a name="example"></a><span data-ttu-id="1a7fd-125">예시</span><span class="sxs-lookup"><span data-stu-id="1a7fd-125">Example</span></span>


### <a name="get-the-latest-devices-that-have-been-assigned-specific-ip-addresses"></a><span data-ttu-id="1a7fd-126">특정 IP 주소가 할당된 최신 장치 다운로드</span><span class="sxs-lookup"><span data-stu-id="1a7fd-126">Get the latest devices that have been assigned specific IP addresses</span></span>

```kusto
DeviceNetworkEvents 
| limit 100 
| project IP = LocalIP 
| invoke DeviceFromIP()
```

## <a name="related-topics"></a><span data-ttu-id="1a7fd-127">관련 항목</span><span class="sxs-lookup"><span data-stu-id="1a7fd-127">Related topics</span></span>
- [<span data-ttu-id="1a7fd-128">지능형 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="1a7fd-128">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="1a7fd-129">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="1a7fd-129">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="1a7fd-130">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="1a7fd-130">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
