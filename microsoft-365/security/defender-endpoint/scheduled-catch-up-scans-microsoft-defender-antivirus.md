---
title: 정기적인 빠른 검사 및 전체 검사 Microsoft Defender 바이러스 백신
description: 실행해야 하는 시간 및 전체 검사 또는 빠른 검사로 실행 여부를 포함하여 재발(예약된) 검사 설정
keywords: 빠른 검사, 전체 검사, 빠른 대 전체, 검사 예약, 매일, 매주, 시간, 예약, 정기적인
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/04/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: f1344026878b7fbd6242d82b1afb0e6671c32073
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789271"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a><span data-ttu-id="81f85-104">예약된 빠른 또는 전체 Microsoft Defender 바이러스 백신 검사 구성</span><span class="sxs-lookup"><span data-stu-id="81f85-104">Configure scheduled quick or full Microsoft Defender Antivirus scans</span></span>

<span data-ttu-id="81f85-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="81f85-105">**Applies to:**</span></span>

- [<span data-ttu-id="81f85-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="81f85-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)


> [!NOTE]
> <span data-ttu-id="81f85-107">기본적으로 Microsoft Defender 바이러스 백신 검사 시간이 15분 전에 업데이트를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-107">By default, Microsoft Defender Antivirus checks for an update 15 minutes before the time of any scheduled scans.</span></span> <span data-ttu-id="81f85-108">이 [기본값을](manage-protection-update-schedule-microsoft-defender-antivirus.md) 다시 설정하기 위해 보호 업데이트를 다운로드하고 적용해야 하는 일정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-108">You can [Manage the schedule for when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) to override this default.</span></span> 

<span data-ttu-id="81f85-109">항상 실시간 보호 및 필요한 경우 [](run-scan-microsoft-defender-antivirus.md) 검사뿐만 아니라 정기적인 예약된 검사도 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-109">In addition to always-on real-time protection and [on-demand](run-scan-microsoft-defender-antivirus.md) scans, you can set up regular, scheduled scans.</span></span> 

