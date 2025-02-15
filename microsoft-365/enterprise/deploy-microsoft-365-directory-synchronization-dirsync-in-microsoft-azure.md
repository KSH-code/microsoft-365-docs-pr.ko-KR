---
title: Microsoft 365 디렉터리 동기화 배포 Microsoft Azure
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 11/05/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: b8464818-4325-4a56-b022-5af1dad2aa8b
description: Azure의 가상 머신에 Azure AD 커넥트 배포하여 계정과 Azure AD 테넌트 간에 계정을 동기화하는 방법을 설명합니다.
ms.openlocfilehash: 6535b46fb360cf326d8daf07662cb7fa366ae6c2
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60178818"
---
# <a name="deploy-microsoft-365-directory-synchronization-in-microsoft-azure"></a>Microsoft 365 디렉터리 동기화 배포 Microsoft Azure

Azure Active Directory(Azure AD) 커넥트(이전의 디렉터리 동기화 도구, 디렉터리 동기화 도구 또는 DirSync.exe 도구)는 도메인 가입 서버에 설치하여 사용자의 AD DS(Active Directory 도메인 서비스) 사용자를 Microsoft 365 구독의 Azure AD 테넌트와 동기화하는 응용 프로그램입니다. Microsoft 365 디렉터리 서비스에 대해 Azure AD를 사용하는지 확인합니다. 사용자 Microsoft 365 Azure AD 테넌트가 포함됩니다. 이 테넌트는 Azure의 다른 SaaS 응용 프로그램 및 앱을 포함하여 다른 클라우드 워크로드에서 조직의 ID를 관리하기 위해 사용할 수도 있습니다.

온-프레미스 서버에 Azure AD Connect를 설치할 수 있으며, 다음과 같은 이유로 Azure의 가상 머신에 설치할 수도 있습니다.
  
- 클라우드 기반 서비스를 더 빠르게 프로비저닝하고 구성하여 사용자가 서비스를 더 빠르게 사용하도록 할 수 있습니다.
- Azure에서는 더 적은 노력으로 더 나은 사이트 가용성을 제공합니다.
- 조직의 온-프레미스 서버 수를 줄일 수 있습니다.

이 솔루션을 사용하려면 온-프레미스 네트워크와 Azure Virtual Network가 연결되어 있어야 합니다. 자세한 내용은 [온-프레미스 네트워크를 Microsoft Azure Virtual Network에 연결](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md)을 참조하세요. 
  
> [!NOTE]
> 이 문서에서는 단일 포리스트에서 단일 도메인의 동기화에 대해 설명합니다. Azure AD 커넥트 Active Directory 포리스트의 모든 AD DS 도메인을 Microsoft 365. 단일 포리스트와 동기화할 Active Directory 포리스트가 여러 개 있는 Microsoft 365 단일 포리스트 디렉터리 동기화를 Sign-On [시나리오를 참조합니다.](/azure/active-directory/hybrid/whatis-hybrid-identity) 
  
## <a name="overview-of-deploying-microsoft-365-directory-synchronization-in-azure"></a>Azure에서 Microsoft 365 디렉터리 동기화 배포 개요

다음 다이어그램은 커넥트 AD DS 포리스트를 Microsoft 365 Azure의 가상 컴퓨터(디렉터리 동기화 서버)에서 실행되는 Azure AD Microsoft 365 보여줍니다.
  
![트래픽 흐름을 커넥트 Azure의 가상 머신에 있는 Azure AD Microsoft 365 계정의 Azure AD 테넌트와 동기화합니다.](../media/CP-DirSyncOverview.png)
  
다이어그램에는 사이트 간 VPN 또는 ExpressRoute 연결로 연결되는 2개의 네트워크가 있습니다. AD DS 도메인 컨트롤러가 있는 온-프레미스 네트워크가 있고, [Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594)가 실행되는 가상 머신에 해당하는 디렉터리 동기화 서버를 포함하는 Azure Virtual Network가 있습니다. 디렉터리 동기화 서버에서 시작하는 다음과 같은 두 가지 주요 트래픽 흐름이 있습니다.
  
-  Azure AD Connect는 온-프레미스 네트워크의 도메인 컨트롤러에서 계정 및 암호 변경 내용을 쿼리합니다.
-  Azure AD 커넥트 계정 및 암호에 대한 변경 내용을 구독의 Azure AD Microsoft 365 전송합니다. 디렉터리 동기화 서버가 사내 네트워크의 확장된 부분에 있기 때문에 이러한 변경 내용은 사내 네트워크의 프록시 서버를 통해 전송됩니다.
    
