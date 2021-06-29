---
title: 첫 번째 인시던트에 대한 보안 준비
description: Microsoft 365 첫 번째 인시던트에 대한 테넌트의 보안 Microsoft 365 Defender.
keywords: 인시던트, 경고, 조사, 상관 관계, 공격, 컴퓨터, 장치, 사용자, IDs, ID, 사서함, 전자 메일, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: fcdce7f5a41c23dfe33eb75ef15b579ac12c8742
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194940"
---
# <a name="prepare-your-security-posture-for-your-first-incident"></a><span data-ttu-id="21584-104">첫 번째 인시던트에 대한 보안 준비</span><span class="sxs-lookup"><span data-stu-id="21584-104">Prepare your security posture for your first incident</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="21584-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="21584-105">**Applies to:**</span></span>
- <span data-ttu-id="21584-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="21584-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="21584-107">인시던트 처리를 준비하는 과정에는 다양한 종류의 보안 인시던트에서 조직의 네트워크를 충분히 보호할 수 있는 설정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="21584-107">Preparing for incident handling involves setting up sufficient protection of an organization's network from different kinds of security incidents.</span></span> <span data-ttu-id="21584-108">NIST(National Institute of Standards and Technology)는 보안 인시던트 위험을 줄이기 위해 위험 평가, 호스트 보안 강화, 네트워크를 안전하게 구성 및 맬웨어 방지를 비롯한 몇 가지 보안 관행을 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="21584-108">To reduce the risk of security incidents, National Institute of Standards and Technology (NIST) recommends several security practices including risk assessments, hardening host security, configuring networks securely, and preventing malware.</span></span> 

<span data-ttu-id="21584-109">Microsoft 365 Defender 인시던트 방지의 여러 측면을 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21584-109">Microsoft 365 Defender can help address several aspects of incident prevention:</span></span> 

