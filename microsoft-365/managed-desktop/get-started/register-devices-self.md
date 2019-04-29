---
title: Microsoft Managed Desktop에서 직접 장치 등록
description: Microsoft managed Desktop에서 관리할 수 있도록 장치를 직접 등록
ms.prod: w10
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 02b3b7ab32ff92304ab27ca8e8c805ade803c971
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "33400080"
---
# <a name="register-devices-in-microsoft-managed-desktop"></a><span data-ttu-id="8aaa7-103">Microsoft Managed Desktop에서 장치 등록</span><span class="sxs-lookup"><span data-stu-id="8aaa7-103">Register devices in Microsoft Managed Desktop</span></span>

>[!NOTE]
><span data-ttu-id="8aaa7-104">이 항목에서는 직접 장치를 등록 하는 단계를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-104">This topic describes the steps for you to register devices on your own.</span></span> <span data-ttu-id="8aaa7-105">파트너에 대 한 프로세스는 [Microsoft Managed Desktop for partner의 등록 장치](register-devices-partner.md)에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-105">The process for Partners is documented in [Register devices in Microsoft Managed Desktop for Partners](register-devices-partner.md).</span></span>

<span data-ttu-id="8aaa7-106">Microsoft Managed Desktop은 새로운 장치에서 작동 하거나 이미 사용 중인 장치를 다시 사용할 수 있습니다 (다시 이미지 해야 함).</span><span class="sxs-lookup"><span data-stu-id="8aaa7-106">Microsoft Managed Desktop can work with brand-new devices or you can re-use devices you might already have (which will require that you re-image them).</span></span> <span data-ttu-id="8aaa7-107">Azure Portal에서 Microsoft Managed Desktop을 사용 하 여 장치를 등록 하거나 API를 사용 하 여 유연성을 확보할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-107">You can register devices by using Microsoft Managed Desktop on the Azure Portal or gain flexibility by using an API.</span></span>

## <a name="prepare-to-register-devices"></a><span data-ttu-id="8aaa7-108">장치 등록 준비</span><span class="sxs-lookup"><span data-stu-id="8aaa7-108">Prepare to register devices</span></span>

<span data-ttu-id="8aaa7-109">사용할 장치를 아직 가져오지 않은 경우에는 [Microsoft Managed Desktop devices](../service-description/device-list.md) 를 확인 하 고 장치 파트너와 협력 하 여 지원 되는 장치를 조달 하세요.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-109">If you haven't already obtained the devices you want to use, check [Microsoft Managed Desktop devices](../service-description/device-list.md) and work with a device partner to procure supported devices.</span></span>

<span data-ttu-id="8aaa7-110">완전히 새로운 장치에 대 한 작업을 수행 하 고 있거나 기존 항목을 다시 사용 하 여 Microsoft Managed Desktop에 등록 하 든, **CSV (쉼표로 구분 된) 파일**을 준비 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-110">Whether you're working with completely new devices or re-using existing ones, to register them with Microsoft Managed Desktop, you'll need to prepare a **comma-delimited (CSV) file**.</span></span> <span data-ttu-id="8aaa7-111">이 파일에는 각 장치에 대 한 다음 정보가 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-111">This file should include the following information for each device:</span></span>

>[!NOTE]
><span data-ttu-id="8aaa7-112">이 형식은 셀프 서비스 등록 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-112">This format is for self-service registration only.</span></span> <span data-ttu-id="8aaa7-113">파트너가 사용 해야 하는 형식 파트너는 [Microsoft Managed Desktop for partner의 등록 장치](register-devices-partner.md)에 문서화 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-113">The format Partners should use is documented in [Register devices in Microsoft Managed Desktop for Partners](register-devices-partner.md).</span></span>

<span data-ttu-id="8aaa7-114">이러한 값은 표시 목적으로 사용 되며 장치에서 속성을 정확히 일치 시 키 지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-114">These values are used for display purposes, and don't need to match properties from the device exactly.</span></span>
- <span data-ttu-id="8aaa7-115">장치 제조업체 (예: SpiralOrbit)</span><span class="sxs-lookup"><span data-stu-id="8aaa7-115">Device manufacturer (example: SpiralOrbit)</span></span> 
- <span data-ttu-id="8aaa7-116">장치 모델 (예: ContosoABC)</span><span class="sxs-lookup"><span data-stu-id="8aaa7-116">Device model (example: ContosoABC)</span></span>
- <span data-ttu-id="8aaa7-117">장치 일련 번호</span><span class="sxs-lookup"><span data-stu-id="8aaa7-117">Device serial number</span></span>

