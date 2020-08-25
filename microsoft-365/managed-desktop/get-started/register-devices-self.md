---
title: 직접 새 장치 등록
description: Microsoft Managed Desktop에서 관리할 수 있도록 장치를 직접 등록
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 470047da0a1902a6076add27a6e7ac516edd3150
ms.sourcegitcommit: 22dab0f7604cc057a062698005ff901d40771692
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/25/2020
ms.locfileid: "46869010"
---
# <a name="register-new-devices-yourself"></a>직접 새 장치 등록

Microsoft Managed Desktop은 새로운 장치에서 작동 하거나 이미 사용 중인 장치를 다시 사용할 수 있습니다 (다시 이미지 해야 함). Microsoft Managed Desktop 관리 포털을 사용 하 여 장치를 등록할 수 있습니다.

> [!NOTE]
> 파트너와 협력 하 여 장치 가져오기 그렇다면 하드웨어 해시를 가져오는 것을 걱정 하지 않아도 됩니다. 사용자에 게 필요한 작업입니다. 파트너가 [파트너 센터](https://partner.microsoft.com/dashboard)에서 사용자와 관계를 설정 했는지 확인 합니다. 파트너 [센터 도움말](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer)에서 더 많은 정보를 확인할 수 있습니다. 이 관계가 설정 되 면 파트너는 사용자를 대신 하 여 장치를 등록 합니다 (추가 작업은 필요 하지 않음). 세부 정보를 보거나 파트너에 게 질문이 있는 경우 [에는 파트너가 장치를 등록 하는 단계](register-devices-partner.md)를 참조 하세요. 장치가 등록 되 면 [이미지 확인](#check-the-image) 을 계속 하 고 사용자에 게 [장치를 전달할](#deliver-the-device) 수 있습니다.

## <a name="prepare-to-register-brand-new-devices"></a>새 장치 등록 준비


새 장치를 직접 만들었으면 다음 단계를 수행 합니다.

1. [각 장치에 대 한 하드웨어 해시를 가져옵니다.](#obtain-the-hardware-hash)
2. [해시 데이터 병합](#merge-hash-data)
3. [Microsoft Managed Desktop에서 장치를 등록](#register-devices-by-using-the-admin-portal)합니다.
4. [이미지가 올바른지 다시 한 번 확인 합니다.](#check-the-image)
5. [장치 배달](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>하드웨어 해시 가져오기

Microsoft Managed Desktop은 해당 하드웨어 해시를 참조 하 여 각 장치를 고유 하 게 식별 합니다. 이 정보를 얻기 위한 세 가지 옵션은 다음과 같습니다.

- OEM 공급자에 게 하드웨어 해시를 포함 하는 AutoPilot 등록 파일에 대해 문의 하세요.
- 각 장치에서 [Windows PowerShell 스크립트](#powershell-script-method) 를 실행 하 고 파일에서 결과를 수집 합니다.
- 각 장치를 시작 하지만 Windows 설치 환경을 완료 하지 않고 [이동식 플래시 드라이브에서 해시를 수집](#flash-drive-method)합니다.

#### <a name="powershell-script-method"></a>PowerShell script 메서드

PowerShell 갤러리 웹 사이트에서 [Get-WindowsAutoPilotInfo.ps1](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) powershell 스크립트를 사용할 수 있습니다. 장치 id 및 하드웨어 해시에 대 한 자세한 내용은 [Windows에 장치 추가 Autopilot를](https://docs.microsoft.com/mem/autopilot/add-devices#device-identification)참조 하세요.

1.  관리 권한으로 PowerShell 프롬프트를 엽니다.
2.  실행 `Install-Script -Name Get-WindowsAutoPilotInfo`
3.  실행 `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`

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

>[!IMPORTANT]
>등록을 완료 한 후 다시 등록할 때까지 디바이스에 전원을 공급 하지 마십시오. 


### <a name="merge-hash-data"></a>해시 데이터 병합

등록을 완료 하려면 CSV 파일의 데이터를 단일 파일로 결합 해야 합니다. 다음과 같은 샘플 PowerShell 스크립트를 통해이를 쉽게 확인할 수 있습니다.

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`


#### <a name="register-devices-by-using-the-admin-portal"></a>관리 포털을 사용 하 여 장치 등록

Microsoft Managed Desktop [관리 포털](https://aka.ms/mmdportal)의 왼쪽 탐색 창에서 **장치** 를 선택 합니다. **+ 장치 등록**을 선택 합니다. 날아오기는 다음과 같이 열립니다.

[![등록 장치를 선택한 후 날아오기, 할당 된 사용자, 일련 번호, 상태, 마지막으로 표시 된 날짜 및 연령에 해당 하는 열이 있는 장치 나열](../../media/new-registration-ui.png)](../../media/new-registration-ui.png)


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


다음 단계를 따릅니다.

1. **파일 업로드**에서 이전에 만든 CSV 파일의 경로를 제공 합니다.
3. **장치 등록**을 선택 합니다. 시스템이 장치 **블레이드에서**장치 목록에 추가 되 고 **AutopilotRegistrationRequested**로 표시 됩니다. 등록은 일반적으로 10 분 미만이 걸리고, 성공적으로 완료 되 면 장치에 **사용자가** 사용할 준비가 된 것으로 표시 되 고 사용자가 사용을 시작할 때까지 대기 하 게 됩니다.


기본 **Microsoft Managed Desktop-Devices** 페이지에서 장치 등록의 진행 상태를 모니터링할 수 있습니다. 다음과 같은 가능한 상태가 보고 됩니다.

| 시/도 | 설명 |
|---------------|-------------|
| AutopilotRegistrationRequested | 등록이 아직 완료 되지 않았습니다. 나중에 다시 확인 합니다. |
| 등록 실패 | 등록을 완료할 수 없습니다. 자세한 내용은 [장치 등록 문제 해결](#troubleshooting-device-registration) 을 참조 하세요. |
| 사용자 준비 | 등록을 완료 했으며 이제 장치를 최종 사용자에 게 배달할 준비가 되었습니다. Microsoft Managed Desktop은 처음 설정할 때 가이드를 제공 하므로 추가 준비를 수행할 필요가 없습니다. |
| 활성 | 장치가 최종 사용자에 게 배달 되었으며 테 넌 트에 등록 되어 있습니다. 또한 장치를 정기적으로 사용 하는 것을 나타냅니다. |
| 있었던 | 장치가 최종 사용자에 게 배달 되었으며 테 넌 트에 등록 되어 있습니다. 그러나 최근에 최근 7 일 이내에 장치를 사용 하지 않았습니다.  | 

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






