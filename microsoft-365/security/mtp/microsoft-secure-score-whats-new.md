---
title: Microsoft 보안 점수의 새로운
description: Microsoft 365 보안 센터에서 Microsoft 보안 점수에 대한 새로운 변경 내용에 대해 설명
keywords: Microsoft 보안 점수, 보안 점수, Office 365 보안 점수, Microsoft 보안 점수, Microsoft 365 보안 센터
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 039ec1c3f9b0ba233f950d11b9d58be341b28121
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930597"
---
# <a name="whats-new-in-microsoft-secure-score"></a>Microsoft 보안 점수의 새로운

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Microsoft 보안 점수가 보안 자세를 보다 잘 대표할 수 있도록 몇 가지 변경을 적용하고 있습니다. 계획된 변경에 대한 자세한 내용은 Microsoft 보안 점수의 출시 [예정을 참조하세요.](microsoft-secure-score-whats-coming.md)

Microsoft 보안 점수는 https://security.microsoft.com/securescore Microsoft [365](overview-security-center.md)보안 센터에서 찾을 수 있습니다.

## <a name="january-2021"></a>2021년 1월

### <a name="added-our-first-security-recommendation-for-microsoft-teams"></a>Microsoft Teams에 대한 첫 번째 보안 권장이 추가되었습니다.

Microsoft Teams 고객은 보안 점수의 새로운 개선 작업으로 "익명 사용자가 모임에 참가하지 못하도록 제한"을 볼 수 있습니다.

## <a name="december-2020"></a>2020년 12월

### <a name="added-six-accounts-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a>끝점용 Microsoft Defender(이전의 Microsoft Defender ATP)에 대한 6개의 계정 관련 개선 작업이 추가되었습니다.

- '최소 암호 길이'를 '14자 이상'으로 설정
- '암호 기록 적용'을 '24개 이상의 암호'로 설정
- '최대 암호 사용 기간'을 '60일 이하로 설정하고 0일은 안 되지만'
- '최소 암호 사용'을 '1일 이상'으로 설정
- 기본 제공 관리자 계정을 사용하지 않도록 설정
- 기본 제공 게스트 계정을 사용하지 않도록 설정

## <a name="november-2020"></a>2020년 11월

### <a name="removed-the-ability-to-create-servicenow-tickets-through-secure-score"></a>보안 점수를 통해 ServiceNow 티켓을 만드는 기능을 제거했습니다. 

Share > **ServiceNow로** 진행하여 보안 점수를 통해 ServiceNow 티켓을 만드는 기능을 더 이상 사용할 수 없습니다. 다음 단계를 결정하는 동안 여러분의 피드백에 감사드립니다. 지원을 계속해주신 경우

### <a name="added-three-services-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a>끝점용 Microsoft Defender(이전의 Microsoft Defender ATP)에 대한 세 가지 서비스 관련 개선 작업이 추가되었습니다.

- Windows 서비스에 대한 인용되지 않은 서비스 경로 수정
- 서비스 실행 경로를 공통으로 보호된 위치로 변경
- Windows 레지스트리에서 캐시된 암호를 방지하려면 서비스 계정 변경

## <a name="october-2020"></a>2020년 10월

### <a name="remove-improvement-action-related-to-microsoft-defender-for-endpoint"></a>끝점용 Microsoft Defender 관련 개선 작업 제거

- 경고를 표시하기 위해 Microsoft Defender SmartScreen Windows 스토어 앱 웹 콘텐츠 확인 설정

## <a name="august-2020"></a>2020년 8월

### <a name="updated-improvement-action-for-azure-active-directory"></a>Azure Active Directory에 대한 개선 작업 업데이트

- 정책을 사용하여 레거시 인증 차단

## <a name="incompatibility-with-identity-secure-score-and-graph-api"></a>ID 보안 점수 및 Graph API와의 비호치

Microsoft 보안 점수의 최근 릴리스에서는 향상된 점수 모델이 릴리스되었습니다. 이러한 변경을 통해 보안 자세를 보다 유연하고 정확하게 볼 수 있습니다. 그러나 이러한 업데이트로 Microsoft 보안 점수가 ID 보안 점수 및 Graph API와 일시적으로 무관하게 됩니다.

시간이 지날 때 ID 보안 점수 및 Graph API는 새로운 점수 매기기 모델을 채택합니다. 그 때까지 고객은 Microsoft 보안 점수, ID 보안 점수 및 Graph API에서 보고한 점수의 차이를 확인할 수 있습니다. 이로 인해 불편을 드려 죄송합니다. 향후 이러한 환경이 더욱 호환되도록 지원하기 위해 작업 중입니다.

## <a name="updated-improvement-actions"></a>개선 작업 업데이트

- Azure Active Directory 개선 작업 추가
- ID 개선 작업에 대한 Microsoft Defender 추가
- Endpoint Threat 및 취약성 [& 보안](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) 권장 사항에 대한 Microsoft Defender 지원
    - TVM에서 제공하는 모든 릴리스된 보안 권장 사항을 이제 사용할 수 있습니다.

## <a name="updated-interface-and-functionality"></a>업데이트된 인터페이스 및 기능

* CISO 및 잠재 고객 수준 토론에 대한 모든 새로운 메트릭 및 추세 보기
* 점수를 추적하고 벤치마크하는 새로운 방법
* 점수 회귀에 대한 더 나은 추적 및 이해
* 개선 작업 필터링, 태그, 검색 및 그룹화
* 점수 투영 및 계획된 작업을 사용하여 향후 목표에 대한 관리
* 그리고 더 많이 있습니다!

## <a name="we-want-to-hear-from-you"></a>의견을 보내 주세요.

문제가 있는 경우 보안, 개인 정보 보호 및 규정 준수 커뮤니티에 & [알려주세요.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 커뮤니티를 모니터링하고 있으며 도움을 제공할 것입니다.

## <a name="related-resources"></a>관련 리소스

- [보안 상태 평가](microsoft-secure-score-improvement-actions.md)
- [Microsoft 보안 점수 기록 추적 및 목표 충족](microsoft-secure-score-history-metrics-trends.md)
- [향후 계획](microsoft-secure-score-whats-coming.md)
