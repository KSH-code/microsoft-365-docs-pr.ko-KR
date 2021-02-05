---
title: 결제 방법 관리
f1.keywords:
- CSH
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
- Adm_TOC
- commerce
ms.custom:
- TopSMBIssues
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- MET150
description: Microsoft 365 관리 센터에서 결제 방법을 관리하는 방법을 학습합니다.
ms.date: ''
ms.openlocfilehash: 6cba5e33ba99212cb6e67a90d1535120ccac3c38
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114852"
---
# <a name="manage-payment-methods"></a>결제 방법 관리

::: moniker range="o365-21vianet"
> [!NOTE]
> 관리 센터가 변경되고 있습니다. 사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)를 참조하세요.
::: moniker-end

Microsoft에서 비즈니스 제품 또는 서비스를 구입하는 경우 기존 결제 방법을 사용하거나 새 결제 방법을 추가할 수 있습니다. 신용 카드 또는 직불 카드 또는 은행 계좌를 사용하여 구입한 금액을 결제할 수 있습니다.

비즈니스 계정에 청구 프로필이 있으며 청구 프로필 소유자 또는 청구 프로필 작성자인 경우 신용 카드 또는 송장 결제로 지원되는 청구 프로필을 사용하여 구매하거나 청구서를 결제할 수 있습니다. 청구 송장 관리자인 경우 청구 프로필만 사용하여 청구서를 결제할 수 있습니다. 청구 프로필 및 역할에 대한 자세한 내용은 청구 프로필 [관리를 참조하세요.](manage-billing-profiles.md)

비즈니스 계정에 청구 프로필이 없는 경우 전역 또는 대금 청구 관리자는 비즈니스 계정에 추가된 모든 은행 계좌를 관리하고 사용할 수 있습니다. 그러나 추가한 신용 카드만 관리하거나 사용할 수 있습니다.

> [!NOTE]
> 일부 국가나 지역에서는 은행 계좌로 결제하는 옵션을 사용할 수 없습니다.
>
> 테넌트와 동일한 국가에서 발급된 결제 방법을 사용해야 합니다.

## <a name="before-you-begin"></a>시작하기 전에

이 문서의 작업을 수행하려면 전역 관리자 또는 대금 청구 관리자 되어야 합니다. 자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.

## <a name="add-a-payment-method"></a>결제 방법 추가

