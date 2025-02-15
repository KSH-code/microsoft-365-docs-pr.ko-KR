---
title: 커넥트 CLOUDflare에서 DNS 레코드를 Microsoft 365
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: Microsoft용 Cloudflare에서 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대한 DNS 레코드를 설정하는 방법을 학습하세요.
ms.openlocfilehash: 80c7a3dded1da9c52f0baf215fcd1c39cd90d4f3
ms.sourcegitcommit: da11ffdf7a09490313dfc603355799f80b0c60f9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/26/2021
ms.locfileid: "60586852"
---
# <a name="connect-your-dns-records-at-cloudflare-to-microsoft-365"></a>커넥트 CLOUDflare에서 DNS 레코드를 Microsoft 365

 원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.yml)** 하세요. 

DNS 호스팅 공급자로 Cloudflare를 사용하고 있는 경우 이 문서의 단계에 따라 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online에 대한 DNS 레코드를 설정하세요.

## <a name="before-you-begin"></a>시작하기 전에

도메인에 대한 DNS 레코드를 설정하는 두 가지 옵션이 있습니다.

- [**도메인 커넥트**](#use-domain-connect-to-verify-and-set-up-your-domain) 다른 전자 메일 서비스 공급자와 함께 도메인을 설정하지 않은 경우 Domain 커넥트 단계를 사용하여 도메인 공급자와 함께 사용할 새 도메인을 자동으로 확인하고 Microsoft 365. 

    또는

- [**수동 단계 사용**](#create-dns-records-with-manual-setup) 아래 수동 단계를 사용하여 도메인을 확인하고 도메인 등록 기관에 추가할 레코드를 언제 및 어떤 레코드로 추가할지 선택하세요. 예를 들어 편의상 새 MX(메일) 레코드를 설정할 수 있습니다. 

## <a name="use-domain-connect-to-verify-and-set-up-your-domain"></a>Domain 커넥트 사용하여 도메인 확인 및 설정

다음 단계에 따라 도메인을 사용하여 Cloudflare 도메인을 자동으로 확인하고 Microsoft 365.

1. 다음 Microsoft 365 관리 센터 도메인 **설정** 를 선택하고 설정할  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"></a>도메인을 선택합니다.

1. 세 개의 점(추가 작업)을 > **시작을 선택합니다.**

    :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-2.png" alt-text="설치 시작을 선택합니다.":::

1. On the How do you want to connect your domain? 페이지, **계속을 선택합니다.**   

1. DNS 레코드 추가 페이지에서 DNS 레코드 **추가를 선택합니다.**

1. Cloudflare 로그인 페이지에서 계정에 로그인하고 **승인을 선택합니다.**
    
    그러면 도메인에 대한 도메인 설정이 Microsoft 365. 

## <a name="create-dns-records-with-manual-setup"></a>수동 설정으로 DNS 레코드 만들기

Cloudflare에서 이러한 레코드를 추가하고 나면 도메인이 클라우드 서비스에서 Microsoft 365 설정됩니다.

> [!NOTE]
>  일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 
  
### <a name="change-your-domains-nameserver-ns-records"></a>도메인의 NS(이름 서버) 레코드 변경

> [!IMPORTANT]
> 이 절차는 도메인을 구입하고 등록한 도메인 등록 기관에서 수행해야 합니다. 
  
Cloudflare에 등록할 때 Cloudflare 설치 프로세스를 사용하여 도메인을 추가했습니다. 
  
추가한 도메인은 Cloudflare 또는 별도의 도메인 등록 기관에서 구입한 것입니다. 도메인에서 도메인에 대한 DNS 레코드를 Microsoft 365 먼저 도메인 등록 기관에서 이름 서버를 변경하여 Cloudflare 이름 서버를 사용할 수 있도록 해야 합니다.
  
도메인 등록 기관 웹 사이트에서 도메인 이름 서버를 직접 변경하려면 다음 단계를 따릅니다.
  
1. 도메인 등록 기관의 웹 사이트에서 도메인의 이름 서버를 편집할 수 있는 영역을 찾습니다.
    
2. 다음 표의 값을 사용하여 이름 서비스 레코드를 두 개 만들거나 이러한 값과 일치하게 기존 이름 서비스 레코드를 편집합니다.
    
    |||
    |:-----|:-----|
    |첫 번째 이름 서버  <br/> |Cloudflare에서 제공하는 이름 서비스 값을 사용 합니다.  <br/> |
    |두 번째 이름 서버  <br/> |Cloudflare에서 제공하는 이름 서비스 값을 사용 합니다.  <br/> |
   
    > [!TIP]
    > You should use at least two name server records. 나열된 다른 이름 서버가 있는 경우 해당 서버를 삭제해야 합니다. 
  
3. 변경 내용을 저장합니다.
    
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. 그런 다음 Microsoft 전자 메일 및 기타 서비스가 모두 도메인에서 작동하게 설정됩니다. 
  
### <a name="add-a-txt-record-for-verification"></a>확인을 위해 TXT 레코드 추가

Microsoft에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft에 도메인을 소유하고 있음을 증명할 수 있습니다.
  
> [!NOTE]
> 이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다. 
  
1. 시작하려면 이 링크를 사용하여 Cloudflare의 도메인 [페이지로 이동합니다.](https://www.cloudflare.com/a/login) 먼저 로그인하라는 메시지가 표시됩니다.
  
1. 홈 페이지에서 업데이트할 도메인을 선택합니다. 
 
    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-1.png" alt-text="업데이트할 도메인을 선택합니다.":::
 
1. 도메인의 개요 페이지에서 DNS 를 **선택합니다.**

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-2.png" alt-text="DNS를 선택합니다.":::
  
1. DNS 관리 페이지에서 **+레코드** 추가를 선택한 다음 테이블의 값을 입력하거나 복사하여 붙여넣습니다. 
    
    | **유형** | **이름** | **TTL** | **콘텐츠** |
    |:-----|:-----|:-----|:----|
    |TXT  <br/> |@  <br/> |30분  <br/> |MS=ms *XXXXXXXX*  <br/> **참고:** 이 값은 예시입니다. 여기에는 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다. [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)    |
    
1. **저장** 을 선택합니다.
  
1. 방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.
    
이제 도메인 등록 기관의 사이트에 레코드를 추가한 후 Microsoft로 돌아가 레코드를 검색합니다. Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.
  
다음을 통해 레코드를 Microsoft 365.
  
1. 관리 센터에서 도메인 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**로 이동하세요.**</a>
    
1. 도메인 페이지에서 확인할 도메인을 선택하고 설정 시작 **을 선택합니다.** 

    :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-2.png" alt-text="설치 시작을 선택합니다.":::

1. 계속을 **선택합니다.**
  
1. **도메인 확인** 페이지에서 **확인** 을 선택합니다.
    
> [!NOTE]
> 일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 
    
### <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드 추가하기

1. 시작하려면 이 링크를 사용하여 Cloudflare의 도메인 [페이지로 이동합니다.](https://www.cloudflare.com/a/login) 먼저 로그인하라는 메시지가 표시됩니다.
  
2. 홈 페이지에서 업데이트할 도메인을 선택합니다. 
 
    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-1.png" alt-text="업데이트할 도메인을 선택합니다.":::
 
3. 도메인의 개요 페이지에서 DNS 를 **선택합니다.**

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-2.png" alt-text="DNS를 선택합니다.":::

4. DNS 관리 페이지에서 **+레코드** 추가를 선택한 다음 테이블의 값을 입력하거나 복사하여 붙여넣습니다. 
    
    | **유형** | **이름** | **메일 서버** |  **TTL** | **우선 순위** |
    |:-----|:-----|:-----|:-----|:-----|
    |MX  <br/> |@  <br/> |*\<domain-key\>*  .mail.protection.outlook.com  <br/> **참고:** 사용자 *\<domain-key\>* 계정에서 Microsoft 365.   [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md) |30분  <br/> | 1  <br/> 우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](../setup/domains-faq.yml)을 참조하세요. <br/>|
   
5. **저장** 을 선택합니다.
  
6. MX 레코드 섹션에 나열된 다른 **MX** 레코드가 있는 경우 편집 을 선택하여 해당 레코드를 삭제한 다음 삭제 를 **선택합니다.** 
  
7. 확인 대화 상자에서 삭제를 **선택하여** 변경 내용을 확인할 수 있습니다. 

### <a name="add-the-cname-record-required-for-microsoft"></a>Microsoft에 필요한 CNAME 레코드 추가

1. 시작하려면 이 링크를 사용하여 Cloudflare의 도메인 [페이지로 이동합니다.](https://www.cloudflare.com/a/login) 먼저 로그인하라는 메시지가 표시됩니다.
      
2. 홈 페이지에서 업데이트할 도메인을 선택합니다. 
 
    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-1.png" alt-text="업데이트할 도메인을 선택합니다.":::
 
3. 도메인의 개요 페이지에서 DNS 를 **선택합니다.**

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-2.png" alt-text="DNS를 선택합니다.":::

4. CNAME 레코드를 추가합니다.
    
    DNS 관리 **페이지에서** **+레코드** 추가를 선택한 다음 테이블의 값을 입력하거나 복사하여 붙여넣습니다.

    | 유형 | 이름 | 대상 | TTL |
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |autodiscover  <br/> |autodiscover.outlook.com  <br/> |30분  <br/> |> |
  
6. **저장** 을 선택합니다.
    
### <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가

> [!IMPORTANT]
> 도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다. 도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다. 도메인에 이미 SPF 레코드가 있는 경우 Microsoft 365의 새 SPF 레코드를 만들지 마세요. 대신, 필수 Microsoft 365 값을 현재 레코드에 추가하여 두 값 집합을 모두 포함하는 *단일* SPF 레코드가 있도록 합니다. 
  
1. 시작하려면 이 링크를 사용하여 Cloudflare의 도메인 [페이지로 이동합니다.](https://www.cloudflare.com/a/login) 먼저 로그인하라는 메시지가 표시됩니다.  
  
2. 홈 페이지에서 업데이트할 도메인을 선택합니다. 
 
    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-1.png" alt-text="업데이트할 도메인을 선택합니다.":::
 
3. 도메인의 개요 페이지에서 DNS 를 **선택합니다.**

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-2.png" alt-text="DNS를 선택합니다.":::

4. DNS 관리 페이지에서 **+레코드** 추가를 선택하고 다음 표에서 값을 선택합니다.  
    
    | 유형 | 이름 | TTL | 콘텐츠 |
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |@  <br/> |30분  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.   |
 
5. **저장** 을 선택합니다.
  
## <a name="advanced-option-skype-for-business"></a>고급 옵션: 비즈니스용 Skype

조직에서 채팅, 전화 회의 및 화상 통화와 비즈니스용 Skype 같은 온라인 통신 서비스에도 이 옵션을 사용하는 Microsoft Teams. Skype 사용자 간 통신을 위한 SRV 레코드 2개와 사용자를 로그인하고 서비스에 연결하기 위한 CNAME 레코드 2개 등 4개 레코드가 필요합니다.

### <a name="add-the-two-required-srv-records"></a>필수 SRV 레코드 2개 추가

> [!IMPORTANT]
> Cloudflare는 이 기능을 사용할 수 있도록 하는 책임을 져야 합니다. 아래 단계와 현재 Cloudflare GUI(그래픽 사용자 인터페이스) 간에 불일치가 표시될 경우 [Cloudflare](https://community.cloudflare.com/)Community. 

1. 시작하려면 이 링크를 사용하여 Cloudflare의 도메인 [페이지로 이동합니다.](https://www.cloudflare.com/a/login) 먼저 로그인하라는 메시지가 표시됩니다.
      
2. 홈 페이지에서 업데이트할 도메인을 선택합니다. 

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-1.png" alt-text="업데이트할 도메인을 선택합니다.":::
  
3. 도메인의 개요 페이지에서 DNS 를 **선택합니다.**
  
    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-2.png" alt-text="DNS를 선택합니다.":::

4. 처음 2개의 SRV 레코드를 추가합니다.

    DNS 관리 페이지에서 **+레코드** 추가를 선택한 다음 표의 첫 번째 행의 값을 선택하거나 복사하여 붙여넣습니다.
        
    | **유형** | **이름** | **서비스** | **프로토콜** |  **TTL** | **Priority(우선 순위)** | **Weight(가중치)** | **Port(포트)** | **대상** |
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV|_sip | 사용자 *domain_name*. 예를 들어 contoso.com  ||TLS |30분 | 100|1 |443 |sipfed.online.lync.com  |
    |SRV|_sipfederationtls | TCP|사용자 *domain_name*. 예를 들어 contoso.com   |30분 |100 |1 |5061 | sipfed.online.lync.com |
  
5. **저장** 을 선택합니다.

6. 표의 두 번째 행에서 값을 선택하여 다른 SRV 레코드를 추가합니다. 
 
> [!NOTE]
>  일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 

### <a name="add-the-two-required-cname-records"></a>두 개의 필수 CNAME 레코드 추가
  
1. 시작하려면 이 링크를 사용하여 Cloudflare의 도메인 [페이지로 이동합니다.](https://www.cloudflare.com/a/login) 먼저 로그인하라는 메시지가 표시됩니다.
      
2. 홈 페이지에서 업데이트할 도메인을 선택합니다. 
 
    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-1.png" alt-text="업데이트할 도메인을 선택합니다.":::
 
3. 도메인의 개요 페이지에서 DNS 를 **선택합니다.**

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-2.png" alt-text="DNS를 선택합니다.":::

4. 첫 번째 CNAME 레코드를 추가합니다.
    
    DNS 관리 페이지에서 **+레코드** 추가를 선택한 다음 다음 표에 있는 첫 번째 행의 값을 입력하거나 복사하여 붙여넣습니다.
    
    |**유형**|**Name(이름)**|**Target(대상)**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |sip  <br/> |sipdir.online.lync.com.  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |1시간  <br/> |
    |CNAME  <br/> |lyncdiscover  <br/> |webdir.online.lync.com.  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |1 Hour  <br/> |
  
1. 저장 **을 선택합니다.** 
  
1. 표의 두 번째 행에서 값을 선택하여 다른 CNAME 레코드를 추가합니다.
    
> [!NOTE]
> 일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 
  
## <a name="advanced-option-intune-and-mobile-device-management-for-microsoft-365"></a>고급 옵션: Intune 및 모바일 장치 관리 Microsoft 365

이 서비스는 도메인에 연결하는 모바일 장치를 보호하고 원격으로 관리하는 데 도움이 됩니다. 모바일 장치 관리에는 사용자가 서비스에 장치를 등록할 수 있도록 2개 CNAME 레코드가 필요합니다.

### <a name="add-the-two-required-cname-records"></a>두 개의 필수 CNAME 레코드 추가

1. 시작하려면 이 링크를 사용하여 Cloudflare의 도메인 [페이지로 이동합니다.](https://www.cloudflare.com/a/login) 먼저 로그인하라는 메시지가 표시됩니다.
      
2. 홈 페이지에서 업데이트할 도메인을 선택합니다. 
 
    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-1.png" alt-text="업데이트할 도메인을 선택합니다.":::
 
3. 도메인의 개요 페이지에서 DNS 를 **선택합니다.**

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-2.png" alt-text="DNS를 선택합니다.":::

4. 첫 번째 CNAME 레코드를 추가합니다.
    
    DNS 관리 페이지에서 **+레코드** 추가를 선택한 다음 표의 첫 번째 행 값을 입력하거나 복사하여 붙여넣습니다.
    
    |**유형**|**Name(이름)**|**Target(대상)**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net.  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |1시간  <br/> |
    |CNAME  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |1 Hour  <br/> |
  
8. **저장** 을 선택합니다. 
  
9. 표의 두 번째 행에서 값을 선택하여 다른 CNAME 레코드를 추가합니다.
    
> [!NOTE]
> 일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 

  
