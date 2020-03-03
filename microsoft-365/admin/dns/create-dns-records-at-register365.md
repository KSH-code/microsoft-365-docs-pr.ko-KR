---
title: Register365에서 Office 365용 DNS 레코드 만들기
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
ms.assetid: 004030b4-10ad-4026-96e7-011b6afc7e73
description: 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대 한 DNS 레코드를 Office 365 용 R 365에 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: 7f9398e14ea5280948829b263d4cd66d61fab682
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2020
ms.locfileid: "42362853"
---
# <a name="create-dns-records-at-register365-for-office-365"></a>Register365에서 Office 365용 DNS 레코드 만들기

 **원하는 정보는 찾지 못한 경우 [도메인 질문과 대답을 확인](../setup/domains-faq.md)** 하세요. 
  
DNS 호스팅 공급자로 Register365를 사용하고 있는 경우, 이 문서에 나와 있는 단계를 따라 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 등에 대한 DNS 레코드를 설정합니다. 
  
다음은 추가할 기본 레코드입니다.  
  
- [확인을 위해 TXT 레코드 추가](#add-a-txt-record-for-verification)
    
- [사용자 도메인의 전자 메일이 Office 365로 전송되도록 MX 레코드 추가](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [Office 365에 필요한 6개의 CNAME 레코드 추가](#add-the-six-cname-records-that-are-required-for-office-365)
    
- [전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [Office 365에 필요한 2개의 SRV 레코드 추가](#add-the-two-srv-records-that-are-required-for-office-365)
    
Office 365에서 이러한 레코드를 추가하고 나면 도메인이 Office 365 서비스에서 작동하도록 설정됩니다.
  
Office 365에서 웹 사이트의 웹 호스팅 및 DNS에 대한 자세한 내용은 [Office 365에서 공개 웹 사이트 사용](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)을 참조하세요.
  
> [!NOTE]
>  일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 
  
## <a name="add-a-txt-record-for-verification"></a>확인을 위해 TXT 레코드 추가
<a name="BKMK_verify"> </a>

Office 365에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Office 365에 도메인을 소유하고 있음을 증명할 수 있습니다.
  
> [!NOTE]
> 이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다. 
  
1. 시작하려면 [이 링크](https://admin.register365.com/dns/)를 사용하여 Register365의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.
    
    ![제어판 로그인 페이지](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. **대시보드** 페이지에서 업데이트 중인 도메인 이름을 찾은 다음 드롭다운 목록에서 **DNS 설정**을 선택합니다. 
    
    (You may have to scroll down.)
    
    ![목록에서 DNS 설정 선택](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    행을 추가 해야 하는 경우 **a/CNAME 레코드 추가 (+)** 를 선택 합니다.
    
    (You may have to scroll down.)
    
    |**호스트 이름**|**종류**|**결과**|
    |:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **참고:** 이 값은 예시입니다. 여기에는 Office 365의 표에 있는 특정 **보낼 대상 또는 지점** 값을 사용합니다.           [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![DNS 영역 추가/수정 페이지에서 값 입력](../../media/22326005-de95-464d-8e33-08ea31a89b2d.png)
  
4. **저장**을 선택합니다.
    
    (You may have to scroll down.)
    
    ![저장을 선택](../../media/157cfb98-d5d0-48a3-8dd1-c4e759c2f8a8.png)
  
5. 방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.
    
이제 도메인 등록 기관에 레코드가 추가되었습니다. Office 365로 돌아가서 Office 365에 레코드를 찾을 것을 요청합니다.
  
Office 365에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.
  
1. I관리 센터에서 ** 설정 ** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인 </a> 페이지로 이동하십시오.
    
2. **도메인** 페이지에서 확인 중인 도메인을 선택합니다. 
    
    
  
3. **설정** 페이지에서 **설정 시작**을 선택합니다.
    
    
  
4. **도메인 확인** 페이지에서 **확인**을 선택합니다.
    
    
  
> [!NOTE]
>  일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>사용자 도메인의 전자 메일이 Office 365로 전송되도록 MX 레코드 추가
<a name="BKMK_add_MX"> </a>

1. 시작하려면 [이 링크](https://admin.register365.com/dns/)를 사용하여 Register365의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.
    
    ![제어판 로그인 페이지](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. **대시보드** 페이지에서 업데이트 중인 도메인 이름을 찾은 다음 드롭다운 목록에서 **DNS 설정**을 선택합니다. 
    
    (You may have to scroll down.)
    
    ![목록에서 DNS 설정 선택](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. **Add/Modify DNS Zone**(DNS 영역 추가/수정) 페이지의 **Mail exchange records**(메일 교환 레코드) 구역에서 새 레코드의 상자에 다음 표의 값을 입력하거나 복사하여 붙여넣습니다. 
    
    (You may have to scroll down.)
    
    |**호스트 이름**|**우선 순위**|**결과**|
    |:-----|:-----|:-----|
    |(이 필드는 비워 둡니다.)  <br/> |개  <br/> 우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)을 참조하세요. <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **참고:** Office 365 계정에서 * \<도메인\> 키* 를 가져옵니다.  [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)     |
   
    ![DNS 영역 추가/수정 페이지에서 값 입력](../../media/2d3645a8-9cb8-435e-b895-5535b6b1fffd.png)
  
4. **저장**을 선택합니다.
    
    (You may have to scroll down.)
    
    ![저장을 선택](../../media/0e565fb0-a126-4a48-8ff7-2c2d79d4af32.png)
  
5. **Mail exchange records**(메일 교환 레코드) 구역에 다른 MX 레코드가 있으면 하나씩 선택한 후 키보드의 **Delete** 키를 눌러 삭제합니다. 
    
    ![Deleting records in the Mail exchange records section](../../media/8cc37e4f-2e85-4242-af0e-78149434167f.png)
  
6. **저장**을 선택합니다.
    
    (You may have to scroll down.)
    
    ![저장을 선택](../../media/1fb69bb5-b5df-4060-adf1-eb26cfaa6c4f.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a>Office 365에 필요한 6개의 CNAME 레코드 추가
<a name="BKMK_add_CNAME"> </a>

1. 시작하려면 [이 링크](https://admin.register365.com/dns/)를 사용하여 Register365의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.
    
    ![제어판 로그인 페이지](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. **대시보드** 페이지에서 업데이트 중인 도메인 이름을 찾은 다음 드롭다운 목록에서 **DNS 설정**을 선택합니다. 
    
    (You may have to scroll down.)
    
    ![목록에서 DNS 설정 선택](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. **Add/Modify DNS Zone**(DNS 영역 추가/수정) 페이지의 **A, CNAME, AAAA, TXT and NS records**(A, CNAME, AAAA, TXT 및 NS 레코드) 구역에서 새 레코드의 상자에 다음 표의 값을 입력하거나 복사하여 붙여넣습니다. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    행을 추가 해야 하는 경우 **a/CNAME 레코드 추가 (+)** 를 선택 합니다.
    
    (아래로 스크롤해야 할 수 있습니다.)
    
    |****Host name(호스트 이름)****|****Type(종류)****|****결과****|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![DNS 영역 추가/수정 페이지에서 값 입력](../../media/3b79f0de-9cab-4c98-8fa8-c92b35241e8b.png)
  
4. **저장**을 선택합니다.
    
    ![저장을 선택](../../media/8ded6428-af97-4fd8-9104-477fa22a5586.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다. 도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values. 
  
1. 시작하려면 [이 링크](https://admin.register365.com/dns/)를 사용하여 Register365의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.
    
    ![제어판 로그인 페이지](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. **대시보드** 페이지에서 업데이트 중인 도메인 이름을 찾은 다음 드롭다운 목록에서 **DNS 설정**을 선택합니다. 
    
    (You may have to scroll down.)
    
    ![목록에서 DNS 설정 선택](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    행을 추가 해야 하는 경우 **a/CNAME 레코드 추가 (+)** 를 선택 합니다.
    
    (You may have to scroll down.)
    
    |**호스트 이름**|**종류**|**결과**|
    |:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/>**참고: ** 모든 간격이 올바르게 유지되도록 이 항목을 복사하여 붙여넣는 것이 좋습니다.           |
   
    ![DNS 영역 추가/수정 페이지에서 값 입력](../../media/33976398-da8a-439b-8e3d-534503b20ee0.png)
  
4. **저장**을 선택합니다.
    
    (You may have to scroll down.)
    
    ![저장을 선택](../../media/1d8da122-4861-4ca3-bc9b-d01f18557d4c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Office 365에 필요한 2개의 SRV 레코드 추가
<a name="BKMK_add_SRV"> </a>

1. 시작하려면 [이 링크](https://admin.register365.com/dns/)를 사용하여 Register365의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.
    
    ![제어판 로그인 페이지](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. **대시보드** 페이지에서 업데이트 중인 도메인 이름을 찾은 다음 드롭다운 목록에서 **DNS 설정**을 선택합니다. 
    
    (You may have to scroll down.)
    
    ![목록에서 DNS 설정 선택](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. **Add/Modify DNS Zone**(DNS 영역 추가/수정) 페이지의 **Service records**(서비스 레코드) 구역에서 새 레코드의 상자에 다음 표의 값을 입력하거나 복사하여 붙여넣습니다. 
    
    (아래로 스크롤해야 할 수 있습니다.)
    
    |**이름**|**Priority(우선 순위)**|**Weight(가중치)**|**Port(포트)**|**결과**|
    |:-----|:-----|:-----|:-----|:-----|
    |_sip _tls  <br/> |100  <br/> |개  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls _tcp  <br/> |100  <br/> |개  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
   
    ![서비스 레코드 섹션에 값 입력](../../media/56bb1813-90e2-40c8-98bf-750e2dc3f8b6.png)
  
4. **저장**을 선택합니다.
    
    (You may have to scroll down.)
    
    ![저장을 선택](../../media/3b80757c-01e1-492d-b2ce-f721d71f7235.png)
  
> [!NOTE]
>  일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 
  
