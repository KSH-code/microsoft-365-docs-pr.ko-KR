---
title: Web.com에서 Microsoft에 대 한 DNS 레코드 만들기
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
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대 한 DNS 레코드를 Microsoft 용 web.com에 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: 25df88e05e96e2394628bf89c8cc07af2d0eac1e
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645758"
---
# <a name="create-dns-records-at-webcom-for-microsoft"></a>Web.com에서 Microsoft에 대 한 DNS 레코드 만들기

 원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.md)** 하세요. 
  
Web.com이 DNS 호스팅 공급자 인 경우이 문서의 단계에 따라 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 등에 대 한 DNS 레코드를 설정 합니다.
  
Web.com에서 이러한 레코드를 추가 하 고 나면 도메인이 Microsoft 서비스에서 작동 하도록 설정 됩니다.

  
> [!NOTE]
>  일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 
  
## <a name="change-your-domains-nameserver-ns-records"></a>도메인의 NS(이름 서버) 레코드 변경
<a name="BKMK_Nameservers"> </a>

> [!IMPORTANT]
> 이 절차는 도메인을 구입하고 등록한 도메인 등록 기관에서 수행해야 합니다. 
  
Web.com에 등록할 때 web.com **설치** 프로세스를 사용 하 여 도메인을 추가 했습니다. 
  
Microsoft에서 도메인에 대 한 DNS 레코드를 확인 하 고 만들려면 먼저 이름 서버를 사용 하도록 도메인 등록 기관에서 이름 서버를 변경 해야 합니다.
  
도메인 등록 기관 웹 사이트에서 도메인 이름 서버를 직접 변경하려면 다음 단계를 따릅니다.
  
1. 도메인 등록 기관의 웹 사이트에서 도메인의 이름 서버를 편집할 수 있는 영역을 찾습니다.
    
2. 다음 표의 값을 사용 하 여 두 개의 이름 서버 레코드를 만들거나 기존 이름 서버 레코드를 해당 값과 일치 하도록 편집 합니다.
    
    |||
    |:-----|:-----|
    |첫 번째 이름 서버  <br/> |Web.com에서 제공 하는 이름 서버 값을 사용 합니다.  <br/> |
    |두 번째 이름 서버  <br/> |Web.com에서 제공 하는 이름 서버 값을 사용 합니다.  <br/> |
   
    > [!TIP]
    > You should use at least two name server records. 다른 이름 서버가 나열 되어 있으면 삭제 해야 합니다. 
  
3. 변경 내용을 저장합니다.
    
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. 그러면 Microsoft 전자 메일 및 기타 서비스가 모두 도메인에서 작동 하도록 설정 됩니다. 
  
## <a name="add-a-txt-record-for-verification"></a>확인을 위해 TXT 레코드 추가
<a name="BKMK_verify"> </a>

Microsoft에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft에 도메인을 소유하고 있음을 증명할 수 있습니다.
  
> [!NOTE]
> 이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다. 
  
