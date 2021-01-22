---
title: 고급 헌팅 스키마의 DeviceTvmSecureConfigurationAssessmentKB 표
description: 고급 헌팅 스키마의 DeviceTvmSecureConfigurationAssessmentKB 표에서 위협 및 취약성 관리로 평가되는 다양한 보안 구성에 대해 알아보세요.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 위협 방지, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, schema 참조, kusto, 표, 열, 데이터 형식, 설명, 위협 & 취약성 관리, TVM, 장치 관리, 보안 구성, MITRE ATT&CK 프레임워크, 기술 자료, KB, DeviceTvmSecureConfigurationAssessmentKB
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
ms.openlocfilehash: 4cd23b8f3ba99b38264b9bf1ba18e8ec2574bab6
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931065"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="a79a1-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="a79a1-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a79a1-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="a79a1-105">**Applies to:**</span></span>
- <span data-ttu-id="a79a1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a79a1-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="a79a1-107">고급 헌팅 스키마의 `DeviceTvmSecureConfigurationAssessmentKB` 표에는 [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)에서 확인되는 장치가 자동 업데이트를 보유하고 있는지에 대한 정보 등의 다양한 보안 구성 관련 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a79a1-107">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="a79a1-108">또한 위험 정보, 관련 산업 벤치마크 및 해당 MITRE ATT&CK 기법 및 전술을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="a79a1-108">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="a79a1-109">이 참조를 사용하여 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a79a1-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="a79a1-110">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a79a1-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="a79a1-111">열 이름</span><span class="sxs-lookup"><span data-stu-id="a79a1-111">Column name</span></span> | <span data-ttu-id="a79a1-112">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="a79a1-112">Data type</span></span> | <span data-ttu-id="a79a1-113">설명</span><span class="sxs-lookup"><span data-stu-id="a79a1-113">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="a79a1-114">문자열</span><span class="sxs-lookup"><span data-stu-id="a79a1-114">string</span></span> | <span data-ttu-id="a79a1-115">특정 구성의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="a79a1-115">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="a79a1-116">문자열</span><span class="sxs-lookup"><span data-stu-id="a79a1-116">string</span></span> | <span data-ttu-id="a79a1-117">구성의 등급이 전반적인 구성 점수에 미치는 영향(1-10)</span><span class="sxs-lookup"><span data-stu-id="a79a1-117">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="a79a1-118">문자열</span><span class="sxs-lookup"><span data-stu-id="a79a1-118">string</span></span> | <span data-ttu-id="a79a1-119">구성 이름을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="a79a1-119">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="a79a1-120">문자열</span><span class="sxs-lookup"><span data-stu-id="a79a1-120">string</span></span> | <span data-ttu-id="a79a1-121">구성에 대한 설명</span><span class="sxs-lookup"><span data-stu-id="a79a1-121">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="a79a1-122">문자열</span><span class="sxs-lookup"><span data-stu-id="a79a1-122">string</span></span> | <span data-ttu-id="a79a1-123">관련 위험에 대한 설명</span><span class="sxs-lookup"><span data-stu-id="a79a1-123">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="a79a1-124">문자열</span><span class="sxs-lookup"><span data-stu-id="a79a1-124">string</span></span> | <span data-ttu-id="a79a1-125">구성이 속해 있는 범주 또는 그룹(응용 프로그램, OS, 네트워크, 계정, 보안 제어)</span><span class="sxs-lookup"><span data-stu-id="a79a1-125">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="a79a1-126">문자열</span><span class="sxs-lookup"><span data-stu-id="a79a1-126">string</span></span> |<span data-ttu-id="a79a1-127">구성이 속한 하위 범주나 하위 그룹</span><span class="sxs-lookup"><span data-stu-id="a79a1-127">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="a79a1-128">대부분의 경우 이는 특정 기능이나 특징을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a79a1-128">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="a79a1-129">문자열</span><span class="sxs-lookup"><span data-stu-id="a79a1-129">string</span></span> | <span data-ttu-id="a79a1-130">동일하거나 유사한 구성을 제안하는 산업 벤치마크 목록</span><span class="sxs-lookup"><span data-stu-id="a79a1-130">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `RelatedMitreTechniques` | <span data-ttu-id="a79a1-131">문자열</span><span class="sxs-lookup"><span data-stu-id="a79a1-131">string</span></span> | <span data-ttu-id="a79a1-132">구성과 관련된 Mitre ATT&CK 프레임워크 기법 목록</span><span class="sxs-lookup"><span data-stu-id="a79a1-132">List of Mitre ATT&CK framework techniques related to the configuration</span></span> |
| `RelatedMitreTactics ` | <span data-ttu-id="a79a1-133">문자열</span><span class="sxs-lookup"><span data-stu-id="a79a1-133">string</span></span> | <span data-ttu-id="a79a1-134">구성과 관련된 Mitre ATT&CK 프레임워크 전술 목록</span><span class="sxs-lookup"><span data-stu-id="a79a1-134">List of Mitre ATT&CK framework tactics related to the configuration</span></span> |

## <a name="related-topics"></a><span data-ttu-id="a79a1-135">관련 항목</span><span class="sxs-lookup"><span data-stu-id="a79a1-135">Related topics</span></span>

- [<span data-ttu-id="a79a1-136">사전 대응식 위협 탐지</span><span class="sxs-lookup"><span data-stu-id="a79a1-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a79a1-137">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="a79a1-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="a79a1-138">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="a79a1-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="a79a1-139">장치, 전자 메일, 앱 및 ID를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="a79a1-139">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="a79a1-140">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="a79a1-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="a79a1-141">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="a79a1-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="a79a1-142">위협 및 취약성 관리 개요</span><span class="sxs-lookup"><span data-stu-id="a79a1-142">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
