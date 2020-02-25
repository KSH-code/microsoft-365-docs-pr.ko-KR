---
title: Cloudflare에서 Office 365에 대 한 DNS 레코드 만들기
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
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스 (Office 365 용)에 대 한 DNS 레코드를 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: efd7a4a41a0cc27c2a50da732d648c87c79c6ff7
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42248143"
---
# <a name="create-dns-records-at-cloudflare-for-office-365"></a>Cloudflare에서 Office 365에 대 한 DNS 레코드 만들기

 원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.md)** 하세요. 
  
Cloudflare가 DNS 호스팅 공급자 인 경우이 문서의 단계에 따라 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 등에 대 한 DNS 레코드를 설정 합니다.
  
Cloudflare에서 이러한 레코드를 추가 하 고 나면 도메인이 Office 365 서비스에서 작동 하도록 설정 됩니다.
  
Office 365에서 웹 사이트의 웹 호스팅 및 DNS에 대한 자세한 내용은 [Office 365에서 공개 웹 사이트 사용](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx)을 참조하세요.
  
> [!NOTE]
>  일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 
  
## <a name="change-your-domains-nameserver-ns-records"></a>도메인의 NS(이름 서버) 레코드 변경
<a name="BKMK_Nameservers"> </a>

> [!IMPORTANT]
> 이 절차는 도메인을 구입하고 등록한 도메인 등록 기관에서 수행해야 합니다. 
  
Cloudflare에 등록할 때 Cloudflare **설정** 프로세스를 사용 하 여 도메인을 추가 했습니다. 
  
추가한 도메인은 별도의 도메인 등록 기관에서 구매한 것입니다. Cloudflare는 도메인 등록 서비스를 제공 하지 않습니다. Office 365에서 도메인에 대 한 DNS 레코드를 확인 하 고 만들려면 먼저 도메인 등록 기관에서 이름 서버를 변경 하 여 Cloudflare 이름 서버을 사용 하도록 해야 합니다.
  
도메인 등록 기관 웹 사이트에서 도메인 이름 서버를 직접 변경하려면 다음 단계를 따릅니다.
  
1. 도메인 등록 기관의 웹 사이트에서 도메인의 이름 서버를 편집할 수 있는 영역을 찾습니다.
    
2. 다음 표의 값을 사용 하 여 두 개의 이름 서버 레코드를 만들거나 기존 이름 서버 레코드를 해당 값과 일치 하도록 편집 합니다.
    
    |||
    |:-----|:-----|
    |첫 번째 이름 서버  <br/> |Cloudflare에서 제공 하는 이름 서버 값을 사용 합니다.  <br/> |
    |두 번째 이름 서버  <br/> |Cloudflare에서 제공 하는 이름 서버 값을 사용 합니다.  <br/> |
   
    > [!TIP]
    > You should use at least two name server records. 다른 이름 서버가 나열 되어 있으면 삭제 해야 합니다. 
  
3. 변경 내용을 저장합니다.
    
> [!NOTE]
> 이름 서버 레코드 업데이트가 인터넷의 DNS 시스템 전체에 업데이트되기까지 몇 시간이 걸릴 수 있습니다. 그 후에는 Office 365 전자 메일 및 기타 서비스가 모두 사용자의 도메인을 사용하도록 설정됩니다. 
  
## <a name="add-a-txt-record-for-verification"></a>확인을 위해 TXT 레코드 추가
<a name="BKMK_verify"> </a>

Office 365에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Office 365에 도메인을 소유하고 있음을 증명할 수 있습니다.
  
> [!NOTE]
> 이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다. 
  
