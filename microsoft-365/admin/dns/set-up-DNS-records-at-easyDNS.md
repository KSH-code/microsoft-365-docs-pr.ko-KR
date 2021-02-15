---
title: EasyDNS에서 Microsoft용 DNS 레코드 만들기
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
- MET150
- MOE150
ms.assetid: 446babfe-2e08-4cc2-bbfb-c05b854933ac
description: Microsoft의 easyDNS에서 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대한 DNS 레코드를 설정하는 방법을 배워야 합니다.
ms.openlocfilehash: a971a722f071ef5df9ce0fba387cfacfeb409f5b
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656822"
---
# <a name="create-dns-records-at-easydns-for-microsoft"></a>Microsoft용 easyDNS에서 DNS 레코드 만들기

원하는 정보를 찾지 못하면 도메인 [FAQ를](../setup/domains-faq.yml) 확인 합니다. 
  
등록 기관의 웹 사이트에서 다음 DNS 레코드를 모두 추가하여 메일을 Microsoft로 라우팅하고 Teams 및 비즈니스용 Skype에 대한 도메인을 사용하는 등 모든 DNS 레코드를 추가해야 합니다.
  
참고: SRV 레코드는 현재 모든 easyDNS 서비스 패키지에서 사용할 수 없습니다. 비즈니스용 Skype에 필요한 SRV 레코드를 추가하려면 easyDNS를 통해 더 높은 서비스 수준으로 업그레이드해야 할 수 있습니다.
  
## <a name="verify-that-you-own-the-domain-with-a-txt-record"></a>TXT 레코드가 있는 도메인을 소유하고 있는지 확인

1. 이동하여 [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) 자격 증명으로 로그인합니다. 
    
2. 모든 **도메인 제목 아래에서** **dns를 선택합니다.**
    
3. **TXT 레코드 제목** 아래에서 편집 단추(렌치 아이콘)를 선택합니다. 
    
4. 텍스트 필드에 다음 레코드를 입력합니다.
    
    |**Host(호스트)**|**Text(텍스트)**|
    |:-----|:-----|
    |@  <br/> |MS=msXXXXXXXXX(관리 센터 도메인 페이지에서 제공된 값 사용)  <br/> |
   
5. 다음을 **선택합니다.** 
    
6. 레코드가 올바른지 확인한 다음 **CONFIRM 을 선택합니다.** 
    
7. 방금 만든 레코드가 인터넷에 전파되고 Microsoft에서 검색될 수 있도록 계속하기 몇 분 정도 기다립니다.
    
8. 이제 도메인 등록 기관에 레코드가 추가되었습니다. Microsoft로 돌아가서 레코드를 요청합니다.
    
9. I관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인</a> 페이지로 이동하십시오.
    
10. **도메인** 페이지에서 확인 중인 도메인을 선택합니다. 
    
11. 설치 **페이지에서** 설치 **시작을 선택합니다.**
    
12. **도메인 확인** 페이지에서 **확인** 을 선택합니다. 
    
## <a name="add-an-mx-record-to-route-email-to-microsoft"></a>Microsoft로 전자 메일을 라우팅하는 MX 레코드 추가

1. 이동하여 [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) 자격 증명으로 로그인합니다. 
    
2. 모든 **도메인 제목 아래에서** **dns를 선택합니다.**
    
3. **MX 레코드 제목 아래에서** 편집 단추(렌치 아이콘)를 선택합니다. 
    
4. 텍스트 필드에 다음 레코드를 입력합니다.
    
    |**영역의 메일**|**메일 서버**|**PREF**|
    |:-----|:-----|:-----|
    |@  <br/> |\<domain-key\>.mail.protection.outlook.com(관리 센터 \<domain-key\> 도메인 페이지에서 값 확인)  <br/> |0  <br/> |
   
2. 백업을 위해 다른 MX 레코드를 저장하려는 경우 다른 MX 레코드를 다른 곳에 복사합니다. 계속하기 전에 여기에서 다른 모든 MX 레코드를 제거합니다.
    
5. 다음을 **선택합니다.** 
    
6. 레코드가 올바른지 확인한 다음 **CONFIRM 을 선택합니다.** 
    
## <a name="add-the-required-cname-records"></a>필요한 CNAME 레코드 추가

1. 이동하여 [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) 자격 증명으로 로그인합니다. 
    
2. 모든 **도메인 제목 아래에서** **dns를 선택합니다.**
    
3. **CNAME/별칭** 레코드 제목 아래에서 편집 단추(렌치 아이콘)를 선택합니다. 
    
4. 텍스트 필드에 다음 레코드를 입력합니다.


    |**호스트**|**주소("."로 끝나야 합니다.)**|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com.  <br/> |
    |sip  <br/> |sipdir.online.lync.com.  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com.  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net.  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> |
   
5. 다음을 **선택합니다.** 
    
6. 레코드가 올바른지 확인한 다음 **CONFIRM 을 선택합니다.** 
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가

1. 이동하여 [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) 자격 증명으로 로그인합니다. 
    
2. 모든 **도메인 제목 아래에서** **dns를 선택합니다.**
    
3. **TXT 레코드 제목** 아래에서 편집 단추(렌치 아이콘)를 선택합니다. 
    
4. 텍스트 필드에 다음 레코드를 입력합니다.
    
    |**Host(호스트)**|**Text(텍스트)**|
    |:-----|:-----|
    |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> |
   
5. 다음을 **선택합니다.** 
    
6. 레코드가 올바른지 확인한 다음 **CONFIRM 을 선택합니다.** 
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Microsoft 필요한 2개의 SRV 레코드 추가하기

참고: SRV 레코드는 현재 easyDNS의 Domain Plus 서비스 수준에서 사용할 수 없습니다. SRV 레코드를 추가하려면 easyDNS를 통해 더 높은 서비스 수준으로 업그레이드해야 할 수 있습니다. 
  
1. 이동하여 [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) 자격 증명으로 로그인합니다. 
    
2. 모든 **도메인 제목 아래에서** **dns를 선택합니다.**
    
3. **SRV 레코드** 제목 아래에서 편집 단추(렌치 아이콘)를 선택합니다. 
    
4. 텍스트 필드에 다음 레코드를 입력합니다.
    
    |**서비스**|**PROTO**|**호스트**|**PRI**|**WGT**|**포트**|**TARGET("."로 끝나야 합니다.)**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |TLS  <br/> |@  <br/> |100  <br/> |1   <br/> |443  <br/> |sipdir.online.lync.com.  <br/> |1800  <br/> |
    |_sipfederationtls  <br/> |TCP  <br/> |@  <br/> |100  <br/> |1   <br/> |5061  <br/> |sipfed.online.lync.com.  <br/> |1800  <br/> |
   
5. 다음을 **선택합니다.** 
    
6. 레코드가 올바른지 확인한 다음 **CONFIRM 을 선택합니다.** 
    

