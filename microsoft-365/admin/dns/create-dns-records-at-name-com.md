---
title: name.com에서 Office 365용 DNS 레코드 만들기
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
ms.assetid: 9ddcc2fc-9433-4335-8192-6ffb1f541087
description: 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대 한 DNS 레코드를 Office 365 용 name.com에 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: f21a40f543ff3a9faffe6ffba98f4d541b2a7a7b
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2020
ms.locfileid: "42349982"
---
# <a name="create-dns-records-at-namecom-for-office-365"></a>name.com에서 Office 365용 DNS 레코드 만들기

 **원하는 정보는 찾지 못한 경우 [도메인 질문과 대답을 확인](../setup/domains-faq.md)** 하세요. 
  
DNS 호스팅 공급자로 name.com을 사용하고 있는 경우, 이 문서에 나와 있는 단계를 따라 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 등에 대한 DNS 레코드를 설정합니다.
  
name.com에서 이러한 레코드를 추가하고 나면 도메인이 Office 365 서비스에서 작동하도록 설정됩니다.
  
Office 365에서 웹 사이트의 웹 호스팅 및 DNS에 대한 자세한 내용은 [Office 365에서 공개 웹 사이트 사용](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)을 참조하세요.
  
> [!NOTE]
> 일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 
  
## <a name="add-a-txt-record-for-verification"></a>확인을 위해 TXT 레코드 추가
<a name="BKMK_verify"> </a>

Office 365에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Office 365에 도메인을 소유하고 있음을 증명할 수 있습니다.
  
> [!NOTE]
> 이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다. 
  
