---
title: 직접 기존의 장치 등록
description: 다시 사용 가능한 장치를 등록 하 여 Microsoft Managed Desktop에서 관리할 수 있도록 할 수도 있습니다.
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 6c241894ab50b6b1341b06f47c107c8945fb6e8c
ms.sourcegitcommit: adaedd1418a3bd6e4875b77fd9e008b47e0b2a51
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/18/2020
ms.locfileid: "48104573"
---
# <a name="register-existing-devices-yourself"></a><span data-ttu-id="5318f-103">직접 기존의 장치 등록</span><span class="sxs-lookup"><span data-stu-id="5318f-103">Register existing devices yourself</span></span>

>[!NOTE]
><span data-ttu-id="5318f-104">이 항목에서는 이미 갖고 있는 장치를 다시 사용 하 고 Microsoft Managed Desktop에 등록 하는 단계를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-104">This topic describes the steps for you to re-use devices you already have and register them in Microsoft Managed Desktop.</span></span> <span data-ttu-id="5318f-105">새 장치에 대 한 작업을 수행 하는 경우 대신 [Microsoft Managed Desktop의 새 장치 등록](register-devices-self.md) 에 설명 된 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="5318f-105">If you are working with brand-new devices, follow the steps in [Register new devices in Microsoft Managed Desktop yourself](register-devices-self.md) instead.</span></span>

<span data-ttu-id="5318f-106">파트너에 대 한 프로세스는 [파트너가 장치를 등록 하기 위한 단계](register-devices-partner.md)에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-106">The process for Partners is documented in [Steps for Partners to register devices](register-devices-partner.md).</span></span>

<span data-ttu-id="5318f-107">Microsoft Managed Desktop은 새로운 장치에서 작동 하거나 이미 사용 중인 장치를 다시 사용할 수 있습니다 (다시 이미지 해야 함).</span><span class="sxs-lookup"><span data-stu-id="5318f-107">Microsoft Managed Desktop can work with brand-new devices or you can re-use devices you might already have (which will require that you re-image them).</span></span> <span data-ttu-id="5318f-108">Microsoft Endpoint Manager 포털에서 Microsoft Managed Desktop을 사용 하 여 장치를 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-108">You can register devices with Microsoft Managed Desktop in the Microsoft Endpoint Manager portal.</span></span>

## <a name="prepare-to-register-existing-devices"></a><span data-ttu-id="5318f-109">기존 장치 등록 준비</span><span class="sxs-lookup"><span data-stu-id="5318f-109">Prepare to register existing devices</span></span>


<span data-ttu-id="5318f-110">기존 장치를 등록 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-110">To register existing devices, follow these steps:</span></span>

