---
title: macOS에서 끝점용 Microsoft Defender의 성능 문제 해결
description: MacOS의 끝점용 Microsoft Defender에서 성능 문제를 해결합니다.
keywords: Microsoft, defender, Endpoint용 Microsoft Defender, mac, 성능
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 26a8761b8df141626cf7fcffaeb18e2a32bae69a
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60206962"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-on-macos"></a>macOS에서 끝점용 Microsoft Defender의 성능 문제 해결

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**

- [Microsoft Defender for Endpoint(macOS용)](microsoft-defender-endpoint-mac.md)
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

이 항목에서는 macOS의 끝점용 Microsoft Defender와 관련된 성능 문제를 좁히는 데 사용할 수 있는 몇 가지 일반적인 단계를 제공합니다.

RTP(실시간 보호)는 지속적으로 위협으로부터 장치를 모니터링하고 보호하는 MacOS용 끝점용 Microsoft Defender의 기능입니다. 이 구성은 파일 및 프로세스 모니터링 및 기타추론으로 구성됩니다.

실행 중인 응용 프로그램 및 장치 특성에 따라 macOS에서 끝점용 Microsoft Defender를 실행하면 성능이 하될 수 있습니다. 특히 짧은 시간 동안 많은 리소스에 액세스하는 응용 프로그램 또는 시스템 프로세스는 macOS의 끝점용 Microsoft Defender에서 성능 문제가 발생할 수 있습니다.

다음 단계를 사용하여 이러한 문제를 해결하고 완화할 수 있습니다.

1. 다음 방법 중 하나를 사용하여 실시간 보호를 사용하지 않도록 설정하고 성능이 향상될지 여부를 관찰합니다. 이 방법은 macOS의 끝점용 Microsoft Defender가 성능 문제에 기여하는지 여부를 좁히는 데 도움이 됩니다.

      조직에서 장치를 관리하지 않는 경우 다음 옵션 중 하나를 사용하여 실시간 보호를 사용하지 않도록 설정할 수 있습니다.

    - 사용자 인터페이스에서 macOS에서 끝점용 Microsoft Defender를 열고 설정 **관리로 이동합니다.**

      ![실시간 보호 스크린샷을 관리합니다.](images/mdatp-36-rtp.png)

    - 터미널에서 보안을 위해 이 작업을 수행하려면 권한 상승이 필요합니다.

      ```bash
      mdatp config real-time-protection --value disabled
      ```

      조직에서 장치를 관리하는 경우 관리자가 [macOS의 끝점에 대한 Microsoft Defender](mac-preferences.md)기본 설정의 지침을 사용하여 실시간 보호를 사용하지 않도록 설정할 수 있습니다.

      실시간 보호가 해제된 동안 성능 문제가 지속되면 문제의 원점은 끝점 검색 및 응답 구성 요소일 수 있습니다. 이 경우 고객 지원에 문의하여 추가 지침 및 완화를 요청하세요.

2. 찾기를 열고 응용 **프로그램** \> **유틸리티로 이동합니다.** 작업 **모니터를** 열고 시스템에서 리소스를 사용하는 응용 프로그램을 분석합니다. 일반적인 예로는 소프트웨어 업데이트 프로그램 및 컴파일러가 있습니다.

