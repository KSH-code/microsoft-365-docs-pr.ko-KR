---
title: Bluehost을 사용 하 여 Microsoft를 설정 하도록 이름 서버 변경
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
ms.assetid: 7712b6af-329c-43a0-af7b-c4e4c1befb0e
description: 'Bluehost에서 DNS 레코드를 관리 하도록 Microsoft를 설정 하는 방법을 알아봅니다. '
ms.openlocfilehash: c15ba11e0df57deaef61309f5bc6d1b2a60645b8
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646466"
---
# <a name="change-nameservers-to-set-up-microsoft-with-bluehost"></a>Bluehost을 사용 하 여 Microsoft를 설정 하도록 이름 서버 변경

 원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.md)** 하세요. 
  
Microsoft에서 DNS 레코드를 관리 하도록 하려면 다음 지침을 따릅니다. 원하는 경우 [Bluehost에서 모든 DNS 레코드를 관리할](create-dns-records-at-bluehost.md)수 있습니다.
  
## <a name="add-a-txt-record-for-verification"></a>확인을 위해 TXT 레코드 추가

Microsoft에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft에 도메인을 소유하고 있음을 증명할 수 있습니다.
  
> [!NOTE]
> 이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다. 
  
1. 시작하려면 [이 링크](https://my.bluehost.com/cgi/dm)를 사용하여 Bluehost의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.
    
2. **domains(도메인)** 페이지의 **domain(도메인)** 영역에서 변경 중인 도메인의 행을 찾아 해당 도메인의 확인란을 선택합니다. 
    
    (아래로 스크롤해야 할 수 있습니다.) 
    
3. **Domain_name** 영역의 **dns 영역 편집기** 행에서 **dns 레코드 관리**를 선택 합니다.
    
4. On the **DNS Zone Editor** page, in the Add DNS Record area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (드롭다운 목록에서 **Type(종류)** 값을 선택합니다.) 
    
|||||
|:-----|:-----|:-----|:-----|
|**Host Record** <br/> |**TTL** <br/> |**종류** <br/> |**TXT Value** <br/> |
|@  <br/> |14400  <br/> |TXT  <br/> |MS=ms *XXXXXXXX* <br/> **참고:** 이 값은 예시입니다. 여기에는 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다. [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md) <br/> |

   
5. **레코드 추가**를 선택 합니다.
    
6. 방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.
    
도메인 등록 기관 사이트에서 레코드를 추가 했으므로 이제 Microsoft로 이동 하 여 레코드 검색을 요청 합니다.
  
Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.
  
1. Microsoft 관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동합니다.

    
2. **도메인** 페이지에서 확인 중인 도메인을 선택합니다. 
    
3. **설정** 페이지에서 **설정 시작**을 선택합니다.
    
4. **도메인 확인** 페이지에서 **확인**을 선택합니다.
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요. 
  
## <a name="change-your-domains-nameserver-ns-records"></a>도메인의 NS(이름 서버) 레코드 변경

Microsoft에서 도메인 설정을 완료 하려면 도메인 등록 기관에서 도메인의 NS 레코드를 기본 및 보조 이름 서버를 가리키도록 변경 합니다. 이렇게 하면 Microsoft에서 도메인의 DNS 레코드를 업데이트 하도록 설정 합니다. 전자 메일, 비즈니스용 Skype Online, 공개 웹 사이트가 사용자의 도메인을 사용하도록 모든 레코드가 자동으로 추가되고 모든 설정이 완료됩니다.
  
> [!CAUTION]
> Microsoft 이름 서버를 가리키도록 도메인의 NS 레코드를 변경 하면 현재 도메인에 연결 된 모든 서비스가 영향을 받습니다. 예를 들어 도메인으로 전송 되는 모든 전자 메일 (rob@ *your_domain*  )이 변경 된 후 Microsoft로 시작 됩니다. 
  
> [!IMPORTANT]
>  다음 절차에서는 목록에서 원치 않는 이름 서버를 삭제 하는 방법 및 올바른 이름 서버가 나열 되어 있지 않은 경우 추가 하는 방법을 보여 줍니다. >이 섹션의 단계를 완료 한 후에는 > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com와 같은 4 가지 이름 서버를 나열 해야 합니다. 
  
1. 시작하려면 [이 링크](https://my.bluehost.com/cgi/dm)를 사용하여 Bluehost의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.
    
2. **도메인** 페이지의 **domain_name** 영역에서 도메인에 대 한 확인란을 선택한 다음 **이름 서버**를 선택 합니다.
    
    ![Bluehost-BP-Redelegate-1-1](../../media/8f384386-197c-4272-9675-82037922dac4.png)
  
3. **Domain_name** 영역에서 **사용자 지정 이름 서버 사용**을 선택 합니다.
    
    ![Bluehost-BP-Redelegate-1-2](../../media/9fb47d21-c4ce-4eee-af90-c9569870a329.png)
  
4. 현재 표시된 페이지에 이름 서버가 이미 나열되어 있는지 여부에 따라 다음 두 가지 절차 중 하나를 계속합니다.
    
  - 이미 나열된 이름 서버가 **없으면**[나열된 이름 서버가 없으면](#if-there-are-no-nameservers-already-listed).
    
  - 이미 나열된 이름 서버가 **있으면**[이름 서버가 나열되어 있는 경우](#if-there-are-nameservers-already-listed).
    
### <a name="if-there-are-no-nameservers-already-listed"></a>나열된 이름 서버가 없으면

1. **사용자 지정 이름 서버 사용** 구역에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다. 
    
|||
|:-----|:-----|
|**첫 번째 빈 행** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**두 번째 빈 행** <br/> |ns2.bdm.microsoftonline.com  <br/> |
   
   ![Bluehost-BP-Redelegate-1-3-1](../../media/07b13d6d-a34e-45b5-afd5-48ebd4c1344f.png)
  
2. **행 추가**를 선택 합니다.
    
    ![Bluehost-BP-Redelegate-1-3-2](../../media/db34b632-1d10-44b7-aa1f-44bd27bf09e3.png)
  
3. 계속 **Use Custom Nameservers**(사용자 지정 이름 서버 사용) 구역에서 다음 표에 나온 첫 번째 행의 값을 새 빈 행에 입력하거나 복사하여 붙여넣습니다. 
    
|||
|:-----|:-----|
|**세 번째 빈 행** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**네 번째 빈 행** <br/> |ns4.bdm.microsoftonline.com  <br/> |
  
4. 네 번째 이름 서버 레코드를 추가 하려면 **행 추가** 를 다시 선택 하 고 위의 표에 있는 마지막 행의 값을 사용 하 여 레코드를 만듭니다. 
    
5. **이름 서버 설정 저장**을 선택 합니다.
    
    ![Bluehost-BP-Redelegate-1-4](../../media/b24a4cfd-924b-4b6d-ad3d-2dea148fc77f.png)
  
> [!NOTE]
> 이름 서버 레코드 업데이트가 인터넷의 DNS 시스템 전체에 업데이트되기까지 몇 시간이 걸릴 수 있습니다. 그러면 Microsoft 전자 메일 및 기타 서비스가 모두 도메인에서 작동 하도록 설정 됩니다. 
  
### <a name="if-there-are-nameservers-already-listed"></a>이름 서버가 나열되어 있는 경우

> [!CAUTION]
> Follow these steps only if you have existing nameservers other than the four correct nameservers. (즉, **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**또는 **ns4.bdm.microsoftonline.com**로 이름이 지정 *되지* 않은 현재 이름 서버 삭제 합니다.) 
  
1. 다른 이름 서버가 나열되어 있으면 하나씩 선택한 후 키보드의 **Delete** 키를 눌러 삭제합니다. 
    
    ![Bluehost-BP-Redelegate-1-5](../../media/d1051c43-f8ff-46d7-af26-3975d3f0f621.png)
  
2. 계속 **사용자 지정 이름 서버 사용** 구역에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다. 
    
|||
|:-----|:-----|
|**첫 번째 빈 행** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**두 번째 빈 행** <br/> |ns2.bdm.microsoftonline.com  <br/> |
   
   ![Bluehost-BP-Redelegate-1-3](../../media/1523debf-5eb0-4765-8e05-bcd56e375c20.png)
  
3. **행 추가**를 선택 합니다.
    
    ![Bluehost-BP-Redelegate-1-3-2](../../media/db34b632-1d10-44b7-aa1f-44bd27bf09e3.png)
  
4. 계속 **Use Custom Nameservers**(사용자 지정 이름 서버 사용) 구역에서 다음 표에 나온 첫 번째 행의 값을 새 빈 행에 입력하거나 복사하여 붙여넣습니다. 
    
|||
|:-----|:-----|
|**세 번째 빈 행** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**네 번째 빈 행** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Bluehost-BP-Redelegate-1-3-3](../../media/480b32bb-af27-40a5-90c5-5617ed02bb41.png)
  
5. 네 번째 이름 서버 레코드를 추가 하려면 **행 추가** 를 다시 선택 하 고 위의 표에 있는 마지막 행의 값을 사용 하 여 레코드를 만듭니다. 
    
6. **이름 서버 설정 저장**을 선택 합니다.
    
    ![Bluehost-BP-Redelegate-1-4](../../media/b24a4cfd-924b-4b6d-ad3d-2dea148fc77f.png)
  
> [!NOTE]
> 이름 서버 레코드 업데이트가 인터넷의 DNS 시스템 전체에 업데이트되기까지 몇 시간이 걸릴 수 있습니다. 그러면 Microsoft 전자 메일 및 기타 서비스가 모두 도메인에서 작동 하도록 설정 됩니다. 
  
