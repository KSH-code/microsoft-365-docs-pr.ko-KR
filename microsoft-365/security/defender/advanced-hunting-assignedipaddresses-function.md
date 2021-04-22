---
title: Microsoft 365 Defender에 대한 고급 헌팅의 AssignedIPAddresses() 기능
description: AssignedIPAddresses() 함수를 사용하여 장치에 할당된 최신 IP 주소를 다운로드하는 방법을 학습합니다.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 365 Defender, microsoft 365, m365, 검색, 쿼리, 원격 분석, 스마 참조, kusto, FileProfile, 파일 프로필, 기능, 향상
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
ms.openlocfilehash: d3ebd301d6c79bf5286d9293e04e4073b99d1e35
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934912"
---
# <a name="assignedipaddresses"></a><span data-ttu-id="abb04-104">AssignedIPAddresses()</span><span class="sxs-lookup"><span data-stu-id="abb04-104">AssignedIPAddresses()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="abb04-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="abb04-105">**Applies to:**</span></span>
- <span data-ttu-id="abb04-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="abb04-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="abb04-107">고급 헌팅 쿼리의 기능을 사용하여 장치에 할당된 최신 IP 주소를 빠르게 `AssignedIPAddresses()` 얻습니다. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="abb04-107">Use the `AssignedIPAddresses()` function in your [advanced hunting](advanced-hunting-overview.md) queries to quickly obtain the latest IP addresses that have been assigned to a device.</span></span> <span data-ttu-id="abb04-108">타임스탬프 인수를 지정하면 이 함수는 지정된 시간의 가장 최근 IP 주소를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="abb04-108">If you specify a timestamp argument, this function obtains the most recent IP addresses at the specified time.</span></span> 

<span data-ttu-id="abb04-109">이 함수는 다음 열이 있는 표를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="abb04-109">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="abb04-110">열</span><span class="sxs-lookup"><span data-stu-id="abb04-110">Column</span></span> | <span data-ttu-id="abb04-111">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="abb04-111">Data type</span></span> | <span data-ttu-id="abb04-112">설명</span><span class="sxs-lookup"><span data-stu-id="abb04-112">Description</span></span> |
|------------|-------------|-------------|
| `Timestamp` | <span data-ttu-id="abb04-113">datetime</span><span class="sxs-lookup"><span data-stu-id="abb04-113">datetime</span></span> | <span data-ttu-id="abb04-114">IP 주소를 사용하여 장치가 관찰된 최신 시간</span><span class="sxs-lookup"><span data-stu-id="abb04-114">Latest time when the device was observed using the IP address</span></span> |
| `IPAddress` | <span data-ttu-id="abb04-115">문자열</span><span class="sxs-lookup"><span data-stu-id="abb04-115">string</span></span> | <span data-ttu-id="abb04-116">장치에서 사용하는 IP 주소</span><span class="sxs-lookup"><span data-stu-id="abb04-116">IP address used by the device</span></span> |
| `IPType` | <span data-ttu-id="abb04-117">문자열</span><span class="sxs-lookup"><span data-stu-id="abb04-117">string</span></span> | <span data-ttu-id="abb04-118">IP 주소가 공용 주소인지 개인 주소인지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="abb04-118">Indicates whether the IP address is a public or private address</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="abb04-119">int</span><span class="sxs-lookup"><span data-stu-id="abb04-119">int</span></span> | <span data-ttu-id="abb04-120">IP 주소가 할당된 장치에서 사용하는 네트워크 어댑터 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="abb04-120">Network adapter type used by the device that has been assigned the IP address.</span></span> <span data-ttu-id="abb04-121">가능한 값은 이 [열거를 참조하세요.](/dotnet/api/system.net.networkinformation.networkinterfacetype)</span><span class="sxs-lookup"><span data-stu-id="abb04-121">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.networkinterfacetype)</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="abb04-122">int</span><span class="sxs-lookup"><span data-stu-id="abb04-122">int</span></span> | <span data-ttu-id="abb04-123">할당된 IP 주소가 있는 어댑터가 연결된 네트워크입니다.</span><span class="sxs-lookup"><span data-stu-id="abb04-123">Networks that the adapter with the assigned IP address is connected to.</span></span> <span data-ttu-id="abb04-124">각 JSON 배열에는 네트워크 이름, 범주(공용, 개인 또는 도메인), 설명 및 인터넷에 공개적으로 연결되어 있는지를 나타내는 플래그가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abb04-124">Each JSON array contains the network name, category (public, private, or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |

