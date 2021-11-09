---
title: 피드백-루프 차단
description: 신속한 보호라고도 하는 피드백 루프 차단은 끝점용 Microsoft Defender의 동작 차단 및 포함 기능의 일부입니다.
keywords: 동작 차단, 신속한 보호, 피드백 차단, 끝점용 Microsoft Defender
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
ms.localizationpriority: medium
ms.custom:
- next-gen
- edr
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: 30e1fdb8baede9506af52ae844f456baed1097a9
ms.sourcegitcommit: e09ced3e3628bf2ccb84d205d9699483cbb4b3b0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2021
ms.locfileid: "60882684"
---
# <a name="feedback-loop-blocking"></a>피드백-루프 차단

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)

## <a name="overview"></a>개요

피드백 루프 차단은 신속한 보호라고도 하는 Microsoft [](/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) [Defender for Endpoint의](/windows/security/threat-protection/)동작 차단 및 포함 기능의 구성 요소입니다. 피드백 루프 차단을 통해 조직 전체의 장치를 공격으로부터 더 잘 보호할 수 있습니다. 

## <a name="how-feedback-loop-blocking-works"></a>피드백 루프 차단의 작동 방식

에 의해 의심스러운 동작이나 파일이 Microsoft Defender 바이러스 백신 [경우](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)해당 아티팩트에 대한 정보가 여러 분류자에게 전송됩니다. 신속한 보호 루프 엔진은 파일을 차단할지 여부에 대한 결정을 내리기 위해 정보를 다른 신호와 검사하고 관련합니다. 아티팩트 확인 및 분류는 빠르게 진행됩니다. 확인된 맬웨어를 신속히 차단하고 전체 에코시스템을 보호합니다. 

신속한 보호를 통해 공격의 발판을 넓히기 위한 공격으로 장치, 조직의 다른 장치 및 다른 조직의 디바이스에서 공격을 중지할 수 있습니다.


## <a name="configuring-feedback-loop-blocking"></a>피드백 루프 차단 구성

조직에서 끝점에 Defender를 사용하는 경우 피드백 루프 차단은 기본적으로 사용하도록 설정됩니다. 그러나 신속한 보호는 끝점 기능에 대한 Defender 기능, 기계 학습 보호 기능 및 Microsoft 보안 서비스 전반의 신호 공유를 통해 발생합니다. 끝점용 Defender의 다음 기능을 사용하도록 설정하고 구성해야 합니다.

- [끝점 기준에 대한 Microsoft Defender](/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)

- [끝점용 Microsoft Defender에 온보딩된 장치](/microsoft-365/security/defender-endpoint/onboard-configure)

- [차단 모드의 EDR](/microsoft-365/security/defender-endpoint/edr-in-block-mode)

- [공격 표면 감소](/microsoft-365/security/defender-endpoint/attack-surface-reduction)

- [차세대 보호(바이러스](/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) 백신)

## <a name="related-articles"></a>관련 문서

- [동작 차단 및 제약](behavioral-blocking-containment.md)

- [(블로그) 동작 차단 및 포함: 광학을 보호로 변환](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection/)

- [엔드포인트 리소스에 대한 유용한 Microsoft Defender](/microsoft-365/security/defender-endpoint/helpful-resources)
