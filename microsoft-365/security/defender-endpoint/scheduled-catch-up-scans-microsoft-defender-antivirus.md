---
title: 정기적인 빠른 검사 및 전체 검사 Microsoft Defender 바이러스 백신
description: 실행해야 하는 시간 및 전체 검사 또는 빠른 검사로 실행 여부를 포함하여 재발(예약된) 검사 설정
keywords: 빠른 검사, 전체 검사, 빠른 대 전체, 검사 예약, 매일, 매주, 시간, 예약, 정기적인
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/05/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 1748a33be2c27123eb0437784dcdb2cb7905616a
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274691"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a>예약된 빠른 또는 전체 Microsoft Defender 바이러스 백신 검사 구성

**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)


> [!NOTE]
> 기본적으로 Microsoft Defender 바이러스 백신 검사 시간이 15분 전에 업데이트를 검사합니다. 이 [기본값을](manage-protection-update-schedule-microsoft-defender-antivirus.md) 다시 설정하기 위해 보호 업데이트를 다운로드하고 적용해야 하는 일정을 관리할 수 있습니다. 

항상 실시간 보호 및 필요한 경우 [](run-scan-microsoft-defender-antivirus.md) 검사뿐만 아니라 정기적인 예약된 검사도 설정할 수 있습니다. 

검사 유형, 검사 발생 날짜 및 보호 업데이트 후 또는 끝점을 사용 중이면 검사가 실행될지 구성할 수 있습니다. [](manage-protection-updates-microsoft-defender-antivirus.md) 수정을 완료하기 위한 특별 검사가 언제 실행될지 지정할 수 있습니다.

이 문서에서는 그룹 정책, PowerShell cmdlet 및 WMI를 사용하여 예약된 검색을 구성하는 방법을 설명합니다. 또는 에서 일정 검색을 구성할 [수도](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) [Microsoft Endpoint Configuration Manager](/mem/intune/configuration/device-restrictions-windows-10)Microsoft Intune.

## <a name="to-configure-the-group-policy-settings-described-in-this-article"></a>이 문서에 설명된 그룹 정책 설정을 구성하려면

1. 그룹 정책 관리 컴퓨터의 그룹 정책 편집기에서 컴퓨터 구성 관리 템플릿 및 구성 요소 Windows   >    >    >  **검사로**  >  **Microsoft Defender 바이러스 백신 합니다.**

2. 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭한 다음 편집 **을 선택합니다.**

3. 그룹 정책 개체에 대한 설정을 지정하고 확인 을 **선택합니다.** 

4. 구성할 각 설정에 대해 1-4단계를 반복합니다.

5. 일반적으로와 같은 그룹 정책 개체를 배포합니다. 그룹 정책 개체에 대한 도움이 필요한 경우 그룹 정책 개체 [만들기를 참조합니다.](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)

또한 [보호](manage-protection-update-schedule-microsoft-defender-antivirus.md) 업데이트를 다운로드하여 적용해야 하는 경우 관리 및 사용자가 정책 설정을 로컬로 수정할 수 있도록 허용 안 하도록 허용 항목을 [참조하세요.](configure-local-policy-overrides-microsoft-defender-antivirus.md)

## <a name="quick-scan-versus-full-scan-and-custom-scan"></a>빠른 검사와 전체 검사 및 사용자 지정 검사

예약된 검색을 설정할 때 검사가 전체 검사인지 아니면 빠른 검사인지를 설정할 수 있습니다.


|빠른 검사  |전체 검사  | 사용자 지정 검사 |
|---------|---------|---------|
|빠른 검사는 레지스트리 키 및 알려진 시작 폴더와 같이 시스템으로 시작하기 위해 등록된 맬웨어가 있을 수 있는 모든 Windows 검색합니다. <p>대부분의 경우 빠른 검사만으로 충분하며 예약된 검사에 권장됩니다. |전체 검사는 빠른 검색을 실행하여 시작한 다음 탑재된 모든 고정 디스크 및 이동식/네트워크 드라이브(전체 검사가 구성된 경우)에 대한 파일 검색을 계속합니다. <p>전체 검사는 검사해야 하는 데이터의 양과 유형에 따라 완료하는 데 몇 시간 또는 며칠이 걸릴 수 있습니다.<p>전체 검사가 완료되면 새로운 보안 인텔리전스를 사용할 수 있으며 새 보안 인텔리전스를 통해 다른 위협이 검색되지는 않습니다.   | 사용자 지정 검사는 지정한 파일 및 폴더에서 실행되는 빠른 검사입니다. 예를 들어 USB 드라이브 또는 장치의 로컬 드라이브에 있는 특정 폴더를 검색하도록 선택할 수 있습니다. <p> | 

>[!NOTE]
>기본적으로 빠른 검사는 USB 드라이브와 같은 탑재된 이동식 장치에서 실행됩니다.

### <a name="how-do-i-know-which-scan-type-to-choose"></a>선택할 검사 유형을 어떻게 알 수 있나요?

