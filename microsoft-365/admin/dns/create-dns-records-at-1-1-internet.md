---
title: 1&1gb OS에서 DNS 레코드 만들기
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5762c3ca-1de2-4999-bfe5-4c5e25a8957e
description: 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대 한 DNS 레코드를 설정 하는 방법에 대해 설명 합니다 (예&1).
ms.openlocfilehash: 10c135d8fdc1512f0b2c1b341f3524097d5f6494
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307154"
---
# <a name="create-dns-records-at-11-ionos-for-microsoft"></a>1&1gb OS에서 DNS 레코드 만들기

 원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.md)** 하세요. 
  
> [!CAUTION]
> 1&, 1gb OS는 도메인이 MX 레코드와 최상위 자동 검색 CNAME 레코드를 모두 가질 수 없습니다. 이렇게 하면 Microsoft에 대해 Exchange Online을 구성 하는 방법이 제한 됩니다. 해결 방법은 있지만 1&1gb OS에서 하위 도메인을 만든 경험이 이미 있는 경우에 **만** 이 방법을 사용 하는 것이 좋습니다. >이 [서비스 제한은](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) 1&1gb os에서 자체 Microsoft DNS 레코드를 관리 하도록 선택 하는 경우에는이 문서의 단계에 따라 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 등에 대 한 DNS 레코드를 설정 합니다. 
  
1&, 1gb OS에 이러한 레코드를 추가 하 고 나면 도메인은 Microsoft 서비스에서 작동 하도록 설정 됩니다.
  
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요. 
  
## <a name="add-a-txt-record-for-verification"></a>확인을 위해 TXT 레코드 추가

Microsoft에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft에 도메인을 소유하고 있음을 증명할 수 있습니다.
  
> [!NOTE]
> 이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다. 
  
아래 단계를 따르거나 [비디오를 시청하세요(0:42에 시작)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).
  
