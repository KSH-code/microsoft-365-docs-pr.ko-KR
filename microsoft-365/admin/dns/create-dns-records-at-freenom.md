---
title: Freenom에서 Microsoft용 DNS 레코드 만들기
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
ms.assetid: d8ff45a2-19e3-413d-aa64-a9982bd6633c
description: Microsoft용 Freenom에서 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대한 DNS 레코드를 설정하는 방법을 배워야 합니다.
ms.openlocfilehash: b958a69d1dad9a0b56cf954d12cd42e40d6d4fea
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49657878"
---
# <a name="create-dns-records-at-freenom-for-microsoft"></a>Freenom에서 Microsoft용 DNS 레코드 만들기

원하는 정보를 찾지 못하면 도메인 [FAQ를](../setup/domains-faq.yml) 확인 합니다. 
  
> [!CAUTION]
> Freenom 웹 사이트는 SRV 레코드를 지원하지 않습니다. 즉, 여러 비즈니스용 Skype Online 및 Outlook Web App 기능이 작동하지 않습니다. 어떤 Microsoft 요금제에 사용하든 서비스 제한이 매우 크며 다른 DNS 호스팅 공급자로 전환할 수 있습니다. 
  
서비스 제한에도 불구하고 Freenom에서 자체 Microsoft DNS 레코드를 관리하기로 선택한 경우 이 문서의 단계에 따라 도메인을 확인하고 전자 메일 및 기타 서비스에 대한 DNS 레코드를 설정하세요.
  
  
> [!NOTE]
> 일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 
  
## <a name="add-a-txt-record-for-verification"></a>확인을 위해 TXT 레코드 추가
<a name="bkmk_txt"> </a>

Microsoft에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft에 도메인을 소유하고 있음을 증명할 수 있습니다.
  
> [!NOTE]
> 이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다. 
  
