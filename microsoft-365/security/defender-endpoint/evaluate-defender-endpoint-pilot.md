---
title: 시뮬레이트된 공격을 통해 끝점에 대한 Microsoft Defender(MDE) 경험
description: 테스트 Microsoft 365 Defender 테스트 또는 파일럿 환경을 파일럿합니다.
keywords: Microsoft 365 Defender 평가, Microsoft 365 Defender 평가, Microsoft 365 Defender 평가Microsoft 365 Defender 평가 랩, Microsoft 365 Defender, 사이버 보안, 고급 영구 위협, 엔터프라이즈 보안, 장치, ID, 사용자, 데이터, 응용 프로그램, 인시던트, 자동화된 조사 및 수정, 고급 헌팅
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-jweston
author: jweston-1
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 93e5b0cb5a152868749a68d34ac476660b41cc92
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60152409"
---
# <a name="experience-microsoft-defender-for-endpoint-mde-through-simulated-attacks"></a>시뮬레이트된 공격을 통해 끝점에 대한 Microsoft Defender(MDE) 경험

> [!TIP]
>
> - 끝점용 Microsoft Defender의 최신 향상된 기능: [엔드포인트용 Defender의](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/)새로운 기능.
> - Endpoint용 Defender는 최근 MITRE 평가에서 업계를 선도하는 광학 및 감지 기능을 보여 주었다. 읽기: [MITRE ATT&CK 기반 평가의 인사이트](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).

서비스에 여러 장치를 온보딩하기 전에 Endpoint용 Defender를 경험할 수 있습니다. 이를 위해 몇 가지 테스트 장치에서 제어된 공격 시뮬레이션을 실행할 수 있습니다. 시뮬레이션된 공격을 실행한 후 Endpoint용 Defender가 악의적인 활동을 어떻게 표면화하는지 검토하고 이를 통해 효율적인 대응을 가능하게 하는 방법을 탐색할 수 있습니다.

## <a name="before-you-begin"></a>시작하기 전에

제공된 시뮬레이션을 실행하려면 하나 이상의 온보드 [디바이스가 필요합니다.](onboard-configure.md)

각 공격 시나리오와 함께 제공되는 walkthrough 문서를 읽어 읽습니다. 각 문서에는 OS 및 응용 프로그램 요구 사항과 공격 시나리오와 관련한 자세한 지침이 포함되어 있습니다.

## <a name="run-a-simulation"></a>시뮬레이션 실행

1. 도움말 **시뮬레이션** & 자습서 에서 시뮬레이션할 사용 가능한 공격 시나리오를 \> 선택합니다.

   - **시나리오 1: 문서 드롭 백도어** - 사회적으로 엔지니어링된 Lure 문서의 배달을 시뮬레이트합니다. 이 문서는 공격자가 제어할 수 있는 특수하게 만들어진 백도어를 실행합니다.

   - **시나리오 2: 파일** 없는 공격의 PowerShell 스크립트 - PowerShell을 사용하여 공격 표면 감소 및 악의적인 메모리 활동의 장치 학습 감지를 표시하는 파일 없는 공격을 시뮬레이션합니다.

   - **시나리오 3: 자동화된** 인시던트 대응 - 인시던트 대응 용량을 확장하기 위해 위반 아티팩트를 자동으로 헌팅하고 수정하는 자동화된 조사를 트리거합니다.

2. 선택한 시나리오와 함께 제공된 해당 Walkthrough 문서를 다운로드하고 읽습니다.

3. 시뮬레이션 파일을 다운로드하거나 자습서 에서 도움말  \> **시뮬레이션으로 & 복사합니다.** 테스트 장치에서 파일 또는 스크립트를 다운로드할 수 있지만 필수는 아닙니다.

4. 테스트 장치에서 시뮬레이션 파일 또는 스크립트를 실행합니다. 이 문서의 지시에 따라 실행합니다.

> [!NOTE]
> 시뮬레이션 파일 또는 스크립트는 공격 활동을 모방하지만 실제로는 양호하며 테스트 장치를 손상하거나 손상하지 않습니다.

## <a name="alternate-topic-text"></a>대체 항목 텍스트

## <a name="simulate-attack-scenarios"></a>공격 시나리오 시뮬레이트

테스트 장치를 사용하여 연결하여 자체 공격 시뮬레이션을 실행합니다.

다음을 사용하여 공격 시나리오를 시뮬레이트할 수 있습니다.

