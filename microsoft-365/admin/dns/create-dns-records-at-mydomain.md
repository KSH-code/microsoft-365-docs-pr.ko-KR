---
title: MyDomain에서 Office 365용 DNS 레코드 만들기
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9982191d-ed79-46a9-b2e7-317d1a3a9867
description: My Domain for Office 365에서 도메인을 확인하고 전자 메일, 비즈니스용 Skype 온라인 및 기타 서비스에 대한 DNS 레코드를 설정하는 방법을 알아보세요.
ms.openlocfilehash: 1a75c2ab0077cac07781e5102c43e53ed965b1df
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211694"
---
# <a name="create-dns-records-at-mydomain-for-office-365"></a>MyDomain에서 Office 365용 DNS 레코드 만들기


  
 원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.md)** 하세요. 
  
> [!CAUTION]
> MyDomain 웹 사이트는 SRV 레코드를 지원하지 않습니다. 따라서 일부 비즈니스용 Skype Online 및 Outlook Web App 기능이 작동하지 않습니다. 어떤 Office 365 계획을 사용하든 관계없이 MyDomain에서 DNS 레코드를 관리하는 경우에는 [상당한 서비스 제한 사항](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx)이 있으며 다른 DNS 호스팅 공급자로 전환해야 할 수도 있습니다. 
  
서비스 제한 사항에도 불구하고 MyDomain에서 Office 365 DNS 레코드를 관리하려는 경우 이 문서의 단계를 따라 전자 메일, 비즈니스용 Skype Online 등에 대한 DNS 레코드를 설정합니다.
    
MyDomain에서 이러한 레코드를 추가하고 나면 도메인이 Office 365 서비스에서 작동하도록 설정됩니다.
  
