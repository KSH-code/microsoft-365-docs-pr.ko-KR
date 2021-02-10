---
title: Microsoft 365 보안 센터의 끝점용 Microsoft Defender
description: Microsoft Defender 보안 센터에서 Microsoft 365 보안 센터로의 변경 내용에 대해 자세히 알아보기
keywords: Microsoft 365 보안 센터, OATP, MDATP, MDO, MDE, 단일 창, 수렴형 포털, 보안 포털, Defender 보안 포털 시작
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.openlocfilehash: 03b73901512522edec7fdbc579eaf4073eed5d48
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167464"
---
# <a name="microsoft-defender-for-endpoint-in-the-microsoft-365-security-center"></a>Microsoft 365 보안 센터의 끝점용 Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**적용 대상:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Office 365용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2148715)

개선된 [Microsoft 365](overview-security-center.md) 보안 센터는 전자 메일, 공동 작업, ID 및 장치 위협을 보호, 감지, 조사 및 대응하는 보안 기능을 [https://security.microsoft.com](https://security.microsoft.com) 결합합니다. 이 보안 센터는 Microsoft Defender 보안 센터 및 Office 365 보안 및 규정 준수 센터를 포함하여 기존 Microsoft 보안 포털의 & 제공합니다.

Microsoft Defender 보안 센터에 익숙한 경우 이 문서는 개선된 Microsoft 365 보안 센터의 일부 변경 및 개선 사항을 설명하는 데 도움이 됩니다. 그러나 주의해야 할 몇 가지 새 요소와 업데이트된 요소가 있습니다.

지금까지 Microsoft [Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/portal-overview) 보안 센터는 끝점용 Microsoft Defender의 홈입니다. 엔터프라이즈 보안 팀은 이를 사용하여 잠재적인 고급 영구 위협 활동 또는 데이터 위반에 대한 경고를 모니터링하고 대응하는 데 도움을 주었다. 포털 수를 줄이기 위해 Microsoft 365 보안 센터는 Microsoft ID, 데이터, 장치, 앱 및 인프라 전체의 보안을 모니터링하고 관리할 수 있는 홈이 됩니다.

> [!IMPORTANT]
> Microsoft 365 보안 센터에 표시하는 내용은 현재 구독에 따라 다를 수 있습니다. 예를 들어 Office 365용 Microsoft Defender 라이선스가 없는 경우 전자 메일 & 공동 작업 섹션이 표시되지 않습니다.

개선된 Microsoft 365 보안 센터를 살펴보아야 [https://security.microsoft.com](https://security.microsoft.com) 합니다.

이점에 대해 자세히 알아보시고, [Microsoft 365](overview-security-center.md) 보안 센터 개요

## <a name="whats-changed"></a>변경된 것

이 표는 Microsoft Defender 보안 센터와 Microsoft 365 보안 센터 간의 변경 내용에 대한 빠른 참조입니다.

### <a name="alerts-and-actions"></a>경고 및 작업

|**영역**  |**변경 설명**  |
|---------|---------|
| [인시던트 & 경고](incidents-overview.md)  | Microsoft 365 보안 센터에서 모든 끝점, 전자 메일 및 ID에서 인시던트 및 알림을 관리할 수 있습니다. 관련 이벤트를 보다 쉽게 찾을 수 있도록 환경을 수렴했습니다. 자세한 내용은 인시던트 [개요를 참조하세요.](incidents-overview.md)   |
| [헌팅](advanced-hunting-overview.md)  |  ID 및 전자 메일 테이블을 포함하도록 끝점용 Microsoft Defender에서 만든 사용자 지정 검색 규칙을 수정하면 자동으로 Microsoft 365 Defender로 이동됩니다. 해당 경고는 Microsoft 365 Defender에도 표시됩니다. 이러한 변경 내용에 대한 자세한 내용은 사용자 지정 검색 규칙 [마이그레이션을 참조합니다.](advanced-hunting-migrate-from-mdatp.md#migrate-custom-detection-rules) Microsoft `DeviceAlertEvents` 365 Defender에서는 고급 헌팅 표를 사용할 수 없습니다. Microsoft 365 Defender에서 장치별 경고 정보를 쿼리하려면 테이블을 사용하여 다양한 소스 집합의 더 많은 정보를 수용할 `AlertInfo` `AlertEvidence` 수 있습니다. [DeviceAlertEvents](advanced-hunting-migrate-from-mdatp.md#write-queries-without-devicealertevents)없이 쓰기 쿼리를 수행하여 다음 장치 관련 쿼리를 작성합니다.|
|[센터](mtp-action-center.md)    | 자동화된 조사 및 수정 조치에 따라 수행된 보류 중인 작업 및 완료된 작업을 나열합니다. 이전의 Microsoft Defender 보안 센터의 알림 센터에는 장치에서만 수행된 수정 작업에 대한 보류 중 및 완료된 작업이 나열되어 있으며 자동화된 조사에는 경고 및 상태가 나열되어 있습니다. 향상된 Microsoft 365 보안 센터에서 알림 센터는 전자 메일, 장치 및 사용자에 대한 수정 작업과 조사를 한 위치에 모아 제공합니다.  |
| [위협 분석](threat-analytics.md) |  탐색 모음의 위쪽으로 이동하여 보다 쉽게 검색하고 사용할 수 있습니다. 이제 끝점과 전자 메일 및 공동 작업 둘 다에 대한 위협 정보를 포함합니다.    |

### <a name="endpoints"></a>끝점

|**영역**  |**변경 설명**  |
|---------|---------|
|검색   |  제목 대신 끝점용 Microsoft Defender 검색 표시줄이 끝점 섹션 아래로 이동됩니다. 장치, 파일, 사용자, URL, IPS, 취약성, 소프트웨어 및 권장 사항을 계속 검색할 수 있습니다.  |
|[Dashboard](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/security-operations-dashboard)   |  보안 작업 대시보드입니다. 트리거된 활성 경고 수, 위험에 노출된 장치, 위험 상태의 사용자 및 경고, 장치 및 사용자에 대한 심각도 수준에 대한 개요를 참조하세요. 장치에 센서 문제, 전반적인 서비스 상태 및 해결되지 않은 경고가 감지된 방법을 볼 수도 있습니다. |
|장치 인벤토리 | 변경 내용이 없습니다. |
|[취약성 관리](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)    |    탐색 창에 맞게 이름을 짧게 지정합니다. 모든 페이지가 아래에 있는 위협 및 취약성 관리 섹션과 동일합니다.     |
| 파트너 및 API | 변경 내용이 없습니다. |
| 평가 & 자습서    |     새로운 테스트 및 학습 기능.     |
| 구성 관리   |  변경 내용이 없습니다.  |

> [!NOTE]
> **자동 조사 및 수정은** 이제 인시던트의 일부입니다. 인시던트 및 조사 탭에서 자동화된 조사 **및 수정 > 수** 있습니다.

### <a name="access-and-reporting"></a>액세스 및 보고

|**영역**  |**변경 설명**  |
|---------|---------|
| 보고서  | 위협 방지, 장치 상태 및 규정 & 및 취약한 장치를 포함하여 끝점 및 전자 메일 공동 작업에 대한 보고서를 참조하세요. |
| 상태  |  현재 Microsoft [365](https://admin.microsoft.com/)관리 센터의 "서비스 상태" 페이지로 연결됩니다. |
| 설정 |  Microsoft 365 보안 센터, Microsoft 365 Defender, 끝점, 전자 메일 & 공동 작업, ID 및 장치 검색에 대한 설정을 관리합니다.   |

## <a name="microsoft-365-security-navigation-and-capabilities"></a>Microsoft 365 보안 탐색 및 기능

왼쪽 탐색 또는 빠른 실행 표시줄은 친숙한 모양입니다. 그러나 이 보안 센터에는 몇 가지 새 요소와 업데이트된 요소가 있습니다.

### <a name="incidents-and-alerts"></a>인시던트 및 경고

전자 메일, 장치 및 ID 전반에 걸쳐 인시던트 및 경고 관리를 모아야 합니다. 경고 페이지는 공격 신호를 결합하여 자세한 스토리를 생성하여 경고에 대한 전체 컨텍스트를 제공합니다. 새로운 통합 환경은 이제 워크로드 전반에 걸쳐 일관된 경고 보기를 제공합니다. 신속하게 조사하고 효과적인 조치를 취할 수 있습니다.

- [인시던트에 대해 자세히 알아보기](incidents-overview.md)
- [경고 관리에 대한 자세한 내용은](investigate-alerts.md)

![경고 및 작업 빠른 실행 표시줄](../../media/converge-1-alerts-and-actions.png)

### <a name="hunting"></a>헌팅

고급 헌팅 쿼리를 사용하여 끝점, Office 365 사서함 등에서 위협, 맬웨어 및 악의적인 활동을 사전 [검색합니다.](advanced-hunting-overview.md) 이러한 강력한 쿼리를 사용하여 알려진 위협과 잠재적 위협에 대한 위협 지표 및 엔터티를 찾고 검토할 수 있습니다.

[사용자 지정 검색](custom-detection-rules.md) 규칙은 고급 헌팅 쿼리를 사용하여 위반 활동 및 잘못 구성된 장치를 나타내는 이벤트를 사전 예방적으로 감시하는 데 도움이 될 수 있습니다.


### <a name="action-center"></a>센터

관리 센터에는 자동화된 조사 및 응답 기능으로 만든 조사가 표시되어 있습니다. Microsoft 365 Defender의 이 자동화된 자동 복구는 특정 이벤트에 자동으로 응답하여 보안 팀에 도움을 줄 수 있습니다.

[알림 센터에 대한 자세한 정보 알아보기](mtp-action-center.md)

### <a name="threat-analytics"></a>위협 분석

전문가 Microsoft 보안 연구자로부터 위협 인텔리전스를 얻습니다. Threat Analytics는 새로운 위협에 직면할 때 보안 팀의 효율성을 향상시킵니다. 위협 분석에는 다음이 포함됩니다.

- Office 365용 Microsoft Defender의 전자 메일 관련 검색 및 완화 이는 끝점용 Microsoft Defender에서 이미 사용 가능한 끝점 데이터 외에 추가됩니다.
- 인시던트는 위협과 관련된 보기입니다.
- 보고서에서 실행 가능한 정보를 빠르게 식별하고 사용할 수 있는 향상된 환경입니다.

Microsoft 365 보안 센터의 왼쪽 위 탐색 모음 또는 조직의 최상위 위협을 표시하는 전용 대시보드 카드에서 위협 분석에 액세스할 수 있습니다.

위협 분석을 사용하여 새로운 위협을 추적하고 [대응하는 방법에 대해 자세히 알아보십시오.](https://docs.microsoft.com/microsoft-365/security/mtp/threat-analytics)

### <a name="endpoints-section"></a>Endpoints 섹션

조직에서 끝점 보안을 보고 관리합니다. Microsoft Defender 보안 센터를 사용한 경우 익숙해 보이게 됩니다.

![끝점 빠른 실행 표시줄](../../media/converge-2-endpoints.png)

### <a name="access-and-reports"></a>액세스 및 보고서

보고서를 보고, 설정을 변경하고, 사용자 역할을 수정합니다.

![Access 및 보고 빠른 시작 표시줄](../../media/converge-4-access-and-reporting-new.png)

### <a name="siem-api-connections"></a>SIEM API 연결

Endpoint [SIEM API용 Defender를](/windows/security/threat-protection/microsoft-defender-atp/enable-siem-integration.md)사용하는 경우 계속 진행할 수 있습니다. Microsoft 365 보안 포털의 경고 페이지 또는 인시던트 페이지를 지점으로 하는 API 페이로드에 새 링크가 추가되었습니다. 새 API 필드에는 LinkToMTP 및 IncidentLinkToMTP가 포함됩니다. 자세한 내용은 [끝점용 Microsoft Defender에서 Microsoft 365](/microsoft-365/security/mtp/microsoft-365-security-mde-redirection.md)보안 센터로 계정 리디렉션을 참조하세요.

### <a name="email-alerts"></a>전자 메일 알림

끝점용 Defender에 대한 전자 메일 알림을 계속 사용할 수 있습니다. Microsoft 365 보안 센터의 경고 페이지 또는 인시던트 페이지를 알리는 새 링크가 전자 메일에 추가되었습니다. 자세한 내용은 [끝점용 Microsoft Defender에서 Microsoft 365](/microsoft-365/security/mtp/microsoft-365-security-mde-redirection.md)보안 센터로 계정 리디렉션을 참조하세요.

## <a name="related-information"></a>관련 정보

- [Microsoft 365 보안 센터](overview-security-center.md)
- [Microsoft 365 보안 센터의 끝점용 Microsoft Defender](microsoft-365-security-center-mde.md)
- [끝점용 Microsoft Defender에서 Microsoft 365 보안 센터로 계정 리디렉션](microsoft-365-security-mde-redirection.md)
