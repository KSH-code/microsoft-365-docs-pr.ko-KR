---
title: Windows 10의 Microsoft Defender Offline
description: Microsoft Defender Offline은 바이러스 백신 앱에서 바로 Windows Defender 있습니다. 네트워크에서 배포되는 방법을 관리할 수도 있습니다.
keywords: 검사, defender, 오프라인
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 44a0e78ecfe3854a070831bf01a012c2cec06ce7
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690933"
---
# <a name="run-and-review-the-results-of-a-microsoft-defender-offline-scan"></a>Microsoft Defender 오프라인 검사 실행 및 결과 검토

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/) 

Microsoft Defender Offline은 신뢰할 수 있는 환경에서 부팅하고 검색을 실행할 수 있는 맬웨어 방지 검사 도구입니다. 검사는 일반 Windows 커널 외부에서 실행됩니다. 따라서 MBR(마스터 부트 레코드)을 감염 또는 덮어오는 바이러스 및 루트키와 같이 Windows 셸을 무시하려는 맬웨어를 대상으로 할 수 있습니다.

맬웨어 감염이 의심되는 경우 또는 맬웨어 발생 후 끝점을 완전히 정리하려는 경우 Microsoft Defender Offline을 사용할 수 있습니다.

Windows 10에서는 Windows 보안 앱에서 직접 한 번의 클릭으로 Microsoft Defender Offline을 실행할 [수 있습니다.](microsoft-defender-security-center-antivirus.md) 이전 버전의 Windows에서는 사용자가 부팅 가능한 미디어에 Microsoft Defender Offline을 설치하고 끝점을 다시 시작하고 부팅 가능한 미디어를 로드해야 합니다.

## <a name="prerequisites-and-requirements"></a>선행 조건 및 요구 사항

Windows 10의 Microsoft Defender Offline은 Windows 10과 하드웨어 요구 사항이 동일합니다. 

Windows 10 요구 사항에 대한 자세한 내용은 다음 항목을 참조하세요.

- [최소 하드웨어 요구 사항](/windows-hardware/design/minimum/minimum-hardware-requirements-overview)

- [하드웨어 구성 요소 지침](/windows-hardware/design/component-guidelines/components)

> [!NOTE]
> Microsoft Defender Offline은 프로세서가 ARM 또는 Windows Server Stock Keeping Units에서 지원되지 않습니다.

끝점에서 Microsoft Defender Offline을 실행하려면 사용자가 관리자 권한으로 로그인되어 있어야 합니다.
 
## <a name="microsoft-defender-offline-updates"></a>Microsoft Defender 오프라인 업데이트

Microsoft Defender Offline은 끝점에서 사용할 수 있는 최신 보호 업데이트를 사용 합니다. 바이러스 백신이 업데이트될 때마다 Windows Defender 업데이트됩니다. 

