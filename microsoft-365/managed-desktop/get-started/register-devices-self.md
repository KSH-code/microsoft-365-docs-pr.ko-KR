---
title: 직접 새 장치 등록
description: Microsoft Managed Desktop에서 관리할 수 있도록 장치를 직접 등록
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 8765d6ecd180d71d918a5feda8cd5089e7f561ee
ms.sourcegitcommit: 8d9509e617ede7cc5ba933c54fb9300d2d1c6344
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2020
ms.locfileid: "44347822"
---
# <a name="register-new-devices-yourself"></a><span data-ttu-id="e71c4-103">직접 새 장치 등록</span><span class="sxs-lookup"><span data-stu-id="e71c4-103">Register new devices yourself</span></span>

<span data-ttu-id="e71c4-104">Microsoft Managed Desktop은 새로운 장치에서 작동 하거나 이미 사용 중인 장치를 다시 사용할 수 있습니다 (다시 이미지 해야 함).</span><span class="sxs-lookup"><span data-stu-id="e71c4-104">Microsoft Managed Desktop can work with brand-new devices or you can re-use devices you might already have (which will require that you re-image them).</span></span> <span data-ttu-id="e71c4-105">Azure Portal에서 Microsoft Managed Desktop을 사용 하 여 장치를 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-105">You can register devices by using Microsoft Managed Desktop on the Azure Portal.</span></span>

