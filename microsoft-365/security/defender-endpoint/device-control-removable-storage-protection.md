---
title: Microsoft Defender for Endpoint Device Control 이동식 Storage 보호
description: 사용자 또는 컴퓨터 또는 둘 다 권한이 없는 이동식 저장소 미디어를 사용하지 못하도록 하는 '기능' 이해
keywords: 이동식 저장소 미디어
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-smandalika
author: v-smandalika
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 55171429d3ea447de32eb7e2ec12b8b2c3542e95
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861710"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-protection"></a><span data-ttu-id="9f084-104">Microsoft Defender for Endpoint Device Control 이동식 Storage 보호</span><span class="sxs-lookup"><span data-stu-id="9f084-104">Microsoft Defender for Endpoint Device Control Removable Storage Protection</span></span>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="9f084-105">Microsoft Defender for Endpoint Device Control 이동식 Storage 보호는 사용자 또는 컴퓨터 또는 둘 다 권한이 없는 이동식 저장소 미디어를 사용하지 못하도록 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="9f084-105">Microsoft Defender for Endpoint Device Control Removable Storage Protection prevents user or machine or both from using unauthorized removable storage media.</span></span>

## <a name="protection-policies"></a><span data-ttu-id="9f084-106">보호 정책</span><span class="sxs-lookup"><span data-stu-id="9f084-106">Protection policies</span></span>

### <a name="device-installation"></a><span data-ttu-id="9f084-107">장치 설치</span><span class="sxs-lookup"><span data-stu-id="9f084-107">Device installation</span></span>

<span data-ttu-id="9f084-108">**기능** - 다양한 장치 속성에 따라 제외를 포함하거나 제외하지 않고 설치하지 못하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f084-108">**Capabilities** - Prevent installation with or without exclusion based on various device properties.</span></span>

