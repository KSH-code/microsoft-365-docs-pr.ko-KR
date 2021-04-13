---
title: Microsoft Defender 바이러스 백신을 통해 정기적인 빠른 검사 및 전체 검사 예약
description: 실행해야 하는 시간 및 전체 검사 또는 빠른 검사로 실행 여부를 포함하여 재발(예약된) 검사 설정
keywords: 빠른 검사, 전체 검사, 빠른 대 전체, 검사 예약, 매일, 매주, 시간, 예약, 정기적인
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/02/2020
ms.reviewer: pauhijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 66907fca7a117eeba7ca0b9bd95d59af24c31341
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691301"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a>예약된 빠른 또는 전체 Microsoft Defender 바이러스 백신 검사 구성

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/) 


> [!NOTE]
> 기본적으로 Microsoft Defender 바이러스 백신은 예약된 검사 시간 15분 전에 업데이트를 검사합니다. 이 [기본값을](manage-protection-update-schedule-microsoft-defender-antivirus.md) 다시 설정하기 위해 보호 업데이트를 다운로드하고 적용해야 하는 일정을 관리할 수 있습니다. 

항상 실시간 보호 및 필요한 경우 [](run-scan-microsoft-defender-antivirus.md) 검사뿐만 아니라 정기적인 예약된 검사도 설정할 수 있습니다. 

검사 유형, 검사 발생 날짜 및 보호 업데이트 후 또는 끝점을 사용 중이면 검사가 실행될지 구성할 수 있습니다. [](manage-protection-updates-microsoft-defender-antivirus.md) 수정을 완료하기 위한 특별 검사가 언제 실행될지 지정할 수 있습니다.

이 문서에서는 그룹 정책, PowerShell cmdlet 및 WMI를 사용하여 예약된 검색을 구성하는 방법을 설명합니다. [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) 또는 Microsoft [Intune을](/mem/intune/configuration/device-restrictions-windows-10)사용하여 일정 검색을 구성할 수도 있습니다.

## <a name="to-configure-the-group-policy-settings-described-in-this-article"></a>이 문서에 설명된 그룹 정책 설정을 구성하려면

1.  그룹 정책 관리 컴퓨터의 [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))그룹 정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.**

3.  그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동하십시오.**

4.  관리 **템플릿 을 클릭합니다.**

5.  **Microsoft Defender** 바이러스 백신을 > Windows 구성  요소로 트리를 확장한 다음 아래 표에 지정된 위치를 확장합니다.

6. 아래 표에 지정된 정책 **설정을** 두 번 클릭하고 옵션을 원하는 구성으로 설정하십시오. 

7. 확인 **을** 클릭하고 다른 설정에 대해 반복합니다.

또한 [보호](manage-protection-update-schedule-microsoft-defender-antivirus.md) 업데이트를 다운로드하여 적용해야 하는 경우 관리 및 사용자가 정책 설정을 로컬로 수정할 수 있도록 허용 안 하도록 허용 항목을 [참조하세요.](configure-local-policy-overrides-microsoft-defender-antivirus.md)

## <a name="quick-scan-versus-full-scan-and-custom-scan"></a>빠른 검사와 전체 검사 및 사용자 지정 검사

예약된 검색을 설정할 때 검사가 전체 검사인지 아니면 빠른 검사인지를 설정할 수 있습니다.

빠른 검사는 레지스트리 키 및 알려진 Windows 시작 폴더와 같이 시스템으로 시작하기 위해 등록된 맬웨어가 있을 수 있는 모든 위치를 확인합니다. 

파일을 [](configure-real-time-protection-microsoft-defender-antivirus.md) 열고 닫을 때 그리고 사용자가 폴더로 이동할 때마다 파일을 검토하는 실시간 보호 기능과 결합된 빠른 검사는 시스템으로 시작되는 맬웨어와 커널 수준 맬웨어에 대해 강력한 범위를 제공하는 데 도움이 됩니다.  

대부분의 경우 실시간 보호로 선택되지 않은 맬웨어를 찾기에 빠른 검사가 적절하다는 것을 의미합니다.

전체 검사는 맬웨어 위협이 발생하는 끝점에서 보다 철저한 정리가 필요한 비활성 구성 요소가 있는지 식별하는 데 유용할 수 있습니다. 이 경우 필요한 검사 를 실행하는 경우 전체 [검색을 사용할 수 있습니다.](run-scan-microsoft-defender-antivirus.md)

사용자 지정 스캔을 사용하면 USB 드라이브와 같이 검사할 파일과 폴더를 지정할 수 있습니다. 

>[!NOTE]
>기본적으로 빠른 검사는 USB 드라이브와 같은 탑재된 이동식 장치에서 실행됩니다.

## <a name="set-up-scheduled-scans"></a>예약된 검사 설정

예약된 검사는 지정한 날짜와 시간으로 실행됩니다. 그룹 정책, PowerShell 및 WMI를 사용하여 예약된 검색을 구성할 수 있습니다.

