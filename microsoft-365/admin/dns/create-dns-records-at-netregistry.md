---
title: Netregistry에서 Microsoft용 DNS 레코드 만들기
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
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
- BEA160
ms.assetid: 48e09394-2287-4b3c-9853-21eadf61277e
description: Microsoft용 Netregistry에서 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대한 DNS 레코드를 설정하는 방법을 학습합니다.
ms.openlocfilehash: 857645c685cce946b39a7c3dcadb0a45b43686cf
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49657806"
---
# <a name="create-dns-records-at-netregistry-for-microsoft"></a>Netregistry에서 Microsoft용 DNS 레코드 만들기

원하는 정보를 찾지 못한 경우 [도메인 FAQ를 확인](../setup/domains-faq.yml)하세요. 
  
DNS 호스팅 공급자로 Netregistry를 사용하고 있는 경우 이 문서의 단계를 따라 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online에 대한 DNS 레코드를 설정하세요.
  
다음은 추가할 기본 레코드입니다.
  
- [확인을 위해 TXT 레코드 추가](#add-a-txt-record-for-verification)
    
- [사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드 추가하기](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)

- [Microsoft에 필요한 CNAME 레코드 추가하기](#add-the-cname-records-that-are-required-for-microsoft)
    
- [전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [Microsoft 필요한 2개의 SRV 레코드 추가하기](#add-the-two-srv-records-that-are-required-for-microsoft)
    
Netregistry에서 이러한 레코드를 추가하고 나면 도메인이 Microsoft 서비스에서 작동하게 설정됩니다.
  
  
> [!NOTE]
> 일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 
  
## <a name="add-a-txt-record-for-verification"></a>확인을 위해 TXT 레코드 추가
<a name="bkmk_txt"> </a>

Microsoft에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft에 도메인을 소유하고 있음을 증명할 수 있습니다.
  
> [!NOTE]
> 이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다. 
  
1. 시작하려면 이 링크를 사용하여 Netregistry의 도메인 [페이지로 이동합니다.](https://theconsole.netregistry.com.au/) You'll be prompted to log in.
    
    ![Netregistry_login](../../media/ed3c785f-01c3-49e7-affd-c04637c0ffe9.png)
  
2. 관리하려는 도메인 옆에서 관리 를 **선택합니다.**
    
    ![Netregistry_Manage](../../media/64ad542a-5ec4-4148-96f8-d6e163449352.png)
  
3. 영역 **관리자를 선택합니다.**
    
    ![Netregistry_selectZoneManager](../../media/e18c32f9-c1e7-4aa2-9aa6-8dc9c5ea44af.png)
  
4. 영역 **레코드 추가 목록에서** **TXT** 레코드를 선택한 다음 새 레코드 **만들기를 선택합니다.**
    
    ![Netregistry_TXT_select](../../media/eb1761e6-9deb-4631-8deb-bc5d09926722.png)
  
    > [!NOTE]
    > TXT 상자의 항목 앞과 뒤에서 인용 부호를 사용해야 합니다. 
  
    새 **TXT 레코드** 폼에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다. 
    
    |**이름**|**TTL(SEC)**|**TXT(주소 또는 값 포인트)**|
    |:-----|:-----|:-----|
    |(공백으로 둠)  <br/> |3600(초)  <br/> |"MS=msXXXXXXXXX"  <br/> **참고:** 이 값은 예시입니다. 여기에는 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다. [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)  |
       
    ![Netregistry_verificationTXTvalues](../../media/cfe8b05a-fa8b-4dba-9554-7a3466e6c012.png)
  
6. 레코드 **추가를 선택합니다.**
    
이제 도메인 등록 기관에 레코드가 추가되었습니다. Microsoft로 돌아가서 레코드를 요청합니다.
  
Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.
  
1. I관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인</a> 페이지로 이동하십시오.
    
2. **도메인** 페이지에서 확인 중인 도메인을 선택합니다. 
    
    
  
3. **설정** 페이지에서 **설정 시작** 을 선택합니다.
    
    
  
4. **도메인 확인** 페이지에서 **확인** 을 선택합니다.
    
    
  
> [!NOTE]
>  일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드 추가하기
<a name="bkmk_mx"> </a>

1. 시작하려면 이 링크를 사용하여 Netregistry의 도메인 [페이지로 이동합니다.](https://theconsole.netregistry.com.au/) You'll be prompted to log in.
    
    ![Netregistry_login](../../media/80277b0e-547e-4635-aa6a-5d8ebe3fba85.png)
  
2. 관리하려는 도메인 옆에서 관리 를 **선택합니다.**
    
    ![Netregistry_Manage](../../media/96e2c6e4-21fd-4405-a4fe-b1188400b985.png)
  
3. 영역 **관리자를 선택합니다.**
    
    ![Netregistry_selectZoneManager](../../media/914021f6-dff3-4640-84d6-b83cf8f61cf1.png)
  
4. 현재 **영역 레코드에서** 목록의 각 MX  레코드 옆에 있는 제거를 선택하여 기본 MX 레코드를 제거합니다. 
    
    ![Netregistry_MX_remove](../../media/494670a9-8b8d-46e5-8136-05e82212a115.png)
  
5. 영역 **레코드 추가 아래** 목록에서 **MX** 레코드를 선택한 다음 새 레코드 **만들기를 선택합니다.**
    
    ![Netregistry_MX_select](../../media/29b60eb9-6c40-490f-9669-e65b65962f37.png)
  
6. 새 **MX 레코드** 폼에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다. 
    
    |**이름**|**TTL(SEC)**|**Exchange(주소 또는 값 지점)**|**호스트가 정식으로 자격을 갖춘가요?**|**기본 설정(우선 순위)**|
    |:-----|:-----|:-----|:-----|:-----|
    |(공백으로 둠)  <br/> |3600(초)  <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **참고:** Microsoft  *\<domain-key\>*  계정에서 다운로드하세요.  [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)      |(확인란 선택)  <br/> |10    <br/> For more information about priority, see What is MX priority?  <br/> |
       
    ![Netregistry_MX_values](../../media/518b3da6-4055-4e2d-b5ce-44a0fee25419.png)
  
7. 레코드 **추가를 선택합니다.**
    
    ![Netregistry_MX_values_AddRecord](../../media/8194cb38-afa0-48ac-831c-fd34b6ad652e.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>Microsoft에 필요한 CNAME 레코드 추가하기
<a name="bkmk_cname"> </a>

1. 시작하려면 이 링크를 사용하여 Netregistry의 도메인 [페이지로 이동합니다.](https://theconsole.netregistry.com.au/) You'll be prompted to log in.
    
    ![Netregistry_login](../../media/cbf83dce-86d2-4008-9400-56def4b6fcd7.png)
  
2. 관리하려는 도메인 옆에서 관리 를 **선택합니다.**
    
    ![Netregistry_Manage](../../media/7bee4b0f-2c1d-43ca-b1bb-9b889ca0c5e4.png)
  
3. 영역 **관리자를 선택합니다.**
    
    ![Netregistry_selectZoneManager](../../media/58384add-0a9d-472b-a5d0-51ec8155fd41.png)
  
4. 영역 **레코드 추가 목록에서** **CNAME** 레코드를 선택한 다음 새 레코드 **만들기를 선택합니다.**
    
    ![Netregistry_CNAME_CreateNewRecord](../../media/7b4f133f-45da-48da-93c0-62f57c786165.png)
  
5. 새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.
    
    |**이름**|**Type(종류)**|**TTL**|**HOST(Points to or address value)**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |3600(초)  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |3600(초)  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |3600(초)  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |3600(초)  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |3600(초)  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
       
    ![Netregistry_CNAME_values](../../media/93c479f0-3ce2-491a-9113-6dde1cd7131b.png)
      
6. 레코드 **추가를 선택합니다.**
    
    ![Netregistry_CNAME_values_AddRecord](../../media/046c8c64-ea71-4530-9fc6-69f0c70993b6.png)
  
7. 이전 단계를 반복하여 나머지 5개의 CNAME 레코드를 만드십시오.
    
    각 레코드에 대해 위 표의 다음 행 값을 해당 레코드의 상자에 입력하거나 복사하여 붙여넣습니다.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가
<a name="bkmk_spf"> </a>

> [!IMPORTANT]
> 도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다. 도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다. 도메인에 이미 SPF 레코드가 있는 경우 Microsoft의 새 SPF 레코드를 만들지 마세요. 대신 두 값 집합을 모두 포함하는  *단일*  SPF 레코드가 있도록 현재 레코드에 필요한 Microsoft 값을 추가합니다.
  
1. 시작하려면 이 링크를 사용하여 Netregistry의 도메인 [페이지로 이동합니다.](https://theconsole.netregistry.com.au/) You'll be prompted to log in.
    
    ![Netregistry_login](../../media/a841f11f-1c0f-4926-acea-a2b8bb083984.png)
  
2. 관리하려는 도메인 옆에서 관리 를 **선택합니다.**
    
    ![Netregistry_Manage](../../media/4245bbbb-4e2d-49e7-a89c-679949aa3d18.png)
  
3. 영역 **관리자를 선택합니다.**
    
    ![Netregistry_selectZoneManager](../../media/372e5918-b6dc-4268-8f9a-0aa71d65deef.png)
  
4. 영역 **레코드 추가 목록에서** **TXT** 레코드를 선택한 다음 새 레코드 **만들기를 선택합니다.**
    
    ![Netregistry_TXT_select](../../media/a2930d03-853a-4f1e-9205-d00f25bed35f.png)
  
5. 새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다. 
    
    > [!NOTE]
    > TXT 상자의 항목 앞과 뒤에서 인용 부호를 사용해야 합니다. 
  
    |**이름**|**Type(종류)**|**TTL**|**TXT 데이터(대상)**|
    |:-----|:-----|:-----|:-----|
    |(공백으로 둠)  <br/> |TXT  <br/> |3600(초)  <br/> |"v=spf1 include:spf.protection.outlook.com -all"  <br/> **참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.           |
   
    ![Netregistry_SPF-TXTvalues](../../media/a369345a-d774-48bc-8160-b628ab8247f9.png)
  
6. 레코드 **추가를 선택합니다.**
    
    ![Netregistry_SPF-TXTvalues_AddRecord](../../media/063bfbaf-940a-489f-970f-29c026b4b312.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Microsoft 필요한 2개의 SRV 레코드 추가하기
<a name="bkmk_srv"> </a>

1. 시작하려면 이 링크를 사용하여 Netregistry의 도메인 [페이지로 이동합니다.](https://theconsole.netregistry.com.au/) You'll be prompted to log in.
    
    ![Netregistry_login](../../media/accf6584-e5f4-4d68-a641-0f8847f8370f.png)
  
2. 관리하려는 도메인 옆에서 관리 를 **선택합니다.**
    
    ![Netregistry_Manage](../../media/e0ddc79e-0123-4e24-8380-9645bdb41aac.png)
  
3. 영역 **관리자를 선택합니다.**
    
    ![Netregistry_selectZoneManager](../../media/f122888b-3cc5-40ec-adac-0ede04799d9a.png)
  
4. 영역 **레코드 추가 아래** 목록에서 **SRV** 레코드를 선택한 다음 새 레코드 **만들기를 선택합니다.**
    
    ![Netregistry_SRV_select](../../media/e5dab850-acd1-48b8-8b4a-e3b9777cf508.png)
  
5. 새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.
    
    > [!NOTE]
    > Name 필드는 서비스(예: _sip) 및 프로토콜(예: _tls)의 조합입니다. 
  
    |**유형**|**이름**|**TTL(SEC)**|**Priority(우선 순위)**|**Weight(가중치)**|**Port(포트)**|**대상**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV(서비스)  <br/> |_sip._tls  <br/> |3600(초)  <br/> |100  <br/> |1   <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |SRV(서비스)  <br/> |_sipfederationtls._tcp  <br/> |3600(초)  <br/> |100  <br/> |1   <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
       
    ![Netregistry_SRV_values](../../media/49292846-1598-4b8c-9940-db6e10675753.png)
  
6. 레코드 **추가를 선택합니다.**
    
    ![Netregistry_SRV_values_AddRecord](../../media/abc82061-939f-4757-87e4-0e8f9e43ebcb.png)
  
7. 이전 단계를 반복하여 다른 SRV 레코드를 만들 수 있습니다.
    
    위 표에 있는 두 번째 행의 값을 두 번째 레코드의 상자에 입력하거나 복사하여 붙여넣습니다.
    
> [!NOTE]
> 일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 
  

