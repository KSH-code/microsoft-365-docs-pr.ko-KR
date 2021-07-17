---
title: 끝점 아키텍처 요구 사항 및 주요 개념에 대한 Microsoft Defender 검토
description: Microsoft Defender for Endpoint용 기술 다이어그램은 Microsoft 365 Defender 랩 또는 파일럿 환경을 구축하기 전에 Microsoft 365 ID를 이해하는 데 도움이 됩니다.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-jweston
author: jweston-1
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 4df1ac2ca5fdfaa88ec2d08c85112f52da26b873
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458126"
---
# <a name="review-microsoft-defender-for-endpoint-architecture-requirements-and-key-concepts"></a><span data-ttu-id="b0602-103">끝점 아키텍처 요구 사항 및 주요 개념에 대한 Microsoft Defender 검토</span><span class="sxs-lookup"><span data-stu-id="b0602-103">Review Microsoft Defender for Endpoint architecture requirements and key concepts</span></span>

<span data-ttu-id="b0602-104">**적용 사항: Microsoft 365 Defender**</span><span class="sxs-lookup"><span data-stu-id="b0602-104">**Applies to:** Microsoft 365 Defender</span></span>

<span data-ttu-id="b0602-105">이 문서에서는 끝점 환경용 Microsoft Defender에 대한 평가를 설정하는 과정을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="b0602-105">This article will guide you in the process of setting up the evaluation for Microsoft Defender for Endpoint environment.</span></span>

<span data-ttu-id="b0602-106">이 프로세스에 대한 자세한 내용은 개요 문서를 [참조하세요.](eval-defender-endpoint-overview.md)</span><span class="sxs-lookup"><span data-stu-id="b0602-106">For more information about this process, see the [overview article](eval-defender-endpoint-overview.md).</span></span>

<span data-ttu-id="b0602-107">끝점에 대해 Microsoft Defender를 사용하도록 설정하기 전에 아키텍처를 이해하고 요구 사항을 충족할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b0602-107">Before enabling Microsoft Defender for Endpoint, be sure you understand the architecture and can meet the requirements.</span></span>

## <a name="understand-the-architecture"></a><span data-ttu-id="b0602-108">아키텍처 이해</span><span class="sxs-lookup"><span data-stu-id="b0602-108">Understand the architecture</span></span>

<span data-ttu-id="b0602-109">다음 다이어그램에서는 끝점 아키텍처 및 통합을 위한 Microsoft Defender를 보여 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b0602-109">The following diagram illustrates Microsoft Defender for Endpoint architecture and integrations.</span></span> 

![Defender 평가 환경에 Office Microsoft Defender를 추가하는 단계](../../media/defender/m365-defender-endpoint-architecture.png)

<span data-ttu-id="b0602-111">다음 표에서는 그림에 대해 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0602-111">The following table describes the illustration.</span></span>

<span data-ttu-id="b0602-112">Call-out</span><span class="sxs-lookup"><span data-stu-id="b0602-112">Call-out</span></span> | <span data-ttu-id="b0602-113">설명</span><span class="sxs-lookup"><span data-stu-id="b0602-113">Description</span></span>
:---|:---|
<span data-ttu-id="b0602-114">1</span><span class="sxs-lookup"><span data-stu-id="b0602-114">1</span></span> | <span data-ttu-id="b0602-115">디바이스는 지원되는 관리 도구 중 하나를 통해 보드됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0602-115">Devices are on-boarded through one of the supported management tools.</span></span> 
<span data-ttu-id="b0602-116">2 </span><span class="sxs-lookup"><span data-stu-id="b0602-116">2</span></span> | <span data-ttu-id="b0602-117">On-boarded devices provide and respond to Microsoft Defender for Endpoint signal data.</span><span class="sxs-lookup"><span data-stu-id="b0602-117">On-boarded devices provide and respond to Microsoft Defender for Endpoint signal data.</span></span>
<span data-ttu-id="b0602-118">3 </span><span class="sxs-lookup"><span data-stu-id="b0602-118">3</span></span> | <span data-ttu-id="b0602-119">관리되는 디바이스가 가입 및/또는 등록된 Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b0602-119">Managed devices are joined and/or enrolled in Azure Active Directory.</span></span>
<span data-ttu-id="b0602-120">4 </span><span class="sxs-lookup"><span data-stu-id="b0602-120">4</span></span> | <span data-ttu-id="b0602-121">도메인에 가입된 Windows 10 장치를 사용하여 Azure Active Directory 동기화 Azure Active Directory 커넥트.</span><span class="sxs-lookup"><span data-stu-id="b0602-121">Domain-joined Windows 10 devices are synchronized to Azure Active Directory using Azure Active Directory Connect.</span></span>
<span data-ttu-id="b0602-122">5 </span><span class="sxs-lookup"><span data-stu-id="b0602-122">5</span></span> | <span data-ttu-id="b0602-123">끝점 경고, 조사 및 응답에 대한 Microsoft Defender는 모든 Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="b0602-123">Microsoft Defender for Endpoint alerts, investigations, and responses are managed in Microsoft 365 Defender.</span></span>

