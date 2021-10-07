---
title: Project Server 2007 지원 종료 로드맵
ms.author: efrene
author: efrene
manager: laurawi
ms.date: 1/31/2018
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
ms.assetid: d379018f-72b7-4284-b40a-6c23c8ae38fe
description: 2017년 10월 10일, Project Server 2007, Project Portfolio Server 및 Project 2007에 대한 지원이 종료됩니다. 지금 업그레이드를 계획하려면 이 문서를 사용하세요.
ms.openlocfilehash: c492c7154006a139589cff1c768dd77c13804c07
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60168461"
---
# <a name="project-server-2007-end-of-support-roadmap"></a>Project Server 2007 지원 종료 로드맵

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

2017년 Office 2007 서버 및 응용 프로그램에 대한 지원이 종료되었습니다. 마이그레이션 계획을 고려해야 합니다. 현재 Project Server 2007 및 관련 제품을 사용하고 있는 경우 다음 지원 종료 날짜를 유의합니다.
  
|**제품**|**지원 종료 날짜**|
|:-----|:-----|
|Project Server 2007  <br/> |2017년 10월 10일  <br/> |
|Project Portfolio Server 2007  <br/> |2017년 10월 10일  <br/> |
|Project 2007 Standard  <br/> |2017년 10월 10일  <br/> |
|Project 2007 Professional  <br/> |2017년 10월 10일  <br/> |
   
2007 Office 서버에 대한 자세한 내용은 Upgrade from [Office servers and client products을 참조하십시오.](upgrade-from-office-2007-servers-and-products.md)
  
## <a name="what-does-end-of-support-mean"></a>지원 *종료는 무엇을 의미하나요?*

대부분의 Microsoft 제품에는 새로운 기능, 버그 수정, 보안 수정 등 지원 수명 주기가 있습니다. 이 수명 주기는 일반적으로 제품의 초기 릴리스부터 10년 동안 지속됩니다. 이 수명 주기의 끝을 제품의 지원 종료라고 합니다. Project Server 2007이 2017년 10월 10일 지원이 종료되어 Microsoft는 더 이상 다음을 제공하지 않습니다.
  
- 발생할 수 있는 문제에 대한 기술 지원
    
- 서버의 안정성과 사용 가능성에 영향을 줄 수 있는 문제에 대한 버그 수정
    
- 서버가 보안 위반에 취약해질 수 있는 취약점에 대한 보안 수정
    
- 표준 시간대 업데이트.
    
이 Project Server 2007 설치는 계속 실행됩니다. 그러나 이전에 나열된 변경 내용으로 인하여 가능한 한 빨리 Project Server 2007에서 마이그레이션하는 것이 좋습니다.
  
## <a name="what-are-my-options"></a>내 옵션은 무엇입니까?

Project Server 2007을 사용하는 경우 다음과 같은 마이그레이션 옵션을 탐색해야 합니다.
  
- 마이그레이션을 Project Online
    
- 최신 버전의 Project Server로 마이그레이션(Project Server 2016)
    
|**마이그레이션을 선호하는 이유는 Project Online**|**마이그레이션을 선호하는 이유는 Project Server 2016**|
|:-----|:-----|
| 모바일 사용자가 있습니다.  <br/> <br/>마이그레이션 비용은 중요한 문제입니다(하드웨어, 소프트웨어, 시간 및 구현 노력). <br/><br/>  마이그레이션 후 내 환경을 유지 관리하는 데 들이는 비용이 중요한 문제입니다(예: 자동 업데이트, 보장된 작업 시간 등).  <br/> | 비즈니스 규칙은 클라우드에서 비즈니스를 운영하지 못하도록 제한합니다.<br/><br/>  환경에 대한 업데이트를 제어해야 합니다.  |
   
