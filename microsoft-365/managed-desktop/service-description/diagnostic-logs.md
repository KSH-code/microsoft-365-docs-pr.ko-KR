---
title: 진단 로그
description: 문제 해결 중에 장치에서 수집될 수 있는 로그 및 로그가 저장되는 방법
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: ef7d19fef989610c10323c2a9820a5314d5e1641
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52272898"
---
# <a name="diagnostic-logs"></a><span data-ttu-id="f1052-104">진단 로그</span><span class="sxs-lookup"><span data-stu-id="f1052-104">Diagnostic logs</span></span>

<span data-ttu-id="f1052-105">사용자가 보고한 것이든 서비스에서 식별되어 있는지에 Microsoft Managed Desktop 관리되는 장치의 문제를 해결할 때 사용자의 개입 없이 장치에서 특정 진단 로그를 수집해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1052-105">When we troubleshoot an issue on a device managed by Microsoft Managed Desktop, whether one you've reported or one identified by our service, we might have to collect certain diagnostic logs from the device without intervention from the user.</span></span> <span data-ttu-id="f1052-106">사용자 생성 콘텐츠나 정보는 사용자 Director에서 수집하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f1052-106">We don't collect any user-generated content or information from user directories.</span></span> <span data-ttu-id="f1052-107">장치 상태와 관련한 진단 및 로그 데이터만 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="f1052-107">We only collect diagnostic and log data that concerns device health and status.</span></span>

<span data-ttu-id="f1052-108">수집된 로그는 28일 동안 저장한 다음 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="f1052-108">We store any collected logs for 28 days, and then delete them.</span></span> <span data-ttu-id="f1052-109">데이터 처리 표준에 따라 장치에서 [수집된 모든 로그를 처리합니다.](privacy-personal-data.md)</span><span class="sxs-lookup"><span data-stu-id="f1052-109">We process any logs collected from a device following our [data handling standards](privacy-personal-data.md).</span></span>

## <a name="data-collected"></a><span data-ttu-id="f1052-110">수집된 데이터</span><span class="sxs-lookup"><span data-stu-id="f1052-110">Data collected</span></span>

<span data-ttu-id="f1052-111">이 목록에는 진단 로그를 수집할 수 있는 모든 폴더, Microsoft Managed Desktop, 실행 파일 또는 레지스트리 위치가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1052-111">This list includes all the folders, event logs, executables, or registry locations that Microsoft Managed Desktop might collect diagnostic logs from.</span></span> <span data-ttu-id="f1052-112">수집된 실제 데이터는 이 목록의 하위 집합이 되고 식별된 문제의 종속됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1052-112">The actual data collected will be a subset of this list and depends on the identified issue.</span></span>

### <a name="registry-keys"></a><span data-ttu-id="f1052-113">레지스트리 키</span><span class="sxs-lookup"><span data-stu-id="f1052-113">Registry keys</span></span>

