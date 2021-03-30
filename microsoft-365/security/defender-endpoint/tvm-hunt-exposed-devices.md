---
title: 노출된 장치 헌팅
description: 보안 관리자, IT 관리자 및 SecOps가 공동 작업을 하는 데 위협 및 취약성 관리를 사용하는 방법에 대해 자세히 알아보습니다.
keywords: mdatp-tvm 시나리오, mdatp, tvm, tvm 시나리오, 위협 & 취약성 노출 감소, 위협 및 취약성 감소, 보안 구성 향상, 장치에 대한 Microsoft 보안 점수 증가, 장치용 Microsoft 보안 점수 증가& 장치용 Microsoft 보안 점수, 장치에 대한 Microsoft 보안 점수, 노출 점수, 보안 제어
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 99e59005bc01a113567e64c921ddcdc1d66785d2
ms.sourcegitcommit: c75aac39ee8d93218a79585113ef6b36f47c9ddf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/29/2021
ms.locfileid: "51408294"
---
# <a name="hunt-for-exposed-devices---threat-and-vulnerability-management"></a><span data-ttu-id="4d31f-104">노출된 장치 헌트 - 위협 및 취약성 관리</span><span class="sxs-lookup"><span data-stu-id="4d31f-104">Hunt for exposed devices - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4d31f-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="4d31f-105">**Applies to:**</span></span>

