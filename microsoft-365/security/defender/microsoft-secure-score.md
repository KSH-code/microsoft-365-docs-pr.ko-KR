---
title: Microsoft Secure Score
description: Microsoft 365 Defender 포털의 Microsoft 보안 점수, 보안 상태 개선 방법 및 보안 관리자가 기대할 수 있는 항목에 대해 설명
keywords: Microsoft 보안 점수, 보안 점수, Office 365 보안 점수, Microsoft 보안 점수, Microsoft 365 Defender 포털, 개선 작업
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- Adm_TOC
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: bfe3718a6e8c82c516a395e2d2c7f43d21ceda04
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60196672"
---
# <a name="microsoft-secure-score"></a>Microsoft Secure Score

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Microsoft Secure Score는 조직의 보안 태세에 대한 평가 점수로, 점수가 높을수록 더 많은 개선 작업이 수행되었다는 뜻입니다. 이 사이트는 사이트 포털 https://security.microsoft.com/securescore [에서 Microsoft 365 Defender 있습니다.](overview-security-center.md)

Secure Score 권장 사항을 따르면 조직을 위협으로부터 지킬 수 있습니다. 조직은 Microsoft 365 Defender 포털의 중앙 집중식 대시보드에서 ID, 앱 및 Microsoft 365 보안에 대해 모니터링하고 작업할 수 있습니다.

Secure Score는 조직에 다음과 같은 도움을 제공합니다.  

* 조직 보안 태세의 현 상태를 보고합니다.
* 검색 가능성과 표시 여부, 안내, 컨트롤을 제공함으로써 보안 태세를 개선합니다.  
* 벤치마크와 비교 및 KPI(핵심성과지표) 수립.

조직은 메트릭 및 추세의 강력한 시각화, 다른 Microsoft 제품과의 통합, 유사한 조직과의 점수 비교 등의 강력한 시각화에 액세스할 수 있습니다. 또한 타사 솔루션에서 권장 작업을 해결한 경우 점수가 반영될 수 있습니다.

![보안 점수 홈페이지입니다.](../../media/secure-score/secure-score-home-page.png)

## <a name="how-it-works"></a>작업 방법

다음 작업에 대한 포인트가 부여됩니다.

- 권장 보안 기능 구성
- 보안 관련 작업 수행
- 타사 응용 프로그램 또는 소프트웨어를 사용하여 개선 작업 해결 또는 대체 완화

일부 개선 작업은 완전히 완료될 때만 포인트를 제공 합니다. 일부는 일부 장치 또는 사용자에 대해 완료된 경우 부분 지점을 제공합니다. 개선 작업 중 하나를 제정할 수 없는 경우 위험 또는 남은 위험을 수락할 수 있습니다.

지원되는 Microsoft 제품 중 하나에 대한 라이선스가 있는 경우 해당 제품에 대한 권장 사항이 표시 됩니다. 라이선스 버전, 구독 또는 계획에 관계없이 제품에 대해 가능한 전체 개선된 기능 집합이 표시되어 있습니다. 이렇게 하면 보안 모범 사례를 이해하고 점수를 향상시킬 수 있습니다. 보안 점수로 표현되는 절대 보안 설정은 조직이 특정 제품에 대해 소유하는 라이선스에 상관없이 동일하게 유지 됩니다. 보안은 항상 사용 편의성과 균형을 유지해야 하며, 환경에 대한 권장 사항은 일부에 적용되지 않습니다.

점수는 시각화 및 개선 작업 페이지에 제공된 정보를 반영하여 실시간으로 업데이트됩니다. 또한 보안 점수는 각 작업에서 달성한 점수에 대한 시스템 데이터를 수신하기 위해 매일 동기화됩니다.

### <a name="key-scenarios"></a>주요 시나리오

