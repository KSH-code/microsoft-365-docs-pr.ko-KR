---
title: 비영구 가상 데스크톱 인프라(VDI) 장치 온보딩
description: VDI(가상 데스크톱 인프라) 장치에 구성 패키지를 배포하여 Microsoft Defender ATP 서비스에 온보딩합니다.
keywords: VDI(가상 데스크톱 인프라) 장치 구성, vdi, 장치 관리, Windows ATP 끝점 구성, 끝점용 Microsoft Defender 구성
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 04/16/2020
ms.technology: mde
ms.openlocfilehash: bf1e706562db06064409cb7cf11441d048ef8db6
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445289"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a><span data-ttu-id="c1f65-104">비영구 가상 데스크톱 인프라(VDI) 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="c1f65-104">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c1f65-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="c1f65-105">**Applies to:**</span></span>
- [<span data-ttu-id="c1f65-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="c1f65-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c1f65-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c1f65-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- <span data-ttu-id="c1f65-108">VDI(가상 데스크톱 인프라) 장치</span><span class="sxs-lookup"><span data-stu-id="c1f65-108">Virtual desktop infrastructure (VDI) devices</span></span>
- <span data-ttu-id="c1f65-109">Windows 10, Windows Server 2019, Windows Server 2008R2/2012R2/2016</span><span class="sxs-lookup"><span data-stu-id="c1f65-109">Windows 10, Windows Server 2019, Windows Server 2008R2/2012R2/2016</span></span>

><span data-ttu-id="c1f65-110">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="c1f65-110">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c1f65-111">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f65-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configvdi-abovefoldlink)

## <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a><span data-ttu-id="c1f65-112">비영구 가상 데스크톱 인프라(VDI) 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="c1f65-112">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>

<span data-ttu-id="c1f65-113">Endpoint용 Defender는 비영구 VDI 세션 온보딩을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f65-113">Defender for Endpoint supports non-persistent VDI session onboarding.</span></span> 


<span data-ttu-id="c1f65-114">VIS를 온보드할 때 관련 문제가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f65-114">There might be associated challenges when onboarding VDIs.</span></span> <span data-ttu-id="c1f65-115">이 시나리오의 일반적인 문제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f65-115">The following are typical challenges for this scenario:</span></span>

- <span data-ttu-id="c1f65-116">실제 프로비저닝 전에 끝점용 Defender에 온보딩해야 하는 짧은 세션의 초기 온보딩을 즉각적으로 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f65-116">Instant early onboarding of a short-lived sessions, which must be onboarded to Defender for Endpoint prior to the actual provisioning.</span></span>
- <span data-ttu-id="c1f65-117">일반적으로 장치 이름은 새 세션에 다시 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f65-117">The device name is typically reused for new sessions.</span></span>

<span data-ttu-id="c1f65-118">VDI 장치는 Endpoint 포털용 Defender에 다음 중 하나와 같은 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f65-118">VDI devices can appear in Defender for Endpoint portal as either:</span></span>

- <span data-ttu-id="c1f65-119">각 디바이스에 대한 단일 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="c1f65-119">Single entry for each device.</span></span>

  > [!NOTE]
  > <span data-ttu-id="c1f65-120">이 경우 세션을 만들 때(예: 무인 응답 파일 사용) 동일한 장치 이름을 구성해야 합니다. </span><span class="sxs-lookup"><span data-stu-id="c1f65-120">In this case, the *same* device name must be configured when the session is created, for example using an unattended answer file.</span></span>

- <span data-ttu-id="c1f65-121">각 디바이스에 대한 여러 항목( 각 세션에 대해 하나씩)</span><span class="sxs-lookup"><span data-stu-id="c1f65-121">Multiple entries for each device - one for each session.</span></span>

<span data-ttu-id="c1f65-122">다음 단계에서는 VDI 장치를 등록하는 단계를 안내하고 단일 항목과 여러 항목에 대한 단계를 강조합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f65-122">The following steps will guide you through onboarding VDI devices and will highlight steps for single and multiple entries.</span></span>

>[!WARNING]
> <span data-ttu-id="c1f65-123">리소스 구성이 낮은 환경에서는 VDI 부팅 절차로 끝점 센서의 Defender 온보딩 속도가 느려질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f65-123">For environments where there are low resource configurations, the VDI boot procedure might slow the Defender for Endpoint sensor onboarding.</span></span> 


### <a name="for-windows-10-or-windows-server-2019"></a><span data-ttu-id="c1f65-124">Windows 10 또는 Windows Server 2019의 경우</span><span class="sxs-lookup"><span data-stu-id="c1f65-124">For Windows 10 or Windows Server 2019</span></span>

1.  <span data-ttu-id="c1f65-125">서비스 온보더링 마법사에서 다운로드한 VDI 구성 패키지 *.zip* 파일(WindowsDefenderATPOnboardingPackage.zip)을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f65-125">Open the VDI configuration package .zip file (*WindowsDefenderATPOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="c1f65-126">Microsoft Defender 보안 센터에서 패키지를 [다운로드할 수 있습니다.](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="c1f65-126">You can also get the package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

    1.  <span data-ttu-id="c1f65-127">탐색 창에서 설정   >  **온보드 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c1f65-127">In the navigation pane, select **Settings** > **Onboarding**.</span></span>

    1. <span data-ttu-id="c1f65-128">운영 체제로 Windows 10을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f65-128">Select Windows 10 as the operating system.</span></span>

    1.  <span data-ttu-id="c1f65-129">배포 **방법 필드에서** 비영구 끝점에 **대한 VDI 온보딩 스크립트를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c1f65-129">In the **Deployment method** field, select **VDI onboarding scripts for non-persistent endpoints**.</span></span>

    1. <span data-ttu-id="c1f65-130">패키지 **다운로드를 클릭하고** .zip 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f65-130">Click **Download package** and save the .zip file.</span></span>

2. <span data-ttu-id="c1f65-131">.zip 파일에서 추출한 WindowsDefenderATPOnboardingPackage 폴더의 파일을 경로 아래 `golden/master` 이미지로 `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f65-131">Copy the files from the WindowsDefenderATPOnboardingPackage folder extracted from the .zip file into the `golden/master` image under the path `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup`.</span></span> 

    1. <span data-ttu-id="c1f65-132">각 장치에 대해 단일 항목을 구현하지 않는 경우 WindowsDefenderATPOnboardingScript.cmd를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f65-132">If you are not implementing a single entry for each device, copy WindowsDefenderATPOnboardingScript.cmd.</span></span>

    1. <span data-ttu-id="c1f65-133">각 장치에 대해 단일 항목을 구현하는 경우 Onboard-NonPersistentMachine.ps1 및 WindowsDefenderATPOnboardingScript.cmd를 모두 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f65-133">If you are implementing a single entry for each device, copy both Onboard-NonPersistentMachine.ps1 and WindowsDefenderATPOnboardingScript.cmd.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c1f65-134">폴더가 없는 경우 `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` 숨겨져 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f65-134">If you don't see the `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` folder, it might be hidden.</span></span> <span data-ttu-id="c1f65-135">파일 탐색기에서 숨겨진 파일 및 **폴더 표시** 옵션을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f65-135">You'll need to choose the **Show hidden files and folders** option from File Explorer.</span></span>

3. <span data-ttu-id="c1f65-136">로컬 그룹 정책 편집기 창을 열고 **컴퓨터** 구성 Windows 설정 스크립트 시작  >    >    >  **으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="c1f65-136">Open a Local Group Policy Editor window and navigate to **Computer Configuration** > **Windows Settings** > **Scripts** > **Startup**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c1f65-137">도메인 그룹 정책은 비영구적 VDI 장치를 온보드하는 데도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f65-137">Domain Group Policy may also be used for onboarding non-persistent VDI devices.</span></span>

4. <span data-ttu-id="c1f65-138">구현할 메서드에 따라 적절한 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f65-138">Depending on the method you'd like to implement, follow the appropriate steps:</span></span>

   - <span data-ttu-id="c1f65-139">각 디바이스에 대한 단일 항목:</span><span class="sxs-lookup"><span data-stu-id="c1f65-139">For single entry for each device:</span></span>
   
     <span data-ttu-id="c1f65-140">**PowerShell 스크립트 탭을** 선택한  다음 추가를 클릭합니다(Windows 탐색기는 앞서 온보딩 스크립트를 복사한 경로에서 직접 열립니다).를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f65-140">Select the **PowerShell Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="c1f65-141">온보딩 PowerShell 스크립트로 `Onboard-NonPersistentMachine.ps1` 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f65-141">Navigate to onboarding PowerShell script `Onboard-NonPersistentMachine.ps1`.</span></span> <span data-ttu-id="c1f65-142">다른 파일은 자동으로 트리거되어 다른 파일을 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f65-142">There is no need to specify the other file, as it will be triggered automatically.</span></span>
   
   - <span data-ttu-id="c1f65-143">각 장치에 대한 여러 항목의 경우:</span><span class="sxs-lookup"><span data-stu-id="c1f65-143">For multiple entries for each device:</span></span>
   
     <span data-ttu-id="c1f65-144">스크립트 **탭을** 선택한 다음  추가를 클릭합니다(Windows 탐색기는 앞서 온보딩 스크립트를 복사한 경로에서 직접 열립니다).를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f65-144">Select the **Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="c1f65-145">온보딩 bash 스크립트로 `WindowsDefenderATPOnboardingScript.cmd` 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f65-145">Navigate to the onboarding bash script `WindowsDefenderATPOnboardingScript.cmd`.</span></span>

5. <span data-ttu-id="c1f65-146">솔루션을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f65-146">Test your solution:</span></span>

   1. <span data-ttu-id="c1f65-147">하나의 장치로 풀을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f65-147">Create a pool with one device.</span></span>
      
   1. <span data-ttu-id="c1f65-148">장치에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f65-148">Logon to device.</span></span>
      
   1. <span data-ttu-id="c1f65-149">장치에서 로그프합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f65-149">Logoff from device.</span></span>

   1. <span data-ttu-id="c1f65-150">다른 사용자와 함께 장치에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f65-150">Logon to device with another user.</span></span>
      
   1. <span data-ttu-id="c1f65-151">구현할 메서드에 따라 적절한 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f65-151">Depending on the method you'd like to implement, follow the appropriate steps:</span></span>
   
      - <span data-ttu-id="c1f65-152">각 디바이스에 대한 단일 항목:</span><span class="sxs-lookup"><span data-stu-id="c1f65-152">For single entry for each device:</span></span> 
    
        <span data-ttu-id="c1f65-153">Microsoft Defender 보안 센터에서 하나의 항목만 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f65-153">Check only one entry in Microsoft Defender Security Center.</span></span>

      - <span data-ttu-id="c1f65-154">각 장치에 대한 여러 항목의 경우:</span><span class="sxs-lookup"><span data-stu-id="c1f65-154">For multiple entries for each device:</span></span> 
       
        <span data-ttu-id="c1f65-155">Microsoft Defender 보안 센터에서 여러 항목을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f65-155">Check multiple entries in Microsoft Defender Security Center.</span></span>

6. <span data-ttu-id="c1f65-156">탐색 **창에서** 장치 목록을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f65-156">Click **Devices list** on the Navigation pane.</span></span>

7. <span data-ttu-id="c1f65-157">장치 이름을 입력하고 검색 유형으로 **장치를** 선택하여 검색 기능을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f65-157">Use the search function by entering the device name and select **Device** as search type.</span></span>


## <a name="for-downlevel-skus"></a><span data-ttu-id="c1f65-158">다운클레드 SUS의 경우</span><span class="sxs-lookup"><span data-stu-id="c1f65-158">For downlevel SKUs</span></span>

> [!NOTE]
> <span data-ttu-id="c1f65-159">다음 레지스트리는 '각 장치에 대한 단일 항목'을 달성하는 것이 목표인 경우만 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f65-159">The following registry is relevant only when the aim is to achieve a 'Single entry for each device'.</span></span>

1. <span data-ttu-id="c1f65-160">레지스트리 값을 다음으로 설정</span><span class="sxs-lookup"><span data-stu-id="c1f65-160">Set registry value to:</span></span>

    ```console
   [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging]
    "VDI"="NonPersistent"
    ```

    <span data-ttu-id="c1f65-161">또는 명령줄 사용:</span><span class="sxs-lookup"><span data-stu-id="c1f65-161">or using command line:</span></span>

    ```console
    reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging" /v VDI /t REG_SZ /d "NonPersistent" /f
    ```

2. <span data-ttu-id="c1f65-162">서버 [온보더링 프로세스를 따르는 경우.](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016)</span><span class="sxs-lookup"><span data-stu-id="c1f65-162">Follow the [server onboarding process](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016).</span></span> 



## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a><span data-ttu-id="c1f65-163">비영구적 VDI(가상 데스크톱 인프라) 이미지 업데이트</span><span class="sxs-lookup"><span data-stu-id="c1f65-163">Updating non-persistent virtual desktop infrastructure (VDI) images</span></span>
<span data-ttu-id="c1f65-164">최상의 방법은 오프라인 서비스 도구를 사용하여 골든/마스터 이미지를 패치하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f65-164">As a best practice, we recommend using offline servicing tools to patch golden/master images.</span></span><br>
<span data-ttu-id="c1f65-165">예를 들어 아래 명령을 사용하여 이미지가 오프라인 상태로 유지되는 동안 업데이트를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f65-165">For example, you can use the below commands to install an update while the image remains offline:</span></span>

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

<span data-ttu-id="c1f65-166">DISM 명령 및 오프라인 서비스에 대한 자세한 내용은 아래 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c1f65-166">For more information on DISM commands and offline servicing, please refer to the articles below:</span></span>
- [<span data-ttu-id="c1f65-167">DISM을 사용하여 Windows 이미지 수정</span><span class="sxs-lookup"><span data-stu-id="c1f65-167">Modify a Windows image using DISM</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [<span data-ttu-id="c1f65-168">DISM 이미지 관리 Command-Line 옵션</span><span class="sxs-lookup"><span data-stu-id="c1f65-168">DISM Image Management Command-Line Options</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [<span data-ttu-id="c1f65-169">오프라인 Windows 이미지의 구성 요소 저장소 크기 줄이기</span><span class="sxs-lookup"><span data-stu-id="c1f65-169">Reduce the Size of the Component Store in an Offline Windows Image</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

<span data-ttu-id="c1f65-170">오프라인 서비스에서 비영구적 VDI 환경에 대한 사용 가능한 옵션이 아닌 경우 일관성 및 센서 상태 보장을 위해 다음 단계를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f65-170">If offline servicing is not a viable option for your non-persistent VDI environment, the following steps should be taken to ensure consistency and sensor health:</span></span>

1. <span data-ttu-id="c1f65-171">온라인 서비스 또는 패치에 대한 마스터 이미지를 부팅한 후 오프보딩 스크립트를 실행하여 Endpoint용 Defender 센서를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f65-171">After booting the master image for online servicing or patching, run an offboarding script to turn off the Defender for Endpoint sensor.</span></span> <span data-ttu-id="c1f65-172">자세한 내용은 [로컬 스크립트를 사용하여 장치 오프보드를 참조하세요.](configure-endpoints-script.md#offboard-devices-using-a-local-script)</span><span class="sxs-lookup"><span data-stu-id="c1f65-172">For more information, see [Offboard devices using a local script](configure-endpoints-script.md#offboard-devices-using-a-local-script).</span></span>

2. <span data-ttu-id="c1f65-173">CMD 창에서 아래 명령을 실행하여 센서가 중지되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f65-173">Ensure the sensor is stopped by running the command below in a CMD window:</span></span>

   ```console
   sc query sense
   ```

3. <span data-ttu-id="c1f65-174">필요한 경우 이미지를 서비스합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f65-174">Service the image as needed.</span></span>

4. <span data-ttu-id="c1f65-175">부팅 후 센서가 누적할 수 있는 사이버 폴더 콘텐츠를 정리하기 위해 다운로드할 수 있는 PsExec.exe 명령을 사용하여 다음 명령을 https://download.sysinternals.com/files/PSTools.zip) 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f65-175">Run the below commands using PsExec.exe (which can be downloaded from https://download.sysinternals.com/files/PSTools.zip) to cleanup the cyber folder contents that the sensor may have accumulated since boot:</span></span>

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. <span data-ttu-id="c1f65-176">평소처럼 골든/마스터 이미지를 다시 봉인합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f65-176">Re-seal the golden/master image as you normally would.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c1f65-177">관련 항목</span><span class="sxs-lookup"><span data-stu-id="c1f65-177">Related topics</span></span>
- [<span data-ttu-id="c1f65-178">그룹 정책을 사용하여 Windows 10 장치 온보드</span><span class="sxs-lookup"><span data-stu-id="c1f65-178">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="c1f65-179">Microsoft Endpoint Configuration Manager를 사용하여 Windows 10 장치 온보드</span><span class="sxs-lookup"><span data-stu-id="c1f65-179">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="c1f65-180">모바일 장치 관리 도구를 사용하여 Windows 10 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="c1f65-180">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md)
- [<span data-ttu-id="c1f65-181">로컬 스크립트를 사용하여 Windows 10 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="c1f65-181">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="c1f65-182">끝점 온보딩 문제에 대한 Microsoft Defender 문제 해결</span><span class="sxs-lookup"><span data-stu-id="c1f65-182">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
