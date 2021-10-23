---
title: 커넥트 DNS 레코드를 web.com Microsoft 365
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
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: Microsoft 2013에서 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대한 DNS web.com 대해 자세히 알아보습니다.
ms.openlocfilehash: 0a8f3db894ee3171f6b086a1eeefbdaf7a7c841a
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2021
ms.locfileid: "60557021"
---
# <a name="connect-your-dns-records-at-webcom-to-microsoft-365"></a>커넥트 DNS 레코드를 web.com Microsoft 365

 원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.yml)** 하세요. 
  
DNS web.com 공급자로 설정한 경우 이 문서의 단계에 따라 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online에 대한 DNS 레코드를 설정하세요.
  
다음에 이러한 레코드를 web.com 도메인이 사용자 도메인과 함께 작동하게 Microsoft 서비스.

> [!NOTE]
>  일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 
  
## <a name="change-your-domains-nameserver-ns-records"></a>도메인의 NS(이름 서버) 레코드 변경

> [!IMPORTANT]
> 이 절차는 도메인을 구입하고 등록한 도메인 등록 기관에서 수행해야 합니다. 
  
등록한 web.com 설치 프로세스를 사용하여 도메인을 **web.com.** 
  
Microsoft에서 도메인에 대한 DNS 레코드를 확인하고 만들하려면 먼저 도메인 등록 기관에서 web.com의 이름 서버를 사용할 수 있도록 이름 서버를 변경해야 합니다.
  
도메인 등록 기관 웹 사이트에서 도메인 이름 서버를 직접 변경하려면 다음 단계를 따릅니다.
  
1. 도메인 등록 기관의 웹 사이트에서 도메인의 이름 서버를 편집할 수 있는 영역을 찾습니다.
    
2. 다음 표의 값을 사용하여 이름 서비스 레코드를 두 개 만들거나 이러한 값과 일치하게 기존 이름 서비스 레코드를 편집합니다.
    
    |||
    |:-----|:-----|
    |첫 번째 이름 서버  <br/> |2016에서 제공하는 이름server 값을 web.com.  <br/> |
    |두 번째 이름 서버  <br/> |2016에서 제공하는 이름server 값을 web.com.  <br/> |
   
    > [!TIP]
    > You should use at least two name server records. 나열된 다른 이름 서버가 있는 경우 해당 서버를 삭제해야 합니다. 
  
3. 변경 내용을 저장합니다.
    
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. 그런 다음 Microsoft 전자 메일 및 기타 서비스가 모두 도메인에서 작동하게 설정됩니다. 
  
## <a name="add-a-txt-record-for-verification"></a>확인을 위해 TXT 레코드 추가

Microsoft에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft에 도메인을 소유하고 있음을 증명할 수 있습니다.
  
> [!NOTE]
> 이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다. 
  
