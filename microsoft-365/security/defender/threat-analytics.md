---
title: 위협 분석을 사용하여 새로운 위협 추적 및 대응
ms.reviewer: ''
description: 새로운 위협 및 공격 기술과 이를 중지하는 방법에 대해 자세히 알아보십시오. 조직에 미치는 영향을 평가하고 조직 탄력성 평가
keywords: 위협 분석, 위험 평가, Microsoft 365 Defender, M365D, 완화 상태, 보안 구성, Office 365용 Microsoft Defender, Office 365 위협 분석용 Microsoft Defender, MDO 위협 분석, MDE 및 MDO 위협 분석 통합, 위협 분석 데이터 통합, 통합 Microsoft 365 Defender 위협 분석
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3f7f1453e840d3c709bcabdb67d7d2dc048ea443
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076284"
---
# <a name="track-and-respond-to-emerging-threats-with-threat-analytics"></a><span data-ttu-id="8bbf7-105">위협 분석을 사용하여 새로운 위협 추적 및 대응</span><span class="sxs-lookup"><span data-stu-id="8bbf7-105">Track and respond to emerging threats with threat analytics</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="8bbf7-106">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="8bbf7-106">**Applies to:**</span></span>
- <span data-ttu-id="8bbf7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8bbf7-107">Microsoft 365 Defender</span></span>

> <span data-ttu-id="8bbf7-108">Microsoft 365 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="8bbf7-108">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="8bbf7-109">랩 [환경에서 평가하거나](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) 프로덕션 [환경에서 파일럿](m365d-pilot.md?ocid=cx-evalpilot)프로젝트를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-109">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>

[!INCLUDE [Prerelease](../includes/prerelease.md)]


<span data-ttu-id="8bbf7-110">위협 분석은 전문 Microsoft 보안 연구원이 제공하는 제품 내 위협 인텔리전스 솔루션으로, 다음을 비롯한 새로운 위협에 직면할 때 보안 팀이 가능한 한 효율적으로 하도록 지원하도록 디자인된 제품 내 위협 인텔리전스 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-110">Threat analytics is our in-product threat intelligence solution from expert Microsoft security researchers, designed to assist security teams to be as efficient as possible while facing emerging threats, including:</span></span>

- <span data-ttu-id="8bbf7-111">활성 위협 요소 및 캠페인</span><span class="sxs-lookup"><span data-stu-id="8bbf7-111">Active threat actors and their campaigns</span></span>
- <span data-ttu-id="8bbf7-112">인기 있는 새로운 공격 기술</span><span class="sxs-lookup"><span data-stu-id="8bbf7-112">Popular and new attack techniques</span></span>
- <span data-ttu-id="8bbf7-113">중요한 취약성</span><span class="sxs-lookup"><span data-stu-id="8bbf7-113">Critical vulnerabilities</span></span>
- <span data-ttu-id="8bbf7-114">일반적인 공격 표면</span><span class="sxs-lookup"><span data-stu-id="8bbf7-114">Common attack surfaces</span></span>
- <span data-ttu-id="8bbf7-115">맬웨어가 보인 경우</span><span class="sxs-lookup"><span data-stu-id="8bbf7-115">Prevalent malware</span></span>

<span data-ttu-id="8bbf7-116">이 짧은 비디오를 시청하여 위협 분석을 통해 최신 위협을 추적하고 중지하는 방법에 대해 자세히 알아보십시오.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-116">Watch this short video to learn more about how threat analytics can help you track the latest threats and stop them.</span></span>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWwJfU]

<span data-ttu-id="8bbf7-117">Microsoft 365 보안 포털의 탐색 모음 왼쪽 위나, 또는 해당 도구 모음의 최상위 위협을 표시하는 전용 대시보드 카드에서 위협 분석에 액세스할 수 있습니다. 활성 또는 지속적인 캠페인에 대한 가시성을 확보하고 위협 분석을 통해 무엇을 할지 알면 보안 운영 팀에 정보를 제공한 결정을 내리는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-117">You can access threat analytics either from the upper left-hand side of Microsoft 365 security portal’s navigation bar, or from a dedicated dashboard card which shows the top threats in your org. Getting visibility on active or ongoing campaigns and knowing what to do through threat analytics can help equip your security operations team with informed decisions.</span></span> 