- [현재 점수 확인](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [점수를 사용자와 같은 조직과 비교](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [개선 작업 보기 및 작업 계획 결정](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [조사 또는 구현을 위한 작업 흐름 시작](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)

### <a name="how-improvement-actions-are-scored"></a>개선 작업 점수가 있는 방법

각 개선 작업은 10포인트 이하의 가치가 있으며 대부분 이진적인 점수로 점수가 매겨진 것입니다. 새 정책을 만들거나 특정 설정을 켜는 등 개선 작업을 구현하면 100%의 포인트를 얻게 됩니다. 다른 개선 작업의 경우 포인트가 전체 구성의 백분율로 부여됩니다.

예를 들어 다단계 인증을 통해 모든 사용자를 보호하여 개선 작업 상태는 10포인트가 됩니다. 총 사용자 100명 중 50명만 보호되어 있으므로 부분 점수가 5점(보호된 50/ 총 100 * 10 max pts = 5 pts)으로 표시됩니다.

### <a name="products-included-in-secure-score"></a>보안 점수에 포함된 제품

현재 다음 제품에 대한 권장 사항이 있습니다.

- Microsoft 365(Exchange Online)
- Azure Active Directory
- 엔드포인트용 Microsoft Defender
- ID용 Microsoft Defender
- 클라우드 앱 보안
- Microsoft Teams

권장 사항 보안 제품에 대한 자세한 계획은 곧 출시될 예정입니다. 권장 사항은 각 제품과 연결된 모든 공격 표면을 다루지 않지만 좋은 기준선입니다. 제3자 또는 대체 완화에서 다루는 개선 작업을 표시할 수도 있습니다.

### <a name="security-defaults"></a>보안 기본값

Microsoft Secure Score는 일반적인 공격에 대해 미리 구성된 보안 설정으로 조직을 보다 [쉽게](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)보호할 수 있도록 Azure Active Directory 보안 기본값을 지원하기 위해 개선 작업을 업데이트했습니다.

보안 기본값을 설정하면 다음과 같은 개선 작업에 대한 전체 점수가 수여됩니다.

- 모든 사용자가 보안 액세스를 위해 다단계 인증을 완료할 수 있도록 합니다(9포인트).
- 관리 역할에 MFA 필요(10포인트)
- 레거시 인증을 차단하는 정책 사용(7포인트)

>[!IMPORTANT]
>보안 기본값에는 "로그인 위험 정책" 및 "사용자 위험 정책" 개선 작업과 유사한 보안을 제공하는 보안 기능이 포함됩니다. 보안 기본값 위에 이러한 정책을 설정하는 대신 상태를 "대체 완화를 통해 해결되었습니다."로 업데이트하는 것이 좋습니다.

## <a name="required-permissions"></a>필요한 사용 권한

Microsoft 보안 점수에 액세스할 수 있는 권한을 부여하려면 보안 점수에서 다음 역할 중 하나를 할당해야 Azure Active Directory.

### <a name="read-and-write-roles"></a>역할 읽기 및 쓰기

읽기 및 쓰기 액세스를 사용하면 변경을 통해 보안 점수와 직접 상호 작용할 수 있습니다. 다른 사용자에게 읽기 전용 액세스 권한을 할당할 수도 있습니다.

* 전역 관리자
* 보안 관리자
* Exchange 관리자
* SharePoint 관리자

### <a name="read-only-roles"></a>읽기 전용 역할

읽기 전용 액세스를 사용하면 개선 작업, 점수 영역 편집 또는 사용자 지정 비교 편집에 대한 상태 또는 메모를 편집할 수 없습니다.

* 헬프데스크 관리자
* 사용자 관리자
* 서비스 지원 관리자
* 보안 읽기 권한자
* 보안 운영자
* 전역 읽기 권한자

## <a name="risk-awareness"></a>위험 인식

Microsoft 보안 점수는 시스템 구성, 사용자 동작 및 기타 보안 관련 측정값을 기반으로 보안의 수식 요약입니다. 시스템 또는 데이터가 침해될 가능성에 대한 절대 측정은 아니며, 대신 Microsoft 환경에서 보안 제어를 채택한 정도를 나타내며 위반 위험을 완화하는 데 도움이 될 수 있습니다. 온라인 서비스가 보안 위반으로부터 보호되지 않는 것은 아니며 보안 점수는 어떤 방식으로든 보안 위반에 대한 보장으로 해석되지 않습니다.

## <a name="we-want-to-hear-from-you"></a>의견을 보내 주세요.

문제가 있는 경우 보안, 개인 정보 보호 및 규정 준수 커뮤니티에 게시하여 & [알려주세요.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 커뮤니티를 모니터링하고 있으며 도움을 제공할 것입니다.

## <a name="related-resources"></a>관련 리소스

- [보안 상태 평가](microsoft-secure-score-improvement-actions.md)
- [Microsoft 보안 점수 기록 추적 및 목표 충족](microsoft-secure-score-history-metrics-trends.md)
- [향후 계획](microsoft-secure-score-whats-coming.md)
- [새로운 기능](microsoft-secure-score-whats-new.md)
