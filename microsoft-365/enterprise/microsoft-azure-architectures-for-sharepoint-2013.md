---
title: SharePoint 2013용 Microsoft Azure 아키텍처
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Architecture
- seo-marvel-apr2020
ms.assetid: 98fc1006-9399-4ff0-a216-c7c05820d822
description: SharePoint 가상 SharePoint 호스트할 수 있는 Microsoft Azure 솔루션 유형과 호스트할 Azure를 설정하는 방법을 설명합니다.
ms.openlocfilehash: 8bbaeb7a20b467625d57800cdf95f42e5b11f434
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60168557"
---
# <a name="microsoft-azure-architectures-for-sharepoint-2013"></a>SharePoint 2013용 Microsoft Azure 아키텍처

Azure는 SharePoint Server 2013 솔루션을 호스팅하기에 좋은 환경입니다. 대부분의 경우 권장되는 Microsoft 365 Azure에서 호스팅되는 SharePoint 서버 팜은 특정 솔루션에 대한 좋은 옵션일 수 있습니다. 이 문서에서는 Azure 플랫폼에 적합한 SharePoint 솔루션을 설계하는 방법을 설명합니다. 예를 들어 다음과 같은 두 가지 특정 솔루션이 사용됩니다.
  
- [Microsoft Azure에서 SharePoint Server 2013 재해 복구](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md)
    
- [SharePoint Server 2013을 사용하는 Microsoft Azure의 인터넷 사이트](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md)
    
## <a name="recommended-sharepoint-solutions-for-azure-infrastructure-services"></a>Azure 인프라 SharePoint 권장 솔루션

Azure 인프라 서비스는 클라우드 솔루션을 호스팅하기 위한 SharePoint 옵션입니다. 일부 솔루션은 다른 솔루션보다 이 플랫폼에 더 잘 맞습니다. 다음 표에서는 권장 해결법을 보여줍니다.
  
|**솔루션**|**Azure에 이 솔루션이 권장되는 이유**|
|:-----|:-----|
|개발 및 테스트 환경  <br/> |이러한 환경은 쉽게 만들고 관리할 수 있습니다.  <br/> |
|Azure로의 SharePoint 팜의 재해 복구  <br/> |**호스팅된 보조 데이터 센터** 다른 지역의 보조 데이터 센터에 투자하는 대신 Azure를 사용합니다. <br/> **낮은 비용의 재해 복구 환경** 프레미스 재해 복구 환경보다 적은 수의 리소스를 유지 관리하고 비용을 지불합니다. 리소스 수는 콜드 대기, 웜 대기 또는 핫 대기 중 선택하는 재해 복구 환경에 따라 다를 수 있습니다. <br/> **보다 탄력적인 플랫폼** 재해가 발생하면 팜에서 복구를 SharePoint 요구 사항을 충족할 수 있습니다. 리소스가 더 이상 필요하지 않습니다. <br/> 에서 [SharePoint Server 2013 재해 복구를 Microsoft Azure.](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md)  <br/> |
|기능 및 규모를 사용하는 인터넷 연결 사이트는 사이트에서 사용할 수 Microsoft 365  <br/> |**노력에 집중** 인프라를 구축하는 대신 멋진 사이트를 구축하는 데 집중합니다. <br/> **Azure에서 탄력성 활용** 새 서버를 추가하여 수요에 따라 팜의 크기를 설정하고 필요한 리소스만 지불합니다. 동적 컴퓨터 할당은 지원되지 않습니다(자동 크기 조정). <br/> **AD Azure Active Directory 사용** 고객 계정에 대해 Azure AD를 활용합니다. <br/> **다른 SharePoint 사용할** 수 없는 추가 Microsoft 365 심층 보고 및 웹 분석을 추가합니다. <br/> Microsoft Azure Server [2013을 SharePoint 인터넷 사이트를 참조합니다.](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md)  <br/> |
|앱 또는 Microsoft 365 환경을 지원하기 위한 앱 팜  <br/> |**Azure에서** 앱을 빌드, 테스트 및 호스트하여 사내 환경과 클라우드 환경을 모두 지원합니다. <br/> **Azure에서** 이 역할을 호스트하는 대신, 사내 환경의 새 하드웨어를 구입하세요. <br/> |
   
