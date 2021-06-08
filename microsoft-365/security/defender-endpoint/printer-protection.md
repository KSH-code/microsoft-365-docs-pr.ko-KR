---
title: 끝점 장치 제어 프린터 보호용 Microsoft Defender
description: Microsoft Defender for Endpoint Device Control Printer Protection은 회사용이 아닌 프린터 또는 승인되지 않은 USB 프린터를 통해 인쇄할 수 없습니다.
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.author: v-lsaldanha
author: lovina-saldanha
ms.reviewer: dansimp
manager: dansimp
audience: ITPro
ms.technology: mde
ms.openlocfilehash: 431497ded684543c33d91c49a0da47e92297321f
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809263"
---
# <a name="device-control-printer-protection"></a><span data-ttu-id="3adcd-103">장치 제어 프린터 보호</span><span class="sxs-lookup"><span data-stu-id="3adcd-103">Device Control Printer Protection</span></span> 

<span data-ttu-id="3adcd-104">Microsoft Defender for Endpoint Device Control Printer Protection은 회사용이 아닌 프린터 또는 승인되지 않은 USB 프린터를 통해 인쇄할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3adcd-104">Microsoft Defender for Endpoint Device Control Printer Protection blocks people from printing via non-corporate printers or non-approved USB printer.</span></span>

## <a name="licensing"></a><span data-ttu-id="3adcd-105">라이선싱</span><span class="sxs-lookup"><span data-stu-id="3adcd-105">Licensing</span></span> 

<span data-ttu-id="3adcd-106">프린터 보호를 시작하기 전에 프린터 보호 [구독을 Microsoft 365 합니다.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)</span><span class="sxs-lookup"><span data-stu-id="3adcd-106">Before you get started with Printer Protection, you should [confirm your Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1).</span></span> <span data-ttu-id="3adcd-107">프린터 보호에 액세스하고 사용하려면 다음이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3adcd-107">To access and use Printer Protection, you must have the following:</span></span>

- <span data-ttu-id="3adcd-108">Microsoft 365 E3/정책 배포에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="3adcd-108">Microsoft 365 E3 for functionality/policy deployment</span></span> 
- <span data-ttu-id="3adcd-109">Microsoft 365 E5 위한 보고서</span><span class="sxs-lookup"><span data-stu-id="3adcd-109">Microsoft 365 E5 for reporting</span></span> 

## <a name="permission"></a><span data-ttu-id="3adcd-110">사용 권한</span><span class="sxs-lookup"><span data-stu-id="3adcd-110">Permission</span></span> 

<span data-ttu-id="3adcd-111">Intune의 정책 배포의 경우 OMA-URI를 통해 정책을 배포하려면 계정에 장치 구성 프로필을 만들거나 편집, 업데이트 또는 삭제할 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3adcd-111">For Policy deployment in Intune, to deploy policy via OMA-URI, the account must have permissions to create, edit, update, or delete device configuration profiles.</span></span> <span data-ttu-id="3adcd-112">다음 사용 권한으로 사용자 지정 역할을 만들거나 기본 제공 역할을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3adcd-112">You can create custom roles or use any of the built-in roles with these permissions:</span></span>  

- <span data-ttu-id="3adcd-113">정책 및 프로필 관리자 역할</span><span class="sxs-lookup"><span data-stu-id="3adcd-113">Policy and profile Manager role.</span></span> 
- <span data-ttu-id="3adcd-114">또는 장치 구성 프로필에 대해 보고서 만들기/편집/업데이트/읽기/삭제/보기 권한이 설정되어 있는 사용자 지정 역할</span><span class="sxs-lookup"><span data-stu-id="3adcd-114">Or custom role with Create/Edit/Update/Read/Delete/View Reports permissions turned on for Device Configuration profiles</span></span>  
- <span data-ttu-id="3adcd-115">또는 전역 관리자</span><span class="sxs-lookup"><span data-stu-id="3adcd-115">Or Global admin</span></span>

<span data-ttu-id="3adcd-116">장치 구성 보고서를 확인하려면 계정에 보고서 보기 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3adcd-116">To see device configuration reports, the account must have view reports permissions.</span></span> <span data-ttu-id="3adcd-117">다음 사용 권한으로 사용자 지정 역할을 만들거나 기본 제공 역할을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3adcd-117">You can create custom roles or use the built-in roles with these permissions:</span></span>  

- <span data-ttu-id="3adcd-118">전역 보안 관리자</span><span class="sxs-lookup"><span data-stu-id="3adcd-118">Global security admin</span></span>
- <span data-ttu-id="3adcd-119">보안 관리자</span><span class="sxs-lookup"><span data-stu-id="3adcd-119">Security admin</span></span>
- <span data-ttu-id="3adcd-120">보안 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="3adcd-120">Security Reader</span></span> 

