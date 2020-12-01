---
title: Project Server 2010 지원 종료 로드맵
ms.author: efrene
author: efrene
manager: pamg
ms.date: 04/14/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: IT_ProjectAdmin
search.appverid:
- MET150
- ZPJ120
- PJU120
- PJW120
description: Project Server 2010의 지원 종료는 4 월 13 2021 일에 종료 됩니다. 이 문서를 사용 하 여 Project Online으로 업그레이드 하는 방법 또는 온-프레미스 Project Server의 새 버전으로 업그레이드할 수 있습니다.
ms.openlocfilehash: 239b3d93cfa6a1184ea21225fa97732712b8eb14
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519705"
---
# <a name="project-server-2010-end-of-support-roadmap"></a>Project Server 2010 지원 종료 로드맵

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

Project Server 2010는 **2021 년 4 월 13 일** 에 지원 종료에 도달 합니다. 이 날짜는 이전의 지원 종료 날짜에서 2020 년 10 월 13 일까지 연장 되었습니다. 현재 Project Server 2010을 사용 하 고 있는 경우 이러한 관련 제품에는 다음과 같은 지원 종료 날짜가 포함 되어 있습니다.

|제품 |지원 종료 날짜|
|---|---|
|Project 2010 Standard|2020년 10월 13일|
|Project 2010 Professional|2020년 10월 13일|

지원 종료에 대 한 자세한 내용은 [Office 2010 서버 및 클라이언트 제품에서 업그레이드](plan-upgrade-previous-versions-office.md)를 참조 하세요.

## <a name="what-does-end-of-support-mean"></a>*지원이 끝나는* 것은 무엇을 의미 하나요?

거의 모든 Microsoft 제품에는 새로운 기능, 버그 수정 및 보안 업데이트가 제공 되는 지원 주기가 제공 됩니다. 이 수명 주기는 일반적으로 제품 초기 릴리스에서 10 년 동안 지속 됩니다. 이 수명 주기의 끝은 제품의 지원 종료 라고 합니다. Project Server 2010이 2021 지원 종료 되 면 Microsoft는 더 이상 다음을 제공 하지 않습니다.

- 발생할 수 있는 문제에 대 한 기술 지원

- 검색 된 문제와 서버의 안정성 및 유용성에 영향을 줄 수 있는 문제에 대 한 버그 수정

- 검색 되어 서버에서 보안 위반에 취약 해질 수 있는 취약성에 대 한 보안 수정

- 표준 시간대 업데이트

이 날짜 후에는 Project Server 2010의 설치가 계속 실행 됩니다. 그러나 이전에 나열 된 변경 사항으로 인해 가능한 한 빨리 Project Server 2010에서 마이그레이션하는 것이 좋습니다.

## <a name="what-are-my-options"></a>내 옵션 이란?

마이그레이션 옵션은 다음과 같습니다.

- Project Online으로 마이그레이션

- 새 온-프레미스 버전의 Project Server로 마이그레이션 (가능한 Project Server 2019)

다음은 Project Server 2010에 대 한 지원 종료를 방지 하기 위해 수행할 수 있는 두 가지 경로입니다.

![Project Server 2010 업그레이드 경로](../media/project-server-2010-end-of-support/project-server-2010-end-of-support-timeline.png)

|Project Server 2019로 마이그레이션하는 이유는 무엇 인가요?|Project Online으로 마이그레이션하는 이유는 무엇 인가요?|
|---|---|
|비즈니스 규칙 클라우드에서 내 비즈니스를 운영 하는 것을 제한 합니다.  <br/><br/>  내 환경에 대 한 업데이트를 제어 해야 합니다.|모바일 또는 원격 사용자가 있는 경우<br/><br/>  온-프레미스 서버를 마이그레이션하는 데 드는 비용은 중요 한 관심사 (즉, 구현에 있어 하드웨어, 소프트웨어, 시간 및 노력 등)입니다. <br/><br/>  마이그레이션 후에는 내 환경을 유지 관리 하기 위한 비용 (예: 자동 업데이트, 보장 된 가동 시간 등)이 중요 합니다.|

