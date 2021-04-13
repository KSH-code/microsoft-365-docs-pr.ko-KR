---
title: 예약된 검사 및 필요에 따라 검사 실행 및 사용자 지정
description: 네트워크의 끝점에서 Microsoft Defender 바이러스 백신 검색을 사용자 지정하고 시작합니다.
keywords: 검사, 일정, 사용자 지정, 제외, 파일 제외, 수정, 검사 결과, 검지, 위협 제거, 빠른 검사, 전체 검사, Microsoft Defender 바이러스 백신
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 5f8e5606b01186e31a58f6d506b5898f20b63511
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690793"
---
# <a name="customize-initiate-and-review-the-results-of-microsoft-defender-antivirus-scans--remediation"></a>Microsoft Defender 바이러스 백신 검사 사용자 지정, 시작 및 수정 & 검토

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/) 

그룹 정책, PowerShell 및 WMI(Windows Management Instrumentation)를 사용하여 Microsoft Defender 바이러스 백신 검색을 구성할 수 있습니다. 

## <a name="in-this-section"></a>이 섹션의 내용

| 문서 | 설명 |
|:---|:---|
|[Microsoft Defender 바이러스 백신 검사에서 파일, 폴더 및 프로세스에서 연 파일 제외 구성 및 유효성 검사](configure-exclusions-microsoft-defender-antivirus.md) | 파일(지정된 프로세스에서 수정한 파일 포함) 및 폴더를 필요한 검사, 예약된 검사 및 항상 실시간 보호 모니터링 및 검사에서 제외할 수 있습니다. |
|[Microsoft Defender 바이러스 백신 검사 옵션 구성](configure-advanced-scan-types-microsoft-defender-antivirus.md) | 검사에 특정 유형의 전자 메일 저장소 파일, 백업 또는 재분석 지점, 보관된 파일(예: .zip 파일)을 포함하도록 Microsoft Defender 바이러스 백신을 구성할 수 있습니다. 네트워크 파일 검색을 사용하도록 설정할 수 있습니다. |
|[검사에 대한 수정 구성](configure-remediation-microsoft-defender-antivirus.md) | 위협을 감지할 때 Microsoft Defender 바이러스 백신이 어떤 작업을 해야 하는지, 그리고 분리된 파일을 검지 폴더에 보존해야 하는 기간 구성 |
|[예약된 검사 구성](scheduled-catch-up-scans-microsoft-defender-antivirus.md) | 실행해야 하는 시간 및 전체 검사 또는 빠른 검사로 실행 여부를 포함하여 재발(예약된) 검사 설정 |
|[검사 구성 및 실행](run-scan-microsoft-defender-antivirus.md) | PowerShell, Windows Management Instrumentation을 사용하여 또는 Windows 보안 앱을 사용하여 끝점에서 개별적으로 요구 시 검사 실행 및 구성 |
|[검사 결과 검토](review-scan-results-microsoft-defender-antivirus.md) | Microsoft Endpoint Configuration Manager, Microsoft Intune 또는 Windows 보안 앱을 사용하여 검사 결과 검토 |