Office 365에서 웹 사이트의 웹 호스팅 및 DNS에 대한 자세한 내용은 [Office 365에서 공개 웹 사이트 사용](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)을 참조하세요.
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [Office 365에서 도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요. 
  
## <a name="add-a-txt-record-for-verification"></a>확인을 위해 TXT 레코드 추가
<a name="BKMK_verify"> </a>

Office 365에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Office 365에 도메인을 소유하고 있음을 증명할 수 있습니다.
  
> [!NOTE]
> 이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다. 
  
1. 시작하려면 [이 링크](https://www.mydomain.com/controlpanel)를 사용하여 MyDomain의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.
    
2. **내 즐겨 찾기** 섹션에서 **도메인 센터**를 선택합니다.
    
3. **도메인**에서 편집할 도메인 이름을 선택합니다.
    
4. **개요** 행에서 **DNS**를 선택합니다.
    
5. **수정** 드롭다운 목록에서 **TXT/SPF 레코드**를 선택합니다.
    
6. 
            **콘텐츠** 아래의 새 레코드에 대한 상자에 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.
    
    ||
    |:-----|
    |**콘텐츠** <br/> |
    |MS=ms *XXXXXXXX*  <br/> **참고:** 이 값은 예시입니다. 여기에는 Office 365의 표에 있는 특정 **보낼 대상 또는 지점** 값을 사용합니다. [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)          |
   
7. **추가**를 선택합니다.
    
8. 방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.
    
이제 도메인 등록 기관에 레코드가 추가되었습니다. Office 365로 돌아가서 Office 365에 레코드를 찾을 것을 요청합니다.
  
Office 365에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.
  
1. I관리 센터에서 ** 설정 ** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인 </a> 페이지로 이동하십시오.
    
2. **도메인** 페이지에서 확인 중인 도메인을 선택합니다. 
    
3. **설정** 페이지에서 **설정 시작**을 선택합니다.
    
4. **도메인 확인** 페이지에서 **확인**을 선택합니다.
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [Office 365에서 도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요. 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>사용자 도메인의 전자 메일이 Office 365로 전송되도록 MX 레코드 추가
<a name="BKMK_add_MX"> </a>

1. 시작하려면 [이 링크](https://www.mydomain.com/controlpanel)를 사용하여 MyDomain의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.
    
2. **내 즐겨 찾기** 섹션에서 **도메인 센터**를 선택합니다.
    
3. **도메인**에서 편집할 도메인 이름을 선택합니다.
    
4. **개요** 행에서 **DNS**를 선택합니다.
    
5. 
            **Modify(수정)** 드롭다운 목록에서 **MX Record(MX 레코드)** 를 선택합니다.
    
    ![MyDomain-BP-Configure-2-1](../../media/bbfba978-8c53-471b-8c9e-8ae62e559d15.png)
  
6. 새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.
    
    |**우선 순위**|**Host(호스트)**|**연결 대상**|
    |:-----|:-----|:-----|
    |0  <br/> 우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)을 참조하세요. <br/> |@  <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **참고:** Office 365 계정에서 \<*도메인-키*\>를 가져옵니다. > [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![MyDomain-BP-Configure-2-2](../../media/3e19cec3-7f3b-493d-81f7-cda30ba007d5.png)
  
7. **추가**를 선택합니다.
    
    ![MyDomain-BP-Configure-2-3](../../media/1a1951a8-11d7-405d-bef5-285bbb053ce8.png)
  
8. 기존의 다른 MX 레코드가 있는 경우 삭제할 각 레코드에 대해 **Action(작업)** 열에서 **Remove(제거)** 를 선택합니다. 
    
    ![MyDomain-BP-Configure-2-4](../../media/42576149-e056-4a81-a5fd-2c5dfac44e2e.png)
  
9. **확인**을 선택합니다.
    
    ![MyDomain-BP-Configure-2-5](../../media/d6b70eb7-b79c-499e-82ff-ecef2e300368.png)
  
## <a name="add-the-cname-records-that-are-required-for-office-365"></a>Office 365에 필요한 CNAME 레코드 추가
<a name="BKMK_add_CNAME"> </a>

1. 시작하려면 [이 링크](https://www.mydomain.com/controlpanel)를 사용하여 MyDomain의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.
    
2. **내 즐겨 찾기** 섹션에서 **도메인 센터**를 선택합니다.
    
3. **도메인**에서 편집할 도메인 이름을 선택합니다.
    
4. **개요** 행에서 **DNS**를 선택합니다.
    
5. 
            **Modify(수정)** 드롭다운 목록에서 **CNAME Alias(CNAME 별칭)** 를 선택합니다.
    
    ![MyDomain-BP-Configure-3-1](../../media/628267fc-d37b-42ef-bb92-265284e339ac.png)
  
6. 첫 번째 CNAME 레코드를 추가합니다.
    
    새 레코드의 상자에서 다음 표에 있는 첫 번째 행의 값을 입력하거나 복사하여 붙여넣습니다. 
    
    |**Host(호스트)**|**연결 대상**|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![MyDomain-BP-Configure-3-2](../../media/3c8660b3-40bb-453d-8b99-4d22032bc4b3.png)
  
7. **추가**를 선택하여 첫 번째 레코드를 추가합니다. 
    
    ![MyDomain-BP-Configure-3-3](../../media/103a1d99-70da-4fdf-9291-7dd058ec6c4a.png)
  
8. 두 번째 CNAME 레코드를 추가합니다.
    
    위 표의 두 번째 행의 값을 사용한 다음 **추가**를 선택하여 두 번째 레코드를 추가합니다. 
    
    표의 세 번째, 네 번째, 다섯 번째 및 여섯 번째 행의 값을 사용하여 같은 방법으로 나머지 레코드를 추가합니다.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다. 도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values. 예제가 필요하세요? [Office 365에 대한 외부 Domain Name System 레코드](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords)를 참조하세요. To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md). 
  
1. 시작하려면 [이 링크](https://www.mydomain.com/controlpanel)를 사용하여 MyDomain의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.
    
2. **내 즐겨 찾기** 섹션에서 **도메인 센터**를 선택합니다.
    
3. **도메인**에서 편집할 도메인 이름을 선택합니다.
    
4. **개요** 행에서 **DNS**를 선택합니다.
    
5. 
            **수정** 드롭다운 목록에서 **TXT/SPF 레코드**를 선택합니다.
    
    ![MyDomain-BP-Configure-4-1](../../media/c461c762-52e6-4fde-b5bc-4dd5e5d62ed3.png)
  
6. 
            **콘텐츠** 아래의 새 레코드에 대한 상자에 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.
    
    |**콘텐츠**|
    |:-----|
    |v=spf1 include:spf.protection.outlook.com -all  <br/> **참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.           |
   
    ![MyDomain-BP-Configure-4-2](../../media/17d43106-88e6-47e5-aeba-0f18484acf3e.png)
  
7. **추가**를 선택합니다.
    
    ![MyDomain-BP-Configure-4-3](../../media/b3670563-b620-470c-a42b-2c77888981f8.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Office 365에 필요한 2개의 SRV 레코드 추가
<a name="BKMK_add_SRV"> </a>

> [!CAUTION]
> MyDomain 웹 사이트는 SRV 레코드를 지원하지 않습니다. 따라서 일부 비즈니스용 Skype Online 및 Outlook Web App 기능이 작동하지 않습니다. 어떤 Office 365 계획을 사용하든 관계없이 MyDomain에서 DNS 레코드를 관리하는 경우에는 [상당한 서비스 제한 사항](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx)이 있으며 다른 DNS 호스팅 공급자로 전환해야 할 수도 있습니다. 
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [Office 365에서 도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요. 
  
