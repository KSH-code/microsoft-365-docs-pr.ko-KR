---
title: DNS 기본 사항
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
- admindeeplinkMAC
search.appverid:
- MET150
- MOE150
- GEA150
- BSA160
ms.assetid: 854b6b2b-0255-4089-8019-b765cff70377
ROBOTS: NOINDEX
description: 도메인 이름 시스템은 컴퓨터 호스트 이름을 IP 주소에 매핑하며 DNS 및 도메인 등록 기관의 기본 기능을 이해하면 도메인을 관리하는 데 도움이 됩니다.
ms.openlocfilehash: 42c93ba7c0edd76b1371015ea9c3b2dd1e4f8bbb
ms.sourcegitcommit: aebcdbef52e42f37492a7f780b8b9b2bc0998d5c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2021
ms.locfileid: "59774607"
---
# <a name="dns-basics"></a>DNS 기본 사항

 원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.yml)** 하세요. 
  
::: moniker range="o365-worldwide"

도메인 이름(예: contoso.com)은 전 세계 도메인 등록 기관 및 데이터베이스 시스템을 사용하여 관리됩니다. DNS(Domain Name System)는 사람이 읽을 수 있는 컴퓨터 호스트 이름과 네트워킹 장비에서 사용하는 IP 주소 간의 매핑을 제공합니다. DNS 및 도메인 등록 기관 기본 사항을 이해하면 도메인을 관리하는 데 도움이 될 수 있습니다.

## <a name="watch-domains--dns-an-overview"></a>시청: 도메인 및 DNS: 개요
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c005f2a4-90ad-46fe-b1ab-90f41f2a9d53?autoplay=false]
  
::: moniker-end

::: moniker range="o365-germany"

도메인 이름(예: contoso.com)은 전 세계 도메인 등록 기관 및 데이터베이스 시스템을 사용하여 관리됩니다. DNS(Domain Name System)는 사람이 읽을 수 있는 컴퓨터 호스트 이름과 네트워킹 장비에서 사용하는 IP 주소 간의 매핑을 제공합니다. DNS 및 도메인 등록 기관 기본 사항을 이해하면 도메인을 관리하는 데 도움이 될 수 있습니다.

## <a name="watch-domains--dns-an-overview"></a>시청: 도메인 및 DNS: 개요
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c005f2a4-90ad-46fe-b1ab-90f41f2a9d53?autoplay=false]
  
::: moniker-end

::: moniker range="o365-21vianet"

도메인 이름(예: contoso.com)은 전 세계 도메인 등록 기관 및 데이터베이스 시스템을 사용하여 관리됩니다. DNS(Domain Name System)는 사람이 읽을 수 있는 컴퓨터 호스트 이름과 네트워킹 장비에서 사용하는 IP 주소 간의 매핑을 제공합니다. DNS 및 도메인 등록 기관 기본 사항을 이해하면 관리자가 도메인을 관리하는 데 도움이 됩니다.
  
::: moniker-end

## <a name="what-are-domain-names"></a>도메인 이름이란?

도메인 이름은 URL 및 전자 메일 주소에서 사용되며 여러 수준으로 구성됩니다. 예를 들어, mail.contoso.com에는 다음과 같은 세 수준이 있습니다.
  
- **.com** 은 최상위 도메인입니다. 
    
- **contoso** 는 두 번째 수준 도메인입니다. 
    
- **mail** 은 세 번째 수준 도메인입니다. 
    
세 번째 수준 도메인을 사용하는 이유는 무엇일까요? 사용자가 마케팅 또는 블로그에 다른 도메인 이름을 원할 수 있습니다. 예를 들어 blog.contoso.com입니다. 일반적으로 Microsoft에서 사용하도록 contoso.com과 같은 두 번째 수준 도메인을 추가하지만, 원한다면 세 번째 수준 도메인을 사용할 수도 있습니다.
  
각 제품 유형에 따라 도메인에서 수행할 수 있는 기능에 대한 자세한 내용은 [Microsoft 365 및 Office 365 플랫폼 서비스 설명](/office365/servicedescriptions/office-365-platform-service-description/domains)을 참조하세요.
  
## <a name="understand-dns-record-types"></a>DNS 레코드 종류 이해

도메인의 DNS 호스트에 저장된 DNS 레코드는 도메인의 트래픽을 전달하는 데 사용됩니다. 다음 표에서는 자주 사용하는 DNS 레코드와 이러한 레코드를 사용하는 방식에 대해 설명합니다.
  
