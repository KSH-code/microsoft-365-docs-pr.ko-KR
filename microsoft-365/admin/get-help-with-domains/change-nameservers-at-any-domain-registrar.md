---
title: 모든 도메인 등록 기관에서 Microsoft 365을 설정 하도록 이름 서버 변경
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
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEU150
- GEA150
ms.assetid: a8b487a9-2a45-4581-9dc4-5d28a47010a2
description: 전자 메일 및 비즈니스용 Skype 온라인 등의 서비스에서 고유한 도메인 이름을 사용 하도록 Microsoft 365에서 도메인을 추가 및 설정 하는 방법에 대해 알아봅니다.
ms.custom: okr_smb
ms.openlocfilehash: e987d1194d3ee86548a6628310ebdfd14cdbb9ea
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43628509"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-any-domain-registrar"></a>모든 도메인 등록 기관에서 Microsoft 365을 설정 하도록 이름 서버 변경

 원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.md)** 하세요. 
  
먼저 [도메인 설정 (호스트 관련 지침)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) 을 선택 하 여 등록 기관에 대 한 지침이 있는지 확인 합니다. 
  
다음 지침에 따라 Microsoft 365에서 도메인을 추가 및 설정 하 여 전자 메일 및 비즈니스용 Skype Online과 같은 서비스에서 자체 도메인 이름을 사용 하도록 합니다. 이렇게 하려면 도메인을 확인 한 다음 올바른 DNS 레코드를 설정할 수 있도록 도메인의 이름 서버를 Microsoft 365으로 변경 합니다. 다음 문이 상황을 설명 하는 경우 다음 단계를 수행 합니다.
  
- 사용자의 고유한 도메인을 Microsoft 365에서 사용 하도록 설정 하려고 합니다.
    
- Microsoft 365에서 DNS 레코드를 관리 하도록 하려고 합니다. 원하는 경우 [고유한 DNS 레코드를 관리](../setup/add-domain.md)할 수도 있습니다.
    
## <a name="add-a-txt-or-mx-record-for-verification"></a>확인을 위해 TXT 또는 MX 레코드 추가
<a name="BKMK_verify"> </a>

> [!NOTE]
> 이러한 레코드 중 하나만 만들어집니다. TXT가 기본 레코드 형식이지만 일부 DNS 호스팅 공급자는 이를 지원하지 않으며, 이 경우 대신 MX 레코드를 만들면 됩니다. 
  
Microsoft 365에서 도메인을 사용 하기 전에 사용자가 소유 하 고 있는지 확인 해야 합니다. 도메인 등록 기관에서 계정에 로그인 하 고 DNS 레코드를 만들 수 있는 기능은 Microsoft 365에 도메인을 소유 하 고 있음을 증명 합니다.
  
> [!NOTE]
> 이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다. 
  
### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a>DNS 호스팅 공급자 웹 사이트에서 새 레코드를 만들 수 있는 영역을 찾습니다.

1. DNS 호스팅 공급자의 웹 사이트에 로그인합니다.
    
2. 도메인을 선택합니다.
    
3. 도메인의 DNS 레코드를 편집할 수 있는 페이지를 찾습니다.
    
### <a name="create-the-record"></a>레코드 만들기

만드는 레코드가 TXT 레코드인지 MX 레코드인지에 따라 다음 중 하나를 수행합니다.
  
**TXT 레코드를 만드는 경우 다음 값을 사용합니다.**
    
|||||
|:-----|:-----|:-----|:-----|
|**Record Type(레코드 종류)** <br/> |**Alias(별칭)** 또는 **Host Name(호스트 이름)** <br/> |**Value(값)** <br/> |**TTL** <br/> |
|TXT  <br/> |다음 중 하나를 수행합니다. **@** 을 입력하거나 필드를 비워 두거나 도메인 이름을 입력합니다.      <br/> > [!NOTE]> 이 필드의 경우 각 DNS 호스트마다 요구 사항이 다릅니다.           
|MS=ms *XXXXXXXX*  <br/> > [!NOTE]> 이 값은 예시입니다. 여기에는 Microsoft 365의 표에 나와 있는 특정 **대상 또는 지점** 값을 사용 합니다.           [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)          |이 값을 **1시간** 또는 등가의 분( **60** ), 초( **3600** ) 단위로 설정합니다.  <br/> |
   
