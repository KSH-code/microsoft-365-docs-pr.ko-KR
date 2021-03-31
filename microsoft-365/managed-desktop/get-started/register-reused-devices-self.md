---
title: 직접 기존의 장치 등록
description: Microsoft Managed Desktop에서 관리할 수 있도록 이미 사용 중일 수 있는 다시 사용 장치 등록
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 1703e4ed4ea0f3306edf6fdf07ab9c97a9266d4f
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445569"
---
# <a name="register-existing-devices-yourself"></a><span data-ttu-id="32ac7-104">직접 기존의 장치 등록</span><span class="sxs-lookup"><span data-stu-id="32ac7-104">Register existing devices yourself</span></span>

>[!NOTE]
><span data-ttu-id="32ac7-105">이 항목에서는 이미 있는 장치를 다시 사용하여 Microsoft Managed Desktop에 등록하는 단계를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-105">This topic describes the steps for you to reuse devices you already have and register them in Microsoft Managed Desktop.</span></span> <span data-ttu-id="32ac7-106">새 장치로 작업하는 경우 대신 Microsoft [Managed Desktop에서](register-devices-self.md) 새 장치 등록의 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="32ac7-106">If you are working with brand-new devices, follow the steps in [Register new devices in Microsoft Managed Desktop yourself](register-devices-self.md) instead.</span></span>

<span data-ttu-id="32ac7-107">파트너를 위한 프로세스는 디바이스를 등록하는 [파트너 단계에 설명되어 있습니다.](register-devices-partner.md)</span><span class="sxs-lookup"><span data-stu-id="32ac7-107">The process for Partners is documented in [Steps for Partners to register devices](register-devices-partner.md).</span></span>

<span data-ttu-id="32ac7-108">Microsoft Managed Desktop은 새로운 장치로 작동하거나 이미 있을 수 있는 장치를 다시 사용할 수 있습니다(다시 이미 사용하려면 다시 이미 사용해야 합니다).</span><span class="sxs-lookup"><span data-stu-id="32ac7-108">Microsoft Managed Desktop can work with brand-new devices or you can reuse devices you might already have (which will require that you reimage them).</span></span> <span data-ttu-id="32ac7-109">Microsoft Endpoint Manager 포털에서 Microsoft Managed Desktop에 장치를 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-109">You can register devices with Microsoft Managed Desktop in the Microsoft Endpoint Manager portal.</span></span>

## <a name="prepare-to-register-existing-devices"></a><span data-ttu-id="32ac7-110">기존 장치 등록 준비</span><span class="sxs-lookup"><span data-stu-id="32ac7-110">Prepare to register existing devices</span></span>


<span data-ttu-id="32ac7-111">기존 장치를 등록하기 위해 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-111">To register existing devices, follow these steps:</span></span>