|**NS(이름 서버) 레코드**|**특정 도메인에 대해 "신뢰할 수 있는 이름 서버"를 식별합니다. 도메인의 이름 서버를 변경하면 DNS 레코드가 관리되는 위치 및 DNS 시스템이 메일 서버 등에 관한 정보를 찾는 위치가 변경됩니다. Microsoft에는 자체 이름 서버가 있지만, 도메인에 이미 설정되어 있는 이름 서버를 계속 사용할 수도 있습니다.**|
|:-----|:-----|
|레코드(주소 레코드)  <br/> |IP 주소와 도메인 이름을 연결합니다.  <br/> |
|CNAME(별칭 또는 정식 이름) 레코드  <br/> |DNS 시스템의 한 도메인을 다른 도메인으로 리디렉션합니다. 이름 서버가 도메인을 조회하여 CNAME 레코드가 있다는 것을 발견하면 첫 번째 도메인 이름을 CNAME으로 대체하고 새 이름을 조회합니다.  <br/> |
|MX(메일 교환기) 레코드  <br/> |전자 메일을 보낼 위치를 가리킵니다. 여기에는 우선 순위 필드도 있어 우선 순위대로 여러 서버에 메일을 전송할 수 있습니다.  <br/> |
|SPF(Sender Policy Framework) 레코드  <br/> |전자 메일 스푸핑 및 피싱을 방지하는 데 도움이 되는 TXT 레코드입니다.  <br/> |
|SRV(서비스) 레코드  <br/> |비즈니스용 Skype Online 및 Exchange Online에서 Microsoft 서비스 간의 정보 흐름을 조정하는 데 사용됩니다. 예를 들어 SRV 레코드는 Outlook Web App에서 현재 상태를 확인하고 비즈니스용 Skype Online, Skype 또는 다른 회사의 사용자와 기타 인스턴트 메시징 도구를 사용하는 데 필요합니다.  <br/> |
|TTL(time-to-live)  <br/> |이름 서버가 업데이트된 버전을 찾기 전에 서버에서 DNS 레코드가 유지되는 시간입니다.  <br/> |
   
## <a name="how-does-dns-work"></a>DNS의 작동 방식

Microsoft 365와 같은 클라우드 서비스를 사용하여 도메인을 설정하는 과정에는 도메인에 대한 [DNS 레코드](dns-basics.md)를 변경하거나 추가하는 작업이 포함됩니다. 인터넷이 DNS(Domain Name System) 및 도메인 이름과 작동하는 방식 때문에, 전자 메일 및 웹 사이트 등 항목을 보내거나 찾을 위치를 파악하기 위해 이러한 변경 작업이 필요합니다. 
  
인터넷은 DNS(Domain Name System)를 사용하도록 설정되어 있기 때문에, 실제로는 IP(인터넷 프로토콜) 주소라고 하는 외우기 힘든 숫자로 된 특정 인터넷 위치를 사용자는 contoso.com과 같은 친숙한 이름을 사용하여 찾을 수 있는 것입니다. IP 주소는 70.42.241.42와 같은 형식입니다. 따라서 도메인 이름을 사용하여 전자 메일 호스트 및 웹 사이트 등의 위치를 식별하는 것이 훨씬 더 쉽습니다.
  
즉, DNS 레코드는 전자 메일을 보낼 위치(예: joe@contoso.com) 또는 도메인 이름을 사용하는 웹 사이트를 찾을 위치(예: www.contoso.com)를 인터넷에 알려줍니다. 올바른 정보를 도메인의 올바른 DNS 레코드에 입력하면 DNS 시스템이 모든 것을 정확하게 라우팅하므로 사용자의 전자 메일이 다른 곳이 아닌 Microsoft 365에 도착합니다.
  
도메인의 DNS 레코드는 다른 방법으로도 유용할 수 있습니다.  예를 들어 Exchange는 Outlook이 올바른 Exchange 서버에 대한 연결을 자동으로 설정할 수 있게 하는 DNS 레코드를 확인합니다.
  
### <a name="dns-records-help-the-internet-send-email-to-the-right-place"></a>DNS 레코드를 통해 인터넷에서 올바른 위치에 전자 메일 전송

위에서 설명했듯이, DNS는 기본적으로 트래픽을 인터넷으로 전달하여 외우기 어려운 IP 주소에 친숙한 도메인 이름을 매핑합니다. MX 레코드라고 하는 DNS 레코드는 특히 전자 메일을 올바른 호스트에 보내는 레코드입니다.
  
