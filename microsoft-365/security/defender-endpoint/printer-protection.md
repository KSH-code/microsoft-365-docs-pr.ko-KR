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
ms.topic: article
ms.openlocfilehash: 0f089efedef1e4fb6b146692da3f1a630f2bacac
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289694"
---
# <a name="device-control-printer-protection"></a><span data-ttu-id="903ea-103">장치 제어 프린터 보호</span><span class="sxs-lookup"><span data-stu-id="903ea-103">Device Control Printer Protection</span></span>

<span data-ttu-id="903ea-104">Microsoft Defender for Endpoint Device Control Printer Protection은 회사용이 아닌 프린터 또는 승인되지 않은 USB 프린터를 통해 인쇄할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="903ea-104">Microsoft Defender for Endpoint Device Control Printer Protection blocks people from printing via non-corporate printers or non-approved USB printer.</span></span>

## <a name="licensing"></a><span data-ttu-id="903ea-105">라이선싱</span><span class="sxs-lookup"><span data-stu-id="903ea-105">Licensing</span></span>

<span data-ttu-id="903ea-106">프린터 보호를 시작하기 전에 프린터 보호 [구독을 Microsoft 365 합니다.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)</span><span class="sxs-lookup"><span data-stu-id="903ea-106">Before you get started with Printer Protection, you should [confirm your Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1).</span></span> <span data-ttu-id="903ea-107">프린터 보호에 액세스하고 사용하려면 다음이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="903ea-107">To access and use Printer Protection, you must have the following:</span></span>

- <span data-ttu-id="903ea-108">Microsoft 365 E3/정책 배포에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="903ea-108">Microsoft 365 E3 for functionality/policy deployment</span></span>
- <span data-ttu-id="903ea-109">Microsoft 365 E5 위한 보고서</span><span class="sxs-lookup"><span data-stu-id="903ea-109">Microsoft 365 E5 for reporting</span></span>

## <a name="permission"></a><span data-ttu-id="903ea-110">사용 권한</span><span class="sxs-lookup"><span data-stu-id="903ea-110">Permission</span></span>

<span data-ttu-id="903ea-111">Intune의 정책 배포의 경우 OMA-URI를 통해 정책을 배포하려면 계정에 장치 구성 프로필을 만들거나 편집, 업데이트 또는 삭제할 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="903ea-111">For Policy deployment in Intune, to deploy policy via OMA-URI, the account must have permissions to create, edit, update, or delete device configuration profiles.</span></span> <span data-ttu-id="903ea-112">다음 사용 권한으로 사용자 지정 역할을 만들거나 기본 제공 역할을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="903ea-112">You can create custom roles or use any of the built-in roles with these permissions:</span></span>

- <span data-ttu-id="903ea-113">정책 및 프로필 관리자 역할</span><span class="sxs-lookup"><span data-stu-id="903ea-113">Policy and profile Manager role.</span></span>
- <span data-ttu-id="903ea-114">또는 장치 구성 프로필에 대해 보고서 만들기/편집/업데이트/읽기/삭제/보기 권한이 설정되어 있는 사용자 지정 역할</span><span class="sxs-lookup"><span data-stu-id="903ea-114">Or custom role with Create/Edit/Update/Read/Delete/View Reports permissions turned on for Device Configuration profiles</span></span>
- <span data-ttu-id="903ea-115">또는 전역 관리자</span><span class="sxs-lookup"><span data-stu-id="903ea-115">Or Global admin</span></span>

<span data-ttu-id="903ea-116">장치 구성 보고서를 확인하려면 계정에 보고서 보기 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="903ea-116">To see device configuration reports, the account must have view reports permissions.</span></span> <span data-ttu-id="903ea-117">다음 사용 권한으로 사용자 지정 역할을 만들거나 기본 제공 역할을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="903ea-117">You can create custom roles or use the built-in roles with these permissions:</span></span>

- <span data-ttu-id="903ea-118">전역 보안 관리자</span><span class="sxs-lookup"><span data-stu-id="903ea-118">Global security admin</span></span>
- <span data-ttu-id="903ea-119">보안 관리자</span><span class="sxs-lookup"><span data-stu-id="903ea-119">Security admin</span></span>
- <span data-ttu-id="903ea-120">보안 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="903ea-120">Security Reader</span></span>

## <a name="prepare-your-endpoints"></a><span data-ttu-id="903ea-121">엔드포인트 준비하기</span><span class="sxs-lookup"><span data-stu-id="903ea-121">Prepare your endpoints</span></span>

