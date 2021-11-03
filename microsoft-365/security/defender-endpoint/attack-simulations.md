---
title: 시뮬레이트된 공격을 통해 끝점에 대한 Microsoft Defender 경험
description: 제공된 공격 시나리오 시뮬레이션을 실행하여 Microsoft Defender for Endpoint가 위반을 감지, 조사 및 대응하는 방법을 경험합니다.
keywords: test, scenario, attack, simulation, simulationd, diy, Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 11/20/2018
ms.technology: mde
ms.openlocfilehash: 04219d19136d54830b00cdc10bfd694e78cdd7b1
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60667377"
---
# <a name="experience-microsoft-defender-for-endpoint-through-simulated-attacks"></a>시뮬레이트된 공격을 통해 끝점에 대한 Microsoft Defender 경험 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-attacksimulations-abovefoldlink)

> [!TIP]
>
> - 끝점용 Microsoft Defender의 최신 향상된 기능: [엔드포인트용 Defender의](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/)새로운 기능.
> - Endpoint용 Defender는 최근 MITRE 평가에서 업계를 선도하는 광학 및 감지 기능을 보여 주었다. 읽기: [MITRE ATT&CK 기반 평가의 인사이트](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).

서비스에 여러 장치를 온보딩하기 전에 Endpoint용 Defender를 경험할 수 있습니다. 이를 위해 몇 가지 테스트 장치에서 제어된 공격 시뮬레이션을 실행할 수 있습니다. 시뮬레이션된 공격을 실행한 후 Endpoint용 Defender가 악의적인 활동을 어떻게 표면화하는지 검토하고 이를 통해 효율적인 대응을 가능하게 하는 방법을 탐색할 수 있습니다.

## <a name="before-you-begin"></a>시작하기 전에

제공된 시뮬레이션을 실행하려면 하나 이상의 온보드 [디바이스가 필요합니다.](onboard-configure.md)

각 공격 시나리오와 함께 제공되는 walkthrough 문서를 읽어 읽습니다. 각 문서에는 OS 및 응용 프로그램 요구 사항과 공격 시나리오와 관련한 자세한 지침이 포함되어 있습니다.

## <a name="run-a-simulation"></a>시뮬레이션 실행

1. **Endpoints** Evaluation & 자습서 자습서 & 시뮬레이션 에서 시뮬레이션할 사용 가능한 공격 시나리오를 \>  \> 선택합니다.
   - **시나리오 1: 문서 드롭 백도어** - 사회적으로 엔지니어링된 Lure 문서의 배달을 시뮬레이트합니다. 이 문서는 공격자가 제어할 수 있는 특수하게 만들어진 백도어를 실행합니다.
   - **시나리오 2: 파일** 없는 공격의 PowerShell 스크립트 - PowerShell을 사용하여 공격 표면 감소 및 악의적인 메모리 활동의 장치 학습 감지를 표시하는 파일 없는 공격을 시뮬레이션합니다.
   - **시나리오 3: 자동화된** 인시던트 대응 - 인시던트 대응 용량을 확장하기 위해 위반 아티팩트를 자동으로 헌팅하고 수정하는 자동화된 조사를 트리거합니다.

2. 선택한 시나리오와 함께 제공된 해당 Walkthrough 문서를 다운로드하고 읽습니다.

3. 시뮬레이션 파일을 다운로드하거나 **Evaluation** & 자습서를 통해 시뮬레이션 스크립트를 \> **& 복사합니다.** 테스트 장치에서 파일 또는 스크립트를 다운로드할 수 있지만 필수는 아닙니다.

4. 테스트 장치에서 시뮬레이션 파일 또는 스크립트를 실행합니다. 이 문서의 지시에 따라 실행합니다.

> [!NOTE]
> 시뮬레이션 파일 또는 스크립트는 공격 활동을 모방하지만 실제로는 양호하며 테스트 장치를 손상하거나 손상하지 않습니다.
>
> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-attacksimulations-belowfoldlink)

## <a name="related-topics"></a>관련 항목

- [온보딩 장치](onboard-configure.md)
- [그룹 정책을 통한 Windows 장치 온보딩](configure-endpoints.md)
