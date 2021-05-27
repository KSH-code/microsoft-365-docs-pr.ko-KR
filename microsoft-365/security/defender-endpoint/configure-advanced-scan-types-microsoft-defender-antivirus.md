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
ms.date: 05/26/2021
ms.topic: how-to
ms.openlocfilehash: 34f423222068236271afdda13afb95cffa58b709
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683814"
---
# <a name="configure-microsoft-defender-antivirus-scanning-options"></a><span data-ttu-id="de308-104">Microsoft Defender 바이러스 백신 검사 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="de308-104">Configure Microsoft Defender Antivirus scanning options</span></span>

<span data-ttu-id="de308-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="de308-105">**Applies to:**</span></span>

- [<span data-ttu-id="de308-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="de308-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

## <a name="use-microsoft-intune-to-configure-scanning-options"></a><span data-ttu-id="de308-107">검색 Microsoft Intune 사용하여 검사 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="de308-107">Use Microsoft Intune to configure scanning options</span></span>

<span data-ttu-id="de308-108">다음 리소스를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="de308-108">See the following resources:</span></span> 

- [<span data-ttu-id="de308-109">장치에서 장치 제한 Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="de308-109">Configure device restriction settings in Microsoft Intune</span></span>](/intune/device-restrictions-configure) 
- [<span data-ttu-id="de308-110">Microsoft Defender 바이러스 백신 Intune의 Windows 10 장치 제한 설정</span><span class="sxs-lookup"><span data-stu-id="de308-110">Microsoft Defender Antivirus device restriction settings for Windows 10 in Intune</span></span>](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)

## <a name="use-microsoft-endpoint-manager-to-configure-scanning-options"></a><span data-ttu-id="de308-111">검색 Microsoft Endpoint Manager 사용하여 검사 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="de308-111">Use Microsoft Endpoint Manager to configure scanning options</span></span>

<span data-ttu-id="de308-112">맬웨어 방지 정책을 만들고 [배포하는 방법: 검사 설정을 참조하세요.](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings)</span><span class="sxs-lookup"><span data-stu-id="de308-112">See [How to create and deploy antimalware policies: Scan settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings).</span></span>

## <a name="use-group-policy-to-configure-scanning-options"></a><span data-ttu-id="de308-113">그룹 정책을 사용하여 검사 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="de308-113">Use Group Policy to configure scanning options</span></span>

1. <span data-ttu-id="de308-114">그룹 정책 관리 컴퓨터에서 [그룹 정책 관리 콘솔](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="de308-114">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="de308-115">구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭한 다음 편집 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="de308-115">Right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

3. <span data-ttu-id="de308-116">그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동하여** 관리 템플릿 **을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="de308-116">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

4. <span data-ttu-id="de308-117">트리를 확장하여 Windows **구성** Microsoft Defender 바이러스 백신 를 선택한 다음 위치를  >  선택합니다(이 [문서의](#settings-and-locations) 설정 위치 참조).</span><span class="sxs-lookup"><span data-stu-id="de308-117">Expand the tree to **Windows components** > **Microsoft Defender Antivirus**, and then select a location (refer to [Settings and locations](#settings-and-locations) in this article).</span></span>

5. <span data-ttu-id="de308-118">정책 개체를 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="de308-118">Edit the policy object.</span></span> 

6. <span data-ttu-id="de308-119">확인 **을** 클릭하고 다른 설정에 대해 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="de308-119">Click **OK**, and repeat for any other settings.</span></span>

### <a name="settings-and-locations"></a><span data-ttu-id="de308-120">설정 및 위치</span><span class="sxs-lookup"><span data-stu-id="de308-120">Settings and locations</span></span>

| <span data-ttu-id="de308-121">정책 항목 및 위치</span><span class="sxs-lookup"><span data-stu-id="de308-121">Policy item and location</span></span> | <span data-ttu-id="de308-122">기본 설정(구성되지 않은 경우)</span><span class="sxs-lookup"><span data-stu-id="de308-122">Default setting (if not configured)</span></span> | <span data-ttu-id="de308-123">클래스의 PowerShell `Set-MpPreference` 매개 변수 또는 WMI `MSFT_MpPreference` 속성</span><span class="sxs-lookup"><span data-stu-id="de308-123">PowerShell `Set-MpPreference` parameter or WMI property for `MSFT_MpPreference` class</span></span> |
|---|---|---|
| <span data-ttu-id="de308-124">전자 메일 검사</span><span class="sxs-lookup"><span data-stu-id="de308-124">Email scanning</span></span> <p> <span data-ttu-id="de308-125">**스캔**  >  **전자 메일 검사 켜기**</span><span class="sxs-lookup"><span data-stu-id="de308-125">**Scan** > **Turn on e-mail scanning**</span></span><p><span data-ttu-id="de308-126">전자 [메일 검색 제한(이](#email-scanning-limitations) 문서의)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="de308-126">See [Email scanning limitations](#email-scanning-limitations) (in this article)</span></span> | <span data-ttu-id="de308-127">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="de308-127">Disabled</span></span> | `-DisableEmailScanning` |
|<span data-ttu-id="de308-128">[재분석 지점 검사](/windows/win32/fileio/reparse-points)</span><span class="sxs-lookup"><span data-stu-id="de308-128">Scan [reparse points](/windows/win32/fileio/reparse-points)</span></span> <p> <span data-ttu-id="de308-129">**스캔**  >  **재분석 지점 검사 켜기**</span><span class="sxs-lookup"><span data-stu-id="de308-129">**Scan** > **Turn on reparse point scanning**</span></span> | <span data-ttu-id="de308-130">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="de308-130">Disabled</span></span> | <span data-ttu-id="de308-131">사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="de308-131">Not available</span></span> <p><span data-ttu-id="de308-132">[재분석 지점 참조](/windows/win32/fileio/reparse-points)</span><span class="sxs-lookup"><span data-stu-id="de308-132">See [Reparse points](/windows/win32/fileio/reparse-points)</span></span>  |
| <span data-ttu-id="de308-133">매핑된 네트워크 드라이브 검사</span><span class="sxs-lookup"><span data-stu-id="de308-133">Scan mapped network drives</span></span> <p> <span data-ttu-id="de308-134">**스캔**  >  **매핑된 네트워크 드라이브에서** 전체 검사 실행</span><span class="sxs-lookup"><span data-stu-id="de308-134">**Scan** > **Run full scan on mapped network drives**</span></span> | <span data-ttu-id="de308-135">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="de308-135">Disabled</span></span> | `-DisableScanningMappedNetworkDrivesForFullScan`|
| <span data-ttu-id="de308-136">보관 파일(예: 파일 .zip 또는 .rar 검사).</span><span class="sxs-lookup"><span data-stu-id="de308-136">Scan archive files (such as .zip or .rar files).</span></span>  <p> <span data-ttu-id="de308-137">**스캔**  >  **보관 파일 검사**</span><span class="sxs-lookup"><span data-stu-id="de308-137">**Scan** > **Scan archive files**</span></span> | <span data-ttu-id="de308-138">사용</span><span class="sxs-lookup"><span data-stu-id="de308-138">Enabled</span></span> | `-DisableArchiveScanning` <p><span data-ttu-id="de308-139">확장 [제외](configure-extension-file-exclusions-microsoft-defender-antivirus.md) 목록이 이 설정보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="de308-139">The [extensions exclusion list](configure-extension-file-exclusions-microsoft-defender-antivirus.md) will take precedence over this setting.</span></span>|
| <span data-ttu-id="de308-140">네트워크의 파일 검색</span><span class="sxs-lookup"><span data-stu-id="de308-140">Scan files on the network</span></span> <p> <span data-ttu-id="de308-141">**스캔**  >  **네트워크 파일 검사**</span><span class="sxs-lookup"><span data-stu-id="de308-141">**Scan** > **Scan network files**</span></span> | <span data-ttu-id="de308-142">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="de308-142">Disabled</span></span> | `-DisableScanningNetworkFiles` |
| <span data-ttu-id="de308-143">압축된 실행 실행기 검사</span><span class="sxs-lookup"><span data-stu-id="de308-143">Scan packed executables</span></span> <p> <span data-ttu-id="de308-144">**스캔**  >  **압축된 실행 실행기 검사**</span><span class="sxs-lookup"><span data-stu-id="de308-144">**Scan** > **Scan packed executables**</span></span> | <span data-ttu-id="de308-145">사용</span><span class="sxs-lookup"><span data-stu-id="de308-145">Enabled</span></span> | <span data-ttu-id="de308-146">사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="de308-146">Not available</span></span> |
| <span data-ttu-id="de308-147">전체 검사 중에 이동식 드라이브 검색만</span><span class="sxs-lookup"><span data-stu-id="de308-147">Scan removable drives during full scans only</span></span> <p> <span data-ttu-id="de308-148">**스캔**  >  **이동식 드라이브 검사**</span><span class="sxs-lookup"><span data-stu-id="de308-148">**Scan** > **Scan removable drives**</span></span> | <span data-ttu-id="de308-149">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="de308-149">Disabled</span></span> | `-DisableRemovableDriveScanning` |
| <span data-ttu-id="de308-150">검사할 보관 폴더 내의 하위 폴더 수준 지정</span><span class="sxs-lookup"><span data-stu-id="de308-150">Specify the level of subfolders within an archive folder to scan</span></span> <p><span data-ttu-id="de308-151">**스캔**  >  **보관 파일을 검색할 최대 깊이 지정**</span><span class="sxs-lookup"><span data-stu-id="de308-151">**Scan** > **Specify the maximum depth to scan archive files**</span></span> | <span data-ttu-id="de308-152">0</span><span class="sxs-lookup"><span data-stu-id="de308-152">0</span></span> | <span data-ttu-id="de308-153">사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="de308-153">Not available</span></span> |
| <span data-ttu-id="de308-154">검사하는 동안 최대 CPU 부하를 백분율로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="de308-154">Specify the maximum CPU load (as a percentage) during a scan.</span></span> <p> <span data-ttu-id="de308-155">**스캔**  >  **검사 중 CPU 사용률의 최대 백분율 지정**</span><span class="sxs-lookup"><span data-stu-id="de308-155">**Scan** > **Specify the maximum percentage of CPU utilization during a scan**</span></span> | <span data-ttu-id="de308-156">50</span><span class="sxs-lookup"><span data-stu-id="de308-156">50</span></span> |  `-ScanAvgCPULoadFactor` <p><span data-ttu-id="de308-157">**참고:** 최대 CPU 부하는 하드 한도가 아니며 검색 엔진이 평균 최대값을 초과하지 않는 지침입니다.</span><span class="sxs-lookup"><span data-stu-id="de308-157">**NOTE**: The maximum CPU load is not a hard limit, but is guidance for the scanning engine to not exceed the maximum on average.</span></span> <span data-ttu-id="de308-158">수동 실행 검사는 이 설정을 무시하고 CPU 제한 없이 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="de308-158">Manually run scans will ignore this setting and run without any CPU limits.</span></span> |
| <span data-ttu-id="de308-159">검사해야 하는 보관 파일의 최대 크기(킬로바이트)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="de308-159">Specify the maximum size (in kilobytes) of archive files that should be scanned.</span></span> <p> <span data-ttu-id="de308-160">**스캔**  >  **검사할 보관 파일의** 최대 크기 지정</span><span class="sxs-lookup"><span data-stu-id="de308-160">**Scan** > **Specify the maximum size of archive files to be scanned**</span></span> | <span data-ttu-id="de308-161">제한 없음</span><span class="sxs-lookup"><span data-stu-id="de308-161">No limit</span></span> | <span data-ttu-id="de308-162">사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="de308-162">Not available</span></span> <p><span data-ttu-id="de308-163">기본값인 0은 제한 없음을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="de308-163">The default value of 0 applies no limit</span></span> |
| <span data-ttu-id="de308-164">예약된 검사에 대해 낮은 CPU 우선 순위 구성</span><span class="sxs-lookup"><span data-stu-id="de308-164">Configure low CPU priority for scheduled scans</span></span> <p> <span data-ttu-id="de308-165">**스캔**  >  **예약된 검사에 대해 낮은 CPU 우선 순위 구성**</span><span class="sxs-lookup"><span data-stu-id="de308-165">**Scan** > **Configure low CPU priority for scheduled scans**</span></span> | <span data-ttu-id="de308-166">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="de308-166">Disabled</span></span> | <span data-ttu-id="de308-167">사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="de308-167">Not available</span></span> |
 
> [!NOTE]
> <span data-ttu-id="de308-168">실시간 보호가 켜져 있는 경우 파일에 액세스하고 실행하기 전에 파일을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="de308-168">If real-time protection is turned on, files are scanned before they are accessed and executed.</span></span> <span data-ttu-id="de308-169">검사 범위에는 USB 드라이브와 같은 탑재된 이동식 미디어의 파일을 비롯한 모든 파일이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="de308-169">The scanning scope includes all files, including files on mounted removable media, such as USB drives.</span></span> <span data-ttu-id="de308-170">검색을 수행하는 장치에 실시간 보호 또는 액세스 보호가 켜져 있는 경우 검색에는 네트워크 공유도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="de308-170">If the device performing the scan has real-time protection or on-access protection turned on, the scan will also include network shares.</span></span>

## <a name="use-powershell-to-configure-scanning-options"></a><span data-ttu-id="de308-171">PowerShell을 사용하여 검사 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="de308-171">Use PowerShell to configure scanning options</span></span>

<span data-ttu-id="de308-172">다음 리소스를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="de308-172">See the following resources:</span></span>

- [<span data-ttu-id="de308-173">PowerShell cmdlet을 사용하여 Microsoft Defender 바이러스 백신 관리</span><span class="sxs-lookup"><span data-stu-id="de308-173">Manage Microsoft Defender Antivirus with PowerShell cmdlets</span></span>](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [<span data-ttu-id="de308-174">Defender cmdlet</span><span class="sxs-lookup"><span data-stu-id="de308-174">Defender cmdlets</span></span>](/powershell/module/defender/)

## <a name="use-wmi-to-configure-scanning-options"></a><span data-ttu-id="de308-175">WMI를 사용하여 검사 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="de308-175">Use WMI to configure scanning options</span></span>

<span data-ttu-id="de308-176">[WMIv2 api를 Windows Defender 참조합니다.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="de308-176">See [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

## <a name="email-scanning-limitations"></a><span data-ttu-id="de308-177">전자 메일 검사 제한 사항</span><span class="sxs-lookup"><span data-stu-id="de308-177">Email scanning limitations</span></span>

<span data-ttu-id="de308-178">전자 메일 검색을 사용하면 사용자 Outlook 예약된 검사 중에 전자 메일 클라이언트 및 기타 메일 클라이언트에서 사용하는 전자 메일 파일을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de308-178">Email scanning enables scanning of email files used by Outlook and other mail clients during on-demand and scheduled scans.</span></span> <span data-ttu-id="de308-179">전자 메일에 포함된 개체(예: 첨부 파일 및 보관된 파일)도 검사됩니다.</span><span class="sxs-lookup"><span data-stu-id="de308-179">Embedded objects within email (such as attachments and archived files) are also scanned.</span></span> <span data-ttu-id="de308-180">다음 파일 형식 형식을 검사하고 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de308-180">The following file format types can be scanned and remediated:</span></span>

- <span data-ttu-id="de308-181">DBX</span><span class="sxs-lookup"><span data-stu-id="de308-181">DBX</span></span>
- <span data-ttu-id="de308-182">MBX</span><span class="sxs-lookup"><span data-stu-id="de308-182">MBX</span></span>
- <span data-ttu-id="de308-183">MIME</span><span class="sxs-lookup"><span data-stu-id="de308-183">MIME</span></span>

<span data-ttu-id="de308-184">Outlook 2003 또는 이전 버전에서 사용하는 PST 파일(보관 유형이 유니코드가 아닌 것으로 설정되어 있는 경우)도 검색되지만 Microsoft Defender 바이러스 백신 PST 파일 내에서 감지된 위협을 수정하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="de308-184">PST files used by Outlook 2003 or older (where the archive type is set to non-unicode) are also scanned, but Microsoft Defender Antivirus cannot remediate threats that are detected inside PST files.</span></span>

<span data-ttu-id="de308-185">전자 Microsoft Defender 바이러스 백신 내부에서 위협을 감지하는 경우 위협을 수동으로 수정할 수 있도록 손상된 전자 메일을 식별하는 데 도움이 되는 다음 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="de308-185">If Microsoft Defender Antivirus detects a threat inside an email message, it will show you the following information to assist you in identifying the compromised email, so you can remediate the threat manually:</span></span>

- <span data-ttu-id="de308-186">전자 메일 제목</span><span class="sxs-lookup"><span data-stu-id="de308-186">Email subject</span></span>
- <span data-ttu-id="de308-187">첨부 파일 이름</span><span class="sxs-lookup"><span data-stu-id="de308-187">Attachment name</span></span>

## <a name="see-also"></a><span data-ttu-id="de308-188">참고 항목</span><span class="sxs-lookup"><span data-stu-id="de308-188">See also</span></span>

- [<span data-ttu-id="de308-189">사용자 지정, 시작 및 재구성 결과 Microsoft Defender 바이러스 백신 검토</span><span class="sxs-lookup"><span data-stu-id="de308-189">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="de308-190">요청 기반 Microsoft Defender 바이러스 백신 검사 구성 및 실행</span><span class="sxs-lookup"><span data-stu-id="de308-190">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>](run-scan-microsoft-defender-antivirus.md)
- [<span data-ttu-id="de308-191">예약된 Microsoft Defender 바이러스 백신 구성</span><span class="sxs-lookup"><span data-stu-id="de308-191">Configure scheduled Microsoft Defender Antivirus scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="de308-192">Windows 10의 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="de308-192">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
