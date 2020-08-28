---
title: Microsoft 보안 점수의 새로운 기능
description: Microsoft 365 보안 센터에서 Microsoft 보안 점수에 대 한 새로운 변경 사항에 대해 설명 합니다.
keywords: 보안, 맬웨어, Microsoft 365, M365, 보안 점수, 보안 센터, 개선 작업
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
ms.openlocfilehash: 8b0fda2d8a0b7d9cb6b2c6a4cca2e8e34a876fec
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289426"
---
# <a name="whats-new-in-microsoft-secure-score"></a>Microsoft 보안 점수의 새로운 기능

Microsoft 보안 점수가 보안 상태를 보다 효율적으로 대표 하도록 하기 위해 몇 가지 사항을 변경 했습니다. 계획 된 변경 사항에 대 한 자세한 내용은 [Microsoft 보안 점수에서](microsoft-secure-score-whats-coming.md)제공 되는 기능을 참조 하세요.

## <a name="august-2020"></a>2020년 8월

### <a name="update-improvement-action-for-azure-active-directory"></a>Azure Active Directory에 대 한 업데이트 개선 작업

- 정책을 사용 하 여 레거시 인증 차단

## <a name="july-2020"></a>2020년 7월

### <a name="adding-improvement-actions-for-azure-advanced-threat-protection"></a>Azure Advanced Threat Protection에 대 한 개선 작업 추가

- 위험한 이동 경로
- 보안 되지 않은 계정 특성
- Active Directory 트러스트에서 보안 기능을 사용 하도록 설정
- 엔터티에서 보안 되지 않은 SID 기록 특성 제거

## <a name="june-2020"></a>2020년 6월

### <a name="removed-improvement-action-for-microsoft-defender-advanced-threat-protection"></a>Microsoft Defender Advanced Threat Protection에 대 한 개선 작업 제거 됨

* 공격 표면 축소 규칙 켜기

### <a name="added-improvement-actions-for-microsoft-defender-advanced-threat-protection"></a>Microsoft Defender Advanced Threat Protection에 대 한 개선 작업 추가

* 하위 프로세스를 만들지 못하도록 Adobe Reader 차단
* 랜 섬 웨어에 대 한 고급 보호 사용
* 모든 Office 응용 프로그램에서 하위 프로세스를 만들지 못하도록 차단
* Office 응용 프로그램에서 실행 가능한 콘텐츠를 만들지 못하도록 차단
* 다운로드 한 실행 가능한 콘텐츠를 실행 하는 JavaScript 또는 VBScript 차단
* 잠재적으로 난독 처리 된 스크립트의 실행 차단
* 전자 메일 클라이언트 및 webmail에서 실행 가능한 콘텐츠 차단
* Office 통신 응용 프로그램에서 하위 프로세스를 만들지 못하도록 차단
* 신뢰할 수 없으며 USB에서 실행 되는 서명 되지 않은 프로세스 차단
* WMI 이벤트 구독을 통해 지 속성 차단
* Office 응용 프로그램에서 다른 프로세스에 코드를 주입 하지 못하도록 차단
* 실행 파일이 전파, 연령 또는 신뢰할 수 있는 목록 조건을 충족 하지 않는 이상 실행 되지 않도록 차단
* PSExec 및 WMI 명령에서 시작 되는 프로세스 만들기 차단
* Windows 로컬 보안 기관 하위 시스템 (lsass.exe)에서 자격 증명 가로채기 차단
* Office 매크로에서 Win32 API 호출 차단

## <a name="incompatibility-with-identity-secure-score-and-graph-api"></a>Id 보안 점수 및 그래프 API와 호환 되지 않는 문제

최신 버전의 Microsoft 보안 점수에서는 향상 된 점수 매기기 모델이 출시 되었습니다. 이러한 변경으로 인해 보안 환경을 보다 유연 하 고 정확 하 게 확인할 수 있습니다. 그러나 이러한 업데이트는 Microsoft 보안 점수가 Id 보안 점수 및 그래프 API와 일시적으로 호환 되지 않습니다.

보안 성과를 식별 하 고 Graph API가 새 점수 매기기 모델을 채택 합니다. 그때까지 고객은 Microsoft 보안 점수, Id 보안 점수 및 그래프 API에서 보고 하는 점수의 차이를 볼 수 있습니다. 이로 인해 불편을 끼쳐 드려서 죄송 하며, 향후 이러한 환경이 더 높은 호환성을 유지 하기 위해 노력 하 고 있습니다.

## <a name="updated-improvement-actions"></a>업데이트 된 개선 작업

- Azure Active Directory 개선 작업 추가 됨
- Azure Advanced Threat Protection 개선 작업 추가
- Microsoft Defender ATP [위협 & 취약성 관리](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) 보안 권장 사항에 대 한 지원
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
