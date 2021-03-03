---
title: 고급 헌팅 schema의 DeviceTvmSoftwareInventory 테이블
description: 고급 헌팅 스파이마의 DeviceTvmSoftwareInventory 표에서 장치의 소프트웨어 인벤토리에 대해 자세히 알아보습니다.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 위협 방지, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, software, inventory, vulnerabilities, CVE ID, OS DeviceTvmSoftwareInventoryVulnerabilities
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: maccruz
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 5edb6205e0392441163060aa7181ca031e1fbb0d
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/03/2021
ms.locfileid: "50416841"
---
# <a name="devicetvmsoftwareinventory"></a><span data-ttu-id="e18df-104">DeviceTvmSoftwareInventory</span><span class="sxs-lookup"><span data-stu-id="e18df-104">DeviceTvmSoftwareInventory</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e18df-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="e18df-105">**Applies to:**</span></span>
- <span data-ttu-id="e18df-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e18df-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="e18df-107">일부 정보는 상업적으로 출시되기 전에 상당수 수정될 수 있는 미리 시판된 제품과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e18df-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="e18df-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="e18df-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


<span data-ttu-id="e18df-109">고급 헌팅 & 표에는 지원 종료 정보를 포함하여 현재 네트워크의 장치에 설치된 소프트웨어의 위협 & 취약성 관리 인벤토리가 `DeviceTvmSoftwareInventory` 포함되어 있습니다. [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)</span><span class="sxs-lookup"><span data-stu-id="e18df-109">The `DeviceTvmSoftwareInventory` table in the advanced hunting schema contains the [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) inventory of software currently installed on devices in your network, including end of support information.</span></span> <span data-ttu-id="e18df-110">예를 들어 현재 취약한 소프트웨어 버전으로 설치된 장치와 관련된 이벤트를 헌팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e18df-110">You can, for instance, hunt for events involving devices that are installed with a currently vulnerable software version.</span></span> <span data-ttu-id="e18df-111">이 참조를 사용하여 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e18df-111">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
> <span data-ttu-id="e18df-112">및 `DeviceTvmSoftwareInventory` `DeviceTvmSoftwareVulnerabilities` 테이블이 테이블을 `DeviceTvmSoftwareInventoryVulnerabilities` 대체했습니다.</span><span class="sxs-lookup"><span data-stu-id="e18df-112">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="e18df-113">처음 두 표에는 다양한 관리 활동을 알리거나 취약한 장치를 헌팅하는 데 도움이 되는 더 많은 열이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e18df-113">Together, the first two tables include more columns you can use to help inform your vulnerablity management activities or hunt for vulnerable devices.</span></span>

<span data-ttu-id="e18df-114">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e18df-114">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="e18df-115">열 이름</span><span class="sxs-lookup"><span data-stu-id="e18df-115">Column name</span></span> | <span data-ttu-id="e18df-116">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="e18df-116">Data type</span></span> | <span data-ttu-id="e18df-117">설명</span><span class="sxs-lookup"><span data-stu-id="e18df-117">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="e18df-118">문자열</span><span class="sxs-lookup"><span data-stu-id="e18df-118">string</span></span> | <span data-ttu-id="e18df-119">서비스에서 시스템의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="e18df-119">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="e18df-120">문자열</span><span class="sxs-lookup"><span data-stu-id="e18df-120">string</span></span> | <span data-ttu-id="e18df-121">컴퓨터의 FQDN(정규화된 도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="e18df-121">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="e18df-122">문자열</span><span class="sxs-lookup"><span data-stu-id="e18df-122">string</span></span> | <span data-ttu-id="e18df-123">컴퓨터에서 실행 중인 운영 체제의 플랫폼</span><span class="sxs-lookup"><span data-stu-id="e18df-123">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="e18df-124">이는 Windows 10 및 Windows 7과 같이 동일한 제품군 내의 변형을 포함하여 특정 운영 체제를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e18df-124">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="e18df-125">문자열</span><span class="sxs-lookup"><span data-stu-id="e18df-125">string</span></span> | <span data-ttu-id="e18df-126">컴퓨터에서 실행 중인 운영 체제 버전</span><span class="sxs-lookup"><span data-stu-id="e18df-126">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="e18df-127">문자열</span><span class="sxs-lookup"><span data-stu-id="e18df-127">string</span></span> | <span data-ttu-id="e18df-128">컴퓨터에서 실행 중인 운영 체제의 아키텍처</span><span class="sxs-lookup"><span data-stu-id="e18df-128">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="e18df-129">문자열</span><span class="sxs-lookup"><span data-stu-id="e18df-129">string</span></span> | <span data-ttu-id="e18df-130">소프트웨어 공급업체의 이름</span><span class="sxs-lookup"><span data-stu-id="e18df-130">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="e18df-131">문자열</span><span class="sxs-lookup"><span data-stu-id="e18df-131">string</span></span> | <span data-ttu-id="e18df-132">소프트웨어 제품의 이름</span><span class="sxs-lookup"><span data-stu-id="e18df-132">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="e18df-133">문자열</span><span class="sxs-lookup"><span data-stu-id="e18df-133">string</span></span> | <span data-ttu-id="e18df-134">소프트웨어 제품의 버전 번호</span><span class="sxs-lookup"><span data-stu-id="e18df-134">Version number of the software product</span></span> |
| `EndOfSupportStatus` | <span data-ttu-id="e18df-135">문자열</span><span class="sxs-lookup"><span data-stu-id="e18df-135">string</span></span> | <span data-ttu-id="e18df-136">지정된 EOS(지원 종료) 또는 EOL(종료 날짜)을 상대로 소프트웨어 제품의 수명 주기 스테이지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e18df-136">Indicates the lifecycle stage of the software product relative to its specified end-of-support (EOS) or end-of-life (EOL) date</span></span> |
| `EndOfSupportDate` | <span data-ttu-id="e18df-137">문자열</span><span class="sxs-lookup"><span data-stu-id="e18df-137">string</span></span> | <span data-ttu-id="e18df-138">소프트웨어 제품의 EOS(지원 종료) 또는 EOL(종료 날짜)</span><span class="sxs-lookup"><span data-stu-id="e18df-138">End-of-support (EOS) or end-of-life (EOL) date of the software product</span></span> |



## <a name="related-topics"></a><span data-ttu-id="e18df-139">관련 항목</span><span class="sxs-lookup"><span data-stu-id="e18df-139">Related topics</span></span>

- [<span data-ttu-id="e18df-140">사전 대응식 위협 탐지</span><span class="sxs-lookup"><span data-stu-id="e18df-140">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e18df-141">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="e18df-141">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e18df-142">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="e18df-142">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="e18df-143">장치, 전자 메일, 앱 및 ID를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="e18df-143">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="e18df-144">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="e18df-144">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="e18df-145">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="e18df-145">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="e18df-146">위협 및 취약성 관리 개요</span><span class="sxs-lookup"><span data-stu-id="e18df-146">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