1. 시작하려면 [이 링크](https://www.name.com/account/domain)를 사용하여 name.com의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. **내 도메인**아래에서 수정할 도메인의 이름을 선택 합니다.
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. **세부 정보** 열에서 * * DNS 레코드 * *를 선택 합니다. 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. 새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여 넣습니다.
    
    (Choose the **Type** value from the drop-down list.) 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**Type(종류)** <br/> |**호스트** <br/> |**응답** <br/> |**TTL** <br/> |
    |TXT  <br/> |(Leave this field empty.)  <br/> |MS=ms *XXXXXXXX*  <br/> **참고:** 이 값은 예시입니다. 여기에는 Office 365의 표에 있는 특정 **보낼 대상 또는 지점** 값을 사용합니다.           [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)          |Use the default value (300).  <br/> |
   
    ![이름-BP-Verify-1-1](../../media/0c352fd3-cf84-439f-a481-0705e225cc54.png)
  
5. **레코드 추가**를 선택 합니다.
    
    ![Name-BP-Verify-1-2](../../media/816fc60b-17ab-4982-8849-6c3fcf3ca3d6.png)
  
6. 방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.
    
이제 도메인 등록 기관에 레코드가 추가되었습니다. Office 365로 돌아가서 Office 365에 레코드를 찾을 것을 요청합니다.
  
Office 365에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.
  
1. I관리 센터에서 ** 설정 ** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인 </a> 페이지로 이동하십시오.
    
2. **도메인** 페이지에서 확인 중인 도메인을 선택합니다. 
    
    
  
3. **설정** 페이지에서 **설정 시작**을 선택합니다.
    
    
  
4. **도메인 확인** 페이지에서 **확인**을 선택합니다.
    
    
  
> [!NOTE]
> 일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>사용자 도메인의 전자 메일이 Office 365로 전송되도록 MX 레코드 추가
<a name="BKMK_add_MX"> </a>

1. 시작하려면 [이 링크](https://www.name.com/account/domain)를 사용하여 name.com의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. **내 도메인**아래에서 수정할 도메인의 이름을 선택 합니다.
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. **세부 정보** 열에서 **DNS 레코드**를 선택 합니다. 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. 새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여 넣습니다.
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Type(종류)**|**호스트**|**응답**|**TTL**|**우선 순위**|
    |:-----|:-----|:-----|:-----|:-----|
    |MX  <br/> |(이 필드는 비워 둡니다.)  <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **참고:** Office 365 계정에서 * \<도메인\> 키* 를 가져옵니다.           [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)          |Use the default value (300).  <br/> |개  <br/> 우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)을 참조하세요. <br/> |
   
   ![이름-BP-구성-2-1](../../media/11ba2160-fc8e-4196-bb15-2b7c6d49c8fc.png)
  
5. **레코드 추가**를 선택 합니다.
    
    ![Name-BP-Configure-2-2](../../media/fd09f161-7cc4-4723-aec2-5fa801bd19e9.png)
  
6. 다른 MX 레코드가 있으면 다음 2단계 절차를 사용하여 각 레코드를 삭제합니다.
    
    각각의 다른 MX 레코드에 대해 **작업** 열에서 **삭제** 를 선택 합니다. 
    
    ![Name-BP-Configure-2-3](../../media/16734a98-31c4-4023-a2a5-10b7c95bc58e.png)
  
    각 삭제를 확인 하려면 **작업** 열에서 **삭제** 를 다시 선택 합니다. 
    
    ![Name-BP-Configure-2-4](../../media/409c21c5-51f4-4244-bb84-5d32084224b2.png)
  
    다른 MX 레코드를 각각 삭제할 때까지 이 2단계 절차를 반복합니다.
    
## <a name="add-the-cname-records-that-are-required-for-office-365"></a>Office 365에 필요한 CNAME 레코드 추가
<a name="BKMK_add_CNAME"> </a>

1. 시작하려면 [이 링크](https://www.name.com/account/domain)를 사용하여 name.com의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. **내 도메인**아래에서 수정할 도메인의 이름을 선택 합니다.
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. **세부 정보** 열에서 **DNS 레코드**를 선택 합니다. 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. 첫 번째 CNAME 레코드를 추가합니다.
    
    새 레코드의 상자에서 다음 표에 있는 첫 번째 행의 값을 입력하거나 복사하여 붙여넣습니다. 
    
    (드롭다운 목록에서 **Type(종류)** 값을 선택합니다.) 
    
    |**Type(종류)**|**호스트**|**응답**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |autodiscover  <br/> |autodiscover.outlook.com  <br/> |기본값(300)을 사용합니다.  <br/> |
    |CNAME  <br/> |sip  <br/> |sipdir.online.lync.com  <br/> |기본값(300)을 사용합니다.  <br/> |
    |CNAME  <br/> |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |기본값(300)을 사용합니다.  <br/> |
    |CNAME  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |기본값(300)을 사용합니다.  <br/> |
    |CNAME  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |기본값(300)을 사용합니다.  <br/> |
   
   ![이름-BP-구성-3-1](../../media/4e34caaf-b418-40ec-abfa-fe62175a87c2.png)
  
5. **레코드 추가** 를 선택 하 여 첫 번째 레코드를 추가 합니다. 
    
    ![Name-BP-Configure-3-2](../../media/1053c2a7-07c3-4c1b-b54a-1c02881fb0ec.png)
  
6. 두 번째 CNAME 레코드를 추가합니다.
    
    위 표에 있는 두 번째 행의 값을 사용한 다음 **레코드 추가** 를 선택 하 여 두 번째 레코드를 추가 합니다. 
    
    표의 세 번째, 네 번째, 다섯 번째 및 여섯 번째 행의 값을 사용하여 같은 방법으로 나머지 레코드를 추가합니다.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다. 도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values. 
  
1. 시작하려면 [이 링크](https://www.name.com/account/domain)를 사용하여 name.com의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. **내 도메인**아래에서 수정할 도메인의 이름을 선택 합니다.

    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. **세부 정보** 열에서 **DNS 레코드**를 선택 합니다. 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. 새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여 넣습니다.
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Type(종류)**|**호스트**|**응답**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |(Leave this field empty.)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **참고: ** 모든 간격이 올바르게 유지되도록 이 항목을 복사하여 붙여넣는 것이 좋습니다.           |Use the default value (300).  <br/> |
   
   ![이름-BP-구성-4-1](../../media/cbbfc071-840a-4ffa-a59e-0dfce03063cc.png)
  
5. **레코드 추가**를 선택 합니다.
    
    ![Name-BP-Configure-4-2](../../media/db1e0e09-2b95-4fc1-88bd-e86da536921f.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Office 365에 필요한 2개의 SRV 레코드 추가
<a name="BKMK_add_SRV"> </a>

1. 시작하려면 [이 링크](https://www.name.com/account/domain)를 사용하여 name.com의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. **내 도메인**아래에서 수정할 도메인의 이름을 선택 합니다.
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. **세부 정보** 열에서 **DNS 레코드 +** 를 선택 합니다. 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. 첫 번째 SRV 레코드를 추가합니다.
    
    새 레코드의 상자에서 다음 표에 있는 첫 번째 행의 값을 입력하거나 복사하여 붙여넣습니다.
    
    (드롭다운 목록에서 **Type(종류)** 값을 선택합니다.) 
    
    |**유형**|**서비스**|**가중치**|**TTL**|**우선 순위**|**프로토콜**|**포트**|**대상**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV|sip|개|기본값(300)을 사용합니다.|100|tls|443|sipdir.online.lync.com <br> **참고: ** 모든 간격이 올바르게 유지되도록 이 항목을 복사하여 붙여넣는 것이 좋습니다.           |
    |SRV|sipfederationtls|개|기본값(300)을 사용합니다.|100|tcp|5061|sipfed.online.lync.com <br>**참고: ** 모든 간격이 올바르게 유지되도록 이 항목을 복사하여 붙여넣는 것이 좋습니다.           |
   
   ![이름-BP-구성-5-1](../../media/d9a885fd-7300-45b6-ad4c-0b4bf1067560.png)
  
5. **레코드 추가**를 선택 합니다.

    ![Name-BP-Configure-5-2](../../media/a804d51d-8f57-4b0b-8bd6-a52eb1c87a97.png)
  
6. 두 번째 SRV 레코드 추가:

위 표에 있는 다음 행의 값을 사용한 다음 **레코드 추가** 를 선택 하 여 두 번째 레코드를 추가 합니다.

>[!NOTE]
>일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.
