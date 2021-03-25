---
title: 고급 헌팅 스키마의 DeviceTvmSecureConfigurationAssessment 표
description: 고급 헌팅 & DeviceTvmSecureConfigurationAssessment 표에서 위협 및 취약성 관리 보안 평가 이벤트에 대해 자세히 알아보습니다. 이러한 이벤트는 장치 정보와 보안 구성 세부 정보, 영향 및 규정 준수 정보를 제공합니다.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, mdatp, microsoft defender atp, wdatp 검색, 쿼리, 원격 분석, schema 참조, kusto, 표, 열, 데이터 형식, 설명, 위협 & 취약성 관리, TVM, 장치 관리, 보안 구성, DeviceTvmSecureConfigurationAssessment
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
ms.openlocfilehash: 1be5d911d1a2d21abdadce5745151a2778361672
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075047"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="3d464-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="3d464-105">DeviceTvmSecureConfigurationAssessment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3d464-106">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="3d464-106">**Applies to:**</span></span>
- [<span data-ttu-id="3d464-107">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3d464-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)



><span data-ttu-id="3d464-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="3d464-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="3d464-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="3d464-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="3d464-110">`DeviceTvmSecureConfigurationAssessment` 표의 각 행에는 [위협 및 취약성 관리](next-gen-threat-and-vuln-mgt.md)의 특정 보안 구성에 대한 평가 이벤트가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d464-110">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md).</span></span> <span data-ttu-id="3d464-111">이 참조를 사용하여 최신 평가 결과를 확인하고 장치가 호환되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3d464-111">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="3d464-112">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d464-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="3d464-113">열 이름</span><span class="sxs-lookup"><span data-stu-id="3d464-113">Column name</span></span> | <span data-ttu-id="3d464-114">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3d464-114">Data type</span></span> | <span data-ttu-id="3d464-115">설명</span><span class="sxs-lookup"><span data-stu-id="3d464-115">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="3d464-116">문자열</span><span class="sxs-lookup"><span data-stu-id="3d464-116">string</span></span> | <span data-ttu-id="3d464-117">서비스에서 디바이스의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="3d464-117">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="3d464-118">문자열</span><span class="sxs-lookup"><span data-stu-id="3d464-118">string</span></span> | <span data-ttu-id="3d464-119">장치의 FQDN(FQDN)</span><span class="sxs-lookup"><span data-stu-id="3d464-119">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="3d464-120">문자열</span><span class="sxs-lookup"><span data-stu-id="3d464-120">string</span></span> | <span data-ttu-id="3d464-121">디바이스에서 실행되는 운영 체제의 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="3d464-121">Platform of the operating system running on the device.</span></span> <span data-ttu-id="3d464-122">이는 Windows 10 및 Windows 7과 같이 동일한 제품군 내의 변형을 포함하여 특정 운영 체제를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3d464-122">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="3d464-123">날짜 시간</span><span class="sxs-lookup"><span data-stu-id="3d464-123">datetime</span></span> |<span data-ttu-id="3d464-124">레코드 생성 날짜 및 시간</span><span class="sxs-lookup"><span data-stu-id="3d464-124">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="3d464-125">문자열</span><span class="sxs-lookup"><span data-stu-id="3d464-125">string</span></span> | <span data-ttu-id="3d464-126">특정 구성의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="3d464-126">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="3d464-127">문자열</span><span class="sxs-lookup"><span data-stu-id="3d464-127">string</span></span> | <span data-ttu-id="3d464-128">구성이 속해 있는 범주 또는 그룹(응용 프로그램, OS, 네트워크, 계정, 보안 제어)</span><span class="sxs-lookup"><span data-stu-id="3d464-128">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="3d464-129">문자열</span><span class="sxs-lookup"><span data-stu-id="3d464-129">string</span></span> |<span data-ttu-id="3d464-130">구성이 속한 하위 범주나 하위 그룹</span><span class="sxs-lookup"><span data-stu-id="3d464-130">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="3d464-131">대부분의 경우 이는 특정 기능이나 특징을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3d464-131">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="3d464-132">문자열</span><span class="sxs-lookup"><span data-stu-id="3d464-132">string</span></span> | <span data-ttu-id="3d464-133">구성의 등급이 전반적인 구성 점수에 미치는 영향(1-10)</span><span class="sxs-lookup"><span data-stu-id="3d464-133">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="3d464-134">부울</span><span class="sxs-lookup"><span data-stu-id="3d464-134">boolean</span></span> | <span data-ttu-id="3d464-135">구성 또는 정책이 올바르게 구성되어 있는지 여부</span><span class="sxs-lookup"><span data-stu-id="3d464-135">Indicates whether the configuration or policy is properly configured</span></span> |
| `IsApplicable` | <span data-ttu-id="3d464-136">부울</span><span class="sxs-lookup"><span data-stu-id="3d464-136">boolean</span></span> | <span data-ttu-id="3d464-137">구성 또는 정책이 장치에 적용되는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3d464-137">Indicates whether the configuration or policy applies to the device</span></span> |
| `Context` | <span data-ttu-id="3d464-138">문자열</span><span class="sxs-lookup"><span data-stu-id="3d464-138">string</span></span> | <span data-ttu-id="3d464-139">구성 또는 정책에 대한 추가 상황 정보</span><span class="sxs-lookup"><span data-stu-id="3d464-139">Additional contextual information about the configuration or policy</span></span> |
| `IsExpectedUserImpactCompliant` | <span data-ttu-id="3d464-140">부울</span><span class="sxs-lookup"><span data-stu-id="3d464-140">boolean</span></span> | <span data-ttu-id="3d464-141">구성 또는 정책이 적용되는 경우 사용자에게 영향을 줄지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3d464-141">Indicates whether there will be user impact if the configuration or policy is applied</span></span> |

## <a name="related-topics"></a><span data-ttu-id="3d464-142">관련 항목</span><span class="sxs-lookup"><span data-stu-id="3d464-142">Related topics</span></span>

- [<span data-ttu-id="3d464-143">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="3d464-143">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="3d464-144">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="3d464-144">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="3d464-145">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="3d464-145">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="3d464-146">위협 및 취약성 관리 개요</span><span class="sxs-lookup"><span data-stu-id="3d464-146">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)