1. 시작하려면 이 링크를 사용하여 web.com [페이지로 이동합니다.](https://checkout.web.com/manage-it/index.jsp) 먼저 로그인합니다.
  
1. 방문 페이지에서 도메인 **이름을 선택합니다.** 
  
1. 작업 **아래에서** 세 개의 점을 선택한  다음 드롭다운 목록에서 관리를 선택합니다.

    :::image type="content" source="../../media/dns-webcom/webcom-domains-1.png" alt-text="드롭다운 목록에서 관리를 선택합니다."::: 
  
1. 아래로 스크롤하여 **고급** 도구 를 선택하고 **고급 DNS 레코드** 옆에 있는 관리 를 **선택합니다.**
    
    고급 DNS 레코드  관리 페이지로 이동하려면 계속을 선택해야 할 수 있습니다.
  
    :::image type="content" source="../../media/dns-webcom/webcom-domains-2.png" alt-text="고급 DNS 레코드 옆에 있는 관리를 선택합니다.":::

1. 고급 DNS 레코드 관리 페이지에서 **+ 레코드 추가 를 선택합니다.**

1. **유형에서** 드롭다운 목록에서 **TXT를** 선택합니다.

1. 다음 표의 값을 선택하거나 복사하여 붙여넣습니다. 
    
    |**참조**|**TXT 값**|**TTL**|
    |:-----|:-----|:----|
    |@  <br/> |MS=ms *XXXXXXXX*  <br/> **참고:** 이 값은 예시입니다. 여기에는 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.  [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)    |1시간  <br/> |
  
5. 추가 **를 선택합니다.**
  
6. 방금 만든 레코드가 인터넷을 통해 업데이트될 수 있도록 몇 분 정도 기다렸다가 새 TXT 레코드를 확인합니다.
    
이제 도메인 등록 기관에 레코드가 추가되었습니다. Microsoft로 돌아가서 레코드를 요청합니다. Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.
  
다음을 통해 레코드를 Microsoft 365.
  
1. 관리 센터에서 도메인 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**로 이동하세요.**</a>
    
2. 도메인 페이지에서 확인할 도메인을 선택하고 설정 시작 **을 선택합니다.**   
  
3. **도메인 확인** 페이지에서 **확인** 을 선택합니다.
    
> [!NOTE]
> 일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드 추가하기

1. 시작하려면 이 링크를 사용하여 web.com [페이지로 이동합니다.](https://checkout.web.com/manage-it/index.jsp) 먼저 로그인합니다.
  
1. 방문 페이지에서 도메인 **이름을 선택합니다.** 
  
1. 작업 **아래에서** 세 개의 점을 선택한  다음 드롭다운 목록에서 관리를 선택합니다.

    :::image type="content" source="../../media/dns-webcom/webcom-domains-1.png" alt-text="드롭다운 목록에서 관리를 선택합니다.":::
  
1. 아래로 스크롤하여 **고급** 도구 를 선택하고 **고급 DNS 레코드** 옆에 있는 관리 를 **선택합니다.**
    
    고급 DNS 레코드  관리 페이지로 이동하려면 계속을 선택해야 할 수 있습니다.
  
    :::image type="content" source="../../media/dns-webcom/webcom-domains-2.png" alt-text="고급 DNS 레코드 옆에 있는 관리를 선택합니다.":::

1. 고급 DNS 레코드 관리 페이지에서 **+ 레코드 추가 를 선택합니다.**

1. **유형에서** 드롭다운 목록에서 **MX를** 선택합니다.

1. 다음 표의 값을 선택하거나 복사하여 붙여넣습니다. 
    
    | **참조 대상** | **메일 서버**|**Priority(우선 순위)**|**TTL**|
    |:-----|:-----|:-----|:-----| 
    | @ |*\<domain-key\>*  .mail.protection.outlook.com  <br/> **참고:** Microsoft  *\<domain-key\>*  관리 센터에서 다운로드하세요.   [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md) | 우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](../setup/domains-faq.yml)을 참조하세요. <br/> 1| 1 Hour  <br/> |
   
1. 추가 **를 선택합니다.**
  
1. MX 레코드 구역에 다른 **MX** 레코드가 나열되어 있는 경우 삭제 아래 레코드 옆의 확인란을 선택하고 저장을 **선택합니다.** 

## <a name="add-the-cname-record-required-for-microsoft"></a>Microsoft에 필요한 CNAME 레코드 추가

1. 시작하려면 이 링크를 사용하여 web.com [페이지로 이동합니다.](https://checkout.web.com/manage-it/index.jsp) 먼저 로그인합니다.
  
1. 방문 페이지에서 도메인 **이름을 선택합니다.** 
  
1. 작업 **아래에서** 세 개의 점을 선택한  다음 드롭다운 목록에서 관리를 선택합니다.
 
    :::image type="content" source="../../media/dns-webcom/webcom-domains-1.png" alt-text="드롭다운 목록에서 관리를 선택합니다.":::
 
1. 아래로 스크롤하여 **고급** 도구 를 선택하고 **고급 DNS 레코드** 옆에 있는 관리 를 **선택합니다.**
    
    고급 DNS 레코드  관리 페이지로 이동하려면 계속을 선택해야 할 수 있습니다.
  
    :::image type="content" source="../../media/dns-webcom/webcom-domains-2.png" alt-text="고급 DNS 레코드 옆에 있는 관리를 선택합니다.":::

1. 고급 DNS 레코드 관리 페이지에서 **+ 레코드 추가 를 선택합니다.**

1. **유형에서** 드롭다운 목록에서 **CNAME을** 선택합니다.

1. 다음 표의 값을 선택하거나 복사하여 붙여넣습니다. 
    
    |**참조 대상** | **호스트 이름** | **별칭 대상**|**TTL**|
    |:-----|:-----|:-----|
    | 기타 호스트  <br/>| autodiscover  <br/>| autodiscover.outlook.com  <br/> | 1시간  <br/>  |
  
1. 추가 **를 선택합니다.**
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가

> [!IMPORTANT]
> 도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다. 도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다. 도메인에 이미 SPF 레코드가 있는 경우 Microsoft의 새 SPF 레코드를 만들지 마세요. 대신 두 값 집합을 모두 포함하는  *단일*  SPF 레코드가 있도록 현재 레코드에 필요한 Microsoft 값을 추가합니다. 
  
1. 시작하려면 이 링크를 사용하여 web.com [페이지로 이동합니다.](https://checkout.web.com/manage-it/index.jsp) 먼저 로그인합니다.
  
1. 방문 페이지에서 도메인 **이름을 선택합니다.** 
  
1. 작업 **아래에서** 세 개의 점을 선택한  다음 드롭다운 목록에서 관리를 선택합니다.

    :::image type="content" source="../../media/dns-webcom/webcom-domains-1.png" alt-text="드롭다운 목록에서 관리를 선택합니다.":::
  
1. 아래로 스크롤하여 **고급** 도구 를 선택하고 **고급 DNS 레코드** 옆에 있는 관리 를 **선택합니다.**
    
    고급 DNS 레코드  관리 페이지로 이동하려면 계속을 선택해야 할 수 있습니다.
  
    :::image type="content" source="../../media/dns-webcom/webcom-domains-2.png" alt-text="고급 DNS 레코드 옆에 있는 관리를 선택합니다.":::

1. 고급 DNS 레코드 관리 페이지에서 **+ 레코드 추가 를 선택합니다.**

1. **유형에서** 드롭다운 목록에서 **TXT를** 선택합니다.

1. 다음 표의 값을 선택하거나 복사하여 붙여넣습니다. 
    
    |**참조 대상**|**TXT 값**|**TTL**|
    |:-----|:-----|:-----|
    |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.  | 1 Hour  <br/> 
 
5. 추가 **를 선택합니다.**
  
## <a name="advanced-option-skype-for-business"></a>고급 옵션: 비즈니스용 Skype

조직에서 채팅, 전화 회의 및 화상 통화와 비즈니스용 Skype 같은 온라인 통신 서비스에도 이 옵션을 사용하는 Microsoft Teams. Skype 사용자 간 통신을 위한 SRV 레코드 2개와 사용자를 로그인하고 서비스에 연결하기 위한 CNAME 레코드 2개 등 4개 레코드가 필요합니다.

### <a name="add-the-two-required-srv-records"></a>필수 SRV 레코드 2개 추가

1. 시작하려면 이 링크를 사용하여 web.com [페이지로 이동합니다.](https://checkout.web.com/manage-it/index.jsp) 먼저 로그인합니다.
  
1. 방문 페이지에서 도메인 **이름을 선택합니다.** 
  
1. 작업 **아래에서** 세 개의 점을 선택한  다음 드롭다운 목록에서 관리를 선택합니다.

    :::image type="content" source="../../media/dns-webcom/webcom-domains-1.png" alt-text="드롭다운 목록에서 관리를 선택합니다.":::
  
1. 아래로 스크롤하여 **고급** 도구 를 선택하고 **고급 DNS 레코드** 옆에 있는 관리 를 **선택합니다.**
    
    고급 DNS 레코드  관리 페이지로 이동하려면 계속을 선택해야 할 수 있습니다.
  
    :::image type="content" source="../../media/dns-webcom/webcom-domains-2.png" alt-text="고급 DNS 레코드 옆에 있는 관리를 선택합니다.":::

1. 고급 DNS 레코드 관리 페이지에서 **+ 레코드 추가 를 선택합니다.**

1. **유형에서** **드롭다운 목록에서 SRV를** 선택합니다.

1. 다음 표의 값을 선택하거나 복사하여 붙여넣습니다. 
    
    | **유형** |**서비스**|**프로토콜**|**Weight(가중치)**|**Port(포트)**|**대상**|**Priority(우선 순위)**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    | SRV |_sip  <br/> |TLS  <br/> |100  <br/> |443  <br/> |sipdir.online.lync.com  <br/> **이 값은 기간(.)으로 끝날 수 없습니다.** <br/> | 1  <br/> | 1시간  <br/> |
    | SRV |_sipfederationtls  <br/> |TCP <br/> |100  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> **이 값은 기간(.)으로 끝날 수 없습니다.** <br/> |1  <br/> | 1 Hour  <br/> |
  
6. 추가 **를 선택합니다.**
  
7. 다른 SRV 레코드를 추가하려면
    
    고급 **DNS 섹션에서** 표의 두 번째 행 값을 사용하여 레코드를 만든  다음 추가를 다시 선택하여 해당 레코드를 완료합니다. 
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요. 

### <a name="add-the-two-required-cname-records"></a>두 개의 필수 CNAME 레코드 추가 
    
1. 시작하려면 이 링크를 사용하여 web.com [페이지로 이동합니다.](https://checkout.web.com/manage-it/index.jsp) 먼저 로그인합니다.
  
1. 방문 페이지에서 도메인 **이름을 선택합니다.** 
  
1. 작업 **아래에서** 세 개의 점을 선택한  다음 드롭다운 목록에서 관리를 선택합니다.
 
    :::image type="content" source="../../media/dns-webcom/webcom-domains-1.png" alt-text="드롭다운 목록에서 관리를 선택합니다.":::
 
1. 아래로 스크롤하여 **고급** 도구 를 선택하고 **고급 DNS 레코드** 옆에 있는 관리 를 **선택합니다.**
  
    :::image type="content" source="../../media/dns-webcom/webcom-domains-2.png" alt-text="고급 DNS 레코드 옆에 있는 관리를 선택합니다.":::

    고급 DNS 레코드  관리 페이지로 이동하려면 계속을 선택해야 할 수 있습니다.

1. 고급 DNS 레코드 관리 페이지에서 **+ 레코드 추가 를 선택합니다.**

1. **유형에서** 드롭다운 목록에서 **CNAME을** 선택합니다.

1. 다음 표의 값을 선택하거나 복사하여 붙여넣습니다. 
    
    | **유형**|**참조 | 호스트 이름**|**별칭 대상**| **TTL** |
    |:-----|:-----|:-----|:-----|:-----|
    | CNAME | 기타 호스트 | sip  <br/> |sipdir.online.lync.com  <br/> **이 값은 기간(.)으로 끝날 수 없습니다.** <br/> |1시간  <br/> |
    | CNAME| 기타 호스트 | lyncdiscover  <br/> |webdir.online.lync.com  <br/> **이 값은 기간(.)으로 끝날 수 없습니다.** <br/> | 1 Hour  <br/> |
  
1. 추가 **를 선택합니다.**
  
1. 위의 단계와 표의 두 번째 행 값을 사용하여 다른 CNAME 레코드를 추가합니다.
    
> [!NOTE]
> 일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 
  
## <a name="advanced-option-intune-and-mobile-device-management-for-microsoft-365"></a>고급 옵션: Intune 및 모바일 장치 관리 Microsoft 365

이 서비스는 도메인에 연결하는 모바일 장치를 보호하고 원격으로 관리하는 데 도움이 됩니다. 모바일 장치 관리에는 사용자가 서비스에 장치를 등록할 수 있도록 2개 CNAME 레코드가 필요합니다.

### <a name="add-the-two-required-cname-records"></a>두 개의 필수 CNAME 레코드 추가

1. 시작하려면 이 링크를 사용하여 web.com [페이지로 이동합니다.](https://checkout.web.com/manage-it/index.jsp) 먼저 로그인합니다.
  
1. 방문 페이지에서 도메인 **이름을 선택합니다.** 
  
1. 작업 **아래에서** 세 개의 점을 선택한  다음 드롭다운 목록에서 관리를 선택합니다.
 
    :::image type="content" source="../../media/dns-webcom/webcom-domains-1.png" alt-text="드롭다운 목록에서 관리를 선택합니다.":::
 
1. 아래로 스크롤하여 **고급** 도구 를 선택하고 **고급 DNS 레코드** 옆에 있는 관리 를 **선택합니다.**
    
    고급 DNS 레코드  관리 페이지로 이동하려면 계속을 선택해야 할 수 있습니다.
  
    :::image type="content" source="../../media/dns-webcom/webcom-domains-2.png" alt-text="고급 DNS 레코드 옆에 있는 관리를 선택합니다.":::

1. 고급 DNS 레코드 관리 페이지에서 **+ 레코드 추가 를 선택합니다.**

1. **유형에서** 드롭다운 목록에서 **CNAME을** 선택합니다.

1. 다음 표의 값을 선택하거나 복사하여 붙여넣습니다. 
    
    | **유형**|**참조 | 호스트 이름**|**별칭 대상**| **TTL** |
    |:-----|:-----|:-----|:-----|:-----|
    | CNAME | 기타 호스트 | enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> **이 값은 기간(.)으로 끝날 수 없습니다.** <br/> | 1시간  <br/> |
    | CNAME | 기타 호스트 |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> **이 값은 기간(.)으로 끝날 수 없습니다.** <br/> | 1 Hour  <br/> |
  
1. 추가 **를 선택합니다.**
  
1. 위의 단계와 표의 두 번째 행 값을 사용하여 다른 CNAME 레코드를 추가합니다.
    
> [!NOTE]
> 일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.