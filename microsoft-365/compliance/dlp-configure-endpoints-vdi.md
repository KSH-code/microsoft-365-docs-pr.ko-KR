---
title: 온보드 VDI (가상 데스크톱 인프라) 장치 (비영구)
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
description: Microsoft 365 끝점 데이터 손실 방지 서비스에 등록 수 있도록 VDI (가상 데스크톱 인프라) 장치에 구성 패키지를 배포 합니다.
ms.openlocfilehash: ce5ad0ba6af3e18a6f6c53e1860fc47a77c38770
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769451"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a><span data-ttu-id="ae5e3-103">온보드 VDI (가상 데스크톱 인프라) 장치 (비영구)</span><span class="sxs-lookup"><span data-stu-id="ae5e3-103">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>

<span data-ttu-id="ae5e3-104">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="ae5e3-104">**Applies to:**</span></span>
- [<span data-ttu-id="ae5e3-105">Microsoft 365 Endpoint data 손실 방지 (DLP)</span><span class="sxs-lookup"><span data-stu-id="ae5e3-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)

- <span data-ttu-id="ae5e3-106">VDI (가상 데스크톱 인프라) 장치</span><span class="sxs-lookup"><span data-stu-id="ae5e3-106">Virtual desktop infrastructure (VDI) devices</span></span>

>[!WARNING]
> <span data-ttu-id="ae5e3-107">Windows 가상 데스크톱에 대 한 Microsoft 365 끝점 데이터 손실 방지 지원은 단일 세션 시나리오를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5e3-107">Microsoft 365 Endpoint data loss prevention support for Windows Virtual Desktop supports single session scenarios.</span></span> <span data-ttu-id="ae5e3-108">Windows 가상 데스크톱의 다중 세션 시나리오는 현재 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ae5e3-108">Multi-session scenarios on Windows Virtual Desktop are currently not supported.</span></span>

## <a name="onboard-vdi-devices"></a><span data-ttu-id="ae5e3-109">온보드 VDI 장치</span><span class="sxs-lookup"><span data-stu-id="ae5e3-109">Onboard VDI devices</span></span>

<span data-ttu-id="ae5e3-110">Microsoft 365 Endpoint data 손실 방지는 비영구 VDI 세션 온 보 딩을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5e3-110">Microsoft 365 Endpoint data loss prevention supports non-persistent VDI session onboarding.</span></span> 

>[!Note]
><span data-ttu-id="ae5e3-111">비영구 VDI 세션을 온보드 하려면 VDI 장치가 Windows 10 1809 이상에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5e3-111">To onboard non-persistent VDI sessions, VDI devices must be on Windows 10 1809 or higher.</span></span>

<span data-ttu-id="ae5e3-112">온 보 딩 VDIs 때 관련 과제가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae5e3-112">There might be associated challenges when onboarding VDIs.</span></span> <span data-ttu-id="ae5e3-113">이 시나리오의 일반적인 문제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ae5e3-113">The following are typical challenges for this scenario:</span></span>

- <span data-ttu-id="ae5e3-114">일시적인 세션의 신속한 온 보 딩, 실제 프로 비전 전에 Microsoft 365 끝점 데이터 손실 방지로 등록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5e3-114">Instant early onboarding of a short-lived sessions, which must be onboarded to  Microsoft 365 Endpoint data loss prevention prior to the actual provisioning.</span></span>
- <span data-ttu-id="ae5e3-115">일반적으로 새 세션에 장치 이름이 다시 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae5e3-115">The device name is typically reused for new sessions.</span></span>

<span data-ttu-id="ae5e3-116">VDI 장치는 다음 중 하나로 Microsoft 365 준수 센터에 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae5e3-116">VDI devices can appear in the Microsoft 365 Compliance center as either:</span></span>

- <span data-ttu-id="ae5e3-117">각 장치에 대 한 단일 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="ae5e3-117">Single entry for each device.</span></span>  
<span data-ttu-id="ae5e3-118">이 경우에는 무인 응답 파일을 사용 하는 등의 방법으로 세션을 만들 때 *동일한* 장치 이름을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5e3-118">Note that in this case, the *same* device name must be configured when the session is created, for example using an unattended answer file.</span></span>
- <span data-ttu-id="ae5e3-119">각 장치에 대 한 여러 항목 (각 세션에 대해 하나씩)</span><span class="sxs-lookup"><span data-stu-id="ae5e3-119">Multiple entries for each device - one for each session.</span></span>

<span data-ttu-id="ae5e3-120">다음 단계에서는 온 보 딩 VDI 장치를 안내 하 고 여러 항목에 대 한 단계를 강조 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5e3-120">The following steps will guide you through onboarding VDI devices and will highlight steps for single and multiple entries.</span></span>

>[!WARNING]
> <span data-ttu-id="ae5e3-121">리소스 구성이 낮은 환경에서는 VDI 부트 프로시저가 Microsoft 365 끝점 데이터 손실 방지 온 보 딩 속도를 저하 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae5e3-121">For environments where there are low resource configurations, the VDI boot procedure might slow the Microsoft 365 Endpoint data loss prevention onboarding.</span></span> 

1.  <span data-ttu-id="ae5e3-122">서비스 온 보 딩 마법사에서 다운로드 한 VDI 구성 패키지 .zip 파일 ( *DeviceCompliancePackage.zip* )을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ae5e3-122">Open the VDI configuration package .zip file ( *DeviceCompliancePackage.zip* ) that you downloaded from the service onboarding wizard.</span></span>

2.  <span data-ttu-id="ae5e3-123">탐색 창에서 **설정**  >  **장치 온 보**  >  **딩 온** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5e3-123">In the navigation pane, select **Settings** > **Device onboarding** > **Onboarding** .</span></span>

3. <span data-ttu-id="ae5e3-124">**배포 방법** 필드에서 **비영구 끝점에 대 한 VDI 온 보 딩 스크립트** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5e3-124">In the **Deployment method** field, select **VDI onboarding scripts for non-persistent endpoints** .</span></span>

5. <span data-ttu-id="ae5e3-125">**패키지 다운로드** 를 클릭 하 고 .zip 파일을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5e3-125">Click **Download package** and save the .zip file.</span></span>

6. <span data-ttu-id="ae5e3-126">.Zip 파일에서 추출한 DeviceCompliancePackage 폴더의 파일을 `golden/master` 경로 아래의 이미지로 복사 `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5e3-126">Copy the files from the DeviceCompliancePackage folder extracted from the .zip file into the `golden/master` image under the path `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup`.</span></span> 

7. <span data-ttu-id="ae5e3-127">각 장치에 대해 단일 항목을 구현 하지 않는 경우에는 DeviceComplianceOnboardingScript .cmd를 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5e3-127">If you are not implementing a single entry for each device, copy DeviceComplianceOnboardingScript.cmd.</span></span>

8. <span data-ttu-id="ae5e3-128">각 장치에 대해 단일 항목을 구현 하는 경우 Onboard-NonPersistentMachine.ps1 및 DeviceComplianceOnboardingScript를 모두 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5e3-128">If you are implementing a single entry for each device, copy both Onboard-NonPersistentMachine.ps1 and DeviceComplianceOnboardingScript.cmd.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ae5e3-129">이 폴더가 표시 되지 않으면 `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` 숨겨져 있는 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae5e3-129">If you don't see the `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` folder, it might be hidden.</span></span> <span data-ttu-id="ae5e3-130">파일 탐색기에서 **숨김 파일 및 폴더 표시** 옵션을 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5e3-130">You'll need to choose the **Show hidden files and folders** option from File Explorer.</span></span>

9. <span data-ttu-id="ae5e3-131">로컬 그룹 정책 편집기 창을 열고 **컴퓨터 구성**  >  **Windows 설정**  >  **스크립트**  >  **시작** 으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5e3-131">Open a Local Group Policy Editor window and navigate to **Computer Configuration** > **Windows Settings** > **Scripts** > **Startup** .</span></span>

   > [!NOTE]
   > <span data-ttu-id="ae5e3-132">도메인 그룹 정책은 온 보 딩 비영구 VDI 장치에도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae5e3-132">Domain Group Policy may also be used for onboarding non-persistent VDI devices.</span></span>

4. <span data-ttu-id="ae5e3-133">구현 하려는 방법에 따라 적절 한 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="ae5e3-133">Depending on the method you'd like to implement, follow the appropriate steps:</span></span>

   <span data-ttu-id="ae5e3-134">**각 장치에 대 한 단일 항목**</span><span class="sxs-lookup"><span data-stu-id="ae5e3-134">**For single entry for each device**</span></span>
   
   <span data-ttu-id="ae5e3-135">**PowerShell 스크립트** 탭을 선택한 다음 **추가** 를 클릭 합니다 (앞에서 온 보 딩 스크립트를 복사한 경로에서 Windows 탐색기가 바로 열립니다).</span><span class="sxs-lookup"><span data-stu-id="ae5e3-135">Select the **PowerShell Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="ae5e3-136">온 보 딩 PowerShell 스크립트로 이동 `Onboard-NonPersistentMachine.ps1` 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5e3-136">Navigate to onboarding PowerShell script `Onboard-NonPersistentMachine.ps1`.</span></span>
   
   <span data-ttu-id="ae5e3-137">**각 장치에 대 한 여러 항목** :</span><span class="sxs-lookup"><span data-stu-id="ae5e3-137">**For multiple entries for each device** :</span></span>
   
   <span data-ttu-id="ae5e3-138">**스크립트** 탭을 선택한 다음 **추가** 를 클릭 합니다 (앞에서 온 보 딩 스크립트를 복사한 경로에서 Windows 탐색기가 바로 열립니다).</span><span class="sxs-lookup"><span data-stu-id="ae5e3-138">Select the **Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="ae5e3-139">온 보 딩 bash 스크립트로 이동 `DeviceComplianceOnboardingScript.cmd` 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5e3-139">Navigate to the onboarding bash script `DeviceComplianceOnboardingScript.cmd`.</span></span>

5. <span data-ttu-id="ae5e3-140">솔루션 테스트:</span><span class="sxs-lookup"><span data-stu-id="ae5e3-140">Test your solution:</span></span>

   1. <span data-ttu-id="ae5e3-141">장치 한 개를 사용 하 여 풀을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ae5e3-141">Create a pool with one device.</span></span>
      
   1. <span data-ttu-id="ae5e3-142">장치에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5e3-142">Logon to device.</span></span>
      
   1. <span data-ttu-id="ae5e3-143">장치에서 로그 오프 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5e3-143">Logoff from device.</span></span>

   1. <span data-ttu-id="ae5e3-144">다른 사용자와 장치를 함께 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5e3-144">Logon to device with another user.</span></span>
      
   1. <span data-ttu-id="ae5e3-145">**각 장치에 대 한 단일 항목** : Microsoft Defender 보안 센터에서 하나의 항목만 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5e3-145">**For single entry for each device** : Check only one entry in Microsoft Defender Security Center.</span></span><br>
      <span data-ttu-id="ae5e3-146">**각 장치에 대 한 여러 항목** : Microsoft Defender 보안 센터에서 여러 항목을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5e3-146">**For multiple entries for each device** : Check multiple entries in Microsoft Defender Security Center.</span></span>

6. <span data-ttu-id="ae5e3-147">탐색 창에서 **장치 목록을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5e3-147">Click **Devices list** on the Navigation pane.</span></span>

7. <span data-ttu-id="ae5e3-148">검색 기능을 사용 하 여 장치 이름을 입력 하 고 **장치** 를 검색 유형으로 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5e3-148">Use the search function by entering the device name and select **Device** as search type.</span></span>

## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a><span data-ttu-id="ae5e3-149">비영구 VDI (가상 데스크톱 인프라) 이미지 업데이트</span><span class="sxs-lookup"><span data-stu-id="ae5e3-149">Updating non-persistent virtual desktop infrastructure (VDI) images</span></span>
<span data-ttu-id="ae5e3-150">최상의 방법으로는 오프 라인 서비스 도구를 사용 하 여 골든/마스터 이미지를 패치 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ae5e3-150">As a best practice, we recommend using offline servicing tools to patch golden/master images.</span></span><br>
<span data-ttu-id="ae5e3-151">예를 들어 이미지가 오프 라인 상태로 유지 되는 동안 다음 명령을 사용 하 여 업데이트를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae5e3-151">For example, you can use the below commands to install an update while the image remains offline:</span></span>

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

<span data-ttu-id="ae5e3-152">DISM 명령 및 오프 라인 서비스에 대 한 자세한 내용은 다음 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ae5e3-152">For more information on DISM commands and offline servicing, please refer to the articles below:</span></span>
- [<span data-ttu-id="ae5e3-153">DISM을 사용 하 여 Windows 이미지 수정</span><span class="sxs-lookup"><span data-stu-id="ae5e3-153">Modify a Windows image using DISM</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [<span data-ttu-id="ae5e3-154">DISM 이미지 관리 Command-Line 옵션</span><span class="sxs-lookup"><span data-stu-id="ae5e3-154">DISM Image Management Command-Line Options</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [<span data-ttu-id="ae5e3-155">오프 라인 Windows 이미지에서 구성 요소 저장소의 크기 줄이기</span><span class="sxs-lookup"><span data-stu-id="ae5e3-155">Reduce the Size of the Component Store in an Offline Windows Image</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

<span data-ttu-id="ae5e3-156">비영구 VDI 환경에서 오프 라인 서비스를 사용할 수 없는 경우에는 다음 단계를 수행 하 여 일관성 및 센서 상태를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5e3-156">If offline servicing is not a viable option for your non-persistent VDI environment, the following steps should be taken to ensure consistency and sensor health:</span></span>

1. <span data-ttu-id="ae5e3-157">온라인 서비스 또는 패치에 대 한 마스터 이미지를 부팅 한 후에는 오프 보 딩 스크립트를 실행 하 여 Microsoft 365 끝점 데이터 손실 방지 센서를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5e3-157">After booting the master image for online servicing or patching, run an offboarding script to turn off the Microsoft 365 Endpoint data loss prevention sensor.</span></span> <span data-ttu-id="ae5e3-158">자세한 내용은 [로컬 스크립트를 사용 하 여 Offboard 장치](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ae5e3-158">For more information, see [Offboard devices using a local script](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script).</span></span>

2. <span data-ttu-id="ae5e3-159">CMD 창에서 아래 명령을 실행 하 여 센서가 중지 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5e3-159">Ensure the sensor is stopped by running the command below in a CMD window:</span></span>

   ```console
   sc query sense
   ```

3. <span data-ttu-id="ae5e3-160">필요에 따라 이미지를 서비스 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5e3-160">Service the image as needed.</span></span>

4. <span data-ttu-id="ae5e3-161">다음 명령을 실행 하 여 PsExec.exe (다운로드 가능)를 사용 하 여 https://download.sysinternals.com/files/PSTools.zip) 사이버 폴더 콘텐츠를 시작할 수 있는 것으로 정리 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5e3-161">Run the below commands using PsExec.exe (which can be downloaded from https://download.sysinternals.com/files/PSTools.zip) to cleanup the cyber folder contents that the sensor may have accumulated since boot:</span></span>

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. <span data-ttu-id="ae5e3-162">보통 때와 같이 골든/마스터 이미지를 다시 봉인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5e3-162">Re-seal the golden/master image as you normally would.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ae5e3-163">관련 항목</span><span class="sxs-lookup"><span data-stu-id="ae5e3-163">Related topics</span></span>
- [<span data-ttu-id="ae5e3-164">그룹 정책을 사용 하는 온보드 Windows 10 장치</span><span class="sxs-lookup"><span data-stu-id="ae5e3-164">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="ae5e3-165">Microsoft Endpoint Configuration Manager를 사용 하는 Windows 10 장치 온보드</span><span class="sxs-lookup"><span data-stu-id="ae5e3-165">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="ae5e3-166">모바일 장치 관리 도구를 사용 하는 온보드 Windows 10 장치</span><span class="sxs-lookup"><span data-stu-id="ae5e3-166">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="ae5e3-167">로컬 스크립트를 사용 하는 온보드 Windows 10 장치</span><span class="sxs-lookup"><span data-stu-id="ae5e3-167">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="ae5e3-168">Microsoft Defender Advanced Threat Protection 온 보 딩 문제 해결</span><span class="sxs-lookup"><span data-stu-id="ae5e3-168">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
