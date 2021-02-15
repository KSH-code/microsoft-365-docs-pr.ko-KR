---
title: 비영구 가상 데스크톱 인프라(VDI) 장치 온보딩
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: VDI(가상 데스크톱 인프라) 장치에 구성 패키지를 배포하여 Microsoft 365 끝점 데이터 손실 방지 서비스에 온보드합니다.
ms.openlocfilehash: ce5ad0ba6af3e18a6f6c53e1860fc47a77c38770
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769451"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a><span data-ttu-id="f8832-103">비영구 가상 데스크톱 인프라(VDI) 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="f8832-103">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>

<span data-ttu-id="f8832-104">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="f8832-104">**Applies to:**</span></span>
- [<span data-ttu-id="f8832-105">Microsoft 365 끝점 DLP(데이터 손실 방지)</span><span class="sxs-lookup"><span data-stu-id="f8832-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)

- <span data-ttu-id="f8832-106">VDI(가상 데스크톱 인프라) 장치</span><span class="sxs-lookup"><span data-stu-id="f8832-106">Virtual desktop infrastructure (VDI) devices</span></span>

>[!WARNING]
> <span data-ttu-id="f8832-107">Windows Virtual Desktop에 대한 Microsoft 365 엔드포인트 데이터 손실 방지 지원은 단일 세션 시나리오를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="f8832-107">Microsoft 365 Endpoint data loss prevention support for Windows Virtual Desktop supports single session scenarios.</span></span> <span data-ttu-id="f8832-108">Windows Virtual Desktop의 다중 세션 시나리오는 현재 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f8832-108">Multi-session scenarios on Windows Virtual Desktop are currently not supported.</span></span>

## <a name="onboard-vdi-devices"></a><span data-ttu-id="f8832-109">VDI 장치 온보드</span><span class="sxs-lookup"><span data-stu-id="f8832-109">Onboard VDI devices</span></span>

<span data-ttu-id="f8832-110">Microsoft 365 끝점 데이터 손실 방지는 비영구적 VDI 세션 온보더링을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="f8832-110">Microsoft 365 Endpoint data loss prevention supports non-persistent VDI session onboarding.</span></span> 

>[!Note]
><span data-ttu-id="f8832-111">비영구 VDI 세션을 온보드하려면 VDI 장치가 Windows 10 1809 이상에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8832-111">To onboard non-persistent VDI sessions, VDI devices must be on Windows 10 1809 or higher.</span></span>

<span data-ttu-id="f8832-112">VIS를 온보드할 때 관련 문제가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8832-112">There might be associated challenges when onboarding VDIs.</span></span> <span data-ttu-id="f8832-113">이 시나리오의 일반적인 문제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f8832-113">The following are typical challenges for this scenario:</span></span>

- <span data-ttu-id="f8832-114">실제 프로비저닝 전에 Microsoft 365 끝점 데이터 손실 방지에 온보더해야 하는 짧은 세션의 초기 온보드를 즉시 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="f8832-114">Instant early onboarding of a short-lived sessions, which must be onboarded to  Microsoft 365 Endpoint data loss prevention prior to the actual provisioning.</span></span>
- <span data-ttu-id="f8832-115">일반적으로 장치 이름은 새 세션에 다시 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f8832-115">The device name is typically reused for new sessions.</span></span>

<span data-ttu-id="f8832-116">VDI 장치는 다음 중 한 가지로 Microsoft 365 규정 준수 센터에 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8832-116">VDI devices can appear in the Microsoft 365 Compliance center as either:</span></span>

- <span data-ttu-id="f8832-117">각 디바이스에 대한 단일 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="f8832-117">Single entry for each device.</span></span>  
<span data-ttu-id="f8832-118">이 경우 세션을  만들 때 무인 응답 파일을 사용하는 등 동일한 장치 이름을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8832-118">Note that in this case, the *same* device name must be configured when the session is created, for example using an unattended answer file.</span></span>
- <span data-ttu-id="f8832-119">각 디바이스에 대한 여러 항목 - 각 세션에 대해 하나씩</span><span class="sxs-lookup"><span data-stu-id="f8832-119">Multiple entries for each device - one for each session.</span></span>

<span data-ttu-id="f8832-120">다음 단계에서는 VDI 디바이스 온보더링을 안내하고 단일 및 여러 항목에 대한 단계를 강조합니다.</span><span class="sxs-lookup"><span data-stu-id="f8832-120">The following steps will guide you through onboarding VDI devices and will highlight steps for single and multiple entries.</span></span>

>[!WARNING]
> <span data-ttu-id="f8832-121">리소스 구성이 낮은 환경에서는 VDI 부팅 절차로 Microsoft 365 끝점 데이터 손실 방지 온보드가 느려질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8832-121">For environments where there are low resource configurations, the VDI boot procedure might slow the Microsoft 365 Endpoint data loss prevention onboarding.</span></span> 

1.  <span data-ttu-id="f8832-122">서비스 온보더링 마법사에서 \*\* 다운로드한 VDI 구성 패키지 .zip 파일(DeviceCompliancePackage.zip)을 니다.</span><span class="sxs-lookup"><span data-stu-id="f8832-122">Open the VDI configuration package .zip file (*DeviceCompliancePackage.zip*) that you downloaded from the service onboarding wizard.</span></span>

2.  <span data-ttu-id="f8832-123">탐색 창에서 설정 장치  >  **온보더링을**  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f8832-123">In the navigation pane, select **Settings** > **Device onboarding** > **Onboarding**.</span></span>

3. <span data-ttu-id="f8832-124">배포 방법 **필드에서** 비영구 끝점에 대한 **VDI 온보딩 스크립트를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f8832-124">In the **Deployment method** field, select **VDI onboarding scripts for non-persistent endpoints**.</span></span>

5. <span data-ttu-id="f8832-125">패키지 **다운로드를 클릭하고** .zip 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="f8832-125">Click **Download package** and save the .zip file.</span></span>

6. <span data-ttu-id="f8832-126">.zip 파일에서 추출한 DeviceCompliancePackage 폴더의 파일을 경로 아래 이미지로 `golden/master` `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="f8832-126">Copy the files from the DeviceCompliancePackage folder extracted from the .zip file into the `golden/master` image under the path `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup`.</span></span> 

7. <span data-ttu-id="f8832-127">각 장치에 대해 단일 항목을 구현하지 않는 경우 DeviceComplianceOnboardingScript.cmd를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="f8832-127">If you are not implementing a single entry for each device, copy DeviceComplianceOnboardingScript.cmd.</span></span>

8. <span data-ttu-id="f8832-128">각 장치에 대해 단일 항목을 구현하는 경우 Onboard-NonPersistentMachine.ps1 및 DeviceComplianceOnboardingScript.cmd를 모두 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="f8832-128">If you are implementing a single entry for each device, copy both Onboard-NonPersistentMachine.ps1 and DeviceComplianceOnboardingScript.cmd.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f8832-129">폴더가 표시되지 않는 `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` 경우 해당 폴더가 숨겨져 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8832-129">If you don't see the `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` folder, it might be hidden.</span></span> <span data-ttu-id="f8832-130">파일 탐색기에서 숨겨진 파일 및 폴더 **표시** 옵션을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8832-130">You'll need to choose the **Show hidden files and folders** option from File Explorer.</span></span>

9. <span data-ttu-id="f8832-131">로컬 그룹 정책 편집기 창을 열고 **컴퓨터** 구성 Windows 설정 스크립트  >    >    >  **시작으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="f8832-131">Open a Local Group Policy Editor window and navigate to **Computer Configuration** > **Windows Settings** > **Scripts** > **Startup**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f8832-132">도메인 그룹 정책은 비영구적 VDI 장치를 등록하는 데도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8832-132">Domain Group Policy may also be used for onboarding non-persistent VDI devices.</span></span>

4. <span data-ttu-id="f8832-133">구현할 방법에 따라 적절한 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f8832-133">Depending on the method you'd like to implement, follow the appropriate steps:</span></span>

   <span data-ttu-id="f8832-134">**각 디바이스에 대한 단일 항목**</span><span class="sxs-lookup"><span data-stu-id="f8832-134">**For single entry for each device**</span></span>
   
   <span data-ttu-id="f8832-135">**PowerShell** 스크립트 탭을 선택한 다음 **추가를** 클릭합니다(Windows 탐색기는 앞에서 온보딩 스크립트를 복사한 경로에서 직접 열립니다).</span><span class="sxs-lookup"><span data-stu-id="f8832-135">Select the **PowerShell Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="f8832-136">온보딩 PowerShell 스크립트로 `Onboard-NonPersistentMachine.ps1` 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f8832-136">Navigate to onboarding PowerShell script `Onboard-NonPersistentMachine.ps1`.</span></span>
   
   <span data-ttu-id="f8832-137">**각 장치에 대한 여러 항목의 경우:**</span><span class="sxs-lookup"><span data-stu-id="f8832-137">**For multiple entries for each device**:</span></span>
   
   <span data-ttu-id="f8832-138">스크립트 **탭을 선택한** 다음 **추가를** 클릭합니다(Windows 탐색기는 앞에서 온보딩 스크립트를 복사한 경로에서 직접 열립니다).</span><span class="sxs-lookup"><span data-stu-id="f8832-138">Select the **Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="f8832-139">온보딩 bash 스크립트로 `DeviceComplianceOnboardingScript.cmd` 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f8832-139">Navigate to the onboarding bash script `DeviceComplianceOnboardingScript.cmd`.</span></span>

5. <span data-ttu-id="f8832-140">솔루션을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="f8832-140">Test your solution:</span></span>

   1. <span data-ttu-id="f8832-141">하나의 장치로 풀을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8832-141">Create a pool with one device.</span></span>
      
   1. <span data-ttu-id="f8832-142">장치에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="f8832-142">Logon to device.</span></span>
      
   1. <span data-ttu-id="f8832-143">장치에서 로그프합니다.</span><span class="sxs-lookup"><span data-stu-id="f8832-143">Logoff from device.</span></span>

   1. <span data-ttu-id="f8832-144">다른 사용자와 함께 장치에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="f8832-144">Logon to device with another user.</span></span>
      
   1. <span data-ttu-id="f8832-145">**각 장치에 대한 단일** 항목: Microsoft Defender 보안 센터에서 하나의 항목만 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f8832-145">**For single entry for each device**: Check only one entry in Microsoft Defender Security Center.</span></span><br>
      <span data-ttu-id="f8832-146">**각 장치에 대한 여러** 항목: Microsoft Defender 보안 센터에서 여러 항목을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f8832-146">**For multiple entries for each device**: Check multiple entries in Microsoft Defender Security Center.</span></span>

6. <span data-ttu-id="f8832-147">탐색 **창에서** 장치 목록을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f8832-147">Click **Devices list** on the Navigation pane.</span></span>

7. <span data-ttu-id="f8832-148">디바이스 이름을 입력하고 검색 유형으로 **디바이스를** 선택하여 검색 기능을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f8832-148">Use the search function by entering the device name and select **Device** as search type.</span></span>

## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a><span data-ttu-id="f8832-149">비영구 가상 데스크톱 인프라(VDI) 이미지 업데이트</span><span class="sxs-lookup"><span data-stu-id="f8832-149">Updating non-persistent virtual desktop infrastructure (VDI) images</span></span>
<span data-ttu-id="f8832-150">최상의 방법은 오프라인 서비스 도구를 사용하여 골든/마스터 이미지를 패치하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f8832-150">As a best practice, we recommend using offline servicing tools to patch golden/master images.</span></span><br>
<span data-ttu-id="f8832-151">예를 들어 아래 명령을 사용하여 이미지가 오프라인 상태로 유지되는 동안 업데이트를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8832-151">For example, you can use the below commands to install an update while the image remains offline:</span></span>

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

<span data-ttu-id="f8832-152">DISM 명령 및 오프라인 서비스에서 자세한 내용은 아래 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f8832-152">For more information on DISM commands and offline servicing, please refer to the articles below:</span></span>
- [<span data-ttu-id="f8832-153">DISM을 사용하여 Windows 이미지 수정</span><span class="sxs-lookup"><span data-stu-id="f8832-153">Modify a Windows image using DISM</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [<span data-ttu-id="f8832-154">DISM 이미지 관리 Command-Line 옵션</span><span class="sxs-lookup"><span data-stu-id="f8832-154">DISM Image Management Command-Line Options</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [<span data-ttu-id="f8832-155">오프라인 Windows 이미지의 구성 요소 저장소 크기 줄이기</span><span class="sxs-lookup"><span data-stu-id="f8832-155">Reduce the Size of the Component Store in an Offline Windows Image</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

<span data-ttu-id="f8832-156">오프라인 서비스에서 비영구적 VDI 환경에 대해 가능한 옵션이 아닌 경우 일관성 및 센서 상태 확인을 위해 다음 단계를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8832-156">If offline servicing is not a viable option for your non-persistent VDI environment, the following steps should be taken to ensure consistency and sensor health:</span></span>

1. <span data-ttu-id="f8832-157">온라인 서비스 또는 패치에 대한 마스터 이미지를 부팅한 후 오프보딩 스크립트를 실행하여 Microsoft 365 끝점 데이터 손실 방지 센서를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="f8832-157">After booting the master image for online servicing or patching, run an offboarding script to turn off the Microsoft 365 Endpoint data loss prevention sensor.</span></span> <span data-ttu-id="f8832-158">자세한 내용은 로컬 스크립트를 사용하여 [오프보드 장치를 참조하세요.](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script)</span><span class="sxs-lookup"><span data-stu-id="f8832-158">For more information, see [Offboard devices using a local script](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script).</span></span>

2. <span data-ttu-id="f8832-159">CMD 창에서 아래 명령을 실행하여 센서가 중지되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8832-159">Ensure the sensor is stopped by running the command below in a CMD window:</span></span>

   ```console
   sc query sense
   ```

3. <span data-ttu-id="f8832-160">이미지를 필요한 경우 서비스합니다.</span><span class="sxs-lookup"><span data-stu-id="f8832-160">Service the image as needed.</span></span>

4. <span data-ttu-id="f8832-161">아래 명령을 실행하여 PsExec.exe(부팅 후 센서가 누적한 사이버 폴더 콘텐츠를 정리하기 위해 다운로드할 https://download.sysinternals.com/files/PSTools.zip) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8832-161">Run the below commands using PsExec.exe (which can be downloaded from https://download.sysinternals.com/files/PSTools.zip) to cleanup the cyber folder contents that the sensor may have accumulated since boot:</span></span>

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. <span data-ttu-id="f8832-162">평소처럼 골든/마스터 이미지를 다시 봉인합니다.</span><span class="sxs-lookup"><span data-stu-id="f8832-162">Re-seal the golden/master image as you normally would.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f8832-163">관련 항목</span><span class="sxs-lookup"><span data-stu-id="f8832-163">Related topics</span></span>
- [<span data-ttu-id="f8832-164">그룹 정책을 사용하여 Windows 10 장치 온보드</span><span class="sxs-lookup"><span data-stu-id="f8832-164">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="f8832-165">Microsoft Endpoint Configuration Manager를 사용하여 Windows 10 장치 온보드</span><span class="sxs-lookup"><span data-stu-id="f8832-165">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="f8832-166">모바일 장치 관리 도구를 사용하여 Windows 10 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="f8832-166">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="f8832-167">로컬 스크립트를 사용하여 Windows 10 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="f8832-167">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="f8832-168">Microsoft Defender Advanced Threat Protection 온보딩 문제 해결</span><span class="sxs-lookup"><span data-stu-id="f8832-168">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
