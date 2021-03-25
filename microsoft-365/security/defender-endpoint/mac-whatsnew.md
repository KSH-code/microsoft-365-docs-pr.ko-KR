---
title: Mac용 끝점용 Microsoft Defender의 새로운
description: Mac용 끝점용 Microsoft Defender의 이전 버전에 대한 주요 변경 내용에 대해 자세히 알아보습니다.
keywords: microsoft, defender, atp, mac, installation, macos, whatsnew
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: be906baca3a54183e22fa3b4ee424a9d8fc6957a
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198696"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-for-mac"></a>Mac용 끝점용 Microsoft Defender의 새로운

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 끝점용 Microsoft Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!IMPORTANT]
> macOS 11(Big Sur)에서는 끝점용 Microsoft Defender에 추가 구성 프로필이 필요합니다. 이전 버전의 macOS에서 업그레이드하는 기존 고객인 경우 이 페이지에 나열된 추가 구성 프로필을 [배포해야 합니다.](mac-sysext-policies.md)

> [!IMPORTANT]
> MacOS 10.13(High Sierra)에 대한 지원은 2021년 2월 15일부터 중단됩니다.

## <a name="1012279-20121012122790"></a>101.22.79 (20.121012.12279.0)

- 버그 수정을 & 성능 개선

## <a name="1011988-20121011119880"></a>101.19.88 (20.121011.11988.0)

- 버그 수정을 & 성능 개선

## <a name="1011948-20120121119480"></a>101.19.48 (20.120121.11948.0)