다음 표를 사용하여 검사 유형을 선택하십시오.


|시나리오  |권장 검사 유형  |
|---------|---------|
|정기적인 예약된 검색을 설정하려는 경우     | 빠른 검사 <p>빠른 검사는 디바이스의 프로세스, 메모리, 프로필 및 특정 위치를 확인합니다. 빠른 [검사는 항상 실시간](configure-real-time-protection-microsoft-defender-antivirus.md)보호와 결합되어 시스템으로 시작되는 맬웨어와 커널 수준 맬웨어에 대해 강력한 범위를 제공합니다. 실시간 보호는 파일을 열고 닫을 때와 사용자가 폴더로 이동할 때마다 검토합니다.         |
|맬웨어와 같은 위협이 장치에서 감지됩니다.     | 전체 검사 <p>전체 검사는 보다 철저한 정리가 필요한 비활성 구성 요소가 있는지 여부를 식별하는 데 도움이 될 수 있습니다.         |
|필요한 경우 검색을 [실행하려는 경우](run-scan-microsoft-defender-antivirus.md)     | 전체 검사  <p>전체 검사는 부실, 보관 및 매일 액세스되지 않는 파일을 포함하여 장치 디스크의 모든 파일을 확인합니다.      |
| USB 드라이브와 같은 휴대용 장치에 맬웨어가 포함되어 있지 않은지 확인하려는 경우 | 사용자 지정 검사 <p>사용자 지정 검색을 사용하면 특정 위치, 폴더 또는 파일을 선택하고 빠른 검색을 실행합니다. |

### <a name="what-else-do-i-need-to-know-about-quick-and-full-scans"></a>빠른 검사 및 전체 검사에 대해 알아야 할 다른 것은 무엇입니까?

- 악성 파일은 빠른 검사에 포함되지 않은 위치에 저장할 수 있습니다. 그러나 항상 실시간 보호는 열고 닫힌 모든 파일과 사용자가 액세스한 폴더에 있는 모든 파일을 검토합니다. 실시간 보호와 빠른 검사의 조합은 맬웨어에 대한 강력한 보호를 제공하는 데 도움이 됩니다.

- 클라우드 제공 보호를 통해 액세스 보호 기능을 사용하면 시스템에서 액세스하는 모든 파일이 최신 보안 인텔리전스 및 클라우드 기계 학습 모델을 통해 스캔되도록 할 수 있습니다. [](cloud-protection-microsoft-defender-antivirus.md)

- 실시간 보호가 맬웨어를 감지하고 영향을 받는 파일의 범위가 처음에 결정되지 않은 경우 Microsoft Defender 바이러스 백신 프로세스의 일부로 전체 검사가 시작됩니다.

- 전체 검사는 빠른 검사와 같은 다른 검사에서 검색되지 않은 악성 파일을 검색할 수 있습니다. 그러나 전체 검사는 시간이 걸릴 수 있으며 중요한 시스템 리소스를 사용하여 완료할 수 있습니다.

- 장치가 오랜 시간 동안 오프라인 상태인 경우 전체 검사가 완료되는 데 더 오래 걸릴 수 있습니다. 

## <a name="set-up-scheduled-scans"></a>예약된 검사 설정

예약된 검사는 지정한 날짜 및 시간으로 실행됩니다. 그룹 정책, PowerShell 및 WMI를 사용하여 예약된 검색을 구성할 수 있습니다.

> [!NOTE]
> 예약된 전체 검사 중에 디바이스의 연결이 풀리며 배터리에서 실행되는 경우 예약된 검사는 완료 전에 스캔이 중지된 이벤트 1002와 함께 중지됩니다. Microsoft Defender 바이러스 백신 예약된 다음에 전체 검사가 실행됩니다.

### <a name="use-group-policy-to-schedule-scans"></a>그룹 정책을 사용하여 검사 예약

|위치 | 설정 | 설명 | 기본 설정(구성되지 않은 경우) |
|:---|:---|:---|:---|
|검사 | 예약된 검사에 사용할 검사 유형 지정 | 빠른 검사 |
|검사 | 예약된 검색을 실행할 날짜 지정 | 검색을 실행할 날짜를 지정하거나 지정하지 않습니다. | 없음 |
|검사 | 예약된 검색을 실행할 시간 지정 | 자정 이후의 시간(분)을 지정합니다(예: **60** :a.m.). | 2:a.m. |
|루트 | 예약된 작업 시간 임의로 |이 Microsoft Defender 바이러스 백신 검사 시작 시간을 0시간에서 4시간 사이의 간격으로 임의로 임의로 변경합니다. <p>[SCEP에서](/mem/intune/protect/certificates-scep-configure)임의로 스캔을 30분을 더하거나 30분을 더한 간격으로 임의로 변경합니다. 이는 가상 컴퓨터 또는 VDI 배포에서 유용할 수 있습니다. | 사용 |


### <a name="use-powershell-cmdlets-to-schedule-scans"></a>PowerShell cmdlet을 사용하여 검사 예약