- <span data-ttu-id="f1052-114">HKLM \\ SYSTEM \\ CurrentControlSet \\ Services</span><span class="sxs-lookup"><span data-stu-id="f1052-114">HKLM\\SYSTEM\\CurrentControlSet\\Services</span></span>
- <span data-ttu-id="f1052-115">HKLM \\ 소프트웨어 \\ Microsoft \\ Surface</span><span class="sxs-lookup"><span data-stu-id="f1052-115">HKLM\\SOFTWARE\\Microsoft\\Surface</span></span>
- <span data-ttu-id="f1052-116">HKLM \\ 소프트웨어 정책 Microsoft Windows \\ \\ \\ \\ WindowsUpdate</span><span class="sxs-lookup"><span data-stu-id="f1052-116">HKLM\\SOFTWARE\\Policies\\Microsoft\\Windows\\WindowsUpdate</span></span>
- <span data-ttu-id="f1052-117">HKLM \\ SYSTEM \\ CurrentControlSet \\ 컨트롤 \\ MUI \\ UILanguages</span><span class="sxs-lookup"><span data-stu-id="f1052-117">HKLM\\SYSTEM\\CurrentControlSet\\Control\\MUI\\UILanguages</span></span>
- <span data-ttu-id="f1052-118">HKLM \\ 소프트웨어 정책 Microsoft \\ \\ \\ WindowsStore</span><span class="sxs-lookup"><span data-stu-id="f1052-118">HKLM\\Software\\Policies\\Microsoft\\WindowsStore</span></span>
- <span data-ttu-id="f1052-119">HKLM \\ 소프트웨어 Microsoft Windows \\ \\ \\ CurrentVersion \\ WindowsStore \\ WindowsUpdate</span><span class="sxs-lookup"><span data-stu-id="f1052-119">HKLM\\Software\\Microsoft\\Windows\\CurrentVersion\\WindowsStore\\WindowsUpdate</span></span>
- <span data-ttu-id="f1052-120">HKLM \\ SOFTWARE Microsoft Windows NT \\ \\ \\ CurrentVersion</span><span class="sxs-lookup"><span data-stu-id="f1052-120">HKLM\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion</span></span>
- <span data-ttu-id="f1052-121">HKLM \\ SOFTWARE Microsoft Windows NT \\ \\ \\ CurrentVersion</span><span class="sxs-lookup"><span data-stu-id="f1052-121">HKLM\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion</span></span>
- <span data-ttu-id="f1052-122">HKLM \\ SOFTWARE Microsoft Windows \\ \\ \\ CurrentVersion \\ AppModel</span><span class="sxs-lookup"><span data-stu-id="f1052-122">HKLM\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\AppModel</span></span>
- <span data-ttu-id="f1052-123">HKLM \\ SYSTEM \\ CurrentControlSet \\ 컨트롤 \\ 펌웨어소싱</span><span class="sxs-lookup"><span data-stu-id="f1052-123">HKLM\\SYSTEM\\CurrentControlSet\\Control\\FirmwareResources</span></span>
- <span data-ttu-id="f1052-124">HKLM \\ SOFTWARE \\ Microsoft \\ WindowsSelfhost</span><span class="sxs-lookup"><span data-stu-id="f1052-124">HKLM\\SOFTWARE\\Microsoft\\WindowsSelfhost</span></span>
- <span data-ttu-id="f1052-125">HKLM \\ SOFTWARE \\ Microsoft \\ WindowsUpdate</span><span class="sxs-lookup"><span data-stu-id="f1052-125">HKLM\\SOFTWARE\\Microsoft\\WindowsUpdate</span></span>
- <span data-ttu-id="f1052-126">HKLM \\ SOFTWARE Microsoft Windows \\ \\ \\ CurrentVersion \\ Appx</span><span class="sxs-lookup"><span data-stu-id="f1052-126">HKLM\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Appx</span></span>
- <span data-ttu-id="f1052-127">HKLM \\ SOFTWARE Microsoft Windows NT \\ \\ \\ CurrentVersion \\ Superfetch</span><span class="sxs-lookup"><span data-stu-id="f1052-127">HKLM\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Superfetch</span></span>
- <span data-ttu-id="f1052-128">HKLM \\ 시스템 \\ 설정</span><span class="sxs-lookup"><span data-stu-id="f1052-128">HKLM\\SYSTEM\\Setup</span></span>
- <span data-ttu-id="f1052-129">HKLM \\ Software \\ Microsoft \\ IntuneManagementExtension</span><span class="sxs-lookup"><span data-stu-id="f1052-129">HKLM\\Software\\Microsoft\\IntuneManagementExtension</span></span>
- <span data-ttu-id="f1052-130">HKLM \\ SOFTWARE \\ Microsoft \\ SystemCertificates \\ AuthRoot</span><span class="sxs-lookup"><span data-stu-id="f1052-130">HKLM\\SOFTWARE\\Microsoft\\SystemCertificates\\AuthRoot</span></span>
- <span data-ttu-id="f1052-131">HKLM \\ SOFTWARE Microsoft Windows Advanced Threat \\ \\ Protection</span><span class="sxs-lookup"><span data-stu-id="f1052-131">HKLM\\SOFTWARE\\Microsoft\\Windows Advanced Threat Protection</span></span>
- <span data-ttu-id="f1052-132">HKLM \\ SOFTWARE Microsoft Windows \\ \\ \\ CurrentVersion \\ Authentication \\ LogonUI</span><span class="sxs-lookup"><span data-stu-id="f1052-132">HKLM\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI</span></span>
- <span data-ttu-id="f1052-133">HKLM \\ SOFTWARE Microsoft Windows \\ \\ \\ CurrentVersion \\ Internet 설정</span><span class="sxs-lookup"><span data-stu-id="f1052-133">HKLM\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings</span></span>
- <span data-ttu-id="f1052-134">HKLM \\ 소프트웨어 Microsoft Windows \\ \\ \\ CurrentVersion \\ 제거</span><span class="sxs-lookup"><span data-stu-id="f1052-134">HKLM\\Software\\Microsoft\\Windows\\CurrentVersion\\Uninstall</span></span>
- <span data-ttu-id="f1052-135">HKLM \\ \\ 소프트웨어 정책</span><span class="sxs-lookup"><span data-stu-id="f1052-135">HKLM\\Software\\Policies</span></span>
- <span data-ttu-id="f1052-136">HKLM \\ 소프트웨어 정책 Microsoft \\ \\ \\ Cryptography \\ Configuration \\ SSL</span><span class="sxs-lookup"><span data-stu-id="f1052-136">HKLM\\SOFTWARE\\Policies\\Microsoft\\Cryptography\\Configuration\\SSL</span></span>
- <span data-ttu-id="f1052-137">HKLM 소프트웨어 정책 Microsoft Windows \\ \\ Advanced Threat \\ \\ Protection</span><span class="sxs-lookup"><span data-stu-id="f1052-137">HKLM\\SOFTWARE\\Policies\\Microsoft\\Windows Advanced Threat Protection</span></span>
- <span data-ttu-id="f1052-138">HKLM \\ SOFTWARE \\ WOW6432Node Microsoft Windows \\ \\ \\ CurrentVersion \\ 제거</span><span class="sxs-lookup"><span data-stu-id="f1052-138">HKLM\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall</span></span>
- <span data-ttu-id="f1052-139">HKLM \\ SYSTEM \\ CurrentControlSet \\ Control \\ SecurityProviders \\ SCHANNEL</span><span class="sxs-lookup"><span data-stu-id="f1052-139">HKLM\\SYSTEM\\CurrentControlSet\\Control\\SecurityProviders\\SCHANNEL</span></span>

