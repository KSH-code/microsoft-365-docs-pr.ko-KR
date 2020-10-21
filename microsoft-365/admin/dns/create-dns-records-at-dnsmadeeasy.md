---
title: DNSMadeEasy에서 Microsoft에 대 한 DNS 레코드 만들기
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
ms.assetid: e158b079-b054-4b7e-8e01-e55169ce18d7
description: 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대 한 DNS 레코드를 Microsoft 용 DNSMadeEasy에 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: 266f5e8460395ae10b9c430cf66e1f443126ff64
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646214"
---
# <a name="create-dns-records-at-dnsmadeeasy-for-microsoft"></a>DNSMadeEasy에서 Microsoft에 대 한 DNS 레코드 만들기

 **원하는 정보는 찾지 못한 경우 [도메인 질문과 대답을 확인](../setup/domains-faq.md)** 하세요. 
  
DNS 호스팅 공급자로 DNSMadeEasy를 사용하고 있는 경우, 이 문서에 나와 있는 단계를 따라 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 등에 대한 DNS 레코드를 설정합니다.
  
DNSMadeEasy에서 이러한 레코드를 추가 하 고 나면 도메인이 Microsoft 서비스에서 작동 하도록 설정 됩니다.
  

  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요. 
  
## <a name="add-a-txt-record-for-verification"></a>확인을 위해 TXT 레코드 추가
<a name="BKMK_verify"> </a>

Microsoft에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft에 도메인을 소유하고 있음을 증명할 수 있습니다.
  
> [!NOTE]
> 이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다. 
  
> [!IMPORTANT]
> DNSMadeEasy 계정의 경우 추가한 도메인은 별도의 도메인 등록 기관에서 구매한 것입니다. DNSMadeEasy는 도메인 등록 서비스를 제공하지 않습니다. DNSMadeEasy에서 로그인하고 DNS 레코드를 만드는 기능은 소유권의 충분한 증명이 됩니다. 
  
