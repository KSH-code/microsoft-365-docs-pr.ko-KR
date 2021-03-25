---
title: 고급 헌팅의 DeviceTvmSoftwareVulnerabilities 테이블
description: 고급 헌팅 스위마의 DeviceTvmSoftwareVulnerabilities 표에 있는 각 취약점을 해결할 수 있는 사용 가능한 보안 업데이트 목록 및 장치에서 발견된 소프트웨어 취약점에 대해 자세히 알아보습니다.
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
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 6911031e3caa27eff80bb83a3a88643cac2b6918
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073964"
---
# <a name="devicetvmsoftwarevulnerabilities"></a><span data-ttu-id="c31cc-104">DeviceTvmSoftwareVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="c31cc-104">DeviceTvmSoftwareVulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c31cc-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="c31cc-105">**Applies to:**</span></span>
- <span data-ttu-id="c31cc-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c31cc-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="c31cc-107">일부 정보는 상용으로 출시되기 전에 실질적으로 수정될 수 있는 사전 릴리스된 제품과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c31cc-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="c31cc-108">Microsoft는 여기에서 제공하는 정보와 관련하여 명시적이거나 묵시적인 어떠한 보증도 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c31cc-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="c31cc-109">고급 헌팅 계획의 표에는 설치된 소프트웨어 제품의 취약점에 대한 위협 & 취약성 관리 `DeviceTvmSoftwareVulnerabilities` 목록이 포함되어 [](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c31cc-109">The `DeviceTvmSoftwareVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) list of vulnerabilities in installed software products.</span></span> <span data-ttu-id="c31cc-110">이 표에는 운영 체제 정보, CVE ID 및 취약성 심각도 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c31cc-110">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="c31cc-111">예를 들어 이 표를 사용하여 소프트웨어에 심각한 취약점이 있는 장치를 포함하는 이벤트를 헌팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c31cc-111">You can use this table, for example, to hunt for events involving devices that have severe vulnerabilities in their software.</span></span> <span data-ttu-id="c31cc-112">이 참조를 사용하여 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c31cc-112">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
> <span data-ttu-id="c31cc-113">및 `DeviceTvmSoftwareInventory` `DeviceTvmSoftwareVulnerabilities` 테이블이 테이블을 `DeviceTvmSoftwareInventoryVulnerabilities` 대체했습니다.</span><span class="sxs-lookup"><span data-stu-id="c31cc-113">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="c31cc-114">처음 두 표에는 다양한 관리 활동을 알리거나 취약한 장치를 헌팅하는 데 도움이 되는 더 많은 열이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c31cc-114">Together, the first two tables include more columns you can use to help inform your vulnerablity management activities or hunt for vulnerable devices.</span></span>

<span data-ttu-id="c31cc-115">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c31cc-115">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="c31cc-116">열 이름</span><span class="sxs-lookup"><span data-stu-id="c31cc-116">Column name</span></span> | <span data-ttu-id="c31cc-117">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c31cc-117">Data type</span></span> | <span data-ttu-id="c31cc-118">설명</span><span class="sxs-lookup"><span data-stu-id="c31cc-118">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="c31cc-119">문자열</span><span class="sxs-lookup"><span data-stu-id="c31cc-119">string</span></span> | <span data-ttu-id="c31cc-120">서비스에서 시스템의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="c31cc-120">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="c31cc-121">문자열</span><span class="sxs-lookup"><span data-stu-id="c31cc-121">string</span></span> | <span data-ttu-id="c31cc-122">컴퓨터의 FQDN(정규화된 도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="c31cc-122">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="c31cc-123">문자열</span><span class="sxs-lookup"><span data-stu-id="c31cc-123">string</span></span> | <span data-ttu-id="c31cc-124">컴퓨터에서 실행 중인 운영 체제의 플랫폼</span><span class="sxs-lookup"><span data-stu-id="c31cc-124">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="c31cc-125">이는 Windows 10 및 Windows 7과 같이 동일한 제품군 내의 변형을 포함하여 특정 운영 체제를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c31cc-125">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="c31cc-126">문자열</span><span class="sxs-lookup"><span data-stu-id="c31cc-126">string</span></span> | <span data-ttu-id="c31cc-127">컴퓨터에서 실행 중인 운영 체제 버전</span><span class="sxs-lookup"><span data-stu-id="c31cc-127">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="c31cc-128">문자열</span><span class="sxs-lookup"><span data-stu-id="c31cc-128">string</span></span> | <span data-ttu-id="c31cc-129">컴퓨터에서 실행 중인 운영 체제의 아키텍처</span><span class="sxs-lookup"><span data-stu-id="c31cc-129">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="c31cc-130">문자열</span><span class="sxs-lookup"><span data-stu-id="c31cc-130">string</span></span> | <span data-ttu-id="c31cc-131">소프트웨어 공급업체의 이름</span><span class="sxs-lookup"><span data-stu-id="c31cc-131">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="c31cc-132">문자열</span><span class="sxs-lookup"><span data-stu-id="c31cc-132">string</span></span> | <span data-ttu-id="c31cc-133">소프트웨어 제품의 이름</span><span class="sxs-lookup"><span data-stu-id="c31cc-133">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="c31cc-134">문자열</span><span class="sxs-lookup"><span data-stu-id="c31cc-134">string</span></span> | <span data-ttu-id="c31cc-135">소프트웨어 제품의 버전 번호</span><span class="sxs-lookup"><span data-stu-id="c31cc-135">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="c31cc-136">문자열</span><span class="sxs-lookup"><span data-stu-id="c31cc-136">string</span></span> | <span data-ttu-id="c31cc-137">CVE(Common Vulnerabilities and Exposures) 시스템에서 보안 취약점에 할당된 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="c31cc-137">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="c31cc-138">문자열</span><span class="sxs-lookup"><span data-stu-id="c31cc-138">string</span></span> | <span data-ttu-id="c31cc-139">CVSS 점수 및 위협 환경에 영향을 받은 동적 요인에 따라 보안 취약성에 할당된 심각도 수준</span><span class="sxs-lookup"><span data-stu-id="c31cc-139">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `RecommendedSecurityUpdate` | <span data-ttu-id="c31cc-140">문자열</span><span class="sxs-lookup"><span data-stu-id="c31cc-140">string</span></span> | <span data-ttu-id="c31cc-141">취약점을 해결하기 위해 소프트웨어 공급업체가 제공하는 보안 업데이트의 이름 또는 설명</span><span class="sxs-lookup"><span data-stu-id="c31cc-141">Name or description of the security update provided by the software vendor to address the vulnerability</span></span> |
| `RecommendedSecurityUpdateId` | <span data-ttu-id="c31cc-142">문자열</span><span class="sxs-lookup"><span data-stu-id="c31cc-142">string</span></span> | <span data-ttu-id="c31cc-143">해당 지침 또는 기술 자료(KB) 문서의 해당 보안 업데이트 또는 식별자 식별자</span><span class="sxs-lookup"><span data-stu-id="c31cc-143">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> |



## <a name="related-topics"></a><span data-ttu-id="c31cc-144">관련 항목</span><span class="sxs-lookup"><span data-stu-id="c31cc-144">Related topics</span></span>

- [<span data-ttu-id="c31cc-145">사전 대응식 위협 탐지</span><span class="sxs-lookup"><span data-stu-id="c31cc-145">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c31cc-146">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="c31cc-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c31cc-147">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="c31cc-147">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="c31cc-148">장치, 전자 메일, 앱 및 ID를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="c31cc-148">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="c31cc-149">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="c31cc-149">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="c31cc-150">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="c31cc-150">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="c31cc-151">위협 및 취약성 관리 개요</span><span class="sxs-lookup"><span data-stu-id="c31cc-151">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)