1. 시작 하려면 [이 링크](https://checkout.web.com/manage-it/index.jsp)를 사용 하 여 web.com의 도메인 페이지로 이동 합니다. 먼저 로그인 합니다.
  
2. **계정 관리자** 페이지에서 **내 도메인 이름을**선택 합니다. 
  
3. * * 관리 * 내 도메인 * * *에서 **고급 DNS 레코드 편집**을 선택 합니다.

  
4. **도메인 이름** 페이지의 **텍스트 (txt 레코드)** 에서 **txt 레코드 편집**을 클릭 하 고 다음 표에서 값을 선택 합니다. 
    
    |**호스트**|**TTL**|**텍스트**|
    |:-----|:-----|:----|
    |@  <br/> |3600  <br/> |MS=ms *XXXXXXXX*  <br/> **참고:** 이 값은 예시입니다. 여기에는 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.           [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. **계속**을 선택 합니다.
  
  
6. 방금 만든 레코드가 인터넷에서 업데이트 될 수 있도록 새 TXT 레코드를 확인 하기 전에 몇 분 정도 기다립니다.
    
이제 도메인 등록 기관에 레코드가 추가되었습니다. Microsoft로 돌아가서 레코드를 요청합니다.
  
Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.
  
1. I관리 센터에서 ** 설정 ** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인 </a> 페이지로 이동하십시오.

    
2. **도메인** 페이지에서 확인 중인 도메인을 선택합니다. 
    
    
  
3. **설정** 페이지에서 **설정 시작**을 선택합니다.
    
    
  
4. **도메인 확인** 페이지에서 **확인**을 선택합니다.
    
    
  
> [!NOTE]
>  일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드 추가하기
<a name="BKMK_add_MX"> </a>

1. 시작 하려면 [이 링크](https://checkout.web.com/manage-it/index.jsp)를 사용 하 여 web.com의 도메인 페이지로 이동 합니다. 먼저 로그인 합니다.
  
2. **계정 관리자** 페이지에서 **내 도메인 이름을**선택 합니다. 
  
3. * * 관리 * 내 도메인 * * *에서 **고급 DNS 레코드 편집**을 선택 합니다.

4. **메일 서버 (Mx 레코드)** 에서 **mx 레코드 편집**을 클릭 하 고 다음 표에서 값을 선택 합니다. 
    
    |**Priority(우선 순위)**|**TTL**|**메일 서버**|
    |:-----|:-----|:-----|
    |1   <br/> 우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)을 참조하세요. <br/> |3600  <br/> |*\<domain-key\>*  .mail.protection.outlook.com  <br/> **참고:**  *\<domain-key\>*  Microsoft 계정에서를 다운로드 하세요.   [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md) |
   

5. **저장**을 선택합니다.
  
6. **Mx 레코드** 구역에 다른 mx 레코드가 나열 되어 있으면 **삭제**아래의 레코드 옆에 있는 확인란을 선택 하 고 **저장**을 선택 합니다. 
  
7. 확인 화면에서 **변경 내용 저장**을 선택 합니다. 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Microsoft에 필요한 6 개의 CNAME 레코드를 추가 합니다.
<a name="BKMK_add_CNAME"> </a>

1. 시작 하려면 [이 링크](https://checkout.web.com/manage-it/index.jsp)를 사용 하 여 web.com의 도메인 페이지로 이동 합니다. 먼저 로그인하라는 메시지가 표시됩니다.
     
2. **계정 관리자** 페이지에서 **내 도메인 이름을**선택 합니다. 
  
3. * * 관리 * 내 도메인 * * *에서 **고급 DNS 레코드 편집**을 선택 합니다.

4. 6개의 CNAME 레코드 중 첫 번째 레코드를 추가합니다.
    
    **호스트 별칭 (Cname 레코드)** 에서 **CNAME 레코드 편집**을 클릭 하 고 다음 표에서 값을 선택 합니다.
    
    
    |**별칭**|**TTL**|**호스트 이름 참조**|**기타 호스트**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |3600  <br/> |@ (없음)  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |3600  <br/> |@ (없음)  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |3600  <br/> |@ (없음)  <br/> | webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |3600  <br/> |@ (없음)  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |3600  <br/> |@ (없음)  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
    |msoid  <br/> |3600  <br/> |@ (없음)  <br/> |clientconfig.microsoftonline-p.net  <br/> |
    
  
5. **계속**을 선택 합니다.
  
6. 나머지 5개의 CNAME 레코드를 각각 추가합니다.

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다. 도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다. 도메인에 이미 SPF 레코드가 있는 경우 Microsoft의 새 SPF 레코드를 만들지 마세요. 대신, 두 값 집합을 모두 포함 하는  *단일*  SPF 레코드가 있도록 현재 레코드에 필수 Microsoft 값을 추가 합니다. 
  
1. 시작 하려면 [이 링크](https://checkout.web.com/manage-it/index.jsp)를 사용 하 여 web.com의 도메인 페이지로 이동 합니다. 먼저 로그인 합니다.
    
  
2. **계정 관리자** 페이지에서 **내 도메인 이름을**선택 합니다. 
  
3. * * 관리 * 내 도메인 * * *에서 **고급 DNS 레코드 편집**을 선택 합니다.

  
4. **도메인 이름** 페이지의 **텍스트 (txt 레코드)** 에서 **txt 레코드 편집**을 클릭 하 고 다음 표에서 값을 선택 합니다.   
    
    |**호스트**|**TTL**|**텍스트**|
    |:-----|:-----|:-----|
    |@  <br/> |3600  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.   |

 
5. **계속**을 선택 합니다.

6. **변경 내용 저장**을 선택합니다.
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Microsoft 필요한 2개의 SRV 레코드 추가하기
<a name="BKMK_add_SRV"> </a>

> [!IMPORTANT]
> Web.com는이 기능을 사용 하도록 설정 해야 합니다. 아래 단계와 현재 web.com GUI (그래픽 사용자 인터페이스) 간의 불일치가 표시 되는 경우 [Web.com 커뮤니티](https://community.web.com.com/)를 활용 하세요. 

1. 시작 하려면 [이 링크](https://checkout.web.com/manage-it/index.jsp)를 사용 하 여 web.com의 도메인 페이지로 이동 합니다. 먼저 로그인 합니다.
      
2. **계정 관리자** 페이지에서 **내 도메인 이름을**선택 합니다. 
  
3. * * 관리 * 내 도메인 * * *에서 **고급 DNS 레코드 편집**을 선택 합니다.
  
4. 처음 2개의 SRV 레코드를 추가합니다.

    **서비스 (Srv 레코드)** 에서 **SRV 레코드 편집**을 클릭 하 고 다음 표에서 값을 선택 합니다. 
        
    |**서비스**|**프로토콜**|**TTL**|**Priority(우선 순위)**|**Weight(가중치)**|**Port(포트)**|**대상**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip |_tls |3600 | 100|1  |443 |sipfed.online.lync.com  |
    |_sipfederationtls |_tcp |3600 |100 |1  |5061 | sipfed.online.lync.com |

  
5. 표의 두 번째 행에서 값을 선택 하 여 다른 SRV 레코드를 추가 합니다. 
  
6. **계속**을 선택 합니다.

7. **변경 내용 저장**을 선택합니다.

    
> [!NOTE]
>  일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 
  
