---
title: Google 도메인에서 이름 서버를 변경하여 Office 365 설정
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
ms.assetid: 68a08e94-26c2-4df2-9216-026b8ec907ca
description: Google 도메인에서 사용자 지정 도메인의 DNS 레코드를 관리 하기 위해 Office 365을 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: 771d38b9a3d08bef75c3ad1958f981539edb6c04
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42246684"
---
# <a name="change-nameservers-to-set-up-office-365-with-google-domains"></a>Google 도메인에서 이름 서버를 변경하여 Office 365 설정

 **원하는 정보는 찾지 못한 경우 [도메인 질문과 대답을 확인](../setup/domains-faq.md)** 하세요. 
  
Office 365에서 Office 365 DNS 레코드를 관리하도록 하려면 다음 지침을 따릅니다. 원하는 경우 [모든 Office 365 DNS 레코드를 Google Domains에서 관리](create-dns-records-at-google-domains.md)할 수 있습니다.
  
    
## <a name="add-a-txt-record-for-verification"></a>확인을 위해 TXT 레코드 추가

Office 365에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Office 365에 도메인을 소유하고 있음을 증명할 수 있습니다.
  
> [!NOTE]
>  이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다. 
  
1. 시작 하려면 [이 링크](https://domains.google.com/registrar)를 통해 Google 도메인의 도메인 페이지로 이동 합니다. You'll be prompted to sign in. To do so:
    
1. **로그인**을 선택 합니다.
    
2. 로그인 자격 증명을 입력 하 고 다시 **로그인**을 선택 합니다.
    
2. **Domains** (도메인) 페이지의 **domain (도메인** ) 섹션에서 편집 하려는 도메인에 대해 **DNS 구성을** 선택 합니다. 
    
3. In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (You may have to scroll down.)
    
    (Choose the **Type** value from the drop-down list.) 
    
|||||
|:-----|:-----|:-----|:-----|
|**이름** <br/> |**종류** <br/> |**TTL** <br/> |**데이터** <br/> |
|@  <br/> |TXT  <br/> |1H  <br/> |MS=ms *XXXXXXXX* <br/> **참고:** 예를 들면 다음과 같습니다. 여기에는 Office 365의 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다. [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)       <br/>  |
   
4. **추가**를 선택합니다.
    
5. 방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. 관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동 합니다.

    
2. **도메인** 페이지에서 확인 하려는 도메인을 선택 합니다. 
    
3. **설정** 페이지에서 **설정 시작**을 선택 합니다.
    
4. **도메인 확인** 페이지에서 **확인**을 선택 합니다.
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제에 문제가 있는 경우 [Office 365에서 도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조 하세요. 
  
## <a name="change-your-domains-nameserver-ns-records"></a>도메인의 NS(이름 서버) 레코드 변경

Office 365에서 도메인 설정을 완료하려면 도메인 등록 기관에서 도메인의 NS 레코드가 Office 365 기본 및 보조 이름 서버를 가리키도록 변경합니다. 이렇게 하면 Office 365가 사용자 대신 도메인의 DNS 레코드를 업데이트하도록 설정됩니다. 전자 메일, 비즈니스용 Skype Online, 공개 웹 사이트가 사용자의 도메인을 사용하도록 모든 레코드가 자동으로 추가되고 모든 설정이 완료됩니다.
  
> [!CAUTION]
> Office 365 이름 서버를 가리키도록 도메인 NS 레코드를 변경하면 현재 도메인에 연결되는 모든 서비스가 영향을 받습니다. 예를 들어 rob@ *your_domain* 와 같이 도메인으로 전송 되는 모든 전자 메일  com)이 변경 된 후에 Office 365로 시작 됩니다. 
  
> [!IMPORTANT]
> The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list. >이 섹션의 단계를 완료 한 후에는 다음 4 가지 이름 서버 나열 해야 합니다. 
  
1. 시작하려면 [이 링크](https://domains.google.com/registrar)를 사용하여 Google Domains의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다. 방법은 다음과 같습니다.
    
1. **로그인**을 선택 합니다.
    
2. 로그인 자격 증명을 입력 하 고 다시 **로그인**을 선택 합니다.
    
2. **Domains** (도메인) 페이지의 **domain (도메인** ) 섹션에서 편집 하려는 도메인에 대해 **DNS 구성을** 선택 합니다. 
    
3. **도메인** 페이지의 **이름 서버** 구역에서 **사용자 지정 이름 서버 사용**을 선택합니다.
    
    ![Google-Domains-BP-Redelegate-1-1](../media/e264bc05-5a56-4962-bcaf-e2d999f62278.png)
  
4. 현재 표시된 페이지에 이름 서버가 이미 나열되어 있는지 여부에 따라 다음 두 가지 절차 중 하나를 계속합니다.
    
  - 이미 나열된 이름 서버가 **없으면**[나열된 이름 서버가 없으면](#if-there-are-no-nameservers-already-listed).
    
  - 이미 나열된 이름 서버가 **있으면**[이름 서버가 나열되어 있는 경우](#if-there-are-nameservers-already-listed).
    
### <a name="if-there-are-no-nameservers-already-listed"></a>나열된 이름 서버가 없으면

1. 첫 번째 이름 서버를 추가합니다.
    
    **Name servers**(이름 서버) 섹션의 **NAME SERVER**(이름 서버) 상자에 다음 표의 첫 번째 값을 입력하거나 복사하여 붙여넣습니다. 
    
|||
|:-----|:-----|
|**첫 번째 이름 서버** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**두 번째 이름 서버** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**세 번째 이름 서버** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**네 번째 이름 서버** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Google-Domains-Redelegate-1-2](../media/6d14544d-7783-4ed4-b4dd-691624af7172.png)
  
2. **+ (추가)** 컨트롤을 선택 하 여 빈 행을 만듭니다. 
    
    ![Google-Domains-BP-Redelegate-1-3](../media/ea23e5fc-07e1-4ffc-b8cf-8526867b752d.png)
  
3. 나머지 세 개의 이름 서버 레코드를 추가합니다.
    
    **사용자 지정 이름 서버 사용** 섹션에서 표의 다음 행 값을 사용 하 여 레코드를 만들고 **+ (추가)** 컨트롤을 선택 하 여 다른 행을 추가 합니다. 
    
    4개의 이름 서버 레코드를 모두 만들 때까지 이 과정을 반복합니다.
    
4. **저장**을 선택합니다.
    
    ![Google-Domains-BP-Redelegate-1-5](../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> 이름 서버 레코드 업데이트가 인터넷의 DNS 시스템 전체에 업데이트되기까지 몇 시간이 걸릴 수 있습니다. 그 후에는 Office 365 전자 메일 및 기타 서비스가 모두 사용자의 도메인을 사용하도록 설정됩니다. 
  
### <a name="if-there-are-nameservers-already-listed"></a>이름 서버가 나열되어 있는 경우

1. 다른 이름 서버 나열 되어 있는 경우 **편집**을 선택 합니다.
    
    > [!CAUTION]
    > Follow these steps only if you have existing nameservers other than the four correct nameservers. (즉, **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**또는 **ns4.bdm.microsoftonline.com**로 이름이 지정 *되지* 않은 현재 이름 서버 삭제 합니다.) 
  
    ![Google-Domains-BP-Redelegate-1-6-1](../media/fb45d120-55ab-42c2-bdb6-19b130c3c7db.png)
  
2. 이름 서버를 하나씩 선택하고 키보드에서 **Delete** 키를 눌러 삭제합니다. 
    
    ![Google-Domains-BP-Redelegate-1-6-2](../media/524e64ad-56e6-4254-8a64-e4a4c3230f89.png)
  
3. **이름 서버** 구역의 **이름 서버** 행에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다. 
    
|||
|:-----|:-----|
|**첫 번째 이름 서버** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**두 번째 이름 서버** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**세 번째 이름 서버** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**네 번째 이름 서버** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Google-Domains-Redelegate-1-7](../media/e008dccb-d789-4f52-8ecc-02831b7c6fb2.png)
  
4. **+ (추가)** 컨트롤을 선택 하 여 빈 행을 만듭니다. 
    
    ![Google-Domains-BP-Redelegate-1-8](../media/6ce40b1e-8464-443f-a64a-825dc8764590.png)
  
5. 나머지 두 개의 이름 서버 레코드를 추가합니다.
    
    **사용자 지정 이름 서버 사용** 섹션에서 표의 다음 행 값을 사용 하 여 레코드를 만들고 **+ (추가)** 컨트롤을 선택 하 여 다른 행을 추가 합니다. 
    
    4개의 이름 서버 레코드를 모두 만들 때까지 이 과정을 반복합니다.
    
6. **저장**을 선택합니다.
    
    ![Google-Domains-BP-Redelegate-1-5](../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> 이름 서버 레코드 업데이트가 인터넷의 DNS 시스템 전체에 업데이트되기까지 몇 시간이 걸릴 수 있습니다. 그 후에는 Office 365 전자 메일 및 기타 서비스가 모두 사용자의 도메인을 사용하도록 설정됩니다. 
  
