---
title: Windows 보안 앱의 Microsoft Defender 바이러스 백신
description: 이제 Microsoft Defender 바이러스 백신이 Windows 보안 앱에 포함되어 있는 경우 일반적인 작업을 검토, 비교 및 수행할 수 있습니다.
keywords: wdav, 바이러스 백신, 방화벽, 보안, windows
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 7635209c03dfc0367df16bfb650a4e52d2b2b3f8
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765326"
---
# <a name="microsoft-defender-antivirus-in-the-windows-security-app"></a>Windows 보안 앱의 Microsoft Defender 바이러스 백신

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/) 

Windows 10 버전 1703 이상에서 Windows Defender 앱은 Windows 보안의 일부입니다.

이전에는 Windows Defender Windows 설정에 추가된 설정이 결합되어 Windows 10 버전 1703의 일부로 기본적으로 설치되는 새 앱으로 이동되었습니다.

> [!IMPORTANT]
> Windows 보안 센터 서비스를 사용하지 않도록 설정하면 Microsoft Defender 바이러스 백신 또는 방화벽이 Windows Defender [않습니다.](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) 타사 바이러스 백신 또는 방화벽 제품을 설치하고 최신 상태로 유지하면 이러한 기능이 자동으로 사용하지 않도록 설정됩니다.
>
> Windows 보안 센터 서비스를 사용하지 않도록 설정하거나 연결된 그룹 정책 설정을 구성하여 시작하거나 실행하지 못하도록 하는 경우 Windows 보안 앱은 장치에 설치한 바이러스 백신 또는 방화벽 제품에 대한 부실하거나 부정확한 정보를 표시할 수 있습니다.
> 또한 이전 또는 오래된 타사 바이러스 백신이 있는 경우 또는 이전에 설치한 타사 바이러스 백신 제품을 제거한 경우 Microsoft Defender 바이러스 백신이 자체적으로 활성화되지 않도록 할 수 있습니다.
> 이렇게 하면 장치의 보호가 현저히 낮아지며 맬웨어 감염으로 이어질 수 있습니다.

앱에서 [모니터링할 수](/windows/threat-protection/windows-defender-security-center/windows-defender-security-center) 있는 다른 Windows 보안 기능에 대한 자세한 내용은 Windows 보안 문서를 참조하세요.

Windows 보안 앱은 Windows 10 버전 1703 이상의 클라이언트 인터페이스입니다. 끝점용 Microsoft Defender를 검토하고 관리하는 데 사용되는 Microsoft Defender 보안 센터 [웹 포털이 아니며,](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)

## <a name="review-virus-and-threat-protection-settings-in-the-windows-security-app"></a>Windows 보안 앱에서 바이러스 및 위협 방지 설정 검토

![Windows 보안 앱의 바이러스 & 보호 설정 레이블 스크린샷](images/defender/wdav-protection-settings-wdsc.png)

1. 작업 표시줄에서 방패 아이콘을 클릭하거나 **Defender의** 시작 메뉴를 검색하여 Windows 보안 앱을 열 수 있습니다.

2. 바이러스 & **보호** 타일(또는 왼쪽 메뉴 표시줄의 방패 아이콘)을 선택합니다.
   
다음 섹션에서는 Windows 보안 앱에서 Microsoft Defender 바이러스 백신에서 제공하는 위협 방지를 검토하거나 상호 작용할 때 가장 일반적인 몇 가지 작업을 수행하는 방법을 설명합니다.

> [!NOTE]
> 그룹 정책을 사용하여 이러한 설정을 구성하고 배포하는 경우 이 섹션에 설명된 설정은 회색으로 표시됩니다. 개별 끝점에서 사용할 수 없습니다. 그룹 정책 개체를 통해 변경한 내용은 먼저 개별 끝점에 배포해야 설정이 Windows 설정에서 업데이트됩니다. Microsoft Defender 바이러스 [백신과의 최종](configure-end-user-interaction-microsoft-defender-antivirus.md) 사용자 상호 작용 구성 항목에서는 로컬 정책이 설정을 구성하는 방법에 대해 설명합니다.

## <a name="run-a-scan-with-the-windows-security-app"></a>Windows 보안 앱을 통해 검사 실행

1. 시작 메뉴에서 보안 을 검색한 다음 Windows 보안 을 선택하여 Windows 보안 **앱을 열 수 있습니다.**

2. 바이러스 & **보호** 타일(또는 왼쪽 메뉴 표시줄의 방패 아이콘)을 선택합니다.

3. 빠른 **검사 를 선택합니다.** 또는 전체 검색을 실행하려면 검사 옵션 을 선택한 다음 전체 검사와 같은 **옵션을 선택합니다.**

## <a name="review-the-security-intelligence-update-version-and-download-the-latest-updates-in-the-windows-security-app"></a>보안 인텔리전스 업데이트 버전을 검토하고 Windows 보안 앱에서 최신 업데이트를 다운로드합니다.

![보안 인텔리전스 버전 번호 정보](images/defender/wdav-wdsc-defs.png)

1. 시작 메뉴에서 보안 을 검색한 다음 Windows 보안 을 선택하여 Windows 보안 **앱을 열 수 있습니다.**

2. 바이러스 & **보호** 타일(또는 왼쪽 메뉴 표시줄의 방패 아이콘)을 선택합니다.