> [!NOTE]
> 이 릴리스에서는 이전 명령줄 도구 구문이 사용되지 않습니다. 새 구문에 대한 자세한 내용은 Resources 을 [참조하십시오.](mac-resources.md#configuring-from-the-command-line)

- 네트워크 확장을 사용하지 않도록 설정하는 새 명령줄 스위치가 `mdatp system-extension network-filter disable` 추가되었습니다. . 이 명령은 Mac용 끝점용 Microsoft Defender와 관련이 있을 수 있는 네트워킹 문제를 해결하는 데 유용할 수 있습니다.
- 버그 수정을 & 성능 개선

## <a name="1011921-20120101119210"></a>101.19.21 (20.120101.11921.0)

- 버그 수정

## <a name="1011526-20120102115260"></a>101.15.26 (20.120102.11526.0)

- macOS 11 Big Sur에서 실행될 때 에이전트의 안정성 향상
- 사용자 지정 검사 중에 AV 제외를 무시하는 새 명령줄 스위치()가 `--ignore-exclusions` 추가되었습니다. `mdatp scan custom`
- 버그 수정을 & 성능 개선

## <a name="1011375-20120101113750"></a>101.13.75 (20.120101.11375.0)

- 끝점용 Microsoft Defender가 커널 창에 매니페스트되는 macOS 11(Big Sur) 버그를 트리거할 때 제거된 조건
- Mac 11(Big Sur)에서 실행되는 경우 Endpoint 보안 시스템 확장의 메모리 누수 수정
- 버그 수정

## <a name="1011072"></a>101.10.72

- 버그 수정

## <a name="1010961"></a>101.09.61

- 피드백을 보내기 위한 옵션을 사용할 수 있도록 설정하기 위한 새로운 관리 기본 [설정이 추가되었습니다.](mac-preferences.md#show--hide-option-to-send-feedback)
- 이제 상태 메뉴 아이콘은 제품 설정이 관리되는 경우 정상 상태를 보여 줍니다. 이전에는 관리자가 제품 설정을 관리했어도 상태 메뉴 아이콘에 경고 또는 오류 상태가 표시했습니다.
- 버그 수정을 & 성능 개선

## <a name="1010950"></a>101.09.50

- 이 제품 버전은 macOS Big Sur 11 베타 9에서 유효성이 검사되었습니다.

- 이제 명령줄 도구의 새 구문이 `mdatp` 기본 구문이 됩니다. 새 구문에 대한 자세한 내용은 [Mac용 끝점용 Microsoft Defender 리소스를 참조하세요.](mac-resources.md#configuring-from-the-command-line)

  > [!NOTE]
  > 이전 명령줄 도구 구문은 **2021년 1월 1일** 제품에서 제거됩니다.

- 진단 로그를 다른 디렉터리에 저장할 수 있도록 하는 새 매개 변수()로 `mdatp diagnostic create` `--path [directory]` 확장
- 버그 수정을 & 성능 개선

## <a name="1010949"></a>101.09.49

- IT 관리자가 관리하는 제외와 로컬 사용자가 정의한 제외를 차별화하기 위한 사용자 인터페이스 개선
- 필요한 검사 중 CPU 사용률 향상
- 버그 수정을 & 성능 개선

## <a name="1010723"></a>101.07.23

- 수동 모드 및 EDR 그룹 ID의 상태를 확인할 수 있는 새 필드가 출력에 `mdatp --health` 추가되었습니다.

  > [!NOTE]
  > `mdatp --health` 는 향후 제품 업데이트에서 `mdatp health` 대체될 예정입니다.

- 자동 샘플 제출이 사용자 인터페이스에서 관리되는 것으로 표시되지 않는 버그가 수정되었습니다.
- 바이러스 백신 검사 기록의 항목 보존을 제어하기 위한 새 설정이 추가되었습니다. 이제 검사 [기록에](mac-preferences.md#antivirus-scan-history-retention-in-days) 항목을 보존할 일 수를 지정하고 검사 기록의 최대 항목 수를 [지정할 수 있습니다.](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)
- 버그 수정

## <a name="1010663"></a>101.06.63

- 버전 에 도입된 성능 회귀 문제를 `101.05.17` 해결했습니다. 회귀는 일부 고객이 SMB 공유에 액세스할 때 관찰한 커널 패니크를 제거하기 위해 수정과 함께 도입되었습니다. 이 코드 변경을 되살리며 커널 패니를 제거하는 다른 방법을 조사하고 있습니다.

## <a name="1010517"></a>101.05.17

> [!IMPORTANT]
> 명령줄 도구에 대한 새 구문과 향상된 구문을 `mdatp` 사용 중입니다. 새 구문은 현재 Insider Fast 및 Insider Slow 업데이트 채널에서 기본값입니다. 이 새 구문을 사용하면 됩니다.
> 
> 계속해서 새 구문과 함께 이전 구문을 지원할 예정으로, 앞으로 몇 개월 후의 이전 구문에 대한 사용 안 하게 될 계획에 대해 좀 더 많은 통신을 제공할 것입니다.

- SMB 파일 공유에 액세스할 때 가끔 발생하는 커널 패니크 해결
- 버그 수정을 & 성능 개선

## <a name="1010516"></a>101.05.16

- 검색된 파일 수를 크게 줄일 수 있는 빠른 검사 논리 개선
- 명령줄 [도구에](mac-resources.md#how-to-enable-autocompletion) 대한 자동 보완 지원이 추가되었습니다.
- 버그 수정

## <a name="1010312"></a>101.03.12

- 버그 수정을 & 성능 개선

## <a name="1010154"></a>101.01.54

- 시간 컴퓨터와의 호환성 개선
- 향상된 접근성
- 버그 수정을 & 성능 개선

## <a name="1010031"></a>101.00.31

- [Intune 사용자에 대한](https://docs.microsoft.com/mem/intune/apps/apps-advanced-threat-protection-macos) 향상된 제품 온보더링 환경
- 바이러스 [백신 제외에서 와일드카드 지원](mac-exclusions.md#supported-exclusion-types)
- macOS 상황에 맞는 메뉴에서 바이러스 백신 검색을 트리거하는 기능을 추가했습니다. 이제 Finder에서 파일 또는 폴더를 마우스 오른쪽 단추로 클릭하고 **끝점용 Microsoft Defender로 스캔을** 선택할 수 있습니다.
- 현재 있는 제품 다운그레이드가 설치 관리자에 의해 명시적으로 허용되지 않습니다. 다운그레이드해야 하는 경우 먼저 기존 버전을 제거하고 장치를 다시 구성합니다.
- 버그 수정에 & 성능 향상

## <a name="1009027"></a>100.90.27

- 이제 시스템 [전체 업데이트](mac-updates.md#set-the-channel-name) 채널과 다른 Mac용 끝점용 Microsoft Defender에 대한 업데이트 채널을 설정할 수 있습니다.
- 새 제품 아이콘
- 기타 사용자 환경 개선
- 버그 수정

## <a name="1008692"></a>100.86.92

- 시간 컴퓨터와의 호환성 개선
- 제품이 제거 중에 일부 파일을 정리하지 않는 문제를 `/Library/Application Support/Microsoft/Defender` 해결했습니다.
- Microsoft 자동 업데이트를 통해 Microsoft 제품이 업데이트될 때 제품의 CPU 사용률 감소
- 버그 수정에 & 성능 향상

## <a name="1008691"></a>100.86.91

> [!CAUTION]
> To ensure the most complete protection for your macOS devices and in alignment with Apple stopping delivery of macOS native security updates to OS versions older than [current – 2], MDATP for Mac deployment and updates will no longer be supported on macOS Sierra [10.12]. Mac용 MDATP 업데이트 및 향상된 기능은 카탈로나[10.15], Mojave [10.14] 및 High Sierra [10.13]을 실행하는 장치에 제공됩니다. 
>
> If you already have MDATP for Mac deployed to your Sierra [10.12] devices, please upgrade to the latest macOS version to eliminate risks of losing protection.

- 버그 수정을 & 성능 개선

## <a name="1008373"></a>100.83.73

- 제외 [관리,](mac-preferences.md#exclusion-merge-policy)위협 유형 설정 관리 및 금지된 [](mac-preferences.md#threat-type-settings-merge-policy)위협 작업과 같은 IT 관리자를 위한 더 많은 제어가 [추가되었습니다.](mac-preferences.md#disallowed-threat-actions)
- 장치에서 전체 디스크 액세스를 사용하도록 설정하지 않은 경우 상태 메뉴에 경고가 표시됩니다.
- 버그 수정을 & 성능 개선

## <a name="1008260"></a>100.82.60

- 정의 업데이트 후 제품이 시작되지 못하는 문제를 해결했습니다.

## <a name="1008042"></a>100.80.42

- 버그 수정

## <a name="1007942"></a>100.79.42

- Mac용 끝점용 Microsoft Defender가 때때로 시간 컴퓨터로 떨어졌다는 문제를 해결했습니다.
- 백end 서비스와의 연결을 테스트하기 위한 명령줄 유틸리티에 새 스위치가 추가되었습니다.
  ```bash
  mdatp connectivity test
  ```
- 사용자 인터페이스에서 전체 위협 기록을 볼 수 있는 기능 추가(보호 기록 보기에서 액세스할 **수** 있습니다.
- 버그 수정을 & 성능 개선

## <a name="1007215"></a>100.72.15

- 버그 수정

## <a name="1007099"></a>100.70.99

- 실시간 보호를 사용하는 경우 일부 사용자가 macOS 카탈로나로 업그레이드하는 능력에 영향을 미치는 문제를 해결했습니다. 이 소문자 문제는 카탈로나 업그레이드 패키지 내의 끝점 잠금 파일을 검사하는 동안 카탈로나 업그레이드 패키지 내의 끝점 잠금 파일에서 발생하여 업그레이드 순서에 오류가 발생했습니다.

## <a name="1006899"></a>100.68.99

- 수동 모드에서 실행하도록 바이러스 백신 기능을 구성하는 [기능이 추가되었습니다.](mac-preferences.md#enable--disable-passive-mode)
- 버그 수정을 & 성능 개선

## <a name="1006528"></a>100.65.28

- MacOS 카탈로니아에 대한 지원이 추가되었습니다.

  > [!CAUTION]
  > macOS 10.15(카탈로니아)에는 새로운 보안 및 개인 정보 보호 향상 기능이 포함되어 있습니다. 이 버전부터 응용 프로그램은 기본적으로 명시적 동의 없이 디스크의 특정 위치(예: 문서, 다운로드, 데스크톱 등)에 액세스할 수 없습니다. 이 동의가 없는 경우 끝점용 Microsoft Defender는 장치를 완전히 보호할 수 없습니다.
  >
  > 이 동의를 부여하는 메커니즘은 끝점용 Microsoft Defender를 배포한 방법에 따라 달라 습니다.
  >
  > - 수동 배포에 대한 자세한 내용은 수동 배포 항목의 [업데이트된 지침을 참조하세요.](mac-install-manually.md#how-to-allow-full-disk-access)
  > - 관리되는 배포에 대한 자세한 내용은 [JAMF 기반](mac-install-with-jamf.md) 배포 및 [Microsoft Intune](mac-install-with-intune.md#create-system-configuration-profiles) 기반 배포 항목의 업데이트된 지침을 참조하세요.

- 버그 수정을 & 성능 개선
