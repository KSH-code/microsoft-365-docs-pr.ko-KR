---
title: 모든 DNS 호스팅 공급자에서 DNS 레코드 만들기
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 7b7b075d-79f9-4e37-8a9e-fb60c1d95166
description: Microsoft 365용 모든 DNS 호스팅 공급자에서 도메인을 확인하고 DNS 레코드를 만드는 방법을 배웁니다.
ms.custom: okr_smb
ms.openlocfilehash: a2d9b57f0230aa736944727e39845f3a0a533426
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048786"
---
# <a name="create-dns-records-at-any-dns-hosting-provider"></a>모든 DNS 호스팅 공급자에서 DNS 레코드 만들기

 원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.md)** 하세요. 
  
호스트를 찾으려면 [호스트 별 지침](https://support.office.com/article/ae950c9e-e8d9-4108-b0cb-449156998580) 목록을 확인하고 다음 단계에 따라 필요한 모든 레코드를 추가합니다. 
  
사용 중인 도메인의 DNS 호스팅 공급자 또는 도메인 등록 기관을 모르는 경우 [도메인 등록자 또는 DNS 호스팅 공급자 찾기](../get-help-with-domains/find-your-domain-registrar.md)를 참조하세요.
  
레코드를 직접 설정하려는 경우 추가해야 할 레코드입니다. 확인 레코드와 MX 레코드는 도메인마다 고유합니다. 이를 설정하려면 도메인에 특정 "토큰"값을 가져와 사용해야 합니다. 이 작업을 수행하는 방법은 아래 단계에 설명되어 있습니다.
  
> [!IMPORTANT]
> 각 유형의 DNS 레코드를 생성하기 위해 정보를 입력하거나 붙여 넣은 상자 또는 *필드*의 정확한 이름은 DNS 호스트마다 다릅니다. DNS 호스트는 웹 사이트에 도움말을 표시하여 여기에 표시된 지침을 해당 웹 사이트의 정확한 필드에 매핑할 수 있습니다. [Microsoft 365용 DNS 레코드 만들기](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23.aspx)에서 DNS 호스트에 대한 단계별 지침이 있는지 확인하십시오. > 일부 DNS 호스트를 사용하면 Microsoft 365에서 [서비스 제한이 발생](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)되는 모든 필수 레코드 유형을 만들 수 없습니다. 예를 들어 도메인의 호스트가 SRV, TXT 또는 CNAME 레코드를 지원하지 않는 경우 모든 필수 레코드를 지원하는 DNS 호스트로 [도메인을 이전](../get-help-with-domains/buy-a-domain-name.md)하는 것이 좋습니다. Microsoft 365로 빠르고 자동화된 프로세스를 설정하려면 도메인을 GoDaddy로 이전하는 것이 좋습니다. 
  
> [!NOTE]
> 일반적으로 몇 분 정도만 있으면 DNS 변경 사항이 적용됩니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가 한 후 메일 흐름 또는 기타 문제에 문제가 있는 경우 [도메인 이름 또는 DNS 레코드를 변경한 후 문제 찾기 및 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하십시오. 
  
## <a name="add-a-txt-or-mx-record-for-verification"></a>확인을 위해 TXT 또는 MX 레코드 추가
<a name="BKMK_verify"> </a>

> [!NOTE]
> 이러한 레코드 중 하나만 만들어집니다. TXT가 기본 레코드 형식이지만 일부 DNS 호스팅 공급자는 이를 지원하지 않으며, 이 경우 대신 MX 레코드를 만들면 됩니다. 
  
Microsoft 365에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft 365에 도메인을 소유하고 있음을 증명할 수 있습니다.
  
> [!NOTE]
> 이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다. 
  
 **사용 중인 DNS 호스팅 공급자 웹 사이트에서 새 레코드를 만들 수 있는 영역을 찾습니다.**
  
1. DNS 호스팅 공급자의 웹 사이트에 로그인합니다.
    
2. 도메인을 선택합니다.
    
3. 도메인의 DNS 레코드를 편집할 수 있는 페이지를 찾습니다.
    
 **레코드를 만듭니다.**
  
1. 만드는 레코드가 TXT 레코드인지 MX 레코드인지에 따라 다음 중 하나를 수행합니다.
    
   - **TXT 레코드를 만드는 경우 다음 값을 사용합니다.**
    
      |||||
      |:-----|:-----|:-----|:-----|
      |**Record Type(레코드 종류)**|**Alias(별칭)** 또는 **Host Name(호스트 이름)**|**Value(값)**|**TTL**|
      |TXT|다음 중 하나를 수행합니다. **@** 을 입력하거나 필드를 비워 두거나 도메인 이름을 입력합니다.      <br/> **참고: ** 이 필드의 경우 각 DNS 호스트마다 요구 사항이 다릅니다. |MS=ms *XXXXXXXX*  <br/> **참고:** 이 값은 예시입니다. 여기에는 Microsoft 365의 표에 있는 특정 **주소를 지정할 대상 또는 지점** 값을 사용합니다.  <br/>        [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)     <br/>     |이 값을 **1시간** 또는 등가의 분( **60** ), 초( **3600** ) 단위로 설정합니다.  |
   
   - **MX 레코드를 만드는 경우 다음 값을 사용합니다.**
    
      ||||||
      |:-----|:-----|:-----|:-----|:-----|
      |**Record Type(레코드 종류)**|**Alias(별칭)** 또는 **Host Name(호스트 이름)**|**Value(값)**|**Priority(우선 순위)**|**TTL**|
      |MX|**@** 또는 도메인 이름을 입력합니다. |MS=ms *XXXXXXXX* <br/> **참고:** 이 값은 예시입니다. 여기에는 Office 365의 표에 있는 특정 **보낼 대상 또는 지점** 값을 사용합니다.    <br/>       [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)     <br/>     |**우선 순위**의 경우, 메일 흐름에 사용되는 MX 레코드와의 충돌을 피하기 위해 기존 MX 레코드의 우선 순위보다 낮은 우선 순위를 사용합니다. <br/> 우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)을 참조하세요. <br/> |이 값을 **1시간** 또는 등가의 분( **60** ), 초( **3600** ) 단위로 설정합니다. |
   
2. 레코드를 저장합니다.
    
이제 도메인 등록 기관에 레코드가 추가되었습니다. Microsoft 365로 돌아가서 Microsoft 365에 레코드를 찾을 것을 요청합니다.
  
Microsoft 365에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.
  
1. I관리 센터에서 ** 설정 ** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인 </a> 페이지로 이동하십시오.
    
2. **도메인** 페이지에서 확인 중인 도메인을 선택합니다. 
  
3. **설정** 페이지에서 **설정 시작**을 선택합니다.
       
4. **도메인 확인** 페이지에서 **확인**을 선택합니다.   
  
> [!NOTE]
>  일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 
  
## <a name="add-mx-record-to-route-email"></a>전자 메일을 라우팅하기 위해 MX 레코드 추가
<a name="BKMK_add_MX"> </a>

사용자 도메인의 전자 메일이 Microsoft 365로 전송되도록 MX 레코드를 추가합니다.  *도메인의 MX 레코드를 업데이트하면 해당 도메인을 사용하는 사용자의 모든 새 전자 메일이 이제 Microsoft 365로 옵니다*. [전자 메일 및 연락처를 Microsoft 365로 마이그레이션하기](../setup/migrate-email-and-contacts-admin.md)로 결정한 경우가 아니면, 이미 가지고 있는 전자 메일은 현재 전자 메일 호스트에 남습니다.

 **작업**
  
도메인에 대한 레코드를 만들 수 있는 페이지를 찾습니다.
  
1. DNS 호스트의 웹 사이트에 로그인합니다.
    
2. 도메인을 선택합니다.
    
3. 도메인의 DNS 레코드를 편집할 수 있는 페이지를 찾습니다.
    
::: moniker range="o365-worldwide"

  추가할 MX 레코드에는 \<MX 토큰\> .mail.protection.outlook.com과 같은 값 (**지점 주소** 값)이 포함됩니다. 여기서 \<MX 토큰\>은 MSxxxxxxx와 같은 값입니다. 

::: moniker-end

::: moniker range="o365-germany"

  추가 할 MX 레코드에는 \<MX 토큰\> .mail.protection.outlook.de와 같은 값(** 지점 주소** 값)이 포함됩니다. 여기서 \<MX 토큰\>은 MSxxxxxxx와 같은 값입니다. 

::: moniker-end

4. DNS 호스트의 웹 사이트에서 새 MX 레코드를 추가합니다.
    
    이제 Microsoft 365에서 [MX 레코드에 대한 정보를 가져옵니다](../get-help-with-domains/information-for-dns-records.md). 
    
5. 위 단계의 MX 레코드에 대해 **대상 주소** 값을 복사합니다. 
    
    이 값은 DNS 호스트의 사이트에서 만드는 레코드에 사용합니다. 이에 대해서는 다음 단계에서 설명합니다.
    
6. DNS 호스트의 사이트에서 새 MX 레코드에 정확히 다음 값으로 필드가 설정되었는지 확인합니다.
    
   - **Record Type(레코드 형식)**: **MX**
    
   - **Priority(우선 순위)**: MX 레코드의 우선 순위를 사용할 수 있는 가장 높은 값(일반적으로 **0**)으로 설정합니다.
    
      우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)을 참조하세요.
    
   - **호스트 이름**: **@**
    
   - **대상 주소**: Microsoft 365에서 복사한 **대상 주소** 값을 여기에 붙여 넣습니다. 
    
   - **TTL**: 이 값을 **1시간** 또는 등가의 분(**60**), 초(**3600**) 단위로 설정합니다. 
    
