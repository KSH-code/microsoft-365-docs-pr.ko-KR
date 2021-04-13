---
title: Microsoft Defender 바이러스 백신을 통해 정기적인 빠른 검사 및 전체 검사 예약
description: 실행해야 하는 시간 및 전체 검사 또는 빠른 검사로 실행 여부를 포함하여 재발(예약된) 검사 설정
keywords: 빠른 검사, 전체 검사, 빠른 대 전체, 검사 예약, 매일, 매주, 시간, 예약, 정기적인
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/02/2020
ms.reviewer: pauhijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 66907fca7a117eeba7ca0b9bd95d59af24c31341
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691301"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a><span data-ttu-id="4ae74-104">예약된 빠른 또는 전체 Microsoft Defender 바이러스 백신 검사 구성</span><span class="sxs-lookup"><span data-stu-id="4ae74-104">Configure scheduled quick or full Microsoft Defender Antivirus scans</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="4ae74-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="4ae74-105">**Applies to:**</span></span>

- <span data-ttu-id="4ae74-106">[엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/) </span><span class="sxs-lookup"><span data-stu-id="4ae74-106">[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)</span></span>


> [!NOTE]
> <span data-ttu-id="4ae74-107">기본적으로 Microsoft Defender 바이러스 백신은 예약된 검사 시간 15분 전에 업데이트를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae74-107">By default, Microsoft Defender Antivirus checks for an update 15 minutes before the time of any scheduled scans.</span></span> <span data-ttu-id="4ae74-108">이 [기본값을](manage-protection-update-schedule-microsoft-defender-antivirus.md) 다시 설정하기 위해 보호 업데이트를 다운로드하고 적용해야 하는 일정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ae74-108">You can [Manage the schedule for when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) to override this default.</span></span> 

<span data-ttu-id="4ae74-109">항상 실시간 보호 및 필요한 경우 [](run-scan-microsoft-defender-antivirus.md) 검사뿐만 아니라 정기적인 예약된 검사도 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ae74-109">In addition to always-on real-time protection and [on-demand](run-scan-microsoft-defender-antivirus.md) scans, you can set up regular, scheduled scans.</span></span> 

<span data-ttu-id="4ae74-110">검사 유형, 검사 발생 날짜 및 보호 업데이트 후 또는 끝점을 사용 중이면 검사가 실행될지 구성할 수 있습니다. [](manage-protection-updates-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="4ae74-110">You can configure the type of scan, when the scan should occur, and if the scan should occur after a [protection update](manage-protection-updates-microsoft-defender-antivirus.md) or if the endpoint is being used.</span></span> <span data-ttu-id="4ae74-111">수정을 완료하기 위한 특별 검사가 언제 실행될지 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ae74-111">You can also specify when special scans to complete remediation should occur.</span></span>

<span data-ttu-id="4ae74-112">이 문서에서는 그룹 정책, PowerShell cmdlet 및 WMI를 사용하여 예약된 검색을 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae74-112">This article describes how to configure scheduled scans with Group Policy, PowerShell cmdlets, and WMI.</span></span> <span data-ttu-id="4ae74-113">[Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) 또는 Microsoft [Intune을](/mem/intune/configuration/device-restrictions-windows-10)사용하여 일정 검색을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ae74-113">You can also configure schedules scans with [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) or [Microsoft Intune](/mem/intune/configuration/device-restrictions-windows-10).</span></span>

## <a name="to-configure-the-group-policy-settings-described-in-this-article"></a><span data-ttu-id="4ae74-114">이 문서에 설명된 그룹 정책 설정을 구성하려면</span><span class="sxs-lookup"><span data-stu-id="4ae74-114">To configure the Group Policy settings described in this article</span></span>

1.  <span data-ttu-id="4ae74-115">그룹 정책 관리 컴퓨터의 [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))그룹 정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ae74-115">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="4ae74-116">그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="4ae74-116">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="4ae74-117">관리 **템플릿 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ae74-117">Click **Administrative templates**.</span></span>

