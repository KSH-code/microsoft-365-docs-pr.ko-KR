---
title: 조직에 대 한 복잡 한 구성
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 832276bd-d024-47b6-a80a-a6b884907a5b
description: 'Exchange PowerShell을 사용 하 여 조직의 모든 또는 특정 사용자에 대해 낮은 우선 순위 기능을 사용 하거나 사용 하지 않도록 설정 하는 방법을 알아봅니다. '
ms.openlocfilehash: 65aa614095ecbebaad3d7eb38af1e74166ce20ac
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42255286"
---
# <a name="configure-clutter-for-your-organization"></a>조직에 대 한 복잡 한 구성

> [!TIP]
> [중요 받은 편지함](../setup/configure-focused-inbox.md) 에서 낮은 우선 순위를 대체 합니다. 자세한 내용은 [중요 받은 편지함에 대 한 업데이트 및 낮은 계획에 대 한 요금제](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448) 를 확인 하세요.
  
관리자는 Office 365에서 낮은 우선 순위 기능을 관리 해야 할 수 있습니다. 조직의 사용자에 대해 낮은 우선 순위 기능을 설정/해제 하려면 Exchange PowerShell을 사용 해야 합니다. 사용자는 다음 [지침을 사용](https://support.office.com/article/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c.aspx)하 여이 기능을 설정/해제할 수 있습니다. 
  
Exchange PowerShell 사용에 대 한 자세한 내용은 [Exchange online에서 PowerShell을 사용](https://go.microsoft.com/fwlink/?LinkID=402831) 하 고 Exchange [Online PowerShell에 연결](https://go.microsoft.com/fwlink/?LinkID=722415) 을 참조 하세요. 적어도 Exchange 서비스 관리자 역할을 가진 계정 및 PowerShell을 사용 하 여 Exchange Online에 연결 하는 기능이 있어야 합니다. 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a>Exchange PowerShell을 사용 하 여 정리 기능 설정

[낮은 우선 순위](https://go.microsoft.com/fwlink/?LinkID=834446) cmdlet을 실행 하 여 사서함에 대해 복잡 한 방법을 수동으로 설정할 수 있습니다. [낮은 우선 순위](https://go.microsoft.com/fwlink/?LinkID=834759) cmdlet을 실행 하 여 조직의 사서함에 대 한 낮은 수준의 설정을 볼 수도 있습니다. 
  
Allie 라는 단일 사용자에 대해 정리 기능을 사용 하지 않습니다.
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a>Exchange PowerShell을 사용 하 여 정리 기능 해제

[낮은](https://go.microsoft.com/fwlink/?LinkID=834446) 우선 순위 cmdlet을 실행 하 여 사서함에 대해 복잡 한 방법을 수동으로 사용 하지 않도록 설정할 수 있습니다. [낮은 우선 순위](https://go.microsoft.com/fwlink/?LinkID=834759) cmdlet을 실행 하 여 조직의 사서함에 대 한 **낮은** 수준의 설정을 볼 수도 있습니다. 
  
Allie 라는 단일 사용자에 대해 혼란을 끕니다.
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

PowerShell을 사용 하 여 사용자를 대량으로 만드는 경우에는 각 사용자의 사서함에 대해 [설정 된 복잡 한 설정을](https://go.microsoft.com/fwlink/?LinkID=834446) 실행 하 여 혼란을 관리 해야 합니다. 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a>웹에서 Outlook의 사용자에 게 간편 하 게 설정/해제 스위치가 표시 되는 경우
<a name="bkmk_onoff"> </a>

관리자는 Exchange PowerShell을 사용 하 여 혼란을 다시 사용 하도록 설정할 수 있습니다. 이 작업이 완료 되 면 중요 받은 편지함이 꺼지고 깔끔하게 다시 활성화 됩니다. 
  
 **Office 365 비즈니스 구독을 사용 하 여 웹에서 Outlook을 사용 하는 경우 다음을 수행 합니다.**
  
- 현재 사용자가 낮은 사용을 설정한 경우: 
    
  - 낮은 우선 순위 설정 표시
    
- 사용자에 게 현재 중요 받은 편지함을 사용 하도록 설정한 경우: 
    
  - 낮은 우선 순위 설정이 나타나지 않음
    
- 불필요 한 받은 편지함이 사용 하도록 설정 되어 있지 않은 경우: 
    
  - 사용자의 메일 설정에서 낮은 우선 순위 및 중요 받은 편지함 모두 옵션으로 표시 됩니다.
    
 **Outlook.com을 사용 하는 경우:**
  
- 현재 사용자가 낮은 사용을 설정한 경우: 
    
  - 낮은 우선 순위 설정 표시
    
- 사용자에 게 현재 중요 받은 편지함을 사용 하도록 설정한 경우: 
    
  - 낮은 우선 순위 설정이 나타나지 않음
    
- 불필요 한 받은 편지함이 사용 하도록 설정 되어 있지 않은 경우: 
    
  - 사용자의 메일 설정에서 낮은 우선 순위 및 중요 받은 편지함 모두 옵션으로 표시 됩니다.
    
- 사용자가 이전의 특정 시점에 중요 받은 편지함을 사용 하도록 설정한 경우:
    
  - 낮은 우선 순위 설정이 나타나지 않습니다.
    
    방법 
    
  - 낮은 설정이 표시 됩니다.
    
## <a name="related-articles"></a>관련 문서
<a name="bkmk_onoff"> </a>

[간단 하 게 Outlook에서 낮은 우선 순위 메시지 정렬](https://support.office.com/article/7755ebf5-4585-469b-b1ab-8b12425c6b6b.aspx)
    
[간단 하 게 OWA에서 낮은 우선 순위의 메시지 정렬](https://support.office.com/article/fe4d64ca-bf73-48f1-91b4-9a659e008bce.aspx)
    
[Outlook에서 혼란을 끕니다.](https://support.office.com/article/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c.aspx)
    

