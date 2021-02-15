---
title: Microsoft Secure Score
description: Microsoft 365 보안 센터의 Microsoft 보안 점수, 보안 자세를 개선하는 방법 및 보안 관리자가 기대할 수 있는 기능을 기술합니다.
keywords: Microsoft 보안 점수, 보안 점수, Office 365 보안 점수, Microsoft 보안 점수, Microsoft 365 보안 센터, 개선 작업
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
ms.openlocfilehash: 39abcbde82c2902b091b42db3dbc8e1ee2cbd924
ms.sourcegitcommit: 8b3ff6e9f8931327b6f0541fd882107687cd123e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2021
ms.locfileid: "49942793"
---
# <a name="microsoft-secure-score"></a>Microsoft 보안 점수

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Microsoft 보안 점수는 조직의 보안 자세를 측정한 것으로, 수치가 높을수록 개선 작업이 더 많이 수행됩니다. Microsoft https://security.microsoft.com/securescore [365](overview-security-center.md)보안 센터에서 찾을 수 있습니다.

보안 점수 권장 사항을 따라 조직을 위협으로부터 보호할 수 있습니다. Microsoft 365 보안 센터의 중앙 집중식 대시보드에서 조직은 Microsoft 365 ID, 앱 및 장치의 보안을 모니터링하고 작업할 수 있습니다.

보안 점수는 조직에 도움이 됩니다.  

* 조직의 보안 상태의 현재 상태를 보고합니다.
* 검색 가능성, 가시성, 지침 및 제어 기능을 제공하여 보안의 보안을 개선합니다.  
* 벤치마크와 비교하여 KP(핵심 성과 지표)를 설정합니다.

조직은 메트릭 및 추세의 강력한 시각화, 다른 Microsoft 제품과의 통합, 유사한 조직과의 점수 비교 등의 강력한 시각화에 액세스할 수 있습니다. 또한 타사 솔루션에서 권장 작업을 해결한 경우 점수가 반영될 수 있습니다.

