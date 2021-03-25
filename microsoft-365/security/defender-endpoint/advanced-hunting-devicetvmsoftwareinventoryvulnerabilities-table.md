---
title: 고급 헌팅 스키마의 DeviceTvmSoftwareInventoryVulnerabilities 표
description: 고급 헌팅 스키마의 DeviceTvmSoftwareInventoryVulnerabilities 표에서 장치의 소프트웨어 인벤토리와 취약성에 대해 알아봅니다.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, mdatp, microsoft defender atp, wdatp 검색, 쿼리, 원격 분석, schema 참조, kusto, 표, 열, 데이터 형식, 설명, 위협 & 취약성 관리, TVM, 장치 관리, 소프트웨어, 인벤토리, 취약성, CVE ID, OS DeviceTvmSoftwareInventoryVulnerabilities
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: bbb535aa3f106c8569edb3c64ba95bba9bf36186
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163462"
---
# <a name="devicetvmsoftwareinventoryvulnerabilities"></a><span data-ttu-id="85d81-104">DeviceTvmSoftwareInventoryVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="85d81-104">DeviceTvmSoftwareInventoryVulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="85d81-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="85d81-105">**Applies to:**</span></span>

- [<span data-ttu-id="85d81-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="85d81-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="85d81-107">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="85d81-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="85d81-108">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="85d81-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="85d81-109">고급 헌팅 스키마의 `DeviceTvmSoftwareInventoryVulnerabilities` 표에는 이러한 소프트웨어 제품의 알려진 모든 취약점과 함께 장치의 소프트웨어 [위협 & 취약성 관리](next-gen-threat-and-vuln-mgt.md) 인벤토리가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85d81-109">The `DeviceTvmSoftwareInventoryVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md) inventory of software on your devices as well as any known vulnerabilities in these software products.</span></span> <span data-ttu-id="85d81-110">이 표에는 운영 체제 정보, CVE ID 및 취약성 심각도 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85d81-110">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="85d81-111">이 참조를 사용하여 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="85d81-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="85d81-112">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="85d81-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="85d81-113">열 이름</span><span class="sxs-lookup"><span data-stu-id="85d81-113">Column name</span></span> | <span data-ttu-id="85d81-114">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="85d81-114">Data type</span></span> | <span data-ttu-id="85d81-115">설명</span><span class="sxs-lookup"><span data-stu-id="85d81-115">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="85d81-116">문자열</span><span class="sxs-lookup"><span data-stu-id="85d81-116">string</span></span> | <span data-ttu-id="85d81-117">서비스에서 디바이스의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="85d81-117">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="85d81-118">문자열</span><span class="sxs-lookup"><span data-stu-id="85d81-118">string</span></span> | <span data-ttu-id="85d81-119">장치의 FQDN(FQDN)</span><span class="sxs-lookup"><span data-stu-id="85d81-119">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="85d81-120">문자열</span><span class="sxs-lookup"><span data-stu-id="85d81-120">string</span></span> | <span data-ttu-id="85d81-121">디바이스에서 실행되는 운영 체제의 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="85d81-121">Platform of the operating system running on the device.</span></span> <span data-ttu-id="85d81-122">이는 Windows 10 및 Windows 7과 같이 동일한 제품군 내의 변형을 포함하여 특정 운영 체제를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="85d81-122">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="85d81-123">문자열</span><span class="sxs-lookup"><span data-stu-id="85d81-123">string</span></span> | <span data-ttu-id="85d81-124">장치에서 실행되는 운영 체제 버전</span><span class="sxs-lookup"><span data-stu-id="85d81-124">Version of the operating system running on the device</span></span> |
| `OSArchitecture` | <span data-ttu-id="85d81-125">문자열</span><span class="sxs-lookup"><span data-stu-id="85d81-125">string</span></span> | <span data-ttu-id="85d81-126">장치에서 실행되는 운영 체제의 아키텍처</span><span class="sxs-lookup"><span data-stu-id="85d81-126">Architecture of the operating system running on the device</span></span> |
| `SoftwareVendor` | <span data-ttu-id="85d81-127">문자열</span><span class="sxs-lookup"><span data-stu-id="85d81-127">string</span></span> | <span data-ttu-id="85d81-128">소프트웨어 공급업체의 이름</span><span class="sxs-lookup"><span data-stu-id="85d81-128">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="85d81-129">문자열</span><span class="sxs-lookup"><span data-stu-id="85d81-129">string</span></span> | <span data-ttu-id="85d81-130">소프트웨어 제품의 이름</span><span class="sxs-lookup"><span data-stu-id="85d81-130">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="85d81-131">문자열</span><span class="sxs-lookup"><span data-stu-id="85d81-131">string</span></span> | <span data-ttu-id="85d81-132">소프트웨어 제품의 버전 번호</span><span class="sxs-lookup"><span data-stu-id="85d81-132">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="85d81-133">문자열</span><span class="sxs-lookup"><span data-stu-id="85d81-133">string</span></span> | <span data-ttu-id="85d81-134">CVE(Common Vulnerabilities and Exposures) 시스템에서 보안 취약점에 할당된 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="85d81-134">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="85d81-135">문자열</span><span class="sxs-lookup"><span data-stu-id="85d81-135">string</span></span> | <span data-ttu-id="85d81-136">CVSS 점수 및 위협 환경에 영향을 받은 동적 요인에 따라 보안 취약성에 할당된 심각도 수준</span><span class="sxs-lookup"><span data-stu-id="85d81-136">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |



## <a name="related-topics"></a><span data-ttu-id="85d81-137">관련 항목</span><span class="sxs-lookup"><span data-stu-id="85d81-137">Related topics</span></span>

- [<span data-ttu-id="85d81-138">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="85d81-138">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="85d81-139">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="85d81-139">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="85d81-140">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="85d81-140">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="85d81-141">위협 및 취약성 관리 개요</span><span class="sxs-lookup"><span data-stu-id="85d81-141">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)
