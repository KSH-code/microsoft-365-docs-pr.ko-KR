---
title: Microsoft Defender 바이러스 백신 앱의 Windows 보안
description: 이제 Microsoft Defender 바이러스 백신 앱에 Windows 보안 일반적인 작업을 검토, 비교 및 수행할 수 있습니다.
keywords: wdav, 바이러스 백신, 방화벽, 보안, windows
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection: M365-security-compliance
ms.openlocfilehash: 23e89bd4aee02299e0710ff65fbe496fd8535b8f
ms.sourcegitcommit: 6968594dc8cf8b30a4c958df6d65dfd0cd2cfae1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2021
ms.locfileid: "59490120"
---
# <a name="microsoft-defender-antivirus-in-the-windows-security-app"></a>Microsoft Defender 바이러스 백신 앱의 Windows 보안

**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

Windows 10 버전 1703 이상에서 Windows Defender 앱은 Windows 보안.

설정 클라이언트 및 Windows Defender 주 Windows 설정 통합되어 기본적으로 Windows 10 버전 1703의 일부로 설치되는 새 앱으로 이동되었습니다.

> [!IMPORTANT]
> Windows 보안 센터 서비스를 사용하지 않도록 설정하면 방화벽이 Microsoft Defender 바이러스 백신 Windows Defender [않습니다.](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) 타사 바이러스 백신 또는 방화벽 제품을 설치하고 최신 상태로 유지하면 이러한 기능이 자동으로 사용하지 않도록 설정됩니다.
>
> Windows 보안 Center 서비스를 사용하지 않도록 설정하거나 연결된 그룹 정책 설정을 구성하여 시작하거나 실행하지 못하도록 하는 경우 Windows 보안 앱은 장치에 설치한 바이러스 백신 또는 방화벽 제품에 대한 부실하거나 부정확한 정보를 표시할 수 있습니다.
> 또한 이전 또는 Microsoft Defender 바이러스 백신 바이러스 백신이 있는 경우 또는 이전에 설치한 타사 바이러스 백신 제품을 제거한 경우 해당 제품을 사용하지 못하게 할 수도 있습니다.
> 이렇게 하면 장치의 보호가 현저히 낮아지며 맬웨어 감염으로 이어질 수 있습니다.

앱에서 [모니터링할 Windows 보안](/windows/threat-protection/windows-defender-security-center/windows-defender-security-center) 다른 보안 기능에 대한 자세한 내용은 Windows 문서를 참조하세요.

Windows 보안 앱은 Windows 10 버전 1703 이상의 클라이언트 인터페이스입니다. 이 웹 Microsoft Defender 보안 센터 끝점용 Microsoft Defender를 검토하고 관리하는 [데 사용되는 웹 포털이 아니며,](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)

## <a name="review-virus-and-threat-protection-settings-in-the-windows-security-app"></a>앱의 바이러스 및 위협 방지 Windows 보안 검토

:::image type="content" source="../../media/wdav-protection-settings-wdsc.png" alt-text="앱의 바이러스 및 위협 방지 Windows 보안.":::

1. 작업 표시줄에서 방패 아이콘을 클릭하거나 **Defender의** 시작 메뉴를 검색하여 Windows 보안 앱을 열 수 있습니다.

2. 바이러스 & **보호** 타일(또는 왼쪽 메뉴 표시줄의 방패 아이콘)을 선택합니다.

다음 섹션에서는 Microsoft Defender 바이러스 백신 앱에서 제공하는 위협 방지를 검토하거나 상호 작용할 때 가장 일반적인 몇 가지 작업을 Windows 보안 설명합니다.

> [!NOTE]
> 그룹 정책을 사용하여 이러한 설정을 구성하고 배포하는 경우 이 섹션에 설명된 설정은 회색으로 표시됩니다. 개별 끝점에서 사용할 수 없습니다. 설정이 Windows 설정에서 업데이트되기 전에 먼저 그룹 정책 개체를 통해 수행한 변경을 개별 엔드포인트에 배포해야 합니다. Configure [end-user interaction with Microsoft Defender 바이러스 백신](configure-end-user-interaction-microsoft-defender-antivirus.md) 항목에서는 로컬 정책 Microsoft Defender 바이러스 백신 구성할 수 있는 방법에 대해 설명합니다.

## <a name="run-a-scan-with-the-windows-security-app"></a>앱과 함께 Windows 보안 실행

1. 시작 메뉴에서 보안 Windows 보안 를 검색한 다음 을 선택하여 앱 앱을 **Windows 보안.**

2. 바이러스 & **보호** 타일(또는 왼쪽 메뉴 표시줄의 방패 아이콘)을 선택합니다.

3. 빠른 **검사 를 선택합니다.** 또는 전체 검색을 실행하려면 검사 옵션 을 선택한 다음 전체 검사와 같은 **옵션을 선택합니다.**

## <a name="review-the-security-intelligence-update-version-and-download-the-latest-updates-in-the-windows-security-app"></a>보안 인텔리전스 업데이트 버전을 검토하고 Windows 보안 업데이트 다운로드

:::image type="content" source="../../media/wdav-wdsc-defs.png" alt-text="보안 인텔리전스 버전 번호입니다.":::

1. 시작 메뉴에서 보안 Windows 보안 를 검색한 다음 을 선택하여 앱 앱을 **Windows 보안.**

2. 바이러스 & **보호** 타일(또는 왼쪽 메뉴 표시줄의 방패 아이콘)을 선택합니다.

