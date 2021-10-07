---
title: Microsoft Azure에서 SharePoint Server 2013 재해 복구
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 04/17/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Deployment
- seo-marvel-apr2020
ms.assetid: e9d14cb2-ff28-4a18-a444-cebf891880ea
description: 이 문서에서는 Azure를 사용하여 팜에 대한 재해 복구 환경을 만드는 SharePoint 설명합니다.
ms.openlocfilehash: 80b85aeb602cadf3fb2306c5ef929acbe35d3762
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60214180"
---
# <a name="sharepoint-server-2013-disaster-recovery-in-microsoft-azure"></a>Microsoft Azure에서 SharePoint Server 2013 재해 복구

 Azure를 사용하여 팜에 대한 재해 복구 환경을 만들 수 SharePoint 있습니다. 이 문서에서는 이 솔루션을 디자인하고 구현하는 방법을 설명합니다.

 **SharePoint Server 2013 재해 복구 개요 비디오 시청**
> [!VIDEO https://www.microsoft.com/videoplayer/embed/1b73ec8f-29bd-44eb-aa3a-f7932784bfd9?autoplay=false]
  
 재해로 SharePoint 환경을 복구할 때 가장 우선 순위는 시스템을 다시 빠르게 실행하는 것입니다. 재해 복구를 SharePoint 백업 환경이 이미 실행되고 있는 경우 더 빠르고 쉽게 Microsoft Azure. 이 비디오에서는 웜 장애 조치(failover) SharePoint 기본 개념을 설명하고 이 문서에서 사용할 수 있는 전체 세부 정보를 보완합니다.
  
다음 솔루션 모델과 함께 이 문서를 SharePoint **재해 복구를 Microsoft Azure.**
  
[![SharePoint 복구 프로세스를 Azure로 변경합니다.](../media/SP-DR-Azure.png)](https://go.microsoft.com/fwlink/p/?LinkId=392555)
  
 [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392555) |  [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392554)
  
## <a name="use-azure-infrastructure-services-for-disaster-recovery"></a>재해 복구를 위해 Azure 인프라 서비스 사용

대부분의 조직에는 조직의 재해 복구 환경이 SharePoint 복구 환경이 없습니다. 이 환경은 사내에서 구축 및 유지 관리하기에 비용이 많이 들 수 있습니다. Azure 인프라 서비스는 재해 복구 환경에 대해 사내 대안보다 유연성이 높고 비용이 덜 드는 융통성 있는 옵션을 제공합니다.
  
Azure 인프라 서비스를 사용할 경우의 이점은 다음과 같습니다.
  
- **비용이 많이 드는 리소스 수 감소** 프레미스 재해 복구 환경보다 적은 수의 리소스를 유지 관리하고 비용을 지불합니다. 리소스 수는 콜드 대기, 웜 대기 또는 핫 대기 중 어떤 재해 복구 환경을 선택하는지에 따라 달라 집니다.
    
- **더 나은 리소스 유연성** 재해가 발생하면 부하 요구 사항에 SharePoint 복구 팜을 쉽게 확장할 수 있습니다. 리소스가 더 이상 필요하지 않습니다.
    
- **낮은 데이터 센터 약정** 다른 지역의 보조 데이터 센터에 투자하는 대신 Azure 인프라 서비스를 사용합니다.
    
재해 복구를 시작하는 조직에는 덜 복잡한 옵션과 복구 요구 사항이 높은 조직을 위한 고급 옵션이 있습니다. 콜드, 웜 및 핫 대기 환경에 대한 정의는 환경이 클라우드 플랫폼에서 호스팅된 경우 약간 다릅니다. 다음 표에서는 Azure에서 복구 팜을 SharePoint 환경에 대해 설명합니다.
  
**표: 복구 환경**

|**복구 환경 유형**|**설명**|
|:-----|:-----|
|핫  <br/> |완전히 크기의 팜이 프로비전, 업데이트 및 대기에서 실행됩니다.  <br/> |
|웜  <br/> |팜이 구축되고 가상 컴퓨터도 실행되고 업데이트됩니다.  <br/> 복구에는 콘텐츠 데이터베이스 연결, 서비스 응용 프로그램 프로비전 및 콘텐츠 크롤링이 포함됩니다.  <br/> 팜은 더 작은 버전의 프로덕션 팜이 될 수 있으며 전체 사용자 기반을 지원하도록 확장할 수 있습니다.  <br/> |
|콜드  <br/> |팜이 완전히 구축되지만 가상 컴퓨터는 중지됩니다.  <br/> 환경을 유지 관리하기 위해 가상 컴퓨터를 수시로 시작하고, 패치하고, 업데이트하고, 환경을 확인하는 작업도 포함됩니다.  <br/> 재해 발생 시 전체 환경을 시작하십시오.  <br/> |
   
조직의 복구 시간 목표(RTOS) 및 복구 지점 목표(RPOS)를 평가하는 것이 중요합니다. 이러한 요구 사항에 따라 조직에 가장 적합한 투자 환경이 결정됩니다.
  
이 문서의 지침에서는 웜 대기 환경을 구현하는 방법을 설명합니다. 이러한 종류의 환경을 지원하려면 추가 절차를 따라야 하지만 콜드 대기 환경에 맞게 해당 환경을 적응할 수도 있습니다. 이 문서에서는 핫 대기 환경을 구현하는 방법에 대해 설명하지 않습니다.
  
재해 복구 솔루션에 대한 자세한 내용은 [High availability and disaster recovery concepts in SharePoint 2013](/SharePoint/administration/high-availability-and-disaster-recovery-concepts) 및 Choose a disaster recovery [strategy for SharePoint 2013을](/SharePoint/administration/plan-for-disaster-recovery)참조하십시오.
  
## <a name="solution-description"></a>솔루션 설명

웜 대기 재해 복구 솔루션에는 다음 환경이 필요합니다.
  
- 프로덕션 팜의 SharePoint 프레미스
    
- Azure의 SharePoint 팜 복구
    
- 두 환경 간의 사이트 간 VPN 연결
    
다음 그림에서는 이러한 세 가지 요소를 보여 주었다.
  
**그림: Azure의 웜 대기 솔루션 요소**

![Azure의 SharePoint 웜 대기 솔루션의 요소입니다.](../media/AZarch-AZWarmStndby.png)
  
SQL Server DFSR(분산 파일 시스템 복제)을 사용한 로그 전달은 Azure의 복구 팜에 데이터베이스 백업 및 트랜잭션 로그를 복사하는 데 사용됩니다. 
  
- DFSR은 프로덕션 환경에서 복구 환경으로 로그를 전송합니다. WAN 시나리오에서 DFSR은 Azure의 보조 서버로 직접 로그를 전달하는 것보다 더 효율적입니다.
    
- 로그는 Azure의 복구 SQL Server 로그에 재생됩니다.
    
- 복구 연습이 수행될 때까지 SharePoint 콘텐츠 데이터베이스에서 로그가 발송된 데이터베이스를 연결하지 않습니다.
    
다음 단계를 수행하여 팜을 복구합니다.
  
1. 로그 전달을 중지합니다.
    
2. 기본 팜에 대한 트래픽 허용을 중지합니다.
    
3. 최종 트랜잭션 로그를 재생합니다.
    
4. 콘텐츠 데이터베이스를 팜에 연결합니다.
    
5. 복제된 서비스 데이터베이스에서 서비스 응용 프로그램을 복원합니다.
    
6. 복구 팜을 지점으로 DNS(Domain Name System) 레코드를 업데이트합니다.
    
7. 전체 크롤링을 시작합니다.
    
라이브 복구가 원활하게 실행되도록 이러한 단계를 정기적으로 리허설하고 문서화하는 것이 좋습니다. 콘텐츠 데이터베이스를 연결하고 서비스 응용 프로그램을 복원하는 데는 시간이 걸릴 수 있으며 일반적으로 몇 가지 수동 구성이 필요합니다.
  
복구가 수행된 후 이 솔루션은 다음 표에 나열된 항목을 제공합니다.
  
**표: 솔루션 복구 목표**

|**항목**|**설명**|
|:-----|:-----|
|사이트 및 콘텐츠  <br/> |사이트 및 콘텐츠는 복구 환경에서 사용할 수 있습니다.  <br/> |
|새 검색 인스턴스  <br/> |이 웜 대기 솔루션에서는 검색 데이터베이스에서 검색이 복원되지 않습니다. 복구 팜의 검색 구성 요소는 프로덕션 팜과 최대한 비슷하게 구성됩니다. 사이트 및 콘텐츠가 복원되면 전체 크롤링이 시작되어 검색 인덱스가 다시 생성됩니다. 사이트 및 콘텐츠를 사용할 수 있도록 만들기 위해 크롤링이 완료될 때까지 기다릴 필요는 없습니다.  <br/> |
|서비스  <br/> | 데이터베이스에 데이터를 저장하는 서비스는 로그 제공 데이터베이스에서 복원됩니다. 데이터베이스에 데이터를 저장하지 않는 서비스는 간단히 시작됩니다. <br/>  데이터베이스가 있는 모든 서비스를 복원할 필요는 없습니다. 다음 서비스는 데이터베이스에서 복원할 필요가 없습니다. 장애 조치(failover) 후 간단히 시작할 수 있습니다. <br/>  Usage and Health Data Collection <br/>  State Service <br/>  Word 자동화 <br/>  데이터베이스를 사용하지 않는 다른 모든 서비스 <br/> |
   
MCS(Microsoft Consulting Services) 또는 파트너와 협력하여 보다 복잡한 복구 목표를 해결할 수 있습니다. 이러한 설명은 다음 표에 요약됩니다.
  
**표: MCS 또는 파트너가 해결할 수 있는 기타 항목**

|**항목**|**설명**|
|:-----|:-----|
|사용자 지정 팜 솔루션 동기화  <br/> |이상적으로 복구 팜 구성은 프로덕션 팜과 동일합니다. 컨설턴트 또는 파트너와 협력하여 사용자 지정 팜 솔루션을 복제할지 여부와 두 환경을 동기화된 환경에 유지하기 위한 프로세스가 있는지 여부를 평가할 수 있습니다.  <br/> |
|데이터 원본에 대한 연결(사내 데이터 원본)  <br/> |백업 도메인 컨트롤러(BDC) 연결 및 검색 콘텐츠 원본과 같은 백 엔드 데이터 시스템에 대한 연결을 복제하는 것은 실용적이지 않을 수 있습니다.  <br/> |
|검색 복원 시나리오  <br/> |엔터프라이즈 검색 배포는 매우 고유하고 복잡하기 때문에 데이터베이스에서 검색을 복원하려면 더 많은 투자가 필요합니다. 컨설턴트 또는 파트너와 협력하여 조직에 필요할 수 있는 검색 복원 시나리오를 식별하고 구현할 수 있습니다.  <br/> |
   
이 문서에서 제공하는 지침에서는 사내 팜이 이미 설계 및 배포되어 있는 것으로 가정합니다.
  
## <a name="detailed-architecture"></a>자세한 아키텍처

Azure의 복구 팜 구성은 다음을 포함하여 프로덕션 팜의 사내와 동일합니다.
  
- 서버 역할의 동일한 표현
    
- 동일한 사용자 지정 구성
    
- 검색 구성 요소의 동일한 구성
    
Azure의 환경은 더 작은 버전의 프로덕션 팜일 수 있습니다. 장애 조치(failover) 후 복구 팜을 수립할 계획인 경우 각 서버 역할 유형을 처음에 나타내는 것이 중요합니다.
  
일부 구성은 장애 조치(failover) 환경에서 복제하는 것이 실용적이지 않을 수 있습니다. 장애 조치 팜에서 예상 서비스 수준을 제공하는지 확인하도록 장애 조치(failover) 절차 및 환경을 테스트해야 합니다.
  
이 솔루션에서는 특정 팜에 대한 특정 토폴로지가 SharePoint 않습니다. 이 솔루션의 초점은 장애 조치 팜에 Azure를 사용하여 두 환경 간에 로그 전달 및 DFSR을 구현하는 것입니다.
  
### <a name="warm-standby-environments"></a>웜 대기 환경

웜 대기 환경에서는 Azure 환경의 모든 가상 머신이 실행됩니다. 환경은 장애 조치(failover) 연습 또는 이벤트를 준비합니다.
  
다음 그림에서는 온-프레미스 SharePoint 팜에서 웜 대기 환경으로 구성된 Azure 기반 SharePoint 팜으로의 재해 복구 솔루션을 보여 줍니다.
  
**그림: 프로덕션 팜 및 웜 대기 복구 팜의 토폴로지 및 주요 요소**

![SharePoint 팜 및 웜 대기 복구 팜의 토폴로지](../media/AZarch-AZWarmStndby.png)
  
다음은 이 다이어그램에 대한 설명입니다.
  
- 두 환경, 즉 온-프레미스 SharePoint Azure의 웜 대기 팜이 나란히 설명되어 있습니다.
    
- 각 환경에는 파일 공유가 있습니다.
    
- 각 팜에는 네 개의 계층이 포함됩니다. 고가용성을 달성하기 위해 각 계층에는 프런트 엔드 서비스, 분산 캐시, 백 엔드 서비스 및 데이터베이스와 같은 특정 역할에 대해 동일하게 구성된 두 개의 서버 또는 가상 컴퓨터를 포함합니다. 이 그림에서는 특정 구성 요소를 호출하는 것이 중요하지 않습니다. 두 팜은 동일하게 구성됩니다.
    
- 네 번째 계층은 데이터베이스 계층입니다. 로그 전달은온-프레미스 환경의 보조 데이터베이스 서버에서 동일한 환경의 파일 공유로 로그를 복사하는 데 사용됩니다.
    
- DFSR은 온-프레미스 환경의 파일 공유에서 Azure 환경의 파일 공유로 파일을 복사합니다.
    
- 로그 전달은 Azure 환경의 파일 공유에서 복구 환경의 SQL Server AlwaysOn 가용성 그룹에 있는 기본 복제본으로 로그를 재생합니다.
    
### <a name="cold-standby-environments"></a>콜드 대기 환경

콜드 대기 환경에서는 대부분의 SharePoint 가상 컴퓨터를 종료할 수 있습니다. 각 가상 컴퓨터를 도메인과 동기화할 수 있도록 가끔씩 2주 또는 한 달에 한 번씩 가상 컴퓨터를 시작하는 것이 좋습니다. 로그 전달 및 DFSR의 연속 작업을 보장하려면 Azure 복구 환경의 다음 가상 컴퓨터를 계속 실행해야 합니다.
  
- 파일 공유
    
- 기본 데이터베이스 서버
    
- 도메인 서비스 및 DNS를 실행하는 Windows Server Active Directory 가상 컴퓨터 하나 이상
    
다음 그림에서는 파일 공유 가상 컴퓨터 및 기본 SharePoint Azure 장애 조치(failover) 환경을 보여 줍니다. 다른 모든 SharePoint 가상 컴퓨터를 중지합니다. DNS 및 WINDOWS SERVER ACTIVE DIRECTORY 실행 중인 가상 컴퓨터는 표시되지 않습니다.
  
**그림: 가상 컴퓨터를 실행하는 콜드 대기 복구 팜**

![Azure의 SharePoint 콜드 대기 솔루션의 요소입니다.](../media/AZarch-AZColdStndby.png)
  
콜드 대기 환경으로의 장애 조치(failover)가 시작된 후 모든 가상 컴퓨터를 시작하고 AlwaysOn 가용성 그룹과 같이 데이터베이스 서버의 고가용성을 SQL Server 구성해야 합니다.
  
여러 저장소 그룹을 구현하는 경우(데이터베이스가 여러 SQL Server 고가용성 집합에 분산되어 있는 경우 저장소 그룹과 연결된 로그를 수락하려면 각 저장소 그룹의 기본 데이터베이스가 실행되고 있어야 합니다.
  
### <a name="skills-and-experience"></a>기술 및 환경

이 재해 복구 솔루션에는 여러 기술이 사용됩니다. 이러한 기술이 예상대로 상호 작용하도록 보장하려면 사내 및 Azure 환경의 각 구성 요소를 올바르게 설치 및 구성해야 합니다. 이 솔루션을 설정하는 사람 또는 팀이 다음 문서에 설명된 기술에 대한 강력한 실무 지식과 실무 지식을 습득하는 것이 좋습니다.
  
- [DFS(분산 파일 시스템) 복제 서비스](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj127250(v=ws.11))
    
- [Windows WSFC(서버 장애 조치(failover) 클러스터링) SQL Server](/sql/sql-server/failover-clusters/windows/windows-server-failover-clustering-wsfc-with-sql-server)
    
- [AlwaysOn 가용성 그룹(SQL Server)](/sql/database-engine/availability-groups/windows/always-on-availability-groups-sql-server)
    
- [데이터베이스 백업 및 SQL Server 복원](/sql/relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases)
    
- [SharePoint Server 2013 설치 및 팜 배포](/SharePoint/install/installation-and-configuration-overview)
    
- [Microsoft Azure](/azure/)
    
마지막으로 이러한 기술과 관련된 작업을 자동화하는 데 사용할 수 있는 스크립팅 기술을 사용하는 것이 좋습니다. 사용 가능한 사용자 인터페이스를 사용하여 이 솔루션에 설명된 모든 작업을 완료할 수 있습니다. 그러나 수동 방식은 시간이 오래 걸리고 오류가 발생하기 까다로우며 불일치한 결과를 제공합니다.
  
Windows PowerShell 외에도 Windows PowerShell, SQL Server Server 및 Azure용 SharePoint 라이브러리도 있습니다. 재해 복구 환경을 구성하고 SQL 시간을 줄이는 데에도 도움이 될 수 있는 T-T-2를 잊지 마세요.
  
## <a name="disaster-recovery-roadmap"></a>재해 복구 로드맵

![재해 복구 SharePoint 로드맵의 시각적 표현입니다.](../media/Azure-DRroadmap.png)
  
이 로드맵에서는 프로덕션에 배포된 SharePoint Server 2013 팜이 이미 있는 것으로 가정합니다.
  
**표: 재해 복구 로드맵**

|**작업 단계**|**설명**|
|:-----|:-----|
|1단계  <br/> |재해 복구 환경을 디자인합니다.  <br/> |
|2단계  <br/> |Azure Virtual Network 및 VPN 연결을 생성합니다.  <br/> |
|3단계  <br/> |Azure Windows Active Directory 및 Domain Name Services를 배포합니다.  <br/> |
|4단계  <br/> |Azure에서 SharePoint 복구 팜을 배포합니다.  <br/> |
|5단계  <br/> |팜 간에 DFSR을 설정합니다.  <br/> |
|6단계  <br/> |복구 팜에 대한 로그 전달을 설정합니다.  <br/> |
|7단계  <br/> | 장애 조치 및 복구 솔루션의 유효성을 검사합니다. 여기에는 다음 절차 및 기술이 포함됩니다. <br/>  로그 전달을 중지합니다. <br/>  백업을 복원합니다. <br/>  콘텐츠를 크롤링합니다. <br/>  서비스를 복구합니다. <br/>  DNS 레코드 관리 <br/> |
   
## <a name="phase-1-design-the-disaster-recovery-environment"></a>1단계: 재해 복구 환경 디자인

Microsoft Azure [Architectures for SharePoint 2013의](microsoft-azure-architectures-for-sharepoint-2013.md) 지침을 사용하여 SharePoint 복구 팜을 비롯한 재해 복구 환경을 디자인합니다. Azure SharePoint [재해](https://go.microsoft.com/fwlink/p/?LinkId=392554) 복구 솔루션의 그래픽을 사용하여 Visio 프로세스를 시작할 수 있습니다. Azure 환경에서 작업을 시작하기 전에 전체 환경을 디자인하는 것이 좋습니다.
  
가상 네트워크, VPN 연결, Active Directory 및 SharePoint 팜을 디자인하기 위해 Microsoft Azure [Architectures for SharePoint 2013에](microsoft-azure-architectures-for-sharepoint-2013.md) 제공된 지침 외에도 Azure 환경에 파일 공유 역할을 추가해야 합니다.
  
재해 복구 솔루션에서 로그 전달을 지원하기 위해 파일 공유 가상 컴퓨터는 데이터베이스 역할이 있는 서브넷에 추가됩니다. 또한 파일 공유는 AlwaysOn 가용성 그룹의 노드 SQL Server 노드 역할을 합니다. AlwaysOn 가용성 그룹을 사용하는 표준 SharePoint 팜에 권장되는 SQL Server 구성입니다. 
  
> [!NOTE]
> 데이터베이스가 AlwaysOn 가용성 그룹에 참여하려면 데이터베이스의 SQL Server 검토해야 합니다. 자세한 내용은 AlwaysOn 가용성 그룹에 대한 권장 사항, 제한 사항 및 [추가 정보를 참조하세요.](/sql/database-engine/availability-groups/windows/prereqs-restrictions-recommendations-always-on-availability) 
  
**그림: 재해 복구 솔루션에 사용되는 파일 서버 배치**

![데이터베이스 서버 역할이 포함된 동일한 클라우드 서비스에 추가된 파일 SharePoint VM을 보여줍니다.](../media/AZenv-FSforDFSRandWSFC.png)
  
이 다이어그램에서 파일 공유 가상 컴퓨터는 데이터베이스 서버 역할을 포함하는 Azure의 동일한 서브넷에 추가됩니다. 파일 공유 가상 컴퓨터는 파일 공유 역할과 같은 다른 서버 역할과 함께 가용성 집합에 SQL Server 않습니다.
  
로그의 고가용성이 우려되는 경우 Azure Blob SQL Server 서비스에서 백업 및 복원을 사용하여 다른 방법을 [Storage 것이 좋습니다.](/sql/relational-databases/backup-restore/sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service) 이 기능은 Blob Storage URL에 직접 로그를 저장하는 Azure의 새로운 기능입니다. 이 솔루션에는 이 기능 사용에 대한 지침이 포함되어 있지 않습니다.
  
복구 팜을 디자인할 때 성공적인 재해 복구 환경은 복구하려는 프로덕션 팜을 정확하게 반영합니다. 복구 팜의 디자인, 배포 및 테스트에서 복구 팜의 크기가 가장 중요한 것은 아닙니다. 팜 규모는 비즈니스 요구 사항에 따라 조직마다 다릅니다. 짧은 시간 동안 또는 성능 및 용량 요구에 따라 팜을 확장해야 할 때까지 축소된 팜을 사용할 수 있습니다.
  
복구 팜이 SLA(서비스 수준 계약) 요구 사항을 충족하고 비즈니스를 지원하는 데 필요한 기능을 제공하도록 프로덕션 팜과 최대한 동일하게 구성합니다. 재해 복구 환경을 디자인할 때 프로덕션 환경에 대한 변경 관리 프로세스도 살펴 봐야 합니다. 변경 관리 프로세스를 프로덕션 환경과 같은 간격으로 복구 환경을 업데이트하여 복구 환경으로 확장하는 것이 좋습니다. 변경 관리 프로세스의 일부로 팜 구성, 응용 프로그램 및 사용자의 자세한 인벤토리를 유지 관리하는 것이 좋습니다. 
  
## <a name="phase-2-create-the-azure-virtual-network-and-vpn-connection"></a>2단계: Azure Virtual Network 및 VPN 연결 만들기

커넥트 프레미스 네트워크를 Microsoft Azure Azure에서 가상 네트워크를 계획 및 [배포하는](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md) 방법과 VPN 연결을 만드는 방법을 보여줍니다. 항목의 지침에 따라 다음 절차를 완료합니다.
  
- 가상 네트워크의 개인 IP 주소 공간을 계획합니다.
    
- 가상 네트워크의 라우팅 인프라 변경 사항을 계획합니다.
    
- 사내 VPN 장치와의 트래픽에 대한 방화벽 규칙을 계획합니다.
    
- Azure에서 프레미스 간 가상 네트워크를 생성합니다.
    
- 사내 네트워크와 가상 네트워크 간의 라우팅을 구성합니다.
    
## <a name="phase-3-deploy-active-directory-and-domain-name-services-to-the-azure-virtual-network"></a>3단계: Azure Virtual Network에 Active Directory 및 도메인 이름 서비스 배포

이 단계에서는 Microsoft Azure [Architectures for SharePoint 2013에](microsoft-azure-architectures-for-sharepoint-2013.md) 설명된 바와 같이 다음 그림에 설명된 바와 같이 하이브리드 시나리오에서 Windows Server Active Directory 및 DNS를 모두 가상 네트워크에 배포합니다.
  
**그림: 하이브리드 Active Directory 도메인 구성**

![Azure Virtual Network에 배포된 두 개의 가상 컴퓨터와 SharePoint 팜 서브넷은 복제본 도메인 컨트롤러와 DNS 서버입니다.](../media/AZarch-HyADdomainConfig.png)
  
그림에서 두 가상 컴퓨터는 동일한 서브넷에 배포됩니다. 이러한 가상 컴퓨터는 각각 Active Directory 및 DNS의 두 역할을 호스팅합니다.
  
Azure에서 Active Directory를 배포하기 전에 Azure 가상 머신에 Windows Server Active Directory [지침을 읽어야 합니다.](/windows-server/identity/ad-ds/introduction-to-active-directory-domain-services-ad-ds-virtualization-level-100) 이러한 지침은 솔루션에 다른 아키텍처 또는 다른 구성 설정이 필요한지 여부를 결정하는 데 도움이 됩니다.
  
Azure에서 도메인 컨트롤러를 설정하는 방법에 대한 자세한 지침은 [Azure Virtual Networks에서 복제본 Active Directory 도메인 컨트롤러 설치를 참조하세요.](/windows-server/identity/ad-ds/introduction-to-active-directory-domain-services-ad-ds-virtualization-level-100)
  
이 단계 전에는 가상 컴퓨터를 가상 네트워크에 배포하지 않은 경우 Active Directory 및 DNS를 호스팅하기 위한 가상 컴퓨터는 솔루션에 필요한 최대 가상 컴퓨터는 아닙니다. 이러한 가상 컴퓨터를 배포하기 전에 먼저 가상 네트워크에서 사용할 가장 큰 가상 컴퓨터를 만들어야 합니다. 이렇게 하면 솔루션이 필요한 최대 크기를 허용하는 Azure의 태그에 착수할 수 있습니다. 현재 이 가상 컴퓨터는 구성할 필요가 없습니다. 간단히 만들고 옆으로 설정하기만 합니다. 이렇게 하지 않는 경우 나중에 이 문서가 작성될 때 문제인 더 큰 가상 컴퓨터를 만들려고 할 때 제한이 있을 수 있습니다. 
  
## <a name="phase-4-deploy-the-sharepoint-recovery-farm-in-azure"></a>4단계: Azure에 SharePoint 복구 팜 배포

디자인 SharePoint 따라 가상 네트워크에서 SharePoint 팜을 배포합니다. Azure에서 SharePoint 역할을 배포하기 전에 [Azure](/previous-versions/azure/dn275958(v=azure.100)) 인프라 서비스에서 SharePoint 계획을 검토하는 것이 유용할 수 있습니다.
  
개념 증명 환경을 구축하여 배운 다음 사례를 고려합니다.
  
- Azure Portal 또는 PowerShell을 사용하여 가상 컴퓨터를 만들 수 있습니다.
    
- Azure 및 Hyper-V 동적 메모리를 지원하지 않습니다. 성능 및 용량 계획에 이러한 요소를 고려해야 합니다.
    
- 가상 컴퓨터 자체가 아니라 Azure 인터페이스를 통해 가상 컴퓨터를 다시 시작합니다. Azure 인터페이스를 사용하면 더 잘 작동하고 예측이 더 가능합니다.
    
- 비용을 절약하기 위해 가상 컴퓨터를 종료하려는 경우 Azure 인터페이스를 사용합니다. 가상 컴퓨터 로그온을 종료하면 요금이 계속 증가합니다.
    
- 가상 컴퓨터의 이름 규칙 사용
    
- 가상 컴퓨터를 배포하는 데이터 센터 위치에 주의해야 합니다.
    
- Azure의 자동 크기 조정 기능은 모든 역할에 SharePoint 지원되지 않습니다.
    
- 복원할 팜의 항목(예: 사이트 모음)을 구성하지 않습니다. 
    
## <a name="phase-5-set-up-dfsr-between-the-farms"></a>5단계: 팜 간에 DFSR 설정

DFSR을 사용하여 파일 복제를 설정하기 위해 DNS 관리 스냅인을 사용합니다. 그러나 DFSR을 설정하기 전에, 프레미스 파일 서버 및 Azure 파일 서버에 로그온하고 해당 서버에서 서비스를 Windows.
  
서버 관리자 대시보드에서 다음 단계를 완료합니다.
  
- 로컬 서버를 구성합니다.
    
- **역할 및 기능 추가 마법사** 를 시작합니다.
    
- 파일 **및 Storage 서비스 노드를 니다.**
    
- **DFS 네임스페이스** 및 **DFS 복제 를 선택합니다.**
    
- **다음을** 클릭하여 마법사 단계를 완료합니다.
    
다음 표에서는 DFSR 참조 문서 및 블로그 게시물에 대한 링크를 제공합니다.
  
**표: DFSR에 대한 참조 문서**

|**제목**|**설명**|
|:-----|:-----|
|[복제](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc770278(v=ws.11)) <br/> |복제 링크가 있는 DFS 관리 TechNet 항목  <br/> |
|[DFS 복제: 서바이벌 가이드](https://go.microsoft.com/fwlink/p/?LinkId=392737) <br/> |DFS 정보에 대한 링크가 있는 Wiki  <br/> |
|[DFS 복제: 질문과 대답](/previous-versions/windows/it-pro/windows-server-2003/cc773238(v=ws.10)) <br/> |DFS 복제 TechNet 항목  <br/> |
|[Jose Barreto의 블로그](/archive/blogs/josebda/) <br/> |Microsoft 파일 서버 팀의 보안 주체 프로그램 관리자가 작성한 블로그  <br/> |
|[Microsoft Storage 팀 - 파일 캐비닛 블로그](https://go.microsoft.com/fwlink/p/?LinkId=392740) <br/> |Windows 서버의 파일 서비스 및 저장소 기능에 대한 블로그  <br/> |
   
## <a name="phase-6-set-up-log-shipping-to-the-recovery-farm"></a>6단계: 복구 팜에 대한 로그 전달 설정

로그 전달은 이 환경에서 재해 복구를 설정하는 데 중요한 구성 요소입니다. 로그 전달을 사용하여 기본 데이터베이스 서버 인스턴스에서 보조 데이터베이스 서버 인스턴스로 데이터베이스에 대한 트랜잭션 로그 파일을 자동으로 보낼 수 있습니다. 로그 전달을 설정하려면 [Configure log shipping in SharePoint 2013을 참조합니다.](/sharepoint/administration/configure-log-shipping) 
  
> [!IMPORTANT]
> SharePoint 서버의 로그 전달 지원은 특정 데이터베이스로 제한됩니다. 자세한 내용은 [Supported high availability and disaster recovery options for SharePoint databases (SharePoint 2013)을 참조하십시오.](/SharePoint/administration/supported-high-availability-and-disaster-recovery-options-for-sharepoint-databas) 
  
## <a name="phase-7-validate-failover-and-recovery"></a>7단계: 장애 조치 및 복구 유효성 검사

이 최종 단계의 목표는 재해 복구 솔루션이 계획대로 작동하는지 확인하는 것입니다. 이렇게 하여 프로덕션 팜을 종료하고 대체 복구 팜을 시작하는 장애 조치(failover) 이벤트를 만들어야 합니다. 수동으로 또는 스크립트를 사용하여 장애 조치 시나리오를 시작할 수 있습니다.
  
첫 번째 단계는 팜 서비스 또는 콘텐츠에 대한 들어오는 사용자 요청을 중지하는 것입니다. DNS 항목을 사용하지 못하게 설정하거나 프런트 엔드 웹 서버를 종료하여 이 작업을 할 수 있습니다. 팜이 "다운"된 후 복구 팜으로 장애 조치(fail over)할 수 있습니다.
  
### <a name="stop-log-shipping"></a>로그 전달 중지

팜 복구 전에 로그 전달을 중지해야 합니다. 먼저 Azure의 보조 서버에서 로그 전달을 중지한 다음 기본 서버의 사내에서 로그 전달을 중지합니다. 다음 스크립트를 사용하여 보조 서버에서 먼저 로그 전달을 중지한 다음 기본 서버에서 로그 전달을 중지합니다. 스크립트의 데이터베이스 이름은 환경에 따라 다를 수 있습니다.
  
```
-- This script removes log shipping from the server.
-- Commands must be executed on the secondary server first and then on the primary server.

SET NOCOUNT ON
DECLARE  @PriDB nvarchar(max)
,@SecDB nvarchar(250)
,@PriSrv nvarchar(250)
,@SecSrv nvarchar(250)

Set @PriDB= ''
SET @PriDB = UPPER(@PriDB)
SET @PriDB = REPLACE(@PriDB, ' ', '')
SET @PriDB = '''' + REPLACE(@PriDB, ',', ''', ''') + ''''

Set @SecDB = @PriDB

Exec ( 'Select  ''exec master..sp_delete_log_shipping_secondary_database '' + '''''''' + prm.primary_database +  ''''''''   
from msdb.dbo.log_shipping_monitor_primary prm INNER JOIN msdb.dbo.log_shipping_primary_secondaries sec  ON  prm.primary_database=sec.secondary_database
where prm.primary_database in ( ' + @PriDB + ' )')

Exec ( 'Select  ''exec master..sp_delete_log_shipping_primary_secondary '' + '''''''' + prm.Primary_Database + '''''', '''''' + sec.Secondary_Server + '''''', '''''' + sec.Secondary_database + ''''''''   
from msdb.dbo.log_shipping_monitor_primary prm INNER JOIN msdb.dbo.log_shipping_primary_secondaries sec  ON  prm.primary_database=sec.secondary_database
where prm.primary_database in ( ' + @PriDB + ' )')

Exec ( 'Select  ''exec master..sp_delete_log_shipping_primary_database '' + '''''''' + prm.primary_database +  ''''''''   
from msdb.dbo.log_shipping_monitor_primary prm INNER JOIN msdb.dbo.log_shipping_primary_secondaries sec  ON  prm.primary_database=sec.secondary_database
where prm.primary_database in ( ' + @PriDB + ' )')

Exec ( 'Select  ''exec master..sp_delete_log_shipping_secondary_primary '' + '''''''' + prm.primary_server + '''''', '''''' + prm.primary_database +  ''''''''   
from msdb.dbo.log_shipping_monitor_primary prm INNER JOIN msdb.dbo.log_shipping_primary_secondaries sec  ON  prm.primary_database=sec.secondary_database
where prm.primary_database in ( ' + @PriDB + ' )')

```

### <a name="restore-the-backups"></a>백업 복원

백업을 만든 순서대로 복원해야 합니다. 특정 트랜잭션 로그 백업을 복원하려면 먼저 커밋되지 않은 트랜잭션(즉, 을 사용하여)을 롤백하지 않고 다음 이전 백업을 복원해야  `WITH NORECOVERY` 합니다.
  
- 전체 데이터베이스 백업 및 마지막 차분 백업 - 이러한 백업(있는 경우)을 특정 트랜잭션 로그 백업 전에 복원합니다. 가장 최근의 전체 또는 차분 데이터베이스 백업을 만들기 전에 데이터베이스는 전체 복구 모델 또는 대량으로 기록된 복구 모델을 사용했습니다.
    
- 모든 트랜잭션 로그 백업 - 전체 데이터베이스 백업 또는 차분 백업(복원하는 경우)과 특정 트랜잭션 로그 백업 이전의 모든 트랜잭션 로그 백업을 복원합니다. 로그 백업은 로그 체인의 간격 없이 백업을 만든 순서대로 적용해야 합니다.
    
사이트가 렌더링될 수 있도록 보조 서버의 콘텐츠 데이터베이스를 복구하려면 복구 전에 모든 데이터베이스 연결을 제거합니다. 데이터베이스를 복원하려면 다음 SQL 실행합니다.
  
```
restore database WSS_Content with recovery

```

> [!IMPORTANT]
> T-SQL 명시적으로 사용하는 경우 모호성을 없애기 위해 모든 RESTORE 문에 **WITH NORECOVERY** 또는 **WITH RECOVERY를** 지정합니다. 스크립트를 작성하는 경우 매우 중요합니다. 전체 및 차분 백업을 복원한 후 트랜잭션 로그를 복원할 수 SQL Server Management Studio. 또한 로그 전달이 이미 중지되어 있으므로 콘텐츠 데이터베이스는 대기 상태이기 때문에 상태를 모든 액세스로 변경해야 합니다.
  
SQL Server Management Studio 데이터베이스를 마우스 오른쪽 단추로 **클릭하고** WSS_Content 복원을 클릭한 다음 트랜잭션 로그를 클릭합니다(전체 백업을 복원하지 않은 경우 사용할 수   >  없습니다).  자세한 내용은[Restore a Transaction Log Backup (SQL Server)을 참조하십시오.](/sql/relational-databases/backup-restore/restore-a-transaction-log-backup-sql-server)
  
### <a name="crawl-the-content-source"></a>콘텐츠 원본 크롤링

Search Service를 복원하려면 각 콘텐츠 원본에 대해 전체 크롤링을 시작해야 합니다. 검색 권장 사항과 같은 일부 분석 정보가 사내 팜에서 손실됩니다. 전체 크롤링을 시작하기 전에 **Windows PowerShell Cmdlet Restore-SPEnterpriseSearchServiceApplication을** 사용하여 로그를 발송하고 복제된 검색 **관리 <GUID>** 데이터베이스(를 지정합니다Search_Service__DB_. 이 cmdlet은 검색 구성, schema, 관리 속성, 규칙 및 원본을 제공하며 다른 구성 요소의 기본 집합을 만듭니다.
  
전체 크롤링을 시작하기 위해 다음 단계를 완료합니다.
  
1. SharePoint 2013 중앙 관리에서 **응용** 프로그램 관리 서비스 응용 프로그램 관리 서비스 응용 프로그램으로 이동한 다음 크롤링할 Search Service 응용 프로그램을  >    >  클릭합니다.
    
2. 검색 **관리 페이지에서** 콘텐츠 **원본을** 클릭하고 원하는 콘텐츠 원본을 가리 클릭하고 화살표를 클릭한 다음 전체 크롤링 시작 **을 클릭합니다.**
    
### <a name="recover-farm-services"></a>팜 서비스 복구

다음 표에서는 로그 전달 데이터베이스가 있는 서비스, 데이터베이스가 있지만 로그 전달을 사용하여 복원하지 않는 서비스 및 데이터베이스가 없는 서비스를 복구하는 방법을 보여줍니다.
  
> [!IMPORTANT]
> Azure 환경에 SharePoint 데이터베이스를 복원하면 Azure에 아직 설치하지 않은 SharePoint 서비스가 복구되지 않습니다. 
  
**표: 서비스 응용 프로그램 데이터베이스 참조**

|**로그 제공 데이터베이스에서 이러한 서비스 복원**|**이러한 서비스에는 데이터베이스가 있지만 데이터베이스를 복원하지 않고 이러한 서비스를 시작하는 것이 좋습니다.**|**이러한 서비스는 데이터베이스에 데이터를 저장하지 않습니다. 장애 조치(failover) 후 이러한 서비스 시작**|
|:-----|:-----|:-----|
| 기계 번역 서비스 <br/>  Managed Metadata Service <br/>  Secure Store Service <br/>  사용자 프로필. 프로필 및 공유 태그 지정 데이터베이스만 지원됩니다. 동기화 데이터베이스는 지원되지 않습니다.) <br/>  Microsoft SharePoint Foundation 가입 설정 서비스 <br/> | Usage and Health Data Collection <br/>  State Service <br/>  Word 자동화 <br/> | Excel Services <br/>  PerformancePoint Services <br/>  PowerPoint Conversion <br/>  Visio Graphics Service <br/>  작업 관리 <br/> |
   
다음 예제에서는 데이터베이스에서 Managed Metadata Service를 복원하는 방법을 보여줍니다.
  
이 경우 기존 데이터베이스 Managed_Metadata_DB 사용됩니다. 이 데이터베이스는 로그가 제공되지만 보조 팜에는 활성 서비스 응용 프로그램이 있으므로 서비스 응용 프로그램을 적용한 후에 연결해야 합니다.
  
먼저 를 사용하여 복원된 데이터베이스의 이름으로  `New-SPMetadataServiceApplication`  `DatabaseName` 스위치를 지정합니다.
  
다음으로 보조 서버에서 다음과 같이 새 Managed Metadata Service 응용 프로그램을 구성합니다.
  
- 이름: Managed Metadata Service
    
- 데이터베이스 서버: 선적된 트랜잭션 로그의 데이터베이스 이름
    
- 데이터베이스 이름: Managed_Metadata_DB
    
- 응용 프로그램 풀: SharePoint 서비스 응용 프로그램 
    
### <a name="manage-dns-records"></a>DNS 레코드 관리

DNS 레코드를 수동으로 만들어 해당 팜을 SharePoint 합니다.
  
프런트 엔드 웹 서버가 여러 대인 대부분의 경우 팜의 웹 프런트 엔드 서버로 요청을 분산하기 위해 Windows Server 2012 또는 하드웨어 부하 분산 기능의 네트워크 부하 분산 기능을 활용하는 것이 좋습니다. 또한 웹 프런트 엔드 서버 중 하나에 오류가 발생하면 네트워크 부하 분산을 통해 요청을 다른 서버로 분산하여 위험을 줄일 수도 있습니다. 
  
일반적으로 네트워크 부하 분산을 설정할 때 클러스터에 단일 IP 주소가 할당됩니다. 그런 다음 클러스터를 지점으로 하는 네트워크의 DNS 공급자에 DNS 호스트 레코드를 생성합니다. (이 프로젝트의 경우, Azure에 DNS 서버를 추가하여, 프레미스 데이터 센터 오류 시 복구를 위해 넣습니다.) 예를 들어 Active Directory의 DNS 관리자에서 부하가 균형이 조정된 클러스터의 IP 주소를 지점으로 하는 DNS 레코드(예: 를 만들  `https://sharepoint.contoso.com` 수 있습니다.
  
SharePoint 팜에 대한 외부 액세스의 경우 클라이언트가 인트라넷에서 사용하는 URL(예: )을 사용하여 외부 DNS 서버에 방화벽의 외부 IP 주소를 지정하는 호스트 레코드를 만들 수 `https://sharepoint.contoso.com` 있습니다. 이 예제를 사용하는 가장 좋은 방법은 분할된 DNS를 설정하여 내부 DNS 서버가 요청을 외부 DNS 서버로 라우팅하는 대신 SharePoint 팜 클러스터로 직접 라우팅할 수 있도록 하는 `contoso.com` 것입니다. 그런 다음 클라이언트가 찾고 있는 리소스를 찾게 외부 IP 주소를 사내 클러스터의 내부 IP 주소에 매핑할 수 있습니다.
  
여기서는 다음과 같은 몇 가지 재해 복구 시나리오가 실행될 수 있습니다.
  
 **예제 시나리오: SharePoint 팜의 하드웨어 오류로 인한 사내 프레미스 SharePoint 사용할 수 없습니다.** 이 경우 Azure SharePoint 팜에 대한 장애 조치(failover) 단계를 완료한 후 복구 SharePoint 팜의 웹 프런트 엔드 서버에서와 동일한 방식으로 네트워크 부하 분산을 구성할 수 있습니다. 그런 다음 내부 DNS 공급자의 호스트 레코드가 복구 팜의 클러스터 IP 주소를 지점으로 리디렉션할 수 있습니다. 클라이언트의 캐시된 DNS 레코드를 새로 고치고 복구 팜을 설정하기까지 다소 시간이 걸릴 수 있습니다.
  
 **예제 시나리오: 사내 데이터 센터가 완전히 손실됩니다.** 이 시나리오는 화재나 홍수와 같은 자연 재해로 인해 발생할 수 있습니다. 이 경우 엔터프라이즈의 경우 자체 디렉터리 서비스와 DNS가 있는 Azure 서브넷뿐만 아니라 다른 지역에서 호스트되는 보조 데이터 센터가 있을 수 있습니다. 이전 재해 시나리오에서와 동일하게 내부 및 외부 DNS 레코드가 Azure SharePoint 팜을 SharePoint 있습니다. 다시 DNS 레코드 전파에는 시간이 걸릴 수 있습니다.
  
호스트 이름으로 된 사이트 모음 아키텍처 및 [배포(SharePoint 2013)에서](/SharePoint/administration/host-named-site-collection-architecture-and-deployment)권장한 호스트 이름으로 된 사이트 모음을 사용하는 경우 SharePoint 팜의 동일한 웹 응용 프로그램에서 호스트되는 여러 사이트 모음과 고유한 DNS 이름(예: )이 있을 수 있습니다. `https://sales.contoso.com` `https://marketing.contoso.com` 이 경우 클러스터 IP 주소를 지점하는 각 사이트 모음에 대한 DNS 레코드를 만들 수 있습니다. 요청이 SharePoint 웹 프런트 엔드 서버에 도달하면 각 요청을 적절한 사이트 모음으로 라우팅하는 작업을 처리합니다.
  
## <a name="microsoft-proof-of-concept-environment"></a>Microsoft 개념 증명 환경

이 솔루션에 대한 개념 증명 환경을 설계하고 테스트했습니다. 테스트 환경의 디자인 목표는 고객 환경에서 찾을 수 있는 SharePoint 팜을 배포하고 복구하는 것입니다. 몇 가지 가정을 했지만 사용자 지정 없이 팜이 모든 바로 사용 기능을 제공하는 데 필요한 것으로 알고 있습니다. 토폴로지는 필드 및 제품 그룹의 모범 사례 지침을 사용하여 고가용성을 위해 디자인된 것입니다.
  
다음 표에서는 Hyper-V 테스트 환경에 대해 만들어 구성한 가상 컴퓨터의 구성에 대해 설명되어 있습니다.
  
**표: 사내 테스트용 가상 컴퓨터**

|**서버 이름**|**역할**|**구성**|
|:-----|:-----|:-----|
|DC1  <br/> |Active Directory가 있는 도메인 컨트롤러.  <br/> |프로세서 2개  <br/> 512MB에서 4GB RAM까지  <br/> 1 x 127GB 하드 디스크  <br/> |
|RRAS  <br/> |RRAS(라우팅 및 원격 액세스 서비스) 역할로 구성된 서버입니다.  <br/> |프로세서 2개  <br/> 2-8GB RAM  <br/> 1 x 127GB 하드 디스크  <br/> |
|FS1  <br/> |백업에 대한 공유가 있는 파일 서버 및 DFSR의 끝점입니다.  <br/> |프로세서 4개  <br/> 2-12GB RAM  <br/> 1 x 127GB 하드 디스크  <br/> SAN(하드 디스크 1개) 1개  <br/> 750GB 하드 디스크 1개  <br/> |
|SP-WFE1, SP-WFE2  <br/> |프런트 엔드 웹 서버.  <br/> |프로세서 4개  <br/> 16GB RAM  <br/> |
|SP-APP1, SP-APP2, SP-APP3  <br/> |응용 프로그램 서버.  <br/> |프로세서 4개  <br/> 2-16GB RAM  <br/> |
|SP-SQL-HA1, SP-SQL-HA2  <br/> |고가용성을 제공하기 위해 SQL Server 2012 AlwaysOn 가용성 그룹으로 구성된 데이터베이스 서버. 이 구성에서는 SP-SQL-HA1 및 SP-SQL-HA2를 기본 및 보조 복제본으로 사용했습니다.  <br/> |프로세서 4개  <br/> 2-16GB RAM  <br/> |
   
다음 표에서는 Hyper-V 테스트 환경의 프런트 엔드 웹 및 응용 프로그램 서버에 대해 만들어 구성한 Hyper-V 가상 컴퓨터의 드라이브 구성에 대해 설명하고 있습니다.
  
**표: 프런트 엔드 웹 및 응용 프로그램 서버에 대한 가상 컴퓨터 드라이브 요구 사항**

|**드라이브 문자**|**크기**|**디렉터리 이름**|**Path**|
|:-----|:-----|:-----|:-----|
|C  <br/> |80  <br/> |시스템 드라이브  <br/> |<DriveLetter>: \\ Program Files \\ Microsoft SQL Server\\  <br/> |
|E  <br/> |80  <br/> |로그 드라이브(40GB)  <br/> |<DriveLetter>: \\ Program Files Microsoft SQL Server \\ \\ MSSQL10_50.MSSQLSERVER \\ MSSQL \\ DATA  <br/> |
|F  <br/> |80  <br/> |페이지(36GB)  <br/> |<DriveLetter>: \\ \\ \\ MSSQL Microsoft SQL Server 프로그램 \\ 파일  <br/> |
   
다음 표에서는 Hyper-V 데이터베이스 서버 역할을 하도록 구성된 가상 컴퓨터의 드라이브 구성에 대해 설명하고 있습니다. 구성 **데이터베이스 엔진** 탭에 액세스하여 다음  표에 표시된 설정을 설정하고 확인합니다.
  
**표: 사내 테스트용 데이터베이스 서버에 대한 가상 컴퓨터 드라이브 요구 사항**

|**드라이브 문자**|**크기**|**디렉터리 이름**|**Path**|
|:-----|:-----|:-----|:-----|
|C  <br/> |80  <br/> |데이터 루트 디렉터리  <br/> |<DriveLetter>: \\ Program Files \\ Microsoft SQL Server\\  <br/> |
|E  <br/> |500  <br/> |사용자 데이터베이스 디렉터리  <br/> |<DriveLetter>: \\ Program Files Microsoft SQL Server \\ \\ MSSQL10_50.MSSQLSERVER \\ MSSQL \\ DATA  <br/> |
|F  <br/> |500  <br/> |사용자 데이터베이스 로그 디렉터리  <br/> |<DriveLetter>: \\ Program Files Microsoft SQL Server \\ \\ MSSQL10_50.MSSQLSERVER \\ MSSQL \\ DATA  <br/> |
|G  <br/> |500  <br/> |Temp DB 디렉터리  <br/> |<DriveLetter>: \\ Program Files Microsoft SQL Server \\ \\ MSSQL10_50.MSSQLSERVER \\ MSSQL \\ DATA  <br/> |
|H  <br/> |500  <br/> |Temp DB 로그 디렉터리  <br/> |<DriveLetter>: \\ Program Files Microsoft SQL Server \\ \\ MSSQL10_50.MSSQLSERVER \\ MSSQL \\ DATA  <br/> |
   
### <a name="setting-up-the-test-environment"></a>테스트 환경 설정

여러 배포 단계 동안 테스트 팀은 일반적으로 먼저 사내 아키텍처를 먼저 작업한 다음 해당 Azure 환경에서 작업했습니다. 이는 사 내 프로덕션 팜이 이미 실행되고 있는 일반적인 실제 사례를 반영합니다. 더욱 중요한 점은 현재 프로덕션 작업량, 용량 및 일반적인 성능을 알아야 한다는 것입니다. 비즈니스 요구 사항을 충족할 수 있는 재해 복구 모델을 구축하는 것 외에도 복구 팜 서버의 크기를 최소 수준의 서비스를 제공해야 합니다. 콜드 또는 웜 대기 환경에서 복구 팜은 일반적으로 프로덕션 팜보다 작습니다. 복구 팜이 안정화되고 프로덕션에서 작업 요구 사항을 충족하기 위해 팜을 수리 및 수리할 수 있습니다.
  
다음 세 단계에 테스트 환경을 배포했습니다.
  
- 하이브리드 인프라 설정
    
- 서버 프로비전
    
- 팜 SharePoint 배포
    
#### <a name="set-up-the-hybrid-infrastructure"></a>하이브리드 인프라 설정

이 단계에서는 Azure의 복구 팜 및 사내 팜에 대한 도메인 환경을 설정하는 과정이 진행되었습니다. 테스트 팀은 Active Directory 구성과 관련된 일반적인 작업 외에도 두 환경 간의 라우팅 솔루션 및 VPN 연결을 구현했습니다.
  
#### <a name="provision-the-servers"></a>서버 프로비전

팜 서버 외에도 도메인 컨트롤러용 서버를 프로비전하고 RRAS 및 사이트 대 사이트 VPN을 처리하도록 서버를 구성해야 합니다. DFSR 서비스에 대해 두 개의 파일 서버가 프로비전되었습니다. 테스터를 위해 여러 클라이언트 컴퓨터가 프로비전되었습니다.
  
#### <a name="deploy-the-sharepoint-farms"></a>팜 SharePoint 배포

SharePoint 팜은 환경 손떨림 보정 및 문제 해결을 간소화하기 위해 두 단계로 배포되었습니다(필요한 경우). 첫 번째 단계에서는 필요한 기능을 지원하기 위해 각 토폴로지의 각 계층에 대한 최소 서버 수에 각 팜을 배포했습니다.
  
2013 서버를 만들기 전에 SQL Server 데이터베이스 서버를 SharePoint 만들어야 합니다. 새 배포이기 때문에 새 배포를 배포하기 전에 가용성 그룹을 SharePoint. MCS 모범 사례 지침을 기반으로 3개의 그룹을 만들 수 있습니다. 
  
> [!NOTE]
> 설치하기 전에 가용성 그룹을 만들 수 있도록 자리 SharePoint 만듭니다. 자세한 내용은 [Configure SQL Server AlwaysOn Availability Groups for SharePoint 2013을 참조하십시오.](/SharePoint/administration/configure-an-alwayson-availability-group)
  
팜을 만들어 다음 순서로 추가 서버를 추가했습니다.
  
- SP-SQL-HA1 및 SP-SQL-HA2를 프로비전합니다.
    
- AlwaysOn을 구성하고 팜에 대해 세 가지 가용성 그룹을 만들 수 있습니다. 
    
- 중앙 관리 호스트를 위해 SP-APP1을 프로비전합니다.
    
- 배포된 캐시를 호스트하기 위해 SP-WFE1 및 SP-WFE2를 프로비전합니다. 
    
명령줄에서psconfig.exe _skipRegisterAsDistributedCachehost_ 매개  변수를 사용했습니다. 자세한 내용은 [Plan for feeds and the Distributed Cache service in SharePoint Server 2013을 참조하십시오.](/sharepoint/administration/plan-for-feeds-and-the-distributed-cache-service) 
  
복구 환경에서 다음 단계를 반복했습니다.
  
- AZ-SQL-HA1 및 AZ-SQL-HA2를 프로비전합니다.
    
- AlwaysOn을 구성하고 팜에 대해 세 가지 가용성 그룹을 만들 수 있습니다.
    
- 중앙 관리 호스트를 위해 AZ-APP1을 프로비전합니다.
    
- 배포된 캐시를 호스트하기 위해 AZ-WFE1 및 AZ-WFE2를 프로비전합니다.
    
배포된 캐시를 구성하고 테스트 사용자를 추가하고 테스트 콘텐츠를 추가한 후 배포의 2단계를 시작했습니다. 이 경우 계층을 확장하고 팜 아키텍처에 설명된 고가용성 토폴로지 지원을 위해 팜 서버를 구성해야 합니다.
  
다음 표에서는 복구 팜에 대해 설정한 가상 컴퓨터, 서브넷 및 가용성 집합에 대해 설명하고 있습니다.
  
**표: 복구 팜 인프라**

|**서버 이름**|**역할**|**구성**|**서브넷**|**가용성 집합**|
|:-----|:-----|:-----|:-----|:-----|
|spDRAD  <br/> |Active Directory가 있는 도메인 컨트롤러  <br/> |프로세서 2개  <br/> 512MB에서 4GB RAM까지  <br/> 1 x 127GB 하드 디스크  <br/> |sp-ADservers  <br/> ||
|AZ-SP-FS  <br/> |백업을 위한 공유가 있는 파일 서버 및 DFSR의 끝점  <br/> | A5 구성: <br/>  프로세서 2개 <br/>  14GB RAM <br/>  1 x 127GB 하드 디스크 <br/>  1 x 135GB 하드 디스크 <br/>  1 x 127GB 하드 디스크 <br/>  1 x 150GB 하드 디스크 <br/> |sp-databaseservers  <br/> |DATA_SET  <br/> |
|AZ-WFE1, AZ -WFE2  <br/> |프런트 엔드 웹 서버  <br/> | A5 구성: <br/>  프로세서 2개 <br/>  14GB RAM <br/>  1 x 127GB 하드 디스크 <br/> |sp-webservers  <br/> |WFE_SET  <br/> |
|AZ -APP1, AZ -APP2, AZ -APP3  <br/> |응용 프로그램 서버  <br/> | A5 구성: <br/>  프로세서 2개 <br/>  14GB RAM <br/>  1 x 127GB 하드 디스크 <br/> |sp-applicationservers  <br/> |APP_SET  <br/> |
|AZ -SQL-HA1, AZ -SQL-HA2  <br/> |AlwaysOn 가용성 그룹에 대한 데이터베이스 서버 및 기본 및 보조 복제본  <br/> | A5 구성: <br/>  프로세서 2개 <br/>  14GB RAM <br/> |sp-databaseservers  <br/> |DATA_SET  <br/> |
   
### <a name="operations"></a>작업

테스트 팀은 팜 환경을 안정화하고 기능 테스트를 완료한 후, 다음과 같은 작업 작업을 시작하여 사내 복구 환경을 구성하는 데 필요한 작업을 시작했습니다.
  
- 전체 및 차차 백업을 구성합니다.
    
- 사내 환경과 Azure 환경 간에 트랜잭션 로그를 전송하는 파일 서버에서 DFSR을 구성합니다.
    
- 기본 데이터베이스 서버에서 로그 전달을 구성합니다.
    
- 필요한 경우 로그 전달을 안정화, 유효성 검사 및 문제 해결합니다. 여기에는 로그 전달 또는 DFSR 파일 동기화 오류가 발생할 수 있는 네트워크 대기 시간과 같은 문제를 일으킬 수 있는 동작을 식별하고 문서화하는 작업도 포함됩니다.
    
### <a name="databases"></a>데이터베이스

장애 조치(failover) 테스트에는 다음과 같은 데이터베이스가 포함되었습니다. 
  
- WSS_Content
    
- ManagedMetadata
    
- 프로필 DB
    
- 동기화 DB
    
- Social DB
    
- 콘텐츠 형식 허브(전용 콘텐츠 형식 Syndication 허브용 데이터베이스)
    
## <a name="troubleshooting-tips"></a>문제 해결 팁

이 섹션에서는 테스트 중에 발생하는 문제 및 해결 방법 설명을 제공합니다. 
  
### <a name="using-the-term-store-management-tool-caused-the-error-the-managed-metadata-store-or-connection-is-currently-not-available"></a>용어 저장소 관리 도구를 사용하면 "관리되는 메타데이터 저장소 또는 연결을 현재 사용할 수 없습니다."라는 오류가 발생했습니다.

웹 응용 프로그램에서 사용하는 응용 프로그램 풀 계정에 용어 저장소에 대한 읽기 권한이 있는지 확인
  
### <a name="custom-term-sets-are-not-available-in-the-site-collection"></a>사이트 모음에서 사용자 지정 용어 집합을 사용할 수 없습니다.

콘텐츠 사이트 모음과 콘텐츠 형식 허브 간에 누락된 서비스 응용 프로그램 연결 확인 또한 **관리되는 <site collection name>** 메타데이터 - 연결 속성 화면에서 이 서비스 응용 프로그램이 열 특정 용어 집합의 기본 저장소 위치인 이 옵션을 사용하도록 설정되어 있는지 **확인합니다.**
  
### <a name="the-get-adforest-windows-powershell-command-generates-the-error-the-term-get-adforest-is-not-recognized-as-the-name-of-a-cmdlet-function-script-file-or-operable-program"></a>Get-ADForest Windows PowerShell 명령은 "'Get-ADForest' 용어가 cmdlet, 함수, 스크립트 파일 또는 작동할 수 있는 프로그램의 이름으로 인식되지 않습니다."라는 오류가 발생합니다.

사용자 프로필을 설정할 때 Active Directory 포리스트 이름이 필요합니다. 역할 및 기능 추가 마법사에서 Ad DS 및 **AD LDS** 도구 섹션에서 원격 서버 관리 도구>역할 관리 도구 섹션에서 Windows PowerShell>Active Directory 모듈을 사용하도록 설정해야 합니다. 또한 **Get-ADForest를** 사용하기 전에 다음 명령을 실행하여 소프트웨어 종속성 로드를 보장합니다.
  
```
Import-module servermanager
Import-module activedirectory

```

### <a name="availability-group-creation-fails-at-starting-the-alwayson_health-xevent-session-on-server-name"></a>'에서 'AlwaysOn_health' XEvent 세션 시작 시 가용성 그룹 만들기가 <server name> 실패합니다.

장애 조치(failover) 클러스터의 두 노드가 모두 "일시 중지됨" 또는 "중지됨" 상태가 아닌 "위"에 있도록 합니다. 
  
### <a name="sql-server-log-shipping-job-fails-with-access-denied-error-trying-to-connect-to-the-file-share"></a>SQL Server 공유에 연결하려고 하는 액세스 거부 오류로 로그 전달 작업이 실패했습니다.

기본 자격 SQL Server 대신 네트워크 자격 증명으로 에이전트가 실행되고 있는지 확인합니다.
  
### <a name="sql-server-log-shipping-job-indicates-success-but-no-files-are-copied"></a>SQL Server 로그 전달 작업이 성공을 나타내지만 파일이 복사되는 것은 없습니다.

이 문제는 가용성 그룹의 기본 백업 기본 설정이 보조 **선호이기 때문에 발생합니다.** 기본 서버가 아닌 가용성 그룹의 보조 서버에서 로그 전달 작업을 실행해야 합니다. 그렇지 않으면 작업이 자동으로 실패합니다. 
  
### <a name="managed-metadata-service-or-other-sharepoint-service-fails-to-start-automatically-after-installation"></a>Managed Metadata Service(또는 기타 SharePoint 서비스)가 설치 후 자동으로 시작되지 않습니다.

서버의 성능 및 현재 부하에 따라 서비스를 시작하는 데 몇 분 정도 걸릴 SharePoint 있습니다. 서비스에 **대한 시작을** 수동으로 클릭하고 때때로 서버 제공 서비스 화면을 새로 고쳐 상태를 모니터링하는 동안 적절한 시작 시간을 제공합니다. 서비스가 중지된 상태로 유지되는 SharePoint 진단 로깅을 사용하도록 설정하고 서비스를 다시 시작한 다음 로그에서 오류를 확인 합니다. 자세한 내용은 [Configure diagnostic logging in SharePoint 2013을 참조하십시오.](/sharepoint/administration/configure-diagnostic-logging)
  
### <a name="after-changing-dns-to-the-azure-failover-environment-client-browsers-continue-to-use-the-old-ip-address-for-the-sharepoint-site"></a>DNS를 Azure 장애 조치(failover) 환경으로 변경한 후 클라이언트 브라우저는 해당 사이트의 이전 IP SharePoint 사용합니다.

일부 클라이언트에는 DNS 변경이 즉시 표시되지 않을 수 있습니다. 테스트 클라이언트에서 상승된 명령 프롬프트에서 다음 명령을 수행하고 사이트에 다시 액세스를 시도합니다.
  
```
Ipconfig /flushdns
```

## <a name="additional-resources"></a>추가 리소스

[SharePoint 데이터베이스에 대해 지원되는 고가용성 및 재해 복구 옵션](/sharepoint/administration/supported-high-availability-and-disaster-recovery-options-for-sharepoint-databas)
  
[2013에 SQL Server 2012 AlwaysOn 가용성 SharePoint 구성](/SharePoint/administration/configure-an-alwayson-availability-group)
  
## <a name="see-also"></a>참고 항목

[Microsoft 365 솔루션 및 아키텍처 센터](../solutions/index.yml)