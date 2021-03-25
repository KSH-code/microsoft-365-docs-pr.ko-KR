---
title: McAfee에서 끝점용 Microsoft Defender로 마이그레이션
description: McAfee에서 끝점용 Microsoft Defender로 전환합니다. 개요는 이 문서를 읽어 읽습니다.
keywords: 마이그레이션, Windows Defender Advanced Threat Protection, atp, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
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
- m365solution-mcafeemigrate
- m365solution-overview
ms.topic: conceptual
ms.custom: migrationguides
ms.date: 03/03/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 53d9e68fa357d07cf70ab2282de9cee9fc0bd90d
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185638"
---
# <a name="migrate-from-mcafee-to-microsoft-defender-for-endpoint"></a>McAfee에서 끝점용 Microsoft Defender로 마이그레이션

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

McAfee Endpoint Security(McAfee)에서 [끝점용 Microsoft Defender(끝점용 Microsoft Defender)로](https://docs.microsoft.com/windows/security/threat-protection) 전환할 계획이면 올바른 장소에 있습니다. 이 문서를 가이드로 사용하세요.


:::image type="content" source="images/mcafee-mde-migration.png" alt-text="McAfee에서 끝점용 Defender로 마이그레이션 개요":::

McAfee에서 Endpoint용 Defender로 전환하는 경우 활성 모드에서 McAfee 솔루션으로 시작하고, 수동 모드에서 끝점용 Defender를 구성하고, 끝점용 Defender에 온보딩한 다음 Endpoint용 Defender를 활성 모드로 설정하고 McAfee를 제거합니다.

## <a name="the-migration-process"></a>마이그레이션 프로세스

McAfee에서 끝점용 Microsoft Defender로 전환하는 경우 준비, 설치 및 온보딩의 세 단계로 나눌 수 있는 프로세스를 따를 수 있습니다. 

![마이그레이션 단계 - 설치 온보드 준비](images/phase-diagrams/migration-phases.png)

|단계 |설명 |
|--|--|
|[마이그레이션 준비](mcafee-to-microsoft-defender-prepare.md) |준비 [**단계에서는**](mcafee-to-microsoft-defender-prepare.md) 조직의 장치를 업데이트하고, 끝점용 Microsoft Defender를 다운로드하고, 역할 및 권한을 계획하고, Microsoft Defender 보안 센터에 대한 액세스 권한을 부여합니다. 또한 조직의 장치와 끝점용 Microsoft Defender 간의 통신을 사용하도록 장치 프록시 및 인터넷 설정을 구성합니다. |
|[끝점에 대한 Microsoft Defender 설정](mcafee-to-microsoft-defender-setup.md) |설치 [**단계에서는**](mcafee-to-microsoft-defender-setup.md) Microsoft Defender 바이러스 백신을 사용하도록 설정하고 수동 모드에 있는지 확인한 다음 Microsoft Defender 바이러스 백신, 끝점용 Microsoft Defender 및 McAfee에 & 제외 설정을 구성합니다. 장치 그룹, 컬렉션 및 조직 구성 단위도 만들 수 있습니다. 마지막으로 맬웨어 방지 정책 및 실시간 보호 설정을 구성합니다.|
|[끝점용 Microsoft Defender에 온보딩](mcafee-to-microsoft-defender-onboard.md) |[**온보딩**](mcafee-to-microsoft-defender-onboard.md) 단계에서는 디바이스를 끝점용 Microsoft Defender에 온보딩하고 해당 장치가 끝점용 Microsoft Defender와 통신하는지 확인할 수 있습니다. 마지막으로 McAfee를 제거하고 끝점용 Microsoft Defender & Microsoft Defender 바이러스 백신을 통한 보호가 활성 모드에 있는지 확인 합니다. |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a>끝점용 Microsoft Defender에는 무엇이 포함되어 있나요?

이 마이그레이션 가이드에서는 끝점용 Microsoft [](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) Defender로 이동하기 위한 시작점으로 차세대 보호 및 끝점 감지 및 응답 기능에 중점을 두고 있습니다. [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) 그러나 끝점용 Microsoft Defender에는 바이러스 백신 및 끝점 보호보다 훨씬 더 많은 보호가 포함되어 있습니다. 엔드포인트용 Microsoft Defender는 예방적 보호, 침해 후 감지, 자동화된 조사 및 대응을 위한 통합 플랫폼입니다. 다음 표에는 끝점용 Microsoft Defender의 기능이 요약되어 있습니다. 

| 기능/기능 | 설명 |
|---|---|
| [위협 & 취약성 관리](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) | 위협 & 관리 기능은 끝점(예: 장치)에서 약점을 식별, 평가 및 수정하는 데 도움이 됩니다. |
| [공격 표면 감소](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-attack-surface-reduction) | 공격 표면 감소 규칙은 사이버 위협 및 공격으로부터 조직의 장치 및 응용 프로그램을 보호하는 데 도움이 됩니다. |
| [차세대 보호](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) | 차세대 보호에는 위협과 맬웨어를 차단하는 데 도움이 되는 Microsoft Defender 바이러스 백신이 포함되어 있습니다. |
| [끝점 감지 및 대응](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) | 끝점 감지 및 응답 기능은 침입 시도 및 활성 위반을 감지, 조사 및 대응합니다.  |
| [고급 헌팅](advanced-hunting-overview.md) | 고급 헌팅 기능을 통해 보안 운영 팀은 알려진 위협 또는 잠재적인 위협의 지표와 엔터티를 찾을 수 있습니다. |
| [동작 차단 및 포함](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) | 동작 차단 및 포함 기능은 위협이 실행을 시작한 경우에도 동작 및 처리 트리를 기반으로 위협을 식별하고 중지하는 데 도움이 됩니다. |
| [자동화된 조사 및 수정](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations) | 자동화된 조사 및 대응 기능은 경고를 검사하고 위반을 해결하기 위해 즉시 수정 조치를 취합니다. |
| [위협 헌팅 서비스(Microsoft](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-threat-experts) 위협 전문가) | 위협 헌팅 서비스는 보안 운영 팀에 전문가 수준의 모니터링 및 분석을 제공하고 중요한 위협이 누락되지 않도록 합니다. |

**자세한 내용을 원하세요? [끝점용 Microsoft Defender를 참조합니다.](https://docs.microsoft.com/windows/security/threat-protection)**

## <a name="next-step"></a>다음 단계

- 마이그레이션 [준비로 진행합니다.](mcafee-to-microsoft-defender-prepare.md)
