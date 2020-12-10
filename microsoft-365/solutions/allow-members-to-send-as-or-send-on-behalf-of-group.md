---
title: 구성원이 그룹으로 보내거나 그룹을 대신하여 보낼 수 있도록 허용
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
description: 구성원이 Microsoft 365 그룹으로 전자 메일을 보내거나 Microsoft 365 그룹을 대신하여 전자 메일을 보낼 수 있도록 허용하는 방법을 배워야 합니다.
ms.openlocfilehash: 2abf0668411ccd08db5bbd8408605dcd0aa2d832
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613575"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a>구성원이 그룹으로 보내거나 그룹을 대신하여 보낼 수 있도록 허용

다른 사람으로 보내기 또는 대신 보내기  권한이 부여된 Microsoft 365 그룹의 구성원은 그룹으로 또는 그룹을 대신하여 전자 메일을 보낼 수 있습니다.  이 문서에서는 관리자가 이러한 권한을 설정하는 방법에 대해 설명합니다.
  
예를 들어 Megan Bowen이 **교육** Microsoft 365 그룹의  일부이고 그룹에 대한 권한으로 보내기 권한을 가지는 경우 그룹으로  전자 메일을 보내는 경우 교육 그룹이 전자 메일을 보낸 것 같습니다. 
  
대신 **보내기 권한을** 사용하면 Microsoft 365 그룹을 대신하여 전자 메일을 보낼 수 있습니다. 예를 들어 Alex Wilber가 **마케팅** Microsoft 365 그룹의 일부로, 대신 보내기 권한을 가지고 그룹으로 전자 메일을 보내는 경우 이 전자 메일은 마케팅을 대신하여 **Alex Wilber가** 보낸 것 같습니다. 

> [!IMPORTANT]
> 특정 사용자에 대해  **다른** 사람으로 보내기 또는 대신 보내기 구성할 수 있지만 둘 다 구성할 수 없습니다. 두 가지를 모두 구성하는 경우 기본적으로 "다른 사람으로 **보내기"가 사용됩니다.**

> [!TIP]
> Outlook 및 웹용 Outlook을 사용하여 그룹에서 전자 메일을 보내는 방법에 대한 자세한 내용은 Microsoft 365 그룹 또는 [Microsoft 365](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) 그룹 대신 전자 메일 보내기를 참조하세요.
    
## <a name="allow-members-to-send-email-as-a-group"></a>구성원이 그룹으로 전자 메일을 보낼 수 있도록 허용

이 섹션에서는 사용자가 [Exchange](https://go.microsoft.com/fwlink/p/?linkid=2059104) Online의 EAC(Exchange 관리 센터)에서 그룹으로 전자 메일을 보낼 수 있도록 허용하는 방법에 대해 설명합니다.
  
1. Exchange 관리 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">센터에서</a>받는 사람 **그룹으로** \> **이동 합니다.**
    
2. 사용자가 **다른 사람으로** 보낼 수 있도록 허용할 그룹 편집 ![ ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 아이콘을 선택합니다.   
    
3. 그룹 **위임 선택.**
    
4. 다른 **사람으로** 보내기 섹션에서 그룹으로 보낼 사용자를 **+** 추가하는 기호를 선택합니다. 
    
    ![다른 사람으로 보내기 대화 상자 스크린샷](../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. 목록에서 사용자를 검색하거나 선택하기 위해 입력합니다. 확인을 **선택하고** **저장합니다.**
    
    ![목록에서 사용자를 검색하거나 선택할 입력](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a>구성원이 그룹을 대신하여 전자 메일을 보낼 수 있도록 허용

이 섹션에서는 사용자가 Exchange Online의 EAC(Exchange 관리 센터)에서 그룹을 대신하여 전자 메일을 보낼 수 있도록 허용하는 방법에 대해 설명합니다.
  
1. Exchange 관리 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">센터에서</a>받는 사람 **그룹으로** \> **이동 합니다.**
    
2. 사용자가 **다른 사람으로** 보낼 수 있도록 허용할 그룹에서 편집 그룹 ![ ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 아이콘을 선택합니다. 
    
3. 그룹 **위임 선택.**
    
4. 대신 보내기 섹션에서 그룹으로 보낼 사용자를 추가하려면 **+** 기호를 선택합니다. 
    
    ![대화 상자 대신 보내기 스크린샷](../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. 목록에서 사용자를 검색하거나 선택하기 위해 입력합니다. 확인을 **선택하고** **저장합니다.**
    
    ![목록에서 사용자를 검색하거나 선택할 입력](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a>관련 문서

[공동 작업 거버넌스 계획 단계별](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[공동 작업 거버넌스 계획 만들기](collaboration-governance-first.md)

[Microsoft 365 그룹에 대해 자세히 알아보기](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[Add-RecipientPermission](https://go.microsoft.com/fwlink/p/?LinkId=723960)

[Set-UnifiedGroup](https://go.microsoft.com/fwlink/p/?LinkId=616189)
