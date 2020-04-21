---
title: 도메인 제거
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f09696b2-8c29-4588-a08b-b333da19810c
description: Microsoft 365에서 이전 도메인을 제거 하 고 사용자 및 그룹을 다른 도메인으로 이동 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 21b2b17e5cab022f67c71c0d3858f8a03b45899b
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43628437"
---
# <a name="remove-a-domain"></a>도메인 제거

참가자: [![Peter Baumgartner](../../media/e70dc696-c5f8-4717-a48b-9087431503e7.png)](https://go.microsoft.com/fwlink/p/?linkid=847121)
  
 **원하는 정보는 찾지 못한 경우 [도메인 질문과 대답을 확인](../setup/domains-faq.md)** 하세요. 
  
다른 Microsoft 365 구독 계획에 추가 하려고 하기 때문에 도메인을 제거 하 고 계십니까? 아니면 단지 구독을 취소하고 싶으신가요? [ 또는 구독을 변경 ](../../commerce/subscriptions/switch-to-a-different-plan.md)하거나 [구독을 취소](../../commerce/subscriptions/cancel-your-subscription.md)할 수 있습니다.
  
### <a name="step-1-move-users-to-another-domain"></a>1 단계: 사용자를 다른 도메인으로 이동

#### <a name="move-users"></a>사용자 이동

::: moniker range="o365-worldwide"

> [!NOTE]
> 새로운 Microsoft 365 관리 센터를 사용하지 않는 경우 홈페이지 상단에 있는 **새 관리 센터 시도** 토글을 선택하여 켤 수 있습니다.

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">관리 센터로</a>이동 합니다.

2. **사용자** > **활성 사용자**를 선택 합니다.

3. 이동 하려는 모든 사용자의 이름 옆에 있는 상자를 선택 합니다.

4. 페이지 맨 위에 있는 **기타 옵션** (**...**)을 선택 하 고 **도메인 변경을**선택 합니다.

5. **도메인 변경** 창에서 다른 도메인을 선택 합니다.

현재 제거 중인 도메인에 있는 경우 직접 이 작업을 해야 합니다. 사용자 계정의 도메인을 편집하는 경우 계속하려면 로그아웃한 후 선택한 새 도메인을 사용하여 다시 로그인해야 합니다.

::: moniker-end

::: moniker range="o365-germany"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">관리 센터로</a>이동 합니다.  

2. **사용자** > **활성 사용자**를 선택 합니다.

3. 이동 하려는 모든 사용자의 이름 옆에 있는 상자를 선택 합니다.

4. 페이지 맨 위에서 **기타** > **도메인 편집**을 선택 합니다.

5. **도메인 편집** 창에서 다른 도메인을 선택 합니다.
  
현재 제거 중인 도메인에 있는 경우 직접 이 작업을 해야 합니다. 사용자 계정의 도메인을 편집하는 경우 계속하려면 로그아웃한 후 선택한 새 도메인을 사용하여 다시 로그인해야 합니다.

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">관리 센터로</a>이동 합니다.  

2. **사용자** > **활성 사용자**를 선택 합니다.

3. 이동 하려는 모든 사용자의 이름 옆에 있는 상자를 선택 합니다.

4. 페이지 맨 위에서 **기타** > **도메인 편집**을 선택 합니다.

5. **도메인 편집** 창에서 다른 도메인을 선택 합니다.
  
현재 제거 중인 도메인에 있는 경우 직접 이 작업을 해야 합니다. 사용자 계정의 도메인을 편집하는 경우 계속하려면 로그아웃한 후 선택한 새 도메인을 사용하여 다시 로그인해야 합니다.

::: moniker-end

#### <a name="move-yourself"></a>직접 이동

::: moniker range="o365-worldwide"

> [!NOTE]
> 새로운 Microsoft 365 관리 센터를 사용하지 않는 경우 홈페이지 상단에 있는 **새 관리 센터 시도** 토글을 선택하여 켤 수 있습니다.

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">관리 센터로</a>이동 합니다.

2. **사용자** \> **활성 사용자**로 이동한 다음 목록에서 계정을 선택 합니다.

3. **계정** 탭에서 **사용자 이름 관리**를 선택 하 고 다른 도메인을 선택 합니다.
  
4. 맨 위에서 계정 이름을 선택한 다음 **로그 아웃**을 선택 합니다.

5. 새 도메인 및 같은 암호를 사용 하 여 로그인 합니다.

PowerShell을 사용하여 사용자를 다른 도메인으로 이동할 수도 있습니다. 자세한 내용은 [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)을 참조하세요. 기본 도메인을 설정하려면 [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0)을 사용하세요.

::: moniker-end

::: moniker range="o365-germany"

1. **사용자** \> **활성 사용자**로 이동한 다음 목록에서 이름을 선택 합니다.

2. **사용자 이름/전자 메일** 섹션에서 **편집**을 선택 하 고 다른 도메인을 선택 합니다.

3. 기본 > **Save** 저장 > **닫기를** **설정을** 선택 합니다.
  
4. 맨 위에서 계정 이름을 선택한 다음 **로그 아웃**을 선택 합니다.

5. 새 도메인 및 같은 암호를 사용 하 여 로그인 합니다.

PowerShell을 사용하여 사용자를 다른 도메인으로 이동할 수도 있습니다. 자세한 내용은 [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)을 참조하세요. 기본 도메인을 설정하려면 [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0)을 사용하세요.

::: moniker-end

::: moniker range="o365-21vianet"

1. **사용자** \> **활성 사용자**로 이동한 다음 목록에서 이름을 선택 합니다.

2. **사용자 이름/전자 메일** 섹션에서 **편집**을 선택 하 고 다른 도메인을 선택 합니다.

3. 기본 > **Save** 저장 > **닫기를** **설정을** 선택 합니다.
  
4. 맨 위에서 계정 이름을 선택한 다음 **로그 아웃**을 선택 합니다.

5. 새 도메인 및 같은 암호를 사용 하 여 로그인 합니다.

PowerShell을 사용하여 사용자를 다른 도메인으로 이동할 수도 있습니다. 자세한 내용은 [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)을 참조하세요. 기본 도메인을 설정하려면 [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0)을 사용하세요.

::: moniker-end

### <a name="step-2-move-groups-to-another-domain"></a>2 단계: 그룹을 다른 도메인으로 이동

::: moniker range="o365-worldwide"

1. 관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">그룹</a> 페이지로 이동 합니다.
  
2. 그룹 이름을 선택한 다음 **일반** 탭의 **전자 메일 주소, 주**에서 **편집**을 선택 합니다.

3. 드롭다운 목록을 사용 하 여 다른 도메인을 선택 합니다.

4. **저장**을 선택한 다음 **닫기**를 선택합니다. 제거하려는 도메인과 연관된 그룹 또는 분배 목록에 대해 이 단계를 반복합니다.

::: moniker-end

::: moniker range="o365-germany"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">관리 센터</a>에서 **그룹** > **그룹** 페이지로 이동 합니다.

2. 그룹 이름을 선택한 다음 **이름**옆에 있는 **편집** 을 선택 합니다.

3. 드롭다운 목록을 사용 하 여 다른 도메인을 선택 합니다.

4. **저장**을 선택한 다음 **닫기**를 선택합니다. 제거하려는 도메인과 연관된 그룹 또는 분배 목록에 대해 이 단계를 반복합니다.

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">관리 센터</a>에서 **그룹** > **그룹** 페이지로 이동 합니다.

2. 그룹 이름을 선택한 다음 **이름**옆에 있는 **편집** 을 선택 합니다.

3. 드롭다운 목록을 사용 하 여 다른 도메인을 선택 합니다.

4. **저장**을 선택한 다음 **닫기**를 선택합니다. 제거하려는 도메인과 연관된 그룹 또는 분배 목록에 대해 이 단계를 반복합니다.

::: moniker-end

### <a name="step-3-remove-the-old-domain"></a>3 단계: 이전 도메인 제거

::: moniker range="o365-worldwide"

1. I관리 센터에서 ** 설정 ** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인 </a> 페이지로 이동하십시오.

::: moniker-end

::: moniker range="o365-germany"

1. 관리 센터에서 <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">도메인</a> **설정** \> 페이지로 이동 합니다.

::: moniker-end

::: moniker range="o365-21vianet"

1. 관리 센터에서 <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">도메인</a> **설정** \> 페이지로 이동 합니다.

::: moniker-end
  
2. **도메인** 페이지에서 제거 하려는 도메인을 선택 합니다.

3. 오른쪽 창에서 **제거**를 선택 합니다.

4. 추가 프롬프트를 따른 다음 **닫기를**선택 합니다.

## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a>도메인을 제거하는 데 걸리는 시간은 얼마인가요?

Microsoft 365이 보안 그룹, 메일 그룹, 사용자 및 Microsoft 365 그룹과 같은 많은 위치에서 참조 되지 않는 경우 도메인을 제거 하는 데에는 5 분 정도 걸릴 수 있습니다. 도메인을 사용하는 참조가 많으면 도메인을 제거하는 데 몇 시간(하루)이 걸릴 수 있습니다.
  
수백 또는 수천 명의 사용자가 있는 경우 PowerShell을 사용하여 모든 사용자에 대해 쿼리한 다음 사용자를 다른 도메인으로 이동합니다. 그러지 않으면 UI에서 몇 명의 사용자가 누락될 수 있으며, 이 경우 도메인을 제거하기 위해 이동하면 도메인을 제거할 수 없으며 이유를 알지 못하게 됩니다. 자세한 내용은 [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)을 참조하세요. 기본 도메인을 설정하려면 [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0)을 사용하세요.
  
## <a name="still-need-help"></a>여전히 도움이 필요하세요?

::: moniker range="o365-worldwide"

> [!NOTE]
> 계정에서 [". onmicrosoft.com"](https://support.office.com/article/b9fc3018-8844-43f3-8db1-1b3a8e9cfd5a.aspx) 도메인을 제거할 수 없습니다.
  
여전히 작동하지 않나요? 도메인을 수동으로 제거해야 할 수도 있습니다. [전화로 연락주시면](../contact-support-for-business-products.md) 작업을 수행할 수 있도록 지원하겠습니다.
  
::: moniker-end

## <a name="related-articles"></a>관련 문서

[도메인 FAQ](../setup/domains-faq.md)

[Office 365 도메인에 대 한 도움말 보기](get-help-with-domains.md)

[다른 Microsoft 365 for business 요금제로 전환](../../commerce/subscriptions/switch-to-a-different-plan.md)

[구독 취소](../../commerce/subscriptions/cancel-your-subscription.md)
