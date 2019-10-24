---
title: 요금 청구 방식
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsInvoices
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: ''
search.appverid:
- MET150
description: Microsoft 비즈니스 제품의 송장을 읽고 이해 하는 방법을 알아봅니다.
keywords: 청구 계정, 조직 정보, 송장
ms.openlocfilehash: e0af9ec0808de97e55ef550c6feb51a146dbb5f6
ms.sourcegitcommit: 1e3916bbe94d4fbb858566e7db5018e1e46bcd0d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2019
ms.locfileid: "37646450"
---
# <a name="understand-your-invoice"></a>요금 청구 방식

송장에서는 결제에 대 한 요금 및 지침을 요약해 서 제공 합니다. Microsoft 365 관리 센터에서 [온라인 송장을 볼](#view-your-online-invoice) 수 있습니다. 또한이 파일을 휴대용 문서 형식 (.pdf)으로 다운로드 하 여 전자 메일을 통해 보낼 수 있습니다.

Office 365 구독이 있는 경우 [office 365 비즈니스 에디션에 대 한 청구서 보기](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/view-your-bill-or-invoice)를 참조 하세요.

## <a name="understand-the-invoice-header"></a>송장 헤더 이해

첫 페이지의 맨 위에는 결제를 담당 하는 사람, 청구서가 전송 되는 위치 및 청구 비용이 요약 되어 있습니다.

| 용어 | 설명 |
| --- | --- |
| 판매 대상 |지불을 담당 하는 법률 엔터티의 이름과 주소를 식별 하는 청구 계정입니다. 이 정보는 계정 계약을 찾고 역할 및 사용 권한을 관리할 수 있는 <a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">청구 계정</a> 페이지에서 관리할 수 있습니다. |
| 청구지 |송장을 받는 사람을 식별 합니다. 이 정보는 <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">청구 프로필</a> 페이지에서 관리할 수 있습니다. 대금 청구 프로필은 **송장 요약** 섹션의 온라인 송장 페이지에도 표시 됩니다. 청구 프로필에 대 한 자세한 내용과이를 사용 하 여 조직에 대 한 보다 유연한 대금 청구 옵션을 만드는 방법에 대 한 자세한 내용은 [청구 프로필 관리](manage-billing-profiles.md)를 참조 하세요. |
| 청구 프로필 |청구지, PO 번호 및 지불 조건 같은 송장 속성을 정의 하는 데 사용 되는 대금 청구 프로필의 이름입니다. 이 정보는 <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">청구 프로필</a> 페이지에서 관리할 수 있습니다. 청구 프로필에 대 한 자세한 내용과이를 사용 하 여 조직에 보다 유연한 대금 청구 옵션을 만드는 방법에 대 한 자세한 내용은 [청구 프로필 관리](manage-billing-profiles.md)를 참조 하세요. |
| 송장 번호 |추적 목적으로 사용 되는 Microsoft에서 생성 한 고유 송장 번호입니다. |
| 송장 날짜 |송장이 생성 된 날짜 (일반적으로 대금 청구 주기 종료 후 5 ~ 12 일)입니다. 청구 프로필 세부 정보 페이지에서 청구서 날짜를 확인할 수 있습니다. 청구 기간 및 송장 날짜의 끝 시간 사이에 발생 하는 요금은 다음 결제 기간에 해당 하는 경우 다음 달에 대 한 송장에 포함 됩니다. 각 송장에 대 한 청구 기간 시작 및 종료 날짜는 **대금 청구 요약**위의 송장 PDF에 나열 되어 있습니다.|
| 지불 조건 |Microsoft 청구서 지불 방법 *Net 30 일* 이란 송장에 대 한 지침에 따라 청구서 날짜 로부터 30 일 이내에 지불 하는 것을 의미 합니다. |

## <a name="understand-the-billing-summary"></a>대금 청구 요약 이해

**대금 청구 요약** 에는 이전 대금 청구 기간 이후의 금액, 적용 된 제작진, 세금 및 총 금액에 대 한 요약이 표시 됩니다.

| 용어 | 설명 |
| --- | --- |
| 요금|이 대금 청구 기간에 대해 구매한 총 제품 수 및 관련 요금 및 세금입니다. 구매는 자재 명세서를 간결 하 게 볼 수 있도록 집계 됩니다. |
| 크레딧 |반환 받은 제작진 |
| Azure 제작진 적용 |Azure 크레딧이 각 대금 청구 기간에 자동으로 적용 됩니다. Azure 크레딧이 없는 경우이 필드는 숨겨집니다. Azure 크레딧에 대 한 자세한 내용은 [Microsoft 고객 계약 Azure 크레딧 잔액 추적](https://docs.microsoft.com/en-us/azure/billing/billing-mca-check-azure-credits-balance)을 참조 하십시오. |
| 부분합과 |기한 전 금액 |
| 세금 |대금 청구 프로필의 국가에 따라 지불 하는 세금의 유형 및 수량입니다. 세금을 지불할 필요가 없으면 송장에 세금을 표시 하지 않습니다. |

### <a name="understand-your-charges"></a>비용 이해

비용 페이지에는 제품별로 세분화 된 비용이 표시 됩니다. Azure 고객의 경우 청구서 섹션에 따라 비용이 청구 될 수 있습니다. Azure 제품에서 송장 섹션을 사용 하는 방법에 대 한 자세한 내용은 [Microsoft 고객 계약 청구 계정 시작](https://docs.microsoft.com/en-us/azure/billing/billing-mca-overview)의 [송장 섹션](https://docs.microsoft.com/en-us/azure/billing/billing-mca-overview#invoice-sections) 을 참조 하세요. 각 제품 주문 내에서 비용은 서비스 제품군으로 구분 됩니다.

| 용어 |설명 |
| --- | --- |
| 단가 | 요금 청구를 계산 하는 데 사용 되는 서비스의 실제 단가 (가격 산정 금액)입니다. 이 가격은 제품, 서비스 제품군, 측정기 및 혜택에 고유 합니다. |
| 수량 | 대금 청구 기간 중 구입 또는 소비 수량 |
| 요금/제작진 | 제작진/refunds가 적용 된 후의 네트워크 금액입니다. |
| Azure 크레딧 | 청구 금액/제작진에 적용 된 Azure 제작진 |
| 세금 비율 | 국가에 따른 세금 비율입니다. |
| 세금 금액 | 세금 급여에 따라 구매에 적용 된 세금의 양 |
| 합계 | 구매로 인 한 총 금액 |

라인 항목 세부 정보는 요금이 부과 되는 제품 유형에 따라 달라 집니다. 예를 들어 Azure 제품의 경우 적용 된 Azure 크레딧 양이 표시 됩니다. 좌석 기반 제품은 단가와 수량을 표시 합니다. 송장 세부 정보에는 구매한 제품, 할인 또는 제작진, 세금 및 총액, 품목 합계가 요약 되어 있습니다.

`Total = Charges - Azure Credit + Tax`

각 서비스 제품군의 총 금액은 크레딧/요금에서 Azure 제작진을 빼서 세금을 추가 하 여 계산 됩니다.

`Total = Charges/Credits - Azure Credit + Tax`

송장에 자세한 세부 정보를 보려는 Azure 요금이 있는 경우 [Microsoft 고객 계약 송장의 청구 요금 이해](https://docs.microsoft.com/en-us/azure/billing/billing-mca-understand-your-bill)를 참조 하세요.

## <a name="understand-the-last-invoice-page"></a>마지막 송장 페이지 이해

### <a name="payment-instructions"></a>결제 지침

송장 맨 아래에 청구서 지불 방법에 대 한 지침이 나와 있습니다. 유선, 확인 또는 온라인으로 결제를 수행할 수 있습니다.

### <a name="publisher-information"></a>게시자 정보

청구서에 타사 서비스가 있는 경우 각 출판사의 이름과 주소가 송장 아래쪽에 나열 됩니다.

## <a name="view-your-online-invoice"></a>온라인 송장 보기

송장을 온라인으로 사용할 수 있습니다. 온라인 송장에 대 한 링크는 PDF 송장과 전자 메일 알림에서 제공 됩니다. 온라인 송장을 확장 하 여 송장에 대 한 청구 금액을 확인 하 고 각 항목에 대 한 세부 정보를 볼 수 있습니다. 온라인 송장에는 다음이 포함 됩니다.

- **가격 산정 정보** &mdash; 할인 및 제품 가격에 대 한 세부 정보를 포함 한 추가 정보입니다.

- **온라인 지불** &mdash; 송장에서 지불을 온라인으로 설정 하도록 선택할 수 있습니다.

- Azure **비용 관리** &mdash; azure 고객의 온라인 송장은 azure 비용 관리에 대 한 링크를 포함 합니다.

### <a name="to-view-your-online-invoice"></a>온라인 송장을 보려면

1. 관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">금액 & 지불</a> 페이지로 이동 합니다.

2. 해당 송장의 .pdf 버전을 다운로드 하려면 보려는 송장에 대 한 행에서 **송장 Pdf 다운로드** 를 선택 합니다.

3. 온라인 송장을 보려면 목록에서 송장을 선택 합니다. 송장 세부 정보 페이지 에서도 .pdf를 다운로드할 수 있습니다.

## <a name="need-help-contact-support"></a>도움이 필요 하세요? 고객 지원에 문의하세요.

Azure 제작진 관련 질문이 있거나 도움이 필요한 경우 <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">azure 지원 서비스를 통해 지원 요청을 만듭니다</a>.

Microsoft 365 관리 센터의 청구서에 대 한 질문이 있거나 도움이 필요한 경우 [비즈니스 제품 지원 서비스에 문의 하세요](https://docs.microsoft.com/en-us/office365/admin/contact-support-for-business-products).