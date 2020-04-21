---
title: Microsoft의 AWS (Amazon Web Services)에서 DNS 레코드 만들기
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
ms.assetid: 7a2efd75-0771-4897-ba7b-082fe5bfa9da
description: Microsoft의 AWS (Amazon Web Services)에서 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대 한 DNS 레코드를 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: 086a5d7210d2c722aeda701dc62a699ca0eaec87
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629734"
---
# <a name="create-dns-records-at-amazon-web-services-aws-for-microsoft"></a>Microsoft의 AWS (Amazon Web Services)에서 DNS 레코드 만들기

 원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.md)** 하세요. 
  
AWS이 DNS 호스팅 공급자 인 경우이 문서의 단계에 따라 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 등에 대 한 DNS 레코드를 설정 합니다.
  
AWS에서 이러한 레코드를 추가 하 고 나면 도메인이 Microsoft 서비스에서 작동 하도록 설정 됩니다.
  
마이크로 sfot을 사용 하는 웹 사이트에 대 한 호스트 및 DNS에 대 한 자세한 내용은 [Microsoft에서 공개 웹 사이트 사용](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)을 참조 하세요.
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제에 문제가 있는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조 하세요. 
  
## <a name="add-a-txt-record-for-verification"></a>확인을 위해 TXT 레코드 추가
<a name="BKMK_verify"> </a>

Microsoft에서 도메인을 사용 하기 전에 사용자가 소유 하 고 있는지 확인 해야 합니다. 도메인 등록 기관에서 계정에 로그인 하 고 DNS 레코드를 만들 수 있는 기능은 Microsoft에 도메인을 소유 하 고 있음을 증명 합니다.
  
> [!NOTE]
> 이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다. 
  
1. 시작하려면 [이 링크](https://console.aws.amazon.com/route53/home)를 사용하여 AWS의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.
    
2. **리소스** 페이지에서 **호스트 된 영역**을 선택 합니다.
    
3. * * 호스팅 영역 * * 페이지의 **도메인 이름** 열에서 편집 하려는 도메인의 이름을 선택 합니다. 
    
4. **레코드 집합 만들기**를 선택 합니다.
    
5. In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** and **Routing Policy** values from the drop-down lists.) 
    
    > [!TIP]
    > The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually. 
  
    |||||||
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |**이름** <br/> |**종류** <br/> |**별칭** <br/> |**TTL(초)** <br/> |**값** <br/> |**라우팅 정책** <br/> |
    |(Leave this field empty.)  <br/> |TXT - Text  <br/> |아니요  <br/> |300  <br/> |MS=ms *XXXXXXXX*  <br/>**참고:** 이 값은 예시입니다. 여기에는 Microsoft 365의 표에 나와 있는 특정 **대상 또는 지점** 값을 사용 합니다. [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)          |Simple(단순형)  <br/> |
   
6. **만들기**를 선택합니다.
    
7. 방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.
    
도메인 등록 기관 사이트에서 레코드를 추가 했으므로 이제 Microsoft로 이동 하 여 레코드 검색을 요청 합니다.
  
Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인 된 것입니다.
  
1. Microsoft 관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동 합니다.

    
2. **도메인** 페이지에서 확인 중인 도메인을 선택합니다. 
    
3. **설정** 페이지에서 **설정 시작**을 선택합니다.
    
4. **도메인 확인** 페이지에서 **확인**을 선택합니다.
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제에 문제가 있는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조 하세요. 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft-365"></a>도메인에 대 한 전자 메일이 Microsoft 365에 제공 되도록 MX 레코드를 추가 합니다.
<a name="BKMK_add_MX"> </a>

1. 시작하려면 [이 링크](https://console.aws.amazon.com/route53/home)를 사용하여 AWS의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.
    
2. **리소스** 페이지에서 **호스트 된 영역**을 선택 합니다.
    
3. **호스팅된 영역** 페이지의 **Domain Name (도메인 이름** ) 열에서 편집 하려는 도메인의 이름을 선택 합니다. 
    
4. **레코드 집합 만들기**를 선택 합니다.
    
5. In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** and **Routing Policy** values from the drop-down lists.) 
    
    |**이름**|**종류**|**별칭**|**TTL(초)**|**값**|**라우팅 정책**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |(이 필드는 비워 둡니다.)  <br/> |MX - Mail Exchanger(MX - 메일 교환기)  <br/> |아니요  <br/> |300  <br/> |0  *\<도메인 키\>*  .mail.protection.outlook.com.  <br/> 0은 MX 우선 순위 값입니다. 이 값을 MX 값 시작 부분에 추가하고 나머지 값과 공백으로 구분합니다.  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> **참고:** \<Microsoft 365 계정에서 *도메인 키* \> 를 가져옵니다. [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)          |Simple(단순형)  <br/> |
       
    ![AWS-BP-구성-2-1](../../media/94a71ce7-1b3b-4b1a-9ad3-9592db133075.png)
  
