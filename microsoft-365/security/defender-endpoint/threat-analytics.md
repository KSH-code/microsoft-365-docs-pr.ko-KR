---
title: Endpoint 위협 분석을 위한 Microsoft Defender를 사용하여 새로운 위협 추적 및 대응
ms.reviewer: ''
description: 새로운 위협 및 공격 기술 및 이를 중지하는 방법을 이해합니다. 조직에 미치는 영향을 평가하고 조직 탄력성 평가
keywords: 위협 분석, 위험 평가, OS 완화, 마이크로코드 완화, 완화 상태
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 63303f9eacd25a8de1c7154ac66c73578bfd495a
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924458"
---
# <a name="track-and-respond-to-emerging-threats-through-threat-analytics"></a><span data-ttu-id="5481c-105">위협 분석을 통해 새로운 위협 추적 및 대응</span><span class="sxs-lookup"><span data-stu-id="5481c-105">Track and respond to emerging threats through threat analytics</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5481c-106">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="5481c-106">**Applies to:**</span></span>
- [<span data-ttu-id="5481c-107">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="5481c-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="5481c-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5481c-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="5481c-109">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="5481c-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5481c-110">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="5481c-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="5481c-111">더욱 정교한 공격자 및 새로운 위협이 자주 발생하고 자주 등장하는 경우 빠르게 다음을 할 수 있는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="5481c-111">With more sophisticated adversaries and new threats emerging frequently and prevalently, it's critical to be able to quickly:</span></span>

- <span data-ttu-id="5481c-112">새로운 위협의 영향 평가</span><span class="sxs-lookup"><span data-stu-id="5481c-112">Assess the impact of new threats</span></span>
- <span data-ttu-id="5481c-113">위협에 대한 또는 노출에 대한 탄력성 검토</span><span class="sxs-lookup"><span data-stu-id="5481c-113">Review your resilience against or exposure to the threats</span></span>
- <span data-ttu-id="5481c-114">위협을 중지하거나 포함하기 위해 수행할 수 있는 작업 식별</span><span class="sxs-lookup"><span data-stu-id="5481c-114">Identify the actions you can take to stop or contain the threats</span></span>

<span data-ttu-id="5481c-115">위협 분석은 다음을 포함하여 가장 관련성이 높은 위협을 다루는 전문 Microsoft 보안 연구원의 보고서 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="5481c-115">Threat analytics is a set of reports from expert Microsoft security researchers covering the most relevant threats, including:</span></span>

- <span data-ttu-id="5481c-116">활성 위협 요소 및 캠페인</span><span class="sxs-lookup"><span data-stu-id="5481c-116">Active threat actors and their campaigns</span></span>
- <span data-ttu-id="5481c-117">인기 있는 새로운 공격 기술</span><span class="sxs-lookup"><span data-stu-id="5481c-117">Popular and new attack techniques</span></span>
- <span data-ttu-id="5481c-118">중요한 취약성</span><span class="sxs-lookup"><span data-stu-id="5481c-118">Critical vulnerabilities</span></span>
- <span data-ttu-id="5481c-119">일반적인 공격 표면</span><span class="sxs-lookup"><span data-stu-id="5481c-119">Common attack surfaces</span></span>
- <span data-ttu-id="5481c-120">맬웨어가 보인 경우</span><span class="sxs-lookup"><span data-stu-id="5481c-120">Prevalent malware</span></span>

<span data-ttu-id="5481c-121">각 보고서는 위협에 대한 자세한 분석과 위협을 방어하는 방법에 대한 광범위한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5481c-121">Each report provides a detailed analysis of a threat and extensive guidance on how to defend against that threat.</span></span> <span data-ttu-id="5481c-122">또한 네트워크의 데이터를 통합하여 위협이 활성 상태인지 여부와 적용 가능한 보호가 설정되어 있는지 여부를 나타 내보입니다.</span><span class="sxs-lookup"><span data-stu-id="5481c-122">It also incorporates data from your network, indicating whether the threat is active and if you have applicable protections in place.</span></span>

<span data-ttu-id="5481c-123">이 짧은 비디오를 시청하여 위협 분석을 통해 최신 위협을 추적하고 중지하는 방법에 대해 자세히 알아보십시오.</span><span class="sxs-lookup"><span data-stu-id="5481c-123">Watch this short video to learn more about how threat analytics can help you track the latest threats and stop them.</span></span>
<p></p>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bw1f]

## <a name="view-the-threat-analytics-dashboard"></a><span data-ttu-id="5481c-124">위협 분석 대시보드 보기</span><span class="sxs-lookup"><span data-stu-id="5481c-124">View the threat analytics dashboard</span></span>

