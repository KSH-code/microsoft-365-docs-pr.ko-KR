---
title: 타사 솔루션에서 마이그레이션하는 동안 Microsoft Defender 바이러스 백신 문제 해결
description: 마이그레이션할 때 발생하는 일반적인 오류 Microsoft Defender 바이러스 백신
keywords: 이벤트, 오류 코드, 로깅, 문제 해결, Microsoft Defender 바이러스 백신, Windows Defender 바이러스 백신, 마이그레이션
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: martyav
ms.author: v-maave
ms.custom: nextgen
ms.date: 09/11/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3fcc79e767edb533a20402a2f92ba4abc7d8386a
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764594"
---
# <a name="troubleshoot-microsoft-defender-antivirus-while-migrating-from-a-third-party-solution"></a><span data-ttu-id="23665-104">타사 솔루션에서 마이그레이션하는 동안 Microsoft Defender 바이러스 백신 문제 해결</span><span class="sxs-lookup"><span data-stu-id="23665-104">Troubleshoot Microsoft Defender Antivirus while migrating from a third-party solution</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="23665-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="23665-105">**Applies to:**</span></span>

- [<span data-ttu-id="23665-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="23665-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)


<span data-ttu-id="23665-107">타사 보안 솔루션에서 타사 보안 솔루션으로 마이그레이션하는 동안 문제가 발생하는 경우 여기에서 도움말을 Microsoft Defender 바이러스 백신.</span><span class="sxs-lookup"><span data-stu-id="23665-107">You can find help here if you encounter issues while migrating from a third-party security solution to Microsoft Defender Antivirus.</span></span>

## <a name="review-event-logs"></a><span data-ttu-id="23665-108">이벤트 로그 검토</span><span class="sxs-lookup"><span data-stu-id="23665-108">Review event logs</span></span>

<span data-ttu-id="23665-109">작업 표시줄에서 검색 아이콘을  선택하고 이벤트 뷰어를 검색하여 이벤트 뷰어 *앱을 열 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="23665-109">Open the Event viewer app by selecting the **Search** icon in the taskbar, and searching for *event viewer*.</span></span>

<span data-ttu-id="23665-110">응용 프로그램에 Microsoft Defender 바이러스 백신 응용 프로그램 및 서비스 로그 Microsoft Windows  >    >  **Windows Defender.**  >  </span><span class="sxs-lookup"><span data-stu-id="23665-110">Information about Microsoft Defender Antivirus can be found under  **Applications and Services Logs** > **Microsoft** > **Windows** > **Windows Defender**.</span></span> 

<span data-ttu-id="23665-111">이 위치에서 작동 **아래의 열기** 를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="23665-111">From there, select **Open** underneath **Operational**.</span></span>

<span data-ttu-id="23665-112">세부 정보 창에서 이벤트를 선택하면 아래쪽 창의 일반 및 세부 정보 탭에서  이벤트에 대한 자세한 정보가 표시됩니다. </span><span class="sxs-lookup"><span data-stu-id="23665-112">Selecting an event from the details pane will show you more information about an event in the lower pane, under the **General** and **Details** tabs.</span></span>

## <a name="microsoft-defender-antivirus-wont-start"></a><span data-ttu-id="23665-113">Microsoft Defender 바이러스 백신 시작되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="23665-113">Microsoft Defender Antivirus won't start</span></span>

<span data-ttu-id="23665-114">이 문제는 여러 가지 이벤트 ID의 형태로 매니페스트될 수 있습니다. 이 모든 이벤트는 모두 동일한 원인이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23665-114">This issue can manifest in the form of  several different event IDs, all of which have the same underlying cause.</span></span>

### <a name="associated-event-ids"></a><span data-ttu-id="23665-115">연결된 이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="23665-115">Associated event IDs</span></span>

 <span data-ttu-id="23665-116">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="23665-116">Event ID</span></span> | <span data-ttu-id="23665-117">로그 이름</span><span class="sxs-lookup"><span data-stu-id="23665-117">Log name</span></span> | <span data-ttu-id="23665-118">설명</span><span class="sxs-lookup"><span data-stu-id="23665-118">Description</span></span> | <span data-ttu-id="23665-119">원본</span><span class="sxs-lookup"><span data-stu-id="23665-119">Source</span></span>
