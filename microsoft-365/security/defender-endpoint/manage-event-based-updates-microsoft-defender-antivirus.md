---
title: 특정 Microsoft Defender 바이러스 백신 후 업데이트 적용
description: 시작 또는 Microsoft Defender 바이러스 백신 검색 보고서를 받은 후 보안 인텔리전스 업데이트를 적용하는 방법을 관리합니다.
keywords: 업데이트, 보호, 강제 업데이트, 이벤트, 시작, 최신 확인, 알림
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/17/2018
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: 3edca602d9e49d8ddc67da0e740c862364b0d6b4
ms.sourcegitcommit: 6968594dc8cf8b30a4c958df6d65dfd0cd2cfae1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2021
ms.locfileid: "59491352"
---
# <a name="manage-event-based-forced-updates"></a>이벤트 기반 강제 업데이트 관리

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

Microsoft Defender 바이러스 백신 시작 시 또는 클라우드 제공 보호 서비스에서 특정 보고서를 받은 후와 같은 특정 이벤트가 발생하거나 업데이트가 발생하면 안 되는지 여부를 결정할 수 있습니다.

## <a name="check-for-protection-updates-before-running-a-scan"></a>검사를 실행하기 전에 보호 업데이트 확인

그룹 정책, Microsoft Endpoint Configuration Manager, PowerShell cmdlet 및 WMI를 사용하여 예약된 검사를 실행하기 전에 Microsoft Defender 바이러스 백신 업데이트를 강제로 확인하고 다운로드할 수 있습니다.

### <a name="use-configuration-manager-to-check-for-protection-updates-before-running-a-scan"></a>Configuration Manager를 사용하여 검사를 실행하기 전에 보호 업데이트 확인

1. Microsoft Endpoint Manager 콘솔에서 변경할 맬웨어 방지 정책을 열고(왼쪽의 탐색 창에서 자산 및 규정 준수를  클릭한 다음 개요 Endpoint Protection 맬웨어 방지 정책)  \>  \> 

2. 예약된 검사 **섹션으로 이동하여** 검사를 실행하기 전에 최신 보안 인텔리전스 업데이트 확인을  **예로 설정하세요.**

3. **확인** 을 클릭합니다.

4. [평소와 같이 업데이트된 정책을 배포합니다.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)

### <a name="use-group-policy-to-check-for-protection-updates-before-running-a-scan"></a>그룹 정책을 사용하여 검사를 실행하기 전에 보호 업데이트 확인

1. 그룹 정책 관리 컴퓨터의 [](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)그룹 정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.**

2. 그룹 정책 **관리 편집기를 사용하여 컴퓨터** **구성으로 이동하십시오.**

3. 정책을 **클릭한** 다음 **관리 템플릿을 클릭합니다.**

4. 검색에서 구성 **Windows** \> **트리를 Microsoft Defender 바이러스 백신** \> **확장합니다.**

5. 예약된  검사를 실행하기 전에 최신 바이러스 및 스파이웨어 정의 확인을 두 번 클릭하고 옵션을 사용으로 **설정합니다.**

6. **확인** 을 클릭합니다.

### <a name="use-powershell-cmdlets-to-check-for-protection-updates-before-running-a-scan"></a>검사를 실행하기 전에 PowerShell cmdlet을 사용하여 보호 업데이트 확인

다음 cmdlet을 사용 합니다.

```PowerShell
Set-MpPreference -CheckForSignaturesBeforeRunningScan
```

자세한 내용은 [PowerShell cmdlet을 사용하여 Microsoft Defender 바이러스 백신 구성 및 실행](use-powershell-cmdlets-microsoft-defender-antivirus.md)과 [Defender cmdlet](/powershell/module/defender/index)을 참조하세요.

### <a name="use-windows-management-instruction-wmi-to-check-for-protection-updates-before-running-a-scan"></a>WMI(Windows 관리 명령)를 사용하여 검사를 실행하기 전에 보호 업데이트를 확인합니다.

다음 [  속성에 MSFT_MpPreference  ](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) 클래스의 Set 메서드를 사용합니다.

```WMI
CheckForSignaturesBeforeRunningScan
```

