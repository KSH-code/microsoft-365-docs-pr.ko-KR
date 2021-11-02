---
title: 커넥트 IONOS에서 DNS 레코드를 1에서&1에서 Microsoft 365
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
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
ms.assetid: 5762c3ca-1de2-4999-bfe5-4c5e25a8957e
description: Microsoft용 1 IONOS 1에서 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대한 DNS&설정하는 방법을 배워야 합니다.
ms.openlocfilehash: 8dc3a509a05e55e984d1c06e59319661a19019e7
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60648722"
---
# <a name="connect-your-dns-records-at-ionos-by-11-to-microsoft-365"></a>커넥트 IONOS에서 DNS 레코드를 1에서&1에서 Microsoft 365

 원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.yml)** 하세요. 

DNS 호스팅 공급자로 IONOS를&1로 설정하는 경우 이 문서의 단계에 따라 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online에 대한 DNS 레코드를 설정하세요.

## <a name="before-you-begin"></a>시작하기 전에

도메인에 대한 DNS 레코드를 설정하는 두 가지 옵션이 있습니다.

- [**도메인 커넥트**](#use-domain-connect-to-verify-and-set-up-your-domain) 다른 전자 메일 서비스 공급자와 함께 도메인을 설정하지 않은 경우 Domain 커넥트 단계를 사용하여 도메인 공급자와 함께 사용할 새 도메인을 자동으로 확인하고 Microsoft 365. 

    또는

- [**수동 단계 사용**](#create-dns-records-with-manual-setup) 아래 수동 단계를 사용하여 도메인을 확인하고 도메인 등록 기관에 추가할 레코드를 언제 및 어떤 레코드로 추가할지 선택하세요. 예를 들어 편의상 새 MX(메일) 레코드를 설정할 수 있습니다. 

## <a name="use-domain-connect-to-verify-and-set-up-your-domain"></a>Domain 커넥트 사용하여 도메인 확인 및 설정

다음 단계에 따라 IONOS를 1개 도메인과 1개&1개까지 자동으로 Microsoft 365.

1. 다음 Microsoft 365 관리 센터 도메인 **설정** 를 선택하고 설정할  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"></a>도메인을 선택합니다.

    :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-1.png" alt-text="Select your domain in Microsoft 365.":::

1. 세 개의 점(추가 작업)을 > **시작을 선택합니다.**

    :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-2.png" alt-text="설치 시작을 선택합니다.":::

1. On the How do you want to connect your domain? 페이지, **계속을 선택합니다.**   

1. DNS 레코드 추가 페이지에서 DNS 레코드 **추가를 선택합니다.**

1. IONOS by 1&1 로그인 페이지에서 계정에 로그인하고 커넥트 및 **허용을** **선택합니다.**

    :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-3.png" alt-text="선택 커넥트 다음 허용을 선택합니다.":::

    그러면 도메인에 대한 도메인 설정이 Microsoft 365. 

## <a name="create-dns-records-with-manual-setup"></a>수동 설정으로 DNS 레코드 만들기

IONOS에서 1에서 1&1까지 이러한 레코드를 추가하면 도메인이 2016년 1월 1일로 Microsoft 서비스.
  
> [!CAUTION]
> IONOS by 1&1은 도메인에 MX 레코드와 최상위 자동 검색 CNAME 레코드를 둘 다 허용하지 않습니다. 이를 통해 Microsoft용 Exchange Online을 구성할 수 있는 방법이 제한됩니다. 해결이 있지만 IONOS에서 1바이트  1로 하위&이미 경험이 있는 경우 이 기능을&좋습니다.
> 이 서비스 [](../setup/domains-faq.yml) 제한에도 불구하고 IONOS 1에서 1&1로 Microsoft DNS 레코드를 관리하기로 선택한 경우 이 문서의 단계를 따라 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online에 대한 DNS 레코드를 설정하십시오.
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요.
  
### <a name="add-a-txt-record-for-verification"></a>확인을 위해 TXT 레코드 추가

Microsoft에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft에 도메인을 소유하고 있음을 증명할 수 있습니다.
  
> [!NOTE]
> 이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.
  
1. 시작하려면 이 링크를 사용하여 IONOS의 도메인 페이지로&[1로 이동합니다.](https://my.1and1.com/) You'll be prompted to log in.

1. 메뉴 **를** 선택한 다음 도메인 및 **SSL 을 선택합니다.**
  
   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-1.png" alt-text="도메인 및 SSL을 선택합니다.":::
  
1. **업데이트할** 도메인에 대한 작업에서 기어 컨트롤을 선택한 다음 DNS 를 **선택합니다.**

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-2.png" alt-text="드롭다운 목록에서 DNS를 선택합니다.":::

1. 레코드 **추가 를 선택합니다.**

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-3.png" alt-text="레코드 추가를 선택합니다.":::

1. **TXT 섹션을** 선택합니다.

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-4.png" alt-text="TXT 섹션을 선택합니다.":::

1. DNS 레코드 추가 페이지의 새 레코드용 상자에 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.

    |**호스트 이름** <br/> |**Value(값)** <br/> | **TTL**
    |:-----|:-----|:-----|
    |(이 필드를 비워 두십시오.)  <br/> |MS=ms *XXXXXXXX*  <br/> 참고: 이 예제는 다음과 같습니다. 여기에는 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다. [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)          | 1시간 |

1. **저장** 을 선택합니다.
  
    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-5.png" alt-text="저장을 선택합니다.":::
  
    방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.

이제 도메인 등록 기관에 레코드가 추가되었습니다. Microsoft 365로 돌아가서 Microsoft 365에 레코드를 찾을 것을 요청합니다. Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.

다음을 통해 레코드를 Microsoft 365.
  
1. 관리 센터에서 도메인 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**로 이동하세요.**</a>

1. 도메인 페이지에서 확인할 도메인을 선택하고 설정 시작 **을 선택합니다.**

    :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-2.png" alt-text="설치 시작을 선택합니다.":::

1. **계속** 을 선택합니다.
  
1. **도메인 확인** 페이지에서 **확인** 을 선택합니다.

> [!NOTE]
> 일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.
  
### <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드 추가하기
  
> [!NOTE]
> 등록한 경우 1und1.de [에 로그인합니다.](https://go.microsoft.com/fwlink/?linkid=859152) 

1. 시작하려면 이 링크를 사용하여 IONOS의 도메인 페이지로&[1로 이동합니다.](https://my.1and1.com/) You'll be prompted to log in.

1. 메뉴 **를** 선택한 다음 도메인 및 **SSL 을 선택합니다.**
  
   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-1.png" alt-text="도메인 및 SSL을 선택합니다.":::
  
1. **업데이트할** 도메인에 대한 작업에서 기어 컨트롤을 선택한 다음 DNS 를 **선택합니다.**

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-2.png" alt-text="드롭다운 목록에서 DNS를 선택합니다.":::

1. 레코드 **추가 를 선택합니다.**

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-3.png" alt-text="레코드 추가를 선택합니다.":::

1. **MX 섹션을** 선택합니다.

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-MX.png" alt-text="MX 섹션을 선택합니다.":::
  
1. DNS 레코드 추가 페이지의 새 레코드용 상자에 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.

    | **호스트 이름**| **연결 대상** |**Priority(우선 순위)**| **TTL** |
    |:-----|:-----|:-----| :-----|
    |  @  | *\<domain-key\>*  .mail.protection.outlook.com  <br/>  참고: \<domain-key\> Microsoft 계정에서 다운로드합니다. [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)          |10   <br/> 우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](../setup/domains-faq.yml)을 참조하세요. | 1시간 |
  
1. **저장** 을 선택합니다.

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-MX-Save.png" alt-text="저장을 선택합니다.":::

1. MX 레코드가 이미 나열되어 있는 경우 레코드 추가  페이지에서 레코드 휴지통 삭제를 선택하여 각 레코드를 **삭제합니다.**

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-Delete.png" alt-text="레코드 삭제를 선택합니다.":::

### <a name="add-the-cname-record-required-for-microsoft"></a>Microsoft에 필요한 CNAME 레코드 추가

> [!NOTE]
> 등록한 경우 1und1.de [에 로그인합니다.](https://go.microsoft.com/fwlink/?linkid=859152) 
  
1. 시작하려면 이 링크를 사용하여 IONOS의 도메인 페이지로&[1로 이동합니다.](https://my.1and1.com/) You'll be prompted to log in.

1. 메뉴 **를** 선택한 다음 도메인 및 **SSL 을 선택합니다.**
  
   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-1.png" alt-text="도메인 및 SSL을 선택합니다.":::
  
1. **업데이트할** 도메인에 대한 작업에서 기어 컨트롤을 선택한 다음 DNS 를 **선택합니다.**

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-2.png" alt-text="드롭다운 목록에서 DNS를 선택합니다.":::

    두 개의 하위 도메인을 만들고 각 도메인에 대한 **별칭** 값을 설정합니다.<br/>1개&IONOS에서는 최상위 CNAME 레코드가 하나만 지원되지만 Microsoft에는 여러 CNAME 레코드가 필요하기 때문에 이 요구가 필요합니다.<br/>먼저 자동 검색 하위 도메인을 만듭니다.

1. **하위omains 를 선택합니다.**
  
   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-Subdomains.png" alt-text="하위omain을 선택합니다.":::
  
1. **하위omain 추가를 선택합니다.**

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-add-subdomains.png" alt-text="하위omain 추가를 선택합니다.":::
  
1. 새 **하위도메인에** 대한 하위도메인 추가 상자에 다음 표의  하위도메인 추가 값만 입력하거나 복사하여 붙여넣습니다. (이후 단계에서 **별칭** 값을 추가합니다.)

    |**하위omain 추가**| **별칭** |
    |:-----|:-----|
    |autodiscover  <br/> | autodiscover.outlook.com |

1. **방금** 만든 **자동** 검색 하위 도메인에 대한 작업에서 기어 컨트롤을 선택한 다음 드롭다운 목록에서 **DNS를** 선택합니다. <br/>

1. 레코드 **추가를** 선택한 다음 **CNAME 섹션을** 선택합니다.

1. **별칭:** 상자에서 다음 표의 **별칭** 값만 입력하거나 복사하여 붙여넣습니다. <br/>

    |**하위omain 추가**| **별칭** |
    |:-----|:-----|
    |autodiscover  <br/> | autodiscover.outlook.com |
  
1. **저장** 을 선택합니다.

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가

> [!IMPORTANT]
> 도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다. 도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다. 도메인에 이미 SPF 레코드가 있는 경우 Microsoft의 새 SPF 레코드를 만들지 마세요. 대신 두 값 집합을 모두 포함하는  *단일*  SPF 레코드가 있도록 현재 레코드에 필요한 Microsoft 값을 추가합니다. 예제가 필요하세요? [Microsoft에 대한 외부 Domain Name System 레코드](../../enterprise/external-domain-name-system-records.md)를 참조하세요. SPF 레코드의 유효성을 검사하기 위해 다음 SPF 유효성 검사 도구 중[하나를 사용할 수 있습니다.](../setup/domains-faq.yml) 
  
> [!NOTE]
> 등록한 경우 1und1.de [에 로그인합니다.](https://go.microsoft.com/fwlink/?linkid=859152) 
  
1. 시작하려면 이 링크를 사용하여 IONOS의 도메인 페이지로&[1로 이동합니다.](https://my.1and1.com/) You'll be prompted to log in.

1. 메뉴 **를** 선택한 다음 도메인 및 **SSL 을 선택합니다.**
  
   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-1.png" alt-text="도메인 및 SSL을 선택합니다.":::
  
1. **업데이트할** 도메인에 대한 작업에서 기어 컨트롤을 선택한 다음 DNS 를 **선택합니다.**

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-2.png" alt-text="드롭다운 목록에서 DNS를 선택합니다.":::

1. 레코드 **추가 를 선택합니다.**

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-3.png" alt-text="레코드 추가를 선택합니다.":::

1. **SPF(TXT) 섹션을** 선택합니다.

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-SPFTXT.png" alt-text="SPF(TXT) 섹션을 선택합니다.":::

1. 새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다. <br/>

    |**유형**|**호스트 이름**|**Value(값)**| **TTL** |
    |:-----|:-----|:-----|:-----|
    |SPF (TXT)  <br/> |(이 필드는 비워 둡니다.)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **참고:** 모든 간격이 올바르게 유지되도록 이 항목을 복사하여 붙여넣는 것이 좋습니다. | 1시간 |
  
1. **저장** 을 선택합니다.

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-SPFTXT-Save.png" alt-text="저장을 선택합니다.":::

## <a name="advanced-option-skype-for-business"></a>고급 옵션: 비즈니스용 Skype

조직에서 채팅, 전화 회의 및 화상 통화와 비즈니스용 Skype 같은 온라인 통신 서비스에도 이 옵션을 사용하는 Microsoft Teams. Skype 사용자 간 통신을 위한 SRV 레코드 2개와 사용자를 로그인하고 서비스에 연결하기 위한 CNAME 레코드 2개 등 4개 레코드가 필요합니다.

### <a name="add-two-additional-cname-records"></a>두 개의 추가 CNAME 레코드 추가
  
1. 시작하려면 이 링크를 사용하여 IONOS의 도메인 페이지로&[1로 이동합니다.](https://my.1and1.com/) You'll be prompted to log in.

1. 메뉴 **를** 선택한 다음 도메인 및 **SSL 을 선택합니다.**
  
   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-1.png" alt-text="도메인 및 SSL을 선택합니다.":::
  
1. **업데이트할** 도메인에 대한 작업에서 기어 컨트롤을 선택한 다음 DNS 를 **선택합니다.**

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-2.png" alt-text="드롭다운 목록에서 DNS를 선택합니다.":::

    두 개의 하위 도메인을 만들고 각 도메인에 대한 **별칭** 값을 설정합니다.<br/>1개&IONOS에서는 최상위 CNAME 레코드가 하나만 지원되지만 Microsoft에는 여러 CNAME 레코드가 필요하기 때문에 이 요구가 필요합니다.<br/>먼저 lyncdiscover 하위omain을 만들어야 합니다.

1. **하위omains 를 선택합니다.**
  
   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-Subdomains.png" alt-text="하위omain을 선택합니다.":::
  
1. **하위omain 추가를 선택합니다.**

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-add-subdomains.png" alt-text="하위omain 추가를 선택합니다.":::

1. 새 **하위도메인에** 대한 하위도메인 추가 상자에 다음 표의  하위도메인 추가 값만 입력하거나 복사하여 붙여넣습니다. (이후 단계에서 **별칭** 값을 추가합니다.)<br/> 

    |**하위omain 추가**|**별칭**|
    |:-----|:-----|
    |lyncdiscover   |webdir.online.lync.com  |

1. **방금** 만든 **lyncdiscover** 하위 도메인에 대한 작업에서 기어 컨트롤을 선택한 다음 드롭다운 목록에서 **DNS를** 선택합니다. <br/>

1. 레코드 **추가를** 선택한 다음 **CNAME 섹션을** 선택합니다.

1. **별칭:** 상자에서 다음 표의 **별칭** 값만 입력하거나 복사하여 붙여넣습니다. <br/>

    |**하위 도메인 만들기**|**별칭**|
    |:-----|:-----|
    |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |

1. 다른 하위omain(SIP)을 만들 수 있습니다. <br/>**하위omain 추가를 선택합니다.**

1. 새 **하위도메인에** 대한 하위도메인 추가 상자에 다음 표의  하위도메인 추가 값만 입력하거나 복사하여 붙여넣습니다. (이후 단계에서 **별칭** 값을 추가합니다.) <br/>

    |**하위omain 추가**|**별칭**|
    |:-----|:-----|
    |sip  <br/> |sipdir.online.lync.com  <br/> |

1. **방금** 만든 하위 도메인에 대한 작업에서 기어 컨트롤을 선택한 다음 드롭다운 목록에서 **DNS를** 선택합니다. <br/>

1. 레코드 **추가 를 선택합니다.**

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-3.png" alt-text="레코드 추가를 선택합니다.":::

1. **CNAME 섹션을** 선택합니다.

1. **별칭: 상자에** 다음 표의 **별칭** 값만 입력하거나 복사하여 붙여넣습니다. 

    |**하위 도메인 만들기**|**별칭**|
    |:-----|:-----|
    |sip  <br/> |sipdir.online.lync.com  <br/> |

1. 고지 사항 **알고 있음** 에 대한 확인란을 선택한 다음 **저장** 을 선택합니다.

## <a name="add-the-two-srv-records-required-for-microsoft"></a>Microsoft에 필요한 두 SRV 레코드 추가
  
> [!NOTE]
> 등록한 경우 1und1.de [에 로그인합니다.](https://go.microsoft.com/fwlink/?linkid=859152) 
  
1. 시작하려면 이 링크를 사용하여 IONOS의 도메인 페이지로&[1로 이동합니다.](https://my.1and1.com/) You'll be prompted to log in.

1. 메뉴 **를** 선택한 다음 도메인 및 **SSL 을 선택합니다.**
  
   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-1.png" alt-text="도메인 및 SSL을 선택합니다.":::
  
1. **업데이트할** 도메인에 대한 작업에서 기어 컨트롤을 선택한 다음 DNS 를 **선택합니다.**

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-2.png" alt-text="드롭다운 목록에서 DNS를 선택합니다.":::

1. 레코드 **추가 를 선택합니다.**

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-3.png" alt-text="레코드 추가를 선택합니다.":::

1. **SRV 섹션을** 선택합니다.

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-SRV.png" alt-text="SRV 섹션을 선택합니다.":::

1. 새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다. <br/>

    |**유형**|**서비스**|**프로토콜**|**호스트 이름**|**연결 대상**|**Priority(우선 순위)**|**Weight(가중치)**|**Port(포트)**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV  <br/> |_sip  <br/> |tls  <br/> |(이 필드는 비워 둡니다.)  <br/> |sipdir.online.lync.com  <br/> |100  <br/> |1  <br/> |443  <br/> |1시간  <br/> |
    |SRV  <br/> |_sipfederationtls  <br/> |tcp  <br/> |(이 필드는 비워 둡니다.)  <br/> |sipfed.online.lync.com  <br/> |100  <br/> |1  <br/> |5061  <br/> |1시간 <br/> |  
  
1. **저장** 을 선택합니다.

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-SRV-Save.png" alt-text="저장을 선택합니다.":::

1. 다른 SRV 레코드를 추가합니다.

> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요. 

## <a name="advanced-option-intune-and-mobile-device-management-for-microsoft-365"></a>고급 옵션: Intune 및 모바일 장치 관리 Microsoft 365

이 서비스는 도메인에 연결하는 모바일 장치를 보호하고 원격으로 관리하는 데 도움이 됩니다. 모바일 장치 관리에는 사용자가 서비스에 장치를 등록할 수 있도록 2개 CNAME 레코드가 필요합니다.

### <a name="add-the-two-required-cname-records"></a>두 개의 필수 CNAME 레코드 추가

> [!IMPORTANT]
> 다른 CNAME 레코드에 사용한 하위omain 프로시저를 수행하고 다음 표의 값을 제공합니다. 
  
1. 시작하려면 이 링크를 사용하여 IONOS의 도메인 페이지로&[1로 이동합니다.](https://my.1and1.com/) You'll be prompted to log in.

1. 메뉴 **를** 선택한 다음 도메인 및 **SSL 을 선택합니다.**
  
   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-1.png" alt-text="도메인 및 SSL을 선택합니다.":::
  
1. **업데이트할** 도메인에 대한 작업에서 기어 컨트롤을 선택한 다음 DNS 를 **선택합니다.**

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-2.png" alt-text="드롭다운 목록에서 DNS를 선택합니다.":::

    두 개의 하위 도메인을 만들고 각 도메인에 대한 **별칭** 값을 설정합니다.<br/>1개&IONOS에서는 최상위 CNAME 레코드가 하나만 지원되지만 Microsoft에는 여러 CNAME 레코드가 필요하기 때문에 이 요구가 필요합니다.<br/>먼저 lyncdiscover 하위omain을 만들어야 합니다.

1. **하위omains 를 선택합니다.**
  
   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-Subdomains.png" alt-text="하위omain을 선택합니다.":::
  
1. **하위omain 추가를 선택합니다.**

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-add-subdomains.png" alt-text="하위omain 추가를 선택합니다.":::

1. 새 **하위도메인에** 대한 하위도메인 추가 상자에 다음 표의  하위도메인 추가 값만 입력하거나 복사하여 붙여넣습니다. (이후 단계에서 **별칭** 값을 추가합니다.)<br/> 

    |**하위omain 추가**|**별칭**|
    |:-----|:-----|
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |

1. **방금** 만든 **enterpriseregistration** 하위 도메인에 대한 작업에서 기어 컨트롤을 선택한 다음 드롭다운 목록에서 **DNS를** 선택합니다. <br/>

1. 레코드 **추가를** 선택한 다음 **CNAME 섹션을** 선택합니다.

1. **별칭:** 상자에서 다음 표의 **별칭** 값만 입력하거나 복사하여 붙여넣습니다. <br/>

    |**하위omain 추가**|**별칭**|
    |:-----|:-----|
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |

1. 다른 하위omain을 만들 수 있습니다. <br/>**하위omain 추가를 선택합니다.**

1. 새 **하위도메인에** 대한 하위도메인 추가 상자에 다음 표의  하위도메인 추가 값만 입력하거나 복사하여 붙여넣습니다. (이후 단계에서 **별칭** 값을 추가합니다.) <br/>

    |**하위omain 추가**|**별칭**|
    |:-----|:-----|
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |

1. **방금** 만든 **enterpriseenrollment** 하위 도메인에 대한 작업에서 기어 컨트롤을 선택한 다음 드롭다운 목록에서 **DNS를** 선택합니다. <br/>

1. 레코드 **추가 를 선택합니다.**

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-3.png" alt-text="레코드 추가를 선택합니다.":::

1. **CNAME 섹션을** 선택합니다.

1. **별칭: 상자에** 다음 표의 **별칭** 값만 입력하거나 복사하여 붙여넣습니다. 

    |**하위 도메인 만들기**|**별칭**|
    |:-----|:-----|
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |

1. 고지 사항 **알고 있음** 에 대한 확인란을 선택한 다음 **저장** 을 선택합니다.