1. [<span data-ttu-id="32ac7-112">각 디바이스에 대한 하드웨어 해시를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-112">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="32ac7-113">해시 데이터 병합</span><span class="sxs-lookup"><span data-stu-id="32ac7-113">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="32ac7-114">[Microsoft Managed Desktop에 장치를 등록합니다.](#register-devices-by-using-the-admin-portal)</span><span class="sxs-lookup"><span data-stu-id="32ac7-114">[Register the devices in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).</span></span>
4. [<span data-ttu-id="32ac7-115">이미지가 올바른지 다시 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-115">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="32ac7-116">디바이스 전달</span><span class="sxs-lookup"><span data-stu-id="32ac7-116">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="32ac7-117">하드웨어 해시 얻기</span><span class="sxs-lookup"><span data-stu-id="32ac7-117">Obtain the hardware hash</span></span>

<span data-ttu-id="32ac7-118">Microsoft Managed Desktop은 하드웨어 해시를 참조하여 각 장치를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-118">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="32ac7-119">이미 사용 중이신 디바이스에서 이 정보를 4개의 옵션으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-119">You have four options for getting this information from devices you're already using:</span></span>

- <span data-ttu-id="32ac7-120">OEM 공급업체에 하드웨어 해시를 포함할 AutoPilot 등록 파일을 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-120">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="32ac7-121">[Microsoft Endpoint Configuration Manager에서 정보를 수집합니다.](#microsoft-endpoint-configuration-manager)</span><span class="sxs-lookup"><span data-stu-id="32ac7-121">Collect information in [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager).</span></span>
- <span data-ttu-id="32ac7-122">Active [Directory를](#active-directory-powershell-script-method) Windows PowerShell 스크립트를 실행하거나 각 [](#manual-powershell-script-method) 디바이스에서 수동으로 스크립트를 실행하고 결과를 파일에 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-122">Run a Windows PowerShell script--either by using [Active Directory](#active-directory-powershell-script-method) or [manually](#manual-powershell-script-method) on each device--and collect the results in a file.</span></span>
- <span data-ttu-id="32ac7-123">각 디바이스를 시작하지만 Windows 설치 환경을 완료하지는 않습니다. 이동식 플래시 드라이브에서 [해시를 수집합니다.](#flash-drive-method)</span><span class="sxs-lookup"><span data-stu-id="32ac7-123">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="32ac7-124">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="32ac7-124">Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="32ac7-125">Microsoft Endpoint Configuration Manager를 사용하여 Microsoft Managed Desktop에 등록하려는 기존 장치에서 하드웨어 해시를 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-125">You can use Microsoft Endpoint Configuration Manager to collect the hardware hashes from existing devices that you want to register with Microsoft Managed Desktop.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="32ac7-126">이 정보를 얻게 될 디바이스는 Windows 10 버전 1703 이상을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-126">Any devices you want to get this information for must be running Windows 10, version 1703 or later.</span></span> 

<span data-ttu-id="32ac7-127">이러한 모든 선행 단계를 충족하면 다음 단계에 따라 정보를 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-127">If you've met all these prerequisites, you're ready to collect the information by following these steps:</span></span>

1. <span data-ttu-id="32ac7-128">Configuration Manager 콘솔에서 모니터링 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="32ac7-128">In the Configuration Manager console, select **Monitoring**.</span></span> 
2. <span data-ttu-id="32ac7-129">모니터링 작업 영역의 **보고** 노드, **보고서** 및 **하드웨어 -** 일반 노드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-129">In the Monitoring workspace, expand the **Reporting** node, expand **Reports**, and select the **Hardware - General** node.</span></span> 
3. <span data-ttu-id="32ac7-130">보고서를 실행하고 **Windows Autopilot 장치 정보 를 실행하고** 결과를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-130">Run the report, **Windows Autopilot Device Information**, and view the results.</span></span>
4. <span data-ttu-id="32ac7-131">보고서 뷰어에서 내보내기  아이콘을 선택하고 **CSV(콤보로 구성)** 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-131">In the report viewer, select the **Export** icon, and choose the **CSV (comma-delimited)** option.</span></span>
5. <span data-ttu-id="32ac7-132">파일을 저장한 후 Microsoft Managed Desktop에 등록하고 데이터를 Microsoft Managed Desktop에 업로드할 장치로만 결과를 필터링해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-132">After saving the file, you will need to filter results to just those devices you plan to register with Microsoft Managed Desktop and upload the data to Microsoft Managed Desktop.</span></span> <span data-ttu-id="32ac7-133">Microsoft Endpoint Manager를 열고 장치 메뉴로 이동한 다음 Microsoft Managed Desktop 섹션을 찾아 장치 를 **선택합니다.** </span><span class="sxs-lookup"><span data-stu-id="32ac7-133">Open Microsoft Endpoint Manager and navigate to the **Devices** menu, then look for Microsoft Managed Desktop section and select **Devices**.</span></span> <span data-ttu-id="32ac7-134">**+ 장치 등록 을 선택하여** 플라이인을 열어 새 장치를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-134">Select **+ Register devices**, which opens a fly-in to register new devices.</span></span>


<span data-ttu-id="32ac7-135">자세한 내용은 [관리 포털을 사용하여](#register-devices-by-using-the-admin-portal) 장치 등록을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="32ac7-135">Refer to [Register devices by using the Admin Portal](#register-devices-by-using-the-admin-portal) for more information.</span></span>


#### <a name="active-directory-powershell-script-method"></a><span data-ttu-id="32ac7-136">Active Directory PowerShell 스크립트 방법</span><span class="sxs-lookup"><span data-stu-id="32ac7-136">Active Directory PowerShell script method</span></span>

<span data-ttu-id="32ac7-137">Active Directory `Get-WindowsAutoPilotInfo` 환경에서는 PowerShell cmdlet을 사용하여 WinRM을 사용하여 Active Directory 그룹의 장치에서 정보를 원격으로 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-137">In an Active Directory environment, you can use the `Get-WindowsAutoPilotInfo` PowerShell cmdlet to remotely collect the information from devices in Active Directory Groups by using WinRM.</span></span> <span data-ttu-id="32ac7-138">cmdlet을 사용하여 카탈로그에 포함된 특정 하드웨어 모델 이름에 대해 필터링된 `Get-AD Computer` 결과를 얻을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-138">You can also use the `Get-AD Computer` cmdlet and get filtered results for a specific hardware model name included in the catalog.</span></span> <span data-ttu-id="32ac7-139">계속하기 전에 먼저 이러한 선행 단계를 확인한 후 다음 단계를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-139">Before you proceed, first confirm these prerequisites, and then proceed with the steps:</span></span>

- <span data-ttu-id="32ac7-140">WinRM이 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-140">WinRM is enabled.</span></span>
- <span data-ttu-id="32ac7-141">등록하려는 장치가 네트워크에서 활성화되어 있습니다(즉, 연결이 끊어지거나 꺼져 있지 않습니다).</span><span class="sxs-lookup"><span data-stu-id="32ac7-141">The devices you want to register are active on the network (that is, they are not disconnected or turned off).</span></span>
- <span data-ttu-id="32ac7-142">디바이스에서 원격으로 실행할 수 있는 권한이 있는 도메인 자격 증명 매개 변수가 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="32ac7-142">Make sure you have a domain credential parameter that has permission to execute remotely on the devices.</span></span>
- <span data-ttu-id="32ac7-143">Windows 방화벽에서 WMI에 대한 액세스를 허용하는지 확인</span><span class="sxs-lookup"><span data-stu-id="32ac7-143">Make sure that Windows Firewall allows access to WMI.</span></span> <span data-ttu-id="32ac7-144">이렇게 하여 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-144">To do that, follow these steps:</span></span>

    1. <span data-ttu-id="32ac7-145">Windows Defender **방화벽** 제어판을 열고 방화벽을 통해 앱 또는 **기능 Windows Defender 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="32ac7-145">Open the **Windows Defender Firewall** control panel and select **Allow an app or feature through Windows Defender Firewall**.</span></span>
    
    2. <span data-ttu-id="32ac7-146">목록에서 **WMI(Windows Management Instrumentation)를** 찾고 개인 및 공용 모두에 대해 사용하도록 **설정한** 다음 확인 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="32ac7-146">Find **Windows Management Instrumentation (WMI)** in the list, enable for both **Private and Public**, and then select **OK**.</span></span>

1.  <span data-ttu-id="32ac7-147">관리 권한으로 PowerShell 프롬프트를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-147">Open a PowerShell prompt with administrative rights.</span></span>

2.  <span data-ttu-id="32ac7-148">다음 *스크립트 중* 하나를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-148">Run *either one* of these scripts:</span></span>

    ```powershell
    Install-script -name Get-WindowsAutoPilotInfo 
    #example one – leverage Get-ADComputer to enumerate devices 
    Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname>
    ```

    ```powershell 
    #example two – target specific devices: 
    Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
    ```

3. <span data-ttu-id="32ac7-149">장치에 대한 항목이 있을 수 있는 모든 Director에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-149">Access any directories where there might be entries for the devices.</span></span> <span data-ttu-id="32ac7-150">Windows Server Active  Directory 도메인 서비스 및 Azure Active Directory를 비롯한 모든 디렉터리에서 각 장치에 대한 항목을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-150">Remove entries for each device from *all* directories, including Windows Server Active Directory Domain Services and Azure Active Directory.</span></span> <span data-ttu-id="32ac7-151">제거를 완전히 처리하는 데 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-151">Be aware that removal could take a few hours to completely process.</span></span>

4. <span data-ttu-id="32ac7-152">장치에 대한 항목이 있을 수 있는 액세스 관리 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-152">Access management services where there might be entries for the devices.</span></span> <span data-ttu-id="32ac7-153">Microsoft Endpoint Configuration  Manager, Microsoft Intune 및 Windows Autopilot을 비롯한 모든 관리 서비스에서 각 장치에 대한 항목을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-153">Remove entries for each device from *all* management services, including Microsoft Endpoint Configuration Manager, Microsoft Intune, and Windows Autopilot.</span></span> <span data-ttu-id="32ac7-154">제거를 완전히 처리하는 데 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-154">Be aware that removal could take a few hours to completely process.</span></span>

<span data-ttu-id="32ac7-155">이제 장치 [등록을 진행할 수 있습니다.](#register-devices-by-using-the-admin-portal)</span><span class="sxs-lookup"><span data-stu-id="32ac7-155">Now you can proceed to [register devices](#register-devices-by-using-the-admin-portal).</span></span>

#### <a name="manual-powershell-script-method"></a><span data-ttu-id="32ac7-156">수동 PowerShell 스크립트 방법</span><span class="sxs-lookup"><span data-stu-id="32ac7-156">Manual PowerShell script method</span></span>

1.  <span data-ttu-id="32ac7-157">관리 권한으로 PowerShell 프롬프트를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-157">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="32ac7-158">실행 `Install-Script -Name Get-WindowsAutoPilotInfo`</span><span class="sxs-lookup"><span data-stu-id="32ac7-158">Run `Install-Script -Name Get-WindowsAutoPilotInfo`</span></span>
3.  <span data-ttu-id="32ac7-159">실행 `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="32ac7-159">Run `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
4. [<span data-ttu-id="32ac7-160">해시 데이터를 병합합니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-160">Merge the hash data.</span></span>](#merge-hash-data)

#### <a name="flash-drive-method"></a><span data-ttu-id="32ac7-161">플래시 드라이브 방법</span><span class="sxs-lookup"><span data-stu-id="32ac7-161">Flash drive method</span></span>

1. <span data-ttu-id="32ac7-162">등록할 장치 외의 디바이스에서 USB 드라이브를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-162">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="32ac7-163">관리 권한으로 PowerShell 프롬프트를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-163">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="32ac7-164">실행 `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="32ac7-164">Run `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="32ac7-165">등록하는 장치를 켜지만 설치 *환경을 시작하지는 않습니다.*</span><span class="sxs-lookup"><span data-stu-id="32ac7-165">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="32ac7-166">실수로 설치 환경을 시작한 경우 장치를 초기화하거나 다시 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-166">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="32ac7-167">USB 드라이브를 삽입한 다음 Shift + F10을 누를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-167">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="32ac7-168">관리 권한으로 PowerShell 프롬프트를 열고 를 `cd <pathToUsb>` 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-168">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="32ac7-169">실행 `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="32ac7-169">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="32ac7-170">실행 `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="32ac7-170">Run `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="32ac7-171">USB 드라이브를 제거한 다음 를 실행하여 디바이스를 종료합니다. `shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="32ac7-171">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>
10. [<span data-ttu-id="32ac7-172">해시 데이터를 병합합니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-172">Merge the hash data.</span></span>](#merge-hash-data)

>[!IMPORTANT]
><span data-ttu-id="32ac7-173">등록을 완료할 때까지 다시 등록하는 디바이스에 전원을 들이지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-173">Do not power on the device you are registering again until you've completed registration for it.</span></span> 



### <a name="merge-hash-data"></a><span data-ttu-id="32ac7-174">해시 데이터 병합</span><span class="sxs-lookup"><span data-stu-id="32ac7-174">Merge hash data</span></span>

<span data-ttu-id="32ac7-175">수동 PowerShell 또는 플래시 드라이브 방법을 통해 하드웨어 해시 데이터를 수집한 경우 이제 등록을 완료하려면 CSV 파일의 데이터를 단일 파일로 결합해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-175">If you collected the hardware hash data by the manual PowerShell or flash drive methods, you now need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="32ac7-176">다음은 쉽게 사용할 수 있도록 하는 샘플 PowerShell 스크립트입니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-176">Here's a sample PowerShell script to make it easy:</span></span>

```powershell
Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv
```

<span data-ttu-id="32ac7-177">해시 데이터가 하나의 CSV 파일에 병합되어 이제 장치를 [등록할 수 있습니다.](#register-devices-by-using-the-admin-portal)</span><span class="sxs-lookup"><span data-stu-id="32ac7-177">With the hash data merged into one CSV file, you can now proceed to [register the devices](#register-devices-by-using-the-admin-portal).</span></span>


#### <a name="register-devices-by-using-the-admin-portal"></a><span data-ttu-id="32ac7-178">관리 포털을 사용하여 장치 등록</span><span class="sxs-lookup"><span data-stu-id="32ac7-178">Register devices by using the Admin Portal</span></span>

<span data-ttu-id="32ac7-179">[Microsoft 끝점 관리자의](https://endpoint.microsoft.com/) **왼쪽** 탐색 창에서 장치를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-179">In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="32ac7-180">메뉴의 Microsoft Managed Desktop 섹션을 찾아 장치를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="32ac7-180">Look for the Microsoft Managed Desktop section of the menu and select **Devices**.</span></span> <span data-ttu-id="32ac7-181">Microsoft Managed Desktop Devices 작업 영역에서 **+** 장치 등록을 선택합니다. 이 경우 새 장치를 등록하기 위해 플라이인이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-181">In the Microsoft Managed Desktop Devices workspace, Select **+ Register devices**, which opens a fly-in to register new devices.</span></span>

<!-- Update with new picture [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="32ac7-182">다음 단계를 따릅니다:</span><span class="sxs-lookup"><span data-stu-id="32ac7-182">Follow these steps:</span></span>

1. <span data-ttu-id="32ac7-183">파일 **업로드에서** 이전에 만든 CSV 파일의 경로를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-183">In **File upload**, provide a path to the CSV file you created previously.</span></span>

1. <span data-ttu-id="32ac7-184">장치 **등록을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="32ac7-184">Select **Register devices**.</span></span> <span data-ttu-id="32ac7-185">시스템은 등록 보류 중으로 표시된 장치 블레이드의 장치 목록에 **장치를 추가합니다.**</span><span class="sxs-lookup"><span data-stu-id="32ac7-185">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="32ac7-186">등록에는 일반적으로 10분 미만이 걸리며, 등록에 성공하면 장치가 준비된 사용자로 표시되어 사용자가 사용을 시작할 때까지 기다립니다. </span><span class="sxs-lookup"><span data-stu-id="32ac7-186">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for a user to start using.</span></span>


<span data-ttu-id="32ac7-187">기본 페이지에서 장치 등록 진행률을 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-187">You can monitor the progress of device registration on the main page.</span></span> <span data-ttu-id="32ac7-188">보고된 가능한 상태는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-188">Possible states reported there include:</span></span>

| <span data-ttu-id="32ac7-189">시/도</span><span class="sxs-lookup"><span data-stu-id="32ac7-189">State</span></span> | <span data-ttu-id="32ac7-190">설명</span><span class="sxs-lookup"><span data-stu-id="32ac7-190">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="32ac7-191">등록 보류 중</span><span class="sxs-lookup"><span data-stu-id="32ac7-191">Registration Pending</span></span> | <span data-ttu-id="32ac7-192">등록이 아직 완료되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-192">Registration is not done yet.</span></span> <span data-ttu-id="32ac7-193">나중에 다시 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-193">Check back later.</span></span> |
| <span data-ttu-id="32ac7-194">등록 실패</span><span class="sxs-lookup"><span data-stu-id="32ac7-194">Registration failed</span></span> | <span data-ttu-id="32ac7-195">등록을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-195">Registration could not be completed.</span></span> <span data-ttu-id="32ac7-196">자세한 내용은 [장치 등록](#troubleshooting-device-registration) 문제 해결을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="32ac7-196">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="32ac7-197">사용자 준비</span><span class="sxs-lookup"><span data-stu-id="32ac7-197">Ready for user</span></span> | <span data-ttu-id="32ac7-198">등록이 성공하고 이제 디바이스를 사용자에게 전달할 준비가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-198">Registration succeeded and the device is now ready to be delivered to the user.</span></span> <span data-ttu-id="32ac7-199">Microsoft Managed Desktop은 최초 설치를 안내하기 때문에 추가 준비를 할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-199">Microsoft Managed Desktop will guide them through first-time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="32ac7-200">활성</span><span class="sxs-lookup"><span data-stu-id="32ac7-200">Active</span></span> | <span data-ttu-id="32ac7-201">장치가 사용자에게 전달되고 테넌트에 등록되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-201">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="32ac7-202">이는 또한 장치가 정기적으로 사용 중이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-202">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="32ac7-203">비활성</span><span class="sxs-lookup"><span data-stu-id="32ac7-203">Inactive</span></span> | <span data-ttu-id="32ac7-204">장치가 사용자에게 전달되고 테넌트에 등록되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-204">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="32ac7-205">그러나 최근(지난 7일)에는 장치를 사용한 것이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-205">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="32ac7-206">장치 등록 문제 해결</span><span class="sxs-lookup"><span data-stu-id="32ac7-206">Troubleshooting device registration</span></span>

| <span data-ttu-id="32ac7-207">오류 메시지</span><span class="sxs-lookup"><span data-stu-id="32ac7-207">Error message</span></span> | <span data-ttu-id="32ac7-208">세부 정보</span><span class="sxs-lookup"><span data-stu-id="32ac7-208">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="32ac7-209">장치를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-209">Device not found</span></span> | <span data-ttu-id="32ac7-210">제공된 제조업체, 모델 또는 일련 번호에 대한 일치를 찾을 수 없는 경우 이 장치를 등록할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-210">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="32ac7-211">장치 공급업체에 이러한 값을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-211">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="32ac7-212">하드웨어 해시가 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-212">Hardware hash not valid</span></span> | <span data-ttu-id="32ac7-213">이 장치에 대해 제공한 하드웨어 해시의 형식이 올바로 설정되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-213">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="32ac7-214">하드웨어 해시를 다시 확인한 다음 다시 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-214">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="32ac7-215">디바이스가 이미 등록되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-215">Device already registered</span></span> | <span data-ttu-id="32ac7-216">이 장치는 조직에 이미 등록되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-216">This device is already registered to your organization.</span></span> <span data-ttu-id="32ac7-217">추가 작업이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-217">No further action required.</span></span> |
| <span data-ttu-id="32ac7-218">다른 조직에서 클레임한 장치</span><span class="sxs-lookup"><span data-stu-id="32ac7-218">Device claimed by another organization</span></span> | <span data-ttu-id="32ac7-219">이 디바이스는 다른 조직에서 이미 클레임했습니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-219">This device has already been claimed by another organization.</span></span> <span data-ttu-id="32ac7-220">장치 공급업체에 문의하십시오.</span><span class="sxs-lookup"><span data-stu-id="32ac7-220">Check with your device supplier.</span></span> |
| <span data-ttu-id="32ac7-221">예기치 않은 오류</span><span class="sxs-lookup"><span data-stu-id="32ac7-221">Unexpected error</span></span> | <span data-ttu-id="32ac7-222">요청을 자동으로 처리하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-222">Your request could not be automatically processed.</span></span> <span data-ttu-id="32ac7-223">고객 지원에 문의하여 요청 ID를 제공합니다. <requestId></span><span class="sxs-lookup"><span data-stu-id="32ac7-223">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="32ac7-224">이미지 확인</span><span class="sxs-lookup"><span data-stu-id="32ac7-224">Check the image</span></span>

<span data-ttu-id="32ac7-225">디바이스가 Microsoft Managed Desktop 파트너 공급업체에서 제공된 경우 이미지가 정확해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-225">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="32ac7-226">원하는 경우 직접 이미지를 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-226">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="32ac7-227">시작하기 위해 함께 작업하는 Microsoft 담당자에게 연락하여 이미지 적용 위치와 단계를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-227">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="32ac7-228">디바이스 전달</span><span class="sxs-lookup"><span data-stu-id="32ac7-228">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="32ac7-229">사용자에게 장치를 제공하려면 먼저 해당 사용자에게 적절한 라이선스를 획득하고 [적용해야](../get-ready/prerequisites.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-229">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="32ac7-230">모든 라이선스가 적용된 경우 [](get-started-devices.md)사용자가 디바이스를 사용할 수 있도록 준비할 수 있습니다. 그러면 사용자가 디바이스를 시작하고 Windows 설치 환경을 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32ac7-230">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>









