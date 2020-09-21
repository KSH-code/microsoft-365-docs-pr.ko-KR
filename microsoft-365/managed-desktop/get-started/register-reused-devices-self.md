---
title: 직접 기존의 장치 등록
description: 다시 사용 가능한 장치를 등록 하 여 Microsoft Managed Desktop에서 관리할 수 있도록 할 수도 있습니다.
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 6c241894ab50b6b1341b06f47c107c8945fb6e8c
ms.sourcegitcommit: adaedd1418a3bd6e4875b77fd9e008b47e0b2a51
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/18/2020
ms.locfileid: "48104573"
---
# <a name="register-existing-devices-yourself"></a>직접 기존의 장치 등록

>[!NOTE]
>이 항목에서는 이미 갖고 있는 장치를 다시 사용 하 고 Microsoft Managed Desktop에 등록 하는 단계를 설명 합니다. 새 장치에 대 한 작업을 수행 하는 경우 대신 [Microsoft Managed Desktop의 새 장치 등록](register-devices-self.md) 에 설명 된 단계를 따르세요.

파트너에 대 한 프로세스는 [파트너가 장치를 등록 하기 위한 단계](register-devices-partner.md)에 설명 되어 있습니다.

Microsoft Managed Desktop은 새로운 장치에서 작동 하거나 이미 사용 중인 장치를 다시 사용할 수 있습니다 (다시 이미지 해야 함). Microsoft Endpoint Manager 포털에서 Microsoft Managed Desktop을 사용 하 여 장치를 등록할 수 있습니다.

## <a name="prepare-to-register-existing-devices"></a>기존 장치 등록 준비


기존 장치를 등록 하려면 다음 단계를 수행 합니다.