5.  <span data-ttu-id="4ae74-118">**Microsoft Defender** 바이러스 백신을 > Windows 구성  요소로 트리를 확장한 다음 아래 표에 지정된 위치를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae74-118">Expand the tree to **Windows components > Microsoft Defender Antivirus** and then the **Location** specified in the table below.</span></span>

6. <span data-ttu-id="4ae74-119">아래 표에 지정된 정책 **설정을** 두 번 클릭하고 옵션을 원하는 구성으로 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="4ae74-119">Double-click the policy **Setting** as specified in the table below, and set the option to your desired configuration.</span></span> 

7. <span data-ttu-id="4ae74-120">확인 **을** 클릭하고 다른 설정에 대해 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae74-120">Click **OK**, and repeat for any other settings.</span></span>

<span data-ttu-id="4ae74-121">또한 [보호](manage-protection-update-schedule-microsoft-defender-antivirus.md) 업데이트를 다운로드하여 적용해야 하는 경우 관리 및 사용자가 정책 설정을 로컬로 수정할 수 있도록 허용 안 하도록 허용 항목을 [참조하세요.](configure-local-policy-overrides-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="4ae74-121">Also see the [Manage when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) and [Prevent or allow users to locally modify policy settings](configure-local-policy-overrides-microsoft-defender-antivirus.md) topics.</span></span>

## <a name="quick-scan-versus-full-scan-and-custom-scan"></a><span data-ttu-id="4ae74-122">빠른 검사와 전체 검사 및 사용자 지정 검사</span><span class="sxs-lookup"><span data-stu-id="4ae74-122">Quick scan versus full scan and custom scan</span></span>

<span data-ttu-id="4ae74-123">예약된 검색을 설정할 때 검사가 전체 검사인지 아니면 빠른 검사인지를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ae74-123">When you set up scheduled scans, you can set up whether the scan should be a full or quick scan.</span></span>

<span data-ttu-id="4ae74-124">빠른 검사는 레지스트리 키 및 알려진 Windows 시작 폴더와 같이 시스템으로 시작하기 위해 등록된 맬웨어가 있을 수 있는 모든 위치를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae74-124">Quick scans look at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span> 

<span data-ttu-id="4ae74-125">파일을 [](configure-real-time-protection-microsoft-defender-antivirus.md) 열고 닫을 때 그리고 사용자가 폴더로 이동할 때마다 파일을 검토하는 실시간 보호 기능과 결합된 빠른 검사는 시스템으로 시작되는 맬웨어와 커널 수준 맬웨어에 대해 강력한 범위를 제공하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ae74-125">Combined with [always-on real-time protection capability](configure-real-time-protection-microsoft-defender-antivirus.md) - which reviews files when they are opened and closed, and whenever a user navigates to a folder - a quick scan helps provide strong coverage both for malware that starts with the system and kernel-level malware.</span></span>  

<span data-ttu-id="4ae74-126">대부분의 경우 실시간 보호로 선택되지 않은 맬웨어를 찾기에 빠른 검사가 적절하다는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae74-126">In most instances, this means a quick scan is adequate to find malware that wasn't picked up by real-time protection.</span></span>

<span data-ttu-id="4ae74-127">전체 검사는 맬웨어 위협이 발생하는 끝점에서 보다 철저한 정리가 필요한 비활성 구성 요소가 있는지 식별하는 데 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ae74-127">A full scan can be useful on endpoints that have encountered a malware threat to identify if there are any inactive components that require a more thorough clean-up.</span></span> <span data-ttu-id="4ae74-128">이 경우 필요한 검사 를 실행하는 경우 전체 [검색을 사용할 수 있습니다.](run-scan-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="4ae74-128">In this instance, you may want to use a full scan when running an [on-demand scan](run-scan-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="4ae74-129">사용자 지정 스캔을 사용하면 USB 드라이브와 같이 검사할 파일과 폴더를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ae74-129">A custom scan allows you to specify the files and folders to scan, such as a USB drive.</span></span> 

>[!NOTE]
><span data-ttu-id="4ae74-130">기본적으로 빠른 검사는 USB 드라이브와 같은 탑재된 이동식 장치에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ae74-130">By default, quick scans run on mounted removable devices, such as USB drives.</span></span>

## <a name="set-up-scheduled-scans"></a><span data-ttu-id="4ae74-131">예약된 검사 설정</span><span class="sxs-lookup"><span data-stu-id="4ae74-131">Set up scheduled scans</span></span>

<span data-ttu-id="4ae74-132">예약된 검사는 지정한 날짜와 시간으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ae74-132">Scheduled scans will run at the day and time you specify.</span></span> <span data-ttu-id="4ae74-133">그룹 정책, PowerShell 및 WMI를 사용하여 예약된 검색을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ae74-133">You can use Group Policy, PowerShell, and WMI to configure scheduled scans.</span></span>

>[!NOTE]
><span data-ttu-id="4ae74-134">예약된 전체 검사 중에 컴퓨터의 연결이 풀리며 배터리로 실행되는 경우 예약된 검사는 완료 전에 스캔이 중지된 이벤트 1002와 함께 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ae74-134">If a computer is unplugged and running on battery during a scheduled full scan, the scheduled scan will stop with event 1002, which states that the scan stopped before completion.</span></span> <span data-ttu-id="4ae74-135">Microsoft Defender 바이러스 백신은 다음에 예약된 시간으로 전체 검사가 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ae74-135">Microsoft Defender Antivirus will run a full scan at the next scheduled time.</span></span>

### <a name="use-group-policy-to-schedule-scans"></a><span data-ttu-id="4ae74-136">그룹 정책을 사용하여 검사 예약</span><span class="sxs-lookup"><span data-stu-id="4ae74-136">Use Group Policy to schedule scans</span></span>

|<span data-ttu-id="4ae74-137">위치</span><span class="sxs-lookup"><span data-stu-id="4ae74-137">Location</span></span> | <span data-ttu-id="4ae74-138">설정</span><span class="sxs-lookup"><span data-stu-id="4ae74-138">Setting</span></span> | <span data-ttu-id="4ae74-139">설명</span><span class="sxs-lookup"><span data-stu-id="4ae74-139">Description</span></span> | <span data-ttu-id="4ae74-140">기본 설정(구성되지 않은 경우)</span><span class="sxs-lookup"><span data-stu-id="4ae74-140">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="4ae74-141">검사</span><span class="sxs-lookup"><span data-stu-id="4ae74-141">Scan</span></span> | <span data-ttu-id="4ae74-142">예약된 검사에 사용할 검사 유형 지정</span><span class="sxs-lookup"><span data-stu-id="4ae74-142">Specify the scan type to use for a scheduled scan</span></span> | <span data-ttu-id="4ae74-143">빠른 검사</span><span class="sxs-lookup"><span data-stu-id="4ae74-143">Quick scan</span></span> |
|<span data-ttu-id="4ae74-144">검사</span><span class="sxs-lookup"><span data-stu-id="4ae74-144">Scan</span></span> | <span data-ttu-id="4ae74-145">예약된 검색을 실행할 날짜 지정</span><span class="sxs-lookup"><span data-stu-id="4ae74-145">Specify the day of the week to run a scheduled scan</span></span> | <span data-ttu-id="4ae74-146">검색을 실행할 날짜를 지정하거나 지정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ae74-146">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="4ae74-147">없음</span><span class="sxs-lookup"><span data-stu-id="4ae74-147">Never</span></span> |
|<span data-ttu-id="4ae74-148">검사</span><span class="sxs-lookup"><span data-stu-id="4ae74-148">Scan</span></span> | <span data-ttu-id="4ae74-149">예약된 검색을 실행할 시간 지정</span><span class="sxs-lookup"><span data-stu-id="4ae74-149">Specify the time of day to run a scheduled scan</span></span> | <span data-ttu-id="4ae74-150">자정 이후의 시간(분)을 지정합니다(예: **60** :a.m.).</span><span class="sxs-lookup"><span data-stu-id="4ae74-150">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.).</span></span> | <span data-ttu-id="4ae74-151">2:a.m.</span><span class="sxs-lookup"><span data-stu-id="4ae74-151">2 a.m.</span></span> |
|<span data-ttu-id="4ae74-152">루트</span><span class="sxs-lookup"><span data-stu-id="4ae74-152">Root</span></span> | <span data-ttu-id="4ae74-153">예약된 작업 시간 임의로</span><span class="sxs-lookup"><span data-stu-id="4ae74-153">Randomize scheduled task times</span></span> |<span data-ttu-id="4ae74-154">Microsoft Defender 바이러스 백신: 검사 시작 시간을 0시간에서 4시간 사이의 간격으로 임의로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae74-154">In Microsoft Defender Antivirus: Randomize the start time of the scan to any interval from 0 to 4 hours.</span></span> <br><span data-ttu-id="4ae74-155">FEP/SCEP: 임의 간격에 더하거나 30분을 에서 을(를) 음으로 임의화합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae74-155">In FEP/SCEP: randomize to any interval plus or minus 30 minutes.</span></span> <span data-ttu-id="4ae74-156">이는 VM 또는 VDI 배포에서 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ae74-156">This can be useful in VM or VDI deployments.</span></span> | <span data-ttu-id="4ae74-157">사용</span><span class="sxs-lookup"><span data-stu-id="4ae74-157">Enabled</span></span> |