![위협 분석 대시보드의 이미지](../../media/threat-analytics/ta_inlandingpage_mtp.png)

<span data-ttu-id="8bbf7-119">_위협 분석에 액세스하는 위치_</span><span class="sxs-lookup"><span data-stu-id="8bbf7-119">_Where to access threat analytics_</span></span>

<span data-ttu-id="8bbf7-120">더욱 정교한 공격자 및 새로운 위협이 자주 발생하고 자주 등장하는 경우 빠르게 다음을 할 수 있는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-120">With more sophisticated adversaries and new threats emerging frequently and prevalently, it's critical to be able to quickly:</span></span>

- <span data-ttu-id="8bbf7-121">새로운 위협 식별 및 대응</span><span class="sxs-lookup"><span data-stu-id="8bbf7-121">Identify and react to emerging threats</span></span> 
- <span data-ttu-id="8bbf7-122">현재 공격을 중인지 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="8bbf7-122">Learn if you are currently under attack</span></span>
- <span data-ttu-id="8bbf7-123">자산에 대한 위협의 영향 평가</span><span class="sxs-lookup"><span data-stu-id="8bbf7-123">Assess the impact of the threat to your assets</span></span>
- <span data-ttu-id="8bbf7-124">위협에 대한 또는 노출에 대한 탄력성 검토</span><span class="sxs-lookup"><span data-stu-id="8bbf7-124">Review your resilience against or exposure to the threats</span></span>
- <span data-ttu-id="8bbf7-125">위협을 중지하거나 포함하기 위해 취할 수 있는 완화, 복구 또는 방지 작업 식별</span><span class="sxs-lookup"><span data-stu-id="8bbf7-125">Identify the mitigation, recovery, or prevention actions you can take to stop or contain the threats</span></span>

<span data-ttu-id="8bbf7-126">각 보고서는 추적된 위협에 대한 분석과 위협을 방어하는 방법에 대한 광범위한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-126">Each report provides an analysis of a tracked threat and extensive guidance on how to defend against that threat.</span></span> <span data-ttu-id="8bbf7-127">또한 네트워크의 데이터를 통합하여 위협이 활성 상태인지 여부와 적용 가능한 보호가 설정되어 있는지 여부를 나타 내보입니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-127">It also incorporates data from your network, indicating whether the threat is active and if you have applicable protections in place.</span></span>

## <a name="view-the-threat-analytics-dashboard"></a><span data-ttu-id="8bbf7-128">위협 분석 대시보드 보기</span><span class="sxs-lookup"><span data-stu-id="8bbf7-128">View the threat analytics dashboard</span></span>