DNS 레코드는 도메인에 대한 정보의 데이터베이스와 유사합니다. 레코드 및 해당 값은 영역 파일이라는 항목에 보관되며 여기에는 도메인에 대한 각 레코드 목록과 해당 값이 포함됩니다. 도메인 등록 기관과 기타 DNS 호스팅 회사는 사용자의 도메인 영역 파일에서 레코드를 편집할 수 있도록 웹 사이트에 UI를 제공합니다. 이는 도메인에 대한 MX 레코드를 업데이트하여 전자 메일 메시지가 Microsoft 365로 전송되도록 하는 곳입니다.
  
 *다음 단계에서 도메인의 MX 레코드를 업데이트하여 전자 메일을 Microsoft 365로 변경하면 해당 도메인으로 전송된 모든 전자 메일이 Microsoft 365로 배달되기 시작합니다.*  다른 사용자가 해당 도메인을 전자 메일에 사용하는 경우 해당 사용자 각각에 대해 Microsoft 365 사서함을 설정해야 합니다. 
  
복잡하게 들리나요? 물론 Microsoft 도메인 설정의 각 단계가 설명될 수 있습니다.
  
### <a name="dns-tells-the-internet-where-to-look-for-websites-too"></a>DNS는 또한 인터넷에 웹 사이트를 찾을 위치를 알립니다.

예를 들어 www.contoso.com과 같이 웹 사이트 주소를 입력하면 인터넷은 먼저 DNS 서버 중 하나에서 contoso.com에 대한 NS(이름 서버) 레코드를 사용하여 확인합니다. NS 레코드는 해당 도메인에 대한 다른 모든 DNS 레코드 값을 포함하는 영역 파일을 찾을 위치를 인터넷에 알려줍니다. DNS 서버는 많은 수가 있으며, 이들은 모두 서로 연결되어 있습니다. 서버들은 서로 협력하여 고유하게 등록된 모든 도메인 이름과 도메인의 영역 파일이 있는 위치를 추적합니다.
  
::: moniker range="o365-worldwide"

Contoso.com의 NS 레코드에 "godaddy.com"이 있다고 가정해 보겠습니다. 이제 인터넷은 contoso.com에 대한 다른 모든 DNS 레코드를 나열하는 영역 파일을 찾을 위치가 GoDaddy.com이라는 것을 알고 있습니다. 이러한 DNS 레코드에는 contoso.com 및 기타 레코드에 대한 전자 메일을 보낼 위치를 나타내는 MX 레코드가 포함됩니다. MX 레코드에 "Microsoft 365로 전자 메일 보내기"를 설정(기술적 용어로)하는 값이 있는 경우에는 contoso.com 전자 메일 주소(예: joe@contoso.com)로 전송된 모든 전자 메일 메시지가 Microsoft 365로 전송됩니다. 그런 다음 해당 위치에 "joe" 라는 사서함이 있으면 전자 메일이 전송됩니다.

::: moniker-end

::: moniker range="o365-germany"

Contoso.com의 NS 레코드에 "godaddy.com"이 있다고 가정해 보겠습니다. 이제 인터넷은 contoso.com에 대한 다른 모든 DNS 레코드를 나열하는 영역 파일을 찾을 위치가 GoDaddy.com이라는 것을 알고 있습니다. 이러한 DNS 레코드에는 contoso.com 및 기타 레코드에 대한 전자 메일을 보낼 위치를 나타내는 MX 레코드가 포함됩니다. MX 레코드에 "Microsoft 365로 전자 메일 보내기"를 설정(기술적 용어로)하는 값이 있는 경우에는 contoso.com 전자 메일 주소(예: joe@contoso.com)로 전송된 모든 전자 메일 메시지가 Microsoft 365로 전송됩니다. 그런 다음 해당 위치에 "joe" 라는 사서함이 있으면 전자 메일이 전송됩니다.

::: moniker-end

::: moniker range="o365-21vianet"

Contoso.com의 NS 레코드에 "hichina.com."이 있다고 가정해 보겠습니다. 이제 인터넷은 contoso.com에 대한 다른 모든 DNS 레코드를 나열하는 영역 파일을 찾을 위치가 hichina.com이라는 것을 알고 있습니다. 이러한 DNS 레코드에는 contoso.com 및 기타 레코드에 대한 전자 메일을 보낼 위치를 나타내는 MX 레코드가 포함됩니다. MX 레코드에 "Microsoft 365로 전자 메일 보내기"를 설정(기술적 용어로)하는 값이 있는 경우에는 contoso.com 전자 메일 주소(예: joe@contoso.com)로 전송된 모든 전자 메일 메시지가 Microsoft 365로 전송됩니다. 그런 다음 해당 위치에 "joe" 라는 사서함이 있으면 전자 메일이 전송됩니다.