### <a name="use-powershell-cmdlets-to-schedule-scans"></a><span data-ttu-id="4ae74-158">PowerShell cmdlet을 사용하여 검사 예약</span><span class="sxs-lookup"><span data-stu-id="4ae74-158">Use PowerShell cmdlets to schedule scans</span></span>

<span data-ttu-id="4ae74-159">다음 cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae74-159">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

<span data-ttu-id="4ae74-160">Microsoft Defender 바이러스 백신과 함께 PowerShell을 사용하는 방법에 대한 자세한 내용은 [PowerShell cmdlet을](use-powershell-cmdlets-microsoft-defender-antivirus.md) 사용하여 Microsoft Defender 바이러스 백신 및 [Defender cmdlet](/powershell/module/defender/) 구성 및 실행을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4ae74-160">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a><span data-ttu-id="4ae74-161">WMI(Windows Management Instruction)를 사용하여 검사 예약</span><span class="sxs-lookup"><span data-stu-id="4ae74-161">Use Windows Management Instruction (WMI) to schedule scans</span></span>

<span data-ttu-id="4ae74-162">다음 [  속성에 MSFT_MpPreference  ](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) 클래스의 Set 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae74-162">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

<span data-ttu-id="4ae74-163">자세한 정보 및 허용되는 매개 변수는 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4ae74-163">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="4ae74-164">Windows Defender WMIv2 API</span><span class="sxs-lookup"><span data-stu-id="4ae74-164">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)




