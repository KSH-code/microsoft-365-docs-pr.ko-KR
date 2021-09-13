---
title: PerformancePoint Server 2007 지원 종료 로드맵
ms.author: kvice
author: kelleyvice-msft
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
ms.openlocfilehash: 88818fe4ecc0a2be7a63abe615bd4206c50ead3b
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59220780"
---
# <a name="performancepoint-server-2007-end-of-support-roadmap"></a>PerformancePoint Server 2007 지원 종료 로드맵

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

Office 2007 서버 및 응용 프로그램은 BI(비즈니스 인텔리전스) 솔루션의 일부로 사용할 수 있는 서버 및 응용 프로그램을 포함하여 지원이 종료되었습니다. 다음 표에는 영향을 받는 BI 응용 프로그램이 나열됩니다.
  
|**Microsoft BI 응용 프로그램**|**종료된 날짜 지원**|
|:-----|:-----|
|ProClarity Analytics Server 6.3 서비스 팩 3  <br/> ProClarity Desktop Professional 6.3  <br/> ProClarity SharePoint Viewer 6.3  <br/> |2017년 7월 11일  <br/> |
|SharePoint Server 2007 서비스 팩 3  <br/> |2017년 10월 10일  <br/> |
|PerformancePoint Server 2007 서비스 팩 3  <br/> |2018년 1월 9일  <br/> |
   
자세한 내용은 [Office 2007 서버](upgrade-from-office-2007-servers-and-products.md)및 클라이언트에서 업그레이드하는 데 도움이 되는 리소스를 참조하세요.
  
## <a name="what-does-end-of-support-mean"></a>지원 *종료는 무엇을 의미하나요?*

대부분의 Microsoft 제품과 마찬가지로 PerformancePoint Server 2007 SP3, ProClarity 소프트웨어 및 SharePoint Server 2007 SP3도 지원 수명 주기를 가지며, 이 기간 동안 Microsoft는 새로운 기능, 버그 수정 및 보안 업데이트를 제공합니다. 제품의 수명 주기는 일반적으로 제품의 초기 릴리스로부터 10년 동안 지속됩니다. 이 수명 주기의 끝을 제품의 지원 종료라고 합니다. ProClarity, PerformancePoint Server 및 SharePoint Server 2007이 지원 종료에 도달하면 Microsoft는 더 이상 다음을 제공하지 않습니다.
  
- 발생할 수 있는 문제에 대한 기술 지원
    
- 검색된 문제에 대한 버그 수정으로, 서버의 안정성과 사용 가능성에 영향을 줄 수 있습니다.
    
- 검색된 취약점에 대한 보안 수정으로, 서버 또는 응용 프로그램이 보안 위반에 취약해질 수 있습니다.
    
- 표준 시간대 업데이트.
    
ProClarity, SharePoint Server 2007 SP3 및 PerformancePoint Server 2007 SP3 설치는 지원이 종료된 경우에도 계속 실행됩니다. 그러나 이러한 응용 프로그램에서 가능한 한 빨리 마이그레이션하는 것이 좋습니다.
  
## <a name="what-are-my-options"></a>내 옵션은 무엇입니까?

2007년 이후로 Microsoft BI 응용 프로그램이 많이 변경되었습니다. 다음 표에 요약된 몇 가지 옵션을 고려해야 합니다.
  
