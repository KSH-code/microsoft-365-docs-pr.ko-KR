---
title: 고급 헌팅chema의 DeviceNetworkInfo 테이블
description: 고급 헌팅 schema의 DeviceNetworkInfo 표에서 네트워크 구성 정보에 대해 자세히 알아보시다.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 위협 방지, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, schema reference, kusto, table, column, data type, description, machinenetworkinfo, DeviceNetworkInfo, device, machine, mac, ip, adapter, dns, dhcp, gateway, tunnel
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 1c8a3f3ab91add9e057c4661677997e658f42386
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071548"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="65144-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="65144-104">DeviceNetworkInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="65144-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="65144-105">**Applies to:**</span></span>
- <span data-ttu-id="65144-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="65144-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="65144-107">고급 `DeviceNetworkInfo` 헌팅 schema의 표에는 네트워크 어댑터, IP 및 MAC 주소, 연결된 네트워크 또는 도메인을 비롯한 컴퓨터의 네트워킹 구성에 대한 정보가 포함되어 있습니다. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="65144-107">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of machines, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="65144-108">이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="65144-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="65144-109">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="65144-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="65144-110">열 이름</span><span class="sxs-lookup"><span data-stu-id="65144-110">Column name</span></span> | <span data-ttu-id="65144-111">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="65144-111">Data type</span></span> | <span data-ttu-id="65144-112">설명</span><span class="sxs-lookup"><span data-stu-id="65144-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="65144-113">datetime</span><span class="sxs-lookup"><span data-stu-id="65144-113">datetime</span></span> | <span data-ttu-id="65144-114">이벤트가 기록된 날짜와 시간</span><span class="sxs-lookup"><span data-stu-id="65144-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="65144-115">문자열</span><span class="sxs-lookup"><span data-stu-id="65144-115">string</span></span> | <span data-ttu-id="65144-116">서비스에서 시스템의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="65144-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="65144-117">문자열</span><span class="sxs-lookup"><span data-stu-id="65144-117">string</span></span> | <span data-ttu-id="65144-118">컴퓨터의 FQDN(정규화된 도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="65144-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ReportId` | <span data-ttu-id="65144-119">long</span><span class="sxs-lookup"><span data-stu-id="65144-119">long</span></span> | <span data-ttu-id="65144-120">반복 카운터를 기반으로 하는 이벤트 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="65144-120">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="65144-121">고유한 이벤트를 식별하려면 이 열을 DeviceName 및 Timestamp 열과 함께 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65144-121">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="65144-122">문자열</span><span class="sxs-lookup"><span data-stu-id="65144-122">string</span></span> | <span data-ttu-id="65144-123">네트워크 어댑터의 이름</span><span class="sxs-lookup"><span data-stu-id="65144-123">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="65144-124">문자열</span><span class="sxs-lookup"><span data-stu-id="65144-124">string</span></span> | <span data-ttu-id="65144-125">네트워크 어댑터의 MAC 주소</span><span class="sxs-lookup"><span data-stu-id="65144-125">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="65144-126">문자열</span><span class="sxs-lookup"><span data-stu-id="65144-126">string</span></span> | <span data-ttu-id="65144-127">네트워크 어댑터 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="65144-127">Network adapter type.</span></span> <span data-ttu-id="65144-128">가능한 값은 이 [열거를 참조하세요.](/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="65144-128">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="65144-129">문자열</span><span class="sxs-lookup"><span data-stu-id="65144-129">string</span></span> | <span data-ttu-id="65144-130">네트워크 어댑터의 작동 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="65144-130">Operational status of the network adapter.</span></span> <span data-ttu-id="65144-131">가능한 값은 이 [열거를 참조하세요.](/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="65144-131">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span></span> |
| `TunnelType` | <span data-ttu-id="65144-132">문자열</span><span class="sxs-lookup"><span data-stu-id="65144-132">string</span></span> | <span data-ttu-id="65144-133">터널링 프로토콜( 인터페이스가 이 용도로 사용되는 경우(예: 6to4, Teredo, ISATAP, PPTP, SSTP 및 SSH)</span><span class="sxs-lookup"><span data-stu-id="65144-133">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="65144-134">문자열</span><span class="sxs-lookup"><span data-stu-id="65144-134">string</span></span> | <span data-ttu-id="65144-135">어댑터가 연결된 네트워크입니다.</span><span class="sxs-lookup"><span data-stu-id="65144-135">Networks that the adapter is connected to.</span></span> <span data-ttu-id="65144-136">각 JSON 배열에는 네트워크 이름, 범주(공용, 개인 또는 도메인), 설명 및 인터넷에 공개적으로 연결되어 있는지를 나타내는 플래그가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65144-136">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="65144-137">문자열</span><span class="sxs-lookup"><span data-stu-id="65144-137">string</span></span> | <span data-ttu-id="65144-138">JSON 배열 형식의 DNS 서버 주소</span><span class="sxs-lookup"><span data-stu-id="65144-138">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="65144-139">문자열</span><span class="sxs-lookup"><span data-stu-id="65144-139">string</span></span> | <span data-ttu-id="65144-140">DHCP 서버의 IPv4 주소</span><span class="sxs-lookup"><span data-stu-id="65144-140">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="65144-141">문자열</span><span class="sxs-lookup"><span data-stu-id="65144-141">string</span></span> | <span data-ttu-id="65144-142">DHCP 서버의 IPv6 주소</span><span class="sxs-lookup"><span data-stu-id="65144-142">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="65144-143">문자열</span><span class="sxs-lookup"><span data-stu-id="65144-143">string</span></span> | <span data-ttu-id="65144-144">JSON 배열 형식의 기본 게이트웨이 주소</span><span class="sxs-lookup"><span data-stu-id="65144-144">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="65144-145">문자열</span><span class="sxs-lookup"><span data-stu-id="65144-145">string</span></span> | <span data-ttu-id="65144-146">어댑터에 할당된 모든 IP 주소와 해당 서브넷 접두사 및 IP 주소 공간(예: 공용, 개인 또는 링크 로컬)을 포함하는 JSON 배열</span><span class="sxs-lookup"><span data-stu-id="65144-146">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |

## <a name="related-topics"></a><span data-ttu-id="65144-147">관련 항목</span><span class="sxs-lookup"><span data-stu-id="65144-147">Related topics</span></span>
- [<span data-ttu-id="65144-148">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="65144-148">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="65144-149">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="65144-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="65144-150">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="65144-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="65144-151">장치, 전자 메일, 앱 및 ID를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="65144-151">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="65144-152">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="65144-152">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="65144-153">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="65144-153">Apply query best practices</span></span>](advanced-hunting-best-practices.md)