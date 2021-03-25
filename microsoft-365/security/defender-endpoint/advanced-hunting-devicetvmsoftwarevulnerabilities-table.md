---
title: 고급 헌팅의 DeviceTvmSoftwareVulnerabilities 테이블
description: 고급 헌팅 스위마의 DeviceTvmSoftwareVulnerabilities 표에 있는 각 취약점을 해결할 수 있는 사용 가능한 보안 업데이트 목록과 장치에서 발견된 소프트웨어 취약점에 대해 자세히 알아보습니다.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, mdatp, microsoft defender atp, wdatp 검색, 쿼리, 원격 분석, schema 참조, kusto, 표, 열, 데이터 형식, 설명, 위협 & 취약성 관리, TVM, 장치 관리, 소프트웨어, 인벤토리, 취약성, CVE ID, OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.openlocfilehash: 6b38297cd0fa2e931619ff9c0557d2ae868c7aa4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076036"
---
# <a name="devicetvmsoftwarevulnerabilities"></a><span data-ttu-id="6a3cd-104">DeviceTvmSoftwareVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="6a3cd-104">DeviceTvmSoftwareVulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6a3cd-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="6a3cd-105">**Applies to:**</span></span>
- [<span data-ttu-id="6a3cd-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6a3cd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="6a3cd-107">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="6a3cd-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6a3cd-108">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="6a3cd-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="6a3cd-109">고급 헌팅 계획의 표에는 설치된 소프트웨어 제품의 취약점에 대한 위협 & 취약성 관리 `DeviceTvmSoftwareVulnerabilities` 목록이 포함되어 [](next-gen-threat-and-vuln-mgt.md) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a3cd-109">The `DeviceTvmSoftwareVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md) list of vulnerabilities in installed software products.</span></span> <span data-ttu-id="6a3cd-110">이 표에는 운영 체제 정보, CVE ID 및 취약성 심각도 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a3cd-110">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="6a3cd-111">예를 들어 이 표를 사용하여 소프트웨어에 심각한 취약점이 있는 장치를 포함하는 이벤트를 헌팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a3cd-111">You can use this table, for example, to hunt for events involving devices that have severe vulnerabilities in their software.</span></span> <span data-ttu-id="6a3cd-112">이 참조를 사용하여 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="6a3cd-112">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
><span data-ttu-id="6a3cd-113">및 `DeviceTvmSoftwareInventory` `DeviceTvmSoftwareVulnerabilities` 테이블이 테이블을 `DeviceTvmSoftwareInventoryVulnerabilities` 대체했습니다.</span><span class="sxs-lookup"><span data-stu-id="6a3cd-113">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="6a3cd-114">처음 두 표에는 취약점 관리 활동을 알리는 데 사용할 수 있는 열이 더 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a3cd-114">Together, the first two tables include more columns you can use to help inform your vulnerability management activities.</span></span>

<span data-ttu-id="6a3cd-115">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6a3cd-115">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="6a3cd-116">열 이름</span><span class="sxs-lookup"><span data-stu-id="6a3cd-116">Column name</span></span> | <span data-ttu-id="6a3cd-117">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="6a3cd-117">Data type</span></span> | <span data-ttu-id="6a3cd-118">설명</span><span class="sxs-lookup"><span data-stu-id="6a3cd-118">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="6a3cd-119">문자열</span><span class="sxs-lookup"><span data-stu-id="6a3cd-119">string</span></span> | <span data-ttu-id="6a3cd-120">서비스에서 디바이스의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="6a3cd-120">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="6a3cd-121">문자열</span><span class="sxs-lookup"><span data-stu-id="6a3cd-121">string</span></span> | <span data-ttu-id="6a3cd-122">장치의 FQDN(FQDN)</span><span class="sxs-lookup"><span data-stu-id="6a3cd-122">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="6a3cd-123">문자열</span><span class="sxs-lookup"><span data-stu-id="6a3cd-123">string</span></span> | <span data-ttu-id="6a3cd-124">디바이스에서 실행되는 운영 체제의 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="6a3cd-124">Platform of the operating system running on the device.</span></span> <span data-ttu-id="6a3cd-125">이는 Windows 10 및 Windows 7과 같이 동일한 제품군 내의 변형을 포함하여 특정 운영 체제를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6a3cd-125">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="6a3cd-126">문자열</span><span class="sxs-lookup"><span data-stu-id="6a3cd-126">string</span></span> | <span data-ttu-id="6a3cd-127">장치에서 실행되는 운영 체제 버전</span><span class="sxs-lookup"><span data-stu-id="6a3cd-127">Version of the operating system running on the device</span></span> |
| `OSArchitecture` | <span data-ttu-id="6a3cd-128">문자열</span><span class="sxs-lookup"><span data-stu-id="6a3cd-128">string</span></span> | <span data-ttu-id="6a3cd-129">장치에서 실행되는 운영 체제의 아키텍처</span><span class="sxs-lookup"><span data-stu-id="6a3cd-129">Architecture of the operating system running on the device</span></span> |
| `SoftwareVendor` | <span data-ttu-id="6a3cd-130">문자열</span><span class="sxs-lookup"><span data-stu-id="6a3cd-130">string</span></span> | <span data-ttu-id="6a3cd-131">소프트웨어 공급업체의 이름</span><span class="sxs-lookup"><span data-stu-id="6a3cd-131">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="6a3cd-132">문자열</span><span class="sxs-lookup"><span data-stu-id="6a3cd-132">string</span></span> | <span data-ttu-id="6a3cd-133">소프트웨어 제품의 이름</span><span class="sxs-lookup"><span data-stu-id="6a3cd-133">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="6a3cd-134">문자열</span><span class="sxs-lookup"><span data-stu-id="6a3cd-134">string</span></span> | <span data-ttu-id="6a3cd-135">소프트웨어 제품의 버전 번호</span><span class="sxs-lookup"><span data-stu-id="6a3cd-135">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="6a3cd-136">문자열</span><span class="sxs-lookup"><span data-stu-id="6a3cd-136">string</span></span> | <span data-ttu-id="6a3cd-137">CVE(Common Vulnerabilities and Exposures) 시스템에서 보안 취약점에 할당된 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="6a3cd-137">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="6a3cd-138">문자열</span><span class="sxs-lookup"><span data-stu-id="6a3cd-138">string</span></span> | <span data-ttu-id="6a3cd-139">CVSS 점수 및 위협 환경에 영향을 받은 동적 요인에 따라 보안 취약성에 할당된 심각도 수준</span><span class="sxs-lookup"><span data-stu-id="6a3cd-139">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `RecommendedSecurityUpdate` | <span data-ttu-id="6a3cd-140">문자열</span><span class="sxs-lookup"><span data-stu-id="6a3cd-140">string</span></span> | <span data-ttu-id="6a3cd-141">취약점을 해결하기 위해 소프트웨어 공급업체가 제공하는 보안 업데이트의 이름 또는 설명</span><span class="sxs-lookup"><span data-stu-id="6a3cd-141">Name or description of the security update provided by the software vendor to address the vulnerability</span></span> |
| `RecommendedSecurityUpdateId` | <span data-ttu-id="6a3cd-142">문자열</span><span class="sxs-lookup"><span data-stu-id="6a3cd-142">string</span></span> | <span data-ttu-id="6a3cd-143">해당 지침 또는 기술 자료(KB) 문서의 해당 보안 업데이트 또는 식별자 식별자</span><span class="sxs-lookup"><span data-stu-id="6a3cd-143">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> |



## <a name="related-topics"></a><span data-ttu-id="6a3cd-144">관련 항목</span><span class="sxs-lookup"><span data-stu-id="6a3cd-144">Related topics</span></span>

- [<span data-ttu-id="6a3cd-145">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="6a3cd-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6a3cd-146">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="6a3cd-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="6a3cd-147">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="6a3cd-147">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="6a3cd-148">위협 및 취약성 관리 개요</span><span class="sxs-lookup"><span data-stu-id="6a3cd-148">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)
