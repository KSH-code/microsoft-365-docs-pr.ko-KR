---
title: 고급 헌팅 스키마의 DeviceTvmSoftwareVulnerabilitiesKB 표
description: 고급 헌팅 스키마의 DeviceTvmSoftwareVulnerabilitiesKB 표에서 위협 및 취약성 관리를 통해 추적하는 소프트웨어 취약성에 대해 알아봅니다.
keywords: 고급 구하기, 위협 검색, 사이버 위협 검색, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 스키마, 참조, kusto, table, column, data type, description, threat & 취약성 관리, TVM, 장치 관리, 소프트웨어, 인벤토리, 취약성, CVE ID, CVSS, DeviceTvmSoftwareVulnerabilitiesKB
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
ms.openlocfilehash: d4969cdfa2851acc6f94e5e1a903a9b59f73489e
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/12/2020
ms.locfileid: "46648924"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a><span data-ttu-id="d403c-104">DeviceTvmSoftwareVulnerabilitiesKB</span><span class="sxs-lookup"><span data-stu-id="d403c-104">DeviceTvmSoftwareVulnerabilitiesKB</span></span>

<span data-ttu-id="d403c-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="d403c-105">**Applies to:**</span></span>
- <span data-ttu-id="d403c-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="d403c-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="d403c-107">고급 헌팅 스키마의 `DeviceTvmSoftwareVulnerabilitiesKB` 표에는 [위협 및 취약성 관리](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)에서 장치를 평가하는 취약성 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d403c-107">The `DeviceTvmSoftwareVulnerabilitiesKB` table in the advanced hunting schema contains the list of vulnerabilities [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) assesses devices for.</span></span> <span data-ttu-id="d403c-108">이 참조를 사용하여 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d403c-108">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="d403c-109">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d403c-109">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="d403c-110">열 이름</span><span class="sxs-lookup"><span data-stu-id="d403c-110">Column name</span></span> | <span data-ttu-id="d403c-111">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d403c-111">Data type</span></span> | <span data-ttu-id="d403c-112">설명</span><span class="sxs-lookup"><span data-stu-id="d403c-112">Description</span></span> |
|-------------|-----------|-------------|
| `CveId` | <span data-ttu-id="d403c-113">문자열</span><span class="sxs-lookup"><span data-stu-id="d403c-113">string</span></span> | <span data-ttu-id="d403c-114">CVE(Common Vulnerabilities and Exposures) 시스템에서 보안 취약점에 할당된 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="d403c-114">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `CvssScore` | <span data-ttu-id="d403c-115">문자열</span><span class="sxs-lookup"><span data-stu-id="d403c-115">string</span></span> | <span data-ttu-id="d403c-116">CVSS(Common Vulnerability Scoring System)에서 보안 취약점에 할당된 심각도 점수</span><span class="sxs-lookup"><span data-stu-id="d403c-116">Severity score assigned to the security vulnerability under th Common Vulnerability Scoring System (CVSS)</span></span> |
| `IsExploitAvailable` | <span data-ttu-id="d403c-117">부울</span><span class="sxs-lookup"><span data-stu-id="d403c-117">boolean</span></span> | <span data-ttu-id="d403c-118">취약점에 대한 악용 코드를 공개적으로 사용할 수 있는지 여부</span><span class="sxs-lookup"><span data-stu-id="d403c-118">Indicates whether exploit code for the vulnerability is publicly available</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="d403c-119">문자열</span><span class="sxs-lookup"><span data-stu-id="d403c-119">string</span></span> | <span data-ttu-id="d403c-120">CVSS 점수 및 위협의 영향을 받은 동적 요인에 따라 보안 취약성에 할당된 심각도 수준</span><span class="sxs-lookup"><span data-stu-id="d403c-120">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `LastModifiedTime` | <span data-ttu-id="d403c-121">날짜/시간</span><span class="sxs-lookup"><span data-stu-id="d403c-121">datetime</span></span> | <span data-ttu-id="d403c-122">항목 또는 관련된 메타 데이터가 마지막으로 수정된 날짜와 시간</span><span class="sxs-lookup"><span data-stu-id="d403c-122">Date and time the item or related metadata was last modified</span></span> |
| `PublishedDate` | <span data-ttu-id="d403c-123">날짜/시간</span><span class="sxs-lookup"><span data-stu-id="d403c-123">datetime</span></span> | <span data-ttu-id="d403c-124">취약점이 공개된 날짜</span><span class="sxs-lookup"><span data-stu-id="d403c-124">Date vulnerability was disclosed to public</span></span> |
| `VulnerabilityDescription` | <span data-ttu-id="d403c-125">문자열</span><span class="sxs-lookup"><span data-stu-id="d403c-125">string</span></span> | <span data-ttu-id="d403c-126">취약점과 관련된 위험에 대한 설명</span><span class="sxs-lookup"><span data-stu-id="d403c-126">Description of vulnerability and associated risks</span></span> |
| `AffectedSoftware` | <span data-ttu-id="d403c-127">문자열</span><span class="sxs-lookup"><span data-stu-id="d403c-127">string</span></span> | <span data-ttu-id="d403c-128">취약점에 영향을 받는 모든 소프트웨어 제품 목록</span><span class="sxs-lookup"><span data-stu-id="d403c-128">List of all software products affected by the vulnerability</span></span> |

## <a name="related-topics"></a><span data-ttu-id="d403c-129">관련 항목</span><span class="sxs-lookup"><span data-stu-id="d403c-129">Related topics</span></span>

- [<span data-ttu-id="d403c-130">사전 대응식 위협 탐지</span><span class="sxs-lookup"><span data-stu-id="d403c-130">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d403c-131">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="d403c-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d403c-132">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="d403c-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="d403c-133">장치, 전자 메일, 앱 및 id 간 헌트</span><span class="sxs-lookup"><span data-stu-id="d403c-133">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="d403c-134">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="d403c-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="d403c-135">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="d403c-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="d403c-136">위협 및 취약성 관리 개요</span><span class="sxs-lookup"><span data-stu-id="d403c-136">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
