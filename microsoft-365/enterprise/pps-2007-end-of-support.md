---
title: PerformancePoint Server 2007 지원 종료 로드맵
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
search.appverid:
- PSV120
- PDD140
- MET150
ms.assetid: 89d9feee-2285-419c-8c14-0f7f583536e0
f1.keywords:
- NOCSH
description: PerformancePoint Server 2007, ProClarity 및 SharePoint Server 2007의 지원이 종료됩니다. BI 솔루션 업그레이드를 계획하는 데 도움이 되는 이 문서를 읽어 보십시오.
ms.openlocfilehash: 4a13e6f8a40de78c0d98b03369b52a78899fc7a9
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519600"
---
# <a name="performancepoint-server-2007-end-of-support-roadmap"></a>PerformancePoint Server 2007 지원 종료 로드맵

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

OFFICE 2007 서버 및 응용 프로그램은 BI(비즈니스 인텔리전스) 솔루션의 일부로 사용할 수 있는 서버 및 응용 프로그램을 포함하여 지원이 종료되었습니다. 다음 표에는 영향을 받는 BI 응용 프로그램이 나열됩니다.
  
|**Microsoft BI 응용 프로그램**|**종료된 날짜 지원**|
|:-----|:-----|
|ProClarity Analytics Server 6.3 서비스 팩 3  <br/> ProClarity Desktop Professional 6.3  <br/> ProClarity SharePoint Viewer 6.3  <br/> |2017년 7월 11일  <br/> |
|SharePoint Server 2007 서비스 팩 3  <br/> |2017년 10월 10일  <br/> |
|PerformancePoint Server 2007 서비스 팩 3  <br/> |2018년 1월 9일  <br/> |
   
자세한 내용은 [Office 2007](upgrade-from-office-2007-servers-and-products.md)서버 및 클라이언트에서 업그레이드하는 데 도움이 되는 리소스를 참조하십시오.
  
## <a name="what-does-end-of-support-mean"></a>지원 *종료는 무엇을 의미하나요?*

대부분의 Microsoft 제품과 마찬가지로 PerformancePoint Server 2007 SP3, ProClarity 소프트웨어 및 SharePoint Server 2007 SP3에는 지원 수명 주기가 있습니다. 이 기간 동안 Microsoft는 새로운 기능, 버그 수정 및 보안 업데이트를 제공합니다. 제품의 수명 주기는 일반적으로 제품의 초기 릴리스부터 10년 동안 지속됩니다. 수명 주기의 끝을 제품의 지원 종료라고 합니다. ProClarity, PerformancePoint Server 및 SharePoint Server 2007이 지원 종료에 도달하면 Microsoft는 더 이상 다음을 제공하지 않습니다.
  
- 발생할 수 있는 문제에 대한 기술 지원
    
- 검색된 문제에 대한 버그 수정으로 서버의 안정성과 사용 가능성에 영향을 줄 수 있습니다.
    
- 검색된 취약점에 대한 보안 수정으로 서버 또는 응용 프로그램이 보안 침해에 취약해질 수 있습니다.
    
- 표준 시간대 업데이트.
    
ProClarity, SharePoint Server 2007 SP3 및 PerformancePoint Server 2007 SP3 설치는 지원이 종료된 경우에도 계속 실행됩니다. 그러나 이러한 응용 프로그램에서 가능한 한 빨리 마이그레이션하는 것이 좋습니다.
  
## <a name="what-are-my-options"></a>내 옵션은 무엇입니까?

2007년 이후로 Microsoft BI 응용 프로그램이 많이 변경되었습니다. 다음 표에 요약된 몇 가지 옵션을 고려해야 합니다.
  
