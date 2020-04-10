---
title: Wix for Office 365에서 DNS 레코드 만들기
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7173c635-58b3-400f-95e0-97abe915565e
description: 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 및 Office 365 용 Wix의 기타 서비스에 대 한 DNS 레코드를 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: 8487c49e989bf2db345ae9e6d0e2970c5eb40cb6
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211065"
---
# <a name="create-dns-records-at-wix-for-office-365"></a>Wix for Office 365에서 DNS 레코드 만들기

 원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.md)** 하세요. 
  
Wix가 DNS 호스팅 공급자 이면이 문서에 나와 있는 단계에 따라 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 등에 대 한 DNS 레코드를 설정 합니다.
  
다음은 추가할 기본 레코드입니다. 
  
- [확인을 위해 TXT 레코드를 추가](#add-a-txt-record-for-verification)합니다.
    
- [도메인에 대 한 전자 메일이 Office 365에 제공 되도록 MX 레코드를 추가](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)합니다.
    
- [Office 365에 필요한 다섯 개의 CNAME 레코드를 추가](#add-the-five-cname-records-that-are-required-for-office-365)합니다.
    
- [SPF에 대 한 TXT 레코드를 추가 하 여 전자 메일 스팸 방지](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [Office 365에 필요한 두 개의 SRV 레코드를 추가](#add-the-two-srv-records-that-are-required-for-office-365)합니다.
    
Wix에서 이러한 레코드를 추가 하 고 나면 도메인이 Office 365 서비스에서 작동 하도록 설정 됩니다.
  
> [!NOTE]
>  일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 
  
## <a name="add-a-txt-record-for-verification"></a>확인을 위해 TXT 레코드 추가
<a name="BKMK_txt"> </a>

Office 365에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Office 365에 도메인을 소유하고 있음을 증명할 수 있습니다.
  
> [!NOTE]
> 이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다. 
  
1. 시작 하려면 [이 링크](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)를 사용 하 여 Wix의 도메인 페이지로 이동 합니다. 먼저 로그인하라는 메시지가 표시됩니다.
    
2. **My Domains (내 도메인** ) 페이지의 **고급** 영역에서 **DNS 편집** 단추를 선택 합니다. 
    
3. DNS 편집기의 **TXT (텍스트)** 행에서 **다른** 열을 선택 합니다. 
    
4. In the boxes for the new record, type or copy and paste the values from the following table. 
    
||||
|:-----|:-----|:-----|
|**Host Name** <br/> |**TXT 값** <br/> |**TTL** <br/> |
|자동으로 채워짐  <br/> |MS=ms *XXXXXXXX*  <br/> **참고:** 이 값은 예시입니다. 여기에는 Office 365의 표에 있는 특정 **보낼 대상 또는 지점** 값을 사용합니다.  [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)|1 Hour <br/> |          |
   
5. DNS 편집기 위쪽에 있는 **Dns 저장** 단추를 선택 합니다. 
    
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
<a name="BKMK_mx"> </a>

1. 시작 하려면 [이 링크](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)를 사용 하 여 Wix의 도메인 페이지로 이동 합니다. 먼저 로그인하라는 메시지가 표시됩니다.
    
2. **My Domains (내 도메인** ) 페이지의 **사서함** 영역에서 **MX 레코드 구성** 링크를 선택 합니다. 
    
3. **전자 메일 공급자** 드롭다운 목록에서 **기타** 를 선택 합니다. 
    
4. **+ 다른 추가**를 선택 합니다.
    
5. 새 레코드의 상자에서 다음 표의 값을 입력 하거나 복사 하 여 붙여넣습니다.
    
|**Host Name**|**연결 대상**|**Priority(우선 순위)**|**TTL**|
|:-----|:-----|:-----|:-----|
|자동으로 채워짐 <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **참고:** Office 365 계정에서 * \<도메인\> 키* 를 가져옵니다.   [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md) |개  <br/> 우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://support.office.com/article/What-is-MX-priority-2784cc4d-95be-443d-b5f7-bb5dd867ba83)을 참조하세요. | 1 Hour|
   
6. 다른 MX 레코드가 나열 되어 있는 경우 각 레코드를 삭제 합니다. 
    
7. **확인**을 선택합니다.
    
8. 확인 대화 상자에서 **확인**을 선택 합니다.
    
## <a name="add-the-five-cname-records-that-are-required-for-office-365"></a>Office 365에 필요한 다섯 개의 CNAME 레코드를 추가 합니다.
<a name="BKMK_cname"> </a>

1. 시작 하려면 [이 링크](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)를 사용 하 여 Wix의 도메인 페이지로 이동 합니다. You'll be prompted to login first.
    
2. **My Domains (내 도메인** ) 페이지의 **고급** 영역에서 **DNS 편집** 단추를 선택 합니다. 
    
3. 각 CNAME 레코드에 대 한 DNS 편집기의 **cname (별칭)** 행에서 다른 열로 **추가** 를 선택 합니다. 
    
4. 새 레코드의 상자에서 다음 표의 값을 입력 하거나 복사 하 여 붙여넣습니다.
    
|**Host Name**|**Points to(연결 대상)**|**TTL**|
|:-----|:-----|:-----|
|autodiscover  <br/> |autodiscover.outlook.com  <br/> |1 Hour  <br/> |
|sip  <br/> |sipdir.online.lync.com  <br/> |1 Hour <br/> |
|lyncdiscover  <br/> |webdir.online.lync.com   <br/> |1 Hour  <br/> |
|enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |1시간 <br/> |
|enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |1 Hour  <br/> |
   
5. DNS 편집기 위쪽에 있는 **Dns 저장** 단추를 선택 합니다. 
    
6. 방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가
<a name="BKMK_spf"> </a>

> [!IMPORTANT]
> 도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다. 도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.  
  
1. 시작 하려면 [이 링크](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)를 사용 하 여 Wix의 도메인 페이지로 이동 합니다. 먼저 로그인하라는 메시지가 표시됩니다.
    
2. **My Domains (내 도메인** ) 페이지의 **고급** 영역에서 **DNS 편집** 단추를 선택 합니다. 
    
3. DNS 편집기의 **TXT (텍스트)** 행에서 **다른** 열을 선택 합니다. 
    
4. 새 레코드의 상자에서 다음 표의 값을 입력 하거나 복사 하 여 붙여넣습니다.
    
|**Host Name**|**TXT 값**|**TTL**|
|:-----|:-----|:-----|
|[이 값을 비워 둠]  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.<br/> |TXT  <br/> | 1 Hour |
   
5. DNS 편집기 위쪽에 있는 **Dns 저장** 단추를 선택 합니다. 
    
6. 방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.
    
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Office 365에 필요한 2개의 SRV 레코드 추가
<a name="BKMK_srv"> </a>

1. 시작 하려면 [이 링크](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)를 사용 하 여 Wix의 도메인 페이지로 이동 합니다. 먼저 로그인하라는 메시지가 표시됩니다.
    
2. **My Domains (내 도메인** ) 페이지의 **고급** 영역에서 **DNS 편집** 단추를 선택 합니다. 
    
3. DNS 편집기의 **SRV** 행에서 **다른 추가** 를 선택 합니다. 
    
4. 새 레코드의 상자에서 다음 표의 값을 입력 하거나 복사 하 여 붙여넣습니다.
    
|**서비스**|**프로토콜**|**이름**|**Weight(가중치)**|**Port(포트)**|**대상**|**Priority(우선 순위)**|**TTL**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|sip  |tls  |자동으로 채워짐 |1   |443   |sipdir.online.lync.com |100 |1 Hour |
|sipfed.online.lync.com>|tcp |자동으로 채워짐|1  |5061 |sipfed.online.lync.com|100 | 1 Hour |
   
5. DNS 편집기 위쪽에 있는 **Dns 저장** 단추를 선택 합니다. 
    
6. 방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.
    
> [!NOTE]
>  일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 
  