## <a name="start-scheduled-scans-only-when-the-endpoint-is-not-in-use"></a><span data-ttu-id="4ae74-165">끝점이 사용되지 않는 경우만 예약된 검사 시작</span><span class="sxs-lookup"><span data-stu-id="4ae74-165">Start scheduled scans only when the endpoint is not in use</span></span>

<span data-ttu-id="4ae74-166">끝점이 켜져 있지만 그룹 정책, PowerShell 또는 WMI와 함께 사용되지 않는 경우 예약된 검색이 발생하게 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ae74-166">You can set the scheduled scan to only occur when the endpoint is turned on but not in use with Group Policy, PowerShell, or WMI.</span></span>

> [!NOTE]
> <span data-ttu-id="4ae74-167">이러한 검사는 CPU 스로틀 구성을 적용하지 않을 것이고 가능한 한 빨리 검색을 완료하는 데 사용할 수 있는 리소스를 최대한 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae74-167">These scans will not honor the CPU throttling configuration and take full advantage of the resources available to complete the scan as fast as possible.</span></span>

### <a name="use-group-policy-to-schedule-scans"></a><span data-ttu-id="4ae74-168">그룹 정책을 사용하여 검사 예약</span><span class="sxs-lookup"><span data-stu-id="4ae74-168">Use Group Policy to schedule scans</span></span>

