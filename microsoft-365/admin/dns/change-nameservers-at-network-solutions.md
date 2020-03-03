---
title: Network Solutions에서 이름 서버를 변경하여 Office 365 설정
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
ms.assetid: d4ba60f3-4e1c-4180-99bd-250b8955be2a
description: 'Office 365에서 DNS 레코드를 관리 하도록 하려면 네트워크 솔루션을 사용 하 여 Office 365 사용자 지정 도메인을 설정 하는 방법을 알아봅니다. '
ms.openlocfilehash: 5eae7561baa6e0efb4436e6758d3fd972a2700cc
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2020
ms.locfileid: "42351759"
---
# <a name="change-nameservers-to-set-up-office-365-with-network-solutions"></a>Network Solutions에서 이름 서버를 변경하여 Office 365 설정

 **원하는 정보는 찾지 못한 경우 [도메인 질문과 대답을 확인](../setup/domains-faq.md)** 하세요.
  
Office 365에서 Office 365 DNS 레코드를 관리하도록 하려면 다음 지침을 따릅니다. 원하는 경우 [모든 Office 365 DNS 레코드를 Network Solutions에서 관리](create-dns-records-at-network-solutions.md)할 수 있습니다.
  
    
## <a name="add-a-txt-record-at-network-solutions-to-verify-that-you-own-the-domain"></a>Network Solutions에서 TXT 레코드를 추가해 도메인을 소유하고 있는지 확인

Office 365에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Office 365에 도메인을 소유하고 있음을 증명할 수 있습니다.
  
> [!NOTE]
> 이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다. 
  