> [!NOTE]
> 오프라인 검색을 실행하기 전에 Microsoft Defender AV 보호를 업데이트해야 합니다. 그룹 정책을 사용하여 업데이트를 강제 적용하거나 일반적으로 끝점에 업데이트를 배포하거나 에서 수동으로 최신 보호 업데이트를 다운로드하여 설치할 [Microsoft 맬웨어 보호 센터.](https://www.microsoft.com/security/portal/definitions/adl.aspx)

자세한 내용은 [Microsoft Defender 바이러스 백신 보안 인텔리전스 업데이트 관리](manage-protection-updates-microsoft-defender-antivirus.md) 항목을 참조하세요.

## <a name="usage-scenarios"></a>사용 시나리오

Windows 10 버전 1607에서는 오프라인 스캔을 수동으로 강제할 수 있습니다. 또는 Windows Defender Microsoft Defender Offline을 실행해야 하도록 결정하면 끝점에서 사용자에게 메시지를 표시하는 메시지가 표시될 수 있습니다. 

오프라인 검사 수행의 필요성은 끝점을 관리하는 데 사용하는 경우 Microsoft Endpoint Manager에도 공개됩니다.

프롬프트는 다음과 유사한 알림을 통해 발생할 수 있습니다.

![Microsoft Defender 오프라인 실행 요구 사항을 보여주는 Windows 알림](images/defender/notification.png)

또한 사용자는 클라이언트 내에서 Windows Defender 알림을 하게 됩니다.

Configuration Manager에서 **Monitoring > Overview > Endpoint Protection Status > System Center Endpoint Protection Status로**> 끝점 상태를 식별할 수 있습니다. 

Microsoft Defender 오프라인 검사는  오프라인 검사가 필요하여 맬웨어 수정 **상태 아래에 표시됩니다.**

![Microsoft Defender 오프라인 검사 필요를 나타내는 Microsoft Endpoint Manager](images/defender/sccm-wdo.png)

## <a name="configure-notifications"></a>알림 구성

Microsoft Defender 오프라인 알림은 다른 Microsoft Defender AV 알림과 동일한 정책 설정으로 구성됩니다.

앱의 알림에 Windows Defender 끝점에 나타나는 알림 구성 항목을 [참조하세요.](configure-notifications-microsoft-defender-antivirus.md)

## <a name="run-a-scan"></a>검사 실행 

> [!IMPORTANT]
> Microsoft Defender Offline을 사용하기 전에 파일을 저장하고 실행 중인 프로그램을 종료해야 합니다. Microsoft Defender Offline 검사는 실행하는 데 15분 정도 걸립니다. 검사가 완료되면 끝점이 다시 시작됩니다. 검사는 일반적인 Windows 운영 환경 외부에서 수행됩니다. 사용자 인터페이스는 사용자가 수행한 일반 검사와 다르게 Windows Defender. 검사가 완료되면 끝점이 다시 시작하고 Windows가 정상적으로 로드됩니다.

다음을 사용하여 Microsoft Defender Offline 스캔을 실행할 수 있습니다.

- PowerShell
- WMI(Windows Management Instrumentation)
- Windows 보안 앱



### <a name="use-powershell-cmdlets-to-run-an-offline-scan"></a>PowerShell cmdlet을 사용하여 오프라인 검사 실행

다음 cmdlet을 사용 합니다.

```PowerShell
Start-MpWDOScan
```

Microsoft Defender 바이러스 백신과 함께 PowerShell을 사용하는 방법에 대한 자세한 내용은 [PowerShell cmdlet을](use-powershell-cmdlets-microsoft-defender-antivirus.md) 사용하여 Microsoft Defender 바이러스 백신 및 [Defender cmdlet](/powershell/module/defender/) 구성 및 실행을 참조하세요.

### <a name="use-windows-management-instruction-wmi-to-run-an-offline-scan"></a>WMI(Windows Management Instruction)를 사용하여 오프라인 검사 실행

MSFT_MpWDOScan [**클래스를**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) 사용하여 오프라인 검색을 실행합니다.

다음 WMI 스크립트 코드 코드는 즉시 Microsoft Defender Offline 스캔을 실행합니다. 그러면 끝점이 다시 시작하고 오프라인 검색을 실행한 다음 Windows로 다시 시작 및 부팅됩니다.

```console
wmic /namespace:\\root\Microsoft\Windows\Defender path MSFT_MpWDOScan call Start 
```

자세한 내용은 다음을 참조하세요.
- [Windows Defender WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


### <a name="use-the-windows-defender-security-app-to-run-an-offline-scan"></a>보안 Windows Defender 사용하여 오프라인 검사 실행

1. 작업 표시줄에서 방패 아이콘을 클릭하거나 **Defender의** 시작 메뉴를 검색하여 Windows 보안 앱을 열 수 있습니다.

2. 바이러스 & **보호** 타일(또는 왼쪽 메뉴 표시줄의 방패 아이콘)을 클릭한 다음 **고급 검사 레이블을** 클릭합니다.
    
3. **Microsoft Defender Offline 검사 를 선택하고** 지금 **스캔을 클릭합니다.**

    > [!NOTE]
    > Windows 10 버전 1607에서 오프라인 검사는 **Windows** 설정 업데이트 및 보안 & 또는 Windows Defender 클라이언트에서 Windows Defender  >    >   수 있습니다.


## <a name="review-scan-results"></a>검사 결과 검토

Microsoft Defender 오프라인 검사 결과가 Windows 보안 앱의 검사 기록 [섹션에 나열됩니다.](microsoft-defender-security-center-antivirus.md) 


## <a name="related-articles"></a>관련 문서

- [검사 및 수정 결과 사용자 지정, 시작 및 검토](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Windows 10의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-in-windows-10.md)