-|-|-|-
<span data-ttu-id="23665-120">15</span><span class="sxs-lookup"><span data-stu-id="23665-120">15</span></span> | <span data-ttu-id="23665-121">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="23665-121">Application</span></span> | <span data-ttu-id="23665-122">업데이트된 Windows Defender 상태가 SECURITY_PRODUCT_STATE_OFF.</span><span class="sxs-lookup"><span data-stu-id="23665-122">Updated Windows Defender status successfully to SECURITY_PRODUCT_STATE_OFF.</span></span> | <span data-ttu-id="23665-123">보안 센터</span><span class="sxs-lookup"><span data-stu-id="23665-123">Security Center</span></span>
<span data-ttu-id="23665-124">5007</span><span class="sxs-lookup"><span data-stu-id="23665-124">5007</span></span> | <span data-ttu-id="23665-125">Microsoft-Windows-Windows Defender/Operational</span><span class="sxs-lookup"><span data-stu-id="23665-125">Microsoft-Windows-Windows Defender/Operational</span></span> | <span data-ttu-id="23665-126">Windows Defender 바이러스 백신 구성이 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="23665-126">Windows Defender Antivirus Configuration has changed.</span></span>  <span data-ttu-id="23665-127">이 이벤트가 예기치 않은 이벤트인 경우 맬웨어의 결과일 수 있는 설정을 검토해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23665-127">If this is an unexpected event you should review the settings as this may be the result of malware.</span></span><br /><br /><span data-ttu-id="23665-128">**이전 값:** Default\IsServiceRunning = 0x0</span><span class="sxs-lookup"><span data-stu-id="23665-128">**Old value:** Default\IsServiceRunning = 0x0</span></span><br /><span data-ttu-id="23665-129">**새 값:** HKLM\SOFTWARE\Microsoft\Windows Defender\IsServiceRunning = 0x1</span><span class="sxs-lookup"><span data-stu-id="23665-129">**New value:** HKLM\SOFTWARE\Microsoft\Windows Defender\IsServiceRunning = 0x1</span></span> | <span data-ttu-id="23665-130">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="23665-130">Windows Defender</span></span>
<span data-ttu-id="23665-131">5010</span><span class="sxs-lookup"><span data-stu-id="23665-131">5010</span></span> | <span data-ttu-id="23665-132">Microsoft-Windows-Windows Defender/Operational</span><span class="sxs-lookup"><span data-stu-id="23665-132">Microsoft-Windows-Windows Defender/Operational</span></span> | <span data-ttu-id="23665-133">Windows Defender 바이러스 백신 소프트웨어 및 사용자 원치 않는 기타 소프트웨어에 대한 검사가 사용되지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="23665-133">Windows Defender Antivirus scanning for spyware and other potentially unwanted software is disabled.</span></span> | <span data-ttu-id="23665-134">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="23665-134">Windows Defender</span></span>

### <a name="how-to-tell-if-microsoft-defender-antivirus-wont-start-because-a-third-party-antivirus-is-installed"></a><span data-ttu-id="23665-135">타사 바이러스 백신이 Microsoft Defender 바이러스 백신 프로그램 업데이트가 시작되지 않는지 어떻게 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23665-135">How to tell if Microsoft Defender Antivirus won't start because a third-party antivirus is installed</span></span>

<span data-ttu-id="23665-136">Windows 10 장치에서 끝점용 Microsoft Defender를 사용하지 않는 경우 타사 바이러스 백신이 설치되어 있는 경우 Microsoft Defender 바이러스 백신 자동으로 꺼집니다.</span><span class="sxs-lookup"><span data-stu-id="23665-136">On a Windows 10 device, if you are not using Microsoft Defender for Endpoint, and you have a third-party antivirus installed, then Microsoft Defender Antivirus will be automatically turned off.</span></span> <span data-ttu-id="23665-137">타사 바이러스 백신이 설치된 끝점용 Microsoft Defender를 사용하는 경우 Microsoft Defender 바이러스 백신 기능이 축소되어 수동 모드로 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="23665-137">If you are using Microsoft Defender for Endpoint with a third-party antivirus installed, Microsoft Defender Antivirus will start in passive mode, with reduced functionality.</span></span>

