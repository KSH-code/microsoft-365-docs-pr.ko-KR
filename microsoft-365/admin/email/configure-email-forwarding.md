---
title: Office 365에서 전자 메일 전달 구성
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: Office365을 사용 하 여 하나 이상의 전자 메일 계정으로 전자 메일을 전달 하도록 설정 합니다.
ms.openlocfilehash: b6ad4032748c35db8e8c18b609915aef4231cb6c
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42255275"
---
# <a name="configure-email-forwarding-in-office-365"></a>Office 365에서 전자 메일 전달 구성
  
Office 365 조직의 관리자는 사용자 사서함에 대 한 전자 메일 전달을 설정 하기 위한 회사 요구 사항이 있을 수 있습니다. 전자 메일 전달을 사용 하면 사용자의 사서함에 전송 된 전자 메일 메시지를 조직의 내부 또는 외부에 있는 다른 사용자의 사서함으로 전달할 수 있습니다.

  
## <a name="configure-email-forwarding"></a>전자 메일 전달 구성

 전자 메일 전달을 설정 하기 전에 다음 사항에 유의 하세요. 

- 전자 메일 전달을 설정한 후에는 *보낸* 사람 사서함으로 전송 되는 **새** 전자 메일만 구성 됩니다. 
    
- 전자 메일을 전달 하려면 *보낸 사람* 계정에 라이선스가 있어야 합니다. 사용자가 조직을 떠난 경우 전자 메일 전달을 설정 하는 경우 [사서함을 공유 사서함으로 변환](convert-user-mailbox-to-shared-mailbox.md)하는 옵션이 있습니다. 여러 사용자가 액세스할 수 있는 방식입니다. 그러나 공유 사서함은 50GB를 초과할 수 없습니다. 
    
이러한 단계를 수행 하려면 Exchange 관리자 이거나 Office 365의 전역 관리자 여야 합니다. 자세한 내용은 [관리 역할에 대 한](../add-users/about-admin-roles.md)항목을 참조 하십시오.

::: moniker range="o365-worldwide"

> [!NOTE]
> 새로운 Microsoft 365 관리 센터를 사용하지 않는 경우 홈페이지 상단에 있는 **새 관리 센터 시도** 토글을 선택하여 켤 수 있습니다.

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다..
    
2. 전자 메일을 전달 하려는 사용자의 이름을 선택 하 여 속성 페이지를 엽니다. 
 
3. **메일** 탭에서 **전자 메일 전달 관리**를 선택 합니다. 
  
4. 전자 메일 전달 페이지에서 **이 사서함에 보낸 모든 전자 메일**전달을 선택 하 고 전달 주소를 입력 한 다음 전달 된 전자 메일의 복사본을 유지할지 여부를 선택 합니다. 이 옵션이 표시 되지 않으면 라이선스가 사용자 계정에 할당 되었는지 확인 합니다. **변경 내용 저장**을 선택 합니다.
    
    **여러 전자 메일 주소로 착신 전환**하려면 사용자에 게 Outlook에서 주소로 전달할 규칙을 설정 하도록 요청할 수 있습니다. 자세한 내용은 [규칙을 사용 하 여 메시지 자동 전달을](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746)참조 하십시오. 
    
     또는 관리 센터에서 [메일 그룹을 만들고](../setup/create-distribution-lists.md) [여기에 주소를 추가한](add-user-or-contact-to-distribution-list.md)다음이 문서의 지침을 사용 하 여 DL을 가리키도록 착신 전환을 설정 합니다.
    
5. 전달 하는 전자 메일 사용자의 계정을 삭제 하지 마세요, 아니면 해당 라이선스를 제거 합니다.  이렇게 하면 전자 메일 전달이 중지 됩니다. 

::: moniker-end

::: moniker range="o365-germany"
    
 1.   관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다.. 
    
2. 전자 메일을 전달 하려는 사용자의 이름을 선택 하 여 속성 페이지를 엽니다. 

3. **메일 설정을**확장 하 고 **전자 메일 전달** 섹션에서 **편집**을 선택 합니다.

4. 전자 메일 전달 페이지에서 켜기/ **끄기를 설정**하 고 전달 주소를 입력 한 다음 전달 된 전자 메일의 복사본을 유지할지 여부를 선택 합니다. 이 옵션이 표시 되지 않으면 라이선스가 사용자 계정에 할당 되었는지 확인 합니다. **저장**을 선택합니다.
    
    **여러 전자 메일 주소로 착신 전환**하려면 사용자에 게 Outlook에서 주소로 전달할 규칙을 설정 하도록 요청할 수 있습니다. 자세한 내용은 [규칙을 사용 하 여 메시지 자동 전달을](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746)참조 하십시오. 
    
     또는 관리 센터에서 [메일 그룹을 만들고](../setup/create-distribution-lists.md) [여기에 주소를 추가한](add-user-or-contact-to-distribution-list.md)다음이 문서의 지침을 사용 하 여 DL을 가리키도록 착신 전환을 설정 합니다.
    
5. 전달 하는 전자 메일 사용자의 계정을 삭제 하지 마세요, 아니면 해당 라이선스를 제거 합니다.  이렇게 하면 전자 메일 전달이 중지 됩니다.    

::: moniker-end

::: moniker range="o365-21vianet"

 1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다.. 
    
2. 전자 메일을 전달 하려는 사용자의 이름을 선택 하 여 속성 페이지를 엽니다. 

3. **메일 설정을**확장 하 고 **전자 메일 전달** 섹션에서 **편집**을 선택 합니다.

4. 전자 메일 전달 페이지에서 켜기/ **끄기를 설정**하 고 전달 주소를 입력 한 다음 전달 된 전자 메일의 복사본을 유지할지 여부를 선택 합니다. 이 옵션이 표시 되지 않으면 라이선스가 사용자 계정에 할당 되었는지 확인 합니다. **저장**을 선택합니다.
    
    **여러 전자 메일 주소로 착신 전환**하려면 사용자에 게 Outlook에서 주소로 전달할 규칙을 설정 하도록 요청할 수 있습니다. 자세한 내용은 [규칙을 사용 하 여 메시지 자동 전달을](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746)참조 하십시오. 
    
     또는 관리 센터에서 [메일 그룹을 만들고](../setup/create-distribution-lists.md) [여기에 주소를 추가한](add-user-or-contact-to-distribution-list.md)다음이 문서의 지침을 사용 하 여 DL을 가리키도록 착신 전환을 설정 합니다.
    
5. 전달 하는 전자 메일 사용자의 계정을 삭제 하지 마세요, 아니면 해당 라이선스를 제거 합니다.  이렇게 하면 전자 메일 전달이 중지 됩니다. 

::: moniker-end 
