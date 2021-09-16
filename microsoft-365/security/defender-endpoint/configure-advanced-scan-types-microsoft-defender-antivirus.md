---
title: 사용자에 대한 검사 옵션 Microsoft Defender 바이러스 백신
description: '전자 메일 저장소 파일, 백업 또는 재분석 지점, 네트워크 파일 및 보관된 파일(예: .zip 파일)을 검색하도록 Microsoft Defender AV를 구성할 수 있습니다.'
keywords: 고급 검사, 검사, 전자 메일, 보관, zip, rar, 보관, 재분석 검사
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.date: 09/14/2021
ms.topic: how-to
ms.openlocfilehash: 87200c519aa27a2f8472a025f90a283978fd21a0
ms.sourcegitcommit: 4740e69326eb7f8302eec7bab5bd516d498e4492
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/16/2021
ms.locfileid: "59399817"
---
# <a name="configure-microsoft-defender-antivirus-scanning-options"></a>Microsoft Defender 바이러스 백신 검사 옵션 구성

**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

## <a name="use-microsoft-intune-to-configure-scanning-options"></a>검색 Microsoft Intune 사용하여 검사 옵션 구성

자세한 내용은 [Intune에서](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)Microsoft Intune 및 Microsoft Defender 바이러스 백신 장치 제한 설정 구성을 Windows 10 참조하세요. [](/intune/device-restrictions-configure)

## <a name="use-microsoft-endpoint-manager-to-configure-scanning-options"></a>검색 Microsoft Endpoint Manager 사용하여 검사 옵션 구성

맬웨어 방지 정책(현재 분기Microsoft Endpoint Manager 구성하는 방법에 대한 자세한 내용은 맬웨어 방지 정책을 만들고 배포하는 [방법: 검사 설정 을 참조하세요.](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings)

## <a name="use-group-policy-to-configure-scanning-options"></a>그룹 정책을 사용하여 검사 옵션 구성

1. 그룹 정책 관리 컴퓨터에서 [그룹 정책 관리 콘솔](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))을 엽니다.

2. 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭한 다음 편집 **을 선택합니다.**

3. 그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동하여** 관리 템플릿 **을 클릭합니다.**

