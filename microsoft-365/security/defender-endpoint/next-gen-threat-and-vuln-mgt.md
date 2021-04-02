---
title: 위협 및 취약점 관리
description: 이 새로운 기능은 게임이 변화하는 위험 기반 접근 방식을 사용하여 끝점 취약성 및 잘못 구성을 검색, 우선 순위 지정 및 수정합니다.
keywords: 위협 & 관리, 위협 및 취약성 관리, MDATP TVM, MDATP-TVM, 취약점 관리, 취약점 평가, 위협 및 취약점 검사, 보안 구성 평가, Microsoft Defender atp, Microsoft Defender atp, 끝점 취약성, 차세대
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: overview
ms.technology: mde
ms.openlocfilehash: 0c3c5ebbcd4483cae159fe9b46a6f4c376443be3
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499063"
---
# <a name="threat-and-vulnerability-management"></a><span data-ttu-id="095c6-104">위협 및 취약점 관리</span><span class="sxs-lookup"><span data-stu-id="095c6-104">Threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="095c6-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="095c6-105">**Applies to:**</span></span>
- [<span data-ttu-id="095c6-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="095c6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="095c6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="095c6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="095c6-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="095c6-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="095c6-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="095c6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="095c6-110">끝점 약점을 효과적으로 식별, 평가 및 수정하는 것은 건전한 보안 프로그램을 실행하고 조직의 위험을 줄이는 데 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="095c6-110">Effectively identifying, assessing, and remediating endpoint weaknesses is pivotal in running a healthy security program and reducing organizational risk.</span></span> <span data-ttu-id="095c6-111">위협과 취약점 관리는 조직 노출을 줄이고, 엔드포인트 노출 영역을 강화하며, 조직 복원력을 높이는 인프라 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="095c6-111">Threat and vulnerability management serves as an infrastructure for reducing organizational exposure, hardening endpoint surface area, and increasing organizational resilience.</span></span>

<span data-ttu-id="095c6-112">에이전트 또는 주기적인 검사 없이 센서를 사용하여 실시간으로 취약성 및 잘못 구성을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="095c6-112">Discover vulnerabilities and misconfigurations in real time with sensors, and without the need of agents or periodic scans.</span></span> <span data-ttu-id="095c6-113">위협 환경, 조직의 탐지, 취약한 장치에 대한 중요한 정보 및 비즈니스 컨텍스트에 따라 취약성의 우선 순위를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="095c6-113">It prioritizes vulnerabilities based on the threat landscape, detections in your organization, sensitive information on vulnerable devices, and business context.</span></span>

<span data-ttu-id="095c6-114">위협 및 취약성 관리에 대한 간략한 개요는 이 비디오를 시청하세요.</span><span class="sxs-lookup"><span data-stu-id="095c6-114">Watch this video for a quick overview of threat and vulnerability management.</span></span>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4mLsn]

## <a name="bridging-the-workflow-gaps"></a><span data-ttu-id="095c6-115">워크플로 간격 브리그링</span><span class="sxs-lookup"><span data-stu-id="095c6-115">Bridging the workflow gaps</span></span>

<span data-ttu-id="095c6-116">위협 및 취약성 관리는 기본 제공, 실시간 및 클라우드 기반입니다.</span><span class="sxs-lookup"><span data-stu-id="095c6-116">Threat and vulnerability management is built in, real time, and cloud powered.</span></span> <span data-ttu-id="095c6-117">Microsoft 끝점 보안 스택, Microsoft 지능형 보안 그래프 및 응용 프로그램 분석 기술 자료와 완전히 통합되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="095c6-117">It's fully integrated with Microsoft endpoint security stack, the Microsoft Intelligent Security Graph, and the application analytics knowledge base.</span></span>  

