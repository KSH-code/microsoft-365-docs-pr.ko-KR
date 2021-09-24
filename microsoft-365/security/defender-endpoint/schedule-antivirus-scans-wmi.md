---
title: 관리 계측을 사용하여 바이러스 Windows 예약
description: WMI를 사용하여 바이러스 백신 검사 예약
keywords: 빠른 검사, 전체 검사, WMI, 일정, 바이러스 백신
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/09/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.collection: M365-security-compliance
ms.openlocfilehash: ed314a9c0c894d885571b8493a33674da7471343
ms.sourcegitcommit: 584445b62cb82218597b62495fb76fcb5b12af9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2021
ms.locfileid: "59498211"
---
# <a name="schedule-antivirus-scans-using-windows-management-instrumentation-wmi"></a>WMI(WMI(Windows Management Instrumentation))를 사용하여 바이러스 백신 검사 예약

**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

이 문서에서는 WMI를 사용하여 예약된 검색을 구성하는 방법을 설명합니다. 검사 예약 및 검사 유형에 대한 자세한 내용은 [Configure scheduled quick or full Microsoft Defender 바이러스 백신 scan을 참조합니다.](schedule-antivirus-scans.md) 

## <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a>WMI(Windows 관리 명령)를 사용하여 검사 예약

다음 [  속성에 MSFT_MpPreference  ](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) 클래스의 Set 메서드를 사용합니다.

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

자세한 내용은 [WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) API Windows Defender 참조하세요.

## <a name="wmi-for-scheduling-scans-when-an-endpoint-is-not-in-use"></a>끝점이 사용되지 않는 경우 검색을 위한 WMI

다음 [속성에 MSFT_MpPreference 클래스의 Set](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) 메서드를 사용합니다.

```WMI
ScanOnlyIfIdleEnabled
```

API 및 허용되는 매개 변수에 대한 자세한 내용은 [WMIv2 api Windows Defender 참조하세요.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

> [!NOTE]
> 끝점이 사용되지 않는 시간을 위해 검색을 예약하는 경우 검색은 CPU 스로틀 구성을 적용하지 못하며 가능한 한 빨리 검색을 완료하기 위해 사용 가능한 리소스를 최대한 활용합니다.


## <a name="wmi-for-scheduling-scans-to-complete-remediation"></a>재구성 완료를 위한 검사 예정용 WMI

다음 [  속성에 MSFT_MpPreference  ](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) 클래스의 Set 메서드를 사용합니다.

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

자세한 정보 및 허용되는 매개 변수는 [WMIv2 api Windows Defender 참조하세요.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="wmi-for-scheduling-daily-scans"></a>일별 검색을 위한 WMI

다음 [  속성에 MSFT_MpPreference  ](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) 클래스의 Set 메서드를 사용합니다.

```WMI
ScanScheduleQuickScanTime
```

자세한 정보 및 허용되는 매개 변수는 [WMIv2 api Windows Defender 참조하세요.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

