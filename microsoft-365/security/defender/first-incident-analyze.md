---
title: 1단계. 첫 번째 인시던트의 세분화 및 분석
description: Defender에서 첫 번째 인시던트의 분석을 Microsoft 365 방법.
keywords: 인시던트, 경고, 조사, 상관 관계, 공격, 컴퓨터, 장치, 사용자, ID, ID, 사서함, 전자 메일, 365, Microsoft, m365, 인시던트 대응, 사이버 공격
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
ms.openlocfilehash: 1890b4f9b4c71efebe833ebaee62debedbf0fb72
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114923"
---
# <a name="step-1-triage-and-analyze-your-first-incident"></a><span data-ttu-id="0269c-105">1단계.</span><span class="sxs-lookup"><span data-stu-id="0269c-105">Step 1.</span></span> <span data-ttu-id="0269c-106">첫 번째 인시던트의 세분화 및 분석</span><span class="sxs-lookup"><span data-stu-id="0269c-106">Triage and analyze your first incident</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="0269c-107">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="0269c-107">**Applies to:**</span></span>
- <span data-ttu-id="0269c-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0269c-108">Microsoft 365 Defender</span></span>

<span data-ttu-id="0269c-109">조직의 표준에 따라 보안 조치를 설정, 구현 및 유지 관리하는 데 시간을 소비할 때 보안 솔루션을 설정하여 보안 위험과 위협을 빠르게 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-109">As you spend some time establishing, implementing, and maintaining security measures according to the organization’s standards, you can set up security solutions to help you quickly identify security risks and threats.</span></span> <span data-ttu-id="0269c-110">Microsoft 365 Defender를 사용하면 적시에 결정을 내리는 데 필요한 정보를 찾을 수 있는 단일 창 창 환경을 통해 인시던트 감지, 판정 및 조사를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-110">Microsoft 365 Defender allows you to detect, triage, and investigate incidents through its single-pane-of-glass experience where you can find the information you need to make timely decisions.</span></span> 

<span data-ttu-id="0269c-111">보안 인시던트가 감지되면 Microsoft 365 Defender가 다른 인시던트나 인시던트에 대해 우선 순위를 지정하거나 우선 순위를 지정하는 데 필요한 세부 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-111">Once a security incident is detected, Microsoft 365 Defender presents details you will need to triage or prioritize an incident or incidents over others.</span></span> <span data-ttu-id="0269c-112">우선 순위를 결정한 후 분석가가 할당된 사례를 조사하는 데 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-112">After determining prioritization, analysts can then focus their energy on investigating cases assigned to them.</span></span>

## <a name="detection-by-microsoft-365-defender"></a><span data-ttu-id="0269c-113">Defender의 Microsoft 365 검색</span><span class="sxs-lookup"><span data-stu-id="0269c-113">Detection by Microsoft 365 Defender</span></span>

<span data-ttu-id="0269c-114">Microsoft 365 Defender는 여러 Microsoft 보안 플랫폼에서 경고 및 이벤트를 감지 원본으로 수신하여 악의적인 활동의 전체적인 그림과 컨텍스트를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-114">Microsoft 365 Defender receives alerts and events from multiple Microsoft security platforms as detection sources to create a holistic picture and context of malicious activity.</span></span> <span data-ttu-id="0269c-115">다음은 가능한 검색 원본입니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-115">These are the possible detection sources:</span></span>