1. 시작 하려면 [이 링크](https://my.1and1.com/)를 사용 하 여 1&1gb os의 도메인 페이지로 이동 합니다. You'll be prompted to log in.
    
2. **도메인 관리**를 선택 합니다.
    
3. **Domain Center (도메인 센터** ) 페이지에서 업데이트 하려는 도메인을 찾은 다음 해당 도메인에 대 한 **패널** ( **v**) 컨트롤을 선택 합니다.
    
4. **도메인 설정** 영역에서 **DNS 설정 편집**을 선택 합니다.
    
5. **TXT 및 SRV 레코드** 섹션에서 **레코드 추가**를 선택 합니다.
    
6. In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (드롭다운 목록에서 **Type(종류)** 값을 선택합니다.) 
    
    ||||
    |:-----|:-----|:-----|
    |**종류** <br/> |**Prefix(접두사)** <br/> |**Name Value(이름 값)** <br/> |
    |TXT  <br/> |(이 필드를 비워 둠)  <br/> |MS=ms *XXXXXXXX*  <br/> 참고:이는 예입니다. 여기에는 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다. [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)          |
   
7. **저장**을 선택합니다.
    
8. **저장** 을 다시 선택 합니다. 
    
9. **DNS 설정 편집** 대화 상자에서 **예**를 선택 합니다.
    
10. 방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.
    
이제 도메인 등록 기관에 레코드가 추가되었습니다. Microsoft 365로 돌아가서 Microsoft 365에 레코드를 찾을 것을 요청합니다.
  
Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.
  
1. Microsoft 관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동합니다.

    
2. **도메인** 페이지에서 확인 중인 도메인을 선택합니다. 
    
3. **설정** 페이지에서 **설정 시작**을 선택합니다.
    
4. **도메인 확인** 페이지에서 **확인**을 선택합니다.
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요. 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드 추가하기
<a name="BKMK_add_MX"> </a>

아래 단계를 따르거나 [비디오를 시청하세요(3:22에 시작)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).
  
> [!NOTE]
> 1und1.de에 등록 한 경우 [여기에 로그인](https://go.microsoft.com/fwlink/?linkid=859152)합니다. 
  
1. 시작 하려면 [이 링크](https://my.1and1.com/)를 사용 하 여 1&1gb os의 도메인 페이지로 이동 합니다. You'll be prompted to log in.
    
2. **도메인 관리**를 선택 합니다.
    
3. **Domain Center (도메인 센터** ) 페이지에서 업데이트 하려는 도메인을 찾은 다음 해당 도메인에 대 한 **패널** ( **v**) 컨트롤을 선택 합니다.
    
4. **도메인 설정** 영역에서 **DNS 설정 편집**을 선택 합니다.
    
5. **Mx 레코드** 섹션의 **메일 교환기 (mx 레코드)** 영역에서 **다른 메일 서버**를 선택 합니다.<br/>(아래로 스크롤해야 할 수 있습니다.)<br/>![1 &amp; 1-BP-구성-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png) <br/>
  
6. MX 레코드가 이미 나열되어 있으면 레코드를 선택한 다음 키보드의 **Delete** 키를 눌러 하나씩 삭제합니다.<br/>(MX 레코드가 나열되어 있지 않으면 다음 단계를 진행합니다.)<br/>![1 &amp; 1-BP-구성-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)<br/>
  
7. **MX 1** 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다. 
    
    |**MX 1**|**우선 순위**|
    |:-----|:-----|
    | *\<domain-key\>*  .mail.protection.outlook.com  <br/>  참고: \<domain-key\> Microsoft 계정에서 가져옵니다. [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)          |10   <br/> 우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)을 참조하세요. <br/> | 
    
    ![1, 1-2 및 3 구성](../../media/3afb04d1-7bbf-4147-89ae-561e14ded26d.png)<br/>
  
8. **저장**을 선택합니다.<br/>(아래로 스크롤해야 할 수 있습니다.)<br/>![1 &amp; 1-BP-구성-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)
  
9. **DNS 설정 편집** 대화 상자에서 **예**를 선택 합니다.<br/>![DNS 설정 편집 대화 상자에서 예 선택](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Microsoft에 필요한 6 개의 CNAME 레코드를 추가 합니다.
<a name="BKMK_add_CNAME"> </a>

1&에는 Microsoft 전자 메일 서비스에 필요한 CNAME 레코드와 함께 MX 레코드를 사용할 수 있도록 해결 방법이 필요 합니다. 이 해결 방법을 사용 하려면 1&, 1gb OS의 하위 도메인 집합을 만들고이를 CNAME 레코드에 할당 해야 합니다.
  
> [!IMPORTANT]
> 이 절차를 시작하기 전에 두 개 이상의 하위 도메인을 사용할 수 있는지 확인하세요. 1&1gb OS에서 하위 도메인을 만든 경험이 이미 있는 경우에만이 솔루션을 사용 하는 것이 좋습니다. 
  
### <a name="basic-cname-records"></a>기본 CNAME 레코드

아래 단계를 따르거나 [비디오를 시청하세요(3:57에 시작)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).
  
> [!NOTE]
> 1und1.de에 등록 한 경우 [여기에 로그인](https://go.microsoft.com/fwlink/?linkid=859152)합니다. 
  
1. 시작 하려면 [이 링크](https://my.1and1.com/)를 사용 하 여 1&1gb os의 도메인 페이지로 이동 합니다. You'll be prompted to log in.
    
2. **도메인 관리**를 선택 합니다.
    
3. **Domain Center (도메인 센터** ) 페이지에서 업데이트 하려는 도메인을 찾은 다음 하위 **도메인 관리**를 선택 합니다.<br/>![1 &amp; 1-BP-구성-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png) <br/>두 개의 하위 도메인을 만들고 각 도메인에 대한 **별칭** 값을 설정합니다.<br/>1&, 1gb OS는 최상위 CNAME 레코드를 하나만 지원 하기 때문에 필요 하지만 Microsoft에서는 여러 CNAME 레코드가 필요 합니다.<br/>먼저 자동 검색 하위 도메인을 만듭니다.
    
4. 하위 **도메인 개요** 섹션에서 하위 **도메인 만들기**를 선택 합니다.
    
    ![1&amp;1-BP-Configure-3-1](../../media/95c63639-eb80-443d-8951-98e8b6cdcc4f.png)
  
5. 새 하위 도메인에 대한 **하위 도메인 만들기** 상자에 다음 표의 **하위 도메인 만들기** 값만 입력하거나 복사하여 붙여넣습니다. (이후 단계에서 **별칭** 값을 추가합니다.)

    |**하위 도메인 만들기**|**별칭**|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com   | 

    ![1 &amp; 1-BP-구성-3-2](../../media/9be45113-ebaf-48e6-983c-a7e6ff9eea45.png)
  
6. 하위 **도메인 만들기**를 선택 합니다.<br/>![1 &amp; 1-BP-구성-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)
  
7. 하위 **도메인 개요** 섹션에서 방금 만든 **자동 검색** 하위 도메인을 찾은 다음 해당 하위 도메인에 대 한 **패널 (v)** 컨트롤을 선택 합니다. <br/>![1 &amp; 1-BP-구성-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)
  
8. 하위 **도메인 설정** 영역에서 **DNS 설정 편집**을 선택 합니다. <br/>![1 &amp; 1-BP-구성-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)
  
9. **A/AAAA 레코드 (Ip 주소)** 섹션의 **Ip 주소 (레코드)** 영역에서 **CNAME**을 선택 합니다.<br/>![1 &amp; 1-BP-구성-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)
  
10. **별칭:** 상자에서 다음 표의 **별칭** 값만 입력하거나 복사하여 붙여넣습니다.<br/> 
    
    |**하위 도메인 만들기**|**별칭**|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com   |

    ![1 &amp; 1-BP-구성-3-7](../../media/afac3118-3337-4f99-98dd-a7ca930230ce.png)
  
11. 고지 사항을 **알고 있음**에 대한 확인란을 선택합니다.<br/>![1 &amp; 1-BP-구성-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)
  
12. **저장**을 선택합니다.<br/>![1 &amp; 1-BP-구성-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)
  
  
### <a name="additional-cname-records"></a>추가 CNAME 레코드

다음 절차에서 만든 추가 CNAME 레코드가 비즈니스용 Skype Online 서비스를 활성화합니다. 이미 만든 2개의 CNAME 레코드를 만들 때와 동일한 단계를 사용합니다.
  
1. 세 번째 하위 도메인(Lyncdiscover)을 만듭니다.<br/>하위 **도메인 개요** 섹션에서 하위 **도메인 만들기**를 선택 합니다.
    
2. 새 하위 도메인에 대한 **하위 도메인 만들기** 상자에 다음 표의 **하위 도메인 만들기** 값만 입력하거나 복사하여 붙여넣습니다. (이후 단계에서 **별칭** 값을 추가합니다.)<br/> 
    
    |**하위 도메인 만들기**|**별칭**|
    |:-----|:-----|
    |lyncdiscover   |webdir.online.lync.com  |
   
3. 하위 **도메인 만들기**를 선택 합니다.
    
4. **도메인 센터** 페이지에서 하위 도메인 **관리**를 선택 합니다.
    
5. 하위 **도메인 개요** 섹션에서 방금 만든 **lyncdiscover** 하위 도메인을 찾은 다음 해당 하위 도메인에 대 한 **패널 (v)** 컨트롤을 선택 합니다. <br/>하위 **도메인 설정** 영역에서 **DNS 설정 편집**을 선택 합니다.
    
6. **A/AAAA 레코드 (Ip 주소)** 섹션의 **Ip 주소 (레코드)** 영역에서 **CNAME**을 선택 합니다.
    
7. **별칭:** 상자에서 다음 표의 **별칭** 값만 입력하거나 복사하여 붙여넣습니다. <br/>
    
    |**하위 도메인 만들기**|**별칭**|
    |:-----|:-----|
    |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |
   
8. **알고** 있는 고 지 사항에 대 한 확인란을 선택 하 고 **저장**을 선택 합니다.
    
9. **DNS 설정 편집** 대화 상자에서 **예**를 선택 합니다.
    
10. 네 번째 하위 도메인(SIP)을 만듭니다. <br/>하위 **도메인 개요** 섹션에서 하위 **도메인 만들기**를 선택 합니다.
    
11. 새 하위 도메인에 대한 **하위 도메인 만들기** 상자에 다음 표의 **하위 도메인 만들기** 값만 입력하거나 복사하여 붙여넣습니다. (이후 단계에서 **별칭** 값을 추가합니다.)<br/>
    
    |**하위 도메인 만들기**|**별칭**|
    |:-----|:-----|
    |sip  <br/> |sipdir.online.lync.com  <br/> |
   
12. 하위 **도메인 만들기**를 선택 합니다.
    
13. **도메인 센터** 페이지에서 하위 도메인 **관리**를 선택 합니다.
    
14. 하위 **도메인 개요** 섹션에서 방금 만든 **sip** 하위 도메인을 찾은 다음 해당 하위 도메인에 대 한 **패널 (v)** 컨트롤을 선택 합니다. <br/>하위 **도메인 설정** 영역에서 **DNS 설정 편집**을 선택 합니다.
    
15. **A/AAAA 레코드 (Ip 주소)** 섹션의 **Ip 주소 (레코드)** 영역에서 **CNAME**을 선택 합니다.
    
16. **별칭:** 상자에서 다음 표의 **별칭** 값만 입력하거나 복사하여 붙여넣습니다. 
    
    |**하위 도메인 만들기**|**별칭**|
    |:-----|:-----|
    |sip  <br/> |sipdir.online.lync.com  <br/> |
   
17. **알고** 있는 고 지 사항에 대 한 확인란을 선택 하 고 **저장**을 선택 합니다.
    
18. **DNS 설정 편집** 대화 상자에서 **예**를 선택 합니다.
    
### <a name="cname-records-needed-for-mdm"></a>MDM에 필요한 CNAME 레코드

> [!IMPORTANT]
> 다른 4개의 CNAME 레코드를 만드는 데 사용한 절차를 따르되 다음 표의 값을 입력합니다. 
  
|**하위 도메인 만들기**|**별칭**|
|:-----|:-----|
|enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |
|enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가

> [!IMPORTANT]
> 도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다. 도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다. 도메인에 이미 SPF 레코드가 있는 경우 Microsoft의 새 SPF 레코드를 만들지 마세요. 대신, 두 값 집합을 모두 포함 하는  *단일*  SPF 레코드가 있도록 현재 레코드에 필수 Microsoft 값을 추가 합니다. 예제가 필요하세요? [Microsoft에 대한 외부 Domain Name System 레코드](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records)를 참조하세요. SPF 레코드의 유효성을 검사 하기 위해 이러한[spf 유효성 검사 도구](../setup/domains-faq.md)중 하나를 사용할 수 있습니다. 
  
아래 단계를 따르거나 [비디오를 시청하세요(5:09에 시작)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).
  
> [!NOTE]
> 1und1.de에 등록 한 경우 [여기에 로그인](https://go.microsoft.com/fwlink/?linkid=859152)합니다. 
  
1. 시작 하려면 [이 링크](https://my.1and1.com/)를 사용 하 여 1&1gb os의 도메인 페이지로 이동 합니다. You'll be prompted to log in.
    
2. **도메인 관리**를 선택 합니다.
    
3. **Domain Center (도메인 센터** ) 페이지에서 업데이트 하려는 도메인을 찾은 다음 해당 도메인에 대 한 **패널** (**v**) 컨트롤을 선택 합니다.
    
4. **도메인 설정** 영역에서 **DNS 설정 편집**을 선택 합니다.
    
5. **TXT 및 SRV 레코드** 섹션에서 **레코드 추가**를 선택 합니다. <br/>(아래로 스크롤해야 할 수 있습니다.)
    
6. In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table. <br/>(드롭다운 목록에서 **Type(종류)** 값을 선택합니다.) <br/>
    
    |**종류**|**Prefix(접두사)**|**Name Value(이름 값)**|
    |:-----|:-----|:-----|
    |TXT  <br/> |(Leave this field empty.)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.           | 
    
    ![TXT 레코드](../../media/0b3ba3b4-64b9-4d68-9ee1-04eb3a17d4c5.png)
  
7. **저장**을 선택합니다.<br/>![레코드 추가](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)
  
8. **저장**을 선택합니다.<br/>![레코드 저장](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)
  
9. **DNS 설정 편집** 대화 상자에서 **예**를 선택 합니다.<br/>![DNS 설정 편집 대화 상자에서 예 선택](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Microsoft 필요한 2개의 SRV 레코드 추가하기

아래 단계를 따르거나 [비디오를 시청하세요(5:51에 시작)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).
  
> [!NOTE]
> 1und1.de에 등록 한 경우 [여기에 로그인](https://go.microsoft.com/fwlink/?linkid=859152)합니다. 
  
1. 시작 하려면 [이 링크](https://my.1and1.com/)를 사용 하 여 1&1gb os의 도메인 페이지로 이동 합니다. You'll be prompted to log in.
    
2. **도메인 관리**를 선택 합니다.
    
3. **Domain Center (도메인 센터** ) 페이지에서 업데이트 하려는 도메인을 찾은 다음 해당 도메인에 대 한 **패널** ( **v**) 컨트롤을 선택 합니다.
    
4. **도메인 설정** 영역에서 **DNS 설정 편집**을 선택 합니다.
    
5. **TXT 및 SRV 레코드** 섹션에서 **레코드 추가**를 선택 합니다.
    
6. 처음 2개의 SRV 레코드를 추가합니다.<br/>**레코드 추가** 영역의 새 레코드용 상자에 다음 표에 있는 첫 번째 행의 값을 입력하거나 복사하여 붙여넣습니다. <br/>(드롭다운 목록에서 **Type (종류** ) 및 **TTL** 값을 선택 합니다.) 
    
    |**유형**|**서비스**|**프로토콜**|**이름**|**호스트**|**Priority(우선 순위)**|**Weight(가중치)**|**Port(포트)**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV  <br/> |sip  <br/> |tls  <br/> |(이 필드는 비워 둡니다.)  <br/> |sipdir.online.lync.com  <br/> |100  <br/> |1   <br/> |443  <br/> |3600(1시간)  <br/> |
    |SRV  <br/> |sipfederationtls  <br/> |tcp  <br/> |(이 필드는 비워 둡니다.)  <br/> |sipfed.online.lync.com  <br/> |100  <br/> |1   <br/> |5061  <br/> |3600(1시간)  <br/> |  
    
    ![1 &amp; 1-BP-구성-5-1](../../media/087e337d-926b-42ff-b11d-b449cfaed76c.png)
  
7. **저장**을 선택합니다. <br/>![1 &amp; 1-BP-구성-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)
  
8. **저장**을 선택합니다. <br/>![1 &amp; 1-BP-구성-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)
  
9. **DNS 설정 편집** 대화 상자에서 **예**를 선택 합니다. <br/>![DNS 설정 편집 대화 상자에서 예 선택](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)
  
10. 다른 SRV 레코드를 추가합니다. <br/>**TXT 및 SRV 레코드** 섹션에서 **레코드 추가**를 선택 합니다. <br/>**레코드 추가** 영역에서 표에 있는 다른 행의 값을 사용 하 여 레코드를 만든 다음 다시 **추가**, **저장**및 **예** 를 선택 하 여 레코드를 완성 합니다. 
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요. 
  
