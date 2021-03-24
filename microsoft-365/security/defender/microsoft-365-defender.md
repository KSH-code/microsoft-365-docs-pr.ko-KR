---
title: Microsoft 365 Defender
description: Microsoft 365 Defender는 장치, ID, 데이터 및 응용 프로그램을 보호하도록 설계된 조정된 위협 방지 솔루션입니다.
keywords: Microsoft 위협 방지, 사이버 보안, 고급 영구 위협, 엔터프라이즈 보안, 장치, 장치, ID, 사용자, 데이터, 응용 프로그램, 인시던트, 자동화된 조사 및 수정, 고급 헌팅 소개
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: f789053e0922ee81155a243bbaa7b3ab5b0f6d87
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072695"
---
# <a name="microsoft-365-defender"></a><span data-ttu-id="d900f-104">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d900f-104">Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d900f-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="d900f-105">**Applies to:**</span></span>
- <span data-ttu-id="d900f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d900f-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="d900f-107">Microsoft 365 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="d900f-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="d900f-108">랩 [환경에서 평가하거나](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) 프로덕션 [환경에서 파일럿](m365d-pilot.md?ocid=cx-evalpilot)프로젝트를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d900f-108">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>

<span data-ttu-id="d900f-109">Microsoft 365 Defender는 엔드포인트, ID, 전자 메일 및 응용 프로그램에서 감지, 예방, 조사 및 대응을 기본적으로 조정하여 정교한 공격으로부터 통합된 보호를 제공하는 통합 사전 및 사후 침해 엔터프라이즈 방어 제품군입니다.</span><span class="sxs-lookup"><span data-stu-id="d900f-109">Microsoft 365 Defender is a unified pre- and post-breach enterprise defense suite that natively coordinates detection, prevention, investigation, and response across endpoints, identities, email, and applications to provide integrated protection against sophisticated attacks.</span></span>

<span data-ttu-id="d900f-110">통합된 Microsoft 365 Defender 솔루션을 사용하여 보안 전문가는 이러한 각 제품이 수신하는 위협 신호를 통합하고 위협의 전체 범위와 영향을 확인할 수 있습니다. 환경이 환경에 들어오고 있는 방법, 영향을 받는 방법 및 현재 조직에 미치는 영향</span><span class="sxs-lookup"><span data-stu-id="d900f-110">With the integrated Microsoft 365 Defender solution, security professionals can stitch together the threat signals that each of these products receive and determine the full scope and impact of the threat; how it entered the environment, what it's affected, and how it's currently impacting the organization.</span></span> <span data-ttu-id="d900f-111">Microsoft 365 Defender는 공격을 방지하거나 중지하고 영향을 받는 사서함, 끝점 및 사용자 ID를 자체적으로 고치기 위한 자동 조치를 취합니다.</span><span class="sxs-lookup"><span data-stu-id="d900f-111">Microsoft 365 Defender takes automatic action to prevent or stop the attack and self-heal affected mailboxes, endpoints, and user identities.</span></span>  


<center><h2><span data-ttu-id="d900f-112">Microsoft 365 Defender 서비스</center></span><span class="sxs-lookup"><span data-stu-id="d900f-112">Microsoft 365 Defender services</center></span></span></h2>
<table><tr><td><span data-ttu-id="d900f-113"><center><b><a href="https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection"><b>끝점용 Microsoft Defender</b></center></span><span class="sxs-lookup"><span data-stu-id="d900f-113"><center><b><a href="https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection"><b>Microsoft Defender for Endpoint</b></center></span></span></a></td>
<td><span data-ttu-id="d900f-114"><center><b><a href="https://docs.microsoft.com/office365/securitycompliance/office-365-atp"><b>Office 365용 Microsoft Defender</b></center></span><span class="sxs-lookup"><span data-stu-id="d900f-114"><center><b><a href="https://docs.microsoft.com/office365/securitycompliance/office-365-atp"><b>Microsoft Defender for Office 365</b></center></span></span></a></td>
<td><span data-ttu-id="d900f-115"><center><b><a href="/azure-advanced-threat-protection/"><b>Id용 Microsoft Defender</b></a></center></span><span class="sxs-lookup"><span data-stu-id="d900f-115"><center><b><a href="/azure-advanced-threat-protection/"><b>Microsoft Defender for Identity</b></a></center></span></span></td>
<td><span data-ttu-id="d900f-116"><center><b><a href="/cloud-app-security/"><b>Microsoft Cloud App Security</b></a></center></span><span class="sxs-lookup"><span data-stu-id="d900f-116"><center><b><a href="/cloud-app-security/"><b>Microsoft Cloud App Security</b></a></center></span></span></td>
</tr>
</table>
<br>

