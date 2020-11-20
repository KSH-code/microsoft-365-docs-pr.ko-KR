---
title: Microsoft 보안 점수의 새로운 기능
description: Microsoft 365 보안 센터에서 Microsoft 보안 점수에 대 한 새로운 변경 사항에 대해 설명 합니다.
keywords: microsoft 보안 점수, 보안 점수, office 365 보안 점수, microsoft security 점수, microsoft 365 보안 센터
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 6d1358da465bd7e31ca7b234f140aa8e48bb7508
ms.sourcegitcommit: aa8d2de6ffac0157fffd14d0ea7f51ef0c287607
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/20/2020
ms.locfileid: "49373998"
---
# <a name="whats-new-in-microsoft-secure-score"></a>Microsoft 보안 점수의 새로운 기능

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Microsoft 보안 점수가 보안 상태를 보다 효율적으로 대표 하도록 하기 위해 몇 가지 사항을 변경 했습니다. 계획 된 변경 사항에 대 한 자세한 내용은 [Microsoft 보안 점수에서](microsoft-secure-score-whats-coming.md)제공 되는 기능을 참조 하세요.

Microsoft 보안 점수 https://security.microsoft.com/securescore 는 [microsoft 365 보안 센터](overview-security-center.md)에서 찾을 수 있습니다.

## <a name="november-2020"></a>11 월 2020

### <a name="added-3-services-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a>끝점에 대 한 Microsoft Defender에 대 한 서비스 관련 향상 작업 3 개 (이전의 Microsoft Defender ATP)가 추가 되었습니다.

- Windows 서비스에 대 한 따옴표 붙지 않은 서비스 경로 수정
- 서비스 실행 가능한 경로를 일반 보호 위치로 변경
- Windows 레지스트리에서 캐시 된 암호를 사용 하지 않도록 서비스 계정 변경

## <a name="october-2020"></a>2020년 10월

### <a name="remove-improvement-action-related-to-microsoft-defender-for-endpoint"></a>끝점에 대 한 Microsoft Defender와 관련 된 개선 작업 제거

- Microsoft Defender SmartScreen Windows 스토어 앱 웹 콘텐츠 검사를 설정 하 여 경고 표시

## <a name="august-2020"></a>2020년 8월

### <a name="updated-improvement-action-for-azure-active-directory"></a>Azure Active Directory에 대 한 개선 된 기능 업데이트

- 정책을 사용 하 여 레거시 인증 차단

## <a name="incompatibility-with-identity-secure-score-and-graph-api"></a>Id 보안 점수 및 그래프 API와 호환 되지 않는 문제

최신 버전의 Microsoft 보안 점수에서는 향상 된 점수 매기기 모델이 출시 되었습니다. 이러한 변경으로 인해 보안 환경을 보다 유연 하 고 정확 하 게 확인할 수 있습니다. 그러나 이러한 업데이트는 Microsoft 보안 점수가 Id 보안 점수 및 그래프 API와 일시적으로 호환 되지 않습니다.

보안 성과를 식별 하 고 Graph API가 새 점수 매기기 모델을 채택 합니다. 그때까지 고객은 Microsoft 보안 점수, Id 보안 점수 및 그래프 API에서 보고 하는 점수의 차이를 볼 수 있습니다. 이로 인해 불편을 끼쳐 드려서 죄송 하며, 향후 이러한 환경이 더 높은 호환성을 유지 하기 위해 노력 하 고 있습니다.

## <a name="updated-improvement-actions"></a>업데이트 된 개선 작업

- Azure Active Directory 개선 작업 추가 됨
- Id 향상 작업을 위해 Microsoft Defender를 추가 했습니다.
- 끝점 위협에 대 한 Microsoft Defender 지원 [& 취약성 관리](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) 보안 권장 사항
    - 이제 TVM에서 제공 하는 모든 릴리스된 보안 권장 사항을 사용할 수 있습니다.

## <a name="updated-interface-and-functionality"></a>업데이트 된 인터페이스 및 기능

* CISO 팀장 수준 토론을 위한 모든 새 메트릭 및 추세 보기
* 점수를 추적 하 고 벤치 마크 위한 새로운 방법
* 점수 재발에 대 한 추적 및 이해 향상
* 개선 작업 필터링, 태그, 검색 및 그룹화
* 점수 예측 및 계획 된 작업을 사용 하 여 향후 목표를 향해 관리
* 더 많은 내용을 확인해 보세요.

## <a name="we-want-to-hear-from-you"></a>사용자의 의견을 듣고 싶습니다.

문제가 있는 경우 [보안, 개인 정보 & 준수](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 커뮤니티에 게시 하 여 알려 주세요. 당사는 커뮤니티를 모니터링 하 고 도움이 될 것입니다.

## <a name="related-resources"></a>관련 리소스

- [보안 상태 평가](microsoft-secure-score-improvement-actions.md)
- [Microsoft 보안 점수 기록 및 목표를 충족 하는 추적](microsoft-secure-score-history-metrics-trends.md)
- [향후 계획](microsoft-secure-score-whats-coming.md)