<span data-ttu-id="5481c-125">위협 분석 대시보드는 조직과 가장 관련이 있는 보고서로 이동하기 위한 훌륭한 지점입니다.</span><span class="sxs-lookup"><span data-stu-id="5481c-125">The threat analytics dashboard is a great jump off point for getting to the reports that are most relevant to your organization.</span></span> <span data-ttu-id="5481c-126">다음 섹션에서는 위협을 요약하여 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5481c-126">It summarizes the threats in the following sections:</span></span>

- <span data-ttu-id="5481c-127">**최신 위협**- 최근 게시된 위협 보고서와 활성 및 해결된 경고가 있는 장치 수를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="5481c-127">**Latest threats**—lists the most recently published threat reports, along with the number of devices with active and resolved alerts.</span></span>
- <span data-ttu-id="5481c-128">**영향력이 큰 위협**- 조직에 가장 큰 영향을 미치는 위협을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="5481c-128">**High-impact threats**—lists the threats that have had the highest impact to the organization.</span></span> <span data-ttu-id="5481c-129">이 섹션에서는 활성 경고가 있는 장치 수를 통해 위협의 순위를 매기고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5481c-129">This section ranks threats by the number of devices that have active alerts.</span></span>
- <span data-ttu-id="5481c-130">**위협 요약**- 활성 및 해결된 경고와 함께 위협 수를 표시하여 추적된 위협의 전반적인 영향을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="5481c-130">**Threat summary**—shows the overall impact of tracked threats by showing the number of threats with active and resolved alerts.</span></span>

<span data-ttu-id="5481c-131">대시보드에서 위협을 선택하여 해당 위협에 대한 보고서를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5481c-131">Select a threat from the dashboard to view the report for that threat.</span></span>

![위협 분석 대시보드의 이미지](images/ta_dashboard.png)

## <a name="view-a-threat-analytics-report"></a><span data-ttu-id="5481c-133">위협 분석 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="5481c-133">View a threat analytics report</span></span>

<span data-ttu-id="5481c-134">각 위협 분석 보고서는 **개요,** 분석가 보고서 및 완화의 세 섹션으로 정보를 **제공합니다.** </span><span class="sxs-lookup"><span data-stu-id="5481c-134">Each threat analytics report provides information in three sections: **Overview**, **Analyst report**, and **Mitigations**.</span></span>

### <a name="overview-quickly-understand-the-threat-assess-its-impact-and-review-defenses"></a><span data-ttu-id="5481c-135">개요: 위협을 신속하게 이해하고, 영향을 평가하고, 방어를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="5481c-135">Overview: Quickly understand the threat, assess its impact, and review defenses</span></span>

<span data-ttu-id="5481c-136">개요 **섹션에서는** 자세한 분석 보고서의 미리 보기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5481c-136">The **Overview** section provides a preview of the detailed analyst report.</span></span> <span data-ttu-id="5481c-137">또한 잘못 구성 및 패치되지 않은 장치를 통해 조직에 위협이 미치는 영향과 노출을 강조하는 차트도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5481c-137">It also provides charts that highlight the impact of the threat to your organization and your exposure through misconfigured and unpatched devices.</span></span>

<span data-ttu-id="5481c-138">![위협 분석 보고서 개요 섹션의 개요 ](images/ta-overview.png)
 _섹션 이미지_</span><span class="sxs-lookup"><span data-stu-id="5481c-138">![Image of the overview section of a threat analytics report](images/ta-overview.png)
_Overview section of a threat analytics report_</span></span>

#### <a name="assess-the-impact-to-your-organization"></a><span data-ttu-id="5481c-139">조직에 미치는 영향 평가</span><span class="sxs-lookup"><span data-stu-id="5481c-139">Assess the impact to your organization</span></span>
<span data-ttu-id="5481c-140">각 보고서에는 위협의 조직적 영향에 대한 정보를 제공하도록 디자인된 차트가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5481c-140">Each report includes charts designed to provide information about the organizational impact of a threat:</span></span>
- <span data-ttu-id="5481c-141">**경고가 있는 장치**- 위협의 영향을 을 수 있는 고유한 장치의 현재 수를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="5481c-141">**Devices with alerts**—shows the current number of distinct devices that have been impacted by the threat.</span></span> <span data-ttu-id="5481c-142">해당 위협과 연결된  경고가 하나 이상 있는 경우 장치가 활성으로 분류되고 장치의 위협과 관련된 모든 경고가 해결된 경우 해결됩니다.  </span><span class="sxs-lookup"><span data-stu-id="5481c-142">A device is categorized as **Active** if there is at least one alert associated with that threat and **Resolved** if *all* alerts associated with the threat on the device have been resolved.</span></span>
- <span data-ttu-id="5481c-143">**시간이 지날 때 경고가** 있는 디바이스는 시간이 지날 때 **활성** 및 해결된 경고가 있는 고유한 장치 **수를** 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="5481c-143">**Devices with alerts over time**—shows the number of distinct devices with **Active** and **Resolved** alerts over time.</span></span> <span data-ttu-id="5481c-144">해결된 경고 수는 조직이 위협과 관련된 경고에 얼마나 빠르게 응답하는지 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5481c-144">The number of resolved alerts indicates how quickly your organization responds to alerts associated with a threat.</span></span> <span data-ttu-id="5481c-145">이상적으로는 며칠 내에 해결된 경고가 차트에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5481c-145">Ideally, the chart should be showing alerts resolved within a few days.</span></span>