### <a name="commands"></a><span data-ttu-id="f1052-140">명령</span><span class="sxs-lookup"><span data-stu-id="f1052-140">Commands</span></span>

- <span data-ttu-id="f1052-141">%programfiles% \\ windows defender \\mpcmdrun.exe -GetFiles</span><span class="sxs-lookup"><span data-stu-id="f1052-141">%programfiles%\\windows defender\\mpcmdrun.exe -GetFiles</span></span>
- <span data-ttu-id="f1052-142">%windir% \\ system32 \\certutil.exe -store</span><span class="sxs-lookup"><span data-stu-id="f1052-142">%windir%\\system32\\certutil.exe -store</span></span>
- <span data-ttu-id="f1052-143">%windir% \\ system32 \\certutil.exe -store -user my</span><span class="sxs-lookup"><span data-stu-id="f1052-143">%windir%\\system32\\certutil.exe -store -user my</span></span>
- <span data-ttu-id="f1052-144">%windir% \\ system32 \\Dsregcmd.exe /status</span><span class="sxs-lookup"><span data-stu-id="f1052-144">%windir%\\system32\\Dsregcmd.exe /status</span></span>
- <span data-ttu-id="f1052-145">%windir% \\ system32 \\ipconfig.exe /all</span><span class="sxs-lookup"><span data-stu-id="f1052-145">%windir%\\system32\\ipconfig.exe /all</span></span>
- <span data-ttu-id="f1052-146">%windir% \\ system32 \\ipconfig.exe /displaydns</span><span class="sxs-lookup"><span data-stu-id="f1052-146">%windir%\\system32\\ipconfig.exe /displaydns</span></span>
- <span data-ttu-id="f1052-147">%windir% \\ system32 \\mdmdiagnosticstool.exe</span><span class="sxs-lookup"><span data-stu-id="f1052-147">%windir%\\system32\\mdmdiagnosticstool.exe</span></span>
- <span data-ttu-id="f1052-148">%windir% \\ system32 \\msinfo32.exe /report %temp% \\ MDMDiagnostics \\ msinfo32.log</span><span class="sxs-lookup"><span data-stu-id="f1052-148">%windir%\\system32\\msinfo32.exe /report %temp%\\MDMDiagnostics\\msinfo32.log</span></span>
- <span data-ttu-id="f1052-149">%windir% \\ system32netsh.exe \\ advfirewall show allprofiles</span><span class="sxs-lookup"><span data-stu-id="f1052-149">%windir%\\system32\\netsh.exe advfirewall show allprofiles</span></span>
- <span data-ttu-id="f1052-150">%windir% \\ system32 \\netsh.exe advfirewall show global</span><span class="sxs-lookup"><span data-stu-id="f1052-150">%windir%\\system32\\netsh.exe advfirewall show global</span></span>
- <span data-ttu-id="f1052-151">%windir% \\ system32 \\netsh.exe lan show profiles</span><span class="sxs-lookup"><span data-stu-id="f1052-151">%windir%\\system32\\netsh.exe lan show profiles</span></span>
- <span data-ttu-id="f1052-152">%windir% \\ system32 \\netsh.exe winhttp show proxy</span><span class="sxs-lookup"><span data-stu-id="f1052-152">%windir%\\system32\\netsh.exe winhttp show proxy</span></span>
- <span data-ttu-id="f1052-153">%windir% \\ system32 \\netsh.exe wlan show profiles</span><span class="sxs-lookup"><span data-stu-id="f1052-153">%windir%\\system32\\netsh.exe wlan show profiles</span></span>
- <span data-ttu-id="f1052-154">%windir% \\ system32 \\netsh.exe wlanreport 표시</span><span class="sxs-lookup"><span data-stu-id="f1052-154">%windir%\\system32\\netsh.exe wlan show wlanreport</span></span>
- <span data-ttu-id="f1052-155">%windir% \\ system32 \\ping.exe -n 50 localhost</span><span class="sxs-lookup"><span data-stu-id="f1052-155">%windir%\\system32\\ping.exe -n 50 localhost</span></span>
- <span data-ttu-id="f1052-156">%windir% \\ system32 \\powercfg.exe /batteryreport /output %temp% \\ MDMDiagnostics \\battery-report.html</span><span class="sxs-lookup"><span data-stu-id="f1052-156">%windir%\\system32\\powercfg.exe /batteryreport /output %temp%\\MDMDiagnostics\\battery-report.html</span></span>
- <span data-ttu-id="f1052-157">%windir% \\ system32 \\powercfg.exe /energy /output %temp% \\ MDMDiagnostics \\energy-report.html</span><span class="sxs-lookup"><span data-stu-id="f1052-157">%windir%\\system32\\powercfg.exe /energy /output %temp%\\MDMDiagnostics\\energy-report.html</span></span>
- <span data-ttu-id="f1052-158">bitsadmin /list /allusers /verbose</span><span class="sxs-lookup"><span data-stu-id="f1052-158">bitsadmin /list /allusers /verbose</span></span>
- <span data-ttu-id="f1052-159">fltMC.exe</span><span class="sxs-lookup"><span data-stu-id="f1052-159">fltMC.exe</span></span>
- <span data-ttu-id="f1052-160">bcdedit /enum all /v</span><span class="sxs-lookup"><span data-stu-id="f1052-160">bcdedit /enum all /v</span></span>
- <span data-ttu-id="f1052-161">manage-bde -protectors -get</span><span class="sxs-lookup"><span data-stu-id="f1052-161">manage-bde -protectors -get</span></span>
- <span data-ttu-id="f1052-162">Windows PowerShell 명령:</span><span class="sxs-lookup"><span data-stu-id="f1052-162">Windows PowerShell commands:</span></span>
    - <span data-ttu-id="f1052-163">Get-appxpackage -allusers</span><span class="sxs-lookup"><span data-stu-id="f1052-163">Get-appxpackage -allusers</span></span>
    - <span data-ttu-id="f1052-164">Get-appxpackage -packagetype 번들</span><span class="sxs-lookup"><span data-stu-id="f1052-164">Get-appxpackage -packagetype bundle</span></span>
    - <span data-ttu-id="f1052-165">Get-Service wuauserv</span><span class="sxs-lookup"><span data-stu-id="f1052-165">Get-Service wuauserv</span></span>
    - <span data-ttu-id="f1052-166">Get-NetFirewallRule</span><span class="sxs-lookup"><span data-stu-id="f1052-166">Get-NetFirewallRule</span></span>
    - <span data-ttu-id="f1052-167">Get-WmiObject -Class win32 \_ 제품</span><span class="sxs-lookup"><span data-stu-id="f1052-167">Get-WmiObject -Class win32\_product</span></span>
    - <span data-ttu-id="f1052-168">Get-ComputerInfo</span><span class="sxs-lookup"><span data-stu-id="f1052-168">Get-ComputerInfo</span></span>
    - <span data-ttu-id="f1052-169">Get-Service</span><span class="sxs-lookup"><span data-stu-id="f1052-169">Get-Service</span></span>
    - <span data-ttu-id="f1052-170">Get-Process</span><span class="sxs-lookup"><span data-stu-id="f1052-170">Get-Process</span></span>
    - <span data-ttu-id="f1052-171">Get-WmiObject Win32 \_ PnPSignedDriver</span><span class="sxs-lookup"><span data-stu-id="f1052-171">Get-WmiObject Win32\_PnPSignedDriver</span></span>