|**사용 중이면...**|**다음 옵션 살펴보기...**|**그리고 이 사실에 유의해야 합니다.**|
|:-----|:-----|:-----|
| PerformancePoint Server 다음을 비롯한 2007 Monitoring &amp; Analytics 기능<br/>- PerformancePoint 모니터링 서버 <br/>- PerformancePoint 대시보드 디자이너<br/>- 대시보드 뷰어 for SharePoint Services(PerformancePoint 대시보드, 성과 기록표 및 보고서 렌더링에 사용)<br/> |**브라우저에서 Excel을 사용하는** Excel(클라우드 또는 On-premises)입니다. 개요는 Excel 및 [Microsoft 365의 BI 기능을 참조하세요.](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx)<br/><br/> **Power BI(클라우드** 또는 프레미스) 개요는 Power [BI란?](https://go.microsoft.com/fwlink/?linkid=841341) <br/><br/> **SQL Server Reporting** Services(-프레미스) 개요는 SQL Server [Reporting Services(SSRS):](https://go.microsoft.com/fwlink/?linkid=841342)모바일 및 페이지가 추가된 보고서를 만들고 배포하고 관리합니다. <br/><br/>  PerformancePoint Services(-프레미스). 개요는 [PerformancePoint Services(SharePoint Server 2010)를 참조하세요.](https://go.microsoft.com/fwlink/?linkid=841343) <br/> |Excel은 온라인(클라우드 기반) 또는온-프레미스 솔루션으로 사용할 수 있습니다. Excel에서는 많은 보고 및 대시보드 요구 사항을 충족할 수 있습니다.  <br/><br/> Power BI는 온라인 또는온-프레미스 솔루션으로 사용할 수 있습니다. Power BI는 Microsoft 365에 포함되어 있지 않습니다. 그러나 Power BI 사용을 무료로 시작할 수 있습니다. 나중에 데이터 사용량 및 비즈니스 요구에 따라 Microsoft 365 E5를 사용하여 Power BI Pro로 업그레이드할 수 있습니다.<br/> <br/> Reporting Services 및 PerformancePoint Services 솔루션 모두입니다. <br/><br/> PerformancePoint Services SharePoint Server 2010, SharePoint Server 2013 및 SharePoint Server 2016에서 사용할 수 있습니다. <br/> <br/> PerformancePoint Server 2007에서 사용할 수 있는 일부 기능 및 보고서 유형은 Excel, Power BI, Reporting Services 또는 PerformancePoint Services. 사용 가능한 기능을 검토하여 비즈니스 요구에 가장 적합한 솔루션을 결정하십시오. <br/> |
| 다음을 포함한 ProClarity 소프트웨어<br/>- ProClarity Desktop Professional<br/> - ProClarity Analytics Server<br/>- ProClarity SharePoint Viewer<br/> |**Microsoft 파트너와** 협력하여 요구 사항을 가장 잘 충족하는 솔루션을 식별합니다. Microsoft 파트너 [센터를 방문하세요.](https://go.microsoft.com/fwlink/?linkid=841249) <br/><br/> Excel과 함께 브라우저, Power BI, reporting Services 또는 SQL Server Excel을 사용할 수도 PerformancePoint Services.  <br/> |Excel, Power BI, Reporting Services 및 ProClarity를 비롯한 다른 Microsoft 제품에서는 ProClarity 소프트웨어의 일부 기능을 사용할 수 PerformancePoint Services.  <br/> |
|SharePoint Server 2007 KPIS(MOSS KP라고도 하는)  <br/> |**Excel에서 Excel Services.** 개요는 Excel 및 [Excel Services(SharePoint Server 2013)의](https://support.office.com/article/2740f10c-579d-4b40-a1d9-7beb5d38547c.aspx)비즈니스 인텔리전스를 참조하십시오. <br/> |SharePoint Server 2007을 사용하여 만든 MOSS KP는 SharePoint Server 2010, SharePoint Server 2013 및 SharePoint Server 2016에서 사용할 수 있습니다. 그러나 새 MOSS KP는 만들 수 없습니다.  <br/> |
|Excel 2007  <br/> |**Excel(클라우드** 또는 프레미스) 개요는 Excel 및 [Office 365의 BI 기능을 참조하세요.](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx) <br/><br/> **Power BI(클라우드** 또는 프레미스) 개요는 Power [BI란?](https://go.microsoft.com/fwlink/?linkid=841341) <br/> |Excel과 Power BI는 모두 다양한 데이터 원본을 지원하며 조직 클라우드 기반 및 프레미스 솔루션을 제공합니다.  <br/> |
   
### <a name="help-selecting-a-solution"></a>해결 방법 선택 도움말

사용할 수 있는 BI 선택이 너무 많을 경우 어떤 옵션이 가장 적합한지 결정하는 것이 부담스러웠을 수 있습니다. 온라인 가이드를 통해 도움을 줄 수 있습니다. 분석 및 보고를 위한 [Microsoft BI(비즈니스 인텔리전스) 도구 선택을 참조합니다.](https://go.microsoft.com/fwlink/?linkid=839877)
  
### <a name="what-if-i-dont-upgrade-now"></a>지금 업그레이드하지 않는 경우 어떻게 하나요?

즉시 업그레이드하지 않을 수 있습니다. 기존 서버 및 응용 프로그램이 계속 실행됩니다. 하지만 지원이 종료된 이후 보안 업데이트를 포함하여 추가 업데이트를 받지 못합니다. 또한 서버 응용 프로그램에 문제가 있는 경우 Microsoft 기술 지원 서비스에서 도움을 받을 수 없습니다.
  
## <a name="how-do-i-plan-my-upgrade"></a>업그레이드를 계획하려면 어떻게 해야 합니까?

업그레이드 옵션을 살펴보고 나면 다음 단계는 업그레이드 계획을 준비하는 것입니다. 다음 섹션에는 도움이 되는 정보와 추가 리소스가 포함되어 있습니다. 클라우드 또는 On-premises에서 모두 작동 하는 두 개와 두 개의 기본 옵션(두 개의 기본 옵션 포함)이 있습니다.
  
|**옵션**|**클라우드 또는 프레미스에 있나요?**|
|:-----|:-----|
|[SharePoint Server가 있는 Excel(-프레미스)](#excel-with-sharepoint-server-on-premises) <br/> |둘 다  <br/> |
|[Power BI](#use-power-bi-in-the-cloud-or-on-premises)<br/> |둘 다  <br/> |
|[보고 서비스](#use-reporting-services-on-premises) <br/> |On-premises only(프레미스만 해당)  <br/> |
|[PerformancePoint Services](#use-performancepoint-services-on-premises) <br/> |On-premises only(프레미스만 해당)  <br/> |
   
### <a name="use-excel-in-the-cloud-or-on-premises"></a>Excel 사용(클라우드 또는 프레미스에서)

SharePoint Server에서 통합  Excel Services Excel을 사용하면 컴퓨터에 Excel이 설치되어 있지 않은 경우에도 브라우저 창에서 통합 문서가 표시 및 사용할 수 있습니다. Excel을 사용하여 보고서, 점수 기록표 및 대시보드를 만들 수 있습니다. 그런 다음 Microsoft 365 또는 SharePoint Server의 일부로 SharePoint Online을 사용 중이든, 브라우저에서 Excel을 사용할 수 있는 다른 사용자와 통합 문서 공유 다양한 데이터 원본을 사용할 수 있도록 하여, 클라우드 또는프레미스에 저장된 데이터를 사용할 수 있습니다.
  
다음 표에서는 Microsoft 365에서 Excel을 사용하여 SharePoint Server에서 Excel을 사용할 때의 주요 이점을 비교합니다. 자세한 내용은 다음과 같습니다.
  
|**Microsoft 365가 있는 Excel(클라우드)**|**SharePoint Server가 있는 Excel(-프레미스)**|
|:-----|:-----|
|**최신 버전의 Excel을 다운로드할 수 있습니다.** Microsoft 365에서는 강력한 새 차트 유형, 쉽고 빠르게 차트 및 표를 만드는 능력, 더 많은 데이터 원본에 대한 지원이 포함된 최신 버전의 Excel을 사용할 수 있습니다. <br/> <br/> **설치가 훨씬 간단합니다.** Excel은 비즈니스용 Microsoft 365에 포함되어 있으므로 큰 부담이 없습니다. 등록 및 로그인하면, 등록하고, 더 빠르고 효율적으로 등록하고 실행하게 됩니다. <br/> <br/> **모든 사용자들이 통합 문서에 액세스할 수 있습니다.** 컴퓨터, 스마트폰 및 태블릿을 사용하여 어디에서든 통합 문서가 안전하게 볼 수 있습니다. <br/> <br/> **거기 더 있어!** [Excel 및 Office 365의 BI 기능을 참조합니다.](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx) <br/> |**전역 설정을 관리합니다.** SharePoint 관리자는 보안, 부하 분산, 세션 관리, 통합 문서 캐싱 및 외부 데이터 연결과 같은 전역 설정을 지정할 수 있습니다. <br/> <br/> **다음에서 Excel Services 사용할 PerformancePoint Services.** SharePoint Server Excel Services PerformancePoint Services 구성하고 PerformancePoint 대시보드에 Excel Services 보고서를 포함할 수 있습니다. <br/> <br/> **거기 더 있어!** Excel [및 Excel Services(SharePoint Server 2013)의](https://support.office.com/article/2740f10c-579d-4b40-a1d9-7beb5d38547c.aspx)비즈니스 인텔리전스를 참조합니다. <br/> |
   
#### <a name="excel-with-microsoft-365-in-the-cloud"></a>Microsoft 365가 있는 Excel(클라우드)

Microsoft 365로 이동하는 경우 Excel 2016을 비롯한 최신 서비스 및 응용 프로그램이 있습니다. PerformancePoint Services Microsoft 365에서는 사용할 수 없습니다. 따라서 PerformancePoint 대시보드 콘텐츠를 Excel 통합 문서 또는 기타 보고서로 대체하게 됩니다. 다행하게도 Excel 2016에는 새로운 차트 유형이 많이 있으며 Excel에서 대시보드를 보다 쉽게 만들 수 있습니다. 또한 새로운 기능은 정기적으로 추가됩니다. 자세한 내용은 [Windows용 Excel 2016의](https://support.office.com/article/5fdb9208-ff33-45b6-9e08-1f5cdb3a6c73.aspx)새로운 내용을 참조합니다.
  
또한 사용자 수가 50명 이상인 Microsoft 365를 구매하는 경우 Microsoft FastTrack 팀에서 설정하는 데 도움을 줄 수 있습니다. 자세한 내용은 [FastTrack을 방문합니다.](https://www.microsoft.com/fasttrack/microsoft-365)
  
#### <a name="excel-with-sharepoint-server-on-premises"></a>SharePoint Server가 있는 Excel(-프레미스)

최신 버전의 SharePoint로 업그레이드하는 경우 다음과 같이 Excel Services 또는 브라우저에서 Excel을 사용할 수 있습니다.
  
- Excel Services SharePoint Server 2010의 경우
    
- SharePoint Server 2013의 Excel Services
    
- Office Online Server의 일부인 Excel은 SharePoint Server 2016과 별도로 설치됩니다.
    
새 PerformancePoint Services SharePoint Server에서 구성하고 Excel과 함께 사용할 수 있습니다.
  
SharePoint 업그레이드 옵션에 대한 자세한 내용은 [SharePoint Server 2007 지원 종료 로드맵을 참조하세요.](sharepoint-2007-end-of-support.md)
  
자세한 내용은 Excel Services [개요(SharePoint Server Excel Services)를 참조하세요.](https://go.microsoft.com/fwlink/?linkid=841362)
  
### <a name="use-power-bi-in-the-cloud-or-on-premises"></a>Power BI 사용(클라우드 또는 프레미스에서)

Power BI는 데이터를 분석하고 정보를 공유하는 비즈니스 분석 도구 모음입니다. Power BI를 사용하면 온라인 데이터 원본 또는온-프레미스를 사용하여 대화형 보고서 및 대시보드를 만들 수 있습니다. 사용자 컴퓨터 또는 모바일 장치에서 보고서 및 대시보드를 보고 사용할 수 있습니다.
  
Power BI는 Microsoft 365 또는 SharePoint Server에 참여하지 않습니다. Power BI Desktop, Power BI 게이트웨이 및 Power BI 서비스를 포함하는 별도의 제품입니다. Power BI는 SharePoint Online과도 통합됩니다. Power BI를 무료로 시작할 수 있습니다. 데이터 사용 및 비즈니스 요구에 따라 나중에 Microsoft 365 E5를 사용하여 Power BI Pro로 업그레이드할 수 있습니다. 자세한 내용은 [Power BI란?](https://go.microsoft.com/fwlink/?linkid=841341)
  
### <a name="use-reporting-services-on-premises"></a>Reporting Services 사용(-프레미스)

SQL Server Reporting Services는 강력한 보고 솔루션을 제공합니다. Reporting Services는 기본 모드 또는 SharePoint 통합 모드로 구성할 수 있습니다. 보고서 디자이너, 보고서 작성기 및 보고서 작성기 등의 다양한 도구를 사용하여 보고서를 Power View. 최신 릴리스의 SQL Server 모바일 보고서 게시자를 사용하여 SQL Server 크기에 따라 확장되는 보고서를 제공할 수 있습니다. 이를 통해 사용자는 모바일 장치에서 보고서를 사용할 수 있습니다. 자세한 내용은 [SQL Server Reporting Services(SSRS):](https://go.microsoft.com/fwlink/?linkid=841342)모바일 및 페이지가 추가된 보고서 만들기, 배포 및 관리.를 참조하세요.
  
### <a name="use-performancepoint-services-on-premises"></a>사용 PerformancePoint Services(-프레미스)

PerformancePoint Server 2007은 SharePoint Server 2007과 별도로 판매됩니다. SharePoint Server 2010부터 PerformancePoint Services 응용 프로그램은 SharePoint Server의 서비스 응용 프로그램입니다. 따라서 별도의 서버 라이선스 또는 하드웨어를 구입하여 해당 라이선스를 사용할 PerformancePoint Services.
  
2007에서 PerformancePoint Server 2007로 PerformancePoint Services SharePoint Server의 최신 버전으로 이동하고 해당 버전을 PerformancePoint Services. 이동하는 SharePoint Server 버전에 따라 기존 대시보드 콘텐츠를 PerformancePoint Server 2007에서 대시보드로 가져올 수 PerformancePoint Services.
  
- SharePoint Server 2010으로 업그레이드하는 경우 PerformancePoint 대시보드 콘텐츠를 PerformancePoint Server 2007에서 SharePoint Server 2010의 PerformancePoint Services 가져올 수 있습니다. 자세한 내용은 [가져오기 마법사: PerformancePoint Server 2007 콘텐츠를 SharePoint Server 2010으로 가져오기.를 참조하세요.](https://go.microsoft.com/fwlink/?linkid=838873)
    
- SharePoint Server 2013 또는 SharePoint Server 2016으로 이동하는 경우 새 대시보드 콘텐츠(데이터 원본, 보고서, 점수 기록표 및 대시보드 페이지)를 만들어야 할 수 있습니다.
    
업그레이드 PerformancePoint Services 시작하려면 다음 리소스를 참조합니다.
  
- [SharePoint Server 2007 지원 종료 로드맵](sharepoint-2007-end-of-support.md)
    
- 이동하는 SharePoint 버전을 알고 있는 경우 다음에 대한 해당 문서를 PerformancePoint Services.
    
  - [PerformancePoint Services 계획(SharePoint Server 2010)](https://go.microsoft.com/fwlink/?linkid=841363)
    
  - [SharePoint Server 2013의 PerformancePoint Services 개요](https://go.microsoft.com/fwlink/?linkid=841551)
    
  - [SharePoint Server 2016의 PerformancePoint Services 개요](https://go.microsoft.com/fwlink/?linkid=874704)
    
새 기능으로 업그레이드할 PerformancePoint Services 몇 가지 새로운 기능과 향상된 기능이 있습니다. PerformancePoint Services 개선된 점수 기록표를 제공합니다. 분해 트리 및 KPI 세부 정보 보고서와 같은 새 시각화 더 많은 차트 유형; 더 나은 시간 인텔리전스 필터링 기능 및 향상된 접근성 준수. 자세한 내용은 새로운 [PerformancePoint Services(SharePoint Server 2010)를 참조합니다.](https://go.microsoft.com/fwlink/?linkid=841343)
  
## <a name="where-can-i-get-help-with-my-upgrade"></a>업그레이드에 대한 도움말은 어디에서 얻을 수 있나요?

프레미스에서 업그레이드하거나 Microsoft 365로 이동하는 경우 Microsoft 파트너와 함께 작업하는 것이 좋습니다. 적격 파트너는 비즈니스 요구를 가장 잘 충족하고 배포에 도움이 되는 솔루션을 식별하는 데 도움을 줄 수 있습니다. Microsoft 파트너 [센터를 방문하고](https://go.microsoft.com/fwlink/?linkid=841249)검색 필터를 사용하여 솔루션 공급자를 찾을 수 있습니다.
  
## <a name="related-topics"></a>관련 항목

[Office 2007 서버 및 클라이언트에서 업그레이드하는 데 도움이 되는 리소스](upgrade-from-office-2007-servers-and-products.md)