> [!TIP]
> <span data-ttu-id="23665-138">방금 설명한 시나리오는 해당 시나리오에만 Windows 10.</span><span class="sxs-lookup"><span data-stu-id="23665-138">The scenario just described applies only to Windows 10.</span></span> <span data-ttu-id="23665-139">다른 버전의 Windows [타사](microsoft-defender-antivirus-compatibility.md) 보안 소프트웨어와 함께 실행되는 Microsoft Defender 바이러스 백신 응답이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="23665-139">Other versions of Windows have [different responses](microsoft-defender-antivirus-compatibility.md) to Microsoft Defender Antivirus being run alongside third-party security software.</span></span>

#### <a name="use-services-app-to-check-if-microsoft-defender-antivirus-is-turned-off"></a><span data-ttu-id="23665-140">서비스 앱을 사용하여 서비스 Microsoft Defender 바이러스 백신 해제되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="23665-140">Use Services app to check if Microsoft Defender Antivirus is turned off</span></span>

<span data-ttu-id="23665-141">서비스 앱을 열하려면 작업  표시줄에서 검색 아이콘을 선택하고 서비스를 *검색합니다.*</span><span class="sxs-lookup"><span data-stu-id="23665-141">To open the Services app, select the **Search** icon from the taskbar and search for *services*.</span></span> <span data-ttu-id="23665-142">services.msc 를 입력하여 명령줄에서 앱을 열 *수도 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="23665-142">You can also open the app from the command-line by typing *services.msc*.</span></span>

<span data-ttu-id="23665-143">서비스 Microsoft Defender 바이러스 백신 대한 정보는 운영 에서 서비스 앱 **Windows Defender**  >  **나열됩니다.**</span><span class="sxs-lookup"><span data-stu-id="23665-143">Information about Microsoft Defender Antivirus will be listed within the Services app under **Windows Defender** > **Operational**.</span></span> <span data-ttu-id="23665-144">바이러스 백신 서비스 이름은 Windows Defender 바이러스 백신 *입니다.*</span><span class="sxs-lookup"><span data-stu-id="23665-144">The antivirus service name is *Windows Defender Antivirus Service*.</span></span>

<span data-ttu-id="23665-145">앱을 검사하는 동안 Windows Defender 바이러스 백신 *서비스가* 수동으로 설정되어 있는 것을 볼 수 있지만 이 서비스를 수동으로 시작하려고 시도하면 로컬 컴퓨터에서 Windows Defender 바이러스 백신 서비스 서비스가 시작된 다음 중지됨을 표시하는 경고가 *표시됩니다. 일부 서비스는 다른* 서비스 또는 프로그램에서 사용하지 않는 경우 자동으로 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="23665-145">While checking the app, you may see that *Windows Defender Antivirus Service* is set to manual — but when you try to start this service manually, you get a warning stating, *The Windows Defender Antivirus Service service on Local Computer started and then stopped. Some services stop automatically if they are not in use by other services or programs.*</span></span>

<span data-ttu-id="23665-146">이는 타사 Microsoft Defender 바이러스 백신 호환성을 유지하기 위해 자동으로 꺼져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23665-146">This indicates that Microsoft Defender Antivirus has been automatically turned off to preserve compatibility with a third-party antivirus.</span></span>

#### <a name="generate-a-detailed-report"></a><span data-ttu-id="23665-147">자세한 보고서 생성</span><span class="sxs-lookup"><span data-stu-id="23665-147">Generate a detailed report</span></span>

<span data-ttu-id="23665-148">관리자 모드로 실행 모드에서 명령 프롬프트를 열고  다음 명령을 입력하여 현재 활성 그룹 정책에 대한 자세한 보고서를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23665-148">You can generate a detailed report about currently active group policies by opening a command prompt in **Run as admin** mode, then entering the following command:</span></span>

```powershell
GPresult.exe /h gpresult.html
```

<span data-ttu-id="23665-149">그러면 *./gpresult.html에 있는 gpresult.htm생성됩니다.*</span><span class="sxs-lookup"><span data-stu-id="23665-149">This will generate a report located at *./gpresult.html*.</span></span> <span data-ttu-id="23665-150">이 파일을 열면 끄는 방법에 따라 다음과 같은 Microsoft Defender 바이러스 백신 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23665-150">Open this file and you might see the following results, depending on how Microsoft Defender Antivirus was turned off.</span></span>