- ["직접" 공격 시나리오](https://securitycenter.windows.com/tutorials)
- 위협 시뮬레이터

고급 [헌팅을](advanced-hunting-overview.md) 사용하여 데이터 및 [위협](threat-analytics.md) 분석을 쿼리하여 새로운 위협에 대한 보고서를 볼 수 있습니다.

### <a name="do-it-yourself-attack-scenarios"></a>직접 공격 시나리오

미리 만든 시뮬레이션을 찾고 있는 경우 ["직접 실행"](https://securitycenter.windows.com/tutorials)공격 시나리오를 사용할 수 있습니다. 이러한 스크립트는 안전하고 문서화되어 있으며 사용하기 쉽습니다. 이러한 시나리오는 끝점 기능에 대한 Defender를 반영하고 조사 환경을 진행합니다.

> [!NOTE]
> 테스트 장치에 대한 연결은 RDP를 사용하여 수행됩니다. 방화벽 설정에서 RDP 연결을 허용하는지 확인합니다.

1. 커넥트 를 선택하여 장치에 연결하고 를 선택하여 **공격 시뮬레이션을 커넥트.**

    ![테스트 장치에 대한 연결 단추의 이미지입니다.](images/test-machine-table.png)

2. RDP 파일을 저장하고 를 선택하여 **커넥트.**

    ![원격 데스크톱 연결의 이미지입니다.](images/remote-connection.png)

    > [!NOTE]
    > 초기 설정 중에 암호 복사본을 저장하지 않은 경우 메뉴에서 암호 다시 설정을 선택하여 암호를 **다시** 설정할 수 있습니다.
    >
    > ![암호 재설정 이미지입니다.](images/reset-password-test-machine.png)
    >
    > 디바이스의 상태가 "암호 재설정 실행"으로 변경되면 몇 분 후에 새 암호가 표시됩니다.

3. 디바이스를 만들 때 표시된 암호를 입력합니다.

   ![자격 증명을 입력할 창의 이미지입니다.](images/enter-password.png)

4. 장치에서 Do-it-yourself 공격 시뮬레이션을 실행합니다.

### <a name="threat-simulator-scenarios"></a>위협 시뮬레이터 시나리오

랩 설정 중에 지원되는 위협 시뮬레이터를 설치하도록 선택한 경우 평가 랩 디바이스에서 기본 제공 시뮬레이션을 실행할 수 있습니다.

타사 플랫폼을 사용하여 위협 시뮬레이션을 실행하는 것은 테스트 환경의 범위 내에서 끝점 기능에 대한 Microsoft Defender를 평가하는 좋은 방법입니다.

> [!NOTE]
> 시뮬레이션을 실행하기 전에 다음 요구 사항을 충족하는지 확인합니다.
>
> - 디바이스를 평가 랩에 추가해야 합니다.
> - 위협 시뮬레이터를 평가 랩에 설치해야 합니다.

1. 포털에서 시뮬레이션 **만들기를 선택합니다.**

2. 위협 시뮬레이터를 선택합니다.

    ![위협 시뮬레이터 선택 이미지입니다.](images/select-simulator.png)

3. 시뮬레이션을 선택하거나 시뮬레이션 갤러리를 살펴보고 사용 가능한 시뮬레이션을 탐색합니다.

   시뮬레이션 갤러리는 다음에서 얻을 수 있습니다.

   - 시뮬레이션 개요 타일의 주 평가 **대시보드 또는**
   - 탐색 창 평가 및 자습서  시뮬레이션을 탐색하여 \> **자습서를 &** 시뮬레이션 **카탈로그를 선택합니다.**

4. 시뮬레이션을 실행할 디바이스를 선택합니다.

5. 시뮬레이션 **만들기를 선택합니다.**

6. 시뮬레이션 탭을 선택하여 시뮬레이션 **진행률을 니다.** 시뮬레이션 상태, 활성 경고 및 기타 세부 정보를 볼 수 있습니다.

    ![시뮬레이션 탭의 이미지입니다.](images/simulations-tab.png)

시뮬레이션을 실행한 후 랩 진행률 표시줄을 살펴보고 자동화된 조사 및 수정을 트리거한 **Endpoint용 Microsoft Defender를** 살펴보는 것이 좋습니다. 기능에서 수집 및 분석한 증거를 확인해 보아야 합니다.

풍부한 쿼리 언어 및 원시 원격 분석을 사용하여 고급 헌팅을 통해 공격 증거를 헌팅하고 위협 분석에 문서화되어 있는 전 세계 위협을 확인해보십시오.
