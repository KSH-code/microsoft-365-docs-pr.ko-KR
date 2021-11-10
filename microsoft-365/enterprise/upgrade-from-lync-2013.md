---
title: Lync Server 2013에서 업그레이드
ms.author: serdars
author: serdarsoysal
manager: serdars
ms.date: 11/10/2021
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
ms.collection:
- Ent_O365
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: Lync Server 2013에서 업그레이드할 정보 및 리소스를 찾아야 합니다. 지원은 2023년 4월 11일로 종료됩니다.
ms.openlocfilehash: a770ce6acab4320bc84e920b1c527e9c63e72bbb
ms.sourcegitcommit: 16e3a6e6df253de1153e46d058941cd9a2bbf2b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2021
ms.locfileid: "60889906"
---
# <a name="upgrading-from-lync-server-2013"></a>Lync Server 2013에서 업그레이드

Microsoft Lync Server 2013은 **2023년 4월 11일부터** 지원이 종료됩니다. 이 문서에서는 온-프레미스에서 기존 Lync Server 배포를 Microsoft Teams 비즈니스용 Skype 리소스를 제공합니다.

## <a name="what-is-end-of-support"></a>지원이 *종료된 것은 무엇입니까?*

대부분의 Microsoft 제품에는 새로운 기능, 버그 수정, 보안 수정 등 지원 수명 주기가 있습니다. 지원 종료 날짜가 지난 후 제품 작동이 중지되지 않지만 Microsoft는 더 이상 다음을 제공하지 않습니다.

- 발생할 수 있는 문제에 대한 기술 지원

- 서버의 안정성과 사용 가능성에 영향을 줄 수 있는 문제에 대한 버그 수정

- 서버가 보안 위반에 취약해질 수 있는 취약점에 대한 보안 수정

- 표준 시간대 업데이트.

즉, 제품에 대한 추가 업데이트, 패치 또는 수정이 없습니다(보안 패치/수정 포함). Microsoft 지원은 지원 노력을 최신 버전으로 완전히 전환할 것입니다.

## <a name="plan-ahead"></a>미리 계획

제품 수명 주기 사이트에서 종료 날짜를 [확인 합니다.](/lifecycle/products/lync-server-2013) 이러한 날짜를 염두에 두어 업그레이드 또는 마이그레이션을 계획합니다. 제품이 나열된 날짜에 *작동을* 중지하지 않습니다. 그러나 해당 날짜 이후에는 설치가 더 이상 패치되지 않습니다. 따라서 제품의 다음 버전으로의 매끄러운 전환을 계획할 수 있습니다. 아래 표에는 사용 가능한 옵션이 나열됩니다.

|지원 제품 종료|지원|권장|
|---|---|---|
|Lync Server 2013|2015 비즈니스용 Skype 서버 2019로 업그레이드|Microsoft Teams로 업그레이드

## <a name="whats-next"></a>다음 작업

업그레이드하는 것이 Microsoft Teams. Microsoft Teams Lync Server의 기능을 확장하여 채팅, 모임, 통화, 공동 작업, 앱 통합 및 파일 저장소를 단일 인터페이스로 통합합니다. Teams 통해 사용자가 작업 수행 방법을 간소화하고 사용자 만족도를 개선하고 비즈니스 결과를 가속화할 수 있습니다. Microsoft는 Teams의 기능을 지속적으로 확장하여 사용자가 새 방식으로 통신 및 협업하고, 조직 및 지리적 장애를 분석하며, 프로세스 및 의사 결정의 효율성을 높이도록 합니다.

업그레이드할 수 없는 경우 Microsoft Teams 2015 또는 2019로 업그레이드할 비즈니스용 Skype 서버 있습니다. 이 두 제품 모두 2025년 10월 14일 지원이 종료될 예정인 것을 알아야 합니다. 자세한 내용은 다음 지원 수명 주기 페이지를 참조하세요.

- [비즈니스용 Skype 서버 2015 지원 수명 주기 정보](/lifecycle/products/skype-for-business-server-2015)
- [비즈니스용 Skype 서버 2019 지원 수명 주기 정보](/lifecycle/products/skype-for-business-server-2019)