인트라넷 및 공동 작업 솔루션 및 워크로드의 경우 다음 옵션을 고려하세요.
  
- 비즈니스 Microsoft 365 충족하는지 아니면 솔루션의 일부가 될 수 있는지 확인합니다. Microsoft 365 항상 최신으로 유지되는 다양한 기능 집합을 사용할 수 있습니다.
    
- 모든 Microsoft 365 충족하지 않는 경우 MCS(Microsoft Consulting Services)에서 SharePoint 2013의 표준 구현을 고려하세요. 표준 아키텍처는 사용자 지정된 아키텍처보다 더 빠르고 저렴한 솔루션이 될 수 있습니다. 
    
- 표준 구현이 비즈니스 요구 사항을 충족하지 않는 경우 사용자 지정된 사내 솔루션을 고려하세요.
    
- 비즈니스 요구 사항에 클라우드 플랫폼을 사용하는 것이 중요한 경우 Azure 인프라 서비스에서 호스팅되는 SharePoint 2013의 표준 또는 사용자 지정 구현을 고려하세요. SharePoint 솔루션은 다른 기본이 아닌 Microsoft 공용 클라우드 플랫폼보다 Azure에서 훨씬 더 쉽게 지원할 수 있습니다.
    
## <a name="before-you-design-the-azure-environment"></a>Azure 환경을 디자인하기 전에

이 문서에서는 예제 SharePoint 토폴로지의 경우 이러한 디자인 개념을 모든 팜 토폴로지에서 사용할 SharePoint 있습니다. Azure 환경을 디자인하기 전에 다음 토폴로지, 아키텍처, 용량 및 성능 지침을 사용하여 SharePoint 팜을 디자인합니다.
  
- [2013 IT SharePoint 아키텍처 디자인](/SharePoint/technical-reference/technical-diagrams)
    
- [SharePoint Server 2013에서 성능 및 용량 관리 계획](/SharePoint/administration/performance-planning-in-sharepoint-server-2013)
    
## <a name="determine-the-active-directory-domain-type"></a>Active Directory 도메인 유형 확인

각 SharePoint 서버 팜은 Active Directory를 통해 팜 설정에 대한 관리 계정을 제공합니다. 현재 Azure의 여러 솔루션에 SharePoint 옵션이 있습니다. 이러한 내용은 다음 표에 설명되어 있습니다.
  
|**옵션**|**설명**|
|:-----|:-----|
|전용 도메인  <br/> |Azure에 격리된 전용 Active Directory 도메인을 배포하여 사용자 팜을 SharePoint 있습니다. 공용 인터넷 사이트에는 이 선택이 좋습니다.  <br/> |
|크로스-프레미스 연결을 통해 사내 도메인 확장  <br/> |크로스-프레미스 연결을 통해 사내 도메인을 확장하면 사용자는 인트라넷을 통해 호스트된 SharePoint 팜에 액세스합니다. 프레미스 Active Directory 및 DNS 구현을 활용할 수 있습니다.  <br/> Azure에서 재해 복구 환경을 구축하려면 프레미스 간 연결이 필요합니다.  <br/> |
   
이 문서에는 크로스-프레미스 연결을 통해 사내 도메인을 확장하기 위한 디자인 개념이 포함되어 있습니다. 솔루션에서 전용 도메인을 사용하는 경우 프레미스 간 연결이 필요하지 않습니다.
  
## <a name="design-the-virtual-network"></a>가상 네트워크 디자인

먼저 Azure에 가상 컴퓨터를 두는 서브넷이 포함된 가상 네트워크가 필요합니다. 가상 네트워크에는 서브넷에 할당하는 개인 IP 주소 공간이 필요합니다.
  
크로스-프레미스 연결을 통해 Azure로 사내 네트워크를 확장하는 경우(재해 복구 환경에 필요) 조직 네트워크의 다른 곳에서 아직 사용되지 않는 개인 주소 공간을 선택해야 합니다. 여기에는 사내 환경 및 기타 Azure Virtual Network가 포함됩니다. 
  
**그림 1: Azure의 가상 네트워크가 있는 사내 환경**