![보안 점수 홈페이지](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a>작동 방식

다음 작업에 대한 포인트가 부여됩니다.

- 권장 보안 기능 구성
- 보안 관련 작업 수행
- 타사 응용 프로그램 또는 소프트웨어를 사용하여 개선 작업 해결 또는 대체 완화

일부 개선 작업은 완전히 완료될 때만 포인트를 제공 합니다. 일부는 일부 장치 또는 사용자에 대해 완료된 경우 부분 지점을 제공합니다. 개선 작업 중 하나를 제정할 수 없는 경우 위험 또는 남은 위험을 수용할 수 있습니다.

지원되는 Microsoft 제품 중 하나의 라이선스가 있는 경우 해당 제품에 대한 권장 사항을 볼 수 있습니다. 라이선스 버전, 구독 또는 계획에 관계없이 제품에 대해 가능한 전체 개선된 기능 집합이 표시되어 있습니다. 이렇게 하면 보안 모범 사례를 이해하고 점수를 향상시킬 수 있습니다. 보안 점수로 표현되는 절대 보안 자세는 조직이 특정 제품에 대해 소유하는 라이선스에 상관없이 동일하게 유지 됩니다. 보안은 사용 가능성과 균형을 유지해야 하며, 모든 권장이 사용자 환경에 작동할 수 있는 것은 아니라는 사실에 유의하십시오.

점수는 시각화 및 개선 작업 페이지에 제공된 정보를 반영하기 위해 실시간으로 업데이트됩니다. 또한 보안 점수는 매일 동기화하여 각 작업의 달성한 점수에 대한 시스템 데이터를 수신합니다.

### <a name="key-scenarios"></a>주요 시나리오

- [현재 점수 확인](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [점수를 사용자와 같은 조직과 비교](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [개선 작업 보기 및 작업 계획 결정](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [조사 또는 구현을 위한 작업 흐름 시작](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)

### <a name="how-improvement-actions-are-scored"></a>개선 작업 점수가 기록된 방법

각 개선 작업은 10포인트 이하의 가치가 있으며 대부분의 점수는 이진수로 점수가 매겨진 것입니다. 새 정책을 만들거나 특정 설정을 켜는 등 개선 작업을 구현하는 경우 100%의 포인트를 얻게 됩니다. 다른 개선 작업의 경우 포인트는 총 구성의 백분율로 부여됩니다.

예를 들어 향상된 작업 상태는 다단계 인증으로 모든 사용자를 보호하여 10점을 얻게 됩니다. 총 사용자 100명 중 50명만 보호할 수 있으므로 부분 점수(50 보호/ 총 100개 * 10 max pts = 5pts)를 얻게 됩니다.

### <a name="products-included-in-secure-score"></a>보안 점수에 포함된 제품

현재 다음 제품에 대한 권장 사항이 있습니다.

- Microsoft 365(Exchange Online 포함)
- Azure Active Directory
- 엔드포인트용 Microsoft Defender
- ID용 Microsoft Defender
- 클라우드 앱 보안
- Microsoft Teams

다른 보안 제품에 대한 권장 사항은 곧 제공될 예정입니다. 권장 사항은 각 제품과 관련된 모든 공격 표면을 다루지 않지만 좋은 기준입니다. 또한 제3자 또는 대체 완화에 의해 적용된 개선 작업을 표시할 수도 있습니다.

### <a name="security-defaults"></a>보안 기본값

Microsoft Secure Score는 일반적인 공격에 대해 미리 구성된 보안 설정으로 조직을 보다 쉽게 보호할 수 있도록 [Azure Active Directory의](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)보안 기본값을 지원하기 위해 개선 작업을 업데이트했습니다.

보안 기본값을 설정하면 다음과 같은 개선 작업에 대한 전체 점수가 주어지게 됩니다.

- 모든 사용자가 보안 액세스를 위해 다단계 인증을 완료할 수 있도록 합니다(9포인트).
- 관리 역할에 MFA 필요(10포인트)
- 레거시 인증을 차단하는 정책 사용(7포인트)

>[!IMPORTANT]
>보안 기본값에는 "로그인 위험 정책" 및 "사용자 위험 정책" 개선 작업과 유사한 보안을 제공하는 보안 기능이 포함됩니다. 보안 기본값 위에 이러한 정책을 설정하는 대신 상태를 "대체 완화를 통해 해결되었습니다."로 업데이트하는 것이 좋습니다.

## <a name="required-permissions"></a>필요한 사용 권한

Microsoft 보안 점수에 액세스할 수 있는 권한을 부여하려면 Azure Active Directory에서 다음 역할 중 하나를 할당해야 합니다.

### <a name="read-and-write-roles"></a>역할 읽기 및 쓰기

읽기 및 쓰기 권한을 사용하면 변경을 통해 보안 점수와 직접 상호 작용할 수 있습니다. 다른 사용자에게 읽기 전용 액세스를 할당할 수도 있습니다.

* 전역 관리자
* 보안 관리자
* Exchange 관리자
* SharePoint 관리자
* 계정 관리자

### <a name="read-only-roles"></a>읽기 전용 역할

읽기 전용 액세스를 사용하면 개선 작업의 상태 또는 메모를 편집하거나, 점수 영역 편집 또는 사용자 지정 비교를 편집할 수 없습니다.

* 헬프데스크 관리자
* 사용자 관리자
* 서비스 관리자
* 보안 읽기 권한자
* 보안 운영자
* 전역 읽기 권한자

## <a name="risk-awareness"></a>위험 인식

Microsoft 보안 점수는 시스템 구성, 사용자 동작 및 기타 보안 관련 측정값을 기반으로 하는 보안의 수치 요약입니다. 이는 시스템 또는 데이터가 침해될 가능성에 대한 절대적인 측정치가 아니며, 그보다는 Microsoft 환경에서 보안 제어를 채택하여 위반 위험을 완화할 수 있는 범위를 나타내는 것입니다. 온라인 서비스가 보안 침해로부터 영향을 받는 것은 아니며 보안 점수는 어떤 방식으로든 보안 위반에 대한 보장으로 해석되지 않습니다.

## <a name="we-want-to-hear-from-you"></a>의견을 보내 주세요.

문제가 있는 경우 보안, 개인 정보 보호 및 규정 준수 커뮤니티에 & [알려주세요.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 커뮤니티를 모니터링하고 있으며 도움을 제공할 것입니다.

## <a name="related-resources"></a>관련 리소스

- [보안 상태 평가](microsoft-secure-score-improvement-actions.md)
- [Microsoft 보안 점수 기록 추적 및 목표 충족](microsoft-secure-score-history-metrics-trends.md)
- [향후 계획](microsoft-secure-score-whats-coming.md)
- [새로운 기능](microsoft-secure-score-whats-new.md)
