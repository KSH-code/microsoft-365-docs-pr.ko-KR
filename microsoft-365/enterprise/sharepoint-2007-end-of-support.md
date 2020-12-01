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
localization_priority: Normal
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
description: SharePoint Server 2007에 대 한 지원은 10 월 2017에 종료 되었습니다. 이 문서에서는 업그레이드, 마이그레이션 및 지원 옵션에 대해 알아봅니다.
ms.openlocfilehash: aa09669d1c7b90f70e6c136a85d06ef2a516e4b5
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519637"
---
# <a name="sharepoint-server-2007-end-of-support-roadmap"></a>SharePoint Server 2007 지원 종료 로드맵

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

**2017 년 10 월 10 일**, Microsoft Office SharePoint Server 2007 지원 종료에 도달 했습니다. SharePoint Server 2007에서 Microsoft 365 또는 최신 버전의 SharePoint Server 온-프레미스로 마이그레이션한 적이 없는 경우에는 계획을 시작 하는 데 시간이 더 됩니다. 이 문서에서는 데이터를 SharePoint Online으로 마이그레이션하거나 SharePoint Server를 온-프레미스로 업그레이드 하는 데 도움이 되는 리소스를 제공 합니다.
  
## <a name="what-does-end-of-support-mean"></a>*지원이 끝나는* 것은 무엇을 의미 하나요?

대부분의 Microsoft 제품과 마찬가지로 SharePoint Server에는 지원 수명 주기가 있으며,이 기간 동안 Microsoft는 새로운 기능, 버그 수정, 보안 픽스 등을 제공 합니다. 이 수명 주기는 일반적으로 제품 초기 릴리스에서 10 년 동안 지속 됩니다. 이 수명 주기의 끝은 제품의 지원 종료 라고 합니다. 지원이 종료 된 후에는 Microsoft가 더 이상 다음을 제공 하지 않습니다.
  
- 발생할 수 있는 문제에 대 한 기술 지원
    
- 서버의 안정성 및 유용성에 영향을 줄 수 있는 문제에 대 한 버그 수정
    
- 보안 침해에 취약 한 서버를 만들 수 있는 취약성에 대 한 보안 수정
    
- 표준 시간대 업데이트
    
SharePoint Server 2007 팜은 2017부터 여전히 작동 하지만 보안 패치/픽스를 포함 하 여 제품에 대 한 추가 업데이트, 패치 또는 수정 내용은 릴리스되지 않습니다. Microsoft Support는 제품의 최신 버전에 대 한 지원 노력을 완전히 이동 했습니다. 설치가 더 이상 지원 되지 않거나 패치가 아니므로 제품을 업그레이드 하거나 중요 한 데이터를 마이그레이션해야 합니다.
  