![Microsoft Azure 솔루션에 대한 가상 네트워크 SharePoint 있습니다. Azure 게이트웨이용 서브넷 1개 가상 컴퓨터용 서브넷 1개](../media/OPrrasconWA-AZarch.png)
  
다음은 이 다이어그램에 대한 설명입니다.
  
- Azure의 가상 네트워크는 사내 환경과 나란히 설명되어 있습니다. 두 환경은 사이트 간 VPN 연결 또는 ExpressRoute일 수 있는 프레미스 간 연결로 아직 연결되지 않습니다.
    
- 이때 가상 네트워크는 서브넷만 포함하며 다른 아키텍처 요소는 포함하지 않습니다. 하나의 서브넷은 Azure 게이트웨이를 호스트하고 다른 서브넷은 SharePoint 팜의 계층을 호스트하고 Active Directory 및 DNS에 대한 추가 서브넷을 호스트합니다.
    
## <a name="add-cross-premises-connectivity"></a>크로스-프레미스 연결 추가

다음 배포 단계는 프레미스 간 연결을 만드는 것입니다(솔루션에 적용되는 경우). 크로스-프레미스 연결의 경우 Azure 게이트웨이는 별도의 게이트웨이 서브넷에 있으며 주소 공간을 만들고 할당해야 합니다. 
  
크로스-프레미스 연결을 계획할 때 Azure 게이트웨이 및 연결은 정의하고 만들 수 있습니다.
  
**그림 2: Azure 게이트웨이 및 사내 게이트웨이 장치를 사용하여 사내 환경과 Azure 간에 사이트 간 연결을 제공합니다.**

![사이트 간 VPN 연결 또는 ExpressRoute일 수 있는 프레미스 간 연결을 통해 Azure Virtual Network에 연결된 사내 환경](../media/AZarch-VPNgtwyconnct.png)
  
다음은 이 다이어그램에 대한 설명입니다.
  
- 이전 다이어그램에 추가하면, 사이트 간 VPN 연결 또는 ExpressRoute일 수 있는 프레미스 간 연결을 통해 Azure Virtual Network에 연결됩니다.
    
- Azure 게이트웨이가 게이트웨이 서브넷에 있습니다.
    
- 사내 환경에는 라우터 또는 VPN 서버와 같은 게이트웨이 장치가 포함됩니다.
    
프레미스 간 가상 네트워크를 계획하고 만드는 자세한 내용은 커넥트 가상 네트워크에 대한 Microsoft Azure [참조하세요.](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md)
  
## <a name="add-active-directory-domain-services-ad-ds-and-dns"></a>AD DS(Active Directory 도메인 서비스) 및 DNS 추가

Azure의 재해 복구를 위해 Windows Server AD 및 DNS를 배포하는 하이브리드 시나리오에서는 Windows Server AD 및 Azure Virtual Machines 둘 다에 배포합니다.
  
**그림 3: 하이브리드 Active Directory 도메인 구성**

![Azure Virtual Network에 배포된 STwo 가상 컴퓨터와 SharePoint 팜 서브넷은 복제본 도메인 컨트롤러 및 DNS 서버입니다.](../media/AZarch-HyADdomainConfig.png)
  
이 다이어그램은 가상 컴퓨터와 DNS 서브넷에 두 개의 가상 컴퓨터를 Windows Server AD 다이어그램을 토대합니다. 이러한 가상 컴퓨터는 복제본 도메인 컨트롤러 및 DNS 서버입니다. 이러한 확장은 프레미스 환경의 Windows Server AD 확장입니다. 
  
다음 표에서는 Azure의 이러한 가상 머신에 대한 구성 권장 사항을 제공합니다. Azure 환경이 프레미스 환경과 통신하지 않는 전용 도메인의 경우에도 사용자 환경을 디자인하기 위한 시작점으로 사용할 수 있습니다.
  