### <a name="upgrade-to-microsoft-teams"></a>Microsoft Teams로 업그레이드

이 가이드에서는 프레미스 배포에서 Microsoft Teams 자세한 지침을 제공합니다. 먼저 몇 가지 주요 기술 요구 사항을 설명해 보시고, 사용자를 하이브리드 연결로 이동하는 데 사용할 수 있는 하이브리드 연결을 설정해야 Teams. [하이브리드 연결 계획은](/SkypeForBusiness/hybrid/plan-hybrid-connectivity) 하이브리드 설정에 대한 개요를 제공합니다. 이 문서에서는 모든 비즈니스용 Skype Lync Server 2013에도 적용됩니다. Lync Server 2013 관련 세부 정보는 서버 버전 요구 사항 섹션을 참조하세요. [](/SkypeForBusiness/hybrid/plan-hybrid-connectivity#server-version-requirements)

또한 Lync Server 2013을 완전히 최신으로 배포해야 합니다. [Lync Server 2013의](https://support.microsoft.com/topic/updates-for-lync-server-2013-a2a042ac-79f0-2665-7453-0a541fb25164) 모든 최신 업데이트 목록을 게시합니다. 그러나 다음 업데이트는 Lync Server 2013으로의 업그레이드를 위한 전제 Microsoft Teams.

- [Lync Server 2013용 2021년 9월 누적 업데이트 5.0.8308.1149,](https://support.microsoft.com/topic/september-2021-cumulative-update-5-0-8308-1149-for-lync-server-2013-core-components-6755903a-fc9a-44d2-b835-2a6d01f14043)핵심 구성 요소: 이 업데이트는 온-프레미스 사용자를 서버로 이동하는 데 사용되는 cmdlet에 대한 OAuth 인증 프로토콜로 `Move-CSUser` Microsoft Teams.

Lync의 사용자 Microsoft Teams 훨씬 더 다양하고 우수하기는 하지만 Lync도 크게 다릅니다. 따라서 조직과 사용자도 조직의 빠른 채택을 보장할 수 있도록 준비해야 Microsoft Teams. 조직을 준비하고, 업그레이드를 계획하고, 성공적인 롤아웃을 보장하는 방법에 대한 다양한 Teams 있습니다. 

**기술 정보, 교육 [리소스Teams](/MicrosoftTeams/upgrade-skype-teams)** Ignite 세션에 대한 링크, 사용 가능한 도움말 리소스, 사례 연구 등도 찾을 수 있는 Teams 업그레이드 포털에서 시작하는 것이 좋습니다.

:::image type="content" source="../media/teams-upgrade-portal.png" alt-text="업그레이드 포털의 Teams 스크린샷":::

### <a name="upgrade-to-skype-for-business-server"></a>비즈니스용 Skype 서버 업그레이드

업그레이드할 비즈니스용 Skype 서버 경로는 업그레이드할 버전에 따라 다릅니다. 비즈니스용 Skype 서버 2015에서는 Lync Server 2013의 현재 업그레이드가 지원됩니다. 반면에 비즈니스용 Skype 서버 2019로 업그레이드하려면 먼저 비즈니스용 Skype 서버 2019를 Lync Server 2013 조직에 도입한 다음 작업을 새 서버로 전송해야 합니다. 

고려해야 할 한 가지 중요한 점은 각 제품에 대한 현재 지원 단계인 비즈니스용 Skype 2019는 기본 지원에 있으며 비즈니스용 Skype 2015는 현재 확장 지원 중입니다.  따라서 2019년 8월로 업그레이드하는 비즈니스용 Skype 서버 좋습니다. 기본 지원과 확장 지원의 차이점에 대한 자세한 내용은 [고정 수명 주기 정책을 참조합니다.](/lifecycle/policies/fixed)

각 업그레이드 시나리오에 대한 자세한 내용은 다음 리소스를 참조하십시오.

- [2019년 비즈니스용 Skype 서버 업그레이드](/skypeforbusiness/migration/migration-to-skype-for-business-server-2019)
- [2015 비즈니스용 Skype 서버 업그레이드](/skypeforbusiness/deploy/upgrade-to-skype-for-business-server)