## <a name="microsoft-365-defender-interactive-guide"></a><span data-ttu-id="d900f-117">Microsoft 365 Defender 대화형 가이드</span><span class="sxs-lookup"><span data-stu-id="d900f-117">Microsoft 365 Defender interactive guide</span></span>

<span data-ttu-id="d900f-118">이 대화형 가이드에서는 Microsoft 365 Defender로 조직을 보호하는 방법을 배우게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d900f-118">In this interactive guide, you'll learn how to protect your organization with Microsoft 365 Defender.</span></span> <span data-ttu-id="d900f-119">Microsoft 365 Defender가 보안 위험을 감지하고, 조직에 대한 공격을 조사하고, 유해한 활동을 자동으로 방지하는 데 어떻게 도움을 줄 수 있는지 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d900f-119">You'll see how Microsoft 365 Defender can help you detect security risks, investigate attacks to your organization, and prevent harmful activities automatically.</span></span>

> [!VIDEO https://aka.ms/M365Defender-InteractiveGuide]



<span data-ttu-id="d900f-120">Microsoft 365 Defender 제품군은 다음을 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="d900f-120">Microsoft 365 Defender suite protects:</span></span> 
- <span data-ttu-id="d900f-121">**Endpoint용 Microsoft Defender의** 끝점 - 끝점용 Microsoft Defender는 예방적 보호, 사후 위반 감지, 자동화된 조사 및 대응을 위한 통합된 끝점 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="d900f-121">**Endpoints with Microsoft Defender for Endpoint** - Microsoft Defender for Endpoint is a unified endpoint platform for preventative protection, post-breach detection, automated investigation, and response.</span></span> 
- <span data-ttu-id="d900f-122">**Microsoft Defender for Office 365와의** 전자 메일 및 공동 작업 - Office 365용 Defender는 전자 메일 메시지, 링크(URL) 및 공동 작업 도구로 위협되는 악의적인 위협에 대해 조직을 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="d900f-122">**Email and collaboration with Microsoft Defender for Office 365** - Defender for Office 365 safeguards your organization against malicious threats posed by email messages, links (URLs) and collaboration tools.</span></span> 
- <span data-ttu-id="d900f-123">**ID에 대한 Microsoft Defender 및 Azure AD ID** 보호를 사용하는 ID - ID용 Microsoft Defender는 Active Directory 신호를 사용하여 조직에 대한 고급 위협, 손상된 ID 및 악의적인 내부자 작업을 식별, 감지 및 조사합니다.</span><span class="sxs-lookup"><span data-stu-id="d900f-123">**Identities with Microsoft Defender for Identity and Azure AD Identity Protection** - Microsoft Defender for Identity uses Active Directory signals to identify, detect, and investigate advanced threats, compromised identities, and malicious insider actions directed at your organization.</span></span> 
- <span data-ttu-id="d900f-124">**Microsoft Cloud App security를** 사용하는 응용 프로그램 - Microsoft Cloud App security는 클라우드 앱에 심층 가시성, 강력한 데이터 제어 및 향상된 위협 보호를 가져오는 포괄적인 교차 SaaS 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="d900f-124">**Applications with Microsoft Cloud App security** - Microsoft Cloud App security is a comprehensive cross-SaaS solution bringing deep visibility, strong data controls, and enhanced threat protection to your cloud apps.</span></span> 

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4Bzww] 