1. [<span data-ttu-id="5318f-111">각 장치에 대 한 하드웨어 해시를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-111">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="5318f-112">해시 데이터 병합</span><span class="sxs-lookup"><span data-stu-id="5318f-112">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="5318f-113">[Microsoft Managed Desktop에서 장치를 등록](#register-devices-by-using-the-admin-portal)합니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-113">[Register the devices in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).</span></span>
4. [<span data-ttu-id="5318f-114">이미지가 올바른지 다시 한 번 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-114">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="5318f-115">장치 배달</span><span class="sxs-lookup"><span data-stu-id="5318f-115">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="5318f-116">하드웨어 해시 가져오기</span><span class="sxs-lookup"><span data-stu-id="5318f-116">Obtain the hardware hash</span></span>

<span data-ttu-id="5318f-117">Microsoft Managed Desktop은 해당 하드웨어 해시를 참조 하 여 각 장치를 고유 하 게 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-117">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="5318f-118">이미 사용 중인 장치에서이 정보를 가져올 수 있는 옵션은 다음 네 가지입니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-118">You have four options for getting this information from devices you're already using:</span></span>

- <span data-ttu-id="5318f-119">OEM 공급자에 게 하드웨어 해시를 포함 하는 AutoPilot 등록 파일에 대해 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="5318f-119">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="5318f-120">[Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager)에서 정보를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-120">Collect information in [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager).</span></span>
- <span data-ttu-id="5318f-121">[Active Directory](#active-directory-powershell-script-method) 를 사용 하거나 각 장치에서 [수동으로](#manual-powershell-script-method) Windows PowerShell 스크립트를 실행 하 고 파일에서 결과를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-121">Run a Windows PowerShell script--either by using [Active Directory](#active-directory-powershell-script-method) or [manually](#manual-powershell-script-method) on each device--and collect the results in a file.</span></span>
- <span data-ttu-id="5318f-122">각 장치를 시작 하지만 Windows 설치 환경을 완료 하지 않고 [이동식 플래시 드라이브에서 해시를 수집](#flash-drive-method)합니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-122">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="5318f-123">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="5318f-123">Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="5318f-124">Microsoft Endpoint Configuration Manager를 사용 하 여 Microsoft Managed Desktop에 등록 하려는 기존 장치의 하드웨어 해시를 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-124">You can use Microsoft Endpoint Configuration Manager to collect the hardware hashes from existing devices that you want to register with Microsoft Managed Desktop.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5318f-125">이 정보를 가져올 장치에는 Windows 10, 버전 1703 이상을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-125">Any devices you want to get this information for must be running Windows 10, version 1703 or later.</span></span> 

<span data-ttu-id="5318f-126">이러한 필수 구성 요소를 모두 충족 하면 다음 단계를 수행 하 여 정보를 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-126">If you've met all these prerequisites, you're ready to collect the information by following these steps:</span></span>

1. <span data-ttu-id="5318f-127">Configuration Manager 콘솔에서 **모니터링**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-127">In the Configuration Manager console, select **Monitoring**.</span></span> 
2. <span data-ttu-id="5318f-128">모니터링 작업 영역에서 **보고** 노드를 확장 하 고 **보고서**를 확장 한 다음 **하드웨어-일반** 노드를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-128">In the Monitoring workspace, expand the **Reporting** node, expand **Reports**, and select the **Hardware - General** node.</span></span> 
3. <span data-ttu-id="5318f-129">보고서를 실행 하 고 **Windows Autopilot 장치 정보**를 검색 한 다음 결과를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-129">Run the report, **Windows Autopilot Device Information**, and view the results.</span></span>
4. <span data-ttu-id="5318f-130">보고서 뷰어에서 **내보내기** 아이콘을 선택 하 고 **CSV (쉼표로 분리)** 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-130">In the report viewer, select the **Export** icon, and choose the **CSV (comma-delimited)** option.</span></span>
5. <span data-ttu-id="5318f-131">파일을 저장 한 후에는 Microsoft Managed Desktop에 등록할 장치에만 결과를 필터링 하 고 Microsoft Managed Desktop에 데이터를 업로드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-131">After saving the file, you will need to filter results to just those devices you plan to register with Microsoft Managed Desktop and upload the data to Microsoft Managed Desktop.</span></span> <span data-ttu-id="5318f-132">Microsoft Endpoint Manager를 열고 **장치** 메뉴로 이동한 다음 Microsoft Managed Desktop 섹션을 찾아 **장치**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-132">Open Microsoft Endpoint Manager and navigate to the **Devices** menu, then look for Microsoft Managed Desktop section and select **Devices**.</span></span> <span data-ttu-id="5318f-133">새 장치를 등록 하기 위해 날아오기/끄기 **장치** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-133">Select **+ Register devices** which opens a fly-in to register new devices.</span></span>


<span data-ttu-id="5318f-134">자세한 내용은 [Admin Portal을 사용 하 여 장치 등록](#register-devices-by-using-the-admin-portal) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5318f-134">Refer to [Register devices by using the Admin Portal](#register-devices-by-using-the-admin-portal) for more information.</span></span>


#### <a name="active-directory-powershell-script-method"></a><span data-ttu-id="5318f-135">Active Directory PowerShell 스크립트 메서드</span><span class="sxs-lookup"><span data-stu-id="5318f-135">Active Directory PowerShell script method</span></span>

<span data-ttu-id="5318f-136">Active Directory 환경에서는 PowerShell cmdlet을 사용 하 여 `Get-WindowsAutoPilotInfo` WinRM을 사용 하 여 Active Directory 그룹의 장치에서 정보를 원격으로 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-136">In an Active Directory environment, you can use the `Get-WindowsAutoPilotInfo` PowerShell cmdlet to remotely collect the information from devices in Active Directory Groups by using WinRM.</span></span> <span data-ttu-id="5318f-137">또한이 cmdlet을 사용 하 여 `Get-AD Computer` 카탈로그에 포함 된 특정 하드웨어 모델 이름에 대 한 필터링 된 결과를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-137">You can also use the `Get-AD Computer` cmdlet and get filtered results for a specific hardware model names included in the catalog.</span></span> <span data-ttu-id="5318f-138">이 작업을 수행 하려면 먼저 다음 필수 구성 요소를 확인 한 다음 단계를 진행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-138">To do this, first confirm these prerequisites, and then proceed with the steps:</span></span>

- <span data-ttu-id="5318f-139">WinRM을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-139">WinRM is enabled.</span></span>
- <span data-ttu-id="5318f-140">등록 하려는 장치가 네트워크에서 활성 상태 (즉, 연결이 끊어지거나 꺼져 있지 않음)입니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-140">The devices you want to register are active on the network (that is, they are not disconnected or turned off).</span></span>
- <span data-ttu-id="5318f-141">장치에서 원격으로 실행할 수 있는 권한이 있는 도메인 자격 증명 매개 변수가 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-141">Make sure you have a domain credential parameter that has permission to execute remotely on the devices.</span></span>
- <span data-ttu-id="5318f-142">Windows 방화벽에서 WMI 액세스를 허용 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-142">Make sure that Windows Firewall allows access to WMI.</span></span> <span data-ttu-id="5318f-143">이 작업을 수행 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-143">To do that, follow these steps:</span></span>

    1. <span data-ttu-id="5318f-144">**Windows Defender 방화벽** 제어판을 열고 **windows defender 방화벽을 통해 앱 또는 기능 허용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-144">Open the **Windows Defender Firewall** control panel and select **Allow an app or feature through Windows Defender Firewall**.</span></span>
    
    2. <span data-ttu-id="5318f-145">목록에서 **WMI (Windows Management Instrumentation)** 를 찾고 **개인 및 공용**모두에 대해이 기능을 사용 하도록 설정 하 고 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-145">Find **Windows Management Instrumentation (WMI)** in the list, enable for both **Private and Public**, and then select **OK**.</span></span>

1.  <span data-ttu-id="5318f-146">관리 권한으로 PowerShell 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-146">Open a PowerShell prompt with administrative rights.</span></span>

2.  <span data-ttu-id="5318f-147">다음 스크립트 중 *하나* 를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-147">Run *either one* of these scripts:</span></span>

    ```powershell
    Install-script -name Get-WindowsAutoPilotInfo 
    #example one – leverage Get-ADComputer to enumerate devices 
    Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname>
    ```

    ```powershell 
    #example two – target specific devices: 
    Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
    ```

3. <span data-ttu-id="5318f-148">장치에 대 한 항목이 있을 수 있는 모든 디렉터리에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-148">Access any directories where there might be entries for the devices.</span></span> <span data-ttu-id="5318f-149">Windows Server Active Directory 도메인 서비스 및 Azure Active Directory를 포함 하 여 *모든* 디렉터리에서 각 장치에 대 한 항목을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-149">Remove entries for each device from *all* directories, including Windows Server Active Directory Domain Services and Azure Active Directory.</span></span> <span data-ttu-id="5318f-150">이 제거 작업을 완료 하는 데 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-150">Be aware that this removal could take a few hours to completely process.</span></span>

4. <span data-ttu-id="5318f-151">장치에 대 한 항목이 있을 수 있는 관리 서비스에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-151">Access management services where there might be entries for the devices.</span></span> <span data-ttu-id="5318f-152">Microsoft Endpoint Configuration Manager, Microsoft Intune 및 Windows Autopilot를 비롯 한 *모든* 관리 서비스에서 각 장치에 대 한 항목을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-152">Remove entries for each device from *all* management services, including Microsoft Endpoint Configuration Manager, Microsoft Intune, and Windows Autopilot.</span></span> <span data-ttu-id="5318f-153">이 제거 작업을 완료 하는 데 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-153">Be aware that this removal could take a few hours to completely process.</span></span>

<span data-ttu-id="5318f-154">이제 [장치 등록](#register-devices-by-using-the-admin-portal)을 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-154">Now you can proceed to [register devices](#register-devices-by-using-the-admin-portal).</span></span>

#### <a name="manual-powershell-script-method"></a><span data-ttu-id="5318f-155">PowerShell 수동 스크립트 방법</span><span class="sxs-lookup"><span data-stu-id="5318f-155">Manual PowerShell script method</span></span>

1.  <span data-ttu-id="5318f-156">관리 권한으로 PowerShell 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-156">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="5318f-157">실행 `Install-Script -Name Get-WindowsAutoPilotInfo`</span><span class="sxs-lookup"><span data-stu-id="5318f-157">Run `Install-Script -Name Get-WindowsAutoPilotInfo`</span></span>
3.  <span data-ttu-id="5318f-158">실행 `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="5318f-158">Run `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
4. [<span data-ttu-id="5318f-159">해시 데이터를 병합 합니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-159">Merge the hash data.</span></span>](#merge-hash-data)

#### <a name="flash-drive-method"></a><span data-ttu-id="5318f-160">Flash drive 메서드</span><span class="sxs-lookup"><span data-stu-id="5318f-160">Flash drive method</span></span>

1. <span data-ttu-id="5318f-161">등록 중인 장치 이외의 디바이스에서 USB 드라이브를 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-161">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="5318f-162">관리 권한으로 PowerShell 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-162">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="5318f-163">실행 `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="5318f-163">Run `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="5318f-164">등록 중인 디바이스를 켜면 *설치 환경이 시작 되지*않습니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-164">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="5318f-165">실수로 설치 환경을 시작한 경우 장치를 초기화 하거나 다시 이미지로 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-165">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="5318f-166">USB 드라이브를 삽입 한 다음 SHIFT + F10 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-166">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="5318f-167">관리 권한으로 PowerShell 프롬프트를 열고를 실행 `cd <pathToUsb>` 합니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-167">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="5318f-168">실행 `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="5318f-168">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="5318f-169">실행 `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="5318f-169">Run `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="5318f-170">USB 드라이브를 제거한 다음 다음을 실행 하 여 장치를 종료 합니다. `shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="5318f-170">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>
10. [<span data-ttu-id="5318f-171">해시 데이터를 병합 합니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-171">Merge the hash data.</span></span>](#merge-hash-data)

>[!IMPORTANT]
><span data-ttu-id="5318f-172">등록을 완료 한 후 다시 등록할 때까지 디바이스에 전원을 공급 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="5318f-172">Do not power on the device you are registering again until you've completed registration for it.</span></span> 



### <a name="merge-hash-data"></a><span data-ttu-id="5318f-173">해시 데이터 병합</span><span class="sxs-lookup"><span data-stu-id="5318f-173">Merge hash data</span></span>

<span data-ttu-id="5318f-174">수동 PowerShell 또는 플래시 드라이브 방법으로 하드웨어 해시 데이터를 수집한 경우에는 CSV 파일의 데이터를 단일 파일로 결합 하 여 등록을 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-174">If you collected the hardware hash data by the manual PowerShell or flash drive methods, you now need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="5318f-175">다음과 같은 샘플 PowerShell 스크립트를 통해이를 쉽게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-175">Here's a sample PowerShell script to make this easy:</span></span>

```powershell
Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv
```

<span data-ttu-id="5318f-176">해시 데이터를 하나의 CSV 파일에 병합 하 여 이제 [장치 등록](#register-devices-by-using-the-admin-portal)을 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-176">With the hash data merged into one CSV file, you can now proceed to [register the devices](#register-devices-by-using-the-admin-portal).</span></span>


#### <a name="register-devices-by-using-the-admin-portal"></a><span data-ttu-id="5318f-177">관리 포털을 사용 하 여 장치 등록</span><span class="sxs-lookup"><span data-stu-id="5318f-177">Register devices by using the Admin Portal</span></span>

<span data-ttu-id="5318f-178">[Microsoft Endpoint Manager](https://endpoint.microsoft.com/)의 왼쪽 탐색 창에서 **장치** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-178">In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="5318f-179">메뉴의 Microsoft Managed Desktop 섹션을 찾아 **장치**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-179">Look for the Microsoft Managed Desktop section of the menu and select **Devices**.</span></span> <span data-ttu-id="5318f-180">Microsoft Managed Desktop Devices 작업 영역에서 **+ register Devices** 를 선택 하 여 새 장치를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-180">In the Microsoft Managed Desktop Devices workspace, Select **+ Register devices** which opens a fly-in to register new devices.</span></span>

<!-- Update with new picture [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="5318f-181">다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-181">Follow these steps:</span></span>

1. <span data-ttu-id="5318f-182">**파일 업로드**에서 이전에 만든 CSV 파일의 경로를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-182">In **File upload**, provide a path to the CSV file you created previously.</span></span>

1. <span data-ttu-id="5318f-183">**장치 등록**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-183">Select **Register devices**.</span></span> <span data-ttu-id="5318f-184">시스템이 장치 **블레이드에서**장치 목록에 추가 되 고 **AutopilotRegistrationRequested**로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-184">The system will add the devices to your list of devices on the **Devices blade**, marked as **AutopilotRegistrationRequested**.</span></span> <span data-ttu-id="5318f-185">등록은 일반적으로 10 분 미만이 걸리고, 성공적으로 완료 되 면 장치에 **사용자가** 사용할 준비가 된 것으로 표시 되 고 사용자가 사용을 시작할 때까지 대기 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-185">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for a user to start using.</span></span>


<span data-ttu-id="5318f-186">기본 페이지에서 장치 등록의 진행 상태를 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-186">You can monitor the progress of device registration on the main page.</span></span> <span data-ttu-id="5318f-187">다음과 같은 가능한 상태가 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-187">Possible states reported there include:</span></span>

| <span data-ttu-id="5318f-188">시/도</span><span class="sxs-lookup"><span data-stu-id="5318f-188">State</span></span> | <span data-ttu-id="5318f-189">설명</span><span class="sxs-lookup"><span data-stu-id="5318f-189">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="5318f-190">AutopilotRegistrationRequested</span><span class="sxs-lookup"><span data-stu-id="5318f-190">AutopilotRegistrationRequested</span></span> | <span data-ttu-id="5318f-191">등록이 아직 완료 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-191">Registration is not done yet.</span></span> <span data-ttu-id="5318f-192">나중에 다시 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-192">Check back later.</span></span> |
| <span data-ttu-id="5318f-193">등록 실패</span><span class="sxs-lookup"><span data-stu-id="5318f-193">Registration failed</span></span> | <span data-ttu-id="5318f-194">등록을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-194">Registration could not be completed.</span></span> <span data-ttu-id="5318f-195">자세한 내용은 [장치 등록 문제 해결](#troubleshooting-device-registration) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5318f-195">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="5318f-196">사용자 준비</span><span class="sxs-lookup"><span data-stu-id="5318f-196">Ready for user</span></span> | <span data-ttu-id="5318f-197">등록을 완료 했으며 이제 장치를 사용자에 게 배달할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-197">Registration succeeded and the device is now ready to be delivered to the user.</span></span> <span data-ttu-id="5318f-198">Microsoft Managed Desktop은 처음 설정할 때 가이드를 제공 하므로 추가 준비를 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-198">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="5318f-199">활성</span><span class="sxs-lookup"><span data-stu-id="5318f-199">Active</span></span> | <span data-ttu-id="5318f-200">장치가 사용자에 게 배달 되었으며 테 넌 트에 등록 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-200">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="5318f-201">또한 장치를 정기적으로 사용 하는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-201">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="5318f-202">있었던</span><span class="sxs-lookup"><span data-stu-id="5318f-202">Inactive</span></span> | <span data-ttu-id="5318f-203">장치가 사용자에 게 배달 되었으며 테 넌 트에 등록 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-203">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="5318f-204">그러나 최근에 최근 7 일 이내에 장치를 사용 하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-204">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="5318f-205">장치 등록 문제 해결</span><span class="sxs-lookup"><span data-stu-id="5318f-205">Troubleshooting device registration</span></span>

| <span data-ttu-id="5318f-206">오류 메시지</span><span class="sxs-lookup"><span data-stu-id="5318f-206">Error message</span></span> | <span data-ttu-id="5318f-207">세부 정보</span><span class="sxs-lookup"><span data-stu-id="5318f-207">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="5318f-208">장치를 찾을 수 없음</span><span class="sxs-lookup"><span data-stu-id="5318f-208">Device not found</span></span> | <span data-ttu-id="5318f-209">제공 된 제조업체, 모델 또는 일련 번호에 대해 일치 하는 항목을 찾을 수 없기 때문에이 장치를 등록할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-209">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="5318f-210">장치 공급자에서 이러한 값을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-210">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="5318f-211">하드웨어 해시가 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-211">Hardware hash not valid</span></span> | <span data-ttu-id="5318f-212">이 장치에 대해 제공한 하드웨어 해시가 올바르게 포맷 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-212">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="5318f-213">하드웨어 해시를 두 번 확인 한 다음 다시 제출 합니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-213">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="5318f-214">장치가 이미 등록 됨</span><span class="sxs-lookup"><span data-stu-id="5318f-214">Device already registered</span></span> | <span data-ttu-id="5318f-215">이 장치는 이미 조직에 등록 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-215">This device is already registered to your organization.</span></span> <span data-ttu-id="5318f-216">추가 작업이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-216">No further action required.</span></span> |
| <span data-ttu-id="5318f-217">다른 조직에서 요구 하는 장치</span><span class="sxs-lookup"><span data-stu-id="5318f-217">Device claimed by another organization</span></span> | <span data-ttu-id="5318f-218">이 장치는 다른 조직에서 이미 요구 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-218">This device has already been claimed by another organization.</span></span> <span data-ttu-id="5318f-219">장치 공급자에 게 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="5318f-219">Check with your device supplier.</span></span> |
| <span data-ttu-id="5318f-220">예기치 않은 오류</span><span class="sxs-lookup"><span data-stu-id="5318f-220">Unexpected error</span></span> | <span data-ttu-id="5318f-221">요청을 자동으로 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-221">Your request could not be automatically processed.</span></span> <span data-ttu-id="5318f-222">지원 서비스에 문의 하 여 요청 ID를 제공 합니다. <requestId></span><span class="sxs-lookup"><span data-stu-id="5318f-222">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="5318f-223">이미지 확인</span><span class="sxs-lookup"><span data-stu-id="5318f-223">Check the image</span></span>

<span data-ttu-id="5318f-224">장치가 Microsoft 관리 되는 데스크톱 파트너 공급자 로부터 온 것 이라면 이미지가 정확 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-224">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="5318f-225">원하는 경우 이미지를 직접 적용 하는 것도 환영 합니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-225">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="5318f-226">시작 하려면 사용 중인 Microsoft 담당자에 게 문의 하 여 이미지를 적용할 위치와 단계를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-226">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="5318f-227">장치 배달</span><span class="sxs-lookup"><span data-stu-id="5318f-227">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5318f-228">사용자에 게 디바이스를 전달 하기 전에 해당 사용자에 대 한 [적절 한 라이선스](../get-ready/prerequisites.md) 를 확보 하 고 적용 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-228">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="5318f-229">모든 라이선스가 적용 되 면 [사용자가 장치를 사용할 준비가](get-started-devices.md)되 면 사용자가 장치를 시작 하 고 Windows 설치 환경을 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5318f-229">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>