|<span data-ttu-id="4ae74-169">위치</span><span class="sxs-lookup"><span data-stu-id="4ae74-169">Location</span></span> | <span data-ttu-id="4ae74-170">설정</span><span class="sxs-lookup"><span data-stu-id="4ae74-170">Setting</span></span> | <span data-ttu-id="4ae74-171">설명</span><span class="sxs-lookup"><span data-stu-id="4ae74-171">Description</span></span> | <span data-ttu-id="4ae74-172">기본 설정(구성되지 않은 경우)</span><span class="sxs-lookup"><span data-stu-id="4ae74-172">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="4ae74-173">검사</span><span class="sxs-lookup"><span data-stu-id="4ae74-173">Scan</span></span> | <span data-ttu-id="4ae74-174">컴퓨터가 사용 중이지만 사용 중이 아닌 경우만 예약된 검사 시작</span><span class="sxs-lookup"><span data-stu-id="4ae74-174">Start the scheduled scan only when computer is on but not in use</span></span> | <span data-ttu-id="4ae74-175">컴퓨터가 설정되지만 사용되지 않는 한 예약된 검사는 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ae74-175">Scheduled scans will not run, unless the computer is on but not in use</span></span> | <span data-ttu-id="4ae74-176">사용</span><span class="sxs-lookup"><span data-stu-id="4ae74-176">Enabled</span></span> |

### <a name="use-powershell-cmdlets"></a><span data-ttu-id="4ae74-177">PowerShell cmdlet 사용</span><span class="sxs-lookup"><span data-stu-id="4ae74-177">Use PowerShell cmdlets</span></span>

<span data-ttu-id="4ae74-178">다음 cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae74-178">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

<span data-ttu-id="4ae74-179">Microsoft Defender 바이러스 백신과 함께 PowerShell을 사용하는 방법에 대한 자세한 내용은 [PowerShell cmdlet을](use-powershell-cmdlets-microsoft-defender-antivirus.md) 사용하여 Microsoft Defender 바이러스 백신 및 [Defender cmdlet](/powershell/module/defender/) 구성 및 실행을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4ae74-179">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi"></a><span data-ttu-id="4ae74-180">WMI(Windows Management Instruction) 사용</span><span class="sxs-lookup"><span data-stu-id="4ae74-180">Use Windows Management Instruction (WMI)</span></span>

