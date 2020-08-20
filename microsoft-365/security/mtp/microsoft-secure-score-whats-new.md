---
title: Microsoft 보안 점수의 새로운 기능
description: Microsoft 365 보안 센터에서 Microsoft 보안 점수가 변경된 새로운 사항에 대해 설명합니다.
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
ms.openlocfilehash: 644e12d3b9dfecc0a31c8d464033e41670bc7b88
ms.sourcegitcommit: 22fd8517707ed3ab6ef996247ad2aa372535ee56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2020
ms.locfileid: "46815234"
---
# <a name="whats-new-in-microsoft-secure-score"></a>Microsoft 보안 점수의 새로운 기능

Microsoft 보안 점수를 보다 정확하게 위한 보안 환경을 만들려면 몇 가지 사항을 변경하시기 가간 작업을 수행하겠습니다. 계획된 변경 사항에 대한 자세한 내용은 [Microsoft Secure Score를 통해 제공될 기능을 확인합니다.](microsoft-secure-score-whats-coming.md)

## <a name="july-2020"></a>2020년 7월

### <a name="adding-improvement-actions-for-azure-advanced-threat-protection"></a>Azure Advanced Threat Protection에 대한 개선 작업 추가

- 위험한 기본 이동 경로
- 보안되지 않은 계정 특성
- Active Directory 트러스트에서 보안 기능 사용
- ID의 보안되지 않은 SID 기록 특성 제거

## <a name="june-2020"></a>2020년 6월

### <a name="removed-improvement-action-for-microsoft-defender-advanced-threat-protection"></a>Microsoft Defender Advanced Threat Protection에 대한 향상 조치 제거

* 공격 범위 축소 규칙 켜기

### <a name="added-improvement-actions-for-microsoft-defender-advanced-threat-protection"></a>Microsoft Defender Advanced Threat Protection에 대한 개선 조치 추가

* Adobe Reader에서 하위 프로세스를 만들 수 차단
* 임의 배포에 고급 보호 사용
* 모든 Office 응용 프로그램에서 하위 프로세스를 만드는 것을 차단합니다.
* Office 응용 프로그램에서 실행 가능 콘텐츠를 만드는 것을 차단
* JavaScript 또는 VBScript에서 다운로드된 실행 가능 콘텐츠 실행 차단
* 잠재적으로 조작된 스크립트 실행을 차단
* 메일 클라이언트 및 웹 메일에서 실행 콘텐츠 차단
* Office 통신 응용 프로그램에서 하위 프로세스를 만드는 것을 차단
* USB에서 실행되는 신뢰할 수 없는 프로세스와 서명되지 않은 프로세스 차단
* WMI 이벤트 구독을 통해 지속성 차단
* Office 응용 프로그램이 다른 프로세스에 코드를 삽입하는 작업을 차단
* 준비, 연령 또는 신뢰할 수 있는 목록 조건을 충족하지 않는 경우 실행 파일이 실행되지 않도록 차단
* PSExec 및 WMI 명령에서 실행되는 프로세스 생성 차단
* Windows 로컬 보안 기관 하위 시스템(2)에서 자격 증명 lsass.exe 차단
* Office 매크로에서 Win32 API 호출 차단

## <a name="incompatibility-with-identity-secure-score-and-graph-api"></a>ID 보안 점수 및 Graph API와 이전 버전과의 호환성

Microsoft 보안 점수의 최근 릴리스에서 개선된 점수 모델이 릴리스되었습니다. 이러한 변경 사항을 통해 보안 환경을 보다 유연하고 정확하고 정확한 보기로 볼 수 있습니다. 그러나 이러한 업데이트는 ID 보안 점수 및 그래프 API와 일시적으로 호환되지 않아진 상태에서 Microsoft Secure Score로 만들였습니다.

시간으로 ID 보안 점수 및 Graph API가 새 점수 모델을 채택합니다. 고객에게Microsoft Secure Score, ID Secure Score 및 Graph API에서 보고한 점수에 차이점이 표시됩니다. 이러한 경험이 어우러지고, 이로 인해 이러한 환경이 더욱 호환되는지 확인하기 위해 노트하세요.

## <a name="updated-improvement-actions"></a>업데이트된 개선 작업

- Azure Active Directory 개선 작업 추가됨
- Azure Advanced Threat Protection 개선 작업 추가됨
- Microsoft Defender ATP [위협 & 취약성 관리 보안](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) 권장 사항에 대한 지원
    - 현재 출시된 모든 보안 권장 사항이 이제 사용 가능

## <a name="updated-interface-and-functionality"></a>업데이트된 인터페이스 및 기능

* CISO 및 리더 수준 토론에 대한 모든 새로운 메트릭 및 추세 보기
* 점수를 추적 및 벤치마크하는 새로운 방법
* 점수 회수에 대한 추적 및 이해 향상
* 개선 조치를 필터링, 태그, 검색 및 그룹화
* 점수 프로젝션 및 계획된 작업을 사용하여 향후 목표 관리
* 기타!

## <a name="we-want-to-hear-from-you"></a>Microsoft에서 날레이를 우리 저

문제가 있는 경우 보안, 개인 정보 보호 및 준수 [커뮤니티에 &](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 알려주세요. 커뮤니티 모니터링 및 지원을 제공합니다.

## <a name="related-resources"></a>관련 리소스

- [보안 상태 평가](microsoft-secure-score-improvement-actions.md)
- [Microsoft 보안 점수 기록 추적 및 목표 충족](microsoft-secure-score-history-metrics-trends.md)
- [향후 계획](microsoft-secure-score-whats-coming.md)