#### <a name="review-security-resilience-and-posture"></a><span data-ttu-id="5481c-146">보안 탄력성 및 자세 검토</span><span class="sxs-lookup"><span data-stu-id="5481c-146">Review security resilience and posture</span></span>
<span data-ttu-id="5481c-147">각 보고서에는 조직이 주어진 위협에 대해 얼마나 탄력적인지 간략하게 설명하는 차트가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5481c-147">Each report includes charts that provide an overview of how resilient your organization is against a given threat:</span></span>
- <span data-ttu-id="5481c-148">**보안 구성 상태**- 위협을 완화하는 데 도움이 될 수 있는 권장 보안 설정을 적용한 장치 수를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="5481c-148">**Security configuration status**—shows the number of devices that have applied the recommended security settings that can help mitigate the threat.</span></span> <span data-ttu-id="5481c-149">추적된 **모든** 설정을 적용한 장치는 보안으로 간주됩니다. </span><span class="sxs-lookup"><span data-stu-id="5481c-149">Devices are considered **Secure** if they have applied _all_ the tracked settings.</span></span>
- <span data-ttu-id="5481c-150">**취약점 패치 상태**- 위협에 악용되는 취약점을 해결하는 보안 업데이트 또는 패치를 적용한 장치 수를 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="5481c-150">**Vulnerability patching status**—shows the number of devices that have applied security updates or patches that address vulnerabilities exploited by the threat.</span></span>

### <a name="analyst-report-get-expert-insight-from-microsoft-security-researchers"></a><span data-ttu-id="5481c-151">분석가 보고서: Microsoft 보안 연구원으로부터 전문가 인사이트 얻기</span><span class="sxs-lookup"><span data-stu-id="5481c-151">Analyst report: Get expert insight from Microsoft security researchers</span></span>
<span data-ttu-id="5481c-152">분석가 **보고서 섹션으로 이동하여** 자세한 전문가 쓰기를 읽어 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="5481c-152">Go to the **Analyst report** section to read through the detailed expert write-up.</span></span> <span data-ttu-id="5481c-153">대부분의 보고서는 MITRE ATT&CK 프레임워크에 매핑된 전략 및 기술, 권장 사항의 전체 목록 및 강력한 위협 헌팅 지침을 포함하여 공격 체인에 대한 자세한 [설명을](advanced-hunting-overview.md) 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5481c-153">Most reports provide detailed descriptions of attack chains, including tactics and techniques mapped to the MITRE ATT&CK framework, exhaustive lists of recommendations, and powerful [threat hunting](advanced-hunting-overview.md) guidance.</span></span>

[<span data-ttu-id="5481c-154">분석 보고서에 대해 자세히 알아보시다</span><span class="sxs-lookup"><span data-stu-id="5481c-154">Learn more about the analyst report</span></span>](threat-analytics-analyst-reports.md)

### <a name="mitigations-review-list-of-mitigations-and-the-status-of-your-devices"></a><span data-ttu-id="5481c-155">완화: 완화 목록 및 장치 상태 검토</span><span class="sxs-lookup"><span data-stu-id="5481c-155">Mitigations: Review list of mitigations and the status of your devices</span></span>
<span data-ttu-id="5481c-156">완화 **섹션에서** 위협에 대한 조직 탄력을 강화하는 데 도움이 될 수 있는 실행 가능한 특정 권장 사항 목록을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="5481c-156">In the **Mitigations** section, review the list of specific actionable recommendations that can help you increase your organizational resilience against the threat.</span></span> <span data-ttu-id="5481c-157">추적된 완화 목록은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5481c-157">The list of tracked mitigations includes:</span></span>

- <span data-ttu-id="5481c-158">**보안 업데이트**- 취약점에 대한 보안 업데이트 또는 패치 배포</span><span class="sxs-lookup"><span data-stu-id="5481c-158">**Security updates**—deployment of security updates or patches for vulnerabilities</span></span>
- <span data-ttu-id="5481c-159">**Microsoft Defender 바이러스 백신 설정**</span><span class="sxs-lookup"><span data-stu-id="5481c-159">**Microsoft Defender Antivirus settings**</span></span>
  - <span data-ttu-id="5481c-160">보안 인텔리전스 버전</span><span class="sxs-lookup"><span data-stu-id="5481c-160">Security intelligence version</span></span>
  - <span data-ttu-id="5481c-161">클라우드 제공 보호</span><span class="sxs-lookup"><span data-stu-id="5481c-161">Cloud-delivered protection</span></span>  
  - <span data-ttu-id="5481c-162">잠재적으로 원치 않는 응용 프로그램(PUA) 보호</span><span class="sxs-lookup"><span data-stu-id="5481c-162">Potentially unwanted application (PUA) protection</span></span>
  - <span data-ttu-id="5481c-163">실시간 보호</span><span class="sxs-lookup"><span data-stu-id="5481c-163">Real-time protection</span></span>
 
