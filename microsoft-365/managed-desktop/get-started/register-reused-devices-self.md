---
title: 직접 기존의 장치 등록
description: Microsoft Managed Desktop에서 관리할 수 있도록 이미 사용 중일 수 있는 다시 사용 디바이스 등록
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: c2ba687b38f1de4d2ed09b0bd690e02b43f15f8d
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840518"
---
# <a name="register-existing-devices-yourself"></a>직접 기존의 장치 등록

>[!NOTE]
>이 항목에서는 이미 있는 장치를 다시 사용하여 Microsoft Managed Desktop에 등록하는 단계를 설명합니다. 새 디바이스로 작업하는 경우 대신 Microsoft [Managed Desktop에서 새](register-devices-self.md) 디바이스를 등록하는 단계를 따릅니다.

파트너를 위한 프로세스는 디바이스를 등록하는 [파트너를 위한 단계에 설명되어 있습니다.](register-devices-partner.md)

Microsoft Managed Desktop은 새로운 디바이스에서 작동하거나 이미 있을 수 있는 장치를 다시 사용할 수 있습니다(이 경우 다시 이미 이미 있는 디바이스를 다시 사용해야 합니다). Microsoft Endpoint Manager 포털에서 Microsoft Managed Desktop에 장치를 등록할 수 있습니다.

## <a name="prepare-to-register-existing-devices"></a>기존 장치 등록 준비


기존 장치를 등록하기 위해 다음 단계를 수행합니다.