##### <a name="group-policy-results"></a><span data-ttu-id="23665-151">그룹 정책 결과</span><span class="sxs-lookup"><span data-stu-id="23665-151">Group policy results</span></span>

##### <a name="if-security-settings-are-implemented-via-group-policy-gpo-at-the-domain-or-local-level-or-though-system-center-configuration-manager-sccm"></a><span data-ttu-id="23665-152">도메인 또는 로컬 수준에서 또는 SCCM(System Center Configuration Manager)을 통해 GPO(그룹 정책)를 통해 보안 설정을 구현하는 경우</span><span class="sxs-lookup"><span data-stu-id="23665-152">If security settings are implemented via group policy (GPO) at the domain or local level, or though System center configuration manager (SCCM)</span></span>

<span data-ttu-id="23665-153">GPResults 보고서의 제목 아래에 Windows *Components/Windows Defender 바이러스 백신*, 다음과 같은 항목이 표시될 수 있습니다. 이 항목은 Microsoft Defender 바이러스 백신 끄는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="23665-153">Within the GPResults report, under the heading, *Windows Components/Windows Defender Antivirus*, you may see something like the following entry, indicating that Microsoft Defender Antivirus is turned off.</span></span>

<span data-ttu-id="23665-154">정책</span><span class="sxs-lookup"><span data-stu-id="23665-154">Policy</span></span> | <span data-ttu-id="23665-155">설정</span><span class="sxs-lookup"><span data-stu-id="23665-155">Setting</span></span> | <span data-ttu-id="23665-156">더하기 GPO</span><span class="sxs-lookup"><span data-stu-id="23665-156">Winning GPO</span></span>
-|-|-
<span data-ttu-id="23665-157">끄기 Windows Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="23665-157">Turn off Windows Defender Antivirus</span></span> | <span data-ttu-id="23665-158">사용</span><span class="sxs-lookup"><span data-stu-id="23665-158">Enabled</span></span> | <span data-ttu-id="23665-159">Win10-Workstations</span><span class="sxs-lookup"><span data-stu-id="23665-159">Win10-Workstations</span></span>

###### <a name="if-security-settings-are-implemented-via-group-policy-preference-gpp"></a><span data-ttu-id="23665-160">GPP(그룹 정책 기본 설정)를 통해 보안 설정을 구현하는 경우</span><span class="sxs-lookup"><span data-stu-id="23665-160">If security settings are implemented via Group policy preference (GPP)</span></span>

<span data-ttu-id="23665-161">레지스트리 항목(키 *경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender, 값 이름: DisableAntiSpyware)* 아래에 다음과 같은 항목이 표시되어 Microsoft Defender 바이러스 백신 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="23665-161">Under the heading, *Registry item (Key path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender, Value name: DisableAntiSpyware)*, you may see something like the following entry, indicating that Microsoft Defender Antivirus is turned off.</span></span>

<span data-ttu-id="23665-162">DisableAntiSpyware</span><span class="sxs-lookup"><span data-stu-id="23665-162">DisableAntiSpyware</span></span> | -
-|-
<span data-ttu-id="23665-163">더하기 GPO</span><span class="sxs-lookup"><span data-stu-id="23665-163">Winning GPO</span></span> | <span data-ttu-id="23665-164">Win10-Workstations</span><span class="sxs-lookup"><span data-stu-id="23665-164">Win10-Workstations</span></span>
<span data-ttu-id="23665-165">결과: 성공</span><span class="sxs-lookup"><span data-stu-id="23665-165">Result: Success</span></span> | 
<span data-ttu-id="23665-166">**일반**</span><span class="sxs-lookup"><span data-stu-id="23665-166">**General**</span></span> | 
<span data-ttu-id="23665-167">조치</span><span class="sxs-lookup"><span data-stu-id="23665-167">Action</span></span> | <span data-ttu-id="23665-168">업데이트</span><span class="sxs-lookup"><span data-stu-id="23665-168">Update</span></span>
<span data-ttu-id="23665-169">**속성**</span><span class="sxs-lookup"><span data-stu-id="23665-169">**Properties**</span></span> | 
<span data-ttu-id="23665-170">Hive</span><span class="sxs-lookup"><span data-stu-id="23665-170">Hive</span></span> | <span data-ttu-id="23665-171">HKEY_LOCAL_MACHINE</span><span class="sxs-lookup"><span data-stu-id="23665-171">HKEY_LOCAL_MACHINE</span></span>
<span data-ttu-id="23665-172">키 경로</span><span class="sxs-lookup"><span data-stu-id="23665-172">Key path</span></span> | <span data-ttu-id="23665-173">SOFTWARE\Policies\Microsoft\Windows Defender</span><span class="sxs-lookup"><span data-stu-id="23665-173">SOFTWARE\Policies\Microsoft\Windows Defender</span></span>
<span data-ttu-id="23665-174">값 이름</span><span class="sxs-lookup"><span data-stu-id="23665-174">Value name</span></span> | <span data-ttu-id="23665-175">DisableAntiSpyware</span><span class="sxs-lookup"><span data-stu-id="23665-175">DisableAntiSpyware</span></span>
<span data-ttu-id="23665-176">값 유형</span><span class="sxs-lookup"><span data-stu-id="23665-176">Value type</span></span> | <span data-ttu-id="23665-177">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="23665-177">REG_DWORD</span></span>
<span data-ttu-id="23665-178">값 데이터</span><span class="sxs-lookup"><span data-stu-id="23665-178">Value data</span></span> | <span data-ttu-id="23665-179">0x1 (1)</span><span class="sxs-lookup"><span data-stu-id="23665-179">0x1 (1)</span></span>