1. 시작하려면 [이 링크](https://cp.dnsmadeeasy.com/)를 사용하여 DNSMadeEasy의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.
    
2. **관리 콘솔** 페이지의 **최근에 업데이트 된 도메인** 영역에서 업데이트할 도메인을 선택 합니다. 
    
3. **관리 되는 DNS** 페이지의 **TXT 레코드** 영역에서 ( **+** ) 컨트롤 ( **새로 추가**)을 선택 합니다.
    
    (아래로 스크롤해야 할 수 있습니다.)
    
4. In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    ||||
    |:-----|:-----|:-----|
    |**이름** <br/> |**Value(값)** <br/> |**TTL** <br/> |
    |(이 필드는 비워 둡니다.)  <br/> |MS=ms *XXXXXXXX*  <br/> **참고:** 이 값은 예시입니다. 여기에는 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다. [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)          |1800  <br/> |
   
5. **전송**을 선택합니다.
    
6. 방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.
    
이제 도메인 등록 기관에 레코드가 추가되었습니다. Microsoft로 돌아가서 레코드를 요청합니다.
  
Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.
  
1. Microsoft 관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동합니다.

    
2. **도메인** 페이지에서 확인 중인 도메인을 선택합니다. 
    
3. **설정** 페이지에서 **설정 시작**을 선택합니다.
    
4. **도메인 확인** 페이지에서 **확인**을 선택합니다.
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요. 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드 추가하기
<a name="BKMK_add_MX"> </a>

1. 시작하려면 [이 링크](https://cp.dnsmadeeasy.com/)를 사용하여 DNSMadeEasy의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.
    
2. **관리 콘솔** 페이지의 **최근에 업데이트 된 도메인** 영역에서 업데이트할 도메인을 선택 합니다. 
    
    **관리 콘솔** 페이지의 **최근에 업데이트 된 도메인** 영역에서 업데이트할 도메인을 선택 합니다. 
    
    ![DNSMadeEasy-BP-구성-1-2](../../media/8d8f403e-d7cd-429e-913b-dacb1f4644a2.png)
  
3. **관리 되는 DNS** 페이지의 **MX 레코드** 영역에서 **(+)** 컨트롤 ( **새로 추가**)을 선택 합니다.
    
    (아래로 스크롤해야 할 수 있습니다.)
    
    ![DNSMadeEasy-BP-구성-2-1](../../media/404c73bf-1db4-4d68-82d8-68303f418ed4.png)
  
4. **MX 레코드 추가** 영역의 새 레코드용 상자에 다음 표의 값을 입력하거나 복사하여 붙여넣습니다. 
    
    (아래로 스크롤해야 할 수 있습니다.)
    
    |**이름**|**서버**|**MX 수준**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |(이 필드는 비워 둡니다.)  <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> **참고:** Microsoft 계정에서 \<*domain-key*\>을(를) 받으세요. [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)          |10    <br/> 우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)을 참조하세요. <br/> |1800  <br/> |
   
    ![DNSMadeEasy-BP-구성-2-2](../../media/69b53af9-1eec-435c-8434-1b6058c1ec82.png)
  
5. **전송**을 선택합니다.
    
    ![DNSMadeEasy-BP-구성-2-3](../../media/381054a6-bb85-4ebb-b576-42cbba78ed1b.png)
  
6. **MX 레코드** 구역에 다른 MX 레코드가 나열되어 있으면 하나씩 선택하여 모두 삭제합니다. 
    
    ![DNSMadeEasy-BP-구성-2-4-1](../../media/58a07769-0b30-4111-b555-bfc3b82a7d4c.png)
  
7. 모든 레코드를 선택 하 고 선택 **삭제**를 선택 합니다.
    
    ![DNSMadeEasy-BP-구성-2-4-2](../../media/e9064c07-1ce7-4387-b47a-90d4193da374.png)
  
8. **MX 레코드 삭제** 대화 상자에서 **삭제** 를 선택 하 여 변경 내용을 확인 합니다. 
    
    ![DNSMadeEasy-BP-구성-2-5](../../media/03c405e5-868f-468f-b6d2-046d27b201fb.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a>Microsoft에 필요한 5개의 CNAME 레코드 추가하기
<a name="BKMK_add_CNAME"> </a>

1. 시작하려면 [이 링크](https://cp.dnsmadeeasy.com/)를 사용하여 DNSMadeEasy의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.
    
2. **관리 콘솔** 페이지의 **최근에 업데이트 된 도메인** 영역에서 업데이트할 도메인을 선택 합니다. 
    
3. **관리 되는 DNS** 페이지의 **CNAME 레코드** 영역에서 **(+)** 컨트롤 ( **새로 추가**)을 선택 합니다.
    
    (아래로 스크롤해야 할 수 있습니다.)
    
    ![DNSMadeEasy-BP-구성-3-1](../../media/a5feb238-690d-4b64-a625-91a82b3f4068.png)
  
4. 5 개의 CNAME 레코드 중 처음 일부를 추가 합니다.
    
    **CNAME 레코드 추가** 영역의 새 레코드용 상자에 다음 표의 첫 번째 행의 값을 입력하거나 복사하여 붙여넣습니다. 
    
    |**이름**|**별칭 대상**|**TTL**|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com.  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |1800  <br/> |
    |sip  <br/> |sipdir.online.lync.com.  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |1800  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com.  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |1800  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net.  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |1800  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |1800  <br/> |
   
    ![DNSMadeEasy-BP-구성-3-2](../../media/de6dddcd-bf0a-4993-ab4c-a6d10167bf34.png)
  
5. **전송**을 선택합니다.
    
    ![DNSMadeEasy-BP-구성-3-3](../../media/e44ef73e-99cb-41ce-a3f2-549cb2f29eef.png)
  
6. 나머지 4 개의 CNAME 레코드를 각각 추가 합니다.
    
    **CNAME 레코드** 구역에서 **(+)** 컨트롤 ( **새로 추가**)을 선택 하 고 표에 있는 다음 행의 값을 사용 하 여 레코드를 만든 다음 다시 **제출을** 선택 하 여 해당 레코드를 완료 합니다. 
    
    5 개의 CNAME 레코드를 모두 만들 때까지이 프로세스를 반복 합니다.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다. 도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다. 도메인에 이미 SPF 레코드가 있는 경우 Microsoft의 새 SPF 레코드를 만들지 마세요. 대신, 두 값 집합을 모두 포함 하는  *단일*  SPF 레코드가 있도록 현재 레코드에 필수 Microsoft 값을 추가 합니다. 예제가 필요하세요? [Microsoft에 대한 외부 Domain Name System 레코드](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records)를 참조하세요. SPF 레코드의 유효성을 검사 하기 위해 이러한[spf 유효성 검사 도구](../setup/domains-faq.md)중 하나를 사용할 수 있습니다. 
  
1. 시작하려면 [이 링크](https://cp.dnsmadeeasy.com/)를 사용하여 DNSMadeEasy의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.
    
2. **관리 콘솔** 페이지의 **최근에 업데이트 된 도메인** 영역에서 업데이트할 도메인을 선택 합니다. 
    
3. **관리 되는 DNS** 페이지의 **TXT 레코드** 영역에서 **(+)** 컨트롤 ( **새로 추가**)을 선택 합니다.
    
    (아래로 스크롤해야 할 수 있습니다.)
    
    ![DNSMadeEasy-BP-구성-4-1](../../media/657b87a5-dcb4-4ae7-8f27-bd857f0f4189.png)
  
4. In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    |**이름**|**Value(값)**|**TTL**|
    |:-----|:-----|:-----|
    |(이 필드는 비워 둡니다.)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.           |1800  <br/> |
   
    ![DNSMadeEasy-BP-구성-4-2](../../media/b317bcb9-18c6-4609-a8f4-963823032669.png)
  
5. **전송**을 선택합니다.
    
    ![DNSMadeEasy-BP-구성-4-3](../../media/8a1c53c3-1222-4127-a190-70f6f5059433.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Microsoft 필요한 2개의 SRV 레코드 추가하기
<a name="BKMK_add_SRV"> </a>

1. 시작하려면 [이 링크](https://cp.dnsmadeeasy.com/)를 사용하여 DNSMadeEasy의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.
    
2. **관리 콘솔** 페이지의 **최근에 업데이트 된 도메인** 영역에서 업데이트할 도메인을 선택 합니다. 
    
3. **관리 되는 DNS** 페이지의 **SRV 레코드** 영역에서 **(+)** 컨트롤 ( **새로 추가**)을 선택 합니다.
    
    (아래로 스크롤해야 할 수 있습니다.)
    
    ![DNSMadeEasy-BP-구성-5-1](../../media/5c9e8f50-adbd-4f23-8ce3-2844b2896f3f.png)
  
4. 2개의 SRV 레코드 중 첫 번째 레코드를 추가합니다.
    
    **SRV 레코드 추가** 영역의 새 레코드용 상자에 다음 표의 첫 번째 행의 값을 입력하거나 복사하여 붙여넣습니다. 
    
    |**이름**|**Priority(우선 순위)**|**Weight(가중치)**|**Port(포트)**|**호스트**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip._tls  <br/> |100  <br/> |1   <br/> |443  <br/> |sipdir.online.lync.com.  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |1800  <br/> |
    |_sipfederationtls._tcp  <br/> |100  <br/> |1   <br/> |5061  <br/> |sipfed.online.lync.com  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |1800  <br/> |
   
    ![DNSMadeEasy-BP-구성-5-2](../../media/e1155f94-575f-441a-9a61-d948391d42ca.png)
  
5. **전송**을 선택합니다.
    
    ![DNSMadeEasy-BP-구성-5-3](../../media/7eae54e1-08bd-4902-afdf-fd5cc251ab59.png)
  
6. 다른 SRV 레코드를 추가합니다.
    
    **SRV 레코드** 구역에서 **(+)** 컨트롤 ( **새로 추가**)을 선택 하 고 표에 있는 다음 행의 값을 사용 하 여 레코드를 만든 다음 다시 **제출을** 선택 하 여 해당 레코드를 완료 합니다. 
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요. 
  

