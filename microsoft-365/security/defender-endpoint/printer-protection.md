---
title: 끝점 장치 제어 프린터 보호용 Microsoft Defender
description: Microsoft Defender for Endpoint Device Control Printer Protection은 회사용이 아닌 프린터 또는 승인되지 않은 USB 프린터를 통해 인쇄할 수 없습니다.
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.author: dansimp
author: lovina-saldanha
ms.reviewer: dansimp
manager: dansimp
audience: ITPro
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: 48a813765693c69cff726c6973959ee63200a357
ms.sourcegitcommit: dc26169e485c3a31e1af9a5f495be9db75c49760
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60753924"
---
# <a name="device-control-printer-protection"></a>장치 제어 프린터 보호

Microsoft Defender for Endpoint Device Control Printer Protection은 회사용이 아닌 프린터 또는 승인되지 않은 USB 프린터를 통해 인쇄할 수 없습니다.

## <a name="licensing"></a>라이선싱

프린터 보호를 시작하기 전에 프린터 보호 [구독을 Microsoft 365 합니다.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) 프린터 보호에 액세스하고 사용하려면 다음이 있어야 합니다.

- Microsoft 365 E3/정책 배포에 대한 자세한 정보
- Microsoft 365 E5 위한 보고서

## <a name="permission"></a>사용 권한

Intune의 정책 배포의 경우 OMA-URI를 통해 정책을 배포하려면 계정에 장치 구성 프로필을 만들거나 편집, 업데이트 또는 삭제할 권한이 있어야 합니다. 다음 사용 권한으로 사용자 지정 역할을 만들거나 기본 제공 역할을 사용할 수 있습니다.

- 정책 및 프로필 관리자 역할
- 또는 장치 구성 프로필에 대해 보고서 만들기/편집/업데이트/읽기/삭제/보기 권한이 설정되어 있는 사용자 지정 역할
- 또는 전역 관리자

장치 구성 보고서를 확인하려면 계정에 보고서 보기 권한이 있어야 합니다. 다음 사용 권한으로 사용자 지정 역할을 만들거나 기본 제공 역할을 사용할 수 있습니다.

- 전역 보안 관리자
- 보안 관리자
- 보안 읽기 권한자

## <a name="prepare-your-endpoints"></a>엔드포인트 준비하기

이러한 요구 사항을 Windows 10 프린터 보호를 배포할 계획인 디바이스가 있는지 확인합니다.

