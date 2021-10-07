---
title: Project Server 2010 지원 종료 로드맵
ms.author: efrene
author: efrene
manager: pamg
ms.date: 04/14/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: IT_ProjectAdmin
search.appverid:
- MET150
- ZPJ120
- PJU120
- PJW120
description: 2021년 4월 13일 Project Server 2010에 대한 지원이 종료됩니다. 이 문서를 가이드로 사용하여 Project Online 또는 최신 버전의 Project 서버로 업그레이드할 수 있습니다.
ms.openlocfilehash: 9d04df22af0a0614270907f4ad4026324b026211
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60213328"
---
# <a name="project-server-2010-end-of-support-roadmap"></a>Project Server 2010 지원 종료 로드맵

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

Project Server 2010은 **2021년 4월 13일** 지원이 종료됩니다. 이 날짜는 2020년 10월 13일의 이전 지원 종료 날짜로부터 연장됩니다. 현재 Project Server 2010을 사용하고 있는 경우 이러한 관련 제품에는 다음과 같은 지원 종료 날짜가 있습니다.

|제품 |지원 종료 날짜|
|---|---|
|Project 2010 Standard|2020년 10월 13일|
|Project 2010 Professional|2020년 10월 13일|

지원 종료에 대한 자세한 내용은 [Upgrade from Office servers and client products을 참조하십시오.](plan-upgrade-previous-versions-office.md)

## <a name="what-does-end-of-support-mean"></a>지원 *종료는 무엇을 의미하나요?*

거의 모든 Microsoft 제품에는 지원 수명 주기가 있으며, 이 기간 동안에는 새로운 기능, 버그 수정 및 보안 업데이트가 있습니다. 이 수명 주기는 일반적으로 제품의 초기 릴리스부터 10년 동안 지속됩니다. 이 수명 주기의 끝을 제품의 지원 종료라고 합니다. Project Server 2010이 2021년 4월 13일 지원 종료에 도달하면 Microsoft는 더 이상 다음을 제공하지 않습니다.

- 발생할 수 있는 문제에 대한 기술 지원

- 검색된 문제에 대한 버그 수정으로, 서버의 안정성과 사용 가능성에 영향을 줄 수 있습니다.

- 검색된 취약점에 대한 보안 수정으로 서버가 보안 위반에 취약해질 수 있습니다.

- 표준 시간대 업데이트.

이 Project Server 2010 설치는 계속 실행됩니다. 그러나 이전에 나열된 변경 내용으로 인하여 가능한 한 빨리 Project 서버 2010에서 마이그레이션하는 것이 좋습니다.

## <a name="what-are-my-options"></a>내 옵션은 무엇입니까?

마이그레이션 옵션은 다음과 같습니다.

- 마이그레이션을 Project Online

- 최신 버전의 Project Server로 마이그레이션(Project Server 2019)

다음은 Project 서버 2010에 대한 지원이 종료되지 않도록 할 수 있는 두 가지 경로입니다.

![Project Server 2010 업그레이드 경로입니다.](../media/project-server-2010-end-of-support/project-server-2010-end-of-support-timeline.png)

|Server 2019로 마이그레이션하는 Project 이유는 무엇입니까?|마이그레이션을 선호하는 이유는 Project Online?|
|---|---|
|비즈니스 규칙은 클라우드에서 비즈니스를 운영하지 못하도록 제한합니다.  <br/><br/>  환경에 대한 업데이트를 제어해야 합니다.|모바일 또는 원격 사용자가 있습니다.<br/><br/>  사내 서버를 마이그레이션하는 데 들이는 비용은 중요한 문제입니다(하드웨어, 소프트웨어, 구현하는 데 들이는 시간 및 노력). <br/><br/>  마이그레이션 후 내 환경을 유지 관리하는 데 들이는 비용이 중요합니다(예: 자동 업데이트, 보장된 작업 시간 등).|

