---
title: 청구 프로필 이해
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsBillingProfiles
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- Commerce
search.appverid:
- MET150
description: 청구 프로필에서 송장을 지원하는 방법을 알아보세요.
ms.openlocfilehash: 708096b624caa9c23a40df4842ccfce856db048d
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/14/2020
ms.locfileid: "49667780"
---
# <a name="understand-billing-profiles"></a>청구 프로필 이해

::: moniker range="o365-21vianet"

> [!NOTE]
> 관리 센터가 변경되고 있습니다. 사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)를 참조하세요.

::: moniker-end

Microsoft에서 제품 및 서비스를 구입하는 상용 고객의 경우 청구 프로필을 통해 송장에 포함된 항목과 송장 결제 방법을 사용자 지정할 수 있습니다.

청구 프로필에는 다음 정보가 포함됩니다.

- **청구 계정** &ndash; 프로필과 관련된 청구 계정의 이름
- **결제 방법** &ndash; 신용 카드 또는 직불 카드, 은행 계좌, 수표 또는 전신 송금
- **연락처 정보** &ndash; 청구 주소 및 연락처 이름
- **송장 설정** &ndash; 청구 계정의 국가, 선택적 PO 번호 및 전자 메일 첨부 파일로 송장을 받는 옵션에 기반한 통화
- **사용 권한** &ndash; 청구 프로필을 변경하거나, 청구서를 결제하거나, 청구 프로필에서 결제 방법을 사용하여 구매할 수 있는 권한

청구 프로필을 사용하여 구매를 제어하고 송장을 사용자 지정합니다. 청구 프로필을 사용하여 구입한 제품에 대해 월별 송장이 생성됩니다. 구매 주문 번호 및 전자 메일 송장 기본 설정 업데이트와 같은 송장을 사용자 지정할 수 있습니다.

첫 구매 중에 청구 계정에 대한 청구 프로필이 자동으로 만들어집니다. 청구 프로필 페이지에서 청구 프로필을 만들어 더 많은 송장을 설정할 수 있습니다. <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank"></a> 예를 들어 조직의 각 부서에 대해 구매할 때 다른 청구 프로필을 사용할 수 있습니다. 다음 청구 날짜에 각 청구 프로필에 대한 송장을 받게 됩니다.

## <a name="billing-profile-roles"></a>청구 프로필 역할

청구 프로필의 역할에는 구매를 제어하고 송장을 보고 관리할 수 있는 권한이 있습니다. 조직의 조달 팀 구성원과 같은 송장을 추적, 구성 및 결제하는 사용자에게 이러한 역할을 할당합니다.

| 역할                          | 설명                                                                       |
|-----------------------------  |---------------------------------------------------------------------------------  |
| 청구 프로필 소유자         | 청구 프로필에 대한 모든 관리                                           |
| 청구 프로필 참가자   | 청구 프로필의 사용 권한을 제외한 모든 관리                         |
| 청구 프로필 판독기        | 청구 프로필의 모든 내용을 읽기 전용으로 볼 수 있습니다.                                 |
| 송장 관리자               | 청구서 보기 및 결제, 청구 프로필의 모든 내용을 읽기 전용 보기   |

## <a name="view-billing-profiles"></a>청구 프로필 보기

1. 관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">청구서 및 결제</a> 페이지로 이동하십시오.

2. 청구 **프로필을 선택한** 다음 목록에서 청구 프로필을 선택합니다.

    - 개요 **탭에서** 청구 프로필 세부 정보를 편집하고 전자 메일로 송장 보내기를 설정하거나 해제할 수 있습니다.

    - 사용 권한 **탭에서** 사용자에게 송장 결제 역할을 할당할 수 있습니다.

    - Azure 신용 **잔액** 탭에서 Azure 고객은 해당 청구 프로필에서 사용하는 Azure 크레딧에 대한 거래 잔액 기록을 볼 수 있습니다.

    - Azure **크레딧** 탭에서 Azure 고객은 해당 청구 프로필과 연결된 Azure 크레딧 목록과 만료 날짜를 볼 수 있습니다.

    > [!NOTE]
    > Azure 크레딧이 없는 경우 **Azure** 크레딧 잔액 또는 Azure 크레딧 **탭이 표시되지** 않습니다.

## <a name="need-help-contact-support"></a>도움이 필요하신가요? 고객 지원에 문의하세요.

질문이 있는 경우 또는 Azure 요금에 대한 도움이 필요한 경우 Azure 지원으로 <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">지원 요청을 만드하세요.</a>

Microsoft 365 관리 센터에서 청구 프로필에 대한 질문이나 도움이 필요한 경우 비즈니스 제품에 대한 지원에 [문의하세요.](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)
