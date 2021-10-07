---
title: SharePoint Server 2007 지원 종료 로드맵
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 01/28/2019
audience: ITPro
ms.topic: conceptual
f1.keywords:
- CSH
ms.custom:
- vsemail
- MS_WSS_DirectoryManagement
- MS_WSS_ConfigEmail
- globalemailconfig
- configssc
- AppDefToBDC
- seo-marvel-apr2020
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- SPO_Content
search.appverid:
- MET150
- OFU120
- SPS150
- OSU140
- WSU120
- OSR120
- SPO160
- PJW120
- SPB160
- OSI150
- OSI160
- BSA160
- OSU160
ms.assetid: ba124775-d5c0-4d68-b88d-8458ad4c3717
description: SharePoint Server 2007에 대한 지원은 2017년 10월에 종료됩니다. 이 문서에서는 업그레이드, 마이그레이션 및 지원 옵션에 대해 자세히 알아보습니다.
ms.openlocfilehash: d09e0cf58ef814a76cdac28f6029189eaf655efc
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60197272"
---
# <a name="sharepoint-server-2007-end-of-support-roadmap"></a>SharePoint Server 2007 지원 종료 로드맵

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

**2017년 10월 10일** Microsoft Office SharePoint Server 2007 지원이 종료됩니다. SharePoint Server 2007에서 Microsoft 365 또는 최신 버전의 SharePoint Server로 마이그레이션하지 않은 경우 이제 계획을 시작할 시간입니다. 이 문서에서는 데이터를 SharePoint Online으로 마이그레이션하거나 SharePoint Server를 업그레이드하는 데 도움이 되는 리소스를 제공합니다.
  
## <a name="what-does-end-of-support-mean"></a>지원 *종료는 무엇을 의미하나요?*

SharePoint 대부분의 Microsoft 제품과 마찬가지로 서버는 지원 수명 주기를 가지며, 이 기간 동안 Microsoft는 새로운 기능, 버그 수정, 보안 픽스를 제공합니다. 이 수명 주기는 일반적으로 제품의 초기 릴리스부터 10년 동안 지속됩니다. 이 수명 주기의 끝을 제품의 지원 종료라고 합니다. 지원이 종료된 후 Microsoft는 더 이상 다음을 제공하지 않습니다.
  
- 발생할 수 있는 문제에 대한 기술 지원
    
- 서버의 안정성과 사용 가능성에 영향을 줄 수 있는 문제에 대한 버그 수정
    
- 서버가 보안 위반에 취약해질 수 있는 취약점에 대한 보안 수정
    
- 표준 시간대 업데이트.
    
SharePoint Server 2007 팜은 2017년 10월 10일 이후에도 계속 작동되지만 보안 패치/수정을 포함하여 제품에 대한 추가 업데이트, 패치 또는 수정 사항은 릴리스되지 않습니다. Microsoft 지원은 지원 노력을 최신 버전의 제품으로 완전히 전환했습니다. 설치가 더 이상 지원되거나 패치되지 않도록 제품을 업그레이드하거나 중요한 데이터를 마이그레이션해야 합니다.
  
