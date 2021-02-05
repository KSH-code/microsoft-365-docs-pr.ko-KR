---
title: 도메인 이름 구매
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1561140a-16a9-4a02-822d-a989250e479d
description: Microsoft 365에서 도메인 이름을 구입하는 방법을 학습합니다.
ms.openlocfilehash: 40fc44dfa3bc3e608b590157b7db423302af748d
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50113966"
---
# <a name="buy-a-domain-name"></a>도메인 이름 구매

::: moniker range="o365-21vianet"

> [!NOTE]
> 관리 센터가 변경되고 있습니다. 사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)를 참조하세요.

::: moniker-end

 *도메인을 추가, 수정 또는  제거하려면  비즈니스 또는 엔터프라이즈 계획의 전역 관리자 [되어야 합니다.](https://products.office.com/business/office) 이러한 변경 내용은 전체 테넌트,   사용자 지정된 관리자 또는 일반 사용자에게 영향을 미치며 이러한 변경은 할 수 없습니다.*  

 원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.yml)** 하세요. 
  
### <a name="sign-in-and-go-to-settings--domains--buy-a-domain"></a>로그인하고 설정 \> 도메인 \> 구입 도메인으로 이동

1. I관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인</a> 페이지로 이동하십시오.
    
3. On the **Domains** page, select **Buy domain**.
    
도메인의 다음 최상위 도메인에서 선택할 수 있습니다.
  
- .biz
    
- .com
    
- .info
    
- .me
    
- .mobi
    
- .net
    
- .org
    
- .tv
    
- .co.uk
    
- org.uk
    

> [!NOTE]
> 도메인 구입을 **선택하면** Microsoft 파트너를 통해 테넌트가 구매/관리되는 경우 Microsoft 파트너의 웹 사이트로 리디렉션될 수 있습니다.

### <a name="domain-privacy"></a>도메인 개인 정보
도메인 구입 시 무료 도메인 개인 정보 구독을 제공합니다. 그러면 연락처 정보가 ICANN 비공개로 도메인 등록에 첨부됩니다. [더 알아보세요.](https://whois.icann.org/en/privacy-and-proxy-services)
  
### <a name="buy-a-domain-from-another-domain-registrar"></a>다른 도메인 등록 기관에서 도메인 구입
[GoDaddy가](https://www.godaddy.com)외의 도메인 등록 기관에서 도메인을 구입하려면 자동 설정(Domain Connect)을 지원하는 아래의 도메인을 사용하는 것이 좋습니다. 
  
- [1 &amp; 1 IONOS](https://www.1and1.com/)
- [WordPress](https://www.wordpress.com) 

   
### <a name="transfer-your-domain-to-a-different-domain-registrar"></a>다른 도메인 등록 기관으로 도메인 전송

도메인이 필요한 모든 DNS 레코드를 지원하지 않는 공급자에서 관리되는 경우 해당 도메인을 다른 등록 기관으로 전송할 수 있습니다. 도메인을 전송하면 도메인 이름을 갱신하고 유지하기 위해 비용을 지불하는 대상이 변경됩니다.
  
도메인을 이동하려는 등록 기관에서 전송을 요청합니다. 해당 웹 사이트에서 **DNS 전송** 등의 옵션을 확인합니다. 변경한 후 인터넷에서 업데이트되는 데에는 며칠이 걸릴 수 있다는 점에 유의하세요.
 



::: moniker range="o365-21vianet"
## <a name="how-to-buy-a-domain-for-office-365-operated-by-21vianet"></a>21Vianet에서 운영하는 Office 365에 대한 도메인 구입 방법



고유한 도메인이 아직 없다면 도메인 이름 등록 기관이나 도메인 판매자 또는 현재 인터넷 제공업체에서 온라인으로 손쉽게 도메인을 구입할 수 있습니다. 21Vianet에서 운영하는 Office 365에 등록하면 contoso.partner.onmschina.cn 같은 도메인 이름이 제공됩니다. 하지만 fourthcoffee.com 같은 사용자 지정 도메인 이름도 사용할 수 있습니다.
  
Microsoft 365에서 도메인을 설정하려면 도메인을 소유하고 도메인의 일부 DNS 레코드를 변경해야 합니다.
  
> [!CAUTION]
> 일부 도메인 등록 기관 또는 DNS 호스팅 공급자는 Microsoft 365에 필요한 모든 DNS 레코드를 만들 수 없습니다. 다음 나열된 호스팅 공급자는 필요한 레코드를 모두 지원합니다. 다른 호스팅 공급자를 사용하는 것을 고려하고 있다면 [Service limitations when your hosting provider does not support SRV, CNAME, TXT, or redirection](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77). 
  
도메인 등록 기관에서 도메인을 등록한 후 관리자로 Microsoft 365에 로그인하고 전자 메일 주소 및 기타 서비스와 함께 사용할 수 있도록 도메인을 설정합니다.
  
> [!NOTE]
> 이 문서의 SharePoint Online 공개 웹 사이트 정보는 조직에서 2015년 3월 9일 이전에 Microsoft 365를 구입한 경우만 적용됩니다. 

## <a name="domain-registrars-that-support-all-dns-records-required-for-microsoft-365"></a>Microsoft 365에 필요한 모든 DNS 레코드를 지원하는 도메인 등록 기관

- [Oray](https://oray.com/)
    
- [HiChina](https://www.hichina.com/)
    
- [east.net](http://www.east.net/)
    
- [BIZCN](https://www.bizcn.com/)
    
::: moniker-end

## <a name="related-articles"></a>관련 문서

[Microsoft 365에 도메인 추가](../setup/add-domain.md)

[도메인 FAQ](../setup/domains-faq.yml)

[DNS 레코드를 업데이트하여 현재](https://docs.microsoft.com/microsoft-365/admin/dns/update-dns-records-to-retain-current-hosting-provider)호스팅 공급자와 함께 웹 사이트를 유지하세요.
