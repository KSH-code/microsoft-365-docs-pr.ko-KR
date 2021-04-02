---
title: 고급 헌팅chema의 DeviceNetworkInfo 테이블
description: 고급 헌팅 schema의 DeviceNetworkInfo 표에서 네트워크 구성 정보에 대해 자세히 알아보시다.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, 검색, 쿼리, 원격 분석, schema 참조, kusto, 표, 열, 데이터 형식, 설명, devicenetworkinfo, 장치, 장치, mac, ip, 어댑터, dns, dhcp, 게이트웨이, 터널, DeviceNetworkInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e63af4153804a09424c36fb03ac715da5f6d9485
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499134"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="c47c0-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="c47c0-104">DeviceNetworkInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c47c0-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="c47c0-105">**Applies to:**</span></span>
- [<span data-ttu-id="c47c0-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="c47c0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="c47c0-107">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="c47c0-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c47c0-108">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="c47c0-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="c47c0-109">고급 `DeviceNetworkInfo` 헌팅 schema의 표에는 네트워크 어댑터, IP 및 MAC 주소, 연결된 네트워크 또는 도메인을 비롯한 장치의 네트워킹 구성에 대한 정보가 포함되어 있습니다. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="c47c0-109">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of devices, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="c47c0-110">이 참조를 사용하여 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c47c0-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="c47c0-111">고급 헌팅 스마의 다른 표에 대한 자세한 내용은 고급 헌팅 스마 [참조 를 참조하세요.](advanced-hunting-schema-reference.md)</span><span class="sxs-lookup"><span data-stu-id="c47c0-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="c47c0-112">열 이름</span><span class="sxs-lookup"><span data-stu-id="c47c0-112">Column name</span></span> | <span data-ttu-id="c47c0-113">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c47c0-113">Data type</span></span> | <span data-ttu-id="c47c0-114">설명</span><span class="sxs-lookup"><span data-stu-id="c47c0-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="c47c0-115">datetime</span><span class="sxs-lookup"><span data-stu-id="c47c0-115">datetime</span></span> | <span data-ttu-id="c47c0-116">이벤트가 기록된 날짜와 시간</span><span class="sxs-lookup"><span data-stu-id="c47c0-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="c47c0-117">문자열</span><span class="sxs-lookup"><span data-stu-id="c47c0-117">string</span></span> | <span data-ttu-id="c47c0-118">서비스에서 디바이스의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="c47c0-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="c47c0-119">문자열</span><span class="sxs-lookup"><span data-stu-id="c47c0-119">string</span></span> | <span data-ttu-id="c47c0-120">장치의 FQDN(FQDN)</span><span class="sxs-lookup"><span data-stu-id="c47c0-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `ReportId` | <span data-ttu-id="c47c0-121">long</span><span class="sxs-lookup"><span data-stu-id="c47c0-121">long</span></span> | <span data-ttu-id="c47c0-122">반복 카운터를 기반으로 하는 이벤트 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="c47c0-122">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="c47c0-123">고유한 이벤트를 식별하려면 이 열을 및 열과 `DeviceName` 함께 `Timestamp` 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c47c0-123">To identify unique events, this column must be used in conjunction with the `DeviceName` and `Timestamp` columns</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="c47c0-124">문자열</span><span class="sxs-lookup"><span data-stu-id="c47c0-124">string</span></span> | <span data-ttu-id="c47c0-125">네트워크 어댑터의 이름</span><span class="sxs-lookup"><span data-stu-id="c47c0-125">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="c47c0-126">문자열</span><span class="sxs-lookup"><span data-stu-id="c47c0-126">string</span></span> | <span data-ttu-id="c47c0-127">네트워크 어댑터의 MAC 주소</span><span class="sxs-lookup"><span data-stu-id="c47c0-127">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="c47c0-128">문자열</span><span class="sxs-lookup"><span data-stu-id="c47c0-128">string</span></span> | <span data-ttu-id="c47c0-129">네트워크 어댑터 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="c47c0-129">Network adapter type.</span></span> <span data-ttu-id="c47c0-130">가능한 값은 이 [열거를 참조하세요.](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2&preserve-view=true)</span><span class="sxs-lookup"><span data-stu-id="c47c0-130">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2&preserve-view=true)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="c47c0-131">문자열</span><span class="sxs-lookup"><span data-stu-id="c47c0-131">string</span></span> | <span data-ttu-id="c47c0-132">네트워크 어댑터의 작동 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="c47c0-132">Operational status of the network adapter.</span></span> <span data-ttu-id="c47c0-133">가능한 값은 이 [열거를 참조하세요.](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2&preserve-view=true)</span><span class="sxs-lookup"><span data-stu-id="c47c0-133">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2&preserve-view=true)</span></span> |
| `TunnelType` | <span data-ttu-id="c47c0-134">문자열</span><span class="sxs-lookup"><span data-stu-id="c47c0-134">string</span></span> | <span data-ttu-id="c47c0-135">터널링 프로토콜( 인터페이스가 이 용도로 사용되는 경우(예: 6to4, Teredo, ISATAP, PPTP, SSTP 및 SSH)</span><span class="sxs-lookup"><span data-stu-id="c47c0-135">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="c47c0-136">문자열</span><span class="sxs-lookup"><span data-stu-id="c47c0-136">string</span></span> | <span data-ttu-id="c47c0-137">어댑터가 연결된 네트워크입니다.</span><span class="sxs-lookup"><span data-stu-id="c47c0-137">Networks that the adapter is connected to.</span></span> <span data-ttu-id="c47c0-138">각 JSON 배열에는 네트워크 이름, 범주(공용, 개인 또는 도메인), 설명 및 인터넷에 공개적으로 연결되어 있는지를 나타내는 플래그가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c47c0-138">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="c47c0-139">문자열</span><span class="sxs-lookup"><span data-stu-id="c47c0-139">string</span></span> | <span data-ttu-id="c47c0-140">JSON 배열 형식의 DNS 서버 주소</span><span class="sxs-lookup"><span data-stu-id="c47c0-140">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="c47c0-141">문자열</span><span class="sxs-lookup"><span data-stu-id="c47c0-141">string</span></span> | <span data-ttu-id="c47c0-142">DHCP 서버의 IPv4 주소</span><span class="sxs-lookup"><span data-stu-id="c47c0-142">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="c47c0-143">문자열</span><span class="sxs-lookup"><span data-stu-id="c47c0-143">string</span></span> | <span data-ttu-id="c47c0-144">DHCP 서버의 IPv6 주소</span><span class="sxs-lookup"><span data-stu-id="c47c0-144">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="c47c0-145">문자열</span><span class="sxs-lookup"><span data-stu-id="c47c0-145">string</span></span> | <span data-ttu-id="c47c0-146">JSON 배열 형식의 기본 게이트웨이 주소</span><span class="sxs-lookup"><span data-stu-id="c47c0-146">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="c47c0-147">문자열</span><span class="sxs-lookup"><span data-stu-id="c47c0-147">string</span></span> | <span data-ttu-id="c47c0-148">어댑터에 할당된 모든 IP 주소와 해당 서브넷 접두사 및 IP 주소 공간(예: 공용, 개인 또는 링크 로컬)을 포함하는 JSON 배열</span><span class="sxs-lookup"><span data-stu-id="c47c0-148">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |

## <a name="related-topics"></a><span data-ttu-id="c47c0-149">관련 항목</span><span class="sxs-lookup"><span data-stu-id="c47c0-149">Related topics</span></span>
- [<span data-ttu-id="c47c0-150">지능형 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="c47c0-150">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c47c0-151">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="c47c0-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c47c0-152">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="c47c0-152">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
