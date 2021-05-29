---
title: 공유 사서함에서 라이선스 제거
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
ms.reviewer: nicholak
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
- commerce_licensing
search.appverid:
- BCS160
- MET150
- MOE150
description: '공유 사서함에서 라이선스를 제거하여 다른 사용자에게 할당하거나 라이선스 비용을 지불하지 않을 수 있도록 라이선스를 반환합니다. '
ms.openlocfilehash: d33487879506402c5f0de2f7942c3299c5698b73
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706289"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a>공유 사서함에서 라이선스 제거

공유 사서함에는 일반적으로 라이선스가 필요하지 않습니다. 다음 지침에 따라 공유 사서함에서 라이선스를 제거하여 사용자에게 라이선스를 할당하거나 필요하지 않은 라이선스 비용을 지불하지 않을 수 있도록 라이선스를 반환할 수 있습니다.

> [!NOTE]
>
> 다음과 같은 시나리오에서는 라이선스가 필요합니다.
>
> 1. 공유 사서함에 사용 중이 50GB가 넘는 저장소가 있습니다.
> 2. 공유 사서함은 인바운드 보관을 사용 합니다.
> 3. 공유 사서함은 소송 보류에 배치됩니다.
> 4. 공유 사서함에 Microsoft Defender 라이선스가 할당되어 있습니다.

## <a name="remove-the-license"></a>라이선스 제거

::: moniker range="o365-worldwide"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다.

::: moniker-end

::: moniker range="o365-germany"

 1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다.

::: moniker-end

::: moniker range="o365-21vianet"

 1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다.

::: moniker-end

   > [!NOTE]
   > 활성 사용자 페이지에서 라이선스를 제거해야 합니다. 라이선스는 사용자 설정이기 때문에 공유 사서함 페이지에서 라이선스를 제거할 수 없습니다.
  
2. 공유 사서함을 선택합니다.

3. 라이선스 **및** 앱 탭 중  하나에서 라이선스를 확장하고 제거할 라이선스의 확인란을 선택하지 않습니다.

4. **변경 내용 저장** 을 선택합니다.

5. 활성 사용자 페이지로 **돌아오면** 공유 사서함의 상태가 라이선스가 없는 **상태가 됩니다.**

6. 라이선스 비용은 계속 지불하고 있습니다. 요금 지불을 중지하려면 구독에서 [라이선스를 제거합니다.](../../commerce/licenses/buy-licenses.md)

## <a name="related-content"></a>관련 콘텐츠

[공유 사서함 정보](about-shared-mailboxes.md)(문서)\
[공유 사서함](create-a-shared-mailbox.md) 만들기(문서)\
[공유 사서함 구성](configure-a-shared-mailbox.md)(문서)\
[사용자 사서함을 공유 사서함으로 변환](convert-user-mailbox-to-shared-mailbox.md)(문서)\
[공유 사서함 문제 해결](resolve-issues-with-shared-mailboxes.md)(문서)
