---
title: Microsoft Defender AV에서 요구 시 검사 실행 및 사용자 지정
description: PowerShell, Windows Management Instrumentation을 사용하여 또는 Windows 보안 앱을 사용하여 끝점에서 개별적으로 요구 시 검사 실행 및 구성
keywords: 검사, on-demand, dos, intune, instant scan
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/13/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 2f60bdb0bbd8b87895547e608b5c3c92414ea834
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691173"
---
# <a name="configure-and-run-on-demand-microsoft-defender-antivirus-scans"></a>Microsoft Defender 바이러스 백신 검사 구성 및 실행

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/) 

개별 끝점에서 필요한 경우 검색을 실행할 수 있습니다. 이러한 검사는 즉시 시작하며 위치 또는 유형과 같은 검사에 대한 매개 변수를 정의할 수 있습니다.

## <a name="quick-scan-versus-full-scan"></a>빠른 검사와 전체 검사

빠른 검사는 레지스트리 키 및 알려진 Windows 시작 폴더와 같이 시스템으로 시작하기 위해 등록된 맬웨어가 있을 수 있는 모든 위치를 확인합니다.

> [!IMPORTANT]
> Microsoft Defender 바이러스 백신은 로컬 검색을 수행할 때 [LocalSystem](/windows/win32/services/localsystem-account) 계정의 컨텍스트에서 실행됩니다. 네트워크 검사의 경우 디바이스 계정의 컨텍스트를 사용합니다. 도메인 장치 계정에 공유에 액세스할 수 있는 적절한 권한이 없는 경우 검사가 작동하지 않습니다. 디바이스에 액세스 네트워크 공유에 대한 사용 권한이 있는지 확인합니다.

파일을 [](configure-real-time-protection-microsoft-defender-antivirus.md)열고 닫을 때 그리고 사용자가 폴더로 이동할 때마다 파일을 검토하는 실시간 보호 기능과 함께 빠른 검사는 시스템으로 시작하는 맬웨어와 커널 수준 맬웨어에 대해 강력한 적용 범위를 제공하는 데 도움이 됩니다.  

대부분의 경우 빠른 검사는 실시간 보호로 선택되지 않은 맬웨어를 찾는 데 적합합니다.

전체 검사는 맬웨어 위협을 보고한 끝점에서 유용할 수 있습니다. 검사는 보다 철저한 정리가 필요한 비활성 구성 요소가 있는지 식별할 수 있습니다. 이는 조직에서 요구 시 검색을 실행하는 경우 이상적입니다.

> [!NOTE]
> 기본적으로 빠른 검사는 USB 드라이브와 같은 탑재된 이동식 장치에서 실행됩니다.

## <a name="use-microsoft-endpoint-manager-to-run-a-scan"></a>Microsoft Endpoint Manager를 사용하여 검사 실행

1. Microsoft Endpoint Manager 관리 센터()로 이동하여 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 로그인합니다.
2. 끝점 **보안 바이러스 백신**  >  **을 선택 합니다.**
3. 탭 목록에서 **Windows 10의 Unhealthy endpoints 를 선택합니다.**
4. 제공된 작업 목록에서 빠른 검사 또는 **전체** 검사 **를 선택합니다.**

[![이미지 ](images/mem-antivirus-scan-on-demand.png)](images/mem-antivirus-scan-on-demand.png#lightbox)

> [!TIP]
> Microsoft Endpoint Manager를 사용하여 검색을 실행하는 방법에 대한 자세한 내용은 맬웨어 방지 및 방화벽 작업: 필요한 경우 검색을 수행하는 [방법을 참조하세요.](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers)

## <a name="use-the-mpcmdrunexe-command-line-utility-to-run-a-scan"></a>명령줄 mpcmdrun.exe 사용하여 검사 실행

다음 매개 `-scan` 변수를 사용합니다.

```console
mpcmdrun.exe -scan -scantype 1
```

전체 검사 시작 또는 경로 정의를 포함하여 도구 및 추가 매개 변수를 사용하는 방법에 대한 자세한 내용은 mpcmdrun.exe 명령줄 도구를 사용하여 Microsoft Defender 바이러스 백신 구성 및 관리를 [참조하세요.](command-line-arguments-microsoft-defender-antivirus.md)

## <a name="use-microsoft-intune-to-run-a-scan"></a>Microsoft Intune을 사용하여 검사 실행

1. Microsoft Endpoint Manager 관리 센터()로 이동하여 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 로그인합니다.
2. 사이드바에서 장치 > **디바이스를 선택하고** 스캔할 장치를 선택합니다.
3. **...를 선택합니다. 추가 .** 옵션에서 빠른 검사 **또는 전체** 검사 **를 선택합니다.**

## <a name="use-the-windows-security-app-to-run-a-scan"></a>Windows 보안 앱을 사용하여 검사 실행

개별 [끝점에서](microsoft-defender-security-center-antivirus.md) 검색을 실행하는 방법에 대한 지침은 Windows 보안 앱에서 검사 실행을 참조하세요.

## <a name="use-powershell-cmdlets-to-run-a-scan"></a>PowerShell cmdlet을 사용하여 검사 실행

다음 cmdlet을 사용 합니다.

```PowerShell
Start-MpScan
```

Microsoft Defender 바이러스 백신에서 PowerShell을 사용하는 방법에 대한 자세한 내용은 [PowerShell cmdlet을](use-powershell-cmdlets-microsoft-defender-antivirus.md) 사용하여 Microsoft Defender 바이러스 백신 및 Defender cmdlet 구성 및 [실행을 참조하세요.](/powershell/module/defender/)

## <a name="use-windows-management-instruction-wmi-to-run-a-scan"></a>WMI(Windows Management Instruction)를 사용하여 검사 실행

이 [ **클래스의 Start**](/previous-versions/windows/desktop/defender/start-msft-mpscan) 메서드를 MSFT_MpScan **사용합니다.**

허용되는 매개 변수에 대한 자세한 내용은 [WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) API Windows Defender 참조하세요.

## <a name="related-articles"></a>관련 문서

- [Microsoft Defender 바이러스 백신 검사 옵션 구성](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [예약된 Microsoft Defender 바이러스 백신 검사 구성](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Windows 10의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-in-windows-10.md)