<span data-ttu-id="095c6-118">취약점 관리는 재구성 프로세스 중에 보안 관리와 IT 관리 간의 격차를 해소하기 위한 업계 첫 번째 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="095c6-118">Vulnerability management is the first solution in the industry to bridge the gap between security administration and IT administration during remediation process.</span></span> <span data-ttu-id="095c6-119">Microsoft Intune 및 Microsoft Endpoint Configuration Manager와 통합하여 보안 작업 또는 티켓을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="095c6-119">Create a security task or ticket by integrating with Microsoft Intune and Microsoft Endpoint Configuration Manager.</span></span>

### <a name="real-time-discovery"></a><span data-ttu-id="095c6-120">실시간 검색</span><span class="sxs-lookup"><span data-stu-id="095c6-120">Real-time discovery</span></span>

<span data-ttu-id="095c6-121">끝점 취약성 및 잘못된 구성을 발견하기 위해 위협 및 취약점 관리는 엔드포인트 센서에 대해 에이전트 없는 기본 제공 Defender를 사용하여 번거로운 네트워크 검사 및 IT 오버헤드를 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="095c6-121">To discover endpoint vulnerabilities and misconfiguration, threat and vulnerability management uses the same agentless built-in Defender for Endpoint sensors to reduce cumbersome network scans and IT overhead.</span></span>

<span data-ttu-id="095c6-122">또한 다음을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="095c6-122">It also provides:</span></span>

- <span data-ttu-id="095c6-123">**실시간 장치 인벤토리** - Endpoint용 Defender에 온보딩된 장치는 취약점 및 보안 구성 데이터를 대시보드에 자동으로 보고하고 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="095c6-123">**Real-time device inventory** - Devices onboarded to Defender for Endpoint automatically report and push vulnerability and security configuration data to the dashboard.</span></span>
- <span data-ttu-id="095c6-124">**소프트웨어 및** 취약점에 대한 가시성 - 조직의 소프트웨어 인벤토리에 대한 광학, 설치, 제거 및 패치와 같은 소프트웨어 변경</span><span class="sxs-lookup"><span data-stu-id="095c6-124">**Visibility into software and vulnerabilities** - Optics into the organization's software inventory, and software changes like installations, uninstalls, and patches.</span></span> <span data-ttu-id="095c6-125">새로 발견된 취약성은 제1 및 제3자 응용 프로그램에 대한 실행 가능한 완화 권장 사항으로 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="095c6-125">Newly discovered vulnerabilities are reported with actionable mitigation recommendations for 1st and 3rd party applications.</span></span>
- <span data-ttu-id="095c6-126">**응용 프로그램 런타임 컨텍스트** - 더 나은 우선 순위 지정 및 의사 결정에 대한 응용 프로그램 사용 패턴 표시</span><span class="sxs-lookup"><span data-stu-id="095c6-126">**Application runtime context** - Visibility on application usage patterns for better prioritization and decision-making.</span></span>
- <span data-ttu-id="095c6-127">**구성 상태** - 조직 보안 구성 또는 잘못 구성을 가시성합니다.</span><span class="sxs-lookup"><span data-stu-id="095c6-127">**Configuration posture** - Visibility into organizational security configuration or misconfigurations.</span></span> <span data-ttu-id="095c6-128">실행 가능한 보안 권장 사항을 사용하여 대시보드에 문제가 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="095c6-128">Issues are reported in the dashboard with actionable security recommendations.</span></span>

### <a name="intelligence-driven-prioritization"></a><span data-ttu-id="095c6-129">인텔리전스 기반 우선 순위 지정</span><span class="sxs-lookup"><span data-stu-id="095c6-129">Intelligence-driven prioritization</span></span>

<span data-ttu-id="095c6-130">위협 및 취약성 관리는 고객이 조직에 가장 긴급하고 가장 높은 위험을 내포하는 약점에 우선 순위를 지정하고 초점을 맞추는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="095c6-130">Threat and vulnerability management helps customers prioritize and focus on the weaknesses that pose the most urgent and the highest risk to the organization.</span></span> <span data-ttu-id="095c6-131">보안 권장 사항을 동적 위협 및 비즈니스 컨텍스트와 함께 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="095c6-131">It fuses security recommendations with dynamic threat and business context:</span></span>