<span data-ttu-id="8aaa7-118">하드웨어 해시는 정확히 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-118">The hardware hash must be an exact match.</span></span>
- <span data-ttu-id="8aaa7-119">하드웨어 해시</span><span class="sxs-lookup"><span data-stu-id="8aaa7-119">Hardware hash</span></span>

<span data-ttu-id="8aaa7-120">하드웨어 해시를 얻으려면 OEM 또는 파트너 로부터 도움을 요청 하거나 각 장치에 대해 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-120">To obtain the hardware hash you can ask for help from your OEM or Partner, or follow these steps for each device:</span></span>

1.  <span data-ttu-id="8aaa7-121">관리 권한으로 PowerShell 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-121">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="8aaa7-122">실행`Install-Script -Name Get-WindowsAutoPilotInfo`</span><span class="sxs-lookup"><span data-stu-id="8aaa7-122">Run `Install-Script -Name Get-WindowsAutoPilotInfo`</span></span>
3.  <span data-ttu-id="8aaa7-123">실행`powershell -ExecutionPolicy Unrestricted Get-WindowsAutopilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="8aaa7-123">Run `powershell -ExecutionPolicy Unrestricted Get-WindowsAutopilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>


<span data-ttu-id="8aaa7-124">또는 처음으로 OOBE를 진행 하기 전에 새 장치에서 다음 단계를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-124">Alternately, you can follow these steps on a brand-new device (before going through OOBE for the first time):</span></span>

