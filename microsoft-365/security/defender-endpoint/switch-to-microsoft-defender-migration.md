---
title: Microsoft가 아닌 다른 끝점 솔루션에서 끝점용 Microsoft Defender로 전환
description: 끝점용 Microsoft Defender로 전환합니다. 개요는 이 문서를 읽어 읽습니다.
keywords: migration, windows defender advanced endpoint protection, for Endpoint, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-migratetomdatp
- m365solution-overview
ms.topic: conceptual
ms.custom: migrationguides
ms.date: 05/14/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.technology: mde
ms.openlocfilehash: 013205a1b5b9db204f626a6fe6ab76ad07378558
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538006"
---
# <a name="make-the-switch-from-a-non-microsoft-endpoint-solution-to-microsoft-defender-for-endpoint"></a>Microsoft가 아닌 다른 끝점 솔루션에서 끝점용 Microsoft Defender로 전환

Microsoft가 아닌 끝점 보호 솔루션에서 [끝점용 Microsoft Defender(Endpoint용 Defender)로](microsoft-defender-endpoint.md) 전환할 계획이면 올바른 장소에 있습니다. 이 문서를 가이드로 사용하세요.

:::image type="content" source="images/nonms-mde-migration.png" alt-text="끝점용 Defender로의 마이그레이션 개요":::

Endpoint용 Defender로 전환할 때 활성 모드에서 Microsoft가 아닌 솔루션으로 시작하고, 수동 모드에서 끝점에 대한 Defender를 구성하고, 끝점용 Defender에 온보딩한 다음 끝점용 Defender를 활성 모드로 설정하고 Microsoft가 아닌 솔루션을 제거합니다.

> [!TIP]
> - 현재 McAfee 끝점 보안(McAfee)을 사용 중인 경우 [Migrate from McAfee to Defender for Endpoint를 참조합니다.](mcafee-to-microsoft-defender-migration.md)
> - 현재 Symantec Endpoint Protection(Symantec)를 사용하는 경우 [Migrate from Symantec to Defender for Endpoint를 참조합니다.](symantec-to-microsoft-defender-endpoint-migration.md)

## <a name="the-migration-process"></a>마이그레이션 프로세스

Endpoint용 Defender로 전환할 때 다음 표에 설명된 세 단계로 나눌 수 있는 프로세스를 따를 수 있습니다.

![마이그레이션 단계 - 준비, 설정, 온보드](images/phase-diagrams/migration-phases.png)

|단계 |설명 |
|--|--|
|[마이그레이션 준비](switch-to-microsoft-defender-prepare.md) |준비 [ **단계에서는**](switch-to-microsoft-defender-prepare.md)조직의 장치를 업데이트하고, 끝점에 대한 Defender를 다운로드하고, 역할 및 권한을 계획하고, 조직에 대한 액세스 권한을 Microsoft Defender 보안 센터. 또한 조직의 장치와 Endpoint용 Defender 간의 통신을 사용하도록 장치 프록시 및 인터넷 설정을 구성합니다. |
|[끝점에 대한 Defender 설정](switch-to-microsoft-defender-setup.md) |설치 [ **단계 중에는**](switch-to-microsoft-defender-setup.md)를 사용하도록 Microsoft Defender 바이러스 백신 수동 모드로 설정할 수 있습니다. 또한 기존 끝점 & 솔루션에 Microsoft Defender 바이러스 백신 제외에 대한 설정을 구성할 수 있습니다. 그런 다음 장치 그룹, 컬렉션 및 조직 구성 단위를 생성합니다. 마지막으로 맬웨어 방지 정책 및 실시간 보호 설정을 구성합니다.|
|[끝점용 Defender에 온보딩](switch-to-microsoft-defender-onboard.md) |[ **온보딩**](switch-to-microsoft-defender-onboard.md)단계에서 끝점용 Defender에 장치를 온보딩하고, Microsoft Defender 바이러스 백신 모드로 실행 중인지 확인하고, 끝점이 끝점용 Defender와 통신하는지 확인할 수 있습니다. 그런 다음 기존 끝점 보호 솔루션을 제거하고 끝점용 Defender가 제대로 작동하고 있는지 확인합니다. |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a>끝점용 Microsoft Defender에는 무엇이 포함되어 있나요?

이 마이그레이션 가이드에서는 엔드포인트용 Defender로 이동하기 위한 시작점으로 차세대 보호 및 끝점 감지 및 응답 기능에 중점을 두고 있습니다. [](microsoft-defender-antivirus-in-windows-10.md) [](overview-endpoint-detection-response.md) 그러나 Endpoint용 Defender에는 바이러스 백신 및 끝점 보호보다 훨씬 더 많은 보호가 포함되어 있습니다. Endpoint용 Defender는 예방적 보호, 위반 후 감지, 자동화된 조사 및 대응을 위한 통합 플랫폼입니다. 다음 표에는 끝점용 Defender의 기능이 요약되어 있습니다. 

| 기능/기능 | 설명 |
|---|---|
| [위협 및 취약성 관리](next-gen-threat-and-vuln-mgt.md) | 위협 & 취약성 관리 기능은 끝점(예: 장치)에서 약점을 식별, 평가 및 수정하는 데 도움이 됩니다. |
| [공격 표면 감소](overview-attack-surface-reduction.md) | 공격 표면 감소 규칙은 사이버 위협 및 공격으로부터 조직의 장치 및 응용 프로그램을 보호하는 데 도움이 됩니다. |
| [차세대 보호](microsoft-defender-antivirus-in-windows-10.md) | 차세대 보호에는 위협 Microsoft Defender 바이러스 백신 맬웨어를 차단하는 데 도움이 되는 여러 가지 기능도 포함되어 있습니다. |
| [엔드포인트 검색 및 대응](overview-endpoint-detection-response.md) | 끝점 감지 및 응답 기능은 침입 시도 및 활성 위반을 감지, 조사 및 대응합니다.  |
| [지능형 헌팅](advanced-hunting-overview.md) | 고급 헌팅 기능을 통해 보안 운영 팀은 알려진 위협 또는 잠재적인 위협의 지표와 엔터티를 찾을 수 있습니다. |
| [동작 차단 및 제약](behavioral-blocking-containment.md) | 동작 차단 및 포함 기능은 위협이 실행을 시작한 경우에도 동작 및 처리 트리를 기반으로 위협을 식별하고 중지하는 데 도움이 됩니다. |
| [자동화된 조사 및 수정](automated-investigations.md) | 자동화된 조사 및 대응 기능은 경고를 검사하고 위반을 해결하기 위해 즉시 수정 조치를 취합니다. |
| [위협 헌팅](microsoft-threat-experts.md) 서비스(Microsoft 위협 전문가) | 위협 헌팅 서비스는 보안 운영 팀에 전문가 수준의 모니터링 및 분석을 제공하고 중요한 위협이 누락되지 않도록 합니다. |

**자세한 내용을 원하세요? [끝점에 대한 Defender를 참조합니다.](microsoft-defender-endpoint.md)**

## <a name="next-step"></a>다음 단계

- 마이그레이션 [준비로 진행합니다.](switch-to-microsoft-defender-prepare.md)
