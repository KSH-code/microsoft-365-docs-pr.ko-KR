---
title: PowerShell을 사용하여 바이러스 백신 검사 예약
description: PowerShell을 사용하여 바이러스 백신 검사 예약
keywords: 빠른 검사, 전체 검사, 바이러스 백신, 일정, PowerShell
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
ms.openlocfilehash: 1c9dc7f6b5b34fbfd2eb2c6b76b62650d0d213ca
ms.sourcegitcommit: 584445b62cb82218597b62495fb76fcb5b12af9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2021
ms.locfileid: "59498235"
---
# <a name="schedule-antivirus-scans-using-powershell"></a>PowerShell을 사용하여 바이러스 백신 검사 예약

**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

이 문서에서는 PowerShell cmdlet을 사용하여 예약된 검색을 구성하는 방법을 설명합니다. 검사 예약 및 검사 유형에 대한 자세한 내용은 [Configure scheduled quick or full Microsoft Defender 바이러스 백신 scan을 참조합니다.](schedule-antivirus-scans.md) 

## <a name="use-powershell-cmdlets-to-schedule-scans"></a>PowerShell cmdlet을 사용하여 검사 예약

다음 cmdlet을 사용 합니다.

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

자세한 내용은 [PowerShell cmdlet을](use-powershell-cmdlets-microsoft-defender-antivirus.md) 사용하여 구성 및 Microsoft Defender 바이러스 백신 및 [Defender cmdlet을](/powershell/module/defender/) 사용하여 PowerShell을 사용하는 방법에 대한 자세한 Microsoft Defender 바이러스 백신.

## <a name="powershell-cmdlets-for-scheduling-scans-when-an-endpoint-is-not-in-use"></a>끝점이 사용되지 않는 경우 검색을 위한 PowerShell cmdlet

다음 cmdlet을 사용 합니다.

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

자세한 내용은 [PowerShell cmdlet을 사용하여 Microsoft Defender 바이러스 백신 구성 및 실행](use-powershell-cmdlets-microsoft-defender-antivirus.md)과 [Defender cmdlet](/powershell/module/defender/)을 참조하세요.

> [!NOTE]
> 끝점이 사용되지 않는 시간을 위해 검색을 예약하는 경우 검색은 CPU 스로틀 구성을 적용하지 못하며 가능한 한 빨리 검색을 완료하기 위해 사용 가능한 리소스를 최대한 활용합니다.

## <a name="powershell-cmdlets-for-scheduling-scans-to-complete-remediation"></a>재구성 완료를 위한 검사에 대한 PowerShell cmdlet

다음 cmdlet을 사용 합니다.

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

PowerShell과 함께 PowerShell을 사용하는 방법에 대한 자세한 내용은 [PowerShell cmdlet을](use-powershell-cmdlets-microsoft-defender-antivirus.md) 사용하여 Microsoft Defender 바이러스 백신 및 [Defender cmdlet을](/powershell/module/defender/) 구성하고 실행을 Microsoft Defender 바이러스 백신.

## <a name="powershell-cmdlets-for-scheduling-daily-scans"></a>매일 검색을 위한 PowerShell cmdlet

다음 cmdlet을 사용 합니다.

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

PowerShell과 함께 PowerShell을 사용하는 방법에 대한 자세한 Microsoft Defender 바이러스 백신 [PowerShell cmdlet을](use-powershell-cmdlets-microsoft-defender-antivirus.md) 사용하여 Microsoft Defender 바이러스 백신 [및 Defender cmdlet](/powershell/module/defender/)구성 및 실행을 참조하세요.