> [!NOTE]
> 이 솔루션은 단일 Active Directory 포리스트에서 단일 Active Directory 도메인의 동기화에 대해 설명합니다. Azure AD 커넥트 Active Directory 포리스트의 모든 Active Directory 도메인을 동기화하는 Microsoft 365. 단일 포리스트와 동기화할 Active Directory 포리스트가 여러 개 있는 Microsoft 365 단일 포리스트 디렉터리 동기화를 Sign-On [시나리오를 참조합니다.](/azure/active-directory/hybrid/whatis-hybrid-identity) 
  
이 솔루션을 배포할 때는 다음과 같은 두 가지 주요 단계가 진행됩니다.
  
1. Azure Virtual Network를 만들고 온-프레미스 네트워크에 대한 사이트 간 VPN 연결을 설정합니다. 자세한 내용은 [온-프레미스 네트워크를 Microsoft Azure Virtual Network에 연결](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md)을 참조하세요.
    
2. [Azure의 커넥트](https://www.microsoft.com/download/details.aspx?id=47594) 가입된 가상 머신에 Azure AD 계정을 설치한 다음, 프레미스 AD DS를 동기화하여 Microsoft 365. 여기에는 다음이 포함됩니다.
    
    Azure AD Connect를 실행할 Azure Virtual Machine 만들기
    
    [Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594) 설치 및 구성
    
    Azure AD 커넥트 구성하려면 Azure AD 관리자 계정 및 AD DS 엔터프라이즈 관리자 계정의 자격 증명(사용자 이름 및 암호)이 필요합니다. Azure AD 커넥트 즉시 실행되어 계속 실행되어 프레미스 AD DS 포리스트를 프레미스 AD DS 포리스트와 동기화할 Microsoft 365.
    
프로덕션 환경에서 이 솔루션을 배포하기 전에 시뮬레이트된 엔터프라이즈 기반 구성의 지침을 사용하여 이 구성을 개념 증명, 데모 또는 실험용으로 설정할 수 있습니다. [](simulated-ent-base-configuration-microsoft-365-enterprise.md)
  
> [!IMPORTANT]
> Azure AD Connect 구성이 완료될 때 AD DS 엔터프라이즈 관리자 계정 자격 증명이 저장되지는 않습니다. 
  
> [!NOTE]
> 이 솔루션에서는 단일 AD DS 포리스트를 단일 AD DS 포리스트와 동기화하는 Microsoft 365. 이 문서에서 설명하는 토폴로지는 이 솔루션을 구현하는 한 가지 방법만 제공합니다. 조직의 토폴로지가 고유한 네트워크 요구 사항 및 보안 고려 사항에 따라 다를 수 있습니다. 
  
## <a name="plan-for-hosting-a-directory-sync-server-for-microsoft-365-in-azure"></a>Azure에서 사용자에 대한 디렉터리 동기화 Microsoft 365 계획
<a name="PlanningVirtual"> </a>

### <a name="prerequisites"></a>필수 구성 요소

시작하기 전에 이 솔루션에 대한 다음 필수 구성 요소를 검토하세요.
  
- [Azure Virtual Network 계획](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#plan-your-azure-virtual-network)에서 관련 계획 콘텐츠를 검토하세요.
    
- Azure Virtual Network 구성을 위한 모든 [필수 구성 요소](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#prerequisites)가 충족되는지 확인합니다.
    
- Active Directory Microsoft 365 기능이 포함된 구독이 있는 경우 구독에 Microsoft 365 대한 자세한 내용은 Microsoft 365 [페이지로 이동하세요.](https://products.office.com/compare-all-microsoft-office-products?tab=2)
    
- Azure AD 디비전을 실행하여 커넥트 AD DS 포리스트를 사용자와 동기화하는 Azure Virtual Machine을 Microsoft 365.
    
    AD DS 엔터프라이즈 관리자 계정 및 Azure AD 관리자 계정의 자격 증명(이름 및 암호)이 있어야 합니다.
    
### <a name="solution-architecture-design-assumptions"></a>솔루션 아키텍처 디자인 가정

다음 목록은 이 솔루션을 위한 디자인 선택 옵션에 대해 설명합니다.
  
- 이 솔루션은 사이트 간 VPN 연결을 사용하는 단일 Azure Virtual Network를 사용합니다. Azure Virtual Network는 Azure AD Connect를 실행하는 디렉터리 동기화 서버에 해당하는 하나의 서버가 포함된 단일 서브넷을 호스트합니다. 
    
- 온-프레미스 네트워크에 도메인 컨트롤러 및 DNS 서버가 존재합니다.
    
- Azure AD Connect는 Single Sign-On 대신 암호 해시 동기화를 수행합니다. AD FS(Active Directory Federation Services) 인프라를 배포할 필요는 없습니다. 암호 해시 동기화 및 Single Sign-On 옵션에 대한 자세한 내용은 [Azure Active Directory 하이브리드 ID 솔루션에 적합한 인증 방법 선택](/azure/active-directory/hybrid/choose-ad-authn)을 참조하세요.
    
작업 환경에서 이 솔루션을 배포할 때 다음을 비롯한 추가 디자인 선택 옵션을 고려할 수 있습니다.
  
- 기존 Azure Virtual Network에 기존 DNS 서버가 있는 경우 디렉터리 동기화 서버에서 이름 확인을 위해 온-프레미스 네트워크의 DNS 서버 대신, 기존 DNS 서버를 사용하도록 할지 여부를 결정합니다.
    
- 기존 Azure Virtual Network에 도메인 컨트롤러가 있는 경우 Active Directory 사이트 및 서비스를 구성하는 것이 더 나은 옵션인지 결정합니다. 디렉터리 동기화 서버는 온-프레미스 네트워크의 도메인 컨트롤러 대신, Azure Virtual Network의 도메인 컨트롤러에서 계정 및 암호 변경 내용을 쿼리할 수 있습니다.
    
## <a name="deployment-roadmap"></a>배포 로드맵

Azure의 가상 머신에 Azure AD Connect를 배포하는 과정은 다음 세 단계로 구성됩니다.
  
- 1단계: Azure Virtual Network 만들기 및 구성
    
- 2단계: Azure Virtual Machine 만들기 및 구성
    
- 3단계: Azure AD Connect 설치 및 구성
    
배포 후 새 사용자 계정에 대한 위치 및 라이선스도 배포 후에 할당해야 Microsoft 365.


### <a name="phase-1-create-and-configure-the-azure-virtual-network"></a>1단계: Azure Virtual Network 만들기 및 구성

Azure Virtual Network를 만들고 구성하려면 [ 온-프레미스 네트워크를 Microsoft Azure Virtual Network에 연결](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md)의 배포 로드맵에서 [1단계: 온-프레미스 네트워크 준비](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#phase-1-prepare-your-on-premises-network) 및 [2단계: Azure에 프레미스 간 가상 네트워크 만들기](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#phase-2-create-the-cross-premises-virtual-network-in-azure)를 완료합니다.
  
구성 결과는 다음과 같습니다.
  
![Azure에서 호스트되는 서버의 디렉터리 동기화 Microsoft 365 1단계.](../media/aab6a9a4-eb78-4d85-9b96-711e6de420d7.png)
  
이 그림에서는 사이트 간 VPN 또는 ExpressRoute 연결을 통해 Azure Virtual Network에 연결된 온-프레미스를 보여줍니다.
  
### <a name="phase-2-create-and-configure-the-azure-virtual-machine"></a>2단계: Azure Virtual Machine 만들기 및 구성

[Azure Portal에서 첫 번째 Windows Virtual Machine 만들기](https://go.microsoft.com/fwlink/p/?LinkId=393098)의 지침에 따라 Azure에 가상 머신을 만듭니다.
  
- **기초** 창에서 사용자 가상 네트워크와 동일한 구독, 위치 및 리소스 그룹을 선택합니다. 사용자 이름과 암호를 안전한 위치에 기록합니다. 나중에 가상 컴퓨터에 연결하려면 이러한 정보가 필요합니다.
    
- **크기 선택** 창에서 **A2 표준** 크기를 선택합니다.
    
- **설정** 창의 **저장소** 섹션에서 **표준** 저장소 유형을 선택합니다. **네트워크** 섹션에서 디렉터리 동기화 서버를 호스트하기 위한 가상 네트워크 및 서브넷 이름을 선택합니다(GatewaySubnet 제외). 다른 설정은 기본값을 그대로 사용합니다.
    
내부 DNS를 확인하여 주소 (A) 레코드가 해당 IP 주소의 가상 머신에 대해 추가되었는지 검토함으로써 디렉터리 동기화 서버가 DNS를 올바르게 사용하고 있는지 확인합니다. 
  
[가상 머신에 연결 및 로그온](/azure/virtual-machines/windows/connect-logon)의 지침을 사용하여 원격 데스크톱 연결을 통해 디렉터리 동기화 서버에 연결합니다. 로그인한 후에 가상 머신을 온-프레미스 AD DS 도메인에 가입합니다.
  
Azure AD Connect가 인터넷 리소스에 액세스할 수 있게 하려면 온-프레미스 네트워크의 프록시 서버를 사용하도록 디렉터리 동기화 서버를 구성해야 합니다. 수행할 추가 구성 단계에 대해서는 네트워크 관리자에게 문의하세요.
  
구성 결과는 다음과 같습니다.
  
![Azure에서 호스트되는 Microsoft 365 디렉터리 동기화 서버의 2단계.](../media/9d8c9349-a207-4828-9b2b-826fe9c06af3.png)
  
이 그림은 크로스-프레미스 Azure Virtual Network의 디렉터리 동기화 서버 가상 머신을 보여줍니다.
  
### <a name="phase-3-install-and-configure-azure-ad-connect"></a>3단계: Azure AD Connect 설치 및 구성

다음 절차를 완료합니다.
  
1. 로컬 관리자 권한이 있는 AD DS 도메인 계정으로 원격 데스크톱 연결을 통해 디렉터리 동기화 서버에 연결합니다. [가상 머신에 연결 및 로그온](/azure/virtual-machines/windows/connect-logon)을 참조하세요.
    
2. 디렉터리 동기화 서버에서 디렉터리 동기화 설정 문서를 [Microsoft 365](set-up-directory-synchronization.md) 암호 해시 동기화를 사용하여 디렉터리 동기화에 대한 지침을 따르십시오.
    
> [!CAUTION]
> 설치 프로그램은 로컬 사용자 OU(조직 구성 단위)에 **AAD_xxxxxxxxxxxx** 계정을 만듭니다. 이 계정을 이동하거나 제거하면 안 됩니다. 이 경우 동기화가 실패합니다.
  
구성 결과는 다음과 같습니다.
  
![Azure에서 호스트되는 Microsoft 365 디렉터리 동기화 서버의 3단계.](../media/3f692b62-b77c-4877-abee-83c7edffa922.png)
  
이 그림은 크로스-프레미스 Azure Virtual Network에서 Azure AD Connect를 사용하는 디렉터리 동기화 서버를 보여줍니다.
  
### <a name="assign-locations-and-licenses-to-users-in-microsoft-365"></a>2013에서 사용자에게 위치 및 라이선스 Microsoft 365

Azure AD 커넥트 계정은 Microsoft 365 AD DS에서 Microsoft 365 구독에 계정을 추가하지만 사용자가 Microsoft 365 로그인하고 해당 서비스를 사용하려면 위치 및 라이선스를 사용하여 계정을 구성해야 합니다. 다음 단계를 사용하여 위치를 추가하고 해당 사용자 계정에 대한 라이선스를 활성화합니다.
  
1. 에 로그인하여 [Microsoft 365 관리 센터](https://admin.microsoft.com)를 클릭한 다음 관리자 를 **클릭합니다.**
    
2. 왼쪽 탐색에서 사용자 활성  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">**사용자를 클릭합니다.**</a>
3. 사용자 계정 목록에서 정품 인증하려는 사용자 옆에 있는 확인란을 선택합니다.
    
4. 사용자 페이지에서 **제품 라이선스** 에 대해 **편집** 을 클릭합니다.
    
5. **제품 라이선스** 페이지에서 **위치** 로 사용자의 위치를 선택한 다음, 사용자를 위한 적절한 라이선스를 사용하도록 설정합니다.
    
6. 완료되면 **저장** 을 클릭한 다음 **닫기** 를 두 번 클릭합니다.
    
7. 추가 사용자가 있으면 3단계로 돌아갑니다.
    
## <a name="see-also"></a>참고 항목

[Microsoft 365 솔루션 및 아키텍처 센터](../solutions/index.yml)
  
[온-프레미스 네트워크를 Microsoft Azure Virtual Network에 연결](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md)

[Azure AD Connect 다운로드](https://www.microsoft.com/download/details.aspx?id=47594)
  
[사용자에 대한 디렉터리 동기화 Microsoft 365](set-up-directory-synchronization.md)
