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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 832276bd-d024-47b6-a80a-a6b884907a5b
description: 'PowerShell을 사용하여 조직의 전체 또는 특정 사용자에 대해 클러터 기능을 사용하도록 설정하거나 사용하지 않도록 Exchange 방법을 학습합니다. '
ms.openlocfilehash: 055e02cd9a53dfcb8dd5bc3d3b7b601e3efe53ad
ms.sourcegitcommit: aebcdbef52e42f37492a7f780b8b9b2bc0998d5c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2021
ms.locfileid: "59774679"
---
# <a name="configure-clutter-for-your-organization"></a>조직에 대한 클러터 구성

> [!TIP]
> [포커스가 있는 받은 편지함이](../setup/configure-focused-inbox.md) 클러터를 대체합니다. 자세한 정보: 집중 받은 편지함 및 클러터에 대한 [계획에 대한 업데이트](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)
  
관리자는 관리 팀에서 클러터 기능을 관리해야 할 Microsoft 365. 조직의 사용자에 대해 클러터 기능을 설정/해제하려면 PowerShell을 사용하여 Exchange 합니다. (개인은 다음 지침에 따라 켜기/끄기: 에서 [클러터 끄기/켜기](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c)Outlook.
  
PowerShell 사용에 대한 자세한 내용은 [PowerShell을](/powershell/exchange/exchange-online-powershell) Exchange Online 커넥트 [Exchange Online PowerShell을](/powershell/exchange/connect-to-exchange-online-powershell) 사용하여 Exchange 참조합니다. PowerShell을 사용하여 서비스 관리자 역할에 Exchange 계정이 Exchange Online 필요합니다. 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a>PowerShell을 사용하여 Exchange 켜기

[Set-Clutter](/powershell/module/exchange/set-clutter) cmdlet을 실행하여 사서함에 대해 클러터를 수동으로 사용하도록 설정할 수 있습니다. [Get-Clutter](/powershell/module/exchange/get-clutter) cmdlet을 실행하여 조직의 사서함에 대한 클러터 설정을 볼 수도 있습니다. 
  
Allie Bellew라는 단일 사용자에 대해 클러터 켜기
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a>PowerShell을 사용하여 Exchange 끄기

[Set-Clutter](/powershell/module/exchange/set-clutter) cmdlet을 실행하여 사서함에 대해 수동으로 클러터를 사용하지 않도록 설정할 수 있습니다. [Get-Clutter](/powershell/module/exchange/get-clutter) cmdlet을 실행하여 조직의 사서함에 대한 클러터 설정을 볼 수도 있습니다.  
  
Allie Bellew라는 단일 사용자에 대해 클러터를 끄는 경우:
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

PowerShell을 사용하여 사용자를 대량으로 만드는 경우 각 사용자의 사서함에 [대해 Set-Clutter를](/powershell/module/exchange/set-clutter) 실행하여 클러터를 관리해야 합니다. 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a>클러터 켜기/끄기 스위치는 웹용 Outlook?
<a name="bkmk_onoff"> </a>

관리자는 PowerShell을 사용하여 클러터를 다시 Exchange 있습니다. 이 완료되면 집중 받은 편지함이 꺼지며 클러터가 다시 활성화됩니다. 
  
 **구독과 함께 웹용 Outlook 사용하는 Microsoft 365 Business Premium:**
  
- 사용자가 현재 클러터를 사용하도록 설정한 경우: 
    
  - 클러터 설정 표시
    
- 사용자가 현재 중점 받은 편지함을 사용하도록 설정한 경우: 
    
  - 클러터 설정이 나타나지 않습니다.
    
- 클러터나 포커스가 있는 받은 편지함이 모두 사용하도록 설정되지 않았습니다. 
    
  - 클러터와 포커스가 있는 받은 편지함은 모두 사용자의 메일 메시지에 옵션으로 설정
    
 **Outlook.com을 사용하는 경우:**
  
- 사용자가 현재 클러터를 사용하도록 설정한 경우: 
    
  - 클러터 설정 표시
    
- 사용자가 현재 중점 받은 편지함을 사용하도록 설정한 경우: 
    
  - 클러터 설정이 나타나지 않습니다.
    
- 클러터나 포커스가 있는 받은 편지함이 모두 사용하도록 설정되지 않았습니다. 
    
  - 클러터와 포커스가 있는 받은 편지함은 모두 사용자의 메일 메시지에 옵션으로 설정
    
- 사용자가 과거의 특정 시점에서 중점 받은 편지함을 사용하도록 설정한 경우:
    
  - 클러터 설정이 나타나지 않습니다.
    
    그렇지 않으면 
    
  - 클러터 설정이 나타납니다.
    
## <a name="related-content"></a>관련 콘텐츠

[낮은 우선 순위의](https://support.microsoft.com/office/7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0) 메시지를 낮은 우선 순위로 정렬하는 데 낮은 우선 순위 Outlook(문서)\
[낮은 우선 순위의 메시지를 OWA에서](https://support.microsoft.com/office/fe4d64ca-bf73-48f1-91b4-9a659e008bce) 정렬하는 낮은 우선 순위 메일(문서)\
[클러터를 끄는](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c) Outlook(문서)
