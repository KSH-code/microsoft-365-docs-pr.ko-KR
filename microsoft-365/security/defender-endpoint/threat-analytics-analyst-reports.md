---
title: 위협 분석의 분석 보고서 섹션 이해
ms.reviewer: ''
description: 각 위협 분석 보고서의 분석 보고서 섹션에 대해 자세히 알아보십시오. 위협, 완화, 탐지, 고급 헌팅 쿼리에 대한 정보를 제공하는 방법을 이해합니다.
keywords: 분석 보고서, 위협 분석, 검색, 고급 헌팅 쿼리, 완화,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 599eab29628d11d67843f89a0eb59bb4db1e66ad
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185458"
---
# <a name="understand-the-analyst-report-in-threat-analytics"></a><span data-ttu-id="c46ce-105">위협 분석의 분석 보고서 이해</span><span class="sxs-lookup"><span data-stu-id="c46ce-105">Understand the analyst report in threat analytics</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c46ce-106">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="c46ce-106">**Applies to:**</span></span>
- [<span data-ttu-id="c46ce-107">Microsoft Defender Advanced Threat Protection(Microsoft Defender ATP)</span><span class="sxs-lookup"><span data-stu-id="c46ce-107">Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2069559)
- [<span data-ttu-id="c46ce-108">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="c46ce-108">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c46ce-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c46ce-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c46ce-110">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="c46ce-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c46ce-111">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="c46ce-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="c46ce-112">각 [위협 분석 보고서에는](threat-analytics.md) 동적 섹션과 분석 보고서라는 포괄적인 서면 _섹션이 포함되어 있습니다._</span><span class="sxs-lookup"><span data-stu-id="c46ce-112">Each [threat analytics report](threat-analytics.md) includes dynamic sections and a comprehensive written section called the _analyst report_.</span></span> <span data-ttu-id="c46ce-113">이 섹션에 액세스하려면 추적된 위협에 대한 보고서를 열고 분석가 보고서 **탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c46ce-113">To access this section, open the report about the tracked threat and select the **Analyst report** tab.</span></span>

![위협 분석 보고서의 분석 보고서 섹션 이미지](images/ta-analyst-report-small.png)

<span data-ttu-id="c46ce-115">_위협 분석 보고서의 분석가 보고서 섹션_</span><span class="sxs-lookup"><span data-stu-id="c46ce-115">_Analyst report section of a threat analytics report_</span></span>

## <a name="scan-the-analyst-report"></a><span data-ttu-id="c46ce-116">분석가 보고서 검사</span><span class="sxs-lookup"><span data-stu-id="c46ce-116">Scan the analyst report</span></span> 
<span data-ttu-id="c46ce-117">분석 보고서의 각 섹션은 실행 가능한 정보를 제공하도록 디자인됩니다.</span><span class="sxs-lookup"><span data-stu-id="c46ce-117">Each section of the analyst report is designed to provide actionable information.</span></span> <span data-ttu-id="c46ce-118">보고서는 다르지만 대부분의 보고서에는 다음 표에 설명된 섹션이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c46ce-118">While reports vary, most reports include the sections described in the following table.</span></span>

| <span data-ttu-id="c46ce-119">보고서 섹션</span><span class="sxs-lookup"><span data-stu-id="c46ce-119">Report section</span></span> | <span data-ttu-id="c46ce-120">설명</span><span class="sxs-lookup"><span data-stu-id="c46ce-120">Description</span></span> |
|--|--|
| <span data-ttu-id="c46ce-121">요약</span><span class="sxs-lookup"><span data-stu-id="c46ce-121">Executive summary</span></span> | <span data-ttu-id="c46ce-122">위협이 처음 확인된 경우, 그 동기, 중요한 이벤트, 주요 대상 및 고유한 도구와 기술을 포함하여 위협에 대한 개요</span><span class="sxs-lookup"><span data-stu-id="c46ce-122">Overview of the threat, including when it was first seen, its motivations, notable events, major targets, and distinct tools and techniques.</span></span> <span data-ttu-id="c46ce-123">이 정보를 사용하여 산업, 지리적 위치 및 네트워크 컨텍스트에서 위협의 우선 순위를 지정하는 방법을 추가로 평가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c46ce-123">You can use this information to further assess how to prioritize the threat in the context of your industry, geographic location, and network.</span></span> |
| <span data-ttu-id="c46ce-124">분석</span><span class="sxs-lookup"><span data-stu-id="c46ce-124">Analysis</span></span> | <span data-ttu-id="c46ce-125">공격의 세부 정보와 공격자가 새로운 기술 또는 공격 표면을 활용하는 방법을 포함하여 위협에 대한 기술 정보</span><span class="sxs-lookup"><span data-stu-id="c46ce-125">Technical information about the threats, including the details of an attack and how attackers might utilize a new technique or attack surface</span></span> | 
| <span data-ttu-id="c46ce-126">MITRE ATT&CK 기술 관찰</span><span class="sxs-lookup"><span data-stu-id="c46ce-126">MITRE ATT&CK techniques observed</span></span> | <span data-ttu-id="c46ce-127">관찰된 기술이 [MITRE ATT](https://attack.mitre.org/) 및 CK 공격&매핑되는 방법</span><span class="sxs-lookup"><span data-stu-id="c46ce-127">How observed techniques map to the [MITRE ATT&CK attack framework](https://attack.mitre.org/)</span></span> | 
| [<span data-ttu-id="c46ce-128">완화</span><span class="sxs-lookup"><span data-stu-id="c46ce-128">Mitigations</span></span>](#apply-additional-mitigations) | <span data-ttu-id="c46ce-129">위협의 영향을 중지하거나 줄이는 데 도움이 될 수 있는 권장 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="c46ce-129">Recommendations that can stop or help reduce the impact of the threat.</span></span> <span data-ttu-id="c46ce-130">이 섹션에는 위협 분석 보고서의 일부로 동적으로 추적되지 않는 완화 기능도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c46ce-130">This section also includes mitigations that aren't tracked dynamically as part of the threat analytics report.</span></span> |
| [<span data-ttu-id="c46ce-131">검색 세부 정보</span><span class="sxs-lookup"><span data-stu-id="c46ce-131">Detection details</span></span>](#understand-how-each-threat-can-be-detected) | <span data-ttu-id="c46ce-132">위협과 관련된 활동 또는 구성 요소를 표면화할 수 있는 Microsoft 보안 솔루션에서 제공하는 특정 및 일반 감지.</span><span class="sxs-lookup"><span data-stu-id="c46ce-132">Specific and generic detections provided by Microsoft security solutions that can surface activity or components associated with the threat.</span></span> | 
| [<span data-ttu-id="c46ce-133">고급 헌팅</span><span class="sxs-lookup"><span data-stu-id="c46ce-133">Advanced hunting</span></span>](#find-subtle-threat-artifacts-using-advanced-hunting) | <span data-ttu-id="c46ce-134">[고급 헌팅은 가능한](advanced-hunting-overview.md) 위협 활동을 사전 식별하기 위한 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="c46ce-134">[Advanced hunting queries](advanced-hunting-overview.md) for proactively identifying possible threat activity.</span></span> <span data-ttu-id="c46ce-135">대부분의 쿼리는 검색을 보완하기 위해 제공됩니다. 특히 악의적인 것으로 동적으로 평가할 수 없는 잠재적으로 악의적인 구성 요소 또는 동작을 찾기 위한 쿼리가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="c46ce-135">Most queries are provided to supplement detections, especially for locating potentially malicious components or behaviors that couldn't be dynamically assessed to be malicious.</span></span> | 
| <span data-ttu-id="c46ce-136">참조</span><span class="sxs-lookup"><span data-stu-id="c46ce-136">References</span></span> | <span data-ttu-id="c46ce-137">보고서를 작성하는 동안 분석가가 참조하는 Microsoft 및 타사 발행물</span><span class="sxs-lookup"><span data-stu-id="c46ce-137">Microsoft and third-party publications referenced by analysts during the creation of the report.</span></span> <span data-ttu-id="c46ce-138">위협 분석 콘텐츠는 Microsoft 연구원이 유효성을 검사한 데이터를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="c46ce-138">Threat analytics content is based on data validated by Microsoft researchers.</span></span> <span data-ttu-id="c46ce-139">공개적으로 사용 가능한 타사 원본의 정보는 명확하게 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="c46ce-139">Information from publicly available, third-party sources are identified clearly as such.</span></span> | 
| <span data-ttu-id="c46ce-140">로그 변경</span><span class="sxs-lookup"><span data-stu-id="c46ce-140">Change log</span></span> | <span data-ttu-id="c46ce-141">보고서가 게시된 시간 및 보고서가 크게 변경된 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="c46ce-141">The time the report was published and when significant changes were made to the report.</span></span> |

## <a name="apply-additional-mitigations"></a><span data-ttu-id="c46ce-142">추가 완화 적용</span><span class="sxs-lookup"><span data-stu-id="c46ce-142">Apply additional mitigations</span></span>
<span data-ttu-id="c46ce-143">위협 분석은 보안 업데이트 및 보안 구성의 상태를 [동적으로 추적합니다.](threat-analytics.md#mitigations-review-list-of-mitigations-and-the-status-of-your-devices)</span><span class="sxs-lookup"><span data-stu-id="c46ce-143">Threat analytics dynamically tracks the [status of security updates and secure configurations](threat-analytics.md#mitigations-review-list-of-mitigations-and-the-status-of-your-devices).</span></span> <span data-ttu-id="c46ce-144">이 정보는 완화 탭의 차트 및 **표로 사용할 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c46ce-144">This information is available as charts and tables in the **Mitigations** tab.</span></span>

<span data-ttu-id="c46ce-145">이러한 추적된 완화 외에도 분석가 보고서에서는 동적으로 모니터링되지 않는 완화에 _대해_ 논의합니다.</span><span class="sxs-lookup"><span data-stu-id="c46ce-145">In addition to these tracked mitigations, the analyst report also discusses mitigations that are _not_ dynamically monitored.</span></span> <span data-ttu-id="c46ce-146">다음은 동적으로 추적되지 않는 중요한 완화의 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="c46ce-146">Here are some examples of important mitigations that are not dynamically tracked:</span></span>

- <span data-ttu-id="c46ce-147">_.lnk_ 첨부 파일 또는 기타 의심스러운 파일 형식이 있는 전자 메일 차단</span><span class="sxs-lookup"><span data-stu-id="c46ce-147">Block emails with _.lnk_ attachments or other suspicious file types</span></span>
- <span data-ttu-id="c46ce-148">로컬 관리자 암호 임의로 설정</span><span class="sxs-lookup"><span data-stu-id="c46ce-148">Randomize local administrator passwords</span></span>
- <span data-ttu-id="c46ce-149">최종 사용자에게 피싱 전자 메일 및 기타 위협 벡터 교육</span><span class="sxs-lookup"><span data-stu-id="c46ce-149">Educate end users about phishing email and other threat vectors</span></span>
- <span data-ttu-id="c46ce-150">특정 공격 [표면 감소 규칙 켜기](attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="c46ce-150">Turn on specific [attack surface reduction rules](attack-surface-reduction.md)</span></span>

<span data-ttu-id="c46ce-151">완화 탭을  사용하여 위협에 대한 보안 상태를 평가할 수 있는 반면, 이러한 권장 사항을 통해 보안 상태를 개선하기 위한 추가 단계를 취할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c46ce-151">While you can use the **Mitigations** tab to assess your security posture against a threat, these recommendations let you take additional steps towards improving your security posture.</span></span> <span data-ttu-id="c46ce-152">분석가 보고서의 모든 완화 지침을 신중하게 읽고 가능한 경우 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="c46ce-152">Carefully read all the mitigation guidance in the analyst report and apply them whenever possible.</span></span>

## <a name="understand-how-each-threat-can-be-detected"></a><span data-ttu-id="c46ce-153">각 위협을 검색할 수 있는 방법 이해</span><span class="sxs-lookup"><span data-stu-id="c46ce-153">Understand how each threat can be detected</span></span>
<span data-ttu-id="c46ce-154">분석가 보고서는 끝점 바이러스 백신 및 끝점  감지 및 응답(EDR) 기능에 대한 Microsoft Defender의 검색 기능도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c46ce-154">The analyst report also provides the detections from Microsoft Defender for Endpoint antivirus and _endpoint detection and response_ (EDR) capabilities.</span></span>

### <a name="antivirus-detections"></a><span data-ttu-id="c46ce-155">바이러스 백신 검색</span><span class="sxs-lookup"><span data-stu-id="c46ce-155">Antivirus detections</span></span>
<span data-ttu-id="c46ce-156">이러한 검색은 [Microsoft Defender 바이러스](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) 백신이 켜져 있는 장치에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c46ce-156">These detections are available on devices with [Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) turned on.</span></span> <span data-ttu-id="c46ce-157">끝점용 Microsoft Defender에 온보딩된 장치에서 이러한 검색이 발생하면 보고서의 차트를 밝게 하는 경고도 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="c46ce-157">When these detections occur on devices that have been onboarded to Microsoft Defender for Endpoint, they also trigger alerts that light up the charts in the report.</span></span>

>[!NOTE]
><span data-ttu-id="c46ce-158">또한 분석가 보고서에는 추적된 위협과 관련한 구성 요소 또는 동작 외에도 광범위한 위협을 식별할 수 있는 일반 탐지가 나열됩니다. </span><span class="sxs-lookup"><span data-stu-id="c46ce-158">The analyst report also lists **generic detections** that can identify a wide-range of threats, in addition to components or behaviors specific to the tracked threat.</span></span> <span data-ttu-id="c46ce-159">이러한 일반 검색은 차트에 반영되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c46ce-159">These generic detections don't reflect in the charts.</span></span>

### <a name="endpoint-detection-and-response-edr-alerts"></a><span data-ttu-id="c46ce-160">끝점 감지 및 응답(EDR) 경고</span><span class="sxs-lookup"><span data-stu-id="c46ce-160">Endpoint detection and response (EDR) alerts</span></span>
<span data-ttu-id="c46ce-161">끝점용 Microsoft Defender에 온보딩된 장치에 대해 EDR [경고가 발생했습니다.](onboard-configure.md)</span><span class="sxs-lookup"><span data-stu-id="c46ce-161">EDR alerts are raised for [devices onboarded to Microsoft Defender for Endpoint](onboard-configure.md).</span></span> <span data-ttu-id="c46ce-162">이러한 경고는 일반적으로 Microsoft Defender for Endpoint 센서 및 기타 끝점 기능(예: 바이러스 백신, 네트워크 보호, 변조 방지)에서 수집한 보안 신호와 강력한 신호 원본 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="c46ce-162">These alerts generally rely on security signals collected by the Microsoft Defender for Endpoint sensor and other endpoint capabilities—such as antivirus, network protection, tamper protection—that serve as powerful signal sources.</span></span>

<span data-ttu-id="c46ce-163">바이러스 백신 검색 목록과 마찬가지로 일부 EDR 경고는 추적된 위협과 연결되지 않을 수 있는 의심스러운 동작에 일반적으로 플래그를 지정하도록 디자인됩니다.</span><span class="sxs-lookup"><span data-stu-id="c46ce-163">Like the list of antivirus detections, some EDR alerts are designed to generically flag suspicious behavior that might not be associated with the tracked threat.</span></span> <span data-ttu-id="c46ce-164">이러한 경우 보고서는 경고를 "일반"으로 명확하게 식별하고 보고서의 차트에 영향을주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c46ce-164">In such cases, the report will clearly identify the alert as "generic" and that it doesn't influence any of the charts in the report.</span></span>

## <a name="find-subtle-threat-artifacts-using-advanced-hunting"></a><span data-ttu-id="c46ce-165">고급 헌팅을 사용하여 미묘한 위협 요소 찾기</span><span class="sxs-lookup"><span data-stu-id="c46ce-165">Find subtle threat artifacts using advanced hunting</span></span>
<span data-ttu-id="c46ce-166">검색을 통해 추적된 위협을 자동으로 식별하고 중지할 수 있는 반면, 많은 공격 활동은 추가 검사가 필요한 미묘한 추적을 남길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c46ce-166">While detections allow you to identify and stop the tracked threat automatically, many attack activities leave subtle traces that require additional inspection.</span></span> <span data-ttu-id="c46ce-167">일부 공격 활동은 정상일 수도 있는 동작을 나타내기 때문에 동적으로 감지하면 작동 노이즈가 발생하거나 오탐지가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c46ce-167">Some attack activities exhibit behaviors that can also be normal, so detecting them dynamically can result in operational noise or even false positives.</span></span>

<span data-ttu-id="c46ce-168">[고급 헌팅은](advanced-hunting-overview.md) 위협 활동의 미묘한 표시기를 쉽게 찾은 Kusto 쿼리 언어를 기반으로 하는 쿼리 인터페이스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c46ce-168">[Advanced hunting](advanced-hunting-overview.md) provides a query interface based on Kusto Query Language that simplifies locating subtle indicators of threat activity.</span></span> <span data-ttu-id="c46ce-169">또한 상황 정보를 표시하고 지표가 위협에 연결되어 있는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c46ce-169">It also allows you to surface contextual information and verify whether indicators are connected to a threat.</span></span>

<span data-ttu-id="c46ce-170">분석가 보고서의 고급 헌팅 쿼리는 Microsoft 분석가에 의해 검색되어 고급 헌팅 쿼리 편집기에서 실행할 [준비가 완료되었습니다.](https://securitycenter.windows.com/advanced-hunting)</span><span class="sxs-lookup"><span data-stu-id="c46ce-170">Advanced hunting queries in the analyst reports have been vetted by Microsoft analysts and are ready for you to run in the [advanced hunting query editor](https://securitycenter.windows.com/advanced-hunting).</span></span> <span data-ttu-id="c46ce-171">또한 쿼리를 사용하여 향후 [](custom-detection-rules.md) 일치 시 경고를 트리거하는 사용자 지정 검색 규칙을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c46ce-171">You can also use the queries to create [custom detection rules](custom-detection-rules.md) that trigger alerts for future matches.</span></span>


## <a name="related-topics"></a><span data-ttu-id="c46ce-172">관련 항목</span><span class="sxs-lookup"><span data-stu-id="c46ce-172">Related topics</span></span>
- [<span data-ttu-id="c46ce-173">위협 분석 개요</span><span class="sxs-lookup"><span data-stu-id="c46ce-173">Threat analytics overview</span></span>](threat-analytics.md)
- [<span data-ttu-id="c46ce-174">고급 헌팅을 통해 위협을 사전 대응적으로 찾기</span><span class="sxs-lookup"><span data-stu-id="c46ce-174">Proactively find threats with advanced hunting</span></span>](advanced-hunting-overview.md) 
- [<span data-ttu-id="c46ce-175">사용자 지정 검색 규칙</span><span class="sxs-lookup"><span data-stu-id="c46ce-175">Custom detection rules</span></span>](custom-detection-rules.md)