3. 바이러스 **보호 & 업데이트를 선택합니다.** 현재 설치된 버전이 다운로드된 경우에 대한 몇 가지 정보와 함께 표시됩니다. 현재 버전을 수동으로 다운로드할 수 있는 최신 버전을 확인하거나 해당 버전에 대한 변경 로그를 검토할 수 있습니다. Microsoft Defender 바이러스 백신 및 기타 Microsoft 맬웨어 [방지에 대한 보안 인텔리전스 업데이트를 참조하세요.](https://www.microsoft.com/en-us/wdsi/defenderupdates)

4. 업데이트 **확인을 선택하여** 새 보호 업데이트를 다운로드합니다(있는 경우).

## <a name="ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app"></a>Windows 보안 앱에서 Microsoft Defender 바이러스 백신을 사용하도록 설정되어 있는지 확인

1. 시작 메뉴에서 보안 을 검색한 다음 Windows 보안 을 선택하여 Windows 보안 **앱을 열 수 있습니다.**

2. 바이러스 & **보호** 타일(또는 왼쪽 메뉴 표시줄의 방패 아이콘)을 선택합니다.

3. 바이러스 **보호 & 보호 설정을 선택합니다.**

4. 실시간 보호 **스위치를** 켜기 로 **전환합니다.**

    > [!NOTE]
    > 실시간 **보호를** 끄면 짧은 지연 후 자동으로 다시 켜집니다. 이는 맬웨어 및 위협으로부터 보호하기 위한 것입니다.
    > 다른 바이러스 백신 제품을 설치하는 경우 Microsoft Defender 바이러스 백신은 자동으로 자체를 사용하지 않도록 설정하며 Windows 보안 앱에 표시되어 있습니다. 제한된 주기적 검색을 사용하도록 설정할 수 있는 [설정이 나타납니다.](limited-periodic-scanning-microsoft-defender-antivirus.md)

## <a name="add-exclusions-for-microsoft-defender-antivirus-in-the-windows-security-app"></a>Windows 보안 앱에서 Microsoft Defender 바이러스 백신 제외 추가

1. 시작 메뉴에서 보안 을 검색한 다음 Windows 보안 을 선택하여 Windows 보안 **앱을 열 수 있습니다.**

2. 바이러스 & **보호** 타일(또는 왼쪽 메뉴 표시줄의 방패 아이콘)을 선택합니다.

3. 설정 **관리에서** 바이러스 및 **위협 방지 & 를 선택합니다.**

4. 제외 **설정에서** 제외 추가 **또는 제거를 선택합니다.** 

5. 더하기 아이콘( )을 선택하여 유형을 선택하고 각 제외에 대한 옵션을 **+** 설정할 수 있습니다. 

다음 표에서는 제외 유형과 발생하는 결과를 요약하여 제공합니다.

|제외 유형  |정의한 사용자  |진행 작업  |
|---------|---------|---------|
|**파일** |위치 <br/>예: `c:\sample\sample.test` |특정 파일은 Microsoft Defender 바이러스 백신에서 건너뜁니다. |
|**폴더**    |위치 <br/>예: `c:\test\sample`       |지정된 폴더의 모든 항목은 Microsoft Defender 바이러스 백신에서 건너뜁니다.         |
|**파일 형식**   |파일 확장명 <br/>예: `.test` |디바이스의 아무 곳에나 확장이 있는 모든 파일은 Microsoft Defender 바이러스 백신에서 `.test` 건너뜁니다.         |
|**프로세스**     |실행 파일 경로 <br>예: `c:\test\process.exe`         |특정 프로세스 및 해당 프로세스에서 연 파일은 Microsoft Defender 바이러스 백신에서 건너뜁니다.         |

자세한 내용은 다음 리소스를 참조하세요.
- [파일 확장명 및 폴더 위치에 따라 제외 구성 및 유효성 검사](./configure-extension-file-exclusions-microsoft-defender-antivirus.md) 
- [프로세스에서 연 파일에 대한 제외 구성](./configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="review-threat-detection-history-in-the-windows-defender-security-center-app"></a>보안 센터 앱의 Windows Defender 검색 기록 검토

1. 시작 메뉴에서 보안 을 검색한 다음 Windows 보안 을 선택하여 Windows 보안 **앱을 열 수 있습니다.**

2. 바이러스 & **보호** 타일(또는 왼쪽 메뉴 표시줄의 방패 아이콘)을 선택합니다.

3. 보호 **기록 을 선택합니다.** 모든 최근 항목이 나열됩니다.

## <a name="set-ransomware-protection-and-recovery-options"></a>랜섬웨어 보호 및 복구 옵션 설정

1. 시작 메뉴에서 보안 을 검색한 다음 Windows 보안 을 선택하여 Windows 보안 **앱을 열 수 있습니다.**

2. 바이러스 & **보호** 타일(또는 왼쪽 메뉴 표시줄의 방패 아이콘)을 선택합니다.

3. **랜섬웨어 보호에서** **랜섬웨어** 보호 관리를 선택합니다.

4. 제어된 폴더 **액세스 설정을 변경하려면** 제어된 폴더 액세스로 중요한 [폴더 보호를 참조하세요.](/microsoft-365/security/defender-endpoint/controlled-folders)

5. 랜섬웨어 복구 옵션을 설정하려면  **랜섬웨어** 데이터 복구에서 설정을 선택하고 랜섬웨어 공격으로부터 쉽게 복구할 수 있도록 OneDrive 계정을 연결하거나 설정하기 위한 지침을 따릅니다.

## <a name="see-also"></a>참고 항목
- [Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-in-windows-10.md)