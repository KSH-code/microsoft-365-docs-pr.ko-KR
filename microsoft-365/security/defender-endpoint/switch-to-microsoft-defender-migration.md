---
title: Microsoft가 아닌 엔드포인트 보호에서 끝점용 Microsoft Defender로 전환
description: 끝점 보호 솔루션에 대한 Microsoft Defender 바이러스 백신 Microsoft Defender for Endpoint로 전환합니다.
keywords: 마이그레이션, windows defender, 고급 끝점 보호, 바이러스 백신, 맬웨어 방지, 수동 모드, 활성 모드
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-migratetomdatp
- m365solution-overview
- m365solution-mcafeemigrate
- m365solution-symantecmigrate
ms.topic: conceptual
ms.custom: migrationguides
ms.date: 09/23/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.technology: mde
ms.openlocfilehash: e7b6777970102b71f61fcaed7a8a13daf8d73fa7
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60205202"
---
# <a name="make-the-switch-from-non-microsoft-endpoint-protection-to-microsoft-defender-for-endpoint"></a>Microsoft가 아닌 엔드포인트 보호에서 끝점용 Microsoft Defender로 전환

Microsoft가 아닌 끝점 보호 솔루션에서 [끝점용 Microsoft Defender(Defender for Endpoint)로](microsoft-defender-endpoint.md) 전환하는 방안을 고민하고 있는 경우 올바른 장소에 있습니다. 이 문서를 가이드로 사용하세요.

:::image type="content" source="images/nonms-mde-migration.png" alt-text="끝점 보호 솔루션을 Endpoint용 Defender로 전환합니다.":::

Endpoint용 Defender로 전환할 때 활성 모드에서 Microsoft가 아닌 바이러스 백신/맬웨어 방지 보호 기능으로 전환합니다. 그런 다음 수동 Microsoft Defender 바이러스 백신 구성하고 끝점용 Defender에 장치를 온보딩합니다. 그런 다음 끝점 보호 기능을 구성하고, Microsoft Defender 바이러스 백신 모드로 설정하고, 모든 기능이 제대로 작동하고 있는지 확인합니다. 마지막으로 Microsoft가 아닌 솔루션을 제거합니다.

## <a name="the-migration-process"></a>마이그레이션 프로세스

다음 표에 설명된 바와 같이 끝점용 Defender로 마이그레이션하는 프로세스는 세 단계로 나눌 수 있습니다.

![MDE 마이그레이션 프로세스.](images/phase-diagrams/migration-phases.png)

<br/><br/>

|단계|설명|
|--|--|
|[마이그레이션 준비](switch-to-microsoft-defender-prepare.md)|[준비 **단계 중:**](switch-to-microsoft-defender-prepare.md) <br/>1. 조직의 장치를 업데이트합니다.<br/>2. 끝점용 Defender를 얻습니다.<br/>3. 역할 및 사용 권한을 계획하고 앱 포털에 대한 Microsoft 365 Defender 부여합니다.<br/>4. 조직의 장치와 Endpoint용 Defender 간의 통신을 사용하도록 장치 프록시 및 인터넷 설정을 구성합니다. |
|[끝점에 대한 Defender 설정](switch-to-microsoft-defender-setup.md)|설치 [ **단계 중:**](switch-to-microsoft-defender-setup.md) <br/>1. 사용/다시 설치 Microsoft Defender 바이러스 백신 수동 모드로 설정<br/>2. 끝점에 대한 Defender를 구성합니다.<br/>3. 기존 솔루션의 제외 목록에 끝점용 Defender를 추가합니다.<br/>4. 기존 솔루션을 기존 솔루션의 제외 목록에 Microsoft Defender 바이러스 백신.<br/>5. 장치 그룹, 컬렉션 및 조직 구성 단위를 설치합니다.<br/>6. 맬웨어 방지 정책 및 실시간 보호 설정을 구성합니다.|
|[끝점용 Defender에 온보딩](switch-to-microsoft-defender-onboard.md)|[ **온보더 단계 중:**](switch-to-microsoft-defender-onboard.md) <br/>1. 끝점용 Defender에 장치를 온보딩합니다.<br/>2. 검색 테스트를 실행합니다.<br/>3. 수동 Microsoft Defender 바이러스 백신 실행 중인지 확인<br/>4. 설치에 대한 업데이트를 Microsoft Defender 바이러스 백신.<br/>5. 기존 끝점 보호 솔루션을 제거합니다.<br/>6. 끝점에 대한 Defender가 제대로 작동하고 있는지 확인합니다.|

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a>끝점용 Microsoft Defender에는 무엇이 포함되어 있나요?

이 마이그레이션 가이드에서는 엔드포인트용 Defender로 이동하기 위한 시작점으로 차세대 보호 및 끝점 감지 및 응답 기능에 중점을 두고 있습니다. [](microsoft-defender-antivirus-in-windows-10.md) [](overview-endpoint-detection-response.md) 그러나 Endpoint용 Defender에는 바이러스 백신 및 끝점 보호보다 훨씬 더 많은 보호가 포함되어 있습니다. Endpoint용 Defender는 예방적 보호, 위반 후 감지, 자동화된 조사 및 대응을 위한 통합 플랫폼입니다. 다음 표에는 끝점용 Defender의 기능이 요약되어 있습니다.

<br/><br/>

|기능/기능|설명|
|---|---|
|[위협 및 취약성 관리](next-gen-threat-and-vuln-mgt.md)|위협 & 취약성 관리 기능은 끝점(예: 장치)에서 약점을 식별, 평가 및 수정하는 데 도움이 됩니다.|
|[공격 표면 감소](overview-attack-surface-reduction.md)|공격 표면 감소 규칙은 사이버 위협 및 공격으로부터 조직의 장치 및 응용 프로그램을 보호하는 데 도움이 됩니다.|
|[차세대 보호](microsoft-defender-antivirus-in-windows-10.md)|차세대 보호에는 위협 Microsoft Defender 바이러스 백신 맬웨어를 차단하는 데 도움이 되는 여러 가지 기능도 포함되어 있습니다.|
|[엔드포인트 검색 및 대응](overview-endpoint-detection-response.md)|끝점 감지 및 응답 기능은 침입 시도 및 활성 위반을 감지, 조사 및 대응합니다.|
|[지능형 헌팅](advanced-hunting-overview.md)|고급 헌팅 기능을 통해 보안 운영 팀은 알려진 위협 또는 잠재적인 위협의 지표와 엔터티를 찾을 수 있습니다.|
|[동작 차단 및 제약](behavioral-blocking-containment.md)|동작 차단 및 포함 기능은 위협이 실행을 시작한 경우에도 동작 및 처리 트리를 기반으로 위협을 식별하고 중지하는 데 도움이 됩니다.|
|[자동 조사 및 수정](automated-investigations.md)|자동화된 조사 및 대응 기능은 경고를 검사하고 위반을 해결하기 위해 즉시 수정 조치를 취합니다.|
|[위협 헌팅](microsoft-threat-experts.md) 서비스(Microsoft 위협 전문가)|위협 헌팅 서비스는 보안 운영 팀에 전문가 수준의 모니터링 및 분석을 제공하고 중요한 위협이 누락되지 않도록 합니다.|

**자세한 내용을 원하세요? [끝점에 대한 Defender를 참조합니다.](microsoft-defender-endpoint.md)**

## <a name="next-step"></a>다음 단계

- 마이그레이션 [준비로 진행합니다.](switch-to-microsoft-defender-prepare.md)