> [!TIP]
> 업그레이드 또는 마이그레이션을 아직 계획 하지 않은 경우에는 [SharePoint 2007 마이그레이션 옵션을 참조 하 여](sharepoint-2007-migration-options.md) 시작할 위치에 대 한 몇 가지 예를 살펴보겠습니다. 또한 업그레이드 또는 Microsoft 365 마이그레이션 (또는 둘 다)을 통해 도움을 받을 수 있는 [Microsoft 파트너](https://go.microsoft.com/fwlink/?linkid=841249) 를 검색할 수도 있습니다.
  
Office 2007 서버에 대 한 자세한 내용과 지원 종료에 대 한 자세한 내용은 [office 2007 서버 및 클라이언트에서 업그레이드 하는 데 도움이](upgrade-from-office-2007-servers-and-products.md)되는 리소스를 참조 하세요.
  
## <a name="what-are-my-options"></a>내 옵션 이란?

첫 번째 중지는 [제품 수명 주기 사이트](https://go.microsoft.com/fwlink/?linkid=843148)여야 합니다. 온-프레미스 Microsoft 제품이 에이징을 사용 중인 경우에는 지원 날짜를 확인 하 여 일년 이상이 나 업그레이드 또는 마이그레이션을 예약할 수 있도록 합니다. 다음 단계를 선택 하는 경우에는 어떤 제품 기능을 충분히 효과적으로 사용할 수 있으며,이 방법이 가장 적합 합니다. 예를 들면 다음과 같습니다. 
  
|**좋습니다**|**바람직합니다**|**방법은**|
|:-----|:-----|:-----|
|SharePoint Server 2010  <br/> |SharePoint Server 2013  <br/> |SharePoint Online  <br/> |
||SharePoint 하이브리드  <br/> |SharePoint Server 2016  <br/> |
| | |SharePoint 하이브리드  <br/> |
   
"충분히 양호" 옵션을 선택 하는 경우 SharePoint Server 2007에서 마이그레이션한 후에 다른 업그레이드 계획을 시작 해야 합니다. 

>[!NOTE] 
>지원 종료 날짜는 변경 될 수 있습니다. [제품 수명 주기 사이트](https://support.microsoft.com/lifecycle)를 확인 합니다.
  
## <a name="where-can-i-go-next"></a>다음으로 이동할 위치

SharePoint Server는 자체 서버에 온-프레미스로 설치할 수 있습니다. 또는 Microsoft 365의 일부인 온라인 서비스인 SharePoint Online을 사용할 수 있습니다. 옵션은 다음과 같습니다.
  
- SharePoint Online으로 마이그레이션합니다.
    
- SharePoint Server 온-프레미스를 업그레이드 합니다.
    
- 위의 두 가지 작업을 모두 수행 합니다.
    
- [SharePoint 하이브리드](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx) 솔루션을 구현 합니다.
    
서버 팜 유지 관리, 사용자 지정 내용 유지 관리 또는 마이그레이션, SharePoint Server에 필요한 하드웨어 업그레이드와 관련 하 여 숨겨진 비용을 파악 해야 합니다. 필요한 경우 온-프레미스 SharePoint Server 팜이 있는 것을 rewarding 합니다. 하지만 고급 사용자 지정을 수행 하지 않고 레거시 SharePoint 서버에서 팜을 실행 하는 경우에는 SharePoint Online으로 마이그레이션하는 것을 활용할 수 있습니다.
  
> [!IMPORTANT]
> SharePoint 2007의 콘텐츠가 자주 사용 되지 않는 경우에는 다른 옵션을 사용할 수 있습니다. 일부 SharePoint 관리자는 Microsoft 365 구독을 만들고, 새 SharePoint Online 사이트를 설정 하 고, SharePoint 2007에서 새로운 SharePoint Online 사이트에 대 한 중요 한 문서만을 제외 하는 방법을 선택 합니다. 그런 다음 SharePoint 2007 사이트에서 보관 사서함으로 데이터를 제거할 수 있습니다. 사용자가 SharePoint 2007 설치에서 데이터를 사용 하는 방법을 고려 합니다. 요구 사항을 관리 하는 독창적인 방법이 있을 수 있습니다.
  
|**SharePoint Online (SPO)**|**SharePoint Server 온-프레미스**|
|:-----|:-----|
|높은 비용 (계획/실행/확인)  <br/> |높은 비용 (계획/실행/확인)  <br/> |
|저렴 한 비용 (하드웨어 구입 없음)  <br/> |자금 비용 (하드웨어 + devs/관리자)  <br/> |
|마이그레이션 1 회 비용  <br/> |향후 마이그레이션 당 1 회 비용 반복  <br/> |
|낮은 총 소유 비용/유지 관리  <br/> |높은 총 소유 비용/유지 관리  <br/> |
   
Microsoft 365로 마이그레이션하는 경우 일회성 이동 비용이 더 많이 드는 반면, 데이터를 구성 하 고 클라우드로 수행 해야 하는 작업 및 뒤에 남길 작업을 결정 하는 데에는 많은 시간이 걸립니다. 그러나 이후 업그레이드는 자동으로 수행 되므로 하드웨어 및 소프트웨어 업데이트를 더 이상 관리할 필요가 없습니다. 또한 팜의 작동 시간은[SLA](https://go.microsoft.com/fwlink/?linkid=843153)(서비스 수준 계약)를 통해 지원 됩니다.
  
### <a name="migrate-to-sharepoint-online"></a>SharePoint Online으로 마이그레이션

SharePoint Online에 필요한 모든 기능이 포함 되어 있는지 확인 합니다. [Microsoft 365 및 Office 365 서비스 설명을](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)참조 하세요.
  
SharePoint 2007에서 SharePoint Online으로 직접 마이그레이션할 수는 없습니다. SharePoint Online으로 이동 하는 작업은 수동으로 수행 해야 합니다. SharePoint Server 2013 또는 SharePoint Server 2016로 업그레이드 하는 경우 SharePoint 마이그레이션 API (예: 비즈니스용 OneDrive로 정보 마이그레이션)를 사용할 수 있습니다.
  
|**온라인 pro**|**온라인 con**|
|:-----|:-----|
|Microsoft는 SPO 하드웨어 및 모든 하드웨어 관리를 제공 합니다.  <br/> |사용 가능한 기능은 SharePoint Server 온-프레미스와 SPO에서 서로 다를 수 있습니다.  <br/> |
|구독에 대 한 전역 관리자 이며 관리자를 SPO 사이트에 할당할 수 있습니다.  <br/> |SharePoint Server 온-프레미스의 팜 관리자가 사용할 수 있는 일부 작업은 존재 하지 않거나 Microsoft 365의 SharePoint 관리자 역할에 포함 되지 않을 수도 있습니다.  <br/> |
|Microsoft는 기본 하드웨어 및 소프트웨어에 패치, 수정 사항 및 업데이트를 적용 합니다. <br/> |서비스의 기본 파일 시스템에 대 한 액세스 권한이 없기 때문에 사용자 지정이 제한 됩니다.  <br/> |
|Microsoft는 서비스 수준 [계약](https://go.microsoft.com/fwlink/?linkid=843153) 을 게시 하 고 신속 하 게 이동 하 여 서비스 수준 인시던트를 해결 합니다. <br/> |백업 및 복원 및 기타 복구 옵션은 SharePoint Online의 서비스에 의해 자동화 됩니다. 사용 하지 않는 경우 백업을 덮어씁니다. <br/> |
|보안 테스트 및 서버 성능 조정은 Microsoft의 서비스에서 지속적으로 수행 됩니다. <br/> |사용자 인터페이스 및 기타 SharePoint 기능의 변경 내용은 서비스에 의해 설치 되며 설정 또는 해제 해야 할 수 있습니다. <br/> |
|Microsoft 365는 다양 한 업계 표준을 [충족 합니다.](https://go.microsoft.com/fwlink/?linkid=843165)  <br/> |마이그레이션에 대 한 [Fasttrack](https://www.microsoft.com/fasttrack/microsoft-365) 지원은 제한 됩니다.  <br/> 업그레이드의 대부분은 수동 또는 [SharePoint Online 및 OneDrive 마이그레이션 콘텐츠 로드맵](https://go.microsoft.com/fwlink/?linkid=843184)에 설명 된 SPO 마이그레이션 API를 통해 진행 됩니다.  <br/> |
|Microsoft 지원 엔지니어 및 데이터 센터 직원은 구독에 대 한 무제한 관리자 액세스 권한을 갖지 않습니다. <br/> |최신 버전의 SharePoint를 지원 하도록 하드웨어를 업그레이드 해야 하는 경우 또는 보조 팜이 업그레이드에 필요한 경우에는 추가 비용이 있을 수 있습니다.  <br/> |
|파트너는 데이터를 SharePoint Online으로 마이그레이션하는 일회성 작업을 지원할 수 있습니다.  <br/> ||
|온라인 제품은 자동으로 업데이트 됩니다. 기능은 사용 중지 수 있지만 실제로는 지원 되지 않습니다. <br/> ||
   
새 Microsoft 365 사이트를 만들고 필요에 따라 데이터를 수동으로 마이그레이션하려는 경우 [microsoft 365 옵션](https://www.microsoft.com/microsoft-365/)을 확인 합니다.
  
### <a name="upgrade-sharepoint-server-on-premises"></a>SharePoint Server 온-프레미스 업그레이드

SharePoint 업그레이드에서 버전을 건너뛰는 방법은 없습니다. 업그레이드는 순차적으로 진행 됩니다.
  
- Sharepoint 2007 \> sharepoint server 2010 sharepoint server \> 2013 \> sharepoint server 2016
   
SharePoint 2007에서 SharePoint Server 2016로 이동 하는 것은 상당한 시간 투자를 의미 하며 하드웨어 비용 (SQL server도 업그레이드 해야 함), 소프트웨어 및 관리를 포함 하는 것입니다. 사용자 지정 항목을 업그레이드 하거나 중단 해야 합니다.
  
> [!NOTE]
> 수명 종료 SharePoint 2007 팜을 유지 관리 하 고, 새 하드웨어에 SharePoint Server 2016 팜을 설치한 다음, 별도의 팜을 함께 실행 하 고 콘텐츠를 수동으로 마이그레이션을 계획 하 고 실행 하 여 콘텐츠를 다운로드 하 고 다시 업로드 하는 것이 가능 합니다. 하지만 수동 이동에 대 한 몇 가지 주의할 점 (예: 수동으로 이동한 계정을 수동 이동을 수행 하는 계정의 별칭으로 마지막으로 수정한 문서 이동) 또한 사이트, 하위 사이트, 사용 권한 및 목록 구조를 다시 만드는 것과 같은 시간 전에 수행 해야 하는 작업을 고려해 야 합니다. 마이그레이션에 대 한 영향을 줄이기 위해 저장소 또는 삭제로 이동할 수 있는 데이터를 미리 고려 합니다.
  
업그레이드 하기 전에 환경을 정리 하는 것이 중요 합니다. 업그레이드 하기 전에 기존 팜이 제대로 작동 하 고 있어야 합니다.
  
*지원 및 지원 되지 않는 업그레이드 경로* 를 검토 해야 합니다. 
  
- [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843157)
    
사용자 지정 내용이 있는 경우 마이그레이션 경로의 각 단계에 대 한 계획을 수립 하는 것이 중요 합니다. 
  
- [SharePoint 2007](https://go.microsoft.com/fwlink/?linkid=843158)
    
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843160)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843162)
    
|**온-프레미스 pro**|**온-프레미스 con**|
|:-----|:-----|
|서버 하드웨어에서 SharePoint 팜의 모든 측면에 대 한 모든 권한  <br/> |모든 휴식 및 수정 사항은 회사의 책임입니다 (제품의 지원 종료를 초과 하지 않는 경우에는 Microsoft Support를 지불 하면 됩니다.).  <br/> |
|하이브리드를 통해 온-프레미스 팜을 SharePoint Online 구독에 연결 하는 옵션을 사용 하는 SharePoint Server 온-프레미스의 전체 기능 집합입니다.  <br/> |업그레이드, 패치, 보안 픽스 및 모든 SharePoint Server의 온-프레미스 유지 관리  <br/> |
|보다 강력한 사용자 지정을 위한 모든 권한  <br/> |[Microsoft 규정 준수 제품은](https://go.microsoft.com/fwlink/?linkid=843165) 온-프레미스에서 수동으로 구성 해야 합니다.  <br/> |
|보안 테스트 및 서버 성능 조정은 온-프레미스에서 수행 됩니다 (컨트롤 아래).  <br/> |Microsoft 365은 sharepoint Online에서 SharePoint Server 온-프레미스와 상호 작용 하지 않는 기능을 사용할 수 있도록 합니다.  <br/> |
|파트너는 다음 버전의 SharePoint Server (및 이후)로 데이터 마이그레이션을 지원할 수 있습니다.  <br/> |Sharepoint Server 사이트에서는 SharePoint Online에 표시 되는 대로 [SSL/TLS](https://go.microsoft.com/fwlink/?linkid=843167) 인증서를 자동으로 사용 하지 않습니다.  <br/> |
|SharePoint Server 온-프레미스의 명명 규칙, 백업 및 복원 및 기타 복구 옵션에 대 한 모든 권한  <br/> |SharePoint Server 온-프레미스는 제품 수명 주기에 중요 합니다.  <br/> |
   
### <a name="upgrade-resources"></a>리소스 업그레이드

환경이 하드웨어 및 소프트웨어 요구 사항을 충족 하는지 확인 한 다음 지원 되는 업그레이드 방법을 따릅니다.
  
- 다음 **에 대 한 하드웨어/소프트웨어 요구 사항**: 
    
    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)
    
- 다음 **에 대 한 소프트웨어 경계 및 제한** 사항: 
    
    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843245)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)
    
- **업그레이드 프로세스 개요**: 
    
    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843250)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)
    
### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>SharePoint Online과 온-프레미스 간에 SharePoint 하이브리드 솔루션 만들기

마이그레이션 요구 사항에 대 한 대답이 온-프레미스에서 제공 되는 자체 제어와 SharePoint Online에서 제공 하는 소유 지분 비용이 더 많은 경우에는 하이브리드를 통해 SharePoint Server 2013 또는 2016 팜을 SharePoint Online에 연결할 수 있습니다. [SharePoint 하이브리드 솔루션에 대해 알아봅니다](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx).
  
하이브리드 SharePoint Server 팜이 비즈니스에 이익이 되는 경우 기존 유형의 하이브리드을 숙지 하 고 온-프레미스 SharePoint 팜과 Microsoft 365 구독 간에 연결을 구성 하는 방법에 대해 알아봅니다.
  
| 옵션 | 설명 |
|:-----|:-----|
[Microsoft 규정 준수 제품](https://go.microsoft.com/fwlink/?linkid=843165)  <br/> |마이그레이션에 대 한 [Fasttrack](https://www.microsoft.com/fasttrack/microsoft-365) 지원은 제한 됩니다.  <br/> 업그레이드의 대부분은 수동 또는 [SharePoint Online 및 OneDrive 마이그레이션 콘텐츠 로드맵](https://go.microsoft.com/fwlink/?linkid=843184)에 설명 된 SPO 마이그레이션 API를 통해 진행 됩니다.  <br/> |
|Microsoft 지원 엔지니어 및 데이터 센터 직원은 구독에 대 한 무제한 관리자 액세스 권한이 없습니다.<br/> |최신 버전의 SharePoint를 지원 하도록 하드웨어 인프라를 업그레이드 해야 하거나 업그레이드에 보조 팜이 필요한 경우에는 추가 비용이 있을 수 있습니다.  <br/> |
|파트너는 데이터를 SharePoint Online으로 마이그레이션하는 일회성 작업을 지원할 수 있습니다.  <br/> ||
|온라인 제품은 서비스 간에 자동으로 업데이트 됩니다. 기능이 사용 중지 수는 있지만 실제로는 지원 되지 않습니다.<br/> ||
   
새 Microsoft 365 사이트를 만들고 필요에 따라 데이터를 수동으로 마이그레이션하려는 경우 [microsoft 365 옵션](https://www.microsoft.com/microsoft-365/)을 확인 합니다.
  
### <a name="upgrade-sharepoint-server-on-premises"></a>SharePoint Server 온-프레미스 업그레이드

SharePoint 업그레이드에서 버전을 건너뛰는 방법은 없습니다. 업그레이드는 순차적으로 진행 됩니다.
  
- Sharepoint 2007 \> sharepoint server 2010 sharepoint server \> 2013 \> sharepoint server 2016
   
SharePoint 2007에서 SharePoint Server 2016로 이동 하려면 시간이 상당히 투자 되 고 하드웨어 비용 (SQL server도 업그레이드 해야 함), 소프트웨어 및 관리가 수반 됩니다. 사용자 지정 항목을 업그레이드 하거나 중단 해야 합니다.
  
> [!NOTE]
> 수명 종료 SharePoint 2007 팜을 유지 관리 하 고, 새 하드웨어에 SharePoint Server 2016 팜을 설치한 다음, 별도의 팜을 함께 실행 하 고 콘텐츠를 수동으로 마이그레이션을 계획 하 고 실행 하 여 콘텐츠를 다운로드 하 고 다시 업로드 하는 것이 가능 합니다. 그러나 마지막으로 수정한 계정을 변경 하는 문서를 수동 이동을 수행 하는 계정의 별칭으로 이동 하는 것과 같은 수동 이동에 대 한 주의를 들 수 있으며, 사이트, 하위 사이트, 사용 권한 및 목록 구조를 다시 만드는 것과 같이 시간에 앞서 수행 해야 하는 작업을 고려해 야 합니다. 마이그레이션에 대 한 영향을 줄이기 위해 저장소 또는 삭제로 이동할 수 있는 데이터를 고려 합니다.
  
업그레이드 전에 환경을 정리 합니다. 업그레이드 하기 전에 기존 팜이 제대로 작동 하 고 있어야 합니다. 
  
*지원 및 지원 되지 않는 업그레이드 경로* 를 검토 해야 합니다. 
  
- [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843157)
    
*사용자 지정* 내용이 있는 경우 마이그레이션 경로의 각 단계에 대 한 업그레이드 계획을 수립 하는 것이 중요 합니다. 
  
- [SharePoint 2007](https://go.microsoft.com/fwlink/?linkid=843158)
    
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843160)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843162)
    
|**온-프레미스 Pro**|**온-프레미스 Con**|
|:-----|:-----|
|서버 하드웨어에서 SharePoint 팜의 모든 측면에 대 한 모든 권한  <br/> |모든 휴식 및 수정 사항은 회사의 책임입니다. (제품이 더 이상 지원 되지 않는 경우에는 Microsoft 지원을 유료으로 사용할 수 있습니다.)  <br/> |
|하이브리드를 통해 온-프레미스 팜을 SharePoint Online 구독에 연결 하는 옵션을 사용 하는 SharePoint Server 온-프레미스의 전체 기능 집합입니다.  <br/> |업그레이드, 패치, 보안 픽스 및 모든 SharePoint Server의 온-프레미스 유지 관리  <br/> |
|보다 강력한 사용자 지정을 위한 모든 권한  <br/> |[Microsoft 규정 준수 제품은](https://go.microsoft.com/fwlink/?linkid=843165) 온-프레미스에서 수동으로 구성 해야 합니다.  <br/> |
|보안 테스트 및 서버 성능 조정은 사용자의 제어에 따라 온-프레미스에서 수행 됩니다.  <br/> |Microsoft 365은 sharepoint Online에서 SharePoint Server 온-프레미스와 상호 작용 하지 않는 기능을 사용 하도록 설정할 수 있습니다.  <br/> |
|파트너는 다음 버전의 SharePoint Server (및 이외)로 데이터를 마이그레이션하는 데 도움이 될 수 있습니다.  <br/> |Sharepoint Server 사이트에서는 SharePoint Online에 표시 되는 대로 [SSL/TLS](https://go.microsoft.com/fwlink/?linkid=843167) 인증서를 자동으로 사용 하지 않습니다.  <br/> |
|SharePoint Server 온-프레미스의 명명 규칙, 백업 및 복원 및 기타 복구 옵션에 대 한 모든 권한  <br/> |SharePoint Server 온-프레미스는 제품 수명 주기에 중요 합니다.  <br/> |
   
### <a name="upgrade-resources"></a>리소스 업그레이드

사용자 환경이 하드웨어 및 소프트웨어 요구 사항을 충족 하는지 확인 합니다. 그런 다음 지원 되는 업그레이드 방법을 따릅니다.
  
- **다음에 대 한 하드웨어/소프트웨어 요구 사항:** 
    
    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)
    
- **다음에 대 한 소프트웨어 경계 및 제한 사항:** 
    
    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843245)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)
    
- **업그레이드 프로세스 개요:** 
    
    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843250)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)
    
### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>SharePoint Online과 온-프레미스 간에 SharePoint 하이브리드 솔루션 만들기

마이그레이션 요구 사항에 대 한 대답이 온-프레미스에서 제공 되는 자체 제어와 SharePoint Online에서 제공 하는 소유 지분 비용이 더 많은 경우에는 하이브리드를 통해 SharePoint Server 2013 또는 2016 팜을 SharePoint Online에 연결할 수 있습니다. [SharePoint 하이브리드 솔루션에 대 한 자세한 정보](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)
  
하이브리드 SharePoint Server 팜이 비즈니스에 이익이 되는 경우 기존 유형의 하이브리드을 숙지 하 고 온-프레미스 SharePoint 팜과 Microsoft 365 구독 간에 연결을 구성 하는 방법에 대해 알아봅니다.
  
[테스트 랩 가이드](m365-enterprise-test-lab-guides.md)를 사용 하 여 설정할 수 있는 Microsoft 365 개발/테스트 환경을 만드는 것이 어떻게 작동 하는지 확인 하는 좋은 방법 중 하나입니다. 평가판을 받거나 Microsoft 365 구독을 구매한 후에는 SharePoint Online에서 데이터를 마이그레이션할 수 있는 사이트 모음, 웹 및 문서 라이브러리를 만들 수 있습니다. 마이그레이션 API를 사용 하 여 수동으로 마이그레이션하거나, 하이브리드 마법사를 통해 내 사이트 콘텐츠를 비즈니스용 OneDrive로 마이그레이션할 수 있습니다.
  
> [!NOTE]
> 하이브리드 옵션을 사용 하려면 SharePoint 2007 팜을 온-프레미스에서 SharePoint Server 2013 또는 SharePoint Server 2016로 업그레이드 해야 합니다.
  
## <a name="related-topics"></a>관련 항목

[업그레이드 문제 해결 및 다시 시작 (Office SharePoint Server 2007)](https://go.microsoft.com/fwlink/?linkid=843192)
  
[업그레이드 문제 해결 (SharePoint Server 2010)](https://go.microsoft.com/fwlink/?linkid=843194)
  
[SharePoint 2013에서 데이터베이스 업그레이드 문제 해결](https://go.microsoft.com/fwlink/?linkid=843195)
  
[업그레이드에 도움이 되는 Microsoft 파트너를 검색 합니다.](https://go.microsoft.com/fwlink/?linkid=841249)
  
[Office 2007 서버 및 클라이언트에서 업그레이드 하는 데 도움이 되는 리소스](upgrade-from-office-2007-servers-and-products.md)
  
