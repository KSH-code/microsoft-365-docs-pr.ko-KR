---
title: 위협 방지(Windows 10)
description: 엔드포인트용 Microsoft Defender는 예방적 보호, 침해 후 감지, 자동화된 조사 및 대응을 위한 통합 플랫폼입니다.
keywords: 위협 방지, 끝점용 Microsoft Defender, 공격 표면 감소, 차세대 보호, 끝점 감지 및 대응, 자동화된 조사 및 대응, Microsoft 위협 전문가, 장치용 Microsoft 보안 점수, 고급 헌팅, 사이버 위협 헌팅, 웹 위협 방지
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: 3098c2786874650ad14d226beacd5ec760decef0
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934936"
---
# <a name="threat-protection"></a><span data-ttu-id="df79e-104">위협 방지</span><span class="sxs-lookup"><span data-stu-id="df79e-104">Threat Protection</span></span>
<span data-ttu-id="df79e-105">[엔드포인트용 Microsoft Defender](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection)는 예방적 보호, 침해 후 감지, 자동화된 조사 및 대응을 위한 통합 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="df79e-105">[Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection) is a unified platform for preventative protection, post-breach detection, automated investigation, and response.</span></span> <span data-ttu-id="df79e-106">Endpoint용 Defender는 사이버 위협으로부터 끝점을 보호하고, 고급 공격 및 데이터 위반을 감지하고, 보안 인시던트를 자동화하며, 보안 입장을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="df79e-106">Defender for Endpoint protects endpoints from cyber threats, detects advanced attacks and data breaches, automates security incidents, and improves security posture.</span></span>

> [!TIP]
> <span data-ttu-id="df79e-107">사용자가 클라우드 서비스 및 사내 응용 프로그램에 쉽게 액세스할 수 있도록 지원하고 모든 장치에 대한 최신 관리 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df79e-107">Enable your users to access cloud services and on-premises applications with ease and enable modern management capabilities for all devices.</span></span> <span data-ttu-id="df79e-108">자세한 내용은 원격 인력 [보호를 참조하세요.](https://docs.microsoft.com/enterprise-mobility-security/remote-work/)</span><span class="sxs-lookup"><span data-stu-id="df79e-108">For more information, see [Secure your remote workforce](https://docs.microsoft.com/enterprise-mobility-security/remote-work/).</span></span> 

<center><h2><span data-ttu-id="df79e-109">엔드포인트용 Microsoft Defender</center></span><span class="sxs-lookup"><span data-stu-id="df79e-109">Microsoft Defender for Endpoint</center></span></span></h2>
<table>
<tr>
<td><a href="#tvm"><center><img src="images/TVM_icon.png" alt="threat and vulnerability icon"> <br><span data-ttu-id="df79e-110"><b>위협 & 취약성 관리</b></center></a></span><span class="sxs-lookup"><span data-stu-id="df79e-110"><b>Threat & vulnerability management</b></center></a></span></span></td>
<td><a href="#asr"><center><img src="images/asr-icon.png" alt="attack surface reduction icon"> <br><span data-ttu-id="df79e-111"><b>공격 표면 감소</b></center></a></span><span class="sxs-lookup"><span data-stu-id="df79e-111"><b>Attack surface reduction</b></center></a></span></span></td>
<td><center><a href="#ngp"><img src="images/ngp-icon.png" alt="next generation protection icon"><br> <span data-ttu-id="df79e-112"><b>차세대 보호</b></a></center></span><span class="sxs-lookup"><span data-stu-id="df79e-112"><b>Next-generation protection</b></a></center></span></span></td>
<td><center><a href="#edr"><img src="images/edr-icon.png" alt="endpoint detection and response icon"><br> <span data-ttu-id="df79e-113"><b>끝점 검색 및 응답</b></a></center></span><span class="sxs-lookup"><span data-stu-id="df79e-113"><b>Endpoint detection and response</b></a></center></span></span></td>
<td><center><a href="#ai"><img src="images/air-icon.png" alt="automated investigation and remediation icon"><br> <span data-ttu-id="df79e-114"><b>자동화된 조사 및 수정</b></a></center></span><span class="sxs-lookup"><span data-stu-id="df79e-114"><b>Automated investigation and remediation</b></a></center></span></span></td>
<td><center><a href="#mte"><img src="images/mte-icon.png" alt="microsoft threat experts icon"><br> <span data-ttu-id="df79e-115"><b>Microsoft 위협 전문가</b></a></center></span><span class="sxs-lookup"><span data-stu-id="df79e-115"><b>Microsoft Threat Experts</b></a></center></span></span></td>
</tr>
<tr>
<td colspan="7"><span data-ttu-id="df79e-116">
<a href="#apis"><center><b>중앙 집중식 구성 및 관리, API</a></span><span class="sxs-lookup"><span data-stu-id="df79e-116">
<a href="#apis"><center><b>Centralized configuration and administration, APIs</a></span></span></b></center></td>
</tr>
<tr>
<td colspan="7"><span data-ttu-id="df79e-117"><a href="#mtp"><center><b>Microsoft 365 Defender</a></span><span class="sxs-lookup"><span data-stu-id="df79e-117"><a href="#mtp"><center><b>Microsoft 365 Defender</a></span></span></center></b></td>
</tr>
</table>
<br>