> [!TIP]
> 업그레이드 또는 마이그레이션을 아직 계획하지 않은 경우 SharePoint [2007](sharepoint-2007-migration-options.md) 마이그레이션 옵션을 참조하여 시작할 위치의 몇 가지 예를 참조하세요. 업그레이드 또는 마이그레이션(또는 둘 다)에 도움을 줄 수 있는 [Microsoft](https://go.microsoft.com/fwlink/?linkid=841249) 파트너를 Microsoft 365 수 있습니다.
  
Office 2007 서버 및 지원 종료에 대한 자세한 내용은 [Resources to help you upgrade from Office servers and clients을 참조하십시오.](upgrade-from-office-2007-servers-and-products.md)
  
## <a name="what-are-my-options"></a>내 옵션은 무엇입니까?

첫 번째 중지는 제품 [수명 주기 사이트 입니다.](/lifecycle/products/?alpha=Microsoft+Office+SharePoint+Server+2007) 사용 기간이 1년 이상이 되거나 업그레이드 또는 마이그레이션을 예약할 수 있도록 지원 종료 날짜를 확인한 후, 프레미스 Microsoft 제품이 사용되지 않습니다. 다음 단계를 선택할 때 충분히 양호하고, 더 나은, 가장 적합한 제품 기능을 고려합니다. 다음은 예입니다. 
  
|**좋음**|**더 나은**|**가장 적합한**|
|:-----|:-----|:-----|
|SharePoint Server 2010  <br/> |SharePoint Server 2013  <br/> |SharePoint Online  <br/> |
||SharePoint 하이브리드  <br/> |SharePoint Server 2016  <br/> |
| | |SharePoint 하이브리드  <br/> |
   
"충분히 양호한" 옵션을 선택하는 경우 SharePoint Server 2007에서 마이그레이션을 완료한 후 다른 업그레이드 계획을 수립해야 합니다. 

>[!NOTE] 
>지원 종료 날짜는 변경될 수 있습니다. 제품 [수명 주기 사이트를 검사합니다.](https://support.microsoft.com/lifecycle)
  
## <a name="where-can-i-go-next"></a>다음으로 이동할 위치

SharePoint 서버를 자체 서버에 사내에 설치할 수 있습니다. 또는 SharePoint 있는 온라인 서비스인 Microsoft 365. 옵션은 다음과 같습니다.
  
- 온라인으로 SharePoint 마이그레이션합니다.
    
- 서버 SharePoint 업그레이드합니다.
    
- 위의 두 가지 작업을 모두 합니다.
    
- 하이브리드 SharePoint [구현합니다.](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)
    
서버 팜 유지 관리, 사용자 지정 유지 관리 또는 마이그레이션, 서버 요구에 따라 하드웨어 업그레이드와 관련된 숨겨진 SharePoint 주의해야 합니다. 필요한 경우 SharePoint 서버 팜에 대해 보상을 받으면 됩니다. 그러나 사용자 지정을 많이 수행하지 않고 레거시 SharePoint 서버에서 팜을 실행하면 Online으로의 마이그레이션을 SharePoint 있습니다.
  
> [!IMPORTANT]
> 2007 2007의 콘텐츠가 SharePoint 다른 옵션이 있습니다. 일부 SharePoint 관리자는 Microsoft 365 구독을 만들고, 새 SharePoint Online 사이트를 설정한 다음, SharePoint 2007에서 정리하여 필수 문서만 최신 SharePoint Online 사이트에 저장합니다. 그런 다음 2007 사이트의 데이터를 SharePoint 보관함으로 드레인할 수 있습니다. 사용자가 2007 또는 2007년도에 설치한 데이터를 사용하여 작업하는 SharePoint 고려합니다. 요구 사항을 관리하는 창의적인 방법이 있을 수 있습니다.
  
|**SharePoint 온라인(SPO)**|**SharePoint 서버 On-premises**|
|:-----|:-----|
|높은 시간(계획/실행/확인)  <br/> |높은 시간(계획/실행/확인)  <br/> |
|자금 비용 절감(하드웨어 구매 없음)  <br/> |자금 비용이 더 높음(하드웨어 + 개발자/관리자)  <br/> |
|마이그레이션의 일회성 비용  <br/> |향후 마이그레이션당 일회성 비용 반복  <br/> |
|총 소유/유지 관리 비용 절감  <br/> |총 소유/유지 관리 비용 높음  <br/> |
   
마이그레이션을 Microsoft 365 일회성 이동은 데이터를 구성하고 클라우드로 이동할 데이터 및 남길 데이터를 결정하는 동안 더 많은 비용을 선행에 들이게 됩니다. 하지만 향후 업그레이드는 자동으로 수행될 것이고 더 이상 하드웨어 및 소프트웨어 업데이트를 관리할 필요가 없습니다. 또한 팜의 사용 시간은 Microsoft SLA(서비스 수준 계약)에 의해[지원됩니다.](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement)
  
### <a name="migrate-to-sharepoint-online"></a>SharePoint Online으로 마이그레이션

온라인에서 SharePoint 기능이 모두 있는지 확인 자세한 [Microsoft 365 및 Office 365 설명을 참조하세요.](/office365/servicedescriptions/office-365-service-descriptions-technet-library)
  
2007년 8월 20일부로 직접 마이그레이션할 SharePoint 온라인 SharePoint 없습니다. 온라인 SharePoint 이동은 수동으로 수행됩니다. SharePoint Server 2013 또는 SharePoint Server 2016으로 업그레이드하는 경우 SharePoint 마이그레이션 API를 사용하여 정보를 비즈니스용 OneDrive 마이그레이션할 수 있습니다.
  
|**온라인 pro**|**Online con**|
|:-----|:-----|
|Microsoft는 SPO 하드웨어 및 모든 하드웨어 관리 기능을 제공합니다.  <br/> |사용 가능한 기능은 서버 SharePoint SPO 간에 다를 수 있습니다.  <br/> |
|구독의 Sharepoint 관리자 또는 전역 관리자로서 SPO 사이트에 관리자를 할당할 수 있습니다.  <br/> |SharePoint Server의 팜 관리자가 사용할 수 있는 일부 작업이 존재하지 않을 수도 SharePoint 관리자 역할에 포함되어 있지 않을 수도 Microsoft 365.  <br/> |
|Microsoft는 기본 하드웨어 및 소프트웨어에 패치, 수정 및 업데이트를 적용합니다. <br/> |서비스에서 현재 파일 시스템에 액세스할 수 없는 경우 사용자 지정이 제한됩니다.  <br/> |
|Microsoft는 서비스 수준 [계약을 게시하고](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement) 서비스 수준 인시던트 해결을 위해 신속하게 움직입니다. <br/> |백업 및 복원 및 기타 복구 옵션은 온라인에서 서비스에서 SharePoint 있습니다. 사용되지 않는 경우 백업을 덮어 쓰게 됩니다. <br/> |
|보안 테스트 및 서버 성능 조정은 Microsoft의 서비스에서 지속적인 기준에 따라 수행됩니다. <br/> |사용자 인터페이스 및 기타 SharePoint 기능에 대한 변경 내용은 서비스에 의해 설치되어 설정 또는 해제해야 할 수 있습니다. <br/> |
|Microsoft 365 Microsoft 규정 준수 제품인 다양한 산업 [표준을 충족합니다.](/compliance/regulatory/offering-home)  <br/> |[FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) 지원이 제한됩니다.  <br/> 업그레이드의 상당수는 수동 또는 SharePoint Online 및 OneDrive 콘텐츠 로드맵에 설명된 SPO 마이그레이션 API를 통해 [수행됩니다.](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets)  <br/> |
|Microsoft 지원 엔지니어 및 데이터 센터 직원은 구독에 대한 무제한 관리자 액세스 권한이 없습니다. <br/> |최신 버전의 하드웨어를 지원하기 위해 하드웨어를 업그레이드해야 하는 경우 또는 업그레이드를 위해 SharePoint 팜이 필요한 경우 추가 비용이 있을 수 있습니다.  <br/> |
|파트너는 데이터를 온라인으로 마이그레이션하는 일회성 작업을 지원할 SharePoint 있습니다.  <br/> ||
|온라인 제품은 자동으로 업데이트됩니다. 기능이 더 이상 사용 불가능할 수 있습니다. <br/> ||
   
새 Microsoft 365 만들기로 결정하고 필요한 경우 데이터를 수동으로 마이그레이션할 경우 Microsoft 365 [옵션을 선택합니다.](https://www.microsoft.com/microsoft-365/)
  
### <a name="upgrade-sharepoint-server-on-premises"></a>SharePoint 서버 업그레이드

업그레이드에서 버전을 건너뛸 SharePoint 없습니다. 업그레이드는 직렬로 진행됩니다.
  
- SharePoint 2007 \> SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016
   
SharePoint 2007에서 SharePoint Server 2016으로 이동하려면 상당한 시간을 투자하며 하드웨어(SQL 서버를 업그레이드해야 하는 경우), 소프트웨어 및 관리에 많은 비용이 들이게 됩니다. 사용자 지정을 업그레이드하거나 중단해야 합니다.
  
> [!NOTE]
> 사용 종료 SharePoint 2007 팜을 유지 관리하고, 새 하드웨어에 SharePoint Server 2016 팜을 설치한 다음(별도의 팜을 나란히 실행) 콘텐츠의 수동 마이그레이션(예: 콘텐츠 다운로드 및 다시 업로드)을 계획하고 실행할 수 있습니다. 그러나 수동으로 이동하는 마지막 수정된 계정을 계정의 별칭으로 바꾸는 문서 이동과 같은 수동 이동의 일부에 주의해야 합니다. 사이트, 하위 사이트, 사용 권한 및 목록 구조를 다시 설정하는 등의 작업을 미리 고려해야 합니다. 저장소로 이동하거나 삭제할 수 있는 데이터를 미리 고려하여 마이그레이션의 영향을 줄입니다.
  
업그레이드하기 전에 환경을 정리하는 것이 중요합니다. 업그레이드하기 전에 그리고 해제하기 전에 기존 팜이 작동해야 합니다.
  
지원되는 업그레이드 경로와 지원되지 않는 업그레이드 경로를 *검토해야 합니다.* 
  
- [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))
    
- [SharePoint Server 2010](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))
    
- [SharePoint Server 2013](/SharePoint/upgrade-and-update/review-supported-editions-and-products-for-upgrading-to-sharepoint-2013)
    
사용자 지정이 있는 경우 마이그레이션 경로의 각 단계에 대한 계획을 세우는 것이 중요합니다. 
  
- [SharePoint 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc263203(v=office.12))
    
- [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc263203(v=office.14))
    
- [SharePoint Server 2013](/SharePoint/upgrade-and-update/create-a-communication-plan-for-the-upgrade-to-sharepoint-2013)
    
|**On-premises pro**|**On-premises con**|
|:-----|:-----|
|서버 하드웨어에서 SharePoint 팜의 모든 측면을 완전하게 제어할 수 있습니다.  <br/> |모든 중단 및 수정은 회사의 책임입니다(제품이 지원 종료되지 않은 경우 유료 Microsoft 지원에 참여할 수 있습니다).  <br/> |
|하이브리드를 통해 SharePoint 팜을 SharePoint 온라인 구독에 연결하는 옵션이 있는 SharePoint 서버의 전체 기능 집합입니다.  <br/> |업그레이드, 패치, 보안 픽스 및 모든 SharePoint 관리되는 서버의 모든 유지 관리  <br/> |
|보다 많은 사용자 지정을 위한 모든 권한이 있습니다.  <br/> |[Microsoft 규정 준수 제품은](/compliance/regulatory/offering-home) 수동으로 구성해야 합니다.  <br/> |
|보안 테스트 및 서버 성능 조정은 프레미스(제어에 따라)에서 수행됩니다.  <br/> |Microsoft 365 SharePoint Server와 상호 연결되지 않는 SharePoint Online에서 사용할 수 있습니다.  <br/> |
|파트너는 다음 버전의 SharePoint 서버 이상으로 데이터를 마이그레이션하는 데 도움을 줄 수 있습니다.  <br/> |SharePoint Server 사이트에서는 SharePoint Online에 표시되어 있는 [SSL/TLS](/SharePoint/security-for-sharepoint-server/enable-tls-1-1-and-tls-1-2-support-in-sharepoint-server-2016) 인증서를 자동으로 SharePoint 않습니다.  <br/> |
|SharePoint Server의 이름 규칙, 백업 및 복원 및 기타 복구 옵션에 대한 모든 SharePoint 제어합니다.  <br/> |SharePoint 서버의 사내는 제품 수명 주기에 민감합니다.  <br/> |
   
### <a name="upgrade-resources"></a>리소스 업그레이드

환경이 하드웨어 및 소프트웨어 요구 사항을 충족하는지 확인한 다음 지원되는 업그레이드 방법을 따르는 것이 좋습니다.
  
- **에 대한 하드웨어/소프트웨어 요구 사항** 
    
    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/hardware-and-software-requirements-0)  |  [SharePoint Server 2016](/SharePoint/install/hardware-and-software-requirements)
    
