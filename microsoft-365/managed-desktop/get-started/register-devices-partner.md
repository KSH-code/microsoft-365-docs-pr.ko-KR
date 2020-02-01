---
title: 파트너가 장치를 등록하기 위한 단계
description: 파트너가 장치를 등록 하 여 Microsoft Managed Desktop에서 관리할 수 있도록 하는 방법
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: a9a2a0ccb1e0830d674f4b1b1ef5495fafb38ca3
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596555"
---
# <a name="steps-for-partners-to-register-devices"></a><span data-ttu-id="f679e-103">파트너가 장치를 등록하기 위한 단계</span><span class="sxs-lookup"><span data-stu-id="f679e-103">Steps for Partners to register devices</span></span>


<span data-ttu-id="f679e-104">이 항목에서는 파트너가 장치를 등록 하기 위해 수행 해야 하는 단계에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f679e-104">This topic describes the steps for Partners to follow to register devices.</span></span> <span data-ttu-id="f679e-105">장치를 직접 등록 하는 프로세스는 [Microsoft Managed Desktop의 등록 장치에 직접](register-devices-self.md)기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f679e-105">The process for registering devices yourself is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>



## <a name="prepare-for-registration"></a><span data-ttu-id="f679e-106">등록 준비</span><span class="sxs-lookup"><span data-stu-id="f679e-106">Prepare for registration</span></span> 
<span data-ttu-id="f679e-107">고객에 대 한 등록을 완료 하기 전에 먼저 [파트너 센터](https://partner.microsoft.com/dashboard)에서 해당 사용자와의 관계를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f679e-107">Before completing registration for a customer, you must first establish a relationship with them at the [Partner Center](https://partner.microsoft.com/dashboard).</span></span> <span data-ttu-id="f679e-108">**Azure Active Directory 및 Office 365에 대 한 위임 된 관리 권한 포함**을 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f679e-108">Be sure to select **Include delegated administration privileges for Azure Active Directory and Office 365**.</span></span> <span data-ttu-id="f679e-109">자세한 내용은 [파트너 센터 도움말을 참조](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer)하십시오.</span><span class="sxs-lookup"><span data-stu-id="f679e-109">Learn more at [Partner Center help](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer).</span></span>

<span data-ttu-id="f679e-110">고객에 대 한 등록을 완료 하려면 먼저 CSV 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f679e-110">To complete registration for your customer, first create a CSV file.</span></span>

>[!NOTE]
><span data-ttu-id="f679e-111">편의상이 *파트너 버전*에 대 한 [예제 CSV 파일](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.csv) 을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f679e-111">For your convenience, you can download a [sample CSV file](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.csv) for this *Partner version*.</span></span>

<span data-ttu-id="f679e-112">샘플 1과 **정확히 같은 열 머리글** 을 포함 해야 하지만 (제조업체, 모델 등), 다른 행에 대 한 고유한 데이터를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f679e-112">Your file needs to include the **exact same column headings** as the sample one (Manufacturer, Model, etc.), but your own data for the other rows.</span></span> <span data-ttu-id="f679e-113">서식 파일을 사용 하는 경우 메모장 등의 텍스트 편집 도구에서이 템플릿을 열고 행 2와 아래에 데이터만 입력 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f679e-113">If you use the template, open it in a text editing tool such as Notepad, and consider leaving all the data in row 1 alone, only entering data in rows 2 and below.</span></span> 
    
  ```
 Manufacturer,Model,Serial Number
  SpiralOrbit,ContosoABC,000000000000
  
  
  ```




>[!NOTE]
><span data-ttu-id="f679e-114">이 형식은 파트너 프로세스에만 해당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f679e-114">This format is only for the Partner process.</span></span> <span data-ttu-id="f679e-115">자동 등록 프로세스는 [Microsoft Managed Desktop의 등록 장치에서 직접](register-devices-self.md)설명 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f679e-115">The process for self-registration is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>

>[!IMPORTANT]
><span data-ttu-id="f679e-116">이러한 값은 대/소문자 및 특수 문자를 포함 하 여 SMBIOS의 제조업체 값과 정확히 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f679e-116">These values must match the manufacturer values from SMBIOS exactly, including capitalization and special characters.</span></span> 

- <span data-ttu-id="f679e-117">장치 제조업체 (예: SpiralOrbit)</span><span class="sxs-lookup"><span data-stu-id="f679e-117">Device manufacturer (example: SpiralOrbit)</span></span> 
- <span data-ttu-id="f679e-118">장치 모델 (예: ContosoABC)</span><span class="sxs-lookup"><span data-stu-id="f679e-118">Device model (example: ContosoABC)</span></span>
- <span data-ttu-id="f679e-119">장치 일련 번호</span><span class="sxs-lookup"><span data-stu-id="f679e-119">Device serial number</span></span>

## <a name="register-devices-by-using-the-azure-portal"></a><span data-ttu-id="f679e-120">Azure Portal을 사용 하 여 장치 등록</span><span class="sxs-lookup"><span data-stu-id="f679e-120">Register devices by using the Azure Portal</span></span>

<span data-ttu-id="f679e-121">Azure Portal을 사용 하 여 등록 하는 것은 다른 방법으로 포털에 액세스 하는 것을 제외 하 고 셀프 서비스와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="f679e-121">Registering by using the Azure Portal is the same as for self-service, except you access the portal differently.</span></span> <span data-ttu-id="f679e-122">다음 단계를 따릅니다:</span><span class="sxs-lookup"><span data-stu-id="f679e-122">Follow these steps:</span></span>

1. <span data-ttu-id="f679e-123">[파트너 센터로](https://partner.microsoft.com/dashboard) 이동</span><span class="sxs-lookup"><span data-stu-id="f679e-123">Navigate to [Partner Center](https://partner.microsoft.com/dashboard)</span></span>
2. <span data-ttu-id="f679e-124">**고객**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f679e-124">Select **Customers**.</span></span>
3. <span data-ttu-id="f679e-125">관리할 고객을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f679e-125">Select the customer you want to manage.</span></span>
4. <span data-ttu-id="f679e-126">**서비스 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f679e-126">Select **Service Administration**.</span></span>
5. <span data-ttu-id="f679e-127">**Intune**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f679e-127">Select **Intune**.</span></span>
6. <span data-ttu-id="f679e-128">Azure portal의 위쪽 검색 상자에서 "mmd"를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="f679e-128">Search for "mmd" in the top search box of the Azure portal.</span></span>
7. <span data-ttu-id="f679e-129">**장치**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f679e-129">Select **Devices**.</span></span>
8. <span data-ttu-id="f679e-130">**파일 업로드**에서 이전에 만든 CSV 파일의 경로를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f679e-130">In **File upload**, provide a path to the CSV file you created previously.</span></span>
9. <span data-ttu-id="f679e-131">원하는 경우 사용자의 추적 목적으로 **주문 id** 또는 **구매 ID** 를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f679e-131">Optionally, you can add an **Order ID** or **Purchase ID** for your own tracking purposes.</span></span> <span data-ttu-id="f679e-132">이러한 값에 대 한 형식 요구 사항은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f679e-132">There are no format requirements for these values.</span></span>
10. <span data-ttu-id="f679e-133">**장치 등록**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f679e-133">Select **Register devices**.</span></span> <span data-ttu-id="f679e-134">시스템은 장치를 디바이스 **블레이드에서**장치 목록에 추가 하 고 **등록 보류 중**으로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="f679e-134">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="f679e-135">등록은 일반적으로 10 분 미만이 걸리고, 성공적인 장치는 **사용자가** 사용할 준비가 된 것으로 표시 되 고 최종 사용자가 사용을 시작할 때까지 기다릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f679e-135">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for an end-user to start using.</span></span>


<span data-ttu-id="f679e-136">기본 **Microsoft Managed Desktop-Devices** 페이지에서 장치 등록의 진행 상태를 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f679e-136">You can monitor the progress of device registration on the main **Microsoft Managed Desktop - Devices** page.</span></span> <span data-ttu-id="f679e-137">다음과 같은 가능한 상태가 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f679e-137">Possible states reported there include:</span></span>

| <span data-ttu-id="f679e-138">시/도</span><span class="sxs-lookup"><span data-stu-id="f679e-138">State</span></span> | <span data-ttu-id="f679e-139">설명</span><span class="sxs-lookup"><span data-stu-id="f679e-139">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="f679e-140">등록 보류 중</span><span class="sxs-lookup"><span data-stu-id="f679e-140">Registration pending</span></span> | <span data-ttu-id="f679e-141">등록이 아직 완료 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="f679e-141">Registration is not done yet.</span></span> <span data-ttu-id="f679e-142">나중에 다시 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f679e-142">Check back later.</span></span> |
| <span data-ttu-id="f679e-143">등록 실패</span><span class="sxs-lookup"><span data-stu-id="f679e-143">Registration failed</span></span> | <span data-ttu-id="f679e-144">등록을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f679e-144">Registration could not be completed.</span></span> <span data-ttu-id="f679e-145">자세한 내용은 [장치 등록 문제 해결](register-devices-self.md#troubleshooting-device-registration) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f679e-145">Refer to [Troubleshooting device registration](register-devices-self.md#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="f679e-146">사용자 준비</span><span class="sxs-lookup"><span data-stu-id="f679e-146">Ready for user</span></span> | <span data-ttu-id="f679e-147">등록을 완료 했으며 이제 장치를 최종 사용자에 게 배달할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f679e-147">Registration succeeded and the device is now ready to be delivered to the end user.</span></span> <span data-ttu-id="f679e-148">Microsoft Managed Desktop은 처음 설정할 때 가이드를 제공 하므로 추가 준비를 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f679e-148">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="f679e-149">활성</span><span class="sxs-lookup"><span data-stu-id="f679e-149">Active</span></span> | <span data-ttu-id="f679e-150">장치가 최종 사용자에 게 배달 되었으며 테 넌 트에 등록 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f679e-150">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="f679e-151">또한 장치를 정기적으로 사용 하는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f679e-151">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="f679e-152">있었던</span><span class="sxs-lookup"><span data-stu-id="f679e-152">Inactive</span></span> | <span data-ttu-id="f679e-153">장치가 최종 사용자에 게 배달 되었으며 테 넌 트에 등록 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f679e-153">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="f679e-154">그러나 최근에 최근 7 일 이내에 장치를 사용 하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="f679e-154">However, they have not used the device recently (in the last 7 days).</span></span>  |



## <a name="troubleshooting"></a><span data-ttu-id="f679e-155">문제 해결</span><span class="sxs-lookup"><span data-stu-id="f679e-155">Troubleshooting</span></span>

| <span data-ttu-id="f679e-156">오류 메시지</span><span class="sxs-lookup"><span data-stu-id="f679e-156">Error message</span></span> | <span data-ttu-id="f679e-157">세부 정보</span><span class="sxs-lookup"><span data-stu-id="f679e-157">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="f679e-158">장치를 찾을 수 없음</span><span class="sxs-lookup"><span data-stu-id="f679e-158">Device not found</span></span> | <span data-ttu-id="f679e-159">제공 된 제조업체, 모델 또는 일련 번호에 대해 일치 하는 항목을 찾을 수 없기 때문에이 장치를 등록할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f679e-159">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="f679e-160">장치 공급자에서 이러한 값을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f679e-160">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="f679e-161">하드웨어 해시가 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f679e-161">Hardware hash not valid</span></span> | <span data-ttu-id="f679e-162">이 장치에 대해 제공한 하드웨어 해시가 올바르게 포맷 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="f679e-162">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="f679e-163">하드웨어 해시를 두 번 확인 한 다음 다시 제출 합니다.</span><span class="sxs-lookup"><span data-stu-id="f679e-163">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="f679e-164">장치가 이미 등록 됨</span><span class="sxs-lookup"><span data-stu-id="f679e-164">Device already registered</span></span> | <span data-ttu-id="f679e-165">이 장치는 이미 조직에 등록 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f679e-165">This device is already registered to your organization.</span></span> <span data-ttu-id="f679e-166">추가 작업이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f679e-166">No further action required.</span></span> |
| <span data-ttu-id="f679e-167">다른 조직에서 요구 하는 장치</span><span class="sxs-lookup"><span data-stu-id="f679e-167">Device claimed by another organization</span></span> | <span data-ttu-id="f679e-168">이 장치는 다른 조직에서 이미 요구 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f679e-168">This device has already been claimed by another organization.</span></span> <span data-ttu-id="f679e-169">장치 공급자에 게 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="f679e-169">Check with your device supplier.</span></span> |
| <span data-ttu-id="f679e-170">예기치 않은 오류</span><span class="sxs-lookup"><span data-stu-id="f679e-170">Unexpected error</span></span> | <span data-ttu-id="f679e-171">요청을 자동으로 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f679e-171">Your request could not be automatically processed.</span></span> <span data-ttu-id="f679e-172">지원 서비스에<support link>문의 () 하 고 요청 ID를 제공 합니다.<requestId></span><span class="sxs-lookup"><span data-stu-id="f679e-172">Contact Support (<support link>) and provide the Request ID: <requestId></span></span> |