결제 방법을 추가해도 구독은 연결되지 않습니다. 결제 방법에 단일 구독을 할당하려면 단일 구독의 결제 방법 [변경을 참조하세요.](#change-a-payment-method-for-a-single-subscription) 다른 결제 방법을 사용하는 모든 구독을 새 결제 방법으로 바꾸기하려면 결제 방법 [바꾸기를 참조하세요.](#replace-a-payment-method)

1. 관리 센터에서 **청구** > **청구서 및 결제** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">결제 방법</a> 페이지로 이동합니다.
2. **결제 방법 추가** 를 선택합니다.
3. **결제 방법** 페이지의 드롭다운 메뉴에서 결제 방법을 선택합니다.
4. 새 카드 또는 은행 계좌에 대한 정보를 입력한 다음 추가를 **선택합니다.**

## <a name="update-payment-method-details"></a>결제 방법 업데이트

기존 결제 방법에 대한 신용 카드 또는 직불 카드, 청구 주소 또는 만료 날짜의 이름을 변경할 수 있습니다. 그러나 카드 또는 계정 번호를 변경할 수는 없습니다. 계정 번호가 변경된 [](#replace-a-payment-method)경우 다른 결제 방법으로 바꾸고 이전 결제 방법을 [삭제합니다.](#delete-a-payment-method)

1. 관리 센터에서 **청구** > **청구서 및 결제** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">결제 방법</a> 페이지로 이동합니다.
2. 업데이트할 결제 방법의 행을 선택합니다. 오른쪽 창에서 **편집** 을 선택합니다.
3. 신용 카드나 직불 카드의 이름, 대금 청구 주소 또는 만료 날짜를 비롯한 결제 방법 정보를 업데이트하고 **저장** 을 선택합니다.

## <a name="replace-a-payment-method"></a>결제 방법 변경

결제 방법을 바꿀 때 동일한 결제 방법을 사용하는 모든 구독 및 청구 프로필에 대해 결제 방법을 대체합니다. 결제 방법을 바꾸면 기존 결제 방법이 삭제되지 않습니다. 다른 구독 및 청구 프로필을 선택하고 사용할 수 있습니다.

단일 구독의 결제 방법을 변경하려면 단일 구독의 결제 방법 [변경을 참조하세요.](#change-a-payment-method-for-a-single-subscription)

1. 관리 센터에서 **청구** > **청구서 및 결제** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">결제 방법</a> 페이지로 이동합니다.
2. 변경할 결제 방법의 행을 선택합니다. 오른쪽 창에는 선택한 결제 방법을 사용하는 모든 청구 프로필 및 개인 구독이 표시됩니다.
3. 오른쪽 창에서 **모든 항목에 대해 결제 방법 변경** 을 선택합니다.
4. 기존 결제 방법을 사용하려는 경우, 드롭다운 목록에서 하나를 선택하고 **변경** 을 선택합니다.
    > [!NOTE]
    > 청구 프로필과 연결된 구독이 있는 경우, 신용 카드나 직불 카드로만 결제할 수 있습니다. **결제 방법** 페이지에 나열된 은행 계좌를 사용하는 경우, 드롭다운 목록에서 선택할 수 없습니다.
5. 새 결제 방법을 추가하려면 **결제 방법 추가** 를 선택합니다.
6. **결제 방법 추가** 창에서 계좌 정보를 입력하고 **저장** 을 선택합니다. 테넌트와 동일한 국가의 결제 방법을 사용해야 합니다.
7. 드롭다운 목록에 새 결제 방법이 이미 선택되어 있습니다. **변경** 을 선택합니다.

## <a name="change-a-payment-method-for-a-single-subscription"></a>단일 구독의 결제 방법 변경

단일 구독 비용을 결제하는 데 사용되는 결제 방법을 변경할 수 있습니다.

1. 관리 센터에서 **빌링** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">제품</a>페이지로 이동합니다.
2. 제품 **탭에서** 대체 결제 방법으로 결제할 구독을 찾아야 합니다.
3. 추가 **작업(3개** 점)을 선택한 다음 **결제 바꾸기 방법을 선택합니다.**
4. 결제 **방법 바꾸기** 창의 드롭다운 목록에서 대체 결제 방법을 선택하거나 결제 방법을 추가합니다.
5. 결제 방법을 추가하는 경우 카드 또는 계정 세부 정보를 입력한 다음 저장을 **선택합니다.**
6. 선택한 결제 방법이 올바른지 확인한 다음 **바꾸기 를 선택합니다.**

## <a name="delete-a-payment-method"></a>결제 방법 제거

구독 또는 청구 프로필에 연결되지 않은 결제 방법만 삭제할 수 있습니다. 이는 모든 구독에 적용됩니다( 상태와는 다를 수 있습니다.

### <a name="delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached"></a>구독 또는 청구 프로필이 첨부되지 않는 결제 방법 삭제

결제 방법이 구독 또는 청구 프로필과 연결되지 않은 경우 즉시 삭제할 수 있습니다.

1. 관리 센터에서 **청구** > **청구서 및 결제** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">결제 방법</a> 페이지로 이동합니다.
2. 삭제할 결제 방법을 찾아 3개의 점을 선택한 다음 삭제를 **선택합니다.**
3. 오른쪽 창의 아래쪽에서 삭제를 **선택합니다.**

### <a name="delete-a-payment-method-with-subscriptions-or-billing-profiles-attached"></a>구독 또는 청구 프로필이 연결된 결제 방법 삭제

결제 방법이 구독 또는 청구 프로필에 연결된 경우 먼저 기존 결제 방법으로 바꾸거나 새 결제 방법을 추가한 다음 이전 결제 방법을 삭제합니다.

1. 관리 센터에서 **청구** > **청구서 및 결제** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">결제 방법</a> 페이지로 이동합니다.
2. 삭제할 결제 방법의 행을 선택합니다. 오른쪽 창에는 해당 결제 방법을 사용하는 기존 구독이 나열됩니다.
3. 오른쪽 창에서 삭제를 **선택합니다.**
4. 기존 결제 방법을 사용하려면 드롭다운 목록에서 하나를 선택하고 다음을 선택한 다음 삭제를 **선택합니다.**
    > [!NOTE]
    > 청구 프로필과 연결된 구독이 있는 경우 신용 카드를 사용하여 결제만 할 수 있습니다. 결제 방법에 은행 계좌가  나열되어 있는 경우 드롭다운 목록에서 선택할 수 없습니다.
5. 새 결제 방법을 추가하려면 **결제 방법 추가** 를 선택합니다.
6. 추가할 결제 방법을 선택하고 계정 정보를 입력한 다음 저장을 **선택합니다.**
7. 드롭다운 목록에 새 결제 방법이 이미 선택되어 있습니다. **다음** 을 선택합니다.
8. **삭제** 를 선택합니다.

## <a name="troubleshoot-payment-methods"></a>결제 방법 문제 해결

| 문제 | 문제 해결 단계 |
|:----------|:-----|
|**"브라우저가 현재 쿠키를 차단할 수 있습니다."라는 오류 메시지가 표시됩니다.** |타사 쿠키를 허용하도록 브라우저를 설정하고 다시 시도하세요. |
|**신용 카드 또는 직불 카드가 거부됩니다.** |신용 카드 또는 직불 카드로 결제하는 경우 카드가 거부된 경우 Microsoft에서 결제를 처리하지 못했다는 내용의 전자 메일을 받게 됩니다. 카드 세부 정보 카드 번호, 만료 날짜, 카드의 이름 및 주소(구,시 및 우편 번호 포함)가 카드 및 명세서와 동일하게 나타나는지 다시 한 번 &mdash; &mdash; 검사합니다. 카드 정보를 업데이트하고 구독 세부 정보 페이지의  청구 섹션에  있는 잔액 결제 링크를 사용하여 즉시 결제를 제출할 수 있습니다. 자세한 내용은 미지원 잔액이 있는 경우 [어떻게 하나요?](pay-for-your-subscription.md#what-if-i-have-an-outstanding-balance)  <br/><br/>  계속 "거절" 메시지가 표시될 경우 은행에 문의합니다. 카드가 활성화되지 않은 것일 수 있습니다. 최근에 업데이트된 만료 날짜가 있는 메일에서 카드를 받은 경우 활성화되어 있는지 확인합니다. 또한 은행에서 카드가 온라인, 국제 거래 또는 재발 거래에 대해 승인되지 않는지 여부를 알 수 있습니다. |
|**카드 또는 은행 계좌 번호를 업데이트하고자 합니다.** |기존 결제 방법에서는 카드 또는 계좌 번호를 변경할 수 없습니다. 카드 또는 계정 번호가 변경된 경우 모든 활성 구독을 결제 방법에서 새 구독으로 이동하는 다른 결제 방법으로 바꾸고 이전 결제 방법을 [삭제합니다.](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached) [](#replace-a-payment-method) |
|**내 계정에 카드 또는 은행 계좌가 하나만 있으며 제거하고 싶을 것입니다.** |결제 방법이 하나뿐인 경우 [](#replace-a-payment-method) 새 결제 방법으로 바꾸야만 삭제할 수 있습니다. |
|**내 카드 또는 은행 계좌를 추가할 수 없습니다.**  |테넌트와 동일한 국가에서 발급된 결제 방법을 사용해야 합니다. 카드 또는 은행 계좌 정보를 입력하는 데 문제가 있는 경우 지원에 [문의할 수 있습니다.](../../admin/contact-support-for-business-products.md) |

## <a name="related-content"></a>관련 콘텐츠

[비즈니스 구독 결제(문서)\](pay-for-your-subscription.md)
[청구 프로필](manage-billing-profiles.md) 관리(문서)\
[청구 주기](change-payment-frequency.md) 변경(문서)