- **에 대한 소프트웨어 경계 및 제한** 사항 
    
    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262787(v=office.12))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262787(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/software-boundaries-and-limits)  |  [SharePoint Server 2016](/SharePoint/install/software-boundaries-and-limits-0)
    
- **에 대한 업그레이드 프로세스 개요** 
    
    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc303420(v=office.12))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc303420(v=office.14))  |  [SharePoint Server 2013](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)  |  [SharePoint Server 2016](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)
    
### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>SharePoint Online과 SharePoint 하이브리드 솔루션 만들기

마이그레이션 요구에 대한 대답이 사내에서 제공하는 자체 제어와 SharePoint Online에서 제공하는 낮은 소유권 비용 사이에 있는 경우 하이브리드를 통해 SharePoint Server 2013 또는 2016 팜을 SharePoint Online에 연결할 수 있습니다. [하이브리드 솔루션 SharePoint 대해 자세히 알아보십시오.](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)
  
하이브리드 SharePoint 서버 팜이 비즈니스에 도움이 된다고 판단되는 경우 기존 유형의 하이브리드 및 프레미스 SharePoint 팜과 Microsoft 365 구독 간에 연결을 구성하는 방법을 익히십시오.
  
| 옵션 | 설명 |
|:-----|:-----|
[Microsoft 규정 준수 제품](/compliance/regulatory/offering-home)  <br/> |[FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) 지원이 제한됩니다.  <br/> 업그레이드의 상당수는 수동 또는 SharePoint Online 및 OneDrive 콘텐츠 로드맵에 설명된 SPO 마이그레이션 API를 통해 [수행됩니다.](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets)  <br/> |
|Microsoft 지원 엔지니어 및 데이터 센터 직원은 구독에 대한 무제한 관리자 액세스 권한이 없습니다.<br/> |최신 버전의 하드웨어 인프라를 지원하기 위해 하드웨어 인프라를 업그레이드해야 하는 경우 또는 업그레이드를 위해 SharePoint 팜이 필요한 경우 추가 비용이 있을 수 있습니다.  <br/> |
|파트너는 데이터를 온라인으로 마이그레이션하는 일회성 작업을 지원할 SharePoint 있습니다.  <br/> ||
|온라인 제품은 서비스 전체에서 자동으로 업데이트됩니다. 기능이 더 이상 사용 불가능할 수 있습니다.<br/> ||
   
