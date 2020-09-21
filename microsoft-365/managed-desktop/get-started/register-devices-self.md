---
title: 직접 새 장치 등록
description: Microsoft Managed Desktop에서 관리할 수 있도록 장치를 직접 등록
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 550f7dd35b3990a08da4c2bb9dd3042ff084b185
ms.sourcegitcommit: adaedd1418a3bd6e4875b77fd9e008b47e0b2a51
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/18/2020
ms.locfileid: "48104403"
---
# <a name="register-new-devices-yourself"></a><span data-ttu-id="e524b-103">직접 새 장치 등록</span><span class="sxs-lookup"><span data-stu-id="e524b-103">Register new devices yourself</span></span>

<span data-ttu-id="e524b-104">Microsoft Managed Desktop은 새로운 장치에서 작동 하거나 이미 사용 중인 장치를 다시 사용할 수 있습니다 (다시 이미지 해야 함).</span><span class="sxs-lookup"><span data-stu-id="e524b-104">Microsoft Managed Desktop can work with brand-new devices or you can re-use devices you might already have (which will require that you re-image them).</span></span> <span data-ttu-id="e524b-105">Microsoft Endpoint Manager 포털에서 Microsoft Managed Desktop을 사용 하 여 장치를 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-105">You can register devices with Microsoft Managed Desktop in the Microsoft Endpoint Manager portal.</span></span>