1. 시작하려면 이 링크를 사용하여 Freenom의 도메인 [페이지로 이동합니다.](https://my.freenom.com/) You'll be prompted to log in.
    
    ![Freenom 로그인](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. 서비스를 **선택하고** 내 **도메인을 선택합니다.**
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. 편집할 도메인의 경우 도메인 **관리(Manage Domain)를 선택합니다.**
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. **Freenom DNS 관리 선택.**
    
    ![Freenom Manage Freenom DNS](../../media/9854a511-27e3-4658-8903-34b3d425096d.png)
  
5. 레코드 **추가의** 종류 **열에서** 메뉴에서 **TXT를** 선택합니다. 
    
    ![Freenom Add Record type TXT](../../media/7f0e85e7-844f-4962-815e-5d80d9e6efa0.png)
  
6. 새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다. 
    
    |**이름**|**Type(종류)**|**TTL**|**Target(대상)**|
    |:-----|:-----|:-----|:-----|
    |(공백으로 둠)  <br/> |TXT  <br/> |3600(초)  <br/> |MS=msXXXXXXXXX  <br/> **참고:** 이 값은 예시입니다. 여기에는 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.           [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![확인을 위한 Freenom TXT 값](../../media/650098df-b3aa-47e5-9763-7fde24e34c3f.png)
  
7. 변경 **내용 저장을 선택합니다.**
    
    ![Freenom TXT 레코드 변경 내용 저장](../../media/b1a63f9a-4578-491a-9554-c40f73b37e09.png)
  
8. 방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.
    
이제 도메인 등록 기관에 레코드가 추가되었습니다. Microsoft로 돌아가서 레코드를 요청합니다.
  
Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.
  
1. Microsoft 관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동합니다.

    
2. **도메인** 페이지에서 확인 중인 도메인을 선택합니다. 
    
    
  
3. **설정** 페이지에서 **설정 시작** 을 선택합니다.
    
    
  
4. **도메인 확인** 페이지에서 **확인** 을 선택합니다.
    
    
  
> [!NOTE]
>  일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드 추가하기
<a name="bkmk_mx"> </a>

1. 시작하려면 이 링크를 사용하여 Freenom의 도메인 [페이지로 이동합니다.](https://my.freenom.com/) You'll be prompted to log in.
    
    ![Freenom 로그인](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. 서비스를 **선택하고** 내 **도메인을 선택합니다.**
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. 편집할 도메인의 경우 도메인 **관리(Manage Domain)를 선택합니다.**
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. 도메인에 대한 이름을 기본 Freenom 이름 서버로 설정하십시오. 관리 **도구를 선택한** 다음 이름 **보호를 선택합니다.**
    
    ![Freenom Nameservers 설정](../../media/a6ae877a-c248-42b9-bae9-210a80cd01e7.png)
  
5. 기본 이름 **서비스 사용이 선택되어** 있는지 확인한 다음 이름 서비스 **변경을 선택합니다.**
    
    ![Freenom Change Nameservers](../../media/0ef90d84-c0a0-4ef9-9e4c-43ef0aac3a2e.png)
  
6. **Freenom DNS 관리 선택.**
    
    ![Freenom 선택 Freenom DNS 관리](../../media/f55a8053-2411-45da-a357-776c6699f721.png)
  
7. 레코드 **추가의** 종류 **열에서** 메뉴에서 **MX를** 선택합니다. 
    
    ![Freenom Add Record type MX](../../media/c728c6ee-786c-4f6a-8ad5-1d9914a5bfcf.png)
  
8. 새 레코드의 상자에서 다음 표에 있는 첫 번째 행의 값을 입력하거나 복사하여 붙여넣습니다. 
    
    |**이름**|**Type(종류)**|**TTL**|**Target(대상)**|**우선 순위**|
    |:-----|:-----|:-----|:-----|:-----|
    |(공백으로 둠)  <br/> |MX (Mail Exchanger)(MX(메일 교환기))  <br/> |3600(초)  <br/> |\<domain-key\>.mail.protection.outlook.com  <br/> **참고:** Microsoft  *\<domain-key\>*  계정에서 다운로드하세요.   [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)          |10   <br/> 우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)을 참조하세요. <br/> |
   
   ![Freenom MX 레코드](../../media/8896c4a9-b3dd-45ed-9916-f7da2715ba8c.png)
  
9. 변경 **내용 저장을 선택합니다.**
    
    ![Freenom MX 레코드 변경 내용 저장](../../media/7aa0a464-d136-417f-be40-48d3f728eeb7.png)
  
10. 다른 MX 레코드가 있는 경우 모두 삭제합니다. 각 레코드에 대해 삭제를 **선택합니다.** 이 항목을 실제로 제거하고 **싶나요?** 메시지가 나타나면 확인을 **선택합니다.**
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>Microsoft에 필요한 CNAME 레코드 추가하기
<a name="bkmk_cname"> </a>

1. 시작하려면 이 링크를 사용하여 Freenom의 도메인 [페이지로 이동합니다.](https://my.freenom.com/) You'll be prompted to log in.
    
    ![Freenom 로그인](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. 서비스를 **선택하고** 내 **도메인을 선택합니다.**
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. 편집할 도메인의 경우 도메인 **관리(Manage Domain)를 선택합니다.**
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. **Freenom DNS 관리 선택.**
    
    ![Freenom 선택 Freenom DNS 관리](../../media/5e7bc3a7-0d5e-431b-bb27-da3b0f316d01.png)
  
5. 레코드 **추가의** **종류** 열에서 메뉴에서 **CNAME을** 선택합니다. 
    
    ![Freenom Add Record type CNAME](../../media/9b204755-ca2a-46d2-bce2-030d82fd1f9e.png)
  
6. 첫 번째 CNAME 레코드를 만듭니다. 새 레코드의 상자에서 다음 표에 있는 첫 번째 행의 값을 입력하거나 복사하여 붙여넣습니다. 
    
    |**이름**|**Record type(레코드 종류)**|**TTL**|**Target(대상)**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |3600(초)  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |3600(초)  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |3600(초)  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |3600(초)  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |3600(초)  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![Freenom CNAME 값](../../media/752fc682-e3f2-4b9c-9253-bf1ba2d414e9.png)
  
7. 변경 **내용 저장을 선택합니다.**
    
    ![Freenom CNAME Save Changes](../../media/68103fd2-0f5f-4aac-a875-25157c6bbdd2.png)
  
8. 이전 단계를 반복하여 나머지 5개의 CNAME 레코드를 만드십시오. 
    
    각 레코드에 대해 위 표의 다음 행 값을 해당 레코드의 상자에 입력하거나 복사하여 붙여넣습니다.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가
<a name="bkmk_spf"> </a>

> [!IMPORTANT]
> 도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다. 도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다. 도메인에 이미 SPF 레코드가 있는 경우 Microsoft의 새 SPF 레코드를 만들지 마세요. 대신 두 값 집합을 모두 포함하는  *단일*  SPF 레코드가 있도록 현재 레코드에 필요한 Microsoft 값을 추가합니다. 

1. 시작하려면 이 링크를 사용하여 Freenom의 도메인 [페이지로 이동합니다.](https://my.freenom.com/) You'll be prompted to log in.
    
    ![Freenom 로그인](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. 서비스를 **선택하고** 내 **도메인을 선택합니다.**
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. 편집할 도메인의 경우 도메인 **관리(Manage Domain)를 선택합니다.**
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. **Freenom DNS 관리 선택.**
    
    ![Freenom 선택 Freenom DNS 관리](../../media/94809955-0315-409c-a15d-703a2fe4c4ed.png)
  
5. 레코드 **추가의** 종류 **열에서** 메뉴에서 **TXT를** 선택합니다. 
    
    ![Freenom Add Record type TXT](../../media/d8854285-c4ae-416c-a072-72a11ba1cd9a.png)
  
6. In the boxes for the new record, type or copy and paste the following values. 
    
    |**이름**|**Record type(레코드 종류)**|**TTL**|**Target(대상)**|
    |:-----|:-----|:-----|:-----|
    |(공백으로 둠)  <br/> |TXT  <br/> |3600(초)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/>**참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.           |
   
    ![SPF의 Freenom TXT 값](../../media/1b3b1199-9104-4ca1-acdb-786d139c21ac.png)
  
7. 변경 **내용 저장을 선택합니다.**
    
    ![SPF 저장 변경 내용에 대한 Freenom TXT 레코드](../../media/e2fc52b1-0dcb-4595-9a4c-fca5e2ef9f97.png)
  

