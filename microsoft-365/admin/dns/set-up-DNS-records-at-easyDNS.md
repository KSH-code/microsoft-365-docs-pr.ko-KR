---
title: EasyDNS에서 Microsoft에 대 한 DNS 레코드 만들기
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
- MET150
- MOE150
ms.assetid: 446babfe-2e08-4cc2-bbfb-c05b854933ac
description: 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대 한 DNS 레코드를 Microsoft 용 easyDNS에 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: 24f477d240af936975141c53d382e114a24c0ac5
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400235"
---
# <a name="create-dns-records-at-easydns-for-microsoft"></a>EasyDNS에서 Microsoft에 대 한 DNS 레코드 만들기

원하는 정보를 찾지 못한 경우 [도메인 FAQ를 확인](../setup/domains-faq.md) 합니다. 
  
Microsoft로 메일을 라우팅하기 위해 등록자의 웹 사이트에서 다음 DNS 레코드를 모두 추가 하 고, 팀과 비즈니스용 Skype 등에 대해 도메인을 사용 해야 합니다.
  
참고: SRV 레코드는 현재 모든 easyDNS 서비스 패키지에서 사용할 수 없습니다. 비즈니스용 Skype에 필요한 SRV 레코드를 추가 하려면 easyDNS를 사용 하 여 더 높은 수준의 서비스 수준으로 업그레이드 해야 할 수 있습니다.
  
## <a name="verify-that-you-own-the-domain-with-a-txt-record"></a>TXT 레코드를 사용 하 여 도메인을 소유 하 고 있는지 확인

1. 으로 이동 하 여 [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) 자격 증명을 사용 하 여 로그인 합니다. 
    
2. **모든 도메인** 머리글에서 dns를 선택 **합니다.**
    
3. **TXT 레코드** 제목 아래에서 편집 단추 (렌치 아이콘)를 선택 합니다. 
    
4. 텍스트 필드에 다음 레코드를 입력 합니다.
    
    |**Host(호스트)**|**텍스트**|
    |:-----|:-----|
    |@  <br/> |MS = msXXXXXXXX (관리 센터 도메인에 제공 된 값 사용 페이지)  <br/> |
   
5. **다음**을 선택 합니다. 
    
6. 레코드가 올바른지 확인 하 고 **확인**을 선택 합니다. 
    
7. 방금 만든 레코드가 인터넷을 통해 전파 되 고 Microsoft에서 검색할 수 있도록 몇 분 정도 기다립니다.
    
8. 이제 도메인 등록 기관에 레코드가 추가되었습니다. Microsoft로 돌아가서 레코드를 요청합니다.
    
9. I관리 센터에서 ** 설정 ** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인 </a> 페이지로 이동하십시오.
    
10. **도메인** 페이지에서 확인 중인 도메인을 선택합니다. 
    
11. **설정** 페이지에서 **설정 시작을 선택 합니다.**
    
12. **도메인 확인** 페이지에서 **확인**을 선택합니다. 
    
## <a name="add-an-mx-record-to-route-email-to-microsoft"></a>Microsoft에 전자 메일을 라우팅하기 위한 MX 레코드 추가

1. 으로 이동 하 여 [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) 자격 증명을 사용 하 여 로그인 합니다. 
    
2. **모든 도메인** 머리글에서 dns를 선택 **합니다.**
    
3. **MX 레코드** 제목 아래에서 편집 단추 (렌치 아이콘)를 선택 합니다. 
    
4. 텍스트 필드에 다음 레코드를 입력 합니다.
    
    |**영역에 대 한 메일**|**메일 서버**|**우선**|
    |:-----|:-----|:-----|
    |@  <br/> |\<domain-key\>mail.protection.outlook.com ( \<domain-key\> 관리 센터 도메인 페이지에서 값 가져오기)  <br/> |개  <br/> |
   
2. 백업 목적으로 다른 MX 레코드를 저장 하려면 그 위치에 복사 합니다. 이동 하기 전에 여기에서 다른 모든 MX 레코드를 제거 합니다.
    
5. **다음**을 선택 합니다. 
    
6. 레코드가 올바른지 확인 하 고 **확인**을 선택 합니다. 
    
## <a name="add-the-required-cname-records"></a>필요한 CNAME 레코드 추가

1. 으로 이동 하 여 [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) 자격 증명을 사용 하 여 로그인 합니다. 
    
2. **모든 도메인** 머리글에서 dns를 선택 **합니다.**
    
3. **CNAME/별칭 레코드** 제목에서 편집 단추 (렌치 아이콘)를 선택 합니다. 
    
4. 텍스트 필드에 다음 레코드를 입력 합니다.


    |**호스트**|**주소 ("."로 끝나야 함)**|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
5. **다음**을 선택 합니다. 
    
6. 레코드가 올바른지 확인 하 고 **확인**을 선택 합니다. 
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가

1. 으로 이동 하 여 [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) 자격 증명을 사용 하 여 로그인 합니다. 
    
2. **모든 도메인** 머리글에서 dns를 선택 **합니다.**
    
3. **TXT 레코드** 제목 아래에서 편집 단추 (렌치 아이콘)를 선택 합니다. 
    
4. 텍스트 필드에 다음 레코드를 입력 합니다.
    
    |**Host(호스트)**|**텍스트**|
    |:-----|:-----|
    |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> |
   
5. **다음**을 선택 합니다. 
    
6. 레코드가 올바른지 확인 하 고 **확인**을 선택 합니다. 
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Microsoft 필요한 2개의 SRV 레코드 추가하기

참고: easyDNS ' 도메인 Plus 서비스 수준 '에서는 현재 SRV 레코드를 사용할 수 없습니다. SRV 레코드를 추가 하려면 easyDNS를 사용 하 여 더 높은 서비스 수준으로 업그레이드 해야 할 수 있습니다. 
  
1. 으로 이동 하 여 [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) 자격 증명을 사용 하 여 로그인 합니다. 
    
2. **모든 도메인** 머리글에서 dns를 선택 **합니다.**
    
3. **SRV 레코드** 제목 아래에서 편집 단추 (렌치 아이콘)를 선택 합니다. 
    
4. 텍스트 필드에 다음 레코드를 입력 합니다.
    
    |**서비스**|**프로토콜**|**호스트**|**PRI**|**WGT**|**포트**|**대상 ("."로 끝나야 함)**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |TLS  <br/> |@  <br/> |100  <br/> |1   <br/> |443  <br/> |sipdir.online.lync.com  <br/> |1800  <br/> |
    |_sipfederationtls  <br/> |TCP  <br/> |@  <br/> |100  <br/> |1   <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |1800  <br/> |
   
5. **다음**을 선택 합니다. 
    
6. 레코드가 올바른지 확인 하 고 **확인**을 선택 합니다. 
    