## <a name="understand-key-concepts"></a><span data-ttu-id="b0602-124">주요 개념 이해</span><span class="sxs-lookup"><span data-stu-id="b0602-124">Understand key concepts</span></span>

<span data-ttu-id="b0602-125">다음 표에서는 끝점용 Microsoft Defender를 평가, 구성 및 배포할 때 이해해야 하는 주요 개념을 확인했습니다.</span><span class="sxs-lookup"><span data-stu-id="b0602-125">The following table identified key concepts that are important to understand when evaluating, configuring, and deploying Microsoft Defender for Endpoint:</span></span> 

<span data-ttu-id="b0602-126">개념</span><span class="sxs-lookup"><span data-stu-id="b0602-126">Concept</span></span> | <span data-ttu-id="b0602-127">설명</span><span class="sxs-lookup"><span data-stu-id="b0602-127">Description</span></span> | <span data-ttu-id="b0602-128">추가 정보</span><span class="sxs-lookup"><span data-stu-id="b0602-128">More information</span></span>
:---|:---|:---|
<span data-ttu-id="b0602-129">관리 포털</span><span class="sxs-lookup"><span data-stu-id="b0602-129">Administration Portal</span></span> | <span data-ttu-id="b0602-130">Microsoft 365 Defender 잠재적인 지속적인 위협 활동 또는 데이터 위반 경고에 대한 대응을 모니터링하고 지원할 수 있는 포털입니다.</span><span class="sxs-lookup"><span data-stu-id="b0602-130">Microsoft 365 Defender portal to monitor and assist in responding to alerts of potential advanced persistent threat activity or data breaches.</span></span> | [<span data-ttu-id="b0602-131">끝점용 Microsoft Defender 포털 개요</span><span class="sxs-lookup"><span data-stu-id="b0602-131">Microsoft Defender for Endpoint portal overview</span></span>](/defender-endpoint/portal-overview)
<span data-ttu-id="b0602-132">공격 표면 감소</span><span class="sxs-lookup"><span data-stu-id="b0602-132">Attack Surface Reduction</span></span> | <span data-ttu-id="b0602-133">조직이 사이버 위협 및 공격에 취약한 장소를 최소화하여 공격 표면을 줄이는 데 도움을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0602-133">Help reduce your attack surfaces by minimizing the places where your organization is vulnerable to cyberthreats and attacks.</span></span> | [<span data-ttu-id="b0602-134">공격 표면 감소 개요</span><span class="sxs-lookup"><span data-stu-id="b0602-134">Overview of attack surface reduction</span></span>](/defender-endpoint/overview-attack-surface-reduction)
<span data-ttu-id="b0602-135">끝점 검색 및 응답</span><span class="sxs-lookup"><span data-stu-id="b0602-135">Endpoint Detection and Response</span></span> | <span data-ttu-id="b0602-136">끝점 감지 및 응답 기능은 거의 실시간으로 실행 가능한 고급 공격 감지 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b0602-136">Endpoint detection and response capabilities provide advanced attack detections that are near real-time and actionable.</span></span> | [<span data-ttu-id="b0602-137">끝점 검색 및 응답 기능 개요</span><span class="sxs-lookup"><span data-stu-id="b0602-137">Overview of endpoint detection and response capabilities</span></span>](/defender-endpoint/overview-endpoint-detection-response)
<span data-ttu-id="b0602-138">동작 차단 및 포함</span><span class="sxs-lookup"><span data-stu-id="b0602-138">Behavioral Blocking and Containment</span></span> | <span data-ttu-id="b0602-139">동작 차단 및 포함 기능은 위협이 실행을 시작한 경우에도 동작 및 처리 트리에 따라 위협을 식별하고 중지하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0602-139">Behavioral blocking and containment capabilities can help identify and stop threats, based on their behaviors and process trees even when the threat has started execution.</span></span> | [<span data-ttu-id="b0602-140">동작 차단 및 제약</span><span class="sxs-lookup"><span data-stu-id="b0602-140">Behavioral blocking and containment</span></span>](/defender-endpoint/behavioral-blocking-containment)
<span data-ttu-id="b0602-141">자동화된 조사 및 대응</span><span class="sxs-lookup"><span data-stu-id="b0602-141">Automated Investigation and Response</span></span> | <span data-ttu-id="b0602-142">자동화된 조사는 보안 분석가가 사용하는 프로세스에 따라 다양한 검사 알고리즘을 사용하며 경고를 검사하고 위반을 해결하기 위해 즉각적인 조치를 취하도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b0602-142">Automated investigation uses various inspection algorithms based on processes that are used by security analysts and designed to examine alerts and take immediate action to resolve breaches.</span></span> | [<span data-ttu-id="b0602-143">자동화된 조사를 사용하여 위협 조사 및 수정</span><span class="sxs-lookup"><span data-stu-id="b0602-143">Use automated investigations to investigate and remediate threats</span></span>](/defender-endpoint/automated-investigations)
<span data-ttu-id="b0602-144">지능형 헌팅</span><span class="sxs-lookup"><span data-stu-id="b0602-144">Advanced Hunting</span></span> | <span data-ttu-id="b0602-145">고급 헌팅은 네트워크에서 이벤트를 사전 검사하여 위협 표시기 및 엔터티를 찾을 수 있도록 최대 30일의 원시 데이터를 탐색할 수 있는 쿼리 기반 위협 헌팅 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="b0602-145">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data so that you can proactively inspect events in your network to locate threat indicators and entities.</span></span> | [<span data-ttu-id="b0602-146">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="b0602-146">Overview of advanced hunting</span></span>](/defender-endpoint/advanced-hunting-overview)
<span data-ttu-id="b0602-147">위협 분석</span><span class="sxs-lookup"><span data-stu-id="b0602-147">Threat Analytics</span></span> | <span data-ttu-id="b0602-148">위협 분석은 가장 관련성이 높은 위협을 다루는 전문 Microsoft 보안 연구원의 보고서 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="b0602-148">Threat analytics is a set of reports from expert Microsoft security researchers covering the most relevant threats.</span></span> | [<span data-ttu-id="b0602-149">새로운 위협 추적 및 대응</span><span class="sxs-lookup"><span data-stu-id="b0602-149">Track and respond to emerging threats</span></span>](/defender-endpoint/threat-analytics)


