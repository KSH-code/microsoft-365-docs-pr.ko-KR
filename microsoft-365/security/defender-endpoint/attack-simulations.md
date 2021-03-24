---
title: 시뮬레이션된 공격을 통해 Microsoft Defender ATP 경험
description: 제공된 공격 시나리오 시뮬레이션을 실행하여 Microsoft Defender ATP가 위반을 감지, 조사 및 대응하는 방법을 경험합니다.
keywords: wdatp, 테스트, 시나리오, 공격, 시뮬레이션, 시뮬레이션, diy, 끝점용 Microsoft Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 11/20/2018
ms.technology: mde
ms.openlocfilehash: 25538e1866db8f4a7bff24ac336005bf2e1ce78b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073052"
---
# <a name="experience-microsoft-defender-for-endpoint-through-simulated-attacks"></a>시뮬레이트된 공격을 통해 끝점에 대한 Microsoft Defender 경험 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Endpoint용 Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-attacksimulations-abovefoldlink)

>[!TIP]
>- Microsoft Defender ATP의 최신 향상된 기능: [끝점용 Defender의 새로운 기능에 대해 자세히 알아보세요.](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/)
>- Endpoint용 Defender는 최근 MITRE 평가에서 업계를 선도하는 광학 및 감지 기능을 보여 주었다. 읽기: [MITRE ATT의 인사이트&CK 기반 평가.](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)

서비스에 여러 장치를 온보딩하기 전에 Endpoint용 Defender를 경험할 수 있습니다. 이를 위해 몇 가지 테스트 장치에서 제어된 공격 시뮬레이션을 실행할 수 있습니다. 시뮬레이션된 공격을 실행한 후 Endpoint용 Defender가 악의적인 활동을 어떻게 표면화하는지 검토하고 이를 통해 효율적인 대응을 가능하게 하는 방법을 탐색할 수 있습니다.

## <a name="before-you-begin"></a>시작하기 전에

제공된 시뮬레이션을 실행하려면 하나 이상의 온보드 [디바이스가 필요합니다.](onboard-configure.md) 

각 공격 시나리오와 함께 제공되는 walkthrough 문서를 읽어 읽습니다. 각 문서에는 OS 및 응용 프로그램 요구 사항과 공격 시나리오와 관련한 자세한 지침이 포함되어 있습니다.

## <a name="run-a-simulation"></a>시뮬레이션 실행

1. 도움말 **시뮬레이션**& 자습서 에서 시뮬레이션할 사용 가능한 공격 시나리오를  >  선택합니다.

   - **시나리오 1: 문서 드롭 백도어** - 사회적으로 엔지니어링된 Lure 문서의 배달을 시뮬레이트합니다. 이 문서는 공격자가 제어할 수 있는 특수하게 만들어진 백도어를 실행합니다.

   - **시나리오 2: 파일** 없는 공격의 PowerShell 스크립트 - PowerShell을 사용하여 공격 표면 감소 및 악의적인 메모리 활동의 장치 학습 감지를 표시하는 파일 없는 공격을 시뮬레이션합니다.
    
   - **시나리오 3: 자동화된** 인시던트 대응 - 인시던트 대응 용량을 확장하기 위해 위반 아티팩트를 자동으로 헌팅하고 수정하는 자동화된 조사를 트리거합니다.

2. 선택한 시나리오와 함께 제공된 해당 Walkthrough 문서를 다운로드하고 읽습니다.

3. 시뮬레이션 파일을 다운로드하거나 자습서 에서 도움말   >  **시뮬레이션으로 & 복사합니다.** 테스트 장치에서 파일 또는 스크립트를 다운로드할 수 있지만 필수는 아닙니다.

4. 테스트 장치에서 시뮬레이션 파일 또는 스크립트를 실행합니다. 이 문서의 지시에 따라 실행합니다.

> [!NOTE]
> 시뮬레이션 파일 또는 스크립트는 공격 활동을 모방하지만 실제로는 양호하며 테스트 장치를 손상하거나 손상하지 않습니다.
> 
> 
> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-attacksimulations-belowfoldlink)


## <a name="related-topics"></a>관련 항목

- [장치 온보드](onboard-configure.md)
- [Windows 10 장치 온보드](configure-endpoints.md)