|**항목**|**구성**|
|:-----|:-----|
|Azure의 가상 컴퓨터 크기  <br/> |표준 계층의 A1 또는 A2 크기  <br/> |
|운영 체제  <br/> |Windows Server 2012 R2  <br/> |
|Active Directory 역할  <br/> |글로벌 카탈로그 서버로 지정된 AD DS 도메인 컨트롤러입니다. 이 구성을 통해 크로스-프레미스 연결을 통해 트래픽을 내보내게 됩니다.  <br/> 변경률이 높은 다중 도메인 환경에서(일반적이지 않은 경우) 복제 트래픽을 줄이기 위해 Azure의 글로벌 카탈로그 서버와 동기화되지 않는 도메인 컨트롤러를 구성합니다.  <br/> |
|DNS 역할  <br/> |도메인 컨트롤러에 DNS Server 서비스를 설치하고 구성합니다.  <br/> |
|데이터 디스크  <br/> |Active Directory 데이터베이스, 로그 및 SYSVOL을 추가 Azure 데이터 디스크에 저장합니다. 이러한 디스크는 운영 체제 디스크 또는 Azure에서 제공하는 임시 디스크에 두지 않습니다.  <br/> |
|IP 주소  <br/> |고정 IP 주소를 사용하여 도메인 컨트롤러가 구성된 후 가상 네트워크의 가상 머신에 이러한 주소를 할당하도록 가상 네트워크를 구성합니다.  <br/> |
   
> [!IMPORTANT]
> Azure에서 Active Directory를 배포하기 전에 Azure 가상 머신에 Windows Server Active Directory [지침을 읽어야 합니다.](/windows-server/identity/ad-ds/introduction-to-active-directory-domain-services-ad-ds-virtualization-level-100) 이러한 설정은 솔루션에 다른 아키텍처 또는 다른 구성 설정이 필요한지 여부를 결정하는 데 도움이 됩니다. 
  
## <a name="add-the-sharepoint-farm"></a>팜 SharePoint 추가

적절한 서브넷의 SharePoint 팜의 가상 컴퓨터를 계층에 두습니다.
  
**그림 4: 가상 SharePoint 배치**

![데이터베이스 서버 및 SharePoint 팜 서브넷 내의 Azure Virtual Network에 추가된 SharePoint 서버 역할입니다.](../media/AZarch-SPVMsinCloudSer.png)
  
이 다이어그램은 각 계층에 SharePoint 팜 서버 역할을 추가하여 이전 다이어그램을 작성합니다.
  
- 실행 중인 두 데이터베이스 가상 SQL Server 계층을 만듭니다.
    
- 프런트 엔드 서버SharePoint 분산 캐시 서버 및 백 엔드 서버 등 각 계층에 대해 SharePoint Server 2013을 실행하는 가상 컴퓨터 2대.
    
## <a name="design-and-fine-tune-server-roles-for-availability-sets-and-fault-domains"></a>가용성 집합 및 장애 도메인에 대한 서버 역할 디자인 및 미세 조정

장애 도메인은 역할 인스턴스가 실행되는 하드웨어 그룹입니다. Azure 인프라에서 동일한 장애 도메인 내의 가상 컴퓨터를 동시에 업데이트할 수 있습니다. 또는 동일한 랙을 공유하기 때문에 동시에 실패할 수 있습니다. 동일한 장애 도메인에 두 개의 가상 컴퓨터를 사용할 위험이 없는 경우 가상 컴퓨터를 가용성 집합으로 구성하여 각 가상 컴퓨터의 장애 도메인이 서로 다른 도메인에 있도록 할 수 있습니다. 세 개의 가상 컴퓨터를 가용성 집합으로 구성하는 경우 Azure는 두 개 이상의 가상 컴퓨터를 동일한 장애 도메인에 두 개 이상 위치하지 않습니다.
  
SharePoint 팜에 대해 Azure 아키텍처를 디자인할 때 가용성 집합의 일부로 동일한 서버 역할을 구성합니다. 이렇게 하면 가상 컴퓨터를 여러 장애 도메인에 분산할 수 있습니다.
  
**그림 5: Azure 가용성 집합을 사용하여 SharePoint 팜 계층에 대한 고가용성 제공**

![2013 솔루션에 대한 Azure 인프라의 가용성 SharePoint 구성합니다.](../media/AZenv-WinAzureAvailSetsHA.png)
  
이 다이어그램에서는 Azure 인프라 내에서 가용성 집합의 구성을 호출합니다. 다음 각 역할은 별도의 가용성 집합을 공유합니다.
  
- Active Directory 및 DNS
    
- Database
    
- 백 엔드
    
