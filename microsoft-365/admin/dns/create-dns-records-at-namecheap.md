---
title: Office 365에 대 한 Namecheap에서 DNS 레코드 만들기
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
ms.assetid: 54ae2002-b38e-43a1-82fa-3e49d78fda56
description: 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 및 Office 365에 대 한 Namecheap의 기타 서비스에 대 한 DNS 레코드를 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: a913aa5f2d88be5bed246e813bebd590f401c07f
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42246547"
---
# <a name="create-dns-records-at-namecheap-for-office-365"></a>Office 365에 대 한 Namecheap에서 DNS 레코드 만들기

 원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.md)** 하세요. 
  
Namecheap DNS 호스팅 공급자 이면이 문서에 나와 있는 단계를 수행 하 여 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 등에 대 한 DNS 레코드를 설정 합니다.
  
Namecheap 이러한 레코드를 추가 하 고 나면 도메인이 Office 365 서비스에서 작동 하도록 설정 됩니다.
  
> [!NOTE]
> 일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 
  
## <a name="add-a-txt-record-for-verification"></a>확인을 위해 TXT 레코드 추가
<a name="BKMK_verify"> </a>

Office 365에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Office 365에 도메인을 소유하고 있음을 증명할 수 있습니다.
  
> [!NOTE]
> 이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다. 
  
아래 단계를 따릅니다.
  