> [!NOTE]
> <span data-ttu-id="e524b-106">파트너와 협력 하 여 장치 가져오기</span><span class="sxs-lookup"><span data-stu-id="e524b-106">Working with a partner to obtain devices?</span></span> <span data-ttu-id="e524b-107">그렇다면 하드웨어 해시를 가져오는 것을 걱정 하지 않아도 됩니다. 사용자에 게 필요한 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-107">If so, you don't need to worry about getting the hardware hashes; they'll take care of that for you.</span></span> <span data-ttu-id="e524b-108">파트너가 [파트너 센터](https://partner.microsoft.com/dashboard)에서 사용자와 관계를 설정 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-108">Make sure your partner establishes a relationship with you at the [Partner Center](https://partner.microsoft.com/dashboard).</span></span> <span data-ttu-id="e524b-109">파트너 [센터 도움말](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer)에서 더 많은 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-109">Your partner can learn more at [Partner Center help](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer).</span></span> <span data-ttu-id="e524b-110">이 관계가 설정 되 면 파트너는 사용자를 대신 하 여 장치를 등록 합니다 (추가 작업은 필요 하지 않음).</span><span class="sxs-lookup"><span data-stu-id="e524b-110">Once this relationship established, your partner will simply register devices on your behalf – no further action required from you.</span></span> <span data-ttu-id="e524b-111">세부 정보를 보거나 파트너에 게 질문이 있는 경우 [에는 파트너가 장치를 등록 하는 단계](register-devices-partner.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e524b-111">If you want to see the details, or your partner has questions, see [Steps for Partners to register devices](register-devices-partner.md).</span></span> <span data-ttu-id="e524b-112">장치가 등록 되 면 [이미지 확인](#check-the-image) 을 계속 하 고 사용자에 게 [장치를 전달할](#deliver-the-device) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-112">Once the devices are registered, you can proceed with [checking the image](#check-the-image) and [delivering the devices](#deliver-the-device) to your users.</span></span>

## <a name="prepare-to-register-brand-new-devices"></a><span data-ttu-id="e524b-113">새 장치 등록 준비</span><span class="sxs-lookup"><span data-stu-id="e524b-113">Prepare to register brand-new devices</span></span>


<span data-ttu-id="e524b-114">새 장치를 직접 만들었으면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-114">Once you have the new devices in hand, you'll follow these steps:</span></span>

1. [<span data-ttu-id="e524b-115">각 장치에 대 한 하드웨어 해시를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-115">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="e524b-116">해시 데이터 병합</span><span class="sxs-lookup"><span data-stu-id="e524b-116">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="e524b-117">[Microsoft Managed Desktop에서 장치를 등록](#register-devices-by-using-the-admin-portal)합니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-117">[Register the devices in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).</span></span>
4. [<span data-ttu-id="e524b-118">이미지가 올바른지 다시 한 번 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-118">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="e524b-119">장치 배달</span><span class="sxs-lookup"><span data-stu-id="e524b-119">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="e524b-120">하드웨어 해시 가져오기</span><span class="sxs-lookup"><span data-stu-id="e524b-120">Obtain the hardware hash</span></span>

<span data-ttu-id="e524b-121">Microsoft Managed Desktop은 해당 하드웨어 해시를 참조 하 여 각 장치를 고유 하 게 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-121">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="e524b-122">이 정보를 얻기 위한 세 가지 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-122">You have three options for getting this information:</span></span>

- <span data-ttu-id="e524b-123">OEM 공급자에 게 하드웨어 해시를 포함 하는 AutoPilot 등록 파일에 대해 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="e524b-123">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="e524b-124">각 장치에서 [Windows PowerShell 스크립트](#powershell-script-method) 를 실행 하 고 파일에서 결과를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-124">Run a [Windows PowerShell script](#powershell-script-method) on each device and collect the results in a file.</span></span>
- <span data-ttu-id="e524b-125">각 장치를 시작 하지만 Windows 설치 환경을 완료 하지 않고 [이동식 플래시 드라이브에서 해시를 수집](#flash-drive-method)합니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-125">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="powershell-script-method"></a><span data-ttu-id="e524b-126">PowerShell script 메서드</span><span class="sxs-lookup"><span data-stu-id="e524b-126">PowerShell script method</span></span>

<span data-ttu-id="e524b-127">PowerShell 갤러리 웹 사이트에서 [Get-WindowsAutoPilotInfo.ps1](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) powershell 스크립트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-127">You can use the [Get-WindowsAutoPilotInfo.ps1](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) PowerShell script on the PowerShell Gallery website.</span></span> <span data-ttu-id="e524b-128">장치 id 및 하드웨어 해시에 대 한 자세한 내용은 [Windows에 장치 추가 Autopilot를](https://docs.microsoft.com/mem/autopilot/add-devices#device-identification)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e524b-128">For more information about device identification and hardware hash, see [Adding devices to Windows Autopilot](https://docs.microsoft.com/mem/autopilot/add-devices#device-identification).</span></span>

1.  <span data-ttu-id="e524b-129">관리 권한으로 PowerShell 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-129">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="e524b-130">실행 `Install-Script -Name Get-WindowsAutoPilotInfo`</span><span class="sxs-lookup"><span data-stu-id="e524b-130">Run `Install-Script -Name Get-WindowsAutoPilotInfo`</span></span>
3.  <span data-ttu-id="e524b-131">실행 `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="e524b-131">Run `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>

#### <a name="flash-drive-method"></a><span data-ttu-id="e524b-132">Flash drive 메서드</span><span class="sxs-lookup"><span data-stu-id="e524b-132">Flash drive method</span></span>

1. <span data-ttu-id="e524b-133">등록 중인 장치 이외의 디바이스에서 USB 드라이브를 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-133">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="e524b-134">관리 권한으로 PowerShell 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-134">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="e524b-135">실행 `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="e524b-135">Run `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="e524b-136">등록 중인 디바이스를 켜면 *설치 환경이 시작 되지*않습니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-136">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="e524b-137">실수로 설치 환경을 시작한 경우 장치를 초기화 하거나 다시 이미지로 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-137">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="e524b-138">USB 드라이브를 삽입 한 다음 SHIFT + F10 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-138">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="e524b-139">관리 권한으로 PowerShell 프롬프트를 열고를 실행 `cd <pathToUsb>` 합니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-139">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="e524b-140">실행 `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="e524b-140">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="e524b-141">실행 `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="e524b-141">Run `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="e524b-142">USB 드라이브를 제거한 다음 다음을 실행 하 여 장치를 종료 합니다. `shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="e524b-142">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>

>[!IMPORTANT]
><span data-ttu-id="e524b-143">등록을 완료 한 후 다시 등록할 때까지 디바이스에 전원을 공급 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="e524b-143">Do not power on the device you are registering again until you've completed registration for it.</span></span> 


### <a name="merge-hash-data"></a><span data-ttu-id="e524b-144">해시 데이터 병합</span><span class="sxs-lookup"><span data-stu-id="e524b-144">Merge hash data</span></span>

<span data-ttu-id="e524b-145">등록을 완료 하려면 CSV 파일의 데이터를 단일 파일로 결합 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-145">You'll need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="e524b-146">다음과 같은 샘플 PowerShell 스크립트를 통해이를 쉽게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-146">Here's a sample PowerShell script to make this easy:</span></span>

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`


#### <a name="register-devices-by-using-the-admin-portal"></a><span data-ttu-id="e524b-147">관리 포털을 사용 하 여 장치 등록</span><span class="sxs-lookup"><span data-stu-id="e524b-147">Register devices by using the Admin Portal</span></span>

<span data-ttu-id="e524b-148">[Microsoft Endpoint Manager](https://endpoint.microsoft.com/)의 왼쪽 탐색 창에서 **장치** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-148">In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="e524b-149">메뉴의 Microsoft Managed Desktop 섹션을 찾아 **장치**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-149">Look for the Microsoft Managed Desktop section of the menu and select **Devices**.</span></span> <span data-ttu-id="e524b-150">Microsoft Managed Desktop Devices 작업 영역에서 **+ register Devices** 를 선택 하 여 새 장치를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-150">In the Microsoft Managed Desktop Devices workspace, Select **+ Register devices** which opens a fly-in to register new devices.</span></span>

<!-- [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="e524b-151">다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-151">Follow these steps:</span></span>

1. <span data-ttu-id="e524b-152">**파일 업로드**에서 이전에 만든 CSV 파일의 경로를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-152">In **File upload**, provide a path to the CSV file you created previously.</span></span>
3. <span data-ttu-id="e524b-153">**장치 등록**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-153">Select **Register devices**.</span></span> <span data-ttu-id="e524b-154">시스템이 장치 **블레이드에서**장치 목록에 추가 되 고 **AutopilotRegistrationRequested**로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-154">The system will add the devices to your list of devices on the **Devices blade**, marked as **AutopilotRegistrationRequested**.</span></span> <span data-ttu-id="e524b-155">등록은 일반적으로 10 분 미만이 걸리고, 성공적으로 완료 되 면 장치에 **사용자가** 사용할 준비가 된 것으로 표시 되 고 사용자가 사용을 시작할 때까지 대기 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-155">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for a user to start using.</span></span>


<span data-ttu-id="e524b-156">기본 페이지에서 장치 등록의 진행 상태를 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-156">You can monitor the progress of device registration on the main page.</span></span> <span data-ttu-id="e524b-157">다음과 같은 가능한 상태가 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-157">Possible states reported there include:</span></span>

| <span data-ttu-id="e524b-158">시/도</span><span class="sxs-lookup"><span data-stu-id="e524b-158">State</span></span> | <span data-ttu-id="e524b-159">설명</span><span class="sxs-lookup"><span data-stu-id="e524b-159">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="e524b-160">AutopilotRegistrationRequested</span><span class="sxs-lookup"><span data-stu-id="e524b-160">AutopilotRegistrationRequested</span></span> | <span data-ttu-id="e524b-161">등록이 아직 완료 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-161">Registration is not done yet.</span></span> <span data-ttu-id="e524b-162">나중에 다시 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-162">Check back later.</span></span> |
| <span data-ttu-id="e524b-163">등록 실패</span><span class="sxs-lookup"><span data-stu-id="e524b-163">Registration failed</span></span> | <span data-ttu-id="e524b-164">등록을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-164">Registration could not be completed.</span></span> <span data-ttu-id="e524b-165">자세한 내용은 [장치 등록 문제 해결](#troubleshooting-device-registration) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e524b-165">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="e524b-166">사용자 준비</span><span class="sxs-lookup"><span data-stu-id="e524b-166">Ready for user</span></span> | <span data-ttu-id="e524b-167">등록을 완료 했으며 이제 장치를 사용자에 게 배달할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-167">Registration succeeded and the device is now ready to be delivered to the user.</span></span> <span data-ttu-id="e524b-168">Microsoft Managed Desktop은 처음 설정할 때 가이드를 제공 하므로 추가 준비를 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-168">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="e524b-169">활성</span><span class="sxs-lookup"><span data-stu-id="e524b-169">Active</span></span> | <span data-ttu-id="e524b-170">장치가 사용자에 게 배달 되었으며 테 넌 트에 등록 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-170">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="e524b-171">또한 장치를 정기적으로 사용 하는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-171">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="e524b-172">있었던</span><span class="sxs-lookup"><span data-stu-id="e524b-172">Inactive</span></span> | <span data-ttu-id="e524b-173">장치가 사용자에 게 배달 되었으며 테 넌 트에 등록 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-173">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="e524b-174">그러나 최근에 최근 7 일 이내에 장치를 사용 하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-174">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="e524b-175">장치 등록 문제 해결</span><span class="sxs-lookup"><span data-stu-id="e524b-175">Troubleshooting device registration</span></span>

| <span data-ttu-id="e524b-176">오류 메시지</span><span class="sxs-lookup"><span data-stu-id="e524b-176">Error message</span></span> | <span data-ttu-id="e524b-177">세부 정보</span><span class="sxs-lookup"><span data-stu-id="e524b-177">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="e524b-178">장치를 찾을 수 없음</span><span class="sxs-lookup"><span data-stu-id="e524b-178">Device not found</span></span> | <span data-ttu-id="e524b-179">제공 된 제조업체, 모델 또는 일련 번호에 대해 일치 하는 항목을 찾을 수 없기 때문에이 장치를 등록할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-179">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="e524b-180">장치 공급자에서 이러한 값을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-180">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="e524b-181">하드웨어 해시가 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-181">Hardware hash not valid</span></span> | <span data-ttu-id="e524b-182">이 장치에 대해 제공한 하드웨어 해시가 올바르게 포맷 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-182">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="e524b-183">하드웨어 해시를 두 번 확인 한 다음 다시 제출 합니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-183">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="e524b-184">장치가 이미 등록 됨</span><span class="sxs-lookup"><span data-stu-id="e524b-184">Device already registered</span></span> | <span data-ttu-id="e524b-185">이 장치는 이미 조직에 등록 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-185">This device is already registered to your organization.</span></span> <span data-ttu-id="e524b-186">추가 작업이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-186">No further action required.</span></span> |
| <span data-ttu-id="e524b-187">다른 조직에서 요구 하는 장치</span><span class="sxs-lookup"><span data-stu-id="e524b-187">Device claimed by another organization</span></span> | <span data-ttu-id="e524b-188">이 장치는 다른 조직에서 이미 요구 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-188">This device has already been claimed by another organization.</span></span> <span data-ttu-id="e524b-189">장치 공급자에 게 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="e524b-189">Check with your device supplier.</span></span> |
| <span data-ttu-id="e524b-190">예기치 않은 오류</span><span class="sxs-lookup"><span data-stu-id="e524b-190">Unexpected error</span></span> | <span data-ttu-id="e524b-191">요청을 자동으로 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-191">Your request could not be automatically processed.</span></span> <span data-ttu-id="e524b-192">지원 서비스에 문의 하 여 요청 ID를 제공 합니다. <requestId></span><span class="sxs-lookup"><span data-stu-id="e524b-192">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="e524b-193">이미지 확인</span><span class="sxs-lookup"><span data-stu-id="e524b-193">Check the image</span></span>

<span data-ttu-id="e524b-194">장치가 Microsoft 관리 되는 데스크톱 파트너 공급자 로부터 온 것 이라면 이미지가 정확 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-194">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="e524b-195">원하는 경우 이미지를 직접 적용 하는 것도 환영 합니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-195">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="e524b-196">시작 하려면 사용 중인 Microsoft 담당자에 게 문의 하 여 이미지를 적용할 위치와 단계를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-196">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="e524b-197">장치 배달</span><span class="sxs-lookup"><span data-stu-id="e524b-197">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e524b-198">사용자에 게 디바이스를 전달 하기 전에 해당 사용자에 대 한 [적절 한 라이선스](../get-ready/prerequisites.md) 를 확보 하 고 적용 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-198">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="e524b-199">모든 라이선스가 적용 되 면 [사용자가 장치를 사용할 준비가](get-started-devices.md)되 면 사용자가 장치를 시작 하 고 Windows 설치 환경을 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e524b-199">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>