7. 레코드를 저장합니다.
    
다른 모든 MX 레코드는 제거합니다.
  
전자 메일을 Microsoft 365 이외의 다른 위치로 보내는 MX 레코드가 이 도메인에 있다면 모두 삭제합니다.
  
## <a name="add-three-cname-records"></a>3개의 CNAME 레코드 추가
<a name="BKMK_add_MX"> </a>

::: moniker range="o365-worldwide"

아래 단계에 따라 Microsoft 365에 필요한 세 개의 CNAME 레코드를 추가하십시오. Microsoft 365에 추가 CNAME 레코드가 나열되면 여기에 표시된 동일한 일반적인 단계에 따라 해당 레코드를 추가합니다.
  
DNS 호스트의 웹 사이트에서 3개의 새 CNAME 레코드를 일반적으로 한 번에 하나씩 만듭니다.
  
1. 각각의 새 레코드의 상자에서 다음 값을 입력하거나 복사하여 붙여넣습니다. 처음 세 개의 새 레코드 각각을 추가 한 후 다른 CNAME 레코드를 작성하도록 선택하십시오.
    
      |||||
      |:-----|:-----|:-----|:-----|
      |**레코드 종류** <br/> |**Host(호스트)** <br/> |**Points to(연결 대상)** <br/> |**TTL** <br/> |
      |CNAME (Alias)(CNAME(별칭))  <br/> |autodiscover  <br/> |autodiscover.outlook.com  <br/> |1시간  <br/> |
      |CNAME (Alias)(CNAME(별칭))  <br/> |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |1시간  <br/> |
      |CNAME (Alias)(CNAME(별칭))  <br/> |sip  <br/> |sipdir.online.lync.com  <br/> |1시간  <br/> |
   
   > [!NOTE]
   > **TTL**의 경우 :이 값을 ** 1시간 **으로 설정하거나 분(**60 **), 초 (**3600**) 등으로 설정하십시오. >이 레코드는 Exchange, Lync 또는 비즈니스용 Skype 하이브리드 배포에는 적용되지 않습니다. 
  