1. 다음 Windows 업데이트가 설치되어 있습니다.
    - 1809 Windows: 업데이트 Windows [KB5003217](https://support.microsoft.com/topic/may-20-2021-kb5003217-os-build-17763-1971-preview-08687c95-0740-421b-a205-54aa2c716b46) 설치
    - 1909 Windows: 업데이트 Windows [KB5003212](https://support.microsoft.com/topic/may-20-2021-kb5003212-os-build-18363-1593-preview-05381524-8380-4b30-b783-e330cad3d4a1) 설치
    - 2004 Windows

2. 그룹 정책을 통해 정책을 배포하려면 디바이스를 끝점용 Microsoft Defender에 온보딩해야 합니다. 정책을 통해 정책을 배포하려면 Microsoft Endpoint Manager 장치를 사용하여 가입해야 Microsoft Intune.

## <a name="deploy-device-control-printer-protection-policy"></a>장치 제어 프린터 보호 정책 배포

그룹 정책 또는 Intune을 통해 정책을 배포할 수 있습니다.

<br>

****

|제목|설명|CSP 지원 | GPO 지원 | 사용자 기반 지원 | 컴퓨터 기반 지원 |
|---|---|:---:|:---:|:---:|:---:|
|**장치 컨트롤 인쇄 제한 사용**|회사용이 아닌 프린터를 통해 인쇄할 수 없습니다.|예|예|예|예|
|**승인된 USB 연결 인쇄 장치 목록**\*|특정 USB 프린터 허용|예|예|예|예|
|

\*이 정책은 장치 컨트롤 인쇄 제한 **사용과 함께 사용되어야 합니다.**

## <a name="deploy-policy-via-intune"></a>Intune을 통해 정책 배포

Intune의 경우 현재 장치 제어 프린터 보호는 OMA-URI만 지원됩니다.

### <a name="scenario-1-block-people-from-printing-via-any-non-corporate-printer-using-intune"></a>시나리오 1: Intune을 사용하여 회사용이 아닌 프린터를 통해 인쇄하지 못하게 차단

- 컴퓨터 위에 정책을 적용합니다.

  `./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControl`

- 사용자에 대한 정책 적용:

  `./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControlUser`

CSP 지원 문자열은 `<enabled/>` 입니다.

:::image type="content" source="../../media/customeditrow.png" alt-text="사용자 지정 편집 행.":::

### <a name="scenario-2-allow-specific-approved-usb-printers-using-intune"></a>시나리오 2: Intune을 사용하여 승인된 특정 USB 프린터 허용

- 컴퓨터 위에 정책을 적용합니다.

  `./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevices`

- 사용자에 대한 정책 적용:

  `./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevicesUser`

'ApprovedUsbPrintDevices' 속성을 통해 승인된 USB 프린터가 있는 CSP 지원 문자열(예: `<enabled><data id="ApprovedUsbPrintDevices_List" value="03F0/0853,0351/0872">` :

:::image type="content" source="../../media/editrow.png" alt-text="행을 편집합니다.":::

## <a name="deploy-policy-via-group-policy"></a>그룹 정책을 통해 정책 배포

장치가 Intune에 가입되지 않은 경우 그룹 정책을 통해 정책을 배포할 수 있습니다.

### <a name="scenario-1-block-people-from-printing-via-any-non-corporate-printer-using-group-policy"></a>시나리오 1: 그룹 정책을 사용하여 회사용이 아닌 프린터를 통해 인쇄하지 못하게 차단

- 컴퓨터 위에 정책을 적용합니다.

  컴퓨터 구성 \> 관리 템플릿 \> 프린터: 장치 제어 인쇄 제한 사용

- 사용자에 대한 정책 적용:

  사용자 구성 \> 관리 템플릿 \> 제어판 프린터: 장치 제어 인쇄 제한 \> 사용

:::image type="content" source="../../media/enable-device-ctrl-printing-restrictions.png" alt-text="디바이스 인쇄 제한을 사용하도록 설정":::

### <a name="scenario-2-allow-specific-approved-usb-printers-using-group-policy"></a>시나리오 2: 그룹 정책을 사용하여 승인된 특정 USB 프린터 허용

- 컴퓨터 위에 정책을 적용합니다.

  컴퓨터 구성 \> 관리 템플릿 \> 프린터: 승인된 USB 연결 인쇄 장치 목록

- 사용자에 대한 정책 적용:

  사용자 구성 \> 관리 템플릿 \> 제어판 \> 프린터: 승인된 USB 연결 인쇄 장치 목록

:::image type="content" source="../../media/list-of-approved-connected-print-devices.png" alt-text="승인된 USB 연결 인쇄 장치 목록입니다.":::

## <a name="view-device-control-printer-protection-data-in-microsoft-defender-for-endpoint-portal"></a>끝점 포털용 Microsoft Defender에서 장치 제어 프린터 보호 데이터 보기

Microsoft 365 [보안 센터에는](https://security.microsoft.com) 위의 장치 제어 프린터 보호 정책에 의해 차단된 인쇄가 표시됩니다.

```kusto
DeviceEvents
| where ActionType == 'PrintJobBlocked'
| extend parsed=parse_json(AdditionalFields)
| extend PrintedFile=tostring(parsed.JobOrDocumentName)
| extend PrintPortName=tostring(parsed.PortName)
| extend PrinterName=tostring(parsed.PrinterName)
| extend Policy=tostring(parsed.RestrictionReason) 
| project Timestamp, DeviceId, DeviceName, ActionType, InitiatingProcessAccountName, Policy, PrintedFile, PrinterName, PrintPortName, AdditionalFields
| order by Timestamp desc
```

 :::image type="content" source="../../media/device-control-advanced-hunting.png" alt-text="고급 헌팅.":::

 PnP 이벤트를 사용하여 조직에서 사용되는 USB 프린터를 찾을 수 있습니다.

```kusto
//find the USB Printer VID/PID
DeviceEvents
| where ActionType == "PnpDeviceConnected"
| extend parsed=parse_json(AdditionalFields)
| extend DeviceDescription = tostring(parsed.DeviceDescription) 
| extend PrinterDeviceId = tostring(parsed.DeviceId) 
| extend VID_PID_Array = split(split(PrinterDeviceId, "\\")[1], "&")
| extend VID_PID = replace_string(strcat(VID_PID_Array[0], '/', VID_PID_Array[1]), 'VID_', '')
| extend VID_PID = replace_string(VID_PID, 'PID_', '')
| extend ClassId = tostring(parsed.ClassId) 
| extend VendorIds = tostring(parsed.VendorIds) 
| where DeviceDescription == 'USB Printing Support'
| project Timestamp , DeviceId, DeviceName, ActionType, DeviceDescription, VID_PID, ClassId, PrinterDeviceId, VendorIds, parsed
| order by Timestamp desc
```

 :::image type="content" source="https://user-images.githubusercontent.com/81826151/128954383-71df3009-77ef-40db-b575-79c73fda332b.png" alt-text="고급 헌팅":::








 
 
 
 