새 Microsoft 365 만들기로 결정하고 필요한 경우 데이터를 수동으로 마이그레이션할 경우 Microsoft 365 [옵션을 선택합니다.](https://www.microsoft.com/microsoft-365/)
  
### <a name="upgrade-sharepoint-server-on-premises"></a>SharePoint 서버 업그레이드

업그레이드에서 버전을 건너뛸 SharePoint 없습니다. 업그레이드는 직렬로 진행됩니다.
  
- SharePoint 2007 \> SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016
   
SharePoint 2007에서 SharePoint Server 2016으로 이동하려면 상당한 시간을 투자하며 하드웨어(SQL 서버도 업그레이드해야 하는 경우), 소프트웨어 및 관리에 들이는 비용이 수반됩니다. 사용자 지정을 업그레이드하거나 중단해야 합니다.
  
> [!NOTE]
> 사용 종료 SharePoint 2007 팜을 유지 관리하고, 새 하드웨어에 SharePoint Server 2016 팜을 설치한 다음(별도의 팜을 나란히 실행) 콘텐츠의 수동 마이그레이션(예: 콘텐츠 다운로드 및 다시 업로드)을 계획하고 실행할 수 있습니다. 그러나 수동으로 이동하는 마지막 수정된 계정을 계정의 별칭으로 바꾸는 문서 이동, 사이트, 하위 사이트, 사용 권한 및 목록 구조 다시 작성과 같이 미리 수행해야 하는 작업과 같은 수동 이동의 잠재적인 문제를 주의해야 합니다. 마이그레이션의 영향을 줄이기 위해 저장소로 이동하거나 삭제할 수 있는 데이터를 고려합니다.
  
업그레이드 전에 환경을 정리합니다. 업그레이드하기 전에 그리고 해제하기 전에 기존 팜이 작동해야 합니다. 
  
지원되는 업그레이드 경로와 지원되지 않는 업그레이드 경로를 *검토해야 합니다.* 
  
- [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))
    
