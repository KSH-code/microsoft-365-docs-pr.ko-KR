---
title: 고려할 SharePoint 2007 마이그레이션 옵션
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Normal
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
ms.openlocfilehash: 3e37a01f1a2d387cda6723a8df1f73734fa3ba9d
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694957"
---
# <a name="sharepoint-2007-migration-options-to-consider"></a>고려할 SharePoint 2007 마이그레이션 옵션

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

Microsoft SharePoint 2007 및 SharePoint Server 2007이 지원이 종료됩니다. 이제 업그레이드해야 합니다. 이 문서에서는 마이그레이션 옵션에 대한 정보를 제공합니다.
  
## <a name="common-upgrade-strategies-for-sharepoint"></a>SharePoint의 일반적인 업그레이드 전략

SharePoint Server 환경을 업그레이드하는 방법에는 여러 가지가 있습니다. SharePoint Server 2007 Microsoft Office 업그레이드 방법의 몇 가지 예는 다음과 같습니다.
  
- 데이터베이스 연결
    
- 나란히 업그레이드
    
- 전체 업그레이드
    
- 하이브리드 업그레이드(분리된 데이터베이스가 있는 모든 환경/별도의 데이터베이스 연결)
    
- SharePoint 하이브리드(온라인에서온-프레미스 SharePoint에 연결)
    
- 사이트 모음 또는 라이브러리 간에 수동으로 데이터 이동
    
