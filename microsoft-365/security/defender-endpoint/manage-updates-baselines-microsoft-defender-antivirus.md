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
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.date: 06/08/2021
ms.openlocfilehash: ccbb57d781196e352e0fed456a1f7cb43eb17300
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822277"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="daf40-104">업데이트 Microsoft Defender 바이러스 백신 관리하고 기준 적용</span><span class="sxs-lookup"><span data-stu-id="daf40-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="daf40-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="daf40-105">**Applies to:**</span></span>

- [<span data-ttu-id="daf40-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="daf40-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="daf40-107">Windows Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="daf40-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="daf40-108">최신 업데이트와 관련된 두 가지 유형의 업데이트가 Microsoft Defender 바이러스 백신 있습니다.</span><span class="sxs-lookup"><span data-stu-id="daf40-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="daf40-109">보안 인텔리전스 업데이트</span><span class="sxs-lookup"><span data-stu-id="daf40-109">Security intelligence updates</span></span>
- <span data-ttu-id="daf40-110">제품 업데이트</span><span class="sxs-lookup"><span data-stu-id="daf40-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="daf40-111">최신 Microsoft Defender 바이러스 백신 유지하는 것은 장치에 새로운 맬웨어 및 공격 기술로부터 보호하는 데 필요한 최신 기술 및 기능을 유지하는 데 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="daf40-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>
> 
> <span data-ttu-id="daf40-112">수동 모드에서 실행 중인 경우에도 바이러스 Microsoft Defender 바이러스 백신 [업데이트해야 합니다.](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="daf40-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="daf40-113">최신 엔진, 플랫폼 및 서명 날짜를 확인하기 위해 Microsoft Defender 바이러스 백신 Microsoft 맬웨어 방지에 대한 보안 [인텔리전스 업데이트를 방문하세요.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="daf40-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="daf40-114">보안 인텔리전스 업데이트</span><span class="sxs-lookup"><span data-stu-id="daf40-114">Security intelligence updates</span></span>

<span data-ttu-id="daf40-115">Microsoft Defender 바이러스 백신 Microsoft Advanced [](cloud-protection-microsoft-defender-antivirus.md) Protection Service 또는 MAPS라고도 하는 클라우드 제공 보호를 사용하며 보안 인텔리전스 업데이트를 주기적으로 다운로드하여 보호 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="daf40-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="daf40-116">업데이트는 아래 KB 번호에 따라 릴리스됩니다.</span><span class="sxs-lookup"><span data-stu-id="daf40-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="daf40-117">Microsoft Defender 바이러스 백신: KB2267602</span><span class="sxs-lookup"><span data-stu-id="daf40-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="daf40-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="daf40-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="daf40-119">클라우드 제공 보호는 항상 설정되어 있으며 인터넷에 대한 활성 연결이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="daf40-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="daf40-120">보안 인텔리전스 업데이트는 예약된 일정에 따라 발생합니다(정책을 통해 구성 가능).</span><span class="sxs-lookup"><span data-stu-id="daf40-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="daf40-121">자세한 내용은 에서 Microsoft 클라우드 제공 보호 [Microsoft Defender 바이러스 백신.](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="daf40-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="daf40-122">최신 보안 인텔리전스 업데이트 목록은 보안 인텔리전스 업데이트 및 Microsoft Defender 바이러스 백신 [맬웨어 방지를 참조하세요.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="daf40-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="daf40-123">엔진 업데이트는 보안 인텔리전스 업데이트에 포함되어 있으며 월별 케이던스에 릴리스됩니다.</span><span class="sxs-lookup"><span data-stu-id="daf40-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="daf40-124">제품 업데이트</span><span class="sxs-lookup"><span data-stu-id="daf40-124">Product updates</span></span>

<span data-ttu-id="daf40-125">Microsoft Defender 바이러스 백신  [업데이트(KB4052623)(플랫폼](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) 업데이트라고도 알려)가 필요하며, 주요 기능 업데이트와 함께 Windows 10 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="daf40-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="daf40-126">다음 방법 중 하나를 통해 업데이트 배포를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="daf40-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="daf40-127">Windows WSUS(서버 업데이트 서비스)</span><span class="sxs-lookup"><span data-stu-id="daf40-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="daf40-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="daf40-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="daf40-129">Microsoft를 배포하고 네트워크의 끝점에 Windows 배포하는 데 사용하는 일반적인 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="daf40-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="daf40-130">자세한 내용은 [Manage the sources for Microsoft Defender 바이러스 백신 protection updates를 참조하십시오.](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)</span><span class="sxs-lookup"><span data-stu-id="daf40-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="daf40-131">월별 업데이트는 단계적으로 릴리스되어 Window Server Update Services에 여러 [패키지가 표시됩니다.](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)</span><span class="sxs-lookup"><span data-stu-id="daf40-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="daf40-132">월별 플랫폼 및 엔진 버전</span><span class="sxs-lookup"><span data-stu-id="daf40-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="daf40-133">플랫폼 업데이트를 업데이트하거나 설치하는 방법에 대한 자세한 내용은 Windows Defender 맬웨어 방지 플랫폼용 업데이트를 [참조하세요.](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)</span><span class="sxs-lookup"><span data-stu-id="daf40-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="daf40-134">모든 업데이트에 포함</span><span class="sxs-lookup"><span data-stu-id="daf40-134">All our updates contain</span></span> 
- <span data-ttu-id="daf40-135">성능 개선</span><span class="sxs-lookup"><span data-stu-id="daf40-135">performance improvements;</span></span>
- <span data-ttu-id="daf40-136">서비스성 개선 및</span><span class="sxs-lookup"><span data-stu-id="daf40-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="daf40-137">통합 개선된 기능(클라우드, Microsoft 365 [Defender).](/microsoft-365/security/defender/microsoft-365-defender)</span><span class="sxs-lookup"><span data-stu-id="daf40-137">integration improvements (Cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="daf40-138">2021년 5월(플랫폼: 4.18.2105.4 | 엔진: 1.1.18200.4)</span><span class="sxs-lookup"><span data-stu-id="daf40-138">May-2021 (Platform: 4.18.2105.4 | Engine: 1.1.18200.4)</span></span></summary>

<span data-ttu-id="daf40-139">&ensp;보안 인텔리전스 업데이트 버전: **1.341.8.0**</span><span class="sxs-lookup"><span data-stu-id="daf40-139">&ensp;Security intelligence update version: **1.341.8.0**</span></span>  
<span data-ttu-id="daf40-140">&ensp;릴리스: **2021년 6월 4일**</span><span class="sxs-lookup"><span data-stu-id="daf40-140">&ensp;Released: **June 4, 2021**</span></span>  
<span data-ttu-id="daf40-141">&ensp;플랫폼: **4.18.2105.4**</span><span class="sxs-lookup"><span data-stu-id="daf40-141">&ensp;Platform: **4.18.2105.4**</span></span>  
<span data-ttu-id="daf40-142">&ensp;엔진: **1.1.18200.4**</span><span class="sxs-lookup"><span data-stu-id="daf40-142">&ensp;Engine: **1.1.18200.4**</span></span>  
<span data-ttu-id="daf40-143">&ensp;지원 단계: **보안 및 중요 업데이트**</span><span class="sxs-lookup"><span data-stu-id="daf40-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="daf40-144">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="daf40-144">What's new</span></span>
- <span data-ttu-id="daf40-145">동작 모니터링 [개선](client-behavioral-blocking.md)</span><span class="sxs-lookup"><span data-stu-id="daf40-145">Improvements to [behavior monitoring](client-behavioral-blocking.md)</span></span> 
- <span data-ttu-id="daf40-146">고정 [네트워크 보호](network-protection.md) 알림 필터링 기능</span><span class="sxs-lookup"><span data-stu-id="daf40-146">Fixed [network protection](network-protection.md) notification filtering feature</span></span>

### <a name="known-issues"></a><span data-ttu-id="daf40-147">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="daf40-147">Known Issues</span></span>
<span data-ttu-id="daf40-148">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="daf40-148">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="daf40-149">2021년 4월(플랫폼: 4.18.2104.14 | 엔진: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="daf40-149">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="daf40-150">&ensp;보안 인텔리전스 업데이트 버전: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="daf40-150">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="daf40-151">&ensp;릴리스: **2021년 4월 1일**</span><span class="sxs-lookup"><span data-stu-id="daf40-151">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="daf40-152">&ensp;플랫폼: **4.18.2104.14**</span><span class="sxs-lookup"><span data-stu-id="daf40-152">&ensp;Platform: **4.18.2104.14**</span></span>  
<span data-ttu-id="daf40-153">&ensp;엔진: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="daf40-153">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="daf40-154">&ensp;지원 단계: **보안 및 중요 업데이트**</span><span class="sxs-lookup"><span data-stu-id="daf40-154">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="daf40-155">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="daf40-155">What's new</span></span>
- <span data-ttu-id="daf40-156">추가 동작 모니터링 논리</span><span class="sxs-lookup"><span data-stu-id="daf40-156">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="daf40-157">커널 모드 키로거 검색 개선</span><span class="sxs-lookup"><span data-stu-id="daf40-157">Improved kernel mode keylogger detection</span></span>
- <span data-ttu-id="daf40-158">Microsoft Defender 업데이트의점적 출시 프로세스를 관리하기 위한 새 [컨트롤이 추가되었습니다.](updates.md)</span><span class="sxs-lookup"><span data-stu-id="daf40-158">Added new controls to manage the gradual rollout process for [Microsoft Defender updates](updates.md)</span></span>

### <a name="known-issues"></a><span data-ttu-id="daf40-159">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="daf40-159">Known Issues</span></span>
<span data-ttu-id="daf40-160">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="daf40-160">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="daf40-161">2021년 3월(플랫폼: 4.18.2103.7 | 엔진: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="daf40-161">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="daf40-162">&ensp;보안 인텔리전스 업데이트 버전: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="daf40-162">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="daf40-163">&ensp;릴리스: **2021년 4월 1일**</span><span class="sxs-lookup"><span data-stu-id="daf40-163">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="daf40-164">&ensp;플랫폼: **4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="daf40-164">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="daf40-165">&ensp;엔진: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="daf40-165">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="daf40-166">&ensp;지원 단계: **보안 및 중요 업데이트**</span><span class="sxs-lookup"><span data-stu-id="daf40-166">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="daf40-167">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="daf40-167">What's new</span></span>

- <span data-ttu-id="daf40-168">동작 모니터링 엔진 개선</span><span class="sxs-lookup"><span data-stu-id="daf40-168">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="daf40-169">확장된 네트워크 무차별 공격 완화</span><span class="sxs-lookup"><span data-stu-id="daf40-169">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="daf40-170">변조 방지를 사용하도록 설정한 경우 추가 변조 시도 이벤트 생성 [실패](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="daf40-170">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="daf40-171">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="daf40-171">Known Issues</span></span>
<span data-ttu-id="daf40-172">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="daf40-172">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="daf40-173">이전 버전 업데이트: 기술 업그레이드 지원만</span><span class="sxs-lookup"><span data-stu-id="daf40-173">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="daf40-174">새 패키지 버전이 출시된 후 이전 두 버전에 대한 지원은 기술 지원으로만 축소됩니다.</span><span class="sxs-lookup"><span data-stu-id="daf40-174">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="daf40-175">이 섹션에 나열된 버전보다 오래된 버전은 기술 업그레이드 지원 전용으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="daf40-175">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="daf40-176">2021년 2월(플랫폼: 4.18.2102.3 | 엔진: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="daf40-176">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="daf40-177">&ensp;보안 인텔리전스 업데이트 버전: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="daf40-177">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="daf40-178">&ensp;릴리스: **2021년 3월 9일**</span><span class="sxs-lookup"><span data-stu-id="daf40-178">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="daf40-179">&ensp;플랫폼: **4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="daf40-179">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="daf40-180">&ensp;엔진: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="daf40-180">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="daf40-181">&ensp;지원 단계: **기술 업그레이드 지원(전용)**</span><span class="sxs-lookup"><span data-stu-id="daf40-181">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="daf40-182">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="daf40-182">What's new</span></span>

- <span data-ttu-id="daf40-183">변조 방지를 통한 [서비스 복구 개선](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="daf40-183">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="daf40-184">변조 보호 범위 확장</span><span class="sxs-lookup"><span data-stu-id="daf40-184">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="daf40-185">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="daf40-185">Known Issues</span></span>
<span data-ttu-id="daf40-186">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="daf40-186">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="daf40-187">2021년 1월(플랫폼: 4.18.2101.9 | 엔진: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="daf40-187">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="daf40-188">&ensp;보안 인텔리전스 업데이트 버전: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="daf40-188">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="daf40-189">&ensp;릴리스: **2021년 2월 2일**</span><span class="sxs-lookup"><span data-stu-id="daf40-189">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="daf40-190">&ensp;플랫폼: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="daf40-190">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="daf40-191">&ensp;엔진: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="daf40-191">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="daf40-192">&ensp;지원 단계: **기술 업그레이드 지원(전용)**</span><span class="sxs-lookup"><span data-stu-id="daf40-192">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="daf40-193">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="daf40-193">What's new</span></span>

- <span data-ttu-id="daf40-194">셸 코드 악용 감지 개선</span><span class="sxs-lookup"><span data-stu-id="daf40-194">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="daf40-195">자격 증명 도용 시도에 대한 가시성 향상</span><span class="sxs-lookup"><span data-stu-id="daf40-195">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="daf40-196">서비스에서 향상된 Microsoft Defender 바이러스 백신 기능</span><span class="sxs-lookup"><span data-stu-id="daf40-196">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="daf40-197">x64 에뮬 ARM 지원 개선</span><span class="sxs-lookup"><span data-stu-id="daf40-197">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="daf40-198">해결 방법: EDR 보호가 초기 검색을 수행한 후 위협 기록에 차단 알림이 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="daf40-198">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="daf40-199">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="daf40-199">Known Issues</span></span>
<span data-ttu-id="daf40-200">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="daf40-200">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="daf40-201">2020년 11월-2020년 11월(플랫폼: 4.18.2011.6 | 엔진: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="daf40-201">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="daf40-202">&ensp;보안 인텔리전스 업데이트 버전: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="daf40-202">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="daf40-203">&ensp;릴리스: **2020년 12월 3일**</span><span class="sxs-lookup"><span data-stu-id="daf40-203">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="daf40-204">&ensp;플랫폼: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="daf40-204">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="daf40-205">&ensp;엔진: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="daf40-205">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="daf40-206">&ensp;지원 단계: **기술 업그레이드 지원(전용)**</span><span class="sxs-lookup"><span data-stu-id="daf40-206">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="daf40-207">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="daf40-207">What's new</span></span>

- <span data-ttu-id="daf40-208">향상된 [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) 상태 지원 로깅</span><span class="sxs-lookup"><span data-stu-id="daf40-208">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="daf40-209">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="daf40-209">Known Issues</span></span>
<span data-ttu-id="daf40-210">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="daf40-210">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="daf40-211">2020년 10월(플랫폼: 4.18.2010.7 | 엔진: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="daf40-211">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="daf40-212">&ensp;보안 인텔리전스 업데이트 버전: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="daf40-212">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="daf40-213">&ensp;릴리스: **2020년 10월 29일**</span><span class="sxs-lookup"><span data-stu-id="daf40-213">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="daf40-214">&ensp;플랫폼: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="daf40-214">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="daf40-215">&ensp;엔진: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="daf40-215">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="daf40-216">&ensp;지원 단계: **기술 업그레이드 지원(전용)**</span><span class="sxs-lookup"><span data-stu-id="daf40-216">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="daf40-217">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="daf40-217">What's new</span></span>

- <span data-ttu-id="daf40-218">특수 위협 범주에 대한 새 설명</span><span class="sxs-lookup"><span data-stu-id="daf40-218">New descriptions for special threat categories</span></span>
- <span data-ttu-id="daf40-219">향상된 에뮬ation 기능</span><span class="sxs-lookup"><span data-stu-id="daf40-219">Improved emulation capabilities</span></span>
- <span data-ttu-id="daf40-220">향상된 호스트 주소 허용/차단 기능</span><span class="sxs-lookup"><span data-stu-id="daf40-220">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="daf40-221">Defender CSP의 새 옵션에서 로컬 사용자 제외의 무시</span><span class="sxs-lookup"><span data-stu-id="daf40-221">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="daf40-222">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="daf40-222">Known Issues</span></span>

<span data-ttu-id="daf40-223">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="daf40-223">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="daf40-224">2020년 9월(플랫폼: 4.18.2009.7 | 엔진: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="daf40-224">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="daf40-225">&ensp;보안 인텔리전스 업데이트 버전: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="daf40-225">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="daf40-226">&ensp;릴리스: **2020년 10월 1일**</span><span class="sxs-lookup"><span data-stu-id="daf40-226">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="daf40-227">&ensp;플랫폼: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="daf40-227">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="daf40-228">&ensp;엔진: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="daf40-228">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="daf40-229">&ensp;지원 단계: **기술 업그레이드 지원(전용)**</span><span class="sxs-lookup"><span data-stu-id="daf40-229">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="daf40-230">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="daf40-230">What's new</span></span>

- <span data-ttu-id="daf40-231">파일을 Quarantine에서 복원하려면 관리자 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="daf40-231">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="daf40-232">이제 XML 형식 이벤트가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="daf40-232">XML formatted events are now supported</span></span>
- <span data-ttu-id="daf40-233">제외 병합을 외면하기 위한 CSP 지원</span><span class="sxs-lookup"><span data-stu-id="daf40-233">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="daf40-234">새 관리 인터페이스:</span><span class="sxs-lookup"><span data-stu-id="daf40-234">New management interfaces for:</span></span>
   - <span data-ttu-id="daf40-235">UDP 검사</span><span class="sxs-lookup"><span data-stu-id="daf40-235">UDP Inspection</span></span>
   - <span data-ttu-id="daf40-236">Server 2019의 네트워크 보호</span><span class="sxs-lookup"><span data-stu-id="daf40-236">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="daf40-237">네트워크 보호를 위한 IP 주소 제외</span><span class="sxs-lookup"><span data-stu-id="daf40-237">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="daf40-238">TPM 측정에 대한 가시성 향상</span><span class="sxs-lookup"><span data-stu-id="daf40-238">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="daf40-239">VBA 모듈 Office 향상</span><span class="sxs-lookup"><span data-stu-id="daf40-239">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="daf40-240">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="daf40-240">Known Issues</span></span>

<span data-ttu-id="daf40-241">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="daf40-241">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="daf40-242">2020년 8월(플랫폼: 4.18.2008.9 | 엔진: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="daf40-242">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="daf40-243">&ensp;보안 인텔리전스 업데이트 버전: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="daf40-243">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="daf40-244">&ensp;릴리스: **2020년 8월 27일**</span><span class="sxs-lookup"><span data-stu-id="daf40-244">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="daf40-245">&ensp;플랫폼: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="daf40-245">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="daf40-246">&ensp;엔진: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="daf40-246">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="daf40-247">&ensp;지원 단계: **기술 업그레이드 지원(전용)**</span><span class="sxs-lookup"><span data-stu-id="daf40-247">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="daf40-248">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="daf40-248">What's new</span></span>

- <span data-ttu-id="daf40-249">원격 분석 이벤트 추가</span><span class="sxs-lookup"><span data-stu-id="daf40-249">Add more telemetry events</span></span>
- <span data-ttu-id="daf40-250">향상된 검사 이벤트 원격 분석</span><span class="sxs-lookup"><span data-stu-id="daf40-250">Improved scan event telemetry</span></span>
- <span data-ttu-id="daf40-251">메모리 검사에 대한 향상된 동작 모니터링</span><span class="sxs-lookup"><span data-stu-id="daf40-251">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="daf40-252">향상된 매크로 스트림 검사</span><span class="sxs-lookup"><span data-stu-id="daf40-252">Improved macro streams scanning</span></span>
- <span data-ttu-id="daf40-253">`AMRunningMode`PowerShell cmdlet에 Get-MpComputerStatus 추가</span><span class="sxs-lookup"><span data-stu-id="daf40-253">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="daf40-254">[DisableAntiSpyware는](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="daf40-254">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="daf40-255">Microsoft Defender 바이러스 백신 바이러스 백신 프로그램을 검색하면 자동으로 꺼집니다.</span><span class="sxs-lookup"><span data-stu-id="daf40-255">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="daf40-256">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="daf40-256">Known Issues</span></span>
<span data-ttu-id="daf40-257">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="daf40-257">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="daf40-258">2020년 7월(플랫폼: 4.18.2007.8 | 엔진: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="daf40-258">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="daf40-259">&ensp;보안 인텔리전스 업데이트 버전: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="daf40-259">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="daf40-260">&ensp;릴리스: **2020년 7월 28일**</span><span class="sxs-lookup"><span data-stu-id="daf40-260">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="daf40-261">&ensp;플랫폼: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="daf40-261">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="daf40-262">&ensp;엔진: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="daf40-262">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="daf40-263">&ensp;지원 단계: **기술 업그레이드 지원(전용)**</span><span class="sxs-lookup"><span data-stu-id="daf40-263">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="daf40-264">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="daf40-264">What's new</span></span>

- <span data-ttu-id="daf40-265">BITS에 대한 향상된 원격 분석</span><span class="sxs-lookup"><span data-stu-id="daf40-265">Improved telemetry for BITS</span></span>
- <span data-ttu-id="daf40-266">Authenticode 코드 서명 인증서 유효성 검사 개선</span><span class="sxs-lookup"><span data-stu-id="daf40-266">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="daf40-267">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="daf40-267">Known Issues</span></span>
<span data-ttu-id="daf40-268">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="daf40-268">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="daf40-269">2020년 6월(플랫폼: 4.18.2006.10 | 엔진: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="daf40-269">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="daf40-270">&ensp;보안 인텔리전스 업데이트 버전: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="daf40-270">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="daf40-271">&ensp;릴리스: **2020년 6월 22일**</span><span class="sxs-lookup"><span data-stu-id="daf40-271">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="daf40-272">&ensp;플랫폼: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="daf40-272">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="daf40-273">&ensp;엔진: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="daf40-273">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="daf40-274">&ensp;지원 단계: **기술 업그레이드 지원(전용)**</span><span class="sxs-lookup"><span data-stu-id="daf40-274">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="daf40-275">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="daf40-275">What's new</span></span>

- <span data-ttu-id="daf40-276">지원 [로그의 위치를 지정할 수 있습니다.](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="daf40-276">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="daf40-277">수동 모드에서 적극적인 catchup 검사 건너뛰기</span><span class="sxs-lookup"><span data-stu-id="daf40-277">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="daf40-278">데이터 데이터 연결에서 Defender 업데이트 허용</span><span class="sxs-lookup"><span data-stu-id="daf40-278">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="daf40-279">캐싱을 사용하지 않도록 설정한 경우의 고정 성능 조정</span><span class="sxs-lookup"><span data-stu-id="daf40-279">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="daf40-280">고정 레지스트리 쿼리</span><span class="sxs-lookup"><span data-stu-id="daf40-280">Fixed registry query</span></span> 
- <span data-ttu-id="daf40-281">ADMX의 검사 시간 임의 지정 수정</span><span class="sxs-lookup"><span data-stu-id="daf40-281">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="daf40-282">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="daf40-282">Known Issues</span></span>
<span data-ttu-id="daf40-283">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="daf40-283">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="daf40-284">2020년 5월(플랫폼: 4.18.2005.4 | 엔진: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="daf40-284">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="daf40-285">&ensp;보안 인텔리전스 업데이트 버전: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="daf40-285">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="daf40-286">&ensp;릴리스: **2020년 5월 26일**</span><span class="sxs-lookup"><span data-stu-id="daf40-286">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="daf40-287">&ensp;플랫폼: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="daf40-287">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="daf40-288">&ensp;엔진: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="daf40-288">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="daf40-289">&ensp;지원 단계: **기술 업그레이드 지원(전용)**</span><span class="sxs-lookup"><span data-stu-id="daf40-289">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="daf40-290">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="daf40-290">What's new</span></span>

- <span data-ttu-id="daf40-291">검사 이벤트에 대한 로깅 개선</span><span class="sxs-lookup"><span data-stu-id="daf40-291">Improved logging for scan events</span></span>
- <span data-ttu-id="daf40-292">향상된 사용자 모드 크래시 처리.</span><span class="sxs-lookup"><span data-stu-id="daf40-292">Improved user mode crash handling.</span></span>
- <span data-ttu-id="daf40-293">변조 방지를 위한 이벤트 추적이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="daf40-293">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="daf40-294">AMSI 샘플 제출 수정</span><span class="sxs-lookup"><span data-stu-id="daf40-294">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="daf40-295">AMSI 클라우드 차단 수정</span><span class="sxs-lookup"><span data-stu-id="daf40-295">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="daf40-296">고정 보안 업데이트 설치 로그</span><span class="sxs-lookup"><span data-stu-id="daf40-296">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="daf40-297">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="daf40-297">Known Issues</span></span>
<span data-ttu-id="daf40-298">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="daf40-298">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="daf40-299">2020년 4월(플랫폼: 4.18.2004.6 | 엔진: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="daf40-299">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="daf40-300">&ensp;보안 인텔리전스 업데이트 버전: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="daf40-300">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="daf40-301">&ensp;릴리스: **2020년 4월 30일**</span><span class="sxs-lookup"><span data-stu-id="daf40-301">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="daf40-302">&ensp;플랫폼: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="daf40-302">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="daf40-303">&ensp;엔진: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="daf40-303">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="daf40-304">&ensp;지원 단계: **기술 업그레이드 지원(전용)**</span><span class="sxs-lookup"><span data-stu-id="daf40-304">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="daf40-305">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="daf40-305">What's new</span></span>
- <span data-ttu-id="daf40-306">WDfilter 개선</span><span class="sxs-lookup"><span data-stu-id="daf40-306">WDfilter improvements</span></span>
- <span data-ttu-id="daf40-307">더 실행 가능한 이벤트 데이터를 추가하여 표면 감소 감지 이벤트 공격</span><span class="sxs-lookup"><span data-stu-id="daf40-307">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="daf40-308">진단 데이터 및 WMI의 고정 버전 정보</span><span class="sxs-lookup"><span data-stu-id="daf40-308">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="daf40-309">플랫폼 업데이트 후 UI에서 잘못된 플랫폼 버전 수정</span><span class="sxs-lookup"><span data-stu-id="daf40-309">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="daf40-310">파일 없는 위협 방지를 위한 동적 URL intel</span><span class="sxs-lookup"><span data-stu-id="daf40-310">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="daf40-311">UEFI 검사 기능</span><span class="sxs-lookup"><span data-stu-id="daf40-311">UEFI scan capability</span></span>
- <span data-ttu-id="daf40-312">업데이트 로깅 확장</span><span class="sxs-lookup"><span data-stu-id="daf40-312">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="daf40-313">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="daf40-313">Known Issues</span></span>
<span data-ttu-id="daf40-314">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="daf40-314">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="daf40-315">2020년 3월(플랫폼: 4.18.2003.8 | 엔진: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="daf40-315">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="daf40-316">&ensp;보안 인텔리전스 업데이트 버전: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="daf40-316">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="daf40-317">&ensp;릴리스: **2020년 3월 24일**</span><span class="sxs-lookup"><span data-stu-id="daf40-317">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="daf40-318">&ensp;플랫폼: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="daf40-318">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="daf40-319">&ensp;엔진: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="daf40-319">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="daf40-320">&ensp;지원 단계: **기술 업그레이드 지원(전용)**</span><span class="sxs-lookup"><span data-stu-id="daf40-320">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="daf40-321">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="daf40-321">What's new</span></span>

- <span data-ttu-id="daf40-322">[MpCmdRun에](./command-line-arguments-microsoft-defender-antivirus.md) 추가된 CPU 스로틀 옵션</span><span class="sxs-lookup"><span data-stu-id="daf40-322">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="daf40-323">진단 기능 개선</span><span class="sxs-lookup"><span data-stu-id="daf40-323">Improve diagnostic capability</span></span>
- <span data-ttu-id="daf40-324">보안 인텔리전스 시간 제한 단축(5분)</span><span class="sxs-lookup"><span data-stu-id="daf40-324">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="daf40-325">AMSI 엔진 내부 로그 기능 확장</span><span class="sxs-lookup"><span data-stu-id="daf40-325">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="daf40-326">프로세스 차단에 대한 알림 개선</span><span class="sxs-lookup"><span data-stu-id="daf40-326">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="daf40-327">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="daf40-327">Known Issues</span></span>
<span data-ttu-id="daf40-328">[**Fixed**] Microsoft Defender 바이러스 백신 실행 시 파일을 건너뛰고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="daf40-328">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="daf40-329">2020년 2월(플랫폼: - | 엔진: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="daf40-329">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="daf40-330">&ensp;보안 인텔리전스 업데이트 버전: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="daf40-330">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="daf40-331">&ensp;릴리스: **2020년 2월 25일**</span><span class="sxs-lookup"><span data-stu-id="daf40-331">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="daf40-332">&ensp;플랫폼/클라이언트: **-**</span><span class="sxs-lookup"><span data-stu-id="daf40-332">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="daf40-333">&ensp;엔진: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="daf40-333">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="daf40-334">&ensp;지원 단계: **기술 업그레이드 지원(전용)**</span><span class="sxs-lookup"><span data-stu-id="daf40-334">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="daf40-335">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="daf40-335">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="daf40-336">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="daf40-336">Known Issues</span></span>
<span data-ttu-id="daf40-337">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="daf40-337">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="daf40-338">2020년 1월(플랫폼: 4.18.2001.10 | 엔진: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="daf40-338">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="daf40-339">보안 인텔리전스 업데이트 버전: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="daf40-339">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="daf40-340">릴리스: **2020년 1월 30일**</span><span class="sxs-lookup"><span data-stu-id="daf40-340">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="daf40-341">플랫폼/클라이언트: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="daf40-341">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="daf40-342">엔진: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="daf40-342">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="daf40-343">&ensp;지원 단계: **기술 업그레이드 지원(전용)**</span><span class="sxs-lookup"><span data-stu-id="daf40-343">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="daf40-344">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="daf40-344">What's new</span></span>

- <span data-ttu-id="daf40-345">WS2016의 고정 BSOD 및 Exchange</span><span class="sxs-lookup"><span data-stu-id="daf40-345">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="daf40-346">TMP가 네트워크 경로로 리디렉션될 때 플랫폼 업데이트 지원</span><span class="sxs-lookup"><span data-stu-id="daf40-346">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="daf40-347">플랫폼 및 엔진 버전이 [WDSI에 추가됩니다.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="daf40-347">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="daf40-348">긴급 서명 업데이트를 [수동 모드로 확장](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="daf40-348">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="daf40-349">4.18.1911.3 중단 수정</span><span class="sxs-lookup"><span data-stu-id="daf40-349">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="daf40-350">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="daf40-350">Known Issues</span></span>

<span data-ttu-id="daf40-351">[**고정**] [](/windows-hardware/design/device-experiences/modern-standby) 최신 대기 모드를 활용하는 장치는 보호의 간격을 Windows Defender 필터 드라이버가 중단될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="daf40-351">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="daf40-352">영향을 받는 컴퓨터는 최신 맬웨어 방지 플랫폼으로 업데이트되지 않은 것으로 고객에게 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="daf40-352">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="daf40-353">이 업데이트는:</span><span class="sxs-lookup"><span data-stu-id="daf40-353">This update is:</span></span>
> - <span data-ttu-id="daf40-354">SHA2를 지원하기 위해 더 낮은 버전의 플랫폼을 실행하는 RS1 장치에서 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="daf40-354">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="daf40-355">문제가 있는 시스템에 대한 재부팅 플래그가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="daf40-355">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="daf40-356">는 2020년 4월에 다시 출시될 예정으로, 향후 가용성을 유지하기 위해 최신 업데이트로 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="daf40-356">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="daf40-357">는 재부팅 요구 사항으로 인해 업데이트로 분류됩니다. 및</span><span class="sxs-lookup"><span data-stu-id="daf40-357">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="daf40-358">는 업데이트 [에서만 Windows 있습니다.](https://support.microsoft.com/help/4027667/windows-10-update)</span><span class="sxs-lookup"><span data-stu-id="daf40-358">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="daf40-359">2019년 11월부터 2019년 11월까지(플랫폼: 4.18.1911.3 | 엔진: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="daf40-359">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="daf40-360">보안 인텔리전스 업데이트 버전: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="daf40-360">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="daf40-361">릴리스: **2019년 12월 7일**</span><span class="sxs-lookup"><span data-stu-id="daf40-361">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="daf40-362">플랫폼: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="daf40-362">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="daf40-363">엔진: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="daf40-363">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="daf40-364">지원 단계: **지원 없음**</span><span class="sxs-lookup"><span data-stu-id="daf40-364">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="daf40-365">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="daf40-365">What's new</span></span>

- <span data-ttu-id="daf40-366">고정 MpCmdRun 추적 수준</span><span class="sxs-lookup"><span data-stu-id="daf40-366">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="daf40-367">WDFilter 버전 정보 수정</span><span class="sxs-lookup"><span data-stu-id="daf40-367">Fixed WDFilter version info</span></span>
- <span data-ttu-id="daf40-368">알림 개선(PUA)</span><span class="sxs-lookup"><span data-stu-id="daf40-368">Improve notifications (PUA)</span></span>
- <span data-ttu-id="daf40-369">MRT 로그를 추가하여 파일 지원</span><span class="sxs-lookup"><span data-stu-id="daf40-369">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="daf40-370">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="daf40-370">Known Issues</span></span>
<span data-ttu-id="daf40-371">이 업데이트를 설치하면 디바이스에서 점프 패키지 4.18.2001.10을 최신 플랫폼 버전으로 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="daf40-371">When this update is installed, the device needs the jump package 4.18.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="daf40-372">Microsoft Defender 바이러스 백신 플랫폼 지원</span><span class="sxs-lookup"><span data-stu-id="daf40-372">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="daf40-373">플랫폼 및 엔진 업데이트는 월별 케이던스에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="daf40-373">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="daf40-374">완전히 지원받기 위해 최신 플랫폼 업데이트를 최신으로 유지하세요.</span><span class="sxs-lookup"><span data-stu-id="daf40-374">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="daf40-375">지원 구조는 동적이며, 최신 플랫폼 버전의 가용성에 따라 다음 두 단계로 진화합니다.</span><span class="sxs-lookup"><span data-stu-id="daf40-375">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="daf40-376">**보안 및** 중요 업데이트 서비스 단계 - 최신 플랫폼 버전을 실행하는 경우 맬웨어 방지 플랫폼에 대한 보안 및 중요 업데이트를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="daf40-376">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="daf40-377">**기술 지원(전용) 단계** - 새 플랫폼 버전이 출시된 후 이전 버전(N-2)에 대한 지원은 기술 지원으로만 축소됩니다.</span><span class="sxs-lookup"><span data-stu-id="daf40-377">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="daf40-378">N-2 이전의 플랫폼 버전은 더 이상 지원되지 않습니다.\*</span><span class="sxs-lookup"><span data-stu-id="daf40-378">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="daf40-379">\*기술 지원은 Windows 10 릴리스 버전에서 최신 플랫폼 버전으로의 업그레이드를 위해 계속 [제공됩니다(Windows 10](#platform-version-included-with-windows-10-releases)릴리스에 포함된 플랫폼 버전 참조).</span><span class="sxs-lookup"><span data-stu-id="daf40-379">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="daf40-380">기술 지원(전용) 단계 중에는 상업적으로 합리적인 지원 인시던트가 Microsoft 고객 서비스 & 지원 및 Microsoft의 관리 지원 서비스(예: 프리미어 지원)를 통해 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="daf40-380">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="daf40-381">지원 인시던트가 추가 지침을 위해 개발로 에스컬레이터해야 하는 경우, 비보안 업데이트가 필요하거나, 보안 업데이트가 필요한 경우 고객에게 최신 플랫폼 버전 또는 중간 업데이트(\*)로 업그레이드할지 묻는 요청이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="daf40-381">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="daf40-382">릴리스에 포함된 플랫폼 Windows 10 버전</span><span class="sxs-lookup"><span data-stu-id="daf40-382">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="daf40-383">아래 표에는 최신 Microsoft Defender 바이러스 백신 함께 제공된 플랫폼 및 엔진 버전이 Windows 10 있습니다.</span><span class="sxs-lookup"><span data-stu-id="daf40-383">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="daf40-384">Windows 10 릴리스</span><span class="sxs-lookup"><span data-stu-id="daf40-384">Windows 10 release</span></span>  |<span data-ttu-id="daf40-385">플랫폼 버전</span><span class="sxs-lookup"><span data-stu-id="daf40-385">Platform version</span></span>  |<span data-ttu-id="daf40-386">엔진 버전</span><span class="sxs-lookup"><span data-stu-id="daf40-386">Engine version</span></span> |<span data-ttu-id="daf40-387">지원 단계</span><span class="sxs-lookup"><span data-stu-id="daf40-387">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="daf40-388">2004(20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="daf40-388">2004  (20H1/20H2)</span></span> |<span data-ttu-id="daf40-389">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="daf40-389">4.18.1909.6</span></span> |<span data-ttu-id="daf40-390">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="daf40-390">1.1.17000.2</span></span> | <span data-ttu-id="daf40-391">기술 업그레이드 지원(전용)</span><span class="sxs-lookup"><span data-stu-id="daf40-391">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="daf40-392">1909(19H2)</span><span class="sxs-lookup"><span data-stu-id="daf40-392">1909  (19H2)</span></span> |<span data-ttu-id="daf40-393">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="daf40-393">4.18.1902.5</span></span> |<span data-ttu-id="daf40-394">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="daf40-394">1.1.16700.3</span></span> | <span data-ttu-id="daf40-395">기술 업그레이드 지원(전용)</span><span class="sxs-lookup"><span data-stu-id="daf40-395">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="daf40-396">1903(19H1)</span><span class="sxs-lookup"><span data-stu-id="daf40-396">1903  (19H1)</span></span> |<span data-ttu-id="daf40-397">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="daf40-397">4.18.1902.5</span></span> |<span data-ttu-id="daf40-398">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="daf40-398">1.1.15600.4</span></span> | <span data-ttu-id="daf40-399">기술 업그레이드 지원(전용)</span><span class="sxs-lookup"><span data-stu-id="daf40-399">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="daf40-400">1809(RS5)</span><span class="sxs-lookup"><span data-stu-id="daf40-400">1809  (RS5)</span></span> |<span data-ttu-id="daf40-401">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="daf40-401">4.18.1807.18075</span></span> |<span data-ttu-id="daf40-402">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="daf40-402">1.1.15000.2</span></span> | <span data-ttu-id="daf40-403">기술 업그레이드 지원(전용)</span><span class="sxs-lookup"><span data-stu-id="daf40-403">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="daf40-404">1803(RS4)</span><span class="sxs-lookup"><span data-stu-id="daf40-404">1803  (RS4)</span></span> |<span data-ttu-id="daf40-405">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="daf40-405">4.13.17134.1</span></span> |<span data-ttu-id="daf40-406">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="daf40-406">1.1.14600.4</span></span> | <span data-ttu-id="daf40-407">기술 업그레이드 지원(전용)</span><span class="sxs-lookup"><span data-stu-id="daf40-407">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="daf40-408">1709(RS3)</span><span class="sxs-lookup"><span data-stu-id="daf40-408">1709  (RS3)</span></span> |<span data-ttu-id="daf40-409">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="daf40-409">4.12.16299.15</span></span> |<span data-ttu-id="daf40-410">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="daf40-410">1.1.14104.0</span></span> | <span data-ttu-id="daf40-411">기술 업그레이드 지원(전용)</span><span class="sxs-lookup"><span data-stu-id="daf40-411">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="daf40-412">1703(RS2)</span><span class="sxs-lookup"><span data-stu-id="daf40-412">1703  (RS2)</span></span> |<span data-ttu-id="daf40-413">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="daf40-413">4.11.15603.2</span></span> |<span data-ttu-id="daf40-414">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="daf40-414">1.1.13504.0</span></span> | <span data-ttu-id="daf40-415">기술 업그레이드 지원(전용)</span><span class="sxs-lookup"><span data-stu-id="daf40-415">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="daf40-416">1607(RS1)</span><span class="sxs-lookup"><span data-stu-id="daf40-416">1607 (RS1)</span></span> |<span data-ttu-id="daf40-417">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="daf40-417">4.10.14393.3683</span></span> |<span data-ttu-id="daf40-418">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="daf40-418">1.1.12805.0</span></span> | <span data-ttu-id="daf40-419">기술 업그레이드 지원(전용)</span><span class="sxs-lookup"><span data-stu-id="daf40-419">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="daf40-420">릴리스 Windows 10 자세한 내용은 수명 주기 Windows [시트를 참조하세요.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)</span><span class="sxs-lookup"><span data-stu-id="daf40-420">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="daf40-421">DISM(배포 이미지 서비스 및 관리)에 대한 업데이트</span><span class="sxs-lookup"><span data-stu-id="daf40-421">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="daf40-422">최신 바이러스 백신 및 맬웨어 방지 업데이트로 Windows 10(Enterprise, Pro 및 Home edition), Windows Server 2019 및 Windows Server 2016 OS 설치 이미지를 업데이트하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="daf40-422">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="daf40-423">OS 설치 이미지를 최신으로 유지하면 보호 격차를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="daf40-423">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="daf40-424">자세한 내용은 운영 체제 설치 Windows Microsoft [Defender 업데이트를 참조하세요.](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)</span><span class="sxs-lookup"><span data-stu-id="daf40-424">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="daf40-425">1.1.2106.01</span><span class="sxs-lookup"><span data-stu-id="daf40-425">1.1.2106.01</span></span></summary>

<span data-ttu-id="daf40-426">&ensp;패키지 버전: **1.1.2106.01**  </span><span class="sxs-lookup"><span data-stu-id="daf40-426">&ensp;Package version: **1.1.2106.01**  </span></span>  
<span data-ttu-id="daf40-427">&ensp;플랫폼 버전: **4.18.2104.14** </span><span class="sxs-lookup"><span data-stu-id="daf40-427">&ensp;Platform version: **4.18.2104.14** </span></span>  
<span data-ttu-id="daf40-428">&ensp;엔진 버전: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="daf40-428">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="daf40-429">&ensp;서명 버전: **1.339.1923.0**</span><span class="sxs-lookup"><span data-stu-id="daf40-429">&ensp;Signature version: **1.339.1923.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="daf40-430">수정</span><span class="sxs-lookup"><span data-stu-id="daf40-430">Fixes</span></span>
- <span data-ttu-id="daf40-431">없음</span><span class="sxs-lookup"><span data-stu-id="daf40-431">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="daf40-432">추가 정보</span><span class="sxs-lookup"><span data-stu-id="daf40-432">Additional information</span></span>
- <span data-ttu-id="daf40-433">없음</span><span class="sxs-lookup"><span data-stu-id="daf40-433">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="daf40-434">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="daf40-434">1.1.2105.01</span></span></summary>

<span data-ttu-id="daf40-435">&ensp;패키지 버전: **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="daf40-435">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="daf40-436">&ensp;플랫폼 버전: **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="daf40-436">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="daf40-437">&ensp;엔진 버전: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="daf40-437">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="daf40-438">&ensp;서명 버전: **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="daf40-438">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="daf40-439">수정</span><span class="sxs-lookup"><span data-stu-id="daf40-439">Fixes</span></span>
- <span data-ttu-id="daf40-440">없음</span><span class="sxs-lookup"><span data-stu-id="daf40-440">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="daf40-441">추가 정보</span><span class="sxs-lookup"><span data-stu-id="daf40-441">Additional information</span></span>
- <span data-ttu-id="daf40-442">없음</span><span class="sxs-lookup"><span data-stu-id="daf40-442">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="daf40-443">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="daf40-443">1.1.2104.01</span></span></summary>

<span data-ttu-id="daf40-444">&ensp;패키지 버전: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="daf40-444">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="daf40-445">&ensp;플랫폼 버전: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="daf40-445">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="daf40-446">&ensp;엔진 버전: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="daf40-446">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="daf40-447">&ensp;서명 버전: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="daf40-447">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="daf40-448">수정</span><span class="sxs-lookup"><span data-stu-id="daf40-448">Fixes</span></span>
- <span data-ttu-id="daf40-449">없음</span><span class="sxs-lookup"><span data-stu-id="daf40-449">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="daf40-450">추가 정보</span><span class="sxs-lookup"><span data-stu-id="daf40-450">Additional information</span></span>
- <span data-ttu-id="daf40-451">없음</span><span class="sxs-lookup"><span data-stu-id="daf40-451">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="daf40-452">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="daf40-452">1.1.2103.01</span></span></summary>

<span data-ttu-id="daf40-453">&ensp;패키지 버전: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="daf40-453">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="daf40-454">&ensp;플랫폼 버전: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="daf40-454">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="daf40-455">&ensp;엔진 버전: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="daf40-455">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="daf40-456">&ensp;서명 버전: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="daf40-456">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="daf40-457">수정</span><span class="sxs-lookup"><span data-stu-id="daf40-457">Fixes</span></span>
- <span data-ttu-id="daf40-458">없음</span><span class="sxs-lookup"><span data-stu-id="daf40-458">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="daf40-459">추가 정보</span><span class="sxs-lookup"><span data-stu-id="daf40-459">Additional information</span></span>
- <span data-ttu-id="daf40-460">없음</span><span class="sxs-lookup"><span data-stu-id="daf40-460">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="daf40-461">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="daf40-461">1.1.2102.03</span></span></summary>

<span data-ttu-id="daf40-462">&ensp;패키지 버전: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="daf40-462">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="daf40-463">&ensp;플랫폼 버전: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="daf40-463">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="daf40-464">&ensp;엔진 버전: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="daf40-464">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="daf40-465">&ensp;서명 버전: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="daf40-465">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="daf40-466">수정</span><span class="sxs-lookup"><span data-stu-id="daf40-466">Fixes</span></span>
- <span data-ttu-id="daf40-467">없음</span><span class="sxs-lookup"><span data-stu-id="daf40-467">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="daf40-468">추가 정보</span><span class="sxs-lookup"><span data-stu-id="daf40-468">Additional information</span></span>
- <span data-ttu-id="daf40-469">없음</span><span class="sxs-lookup"><span data-stu-id="daf40-469">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="daf40-470">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="daf40-470">1.1.2101.02</span></span></summary>

<span data-ttu-id="daf40-471">&ensp;패키지 버전: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="daf40-471">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="daf40-472">&ensp;플랫폼 버전: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="daf40-472">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="daf40-473">&ensp;엔진 버전: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="daf40-473">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="daf40-474">&ensp;서명 버전: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="daf40-474">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="daf40-475">수정</span><span class="sxs-lookup"><span data-stu-id="daf40-475">Fixes</span></span>
- <span data-ttu-id="daf40-476">없음</span><span class="sxs-lookup"><span data-stu-id="daf40-476">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="daf40-477">추가 정보</span><span class="sxs-lookup"><span data-stu-id="daf40-477">Additional information</span></span>
- <span data-ttu-id="daf40-478">없음</span><span class="sxs-lookup"><span data-stu-id="daf40-478">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="daf40-479">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="daf40-479">1.1.2012.01</span></span></summary>

<span data-ttu-id="daf40-480">&ensp;패키지 버전: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="daf40-480">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="daf40-481">&ensp;플랫폼 버전: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="daf40-481">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="daf40-482">&ensp;엔진 버전: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="daf40-482">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="daf40-483">&ensp;서명 버전: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="daf40-483">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="daf40-484">수정</span><span class="sxs-lookup"><span data-stu-id="daf40-484">Fixes</span></span>
- <span data-ttu-id="daf40-485">없음</span><span class="sxs-lookup"><span data-stu-id="daf40-485">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="daf40-486">추가 정보</span><span class="sxs-lookup"><span data-stu-id="daf40-486">Additional information</span></span>
- <span data-ttu-id="daf40-487">없음</span><span class="sxs-lookup"><span data-stu-id="daf40-487">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="daf40-488">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="daf40-488">1.1.2011.02</span></span></summary>

<span data-ttu-id="daf40-489">&ensp;패키지 버전: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="daf40-489">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="daf40-490">&ensp;플랫폼 버전: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="daf40-490">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="daf40-491">&ensp;엔진 버전: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="daf40-491">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="daf40-492">&ensp;서명 버전: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="daf40-492">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="daf40-493">수정</span><span class="sxs-lookup"><span data-stu-id="daf40-493">Fixes</span></span>
- <span data-ttu-id="daf40-494">없음</span><span class="sxs-lookup"><span data-stu-id="daf40-494">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="daf40-495">추가 정보</span><span class="sxs-lookup"><span data-stu-id="daf40-495">Additional information</span></span>
- <span data-ttu-id="daf40-496">새로 고쳐진 Microsoft Defender 바이러스 백신 서명</span><span class="sxs-lookup"><span data-stu-id="daf40-496">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="daf40-497">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="daf40-497">1.1.2011.01</span></span></summary>

<span data-ttu-id="daf40-498">&ensp;패키지 버전: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="daf40-498">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="daf40-499">&ensp;플랫폼 버전: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="daf40-499">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="daf40-500">&ensp;엔진 버전: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="daf40-500">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="daf40-501">&ensp;서명 버전: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="daf40-501">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="daf40-502">수정</span><span class="sxs-lookup"><span data-stu-id="daf40-502">Fixes</span></span>
- <span data-ttu-id="daf40-503">없음</span><span class="sxs-lookup"><span data-stu-id="daf40-503">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="daf40-504">추가 정보</span><span class="sxs-lookup"><span data-stu-id="daf40-504">Additional information</span></span>
- <span data-ttu-id="daf40-505">없음</span><span class="sxs-lookup"><span data-stu-id="daf40-505">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="daf40-506">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="daf40-506">1.1.2009.10</span></span></summary>

<span data-ttu-id="daf40-507">&ensp;패키지 버전: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="daf40-507">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="daf40-508">&ensp;플랫폼 버전: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="daf40-508">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="daf40-509">&ensp;엔진 버전: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="daf40-509">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="daf40-510">&ensp;서명 버전: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="daf40-510">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="daf40-511">수정</span><span class="sxs-lookup"><span data-stu-id="daf40-511">Fixes</span></span>
- <span data-ttu-id="daf40-512">없음</span><span class="sxs-lookup"><span data-stu-id="daf40-512">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="daf40-513">추가 정보</span><span class="sxs-lookup"><span data-stu-id="daf40-513">Additional information</span></span>
- <span data-ttu-id="daf40-514">RS1 Windows 10 OS 설치 이미지에 대한 지원이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="daf40-514">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="daf40-515">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="daf40-515">Additional resources</span></span>

| <span data-ttu-id="daf40-516">문서</span><span class="sxs-lookup"><span data-stu-id="daf40-516">Article</span></span> | <span data-ttu-id="daf40-517">설명</span><span class="sxs-lookup"><span data-stu-id="daf40-517">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="daf40-518">운영 체제 설치 Windows 대한 Microsoft Defender 업데이트</span><span class="sxs-lookup"><span data-stu-id="daf40-518">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="daf40-519">OS 설치 이미지(WIM 및 VHD 파일)에 대한 맬웨어 방지 업데이트 패키지를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="daf40-519">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="daf40-520">Microsoft Defender 바이러스 백신(Windows 10 Enterprise, Pro 및 Home edition), Windows Server 2019 및 Windows Server 2016 설치 이미지에 대한 Windows Server 2016 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="daf40-520">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="daf40-521">보호 업데이트를 다운로드하고 적용하는 방법 관리</span><span class="sxs-lookup"><span data-stu-id="daf40-521">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="daf40-522">보호 업데이트는 여러 소스를 통해 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="daf40-522">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="daf40-523">보호 업데이트를 다운로드하고 적용해야 하는 경우 관리</span><span class="sxs-lookup"><span data-stu-id="daf40-523">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="daf40-524">보호 업데이트를 다운로드해야 하는 경우를 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="daf40-524">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="daf40-525">최신이 지난 끝점에 대한 업데이트 관리</span><span class="sxs-lookup"><span data-stu-id="daf40-525">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="daf40-526">끝점에서 업데이트 또는 예약된 검사가 누락된 경우 다음에 사용자가 로그인할 때 강제로 업데이트를 실행하거나 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="daf40-526">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="daf40-527">이벤트 기반 강제 업데이트 관리</span><span class="sxs-lookup"><span data-stu-id="daf40-527">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="daf40-528">시작 시 또는 특정 클라우드 제공 보호 이벤트 후에 보호 업데이트를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="daf40-528">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="daf40-529">모바일 장치 및 VM(가상 머신)에 대한 업데이트 관리</span><span class="sxs-lookup"><span data-stu-id="daf40-529">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="daf40-530">모바일 장치 및 가상 머신에 특히 유용한 배터리 전원에서 업데이트가 발생해야 하는지 여부와 같은 설정을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="daf40-530">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