2. 모두 마쳤으면 레코드를 저장합니다.
    
::: moniker-end
::: moniker range="o365-germany"

아래 단계에 따라 Microsoft 365에 필요한 세 개의 CNAME 레코드를 추가하십시오. Microsoft 365에 추가 CNAME 레코드가 나열되면 여기에 표시된 동일한 일반적인 단계에 따라 해당 레코드를 추가합니다.
  
DNS 호스트의 웹 사이트에서 3개의 새 CNAME 레코드를 일반적으로 한 번에 하나씩 만듭니다.
  
1. 각각의 새 레코드의 상자에서 다음 값을 입력하거나 복사하여 붙여넣습니다. 처음 세 개의 새 레코드 각각을 추가 한 후 다른 CNAME 레코드를 작성하도록 선택하십시오.
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**레코드 종류** <br/> |**Host(호스트)** <br/> |**Points to(연결 대상)** <br/> |**TTL** <br/> |
    |CNAME (Alias)(CNAME(별칭))  <br/> |autodiscover  <br/> |autodiscover-outlook.office.de  <br/> |1시간  <br/> |
    |CNAME (Alias)(CNAME(별칭))  <br/> |lyncdiscover  <br/> |webdir.online.skype.de  <br/> |1시간  <br/> |
    |CNAME (Alias)(CNAME(별칭))  <br/> |sip  <br/> |sipdir.online.lync.de  <br/> |1시간  <br/> |
   
     > [!NOTE]
     > **TTL**의 경우 :이 값을 ** 1시간 **으로 설정하거나 분(**60 **), 초 (**3600**) 등으로 설정하십시오. >이 레코드는 Exchange, Lync 또는 비즈니스용 Skype 하이브리드 배포에는 적용되지 않습니다. 
  
2. 모두 마쳤으면 레코드를 저장합니다.
    
::: moniker-end

::: moniker range="o365-21vianet"

아래 단계에 따라 Microsoft 365에 필요한 세 개의 CNAME 레코드를 추가하십시오. Microsoft 365에 추가 CNAME 레코드가 나열되면 여기에 표시된 동일한 일반적인 단계에 따라 해당 레코드를 추가합니다.
  
DNS 호스트의 웹 사이트에서 3개의 새 CNAME 레코드를 일반적으로 한 번에 하나씩 만듭니다.
  