6. **만들기**를 선택합니다.
    
    ![AWS-BP-Configure-2-2](../../media/1c050c72-c04f-48d5-a8e9-44cd83ddd33e.png)
  
7. 다른 MX 레코드가 있으면 해당 레코드를 제거합니다.
    
    > [!IMPORTANT]
    > AWS에서는 MX 레코드를 여러 레코드가 포함될 수 있는 한 집합으로 저장합니다. **레코드 집합 삭제** **를 선택 하면** 방금 추가한 MX 레코드를 포함 하 여 모두 삭제 됩니다. 대신 다음 지침을 따릅니다. 
  
    먼저 MX 레코드 집합을 선택 합니다.
    
    ![AWS-BP-Configure-2-3](../../media/9d9388cb-e2d0-43b7-928c-e1d07e519c6f.png)
  
    다음으로, **Edit Record Set(레코드 집합 편집)** 영역의 **Value(값)** 상자에서 항목을 선택한 다음 키보드의 **Delete** 키를 눌러 오래된 각 MX 레코드를 삭제합니다. 
    
    ![AWS-BP-Configure-2-4](../../media/c3b0c1bc-21ab-44cc-84b7-f504725c5540.png)
  
8. **레코드 집합 저장**을 선택 합니다.
    
    ![AWS-BP-Configure-2-5](../../media/86f0998d-f5d4-4750-a93d-ac13b318c40b.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft-365"></a>Microsoft 365에 필요한 5 개의 CNAME 레코드 추가
<a name="BKMK_add_CNAME"> </a>

1. 시작하려면 [이 링크](https://console.aws.amazon.com/route53/home)를 사용하여 AWS의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.
    
2. **리소스** 페이지에서 **호스트 된 영역**을 선택 합니다.
    
3. **호스팅된 영역** 페이지의 **Domain Name (도메인 이름** ) 열에서 편집 하려는 도메인의 이름을 선택 합니다. 
    
4. **레코드 집합 만들기**를 선택 합니다.
    
5. 첫 번째 CNAME 레코드를 추가합니다.
    
    **Create Record Set(레코드 집합 만들기)** 영역의 새 레코드용 상자에 다음 표의 첫 번째 행에 있는 값을 입력하거나 복사하여 붙여 넣습니다. 
    
    (드롭다운 목록에서 **Type**(종류) 및 **Routing Policy**(라우팅 정책) 값을 선택합니다.) 
    
    |**이름**|**종류**|**별칭**|**TTL(초)**|**값**|**라우팅 정책**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME - Canonical name(CNAME - 정식 이름)  <br/> |No(아니요)  <br/> |300  <br/> |autodiscover.outlook.com  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |Simple(단순형)  <br/> |
    |sip  <br/> |CNAME - Canonical name(CNAME - 정식 이름)  <br/> |No(아니요)  <br/> |300  <br/> |sipdir.online.lync.com  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |Simple(기본)  <br/> |
    |lyncdiscover  <br/> |CNAME - Canonical name(CNAME - 정식 이름)  <br/> |No(아니요)  <br/> |300  <br/> |webdir.online.lync.com  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |Simple(단순형)  <br/> |
    |enterpriseregistration  <br/> |CNAME - Canonical name(CNAME - 정식 이름)  <br/> |No(아니요)  <br/> |300  <br/> |enterpriseregistration.windows.net  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |Simple(기본)  <br/> |
    |enterpriseenrollment  <br/> |CNAME - Canonical name(CNAME - 정식 이름)  <br/> |No(아니요)  <br/> |300  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |Simple(단순형)  <br/> |
   
    ![AWS-BP-구성-3-1](../../media/895c71bd-0e3a-425e-9681-98c1c67e714b.png)
  
6. **만들기**를 선택합니다.
    
    ![AWS-BP-Configure-3-2](../../media/33964846-5282-44a4-b241-62ce02b96735.png)
  
7. 나머지 4개의 CNAME 레코드를 추가합니다.
    
    **호스팅된 영역** 페이지에서 **레코드 집합 만들기**를 선택 하 고 표의 다음 행에 있는 값을 사용 하 여 레코드를 만든 다음 다시 **만들기** 를 선택 하 여 해당 레코드를 완료 합니다. 
    
    5 개의 CNAME 레코드를 모두 만들 때까지이 프로세스를 반복 합니다.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다. 도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다. 도메인에 대 한 SPF 레코드가 이미 있는 경우 Microsoft에 대해 새로 만들지 마십시오. 대신, 두 값 집합을 모두 포함 하는 *단일* SPF 레코드가 있도록 현재 레코드에 필수 Microsoft 값을 추가 합니다. 예제가 필요하세요? 이러한 [외부 도메인 이름 시스템 레코드를 Microsoft에](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0)체크 아웃 합니다. SPF 레코드의 유효성을 검사 하기 위해 이러한[spf 유효성 검사 도구](../setup/domains-faq.md)중 하나를 사용할 수 있습니다. 
  
1. 시작하려면 [이 링크](https://console.aws.amazon.com/route53/home)를 사용하여 AWS의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.
    
2. **리소스** 페이지에서 **호스트 된 영역**을 선택 합니다.
    
3. **호스팅된 영역** 페이지의 **Domain Name (도메인 이름** ) 열에서 편집 하려는 도메인의 이름을 선택 합니다. 
    
4. **TXT** 레코드 집합을 선택 합니다. 
    
    ![AWS-BP-Configure-4-1](../../media/0310fa66-c016-4987-80df-930f1c8f3c39.png)
  
5. **레코드 집합 편집** 영역에서 기존 레코드의 **값:** 상자에 있는 현재 항목의 맨 끝에서 키보드의 Enter를 눌러 새 줄을 만든 다음, 이 새 줄에서(기존 값 아래) 다음 표의 값을 입력하거나 복사하여 붙여넣습니다. (표 아래 그림의 예를 참조할 수 있습니다.) 
    
    |**값:**|
    |:-----|
    |v=spf1 include:spf.protection.outlook.com -all  <br/> (화면 지침에 필요한 물음표가 자동으로 제공됩니다. 직접 입력할 필요가 없습니다.)  <br/> **참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.           |
   
    ![AWS-BP-구성-4-2](../../media/beb3c086-eaf8-4245-9860-18512a3ff72e.png)
  
6. **레코드 집합 저장**을 선택 합니다.
    
    ![AWS-BP-Configure-4-3](../../media/94b9306c-bdc9-4f84-ad6f-6d12edbfde90.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft-365"></a>Microsoft 365에 필요한 2 개의 SRV 레코드를 추가 합니다.
<a name="BKMK_add_SRV"> </a>

1. 시작하려면 [이 링크](https://console.aws.amazon.com/route53/home)를 사용하여 AWS의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.
    
2. **리소스** 페이지에서 **호스트 된 영역**을 선택 합니다.
    
3. **호스팅된 영역** 페이지의 **Domain Name (도메인 이름** ) 열에서 편집 하려는 도메인의 이름을 선택 합니다. 
    
4. **레코드 집합 만들기**를 선택 합니다.
    
5. 첫 번째 SRV 레코드를 추가합니다.
    
    **Create Record Set(레코드 집합 만들기)** 영역의 새 레코드용 상자에 다음 표의 첫 번째 행에 있는 값을 입력하거나 복사하여 붙여 넣습니다. 
    
    (드롭다운 목록에서 **Type**(종류) 및 **Routing Policy**(라우팅 정책) 값을 선택합니다.) 
    
    |**이름**|**종류**|**별칭**|**TTL(초)**|**값**|**라우팅 정책**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip _tls|SRV - Service locator(SRV - 서비스 로케이터)|아니요|300|100 1 443 sipdir.online.lync.com. **이 값은 마침표 (.)로 끝나야 합니다.**><br> **참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.           |Simple(단순형)|
    |_sipfederationtls _tcp|SRV - Service locator(SRV - 서비스 로케이터)|아니요|300|100 1 5061 sipfed.online.lync.com. **This value MUST end with a period (.)**<br> **참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.           |Simple(단순형)|
   
    ![AWS-BP-구성-5-1](../../media/c3f841d3-6076-428f-bb04-e71cc5f392fa.png)
  
6. **만들기**를 선택합니다.
    
    ![AWS-BP-Configure-5-2](../../media/1bf5dc58-a46b-47a5-bd69-7c2147dd4e50.png)
  
7. 다른 SRV 레코드를 추가하려면
    
    **호스팅된 영역** 페이지에서 **레코드 집합 만들기**를 선택 하 고 표의 다음 행에 있는 값을 사용 하 여 레코드를 만든 다음 다시 **만들기** 를 선택 하 여 해당 레코드를 완료 합니다. 
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제에 문제가 있는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조 하세요. 
  
