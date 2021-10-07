---
title: SharePoint 2007 마이그레이션 옵션
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- SPO_Content
search.appverid:
- MET150
- SPS150
- OSU140
- SPO160
- SPB160
- OSI150
- OSI160
- BSA160
- OSU160
ms.assetid: 66325a43-5816-4f8e-81ba-c11b71345b7c
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
description: 이 문서에서는 SharePoint Server 2007을 사용하여 업그레이드를 계획하는 데 도움이 되는 정보를 제공합니다.
ms.openlocfilehash: 9f374e3e4f2282a7740575c60eb52e7095321c92
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60210200"
---
# <a name="sharepoint-2007-migration-options-to-consider"></a>SharePoint 2007 마이그레이션 옵션

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

Microsoft SharePoint 2007 및 SharePoint Server 2007의 지원이 종료됩니다. 이제 업그레이드할 시간입니다. 이 문서에서는 마이그레이션 옵션에 대한 정보를 제공합니다.
  
## <a name="common-upgrade-strategies-for-sharepoint"></a>일반적인 업그레이드 SharePoint

서버 환경을 업그레이드하는 방법에는 여러 가지가 SharePoint 있습니다. 서버 2007 Microsoft Office SharePoint 있는 경우 업그레이드 방법의 몇 가지 예는 다음과 같습니다.
  
- 데이터베이스 연결
    
- 나란히 업그레이드
    
- 전체 업그레이드
    
- 하이브리드 업그레이드(분리된 데이터베이스가 있는 전제/ 별도의 데이터베이스 연결)
    
- SharePoint 하이브리드(온라인에서 SharePoint)
    
- 사이트 모음 또는 라이브러리 간에 데이터를 수동으로 이동
    
