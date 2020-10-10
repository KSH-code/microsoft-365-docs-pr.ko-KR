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
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 7f0b479051c46fe35ec9aea84b23ca0c4937fbfe
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412325"
---
# <a name="assignedipaddresses"></a><span data-ttu-id="f0690-104">AssignedIPAddresses()</span><span class="sxs-lookup"><span data-stu-id="f0690-104">AssignedIPAddresses()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f0690-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="f0690-105">**Applies to:**</span></span>
- <span data-ttu-id="f0690-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="f0690-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="f0690-107">`AssignedIPAddresses()` [고급 구하기](advanced-hunting-overview.md) 쿼리의 함수를 사용 하 여 장치에 할당 된 최신 IP 주소를 빠르게 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="f0690-107">Use the `AssignedIPAddresses()` function in your [advanced hunting](advanced-hunting-overview.md) queries to quickly obtain the latest IP addresses that have been assigned to a device.</span></span> <span data-ttu-id="f0690-108">Timestamp 인수를 지정 하면이 함수는 지정 된 시간에 가장 최근 IP 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f0690-108">If you specify a timestamp argument, this function obtains the most recent IP addresses at the specified time.</span></span> 

<span data-ttu-id="f0690-109">이 함수는 다음과 같은 열이 있는 table을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0690-109">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="f0690-110">열</span><span class="sxs-lookup"><span data-stu-id="f0690-110">Column</span></span> | <span data-ttu-id="f0690-111">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="f0690-111">Data type</span></span> | <span data-ttu-id="f0690-112">설명</span><span class="sxs-lookup"><span data-stu-id="f0690-112">Description</span></span> |
|------------|-------------|-------------|
| `Timestamp` | <span data-ttu-id="f0690-113">datetime</span><span class="sxs-lookup"><span data-stu-id="f0690-113">datetime</span></span> | <span data-ttu-id="f0690-114">IP 주소를 사용 하 여 장치를 확인 한 최근 시간</span><span class="sxs-lookup"><span data-stu-id="f0690-114">Latest time when the device was observed using the IP address</span></span> |
| `IPAddress` | <span data-ttu-id="f0690-115">문자열</span><span class="sxs-lookup"><span data-stu-id="f0690-115">string</span></span> | <span data-ttu-id="f0690-116">장치에서 사용 하는 IP 주소</span><span class="sxs-lookup"><span data-stu-id="f0690-116">IP address used by the device</span></span> |
| `IPType` | <span data-ttu-id="f0690-117">문자열</span><span class="sxs-lookup"><span data-stu-id="f0690-117">string</span></span> | <span data-ttu-id="f0690-118">IP 주소가 공용 또는 개인 주소 인지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f0690-118">Indicates whether the IP address is a public or private address</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="f0690-119">int</span><span class="sxs-lookup"><span data-stu-id="f0690-119">int</span></span> | <span data-ttu-id="f0690-120">IP 주소가 할당 된 장치에서 사용 하는 네트워크 어댑터 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="f0690-120">Network adapter type used by the device that has been assigned the IP address.</span></span> <span data-ttu-id="f0690-121">가능한 값은 [this 열거형](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f0690-121">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype)</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="f0690-122">int</span><span class="sxs-lookup"><span data-stu-id="f0690-122">int</span></span> | <span data-ttu-id="f0690-123">할당 된 IP 주소가 있는 어댑터가 연결 되는 네트워크입니다.</span><span class="sxs-lookup"><span data-stu-id="f0690-123">Networks that the adapter with the assigned IP address is connected to.</span></span> <span data-ttu-id="f0690-124">각 JSON 배열에는 네트워크 이름, 범주 (공용, 개인 또는 도메인), 설명 및 공용이 인터넷에 연결 되어 있는지 여부를 나타내는 플래그가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0690-124">Each JSON array contains the network name, category (public, private, or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |

## <a name="syntax"></a><span data-ttu-id="f0690-125">구문과</span><span class="sxs-lookup"><span data-stu-id="f0690-125">Syntax</span></span>

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a><span data-ttu-id="f0690-126">인수나</span><span class="sxs-lookup"><span data-stu-id="f0690-126">Arguments</span></span>

- <span data-ttu-id="f0690-127">**x**- `DeviceId` `DeviceName` 장치를 식별 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f0690-127">**x**—`DeviceId` or `DeviceName` value identifying the device</span></span>
- <span data-ttu-id="f0690-128">**y**- `Timestamp` (datetime)-함수가 특정 시간에서 가장 최근 할당 된 IP 주소를 가져오도록 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0690-128">**y**—`Timestamp` (datetime) value instructing the function to obtain the most recent assigned IP addresses from a specific time.</span></span> <span data-ttu-id="f0690-129">이를 지정 하지 않으면이 함수는 최신 IP 주소를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0690-129">If not specified, the function returns the latest IP addresses.</span></span>

## <a name="examples"></a><span data-ttu-id="f0690-130">예</span><span class="sxs-lookup"><span data-stu-id="f0690-130">Examples</span></span>

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a><span data-ttu-id="f0690-131">장치에서 사용 하는 IP 주소 목록을 24 시간 전에 가져오기</span><span class="sxs-lookup"><span data-stu-id="f0690-131">Get the list of IP addresses used by a device 24 hours ago</span></span>

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a><span data-ttu-id="f0690-132">장치에서 사용 하는 IP 주소 가져오기 및 it와 통신 하는 장치 찾기</span><span class="sxs-lookup"><span data-stu-id="f0690-132">Get IP addresses used by a device and find devices communicating with it</span></span>
<span data-ttu-id="f0690-133">이 쿼리는 함수를 사용 하 여 `AssignedIPAddresses()` `example-device-name` 특정 날짜 또는 그 이전에 장치에 할당 된 IP 주소를 가져옵니다 `example-date` .</span><span class="sxs-lookup"><span data-stu-id="f0690-133">This query uses the `AssignedIPAddresses()` function to get assigned IP addresses for the device (`example-device-name`) on or before a specific date (`example-date`).</span></span> <span data-ttu-id="f0690-134">그런 다음 IP 주소를 사용 하 여 다른 장치가 시작한 장치에 대 한 연결을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="f0690-134">It then uses the IP addresses to find connections to the device initiated by other devices.</span></span> 

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

## <a name="related-topics"></a><span data-ttu-id="f0690-135">관련 항목</span><span class="sxs-lookup"><span data-stu-id="f0690-135">Related topics</span></span>
- [<span data-ttu-id="f0690-136">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="f0690-136">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f0690-137">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="f0690-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f0690-138">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="f0690-138">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