<a name="tvm"></a>


>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4obJq]

<span data-ttu-id="df79e-118">**[위협 및 취약성 관리](next-gen-threat-and-vuln-mgt.md)**</span><span class="sxs-lookup"><span data-stu-id="df79e-118">**[Threat & vulnerability management](next-gen-threat-and-vuln-mgt.md)**</span></span><br>
<span data-ttu-id="df79e-119">이 기본 제공 기능은 게임이 변화하는 위험 기반 접근 방식을 사용하여 끝점 취약성 및 잘못 구성을 검색, 우선 순위 지정 및 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="df79e-119">This built-in capability uses a game-changing risk-based approach to the discovery, prioritization, and remediation of endpoint vulnerabilities and misconfigurations.</span></span>

- [<span data-ttu-id="df79e-120">위협 & 관리 개요</span><span class="sxs-lookup"><span data-stu-id="df79e-120">Threat & vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="df79e-121">시작</span><span class="sxs-lookup"><span data-stu-id="df79e-121">Get started</span></span>](tvm-prerequisites.md)
- [<span data-ttu-id="df79e-122">보안 설정 액세스</span><span class="sxs-lookup"><span data-stu-id="df79e-122">Access your security posture</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="df79e-123">보안 자세를 개선하고 위험을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="df79e-123">Improve your security posture and reduce risk</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="df79e-124">장치의 취약성 이해</span><span class="sxs-lookup"><span data-stu-id="df79e-124">Understand vulnerabilities on your devices</span></span>](tvm-software-inventory.md)

<a name="asr"></a>

<span data-ttu-id="df79e-125">**[공격 표면 감소](overview-attack-surface-reduction.md)**</span><span class="sxs-lookup"><span data-stu-id="df79e-125">**[Attack surface reduction](overview-attack-surface-reduction.md)**</span></span><br>
<span data-ttu-id="df79e-126">공격 표면 감소 기능 집합은 스택의 첫 번째 방어 선을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="df79e-126">The attack surface reduction set of capabilities provide the first line of defense in the stack.</span></span> <span data-ttu-id="df79e-127">구성 설정이 올바르게 설정되고 악용 완화 기술이 적용되었는지 확인하여 이러한 기능 집합은 공격 및 악용을 저항합니다.</span><span class="sxs-lookup"><span data-stu-id="df79e-127">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, these set of capabilities resist attacks and exploitation.</span></span>

