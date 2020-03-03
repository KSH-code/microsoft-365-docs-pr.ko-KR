---
title: GoDaddy에서 Office 365용 DNS 레코드 만들기
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
ms.assetid: f40a9185-b6d5-4a80-bb31-aa3bb0cab48a
description: 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 및 Office 365에 대 한 GoDaddy의 기타 서비스에 대 한 DNS 레코드를 설정 하는 방법을 알아봅니다.
ms.custom: okr_smb
ms.openlocfilehash: e037e989a51a95b16077d1edfcdff4b341ee3b80
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2020
ms.locfileid: "42349239"
---
# <a name="create-dns-records-at-godaddy-for-office-365"></a>GoDaddy에서 Office 365용 DNS 레코드 만들기

 **원하는 정보는 찾지 못한 경우 [도메인 질문과 대답을 확인](../setup/domains-faq.md)** 하세요.

DNS 호스팅 공급자로 GoDaddy를 사용하고 있는 경우, 이 문서에 나와 있는 단계를 따라 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 등에 대한 DNS 레코드를 설정합니다.

GoDaddy에서 이러한 레코드를 추가하고 나면 도메인이 Office 365 서비스에서 작동하도록 설정됩니다.

Office 365에서 웹 사이트의 웹 호스팅 및 DNS에 대한 자세한 내용은 [Office 365에서 공개 웹 사이트 사용](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)을 참조하세요.

> [!NOTE]
> 일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.

## <a name="add-a-txt-record-for-verification"></a>확인을 위해 TXT 레코드 추가
<a name="BKMK_verify"> </a>

Office 365에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Office 365에 도메인을 소유하고 있음을 증명할 수 있습니다.

> [!NOTE]
> 이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.

아래 단계를 따릅니다.