<span data-ttu-id="4ae74-181">다음 [  속성에 MSFT_MpPreference  ](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) 클래스의 Set 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae74-181">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanOnlyIfIdleEnabled
```

<span data-ttu-id="4ae74-182">자세한 정보 및 허용되는 매개 변수는 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4ae74-182">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="4ae74-183">Windows Defender WMIv2 API</span><span class="sxs-lookup"><span data-stu-id="4ae74-183">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

<a id="remed"></a>
## <a name="configure-when-full-scans-should-be-run-to-complete-remediation"></a><span data-ttu-id="4ae74-184">재구성 완료를 위해 전체 검사 실행 시 구성</span><span class="sxs-lookup"><span data-stu-id="4ae74-184">Configure when full scans should be run to complete remediation</span></span>

<span data-ttu-id="4ae74-185">일부 위협은 제거 및 수정을 완료하기 위해 전체 검사가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ae74-185">Some threats may require a full scan to complete their removal and remediation.</span></span> <span data-ttu-id="4ae74-186">그룹 정책, PowerShell 또는 WMI에서 이러한 검사가 실행되는 경우를 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ae74-186">You can schedule when these scans should occur with Group Policy, PowerShell, or WMI.</span></span>

### <a name="use-group-policy-to-schedule-remediation-required-scans"></a><span data-ttu-id="4ae74-187">그룹 정책을 사용하여 재구성 필요 검사 예약</span><span class="sxs-lookup"><span data-stu-id="4ae74-187">Use Group Policy to schedule remediation-required scans</span></span>

| <span data-ttu-id="4ae74-188">위치</span><span class="sxs-lookup"><span data-stu-id="4ae74-188">Location</span></span> | <span data-ttu-id="4ae74-189">설정</span><span class="sxs-lookup"><span data-stu-id="4ae74-189">Setting</span></span> | <span data-ttu-id="4ae74-190">설명</span><span class="sxs-lookup"><span data-stu-id="4ae74-190">Description</span></span> | <span data-ttu-id="4ae74-191">기본 설정(구성되지 않은 경우)</span><span class="sxs-lookup"><span data-stu-id="4ae74-191">Default setting (if not configured)</span></span> |
|---|---|---|---|
|<span data-ttu-id="4ae74-192">수정</span><span class="sxs-lookup"><span data-stu-id="4ae74-192">Remediation</span></span> | <span data-ttu-id="4ae74-193">재구성 완료를 위해 예약된 전체 검사 실행을 위해 주중 날짜 지정</span><span class="sxs-lookup"><span data-stu-id="4ae74-193">Specify the day of the week to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="4ae74-194">검색을 실행할 날짜를 지정하거나 지정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ae74-194">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="4ae74-195">없음</span><span class="sxs-lookup"><span data-stu-id="4ae74-195">Never</span></span> |
|<span data-ttu-id="4ae74-196">수정</span><span class="sxs-lookup"><span data-stu-id="4ae74-196">Remediation</span></span> | <span data-ttu-id="4ae74-197">재구성 완료를 위해 예약된 전체 검사 실행 시간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae74-197">Specify the time of day to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="4ae74-198">자정 이후의 시간(분)을 지정합니다(예: **60** :a.m.)</span><span class="sxs-lookup"><span data-stu-id="4ae74-198">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="4ae74-199">2:a.m.</span><span class="sxs-lookup"><span data-stu-id="4ae74-199">2 a.m.</span></span> |

### <a name="use-powershell-cmdlets"></a><span data-ttu-id="4ae74-200">PowerShell cmdlet 사용</span><span class="sxs-lookup"><span data-stu-id="4ae74-200">Use PowerShell cmdlets</span></span>

<span data-ttu-id="4ae74-201">다음 cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae74-201">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

<span data-ttu-id="4ae74-202">Microsoft Defender 바이러스 백신과 함께 PowerShell을 사용하는 방법에 대한 자세한 내용은 [PowerShell cmdlet을](use-powershell-cmdlets-microsoft-defender-antivirus.md) 사용하여 Microsoft Defender 바이러스 백신 및 [Defender cmdlet](/powershell/module/defender/) 구성 및 실행을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4ae74-202">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi"></a><span data-ttu-id="4ae74-203">WMI(Windows Management Instruction) 사용</span><span class="sxs-lookup"><span data-stu-id="4ae74-203">Use Windows Management Instruction (WMI)</span></span>

<span data-ttu-id="4ae74-204">다음 [  속성에 MSFT_MpPreference  ](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) 클래스의 Set 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae74-204">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

<span data-ttu-id="4ae74-205">자세한 정보 및 허용되는 매개 변수는 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4ae74-205">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="4ae74-206">Windows Defender WMIv2 API</span><span class="sxs-lookup"><span data-stu-id="4ae74-206">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)




## <a name="set-up-daily-quick-scans"></a><span data-ttu-id="4ae74-207">매일 빠른 검사 설정</span><span class="sxs-lookup"><span data-stu-id="4ae74-207">Set up daily quick scans</span></span>

<span data-ttu-id="4ae74-208">그룹 정책, PowerShell 또는 WMI를 사용하여 예약된 다른 검사 외에 실행할 수 있는 매일 빠른 검색을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ae74-208">You can enable a daily quick scan that can be run in addition to your other scheduled scans with Group Policy, PowerShell, or WMI.</span></span>


### <a name="use-group-policy-to-schedule-daily-scans"></a><span data-ttu-id="4ae74-209">그룹 정책을 사용하여 일별 검사 예약</span><span class="sxs-lookup"><span data-stu-id="4ae74-209">Use Group Policy to schedule daily scans</span></span>


|<span data-ttu-id="4ae74-210">위치</span><span class="sxs-lookup"><span data-stu-id="4ae74-210">Location</span></span> | <span data-ttu-id="4ae74-211">설정</span><span class="sxs-lookup"><span data-stu-id="4ae74-211">Setting</span></span> | <span data-ttu-id="4ae74-212">설명</span><span class="sxs-lookup"><span data-stu-id="4ae74-212">Description</span></span> | <span data-ttu-id="4ae74-213">기본 설정(구성되지 않은 경우)</span><span class="sxs-lookup"><span data-stu-id="4ae74-213">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="4ae74-214">검사</span><span class="sxs-lookup"><span data-stu-id="4ae74-214">Scan</span></span> | <span data-ttu-id="4ae74-215">매일 빠른 검색을 실행할 간격 지정</span><span class="sxs-lookup"><span data-stu-id="4ae74-215">Specify the interval to run quick scans per day</span></span> | <span data-ttu-id="4ae74-216">다음 빠른 검사 전에 경과해야 하는 시간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae74-216">Specify how many hours should elapse before the next quick scan.</span></span> <span data-ttu-id="4ae74-217">예를 들어 2시간마다 실행을 위해 **2를** 입력하고, 하루 한 번씩 **24를 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ae74-217">For example, to run every two hours, enter **2**, for once a day, enter **24**.</span></span> <span data-ttu-id="4ae74-218">**0을 입력하여** 매일 빠른 검색을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ae74-218">Enter **0** to never run a daily quick scan.</span></span> | <span data-ttu-id="4ae74-219">없음</span><span class="sxs-lookup"><span data-stu-id="4ae74-219">Never</span></span> |
|<span data-ttu-id="4ae74-220">검사</span><span class="sxs-lookup"><span data-stu-id="4ae74-220">Scan</span></span> | <span data-ttu-id="4ae74-221">매일 빠른 검사에 대한 시간 지정</span><span class="sxs-lookup"><span data-stu-id="4ae74-221">Specify the time for a daily quick scan</span></span> | <span data-ttu-id="4ae74-222">자정 이후의 시간(분)을 지정합니다(예: **60** :a.m.)</span><span class="sxs-lookup"><span data-stu-id="4ae74-222">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="4ae74-223">2:a.m.</span><span class="sxs-lookup"><span data-stu-id="4ae74-223">2 a.m.</span></span> |

### <a name="use-powershell-cmdlets-to-schedule-daily-scans"></a><span data-ttu-id="4ae74-224">PowerShell cmdlet을 사용하여 일일 검사 예약</span><span class="sxs-lookup"><span data-stu-id="4ae74-224">Use PowerShell cmdlets to schedule daily scans</span></span>

<span data-ttu-id="4ae74-225">다음 cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae74-225">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

<span data-ttu-id="4ae74-226">Microsoft Defender 바이러스 백신과 함께 PowerShell을 사용하는 방법에 대한 자세한 내용은 [PowerShell cmdlet을](use-powershell-cmdlets-microsoft-defender-antivirus.md) 사용하여 Microsoft Defender 바이러스 백신 및 [Defender cmdlet](/powershell/module/defender/) 구성 및 실행을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4ae74-226">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-schedule-daily-scans"></a><span data-ttu-id="4ae74-227">WMI(Windows Management Instruction)를 사용하여 일일 검사 예약</span><span class="sxs-lookup"><span data-stu-id="4ae74-227">Use Windows Management Instruction (WMI) to schedule daily scans</span></span>

<span data-ttu-id="4ae74-228">다음 [  속성에 MSFT_MpPreference  ](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) 클래스의 Set 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae74-228">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanScheduleQuickScanTime
```