- <span data-ttu-id="0269c-116">[끝점용 Microsoft Defender는](../defender-endpoint/microsoft-defender-endpoint.md) Microsoft Defender 바이러스 백신과 Microsoft 보안 기능을 사용하는 클라우드 사용 고급 위협 방지를 사용하는 끝점 감지 및 응답 솔루션(EDR)Graph.</span><span class="sxs-lookup"><span data-stu-id="0269c-116">[Microsoft Defender for Endpoint](../defender-endpoint/microsoft-defender-endpoint.md) is an endpoint detection and response solution (EDR) that uses Microsoft Defender antivirus as well as cloud-enabled advanced threat protection using Microsoft Security Graph.</span></span> <span data-ttu-id="0269c-117">Endpoint용 Defender는 예방적 보호, 위반 후 감지, 자동화된 조사 및 대응을 위한 통합 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-117">Defender for Endpoint is a unified platform for preventative protection, post-breach detection, automated investigation, and response.</span></span> <span data-ttu-id="0269c-118">사이버 위협으로부터 끝점을 보호하고, 고급 공격 및 데이터 위반을 감지하고, 보안 인시던트를 자동화하며, 보안 자세를 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-118">It protects endpoints from cyberthreats, detects advanced attacks and data breaches, automates security incidents, and improves security posture.</span></span> 
- <span data-ttu-id="0269c-119">[Id용 Microsoft Defender는](https://docs.microsoft.com/defender-for-identity/what-is) 클라우드 기반 보안 솔루션으로, 조직에 대한 고급 위협, ID 손상 및 악의적인 내부자 작업을 식별, 감지 및 조사하기 위해 AD DS(Active Directory 도메인 서비스) 신호를 사용하는 클라우드 기반 보안 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-119">[Microsoft Defender for Identity](https://docs.microsoft.com/defender-for-identity/what-is) is a cloud-based security solution that uses your on-premises Active Directory Domain Services (AD DS) signals to identify, detect, and investigate advanced threats, compromised identities, and malicious insider actions directed at your organization.</span></span> 
- <span data-ttu-id="0269c-120">[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/) 위치와 사용 디바이스에 관계없이 엔터프라이즈 사용자와 사용하는 클라우드 리소스 간의 액세스를 실시간으로 브로커하는 게이트키퍼 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-120">[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/) acts as a gatekeeper to broker access in real time between your enterprise users and the cloud resources they use, wherever your users are located and regardless of the device they are using.</span></span> 
- <span data-ttu-id="0269c-121">[Microsoft Defender for Office 365](../office-365-security/overview.md) 전자 메일 메시지, 링크(URL) 및 공동 작업 도구의 악의적인 위협에 대해 조직을 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-121">[Microsoft Defender for Office 365](../office-365-security/overview.md) safeguards your organization against malicious threats in email messages, links (URLs), and collaboration tools.</span></span> 
- <span data-ttu-id="0269c-122">[Azure Security Center는](https://docs.microsoft.com/azure/security-center/security-center-introduction) 데이터 센터의 보안 환경이 강화되고 클라우드와 사내의 하이브리드 워크로드에서 고급 위협 보호를 제공하는 통합 인프라 보안 관리 시스템입니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-122">[Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-introduction) is a unified infrastructure security management system that strengthens the security posture of your data centers and provides advanced threat protection across your hybrid workloads in the cloud as well as on premises.</span></span> 

<span data-ttu-id="0269c-123">Microsoft 365 Defender에서 [](incidents-overview.md) 인시던트는 이러한 다양한 검색 원본의 경고를 상호 연결하여 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-123">In Microsoft 365 Defender, [incidents](incidents-overview.md) are identified by correlating alerts from these different detection sources.</span></span> <span data-ttu-id="0269c-124">리소스를 함께 스트링하거나 여러 경고를 해당 인시던트로 구분하는 대신, 바로 Microsoft 365 Defender에서 인시던트 큐로 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-124">Instead of spending resources stringing together or distinguishing multiple alerts into their respective incidents, you can start with the incident queue in Microsoft 365 Defender right away.</span></span> <span data-ttu-id="0269c-125">이를 통해 끝점, ID, 전자 메일 및 응용 프로그램 전반에서 인시던트의 효율적인 방식으로 인시던트의 선을 들이고 공격으로 인한 손상을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-125">This allows you to triage incidents in an efficient manner across endpoints, identities, email, and applications, and reduce the damage from an attack.</span></span>

## <a name="triage-your-incidents"></a><span data-ttu-id="0269c-126">인시던트 세분화</span><span class="sxs-lookup"><span data-stu-id="0269c-126">Triage your incidents</span></span>

<span data-ttu-id="0269c-127">조직의 권장 우선 순위 Microsoft 365 사용하여 인시던트 목록을 조사한 후 Defender의 인시던트 대응이 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-127">Incident response in Microsoft 365 Defender starts once you triage the list of incidents using your organization’s recommended method of prioritization.</span></span> <span data-ttu-id="0269c-128">인시던트에 중요도나 긴급성을 할당하는 것은 인시던트가 조사되는 순서를 결정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-128">To triage means to assign a level of importance or urgency to incidents, which then determines the order in which they will be investigated.</span></span> 

<span data-ttu-id="0269c-129">Severity + Impact = Priority 수식으로 Microsoft 365 Defender에서 우선 순위를 지정할 인시던트를 결정하는 유용한 샘플 *가이드입니다.*</span><span class="sxs-lookup"><span data-stu-id="0269c-129">A useful sample guide for determining which incident to prioritize in Microsoft 365 Defender can be summarized by the formula: *Severity + Impact = Priority*.</span></span> 

- <span data-ttu-id="0269c-130">**심각도는** Defender 및 Microsoft 365 구성 요소에 의해 지정된 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-130">**Severity** is the level designated by Microsoft 365 Defender and its integrated security components.</span></span> 
- <span data-ttu-id="0269c-131">**영향은** 조직에 의해 결정하며 일반적으로 영향을 받는 사용자, 장치, 영향을 받는 서비스(또는 이러한 조합) 및 경고 유형에 대한 임계값 수를 포함하지만 이에 국한되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-131">**Impact** is determined by the organization and generally includes, but not limited to, a threshold number of impacted users, devices, services affected (or a combination thereof), and even alert type.</span></span> 

<span data-ttu-id="0269c-132">그런 다음 분석가가 조직에서 설정한 **우선** 순위 기준에 따라 조사를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-132">Analysts then initiate investigations based on the **Priority** criteria set by the organization.</span></span>

<span data-ttu-id="0269c-133">인시던트 우선 순위는 조직에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-133">Incident prioritization might vary depending on the organization.</span></span> <span data-ttu-id="0269c-134">또한 인시던트의 기능 및 정보 영향 및 복구 가능성도 고려하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-134">NIST recommends also considering the functional and informational impact of the incident, and recoverability.</span></span>  

<span data-ttu-id="0269c-135">다음은 한 가지 접근 방식에 불과합니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-135">The following is just one approach to triage:</span></span> 

1. <span data-ttu-id="0269c-136">[인시던트 페이지로](incidents-overview.md) 이동하여 재판을 시작하세요.</span><span class="sxs-lookup"><span data-stu-id="0269c-136">Go to the [incidents](incidents-overview.md) page to initiate triage.</span></span> <span data-ttu-id="0269c-137">조직에 영향을 주는 인시던트 목록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-137">Here you can see a list of incidents affecting your organization.</span></span> <span data-ttu-id="0269c-138">기본적으로 가장 최근 인시던트부터 가장 오래된 인시던트까지 정렬됩니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-138">By default, they are arranged from the most recent to the oldest incident.</span></span> <span data-ttu-id="0269c-139">여기에서 각 인시던트의 심각도, 범주, 활성 경고 수 및 영향을 미치는 엔터티를 보여 미치는 각 인시던트에 대한 다양한 열을 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-139">From here, you can also see different columns for each incident showing their severity, category, number of active alerts, and impacted entities, among others.</span></span> <span data-ttu-id="0269c-140">열 집합을 사용자 지정하고 열 이름을 선택하여 이러한 열을 사용하여 인시던트 큐를 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-140">You can customize the set of columns and sort the incident queue by some these columns by selecting the column name.</span></span> <span data-ttu-id="0269c-141">요구에 따라 인시던트 큐를 필터링할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-141">You can also filter the incident queue according to your needs.</span></span> <span data-ttu-id="0269c-142">사용 가능한 필터의 전체 목록은 인시던트 [우선 순위 지정을 참조하세요.](incident-queue.md#available-filters)</span><span class="sxs-lookup"><span data-stu-id="0269c-142">For a full list of available filters, see [Prioritize incidents](incident-queue.md#available-filters).</span></span>
  
   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-queue.png" alt-text="인시던트 큐의 예"::: 

    <span data-ttu-id="0269c-144">이 인시던트 집합에 대해 순위를 지정하는 방법의 한 가지 예는 더 많은 사용자 및 장치에 영향을 주는 인시던트의 우선 순위를 지정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-144">One example of how you might perform triage for this set of incidents is to prioritize incidents that affected more users and devices.</span></span> <span data-ttu-id="0269c-145">이 예에서는 인시던트 ID 6769가 최대 엔터티 수(장치 7개, 사용자 6명 및 사서함 2개)에 영향을 주어 인시던트 ID 6769의 우선 순위를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-145">In this example, you might prioritize incident ID 6769 because it affected the largest number of entities: 7 devices, 6 users, and 2 mailboxes.</span></span> <span data-ttu-id="0269c-146">또한 인시던트는 ID 기반 경고 및 가능한 자격 증명 도난을 나타내는 Id에 대한 Microsoft Defender의 경고를 포함하는 것으로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-146">Furthermore, the incident appears to contain alerts from Microsoft Defender for Identity which indicate an identity-based alert and possible credential theft.</span></span>

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-high-impact.png" alt-text="영향력이 큰 인시던트의 예":::
 
2. <span data-ttu-id="0269c-148">인시던트 이름 옆의 원을 선택하여 세부 정보를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-148">Select the circle next to the incident name to review the details.</span></span> <span data-ttu-id="0269c-149">왼쪽 창이 오른쪽에 표시될 수 있습니다. 이 창에는 추가 정보를 포함해 더 많은 정보를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-149">A side pane will appear on the right side, which contains additional information that can assist your triage further.</span></span> 
 
   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout.png" alt-text="인시던트 쪽 창의 예"::: 

   <span data-ttu-id="0269c-151">예를 들어 [MITRE ATT&CK에서](https://attack.mitre.org/) 공격자가 인시던트의 범주에 따라 사용하는 전술을 보고, 공격자가 훔친 자격 증명을 사용, 설정한 명령 및 제어, 측면 이동을 수행하고 일부 데이터를 유출하기 때문에 이 인시던트의 우선 순위를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-151">For example, by looking at which [MITRE ATT&CK](https://attack.mitre.org/) tactics the attacker used based on the incident’s categories, you might prioritize this incident because the attacker used stolen credentials, established command and control, performed lateral movement, and exfiltrated some data.</span></span> <span data-ttu-id="0269c-152">이는 공격자가 이미 네트워크로 깊숙이 들어간 후 기밀 정보를 훔친 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-152">This suggests the attacker has already gone deep into the network and possibly stolen confidential information.</span></span>

   <span data-ttu-id="0269c-153">또한 조직에서 Zero Trust 프레임워크를 구현한 경우 자격 증명 액세스는 우선 순위를 정하는 데 중요한 보안 위반으로 고려할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-153">Additionally, if your organization has implemented the Zero Trust framework, you would consider credential access as an important security violation worth prioritizing.</span></span>
 
   <span data-ttu-id="0269c-154">왼쪽 창 아래로 스크롤하면 사용자, 장치 및 사서함과 같은 영향을 받는 특정 엔터티가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-154">Scrolling down the side pane, you will see the specific impacted entities such as users, devices, and mailboxes.</span></span> <span data-ttu-id="0269c-155">각 장치 및 영향을 받는 사서함의 소유자의 노출 수준을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-155">You can check the exposure level of each device and the owners of affected mailboxes.</span></span>

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout-details.png" alt-text="인시던트 쪽 창 세부 정보의 예"::: 
 
3. <span data-ttu-id="0269c-157">왼쪽 창 아래에서 관련 경고를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-157">Further down the side pane, you can find the associated alerts.</span></span> <span data-ttu-id="0269c-158">Microsoft 365 Defender는 이미 경고의 상관을 단일 인시던트에 수행하여 공격을 수정하는 데 더 많은 시간 및 리소스를 절약했습니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-158">Microsoft 365 Defender has already performed the correlation of said alerts into a single incident, saving you time and resources better spent remediating the attack.</span></span> <span data-ttu-id="0269c-159">경고는 의심스러우며 네트워크에서 공격자가 존재할 수 있는 악성 시스템 이벤트일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-159">Alerts are suspicious and therefore possibly malicious system events that suggest the presence of an attacker on a network.</span></span> 

   <span data-ttu-id="0269c-160">이 예에서는 87개 개별 경고가 하나의 보안 인시던트의 일부로 결정했습니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-160">In this example, 87 individual alerts were determined to be part of one security incident.</span></span> <span data-ttu-id="0269c-161">모든 경고를 보고 공격이 어떻게 재생된 방식에 대한 빠른 보기를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-161">You can view all the alerts to get a quick view of how the attack played out.</span></span>

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout-alerts.png" alt-text="인시던트 쪽 창의 경고 예"::: 
 
## <a name="analyze-your-first-incident"></a><span data-ttu-id="0269c-163">첫 번째 인시던트 분석</span><span class="sxs-lookup"><span data-stu-id="0269c-163">Analyze your first incident</span></span>

<span data-ttu-id="0269c-164">경고를 둘러싼 컨텍스트를 이해하는 것은 똑같이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-164">Understanding the context surrounding alerts is equally important.</span></span> <span data-ttu-id="0269c-165">경고는 단일 독립 이벤트가 아닌 경우가 종종 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-165">Often an alert is not a single independent event.</span></span> <span data-ttu-id="0269c-166">동시에 발생하지 않을 수 있는 프로세스, 명령 및 작업의 체인이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-166">There is a chain of processes created, commands, and actions that might not have occurred at the same time.</span></span> <span data-ttu-id="0269c-167">따라서 분석가가 장치 타임라인에서 의심스러운 엔터티의 첫 번째 및 마지막 활동을 찾아 경고의 컨텍스트를 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-167">Therefore, an analyst must look for the first and last activities of the suspicious entity in device timelines to understand the context of the alerts.</span></span>

<span data-ttu-id="0269c-168">Microsoft 365 Defender를 사용하여 데이터를 읽고 분석하는 방법에는 여러 가지가 있지만 분석가의 최종 목표는 가능한 한 빠르게 인시던트에 대응하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-168">There are multiple ways to read and analyze data using Microsoft 365 Defender but the end goal for analysts is to respond to incidents as quickly as possible.</span></span> <span data-ttu-id="0269c-169">Microsoft 365 업계 최고의 자동 수정 기능을 통해 [MTTR(평균](https://www.microsoft.com/security/blog/2020/05/04/lessons-learned-microsoft-soc-part-3c/) 재구성 시간)을 크게 줄일 수 있는 반면, 수동 분석이 필요한 경우도 항상 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-169">While Microsoft 365 Defender can significantly reduce [Mean Time to Remediate (MTTR)](https://www.microsoft.com/security/blog/2020/05/04/lessons-learned-microsoft-soc-part-3c/) through the industry-leading Auto-Remediation feature, there are always cases that require manual analysis.</span></span> 

<span data-ttu-id="0269c-170">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-170">Here's an example:</span></span>

1. <span data-ttu-id="0269c-171">우선 순위가 결정되면 분석가가 인시던트 이름을 선택하여 심층 분석을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-171">Once triage priority has been determined, an analyst begins an in-depth analysis by selecting the incident name.</span></span> <span data-ttu-id="0269c-172">이 페이지에서는 분석을 **지원하기** 위해 데이터가 탭에 표시되는 인시던트 요약을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-172">This page brings up the **Incident Summary** where data is displayed in tabs to assist with the analysis.</span></span> <span data-ttu-id="0269c-173">경고 **탭 아래에** 경고 유형이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-173">Under the **Alerts** tab the type of alerts are displayed.</span></span> <span data-ttu-id="0269c-174">분석가가 각 경고를 클릭하여 각 검색 원본으로 드릴다운할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-174">Analysts can click on each alert to drill down into the respective detection source.</span></span> 

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-summary-tab.png" alt-text="인시던트의 요약 탭 예"::: 
 
    <span data-ttu-id="0269c-176">각 검색 원본에서 다루는 도메인에 대한 빠른 가이드를 확인하려면 이 문서의 [검색](#detection-by-microsoft-365-defender) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0269c-176">For a quick guide about which domain each detection source covers, review the [Detect](#detection-by-microsoft-365-defender) section of this article.</span></span>

2.  <span data-ttu-id="0269c-177">경고 **탭에서** 분석가가 검색 원본에 피벗하여 보다 심층적인 조사 및 분석을 수행 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-177">From the **Alerts** tab, an analyst can pivot to the detection source to conduct a more in-depth investigation and analysis.</span></span> <span data-ttu-id="0269c-178">예를 들어 검색 원본으로 Microsoft Cloud App Security 맬웨어 검색을 선택하면 분석가가 해당 경고 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-178">For example, selecting Malware Detection with Microsoft Cloud App Security as the detection source takes the analyst to its corresponding alert page.</span></span>
  
    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-select-alert.png" alt-text="인시던트 경고 선택의 예"::: 
  
    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-link-to-mcas.png" alt-text="2016의 해당 페이지의 Microsoft Cloud App Security"::: 
  
3.  <span data-ttu-id="0269c-181">예제를 더 조사하려면 페이지 맨 아래로 스크롤하여 영향을 받은 **사용자를 를 니다.**</span><span class="sxs-lookup"><span data-stu-id="0269c-181">To investigate our example further, scrolling to the bottom of the page to view the **Users affected**.</span></span> <span data-ttu-id="0269c-182">맬웨어 검색을 둘러싼 활동 및 컨텍스트를 확인하려면 AnnetteEtte의 사용자 페이지를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-182">To see the activity and context surrounding the malware detection, select Annette Hill’s user page .</span></span> 
  
    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-user-page.png" alt-text="사용자 페이지의 예":::
  
4.  <span data-ttu-id="0269c-184">사용자 페이지에는 TOR 네트워크 IP 주소 경고에서 위험한 로그인으로 시작하는 이벤트의 연대기 *목록이* 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-184">On the user page is a chronological list of events starting with a *Risky Sign-in from a TOR network IP Address* alert.</span></span> <span data-ttu-id="0269c-185">활동의 의심스러운 가능성은 조직이 비즈니스를 수행한 방식의 특성에 따라 달라지지만, 대부분의 경우 사용자가 웹을 익명으로 탐색할 수 있는 네트워크인 TOR(Onion 라우터)을 사용하는 경우 엔터프라이즈 환경에서는 일반 온라인 작업의 경우 매우 가능성 높고 불필요한 것으로 간주될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-185">While the suspiciousness of an activity depends on the nature of how an organization conducts its business, in most cases the use of The Onion Router (TOR), a network that allows users to browse the web anonymously, in an enterprise environment might be considered highly unlikely and unnecessary for regular online operations.</span></span>
  
    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-user-event-list.png" alt-text="사용자에 대한 이벤트의 연도 목록 예":::
  
5.  <span data-ttu-id="0269c-187">각 경고를 선택하면 활동에 대한 자세한 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-187">Each alert can be selected to obtain more information on the activity.</span></span> <span data-ttu-id="0269c-188">예를 들어 **Tor IP 주소** 경고에서 활동을 선택하면 해당 경고의 자체 페이지로 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-188">For example, selecting **Activity from a Tor IP Address** alert leads you to that alert’s own page.</span></span> <span data-ttu-id="0269c-189">Annette는 관리자로서 Office 365 권한이 상승되어 원본 인시던트가 기밀 정보에 액세스하게 됐을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-189">Annette is an Administrator of Office 365, which means she has elevated privileges and the source incident might have led to access to confidential information.</span></span> 
  
    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-mcas-alert.png" alt-text="알림 세부 정보의 Microsoft Cloud App Security"::: 
 
6.  <span data-ttu-id="0269c-191">다른 경고를 선택하면 분석가가 공격의 전체적인 그림을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0269c-191">By selecting other alerts, an analyst can get a complete picture of the attack.</span></span>

## <a name="next-step"></a><span data-ttu-id="0269c-192">다음 단계</span><span class="sxs-lookup"><span data-stu-id="0269c-192">Next step</span></span>

<span data-ttu-id="0269c-193">[![2단계: 인시던트 수정 방법 학습](../../media/first-incident-overview/first-incident-path-step2.png)](first-incident-remediate.md)</span><span class="sxs-lookup"><span data-stu-id="0269c-193">[![Step 2: Learn how to remediate incidents](../../media/first-incident-overview/first-incident-path-step2.png)](first-incident-remediate.md)</span></span>

<span data-ttu-id="0269c-194">인시던트 [수정 방법을 학습합니다.](first-incident-remediate.md)</span><span class="sxs-lookup"><span data-stu-id="0269c-194">Learn how to [remediate incidents](first-incident-remediate.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0269c-195">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0269c-195">See also</span></span>

- [<span data-ttu-id="0269c-196">인시던트 개요</span><span class="sxs-lookup"><span data-stu-id="0269c-196">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="0269c-197">인시던트 분석</span><span class="sxs-lookup"><span data-stu-id="0269c-197">Analyze incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="0269c-198">인시던트 관리</span><span class="sxs-lookup"><span data-stu-id="0269c-198">Manage incidents</span></span>](manage-incidents.md)