- [SharePoint Server 2010](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))
    
- [SharePoint Server 2013](/SharePoint/upgrade-and-update/review-supported-editions-and-products-for-upgrading-to-sharepoint-2013)
    
사용자 *지정이* 있는 경우 마이그레이션 경로의 각 단계에 대한 업그레이드 계획을 세우는 것이 중요합니다. 
  
- [SharePoint 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc263203(v=office.12))
    
- [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc263203(v=office.14))
    
- [SharePoint Server 2013](/SharePoint/upgrade-and-update/create-a-communication-plan-for-the-upgrade-to-sharepoint-2013)
    
|**Pro**|**On-premises Con**|
|:-----|:-----|
|서버 하드웨어에서 SharePoint 팜의 모든 측면을 완전하게 제어할 수 있습니다.  <br/> |모든 중단 및 수정은 회사의 책임입니다. (제품이 지원 종료되지 않은 경우 유료 Microsoft 지원에 참여할 수 있습니다.)  <br/> |
|하이브리드를 통해 SharePoint 팜을 SharePoint 온라인 구독에 연결하는 옵션이 있는 SharePoint 서버의 전체 기능 집합입니다.  <br/> |업그레이드, 패치, 보안 픽스 및 모든 SharePoint 관리되는 서버의 모든 유지 관리  <br/> |
|보다 많은 사용자 지정을 위한 모든 권한이 있습니다.  <br/> |[Microsoft 규정 준수 제품은](/compliance/regulatory/offering-home) 수동으로 구성해야 합니다.  <br/> |
|보안 테스트 및 서버 성능 조정은 제어 하에 프레미스에서 수행됩니다.  <br/> |Microsoft 365 SharePoint Server와 상호 연결되지 않는 SharePoint 기능을 사용할 수 SharePoint 있습니다.  <br/> |
|파트너는 데이터를 다음 버전의 SharePoint 서버 이상으로 마이그레이션하는 데 도움을 줄 수 있습니다.  <br/> |SharePoint Online에 표시되어 있는 [SSL/TLS](/SharePoint/security-for-sharepoint-server/enable-tls-1-1-and-tls-1-2-support-in-sharepoint-server-2016) 인증서는 SharePoint 않습니다.  <br/> |
|SharePoint Server의 이름 규칙, 백업 및 복원 및 기타 복구 옵션에 대한 모든 SharePoint 제어합니다.  <br/> |SharePoint 서버의 사내는 제품 수명 주기에 민감합니다.  <br/> |
   