> [!NOTE]
> 마이그레이션 옵션에 대한 자세한 내용은 [Resources to help you upgrade from Office servers and clients을 참조하십시오.](upgrade-from-office-2010-servers-and-products.md) Project Server와 Project 동일한 리소스 풀을 공유할 수 Project Online 서버는 하이브리드 구성을 지원하지 않습니다.

### <a name="what-are-my-options-for-project-client"></a>클라이언트에 대한 내 옵션은 Project 무엇입니까?

Project Professional 2010 또는 Project Standard 사용하는 경우 옵션은 다음과 같습니다.

- 최신 버전의 Project Professional 또는 Project Standard
- 웹용 Project Online 같은 Project 솔루션으로 이동

#### <a name="move-to-a-newer-version-of-project-client"></a>최신 버전의 클라이언트로 Project 이동

Project Standard 2010에서 마이그레이션하는 경우 최신 버전의 Project Standard(Project Standard 2016 또는 Project Standard 2019)로 이동할 수 있습니다. 최신 기능을 활용하기 위해 최신 버전으로 이동하는 것이 좋습니다. 최신 버전(Project Standard 2016)으로 마이그레이션하면 더 빨리 다시 마이그레이션해야 합니다.

마찬가지로 Project Professional 2010에서 마이그레이션하는 경우 최신 버전(Project Professional 2019 또는 Project Professional 2016)으로 이동할 수 있습니다. 가능하면 최신 버전으로 이동하십시오. Project Professional 사용하여 Project Server에 연결하는 경우 사용하는 Project Professional Server 버전과 연결하는 Project Professional Project 버전으로 마이그레이션해야 합니다.

Project Professional 2010 사용자는 구독 기반 버전의 Project Online 2019인 Project Professional 클라이언트로 마이그레이션할 수도 있습니다. 이 구독은 Project 플랜 3 Project 플랜 5 포함되어 있습니다.

#### <a name="move-to-an-online-solution"></a>온라인 솔루션으로 이동

