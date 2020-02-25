---
title: Office 365에서 도메인 이름 구입
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1561140a-16a9-4a02-822d-a989250e479d
description: Office 365에서 도메인 이름을 구입 하는 방법을 알아봅니다.
ms.custom: okr_smb
ms.openlocfilehash: 8b2b23e2e699723d54ecb7ca2807296641178664
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42255163"
---
# <a name="buy-a-domain-name-in-office-365"></a>Office 365에서 도메인 이름 구입

 *도메인을 추가, 수정 또는 제거 하려면 [비즈니스 또는 기업 계획](https://products.office.com/business/office)의 **전역 관리자** **여야 합니다** . 이러한 변경 내용은 전체 테 넌 트에 영향을 미치며 *사용자 지정 된 관리자* 또는 *일반 사용자* 는 이러한 변경 작업을 수행할 수 없습니다.*  

 원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.md)** 하세요. 
  
### <a name="sign-in-and-go-to-settings--domains--buy-a-domain"></a>로그인 하 고 설정 \> 도메인 \> 으로 이동 하 여 도메인 구입

1. 관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동 합니다.
    
3. **도메인** 페이지에서 **도메인 구입**을 선택 합니다.
    
도메인의 다음 최상위 도메인에서 선택할 수 있습니다.
  
- biz
    
- .com
    
- . 정보
    
- . me
    
- . mobi
    
- net
    
- org
    
- tv
    
- . co.uk
    
- org.uk
    

> [!NOTE]
> **도메인 구입**을 선택 하면 microsoft 파트너를 통해 테 넌 트를 구매/관리 하는 경우 microsoft 파트너의 웹 사이트로 리디렉션될 수 있습니다.

### <a name="domain-privacy"></a>도메인 개인 정보
Microsoft는 도메인 구입과 함께 무료 도메인 개인 정보 구독을 제공 합니다. 이렇게 하면 ICANN private을 사용 하 여 도메인 등록에 대 한 연락처 정보가 연결 됩니다. [더 알아보세요.](https://whois.icann.org/en/privacy-and-proxy-services)
  
### <a name="buy-a-domain-from-another-domain-registrar"></a>다른 도메인 등록 기관에서 도메인 구입
[Godaddy](https://www.godaddy.com)이외의 다른 도메인 등록 기관에서 도메인을 구입 하려면 자동 설치 (도메인 연결)를 지 원하는 아래를 사용 하는 것이 좋습니다. 
  
- [1&amp;1GB 이상 os](https://www.1and1.com/)
- [WordPress](https://www.wordpress.com) 

   
### <a name="transfer-your-domain-to-a-different-domain-registrar"></a>다른 도메인 등록 기관으로 도메인 전송

도메인이 필요한 모든 DNS 레코드를 지원하지 않는 공급자에서 관리되는 경우 해당 도메인을 다른 등록 기관으로 전송할 수 있습니다. 도메인을 전송하면 도메인 이름을 갱신하고 유지하기 위해 비용을 지불하는 대상이 변경됩니다.
  
도메인을 이동하려는 등록 기관에서 전송을 요청합니다. 해당 웹 사이트에서 **DNS 전송** 등의 옵션을 확인합니다. 변경한 후 인터넷에서 업데이트되는 데에는 며칠이 걸릴 수 있다는 점에 유의하세요.
 



::: moniker range="o365-21vianet"
## <a name="how-to-buy-a-domain-for-office-365-operated-by-21vianet"></a>21Vianet에서 운영하는 Office 365에 대한 도메인 구입 방법



고유한 도메인이 아직 없다면 도메인 이름 등록 기관이나 도메인 판매자 또는 현재 인터넷 제공업체에서 온라인으로 손쉽게 도메인을 구입할 수 있습니다. 21Vianet에서 운영하는 Office 365에 등록하면 contoso.partner.onmschina.cn 같은 도메인 이름이 제공됩니다. 하지만 fourthcoffee.com 같은 사용자 지정 도메인 이름도 사용할 수 있습니다.
  
Office 365에서 도메인을 설정하려면 사용자가 도메인을 소유하고 있어야 하며 도메인의 일부 DNS 레코드를 변경해야 합니다.
  
> [!CAUTION]
> 일부 도메인 등록 기관이나 DNS 호스팅 공급자는 Office 365에 필요한 일부 DNS 레코드를 만드는 것을 허용하지 않습니다. 다음 나열된 호스팅 공급자는 필요한 레코드를 모두 지원합니다. 다른 호스팅 공급자를 사용하는 것을 고려하고 있다면 [Service limitations when your hosting provider does not support SRV, CNAME, TXT, or redirection](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77). 
  
도메인 등록 기관에서 도메인을 등록한 후에는 Office 365에 관리자로 로그인하고 전자 메일 주소 및 기타 서비스에 해당 도메인을 사용할 수 있도록 설정합니다.
  
> [!NOTE]
> The SharePoint Online Public Website information in this article only applies if your organization purchased Office 365 prior to March 9, 2015. 

## <a name="domain-registrars-that-support-all-dns-records-required-for-office-365"></a>Office 365에 필요한 모든 DNS 레코드를 지원하는 도메인 등록 기관

- [Oray](https://oray.com/)
    
- [HiChina](https://www.hichina.com/)
    
- [east.net](http://www.east.net/)
    
- [BIZCN](https://www.bizcn.com/)
    
::: moniker-end

## <a name="related-articles"></a>관련 문서

[Office 365에 도메인 추가](../setup/add-domain.md)

[도메인 FAQ](../setup/domains-faq.md)

[Office 365 도메인에 대 한 도움말 보기](get-help-with-domains.md)