<span data-ttu-id="5481c-164">이 섹션의 완화 정보는 보고서의 [](next-gen-threat-and-vuln-mgt.md)다양한 링크에 위협 및 취약성 관리 자세한 드릴다운 정보도 제공하는 위협 및 취약성 관리 데이터를 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="5481c-164">Mitigation information in this section incorporates data from [threat and vulnerability management](next-gen-threat-and-vuln-mgt.md), which also provides detailed drill-down information from various links in the report.</span></span>

<span data-ttu-id="5481c-165">![위협 분석 보고서의 완화 섹션 이미지 위협 분석 보고서 완화 섹션 ](images/ta-mitigations.png)
 </span><span class="sxs-lookup"><span data-stu-id="5481c-165">![Image of the mitigations section of a threat analytics report](images/ta-mitigations.png)
_Mitigations section of a threat analytics report_</span></span>

## <a name="additional-report-details-and-limitations"></a><span data-ttu-id="5481c-166">추가 보고서 세부 정보 및 제한 사항</span><span class="sxs-lookup"><span data-stu-id="5481c-166">Additional report details and limitations</span></span>
<span data-ttu-id="5481c-167">보고서를 사용할 때 다음에 유의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5481c-167">When using the reports, keep the following in mind:</span></span> 

- <span data-ttu-id="5481c-168">데이터 범위는 RBAC(역할 기반 액세스 제어) 범위에 따라 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="5481c-168">Data is scoped based on your role-based access control (RBAC) scope.</span></span> <span data-ttu-id="5481c-169">에 액세스할 수 있는 그룹으로 장치의 [상태가 표시됩니다.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="5481c-169">You will see the status of devices in [groups that you can access](machine-groups.md).</span></span>
- <span data-ttu-id="5481c-170">차트에는 추적되는 완화만 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="5481c-170">Charts reflect only mitigations that are tracked.</span></span> <span data-ttu-id="5481c-171">보고서 개요에서 차트에 나와 있지 않은 추가 완화를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5481c-171">Check the report overview for additional mitigations that are not shown in the charts.</span></span>
- <span data-ttu-id="5481c-172">완화는 완전한 탄력을 보장하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5481c-172">Mitigations don't guarantee complete resilience.</span></span> <span data-ttu-id="5481c-173">제공된 완화에는 탄력성을 개선하는 데 필요한 최상의 조치가 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="5481c-173">The provided mitigations reflect the best possible actions needed to improve resiliency.</span></span>
- <span data-ttu-id="5481c-174">장치가 서비스로 데이터를 전송하지 않은 경우 장치는 "사용할 수 없음"으로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="5481c-174">Devices are counted as "unavailable" if they have not transmitted data to the service.</span></span>
- <span data-ttu-id="5481c-175">바이러스 백신 관련 통계는 설정에 Microsoft Defender 바이러스 백신 합니다.</span><span class="sxs-lookup"><span data-stu-id="5481c-175">Antivirus-related statistics are based on Microsoft Defender Antivirus settings.</span></span> <span data-ttu-id="5481c-176">타사 바이러스 백신 솔루션이 있는 장치는 "노출"으로 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5481c-176">Devices with third-party antivirus solutions can appear as "exposed".</span></span>

## <a name="related-topics"></a><span data-ttu-id="5481c-177">관련 항목</span><span class="sxs-lookup"><span data-stu-id="5481c-177">Related topics</span></span>
- [<span data-ttu-id="5481c-178">고급 헌팅을 통해 위협을 사전 대응적으로 찾기</span><span class="sxs-lookup"><span data-stu-id="5481c-178">Proactively find threats with advanced hunting</span></span>](advanced-hunting-overview.md) 
- [<span data-ttu-id="5481c-179">분석가 보고서 섹션 이해</span><span class="sxs-lookup"><span data-stu-id="5481c-179">Understand the analyst report section</span></span>](threat-analytics-analyst-reports.md)
- [<span data-ttu-id="5481c-180">보안 약점 및 노출 평가 및 해결</span><span class="sxs-lookup"><span data-stu-id="5481c-180">Assess and resolve security weaknesses and exposures</span></span>](next-gen-threat-and-vuln-mgt.md)
