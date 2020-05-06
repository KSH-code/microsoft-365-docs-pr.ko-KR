---
title: Hostgator에서 Microsoft에 대 한 DNS 레코드 만들기
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
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5f0c840e-4140-4571-88ed-cf235ff142d6
description: 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대 한 DNS 레코드를 Microsoft 용 Hostgator에 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: fb510bcdcdefb141535e9a1099e18b63adffd2ab
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049002"
---
# <a name="create-dns-records-at-hostgator-for-microsoft"></a>Hostgator에서 Microsoft에 대 한 DNS 레코드 만들기

 **원하는 정보는 찾지 못한 경우 [도메인 질문과 대답을 확인](../setup/domains-faq.md)** 하세요. 
  
DNS 호스팅 공급자로 Hostgator를 사용하고 있는 경우, 이 문서에 나와 있는 단계를 따라 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 등에 대한 DNS 레코드를 설정합니다.
  
> [!IMPORTANT]
> 이 문서의 다른 절차를 사용 하 여 DNS 레코드를 추가 하기 전에 첫 번째 procedurebelow를 수행 하 여 [호스팅 계정에 대 한 도메인을 가리키도록](#point-your-domain-to-your-hosting-account)해야 합니다. 

Hostgator에서 이러한 모든 변경 작업을 수행한 후에는 도메인이 Microsoft 서비스에서 작동 하도록 설정 됩니다.
  

  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요. 
  
## <a name="point-your-domain-to-your-hosting-account"></a>도메인을 호스팅 계정에 연결
<a name="BKMK_PointDomain"> </a>

> [!IMPORTANT]
> 이 문서의 다른 절차를 수행하기 전에 이 절차를 수행해야 합니다. 
  
이러한 단계에 따라 도메인 및 호스팅 계정을 연결합니다.
  
1. 시작하려면 [이 링크](https://portal.hostgator.com/)를 사용하여 Hostgator의 도메인 관리 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.
    
2. 왼쪽에서 **도메인** 을 선택 합니다.
  
3. **도메인 관리** 페이지에서 업데이트 하려는 도메인을 선택 합니다. 
  
4. 왼쪽의 팝업 메뉴에서 **이름 서버**를 선택 합니다.
  
5. 도메인의 **이름 서버** 페이지에 있는 **이 도메인을 내 호스팅 계정으로 자동 가리키기** 드롭다운 목록에서 도메인과 연결 된 호스팅 계정을 선택 합니다. 
  
6. **이름 서버 저장**을 선택 합니다.
    
  
## <a name="add-a-txt-record-for-verification"></a>확인을 위해 TXT 레코드 추가
<a name="BKMK_verify"> </a>

> [!IMPORTANT]
> 이 절차를 수행하기 전에 이 문서의 첫 번째 구역에 있는 절차, [도메인을 호스팅 계정에 연결](#point-your-domain-to-your-hosting-account)을 수행해야 합니다. 
  
Microsoft에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft에 도메인을 소유하고 있음을 증명할 수 있습니다.
  
> [!NOTE]
> 이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다. 
  
1. To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.
    
    (Each hosted account at Hostgator is assigned a unique cPanel address. cPanel 주소의 형식은 https://YourSiteAddress:secure-port-number와 같습니다. Hostgator에서 받은 등록 전자 메일에는 해당 주소가 지정 되 고, **호스팅** 페이지 에서도 cpanel 링크를 사용할 수 있습니다.
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. Microsoft를 시작 하려면 Hostgator 또는 redelegate에서 호스팅 계정을 구입 [하 여 microsoft를 가리키도록](change-nameservers-at-hostgator.md)할 수 있습니다. 
  
2. **제어판** 페이지의 **도메인** 영역에서 **고급 영역 편집기**를 선택 합니다.
    
3. **고급 영역 편집기** 페이지의 **레코드 추가** 영역에서 새 레코드 용 상자에 다음 표의 값을 입력 하거나 복사 하 여 붙여넣습니다. 
    
    (드롭다운 목록에서 **Type(종류)** 값을 선택합니다.) 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**이름** <br/> |**TTL** <br/> |**유형** <br/> |**TXT 데이터** <br/> |
    |*Domain_name*를 사용 합니다. (for example, fourthcoffee.com.)  <br/> **This value MUST end with a period (.)** <br/> |개  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **참고:** 이 값은 예시입니다. 여기에는 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다. [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)          |
   
4. **레코드 추가**를 선택 합니다.
    
5. 방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.
    
이제 도메인 등록 기관에 레코드가 추가되었습니다. Microsoft로 돌아가서 레코드를 요청합니다.
  
Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.
  
1. I관리 센터에서 ** 설정 ** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인 </a> 페이지로 이동하십시오.
    
2. **도메인** 페이지에서 확인 중인 도메인을 선택합니다. 
    
3. **설정** 페이지에서 **설정 시작**을 선택합니다.
    
4. **도메인 확인** 페이지에서 **확인**을 선택합니다.
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요. 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드 추가하기
<a name="BKMK_add_MX"> </a>

> [!IMPORTANT]
> 이 절차를 수행하기 전에 이 문서의 첫 번째 구역에 있는 절차, [도메인을 호스팅 계정에 연결](#point-your-domain-to-your-hosting-account)을 수행해야 합니다. 
  
1. 시작하려면 Hostgator의 cPanel 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.
    
    (Hostgator에서 호스팅되는 각 계정에는 고유 cPanel 주소가 할당되어 있습니다. cPanel 주소의 형식은 https://YourSiteAddress:secure-port-number와 같습니다. Hostgator에서 받은 등록 전자 메일에는 해당 주소가 지정 되 고, **호스팅** 페이지 에서도 cpanel 링크를 사용할 수 있습니다.
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. Microsoft를 시작 하려면 Hostgator 또는 redelegate에서 호스팅 계정을 구입 [하 여 microsoft를 가리키도록](change-nameservers-at-hostgator.md)할 수 있습니다. 
  
2. **제어판** 페이지의 **전자 메일** 영역에서 **MX 항목**을 선택 합니다.
    
 
3. **전자 메일 라우팅** 영역에서 **원격 메일 교환기**를 선택합니다.

4. **변경을**선택 합니다.
  
5. **새 레코드 추가** 영역의 새 레코드 용 상자에 다음 표의 값을 입력 하거나 복사 하 여 붙여넣습니다. 
    
    |**우선 순위**|**대상**|
    |:-----|:-----|
    |개  <br/> 우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)을 참조하세요. <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **참고:** \< Microsoft 계정에서 *도메인 키* \> 를 가져옵니다.    [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)          |
  
6. **새 레코드 추가**를 선택 합니다.
   
 
7. **Mx 레코드** 구역에 다른 mx 레코드가 있으면 각 레코드를 제거 합니다. 

    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Microsoft에 필요한 6 개의 CNAME 레코드를 추가 합니다.
<a name="BKMK_add_CNAME"> </a>

> [!IMPORTANT]
> 이 절차를 수행하기 전에 이 문서의 첫 번째 구역에 있는 절차, [도메인을 호스팅 계정에 연결](#point-your-domain-to-your-hosting-account)을 수행해야 합니다. 
  
1. 시작하려면 Hostgator의 cPanel 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.
    
    (Hostgator에서 호스팅되는 각 계정에는 고유 cPanel 주소가 할당되어 있습니다. cPanel 주소의 형식은 https://YourSiteAddress:secure-port-number와 같습니다. Hostgator에서 받은 등록 전자 메일에는 해당 주소가 지정 되 고, **호스팅** 페이지 에서도 cpanel 링크를 사용할 수 있습니다.
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. Microsoft를 시작 하려면 Hostgator 또는 redelegate에서 호스팅 계정을 구입 [하 여 microsoft를 가리키도록](change-nameservers-at-hostgator.md)할 수 있습니다. 
  
2. **제어판** 페이지의 **도메인** 영역에서 **고급 영역 편집기**를 선택 합니다.
    
3. 6개의 CNAME 레코드 중 첫 번째 레코드를 추가합니다.
    
    **고급 영역 편집기** 페이지의 **레코드 추가** 영역의 새 레코드 용 상자에 다음 표에 있는 첫 번째 행의 값을 입력 하거나 복사 하 여 붙여넣습니다. 
    
    (드롭다운 목록에서 **Type(종류)** 값을 선택합니다.) 
    
    |**이름**|**TTL**|**종류**|**CNAME**|
    |:-----|:-----|:-----|:-----|
    |autodiscover. *domain_name*합니다. (예: autodiscover.fourthcoffee.com)  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |3600  <br/> |CNAME  <br/> |autodiscover.outlook.com  <br/> |
    |sip. *domain_name*합니다. (예: sip.fourthcoffee.com)  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |3600  <br/> |CNAME  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover. *domain_name*합니다. (예: lyncdiscover.fourthcoffee.com)  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |3600  <br/> |CNAME  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration. *domain_name*합니다. (예: enterpriseregistration.fourthcoffee.com)  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |3600  <br/> |CNAME  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment. *domain_name*합니다. (예: enterpriseregistration.fourthcoffee.com)  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |3600  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |

  
4. **레코드 추가**를 선택 합니다.

5. 나머지 5개의 CNAME 레코드를 각각 추가합니다.
    
    **레코드 추가** 구역에서 표의 다음 행 값을 사용 하 여 레코드를 만들고 다시 **레코드 추가** 를 선택 하 여 해당 레코드를 완료 합니다. 
    
    6개의 CNAME 레코드를 모두 만들 때까지 이 프로세스를 반복합니다.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다. 도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다. 도메인에 이미 SPF 레코드가 있는 경우 Microsoft의 새 SPF 레코드를 만들지 마세요. 대신, 필수 Microsoft 값을 현재 레코드에 추가하여 두 값 집합을 모두 포함하는 단일 SPF 레코드가 있도록 합니다. 예제가 필요하세요? [Microsoft에 대한 외부 Domain Name System 레코드](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records#bkmk_spfrecords)를 참조하세요. To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md). 
  
> [!IMPORTANT]
> 이 절차를 수행하기 전에 이 문서의 첫 번째 구역에 있는 절차, [도메인을 호스팅 계정에 연결](#point-your-domain-to-your-hosting-account)을 수행해야 합니다. 
  
1. 시작하려면 Hostgator의 cPanel 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.
    
    (Hostgator에서 호스팅되는 각 계정에는 고유 cPanel 주소가 할당되어 있습니다. cPanel 주소의 형식은 https://YourSiteAddress:secure-port-number와 같습니다. Hostgator에서 받은 등록 전자 메일에는 해당 주소가 지정 되 고, **호스팅** 페이지 에서도 cpanel 링크를 사용할 수 있습니다.
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. Microsoft를 시작 하려면 Hostgator 또는 redelegate에서 호스팅 계정을 구입 [하 여 microsoft를 가리키도록](change-nameservers-at-hostgator.md)할 수 있습니다. 
  
2. **제어판** 페이지의 **도메인** 영역에서 **고급 영역 편집기**를 선택 합니다.
    
3. On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (드롭다운 목록에서 **Type(종류)** 값을 선택합니다.) 
    
    |**이름**|**TTL**|**유형**|**TXT 데이터**|
    |:-----|:-----|:-----|:-----|
    |*Domain_name*를 사용 합니다. (for example, fourthcoffee.com.)  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |3600  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.           |
  
4. **레코드 추가**를 선택 합니다.
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Microsoft 필요한 2개의 SRV 레코드 추가하기
<a name="BKMK_add_SRV"> </a>

> [!IMPORTANT]
> 이 절차를 수행하기 전에 이 문서의 첫 번째 구역에 있는 절차, [도메인을 호스팅 계정에 연결](#point-your-domain-to-your-hosting-account)을 수행해야 합니다. 
  
1. 시작하려면 Hostgator의 cPanel 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.
    
    (Hostgator에서 호스팅되는 각 계정에는 고유 cPanel 주소가 할당되어 있습니다. cPanel 주소의 형식은 https://YourSiteAddress:secure-port-number와 같습니다. Hostgator에서 받은 등록 전자 메일에는 해당 주소가 지정 되 고, **호스팅** 페이지 에서도 cpanel 링크를 사용할 수 있습니다.
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. Microsoft를 시작 하려면 Hostgator 또는 redelegate에서 호스팅 계정을 구입 [하 여 microsoft를 가리키도록](change-nameservers-at-hostgator.md)할 수 있습니다. 
  
2. **제어판** 페이지의 **도메인** 영역에서 **고급 영역 편집기**를 선택 합니다.

    
3. 2개의 SRV 레코드 중 첫 번째 레코드를 추가합니다.
    
    **고급 DNS 영역 편집기** 페이지의 **레코드 추가** 영역에서 새 레코드용 상자에 다음 표의 첫 번째 행 값을 입력하거나 복사하여 붙여넣습니다. 
    
    (드롭다운 목록에서 **Type(종류)** 값을 선택합니다.) 
    
    |**이름**|**TTL**|**종류**|**Priority(우선 순위)**|**Weight(가중치)**|**Port(포트)**|**대상**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_tls을 _sip 합니다. *domain_name*합니다. 예를 들어 fourthcoffee를 _tls _sip 합니다.  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |3600  <br/> |SRV  <br/> |100  <br/> |개  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_tcp을 _sipfederationtls 합니다. *domain_name*합니다. 예를 들어 fourthcoffee를 _tcp _sipfederationtls 합니다.  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |3600  <br/> |SRV  <br/> |100  <br/> |개  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
   

4. **레코드 추가**를 선택 합니다.

  
5. 다른 SRV 레코드를 추가합니다.
    
    **레코드 추가** 구역에서 표의 다음 행 값을 사용 하 여 레코드를 만들고 다시 **레코드 추가** 를 선택 하 여 해당 레코드를 완료 합니다. 
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요. 
