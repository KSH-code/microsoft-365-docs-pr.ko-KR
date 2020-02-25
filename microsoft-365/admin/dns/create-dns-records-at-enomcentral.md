---
title: eNomCentral에서 Office 365용 DNS 레코드 만들기
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
ms.assetid: a6626053-a9c8-445b-81ee-eeb6672fae77
description: 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 및 기타 365 서비스에 대 한 DNS 레코드를 설정 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: c4cd12667ebf945aa2f354ccfa0bad1688dc9863
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42245220"
---
# <a name="create-dns-records-at-enomcentral-for-office-365"></a>eNomCentral에서 Office 365용 DNS 레코드 만들기

 **원하는 정보는 찾지 못한 경우 [도메인 질문과 대답을 확인](../setup/domains-faq.md)** 하세요. 
  
DNS 호스팅 공급자로 eNomCentral을 사용하고 있는 경우, 이 문서에 나와 있는 단계를 따라 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 등에 대한 DNS 레코드를 설정합니다.
  
eNomCentral에서 이러한 레코드를 추가하고 나면 도메인이 Office 365 서비스에서 작동하도록 설정됩니다.
  
Office 365에서 웹 사이트의 웹 호스팅 및 DNS에 대한 자세한 내용은 [Office 365에서 공개 웹 사이트 사용](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)을 참조하세요.
  
> [!NOTE]
>  일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 
  
## <a name="add-a-txt-record-for-verification"></a>확인을 위해 TXT 레코드 추가
<a name="BKMK_verify"> </a>

Office 365에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Office 365에 도메인을 소유하고 있음을 증명할 수 있습니다.
  
> [!NOTE]
> 이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다. 
  