<span data-ttu-id="903ea-122">이러한 요구 사항을 Windows 10 프린터 보호를 배포할 계획인 디바이스가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="903ea-122">Make sure that the Windows 10 devices that you plan on deploying Printer Protection to meet these requirements.</span></span>

1. <span data-ttu-id="903ea-123">Insider 프로그램에 참여합니다.</span><span class="sxs-lookup"><span data-stu-id="903ea-123">Join the Insider Program.</span></span>

1. <span data-ttu-id="903ea-124">다음 Windows 업데이트가 설치되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="903ea-124">The following Windows Updates are installed.</span></span>
    - <span data-ttu-id="903ea-125">1809 Windows: 업데이트 Windows [KB5003217](https://support.microsoft.com/topic/may-20-2021-kb5003217-os-build-17763-1971-preview-08687c95-0740-421b-a205-54aa2c716b46) 설치</span><span class="sxs-lookup"><span data-stu-id="903ea-125">For Windows 1809: install Windows Update [KB5003217](https://support.microsoft.com/topic/may-20-2021-kb5003217-os-build-17763-1971-preview-08687c95-0740-421b-a205-54aa2c716b46)</span></span>
    - <span data-ttu-id="903ea-126">1909 Windows: 업데이트 Windows [KB5003212](https://support.microsoft.com/topic/may-20-2021-kb5003212-os-build-18363-1593-preview-05381524-8380-4b30-b783-e330cad3d4a1) 설치</span><span class="sxs-lookup"><span data-stu-id="903ea-126">For Windows 1909: install Windows Update [KB5003212](https://support.microsoft.com/topic/may-20-2021-kb5003212-os-build-18363-1593-preview-05381524-8380-4b30-b783-e330cad3d4a1)</span></span>
    - <span data-ttu-id="903ea-127">2004 Windows</span><span class="sxs-lookup"><span data-stu-id="903ea-127">For Windows 2004 or later</span></span>

1. <span data-ttu-id="903ea-128">그룹 정책을 통해 정책을 배포하려면 장치가 MDATP에 가입되어야 합니다. MEM을 통해 정책을 배포하려면 장치가 Intune에 가입되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="903ea-128">If you're planning to deploy policy via Group Policy, the device must be MDATP joined; if you're planning to deploy policy via MEM, the device must be Intune joined.</span></span>

## <a name="deploy-device-control-printer-protection-policy"></a><span data-ttu-id="903ea-129">장치 제어 프린터 보호 정책 배포</span><span class="sxs-lookup"><span data-stu-id="903ea-129">Deploy Device Control Printer Protection policy</span></span>

<span data-ttu-id="903ea-130">그룹 정책 또는 Intune을 통해 정책을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="903ea-130">You can deploy the policy via Group Policy or Intune.</span></span>

<br>

****

|<span data-ttu-id="903ea-131">제목</span><span class="sxs-lookup"><span data-stu-id="903ea-131">Title</span></span>|<span data-ttu-id="903ea-132">설명</span><span class="sxs-lookup"><span data-stu-id="903ea-132">Description</span></span>|<span data-ttu-id="903ea-133">CSP 지원</span><span class="sxs-lookup"><span data-stu-id="903ea-133">CSP Support</span></span> | <span data-ttu-id="903ea-134">GPO 지원</span><span class="sxs-lookup"><span data-stu-id="903ea-134">GPO Support</span></span> | <span data-ttu-id="903ea-135">사용자 기반 지원</span><span class="sxs-lookup"><span data-stu-id="903ea-135">User-based Support</span></span> | <span data-ttu-id="903ea-136">컴퓨터 기반 지원</span><span class="sxs-lookup"><span data-stu-id="903ea-136">Machine-based Support</span></span> |
|---|---|:---:|:---:|:---:|:---:|
|<span data-ttu-id="903ea-137">**장치 컨트롤 인쇄 제한 사용**</span><span class="sxs-lookup"><span data-stu-id="903ea-137">**Enable Device control Printing Restrictions**</span></span>|<span data-ttu-id="903ea-138">회사용이 아닌 프린터를 통해 인쇄할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="903ea-138">Block people from printing via non-corporate printer</span></span>|<span data-ttu-id="903ea-139">예</span><span class="sxs-lookup"><span data-stu-id="903ea-139">Yes</span></span>|<span data-ttu-id="903ea-140">예</span><span class="sxs-lookup"><span data-stu-id="903ea-140">Yes</span></span>|<span data-ttu-id="903ea-141">예</span><span class="sxs-lookup"><span data-stu-id="903ea-141">Yes</span></span>|<span data-ttu-id="903ea-142">예</span><span class="sxs-lookup"><span data-stu-id="903ea-142">Yes</span></span>|
|<span data-ttu-id="903ea-143">**승인된 USB 연결 인쇄 장치 목록**\*</span><span class="sxs-lookup"><span data-stu-id="903ea-143">**List of Approved USB-connected print devices**\*</span></span>|<span data-ttu-id="903ea-144">특정 USB 프린터 허용</span><span class="sxs-lookup"><span data-stu-id="903ea-144">Allow specific USB printer</span></span>|<span data-ttu-id="903ea-145">예</span><span class="sxs-lookup"><span data-stu-id="903ea-145">Yes</span></span>|<span data-ttu-id="903ea-146">예</span><span class="sxs-lookup"><span data-stu-id="903ea-146">Yes</span></span>|<span data-ttu-id="903ea-147">예</span><span class="sxs-lookup"><span data-stu-id="903ea-147">Yes</span></span>|<span data-ttu-id="903ea-148">예</span><span class="sxs-lookup"><span data-stu-id="903ea-148">Yes</span></span>|
|

<span data-ttu-id="903ea-149">\*이 정책은 장치 컨트롤 인쇄 제한 **사용과 함께 사용되어야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="903ea-149">\* This policy must be used together with **Enable Device control Printing Restrictions**.</span></span>

## <a name="deploy-policy-via-intune"></a><span data-ttu-id="903ea-150">Intune을 통해 정책 배포</span><span class="sxs-lookup"><span data-stu-id="903ea-150">Deploy policy via Intune</span></span>

<span data-ttu-id="903ea-151">Intune의 경우 현재 장치 제어 프린터 보호는 OMA-URI만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="903ea-151">For Intune, currently Device Control Printer Protection supports OMA-URI only.</span></span>

### <a name="scenario-1-block-people-from-printing-via-any-non-corporate-printer-using-intune"></a><span data-ttu-id="903ea-152">시나리오 1: Intune을 사용하여 회사용이 아닌 프린터를 통해 인쇄하지 못하게 차단</span><span class="sxs-lookup"><span data-stu-id="903ea-152">Scenario 1: Block people from printing via any non-corporate printer using Intune</span></span>

- <span data-ttu-id="903ea-153">컴퓨터 위에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="903ea-153">Apply policy over machine:</span></span>

  `./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControl`

- <span data-ttu-id="903ea-154">사용자에 대한 정책 적용:</span><span class="sxs-lookup"><span data-stu-id="903ea-154">Apply policy over user:</span></span>

  `./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControlUser`

<span data-ttu-id="903ea-155">CSP 지원 문자열은 `<enabled/>` 입니다.</span><span class="sxs-lookup"><span data-stu-id="903ea-155">The CSP support string with `<enabled/>`:</span></span>

:::image type="content" source="../../media/customeditrow.png" alt-text="사용자 지정 편집 행":::

### <a name="scenario-2-allow-specific-approved-usb-printers-using-intune"></a><span data-ttu-id="903ea-157">시나리오 2: Intune을 사용하여 승인된 특정 USB 프린터 허용</span><span class="sxs-lookup"><span data-stu-id="903ea-157">Scenario 2: Allow specific approved USB printers using Intune</span></span>

- <span data-ttu-id="903ea-158">컴퓨터 위에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="903ea-158">Apply policy over machine:</span></span>

  `./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevices`

- <span data-ttu-id="903ea-159">사용자에 대한 정책 적용:</span><span class="sxs-lookup"><span data-stu-id="903ea-159">Apply policy over user:</span></span>

  `./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevicesUser`

<span data-ttu-id="903ea-160">'ApprovedUsbPrintDevices' 속성을 통해 승인된 USB 프린터가 있는 CSP 지원 문자열(예: `<enabled><data id="ApprovedUsbPrintDevices_List" value="03F0/0853,0351/0872">` :</span><span class="sxs-lookup"><span data-stu-id="903ea-160">The CSP support string with approved USB printers via 'ApprovedUsbPrintDevices' property, example `<enabled><data id="ApprovedUsbPrintDevices_List" value="03F0/0853,0351/0872">`:</span></span>

:::image type="content" source="../../media/editrow.png" alt-text="행 편집":::

## <a name="deploy-policy-via-group-policy"></a><span data-ttu-id="903ea-162">그룹 정책을 통해 정책 배포</span><span class="sxs-lookup"><span data-stu-id="903ea-162">Deploy policy via Group Policy</span></span>

<span data-ttu-id="903ea-163">장치가 Intune에 가입되지 않은 경우 그룹 정책을 통해 정책을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="903ea-163">If the device isn't Intune joined, you can also deploy the policy via Group Policy.</span></span>

### <a name="scenario-1-block-people-from-printing-via-any-non-corporate-printer-using-group-policy"></a><span data-ttu-id="903ea-164">시나리오 1: 그룹 정책을 사용하여 회사용이 아닌 프린터를 통해 인쇄하지 못하게 차단</span><span class="sxs-lookup"><span data-stu-id="903ea-164">Scenario 1: Block people from printing via any non-corporate printer using Group Policy</span></span>

- <span data-ttu-id="903ea-165">컴퓨터 위에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="903ea-165">Apply policy over machine:</span></span>

  <span data-ttu-id="903ea-166">컴퓨터 구성 \> 관리 템플릿 \> 프린터: 장치 제어 인쇄 제한 사용</span><span class="sxs-lookup"><span data-stu-id="903ea-166">Computer Configuration \> Administrative Templates \> Printer: Enable Device control Printing Restrictions</span></span>

- <span data-ttu-id="903ea-167">사용자에 대한 정책 적용:</span><span class="sxs-lookup"><span data-stu-id="903ea-167">Apply policy over user:</span></span>

  <span data-ttu-id="903ea-168">사용자 구성 \> 관리 템플릿 \> 제어판 프린터: 장치 제어 인쇄 제한 \> 사용</span><span class="sxs-lookup"><span data-stu-id="903ea-168">User Configuration \> Administrative Templates \> Control Panel \> Printers: Enable Device control Printing Restrictions</span></span>

:::image type="content" source="../../media/enable-device-ctrl-printing-restrictions.png" alt-text="장치 인쇄 제한 사용":::

### <a name="scenario-2-allow-specific-approved-usb-printers-using-group-policy"></a><span data-ttu-id="903ea-170">시나리오 2: 그룹 정책을 사용하여 승인된 특정 USB 프린터 허용</span><span class="sxs-lookup"><span data-stu-id="903ea-170">Scenario 2: Allow specific approved USB printers using Group Policy</span></span>

- <span data-ttu-id="903ea-171">컴퓨터 위에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="903ea-171">Apply policy over machine:</span></span>

  <span data-ttu-id="903ea-172">컴퓨터 구성 \> 관리 템플릿 \> 프린터: 승인된 USB 연결 인쇄 장치 목록</span><span class="sxs-lookup"><span data-stu-id="903ea-172">Computer Configuration \> Administrative Templates \> Printer:  List of Approved USB-connected print devices</span></span>

- <span data-ttu-id="903ea-173">사용자에 대한 정책 적용:</span><span class="sxs-lookup"><span data-stu-id="903ea-173">Apply policy over user:</span></span>

  <span data-ttu-id="903ea-174">사용자 구성 \> 관리 템플릿 \> 제어판 \> 프린터: 승인된 USB 연결 인쇄 장치 목록</span><span class="sxs-lookup"><span data-stu-id="903ea-174">User Configuration \> Administrative Templates \> Control Panel \> Printers: List of Approved USB-connected print devices</span></span>

:::image type="content" source="../../media/list-of-approved-connected-print-devices.png" alt-text="승인된 USB 연결 인쇄 장치 목록":::

## <a name="view-device-control-printer-protection-data-in-microsoft-defender-for-endpoint-portal"></a><span data-ttu-id="903ea-176">끝점 포털용 Microsoft Defender에서 장치 제어 프린터 보호 데이터 보기</span><span class="sxs-lookup"><span data-stu-id="903ea-176">View Device Control Printer Protection data in Microsoft Defender for Endpoint portal</span></span>

<span data-ttu-id="903ea-177">Microsoft 365 [보안 센터에는](https://security.microsoft.com) 위의 장치 제어 프린터 보호 정책에 의해 차단된 인쇄가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="903ea-177">The [Microsoft 365 security center](https://security.microsoft.com) shows printing blocked by the Device Control Printer Protection policy above.</span></span>

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
