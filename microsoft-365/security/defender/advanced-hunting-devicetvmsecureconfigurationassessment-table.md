---
title: 고급 헌팅 스키마의 DeviceTvmSecureConfigurationAssessment 표
description: 고급 헌팅 계획의 DeviceTvmSecureConfigurationAssessment 표에서 보안 평가 이벤트에 대해 자세히 알아보습니다. 이러한 위협 & 취약성 관리 이벤트는 장치 정보와 보안 구성 세부 정보, 영향 및 규정 준수 정보를 제공합니다.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 365 Defender, microsoft 365, m365, 검색, 쿼리, 원격 분석, 스마마 참조, kusto, 표, 열, 데이터 형식, 설명, 위협 & 취약성 관리, TVM, 장치 관리, 보안 구성, DeviceTvmSecureConfigurationAssessment
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
ms.openlocfilehash: 2e3e649911cb2ce63c2a49be0ebc93e35e8055d6
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2021
ms.locfileid: "52024220"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="e38e5-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="e38e5-105">DeviceTvmSecureConfigurationAssessment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e38e5-106">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="e38e5-106">**Applies to:**</span></span>
- <span data-ttu-id="e38e5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e38e5-107">Microsoft 365 Defender</span></span>
- <span data-ttu-id="e38e5-108">끝점용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e38e5-108">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="e38e5-109">`DeviceTvmSecureConfigurationAssessment` 표의 각 행에는 [위협 및 취약성 관리](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)의 특정 보안 구성에 대한 평가 이벤트가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e38e5-109">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="e38e5-110">이 참조를 사용하여 최신 평가 결과를 확인하고 장치가 호환되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e38e5-110">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="e38e5-111">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e38e5-111">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="e38e5-112">열 이름</span><span class="sxs-lookup"><span data-stu-id="e38e5-112">Column name</span></span> | <span data-ttu-id="e38e5-113">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="e38e5-113">Data type</span></span> | <span data-ttu-id="e38e5-114">설명</span><span class="sxs-lookup"><span data-stu-id="e38e5-114">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="e38e5-115">문자열</span><span class="sxs-lookup"><span data-stu-id="e38e5-115">string</span></span> | <span data-ttu-id="e38e5-116">서비스에서 디바이스의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="e38e5-116">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="e38e5-117">문자열</span><span class="sxs-lookup"><span data-stu-id="e38e5-117">string</span></span> | <span data-ttu-id="e38e5-118">장치의 FQDN(FQDN)</span><span class="sxs-lookup"><span data-stu-id="e38e5-118">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="e38e5-119">문자열</span><span class="sxs-lookup"><span data-stu-id="e38e5-119">string</span></span> | <span data-ttu-id="e38e5-120">디바이스에서 실행되는 운영 체제의 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="e38e5-120">Platform of the operating system running on the device.</span></span> <span data-ttu-id="e38e5-121">이는 Windows 10 및 Windows 7과 같이 동일한 제품군 내의 변형을 포함하여 특정 운영 체제를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e38e5-121">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="e38e5-122">날짜 시간</span><span class="sxs-lookup"><span data-stu-id="e38e5-122">datetime</span></span> | <span data-ttu-id="e38e5-123">레코드 생성 날짜 및 시간</span><span class="sxs-lookup"><span data-stu-id="e38e5-123">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="e38e5-124">문자열</span><span class="sxs-lookup"><span data-stu-id="e38e5-124">string</span></span> | <span data-ttu-id="e38e5-125">특정 구성의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="e38e5-125">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="e38e5-126">문자열</span><span class="sxs-lookup"><span data-stu-id="e38e5-126">string</span></span> | <span data-ttu-id="e38e5-127">구성이 속해 있는 범주 또는 그룹(응용 프로그램, OS, 네트워크, 계정, 보안 제어)</span><span class="sxs-lookup"><span data-stu-id="e38e5-127">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="e38e5-128">문자열</span><span class="sxs-lookup"><span data-stu-id="e38e5-128">string</span></span> | <span data-ttu-id="e38e5-129">구성이 속한 하위 범주나 하위 그룹</span><span class="sxs-lookup"><span data-stu-id="e38e5-129">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="e38e5-130">대부분의 경우 이는 특정 기능이나 특징을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e38e5-130">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="e38e5-131">문자열</span><span class="sxs-lookup"><span data-stu-id="e38e5-131">string</span></span> | <span data-ttu-id="e38e5-132">구성의 등급이 전반적인 구성 점수에 미치는 영향(1-10)</span><span class="sxs-lookup"><span data-stu-id="e38e5-132">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="e38e5-133">부울</span><span class="sxs-lookup"><span data-stu-id="e38e5-133">boolean</span></span> | <span data-ttu-id="e38e5-134">구성 또는 정책이 올바르게 구성되어 있는지 여부</span><span class="sxs-lookup"><span data-stu-id="e38e5-134">Indicates whether the configuration or policy is properly configured</span></span> |
| `IsApplicable` | <span data-ttu-id="e38e5-135">부울</span><span class="sxs-lookup"><span data-stu-id="e38e5-135">boolean</span></span> | <span data-ttu-id="e38e5-136">구성 또는 정책이 장치에 적용되는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e38e5-136">Indicates whether the configuration or policy applies to the device</span></span> |
| `Context` | <span data-ttu-id="e38e5-137">문자열</span><span class="sxs-lookup"><span data-stu-id="e38e5-137">string</span></span> | <span data-ttu-id="e38e5-138">구성 또는 정책에 대한 추가 상황 정보</span><span class="sxs-lookup"><span data-stu-id="e38e5-138">Additional contextual information about the configuration or policy</span></span> |
| `IsExpectedUserImpact` | <span data-ttu-id="e38e5-139">부울</span><span class="sxs-lookup"><span data-stu-id="e38e5-139">boolean</span></span> | <span data-ttu-id="e38e5-140">구성 또는 정책이 적용되는 경우 사용자에게 영향을 줄지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e38e5-140">Indicates whether there will be user impact if the configuration or policy is applied</span></span> |

## <a name="related-topics"></a><span data-ttu-id="e38e5-141">관련 항목</span><span class="sxs-lookup"><span data-stu-id="e38e5-141">Related topics</span></span>

- [<span data-ttu-id="e38e5-142">사전 대응식 위협 탐지</span><span class="sxs-lookup"><span data-stu-id="e38e5-142">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e38e5-143">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="e38e5-143">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e38e5-144">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="e38e5-144">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="e38e5-145">장치, 전자 메일, 앱 및 ID를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="e38e5-145">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="e38e5-146">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="e38e5-146">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="e38e5-147">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="e38e5-147">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="e38e5-148">위협 및 취약성 관리 개요</span><span class="sxs-lookup"><span data-stu-id="e38e5-148">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)