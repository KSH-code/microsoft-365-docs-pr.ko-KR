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
# <a name="register-new-devices-yourself"></a>직접 새 장치 등록

Microsoft Managed Desktop은 새로운 디바이스에서 작동하거나 이미 있을 수 있는 장치를 다시 사용할 수 있습니다(이 경우 다시 이미 이미 있는 디바이스를 다시 사용해야 합니다). Microsoft Endpoint Manager 포털에서 Microsoft Managed Desktop에 장치를 등록할 수 있습니다.

> [!NOTE]
> 파트너와 협력하여 디바이스를 얻습니까? 그렇다면 하드웨어 해시를 사용할 때 걱정할 필요가 없습니다. 이러한 경우를 관리합니다. 파트너가 파트너 센터에서 사용자와 관계를 [설정하는지 확인](https://partner.microsoft.com/dashboard) 파트너는 파트너 센터 도움말에서 자세한 [정보를 볼 수 있습니다.](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer) 이 관계가 설정되면 파트너는 단순히 사용자 대신 디바이스를 등록합니다. 추가 작업이 필요하지 않습니다. 세부 정보를 보거나 파트너에게 질문이 있는 경우 파트너가 디바이스를 등록하는 [단계를 참조하세요.](register-devices-partner.md) 디바이스가 등록된 후 이미지를 확인하고 [](#check-the-image) 사용자에게 디바이스를 [](#deliver-the-device) 전달할 수 있습니다.

## <a name="prepare-to-register-brand-new-devices"></a>새 장치 등록 준비


새 장치를 사용할 수 있는 경우 다음 단계를 수행합니다.

1. [각 디바이스에 대한 하드웨어 해시를 얻습니다.](#obtain-the-hardware-hash)
2. [해시 데이터 병합](#merge-hash-data)
3. [Microsoft Managed Desktop에서 디바이스를 등록합니다.](#register-devices-by-using-the-admin-portal)
4. [이미지가 올바른지 다시 확인합니다.](#check-the-image)
5. [디바이스 전달](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>하드웨어 해시 획득

Microsoft Managed Desktop은 하드웨어 해시를 참조하여 각 장치를 고유하게 식별합니다. 이 정보를 수집하는 세 가지 옵션이 있습니다.

- OEM 공급업체에 하드웨어 해시를 포함할 AutoPilot 등록 파일을 요청합니다.
- 각 [Windows PowerShell 스크립트를](#powershell-script-method) 실행하고 파일에 결과를 수집합니다.
- 각 디바이스를 시작하지만 Windows 설치 환경을 완료하지는 않습니다. 이동식 플래시 드라이브에서 [해시를 수집합니다.](#flash-drive-method)

#### <a name="powershell-script-method"></a>PowerShell 스크립트 메서드

PowerShell 갤러리 [Get-WindowsAutoPilotInfo.ps1](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) PowerShell 스크립트를 사용할 수 있습니다. 장치 식별 및 하드웨어 해시에 대한 자세한 내용은 [Windows Autopilot에 장치 추가를 참조하세요.](https://docs.microsoft.com/mem/autopilot/add-devices#device-identification)

1.  관리 권한으로 PowerShell 프롬프트를 열 수 있습니다.
2.  실행 `Install-Script -Name Get-WindowsAutoPilotInfo`
3.  실행 `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
4.  후속 무제한 스크립트가 실행되지 않도록 `powershell -ExecutionPolicy restricted` 실행합니다.


#### <a name="flash-drive-method"></a>플래시 드라이브 방법

1. 등록할 장치 외의 디바이스에 USB 드라이브를 삽입합니다.
2. 관리 권한으로 PowerShell 프롬프트를 열 수 있습니다.
3. 실행 `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`
4. 등록할 디바이스를 켜지만 설치 *환경을 시작하지는 않습니다.* 실수로 설치 환경을 시작한 경우 장치를 초기화하거나 다시 이미지해야 합니다.
5. USB 드라이브를 삽입한 다음 Shift + F10을 누를 수 있습니다.
6. 관리 권한으로 PowerShell 프롬프트를 열고 `cd <pathToUsb>` 실행합니다.
7. 실행 `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`
8. 실행 `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
9. USB 드라이브를 제거한 다음 실행하여 디바이스를 종료합니다. `shutdown -s -t 0`

>[!IMPORTANT]
>등록을 완료할 때까지 다시 등록하는 디바이스에서 전원을 공급하지 않습니다. 


### <a name="merge-hash-data"></a>해시 데이터 병합

등록을 완료하려면 CSV 파일의 데이터를 단일 파일로 결합해야 합니다. 다음은 쉽게 사용할 수 있도록 하는 샘플 PowerShell 스크립트입니다.

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`


#### <a name="register-devices-by-using-the-admin-portal"></a>관리 포털을 사용하여 장치 등록

[Microsoft 끝점 관리자의](https://endpoint.microsoft.com/)왼쪽 탐색 창에서 장치를 선택합니다.  메뉴의 Microsoft Managed Desktop 섹션을 찾아 장치를 **선택합니다.** Microsoft Managed Desktop Devices 작업 영역에서 **새 장치를** 등록하기 위해 플라이인을 여는 + 장치 등록을 선택합니다.

<!-- [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


아래 단계를 수행하세요.

1. 파일 **업로드에서** 이전에 만든 CSV 파일의 경로를 제공합니다.
3. 장치 **등록을 선택합니다.** 시스템은 등록 보류 중으로 표시된 디바이스의 장치 목록에 **장치를 추가합니다.** 등록에는 일반적으로 10분 미만이 걸리며, 성공하면 장치가 준비된 것으로 표시되어 사용자가 사용을 시작할 때까지 기다립니다. 


주 페이지에서 장치 등록의 진행률을 모니터링할 수 있습니다. 보고된 가능한 상태는 다음과 같습니다.

| 시/도 | 설명 |
|---------------|-------------|
| 등록 보류 중 | 등록이 아직 완료되지 않았습니다. 나중에 다시 확인 |
| 등록 실패 | 등록을 완료할 수 없습니다. 자세한 내용은 [장치](#troubleshooting-device-registration) 등록 문제 해결을 참조하세요. |
| 사용자 준비 | 등록이 성공하고 이제 디바이스를 사용자에게 전달할 준비가 완료되었습니다. Microsoft Managed Desktop은 최초 설치를 안내하기 때문에 추가 준비를 할 필요가 없습니다. |
| 활성 | 장치가 사용자에게 전달되고 테넌트에 등록되어 있습니다. 또한 이 상태는 장치가 정기적으로 사용 중이기도 합니다. |
| 비활성 | 장치가 사용자에게 전달되고 테넌트에 등록되어 있습니다. 그러나 최근(지난 7일)에는 장치를 사용한 것이 없습니다.  | 

#### <a name="troubleshooting-device-registration"></a>장치 등록 문제 해결

| 오류 메시지 | 세부 정보 |
|---------------|-------------|
| 디바이스를 찾을 수 없습니다. | 제공된 제조업체, 모델 또는 일련 번호에 대한 일치를 찾을 수 없는 경우 이 장치를 등록할 수 없습니다. 장치 공급업체에 이러한 값을 확인합니다. |
| 하드웨어 해시가 유효하지 않습니다. | 이 장치에 대해 제공한 하드웨어 해시의 형식이 올바로 지정되지 않았습니다. 하드웨어 해시를 다시 확인한 다음 다시 제출합니다. |
| 디바이스가 이미 등록되어 있습니다. | 이 장치는 이미 조직에 등록되어 있습니다. 추가 작업이 필요하지 않습니다. |
| 다른 조직에서 클레임된 장치 | 이 디바이스는 다른 조직에서 이미 클레임했습니다. 장치 공급업체에 문의하십시오. |
| 예기치 않은 오류 | 요청을 자동으로 처리하지 못했습니다. 고객 지원에 문의하여 요청 ID를 제공합니다. <requestId> |

### <a name="check-the-image"></a>이미지 확인

디바이스가 Microsoft Managed Desktop 파트너 공급업체에서 제공된 경우 이미지가 정확해야 합니다.

원하는 경우 직접 이미지를 적용할 수도 있습니다. 시작을 위해 함께 작업하는 Microsoft 담당자에게 연락하여 이미지 적용 위치와 단계를 제공합니다.

### <a name="deliver-the-device"></a>디바이스 전달

> [!IMPORTANT]
> 디바이스를 사용자에게 제공하려면 먼저 해당 사용자에게 적절한 라이선스를 획득하고 [적용해야](../get-ready/prerequisites.md) 합니다.

모든 라이선스가 적용된 경우 [](get-started-devices.md)사용자가 디바이스를 사용할 수 있도록 준비한 다음 사용자가 디바이스를 시작하고 Windows 설치 환경을 진행할 수 있습니다.