> [!NOTE]
> Office 2007 서버에서 이동하는 옵션에 대한 자세한 내용은 [Resources to help you upgrade from Office servers and clients을 참조하십시오.](upgrade-from-office-2007-servers-and-products.md) Project 서버와 서버가 동일한 리소스 풀을 공유할 수 Project Project Online 서버는 하이브리드 구성을 지원하지 않습니다. 
  
## <a name="important-considerations-when-you-migrate-from-project-server-2007"></a>Project Server 2007에서 마이그레이션할 때의 중요한 고려 사항

Server 2007에서 마이그레이션할 계획인 Project 고려합니다.
  
- **Microsoft 파트너의** 도움을 받을 수 있습니다. Project Server 2007에서 업그레이드하는 것은 어려울 수 있으며 많은 준비와 계획이 필요합니다. 원래 Server 2007을 설치한 사람이 아니어도 Project 어려울 수 있습니다. 다행히 Microsoft 파트너는 마이그레이션 계획에 관계가 없는지 또는 다른 사용자로 마이그레이션할지 Project Server 2016 있습니다Project Online. Microsoft 파트너 센터에서 마이그레이션에 도움이 되는 [Microsoft 파트너를 검색합니다.](https://go.microsoft.com/fwlink/p/?linkid=841249) *Gold* Project 및 포트폴리오 관리 용어를 검색하여 비즈니스에 대한 전문 지식이 있는 모든 Microsoft 파트너의 Project. 
    
- **사용자 지정** 계획 - Project Server 2007 환경으로 마이그레이션할 때 대부분의 사용자 지정이 작동하지 않을 Project Server 2016 Project Online. 버전 간에는 서버 Project 크게 차이가 있습니다. 지원되는 필수 운영 체제, 데이터베이스 서버 및 클라이언트 웹 브라우저도 다릅니다. 새 환경에 대한 사용자 지정을 테스트하거나 다시 만들 방법을 계획합니다. 또한 계획을 세우면 각 사용자 지정이 여전히 필요한지 여부를 고려할 수 있습니다. 자세한 내용은 [Create a plan for current customizations during upgrade to SharePoint 2013를 참조하십시오.](/SharePoint/upgrade-and-update/create-a-communication-plan-for-the-upgrade-to-sharepoint-2013) 
    
- **시간 및 인내** - 업그레이드 계획, 실행 및 테스트에는 특히 업그레이드 계획, 실행 및 테스트에 많은 시간이 Project Server 2016. 예를 들어 Project Server 2007에서 Project Server 2016로 마이그레이션하는 경우 먼저 Project Server 2010으로 마이그레이션하고 데이터를 확인한 다음 이후 각 버전으로 마이그레이션할 때 동일한 작업을 해야 합니다. Microsoft 파트너에게 확인하여 예상 시간이 얼마나 걸릴지와 비용이 필요한지 확인할 수 있습니다.
    
## <a name="migrate-to-project-online"></a>마이그레이션을 Project Online

Project Server 2007에서 Project Online 마이그레이션하기로 선택한 경우 다음을 수행하여 프로젝트 계획 데이터를 수동으로 마이그레이션할 수 있습니다.
  
1. 서버 2003에서 Project 계획을 .mpp 형식으로 저장합니다.
    
2. Project Professional 2013, Project Professional 2016 또는 Project Online 데스크톱 클라이언트에서 각 .mpp 파일을 연 다음 해당 파일을 저장하여 Project Online.
    
웹앱에서 Microsoft Project Web App(PWA) 구성을 수동으로 만들 Project Online. 예를 들어 필요한 사용자 정의 필드나 Enterprise 달력을 다시 만들 수 있습니다. Microsoft 파트너도 이 프로세스에 도움을 줄 수 있습니다.
  
주요 리소스:
  
|**리소스**|**설명**|
|:-----|:-----|
|[Project Online 시작](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11) <br/> |설치 및 사용 Project Online <br/> |
|[Project Online 서비스 설명](/office365/servicedescriptions/project-online-service-description/project-online-service-description) <br/> |사용할 수 있는 다양한 Project Online 계획에 대한 정보 <br/> |
   
## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>최신 버전의 Project 서버로 마이그레이션

사용자 환경으로 마이그레이션하여 최상의 가치와 사용자 환경을 얻을 수 Project Online. 그러나 일부 조직에서는 프로젝트 데이터를 사내 환경에서 유지해야 한다는 사실도 알고 있습니다. 프로젝트 데이터를 사내에 유지하려면 Project Server 2007 환경을 Project Server 2010, Project Server 2013 또는 Project Server 2016.
  
마이그레이션할 수 없는 경우 Project Online 마이그레이션하는 것이 Project Server 2016. Project Server 2016 Server의 이전 릴리스의 모든 기능을 Project 포함되어 있습니다. 일부 기능은 Project Online 사용 가능한 환경과 가장 Project Online.
  
마이그레이션이 끝날 때마다 데이터가 성공적으로 마이그레이션된 것이 확인됩니다.
  
> [!NOTE]
>
  
### <a name="how-do-i-migrate-to-project-server-2016"></a>마이그레이션하려면 어떻게 Project Server 2016?

Project Server 2007과 Project Server 2016 아키텍처 차이로 인해 직접 마이그레이션 경로가 차단됩니다. 따라서 Project Server 2007 데이터를 연속된 각 Project Server 버전으로 마이그레이션해야 Project Server 2016.
  
다음 단계에 따라 Project Server 2016.
  
1. Project Server 2007에서 Project 서버 2010으로 마이그레이션합니다.
    
2. Project 2010에서 Project Server 2013으로 마이그레이션합니다.
    
3. Project Server 2013에서 2013으로 Project Server 2016.
    
마이그레이션이 끝날 때마다 데이터가 성공적으로 마이그레이션된 것이 확인됩니다.
  
### <a name="step-1-migrate-from-project-server-2007-to-project-server-2010"></a>1단계: Project Server 2007에서 Project Server 2010으로 마이그레이션

Project Server 2007에서 Project Server 2010으로 업그레이드하기 위해 필요한 작업을 포괄적으로 설명하려면 [Upgrade to Project Server 2010을 참조하세요.](/previous-versions/office/project-server-2010/gg502590(v=office.14))
  
주요 리소스:
  
|**리소스**|**설명**|
|:-----|:-----|
|[Project Server 2010 업그레이드 개요](/previous-versions/office/project-server-2010/ee662496(v=office.14)) <br/> |Project Server 2007에서 Project Server 2010으로 업그레이드하기 위해 필요한 Project 보기 <br/> |
|[Project Server 2010으로 업그레이드 계획](/previous-versions/office/project-server-2010/ff603505(v=office.14)) <br/> |Project Server 2007에서 Project Server 2010으로 업그레이드할 때의 계획 고려 사항(시스템 요구 사항 포함)  <br/> |
   
#### <a name="how-do-i-upgrade"></a>업그레이드 방법

자세한 내용은 [Upgrade to Project Server 2010을 참조합니다.](/previous-versions/office/project-server-2010/gg502590(v=office.14)) 그러나 업그레이드에 사용할 수 있는 두 가지 고유한 방법이 있습니다.
  
- **데이터베이스 연결 업그레이드:** 이 방법은 구성 설정이 아닌 환경의 콘텐츠만 업그레이드합니다. 32비트 서버 운영 체제만 지원하는 하드웨어에 Office Project Server 2007에서 업그레이드하는 경우 필요합니다. 데이터베이스 연결 업그레이드 방법에는 다음 두 가지 유형이 있습니다.
    
  - **데이터베이스 연결** 전체 업그레이드 - Office Project Server 2007 데이터베이스에 저장된 프로젝트 데이터와 Microsoft Project 콘텐츠 데이터베이스에 저장된 Microsoft Project Web App 사이트 데이터를 SharePoint 마이그레이션합니다.
    
  - **데이터베이스 연결 *핵심 업그레이드*** - Project 서버에 저장된 프로젝트 데이터만 마이그레이션합니다.
    
- **전체 업그레이드:** 팜 및 팜의 모든 콘텐츠에 대한 구성 데이터가 고정된 순서로 기존 하드웨어에서 업그레이드됩니다. 업그레이드 프로세스를 시작하면 설치 프로그램이 전체 팜을 오프라인 상태로 전환합니다. 업그레이드가 Microsoft Project 웹 사이트 및 웹앱 사이트를 사용할 수 없는 경우 설치 프로그램이 서버를 다시 시작합니다. 현재 업그레이드를 시작한 후 업그레이드를 일시 중지하거나 이전 버전으로 롤백할 수 없습니다. 프로덕션 환경의 미러된 이미지를 만들어 프로덕션 환경이 아닌 이 환경으로 바로 업그레이드하는 것이 가장 좋습니다. 
    
추가 리소스:
  
- [Microsoft Project Server 2010 업그레이드를 위한 SuperFlow](/samples/browse/?redirectedfrom=TechNet-Gallery)
    
- [Project Server 2007에서 Project Server 2010으로 마이그레이션](/samples/browse/?redirectedfrom=TechNet-Gallery)
    
- [Project Web App 웹 파트 업그레이드 고려 사항](/previous-versions/office/project-server-2010/gg314581(v=office.14))
    
- [Project SDK(소프트웨어 개발 키트)](/previous-versions/office/developer/office-2010/ms481966(v=office.14))
    
### <a name="step-2-migrate-to-project-server-2013"></a>2단계: Project Server 2013으로 마이그레이션

데이터가 성공적으로 마이그레이션된 것을 확인한 후 다음 단계는 Server 2013으로 Project 것입니다.
  
Project Server 2010에서 Project Server 2013으로 업그레이드하기 위해 필요한 작업을 포괄적으로 설명하려면 [Upgrade to Project Server 2013을 참조하세요.](/project/upgrade-to-project-server-2016) 
  
주요 리소스:
  
|**리소스**|**설명**|
|:-----|:-----|
|[Project Server 2013 업그레이드 프로세스 개요](/project/upgrade-to-project-server-2016) <br/> |Project Server 2013으로 업그레이드하기 위해 Project 개요  <br/> |
|[Project Server 2013으로 업그레이드 계획](/project/plan-for-upgrade-to-project-server-2016) <br/> |Project Server 2010에서 Project Server 2013으로 업그레이드할 때의 계획 고려 사항(시스템 요구 사항 포함) <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>이 버전으로의 업그레이드에 대해 알아야 할 것

[Project Server 2013의](/project/what-s-new-in-project-server-2013-upgrade) 새로운 업그레이드에서는 이 버전에 대한 업그레이드에 대한 중요한 변경 사항을 설명하고 있습니다. 가장 두드러진 것은 다음입니다. 
  
- 2013 Server 2013에는 현재 Project 없습니다. 데이터베이스 연결 방법은 Project Server 2010에서 Project Server 2013으로 업그레이드하는 유일한 방법입니다.
    
- 업그레이드 프로세스에서는 Project Server 2010 데이터를 Project Server 2013 형식으로 변환할 뿐만 아니라 4개의 Project Server 2010 데이터베이스를 단일 Project Web App 데이터베이스로 통합합니다.
    
- 2013 버전에서는 SharePoint Server와 Project Server가 모두 클레임 기반 인증으로 변경되었습니다. 클래식 인증을 사용하는 경우 업그레이드를 위해 이 요소를 고려해야 합니다. 자세한 내용은 [Migrate from classic-mode to claims-based authentication in SharePoint](/sharepoint/security-for-sharepoint-server/security-for-sharepoint-server).
    
추가 리소스:
  
- [Project Server 2013으로의 업그레이드 프로세스 개요](/project/overview-of-the-project-server-2016-upgrade-process)
    
- [데이터베이스 및 Project Web App 사이트 모음 업그레이드(Project Server 2013)](/project/upgrading-to-project-server-2016)
    
- [Microsoft Project 서버 업그레이드 프로세스 다이어그램](https://go.microsoft.com/fwlink/p/?linkid=841270)
    
- [서버 2010에서 Project 2013으로의 뛰어난 데이터베이스 통합(8단계로 마이그레이션)](https://go.microsoft.com/fwlink/p/?linkid=841271)
    
### <a name="step-3-migrate-to-project-server-2016"></a>3단계: 마이그레이션을 Project Server 2016

데이터가 성공적으로 마이그레이션된 것을 확인한 후 다음 단계는 마이그레이션된 데이터로 Project Server 2016.
  
Project Server 2013에서 2013으로 업그레이드하기 위해 Project Server 2016 자세한 내용은 [Upgrade to Project Server 2016.](//project/upgrading-to-project-server-2016)
  
주요 리소스:
  
|**리소스**|**설명**|
|:-----|:-----|
|[Project Server 2016 업그레이드 프로세스 개요](/previous-versions/office/project-server-2010/ee662104(v=office.14)) <br/> |Project Server 2013에서 서버로 업그레이드하기 위해 Project Server 2016 <br/> |
|[Project Server 2016으로의 업그레이드 계획](/project/plan-for-upgrade-to-project-server-2016) <br/> |Project Server 2013에서 2013으로 업그레이드할 계획 Project Server 2016 <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>이 버전으로의 업그레이드에 대해 알아야 할 것

[업그레이드에](/project/plan-for-upgrade-to-project-server-2016) 대해 알아야 Project Server 2016 다음을 포함해 이 버전에 대한 업그레이드에 대한 몇 가지 중요한 변경 사항을 알 수 있습니다.
  
- Project Project Server 2016 Server 2013 데이터를 마이그레이션할 Project Server 2016 환경을 만들면 Project Server 2016 설치 파일이 SharePoint Server 2016에 포함됩니다. 자세한 내용은 [Deploy Project Server 2016.](/project/deploy-project-server-2016)
    
- 자원 계획은 2016년 9월에 Project Server 2016. Project Server 2013 리소스 계획은 Project Server 2016 및 리소스 계약으로 Project Online. 자세한 [내용은 개요: 리소스](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) 계약을 참조하세요. 
    
## <a name="migrate-from-portfolio-server-2007"></a>Portfolio Server 2007에서 마이그레이션

Project Portfolio Server 2007은 포트폴리오 전략Project 우선 순위 지정 및 최적화를 위해 Project Server 2007과 함께 사용했습니다. 이 버전 이후에는 추가 Project 포트폴리오 서버가 만들어지지 않습니다. 그러나 포트폴리오 관리 기능은 Project Server 2016 Premium 버전에서 사용할 수 Project Online. 그러나 Project Portfolio Server 2007의 데이터는 두 데이터 중 하나로 마이그레이션할 수 없습니다. 비즈니스 드라이버와 같은 데이터를 다시해야 합니다.
  
기타 리소스:
  
- [Project Online 설명:](/office365/servicedescriptions/project-online-service-description/project-online-service-description) 2016 및 2013에 포함된 포트폴리오 관리 Project Server 2016 Project Online Premium.
    
- [Microsoft Office Project Portfolio Server 2007 마이그레이션 가이드입니다.](https://go.microsoft.com/fwlink/p/?linkid=841279)
    
## <a name="related-topics"></a>관련 항목

[SharePoint Server 2007 지원 종료 로드맵](sharepoint-2007-end-of-support.md)
  
[2007 서버 및 클라이언트에서 업그레이드하는 Office 리소스](upgrade-from-office-2007-servers-and-products.md)