아래 단계를 따르거나 [비디오를 시청하세요(0:47에 시작)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-Network-Solutions-69b092e3-c026-4d19-a7d0-16cdb2d8b261?ui=en-US&amp;rs=en-US&amp;ad=US).
  
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
|@  <br/> (The system will change this value to **@ (None)** when you save the record.)  <br/> |3600  <br/> |MS=ms *XXXXXXXX*  <br/> **참고**:이는 예입니다. 여기에는 Office 365의 표에 있는 특정 **보낼 대상 또는 지점** 값을 사용합니다.           [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)
   
    
   ![새 레코드의 상자에 값을 입력 하거나 붙여넣습니다.](../../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. **계속**을 선택 합니다.
    
    ![계속을 선택](../../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. **변경 내용 저장**을 선택 합니다.
    
    ![변경 내용 저장을 선택 합니다.](../../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. 방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.
    
이제 도메인 등록 기관에 레코드가 추가되었습니다. Office 365로 돌아가서 Office 365에 레코드를 찾을 것을 요청합니다.
  
Office 365에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.
  
1. I관리 센터에서 ** 설정 ** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인 </a> 페이지로 이동하십시오.

    
2. **도메인** 페이지에서 확인 중인 도메인을 선택합니다. 
    
    
  
3. **설정** 페이지에서 **설정 시작**을 선택합니다.
    
    
  
4. **도메인 확인** 페이지에서 **확인**을 선택합니다.
    
    
  
> [!NOTE]
>  일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 
  
## <a name="change-your-domains-nameserver-ns-records"></a>도메인의 NS(이름 서버) 레코드 변경

Office 365에서 도메인 설정을 완료하려면 도메인 등록 기관에서 도메인의 NS 레코드가 Office 365 기본 및 보조 이름 서버를 가리키도록 변경합니다. 이렇게 하면 Office 365가 사용자 대신 도메인의 DNS 레코드를 업데이트하도록 설정됩니다. 전자 메일, 비즈니스용 Skype Online, 공개 웹 사이트가 사용자의 도메인을 사용하도록 모든 레코드가 자동으로 추가되고 모든 설정이 완료됩니다.
  
> [!CAUTION]
> Office 365 이름 서버를 가리키도록 도메인 NS 레코드를 변경하면 현재 도메인에 연결되는 모든 서비스가 영향을 받습니다. 예를 들어 이 변경 내용을 적용하면 사용자의 도메인(예: rob@ *사용자_도메인*  .com)으로 보낸 전자 메일이 Office 365로 수신됩니다.
  
Office 365에서 도메인을 설정할 수 있도록 NS 레코드를 변경할 준비가 되면 아래 단계를 따르거나 [비디오를 시청하세요(2:23에 시작)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-Network-Solutions-69b092e3-c026-4d19-a7d0-16cdb2d8b261?ui=en-US&amp;rs=en-US&amp;ad=US).
  
> [!IMPORTANT]
>  이 섹션의 단계를 완료 한 후에는 **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**및 **ns4.bdm.microsoftonline.com**와 같은 4 *가지 이름 서버를 나열 해야 합니다.* 다음 절차에는 원치 않는 기타 이름 서버를 목록에서 삭제하는 방법과  *올바른*  이름 서버가 목록에 아직 없는 경우 이를 추가하는 방법이 나타나 있습니다. 
  
1. 시작하려면 [이 링크](https://www.networksolutions.com/manage-it)를 사용하여 Network Solutions의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.
    
    > [!IMPORTANT]
    > **로그인** 단추를 선택 하기 전에 로그인 **:** 드롭다운 목록에서 **내 도메인 이름 관리** 를 선택 합니다. 
  
    ![Manage My Domain Names(내 도메인 이름 관리)를 선택하고 Network Solutions에 로그인합니다.](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. 수정하려는 도메인 이름 옆의 확인란을 선택합니다.
    
    ![도메인에 대한 확인란을 선택합니다.](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. **DNS 편집**을 선택 합니다.
    
    ![DNS 편집을 선택 합니다.](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. **DNS 이동을**선택 합니다.
    
    ![NetworkSolutionsBP-Redelegate-1-1](../../media/e57a30f3-63d5-4bcb-84c6-c8be21c261a2.png)
  
5. 현재 표시된 페이지에 이름 서버가 이미 나열되어 있는지 여부에 따라 다음 두 가지 절차 중 하나를 계속합니다.
    
  - 이미 나열된 이름 서버가 **없으면**[나열된 이름 서버가 없으면](#if-there-are-no-nameservers-already-listed).
    
  - 이미 나열된 이름 서버가 **있으면**[이름 서버가 나열되어 있는 경우](#if-there-are-nameservers-already-listed).
    
### <a name="if-there-are-no-nameservers-already-listed"></a>나열된 이름 서버가 없으면

1. **도메인 페이지의** **도메인 이름 서버 지정** 섹션에서 **다른 이름 서버 추가**를 선택 합니다.
    
    ![NetworkSolutionsBP-Redelegate-1-2-1](../../media/57e22ef1-ac88-4d4a-bc8e-058023255dfd.png)
  
2. **도메인 이름** 페이지에서 다음 표의 이름 서버 값을 입력하거나 복사하여 붙여넣습니다. 
    
|||
|:-----|:-----|
|**이름 서버 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**이름 서버 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**이름 서버 2** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**이름 서버 2** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
    
![NetworkSolutionsBP-Redelegate-1-2-2](../../media/795e8c6b-4828-4de2-b624-82f067bb2eb1.png)
  
3. **DNS 이동을**선택 합니다.
    
    ![NetworkSolutionsBP-Redelegate-1-2-3](../../media/d4a0a7c2-6868-471f-bbf4-16ce2e2348de.png)
  
4. **변경 내용 저장**을 선택 합니다.
    
    ![NetworkSolutionsBP-Redelegate-1-2-4](../../media/897bc864-b340-4385-abeb-f94bc7f73e5e.png)
  
> [!NOTE]
> 이름 서버 레코드 업데이트가 인터넷의 DNS 시스템 전체에 업데이트되기까지 몇 시간이 걸릴 수 있습니다. 그 후에는 Office 365 전자 메일 및 기타 서비스가 모두 사용자의 도메인을 사용하도록 설정됩니다. 
  
### <a name="if-there-are-nameservers-already-listed"></a>이름 서버가 나열되어 있는 경우

> [!CAUTION]
> 네 개의  *올바른*  이름 서버 외에 기존 이름 서버가 있는 경우에  *만*  다음 단계를 따릅니다(즉, 이름이 *ns1.bdm.microsoftonline.com*, *ns2.bdm.microsoftonline.com*, **ns3.bdm.microsoftonline.com** 또는 **ns4.bdm.microsoftonline.com** 이  **아닌**  현재 모든 이름 서버  **만**  삭제).
  
1. 다른 이름 서버가 나열되어 있으면 하나씩 선택한 후 키보드의 **Delete** 키를 눌러 삭제합니다.
    
    ![NetworkSolutions-BP-Redelegate-1-5](../../media/eeb8ad22-bf4a-43a8-b97a-f09c3654d89b.png)
  
2. **다른 이름 서버 추가**를 선택 합니다.
    
    ![NetworkSolutionsBP-Redelegate-1-2-1](../../media/57e22ef1-ac88-4d4a-bc8e-058023255dfd.png)
  
3. **도메인 이름** 페이지에서 다음 표의 이름 서버 값을 입력하거나 복사하여 붙여넣습니다.
 
    
|||
|:-----|:-----|
|**이름 서버 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**이름 서버 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Name Server 3**(이름 서버 3) <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Name Server 4**(이름 서버 4) <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
    
![NetworkSolutionsBP-Redelegate-1-2-2](../../media/795e8c6b-4828-4de2-b624-82f067bb2eb1.png)
  
4. **DNS 이동을**선택 합니다.
    
    ![NetworkSolutionsBP-Redelegate-1-2-3](../../media/d4a0a7c2-6868-471f-bbf4-16ce2e2348de.png)
  
5. **변경 내용 저장을 선택 합니다.**
    
    ![NetworkSolutionsBP-Redelegate-1-2-4](../../media/897bc864-b340-4385-abeb-f94bc7f73e5e.png)
  
> [!NOTE]
> 이름 서버 레코드 업데이트가 인터넷의 DNS 시스템 전체에 업데이트되기까지 몇 시간이 걸릴 수 있습니다. 그 후에는 Office 365 전자 메일 및 기타 서비스가 모두 사용자의 도메인을 사용하도록 설정됩니다.
