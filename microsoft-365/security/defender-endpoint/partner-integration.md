---
title: Microsoft Defender ATP 파트너 기회 및 시나리오
ms.reviewer: ''
description: 개방형 프레임워크 및 다양한 API 집합을 토폴로지에서 기존 보안 서비스를 확장하여 Microsoft Defender ATP와의 확장 및 통합을 구축하는 방법에 대해 자세히 알아보습니다.
keywords: API, 파트너, 확장, 개방형 프레임워크, api, 확장, 통합, 감지, 관리, 응답, 취약성, 인텔리전스
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 1db82afa06fd0b6b3d7228aaf3020c5496ed69e7
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186896"
---
# <a name="microsoft-defender-for-endpoint-partner-opportunities-and-scenarios"></a><span data-ttu-id="4082b-104">끝점 파트너 기회 및 시나리오용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="4082b-104">Microsoft Defender for Endpoint partner opportunities and scenarios</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4082b-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="4082b-105">**Applies to:**</span></span>
- [<span data-ttu-id="4082b-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="4082b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4082b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4082b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="4082b-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="4082b-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4082b-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="4082b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="4082b-110">파트너는 개방형 프레임워크 및 풍부한 API 집합을 통해 기존 보안 서비스를 쉽게 확장하여 끝점용 Defender와의 확장 및 통합을 구축할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4082b-110">Partners can easily extend their existing security offerings on top of the open framework and a rich and complete set of APIs to build extensions and integrations with Defender for Endpoint.</span></span> 

<span data-ttu-id="4082b-111">API는 검색, 관리, 대응, 취약성 및 인텔리전스 전체 사용 사례를 비롯한 기능 영역에 걸쳐 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4082b-111">The APIs span functional areas including detection, management, response, vulnerabilities, and intelligence-wide range of use cases.</span></span> <span data-ttu-id="4082b-112">사용 사례 및 필요에 따라 파트너는 끝점용 Defender에서 데이터를 스트리밍하거나 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4082b-112">Based on the use case and need, partners can either stream or query data from Defender for Endpoint.</span></span> 


## <a name="scenario-1-external-alert-correlation-and-automated-investigation-and-remediation"></a><span data-ttu-id="4082b-113">시나리오 1: 외부 경고 상관 관계 및 자동화된 조사 및 수정</span><span class="sxs-lookup"><span data-stu-id="4082b-113">Scenario 1: External alert correlation and Automated investigation and remediation</span></span>
<span data-ttu-id="4082b-114">Endpoint용 Defender는 인시던트 대응을 대규모로 구동하는 고유한 자동화된 조사 및 수정 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4082b-114">Defender for Endpoint offers unique automated investigation and remediation capabilities to drive incident response at scale.</span></span> 

<span data-ttu-id="4082b-115">자동화된 조사 및 응답 기능을 네트워크 보안 제품 또는 기타 끝점 보안 제품과 같은 다른 솔루션과 통합하면 경고를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4082b-115">Integrating the automated investigation and response capability with other solutions such as network security products or other endpoint security products will help to address alerts.</span></span> <span data-ttu-id="4082b-116">또한 통합은 네트워크 및 장치 신호 상관 관계와 관련한 복잡한 문제를 최소화하여 디바이스에서 조사 및 위협 수정 작업을 효과적으로 간소화합니다.</span><span class="sxs-lookup"><span data-stu-id="4082b-116">The integration also minimizes the complexities surrounding network and device signal correlation, effectively streamlining the investigation and threat remediation actions on devices.</span></span>

<span data-ttu-id="4082b-117">Endpoint용 Defender는 다음 양식에서 이 시나리오에 대한 지원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4082b-117">Defender for Endpoint adds support for this scenario in the following forms:</span></span>

- <span data-ttu-id="4082b-118">외부 경고는 Endpoint용 Defender로 푸시하고 Endpoint용 Defender의 추가 장치 기반 경고와 함께 나란히 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4082b-118">External alerts can be pushed into Defender for Endpoint and presented side by side with additional device-based alerts from Defender for Endpoint.</span></span> <span data-ttu-id="4082b-119">이 보기는 실제 프로세스 및 전체 공격 스토리를 통해 경고의 전체 컨텍스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4082b-119">This view provides the full context of the alert - with the real process and the full story of attack.</span></span>

- <span data-ttu-id="4082b-120">경고가 생성된 후 엔터프라이즈의 끝점으로 보호된 끝점에 대한 모든 Defender에서 신호가 공유됩니다.</span><span class="sxs-lookup"><span data-stu-id="4082b-120">Once an alert is generated, the signal is shared across all Defender for Endpoint protected endpoints in the enterprise.</span></span> <span data-ttu-id="4082b-121">Endpoint용 Defender는 경고를 해결하기 위해 즉각적인 자동화 또는 운영자 지원 응답을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4082b-121">Defender for Endpoint takes immediate automated or operator-assisted response to address the alert.</span></span>

## <a name="scenario-2-security-orchestration-and-automation-response-soar-integration"></a><span data-ttu-id="4082b-122">시나리오 2: SOAR(보안 오케스트레이션 및 자동화 응답) 통합</span><span class="sxs-lookup"><span data-stu-id="4082b-122">Scenario 2: Security orchestration and automation response (SOAR) integration</span></span>
<span data-ttu-id="4082b-123">오케스트레이션 솔루션은 플레이북을 빌드하고 엔드포인트 API용 Defender가 장치 데이터 쿼리, 장치 격리 트리거, 차단/허용, 경고 해결 등의 응답을 오케스트레이션하기 위해 노출하는 다양한 데이터 모델과 작업을 통합하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4082b-123">Orchestration solutions can help build playbooks and integrate the rich data model and actions that Defender for Endpoint APIs expose to orchestrate responses, such as query for device data, trigger device isolation, block/allow, resolve alert and others.</span></span>

## <a name="scenario-3-indicators-matching"></a><span data-ttu-id="4082b-124">시나리오 3: 일치하는 표시기</span><span class="sxs-lookup"><span data-stu-id="4082b-124">Scenario 3: Indicators matching</span></span> 
<span data-ttu-id="4082b-125">IoC(손상 표시기) 일치는 모든 끝점 보호 솔루션에서 필수적인 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="4082b-125">Indicator of compromise (IoCs) matching is an essential feature in every endpoint protection solution.</span></span> <span data-ttu-id="4082b-126">이 기능은 Endpoint용 Defender에서 사용할 수 있으며 엔터티의 방지, 검색 및 제외에 대한 표시기 목록을 설정하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4082b-126">This capability is available in Defender for Endpoint and gives the ability to set a list of indicators for prevention, detection, and exclusion of entities.</span></span> <span data-ttu-id="4082b-127">작업 적용 기간뿐만 아니라 수행될 작업을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4082b-127">One can define the action to be taken as well as the duration for when to apply the action.</span></span>

<span data-ttu-id="4082b-128">위의 시나리오는 플랫폼의 extensibility의 예로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4082b-128">The above scenarios serve as examples of the extensibility of the platform.</span></span> <span data-ttu-id="4082b-129">예제로 제한되지는 않습니다. 개방형 프레임워크를 활용하여 다른 시나리오를 검색하고 탐색하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4082b-129">You are not limited to the examples and we certainly encourage you to leverage the open framework to discover and explore other scenarios.</span></span>

<span data-ttu-id="4082b-130">[Endpoint용 Microsoft Defender](get-started-partner-integration.md) 파트너 되기의 단계에 따라 끝점용 Defender에서 솔루션을 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="4082b-130">Follow the steps in [Become a Microsoft Defender for Endpoint partner](get-started-partner-integration.md) to integrate your solution in Defender for Endpoint.</span></span>

## <a name="related-topic"></a><span data-ttu-id="4082b-131">관련 항목</span><span class="sxs-lookup"><span data-stu-id="4082b-131">Related topic</span></span>
- [<span data-ttu-id="4082b-132">관리 및 API 개요</span><span class="sxs-lookup"><span data-stu-id="4082b-132">Overview of management and APIs</span></span>](management-apis.md)
