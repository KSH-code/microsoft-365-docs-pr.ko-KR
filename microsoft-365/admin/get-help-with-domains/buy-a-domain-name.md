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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1561140a-16a9-4a02-822d-a989250e479d
description: 2016에서 도메인 이름을 구입하는 Microsoft 365.
ms.openlocfilehash: 4d2a6546703c93f4b4d6a55e82c309120e384ead
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59184676"
---
# <a name="buy-a-domain-name"></a>도메인 이름 구매

> [!NOTE]
> 조직에서 중국의 Office 365 운영하는 21Vianet을 사용하는 경우 [중국의 21Vianet에서](#how-to-buy-a-domain-for-office-365-operated-by-21vianet)운영하는 Office 365 도메인을 구입하는 방법을 참조합니다.

 *도메인을 추가, 수정 또는 제거하려면  **비즈니스** 또는 엔터프라이즈 계획의 전역 관리자 [되어야 합니다.](https://products.office.com/business/office) 이러한 변경 내용은 전체 테넌트,   사용자 지정된 관리자 또는 일반 사용자에게 영향을 미치며 이러한 변경을 할 수 없습니다.*  

 원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.yml)** 하세요. 
  
## <a name="sign-in-and-go-to-settings--domains--buy-a-domain"></a>로그인한 후 도메인 설정 \> 도메인 \> 구입으로 이동

1. I관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인</a> 페이지로 이동하십시오.
    
3. 도메인 **페이지에서** 도메인 **구입을 선택합니다.**
    
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
> 도메인 **구입을 선택하면** Microsoft 파트너를 통해 테넌트가 구매/관리되는 경우 Microsoft 파트너의 웹 사이트로 리디렉션될 수 있습니다.

## <a name="domain-privacy"></a>도메인 개인 정보
도메인 구입 시 도메인 개인 정보 구독을 무료로 제공합니다. 그러면 연락처 정보가 ICANN 비공개로 도메인 등록에 첨부됩니다. [더 알아보세요.](https://whois.icann.org/en/privacy-and-proxy-services)
  
## <a name="buy-a-domain-from-another-domain-registrar"></a>다른 도메인 등록 기관에서 도메인 구입
[GoDaddy가](https://www.godaddy.com)다른 도메인 등록 기관에서 도메인을 구입하려는 경우 자동 설정(Domain 커넥트)을 지원하는 도메인을 사용하는 것이 커넥트. 
  
- [1 &amp; 1 IONOS](https://www.1and1.com/)
- [WordPress](https://www.wordpress.com) 

   
## <a name="transfer-your-domain-to-a-different-domain-registrar"></a>다른 도메인 등록 기관으로 도메인 전송

도메인이 필요한 모든 DNS 레코드를 지원하지 않는 공급자에서 관리되는 경우 해당 도메인을 다른 등록 기관으로 전송할 수 있습니다. 도메인을 전송하면 도메인 이름을 갱신하고 유지하기 위해 비용을 지불하는 대상이 변경됩니다.
  
도메인을 이동하려는 등록 기관에서 전송을 요청합니다. 해당 웹 사이트에서 **DNS 전송** 등의 옵션을 확인합니다. 변경한 후 인터넷에서 업데이트되는 데에는 며칠이 걸릴 수 있다는 점에 유의하세요.


::: moniker range="o365-21vianet"

## <a name="how-to-buy-a-domain-for-office-365-operated-by-21vianet"></a>21Vianet에서 운영하는 Office 365에 대한 도메인 구입 방법

고유한 도메인이 아직 없다면 도메인 이름 등록 기관이나 도메인 판매자 또는 현재 인터넷 제공업체에서 온라인으로 손쉽게 도메인을 구입할 수 있습니다. 21Vianet에서 운영하는 Office 365에 등록하면 contoso.partner.onmschina.cn 같은 도메인 이름이 제공됩니다. 하지만 fourthcoffee.com 같은 사용자 지정 도메인 이름도 사용할 수 있습니다.
  
도메인에서 도메인을 Microsoft 365 도메인을 소유하고 도메인의 DNS 레코드 중 일부를 변경해야 합니다.
  
> [!CAUTION]
> 일부 도메인 등록 기관 또는 DNS 호스팅 공급자는 도메인 등록 기관에 필요한 모든 DNS 레코드를 만들 수 Microsoft 365. 다음 나열된 호스팅 공급자는 필요한 레코드를 모두 지원합니다. 다른 호스팅 공급자를 사용하는 것을 고려하고 있다면 [Service limitations when your hosting provider does not support SRV, CNAME, TXT, or redirection](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77). 
  
도메인 등록 기관에서 도메인을 등록한 후 관리자로 Microsoft 365 도메인을 설정하여 전자 메일 주소 및 기타 서비스와 함께 사용할 수 있도록 합니다.
  
> [!NOTE]
> 이 SharePoint 온라인 공개 웹 사이트 정보는 조직이 2015년 3월 9일 이전에 Microsoft 365 구매한 경우 적용됩니다. 

### <a name="domain-registrars-that-support-all-dns-records-required-for-microsoft-365"></a>도메인 등록 기관에 필요한 모든 DNS 레코드를 지원하는 Microsoft 365

- [Oray](https://oray.com/)
    
- [HiChina](https://www.hichina.com/)
    
- [east.net](http://www.east.net/)
    
- [BIZCN](https://www.bizcn.com/)
    
::: moniker-end

## <a name="related-content"></a>관련 콘텐츠

[도메인을 도메인에](../setup/add-domain.md) Microsoft 365(문서)\
[도메인 FAQ](../setup/domains-faq.yml)(문서)\
[DNS 레코드를 업데이트하여 웹 사이트를](../dns/update-dns-records-to-retain-current-hosting-provider.md) 현재 호스팅 공급자와 함께 유지(문서)