<span data-ttu-id="d900f-125">Microsoft 365 Defender의 고유한 제품 간 계층은 개별 제품군 구성 요소를 다음으로 향상합니다.</span><span class="sxs-lookup"><span data-stu-id="d900f-125">Microsoft 365 Defender's unique cross-product layer augments the individual suite components to:</span></span>
- <span data-ttu-id="d900f-126">신호 공유 및 자동화된 작업을 통해 제품군 전체에서 공격으로부터 보호하고 방어 대응을 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="d900f-126">Help protect against attacks and coordinate defensive responses across the suite through signal sharing and automated actions</span></span>
- <span data-ttu-id="d900f-127">경고, 의심스러운 이벤트 및 영향을 미치는 자산을 '인시던트'에 가입하여 보안 팀의 제품 경고, 동작 및 컨텍스트 전반에 걸쳐 공격의 전체 스토리를 내레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="d900f-127">Narrate the full story of the attack across product alerts, behaviors, and context for security teams by joining data on alerts, suspicious events and impacted assets to 'incidents'</span></span>
- <span data-ttu-id="d900f-128">자동화된 수정을 통해 영향을 미치는 자산에 대한 자동 복구를 트리거하여 손상에 대한 대응 자동화</span><span class="sxs-lookup"><span data-stu-id="d900f-128">Automate response to compromise by triggering self-healing for impacted assets through automated remediation</span></span>
- <span data-ttu-id="d900f-129">보안 팀이 끝점 및 Office 데이터에서 자세한 효과적인 위협 헌팅을 수행할 수 있도록 지원</span><span class="sxs-lookup"><span data-stu-id="d900f-129">Enable security teams to perform detailed and effective threat hunting across endpoint and Office data</span></span>

<span data-ttu-id="d900f-130">![인시던트 개요 페이지 이미지](../../media/overview-incident.png)</span><span class="sxs-lookup"><span data-stu-id="d900f-130">![Image of incident overview page](../../media/overview-incident.png)</span></span> <br>
<span data-ttu-id="d900f-131">제품 간 인시던트(개요)</span><span class="sxs-lookup"><span data-stu-id="d900f-131">Cross-product incident (Overview)</span></span>

<span data-ttu-id="d900f-132">![경고 큐의 이미지](../../media/incident-list.png)</span><span class="sxs-lookup"><span data-stu-id="d900f-132">![Image of alerts queue](../../media/incident-list.png)</span></span><br>
<span data-ttu-id="d900f-133">제품군 제품 전반에 걸쳐 단일 인시던트로 상호 연관된 모든 관련 경고(경고 보기)</span><span class="sxs-lookup"><span data-stu-id="d900f-133">All related alerts across the suite products correlated together into a single incident (alerts view)</span></span>

<span data-ttu-id="d900f-134">![인시던트 큐 이미지](../../media/advanced-hunting.png)</span><span class="sxs-lookup"><span data-stu-id="d900f-134">![Image of incident queue](../../media/advanced-hunting.png)</span></span><br>
<span data-ttu-id="d900f-135">전자 메일 및 끝점 원시 데이터를 기반으로 쿼리 기반 헌팅</span><span class="sxs-lookup"><span data-stu-id="d900f-135">Query-based hunting on top of email and endpoint raw data</span></span>


