---
title: Microsoft용 123-REG.CO.UK DNS 레코드 만들기
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
ms.assetid: 1f2d08c9-2a88-4d2f-ae1f-e39f9e358b17
description: Microsoft에서 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대한 DNS 레코드를 설정하는 123-reg.co.uk 대해 자세히 알아보습니다.
ms.openlocfilehash: 3c9af6909f37082a63170adac94ac3d92b717ad1
ms.sourcegitcommit: bf9e0091e5bdc78d9b23be64583eb816bb059eb2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2021
ms.locfileid: "50758907"
---
# <a name="create-dns-records-at-123-regcouk-for-microsoft"></a>Microsoft용 123-REG.CO.UK DNS 레코드 만들기

 **원하는 정보는 찾지 못한 경우 [도메인 질문과 대답을 확인](../setup/domains-faq.yml)** 하세요. 
  
DNS 호스팅 공급자로 123-reg.co.uk를 사용하고 있는 경우, 이 문서에 나와 있는 단계를 따라 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 등에 대한 DNS 레코드를 설정합니다.
  
이 레코드를 123-reg.co.uk Microsoft 서비스에서 작동 하게 도메인이 설정됩니다.
  
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요. 
  
## <a name="add-a-txt-record-for-verification"></a>확인을 위해 TXT 레코드 추가
<a name="BKMK_verify"> </a>

Microsoft에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft에 도메인을 소유하고 있음을 증명할 수 있습니다.
  
> [!NOTE]
> 이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다. 
  
