---
title: AWS(Amazon Web Services)에서 이름 서버 변경
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
ms.assetid: 0ddbe33c-81ea-4c02-8db9-e71d3810c0ec
description: 'AWS(Amazon Web Services)에서 DNS 레코드를 관리하기 위해 Microsoft를 설정하는 방법을 알아보십시오. '
ms.openlocfilehash: 4700557c40973ab051cced81c129197a826964ab
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658455"
---
# <a name="change-nameservers-to-set-up-microsoft-with-amazon-web-services-aws"></a>AWS(Amazon Web Services)에서 이름 서버 변경

 원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.yml)** 하세요. 
  
Microsoft에서 DNS 레코드를 관리하게 하려는 경우 다음 지침을 따릅니다. 원하는 경우 [AWS에서 모든 Microsoft DNS 레코드를 관리할 수](create-dns-records-at-aws.md)있습니다.
  
    
## <a name="add-a-txt-record-for-verification"></a>확인을 위해 TXT 레코드 추가

Microsoft에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft에 도메인을 소유하고 있음을 증명할 수 있습니다.
  
> [!NOTE]
> 이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다. 
  
1. 시작하려면 [이 링크](https://console.aws.amazon.com/route53/home)를 사용하여 AWS의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.
    
2. 리소스 **페이지에서** 호스팅된 **영역 선택**
    
3. 호스팅된 **영역** 페이지의 도메인 **이름** 열에서 편집할 도메인의 이름을 선택합니다. 
    
4. 레코드 **집합 만들기를 선택합니다.**
    
5. In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** and **Routing Policy** values from the drop-down lists.) 
    
    > [!TIP]
    > The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually. 
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**이름** <br/> |**Type(종류)** <br/> |**별칭** <br/> |**TTL(초)** <br/> |**값** <br/> |**라우팅 정책** <br/> |
|(이 필드는 비워 두기)  <br/> |TXT - Text  <br/> |아니요  <br/> |300  <br/> |MS=ms *XXXXXXXX* <br/> **참고:** 이 값은 예시입니다. 여기에는 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다. [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)  <br/>  |Simple(단순형) <br/> |
   
6. **만들기** 를 선택합니다.
    
7. 방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.
    
이제 도메인 등록 기관의 사이트에 레코드를 추가한 후 Microsoft로 돌아가서 레코드에 대한 검색을 요청합니다.
  
Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.
  
1. Microsoft 관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동합니다.

    
2. **도메인** 페이지에서 확인 중인 도메인을 선택합니다. 
    
3. **설정** 페이지에서 **설정 시작** 을 선택합니다.
    
4. **도메인 확인** 페이지에서 **확인** 을 선택합니다.
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요. 
  
## <a name="change-your-domains-nameserver-ns-records"></a>도메인의 NS(이름 서버) 레코드 변경

Microsoft에서 도메인 설정을 완료하려면 도메인 등록 기관에서 Microsoft 기본 및 보조 이름 서버를 지점으로 도메인의 NS 레코드를 변경합니다. 이렇게 하면 도메인의 DNS 레코드가 자동으로 업데이트됩니다. 전자 메일, 비즈니스용 Skype Online, 공개 웹 사이트가 사용자의 도메인을 사용하도록 모든 레코드가 자동으로 추가되고 모든 설정이 완료됩니다.
  
> [!CAUTION]
> Microsoft 이름 서버를 설정하기 위해 도메인의 NS 레코드를 변경하면 현재 도메인과 연결된 모든 서비스가 영향을 받는 것입니다. 예를 들어 도메인으로 전송된 모든 전자 메일(예: rob@ *your_domain*  .com)은 이 변경 후에 Microsoft로 전송됩니다. 
  
> [!IMPORTANT]
>  다음 절차에서는 목록에서 원치 않는 다른 이름 서스터를 삭제하는 방법과 올바른 이름servers가 목록에 없는 경우 추가하는 방법도 보여 주며, > 이 섹션의 단계를 완료하면 다음 네 가지 이름만 나열됩니다. > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com 
  
1. 시작하려면 [이 링크](https://console.aws.amazon.com/route53/home)를 사용하여 AWS의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.
    
2. 리소스 **페이지에서** 호스팅된 **영역 선택**
    
3. 호스팅된 **영역** 페이지의 도메인 **이름** 열에서 편집할 도메인의 이름을 선택합니다. 
    
4. **이름 서버** 레코드 집합을 선택합니다. 
    
    ![Select the recordset](../../media/24e618e4-0a16-43a2-9886-f4f5dac79374.png)
  
5. **NS - Name server(NS - 이름 서버)** 레코드 집합의 **Value(값)** 상자에서 모든 이름 서버를 선택한 다음 키보드의 **Delete** 키를 눌러 모든 이름 서버를 삭제합니다. 
    
    > [!CAUTION]
    > Follow these steps only if you have existing nameservers other than the four correct nameservers. 즉, 이름이 **ns1.bdm.microsoftonline.com,** ns2.bdm.microsoftonline.com, ns3.bdm.microsoftonline.com  또는 ns4.bdm.microsoftonline.com **이름** 없는 모든 현재 이름 ns4.bdm.microsoftonline.com 삭제합니다. 
  
    ![Select and delete all of the nameservers in the Value box](../../media/ecf1e897-fa7d-4abc-b00b-bf55b8ed2139.png)
  
6. **TTL(초):** 영역에서 **1h(1시간)를** 선택합니다. 
    
    ![1시간 동안 1H 선택](../../media/c70070e1-4bde-41a7-b271-9d22c475edf6.png)
  
7. 계속해서 **NS - Name server**(NS - 이름 서버) 레코드 집합의 **Value**(값) 상자에 다음 표의 **First line**(첫 줄)에 있는 값을 입력하거나 복사하여 붙여넣고 키보드의 **Enter** 키를 누른 후 다음 **line**(줄)에 있는 값을 입력하거나 복사하여 붙여넣습니다. 
    
    > [!IMPORTANT]
    > 이름 서버 값은 다음 그림과 같이 *Value(값)* 상자 안의 각기 다른 줄에  **있어야 합니다**  . 
  
|||
|:-----|:-----|
|**첫 줄** <br/> |ns1.bdm.microsoftonline.com.  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |
|**둘째 줄** <br/> |ns2.bdm.microsoftonline.com.  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |
|**셋째 줄** <br/> |ns3.bdm.microsoftonline.com.  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |
|**넷째 줄** <br/> |ns4.bdm.microsoftonline.com.  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |
   
   ![값 상자에 첫 줄 값을 입력하거나 붙여넣습니다.](../../media/b63f41e0-51ef-4ab2-a4b8-ee7380e5ab35.png)
  
8. 레코드 **저장 집합을 선택합니다.**
    
    ![레코드 저장 집합 선택](../../media/ab3c0558-bb7c-41e4-871e-ea82f1553476.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. 그런 다음 Microsoft 전자 메일 및 기타 서비스가 모두 도메인에서 작동하게 설정됩니다. 