4. 트리를 확장하여 Windows **구성** Microsoft Defender 바이러스 백신 를 선택한 다음 위치를 \> 선택합니다(이 [문서의](#settings-and-locations) 설정 위치 참조).

5. 정책 개체를 편집합니다.

6. 확인 **을** 클릭하고 다른 설정에 대해 반복합니다.

### <a name="settings-and-locations"></a>설정 및 위치

|정책 항목 및 위치|기본 설정(구성되지 않은 경우)|클래스의 PowerShell `Set-MpPreference` 매개 변수 또는 WMI `MSFT_MpPreference` 속성|
|---|---|---|
|전자 메일 검사 <p> **스캔** \> **전자 메일 검사 켜기**<p>전자 [메일 검색 제한(이](#email-scanning-limitations) 문서의)을 참조하세요.|사용 안 함|`-DisableEmailScanning`|
|[재분석 지점 검사](/windows/win32/fileio/reparse-points) <p> **스캔** \> **재분석 지점 검사 켜기**|사용 안 함|사용할 수 없음 <p>[재분석 지점 참조](/windows/win32/fileio/reparse-points)|
|매핑된 네트워크 드라이브 검사 <p> **스캔** \> **매핑된 네트워크 드라이브에서** 전체 검사 실행|사용 안 함|`-DisableScanningMappedNetworkDrivesForFullScan`|
|보관 파일(예: 파일 .zip 또는 .rar 검사). <p> **스캔** \> **보관 파일 검사**|사용|`-DisableArchiveScanning` <p>확장 [제외](configure-extension-file-exclusions-microsoft-defender-antivirus.md) 목록이 이 설정보다 우선합니다.|
|네트워크의 파일 검색 <p> **스캔** \> **네트워크 파일 검사**|사용 안 함|`-DisableScanningNetworkFiles`|
|압축된 실행 실행기 검사 <p> **스캔** \> **압축된 실행 실행기 검사**|사용|사용할 수 없음|
|전체 검사 중에 이동식 드라이브 검색만 <p> **스캔** \> **이동식 드라이브 검사**|사용 안 함|`-DisableRemovableDriveScanning`|
|검사할 보관 폴더 내의 하위 폴더 수준 지정 <p>**스캔** \> **보관 파일을 검색할 최대 깊이 지정**|0|사용할 수 없음|
|검사하는 동안 최대 CPU 부하를 백분율로 지정합니다. <p> **스캔** \> **검사 중 CPU 사용률의 최대 백분율 지정**|50|`-ScanAvgCPULoadFactor` <p>**참고:** 최대 CPU 부하는 하드 한도가 아니며 검색 엔진이 평균 최대값을 초과하지 않는 지침입니다. 수동 실행 검사는 이 설정을 무시하고 CPU 제한 없이 실행됩니다.|
|검사해야 하는 보관 파일의 최대 크기(킬로바이트)를 지정합니다. <p> **스캔** \> **검사할 보관 파일의** 최대 크기 지정|제한 없음|사용할 수 없음 <p>기본값인 0은 제한 없음을 적용합니다.|
|예약된 검사에 대해 낮은 CPU 우선 순위 구성 <p> **스캔** \> **예약된 검사에 대해 낮은 CPU 우선 순위 구성**|사용 안 함|사용할 수 없음|

> [!NOTE]
> 실시간 보호가 켜져 있는 경우 파일에 액세스하고 실행하기 전에 파일을 검사합니다. 검사 범위에는 USB 드라이브와 같은 탑재된 이동식 미디어의 파일을 비롯한 모든 파일이 포함됩니다. 검색을 수행하는 장치에 실시간 보호 또는 액세스 보호가 켜져 있는 경우 검색에는 네트워크 공유도 포함됩니다.

## <a name="use-powershell-to-configure-scanning-options"></a>PowerShell을 사용하여 검사 옵션 구성

PowerShell과 함께 PowerShell을 사용하는 방법에 대한 자세한 Microsoft Defender 바이러스 백신 참조하세요.

- [PowerShell cmdlet을 사용하여 Microsoft Defender 바이러스 백신 관리](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Defender cmdlet](/powershell/module/defender/)

## <a name="use-wmi-to-configure-scanning-options"></a>WMI를 사용하여 검사 옵션 구성

[WMIv2 api를 Windows Defender 참조합니다.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="email-scanning-limitations"></a>전자 메일 검사 제한 사항

전자 메일 검색을 사용하면 사용자 Outlook 예약된 검사 중에 전자 메일 클라이언트 및 기타 메일 클라이언트에서 사용하는 전자 메일 파일을 검색할 수 있습니다. 전자 메일에 포함된 개체(예: 첨부 파일 및 보관된 파일)도 검사됩니다. 다음 파일 형식 형식을 검사하고 수정할 수 있습니다.

- DBX
- MBX
- MIME

Outlook 2003 또는 이전 버전에서 사용하는 PST 파일(보관 유형이 유니코드가 아닌 것으로 설정되어 있는 경우)도 검색되지만 Microsoft Defender 바이러스 백신 PST 파일 내에서 감지된 위협을 수정하지 못합니다.

전자 Microsoft Defender 바이러스 백신 내부에서 위협을 감지하는 경우 위협을 수동으로 수정할 수 있도록 손상된 전자 메일을 식별하는 데 도움이 되는 다음 정보가 표시됩니다.

- 전자 메일 제목
- 첨부 파일 이름

## <a name="scanning-mapped-network-drives"></a>매핑된 네트워크 드라이브 검사

모든 OS에서 시스템 수준에서 매핑된 네트워크 드라이브만 검색됩니다. 사용자 수준 매핑된 네트워크 드라이브는 검색되지 않습니다. 사용자 수준 매핑된 네트워크 드라이브는 사용자가 수동으로 자신의 자격 증명을 사용하여 세션에 매핑하는 드라이브입니다.

## <a name="see-also"></a>참고 항목

- [사용자 지정, 시작 및 재구성 결과 Microsoft Defender 바이러스 백신 검토](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [요청 기반 Microsoft Defender 바이러스 백신 검사 구성 및 실행](run-scan-microsoft-defender-antivirus.md)
- [예약된 Microsoft Defender 바이러스 백신 구성](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Windows 10의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-in-windows-10.md)