## <a name="prepare-your-endpoints"></a><span data-ttu-id="3adcd-121">엔드포인트 준비하기</span><span class="sxs-lookup"><span data-stu-id="3adcd-121">Prepare your endpoints</span></span>

<span data-ttu-id="3adcd-122">이러한 요구 사항을 Windows 10 프린터 보호를 배포할 계획인 디바이스가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3adcd-122">Make sure that the Windows 10 devices that you plan on deploying Printer Protection to meet these requirements.</span></span>

1. <span data-ttu-id="3adcd-123">Insider 프로그램에 참여합니다.</span><span class="sxs-lookup"><span data-stu-id="3adcd-123">Join the Insider Program.</span></span>

1. <span data-ttu-id="3adcd-124">다음 Windows 업데이트가 설치되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3adcd-124">The following Windows Updates are installed.</span></span> 

    - <span data-ttu-id="3adcd-125">1809 Windows: 업데이트 Windows [KB5003217](https://support.microsoft.com/en-us/topic/may-20-2021-kb5003217-os-build-17763-1971-preview-08687c95-0740-421b-a205-54aa2c716b46) 설치</span><span class="sxs-lookup"><span data-stu-id="3adcd-125">For Windows 1809: install Windows Update [KB5003217](https://support.microsoft.com/en-us/topic/may-20-2021-kb5003217-os-build-17763-1971-preview-08687c95-0740-421b-a205-54aa2c716b46)</span></span> 
    - <span data-ttu-id="3adcd-126">1909 Windows: 업데이트 Windows [KB5003212](https://support.microsoft.com/en-us/topic/may-20-2021-kb5003212-os-build-18363-1593-preview-05381524-8380-4b30-b783-e330cad3d4a1) 설치</span><span class="sxs-lookup"><span data-stu-id="3adcd-126">For Windows 1909: install Windows Update [KB5003212](https://support.microsoft.com/en-us/topic/may-20-2021-kb5003212-os-build-18363-1593-preview-05381524-8380-4b30-b783-e330cad3d4a1)</span></span>
    - <span data-ttu-id="3adcd-127">2004 Windows</span><span class="sxs-lookup"><span data-stu-id="3adcd-127">For Windows 2004 or later</span></span> 
    
1. <span data-ttu-id="3adcd-128">그룹 정책을 통해 정책을 배포하려면 장치를 연결해야 MDATP 합니다. MEM을 통해 정책을 배포하려면 장치가 Intune에 가입되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3adcd-128">If you're planning to deploy policy via Group Policy, the device must be MDATP joined; if you're planning to deploy policy via MEM, the device must be Intune joined.</span></span>

## <a name="deploy-device-control-printer-protection-policy"></a><span data-ttu-id="3adcd-129">장치 제어 프린터 보호 정책 배포</span><span class="sxs-lookup"><span data-stu-id="3adcd-129">Deploy Device Control Printer Protection policy</span></span>

<span data-ttu-id="3adcd-130">그룹 정책 또는 Intune을 통해 정책을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3adcd-130">You can deploy the policy via Group Policy or Intune.</span></span>

| <span data-ttu-id="3adcd-131">제목</span><span class="sxs-lookup"><span data-stu-id="3adcd-131">Title</span></span> | <span data-ttu-id="3adcd-132">설명</span><span class="sxs-lookup"><span data-stu-id="3adcd-132">Description</span></span> | <span data-ttu-id="3adcd-133">CSP 지원</span><span class="sxs-lookup"><span data-stu-id="3adcd-133">CSP Support</span></span> | <span data-ttu-id="3adcd-134">GPO 지원</span><span class="sxs-lookup"><span data-stu-id="3adcd-134">GPO Support</span></span> | <span data-ttu-id="3adcd-135">사용자 기반 지원</span><span class="sxs-lookup"><span data-stu-id="3adcd-135">User-based Support</span></span> | <span data-ttu-id="3adcd-136">컴퓨터 기반 지원</span><span class="sxs-lookup"><span data-stu-id="3adcd-136">Machine-based Support</span></span> |
|:--|:--|:--|:--|:--|:--|
|<span data-ttu-id="3adcd-137">**장치 컨트롤 인쇄 제한 사용**</span><span class="sxs-lookup"><span data-stu-id="3adcd-137">**Enable Device control Printing Restrictions**</span></span>|<span data-ttu-id="3adcd-138">회사용이 아닌 프린터를 통해 인쇄할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3adcd-138">Block people from printing via non-corporate printer</span></span>|<span data-ttu-id="3adcd-139">예</span><span class="sxs-lookup"><span data-stu-id="3adcd-139">Yes</span></span>|<span data-ttu-id="3adcd-140">예</span><span class="sxs-lookup"><span data-stu-id="3adcd-140">Yes</span></span>|<span data-ttu-id="3adcd-141">예</span><span class="sxs-lookup"><span data-stu-id="3adcd-141">Yes</span></span>|<span data-ttu-id="3adcd-142">예</span><span class="sxs-lookup"><span data-stu-id="3adcd-142">Yes</span></span>|
|<span data-ttu-id="3adcd-143">**승인된 USB 연결 인쇄 장치 목록**\*</span><span class="sxs-lookup"><span data-stu-id="3adcd-143">**List of Approved USB-connected print devices** \*</span></span>|<span data-ttu-id="3adcd-144">특정 USB 프린터 허용</span><span class="sxs-lookup"><span data-stu-id="3adcd-144">Allow specific USB printer</span></span>|<span data-ttu-id="3adcd-145">예</span><span class="sxs-lookup"><span data-stu-id="3adcd-145">Yes</span></span>|<span data-ttu-id="3adcd-146">예</span><span class="sxs-lookup"><span data-stu-id="3adcd-146">Yes</span></span>|<span data-ttu-id="3adcd-147">예</span><span class="sxs-lookup"><span data-stu-id="3adcd-147">Yes</span></span>|<span data-ttu-id="3adcd-148">예</span><span class="sxs-lookup"><span data-stu-id="3adcd-148">Yes</span></span>|
|||||||

<span data-ttu-id="3adcd-149">\* 이 정책은 장치 컨트롤 인쇄 제한 **사용과 함께 사용되어야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="3adcd-149">\* This policy must be used together with **Enable Device control Printing Restrictions**</span></span>
## <a name="deploy-policy-via-intune"></a><span data-ttu-id="3adcd-150">Intune을 통해 정책 배포</span><span class="sxs-lookup"><span data-stu-id="3adcd-150">Deploy policy via Intune</span></span> 

<span data-ttu-id="3adcd-151">Intune의 경우 현재 장치 제어 프린터 보호는 OMA-URI만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="3adcd-151">For Intune, currently Device Control Printer Protection supports OMA-URI only.</span></span>

<span data-ttu-id="3adcd-152">**시나리오 1: 회사용이 아닌 프린터를 통해 인쇄하지 못하게 차단**</span><span class="sxs-lookup"><span data-stu-id="3adcd-152">**Scenario 1: Block people from printing via any non-corporate printer**</span></span> 

 - <span data-ttu-id="3adcd-153">컴퓨터 위에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="3adcd-153">Apply policy over machine:</span></span> 

    - <span data-ttu-id="3adcd-154">./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControl</span><span class="sxs-lookup"><span data-stu-id="3adcd-154">./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControl</span></span> 

- <span data-ttu-id="3adcd-155">사용자에 대한 정책 적용:</span><span class="sxs-lookup"><span data-stu-id="3adcd-155">Apply policy over user:</span></span> 

    - <span data-ttu-id="3adcd-156">./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControlUser</span><span class="sxs-lookup"><span data-stu-id="3adcd-156">./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControlUser</span></span> 

<span data-ttu-id="3adcd-157">CSP 지원 문자열은 `` <enabled/>`` 입니다.</span><span class="sxs-lookup"><span data-stu-id="3adcd-157">The CSP support string with `` <enabled/>``:</span></span> 

:::image type="content" source="../../media/customeditrow.png" alt-text="사용자 지정 편집 행":::

<span data-ttu-id="3adcd-159">**시나리오 2: 특정 승인된 USB 프린터 허용**</span><span class="sxs-lookup"><span data-stu-id="3adcd-159">**Scenario 2: Allow specific approved USB printers**</span></span>

- <span data-ttu-id="3adcd-160">컴퓨터 위에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="3adcd-160">Apply policy over machine:</span></span> 

    - <span data-ttu-id="3adcd-161">./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevices</span><span class="sxs-lookup"><span data-stu-id="3adcd-161">./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevices</span></span> 

- <span data-ttu-id="3adcd-162">사용자에 대한 정책 적용:</span><span class="sxs-lookup"><span data-stu-id="3adcd-162">Apply policy over user:</span></span> 

    - <span data-ttu-id="3adcd-163">./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevicesUser</span><span class="sxs-lookup"><span data-stu-id="3adcd-163">./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevicesUser</span></span>  

<span data-ttu-id="3adcd-164">'ApprovedUsbPrintDevices' 속성을 통해 승인된 USB 프린터가 있는 CSP 지원 문자열(예: `` <enabled/><data id="ApprovedUsbPrintDevices_List" value="03F0/0853,0351/0872"/>`` :</span><span class="sxs-lookup"><span data-stu-id="3adcd-164">The CSP support string with approved USB printers via ‘ApprovedUsbPrintDevices’ property, example `` <enabled/><data id="ApprovedUsbPrintDevices_List" value="03F0/0853,0351/0872"/>``:</span></span> 

:::image type="content" source="../../media/editrow.png" alt-text="행 편집":::

## <a name="deploy-policy-via-group-policy"></a><span data-ttu-id="3adcd-166">그룹 정책을 통해 정책 배포</span><span class="sxs-lookup"><span data-stu-id="3adcd-166">Deploy policy via Group Policy</span></span> 

<span data-ttu-id="3adcd-167">장치가 Intune에 가입되지 않은 경우 그룹 정책을 통해 정책을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3adcd-167">If the device isn't Intune joined, you can also deploy the policy via Group Policy.</span></span> 

<span data-ttu-id="3adcd-168">**시나리오 1: 회사용이 아닌 프린터를 통해 인쇄하지 못하게 차단**</span><span class="sxs-lookup"><span data-stu-id="3adcd-168">**Scenario 1: Block people from printing via any non-corporate printer**</span></span> 

- <span data-ttu-id="3adcd-169">컴퓨터 위에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="3adcd-169">Apply policy over machine:</span></span> 

    - <span data-ttu-id="3adcd-170">컴퓨터 구성 > 관리 템플릿 >: 장치 제어 인쇄 제한 사용</span><span class="sxs-lookup"><span data-stu-id="3adcd-170">Computer Configuration > Administrative Templates > Printer: Enable Device control Printing Restrictions</span></span> 

- <span data-ttu-id="3adcd-171">사용자에 대한 정책 적용:</span><span class="sxs-lookup"><span data-stu-id="3adcd-171">Apply policy over user:</span></span> 

    - <span data-ttu-id="3adcd-172">사용자 구성 > 관리 템플릿 > 제어판 >: 장치 제어 인쇄 제한 사용</span><span class="sxs-lookup"><span data-stu-id="3adcd-172">User Configuration > Administrative Templates > Control Panel > Printers: Enable Device control Printing Restrictions</span></span> 

:::image type="content" source="../../media/enable-device-ctrl-printing-restrictions.png" alt-text="장치 인쇄 제한 사용":::
 

<span data-ttu-id="3adcd-174">**시나리오 2: 특정 승인된 USB 프린터 허용**</span><span class="sxs-lookup"><span data-stu-id="3adcd-174">**Scenario 2: Allow specific approved USB printers**</span></span>

- <span data-ttu-id="3adcd-175">컴퓨터 위에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="3adcd-175">Apply policy over machine:</span></span> 

    - <span data-ttu-id="3adcd-176">컴퓨터 구성 > 관리 템플릿 >: 승인된 USB 연결 인쇄 장치 목록</span><span class="sxs-lookup"><span data-stu-id="3adcd-176">Computer Configuration > Administrative Templates > Printer:  List of Approved USB-connected print devices</span></span> 

- <span data-ttu-id="3adcd-177">사용자에 대한 정책 적용:</span><span class="sxs-lookup"><span data-stu-id="3adcd-177">Apply policy over user:</span></span>  

    - <span data-ttu-id="3adcd-178">사용자 구성 > 관리 템플릿 > 제어판 >: 승인된 USB 연결 인쇄 장치 목록</span><span class="sxs-lookup"><span data-stu-id="3adcd-178">User Configuration > Administrative Templates > Control Panel > Printers: List of Approved USB-connected print devices</span></span> 
 
 :::image type="content" source="../../media/list-of-approved-connected-print-devices.png" alt-text="승인된 USB 연결 인쇄 장치 목록":::

## <a name="view-device-control-printer-protection-data-in-microsoft-defender-for-endpoint-portal"></a><span data-ttu-id="3adcd-180">끝점 포털용 Microsoft Defender에서 장치 제어 프린터 보호 데이터 보기</span><span class="sxs-lookup"><span data-stu-id="3adcd-180">View Device Control Printer Protection data in Microsoft Defender for Endpoint portal</span></span> 

<span data-ttu-id="3adcd-181">Microsoft 365 [보안 센터에는](https://security.microsoft.com) 위의 장치 제어 프린터 보호 정책에 의해 차단된 인쇄가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3adcd-181">The [Microsoft 365 security center](https://security.microsoft.com) shows printing blocked by the Device Control Printer Protection policy above.</span></span>
 
```sql
DeviceEvents 

|where ActionType == 'PrintJobBlocked' 

| extend parsed=parse_json(AdditionalFields) 

| extend PrintedFile=tostring(parsed.JobOrDocumentName) 

| extend PrintPortName=tostring(parsed.PortName) 

| extend PrinterName=tostring(parsed.PrinterName) 

| extend Policy=tostring(parsed.RestrictionReason)  

| project Timestamp, DeviceId, DeviceName, ActionType, InitiatingProcessAccountName,Policy, PrintedFile, PrinterName, PrintPortName, AdditionalFields 

| order by Timestamp desc 
```

 :::image type="content" source="../../media/device-control-advanced-hunting.png" alt-text="고급 헌팅":::
