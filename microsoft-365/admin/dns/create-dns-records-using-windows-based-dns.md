---
title: Windows 기반 DNS를 사용하여 Office 365용 DNS 레코드 만들기
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
ms.assetid: 9eec911d-5773-422c-9593-40e1147ffbde
description: 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대 한 DNS 레코드를 Office 365 용 Windows 기반 DNS에 설정 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: ddea5cb95a7f2abef8b68b37de473f936ee08eb5
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42249311"
---
# <a name="create-dns-records-for-office-365-using-windows-based-dns"></a>Windows 기반 DNS를 사용하여 Office 365용 DNS 레코드 만들기

 원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.md)** 하세요. 
   
Windows 기반 DNS를 사용하여 자체 DNS 레코드를 호스트하는 경우 이 문서의 단계에 따라 전자 메일, 비즈니스용 Skype Online 등에 대한 레코드를 설정하세요.
  
시작 하려면 업데이트할 수 있도록 [Windows 기반 dns에서 dns 레코드를 찾아야](#find-your-dns-records-in-windows-based-dns) 합니다. 또한 온-프레미스 Active Directory를 Office 365과 동기화 하려는 경우 [온-프레미스 Active directory에서 UPN으로 사용 되는 라우팅할 수 없는 전자 메일 주소](#non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory)를 참조 하세요.
  
메일 흐름 문제 또는 기타 문제 DNS 레코드를 추가한 후에는 [도메인 이름 또는 DNS 레코드 변경 후 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조 하세요. 
  
## <a name="find-your-dns-records-in-windows-based-dns"></a>Windows 기반 DNS에서 DNS 레코드 찾기
<a name="BKMK_find_your_dns_1"></a> 도메인에 대 한 DNS 레코드가 있는 페이지로 이동 합니다. Windows Server 2008에서 작업 하는 경우 **시작** > **실행**으로 이동 합니다. Windows Server 2012에서 작업 하는 경우 Windows 키 및 **r**키를 누릅니다. **Dnsmgmnt.msc**를 입력 한 다음 **확인**을 선택 합니다. Dns 관리자에서 ** \<dns 서버 이름\> \> 정방향 조회 영역  **을 확장 합니다. 도메인을 선택합니다. 이제 DNS 레코드를 만들 준비가 되었습니다.
   
## <a name="add-mx-record"></a>MX 레코드 추가
<a name="BKMK_add_MX"> </a>

사용자 도메인의 전자 메일이 Office 365로 전송되도록 MX 레코드를 추가합니다.
- 추가할 MX 레코드에는 mx mail.protection.outlook.com \<\> 와 같이 표시 되는 값 ( **주소에 대 한 점수** 값)이 \<\>포함 되어 있습니다. 
- Office 365의 DNS 레코드 추가 페이지에서 Exchange Online 섹션의 MX 행에서 Points to address에 나열 된 값을 복사 합니다. 이 값은이 작업에서 만드는 레코드에 사용 됩니다. 
- 도메인의 DNS 관리자 페이지에서 **동작** > **MX (메일 교환기)** 로 이동 합니다. 해당 도메인의이 페이지를 찾으려면 [Windows 기반 dns에서 dns 레코드 찾기를](#find-your-dns-records-in-windows-based-dns)참조 하세요.  
- **새 리소스 레코드** 대화 상자에서 필드가 정확히 다음 값으로 설정 되었는지 확인 합니다. 
    - 호스트 이름: 
    - @Address: 방금 Office 365에서 복사한 점수를 주소 값에 붙여 넣습니다.  
    - 우선 
- **변경 내용 저장**을 선택 합니다.
- 사용되지 않는 MX 레코드를 제거합니다. 다른 곳에서 전자 메일을 라우팅하는이 도메인에 대 한 오래 된 MX 레코드가 있는 경우에는 각 이전 레코드 옆의 확인란을 선택 하 고**확인** **삭제** > 를 선택 합니다. 
   
## <a name="add-cname-records"></a>CNAME 레코드 추가
<a name="BKMK_add_CNAME"> </a>

Office 365에 필요한 CNAME 레코드를 추가합니다. Office 365에 추가 CNAME 레코드가 나열되면 여기에 표시된 동일한 일반적인 단계에 따라 해당 레코드를 추가합니다.
  
> [!IMPORTANT]
> Office 365에 대 한 MDM (모바일 장치 관리)이 있는 경우 두 개의 CNAME 레코드를 추가로 만들어야 합니다. Follow the procedure that you used for the other four CNAME records, but supply the values from the following table. (MDM이 없는 경우에는이 단계를 건너뛰어도 됩니다.) 

- 도메인의 DNS 관리자 페이지에서 **작업** > **cname (cname)** 로 이동 합니다.
- **새 리소스 레코드** 대화 상자에서 필드가 정확히 다음 값으로 설정 되었는지 확인 합니다.  
    - 호스트 이름: 자동 검색
    - 형식일 
    - CNAMEAddress: autodiscover.outlook.com
- **O**K를 선택 합니다.

SIP CNAME 레코드를 추가합니다. 
- 도메인의 DNS 관리자 페이지에서 **작업** \> **cname (cname)** 로 이동 합니다. 
- **새 리소스 레코드** 대화 상자에서 필드가 정확히 다음 값으로 설정 되었는지 확인 합니다.  
    - 호스트 이름: sip
    - 유형: CNAME
    - 주소: sipdir.online.lync.com
- **확인**을 선택합니다.

비즈니스용 Skype Online 자동 검색 CNAME 레코드를 추가합니다.  
- 도메인의 DNS 관리자 페이지에서 **작업** \> **cname (cname)** 로 이동 합니다. **새 리소스 레코드** 대화 상자에서 필드가 정확히 다음 값으로 설정 되었는지 확인 합니다.  
    - 호스트 이름: lyncdiscover
    - 유형: CNAME
    - 주소: webdir.online.lync.com
- **확인**을 선택합니다.
   
### <a name="add-two-cname-records-for-mobile-device-management-mdm-for-office-365"></a>Office 365용 MDM(모바일 장치 관리)에 대한 2개의 CNAME 레코드 추가

> [!IMPORTANT]
> Office 365에 대 한 MDM (모바일 장치 관리)이 있는 경우 두 개의 CNAME 레코드를 추가로 만들어야 합니다. Follow the procedure that you used for the other four CNAME records, but supply the values from the following table. > (MDM이 없는 경우이 단계를 건너뛸 수 있습니다.) 
  

MDM Enterpriseregistration CNAME 레코드를 추가합니다.  
- 도메인의 DNS 관리자 페이지에서 **작업** \> **cname (cname)** 로 이동 합니다. 
- **새 리소스 레코드** 대화 상자에서 필드가 정확히 다음 값으로 설정 되었는지 확인 합니다.  
- 호스트 이름: enterpriseregistration
- 유형: CNAME
- 주소: enterpriseregistration.windows.net
- **확인**을 선택합니다. 

MDM Enterpriseenrollment CNAME 레코드를 추가합니다. 
-  도메인의 DNS 관리자 페이지에서 **작업** \> **cname (cname)** 로 이동 합니다. 
-  **새 리소스 레코드** 대화 상자에서 필드가 정확히 다음 값으로 설정 되었는지 확인 합니다.  
    - 호스트 이름: enterpriseenrollment
    - 유형: CNAME
    - 주소: enterpriseenrollment-s.manage.microsoft.com
- **확인**을 선택합니다.
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values. 
  
스팸 메일을 방지하는 데 도움이 되도록 도메인의 SPF TXT 레코드를 추가합니다.
  
- 이 레코드의 TXT 값에 마케팅 전자 메일의 문자열과 같은 다른 문자열이 이미 있을 수 있습니다. 이 경우 해당 문자열은 그대로 두고 이 문자열을 큰따옴표로 구분하여 추가합니다. 
- 도메인의 DNS 관리자 페이지에서 **동작** \> **텍스트 (TXT)** 로 이동 합니다. 
-  **새 리소스 레코드** 대화 상자에서 필드가 정확히 다음 값으로 설정 되었는지 확인 합니다. 
 > [!IMPORTANT]
> 일부 Windows DNS 관리자 버전에서는 txt 레코드를 만들 때 홈 이름이 기본적으로 상위 도메인이 되는 것으로 도메인을 설정 했을 수 있습니다. 이 경우 TXT 레코드를 추가할 때 호스트 이름을 @ 또는 도메인 이름으로 설정하는 대신 비어 있음(값 없음)으로 설정하세요. 

-  호스트 유형: @
-  레코드 유형: TXT
-  주소: v = spf1에는: 
         
-  **확인**을 선택합니다.
   
## <a name="add-srv-records"></a>SRV 레코드 추가
<a name="BKMK_add_SRV"> </a>

Office 365에 필요한 2개의 SRV 레코드를 추가합니다.

비즈니스용 Skype Online 웹 회의에 대한 SIP SRV 레코드를 추가합니다.  <br/> 
-  도메인의 DNS 관리자 페이지에서 **다른 새 레코드** **작업** \> 으로 이동 합니다. 
-   **리소스 레코드 종류** 창에서 **서비스 위치 (SRV)** 를 선택한 다음 **레코드 만들기**를 선택 합니다. 
-   **새 리소스 레코드** 대화 상자에서 필드가 정확히 다음 값으로 설정 되었는지 확인 합니다.  
    -  서비스: _sip
    -  프로토콜: _tls
    -  우선 순위: 100
    -  가중치: 1
    -  포트: 443
    -  대상 (호스트 이름): sipdir.online.lync.com
-  **확인**을 선택합니다. 


비즈니스용 Skype Online 페더레이션에 대한 SIP SRV 레코드를 추가합니다.  
-  도메인의 DNS 관리자 페이지에서 **다른 새 레코드** **작업** \> 으로 이동 합니다.  
-  **리소스 레코드 종류** 창에서 **서비스 위치 (SRV)** 를 선택한 다음 **레코드 만들기**를 선택 합니다. 
-   **새 리소스 레코드** 대화 상자에서 필드가 정확히 다음 값으로 설정 되었는지 확인 합니다.  
    -  서비스: _sipfederationtls
    -  프로토콜: _tcp
    -  우선 순위: 100
    -  가중치: 1
    -  포트: 5061
    -  대상 (호스트 이름): sipfed.online.lync.com
-  **확인**을 선택합니다. 
   
## <a name="add-a-record-to-verify-that-you-own-the-domain-if-you-havent-already"></a>도메인이 없는 경우 레코드를 추가해 도메인을 소유하고 있는지 확인
<a name="BKMK_verify"> </a>

DNS 레코드를 추가하여 Office 365 서비스를 설정하기 전에 Office 365에서 추가하려는 도메인의 소유 여부를 확인해야 합니다. 이렇게 하려면 다음 단계에 따라 레코드를 추가합니다.
  
> [!NOTE]
> 이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 
  

1. Office 365에서 정보를 수집합니다.  <br/> 
2. 관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동 합니다. 
3. **도메인** 페이지의 확인 하려는 도메인에 대 한 **작업** 열에서 **설정 시작**을 선택 합니다. 
4. **Office에 도메인 추가 365** 페이지에서 **1 단계 시작**을 선택 합니다. 
5. 사용자의 **도메인을 소유 하** 고 있는지 확인 페이지의 **이 단계를 수행 하기 위한 지침 보기** 드롭다운 목록에서 **일반 지침**을 선택 합니다. 
6. 표에서 대상 또는 대상 주소 값을 복사합니다. 이 값은 다음 단계에서 필요합니다. 모든 간격이 올바르게 유지되도록 이 값을 복사해서 붙여 넣는 것이 좋습니다.

TXT 레코드를 추가합니다. 
-  도메인의 DNS 관리자 페이지에서 **동작** \> **텍스트 (TXT)** 로 이동 합니다. 
-   **새 리소스 레코드** 대화 상자에서 **편집**을 선택 합니다.  
-  **새 리소스 레코드** 대화 상자의 **사용자 지정 호스트 이름** 영역에서 필드가 정확히 다음 값으로 설정 되었는지 확인 합니다. 

> [!IMPORTANT] 
> 일부 Windows DNS 관리자 버전에서는 txt 레코드를 만들 때 홈 이름이 기본적으로 상위 도메인이 되는 것으로 도메인을 설정 했을 수 있습니다. 이 경우 TXT 레코드를 추가할 때 호스트 이름을 @ 또는 도메인 이름으로 설정하는 대신 비어 있음(값 없음)으로 설정하세요. 

- 호스트 이름: @
- 문자: TXT
- 주소: 방금 Office 365에서 복사한 대상 또는 주소 값을 붙여 넣습니다.  
- **확인** > **완료**를 선택 합니다.

Office 365에서 도메인을 확인합니다.  
> [!IMPORTANT]
> 이 작업을 수행 하기 전에 15 분 정도 기다린 후 방금 만든 레코드가 인터넷을 통해 업데이트 될 수 있도록 합니다.       

- Office 365로 돌아가서 다음 단계에 따라 확인을 요청합니다. 확인을 통해 이전 단계에 추가한 TXT 레코드를 찾습니다. 올바른 TXT 레코드가 발견되면 도메인이 확인됩니다.  
1. 관리 센터에서 <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> **설정** \> 페이지로 이동 합니다.
2. **도메인** 페이지의 확인 하려는 도메인에 대 한 **작업** 열에서 **설정 시작**을 선택 합니다. 
3. 사용자의 **도메인 소유 여부 확인** 페이지에서 **완료, 지금 확인**을 차례로 선택 하 고 확인 대화 상자에서 **마침을**선택 합니다. 
   
> [!NOTE]
>  일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 
  
## <a name="non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory"></a>온-프레미스 Active Directory에서 UPN으로 사용되는 라우팅할 수 없는 전자 메일 주소
<a name="BKMK_ADNote"> </a>

온-프레미스 Active Directory를 Office 365와 동기화하려는 경우 Active Directory UPN(사용자 계정 이름) 접미사가 유효한 도메인 접미사이고 @contoso.local과 같은 지원되지 않는 도메인 접미사가 아닌지 확인하려고 할 것입니다. UPN 접미사를 변경 해야 하는 경우 [디렉터리 동기화를 위해 라우팅할 수 없는 도메인을 준비](https://support.office.com/article/e7968303-c234-46c4-b8b0-b5c93c6d57a7)하는 방법을 참조 하세요.
  
> [!NOTE]
>  일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 
  
