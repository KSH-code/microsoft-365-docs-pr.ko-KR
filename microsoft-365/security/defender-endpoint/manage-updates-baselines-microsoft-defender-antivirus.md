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
ms.date: 06/09/2021
ms.openlocfilehash: 05b2b2af87e423058d18651571d52a97ac387506
ms.sourcegitcommit: 3584c1fe59d12512d67faf3efc955e1d67e2baa0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2021
ms.locfileid: "52862150"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="38c97-104">업데이트 Microsoft Defender 바이러스 백신 관리하고 기준 적용</span><span class="sxs-lookup"><span data-stu-id="38c97-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="38c97-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="38c97-105">**Applies to:**</span></span>

- [<span data-ttu-id="38c97-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="38c97-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="38c97-107">Windows Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="38c97-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="38c97-108">최신 업데이트와 관련된 두 가지 유형의 업데이트가 Microsoft Defender 바이러스 백신 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38c97-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="38c97-109">보안 인텔리전스 업데이트</span><span class="sxs-lookup"><span data-stu-id="38c97-109">Security intelligence updates</span></span>
- <span data-ttu-id="38c97-110">제품 업데이트</span><span class="sxs-lookup"><span data-stu-id="38c97-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="38c97-111">최신 Microsoft Defender 바이러스 백신 유지하는 것은 장치에 새로운 맬웨어 및 공격 기술로부터 보호하는 데 필요한 최신 기술 및 기능을 유지하는 데 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="38c97-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>
> 
> <span data-ttu-id="38c97-112">수동 모드에서 실행 중인 경우에도 바이러스 Microsoft Defender 바이러스 백신 [업데이트해야 합니다.](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="38c97-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="38c97-113">최신 엔진, 플랫폼 및 서명 날짜를 확인하기 위해 Microsoft Defender 바이러스 백신 Microsoft 맬웨어 방지에 대한 보안 [인텔리전스 업데이트를 방문하세요.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="38c97-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="38c97-114">보안 인텔리전스 업데이트</span><span class="sxs-lookup"><span data-stu-id="38c97-114">Security intelligence updates</span></span>

<span data-ttu-id="38c97-115">Microsoft Defender 바이러스 백신 Microsoft Advanced [](cloud-protection-microsoft-defender-antivirus.md) Protection Service 또는 MAPS라고도 하는 클라우드 제공 보호를 사용하며 보안 인텔리전스 업데이트를 주기적으로 다운로드하여 보호 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="38c97-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="38c97-116">업데이트는 아래 KB 번호에 따라 릴리스됩니다.</span><span class="sxs-lookup"><span data-stu-id="38c97-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="38c97-117">Microsoft Defender 바이러스 백신: KB2267602</span><span class="sxs-lookup"><span data-stu-id="38c97-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="38c97-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="38c97-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="38c97-119">클라우드 제공 보호는 항상 설정되어 있으며 인터넷에 대한 활성 연결이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="38c97-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="38c97-120">보안 인텔리전스 업데이트는 예약된 일정에 따라 발생합니다(정책을 통해 구성 가능).</span><span class="sxs-lookup"><span data-stu-id="38c97-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="38c97-121">자세한 내용은 에서 Microsoft 클라우드 제공 보호 [Microsoft Defender 바이러스 백신.](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="38c97-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="38c97-122">최신 보안 인텔리전스 업데이트 목록은 보안 인텔리전스 업데이트 및 Microsoft Defender 바이러스 백신 [맬웨어 방지를 참조하세요.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="38c97-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="38c97-123">엔진 업데이트는 보안 인텔리전스 업데이트에 포함되어 있으며 월별 케이던스에 릴리스됩니다.</span><span class="sxs-lookup"><span data-stu-id="38c97-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="38c97-124">제품 업데이트</span><span class="sxs-lookup"><span data-stu-id="38c97-124">Product updates</span></span>

<span data-ttu-id="38c97-125">Microsoft Defender 바이러스 백신  [업데이트(KB4052623)(플랫폼](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) 업데이트라고도 알려)가 필요하며, 주요 기능 업데이트와 함께 Windows 10 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38c97-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="38c97-126">다음 방법 중 하나를 통해 업데이트 배포를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38c97-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="38c97-127">Windows WSUS(서버 업데이트 서비스)</span><span class="sxs-lookup"><span data-stu-id="38c97-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="38c97-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="38c97-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="38c97-129">Microsoft를 배포하고 네트워크의 끝점에 Windows 배포하는 데 사용하는 일반적인 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="38c97-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="38c97-130">자세한 내용은 [Manage the sources for Microsoft Defender 바이러스 백신 protection updates를 참조하십시오.](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)</span><span class="sxs-lookup"><span data-stu-id="38c97-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="38c97-131">월별 업데이트는 단계적으로 릴리스되어 Window Server Update Services에 여러 [패키지가 표시됩니다.](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)</span><span class="sxs-lookup"><span data-stu-id="38c97-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="38c97-132">월별 플랫폼 및 엔진 버전</span><span class="sxs-lookup"><span data-stu-id="38c97-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="38c97-133">플랫폼 업데이트를 업데이트하거나 설치하는 방법에 대한 자세한 내용은 Windows Defender 맬웨어 방지 플랫폼용 업데이트를 [참조하세요.](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)</span><span class="sxs-lookup"><span data-stu-id="38c97-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="38c97-134">모든 업데이트에 포함</span><span class="sxs-lookup"><span data-stu-id="38c97-134">All our updates contain</span></span> 
- <span data-ttu-id="38c97-135">성능 개선</span><span class="sxs-lookup"><span data-stu-id="38c97-135">performance improvements;</span></span>
- <span data-ttu-id="38c97-136">서비스성 개선 및</span><span class="sxs-lookup"><span data-stu-id="38c97-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="38c97-137">통합 개선된 기능(클라우드, Microsoft 365 [Defender).](/microsoft-365/security/defender/microsoft-365-defender)</span><span class="sxs-lookup"><span data-stu-id="38c97-137">integration improvements (Cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="38c97-138">2021년 5월(플랫폼: 4.18.2105.4 | 엔진: 1.1.18200.4)</span><span class="sxs-lookup"><span data-stu-id="38c97-138">May-2021 (Platform: 4.18.2105.4 | Engine: 1.1.18200.4)</span></span></summary>

<span data-ttu-id="38c97-139">&ensp;보안 인텔리전스 업데이트 버전: **1.341.8.0**</span><span class="sxs-lookup"><span data-stu-id="38c97-139">&ensp;Security intelligence update version: **1.341.8.0**</span></span>  
<span data-ttu-id="38c97-140">&ensp;릴리스: **2021년 6월 3일**</span><span class="sxs-lookup"><span data-stu-id="38c97-140">&ensp;Released: **June 3, 2021**</span></span>  
<span data-ttu-id="38c97-141">&ensp;플랫폼: **4.18.2105.4**</span><span class="sxs-lookup"><span data-stu-id="38c97-141">&ensp;Platform: **4.18.2105.4**</span></span>  
<span data-ttu-id="38c97-142">&ensp;엔진: **1.1.18200.4**</span><span class="sxs-lookup"><span data-stu-id="38c97-142">&ensp;Engine: **1.1.18200.4**</span></span>  
<span data-ttu-id="38c97-143">&ensp;지원 단계: **보안 및 중요 업데이트**</span><span class="sxs-lookup"><span data-stu-id="38c97-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="38c97-144">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="38c97-144">What's new</span></span>
- <span data-ttu-id="38c97-145">동작 모니터링 [개선](client-behavioral-blocking.md)</span><span class="sxs-lookup"><span data-stu-id="38c97-145">Improvements to [behavior monitoring](client-behavioral-blocking.md)</span></span> 
- <span data-ttu-id="38c97-146">고정 [네트워크 보호](network-protection.md) 알림 필터링 기능</span><span class="sxs-lookup"><span data-stu-id="38c97-146">Fixed [network protection](network-protection.md) notification filtering feature</span></span>

### <a name="known-issues"></a><span data-ttu-id="38c97-147">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="38c97-147">Known Issues</span></span>
<span data-ttu-id="38c97-148">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="38c97-148">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="38c97-149">2021년 4월(플랫폼: 4.18.2104.14 | 엔진: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="38c97-149">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="38c97-150">&ensp;보안 인텔리전스 업데이트 버전: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="38c97-150">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="38c97-151">&ensp;릴리스: **2021년 4월 26일(엔진:**  1.1.18100.6 릴리스 2021년 5월 5일) &ensp; 플랫폼: **4.18.2104.14**</span><span class="sxs-lookup"><span data-stu-id="38c97-151">&ensp;Released: **April 26, 2021**  (Engine: 1.1.18100.6 released May 5, 2021) &ensp;Platform: **4.18.2104.14**</span></span>  
<span data-ttu-id="38c97-152">&ensp;엔진: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="38c97-152">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="38c97-153">&ensp;지원 단계: **보안 및 중요 업데이트**</span><span class="sxs-lookup"><span data-stu-id="38c97-153">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="38c97-154">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="38c97-154">What's new</span></span>
- <span data-ttu-id="38c97-155">추가 동작 모니터링 논리</span><span class="sxs-lookup"><span data-stu-id="38c97-155">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="38c97-156">커널 모드 키로거 검색 개선</span><span class="sxs-lookup"><span data-stu-id="38c97-156">Improved kernel mode keylogger detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="38c97-157">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="38c97-157">Known Issues</span></span>
<span data-ttu-id="38c97-158">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="38c97-158">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="38c97-159">2021년 3월(플랫폼: 4.18.2103.7 | 엔진: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="38c97-159">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="38c97-160">&ensp;보안 인텔리전스 업데이트 버전: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="38c97-160">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="38c97-161">&ensp;릴리스: **2021년 4월 2일**</span><span class="sxs-lookup"><span data-stu-id="38c97-161">&ensp;Released: **April 2, 2021**</span></span>  
<span data-ttu-id="38c97-162">&ensp;플랫폼: **4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="38c97-162">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="38c97-163">&ensp;엔진: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="38c97-163">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="38c97-164">&ensp;지원 단계: **보안 및 중요 업데이트**</span><span class="sxs-lookup"><span data-stu-id="38c97-164">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="38c97-165">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="38c97-165">What's new</span></span>

- <span data-ttu-id="38c97-166">동작 모니터링 엔진 개선</span><span class="sxs-lookup"><span data-stu-id="38c97-166">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="38c97-167">확장된 네트워크 무차별 공격 완화</span><span class="sxs-lookup"><span data-stu-id="38c97-167">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="38c97-168">변조 방지를 사용하도록 설정한 경우 추가 변조 시도 이벤트 생성 [실패](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="38c97-168">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="38c97-169">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="38c97-169">Known Issues</span></span>
<span data-ttu-id="38c97-170">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="38c97-170">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="38c97-171">이전 버전 업데이트: 기술 업그레이드 지원만</span><span class="sxs-lookup"><span data-stu-id="38c97-171">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="38c97-172">새 패키지 버전이 출시된 후 이전 두 버전에 대한 지원은 기술 지원으로만 축소됩니다.</span><span class="sxs-lookup"><span data-stu-id="38c97-172">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="38c97-173">이 섹션에 나열된 버전보다 오래된 버전은 기술 업그레이드 지원 전용으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="38c97-173">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="38c97-174">2021년 2월(플랫폼: 4.18.2102.3 | 엔진: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="38c97-174">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="38c97-175">&ensp;보안 인텔리전스 업데이트 버전: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="38c97-175">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="38c97-176">&ensp;릴리스: **2021년 3월 9일**</span><span class="sxs-lookup"><span data-stu-id="38c97-176">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="38c97-177">&ensp;플랫폼: **4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="38c97-177">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="38c97-178">&ensp;엔진: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="38c97-178">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="38c97-179">&ensp;지원 단계: **기술 업그레이드 지원(전용)**</span><span class="sxs-lookup"><span data-stu-id="38c97-179">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="38c97-180">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="38c97-180">What's new</span></span>

- <span data-ttu-id="38c97-181">변조 방지를 통한 [서비스 복구 개선](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="38c97-181">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="38c97-182">변조 보호 범위 확장</span><span class="sxs-lookup"><span data-stu-id="38c97-182">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="38c97-183">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="38c97-183">Known Issues</span></span>
<span data-ttu-id="38c97-184">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="38c97-184">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="38c97-185">2021년 1월(플랫폼: 4.18.2101.9 | 엔진: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="38c97-185">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="38c97-186">&ensp;보안 인텔리전스 업데이트 버전: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="38c97-186">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="38c97-187">&ensp;릴리스: **2021년 2월 2일**</span><span class="sxs-lookup"><span data-stu-id="38c97-187">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="38c97-188">&ensp;플랫폼: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="38c97-188">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="38c97-189">&ensp;엔진: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="38c97-189">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="38c97-190">&ensp;지원 단계: **기술 업그레이드 지원(전용)**</span><span class="sxs-lookup"><span data-stu-id="38c97-190">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="38c97-191">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="38c97-191">What's new</span></span>

- <span data-ttu-id="38c97-192">셸 코드 악용 감지 개선</span><span class="sxs-lookup"><span data-stu-id="38c97-192">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="38c97-193">자격 증명 도용 시도에 대한 가시성 향상</span><span class="sxs-lookup"><span data-stu-id="38c97-193">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="38c97-194">서비스에서 향상된 Microsoft Defender 바이러스 백신 기능</span><span class="sxs-lookup"><span data-stu-id="38c97-194">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="38c97-195">x64 에뮬 ARM 지원 개선</span><span class="sxs-lookup"><span data-stu-id="38c97-195">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="38c97-196">해결 방법: EDR 보호가 초기 검색을 수행한 후 위협 기록에 차단 알림이 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38c97-196">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="38c97-197">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="38c97-197">Known Issues</span></span>
<span data-ttu-id="38c97-198">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="38c97-198">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="38c97-199">2020년 11월-2020년 11월(플랫폼: 4.18.2011.6 | 엔진: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="38c97-199">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="38c97-200">&ensp;보안 인텔리전스 업데이트 버전: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="38c97-200">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="38c97-201">&ensp;릴리스: **2020년 12월 3일**</span><span class="sxs-lookup"><span data-stu-id="38c97-201">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="38c97-202">&ensp;플랫폼: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="38c97-202">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="38c97-203">&ensp;엔진: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="38c97-203">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="38c97-204">&ensp;지원 단계: **기술 업그레이드 지원(전용)**</span><span class="sxs-lookup"><span data-stu-id="38c97-204">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="38c97-205">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="38c97-205">What's new</span></span>

- <span data-ttu-id="38c97-206">향상된 [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) 상태 지원 로깅</span><span class="sxs-lookup"><span data-stu-id="38c97-206">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="38c97-207">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="38c97-207">Known Issues</span></span>
<span data-ttu-id="38c97-208">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="38c97-208">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="38c97-209">2020년 10월(플랫폼: 4.18.2010.7 | 엔진: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="38c97-209">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="38c97-210">&ensp;보안 인텔리전스 업데이트 버전: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="38c97-210">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="38c97-211">&ensp;릴리스: **2020년 10월 29일**</span><span class="sxs-lookup"><span data-stu-id="38c97-211">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="38c97-212">&ensp;플랫폼: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="38c97-212">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="38c97-213">&ensp;엔진: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="38c97-213">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="38c97-214">&ensp;지원 단계: **기술 업그레이드 지원(전용)**</span><span class="sxs-lookup"><span data-stu-id="38c97-214">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="38c97-215">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="38c97-215">What's new</span></span>

- <span data-ttu-id="38c97-216">특수 위협 범주에 대한 새 설명</span><span class="sxs-lookup"><span data-stu-id="38c97-216">New descriptions for special threat categories</span></span>
- <span data-ttu-id="38c97-217">향상된 에뮬ation 기능</span><span class="sxs-lookup"><span data-stu-id="38c97-217">Improved emulation capabilities</span></span>
- <span data-ttu-id="38c97-218">향상된 호스트 주소 허용/차단 기능</span><span class="sxs-lookup"><span data-stu-id="38c97-218">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="38c97-219">Defender CSP의 새 옵션에서 로컬 사용자 제외의 무시</span><span class="sxs-lookup"><span data-stu-id="38c97-219">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="38c97-220">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="38c97-220">Known Issues</span></span>

<span data-ttu-id="38c97-221">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="38c97-221">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="38c97-222">2020년 9월(플랫폼: 4.18.2009.7 | 엔진: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="38c97-222">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="38c97-223">&ensp;보안 인텔리전스 업데이트 버전: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="38c97-223">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="38c97-224">&ensp;릴리스: **2020년 10월 1일**</span><span class="sxs-lookup"><span data-stu-id="38c97-224">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="38c97-225">&ensp;플랫폼: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="38c97-225">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="38c97-226">&ensp;엔진: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="38c97-226">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="38c97-227">&ensp;지원 단계: **기술 업그레이드 지원(전용)**</span><span class="sxs-lookup"><span data-stu-id="38c97-227">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="38c97-228">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="38c97-228">What's new</span></span>

- <span data-ttu-id="38c97-229">파일을 Quarantine에서 복원하려면 관리자 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="38c97-229">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="38c97-230">이제 XML 형식 이벤트가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="38c97-230">XML formatted events are now supported</span></span>
- <span data-ttu-id="38c97-231">제외 병합을 외면하기 위한 CSP 지원</span><span class="sxs-lookup"><span data-stu-id="38c97-231">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="38c97-232">새 관리 인터페이스:</span><span class="sxs-lookup"><span data-stu-id="38c97-232">New management interfaces for:</span></span>
   - <span data-ttu-id="38c97-233">UDP 검사</span><span class="sxs-lookup"><span data-stu-id="38c97-233">UDP Inspection</span></span>
   - <span data-ttu-id="38c97-234">Server 2019의 네트워크 보호</span><span class="sxs-lookup"><span data-stu-id="38c97-234">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="38c97-235">네트워크 보호를 위한 IP 주소 제외</span><span class="sxs-lookup"><span data-stu-id="38c97-235">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="38c97-236">TPM 측정에 대한 가시성 향상</span><span class="sxs-lookup"><span data-stu-id="38c97-236">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="38c97-237">VBA 모듈 Office 향상</span><span class="sxs-lookup"><span data-stu-id="38c97-237">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="38c97-238">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="38c97-238">Known Issues</span></span>

<span data-ttu-id="38c97-239">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="38c97-239">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="38c97-240">2020년 8월(플랫폼: 4.18.2008.9 | 엔진: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="38c97-240">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="38c97-241">&ensp;보안 인텔리전스 업데이트 버전: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="38c97-241">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="38c97-242">&ensp;릴리스: **2020년 8월 27일**</span><span class="sxs-lookup"><span data-stu-id="38c97-242">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="38c97-243">&ensp;플랫폼: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="38c97-243">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="38c97-244">&ensp;엔진: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="38c97-244">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="38c97-245">&ensp;지원 단계: **기술 업그레이드 지원(전용)**</span><span class="sxs-lookup"><span data-stu-id="38c97-245">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="38c97-246">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="38c97-246">What's new</span></span>

- <span data-ttu-id="38c97-247">원격 분석 이벤트 추가</span><span class="sxs-lookup"><span data-stu-id="38c97-247">Add more telemetry events</span></span>
- <span data-ttu-id="38c97-248">향상된 검사 이벤트 원격 분석</span><span class="sxs-lookup"><span data-stu-id="38c97-248">Improved scan event telemetry</span></span>
- <span data-ttu-id="38c97-249">메모리 검사에 대한 향상된 동작 모니터링</span><span class="sxs-lookup"><span data-stu-id="38c97-249">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="38c97-250">향상된 매크로 스트림 검사</span><span class="sxs-lookup"><span data-stu-id="38c97-250">Improved macro streams scanning</span></span>
- <span data-ttu-id="38c97-251">`AMRunningMode`PowerShell cmdlet에 Get-MpComputerStatus 추가</span><span class="sxs-lookup"><span data-stu-id="38c97-251">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="38c97-252">[DisableAntiSpyware는](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="38c97-252">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="38c97-253">Microsoft Defender 바이러스 백신 바이러스 백신 프로그램을 검색하면 자동으로 꺼집니다.</span><span class="sxs-lookup"><span data-stu-id="38c97-253">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="38c97-254">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="38c97-254">Known Issues</span></span>
<span data-ttu-id="38c97-255">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="38c97-255">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="38c97-256">2020년 7월(플랫폼: 4.18.2007.8 | 엔진: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="38c97-256">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="38c97-257">&ensp;보안 인텔리전스 업데이트 버전: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="38c97-257">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="38c97-258">&ensp;릴리스: **2020년 7월 28일**</span><span class="sxs-lookup"><span data-stu-id="38c97-258">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="38c97-259">&ensp;플랫폼: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="38c97-259">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="38c97-260">&ensp;엔진: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="38c97-260">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="38c97-261">&ensp;지원 단계: **기술 업그레이드 지원(전용)**</span><span class="sxs-lookup"><span data-stu-id="38c97-261">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="38c97-262">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="38c97-262">What's new</span></span>

- <span data-ttu-id="38c97-263">BITS에 대한 향상된 원격 분석</span><span class="sxs-lookup"><span data-stu-id="38c97-263">Improved telemetry for BITS</span></span>
- <span data-ttu-id="38c97-264">Authenticode 코드 서명 인증서 유효성 검사 개선</span><span class="sxs-lookup"><span data-stu-id="38c97-264">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="38c97-265">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="38c97-265">Known Issues</span></span>
<span data-ttu-id="38c97-266">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="38c97-266">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="38c97-267">2020년 6월(플랫폼: 4.18.2006.10 | 엔진: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="38c97-267">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="38c97-268">&ensp;보안 인텔리전스 업데이트 버전: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="38c97-268">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="38c97-269">&ensp;릴리스: **2020년 6월 22일**</span><span class="sxs-lookup"><span data-stu-id="38c97-269">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="38c97-270">&ensp;플랫폼: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="38c97-270">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="38c97-271">&ensp;엔진: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="38c97-271">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="38c97-272">&ensp;지원 단계: **기술 업그레이드 지원(전용)**</span><span class="sxs-lookup"><span data-stu-id="38c97-272">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="38c97-273">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="38c97-273">What's new</span></span>

- <span data-ttu-id="38c97-274">지원 [로그의 위치를 지정할 수 있습니다.](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="38c97-274">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="38c97-275">수동 모드에서 적극적인 catchup 검사 건너뛰기</span><span class="sxs-lookup"><span data-stu-id="38c97-275">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="38c97-276">데이터 데이터 연결에서 Defender 업데이트 허용</span><span class="sxs-lookup"><span data-stu-id="38c97-276">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="38c97-277">캐싱을 사용하지 않도록 설정한 경우의 고정 성능 조정</span><span class="sxs-lookup"><span data-stu-id="38c97-277">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="38c97-278">고정 레지스트리 쿼리</span><span class="sxs-lookup"><span data-stu-id="38c97-278">Fixed registry query</span></span> 
- <span data-ttu-id="38c97-279">ADMX의 검사 시간 임의 지정 수정</span><span class="sxs-lookup"><span data-stu-id="38c97-279">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="38c97-280">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="38c97-280">Known Issues</span></span>
<span data-ttu-id="38c97-281">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="38c97-281">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="38c97-282">2020년 5월(플랫폼: 4.18.2005.4 | 엔진: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="38c97-282">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="38c97-283">&ensp;보안 인텔리전스 업데이트 버전: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="38c97-283">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="38c97-284">&ensp;릴리스: **2020년 5월 26일**</span><span class="sxs-lookup"><span data-stu-id="38c97-284">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="38c97-285">&ensp;플랫폼: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="38c97-285">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="38c97-286">&ensp;엔진: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="38c97-286">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="38c97-287">&ensp;지원 단계: **기술 업그레이드 지원(전용)**</span><span class="sxs-lookup"><span data-stu-id="38c97-287">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="38c97-288">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="38c97-288">What's new</span></span>

- <span data-ttu-id="38c97-289">검사 이벤트에 대한 로깅 개선</span><span class="sxs-lookup"><span data-stu-id="38c97-289">Improved logging for scan events</span></span>
- <span data-ttu-id="38c97-290">향상된 사용자 모드 크래시 처리.</span><span class="sxs-lookup"><span data-stu-id="38c97-290">Improved user mode crash handling.</span></span>
- <span data-ttu-id="38c97-291">변조 방지를 위한 이벤트 추적이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="38c97-291">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="38c97-292">AMSI 샘플 제출 수정</span><span class="sxs-lookup"><span data-stu-id="38c97-292">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="38c97-293">AMSI 클라우드 차단 수정</span><span class="sxs-lookup"><span data-stu-id="38c97-293">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="38c97-294">고정 보안 업데이트 설치 로그</span><span class="sxs-lookup"><span data-stu-id="38c97-294">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="38c97-295">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="38c97-295">Known Issues</span></span>
<span data-ttu-id="38c97-296">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="38c97-296">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="38c97-297">2020년 4월(플랫폼: 4.18.2004.6 | 엔진: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="38c97-297">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="38c97-298">&ensp;보안 인텔리전스 업데이트 버전: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="38c97-298">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="38c97-299">&ensp;릴리스: **2020년 4월 30일**</span><span class="sxs-lookup"><span data-stu-id="38c97-299">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="38c97-300">&ensp;플랫폼: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="38c97-300">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="38c97-301">&ensp;엔진: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="38c97-301">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="38c97-302">&ensp;지원 단계: **기술 업그레이드 지원(전용)**</span><span class="sxs-lookup"><span data-stu-id="38c97-302">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="38c97-303">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="38c97-303">What's new</span></span>
- <span data-ttu-id="38c97-304">WDfilter 개선</span><span class="sxs-lookup"><span data-stu-id="38c97-304">WDfilter improvements</span></span>
- <span data-ttu-id="38c97-305">더 실행 가능한 이벤트 데이터를 추가하여 표면 감소 감지 이벤트 공격</span><span class="sxs-lookup"><span data-stu-id="38c97-305">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="38c97-306">진단 데이터 및 WMI의 고정 버전 정보</span><span class="sxs-lookup"><span data-stu-id="38c97-306">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="38c97-307">플랫폼 업데이트 후 UI에서 잘못된 플랫폼 버전 수정</span><span class="sxs-lookup"><span data-stu-id="38c97-307">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="38c97-308">파일 없는 위협 방지를 위한 동적 URL intel</span><span class="sxs-lookup"><span data-stu-id="38c97-308">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="38c97-309">UEFI 검사 기능</span><span class="sxs-lookup"><span data-stu-id="38c97-309">UEFI scan capability</span></span>
- <span data-ttu-id="38c97-310">업데이트 로깅 확장</span><span class="sxs-lookup"><span data-stu-id="38c97-310">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="38c97-311">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="38c97-311">Known Issues</span></span>
<span data-ttu-id="38c97-312">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="38c97-312">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="38c97-313">2020년 3월(플랫폼: 4.18.2003.8 | 엔진: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="38c97-313">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="38c97-314">&ensp;보안 인텔리전스 업데이트 버전: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="38c97-314">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="38c97-315">&ensp;릴리스: **2020년 3월 24일**</span><span class="sxs-lookup"><span data-stu-id="38c97-315">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="38c97-316">&ensp;플랫폼: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="38c97-316">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="38c97-317">&ensp;엔진: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="38c97-317">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="38c97-318">&ensp;지원 단계: **기술 업그레이드 지원(전용)**</span><span class="sxs-lookup"><span data-stu-id="38c97-318">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="38c97-319">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="38c97-319">What's new</span></span>

- <span data-ttu-id="38c97-320">[MpCmdRun에](./command-line-arguments-microsoft-defender-antivirus.md) 추가된 CPU 스로틀 옵션</span><span class="sxs-lookup"><span data-stu-id="38c97-320">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="38c97-321">진단 기능 개선</span><span class="sxs-lookup"><span data-stu-id="38c97-321">Improve diagnostic capability</span></span>
- <span data-ttu-id="38c97-322">보안 인텔리전스 시간 제한 단축(5분)</span><span class="sxs-lookup"><span data-stu-id="38c97-322">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="38c97-323">AMSI 엔진 내부 로그 기능 확장</span><span class="sxs-lookup"><span data-stu-id="38c97-323">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="38c97-324">프로세스 차단에 대한 알림 개선</span><span class="sxs-lookup"><span data-stu-id="38c97-324">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="38c97-325">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="38c97-325">Known Issues</span></span>
<span data-ttu-id="38c97-326">[**Fixed**] Microsoft Defender 바이러스 백신 실행 시 파일을 건너뛰고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38c97-326">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="38c97-327">2020년 2월(플랫폼: - | 엔진: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="38c97-327">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="38c97-328">&ensp;보안 인텔리전스 업데이트 버전: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="38c97-328">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="38c97-329">&ensp;릴리스: **2020년 2월 25일**</span><span class="sxs-lookup"><span data-stu-id="38c97-329">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="38c97-330">&ensp;플랫폼/클라이언트: **-**</span><span class="sxs-lookup"><span data-stu-id="38c97-330">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="38c97-331">&ensp;엔진: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="38c97-331">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="38c97-332">&ensp;지원 단계: **기술 업그레이드 지원(전용)**</span><span class="sxs-lookup"><span data-stu-id="38c97-332">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="38c97-333">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="38c97-333">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="38c97-334">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="38c97-334">Known Issues</span></span>
<span data-ttu-id="38c97-335">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="38c97-335">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="38c97-336">2020년 1월(플랫폼: 4.18.2001.10 | 엔진: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="38c97-336">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="38c97-337">보안 인텔리전스 업데이트 버전: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="38c97-337">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="38c97-338">릴리스: **2020년 1월 30일**</span><span class="sxs-lookup"><span data-stu-id="38c97-338">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="38c97-339">플랫폼/클라이언트: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="38c97-339">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="38c97-340">엔진: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="38c97-340">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="38c97-341">&ensp;지원 단계: **기술 업그레이드 지원(전용)**</span><span class="sxs-lookup"><span data-stu-id="38c97-341">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="38c97-342">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="38c97-342">What's new</span></span>

- <span data-ttu-id="38c97-343">WS2016의 고정 BSOD 및 Exchange</span><span class="sxs-lookup"><span data-stu-id="38c97-343">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="38c97-344">TMP가 네트워크 경로로 리디렉션될 때 플랫폼 업데이트 지원</span><span class="sxs-lookup"><span data-stu-id="38c97-344">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="38c97-345">플랫폼 및 엔진 버전이 [WDSI에 추가됩니다.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="38c97-345">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="38c97-346">긴급 서명 업데이트를 [수동 모드로 확장](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="38c97-346">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="38c97-347">4.18.1911.3 중단 수정</span><span class="sxs-lookup"><span data-stu-id="38c97-347">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="38c97-348">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="38c97-348">Known Issues</span></span>

<span data-ttu-id="38c97-349">[**고정**] [](/windows-hardware/design/device-experiences/modern-standby) 최신 대기 모드를 활용하는 장치는 보호의 간격을 Windows Defender 필터 드라이버가 중단될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38c97-349">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="38c97-350">영향을 받는 컴퓨터는 최신 맬웨어 방지 플랫폼으로 업데이트되지 않은 것으로 고객에게 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="38c97-350">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="38c97-351">이 업데이트는:</span><span class="sxs-lookup"><span data-stu-id="38c97-351">This update is:</span></span>
> - <span data-ttu-id="38c97-352">SHA2를 지원하기 위해 더 낮은 버전의 플랫폼을 실행하는 RS1 장치에서 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="38c97-352">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="38c97-353">문제가 있는 시스템에 대한 재부팅 플래그가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38c97-353">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="38c97-354">는 2020년 4월에 다시 출시될 예정으로, 향후 가용성을 유지하기 위해 최신 업데이트로 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38c97-354">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="38c97-355">는 재부팅 요구 사항으로 인해 업데이트로 분류됩니다. 및</span><span class="sxs-lookup"><span data-stu-id="38c97-355">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="38c97-356">는 업데이트 [에서만 Windows 있습니다.](https://support.microsoft.com/help/4027667/windows-10-update)</span><span class="sxs-lookup"><span data-stu-id="38c97-356">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="38c97-357">2019년 11월부터 2019년 11월까지(플랫폼: 4.18.1911.3 | 엔진: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="38c97-357">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="38c97-358">보안 인텔리전스 업데이트 버전: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="38c97-358">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="38c97-359">릴리스: **2019년 12월 7일**</span><span class="sxs-lookup"><span data-stu-id="38c97-359">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="38c97-360">플랫폼: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="38c97-360">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="38c97-361">엔진: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="38c97-361">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="38c97-362">지원 단계: **지원 없음**</span><span class="sxs-lookup"><span data-stu-id="38c97-362">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="38c97-363">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="38c97-363">What's new</span></span>

- <span data-ttu-id="38c97-364">고정 MpCmdRun 추적 수준</span><span class="sxs-lookup"><span data-stu-id="38c97-364">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="38c97-365">WDFilter 버전 정보 수정</span><span class="sxs-lookup"><span data-stu-id="38c97-365">Fixed WDFilter version info</span></span>
- <span data-ttu-id="38c97-366">알림 개선(PUA)</span><span class="sxs-lookup"><span data-stu-id="38c97-366">Improve notifications (PUA)</span></span>
- <span data-ttu-id="38c97-367">MRT 로그를 추가하여 파일 지원</span><span class="sxs-lookup"><span data-stu-id="38c97-367">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="38c97-368">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="38c97-368">Known Issues</span></span>
<span data-ttu-id="38c97-369">이 업데이트를 설치하면 디바이스에서 점프 패키지 4.18.2001.10을 최신 플랫폼 버전으로 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38c97-369">When this update is installed, the device needs the jump package 4.18.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="38c97-370">Microsoft Defender 바이러스 백신 플랫폼 지원</span><span class="sxs-lookup"><span data-stu-id="38c97-370">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="38c97-371">플랫폼 및 엔진 업데이트는 월별 케이던스에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="38c97-371">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="38c97-372">완전히 지원받기 위해 최신 플랫폼 업데이트를 최신으로 유지하세요.</span><span class="sxs-lookup"><span data-stu-id="38c97-372">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="38c97-373">지원 구조는 동적이며, 최신 플랫폼 버전의 가용성에 따라 다음 두 단계로 진화합니다.</span><span class="sxs-lookup"><span data-stu-id="38c97-373">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="38c97-374">**보안 및** 중요 업데이트 서비스 단계 - 최신 플랫폼 버전을 실행하는 경우 맬웨어 방지 플랫폼에 대한 보안 및 중요 업데이트를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38c97-374">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="38c97-375">**기술 지원(전용) 단계** - 새 플랫폼 버전이 출시된 후 이전 버전(N-2)에 대한 지원은 기술 지원으로만 축소됩니다.</span><span class="sxs-lookup"><span data-stu-id="38c97-375">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="38c97-376">N-2 이전의 플랫폼 버전은 더 이상 지원되지 않습니다.\*</span><span class="sxs-lookup"><span data-stu-id="38c97-376">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="38c97-377">\*기술 지원은 Windows 10 릴리스 버전에서 최신 플랫폼 버전으로의 업그레이드를 위해 계속 [제공됩니다(Windows 10](#platform-version-included-with-windows-10-releases)릴리스에 포함된 플랫폼 버전 참조).</span><span class="sxs-lookup"><span data-stu-id="38c97-377">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="38c97-378">기술 지원(전용) 단계 중에는 상업적으로 합리적인 지원 인시던트가 Microsoft 고객 서비스 & 지원 및 Microsoft의 관리 지원 서비스(예: 프리미어 지원)를 통해 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="38c97-378">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="38c97-379">지원 인시던트가 추가 지침을 위해 개발로 에스컬레이터해야 하는 경우, 비보안 업데이트가 필요하거나, 보안 업데이트가 필요한 경우 고객에게 최신 플랫폼 버전 또는 중간 업데이트(\*)로 업그레이드할지 묻는 요청이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="38c97-379">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="38c97-380">릴리스에 포함된 플랫폼 Windows 10 버전</span><span class="sxs-lookup"><span data-stu-id="38c97-380">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="38c97-381">아래 표에는 최신 Microsoft Defender 바이러스 백신 함께 제공된 플랫폼 및 엔진 버전이 Windows 10 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38c97-381">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="38c97-382">Windows 10 릴리스</span><span class="sxs-lookup"><span data-stu-id="38c97-382">Windows 10 release</span></span>  |<span data-ttu-id="38c97-383">플랫폼 버전</span><span class="sxs-lookup"><span data-stu-id="38c97-383">Platform version</span></span>  |<span data-ttu-id="38c97-384">엔진 버전</span><span class="sxs-lookup"><span data-stu-id="38c97-384">Engine version</span></span> |<span data-ttu-id="38c97-385">지원 단계</span><span class="sxs-lookup"><span data-stu-id="38c97-385">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="38c97-386">2004(20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="38c97-386">2004  (20H1/20H2)</span></span> |<span data-ttu-id="38c97-387">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="38c97-387">4.18.1909.6</span></span> |<span data-ttu-id="38c97-388">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="38c97-388">1.1.17000.2</span></span> | <span data-ttu-id="38c97-389">기술 업그레이드 지원(전용)</span><span class="sxs-lookup"><span data-stu-id="38c97-389">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="38c97-390">1909(19H2)</span><span class="sxs-lookup"><span data-stu-id="38c97-390">1909  (19H2)</span></span> |<span data-ttu-id="38c97-391">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="38c97-391">4.18.1902.5</span></span> |<span data-ttu-id="38c97-392">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="38c97-392">1.1.16700.3</span></span> | <span data-ttu-id="38c97-393">기술 업그레이드 지원(전용)</span><span class="sxs-lookup"><span data-stu-id="38c97-393">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="38c97-394">1903(19H1)</span><span class="sxs-lookup"><span data-stu-id="38c97-394">1903  (19H1)</span></span> |<span data-ttu-id="38c97-395">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="38c97-395">4.18.1902.5</span></span> |<span data-ttu-id="38c97-396">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="38c97-396">1.1.15600.4</span></span> | <span data-ttu-id="38c97-397">기술 업그레이드 지원(전용)</span><span class="sxs-lookup"><span data-stu-id="38c97-397">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="38c97-398">1809(RS5)</span><span class="sxs-lookup"><span data-stu-id="38c97-398">1809  (RS5)</span></span> |<span data-ttu-id="38c97-399">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="38c97-399">4.18.1807.18075</span></span> |<span data-ttu-id="38c97-400">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="38c97-400">1.1.15000.2</span></span> | <span data-ttu-id="38c97-401">기술 업그레이드 지원(전용)</span><span class="sxs-lookup"><span data-stu-id="38c97-401">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="38c97-402">1803(RS4)</span><span class="sxs-lookup"><span data-stu-id="38c97-402">1803  (RS4)</span></span> |<span data-ttu-id="38c97-403">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="38c97-403">4.13.17134.1</span></span> |<span data-ttu-id="38c97-404">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="38c97-404">1.1.14600.4</span></span> | <span data-ttu-id="38c97-405">기술 업그레이드 지원(전용)</span><span class="sxs-lookup"><span data-stu-id="38c97-405">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="38c97-406">1709(RS3)</span><span class="sxs-lookup"><span data-stu-id="38c97-406">1709  (RS3)</span></span> |<span data-ttu-id="38c97-407">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="38c97-407">4.12.16299.15</span></span> |<span data-ttu-id="38c97-408">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="38c97-408">1.1.14104.0</span></span> | <span data-ttu-id="38c97-409">기술 업그레이드 지원(전용)</span><span class="sxs-lookup"><span data-stu-id="38c97-409">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="38c97-410">1703(RS2)</span><span class="sxs-lookup"><span data-stu-id="38c97-410">1703  (RS2)</span></span> |<span data-ttu-id="38c97-411">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="38c97-411">4.11.15603.2</span></span> |<span data-ttu-id="38c97-412">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="38c97-412">1.1.13504.0</span></span> | <span data-ttu-id="38c97-413">기술 업그레이드 지원(전용)</span><span class="sxs-lookup"><span data-stu-id="38c97-413">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="38c97-414">1607(RS1)</span><span class="sxs-lookup"><span data-stu-id="38c97-414">1607 (RS1)</span></span> |<span data-ttu-id="38c97-415">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="38c97-415">4.10.14393.3683</span></span> |<span data-ttu-id="38c97-416">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="38c97-416">1.1.12805.0</span></span> | <span data-ttu-id="38c97-417">기술 업그레이드 지원(전용)</span><span class="sxs-lookup"><span data-stu-id="38c97-417">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="38c97-418">릴리스 Windows 10 자세한 내용은 수명 주기 Windows [시트를 참조하세요.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)</span><span class="sxs-lookup"><span data-stu-id="38c97-418">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="38c97-419">DISM(배포 이미지 서비스 및 관리)에 대한 업데이트</span><span class="sxs-lookup"><span data-stu-id="38c97-419">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="38c97-420">최신 바이러스 백신 및 맬웨어 방지 업데이트로 Windows 10(Enterprise, Pro 및 Home edition), Windows Server 2019 및 Windows Server 2016 OS 설치 이미지를 업데이트하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="38c97-420">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="38c97-421">OS 설치 이미지를 최신으로 유지하면 보호 격차를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38c97-421">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="38c97-422">자세한 내용은 운영 체제 설치 Windows Microsoft [Defender 업데이트를 참조하세요.](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)</span><span class="sxs-lookup"><span data-stu-id="38c97-422">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="38c97-423">1.1.2106.01</span><span class="sxs-lookup"><span data-stu-id="38c97-423">1.1.2106.01</span></span></summary>

<span data-ttu-id="38c97-424">&ensp;패키지 버전: **1.1.2106.01**  </span><span class="sxs-lookup"><span data-stu-id="38c97-424">&ensp;Package version: **1.1.2106.01**  </span></span>  
<span data-ttu-id="38c97-425">&ensp;플랫폼 버전: **4.18.2104.14** </span><span class="sxs-lookup"><span data-stu-id="38c97-425">&ensp;Platform version: **4.18.2104.14** </span></span>  
<span data-ttu-id="38c97-426">&ensp;엔진 버전: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="38c97-426">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="38c97-427">&ensp;서명 버전: **1.339.1923.0**</span><span class="sxs-lookup"><span data-stu-id="38c97-427">&ensp;Signature version: **1.339.1923.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="38c97-428">수정</span><span class="sxs-lookup"><span data-stu-id="38c97-428">Fixes</span></span>
- <span data-ttu-id="38c97-429">없음</span><span class="sxs-lookup"><span data-stu-id="38c97-429">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="38c97-430">추가 정보</span><span class="sxs-lookup"><span data-stu-id="38c97-430">Additional information</span></span>
- <span data-ttu-id="38c97-431">없음</span><span class="sxs-lookup"><span data-stu-id="38c97-431">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="38c97-432">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="38c97-432">1.1.2105.01</span></span></summary>

<span data-ttu-id="38c97-433">&ensp;패키지 버전: **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="38c97-433">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="38c97-434">&ensp;플랫폼 버전: **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="38c97-434">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="38c97-435">&ensp;엔진 버전: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="38c97-435">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="38c97-436">&ensp;서명 버전: **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="38c97-436">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="38c97-437">수정</span><span class="sxs-lookup"><span data-stu-id="38c97-437">Fixes</span></span>
- <span data-ttu-id="38c97-438">없음</span><span class="sxs-lookup"><span data-stu-id="38c97-438">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="38c97-439">추가 정보</span><span class="sxs-lookup"><span data-stu-id="38c97-439">Additional information</span></span>
- <span data-ttu-id="38c97-440">없음</span><span class="sxs-lookup"><span data-stu-id="38c97-440">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="38c97-441">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="38c97-441">1.1.2104.01</span></span></summary>

<span data-ttu-id="38c97-442">&ensp;패키지 버전: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="38c97-442">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="38c97-443">&ensp;플랫폼 버전: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="38c97-443">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="38c97-444">&ensp;엔진 버전: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="38c97-444">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="38c97-445">&ensp;서명 버전: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="38c97-445">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="38c97-446">수정</span><span class="sxs-lookup"><span data-stu-id="38c97-446">Fixes</span></span>
- <span data-ttu-id="38c97-447">없음</span><span class="sxs-lookup"><span data-stu-id="38c97-447">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="38c97-448">추가 정보</span><span class="sxs-lookup"><span data-stu-id="38c97-448">Additional information</span></span>
- <span data-ttu-id="38c97-449">없음</span><span class="sxs-lookup"><span data-stu-id="38c97-449">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="38c97-450">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="38c97-450">1.1.2103.01</span></span></summary>

<span data-ttu-id="38c97-451">&ensp;패키지 버전: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="38c97-451">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="38c97-452">&ensp;플랫폼 버전: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="38c97-452">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="38c97-453">&ensp;엔진 버전: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="38c97-453">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="38c97-454">&ensp;서명 버전: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="38c97-454">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="38c97-455">수정</span><span class="sxs-lookup"><span data-stu-id="38c97-455">Fixes</span></span>
- <span data-ttu-id="38c97-456">없음</span><span class="sxs-lookup"><span data-stu-id="38c97-456">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="38c97-457">추가 정보</span><span class="sxs-lookup"><span data-stu-id="38c97-457">Additional information</span></span>
- <span data-ttu-id="38c97-458">없음</span><span class="sxs-lookup"><span data-stu-id="38c97-458">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="38c97-459">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="38c97-459">1.1.2102.03</span></span></summary>

<span data-ttu-id="38c97-460">&ensp;패키지 버전: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="38c97-460">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="38c97-461">&ensp;플랫폼 버전: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="38c97-461">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="38c97-462">&ensp;엔진 버전: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="38c97-462">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="38c97-463">&ensp;서명 버전: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="38c97-463">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="38c97-464">수정</span><span class="sxs-lookup"><span data-stu-id="38c97-464">Fixes</span></span>
- <span data-ttu-id="38c97-465">없음</span><span class="sxs-lookup"><span data-stu-id="38c97-465">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="38c97-466">추가 정보</span><span class="sxs-lookup"><span data-stu-id="38c97-466">Additional information</span></span>
- <span data-ttu-id="38c97-467">없음</span><span class="sxs-lookup"><span data-stu-id="38c97-467">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="38c97-468">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="38c97-468">1.1.2101.02</span></span></summary>

<span data-ttu-id="38c97-469">&ensp;패키지 버전: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="38c97-469">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="38c97-470">&ensp;플랫폼 버전: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="38c97-470">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="38c97-471">&ensp;엔진 버전: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="38c97-471">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="38c97-472">&ensp;서명 버전: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="38c97-472">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="38c97-473">수정</span><span class="sxs-lookup"><span data-stu-id="38c97-473">Fixes</span></span>
- <span data-ttu-id="38c97-474">없음</span><span class="sxs-lookup"><span data-stu-id="38c97-474">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="38c97-475">추가 정보</span><span class="sxs-lookup"><span data-stu-id="38c97-475">Additional information</span></span>
- <span data-ttu-id="38c97-476">없음</span><span class="sxs-lookup"><span data-stu-id="38c97-476">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="38c97-477">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="38c97-477">1.1.2012.01</span></span></summary>

<span data-ttu-id="38c97-478">&ensp;패키지 버전: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="38c97-478">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="38c97-479">&ensp;플랫폼 버전: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="38c97-479">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="38c97-480">&ensp;엔진 버전: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="38c97-480">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="38c97-481">&ensp;서명 버전: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="38c97-481">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="38c97-482">수정</span><span class="sxs-lookup"><span data-stu-id="38c97-482">Fixes</span></span>
- <span data-ttu-id="38c97-483">없음</span><span class="sxs-lookup"><span data-stu-id="38c97-483">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="38c97-484">추가 정보</span><span class="sxs-lookup"><span data-stu-id="38c97-484">Additional information</span></span>
- <span data-ttu-id="38c97-485">없음</span><span class="sxs-lookup"><span data-stu-id="38c97-485">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="38c97-486">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="38c97-486">1.1.2011.02</span></span></summary>

<span data-ttu-id="38c97-487">&ensp;패키지 버전: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="38c97-487">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="38c97-488">&ensp;플랫폼 버전: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="38c97-488">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="38c97-489">&ensp;엔진 버전: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="38c97-489">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="38c97-490">&ensp;서명 버전: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="38c97-490">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="38c97-491">수정</span><span class="sxs-lookup"><span data-stu-id="38c97-491">Fixes</span></span>
- <span data-ttu-id="38c97-492">없음</span><span class="sxs-lookup"><span data-stu-id="38c97-492">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="38c97-493">추가 정보</span><span class="sxs-lookup"><span data-stu-id="38c97-493">Additional information</span></span>
- <span data-ttu-id="38c97-494">새로 고쳐진 Microsoft Defender 바이러스 백신 서명</span><span class="sxs-lookup"><span data-stu-id="38c97-494">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="38c97-495">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="38c97-495">1.1.2011.01</span></span></summary>

<span data-ttu-id="38c97-496">&ensp;패키지 버전: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="38c97-496">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="38c97-497">&ensp;플랫폼 버전: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="38c97-497">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="38c97-498">&ensp;엔진 버전: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="38c97-498">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="38c97-499">&ensp;서명 버전: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="38c97-499">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="38c97-500">수정</span><span class="sxs-lookup"><span data-stu-id="38c97-500">Fixes</span></span>
- <span data-ttu-id="38c97-501">없음</span><span class="sxs-lookup"><span data-stu-id="38c97-501">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="38c97-502">추가 정보</span><span class="sxs-lookup"><span data-stu-id="38c97-502">Additional information</span></span>
- <span data-ttu-id="38c97-503">없음</span><span class="sxs-lookup"><span data-stu-id="38c97-503">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="38c97-504">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="38c97-504">1.1.2009.10</span></span></summary>

<span data-ttu-id="38c97-505">&ensp;패키지 버전: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="38c97-505">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="38c97-506">&ensp;플랫폼 버전: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="38c97-506">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="38c97-507">&ensp;엔진 버전: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="38c97-507">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="38c97-508">&ensp;서명 버전: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="38c97-508">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="38c97-509">수정</span><span class="sxs-lookup"><span data-stu-id="38c97-509">Fixes</span></span>
- <span data-ttu-id="38c97-510">없음</span><span class="sxs-lookup"><span data-stu-id="38c97-510">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="38c97-511">추가 정보</span><span class="sxs-lookup"><span data-stu-id="38c97-511">Additional information</span></span>
- <span data-ttu-id="38c97-512">RS1 Windows 10 OS 설치 이미지에 대한 지원이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="38c97-512">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="38c97-513">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="38c97-513">Additional resources</span></span>

| <span data-ttu-id="38c97-514">문서</span><span class="sxs-lookup"><span data-stu-id="38c97-514">Article</span></span> | <span data-ttu-id="38c97-515">설명</span><span class="sxs-lookup"><span data-stu-id="38c97-515">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="38c97-516">운영 체제 설치 Windows 대한 Microsoft Defender 업데이트</span><span class="sxs-lookup"><span data-stu-id="38c97-516">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="38c97-517">OS 설치 이미지(WIM 및 VHD 파일)에 대한 맬웨어 방지 업데이트 패키지를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="38c97-517">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="38c97-518">Microsoft Defender 바이러스 백신(Windows 10 Enterprise, Pro 및 Home edition), Windows Server 2019 및 Windows Server 2016 설치 이미지에 대한 Windows Server 2016 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="38c97-518">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="38c97-519">보호 업데이트를 다운로드하고 적용하는 방법 관리</span><span class="sxs-lookup"><span data-stu-id="38c97-519">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="38c97-520">보호 업데이트는 여러 소스를 통해 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38c97-520">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="38c97-521">보호 업데이트를 다운로드하고 적용해야 하는 경우 관리</span><span class="sxs-lookup"><span data-stu-id="38c97-521">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="38c97-522">보호 업데이트를 다운로드해야 하는 경우를 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38c97-522">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="38c97-523">최신이 지난 끝점에 대한 업데이트 관리</span><span class="sxs-lookup"><span data-stu-id="38c97-523">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="38c97-524">끝점에서 업데이트 또는 예약된 검사가 누락된 경우 다음에 사용자가 로그인할 때 강제로 업데이트를 실행하거나 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38c97-524">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="38c97-525">이벤트 기반 강제 업데이트 관리</span><span class="sxs-lookup"><span data-stu-id="38c97-525">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="38c97-526">시작 시 또는 특정 클라우드 제공 보호 이벤트 후에 보호 업데이트를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38c97-526">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="38c97-527">모바일 장치 및 VM(가상 머신)에 대한 업데이트 관리</span><span class="sxs-lookup"><span data-stu-id="38c97-527">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="38c97-528">모바일 장치 및 가상 머신에 특히 유용한 배터리 전원에서 업데이트가 발생해야 하는지 여부와 같은 설정을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38c97-528">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
