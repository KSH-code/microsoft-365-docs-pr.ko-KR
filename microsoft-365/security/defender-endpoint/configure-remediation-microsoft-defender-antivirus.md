---
title: Microsoft Defender 바이러스 백신 검색에 대한 수정 구성
description: 위협을 감지할 때 Microsoft Defender 바이러스 백신이 어떤 작업을 해야 하는지, 그리고 분리된 파일을 검지 폴더에 보존해야 하는 기간 구성
keywords: 수정, 수정, 제거, 위협, 검지, 검사, 복원
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 03/16/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 7f41e9c5b38e93ce84fbd971e02ebc2d77432c3f
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690860"
---
# <a name="configure-remediation-for-microsoft-defender-antivirus-detections"></a>Microsoft Defender 바이러스 백신 검색에 대한 수정 구성

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/) 

Microsoft Defender 바이러스 백신이 검색을 실행하면 감지된 위협을 수정하거나 제거하려고 시도합니다. Microsoft Defender 바이러스 백신이 특정 위협을 어떻게 해결해야 하는지, 수정하기 전에 복원 지점을 만들어야 하는지 여부 및 위협을 제거해야 하는 시점을 구성할 수 있습니다.

이 문서에서는 그룹 정책을 사용하여 이러한 설정을 구성하는 방법에 대해 설명하지만 [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#threat-overrides-settings) 및 Microsoft [Intune을](/intune/device-restrictions-configure)사용할 수 있습니다. 

[ `Set-MpPreference` PowerShell cmdlet](/powershell/module/defender/set-mppreference) 또는 [ `MSFT_MpPreference` WMI](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) 클래스를 사용하여 이러한 설정을 구성할 수도 있습니다.

## <a name="configure-remediation-options"></a>수정 옵션 구성

1. 그룹 정책 관리 컴퓨터에서 그룹 [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.**

2. 그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동하고** 관리 템플릿 **을 선택합니다.**

3. Windows 구성 요소 Microsoft Defender **바이러스 백신까지**  >  **트리를 확장합니다.** 

4. 아래 표를 사용하여 위치를 선택한 다음 필요한 경우 정책을 편집합니다. 

5. **확인** 을 선택합니다.

|위치 | 설정 | 설명 | 기본 설정(구성되지 않은 경우) |
|:---|:---|:---|:---|
|검사 | 시스템 복원 지점 만들기 | 정리 또는 검사가 시도되기 전에 매일 시스템 복원 지점이 생성됩니다. | 사용 안 함|
|검사 | 검사 기록 폴더에서 항목 제거 설정 | 검사 기록에 항목을 보관할 일 수 지정 | 30일 |
|루트 | 루틴 수정 끄기 | Microsoft Defender 바이러스 백신이 위협을 자동으로 수정하는지 또는 끝점 사용자에게 어떤 작업을 해야 하는지 여부를 지정할 수 있습니다. | 사용하지 않도록 설정(위협이 자동으로 수정) |
|격리 | Quarantine 폴더에서 항목 제거 구성 | 항목을 제거하기 전에 보관할 날짜 수 지정 | 90일 |
|위협 | 감지 시 기본 작업을 수행하지 않을 위협 경고 수준 지정 | Microsoft Defender 바이러스 백신에서 감지되는 모든 위협에는 위협 수준(낮음, 중간, 높음 또는 심각)이 할당됩니다. 이 설정을 사용하여 각 위협 수준에 대한 모든 위협을 수정하는 방법(분리, 제거 또는 무시)을 정의할 수 있습니다. | 해당 없음 |
|위협 | 검색 시 기본 작업을 수행하지 않을 위협 지정 | 특정 위협(위협 ID 사용)을 수정하는 방법을 지정합니다. 특정 위협을 분리, 제거 또는 무시할지 여부를 지정할 수 있습니다. | 해당 없음 |

> [!IMPORTANT]
> Microsoft Defender 바이러스 백신은 여러 요인에 따라 파일을 검색하고 수정합니다. 경우에 따라 수정을 완료하려면 재부팅이 필요합니다. 검색이 나중에 가음성으로 확인된 경우에도 모든 추가 수정 단계가 완료되도록 재부팅을 완료해야 합니다.
>
> 특정 Microsoft Defender 바이러스 백신이 가변 긍정에 따라 파일을 검지한 경우 장치를 다시 시작한 후 파일을 검지에서 복원할 수 있습니다. Microsoft Defender 바이러스 [백신에서 quarantined 파일 복원을 참조합니다.](restore-quarantined-files-microsoft-defender-antivirus.md)
> 
> 향후 이 문제를 방지하려면 검사에서 파일을 제외하면 됩니다. Microsoft Defender 바이러스 백신 검사에 대한 제외 구성 [및 유효성 검사를 참조합니다.](configure-exclusions-microsoft-defender-antivirus.md)

또한 [수정이](scheduled-catch-up-scans-microsoft-defender-antivirus.md#remed) 필요한 예약된 전체 Microsoft Defender 바이러스 백신 검사 구성을 참조하여 수정 관련 설정을 참조하세요.

## <a name="see-also"></a>참고 항목

- [Microsoft Defender 바이러스 백신 검사 옵션 구성](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [예약된 Microsoft Defender 바이러스 백신 검사 구성](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender 바이러스 백신 검사 구성 및 실행](run-scan-microsoft-defender-antivirus.md)
- [끝점에 나타나는 알림 구성](configure-notifications-microsoft-defender-antivirus.md)
- [최종 사용자 Microsoft Defender 바이러스 백신 상호 작용 구성](configure-end-user-interaction-microsoft-defender-antivirus.md)
- [Microsoft Defender 바이러스 백신 검사 및 수정 사용자 지정, 시작 및 결과 검토](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Windows 10의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-in-windows-10.md)