1. 시작하려면 [이 링크](https://www.123-reg.co.uk/secure/cpanel/domain/overview)를 사용하여 123-reg.co.uk의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.
    
2. On the **Domain name overview** page, select the name of the domain that you want to edit. 
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. DNS **관리 페이지에서** 고급 **DNS 탭을** 선택합니다. 
    
5. In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    ||||
    |:-----|:-----|:-----|
    |**호스트 이름** <br/> |**종류** <br/> |**Destination TXT/SPF** <br/> |
    |@  <br/> |TXT/SPF  <br/> |MS=ms *XXXXXXXX*  <br/> **참고:** 이 값은 예시입니다. 여기에는 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다. [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)          |
   
6. **추가** 를 선택합니다.
    
7. 방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.
    
이제 도메인 등록 기관의 사이트에 레코드를 추가한 후 Microsoft로 돌아가 레코드에 대한 검색을 요청합니다.
  
Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.
  
1. Microsoft 관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동합니다.

    
2. **도메인** 페이지에서 확인 중인 도메인을 선택합니다. 
    
3. **설정** 페이지에서 **설정 시작** 을 선택합니다.
    
4. **도메인 확인** 페이지에서 **확인** 을 선택합니다.
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요. 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드 추가하기
<a name="BKMK_add_MX"> </a>

1. 시작하려면 [이 링크](https://www.123-reg.co.uk/secure/cpanel/domain/overview)를 사용하여 123-reg.co.uk의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.
    
2. On the **Domain name overview** page, select the name of the domain that you want to edit. 
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. DNS **관리 페이지에서** 고급 **DNS 탭을** 선택합니다. 
    
5. In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**호스트 이름**|**종류**|**우선 순위**|**대상 MX**|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |MX  <br/> |1  <br/> 우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)을 참조하세요. <br/> | *\<domain-key\>*  .mail.protection.outlook.com.  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> **참고:** Microsoft 계정에서 \<domain-key\>을(를) 받으세요. [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![표의 값 복사 및 붙여넣기](../../media/65366165-85a6-4a39-b9a7-6c5f47fbe790.png)
  
6. **추가** 를 선택합니다.
    
    ![추가 단추가 선택된 대화 상자의 스크린샷](../../media/a8ae6c0c-4365-4137-af8a-6e003996e3d0.png)
  
7. 다른 MX 레코드가 있으면 해당 레코드에 대한 **삭제(휴지통)** 아이콘을 선택하여 각 레코드를 삭제합니다. 
    
    ![삭제 선택(휴지통 아이콘)](../../media/3be635e6-b591-49af-8430-a158272834b4.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a>Microsoft에 필요한 5개의 CNAME 레코드 추가하기
<a name="BKMK_add_CNAME"> </a>

1. 시작하려면 [이 링크](https://www.123-reg.co.uk/secure/cpanel/domain/overview)를 사용하여 123-reg.co.uk의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.
    
2. On the **Domain name overview** page, select the name of the domain that you want to edit. 
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. DNS **관리 페이지에서** 고급 **DNS 탭을** 선택합니다. 
    
5. 5개의 CNAME 레코드 중 첫 번째 레코드를 추가합니다.
    
    In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**호스트 이름**|**종류**|**대상 CNAME**|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |autodiscover.outlook.com.  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |
    |sip  <br/> |CNAME  <br/> |sipdir.online.lync.com.  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |webdir.online.lync.com.  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |enterpriseregistration.windows.net.  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |
   
    ![복사하여 붙여넣을 대상 CNAME 스크린샷](../../media/24bf388c-5f7f-4fc0-b4ec-4b17226b6246.png)
  
6. **추가** 를 선택합니다.
    
    ![대상 CNAME을 추가하는 스크린샷](../../media/825a9854-559d-4a22-90ac-5e7a0a54269a.png)
  
7. 나머지 4개의 CNAME 레코드를 추가합니다.
    
    고급 **DNS 섹션에서** 표의 다음 행 값을 사용하여 레코드를 만든 다음  추가를 다시 선택하여 해당 레코드를 완료합니다. 
    
    5개의 CNAME 레코드를 모두 만들 때까지 이 프로세스를 반복합니다.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다. 도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다. 도메인에 대한 SPF 레코드가 이미 있는 경우 Microsfot용 SPF 레코드를 새로 만들지 않습니다. 대신 두 값 집합을 모두 포함하는  *단일*  SPF 레코드가 있도록 현재 레코드에 필요한 Microsoft 값을 추가합니다. 예제가 필요하세요? [Microsoft에 대한 외부 Domain Name System 레코드](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records#external-dns-records-required-for-spf)를 참조하세요. To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.yml). 
  
1. 시작하려면 [이 링크](https://www.123-reg.co.uk/secure/cpanel/domain/overview)를 사용하여 123-reg.co.uk의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.
    
2. On the **Domain name overview** page, select the name of the domain that you want to edit. 
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. DNS **관리 페이지에서** 고급 **DNS 탭을** 선택합니다. 
    
5. In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**호스트 이름**|**종류**|**Destination TXT/SPF**|
    |:-----|:-----|:-----|
    |@  <br/> |TXT/SPF  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.           |
   
    ![123Reg-BP-Configure-4-1](../../media/4697701c-eba0-4b03-8d75-4f7fc3bef94a.png)
  
6. **추가** 를 선택합니다.
    
    ![대상 TXT/SPF 스크린샷](../../media/7906dd91-fd23-44c3-bb37-ef185655c6eb.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Microsoft 필요한 2개의 SRV 레코드 추가하기
<a name="BKMK_add_SRV"> </a>

1. 시작하려면 [이 링크](https://www.123-reg.co.uk/secure/cpanel/domain/overview)를 사용하여 123-reg.co.uk의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.
    
2. On the **Domain name overview** page, select the name of the domain that you want to edit. 
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. DNS **관리 페이지에서** 고급 **DNS 탭을** 선택합니다. 
    
5. 처음 2개의 SRV 레코드를 추가합니다.
    
    In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    ||||||
    |:-----|:-----|:-----|:-----|:-----|
    |호스트 이름|종류|우선 순위|TTL|대상 SRV|
    |_sip._tls|SRV|100|3600|1 443 sipdir.online.lync.com. **이 값은 마침표(.)로 끝나야 합니다.**<br> **참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.           |
    |_sipfederationtls._tcp|SRV|100|3600|1 5061 sipfed.online.lync.com. **이 값은 마침표(.)로 끝나야 합니다.** <br> **참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.           |
   
    ![표의 DNS 값 스크린샷](../../media/c1786b86-52ef-4dca-8b99-b479554fa531.png)
  
6. **추가** 를 선택합니다.
    
    ![대상 SRV를 추가하는 스크린샷](../../media/5fd9d3a2-a8bb-466b-829f-b3a6e54b5104.png)
  
7. 다른 SRV 레코드를 추가하려면
    
    고급 **DNS 섹션에서** 표의 두 번째 행 값을 사용하여 레코드를 만든  다음 추가를 다시 선택하여 해당 레코드를 완료합니다. 
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요. 
  