>[!NOTE]
>예약된 전체 검사 중에 컴퓨터의 연결이 풀리며 배터리로 실행되는 경우 예약된 검사는 완료 전에 스캔이 중지된 이벤트 1002와 함께 중지됩니다. Microsoft Defender 바이러스 백신은 다음에 예약된 시간으로 전체 검사가 실행됩니다.

### <a name="use-group-policy-to-schedule-scans"></a>그룹 정책을 사용하여 검사 예약

|위치 | 설정 | 설명 | 기본 설정(구성되지 않은 경우) |
|:---|:---|:---|:---|
|검사 | 예약된 검사에 사용할 검사 유형 지정 | 빠른 검사 |
|검사 | 예약된 검색을 실행할 날짜 지정 | 검색을 실행할 날짜를 지정하거나 지정하지 않습니다. | 없음 |
|검사 | 예약된 검색을 실행할 시간 지정 | 자정 이후의 시간(분)을 지정합니다(예: **60** :a.m.). | 2:a.m. |
|루트 | 예약된 작업 시간 임의로 |Microsoft Defender 바이러스 백신: 검사 시작 시간을 0시간에서 4시간 사이의 간격으로 임의로 변경합니다. <br>FEP/SCEP: 임의 간격에 더하거나 30분을 에서 을(를) 음으로 임의화합니다. 이는 VM 또는 VDI 배포에서 유용할 수 있습니다. | 사용 |


### <a name="use-powershell-cmdlets-to-schedule-scans"></a>PowerShell cmdlet을 사용하여 검사 예약

다음 cmdlet을 사용 합니다.

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

Microsoft Defender 바이러스 백신과 함께 PowerShell을 사용하는 방법에 대한 자세한 내용은 [PowerShell cmdlet을](use-powershell-cmdlets-microsoft-defender-antivirus.md) 사용하여 Microsoft Defender 바이러스 백신 및 [Defender cmdlet](/powershell/module/defender/) 구성 및 실행을 참조하세요.

### <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a>WMI(Windows Management Instruction)를 사용하여 검사 예약

다음 [  속성에 MSFT_MpPreference  ](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) 클래스의 Set 메서드를 사용합니다.

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

자세한 정보 및 허용되는 매개 변수는 다음을 참조하세요.
- [Windows Defender WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)




## <a name="start-scheduled-scans-only-when-the-endpoint-is-not-in-use"></a>끝점이 사용되지 않는 경우만 예약된 검사 시작

끝점이 켜져 있지만 그룹 정책, PowerShell 또는 WMI와 함께 사용되지 않는 경우 예약된 검색이 발생하게 설정할 수 있습니다.

> [!NOTE]
> 이러한 검사는 CPU 스로틀 구성을 적용하지 않을 것이고 가능한 한 빨리 검색을 완료하는 데 사용할 수 있는 리소스를 최대한 활용합니다.

### <a name="use-group-policy-to-schedule-scans"></a>그룹 정책을 사용하여 검사 예약

|위치 | 설정 | 설명 | 기본 설정(구성되지 않은 경우) |
|:---|:---|:---|:---|
|검사 | 컴퓨터가 사용 중이지만 사용 중이 아닌 경우만 예약된 검사 시작 | 컴퓨터가 설정되지만 사용되지 않는 한 예약된 검사는 실행되지 않습니다. | 사용 |

### <a name="use-powershell-cmdlets"></a>PowerShell cmdlet 사용

다음 cmdlet을 사용 합니다.

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

Microsoft Defender 바이러스 백신과 함께 PowerShell을 사용하는 방법에 대한 자세한 내용은 [PowerShell cmdlet을](use-powershell-cmdlets-microsoft-defender-antivirus.md) 사용하여 Microsoft Defender 바이러스 백신 및 [Defender cmdlet](/powershell/module/defender/) 구성 및 실행을 참조하세요.

### <a name="use-windows-management-instruction-wmi"></a>WMI(Windows Management Instruction) 사용

다음 [  속성에 MSFT_MpPreference  ](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) 클래스의 Set 메서드를 사용합니다.

```WMI
ScanOnlyIfIdleEnabled
```