> [!NOTE]
> <span data-ttu-id="e71c4-106">파트너와 협력 하 여 장치 가져오기</span><span class="sxs-lookup"><span data-stu-id="e71c4-106">Working with a partner to obtain devices?</span></span> <span data-ttu-id="e71c4-107">그렇다면 하드웨어 해시를 가져오는 것을 걱정 하지 않아도 됩니다. 사용자에 게 필요한 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-107">If so, you don't need to worry about getting the hardware hashes; they'll take care of that for you.</span></span> <span data-ttu-id="e71c4-108">파트너가 [파트너 센터](https://partner.microsoft.com/dashboard)에서 사용자와 관계를 설정 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-108">Make sure your partner establishes a relationship with you at the [Partner Center](https://partner.microsoft.com/dashboard).</span></span> <span data-ttu-id="e71c4-109">파트너 [센터 도움말](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer)에서 더 많은 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-109">Your partner can learn more at [Partner Center help](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer).</span></span> <span data-ttu-id="e71c4-110">이 관계가 설정 되 면 파트너는 사용자를 대신 하 여 장치를 등록 합니다 (추가 작업은 필요 하지 않음).</span><span class="sxs-lookup"><span data-stu-id="e71c4-110">Once this relationship established, your partner will simply register devices on your behalf – no further action required from you.</span></span> <span data-ttu-id="e71c4-111">세부 정보를 보거나 파트너에 게 질문이 있는 경우 [에는 파트너가 장치를 등록 하는 단계](register-devices-partner.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e71c4-111">If you want to see the details, or your partner has questions, see [Steps for Partners to register devices](register-devices-partner.md).</span></span> <span data-ttu-id="e71c4-112">장치가 등록 되 면 [이미지 확인](#check-the-image) 을 계속 하 고 사용자에 게 [장치를 전달할](#deliver-the-device) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-112">Once the devices are registered, you can proceed with [checking the image](#check-the-image) and [delivering the devices](#deliver-the-device) to your users.</span></span>

## <a name="prepare-to-register-brand-new-devices"></a><span data-ttu-id="e71c4-113">새 장치 등록 준비</span><span class="sxs-lookup"><span data-stu-id="e71c4-113">Prepare to register brand-new devices</span></span>


<span data-ttu-id="e71c4-114">새 장치를 직접 만들었으면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-114">Once you have the new devices in hand, you'll follow these steps:</span></span>

1. [<span data-ttu-id="e71c4-115">각 장치에 대 한 하드웨어 해시를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-115">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="e71c4-116">해시 데이터 병합</span><span class="sxs-lookup"><span data-stu-id="e71c4-116">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="e71c4-117">[Microsoft Managed Desktop에서 장치를 등록](#register-devices)합니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-117">[Register the devices in Microsoft Managed Desktop](#register-devices).</span></span>
4. [<span data-ttu-id="e71c4-118">이미지가 올바른지 다시 한 번 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-118">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="e71c4-119">장치 배달</span><span class="sxs-lookup"><span data-stu-id="e71c4-119">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="e71c4-120">하드웨어 해시 가져오기</span><span class="sxs-lookup"><span data-stu-id="e71c4-120">Obtain the hardware hash</span></span>

<span data-ttu-id="e71c4-121">Microsoft Managed Desktop은 해당 하드웨어 해시를 참조 하 여 각 장치를 고유 하 게 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-121">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="e71c4-122">이 정보를 얻기 위한 세 가지 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-122">You have three options for getting this information:</span></span>

- <span data-ttu-id="e71c4-123">OEM 공급자에 게 하드웨어 해시를 포함 하는 AutoPilot 등록 파일에 대해 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="e71c4-123">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="e71c4-124">각 장치에서 [Windows PowerShell 스크립트](#powershell-script-method) 를 실행 하 고 파일에서 결과를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-124">Run a [Windows PowerShell script](#powershell-script-method) on each device and collect the results in a file.</span></span>
- <span data-ttu-id="e71c4-125">각 장치를 시작 하지만 Windows 설치 환경을 완료 하지 않고 [이동식 플래시 드라이브에서 해시를 수집](#flash-drive-method)합니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-125">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="powershell-script-method"></a><span data-ttu-id="e71c4-126">PowerShell script 메서드</span><span class="sxs-lookup"><span data-stu-id="e71c4-126">PowerShell script method</span></span>

1.  <span data-ttu-id="e71c4-127">관리 권한으로 PowerShell 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-127">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="e71c4-128">실행`Install-Script -Name Get-MMDRegistrationInfo`</span><span class="sxs-lookup"><span data-stu-id="e71c4-128">Run `Install-Script -Name Get-MMDRegistrationInfo`</span></span>
3.  <span data-ttu-id="e71c4-129">실행`powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="e71c4-129">Run `powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span></span>

#### <a name="flash-drive-method"></a><span data-ttu-id="e71c4-130">Flash drive 메서드</span><span class="sxs-lookup"><span data-stu-id="e71c4-130">Flash drive method</span></span>

1. <span data-ttu-id="e71c4-131">등록 중인 장치 이외의 디바이스에서 USB 드라이브를 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-131">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="e71c4-132">관리 권한으로 PowerShell 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-132">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="e71c4-133">실행`Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="e71c4-133">Run `Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="e71c4-134">등록 중인 디바이스를 켜면 *설치 환경이 시작 되지*않습니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-134">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="e71c4-135">실수로 설치 환경을 시작한 경우 장치를 초기화 하거나 다시 이미지로 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-135">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="e71c4-136">USB 드라이브를 삽입 한 다음 SHIFT + F10 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-136">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="e71c4-137">관리 권한으로 PowerShell 프롬프트를 열고를 실행 `cd <pathToUsb>` 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-137">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="e71c4-138">실행`Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="e71c4-138">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="e71c4-139">실행`.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="e71c4-139">Run `.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="e71c4-140">USB 드라이브를 제거한 다음 다음을 실행 하 여 장치를 종료 합니다.`shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="e71c4-140">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>

>[!IMPORTANT]
><span data-ttu-id="e71c4-141">등록을 완료 한 후 다시 등록할 때까지 디바이스에 전원을 공급 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="e71c4-141">Do not power on the device you are registering again until you've completed registration for it.</span></span> 


### <a name="merge-hash-data"></a><span data-ttu-id="e71c4-142">해시 데이터 병합</span><span class="sxs-lookup"><span data-stu-id="e71c4-142">Merge hash data</span></span>

<span data-ttu-id="e71c4-143">등록을 완료 하려면 CSV 파일의 데이터를 단일 파일로 결합 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-143">You'll need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="e71c4-144">다음과 같은 샘플 PowerShell 스크립트를 통해이를 쉽게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-144">Here's a sample PowerShell script to make this easy:</span></span>

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`
### <a name="register-devices"></a><span data-ttu-id="e71c4-145">장치 등록</span><span class="sxs-lookup"><span data-stu-id="e71c4-145">Register devices</span></span>

<span data-ttu-id="e71c4-146">등록 하려면 CSV 파일을 특정 형식으로 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-146">The CSV file must be in a particular format for registration.</span></span> <span data-ttu-id="e71c4-147">이전 단계에서 데이터를 직접 수집한 경우 파일은 올바른 형식으로 되어 있어야 합니다. 공급자 로부터 파일을 가져오는 경우에는 형식을 조정 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-147">If you collected the data yourself in the previous steps, the file should already be in the right format; if you obtain the file from a supplier, you might need to adjust the format.</span></span>

>[!NOTE]
><span data-ttu-id="e71c4-148">편의를 위해 [예제 CSV 파일](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.csv)을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-148">For your convenience, you can download a [sample CSV file](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.csv).</span></span>

<span data-ttu-id="e71c4-149">샘플 1과 **정확히 같은 열 머리글** 을 포함 해야 하지만 (제조업체, 모델 등), 다른 행에 대 한 고유한 데이터를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-149">Your file needs to include the **exact same column headings** as the sample one (Manufacturer, Model, etc.), but your own data for the other rows.</span></span> <span data-ttu-id="e71c4-150">서식 파일을 사용 하는 경우 메모장 등의 텍스트 편집 도구에서이 템플릿을 열고 행 2와 아래에 데이터만 입력 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-150">If you use the template, open it in a text editing tool such as Notepad, and consider leaving all the data in row 1 alone, only entering data in rows 2 and below.</span></span> 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
><span data-ttu-id="e71c4-151">예제 데이터를 변경 하는 것을 잊은 경우에는 등록이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-151">If you forget to change any of the sample data, registration will fail.</span></span>

#### <a name="register-devices-by-using-the-azure-portal"></a><span data-ttu-id="e71c4-152">Azure Portal을 사용 하 여 장치 등록</span><span class="sxs-lookup"><span data-stu-id="e71c4-152">Register devices by using the Azure Portal</span></span>

<span data-ttu-id="e71c4-153">Microsoft Managed Desktop [Azure Portal](https://aka.ms/mmdportal)의 왼쪽 탐색 창에서 **장치** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-153">From the Microsoft Managed Desktop [Azure Portal](https://aka.ms/mmdportal), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="e71c4-154">**+ 장치 등록**을 선택 합니다. 날아오기는 다음과 같이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-154">Select **+ Register devices**; the fly-in opens:</span></span>

<span data-ttu-id="e71c4-155">[![등록 장치를 선택한 후 날아오기, 할당 된 사용자, 일련 번호, 상태, 마지막으로 표시 된 날짜 및 연령에 해당 하는 열이 있는 장치 나열](../../media/register-devices-flyin-sterile.png)](../../media/register-devices-flyin-sterile.png)</span><span class="sxs-lookup"><span data-stu-id="e71c4-155">[![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/register-devices-flyin-sterile.png)](../../media/register-devices-flyin-sterile.png)</span></span>


[//]: # (Sadly이는 그렇지 않습니다. 이 노트를 제거할 수는 있지만,이 정보를 다시 한 번에 채팅할 때까지 계속 남아 있습니다.)

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="e71c4-157">다음 단계를 따릅니다:</span><span class="sxs-lookup"><span data-stu-id="e71c4-157">Follow these steps:</span></span>

1. <span data-ttu-id="e71c4-158">**파일 업로드**에서 이전에 만든 CSV 파일의 경로를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-158">In **File upload**, provide a path to the CSV file you created previously.</span></span>
2. <span data-ttu-id="e71c4-159">원하는 경우 사용자의 추적 목적으로 **주문 id** 또는 **구매 ID** 를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-159">Optionally, you can add an **Order ID** or **Purchase ID** for your own tracking purposes.</span></span> <span data-ttu-id="e71c4-160">이러한 값에 대 한 형식 요구 사항은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-160">There are no format requirements for these values.</span></span>
3. <span data-ttu-id="e71c4-161">**장치 등록**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-161">Select **Register devices**.</span></span> <span data-ttu-id="e71c4-162">시스템은 장치를 디바이스 **블레이드에서**장치 목록에 추가 하 고 **등록 보류 중**으로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-162">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="e71c4-163">등록은 일반적으로 10 분 미만이 걸리고, 성공적인 장치는 **사용자가** 사용할 준비가 된 것으로 표시 되 고 최종 사용자가 사용을 시작할 때까지 기다릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-163">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for an end-user to start using.</span></span>


<span data-ttu-id="e71c4-164">기본 **Microsoft Managed Desktop-Devices** 페이지에서 장치 등록의 진행 상태를 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-164">You can monitor the progress of device registration on the main **Microsoft Managed Desktop - Devices** page.</span></span> <span data-ttu-id="e71c4-165">다음과 같은 가능한 상태가 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-165">Possible states reported there include:</span></span>

| <span data-ttu-id="e71c4-166">시/도</span><span class="sxs-lookup"><span data-stu-id="e71c4-166">State</span></span> | <span data-ttu-id="e71c4-167">설명</span><span class="sxs-lookup"><span data-stu-id="e71c4-167">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="e71c4-168">등록 보류 중</span><span class="sxs-lookup"><span data-stu-id="e71c4-168">Registration pending</span></span> | <span data-ttu-id="e71c4-169">등록이 아직 완료 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-169">Registration is not done yet.</span></span> <span data-ttu-id="e71c4-170">나중에 다시 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-170">Check back later.</span></span> |
| <span data-ttu-id="e71c4-171">등록 실패</span><span class="sxs-lookup"><span data-stu-id="e71c4-171">Registration failed</span></span> | <span data-ttu-id="e71c4-172">등록을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-172">Registration could not be completed.</span></span> <span data-ttu-id="e71c4-173">자세한 내용은 [장치 등록 문제 해결](#troubleshooting-device-registration) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e71c4-173">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="e71c4-174">사용자 준비</span><span class="sxs-lookup"><span data-stu-id="e71c4-174">Ready for user</span></span> | <span data-ttu-id="e71c4-175">등록을 완료 했으며 이제 장치를 최종 사용자에 게 배달할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-175">Registration succeeded and the device is now ready to be delivered to the end user.</span></span> <span data-ttu-id="e71c4-176">Microsoft Managed Desktop은 처음 설정할 때 가이드를 제공 하므로 추가 준비를 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-176">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="e71c4-177">활성</span><span class="sxs-lookup"><span data-stu-id="e71c4-177">Active</span></span> | <span data-ttu-id="e71c4-178">장치가 최종 사용자에 게 배달 되었으며 테 넌 트에 등록 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-178">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="e71c4-179">또한 장치를 정기적으로 사용 하는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-179">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="e71c4-180">있었던</span><span class="sxs-lookup"><span data-stu-id="e71c4-180">Inactive</span></span> | <span data-ttu-id="e71c4-181">장치가 최종 사용자에 게 배달 되었으며 테 넌 트에 등록 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-181">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="e71c4-182">그러나 최근에 최근 7 일 이내에 장치를 사용 하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-182">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="e71c4-183">장치 등록 문제 해결</span><span class="sxs-lookup"><span data-stu-id="e71c4-183">Troubleshooting device registration</span></span>

| <span data-ttu-id="e71c4-184">오류 메시지</span><span class="sxs-lookup"><span data-stu-id="e71c4-184">Error message</span></span> | <span data-ttu-id="e71c4-185">세부 정보</span><span class="sxs-lookup"><span data-stu-id="e71c4-185">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="e71c4-186">장치를 찾을 수 없음</span><span class="sxs-lookup"><span data-stu-id="e71c4-186">Device not found</span></span> | <span data-ttu-id="e71c4-187">제공 된 제조업체, 모델 또는 일련 번호에 대해 일치 하는 항목을 찾을 수 없기 때문에이 장치를 등록할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-187">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="e71c4-188">장치 공급자에서 이러한 값을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-188">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="e71c4-189">하드웨어 해시가 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-189">Hardware hash not valid</span></span> | <span data-ttu-id="e71c4-190">이 장치에 대해 제공한 하드웨어 해시가 올바르게 포맷 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-190">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="e71c4-191">하드웨어 해시를 두 번 확인 한 다음 다시 제출 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-191">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="e71c4-192">장치가 이미 등록 됨</span><span class="sxs-lookup"><span data-stu-id="e71c4-192">Device already registered</span></span> | <span data-ttu-id="e71c4-193">이 장치는 이미 조직에 등록 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-193">This device is already registered to your organization.</span></span> <span data-ttu-id="e71c4-194">추가 작업이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-194">No further action required.</span></span> |
| <span data-ttu-id="e71c4-195">다른 조직에서 요구 하는 장치</span><span class="sxs-lookup"><span data-stu-id="e71c4-195">Device claimed by another organization</span></span> | <span data-ttu-id="e71c4-196">이 장치는 다른 조직에서 이미 요구 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-196">This device has already been claimed by another organization.</span></span> <span data-ttu-id="e71c4-197">장치 공급자에 게 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="e71c4-197">Check with your device supplier.</span></span> |
| <span data-ttu-id="e71c4-198">예기치 않은 오류</span><span class="sxs-lookup"><span data-stu-id="e71c4-198">Unexpected error</span></span> | <span data-ttu-id="e71c4-199">요청을 자동으로 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-199">Your request could not be automatically processed.</span></span> <span data-ttu-id="e71c4-200">지원 서비스에 문의 하 여 요청 ID를 제공 합니다.<requestId></span><span class="sxs-lookup"><span data-stu-id="e71c4-200">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="e71c4-201">이미지 확인</span><span class="sxs-lookup"><span data-stu-id="e71c4-201">Check the image</span></span>

<span data-ttu-id="e71c4-202">장치가 Microsoft 관리 되는 데스크톱 파트너 공급자 로부터 온 것 이라면 이미지가 정확 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-202">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="e71c4-203">원하는 경우 이미지를 직접 적용 하는 것도 환영 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-203">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="e71c4-204">시작 하려면 사용 중인 Microsoft 담당자에 게 문의 하 여 이미지를 적용할 위치와 단계를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-204">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="e71c4-205">장치 배달</span><span class="sxs-lookup"><span data-stu-id="e71c4-205">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e71c4-206">사용자에 게 디바이스를 전달 하기 전에 해당 사용자에 대 한 [적절 한 라이선스](../get-ready/prerequisites.md) 를 확보 하 고 적용 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-206">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="e71c4-207">모든 라이선스가 적용 되 면 [사용자가 장치를 사용할 준비가](get-started-devices.md)되 면 사용자가 장치를 시작 하 고 Windows 설치 환경을 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e71c4-207">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>






