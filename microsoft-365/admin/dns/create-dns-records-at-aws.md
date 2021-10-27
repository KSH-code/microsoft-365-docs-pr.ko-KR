---
title: 커넥트 AWS(Amazon Web Services)에서 DNS 레코드를 Microsoft 365
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
ms.assetid: 7a2efd75-0771-4897-ba7b-082fe5bfa9da
description: AWS(Amazon Web Services)에서 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대한 DNS 레코드를 설정하는 방법을 알아보십시오.
ms.openlocfilehash: 1e148b13a89def2eb034ca0bcaa4287c890fe904
ms.sourcegitcommit: da11ffdf7a09490313dfc603355799f80b0c60f9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/26/2021
ms.locfileid: "60586448"
---
# <a name="connect-your-dns-records-at-amazon-web-services-aws-to-microsoft-365"></a>커넥트 AWS(Amazon Web Services)에서 DNS 레코드를 Microsoft 365

 원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.yml)** 하세요. 
  
DNS 호스팅 공급자로 AWS를 사용하고 있는 경우 이 문서의 단계에 따라 도메인을 확인하고 전자 메일, 비즈니스용 온라인 Skype DNS 레코드를 설정하세요.
  
AWS에서 이러한 레코드를 추가하고 나면 도메인이 해당 도메인과 함께 작동하게 Microsoft 서비스.
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요. 
  
## <a name="add-a-txt-record-for-verification"></a>확인을 위해 TXT 레코드 추가

Microsoft에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft에 도메인을 소유하고 있음을 증명할 수 있습니다.
  
> [!NOTE]
> 이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다. 
  
