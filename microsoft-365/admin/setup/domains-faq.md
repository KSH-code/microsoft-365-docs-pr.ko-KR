---
title: 도메인 FAQ
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 1272bad0-4bd4-4796-8005-67d6fb3afc5a
description: FAQ에서 질문에 대 한 대답을 찾아 도메인에 대해 자세히 알아보세요.
ms.custom: okr_smb
ms.openlocfilehash: 4ece90306f37b6f07e34ce93423a76f084d50b6f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627597"
---
# <a name="domains-faq"></a>도메인 FAQ

이 문서에는 Office 365의 도메인에 대 한 질문과 대답이 포함 되어 있습니다.

질문에 대한 대답을 찾을 수 없는 경우 저희에게 메모를 남겨 알려주시면 목록에 추가해 드리겠습니다.
    
## <a name="what-is-mx-priority"></a>MX 우선 순위란?

메일은 가장 낮은 기본 설정 번호 (가장 높은 우선 순위)를 사용 하 여 메일 교환 서버로 배달 되므로 메일 라우팅에 사용 하는 MX 레코드는 가장 낮은 기본 설정 번호 (일반적으로 0 또는 *높은* 우선 순위)를 가져야 합니다. 
  
- MX 레코드를 만들 때 대부분의 DNS 호스팅 공급자가 기본 설정 번호를 설정 해야 합니다.
    
- 일부 레이블은 box *기본 설정* 및 일부 레이블의 *우선 순위* 입니다. 
    
- 일부 필요한 경우에는 *낮음* , *중간* 또는 *높음을* 선택 하 라는 것이 좋습니다. 
    
- MX 레코드가 하나인 경우에는 우선 순위 또는 기본 설정에 적절 한 값을 사용할 수 있습니다.
    
- 두 개 이상 있는 경우 메일 라우팅에 대 한 MX 레코드의 우선 순위가 도메인을 소유 하 고 있는지 확인 하는 데 사용 되는 것 보다 높은 지 확인 합니다.
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a>내 도메인에 대 한 SPF 레코드를 확인 하려면 어떻게 하나요?

**SPF에 대해서는 TXT 레코드를**하나만 만들거나 만들어야 합니다. SPF 레코드가 이미 있는 경우 새 Office 365 값을 만드는 대신 새로 만들어 해당 레코드에 추가 해야 합니다. Microsoft 전자 메일에 대 한 SPF 레코드를 추가 하거나 업데이트 한 후 다음 도구 중 하나를 사용 하 여 구문이 올바른지 확인 해야 합니다. 
  
