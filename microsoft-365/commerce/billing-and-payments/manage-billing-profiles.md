---
title: 청구 프로필 관리
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsBillingProfiles
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: ''
search.appverid:
- MET150
description: 청구 프로필에서 송장을 지 원하는 방법을 알아봅니다.
keywords: 청구 프로필, 송장, 요금, 관리 비용
ms.openlocfilehash: f93ca5af11ba416fecd13fcceffe75055a776553
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140893"
---
# <a name="manage-billing-profiles"></a>청구 프로필 관리

::: moniker range="o365-21vianet"

> [!NOTE]
> 관리 센터가 변경 되는 중입니다. 환경이 여기에 나와 있는 세부 정보와 일치 하지 않으면 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)를 참조 하세요.

::: moniker-end

Microsoft의 제품 및 서비스를 구입한 상용 고객의 경우 대금 청구 프로필을 사용 하 여 송장에 포함 되는 항목을 사용자 지정 하 고 청구서 비용을 지불 하는 방법을 확인할 수 있습니다.

대금 청구 프로필에는 다음 정보가 포함 됩니다.

- 청구 계정 프로필과 관련 된 **계정** &ndash; 이름입니다.
- **결제 방법** &ndash; 크레딧 또는 직불 카드, 은행 계좌, 확인 또는 전선 전송
- **연락처 정보** &ndash; 청구 주소 및 연락처 이름
- **송장 설정** &ndash; 대금 청구 계정의 국가, 선택적 PO 번호 및 청구서를 전자 메일 첨부 파일로 수신 하는 옵션을 기준으로 통화
- **사용 권한** &ndash; 권한 프로필을 변경 하거나, 청구서를 지불 하거나, 대금 청구 프로필에서 결제 방법을 사용 하 여 구매를 수행할 수 있도록 하는 권한이 있어야 합니다.

청구 프로필을 사용 하 여 구매를 제어 하 고 송장을 사용자 지정 합니다. 대금 청구 프로필과 함께 구매한 제품에 대해 월별 송장이 생성 됩니다. 구매 주문 번호 및 전자 메일 송장 기본 설정 업데이트와 같은 송장을 사용자 지정할 수 있습니다.

최초 구매 중에 청구 계정에 대 한 대금 청구 프로필이 자동으로 만들어집니다. <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">청구 프로필</a> 페이지에서 청구 프로필을 만들어 추가 송장을 더 설정할 수 있습니다. 예를 들어 조직의 각 부서에 대해 구매를 수행 하는 경우 다른 대금 청구 프로필을 사용할 수 있습니다. 다음 청구 날짜에는 각 대금 청구 프로필에 대 한 송장을 받게 됩니다.

## <a name="billing-profile-roles"></a>청구 프로필 역할

청구 프로필에 대 한 역할에는 구매를 제어 하 고 송장을 보고 관리할 수 있는 권한이 있습니다. 조직의 조달 팀 구성원과 같이 송장을 추적, 구성 및 지불 하는 사용자에 게 이러한 역할을 할당 합니다.

| 역할                          | 설명                                                                       |
|-----------------------------  |---------------------------------------------------------------------------------  |
| 청구 프로필 소유자         | 청구 프로필에 대 한 모든 항목 관리                                           |
| 대금 청구 프로필 참가자   | 청구 프로필의 사용 권한을 제외한 모든 항목 관리                         |
| 청구 프로필 독자        | 대금 청구 프로필의 모든 항목에 대 한 읽기 전용 보기                                 |
| 송장 관리자               | 청구 프로필의 모든 항목에 대 한 읽기 전용 보기 및 청구서 보기 및 지불   |

## <a name="view-billing-profiles"></a>청구 프로필 보기

1. 관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848039" target="_blank">청구서 및 결제</a> 페이지로 이동하십시오.

2. **대금 청구**프로필을 선택한 다음 목록에서 대금 청구 프로필을 선택 합니다.

    - **개요** 탭에서 청구 프로필 세부 정보를 편집 하 고 전자 메일로 송장을 보내지 않거나 사용 하지 않도록 설정할 수 있습니다.

    - **사용 권한** 탭에서 송장을 지불 하기 위해 사용자에 게 역할을 할당할 수 있습니다.

    - Azure **구매 잔액** 탭에서 azure 고객은 해당 청구 프로필에 사용 되는 azure 제작진에 대 한 트랜잭션 균형 기록을 볼 수 있습니다.

    - **Azure 사용** 가능 항목에서 azure 고객은 해당 청구 프로필에 연결 된 azure 제작진 목록과 만료 날짜를 볼 수 있습니다.

    > [!NOTE]
    > Azure 크레딧이 없는 경우 **azure 크레딧 잔액** 또는 **azure 제작진** 탭이 표시 되지 않습니다.

## <a name="need-help-contact-support"></a>도움이 필요하신가요? 고객 지원에 문의하세요.

Azure 청구에 대 한 질문이 있거나 도움이 필요한 경우 <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">azure 지원 서비스를 통해 지원 요청을 만듭니다</a>.

Microsoft 365 관리 센터에서 청구 프로필에 대 한 질문이 있거나 도움이 필요한 경우 [비즈니스 제품 지원에 문의 하세요](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).