###### <a name="if-security-settings-are-implemented-via-registry-key"></a><span data-ttu-id="23665-180">레지스트리 키를 통해 보안 설정이 구현된 경우</span><span class="sxs-lookup"><span data-stu-id="23665-180">If security settings are implemented via registry key</span></span>

<span data-ttu-id="23665-181">보고서에 다음 텍스트가 포함될 수 있습니다. 이 텍스트는 Microsoft Defender 바이러스 백신 해제되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23665-181">The report may contain the following text, indicating that Microsoft Defender Antivirus is turned off:</span></span>
 
> <span data-ttu-id="23665-182">레지스트리(regedit.exe)</span><span class="sxs-lookup"><span data-stu-id="23665-182">Registry (regedit.exe)</span></span>
>
> <span data-ttu-id="23665-183">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender DisableAntiSpyware(dword) 1(16진수)</span><span class="sxs-lookup"><span data-stu-id="23665-183">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender DisableAntiSpyware (dword) 1 (hex)</span></span>

###### <a name="if-security-settings-are-set-in-windows-or-your-windows-server-image"></a><span data-ttu-id="23665-184">보안 설정이 Windows 서버 Windows 경우</span><span class="sxs-lookup"><span data-stu-id="23665-184">If security settings are set in Windows or your Windows Server image</span></span>

<span data-ttu-id="23665-185">이미징 관리자가 보안 정책 **[DisableAntiSpyware를](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)** 설정하거나,GPEdit.exe *,* LGPO.exe \*\* 또는 작업 순서에서 레지스트리를 수정하여 로컬로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23665-185">Your imagining admin might have set the security policy, **[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)**, locally via *GPEdit.exe*, *LGPO.exe*, or by modifying the registry in their task sequence.</span></span> <span data-ttu-id="23665-186">신뢰할 수 [있는 이미지](/windows-hardware/manufacture/desktop/configure-a-trusted-image-identifier-for-windows-defender) 식별자를 구성할 수 Microsoft Defender 바이러스 백신.</span><span class="sxs-lookup"><span data-stu-id="23665-186">You can [configure a Trusted Image Identifier](/windows-hardware/manufacture/desktop/configure-a-trusted-image-identifier-for-windows-defender) for Microsoft Defender Antivirus.</span></span>

### <a name="turn-microsoft-defender-antivirus-back-on"></a><span data-ttu-id="23665-187">다시 Microsoft Defender 바이러스 백신 켜기</span><span class="sxs-lookup"><span data-stu-id="23665-187">Turn Microsoft Defender Antivirus back on</span></span>

<span data-ttu-id="23665-188">Microsoft Defender 바이러스 백신 활성 상태인 다른 바이러스 백신이 없는 경우 자동으로 켜집니다.</span><span class="sxs-lookup"><span data-stu-id="23665-188">Microsoft Defender Antivirus will automatically turn on if no other antivirus is currently active.</span></span> <span data-ttu-id="23665-189">모든 기능을 사용하여 실행할 수 있도록 타사 바이러스 Microsoft Defender 바이러스 백신 완전히 꺼야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23665-189">You'll need to turn the third-party antivirus completely off to ensure Microsoft Defender Antivirus can run with full functionality.</span></span>

