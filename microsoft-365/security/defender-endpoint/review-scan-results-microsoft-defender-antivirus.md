---
title: 검사 결과 Microsoft Defender 바이러스 백신 검토
description: Microsoft Endpoint Configuration Manager, Microsoft Intune 또는 앱 앱을 사용하여 검사 Windows 보안 검토
keywords: 검사 결과, 수정, 전체 검사, 빠른 검사
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/18/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: cec44ad879eb7e425fa8ed20daa468eae7c61af1
ms.sourcegitcommit: e09ced3e3628bf2ccb84d205d9699483cbb4b3b0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2021
ms.locfileid: "60881772"
---
# <a name="review-microsoft-defender-antivirus-scan-results"></a>검사 Microsoft Defender 바이러스 백신 검토

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

검사가 Microsoft Defender 바이러스 백신 검사가 완료되면 결과가 기록되어 [](run-scan-microsoft-defender-antivirus.md) 결과를 볼 [](scheduled-catch-up-scans-microsoft-defender-antivirus.md)수 있습니다. 


## <a name="use-configuration-manager-to-review-scan-results"></a>Configuration Manager를 사용하여 검사 결과 검토

상태 [를 모니터링하는 Endpoint Protection 참조합니다.](/configmgr/protect/deploy-use/monitor-endpoint-protection)

## <a name="use-powershell-cmdlets-to-review-scan-results"></a>PowerShell cmdlet을 사용하여 검사 결과 검토

다음 cmdlet은 끝점에서 각 검색을 반환합니다. 동일한 위협이 여러 번 검색된 경우 각 검색 시간을 기준으로 각 검색이 별도로 나열됩니다.

```PowerShell
Get-MpThreatDetection
```

:::image type="content" source="../../media/wdav-get-mpthreatdetection.png" alt-text="PowerShell cmdlet 및 출력 스크린샷":::

특정 위협에 대한 검색만 표시하도록 출력을 `-ThreatID` 제한하도록 지정할 수 있습니다.

위협 검색을 나열하지만 동일한 위협의 검색을 단일 항목으로 결합하려는 경우 다음 cmdlet을 사용할 수 있습니다.

```PowerShell
Get-MpThreat
```

:::image type="content" source="../../media/wdav-get-mpthreat.png" alt-text="PowerShell 코드.":::

PowerShell과 함께 PowerShell을 사용하는 방법에 대한 자세한 내용은 [PowerShell cmdlet을](use-powershell-cmdlets-microsoft-defender-antivirus.md) 사용하여 Microsoft Defender 바이러스 백신 및 [Defender cmdlet을](/powershell/module/defender/) 구성하고 실행을 Microsoft Defender 바이러스 백신.

## <a name="use-windows-management-instruction-wmi-to-review-scan-results"></a>WMI(Windows 관리 지침)를 사용하여 검사 결과 검토

MSFT_MpThreat 클래스의 [ **Get** **MSFT_MpThreatDetection**](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) 사용합니다.


## <a name="related-articles"></a>관련 문서

- [사용자 지정, 시작 및 재구성 결과 Microsoft Defender 바이러스 백신 검토](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Windows 10의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-in-windows-10.md)