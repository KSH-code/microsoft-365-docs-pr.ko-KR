---
title: Register.com에서 Microsoft에 대 한 DNS 레코드 만들기
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
ms.assetid: 55bd8c38-3316-48ae-a368-4959b2c1684e
description: 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대 한 DNS 레코드를 Microsoft 용 Register.com에 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: 7b2353b4b6832c9316e302ace4db948e2550a28f
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400331"
---
# <a name="create-dns-records-at-registercom-for-microsoft"></a>Register.com에서 Microsoft에 대 한 DNS 레코드 만들기

 **원하는 정보는 찾지 못한 경우 [도메인 질문과 대답을 확인](../setup/domains-faq.md)** 하세요. 
  
DNS 호스팅 공급자로 Register.com을 사용하고 있는 경우, 이 문서에 나와 있는 단계를 따라 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 등에 대한 DNS 레코드를 설정합니다.
  
다음은 추가할 기본 레코드입니다. 아래 단계를 따르거나 [비디오를 시청하세요](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).
  
- [Register.com에서 TXT 레코드를 추가해 도메인을 소유하고 있는지 확인](#add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain)
    
- [사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드 추가하기](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [Microsoft에 필요한 CNAME 레코드 추가하기](#add-the-cname-records-that-are-required-for-microsoft)
    
- [전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가](#add-a-txt-record-for-spf-to-help-prevent-email-spam)

- [Microsoft 필요한 2개의 SRV 레코드 추가하기](#add-the-two-srv-records-that-are-required-for-microsoft)
    
Register.com에서 이러한 레코드를 추가 하 고 나면 도메인이 Microsoft 서비스에서 작동 하도록 설정 됩니다.
  

  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요. 
  
## <a name="add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain"></a>Register.com에서 TXT 레코드를 추가해 도메인을 소유하고 있는지 확인
<a name="BKMK_verify"> </a>

Microsoft에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft에 도메인을 소유하고 있음을 증명할 수 있습니다.
  
> [!NOTE]
> 이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다. 
  
아래 단계를 따르거나 [비디오를 시청하세요(0:44에 시작)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. 시작하려면 [이 링크](https://www.register.com/myaccount/)를 사용하여 Register.com의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.
    
2. **도메인**을 선택합니다.
    
3. **관리**를 선택 합니다.
    
4. 수정 하려는 도메인 이름이 포함 된 행을 찾습니다. 그런 다음 해당 행에서 **관리**를 선택 합니다.
    
5. **고급 기술 설정** 섹션으로 스크롤한 후 **TXT 레코드 편집 (SPF)** 을 선택 합니다.
    
6. In the boxes for the new record, type or copy and paste the values from the following table.
    
    |||
    |:-----|:-----|
    |**Host Name** <br/> |**TXT Record** <br/> |
    |@  <br/> |MS=ms *XXXXXXXX*  <br/> **참고:** 이 값은 예시입니다. 여기에는 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다. [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)          |
   
7. **계속**을 선택 합니다.
    
8. 다음 페이지에서 **계속** 을 다시 선택 하 여 변경 내용을 확인 합니다. 
    
9. 방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.
    
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

아래 단계를 따르거나 [비디오를 시청하세요(3:32에 시작)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. 시작하려면 [이 링크](https://www.register.com/myaccount/)를 사용하여 Register.com의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.
    
2. **도메인**을 선택합니다.
    
3. **관리**를 선택 합니다.
    
4. 수정 하려는 도메인 이름이 포함 된 행을 찾습니다. 그런 다음 해당 행에서 **관리**를 선택 합니다.
    
5. **고급 기술 설정** 섹션으로 스크롤한 다음 **메일 교환기 레코드 편집**을 선택 합니다.
    
    ![메일 교환기 레코드 편집을 선택 합니다.](../../media/366b96a1-9147-4bbb-9f8f-50856466cc61.png)
  
6. 새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.
    
    (드롭다운 목록에서 **Priority (우선 순위** ) 값을 선택 합니다.) 
    
    |****Host Name(호스트 이름)****|****우선 순위****|****Mail Server(메일 서버)****|
    |:-----|:-----|:-----|
    |@  <br/> |높음  <br/> 우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)을 참조하세요. <br/> | *\<domain-key\>*. mail.protection.outlook.com  <br/>  <br/>**참고:** \<*domain-key*\>Microsoft 계정에서를 다운로드 하세요. <br> [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![테이블의 값을 복사 하 여 붙여넣기](../../media/a1a15a14-c3dc-45dc-adcd-90fdb3f7455d.png)
  
7. 이미 나열된 다른 MX 레코드가 있으면 삭제할 레코드를 하나씩 선택합니다.
    
    ![Select each record to delete](../../media/0708d03e-346f-4ae7-8cc4-01589efc00ce.png)
  
8. **계속**을 선택 합니다.
    
    ![계속을 선택](../../media/6ef6ce01-ce21-4e3c-8209-4aa9a3dd4b76.png)
  
9. 다음 페이지에서 **계속** 을 다시 선택 하 여 변경 내용을 확인 하 고 저장 합니다. 
    
    ![계속을 선택](../../media/adba4a60-bf61-44fc-9ad9-360e66f8a2ee.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>Microsoft에 필요한 CNAME 레코드 추가하기
<a name="BKMK_add_CNAME"> </a>

아래 단계를 따르거나 [비디오를 시청하세요(4:23에 시작)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. 시작하려면 [이 링크](https://www.register.com/myaccount/)를 사용하여 Register.com의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.
    
2. **도메인**을 선택합니다.
    
3. **관리**를 선택 합니다.
    
4. 수정 하려는 도메인 이름이 포함 된 행을 찾습니다. 그런 다음 해당 행에서 **관리**를 선택 합니다.
    
5. **고급 기술 설정** 섹션으로 스크롤한 다음 **도메인 별칭 레코드 편집**을 선택 합니다.
    
    ![도메인 별칭 레코드 편집을 선택 합니다.](../../media/9fbc31ed-d67c-4828-8bd4-b51068f1e0ca.png)
  
6. **도메인 별칭 추가**를 선택 합니다.
    
    ![다른 도메인 별칭 추가 선택](../../media/b787505f-5566-4879-8552-13f9e89cbf6b.png)
  
7. 필요한 CNAME 레코드를 추가합니다.
    
    새 레코드의 상자에서 다음 표에 있는 첫 번째 행의 값을 입력하거나 복사하여 붙여넣습니다.
    
    |****첫 번째 필드(레이블이 지정되지 않음)****|****Points to(연결 대상)****|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com  <br/>  <br/> |
    |sip  <br/> |sipdir.online.lync.com  <br/>  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com <br/>  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/>  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/>  <br/> |
   
     ![테이블에서 DNS 값을 복사 하 여 붙여넣기](../../media/0e2b36b2-8a0b-4019-addf-301763f9a626.png)
  
8. 필요한 CNAME 레코드를 모두 추가한 경우 **계속**을 선택 합니다.
    
    ![계속을 선택](../../media/1942612b-338a-48fa-a45d-2d5434516723.png)
  
9. 다음 페이지에서 **계속** 을 다시 선택 하 여 변경 내용을 확인 하 고 저장 합니다. 
    
    ![계속을 선택](../../media/3342b570-0633-49c5-9175-5cc8e4a67b53.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다. 도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다. 도메인에 이미 SPF 레코드가 있는 경우 Microsoft의 새 SPF 레코드를 만들지 마세요. 대신, 필수 Microsoft 값을 현재 레코드에 추가하여 두 값 집합을 모두 포함하는 단일 SPF 레코드가 있도록 합니다.  
  
아래 단계를 따르거나 [비디오를 시청하세요(5:12에 시작)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. 시작하려면 [이 링크](https://www.register.com/myaccount/)를 사용하여 Register.com의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.
    
2. **도메인**을 선택합니다.
    
3. **관리**를 선택 합니다.
    
4. 수정 하려는 도메인 이름이 포함 된 행을 찾습니다. 그런 다음 해당 행에서 **관리**를 선택 합니다.
    
5. **고급 기술 설정** 섹션으로 스크롤한 다음 **SPF (TXT 레코드 편집)** 을 선택 합니다.
    
    ![SPF (TXT 레코드 편집)을 선택 합니다.](../../media/c917577a-8b3a-4210-ab6e-776e84f926d0.png)
  
6. 새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.
    
    |****Host Name(호스트 이름)****|****TXT Record(TXT 레코드)****|
    |:-----|:-----|
    |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **참고: ** 모든 간격이 올바르게 유지되도록 이 항목을 복사하여 붙여넣는 것이 좋습니다.  |
   
     ![테이블의 값을 복사 하 여 붙여넣기](../../media/b1dc5036-c13c-4306-b1e3-5a38a74643b7.png)
  
7. **계속**을 선택 합니다.
    
    ![계속을 선택](../../media/08250c98-1a86-48a8-ad94-f96cf338126b.png)
  
8. 다음 페이지에서 **계속** 을 다시 선택 하 여 변경 내용을 확인 하 고 저장 합니다. 
    
    ![계속을 선택](../../media/56be3b0a-dc71-471c-9be3-6ab927296f67.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Microsoft 필요한 2개의 SRV 레코드 추가하기
<a name="BKMK_add_SRV"> </a>

아래 단계를 따르거나 [비디오를 시청하세요(5:55에 시작)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. 시작하려면 [이 링크](https://www.register.com/myaccount/)를 사용하여 Register.com의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.
    
2. **도메인**을 선택합니다.
    
3. **관리**를 선택 합니다.
    
4. 수정 하려는 도메인 이름이 포함 된 행을 찾습니다. 그런 다음 해당 행에서 **관리**를 선택 합니다.
    
5. **고급 기술 설정** 섹션으로 스크롤한 다음 **SRV 레코드 편집**을 선택 합니다.
    
    ![SRV 레코드 편집을 선택 합니다.](../../media/73c149ae-f0d6-460e-880a-7e04a995acc3.png)
  
6. 처음 2개의 SRV 레코드를 추가합니다.
    
    새 레코드의 상자에서 다음 표에 있는 첫 번째 행의 값을 입력하거나 복사하여 붙여넣습니다. 
    
    (드롭다운 목록에서 **Priority (우선 순위** ) 값을 선택 합니다.) 
    
    |****서비스****|****프로토콜****|****이름****|****우선 순위****|****Weight(가중치)****|****포트****|****대상****|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |_tls  <br/> |@  <br/> |높음  <br/> |1   <br/> |443  <br/> |sipdir.online.lync.com  <br/>  <br/> |
    |_sipfederationtls  <br/> |_tcp  <br/> |@  <br/> |높음  <br/> |1   <br/> |5061  <br/> |sipfed.online.lync.com  <br/>  <br/> |
   
    ![테이블의 값을 복사 하 여 붙여넣기](../../media/71304c81-5845-4a8f-b969-d9efc8721184.png)
  
7. **SRV 레코드 추가**를 선택 합니다.
    
    ![SRV 레코드 추가 선택](../../media/823c6bd2-4af7-4079-bf8c-8d35a5c6730f.png)
  
8. 두 번째 SRV 레코드를 추가합니다.
    
    위 표에 있는 두 번째 행의 값을 두 번째 레코드의 상자에 입력하거나 복사하여 붙여넣습니다.
    
9. 두 SRV 레코드를 모두 추가한 경우 **계속**을 선택 합니다.
    
    ![계속을 선택](../../media/008b255a-42d3-442d-83ea-3ffcb7c8fc5d.png)
  
10. 다음 페이지에서 **계속** 을 다시 선택 하 여 변경 내용을 확인 하 고 저장 합니다. 
    
    ![계속을 선택](../../media/b4166e3d-7e4b-41ef-b616-747e95aefc37.png)
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요. 
  