<span data-ttu-id="8bbf7-129">위협 분석[대시보드(security.microsoft.com/threatanalytics3](https://security.microsoft.com/threatanalytics3))는 조직과 가장 관련이 있는 보고서를 강조합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-129">The threat analytics dashboard ([security.microsoft.com/threatanalytics3](https://security.microsoft.com/threatanalytics3)) highlights the reports that are most relevant to your organization.</span></span> <span data-ttu-id="8bbf7-130">다음 섹션에서는 위협을 요약하여 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-130">It summarizes the threats in the following sections:</span></span>

- <span data-ttu-id="8bbf7-131">**최신 위협**- 최근 게시되거나 업데이트된 위협 보고서와 활성 및 해결된 경고 수를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-131">**Latest threats**—lists the most recently published or updated threat reports, along with the number of active and resolved alerts.</span></span>
- <span data-ttu-id="8bbf7-132">**영향력이 큰 위협**- 조직에 가장 큰 영향을 미치는 위협을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-132">**High-impact threats**—lists the threats that have the highest impact to your organization.</span></span> <span data-ttu-id="8bbf7-133">이 섹션에서는 활성 및 해결된 경고가 가장 많은 위협을 먼저 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-133">This section lists threats with the highest number of active and resolved alerts first.</span></span>
- <span data-ttu-id="8bbf7-134">**위협 요약**- 활성 및 해결된 경고와 함께 위협 수를 표시하여 추적된 모든 위협에 대한 전반적인 영향을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-134">**Threat summary**—provides the overall impact of all tracked threats by showing the number of threats with active and resolved alerts.</span></span>

<span data-ttu-id="8bbf7-135">대시보드에서 위협을 선택하여 해당 위협에 대한 보고서를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-135">Select a threat from the dashboard to view the report for that threat.</span></span>

![위협 분석 대시보드 스크린샷](../../media/threat-analytics/ta_dashboard_mtp.png)

<span data-ttu-id="8bbf7-137">_위협 분석 대시보드. 검색 아이콘을 클릭하여 읽은 위협 분석 보고서와 관련된 키워드의 키를 클릭할 수도 있습니다._</span><span class="sxs-lookup"><span data-stu-id="8bbf7-137">_Threat analytics dashboard. You can also click the Search icon to key in a keyword related to the threat analytics report that you'd like to read._</span></span> 

## <a name="view-a-threat-analytics-report"></a><span data-ttu-id="8bbf7-138">위협 분석 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="8bbf7-138">View a threat analytics report</span></span>

<span data-ttu-id="8bbf7-139">각 위협 분석 보고서는 몇 가지 섹션에 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-139">Each threat analytics report provides information in several sections:</span></span> 

- [<span data-ttu-id="8bbf7-140">**개요**</span><span class="sxs-lookup"><span data-stu-id="8bbf7-140">**Overview**</span></span>](#overview-quickly-understand-the-threat-assess-its-impact-and-review-defenses) 
- [<span data-ttu-id="8bbf7-141">**분석가 보고서**</span><span class="sxs-lookup"><span data-stu-id="8bbf7-141">**Analyst report**</span></span>](#analyst-report-get-expert-insight-from-microsoft-security-researchers)
- [<span data-ttu-id="8bbf7-142">**관련 인시던트**</span><span class="sxs-lookup"><span data-stu-id="8bbf7-142">**Related incidents**</span></span>](#related-incidents-view-and-manage-related-incidents)
- [<span data-ttu-id="8bbf7-143">**영향을 미치는 자산**</span><span class="sxs-lookup"><span data-stu-id="8bbf7-143">**Impacted assets**</span></span>](#impacted-assets-get-list-of-impacted-devices-and-mailboxes)
- [<span data-ttu-id="8bbf7-144">**전자 메일 시도 방지**</span><span class="sxs-lookup"><span data-stu-id="8bbf7-144">**Prevented email attempts**</span></span>](#prevented-email-attempts-view-blocked-or-junked-threat-emails)
- [<span data-ttu-id="8bbf7-145">**완화**</span><span class="sxs-lookup"><span data-stu-id="8bbf7-145">**Mitigations**</span></span>](#mitigations-review-list-of-mitigations-and-the-status-of-your-devices)

### <a name="overview-quickly-understand-the-threat-assess-its-impact-and-review-defenses"></a><span data-ttu-id="8bbf7-146">개요: 위협을 신속하게 이해하고, 영향을 평가하고, 방어를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-146">Overview: Quickly understand the threat, assess its impact, and review defenses</span></span>

<span data-ttu-id="8bbf7-147">개요 **섹션에서는** 자세한 분석 보고서의 미리 보기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-147">The **Overview** section provides a preview of the detailed analyst report.</span></span> <span data-ttu-id="8bbf7-148">또한 잘못 구성 및 패치되지 않은 장치를 통해 조직에 위협이 미치는 영향과 노출을 강조하는 차트도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-148">It also provides charts that highlight the impact of the threat to your organization and your exposure through misconfigured and unpatched devices.</span></span>

![위협 분석 보고서의 개요 섹션 이미지](../../media/threat-analytics/ta_overview_mtp.png)

<span data-ttu-id="8bbf7-150">_위협 분석 보고서의 개요 섹션_</span><span class="sxs-lookup"><span data-stu-id="8bbf7-150">_Overview section of a threat analytics report_</span></span>

#### <a name="assess-impact-on-your-organization"></a><span data-ttu-id="8bbf7-151">조직에 미치는 영향 평가</span><span class="sxs-lookup"><span data-stu-id="8bbf7-151">Assess impact on your organization</span></span>
<span data-ttu-id="8bbf7-152">각 보고서에는 위협의 조직적 영향에 대한 정보를 제공하도록 디자인된 차트가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-152">Each report includes charts designed to provide information about the organizational impact of a threat:</span></span>
- <span data-ttu-id="8bbf7-153">**관련 인시던트**- 다음 데이터를 사용하여 추적된 위협이 조직에 미치는 영향에 대한 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-153">**Related incidents**—provides an overview of the impact of the tracked threat to your organization with the following data:</span></span>
  - <span data-ttu-id="8bbf7-154">활성 경고 수 및 활성 경고와 연관된 활성 인시던트 수</span><span class="sxs-lookup"><span data-stu-id="8bbf7-154">Number of active alerts and the number of active incidents they are associated with</span></span>
  - <span data-ttu-id="8bbf7-155">활성 인시던트의 심각도</span><span class="sxs-lookup"><span data-stu-id="8bbf7-155">Severity of active incidents</span></span>
- <span data-ttu-id="8bbf7-156">**시간의 지난** 알림 - 시간의  지난 관련 **활성** 및 해결된 경고 수를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-156">**Alerts over time**—shows the number of related **Active** and **Resolved** alerts over time.</span></span> <span data-ttu-id="8bbf7-157">해결된 경고 수는 조직이 위협과 관련된 경고에 얼마나 빠르게 응답하는지 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-157">The number of resolved alerts indicates how quickly your organization responds to alerts associated with a threat.</span></span> <span data-ttu-id="8bbf7-158">이상적으로는 며칠 내에 해결된 경고가 차트에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-158">Ideally, the chart should be showing alerts resolved within a few days.</span></span>
- <span data-ttu-id="8bbf7-159">**영향을 받는 자산**- 추적된 위협과 연관된 활성 경고가 하나 이상 있는 고유한 장치 및 전자 메일 계정(사서함)의 수를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-159">**Impacted assets**—shows the number of distinct devices and email accounts (mailboxes) that currently have at least one active alert associated with the tracked threat.</span></span> <span data-ttu-id="8bbf7-160">위협 전자 메일을 받은 사서함에 대해 경고가 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-160">Alerts are triggered for mailboxes that received threat emails.</span></span> <span data-ttu-id="8bbf7-161">위협 전자 메일 배달을 유발하는 재지정에 대한 org-and user-level policies for overrides를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-161">Review both org- and user-level policies for overrides that cause the delivery of threat emails.</span></span>
- <span data-ttu-id="8bbf7-162">**금지된 전자** 메일 시도 - 배달 전에 차단되거나 정크 메일 폴더로 배달된 지난 7일간의 전자 메일 수를 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="8bbf7-162">**Prevented email attempts**—shows the number of emails from the past seven days that were either blocked before delivery or delivered to the junk mail folder.</span></span>

#### <a name="review-security-resilience-and-posture"></a><span data-ttu-id="8bbf7-163">보안 탄력성 및 자세 검토</span><span class="sxs-lookup"><span data-stu-id="8bbf7-163">Review security resilience and posture</span></span>
<span data-ttu-id="8bbf7-164">각 보고서에는 조직이 주어진 위협에 대해 얼마나 탄력적인지 간략하게 설명하는 차트가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-164">Each report includes charts that provide an overview of how resilient your organization is against a given threat:</span></span>
- <span data-ttu-id="8bbf7-165">**보안 구성 상태**- 잘못 구성된 보안 설정이 있는 장치 수를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-165">**Secure configuration status**—shows the number of devices with misconfigured security settings.</span></span> <span data-ttu-id="8bbf7-166">권장 보안 설정을 적용하여 위협을 완화합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-166">Apply the recommended security settings to help mitigate the threat.</span></span> <span data-ttu-id="8bbf7-167">추적된 **모든** 설정을 적용한 장치는 보안으로 간주됩니다. </span><span class="sxs-lookup"><span data-stu-id="8bbf7-167">Devices are considered **Secure** if they have applied _all_ the tracked settings.</span></span>
- <span data-ttu-id="8bbf7-168">**취약성 패치 상태**- 취약한 디바이스의 수를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-168">**Vulnerability patching status**—shows the number of vulnerable devices.</span></span> <span data-ttu-id="8bbf7-169">보안 업데이트 또는 패치를 적용하여 위협에 악용된 취약점을 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-169">Apply security updates or patches to address vulnerabilities exploited by the threat.</span></span>

### <a name="analyst-report-get-expert-insight-from-microsoft-security-researchers"></a><span data-ttu-id="8bbf7-170">분석가 보고서: Microsoft 보안 연구원으로부터 전문가 인사이트 얻기</span><span class="sxs-lookup"><span data-stu-id="8bbf7-170">Analyst report: Get expert insight from Microsoft security researchers</span></span>
<span data-ttu-id="8bbf7-171">분석가 **보고서 섹션에서** 자세한 전문가 쓰기를 읽어 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-171">In the **Analyst report** section, read through the detailed expert write-up.</span></span> <span data-ttu-id="8bbf7-172">대부분의 보고서는 MITRE ATT&CK 프레임워크에 매핑된 전략 및 기술, 권장 사항의 전체 목록 및 강력한 위협 헌팅 지침을 포함하여 공격 체인에 대한 자세한 [설명을](advanced-hunting-overview.md) 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-172">Most reports provide detailed descriptions of attack chains, including tactics and techniques mapped to the MITRE ATT&CK framework, exhaustive lists of recommendations, and powerful [threat hunting](advanced-hunting-overview.md) guidance.</span></span>

[<span data-ttu-id="8bbf7-173">분석 보고서에 대해 자세히 알아보시다</span><span class="sxs-lookup"><span data-stu-id="8bbf7-173">Learn more about the analyst report</span></span>](threat-analytics-analyst-reports.md)

### <a name="related-incidents-view-and-manage-related-incidents"></a><span data-ttu-id="8bbf7-174">관련 인시던트: 관련 인시던트 보기 및 관리</span><span class="sxs-lookup"><span data-stu-id="8bbf7-174">Related incidents: View and manage related incidents</span></span>
<span data-ttu-id="8bbf7-175">관련 **인시던트 탭은** 추적된 위협과 관련된 모든 인시던트 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-175">The **Related incidents** tab provides the list of all incidents related to the tracked threat.</span></span> <span data-ttu-id="8bbf7-176">인시던트를 할당하거나 각 인시던트에 연결된 알림을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-176">You can assign incidents or manage alerts linked to each incident.</span></span> 

![위협 분석 보고서의 관련 인시던트 섹션 이미지](../../media/threat-analytics/ta_related_incidents_mtp.png)

<span data-ttu-id="8bbf7-178">_위협 분석 보고서의 관련 인시던트 섹션_</span><span class="sxs-lookup"><span data-stu-id="8bbf7-178">_Related incidents section of a threat analytics report_</span></span>

### <a name="impacted-assets-get-list-of-impacted-devices-and-mailboxes"></a><span data-ttu-id="8bbf7-179">영향을 받는 자산: 영향을 받는 장치 및 사서함 목록 확인</span><span class="sxs-lookup"><span data-stu-id="8bbf7-179">Impacted assets: Get list of impacted devices and mailboxes</span></span>
<span data-ttu-id="8bbf7-180">활성으로 해결되지 않은 활성 경고의 영향을 받는 자산은 영향을 받는 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-180">An asset is considered impacted if it is affected by an active, unresolved alert.</span></span> <span data-ttu-id="8bbf7-181">영향을 **미치는 자산 탭에는** 다음과 같은 유형의 영향을 미치는 자산이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-181">The **Impacted assets** tab lists the following types of impacted assets:</span></span>
- <span data-ttu-id="8bbf7-182">**영향을 미치는 장치**- 끝점 경고에 대한 Microsoft Defender를 해결하지 않은 끝점입니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-182">**Impacted devices**—endpoints that have unresolved Microsoft Defender for Endpoint alerts.</span></span> <span data-ttu-id="8bbf7-183">이러한 경고는 일반적으로 알려진 위협 표시기 및 활동을 볼 때 발생됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-183">These alerts typically fire on sightings of known threat indicators and activities.</span></span>
- <span data-ttu-id="8bbf7-184">**영향을 받는 사서함**- Office 365용 Microsoft Defender 경고를 트리거한 전자 메일 메시지를 받은 사서함입니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-184">**Impacted mailboxes**—mailboxes that have received email messages that have triggered Microsoft Defender for Office 365 alerts.</span></span> <span data-ttu-id="8bbf7-185">경고를 트리거하는 대부분의 메시지는 일반적으로 차단되는 반면, 사용자 수준 정책은 필터를 대체할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-185">While most messages that trigger alerts are typically blocked, user- or org-level policies can override filters.</span></span>

![위협 분석 보고서의 영향을 미치는 자산 섹션 이미지](../../media/threat-analytics/ta_impacted_assets_mtp.png)

<span data-ttu-id="8bbf7-187">_위협 분석 보고서의 영향을 미치는 자산 섹션_</span><span class="sxs-lookup"><span data-stu-id="8bbf7-187">_Impacted assets section of a threat analytics report_</span></span>

### <a name="prevented-email-attempts-view-blocked-or-junked-threat-emails"></a><span data-ttu-id="8bbf7-188">차단된 전자 메일 시도: 차단 또는 정크 메일 보기</span><span class="sxs-lookup"><span data-stu-id="8bbf7-188">Prevented email attempts: View blocked or junked threat emails</span></span>
<span data-ttu-id="8bbf7-189">Office 365용 Microsoft Defender는 일반적으로 악의적인 링크 또는 첨부 파일을 포함하여 알려진 위협 표시기가 있는 전자 메일을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-189">Microsoft Defender for Office 365 typically blocks emails with known threat indicators, including malicious links or attachments.</span></span> <span data-ttu-id="8bbf7-190">경우에 따라 의심스러운 콘텐츠를 검사하는 사전 필터링 메커니즘은 대신 위협 전자 메일을 정크 메일 폴더로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-190">In some cases, proactive filtering mechanisms that check for suspicious content will instead send threat emails to the junk mail folder.</span></span> <span data-ttu-id="8bbf7-191">두 경우 모두 위협으로 디바이스에서 맬웨어 코드를 시작하게 될 가능성이 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-191">In either case, the chances of the threat launching malware code on the device is reduced.</span></span>

<span data-ttu-id="8bbf7-192">**금지된** 전자 메일 시도 탭에는 배달 전에 차단되거나 Office 365용 Microsoft Defender에 의해 정크 메일 폴더로 전송된 모든 전자 메일이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-192">The **Prevented email attempts** tab lists all the emails that have either been blocked before delivery or sent to the junk mail folder by Microsoft Defender for Office 365.</span></span> 

![위협 분석 보고서의 방지된 전자 메일 시도 섹션 이미지](../../media/threat-analytics/ta_prevented_email_attempts_mtp.png)

<span data-ttu-id="8bbf7-194">_위협 분석 보고서의 전자 메일 시도 방지 섹션_</span><span class="sxs-lookup"><span data-stu-id="8bbf7-194">_Prevented email attempts section of a threat analytics report_</span></span>

### <a name="mitigations-review-list-of-mitigations-and-the-status-of-your-devices"></a><span data-ttu-id="8bbf7-195">완화: 완화 목록 및 장치 상태 검토</span><span class="sxs-lookup"><span data-stu-id="8bbf7-195">Mitigations: Review list of mitigations and the status of your devices</span></span>
<span data-ttu-id="8bbf7-196">완화 **섹션에서** 위협에 대한 조직 탄력을 강화하는 데 도움이 될 수 있는 실행 가능한 특정 권장 사항 목록을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-196">In the **Mitigations** section, review the list of specific actionable recommendations that can help you increase your organizational resilience against the threat.</span></span> <span data-ttu-id="8bbf7-197">추적된 완화 목록은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-197">The list of tracked mitigations includes:</span></span>

- <span data-ttu-id="8bbf7-198">**보안 업데이트**- 온보드 장치에서 발견된 취약점에 대해 지원되는 소프트웨어 보안 업데이트 배포</span><span class="sxs-lookup"><span data-stu-id="8bbf7-198">**Security updates**—deployment of supported software security updates for vulnerabilities found on onboarded devices</span></span>
- <span data-ttu-id="8bbf7-199">**지원되는 보안 구성**</span><span class="sxs-lookup"><span data-stu-id="8bbf7-199">**Supported security configurations**</span></span>
  - <span data-ttu-id="8bbf7-200">클라우드 제공 보호</span><span class="sxs-lookup"><span data-stu-id="8bbf7-200">Cloud-delivered protection</span></span>  
  - <span data-ttu-id="8bbf7-201">잠재적으로 원치 않는 응용 프로그램(PUA) 보호</span><span class="sxs-lookup"><span data-stu-id="8bbf7-201">Potentially unwanted application (PUA) protection</span></span>
  - <span data-ttu-id="8bbf7-202">실시간 보호</span><span class="sxs-lookup"><span data-stu-id="8bbf7-202">Real-time protection</span></span>
 
<span data-ttu-id="8bbf7-203">이 섹션의 완화 정보는 위협 및 [](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)취약성 관리의 데이터를 통합하며, 보고서의 다양한 링크에서 자세한 드릴다운 정보도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-203">Mitigation information in this section incorporates data from [threat and vulnerability management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt), which also provides detailed drill-down information from various links in the report.</span></span>

<span data-ttu-id="8bbf7-204">![보안 구성 세부 정보를 보여 주며 위협 분석 보고서의 완화 섹션 이미지 취약성 세부 정보를 보여주는 위협 분석 보고서의 완화 섹션 ](../../media/threat-analytics/ta_mitigations_mtp.png)
 ![ 이미지](../../media/threat-analytics/ta_mitigations_mtp2.png)</span><span class="sxs-lookup"><span data-stu-id="8bbf7-204">![Image of the mitigations section of a threat analytics report showing secure configuration details](../../media/threat-analytics/ta_mitigations_mtp.png)
![Image of the mitigations section of a threat analytics report showing vulnerability details](../../media/threat-analytics/ta_mitigations_mtp2.png)</span></span>

<span data-ttu-id="8bbf7-205">_위협 분석 보고서의 완화 섹션_</span><span class="sxs-lookup"><span data-stu-id="8bbf7-205">_Mitigations section of a threat analytics report_</span></span>

## <a name="additional-report-details-and-limitations"></a><span data-ttu-id="8bbf7-206">추가 보고서 세부 정보 및 제한 사항</span><span class="sxs-lookup"><span data-stu-id="8bbf7-206">Additional report details and limitations</span></span>
>[!NOTE]
><span data-ttu-id="8bbf7-207">통합 보안 환경의 일부로, 위협 분석은 이제 끝점용 Microsoft Defender 뿐만 아니라 Office E5용 Microsoft Defender 라이선스 소유자도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-207">As part of the unified security experience, threat analytics is now available not just for Microsoft Defender for Endpoint, but also for Microsoft Defender for Office E5 license holders.</span></span>
><span data-ttu-id="8bbf7-208">Microsoft 365 보안 포털(Microsoft 365 Defender)을 사용하지 않는 경우 Microsoft Defender 보안 센터 포털(끝점용 Microsoft Defender)에서 보고서 세부 정보(Office용 Microsoft Defender 없이)를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-208">If you are not using the Microsoft 365 security portal (Microsoft 365 Defender), you can also see the report details (without the Microsoft Defender for Office data) in the Microsoft Defender Security Center portal (Microsoft Defender for Endpoint).</span></span> 

<span data-ttu-id="8bbf7-209">위협 분석 보고서에 액세스하려면 특정 역할 및 사용 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-209">To access threat analytics report you need certain roles and permissions.</span></span> <span data-ttu-id="8bbf7-210">자세한 [내용은 Microsoft 365 Defender에](custom-roles.md) 대한 역할 기반 액세스 제어의 사용자 지정 역할을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-210">See [Custom roles in role-based access control for Microsoft 365 Defender](custom-roles.md) for details.</span></span>
  - <span data-ttu-id="8bbf7-211">경고, 인시던트 또는 영향을 미치는 자산 데이터를 보기 위해 Office용 Microsoft Defender 또는 끝점 경고 데이터용 Microsoft Defender에 대한 사용 권한이 있는 경우 또는 둘 다에 대한 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-211">To view alerts, incidents, or impacted assets data, you need to have permissions to Microsoft Defender for Office or Microsoft Defender for Endpoint alerts data, or both.</span></span>
  - <span data-ttu-id="8bbf7-212">금지된 전자 메일 시도를 확인하려면 Office 헌팅 데이터에 대한 Microsoft Defender에 대한 사용 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-212">To view prevented email attempts, you need to have permissions to Microsoft Defender for Office hunting data.</span></span> 
  - <span data-ttu-id="8bbf7-213">완화를 확인하려면 끝점용 Microsoft Defender에서 위협 및 취약성 관리 데이터에 대한 사용 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-213">To view mitigations, you need to have permissions to threat and vulnerability management data in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="8bbf7-214">위협 분석 데이터를 보는 경우 다음 요인에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-214">When looking at the threat analytics data, remember the following factors:</span></span>
- <span data-ttu-id="8bbf7-215">차트에는 추적되는 완화만 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-215">Charts reflect only mitigations that are tracked.</span></span> <span data-ttu-id="8bbf7-216">보고서 개요에서 차트에 나와 있지 않은 추가 완화를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-216">Check the report overview for additional mitigations that are not shown in the charts.</span></span>
- <span data-ttu-id="8bbf7-217">완화는 완전한 탄력을 보장하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-217">Mitigations don't guarantee complete resilience.</span></span> <span data-ttu-id="8bbf7-218">제공된 완화에는 탄력성을 개선하는 데 필요한 최상의 조치가 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-218">The provided mitigations reflect the best possible actions needed to improve resiliency.</span></span>
- <span data-ttu-id="8bbf7-219">장치가 서비스로 데이터를 전송하지 않은 경우 장치는 "사용할 수 없음"으로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-219">Devices are counted as "unavailable" if they have not transmitted data to the service.</span></span>
- <span data-ttu-id="8bbf7-220">바이러스 백신 관련 통계는 Microsoft Defender 바이러스 백신 설정을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-220">Antivirus-related statistics are based on Microsoft Defender Antivirus settings.</span></span> <span data-ttu-id="8bbf7-221">타사 바이러스 백신 솔루션이 있는 장치는 "노출"으로 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bbf7-221">Devices with third-party antivirus solutions can appear as "exposed".</span></span>

## <a name="related-topics"></a><span data-ttu-id="8bbf7-222">관련 항목</span><span class="sxs-lookup"><span data-stu-id="8bbf7-222">Related topics</span></span>
- [<span data-ttu-id="8bbf7-223">고급 헌팅을 통해 위협을 사전 대응적으로 찾기</span><span class="sxs-lookup"><span data-stu-id="8bbf7-223">Proactively find threats with advanced hunting</span></span>](advanced-hunting-overview.md) 
- [<span data-ttu-id="8bbf7-224">분석가 보고서 섹션 이해</span><span class="sxs-lookup"><span data-stu-id="8bbf7-224">Understand the analyst report section</span></span>](threat-analytics-analyst-reports.md)
- [<span data-ttu-id="8bbf7-225">보안 약점 및 노출 평가 및 해결</span><span class="sxs-lookup"><span data-stu-id="8bbf7-225">Assess and resolve security weaknesses and exposures</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)