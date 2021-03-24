---
title: 고급 헌팅 스키마의 DeviceTvmSoftwareVulnerabilitiesKB 표
description: 고급 헌팅 스키마의 DeviceTvmSoftwareVulnerabilitiesKB 표에서 위협 및 취약성 관리를 통해 추적하는 소프트웨어 취약성에 대해 알아봅니다.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, mdatp, microsoft defender atp, wdatp 검색, 쿼리, 원격 분석, schema 참조, kusto, 표, 열, 데이터 형식, 설명, 위협 & 취약성 관리, TVM, 장치 관리, 소프트웨어, 인벤토리, 취약성, CVE ID, CVSS, DeviceTvmSoftwareVulnerabilitiesKB
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: mde
ms.openlocfilehash: 772a287097f0b204eb329d066cdd81c4eef7a755
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070924"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a><span data-ttu-id="34c50-104">DeviceTvmSoftwareVulnerabilitiesKB</span><span class="sxs-lookup"><span data-stu-id="34c50-104">DeviceTvmSoftwareVulnerabilitiesKB</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="34c50-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="34c50-105">**Applies to:**</span></span>
- [<span data-ttu-id="34c50-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="34c50-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="34c50-107">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="34c50-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="34c50-108">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="34c50-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="34c50-109">고급 헌팅 스키마의 `DeviceTvmSoftwareVulnerabilitiesKB` 표에는 [위협 및 취약성 관리](next-gen-threat-and-vuln-mgt.md)에서 장치를 평가하는 취약성 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34c50-109">The `DeviceTvmSoftwareVulnerabilitiesKB` table in the advanced hunting schema contains the list of vulnerabilities [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md) assesses devices for.</span></span> <span data-ttu-id="34c50-110">이 참조를 사용하여 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="34c50-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="34c50-111">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-reference.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="34c50-111">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="34c50-112">열 이름</span><span class="sxs-lookup"><span data-stu-id="34c50-112">Column name</span></span> | <span data-ttu-id="34c50-113">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="34c50-113">Data type</span></span> | <span data-ttu-id="34c50-114">설명</span><span class="sxs-lookup"><span data-stu-id="34c50-114">Description</span></span> |
|-------------|-----------|-------------|
| `CveId` | <span data-ttu-id="34c50-115">문자열</span><span class="sxs-lookup"><span data-stu-id="34c50-115">string</span></span> | <span data-ttu-id="34c50-116">CVE(Common Vulnerabilities and Exposures) 시스템에서 보안 취약점에 할당된 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="34c50-116">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `CvssScore` | <span data-ttu-id="34c50-117">문자열</span><span class="sxs-lookup"><span data-stu-id="34c50-117">string</span></span> | <span data-ttu-id="34c50-118">CVSS(Common Vulnerability Scoring System)에서 보안 취약점에 할당된 심각도 점수</span><span class="sxs-lookup"><span data-stu-id="34c50-118">Severity score assigned to the security vulnerability under th Common Vulnerability Scoring System (CVSS)</span></span> |
| `IsExploitAvailable` | <span data-ttu-id="34c50-119">부울</span><span class="sxs-lookup"><span data-stu-id="34c50-119">boolean</span></span> | <span data-ttu-id="34c50-120">취약점에 대한 악용 코드를 공개적으로 사용할 수 있는지 여부</span><span class="sxs-lookup"><span data-stu-id="34c50-120">Indicates whether exploit code for the vulnerability is publicly available</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="34c50-121">문자열</span><span class="sxs-lookup"><span data-stu-id="34c50-121">string</span></span> | <span data-ttu-id="34c50-122">CVSS 점수 및 위협의 영향을 받은 동적 요인에 따라 보안 취약성에 할당된 심각도 수준</span><span class="sxs-lookup"><span data-stu-id="34c50-122">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `LastModifiedTime` | <span data-ttu-id="34c50-123">날짜/시간</span><span class="sxs-lookup"><span data-stu-id="34c50-123">datetime</span></span> | <span data-ttu-id="34c50-124">항목 또는 관련된 메타 데이터가 마지막으로 수정된 날짜와 시간</span><span class="sxs-lookup"><span data-stu-id="34c50-124">Date and time the item or related metadata was last modified</span></span> |
| `PublishedDate` | <span data-ttu-id="34c50-125">날짜/시간</span><span class="sxs-lookup"><span data-stu-id="34c50-125">datetime</span></span> | <span data-ttu-id="34c50-126">취약점이 공개된 날짜</span><span class="sxs-lookup"><span data-stu-id="34c50-126">Date vulnerability was disclosed to public</span></span> |
| `VulnerabilityDescription` | <span data-ttu-id="34c50-127">문자열</span><span class="sxs-lookup"><span data-stu-id="34c50-127">string</span></span> | <span data-ttu-id="34c50-128">취약점과 관련된 위험에 대한 설명</span><span class="sxs-lookup"><span data-stu-id="34c50-128">Description of vulnerability and associated risks</span></span> |
| `AffectedSoftware` | <span data-ttu-id="34c50-129">문자열</span><span class="sxs-lookup"><span data-stu-id="34c50-129">string</span></span> | <span data-ttu-id="34c50-130">취약점에 영향을 받는 모든 소프트웨어 제품 목록</span><span class="sxs-lookup"><span data-stu-id="34c50-130">List of all software products affected by the vulnerability</span></span> |

## <a name="related-topics"></a><span data-ttu-id="34c50-131">관련 항목</span><span class="sxs-lookup"><span data-stu-id="34c50-131">Related topics</span></span>

- [<span data-ttu-id="34c50-132">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="34c50-132">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="34c50-133">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="34c50-133">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="34c50-134">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="34c50-134">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="34c50-135">위협 및 취약성 관리 개요</span><span class="sxs-lookup"><span data-stu-id="34c50-135">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)
