---
title: Windows 기반 DNS를 사용하여 Microsoft용 DNS 레코드 만들기
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9eec911d-5773-422c-9593-40e1147ffbde
description: Microsoft용 도메인 기반 DNS에서 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 Windows DNS 레코드를 설정하는 방법을 배워야 합니다.
ms.openlocfilehash: 43cc3679f33a929545ed3d9deec388126aec853c
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60165295"
---
# <a name="create-dns-records-for-microsoft-using-windows-based-dns"></a>Windows 기반 DNS를 사용하여 Microsoft용 DNS 레코드 만들기

 원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.yml)** 하세요. 
   
Windows 기반 DNS를 사용하여 자체 DNS 레코드를 호스트하는 경우 이 문서의 단계에 따라 전자 메일, 비즈니스용 Skype Online 등에 대한 레코드를 설정하세요.
  
시작하려면 업데이트할 수 있도록 Windows [DNS에서 DNS](#find-your-dns-records-in-windows-based-dns) 레코드를 찾아야 합니다. 또한 Microsoft와의 동기화를 계획하는 경우 라우팅할 수 없는 전자 메일 주소가 [On-prem Active Directory](#non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory)에서 UPN으로 사용되는 것을 참조하세요.
  
DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제를 해결하는 데 문제가 발생하면 도메인 이름 또는 DNS 레코드를 변경한 후 문제 [해결을 참조합니다.](../get-help-with-domains/find-and-fix-issues.md) 
  
## <a name="find-your-dns-records-in-windows-based-dns"></a>Windows 기반 DNS에서 DNS 레코드 찾기
<a name="BKMK_find_your_dns_1"></a> 도메인에 대한 DNS 레코드가 있는 페이지로 이동합니다. Windows Server 2008에서 작업하는 경우 실행 시작으로   >  **이동하십시오.** Windows Server 2012에서 작업하는 경우 Windows 키와 **r** 을 누릅니다. **dnsmgmnt.msc** 를 입력한 다음 **확인** 을 선택합니다. DNS 관리자에서 정방 **\<DNS server name\> \> 응답 영역 을 확장합니다.** 도메인을 선택합니다. 이제 DNS 레코드를 만들 준비가 되었습니다.
   
## <a name="add-mx-record"></a>MX 레코드 추가
<a name="BKMK_add_MX"> </a>

도메인의 전자 메일이 Microsoft로 전송될 수 있도록 MX 레코드를 추가합니다.
- 추가할 MX 레코드에는 .mail.protection.outlook.com 값(여기서  \<MX token\> \<MX token\> 은 MSxxxx와 같은 값)을 포함합니다. 
- Microsoft의 DNS 레코드 추가 페이지의 Exchange Online 섹션에 있는 MX 행에서 주소 지점에 나열된 값을 복사합니다. 이 작업에서 만드는 레코드에 이 값을 사용하게 됩니다. 
- 도메인의 DNS 관리자 페이지에서 작업   >  **메일 교환기(MX) 로 이동합니다.** 도메인에 대한 이 페이지를 찾으십시오. Windows [기반 DNS에서 DNS 레코드 찾기를 참조하세요.](#find-your-dns-records-in-windows-based-dns)  
- 새 **자원 레코드** 대화 상자에서 필드가 정확히 다음 값으로 설정되어 있는지 확인하십시오. 
    - 호스트 이름:  
    - @Address: 방금 Microsoft에서 복사한 지점 주소 값을 붙여 넣습니다.  
    - Pref: 
- **변경 사항 저장** 을 선택합니다.
- 사용되지 않는 MX 레코드를 제거합니다. 전자 메일을 다른 곳에서 라우팅하는 이 도메인의 이전 MX 레코드가 있는 경우 각 이전 레코드 옆의 확인란을 선택한 다음 삭제 확인 **을**  >  **선택합니다.** 
   
## <a name="add-cname-records"></a>CNAME 레코드 추가
<a name="BKMK_add_CNAME"> </a>

Microsoft에 필요한 CNAME 레코드를 추가합니다. Microsoft에 추가 CNAME 레코드가 나열되어 있는 경우 여기에 표시된 동일한 일반 단계에 따라 해당 레코드를 추가합니다.
  
> [!IMPORTANT]
> Microsoft용 MDM(모바일 장치 관리)이 있는 경우 두 개의 CNAME 레코드를 추가로 만들어야 합니다. 다른 4개의 CNAME 레코드를 만드는 데 사용한 절차를 따르되 다음 표의 값을 입력합니다. (MDM이 없는 경우 이 단계를 건너뛸 수 있습니다.) 

- 도메인의 DNS 관리자 페이지에서 작업   >  **CNAME(CNAME)으로 이동합니다.**
- 새 **자원 레코드** 대화 상자에서 필드가 정확히 다음 값으로 설정되어 있는지 확인하십시오.  
    - 호스트 이름: autodiscover
    - 유형: 
    - CNAMEAddress: autodiscover.outlook.com
- **O K를** 선택합니다.

SIP CNAME 레코드를 추가합니다. 
- 도메인의 DNS 관리자 페이지에서 작업  \> **CNAME(CNAME)으로 이동합니다.** 
- 새 **자원 레코드** 대화 상자에서 필드가 정확히 다음 값으로 설정되어 있는지 확인하십시오.  
    - 호스트 이름: sip
    - 형식: CNAME
    - 주소: sipdir.online.lync.com
- **확인** 을 선택합니다.

비즈니스용 Skype Online 자동 검색 CNAME 레코드를 추가합니다.  
- 도메인의 DNS 관리자 페이지에서 작업  \> **CNAME(CNAME)으로 이동합니다.** 새 **자원 레코드** 대화 상자에서 필드가 정확히 다음 값으로 설정되어 있는지 확인하십시오.  
    - 호스트 이름: lyncdiscover
    - 형식: CNAME
    - 주소: webdir.online.lync.com
- **확인** 을 선택합니다.
   
### <a name="add-two-cname-records-for-mobile-device-management-mdm-for-microsoft"></a>Microsoft용 MDM(모바일 장치 관리)에 대한 두 개의 CNAME 레코드 추가

> [!IMPORTANT]
> Microsoft용 MDM(모바일 장치 관리)이 있는 경우 두 개의 CNAME 레코드를 추가로 만들어야 합니다. 다른 4개의 CNAME 레코드를 만드는 데 사용한 절차를 따르되 다음 표의 값을 입력합니다. >(MDM이 없는 경우 이 단계를 건너뛸 수 있습니다.) 
  

MDM Enterpriseregistration CNAME 레코드를 추가합니다.  
- 도메인의 DNS 관리자 페이지에서 작업  \> **CNAME(CNAME)으로 이동합니다.** 
- 새 **자원 레코드** 대화 상자에서 필드가 정확히 다음 값으로 설정되어 있는지 확인하십시오.  
- 호스트 이름: enterpriseregistration
- 형식: CNAME
- 주소: enterpriseregistration.windows.net
- **확인** 을 선택합니다. 

MDM Enterpriseenrollment CNAME 레코드를 추가합니다. 
-  도메인의 DNS 관리자 페이지에서 작업  \> **CNAME(CNAME)으로 이동합니다.** 
-  새 **자원 레코드** 대화 상자에서 필드가 정확히 다음 값으로 설정되어 있는지 확인하십시오.  
    - 호스트 이름: enterpriseenrollment
    - 형식: CNAME
    - 주소: enterpriseenrollment-s.manage.microsoft.com
- **확인** 을 선택합니다.
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다. 도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다. 도메인에 이미 SPF 레코드가 있는 경우 Microsoft의 새 SPF 레코드를 만들지 마세요. 대신 두 값 집합을 모두 포함하는  *단일*  SPF 레코드가 있도록 현재 레코드에 필요한 Microsoft 값을 추가합니다. 
  
스팸 메일을 방지하는 데 도움이 되도록 도메인의 SPF TXT 레코드를 추가합니다.
  
- 이 레코드의 TXT 값에 마케팅 전자 메일의 문자열과 같은 다른 문자열이 이미 있을 수 있습니다. 이 경우 해당 문자열은 그대로 두고 이 문자열을 큰따옴표로 구분하여 추가합니다. 
- 도메인의 DNS 관리자 페이지에서 작업  \> **텍스트(TXT)로 이동합니다.** 
-  새 **자원 레코드** 대화 상자에서 필드가 정확히 다음 값으로 설정되어 있는지 확인하십시오. 
 > [!IMPORTANT]
> 일부 Windows DNS 관리자에서는 txt 레코드를 만들 때 홈 이름이 기본적으로 상위 도메인으로 설정될 수 있도록 도메인이 설정되어 있을 수 있습니다. 이 경우 TXT 레코드를 추가할 때 호스트 이름을 @ 또는 도메인 이름으로 설정하는 대신 비어 있음(값 없음)으로 설정하세요. 

-  호스트 유형: @
-  레코드 종류: TXT
-  주소: v=spf1 include:spf.protection.outlook.com -all 
         
-  **확인** 을 선택합니다.
   
## <a name="add-srv-records"></a>SRV 레코드 추가
<a name="BKMK_add_SRV"> </a>

Microsoft에 필요한 두 SRV 레코드를 추가합니다.

비즈니스용 Skype Online 웹 회의에 대한 SIP SRV 레코드를 추가합니다.  <br/> 
-  도메인의 DNS 관리자 페이지에서 작업 **기타** 새 \> **레코드로 이동합니다.** 
-   리소스 **레코드 종류 창에서** **SRV(서비스 위치)** 를 선택한 다음 레코드 만들기 **를 선택합니다.** 
-   새 **자원 레코드** 대화 상자에서 필드가 정확히 다음 값으로 설정되어 있는지 확인하십시오.  
    -  서비스: _sip
    -  프로토콜: _tls
    -  우선 순위: 100
    -  가중치: 1
    -  포트: 443
    -  대상(호스트 이름): sipdir.online.lync.com
-  **확인** 을 선택합니다. 


비즈니스용 Skype Online 페더레이션에 대한 SIP SRV 레코드를 추가합니다.  
-  도메인의 DNS 관리자 페이지에서 작업 **기타** 새 \> **레코드로 이동합니다.**  
-  리소스 **레코드 종류 창에서** **SRV(서비스 위치)** 를 선택한 다음 레코드 만들기 **를 선택합니다.** 
-   새 **자원 레코드** 대화 상자에서 필드가 정확히 다음 값으로 설정되어 있는지 확인하십시오.  
    -  서비스: _sipfederationtls
    -  프로토콜: _tcp
    -  우선 순위: 100
    -  가중치: 1
    -  포트: 5061
    -  대상(호스트 이름): sipfed.online.lync.com
-  **확인** 을 선택합니다. 
   
## <a name="add-a-record-to-verify-that-you-own-the-domain-if-you-havent-already"></a>도메인이 없는 경우 레코드를 추가해 도메인을 소유하고 있는지 확인
<a name="BKMK_verify"> </a>

DNS 레코드를 추가하여 도메인을 Microsoft 서비스 Microsoft는 사용자가 추가하는 도메인을 소유하고 있는지 확인해야 합니다. 이렇게 하려면 다음 단계에 따라 레코드를 추가합니다.
  
> [!NOTE]
> 이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 
  

1. Microsoft에서 정보를 수집합니다.  <br/> 
2. I관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인</a> 페이지로 이동하십시오. 
3. 도메인 **페이지의** 확인 대상  도메인에 대한 작업 열에서 설정 **시작을 선택합니다.** 
4. **Microsoft에 도메인** 추가 페이지에서 시작 **1단계를 선택합니다.** 
5. 도메인 **소유 확인** 페이지의 **이** 단계를 수행하기 위한 지침 참조 드롭다운 목록에서 일반 지침을 **선택합니다.** 
6. 표에서 대상 또는 대상 주소 값을 복사합니다. 이 값은 다음 단계에서 필요합니다. 모든 간격이 올바르게 유지되도록 이 값을 복사해서 붙여 넣는 것이 좋습니다.

TXT 레코드를 추가합니다. 
-  도메인의 DNS 관리자 페이지에서 작업  \> **텍스트(TXT)로 이동합니다.** 
-   새 **자원 레코드 대화** 상자에서 편집 을 **선택합니다.**  
-  새 **리소스 레코드** 대화  상자의 사용자 지정 호스트 이름 영역에서 필드가 정확히 다음 값으로 설정되어 있는지 확인하십시오. 

> [!IMPORTANT] 
> 일부 Windows DNS 관리자에서는 txt 레코드를 만들 때 홈 이름이 기본적으로 상위 도메인으로 설정될 수 있도록 도메인이 설정되어 있을 수 있습니다. 이 경우 TXT 레코드를 추가할 때 호스트 이름을 @ 또는 도메인 이름으로 설정하는 대신 비어 있음(값 없음)으로 설정하세요. 

- 호스트 이름: @
- 유형: TXT
- 주소: Microsoft에서 방금 복사한 대상 또는 대상 주소 값을 여기에 붙여 넣습니다.  
- 확인 **완료**  >  **를 선택합니다.**

Microsoft에서 도메인을 확인 합니다.  
> [!IMPORTANT]
> 이렇게 하기 전에 15분 정도 기다렸다가 방금 만든 레코드가 인터넷을 통해 업데이트될 수 있습니다.       

- Microsoft로 돌아가 아래 단계에 따라 확인 검사를 요청합니다. 확인을 통해 이전 단계에 추가한 TXT 레코드를 찾습니다. 올바른 TXT 레코드가 발견되면 도메인이 확인됩니다.  
1. 관리 센터에서 설치 도메인  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">페이지로</a> 이동합니다.
2. 도메인 **페이지의** 확인 대상  도메인에 대한 작업 열에서 설정 **시작 을 선택합니다.** 
3. 도메인을 **소유하고** 있는지 확인 페이지에서 **완료를** 선택하고 지금 확인을 선택한 다음 확인 대화 상자에서 마친 을 **선택합니다.** 
   
> [!NOTE]
>  일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 
  
## <a name="non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory"></a>온-프레미스 Active Directory에서 UPN으로 사용되는 라우팅할 수 없는 전자 메일 주소
<a name="BKMK_ADNote"> </a>

온-프레미스 Active Directory를 Microsoft와 동기화하려는 경우 active Directory UPN(사용자 계정 이름) 접미사는 유효한 도메인 접미사로, @contoso.local과 같은 지원되지 않는 도메인 접미사는 아닌지 확인합니다. UPN 접미어를 변경해야 하는 경우 디렉터리 동기화를 위해 라우팅할 수 없는 도메인을 [준비하는 방법을 참조합니다.](../../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md)
  
> [!NOTE]
>  일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 

## <a name="related-content"></a>관련 콘텐츠

[Micrsoft 365에서](../get-help-with-domains/transfer-a-domain-from-microsoft-to-another-host.md) 다른 호스트로 도메인 전송(문서)\
[사용자 Microsoft 365 도메인에서](../misc/pilot-microsoft-365-from-my-custom-domain.md) 파일럿 파일럿 시작(문서)\
[도메인 FAQ](../setup/domains-faq.yml) (문서)