<span data-ttu-id="4ae74-229">자세한 정보 및 허용되는 매개 변수는 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4ae74-229">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="4ae74-230">Windows Defender WMIv2 API</span><span class="sxs-lookup"><span data-stu-id="4ae74-230">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="enable-scans-after-protection-updates"></a><span data-ttu-id="4ae74-231">보호 업데이트 후 검사 사용</span><span class="sxs-lookup"><span data-stu-id="4ae74-231">Enable scans after protection updates</span></span>

<span data-ttu-id="4ae74-232">그룹 정책을 사용하여 보호를 업데이트할 때마다 검사가 [강제로](manage-protection-updates-microsoft-defender-antivirus.md) 실행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ae74-232">You can force a scan to occur after every [protection update](manage-protection-updates-microsoft-defender-antivirus.md) with Group Policy.</span></span>

### <a name="use-group-policy-to-schedule-scans-after-protection-updates"></a><span data-ttu-id="4ae74-233">그룹 정책을 사용하여 보호 업데이트 후 검사 예약</span><span class="sxs-lookup"><span data-stu-id="4ae74-233">Use Group Policy to schedule scans after protection updates</span></span>

|<span data-ttu-id="4ae74-234">위치</span><span class="sxs-lookup"><span data-stu-id="4ae74-234">Location</span></span> | <span data-ttu-id="4ae74-235">설정</span><span class="sxs-lookup"><span data-stu-id="4ae74-235">Setting</span></span> | <span data-ttu-id="4ae74-236">설명</span><span class="sxs-lookup"><span data-stu-id="4ae74-236">Description</span></span> | <span data-ttu-id="4ae74-237">기본 설정(구성되지 않은 경우)</span><span class="sxs-lookup"><span data-stu-id="4ae74-237">Default setting (if not configured)</span></span>|
|:---|:---|:---|:---|
|<span data-ttu-id="4ae74-238">서명 업데이트</span><span class="sxs-lookup"><span data-stu-id="4ae74-238">Signature updates</span></span> | <span data-ttu-id="4ae74-239">보안 인텔리전스 업데이트 후 검사 켜기</span><span class="sxs-lookup"><span data-stu-id="4ae74-239">Turn on scan after Security intelligence update</span></span> | <span data-ttu-id="4ae74-240">검사는 새 보호 업데이트가 다운로드된 직후에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae74-240">A scan will occur immediately after a new protection update is downloaded</span></span> | <span data-ttu-id="4ae74-241">사용</span><span class="sxs-lookup"><span data-stu-id="4ae74-241">Enabled</span></span> |