- [<span data-ttu-id="4d31f-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="4d31f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="4d31f-107">위협 및 취약점 관리</span><span class="sxs-lookup"><span data-stu-id="4d31f-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="4d31f-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4d31f-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="4d31f-109">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="4d31f-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4d31f-110">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="4d31f-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

## <a name="use-advanced-hunting-to-find-devices-with-vulnerabilities"></a><span data-ttu-id="4d31f-111">고급 헌팅을 사용하여 취약성 있는 장치 찾기</span><span class="sxs-lookup"><span data-stu-id="4d31f-111">Use advanced hunting to find devices with vulnerabilities</span></span>

<span data-ttu-id="4d31f-112">고급 헌팅은 최대 30일간의 원시 데이터를 탐색할 수 있는 쿼리 기반의 위협 헌팅 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="4d31f-112">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data.</span></span> <span data-ttu-id="4d31f-113">네트워크에서 이벤트를 사전 검사하여 위협 표시기 및 엔터티를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d31f-113">You can proactively inspect events in your network to locate threat indicators and entities.</span></span> <span data-ttu-id="4d31f-114">데이터에 대한 유연한 액세스를 통해 알려진 위협과 잠재적 위협 모두에 대한 제약이 없는 헌팅을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d31f-114">The flexible access to data enables unconstrained hunting for both known and potential threats.</span></span> [<span data-ttu-id="4d31f-115">고급 헌팅에 대해 자세히 알아보시다</span><span class="sxs-lookup"><span data-stu-id="4d31f-115">Learn more about advanced hunting</span></span>](advanced-hunting-overview.md)

### <a name="schema-tables"></a><span data-ttu-id="4d31f-116">스키마 표</span><span class="sxs-lookup"><span data-stu-id="4d31f-116">Schema tables</span></span>

- <span data-ttu-id="4d31f-117">[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md) - 버전 정보 및 지원 종료 상태를 포함하여 장치에 설치된 소프트웨어 인벤토리입니다.</span><span class="sxs-lookup"><span data-stu-id="4d31f-117">[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md) - Inventory of software installed on devices, including their version information and end-of-support status.</span></span>

- <span data-ttu-id="4d31f-118">[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md) - 장치에서 발견되는 소프트웨어 취약성 및 각 취약점을 해결 하는 사용 가능한 보안 업데이트 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="4d31f-118">[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md) - Software vulnerabilities found on devices and the list of available security updates that address each vulnerability.</span></span>

- <span data-ttu-id="4d31f-119">[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md) - 악용 코드를 공개적으로 사용할 수 있는지 여부를 포함하여 공개적으로 공개된 취약성의 기술 자료입니다.</span><span class="sxs-lookup"><span data-stu-id="4d31f-119">[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md) - Knowledge base of publicly disclosed vulnerabilities, including whether exploit code is publicly available.</span></span>

- <span data-ttu-id="4d31f-120">[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md) - 장치의 다양한 보안 구성 상태를 나타내는 위협 및 취약성 관리 평가 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="4d31f-120">[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md) - Threat and vulnerability management assessment events, indicating the status of various security configurations on devices.</span></span>

- <span data-ttu-id="4d31f-121">[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md) - 위협 및 취약성 관리에서 장치를 평가하는 데 & 다양한 보안 구성의 기술 자료 다양한 표준 및 벤치마크에 대한 매핑 포함</span><span class="sxs-lookup"><span data-stu-id="4d31f-121">[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md) - Knowledge base of various security configurations used by Threat & Vulnerability Management to assess devices; includes mappings to various standards and benchmarks</span></span>

## <a name="check-which-devices-are-involved-in-high-severity-alerts"></a><span data-ttu-id="4d31f-122">높은 심각도 경고에 포함되는 장치 확인</span><span class="sxs-lookup"><span data-stu-id="4d31f-122">Check which devices are involved in high severity alerts</span></span>

1. <span data-ttu-id="4d31f-123">Microsoft Defender **보안** 센터의 왼쪽 탐색 창에서 고급 헌팅으로 이동</span><span class="sxs-lookup"><span data-stu-id="4d31f-123">Go to **Advanced hunting** from the left-hand navigation pane of the Microsoft Defender Security Center.</span></span>

2. <span data-ttu-id="4d31f-124">열 이름에 익숙해지기 위해 TVM 고급 헌팅 스마마까지 아래로 스크롤합니다.</span><span class="sxs-lookup"><span data-stu-id="4d31f-124">Scroll down to the TVM advanced hunting schemas to familiarize yourself with the column names.</span></span>

3. <span data-ttu-id="4d31f-125">다음 쿼리를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4d31f-125">Enter the following queries:</span></span>

```kusto
// Search for devices with High active alerts or Critical CVE public exploit
DeviceTvmSoftwareVulnerabilities
| join kind=inner(DeviceTvmSoftwareVulnerabilitiesKB) on CveId
| where IsExploitAvailable == 1 and CvssScore >= 7
| summarize NumOfVulnerabilities=dcount(CveId),
DeviceName=any(DeviceName) by DeviceId
| join kind =inner(DeviceAlertEvents) on DeviceId  
| summarize NumOfVulnerabilities=any(NumOfVulnerabilities),
DeviceName=any(DeviceName) by DeviceId, AlertId
| project DeviceName, NumOfVulnerabilities, AlertId  
| order by NumOfVulnerabilities desc
```

## <a name="related-topics"></a><span data-ttu-id="4d31f-126">관련 항목</span><span class="sxs-lookup"><span data-stu-id="4d31f-126">Related topics</span></span>

- [<span data-ttu-id="4d31f-127">위협 및 취약성 관리 개요</span><span class="sxs-lookup"><span data-stu-id="4d31f-127">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="4d31f-128">보안 권장 사항</span><span class="sxs-lookup"><span data-stu-id="4d31f-128">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="4d31f-129">API</span><span class="sxs-lookup"><span data-stu-id="4d31f-129">APIs</span></span>](next-gen-threat-and-vuln-mgt.md#apis)
- [<span data-ttu-id="4d31f-130">위협 및 취약성 관리 역할에 대한 데이터 액세스 구성</span><span class="sxs-lookup"><span data-stu-id="4d31f-130">Configure data access for threat and vulnerability management roles</span></span>](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group)
- [<span data-ttu-id="4d31f-131">지능형 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="4d31f-131">Advanced hunting overview</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
- [<span data-ttu-id="4d31f-132">모든 고급 헌팅 테이블</span><span class="sxs-lookup"><span data-stu-id="4d31f-132">All advanced hunting tables</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference.md)