1. [각 장치에 대 한 하드웨어 해시를 가져옵니다.](#obtain-the-hardware-hash)
2. [해시 데이터 병합](#merge-hash-data)
3. [Microsoft Managed Desktop에서 장치를 등록](#register-devices-by-using-the-admin-portal)합니다.
4. [이미지가 올바른지 다시 한 번 확인 합니다.](#check-the-image)
5. [장치 배달](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>하드웨어 해시 가져오기

Microsoft Managed Desktop은 해당 하드웨어 해시를 참조 하 여 각 장치를 고유 하 게 식별 합니다. 이미 사용 중인 장치에서이 정보를 가져올 수 있는 옵션은 다음 네 가지입니다.

- OEM 공급자에 게 하드웨어 해시를 포함 하는 AutoPilot 등록 파일에 대해 문의 하세요.
- [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager)에서 정보를 수집 합니다.
- [Active Directory](#active-directory-powershell-script-method) 를 사용 하거나 각 장치에서 [수동으로](#manual-powershell-script-method) Windows PowerShell 스크립트를 실행 하 고 파일에서 결과를 수집 합니다.
- 각 장치를 시작 하지만 Windows 설치 환경을 완료 하지 않고 [이동식 플래시 드라이브에서 해시를 수집](#flash-drive-method)합니다.

#### <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

Microsoft Endpoint Configuration Manager를 사용 하 여 Microsoft Managed Desktop에 등록 하려는 기존 장치의 하드웨어 해시를 수집할 수 있습니다.

> [!IMPORTANT]
> 이 정보를 가져올 장치에는 Windows 10, 버전 1703 이상을 실행 해야 합니다. 

이러한 필수 구성 요소를 모두 충족 하면 다음 단계를 수행 하 여 정보를 수집할 수 있습니다.

1. Configuration Manager 콘솔에서 **모니터링**을 선택 합니다. 
2. 모니터링 작업 영역에서 **보고** 노드를 확장 하 고 **보고서**를 확장 한 다음 **하드웨어-일반** 노드를 선택 합니다. 
3. 보고서를 실행 하 고 **Windows Autopilot 장치 정보**를 검색 한 다음 결과를 확인 합니다.
4. 보고서 뷰어에서 **내보내기** 아이콘을 선택 하 고 **CSV (쉼표로 분리)** 옵션을 선택 합니다.
5. 파일을 저장 한 후에는 Microsoft Managed Desktop에 등록할 장치에만 결과를 필터링 하 고 Microsoft Managed Desktop에 데이터를 업로드 해야 합니다. Microsoft Endpoint Manager를 열고 **장치** 메뉴로 이동한 다음 Microsoft Managed Desktop 섹션을 찾아 **장치**를 선택 합니다. 새 장치를 등록 하기 위해 날아오기/끄기 **장치** 를 선택 합니다.


자세한 내용은 [Admin Portal을 사용 하 여 장치 등록](#register-devices-by-using-the-admin-portal) 을 참조 하세요.


#### <a name="active-directory-powershell-script-method"></a>Active Directory PowerShell 스크립트 메서드

Active Directory 환경에서는 PowerShell cmdlet을 사용 하 여 `Get-WindowsAutoPilotInfo` WinRM을 사용 하 여 Active Directory 그룹의 장치에서 정보를 원격으로 수집할 수 있습니다. 또한이 cmdlet을 사용 하 여 `Get-AD Computer` 카탈로그에 포함 된 특정 하드웨어 모델 이름에 대 한 필터링 된 결과를 얻을 수 있습니다. 이 작업을 수행 하려면 먼저 다음 필수 구성 요소를 확인 한 다음 단계를 진행 합니다.

- WinRM을 사용 하도록 설정 합니다.
- 등록 하려는 장치가 네트워크에서 활성 상태 (즉, 연결이 끊어지거나 꺼져 있지 않음)입니다.
- 장치에서 원격으로 실행할 수 있는 권한이 있는 도메인 자격 증명 매개 변수가 있는지 확인 합니다.
- Windows 방화벽에서 WMI 액세스를 허용 하는지 확인 합니다. 이 작업을 수행 하려면 다음 단계를 수행 합니다.

    1. **Windows Defender 방화벽** 제어판을 열고 **windows defender 방화벽을 통해 앱 또는 기능 허용**을 선택 합니다.
    
    2. 목록에서 **WMI (Windows Management Instrumentation)** 를 찾고 **개인 및 공용**모두에 대해이 기능을 사용 하도록 설정 하 고 **확인**을 선택 합니다.

1.  관리 권한으로 PowerShell 프롬프트를 엽니다.

2.  다음 스크립트 중 *하나* 를 실행 합니다.

    ```powershell
    Install-script -name Get-WindowsAutoPilotInfo 
    #example one – leverage Get-ADComputer to enumerate devices 
    Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname>
    ```

    ```powershell 
    #example two – target specific devices: 
    Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
    ```

3. 장치에 대 한 항목이 있을 수 있는 모든 디렉터리에 액세스 합니다. Windows Server Active Directory 도메인 서비스 및 Azure Active Directory를 포함 하 여 *모든* 디렉터리에서 각 장치에 대 한 항목을 제거 합니다. 이 제거 작업을 완료 하는 데 몇 시간이 걸릴 수 있습니다.

4. 장치에 대 한 항목이 있을 수 있는 관리 서비스에 액세스 합니다. Microsoft Endpoint Configuration Manager, Microsoft Intune 및 Windows Autopilot를 비롯 한 *모든* 관리 서비스에서 각 장치에 대 한 항목을 제거 합니다. 이 제거 작업을 완료 하는 데 몇 시간이 걸릴 수 있습니다.

이제 [장치 등록](#register-devices-by-using-the-admin-portal)을 계속할 수 있습니다.

#### <a name="manual-powershell-script-method"></a>PowerShell 수동 스크립트 방법

1.  관리 권한으로 PowerShell 프롬프트를 엽니다.
2.  실행 `Install-Script -Name Get-WindowsAutoPilotInfo`
3.  실행 `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
4. [해시 데이터를 병합 합니다.](#merge-hash-data)

#### <a name="flash-drive-method"></a>Flash drive 메서드

1. 등록 중인 장치 이외의 디바이스에서 USB 드라이브를 삽입 합니다.
2. 관리 권한으로 PowerShell 프롬프트를 엽니다.
3. 실행 `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`
4. 등록 중인 디바이스를 켜면 *설치 환경이 시작 되지*않습니다. 실수로 설치 환경을 시작한 경우 장치를 초기화 하거나 다시 이미지로 만들어야 합니다.
5. USB 드라이브를 삽입 한 다음 SHIFT + F10 키를 누릅니다.
6. 관리 권한으로 PowerShell 프롬프트를 열고를 실행 `cd <pathToUsb>` 합니다.
7. 실행 `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`
8. 실행 `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
9. USB 드라이브를 제거한 다음 다음을 실행 하 여 장치를 종료 합니다. `shutdown -s -t 0`
10. [해시 데이터를 병합 합니다.](#merge-hash-data)

>[!IMPORTANT]
>등록을 완료 한 후 다시 등록할 때까지 디바이스에 전원을 공급 하지 마십시오. 



### <a name="merge-hash-data"></a>해시 데이터 병합

수동 PowerShell 또는 플래시 드라이브 방법으로 하드웨어 해시 데이터를 수집한 경우에는 CSV 파일의 데이터를 단일 파일로 결합 하 여 등록을 완료 해야 합니다. 다음과 같은 샘플 PowerShell 스크립트를 통해이를 쉽게 확인할 수 있습니다.

```powershell
Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv
```

해시 데이터를 하나의 CSV 파일에 병합 하 여 이제 [장치 등록](#register-devices-by-using-the-admin-portal)을 진행할 수 있습니다.


#### <a name="register-devices-by-using-the-admin-portal"></a>관리 포털을 사용 하 여 장치 등록

[Microsoft Endpoint Manager](https://endpoint.microsoft.com/)의 왼쪽 탐색 창에서 **장치** 를 선택 합니다. 메뉴의 Microsoft Managed Desktop 섹션을 찾아 **장치**를 선택 합니다. Microsoft Managed Desktop Devices 작업 영역에서 **+ register Devices** 를 선택 하 여 새 장치를 등록 합니다.

<!-- Update with new picture [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


다음 단계를 따릅니다.

1. **파일 업로드**에서 이전에 만든 CSV 파일의 경로를 제공 합니다.

1. **장치 등록**을 선택 합니다. 시스템이 장치 **블레이드에서**장치 목록에 추가 되 고 **AutopilotRegistrationRequested**로 표시 됩니다. 등록은 일반적으로 10 분 미만이 걸리고, 성공적으로 완료 되 면 장치에 **사용자가** 사용할 준비가 된 것으로 표시 되 고 사용자가 사용을 시작할 때까지 대기 하 게 됩니다.


기본 페이지에서 장치 등록의 진행 상태를 모니터링할 수 있습니다. 다음과 같은 가능한 상태가 보고 됩니다.

| 시/도 | 설명 |
|---------------|-------------|
| AutopilotRegistrationRequested | 등록이 아직 완료 되지 않았습니다. 나중에 다시 확인 합니다. |
| 등록 실패 | 등록을 완료할 수 없습니다. 자세한 내용은 [장치 등록 문제 해결](#troubleshooting-device-registration) 을 참조 하세요. |
| 사용자 준비 | 등록을 완료 했으며 이제 장치를 사용자에 게 배달할 준비가 되었습니다. Microsoft Managed Desktop은 처음 설정할 때 가이드를 제공 하므로 추가 준비를 수행할 필요가 없습니다. |
| 활성 | 장치가 사용자에 게 배달 되었으며 테 넌 트에 등록 되어 있습니다. 또한 장치를 정기적으로 사용 하는 것을 나타냅니다. |
| 있었던 | 장치가 사용자에 게 배달 되었으며 테 넌 트에 등록 되어 있습니다. 그러나 최근에 최근 7 일 이내에 장치를 사용 하지 않았습니다.  | 

#### <a name="troubleshooting-device-registration"></a>장치 등록 문제 해결

| 오류 메시지 | 세부 정보 |
|---------------|-------------|
| 장치를 찾을 수 없음 | 제공 된 제조업체, 모델 또는 일련 번호에 대해 일치 하는 항목을 찾을 수 없기 때문에이 장치를 등록할 수 없습니다. 장치 공급자에서 이러한 값을 확인 합니다. |
| 하드웨어 해시가 잘못 되었습니다. | 이 장치에 대해 제공한 하드웨어 해시가 올바르게 포맷 되지 않았습니다. 하드웨어 해시를 두 번 확인 한 다음 다시 제출 합니다. |
| 장치가 이미 등록 됨 | 이 장치는 이미 조직에 등록 되어 있습니다. 추가 작업이 필요 하지 않습니다. |
| 다른 조직에서 요구 하는 장치 | 이 장치는 다른 조직에서 이미 요구 되었습니다. 장치 공급자에 게 문의 하세요. |
| 예기치 않은 오류 | 요청을 자동으로 처리할 수 없습니다. 지원 서비스에 문의 하 여 요청 ID를 제공 합니다. <requestId> |

### <a name="check-the-image"></a>이미지 확인

장치가 Microsoft 관리 되는 데스크톱 파트너 공급자 로부터 온 것 이라면 이미지가 정확 해야 합니다.

원하는 경우 이미지를 직접 적용 하는 것도 환영 합니다. 시작 하려면 사용 중인 Microsoft 담당자에 게 문의 하 여 이미지를 적용할 위치와 단계를 제공 합니다.

### <a name="deliver-the-device"></a>장치 배달

> [!IMPORTANT]
> 사용자에 게 디바이스를 전달 하기 전에 해당 사용자에 대 한 [적절 한 라이선스](../get-ready/prerequisites.md) 를 확보 하 고 적용 했는지 확인 합니다.

모든 라이선스가 적용 되 면 [사용자가 장치를 사용할 준비가](get-started-devices.md)되 면 사용자가 장치를 시작 하 고 Windows 설치 환경을 진행할 수 있습니다.









