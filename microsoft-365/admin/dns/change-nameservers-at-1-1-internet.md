---
title: 1 IONOS가 1인 경우 이름&변경
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
ms.assetid: 31efc571-c8b9-46fb-b42d-203c2fb25289
description: 21Vianet에서 운영하는 Office 365를 설정하여 DNS 레코드를 관리하는 방법을 알아보고, DNS 호스팅 공급자로는 1&인터넷이 있습니다.
ms.openlocfilehash: b363718c7d1d1845117f44317ae9e6b24e9a2e28
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658035"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-11-ionos"></a>1 IONOS가 1인 Microsoft 365를 설정하기 위해&변경

 원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.yml)** 하세요. 
  
Microsoft 365에서 Microsoft 365 DNS 레코드를 관리하게 하려는 경우 다음 지침을 따릅니다. 원하는 경우 모든 [Microsoft 365 DNS 레코드를 1 1 IONOS에서](create-dns-records-at-1-1-internet.md)&수 있습니다. 
  

    
## <a name="add-a-txt-record-for-verification"></a>확인을 위해 TXT 레코드 추가


Microsoft 365에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft 365에 도메인을 소유하고 있음을 증명할 수 있습니다.
  
> [!NOTE]
> 이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다. 
  
아래 단계를 따르거나 [비디오를 시청하세요(0:42에 시작)](https://support.microsoft.com/office/0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3).
  
1. To get started, go to your domains page at 1&1 IONOS via [this link.](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F) You'll be prompted to log in. 
    
2. MY **DOMAINS에서** 도메인 **관리를 선택합니다.**
    
3. On the **Domain Center** page, find the domain that you want to update; 그런 다음 해당 **도메인에** 대한 **패널(v)** 컨트롤을 선택합니다.
    
4. 도메인 설정 **영역에서** DNS 설정 **편집을 선택합니다.**
    
5. **TXT 및 SRV 레코드** 섹션에서 레코드 **추가를 선택합니다.**
    
    (아래로 스크롤해야 할 수 있습니다.) 
    
6. In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
||||
|:-----|:-----|:-----|
|**종류** <br/> |**Prefix(접두사)** <br/> |**Name Value(이름 값)** <br/> |
|TXT  <br/> |(Leave this field empty.)  <br/> |MS=ms *XXXXXXXX* <br/> **참고**: 예시입니다. 여기에는 Microsoft 365의 표에 있는 특정 **주소를 지정할 대상 또는 지점** 값을 사용합니다. [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md) <br/> |

   
7. **저장을** 선택한 다음 다시 **저장을** 선택합니다. 
    
8. DNS 설정 **편집** 대화 상자에서 **예를 선택합니다.**
    
9. 방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.
    
이제 도메인 등록 기관에 레코드가 추가되었습니다. Microsoft 365로 돌아가서 Microsoft 365에 레코드를 찾을 것을 요청합니다.
  
Microsoft 365에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.
  
1. I관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인</a> 페이지로 이동하십시오.
    
2. **도메인** 페이지에서 확인 중인 도메인을 선택합니다. 
    
3. **설정** 페이지에서 **설정 시작** 을 선택합니다.
    
4. **도메인 확인** 페이지에서 **확인** 을 선택합니다.
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [Microsoft 365에서](../get-help-with-domains/find-and-fix-issues.md)도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결을 참조합니다. 
  
## <a name="change-your-domains-nameserver-ns-records"></a>도메인의 NS(이름 서버) 레코드 변경

Microsoft 365를 사용하여 도메인 설정을 완료하려면 도메인 등록 기관에서 Microsoft 365 기본 및 보조 이름 서버를 지점으로 도메인의 NS 레코드를 변경합니다. 이렇게 하면 Microsoft 365가 도메인의 DNS 레코드를 자동으로 업데이트합니다. 전자 메일, 비즈니스용 Skype Online, 공개 웹 사이트가 사용자의 도메인을 사용하도록 모든 레코드가 자동으로 추가되고 모든 설정이 완료됩니다.
  
> [!CAUTION]
> Microsoft 365 이름 서버를 지점으로 도메인의 NS 레코드를 변경하면 현재 도메인과 연결된 모든 서비스가 영향을 받는 것입니다. 예를 들어 도메인으로 전송된 모든 전자 메일(예: rob@ *your_domain*  .com)은 이 변경을 한 후 Microsoft 365로 전송됩니다. 
  
Microsoft 365에서 도메인을 설정할 수 있도록 NS 레코드를 변경할 준비가 되신가요? 아래 단계를 따르거나 [비디오를 시청하세요(2:47에 시작).](https://support.microsoft.com/office/0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3)
  
> [!IMPORTANT]
>  다음 절차에서는 원치 않는 다른 이름 서스터를 목록에서 삭제하는 방법과 올바른 이름 서비스(아직 나열되지 않은 경우)를 추가하는 방법을 보여 합니다. > 이 섹션의 단계를 완료하면 다음 네 가지 이름만 나열됩니다. > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com 
  
1. To get started, go to your domains page at 1&1 IONOS by using [this link.](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F) You'll be prompted to log in. 
    
2. MY **DOMAINS에서** 도메인 **관리를 선택합니다.**
    
3. 도메인 센터 **페이지에서** 업데이트할 도메인을 찾은 다음 해당 도메인에 대한 **패널(v)** 컨트롤을 선택합니다. 
    
4. 도메인 설정 **영역에서** DNS 설정 **편집을 선택합니다.**
    
5. **이름 서버 설정** 구역에서 **다른 이름 서버** 를 선택합니다.
    
    (아래로 스크롤해야 할 수 있습니다.)
    
6. 현재 표시된 페이지에 이름 서버가 이미 나열되어 있는지 여부에 따라 다음 두 가지 절차 중 하나를 계속합니다.
    
  - 이미 나열된 이름 서버가 **없으면**[나열된 이름 서버가 없으면](#if-there-are-no-nameservers-already-listed).
    
  - 이미 나열된 이름 서버가 **있으면**[이름 서버가 나열되어 있는 경우](#if-there-are-nameservers-already-listed).
    
### <a name="if-there-are-no-nameservers-already-listed"></a>나열된 이름 서버가 없으면

1. **이름 서버 1** 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다. 
    
|||
|:-----|:-----|
|**이름 서버 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
   
   ![이름 서버 1 상자에 값 입력](../../media/34509935-461f-427f-9796-c3cf840bd9be.png)
  
2. **다른 이름 서버** 드롭다운 목록에서 **내 보조 이름 서버** 를 선택합니다.
    
    ![Choosing My secondary name servers in the list](../../media/7eb14856-86da-45c2-910c-c72312250a18.png)
  
3. **이름 서버 2, 3, 4** 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다. 
    
|||
|:-----|:-----|
|**이름 서버 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**이름 서버 3** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**이름 서버 4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
![이름 서버 값 입력](../../media/0f15880c-88b6-4133-8f31-62f0d98ee63f.png)
  
4. **저장** 을 선택합니다.
    
    ![이름 서버 설정에서 저장 선택 페이지](../../media/864f7927-7127-4784-b8d2-dadfea2f9dc8.png)
  
5. DNS 설정 **편집** 대화 상자에서 **예를 선택합니다.**
    
    ![DNS 설정 편집 대화 상자에서 저장 선택](../../media/0558e24c-17cd-428c-9ec1-5ed46481af7c.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. 그런 다음 Microsoft 전자 메일 및 기타 서비스가 모두 도메인에서 작동하게 설정됩니다. 
  
### <a name="if-there-are-nameservers-already-listed"></a>이름 서버가 나열되어 있는 경우

> [!CAUTION]
> 네 개의  *올바른*  이름 서버 외에 기존 이름 서버가 있는 경우에  *만*  다음 단계를 따릅니다(즉, 이름이 *ns1.bdm.microsoftonline.com*, *ns2.bdm.microsoftonline.com*, **ns3.bdm.microsoftonline.com** 또는 **ns4.bdm.microsoftonline.com** 이  **아닌**  현재 모든 이름 서버  **만**  삭제). 
  
1. **이름 서버** 상자에 이미 이름 서버가 나열되어 있으면 하나씩 선택한 후 키보드의 **Delete** 키를 눌러 삭제합니다. 
    
    ![Deleting name servers](../../media/af0a68cc-b058-4925-b3b1-52dfded003c1.png)
  
2. **이름 서버 1, 2, 3, 4** 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다. 
    
|||
|:-----|:-----|
|**이름 서버 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**이름 서버 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**이름 서버 3** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**이름 서버 4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![이름 서버 값 입력](../../media/52826bd1-0596-4103-a728-d5d28b9610d2.png)
  
3. **저장** 을 선택합니다.
    
    ![이름 서버 설정에서 저장 선택 페이지](../../media/cd10e4fb-b7fa-480f-855b-a443f2705cf2.png)
  
4. DNS 설정 **편집** 대화 상자에서 **예를 선택합니다.**
    
    ![DNS 설정 편집 대화 상자에서 저장 선택](../../media/0558e24c-17cd-428c-9ec1-5ed46481af7c.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. 그런 다음 Microsoft 전자 메일 및 기타 서비스가 모두 도메인에서 작동하게 설정됩니다. 
  


