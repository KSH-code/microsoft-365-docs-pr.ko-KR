---
title: Microsoft Defender 바이러스 백신 업데이트 관리 및 기준 적용
description: Microsoft Defender 바이러스 백신이 보호 및 제품 업데이트를 받는 방법을 관리합니다.
keywords: 업데이트, 보안 기준, 보호, 업데이트 예약, 강제 업데이트, 모바일 업데이트, wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: bf027dd7f5fad032d57d2dd0b686ccd129f568c7
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690980"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="361a6-104">Microsoft Defender 바이러스 백신 업데이트 관리 및 기준 적용</span><span class="sxs-lookup"><span data-stu-id="361a6-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="361a6-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="361a6-105">**Applies to:**</span></span>

- <span data-ttu-id="361a6-106">[엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/) </span><span class="sxs-lookup"><span data-stu-id="361a6-106">[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)</span></span>
- <span data-ttu-id="361a6-107">Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="361a6-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="361a6-108">Microsoft Defender 바이러스 백신을 최신 상태로 유지하는 데 관련된 두 가지 유형의 업데이트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="361a6-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="361a6-109">보안 인텔리전스 업데이트</span><span class="sxs-lookup"><span data-stu-id="361a6-109">Security intelligence updates</span></span>
- <span data-ttu-id="361a6-110">제품 업데이트</span><span class="sxs-lookup"><span data-stu-id="361a6-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="361a6-111">Microsoft Defender 바이러스 백신을 최신 상태로 유지하는 것은 장치에 새로운 맬웨어 및 공격 기술로부터 보호하는 데 필요한 최신 기술 및 기능을 유지하는 데 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="361a6-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>  
> <span data-ttu-id="361a6-112">Microsoft Defender 바이러스 백신이 수동 모드로 실행 중인 경우에도 바이러스 백신 [보호를 업데이트해야 합니다.](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="361a6-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="361a6-113">최신 엔진, 플랫폼 및 서명 날짜를 확인한 후 Microsoft Defender 바이러스 백신 및 기타 Microsoft 맬웨어 방지에 대한 보안 인텔리전스 [업데이트를 방문하세요.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="361a6-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="361a6-114">보안 인텔리전스 업데이트</span><span class="sxs-lookup"><span data-stu-id="361a6-114">Security intelligence updates</span></span>

<span data-ttu-id="361a6-115">Microsoft Defender [](cloud-protection-microsoft-defender-antivirus.md) 바이러스 백신은 클라우드 제공 보호(Microsoft Advanced Protection Service 또는 MAPS라고도 불리는)를 사용하며 보안 인텔리전스 업데이트를 주기적으로 다운로드하여 보호 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="361a6-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="361a6-116">업데이트는 아래 KB 번호에 따라 릴리스됩니다.</span><span class="sxs-lookup"><span data-stu-id="361a6-116">Updates are released under the below KB numbers:</span></span>  
> <span data-ttu-id="361a6-117">Microsoft Defender 바이러스 백신: KB2267602</span><span class="sxs-lookup"><span data-stu-id="361a6-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> <span data-ttu-id="361a6-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="361a6-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="361a6-119">클라우드 제공 보호는 항상 설정되어 있으며 인터넷에 대한 활성 연결이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="361a6-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="361a6-120">보안 인텔리전스 업데이트는 예약된 일정에 따라 발생합니다(정책을 통해 구성 가능).</span><span class="sxs-lookup"><span data-stu-id="361a6-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="361a6-121">자세한 내용은 Microsoft Defender 바이러스 백신에서 Microsoft 클라우드 제공 [보호 사용을 참조하세요.](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="361a6-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="361a6-122">최신 보안 인텔리전스 업데이트 목록은 Microsoft Defender 바이러스 백신 및 기타 Microsoft 맬웨어 방지에 대한 보안 인텔리전스 [업데이트를 참조하세요.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="361a6-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="361a6-123">엔진 업데이트는 보안 인텔리전스 업데이트에 포함되어 있으며 월별 케이던스에 릴리스됩니다.</span><span class="sxs-lookup"><span data-stu-id="361a6-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="361a6-124">제품 업데이트</span><span class="sxs-lookup"><span data-stu-id="361a6-124">Product updates</span></span>

<span data-ttu-id="361a6-125">Microsoft Defender 바이러스 백신은 월별 업데이트(KB4052623)(플랫폼 업데이트라고도 알려)가 필요하며 Windows 10 릴리스와 함께 주요 기능 업데이트를 받게 됩니다. [](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) </span><span class="sxs-lookup"><span data-stu-id="361a6-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="361a6-126">다음 방법 중 하나를 통해 업데이트 배포를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="361a6-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="361a6-127">WSUS(Windows Server Update Service)</span><span class="sxs-lookup"><span data-stu-id="361a6-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="361a6-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="361a6-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="361a6-129">네트워크의 끝점에 Microsoft 및 Windows 업데이트를 배포하는 데 사용하는 일반적인 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="361a6-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="361a6-130">자세한 내용은 Microsoft Defender 바이러스 백신 보호 업데이트에 대한 원본 [관리를 참조하세요.](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)</span><span class="sxs-lookup"><span data-stu-id="361a6-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="361a6-131">월별 업데이트는 단계적으로 릴리스되어 Window Server Update Services에 여러 [패키지가 표시됩니다.](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)</span><span class="sxs-lookup"><span data-stu-id="361a6-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="361a6-132">월별 플랫폼 및 엔진 버전</span><span class="sxs-lookup"><span data-stu-id="361a6-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="361a6-133">플랫폼 업데이트를 업데이트하거나 설치하는 방법에 대한 자세한 내용은 맬웨어 방지 플랫폼에 대한 Windows Defender [참조하세요.](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)</span><span class="sxs-lookup"><span data-stu-id="361a6-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="361a6-134">모든 업데이트에 포함</span><span class="sxs-lookup"><span data-stu-id="361a6-134">All our updates contain</span></span> 
- <span data-ttu-id="361a6-135">성능 개선</span><span class="sxs-lookup"><span data-stu-id="361a6-135">performance improvements;</span></span>
- <span data-ttu-id="361a6-136">서비스성 개선 및</span><span class="sxs-lookup"><span data-stu-id="361a6-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="361a6-137">통합 개선(클라우드, Microsoft 365 Defender).</span><span class="sxs-lookup"><span data-stu-id="361a6-137">integration improvements (Cloud, Microsoft 365 Defender).</span></span>
<br/><br/>

<details>
<summary> <span data-ttu-id="361a6-138">2021년 3월(플랫폼: 4.18.2103.7 | 엔진: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="361a6-138">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="361a6-139">&ensp;보안 인텔리전스 업데이트 버전: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="361a6-139">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="361a6-140">&ensp;릴리스: **2021년 4월 1일**</span><span class="sxs-lookup"><span data-stu-id="361a6-140">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="361a6-141">&ensp;플랫폼: **4.19.2103.7**</span><span class="sxs-lookup"><span data-stu-id="361a6-141">&ensp;Platform: **4.19.2103.7**</span></span>  
<span data-ttu-id="361a6-142">&ensp;엔진: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="361a6-142">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="361a6-143">&ensp;지원 단계: **보안 및 중요 업데이트**</span><span class="sxs-lookup"><span data-stu-id="361a6-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="361a6-144">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="361a6-144">What's new</span></span>

- <span data-ttu-id="361a6-145">동작 모니터링 엔진 개선</span><span class="sxs-lookup"><span data-stu-id="361a6-145">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="361a6-146">확장된 네트워크 무차별 공격 완화</span><span class="sxs-lookup"><span data-stu-id="361a6-146">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="361a6-147">변조 방지를 사용하도록 설정한 경우 추가 변조 시도 이벤트 생성 [실패](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="361a6-147">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="361a6-148">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="361a6-148">Known Issues</span></span>
<span data-ttu-id="361a6-149">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="361a6-149">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="361a6-150">2021년 2월(플랫폼: 4.18.2102.3 | 엔진: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="361a6-150">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="361a6-151">&ensp;보안 인텔리전스 업데이트 버전: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="361a6-151">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="361a6-152">&ensp;릴리스: **2021년 3월 9일**</span><span class="sxs-lookup"><span data-stu-id="361a6-152">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="361a6-153">&ensp;플랫폼: **4.19.2102.3**</span><span class="sxs-lookup"><span data-stu-id="361a6-153">&ensp;Platform: **4.19.2102.3**</span></span>  
<span data-ttu-id="361a6-154">&ensp;엔진: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="361a6-154">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="361a6-155">&ensp;지원 단계: **보안 및 중요 업데이트**</span><span class="sxs-lookup"><span data-stu-id="361a6-155">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="361a6-156">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="361a6-156">What's new</span></span>

- <span data-ttu-id="361a6-157">변조 방지를 통한 [서비스 복구 개선](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="361a6-157">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="361a6-158">변조 보호 범위 확장</span><span class="sxs-lookup"><span data-stu-id="361a6-158">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="361a6-159">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="361a6-159">Known Issues</span></span>
<span data-ttu-id="361a6-160">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="361a6-160">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="361a6-161">2021년 1월(플랫폼: 4.18.2101.9 | 엔진: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="361a6-161">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="361a6-162">&ensp;보안 인텔리전스 업데이트 버전: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="361a6-162">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="361a6-163">&ensp;릴리스: **2021년 2월 2일**</span><span class="sxs-lookup"><span data-stu-id="361a6-163">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="361a6-164">&ensp;플랫폼: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="361a6-164">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="361a6-165">&ensp;엔진: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="361a6-165">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="361a6-166">&ensp;지원 단계: **보안 및 중요 업데이트**</span><span class="sxs-lookup"><span data-stu-id="361a6-166">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="361a6-167">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="361a6-167">What's new</span></span>

- <span data-ttu-id="361a6-168">셸 코드 악용 감지 개선</span><span class="sxs-lookup"><span data-stu-id="361a6-168">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="361a6-169">자격 증명 도용 시도에 대한 가시성 향상</span><span class="sxs-lookup"><span data-stu-id="361a6-169">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="361a6-170">Microsoft Defender 바이러스 백신 서비스의 향상된 제거 기능</span><span class="sxs-lookup"><span data-stu-id="361a6-170">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="361a6-171">x64 에뮬 ARM 지원 개선</span><span class="sxs-lookup"><span data-stu-id="361a6-171">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="361a6-172">해결 방법: EDR 차단 알림은 실시간 보호가 초기 검색을 수행한 후 위협 기록에 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="361a6-172">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="361a6-173">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="361a6-173">Known Issues</span></span>
<span data-ttu-id="361a6-174">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="361a6-174">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="361a6-175">이전 버전 업데이트: 기술 업그레이드 지원만</span><span class="sxs-lookup"><span data-stu-id="361a6-175">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="361a6-176">새 패키지 버전이 출시된 후 이전 두 버전에 대한 지원은 기술 지원으로만 축소됩니다.</span><span class="sxs-lookup"><span data-stu-id="361a6-176">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="361a6-177">이 섹션에 나열된 버전보다 오래된 버전은 기술 업그레이드 지원 전용으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="361a6-177">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="361a6-178">2020년 11월-2020년 11월(플랫폼: 4.18.2011.6 | 엔진: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="361a6-178">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="361a6-179">&ensp;보안 인텔리전스 업데이트 버전: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="361a6-179">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="361a6-180">&ensp;릴리스: **2020년 12월 3일**</span><span class="sxs-lookup"><span data-stu-id="361a6-180">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="361a6-181">&ensp;플랫폼: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="361a6-181">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="361a6-182">&ensp;엔진: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="361a6-182">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="361a6-183">&ensp;지원 단계: **보안 및 중요 업데이트**</span><span class="sxs-lookup"><span data-stu-id="361a6-183">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="361a6-184">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="361a6-184">What's new</span></span>

- <span data-ttu-id="361a6-185">향상된 [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) 상태 지원 로깅</span><span class="sxs-lookup"><span data-stu-id="361a6-185">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="361a6-186">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="361a6-186">Known Issues</span></span>
<span data-ttu-id="361a6-187">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="361a6-187">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="361a6-188">2020년 10월(플랫폼: 4.18.2010.7 | 엔진: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="361a6-188">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="361a6-189">&ensp;보안 인텔리전스 업데이트 버전: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="361a6-189">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="361a6-190">&ensp;릴리스: **2020년 10월 29일**</span><span class="sxs-lookup"><span data-stu-id="361a6-190">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="361a6-191">&ensp;플랫폼: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="361a6-191">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="361a6-192">&ensp;엔진: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="361a6-192">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="361a6-193">&ensp;지원 단계: **보안 및 중요 업데이트**</span><span class="sxs-lookup"><span data-stu-id="361a6-193">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="361a6-194">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="361a6-194">What's new</span></span>

- <span data-ttu-id="361a6-195">특수 위협 범주에 대한 새 설명</span><span class="sxs-lookup"><span data-stu-id="361a6-195">New descriptions for special threat categories</span></span>
- <span data-ttu-id="361a6-196">향상된 에뮬ation 기능</span><span class="sxs-lookup"><span data-stu-id="361a6-196">Improved emulation capabilities</span></span>
- <span data-ttu-id="361a6-197">향상된 호스트 주소 허용/차단 기능</span><span class="sxs-lookup"><span data-stu-id="361a6-197">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="361a6-198">Defender CSP의 새 옵션에서 로컬 사용자 제외의 무시</span><span class="sxs-lookup"><span data-stu-id="361a6-198">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="361a6-199">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="361a6-199">Known Issues</span></span>

<span data-ttu-id="361a6-200">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="361a6-200">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="361a6-201">2020년 9월(플랫폼: 4.18.2009.7 | 엔진: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="361a6-201">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="361a6-202">&ensp;보안 인텔리전스 업데이트 버전: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="361a6-202">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="361a6-203">&ensp;릴리스: **2020년 10월 1일**</span><span class="sxs-lookup"><span data-stu-id="361a6-203">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="361a6-204">&ensp;플랫폼: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="361a6-204">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="361a6-205">&ensp;엔진: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="361a6-205">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="361a6-206">&ensp;지원 단계: **기술 업그레이드 지원(전용)**</span><span class="sxs-lookup"><span data-stu-id="361a6-206">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="361a6-207">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="361a6-207">What's new</span></span>

- <span data-ttu-id="361a6-208">파일을 Quarantine에서 복원하려면 관리자 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="361a6-208">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="361a6-209">이제 XML 형식 이벤트가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="361a6-209">XML formatted events are now supported</span></span>
- <span data-ttu-id="361a6-210">제외 병합을 외면하기 위한 CSP 지원</span><span class="sxs-lookup"><span data-stu-id="361a6-210">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="361a6-211">새 관리 인터페이스:</span><span class="sxs-lookup"><span data-stu-id="361a6-211">New management interfaces for:</span></span>
   - <span data-ttu-id="361a6-212">UDP 검사</span><span class="sxs-lookup"><span data-stu-id="361a6-212">UDP Inspection</span></span>
   - <span data-ttu-id="361a6-213">Server 2019의 네트워크 보호</span><span class="sxs-lookup"><span data-stu-id="361a6-213">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="361a6-214">네트워크 보호를 위한 IP 주소 제외</span><span class="sxs-lookup"><span data-stu-id="361a6-214">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="361a6-215">TPM 측정에 대한 가시성 향상</span><span class="sxs-lookup"><span data-stu-id="361a6-215">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="361a6-216">개선된 Office VBA 모듈 검사</span><span class="sxs-lookup"><span data-stu-id="361a6-216">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="361a6-217">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="361a6-217">Known Issues</span></span>

<span data-ttu-id="361a6-218">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="361a6-218">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="361a6-219">2020년 8월(플랫폼: 4.18.2008.9 | 엔진: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="361a6-219">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="361a6-220">&ensp;보안 인텔리전스 업데이트 버전: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="361a6-220">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="361a6-221">&ensp;릴리스: **2020년 8월 27일**</span><span class="sxs-lookup"><span data-stu-id="361a6-221">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="361a6-222">&ensp;플랫폼: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="361a6-222">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="361a6-223">&ensp;엔진: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="361a6-223">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="361a6-224">&ensp;지원 단계: **기술 업그레이드 지원(전용)**</span><span class="sxs-lookup"><span data-stu-id="361a6-224">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="361a6-225">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="361a6-225">What's new</span></span>

- <span data-ttu-id="361a6-226">원격 분석 이벤트 추가</span><span class="sxs-lookup"><span data-stu-id="361a6-226">Add more telemetry events</span></span>
- <span data-ttu-id="361a6-227">향상된 검사 이벤트 원격 분석</span><span class="sxs-lookup"><span data-stu-id="361a6-227">Improved scan event telemetry</span></span>
- <span data-ttu-id="361a6-228">메모리 검사에 대한 향상된 동작 모니터링</span><span class="sxs-lookup"><span data-stu-id="361a6-228">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="361a6-229">향상된 매크로 스트림 검사</span><span class="sxs-lookup"><span data-stu-id="361a6-229">Improved macro streams scanning</span></span>
- <span data-ttu-id="361a6-230">`AMRunningMode`PowerShell cmdlet에 Get-MpComputerStatus 추가</span><span class="sxs-lookup"><span data-stu-id="361a6-230">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="361a6-231">[DisableAntiSpyware는](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="361a6-231">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="361a6-232">Microsoft Defender 바이러스 백신은 다른 바이러스 백신 프로그램을 감지하면 자동으로 꺼집니다.</span><span class="sxs-lookup"><span data-stu-id="361a6-232">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="361a6-233">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="361a6-233">Known Issues</span></span>
<span data-ttu-id="361a6-234">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="361a6-234">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="361a6-235">2020년 7월(플랫폼: 4.18.2007.8 | 엔진: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="361a6-235">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="361a6-236">&ensp;보안 인텔리전스 업데이트 버전: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="361a6-236">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="361a6-237">&ensp;릴리스: **2020년 7월 28일**</span><span class="sxs-lookup"><span data-stu-id="361a6-237">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="361a6-238">&ensp;플랫폼: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="361a6-238">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="361a6-239">&ensp;엔진: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="361a6-239">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="361a6-240">&ensp;지원 단계: **기술 업그레이드 지원(전용)**</span><span class="sxs-lookup"><span data-stu-id="361a6-240">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="361a6-241">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="361a6-241">What's new</span></span>

- <span data-ttu-id="361a6-242">BITS에 대한 향상된 원격 분석</span><span class="sxs-lookup"><span data-stu-id="361a6-242">Improved telemetry for BITS</span></span>
- <span data-ttu-id="361a6-243">Authenticode 코드 서명 인증서 유효성 검사 개선</span><span class="sxs-lookup"><span data-stu-id="361a6-243">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="361a6-244">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="361a6-244">Known Issues</span></span>
<span data-ttu-id="361a6-245">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="361a6-245">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="361a6-246">2020년 6월(플랫폼: 4.18.2006.10 | 엔진: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="361a6-246">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="361a6-247">&ensp;보안 인텔리전스 업데이트 버전: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="361a6-247">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="361a6-248">&ensp;릴리스: **2020년 6월 22일**</span><span class="sxs-lookup"><span data-stu-id="361a6-248">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="361a6-249">&ensp;플랫폼: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="361a6-249">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="361a6-250">&ensp;엔진: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="361a6-250">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="361a6-251">&ensp;지원 단계: **기술 업그레이드 지원(전용)**</span><span class="sxs-lookup"><span data-stu-id="361a6-251">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="361a6-252">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="361a6-252">What's new</span></span>

- <span data-ttu-id="361a6-253">지원 [로그의 위치를 지정할 수 있습니다.](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="361a6-253">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="361a6-254">수동 모드에서 적극적인 catchup 검사 건너뛰기</span><span class="sxs-lookup"><span data-stu-id="361a6-254">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="361a6-255">데이터 데이터 연결에서 Defender 업데이트 허용</span><span class="sxs-lookup"><span data-stu-id="361a6-255">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="361a6-256">캐싱을 사용하지 않도록 설정한 경우의 고정 성능 조정</span><span class="sxs-lookup"><span data-stu-id="361a6-256">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="361a6-257">고정 레지스트리 쿼리</span><span class="sxs-lookup"><span data-stu-id="361a6-257">Fixed registry query</span></span> 
- <span data-ttu-id="361a6-258">ADMX의 검사 시간 임의 지정 수정</span><span class="sxs-lookup"><span data-stu-id="361a6-258">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="361a6-259">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="361a6-259">Known Issues</span></span>
<span data-ttu-id="361a6-260">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="361a6-260">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="361a6-261">2020년 5월(플랫폼: 4.18.2005.4 | 엔진: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="361a6-261">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="361a6-262">&ensp;보안 인텔리전스 업데이트 버전: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="361a6-262">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="361a6-263">&ensp;릴리스: **2020년 5월 26일**</span><span class="sxs-lookup"><span data-stu-id="361a6-263">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="361a6-264">&ensp;플랫폼: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="361a6-264">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="361a6-265">&ensp;엔진: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="361a6-265">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="361a6-266">&ensp;지원 단계: **기술 업그레이드 지원(전용)**</span><span class="sxs-lookup"><span data-stu-id="361a6-266">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="361a6-267">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="361a6-267">What's new</span></span>

- <span data-ttu-id="361a6-268">검사 이벤트에 대한 로깅 개선</span><span class="sxs-lookup"><span data-stu-id="361a6-268">Improved logging for scan events</span></span>
- <span data-ttu-id="361a6-269">향상된 사용자 모드 크래시 처리.</span><span class="sxs-lookup"><span data-stu-id="361a6-269">Improved user mode crash handling.</span></span>
- <span data-ttu-id="361a6-270">변조 방지를 위한 이벤트 추적이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="361a6-270">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="361a6-271">AMSI 샘플 제출 수정</span><span class="sxs-lookup"><span data-stu-id="361a6-271">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="361a6-272">AMSI 클라우드 차단 수정</span><span class="sxs-lookup"><span data-stu-id="361a6-272">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="361a6-273">고정 보안 업데이트 설치 로그</span><span class="sxs-lookup"><span data-stu-id="361a6-273">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="361a6-274">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="361a6-274">Known Issues</span></span>
<span data-ttu-id="361a6-275">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="361a6-275">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="361a6-276">2020년 4월(플랫폼: 4.18.2004.6 | 엔진: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="361a6-276">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="361a6-277">&ensp;보안 인텔리전스 업데이트 버전: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="361a6-277">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="361a6-278">&ensp;릴리스: **2020년 4월 30일**</span><span class="sxs-lookup"><span data-stu-id="361a6-278">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="361a6-279">&ensp;플랫폼: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="361a6-279">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="361a6-280">&ensp;엔진: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="361a6-280">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="361a6-281">&ensp;지원 단계: **기술 업그레이드 지원(전용)**</span><span class="sxs-lookup"><span data-stu-id="361a6-281">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="361a6-282">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="361a6-282">What's new</span></span>
- <span data-ttu-id="361a6-283">WDfilter 개선</span><span class="sxs-lookup"><span data-stu-id="361a6-283">WDfilter improvements</span></span>
- <span data-ttu-id="361a6-284">더 실행 가능한 이벤트 데이터를 추가하여 표면 감소 감지 이벤트 공격</span><span class="sxs-lookup"><span data-stu-id="361a6-284">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="361a6-285">진단 데이터 및 WMI의 고정 버전 정보</span><span class="sxs-lookup"><span data-stu-id="361a6-285">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="361a6-286">플랫폼 업데이트 후 UI에서 잘못된 플랫폼 버전 수정</span><span class="sxs-lookup"><span data-stu-id="361a6-286">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="361a6-287">파일 없는 위협 방지를 위한 동적 URL intel</span><span class="sxs-lookup"><span data-stu-id="361a6-287">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="361a6-288">UEFI 검사 기능</span><span class="sxs-lookup"><span data-stu-id="361a6-288">UEFI scan capability</span></span>
- <span data-ttu-id="361a6-289">업데이트 로깅 확장</span><span class="sxs-lookup"><span data-stu-id="361a6-289">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="361a6-290">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="361a6-290">Known Issues</span></span>
<span data-ttu-id="361a6-291">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="361a6-291">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="361a6-292">2020년 3월(플랫폼: 4.18.2003.8 | 엔진: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="361a6-292">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="361a6-293">&ensp;보안 인텔리전스 업데이트 버전: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="361a6-293">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="361a6-294">&ensp;릴리스: **2020년 3월 24일**</span><span class="sxs-lookup"><span data-stu-id="361a6-294">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="361a6-295">&ensp;플랫폼: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="361a6-295">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="361a6-296">&ensp;엔진: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="361a6-296">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="361a6-297">&ensp;지원 단계: **기술 업그레이드 지원(전용)**</span><span class="sxs-lookup"><span data-stu-id="361a6-297">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="361a6-298">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="361a6-298">What's new</span></span>

- <span data-ttu-id="361a6-299">[MpCmdRun에](./command-line-arguments-microsoft-defender-antivirus.md) 추가된 CPU 스로틀 옵션</span><span class="sxs-lookup"><span data-stu-id="361a6-299">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="361a6-300">진단 기능 개선</span><span class="sxs-lookup"><span data-stu-id="361a6-300">Improve diagnostic capability</span></span>
- <span data-ttu-id="361a6-301">보안 인텔리전스 시간 제한 단축(5분)</span><span class="sxs-lookup"><span data-stu-id="361a6-301">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="361a6-302">AMSI 엔진 내부 로그 기능 확장</span><span class="sxs-lookup"><span data-stu-id="361a6-302">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="361a6-303">프로세스 차단에 대한 알림 개선</span><span class="sxs-lookup"><span data-stu-id="361a6-303">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="361a6-304">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="361a6-304">Known Issues</span></span>
<span data-ttu-id="361a6-305">[**Fixed**] Microsoft Defender 바이러스 백신이 검사 실행 시 파일을 건너뛰고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="361a6-305">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="361a6-306">2020년 2월(플랫폼: - | 엔진: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="361a6-306">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="361a6-307">&ensp;보안 인텔리전스 업데이트 버전: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="361a6-307">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="361a6-308">&ensp;릴리스: **2020년 2월 25일**</span><span class="sxs-lookup"><span data-stu-id="361a6-308">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="361a6-309">&ensp;플랫폼/클라이언트: **-**</span><span class="sxs-lookup"><span data-stu-id="361a6-309">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="361a6-310">&ensp;엔진: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="361a6-310">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="361a6-311">&ensp;지원 단계: **기술 업그레이드 지원(전용)**</span><span class="sxs-lookup"><span data-stu-id="361a6-311">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="361a6-312">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="361a6-312">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="361a6-313">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="361a6-313">Known Issues</span></span>
<span data-ttu-id="361a6-314">알려진 문제 없음</span><span class="sxs-lookup"><span data-stu-id="361a6-314">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="361a6-315">2020년 1월(플랫폼: 4.18.2001.10 | 엔진: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="361a6-315">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="361a6-316">보안 인텔리전스 업데이트 버전: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="361a6-316">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="361a6-317">릴리스: **2020년 1월 30일**</span><span class="sxs-lookup"><span data-stu-id="361a6-317">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="361a6-318">플랫폼/클라이언트: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="361a6-318">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="361a6-319">엔진: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="361a6-319">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="361a6-320">&ensp;지원 단계: **기술 업그레이드 지원(전용)**</span><span class="sxs-lookup"><span data-stu-id="361a6-320">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="361a6-321">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="361a6-321">What's new</span></span>

- <span data-ttu-id="361a6-322">Exchange를 통해 WS2016의 고정 BSOD</span><span class="sxs-lookup"><span data-stu-id="361a6-322">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="361a6-323">TMP가 네트워크 경로로 리디렉션될 때 플랫폼 업데이트 지원</span><span class="sxs-lookup"><span data-stu-id="361a6-323">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="361a6-324">플랫폼 및 엔진 버전이 [WDSI에 추가됩니다.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="361a6-324">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="361a6-325">긴급 서명 업데이트를 [수동 모드로 확장](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="361a6-325">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="361a6-326">4.18.1911.3 중단 수정</span><span class="sxs-lookup"><span data-stu-id="361a6-326">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="361a6-327">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="361a6-327">Known Issues</span></span>

<span data-ttu-id="361a6-328">[**고정**] [](/windows-hardware/design/device-experiences/modern-standby) 최신 대기 모드를 활용하는 장치는 보호의 간격을 Windows Defender 필터 드라이버가 중단될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="361a6-328">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="361a6-329">영향을 받는 컴퓨터는 최신 맬웨어 방지 플랫폼으로 업데이트되지 않은 것으로 고객에게 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="361a6-329">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="361a6-330">이 업데이트는:</span><span class="sxs-lookup"><span data-stu-id="361a6-330">This update is:</span></span>
> - <span data-ttu-id="361a6-331">SHA2를 지원하기 위해 더 낮은 버전의 플랫폼을 실행하는 RS1 장치에서 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="361a6-331">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="361a6-332">문제가 있는 시스템에 대한 재부팅 플래그가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="361a6-332">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="361a6-333">는 2020년 4월에 다시 출시될 예정으로, 향후 가용성을 유지하기 위해 최신 업데이트로 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="361a6-333">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="361a6-334">는 재부팅 요구 사항으로 인해 업데이트로 분류됩니다. 및</span><span class="sxs-lookup"><span data-stu-id="361a6-334">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="361a6-335">는 Windows [업데이트에서만 제공됩니다.](https://support.microsoft.com/help/4027667/windows-10-update)</span><span class="sxs-lookup"><span data-stu-id="361a6-335">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="361a6-336">2019년 11월부터 2019년 11월까지(플랫폼: 4.18.1911.3 | 엔진: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="361a6-336">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="361a6-337">보안 인텔리전스 업데이트 버전: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="361a6-337">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="361a6-338">릴리스: **2019년 12월 7일**</span><span class="sxs-lookup"><span data-stu-id="361a6-338">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="361a6-339">플랫폼: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="361a6-339">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="361a6-340">엔진: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="361a6-340">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="361a6-341">지원 단계: **지원 없음**</span><span class="sxs-lookup"><span data-stu-id="361a6-341">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="361a6-342">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="361a6-342">What's new</span></span>

- <span data-ttu-id="361a6-343">고정 MpCmdRun 추적 수준</span><span class="sxs-lookup"><span data-stu-id="361a6-343">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="361a6-344">WDFilter 버전 정보 수정</span><span class="sxs-lookup"><span data-stu-id="361a6-344">Fixed WDFilter version info</span></span>
- <span data-ttu-id="361a6-345">알림 개선(PUA)</span><span class="sxs-lookup"><span data-stu-id="361a6-345">Improve notifications (PUA)</span></span>
- <span data-ttu-id="361a6-346">MRT 로그를 추가하여 파일 지원</span><span class="sxs-lookup"><span data-stu-id="361a6-346">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="361a6-347">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="361a6-347">Known Issues</span></span>
<span data-ttu-id="361a6-348">이 업데이트를 설치하면 장치에 점프 패키지 4.10.2001.10이 최신 플랫폼 버전으로 업데이트될 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="361a6-348">When this update is installed, the device needs the jump package 4.10.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="361a6-349">Microsoft Defender 바이러스 백신 플랫폼 지원</span><span class="sxs-lookup"><span data-stu-id="361a6-349">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="361a6-350">플랫폼 및 엔진 업데이트는 월별 케이던스에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="361a6-350">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="361a6-351">완전히 지원받기 위해 최신 플랫폼 업데이트를 최신으로 유지하세요.</span><span class="sxs-lookup"><span data-stu-id="361a6-351">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="361a6-352">지원 구조는 동적이며, 최신 플랫폼 버전의 가용성에 따라 다음 두 단계로 진화합니다.</span><span class="sxs-lookup"><span data-stu-id="361a6-352">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="361a6-353">**보안 및** 중요 업데이트 서비스 단계 - 최신 플랫폼 버전을 실행하는 경우 맬웨어 방지 플랫폼에 대한 보안 및 중요 업데이트를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="361a6-353">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="361a6-354">**기술 지원(전용) 단계** - 새 플랫폼 버전이 출시된 후 이전 버전(N-2)에 대한 지원은 기술 지원으로만 축소됩니다.</span><span class="sxs-lookup"><span data-stu-id="361a6-354">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="361a6-355">N-2 이전의 플랫폼 버전은 더 이상 지원되지 않습니다.\*</span><span class="sxs-lookup"><span data-stu-id="361a6-355">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="361a6-356">\* Windows 10 릴리스 [버전(Windows 10](#platform-version-included-with-windows-10-releases)릴리스에 포함된 플랫폼 버전 참조)에서 최신 플랫폼 버전으로 업그레이드하기 위한 기술 지원이 계속 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="361a6-356">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="361a6-357">기술 지원(전용) 단계 중에는 상업적으로 합리적인 지원 인시던트가 Microsoft 고객 서비스 & 지원 및 Microsoft의 관리 지원 서비스(예: 프리미어 지원)를 통해 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="361a6-357">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="361a6-358">지원 인시던트가 추가 지침을 위해 개발로 에스컬레이터해야 하는 경우, 비보안 업데이트가 필요하거나, 보안 업데이트가 필요한 경우 고객에게 최신 플랫폼 버전 또는 중간 업데이트(\*)로 업그레이드할지 묻는 요청이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="361a6-358">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="361a6-359">Windows 10 릴리스에 포함된 플랫폼 버전</span><span class="sxs-lookup"><span data-stu-id="361a6-359">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="361a6-360">아래 표에는 최신 Windows 10 릴리스와 함께 제공된 Microsoft Defender 바이러스 백신 플랫폼 및 엔진 버전이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="361a6-360">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="361a6-361">Windows 10 릴리스</span><span class="sxs-lookup"><span data-stu-id="361a6-361">Windows 10 release</span></span>  |<span data-ttu-id="361a6-362">플랫폼 버전</span><span class="sxs-lookup"><span data-stu-id="361a6-362">Platform version</span></span>  |<span data-ttu-id="361a6-363">엔진 버전</span><span class="sxs-lookup"><span data-stu-id="361a6-363">Engine version</span></span> |<span data-ttu-id="361a6-364">지원 단계</span><span class="sxs-lookup"><span data-stu-id="361a6-364">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="361a6-365">2004(20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="361a6-365">2004  (20H1/20H2)</span></span> |<span data-ttu-id="361a6-366">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="361a6-366">4.18.1909.6</span></span> |<span data-ttu-id="361a6-367">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="361a6-367">1.1.17000.2</span></span> | <span data-ttu-id="361a6-368">기술 업그레이드 지원(전용)</span><span class="sxs-lookup"><span data-stu-id="361a6-368">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="361a6-369">1909(19H2)</span><span class="sxs-lookup"><span data-stu-id="361a6-369">1909  (19H2)</span></span> |<span data-ttu-id="361a6-370">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="361a6-370">4.18.1902.5</span></span> |<span data-ttu-id="361a6-371">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="361a6-371">1.1.16700.3</span></span> | <span data-ttu-id="361a6-372">기술 업그레이드 지원(전용)</span><span class="sxs-lookup"><span data-stu-id="361a6-372">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="361a6-373">1903(19H1)</span><span class="sxs-lookup"><span data-stu-id="361a6-373">1903  (19H1)</span></span> |<span data-ttu-id="361a6-374">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="361a6-374">4.18.1902.5</span></span> |<span data-ttu-id="361a6-375">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="361a6-375">1.1.15600.4</span></span> | <span data-ttu-id="361a6-376">기술 업그레이드 지원(전용)</span><span class="sxs-lookup"><span data-stu-id="361a6-376">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="361a6-377">1809(RS5)</span><span class="sxs-lookup"><span data-stu-id="361a6-377">1809  (RS5)</span></span> |<span data-ttu-id="361a6-378">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="361a6-378">4.18.1807.18075</span></span> |<span data-ttu-id="361a6-379">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="361a6-379">1.1.15000.2</span></span> | <span data-ttu-id="361a6-380">기술 업그레이드 지원(전용)</span><span class="sxs-lookup"><span data-stu-id="361a6-380">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="361a6-381">1803(RS4)</span><span class="sxs-lookup"><span data-stu-id="361a6-381">1803  (RS4)</span></span> |<span data-ttu-id="361a6-382">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="361a6-382">4.13.17134.1</span></span> |<span data-ttu-id="361a6-383">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="361a6-383">1.1.14600.4</span></span> | <span data-ttu-id="361a6-384">기술 업그레이드 지원(전용)</span><span class="sxs-lookup"><span data-stu-id="361a6-384">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="361a6-385">1709(RS3)</span><span class="sxs-lookup"><span data-stu-id="361a6-385">1709  (RS3)</span></span> |<span data-ttu-id="361a6-386">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="361a6-386">4.12.16299.15</span></span> |<span data-ttu-id="361a6-387">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="361a6-387">1.1.14104.0</span></span> | <span data-ttu-id="361a6-388">기술 업그레이드 지원(전용)</span><span class="sxs-lookup"><span data-stu-id="361a6-388">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="361a6-389">1703(RS2)</span><span class="sxs-lookup"><span data-stu-id="361a6-389">1703  (RS2)</span></span> |<span data-ttu-id="361a6-390">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="361a6-390">4.11.15603.2</span></span> |<span data-ttu-id="361a6-391">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="361a6-391">1.1.13504.0</span></span> | <span data-ttu-id="361a6-392">기술 업그레이드 지원(전용)</span><span class="sxs-lookup"><span data-stu-id="361a6-392">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="361a6-393">1607(RS1)</span><span class="sxs-lookup"><span data-stu-id="361a6-393">1607 (RS1)</span></span> |<span data-ttu-id="361a6-394">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="361a6-394">4.10.14393.3683</span></span> |<span data-ttu-id="361a6-395">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="361a6-395">1.1.12805.0</span></span> | <span data-ttu-id="361a6-396">기술 업그레이드 지원(전용)</span><span class="sxs-lookup"><span data-stu-id="361a6-396">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="361a6-397">Windows 10 릴리스 정보는 [Windows 수명 주기 팩트 시트 를 참조하세요.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)</span><span class="sxs-lookup"><span data-stu-id="361a6-397">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="361a6-398">DISM(배포 이미지 서비스 및 관리)에 대한 업데이트</span><span class="sxs-lookup"><span data-stu-id="361a6-398">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="361a6-399">최신 바이러스 백신 및 맬웨어 방지 업데이트를 사용하여 Windows 10(Enterprise, Pro 및 Home 버전), Windows Server 2019 및 Windows Server 2016 OS 설치 이미지를 업데이트하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="361a6-399">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="361a6-400">OS 설치 이미지를 최신으로 유지하면 보호 격차를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="361a6-400">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="361a6-401">자세한 내용은 Windows 운영 체제 설치 [이미지용 Microsoft Defender 업데이트를 참조하세요.](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)</span><span class="sxs-lookup"><span data-stu-id="361a6-401">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="361a6-402">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="361a6-402">1.1.2104.01</span></span></summary>

<span data-ttu-id="361a6-403">&ensp;패키지 버전: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="361a6-403">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="361a6-404">&ensp;플랫폼 버전: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="361a6-404">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="361a6-405">&ensp;엔진 버전: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="361a6-405">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="361a6-406">&ensp;서명 버전: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="361a6-406">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="361a6-407">수정</span><span class="sxs-lookup"><span data-stu-id="361a6-407">Fixes</span></span>
- <span data-ttu-id="361a6-408">없음</span><span class="sxs-lookup"><span data-stu-id="361a6-408">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="361a6-409">추가 정보</span><span class="sxs-lookup"><span data-stu-id="361a6-409">Additional information</span></span>
- <span data-ttu-id="361a6-410">없음</span><span class="sxs-lookup"><span data-stu-id="361a6-410">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="361a6-411">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="361a6-411">1.1.2103.01</span></span></summary>

<span data-ttu-id="361a6-412">&ensp;패키지 버전: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="361a6-412">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="361a6-413">&ensp;플랫폼 버전: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="361a6-413">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="361a6-414">&ensp;엔진 버전: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="361a6-414">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="361a6-415">&ensp;서명 버전: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="361a6-415">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="361a6-416">수정</span><span class="sxs-lookup"><span data-stu-id="361a6-416">Fixes</span></span>
- <span data-ttu-id="361a6-417">없음</span><span class="sxs-lookup"><span data-stu-id="361a6-417">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="361a6-418">추가 정보</span><span class="sxs-lookup"><span data-stu-id="361a6-418">Additional information</span></span>
- <span data-ttu-id="361a6-419">없음</span><span class="sxs-lookup"><span data-stu-id="361a6-419">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="361a6-420">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="361a6-420">1.1.2102.03</span></span></summary>

<span data-ttu-id="361a6-421">&ensp;패키지 버전: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="361a6-421">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="361a6-422">&ensp;플랫폼 버전: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="361a6-422">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="361a6-423">&ensp;엔진 버전: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="361a6-423">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="361a6-424">&ensp;서명 버전: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="361a6-424">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="361a6-425">수정</span><span class="sxs-lookup"><span data-stu-id="361a6-425">Fixes</span></span>
- <span data-ttu-id="361a6-426">없음</span><span class="sxs-lookup"><span data-stu-id="361a6-426">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="361a6-427">추가 정보</span><span class="sxs-lookup"><span data-stu-id="361a6-427">Additional information</span></span>
- <span data-ttu-id="361a6-428">없음</span><span class="sxs-lookup"><span data-stu-id="361a6-428">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="361a6-429">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="361a6-429">1.1.2101.02</span></span></summary>

<span data-ttu-id="361a6-430">&ensp;패키지 버전: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="361a6-430">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="361a6-431">&ensp;플랫폼 버전: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="361a6-431">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="361a6-432">&ensp;엔진 버전: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="361a6-432">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="361a6-433">&ensp;서명 버전: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="361a6-433">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="361a6-434">수정</span><span class="sxs-lookup"><span data-stu-id="361a6-434">Fixes</span></span>
- <span data-ttu-id="361a6-435">없음</span><span class="sxs-lookup"><span data-stu-id="361a6-435">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="361a6-436">추가 정보</span><span class="sxs-lookup"><span data-stu-id="361a6-436">Additional information</span></span>
- <span data-ttu-id="361a6-437">없음</span><span class="sxs-lookup"><span data-stu-id="361a6-437">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="361a6-438">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="361a6-438">1.1.2012.01</span></span></summary>

<span data-ttu-id="361a6-439">&ensp;패키지 버전: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="361a6-439">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="361a6-440">&ensp;플랫폼 버전: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="361a6-440">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="361a6-441">&ensp;엔진 버전: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="361a6-441">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="361a6-442">&ensp;서명 버전: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="361a6-442">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="361a6-443">수정</span><span class="sxs-lookup"><span data-stu-id="361a6-443">Fixes</span></span>
- <span data-ttu-id="361a6-444">없음</span><span class="sxs-lookup"><span data-stu-id="361a6-444">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="361a6-445">추가 정보</span><span class="sxs-lookup"><span data-stu-id="361a6-445">Additional information</span></span>
- <span data-ttu-id="361a6-446">없음</span><span class="sxs-lookup"><span data-stu-id="361a6-446">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="361a6-447">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="361a6-447">1.1.2011.02</span></span></summary>

<span data-ttu-id="361a6-448">&ensp;패키지 버전: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="361a6-448">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="361a6-449">&ensp;플랫폼 버전: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="361a6-449">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="361a6-450">&ensp;엔진 버전: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="361a6-450">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="361a6-451">&ensp;서명 버전: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="361a6-451">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="361a6-452">수정</span><span class="sxs-lookup"><span data-stu-id="361a6-452">Fixes</span></span>
- <span data-ttu-id="361a6-453">없음</span><span class="sxs-lookup"><span data-stu-id="361a6-453">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="361a6-454">추가 정보</span><span class="sxs-lookup"><span data-stu-id="361a6-454">Additional information</span></span>
- <span data-ttu-id="361a6-455">새로 고쳐진 Microsoft Defender 바이러스 백신 서명</span><span class="sxs-lookup"><span data-stu-id="361a6-455">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="361a6-456">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="361a6-456">1.1.2011.01</span></span></summary>

<span data-ttu-id="361a6-457">&ensp;패키지 버전: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="361a6-457">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="361a6-458">&ensp;플랫폼 버전: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="361a6-458">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="361a6-459">&ensp;엔진 버전: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="361a6-459">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="361a6-460">&ensp;서명 버전: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="361a6-460">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="361a6-461">수정</span><span class="sxs-lookup"><span data-stu-id="361a6-461">Fixes</span></span>
- <span data-ttu-id="361a6-462">없음</span><span class="sxs-lookup"><span data-stu-id="361a6-462">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="361a6-463">추가 정보</span><span class="sxs-lookup"><span data-stu-id="361a6-463">Additional information</span></span>
- <span data-ttu-id="361a6-464">없음</span><span class="sxs-lookup"><span data-stu-id="361a6-464">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="361a6-465">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="361a6-465">1.1.2009.10</span></span></summary>

<span data-ttu-id="361a6-466">&ensp;패키지 버전: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="361a6-466">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="361a6-467">&ensp;플랫폼 버전: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="361a6-467">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="361a6-468">&ensp;엔진 버전: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="361a6-468">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="361a6-469">&ensp;서명 버전: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="361a6-469">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="361a6-470">수정</span><span class="sxs-lookup"><span data-stu-id="361a6-470">Fixes</span></span>
- <span data-ttu-id="361a6-471">없음</span><span class="sxs-lookup"><span data-stu-id="361a6-471">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="361a6-472">추가 정보</span><span class="sxs-lookup"><span data-stu-id="361a6-472">Additional information</span></span>
- <span data-ttu-id="361a6-473">Windows 10 RS1 이상 OS 설치 이미지에 대한 지원이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="361a6-473">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="361a6-474">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="361a6-474">Additional resources</span></span>

| <span data-ttu-id="361a6-475">문서</span><span class="sxs-lookup"><span data-stu-id="361a6-475">Article</span></span> | <span data-ttu-id="361a6-476">설명</span><span class="sxs-lookup"><span data-stu-id="361a6-476">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="361a6-477">Windows 운영 체제 설치 이미지에 대한 Microsoft Defender 업데이트</span><span class="sxs-lookup"><span data-stu-id="361a6-477">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="361a6-478">OS 설치 이미지(WIM 및 VHD 파일)에 대한 맬웨어 방지 업데이트 패키지를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="361a6-478">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="361a6-479">Windows 10(Enterprise, Pro 및 Home 버전), Windows Server 2019 및 Windows Server 2016 설치 이미지에 대한 Microsoft Defender 바이러스 백신 업데이트를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="361a6-479">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="361a6-480">보호 업데이트를 다운로드하고 적용하는 방법 관리</span><span class="sxs-lookup"><span data-stu-id="361a6-480">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="361a6-481">보호 업데이트는 여러 소스를 통해 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="361a6-481">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="361a6-482">보호 업데이트를 다운로드하고 적용해야 하는 경우 관리</span><span class="sxs-lookup"><span data-stu-id="361a6-482">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="361a6-483">보호 업데이트를 다운로드해야 하는 경우를 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="361a6-483">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="361a6-484">최신이 지난 끝점에 대한 업데이트 관리</span><span class="sxs-lookup"><span data-stu-id="361a6-484">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="361a6-485">끝점에서 업데이트 또는 예약된 검사가 누락된 경우 다음에 사용자가 로그인할 때 강제로 업데이트를 실행하거나 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="361a6-485">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="361a6-486">이벤트 기반 강제 업데이트 관리</span><span class="sxs-lookup"><span data-stu-id="361a6-486">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="361a6-487">시작 시 또는 특정 클라우드 제공 보호 이벤트 후에 보호 업데이트를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="361a6-487">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="361a6-488">모바일 장치 및 VM(가상 컴퓨터)에 대한 업데이트 관리</span><span class="sxs-lookup"><span data-stu-id="361a6-488">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="361a6-489">모바일 장치 및 가상 머신에 특히 유용한 배터리 전원에서 업데이트가 발생해야 하는지 여부와 같은 설정을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="361a6-489">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