<span data-ttu-id="81f85-110">검사 유형, 검사 발생 날짜 및 보호 업데이트 후 또는 끝점을 사용 중이면 검사가 실행될지 구성할 수 있습니다. [](manage-protection-updates-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="81f85-110">You can configure the type of scan, when the scan should occur, and if the scan should occur after a [protection update](manage-protection-updates-microsoft-defender-antivirus.md) or if the endpoint is being used.</span></span> <span data-ttu-id="81f85-111">수정을 완료하기 위한 특별 검사가 언제 실행될지 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-111">You can also specify when special scans to complete remediation should occur.</span></span>

<span data-ttu-id="81f85-112">이 문서에서는 그룹 정책, PowerShell cmdlet 및 WMI를 사용하여 예약된 검색을 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-112">This article describes how to configure scheduled scans with Group Policy, PowerShell cmdlets, and WMI.</span></span> <span data-ttu-id="81f85-113">또는 에서 일정 검색을 구성할 [수도](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) [Microsoft Endpoint Configuration Manager](/mem/intune/configuration/device-restrictions-windows-10)Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="81f85-113">You can also configure schedules scans with [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) or [Microsoft Intune](/mem/intune/configuration/device-restrictions-windows-10).</span></span>

## <a name="to-configure-the-group-policy-settings-described-in-this-article"></a><span data-ttu-id="81f85-114">이 문서에 설명된 그룹 정책 설정을 구성하려면</span><span class="sxs-lookup"><span data-stu-id="81f85-114">To configure the Group Policy settings described in this article</span></span>

1. <span data-ttu-id="81f85-115">그룹 정책 관리 컴퓨터의 그룹 정책 편집기에서 컴퓨터 구성 관리 템플릿 및 구성 요소 Windows   >    >    >  **검사로**  >  **Microsoft Defender 바이러스 백신 합니다.**</span><span class="sxs-lookup"><span data-stu-id="81f85-115">On your Group Policy management machine, in the Group Policy Editor, go to **Computer configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

2. <span data-ttu-id="81f85-116">구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭한 다음 편집 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="81f85-116">Right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

3. <span data-ttu-id="81f85-117">그룹 정책 개체에 대한 설정을 지정하고 확인 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="81f85-117">Specify settings for the Group Policy Object, and then select **OK**.</span></span> 

4. <span data-ttu-id="81f85-118">구성할 각 설정에 대해 1-4단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-118">Repeat steps 1-4 for each setting you want to configure.</span></span>

5. <span data-ttu-id="81f85-119">일반적으로와 같은 그룹 정책 개체를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-119">Deploy your Group Policy Object as you normally do.</span></span> <span data-ttu-id="81f85-120">그룹 정책 개체에 대한 도움이 필요한 경우 그룹 정책 개체 [만들기를 참조합니다.](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)</span><span class="sxs-lookup"><span data-stu-id="81f85-120">If you need help with Group Policy Objects, see [Create a Group Policy Object](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object).</span></span>

<span data-ttu-id="81f85-121">또한 [보호](manage-protection-update-schedule-microsoft-defender-antivirus.md) 업데이트를 다운로드하여 적용해야 하는 경우 관리 및 사용자가 정책 설정을 로컬로 수정할 수 있도록 허용 안 하도록 허용 항목을 [참조하세요.](configure-local-policy-overrides-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="81f85-121">Also see the [Manage when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) and [Prevent or allow users to locally modify policy settings](configure-local-policy-overrides-microsoft-defender-antivirus.md) topics.</span></span>

## <a name="quick-scan-versus-full-scan-and-custom-scan"></a><span data-ttu-id="81f85-122">빠른 검사와 전체 검사 및 사용자 지정 검사</span><span class="sxs-lookup"><span data-stu-id="81f85-122">Quick scan versus full scan and custom scan</span></span>

<span data-ttu-id="81f85-123">예약된 검색을 설정할 때 검사가 전체 검사인지 아니면 빠른 검사인지를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-123">When you set up scheduled scans, you can set up whether the scan should be a full or quick scan.</span></span>


|<span data-ttu-id="81f85-124">빠른 검사</span><span class="sxs-lookup"><span data-stu-id="81f85-124">Quick scan</span></span>  |<span data-ttu-id="81f85-125">전체 검사</span><span class="sxs-lookup"><span data-stu-id="81f85-125">Full scan</span></span>  | <span data-ttu-id="81f85-126">사용자 지정 검사</span><span class="sxs-lookup"><span data-stu-id="81f85-126">Custom scan</span></span> |
|---------|---------|---------|
|<span data-ttu-id="81f85-127">빠른 검사는 레지스트리 키 및 알려진 시작 폴더와 같이 시스템으로 시작하기 위해 등록된 맬웨어가 있을 수 있는 모든 Windows 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-127">A quick scan looks at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span> <p><span data-ttu-id="81f85-128">대부분의 경우 빠른 검사만으로 충분하며 예약된 검사에 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-128">In most cases, a quick scan is sufficient and is recommended for scheduled scans.</span></span> |<span data-ttu-id="81f85-129">전체 검사는 빠른 검색을 실행하여 시작한 다음 탑재된 모든 고정 디스크 및 이동식/네트워크 드라이브(전체 검사가 구성된 경우)에 대한 파일 검색을 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-129">A full scan starts by running a quick scan and then continues with a sequential file scan of all mounted fixed disks and removable/network drives (if the full scan is configured to do so).</span></span> <p><span data-ttu-id="81f85-130">전체 검사는 검사해야 하는 데이터의 양과 유형에 따라 완료하는 데 몇 시간 또는 며칠이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-130">A full scan can take a few hours or days to complete, depending on the amount and type of data that needs to be scanned.</span></span><p><span data-ttu-id="81f85-131">전체 검사가 완료되면 새로운 보안 인텔리전스를 사용할 수 있으며 새 보안 인텔리전스를 통해 다른 위협이 검색되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-131">When the full scan is complete, new security intelligence is available, and a new scan is required to make sure that no other threats are detected with the new security intelligence.</span></span>   | <span data-ttu-id="81f85-132">사용자 지정 검사는 지정한 파일 및 폴더에서 실행되는 빠른 검사입니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-132">A custom scan is a quick scan that runs on the files and folders you specify.</span></span> <span data-ttu-id="81f85-133">예를 들어 USB 드라이브 또는 장치의 로컬 드라이브에 있는 특정 폴더를 검색하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-133">For example, you can opt to scan a USB drive, or a specific folder on your device's local drive.</span></span> <p> | 

>[!NOTE]
><span data-ttu-id="81f85-134">기본적으로 빠른 검사는 USB 드라이브와 같은 탑재된 이동식 장치에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-134">By default, quick scans run on mounted removable devices, such as USB drives.</span></span>

### <a name="how-do-i-know-which-scan-type-to-choose"></a><span data-ttu-id="81f85-135">선택할 검사 유형을 어떻게 알 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="81f85-135">How do I know which scan type to choose?</span></span>

<span data-ttu-id="81f85-136">다음 표를 사용하여 검사 유형을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="81f85-136">Use the following table to choose a scan type.</span></span>


|<span data-ttu-id="81f85-137">시나리오</span><span class="sxs-lookup"><span data-stu-id="81f85-137">Scenario</span></span>  |<span data-ttu-id="81f85-138">권장 검사 유형</span><span class="sxs-lookup"><span data-stu-id="81f85-138">Recommended scan type</span></span>  |
|---------|---------|
|<span data-ttu-id="81f85-139">정기적인 예약된 검색을 설정하려는 경우</span><span class="sxs-lookup"><span data-stu-id="81f85-139">You want to set up regular, scheduled scans</span></span>     | <span data-ttu-id="81f85-140">빠른 검사</span><span class="sxs-lookup"><span data-stu-id="81f85-140">Quick scan</span></span> <p><span data-ttu-id="81f85-141">빠른 검사는 디바이스의 프로세스, 메모리, 프로필 및 특정 위치를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-141">A quick scan checks the processes, memory, profiles, and certain locations on the device.</span></span> <span data-ttu-id="81f85-142">빠른 [검사는 항상 실시간](configure-real-time-protection-microsoft-defender-antivirus.md)보호와 결합되어 시스템으로 시작되는 맬웨어와 커널 수준 맬웨어에 대해 강력한 범위를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-142">Combined with [always-on real-time protection](configure-real-time-protection-microsoft-defender-antivirus.md), a quick scan helps provide strong coverage both for malware that starts with the system and kernel-level malware.</span></span> <span data-ttu-id="81f85-143">실시간 보호는 파일을 열고 닫을 때와 사용자가 폴더로 이동할 때마다 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-143">Real-time protection reviews files when they are opened and closed, and whenever a user navigates to a folder.</span></span>         |
|<span data-ttu-id="81f85-144">개별 장치에서 맬웨어와 같은 위협이 감지됩니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-144">Threats, such as malware, are detected on an individual device</span></span>     | <span data-ttu-id="81f85-145">빠른 검사</span><span class="sxs-lookup"><span data-stu-id="81f85-145">Quick scan</span></span> <p><span data-ttu-id="81f85-146">대부분의 경우 빠른 검사는 검색된 맬웨어를 catch하고 정리합니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-146">In most cases, a quick scan will catch and clean up detected malware.</span></span>   |
|<span data-ttu-id="81f85-147">필요한 경우 검색을 [실행하려는 경우](run-scan-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="81f85-147">You want to run an [on-demand scan](run-scan-microsoft-defender-antivirus.md)</span></span>     | <span data-ttu-id="81f85-148">빠른 검사</span><span class="sxs-lookup"><span data-stu-id="81f85-148">Quick scan</span></span>       |
| <span data-ttu-id="81f85-149">USB 드라이브와 같은 휴대용 장치에 맬웨어가 포함되어 있지 않은지 확인하려는 경우</span><span class="sxs-lookup"><span data-stu-id="81f85-149">You want to make sure a portable device, such as a USB drive, does not contain malware</span></span> | <span data-ttu-id="81f85-150">사용자 지정 검사</span><span class="sxs-lookup"><span data-stu-id="81f85-150">Custom scan</span></span> <p><span data-ttu-id="81f85-151">사용자 지정 검색을 사용하면 특정 위치, 폴더 또는 파일을 선택하고 빠른 검색을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-151">A custom scan enables you to select specific locations, folders, or files and runs a quick scan.</span></span> |

### <a name="what-else-do-i-need-to-know-about-quick-and-full-scans"></a><span data-ttu-id="81f85-152">빠른 검사 및 전체 검사에 대해 알아야 할 다른 것은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="81f85-152">What else do I need to know about quick and full scans?</span></span>

- <span data-ttu-id="81f85-153">악성 파일은 빠른 검사에 포함되지 않은 위치에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-153">Malicious files can be stored in locations that are not included in a quick scan.</span></span> <span data-ttu-id="81f85-154">그러나 항상 실시간 보호는 열고 닫힌 모든 파일과 사용자가 액세스한 폴더에 있는 모든 파일을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-154">However, always-on real-time protection reviews all files that are opened and closed, and any files that are in folders that are accessed by a user.</span></span> <span data-ttu-id="81f85-155">실시간 보호와 빠른 검사의 조합은 맬웨어에 대한 강력한 보호를 제공하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-155">The combination of real-time protection and a quick scan helps provide strong protection against malware.</span></span>

- <span data-ttu-id="81f85-156">클라우드 제공 보호를 통해 액세스 보호 기능을 사용하면 시스템에서 액세스하는 모든 파일이 최신 보안 인텔리전스 및 클라우드 기계 학습 모델을 통해 스캔되도록 할 수 있습니다. [](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="81f85-156">On-access protection with [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) helps ensure that all the files accessed on the system are being scanned with the latest security intelligence and cloud machine learning models.</span></span>

- <span data-ttu-id="81f85-157">실시간 보호가 맬웨어를 감지하고 영향을 받는 파일의 범위가 처음에 결정되지 않은 경우 Microsoft Defender 바이러스 백신 프로세스의 일부로 전체 검사가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-157">When real-time protection detects malware and the extent of the affected files is not determined initially, Microsoft Defender Antivirus initiates a full scan as part of the remediation process.</span></span>

- <span data-ttu-id="81f85-158">전체 검사는 빠른 검사와 같은 다른 검사에서 검색되지 않은 악성 파일을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-158">A full scan can detect malicious files that were not detected by other scans, such as a quick scan.</span></span> <span data-ttu-id="81f85-159">그러나 전체 검사는 시간이 걸릴 수 있으며 중요한 시스템 리소스를 사용하여 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-159">However, a full scan can take a while and use valuable system resources to complete.</span></span>

- <span data-ttu-id="81f85-160">장치가 오랜 시간 동안 오프라인 상태인 경우 전체 검사가 완료되는 데 더 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-160">If a device is offline for an extended period of time, a full scan can take longer to complete.</span></span> 

## <a name="set-up-scheduled-scans"></a><span data-ttu-id="81f85-161">예약된 검사 설정</span><span class="sxs-lookup"><span data-stu-id="81f85-161">Set up scheduled scans</span></span>

<span data-ttu-id="81f85-162">예약된 검사는 지정한 날짜 및 시간으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-162">Scheduled scans run on the day and time that you specify.</span></span> <span data-ttu-id="81f85-163">그룹 정책, PowerShell 및 WMI를 사용하여 예약된 검색을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-163">You can use Group Policy, PowerShell, and WMI to configure scheduled scans.</span></span>

> [!NOTE]
> <span data-ttu-id="81f85-164">예약된 전체 검사 중에 디바이스의 연결이 풀리며 배터리에서 실행되는 경우 예약된 검사는 완료 전에 스캔이 중지된 이벤트 1002와 함께 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-164">If a device is unplugged and running on battery during a scheduled full scan, the scheduled scan will stop with event 1002, which states that the scan stopped before completion.</span></span> <span data-ttu-id="81f85-165">Microsoft Defender 바이러스 백신 예약된 다음에 전체 검사가 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-165">Microsoft Defender Antivirus will run a full scan at the next scheduled time.</span></span>

### <a name="use-group-policy-to-schedule-scans"></a><span data-ttu-id="81f85-166">그룹 정책을 사용하여 검사 예약</span><span class="sxs-lookup"><span data-stu-id="81f85-166">Use Group Policy to schedule scans</span></span>

|<span data-ttu-id="81f85-167">위치</span><span class="sxs-lookup"><span data-stu-id="81f85-167">Location</span></span> | <span data-ttu-id="81f85-168">설정</span><span class="sxs-lookup"><span data-stu-id="81f85-168">Setting</span></span> | <span data-ttu-id="81f85-169">설명</span><span class="sxs-lookup"><span data-stu-id="81f85-169">Description</span></span> | <span data-ttu-id="81f85-170">기본 설정(구성되지 않은 경우)</span><span class="sxs-lookup"><span data-stu-id="81f85-170">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="81f85-171">검사</span><span class="sxs-lookup"><span data-stu-id="81f85-171">Scan</span></span> | <span data-ttu-id="81f85-172">예약된 검사에 사용할 검사 유형 지정</span><span class="sxs-lookup"><span data-stu-id="81f85-172">Specify the scan type to use for a scheduled scan</span></span> | <span data-ttu-id="81f85-173">빠른 검사</span><span class="sxs-lookup"><span data-stu-id="81f85-173">Quick scan</span></span> |
|<span data-ttu-id="81f85-174">검사</span><span class="sxs-lookup"><span data-stu-id="81f85-174">Scan</span></span> | <span data-ttu-id="81f85-175">예약된 검색을 실행할 날짜 지정</span><span class="sxs-lookup"><span data-stu-id="81f85-175">Specify the day of the week to run a scheduled scan</span></span> | <span data-ttu-id="81f85-176">검색을 실행할 날짜를 지정하거나 지정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-176">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="81f85-177">공개하지 않음</span><span class="sxs-lookup"><span data-stu-id="81f85-177">Never</span></span> |
|<span data-ttu-id="81f85-178">검사</span><span class="sxs-lookup"><span data-stu-id="81f85-178">Scan</span></span> | <span data-ttu-id="81f85-179">예약된 검색을 실행할 시간 지정</span><span class="sxs-lookup"><span data-stu-id="81f85-179">Specify the time of day to run a scheduled scan</span></span> | <span data-ttu-id="81f85-180">자정 이후의 시간(분)을 지정합니다(예: **60** :a.m.).</span><span class="sxs-lookup"><span data-stu-id="81f85-180">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.).</span></span> | <span data-ttu-id="81f85-181">2:a.m.</span><span class="sxs-lookup"><span data-stu-id="81f85-181">2 a.m.</span></span> |
|<span data-ttu-id="81f85-182">루트</span><span class="sxs-lookup"><span data-stu-id="81f85-182">Root</span></span> | <span data-ttu-id="81f85-183">예약된 작업 시간 임의로</span><span class="sxs-lookup"><span data-stu-id="81f85-183">Randomize scheduled task times</span></span> |<span data-ttu-id="81f85-184">이 Microsoft Defender 바이러스 백신 검사 시작 시간을 0시간에서 4시간 사이의 간격으로 임의로 임의로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-184">In Microsoft Defender Antivirus, randomize the start time of the scan to any interval from 0 to 4 hours.</span></span> <p><span data-ttu-id="81f85-185">[SCEP에서](/mem/intune/protect/certificates-scep-configure)임의로 스캔을 30분을 더하거나 30분을 더한 간격으로 임의로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-185">In [SCEP](/mem/intune/protect/certificates-scep-configure), randomize scans to any interval plus or minus 30 minutes.</span></span> <span data-ttu-id="81f85-186">이는 가상 컴퓨터 또는 VDI 배포에서 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-186">This can be useful in virtual machines or VDI deployments.</span></span> | <span data-ttu-id="81f85-187">사용</span><span class="sxs-lookup"><span data-stu-id="81f85-187">Enabled</span></span> |


### <a name="use-powershell-cmdlets-to-schedule-scans"></a><span data-ttu-id="81f85-188">PowerShell cmdlet을 사용하여 검사 예약</span><span class="sxs-lookup"><span data-stu-id="81f85-188">Use PowerShell cmdlets to schedule scans</span></span>

<span data-ttu-id="81f85-189">다음 cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-189">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

<span data-ttu-id="81f85-190">자세한 내용은 [PowerShell cmdlet을](use-powershell-cmdlets-microsoft-defender-antivirus.md) 사용하여 구성 및 Microsoft Defender 바이러스 백신 및 [Defender cmdlet을](/powershell/module/defender/) 사용하여 PowerShell을 사용하는 방법에 대한 자세한 Microsoft Defender 바이러스 백신.</span><span class="sxs-lookup"><span data-stu-id="81f85-190">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a><span data-ttu-id="81f85-191">WMI(Windows 관리 명령)를 사용하여 검사 예약</span><span class="sxs-lookup"><span data-stu-id="81f85-191">Use Windows Management Instruction (WMI) to schedule scans</span></span>

<span data-ttu-id="81f85-192">다음 [  속성에 MSFT_MpPreference  ](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) 클래스의 Set 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-192">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

<span data-ttu-id="81f85-193">자세한 내용은 [WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) API Windows Defender 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="81f85-193">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>


## <a name="start-scheduled-scans-only-when-the-endpoint-is-not-in-use"></a><span data-ttu-id="81f85-194">끝점이 사용되지 않는 경우만 예약된 검사 시작</span><span class="sxs-lookup"><span data-stu-id="81f85-194">Start scheduled scans only when the endpoint is not in use</span></span>

<span data-ttu-id="81f85-195">끝점이 켜져 있지만 그룹 정책, PowerShell 또는 WMI와 함께 사용되지 않는 경우 예약된 검색이 발생하게 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-195">You can set the scheduled scan to only occur when the endpoint is turned on but not in use with Group Policy, PowerShell, or WMI.</span></span>

> [!NOTE]
> <span data-ttu-id="81f85-196">이러한 검사는 CPU 스로틀 구성을 적용하지 않을 것이고 가능한 한 빨리 검색을 완료하는 데 사용할 수 있는 리소스를 최대한 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-196">These scans will not honor the CPU throttling configuration and take full advantage of the resources available to complete the scan as fast as possible.</span></span>

### <a name="use-group-policy-to-schedule-scans"></a><span data-ttu-id="81f85-197">그룹 정책을 사용하여 검사 예약</span><span class="sxs-lookup"><span data-stu-id="81f85-197">Use Group Policy to schedule scans</span></span>

|<span data-ttu-id="81f85-198">위치</span><span class="sxs-lookup"><span data-stu-id="81f85-198">Location</span></span> | <span data-ttu-id="81f85-199">설정</span><span class="sxs-lookup"><span data-stu-id="81f85-199">Setting</span></span> | <span data-ttu-id="81f85-200">설명</span><span class="sxs-lookup"><span data-stu-id="81f85-200">Description</span></span> | <span data-ttu-id="81f85-201">기본 설정(구성되지 않은 경우)</span><span class="sxs-lookup"><span data-stu-id="81f85-201">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="81f85-202">검사</span><span class="sxs-lookup"><span data-stu-id="81f85-202">Scan</span></span> | <span data-ttu-id="81f85-203">컴퓨터가 사용 중이지만 사용 중이 아닌 경우만 예약된 검사 시작</span><span class="sxs-lookup"><span data-stu-id="81f85-203">Start the scheduled scan only when computer is on but not in use</span></span> | <span data-ttu-id="81f85-204">컴퓨터가 설정되지만 사용되지 않는 한 예약된 검사는 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-204">Scheduled scans will not run, unless the computer is on but not in use</span></span> | <span data-ttu-id="81f85-205">사용</span><span class="sxs-lookup"><span data-stu-id="81f85-205">Enabled</span></span> |

### <a name="use-powershell-cmdlets"></a><span data-ttu-id="81f85-206">PowerShell cmdlet 사용</span><span class="sxs-lookup"><span data-stu-id="81f85-206">Use PowerShell cmdlets</span></span>

<span data-ttu-id="81f85-207">다음 cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-207">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

<span data-ttu-id="81f85-208">자세한 내용은 [PowerShell cmdlet을 사용하여 Microsoft Defender 바이러스 백신 구성 및 실행](use-powershell-cmdlets-microsoft-defender-antivirus.md)과 [Defender cmdlet](/powershell/module/defender/)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="81f85-208">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

### <a name="use-windows-management-instruction-wmi"></a><span data-ttu-id="81f85-209">WMI(Windows 관리 명령) 사용</span><span class="sxs-lookup"><span data-stu-id="81f85-209">Use Windows Management Instruction (WMI)</span></span>

<span data-ttu-id="81f85-210">다음 [  속성에 MSFT_MpPreference  ](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) 클래스의 Set 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-210">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanOnlyIfIdleEnabled
```

<span data-ttu-id="81f85-211">API 및 허용되는 매개 변수에 대한 자세한 내용은 [WMIv2 api Windows Defender 참조하세요.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="81f85-211">For more information about APIs and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

<a id="remed"></a>
## <a name="configure-when-full-scans-should-be-run-to-complete-remediation"></a><span data-ttu-id="81f85-212">재구성 완료를 위해 전체 검사 실행 시 구성</span><span class="sxs-lookup"><span data-stu-id="81f85-212">Configure when full scans should be run to complete remediation</span></span>

<span data-ttu-id="81f85-213">일부 위협은 제거 및 수정을 완료하기 위해 전체 검사가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-213">Some threats might require a full scan to complete their removal and remediation.</span></span> <span data-ttu-id="81f85-214">그룹 정책, PowerShell 또는 WMI에서 이러한 검사가 언제 발생해야 하는지 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-214">You can specify when these scans should occur with Group Policy, PowerShell, or WMI.</span></span>

### <a name="use-group-policy-to-schedule-remediation-required-scans"></a><span data-ttu-id="81f85-215">그룹 정책을 사용하여 재구성 필요 검사 예약</span><span class="sxs-lookup"><span data-stu-id="81f85-215">Use Group Policy to schedule remediation-required scans</span></span>

| <span data-ttu-id="81f85-216">위치</span><span class="sxs-lookup"><span data-stu-id="81f85-216">Location</span></span> | <span data-ttu-id="81f85-217">설정</span><span class="sxs-lookup"><span data-stu-id="81f85-217">Setting</span></span> | <span data-ttu-id="81f85-218">설명</span><span class="sxs-lookup"><span data-stu-id="81f85-218">Description</span></span> | <span data-ttu-id="81f85-219">기본 설정(구성되지 않은 경우)</span><span class="sxs-lookup"><span data-stu-id="81f85-219">Default setting (if not configured)</span></span> |
|---|---|---|---|
|<span data-ttu-id="81f85-220">수정</span><span class="sxs-lookup"><span data-stu-id="81f85-220">Remediation</span></span> | <span data-ttu-id="81f85-221">재구성 완료를 위해 예약된 전체 검사 실행을 위해 주중 날짜 지정</span><span class="sxs-lookup"><span data-stu-id="81f85-221">Specify the day of the week to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="81f85-222">검색을 실행할 날짜를 지정하거나 지정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-222">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="81f85-223">공개하지 않음</span><span class="sxs-lookup"><span data-stu-id="81f85-223">Never</span></span> |
|<span data-ttu-id="81f85-224">수정</span><span class="sxs-lookup"><span data-stu-id="81f85-224">Remediation</span></span> | <span data-ttu-id="81f85-225">재구성 완료를 위해 예약된 전체 검사 실행 시간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-225">Specify the time of day to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="81f85-226">자정 이후의 시간(분)을 지정합니다(예: **60** :a.m.)</span><span class="sxs-lookup"><span data-stu-id="81f85-226">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="81f85-227">2:a.m.</span><span class="sxs-lookup"><span data-stu-id="81f85-227">2 a.m.</span></span> |

### <a name="use-powershell-cmdlets"></a><span data-ttu-id="81f85-228">PowerShell cmdlet 사용</span><span class="sxs-lookup"><span data-stu-id="81f85-228">Use PowerShell cmdlets</span></span>

<span data-ttu-id="81f85-229">다음 cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-229">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

<span data-ttu-id="81f85-230">PowerShell과 함께 PowerShell을 사용하는 방법에 대한 자세한 내용은 [PowerShell cmdlet을](use-powershell-cmdlets-microsoft-defender-antivirus.md) 사용하여 Microsoft Defender 바이러스 백신 및 [Defender cmdlet을](/powershell/module/defender/) 구성하고 실행을 Microsoft Defender 바이러스 백신.</span><span class="sxs-lookup"><span data-stu-id="81f85-230">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi"></a><span data-ttu-id="81f85-231">WMI(Windows 관리 명령) 사용</span><span class="sxs-lookup"><span data-stu-id="81f85-231">Use Windows Management Instruction (WMI)</span></span>

<span data-ttu-id="81f85-232">다음 [  속성에 MSFT_MpPreference  ](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) 클래스의 Set 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-232">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

<span data-ttu-id="81f85-233">자세한 정보 및 허용되는 매개 변수는 [WMIv2 api Windows Defender 참조하세요.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="81f85-233">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>


## <a name="set-up-daily-quick-scans"></a><span data-ttu-id="81f85-234">매일 빠른 검사 설정</span><span class="sxs-lookup"><span data-stu-id="81f85-234">Set up daily quick scans</span></span>

<span data-ttu-id="81f85-235">그룹 정책, PowerShell 또는 WMI를 사용하여 예약된 다른 검사 외에 실행할 수 있는 매일 빠른 검색을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-235">You can enable a daily quick scan that can be run in addition to your other scheduled scans with Group Policy, PowerShell, or WMI.</span></span>

### <a name="use-group-policy-to-schedule-daily-scans"></a><span data-ttu-id="81f85-236">그룹 정책을 사용하여 일별 검사 예약</span><span class="sxs-lookup"><span data-stu-id="81f85-236">Use Group Policy to schedule daily scans</span></span>

|<span data-ttu-id="81f85-237">위치</span><span class="sxs-lookup"><span data-stu-id="81f85-237">Location</span></span> | <span data-ttu-id="81f85-238">설정</span><span class="sxs-lookup"><span data-stu-id="81f85-238">Setting</span></span> | <span data-ttu-id="81f85-239">설명</span><span class="sxs-lookup"><span data-stu-id="81f85-239">Description</span></span> | <span data-ttu-id="81f85-240">기본 설정(구성되지 않은 경우)</span><span class="sxs-lookup"><span data-stu-id="81f85-240">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="81f85-241">검사</span><span class="sxs-lookup"><span data-stu-id="81f85-241">Scan</span></span> | <span data-ttu-id="81f85-242">매일 빠른 검색을 실행할 간격 지정</span><span class="sxs-lookup"><span data-stu-id="81f85-242">Specify the interval to run quick scans per day</span></span> | <span data-ttu-id="81f85-243">다음 빠른 검사 전에 경과해야 하는 시간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-243">Specify how many hours should elapse before the next quick scan.</span></span> <span data-ttu-id="81f85-244">예를 들어 2시간마다 실행을 위해 **2를** 입력하고, 하루 한 번씩 **24를 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="81f85-244">For example, to run every two hours, enter **2**, for once a day, enter **24**.</span></span> <span data-ttu-id="81f85-245">**0을 입력하여** 매일 빠른 검색을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-245">Enter **0** to never run a daily quick scan.</span></span> | <span data-ttu-id="81f85-246">공개하지 않음</span><span class="sxs-lookup"><span data-stu-id="81f85-246">Never</span></span> |
|<span data-ttu-id="81f85-247">검사</span><span class="sxs-lookup"><span data-stu-id="81f85-247">Scan</span></span> | <span data-ttu-id="81f85-248">매일 빠른 검사에 대한 시간 지정</span><span class="sxs-lookup"><span data-stu-id="81f85-248">Specify the time for a daily quick scan</span></span> | <span data-ttu-id="81f85-249">자정 이후의 시간(분)을 지정합니다(예: **60** :a.m.)</span><span class="sxs-lookup"><span data-stu-id="81f85-249">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="81f85-250">2:a.m.</span><span class="sxs-lookup"><span data-stu-id="81f85-250">2 a.m.</span></span> |

### <a name="use-powershell-cmdlets-to-schedule-daily-scans"></a><span data-ttu-id="81f85-251">PowerShell cmdlet을 사용하여 일일 검사 예약</span><span class="sxs-lookup"><span data-stu-id="81f85-251">Use PowerShell cmdlets to schedule daily scans</span></span>

<span data-ttu-id="81f85-252">다음 cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-252">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

<span data-ttu-id="81f85-253">PowerShell과 함께 PowerShell을 사용하는 방법에 대한 자세한 Microsoft Defender 바이러스 백신 [PowerShell cmdlet을](use-powershell-cmdlets-microsoft-defender-antivirus.md) 사용하여 Microsoft Defender 바이러스 백신 [및 Defender cmdlet](/powershell/module/defender/)구성 및 실행을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="81f85-253">For more information about how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

### <a name="use-windows-management-instruction-wmi-to-schedule-daily-scans"></a><span data-ttu-id="81f85-254">WMI(Windows Management Instruction)를 사용하여 일별 검사 예약</span><span class="sxs-lookup"><span data-stu-id="81f85-254">Use Windows Management Instruction (WMI) to schedule daily scans</span></span>

<span data-ttu-id="81f85-255">다음 [  속성에 MSFT_MpPreference  ](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) 클래스의 Set 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-255">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanScheduleQuickScanTime
```

<span data-ttu-id="81f85-256">자세한 정보 및 허용되는 매개 변수는 [WMIv2 api Windows Defender 참조하세요.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="81f85-256">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>


## <a name="enable-scans-after-protection-updates"></a><span data-ttu-id="81f85-257">보호 업데이트 후 검사 사용</span><span class="sxs-lookup"><span data-stu-id="81f85-257">Enable scans after protection updates</span></span>

<span data-ttu-id="81f85-258">그룹 정책을 사용하여 보호를 업데이트할 때마다 검사가 [강제로](manage-protection-updates-microsoft-defender-antivirus.md) 실행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-258">You can force a scan to occur after every [protection update](manage-protection-updates-microsoft-defender-antivirus.md) with Group Policy.</span></span>

### <a name="use-group-policy-to-schedule-scans-after-protection-updates"></a><span data-ttu-id="81f85-259">그룹 정책을 사용하여 보호 업데이트 후 검사 예약</span><span class="sxs-lookup"><span data-stu-id="81f85-259">Use Group Policy to schedule scans after protection updates</span></span>

|<span data-ttu-id="81f85-260">위치</span><span class="sxs-lookup"><span data-stu-id="81f85-260">Location</span></span> | <span data-ttu-id="81f85-261">설정</span><span class="sxs-lookup"><span data-stu-id="81f85-261">Setting</span></span> | <span data-ttu-id="81f85-262">설명</span><span class="sxs-lookup"><span data-stu-id="81f85-262">Description</span></span> | <span data-ttu-id="81f85-263">기본 설정(구성되지 않은 경우)</span><span class="sxs-lookup"><span data-stu-id="81f85-263">Default setting (if not configured)</span></span>|
|:---|:---|:---|:---|
|<span data-ttu-id="81f85-264">서명 업데이트</span><span class="sxs-lookup"><span data-stu-id="81f85-264">Signature updates</span></span> | <span data-ttu-id="81f85-265">보안 인텔리전스 업데이트 후 검사 켜기</span><span class="sxs-lookup"><span data-stu-id="81f85-265">Turn on scan after Security intelligence update</span></span> | <span data-ttu-id="81f85-266">검사는 새 보호 업데이트가 다운로드된 직후에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="81f85-266">A scan will occur immediately after a new protection update is downloaded</span></span> | <span data-ttu-id="81f85-267">사용</span><span class="sxs-lookup"><span data-stu-id="81f85-267">Enabled</span></span> |

## <a name="see-also"></a><span data-ttu-id="81f85-268">참고 항목</span><span class="sxs-lookup"><span data-stu-id="81f85-268">See also</span></span>

- [<span data-ttu-id="81f85-269">사용자가 정책 설정을 로컬로 수정하지 못하도록 차단 또는 허용</span><span class="sxs-lookup"><span data-stu-id="81f85-269">Prevent or allow users to locally modify policy settings</span></span>](configure-local-policy-overrides-microsoft-defender-antivirus.md)
- [<span data-ttu-id="81f85-270">요청 기반 Microsoft Defender 바이러스 백신 검사 구성 및 실행</span><span class="sxs-lookup"><span data-stu-id="81f85-270">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>](run-scan-microsoft-defender-antivirus.md)
- [<span data-ttu-id="81f85-271">Microsoft Defender 바이러스 백신 검사 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="81f85-271">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [<span data-ttu-id="81f85-272">업데이트 Microsoft Defender 바이러스 백신 관리하고 기준 적용</span><span class="sxs-lookup"><span data-stu-id="81f85-272">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="81f85-273">보호 업데이트를 다운로드하고 적용해야 하는 경우 관리</span><span class="sxs-lookup"><span data-stu-id="81f85-273">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) 
- [<span data-ttu-id="81f85-274">Windows 10의 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="81f85-274">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)