- [<span data-ttu-id="df79e-128">하드웨어 기반의 고리</span><span class="sxs-lookup"><span data-stu-id="df79e-128">Hardware based isolation</span></span>](overview-hardware-based-isolation.md)
- [<span data-ttu-id="df79e-129">응용 프로그램 제어</span><span class="sxs-lookup"><span data-stu-id="df79e-129">Application control</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)
- [<span data-ttu-id="df79e-130">장치 제어</span><span class="sxs-lookup"><span data-stu-id="df79e-130">Device control</span></span>](https://docs.microsoft.com/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control)
- [<span data-ttu-id="df79e-131">악용 방지</span><span class="sxs-lookup"><span data-stu-id="df79e-131">Exploit protection</span></span>](exploit-protection.md)
- <span data-ttu-id="df79e-132">[네트워크 보호,](network-protection.md) [웹 보호](web-protection-overview.md)</span><span class="sxs-lookup"><span data-stu-id="df79e-132">[Network protection](network-protection.md), [web protection](web-protection-overview.md)</span></span>
- [<span data-ttu-id="df79e-133">제어된 폴더 액세스</span><span class="sxs-lookup"><span data-stu-id="df79e-133">Controlled folder access</span></span>](controlled-folders.md)
- [<span data-ttu-id="df79e-134">네트워크 방화벽</span><span class="sxs-lookup"><span data-stu-id="df79e-134">Network firewall</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)
- [<span data-ttu-id="df79e-135">공격 표면 감소 규칙</span><span class="sxs-lookup"><span data-stu-id="df79e-135">Attack surface reduction rules</span></span>](attack-surface-reduction.md)

<a name="ngp"></a>

<span data-ttu-id="df79e-136">**[차세대 보호](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**</span><span class="sxs-lookup"><span data-stu-id="df79e-136">**[Next-generation protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**</span></span><br>
<span data-ttu-id="df79e-137">네트워크의 보안 경계를 더욱 강화하기 위해 끝점용 Microsoft Defender는 모든 유형의 새로운 위협을 감지하도록 설계된 차세대 보호를 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="df79e-137">To further reinforce the security perimeter of your network, Microsoft Defender for Endpoint uses next-generation protection designed to catch all types of emerging threats.</span></span>

- [<span data-ttu-id="df79e-138">동작 모니터링</span><span class="sxs-lookup"><span data-stu-id="df79e-138">Behavior monitoring</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)
- [<span data-ttu-id="df79e-139">클라우드 기반 보호</span><span class="sxs-lookup"><span data-stu-id="df79e-139">Cloud-based protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-protection-features-microsoft-defender-antivirus)
- [<span data-ttu-id="df79e-140">기계 학습</span><span class="sxs-lookup"><span data-stu-id="df79e-140">Machine learning</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)
- [<span data-ttu-id="df79e-141">URL 보호</span><span class="sxs-lookup"><span data-stu-id="df79e-141">URL Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)
- [<span data-ttu-id="df79e-142">자동화된 샌드박스 서비스</span><span class="sxs-lookup"><span data-stu-id="df79e-142">Automated sandbox service</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)

<a name="edr"></a>

<span data-ttu-id="df79e-143">**[엔드포인트 검색 및 대응](overview-endpoint-detection-response.md)**</span><span class="sxs-lookup"><span data-stu-id="df79e-143">**[Endpoint detection and response](overview-endpoint-detection-response.md)**</span></span><br>
<span data-ttu-id="df79e-144">끝점 감지 및 대응 기능은 침입 시도 및 활성 위반을 감지, 조사 및 대응하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="df79e-144">Endpoint detection and response capabilities are put in place to detect, investigate, and respond to intrusion attempts and active breaches.</span></span> <span data-ttu-id="df79e-145">고급 헌팅을 사용하면 위반을 사전 예방적으로 찾고 사용자 지정 검색을 만들 수 있는 쿼리 기반 위협 헌팅 도구가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df79e-145">With Advanced hunting, you have a query-based threat-hunting tool that lets your proactively find breaches and create custom detections.</span></span>

- [<span data-ttu-id="df79e-146">경고</span><span class="sxs-lookup"><span data-stu-id="df79e-146">Alerts</span></span>](alerts-queue.md)
- [<span data-ttu-id="df79e-147">기록 끝점 데이터</span><span class="sxs-lookup"><span data-stu-id="df79e-147">Historical endpoint data</span></span>](investigate-machines.md#timeline)
- [<span data-ttu-id="df79e-148">응답 오케스트레이션</span><span class="sxs-lookup"><span data-stu-id="df79e-148">Response orchestration</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)
- [<span data-ttu-id="df79e-149">포렌식 컬렉션</span><span class="sxs-lookup"><span data-stu-id="df79e-149">Forensic collection</span></span>](respond-machine-alerts.md#collect-investigation-package-from-devices)
- [<span data-ttu-id="df79e-150">위협 인텔리전스</span><span class="sxs-lookup"><span data-stu-id="df79e-150">Threat intelligence</span></span>](threat-indicator-concepts.md)
- [<span data-ttu-id="df79e-151">고급 검색 및 분석 서비스</span><span class="sxs-lookup"><span data-stu-id="df79e-151">Advanced detonation and analysis service</span></span>](respond-file-alerts.md#deep-analysis)
- [<span data-ttu-id="df79e-152">지능형 헌팅</span><span class="sxs-lookup"><span data-stu-id="df79e-152">Advanced hunting</span></span>](advanced-hunting-overview.md)
    - [<span data-ttu-id="df79e-153">사용자 지정 검색</span><span class="sxs-lookup"><span data-stu-id="df79e-153">Custom detections</span></span>](overview-custom-detections.md)

<a name="ai"></a>

<span data-ttu-id="df79e-154">**[자동화된 조사 및 수정](automated-investigations.md)**</span><span class="sxs-lookup"><span data-stu-id="df79e-154">**[Automated investigation and remediation](automated-investigations.md)**</span></span><br>
<span data-ttu-id="df79e-155">Microsoft Defender for Endpoint는 고급 공격에 빠르게 대응할 뿐만 아니라 대규모로 경고 볼륨을 분당 줄이는 데 도움이 되는 자동 조사 및 수정 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="df79e-155">In addition to quickly responding to advanced attacks, Microsoft Defender for Endpoint offers automatic investigation and remediation capabilities that help reduce the volume of alerts in minutes at scale.</span></span>

- [<span data-ttu-id="df79e-156">자동화된 조사 및 수정</span><span class="sxs-lookup"><span data-stu-id="df79e-156">Automated investigation and remediation</span></span>](automated-investigations.md)
- [<span data-ttu-id="df79e-157">자동화된 조사의 세부 정보 및 결과 보기</span><span class="sxs-lookup"><span data-stu-id="df79e-157">View details and results of automated investigations</span></span>](auto-investigation-action-center.md)
- [<span data-ttu-id="df79e-158">수정 조치 보기 및 승인</span><span class="sxs-lookup"><span data-stu-id="df79e-158">View and approve remediation actions</span></span>](manage-auto-investigation.md)

<a name="mte"></a>

<span data-ttu-id="df79e-159">**[Microsoft 위협 전문가](microsoft-threat-experts.md)**</span><span class="sxs-lookup"><span data-stu-id="df79e-159">**[Microsoft Threat Experts](microsoft-threat-experts.md)**</span></span><br>
<span data-ttu-id="df79e-160">끝점용 Microsoft Defender의 새로운 관리되는 위협 헌팅 서비스는 사전 헌팅, 우선 순위 지정 및 추가 컨텍스트 및 인사이트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="df79e-160">Microsoft Defender for Endpoint's new managed threat hunting service provides proactive hunting, prioritization, and additional context and insights.</span></span> <span data-ttu-id="df79e-161">Microsoft 위협 전문가는 SOC(보안 운영 센터)에서 위협을 빠르고 정확하게 식별하고 대응할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="df79e-161">Microsoft Threat Experts further empowers Security Operation Centers (SOCs) to identify and respond to threats quickly and accurately.</span></span>

- [<span data-ttu-id="df79e-162">대상 공격 알림</span><span class="sxs-lookup"><span data-stu-id="df79e-162">Targeted attack notification</span></span>](microsoft-threat-experts.md)
- [<span data-ttu-id="df79e-163">전문가가 요구하는 경우</span><span class="sxs-lookup"><span data-stu-id="df79e-163">Experts-on-demand</span></span>](microsoft-threat-experts.md)
- [<span data-ttu-id="df79e-164">Microsoft 365 Defender 관리 헌팅 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="df79e-164">Configure your Microsoft 365 Defender managed hunting service</span></span>](configure-microsoft-threat-experts.md)

<a name="apis"></a>

<span data-ttu-id="df79e-165">**[중앙 집중식 구성 및 관리, API](management-apis.md)**</span><span class="sxs-lookup"><span data-stu-id="df79e-165">**[Centralized configuration and administration, APIs](management-apis.md)**</span></span><br>
<span data-ttu-id="df79e-166">끝점용 Microsoft Defender를 기존 워크플로에 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="df79e-166">Integrate Microsoft Defender for Endpoint into your existing workflows.</span></span>
- [<span data-ttu-id="df79e-167">온보딩</span><span class="sxs-lookup"><span data-stu-id="df79e-167">Onboarding</span></span>](onboard-configure.md)
- [<span data-ttu-id="df79e-168">API 및 SIEM 통합</span><span class="sxs-lookup"><span data-stu-id="df79e-168">API and SIEM integration</span></span>](configure-siem.md)
- [<span data-ttu-id="df79e-169">노출된 API</span><span class="sxs-lookup"><span data-stu-id="df79e-169">Exposed APIs</span></span>](apis-intro.md)
- [<span data-ttu-id="df79e-170">역할 기반 액세스 컨트롤(RBAC)</span><span class="sxs-lookup"><span data-stu-id="df79e-170">Role-based access control (RBAC)</span></span>](rbac.md)
- [<span data-ttu-id="df79e-171">보고 및 추세</span><span class="sxs-lookup"><span data-stu-id="df79e-171">Reporting and trends</span></span>](threat-protection-reports.md)

<a name="integration"></a>
<span data-ttu-id="df79e-172">**[Microsoft 솔루션과의 통합](threat-protection-integration.md)**</span><span class="sxs-lookup"><span data-stu-id="df79e-172">**[Integration with Microsoft solutions](threat-protection-integration.md)**</span></span> <br>
 <span data-ttu-id="df79e-173">끝점용 Microsoft Defender는 다음을 비롯한 다양한 Microsoft 솔루션과 직접 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="df79e-173">Microsoft Defender for Endpoint directly integrates with various Microsoft solutions, including:</span></span>
- <span data-ttu-id="df79e-174">Intune</span><span class="sxs-lookup"><span data-stu-id="df79e-174">Intune</span></span>
- <span data-ttu-id="df79e-175">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="df79e-175">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="df79e-176">ID용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="df79e-176">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="df79e-177">Azure Defender</span><span class="sxs-lookup"><span data-stu-id="df79e-177">Azure Defender</span></span>
- <span data-ttu-id="df79e-178">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="df79e-178">Skype for Business</span></span>
- <span data-ttu-id="df79e-179">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="df79e-179">Microsoft Cloud App Security</span></span>

<a name="mtp"></a>
<span data-ttu-id="df79e-180">**[Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)**</span><span class="sxs-lookup"><span data-stu-id="df79e-180">**[Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)**</span></span><br>
 <span data-ttu-id="df79e-181">Microsoft 365 Defender를 통해 엔드포인트용 Microsoft Defender 및 다양한 Microsoft 보안 솔루션은 엔드포인트, ID, 전자 메일 및 응용 프로그램 전반에 걸쳐 기본적으로 통합되는 통합 사전 및 사후 침해 엔터프라이즈 방어 제품군을 형성하여 정교한 공격을 감지, 방지, 조사 및 자동으로 대응합니다.</span><span class="sxs-lookup"><span data-stu-id="df79e-181">With Microsoft 365 Defender, Microsoft Defender for Endpoint and various Microsoft security solutions form a unified pre- and post-breach enterprise defense suite that natively integrates across endpoint, identity, email, and applications to detect, prevent, investigate, and automatically respond to sophisticated attacks.</span></span>
