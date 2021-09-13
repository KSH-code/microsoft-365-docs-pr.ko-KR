---
title: 셀프 서비스 구매 관리(관리자)
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: mijeffer, pablom
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- okr_smb
- commerce_ssp
search.appverid:
- MET150
description: 관리자는 조직의 사용자가 만든 셀프 서비스 구매를 관리하는 방법을 배울 수 있습니다.
ms.date: 03/26/2021
ms.openlocfilehash: a4ac4b79a9a73f80fc22e6f14696e25925df9faf
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59191642"
---
# <a name="manage-self-service-purchases-admin"></a>셀프 서비스 구매(관리자) 관리

관리자는 조직의 사용자가 셀프 서비스 구매를 볼 수 있습니다. 각 셀프 서비스 구매에 대한 제품 이름, 구매자 이름, 구입한 구독, 만료 날짜, 구매 가격 및 할당된 사용자가 표시됩니다. 조직에서 요구하는 경우 PowerShell을 통해 제품 기준으로 셀프 서비스 구매를 해제할 수 있습니다. 셀프 서비스 구매 또는 중앙에서 구입한 제품에 대해 동일한 데이터 관리 및 액세스 정책이 있습니다.

조직의 사용자가 셀프 서비스 구매를 할 수 있는지 여부를 제어할 수도 있습니다. 자세한 내용은 [MSCommerce PowerShell 모듈에 AllowSelfServicePurchase 사용을 참조하세요.](allowselfservicepurchase-powershell.md)

## <a name="view-self-service-subscriptions"></a>셀프 서비스 구독 보기

::: moniker range="o365-worldwide"

1. 관리 센터에서 **청구** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">내 상품</a> 페이지로 이동합니다.

::: moniker-end

::: moniker range="o365-germany"

1. 관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">내 상품</a> 페이지로 이동합니다.

::: moniker-end

::: moniker range="o365-21vianet"

1. 관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">내 상품</a> 페이지로 이동합니다.
::: moniker-end

2. 제품 **탭에서** 필터 아이콘을 선택한 다음 셀프 **서비스 를 선택합니다.**
3. 구독에 대한 자세한 내용을 확인하려면 목록에서 구독을 선택합니다.

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a>셀프 서비스 구매 구독에 대한 라이선스가 있는 사용자 보기

