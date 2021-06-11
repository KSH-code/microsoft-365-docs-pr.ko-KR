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
ms.date: 06/09/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 5566050e4a64713f6f8b4ac2cb4a7188d3a241c8
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879728"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a><span data-ttu-id="754ce-104">예약된 빠른 또는 전체 Microsoft Defender 바이러스 백신 검사 구성</span><span class="sxs-lookup"><span data-stu-id="754ce-104">Configure scheduled quick or full Microsoft Defender Antivirus scans</span></span>

<span data-ttu-id="754ce-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="754ce-105">**Applies to:**</span></span>

- [<span data-ttu-id="754ce-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="754ce-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="754ce-107">실시간 실시간 보호 및 필요한 바이러스 [](run-scan-microsoft-defender-antivirus.md) 백신 검사 외에도 정기적인 예약된 바이러스 백신 검사도 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="754ce-107">In addition to always-on, real-time protection and [on-demand antivirus](run-scan-microsoft-defender-antivirus.md) scans, you can set up regular, scheduled antivirus scans.</span></span> <span data-ttu-id="754ce-108">검사 유형, 검사가 실행되는 경우 및 보호 업데이트 후 또는 [](manage-protection-updates-microsoft-defender-antivirus.md) 끝점이 사용되지 않을 때 검사가 실행될지 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="754ce-108">You can configure the type of scan, when the scan should occur, and if the scan should occur after a [protection update](manage-protection-updates-microsoft-defender-antivirus.md) or when an endpoint is not being used.</span></span> <span data-ttu-id="754ce-109">필요한 경우 재구성 작업을 완료하기 위해 특수 검색을 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="754ce-109">You can also set up special scans to complete remediation actions if needed.</span></span>

## <a name="what-do-you-want-to-do"></a><span data-ttu-id="754ce-110">무슨 작업을 하고 싶으십니까?</span><span class="sxs-lookup"><span data-stu-id="754ce-110">What do you want to do?</span></span>

- [<span data-ttu-id="754ce-111">빠른 검사, 전체 검사 및 사용자 지정 검사에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="754ce-111">Learn about quick scans, full scans, and custom scans</span></span>](#quick-scan-full-scan-and-custom-scan)
- [<span data-ttu-id="754ce-112">그룹 정책을 사용하여 바이러스 백신 검사 예약</span><span class="sxs-lookup"><span data-stu-id="754ce-112">Use Group Policy to schedule antivirus scans</span></span>](schedule-antivirus-scans-group-policy.md)
- [<span data-ttu-id="754ce-113">이 Windows PowerShell 사용하여 바이러스 백신 검사 예약</span><span class="sxs-lookup"><span data-stu-id="754ce-113">Use Windows PowerShell to Schedule antivirus scans</span></span>](schedule-antivirus-scans-powershell.md)
- [<span data-ttu-id="754ce-114">관리 Windows 사용하여 바이러스 백신 검사 예약</span><span class="sxs-lookup"><span data-stu-id="754ce-114">Use Windows Management Instrumentation to schedule antivirus scans</span></span>](schedule-antivirus-scans-wmi.md)

## <a name="keep-the-following-points-in-mind"></a><span data-ttu-id="754ce-115">다음에 유의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="754ce-115">Keep the following points in mind</span></span>

- <span data-ttu-id="754ce-116">기본적으로 Microsoft Defender 바이러스 백신 검사 시간이 15분 전에 업데이트를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="754ce-116">By default, Microsoft Defender Antivirus checks for an update 15 minutes before the time of any scheduled scans.</span></span> <span data-ttu-id="754ce-117">이 [기본값을](manage-protection-update-schedule-microsoft-defender-antivirus.md) 다시 설정하기 위해 보호 업데이트를 다운로드하고 적용해야 하는 일정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="754ce-117">You can [Manage the schedule for when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) to override this default.</span></span> 

- <span data-ttu-id="754ce-118">예약된 전체 검사 중에 디바이스의 연결이 풀리며 배터리에서 실행되는 경우 예약된 검사는 완료 전에 스캔이 중지된 이벤트 1002와 함께 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="754ce-118">If a device is unplugged and running on battery during a scheduled full scan, the scheduled scan will stop with event 1002, which states that the scan stopped before completion.</span></span> <span data-ttu-id="754ce-119">Microsoft Defender 바이러스 백신 예약된 다음에 전체 검사가 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="754ce-119">Microsoft Defender Antivirus will run a full scan at the next scheduled time.</span></span>

## <a name="quick-scan-full-scan-and-custom-scan"></a><span data-ttu-id="754ce-120">빠른 검사, 전체 검사 및 사용자 지정 검사</span><span class="sxs-lookup"><span data-stu-id="754ce-120">Quick scan, full scan, and custom scan</span></span>

<span data-ttu-id="754ce-121">예약된 검색을 설정할 때 검사가 전체 검사인지 아니면 빠른 검사인지를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="754ce-121">When you set up scheduled scans, you can specify whether the scan should be a full or quick scan.</span></span> <span data-ttu-id="754ce-122">대부분의 경우 빠른 검사가 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="754ce-122">In most cases, a quick scan is recommended.</span></span> 

| <span data-ttu-id="754ce-123">빠른 검사</span><span class="sxs-lookup"><span data-stu-id="754ce-123">Quick scan</span></span>  | <span data-ttu-id="754ce-124">전체 검사</span><span class="sxs-lookup"><span data-stu-id="754ce-124">Full scan</span></span>  | <span data-ttu-id="754ce-125">사용자 지정 검사</span><span class="sxs-lookup"><span data-stu-id="754ce-125">Custom scan</span></span> |
|---------|---------|---------|
| <span data-ttu-id="754ce-126">(권장) 빠른 검사는 레지스트리 키 및 알려진 시작 폴더와 같이 시스템으로 시작하기 위해 등록된 맬웨어가 있을 수 있는 모든 Windows 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="754ce-126">(Recommended) A quick scan looks at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span> <p><span data-ttu-id="754ce-127">파일을 열고 닫을 때 그리고 사용자가 폴더를 탐색할 때마다 파일을 검토하는 실시간 보호와 함께 빠른 검사가 시스템 및 커널 수준 맬웨어로 시작되는 맬웨어를 강력한 보호하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="754ce-127">Combined with always-on, real-time protection, which reviews files when they are opened and closed, and whenever a user navigates to a folder, a quick scan helps provide strong protection against malware that starts with the system and kernel-level malware.</span></span> <p><span data-ttu-id="754ce-128">대부분의 경우 빠른 검사만으로 충분하며 예약된 검사에 권장되는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="754ce-128">In most cases, a quick scan is sufficient and is the recommended option for scheduled scans.</span></span> | <span data-ttu-id="754ce-129">전체 검사는 빠른 검색을 실행하여 시작한 다음 탑재된 모든 고정 디스크 및 이동식/네트워크 드라이브(전체 검사가 구성된 경우)에 대한 파일 검색을 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="754ce-129">A full scan starts by running a quick scan and then continues with a sequential file scan of all mounted fixed disks and removable/network drives (if the full scan is configured to do so).</span></span> <p><span data-ttu-id="754ce-130">전체 검사는 검사해야 하는 데이터의 양과 유형에 따라 완료하는 데 몇 시간 또는 며칠이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="754ce-130">A full scan can take a few hours or days to complete, depending on the amount and type of data that needs to be scanned.</span></span><p><span data-ttu-id="754ce-131">전체 검사가 완료되면 새로운 보안 인텔리전스를 사용할 수 있으며 새 보안 인텔리전스를 통해 다른 위협이 검색되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="754ce-131">When the full scan is complete, new security intelligence is available, and a new scan is then required to make sure that no other threats are detected with the new security intelligence.</span></span> <p><span data-ttu-id="754ce-132">전체 검사와 관련된 시간 및 리소스 때문에 일반적으로 Microsoft는 전체 검사의 시간을 정하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="754ce-132">Because of the time and resources involved in a full scan, in general, Microsoft does not recommend scheduling full scans.</span></span>  | <span data-ttu-id="754ce-133">사용자 지정 검사는 지정한 파일 및 폴더에서 실행되는 빠른 검사입니다.</span><span class="sxs-lookup"><span data-stu-id="754ce-133">A custom scan is a quick scan that runs on the files and folders you specify.</span></span> <span data-ttu-id="754ce-134">예를 들어 USB 드라이브 또는 장치의 로컬 드라이브에 있는 특정 폴더를 검색하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="754ce-134">For example, you can opt to scan a USB drive, or a specific folder on your device's local drive.</span></span> <p> | 

> [!NOTE]
> <span data-ttu-id="754ce-135">기본적으로 빠른 검사는 USB 드라이브와 같은 탑재된 이동식 장치에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="754ce-135">By default, quick scans run on mounted removable devices, such as USB drives.</span></span>

## <a name="how-do-i-know-which-scan-type-to-choose"></a><span data-ttu-id="754ce-136">선택할 검사 유형을 어떻게 알 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="754ce-136">How do I know which scan type to choose?</span></span>

<span data-ttu-id="754ce-137">다음 표를 사용하여 검사 유형을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="754ce-137">Use the following table to choose a scan type.</span></span>

| <span data-ttu-id="754ce-138">시나리오</span><span class="sxs-lookup"><span data-stu-id="754ce-138">Scenario</span></span>  | <span data-ttu-id="754ce-139">권장 검사 유형</span><span class="sxs-lookup"><span data-stu-id="754ce-139">Recommended scan type</span></span>  |
|---------|---------|
| <span data-ttu-id="754ce-140">정기적인 예약된 검색을 설정하려는 경우</span><span class="sxs-lookup"><span data-stu-id="754ce-140">You want to set up regular, scheduled scans</span></span>     | <span data-ttu-id="754ce-141">빠른 검사</span><span class="sxs-lookup"><span data-stu-id="754ce-141">Quick scan</span></span> <p><span data-ttu-id="754ce-142">빠른 검사는 디바이스의 프로세스, 메모리, 프로필 및 특정 위치를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="754ce-142">A quick scan checks the processes, memory, profiles, and certain locations on the device.</span></span> <span data-ttu-id="754ce-143">빠른 [검사는 항상 실시간](configure-real-time-protection-microsoft-defender-antivirus.md)보호와 결합되어 시스템으로 시작되는 맬웨어와 커널 수준 맬웨어에 대해 강력한 범위를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="754ce-143">Combined with [always-on real-time protection](configure-real-time-protection-microsoft-defender-antivirus.md), a quick scan helps provide strong coverage both for malware that starts with the system and kernel-level malware.</span></span> <span data-ttu-id="754ce-144">실시간 보호는 파일을 열고 닫을 때와 사용자가 폴더로 이동할 때마다 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="754ce-144">Real-time protection reviews files when they are opened and closed, and whenever a user navigates to a folder.</span></span>         |
| <span data-ttu-id="754ce-145">개별 장치에서 맬웨어와 같은 위협이 감지됩니다.</span><span class="sxs-lookup"><span data-stu-id="754ce-145">Threats, such as malware, are detected on an individual device</span></span>     | <span data-ttu-id="754ce-146">빠른 검사</span><span class="sxs-lookup"><span data-stu-id="754ce-146">Quick scan</span></span> <p><span data-ttu-id="754ce-147">대부분의 경우 빠른 검사는 검색된 맬웨어를 catch하고 정리합니다.</span><span class="sxs-lookup"><span data-stu-id="754ce-147">In most cases, a quick scan will catch and clean up detected malware.</span></span>   |
| <span data-ttu-id="754ce-148">필요한 경우 검색을 [실행하려는 경우](run-scan-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="754ce-148">You want to run an [on-demand scan](run-scan-microsoft-defender-antivirus.md)</span></span>     | <span data-ttu-id="754ce-149">빠른 검사</span><span class="sxs-lookup"><span data-stu-id="754ce-149">Quick scan</span></span>       |
| <span data-ttu-id="754ce-150">USB 드라이브와 같은 휴대용 장치에 맬웨어가 포함되어 있지 않은지 확인하려는 경우</span><span class="sxs-lookup"><span data-stu-id="754ce-150">You want to make sure a portable device, such as a USB drive, does not contain malware</span></span> | <span data-ttu-id="754ce-151">사용자 지정 검사</span><span class="sxs-lookup"><span data-stu-id="754ce-151">Custom scan</span></span> <p><span data-ttu-id="754ce-152">사용자 지정 검색을 사용하면 특정 위치, 폴더 또는 파일을 선택하고 빠른 검색을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="754ce-152">A custom scan enables you to select specific locations, folders, or files, and runs a quick scan.</span></span> |

## <a name="what-else-do-i-need-to-know-about-quick-and-full-scans"></a><span data-ttu-id="754ce-153">빠른 검사 및 전체 검사에 대해 알아야 할 다른 것은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="754ce-153">What else do I need to know about quick and full scans?</span></span>

- <span data-ttu-id="754ce-154">악성 파일은 빠른 검사에 포함되지 않은 위치에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="754ce-154">Malicious files can be stored in locations that are not included in a quick scan.</span></span> <span data-ttu-id="754ce-155">그러나 항상 실시간 보호는 열고 닫힌 모든 파일과 사용자가 액세스한 폴더에 있는 모든 파일을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="754ce-155">However, always-on real-time protection reviews all files that are opened and closed, and any files that are in folders that are accessed by a user.</span></span> <span data-ttu-id="754ce-156">실시간 보호와 빠른 검사의 조합은 맬웨어에 대한 강력한 보호를 제공하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="754ce-156">The combination of real-time protection and a quick scan helps provide strong protection against malware.</span></span>

- <span data-ttu-id="754ce-157">클라우드 제공 보호를 통해 액세스 보호 기능을 사용하면 시스템에서 액세스하는 모든 파일이 최신 보안 인텔리전스 및 클라우드 기계 학습 모델을 통해 스캔되도록 할 수 있습니다. [](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="754ce-157">On-access protection with [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) helps ensure that all the files accessed on the system are being scanned with the latest security intelligence and cloud machine learning models.</span></span>

- <span data-ttu-id="754ce-158">실시간 보호가 맬웨어를 감지하고 영향을 받는 파일의 범위가 처음에 결정되지 않은 경우 Microsoft Defender 바이러스 백신 프로세스의 일부로 전체 검사가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="754ce-158">When real-time protection detects malware and the extent of the affected files is not determined initially, Microsoft Defender Antivirus initiates a full scan as part of the remediation process.</span></span>

- <span data-ttu-id="754ce-159">전체 검사는 빠른 검사와 같은 다른 검사에서 검색되지 않은 악성 파일을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="754ce-159">A full scan can detect malicious files that were not detected by other scans, such as a quick scan.</span></span> <span data-ttu-id="754ce-160">그러나 전체 검사는 시간이 걸릴 수 있으며 중요한 시스템 리소스를 사용하여 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="754ce-160">However, a full scan can take a while and use valuable system resources to complete.</span></span>

- <span data-ttu-id="754ce-161">장치가 오랜 시간 동안 오프라인 상태인 경우 전체 검사가 완료되는 데 더 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="754ce-161">If a device is offline for an extended period of time, a full scan can take longer to complete.</span></span> 