- [SPF 레코드 테스트 도구](http://www.kitterman.com/spf/validate.html)
    
- [SPF Surveyor](https://dmarcian.com/spf-survey/)
    
- [웹 인터페이스](http://digwebinterface.com/)
    
## <a name="how-does-office-365-manage-my-dns-records"></a>Office 365에서 내 DNS 레코드를 관리 하는 방법

Office 365의 DNS 관리에 대 한 두 가지 옵션이 있습니다.
  
1. NS (이름 서버) 레코드를 변경 하 고 Microsoft는 전자 메일에 대 한 MX 레코드를 설정 하는 것과 같은 모든 서비스 관련 레코드를 관리 합니다. **는**
    
2. DNS 호스트에서 전자 메일 및 기타 Office 365 서비스에 대 한 DNS 레코드를 직접 추가 합니다. **(전문가 전용)**
    
### <a name="office-365-creates-and-hosts-the-dns-records"></a>Office 365에서 DNS 레코드를 만들고 호스트 합니다. 
**장점** 
- Office 365 서비스의 DNS 레코드에 대해 입력 한 값으로 실수를 염려할 필요가 없습니다.  
- 도메인 등록자와 DNS 호스트를 보다 유연 하 게 선택할 수 있습니다. 
- 공급자가 필요한 모든 레코드 형식을 지원 하지 않더라도 이름 서버 레코드를 변경할 수 있는 공급자가 모두 작동 합니다.   
- Office 365에서 새 DNS 레코드를 추가 하는 경우에는 업데이트할 필요가 없습니다.  

#### <a name="disadvantages"></a>단점 
- Office 365 외부에서 전자 메일을 호스팅하도록 DNS 레코드를 변경할 수는 없습니다. 
- Www.fourthcoffee.com와 같이 해당 주소에 대해 도메인에 공용 웹 사이트를 이미 사용 하 고 있는 경우에는 Office 365에서 해당 주소로 사용자를 리디렉션해야 합니다. 
- 리디렉션을 설정 하려면 고정 IP 주소가 필요 하며, 공개 웹 사이트에는 사용 하지 못할 수 있습니다. -현재 도메인 등록 기관에서 도메인의 이름 서버 레코드를 변경 하는 것을 허용 하지 않는 경우이 DNS 관리 옵션을 사용 하려면 다른 등록 기관으로 전환 해야 합니다.  

 ### <a name="you-manage-the-dns-records-yourself"></a>직접 DNS 레코드를 관리 하는 경우 
 #### <a name="advantages"></a>장점
- Office 365 서비스에 대 한 DNS 레코드를 제어 합니다.   
- Www.fourthcoffee.com 처럼 해당 주소에 대 한 도메인을 가진 공개 웹 사이트가 있는 경우에는 리디렉션을 사용 하 여 Office 365에서 도메인을 설정한 후에도 사용자의 웹 사이트에 계속 액세스할 수 있도록 하는 데 신경 쓰지 않아도 됩니다.    
- 온-프레미스 Exchange 서버와 같은 다른 위치에서 전자 메일을 호스팅할 수 있는 유연성이 있습니다.  
 
#### <a name="disadvantages"></a>단점
Office 365 서비스에 대 한 DNS 레코드를 직접 설정 해야 합니다 (GoDaddy 도메인을 갖고 있지 않은 경우). 
-  현재 DNS 호스트가 Microsoft 365에 필요한 레코드 종류 중 일부를 지원 하지 않는 경우 일부 기능을 사용할 수 없으며 다른 DNS 호스트로 전환 해야 할 수 있습니다. 
- Office 365에서 DNS 레코드에 대 한 요구 사항을 변경 하거나 새 서비스를 추가 하는 경우 DNS 호스트에서 직접 업데이트를 수행 해야 합니다. 
   
## <a name="what-is-a-domain-name"></a>도메인 이름 이란?


도메인은 전자 메일 주소에서 **@** 기호 뒤에, 그리고 웹 주소에서 **www.** 뒤에 나타나는 고유한 이름입니다. 일반적으로 *yourbusiness.com* 또는 stateuniversity.edu와 같은 표준 인터넷 접미사와 조직의 이름 형식을 사용 합니다 *.* 
  
"**Rob\@contoso.com**"와 같은 사용자 지정 도메인을 Office 365와 함께 사용 하면 신용 및 브랜드를 위한 신뢰도를 구축 하는 데 도움이 될 수 있습니다. 
  
[Office 365에서 도메인을 구입 하 여이를 자동으로 설정](../get-help-with-domains/buy-a-domain-name.md)하거나 이미 도메인 등록 기관에서 소유한 사용자를 구입 하거나 가져올 수 있습니다.
  
## <a name="can-i-transfer-a-domain-i-purchased-from-microsoft-to-another-provider"></a>Microsoft에서 구입한 도메인을 다른 공급자에 게 전송할 수 있나요?

예, 그러나 office 365 도메인을 다른 등록 365 60 기관으로 전송할 수 없습니다.

*Whois* 쿼리에는 Office 365 구매한 도메인 등록 자가 와일드 서 지 도메인 LLC로 표시 됩니다. 그러나 Office 365 구매한 도메인에 대 한 Office 365에만 문의 해야 합니다.
  
아래 단계에 따라 Office 365의 코드를 가져온 다음 다른 도메인 등록 기관 웹 사이트로 이동 하 여 해당 등록자에 게 도메인 이름을 전송 하도록 설정 합니다.

::: moniker range="o365-worldwide"

1. I관리 센터에서 ** 설정 ** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인 </a> 페이지로 이동하십시오.

::: moniker-end

::: moniker range="o365-germany"

1. I관리 센터에서 ** 설정 ** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank"> 도메인 </a> 페이지로 이동하십시오.

::: moniker-end

::: moniker range="o365-21vianet"

1. 관리 센터에서 <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">라이선스</a> **설정** > 페이지로 이동 합니다.

::: moniker-end
    
2. **도메인** 페이지에서 다른 도메인 등록자에 게 전송할 Office 365 도메인을 선택 하 고 **도메인 전송을** > **사용 하 여 도메인 전송을**선택 합니다.
       
4. 단계에 따라 도메인 전송을 준비 합니다.
    
5. 코드를 받은 후 도메인 이름을 관리 하려는 도메인 등록 기관 웹 사이트로 이동 하 여 도메인을 전송 하기 위한 지침을 따르세요 (웹 사이트에서 도움말 검색).
    
6. 코드를 다시 표시 해야 하는 경우에는 Office 365의 **도메인 설정** 페이지에서 **도메인 전송을 위한 인증 코드 보기**를 선택 합니다.
    
7. 전송이 완료 되 면 새 도메인 등록 기관에서 도메인을 갱신 합니다.
    
8. 프로세스를 마치려면 관리 센터 **도메인** 페이지로 돌아가 **전체 도메인 전송을**선택 합니다. 

*참고: Office 365에서 구매한 도메인은 이름 서버 변경 또는 Office 365 테 넌 트 간에 도메인을 전송 하기에 적합 하지 않습니다.  이러한 두 가지 중 하나가 필요한 경우 도메인 등록을 다른 등록자에 게 전송 해야 합니다.*
    
## <a name="how-do-i-change-how-my-dns-records-are-managed-in-office-365"></a>Office 365에서 내 DNS 레코드를 관리 하는 방법을 변경 하려면 어떻게 해야 하나요?

### <a name="change-dns-management-to-a-dns-host-outside-office-365"></a>DNS 관리를 Office 365 외부의 DNS 호스트로 변경
   
1. 도메인의 도메인 등록 기관에 로그인 합니다.
    
2. 등록자 웹 사이트에서 이름 서버 레코드를 업데이트 하는 영역을 찾고 도메인의 DNS 호스트를 가리키도록 이름 서버을 업데이트 합니다. DNS 호스트는 종종 도메인 등록자입니다.
    
3. 다음 링크를 통해 도메인 설정 마법사로 이동 합니다.

::: moniker range="o365-worldwide"

4. I관리 센터에서 ** 설정 ** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인 </a> 페이지로 이동하십시오.

::: moniker-end

::: moniker range="o365-germany"

4. I관리 센터에서 ** 설정 ** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank"> 도메인 </a> 페이지로 이동하십시오.

::: moniker-end

::: moniker range="o365-21vianet"

4. I관리 센터에서 ** 설정 ** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank"> 도메인 </a> 페이지로 이동하십시오.

::: moniker-end
    
5. **도메인** 페이지에서 전환 중인 도메인을 선택 하 고 **DNS 관리**를 선택 합니다.
    
6. 도메인 설정 마법사의 **온라인 서비스 설정** 페이지에서 **직접 DNS 레코드 관리**를 선택 하 고 **다음**을 선택 합니다.
    
7. **Dns 설정 업데이트** 페이지에서 마법사가 제안한 dns 레코드를 등록자의 웹 사이트에 추가 합니다. 
    
8. 레코드를 추가한 후에는 Office 365로 돌아와서 **확인**을 선택 합니다.
    

### <a name="change-dns-management-to-office-365"></a>DNS 관리를 Office 365으로 변경

::: moniker range="o365-worldwide"

1. 관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동 합니다.

::: moniker-end

::: moniker range="o365-germany"

1. I관리 센터에서 ** 설정 ** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank"> 도메인 </a> 페이지로 이동하십시오.

::: moniker-end

::: moniker range="o365-21vianet"

1. I관리 센터에서 ** 설정 ** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank"> 도메인 </a> 페이지로 이동하십시오.

::: moniker-end
    
2. **도메인** 페이지에서 전환 중인 도메인을 선택 하 고 **DNS 관리**를 선택 합니다.
    
3. 도메인 설정 마법사의 **온라인 서비스 설정** 페이지에서 **내 온라인 서비스 설정을 선택 합니다. (권장)** 를 선택한 후 **다음**을 선택 합니다.
    
4. 아직 도메인을 확인 하지 않은 경우에는이 단계를 수행 하 여 먼저이 작업을 수행 합니다.
    
5. **DNS 설정 업데이트** 페이지에서 Office 365에 대 한 이름 서버를 나열 합니다. 도메인의 도메인 등록 기관으로 이동 하 여 이름 서버를 Office 365 이름 서버로 업데이트 합니다. 
    
4. 이름 서버를 업데이트 한 후 **1 시간 이상 기다립니다**. 그런 다음 Office 365에서 마법사를 다시 클릭 하 고 **확인**을 선택 합니다.
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a>DNS 공급자가 특정 레코드 종류를 지원 하지 않으면 어떻게 되나요?

자체 DNS 레코드를 관리 하는 경우 DNS 호스트가 Office 365에 필요한 모든 DNS 레코드를 지원 하지 않으면 일부 Office 365 기능이 작동 하지 않습니다. 필요한 모든 DNS 레코드를 지 원하는 등록자에 게 도메인을 전송 하는 것이 좋습니다.
  
필요한 모든 DNS 레코드를 지 원하는 공급자:
  
- Dynadot
    
- eNomCentral
    
- Europe Registry
    
- GoDaddy
    
- 가리키기
    
- MyHosting.com
    
- Name.com
    
- 거의 무료 음성
    
- Nettica
    
- NIC(Network Information Center)
    
- Network Solutions
    
- Register.com
    
 **SRV 레코드가 지원 되지 않으면**다음과 같은 Office 365 기능을 사용할 수 없습니다. 
  
- Outlook Web App과의 비즈니스용 Skype 온라인 IM 및 현재 상태 통합
    
- 다른 조직의 비즈니스용 Skype Online 사용자와의 외부 통신 (페더레이션)
    
- Microsoft 계정 (이전의 Windows Live ID)으로 로그인 한 비즈니스용 Skype Online 사용자와의 공용 인터넷 연결 (PIC)
    
 **여러 CNAME 레코드를 지원 하지 않는 경우** 비즈니스용 Skype Online에 대해 다음 기능 중 하나를 선택 해야 합니다. 
  
- 전자 메일 데스크톱 클라이언트와 모바일 클라이언트는 자동 검색을 사용 하 여 사용자가 서버 이름을 입력 하지 않고도 로그인 할 수 있도록 Exchange Online 서비스를 자동적으로 찾을 수 있습니다.
    
- 비즈니스용 skype Online 데스크톱 클라이언트는 자동 검색을 사용 하 여 사용자가 서버 이름을 입력 하지 않고도 로그인 할 수 있도록 비즈니스용 Skype Online 서비스를 자동적으로 찾을 수 있습니다.
    
- 비즈니스용 skype Online 모바일 클라이언트는 자동 검색을 사용 하 여 사용자가 서버 이름을 입력 하지 않고도 로그인 할 수 있도록 비즈니스용 Skype Online 서비스를 자동적으로 찾을 수 있습니다.
    
 **SPF/TXT 레코드를 지원 하지 않는 경우**다른 사용자가 사용자의 도메인을 사용 하 여 스팸 또는 기타 악성 전자 메일을 보낼 수 있습니다. SPF 레코드는 도메인에서 전자 메일을 보낼 수 있는 권한이 부여 된 서버를 식별 하는 방식으로 작동 합니다. 
  
## <a name="how-do-i-set-or-change-the-default-domain-in-office-365"></a>Office 365에서 기본 도메인을 설정 하거나 변경 하려면 어떻게 하나요?

기본 도메인을 선택 하려면 먼저 Office 365에 추가한 사용자 지정 도메인이 하나 이상 있어야 합니다.

::: moniker range="o365-worldwide"

1. I관리 센터에서 ** 설정 ** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인 </a> 페이지로 이동하십시오.

::: moniker-end

::: moniker range="o365-germany"

1. I관리 센터에서 ** 설정 ** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank"> 도메인 </a> 페이지로 이동하십시오.

::: moniker-end

::: moniker range="o365-21vianet"

1. I관리 센터에서 ** 설정 ** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank"> 도메인 </a> 페이지로 이동하십시오.

::: moniker-end
    
2. **도메인** 페이지에서 새 전자 메일 주소에 대 한 기본값으로 설정할 도메인을 선택 합니다. 
    
3. **기본값으로 설정**을 선택합니다.
    
::: moniker range="o365-worldwide"

*Onmicrosoft.com* 도메인의 이름은 변경할 수 없습니다. 

::: moniker-end

::: moniker range="o365-germany"

*Onmicrosoft.de* 도메인의 이름은 변경할 수 없습니다. 

::: moniker-end

::: moniker range="o365-21vianet"

*Partner.onmschina.cn* 도메인의 이름은 변경할 수 없습니다. 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-office-365"></a>사용자 지정 하위 도메인 또는 여러 도메인을 Office 365에 추가할 수 있나요?

::: moniker range="o365-worldwide"

예로! 하위 도메인을 추가 하려면 등록자의 웹 사이트에서 자체 DNS 설정을 관리 해야 합니다. Microsoft에서 NS 레코드를 사용 하 여 DNS 설정을 관리할 수 있도록 하거나 Microsoft 로부터 도메인을 구매한 경우에는 하위 도메인을 추가할 수 없습니다.

::: moniker-end

::: moniker range="o365-germany"

예로! 하위 도메인을 추가 하려면 등록자의 웹 사이트에서 자체 DNS 설정을 관리 해야 합니다. Microsoft에서 NS 레코드를 사용 하 여 DNS 설정을 관리할 수 있도록 하거나 Microsoft 로부터 도메인을 구매한 경우에는 하위 도메인을 추가할 수 없습니다.

::: moniker-end

::: moniker range="o365-21vianet"

예로! 하위 도메인을 추가 하려면 등록자의 웹 사이트에서 자체 DNS 설정을 관리 해야 합니다. 21Vianet에서 NS 레코드를 사용 하 여 DNS 설정을 관리할 수 있도록 허용 하는 경우 하위 도메인을 추가 하면 안 됩니다.

::: moniker-end

일반적으로 Office 365 구독에는 최대 900 개의 도메인을 추가할 수 있습니다.
  
예를 들어 contoso.com 및 contosomarketing.com 도메인을 추가한 다음 하위 도메인 www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com 등을 추가할 수 있습니다.
  
하위 도메인을 추가 하면 유효성이 확인 되는 상위 도메인을 기반으로 자동으로 확인 됩니다.
  
여러 도메인을 Office 365에 추가 하면 추가한 도메인에서 모든 서비스 (예를 들어 전자 메일)를 호스팅할 수 있습니다.  *도메인의 MX 레코드를 업데이트 하 여 전자 메일을 Office 365로 변경 하면 해당 도메인으로 전송 된 모든 전자 메일이 Office 365로 시작 됩니다.* 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> 이미 Office 365 테 넌 트에 contoso.com 도메인을 추가한 경우에는 다른 Office 365 테 넌 트에 xyz.contoso.com 하위 도메인을 추가할 수도 있습니다. 하위 도메인을 추가할 때 DNS 호스팅 공급자에 TXT 레코드를 추가 하 라는 메시지가 표시 됩니다.

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a>"Onmicrosoft.com" 도메인을 보유 하는 이유는 무엇 인가요?

Office 365에서는 서비스에 등록할 때 *contoso.onmicrosoft.com*와 같은 도메인을 만듭니다. 등록할 때 만드는 사용자 ID에는 *alan@contoso.onmicrosoft.com*와 같은 도메인이 포함 됩니다. 
  
 **전자 메일을 *\@alan contoso.com*:** 으로 지정 하려면 [도메인을 구입](../get-help-with-domains/buy-a-domain-name.md) 하거나 사용자 및 도메인을 이미 소유 하 고 있는 경우 [Office 365에 추가](add-domain.md) 의 단계를 수행 하세요. 
  
- **등록 후에는 onmicrosoft 도메인의 이름을 바꿀 수 없습니다.** 예를 들어 선택한 초기 도메인이 fourthcoffee.onmicrosoft.com 인 경우 fabrikam.onmicrosoft.com로 변경할 수 없습니다. 다른 onmicrosoft.com 도메인을 사용 하려면 Office 365에서 새 구독을 시작 해야 합니다. 
    
- **팀 사이트 URL의 이름은 바꿀 수 없습니다.** 팀 사이트 URL은 onmicrosoft.com 도메인 이름을 기반으로 합니다. 아쉽게도 SharePoint Online 아키텍처의 작동 방식 때문에 팀 사이트의 이름을 바꿀 수 없습니다. 
    
- **Onmicrosoft 도메인은 제거할 수 없습니다.** Office 365에서는 구독을 위해 백그라운드에서 사용 되기 때문에이를 유지 해야 합니다. 하지만 사용자 지정 도메인을 추가한 후에는 직접 도메인을 사용할 필요가 없습니다. 
    
도메인을 추가한 후에도 초기 onmicrosoft.com 도메인을 계속 사용할 수 있습니다. 여전히 전자 메일 및 기타 서비스에 대해 작동 하기 때문에 선택 해야 합니다.
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a>"Onmicrosoft.de" 도메인을 보유 하는 이유는 무엇 인가요?

Office 365에서는 서비스에 등록할 때 *contoso.onmicrosoft.de*와 같은 도메인을 만듭니다. 등록할 때 만드는 사용자 ID에는 *alan@contoso.onmicrosoft.de*와 같은 도메인이 포함 됩니다. 
  
 **전자 메일을 *alan@contoso.de*같이 표시 하려면** [도메인을 구입](../get-help-with-domains/buy-a-domain-name.md) 하거나 [사용자와 도메인을 이미 소유한 경우 Office 365에 추가](add-domain.md) 의 단계를 따르세요. 
  
- **등록 후에는 onmicrosoft 도메인의 이름을 바꿀 수 없습니다.** 예를 들어 선택한 초기 도메인이 fourthcoffee.onmicrosoft.de 인 경우 fabrikam.onmicrosoft.de로 변경할 수 없습니다. 다른 onmicrosoft.de 도메인을 사용 하려면 Office 365에서 새 구독을 시작 해야 합니다. 
    
- **팀 사이트 URL의 이름은 바꿀 수 없습니다.** 팀 사이트 URL은 onmicrosoft.de 도메인 이름을 기반으로 합니다. 아쉽게도 SharePoint Online 아키텍처의 작동 방식 때문에 팀 사이트의 이름을 바꿀 수 없습니다. 
    
- **Onmicrosoft 도메인은 제거할 수 없습니다.** Office 365에서는 구독을 위해 백그라운드에서 사용 되기 때문에이를 유지 해야 합니다. 하지만 사용자 지정 도메인을 추가한 후에는 직접 도메인을 사용할 필요가 없습니다. 
    
도메인을 추가한 후에도 초기 onmicrosoft.de 도메인을 계속 사용할 수 있습니다. 여전히 전자 메일 및 기타 서비스에 대해 작동 하기 때문에 선택 해야 합니다.
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a>비영리 또는 학력 상태를 확인 하려면 어떻게 해야 하나요?

1. [관리 센터](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791.aspx) 에서 **설치** 를 선택 하 여 마법사를 시작 합니다. (먼저 Office 365에 로그인 해야 합니다.) 
    
2. 학교 관리자가 되도록 하려면 Office 365에서 **관리자 권한으로 관리** 옵션을 선택 합니다. 
    
3. 도메인에 대 한 DNS 호스트 웹 사이트에 TXT DNS 레코드를 추가 하 라는 메시지가 표시 됩니다. 다음과 같은 이유 때문입니다. DNS 호스트에 로그인 하 고 도메인에 대 한 레코드를 추가 하 여 Office 365에서 도메인 이름을 소유 하 고 있음을 증명 합니다.
    
4. 레코드를 추가한 후에는 Office 365 포털로 돌아가 Office 365에서 확인할 수 있도록 해당 포털을 추가 했는지 확인 합니다.
    
비영리이 있고 Office 365을 받으려면 어떻게 해야 하나요? [조직에서](https://www.microsoft.com/en-us/nonprofits/eligibility) 서비스를 확인 한 다음 등록 합니다. 
  
학교에서 관리자 되는 것에 대해 자세히 알고 싶으십니까? 를 [참고](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
)하세요.
  
## <a name="can-i-pilot-office-365-with-just-a-few-email-addresses-from-my-custom-domain"></a>사용자 지정 도메인의 몇 가지 전자 메일 주소만 사용 하 여 Office 365를 파일럿 할 수 있나요?

다음과 같은 제한이 있습니다.
  
- 현재 전자 메일 공급자가 전자 메일 전달을 제공 해야 합니다.
    
- Office 365에서 이러한 레코드를 관리 하는 것이 아니라 DNS 호스팅 공급자에서 Office 365 관련 DNS 레코드를 관리 해야 합니다. 이에 대 한 자세한 내용은 자신만의 DNS 레코드를 관리 하려는 경우 Office 365에 도메인 추가를 참조 하세요.
    
- 일부 Office 365 기능은 사용할 수 없습니다.
- 사용자는 다른 전자 메일 공급자의 사용자에 대 한 약속 있음/없음 정보를 볼 수 없습니다.
- 관리자는 모든 사용자의 계정을 한 위치에서 관리할 수 없습니다.
- 사용자가 Office 365 스팸 필터링을 사용 하지 못할 수 있습니다.

### <a name="how-to-set-up-an-office-365-pilot"></a>Office 365 파일럿을 설정 하는 방법
    
1. Microsoft 365 관리 센터에 로그인 합니다.
    
    1. 회사 또는 학교 계정을 사용하여 Office 365에 로그인합니다.
        
    2. **설정** \> **도메인**으로 이동 합니다. 
    
2. 사용 하려는 도메인을 소유 하 고 있는지 확인
    
    1. **도메인** 페이지에서 **도메인 추가**를 선택 합니다. 
        
    2. 패널에서 도메인 (이 예에서는 cohowinery.com)을 입력 하 고 **다음**을 선택 합니다. 
        
    3. 도메인 **확인** 페이지에서 단계별 지침을 따릅니다. 
        
    4. 드롭다운 목록에서 DNS 호스팅 공급자를 선택 하 고 지침에 따라 도메인을 소유 하 고 있음을 표시 합니다.
        
    5. **확인**을 선택 합니다. DNS 변경 사항을 적용 하기 위해 몇 분에서 72 시간까지 소요 됩니다. 
        
    6. 확인이 성공 하면 DNS 레코드를 수정 하 라는 메시지가 표시 됩니다.
    
3. Exchange Online에서 도메인을 공유로 표시
    
    1. EAC ( **Exchange 관리 센터** )로 이동 합니다. 
        
    2. **메일 흐름** 섹션에서 **허용 도메인**을 선택 합니다. 
        
    3. 수정 하려는 도메인을 두 번 클릭 합니다.
        
    4. 열려 있는 창에서 **내부 릴레이**를 선택 합니다. 
        
    5. **저장**을 선택합니다. 이 설정을 적용 하려면 몇 분 정도 걸릴 수 있습니다. 
    
4. 필요에 따라 기존 전자 메일 서버 차단 해제
    
    1. Office 365에서는 스팸 보호를 위해 EOP (Exchange Online Protection)를 사용 합니다. EOP에서 현재 메일 서버에 의해 전달 되는 대량의 스팸 볼륨이 감지 되 면 전달이 차단 될 수 있으며,이로 인해 착신 전환 되지 않습니다. 다른 전자 메일 공급자가 사용 하는 스팸 방지 기능이 확실 한 경우에는 해당 서버를 Office 365에서 허용 목록 수 있습니다. 그러나 이렇게 하면 원래 서버를 통해 수신 되는 모든 스팸 메일이 Office 365 사서함으로 전달 되 고, Office 365에서 스팸을 차단 하는 정도를 평가할 수 없습니다.
    
    2. EAC (Exchange 관리 센터)로 이동 합니다.
        
    3. EAC에서 **보호**를 선택 하 고 **연결 필터**를 선택 합니다. 
        
    4. **IP 허용 목록**에서를 선택 **+** 하 고 현재 전자 메일 공급자 로부터 가져올 수 있는 메일 서버 IP 주소를 추가 합니다. 
    
5. 사용자 계정 만들기 및 기본 (회신) 주소 설정
    
    1. Microsoft 365 관리 센터로 이동합니다.
        
    2. 왼쪽 탐색 모음에서 **사용자** \> **활성 사용자**를 선택 합니다. 
        
    3. 사용자 계정을 만듭니다.
        
    4. 각 계정에 대해 **+ (새로 만들기)** 를 선택 하 고 필요한 정보를 입력 합니다. 
        
    5. 사용자의 전자 메일을 현재와 동일 하 게 유지 하려면 **사용자 이름** 필드가 사용자의 기존 전자 메일 주소와 정확히 일치 해야 합니다. 
        
    6. 사용자 이름 옆의 드롭다운 목록에서 사용자 지정 도메인 이름을 선택 합니다.
        
    7. 닫기 **만들기** \> **Close**를 선택 합니다. 
        
6. DNS 호스팅 공급자에서 DNS 레코드 업데이트
    
    1. DNS 호스팅 공급자의 웹 사이트에 로그인 하 고 dns [호스팅 공급자에서 Office 365 단계](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)에 해당 하는 Dns 레코드 만들기를 따릅니다. **다음 예외를 확인 합니다.**
    
        1. 새 MX 레코드를 만들거나 기존 MX 레코드를 변경 하지 않습니다.
            
        2. 이전 전자 메일 공급자에 대 한 SPF (보낸 사람 정책 프레임 워크) 레코드가 이미 있는 경우 Exchange Online에 대 한 새 SPF (TXT) 레코드를 만드는 대신 현재 TXT 레코드에 "include:"를 추가 하기만 하면 됩니다. 예를 들어 "v = spf1 mx에는:adatum를 포함 합니다.
            
        3. SPF 레코드가 아직 없는 경우에는 Office 365에서 권장 하는 하나를 수정 하 여 현재 전자 메일 공급자에 대 한 도메인을 포함 하 고 spf.protection.outlook.com를 추가 합니다. 이렇게 하면 두 전자 메일 시스템에서 보내는 메시지가 모두 승인 됩니다.
            
7. 현재 공급자에서 전자 메일 전달 설정
    
    1. 현재 전자 메일 공급자에서 사용자 전자 메일 계정에 대 한 착신 전환을 onmicrosoft.com 도메인으로 설정 합니다.
        
    2. 사용자 A의 사서함이 usera@yourcompany.onmicrosoft.com로 전달 되어야 함
        
    3. 사용자 B의 사서함이 userb@yourcompany.onmicrosoft.com로 전달 되어야 함
        
    4. 이 단계를 완료 하면 다음이 수행 됩니다.
        
    5. Usera@yourcompany.com 및 userb@yourcompany.com에 게 전송 되는 모든 메일은 Office 365에서 사용할 수 있습니다.
    
    6. 참고:
        
        - 착신 전환 설정에 대 한 정확한 단계는 현재 전자 메일 공급자에 게 문의 하세요.
            
        - 현재 전자 메일 공급자에 메시지 복사본을 보관할 필요가 없습니다.
            
        - 대부분의 공급자는 보낸 사람의 회신 주소를 그대로 두고 전자 메일을 전달 하 여 회신이 원래 보낸 사람에 게 이동 하도록 합니다.
    
8. 메일 흐름 테스트
    
    1. 사용자 A의 자격 증명을 사용 하 여 Outlook Web App에 로그인 합니다.
        
    2. 다음 테스트를 수행 합니다.
        
    3. 로컬 Microsoft 전자 메일을 테스트 합니다. 예를 들어 사용자 B에 게 전자 메일을 보냅니다. 이 전자 메일을 즉시 배달 해야 합니다. 이 시나리오에서는 Office 365에서 사서함을 로컬으로 인식 하기 때문에 메시지가 원래 서버에서 사용자 B의 사서함으로 라우팅되지 않습니다.
        
    4. 다른 전자 메일 시스템에 있는 사람에 대 한 전자 메일을 테스트 합니다. 예를 들어 사용자 C에 게 전자 메일을 보냅니다. 이 전자 메일은 원래 메일 서버에서 사용자 C의 사서함으로 배달 됩니다.
        
    5. 외부 계정에서 또는 다른 전자 메일 시스템의 직원 전자 메일 계정에서 다른 전자 메일 시스템에 대 한 전달이 제대로 설정 되었는지 확인 합니다. 예를 들어 사용자 C의 origninal 서버 계정 또는 Hotmail 계정에서 사용자 A에 게 전자 메일을 보내 사용자 A의 Office 365 사서함에 도착 하는지 확인 합니다.
        
9. 사서함 콘텐츠 이동
    
    1. 사용자는 두 명만 이동할 수 있으며, User A와 User B가 Outlook을 이미 사용 하 고 있으므로 전자 메일을 이동 하려면 이전을 엽니다. PST 파일을 outlook 데이터 파일 (.pst)에서 Outlook 항목 가져오기에 표시 된 대로 새 Outlook 프로필의 메시지, 일정 항목, 연락처 등을 복사 하는 중입니다. Office 365 사서함의 적절 한 위치에 구성 된 항목은 모든 장치에서 어디에 나 액세스할 수 있습니다.
        
    2. 더 많은 사서함이 포함 되거나 직원이 아직 Outlook을 사용 하 고 있지 않은 경우 Exchange 관리 센터에서 사용할 수 있는 마이그레이션 도구를 사용할 수 있습니다. 시작 하려면 Exchange 관리 센터로 이동 하 여 IMAP 서버에서 Exchange Online 사서함으로 전자 메일 마이그레이션의 지침을 따르세요.
    