### <a name="upgrade-resources"></a>리소스 업그레이드

환경이 하드웨어 및 소프트웨어 요구 사항을 충족하는지 확인합니다. 그런 다음 지원되는 업그레이드 방법을 따르게 됩니다.
  
- **하드웨어/소프트웨어 요구 사항:** 
    
    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/hardware-and-software-requirements-0)  |  [SharePoint Server 2016](/SharePoint/install/hardware-and-software-requirements)
    
- **소프트웨어 경계 및 제한:** 
    
    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262787(v=office.12))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262787(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/software-boundaries-and-limits)  |  [SharePoint Server 2016](/SharePoint/install/software-boundaries-and-limits-0)
    
- **업그레이드 프로세스 개요:** 
    
    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc303420(v=office.12))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc303420(v=office.14))  |  [SharePoint Server 2013](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)  |  [SharePoint Server 2016](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)
    
### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>SharePoint Online과 SharePoint 하이브리드 솔루션 만들기

마이그레이션 요구에 대한 대답이 사내에서 제공하는 자체 제어와 SharePoint Online에서 제공하는 낮은 소유권 비용 사이에 있는 경우 하이브리드를 통해 SharePoint Server 2013 또는 2016 팜을 SharePoint Online에 연결할 수 있습니다. [하이브리드 솔루션 SharePoint 대해 자세히 알아보십시오.](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)
  
하이브리드 SharePoint 서버 팜이 비즈니스에 도움이 된다고 판단되는 경우 기존 유형의 하이브리드 및 프레미스 SharePoint 팜과 Microsoft 365 구독 간에 연결을 구성하는 방법을 익히십시오.
  
테스트 랩 가이드를 사용하여 설정할 수 있는 Microsoft 365/테스트 환경을 만드는 것이 이 작업의 작동 방법을 보는 [좋은 방법 중 하나입니다.](m365-enterprise-test-lab-guides.md) 평가판을 얻거나 Microsoft 365 구독을 구매한 후 데이터를 마이그레이션할 수 있는 SharePoint Online에서 사이트 모음, 웹 및 문서 라이브러리를 만들 수 있습니다. 마이그레이션 API를 사용하여 수동으로 마이그레이션하거나 하이브리드 마법사를 통해 내 사이트 콘텐츠를 마이그레이션할 비즈니스용 OneDrive 수 있습니다.
  
> [!NOTE]
> 하이브리드 옵션을 사용하려면 SharePoint 2007 팜을 SharePoint Server 2013 또는 SharePoint Server 2016으로 업그레이드해야 합니다.
  
## <a name="related-topics"></a>관련 항목

[업그레이드 문제 해결 및 다시 시작(Office SharePoint Server 2007)](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262967(v=office.12))
  
[업그레이드 문제 해결(SharePoint Server 2010)](/previous-versions/office/sharepoint-server-2010/cc262967(v=office.14))
  
[SharePoint 2013에서 데이터베이스 업그레이드 문제 해결](/SharePoint/upgrade-and-update/troubleshoot-database-upgrade-issues-in-sharepoint-2013)
  
[업그레이드에 도움이 되는 Microsoft 파트너 검색](https://go.microsoft.com/fwlink/?linkid=841249)
  
[2007 서버 및 클라이언트에서 업그레이드하는 Office 리소스](upgrade-from-office-2007-servers-and-products.md)