> [!NOTE]
> 마이그레이션 옵션에 대 한 자세한 내용은 [Office 2010 서버 및 클라이언트에서 업그레이드 하는 데 도움이](upgrade-from-office-2010-servers-and-products.md)되는 리소스를 참조 하십시오. Project Server 및 Project Online에서는 동일한 자원 그룹을 공유할 수 없으므로 Project Server에서는 하이브리드 구성을 지원 하지 않습니다.

### <a name="what-are-my-options-for-project-client"></a>Project 클라이언트에 대 한 내 옵션은 무엇입니까?

Project Professional 2010 또는 Project Standard 2010을 사용 중인 경우 옵션은 다음과 같습니다.

- 새 버전의 Project Professional 또는 Project Standard로 이동
- Project Online, 웹 프로젝트와 같은 온라인 솔루션으로 이동

#### <a name="move-to-a-newer-version-of-project-client"></a>최신 버전의 Project client로 이동

Project Standard 2010에서 마이그레이션하는 경우 최신 버전의 Project standard (Project Standard 2016 또는 Project Standard 2019)로 이동할 수 있습니다. 최신 기능을 활용할 수 있도록 최신 버전으로 이동 하는 것이 좋습니다. 최신 버전이 아닌 버전으로 마이그레이션하는 경우 (Project Standard 2016) 또한 더 빨리 마이그레이션해야 합니다.

마찬가지로 Project Professional 2010에서 마이그레이션하는 경우에도 최신 버전 (Project Professional 2019 또는 Project Professional 2016)으로 이동할 수 있습니다. 다시 한 번, 가능한 경우 최신 버전으로 이동 합니다. Project Professional을 사용 하 여 Project Server에 연결 하는 경우에는 사용 하는 Project Server 버전과 연결 되는 Project Professional 버전으로 마이그레이션해야 합니다.

Project Professional 2010 사용자는 구독 기반 버전의 Project Professional 2019 인 Project Online 데스크톱 클라이언트로 마이그레이션할 수도 있습니다. 이는 프로젝트 계획 3 및 Project 계획 5 구독에 포함 되어 있습니다.

#### <a name="move-to-an-online-solution"></a>온라인 솔루션으로 이동