1. [각 디바이스에 대한 하드웨어 해시를 얻습니다.](#obtain-the-hardware-hash)
2. [해시 데이터 병합](#merge-hash-data)
3. [Microsoft Managed Desktop에서 디바이스를 등록합니다.](#register-devices-by-using-the-admin-portal)
4. [이미지가 올바른지 다시 확인합니다.](#check-the-image)
5. [디바이스 전달](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>하드웨어 해시 획득

Microsoft Managed Desktop은 하드웨어 해시를 참조하여 각 장치를 고유하게 식별합니다. 이미 사용 중인 디바이스에서 이 정보를 4개의 옵션으로 사용할 수 있습니다.

- OEM 공급업체에 하드웨어 해시를 포함할 AutoPilot 등록 파일을 요청합니다.
- [Microsoft Endpoint Configuration Manager에서 정보를 수집합니다.](#microsoft-endpoint-configuration-manager)
- Active Directory를 Windows PowerShell 또는 각 장치에서 [](#active-directory-powershell-script-method) 수동으로 [](#manual-powershell-script-method) 스크립트를 실행하고 결과를 파일에 수집합니다.
- 각 디바이스를 시작하지만 Windows 설치 환경을 완료하지는 않습니다. 이동식 플래시 드라이브에서 [해시를 수집합니다.](#flash-drive-method)

#### <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

Microsoft Endpoint Configuration Manager를 사용하여 Microsoft Managed Desktop에 등록하려는 기존 장치에서 하드웨어 해시를 수집할 수 있습니다.

> [!IMPORTANT]
> 이 정보를 얻게 될 디바이스는 Windows 10 버전 1703 이상을 실행해야 합니다. 

이러한 모든 선행 단계를 충족하면 다음 단계에 따라 정보를 수집할 수 있습니다.

1. Configuration Manager 콘솔에서 **모니터링을 선택합니다.** 
2. 모니터링 작업 영역에서 **보고** 노드를 확장하고 보고서를 확장한 다음 **하드웨어 - 일반 노드를** 선택합니다. 
3. 보고서를 실행하고 **Windows Autopilot 장치 정보를 실행하고** 결과를 확인합니다.
4. 보고서 뷰어에서 내보내기  아이콘을 선택하고 **CSV( comma-delimited) 옵션을** 선택합니다.
5. 파일을 저장한 후 Microsoft Managed Desktop에 등록할 장치로만 결과를 필터링하고 데이터를 Microsoft Managed Desktop에 업로드해야 합니다. Microsoft Endpoint Manager를 열고 장치 메뉴로 이동한 다음 Microsoft Managed Desktop 섹션을 찾아 장치를 **선택합니다.**  새 **디바이스를 등록하기** 위해 플라이인을 여는 + 장치 등록을 선택합니다.


자세한 내용은 관리 포털을 [사용하여 디바이스](#register-devices-by-using-the-admin-portal) 등록을 참조하세요.


#### <a name="active-directory-powershell-script-method"></a>Active Directory PowerShell 스크립트 메서드

Active Directory `Get-WindowsAutoPilotInfo` 환경에서는 PowerShell cmdlet을 사용하여 WinRM을 사용하여 Active Directory 그룹의 장치에서 정보를 원격으로 수집할 수 있습니다. 이 cmdlet을 사용하여 카탈로그에 포함된 특정 하드웨어 모델 이름에 대한 `Get-AD Computer` 필터링된 결과를 얻을 수도 있습니다. 계속하기 전에 먼저 이러한 선행 단계를 확인한 후 다음 단계를 진행합니다.

- WinRM이 사용하도록 설정됩니다.
- 등록하려는 장치가 네트워크에서 활성화되어 있습니다(즉, 연결이 끊어지거나 꺼지지 않은 경우).
- 디바이스에서 원격으로 실행할 수 있는 권한이 있는 도메인 자격 증명 매개 변수가 있는지 확인
- Windows 방화벽에서 WMI에 대한 액세스를 허용하는지 확인 이렇게 하여 다음 단계를 수행합니다.

    1. Windows Defender **방화벽** 제어판을 열고 방화벽을 통해 앱 또는 **기능 허용을 Windows Defender 선택합니다.**
    
    2. 목록에서 **WMI(Windows Management Instrumentation)를** 찾고 개인 및 공용 모두에 대해 사용하도록 설정한 다음 확인을 **선택합니다.**

1.  관리 권한으로 PowerShell 프롬프트를 열 수 있습니다.

2.  다음 *스크립트 중* 하나를 실행합니다.

    ```powershell
    Install-script -name Get-WindowsAutoPilotInfo 
    #example one – leverage Get-ADComputer to enumerate devices 
    Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname>
    ```

    ```powershell 
    #example two – target specific devices: 
    Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
    ```

3. 장치에 대한 항목이 있을 수 있는 모든 Director에 액세스합니다. Windows Server Active  Directory 도메인 서비스 및 Azure Active Directory를 비롯한 모든 디렉터리에서 각 장치에 대한 항목을 제거합니다. 제거를 완전히 처리하는 데 몇 시간이 걸릴 수 있습니다.

4. 디바이스에 대한 항목이 있을 수 있는 액세스 관리 서비스 Microsoft Endpoint Configuration  Manager, Microsoft Intune 및 Windows Autopilot을 비롯한 모든 관리 서비스에서 각 장치에 대한 항목을 제거합니다. 제거를 완전히 처리하는 데 몇 시간이 걸릴 수 있습니다.

이제 디바이스 등록을 [계속할 수 있습니다.](#register-devices-by-using-the-admin-portal)

#### <a name="manual-powershell-script-method"></a>수동 PowerShell 스크립트 방법

1.  관리 권한으로 PowerShell 프롬프트를 열 수 있습니다.
2.  실행 `Install-Script -Name Get-WindowsAutoPilotInfo`
3.  실행 `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
4. [해시 데이터를 병합합니다.](#merge-hash-data)

#### <a name="flash-drive-method"></a>플래시 드라이브 방법

1. 등록할 장치 외의 디바이스에 USB 드라이브를 삽입합니다.
2. 관리 권한으로 PowerShell 프롬프트를 열 수 있습니다.
3. 실행 `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`
4. 등록할 디바이스를 켜지만 설치 *환경을 시작하지는 않습니다.* 실수로 설치 환경을 시작한 경우 장치를 초기화하거나 다시 이미지해야 합니다.
5. USB 드라이브를 삽입한 다음 Shift + F10을 누를 수 있습니다.
6. 관리 권한으로 PowerShell 프롬프트를 연 다음 `cd <pathToUsb>` 실행합니다.
7. 실행 `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`
8. 실행 `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
9. USB 드라이브를 제거한 다음 실행하여 디바이스를 종료합니다. `shutdown -s -t 0`
10. [해시 데이터를 병합합니다.](#merge-hash-data)

>[!IMPORTANT]
>등록을 완료할 때까지 다시 등록하는 디바이스에서 전원을 공급하지 않습니다. 



### <a name="merge-hash-data"></a>해시 데이터 병합

수동 PowerShell 또는 플래시 드라이브 방법을 통해 하드웨어 해시 데이터를 수집한 경우 이제 등록을 완료하기 위해 CSV 파일의 데이터를 단일 파일로 결합해야 합니다. 다음은 쉽게 사용할 수 있도록 하는 샘플 PowerShell 스크립트입니다.

```powershell
Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv
```

해시 데이터가 하나의 CSV 파일에 병합되어 이제 디바이스를 등록할 [수 있습니다.](#register-devices-by-using-the-admin-portal)


#### <a name="register-devices-by-using-the-admin-portal"></a>관리 포털을 사용하여 장치 등록

[Microsoft Endpoint Manager의](https://endpoint.microsoft.com/)왼쪽 탐색 창에서 디바이스를 선택합니다.  메뉴의 Microsoft Managed Desktop 섹션을 찾아 장치를 **선택합니다.** Microsoft Managed Desktop Devices 작업 영역에서 **새 장치를** 등록하기 위해 플라이인을 여는 + 장치 등록을 선택합니다.

<!-- Update with new picture [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


아래 단계를 수행하세요.

1. 파일 **업로드에서** 이전에 만든 CSV 파일의 경로를 제공합니다.

1. 장치 **등록을 선택합니다.** 시스템은 등록 보류 중으로 표시된 **장치** 블레이드의 장치 목록에 **장치를 추가합니다.** 등록에는 일반적으로 10분 미만이 걸리며, 성공하면 장치가 준비된 것으로 표시되어 사용자가 사용을 시작할 때까지 기다립니다. 


주 페이지에서 장치 등록의 진행률을 모니터링할 수 있습니다. 보고된 가능한 상태는 다음과 같습니다.

| 시/도 | 설명 |
|---------------|-------------|
| 등록 보류 중 | 등록이 아직 완료되지 않았습니다. 나중에 다시 확인 |
| 등록 실패 | 등록을 완료할 수 없습니다. 자세한 내용은 [장치](#troubleshooting-device-registration) 등록 문제 해결을 참조하세요. |
| 사용자 준비 | 등록이 성공하고 이제 디바이스를 사용자에게 전달할 준비가 완료되었습니다. Microsoft Managed Desktop은 최초 설치를 안내하기 때문에 추가 준비를 할 필요가 없습니다. |
| 활성 | 장치가 사용자에게 전달되고 테넌트에 등록되어 있습니다. 또한 장치가 정기적으로 사용 중이기도 합니다. |
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