## <a name="syntax"></a><span data-ttu-id="abb04-125">구문</span><span class="sxs-lookup"><span data-stu-id="abb04-125">Syntax</span></span>

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a><span data-ttu-id="abb04-126">인수</span><span class="sxs-lookup"><span data-stu-id="abb04-126">Arguments</span></span>

- <span data-ttu-id="abb04-127">**x**- `DeviceId` `DeviceName` 또는 디바이스를 식별하는 값</span><span class="sxs-lookup"><span data-stu-id="abb04-127">**x**—`DeviceId` or `DeviceName` value identifying the device</span></span>
- <span data-ttu-id="abb04-128">**y**- (datetime) 특정 시간에서 가장 최근에 할당된 IP 주소를 구하도록 `Timestamp` 함수에 지시하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="abb04-128">**y**—`Timestamp` (datetime) value instructing the function to obtain the most recent assigned IP addresses from a specific time.</span></span> <span data-ttu-id="abb04-129">지정하지 않으면 함수는 최신 IP 주소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="abb04-129">If not specified, the function returns the latest IP addresses.</span></span>

## <a name="examples"></a><span data-ttu-id="abb04-130">예제</span><span class="sxs-lookup"><span data-stu-id="abb04-130">Examples</span></span>

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a><span data-ttu-id="abb04-131">24시간 전 디바이스에서 사용하는 IP 주소 목록 표시</span><span class="sxs-lookup"><span data-stu-id="abb04-131">Get the list of IP addresses used by a device 24 hours ago</span></span>

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a><span data-ttu-id="abb04-132">장치에서 사용하는 IP 주소를 찾고 장치와 통신하는 장치 찾기</span><span class="sxs-lookup"><span data-stu-id="abb04-132">Get IP addresses used by a device and find devices communicating with it</span></span>
<span data-ttu-id="abb04-133">이 쿼리는 함수를 사용하여 특정 날짜()에 또는 그 이전의 디바이스에 할당된 `AssignedIPAddresses()` IP 주소()를 `example-device-name` `example-date` 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="abb04-133">This query uses the `AssignedIPAddresses()` function to get assigned IP addresses for the device (`example-device-name`) on or before a specific date (`example-date`).</span></span> <span data-ttu-id="abb04-134">그런 다음 IP 주소를 사용하여 다른 장치에서 시작한 디바이스에 대한 연결을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="abb04-134">It then uses the IP addresses to find connections to the device initiated by other devices.</span></span> 

```kusto
let Date = datetime(example-date);
let DeviceName = "example-device-name";
// List IP addresses used on or before the specified date
AssignedIPAddresses(DeviceName, Date)
| project DeviceName, IPAddress, AssignedTime = Timestamp 
// Get all network events on devices with the assigned IP addresses as the destination addresses
| join kind=inner DeviceNetworkEvents on $left.IPAddress == $right.RemoteIP
// Get only network events around the time the IP address was assigned
| where Timestamp between ((AssignedTime - 1h) .. (AssignedTime + 1h))
```

## <a name="related-topics"></a><span data-ttu-id="abb04-135">관련 항목</span><span class="sxs-lookup"><span data-stu-id="abb04-135">Related topics</span></span>
- [<span data-ttu-id="abb04-136">지능형 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="abb04-136">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="abb04-137">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="abb04-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="abb04-138">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="abb04-138">Understand the schema</span></span>](advanced-hunting-schema-tables.md)