<span data-ttu-id="b0602-150">끝점용 Microsoft Defender에 포함된 기능에 대한 자세한 내용은 [Endpoint용 Microsoft Defender 를 참조하세요.](/defender-endpoint/microsoft-defender-endpoint)</span><span class="sxs-lookup"><span data-stu-id="b0602-150">For more detailed information about the capabilities included with Microsoft Defender for Endpoint, see [What is Microsoft Defender for Endpoint](/defender-endpoint/microsoft-defender-endpoint).</span></span>

## <a name="siem-integration"></a><span data-ttu-id="b0602-151">SIEM 통합</span><span class="sxs-lookup"><span data-stu-id="b0602-151">SIEM integration</span></span>

<span data-ttu-id="b0602-152">끝점용 Microsoft Defender를 Azure Sentinel과 통합하여 조직 전체의 보안 이벤트를 보다 포괄적으로 분석하고 효과적이고 즉각적인 응답을 위해 플레이북을 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0602-152">You can integrate Microsoft Defender for Endpoint with Azure Sentinel to more comprehensively analyze security events across your organization and build playbooks for effective and immediate response.</span></span> 

<span data-ttu-id="b0602-153">끝점용 Microsoft Defender를 다른 SIEM(보안 정보 및 이벤트 관리) 솔루션에 통합할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0602-153">Microsoft Defender for Endpoint can also be integrated into other Security Information and Event Management (SIEM) solutions.</span></span> <span data-ttu-id="b0602-154">자세한 내용은 [Enable SIEM integration in Microsoft Defender for Endpoint을 참조하세요.](/defender-endpoint/enable-siem-integration)</span><span class="sxs-lookup"><span data-stu-id="b0602-154">For more information, see [Enable SIEM integration in Microsoft Defender for Endpoint](/defender-endpoint/enable-siem-integration).</span></span>


## <a name="next-steps"></a><span data-ttu-id="b0602-155">다음 단계</span><span class="sxs-lookup"><span data-stu-id="b0602-155">Next steps</span></span>
[<span data-ttu-id="b0602-156">평가 사용</span><span class="sxs-lookup"><span data-stu-id="b0602-156">Enable the evaluation</span></span>](eval-defender-endpoint-enable-eval.md)

<span data-ttu-id="b0602-157">[끝점용 Microsoft Defender 평가 개요로 돌아가기](eval-defender-endpoint-overview.md)</span><span class="sxs-lookup"><span data-stu-id="b0602-157">Return to the overview for [Evaluate Microsoft Defender for Endpoint](eval-defender-endpoint-overview.md)</span></span>

<span data-ttu-id="b0602-158">평가 및 파일럿 테스트 [개요로 Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="b0602-158">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>