> [!WARNING]
> <span data-ttu-id="23665-190">*wdboot,* *wdfilter,* wdnisdrv, *wdnissvc* 및 *windefend에* 대한 Windows Defender 시작 값을 편집하는 HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services 지원되지 않을 수 있으며 강제로 시스템을 다시 이미지화해야 할 수 있습니다.  </span><span class="sxs-lookup"><span data-stu-id="23665-190">Solutions suggesting that you edit the *Windows Defender* start values for *wdboot*, *wdfilter*, *wdnisdrv*, *wdnissvc*, and *windefend* in  HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services are unsupported, and may force you to re-image your system.</span></span>

<span data-ttu-id="23665-191">수동 모드는 끝점용 Microsoft Defender 및 타사 바이러스 백신과 함께 사용 가능한 Microsoft Defender 바이러스 백신.</span><span class="sxs-lookup"><span data-stu-id="23665-191">Passive mode is available if you start using Microsoft Defender for Endpoint and a third-party antivirus together with Microsoft Defender Antivirus.</span></span> <span data-ttu-id="23665-192">수동 모드를 사용하면 Microsoft Defender가 파일을 검색하고 자체적으로 업데이트할 수 있지만 위협을 해결하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="23665-192">Passive mode allows Microsoft Defender to scan files and update itself, but it will not remediate threats.</span></span> <span data-ttu-id="23665-193">또한 끝점 [DLP(데이터](/microsoft-365/security/defender-endpoint/information-protection-in-windows-overview) 손실 방지)가 배포되지 않는 한 실시간 보호를 통한 동작 모니터링은 수동 모드에서 사용할 수 없습니다. [](configure-real-time-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="23665-193">In addition, behavior monitoring via [Real Time Protection](configure-real-time-protection-microsoft-defender-antivirus.md) is not available under passive mode, unless [Endpoint data loss prevention (DLP)](/microsoft-365/security/defender-endpoint/information-protection-in-windows-overview) is deployed.</span></span>

<span data-ttu-id="23665-194">제한된 주기적 [](limited-periodic-scanning-microsoft-defender-antivirus.md)검사라고 하는 또 다른 기능은 최종 사용자가 자동으로 끄기 Microsoft Defender 바이러스 백신 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23665-194">Another feature, known as [limited periodic scanning](limited-periodic-scanning-microsoft-defender-antivirus.md), is available to end-users when Microsoft Defender Antivirus is set to automatically turn off.</span></span> <span data-ttu-id="23665-195">이 기능을 Microsoft Defender 바이러스 백신 검색을 통해 타사 바이러스 백신과 함께 파일을 주기적으로 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23665-195">This feature allows Microsoft Defender Antivirus to scan files periodically alongside a third-party antivirus, using a limited number of detections.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="23665-196">엔터프라이즈 환경에서는 제한된 주기적 검색을 권장하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="23665-196">Limited periodic scanning is not recommended in enterprise environments.</span></span> <span data-ttu-id="23665-197">이 모드에서 실행 시 사용할 수 있는 검색, 관리 및 보고 Microsoft Defender 바이러스 백신 활성 모드에 비해 감소합니다.</span><span class="sxs-lookup"><span data-stu-id="23665-197">The detection, management and reporting capabilities available when running Microsoft Defender Antivirus in this mode are reduced as compared to active mode.</span></span>

### <a name="see-also"></a><span data-ttu-id="23665-198">참고 항목</span><span class="sxs-lookup"><span data-stu-id="23665-198">See also</span></span>

* [<span data-ttu-id="23665-199">Microsoft Defender 바이러스 백신 호환성</span><span class="sxs-lookup"><span data-stu-id="23665-199">Microsoft Defender Antivirus compatibility</span></span>](microsoft-defender-antivirus-compatibility.md)
* [<span data-ttu-id="23665-200">Microsoft Defender 바이러스 백신 앱의 Windows 보안</span><span class="sxs-lookup"><span data-stu-id="23665-200">Microsoft Defender Antivirus in the Windows Security app</span></span>](microsoft-defender-security-center-antivirus.md)