1. 각각의 새 레코드의 상자에서 다음 값을 입력하거나 복사하여 붙여넣습니다. 처음 세 개의 새 레코드 각각을 추가 한 후 다른 CNAME 레코드를 작성하도록 선택하십시오.
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**레코드 종류** <br/> |**Host(호스트)** <br/> |**Points to(연결 대상)** <br/> |**TTL** <br/> |
    |CNAME (Alias)(CNAME(별칭))  <br/> |autodiscover  <br/> |autodiscover.partner.outlook.cn  <br/> |1시간  <br/> |
    |CNAME (Alias)(CNAME(별칭))  <br/> |lyncdiscover  <br/> |webdir.online.partner.lync.cn  <br/> |1시간  <br/> |
    |CNAME (Alias)(CNAME(별칭))  <br/> |sip  <br/> |webdir.online.partner.lync.cn  <br/> |1시간  <br/> |
   
     > [!NOTE]
     > **TTL**의 경우 :이 값을 ** 1시간 **으로 설정하거나 분(**60 **), 초 (**3600**) 등으로 설정하십시오. >이 레코드는 Exchange, Lync 또는 비즈니스용 Skype 하이브리드 배포에는 적용되지 않습니다. 
  
2. 모두 마쳤으면 레코드를 저장합니다.
    
::: moniker-end

## <a name="add-two-cname-records-for-mobile-device-management-mdm-for-microsoft-365"></a>Microsoft 365용 MDM(모바일 장치 관리)에 대한 2개의 CNAME 레코드 추가
<a name="BKMK_add_MX"> </a>

::: moniker range="o365-worldwide"