::: moniker-end

Microsoft 365에서 이러한 모든 설정이 제대로 작동하기 위해 입력해야 하는 실제 값이 도메인을 설정할 때 도메인 설정 단계에서 사용자에게 표시됩니다. 수동으로 설정하는 경우 값을 복사하여 DNS 호스트(이는 도메인 등록 기관이 될 수 있지만, 꼭 그럴 필요는 없습니다)의 올바른 DNS 레코드(MX 레코드, CNAME 레코드 등)에 붙여넣습니다.
  
::: moniker range="o365-worldwide"

도메인 영역 파일이 도메인 등록 기관 이외의 다른 곳에 있을 수 있는 이유는 무엇인가요? GoDaddy와 같은 도메인 등록 기관에 도메인 이름을 등록할 수 있지만, DNS 레코드는 별도의 DNS 호스팅 회사나 웹 호스팅 회사 등 다른 곳에서 관리될 수 있습니다. 도메인의 NS 레코드는 해당 정보를 저장하므로 모든 DNS 서버가 검색할 위치를 알 수 있습니다.

::: moniker-end

::: moniker range="o365-germany"

도메인 영역 파일이 도메인 등록 기관 이외의 다른 곳에 있을 수 있는 이유는 무엇인가요? GoDaddy와 같은 도메인 등록 기관에 도메인 이름을 등록할 수 있지만, DNS 레코드는 별도의 DNS 호스팅 회사나 웹 호스팅 회사 등 다른 곳에서 관리될 수 있습니다. 도메인의 NS 레코드는 해당 정보를 저장하므로 모든 DNS 서버가 검색할 위치를 알 수 있습니다.

::: moniker-end

::: moniker range="o365-21vianet"

도메인 영역 파일이 도메인 등록 기관 이외의 다른 곳에 있을 수 있는 이유는 무엇인가요? HiChina와 같은 도메인 등록 기관에 도메인 이름을 등록할 수 있지만, DNS 레코드는 별도의 DNS 호스팅 회사나 웹 호스팅 회사 등 다른 곳에서 관리될 수 있습니다. 도메인의 NS 레코드는 해당 정보를 저장하므로 모든 DNS 서버가 검색할 위치를 알 수 있습니다.

::: moniker-end

::: moniker range="o365-worldwide"
## <a name="why-add-a-domain-in-microsoft-365"></a>Microsoft 365에서 도메인을 추가해야 하는 이유


사용자 지정 도메인(예: fourthcoffee.com)을 Microsoft 365에 추가하면 서비스에서 더 짧고 친숙한 전자 메일 주소와 사용자 ID를 사용할 수 있습니다. Microsoft 365 계정에 가입할 때 [사용할 도메인이 제공](../setup/domains-faq.yml)되지만, 여기에는 "onmicrosoft.com"이 포함됩니다. 많은 사용자가 전자 메일에 Microsoft 365를 사용하려는 경우 조직 또는 비즈니스 도메인을 추가하는 것을 선호합니다. 
  
> [!NOTE]
> Outlook 또는 Word 등의 Microsoft 앱을 다운로드하고 사용하려는 경우에는 도메인을 추가할 필요가 없습니다. [PC 또는 Mac에 Office를 설치](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)하기만 하면 됩니다. 
  
전자 메일, 공개 웹 사이트 및 메신저 주소에 Microsoft 365의 사용자 도메인 이름을 사용할 수 있습니다.
  
- **전자 메일:** 도메인 이름을 사용하면 전자 메일을 사용자 지정할 수 있으므로 계정과 함께 제공되는 [초기 onmicrosoft.com 전자 메일 주소](../setup/domains-faq.yml)보다 더 짧고 기억하기 쉬운 주소를 사용할 수 있습니다. 따라서 전자 메일 주소(Microsoft 365에 로그인하는 데 사용하는 회사 계정으로도 사용됨)가 joe@contoso.onmicrosoft.com 대신 joe@contoso.com으로 될 수 있습니다. 
    
- **웹 사이트:** Microsoft 365 구독에 SharePoint Online 공개 웹 사이트(더 이상 구입할 수 없음)가 포함된 경우 공개 웹 사이트에는 contoso-public.sharepoint.com과 같은 초기 주소가 제공됩니다. 비즈니스를 위한 웹 사이트를 설정한 경우 www.contoso.com과 같이 사용자 지정 도메인 이름을 사용하여 웹 사이트 주소의 이름을 바꿀 수 있습니다. 
    
