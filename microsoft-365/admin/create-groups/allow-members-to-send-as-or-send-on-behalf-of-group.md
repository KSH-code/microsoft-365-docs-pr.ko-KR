---
title: 구성원이 그룹을 대신 하거나 다른 사람 이름으로 보내기 허용
ms.reviewer: arvaradh
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
description: 구성원이 office 365 그룹을 대신 하 여 전자 메일을 보내거나 office 365 그룹을 사용 하 여 전자 메일을 보내는 것을 허용 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 0179dbd2e3093ce80929f6c5f9e689aece845a40
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633786"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a>구성원이 그룹을 대신 하거나 다른 사람 이름으로 보내기 허용

**다른 사람 이름으로 보내기** 또는 **대신 보내기** 권한을 부여 받은 Office 365 그룹의 구성원은 이제 전자 메일을 그룹으로 보내거나 그룹을 대신 하 여 보낼 수 있습니다. 이 항목에서는 관리자가 이러한 사용 권한을 설정 하는 방법에 대해 설명 합니다.
  
예를 들어 Megan Bowen가 **트레이닝** Office 365 그룹에 속하며 그룹에 **다른 사람 이름으로 보내기** 권한이 있는 경우 전자 메일을 그룹으로 보내면 전자 메일을 보낸 **교육** 그룹과 같이 표시 됩니다. 
  
**대신 보내기** 권한을 사용 하면 사용자가 Office 365 그룹을 대신 하 여 전자 메일을 보낼 수 있습니다. 예를 들어 Alex Wilber가 **marketing** Office 365 그룹에 속해 있고 **대신 보내기** 권한을가지고 있고 전자 메일을 그룹으로 보내는 경우 전자 메일은 **마케팅을 대신 하 여 Alex Wilber에서**보낸 것 처럼 보입니다.

> [!IMPORTANT]
> 특정 사용자에 대해 **다른 사람 이름으로 보내기** 또는 **대신 보내기** 를 구성할 수 있습니다. 둘 다를 구성 하는 경우 기본적 **으로로 보내기가**설정 됩니다.

> [!TIP]
> Outlook 및 웹용 Outlook을 사용 하 여 그룹에서 전자 메일을 보내는 방법에 대 한 자세한 내용은 [Office 365 그룹을 통한 전자 메일 보내기 또는 전송](https://support.office.com/article/0f4964af-aec6-484b-a65c-0434df8cdb6b.aspx) 의 단계를 참조 하세요.
    
## <a name="allow-members-to-send-email-as-a-group"></a>구성원이 그룹으로 전자 메일을 보낼 수 있도록 허용

이 섹션에서는 사용자가 Exchange Online의 EAC ( [exchange 관리 센터](https://go.microsoft.com/fwlink/p/?linkid=2059104) )에서 그룹으로 전자 메일을 보내도록 허용 하는 방법에 대해 설명 합니다.
  
1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 관리 센터</a>에서 **받는 사람** \> **그룹**으로 이동 합니다.
    
2. 사용자 **Edit**![에 게 보낼 수](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 있도록 허용할 그룹에서 그룹 편집 아이콘 편집을 선택 합니다.   
    
3. **그룹 위임을**선택 합니다.
    
4. **다른 이름으로 보내기** 섹션에서 그룹으로 **+** 보낼 사용자를 추가 하려면 서명을 선택 합니다. 
    
    ![+ 기호를 선택 하 여 Office 365 그룹으로 보낼 사용자를 추가 합니다.](../../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. 목록에서 사용자를 검색 하거나 선택 하려면 입력 합니다. **확인** 및 **저장**을 선택 합니다.
    
    ![목록에서 사용자를 검색 하거나 선택 하려면 입력 합니다.](../../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a>구성원이 그룹을 대신 하 여 전자 메일을 보낼 수 있도록 허용

이 섹션에서는 사용자가 Exchange Online의 EAC (Exchange 관리 센터)에서 그룹을 대신 하 여 전자 메일을 보내도록 허용 하는 방법에 대해 설명 합니다.
  
1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 관리 센터</a>에서 **받는 사람** \> **그룹**으로 이동 합니다.
    
2. 사용자에 게 보낼 수](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 있도록 허용할 그룹에서 ![ **그룹 편집 아이콘을 선택 합니다** . 
    
3. **그룹 위임을**선택 합니다.
    
4. 대신 보내기 섹션에서 그룹으로 보낼 사용자를 **+** 추가 하려면 서명을 선택 합니다. 
    
    ![+ 기호를 선택 하 여 Office 365 그룹으로 보낼 사용자를 추가 합니다.](../../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. 목록에서 사용자를 검색 하거나 선택 하려면 입력 합니다. **확인** 및 **저장**을 선택 합니다.
    
    ![목록에서 사용자를 검색 하거나 선택 하려면 입력 합니다.](../../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a>관련 문서

[Office 365 그룹에 대한 자세한 정보](https://support.office.com/article/3f780e8e-61aa-4287-830d-ff6209cbc192.aspx)

[Add-recipientpermission 추가](https://go.microsoft.com/fwlink/p/?LinkId=723960)

[Remove-unifiedgroup](https://go.microsoft.com/fwlink/p/?LinkId=616189)