<span data-ttu-id="d900f-136">Microsoft 365 Defender 제품 간 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d900f-136">Microsoft 365 Defender cross-product features include:</span></span> 
- <span data-ttu-id="d900f-137">**제품 간** 단일 창 - 검색, 영향을 미치는 자산, 수행된 자동화된 작업 및 단일 큐의 관련 증거에 대한 모든 정보를 중앙에서 볼 수 [security.microsoft.com.](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="d900f-137">**Cross-product single pane of glass** - Central view all information for detections, impacted assets, automated actions taken, and related evidence in a single queue and a single pane in [security.microsoft.com](https://security.microsoft.com).</span></span> 
- <span data-ttu-id="d900f-138">**결합된** 인시던트 큐 - 전체 공격 범위를 보장하여 보안 전문가가 중요한 작업에 집중할 수 있도록 영향을 미치는 자산 및 자동화된 수정 작업이 그룹화되어 시기적합한 방식으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d900f-138">**Combined incidents queue** - To help security professionals focus on what is critical by ensuring the full attack scope, impacted assets and automated remediation actions are grouped together and surfaced in a timely manner.</span></span> 
- <span data-ttu-id="d900f-139">**위협에 대한** 자동 대응 - Microsoft 365 Defender 제품 간에 실시간으로 중요한 위협 정보를 공유하여 공격 진행을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="d900f-139">**Automatic response to threats** - Critical threat information is shared in real time between the Microsoft 365 Defender products to help stop the progression of an attack.</span></span> <span data-ttu-id="d900f-140">예를 들어 끝점용 Microsoft Defender에서 보호하는 끝점에서 악성 파일이 감지되면 Office 365용 Defender에 모든 전자 메일 메시지에서 파일을 검색하고 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d900f-140">For example, if a malicious file is detected on an endpoint protected by Microsoft Defender for Endpoint, it will instruct Defender for Office 365 to scan and remove the file from all e-mail messages.</span></span> <span data-ttu-id="d900f-141">이 파일은 전체 Microsoft 365 보안 제품군에 의해 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="d900f-141">The file will be blocked on sight by the entire Microsoft 365 security suite.</span></span>
- <span data-ttu-id="d900f-142">**손상된 장치,** 사용자 ID 및 사서함에 대한 자체 복구 - Microsoft 365 Defender는 AI 기반 자동 작업 및 플레이북을 사용하여 영향을 받는 자산을 안전한 상태로 다시 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="d900f-142">**Self-healing for compromised devices, user identities, and mailboxes** - Microsoft 365 Defender uses AI-powered automatic actions and playbooks to remediate impacted assets back to a secure state.</span></span> <span data-ttu-id="d900f-143">Microsoft 365 Defender는 제품군 제품의 자동 수정 기능을 활용하여 인시던트와 관련된 모든 영향을 미치는 자산이 가능한 경우 자동으로 수정되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d900f-143">Microsoft 365 Defender leverages automatic remediation capabilities of the suite products to ensure all impacted assets related to an incident are automatically remediated where possible.</span></span>
- <span data-ttu-id="d900f-144">**제품** 간 위협 헌팅 - 보안 팀은 다양한 보호 제품에서 수집한 원시 데이터에 대해 자체 사용자 지정 쿼리를 만들어 고유한 조직 지식을 활용하여 손상 징후를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d900f-144">**Cross-product threat hunting** - Security teams can leverage their unique organizational knowledge to hunt for signs of compromise by creating their own custom queries over the raw data collected by the various protection products.</span></span> <span data-ttu-id="d900f-145">Microsoft 365 Defender는 끝점 및 Office 365용 Microsoft Defender 데이터에서 30일 동안의 기록 원시 신호 및 경고 데이터에 대한 쿼리 기반 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d900f-145">Microsoft 365 Defender provides query-based access to 30 days of historic raw signals and alert data across endpoint and Microsoft Defender for Office 365 data.</span></span> 


## <a name="get-started"></a><span data-ttu-id="d900f-146">시작하기</span><span class="sxs-lookup"><span data-stu-id="d900f-146">Get started</span></span>
<span data-ttu-id="d900f-147">의 Microsoft 365 보안 센터에서 서비스를 사용하도록 설정하려면 먼저 Microsoft 365 Defender 라이선스 요구 [사항을 security.microsoft.com.](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="d900f-147">Microsoft 365 Defender licensing requirements must be met before you can enable the service in the Microsoft 365 security center at [security.microsoft.com](https://security.microsoft.com).</span></span> <span data-ttu-id="d900f-148">자세한 내용은 다음을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d900f-148">For more information, read:</span></span>
- [<span data-ttu-id="d900f-149">라이선스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="d900f-149">Licensing requirements</span></span>](prerequisites.md#licensing-requirements)
- [<span data-ttu-id="d900f-150">Microsoft 365 Defender 켜기</span><span class="sxs-lookup"><span data-stu-id="d900f-150">Turn on Microsoft 365 Defender</span></span>](m365d-enable.md)
