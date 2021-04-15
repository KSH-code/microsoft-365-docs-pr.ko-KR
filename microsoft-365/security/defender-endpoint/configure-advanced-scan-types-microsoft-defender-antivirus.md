---
title: Microsoft Defender AV에 대한 검사 옵션 구성
description: '전자 메일 저장소 파일, 백업 또는 재분석 지점, 네트워크 파일 및 보관된 파일(예: .zip 파일)을 검색하도록 Microsoft Defender AV를 구성할 수 있습니다.'
keywords: 고급 검사, 검사, 전자 메일, 보관, zip, rar, 보관, 재분석 검사
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 72d5024446e56cc7fa1d94a7b9402cbe898db2a8
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764858"
---
# <a name="configure-microsoft-defender-antivirus-scanning-options"></a>Microsoft Defender 바이러스 백신 검사 옵션 구성

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/) 

## <a name="use-microsoft-intune-to-configure-scanning-options"></a>Microsoft Intune을 사용하여 검사 옵션 구성

자세한 [내용은 Microsoft Intune의](/intune/device-restrictions-configure) 장치 제한 설정 구성 및 [Intune에서 Windows 10에](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) 대한 Microsoft Defender 바이러스 백신 장치 제한 설정을 참조하세요.

## <a name="use-microsoft-endpoint-manager-to-configure-scanning-options"></a>Microsoft Endpoint Manager를 사용하여 검사 옵션 구성

Microsoft Endpoint Manager(현재 분기)를 구성하는 방법에 대한 자세한 내용은 맬웨어 방지 정책을 만들고 배포하는 [방법:](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings) 검사 설정을 참조하세요.

## <a name="use-group-policy-to-configure-scanning-options"></a>그룹 정책을 사용하여 검사 옵션 구성

다음 표에 설명된 그룹 정책 설정을 구성하려면

1. 그룹 정책 관리 컴퓨터에서 그룹 [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.**

2. 그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동하여** 관리 템플릿 **을 클릭합니다.**

3. **Microsoft Defender** 바이러스 백신을 > Windows 구성  요소로 트리를 확장한 다음 아래 표에 지정된 위치를 확장합니다.

4. 아래 표에 지정된 정책 **설정을** 두 번 클릭하고 옵션을 원하는 구성으로 설정하십시오. 확인 **을** 클릭하고 다른 설정에 대해 반복합니다.

설명 | 위치 및 설정 | 기본 설정(구성되지 않은 경우) | 클래스의 PowerShell `Set-MpPreference` 매개 변수 또는 WMI `MSFT_MpPreference` 속성
---|---|---|---
전자 메일 검색 [전자 메일 검사 제한 참조](#ref1)| 검사 > 전자 메일 검사 켜기 | 사용 안 함 | `-DisableEmailScanning`
[재분석 지점 검사](/windows/win32/fileio/reparse-points) | 검사 > 재분석 지점 검사 켜기 | 사용 안 함 | 사용할 수 없음
매핑된 네트워크 드라이브 검사 | 검사 > 네트워크 드라이브에서 전체 검사 실행 | 사용 안 함 | `-DisableScanningMappedNetworkDrivesForFullScan`
 보관 파일(예: .zip 또는 .rar 파일)을 검사합니다. 확장 [제외](configure-extension-file-exclusions-microsoft-defender-antivirus.md) 목록이 이 설정보다 우선합니다. | 검사 > 보관 파일 검사 | 사용 | `-DisableArchiveScanning`
네트워크의 파일 검색 | 검색 > 네트워크 파일 검사 | 사용 안 함 | `-DisableScanningNetworkFiles`
압축된 실행 실행기 검사 | 검사 > 압축된 실행 실행 | 사용 | 사용할 수 없음
전체 검사 중에 이동식 드라이브 검색만 | 이동식 > 검사 | 사용 안 함 | `-DisableRemovableDriveScanning`
검사할 보관 폴더 내의 하위 폴더 수준 지정 | 검사 > 보관 파일을 검색할 최대 깊이 지정 | 0 | 사용할 수 없음
 검사하는 동안 최대 CPU 부하를 백분율로 지정합니다. 참고: 이는 하드 한도가 아니라 검색 엔진이 평균적으로 이 최대값을 초과하지 않는 지침입니다. | 검사 > 검사 중에 최대 CPU 사용률 지정 | 50 |  `-ScanAvgCPULoadFactor`
 검사해야 하는 보관 파일의 최대 크기(킬로바이트)를 지정합니다. 기본값인 **0** 은 제한 없음을 적용합니다. | 검사 > 검사할 보관 파일의 최대 크기 지정 | 제한 없음 | 사용할 수 없음
 예약된 검사에 대해 낮은 CPU 우선 순위 구성 | 검사 > 예약된 검사에 대해 낮은 CPU 우선 순위 구성 | 사용 안 함 | 사용할 수 없음
 
> [!NOTE]
> 실시간 보호가 켜져 있는 경우 파일에 액세스하고 실행하기 전에 파일을 검사합니다. 검사 범위에는 USB 드라이브와 같은 탑재된 이동식 미디어의 파일을 비롯한 모든 파일이 포함됩니다. 검색을 수행하는 장치에 실시간 보호 또는 액세스 보호가 켜져 있는 경우 검색에는 네트워크 공유도 포함됩니다.

## <a name="use-powershell-to-configure-scanning-options"></a>PowerShell을 사용하여 검사 옵션 구성

Microsoft Defender 바이러스 백신과 함께 PowerShell을 사용하는 방법에 대한 자세한 내용은 [PowerShell cmdlet](use-powershell-cmdlets-microsoft-defender-antivirus.md) 및 [Defender cmdlet을](/powershell/module/defender/) 사용하여 Microsoft Defender 바이러스 백신 관리를 참조하세요.

## <a name="use-wmi-to-configure-scanning-options"></a>WMI를 사용하여 검사 옵션 구성

WMI 클래스를 사용하는 경우 [WMIv2 Windows Defender 를 참조합니다.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

<a id="ref1"></a>

## <a name="email-scanning-limitations"></a>전자 메일 검사 제한 사항

전자 메일 검색을 사용하면 Outlook 및 기타 메일 클라이언트에서 사용하는 전자 메일 파일을 요구 시 및 예약된 검사 중에 검색할 수 있습니다. 첨부 파일 및 보관된 파일과 같은 전자 메일 파일 내에 포함된 개체도 검사됩니다. 다음 파일 형식 형식을 검사하고 수정할 수 있습니다.

- DBX
- MBX
- MIME

Outlook 2003 또는 이전 버전에서 사용하는 PST 파일(보관 유형이 유니코드가 아닌 것으로 설정되어 있는 경우)도 검색되지만, PST Windows Defender 감지된 위협을 수정하지는 못합니다.

Microsoft Defender 바이러스 백신이 전자 메일 내에서 위협을 감지하는 경우 손상된 전자 메일을 식별하는 데 도움이 되는 다음 정보를 표시하여 위협을 수동으로 수정합니다.

- 전자 메일 제목
- 첨부 파일 이름

## <a name="related-topics"></a>관련 항목

- [Microsoft Defender 바이러스 백신 검사 및 수정 사용자 지정, 시작 및 결과 검토](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender 바이러스 백신 검사 구성 및 실행](run-scan-microsoft-defender-antivirus.md)
- [예약된 Microsoft Defender 바이러스 백신 검사 구성](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Windows 10의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-in-windows-10.md)