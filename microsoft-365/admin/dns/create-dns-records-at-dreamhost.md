---
title: Microsoft용 에코스트에서 DNS 레코드 만들기
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
ms.assetid: 9c0812e0-908b-4b41-a64b-77f0dbd3db7a
description: 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대한 DNS 레코드를 Microsoft에 대해 도메인을 확인하고 이 서비스에 대한 DNS 레코드를 설정하는 방법을 배워야 합니다.
ms.openlocfilehash: 2faf7cae1fd9a0f9308e303c0588958e56b223e1
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658126"
---
# <a name="create-dns-records-at-dreamhost-for-microsoft"></a>Microsoft용 에코스트에서 DNS 레코드 만들기

 원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.yml)** 하세요. 
  
Dns 호스팅 공급자로인 경우 이 문서의 단계에 따라 도메인을 확인하고 전자 메일, Lync에 대한 DNS 레코드를 설정하세요.
 
TheseHost에서 이러한 레코드를 추가하고 나면 도메인이 Microsoft 서비스에서 작동할 수 있도록 설정됩니다.
  
  
> [!NOTE]
> 일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 
  
## <a name="add-a-txt-record-for-verification"></a>확인을 위해 TXT 레코드 추가
<a name="BKMK_verify"> </a>

Microsoft에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft에 도메인을 소유하고 있음을 증명할 수 있습니다.
  
> [!NOTE]
> 이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다. 
  