- 캐시 배포
    
- 프런트 엔드
    
Azure SharePoint 팜을 세부적으로 조정해야 할 수 있습니다. 모든 구성 요소의 고가용성을 보장하기 위해 서버 역할이 모두 동일하게 구성되어 있는지 확인합니다.
  
다음은 특정 용량 및 성능 목표를 충족하는 표준 인터넷 사이트 아키텍처를 보여 주는 예제입니다. 이 예제는 SharePoint [Server 2013용 인터넷 사이트 검색 아키텍처](https://go.microsoft.com/fwlink/p/?LinkId=261519)아키텍처의 아키텍처 모델에 설명되어 있습니다.
  
**그림 6: 3계층 팜의 용량 및 성능 목표 계획 예제**

![표준 SharePoint 및 성능 목표를 충족하는 구성 요소 할당이 있는 2013 인터넷 사이트 아키텍처](../media/AZarch-CapPerfexmpArch.png)
  
다음은 이 다이어그램에 대한 설명입니다.
  
- 3계층 팜은 웹 서버, 응용 프로그램 서버 및 데이터베이스 서버로 표현됩니다.
    
- 세 개의 웹 서버는 여러 구성 요소와 동일하게 구성됩니다.
    
- 두 데이터베이스 서버는 동일하게 구성됩니다.
    
- 세 응용 프로그램 서버는 동일하게 구성되지 않습니다. 이러한 서버 역할은 Azure의 가용성 집합에 대해 미세 조정이 필요합니다.
    
응용 프로그램 서버 계층에 대해 자세히 살펴보급시다.
  
**그림 7: 미세 조정 전 응용 프로그램 서버 계층**

![예를 SharePoint 가용성 집합에 대해 조정하기 전에 Server 2013 응용 프로그램 Microsoft Azure 예제입니다.](../media/AZarch-AppServtierBefore.png)
  
다음은 이 다이어그램에 대한 설명입니다.
  
- 응용 프로그램 계층에는 세 개의 서버가 포함됩니다.
    
- 첫 번째 서버에는 4개의 구성 요소가 포함됩니다.
    
- 두 번째 서버에는 세 가지 구성 요소가 포함됩니다.
    
- 세 번째 서버에는 두 개의 구성 요소가 포함되어 있습니다.
    
팜의 성능 및 용량 목표에 따라 구성 요소 수를 결정해야 합니다. Azure에 맞게 이 아키텍처를 조정하기 위해 4개의 구성 요소를 세 서버에 모두 복제합니다. 이렇게 하면 성능 및 용량에 필요한 구성 요소 수가 늘어납니다. 이 디자인은 이러한 세 개의 가상 컴퓨터를 가용성 집합에 할당할 때 Azure 플랫폼의 네 가지 구성 요소를 모두 고가용성으로 보장하는 것입니다.
  
**그림 8: 미세 조정 후 응용 프로그램 서버 계층**

![예제 SharePoint 가용성 집합에 대해 조정한 후 Server 2013 응용 프로그램 Microsoft Azure 예제입니다.](../media/AZarch-AppServtierAfter.png)
  
이 다이어그램은 동일한 4개의 구성 요소로 동일하게 구성된 3개의 응용 프로그램 서버를 모두 보여줍니다.
  
가용성 집합을 SharePoint 팜의 계층에 추가하면 구현이 완료됩니다.
  
**그림 9: Azure 인프라 SharePoint 완료된 팜**

![예제 SharePoint, 크로스-프레미스 연결, 서브넷, VM 및 가용성 집합이 있는 Azure 인프라 서비스의 2013 팜을 예로 들 수 있습니다.](../media/7256292f-bf11-485b-8917-41ba206153ee.png)
  
이 다이어그램은 Azure 인프라 서비스에서 SharePoint 팜을 보여 주며, 가용성 집합을 통해 각 계층의 서버에 장애 도메인을 제공합니다.
  
## <a name="see-also"></a>참고 항목

[Microsoft 365 솔루션 및 아키텍처 센터](../solutions/index.yml)
  
[SharePoint Server 2013을 사용하는 Microsoft Azure의 인터넷 사이트](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md)
  
[Microsoft Azure에서 SharePoint Server 2013 재해 복구](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md)