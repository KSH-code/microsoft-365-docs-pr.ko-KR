---
title: Microsoft의 Network Solutions에서 DNS 레코드 만들기
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1dc55f9f-5309-450f-acc3-b2b4119c8be3
description: 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 및 Microsoft 용 네트워크 솔루션의 기타 서비스에 대 한 DNS 레코드를 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: 25e85bf30527b49ada711af9ba5c418409acd24c
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780340"
---
# <a name="create-dns-records-at-network-solutions-for-microsoft"></a>Microsoft의 Network Solutions에서 DNS 레코드 만들기

 **원하는 정보는 찾지 못한 경우 [도메인 질문과 대답을 확인](../setup/domains-faq.md)** 하세요. 
  
DNS 호스팅 공급자로 Network Solutions를 사용하고 있는 경우, 이 문서에 나와 있는 단계를 따라 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 등에 대한 DNS 레코드를 설정합니다.
  
다음은 추가할 기본 레코드입니다. 아래 단계를 따르거나 [비디오를 시청하세요](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099). 
  
- [확인을 위해 TXT 레코드 추가](#add-a-txt-record-for-verification)
    
- [사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드 추가하기](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [Microsoft에 필요한 CNAME 레코드 추가하기](#add-the-cname-records-that-are-required-for-microsoft)
    
- [전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [Microsoft 필요한 2개의 SRV 레코드 추가하기](#add-the-two-srv-records-that-are-required-for-microsoft)
    
네트워크 솔루션에서 이러한 레코드를 추가 하 고 나면 도메인이 Microsoft 서비스에서 작동 하도록 설정 됩니다.
  

  
> [!NOTE]
>  일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 
  
## <a name="add-a-txt-record-for-verification"></a>확인을 위해 TXT 레코드 추가
<a name="BKMK_verify"> </a>

Microsoft에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft에 도메인을 소유하고 있음을 증명할 수 있습니다.
  
> [!NOTE]
> 이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다. 
  
아래 단계를 따르거나 [비디오를 시청하세요(0:47에 시작)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).
  
1. 시작하려면 [이 링크](https://www.networksolutions.com/manage-it)를 사용하여 Network Solutions의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.
    
    > [!IMPORTANT]
    > **로그인** 단추를 선택 하기 전에 로그인 **:** 드롭다운 목록에서 **내 도메인 이름 관리** 를 선택 합니다. 
  
    ![Manage My Domain Names(내 도메인 이름 관리)를 선택하고 Network Solutions에 로그인합니다.](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. 수정하려는 도메인 이름 옆의 확인란을 선택합니다.
    
    ![도메인에 대한 확인란을 선택합니다.](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. **DNS 편집**을 선택 합니다.
    
    ![DNS 편집을 선택 합니다.](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. **고급 DNS 레코드 관리**를 선택 합니다.
    
    (You may have to scroll down.)
    
    ![고급 DNS 레코드 관리 선택](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. 아래쪽 **텍스트 (Txt 레코드)** 구역으로 스크롤한 다음 **txt 레코드 편집**을 선택 합니다.
    
    ![TXT 레코드 편집을 선택 합니다.](../../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. 새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.
    
    |**Host**|**TTL**|**텍스트**|
    |:-----|:-----|:-----|
    |@  <br/> (The system will change this value to **@ (None)** when you save the record.)  <br/> |3600  <br/> |MS=ms *XXXXXXXX*  <br/> **참고:** 이 값은 예시입니다. 여기에는 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.  [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)   |
       
    ![새 레코드의 상자에 값을 입력 하거나 붙여넣습니다.](../../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. **계속**을 선택 합니다.
    
    ![계속을 선택](../../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. **변경 내용 저장**을 선택 합니다.
    
    ![변경 내용 저장을 선택 합니다.](../../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. 방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.
    
이제 도메인 등록 기관에 레코드가 추가되었습니다. Microsoft로 돌아가서 레코드를 요청합니다.
  
Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.

1. I관리 센터에서 ** 설정 ** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인 </a> 페이지로 이동하십시오.
    
2. **도메인** 페이지에서 확인 중인 도메인을 선택합니다. 
    
    
  
3. **설정** 페이지에서 **설정 시작**을 선택합니다.
    
    
  
4. **도메인 확인** 페이지에서 **확인**을 선택합니다.
    
    
  
> [!NOTE]
>  일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드 추가하기
<a name="BKMK_add_MX"> </a>

아래 단계를 따르거나 [비디오를 시청하세요(3:51에 시작)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).
  
1. 시작하려면 [이 링크](https://www.networksolutions.com/manage-it)를 사용하여 Network Solutions의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.
    
    > [!IMPORTANT]
    > **로그인** 단추를 선택 하기 전에 로그인 **:** 드롭다운 목록에서 **내 도메인 이름 관리** 를 선택 합니다. 
  
    ![Manage My Domain Names(내 도메인 이름 관리)를 선택하고 Network Solutions에 로그인합니다.](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. 수정하려는 도메인 이름 옆의 확인란을 선택합니다.
    
    ![도메인에 대한 확인란을 선택합니다.](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. **DNS 편집**을 선택 합니다.
    
    ![DNS 편집을 선택 합니다.](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. **고급 DNS 레코드 관리**를 선택 합니다.
    
    (You may have to scroll down.)
    
    ![고급 DNS 레코드 관리 선택](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. **메일 서버 (Mx 레코드)** 섹션이 될 때까지 아래로 스크롤한 다음 **mx 레코드 편집**을 선택 합니다.
    
    ![MX 레코드 편집을 선택 합니다.](../../media/74b4e412-9073-4d2d-8710-fe340b223798.png)
  
6. 새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.
    
    |**Priority(우선 순위)**|**TTL**|**메일 서버**|
    |:-----|:-----|:-----|
    |10    <br/> 우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)을 참조하세요. <br/> |3600  <br/> | *\<domain-key\>*. mail.protection.outlook.com  <br/> **This value MUST end with a period (.)** <br/> **참고:** *\<domain-key\>* Microsoft 계정에서를 다운로드 하세요. [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![새 레코드의 상자에 값을 입력 하거나 붙여넣습니다.](../../media/0bb96872-cc6e-4dfa-a649-fb7efbbf0012.png)
  
7. **계속**을 선택 합니다.
    
    ![계속을 선택](../../media/963f758b-e79d-4452-8340-7eba8a3972c9.png)
  
8. **변경 내용 저장**을 선택 합니다.
    
    ![변경 내용 저장을 선택 합니다.](../../media/7c2f784a-6dee-4364-866c-ad7202ef1fc2.png)
  
9. 다른 MX 레코드가 있으면 각 레코드에 대한 **삭제**를 선택하여 레코드를 모두 삭제합니다. 
    
    ![Select the Delete check box for other MX records](../../media/709d6133-9f5d-490a-a91e-95e21ca94695.png)
  
10. 모두 선택 되 면 **계속**을 선택 합니다.
    
    ![계속을 선택](../../media/4710f988-0bbc-4ba7-bf31-ca2392b2900e.png)
  
11. **변경 내용 저장**을 선택 합니다.
    
    ![변경 내용 저장을 선택 합니다.](../../media/24432ec6-666b-4612-9488-37c06437959b.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>Microsoft에 필요한 CNAME 레코드 추가하기
<a name="BKMK_add_CNAME"> </a>

아래 단계를 따르거나 [비디오를 시청하세요(4:43에 시작)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).
  
1. 시작하려면 [이 링크](https://www.networksolutions.com/manage-it)를 사용하여 Network Solutions의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.
    
    > [!IMPORTANT]
    > **로그인** 단추를 선택 하기 전에 로그인 **:** 드롭다운 목록에서 **내 도메인 이름 관리** 를 선택 합니다. 
  
    ![Manage My Domain Names(내 도메인 이름 관리)를 선택하고 Network Solutions에 로그인합니다.](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. 수정하려는 도메인 이름 옆의 확인란을 선택합니다.
    
    ![도메인에 대한 확인란을 선택합니다.](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. **DNS 편집**을 선택 합니다.
    
    ![DNS 편집을 선택 합니다.](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. **고급 DNS 레코드 관리**를 선택 합니다.
    
    (You may have to scroll down.)
    
    ![고급 DNS 레코드 관리 선택](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. 아래로 스크롤하여 **호스트 별칭 (CNAME 레코드)** 섹션으로 스크롤한 다음 **CNAME 레코드 편집**을 선택 합니다.
    
    ![호스트 별칭 아래에서 CNAME 레코드 편집을 선택 합니다.](../../media/2d0a4666-8d40-48f4-886c-64a5157baaf5.png)
  
6. 네 개의 새 레코드 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.
    
    |**별칭**|**TTL**|**호스트 이름 참조**|**기타 호스트          ( **기타 호스트** 옵션 단추 선택)**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |3600  <br/> |(설정 없음)  <br/> |autodiscover.outlook.com  <br/> **This value MUST end with a period (.)** <br/> |
    |sip  <br/> |3600  <br/> |(설정 없음)  <br/> |sipdir.online.lync.com  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |
    |lyncdiscover  <br/> |3600  <br/> |(설정 없음)  <br/> |webdir.online.lync.com  <br/> **This value MUST end with a period (.)** <br/> |
    |enterpriseregistration  <br/> |3600  <br/> |(설정 없음)  <br/> |enterpriseregistration.windows.net  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |
    |enterpriseenrollment  <br/> |3600  <br/> |(설정 없음)  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> **This value MUST end with a period (.)** <br/> |
    
    ![새 레코드 값 입력 또는 붙여넣기](../../media/5ce0b30c-b46c-4778-aa5a-fb5e2f0961c1.png)
  
7. 필요한 CNAME 레코드를 모두 추가한 경우 **계속**을 선택 합니다.
    
    ![계속을 선택](../../media/4978bd8b-f6a6-458d-9522-ad612b301c4a.png)
  
8. **변경 내용 저장**을 선택 합니다.
    
    ![변경 내용 저장을 선택 합니다.](../../media/f005c38a-0d8d-4c61-bec6-15e60c89aa5a.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다. 도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다. 도메인에 이미 SPF 레코드가 있는 경우 Microsoft의 새 SPF 레코드를 만들지 마세요. 대신, 두 값 집합을 모두 포함 하는 *단일* SPF 레코드가 있도록 현재 레코드에 필수 Microsoft 값을 추가 합니다. 
  
아래 단계를 따르거나 [비디오를 시청하세요(5:35에 시작)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).
  
1. 시작하려면 [이 링크](https://www.networksolutions.com/manage-it)를 사용하여 Network Solutions의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.
    
    > [!IMPORTANT]
    > **로그인** 단추를 선택 하기 전에 로그인 **:** 드롭다운 목록에서 **내 도메인 이름 관리** 를 선택 합니다. 
  
    ![Manage My Domain Names(내 도메인 이름 관리)를 선택하고 Network Solutions에 로그인합니다.](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. 수정하려는 도메인 이름 옆의 확인란을 선택합니다.
    
    ![도메인에 대한 확인란을 선택합니다.](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. **DNS 편집**을 선택 합니다.
    
    ![DNS 편집을 선택 합니다.](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. **고급 DNS 레코드 관리**를 선택 합니다.
    
    (You may have to scroll down.)
    
    ![고급 DNS 레코드 관리 선택](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. 아래쪽 **텍스트 (Txt 레코드)** 구역으로 스크롤한 다음 **txt 레코드 편집**을 선택 합니다.
    
    ![텍스트 아래에서 TXT 레코드 편집을 선택 합니다.](../../media/a69a2631-6da2-4e81-99ab-9a9ab9b30b07.png)
  
6. 새 레코드의 상자에서 다음 값을 입력하거나 복사하여 붙여 넣습니다.
    
    |**호스트**|**TTL**|**텍스트**|
    |:-----|:-----|:-----|
    |@  <br/> (The system will change this value to **@ (None)** when you save the record.)  <br/> |3600  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **참고: ** 모든 간격이 올바르게 유지되도록 이 항목을 복사하여 붙여넣는 것이 좋습니다. |
       
    ![새 레코드에 대 한 값 입력 또는 붙여넣기](../../media/11564eca-e2ee-4f17-af2b-a00eb7c157db.png)
  
7. **계속**을 선택 합니다.
    
    ![계속을 선택](../../media/482a8dae-0c79-47c4-8bd8-87965683de24.png)
  
8. **변경 내용 저장**을 선택 합니다.
    
    ![변경 내용 저장을 선택 합니다.](../../media/600b8c6d-184f-4213-a50e-8f119ebf3ff0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Microsoft 필요한 2개의 SRV 레코드 추가하기
<a name="BKMK_add_SRV"> </a>

아래 단계를 따르거나 [비디오를 시청하세요(6:18에 시작)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).
  
1. 시작하려면 [이 링크](https://www.networksolutions.com/manage-it)를 사용하여 Network Solutions의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.
    
    > [!IMPORTANT]
    > **로그인** 단추를 선택 하기 전에 로그인 **:** 드롭다운 목록에서 **내 도메인 이름 관리** 를 선택 합니다. 
  
    ![Manage My Domain Names(내 도메인 이름 관리)를 선택하고 Network Solutions에 로그인합니다.](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. 수정하려는 도메인 이름 옆의 확인란을 선택합니다.
    
    ![도메인에 대한 확인란을 선택합니다.](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. **DNS 편집**을 선택 합니다.
    
    ![DNS 편집을 선택 합니다.](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. **고급 DNS 레코드 관리**를 선택 합니다.
    
    (You may have to scroll down.)
    
    ![고급 DNS 레코드 관리 선택](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. 아래로 스크롤하여 **서비스 (Srv 레코드)** 섹션을 찾은 다음 **srv 레코드 편집**을 선택 합니다.
    
    ![서비스 아래에서 SRV 레코드 편집을 선택 합니다.](../../media/9a9248ea-5de5-4e16-9364-f7600fa371f5.png)
  
6. 두 개의 새 레코드 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.
    
    (드롭다운 목록에서 **서비스** 및 **프로토콜** 값을 선택합니다.) 
    
    |**서비스**|**프로토콜**|**TTL**|**Priority(우선 순위)**|**Weight(가중치)**|**Port(포트)**|**대상**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |_tls  <br/> |3600  <br/> |100  <br/> |1   <br/> |443  <br/> |sipdir.online.lync.com  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |
    |_sipfederationtls  <br/> |_tcp  <br/> |3600  <br/> |100  <br/> |1   <br/> |5061  <br/> |sipfed.online.lync.com  <br/> **This value MUST end with a period (.)** <br/> |
       
    ![새 레코드 값 입력 또는 붙여넣기](../../media/86968d1c-8e43-4e61-aeaa-37fc7d7ef7a7.png)
  
7. **계속**을 선택 합니다.
    
    ![계속을 선택](../../media/bfe2c778-5d2b-4bb6-a79d-c3ff9caf9e1e.png)
  
8. **변경 내용 저장**을 선택 합니다.
    
    ![변경 내용 저장을 선택 합니다.](../../media/6d323126-0ebe-45ab-8567-c234711d84c7.png)
  
> [!NOTE]
>  일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 
  