1. To get started, go to your domains page at호st by using [this link.](https://panel.dreamhost.com/) 로그인하라는 메시지가 표시될 것입니다.
    
    ![연산 고스트-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. 대시보드 **페이지에서** 도메인을 선택한 다음 **도메인을 관리합니다.**
    
    ![연산 고스트-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. 도메인 **관리** 페이지의 **도메인** 섹션에서 편집할 도메인의 **DNS를** 선택합니다. 
    
    ![연산 고스트-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (You may have to scroll down.)
    
    (드롭다운 목록에서 **Type(종류)** 값을 선택합니다.) 
    
    |**이름**|**Type(종류)**|**값**|**설명**|
    |:-----|:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **참고:** 이 값은 예시입니다. 여기에는 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.           [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)          |이 필드는 선택 사항입니다.  <br/> |
   
   ![연산 고스트-BP-Verify-1-1](../../media/ed4a7d43-eeeb-4ec8-849c-37f81315dc69.png)
  
5. 지금 **레코드 추가를 선택합니다!**
    
    ![연산 고스트-BP-Verify-1-2](../../media/5b89c89b-3a8e-4624-895a-86f3cc4638f6.png)
  
6. 방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.
    
이제 도메인 등록 기관에 레코드가 추가되었습니다. Microsoft로 돌아가서 레코드를 요청합니다.
  
Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.
  
1. Microsoft 관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동합니다.

    
2. **도메인** 페이지에서 확인 중인 도메인을 선택합니다. 
    
    
  
3. **설정** 페이지에서 **설정 시작** 을 선택합니다.
    
    
  
4. **도메인 확인** 페이지에서 **확인** 을 선택합니다.
    
    
  
> [!NOTE]
>  일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 
  

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드 추가하기
<a name="BKMK_add_MX"> </a>

아래 단계를 따릅니다.
  
1. To get started, go to your domains page at호st by using [this link.](https://panel.dreamhost.com/) 로그인하라는 메시지가 표시될 것입니다.
    
    ![연산 고스트-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. 대시보드 **페이지에서** 메일을 **선택한** 다음 사용자 지정 **MX를 선택합니다.**
    
    ![연산 고스트-BP-Configure-2-1](../../media/58478679-4018-49cc-9d83-371dc5fa4a22.png)
  
3. 메일 배달 **관리 섹션의** **작업** 열에서  편집할 도메인에 대해 편집을 선택합니다. 
    
    ![연산 고스트-BP-Configure-2-2](../../media/6eed0be2-6477-4f49-9f90-39e190499a53.png)
  
4. 사용자 지정 **MX 레코드** 섹션의 새 레코드용 상자에 다음 표의 다음 값을 입력하거나 복사하여 붙여넣습니다. 
    
    (아래로 스크롤해야 할 수 있습니다.)
    
    (다른 기존 MX 레코드가 있는 경우 삭제될 레코드를 표시하십시오.)
    
    |**MX 레코드(필수)**|
    |:-----|
    |0  *\<domain-key\>*  .mail.protection.outlook.com.  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> 0은 MX 우선 순위 값입니다. 이 값을 MX 값 시작 부분에 추가하고 나머지 값과 공백으로 구분합니다.  <br/> **참고:** Microsoft  *\<domain-key\>*  계정에서 다운로드하세요.           [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![연산 고스트-BP-Configure-2-3](../../media/90da1816-e186-4016-ab22-7962f8b86add.png)
  
5. 지금 **사용자 지정 MX 레코드를 사용하려면 이 도메인 변경을 선택합니다!**
    
    ![연산 고스트-BP-Configure-2-4](../../media/3221c767-83d3-4f30-9d08-dc998772d2a3.png)
  
6. 다른 기존 MX 레코드가 있는 경우 항목을 선택한 다음 키보드에서 **Delete** 키를 눌러 각 레코드를 삭제합니다. 
    
    ![연산 고스트-BP-Configure-2-5](../../media/1827733c-3609-4b0f-bba1-531ab090da91.png)
  
7. 레코드를 삭제한 경우 지금 사용자 지정 MX 레코드 **업데이트를 선택합니다.**
    
    ![연산 고스트-BP-Configure-2-6](../../media/177462be-0686-47b7-a389-025dfc8d6526.png)

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Microsoft에 필요한 6개의 CNAME 레코드 추가
<a name="BKMK_add_CNAME"> </a>

아래 단계를 따릅니다.
  
1. To get started, go to your domains page at호st by using [this link.](https://panel.dreamhost.com/) 로그인하라는 메시지가 표시될 것입니다.
    
    ![연산 고스트-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. 대시보드 **페이지에서** 도메인을 선택한 다음 **도메인을 관리합니다.**
    
    ![연산 고스트-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. 도메인 **관리** 페이지의 **도메인** 섹션에서 편집할 도메인의 **DNS를** 선택합니다. 
    
    ![연산 고스트-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. 사용자 지정 **DNS** 레코드 추가 섹션의 새 레코드용 상자에 다음 표의 첫 번째 행 값을 입력하거나 복사하여 붙여넣습니다. 
    
    (아래로 스크롤해야 할 수 있습니다.)
    
    (드롭다운 목록에서 **Type(종류)** 값을 선택합니다.) 
    
    |**이름**|**Type(종류)**|**값**|**설명**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |autodiscover.outlook.com.  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |이 필드는 선택 사항입니다.  <br/> |
    |sip  <br/> |CNAME  <br/> |sipdir.online.lync.com.  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |이 필드는 선택 사항입니다.  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |webdir.online.lync.com.  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |이 필드는 선택 사항입니다.  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |enterpriseregistration.windows.net.  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |이 필드는 선택 사항입니다.  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |이 필드는 선택 사항입니다.  <br/> |
   
    ![연산 고스트-BP-Configure-3-1](../../media/0c4cc587-ea24-47f2-8dc6-a35735b250e6.png)
  
5. 지금 **레코드 추가를 선택합니다!**
    
    ![연산 고스트-BP-Configure-3-2](../../media/b5d4f939-de6d-4d1f-a20a-4eb5fe715281.png)
  
6. 앞의 두 단계와 표에 있는 다른 다섯 행의 값을 사용하여 다른 5개의 CNAME 레코드를 각각 추가합니다.

  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다. 도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다. 도메인에 이미 SPF 레코드가 있는 경우 Microsoft의 새 SPF 레코드를 만들지 마세요. 대신 두 값 집합을 모두 포함하는  *단일*  SPF 레코드가 있도록 현재 레코드에 필요한 Microsoft 값을 추가합니다.
  
아래 단계를 따릅니다.
  
1. To get started, go to your domains page at호st by using [this link.](https://panel.dreamhost.com/) 로그인하라는 메시지가 표시될 것입니다.
    
    ![연산 고스트-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. 대시보드 **페이지에서** 도메인을 선택한 다음 **도메인을 관리합니다.**
    
    ![연산 고스트-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. 도메인 **관리** 페이지의 **도메인** 섹션에서 편집할 도메인의 **DNS를** 선택합니다. 
    
    ![연산 고스트-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. 사용자 지정 **DNS** 레코드 추가 섹션의 새 레코드용 상자에 다음 표의 첫 번째 행 값을 입력하거나 복사하여 붙여넣습니다. 
    
    (아래로 스크롤해야 할 수 있습니다.)
    
    (드롭다운 목록에서 **Type(종류)** 값을 선택합니다.) 
    
    |**이름**|**Type(종류)**|**값**|**설명**|
    |:-----|:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.           |이 필드는 선택 사항입니다.  <br/> |
   
   ![연산 고스트-BP-Configure-4-1](../../media/cbc4bbca-bdbc-4dc9-b1b7-b55491eb1e53.png)
  
5. 지금 **레코드 추가를 선택합니다!**
    
    ![연산 고스트-BP-Configure-4-2](../../media/2bd7cae8-1fbc-4407-8dfa-06ce37c586c0.png)
  
6. 앞의 두 단계와 표의 두 번째 행 값을 사용하여 다른 SRV 레코드를 추가합니다.
    
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Microsoft 필요한 2개의 SRV 레코드 추가하기
<a name="BKMK_add_SRV"> </a>

아래 단계를 따릅니다.
  
1. To get started, go to your domains page at호st by using [this link.](https://panel.dreamhost.com/) 로그인하라는 메시지가 표시될 것입니다.
    
    ![연산 고스트-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. 대시보드 **페이지에서** 도메인을 선택한 다음 **도메인을 관리합니다.**
    
    ![연산 고스트-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. 도메인 **관리** 페이지의 **도메인** 섹션에서 편집할 도메인의 **DNS를** 선택합니다. 
    
    ![연산 고스트-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. 사용자 지정 **DNS** 레코드 추가 섹션의 새 레코드용 상자에 다음 표의 첫 번째 행 값을 입력하거나 복사하여 붙여넣습니다. 
    
    (아래로 스크롤해야 할 수 있습니다.)
    
    (드롭다운 목록에서 **Type(종류)** 값을 선택합니다.) 
    
    |**이름**|**Type(종류)**|**값**|**설명**|
    |:-----|:-----|:-----|:-----|
    |_sip._tls  <br/> |SRV  <br/> |100 1 443  <br/> sipdir.online.lync.com.  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |이 필드는 선택 사항입니다.  <br/> |
    |_sipfederationtls._tcp  <br/> |SRV  <br/> |100 1 5061  <br/> sipfed.online.lync.com.  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |이 필드는 선택 사항입니다.  <br/> |
   
    ![연산 고스트-BP-Configure-5-1](../../media/934eb79f-3617-4b72-802c-c42c7d165283.png)
  
5. Select **Add Record Now!**.
    
    ![연산 고스트-BP-Configure-5-2](../../media/015bc73c-8f88-49ce-87f9-e5a6ea3e10a8.png)
  
6. 앞의 두 단계와 표의 두 번째 행 값을 사용하여 다른 SRV 레코드를 추가합니다.
    
> [!NOTE]
>  일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 

  
