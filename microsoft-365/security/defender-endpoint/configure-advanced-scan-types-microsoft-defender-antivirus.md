---
title: 사용자에 대한 검사 옵션 Microsoft Defender 바이러스 백신
description: '전자 메일 저장소 파일, 백업 또는 재분석 지점, 네트워크 파일 및 보관된 파일(예: .zip 파일)을 검색하도록 Microsoft Defender AV를 구성할 수 있습니다.'
keywords: 고급 검사, 검사, 전자 메일, 보관, zip, rar, 보관, 재분석 검사
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 1efa72d5b8d204b6aec1cef05fe3c8afe1ca82f7
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275310"
---
# <a name="configure-microsoft-defender-antivirus-scanning-options"></a><span data-ttu-id="377c8-104">Microsoft Defender 바이러스 백신 검사 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="377c8-104">Configure Microsoft Defender Antivirus scanning options</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="377c8-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="377c8-105">**Applies to:**</span></span>

- [<span data-ttu-id="377c8-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="377c8-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

## <a name="use-microsoft-intune-to-configure-scanning-options"></a><span data-ttu-id="377c8-107">검색 Microsoft Intune 사용하여 검사 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="377c8-107">Use Microsoft Intune to configure scanning options</span></span>

<span data-ttu-id="377c8-108">자세한 [내용은](/intune/device-restrictions-configure) [Intune에서](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) Microsoft Intune 및 Microsoft Defender 바이러스 백신 장치 제한 설정 구성을 Windows 10 장치 제한 설정을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="377c8-108">See [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure) and [Microsoft Defender Antivirus device restriction settings for Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) for more details.</span></span>

## <a name="use-microsoft-endpoint-manager-to-configure-scanning-options"></a><span data-ttu-id="377c8-109">검색 Microsoft Endpoint Manager 사용하여 검사 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="377c8-109">Use Microsoft Endpoint Manager to configure scanning options</span></span>

<span data-ttu-id="377c8-110">맬웨어 방지 정책을 만들고 배포하는 [방법:](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings) 검색 설정에서 맬웨어 방지 정책(현재 분기)Microsoft Endpoint Manager 정보를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="377c8-110">See [How to create and deploy antimalware policies: Scan settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings) for details on configuring Microsoft Endpoint Manager (current branch).</span></span>

## <a name="use-group-policy-to-configure-scanning-options"></a><span data-ttu-id="377c8-111">그룹 정책을 사용하여 검사 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="377c8-111">Use Group Policy to configure scanning options</span></span>

<span data-ttu-id="377c8-112">다음 표에 설명된 그룹 정책 설정을 구성하려면</span><span class="sxs-lookup"><span data-stu-id="377c8-112">To configure the Group Policy settings described in the following table:</span></span>

1. <span data-ttu-id="377c8-113">그룹 정책 관리 컴퓨터에서 그룹 [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="377c8-113">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="377c8-114">그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동하여** 관리 템플릿 **을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="377c8-114">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="377c8-115">트리를 확장하여 Windows **구성 > Microsoft Defender 바이러스 백신** 다음 아래  표에 지정된 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="377c8-115">Expand the tree to **Windows components > Microsoft Defender Antivirus** and then the **Location** specified in the table below.</span></span>

4. <span data-ttu-id="377c8-116">아래 표에 지정된 정책 **설정을** 두 번 클릭하고 옵션을 원하는 구성으로 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="377c8-116">Double-click the policy **Setting** as specified in the table below, and set the option to your desired configuration.</span></span> <span data-ttu-id="377c8-117">확인 **을** 클릭하고 다른 설정에 대해 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="377c8-117">Click **OK**, and repeat for any other settings.</span></span>

<span data-ttu-id="377c8-118">설명</span><span class="sxs-lookup"><span data-stu-id="377c8-118">Description</span></span> | <span data-ttu-id="377c8-119">위치 및 설정</span><span class="sxs-lookup"><span data-stu-id="377c8-119">Location and setting</span></span> | <span data-ttu-id="377c8-120">기본 설정(구성되지 않은 경우)</span><span class="sxs-lookup"><span data-stu-id="377c8-120">Default setting (if not configured)</span></span> | <span data-ttu-id="377c8-121">클래스의 PowerShell `Set-MpPreference` 매개 변수 또는 WMI `MSFT_MpPreference` 속성</span><span class="sxs-lookup"><span data-stu-id="377c8-121">PowerShell `Set-MpPreference` parameter or WMI property for `MSFT_MpPreference` class</span></span>
---|---|---|---
<span data-ttu-id="377c8-122">전자 메일 검색 [전자 메일 검사 제한 참조](#ref1)</span><span class="sxs-lookup"><span data-stu-id="377c8-122">Email scanning See [Email scanning limitations](#ref1)</span></span>| <span data-ttu-id="377c8-123">검사 > 전자 메일 검사 켜기</span><span class="sxs-lookup"><span data-stu-id="377c8-123">Scan > Turn on e-mail scanning</span></span> | <span data-ttu-id="377c8-124">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="377c8-124">Disabled</span></span> | `-DisableEmailScanning`
<span data-ttu-id="377c8-125">[재분석 지점 검사](/windows/win32/fileio/reparse-points)</span><span class="sxs-lookup"><span data-stu-id="377c8-125">Scan [reparse points](/windows/win32/fileio/reparse-points)</span></span> | <span data-ttu-id="377c8-126">검사 > 재분석 지점 검사 켜기</span><span class="sxs-lookup"><span data-stu-id="377c8-126">Scan > Turn on reparse point scanning</span></span> | <span data-ttu-id="377c8-127">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="377c8-127">Disabled</span></span> | <span data-ttu-id="377c8-128">사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="377c8-128">Not available</span></span>
<span data-ttu-id="377c8-129">매핑된 네트워크 드라이브 검사</span><span class="sxs-lookup"><span data-stu-id="377c8-129">Scan mapped network drives</span></span> | <span data-ttu-id="377c8-130">검사 > 네트워크 드라이브에서 전체 검사 실행</span><span class="sxs-lookup"><span data-stu-id="377c8-130">Scan > Run full scan on mapped network drives</span></span> | <span data-ttu-id="377c8-131">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="377c8-131">Disabled</span></span> | `-DisableScanningMappedNetworkDrivesForFullScan`
 <span data-ttu-id="377c8-132">보관 파일(예: 파일 .zip 또는 .rar 검사).</span><span class="sxs-lookup"><span data-stu-id="377c8-132">Scan archive files (such as .zip or .rar files).</span></span> <span data-ttu-id="377c8-133">확장 [제외](configure-extension-file-exclusions-microsoft-defender-antivirus.md) 목록이 이 설정보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="377c8-133">The [extensions exclusion list](configure-extension-file-exclusions-microsoft-defender-antivirus.md) will take precedence over this setting.</span></span> | <span data-ttu-id="377c8-134">검사 > 보관 파일 검사</span><span class="sxs-lookup"><span data-stu-id="377c8-134">Scan > Scan archive files</span></span> | <span data-ttu-id="377c8-135">사용</span><span class="sxs-lookup"><span data-stu-id="377c8-135">Enabled</span></span> | `-DisableArchiveScanning`
<span data-ttu-id="377c8-136">네트워크의 파일 검색</span><span class="sxs-lookup"><span data-stu-id="377c8-136">Scan files on the network</span></span> | <span data-ttu-id="377c8-137">검색 > 네트워크 파일 검사</span><span class="sxs-lookup"><span data-stu-id="377c8-137">Scan > Scan network files</span></span> | <span data-ttu-id="377c8-138">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="377c8-138">Disabled</span></span> | `-DisableScanningNetworkFiles`
<span data-ttu-id="377c8-139">압축된 실행 실행기 검사</span><span class="sxs-lookup"><span data-stu-id="377c8-139">Scan packed executables</span></span> | <span data-ttu-id="377c8-140">검사 > 압축된 실행 실행</span><span class="sxs-lookup"><span data-stu-id="377c8-140">Scan > Scan packed executables</span></span> | <span data-ttu-id="377c8-141">사용</span><span class="sxs-lookup"><span data-stu-id="377c8-141">Enabled</span></span> | <span data-ttu-id="377c8-142">사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="377c8-142">Not available</span></span>
<span data-ttu-id="377c8-143">전체 검사 중에 이동식 드라이브 검색만</span><span class="sxs-lookup"><span data-stu-id="377c8-143">Scan removable drives during full scans only</span></span> | <span data-ttu-id="377c8-144">이동식 > 검사</span><span class="sxs-lookup"><span data-stu-id="377c8-144">Scan > Scan removable drives</span></span> | <span data-ttu-id="377c8-145">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="377c8-145">Disabled</span></span> | `-DisableRemovableDriveScanning`
<span data-ttu-id="377c8-146">검사할 보관 폴더 내의 하위 폴더 수준 지정</span><span class="sxs-lookup"><span data-stu-id="377c8-146">Specify the level of subfolders within an archive folder to scan</span></span> | <span data-ttu-id="377c8-147">검사 > 보관 파일을 검색할 최대 깊이 지정</span><span class="sxs-lookup"><span data-stu-id="377c8-147">Scan > Specify the maximum depth to scan archive files</span></span> | <span data-ttu-id="377c8-148">0</span><span class="sxs-lookup"><span data-stu-id="377c8-148">0</span></span> | <span data-ttu-id="377c8-149">사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="377c8-149">Not available</span></span>
 <span data-ttu-id="377c8-150">검사하는 동안 최대 CPU 부하를 백분율로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="377c8-150">Specify the maximum CPU load (as a percentage) during a scan.</span></span> <span data-ttu-id="377c8-151">참고: 이는 하드 한도가 아니라 검색 엔진이 평균적으로 이 최대값을 초과하지 않는 지침입니다.</span><span class="sxs-lookup"><span data-stu-id="377c8-151">Note: This is not a hard limit but rather a guidance for the scanning engine to not exceed this maximum on average.</span></span> | <span data-ttu-id="377c8-152">검사 > 검사 중에 최대 CPU 사용률 지정</span><span class="sxs-lookup"><span data-stu-id="377c8-152">Scan > Specify the maximum percentage of CPU utilization during a scan</span></span> | <span data-ttu-id="377c8-153">50</span><span class="sxs-lookup"><span data-stu-id="377c8-153">50</span></span> |  `-ScanAvgCPULoadFactor`
 <span data-ttu-id="377c8-154">검사해야 하는 보관 파일의 최대 크기(킬로바이트)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="377c8-154">Specify the maximum size (in kilobytes) of archive files that should be scanned.</span></span> <span data-ttu-id="377c8-155">기본값인 **0** 은 제한 없음을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="377c8-155">The default, **0**, applies no limit</span></span> | <span data-ttu-id="377c8-156">검사 > 검사할 보관 파일의 최대 크기 지정</span><span class="sxs-lookup"><span data-stu-id="377c8-156">Scan > Specify the maximum size of archive files to be scanned</span></span> | <span data-ttu-id="377c8-157">제한 없음</span><span class="sxs-lookup"><span data-stu-id="377c8-157">No limit</span></span> | <span data-ttu-id="377c8-158">사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="377c8-158">Not available</span></span>
 <span data-ttu-id="377c8-159">예약된 검사에 대해 낮은 CPU 우선 순위 구성</span><span class="sxs-lookup"><span data-stu-id="377c8-159">Configure low CPU priority for scheduled scans</span></span> | <span data-ttu-id="377c8-160">검사 > 예약된 검사에 대해 낮은 CPU 우선 순위 구성</span><span class="sxs-lookup"><span data-stu-id="377c8-160">Scan > Configure low CPU priority for scheduled scans</span></span> | <span data-ttu-id="377c8-161">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="377c8-161">Disabled</span></span> | <span data-ttu-id="377c8-162">사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="377c8-162">Not available</span></span>
 
> [!NOTE]
> <span data-ttu-id="377c8-163">실시간 보호가 켜져 있는 경우 파일에 액세스하고 실행하기 전에 파일을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="377c8-163">If real-time protection is turned on, files are scanned before they are accessed and executed.</span></span> <span data-ttu-id="377c8-164">검사 범위에는 USB 드라이브와 같은 탑재된 이동식 미디어의 파일을 비롯한 모든 파일이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="377c8-164">The scanning scope includes all files, including files on mounted removable media, such as USB drives.</span></span> <span data-ttu-id="377c8-165">검색을 수행하는 장치에 실시간 보호 또는 액세스 보호가 켜져 있는 경우 검색에는 네트워크 공유도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="377c8-165">If the device performing the scan has real-time protection or on-access protection turned on, the scan will also include network shares.</span></span>

## <a name="use-powershell-to-configure-scanning-options"></a><span data-ttu-id="377c8-166">PowerShell을 사용하여 검사 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="377c8-166">Use PowerShell to configure scanning options</span></span>

<span data-ttu-id="377c8-167">PowerShell Microsoft Defender 바이러스 백신 사용하는 방법에 대한 자세한 내용은 [PowerShell cmdlet](use-powershell-cmdlets-microsoft-defender-antivirus.md) 및 [Defender cmdlet을](/powershell/module/defender/) 사용하여 관리 Microsoft Defender 바이러스 백신.</span><span class="sxs-lookup"><span data-stu-id="377c8-167">See [Manage Microsoft Defender Antivirus with PowerShell cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="use-wmi-to-configure-scanning-options"></a><span data-ttu-id="377c8-168">WMI를 사용하여 검사 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="377c8-168">Use WMI to configure scanning options</span></span>

<span data-ttu-id="377c8-169">WMI 클래스 사용에 대한 자세한 내용은 [WMIv2 api Windows Defender 참조합니다.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="377c8-169">For using WMI classes, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

<a id="ref1"></a>

## <a name="email-scanning-limitations"></a><span data-ttu-id="377c8-170">전자 메일 검사 제한 사항</span><span class="sxs-lookup"><span data-stu-id="377c8-170">Email scanning limitations</span></span>

<span data-ttu-id="377c8-171">전자 메일 검색을 사용하면 사용자 Outlook 예약된 검사 중에 전자 메일 클라이언트 및 기타 메일 클라이언트에서 사용하는 전자 메일 파일을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="377c8-171">Email scanning enables scanning of  email files used by Outlook and other mail clients during on-demand and scheduled scans.</span></span> <span data-ttu-id="377c8-172">첨부 파일 및 보관된 파일과 같은 전자 메일 파일 내에 포함된 개체도 검사됩니다.</span><span class="sxs-lookup"><span data-stu-id="377c8-172">Embedded objects within an email file (such as attachments and archived files) are also scanned.</span></span> <span data-ttu-id="377c8-173">다음 파일 형식 형식을 검사하고 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="377c8-173">The following file format types can be scanned and remediated:</span></span>

- <span data-ttu-id="377c8-174">DBX</span><span class="sxs-lookup"><span data-stu-id="377c8-174">DBX</span></span>
- <span data-ttu-id="377c8-175">MBX</span><span class="sxs-lookup"><span data-stu-id="377c8-175">MBX</span></span>
- <span data-ttu-id="377c8-176">MIME</span><span class="sxs-lookup"><span data-stu-id="377c8-176">MIME</span></span>

<span data-ttu-id="377c8-177">Outlook 2003 또는 이전 버전에서 사용하는 PST 파일(보관 유형이 유니코드가 아닌 것으로 설정되어 있는 경우)도 검색되지만 Windows Defender PST 파일 내에서 감지된 위협을 수정할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="377c8-177">PST files used by Outlook 2003 or older (where the archive type is set to non-unicode) will also be scanned, but Windows Defender cannot remediate threats detected inside PST files.</span></span>

<span data-ttu-id="377c8-178">전자 Microsoft Defender 바이러스 백신 위협을 감지하는 경우 손상된 전자 메일을 식별하는 데 도움이 되는 다음 정보가 표시되어 위협을 수동으로 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="377c8-178">If Microsoft Defender Antivirus detects a threat inside an email, it will show you the following information to assist you in identifying the compromised email, so you can remediate the threat manually:</span></span>

- <span data-ttu-id="377c8-179">전자 메일 제목</span><span class="sxs-lookup"><span data-stu-id="377c8-179">Email subject</span></span>
- <span data-ttu-id="377c8-180">첨부 파일 이름</span><span class="sxs-lookup"><span data-stu-id="377c8-180">Attachment name</span></span>

## <a name="related-topics"></a><span data-ttu-id="377c8-181">관련 항목</span><span class="sxs-lookup"><span data-stu-id="377c8-181">Related topics</span></span>

- [<span data-ttu-id="377c8-182">사용자 지정, 시작 및 재구성 결과 Microsoft Defender 바이러스 백신 검토</span><span class="sxs-lookup"><span data-stu-id="377c8-182">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="377c8-183">요청 기반 Microsoft Defender 바이러스 백신 검사 구성 및 실행</span><span class="sxs-lookup"><span data-stu-id="377c8-183">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>](run-scan-microsoft-defender-antivirus.md)
- [<span data-ttu-id="377c8-184">예약된 Microsoft Defender 바이러스 백신 구성</span><span class="sxs-lookup"><span data-stu-id="377c8-184">Configure scheduled Microsoft Defender Antivirus scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="377c8-185">Microsoft Defender 바이러스 백신 Windows 10</span><span class="sxs-lookup"><span data-stu-id="377c8-185">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)