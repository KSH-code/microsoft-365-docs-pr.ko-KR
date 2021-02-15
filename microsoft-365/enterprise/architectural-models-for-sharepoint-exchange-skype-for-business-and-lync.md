---
title: Exchange, SharePoint, 비즈니스용 Skype 및 Lync에 대한 아키텍처 모델
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/16/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Ent_Architecture
ms.assetid: 5b49fa68-f8f2-4705-af96-5f5475e8539a
search.appverid:
- MET150
description: SharePoint, Exchange, 비즈니스용 Skype 및 Lync에 대한 아키텍처 모델, 배포 및 플랫폼 옵션을 설명하는 IT 포스터를 얻습니다.
ms.openlocfilehash: 6d5cda89fb67f5c41dcf161abe7258c4600ee8ce
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2020
ms.locfileid: "48919823"
---
# <a name="architectural-models-for-sharepoint-exchange-skype-for-business-and-lync"></a>Exchange, SharePoint, 비즈니스용 Skype 및 Lync에 대한 아키텍처 모델

이 문서의 IT 포스터는 SharePoint, Exchange, 비즈니스용 Skype 및 Lync에 대한 아키텍처 모델 및 배포 옵션에 대해 설명합니다. 또한 Microsoft Azure에서 SharePoint를 배포하기 위한 디자인 정보도 제공합니다.
  
Microsoft 365를 사용하면 클라우드를 통해 친숙한 공동 작업 및 커뮤니케이션 서비스를 제공할 수 있습니다. 몇 가지 예외를 제외하고 사용자 환경은 사용자가 Microsoft 365를 사용하는지 여부에 따라 동일하게 유지 관리합니다. 

이 통합된 사용자 환경은 각 워크로드를 배치할 위치를 결정하기가 복잡합니다. 또한 궁금한 의문도 제기됩니다.
  
- 개별 워크로드에 대한 플랫폼은 어떻게 선택하나요?
    
- 모든 서비스를 온-프레미스에 두는 것이 적절할까요?
    
- 하이브리드 배포가 적절한 시나리오는 무엇입니까?
    
- Azure는 어떻게 그림에 잘 어울리나요?
    
- Azure에서 지원하는 Office 서버 워크로드의 구성은 무엇입니까?
    
> [!TIP]
> 이 문서의 대부분의 포스터는 여러 언어로 제공됩니다. 사용 가능한 언어에는 중국어, 영어, 프랑스어, 독일어, 이탈리아어, 일본어, 한국어, 포르투갈어, 러시아어 및 스페인어가 포함됩니다. 이러한 언어 중 하나에서 포스터를 다운로드하려면 포스터 미리 보기 이미지 아래에서 추가 언어를 **선택합니다.**
  
의견을 전달해주세요! [cloudadopt@microsoft.com](mailto:cloudadopt@microsoft.com)로 메일을 보내주세요. 
  
다음 링크를 사용하여 필요한 포스터를 받을 수 있습니다.
  
- **아키텍처 모델:** 이러한 리소스를 사용하여 SharePoint 2016 및 비즈니스용 Skype 2015에 이상적인 플랫폼 및 구성을 확인할 수 있습니다.
    
  - [Microsoft SharePoint 2016 아키텍처 모델](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2016_ArchModel)
    
  - [SharePoint Server 2016 데이터베이스](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2016_Databases)
    
  - [Microsoft 비즈니스용 Skype 2015 아키텍처 모델](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SfB2015_ArchModel)
    
- **플랫폼:** 다음 리소스를 사용하여 SharePoint 2013, Exchange 2013 및 Lync 2013에 이상적인 플랫폼 및 구성을 확인할 수 있습니다.
    
  - [SharePoint 2013 플랫폼 옵션](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2013_Options)
    
  - [Exchange 2013 플랫폼 옵션](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Exch2013_options)
    
  - [Lync 2013 플랫폼 옵션](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Lync2013_Options)
    
