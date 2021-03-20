---
title: 라이선스 충돌 해결
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: 796f7eda-b1f8-479a-adee-bd9226ca47ec
description: 비즈니스용 Microsoft 365 구독과 라이선스 충돌을 해결하는 방법을 자세히 알아보습니다.
ms.openlocfilehash: e2b5daa71164b41825282bd5652549347b8307c1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915185"
---
# <a name="resolve-license-conflicts"></a>라이선스 충돌 해결

::: moniker range="o365-21vianet"

> [!NOTE]
> 관리 센터가 변경되고 있습니다. 사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet)를 참조하세요.

::: moniker-end

새 사용자를 만들기 전에 구독에 필요한 라이선스를 구입하는 것이 좋습니다. 이렇게 하면 사용자 계정이 만들어지므로 라이선스를 새 사용자에 할당할 수 있습니다. 이미 사용자에게 라이선스를 모두 할당했지만 일부 라이선스가 만료되었거나 사용자에게 이미 할당한 라이선스를 제거하려면 라이선스 충돌이 발생됩니다. 자세한 내용은 구독에서 [라이선스 제거를 참조하세요.](../../commerce/licenses/buy-licenses.md)
  
## <a name="how-do-i-view-license-conflicts"></a>라이선스 충돌을 확인하는 방법

::: moniker range="o365-worldwide"

1. 관리 센터에서 **청구** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">라이선스</a> 페이지로 이동합니다.

::: moniker-end

::: moniker range="o365-germany"

1. 관리 센터에서 **청구** > <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">라이선스</a> 페이지로 이동합니다.

::: moniker-end

::: moniker range="o365-21vianet"

1. 관리 센터에서 **청구** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">라이선스</a> 페이지로 이동합니다.

::: moniker-end

2. 충돌에 대한 자세한 내용은 **상태** 열을 확인해보세요. 충돌이 있는 경우 한 개 이상의 사용자에게 유효한 라이선스가 필요하다는 경고 메시지가 표시됩니다.

    > [!NOTE]
    > 충돌이 없는 경우에는 **상태** 열이 표시되지 않습니다.

## <a name="how-do-i-resolve-license-conflicts"></a>라이선스 충돌을 해결하는 방법

추가 라이선스를 구입하거나 더 [](../../commerce/licenses/buy-licenses.md) 이상 필요하지 않은 사용자로부터 라이선스를 제거하여 라이선스 [충돌을 해결할 수 있습니다.](remove-licenses-from-users.md) 경우에 따라 [사용자 계정을 삭제하여 라이선스를 확보](../add-users/delete-a-user.md)할 수도 있습니다.
  
## <a name="related-articles"></a>관련 문서

[사용자에게 라이선스 할당](assign-licenses-to-users.md)
  
[사용자의 라이선스 제거](remove-licenses-from-users.md)