## <a name="see-also"></a><span data-ttu-id="4ae74-242">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4ae74-242">See also</span></span>
- [<span data-ttu-id="4ae74-243">사용자가 정책 설정을 로컬로 수정하지 못하도록 차단 또는 허용</span><span class="sxs-lookup"><span data-stu-id="4ae74-243">Prevent or allow users to locally modify policy settings</span></span>](configure-local-policy-overrides-microsoft-defender-antivirus.md)
- [<span data-ttu-id="4ae74-244">Microsoft Defender 바이러스 백신 검사 구성 및 실행</span><span class="sxs-lookup"><span data-stu-id="4ae74-244">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>](run-scan-microsoft-defender-antivirus.md)
- [<span data-ttu-id="4ae74-245">Microsoft Defender 바이러스 백신 검사 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="4ae74-245">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [<span data-ttu-id="4ae74-246">Microsoft Defender 바이러스 백신 업데이트 관리 및 기준 적용</span><span class="sxs-lookup"><span data-stu-id="4ae74-246">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="4ae74-247">보호 업데이트를 다운로드하고 적용해야 하는 경우 관리</span><span class="sxs-lookup"><span data-stu-id="4ae74-247">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) 
- [<span data-ttu-id="4ae74-248">Windows 10의 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="4ae74-248">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)