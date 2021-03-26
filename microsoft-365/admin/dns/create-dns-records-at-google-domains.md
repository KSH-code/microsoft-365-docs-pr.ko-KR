---
title: Microsoft용 Google 도메인에서 DNS 레코드 만들기
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
ms.assetid: 0db29490-2612-48bc-9b77-1862e7a41a8c
description: Microsoft용 Google 도메인에서 도메인을 확인하고 전자 메일용 DNS 레코드를 설정하고, Lync 및 기타 서비스를 설정하는 법을 알아봅니다.
ms.openlocfilehash: 48e23c180533bab2a73e06dd4a45a9c4016680ae
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/26/2021
ms.locfileid: "51221958"
---
# <a name="create-dns-records-at-google-domains-for-microsoft"></a>Microsoft용 Google 도메인에서 DNS 레코드 만들기

 원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.yml)** 하세요. 
  
DNS 호스팅 공급자로 Google Domains를 사용하고 있는 경우, 이 문서에 나와 있는 단계를 따라 도메인을 확인하고 전자 메일, Lync 등에 대한 DNS 레코드를 설정합니다.
  
Google Domains에서 이러한 레코드를 추가하고 나면 도메인이 Microsoft 서비스에서 작동하도록 설정됩니다.
  

  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [Microsoft에서 도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요. 
  
## <a name="add-a-txt-record-for-verification"></a>확인을 위해 TXT 레코드 추가
<a name="BKMK_verify"> </a>

Microsoft에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft에 도메인을 소유하고 있음을 증명할 수 있습니다.
  
> [!NOTE]
> 이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다. 
  
1. 시작하려면 [이 링크](https://domains.google.com/registrar)를 사용하여 Google Domains의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다. 방법은 다음과 같습니다.
    
1. **로그인** 을 선택합니다.
    
2. 로그인 자격 증명을 입력하고 다시 **로그인** 를 선택 합니다.
    
2. **내 도메인** 페이지에서 Microsoft에 사용할 도메인을 찾고 옆에 있는 **관리** 링크를 선택 합니다. 왼쪽 탐색 창에서 **DNS** 를 선택합니다.
    
3. 
            **사용자 지정 리소스 레코드** 구역의 새 레코드 상자에 다음 표의 값을 입력하거나 복사하여 붙여넣습니다. 
    
    (아래로 스크롤해야 할 수 있습니다.)
    
    (드롭다운 목록에서 **Type(종류)** 값을 선택합니다.) 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**이름** <br/> |**Type(종류)** <br/> |**TTL** <br/> |**데이터** <br/> |
    |@  <br/> |TXT  <br/> |1H  <br/> |MS=ms *XXXXXXXX*  <br/> **참고:** 이 값은 예시입니다. 여기에는 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다. [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)          |
   
4. **추가** 를 선택합니다.
    
5. 방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.
    
이제 도메인 등록 기관에 레코드가 추가되었습니다. Microsoft로 돌아가서 레코드를 요청합니다.
  
Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.
  
1. Microsoft 관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동합니다.

    
2. **도메인** 페이지에서 확인 중인 도메인을 선택합니다. 
    
3. **설정** 페이지에서 **설정 시작** 을 선택합니다.
    
4. **도메인 확인** 페이지에서 **확인** 을 선택합니다.
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요. 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드 추가하기
<a name="BKMK_add_MX"> </a>

1. 시작하려면 [이 링크](https://domains.google.com/registrar)를 사용하여 Google Domains의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다. 방법은 다음과 같습니다.
    
2. **로그인** 을 선택합니다.
    
3. 로그인 자격 증명을 입력하고 다시 **로그인** 를 선택 합니다.
4. **도메인** 페이지의 **도메인** 구역에서 편집할 도메인에 대해 **DNS 구성** 을 선택합니다.
    
    > [!IMPORTANT]
    > G Suite 전자 메일 계정이 있는 경우 먼저 해당 계정과 연결된 MX 레코드를 삭제해야 합니다. G Suite MX 레코드는 Microsoft에 필요한 MX 레코드를 비롯한 다른 모든 MX 레코드를 추가하지 못하게 합니다. G Suite 레코드를 삭제한다고 해서 G Suite 계정이 삭제되지는 않습니다. G Suite MX 레코드를 삭제하려면 다음 단계를 사용하세요. 
  
5. 먼저 **G Suite** 영역의 **가상 레코드** 섹션에서 **삭제** 를 선택합니다.
    
    (아래로 스크롤 해야 합니다.)
    
    ![가상 레코드 구역에서 삭제를 선택합니다.](../../media/bd276b5d-5667-4bb1-a233-2dc5194e7ace.png)
  
6. **삭제** 를 선택합니다.
    
    ![삭제를 선택합니다.](../../media/4413a45a-5b82-4ec6-82c6-0091f5be9696.png)
  
7. 
            **사용자 지정 리소스 레코드** 구역의 새 레코드 상자에 다음 표의 값을 입력하거나 복사하여 붙여넣습니다. 
    
    (아래로 스크롤해야 할 수 있습니다.)
    
    (드롭다운 목록에서 **Type(종류)** 값을 선택합니다.) 
    
    |**이름**|**Type(종류)**|**TTL**|**데이터**|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |MX  <br/> |1H  <br/> |0  *\<domain-key\>*  .mail.protection.outlook.com.  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> **0** 은 MX 우선 순위 값입니다. 이 값을 MX 값 시작 부분에 추가하고 나머지 값과 공백으로 구분합니다.  <br/> **참고:** Microsoft 계정에서 \<*domain-key*\>을(를) 받으세요.  [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)          우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](../setup/domains-faq.yml)을 참조하세요. <br/> |
   
    ![사용자 지정 리소스 레코드 섹션에 값을 입력하거나 붙여넣습니다.](../../media/b660ca9e-984d-449f-ae59-a65fe4e2c6bd.png)
  
5. **추가** 를 선택합니다.
    
    ![추가를 선택합니다.](../../media/32f8f23c-0b80-48da-b08e-4e04052971af.png)
  
6. 다른 사용자 지정 MX 레코드가 있으면 해당 레코드를 제거합니다.
    
1. TXT 레코드 행에서 **편집** 을 선택 합니다. 
    
    ![TXT 레코드 행에서 편집을 선택 합니다.](../../media/acc53ae9-3b8a-421d-8d11-d4a4108b2353.png)
  
2. 각각의 다른 사용자 지정 MX 레코드에 대한 **데이터** 상자의 항목을 선택하고 키보드에서 **삭제** 키를 눌러 해당 레코드를 삭제합니다. 
    
    각각의 다른 MX 레코드에 대한 **데이터** 항목을 삭제할 때까지 계속합니다. 
    
    ![Delete entries in the Data box](../../media/28192089-7b38-4d2e-9d52-9b83422c27d5.png)
  
7. 각각의 다른 MX 레코드에 대한 **데이터** 항목을 삭제한 경우 **저장** 을 선택하여 변경 내용을 저장합니다. 
    
    ![저장을 선택합니다.](../../media/bf496d01-ccbe-4800-95f4-7b2283f2e5f6.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a>Microsoft에 필요한 5개의 CNAME 레코드 추가하기

1. 시작하려면, [Google Domains 페이지]로 이동하고 (https://domains.google.com/registrar) 로그인하세요.
    
2. **도메인** 페이지의 **도메인** 구역에서 편집할 도메인에 대해 **DNS 구성** 을 선택합니다. 
    
3. 첫 번째 CNAME 레코드를 추가합니다.
    
    
            **사용자 지정 리소스 레코드** 구역의 새 레코드 상자에 다음 표의 첫 번째 행 값을 입력하거나 복사하여 붙여넣습니다. 
    
    (아래로 스크롤해야 할 수 있습니다.)
    
    (드롭다운 목록에서 **Type(종류)** 값을 선택합니다.) 
    
    |**이름**|**Type(종류)**|**TTL**|**데이터**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |1H  <br/> |autodiscover.outlook.com.  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |
    |sip  <br/> |CNAME  <br/> |1H  <br/> |sipdir.online.lync.com.  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |1H  <br/> |webdir.online.lync.com.  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |1H  <br/> |enterpriseregistration.windows.net.  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |1H  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |
   
    ![사용자 지정 리소스 레코드 섹션에 값을 입력하거나 붙여넣습니다.](../../media/cff9832a-6d57-421f-a183-55320974ed87.png)
  
4. **추가** 를 선택합니다.
    
    ![추가를 선택합니다.](../../media/4a78080a-e0b2-4582-9696-3fe4fea41e91.png)
  
5. 나머지 4개의 CNAME 레코드를 추가합니다.
    
    **사용자 지정 리소스 레코드** 구역에서 표의 다음 행 값을 사용하여 레코드를 만들고 다시 **추가** 를 선택하여 해당 레코드를 완료합니다. 
    
    요청 된 CNAME 레코드를 모두 만들 때까지 이 프로세스를 반복합니다.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가

> [!IMPORTANT]
> 도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다. 도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다. 도메인에 이미 SPF 레코드가 있는 경우 Microsoft의 새 SPF 레코드를 만들지 마세요. 대신, 필수 Microsoft 값을 현재 레코드에 추가하여 두 값 집합을 모두 포함하는 단일 SPF 레코드가 있도록 합니다. 예제가 필요하세요? [Microsoft에 대한 외부 Domain Name System 레코드](../../enterprise/external-domain-name-system-records.md)를 참조하세요. To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.yml). 
  
1. 시작하려면 [이 링크](https://domains.google.com/registrar)를 사용하여 Google Domains의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다. 방법은 다음과 같습니다.
    
1. **로그인** 을 선택합니다.
    
2. 로그인 자격 증명을 입력하고 다시 **로그인** 를 선택 합니다.
    
3. **도메인** 페이지의 **도메인** 구역에서 편집할 도메인에 대해 **DNS 구성** 을 선택합니다. 
    
4. **사용자 지정 리소스 레코드** 구역의 TXT 레코드 행에서 **편집** 을 선택합니다. 
    
    > [!IMPORTANT]
    > Google Domains에서는 여러 레코드를 포함할 수 있는 집합으로 TXT 레코드를 저장합니다. 도메인을 확인하는 데 사용한 TXT 레코드와 같은 다른 TXT 레코드가 하나 이상 있는 경우 해당 레코드 집합에 새 TXT 레코드를 추가해야 합니다. 추가 TXT 레코드를 개별 항목으로 입력하려고 하면 **중복 레코드** 오류 메시지가 표시됩니다. 
  
    ![TXT 레코드 행에서 편집을 선택 합니다.](../../media/eae14850-8d0c-4f29-8587-df8b36129d5f.png)
  
5. **(+)** 컨트롤을 선택합니다.  
    
    ![더하기 관리를 선택](../../media/628604cc-d2b2-42a5-bb5b-13c327b85d9f.png)
  
6. 새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.
    
    (아래로 스크롤해야 할 수 있습니다.)
    
    |**데이터**|
    |:-----|
    |v=spf1 include:spf.protection.outlook.com -all  <br/> 

    > [!NOTE]
    > 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.           
   
   ![사용자 지정 리소스 레코드 섹션에 값을 입력하거나 붙여넣습니다.](../../media/4645cc4f-9fcc-4626-9674-072ed6fa34c2.png)
  
7. **저장** 을 선택합니다.
    
    ![저장을 선택합니다.](../../media/20c4c926-f062-4048-9265-bf752be54e0c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Microsoft 필요한 2개의 SRV 레코드 추가하기
<a name="BKMK_add_SRV"> </a>

1. 시작하려면 [이 링크](https://domains.google.com/registrar)를 사용하여 Google Domains의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다. 방법은 다음과 같습니다.
    
2. **로그인** 을 선택합니다.
    
3. 로그인 자격 증명을 입력하고 다시 **로그인** 를 선택 합니다.
    
4. **도메인** 페이지의 **도메인** 구역에서 편집할 도메인에 대해 **DNS 구성** 을 선택합니다. 
    
5. 첫 번째 SRV 레코드를 추가합니다.
    
    
            **사용자 지정 리소스 레코드** 구역의 새 레코드 상자에 다음 표의 값을 입력하거나 복사하여 붙여넣습니다. 
    
    (아래로 스크롤해야 할 수 있습니다.)
    
    (드롭다운 목록에서 **Type(종류)** 값을 선택합니다.) 
    
    |**이름**|**Type(종류)**|**TTL**|**데이터**|
    |:-----|:-----|:-----|:-----|
    |_sip._tls|SRV|1H|100 1 443 sipdir.online.lync.com. **이 값은 마침표(.)로 끝나야 합니다.** **참고:** 모든 간격이 올바르게 유지되도록 이 항목을 복사하여 붙여넣는 것이 좋습니다.           |
    |_sipfederationtls._tcp|SRV|1H|100 1 5061 sipfed.online.lync.com. **이 값은 마침표(.)로 끝나야 합니다.**

    모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.       
   
    ![사용자 지정 리소스 레코드 섹션에 값을 입력하거나 붙여넣습니다.](../../media/429d06a9-c0af-4961-b7d2-7a8dea6db37e.png)
  
6. **추가** 를 선택합니다.
    
    ![추가를 선택합니다.](../../media/89df6efd-e641-4441-baa2-d9a890424569.png)
  
7. 다른 SRV 레코드를 추가합니다.
    
    **사용자 지정 리소스 레코드** 구역에서 표의 두 번째 행 값을 사용하여 레코드를 만들고 다시 **추가** 를 선택하여 해당 레코드를 완료합니다. 
    
    > [!NOTE]
    > Typically it takes about 15 minutes for DNS changes to take effect. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요. 
