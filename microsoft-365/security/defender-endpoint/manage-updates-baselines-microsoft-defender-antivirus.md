---
title: 업데이트 Microsoft Defender 바이러스 백신 관리하고 기준 적용
description: 보호 및 Microsoft Defender 바이러스 백신 받는 방법을 관리합니다.
keywords: 업데이트, 보안 기준, 보호, 업데이트 예약, 강제 업데이트, 모바일 업데이트, wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr, mkaminska
manager: dansimp
ms.technology: mde
ms.date: 07/06/2021
ms.openlocfilehash: f64c71501a550aabdf16b9de2d7a5db93e48caef
ms.sourcegitcommit: 8b0718f5607ab509092cb80bda854010d885c54f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/07/2021
ms.locfileid: "53314467"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="e4318-104">업데이트 Microsoft Defender 바이러스 백신 관리하고 기준 적용</span><span class="sxs-lookup"><span data-stu-id="e4318-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="e4318-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="e4318-105">**Applies to:**</span></span>

- [<span data-ttu-id="e4318-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e4318-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="e4318-107">Windows Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="e4318-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="e4318-108">최신 Microsoft Defender 바이러스 백신 유지하는 것은 장치에 새로운 맬웨어 및 공격 기술로부터 보호하는 데 필요한 최신 기술 및 기능을 유지하는 데 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="e4318-108">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span> <span data-ttu-id="e4318-109">수동 모드에서 실행 중인 경우에도 바이러스 Microsoft Defender 바이러스 백신 [업데이트해야 합니다.](microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="e4318-109">Make sure to update your antivirus protection, even if Microsoft Defender Antivirus is running in [passive mode](microsoft-defender-antivirus-compatibility.md).</span></span> <span data-ttu-id="e4318-110">최신 업데이트와 관련된 두 가지 유형의 업데이트가 Microsoft Defender 바이러스 백신 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4318-110">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="e4318-111">보안 인텔리전스 업데이트</span><span class="sxs-lookup"><span data-stu-id="e4318-111">Security intelligence updates</span></span>
- <span data-ttu-id="e4318-112">제품 업데이트</span><span class="sxs-lookup"><span data-stu-id="e4318-112">Product updates</span></span>

> [!TIP]
> <span data-ttu-id="e4318-113">최신 엔진, 플랫폼 및 서명 날짜를 확인한 다음 Microsoft Defender 바이러스 백신 Microsoft 맬웨어 방지에 대한 보안 인텔리전스 업데이트를 [방문하세요.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="e4318-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="e4318-114">보안 인텔리전스 업데이트</span><span class="sxs-lookup"><span data-stu-id="e4318-114">Security intelligence updates</span></span>

<span data-ttu-id="e4318-115">Microsoft Defender 바이러스 백신 Microsoft Advanced [](cloud-protection-microsoft-defender-antivirus.md) Protection Service 또는 MAPS라고도 하는 클라우드 제공 보호를 사용하며 보안 인텔리전스 업데이트를 주기적으로 다운로드하여 보호 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e4318-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="e4318-116">업데이트는 아래 KB 번호에 따라 릴리스됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4318-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="e4318-117">Microsoft Defender 바이러스 백신: KB2267602</span><span class="sxs-lookup"><span data-stu-id="e4318-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="e4318-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="e4318-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="e4318-119">클라우드 제공 보호는 항상 설정되어 있으며 인터넷에 대한 활성 연결이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e4318-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="e4318-120">보안 인텔리전스 업데이트는 예약된 일정에 따라 발생합니다(정책을 통해 구성 가능).</span><span class="sxs-lookup"><span data-stu-id="e4318-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="e4318-121">자세한 내용은 에서 Microsoft 클라우드 제공 보호 [Microsoft Defender 바이러스 백신.](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="e4318-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="e4318-122">최신 보안 인텔리전스 업데이트 목록은 보안 인텔리전스 업데이트 및 Microsoft Defender 바이러스 백신 [맬웨어 방지를 참조하세요.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="e4318-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="e4318-123">엔진 업데이트는 보안 인텔리전스 업데이트에 포함되어 있으며 월별 케이던스에 릴리스됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4318-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="e4318-124">제품 업데이트</span><span class="sxs-lookup"><span data-stu-id="e4318-124">Product updates</span></span>

<span data-ttu-id="e4318-125">Microsoft Defender 바이러스 백신 업데이트라고 하는 월별 [업데이트(KB4052623)가](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) *필요합니다.*</span><span class="sxs-lookup"><span data-stu-id="e4318-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) known as *platform updates*.</span></span>

<span data-ttu-id="e4318-126">다음 방법 중 하나를 통해 업데이트 배포를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4318-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="e4318-127">Windows WSUS(서버 업데이트 서비스)</span><span class="sxs-lookup"><span data-stu-id="e4318-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="e4318-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="e4318-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="e4318-129">Microsoft를 배포하고 네트워크의 끝점에 Windows 배포하는 데 사용하는 일반적인 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="e4318-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="e4318-130">자세한 내용은 [Manage the sources for Microsoft Defender 바이러스 백신 protection updates를 참조하십시오.](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)</span><span class="sxs-lookup"><span data-stu-id="e4318-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> - <span data-ttu-id="e4318-131">월별 업데이트는 단계적으로 릴리스되어 Window Server Update Services에 여러 [패키지가 표시됩니다.](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)</span><span class="sxs-lookup"><span data-stu-id="e4318-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>
> - <span data-ttu-id="e4318-132">이 문서에는 광범위한 릴리스 채널에 포함된 변경 내용이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4318-132">This article lists changes that are included in the broad release channel.</span></span> <span data-ttu-id="e4318-133">[여기에서 최신 광범위 채널 릴리스를 참조하세요.](https://www.microsoft.com/security/encyclopedia/adlpackages.aspx?action=info)</span><span class="sxs-lookup"><span data-stu-id="e4318-133">[See the latest broad channel release here](https://www.microsoft.com/security/encyclopedia/adlpackages.aspx?action=info).</span></span> 
> - <span data-ttu-id="e4318-134">단계적 출시 프로세스에 대한 자세한 내용을 알아보고 다음 릴리스에 대한 자세한 내용은 Microsoft Defender 업데이트에 대한 단계적 출시 프로세스 관리를 [참조하세요.](manage-gradual-rollout.md)</span><span class="sxs-lookup"><span data-stu-id="e4318-134">To learn more about the gradual rollout process, and to see more information about the next release, see [Manage the gradual rollout process for Microsoft Defender updates](manage-gradual-rollout.md).</span></span>
> - <span data-ttu-id="e4318-135">보안 인텔리전스 업데이트에 대한 자세한 내용은 보안 인텔리전스 업데이트 및 Microsoft Defender 바이러스 백신 Microsoft 맬웨어 [방지를 참조하세요.](https://www.microsoft.com/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="e4318-135">To learn more about security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/wdsi/defenderupdates).</span></span> 

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="e4318-136">월별 플랫폼 및 엔진 버전</span><span class="sxs-lookup"><span data-stu-id="e4318-136">Monthly platform and engine versions</span></span>

<span data-ttu-id="e4318-137">플랫폼 업데이트를 업데이트하거나 설치하는 방법에 대한 자세한 내용은 Windows Defender 맬웨어 방지 플랫폼용 업데이트를 [참조하세요.](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)</span><span class="sxs-lookup"><span data-stu-id="e4318-137">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="e4318-138">모든 업데이트에 포함</span><span class="sxs-lookup"><span data-stu-id="e4318-138">All our updates contain</span></span> 
- <span data-ttu-id="e4318-139">성능 개선</span><span class="sxs-lookup"><span data-stu-id="e4318-139">performance improvements;</span></span>
- <span data-ttu-id="e4318-140">서비스성 개선 및</span><span class="sxs-lookup"><span data-stu-id="e4318-140">serviceability improvements; and</span></span> 
- <span data-ttu-id="e4318-141">통합 개선(클라우드, [](/microsoft-365/security/defender/microsoft-365-defender)Microsoft 365 Defender).</span><span class="sxs-lookup"><span data-stu-id="e4318-141">integration improvements (Cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="e4318-142">2021년 6월(플랫폼: 4.18.2106.5 | 엔진: 1.1.18300.4)</span><span class="sxs-lookup"><span data-stu-id="e4318-142">June-2021 (Platform: 4.18.2106.5 | Engine: 1.1.18300.4)</span></span></summary>

<span data-ttu-id="e4318-143">&ensp;보안 인텔리전스 업데이트 버전: **1.343.17.0**</span><span class="sxs-lookup"><span data-stu-id="e4318-143">&ensp;Security intelligence update version: **1.343.17.0**</span></span>  
<span data-ttu-id="e4318-144">&ensp;릴리스: **2021년 6월 28일**</span><span class="sxs-lookup"><span data-stu-id="e4318-144">&ensp;Released: **June 28, 2021**</span></span>  
<span data-ttu-id="e4318-145">&ensp;플랫폼: **4.18.2106.5**</span><span class="sxs-lookup"><span data-stu-id="e4318-145">&ensp;Platform: **4.18.2106.5**</span></span>  
<span data-ttu-id="e4318-146">&ensp;엔진: **1.1.18300.4**</span><span class="sxs-lookup"><span data-stu-id="e4318-146">&ensp;Engine: **1.1.18300.4**</span></span>  
<span data-ttu-id="e4318-147">&ensp;지원 단계: **보안 및 중요 업데이트**</span><span class="sxs-lookup"><span data-stu-id="e4318-147">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e4318-148">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="e4318-148">What's new</span></span>
- <span data-ttu-id="e4318-149">Microsoft Defender 업데이트의점적 출시 프로세스를 관리하기 위한 새로운 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="e4318-149">New controls for managing the gradual rollout process of Microsoft Defender updates.</span></span> <span data-ttu-id="e4318-150">Microsoft Defender 업데이트에 대한 서진적 출시 프로세스 [관리를 참조하세요.](manage-gradual-rollout.md)</span><span class="sxs-lookup"><span data-stu-id="e4318-150">See [Manage the gradual rollout process for Microsoft Defender updates](manage-gradual-rollout.md).</span></span>
- <span data-ttu-id="e4318-151">동작 모니터링 엔진 개선</span><span class="sxs-lookup"><span data-stu-id="e4318-151">Improvement to the behavior monitoring engine</span></span>
- <span data-ttu-id="e4318-152">맬웨어 방지 정의의 롤아웃 개선</span><span class="sxs-lookup"><span data-stu-id="e4318-152">Improvements to the rollout of antimalware definitions</span></span>
- <span data-ttu-id="e4318-153">확장 에지 네트워크 이벤트 검사</span><span class="sxs-lookup"><span data-stu-id="e4318-153">Extended Edge network event inspections</span></span>

### <a name="known-issues"></a><span data-ttu-id="e4318-154">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="e4318-154">Known Issues</span></span>
<span data-ttu-id="e4318-155">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="e4318-155">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="e4318-156">2021년 5월(플랫폼: 4.18.2105.4 | 엔진: 1.1.18200.4)</span><span class="sxs-lookup"><span data-stu-id="e4318-156">May-2021 (Platform: 4.18.2105.4 | Engine: 1.1.18200.4)</span></span></summary>

<span data-ttu-id="e4318-157">&ensp;보안 인텔리전스 업데이트 버전: **1.341.8.0**</span><span class="sxs-lookup"><span data-stu-id="e4318-157">&ensp;Security intelligence update version: **1.341.8.0**</span></span>  
<span data-ttu-id="e4318-158">&ensp;릴리스: **2021년 6월 3일**</span><span class="sxs-lookup"><span data-stu-id="e4318-158">&ensp;Released: **June 3, 2021**</span></span>  
<span data-ttu-id="e4318-159">&ensp;플랫폼: **4.18.2105.4**</span><span class="sxs-lookup"><span data-stu-id="e4318-159">&ensp;Platform: **4.18.2105.4**</span></span>  
<span data-ttu-id="e4318-160">&ensp;엔진: **1.1.18200.4**</span><span class="sxs-lookup"><span data-stu-id="e4318-160">&ensp;Engine: **1.1.18200.4**</span></span>  
<span data-ttu-id="e4318-161">&ensp;지원 단계: **보안 및 중요 업데이트**</span><span class="sxs-lookup"><span data-stu-id="e4318-161">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e4318-162">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="e4318-162">What's new</span></span>
- <span data-ttu-id="e4318-163">동작 모니터링 [개선](client-behavioral-blocking.md)</span><span class="sxs-lookup"><span data-stu-id="e4318-163">Improvements to [behavior monitoring](client-behavioral-blocking.md)</span></span> 
- <span data-ttu-id="e4318-164">고정 [네트워크 보호](network-protection.md) 알림 필터링 기능</span><span class="sxs-lookup"><span data-stu-id="e4318-164">Fixed [network protection](network-protection.md) notification filtering feature</span></span>

### <a name="known-issues"></a><span data-ttu-id="e4318-165">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="e4318-165">Known Issues</span></span>
<span data-ttu-id="e4318-166">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="e4318-166">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="e4318-167">2021년 4월(플랫폼: 4.18.2104.14 | 엔진: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="e4318-167">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="e4318-168">&ensp;보안 인텔리전스 업데이트 버전: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="e4318-168">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="e4318-169">&ensp;릴리스: **2021년 4월 26일(엔진:**  1.1.18100.6 릴리스 2021년 5월 5일) &ensp; 플랫폼: **4.18.2104.14**</span><span class="sxs-lookup"><span data-stu-id="e4318-169">&ensp;Released: **April 26, 2021**  (Engine: 1.1.18100.6 released May 5, 2021) &ensp;Platform: **4.18.2104.14**</span></span>  
<span data-ttu-id="e4318-170">&ensp;엔진: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="e4318-170">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="e4318-171">&ensp;지원 단계: **보안 및 중요 업데이트**</span><span class="sxs-lookup"><span data-stu-id="e4318-171">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e4318-172">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="e4318-172">What's new</span></span>
- <span data-ttu-id="e4318-173">추가 동작 모니터링 논리</span><span class="sxs-lookup"><span data-stu-id="e4318-173">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="e4318-174">커널 모드 키 로거 검색 개선</span><span class="sxs-lookup"><span data-stu-id="e4318-174">Improved kernel mode key logger detection</span></span>
- <span data-ttu-id="e4318-175">Microsoft Defender 업데이트의점적 출시 프로세스를 관리하기 위한 새 [컨트롤이 추가되었습니다.](manage-gradual-rollout.md)</span><span class="sxs-lookup"><span data-stu-id="e4318-175">Added new controls to manage the gradual rollout process for [Microsoft Defender updates](manage-gradual-rollout.md)</span></span>


### <a name="known-issues"></a><span data-ttu-id="e4318-176">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="e4318-176">Known Issues</span></span>
<span data-ttu-id="e4318-177">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="e4318-177">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="e4318-178">이전 버전 업데이트: 기술 업그레이드 지원만</span><span class="sxs-lookup"><span data-stu-id="e4318-178">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="e4318-179">새 패키지 버전이 출시된 후 이전 두 버전에 대한 지원은 기술 지원으로만 축소됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4318-179">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="e4318-180">이 섹션에 나열된 버전보다 오래된 버전은 기술 업그레이드 지원 전용으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4318-180">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<details>
<summary> <span data-ttu-id="e4318-181">2021년 3월(플랫폼: 4.18.2103.7 | 엔진: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="e4318-181">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="e4318-182">&ensp;보안 인텔리전스 업데이트 버전: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="e4318-182">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="e4318-183">&ensp;릴리스: **2021년 4월 2일**</span><span class="sxs-lookup"><span data-stu-id="e4318-183">&ensp;Released: **April 2, 2021**</span></span>  
<span data-ttu-id="e4318-184">&ensp;플랫폼: **4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="e4318-184">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="e4318-185">&ensp;엔진: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="e4318-185">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="e4318-186">&ensp;지원 단계: **기술 업그레이드 지원(전용)**</span><span class="sxs-lookup"><span data-stu-id="e4318-186">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e4318-187">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="e4318-187">What's new</span></span>

- <span data-ttu-id="e4318-188">동작 모니터링 엔진 개선</span><span class="sxs-lookup"><span data-stu-id="e4318-188">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="e4318-189">확장된 네트워크 무차별 공격 완화</span><span class="sxs-lookup"><span data-stu-id="e4318-189">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="e4318-190">변조 방지를 사용하도록 설정한 경우 추가 변조 시도 이벤트 생성 [실패](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="e4318-190">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="e4318-191">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="e4318-191">Known Issues</span></span>
<span data-ttu-id="e4318-192">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="e4318-192">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="e4318-193">2021년 2월(플랫폼: 4.18.2102.3 | 엔진: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="e4318-193">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="e4318-194">&ensp;보안 인텔리전스 업데이트 버전: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="e4318-194">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="e4318-195">&ensp;릴리스: **2021년 3월 9일**</span><span class="sxs-lookup"><span data-stu-id="e4318-195">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="e4318-196">&ensp;플랫폼: **4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="e4318-196">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="e4318-197">&ensp;엔진: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="e4318-197">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="e4318-198">&ensp;지원 단계: **기술 업그레이드 지원(전용)**</span><span class="sxs-lookup"><span data-stu-id="e4318-198">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e4318-199">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="e4318-199">What's new</span></span>

- <span data-ttu-id="e4318-200">변조 방지를 통한 [서비스 복구 개선](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="e4318-200">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="e4318-201">변조 보호 범위 확장</span><span class="sxs-lookup"><span data-stu-id="e4318-201">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="e4318-202">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="e4318-202">Known Issues</span></span>
<span data-ttu-id="e4318-203">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="e4318-203">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="e4318-204">2021년 1월(플랫폼: 4.18.2101.9 | 엔진: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="e4318-204">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="e4318-205">&ensp;보안 인텔리전스 업데이트 버전: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="e4318-205">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="e4318-206">&ensp;릴리스: **2021년 2월 2일**</span><span class="sxs-lookup"><span data-stu-id="e4318-206">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="e4318-207">&ensp;플랫폼: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="e4318-207">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="e4318-208">&ensp;엔진: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="e4318-208">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="e4318-209">&ensp;지원 단계: **기술 업그레이드 지원(전용)**</span><span class="sxs-lookup"><span data-stu-id="e4318-209">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e4318-210">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="e4318-210">What's new</span></span>

- <span data-ttu-id="e4318-211">셸 코드 악용 감지 개선</span><span class="sxs-lookup"><span data-stu-id="e4318-211">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="e4318-212">자격 증명 도용 시도에 대한 가시성 향상</span><span class="sxs-lookup"><span data-stu-id="e4318-212">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="e4318-213">서비스에서 향상된 Microsoft Defender 바이러스 백신 기능</span><span class="sxs-lookup"><span data-stu-id="e4318-213">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="e4318-214">x64 에뮬 ARM 지원 개선</span><span class="sxs-lookup"><span data-stu-id="e4318-214">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="e4318-215">해결 방법: EDR 보호가 초기 검색을 수행한 후 위협 기록에 차단 알림이 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4318-215">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="e4318-216">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="e4318-216">Known Issues</span></span>
<span data-ttu-id="e4318-217">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="e4318-217">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="e4318-218">2020년 11월-2020년 11월(플랫폼: 4.18.2011.6 | 엔진: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="e4318-218">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="e4318-219">&ensp;보안 인텔리전스 업데이트 버전: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="e4318-219">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="e4318-220">&ensp;릴리스: **2020년 12월 3일**</span><span class="sxs-lookup"><span data-stu-id="e4318-220">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="e4318-221">&ensp;플랫폼: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="e4318-221">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="e4318-222">&ensp;엔진: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="e4318-222">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="e4318-223">&ensp;지원 단계: **기술 업그레이드 지원(전용)**</span><span class="sxs-lookup"><span data-stu-id="e4318-223">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e4318-224">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="e4318-224">What's new</span></span>

- <span data-ttu-id="e4318-225">향상된 [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) 상태 지원 로깅</span><span class="sxs-lookup"><span data-stu-id="e4318-225">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="e4318-226">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="e4318-226">Known Issues</span></span>
<span data-ttu-id="e4318-227">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="e4318-227">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="e4318-228">2020년 10월(플랫폼: 4.18.2010.7 | 엔진: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="e4318-228">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="e4318-229">&ensp;보안 인텔리전스 업데이트 버전: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="e4318-229">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="e4318-230">&ensp;릴리스: **2020년 10월 29일**</span><span class="sxs-lookup"><span data-stu-id="e4318-230">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="e4318-231">&ensp;플랫폼: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="e4318-231">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="e4318-232">&ensp;엔진: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="e4318-232">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="e4318-233">&ensp;지원 단계: **기술 업그레이드 지원(전용)**</span><span class="sxs-lookup"><span data-stu-id="e4318-233">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e4318-234">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="e4318-234">What's new</span></span>

- <span data-ttu-id="e4318-235">특수 위협 범주에 대한 새 설명</span><span class="sxs-lookup"><span data-stu-id="e4318-235">New descriptions for special threat categories</span></span>
- <span data-ttu-id="e4318-236">향상된 에뮬ation 기능</span><span class="sxs-lookup"><span data-stu-id="e4318-236">Improved emulation capabilities</span></span>
- <span data-ttu-id="e4318-237">향상된 호스트 주소 허용/차단 기능</span><span class="sxs-lookup"><span data-stu-id="e4318-237">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="e4318-238">Defender CSP의 새 옵션에서 로컬 사용자 제외의 무시</span><span class="sxs-lookup"><span data-stu-id="e4318-238">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="e4318-239">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="e4318-239">Known Issues</span></span>

<span data-ttu-id="e4318-240">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="e4318-240">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="e4318-241">2020년 9월(플랫폼: 4.18.2009.7 | 엔진: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="e4318-241">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="e4318-242">&ensp;보안 인텔리전스 업데이트 버전: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="e4318-242">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="e4318-243">&ensp;릴리스: **2020년 10월 1일**</span><span class="sxs-lookup"><span data-stu-id="e4318-243">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="e4318-244">&ensp;플랫폼: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="e4318-244">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="e4318-245">&ensp;엔진: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="e4318-245">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="e4318-246">&ensp;지원 단계: **기술 업그레이드 지원(전용)**</span><span class="sxs-lookup"><span data-stu-id="e4318-246">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e4318-247">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="e4318-247">What's new</span></span>

- <span data-ttu-id="e4318-248">파일을 Quarantine에서 복원하려면 관리자 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e4318-248">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="e4318-249">이제 XML 형식 이벤트가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4318-249">XML formatted events are now supported</span></span>
- <span data-ttu-id="e4318-250">제외 병합을 외면하기 위한 CSP 지원</span><span class="sxs-lookup"><span data-stu-id="e4318-250">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="e4318-251">새 관리 인터페이스:</span><span class="sxs-lookup"><span data-stu-id="e4318-251">New management interfaces for:</span></span>
   - <span data-ttu-id="e4318-252">UDP 검사</span><span class="sxs-lookup"><span data-stu-id="e4318-252">UDP Inspection</span></span>
   - <span data-ttu-id="e4318-253">Server 2019의 네트워크 보호</span><span class="sxs-lookup"><span data-stu-id="e4318-253">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="e4318-254">네트워크 보호를 위한 IP 주소 제외</span><span class="sxs-lookup"><span data-stu-id="e4318-254">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="e4318-255">TPM 측정에 대한 가시성 향상</span><span class="sxs-lookup"><span data-stu-id="e4318-255">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="e4318-256">VBA 모듈 Office 향상</span><span class="sxs-lookup"><span data-stu-id="e4318-256">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="e4318-257">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="e4318-257">Known Issues</span></span>

<span data-ttu-id="e4318-258">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="e4318-258">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="e4318-259">2020년 8월(플랫폼: 4.18.2008.9 | 엔진: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="e4318-259">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="e4318-260">&ensp;보안 인텔리전스 업데이트 버전: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="e4318-260">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="e4318-261">&ensp;릴리스: **2020년 8월 27일**</span><span class="sxs-lookup"><span data-stu-id="e4318-261">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="e4318-262">&ensp;플랫폼: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="e4318-262">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="e4318-263">&ensp;엔진: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="e4318-263">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="e4318-264">&ensp;지원 단계: **기술 업그레이드 지원(전용)**</span><span class="sxs-lookup"><span data-stu-id="e4318-264">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="e4318-265">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="e4318-265">What's new</span></span>

- <span data-ttu-id="e4318-266">원격 분석 이벤트 추가</span><span class="sxs-lookup"><span data-stu-id="e4318-266">Add more telemetry events</span></span>
- <span data-ttu-id="e4318-267">향상된 검사 이벤트 원격 분석</span><span class="sxs-lookup"><span data-stu-id="e4318-267">Improved scan event telemetry</span></span>
- <span data-ttu-id="e4318-268">메모리 검사에 대한 향상된 동작 모니터링</span><span class="sxs-lookup"><span data-stu-id="e4318-268">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="e4318-269">향상된 매크로 스트림 검사</span><span class="sxs-lookup"><span data-stu-id="e4318-269">Improved macro streams scanning</span></span>
- <span data-ttu-id="e4318-270">`AMRunningMode`PowerShell cmdlet에 Get-MpComputerStatus 추가</span><span class="sxs-lookup"><span data-stu-id="e4318-270">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="e4318-271">[DisableAntiSpyware는](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4318-271">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="e4318-272">Microsoft Defender 바이러스 백신 바이러스 백신 프로그램을 검색하면 자동으로 꺼집니다.</span><span class="sxs-lookup"><span data-stu-id="e4318-272">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="e4318-273">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="e4318-273">Known Issues</span></span>
<span data-ttu-id="e4318-274">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="e4318-274">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="e4318-275">2020년 7월(플랫폼: 4.18.2007.8 | 엔진: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="e4318-275">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="e4318-276">&ensp;보안 인텔리전스 업데이트 버전: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="e4318-276">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="e4318-277">&ensp;릴리스: **2020년 7월 28일**</span><span class="sxs-lookup"><span data-stu-id="e4318-277">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="e4318-278">&ensp;플랫폼: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="e4318-278">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="e4318-279">&ensp;엔진: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="e4318-279">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="e4318-280">&ensp;지원 단계: **기술 업그레이드 지원(전용)**</span><span class="sxs-lookup"><span data-stu-id="e4318-280">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e4318-281">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="e4318-281">What's new</span></span>

- <span data-ttu-id="e4318-282">BITS에 대한 향상된 원격 분석</span><span class="sxs-lookup"><span data-stu-id="e4318-282">Improved telemetry for BITS</span></span>
- <span data-ttu-id="e4318-283">Authenticode 코드 서명 인증서 유효성 검사 개선</span><span class="sxs-lookup"><span data-stu-id="e4318-283">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="e4318-284">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="e4318-284">Known Issues</span></span>
<span data-ttu-id="e4318-285">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="e4318-285">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="e4318-286">2020년 6월(플랫폼: 4.18.2006.10 | 엔진: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="e4318-286">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="e4318-287">&ensp;보안 인텔리전스 업데이트 버전: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="e4318-287">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="e4318-288">&ensp;릴리스: **2020년 6월 22일**</span><span class="sxs-lookup"><span data-stu-id="e4318-288">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="e4318-289">&ensp;플랫폼: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="e4318-289">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="e4318-290">&ensp;엔진: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="e4318-290">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="e4318-291">&ensp;지원 단계: **기술 업그레이드 지원(전용)**</span><span class="sxs-lookup"><span data-stu-id="e4318-291">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e4318-292">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="e4318-292">What's new</span></span>

- <span data-ttu-id="e4318-293">지원 [로그의 위치를 지정할 수 있습니다.](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="e4318-293">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="e4318-294">수동 모드에서 적극적인 catchup 검사 건너뛰기</span><span class="sxs-lookup"><span data-stu-id="e4318-294">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="e4318-295">데이터 데이터 연결에서 Defender 업데이트 허용</span><span class="sxs-lookup"><span data-stu-id="e4318-295">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="e4318-296">캐싱을 사용하지 않도록 설정한 경우의 고정 성능 조정</span><span class="sxs-lookup"><span data-stu-id="e4318-296">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="e4318-297">고정 레지스트리 쿼리</span><span class="sxs-lookup"><span data-stu-id="e4318-297">Fixed registry query</span></span> 
- <span data-ttu-id="e4318-298">ADMX의 검사 시간 임의 지정 수정</span><span class="sxs-lookup"><span data-stu-id="e4318-298">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="e4318-299">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="e4318-299">Known Issues</span></span>
<span data-ttu-id="e4318-300">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="e4318-300">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="e4318-301">2020년 5월(플랫폼: 4.18.2005.4 | 엔진: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="e4318-301">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="e4318-302">&ensp;보안 인텔리전스 업데이트 버전: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="e4318-302">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="e4318-303">&ensp;릴리스: **2020년 5월 26일**</span><span class="sxs-lookup"><span data-stu-id="e4318-303">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="e4318-304">&ensp;플랫폼: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="e4318-304">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="e4318-305">&ensp;엔진: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="e4318-305">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="e4318-306">&ensp;지원 단계: **기술 업그레이드 지원(전용)**</span><span class="sxs-lookup"><span data-stu-id="e4318-306">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e4318-307">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="e4318-307">What's new</span></span>

- <span data-ttu-id="e4318-308">검사 이벤트에 대한 로깅 개선</span><span class="sxs-lookup"><span data-stu-id="e4318-308">Improved logging for scan events</span></span>
- <span data-ttu-id="e4318-309">향상된 사용자 모드 크래시 처리.</span><span class="sxs-lookup"><span data-stu-id="e4318-309">Improved user mode crash handling.</span></span>
- <span data-ttu-id="e4318-310">변조 방지를 위한 이벤트 추적이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e4318-310">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="e4318-311">AMSI 샘플 제출 수정</span><span class="sxs-lookup"><span data-stu-id="e4318-311">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="e4318-312">AMSI 클라우드 차단 수정</span><span class="sxs-lookup"><span data-stu-id="e4318-312">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="e4318-313">고정 보안 업데이트 설치 로그</span><span class="sxs-lookup"><span data-stu-id="e4318-313">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="e4318-314">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="e4318-314">Known Issues</span></span>
<span data-ttu-id="e4318-315">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="e4318-315">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="e4318-316">2020년 4월(플랫폼: 4.18.2004.6 | 엔진: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="e4318-316">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="e4318-317">&ensp;보안 인텔리전스 업데이트 버전: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="e4318-317">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="e4318-318">&ensp;릴리스: **2020년 4월 30일**</span><span class="sxs-lookup"><span data-stu-id="e4318-318">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="e4318-319">&ensp;플랫폼: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="e4318-319">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="e4318-320">&ensp;엔진: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="e4318-320">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="e4318-321">&ensp;지원 단계: **기술 업그레이드 지원(전용)**</span><span class="sxs-lookup"><span data-stu-id="e4318-321">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e4318-322">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="e4318-322">What's new</span></span>
- <span data-ttu-id="e4318-323">WDfilter 개선</span><span class="sxs-lookup"><span data-stu-id="e4318-323">WDfilter improvements</span></span>
- <span data-ttu-id="e4318-324">더 실행 가능한 이벤트 데이터를 추가하여 표면 감소 감지 이벤트 공격</span><span class="sxs-lookup"><span data-stu-id="e4318-324">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="e4318-325">진단 데이터 및 WMI의 고정 버전 정보</span><span class="sxs-lookup"><span data-stu-id="e4318-325">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="e4318-326">플랫폼 업데이트 후 UI에서 잘못된 플랫폼 버전 수정</span><span class="sxs-lookup"><span data-stu-id="e4318-326">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="e4318-327">파일 없는 위협 방지를 위한 동적 URL intel</span><span class="sxs-lookup"><span data-stu-id="e4318-327">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="e4318-328">UEFI 검사 기능</span><span class="sxs-lookup"><span data-stu-id="e4318-328">UEFI scan capability</span></span>
- <span data-ttu-id="e4318-329">업데이트 로깅 확장</span><span class="sxs-lookup"><span data-stu-id="e4318-329">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="e4318-330">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="e4318-330">Known Issues</span></span>
<span data-ttu-id="e4318-331">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="e4318-331">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="e4318-332">2020년 3월(플랫폼: 4.18.2003.8 | 엔진: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="e4318-332">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="e4318-333">&ensp;보안 인텔리전스 업데이트 버전: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="e4318-333">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="e4318-334">&ensp;릴리스: **2020년 3월 24일**</span><span class="sxs-lookup"><span data-stu-id="e4318-334">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="e4318-335">&ensp;플랫폼: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="e4318-335">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="e4318-336">&ensp;엔진: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="e4318-336">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="e4318-337">&ensp;지원 단계: **기술 업그레이드 지원(전용)**</span><span class="sxs-lookup"><span data-stu-id="e4318-337">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e4318-338">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="e4318-338">What's new</span></span>

- <span data-ttu-id="e4318-339">[MpCmdRun에](./command-line-arguments-microsoft-defender-antivirus.md) 추가된 CPU 스로틀 옵션</span><span class="sxs-lookup"><span data-stu-id="e4318-339">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="e4318-340">진단 기능 개선</span><span class="sxs-lookup"><span data-stu-id="e4318-340">Improve diagnostic capability</span></span>
- <span data-ttu-id="e4318-341">보안 인텔리전스 시간 제한 단축(5분)</span><span class="sxs-lookup"><span data-stu-id="e4318-341">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="e4318-342">AMSI 엔진 내부 로그 기능 확장</span><span class="sxs-lookup"><span data-stu-id="e4318-342">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="e4318-343">프로세스 차단에 대한 알림 개선</span><span class="sxs-lookup"><span data-stu-id="e4318-343">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="e4318-344">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="e4318-344">Known Issues</span></span>
<span data-ttu-id="e4318-345">[**Fixed**] Microsoft Defender 바이러스 백신 실행 시 파일을 건너뛰고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4318-345">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="e4318-346">2020년 2월(플랫폼: - | 엔진: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="e4318-346">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="e4318-347">&ensp;보안 인텔리전스 업데이트 버전: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="e4318-347">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="e4318-348">&ensp;릴리스: **2020년 2월 25일**</span><span class="sxs-lookup"><span data-stu-id="e4318-348">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="e4318-349">&ensp;플랫폼/클라이언트: **-**</span><span class="sxs-lookup"><span data-stu-id="e4318-349">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="e4318-350">&ensp;엔진: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="e4318-350">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="e4318-351">&ensp;지원 단계: **기술 업그레이드 지원(전용)**</span><span class="sxs-lookup"><span data-stu-id="e4318-351">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="e4318-352">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="e4318-352">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="e4318-353">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="e4318-353">Known Issues</span></span>
<span data-ttu-id="e4318-354">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="e4318-354">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="e4318-355">2020년 1월(플랫폼: 4.18.2001.10 | 엔진: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="e4318-355">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="e4318-356">보안 인텔리전스 업데이트 버전: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="e4318-356">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="e4318-357">릴리스: **2020년 1월 30일**</span><span class="sxs-lookup"><span data-stu-id="e4318-357">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="e4318-358">플랫폼/클라이언트: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="e4318-358">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="e4318-359">엔진: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="e4318-359">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="e4318-360">&ensp;지원 단계: **기술 업그레이드 지원(전용)**</span><span class="sxs-lookup"><span data-stu-id="e4318-360">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="e4318-361">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="e4318-361">What's new</span></span>

- <span data-ttu-id="e4318-362">WS2016의 고정 BSOD 및 Exchange</span><span class="sxs-lookup"><span data-stu-id="e4318-362">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="e4318-363">TMP가 네트워크 경로로 리디렉션될 때 플랫폼 업데이트 지원</span><span class="sxs-lookup"><span data-stu-id="e4318-363">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="e4318-364">플랫폼 및 엔진 버전이 [WDSI에 추가됩니다.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="e4318-364">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="e4318-365">긴급 서명 업데이트를 [수동 모드로 확장](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="e4318-365">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="e4318-366">4.18.1911.3 중단 수정</span><span class="sxs-lookup"><span data-stu-id="e4318-366">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="e4318-367">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="e4318-367">Known Issues</span></span>

<span data-ttu-id="e4318-368">[**고정**] [](/windows-hardware/design/device-experiences/modern-standby) 최신 대기 모드를 활용하는 장치는 보호의 간격을 Windows Defender 필터 드라이버가 중단될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4318-368">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="e4318-369">영향을 받는 컴퓨터는 최신 맬웨어 방지 플랫폼으로 업데이트되지 않은 것으로 고객에게 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4318-369">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="e4318-370">이 업데이트는:</span><span class="sxs-lookup"><span data-stu-id="e4318-370">This update is:</span></span>
> - <span data-ttu-id="e4318-371">SHA2를 지원하기 위해 더 낮은 버전의 플랫폼을 실행하는 RS1 장치에서 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e4318-371">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="e4318-372">문제가 있는 시스템에 대한 재부팅 플래그가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4318-372">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="e4318-373">는 2020년 4월에 다시 출시될 예정으로, 향후 가용성을 유지하기 위해 최신 업데이트로 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e4318-373">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="e4318-374">는 재부팅 요구 사항으로 인해 업데이트로 분류됩니다. 및</span><span class="sxs-lookup"><span data-stu-id="e4318-374">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="e4318-375">는 업데이트 [에서만 Windows 있습니다.](https://support.microsoft.com/help/4027667/windows-10-update)</span><span class="sxs-lookup"><span data-stu-id="e4318-375">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="e4318-376">2019년 11월부터 2019년 11월까지(플랫폼: 4.18.1911.3 | 엔진: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="e4318-376">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="e4318-377">보안 인텔리전스 업데이트 버전: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="e4318-377">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="e4318-378">릴리스: **2019년 12월 7일**</span><span class="sxs-lookup"><span data-stu-id="e4318-378">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="e4318-379">플랫폼: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="e4318-379">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="e4318-380">엔진: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="e4318-380">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="e4318-381">지원 단계: **지원 없음**</span><span class="sxs-lookup"><span data-stu-id="e4318-381">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="e4318-382">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="e4318-382">What's new</span></span>

- <span data-ttu-id="e4318-383">고정 MpCmdRun 추적 수준</span><span class="sxs-lookup"><span data-stu-id="e4318-383">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="e4318-384">WDFilter 버전 정보 수정</span><span class="sxs-lookup"><span data-stu-id="e4318-384">Fixed WDFilter version info</span></span>
- <span data-ttu-id="e4318-385">알림 개선(PUA)</span><span class="sxs-lookup"><span data-stu-id="e4318-385">Improve notifications (PUA)</span></span>
- <span data-ttu-id="e4318-386">MRT 로그를 추가하여 파일 지원</span><span class="sxs-lookup"><span data-stu-id="e4318-386">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="e4318-387">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="e4318-387">Known Issues</span></span>
<span data-ttu-id="e4318-388">이 업데이트를 설치하면 디바이스에서 점프 패키지 4.18.2001.10을 최신 플랫폼 버전으로 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4318-388">When this update is installed, the device needs the jump package 4.18.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="e4318-389">Microsoft Defender 바이러스 백신 플랫폼 지원</span><span class="sxs-lookup"><span data-stu-id="e4318-389">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="e4318-390">플랫폼 및 엔진 업데이트는 월별 케이던스에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4318-390">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="e4318-391">완전히 지원받기 위해 최신 플랫폼 업데이트를 최신으로 유지하세요.</span><span class="sxs-lookup"><span data-stu-id="e4318-391">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="e4318-392">지원 구조는 동적이며, 최신 플랫폼 버전의 가용성에 따라 다음 두 단계로 진화합니다.</span><span class="sxs-lookup"><span data-stu-id="e4318-392">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="e4318-393">**보안 및** 중요 업데이트 서비스 단계 - 최신 플랫폼 버전을 실행하는 경우 맬웨어 방지 플랫폼에 대한 보안 및 중요 업데이트를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4318-393">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="e4318-394">**기술 지원(전용) 단계** - 새 플랫폼 버전이 출시된 후 이전 버전(N-2)에 대한 지원은 기술 지원으로만 축소됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4318-394">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="e4318-395">N-2 이전의 플랫폼 버전은 더 이상 지원되지 않습니다.\*</span><span class="sxs-lookup"><span data-stu-id="e4318-395">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="e4318-396">\*기술 지원은 Windows 10 릴리스 버전에서 최신 플랫폼 버전으로의 업그레이드를 위해 계속 [제공됩니다(Windows 10](#platform-version-included-with-windows-10-releases)릴리스에 포함된 플랫폼 버전 참조).</span><span class="sxs-lookup"><span data-stu-id="e4318-396">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="e4318-397">기술 지원(전용) 단계 중에는 상업적으로 합리적인 지원 인시던트가 Microsoft 고객 서비스 & 지원 및 Microsoft의 관리 지원 서비스(예: 프리미어 지원)를 통해 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4318-397">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="e4318-398">지원 인시던트가 추가 지침을 위해 개발로 에스컬레이터해야 하는 경우, 비보안 업데이트가 필요하거나, 보안 업데이트가 필요한 경우 고객에게 최신 플랫폼 버전 또는 중간 업데이트(\*)로 업그레이드할지 묻는 요청이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4318-398">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="e4318-399">릴리스에 포함된 플랫폼 Windows 10 버전</span><span class="sxs-lookup"><span data-stu-id="e4318-399">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="e4318-400">아래 표에는 최신 Microsoft Defender 바이러스 백신 함께 제공된 플랫폼 및 엔진 버전이 Windows 10 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4318-400">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="e4318-401">Windows 10 릴리스</span><span class="sxs-lookup"><span data-stu-id="e4318-401">Windows 10 release</span></span>  |<span data-ttu-id="e4318-402">플랫폼 버전</span><span class="sxs-lookup"><span data-stu-id="e4318-402">Platform version</span></span>  |<span data-ttu-id="e4318-403">엔진 버전</span><span class="sxs-lookup"><span data-stu-id="e4318-403">Engine version</span></span> |<span data-ttu-id="e4318-404">지원 단계</span><span class="sxs-lookup"><span data-stu-id="e4318-404">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="e4318-405">2004(20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="e4318-405">2004  (20H1/20H2)</span></span> |<span data-ttu-id="e4318-406">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="e4318-406">4.18.1909.6</span></span> |<span data-ttu-id="e4318-407">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="e4318-407">1.1.17000.2</span></span> | <span data-ttu-id="e4318-408">기술 업그레이드 지원(전용)</span><span class="sxs-lookup"><span data-stu-id="e4318-408">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="e4318-409">1909(19H2)</span><span class="sxs-lookup"><span data-stu-id="e4318-409">1909  (19H2)</span></span> |<span data-ttu-id="e4318-410">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="e4318-410">4.18.1902.5</span></span> |<span data-ttu-id="e4318-411">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="e4318-411">1.1.16700.3</span></span> | <span data-ttu-id="e4318-412">기술 업그레이드 지원(전용)</span><span class="sxs-lookup"><span data-stu-id="e4318-412">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="e4318-413">1903(19H1)</span><span class="sxs-lookup"><span data-stu-id="e4318-413">1903  (19H1)</span></span> |<span data-ttu-id="e4318-414">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="e4318-414">4.18.1902.5</span></span> |<span data-ttu-id="e4318-415">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="e4318-415">1.1.15600.4</span></span> | <span data-ttu-id="e4318-416">기술 업그레이드 지원(전용)</span><span class="sxs-lookup"><span data-stu-id="e4318-416">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="e4318-417">1809(RS5)</span><span class="sxs-lookup"><span data-stu-id="e4318-417">1809  (RS5)</span></span> |<span data-ttu-id="e4318-418">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="e4318-418">4.18.1807.18075</span></span> |<span data-ttu-id="e4318-419">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="e4318-419">1.1.15000.2</span></span> | <span data-ttu-id="e4318-420">기술 업그레이드 지원(전용)</span><span class="sxs-lookup"><span data-stu-id="e4318-420">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="e4318-421">1803(RS4)</span><span class="sxs-lookup"><span data-stu-id="e4318-421">1803  (RS4)</span></span> |<span data-ttu-id="e4318-422">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="e4318-422">4.13.17134.1</span></span> |<span data-ttu-id="e4318-423">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="e4318-423">1.1.14600.4</span></span> | <span data-ttu-id="e4318-424">기술 업그레이드 지원(전용)</span><span class="sxs-lookup"><span data-stu-id="e4318-424">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="e4318-425">1709(RS3)</span><span class="sxs-lookup"><span data-stu-id="e4318-425">1709  (RS3)</span></span> |<span data-ttu-id="e4318-426">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="e4318-426">4.12.16299.15</span></span> |<span data-ttu-id="e4318-427">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="e4318-427">1.1.14104.0</span></span> | <span data-ttu-id="e4318-428">기술 업그레이드 지원(전용)</span><span class="sxs-lookup"><span data-stu-id="e4318-428">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="e4318-429">1703(RS2)</span><span class="sxs-lookup"><span data-stu-id="e4318-429">1703  (RS2)</span></span> |<span data-ttu-id="e4318-430">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="e4318-430">4.11.15603.2</span></span> |<span data-ttu-id="e4318-431">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="e4318-431">1.1.13504.0</span></span> | <span data-ttu-id="e4318-432">기술 업그레이드 지원(전용)</span><span class="sxs-lookup"><span data-stu-id="e4318-432">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="e4318-433">1607(RS1)</span><span class="sxs-lookup"><span data-stu-id="e4318-433">1607 (RS1)</span></span> |<span data-ttu-id="e4318-434">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="e4318-434">4.10.14393.3683</span></span> |<span data-ttu-id="e4318-435">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="e4318-435">1.1.12805.0</span></span> | <span data-ttu-id="e4318-436">기술 업그레이드 지원(전용)</span><span class="sxs-lookup"><span data-stu-id="e4318-436">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="e4318-437">릴리스 Windows 10 자세한 내용은 수명 주기 Windows [시트를 참조하세요.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)</span><span class="sxs-lookup"><span data-stu-id="e4318-437">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="e4318-438">DISM(배포 이미지 서비스 및 관리)에 대한 업데이트</span><span class="sxs-lookup"><span data-stu-id="e4318-438">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="e4318-439">최신 바이러스 백신 및 맬웨어 방지 업데이트로 Windows 10(Enterprise, Pro 및 Home edition), Windows Server 2019 및 Windows Server 2016 OS 설치 이미지를 업데이트하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e4318-439">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="e4318-440">OS 설치 이미지를 최신으로 유지하면 보호 격차를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4318-440">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="e4318-441">자세한 내용은 운영 체제 설치 Windows Microsoft [Defender 업데이트를 참조하세요.](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)</span><span class="sxs-lookup"><span data-stu-id="e4318-441">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="e4318-442">1.1.2106.01</span><span class="sxs-lookup"><span data-stu-id="e4318-442">1.1.2106.01</span></span></summary>

<span data-ttu-id="e4318-443">&ensp;패키지 버전: **1.1.2106.01**  </span><span class="sxs-lookup"><span data-stu-id="e4318-443">&ensp;Package version: **1.1.2106.01**  </span></span>  
<span data-ttu-id="e4318-444">&ensp;플랫폼 버전: **4.18.2104.14** </span><span class="sxs-lookup"><span data-stu-id="e4318-444">&ensp;Platform version: **4.18.2104.14** </span></span>  
<span data-ttu-id="e4318-445">&ensp;엔진 버전: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="e4318-445">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="e4318-446">&ensp;서명 버전: **1.339.1923.0**</span><span class="sxs-lookup"><span data-stu-id="e4318-446">&ensp;Signature version: **1.339.1923.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="e4318-447">수정</span><span class="sxs-lookup"><span data-stu-id="e4318-447">Fixes</span></span>
- <span data-ttu-id="e4318-448">없음</span><span class="sxs-lookup"><span data-stu-id="e4318-448">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="e4318-449">추가 정보</span><span class="sxs-lookup"><span data-stu-id="e4318-449">Additional information</span></span>
- <span data-ttu-id="e4318-450">없음</span><span class="sxs-lookup"><span data-stu-id="e4318-450">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="e4318-451">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="e4318-451">1.1.2105.01</span></span></summary>

<span data-ttu-id="e4318-452">&ensp;패키지 버전: **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="e4318-452">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="e4318-453">&ensp;플랫폼 버전: **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="e4318-453">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="e4318-454">&ensp;엔진 버전: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="e4318-454">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="e4318-455">&ensp;서명 버전: **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="e4318-455">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="e4318-456">수정</span><span class="sxs-lookup"><span data-stu-id="e4318-456">Fixes</span></span>
- <span data-ttu-id="e4318-457">없음</span><span class="sxs-lookup"><span data-stu-id="e4318-457">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="e4318-458">추가 정보</span><span class="sxs-lookup"><span data-stu-id="e4318-458">Additional information</span></span>
- <span data-ttu-id="e4318-459">없음</span><span class="sxs-lookup"><span data-stu-id="e4318-459">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="e4318-460">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="e4318-460">1.1.2104.01</span></span></summary>

<span data-ttu-id="e4318-461">&ensp;패키지 버전: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="e4318-461">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="e4318-462">&ensp;플랫폼 버전: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="e4318-462">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="e4318-463">&ensp;엔진 버전: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="e4318-463">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="e4318-464">&ensp;서명 버전: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="e4318-464">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="e4318-465">수정</span><span class="sxs-lookup"><span data-stu-id="e4318-465">Fixes</span></span>
- <span data-ttu-id="e4318-466">없음</span><span class="sxs-lookup"><span data-stu-id="e4318-466">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="e4318-467">추가 정보</span><span class="sxs-lookup"><span data-stu-id="e4318-467">Additional information</span></span>
- <span data-ttu-id="e4318-468">없음</span><span class="sxs-lookup"><span data-stu-id="e4318-468">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="e4318-469">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="e4318-469">1.1.2103.01</span></span></summary>

<span data-ttu-id="e4318-470">&ensp;패키지 버전: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="e4318-470">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="e4318-471">&ensp;플랫폼 버전: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="e4318-471">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="e4318-472">&ensp;엔진 버전: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="e4318-472">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="e4318-473">&ensp;서명 버전: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="e4318-473">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="e4318-474">수정</span><span class="sxs-lookup"><span data-stu-id="e4318-474">Fixes</span></span>
- <span data-ttu-id="e4318-475">없음</span><span class="sxs-lookup"><span data-stu-id="e4318-475">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="e4318-476">추가 정보</span><span class="sxs-lookup"><span data-stu-id="e4318-476">Additional information</span></span>
- <span data-ttu-id="e4318-477">없음</span><span class="sxs-lookup"><span data-stu-id="e4318-477">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="e4318-478">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="e4318-478">1.1.2102.03</span></span></summary>

<span data-ttu-id="e4318-479">&ensp;패키지 버전: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="e4318-479">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="e4318-480">&ensp;플랫폼 버전: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="e4318-480">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="e4318-481">&ensp;엔진 버전: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="e4318-481">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="e4318-482">&ensp;서명 버전: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="e4318-482">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="e4318-483">수정</span><span class="sxs-lookup"><span data-stu-id="e4318-483">Fixes</span></span>
- <span data-ttu-id="e4318-484">없음</span><span class="sxs-lookup"><span data-stu-id="e4318-484">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="e4318-485">추가 정보</span><span class="sxs-lookup"><span data-stu-id="e4318-485">Additional information</span></span>
- <span data-ttu-id="e4318-486">없음</span><span class="sxs-lookup"><span data-stu-id="e4318-486">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="e4318-487">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="e4318-487">1.1.2101.02</span></span></summary>

<span data-ttu-id="e4318-488">&ensp;패키지 버전: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="e4318-488">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="e4318-489">&ensp;플랫폼 버전: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="e4318-489">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="e4318-490">&ensp;엔진 버전: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="e4318-490">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="e4318-491">&ensp;서명 버전: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="e4318-491">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="e4318-492">수정</span><span class="sxs-lookup"><span data-stu-id="e4318-492">Fixes</span></span>
- <span data-ttu-id="e4318-493">없음</span><span class="sxs-lookup"><span data-stu-id="e4318-493">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="e4318-494">추가 정보</span><span class="sxs-lookup"><span data-stu-id="e4318-494">Additional information</span></span>
- <span data-ttu-id="e4318-495">없음</span><span class="sxs-lookup"><span data-stu-id="e4318-495">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="e4318-496">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="e4318-496">1.1.2012.01</span></span></summary>

<span data-ttu-id="e4318-497">&ensp;패키지 버전: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="e4318-497">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="e4318-498">&ensp;플랫폼 버전: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="e4318-498">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="e4318-499">&ensp;엔진 버전: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="e4318-499">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="e4318-500">&ensp;서명 버전: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="e4318-500">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="e4318-501">수정</span><span class="sxs-lookup"><span data-stu-id="e4318-501">Fixes</span></span>
- <span data-ttu-id="e4318-502">없음</span><span class="sxs-lookup"><span data-stu-id="e4318-502">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="e4318-503">추가 정보</span><span class="sxs-lookup"><span data-stu-id="e4318-503">Additional information</span></span>
- <span data-ttu-id="e4318-504">없음</span><span class="sxs-lookup"><span data-stu-id="e4318-504">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="e4318-505">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="e4318-505">1.1.2011.02</span></span></summary>

<span data-ttu-id="e4318-506">&ensp;패키지 버전: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="e4318-506">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="e4318-507">&ensp;플랫폼 버전: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="e4318-507">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="e4318-508">&ensp;엔진 버전: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="e4318-508">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="e4318-509">&ensp;서명 버전: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="e4318-509">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="e4318-510">수정</span><span class="sxs-lookup"><span data-stu-id="e4318-510">Fixes</span></span>
- <span data-ttu-id="e4318-511">없음</span><span class="sxs-lookup"><span data-stu-id="e4318-511">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="e4318-512">추가 정보</span><span class="sxs-lookup"><span data-stu-id="e4318-512">Additional information</span></span>
- <span data-ttu-id="e4318-513">새로 고쳐진 Microsoft Defender 바이러스 백신 서명</span><span class="sxs-lookup"><span data-stu-id="e4318-513">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="e4318-514">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="e4318-514">1.1.2011.01</span></span></summary>

<span data-ttu-id="e4318-515">&ensp;패키지 버전: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="e4318-515">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="e4318-516">&ensp;플랫폼 버전: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="e4318-516">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="e4318-517">&ensp;엔진 버전: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="e4318-517">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="e4318-518">&ensp;서명 버전: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="e4318-518">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="e4318-519">수정</span><span class="sxs-lookup"><span data-stu-id="e4318-519">Fixes</span></span>
- <span data-ttu-id="e4318-520">없음</span><span class="sxs-lookup"><span data-stu-id="e4318-520">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="e4318-521">추가 정보</span><span class="sxs-lookup"><span data-stu-id="e4318-521">Additional information</span></span>
- <span data-ttu-id="e4318-522">없음</span><span class="sxs-lookup"><span data-stu-id="e4318-522">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="e4318-523">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="e4318-523">1.1.2009.10</span></span></summary>

<span data-ttu-id="e4318-524">&ensp;패키지 버전: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="e4318-524">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="e4318-525">&ensp;플랫폼 버전: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="e4318-525">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="e4318-526">&ensp;엔진 버전: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="e4318-526">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="e4318-527">&ensp;서명 버전: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="e4318-527">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="e4318-528">수정</span><span class="sxs-lookup"><span data-stu-id="e4318-528">Fixes</span></span>
- <span data-ttu-id="e4318-529">없음</span><span class="sxs-lookup"><span data-stu-id="e4318-529">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="e4318-530">추가 정보</span><span class="sxs-lookup"><span data-stu-id="e4318-530">Additional information</span></span>
- <span data-ttu-id="e4318-531">RS1 Windows 10 OS 설치 이미지에 대한 지원이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e4318-531">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="e4318-532">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="e4318-532">Additional resources</span></span>

| <span data-ttu-id="e4318-533">문서</span><span class="sxs-lookup"><span data-stu-id="e4318-533">Article</span></span> | <span data-ttu-id="e4318-534">설명</span><span class="sxs-lookup"><span data-stu-id="e4318-534">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="e4318-535">운영 체제 설치 Windows 대한 Microsoft Defender 업데이트</span><span class="sxs-lookup"><span data-stu-id="e4318-535">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="e4318-536">OS 설치 이미지(WIM 및 VHD 파일)에 대한 맬웨어 방지 업데이트 패키지를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="e4318-536">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="e4318-537">Microsoft Defender 바이러스 백신(Windows 10 Enterprise, Pro 및 Home edition), Windows Server 2019 및 Windows Server 2016 설치 이미지에 대한 Windows Server 2016 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="e4318-537">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="e4318-538">보호 업데이트를 다운로드하고 적용하는 방법 관리</span><span class="sxs-lookup"><span data-stu-id="e4318-538">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="e4318-539">보호 업데이트는 여러 소스를 통해 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4318-539">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="e4318-540">보호 업데이트를 다운로드하고 적용해야 하는 경우 관리</span><span class="sxs-lookup"><span data-stu-id="e4318-540">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="e4318-541">보호 업데이트를 다운로드해야 하는 경우를 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4318-541">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="e4318-542">최신이 지난 끝점에 대한 업데이트 관리</span><span class="sxs-lookup"><span data-stu-id="e4318-542">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="e4318-543">끝점에서 업데이트 또는 예약된 검사가 누락된 경우 다음에 사용자가 로그인할 때 강제로 업데이트를 실행하거나 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4318-543">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="e4318-544">이벤트 기반 강제 업데이트 관리</span><span class="sxs-lookup"><span data-stu-id="e4318-544">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="e4318-545">시작 시 또는 특정 클라우드 제공 보호 이벤트 후에 보호 업데이트를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4318-545">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="e4318-546">모바일 장치 및 VM(가상 머신)에 대한 업데이트 관리</span><span class="sxs-lookup"><span data-stu-id="e4318-546">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="e4318-547">모바일 장치 및 가상 머신에 특히 유용한 배터리 전원에서 업데이트가 발생해야 하는지 여부와 같은 설정을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4318-547">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