- **인스턴트 메시징:** 도메인 이름을 사용하도록 비즈니스용 Skype Online 주소를 사용자 지정할 수도 있으므로, 조직의 사용자들이 더 짧고 기억하기 쉬운 주소(예: joe@contoso.com)를 사용하여 비즈니스용 Skype Online에서 서로 연결할 수 있습니다. 
    
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-add-a-domain-in-microsoft-365"></a>Microsoft 365에서 도메인을 추가해야 하는 이유


사용자 지정 도메인(예: fourthcoffee.com)을 Microsoft 365에 추가하면 서비스에서 더 짧고 친숙한 전자 메일 주소와 사용자 ID를 사용할 수 있습니다. Microsoft 365 계정에 가입할 때 [사용할 도메인이 제공](../setup/domains-faq.yml)되지만, 여기에는 "onmicrosoft.com"이 포함됩니다. 많은 사용자가 전자 메일에 Microsoft 365를 사용하려는 경우 조직 또는 비즈니스 도메인을 추가하는 것을 선호합니다. 
  
> [!NOTE]
> Outlook 또는 Word 등의 Microsoft 365 앱만을 다운로드하고 사용하려는 경우에는 도메인을 추가할 필요가 없습니다. [PC 또는 Mac에 Office를 설치](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)하기만 하면 됩니다. 
  
전자 메일, 공개 웹 사이트 및 메신저 주소에 Microsoft 365의 사용자 도메인 이름을 사용할 수 있습니다.
  
- **전자 메일:** 도메인 이름을 사용하면 전자 메일을 사용자 지정할 수 있으므로 계정과 함께 제공되는 [초기 onmicrosoft.com 전자 메일 주소](../setup/domains-faq.yml)보다 더 짧고 기억하기 쉬운 주소를 사용할 수 있습니다. 따라서 전자 메일 주소(Microsoft 365에 로그인하는 데 사용하는 회사 계정으로도 사용됨)가 joe@contoso.onmicrosoft.com 대신 joe@contoso.com으로 될 수 있습니다. 
    
- **웹 사이트:** 구독에 SharePoint Online 공개 웹 사이트(더 이상 구입할 수 없음)가 포함된 경우 공개 웹 사이트에는 contoso-public.sharepoint.com과 같은 초기 주소가 제공됩니다. 비즈니스를 위한 웹 사이트를 설정한 경우 www.contoso.com과 같이 사용자 지정 도메인 이름을 사용하여 웹 사이트 주소의 이름을 바꿀 수 있습니다. 
    
- **인스턴트 메시징:** 도메인 이름을 사용하도록 비즈니스용 Skype Online 주소를 사용자 지정할 수도 있으므로, 조직의 사용자들이 더 짧고 기억하기 쉬운 주소(예: joe@contoso.com)를 사용하여 비즈니스용 Skype Online에서 서로 연결할 수 있습니다. 
    
::: moniker-end

## <a name="the-dns-records-required-for-microsoft-365"></a>Microsoft 365에 필요한 DNS 레코드

Microsoft 365에서 도메인을 사용하려면 많은 DNS 레코드가 필요합니다. 전자 메일이 Microsoft 365로 전송될 수 있도록 도메인의 MX 레코드를 설정하는 것 외에도 Outlook이 올바른 Exchange 서버에 자동으로 연결되고 메신저를 설정하고 스팸 전자 메일을 방지하는 데 도움이 되는 레코드가 있습니다.
  
도메인을 설정하기 위한 [값 목록을 찾을](information-for-dns-records.md) 수 있습니다. <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Microsoft 365 관리 센터</a>에 바로 포함됩니다. 
  
또는 배포를 계획하고 있는 경우 Microsoft 365에 필요한 모든 DNS 레코드, 해당 기능, 예시 값 목록을 검토해 볼 수 있습니다. [Microsoft 365에 대한 외부 Domain Name System 레코드](../../enterprise/external-domain-name-system-records.md)를 참조하세요.
  
## <a name="next-steps"></a>다음 단계

다음 중 하나를 확인하세요. 
  
- 도메인이 어디에 등록되어 있는지 잘 모르시나요? [도메인 등록 기관 찾기 도움말을 확인하세요.](find-your-domain-registrar.md)
- Microsoft 365에서 도메인을 사용하기 전에 먼저 [마법사 단계를 완료해야 하는 이유](../setup/add-domain.md)를 알아보세요.

## <a name="related-content"></a>관련 콘텐츠

[도메인 FAQ](../setup/domains-faq.yml)(문서)\
[도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 수정](find-and-fix-issues.md)(문서)\
[도메인 관리](index.yml)(링크 페이지)