- **Azure의 SharePoint Server 2013: 이러한** IT 포스터를 사용하여 Azure 인프라 서비스에서 SharePoint Server 2013 워크로드를 디자인하고 구성합니다.
    
  - [SharePoint Server 2013을 사용하는 Azure의 인터넷 사이트](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Azure_sharepoint2013)
    
  - [디자인 샘플: SharePoint 2013용 Azure의 인터넷 사이트](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#DesignSampleInternetSites)
    
  - [Azure로의 SharePoint 재해 복구](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#sharepoint_recovery_Azure)
    
## <a name="architectural-models-posters"></a>아키텍처 모델 포스터

SharePoint 2016 및 비즈니스용 Skype 2015용 IT 포스터를 통해 쉽게 인쇄할 수 있는 형식으로 배포 방법을 비교할 수 있습니다. 포스터에는 모든 구성 또는 플랫폼 옵션이 나열됩니다. 각 옵션에 대해 다음 정보를 제공합니다.
  
- **개요**: 개념 다이어그램을 포함하여 플랫폼에 대한 간략한 요약입니다.
    
- **최상:** 플랫폼에 가장 적합한 일반적인 시나리오입니다.
    
- **라이선스 요구** 사항 : 배포에 필요한 라이선스입니다.
    
- **아키텍처 작업:** 설계자로 결정해야 하는 결정 사항
    
- **IT pro 작업 또는 책임:** IT 직원이 계획해야 하는 일상적인 책임
    
<a name="SP2016_ArchModel"> </a>
### <a name="microsoft-sharepoint-server-2016-architectural-models"></a>Microsoft SharePoint Server 2016 아키텍처 모델

|항목|설명|
|---|---|
|[![SharePoint Server 2016 아키텍처 모델 포스터의 축소판 그림입니다.](../media/7d3e590c-1f3b-42cf-920d-9edac8fa3e04.png)          ](https://www.microsoft.com/download/details.aspx?id=52650) <br/> [PDF](https://download.microsoft.com/download/4/F/A/4FA0F94B-EE2F-41DB-A047-D9864FEF41E9/SharePoint2016ArchitecturalModels.pdf)  \| [Visio](https://download.microsoft.com/download/4/F/A/4FA0F94B-EE2F-41DB-A047-D9864FEF41E9/SharePoint2016ArchitecturalModels.vsdx)  \| [추가 언어](https://www.microsoft.com/download/details.aspx?id=52650)|이 IT 포스터는 비즈니스 의사 결정권자 및 솔루션 설계자가 알아야 하는 SharePoint Online, Azure 및 SharePoint온-프레미스 구성에 대해 설명합니다. <br/><br/> - **SharePoint Online(SaaS)**: SaaS(Software as a Service) 구독 모델을 통해 SharePoint를 사용하세요. <br/> - **SharePoint 하이브리드:** SharePoint 사이트 및 앱을 자신의 속도에 따라 클라우드로 이동 <br/> - **Azure의 SharePoint(IaaS)**: Azure에 대한 SharePoint 환경을 확장하고 SharePoint 2016 서버를 배포합니다. (이 모델은 고가용성 또는 재해 복구 환경 및 개발/테스트 환경에 권장됩니다.) <br/> - **SharePoint On-premises:** 유지 관리하는 데이터 센터에서 SharePoint 환경을 계획, 배포, 유지 관리 및 사용자 지정합니다.|
   
<a name="SP2016_Databases"> </a>
### <a name="sharepoint-server-2016-databases"></a>SharePoint Server 2016 데이터베이스

|항목|설명|
|---|---|
|[![SharePoint Server 2016 데이터베이스 포스터의 축소판 그림입니다.](../media/c53e9de7-3bf8-446d-8766-e6700c8dd8e1.png)](https://www.microsoft.com/download/details.aspx?id=55041) <br/> [PDF](https://download.microsoft.com/download/D/5/D/D5DC1121-8BC5-4953-834F-1B5BB03EB691/DBrefguideSPS2016_tabloid.pdf)  \| [Visio](https://download.microsoft.com/download/D/5/D/D5DC1121-8BC5-4953-834F-1B5BB03EB691/DBrefguideSPS2016_tabloid.vsdx)  \| [추가 언어](https://www.microsoft.com/download/details.aspx?id=55041)|이 IT 포스터는 SharePoint Server 2016 데이터베이스에 대한 빠른 참조입니다. 각 데이터베이스에 대한 세부 정보가 표시 됩니다. <br/><br/> - 크기 <br/> - 크기 조정 지침 <br/> - I/O 패턴 <br/> - 요구 사항 <br/><br/>  첫 번째 페이지에는 SharePoint 시스템 데이터베이스 및 여러 데이터베이스가 있는 서비스 응용 프로그램이 표시됩니다. 두 번째 페이지에는 단일 데이터베이스가 있는 모든 서비스 응용 프로그램이 표시됩니다. <br/><br/>  자세한 내용은 [SharePoint Server 2016의](https://docs.microsoft.com/SharePoint/technical-reference/database-types-and-descriptions)데이터베이스 유형 및 설명을 참조하세요.|
   
<a name="SfB2015_ArchModel"> </a>
### <a name="microsoft-skype-for-business-2015-architectural-models"></a>Microsoft 비즈니스용 Skype 2015 아키텍처 모델

|항목|설명|
|---|---|
|[![비즈니스용 Skype 아키텍처 모델 포스터의 축소판 그림입니다.](../media/132288c0-6ae4-4394-88ab-b57dae367714.png)](https://www.microsoft.com/download/details.aspx?id=55022) <br/> [PDF](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype%20for%20Business%20Architectural%20Models.pdf)  \| [Visio](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype%20for%20Business%20Architectural%20Models.vsd)  \| [추가 언어](https://www.microsoft.com/download/details.aspx?id=55022)|이 포스터는 비즈니스용 Skype Online,온-프레미스, 하이브리드 및 클라우드 PBX(Private Branch Exchange)에 대해 설명합니다. 또한 비즈니스 의사 결정권자 및 솔루션 설계자가 알아야 하는 Exchange 및 SharePoint 구성과의 통합에 대해 설명합니다. <br/><br/> 이 포스터는 IT 프로들이 비즈니스용 Skype Online 및 비즈니스용 Skype온-프레미스를 사용할 수 있는 기본 아키텍처 모델에 대한 인식을 높이기 위해 작성되었습니다. <br/><br/>조직의 요구 및 계획에 가장 적합한 구성으로 시작하세요. 필요한 경우 다른 구성을 고려하고 사용할 수 있습니다. 예를 들어 Exchange 및 SharePoint와의 통합이나 Microsoft 클라우드 PBX 서비스를 활용하는 솔루션을 고려할 수 있습니다.|
   
## <a name="platform-options-posters"></a>플랫폼 옵션 포스터

SharePoint 2013, Exchange 2013 및 Lync 2013의 IT 포스터는 배포 방법을 한 눈에 비교할 수 있는 방법을 제공합니다. 각 포스터에는 모든 구성 또는 플랫폼 옵션이 나열됩니다. 각 옵션에 대해 다음 정보를 제공합니다.
  
- **개요**: 개념 다이어그램을 포함하여 플랫폼에 대한 간략한 요약입니다.
    
- **최상:** 플랫폼에 가장 적합한 일반적인 시나리오입니다.
    
- **라이선스 요구** 사항 : 배포에 필요한 라이선스입니다.
    
- **아키텍처 작업:** 설계자로 결정해야 하는 결정 사항
    
- **IT pro 작업 또는 책임:** IT 직원이 계획해야 하는 일상적인 책임
    
<a name="SP2013_Options"> </a>
## <a name="sharepoint-2013-platform-options"></a>SharePoint 2013 플랫폼 옵션

|항목|설명|
|---|---|
|[![SharePoint 2013 플랫폼 옵션 포스터의 축소판 그림 이미지입니다.](../media/SP-PlatformOptions.jpg)](https://www.microsoft.com/download/details.aspx?id=40332) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=324594)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=324593)  \| [추가 언어](https://www.microsoft.com/download/details.aspx?id=40332)|비즈니스 의사 결정권자 및 설계자용 이 포스터는 SharePoint 2013, Microsoft 365의 SharePoint, Microsoft 365, Azure 및 프레미스 전용 배포가 있는 프레미스 하이브리드에 대한 플랫폼 옵션을 보여줍니다. 여기에는 각 아키텍처, 권장 사항, 라이선스 요구 사항 및 각 플랫폼에 대한 설계자 및 IT 프로 작업 목록의 개요가 포함됩니다. 이 포스터는 Azure의 여러 SharePoint 솔루션을 강조합니다.|
   
<a name="Exch2013_options"> </a>
## <a name="exchange-2013-platform-options"></a>Exchange 2013 플랫폼 옵션

|항목|설명|
|---|---|
|[![Exchange 플랫폼 옵션 포스터의 축소판 그림 이미지입니다.](../media/ITPro-Other-Exchange2013PlatformOptions.jpg)          ](https://www.microsoft.com/download/details.aspx?id=42676) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkID=398740)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkID=398742)  \| [추가 언어](https://www.microsoft.com/download/details.aspx?id=42676)|비즈니스 의사 결정권자 및 설계자는 이 포스터에서 Exchange 2013의 플랫폼 옵션에 대해 설명하고 있습니다. 고객은 Microsoft 365가 있는 Exchange Online, 하이브리드 Exchange, Exchange Server 및 호스팅된 Exchange에서 선택할 수 있습니다. 포스터는 각 아키텍처 옵션에 대해 자세히 설명하며 각 시나리오에 대한 이상적인 시나리오, 라이선스 요구 사항 및 IT 관련 책임이 있습니다.|
   
<a name="Lync2013_Options"> </a>
## <a name="lync-2013-platform-options"></a>Lync 2013 플랫폼 옵션

|항목|설명|
|---|---|
|[![Lync 2013 플랫폼 옵션 포스터의 축소판 그림 이미지입니다.](../media/Lync-PlatformOptions.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41677) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkID=391837)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkID=391839)  \| [추가 언어](https://www.microsoft.com/download/details.aspx?id=41677)|비즈니스 의사 결정권자 및 설계자는 이 포스터에서 Lync 2013의 플랫폼 옵션에 대해 설명하고 있습니다. 고객은 Microsoft 365를 통해 Lync Online, 하이브리드 Lync, Lync Server 온-프레미스 및 호스팅된 Lync에서 선택할 수 있습니다. IT 포스터는 각 아키텍처 옵션에 대해 자세히 설명하며 각 시나리오에 대한 이상적인 시나리오, 라이선스 요구 사항 및 IT 관련 책임이 있습니다.|
   
<a name="Lync2013_Options"> </a>
## <a name="sharepoint-in-azure-solutions-posters"></a>Azure의 SharePoint 솔루션 포스터

Azure의 SharePoint용 IT 포스터는 SharePoint Server 2013을 사용하는 Azure 기반 솔루션을 보여 주며,
  
<a name="Azure_sharepoint2013"> </a>
### <a name="internet-sites-in-microsoft-azure-using-sharepoint-server-2013"></a>SharePoint Server 2013을 사용하여 Microsoft Azure의 인터넷 사이트

|항목|설명|
|---|---|
|[![SharePoint Server 2013 포스터를 사용하는 Azure의 인터넷 사이트 이미지](../media/MS-AZ-SPInternetSites.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41992) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392552)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392551)  \| [추가 언어](https://www.microsoft.com/download/details.aspx?id=41992)|이 포스터는 Azure의 인터넷 연결 사이트에 대한 주요 디자인 활동 및 권장 아키텍처에 대해 간략하게 설명합니다.  <br/><br/> 자세한 내용은 다음 문서를 참조하세요.  <br/><br/> - [SharePoint Server 2013을 사용하는 Azure의 인터넷 사이트](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md) <br/> - [SharePoint 2013용 Azure 아키텍처](microsoft-azure-architectures-for-sharepoint-2013.md)|
   
<a name="DesignSampleInternetSites"> </a>
### <a name="internet-sites-in-azure-for-sharepoint-2013"></a>SharePoint 2013용 Azure의 인터넷 사이트

|항목|설명|
|---|---|
|[![SharePoint Server 2013용 Microsoft Azure의 인터넷 사이트 이미지](../media/MS-AZ-InternetSitesDesignSample.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41991) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392549)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392548)  \| [추가 언어](https://www.microsoft.com/download/details.aspx?id=41991)|SharePoint Server 2013을 사용하여 Azure에서 인터넷 연결 사이트의 자체 아키텍처를 위한 시작점으로 이 디자인 예제를 사용하세요. <br/><br/> 자세한 내용은 다음 문서를 참조하세요.  <br/><br/> - [SharePoint Server 2013을 사용하는 Azure의 인터넷 사이트](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md) <br/> - [SharePoint 2013용 Azure 아키텍처](microsoft-azure-architectures-for-sharepoint-2013.md)|
   
<a name="sharepoint_recovery_Azure"> </a>
### <a name="sharepoint-disaster-recovery-to-microsoft-azure"></a>Microsoft Azure로의 SharePoint 재해 복구

|항목|설명|
|---|---|
|[![Azure에 대한 SharePoint 재해 복구 프로세스에 대한 포스터의 이미지입니다.](../media/SP-DR-Azure.png)          ](https://www.microsoft.com/download/details.aspx?id=41993) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392555)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392554)  \| [추가 언어](https://www.microsoft.com/download/details.aspx?id=41993)|이 IT 포스터는 Azure의 재해 복구 환경에 대한 아키텍처 원리를 표시합니다. <br/><br/> 자세한 내용은 다음 문서를 참조하십시오.  <br/><br/> - [Azure의 SharePoint Server 2013 재해 복구](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md) <br/> - [SharePoint 2013용 Azure 아키텍처](microsoft-azure-architectures-for-sharepoint-2013.md)|
   
## <a name="see-also"></a>참고 항목

- [Microsoft 365 솔루션 및 아키텍처 센터](../solutions/solution-architecture-center.md)
  
- [Microsoft 클라우드 아키텍처 모델](../solutions/cloud-architecture-models.md)
  
- [Microsoft 365 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)
  
- [하이브리드 솔루션](hybrid-solutions.md)