<span data-ttu-id="9f084-109">**Windows 10 지원 세부 정보**</span><span class="sxs-lookup"><span data-stu-id="9f084-109">**Windows 10 support details**</span></span>
- <span data-ttu-id="9f084-110">컴퓨터 수준에서 적용: 로그온한 사용자에 대해 동일한 정책이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f084-110">Applied at machine level: the same policy applies for any logged on user.</span></span>
- <span data-ttu-id="9f084-111">MEM 및 GPO를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="9f084-111">Supports MEM and GPO.</span></span>
- <span data-ttu-id="9f084-112">나열된['장치 속성'이](#device-properties)지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f084-112">Supported  ‘[Device Properties](#device-properties)’ as listed.</span></span>
- <span data-ttu-id="9f084-113">자세한 내용은 Windows [Microsoft Defender for Endpoint를](control-usb-devices-using-intune.md)사용하여 USB 장치 및 기타 이동식 미디어를 제어하는 방법을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9f084-113">For more information on Windows, see [How to control USB devices and other removable media using Microsoft Defender for Endpoint](control-usb-devices-using-intune.md).</span></span>

<span data-ttu-id="9f084-114">**지원되는 플랫폼** - Windows 10</span><span class="sxs-lookup"><span data-stu-id="9f084-114">**Supported Platform** - Windows 10</span></span>

<span data-ttu-id="9f084-115">**macOS 지원 세부 정보**</span><span class="sxs-lookup"><span data-stu-id="9f084-115">**macOS support details**</span></span>
- <span data-ttu-id="9f084-116">컴퓨터 수준에서 적용: 로그온한 사용자에 대해 동일한 정책이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f084-116">Applied at machine level: the same policy applies for any logged on user</span></span>
- <span data-ttu-id="9f084-117">macOS 관련 정보는 [macOS용 장치 제어를 참조하세요.](mac-device-control-overview.md)</span><span class="sxs-lookup"><span data-stu-id="9f084-117">For macOS specific information, see [Device control for macOS](mac-device-control-overview.md).</span></span>
 
<span data-ttu-id="9f084-118">**지원되는 플랫폼** - macOS 카탈로니아 10.15.4+(시스템 확장 사용 가능)</span><span class="sxs-lookup"><span data-stu-id="9f084-118">**Supported platform** - macOS Catalina 10.15.4+ (with system extensions enabled)</span></span>

### <a name="removable-storage-access-control"></a><span data-ttu-id="9f084-119">이동식 저장소 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="9f084-119">Removable storage Access Control</span></span>

<span data-ttu-id="9f084-120">**기능**</span><span class="sxs-lookup"><span data-stu-id="9f084-120">**Capabilities**</span></span>
- <span data-ttu-id="9f084-121">*감사* 제외를 포함하거나 제외하지 않고 다양한 장치 속성을 기반으로 이동식 저장소에 대한 액세스를 읽거나 쓰기 또는 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9f084-121">*Audit* Read or Write or Execute access to removable storage based on various device properties, with or without an exclusion.</span></span>
- <span data-ttu-id="9f084-122">*방지* 제외를 포함하거나 제외하지 않고 액세스 읽기 또는 쓰기 또는 실행 - 다양한 장치 속성에 따라 특정 장치를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="9f084-122">*Prevent* Read or Write or Execute access with or without an exclusion - Allow specific device based on various device properties.</span></span>

<span data-ttu-id="9f084-123">**Windows 10 지원 세부 정보**</span><span class="sxs-lookup"><span data-stu-id="9f084-123">**Windows 10 support details**</span></span>
- <span data-ttu-id="9f084-124">컴퓨터 또는 사용자 또는 둘 다에서 적용 - 특정 컴퓨터의 특정 이동식 저장소에 대한 읽기/쓰기/실행 액세스를 수행하는 특정 사용자만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="9f084-124">Applied at either machine or user or both – only allow specific people performing Read/Write/Execute access to specific removable storage on specific machine.</span></span>
- <span data-ttu-id="9f084-125">MEM OMA-URI 및 GPO를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="9f084-125">Support MEM OMA-URI and GPO.</span></span>
- <span data-ttu-id="9f084-126">나열된['장치 속성'이](#device-properties)지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f084-126">Supported  ‘[Device Properties](#device-properties)’ as listed.</span></span>
- <span data-ttu-id="9f084-127">이 기능의 Windows [이동식 저장소 액세스 제어를 참조합니다.](device-control-removable-storage-access-control.md)</span><span class="sxs-lookup"><span data-stu-id="9f084-127">For feature in Windows, see [Removable storage Access Control](device-control-removable-storage-access-control.md).</span></span>

<span data-ttu-id="9f084-128">**지원되는 플랫폼** - Windows 10</span><span class="sxs-lookup"><span data-stu-id="9f084-128">**Supported Platform** - Windows 10</span></span>

<span data-ttu-id="9f084-129">**macOS 지원 세부 정보**</span><span class="sxs-lookup"><span data-stu-id="9f084-129">**macOS support details**</span></span>
- <span data-ttu-id="9f084-130">컴퓨터 수준에서 적용: 로그온한 사용자에 대해 동일한 정책이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f084-130">Applied at machine level: the same policy applies for any logged on user.</span></span>
- <span data-ttu-id="9f084-131">macOS 관련 정보는 [macOS용 장치 제어를 참조하세요.](mac-device-control-overview.md)</span><span class="sxs-lookup"><span data-stu-id="9f084-131">For macOS specific information, see [Device control for macOS](mac-device-control-overview.md).</span></span>
 
<span data-ttu-id="9f084-132">**지원되는 플랫폼** - macOS 카탈로니아 10.15.4+(시스템 확장 사용 가능)</span><span class="sxs-lookup"><span data-stu-id="9f084-132">**Supported platform** - macOS Catalina 10.15.4+ (with system extensions enabled)</span></span>

### <a name="windows-portable-device-access-control"></a><span data-ttu-id="9f084-133">Windows 휴대용 장치 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="9f084-133">Windows Portable Device Access Control</span></span>

<span data-ttu-id="9f084-134">**기능** - 태블릿, 휴대용 장치와 [](/windows-hardware/drivers/portable/)같은 Windows 읽기 또는 쓰기 액세스 iPhone.</span><span class="sxs-lookup"><span data-stu-id="9f084-134">**Capabilities** - Deny Read or Write access to any [Windows Portable Device](/windows-hardware/drivers/portable/), for example: Tablet, iPhone.</span></span>

<span data-ttu-id="9f084-135">**설명**</span><span class="sxs-lookup"><span data-stu-id="9f084-135">**Description**</span></span>
- <span data-ttu-id="9f084-136">컴퓨터나 사용자 또는 둘 다에서 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f084-136">Applied at either machine or user or both.</span></span>
- <span data-ttu-id="9f084-137">MEM OMA-URI 및 GPO를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="9f084-137">Support MEM OMA-URI and GPO.</span></span>

<span data-ttu-id="9f084-138">**지원되는 플랫폼** - Windows 10</span><span class="sxs-lookup"><span data-stu-id="9f084-138">**Supported Platform** - Windows 10</span></span>

### <a name="endpoint-dlp-removable-storage"></a><span data-ttu-id="9f084-139">끝점 DLP 이동식 저장소</span><span class="sxs-lookup"><span data-stu-id="9f084-139">Endpoint DLP Removable storage</span></span>

<span data-ttu-id="9f084-140">**기능** - 사용자가 이동식 미디어 또는 USB 장치에 항목 또는 정보를 복사하지 못하도록 감사 또는 경고 또는 방지</span><span class="sxs-lookup"><span data-stu-id="9f084-140">**Capabilities** - Audit or Warn or Prevent a user from copying an item or information to removable media or USB device.</span></span>

<span data-ttu-id="9f084-141">**설명** - 자세한 내용은 Windows 끝점 데이터 손실 Microsoft 365 [정보를 참조하세요.](../../compliance/endpoint-dlp-learn-about.md)</span><span class="sxs-lookup"><span data-stu-id="9f084-141">**Description** - For more information on Windows, see [Learn about Microsoft 365 Endpoint data loss prevention](../../compliance/endpoint-dlp-learn-about.md).</span></span>

<span data-ttu-id="9f084-142">**지원되는 플랫폼** - Windows 10</span><span class="sxs-lookup"><span data-stu-id="9f084-142">**Supported Platform** - Windows 10</span></span>

### <a name="bitlocker"></a><span data-ttu-id="9f084-143">BitLocker</span><span class="sxs-lookup"><span data-stu-id="9f084-143">BitLocker</span></span> 

<span data-ttu-id="9f084-144">**기능**</span><span class="sxs-lookup"><span data-stu-id="9f084-144">**Capabilities**</span></span>
- <span data-ttu-id="9f084-145">보호되지 않은 이동식 드라이브에 기록할 데이터를 BitLocker 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="9f084-145">Block data to be written to removable drives that aren't BitLocker protected.</span></span>
- <span data-ttu-id="9f084-146">이동식 드라이브에 대한 액세스 차단(조직이 소유한 컴퓨터에서 암호화되지 않은 경우)</span><span class="sxs-lookup"><span data-stu-id="9f084-146">Block access to removable drives unless they were encrypted on a computer owned by your organization</span></span>
 
<span data-ttu-id="9f084-147">**설명** - 자세한 내용은 Windows - 이동식 [BitLocker 드라이브를 설정.](/mem/intune/protect/endpoint-security-disk-encryption-profile-settings)</span><span class="sxs-lookup"><span data-stu-id="9f084-147">**Description** - For more information on Windows, see [BitLocker – Removable Drive Settings](/mem/intune/protect/endpoint-security-disk-encryption-profile-settings).</span></span>

<span data-ttu-id="9f084-148">**지원되는 플랫폼** - Windows 10</span><span class="sxs-lookup"><span data-stu-id="9f084-148">**Supported Platform** - Windows 10</span></span>

## <a name="device-properties"></a><span data-ttu-id="9f084-149">장치 속성</span><span class="sxs-lookup"><span data-stu-id="9f084-149">Device properties</span></span>

<span data-ttu-id="9f084-150">Microsoft Defender for Endpoint Device Control 이동식 Storage 보호를 사용하면 아래 표에 설명된 속성에 따라 이동식 저장소 액세스를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f084-150">Microsoft Defender for Endpoint Device Control Removable Storage Protection allows you to restrict the removable storage access based on the properties described in the table below:</span></span>


|<span data-ttu-id="9f084-151">속성 이름</span><span class="sxs-lookup"><span data-stu-id="9f084-151">Property Name</span></span>  |<span data-ttu-id="9f084-152">적용 가능한 정책</span><span class="sxs-lookup"><span data-stu-id="9f084-152">Applicable Policies</span></span>  |<span data-ttu-id="9f084-153">운영 체제에 적용</span><span class="sxs-lookup"><span data-stu-id="9f084-153">Applies to Operating Systems</span></span>  |<span data-ttu-id="9f084-154">설명</span><span class="sxs-lookup"><span data-stu-id="9f084-154">Description</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="9f084-155">Device Class</span><span class="sxs-lookup"><span data-stu-id="9f084-155">Device Class</span></span>    |     [<span data-ttu-id="9f084-156">끝점용 Microsoft Defender를 사용하여 USB 장치 및 기타 이동식 미디어를 제어하는 방법</span><span class="sxs-lookup"><span data-stu-id="9f084-156">How to control USB devices and other removable media using Microsoft Defender for Endpoint</span></span>](control-usb-devices-using-intune.md)     |   <span data-ttu-id="9f084-157">Windows</span><span class="sxs-lookup"><span data-stu-id="9f084-157">Windows</span></span>      |  <span data-ttu-id="9f084-158">장치 ID 형식에 대한 자세한 내용은 장치 설정 [클래스 를 참조하세요.](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors)</span><span class="sxs-lookup"><span data-stu-id="9f084-158">For information about Device ID formats, see [device setup class](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors).</span></span> <span data-ttu-id="9f084-159">**참고:** 이동식 저장소뿐만 아니라 모든 장치에 장치 설치를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f084-159">**Note**: Device Installation can be applied to any devices, not only Removable storage.</span></span>       |
|<span data-ttu-id="9f084-160">기본 ID</span><span class="sxs-lookup"><span data-stu-id="9f084-160">Primary ID</span></span>   |     <span data-ttu-id="9f084-161">이동식 저장소 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="9f084-161">Removable storage Access Control</span></span>    |   <span data-ttu-id="9f084-162">Windows</span><span class="sxs-lookup"><span data-stu-id="9f084-162">Windows</span></span>      |      <span data-ttu-id="9f084-163">기본 ID에는 이동식 저장소 및 CD/DVD가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f084-163">The Primary ID includes removable storage and CD/DVD.</span></span>   |
|<span data-ttu-id="9f084-164">장치 ID</span><span class="sxs-lookup"><span data-stu-id="9f084-164">Device ID</span></span>     |  <span data-ttu-id="9f084-165">[끝점용 Microsoft Defender를](control-usb-devices-using-intune.md)사용하여 USB 장치 및 기타 이동식 미디어를 제어하는 방법 이동식 저장소 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="9f084-165">[How to control USB devices and other removable media using Microsoft Defender for Endpoint](control-usb-devices-using-intune.md); Removable storage Access Control</span></span>       |      <span data-ttu-id="9f084-166">Windows</span><span class="sxs-lookup"><span data-stu-id="9f084-166">Windows</span></span>   |    <span data-ttu-id="9f084-167">장치 ID 형식에 대한 자세한 내용은 표준 USB 식별자(예: USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07)를 참조하세요. [](/windows-hardware/drivers/install/standard-usb-identifiers)</span><span class="sxs-lookup"><span data-stu-id="9f084-167">For information about Device ID formats, see [Standard USB Identifiers](/windows-hardware/drivers/install/standard-usb-identifiers), for example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07</span></span>      |
|<span data-ttu-id="9f084-168">하드웨어 ID</span><span class="sxs-lookup"><span data-stu-id="9f084-168">Hardware ID</span></span>     |     <span data-ttu-id="9f084-169">[끝점용 Microsoft Defender를](control-usb-devices-using-intune.md)사용하여 USB 장치 및 기타 이동식 미디어를 제어하는 방법 이동식 저장소 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="9f084-169">[How to control USB devices and other removable media using Microsoft Defender for Endpoint](control-usb-devices-using-intune.md); Removable storage Access Control</span></span>    |     <span data-ttu-id="9f084-170">Windows</span><span class="sxs-lookup"><span data-stu-id="9f084-170">Windows</span></span>    |    <span data-ttu-id="9f084-171">시스템에서 장치를 식별한 문자열(예: USBSTOR\DiskGeneric_Flash_Disk______8.07) **참고:** 하드웨어 ID가 고유하지 않습니다. 다른 디바이스가 동일한 값을 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f084-171">A string identified the device in the system, for example, USBSTOR\DiskGeneric_Flash_Disk______8.07; **Note**: Hardware ID is not unique; different devices may share same value.</span></span>|
|<span data-ttu-id="9f084-172">인스턴스 ID</span><span class="sxs-lookup"><span data-stu-id="9f084-172">Instance ID</span></span>    | <span data-ttu-id="9f084-173">장치 설치 이동식 저장소 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="9f084-173">Device Installation; Removable storage Access Control</span></span>     |     <span data-ttu-id="9f084-174">Windows</span><span class="sxs-lookup"><span data-stu-id="9f084-174">Windows</span></span>    |   <span data-ttu-id="9f084-175">USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0과 같은 문자열은 시스템에서 장치를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="9f084-175">A string uniquely identifies the device in the system, for example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0</span></span>      |
|<span data-ttu-id="9f084-176">이름</span><span class="sxs-lookup"><span data-stu-id="9f084-176">Friendly Name</span></span>     |     <span data-ttu-id="9f084-177">이동식 저장소 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="9f084-177">Removable storage Access Control</span></span>    |   <span data-ttu-id="9f084-178">Windows</span><span class="sxs-lookup"><span data-stu-id="9f084-178">Windows</span></span>      |    <span data-ttu-id="9f084-179">장치에 연결된 문자열(예: 일반 플래시 디스크 USB 장치)</span><span class="sxs-lookup"><span data-stu-id="9f084-179">A string attached to the device, for example, Generic Flash Disk USB Device</span></span>     |
|<span data-ttu-id="9f084-180">공급업체 ID/제품 ID</span><span class="sxs-lookup"><span data-stu-id="9f084-180">Vendor ID / Product ID</span></span>     |  <span data-ttu-id="9f084-181">이동식 저장소 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="9f084-181">Removable storage Access Control</span></span>       |   <span data-ttu-id="9f084-182">Windows Mac</span><span class="sxs-lookup"><span data-stu-id="9f084-182">Windows Mac</span></span>      |     <span data-ttu-id="9f084-183">공급업체 ID는 USB 위원회가 공급업체에 할당하는 4자리 공급업체 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="9f084-183">Vendor ID is the four-digit vendor code that the USB committee assigns to the vendor.</span></span> <span data-ttu-id="9f084-184">제품 ID는 공급업체가 장치에 할당하는 4자리 제품 코드입니다. 와일드카드를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="9f084-184">Product ID is the four-digit product code that the vendor assigns to the device; Support wildcard.</span></span>    |
|<span data-ttu-id="9f084-185">Serial NumberId</span><span class="sxs-lookup"><span data-stu-id="9f084-185">Serial NumberId</span></span>     |     <span data-ttu-id="9f084-186">이동식 저장소 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="9f084-186">Removable storage Access Control</span></span>    |      <span data-ttu-id="9f084-187">Windows Mac</span><span class="sxs-lookup"><span data-stu-id="9f084-187">Windows Mac</span></span>   |     <span data-ttu-id="9f084-188">예: <SerialNumberId>002324B534BCB431B000058A</SerialNumberId></span><span class="sxs-lookup"><span data-stu-id="9f084-188">For example, <SerialNumberId>002324B534BCB431B000058A</SerialNumberId></span></span>    |

## <a name="related-topic"></a><span data-ttu-id="9f084-189">관련 항목</span><span class="sxs-lookup"><span data-stu-id="9f084-189">Related topic</span></span>

- [<span data-ttu-id="9f084-190">Microsoft Defender for Endpoint Device Control 이동식 Storage 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="9f084-190">Microsoft Defender for Endpoint Device Control Removable Storage Access Control</span></span>](device-control-removable-storage-access-control.md)