아래 단계를 따르거나 [비디오를 시청하세요(0:46에 시작)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. 시작하려면 [이 링크](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)를 사용하여 eNom Central의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.
    
    ![eNom-BP-구성-1-1](../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. **내 도메인**아래에서 편집 하려는 도메인의 이름을 선택 합니다.
    
    ![eNom-BP-구성-1-2](../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. **Manage Domain(도메인 관리)** 드롭다운 목록에서 **Host Records(호스트 레코드)** 를 선택합니다.
    
    ![eNom-BP-Verify-1-1](../media/6e4184a1-9525-47a6-8a8a-9600126c0db4.png)
  
4. In the boxes for the new record, type or copy and paste the values from the following table.
    
    (Choose the **Record Type** value from the drop-down list.) 
    
    ||||
    |:-----|:-----|:-----|
    |**Host Name** <br/> |**Record Type** <br/> |**Address(주소)** <br/> |
    |@  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **참고:** 예를 들면 다음과 같습니다. 여기에는 Office 365의 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.           [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![eNom-BP-Verify-1-2](../media/e1f95529-46a6-40f9-9709-9fe66f373bcf.png)
  
5. **저장**을 선택 합니다.
    
    ![eNom-BP-Verify-1-3](../media/d6277ab0-5d03-44e0-968f-fd5de1905423.png)
  
6. 방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.
    
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

아래 단계를 따르거나 [비디오를 시청하세요(3:40에 시작)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. 시작하려면 [이 링크](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)를 사용하여 eNom Central의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.
    
    ![eNom-BP-구성-1-1](../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. **내 도메인**아래에서 편집 하려는 도메인의 이름을 선택 합니다.
    
    ![eNom-BP-구성-1-2](../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. **Manage Domain(도메인 관리)** 드롭다운 목록에서 **Email Settings(전자 메일 설정)** 를 선택합니다.
    
    ![eNom-BP-구성-1-3](../media/4b438629-afdf-4a47-ab11-56644cdb6158.png)
  
4. **Service Selection**(서비스 선택) 드롭다운 목록에서 **User (MX)**(사용자(MX))를 선택합니다.
    
    ![eNom-BP-구성-1-4](../media/7680ab48-b8d1-4573-b20f-4745a5d7c079.png)
  
5. In the boxes for the new record, type or copy and paste the values from the following table.
    
    |**Host Name**|**주소**|**기본 설정**|
    |:-----|:-----|:-----|
    |@  <br/> | *\<domain-key\>*  .mail.protection.outlook.com.  <br/> **This value MUST end with a period (.)** <br/> **참고:** Office 365 계정에서 * \<도메인\> 키* 를 가져옵니다.           [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)          |10   <br/> 우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)을 참조하세요. <br/> |
       
   ![eNom-BP-구성-2-1](../media/c32e8954-8209-4f77-a3a8-4b7aeea325d5.png)
  
6. **저장**을 선택 합니다.
    
    ![eNom-BP-구성-2-2](../media/cf3058ea-9d30-4747-8cf0-2bc13d5ec6be.png)
  
7. 기본의 다른 MX 레코드가 있으면 해당 레코드의 확인란을 선택하여 레코드를 선택합니다.
    
    ![eNom-BP-구성-2-3](../media/5017ed03-ca76-4c5c-93a7-84ffe24125dc.png)
  
8. 확인을 클릭 하 여 **삭제**를 선택 합니다.
    
    ![eNom-BP-구성-2-4](../media/072dc039-bddb-4c1f-bb44-5660e77f14b0.png)
  
## <a name="add-the-cname-records-that-are-required-for-office-365"></a>Office 365에 필요한 CNAME 레코드 추가
<a name="BKMK_add_CNAME"> </a>

아래 단계를 따르거나 [비디오를 시청하세요(4:24에 시작)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. 시작하려면 [이 링크](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)를 사용하여 eNom Central의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.
    
    ![eNom-BP-구성-1-1](../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. **내 도메인**아래에서 편집 하려는 도메인의 이름을 선택 합니다.
    
    ![eNom-BP-구성-1-2](../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. **Manage Domain(도메인 관리)** 드롭다운 목록에서 **Host Records(호스트 레코드)** 를 선택합니다.
    
    ![eNom-BP-구성-1-5](../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. **새 행**을 선택 합니다.
    
    ![eNom-BP-구성-3-1](../media/a30f0a88-7b09-411e-9133-e7965bcf1de0.png)
  
5. 6개의 새 레코드 상자에서 다음 값을 입력하거나 복사하여 붙여넣습니다.
    
        (Choose the **Record Type** value from the drop-down list.) 
        
    |**Host Name**|**Record Type**|**주소**|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME (Alias)  <br/> |autodiscover.outlook.com  <br/> **This value MUST end with a period (.)** <br/> |
    |sip  <br/> |CNAME (Alias)  <br/> |sipdir.online.lync.com  <br/> **This value MUST end with a period (.)** <br/> |
    |lyncdiscover  <br/> |CNAME (Alias)  <br/> |webdir.online.lync.com  <br/> **This value MUST end with a period (.)** <br/> |
    |enterpriseregistration  <br/> |CNAME (Alias)(CNAME(별칭))  <br/> |enterpriseregistration.windows.net  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |
    |enterpriseenrollment  <br/> |CNAME (Alias)(CNAME(별칭))  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |
   
    ![eNom-BP-구성-3-2](../media/672371c0-51af-44ba-bb18-80286b7676c1.png)
  
6. **저장**을 선택 합니다.
    
    ![eNom-BP-구성-3-3](../media/027b57ce-5699-408b-993b-e46a9ac31090.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.
  
아래 단계를 따르거나 [비디오를 시청하세요(5:12에 시작)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. 시작하려면 [이 링크](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)를 사용하여 eNom Central의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.
    
    ![eNom-BP-구성-1-1](../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. **내 도메인**아래에서 편집 하려는 도메인의 이름을 선택 합니다.
    
    ![eNom-BP-구성-1-2](../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. **Manage Domain(도메인 관리)** 드롭다운 목록에서 **Host Records(호스트 레코드)** 를 선택합니다.
    
    ![eNom-BP-구성-1-5](../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. 새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.
    
    (Choose the **Record Type** value from the drop-down list.) 
    
    |**Host Name**|**Record Type**|**Address(주소)**|
    |:-----|:-----|:-----|
    |@  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/>**참고:** 모든 공백이 올바르게 유지 되도록이 항목을 복사 하 여 붙여 넣는 것이 좋습니다.           |
   
   ![eNom-BP-구성-4-1](../media/64c68697-258d-4044-84b1-c28f4a402e3b.png)
  
5. **저장**을 선택 합니다.
    
    ![eNom-BP-구성-4-2](../media/89f4effa-349e-4734-96a5-cd80b0cecd60.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Office 365에 필요한 2개의 SRV 레코드 추가
<a name="BKMK_add_SRV"> </a>

아래 단계를 따르거나 [비디오를 시청하세요(5:50에 시작)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. 시작하려면 [이 링크](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)를 사용하여 eNom Central의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.
    
    ![eNom-BP-구성-1-1](../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. **내 도메인**아래에서 편집 하려는 도메인의 이름을 선택 합니다.
    
    ![eNom-BP-구성-1-2](../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. **Manage Domain(도메인 관리)** 드롭다운 목록에서 **Host Records(호스트 레코드)** 를 선택합니다.
    
    ![eNom-BP-구성-1-5](../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. **새 행**오른쪽에서 **SRV 또는 SPF 레코드 추가**를 선택 합니다.
    
    ![eNom-BP-구성-5-1](../media/c73c154d-5aa0-41ef-be25-f43129eb178c.png)
  
5. 두 개의 새 레코드 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.
    
    |**서비스**|**프로토콜**|**우선 순위**|**가중치**|**포트**|**대상          (호스트 이름)**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |_tls  <br/> |100  <br/> |개  <br/> |443  <br/> |sipdir.online.lync.com  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |
    |_sipfederationtls  <br/> |_tcp  <br/> |100  <br/> |개  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |
   
    ![eNom-BP-구성-5-2](../media/4d478f40-780f-43b9-940b-712b09da8c63.png)
  
6. **저장** 을 선택
    
    ![eNom-BP-구성-5-3](../media/d03b6f75-49f2-471d-978d-d32c47cd6aa7.png)
  
> [!NOTE]
>  일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 
  

