---
title: 고급 헌팅 스키마의 DeviceTvmSoftwareInventoryVulnerabilities 표
description: 고급 헌팅 스키마의 DeviceTvmSoftwareInventoryVulnerabilities 표에서 장치의 소프트웨어 인벤토리와 취약성에 대해 알아봅니다.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 위협 방지, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, software, inventory, vulnerabilities, CVE ID, OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 517f974657032a1a4b7fee5888b0c681ec8063d7
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931077"
---
# <a name="devicetvmsoftwareinventoryvulnerabilities"></a><span data-ttu-id="cf24e-104">DeviceTvmSoftwareInventoryVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="cf24e-104">DeviceTvmSoftwareInventoryVulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="cf24e-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="cf24e-105">**Applies to:**</span></span>
- <span data-ttu-id="cf24e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cf24e-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="cf24e-107">고급 헌팅 스키마의 `DeviceTvmSoftwareInventoryVulnerabilities` 표에는 이러한 소프트웨어 제품의 알려진 모든 취약점과 함께 장치의 소프트웨어 [위협 & 취약성 관리](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) 인벤토리가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf24e-107">The `DeviceTvmSoftwareInventoryVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) inventory of software on your devices as well as any known vulnerabilities in these software products.</span></span> <span data-ttu-id="cf24e-108">이 표에는 운영 체제 정보, CVE ID 및 취약성 심각도 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf24e-108">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="cf24e-109">이 참조를 사용하여 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="cf24e-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="cf24e-110">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cf24e-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="cf24e-111">열 이름</span><span class="sxs-lookup"><span data-stu-id="cf24e-111">Column name</span></span> | <span data-ttu-id="cf24e-112">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="cf24e-112">Data type</span></span> | <span data-ttu-id="cf24e-113">설명</span><span class="sxs-lookup"><span data-stu-id="cf24e-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="cf24e-114">문자열</span><span class="sxs-lookup"><span data-stu-id="cf24e-114">string</span></span> | <span data-ttu-id="cf24e-115">서비스에서 시스템의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="cf24e-115">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="cf24e-116">문자열</span><span class="sxs-lookup"><span data-stu-id="cf24e-116">string</span></span> | <span data-ttu-id="cf24e-117">컴퓨터의 FQDN(정규화된 도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="cf24e-117">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="cf24e-118">문자열</span><span class="sxs-lookup"><span data-stu-id="cf24e-118">string</span></span> | <span data-ttu-id="cf24e-119">컴퓨터에서 실행 중인 운영 체제의 플랫폼</span><span class="sxs-lookup"><span data-stu-id="cf24e-119">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="cf24e-120">이는 Windows 10 및 Windows 7과 같이 동일한 제품군 내의 변형을 포함하여 특정 운영 체제를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cf24e-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="cf24e-121">문자열</span><span class="sxs-lookup"><span data-stu-id="cf24e-121">string</span></span> | <span data-ttu-id="cf24e-122">컴퓨터에서 실행 중인 운영 체제 버전</span><span class="sxs-lookup"><span data-stu-id="cf24e-122">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="cf24e-123">문자열</span><span class="sxs-lookup"><span data-stu-id="cf24e-123">string</span></span> | <span data-ttu-id="cf24e-124">컴퓨터에서 실행 중인 운영 체제의 아키텍처</span><span class="sxs-lookup"><span data-stu-id="cf24e-124">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="cf24e-125">문자열</span><span class="sxs-lookup"><span data-stu-id="cf24e-125">string</span></span> | <span data-ttu-id="cf24e-126">소프트웨어 공급업체의 이름</span><span class="sxs-lookup"><span data-stu-id="cf24e-126">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="cf24e-127">문자열</span><span class="sxs-lookup"><span data-stu-id="cf24e-127">string</span></span> | <span data-ttu-id="cf24e-128">소프트웨어 제품의 이름</span><span class="sxs-lookup"><span data-stu-id="cf24e-128">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="cf24e-129">문자열</span><span class="sxs-lookup"><span data-stu-id="cf24e-129">string</span></span> | <span data-ttu-id="cf24e-130">소프트웨어 제품의 버전 번호</span><span class="sxs-lookup"><span data-stu-id="cf24e-130">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="cf24e-131">문자열</span><span class="sxs-lookup"><span data-stu-id="cf24e-131">string</span></span> | <span data-ttu-id="cf24e-132">CVE(Common Vulnerabilities and Exposures) 시스템에서 보안 취약점에 할당된 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="cf24e-132">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="cf24e-133">문자열</span><span class="sxs-lookup"><span data-stu-id="cf24e-133">string</span></span> | <span data-ttu-id="cf24e-134">CVSS 점수 및 위협 환경에 영향을 받은 동적 요인에 따라 보안 취약성에 할당된 심각도 수준</span><span class="sxs-lookup"><span data-stu-id="cf24e-134">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |



## <a name="related-topics"></a><span data-ttu-id="cf24e-135">관련 항목</span><span class="sxs-lookup"><span data-stu-id="cf24e-135">Related topics</span></span>

- [<span data-ttu-id="cf24e-136">사전 대응식 위협 탐지</span><span class="sxs-lookup"><span data-stu-id="cf24e-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="cf24e-137">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="cf24e-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="cf24e-138">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="cf24e-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="cf24e-139">장치, 전자 메일, 앱 및 ID를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="cf24e-139">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="cf24e-140">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="cf24e-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="cf24e-141">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="cf24e-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="cf24e-142">위협 및 취약성 관리 개요</span><span class="sxs-lookup"><span data-stu-id="cf24e-142">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
