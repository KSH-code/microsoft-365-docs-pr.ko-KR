---
title: 고급 헌팅 스키마의 DeviceTvmSecureConfigurationAssessmentKB 표
description: Advanced hunting schema의 DeviceTvmSecureConfigurationAssessmentKB 표에서 위협 및 취약성 & 평가하는 다양한 보안 구성에 대해 자세히 알아보습니다.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, mdatp, microsoft defender atp, wdatp 검색, 쿼리, 원격 분석, schema 참조, kusto, 표, 열, 데이터 형식, 설명, 위협 & 취약성 관리, TVM, 장치 관리, 보안 구성, MITRE ATT&CK 프레임워크, 기술 자료, KB, DeviceTvmSecureConfigurationAssesmentKB
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
ms.openlocfilehash: 3ba0d90fae872eff209b41b7ba62baeccfe62808
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075044"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="5a901-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="5a901-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5a901-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="5a901-105">**Applies to:**</span></span>
- [<span data-ttu-id="5a901-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="5a901-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="5a901-107">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="5a901-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5a901-108">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="5a901-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="5a901-109">고급 헌팅 스키마의 `DeviceTvmSecureConfigurationAssessmentKB` 표에는 [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md)에서 확인되는 장치가 자동 업데이트를 보유하고 있는지에 대한 정보 등의 다양한 보안 구성 관련 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a901-109">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md).</span></span> <span data-ttu-id="5a901-110">또한 위험 정보, 관련 산업 벤치마크 및 해당 MITRE ATT&CK 기법 및 전술을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="5a901-110">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="5a901-111">이 참조를 사용하여 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="5a901-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="5a901-112">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5a901-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="5a901-113">열 이름</span><span class="sxs-lookup"><span data-stu-id="5a901-113">Column name</span></span> | <span data-ttu-id="5a901-114">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="5a901-114">Data type</span></span> | <span data-ttu-id="5a901-115">설명</span><span class="sxs-lookup"><span data-stu-id="5a901-115">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="5a901-116">문자열</span><span class="sxs-lookup"><span data-stu-id="5a901-116">string</span></span> | <span data-ttu-id="5a901-117">특정 구성의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="5a901-117">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="5a901-118">문자열</span><span class="sxs-lookup"><span data-stu-id="5a901-118">string</span></span> | <span data-ttu-id="5a901-119">구성의 등급이 전반적인 구성 점수에 미치는 영향(1-10)</span><span class="sxs-lookup"><span data-stu-id="5a901-119">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="5a901-120">문자열</span><span class="sxs-lookup"><span data-stu-id="5a901-120">string</span></span> | <span data-ttu-id="5a901-121">구성 이름을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5a901-121">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="5a901-122">문자열</span><span class="sxs-lookup"><span data-stu-id="5a901-122">string</span></span> | <span data-ttu-id="5a901-123">구성에 대한 설명</span><span class="sxs-lookup"><span data-stu-id="5a901-123">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="5a901-124">문자열</span><span class="sxs-lookup"><span data-stu-id="5a901-124">string</span></span> | <span data-ttu-id="5a901-125">관련 위험에 대한 설명</span><span class="sxs-lookup"><span data-stu-id="5a901-125">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="5a901-126">문자열</span><span class="sxs-lookup"><span data-stu-id="5a901-126">string</span></span> | <span data-ttu-id="5a901-127">구성이 속해 있는 범주 또는 그룹(응용 프로그램, OS, 네트워크, 계정, 보안 제어)</span><span class="sxs-lookup"><span data-stu-id="5a901-127">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="5a901-128">문자열</span><span class="sxs-lookup"><span data-stu-id="5a901-128">string</span></span> |<span data-ttu-id="5a901-129">구성이 속한 하위 범주나 하위 그룹</span><span class="sxs-lookup"><span data-stu-id="5a901-129">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="5a901-130">대부분의 경우 이는 특정 기능이나 특징을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5a901-130">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="5a901-131">문자열</span><span class="sxs-lookup"><span data-stu-id="5a901-131">string</span></span> | <span data-ttu-id="5a901-132">동일하거나 유사한 구성을 제안하는 산업 벤치마크 목록</span><span class="sxs-lookup"><span data-stu-id="5a901-132">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `RelatedMitreTechniques` | <span data-ttu-id="5a901-133">문자열</span><span class="sxs-lookup"><span data-stu-id="5a901-133">string</span></span> | <span data-ttu-id="5a901-134">구성과 관련된 Mitre ATT&CK 프레임워크 기법 목록</span><span class="sxs-lookup"><span data-stu-id="5a901-134">List of Mitre ATT&CK framework techniques related to the configuration</span></span> |
| `RelatedMitreTactics ` | <span data-ttu-id="5a901-135">문자열</span><span class="sxs-lookup"><span data-stu-id="5a901-135">string</span></span> | <span data-ttu-id="5a901-136">구성과 관련된 Mitre ATT&CK 프레임워크 전술 목록</span><span class="sxs-lookup"><span data-stu-id="5a901-136">List of Mitre ATT&CK framework tactics related to the configuration</span></span> |

## <a name="related-topics"></a><span data-ttu-id="5a901-137">관련 항목</span><span class="sxs-lookup"><span data-stu-id="5a901-137">Related topics</span></span>

- [<span data-ttu-id="5a901-138">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="5a901-138">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="5a901-139">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="5a901-139">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="5a901-140">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="5a901-140">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="5a901-141">위협 및 취약성 관리 개요</span><span class="sxs-lookup"><span data-stu-id="5a901-141">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)
