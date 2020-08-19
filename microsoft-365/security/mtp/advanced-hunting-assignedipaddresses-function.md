---
title: Microsoft Threat Protection에 대 한 고급 구하기의 AssignedIPAddresses () 함수
description: AssignedIPAddresses () 함수를 사용 하 여 장치에 할당 된 최신 IP 주소를 가져오는 방법에 대해 알아봅니다.
keywords: 고급 구하기, 위협 검색, 사이버 위협 사냥, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 스키마 참조, kusto, FileProfile, file profile, function, 향상
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 72d02bafa168e48c2d588771f5289da09e6d6000
ms.sourcegitcommit: 234726a1795d984c4659da68f852d30a4dda5711
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/18/2020
ms.locfileid: "46794234"
---
# <a name="assignedipaddresses"></a><span data-ttu-id="d0b18-104">AssignedIPAddresses()</span><span class="sxs-lookup"><span data-stu-id="d0b18-104">AssignedIPAddresses()</span></span>

<span data-ttu-id="d0b18-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="d0b18-105">**Applies to:**</span></span>
- <span data-ttu-id="d0b18-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="d0b18-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="d0b18-107">`AssignedIPAddresses()`장치에 할당 된 최신 ip 주소 또는 지정 된 시점에서 가장 최근 ip 주소를 빠르게 가져오려면이 함수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b18-107">Use the `AssignedIPAddresses()` function to quickly obtain the latest IP addresses that have been assigned to a device or the most recent IP addresses from a specified point in time.</span></span> <span data-ttu-id="d0b18-108">이 함수는 다음과 같은 열이 있는 table을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b18-108">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="d0b18-109">열</span><span class="sxs-lookup"><span data-stu-id="d0b18-109">Column</span></span> | <span data-ttu-id="d0b18-110">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d0b18-110">Data type</span></span> | <span data-ttu-id="d0b18-111">설명</span><span class="sxs-lookup"><span data-stu-id="d0b18-111">Description</span></span> |
|------------|-------------|-------------|
| <span data-ttu-id="d0b18-112">타임 스탬프</span><span class="sxs-lookup"><span data-stu-id="d0b18-112">Timestamp</span></span> | <span data-ttu-id="d0b18-113">datetime</span><span class="sxs-lookup"><span data-stu-id="d0b18-113">datetime</span></span> | <span data-ttu-id="d0b18-114">IP 주소를 사용 하 여 장치를 확인 한 최근 시간</span><span class="sxs-lookup"><span data-stu-id="d0b18-114">Latest time when the device was observed using the IP address</span></span> |
| <span data-ttu-id="d0b18-115">IPAddress</span><span class="sxs-lookup"><span data-stu-id="d0b18-115">IPAddress</span></span> | <span data-ttu-id="d0b18-116">문자열</span><span class="sxs-lookup"><span data-stu-id="d0b18-116">string</span></span> | <span data-ttu-id="d0b18-117">장치에서 사용 하는 IP 주소</span><span class="sxs-lookup"><span data-stu-id="d0b18-117">IP address used by the device</span></span> |
| <span data-ttu-id="d0b18-118">IPType</span><span class="sxs-lookup"><span data-stu-id="d0b18-118">IPType</span></span> | <span data-ttu-id="d0b18-119">문자열</span><span class="sxs-lookup"><span data-stu-id="d0b18-119">string</span></span> | <span data-ttu-id="d0b18-120">IP 주소가 공용 또는 개인 주소 인지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d0b18-120">Indicates whether the IP address is a public or private address</span></span> |
| <span data-ttu-id="d0b18-121">NetworkAdapterType</span><span class="sxs-lookup"><span data-stu-id="d0b18-121">NetworkAdapterType</span></span> | <span data-ttu-id="d0b18-122">int</span><span class="sxs-lookup"><span data-stu-id="d0b18-122">int</span></span> | <span data-ttu-id="d0b18-123">IP 주소가 할당 된 장치에서 사용 하는 네트워크 어댑터 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="d0b18-123">Network adapter type used by the device that has been assigned the IP address.</span></span> <span data-ttu-id="d0b18-124">가능한 값은 [this 열거형](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d0b18-124">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span></span>  |
| <span data-ttu-id="d0b18-125">ConnectedNetworks</span><span class="sxs-lookup"><span data-stu-id="d0b18-125">ConnectedNetworks</span></span> | <span data-ttu-id="d0b18-126">int</span><span class="sxs-lookup"><span data-stu-id="d0b18-126">int</span></span> | <span data-ttu-id="d0b18-127">할당 된 IP 주소가 있는 어댑터가 연결 되는 네트워크입니다.</span><span class="sxs-lookup"><span data-stu-id="d0b18-127">Networks that the adapter with the assigned IP address is connected to.</span></span> <span data-ttu-id="d0b18-128">각 JSON 배열에는 네트워크 이름, 범주 (공용, 개인 또는 도메인), 설명 및 공용이 인터넷에 연결 되어 있는지 여부를 나타내는 플래그가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0b18-128">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |


## <a name="syntax"></a><span data-ttu-id="d0b18-129">구문과</span><span class="sxs-lookup"><span data-stu-id="d0b18-129">Syntax</span></span>

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a><span data-ttu-id="d0b18-130">인수나</span><span class="sxs-lookup"><span data-stu-id="d0b18-130">Arguments</span></span>

- <span data-ttu-id="d0b18-131">**x** - `DeviceId` `DeviceName` 장치를 식별 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d0b18-131">**x** — `DeviceId` or `DeviceName` value identifying the device</span></span>
- <span data-ttu-id="d0b18-132">**y** - `Timestamp` (datetime) 가장 최근 IP 주소를 가져올 특정 시점을 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d0b18-132">**y** — `Timestamp` (datetime) value indicating the specific point in time where to get the most recent IP addresses.</span></span> <span data-ttu-id="d0b18-133">이를 지정 하지 않으면이 함수는 최신 IP 주소를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b18-133">If not specified, the function returns the latest IP addresses.</span></span>

## <a name="examples"></a><span data-ttu-id="d0b18-134">예</span><span class="sxs-lookup"><span data-stu-id="d0b18-134">Examples</span></span>

### <a name="get-the-list-of-ip-addresses-used-by-a-device-as-of-24-hours-ago"></a><span data-ttu-id="d0b18-135">24 시간 전 장치에서 사용 하는 IP 주소 목록 가져오기</span><span class="sxs-lookup"><span data-stu-id="d0b18-135">Get the list of IP addresses used by a device as of 24 hours ago</span></span>

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a><span data-ttu-id="d0b18-136">장치에서 사용 하는 IP 주소 가져오기 및 it와 통신 하는 장치 찾기</span><span class="sxs-lookup"><span data-stu-id="d0b18-136">Get IP addresses used by a device and find devices communicating with it</span></span>
<span data-ttu-id="d0b18-137">이 쿼리는 함수를 사용 하 여 `AssignedIPAddresses()` `example-device-name` 특정 날짜 또는 그 이전에 장치에 할당 된 IP 주소를 가져옵니다 `example-date` .</span><span class="sxs-lookup"><span data-stu-id="d0b18-137">This query uses the `AssignedIPAddresses()` function to get assigned IP addresses for the device (`example-device-name`) on or before a specific date (`example-date`).</span></span> <span data-ttu-id="d0b18-138">그런 다음 IP 주소를 사용 하 여 다른 장치가 시작한 장치에 대 한 연결을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d0b18-138">It then uses the IP addresses to find connections to the device initiated by other devices.</span></span> 

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

## <a name="related-topics"></a><span data-ttu-id="d0b18-139">관련 항목</span><span class="sxs-lookup"><span data-stu-id="d0b18-139">Related topics</span></span>
- [<span data-ttu-id="d0b18-140">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="d0b18-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d0b18-141">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="d0b18-141">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d0b18-142">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="d0b18-142">Understand the schema</span></span>](advanced-hunting-schema-tables.md)