> [!NOTE]
> 관리자는 조직의 사용자가 구입한 셀프 서비스 구매 구독의 라이선스를 할당하거나 할당 취소할 수 없습니다. [셀프 서비스 구매 구독을 이어 받은 다음](#take-over-a-self-service-purchase-subscription)할당 또는 할당 취소할 수 있습니다.

::: moniker range="o365-worldwide"

1. 관리 센터에서 **청구** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">라이선스</a> 페이지로 이동합니다.

::: moniker-end

::: moniker range="o365-germany"

 1. 관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">라이선스</a> 페이지로 이동합니다.

::: moniker-end

::: moniker range="o365-21vianet"

 1. 관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">라이선스</a> 페이지로 이동합니다.

::: moniker-end

2. 필터 아이콘을 선택한 다음 셀프 **서비스 를 선택합니다.**
3. 제품을 선택하여 사용자에게 할당된 라이선스를 볼 수 있습니다.
    > [!NOTE]
    > 제품에 대한 구매가 여러 번 있는 경우 해당 제품은  한 번만 나열됩니다. 사용 가능한 수량 열에는 해당 제품에 대해 구입한 모든 구독의 총계가 표시됩니다.
4. 사용자 **목록은** 셀프 서비스 구매를 한 사용자의 이름으로 그룹화됩니다.
5. 이러한 구독에 대한 라이선스가 있는 사용자 목록을 내보내기하려면 내보낼 구독을 선택한 다음 사용자 **내보내기 를 선택합니다.**

## <a name="disable-or-enable-self-service-purchases"></a>셀프 서비스 구매 사용 또는 사용 안 하도록 설정

조직의 사용자에 대해 셀프 서비스 구매를 사용하지 않도록 설정하거나 사용하도록 설정할 수 있습니다. **MSCommerce** PowerShell 모듈에는 조직의 사용자가 셀프 서비스 구매를 할 수 있는지 여부와 제품을 제어할 수 있는 **AllowSelfServicePurchase에** 대한 **PolicyID** 매개 변수 값이 포함되어 있습니다.

**MSCommerce** PowerShell 모듈을 사용하여 다음을 할 수 있습니다.

- **AllowSelfServicePurchase** 매개 변수 값의 기본 상태(제품에서 사용 또는 사용 안 하도록 설정되어 있는지 여부)를 확인합니다.
- 해당 제품 목록 및 셀프 서비스 구매를 사용할 수 있는지 여부 보기
- 특정 제품의 현재 설정을 보거나 수정하여 특정 제품을 사용하거나 사용하지 않도록 설정

자세한 내용은 [MSCommerce PowerShell 모듈에 AllowSelfServicePurchase 사용을 참조하세요.](allowselfservicepurchase-powershell.md)

## <a name="centralize-licenses-under-a-single-subscription"></a>단일 구독에서 라이선스 중앙 집중화

셀프 서비스 구매에 할당된 사용자의 기존 계약을 통해 기존 라이선스를 할당하거나 추가 구독을 구매할 수 있습니다. 중앙에서 구입한 라이선스를 할당한 후 구매자에 기존 구독을 취소할 수 있습니다.

::: moniker range="o365-worldwide"

1. 관리 센터에서 청구  구매 서비스 > <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">페이지로</a> 이동합니다.

::: moniker-end

::: moniker range="o365-germany"

1. 관리 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">센터에서</a>청구 구매 서비스  > **페이지로** 이동합니다.

::: moniker-end

::: moniker range="o365-21vianet"

1. 관리 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">센터에서</a>청구 구매 서비스  > **페이지로** 이동합니다.

::: moniker-end

2. 구입하려는 제품을 찾아 선택한 다음 구입 을 **선택 합니다.**
3. 나머지 단계를 완료하여 구매를 완료합니다.
4. 셀프 서비스 [](#view-who-has-licenses-for-a-self-service-purchase-subscription) 구매 구독에 대한 라이선스가 있는 사용자 보기의 단계에 따라 다음 단계에서 참조할 사용자 목록을 내보낼 수 있습니다.
5. 다른 구독에 라이선스가 있는 모든 사용자에게 라이선스를 할당합니다. 전체 단계는 [사용자에게 라이선스 할당을 참조하세요.](../../admin/manage/assign-licenses-to-users.md)
6. 셀프 서비스 구매 구독을 구입한 담당자에게 연락하여 [취소해달고 요청합니다.](manage-self-service-purchases-users.md#cancel-a-subscription)

## <a name="take-over-a-self-service-purchase-subscription"></a>셀프 서비스 구매 구독 인계

조직의 사용자가 만든 셀프 서비스 구매 구독을 대신할 수 있습니다. 셀프 서비스 구매 구독을 인계할 경우 다음 두 가지 옵션이 있습니다.

1. 사용자를 다른 구독으로 이동하고 원래 구독을 취소합니다.
2. 셀프 서비스 구매 구독을 취소하고 할당된 사용자에서 라이선스를 제거합니다.

### <a name="move-users-to-a-different-subscription"></a>다른 구독으로 사용자 이동

사용자를 다른 구독으로 이동하면 이전 구독이 자동으로 취소됩니다. 셀프 서비스 구매 구독을 처음 구입한 사용자는 구독이 취소되었습니다.는 전자 메일을 받게 됩니다.

> [!NOTE]
> 사용자를 이동하는 구독에서 이동하는 각 사용자에 대해 사용 가능한 라이선스가 있어야 합니다.

::: moniker range="o365-worldwide"

1. 관리 센터에서 **청구** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">내 상품</a> 페이지로 이동합니다.

::: moniker-end

::: moniker range="o365-germany"

1. 관리 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">센터에서</a>청구 제품  > **페이지로** 이동합니다.

::: moniker-end

::: moniker range="o365-21vianet"

1. 관리 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">센터에서</a>청구 제품  > **페이지로** 이동합니다.

::: moniker-end

2. 제품 **탭에서** 필터 아이콘을 선택한 다음 셀프 **서비스 를 선택합니다.**
3. 인계할 구독을 선택합니다.
4. 구독 세부 정보 페이지의 구독 및 설정 **섹션에서** 이 구독 **제어 를 선택합니다.**
5. 오른쪽 창에서 사용자 **이동을 선택합니다.**
6. 사용자를 이동할 제품을 선택한 다음 사용자 **이동을 선택합니다.**
7. 사용자 **이동 상자에서** 사용자 **이동을 선택합니다.** 이동 프로세스는 몇 분 정도 걸릴 수 있습니다. 프로세스가 실행되는 동안 브라우저를 닫지 않습니다.
8. 이동 프로세스가 완료되면 완료된 **이동 창을 닫습니다.**
9. 구독 세부 정보 페이지에서  셀프 서비스 구매 구독의 구독 상태는 **삭제된 으로 표시됩니다.**

### <a name="cancel-a-self-service-purchase-subscription"></a>셀프 서비스 구매 구독 취소

셀프 서비스 구매 구독을 취소하기로 선택하면 라이선스가 있는 사용자는 제품에 액세스할 수 없습니다. 셀프 서비스 구매 구독을 처음 구입한 사용자는 구독이 취소되었습니다.는 전자 메일을 받게 됩니다.

::: moniker range="o365-worldwide"

1. 관리 센터에서 **청구** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">내 상품</a> 페이지로 이동합니다.

::: moniker-end

::: moniker range="o365-germany"

1. 관리 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">센터에서</a>청구 제품  > **페이지로** 이동합니다.

::: moniker-end

::: moniker range="o365-21vianet"

1. 관리 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">센터에서</a>청구 제품  > **페이지로** 이동합니다.

::: moniker-end

2. 제품 **탭에서** 필터 아이콘을 선택한 다음 셀프 **서비스 를 선택합니다.**
3. 취소하려는 구독을 선택합니다.
4. 구독 세부 정보 페이지의 구독 및 설정 **섹션에서** 이 구독 **제어 를 선택합니다.**
5. 오른쪽 창에서 구독 **취소를 선택합니다.**
6. 드롭다운 목록에서 취소 이유를 선택한 다음 구독 **취소를 선택합니다.**
7. **취소할지 여부** 상자에서 구독 **취소를 선택합니다.**
8. 오른쪽 창을 닫습니다.
9. 구독 세부 정보 페이지에서 구독 **상태가** 삭제된 **것으로 표시됩니다.**

## <a name="need-help-contact-us"></a>도움이 필요하신가요? 문의해 주시기 바랍니다.

셀프 서비스 구매에 대한 일반적인 질문은 셀프 서비스 [구매 FAQ를 참조하세요.](self-service-purchase-faq.yml)

셀프 서비스 구매에 대한 질문이나 도움이 필요한 경우 고객 [지원에 문의하세요.](../../business-video/get-help-support.md)
