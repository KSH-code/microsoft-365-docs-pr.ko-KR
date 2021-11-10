---
title: Project Server 2013 지원 종료 로드맵
ms.author: serdars
author: serdarsoysal
manager: serdars
ms.date: 10/11/2021
audience: ITPro
ms.topic: conceptual
ms.prod: project-server-itpro
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: IT_ProjectAdmin
search.appverid:
- MET150
description: 2023년 4월 11일 Project Server 2013에 대한 지원이 종료됩니다. 이 문서를 가이드로 사용하여 Project Online 또는 최신 버전의 Project 서버로 업그레이드할 수 있습니다.
ms.openlocfilehash: 5a9ae38e819dfdb8f9cc2ca3719dccea2d33fa3e
ms.sourcegitcommit: 16e3a6e6df253de1153e46d058941cd9a2bbf2b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2021
ms.locfileid: "60889889"
---
# <a name="project-server-2013-end-of-support-roadmap"></a>Project Server 2013 지원 종료 로드맵

Project Server 2013은 **2023년 4월 11일** 지원이 종료됩니다. 현재 Project Server 2013을 사용하는 경우 Project 2013 데스크톱 앱도 지원 종료 날짜가 동일합니다.

## <a name="what-does-end-of-support-mean"></a>지원 *종료는 무엇을 의미하나요?*

거의 모든 Microsoft 제품에는 지원 수명 주기가 있으며, 이 기간 동안에는 새로운 기능, 버그 수정 및 보안 업데이트가 있습니다. 이 수명 주기는 일반적으로 제품의 초기 릴리스부터 10년 동안 지속됩니다. 이 수명 주기의 끝을 제품의 지원 종료라고 합니다. Project Server 2013이 2023년 4월 11일 지원 종료에 도달하면 Microsoft는 더 이상 다음을 제공하지 않습니다.

- 발생할 수 있는 문제에 대한 기술 지원

- 검색된 문제에 대한 버그 수정으로, 서버의 안정성과 사용 가능성에 영향을 줄 수 있습니다.

- 검색된 취약점에 대한 보안 수정으로 서버가 보안 위반에 취약해질 수 있습니다.

- 표준 시간대 업데이트.

이 Project Server 2013 설치는 계속 실행됩니다. 그러나 이전에 나열된 변경 내용 때문에 가능한 한 빨리 Project 서버 2013에서 마이그레이션하는 것이 좋습니다.

## <a name="what-are-my-options"></a>내 옵션은 무엇입니까?

마이그레이션 옵션은 다음과 같습니다.

- 마이그레이션을 Project Online

- 최신 버전의 Project 서버(Project Server Subscription Edition)로 마이그레이션

|Server 2019로 마이그레이션하는 Project 이유는 무엇입니까?|마이그레이션을 선호하는 이유는 Project Online?|
|---|---|
|비즈니스 규칙은 클라우드에서 비즈니스를 운영하지 못하도록 제한합니다.  <br/><br/>  환경에 대한 업데이트를 제어해야 합니다.|모바일 또는 원격 사용자가 있습니다.<br/><br/>  사내 서버를 마이그레이션하는 데 들이는 비용은 중요한 문제입니다(하드웨어, 소프트웨어, 구현하는 데 들이는 시간 및 노력). <br/><br/>  마이그레이션 후 내 환경을 유지 관리하는 데 들이는 비용이 중요합니다(예: 자동 업데이트, 보장된 작업 시간 등).|

> [!NOTE]
> Project 서버와 서버가 동일한 리소스 Project 수 Project Online 서버가 하이브리드 구성을 지원하지 않습니다.

## <a name="important-considerations-for-migrating-from-project-server-2013"></a>Project Server 2013에서 마이그레이션할 때의 중요한 고려 사항

Project Server 2013에서 마이그레이션할 계획인 경우 다음을 고려하십시오.