1. 시작하려면 [이 링크](https://account.godaddy.com/products/?go_redirect=disabled)를 사용하여 GoDaddy의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.

    ![GoDaddy-BP-구성-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. **도메인**아래에서 편집 하려는 도메인의 DNS를 선택 합니다.

    ![GoDaddy-BP-구성-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. **추가**를 선택합니다.

    ![GoDaddy-BP-구성-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. 드롭다운 목록에서 **TXT(텍스트)** 를 선택합니다. 새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.

    |**Record type(레코드 종류)** |**Host(호스트)**|**TXT 값**|**TTL** |
    |:-----|:-----|:-----|:-----|
    |TXT(텍스트)|@|MS=ms *XXXXXXXX*<br>**참고**:이는 예입니다. 여기에는 Office 365의 표에 있는 특정 **보낼 대상 또는 지점** 값을 사용합니다. [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)|1시간  <br>(드롭다운 목록에서 값을 선택 합니다.)|

      ![GoDaddy-1-0](../../media/dns/56526870-d6465780-651a-11e9-9cf0-d6fff71e2f62.png)

5. **저장**을 선택합니다.

6. 방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.

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

아래 단계를 따릅니다.

1. 시작하려면 [이 링크](https://account.godaddy.com/products/?go_redirect=disabled)를 사용하여 GoDaddy의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.

    ![GoDaddy-BP-구성-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. **도메인**아래에서 편집 하려는 도메인의 DNS를 선택 합니다.

    ![GoDaddy-BP-구성-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. **추가**를 선택합니다.

    ![GoDaddy-BP-구성-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. 드롭다운 목록에서 **MX(메일 교환기)** 를 선택합니다.

    ![GoDaddy-BP-구성-2-0](../../media/dns/56528642-85842e00-651d-11e9-8dd8-217f468f9a18.png)

5. 새 레코드의 상자에 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.

    (드롭다운 목록에서 **TTL** 값을 선택 합니다.)

    |**Record type(레코드 종류)**|**호스트**|**Points to(연결 대상)**|**Priority(우선 순위)**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|
    |MX (Mail Exchanger)(MX(메일 교환기))  <br/> |@  <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **참고:** Office 365 계정에서 * \<도메인\> 키* 를 가져옵니다.           [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)          |10   <br/> 우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)을 참조하세요. <br/> |1시간  <br/> |

6. **저장**을 선택합니다.

## <a name="add-the-cname-records-that-are-required-for-office-365"></a>Office 365에 필요한 CNAME 레코드 추가
<a name="BKMK_add_CNAME"> </a>

아래 단계를 따릅니다.

1. 시작하려면 [이 링크](https://account.godaddy.com/products/?go_redirect=disabled)를 사용하여 GoDaddy의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.

    ![GoDaddy-BP-구성-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. **도메인**아래에서 편집 하려는 도메인의 DNS를 선택 합니다.

    ![GoDaddy-BP-구성-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. **추가**를 선택합니다.

    ![GoDaddy-BP-구성-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)


4. 드롭다운 목록에서 **CNAME(별칭)** 을 선택합니다.

    ![GoDaddy-BP-구성-3-0](../../media/dns/56528891-e7449800-651d-11e9-8eac-112285b8e38c.png)

5. 첫 번째 CNAME 레코드를 만듭니다.

    새 레코드의 상자에서 다음 표에 있는 첫 번째 행의 값을 입력하거나 복사하여 붙여넣습니다. 

    (드롭다운 목록에서 **TTL** 값을 선택 합니다.)

    |**Record type(레코드 종류)**|**호스트**|**Points to(연결 대상)**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME (Alias)  <br/> |autodiscover  <br/> |autodiscover.outlook.com  <br/> |1시간  <br/> |
    |CNAME (Alias)(CNAME(별칭))  <br/> |sip  <br/> |sipdir.online.lync.com  <br/> |1시간  <br/> |
    |CNAME (Alias)(CNAME(별칭))  <br/> |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |1시간  <br/> |
    |CNAME (Alias)(CNAME(별칭))  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |1시간  <br/> |
    |CNAME (Alias)(CNAME(별칭))  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment.manage.microsoft.com  <br/> |1시간  <br/> |



6. 이 단계를 반복 하 여 CNAME 레코드 6 개를 모두 만들 때까지 다음 CNAME 레코드를 추가 합니다.

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다. 도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.

아래 단계를 따릅니다.

1. 시작하려면 [이 링크](https://account.godaddy.com/products/?go_redirect=disabled)를 사용하여 GoDaddy의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.

    ![GoDaddy-BP-구성-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. **도메인**아래에서 편집 하려는 도메인의 DNS를 선택 합니다.

    ![GoDaddy-BP-구성-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. **추가**를 선택합니다.

    ![GoDaddy-BP-구성-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. 드롭다운 목록에서 **TXT(텍스트)** 를 선택합니다.

    ![GoDaddy-BP-구성-4-0](../../media/dns/56529449-c0d32c80-651e-11e9-90e9-895aa1c4bbf1.png)

5. 새 레코드의 상자에서 다음 값을 입력하거나 복사하여 붙여넣습니다.

    (드롭다운 목록에서 **TTL** 값을 선택 합니다.)

    |**Record type(레코드 종류)**|**Host(호스트)**|**TXT 값**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |TXT(텍스트)  <br/> |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **참고: ** 모든 간격이 올바르게 유지되도록 이 항목을 복사하여 붙여넣는 것이 좋습니다.           |1시간  <br/> |

    ![GoDaddy-BP-구성-4-1](../../media/7c724f02-c9b3-42ab-b9c0-78959fa6ffad.png)

6. **저장**을 선택합니다.


## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Office 365에 필요한 2개의 SRV 레코드 추가
<a name="BKMK_add_SRV"> </a>

아래 단계를 따릅니다.

1. 시작하려면 [이 링크](https://account.godaddy.com/products/?go_redirect=disabled)를 사용하여 GoDaddy의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.

    ![GoDaddy-BP-구성-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. **도메인**아래에서 편집 하려는 도메인의 DNS를 선택 합니다.

    ![GoDaddy-BP-구성-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. **추가**를 선택합니다.

    ![GoDaddy-BP-구성-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. 드롭다운 목록에서 **SRV(서비스)** 를 선택합니다.

    ![GoDaddy-BP-구성-5-0](../../media/dns/56529669-1dcee280-651f-11e9-8ba2-ecf4fc2f6dca.png)

5. 첫 번째 SRV 레코드를 생성합니다.

    새 레코드의 상자에서 다음 표에 있는 첫 번째 행의 값을 입력하거나 복사하여 붙여넣습니다.

    (드롭다운 목록에서 **레코드 종류** 및 **TTL** 값을 선택 합니다.)

    |**Record type(레코드 종류)**|**Name(이름)**|**Target(대상)**|**Protocol(프로토콜)**|**Service(서비스)**|**Priority(우선 순위)**|**Weight(가중치)**|**Port(포트)**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV (Service)(SRV(서비스))  <br/> |@  <br/> |sipdir.online.lync.com  <br/> |_tls  <br/> |_sip  <br/> |100  <br/> |개  <br/> |443  <br/> |1시간  <br/> |
    |SRV (Service)(SRV(서비스))  <br/> |@  <br/> |sipfed.online.lync.com  <br/> |_tcp  <br/> |_sipfederationtls  <br/> |100  <br/> |개  <br/> |5061  <br/> |1시간  <br/> |

    ![GoDaddy-BP-구성-5-1](../../media/a1b15ab1-eb6a-4672-90d1-7ac3e0beb223.png)


6. **5 단계** 를 반복 하 여 다른 SRV 레코드를 만듭니다.

7. **저장**을 선택합니다.

> [!NOTE]
> 일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.