- Microsoft 365로 FastTrack 마법사[업그레이드(SharePoint Online 배포 자문)](https://aka.ms/spoguidance)
    
- Microsoft 365에서 SharePoint Online(SPO)으로의 마이그레이션 API
    
어떤 것이 가장 적합한가요?
  
팜의 작동 및 사용에 대한 지식은 업그레이드와 같은 전술적 강도입니다. SharePoint 팜을 사용하는 방식은 옵션에서 선택하는 데 도움이 됩니다.
  
> [!TIP]
> Microsoft Office SharePoint Server 2007에는 여기에서 다루지 않는 점진적 업그레이드도 있습니다. 단계별 업그레이드 문서 목록을 표시하려면 [SharePoint Server 2007 지원 종료 로드맵을 참조하세요.](sharepoint-2007-end-of-support.md) 
  
업그레이드할 SharePoint 버전에 대한 제품 수명 주기 및 시스템 요구 사항을 확인합니다. [](https://support.microsoft.com/lifecycle/search) 이렇게 하면 다음 업그레이드가 필요한 경우(예: 더 많은 업그레이드를 계획하기 위해 SharePoint Server 2010과 같은 레거시 제품에서 일시 중지하는 경우, 지원 종료 날짜를 알고 있는지 확인) 계획을 지원하는 하드웨어가 있는지를 알 수 있습니다. 
  
SharePoint 사이트의 일부 또는 전체를 클라우드의 Microsoft 365로 전환하려면 Microsoft [365 및 Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)서비스 설명에 대한 링크를 책갈피로 설정해야 합니다. SharePoint Online 기능에 대해 알아보고 이러한 기능이온-프레미스 SharePoint Server와 어떻게 다를 수 있는지 알아보는 데 서비스 설명이 필요합니다. SharePoint Server Microsoft Office 기능 업그레이드 설치에 손상된 사이트가 있는 경우 업그레이드 전에 수정합니다.
  
## <a name="a-note-about-managing-risk"></a>위험 관리에 대한 참고 사항

'나란히' 같은 메서드는 업그레이드 논리 체계에서 중요합니다. 함께 업그레이드하는 경우 Microsoft Office SharePoint Server 2007 팜을 유지 관리하지만 새 하드웨어에서 다음 버전부터 팜을 구축합니다(SharePoint Server 2010). 이렇게 하면 세 가지 방법으로 도움이 됩니다.
  
1. 데이터베이스 연결 기능을 사용하여 Microsoft Office SharePoint Server 2007 데이터베이스의 백업을 별도로 업그레이드할 수 있습니다.
    
2. Microsoft Office SharePoint Server 2007 팜에서 소수의 중요한 문서 라이브러리 및 기타 정보만 사용 중이면 데이터를 Microsoft Office SharePoint Server 2007에서 SharePoint Server 2010으로 수동으로 이동하거나 특정 사이트 및 웹만 다음 버전으로 이동하도록 선택할 수 있습니다(작업을 더 쉽게 만들 수 있습니다).
    
3. SharePoint Server 2007 서버 Microsoft Office 팜에서 직접 업그레이드할 때 팜에 포함된 데이터가 더 안전합니다.
    
In-Place 업그레이드와 같은 방법은 Microsoft Office SharePoint Server 2007 팜에서 직접 실행되어 경로를 중단하고 기본 환경으로 다시 시작할 수 있는 더 적은 수의 간편한 옵션을 제공합니다. 가능한 한 일부 안전 조치(예: 원래 환경의 백업 작성 및 테스트)를 구축합니다. 예를 들어 Microsoft Office SharePoint Server 2007 팜이 가상으로 복제되어 백업 및 복원을 위해 복제된 경우 업그레이드를 위해 서비스 기간 전에 최신 데이터베이스를 백업 및 복원합니다. 데이터베이스 백업을 복원할 수 있는 옵션이 있는 경우 장애 조치(failsafe)가 제공될 뿐만 아니라 안심할 수 있습니다.
  
> [!TIP]
> [SharePoint Server 2007, SharePoint Server 2010 Microsoft Office SharePoint](https://technet.microsoft.com/library/cc261992%28v=office.12%29.aspx)Server [2013](https://technet.microsoft.com/library/cc261992%28v=office.14%29.aspx)및 [SharePoint Server 2016에](https://technet.microsoft.com/library/cc261992%28v=office.16%29.aspx)대한 업그레이드 모범 사례 문서가 있습니다. [](https://technet.microsoft.com/library/cc261992%28v=office.15%29.aspx) 업그레이드 또는 [Microsoft](https://partnercenter.microsoft.com/pcv/search) 365 마이그레이션 경험이 있는 Microsoft 파트너를 검색할 수도 있습니다. 
  
## <a name="make-your-plan"></a>계획 수립

업그레이드해야 하는 경우 계획이 필요하며 이러한 경우 한 크기로는 적합하지 않습니다. 요금제는 'SharePoint Online을 사용하여 Microsoft 365 구독을 만들고, 도메인을 등록하고, 사용자를 리디렉션하여 파일을 저장할 수 있도록 리디렉션'처럼 간단할 수 있습니다. 이 경우 안 될 수 있습니다. 이러한 결정은 사용자의 결정에 따라 결정됩니다.
  
> [!NOTE]
> 수명 주기가 종료된 소프트웨어에서 실행될 위험이 있습니다. 지원이 부재 중인 제품은 문제가 발견될 때 더 이상 패치가 없습니다. 즉, 새로운 보안 위협이 발생할 경우 수명 주기 제품 종료가 더 이상 지원되지 않는 보안 패치 또는 수정이 없습니다. 이 상황을 피하세요! 
  
### <a name="first-know-your-farm"></a>먼저 팜을 알아야 합니다.

업그레이드할 때 의사 결정은 팜이 조직에 대해 어떤 기능을 하는지 기준으로 해야 합니다. 충족해야 하는 것은 무엇입니까? 역할이란? 회사의 각 팜에는 다른 역할이 있을 수 있습니다. 일부 SharePoint 팜은  중요할 수 있습니다. 일부는 파일 보관 파일일 수 있습니다. 안전을 위해 보관할 수 있습니다. 또는 팜이 여러 역할을 동시에 채우는 경우 어떤 사이트 모음, 웹 또는 문서 라이브러리가 어떤 작업을 하는지, 사용자 지정 및 해당 역할이 얼마나 중요한지 알아야 할 수 있습니다. 이 수준에서 데이터를 분석하면 많은 작업으로 보일 수 있지만 업그레이드하거나 마이그레이션하기 전에 도메인을 마스터하기 위한 시간과 노력을 절약할 수 있습니다. 이동하는 모든 부분과 가장 중요한 비트를 알고 나면 사용자가 떠날 수 있는 부분을 알 수 있습니다. 이 지식은 앞으로도 도움이 됩니다. 
  
그렇다면 SharePoint Server 팜에 대해 가장 중요한 것은 무엇일까요?
  
- 기본 제공 SharePoint 기능
    
- 큰 데이터 폴더(예: 파일 보관)
    
- 사용 가능
    
- 팜의 중요 앱, 웹 파트 또는 docs(중요 중요 팜)
    
- 준수 표준 충족
    
- 사용자 지정 기능
    
SharePoint 팜에서 비즈니스에 필수적인 것을 실행하면 클라이언트 서비스 요구 사항에 대한 중요한 데이터의 큰 카탈로그와 같은 역할을 하게 될 경우 '중요 앱' 옆에 '중요 앱'과 '가용성'을 넣습니다. 즉, SharePoint를 한 동안 사용할 수 없는 경우 비즈니스에 영향을 줄 수 있습니다. 마찬가지로 팜에서 제공하는 중요한 서비스는 사용자 지정 코드, 사이트 정의 또는 함께 작동되는 여러 사용자 지정을 기반으로 하여 '사용자 지정'을 확인할 수 있습니다.
  
SharePoint가 소프트웨어에 기본 제공된 기능을 사용하는 것 외의 작업을 수행하지 않고도 이러한 요구를 충족하는 경우 일반적으로 이를 업데이트하고 정상적인 관리 및 유지 관리 작업을 수행한 경우 '기본 제공 SharePoint'를 선택한 것일 수 있습니다. 이는 이전 버전의 SharePoint를 사용하는 이유일 수도 있습니다. 즉, SharePoint Server 2007 지원이 종료될 때까지는 업그레이드에 필요한 Microsoft Office 않습니다.
  
이러한 항목의 목록을 글머리 기호로 표시하면 업그레이드 조건을 만들 수 있습니다. 즉, 모든 업그레이드를 고려하려면 이 표시줄을 충족해야 합니다. 이렇게 하면 현재 요구에 맞지 않는 메서드를 예외로 사용할 수 있습니다.
  
### <a name="a-simple-sample-plan"></a>간단한 샘플 계획

SharePoint 업그레이드가 진행될 경로에 리더십 및 다른 관리자와의 더 광범위한 합의가 필요할 수 있습니다. SharePoint Server 관리자는 종종 관리자와 Microsoft SQL Server 네트워킹 및 보안 팀과 협력합니다. 관련자가 많은 경우 업그레이드 및 마이그레이션 계획에 대한 계약을 구축하거나 조정해야 할 수 있습니다. 예를 들어 회사의 일부가 Microsoft 365에서 SharePoint Online을 사용하게 데이터를 마이그레이션하는 경우 네트워크 내에서 성능 조정 또는 테스트가 필요할 수 있습니다. 영향을 받는 팀은 미리 정보를 알려야 합니다.
  
간단한 샘플에서는 SharePoint 관리자의 제안을 표시한 다음 모든 이해 관계자가 동의한 계획을 나열합니다. 명확하게 설명하기 위해 계약 및 결정을 문서화합니다.
  
이 계획은 팜을 심도 있게 분석한 후 시작하여 팜의 역할, 문제 지점 및 일부 업그레이드 옵션의 범위를 좁힐 수 있는 기타 중요한 정보를 파악합니다. 이후에 SharePoint 관리자가 업그레이드 제안을 수행하고 관련자는 작업 계획에 동의합니다.
  
내 '가장 중요한' 글머리 기호 목록:
  
- 가용성, SharePoint에 기본 제공되는 기능 및 규정 준수 표준
    
- 대부분의 데이터는 세 개의 사이트 모음에 있으며, 하나의 모임 작업 영역은 개발자 팀에서 특히 중요하며 전 세계 여러 표준 시간대에서 많이 사용됩니다.
    
- 널리 사용되는 17개의 다른 사이트가 있습니다.
    
- 두 개의 문서 라이브러리(루트 사이트 모음의 모임 작업 영역 및 문서)가 최대(각각 8,000개가 넘는 문서)입니다. 스프레드시트 첨부 파일이 있는 보관된 문서 및 목록이 많이 있습니다.
    
- 규정 준수를 유지해야 하는 중요한 데이터가 있는 14개의 라이브러리 목록이 있습니다.
    
- 어디로든 보류 및 전자 검색을 할 수 있어야 합니다.
    
- 이 데이터 중 일부는 InfoSec 규칙으로 인해,프레미스에서 유지되어야 합니다.
    
 **내 업그레이드 및 마이그레이션 선택 사항:**
  
| 예 | 아니요 |
|:-----|:-----|
|데이터베이스 연결로 데이터베이스 업그레이드  <br/> |전체 업그레이드  <br/> |
|팜을 나란히 업그레이드  <br/> |하이브리드 업그레이드  <br/> |
|Microsoft 365에서 SPO로의 마이그레이션 API(개인 사이트 데이터용)  <br/> |SharePoint 하이브리드(아직 필요하지 않은)  <br/> |
|중요한 데이터를 위해 SharePoint Online으로 일부 수동 데이터 마이그레이션  <br/> |Microsoft 365로의 FastTrack 마법사 업그레이드  <br/> |
   
 **제안된 계획:**
  
데이터베이스를 먼저 업그레이드할 수 있도록 SharePoint 버전이 나란히 가상화되어 있는 프레미스에서 업그레이드합니다. SharePoint 2007에서 SharePoint 2010으로 이동 관리자 및 개발자는 결과 팜을 테스트합니다. 사용자는 결과 팜을 테스트합니다. 이 시간 동안 모든 표시 중지 문제를 해결합니다. 다시 한 번 SharePoint 2010 데이터베이스를 SharePoint 2013으로 업그레이드합니다. 테스트. 사용자 테스트/파일럿. 이 시간 동안 모든 표시 중지 문제를 해결합니다.
  
- SPO가 있는 Search Federated Hybrid가 요구 사항을 충족하는지 고려합니다.
    
- 여기서 SharePoint Online으로 업그레이드하려면 [FastTrack](https://fasttrack.microsoft.com) 지원을 고려하세요. 
    
- 사이트 모음을 Microsoft 365 구독으로 오프로드할 수 있는지 여부를 판단합니다. (Microsoft 365는 많은 [규정 준수 표준을 충족합니다.](https://technet.microsoft.com/library/office-365-compliance.aspx) Microsoft 365에는 [eDiscovery가](https://support.office.com/article/edea80d6-20a7-40fb-b8c4-5e8c8395f6da) 있으며 준수 센터를 [통해](https://support.office.com/article/A18F8975-AA7F-43B4-A7D6-001D14744D8E) 보류를 할 수 있습니다.) 
    
그렇지 않은 경우 SharePoint Server 2016으로 나란히 업그레이드를 계속합니다.
  
> [!NOTE]
> 업그레이드를 계획하는 관리자가 권장하는 사항과 실제 프로세스 사이에는 업그레이드가 의존하는 다른 관련자와 진행되는 대화가 있습니다. 예를 들어 경제성에 따라 관리자가 계획을 변경해야 하는 경우도 있습니다. 최종 결정이 무엇이든 합의된 계획을 문서화해야 합니다. 다음과 같이 될 수 있습니다. 
  
 **내 작업 계획:**
  
기본적으로 SharePoint Server 2010 및 2013을 빌드하기 위해 가상 환경을 사용했습니다. SharePoint Server 2016은 2016의 시스템 요구 사항을 충족하는 새 하드웨어를 기본으로 구축될 것입니다. SharePoint 2007에서 데이터베이스와 SharePoint Server 2016 간의 모든 버전을 통해 데이터베이스를 업그레이드하기 위해 데이터베이스 연결 작업을 진행합니다. 기본 기능이 요구 사항을 아직 충족하지 않는 경우 핵심 사용자 지정이 현재 SharePoint Server 2016 환경에서 다시 제작되고 테스트됩니다. 업그레이드가 성공하면 업그레이드된 데이터베이스가 있는 새 하드웨어에 프레미스 팜을 설치하고 사용자 지정 수를 줄입니다. 업그레이드된 콘텐츠 데이터베이스를 SharePoint Server 2013의 새 사이트 모음에 연결하고, 테스트, 사용자 테스트/파일럿을 진행한 다음 라이브 사용을 위해 새 SharePoint Server 2016 환경에 DNS를 컷오버합니다.
  
- 현재는 SharePoint Server 2016과 SharePoint Online 간에 페더러이트 하이브리드를 고려하지 않을 것입니다.
    
- 사이트의 약 35%를 베니티 도메인이 있는 새 SPO 사이트로 변경하거나 궁극적으로 비즈니스용 OneDrive 저장소로 사용할 수 있습니다. 사이트를 변환하거나 새 사이트를 SPO로 라우팅할 수 있는 다른 기회를 찾고 있습니다.
    
- 마이그레이션의 이 부분 중 일부는 비즈니스용 OneDrive 개인 사이트로 끌어서 놓기 및 마이그레이션 API를 통해 수동으로 수행됩니다.
    
보다 자세한 단계 또는 특정 업그레이드 방향에 대한 여러 링크는 계획을 따라야 합니다. MOSS 2007 컴퓨터는 해제하면 안 되고 가상 환경은 비교를 위해 유지 관리해야 합니다. 그러나 사용자가 SharePoint Server 2016으로 리디렉션될 때 업그레이드가 완료됩니다.
  
방법을 선택할 때의 주요 요인은 업그레이드의 총 비용과 시간 비용입니다(SharePoint 마이그레이션 로드맵 문서에서 더 많은 정보를 볼 수 있습니다). 그러나 미리 계획을 세우면 기대치를 설정하고 현명하게 선택하고 성공의 모양을 프레이밍할 때 큰 도움이 됩니다.
  
## <a name="related-links"></a>관련 링크

[Office 2007 서버 및 클라이언트에서 업그레이드하는 데 도움이 되는 리소스](upgrade-from-office-2007-servers-and-products.md)
  
[Microsoft 수명 주기 정책 및 수명 주기 검색](https://support.microsoft.com/lifecycle)
  
[업그레이드 또는 마이그레이션에 도움이 될 수 있는 Microsoft 파트너 검색](https://partnercenter.microsoft.com/pcv/search)
  