**MX 레코드를 만드는 경우 다음 값을 사용합니다.**
    
||||||
|:-----|:-----|:-----|:-----|:-----|
|**Record Type(레코드 종류)**|**Alias(별칭)** 또는 **Host Name(호스트 이름)**|**Value(값)**|**Priority(우선 순위)**|**TTL**|
|MX|**@** 또는 도메인 이름을 입력합니다. |MS=ms *XXXXXXXX* > [!NOTE]> 이 값은 예시입니다. 여기에는 Microsoft 365의 표에 나와 있는 특정 **대상 또는 지점** 값을 사용 합니다.           [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)          |**우선 순위**의 경우, 메일 흐름에 사용되는 MX 레코드와의 충돌을 피하기 위해 기존 MX 레코드의 우선 순위보다 낮은 우선 순위를 사용합니다. 우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](../setup/domains-faq.md#what-is-mx-priority)을 참조하세요. |이 값을 **1시간** 또는 등가의 분( **60** ), 초( **3600** ) 단위로 설정합니다. |
   
### <a name="save-the-record"></a>레코드 저장

도메인 등록 기관 사이트에서 레코드를 추가 했으므로 이제 Microsoft 365으로 돌아가 Microsoft 365에 요청 하 여 레코드를 찾을 수 있습니다.
  
Microsoft 365에서 올바른 TXT 레코드를 찾으면 도메인이 확인 된 것입니다.
  

1. I관리 센터에서 ** 설정 ** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인 </a> 페이지로 이동하십시오.
    
2. **도메인** 페이지에서 확인 중인 도메인을 선택합니다. 
    
  
3. **설정** 페이지에서 **설정 시작**을 선택합니다.
 
    
  
4. **도메인 확인** 페이지에서 **확인**을 선택합니다.
    
    
  
> [!NOTE]
>  일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 
  
## <a name="change-your-domains-nameserver-ns-records"></a>도메인의 NS(이름 서버) 레코드 변경
<a name="BKMK_nameservers"> </a>

Microsoft 365에서 도메인 설정 마법사의 마지막 단계로 이동 하면 한 가지 작업이 남아 있습니다. Microsoft 365 services (예를 들어, 전자 메일)를 사용 하 여 도메인을 설정 하려면 도메인 등록 기관에서 도메인의 이름 서버 (또는 NS) 레코드를 Microsoft 365 기본 및 보조 이름 서버를 가리키도록 변경 합니다. 그러면 Microsoft 365에서 DNS를 호스트 하므로 서비스에 필요한 DNS 레코드가 자동으로 설정 됩니다. 도메인 등록 기관의 웹 사이트에서 도움말 콘텐츠를 제공한 경우 해당 단계를 따라 이름 서버 레코드를 직접 업데이트할 수 있습니다. DNS에 익숙하지 않다면 도메인 등록 기관의 지원에 문의하세요.

::: moniker range="o365-worldwide"
  
도메인 등록 기관 웹 사이트에서 도메인 이름 서버를 직접 변경하려면 다음 단계를 따릅니다.
  
1. 도메인 등록 기관의 웹 사이트에서 도메인의 이름 서버를 편집할 수 있는 영역을 찾습니다.
    
2. 이름 서버 레코드를 두 개 만들거나 기존 이름 서버 레코드를 다음 값과 일치하도록 편집합니다.
    
|||
|:-----|:-----|
|첫 번째 이름 서버  <br/> |ns1.bdm.microsoftonline.com  <br/> |
|두 번째 이름 서버  <br/> |ns2.bdm.microsoftonline.com  <br/> |
   
   > [!TIP]
   > 두 개 이상의 이름 서버 레코드를 사용 해야 합니다. 나열 된 다른 이름 서버 있으면 삭제 하거나 **ns3.bdm.microsoftonline.com** 및 **ns4.bdm.microsoftonline.com**로 변경할 수 있습니다. 
  
3. 변경 내용을 저장합니다.
    
> [!CAUTION]
> Microsoft 365 이름 서버를 가리키도록 도메인의 NS 레코드를 변경 하면 현재 도메인에 연결 된 모든 서비스가 영향을 받습니다. 전자 메일 주소 추가와 같은 마법사의 특정 단계를 건너뛰거나 블로그, 장바구니 또는 기타 서비스에 사용자 도메인을 사용 중인 경우 추가 단계가 필요합니다. 추가 단계를 수행하지 않으면 이러한 변경으로 인해 전자 메일 또는 현재 웹 사이트에 액세스 불가와 같은 서비스 중단이 발생할 수 있습니다. 

::: moniker-end

::: moniker range="o365-21vianet"
  
1. 도메인 등록 기관의 웹 사이트에서 도메인의 이름 서버를 편집할 수 있는 영역을 찾습니다.
    
2. 이름 서버 레코드를 두 개 만들거나 기존 이름 서버 레코드를 다음 값과 일치하도록 편집합니다.
    
|||
|:-----|:-----|
|첫 번째 이름 서버  <br/> |ns1.dns.partner.microsoftonline.cn  <br/> |
|두 번째 이름 서버  <br/> |ns2.dns.partner.microsoftonline.cn  <br/> |
   
   > [!TIP]
   > 두 개 이상의 이름 서버 레코드를 사용 해야 합니다. 나열 된 다른 이름 서버 있으면 삭제 하거나 **ns3.dns.partner.microsoftonline.cn** 및 **ns4.dns.partner.microsoftonline.cn**로 변경할 수 있습니다. 
  
3. 변경 내용을 저장합니다.
    
> [!CAUTION]
> 21Vianet 이름 서버에서 운영 하는 Office 365을 가리키도록 도메인의 NS 레코드를 변경 하면 현재 도메인에 연결 된 모든 서비스가 영향을 받습니다. 전자 메일 주소 추가와 같은 마법사의 특정 단계를 건너뛰거나 블로그, 장바구니 또는 기타 서비스에 사용자 도메인을 사용 중인 경우 추가 단계가 필요합니다. 추가 단계를 수행하지 않으면 이러한 변경으로 인해 전자 메일 또는 현재 웹 사이트에 액세스 불가와 같은 서비스 중단이 발생할 수 있습니다. 

::: moniker-end
  
예를 들어, 전자 메일 및 웹 사이트 호스팅 시 다음과 같은 추가 단계가 필요합니다.
  
- NS 레코드를 변경 하기 전에 도메인을 사용 하는 모든 전자 메일 주소를 Microsoft 365로 이동 합니다.
    
- 현재 웹 사이트 주소에 사용되는 도메인(예: www.fourthcoffee.com)을 추가하려면, 도메인을 추가하는 동안 현재 사이트가 호스팅되는 곳에 웹 사이트가 호스팅되도록 하는 단계를 수행할 수 있습니다. 도메인을 추가 하는 동안 사이트를 호스트 하는 웹 사이트를 유지 하 여 Microsoft 365를 가리키도록 도메인의 NS 레코드를 변경한 후에도 사용자가 웹 사이트로 이동할 수 있도록 하려면 다음 단계를 수행 하면 됩니다.

1. I관리 센터에서 ** 설정 ** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인 </a> 페이지로 이동하십시오.

3. 도메인 페이지에서 도메인을 선택합니다.

4. **DNS 설정**에서 **사용자 지정 레코드**를 선택한 다음 **새 사용자 지정 레코드**를 선택 합니다.

5. 추가할 DNS 레코드 유형을 선택 하 고 새 레코드에 대 한 정보를 입력 합니다.

6. **저장**을 선택합니다.
    
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. 그러면 Microsoft 전자 메일 및 기타 서비스가 모두 도메인에서 작동 하도록 설정 됩니다. 
  