다음 cmdlet을 사용 합니다.

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

자세한 내용은 [PowerShell cmdlet을](use-powershell-cmdlets-microsoft-defender-antivirus.md) 사용하여 구성 및 Microsoft Defender 바이러스 백신 및 [Defender cmdlet을](/powershell/module/defender/) 사용하여 PowerShell을 사용하는 방법에 대한 자세한 Microsoft Defender 바이러스 백신.

### <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a>WMI(Windows 관리 명령)를 사용하여 검사 예약

다음 [  속성에 MSFT_MpPreference  ](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) 클래스의 Set 메서드를 사용합니다.

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

자세한 내용은 [WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) API Windows Defender 참조하세요.


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

자세한 내용은 [PowerShell cmdlet을](use-powershell-cmdlets-microsoft-defender-antivirus.md) 사용하여 Microsoft Defender 바이러스 백신 [및 Defender cmdlet을 구성 및 실행을 참조하세요.](/powershell/module/defender/)

### <a name="use-windows-management-instruction-wmi"></a>WMI(Windows 관리 명령) 사용

다음 [  속성에 MSFT_MpPreference  ](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) 클래스의 Set 메서드를 사용합니다.

```WMI
ScanOnlyIfIdleEnabled
```

API 및 허용되는 매개 변수에 대한 자세한 내용은 [WMIv2 api Windows Defender 참조하세요.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

<a id="remed"></a>
## <a name="configure-when-full-scans-should-be-run-to-complete-remediation"></a>재구성 완료를 위해 전체 검사 실행 시 구성

일부 위협은 제거 및 수정을 완료하기 위해 전체 검사가 필요할 수 있습니다. 그룹 정책, PowerShell 또는 WMI에서 이러한 검사가 언제 발생해야 하는지 지정할 수 있습니다.

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

PowerShell과 함께 PowerShell을 사용하는 방법에 대한 자세한 내용은 [PowerShell cmdlet을](use-powershell-cmdlets-microsoft-defender-antivirus.md) 사용하여 Microsoft Defender 바이러스 백신 및 [Defender cmdlet을](/powershell/module/defender/) 구성하고 실행을 Microsoft Defender 바이러스 백신.

### <a name="use-windows-management-instruction-wmi"></a>WMI(Windows 관리 명령) 사용

다음 [  속성에 MSFT_MpPreference  ](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) 클래스의 Set 메서드를 사용합니다.

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

자세한 정보 및 허용되는 매개 변수는 [WMIv2 api Windows Defender 참조하세요.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


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

PowerShell과 함께 PowerShell을 사용하는 방법에 대한 자세한 Microsoft Defender 바이러스 백신 [PowerShell cmdlet을](use-powershell-cmdlets-microsoft-defender-antivirus.md) 사용하여 Microsoft Defender 바이러스 백신 [및 Defender cmdlet](/powershell/module/defender/)구성 및 실행을 참조하세요.

### <a name="use-windows-management-instruction-wmi-to-schedule-daily-scans"></a>WMI(Windows Management Instruction)를 사용하여 일별 검사 예약

다음 [  속성에 MSFT_MpPreference  ](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) 클래스의 Set 메서드를 사용합니다.

```WMI
ScanScheduleQuickScanTime
```

자세한 정보 및 허용되는 매개 변수는 [WMIv2 api Windows Defender 참조하세요.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="enable-scans-after-protection-updates"></a>보호 업데이트 후 검사 사용

그룹 정책을 사용하여 보호를 업데이트할 때마다 검사가 [강제로](manage-protection-updates-microsoft-defender-antivirus.md) 실행될 수 있습니다.

### <a name="use-group-policy-to-schedule-scans-after-protection-updates"></a>그룹 정책을 사용하여 보호 업데이트 후 검사 예약

|위치 | 설정 | 설명 | 기본 설정(구성되지 않은 경우)|
|:---|:---|:---|:---|
|서명 업데이트 | 보안 인텔리전스 업데이트 후 검사 켜기 | 검사는 새 보호 업데이트가 다운로드된 직후에 발생합니다. | 사용 |

## <a name="see-also"></a>참고 항목

- [사용자가 정책 설정을 로컬로 수정하지 못하도록 차단 또는 허용](configure-local-policy-overrides-microsoft-defender-antivirus.md)
- [요청 기반 Microsoft Defender 바이러스 백신 검사 구성 및 실행](run-scan-microsoft-defender-antivirus.md)
- [Microsoft Defender 바이러스 백신 검사 옵션 구성](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [업데이트 Microsoft Defender 바이러스 백신 관리하고 기준 적용](manage-updates-baselines-microsoft-defender-antivirus.md)
- [보호 업데이트를 다운로드하고 적용해야 하는 경우 관리](manage-protection-update-schedule-microsoft-defender-antivirus.md) 
- [Microsoft Defender 바이러스 백신 Windows 10](microsoft-defender-antivirus-in-windows-10.md)