1. 시작하려면 [이 링크](https://console.aws.amazon.com/route53/home)를 사용하여 AWS의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.
    
1. 방문 페이지의 도메인에서 **등록된** **도메인을 선택합니다.**
    
1. 도메인 **이름에서** 설정하려는 도메인을 Microsoft 365.

    **참고:** 도메인에 대해 호스팅된 영역이 만들어지지  않은 경우 호스트된 영역 만들기를 선택하고 다음 단계로 이동하기 전에 단계를 완료합니다. 

   :::image type="content" source="../../media/dns-aws/aws-domains-1.png" alt-text="확인할 도메인의 이름을 선택합니다.":::

1. DNS **관리를 선택합니다.** 

   :::image type="content" source="../../media/dns-aws/aws-domains-2.png" alt-text="드롭다운 목록에서 DNS 관리를 선택합니다.":::

1. 도메인 **이름에서** 확인할 도메인의 호스팅된 영역 버전의 도메인 이름을 선택합니다.

   :::image type="content" source="../../media/dns-aws/aws-domains-3.png" alt-text="확인할 도메인의 이름을 선택합니다.":::

1. 레코드 **만들기 를 선택합니다.**
    
1. 새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다. 
    
    (Choose the **Type** and **Routing Policy** values from the drop-down lists.) 
    
    > [!TIP]
    > The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually. 
  
    ||||||
    |:-----|:-----|:-----|:-----|:-----|
    |**레코드 이름** <br/> |**Record type(레코드 종류)** <br/> |**값** <br/> |**TTL(초)** <br/> |**라우팅 정책** <br/> |
    |(Leave this field empty.)  <br/> |TXT - 전자 메일 보낸 사람 확인에 사용됩니다.  <br/> |MS=ms *XXXXXXXX*  <br/>**참고:** 이 값은 예시입니다. 여기에는 Microsoft 365의 표에 있는 특정 **주소를 지정할 대상 또는 지점** 값을 사용합니다. [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md) |300  <br/> |기본형  <br/> |
   
1. 레코드 **만들기 를 선택합니다.**
    
1. 방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.
    
이제 도메인 등록 기관의 사이트에 레코드를 추가한 후 Microsoft로 돌아가 레코드에 대한 검색을 요청합니다. Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.

다음을 통해 레코드를 Microsoft 365.
  
1. 관리 센터에서 도메인 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**로 이동하세요.**</a>
    
1. 도메인 페이지에서 확인할 도메인을 선택하고 설정 시작 **을 선택합니다.** 

    :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-2.png" alt-text="설치 시작을 선택합니다.":::

1. 계속을 **선택합니다.**
  
1. **도메인 확인** 페이지에서 **확인** 을 선택합니다.
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요. 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft-365"></a>도메인의 전자 메일이 전자 메일로 전송될 수 있도록 MX 레코드를 Microsoft 365

1. 시작하려면 [이 링크](https://console.aws.amazon.com/route53/home)를 사용하여 AWS의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.
    
1. 방문 페이지의 도메인에서 **등록된** **도메인을 선택합니다.**
    
1. 도메인 **이름에서** 설정하려는 도메인을 Microsoft 365.

    **참고:** 도메인에 대해 호스팅된 영역이 만들어지지  않은 경우 호스트된 영역 만들기를 선택하고 다음 단계로 이동하기 전에 단계를 완료합니다. 

   :::image type="content" source="../../media/dns-aws/aws-domains-1.png" alt-text="도메인의 이름을 선택합니다.":::

1. DNS **관리를 선택합니다.** 

   :::image type="content" source="../../media/dns-aws/aws-domains-2.png" alt-text="드롭다운 목록에서 DNS 관리를 선택합니다.":::

1. 도메인 **이름에서** 확인할 도메인의 호스팅된 영역 버전의 도메인 이름을 선택합니다.

   :::image type="content" source="../../media/dns-aws/aws-domains-3.png" alt-text="도메인의 이름을 선택합니다.":::

1. 레코드 **만들기 를 선택합니다.**
    
1. 새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다. 
    
    **(드롭다운 목록에서 유형** 및 라우팅 정책 값을 선택합니다.)  
    
    > [!TIP]
    > The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually. 
    
    |**레코드 이름**|**Record type(레코드 종류)**|**값**|**TTL(초)**|**라우팅 정책**|
    |:-----|:-----|:-----|:-----|:-----|
    |(이 필드는 비워 둡니다.)  <br/> |MX - Mail Exchanger(MX - 메일 교환기)  <br/> |0  *\<domain-key\>*  .mail.protection.outlook.com.  <br/> 0은 MX 우선 순위 값입니다. 이 값을 MX 값 시작 부분에 추가하고 나머지 값과 공백으로 구분합니다.  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> **참고:** 사용자 \<*domain-key*\> 계정에서 Microsoft 365. [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md) | 300  <br/> | 간단한 라우팅 <br/> |
  
1. 레코드 **만들기 를 선택합니다.**
  
1. 다른 MX 레코드가 있는 경우 레코드를 선택한 다음 삭제를 선택하여 해당 레코드를 **제거합니다.**
  
## <a name="add-the-cname-record-required-for-microsoft-365"></a>새 레코드에 필요한 CNAME 레코드를 Microsoft 365

1. 시작하려면 [이 링크](https://console.aws.amazon.com/route53/home)를 사용하여 AWS의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.
    
1. 방문 페이지의 도메인에서 **등록된** **도메인을 선택합니다.**
    
1. 도메인 **이름에서** 설정하려는 도메인을 Microsoft 365.

    **참고:** 도메인에 대해 호스팅된 영역이 만들어지지  않은 경우 호스트된 영역 만들기를 선택하고 다음 단계로 이동하기 전에 단계를 완료합니다. 

   :::image type="content" source="../../media/dns-aws/aws-domains-1.png" alt-text="도메인의 이름을 선택합니다.":::

1. DNS **관리를 선택합니다.** 

   :::image type="content" source="../../media/dns-aws/aws-domains-2.png" alt-text="드롭다운 목록에서 DNS 관리를 선택합니다.":::

1. 도메인 **이름에서** 확인할 도메인의 호스팅된 영역 버전의 도메인 이름을 선택합니다.

   :::image type="content" source="../../media/dns-aws/aws-domains-3.png" alt-text="도메인의 이름을 선택합니다.":::

1. 레코드 **만들기 를 선택합니다.**
    
1. 새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다. 
    
    **(드롭다운 목록에서 유형** 및 라우팅 정책 값을 선택합니다.)  
    
    |**레코드 이름**|**Record type(레코드 종류)**|**Value(값)**| **TTL** |**라우팅 정책**|
    |:-----|:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME - 트래픽을 다른 도메인 이름으로 라우팅  <br/> | autodiscover.outlook.com.  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> | 300  <br/> |기본형  <br/> |
  
6. 레코드 **만들기 를 선택합니다.**
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가

> [!IMPORTANT]
> 도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다. 도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다. 도메인에 이미 SPF 레코드가 있는 경우 Microsoft의 새 SPF 레코드를 만들지 마세요. 대신 두 값 집합을 모두 포함하는  *단일*  SPF 레코드가 있도록 현재 레코드에 필요한 Microsoft 값을 추가합니다. 예제가 필요하세요? [Microsoft에 대한 외부 Domain Name System 레코드](../../enterprise/external-domain-name-system-records.md)를 참조하세요. SPF 레코드의 유효성을 검사하기 위해 다음 SPF 유효성 검사 도구 중[하나를 사용할 수 있습니다.](../setup/domains-faq.yml) 
  
1. 시작하려면 [이 링크](https://console.aws.amazon.com/route53/home)를 사용하여 AWS의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.
    
1. 방문 페이지의 도메인에서 **등록된** **도메인을 선택합니다.**
    
1. 도메인 **이름에서** 설정하려는 도메인을 Microsoft 365.

    **참고:** 도메인에 대해 호스팅된 영역이 만들어지지  않은 경우 호스트된 영역 만들기를 선택하고 다음 단계로 이동하기 전에 단계를 완료합니다. 

   :::image type="content" source="../../media/dns-aws/aws-domains-1.png" alt-text="도메인의 이름을 선택합니다.":::

1. DNS **관리를 선택합니다.** 

   :::image type="content" source="../../media/dns-aws/aws-domains-2.png" alt-text="드롭다운 목록에서 DNS 관리를 선택합니다.":::

1. 도메인 **이름에서** 확인할 도메인의 호스팅된 영역 버전의 도메인 이름을 선택합니다.

   :::image type="content" source="../../media/dns-aws/aws-domains-3.png" alt-text="도메인의 이름을 선택합니다.":::

1. 레코드 **만들기 를 선택합니다.**
    
1. 새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다. 
    
    **(드롭다운 목록에서 유형** 값을 선택합니다.) 
    
    |**Record type(레코드 종류)** | **값**|
    |:-----|:-----|
    |TXT - 전자 메일 보낸 사람 및 응용 프로그램별 값을 확인하는 데 사용됩니다. |v=spf1 include:spf.protection.outlook.com -all  <br/> (화면 지침에 필요한 물음표가 자동으로 제공됩니다. 직접 입력할 필요가 없습니다.)  <br/> **참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.   |
  
6. 레코드 **만들기 를 선택합니다.**

## <a name="advanced-option-skype-for-business"></a>고급 옵션: 비즈니스용 Skype

조직에서 채팅, 전화 회의 및 화상 통화와 비즈니스용 Skype 같은 온라인 통신 서비스에도 이 옵션을 사용하는 Microsoft Teams. Skype 사용자 간 통신을 위한 SRV 레코드 2개와 사용자를 로그인하고 서비스에 연결하기 위한 CNAME 레코드 2개 등 4개 레코드가 필요합니다.

### <a name="add-the-two-required-srv-records"></a>필수 SRV 레코드 2개 추가

1. 시작하려면 [이 링크](https://console.aws.amazon.com/route53/home)를 사용하여 AWS의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.
    
1. 방문 페이지의 도메인에서 **등록된** **도메인을 선택합니다.**
    
1. 도메인 **이름에서** 설정하려는 도메인을 Microsoft 365.

    **참고:** 도메인에 대해 호스팅된 영역이 만들어지지  않은 경우 호스트된 영역 만들기를 선택하고 다음 단계로 이동하기 전에 단계를 완료합니다. 

   :::image type="content" source="../../media/dns-aws/aws-domains-1.png" alt-text="도메인의 이름을 선택합니다.":::

1. DNS **관리를 선택합니다.** 

   :::image type="content" source="../../media/dns-aws/aws-domains-2.png" alt-text="드롭다운 목록에서 DNS 관리를 선택합니다.":::

1. 도메인 **이름에서** 확인할 도메인의 호스팅된 영역 버전의 도메인 이름을 선택합니다.

   :::image type="content" source="../../media/dns-aws/aws-domains-3.png" alt-text="도메인의 이름을 선택합니다.":::

1. 레코드 **만들기 를 선택합니다.**
    
1. 새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다. 
    
    (Choose the **Type** and **Routing Policy** values from the drop-down lists.) 
    
    |**레코드 이름**|**Record type(레코드 종류)**|**값**|**TTL(초)**|**라우팅 정책**|
    |:-----|:-----|:-----|:-----|:-----|
    |_sip._tls|SRV - Service locator(SRV - 서비스 로케이터)|100 1 443 sipdir.online.lync.com. **이 값은 기간(.)으로 끝나야 합니다.**><br> **참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다. | 300 |Simple(단순형)|
    |_sipfederationtls._tcp|SRV - Service locator(SRV - 서비스 로케이터)|100 1 5061 sipfed.online.lync.com. **이 값은 마침표(.)로 끝나야 합니다.**<br> **참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.    | 300 |기본형|
  
7. 다른 SRV 레코드를 추가하려면 **다른** 레코드 추가를 선택하고 표의 다음 행 값을 사용하여 레코드를 만든 다음 레코드 만들기를 다시 **선택합니다.** 
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요. 

### <a name="add-the-two-required-cname-records"></a>두 개의 필수 CNAME 레코드 추가 
    
1. 시작하려면 [이 링크](https://console.aws.amazon.com/route53/home)를 사용하여 AWS의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.
    
1. 방문 페이지의 도메인에서 **등록된** **도메인을 선택합니다.**
    
1. 도메인 **이름에서** 설정하려는 도메인을 Microsoft 365.

    **참고:** 도메인에 대해 호스팅된 영역이 만들어지지  않은 경우 호스트된 영역 만들기를 선택하고 다음 단계로 이동하기 전에 단계를 완료합니다. 

   :::image type="content" source="../../media/dns-aws/aws-domains-1.png" alt-text="도메인의 이름을 선택합니다.":::

1. DNS **관리를 선택합니다.** 

   :::image type="content" source="../../media/dns-aws/aws-domains-2.png" alt-text="드롭다운 목록에서 DNS 관리를 선택합니다.":::

1. 도메인 **이름에서** 확인할 도메인의 호스팅된 영역 버전의 도메인 이름을 선택합니다.

   :::image type="content" source="../../media/dns-aws/aws-domains-3.png" alt-text="도메인의 이름을 선택합니다.":::

1. 레코드 **만들기 를 선택합니다.** 
    
1. 새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다. 
    
    **(드롭다운 목록에서 유형** 및 라우팅 정책 값을 선택합니다.)  

    |**레코드 이름**|**Record type(레코드 종류)**|**Value(값)**| **TTL** |**라우팅 정책**|
    |:-----|:-----|:-----|:-----|:-----|
    |sip  <br/> |CNAME - Canonical name(CNAME - 정식 이름)  <br/> |sipdir.online.lync.com.  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |300  <br/> |Simple(기본)  <br/> |
    |lyncdiscover  <br/> |CNAME - Canonical name(CNAME - 정식 이름)  <br/> |webdir.online.lync.com.  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/>  |300  <br/> ||기본형  <br/> |
  
1. 다른 CNAME 레코드를 추가하려면 **다른** 레코드 추가를 선택하고 표의 다음 행 값을 사용하여 레코드를 만드면 됩니다. 

1. 레코드 **만들기 를 선택합니다.**
    
> [!NOTE]
> 일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 
  
## <a name="advanced-option-intune-and-mobile-device-management-for-microsoft-365"></a>고급 옵션: Intune 및 모바일 장치 관리 Microsoft 365

이 서비스는 도메인에 연결하는 모바일 장치를 보호하고 원격으로 관리하는 데 도움이 됩니다. 모바일 장치 관리에는 사용자가 서비스에 장치를 등록할 수 있도록 두 개의 CNAME 레코드가 필요합니다.

### <a name="add-the-two-required-cname-records"></a>두 개의 필수 CNAME 레코드 추가

1. 시작하려면 [이 링크](https://console.aws.amazon.com/route53/home)를 사용하여 AWS의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.
    
1. 방문 페이지의 도메인에서 **등록된** **도메인을 선택합니다.**
    
1. 도메인 **이름에서** 설정하려는 도메인을 Microsoft 365.

    **참고:** 도메인에 대해 호스팅된 영역이 만들어지지  않은 경우 호스트된 영역 만들기를 선택하고 다음 단계로 이동하기 전에 단계를 완료합니다. 

   :::image type="content" source="../../media/dns-aws/aws-domains-1.png" alt-text="도메인의 이름을 선택합니다.":::

1. DNS **관리를 선택합니다.** 

   :::image type="content" source="../../media/dns-aws/aws-domains-2.png" alt-text="드롭다운 목록에서 DNS 관리를 선택합니다.":::

1. 도메인 **이름에서** 확인할 도메인의 호스팅된 영역 버전의 도메인 이름을 선택합니다.

   :::image type="content" source="../../media/dns-aws/aws-domains-3.png" alt-text="도메인의 이름을 선택합니다.":::

1. 레코드 **만들기 를 선택합니다.**

1. 새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다. 
    
    **(드롭다운 목록에서 유형** 및 라우팅 정책 값을 선택합니다.)  
    
    |**레코드 이름**|**Record type(레코드 종류)**|**Value(값)**| **TTL** |**라우팅 정책**|
    |:-----|:-----|:-----|:-----|:-----|
    |enterpriseregistration  <br/> |CNAME - Canonical name(CNAME - 정식 이름)  <br/> |enterpriseregistration.windows.net.  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |300  <br/> |Simple(기본)  <br/> |
    |enterpriseenrollment  <br/> |CNAME - Canonical name(CNAME - 정식 이름)  <br/> | enterpriseenrollment-s.manage.microsoft.com.  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/>|300  <br/> | |기본형  <br/> |
  
1. 다른 CNAME 레코드를 추가하려면 **다른** 레코드 추가를 선택하고 표의 다음 행 값을 사용하여 레코드를 만드면 됩니다. 

1. 레코드 **만들기 를 선택합니다.**
    
> [!NOTE]
> 일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.