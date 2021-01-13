---
title: 직접 새 장치 등록
description: Microsoft Managed Desktop에서 관리할 수 있도록 직접 디바이스 등록
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: df6013f2f7fec32e79557a82f9b56fe4ad487786
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840684"
---
# <a name="register-new-devices-yourself"></a><span data-ttu-id="cad76-103">직접 새 장치 등록</span><span class="sxs-lookup"><span data-stu-id="cad76-103">Register new devices yourself</span></span>

<span data-ttu-id="cad76-104">Microsoft Managed Desktop은 새로운 디바이스에서 작동하거나 이미 있을 수 있는 장치를 다시 사용할 수 있습니다(이 경우 다시 이미 이미 있는 디바이스를 다시 사용해야 합니다).</span><span class="sxs-lookup"><span data-stu-id="cad76-104">Microsoft Managed Desktop can work with brand-new devices or you can reuse devices you might already have (which will require that you reimage them).</span></span> <span data-ttu-id="cad76-105">Microsoft Endpoint Manager 포털에서 Microsoft Managed Desktop에 장치를 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cad76-105">You can register devices with Microsoft Managed Desktop in the Microsoft Endpoint Manager portal.</span></span>

> [!NOTE]
> <span data-ttu-id="cad76-106">파트너와 협력하여 디바이스를 얻습니까?</span><span class="sxs-lookup"><span data-stu-id="cad76-106">Working with a partner to obtain devices?</span></span> <span data-ttu-id="cad76-107">그렇다면 하드웨어 해시를 사용할 때 걱정할 필요가 없습니다. 이러한 경우를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="cad76-107">If so, you don't need to worry about getting the hardware hashes; they'll take care of that for you.</span></span> <span data-ttu-id="cad76-108">파트너가 파트너 센터에서 사용자와 관계를 [설정하는지 확인](https://partner.microsoft.com/dashboard)</span><span class="sxs-lookup"><span data-stu-id="cad76-108">Make sure your partner establishes a relationship with you at the [Partner Center](https://partner.microsoft.com/dashboard).</span></span> <span data-ttu-id="cad76-109">파트너는 파트너 센터 도움말에서 자세한 [정보를 볼 수 있습니다.](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer)</span><span class="sxs-lookup"><span data-stu-id="cad76-109">Your partner can learn more at [Partner Center help](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer).</span></span> <span data-ttu-id="cad76-110">이 관계가 설정되면 파트너는 단순히 사용자 대신 디바이스를 등록합니다. 추가 작업이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cad76-110">Once this relationship established, your partner will simply register devices on your behalf – no further action required from you.</span></span> <span data-ttu-id="cad76-111">세부 정보를 보거나 파트너에게 질문이 있는 경우 파트너가 디바이스를 등록하는 [단계를 참조하세요.](register-devices-partner.md)</span><span class="sxs-lookup"><span data-stu-id="cad76-111">If you want to see the details, or your partner has questions, see [Steps for Partners to register devices](register-devices-partner.md).</span></span> <span data-ttu-id="cad76-112">디바이스가 등록된 후 이미지를 확인하고 [](#check-the-image) 사용자에게 디바이스를 [](#deliver-the-device) 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cad76-112">Once the devices are registered, you can proceed with [checking the image](#check-the-image) and [delivering the devices](#deliver-the-device) to your users.</span></span>

## <a name="prepare-to-register-brand-new-devices"></a><span data-ttu-id="cad76-113">새 장치 등록 준비</span><span class="sxs-lookup"><span data-stu-id="cad76-113">Prepare to register brand-new devices</span></span>


<span data-ttu-id="cad76-114">새 장치를 사용할 수 있는 경우 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="cad76-114">Once you have the new devices in hand, you'll follow these steps:</span></span>

1. [<span data-ttu-id="cad76-115">각 디바이스에 대한 하드웨어 해시를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="cad76-115">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="cad76-116">해시 데이터 병합</span><span class="sxs-lookup"><span data-stu-id="cad76-116">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="cad76-117">[Microsoft Managed Desktop에서 디바이스를 등록합니다.](#register-devices-by-using-the-admin-portal)</span><span class="sxs-lookup"><span data-stu-id="cad76-117">[Register the devices in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).</span></span>
4. [<span data-ttu-id="cad76-118">이미지가 올바른지 다시 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="cad76-118">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="cad76-119">디바이스 전달</span><span class="sxs-lookup"><span data-stu-id="cad76-119">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="cad76-120">하드웨어 해시 획득</span><span class="sxs-lookup"><span data-stu-id="cad76-120">Obtain the hardware hash</span></span>

<span data-ttu-id="cad76-121">Microsoft Managed Desktop은 하드웨어 해시를 참조하여 각 장치를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="cad76-121">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="cad76-122">이 정보를 수집하는 세 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cad76-122">You have three options for getting this information:</span></span>

- <span data-ttu-id="cad76-123">OEM 공급업체에 하드웨어 해시를 포함할 AutoPilot 등록 파일을 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="cad76-123">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="cad76-124">각 [Windows PowerShell 스크립트를](#powershell-script-method) 실행하고 파일에 결과를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="cad76-124">Run a [Windows PowerShell script](#powershell-script-method) on each device and collect the results in a file.</span></span>
- <span data-ttu-id="cad76-125">각 디바이스를 시작하지만 Windows 설치 환경을 완료하지는 않습니다. 이동식 플래시 드라이브에서 [해시를 수집합니다.](#flash-drive-method)</span><span class="sxs-lookup"><span data-stu-id="cad76-125">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="powershell-script-method"></a><span data-ttu-id="cad76-126">PowerShell 스크립트 메서드</span><span class="sxs-lookup"><span data-stu-id="cad76-126">PowerShell script method</span></span>

<span data-ttu-id="cad76-127">PowerShell 갤러리 [Get-WindowsAutoPilotInfo.ps1](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) PowerShell 스크립트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cad76-127">You can use the [Get-WindowsAutoPilotInfo.ps1](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) PowerShell script on the PowerShell Gallery website.</span></span> <span data-ttu-id="cad76-128">장치 식별 및 하드웨어 해시에 대한 자세한 내용은 [Windows Autopilot에 장치 추가를 참조하세요.](https://docs.microsoft.com/mem/autopilot/add-devices#device-identification)</span><span class="sxs-lookup"><span data-stu-id="cad76-128">For more information about device identification and hardware hash, see [Adding devices to Windows Autopilot](https://docs.microsoft.com/mem/autopilot/add-devices#device-identification).</span></span>

1.  <span data-ttu-id="cad76-129">관리 권한으로 PowerShell 프롬프트를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cad76-129">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="cad76-130">실행 `Install-Script -Name Get-WindowsAutoPilotInfo`</span><span class="sxs-lookup"><span data-stu-id="cad76-130">Run `Install-Script -Name Get-WindowsAutoPilotInfo`</span></span>
3.  <span data-ttu-id="cad76-131">실행 `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="cad76-131">Run `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
4.  <span data-ttu-id="cad76-132">후속 무제한 스크립트가 실행되지 않도록 `powershell -ExecutionPolicy restricted` 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cad76-132">Run `powershell -ExecutionPolicy restricted` to prevent subsequent unrestricted scripts from running.</span></span>


#### <a name="flash-drive-method"></a><span data-ttu-id="cad76-133">플래시 드라이브 방법</span><span class="sxs-lookup"><span data-stu-id="cad76-133">Flash drive method</span></span>

1. <span data-ttu-id="cad76-134">등록할 장치 외의 디바이스에 USB 드라이브를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="cad76-134">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="cad76-135">관리 권한으로 PowerShell 프롬프트를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cad76-135">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="cad76-136">실행 `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="cad76-136">Run `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="cad76-137">등록할 디바이스를 켜지만 설치 *환경을 시작하지는 않습니다.*</span><span class="sxs-lookup"><span data-stu-id="cad76-137">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="cad76-138">실수로 설치 환경을 시작한 경우 장치를 초기화하거나 다시 이미지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad76-138">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="cad76-139">USB 드라이브를 삽입한 다음 Shift + F10을 누를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cad76-139">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="cad76-140">관리 권한으로 PowerShell 프롬프트를 연 다음 `cd <pathToUsb>` 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cad76-140">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="cad76-141">실행 `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="cad76-141">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="cad76-142">실행 `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="cad76-142">Run `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="cad76-143">USB 드라이브를 제거한 다음 실행하여 디바이스를 종료합니다. `shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="cad76-143">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>

>[!IMPORTANT]
><span data-ttu-id="cad76-144">등록을 완료할 때까지 다시 등록하는 디바이스에서 전원을 공급하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cad76-144">Do not power on the device you are registering again until you've completed registration for it.</span></span> 


### <a name="merge-hash-data"></a><span data-ttu-id="cad76-145">해시 데이터 병합</span><span class="sxs-lookup"><span data-stu-id="cad76-145">Merge hash data</span></span>

<span data-ttu-id="cad76-146">등록을 완료하려면 CSV 파일의 데이터를 단일 파일로 결합해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad76-146">You'll need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="cad76-147">다음은 쉽게 사용할 수 있도록 하는 샘플 PowerShell 스크립트입니다.</span><span class="sxs-lookup"><span data-stu-id="cad76-147">Here's a sample PowerShell script to make it easy:</span></span>

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`


#### <a name="register-devices-by-using-the-admin-portal"></a><span data-ttu-id="cad76-148">관리 포털을 사용하여 장치 등록</span><span class="sxs-lookup"><span data-stu-id="cad76-148">Register devices by using the Admin Portal</span></span>

<span data-ttu-id="cad76-149">[Microsoft Endpoint Manager의](https://endpoint.microsoft.com/)왼쪽 탐색 창에서 디바이스를 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="cad76-149">In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="cad76-150">메뉴의 Microsoft Managed Desktop 섹션을 찾아 장치를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="cad76-150">Look for the Microsoft Managed Desktop section of the menu and select **Devices**.</span></span> <span data-ttu-id="cad76-151">Microsoft Managed Desktop Devices 작업 영역에서 **새 장치를** 등록하기 위해 플라이인을 여는 + 장치 등록을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cad76-151">In the Microsoft Managed Desktop Devices workspace, Select **+ Register devices**, which opens a fly-in to register new devices.</span></span>

<!-- [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="cad76-152">아래 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="cad76-152">Follow these steps:</span></span>

1. <span data-ttu-id="cad76-153">파일 **업로드에서** 이전에 만든 CSV 파일의 경로를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cad76-153">In **File upload**, provide a path to the CSV file you created previously.</span></span>
3. <span data-ttu-id="cad76-154">장치 **등록을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="cad76-154">Select **Register devices**.</span></span> <span data-ttu-id="cad76-155">시스템은 등록 보류 중으로 표시된 디바이스의 장치 목록에 **장치를 추가합니다.**</span><span class="sxs-lookup"><span data-stu-id="cad76-155">The system will add the devices to your list of devices on **Devices**, marked as **Registration Pending**.</span></span> <span data-ttu-id="cad76-156">등록에는 일반적으로 10분 미만이 걸리며, 성공하면 장치가 준비된 것으로 표시되어 사용자가 사용을 시작할 때까지 기다립니다. </span><span class="sxs-lookup"><span data-stu-id="cad76-156">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for a user to start using.</span></span>


<span data-ttu-id="cad76-157">주 페이지에서 장치 등록의 진행률을 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cad76-157">You can monitor the progress of device registration on the main page.</span></span> <span data-ttu-id="cad76-158">보고된 가능한 상태는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cad76-158">Possible states reported there include:</span></span>

| <span data-ttu-id="cad76-159">시/도</span><span class="sxs-lookup"><span data-stu-id="cad76-159">State</span></span> | <span data-ttu-id="cad76-160">설명</span><span class="sxs-lookup"><span data-stu-id="cad76-160">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="cad76-161">등록 보류 중</span><span class="sxs-lookup"><span data-stu-id="cad76-161">Registration Pending</span></span> | <span data-ttu-id="cad76-162">등록이 아직 완료되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="cad76-162">Registration is not done yet.</span></span> <span data-ttu-id="cad76-163">나중에 다시 확인</span><span class="sxs-lookup"><span data-stu-id="cad76-163">Check back later.</span></span> |
| <span data-ttu-id="cad76-164">등록 실패</span><span class="sxs-lookup"><span data-stu-id="cad76-164">Registration failed</span></span> | <span data-ttu-id="cad76-165">등록을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cad76-165">Registration could not be completed.</span></span> <span data-ttu-id="cad76-166">자세한 내용은 [장치](#troubleshooting-device-registration) 등록 문제 해결을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cad76-166">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="cad76-167">사용자 준비</span><span class="sxs-lookup"><span data-stu-id="cad76-167">Ready for user</span></span> | <span data-ttu-id="cad76-168">등록이 성공하고 이제 디바이스를 사용자에게 전달할 준비가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cad76-168">Registration succeeded and the device is now ready to be delivered to the user.</span></span> <span data-ttu-id="cad76-169">Microsoft Managed Desktop은 최초 설치를 안내하기 때문에 추가 준비를 할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cad76-169">Microsoft Managed Desktop will guide them through first-time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="cad76-170">활성</span><span class="sxs-lookup"><span data-stu-id="cad76-170">Active</span></span> | <span data-ttu-id="cad76-171">장치가 사용자에게 전달되고 테넌트에 등록되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cad76-171">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="cad76-172">이 상태는 장치가 정기적으로 사용 중이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad76-172">This state also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="cad76-173">비활성</span><span class="sxs-lookup"><span data-stu-id="cad76-173">Inactive</span></span> | <span data-ttu-id="cad76-174">장치가 사용자에게 전달되고 테넌트에 등록되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cad76-174">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="cad76-175">그러나 최근(지난 7일)에는 장치를 사용한 것이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cad76-175">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="cad76-176">장치 등록 문제 해결</span><span class="sxs-lookup"><span data-stu-id="cad76-176">Troubleshooting device registration</span></span>

| <span data-ttu-id="cad76-177">오류 메시지</span><span class="sxs-lookup"><span data-stu-id="cad76-177">Error message</span></span> | <span data-ttu-id="cad76-178">세부 정보</span><span class="sxs-lookup"><span data-stu-id="cad76-178">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="cad76-179">디바이스를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cad76-179">Device not found</span></span> | <span data-ttu-id="cad76-180">제공된 제조업체, 모델 또는 일련 번호에 대한 일치를 찾을 수 없는 경우 이 장치를 등록할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cad76-180">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="cad76-181">장치 공급업체에 이러한 값을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="cad76-181">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="cad76-182">하드웨어 해시가 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cad76-182">Hardware hash not valid</span></span> | <span data-ttu-id="cad76-183">이 장치에 대해 제공한 하드웨어 해시의 형식이 올바로 지정되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="cad76-183">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="cad76-184">하드웨어 해시를 다시 확인한 다음 다시 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="cad76-184">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="cad76-185">디바이스가 이미 등록되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cad76-185">Device already registered</span></span> | <span data-ttu-id="cad76-186">이 장치는 이미 조직에 등록되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cad76-186">This device is already registered to your organization.</span></span> <span data-ttu-id="cad76-187">추가 작업이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cad76-187">No further action required.</span></span> |
| <span data-ttu-id="cad76-188">다른 조직에서 클레임된 장치</span><span class="sxs-lookup"><span data-stu-id="cad76-188">Device claimed by another organization</span></span> | <span data-ttu-id="cad76-189">이 디바이스는 다른 조직에서 이미 클레임했습니다.</span><span class="sxs-lookup"><span data-stu-id="cad76-189">This device has already been claimed by another organization.</span></span> <span data-ttu-id="cad76-190">장치 공급업체에 문의하십시오.</span><span class="sxs-lookup"><span data-stu-id="cad76-190">Check with your device supplier.</span></span> |
| <span data-ttu-id="cad76-191">예기치 않은 오류</span><span class="sxs-lookup"><span data-stu-id="cad76-191">Unexpected error</span></span> | <span data-ttu-id="cad76-192">요청을 자동으로 처리하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="cad76-192">Your request could not be automatically processed.</span></span> <span data-ttu-id="cad76-193">고객 지원에 문의하여 요청 ID를 제공합니다. <requestId></span><span class="sxs-lookup"><span data-stu-id="cad76-193">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="cad76-194">이미지 확인</span><span class="sxs-lookup"><span data-stu-id="cad76-194">Check the image</span></span>

<span data-ttu-id="cad76-195">디바이스가 Microsoft Managed Desktop 파트너 공급업체에서 제공된 경우 이미지가 정확해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad76-195">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="cad76-196">원하는 경우 직접 이미지를 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cad76-196">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="cad76-197">시작을 위해 함께 작업하는 Microsoft 담당자에게 연락하여 이미지 적용 위치와 단계를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cad76-197">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="cad76-198">디바이스 전달</span><span class="sxs-lookup"><span data-stu-id="cad76-198">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cad76-199">디바이스를 사용자에게 제공하려면 먼저 해당 사용자에게 적절한 라이선스를 획득하고 [적용해야](../get-ready/prerequisites.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad76-199">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="cad76-200">모든 라이선스가 적용된 경우 [](get-started-devices.md)사용자가 디바이스를 사용할 수 있도록 준비한 다음 사용자가 디바이스를 시작하고 Windows 설치 환경을 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cad76-200">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>