### <a name="event-logs"></a><span data-ttu-id="f1052-172">이벤트 로그</span><span class="sxs-lookup"><span data-stu-id="f1052-172">Event logs</span></span>

- <span data-ttu-id="f1052-173">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="f1052-173">Application</span></span>
- <span data-ttu-id="f1052-174">Microsoft-Windows-AppLocker/EXE 및 DLL</span><span class="sxs-lookup"><span data-stu-id="f1052-174">Microsoft-Windows-AppLocker/EXE and DLL</span></span>
- <span data-ttu-id="f1052-175">Microsoft-Windows-AppLocker/MSI 및 스크립트</span><span class="sxs-lookup"><span data-stu-id="f1052-175">Microsoft-Windows-AppLocker/MSI and Script</span></span>
- <span data-ttu-id="f1052-176">Microsoft-Windows-AppLocker/Packaged app-Deployment</span><span class="sxs-lookup"><span data-stu-id="f1052-176">Microsoft-Windows-AppLocker/Packaged app-Deployment</span></span>
- <span data-ttu-id="f1052-177">Microsoft-Windows-AppLocker/패키지된 앱 실행</span><span class="sxs-lookup"><span data-stu-id="f1052-177">Microsoft-Windows-AppLocker/Packaged app-Execution</span></span>
- <span data-ttu-id="f1052-178">Microsoft-Windows-Bitlocker/Bitlocker 관리</span><span class="sxs-lookup"><span data-stu-id="f1052-178">Microsoft-Windows-Bitlocker/Bitlocker Management</span></span>
- <span data-ttu-id="f1052-179">Microsoft-Windows-SENSE/Operational</span><span class="sxs-lookup"><span data-stu-id="f1052-179">Microsoft-Windows-SENSE/Operational</span></span>
- <span data-ttu-id="f1052-180">Microsoft-Windows-SenseIR/Operational</span><span class="sxs-lookup"><span data-stu-id="f1052-180">Microsoft-Windows-SenseIR/Operational</span></span>
- <span data-ttu-id="f1052-181">설정</span><span class="sxs-lookup"><span data-stu-id="f1052-181">Setup</span></span>
- <span data-ttu-id="f1052-182">시스템</span><span class="sxs-lookup"><span data-stu-id="f1052-182">System</span></span>