자세한 정보 및 허용되는 매개 변수는 다음을 참조하세요.
- [Windows Defender WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

<a id="remed"></a>
## <a name="configure-when-full-scans-should-be-run-to-complete-remediation"></a>재구성 완료를 위해 전체 검사 실행 시 구성

일부 위협은 제거 및 수정을 완료하기 위해 전체 검사가 필요할 수 있습니다. 그룹 정책, PowerShell 또는 WMI에서 이러한 검사가 실행되는 경우를 예약할 수 있습니다.

### <a name="use-group-policy-to-schedule-remediation-required-scans"></a>그룹 정책을 사용하여 재구성 필요 검사 예약

| 위치 | 설정 | 설명 | 기본 설정(구성되지 않은 경우) |
|---|---|---|---|
|수정 | 재구성 완료를 위해 예약된 전체 검사 실행을 위해 주중 날짜 지정 | 검색을 실행할 날짜를 지정하거나 지정하지 않습니다. | 없음 |
|수정 | 재구성 완료를 위해 예약된 전체 검사 실행 시간을 지정합니다. | 자정 이후의 시간(분)을 지정합니다(예: **60** :a.m.) | 2:a.m. |

### <a name="use-powershell-cmdlets"></a>PowerShell cmdlet 사용

다음 cmdlet을 사용 합니다.

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

Microsoft Defender 바이러스 백신과 함께 PowerShell을 사용하는 방법에 대한 자세한 내용은 [PowerShell cmdlet을](use-powershell-cmdlets-microsoft-defender-antivirus.md) 사용하여 Microsoft Defender 바이러스 백신 및 [Defender cmdlet](/powershell/module/defender/) 구성 및 실행을 참조하세요.

### <a name="use-windows-management-instruction-wmi"></a>WMI(Windows Management Instruction) 사용

다음 [  속성에 MSFT_MpPreference  ](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) 클래스의 Set 메서드를 사용합니다.

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

자세한 정보 및 허용되는 매개 변수는 다음을 참조하세요.
- [Windows Defender WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)




## <a name="set-up-daily-quick-scans"></a>매일 빠른 검사 설정

그룹 정책, PowerShell 또는 WMI를 사용하여 예약된 다른 검사 외에 실행할 수 있는 매일 빠른 검색을 사용하도록 설정할 수 있습니다.


### <a name="use-group-policy-to-schedule-daily-scans"></a>그룹 정책을 사용하여 일별 검사 예약


|위치 | 설정 | 설명 | 기본 설정(구성되지 않은 경우) |
|:---|:---|:---|:---|
|검사 | 매일 빠른 검색을 실행할 간격 지정 | 다음 빠른 검사 전에 경과해야 하는 시간을 지정합니다. 예를 들어 2시간마다 실행을 위해 **2를** 입력하고, 하루 한 번씩 **24를 입력합니다.** **0을 입력하여** 매일 빠른 검색을 실행하지 않습니다. | 없음 |
|검사 | 매일 빠른 검사에 대한 시간 지정 | 자정 이후의 시간(분)을 지정합니다(예: **60** :a.m.) | 2:a.m. |

### <a name="use-powershell-cmdlets-to-schedule-daily-scans"></a>PowerShell cmdlet을 사용하여 일일 검사 예약

다음 cmdlet을 사용 합니다.

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

Microsoft Defender 바이러스 백신과 함께 PowerShell을 사용하는 방법에 대한 자세한 내용은 [PowerShell cmdlet을](use-powershell-cmdlets-microsoft-defender-antivirus.md) 사용하여 Microsoft Defender 바이러스 백신 및 [Defender cmdlet](/powershell/module/defender/) 구성 및 실행을 참조하세요.

### <a name="use-windows-management-instruction-wmi-to-schedule-daily-scans"></a>WMI(Windows Management Instruction)를 사용하여 일일 검사 예약

다음 [  속성에 MSFT_MpPreference  ](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) 클래스의 Set 메서드를 사용합니다.

```WMI
ScanScheduleQuickScanTime
```

자세한 정보 및 허용되는 매개 변수는 다음을 참조하세요.
- [Windows Defender WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="enable-scans-after-protection-updates"></a>보호 업데이트 후 검사 사용

그룹 정책을 사용하여 보호를 업데이트할 때마다 검사가 [강제로](manage-protection-updates-microsoft-defender-antivirus.md) 실행될 수 있습니다.

### <a name="use-group-policy-to-schedule-scans-after-protection-updates"></a>그룹 정책을 사용하여 보호 업데이트 후 검사 예약

|위치 | 설정 | 설명 | 기본 설정(구성되지 않은 경우)|
|:---|:---|:---|:---|
|서명 업데이트 | 보안 인텔리전스 업데이트 후 검사 켜기 | 검사는 새 보호 업데이트가 다운로드된 직후에 발생합니다. | 사용 |

## <a name="see-also"></a>참고 항목
- [사용자가 정책 설정을 로컬로 수정하지 못하도록 차단 또는 허용](configure-local-policy-overrides-microsoft-defender-antivirus.md)
- [Microsoft Defender 바이러스 백신 검사 구성 및 실행](run-scan-microsoft-defender-antivirus.md)
- [Microsoft Defender 바이러스 백신 검사 옵션 구성](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [Microsoft Defender 바이러스 백신 업데이트 관리 및 기준 적용](manage-updates-baselines-microsoft-defender-antivirus.md)
- [보호 업데이트를 다운로드하고 적용해야 하는 경우 관리](manage-protection-update-schedule-microsoft-defender-antivirus.md) 
- [Windows 10의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-in-windows-10.md)