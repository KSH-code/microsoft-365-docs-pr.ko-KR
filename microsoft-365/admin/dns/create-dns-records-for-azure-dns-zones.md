---
title: Azure DNS 영역에 대 한 DNS 레코드 만들기
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
ms.assetid: fbcef2d7-ebaf-40d0-ba1f-cdaeff9f50ef
description: 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 및 Office 365의 Azure DNS 영역에 있는 다른 서비스에 대 한 DNS 레코드를 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: 30e54da8ffd51165b1cc0d2eb82d9d02eefdaf4d
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2020
ms.locfileid: "42362743"
---
# <a name="create-dns-records-for-azure-dns-zones"></a>Azure DNS 영역에 대 한 DNS 레코드 만들기

 원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.md)** 하세요. 
  
Azure가 DNS 호스팅 공급자 이면이 문서에 나와 있는 단계에 따라 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 등에 대 한 DNS 레코드를 설정 합니다.
  
다음은 추가할 기본 레코드입니다. 
  
- [도메인의 NS(이름 서버) 레코드 변경](#change-your-domains-nameserver-ns-records)
    
- [확인을 위해 TXT 레코드 추가](#add-a-txt-record-for-verification)

- [사용자 도메인의 전자 메일이 Office 365로 전송되도록 MX 레코드 추가](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [Office 365에 필요한 4 개의 CNAME 레코드 추가](#add-the-four-cname-records-that-are-required-for-office-365)
    
- [전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [Office 365에 필요한 2개의 SRV 레코드 추가](#add-the-two-srv-records-that-are-required-for-office-365)
    
Azure에서 이러한 레코드를 추가 하 고 나면 도메인이 Office 365 서비스에서 작동 하도록 설정 됩니다.
  
> [!NOTE]
> 일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 
  
## <a name="change-your-domains-nameserver-ns-records"></a>도메인의 NS(이름 서버) 레코드 변경
<a name="BKMK_NS"> </a>

> [!IMPORTANT]
> 이 절차는 도메인을 구입하고 등록한 도메인 등록 기관에서 수행해야 합니다. 
  
Azure에 등록할 때 DNS 영역 내에 리소스 그룹을 만든 다음 해당 리소스 그룹에 도메인 이름을 할당 합니다. 해당 도메인 이름은 외부 도메인 등록자에 등록 됩니다. Azure는 도메인 등록 서비스를 제공 하지 않습니다.
  
Office 365에서 도메인에 대 한 DNS 레코드를 확인 하 고 만들려면 먼저 도메인 등록 기관에서 이름 서버를 변경 하 여 리소스 그룹에 할당 된 Azure 이름 서버을 사용 하도록 해야 합니다.
  
도메인 등록 기관 웹 사이트에서 도메인 이름 서버를 직접 변경하려면 다음 단계를 따릅니다.
  
1. 도메인 등록 기관의 웹 사이트에서 도메인의 이름 서버를 편집할 수 있는 영역을 찾습니다.
    
2. 다음 표의 값을 사용 하 여 두 개의 이름 서버 레코드를 만들거나 기존 이름 서버 레코드를 해당 값과 일치 하도록 편집 합니다. Azure 할당 된 이름 서버의 예는 다음과 같습니다.
    


**첫 번째 이름 서버:** Azure에서 할당 된 이름 서버 값을 사용 합니다.  
**두 번째** 이름 서버: Azure에서 할당 된 이름 서버 값을 사용 합니다.  

![Redelegate-1-1](../../media/3e4805ea-608a-4df9-8f68-1fbf70d13d08.png)
  
> [!TIP]
> You should use at least two name server records. 도메인 등록 기관의 웹 사이트에 다른 이름 서버가 나열 된 경우 해당 서버를 삭제 해야 합니다. 
  
3. 변경 내용을 저장합니다.
    
> [!NOTE]
> 이름 서버 레코드 업데이트가 인터넷의 DNS 시스템 전체에 업데이트되기까지 몇 시간이 걸릴 수 있습니다. 그 후에는 Office 365 전자 메일 및 기타 서비스가 모두 사용자의 도메인을 사용하도록 설정됩니다. 
  
## <a name="add-a-txt-record-for-verification"></a>확인을 위해 TXT 레코드 추가
<a name="BKMK_verify"> </a>

Office 365에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Office 365에 도메인을 소유하고 있음을 증명할 수 있습니다.
  
> [!NOTE]
> 이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다. 
  
1. 시작 하려면 [이 링크](https://portal.azure.com )를 사용 하 여 Azure의 도메인 페이지로 이동 합니다. 먼저 로그인하라는 메시지가 표시됩니다.
    
    ![Azure-BP-구성-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. **대시보드** 페이지의 **검색 표시줄** 을 사용 하 여 **DNS 영역**을 입력 합니다. 결과 표시의 **서비스** 부분 아래에서 **DNS 영역** 을 선택 합니다. 리디렉션된 후에는 업데이트할 도메인을 선택 합니다.
    
    ![Azure-BP-구성-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. 도메인의 **설정** 페이지에 있는 **DNS 영역** 에서 **+ 레코드 집합**을 선택 합니다.
    
    ![Azure-BP-구성-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. **레코드 집합 추가** 영역의 새 레코드 집합에 대 한 상자에서 다음 표의 값을 선택 합니다. 
    
    (드롭다운 목록에서 **Type (종류** ) 및 **TTL 단위** 값을 선택 합니다.) 
    
    |**이름**|**종류**|**TTL**|**TTL 단위**|**값**|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |TXT  <br/> |개  <br/> |시간  <br/> |MS=ms *XXXXXXXX*  <br/> **참고:** 이 값은 예시입니다. 여기에는 Office 365의 표에 있는 특정 **보낼 대상 또는 지점** 값을 사용합니다.           [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Azure-BP-Verify-1-1](../../media/7d5a253c-e88f-4565-a00a-79bba52f9970.png)
  
5. **확인**을 선택합니다.
  
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

1. 시작 하려면 [이 링크](https://portal.azure.com )를 사용 하 여 Azure의 도메인 페이지로 이동 합니다. 먼저 로그인하라는 메시지가 표시됩니다.
    
    ![Azure-BP-구성-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. **대시보드** 페이지의 **모든 리소스** 영역에서 업데이트할 도메인을 선택 합니다. 
    
    ![Azure-BP-구성-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. 도메인의 **설정** 페이지에 있는 **DNS 영역** 에서 **+ 레코드 집합**을 선택 합니다.
    
    ![Azure-BP-구성-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. **레코드 집합 추가** 영역의 새 레코드 집합에 대 한 상자에서 다음 표의 값을 선택 합니다. 
    
    (드롭다운 목록에서 **Type (종류** ) 및 **TTL 단위** 값을 선택 합니다.) 
    
    |**이름**|**종류**|**TTL**|**TTL 단위**|**기본 설정**|**메일 교환**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |MX  <br/> |개  <br/> |시간  <br/> |10   <br/> 우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)을 참조하세요. <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **참고:** Office 365 계정에서 * \<도메인\> 키* 를 가져옵니다.   [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)  
   
    ![Azure-BP-구성-2-1](../../media/712c23ae-9d38-4af2-94e0-0704e70744fe.png)
  
5. **확인**을 선택합니다.
    
    ![Azure-BP-구성-2-2](../../media/2f24225f-69ac-41dc-91c5-93d327360f74.png)
  
6. **Mx 레코드** 구역에 다른 mx 레코드가 나열 되어 있으면 해당 레코드를 삭제 해야 합니다. 
    
    먼저 **DNS 영역** 에서 **MX 레코드 집합**을 선택 합니다.
    
    ![Azure-BP-구성-2-3](../../media/9890da61-6fcd-4c61-888e-ccbb84f80cd0.png)
  
    그런 다음 삭제 하려는 MX 레코드를 선택 합니다.
    
    ![Azure-BP-구성-2-4](../../media/afe54f12-66d2-4ff3-80e9-427448e4c32c.png)
  
7. 상황에 **맞는 메뉴 (...)** 를 선택한 다음 **제거**를 선택 합니다.
    
    ![Azure-BP-구성-2-5](../../media/25219e25-bc14-4bc7-84ed-ee65eb28a8ed.png)
  
8. **저장**을 선택합니다.
    
    ![Azure-BP-구성-2-6](../../media/c6133096-5e43-4637-9c01-b63ee4b03517.png)
  
## <a name="add-the-four-cname-records-that-are-required-for-office-365"></a>Office 365에 필요한 4 개의 CNAME 레코드 추가
<a name="BKMK_add_CNAME"> </a>

1. 시작 하려면 [이 링크](https://portal.azure.com )를 사용 하 여 Azure의 도메인 페이지로 이동 합니다. 먼저 로그인하라는 메시지가 표시됩니다.
    
    ![Azure-BP-구성-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. **대시보드** 페이지의 **모든 리소스** 영역에서 업데이트할 도메인을 선택 합니다. 
    
    ![Azure-BP-구성-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. 도메인의 **설정** 페이지에 있는 **DNS 영역** 에서 **+ 레코드 집합**을 선택 합니다.
    
    ![Azure-BP-구성-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. 4 개의 CNAME 레코드 중 처음 일부를 추가 합니다.
    
    **레코드 집합 추가** 영역의 새 레코드 집합 용 상자에 다음 표에 있는 첫 번째 행의 값을 입력 하거나 복사 하 여 붙여넣습니다. 
    
    (드롭다운 목록에서 **Type (종류** ) 및 **TTL 단위** 값을 선택 합니다.) 
    
    |**이름**|**종류**|**TTL**|**TTL 단위**|**별칭**|
    |:-----|:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |개  <br/> |시간  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |개  <br/> |시간  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |개  <br/> |시간  <br/> |webdir.online.lync.com  <br/> |
    
   
    ![Azure-BP-구성-3-1](../../media/a1c4d869-da97-43b3-952c-d513a20231dc.png)
  
5. **확인**을 선택합니다.
    
    ![Azure-BP-구성-3-2](../../media/b89b51da-1c07-43cf-9fab-75d2e5eb3544.png)
  
6. 나머지 3 개의 CNAME 레코드를 각각 추가 합니다.
    
    **DNS 영역** 영역에서 **+ 레코드 집합**을 선택 합니다. 그런 다음 빈 레코드 집합에서 표의 다음 행 값을 사용 하 여 레코드를 만들고 **확인** 을 선택 하 여 해당 레코드를 완료 합니다. 
    
    4 개의 CNAME 레코드를 모두 만들 때까지이 프로세스를 반복 합니다.
    
7.  반드시 MDM에 대 한 2 개의 CNAME 레코드를 추가 합니다.

> [!IMPORTANT]
> Office 365용 MDM (Mobile Device Management)이있는 경우 두 개의 추가 CNAME 레코드를 만들어야 합니다. 다른 4개의 CNAME 레코드를 만드는 데 사용한 절차를 따르되 다음 표의 값을 입력합니다. (MDM이 없는 경우에는이 단계를 건너뛰어도 됩니다.) 
  
|**이름**|**종류**|**TTL**|**TTL 단위**|**별칭**|
|:-----|:-----|:-----|:-----|:-----|
|enterpriseregistration  <br/> |CNAME  <br/> |개  <br/> |시간  <br/> |enterpriseregistration.windows.net  <br/> |
|enterpriseenrollment  <br/> |CNAME  <br/> |개  <br/> |시간  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다. 도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values. 
  
1. 시작 하려면 [이 링크](https://portal.azure.com )를 사용 하 여 Azure의 도메인 페이지로 이동 합니다. 먼저 로그인하라는 메시지가 표시됩니다.
    
    ![Azure-BP-구성-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. **대시보드** 페이지의 **모든 리소스** 영역에서 업데이트할 도메인을 선택 합니다. 
    
    ![Azure-BP-구성-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. **DNS 영역** 영역에서 **TXT 레코드 집합**을 선택 합니다.
    
    ![Azure-BP-구성-4-1](../../media/03095196-5010-4072-8503-79b812084dbf.png)
  
4. **레코드 집합 속성** 영역의 새 레코드 집합에 대 한 상자에서 다음 표의 값을 선택 합니다. 
    
    (드롭다운 목록에서 **Type (종류** ) 및 **TTL 단위** 값을 선택 합니다.) 
    
    |**이름**|**종류**|**TTL**|**TTL 단위**|**값**|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |TXT  <br/> |개  <br/> |시간  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **참고: ** 모든 간격이 올바르게 유지되도록 이 항목을 복사하여 붙여넣는 것이 좋습니다.           

    ![Azure-BP-구성-4-2](../../media/78e84c43-e0ce-433f-8e74-9157fb093cca.png)
  
5. **저장**을 선택합니다.
    
    ![Azure-BP-구성-4-3](../../media/d7421c7f-ea63-4e11-8595-a482b8c165e0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Office 365에 필요한 2개의 SRV 레코드 추가
<a name="BKMK_add_SRV"> </a>

1. 시작 하려면 [이 링크](https://portal.azure.com )를 사용 하 여 Azure의 도메인 페이지로 이동 합니다. 먼저 로그인하라는 메시지가 표시됩니다.
    
    ![Azure-BP-구성-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. **대시보드** 페이지의 **모든 리소스** 영역에서 업데이트할 도메인을 선택 합니다. 
    
    ![Azure-BP-구성-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. 도메인의 **설정** 페이지에 있는 **DNS 영역** 에서 **+ 레코드 집합**을 선택 합니다.
    
    ![Azure-BP-구성-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. 처음 2개의 SRV 레코드를 추가합니다.
    
    **레코드 집합 추가** 영역의 새 레코드 집합에 대 한 상자에서 다음 표의 첫 번째 행에 있는 값을 선택 합니다. 
    
    (드롭다운 목록에서 **Type (종류** ) 및 **TTL 단위** 값을 선택 합니다.) 
    
    |**이름**|**종류**|**TTL**|**TTL 단위**|**Priority(우선 순위)**|**Weight(가중치)**|**Port(포트)**|**대상**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip _tls  <br/> |SRV  <br/> |개  <br/> |시간  <br/> |100  <br/> |개  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls _tcp  <br/> |SRV  <br/> |개  <br/> |시간  <br/> |100  <br/> |개  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> 

    ![Azure-BP-구성-5-1](../../media/a436e0b4-8bb8-4a66-9c22-4e3b2dcf54ff.png)
  
5. **확인**을 선택합니다.
    
    ![Azure-BP-구성-5-2](../../media/a35b6c8a-d001-4b3c-8a67-96b4890e564c.png)
  
6. 다른 SRV 레코드를 추가합니다.
    
    새 레코드의 상자에서 표의 두 번째 행에 있는 값을 입력 하거나 복사 하 여 붙여넣습니다.
    
> [!NOTE]
> 일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 
  