또한 2010 또는 Project Professional 2010 또는 Project Standard 2010에서 구독 기반 온라인 Project 마이그레이션할 수도 있습니다. Project 플랜 3 계획 5에는 웹용 Project Online 및 최신 클라우드 Project [포함됩니다.](https://support.office.com/article/what-can-you-do-with-project-for-the-web-b30f5442-be5f-43d2-9072-c95bff778ea1) 둘 다 탐색할 수 있는 새로운 기능과 이점을 제공합니다.

기능 및 라이선스에 대한 자세한 내용은 Microsoft Project [설명을 참조하세요.](/office365/servicedescriptions/project-online-service-description/project-online-service-description)

## <a name="important-considerations-for-migrating-from-project-server-2010"></a>Project Server 2010에서 마이그레이션할 때의 중요한 고려 사항

Project Server 2010에서 마이그레이션할 계획인 경우 다음을 고려하십시오.

- **Microsoft 솔루션 공급자의** 도움을 받을 수 있습니다. Project Server 2010에서 업그레이드하는 것이 과제가 될 수 있습니다. 많은 준비와 계획이 필요합니다. 원래 Server 2010을 설치한 사람이 아니어도 Project 있습니다. Microsoft 솔루션 공급자는 Server 2019로 마이그레이션할지 또는 Project Microsoft 솔루션 공급자를 지원할 Project Online. Microsoft 솔루션 공급자 센터에서 솔루션 [공급자를 검색합니다.](https://go.microsoft.com/fwlink/p/?linkid=841249)

- **사용자 지정** 계획 - Project Server 2010 환경의 사용자 지정은 Project Server 2019 또는 Project Online. 버전 간에는 서버 Project 크게 차이가 있습니다. 또한 버전에서 사용하는 필수 운영 체제, 데이터베이스 서버 및 웹 브라우저는 서로 다릅니다. 새 환경에서 사용자 지정을 테스트하거나 다시 만들 수 있는 방법에 대한 계획을 세워야 합니다. 이 기회를 통해 특정 사용자 지정이 여전히 필요한지 확인할 수 있습니다. 자세한 내용은 [Create a plan for current customizations during upgrade to SharePoint 2013를 참조하십시오.](/SharePoint/upgrade-and-update/create-a-plan-for-current-customizations-during-upgrade-to-sharepoint-2013)

- **시간 및 인내** - 업그레이드 계획, 실행 및 테스트에는 상당한 시간 및 노력이 필요합니다( 특히 Project Server 2019로 업그레이드하는 경우). Project Server 2010에서 Project Server 2019로 마이그레이션하는 경우 먼저 Project Server 2013으로 마이그레이션하고 데이터를 확인한 다음 Project Server 2016 서버로 마이그레이션한 다음 Project Server 2019로 마이그레이션해야 합니다. Microsoft 솔루션 공급자에 문의하여 지원할 기간 및 예상 비용을 확인할 수 있습니다.

## <a name="migrate-to-project-online"></a>마이그레이션을 Project Online

Project Server 2010에서 Project Online 마이그레이션하기로 선택한 경우 다음 단계에 따라 프로젝트 계획 데이터를 수동으로 마이그레이션할 수 있습니다.

1. 서버 2010에서 Project 계획을 .mpp 형식으로 저장합니다.

2. Project Professional 2016, Project Professional 2019 또는 Project Online 데스크톱 클라이언트를 사용하여 각 .mpp 파일을 연 다음 파일을 저장하여 Project Online.

필요한 사용자 정의 PWA Enterprise 달력과 같은 Project Online 수동으로 구성을 만들 수 있습니다. Microsoft 솔루션 공급자도 이 프로세스에 도움을 줄 수 있습니다.

주요 리소스:

|리소스|설명|
|---|---|
|[Project Online 시작](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11)|설치 및 사용 Project Online|
|[Project Online 서비스 설명](/office365/servicedescriptions/project-online-service-description/project-online-service-description)|사용 가능한 여러 Project Online 대한 정보|

## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>최신 버전의 Project 서버로 마이그레이션

사용자 환경으로 마이그레이션하여 최상의 가치와 사용자 환경을 얻을 수 Project Online. 그러나 일부 조직에서는 프로젝트 데이터를 사내에 보관해야 하는 경우도 있습니다. 프로젝트 데이터를 Project Server 2010 환경을 Project Server 2013, Project Server 2016 또는 Project Server 2019로 마이그레이션할 수 있습니다.

마이그레이션할 수 없는 경우 Project Online Server 2019로 마이그레이션하는 Project 좋습니다. Project Server 2019에는 이전 릴리스의 Project 주요 기능이 포함되어 있습니다. 또한 일부 기능은 Project Online 사용 가능한 환경과 가장 Project Online.

각 마이그레이션을 완료한 후 데이터가 성공적으로 마이그레이션 지 확인 합니다.

> [!NOTE]
> 사내 솔루션으로 제한되어 있으며 Project Server 2013으로만 마이그레이션하는 것이 좋습니다. 이 버전에는 몇 년 동안의 지원 기간만 남게 됩니다. 2023년 10월 13일 Project Server 2013의 지원 종료 날짜입니다. 지원 종료 날짜에 대한 자세한 내용은 Microsoft 제품 수명 [주기 정책을 참조하세요.](/lifecycle/)

### <a name="how-do-i-migrate-to-project-server-2019"></a>Server 2019로 마이그레이션하는 Project 방법

Project Server 2010과 Project Server 2019의 아키텍처 차이로 인해 직접 마이그레이션 경로가 차단됩니다. 따라서 Project Server 2019에 도달할 때까지 Project Server 2010 데이터를 각 Project 마이그레이션해야 합니다. Project Server 2019로 업그레이드하는 Project 단계:

1. 2013에서 Project 마이그레이션합니다.

2. Project 2013에서 2013으로 Project Server 2016.

3. 2019에서 Project Server 2016 Project 마이그레이션합니다.

각 마이그레이션을 완료한 후 데이터가 성공적으로 마이그레이션 지 확인 합니다.

### <a name="step-1-migrate-to-project-server-2013"></a>1단계: Project Server 2013으로 마이그레이션

Project Server 2010에서 Project Server 2013으로 업그레이드하는 자세한 내용은 Upgrade [to Project Server 2013을 참조하십시오.](/project/upgrade-to-project-server-2016)

주요 리소스:

- [Project Server 2013 업그레이드 프로세스 개요](/project/upgrade-to-project-server-2016)

  Project Server 2010에서 Project Server 2013으로 업그레이드하는 방법을 간략하게 소개합니다.
- [Project Server 2013으로 업그레이드 계획](/project/plan-for-upgrade-to-project-server-2016)

  시스템 요구 사항을 포함하여 Project Server 2010에서 Project Server 2013으로 업그레이드할 때의 계획 고려 사항을 확인합니다.

- [Project Server 2013의](/project/what-s-new-in-project-server-2013-upgrade) 새로운 업그레이드에는 다음을 비롯한 이 버전에 대한 중요한 변경 내용이 다수되어 있습니다.

  - 2013 Server 2013에는 현재 Project 없습니다. 데이터베이스 연결 방법은 Project Server 2013에서 Project 방법입니다.

  - 업그레이드 프로세스에서는 Project Server 2010 데이터를 Project Server 2013 형식으로 변환할 뿐만 아니라 4개의 Project Server 2010 데이터베이스를 단일 Project Web App 데이터베이스로 통합합니다.

  - SharePoint Server 2013과 Project Server 2013은 모두 이전 버전에서 클레임 기반 인증으로 변경되었습니다. 클래식 인증을 사용하는 경우 업그레이드할 때 이를 고려해야 합니다. 자세한 내용은 [Migrate from classic-mode to claims-based authentication in SharePoint](/sharepoint/upgrade-and-update/migrate-from-classic-mode-to-claims-based-authentication-in-sharepoint-2013).

주요 리소스:

- [Project Server 2013으로의 업그레이드 프로세스 개요](/project/overview-of-the-project-server-2016-upgrade-process)

- [데이터베이스 및 Project Web App 사이트 모음 업그레이드(Project Server 2013)](/project/upgrading-to-project-server-2016)

- [Microsoft Project 서버 업그레이드 프로세스 다이어그램](https://go.microsoft.com/fwlink/p/?linkid=841270)

- [서버 2010에서 Project 2013으로의 뛰어난 데이터베이스 통합(8단계로 마이그레이션)](https://go.microsoft.com/fwlink/p/?linkid=841271)

### <a name="step-2-migrate-to-project-server-2016"></a>2단계: 마이그레이션으로 Project Server 2016

Project Server 2013으로 이동하고 데이터가 성공적으로 마이그레이션된 것을 확인한 후 다음 단계는 마이그레이션을 Project Server 2016.

자세한 내용은 [Upgrade to Project Server 2016.](/Project/upgrade-to-project-server-2016)

주요 리소스:

- [Project Server 2016 업그레이드 프로세스 개요](/Project/overview-of-the-project-server-2016-upgrade-process)

  Project Server 2013에서 서버로 업그레이드하기 위해 Project Server 2016.

- [Project Server 2016으로의 업그레이드 계획](/Project/plan-for-upgrade-to-project-server-2016)

  Project Server 2013에서 서버로 업그레이드할 때 고려할 계획 Project Server 2016.

[Project Server 2016 업그레이드에](/project/plan-for-upgrade-to-project-server-2016#thingknow) 대해 알아야 할 사항은 다음을 포함해 이 버전으로의 업그레이드를 위한 중요한 변경 사항을 다 포함합니다.

- Project Server 2016 환경을 만들 때 Project Server 2016 설치 파일은 SharePoint Server 2016에 포함되어 있습니다. 자세한 내용은 [Deploy Project Server 2016.](/project/deploy-project-server-2016)

- 자원 계획은 2016년 9월에 Project Server 2016. Project Server 2013 리소스 계획은 Project Server 2016 및 리소스 계약으로 Project Online. 자세한 [내용은 개요: 리소스](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) 계약을 참조하세요.

### <a name="step-3-migrate-to-project-server-2019"></a>3단계: Project Server 2019로 마이그레이션

Project Server 2016 마이그레이션하고 데이터가 성공적으로 마이그레이션된 것을 확인한 후 다음 단계는 데이터를 Project 서버 2019로 마이그레이션하는 것입니다.

Project Server 2016 Server 2019로 업그레이드하기 위해 Project 필요한 작업을 [알아보하려면 Upgrade to Project Server 2019을 참조합니다.](/Project/upgrade-to-project-server-2016)

주요 리소스:

- [Project Server 2019 업그레이드 프로세스 개요](/project/overview-of-the-project-server-2019-upgrade-process)

  Project Server 2013에서 서버로 업그레이드하기 위해 Project Server 2016.

- [Project Server 2019로의 업그레이드 계획](/project/plan-for-upgrade-to-project-server-2019)

  Project Server 2016 Server 2019로 업그레이드하기 위한 Project 고려 사항을 살펴보아야 합니다.

- [Server 2019 업그레이드에 대해 Project 알아야 할 것](/project/plan-for-upgrade-to-project-server-2016)<br/><br/>다음을 포함해 이 버전으로의 업그레이드를 위한 중요한 변경 내용에 대해 자세히 알아보습니다.

  - 업그레이드 프로세스는 데이터를 Project Server 2016 콘텐츠 데이터베이스로 SharePoint Server 2019 마이그레이션합니다.  Project 서버 2019는 더 이상 Project 서버 팜에 자체 SharePoint 만듭니다.

  - 업그레이드 후에 변경된 몇 가지 사항을 Project Web App.  자세한 내용은 [What's new in Project Server 2019을 참조합니다.](/project/what-s-new-for-it-pros-in-project-server-2019#PWAChanges)

**기타 리소스:**

- [Project Online 서비스 설명:](/office365/servicedescriptions/project-online-service-description/project-online-service-description)Project Server 2016 및 서비스에 포함된 포트폴리오 관리 Project Online Premium.

- [Microsoft Office Project Portfolio Server 2010 마이그레이션 가이드](https://go.microsoft.com/fwlink/p/?linkid=841279)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Office 2010 클라이언트 및 서버 및 Windows 옵션 요약

Office 2010 클라이언트 및 서버와 Windows 7에 대한 업그레이드, 마이그레이션 및 클라우드 옵션으로 이동에 대한 시각적 요약은 [지원 종료 포스터](../downloads/Office2010Windows7EndOfSupport.pdf)를 참조하세요.

[![2010 클라이언트 및 Office 지원 종료 및 Windows 7 포스터.](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

이 포스터는 기본 경로 및 옵션 지원이 강조 표시된 Office 2010 클라이언트 및 서버 제품 및 Windows 7에 대한 지원이 종료되지 않도록 방지하기 위해 취할 수 있는 다양한 Microsoft 365 Enterprise 보여 주며,

이 [포스터를](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) 다운로드하여 편지형, 법률형 또는 타블로이드(11 x 17) 형식으로 인쇄할 수도 있습니다.

## <a name="related-topics"></a>관련 항목

[SharePoint 2010에서 업그레이드](upgrade-from-sharepoint-2010.md)

[Office 2010 서버 및 클라이언트에서 업그레이드](upgrade-from-office-2010-servers-and-products.md)