- <span data-ttu-id="095c6-132">**새로운 공격을** 와일드에 노출 - 보안 권장 사항의 우선 순위를 동적으로 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="095c6-132">**Exposing emerging attacks in the wild** - Dynamically aligns the prioritization of security recommendations.</span></span> <span data-ttu-id="095c6-133">위협 및 취약성 관리는 현재 가장 높은 위험을 야기하는 떠오르는 위협에서 악용되고 있는 취약성에 초점을 맞추고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="095c6-133">Threat and vulnerability management focuses on vulnerabilities currently being exploited in the wild and emerging threats that pose the highest risk.</span></span>
- <span data-ttu-id="095c6-134">**활성 위반을** 파악 - 위협 및 취약성 관리와 EDR 인사이트를 상관하여 조직 내에서 활성 위반에 악용되는 취약성의 우선 순위를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="095c6-134">**Pinpointing active breaches** - Correlates threat and vulnerability management and EDR insights to prioritize vulnerabilities being exploited in an active breach within the organization.</span></span>
- <span data-ttu-id="095c6-135">**고가치 자산** 보호 - 업무상 중요한 응용 프로그램, 기밀 데이터 또는 고가치 사용자로 노출된 장치를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="095c6-135">**Protecting high-value assets** - Identify the exposed devices with business-critical applications, confidential data, or high-value users.</span></span>

### <a name="seamless-remediation"></a><span data-ttu-id="095c6-136">원활한 수정</span><span class="sxs-lookup"><span data-stu-id="095c6-136">Seamless remediation</span></span>

<span data-ttu-id="095c6-137">위협 및 취약성 관리를 통해 보안 관리자와 IT 관리자는 원활하게 공동 작업을 통해 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="095c6-137">Threat and vulnerability management allows security administrators and IT administrators to collaborate seamlessly to remediate issues.</span></span>

- <span data-ttu-id="095c6-138">**IT로 전송된** 수정 요청 - 특정 보안 권장으로부터 Microsoft Intune에서 수정 작업을 만드시다.</span><span class="sxs-lookup"><span data-stu-id="095c6-138">**Remediation requests sent to IT** - Create a remediation task in Microsoft Intune from a specific security recommendation.</span></span> <span data-ttu-id="095c6-139">이 기능을 다른 IT 보안 관리 플랫폼으로 확장할 계획입니다.</span><span class="sxs-lookup"><span data-stu-id="095c6-139">We plan to expand this capability to other IT security management platforms.</span></span>
- <span data-ttu-id="095c6-140">**대체 완화** - 소프트웨어 취약성과 관련된 위험을 줄일 수 있는 구성 변경과 같은 추가 완화에 대한 정보를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="095c6-140">**Alternate mitigations** - Gain insights on additional mitigations, such as configuration changes that can reduce risk associated with software vulnerabilities.</span></span>
- <span data-ttu-id="095c6-141">**실시간** 재구성 상태 - 조직 전체의 재구성 활동의 상태 및 진행률을 실시간으로 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="095c6-141">**Real-time remediation status** - Real-time monitoring of the status and progress of remediation activities across the organization.</span></span>

## <a name="threat-and-vulnerability-management-walk-through"></a><span data-ttu-id="095c6-142">위협 및 취약성 관리 Walk-through</span><span class="sxs-lookup"><span data-stu-id="095c6-142">Threat and vulnerability management walk-through</span></span>

<span data-ttu-id="095c6-143">포괄적인 위협 및 취약성 관리를 위한 이 비디오를 시청합니다.</span><span class="sxs-lookup"><span data-stu-id="095c6-143">Watch this video for a comprehensive walk-through of threat and vulnerability management.</span></span>

