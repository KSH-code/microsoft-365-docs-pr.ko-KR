---
title: 고급 헌팅 스키마의 DeviceTvmSecureConfigurationAssessment 표
description: 고급 헌팅 계획의 DeviceTvmSecureConfigurationAssessment 표에서 보안 평가 이벤트에 대해 자세히 알아보습니다. 이러한 위협 & 취약성 관리 이벤트는 장치 정보와 보안 구성 세부 정보, 영향 및 규정 준수 정보를 제공합니다.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 위협 방지, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, security configuration, DeviceTvmSecureConfigurationAssessment
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
ms.openlocfilehash: 1c4b71139a0fba84928c3f604e3c770d140d9e2b
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499739"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="45bf1-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="45bf1-105">DeviceTvmSecureConfigurationAssessment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="45bf1-106">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="45bf1-106">**Applies to:**</span></span>
- <span data-ttu-id="45bf1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="45bf1-107">Microsoft 365 Defender</span></span>



<span data-ttu-id="45bf1-108">`DeviceTvmSecureConfigurationAssessment` 표의 각 행에는 [위협 및 취약성 관리](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)의 특정 보안 구성에 대한 평가 이벤트가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45bf1-108">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="45bf1-109">이 참조를 사용하여 최신 평가 결과를 확인하고 장치가 호환되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="45bf1-109">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="45bf1-110">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="45bf1-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="45bf1-111">열 이름</span><span class="sxs-lookup"><span data-stu-id="45bf1-111">Column name</span></span> | <span data-ttu-id="45bf1-112">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="45bf1-112">Data type</span></span> | <span data-ttu-id="45bf1-113">설명</span><span class="sxs-lookup"><span data-stu-id="45bf1-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="45bf1-114">문자열</span><span class="sxs-lookup"><span data-stu-id="45bf1-114">string</span></span> | <span data-ttu-id="45bf1-115">서비스에서 디바이스의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="45bf1-115">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="45bf1-116">문자열</span><span class="sxs-lookup"><span data-stu-id="45bf1-116">string</span></span> | <span data-ttu-id="45bf1-117">장치의 FQDN(FQDN)</span><span class="sxs-lookup"><span data-stu-id="45bf1-117">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="45bf1-118">문자열</span><span class="sxs-lookup"><span data-stu-id="45bf1-118">string</span></span> | <span data-ttu-id="45bf1-119">디바이스에서 실행되는 운영 체제의 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="45bf1-119">Platform of the operating system running on the device.</span></span> <span data-ttu-id="45bf1-120">이는 Windows 10 및 Windows 7과 같이 동일한 제품군 내의 변형을 포함하여 특정 운영 체제를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="45bf1-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="45bf1-121">날짜 시간</span><span class="sxs-lookup"><span data-stu-id="45bf1-121">datetime</span></span> | <span data-ttu-id="45bf1-122">레코드 생성 날짜 및 시간</span><span class="sxs-lookup"><span data-stu-id="45bf1-122">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="45bf1-123">문자열</span><span class="sxs-lookup"><span data-stu-id="45bf1-123">string</span></span> | <span data-ttu-id="45bf1-124">특정 구성의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="45bf1-124">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="45bf1-125">문자열</span><span class="sxs-lookup"><span data-stu-id="45bf1-125">string</span></span> | <span data-ttu-id="45bf1-126">구성이 속해 있는 범주 또는 그룹(응용 프로그램, OS, 네트워크, 계정, 보안 제어)</span><span class="sxs-lookup"><span data-stu-id="45bf1-126">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="45bf1-127">문자열</span><span class="sxs-lookup"><span data-stu-id="45bf1-127">string</span></span> | <span data-ttu-id="45bf1-128">구성이 속한 하위 범주나 하위 그룹</span><span class="sxs-lookup"><span data-stu-id="45bf1-128">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="45bf1-129">대부분의 경우 이는 특정 기능이나 특징을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="45bf1-129">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="45bf1-130">문자열</span><span class="sxs-lookup"><span data-stu-id="45bf1-130">string</span></span> | <span data-ttu-id="45bf1-131">구성의 등급이 전반적인 구성 점수에 미치는 영향(1-10)</span><span class="sxs-lookup"><span data-stu-id="45bf1-131">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="45bf1-132">부울</span><span class="sxs-lookup"><span data-stu-id="45bf1-132">boolean</span></span> | <span data-ttu-id="45bf1-133">구성 또는 정책이 올바르게 구성되어 있는지 여부</span><span class="sxs-lookup"><span data-stu-id="45bf1-133">Indicates whether the configuration or policy is properly configured</span></span> |
| `IsApplicable` | <span data-ttu-id="45bf1-134">부울</span><span class="sxs-lookup"><span data-stu-id="45bf1-134">boolean</span></span> | <span data-ttu-id="45bf1-135">구성 또는 정책이 장치에 적용되는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="45bf1-135">Indicates whether the configuration or policy applies to the device</span></span> |
| `Context` | <span data-ttu-id="45bf1-136">문자열</span><span class="sxs-lookup"><span data-stu-id="45bf1-136">string</span></span> | <span data-ttu-id="45bf1-137">구성 또는 정책에 대한 추가 상황 정보</span><span class="sxs-lookup"><span data-stu-id="45bf1-137">Additional contextual information about the configuration or policy</span></span> |
| `IsExpectedUserImpact` | <span data-ttu-id="45bf1-138">부울</span><span class="sxs-lookup"><span data-stu-id="45bf1-138">boolean</span></span> | <span data-ttu-id="45bf1-139">구성 또는 정책이 적용되는 경우 사용자에게 영향을 줄지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="45bf1-139">Indicates whether there will be user impact if the configuration or policy is applied</span></span> |

## <a name="related-topics"></a><span data-ttu-id="45bf1-140">관련 항목</span><span class="sxs-lookup"><span data-stu-id="45bf1-140">Related topics</span></span>

- [<span data-ttu-id="45bf1-141">사전 대응식 위협 탐지</span><span class="sxs-lookup"><span data-stu-id="45bf1-141">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="45bf1-142">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="45bf1-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="45bf1-143">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="45bf1-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="45bf1-144">장치, 전자 메일, 앱 및 ID를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="45bf1-144">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="45bf1-145">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="45bf1-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="45bf1-146">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="45bf1-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="45bf1-147">위협 및 취약성 관리 개요</span><span class="sxs-lookup"><span data-stu-id="45bf1-147">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)