- FastTrack Microsoft 365[업그레이드(SharePoint Online 배포 고문](https://aka.ms/spoguidance))
    
- SPO(SharePoint Online)로의 마이그레이션 API Microsoft 365
    
어떤 것이 가장 적합한가요?
  
팜의 작동 및 사용에 대한 지식은 업그레이드에 대한 전술적 강도입니다. 팜을 사용하는 SharePoint 옵션을 선택하는 데 도움이 됩니다.
  
> [!TIP]
> Microsoft Office SharePoint Server 2007에는 여기에서 다루지 않는 단계적 업그레이드도 있습니다. 단계별 업그레이드 문서 목록을 표시하려면 SharePoint [Server 2007 지원 종료 로드맵을 참조하세요.](sharepoint-2007-end-of-support.md) 
  
업그레이드할 버전에 대한 제품 수명 주기 및 시스템 요구 사항을 SharePoint 합니다. [](https://support.microsoft.com/lifecycle/search) 따라서 다음 업그레이드가 필요한 경우를 알 수 있습니다. 예를 들어 추가 업그레이드를 계획하기 위해 SharePoint Server 2010과 같은 레거시 제품에서 일시 중지하는 경우 지원 날짜를 알고 있어야 합니다. 계획을 지원하는 하드웨어가 있는지 확실하게 알 수 있습니다. 
  
일부 또는 모든 SharePoint 클라우드로 전환하려면 Microsoft 365 서비스 설명 에 대한 링크를 책갈피로 Microsoft 365 Office 365 [합니다.](/office365/servicedescriptions/office-365-service-descriptions-technet-library) SharePoint Online 기능과 이러한 기능이 SharePoint 서버와 어떻게 다를 수 있을지 알아보는 데 서비스 설명이 필요합니다. Server 2007 Microsoft Office SharePoint 기능 업그레이드 설치에 손상된 사이트가 있는 경우 업그레이드 전에 수정합니다.
  
## <a name="a-note-about-managing-risk"></a>위험 관리에 대한 참고 사항

'나란히' 같은 메서드는 업그레이드 논리 체계에서 중요합니다. 나란히 업그레이드하는 경우 Microsoft Office SharePoint Server 2007 팜을 유지 관리하지만 새 하드웨어에 다음 버전부터 팜을 구축(SharePoint Server 2010)합니다. 이 기능은 세 가지 방법으로 도움이 됩니다.
  
1. 데이터베이스 연결 기능을 사용하여 Microsoft Office SharePoint Server 2007 데이터베이스의 백업을 별도로 업그레이드할 수 있습니다.
    
2. Microsoft Office SharePoint Server 2007 팜에서 소수의 중요한 문서 라이브러리 및 기타 정보만 사용 중이면 데이터를 Microsoft Office SharePoint Server 2007에서 SharePoint Server 2010으로 수동으로 이동하거나, 특정 사이트 및 웹을 다음 버전으로 변경합니다(작업을 더 쉽게 만들 수 있습니다).
    
3. Microsoft Office SharePoint Server 2007 서버 팜을 직접 업그레이드할 때 팜에 포함된 데이터가 더 안전합니다.
    
In-Place 업그레이드와 같은 방법은 Microsoft Office SharePoint Server 2007 팜에서 직접 실행되어 경로를 포기하고 기본 환경을 다시 시작할 수 있는 더 적은 수의 간편한 옵션을 제공합니다. 가능한 한 일부 안전 조치(예: 원래 환경의 백업 작성 및 테스트)를 구축합니다. 예를 들어 Microsoft Office SharePoint Server 2007 팜이 가상 팜으로 복제되어 백업 및 복원을 위해 복제된 경우 업그레이드를 위해 서비스 창 이전에 최신 데이터베이스를 백업 및 복원합니다. 데이터베이스 백업을 복원할 수 있는 옵션이 있는 경우 장애 조치(failsafe)가 제공될 뿐만 아니라 안심할 수 있습니다.
  
> [!TIP]
> 업그레이드를 위한 모범 사례 문서는 Microsoft Office SharePoint [Server 2007, SharePoint Server](/previous-versions/office/sharepoint-2007-products-and-technologies/cc261992(v=office.12)) [2010,](/previous-versions/office/sharepoint-server-2010/cc261992(v=office.14)) [SharePoint Server 2013](/SharePoint/upgrade-and-update/best-practices-for-upgrading-from-sharepoint-2010-to-sharepoint-2013)및 SharePoint [Server 2016에](/SharePoint/upgrade-and-update/best-practices-for-upgrade)대한 것입니다. 업그레이드 또는 마이그레이션 경험이 있는 [Microsoft 파트너를](https://partnercenter.microsoft.com/pcv/search) 검색할 Microsoft 365 있습니다. 
  
## <a name="make-your-plan"></a>계획 수립

업그레이드해야 하는 경우 요금제가 필요하며 이러한 경우 한 크기로는 적합하지 않습니다. 요금제는 'Microsoft 365 Online을 사용하여 SharePoint 구독 만들기, 도메인 등록, 파일을 저장하기 위해 사용자를 리디렉션'처럼 간단할 수 있습니다. 아는 경우도 있습니다. 이러한 결정은 사용자의 결정에 따라 결정됩니다.
  
> [!NOTE]
> 수명 주기가 종료된 소프트웨어에서 실행해야 합니다. 지원이 없는 제품은 문제가 발견될 때 더 이상 패치가 없습니다. 즉, 새로운 보안 위협이 발생할 경우 수명 주기 종료 제품이 더 이상 지원되지 않는 보안 패치나 수정이 없습니다. 이러한 상황을 방지하세요! 
  
### <a name="first-know-your-farm"></a>먼저 팜을 알아야 합니다.

업그레이드할 때 의사 결정은 팜이 조직에 대해 어떤 기능을 하는지 기준으로 해야 합니다. 충족해야 하는 것은 무엇입니까? 역할이란? 회사의 각 팜에는 다른 역할이 있을 수 있습니다. 일부 SharePoint 팜은 중요할  수 있습니다. 일부는 안전한 유지를 위해 파일 보관 파일일 수 있습니다. 또는 팜이 여러 역할을 동시에 채우는 경우 어떤 사이트 모음, 웹 또는 문서 라이브러리가 어떤 역할을 하는지, 사용자 지정하는지, 얼마나 중요한지 알아야 할 수 있습니다. 이 수준에서 데이터를 분석하면 많은 작업으로 보일 수 있지만 업그레이드하거나 마이그레이션하기 전에 도메인을 마스터하기 위한 시간과 노력을 절약할 수 있습니다. 이동하는 모든 부분과 가장 중요한 비트를 알고 나면 그 외의 다른 부분에 남겨두어도 될 수 있는 부분을 알 수 있습니다. 해당 지식은 앞으로도 도움이 됩니다. 
  
따라서 사용자의 서버 팜에 대해 가장 중요한 SharePoint 무엇입니까?
  
- 기본 제공 SharePoint 기능
    
- 큰 데이터 폴더(예: 파일 보관 파일)
    
- 사용 가능성
    
- 팜의 중요 앱, 웹 파트 또는 docs(중요 중요 팜)
    
- 준수 표준 충족
    
- 사용자 지정 기능
    
SharePoint 팜에서 비즈니스에 필수적인 것을 실행하면 클라이언트 서비스 요구 사항에 대한 중요한 데이터의 큰 카탈로그와 같은 역할을 하는 경우 '중요 앱' 옆에 틱을 넣을 수 있지만 '가용성' 옆에 틱을 넣을 수 있습니다. 즉, 한 동안 SharePoint 수 없는 경우 비즈니스에 영향을 줄 수 있습니다. 마찬가지로 팜에서 제공하는 중요한 서비스는 사용자 지정 코드, 사이트 정의 또는 함께 작동되는 여러 사용자 지정을 기반으로 하여 '사용자 지정'을 확인할 수 있습니다.
  
SharePoint 소프트웨어에 기본 제공된 기능을 사용하지 않고도 이러한 요구를 충족하는 경우 일반적으로 업데이트하고 정상적인 관리 및 유지 관리 작업을 수행한 경우 '기본 제공 SharePoint'를 선택했다고 할 수 있습니다. 이는 이전 버전의 SharePoint. 즉, 이미 필요한 것은 2007 Server 2007 지원 종료 시에 현재까지 업그레이드할 필요가 Microsoft Office SharePoint 않습니다.
  
이러한 항목의 목록을 글머리 기호로 표시하면 업그레이드 조건을 만들 수 있습니다. 즉, 모든 업그레이드를 고려하려면 이 표시줄을 충족해야 합니다. 이렇게 하면 현재 요구에 맞지 않는 메서드를 예외로 사용할 수 있습니다.
  
### <a name="a-simple-sample-plan"></a>간단한 샘플 계획

업그레이드를 진행하는 데 필요한 경로에 리더십 및 기타 관리자와 더 SharePoint 수 있습니다. SharePoint 서버 관리자는 종종 Microsoft SQL Server 관리자와 협력하고, 네트워킹 및 보안 팀과 협력하는 등 여러 작업을 합니다. 이해 관계자가 많은 경우 업그레이드 및 마이그레이션 계획에 대한 계약을 구축하거나 조정해야 할 수 있습니다. 예를 들어 회사의 일부에서 SharePoint Online을 Microsoft 365 데이터를 마이그레이션하는 경우 네트워크 내부에서 성능 조정 또는 테스트가 필요할 수 있습니다. 영향을 받는 팀은 미리 정보를 알려야 합니다.
  
간단한 샘플에서는 SharePoint 관리자의 제안을 표시한 다음 모든 이해 관계자가 동의한 계획을 나열합니다. 명확성을 위해 계약 및 결정을 문서화합니다.
  
이 계획은 팜을 심도 있게 분석한 후 시작하여 팜의 역할, 문제 지점 및 일부 업그레이드 옵션의 범위를 좁힐 수 있는 기타 중요한 정보를 파악합니다. 이후 업그레이드 제안은 SharePoint 관리자가 수행하고 관련자는 작업 계획에 동의합니다.
  
내 '가장 중요한' 글머리 기호 목록:
  
- 가용성, 기본 제공 SharePoint 및 규정 준수 표준.
    
- 대부분의 데이터는 세 개의 사이트 모음에 있으며, 하나의 모임 작업 영역은 개발자 팀에서 특히 중요하며 전 세계 여러 표준 시간대에서 많이 사용됩니다.
    
- 널리 사용되는 17개의 다른 사이트가 있습니다.
    
- 두 개의 문서 라이브러리(모임 작업 영역 및 루트 사이트 모음의 문서)가 최대(각각 8,000개가 넘는 문서)입니다. 스프레드시트 첨부 파일이 있는 보관된 문서 및 목록이 많이 있습니다.
    
- 규정 준수를 유지해야 하는 중요한 데이터가 있는 14개의 라이브러리 목록이 있습니다.
    
- 어디로든 보류 및 전자 검색을 할 수 있어야 합니다.
    
- 이 데이터 중 일부는 InfoSec 규칙으로 인해 사내에 있어야 합니다.
    
 **내 업그레이드 및 마이그레이션 선택 사항:**
  
| 예 | 아니요 |
|:-----|:-----|
|데이터베이스 연결로 데이터베이스 업그레이드  <br/> |전체 업그레이드  <br/> |
|팜을 나란히 업그레이드  <br/> |하이브리드 업그레이드  <br/> |
|마이그레이션 API를 SPO로 Microsoft 365(개인 사이트 데이터용)  <br/> |SharePoint 하이브리드(아직 필요하지 않습니다)  <br/> |
|중요한 데이터를 위해 SharePoint 일부 수동 데이터 마이그레이션  <br/> |FastTrack 마법사로 업그레이드할 Microsoft 365  <br/> |
   
 **제안된 계획:**
  
데이터베이스를 먼저 업그레이드할 수 있도록 SharePoint 버전이 나란히 있는 가상화된 버전의 프레미스를 업그레이드합니다. 2007 SharePoint 2010으로 SharePoint 있습니다. 관리자 및 개발자는 결과 팜을 테스트합니다. 사용자는 결과 팜을 테스트합니다. 이 시간 동안 중지하는 문제를 해결합니다. 다시 한 번 나란히 2010 데이터베이스를 SharePoint 2013으로 SharePoint 업그레이드합니다. 테스트합니다. 사용자 테스트/파일럿. 이 시간 동안 중지하는 문제를 해결합니다.
  
- SPO가 있는 Search Federated Hybrid가 요구 사항을 충족하는지 고려합니다.
    
- 여기에서 [FastTrack Online으로](https://fasttrack.microsoft.com) 업그레이드하려면 SharePoint 지원을 고려하세요. 
    
- 사이트 모음을 특정 구독으로 오프로드할 수 있는지 Microsoft 365. (Microsoft 365 준수 [표준을 충족합니다.](/compliance/regulatory/offering-home) Microsoft 365 [eDiscovery가](https://support.office.com/article/edea80d6-20a7-40fb-b8c4-5e8c8395f6da) 있으며 준수 센터를 [통해](https://support.office.com/article/A18F8975-AA7F-43B4-A7D6-001D14744D8E) 보류를 할 수 있습니다.) 
    
그렇지 않은 경우 서버 2016으로의 SharePoint 업그레이드를 계속합니다.
  
> [!NOTE]
> 업그레이드를 계획하는 관리자가 권장한 사항과 실제 프로세스 사이에는 업그레이드가 의존하는 다른 관련자와 진행되는 대화가 있습니다. 예를 들어 경우에 따라 관리자가 계획을 변경해야 하는 경우도 있습니다. 최종 결정이 무엇이든 합의된 계획이 무엇일지 문서화해야 합니다. 다음과 같이 될 수 있습니다. 
  
 **내 작업 계획:**
  
사내에서는 가상 환경을 사용하여 기본 SharePoint Server 2010 및 2013을 빌드합니다. SharePoint Server 2016은 2016의 시스템 요구 사항을 충족하는 새 하드웨어를 통해 구축됩니다. 데이터베이스 연결은 SharePoint 2007에서 Server 2016과 서버 2016 사이의 모든 버전으로 SharePoint 연결합니다. 핵심 사용자 지정은 현재 SharePoint Server 2016 환경에서 기본 기능이 요구 사항을 충족하지 않는 경우 다시 제작 및 테스트됩니다. 성공적으로 실행된 경우 업그레이드된 데이터베이스가 있는 새 하드웨어에 사내 팜이 있으며 사용자 지정 횟수가 줄어듭됩니다. 업그레이드된 콘텐츠 데이터베이스를 SharePoint Server 2013의 새 사이트 모음에 연결하고, 테스트, 사용자 테스트/파일럿을 진행한 다음 라이브 사용을 위해 새 SharePoint Server 2016 환경에 대한 DNS 컷오버를 진행합니다.
  
- 현재는 SharePoint Server 2016과 온라인 SharePoint 고려하지 않습니다.
    
- 사이트의 약 35%를 베니티 도메인이 있는 새 SPO 사이트로 변경하거나 궁극적으로는 저장소에 비즈니스용 OneDrive 있습니다. 사이트를 변환하거나 새 사이트를 SPO로 라우팅할 수 있는 다른 기회를 찾고 있습니다.
    
- 마이그레이션의 이 부분 중 일부는 개인 사이트로 끌어서 놓기비즈니스용 OneDrive 마이그레이션 API를 통해 수동으로 수행됩니다.
    
보다 자세한 단계 또는 특정 업그레이드 방향에 대한 여러 링크는 계획을 따라야 합니다. MOSS 2007 컴퓨터는 해제하지 말고, 비교를 위해 가상 환경을 유지 관리해야 합니다. 그러나 사용자가 Server 2016에서 SharePoint 업그레이드가 완료됩니다.
  
방법을 선택할 때의 주요 요인은 업그레이드의 총 비용과 시간 비용입니다(마이그레이션 로드맵 SharePoint 참조). 그러나 미리 계획을 세우면 기대치를 설정하고 현명하게 선택하고 성공의 모양을 밝히는 데 큰 도움이 됩니다.
  
## <a name="related-links"></a>관련 링크

[2007 서버 및 클라이언트에서 업그레이드하는 Office 리소스](upgrade-from-office-2007-servers-and-products.md)
  
[Microsoft 수명 주기 정책 및 수명 주기 검색](https://support.microsoft.com/lifecycle)
  
[업그레이드 또는 마이그레이션에 도움이 될 수 있는 Microsoft 파트너 검색](https://partnercenter.microsoft.com/pcv/search)
