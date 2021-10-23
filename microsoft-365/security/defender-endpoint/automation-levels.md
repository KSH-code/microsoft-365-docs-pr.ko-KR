---
title: 자동화된 조사 및 수정의 자동화 수준
description: 자동화 수준 및 이러한 수준이 끝점용 Microsoft Defender에서 어떻게 작동 하는지 간략하게 설명
keywords: 자동화, 조사, 수준, 끝점용 Microsoft Defender
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: JoeDavies-MSFT
ms.author: josephd
ms.date: 10/22/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.custom: AIR
ms.openlocfilehash: 01b57b0ad376758363e3ce515c53f503d7c409ae
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2021
ms.locfileid: "60555431"
---
# <a name="automation-levels-in-automated-investigation-and-remediation-capabilities"></a>자동 조사 및 수정 기능의 자동화 수준

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

끝점용 Microsoft Defender의 자동화된 조사 및 수정(AIR) 기능은 여러 수준의 자동화 중 하나에 구성할 수 있습니다. 자동화 수준은 AIR 조사 후 수정 작업이 자동으로 수행될지 승인 시에만 수행될지 여부에 영향을 미치게 됩니다.

- *전체* 자동화(권장)는 악의적인 것으로 판단되는 아티팩트에 대해 수정 작업이 자동으로 수행되는 것을 의미합니다.
- *반자동화는* 일부 수정 작업이 자동으로 수행되는 것을 의미하지만 다른 수정 작업은 수행되기 전에 승인을 기다립니다. (자동화 수준에 [있는 표를 참조합니다.)](#levels-of-automation)
- 보류 중인지 완료 여부에 따라 모든 수정 작업은 관리 센터( )에서 [https://securitycenter.windows.com](https://securitycenter.windows.com) 추적됩니다.

> [!TIP]
> 최상의 결과를 얻기 위해 AIR을 구성할 때 전체 [자동화를 사용하는 것이 좋습니다.](configure-automated-investigations-remediation.md) 지난 해에 수집 및 분석된 데이터는 전체 자동화를 사용하는 고객이 낮은 수준의 자동화를 사용하는 고객보다 40% 더 높은 신뢰도의 맬웨어 샘플을 제거한 것으로 나타났습니다. 전체 자동화는 보안 운영 리소스를 확보하여 전략적 이니셔티브에 더 많은 집중하는 데 도움이 될 수 있습니다.

## <a name="levels-of-automation"></a>자동화 수준

다음 표에서는 각 자동화 수준과 자동화의 작동 방식에 대해 설명하고 있습니다.

<br>

****

|자동화 수준|설명|
|---|---|
|**전체 - 자동으로 위협 수정** <br> (전체 *자동화라고도 지칭)*|전체 자동화를 통해 수정 작업이 자동으로 수행됩니다. 수행된 모든 수정 작업은 기록 탭의 관리 [센터에서](auto-investigation-action-center.md) 볼 **수** 있습니다. 필요한 경우 재구성 작업을 실행하지 않습니다. <p> **_전체 자동화는 권장되고,_* 아직 장치 그룹이 정의되지 않은 Microsoft Defender for Endpoint를 사용하여 2020년 8월 16일 이후에 만들어진 테넌트에 대해 기본적으로 선택됩니다.*|
|**Semi - 모든 수정에 대한 승인 필요** <br> *(반자동화라고도 합니다.)*|이 수준의 반자동화에서는 수정 작업을 *수행하려면* 승인이 필요합니다. 이러한 보류 중인 작업은 보류 중인 [](auto-investigation-action-center.md)탭의 작업 센터 에서 보고 승인할 **수** 있습니다. <p> *이 반자 자동화 수준은 장치 그룹이 정의되지 않은 Microsoft Defender for Endpoint를 사용하여 2020년 8월 16일 전에 만들어진 테넌트에 대해 기본적으로 선택됩니다.*|
|**Semi - 핵심 폴더 수정에 대한 승인 필요** <br> *(반자동화의 일종)*|이 수준의 반자동화에서는 핵심 폴더에 있는 파일 또는 실행 파일에 필요한 수정 작업에 대해 승인이 필요합니다. 핵심 폴더에는 Windows( ) 등의 운영 체제 **Windows** `\windows\*` 있습니다. <p> 핵심 폴더가 아닌 다른 폴더에 있는 파일 또는 실행 파일에 대해 수정 작업을 자동으로 수행할 수 있습니다. <p> 핵심 폴더의 파일 또는 실행 파일에 대한 보류 중인 작업은 [](auto-investigation-action-center.md)보류 중인 탭의 작업 센터에서 보고 승인할 **수** 있습니다. <p> 다른 폴더의 파일 또는 실행 파일에 대해 수행된 작업은 [](auto-investigation-action-center.md)사용 기록 탭의 작업 센터 에서 볼 **수** 있습니다.|
|**Semi - 비 임시 폴더 수정에 대한 승인 필요** <br> *(반자동화의 일종)*|이 수준의 반자동화에서는 임시 폴더가 아닌 파일 또는 실행 파일에 필요한  수정 작업에 대해 승인이 필요합니다. <p> 임시 폴더에는 다음 예가 포함됩니다. <ul><li>`\users\*\appdata\local\temp\*`</li><li>`\documents and settings\*\local settings\temp\*`</li><li>`\documents and settings\*\local settings\temporary\*`</li><li>`\windows\temp\*`</li><li>`\users\*\downloads\*`</li><li>`\program files\`</li><li>`\program files (x86)\*`</li><li>`\documents and settings\*\users\*`</li></ul> <p> 임시 폴더에 있는 파일 또는 실행 파일에 대해 수정 작업을 자동으로 수행할 수 있습니다. <p> 임시 폴더에 없는 파일 또는 실행 파일에 대한 보류 중인 작업은 보류 중인 탭의 작업 센터에서 보고 승인할 **수** 있습니다. [](auto-investigation-action-center.md) <p> 임시 폴더의 파일 또는 실행 파일에 대해 수행된 작업은 사용 기록 [](auto-investigation-action-center.md)탭의 작업 센터 에서 보고 승인할 **수** 있습니다.|
|**자동 응답 없음** <br> (자동화 *없음)라고도 합니다.*|자동화가 없는 경우 조직의 장치에서 자동화된 조사가 실행되지 않습니다. 따라서 자동화된 조사의 결과로 수정 작업이 수행되거나 보류되지 않습니다. 그러나 바이러스 백신 및 차세대 [](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)보호 기능이 구성된 방식에 따라 잠재적으로 원치 않는 응용 프로그램의 보호와 같은 다른 위협 방지 기능이 적용될 수 있습니다. <p> ***자동화 *없음 옵션을*** 사용하면 조직의 디바이스의 보안 설정이 줄어들기 때문에 사용하지 않는 것이 좋습니다. [자동화 수준을 전체 자동화(또는](/microsoft-365/security/defender-endpoint/machine-groups)적어도 반 자동화)로 설정할 수 있습니다.|
|

## <a name="important-points-about-automation-levels"></a>자동화 수준에 대한 중요 지점

- 전체 자동화는 신뢰할 수 있고 효율적이며 안전하며 모든 고객에게 권장됩니다. 전체 자동화를 통해 중요한 보안 리소스를 확보하여 전략적 이니셔티브에 더 집중할 수 있습니다.

- Microsoft Defender for Endpoint를 통해 새 테넌트(2020년 8월 16일 이후에 만들어진 테넌트 포함)는 기본적으로 전체 자동화로 설정됩니다.

- 보안 팀에서 자동화 수준으로 장치 그룹을 정의한 경우 이러한 설정은 롤아웃되는 새로운 기본 설정에 의해 변경되지 않습니다.

- 기본 자동화 설정을 유지하거나 조직의 요구에 따라 변경할 수 있습니다. 설정을 변경하려면 [자동화 수준을 설정하세요.](/microsoft-365/security/defender-endpoint/configure-automated-investigations-remediation#set-up-device-groups)

## <a name="next-steps"></a>다음 단계

- [끝점용 Microsoft Defender에서 자동화된 조사 및 수정 기능 구성](configure-automated-investigations-remediation.md)
- [Action Center 방문](/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center)