3. 가장 많은 검색을 트리거하는 응용 프로그램을 찾으기 위해 Mac의 Endpoint용 Defender에서 수집한 실시간 통계를 사용할 수 있습니다.

      > [!NOTE]
      > 이 기능은 버전 100.90.70 이상에서 사용할 수 있습니다.
      이 기능은 **Dogfood** 및 **InsiderFast** 채널에서 기본적으로 사용됩니다. 다른 업데이트 채널을 사용하는 경우 명령줄에서 이 기능을 사용하도록 설정하면 됩니다.

      ```bash
      mdatp config real-time-protection-statistics  --value enabled
      ```

      이 기능을 사용하려면 실시간 보호를 사용하도록 설정해야 합니다. 실시간 보호 상태를 확인하기 위해 다음 명령을 실행합니다.

      ```bash
      mdatp health --field real_time_protection_enabled
      ```

    real_time_protection_enabled **항목이** true인지 확인해야 합니다. 그렇지 않으면 다음 명령을 실행하여 사용하도록 설정하십시오.

      ```bash
      mdatp config real-time-protection --value enabled
      ```

      ```output
      Configuration property updated
      ```

      현재 통계를 수집하기 위해 다음을 실행합니다.

      ```bash
      mdatp diagnostic real-time-protection-statistics --output json > real_time_protection.json
      ```

      > [!NOTE]
      > **--output json(이중** 파선 참고)을 사용하면 출력 형식을 구문 분석할 수 있습니다.
      이 명령의 출력에는 모든 프로세스 및 관련 검사 활동이 표시됩니다.

4. Mac 시스템에서 다음 명령을 사용하여 샘플 Python 파서 high_cpu_parser.py를 다운로드합니다.

    ```bash
    curl -O https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/linux/diagnostic/high_cpu_parser.py
    ```

    이 명령의 출력은 다음과 유사해야 합니다.

    ```Output
    --2020-11-14 11:27:27-- https://raw.githubusercontent.com/microsoft.
    mdatp-xplat/master/linus/diagnostic/high_cpu_parser.py
    Resolving raw.githubusercontent.com (raw.githubusercontent.com)... 151.101.xxx.xxx
    Connecting to raw.githubusercontent.com (raw.githubusercontent.com)| 151.101.xxx.xxx| :443... connected.
    HTTP request sent, awaiting response... 200 OK
    Length: 1020 [text/plain]
    Saving to: 'high_cpu_parser.py'
    100%[===========================================>] 1,020    --.-K/s   in
    0s
    ```

5. 다음으로 다음 명령을 입력합니다.

      ```bash
        chmod +x high_cpu_parser.py
      ```

      ```bash
        cat real_time_protection.json | python high_cpu_parser.py  > real_time_protection.log
      ```

      위의 출력은 성능 문제에 대한 가장 많은 기여자 목록입니다. 첫 번째 열은 PID(프로세스 식별자)이고, 두 번째 열은 te 프로세스 이름이고, 마지막 열은 검사된 파일 수로, 영향별로 정렬됩니다.

      예를 들어 명령의 출력은 다음과 같습니다.

      ```output
        ... > python ~/repo/mdatp-xplat/linux/diagnostic/high_cpu_parser.py <~Downloads/output.json | head -n 10
        27432 None 76703
        73467 actool     1249
        73914 xcodebuild 1081
        73873 bash 1050
        27475 None 836
        1    launchd    407
        73468 ibtool     344
        549  telemetryd_v1   325
        4764 None 228
        125  CrashPlanService 164
      ```

      Mac에서 끝점용 Defender의 성능을 향상하려면 검색된 총 파일 행에서 가장 높은 수의 끝점을 찾고 제외를 추가합니다. 자세한 내용은 [Linux에서 끝점용 Defender에](linux-exclusions.md)대한 제외 구성 및 유효성 검사를 참조하세요.

      > [!NOTE]
      > 응용 프로그램은 통계를 메모리에 저장하고 시작된 후 실시간 보호를 사용하도록 설정한 이후에만 파일 활동을 추적합니다. 실시간 보호가 해제된 이전 또는 기간 동안 시작된 프로세스는 계산되지 않습니다. 또한 검사가 트리거된 이벤트만 계산됩니다.
      >
6. 성능 문제에 기여하는 프로세스 또는 디스크 위치에 대한 제외를 사용하여 macOS의 끝점에 대한 Microsoft Defender를 구성하고 실시간 보호를 다시 사용하도록 설정하세요.

     자세한 [내용은 MacOS의 끝점에 대한 Microsoft Defender 제외](mac-exclusions.md) 구성 및 유효성 검사를 참조합니다.