1. 시작 하려면 [이 링크](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)를 사용 하 여 Namecheap의 도메인 페이지로 이동 합니다. 로그인 하 고 계속 진행 하 라는 메시지가 표시 됩니다.
    
    ![Namecheap-BP-1-1](../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. **랜딩** 페이지의 **계정**아래 드롭다운 목록에서 **도메인 목록을** 선택 합니다. 
    
    ![Namecheap-BP-1-2](../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. **도메인 목록** 페이지에서 편집 하려는 도메인의 이름을 찾은 다음 **관리**를 선택 합니다.
    
    ![Namecheap-BP-1-3](../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. **고급 DNS**를 선택 합니다.
    
    ![Namecheap-BP-1-4](../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. **호스트 레코드** 섹션에서 **새 레코드 추가**를 선택 합니다.
    
    ![Namecheap-BP-1-5](../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. **형식** 드롭다운에서 **TXT 레코드**를 선택 합니다.
    
    > [!NOTE]
    > **새 레코드 추가**를 선택 하면 **유형** 드롭다운이 자동으로 표시 됩니다. 
  
    ![Namecheap-BP-Verify-1-1](../media/a5b40973-19b5-4c32-8e1b-1521aa971836.png)
  
7. In the boxes for the new record, type or copy and paste the values from the following table.
    
    (드롭다운 목록에서 **TTL** 값을 선택 합니다.) 
    
    |**유형**|**호스트**|**값**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |@  <br/> |MS=ms *XXXXXXXX*  <br/>**참고:** 예를 들면 다음과 같습니다. 여기에는 Office 365의 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.  [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)          |30 분  <br/> |
       
    ![Namecheap-BP-Verify-1-2](../media/fe75c0fd-f85c-4bef-8068-edaf9779b7f1.png)
  
8. **변경 내용 저장** (확인 표시) 컨트롤을 선택 합니다. 
    
    ![Namecheap-BP-Verify-1-3](../media/b48d2c67-66b5-4aa4-8e59-0c764f236fac.png)
  
9. 방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. 관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동 합니다.
    
2. **도메인** 페이지에서 확인 하려는 도메인을 선택 합니다. 
    
    
  
3. **설정** 페이지에서 **설정 시작**을 선택 합니다.
    
    
  
4. **도메인 확인** 페이지에서 **확인**을 선택 합니다.
    
    
  
> [!NOTE]
> 일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>사용자 도메인의 전자 메일이 Office 365로 전송되도록 MX 레코드 추가
<a name="BKMK_add_MX"> </a>

아래 단계를 따릅니다.
  
1. 시작 하려면 [이 링크](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)를 사용 하 여 Namecheap의 도메인 페이지로 이동 합니다. 로그인 하 고 계속 진행 하 라는 메시지가 표시 됩니다.
    
    ![Namecheap-BP-1-1](../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. **랜딩** 페이지의 **계정**아래 드롭다운 목록에서 **도메인 목록을** 선택 합니다. 
    
    ![Namecheap-BP-1-2](../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. **도메인 목록** 페이지에서 편집 하려는 도메인의 이름을 찾은 다음 **관리**를 선택 합니다.
    
    ![Namecheap-BP-1-3](../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. **고급 DNS**를 선택 합니다.
    
    ![Namecheap-BP-1-4](../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. **메일 설정** 섹션의 **전자 메일 전달** 드롭다운 목록에서 **사용자 지정 MX** 를 선택 합니다. 
    
    (You may have to scroll down.)
    
    ![Namecheap-BP-2-1](../media/40199e2c-42cf-4c3f-9936-3cbe5d4e81a4.png)
  
6. **새 레코드 추가**를 선택 합니다.
    
    ![Namecheap-BP-2-2-1](../media/8d169b81-ba48-4d51-84ea-a08fa1616457.png)
  
7. 새 레코드의 상자에서 다음 표의 값을 입력 하거나 복사 하 여 붙여넣습니다.
    
    **우선 순위** 상자는 **값** 상자 오른쪽에 있는 이름 없는 상자입니다. 드롭다운 목록에서 **TTL** 값을 선택 합니다. 
    
    |**유형**|**호스트**|**값**|**우선 순위**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|
    |MX 레코드  <br/> |@  <br/> |\<**\>mail.protection.outlook.com를 사용 합니다.  <br/> **This value MUST end with a period (.)** <br/> **참고:** Office 365 계정에서 * \<도메인\> 키* 를 가져옵니다.  [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)          |개  <br/> 우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)을 참조하세요. <br/> |30 분  <br/> |
       
    ![Namecheap-BP-2-2-2](../media/f3b76d62-5022-48c1-901b-8615a8571309.png)
  
8. **변경 내용 저장** (확인 표시) 컨트롤을 선택 합니다. 
    
    ![Namecheap-BP-2-3](../media/ef4e3112-36d2-47c8-a478-136a565dd71d.png)
  
9. 다른 MX 레코드가 있으면 다음 2단계 절차를 사용하여 각 레코드를 제거합니다.
    
    먼저 제거할 레코드에 대 한 **삭제 아이콘** (휴지통 가능)을 선택 합니다. 
    
    ![Namecheap-BP-2-4](../media/7a7a751f-29c2-495f-8f55-98ca37ce555a.png)
  
    두 번째로, **예** 를 선택 하 여 삭제를 확인 합니다. 
    
    ![Namecheap-BP-2-5](../media/85ebc0c7-8787-43ee-9e7b-647375b3345c.png)
  
    이 절차의 앞부분에서 추가한 MX 레코드 중 하나를 제외 하 고 모두 제거 합니다.

  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a>Office 365에 필요한 6개의 CNAME 레코드 추가
<a name="BKMK_add_CNAME"> </a>

아래 단계를 따릅니다.
  
1. 시작 하려면 [이 링크](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)를 사용 하 여 Namecheap의 도메인 페이지로 이동 합니다. 로그인 하 고 계속 진행 하 라는 메시지가 표시 됩니다.
    
    ![Namecheap-BP-1-1](../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. **랜딩** 페이지의 **계정**아래 드롭다운 목록에서 **도메인 목록을** 선택 합니다. 
    
    ![Namecheap-BP-1-2](../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. **도메인 목록** 페이지에서 편집 하려는 도메인의 이름을 찾은 다음 **관리**를 선택 합니다.
    
    ![Namecheap-BP-1-3](../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. **고급 DNS**를 선택 합니다.
    
    ![Namecheap-BP-1-4](../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. **호스트 레코드** 섹션에서 **새 레코드 추가**를 선택 합니다.
    
    ![Namecheap-BP-1-5](../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. **유형** 드롭다운에서 **CNAME 레코드**를 선택 합니다.
    
    > [!NOTE]
    > **새 레코드 추가**를 선택 하면 **유형** 드롭다운이 자동으로 표시 됩니다. 
  
    ![Namecheap-BP-3-1](../media/0898f3b2-06ab-4364-a86a-a603a25b39f4.png)
  
7. 새 레코드의 빈 상자에서 **레코드 종류**로 **CNAME**을 선택한 후 다음 표의 첫 번째 행의 값을 입력하거나 복사하여 붙여넣습니다.
    
    |**유형**|**호스트**|**값**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |autodiscover  <br/> |autodiscover.outlook.com  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |3600  <br/> |
    |CNAME  <br/> |sip  <br/> |sipdir.online.lync.com  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |3600  <br/> |
    |CNAME  <br/> |lyncdiscover  <br/> |webdir.online.lync.com  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |3600  <br/> |
    |CNAME  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |3600  <br/> |
    |CNAME  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |3600  <br/> |
       
    ![Namecheap-BP-3-2](../media/f79c5679-34eb-4544-8517-caa2e8a4111a.png)
  
8. **변경 내용 저장** (확인 표시) 컨트롤을 선택 합니다. 
    
    ![Namecheap-BP-3-3](../media/91a5cce4-ca41-41ec-b976-aafe681a4d68.png)
  
9. 위의 네 가지 단계와 표에 있는 나머지 다섯 개 행의 값을 사용 하 여 나머지 5 개의 CNAME 레코드를 각각 추가 합니다.

  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values. 

아래 단계를 따릅니다.
  
1. 시작 하려면 [이 링크](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)를 사용 하 여 Namecheap의 도메인 페이지로 이동 합니다. 로그인 하 고 계속 진행 하 라는 메시지가 표시 됩니다.
    
2. **랜딩** 페이지의 **계정**아래 드롭다운 목록에서 **도메인 목록을** 선택 합니다. 
    
    ![Namecheap-BP-1-2](../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. **도메인 목록** 페이지에서 편집 하려는 도메인의 이름을 찾은 다음 **관리**를 선택 합니다.
    
    ![Namecheap-BP-1-3](../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. **고급 DNS**를 선택 합니다.
    
    ![Namecheap-BP-1-4](../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. **호스트 레코드** 섹션에서 **새 레코드 추가**를 선택 합니다.
    
    ![Namecheap-BP-1-5](../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. **형식** 드롭다운에서 **TXT 레코드**를 선택 합니다.
    
    > [!NOTE]
    > **새 레코드 추가**를 선택 하면 **유형** 드롭다운이 자동으로 표시 됩니다. 
  
    ![Namecheap-BP-4-1](../media/c5d1fddb-28b5-48ec-91c9-3e5d3955ac80.png)
  
7. 새 레코드의 상자에서 다음 표의 값을 입력 하거나 복사 하 여 붙여넣습니다.
    
    (드롭다운 목록에서 **TTL** 값을 선택 합니다.) 
    
    |**유형**|**호스트**|**값**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **참고:** 모든 공백이 올바르게 유지 되도록이 항목을 복사 하 여 붙여 넣는 것이 좋습니다.           |30 분  <br/> |
       
    ![Namecheap-BP-4-2](../media/ea0829f1-990b-424b-b26e-9859468318dd.png)
  
8. **변경 내용 저장** (확인 표시) 컨트롤을 선택 합니다. 
    
    ![Namecheap-BP-4-3](../media/f2846c36-ace3-43d8-be5d-a65e2c267619.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Office 365에 필요한 2개의 SRV 레코드 추가
<a name="BKMK_add_SRV"> </a>

1. 시작 하려면 [이 링크](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)를 사용 하 여 Namecheap의 도메인 페이지로 이동 합니다. You'll be prompted to sign in.
    
    ![Namecheap-BP-1-1](../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. **랜딩** 페이지의 **계정**아래 드롭다운 목록에서 **도메인 목록을** 선택 합니다. 
    
    ![Namecheap-BP-1-2](../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. **도메인 목록** 페이지에서 편집 하려는 도메인의 이름을 찾은 다음 **관리**를 선택 합니다.
    
    ![Namecheap-BP-1-3](../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. **고급 DNS**를 선택 합니다.
    
    ![Namecheap-BP-1-4](../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. **호스트 레코드** 섹션에서 **새 레코드 추가**를 선택 합니다.
    
    ![Namecheap-BP-1-5](../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. **유형** 드롭다운에서 **SRV 레코드**를 선택 합니다.
    
    > [!NOTE]
    > **새 레코드 추가**를 선택 하면 **유형** 드롭다운이 자동으로 표시 됩니다. 
  
    ![Namecheap-BP-5-1](../media/fd55cd7c-2243-4de1-8d39-2c3f7ea3ae51.png)
  
7. 새 레코드의 빈 상자에 다음 표에 있는 첫 번째 행의 값을 입력 하거나 복사 하 여 붙여넣습니다.
    
    |**서비스**|**프로토콜**|**우선 순위**|**가중치**|**포트**|**대상**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |_tls  <br/> |100  <br/> |개  <br/> |443  <br/> |sipdir.online.lync.com  <br/> **This value MUST end with a period (.)** <br/> |30 분  <br/> |
    |_sipfederationtls  <br/> |_tcp  <br/> |100  <br/> |개  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |30 분  <br/> |
       
    ![Namecheap-BP-5-2](../media/ff9566ea-0096-4b7f-873c-027080a23b56.png)
  
8. **변경 내용 저장** (확인 표시) 컨트롤을 선택 합니다. 
    
    ![Namecheap-BP-5-3](../media/48a8dee4-c66d-449d-8759-9e9784c82b13.png)
  
9. 위의 네 가지 단계와 표의 두 번째 행에 있는 값을 사용 하 여 다른 SRV 레코드를 추가 합니다.
    
> [!NOTE]
> 일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 
  

  