자세한 내용은 [WMIv2 api Windows Defender 참조하세요.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="check-for-protection-updates-on-startup"></a>시작 시 보호 업데이트 확인

그룹 정책을 사용하여 컴퓨터 시작 시 Microsoft Defender 바이러스 백신 보호 업데이트를 강제로 확인하고 다운로드할 수 있습니다.

1. 그룹 정책 관리 컴퓨터에서 그룹 [](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.**

2. 그룹 정책 **관리 편집기를 사용하여 컴퓨터** **구성으로 이동하십시오.**

3. 정책을 **클릭한** 다음 **관리 템플릿을 클릭합니다.**

4. 보안 인텔리전스 **Windows 구성 Microsoft Defender 바이러스 백신** \>  \> **확장합니다.**

5. 시작 시  최신 바이러스 및 스파이웨어 정의 확인을 두 번 클릭하고 옵션을 사용으로 **설정합니다.**

6. **확인** 을 클릭합니다.

그룹 정책, PowerShell 또는 WMI를 사용하여 시작 시 업데이트를 Microsoft Defender 바이러스 백신 확인하도록 구성할 수도 있습니다.

### <a name="use-group-policy-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a>그룹 정책을 사용하여 업데이트가 없는 Microsoft Defender 바이러스 백신 다운로드

1. 그룹 정책 관리 컴퓨터의 [](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)그룹 정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.**

2. 그룹 정책 **관리 편집기를 사용하여** 컴퓨터 **구성으로 이동하십시오.**

3. 정책을 **클릭한** 다음 **관리 템플릿을 클릭합니다.**

4. 보안 인텔리전스 **Windows 구성 Microsoft Defender 바이러스 백신** \>  \> **확장합니다.**

5. 시작 시 보안 **인텔리전스** 업데이트 시작을 두 번 클릭하고 옵션을 사용으로 **설정합니다.**

6. **확인** 을 클릭합니다.

### <a name="use-powershell-cmdlets-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a>PowerShell cmdlet을 사용하여 업데이트가 없는 Microsoft Defender 바이러스 백신 다운로드

다음 cmdlet을 사용 합니다.

```PowerShell
Set-MpPreference -SignatureDisableUpdateOnStartupWithoutEngine
```

자세한 내용은 [PowerShell cmdlet을](use-powershell-cmdlets-microsoft-defender-antivirus.md) 사용하여 Microsoft Defender 바이러스 백신 및 [Defender cmdlet을](/powershell/module/defender/index) 사용하여 PowerShell을 사용하는 방법에 대한 자세한 Microsoft Defender 바이러스 백신.

### <a name="use-windows-management-instruction-wmi-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a>WMI(Windows Management Instruction)를 사용하여 업데이트가 없는 Microsoft Defender 바이러스 백신 다운로드

다음 [  속성에 MSFT_MpPreference  ](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) 클래스의 Set 메서드를 사용합니다.

```WMI
SignatureDisableUpdateOnStartupWithoutEngine
```

자세한 내용은 [WMIv2 api Windows Defender 참조하세요.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

<a id="cloud-report-updates"></a>

## <a name="allow-ad-hoc-changes-to-protection-based-on-cloud-delivered-protection"></a>클라우드 제공 보호를 기반으로 보호에 대한 추가 변경 허용

Microsoft Defender AV는 클라우드 제공 보호를 기반으로 보호를 변경할 수 있습니다. 이러한 변경 내용은 일반 또는 예약된 보호 업데이트 외부에서 발생할 수 있습니다.

클라우드 제공 보호를 사용하도록 설정한 경우 Microsoft Defender AV는 의심스러운 파일을 클라우드로 Windows Defender 전송합니다. 클라우드 서비스에서 파일이 악성으로 보고되고 최근 보호 업데이트에서 파일이 검색된 경우 그룹 정책을 사용하여 해당 보호 업데이트를 자동으로 받도록 Microsoft Defender AV를 구성할 수 있습니다. 기타 중요한 보호 업데이트도 적용할 수 있습니다.

### <a name="use-group-policy-to-automatically-download-recent-updates-based-on-cloud-delivered-protection"></a>그룹 정책을 사용하여 클라우드 제공 보호에 따라 최근 업데이트 자동 다운로드

1. 그룹 정책 관리 컴퓨터의 [](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)그룹 정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.**

2. 그룹 정책 **관리 편집기를 사용하여 컴퓨터** **구성으로 이동하십시오.**

3. 정책을 **클릭한** 다음 **관리 템플릿을 클릭합니다.**

4. 보안 인텔리전스 **Windows 구성 Microsoft Defender 바이러스 백신** \>  \> **확장합니다.**

5. **Microsoft MAPS에** 대한 보고서를 기반으로 하는 실시간 보안 인텔리전스 업데이트 허용을 두 번 클릭하고 옵션을 사용으로 **설정합니다.** 그런 다음 **확인** 을 클릭합니다.

6. **알림에서 정의** 기반 보고서를 Microsoft MAPS에 사용하지 않도록 설정하고 옵션을 사용으로 **설정합니다.** 그런 다음 **확인** 을 클릭합니다.

> [!NOTE]
> **알림이 정의** 기반 보고서를 사용하지 않도록 설정하도록 허용하면 Microsoft MAPS에서 가짓 긍정 보고서를 유발하는 것으로 알려진 정의를 사용하지 않도록 설정할 수 있습니다. 이 기능이 작동하려면 Microsoft MAPS에 가입하도록 컴퓨터를 구성해야 합니다.

## <a name="see-also"></a>참고 항목

- [배포 Microsoft Defender 바이러스 백신](deploy-manage-report-microsoft-defender-antivirus.md)
- [업데이트 Microsoft Defender 바이러스 백신 관리하고 기준 적용](manage-updates-baselines-microsoft-defender-antivirus.md)
- [보호 업데이트를 다운로드하고 적용해야 하는 경우 관리](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [최신이 지난 끝점에 대한 업데이트 관리](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [모바일 장치 및 VM(가상 머신)에 대한 업데이트 관리](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Windows 10의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-in-windows-10.md)