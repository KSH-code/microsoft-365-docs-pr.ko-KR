---
title: 조직에 대한 클러터 구성
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 832276bd-d024-47b6-a80a-a6b884907a5b
description: 'Exchange PowerShell을 사용하여 조직의 모든 또는 특정 사용자에 대해 클러터 기능을 사용하도록 설정하거나 사용하지 않도록 설정하는 방법을 학습합니다. '
ms.openlocfilehash: 67267b0865dfcfd6c0ba66d59ce1d0d111d59325
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780280"
---
# <a name="configure-clutter-for-your-organization"></a>조직에 대한 클러터 구성

> [!TIP]
> [포커스가 있는 받은 편지함은](../setup/configure-focused-inbox.md) 클러터를 대체합니다. 자세한 정보: 집중 받은 편지함 및 클러터에 대한 [계획에 대한 업데이트](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)
  
관리자는 Microsoft 365의 클러터 기능을 관리해야 할 수 있습니다. 조직의 사용자에 대해 클러터 기능을 설정/해제하려면 Exchange PowerShell을 사용해야 합니다. (개인은 다음 지침에 따라 이를 켜고 끄기: [Outlook에서 클러터를 끄고 켜기.](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c)
  
Exchange [Online에서 PowerShell을](https://go.microsoft.com/fwlink/?LinkID=402831) 사용하고 [Exchange Online PowerShell에](https://go.microsoft.com/fwlink/?LinkID=722415) 연결하여 Exchange PowerShell 사용에 대한 자세한 내용을 참조하세요. 적어도 Exchange 서비스 관리자 역할과 PowerShell을 사용하여 Exchange Online에 연결하는 기능을 제공하는 계정이 필요합니다. 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a>Exchange PowerShell을 사용하여 클러터 켜기

[Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) cmdlet을 실행하여 사서함에 대해 클러터를 수동으로 사용하도록 설정할 수 있습니다. [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759) cmdlet을 실행하여 조직의 사서함에 대한 클러터 설정을 볼 수도 있습니다. 
  
Allie Bellew라는 단일 사용자에 대해 클러터 켜기
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a>Exchange PowerShell을 사용하여 클러터 끄기

[Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) cmdlet을 실행하여 사서함에 대해 수동으로 클러터를 사용하지 않도록 설정할 수 있습니다. [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759) cmdlet을 실행하여 조직의 사서함에 대한 클러터 설정을 볼 수도 있습니다.  
  
Allie Bellew라는 단일 사용자에 대한 클러터를 끄는 경우:
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

PowerShell을 사용하여 사용자를 대량으로 만드는 경우 각 사용자의 사서함에 [대해 Set-Clutter를](https://go.microsoft.com/fwlink/?LinkID=834446) 실행하여 클러터를 관리해야 합니다. 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a>클러터 켜기/끄기 스위치는 웹용 Outlook의 사용자에게 언제 표시하나요?
<a name="bkmk_onoff"> </a>

관리자는 Exchange PowerShell을 사용하여 클러터를 다시 사용하도록 설정할 수 있습니다. 이 완료되면 포커스가 있는 받은 편지함이 꺼지며 클러터가 다시 활성화됩니다. 
  
 **웹용 Outlook을 Microsoft 365 Business Premium 구독과 함께 사용하는 경우:**
  
- 사용자가 현재 클러터를 사용하도록 설정한 경우: 
    
  - 클러터 설정 표시
    
- 사용자가 현재 중점 받은 편지함을 사용하도록 설정한 경우: 
    
  - 클러터 설정이 나타나지 않습니다.
    
- 클러터나 포커스가 있는 받은 편지함을 모두 사용할 수 있는 경우: 
    
  - 클러터와 포커스가 있는 받은 편지함이 사용자의 메일 설정에 옵션으로 표시됩니다.
    
 **다음을 사용하는 Outlook.com.**
  
- 사용자가 현재 클러터를 사용하도록 설정한 경우: 
    
  - 클러터 설정 표시
    
- 사용자가 현재 중점 받은 편지함을 사용하도록 설정한 경우: 
    
  - 클러터 설정이 나타나지 않습니다.
    
- 클러터나 포커스가 있는 받은 편지함을 모두 사용할 수 있는 경우: 
    
  - 클러터와 포커스가 있는 받은 편지함이 사용자의 메일 설정에 옵션으로 표시됩니다.
    
- 사용자가 과거에 특정 시점에 중점 받은 편지함을 사용하도록 설정한 경우:
    
  - 클러터 설정이 나타나지 않습니다.
    
    그렇지 않으면 
    
  - 클러터 설정이 나타납니다.
    
## <a name="related-articles"></a>관련 문서
<a name="bkmk_onoff"> </a>

[낮은 우선 순위의 메시지를 Outlook에서 정렬하는 낮은 우선 순위 메일 사용](https://support.microsoft.com/office/7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0)
    
[낮은 우선 순위 메시지를 OWA에서 정렬하는 낮은 우선 순위 메일 사용](https://support.microsoft.com/office/fe4d64ca-bf73-48f1-91b4-9a659e008bce)
    
[Outlook에서 클러터 끄기](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c)
    

