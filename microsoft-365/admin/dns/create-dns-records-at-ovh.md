---
title: Microsoft용 OVH에서 DNS 레코드 만들기
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
ms.assetid: 5176feef-36dc-4d84-842f-1f2b5a21ba96
description: Microsoft용 OVH에서 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대한 DNS 레코드를 설정하는 방법을 배워야 합니다.
ms.openlocfilehash: 14c3796ff6686ae0d98ec32ec6ddf6afc004a3c3
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49657782"
---
# <a name="create-dns-records-at-ovh-for-microsoft"></a>Microsoft용 OVH에서 DNS 레코드 만들기

원하는 정보를 찾지 못한 경우 [도메인 FAQ를 확인](../setup/domains-faq.yml)하세요. 
  
DNS 호스팅 공급자로 OVH를 사용하고 있는 경우 이 문서의 단계에 따라 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online에 대한 DNS 레코드를 설정하세요.
  
다음은 추가할 기본 레코드입니다. 
  
- [Microsoft용 OVH에서 DNS 레코드 만들기](#create-dns-records-at-ovh-for-microsoft)
    
- [사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드 추가하기](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [Microsoft에 필요한 CNAME 레코드 추가하기](#add-the-cname-records-that-are-required-for-microsoft)
    
- [전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [Microsoft 필요한 2개의 SRV 레코드 추가하기](#add-the-two-srv-records-that-are-required-for-microsoft)
    
OVH에서 이러한 레코드를 추가하고 나면 도메인이 Microsoft 서비스에서 작동할 수 있도록 설정됩니다.

  
> [!NOTE]
>  일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 
  
## <a name="add-a-txt-record-for-verification"></a>확인을 위해 TXT 레코드 추가
<a name="bkmk_txt"> </a>

Microsoft에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft에 도메인을 소유하고 있음을 증명할 수 있습니다.
  
> [!NOTE]
> 이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다. 
  
1. 시작하려면 이 링크를 사용하여 OVH의 도메인 [페이지로 이동합니다.](https://www.ovh.com/manager/) You'll be prompted to log in.
    
    ![OVH 로그인](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. **도메인에서** 편집할 도메인의 이름을 선택합니다.
    
    ![OVH 도메인 선택](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. **DNS 영역 선택.**
    
    ![OVH 선택 DNS 영역](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. 항목 **추가를 선택합니다.**
    
    ![OVH 항목 추가](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. **TXT 선택**
    
    ![OVH 선택 TXT 항목](../../media/3aaa9dae-0b1d-436b-a980-b67a970f31a9.png)
  
6. 새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다. TTL 값을 할당하기  위해 드롭다운 목록에서 개인 설정 값을 선택한 다음 텍스트 상자에 값을 입력합니다. 
    
    |**Record type(레코드 종류)**|**하위 도메인**|**TTL**|**값**|
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |(공백으로 둠)  <br/> |3600(초)  <br/> |MS=msxxxxxxxxx  <br/> **참고:** 이 값은 예시입니다. 여기에는 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.           [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)          |
   
7. **확인** 을 선택합니다. 
    
    ![OVH 확인을 위해 TXT 확인](../../media/bde45596-9a55-4634-b5e7-16d7cde6e1b8.png)
  
8. 방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.
    
이제 도메인 등록 기관에 레코드가 추가되었습니다. Microsoft로 돌아가서 레코드를 요청합니다.
  
Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.
  
1. I관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인</a> 페이지로 이동하십시오.
    
2. **도메인** 페이지에서 확인 중인 도메인을 선택합니다. 
    
    
  
3. **설정** 페이지에서 **설정 시작** 을 선택합니다.
    
    
  
4. **도메인 확인** 페이지에서 **확인** 을 선택합니다.
    
    
  
> [!NOTE]
>  일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드 추가하기
<a name="bkmk_mx"> </a>

1. 시작하려면 이 링크를 사용하여 OVH의 도메인 [페이지로 이동합니다.](https://www.ovh.com/manager/) You'll be prompted to log in.
    
    ![OVH 로그인](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. **도메인에서** 편집할 도메인의 이름을 선택합니다.
    
    ![OVH 도메인 선택](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. **DNS 영역 선택.**
    
    ![OVH 선택 DNS 영역](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. 항목 **추가를 선택합니다.**
    
    ![OVH 항목 추가](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. **MX를 선택합니다.**
    
    ![OVH MX 레코드 유형](../../media/29b5e54e-440a-41f2-9eb9-3de573922ddf.png)
  
6. 새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다. TTL 값을 할당하기  위해 드롭다운 목록에서 개인 설정 값을 선택한 다음 텍스트 상자에 값을 입력합니다. 
    
    > [!NOTE]
    > 기본적으로 OVH는 대상에 대해 상대 표기 기능을 사용하여 대상 레코드의 끝에 도메인 이름을 추가합니다. 대신 절대 표기 방법을 사용하세요. 아래 표와 같이 대상 레코드에 점을 추가합니다. 
  
    |**Record type(레코드 종류)**|**하위 도메인**|**TTL**|**우선 순위**|**Target(대상)**|
    |:-----|:-----|:-----|:-----|:-----|
    |MX  <br/> |(공백으로 둠)  <br/> |3600(초)  <br/> |10    <br/> 우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)을 참조하세요. <br/> |\<domain-key\>.mail.protection.outlook.com.  <br/> **참고:** Microsoft  *\<domain-key\>*  계정에서 다운로드하세요.  [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)  |
   
    ![메일에 대한 OVH MX 레코드](../../media/6e2f5655-93e2-4620-8f19-c452e7edf8f0.png)
  
7. **다음** 을 선택합니다.
    
    ![OVH MX 레코드 선택 다음](../../media/4db62d07-0dc4-49f6-bd19-2b4a07fd764a.png)
  
8. **확인** 을 선택합니다.
    
    ![OVH MX 레코드 선택 확인](../../media/090bfb11-a753-4af0-8982-582a4069a169.png)
  
9. 다른 MX 레코드가 있는 경우 DNS 영역 페이지의 목록에서 모두 **삭제합니다.** 각 레코드를 선택한 다음  작업 열에서 휴지통 삭제 **아이콘을** 선택합니다. 
    
    ![OVH 삭제 MX 레코드](../../media/892b328b-7057-4828-b8c5-fe26284dc8c2.png)
  
10. **확인** 을 선택합니다.
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>Microsoft에 필요한 CNAME 레코드 추가하기
<a name="bkmk_cname"> </a>

1. 시작하려면 이 링크를 사용하여 OVH의 도메인 [페이지로 이동합니다.](https://www.ovh.com/manager/) You'll be prompted to log in.
    
    ![OVH 로그인](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. **도메인에서** 편집할 도메인의 이름을 선택합니다.
    
    ![OVH 도메인 선택](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. **DNS 영역 선택.**
    
    ![OVH 선택 DNS 영역](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. 항목 **추가를 선택합니다.**
    
    ![OVH 항목 추가](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. **CNAME을 선택합니다.**
    
    ![OVH CNAME 레코드 유형 추가](../../media/33c7ac74-18d7-4ae1-9e27-1c0f9773a3c3.png)
  
6. 첫 번째 CNAME 레코드를 만듭니다.
    
    새 레코드의 상자에서 다음 표에 있는 첫 번째 행의 값을 입력하거나 복사하여 붙여넣습니다. TTL 값을 할당하기  위해 드롭다운 목록에서 개인 설정 값을 선택한 다음 텍스트 상자에 값을 입력합니다. 
    
    |**Record type(레코드 종류)**|**하위 도메인**|**대상**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |autodiscover  <br/> |autodiscover.outlook.com.  <br/> |3600초  <br/> |
    |CNAME  <br/> |sip  <br/> |sipdir.online.lync.com.  <br/> |3600초  <br/> |
    |CNAME  <br/> |lyncdiscover  <br/> |webdir.online.lync.com.  <br/> |3600초  <br/> |
    |CNAME  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net.  <br/> |3600초  <br/> |
    |CNAME  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> |3600초  <br/> |
   
    ![OVH CNAME 레코드](../../media/516938b3-0b12-4736-a631-099e12e189f5.png)
  
7. **다음** 을 선택합니다.
    
    ![OVH CNAME 값 추가 및 다음 선택](../../media/f9481cb1-559d-4da1-9643-9cacb0d80d29.png)
  
8. **확인** 을 선택합니다.
    
9. 이전 단계를 반복하여 나머지 5개의 CNAME 레코드를 만드십시오.
    
    각 레코드에 대해 위 표의 다음 행 값을 해당 레코드의 상자에 입력하거나 복사하여 붙여넣습니다.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가
<a name="bkmk_spf"> </a>

> [!IMPORTANT]
> 도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다. 도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다. 도메인에 이미 SPF 레코드가 있는 경우 Microsoft의 새 SPF 레코드를 만들지 마세요. 대신 두 값 집합을 모두 포함하는  *단일*  SPF 레코드가 있도록 현재 레코드에 필요한 Microsoft 값을 추가합니다. 
  
1. 시작하려면 이 링크를 사용하여 OVH의 도메인 [페이지로 이동합니다.](https://www.ovh.com/manager/) You'll be prompted to log in.
    
    ![OVH 로그인](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. **도메인에서** 편집할 도메인의 이름을 선택합니다.
    
    ![OVH 도메인 선택](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. **DNS 영역 선택.**
    
    ![OVH 선택 DNS 영역](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. 항목 **추가를 선택합니다.**
    
    ![OVH 항목 추가](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. **TXT를 선택합니다.**
    
6. In the boxes for the new record, type or copy and paste the following values.
    
    |**Record type(레코드 종류)**|**하위 도메인**|**TTL**|**TXT 값**|
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |(공백으로 둠)  <br/> |3600(초)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.           |
   
    ![SPF에 대한 OVH TXT 레코드 추가](../../media/f50466e9-1557-4548-8a39-e98978a5ee2e.png)
  
7. **다음** 을 선택합니다.
    
    ![OVH SPF에 대한 TXT 레코드 추가 및 다음 선택](../../media/7937eb7c-114f-479f-a916-bcbe476d6108.png)
  
8. **확인** 을 선택합니다.
    
    ![SPF 및 Confirm에 대한 OVH TXT 레코드 추가](../../media/649eefeb-3227-49e3-98a0-1ce19c42fa54.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Microsoft 필요한 2개의 SRV 레코드 추가하기
<a name="bkmk_srv"> </a>

1. 시작하려면 이 링크를 사용하여 OVH의 도메인 [페이지로 이동합니다.](https://www.ovh.com/manager/) You'll be prompted to log in.
    
    ![OVH 로그인](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. **도메인에서** 편집할 도메인의 이름을 선택합니다.
    
    ![OVH 도메인 선택](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. **DNS 영역 선택.**
    
    ![OVH 선택 DNS 영역](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. 항목 **추가를 선택합니다.**
    
    ![OVH 항목 추가](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. **SRV를 선택합니다.**
    
    ![OVH 선택 SRV 레코드 유형](../../media/66bad536-a531-4a4e-b08d-c0d99f6ea1b2.png)
  
6. 첫 번째 SRV 레코드를 생성합니다.
    
    새 레코드의 상자에서 다음 표에 있는 첫 번째 행의 값을 입력하거나 복사하여 붙여넣습니다. TTL 값을 할당하기  위해 드롭다운 목록에서 개인 설정 값을 선택한 다음 텍스트 상자에 값을 입력합니다. 
    
    |**Record type(레코드 종류)**|**하위 도메인**|**Priority(우선 순위)**|**Weight(가중치)**|**Port(포트)**|**TTL**|**Target(대상)**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV (Service)(SRV(서비스))  <br/> |_sip._tls  <br/> |100  <br/> |1   <br/> |443  <br/> |3600(초)  <br/> |sipdir.online.lync.com.  <br/> |
    |SRV (Service)(SRV(서비스))  <br/> |_sipfederationtls._tcp  <br/> |100  <br/> |1   <br/> |5061  <br/> |3600(초)  <br/> |sipfed.online.lync.com.  <br/> |
       
    ![OVH SRV 레코드](../../media/73956b9e-9e4f-40a5-803e-c4ead2f77fa6.png)
  
7. **다음** 을 선택합니다.
    
    ![OVH SRV 레코드 선택 다음](../../media/cb4ad7e2-a8f0-4ab1-9797-d1b51c1d2da9.png)
  
8. **확인** 을 선택합니다.
    
9. 이전 단계를 반복하여 다른 SRV 레코드를 만들 수 있습니다. 위 표에 있는 두 번째 행의 값을 두 번째 레코드의 상자에 입력하거나 복사하여 붙여넣습니다.
    
> [!NOTE]
>  일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 
  