>[!VIDEO https://aka.ms/MDATP-TVM-Interactive-Guide]

## <a name="navigation-pane"></a><span data-ttu-id="095c6-144">탐색 창 </span><span class="sxs-lookup"><span data-stu-id="095c6-144">Navigation pane</span></span>

<span data-ttu-id="095c6-145">영역</span><span class="sxs-lookup"><span data-stu-id="095c6-145">Area</span></span> | <span data-ttu-id="095c6-146">설명</span><span class="sxs-lookup"><span data-stu-id="095c6-146">Description</span></span>
:---|:---
<span data-ttu-id="095c6-147">**Dashboard**</span><span class="sxs-lookup"><span data-stu-id="095c6-147">**Dashboard**</span></span>   | <span data-ttu-id="095c6-148">조직 노출 점수, 장치에 대한 Microsoft 보안 점수, 장치 노출 분포, 최상위 보안 권장 사항, 주요 취약한 소프트웨어, 최상위 수정 활동 및 노출된 상위 장치 데이터에 대한 높은 수준의 보기를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="095c6-148">Get a high-level view of the organization exposure score, Microsoft Secure Score for Devices, device exposure distribution, top security recommendations, top vulnerable software, top remediation activities, and top exposed device data.</span></span>
[<span data-ttu-id="095c6-149">**보안 권장 사항**</span><span class="sxs-lookup"><span data-stu-id="095c6-149">**Security recommendations**</span></span>](tvm-security-recommendation.md) | <span data-ttu-id="095c6-150">보안 권장 사항 및 관련 위협 정보 목록을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="095c6-150">See the list of security recommendations and related threat information.</span></span> <span data-ttu-id="095c6-151">목록에서 항목을 선택하면 취약성 세부 정보, 소프트웨어 페이지를 여는 링크, 수정 및 예외 옵션이 있는 플라이아웃 패널이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="095c6-151">When you select an item from the list, a flyout panel opens with vulnerability details, a link to open the software page, and remediation and exception options.</span></span> <span data-ttu-id="095c6-152">디바이스가 Azure Active Directory를 통해 가입되어 있으며 끝점용 Defender에서 Intune 연결을 사용하도록 설정한 경우 Intune에서 티켓을 열 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="095c6-152">You can also open a ticket in Intune if your devices are joined through Azure Active Directory and you've enabled your Intune connections in Defender for Endpoint.</span></span>
[<span data-ttu-id="095c6-153">**수정**</span><span class="sxs-lookup"><span data-stu-id="095c6-153">**Remediation**</span></span>](tvm-remediation.md) | <span data-ttu-id="095c6-154">만든 재구성 활동 및 권장 예외를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="095c6-154">See remediation activities you've created and recommendation exceptions.</span></span>
[<span data-ttu-id="095c6-155">**소프트웨어 인벤토리**</span><span class="sxs-lookup"><span data-stu-id="095c6-155">**Software inventory**</span></span>](tvm-software-inventory.md) | <span data-ttu-id="095c6-156">약점 및 위협 정보와 함께 조직의 취약한 소프트웨어 목록을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="095c6-156">See the list of vulnerable software in your organization, along with weakness and threat information.</span></span>
[<span data-ttu-id="095c6-157">**약점**</span><span class="sxs-lookup"><span data-stu-id="095c6-157">**Weaknesses**</span></span>](tvm-weaknesses.md) | <span data-ttu-id="095c6-158">조직의 일반적인 취약성 및 노출(CV) 목록을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="095c6-158">See the list of common vulnerabilities and exposures (CVEs) in your organization.</span></span>
[<span data-ttu-id="095c6-159">**이벤트 타임라인**</span><span class="sxs-lookup"><span data-stu-id="095c6-159">**Event timeline**</span></span>](threat-and-vuln-mgt-event-timeline.md) | <span data-ttu-id="095c6-160">조직의 위험에 영향을 줄 수 있는 이벤트를 하세요.</span><span class="sxs-lookup"><span data-stu-id="095c6-160">View events that may impact your organization's risk.</span></span>

## <a name="apis"></a><span data-ttu-id="095c6-161">API</span><span class="sxs-lookup"><span data-stu-id="095c6-161">APIs</span></span>

<span data-ttu-id="095c6-162">위협 및 취약성 관리 관련 API 호출을 실행하여 취약성 관리 워크플로를 자동화합니다.</span><span class="sxs-lookup"><span data-stu-id="095c6-162">Run threat and vulnerability management-related API calls to automate vulnerability management workflows.</span></span> <span data-ttu-id="095c6-163">자세한 내용은 [이 Microsoft 기술 커뮤니티 블로그 게시물 을 참조하세요.](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/threat-amp-vulnerability-management-apis-are-now-generally/ba-p/1304615)</span><span class="sxs-lookup"><span data-stu-id="095c6-163">Learn more from this [Microsoft Tech Community blog post](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/threat-amp-vulnerability-management-apis-are-now-generally/ba-p/1304615).</span></span>

<span data-ttu-id="095c6-164">관련 API에 대한 자세한 내용은 다음 문서를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="095c6-164">See the following articles for related APIs:</span></span>

- <span data-ttu-id="095c6-165">[지원되는 엔드포인트용 Microsoft Defender API](exposed-apis-list.md) </span><span class="sxs-lookup"><span data-stu-id="095c6-165">[Supported Microsoft Defender for Endpoint APIs](exposed-apis-list.md)</span></span>
- [<span data-ttu-id="095c6-166">컴퓨터 API</span><span class="sxs-lookup"><span data-stu-id="095c6-166">Machine APIs</span></span>](machine.md)
- [<span data-ttu-id="095c6-167">권장 API</span><span class="sxs-lookup"><span data-stu-id="095c6-167">Recommendation APIs</span></span>](vulnerability.md)
- [<span data-ttu-id="095c6-168">점수 API</span><span class="sxs-lookup"><span data-stu-id="095c6-168">Score APIs</span></span>](score.md)
- [<span data-ttu-id="095c6-169">소프트웨어 API</span><span class="sxs-lookup"><span data-stu-id="095c6-169">Software APIs</span></span>](software.md)
- [<span data-ttu-id="095c6-170">취약성 API</span><span class="sxs-lookup"><span data-stu-id="095c6-170">Vulnerability APIs</span></span>](vulnerability.md)
- [<span data-ttu-id="095c6-171">컴퓨터 및 소프트웨어별 취약성 목록</span><span class="sxs-lookup"><span data-stu-id="095c6-171">List vulnerabilities by machine and software</span></span>](get-all-vulnerabilities-by-machines.md)

## <a name="see-also"></a><span data-ttu-id="095c6-172">참고 항목</span><span class="sxs-lookup"><span data-stu-id="095c6-172">See also</span></span>

- [<span data-ttu-id="095c6-173">지원되는 운영 체제 및 플랫폼</span><span class="sxs-lookup"><span data-stu-id="095c6-173">Supported operating systems and platforms</span></span>](tvm-supported-os.md)
- [<span data-ttu-id="095c6-174">위협 및 취약성 관리 대시보드</span><span class="sxs-lookup"><span data-stu-id="095c6-174">Threat and vulnerability management dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="095c6-175">블로그: Microsoft의 위협 & 취약성 관리는 이제 수천 명의 고객이 실시간으로 취약성을 검색, 우선 순위 지정 및 수정하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="095c6-175">BLOG: Microsoft's Threat & Vulnerability Management now helps thousands of customers to discover, prioritize, and remediate vulnerabilities in real time</span></span>](https://www.microsoft.com/security/blog/2019/07/02/microsofts-threat-vulnerability-management-now-helps-thousands-of-customers-to-discover-prioritize-and-remediate-vulnerabilities-in-real-time/)