3. 바이러스 **보호 & 업데이트를 선택합니다.** 현재 설치된 버전이 다운로드된 경우에 대한 몇 가지 정보와 함께 표시됩니다. 현재 버전을 수동으로 다운로드할 수 있는 최신 버전을 확인하거나 해당 버전에 대한 변경 로그를 검토할 수 있습니다. 보안 [인텔리전스 업데이트 및 Microsoft Defender 바이러스 백신 Microsoft 맬웨어 방지 업데이트를 참조하세요.](https://www.microsoft.com/wdsi/defenderupdates)

4. 업데이트 **확인을 선택하여** 새 보호 업데이트를 다운로드합니다(있는 경우).

## <a name="ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app"></a>앱 Microsoft Defender 바이러스 백신 사용하도록 설정되어 Windows 보안 확인

1. 시작 메뉴에서 보안 Windows 보안 를 검색한 다음 을 선택하여 앱 앱을 **Windows 보안.**

2. 바이러스 & **보호** 타일(또는 왼쪽 메뉴 표시줄의 방패 아이콘)을 선택합니다.

3. 바이러스 **보호 & 보호 설정을 선택합니다.**

4. 실시간 보호 **스위치를** 켜기 로 **전환합니다.**

    > [!NOTE]
    > 실시간 **보호를** 끄면 짧은 지연 후 자동으로 다시 켜집니다. 이는 맬웨어 및 위협으로부터 보호하기 위한 것입니다.
    > 다른 바이러스 백신 제품을 설치하는 경우 Microsoft Defender 바이러스 백신 자동으로 사용하지 않도록 설정되며 Windows 보안 앱에 표시되어 있습니다. 제한된 주기적 검색을 사용하도록 설정할 수 있는 [설정이 나타납니다.](limited-periodic-scanning-microsoft-defender-antivirus.md)

## <a name="add-exclusions-for-microsoft-defender-antivirus-in-the-windows-security-app"></a>앱의 Microsoft Defender 바이러스 백신 제외 Windows 보안 추가

1. 시작 메뉴에서 보안 Windows 보안 를 검색한 다음 을 선택하여 앱 앱을 **Windows 보안.**

2. 바이러스 & **보호** 타일(또는 왼쪽 메뉴 표시줄의 방패 아이콘)을 선택합니다.

3. 설정 **관리에서** 바이러스 및 **위협 방지 & 를 선택합니다.**

4. 제외 **설정에서** 제외 추가 **또는 제거를 선택합니다.**

5. 더하기 아이콘( )을 선택하여 유형을 선택하고 각 제외에 대한 옵션을 **+** 설정할 수 있습니다.

다음 표에서는 제외 유형과 발생하는 결과를 요약하여 제공합니다.

<br>

****
|제외 유형|정의한 사용자|발생 작업|
|---|---|---|
|**파일**|위치 <br/>예: `c:\sample\sample.test`|특정 파일은 특정 파일에서 건너 Microsoft Defender 바이러스 백신.|
|**폴더**|위치 <br/>예: `c:\test\sample`|지정한 폴더의 모든 항목은 폴더에서 건너 Microsoft Defender 바이러스 백신.|
|**파일 형식**|파일 확장명 <br/>예: `.test`|디바이스의 아무 곳에서나 확장명을 사용하여 모든 파일을 `.test` Microsoft Defender 바이러스 백신.|
|**프로세스**|실행 파일 경로 <br>예: `c:\test\process.exe`|특정 프로세스 및 해당 프로세스에서 연 모든 파일은 특정 프로세스에서 Microsoft Defender 바이러스 백신.|
|

자세한 내용은 다음 리소스를 참조하세요.

- [파일 확장명 및 폴더 위치에 따라 제외 구성 및 유효성 검사](./configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [프로세스에서 연 파일에 대한 제외 구성](./configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="review-threat-detection-history-in-the-windows-defender-security-center-app"></a>보안 센터 앱의 Windows Defender 검색 기록 검토

1. 시작 메뉴에서 보안 Windows 보안 를 검색한 다음 을 선택하여 앱 앱을 **Windows 보안.**

2. 바이러스 & **보호** 타일(또는 왼쪽 메뉴 표시줄의 방패 아이콘)을 선택합니다.

3. 보호 **기록 을 선택합니다.** 모든 최근 항목이 나열됩니다.

## <a name="set-ransomware-protection-and-recovery-options"></a>랜섬웨어 보호 및 복구 옵션 설정

1. 시작 메뉴에서 보안 Windows 보안 를 검색한 다음 을 선택하여 앱 앱을 **Windows 보안.**

2. 바이러스 & **보호** 타일(또는 왼쪽 메뉴 표시줄의 방패 아이콘)을 선택합니다.

3. **랜섬웨어 보호에서** **랜섬웨어** 보호 관리를 선택합니다.

4. 제어된 폴더 **액세스 설정을 변경하려면** 제어된 폴더 액세스로 중요한 [폴더 보호를 참조하세요.](/microsoft-365/security/defender-endpoint/controlled-folders)

5. 랜섬웨어 복구 옵션을 설정하려면  **랜섬웨어** 데이터 복구에서 설정을 선택하고 랜섬웨어 공격으로부터 쉽게 복구할 수 있도록 OneDrive 계정을 연결하거나 설정하기 위한 지침을 따릅니다.

## <a name="see-also"></a>참고 항목

- [Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-in-windows-10.md)
