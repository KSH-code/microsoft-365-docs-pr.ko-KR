---
title: Linux에서 끝점용 Microsoft Defender의 성능 문제 해결
description: Linux의 끝점용 Microsoft Defender에서 성능 문제를 해결합니다.
keywords: Microsoft, defender, Endpoint용 Microsoft Defender, linux, 성능
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
mms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 935826d3a89abeef20e1ebb17f964137fdbfccaf
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59220531"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-on-linux"></a>Linux에서 끝점용 Microsoft Defender의 성능 문제 해결

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

이 문서에서는 Linux의 끝점용 Defender와 관련된 성능 문제를 좁히는 데 사용할 수 있는 몇 가지 일반적인 단계를 제공합니다.

RTP(실시간 보호)는 지속적으로 위협으로부터 장치를 모니터링하고 보호하는 Linux의 Endpoint용 Defender 기능입니다. 이 구성은 파일 및 프로세스 모니터링 및 기타추론으로 구성됩니다.

실행 중인 응용 프로그램 및 장치 특성에 따라 Linux에서 Endpoint용 Defender를 실행하면 성능이 멀어질 수 있습니다. 특히 짧은 시간 동안 많은 리소스에 액세스하는 응용 프로그램 또는 시스템 프로세스는 Linux의 Endpoint용 Defender에서 성능 문제를 발생할 수 있습니다.

시작하기 전에 다른 보안 제품이 장치에서 현재 실행되고 **있지 않은지 확인합니다.** 여러 보안 제품이 충돌하여 호스트 성능에 영향을 줄 수 있습니다.

다음 단계를 사용하여 이러한 문제를 해결하고 완화할 수 있습니다.

1. 다음 방법 중 하나를 사용하여 실시간 보호를 사용하지 않도록 설정하고 성능이 향상될지 여부를 관찰합니다. 이 방법은 Linux의 Endpoint용 Defender가 성능 문제에 기여하는지 여부를 좁히는 데 도움이 됩니다.

    조직에서 디바이스를 관리하지 않는 경우 명령줄에서 실시간 보호를 사용하지 않도록 설정할 수 있습니다.

    ```bash
    mdatp config real-time-protection --value disabled
    ```

    ```Output
    Configuration property updated
    ```

    조직에서 디바이스를 관리하는 경우 관리자가 [Linux에서 끝점에](linux-preferences.md)대한 Defender 기본 설정의 지침에 따라 실시간 보호를 사용하지 않도록 설정할 수 있습니다.

    실시간 보호가 해제된 동안 성능 문제가 지속되면 문제의 원점은 끝점 검색 및 응답 구성 요소일 수 있습니다. 이 경우 고객 지원에 문의하여 추가 지침 및 완화를 요청하세요.

2. 가장 많은 검색을 트리거하는 응용 프로그램을 찾기 위해 Linux의 Endpoint용 Defender에서 수집한 실시간 통계를 사용할 수 있습니다.

    > [!NOTE]
    > 이 기능은 버전 100.90.70 이상에서 사용할 수 있습니다.

    이 기능은 및 채널에서 기본적으로 `Dogfood` `InsiderFast` 사용하도록 설정됩니다. 다른 업데이트 채널을 사용하는 경우 명령줄에서 이 기능을 사용하도록 설정하면 됩니다.

    ```bash
    mdatp config real-time-protection-statistics --value enabled
    ```

    이 기능을 사용하려면 실시간 보호를 사용하도록 설정해야 합니다. 실시간 보호 상태를 확인하기 위해 다음 명령을 실행합니다.

    ```bash
    mdatp health --field real_time_protection_enabled
    ```

    항목이 `real_time_protection_enabled` `true` 입니다. 그렇지 않으면 다음 명령을 실행하여 사용하도록 설정하십시오.

    ```bash
    mdatp config real-time-protection --value enabled
    ```

    ```Output
    Configuration property updated
    ```

    현재 통계를 수집하기 위해 다음을 실행합니다.

    ```bash
    mdatp diagnostic real-time-protection-statistics --output json > real_time_protection.json
    ```

    > [!NOTE]
    > 이중 대시를 사용하면 출력 형식을 구문 분석할 ```--output json``` 준비가 됩니다.

    이 명령의 출력에는 모든 프로세스 및 관련 검사 활동이 표시됩니다.

3. Linux 시스템에서 다음 명령을 사용하여 샘플 Python **high_cpu_parser.py를** 다운로드합니다.

    ```bash
    wget -c https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/linux/diagnostic/high_cpu_parser.py
    ```

    이 명령의 출력은 다음과 유사해야 합니다.

    ```Output
    --2020-11-14 11:27:27-- https://raw.githubusercontent.com/microsoft.mdatp-xplat/master/linus/diagnostic/high_cpu_parser.py
    Resolving raw.githubusercontent.com (raw.githubusercontent.com)... 151.101.xxx.xxx
    Connecting to raw.githubusercontent.com (raw.githubusercontent.com)| 151.101.xxx.xxx| :443... connected.
    HTTP request sent, awaiting response... 200 OK
    Length: 1020 [text/plain]
    Saving to: 'high_cpu_parser.py'

    100%[===========================================>] 1,020    --.-K/s   in 0s
    ```

4. 다음으로 다음 명령을 입력합니다.

    ```bash
    chmod +x high_cpu_parser.py
    ```

    ```bash
    cat real_time_protection.json | python high_cpu_parser.py  > real_time_protection.log
    ```

      위의 출력은 성능 문제에 대한 가장 많은 기여자 목록입니다. 첫 번째 열은 PID(프로세스 식별자)이고, 두 번째 열은 프로세스 이름이고, 마지막 열은 검사된 파일 수로, 영향을 따라 정렬됩니다.
    예를 들어 명령의 출력은 다음과 같습니다. 

    ```Output
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

    Linux에서 끝점용 Defender의 성능을 개선하기 위해 행 아래에 있는 가장 높은 숫자의 끝점을 찾고 해당 끝점에 대한 제외를 `Total files scanned` 추가합니다. 자세한 내용은 [Linux에서 끝점용 Defender에](linux-exclusions.md)대한 제외 구성 및 유효성 검사를 참조하세요.

    > [!NOTE]
    > 응용 프로그램은 통계를 메모리에 저장하고 시작된 후 실시간 보호를 사용하도록 설정한 이후에만 파일 활동을 추적합니다. 실시간 보호가 해제된 이전 또는 기간 동안 시작된 프로세스는 계산되지 않습니다. 또한 검사가 트리거된 이벤트만 계산됩니다.

5. 성능 문제에 기여하는 프로세스 또는 디스크 위치에 대한 제외를 사용하여 Linux의 끝점에 대한 Microsoft Defender를 구성하고 실시간 보호를 다시 활성화합니다.

    자세한 내용은 [Linux의 엔드포인트용 Microsoft Defender에 대한 제외 구성 및 유효성 검사](linux-exclusions.md)를 참조하세요.

## <a name="see-also"></a>참고 항목

- [에이전트 상태 문제 조사](health-status.md)