Project Professional 2010 또는 Project Standard 2010에서 Project 구독 기반 온라인 솔루션으로 마이그레이션할 수도 있습니다. Project 요금제 3 및 계획 5에는 Project Online과 [웹에 대 한](https://support.office.com/article/what-can-you-do-with-project-for-the-web-b30f5442-be5f-43d2-9072-c95bff778ea1)최신 클라우드 제공이 포함 되어 있습니다. 둘 다 도움이 되는 새로운 기능과 이점을 제공 합니다.

기능 및 라이선스에 대 한 자세한 내용은 [Microsoft Project service description](https://docs.microsoft.com/office365/servicedescriptions/project-online-service-description/project-online-service-description)을 참조 하십시오.

## <a name="important-considerations-for-migrating-from-project-server-2010"></a>Project Server 2010에서 마이그레이션할 때의 중요 고려 사항

Project Server 2010에서 마이그레이션하려는 경우 다음 사항을 고려 하십시오.

- **Microsoft 솔루션 공급자가 제공 하는 도움말 보기** -Project Server 2010에서 업그레이드 하는 것이 어려울 수 있습니다. 준비 및 계획이 많이 필요 합니다. Project Server 2010을 처음 설정한 사용자가 없는 경우 특히 문제가 되지 않을 수 있습니다. Microsoft 솔루션 공급자는 Project Server 2019로 마이그레이션할지, 아니면 Project Online으로 마이그레이션할 지에 관계 없이 지원에 제공 됩니다. [Microsoft 솔루션 공급자 센터](https://go.microsoft.com/fwlink/p/?linkid=841249)에서 솔루션 공급자를 검색 합니다.

- **사용자 지정에 대 한 계획** -project server 2019 또는 project Online으로 마이그레이션할 때 project server 2010 환경의 사용자 지정 내용이 작동 하지 않을 수 있습니다. Project Server 아키텍처 버전 간에는 중요 한 차이점이 있습니다. 또한 해당 버전에서 작동 하는 필수 운영 체제, 데이터베이스 서버 및 웹 브라우저가 서로 다릅니다. 새 환경에서 사용자 지정 내용을 테스트 하거나 다시 작성 하는 방법에 대 한 계획을 마련 합니다. 이 기회를 통해 특정 사용자 지정 내용이 계속 필요한 지 확인할 수 있습니다. 자세한 내용은 [SharePoint 2013으로 업그레이드 하는 동안 현재 사용자 지정에 대 한 계획 만들기](https://docs.microsoft.com/SharePoint/upgrade-and-update/create-a-plan-for-current-customizations-during-upgrade-to-sharepoint-2013)를 참조 하세요.

- **시간 및** 인 업그레이드 계획, 실행 및 테스트에는 특히 Project Server 2019로 업그레이드 하는 경우 상당한 시간과 노력이 소요 됩니다. Project Server 2010에서 Project Server 2019로 마이그레이션하는 경우 먼저 Project Server 2013로 마이그레이션한 다음 데이터를 확인 하 고 Project server 2016로 마이그레이션한 다음 Project Server 2019로 마이그레이션해야 합니다. Microsoft 솔루션 공급자에 게 시간 프레임과 필요한 예상 비용을 문의 하 여 지원을 받을 수 있습니다.

## <a name="migrate-to-project-online"></a>Project Online으로 마이그레이션

Project Server 2010에서 Project Online으로 마이그레이션을 선택한 경우 다음 단계에 따라 프로젝트 계획 데이터를 수동으로 마이그레이션할 수 있습니다.

1. 프로젝트 계획을 Project Server 2010에서 .mpp 형식으로 저장 합니다.

2. Project Professional 2016, Project Professional 2019 또는 Project Online 데스크톱 클라이언트를 사용 하 여 각 .mpp 파일을 열고 저장 한 후 Project Online에 게시 합니다.

Project Online에서 PWA 구성을 수동으로 만들 수 있습니다 (예: 필요한 사용자 정의 필드 또는 enterprise 달력 새로 만들기). Microsoft 솔루션 공급자는이 프로세스에도 도움이 될 수 있습니다.

주요 리소스:

|리소스|설명|
|---|---|
|[Project Online 시작](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11)|Project Online을 설정 하 고 사용 하는 방법|
|[Project Online 서비스 설명](https://go.microsoft.com/fwlink/p/?linkid=829088)|사용할 수 있는 다른 Project Online 계획에 대 한 정보|

## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>새로운 온-프레미스 버전의 Project Server로 마이그레이션

Project Online으로 마이그레이션하는 것이 최상의 가치와 사용자 환경을 얻게 된다는 것을 강력히 확신 합니다. 그러나 일부 조직에서는 프로젝트 데이터를 온-프레미스로 유지 해야 하는 것도 이해 하 고 있습니다. 프로젝트 데이터를 온-프레미스로 유지 하도록 선택한 경우 Project Server 2010 환경을 Project Server 2013, Project Server 2016 또는 Project Server 2019로 마이그레이션할 수 있습니다.

Project Online으로 마이그레이션할 수 없는 경우 Project Server 2019로 마이그레이션하는 것이 좋습니다. Project Server 2019에는 이전 릴리스의 Project Server에 대 한 대부분의 주요 기능이 포함 되어 있습니다. 또한 Project online에서 사용할 수 있는 환경과 가장 밀접 하 게 일치 하지만 일부 기능은 Project Online 에서만 사용할 수 있습니다.

각 마이그레이션을 완료 한 후에 데이터가 제대로 마이그레이션 되었는지 확인 합니다.

> [!NOTE]
> 온-프레미스 솔루션으로 제한 되며 Project Server 2013로의 마이그레이션만 고려 하는 경우에는이 버전에는 몇 년간의 지원 기간이 더 남았습니다. Project Server 2013 서비스 팩 2 년 10 월 13 일 (2023)에 대 한 지원 종료 날짜입니다. 지원 종료 날짜에 대 한 자세한 내용은 [Microsoft 제품 수명 주기 정책을](https://go.microsoft.com/fwlink/p/?linkid=842066)참조 하세요.

### <a name="how-do-i-migrate-to-project-server-2019"></a>Project Server 2019로 마이그레이션하는 방법

Project Server 2010와 Project Server 2019 간의 아키텍처 차이로 인해 직접 마이그레이션 경로를 사용할 수 없습니다. 따라서 project server 2019에 도달할 때까지 Project server 2010 데이터를 Project Server의 각 연속 버전으로 마이그레이션해야 합니다. Project Server 2010을 Project Server 2019로 업그레이드 하는 단계:

1. Project Server 2013로 마이그레이션합니다.

2. Project 2016 Server 2013의 마이그레이션

3. Project Server 2016에서 Project Server 2019로 마이그레이션

각 마이그레이션을 완료 한 후에 데이터가 제대로 마이그레이션 되었는지 확인 합니다.

### <a name="step-1-migrate-to-project-server-2013"></a>1 단계: Project Server 2013로 마이그레이션

Project Server 2010에서 Project Server 2013로 업그레이드 하는 방법에 대 한 자세한 내용은 [Upgrade To Project server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822)를 참조 하십시오.

주요 리소스:

- [Project Server 2013 업그레이드 프로세스 개요](https://go.microsoft.com/fwlink/p/?linkid=841822)

  Project Server 2010에서 Project Server 2013로 업그레이드 하는 방법에 대 한 간략 한 개요를 확인 하세요.
- [Project Server 2013으로의 업그레이드 계획](https://go.microsoft.com/fwlink/p/?linkid=841823)

  시스템 요구 사항을 포함 하 여 Project Server 2010에서 Project Server 2013로 업그레이드할 때의 계획 고려 사항을 확인 합니다.

- [Project Server 2013 업그레이드의 새로운 기능](https://go.microsoft.com/fwlink/p/?linkid=841824) 에서는 다음을 포함 하 여이 버전에 대 한 중요 한 변경 사항을 다룹니다.

   - Project Server 2013에 전체 업그레이드가 없습니다. Project Server 2010에서 Project Server 2013로 업그레이드 하는 유일한 방법은 데이터베이스 연결 방법입니다.

   - 업그레이드 프로세스에서는 Project Server 2010 데이터를 Project Server 2013 형식으로 변환할 뿐만 아니라 4 개의 Project Server 2010 데이터베이스를 단일 Project Web App 데이터베이스에 통합 합니다.

   - SharePoint Server 2013 및 Project Server 2013이 모두 이전 버전에서 클레임 기반 인증으로 변경 되었습니다. 클래식 인증을 사용 하는 경우 업그레이드할 때이 점을 고려해 야 합니다. 자세한 내용은 [SharePoint 2013에서 클래식 모드에서 클레임 기반 인증으로 마이그레이션을]( https://docs.microsoft.com/sharepoint/upgrade-and-update/migrate-from-classic-mode-to-claims-based-authentication-in-sharepoint-2013)참조 하세요.

주요 리소스:

- [Project Server 2013으로의 업그레이드 프로세스 개요](https://go.microsoft.com/fwlink/p/?linkid=841274)

- [데이터베이스 및 Project Web App 사이트 모음 업그레이드(Project Server 2013)](https://go.microsoft.com/fwlink/p/?linkid=841272)

- [Microsoft Project Server 업그레이드 프로세스 다이어그램](https://go.microsoft.com/fwlink/p/?linkid=841270)

- [편리한 데이터베이스 통합 인 Project Server 2010이 8 단계에서 2013로 마이그레이션](https://go.microsoft.com/fwlink/p/?linkid=841271)

### <a name="step-2-migrate-to-project-server-2016"></a>2 단계: Project Server 2016로 마이그레이션

Project Server 2013로 이동한 후 데이터가 제대로 마이그레이션 되었는지 확인 한 후에는 Project Server 2016로 마이그레이션해야 합니다.

자세한 내용은 [Project Server 2016으로 업그레이드를](https://docs.microsoft.com/Project/upgrade-to-project-server-2016)참조 하세요.

주요 리소스:

- [Project Server 2016 업그레이드 프로세스 개요](https://docs.microsoft.com/Project/overview-of-the-project-server-2016-upgrade-process)

  Project Server 2013에서 Project Server 2016로 업그레이드 하기 위해 수행 해야 하는 작업에 대해 설명 합니다.

- [Project Server 2016으로의 업그레이드 계획](https://docs.microsoft.com/Project/plan-for-upgrade-to-project-server-2016)

  Project Server 2013에서 Project Server 2016로 업그레이드할 때 수행 해야 하는 계획 고려 사항을 확인 합니다.

[Project Server 2016 업그레이드에 대해 알아야 할 사항](https://docs.microsoft.com/project/plan-for-upgrade-to-project-server-2016#thingknow) 이 버전으로 업그레이드 하기 위한 중요 변경 사항에는 다음이 포함 됩니다.

- Project Server 2016 환경을 만들 때 SharePoint Server 2016에 Project Server 2016 설치 파일이 포함 되어 있는 것을 확인 합니다. 자세한 내용은 [Deploy Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841829)를 참조 하십시오.

- Project Server 2016에서는 자원 계획이 더 이상 사용 되지 않습니다. Project Server 2013 자원 계획은 Project Server 2016 및 Project Online에서 리소스 계약으로 마이그레이션됩니다. 자세한 내용은 [Overview (자원 계약](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) )를 참조 하세요.

### <a name="step-3-migrate-to-project-server-2019"></a>3 단계: Project Server 2019로 마이그레이션

Project Server 2016로 마이그레이션한 후 데이터가 제대로 마이그레이션 되었는지 확인 한 후에는 데이터를 Project Server 2019로 마이그레이션합니다.

Project Server 2016에서 Project Server 2019로 업그레이드 하기 위해 수행 해야 하는 작업에 대 한 자세한 내용은 [upgrade To Project server 2019](https://docs.microsoft.com/Project/upgrade-to-project-server-2016)를 참조 하십시오.

주요 리소스:

- [Project Server 2019 업그레이드 프로세스 개요](https://docs.microsoft.com/project/overview-of-the-project-server-2019-upgrade-process)

  Project Server 2013에서 Project Server 2016로 업그레이드 하기 위해 수행 해야 하는 작업에 대 한 높은 수준의 이해를 알아봅니다.

- [Project Server 2019 업그레이드 계획](https://docs.microsoft.com/project/plan-for-upgrade-to-project-server-2019)

  Project Server 2016에서 Project Server 2019로 업그레이드 하기 위한 계획 고려 사항을 확인 합니다.

- [Project Server 2019 업그레이드에 대해 알아야 할 사항](https://go.microsoft.com/fwlink/p/?linkid=841827)<br/><br/>다음을 포함 하 여이 버전으로 업그레이드 하는 경우의 중요 변경 사항에 대해 알아봅니다.

   - 업그레이드 프로세스에서는 Project Server 2016 데이터베이스의 데이터를 SharePoint Server 2019 콘텐츠 데이터베이스로 마이그레이션합니다.  Project Server 2019에서는 더 이상 SharePoint Server 팜에서 자체 Project Server 데이터베이스를 만들지 않습니다.

   - 업그레이드 후에는 Project Web App의 여러 변경 사항에 대해 숙지 해야 합니다.  자세한 내용은 [Project Server 2019의 새로운 기능](https://docs.microsoft.com/project/what-s-new-for-it-pros-in-project-server-2019#PWAChanges)을 참조 하십시오.

**기타 리소스**:

- [Project Online 서비스 설명](https://go.microsoft.com/fwlink/p/?linkid=841280): project Server 2016 및 Project Online Premium에 포함 된 포트폴리오 관리 기능을 확인 합니다.

- [Microsoft Office Project 포트폴리오 서버 2010 마이그레이션 가이드](https://go.microsoft.com/fwlink/p/?linkid=841279)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Office 2010 클라이언트 및 서버 및 Windows 7의 옵션 요약

Office 2010 클라이언트 및 서버와 Windows 7에 대한 업그레이드, 마이그레이션 및 클라우드 옵션으로 이동에 대한 시각적 요약은 [지원 종료 포스터](../downloads/Office2010Windows7EndOfSupport.pdf)를 참조하세요.

[![Office 2010 클라이언트 및 서버 및 Windows 7 포스터에 대 한 지원 종료](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

이 포스터에서는 Office 2010 클라이언트 및 서버 제품 및 Windows 7에 대 한 지원이 종료 되는 것을 방지 하기 위해 수행할 수 있는 다양 한 경로를 설명 하며, Microsoft 365 Enterprise의 기본 설정 경로 및 옵션 지원은 강조 되어 있습니다.

또한이 포스터를 [다운로드](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) 하 여 letter, legal 또는 tabloid (11 x 17) 형식으로 인쇄할 수 있습니다.

## <a name="related-topics"></a>관련 항목

[SharePoint 2010에서 업그레이드](upgrade-from-sharepoint-2010.md)

[Office 2010 서버 및 클라이언트에서 업그레이드](upgrade-from-office-2010-servers-and-products.md)