### <a name="files"></a><span data-ttu-id="f1052-183">파일</span><span class="sxs-lookup"><span data-stu-id="f1052-183">Files</span></span>

- <span data-ttu-id="f1052-184">%ProgramData% \\ Microsoft \\ DiagnosticLogCSP \\ Collectors \\ \* .etl</span><span class="sxs-lookup"><span data-stu-id="f1052-184">%ProgramData%\\Microsoft\\DiagnosticLogCSP\\Collectors\\\*.etl</span></span>
- <span data-ttu-id="f1052-185">%ProgramData% \\ Microsoft \\ IntuneManagementExtension \\ Logs \\ \* .\*</span><span class="sxs-lookup"><span data-stu-id="f1052-185">%ProgramData%\\Microsoft\\IntuneManagementExtension\\Logs\\\*.\*</span></span>
- <span data-ttu-id="f1052-186">%ProgramData% \\ Microsoft Windows Defender 지원 \\ \\ \\MpSupportFiles.cab</span><span class="sxs-lookup"><span data-stu-id="f1052-186">%ProgramData%\\Microsoft\\Windows Defender\\Support\\MpSupportFiles.cab</span></span>
- <span data-ttu-id="f1052-187">%ProgramData% \\ Microsoft \\ Windows \\ WlanReportwlan-report-latest.htm\\ l</span><span class="sxs-lookup"><span data-stu-id="f1052-187">%ProgramData%\\Microsoft\\Windows\\WlanReport\\wlan-report-latest.html</span></span>
- <span data-ttu-id="f1052-188">%ProgramData% \\ Microsoft \\ Windows \\ WlanReport -SourceFileName wlan-report-latest.html</span><span class="sxs-lookup"><span data-stu-id="f1052-188">%ProgramData%\\Microsoft\\Windows\\WlanReport -SourceFileName wlan-report-latest.html</span></span>
- <span data-ttu-id="f1052-189">%windir% \\ ccm \\ logs \* .log</span><span class="sxs-lookup"><span data-stu-id="f1052-189">%windir%\\ccm\\logs\*.log</span></span>
- <span data-ttu-id="f1052-190">%windir% \\ ccmsetup \\ logs \* .log</span><span class="sxs-lookup"><span data-stu-id="f1052-190">%windir%\\ccmsetup\\logs\*.log</span></span>
- <span data-ttu-id="f1052-191">%windir% \\ logs \\ CBS \\ cbs.log</span><span class="sxs-lookup"><span data-stu-id="f1052-191">%windir%\\logs\\CBS\\cbs.log</span></span>
- <span data-ttu-id="f1052-192">%windir% \\ logs \\ measuredboot \* .\*</span><span class="sxs-lookup"><span data-stu-id="f1052-192">%windir%\\logs\\measuredboot\*.\*</span></span>
- <span data-ttu-id="f1052-193">%windir% \\ Logs \\ WindowsUpdate \* .etl</span><span class="sxs-lookup"><span data-stu-id="f1052-193">%windir%\\Logs\\WindowsUpdate\*.etl</span></span>
- <span data-ttu-id="f1052-194">%windir% \\ inf \\ \* .log</span><span class="sxs-lookup"><span data-stu-id="f1052-194">%windir%\\inf\\\*.log</span></span>
- <span data-ttu-id="f1052-195">%windir% \\ 서비스 \\ 세션 \\ActionList.xml</span><span class="sxs-lookup"><span data-stu-id="f1052-195">%windir%\\servicing\\sessions\\ActionList.xml</span></span>
- <span data-ttu-id="f1052-196">%windir% \\ 서비스 \\ 세션 \\Sessions.xml</span><span class="sxs-lookup"><span data-stu-id="f1052-196">%windir%\\servicing\\sessions\\Sessions.xml</span></span>
- <span data-ttu-id="f1052-197">%windir% \\ SoftwareDistribution \\ DataStore \\ Logs \\ edb.log</span><span class="sxs-lookup"><span data-stu-id="f1052-197">%windir%\\SoftwareDistribution\\DataStore\\Logs\\edb.log</span></span>
- <span data-ttu-id="f1052-198">%windir% \\ SoftwareDistribution \\ DataStore \\ DataStore.edb</span><span class="sxs-lookup"><span data-stu-id="f1052-198">%windir%\\SoftwareDistribution\\DataStore\\DataStore.edb</span></span>
- <span data-ttu-id="f1052-199">%windir% \\ logs \\ dism \\ dism.log</span><span class="sxs-lookup"><span data-stu-id="f1052-199">%windir%\\logs\\dism\\dism.log</span></span>
- <span data-ttu-id="f1052-200">%SystemRoot% \\ System32 \\ Winevt \\ Logs</span><span class="sxs-lookup"><span data-stu-id="f1052-200">%SystemRoot%\\System32\\Winevt\\Logs</span></span>\\
- <span data-ttu-id="f1052-201">%appdata% \\ Microsoft Teams 미디어 스택 \\ \\ \\ \* .blog</span><span class="sxs-lookup"><span data-stu-id="f1052-201">%appdata%\\Microsoft\\Teams\\media-stack\\\*.blog</span></span>
- <span data-ttu-id="f1052-202">%appdata% \\ Microsoft \\ Teams \\ skylib \\ \* .blog</span><span class="sxs-lookup"><span data-stu-id="f1052-202">%appdata%\\Microsoft\\Teams\\skylib\\\*.blog</span></span>
- <span data-ttu-id="f1052-203">%appdata% \\ Microsoft Teams 미디어 스택 \\ \\ \\ \* .etl</span><span class="sxs-lookup"><span data-stu-id="f1052-203">%appdata%\\Microsoft\\Teams\\media-stack\\\*.etl</span></span>
- <span data-ttu-id="f1052-204">%appdata% \\ Microsoft \\ Teams \\logs.txt</span><span class="sxs-lookup"><span data-stu-id="f1052-204">%appdata%\\Microsoft\\Teams\\logs.txt</span></span>
- <span data-ttu-id="f1052-205">%windir% \\ Windows \\ System32 \\ winevt \\ \* .\*</span><span class="sxs-lookup"><span data-stu-id="f1052-205">%windir%\\Windows\\System32\\winevt\\\*.\*</span></span>