- <span data-ttu-id="21584-110">Zero [Trust](/security/zero-trust/) 프레임워크 구현</span><span class="sxs-lookup"><span data-stu-id="21584-110">Implementing a [Zero Trust](/security/zero-trust/) framework</span></span>
- <span data-ttu-id="21584-111">Microsoft 보안 점수를 통해 점수를 할당하여 보안 설정 [결정](microsoft-secure-score.md)</span><span class="sxs-lookup"><span data-stu-id="21584-111">Determining your security posture by assigning a score with [Microsoft Secure Score](microsoft-secure-score.md)</span></span>
- <span data-ttu-id="21584-112">위협 및 취약성 관리의 취약점 평가를 통해 위협 [방지](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="21584-112">Preventing threats through vulnerability assessments in [Threat and Vulnerability Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span></span>
- <span data-ttu-id="21584-113">준비할 수 있도록 최신 보안 위협 이해</span><span class="sxs-lookup"><span data-stu-id="21584-113">Understanding the latest security threats so you can prepare for them</span></span>

## <a name="step-1-implement-zero-trust"></a><span data-ttu-id="21584-114">1단계.</span><span class="sxs-lookup"><span data-stu-id="21584-114">Step 1.</span></span> <span data-ttu-id="21584-115">제로 트러스트 구현</span><span class="sxs-lookup"><span data-stu-id="21584-115">Implement Zero Trust</span></span>

<span data-ttu-id="21584-116">[Zero Trust는](/security/zero-trust/) 모바일 인력, 사용자, 장치, 응용 프로그램 및 데이터를 비롯한 모든 최신 환경의 복잡한 특성을 고려하는 통합 보안 철학 및 종단식 전략입니다.</span><span class="sxs-lookup"><span data-stu-id="21584-116">[Zero Trust](/security/zero-trust/) is an integrated security philosophy and end-to-end strategy that considers the complex nature of any modern environment, including the mobile workforce and the users, devices, applications and data, wherever they may be located.</span></span> <span data-ttu-id="21584-117">단일 창을 제공하여 일관된 방식으로 모든 검색을 관리함으로써 Microsoft 365 Defender 팀이 Zero Trust의 기본 원칙을 [](/security/zero-trust/#guiding-principles-of-zero-trust) 보다 쉽게 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21584-117">By providing a single pane of glass to manage all detections in a consistent way, Microsoft 365 Defender can make it easier for your security operations team to implement the [guiding principles](/security/zero-trust/#guiding-principles-of-zero-trust) of Zero Trust.</span></span> 

<span data-ttu-id="21584-118">Microsoft 365 Defender 구성 요소는 끝점용 Microsoft Defender 또는 기타 모바일 보안 공급업체의 데이터를 장치 준수 정책 및 장치 기반 조건부 액세스 정책 구현에 대한 정보 원본으로 통합하여 Zero Trust에 대한 조건부 액세스 정책을 설정하기 위해 구현된 규칙 위반을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21584-118">Components of Microsoft 365 Defender can display violations of rules that have been implemented to establish Conditional Access policies for Zero Trust by integrating data from Microsoft Defender for Endpoint or other mobile security vendors as an information source for device compliance policies and implementation of device-based Conditional Access policies.</span></span> 

<span data-ttu-id="21584-119">장치 위험은 해당 장치의 사용자가 액세스할 수 있는 리소스에 직접적인 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21584-119">Device risk directly influences what resources will be accessible by the user of that device.</span></span> <span data-ttu-id="21584-120">특정 기준에 따라 리소스에 대한 액세스 거부는 Zero Trust의 주요 테마이고 Microsoft 365 Defender 수준 조건을 결정하는 데 필요한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="21584-120">The denial of access to resources based on certain criteria is the main theme of Zero Trust and Microsoft 365 Defender provides information needed to determine the trust level criteria.</span></span> <span data-ttu-id="21584-121">예를 들어 Microsoft 365 Defender 및 취약성 관리 페이지를 통해 장치의 소프트웨어 버전 수준을 제공할 수 있으며 조건부 액세스 정책은 기한이 지난 또는 취약한 버전을 제한하는 장치를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21584-121">For example, Microsoft 365 Defender can provide the software version level of a device through the Threat and Vulnerability Management page while Conditional Access policies restrict devices that have outdated or vulnerable versions.</span></span>

<span data-ttu-id="21584-122">자동화는 제로 트러스트 환경을 구현하고 유지 관리하는 데 중요한 부분입니다. 또한 잠재적으로 IR(인시던트 대응) 이벤트로 이어질 수 있는 경고 수를 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="21584-122">Automation is a crucial part of implementing and maintaining a Zero Trust environment while also reducing the number of alerts that would potentially lead to incident response (IR) events.</span></span> <span data-ttu-id="21584-123">Microsoft 365 Defender 구성 요소는 수정 작업(Microsoft 365 [](m365d-autoir.md) 보안 센터의 인시던트에 대한 조사), 알림 작업, [ServiceNow와](https://microsoft.service-now.com/sp/)같은 지원 티켓 생성 등 자동화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21584-123">Components of Microsoft 365 Defender can be automated such as [remediation actions](m365d-autoir.md) (known as investigations for an incident in the Microsoft 365 security center), notification actions, and even the creation of support tickets such as in [ServiceNow](https://microsoft.service-now.com/sp/).</span></span>

## <a name="step-2-determine-your-organizations-security-posture"></a><span data-ttu-id="21584-124">2단계.</span><span class="sxs-lookup"><span data-stu-id="21584-124">Step 2.</span></span> <span data-ttu-id="21584-125">조직의 보안 설정 결정</span><span class="sxs-lookup"><span data-stu-id="21584-125">Determine your organization’s security posture</span></span>

<span data-ttu-id="21584-126">다음으로 조직은 Microsoft [보안](microsoft-secure-score.md) 점수를 사용하여 현재 보안 Microsoft 365 Defender 결정하고 이를 개선하는 방법에 대한 권장 사항을 고려할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21584-126">Next, organizations can use the [Microsoft Secure Score](microsoft-secure-score.md) in Microsoft 365 Defender to determine your current security posture and consider recommendations on how to improve it.</span></span> <span data-ttu-id="21584-127">점수가 높을수록 조직에서 보안 권장 사항 및 개선 작업을 더 많이 수행했습니다.</span><span class="sxs-lookup"><span data-stu-id="21584-127">The higher the score is, the more security recommendations and improvement actions have been taken by the organization.</span></span> <span data-ttu-id="21584-128">보안 점수 권장 사항은 여러 제품에서 사용할 수 있으며 조직에서 점수를 더 높게 올 수 있도록 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21584-128">Secure Score recommendations can be taken across different products and allow organizations to raise their scores even higher.</span></span> 

:::image type="content" source="../../media/first-incident-prepare/first-incident-secure-score.png" alt-text="Microsoft 보안 센터의 Microsoft 보안 점수 예제":::
 
## <a name="step-3-assess-your-organizations-vulnerability-exposure"></a><span data-ttu-id="21584-130">3단계.</span><span class="sxs-lookup"><span data-stu-id="21584-130">Step 3.</span></span> <span data-ttu-id="21584-131">조직의 취약성 노출 평가</span><span class="sxs-lookup"><span data-stu-id="21584-131">Assess your organization’s vulnerability exposure</span></span>

<span data-ttu-id="21584-132">인시던트 방지는 중요하고 중요한 보안 인시던트에 집중하기 위한 보안 운영 노력을 간소화하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21584-132">Preventing incidents can help streamline security operations efforts to focus on on-going critical and important security incidents.</span></span> <span data-ttu-id="21584-133">소프트웨어 취약성은 종종 데이터 도용, 데이터 손실 또는 비즈니스 운영 중단으로 이어질 수 있는 공격에 대한 예방 가능한 진입점입니다.</span><span class="sxs-lookup"><span data-stu-id="21584-133">Software vulnerabilities are often a preventable entry point for attacks that can lead to data theft, data loss, or disruption of business operations.</span></span> <span data-ttu-id="21584-134">계속되는 공격이 없는 경우 보안 운영은 조직에서 허용되는 수준의 [](../defender-endpoint/tvm-exposure-score.md) 취약점 노출을 달성하고 유지 관리하기 위해 노력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21584-134">If no attacks are on-going, security operations must strive to achieve and maintain an acceptable level of [vulnerability exposure](../defender-endpoint/tvm-exposure-score.md) in their organization.</span></span>

<span data-ttu-id="21584-135">소프트웨어 패치 진행률을 확인하기 [](../defender-endpoint/next-gen-threat-and-vuln-mgt.md) 위해 Endpoint용 Defender의 위협 및 취약성 관리 페이지를 방문하여 추가 리소스 탭을 통해 Microsoft 365 Defender 액세스할 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21584-135">To check your software patching progress, visit the [Threat and Vulnerability Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md) page in Defender for Endpoint, which you can access from Microsoft 365 Defender through the **More resources** tab.</span></span>

:::image type="content" source="../../media/first-incident-prepare/first-incident-vulnerability.png" alt-text="Microsoft 보안 센터의 위협 및 취약성 페이지 예"::: 
 
## <a name="4-understand-emerging-threats"></a><span data-ttu-id="21584-137">4. 새로운 위협 이해</span><span class="sxs-lookup"><span data-stu-id="21584-137">4. Understand emerging threats</span></span>

<span data-ttu-id="21584-138">보안 [센터의](threat-analytics.md) 위협 Microsoft 365 사용하여 현재 보안 위협 환경과 함께 최신 정보를 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21584-138">Use [threat analytics](threat-analytics.md) in the Microsoft 365 security center to keep up-to-date with the current security threat landscape.</span></span> <span data-ttu-id="21584-139">전문가 Microsoft 보안 연구원은 최신 사이버 위협을 자세히 설명하는 보고서를 만들어 사용자의 구독, 장치 및 사용자에게 어떤 Microsoft 365 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21584-139">Expert Microsoft security researchers create reports that describe the latest cyber-threats in detail so you can understand how they might affect your Microsoft 365 subscription, devices, and users.</span></span> <span data-ttu-id="21584-140">이러한 보고서에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="21584-140">These reports can include:</span></span>

- <span data-ttu-id="21584-141">활성 위협 요소 및 캠페인</span><span class="sxs-lookup"><span data-stu-id="21584-141">Active threat actors and their campaigns</span></span>
- <span data-ttu-id="21584-142">인기 있는 새로운 공격 기술</span><span class="sxs-lookup"><span data-stu-id="21584-142">Popular and new attack techniques</span></span>
- <span data-ttu-id="21584-143">중요한 취약성</span><span class="sxs-lookup"><span data-stu-id="21584-143">Critical vulnerabilities</span></span>
- <span data-ttu-id="21584-144">일반적인 공격 표면</span><span class="sxs-lookup"><span data-stu-id="21584-144">Common attack surfaces</span></span>
- <span data-ttu-id="21584-145">맬웨어가 보인 경우</span><span class="sxs-lookup"><span data-stu-id="21584-145">Prevalent malware</span></span>

<span data-ttu-id="21584-146">또한 위협 분석은 구성 및 경고를 확인하여 위험 상태 및 보고서에 적용할 수 있는 활성 경고가 있는지 여부를 파악합니다.</span><span class="sxs-lookup"><span data-stu-id="21584-146">Threat analytics also looks at your configuration and alerts to determine how at-risk you are and if there are active alerts applicable to a report.</span></span>

<span data-ttu-id="21584-147">새로운 위협에 대한 권장 사항을 구현하여 보안 자세를 강화하고 공격 노출 영역을 최소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21584-147">You can implement the recommendations of an emerging threat to strengthen your security posture and minimize your attack surface area.</span></span>

<span data-ttu-id="21584-148">일정을 정해 두어 보안 센터의 [Threat Analytics](threat-analytics.md) 섹션을 Microsoft 365 합니다.</span><span class="sxs-lookup"><span data-stu-id="21584-148">Make time in your schedule to regularly check the [Threat Analytics](threat-analytics.md) section of the Microsoft 365 security center.</span></span>

## <a name="next-step"></a><span data-ttu-id="21584-149">다음 단계</span><span class="sxs-lookup"><span data-stu-id="21584-149">Next step</span></span>

<span data-ttu-id="21584-150">[![1단계: 인시던트의 선별 및 분석 방법 학습](../../media/first-incident-overview/first-incident-path-step1.png)](first-incident-analyze.md)</span><span class="sxs-lookup"><span data-stu-id="21584-150">[![Step 1: Learn how to triage and analyze incidents](../../media/first-incident-overview/first-incident-path-step1.png)](first-incident-analyze.md)</span></span>

<span data-ttu-id="21584-151">인시던트 [를 분석하고 을(를) 분석하는 방법을 배워야 합니다.](first-incident-analyze.md)</span><span class="sxs-lookup"><span data-stu-id="21584-151">Learn how to [triage and analyze incidents](first-incident-analyze.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="21584-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="21584-152">See also</span></span>

- [<span data-ttu-id="21584-153">사고 개요</span><span class="sxs-lookup"><span data-stu-id="21584-153">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="21584-154">사고 조사</span><span class="sxs-lookup"><span data-stu-id="21584-154">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="21584-155">인시던트 관리</span><span class="sxs-lookup"><span data-stu-id="21584-155">Manage incidents</span></span>](manage-incidents.md)
