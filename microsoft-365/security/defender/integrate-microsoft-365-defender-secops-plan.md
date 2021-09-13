---
title: 1단계. Microsoft 365 Defender 작업 준비 계획
description: 보안 운영에 Microsoft 365 Defender 통합할 때 Microsoft 365 Defender 준비를 계획하는 기본 개념입니다.
keywords: 인시던트, 경고, 조사, 상관 관계, 공격, 장치, 사용자, ID, ID, 사서함, 전자 메일, 365, microsoft, m365, 인시던트 대응, 사이버 공격, 보안 작업, soc
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 3e8bf320bd25dacb3312605d5bc6428ad15210fb
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59192462"
---
# <a name="step-1-plan-for-microsoft-365-defender-operations-readiness"></a>1단계. Microsoft 365 Defender 작업 준비 계획

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**적용 대상:**
- Microsoft 365 Defender

보안 작업의 현재 성숙도에 따라서는 SOC(보안 운영 센터)에 맞춰야 합니다. 모든 조직에 적합한 단일 모델은 없는 반면, 다른 조직에 비해 더 일반적인 특정 측면이 있습니다. 

다음 섹션에서는 SOC의 핵심 기능에 대해 설명합니다.

## <a name="provide-situational-awareness-of-modern-threats"></a>최신 위협에 대한 상황 인식 제공

SOC 팀은 조직과 함께 대책 및 대응을 수립할 수 있도록 새로운 위협과 들어오는 위협을 준비하고 헌팅합니다. SOC 팀에는 최신 공격 방법 및 기술에 대해 고도로 교육을 들이고 위협 공격자에 대한 이해를 높이는 담당자가 있습니다. 사이버 킬체인 또는 [](https://www.microsoft.com/security/blog/2016/11/28/disrupting-the-kill-chain/) [MITRE ATT](https://attack.mitre.org/)&CK 프레임워크와 같은 공유 위협 인텔리전스 및 프레임워크는 위협 분석가와 위협 헌터의 역량을 강화할 수 있습니다.

## <a name="provide-first-second-and-potentially-third-level-responses-to-cyber-incidents-and-events"></a>사이버 인시던트 및 이벤트에 대한 첫 번째, 두 번째 및 잠재적으로 세 번째 수준의 대응 제공

SOC는 보안 이벤트 및 인시던트에 대한 방어의 최전선입니다. 이벤트, 위협, 공격, 정책 위반 또는 감사 찾기가 경고 또는 조치 호출을 트리거하는 경우 SOC 팀은 평가를 수행하여 심사를 수행하고 이를 포함하거나 조사를 위해 에스컬레이터합니다. 따라서 SOC 첫 번째 라인 응답자는 보안 이벤트 및 지표에 대한 광범위한 기술 지식을 쌓아야 합니다.

## <a name="centralize-monitoring-and-logging-of-your-organizations-security-sources"></a>조직의 보안 원본 모니터링 및 로깅 중앙 집중화 

일반적으로 SOC 팀의 핵심 기능은 방화벽, 침입 방지 시스템, 데이터 손실 방지 시스템, 위협 및 취약성 관리 시스템 및 ID 시스템과 같은 모든 보안 장치가 올바르게 작동하고 모니터링되고 있는지 확인하는 것입니다. SOC 팀은 ID, DevOps, 클라우드, 응용 프로그램, 데이터 과학 및 기타 비즈니스 팀과 같은 광범위한 네트워크 운영과 함께 작업하여 보안 정보의 분석이 중앙 집중화 및 보안되도록 합니다. 또한 SOC 팀은 데이터의 로그를 사용 가능하고 읽을 수 있는 형식으로 유지 관리합니다. 여기에는 구문 분석 및 정규화가 포함됩니다.

## <a name="establish-red-blue-and-purple-team-operational-readiness"></a>빨간색, 파랑 및 자주색 팀 운영 준비 설정

모든 SOC 팀은 사이버 인시던트에 대응할 준비를 테스트해야 합니다. 테스트는 IT, 보안 및 비즈니스 수준에서 다양한 개인과 함께 실행되는 표 위와 같은 교육 연습을 통해 수행될 수 있습니다. 개별 교육 연습 팀은 대표적인 역할을 기반으로 만들어지며, 방어자(파란색 팀), 공격자(Red Team) 또는 연습(자주색 팀)에서 발견된 장단점을 통해 파란색 팀과 Red 팀의 방법 및 기술을 개선하기 위한 관찰자 역할을 합니다.

## <a name="next-step"></a>다음 단계

[2단계. Zero Trust Framework를 사용하여 SOC 통합 준비 평가 수행](integrate-microsoft-365-defender-secops-readiness.md)