> [!IMPORTANT]
> Microsoft 365용 MDM (모바일 장치 관리)이 있는 경우 두 개의 추가 CNAME 레코드를 만들어야 합니다. 다른 4개의 CNAME 레코드를 만드는 데 사용한 절차를 따르되 다음 표의 값을 입력합니다. >(MDM이 없는 경우에는 이 단계를 건너뛸 수 있습니다. 
  
   |||||
   |:-----|:-----|:-----|:-----|
   |**레코드 종류** <br/> |**Host(호스트)** <br/> |**Points to(연결 대상)** <br/> |**TTL** <br/> |
   |CNAME (Alias)(CNAME(별칭))  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |1시간  <br/> |
   |CNAME (Alias)(CNAME(별칭))  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment.manage.microsoft.com  <br/> |1시간  <br/> |
   
::: moniker-end

::: moniker range="o365-germany"

> [!IMPORTANT]
> Microsoft 365용 MDM (모바일 장치 관리)이 있는 경우 두 개의 추가 CNAME 레코드를 만들어야 합니다. 다른 4개의 CNAME 레코드를 만드는 데 사용한 절차를 따르되 다음 표의 값을 입력합니다. >(MDM이 없는 경우에는 이 단계를 건너뛸 수 있습니다. 
  
   |||||
   |:-----|:-----|:-----|:-----|
   |**레코드 종류** <br/> |**Host(호스트)** <br/> |**Points to(연결 대상)** <br/> |**TTL** <br/> |
   |CNAME (Alias)(CNAME(별칭))  <br/> |enterpriseregistration  <br/> |enterpriseregistration.microsoftonline.de  <br/> |1시간  <br/> |
   |CNAME (Alias)(CNAME(별칭))  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |1시간  <br/> |
   
::: moniker-end

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가
<a name="BKMK_add_MX"> </a>

::: moniker range="o365-worldwide"

> [!IMPORTANT]
> 도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다. 도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다. 도메인에 이미 SPF 레코드가 있는 경우 Microsoft 365의 새 SPF 레코드를 만들지 마세요. 대신, 필수 Microsoft 365 값을 현재 레코드에 추가하여 두 값 집합을 모두 포함하는 *단일* SPF 레코드가 있도록 합니다.
  
DNS 호스트 웹 사이트에서 기존 SPF 레코드를 편집하거나 SPF에 대한 새 TXT 레코드를 만듭니다.
  
> [!IMPORTANT]
> SPF는 스푸핑 차단을 돕지만 SPF가 방어할 수 없는 스푸핑 기술이 있습니다. 이 같은 기술로부터 보호하려면 SPF를 설치한 후에 Microsoft 365의 DKIM 및 DMARC도 구성해야 합니다. 시작하려면 [DKIM을 사용하여 Microsoft 365의 도메인에서 보낸 발신 이메일의 유효성을 검사](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx)를 참조하세요. 다음으로 [DMARC를 사용하여 Microsoft 365에서 전자 메일 유효성 검사](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx)를 참조하세요. 
  
1. 새 레코드에 대한 상자에 아래의 값 집합 중 해당 상황에 적용되는 값 집합을 입력하거나 복사하여 붙여넣습니다.
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**레코드 종류** <br/> |**Host(호스트)** <br/> |**TXT 값** <br/> |**TTL** <br/> |
    |TXT(텍스트)  <br/> |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **참고: ** 모든 간격이 올바르게 유지되도록 이 항목을 복사하여 붙여넣는 것이 좋습니다.           |1시간  <br/> |
   
    For **TTL**: Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc. 
    
2. 모두 마쳤으면 레코드를 저장합니다.
    
3. SPF 레코드의 유효성을 검사하려면 이러한 [SPF 유효성 검사 도구](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain) 중 하나를 사용합니다.

::: moniker-end

::: moniker range="o365-germany"

> [!IMPORTANT]
> 도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다. 도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다. 도메인에 이미 SPF 레코드가 있는 경우 Microsoft 365의 새 SPF 레코드를 만들지 마세요. 대신, 필수 Microsoft 365 값을 현재 레코드에 추가하여 두 값 집합을 모두 포함하는 *단일* SPF 레코드가 있도록 합니다. 
  
DNS 호스트 웹 사이트에서 기존 SPF 레코드를 편집하거나 SPF에 대한 새 TXT 레코드를 만듭니다.
  
> [!IMPORTANT]
> SPF는 스푸핑 차단을 돕지만 SPF가 방어할 수 없는 스푸핑 기술이 있습니다. 이 같은 기술로부터 보호하려면 SPF를 설치한 후에 Microsoft 365의 DKIM 및 DMARC도 구성해야 합니다. 시작하려면 [DKIM을 사용하여 Microsoft 365의 도메인에서 보낸 발신 이메일의 유효성을 검사](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx)를 참조하세요. 다음으로 [DMARC를 사용하여 Microsoft 365에서 전자 메일 유효성 검사](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx)를 참조하세요. 
  
1. 새 레코드에 대한 상자에 아래의 값 집합 중 해당 상황에 적용되는 값 집합을 입력하거나 복사하여 붙여넣습니다.
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**레코드 종류**|**Host(호스트)**|**TXT 값**|**TTL**|
    |TXT(텍스트)|@|v=spf1 include:spf.protection.outlook.de -all <br/>  모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.           |1시간|
   
    For **TTL**: Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc. 
    
2. 모두 마쳤으면 레코드를 저장합니다.
    
3. SPF 레코드의 유효성을 검사하려면 이러한 [SPF 유효성 검사 도구](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain) 중 하나를 사용합니다.
    
::: moniker-end

::: moniker range="o365-21vianet"

> [!IMPORTANT]
> 도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다. 도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다. 도메인에 이미 SPF 레코드가 있는 경우 Microsoft 365의 새 SPF 레코드를 만들지 마세요. 대신, 필수 Microsoft 365 값을 현재 레코드에 추가하여 두 값 집합을 모두 포함하는 *단일* SPF 레코드가 있도록 합니다. 
  
DNS 호스트 웹 사이트에서 기존 SPF 레코드를 편집하거나 SPF에 대한 새 TXT 레코드를 만듭니다.
  
> [!IMPORTANT]
> SPF는 스푸핑 차단을 돕지만 SPF가 방어할 수 없는 스푸핑 기술이 있습니다. 이 같은 기술로부터 보호하려면 SPF를 설치한 후에 Microsoft 365의 DKIM 및 DMARC도 구성해야 합니다. 시작하려면 [DKIM을 사용하여 Microsoft 365의 도메인에서 보낸 발신 이메일의 유효성을 검사](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx)를 참조하세요. 다음으로 [DMARC를 사용하여 Microsoft 365에서 전자 메일 유효성 검사](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx)를 참조하세요. 
  
1. 새 레코드에 대한 상자에 아래의 값 집합 중 해당 상황에 적용되는 값 집합을 입력하거나 복사하여 붙여넣습니다.
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**레코드 종류**|**Host(호스트)**|**TXT 값**|**TTL**|
    |TXT(텍스트)|@|v=spf1 include:spf.protection.partner.outlook.cn -all> [!NOTE]>모든 간격이 올바르게 유지되도록이 항목을 복사하여 붙여넣는 것이 좋습니다.            |1시간|
   
    For **TTL**: Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc. 
    
2. 모두 마쳤으면 레코드를 저장합니다.
    
3. SPF 레코드의 유효성을 검사하려면 이러한 [SPF 유효성 검사 도구](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain) 중 하나를 사용합니다.
    
::: moniker-end

## <a name="add-two-srv-records"></a>2개의 SRV 레코드 추가
<a name="BKMK_add_MX"> </a>

::: moniker range="o365-worldwide"

DNS 호스트의 웹 사이트에서 2개의 새 SRV 레코드를 일반적으로 한 번에 하나씩 만듭니다. 즉, 웹사이트에서 첫 번째 SRV 레코드를 추가한 후 다른 SRV 레코드를 만들도록 선택하십시오.
  
1. 각각의 새 레코드의 상자에서 다음 값을 입력하거나 복사하여 붙여넣습니다. **(DNS 호스트에 이러한 필드가 모두 별도 필드로 포함되어 있지 않을 때 SRV 레코드를 만들려면 아래 참고 사항을 참조하십시오.)**
    
    ||||||||||
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |**레코드 종류** <br/> |**Name(이름)** <br/> |**Target(대상)** <br/> |**Protocol(프로토콜)** <br/> |**Service(서비스)** <br/> |**Priority(우선 순위)** <br/> |**Weight(가중치)** <br/> |**Port(포트)** <br/> |**TTL** <br/> |
    |SRV (Service)(SRV(서비스))  <br/> |@  <br/> (또는 @을 허용하지 않는 경우 비워 둡니다.)  <br/> |sipdir.online.lync.com  <br/> |_tls  <br/> |_sip  <br/> |100  <br/> |1  <br/> |443  <br/> |1시간  <br/> |
    |SRV (Service)(SRV(서비스))  <br/> |@  <br/> (또는 @을 허용하지 않는 경우 비워 둡니다.)  <br/> |sipfed.online.lync.com  <br/> |_tcp  <br/> |_sipfederationtls  <br/> |100  <br/> |1  <br/> |5061  <br/> |1시간  <br/> |
   
    > [!NOTE]
    >  **이름**의 경우 : DNS 호스트가 이를 **@** 로 설정할 수 없는 경우 비워 두십시오. DNS 호스트에 서비스 및 프로토콜 값에 대한 별도의 필드가 있는 경우*에만* 이 방법을 사용하십시오. 그렇지 않으면 아래의 서비스 및 프로토콜 정보를 참조하십시오. 
    > 
    >  **서비스** 및 **프로토콜**의 경우 : DNS 호스트가 SRV 레코드에 이러한 필드를 제공하지 않으면 **서비스** 및 **프로토콜**을 지정해야 합니다. 값을 레코드의 **이름** 값으로 사용하십시오. (참고 : DNS 호스트에 따라 **이름** 필드는 **호스트**, **호스트 이름** 또는 **하위 도메인**과 같은 다른 이름으로 불릴 수 있습니다.) 결합된 값을 설정하려면 값을 점으로 구분하여 단일 문자열을 만듭니다.  예: **이름**: _sip._tls 
    > 
    >  **우선 순위**, **무게** 및 **포트**의 경우 : DNS 호스트가 SRV 레코드에 이러한 필드를 제공하지 않는 경우 이를 레코드의 **대상** 값으로 지정해야합니다. (참고: DNS 호스트에 따라 **대상** 필드는 **콘텐츠**, **IP 주소** 또는 **대상 호스트**.) 결합된 값을 설정하려면 값을 공백으로 구분하고 점으로 끝나는 단일 문자열을 만듭니다. 값은 우선 순위, 무게, 포트, 대상 순서로 포함되어야 합니다. 예: **대상**: 100 1 443 sipdir.online.lync.com. 
    > 
    >  **우선 순위**, **무게** 및 **포트**에 대한 변형: 일부 DNS 호스트는 필수 필드 중 일부를 개별적으로 제공합니다. 이러한 DNS 호스트 사이트의 경우 레코드의 **대상** 값에 대해 개별적으로 표시되지 않는 값을 결합된 문자열로 지정하십시오. (참고: DNS 호스트에 따라 **대상** 필드는 **콘텐츠**, **IP 주소** 또는 **대상 호스트**.) 결합된 값을 설정하려면 값을 공백으로 구분하여 개별적으로 표시되지 않은 필드에 대해 단일 문자열을 만듭니다. 값은 *순서*로 포함되어야 하 우선 순위, 가중치, 포트, 대상과 같이 별도의 필드를 사용할 수있는 값은 제외하십시오. 예를 들어 우선 순위에 대한 별도의 필드가 있는 경우에는 가중치, 포트, 대상 값만 포함합니다(**대상**: 1 443 sipdir.online.lync.com). 
    > 
    > For **TTL**: Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc. 
  
2. 모두 마쳤으면 레코드를 저장합니다.
    
    > [!NOTE]
    >  일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 
  
::: moniker-end


::: moniker range="o365-germany"

DNS 호스트의 웹 사이트에서 2개의 새 SRV 레코드를 일반적으로 한 번에 하나씩 만듭니다. 즉, 웹사이트에서 첫 번째 SRV 레코드를 추가한 후 다른 SRV 레코드를 만들도록 선택하십시오.
  
1. 각각의 새 레코드의 상자에서 다음 값을 입력하거나 복사하여 붙여넣습니다. **(DNS 호스트에 이러한 필드가 모두 별도 필드로 포함되어 있지 않을 때 SRV 레코드를 만들려면 아래 참고 사항을 참조하십시오.)**
    
    ||||||||||
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |**레코드 종류** <br/> |**Name(이름)** <br/> |**Target(대상)** <br/> |**Protocol(프로토콜)** <br/> |**Service(서비스)** <br/> |**Priority(우선 순위)** <br/> |**Weight(가중치)** <br/> |**Port(포트)** <br/> |**TTL** <br/> |
    |SRV (Service)(SRV(서비스))  <br/> |@  <br/> (또는 @을 허용하지 않는 경우 비워 둡니다.)  <br/> |sipdir.online.lync.de  <br/> |_tls  <br/> |_sip  <br/> |100  <br/> |1  <br/> |443  <br/> |1시간  <br/> |
    |SRV (Service)(SRV(서비스))  <br/> |@  <br/> (또는 @을 허용하지 않는 경우 비워 둡니다.)  <br/> |sipfed.online.lync.de  <br/> |_tcp  <br/> |_sipfederationtls  <br/> |100  <br/> |1  <br/> |5061  <br/> |1시간  <br/> |
   
    > [!NOTE]
    >  **이름**의 경우 : DNS 호스트가 이를 **@** 로 설정할 수 없는 경우 비워 두십시오. DNS 호스트에 서비스 및 프로토콜 값에 대한 별도의 필드가 있는 경우*에만* 이 방법을 사용하십시오. 그렇지 않으면 아래의 서비스 및 프로토콜 정보를 참조하십시오. 
    > 
    >  **서비스** 및 **프로토콜**의 경우 : DNS 호스트가 SRV 레코드에 이러한 필드를 제공하지 않으면 **서비스** 및 **프로토콜**을 지정해야 합니다. 값을 레코드의 **이름** 값으로 사용하십시오. (참고 : DNS 호스트에 따라 **이름** 필드는 **호스트**, **호스트 이름** 또는 **하위 도메인**과 같은 다른 이름으로 불릴 수 있습니다.) 결합된 값을 설정하려면 값을 점으로 구분하여 단일 문자열을 만듭니다. > 예: **이름**: _sip._tls 
    > 
    >  **우선 순위**, **무게** 및 **포트**의 경우 : DNS 호스트가 SRV 레코드에 이러한 필드를 제공하지 않는 경우 이를 레코드의 **대상** 값으로 지정해야합니다. (참고: DNS 호스트에 따라 **대상** 필드는 **콘텐츠**, **IP 주소** 또는 **대상 호스트**.) 결합된 값을 설정하려면 값을 공백으로 구분하고 점으로 끝나는 단일 문자열을 만듭니다. 값은 우선 순위, 무게, 포트, 대상 순서로 포함되어야 합니다. > 예: **대상**: 100 1 443 sipdir.online.lync.de 
    > 
    >  **우선 순위**, **무게** 및 **포트**에 대한 변형: 일부 DNS 호스트는 필수 필드 중 일부를 개별적으로 제공합니다. 이러한 DNS 호스트 사이트의 경우 레코드의 **대상** 값에 대해 개별적으로 표시되지 않는 값을 결합된 문자열로 지정하십시오. (참고: DNS 호스트에 따라 **대상** 필드는 **콘텐츠**, **IP 주소** 또는 **대상 호스트**.) 결합된 값을 설정하려면 값을 공백으로 구분하여 개별적으로 표시되지 않은 필드에 대해 단일 문자열을 만듭니다. 값은 *순서*로 포함되어야 하 우선 순위, 가중치, 포트, 대상과 같이 별도의 필드를 사용할 수있는 값은 제외하십시오. > 예를 들어 우선 순위에 대한 별도의 필드가 있는 경우에는 가중치, 포트, 대상 값만 포함합니다(**대상**: 1 443 sipdir.online.lync.de). 
    > 
    >  For **TTL**: Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc. 
  
2. 모두 마쳤으면 레코드를 저장합니다.
    
    > [!NOTE]
    >  일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 
  
::: moniker-end


::: moniker range="o365-21vianet"

DNS 호스트의 웹 사이트에서 2개의 새 SRV 레코드를 일반적으로 한 번에 하나씩 만듭니다. 즉, 웹사이트에서 첫 번째 SRV 레코드를 추가한 후 다른 SRV 레코드를 만들도록 선택하십시오.
  
1. 각각의 새 레코드의 상자에서 다음 값을 입력하거나 복사하여 붙여넣습니다. **(DNS 호스트에 이러한 필드가 모두 별도 필드로 포함되어 있지 않을 때 SRV 레코드를 만들려면 아래 참고 사항을 참조하십시오.)**
    
    ||||||||||
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |**레코드 종류** <br/> |**Name(이름)** <br/> |**Target(대상)** <br/> |**Protocol(프로토콜)** <br/> |**Service(서비스)** <br/> |**Priority(우선 순위)** <br/> |**Weight(가중치)** <br/> |**Port(포트)** <br/> |**TTL** <br/> |
    |SRV (Service)(SRV(서비스))  <br/> |@  <br/> (또는 @을 허용하지 않는 경우 비워 둡니다.)  <br/> |webdir.online.partner.lync.cn  <br/> |_tls  <br/> |_sip  <br/> |100  <br/> |1  <br/> |443  <br/> |1시간  <br/> |
    |SRV (Service)(SRV(서비스))  <br/> |@  <br/> (또는 @을 허용하지 않는 경우 비워 둡니다.)  <br/> |sipfed.online.partner.lync.cn  <br/> |_tcp  <br/> |_sipfederationtls  <br/> |100  <br/> |1  <br/> |5061  <br/> |1시간  <br/> |
   
    > [!NOTE]
    >  **이름**의 경우 : DNS 호스트가 이를 **@** 로 설정할 수 없는 경우 비워 두십시오. DNS 호스트에 서비스 및 프로토콜 값에 대한 별도의 필드가 있는 경우*에만* 이 방법을 사용하십시오. 그렇지 않으면 아래의 서비스 및 프로토콜 정보를 참조하십시오. 
    > 
    >  **서비스** 및 **프로토콜**의 경우 : DNS 호스트가 SRV 레코드에 이러한 필드를 제공하지 않으면 **서비스** 및 **프로토콜**을 지정해야 합니다. 값을 레코드의 **이름** 값으로 사용하십시오. (참고 : DNS 호스트에 따라 **이름** 필드는 **호스트**, **호스트 이름** 또는 **하위 도메인**과 같은 다른 이름으로 불릴 수 있습니다.) 결합된 값을 설정하려면 값을 점으로 구분하여 단일 문자열을 만듭니다. > 예: **이름**: _sip._tls 
    > 
    >  **우선 순위**, **무게** 및 **포트**의 경우 : DNS 호스트가 SRV 레코드에 이러한 필드를 제공하지 않는 경우 이를 레코드의 **대상** 값으로 지정해야합니다. (참고: DNS 호스트에 따라 **대상** 필드는 **콘텐츠**, **IP 주소** 또는 **대상 호스트**.) 결합된 값을 설정하려면 값을 공백으로 구분하고 점으로 끝나는 단일 문자열을 만듭니다. 값은 우선 순위, 무게, 포트, 대상 순서로 포함되어야 합니다. > 예: **대상** : 100 1 443 sipdir.online.partner.lync.cn. 
    > 
    >  **우선 순위**, **무게** 및 **포트**에 대한 변형: 일부 DNS 호스트는 필수 필드 중 일부를 개별적으로 제공합니다. 이러한 DNS 호스트 사이트의 경우 레코드의 **대상** 값에 대해 개별적으로 표시되지 않는 값을 결합된 문자열로 지정하십시오. (참고: DNS 호스트에 따라 **대상** 필드는 **콘텐츠**, **IP 주소** 또는 **대상 호스트**.) 결합된 값을 설정하려면 값을 공백으로 구분하여 개별적으로 표시되지 않은 필드에 대해 단일 문자열을 만듭니다. 값은 *순서*로 포함되어야 하 우선 순위, 가중치, 포트, 대상과 같이 별도의 필드를 사용할 수있는 값은 제외하십시오. > 예를 들어, 우선 순위에 별도의 필드가있는 경우 가중치, 포트 및 대상 값만 연결하십시오 : **대상** : 1 443 sipdir.online.partner.lync.cn 
    > 
    >  For **TTL**: Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc. 
  
2. 모두 마쳤으면 레코드를 저장합니다.
    
    > [!NOTE]
    >  일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 
  
::: moniker-end

## <a name="more-about-updating-dns-records"></a>DNS 레코드 업데이트에 대한 자세한 정보
<a name="BKMK_MoreAbout"> </a>

 **도메인의 DNS 호스트에서 DNS 레코드를 업데이트하는 방법을 알고 있는 경우**, Microsoft 365 DNS 값을 사용하여 도메인의 DNS 호스트에서 레코드를 편집(예 : MX 레코드 또는 SPF 레코드 설정)하십시오. [다음 단계](../get-help-with-domains/information-for-dns-records.md)에서 사용할 특정 값을 찾거나 단계별로 도메인 설정 마법사에서 해당 값을 보십시오.
  
 **필요한 DNS 레코드를 추가하는 방법을 알아내는 데 도움이 필요한 경우**[ 도메인 설정 (호스트 별 지침 ](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions?view=o365-worldwide), [ Microsoft 365 DNS 레코드를 만드는 데 필요한 정보 수집 ](../get-help-with-domains/information-for-dns-records.md)를 먼저 참조합니다. 그런 다음 이 항목의 일반 단계를 사용하여 도메인의 DNS 레코드를 설정하여 전자 메일과 같은 Microsoft 365 서비스에서 도메인을 사용할 수 있도록 합니다.
  
 **사용자 지정 도메인에 사용하는 웹 사이트가 없는 경우**, 모든 설정을 직접 수행하는 대신 Microsoft 365에서 도메인의 DNS 레코드를 설정하고 관리할 수 있습니다. Microsoft 365에서 [사용자 지정 도메인의 DNS 레코드를 설정하고 관리하기 위한 두 가지 옵션](https://support.office.com/article/5980474a-097f-4f21-a864-21245314957f.aspx)에 대해 알아보세요. 
  