1. 시작 하려면 [이 링크](https://www.cloudflare.com/a/login)를 사용 하 여 cloudflare의 도메인 페이지로 이동 합니다. You'll be prompted to log in first.
  
2. **홈** 페이지에서 업데이트할 도메인을 선택 합니다. 
  
3. 도메인의 **개요** 페이지에서 **DNS**를 선택 합니다.

  
4. **DNS 관리** 페이지에서 **레코드 추가**를 클릭 한 후 다음 표의 값을 선택 합니다. 
    
    |**유형**|**이름**|**자동 TTL**|**콘텐츠**|
    |:-----|:-----|:-----|:----|
    |TXT  <br/> |@  <br/> |30분  <br/> |MS=ms *XXXXXXXX*  <br/> **참고:** 예를 들면 다음과 같습니다. 여기에는 Office 365의 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.           [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. **저장**을 선택합니다.
  
  
9. 방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. 관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동 합니다.

    
2. **도메인** 페이지에서 확인 하려는 도메인을 선택 합니다. 
    
    
  
3. **설정** 페이지에서 **설정 시작**을 선택 합니다.
    
    
  
4. **도메인 확인** 페이지에서 **확인**을 선택 합니다.
    
    
  
> [!NOTE]
>  일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>사용자 도메인의 전자 메일이 Office 365로 전송되도록 MX 레코드 추가
<a name="BKMK_add_MX"> </a>

1. 시작 하려면 [이 링크](https://www.cloudflare.com/a/login)를 사용 하 여 cloudflare의 도메인 페이지로 이동 합니다. You'll be prompted to log in first.
  
2. **홈** 페이지에서 업데이트할 도메인을 선택 합니다. 
  
3. 도메인의 **개요** 페이지에서 **DNS**를 선택 합니다.

  
4. **DNS 관리** 페이지에서 **레코드 추가**를 클릭 한 후 다음 표의 값을 선택 합니다. 
    
    |**유형**|**이름**|**메일 서버**|**우선 순위**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|
    |MX  <br/> |@  <br/> |*\<domain-key\>*  .mail.protection.outlook.com  <br/> **참고:** Office 365 계정에서 * \<도메인\> 키* 를 가져옵니다.   [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md) |개  <br/> 우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)을 참조하세요. <br/>|30분  <br/> |
   

  
5. **저장**을 선택합니다.
  
9. **Mx 레코드** 구역에 다른 mx 레코드가 나열 되어 있으면 **삭제 (X)** 아이콘을 선택 하 여 해당 레코드를 삭제 합니다. 
  
10. 확인 대화 상자에서 **삭제** 를 선택 하 여 변경 내용을 확인 합니다. 

  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a>Office 365에 필요한 6 개의 CNAME 레코드 추가
<a name="BKMK_add_CNAME"> </a>

1. 시작 하려면 [이 링크](https://www.cloudflare.com/a/login)를 사용 하 여 cloudflare의 도메인 페이지로 이동 합니다. You'll be prompted to log in first.
    
  
2. **홈** 페이지에서 업데이트할 도메인을 선택 합니다. 
  
3. 도메인의 **개요** 페이지에서 **DNS**를 선택 합니다.

  
4. 5 개의 CNAME 레코드 중 처음 일부를 추가 합니다.
    
    **DNS 관리** 페이지에서 **레코드 추가**를 클릭 한 후 다음 표의 값을 선택 합니다.
    
    
    |**유형**|**이름**|**대상**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |autodiscover  <br/> |autodiscover.outlook.com  <br/> |30분  <br/> |
    |CNAME  <br/> |sip  <br/> |sipdir.online.lync.com  <br/> |30분  <br/> |
    |CNAME  <br/> |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |30분  <br/> |
    |CNAME  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |30분  <br/> |
    |CNAME  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |30분  <br/> |
    |CNAME  <br/> |msoid  <br/> |clientconfig.microsoftonline-p.net  <br/> |30분  <br/> |
    
  
5. **DNS 트래픽** 아이콘 (주황색 클라우드)을 선택 하 여 cloudflare 서버를 사용 하지 않도록 합니다.
  
6. **저장**을 선택합니다.
  
7. 나머지 5개의 CNAME 레코드를 각각 추가합니다.

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values. 
  
1. 시작 하려면 [이 링크](https://www.cloudflare.com/a/login)를 사용 하 여 cloudflare의 도메인 페이지로 이동 합니다. You'll be prompted to log in first.
    
  
2. **홈** 페이지에서 업데이트할 도메인을 선택 합니다. 
  
3. 도메인의 **개요** 페이지에서 **DNS**를 선택 합니다.

  
4. **DNS 관리** 페이지에서 **레코드 추가**를 클릭 한 후 다음 표의 값을 선택 합니다.  
    
    |**유형**|**이름**|**TTL**|**콘텐츠**|
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |@  <br/> |30분  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **참고:** 모든 공백이 올바르게 유지 되도록이 항목을 복사 하 여 붙여 넣는 것이 좋습니다.   |

 
5. **저장**을 선택합니다.
    

  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Office 365에 필요한 2개의 SRV 레코드 추가
<a name="BKMK_add_SRV"> </a>

> [!IMPORTANT]
> Cloudflare는이 기능을 사용 하도록 설정 해야 합니다. 아래 단계와 현재 Cloudflare GUI (그래픽 사용자 인터페이스) 간의 불일치가 표시 되는 경우 [Cloudflare 커뮤니티](https://community.cloudflare.com/)를 활용 하세요. 

1. 시작 하려면 [이 링크](https://www.cloudflare.com/a/login)를 사용 하 여 cloudflare의 도메인 페이지로 이동 합니다. You'll be prompted to log in first.
      
2. **홈** 페이지에서 업데이트할 도메인을 선택 합니다. 
  
3. 도메인의 **개요** 페이지에서 **DNS**를 선택 합니다.
  
4. 처음 2개의 SRV 레코드를 추가합니다.

    **DNS 관리** 페이지에서 **레코드 추가**를 클릭 하 고 다음 표의 첫 번째 행에 있는 값을 선택 합니다.
        
    |**유형**|**서비스**|**프로토콜**|**이름**|**TTL**|**우선 순위**|**가중치**|**포트**|**대상**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV|_sip |TLS |*Domain_name*사용 예를 들어 contoso.com  |30분 | 100|개 |443 |sipfed.online.lync.com  |
    |SRV|_sipfederationtls | TCP|*Domain_name*사용 예를 들어 contoso.com   |30분 |100 |개 |5061 | sipfed.online.lync.com |

  
5. **저장**을 선택합니다.

  
6. 표의 두 번째 행에서 값을 선택 하 여 다른 SRV 레코드를 추가 합니다. 

    
> [!NOTE]
>  일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 
  