- **Microsoft 솔루션 공급자의** 도움을 받을 수 있습니다. Project Server 2013에서 업그레이드하는 것이 과제가 될 수 있습니다. 많은 준비와 계획이 필요합니다. 원래 Server 2013을 설치한 사람이 아니어도 Project 있습니다. Microsoft 솔루션 공급자는 Server Subscription Edition으로 마이그레이션할지 또는 Project Microsoft 솔루션 공급자를 지원할 Project Online. Microsoft 솔루션 공급자 센터에서 솔루션 [공급자를 검색합니다.](https://go.microsoft.com/fwlink/p/?linkid=841249)

- **시간 및 인내** - 업그레이드 계획, 실행 및 테스트는 특히 Server Subscription Edition으로 업그레이드하는 데 많은 Project 합니다. Project Server 2013에서 Project Server Subscription Edition으로 마이그레이션하는 경우 먼저 Project Server 2016 마이그레이션하고 데이터를 확인한 다음 Project Server Subscription Edition으로 마이그레이션해야 합니다. Microsoft 솔루션 공급자에 문의하여 지원할 기간 및 예상 비용을 확인할 수 있습니다.

## <a name="migrate-to-project-online"></a>마이그레이션을 Project Online

Project Server 2013에서 Project Online 마이그레이션하는 경우 다음 단계에 따라 프로젝트 계획 데이터를 수동으로 마이그레이션할 수 있습니다.

1. 서버 2013에서 Project 계획을 .mpp 형식으로 저장합니다.

2. Project Professional 2016, Project Professional 2019 또는 Project Online 데스크톱 클라이언트를 사용하여 각 .mpp 파일을 연 다음 파일을 저장하여 Project Online.

필요한 사용자 정의 PWA Enterprise 달력과 같은 Project Online 수동으로 구성을 만들 수 있습니다. Microsoft 솔루션 공급자도 이 프로세스에 도움을 줄 수 있습니다.

주요 리소스:

|리소스|설명|
|---|---|
|[Project Online 시작](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11)|설치 및 사용 Project Online|
|[Project Online 서비스 설명](/office365/servicedescriptions/project-online-service-description/project-online-service-description)|사용 가능한 여러 Project Online 대한 정보|

## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>최신 버전의 Project 서버로 마이그레이션

사용자 환경으로 마이그레이션하여 최상의 가치와 사용자 환경을 얻을 수 Project Online. 그러나 일부 조직에서는 프로젝트 데이터를 사내에 보관해야 하는 경우도 있습니다. 프로젝트 데이터를 Project Server 2013 환경을 Project Server 2016, Project Server 2019 또는 Project Server Subscription Edition으로 마이그레이션할 수 있습니다.

Project Online 마이그레이션할 수 없는 경우 이전 Project Server 릴리스의 주요 기능을 대부분 포함하는 Project Server Subscription Edition으로 마이그레이션하는 Project 좋습니다. 또한 일부 기능은 Project Online 사용 가능한 환경과 가장 Project Online. 고려해야 할 추가 요인은 다음과 같습니다.

- Project Server Subscription Edition에는 새로운 주 버전의 Project 릴리스할 필요가 없어진 지속적인 업데이트 모델이 도입되었습니다.
- 2019 Project Server 2016 2026년 7월 14일 지원이 종료될 예정입니다. 두 버전 중 하나를 마이그레이션하는 경우 3년 이내에 다른 업그레이드를 계획해야 합니다. 자세한 내용은 [2016 및 2019의](/lifecycle/products/project-server-2016) 지원 수명 주기 페이지를 [참조하세요.](/lifecycle/products/project-server-2019)

각 마이그레이션을 완료한 후 데이터가 성공적으로 마이그레이션 지 확인 합니다.

### <a name="how-do-i-migrate-to-project-server-subscription-edition"></a>Server Subscription Edition으로 마이그레이션하는 Project 방법

Project Server 2013과 Project Server Subscription Edition 간의 아키텍처 차이로 인해 직접 마이그레이션 경로가 차단됩니다. 따라서 먼저 Project Server 2013 데이터를 마이그레이션한 다음 Project Server 2016 Server Subscription Edition으로 Project 합니다. 

1. 마이그레이션을 Project Server 2016.

2. 서버에서 Project Server 2016 Server Subscription Edition으로 Project 마이그레이션합니다.

각 마이그레이션을 완료한 후 데이터가 성공적으로 마이그레이션 지 확인 합니다.

### <a name="step-1-migrate-to-project-server-2016"></a>1단계: 마이그레이션으로 Project Server 2016

Project Server 2013에서 2013으로 업그레이드하는 Project Server 2016 자세한 내용은 [Upgrade to Project Server 2016.](/project/upgrade-to-project-server-2016)

주요 리소스:

- [Project Server 2016 업그레이드](/project/upgrade-to-project-server-2016)프로세스 개요: Project Server 2013에서 업그레이드로 업그레이드하는 방법에 대한 간략한 개요를 Project Server 2016.
- Project Server 2016 업그레이드 [계획:](/project/plan-for-upgrade-to-project-server-2016)Project Server 2013에서 시스템 요구 사항을 포함하여 Project Server 2016 계획 고려 사항을 확인합니다.
- [업그레이드 Project Server 2016](/project/upgrading-to-project-server-2016): 업그레이드 프로세스에 대한 자세한 지침을 참조하세요.

### <a name="step-2-migrate-to-project-server-subscription-edition"></a>2단계: Project Server Subscription Edition으로 마이그레이션

마이그레이션 Project Server 2016 이동하고 데이터가 성공적으로 마이그레이션된 것을 확인한 후 다음 단계는 Project Server Subscription Edition으로 마이그레이션하는 것입니다.

자세한 내용은 [Upgrade to Project Server Subscription Edition을 참조하십시오.](/project/upgrade-project-server-subscription-edition)

주요 리소스:

- [Project Server Subscription Edition](/project/overview-project-server-subscription-edition-upgrade-process)업그레이드 프로세스 개요: Project Server 2013에서 업그레이드를 완료하기 위해 Project Server 2016.
- [Project Server Subscription Edition으로의](/Project/plan-upgrade-project-server-subscription-edition)업그레이드 계획: Project Server 2013에서 Project Server 2016.
- [Project Server Subscription Edition으로](/project/how-to-upgrade-project-server-subscription-edition)업그레이드: 업그레이드 프로세스에 대한 자세한 지침을 참조하세요.