|**사용 중이면...**|**다음 옵션 살펴보기...**|**그리고 이 사실에 유의해야 합니다.**|
|:-----|:-----|:-----|
| PerformancePoint Server 2007 모니터링 &amp; 분석 기능에는 다음이 있습니다.<br/>- PerformancePoint 모니터링 서버 <br/>- PerformancePoint 대시보드 디자이너<br/>- 대시보드 뷰어 for SharePoint Services(PerformancePoint 대시보드, 성과 기록표 및 보고서 렌더링에 사용)<br/> |**Excel(Excel** 또는 클라우드의 경우)에서 사용할 수 있습니다. 개요는 에서 BI 기능을 Excel [및 Microsoft 365.](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx)<br/><br/> **Power BI(클라우드** 또는 사내) 개요는 What [is Power BI?](https://go.microsoft.com/fwlink/?linkid=841341) <br/><br/>  SQL Server Reporting Services(사내). 개요는 [SQL Server Reporting Services(SSRS): 모바일](/sql/reporting-services/create-deploy-and-manage-mobile-and-paginated-reports)및 패지통 보고서 만들기, 배포 및 관리를 참조하세요. <br/><br/>  PerformancePoint Services(사내). 개요는 [What's new for PerformancePoint Services (SharePoint Server 2010)을 참조하십시오.](/previous-versions/office/sharepoint-server-2010/ee661741(v=office.14)) <br/> |Excel(클라우드 기반) 또는 온라인 솔루션으로 사용할 수 있습니다. 많은 보고 및 대시보드 요구 사항을 충족할 수 Excel.  <br/><br/> Power BI 또는 온라인 솔루션으로 사용할 수 있습니다. Power BI 에 포함되어 있지 Microsoft 365. 그러나 무료로 Power BI 수 있습니다. 나중에 데이터 사용량 및 비즈니스 요구에 따라 데이터 사용 현황 및 비즈니스 요구에 따라 업그레이드를 Power BI Pro 수 Microsoft 365 E5.<br/> <br/> Reporting Services 및 PerformancePoint Services 모두 사내 솔루션입니다. <br/><br/> PerformancePoint Services Server 2010, SharePoint SharePoint Server 2013 및 SharePoint Server 2016에서 사용할 수 있습니다. <br/> <br/> PerformancePoint Server 2007에서 사용할 수 있는 일부 기능 및 보고서 유형은 Excel, Power BI, Reporting Services 또는 PerformancePoint Services. 사용 가능한 기능을 검토하여 비즈니스 요구에 가장 적합한 솔루션을 결정하십시오. <br/> |
| ProClarity 소프트웨어( 다음 포함)<br/>- ProClarity Desktop Professional<br/> - ProClarity Analytics Server<br/>- ProClarity SharePoint 뷰어<br/> |**Microsoft 파트너와 협력하여** 요구 사항을 가장 잘 충족하는 솔루션을 식별합니다. Microsoft 파트너 [센터를 방문하세요.](https://go.microsoft.com/fwlink/?linkid=841249) <br/><br/> 또한 브라우저, Excel, Excel 또는 Power BI, SQL Server Reporting Services 또는 PerformancePoint Services.  <br/> |ProClarity 소프트웨어의 일부 기능이 아닌 일부 기능은 Excel, Power BI, Reporting Services 및 기타 Microsoft 서비스에서 사용할 PerformancePoint Services.  <br/> |
|SharePoint Server 2007 KPIS(MOSS KPIS라고도 불리며)  <br/> |**Excel 를 Excel Services.** 개요는 Excel [and Excel Services (SharePoint Server 2013)의](https://support.office.com/article/2740f10c-579d-4b40-a1d9-7beb5d38547c.aspx)비즈니스 인텔리전스를 참조하십시오. <br/> |SharePoint Server 2007을 사용하여 만든 MOSS KP는 SharePoint Server 2010, SharePoint Server 2013 및 SharePoint Server 2016에서 사용할 수 있습니다. 그러나 새 MOSS KP는 만들 수 없습니다.  <br/> |
|Excel 2007  <br/> |**Excel(클라우드** 또는 사내) 개요는 에서 BI 기능을 Excel [및 Office 365.](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx) <br/><br/> **Power BI(클라우드** 또는 사내) 개요는 What [is Power BI?](https://go.microsoft.com/fwlink/?linkid=841341) <br/> |두 Excel Power BI 모두 다양한 데이터 원본에 대한 지원을 통해 조직 클라우드 기반 및 사내 솔루션을 제공합니다.  <br/> |
   
### <a name="help-selecting-a-solution"></a>해결 방법 선택 도움말

사용할 수 있는 BI 선택이 너무 많을 경우 어떤 옵션이 가장 적합한지 결정하는 것이 부담스러웠을 수 있습니다. 지원할 수 있는 온라인 가이드가 있습니다. 분석 및 보고를 [위한 Microsoft BI(비즈니스 인텔리전스) 도구 선택을 참조합니다.](/sql/reporting-services/choosing-microsoft-business-intelligence-bi-tools-for-analysis-and-reporting)
  
### <a name="what-if-i-dont-upgrade-now"></a>지금 업그레이드하지 않는 경우 어떻게 하나요?

즉시 업그레이드하지 않을 수 있습니다. 기존 서버 및 응용 프로그램이 계속 실행됩니다. 하지만 지원이 종료된 이후 보안 업데이트를 비롯한 추가 업데이트는 받지 않습니다. 또한 서버 응용 프로그램에 문제가 있는 경우 Microsoft 기술 지원에서 도움을 받을 수 없습니다.
  
## <a name="how-do-i-plan-my-upgrade"></a>업그레이드를 계획하려면 어떻게 해야 합니까?

업그레이드 옵션을 살펴보고 나면 다음 단계는 업그레이드 계획을 준비하는 것입니다. 다음 섹션에는 도움이 되는 정보 및 추가 리소스가 포함되어 있습니다. 다음과 같은 네 가지 기본 옵션(클라우드 또는 사내에서 모두 작동하고 두 개의 기본 옵션은 클라우드 또는 사내에서만 작동) 및 다음 2개의 기본 옵션이 있습니다.
  
|**옵션**|**클라우드 또는 사내에 있나요?**|
|:-----|:-----|
|[Excel 서버(SharePoint 사용)](#excel-with-sharepoint-server-on-premises) <br/> |둘 다  <br/> |
|[Power BI](#use-power-bi-in-the-cloud-or-on-premises)<br/> |둘 다  <br/> |
|[보고 서비스](#use-reporting-services-on-premises) <br/> |On-premises only(사내 전용)  <br/> |
|[PerformancePoint Services](#use-performancepoint-services-on-premises) <br/> |On-premises only(사내 전용)  <br/> |
   
### <a name="use-excel-in-the-cloud-or-on-premises"></a>클라우드 Excel(클라우드 또는 사내) 사용

Excel 서버의 Excel Services SharePoint 서버라고도 하는 Excel 사용하면 컴퓨터에 통합 문서가 설치되어 있지 않은 경우에도 브라우저 창에서 통합 Excel 볼 수 있습니다.  보고서, Excel 및 대시보드를 만들 수 있습니다. 그런 다음 Excel Online을 SharePoint 또는 SharePoint Server의 일부로 사용하는 경우 브라우저에서 통합 Microsoft 365 사용할 수 있는 다른 사용자와 통합 SharePoint 공유합니다. 사내 또는 클라우드에 저장된 데이터를 사용하여 다양한 데이터 원본을 사용할 수 있습니다.
  
다음 표에서는 Excel 서버와 함께 Microsoft 365 사용할 때의 주요 Excel SharePoint 비교합니다. 자세한 내용은 다음과 같습니다.
  
|**Excel Microsoft 365(클라우드)**|**Excel 서버(SharePoint 사용)**|
|:-----|:-----|
|최신 버전의 을 다운로드할 수 **Excel.** 이 Microsoft 365 사용하면 강력한 새 차트 유형, 쉽고 빠르게 차트 및 표를 만드는 Excel, 더 많은 데이터 원본 지원이 포함된 최신 버전의 차트를 얻을 수 있습니다. <br/> <br/> **설치가 훨씬 더 간단합니다.** Excel 비즈니스용 Microsoft 365 포함되어 있으므로 업무에 큰 부담이 없습니다. 등록하고 로그인하면, 등록하고, 더 빠르고 효율적으로 등록하고 실행하게 됩니다.프레미스 서버를 업그레이드하는 경우보다 더 빠르고 효율적으로 작업할 수 있습니다. <br/> <br/> **모든 사용자들이 통합 문서에 액세스할 수 있습니다.** 컴퓨터, 스마트폰 및 태블릿을 사용하여 어디에서든 통합 문서가 안전하게 볼 수 있습니다. <br/> <br/> **거기 더 있어!** 에서 [BI 기능을 Excel 및 Office 365.](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx) <br/> |**전역 설정을 관리합니다.** 보안 SharePoint, 부하 분산, 세션 관리, 통합 문서 캐싱 및 외부 데이터 연결과 같은 전역 설정을 지정할 수 있습니다. <br/> <br/> **에서 Excel Services 사용할 PerformancePoint Services.** SharePoint 서버 Excel Services PerformancePoint Services 구성하고 PerformancePoint 대시보드에 Excel Services 보고서를 포함할 수 있습니다. <br/> <br/> **거기 더 있어!** Excel [Excel Services(SharePoint Server 2013)의](https://support.office.com/article/2740f10c-579d-4b40-a1d9-7beb5d38547c.aspx)비즈니스 인텔리전스를 참조합니다. <br/> |
   
#### <a name="excel-with-microsoft-365-in-the-cloud"></a>Excel Microsoft 365(클라우드)

새 서비스로 Microsoft 365 서비스 및 응용 프로그램을 포함하여 최신 서비스 및 응용 프로그램을 Excel 2016. PerformancePoint Services 사용할 수 Microsoft 365 수 있으므로 PerformancePoint 대시보드 콘텐츠를 통합 문서 또는 Excel 대체하게 됩니다. 다행인 Excel 2016 차트 종류가 매우 많기 때문에 대시보드를 보다 쉽게 만들 수 Excel. 또한 새로운 기능은 정기적으로 추가됩니다. 자세한 내용은 에 대한 새로운 Excel 2016 [Windows.](https://support.office.com/article/5fdb9208-ff33-45b6-9e08-1f5cdb3a6c73.aspx)
  
또한 사용자 수가 50명 이상인 경우 Microsoft 365 Microsoft FastTrack 팀이 설정하는 데 도움을 줄 수 있습니다. 자세한 내용은 [을(를) FastTrack.](https://www.microsoft.com/fasttrack/microsoft-365)
  
#### <a name="excel-with-sharepoint-server-on-premises"></a>Excel 서버(SharePoint 사용)

최신 버전의 SharePoint 업그레이드하는 경우 다음과 Excel 또는 브라우저에서 Excel Services 사용할 수 있습니다.
  
- Excel Services Server 2010의 SharePoint
    
- SharePoint Server 2013의 Excel Services
    
- Excel Server 2016과 별도로 Office Online Server 설치되는 SharePoint
    
새 PerformancePoint Services Server에서 SharePoint 구성하고 새 서버와 함께 Excel.
  
업그레이드 옵션에 대한 SharePoint 자세한 내용은 SharePoint [Server 2007 지원 종료 로드맵 을 참조하세요.](sharepoint-2007-end-of-support.md)
  
자세한 내용은 Excel Services overview [(Excel Services Server 2010)를](/previous-versions/office/sharepoint-server-2010/ee424405(v=office.14))참조하십시오 SharePoint.
  
### <a name="use-power-bi-in-the-cloud-or-on-premises"></a>클라우드 Power BI(클라우드 또는 사내) 사용

Power BI 데이터를 분석하고 정보를 공유하는 비즈니스 분석 도구 모음입니다. 이 Power BI 또는 온라인 데이터 원본을 사용하여 대화형 보고서 및 대시보드를 만들 수 있습니다. 사용자 컴퓨터 또는 모바일 장치에서 보고서 및 대시보드를 보고 사용할 수 있습니다.
  
Power BI 서버 또는 Microsoft 365 SharePoint 않습니다. 이 서비스는 Power BI Desktop 게이트웨이 및 Power BI 서비스를 포함하는 별도의 Power BI 제공합니다. Power BI Online과 SharePoint 통합됩니다. 무료로 Power BI 수 있습니다. 데이터 사용량 및 비즈니스 요구에 따라 나중에 데이터 사용 현황 및 비즈니스 요구 사항을 Power BI Pro 수 Microsoft 365 E5. 자세한 내용은 What [is Power BI?](https://go.microsoft.com/fwlink/?linkid=841341)
  
### <a name="use-reporting-services-on-premises"></a>Reporting Services 사용(사내)

SQL Server Reporting Services 강력한 보고 솔루션을 제공합니다. Reporting Services는 기본 모드 또는 통합 모드로 SharePoint 수 있습니다. 보고서 디자이너, 보고서 및 보고서 작성을 비롯한 여러 가지 도구를 Report Builder 수 Power View. 최신 버전의 SQL Server 모바일 보고서 SQL Server 사용하여 Publisher 크기에 따라 확장되는 보고서를 제공할 수 있습니다. 이렇게 하면 뷰어가 모바일 장치에서 보고서를 사용할 수 있습니다. 자세한 내용은 [SQL Server Reporting Services(SSRS): 모바일](/sql/reporting-services/create-deploy-and-manage-mobile-and-paginated-reports)및 패지통 보고서 만들기, 배포 및 관리를 참조하세요.
  
### <a name="use-performancepoint-services-on-premises"></a>사용 PerformancePoint Services(사내)

PerformancePoint Server 2007은 SharePoint Server 2007과는 별도로 판매됩니다. SharePoint Server 2010부터 PerformancePoint Services 서버의 서비스 응용 SharePoint 있습니다. 따라서 별도의 서버 라이선스 또는 하드웨어를 구입하여 해당 라이선스를 사용할 PerformancePoint Services.
  
PerformancePoint Server 2007에서 PerformancePoint Services 이동하기 위해 최신 버전의 SharePoint Server로 이동하고 PerformancePoint Services. 이동하는 SharePoint 서버 버전에 따라 기존 대시보드 콘텐츠를 PerformancePoint Server 2007에서 대시보드로 가져올 수 PerformancePoint Services.
  
- SharePoint Server 2010으로 업그레이드하는 경우 PerformancePoint 대시보드 콘텐츠를 PerformancePoint Server 2007에서 PerformancePoint Services Server 2010의 SharePoint 수 있습니다. 자세한 내용은 [Import Wizard: PerformancePoint Server 2007 content to SharePoint Server 2010을 참조하세요.](/previous-versions/office/sharepoint-server-2010/ee681485(v=office.14))
    
- SharePoint Server 2013 또는 SharePoint Server 2016으로 이동하는 경우 새 대시보드 콘텐츠(데이터 원본, 보고서, 성 기록표 및 대시보드 페이지)를 만들어야 할 수 있습니다.
    
업그레이드 PerformancePoint Services 시작하려면 다음 리소스를 참조합니다.
  
- [SharePoint Server 2007 지원 종료 로드맵](sharepoint-2007-end-of-support.md)
    
- 이동하는 SharePoint 버전을 알고 있는 경우 다음에 대한 해당 문서를 PerformancePoint Services.
    
  - [PerformancePoint Services 계획(SharePoint Server 2010)](/previous-versions/office/sharepoint-server-2010/ee681486(v=office.14))
    
  - [SharePoint Server 2013의 PerformancePoint Services 개요](/sharepoint/administration/performancepoint-services-overview)
    
  - [SharePoint Server 2016의 PerformancePoint Services 개요](/sharepoint/administration/performancepoint-services-overview)
    
업그레이드할 때 PerformancePoint Services 몇 가지 새로운 기능과 향상된 기능이 있습니다. PerformancePoint Services 개선된 점수 기록표를 제공합니다. 분해 트리 및 KPI 세부 정보 보고서와 같은 새 시각화 차트 종류가 더 수록됩니다. 더 나은 시간 인텔리전스 필터링 기능 및 향상된 접근성 규정 준수. 자세한 내용은 [What's new for PerformancePoint Services (SharePoint Server 2010)을 참조합니다.](/previous-versions/office/sharepoint-server-2010/ee661741(v=office.14))
  
## <a name="where-can-i-get-help-with-my-upgrade"></a>업그레이드에 대한 도움말은 어디에서 얻을 수 있나요?

Microsoft 파트너와 함께 작업하는 Microsoft 365 업그레이드하거나 업그레이드를 진행하는 것이 좋습니다. 적격 파트너는 비즈니스 요구 사항을 가장 잘 충족하고 배포에 도움이 되는 솔루션을 식별하는 데 도움을 줄 수 있습니다. Microsoft 파트너 [센터를 방문하여](https://go.microsoft.com/fwlink/?linkid=841249)검색 필터를 사용하여 솔루션 공급자를 찾을 수 있습니다.
  
## <a name="related-topics"></a>관련 항목

[2007 서버 및 클라이언트에서 업그레이드하는 Office 리소스](upgrade-from-office-2007-servers-and-products.md)