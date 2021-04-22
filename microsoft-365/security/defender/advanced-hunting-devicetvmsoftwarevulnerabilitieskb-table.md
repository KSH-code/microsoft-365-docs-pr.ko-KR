---
title: 고급 헌팅 스키마의 DeviceTvmSoftwareVulnerabilitiesKB 표
description: 고급 헌팅 스키마의 DeviceTvmSoftwareVulnerabilitiesKB 표에서 위협 및 취약성 관리를 통해 추적하는 소프트웨어 취약성에 대해 알아봅니다.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 365 Defender, microsoft 365, m365, 검색, 쿼리, 원격 분석, schema, 참조, kusto, 표, 열, 데이터 형식, 설명, 위협 & 취약성 관리, TVM, 장치 관리, 소프트웨어, 인벤토리, 취약성, CVE ID, CVSS, DeviceTvmSoftwareVulnerabilitiesKB
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
ms.openlocfilehash: 0c9a29a75b2dc6ea2ae88f84e21ee2ab6455b2b0
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933016"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a><span data-ttu-id="d0560-104">DeviceTvmSoftwareVulnerabilitiesKB</span><span class="sxs-lookup"><span data-stu-id="d0560-104">DeviceTvmSoftwareVulnerabilitiesKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d0560-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="d0560-105">**Applies to:**</span></span>
- <span data-ttu-id="d0560-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d0560-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="d0560-107">고급 헌팅 스키마의 `DeviceTvmSoftwareVulnerabilitiesKB` 표에는 [위협 및 취약성 관리](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)에서 장치를 평가하는 취약성 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0560-107">The `DeviceTvmSoftwareVulnerabilitiesKB` table in the advanced hunting schema contains the list of vulnerabilities [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) assesses devices for.</span></span> <span data-ttu-id="d0560-108">이 참조를 사용하여 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d0560-108">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="d0560-109">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d0560-109">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="d0560-110">열 이름</span><span class="sxs-lookup"><span data-stu-id="d0560-110">Column name</span></span> | <span data-ttu-id="d0560-111">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d0560-111">Data type</span></span> | <span data-ttu-id="d0560-112">설명</span><span class="sxs-lookup"><span data-stu-id="d0560-112">Description</span></span> |
|-------------|-----------|-------------|
| `CveId` | <span data-ttu-id="d0560-113">문자열</span><span class="sxs-lookup"><span data-stu-id="d0560-113">string</span></span> | <span data-ttu-id="d0560-114">CVE(Common Vulnerabilities and Exposures) 시스템에서 보안 취약점에 할당된 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="d0560-114">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `CvssScore` | <span data-ttu-id="d0560-115">문자열</span><span class="sxs-lookup"><span data-stu-id="d0560-115">string</span></span> | <span data-ttu-id="d0560-116">CVSS(Common Vulnerability Scoring System)에서 보안 취약점에 할당된 심각도 점수</span><span class="sxs-lookup"><span data-stu-id="d0560-116">Severity score assigned to the security vulnerability under th Common Vulnerability Scoring System (CVSS)</span></span> |
| `IsExploitAvailable` | <span data-ttu-id="d0560-117">부울</span><span class="sxs-lookup"><span data-stu-id="d0560-117">boolean</span></span> | <span data-ttu-id="d0560-118">취약점에 대한 악용 코드를 공개적으로 사용할 수 있는지 여부</span><span class="sxs-lookup"><span data-stu-id="d0560-118">Indicates whether exploit code for the vulnerability is publicly available</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="d0560-119">문자열</span><span class="sxs-lookup"><span data-stu-id="d0560-119">string</span></span> | <span data-ttu-id="d0560-120">CVSS 점수 및 위협의 영향을 받은 동적 요인에 따라 보안 취약성에 할당된 심각도 수준</span><span class="sxs-lookup"><span data-stu-id="d0560-120">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `LastModifiedTime` | <span data-ttu-id="d0560-121">날짜/시간</span><span class="sxs-lookup"><span data-stu-id="d0560-121">datetime</span></span> | <span data-ttu-id="d0560-122">항목 또는 관련된 메타 데이터가 마지막으로 수정된 날짜와 시간</span><span class="sxs-lookup"><span data-stu-id="d0560-122">Date and time the item or related metadata was last modified</span></span> |
| `PublishedDate` | <span data-ttu-id="d0560-123">날짜/시간</span><span class="sxs-lookup"><span data-stu-id="d0560-123">datetime</span></span> | <span data-ttu-id="d0560-124">취약점이 공개된 날짜</span><span class="sxs-lookup"><span data-stu-id="d0560-124">Date vulnerability was disclosed to public</span></span> |
| `VulnerabilityDescription` | <span data-ttu-id="d0560-125">문자열</span><span class="sxs-lookup"><span data-stu-id="d0560-125">string</span></span> | <span data-ttu-id="d0560-126">취약점과 관련된 위험에 대한 설명</span><span class="sxs-lookup"><span data-stu-id="d0560-126">Description of vulnerability and associated risks</span></span> |
| `AffectedSoftware` | <span data-ttu-id="d0560-127">문자열</span><span class="sxs-lookup"><span data-stu-id="d0560-127">string</span></span> | <span data-ttu-id="d0560-128">취약점에 영향을 받는 모든 소프트웨어 제품 목록</span><span class="sxs-lookup"><span data-stu-id="d0560-128">List of all software products affected by the vulnerability</span></span> |

## <a name="related-topics"></a><span data-ttu-id="d0560-129">관련 항목</span><span class="sxs-lookup"><span data-stu-id="d0560-129">Related topics</span></span>

- [<span data-ttu-id="d0560-130">사전 대응식 위협 탐지</span><span class="sxs-lookup"><span data-stu-id="d0560-130">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d0560-131">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="d0560-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d0560-132">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="d0560-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="d0560-133">장치, 전자 메일, 앱 및 ID를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="d0560-133">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="d0560-134">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="d0560-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="d0560-135">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="d0560-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="d0560-136">위협 및 취약성 관리 개요</span><span class="sxs-lookup"><span data-stu-id="d0560-136">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)