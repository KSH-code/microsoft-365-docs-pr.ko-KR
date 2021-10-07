---
title: Microsoft Defender 바이러스 백신 보호 업데이트 예약
description: 보호 업데이트를 다운로드해야 하는 시기에 대한 일, 시간 및 간격 예약
keywords: 업데이트, 보안 기준, 업데이트 예약
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
search.appverid: met150
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: f1a163b2f56e84b7c93be99972d5aa62894edfed
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60207754"
---
# <a name="manage-the-schedule-for-when-protection-updates-should-be-downloaded-and-applied"></a>보호 업데이트를 다운로드하여 적용해야 하는 경우에 대한 예약 관리

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

Microsoft Defender 바이러스 백신 업데이트를 찾아 다운로드해야 하는 경우를 결정할 수 있습니다.

다음을 통해 끝점에 대한 업데이트를 예약할 수 있습니다.

- 보호 업데이트를 확인할 날짜 지정
- 보호 업데이트를 확인할 간격 지정
- 보호 업데이트를 확인할 시간 지정

또한 각 끝점에서 보호 업데이트를 확인하고 다운로드하는 시간을 임의로 정할 수 있습니다. 자세한 내용은 [Schedule scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) 항목을 참조하십시오.

## <a name="use-configuration-manager-to-schedule-protection-updates"></a>Configuration Manager를 사용하여 보호 업데이트 예약

1. Microsoft Endpoint Manager 콘솔에서 변경할 맬웨어 방지 정책을 열고(왼쪽의 탐색 창에서 자산 및 규정 준수를  클릭한 다음 개요 Endpoint Protection 맬웨어 방지 정책)  \>  \> 

2. 보안 **인텔리전스 업데이트 섹션으로** 이동하세요.

3. 특정 시기에 업데이트를 확인하고 다운로드하려면
      1. 특정 Endpoint Protection **보안** 인텔리전스 업데이트 **확인...을 0으로 설정하세요.**
      2. 매일 **Endpoint Protection 보안 인텔리전스** 업데이트 확인...을 업데이트 확인 시간으로 설정하세요.
      3 
4. 지속적인 간격으로 업데이트를 확인하고 다운로드하려면 특정 간격으로 Endpoint Protection 보안 인텔리전스 업데이트 **확인...을** 업데이트 간에 발생해야 하는 시간으로 설정하세요.

5. [평소와 같이 업데이트된 정책을 배포합니다.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)

## <a name="use-group-policy-to-schedule-protection-updates"></a>그룹 정책을 사용하여 보호 업데이트 예약

> [!IMPORTANT]
> 기본적으로 Microsoft Defender 바이러스 백신 검사 시간이 15분 전에 업데이트가 확인됩니다. 이러한 설정을 사용하도록 설정하면 해당 기본값이 다시 설정됩니다.

1. 그룹 정책 관리 컴퓨터의 [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))그룹 정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.**

2. 그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동하십시오.**

3. 정책을 **클릭한** 다음 **관리 템플릿을 클릭합니다.**

4. 서명 **인텔리전스 Windows 구성 Microsoft Defender 바이러스 백신** 구성 요소를 \>  \> **확장하고** 다음 설정을 구성합니다.

    1. 보안 인텔리전스 업데이트를 확인할 날짜 지정 설정을 두 번 클릭하고 옵션을 사용으로 **설정합니다.**  업데이트를 확인할 주 중일을 입력합니다. **확인** 을 클릭합니다.
    2. 보안 인텔리전스 업데이트를 확인할 간격 지정 설정을 두 번 클릭하고 옵션을 사용으로 **설정합니다.**  업데이트 사이의 시간을 입력합니다. **확인** 을 클릭합니다.
    3. 보안 인텔리전스 업데이트를 확인할 시간 지정 설정을 두 번 클릭하고 옵션을 사용으로 **설정합니다.**  업데이트를 확인할 시간을 입력합니다. 시간은 끝점의 로컬 시간을 기반으로 합니다. **확인** 을 클릭합니다.

## <a name="use-powershell-cmdlets-to-schedule-protection-updates"></a>PowerShell cmdlet을 사용하여 보호 업데이트 예약

다음 cmdlet을 사용 합니다.

```PowerShell
Set-MpPreference -SignatureScheduleDay
Set-MpPreference -SignatureScheduleTime
Set-MpPreference -SignatureUpdateInterval
```

PowerShell과 함께 PowerShell을 사용하는 방법에 대한 자세한 내용은 [PowerShell cmdlet을](use-powershell-cmdlets-microsoft-defender-antivirus.md) 사용하여 Microsoft Defender 바이러스 백신 및 [Defender cmdlet을](/powershell/module/defender/) 구성하고 실행을 Microsoft Defender 바이러스 백신.

## <a name="use-windows-management-instruction-wmi-to-schedule-protection-updates"></a>WMI(Windows 관리 명령)를 사용하여 보호 업데이트 예약

다음 [  속성에 MSFT_MpPreference  ](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) 클래스의 Set 메서드를 사용합니다.

```WMI
SignatureScheduleDay
SignatureScheduleTime
SignatureUpdateInterval
```

자세한 정보 및 허용되는 매개 변수는 다음을 참조하세요.

- [Windows Defender WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="related-articles"></a>관련 문서

- [배포 Microsoft Defender 바이러스 백신](deploy-manage-report-microsoft-defender-antivirus.md)
- [업데이트 Microsoft Defender 바이러스 백신 관리하고 기준 적용](manage-updates-baselines-microsoft-defender-antivirus.md)
- [최신이 지난 끝점에 대한 업데이트 관리](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [이벤트 기반 강제 업데이트 관리](manage-event-based-updates-microsoft-defender-antivirus.md)
- [모바일 장치 및 VM(가상 머신)에 대한 업데이트 관리](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Windows 10의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-in-windows-10.md)