1. <span data-ttu-id="8aaa7-125">다른 장치에서 USB 드라이브를 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-125">On a different device, insert a USB drive.</span></span>
2. <span data-ttu-id="8aaa7-126">관리 권한으로 PowerShell 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-126">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="8aaa7-127">실행`Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="8aaa7-127">Run `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="8aaa7-128">대상 장치를 켜고 설정 환경을 시작 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-128">Turn on the target device, but do not start the setup experience.</span></span> <span data-ttu-id="8aaa7-129">실수로 설치 환경을 시작한 경우 장치를 초기화 하거나 다시 이미지로 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-129">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="8aaa7-130">USB 드라이브를 삽입 한 다음 SHIFT + F10 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-130">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="8aaa7-131">관리 권한으로 PowerShell 프롬프트를 열고를 실행 `cd <pathToUsb>`합니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-131">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="8aaa7-132">실행`Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="8aaa7-132">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="8aaa7-133">실행`.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="8aaa7-133">Run `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
3. <span data-ttu-id="8aaa7-134">USB 드라이브를 제거한 다음 다음을 실행 하 여 장치를 종료 합니다.`shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="8aaa7-134">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>

>[!IMPORTANT]
><span data-ttu-id="8aaa7-135">사용자의 등록을 완료할 때까지 대상 장치에 다시 전원을 공급 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-135">Do not power on the target device again until you've completed registration for it.</span></span> 

>[!NOTE]
><span data-ttu-id="8aaa7-136">편의상이 CSV 파일의 [서식 파일](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx) 을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-136">For your convenience, you can download a [template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx) for this CSV file.</span></span>

<span data-ttu-id="8aaa7-137">샘플 1과 **정확히 같은 열 머리글** 을 포함 해야 하지만 (제조업체, 모델 등), 다른 행에 대 한 고유한 데이터를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-137">Your file needs to include the **exact same column headings** as the sample one (Manufacturer, Model, etc.), but your own data for the other rows.</span></span> <span data-ttu-id="8aaa7-138">서식 파일을 사용 하는 경우 메모장 등의 텍스트 편집 도구에서이 템플릿을 열고 행 2와 아래에 데이터만 입력 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-138">If you use the template, open it in a text editing tool such as Notepad, and consider leaving all the data in row 1 alone, only entering data in rows 2 and below.</span></span> 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
><span data-ttu-id="8aaa7-139">예제 데이터를 변경 하는 것을 잊은 경우에는 등록이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-139">If you forget to change any of the sample data, registration will fail.</span></span>   


## <a name="register-devices-by-using-the-azure-portal"></a><span data-ttu-id="8aaa7-140">Azure Portal을 사용 하 여 장치 등록</span><span class="sxs-lookup"><span data-stu-id="8aaa7-140">Register devices by using the Azure Portal</span></span>

<span data-ttu-id="8aaa7-141">Microsoft Managed Desktop [Azure Portal](https://aka.ms/mmdportal)의 왼쪽 탐색 창에서 **장치** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-141">From the Microsoft Managed Desktop [Azure Portal](https://aka.ms/mmdportal), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="8aaa7-142">**+ 장치 등록**을 선택 합니다. 날아오기는 다음과 같이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-142">Select **+ Register devices**; the fly-in opens:</span></span>

<span data-ttu-id="8aaa7-143">[![레지스터 장치를 선택한 후 날아오기](images/register-devices-flyin-sterile.png)](images/register-devices-flyin-sterile.png)</span><span class="sxs-lookup"><span data-stu-id="8aaa7-143">[![Fly-in after selecting Register devices](images/register-devices-flyin-sterile.png)](images/register-devices-flyin-sterile.png)</span></span>


[//]: # (Sadly이는 그렇지 않습니다. 이 노트를 제거할 수는 있지만,이 정보를 다시 한 번에 채팅할 때까지 계속 남아 있습니다.)

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="8aaa7-145">다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-145">Follow these steps:</span></span>

1. <span data-ttu-id="8aaa7-146">**파일 업로드**에서 이전에 만든 CSV 파일의 경로를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-146">In **File upload**, provide a path to the CSV file you created previously.</span></span>
2. <span data-ttu-id="8aaa7-147">원하는 경우 사용자의 추적 목적으로 **주문 id** 또는 **구매 ID** 를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-147">Optionally, you can add an **Order ID** or **Purchase ID** for your own tracking purposes.</span></span> <span data-ttu-id="8aaa7-148">이러한 값에 대 한 형식 요구 사항은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-148">There are no format requirements for these values.</span></span>
3. <span data-ttu-id="8aaa7-149">**장치 등록**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-149">Select **Register devices**.</span></span> <span data-ttu-id="8aaa7-150">시스템은 장치를 디바이스 **블레이드에서**장치 목록에 추가 하 고 **등록 보류 중**으로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-150">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="8aaa7-151">등록은 일반적으로 10 분 미만이 걸리고, 성공적인 장치는 **사용자가** 사용할 준비가 된 것으로 표시 되 고 최종 사용자가 사용을 시작할 때까지 기다릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-151">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for an end-user to start using.</span></span>


<span data-ttu-id="8aaa7-152">기본 **Microsoft Managed Desktop-Devices** 페이지에서 장치 등록의 진행 상태를 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-152">You can monitor the progress of device registration on the main **Microsoft Managed Desktop - Devices** page.</span></span> <span data-ttu-id="8aaa7-153">다음과 같은 가능한 상태가 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-153">Possible states reported there include:</span></span>

| <span data-ttu-id="8aaa7-154">시/도</span><span class="sxs-lookup"><span data-stu-id="8aaa7-154">State</span></span> | <span data-ttu-id="8aaa7-155">설명</span><span class="sxs-lookup"><span data-stu-id="8aaa7-155">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="8aaa7-156">등록 보류 중</span><span class="sxs-lookup"><span data-stu-id="8aaa7-156">Registration pending</span></span> | <span data-ttu-id="8aaa7-157">등록이 아직 완료 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-157">Registration is not done yet.</span></span> <span data-ttu-id="8aaa7-158">나중에 다시 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-158">Check back later.</span></span> |
| <span data-ttu-id="8aaa7-159">등록 실패</span><span class="sxs-lookup"><span data-stu-id="8aaa7-159">Registration failed</span></span> | <span data-ttu-id="8aaa7-160">등록을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-160">Registration could not be completed.</span></span> <span data-ttu-id="8aaa7-161">자세한 내용은 [문제 해결](register-devices-self.md#troubleshooting) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-161">Refer to [Troubleshooting](register-devices-self.md#troubleshooting) for more information.</span></span> |
| <span data-ttu-id="8aaa7-162">사용자 준비</span><span class="sxs-lookup"><span data-stu-id="8aaa7-162">Ready for user</span></span> | <span data-ttu-id="8aaa7-163">등록을 완료 했으며 이제 장치를 최종 사용자에 게 배달할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-163">Registration succeeded and the device is now ready to be delivered to the end user.</span></span> <span data-ttu-id="8aaa7-164">Microsoft Managed Desktop은 처음 설정할 때 가이드를 제공 하므로 추가 준비를 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-164">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="8aaa7-165">활성</span><span class="sxs-lookup"><span data-stu-id="8aaa7-165">Active</span></span> | <span data-ttu-id="8aaa7-166">장치가 최종 사용자에 게 배달 되었으며 테 넌 트에 등록 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-166">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="8aaa7-167">또한 장치를 정기적으로 사용 하는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-167">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="8aaa7-168">있었던</span><span class="sxs-lookup"><span data-stu-id="8aaa7-168">Inactive</span></span> | <span data-ttu-id="8aaa7-169">장치가 최종 사용자에 게 배달 되었으며 테 넌 트에 등록 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-169">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="8aaa7-170">그러나 최근에 최근 7 일 이내에 장치를 사용 하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-170">However, they have not used the device recently (in the last 7 days).</span></span>  | 


## <a name="register-devices-by-using-an-api"></a><span data-ttu-id="8aaa7-171">API를 사용 하 여 장치 등록</span><span class="sxs-lookup"><span data-stu-id="8aaa7-171">Register devices by using an API</span></span>

<span data-ttu-id="8aaa7-172">REST API를 사용 하 여 더 많은 유연성과 repeatability을 사용 하 여 여러 장치를 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-172">A REST API is available to allow you greater flexibility and repeatability with frequent separate device registrations.</span></span> <span data-ttu-id="8aaa7-173">현재 API를 사용 하려면 Microsoft 연락처에서이 기능의 미리 보기에 참여 하도록 도움을 요청 하세요.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-173">Currently, to use the API, ask for help from your Microsoft contact to join a preview of this capability.</span></span>



## <a name="troubleshooting"></a><span data-ttu-id="8aaa7-174">문제 해결</span><span class="sxs-lookup"><span data-stu-id="8aaa7-174">Troubleshooting</span></span>

| <span data-ttu-id="8aaa7-175">오류 메시지</span><span class="sxs-lookup"><span data-stu-id="8aaa7-175">Error message</span></span> | <span data-ttu-id="8aaa7-176">세부 정보</span><span class="sxs-lookup"><span data-stu-id="8aaa7-176">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="8aaa7-177">장치를 찾을 수 없음</span><span class="sxs-lookup"><span data-stu-id="8aaa7-177">Device not found</span></span> | <span data-ttu-id="8aaa7-178">제공 된 제조업체, 모델 또는 일련 번호에 대해 일치 하는 항목을 찾을 수 없기 때문에이 장치를 등록할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-178">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="8aaa7-179">장치 공급자에서 이러한 값을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-179">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="8aaa7-180">장치를 찾을 수 없음</span><span class="sxs-lookup"><span data-stu-id="8aaa7-180">Device not found</span></span> | <span data-ttu-id="8aaa7-181">이 디바이스가 조직에 없으므로 등록을 취소할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-181">We couldn’t de-register this device because it does not exist in your organization.</span></span> <span data-ttu-id="8aaa7-182">추가 작업이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-182">No further action required.</span></span> |
| <span data-ttu-id="8aaa7-183">하드웨어 해시가 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-183">Hardware hash not valid</span></span> | <span data-ttu-id="8aaa7-184">이 장치에 대해 제공한 하드웨어 해시가 올바르게 포맷 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-184">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="8aaa7-185">하드웨어 해시를 두 번 확인 한 다음 다시 제출 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-185">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="8aaa7-186">장치가 이미 등록 됨</span><span class="sxs-lookup"><span data-stu-id="8aaa7-186">Device already registered</span></span> | <span data-ttu-id="8aaa7-187">이 장치는 이미 조직에 등록 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-187">This device is already registered to your organization.</span></span> <span data-ttu-id="8aaa7-188">추가 작업이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-188">No further action required.</span></span> |
| <span data-ttu-id="8aaa7-189">다른 조직에서 요구 하는 장치</span><span class="sxs-lookup"><span data-stu-id="8aaa7-189">Device claimed by another organization</span></span> | <span data-ttu-id="8aaa7-190">이 장치는 다른 조직에서 이미 요구 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-190">This device has already been claimed by another organization.</span></span> <span data-ttu-id="8aaa7-191">장치 공급자에 게 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-191">Check with your device supplier.</span></span> |
| <span data-ttu-id="8aaa7-192">예기치 않은 오류</span><span class="sxs-lookup"><span data-stu-id="8aaa7-192">Unexpected error</span></span> | <span data-ttu-id="8aaa7-193">요청을 자동으로 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-193">Your request could not be automatically processed.</span></span> <span data-ttu-id="8aaa7-194">지원 서비스에 문의 하 여 요청 ID를 제공 합니다.<requestId></span><span class="sxs-lookup"><span data-stu-id="8aaa7-194">Contact Support and provide the Request ID: <requestId></span></span> |




