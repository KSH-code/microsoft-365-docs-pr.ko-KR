---
title: 청구 계정 이해
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: tugu, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_billing
- AdminTemplateSet
- admindeeplinkMAC
search.appverid: MET150
description: 청구 계정과 이러한 계정이 계정 설정, 송장, 결제 방법 및 구매를 관리하는 데 사용되는 방법에 대해 자세히 알아보습니다.
ms.date: 03/17/2021
ms.openlocfilehash: 551165a9ddcde03f96b6a2d03e5b1f5cd6e93eec
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59190279"
---
# <a name="understand-billing-accounts"></a>청구 계정 이해

Microsoft 제품을 사용해 보거나 구입하기 위해 등록하면 청구 계정이 만들어집니다. 청구 계정을 사용하여 계정 설정, 송장, 결제 방법 및 구매를 관리합니다. 여러 청구 계정에 액세스할 수 있습니다. 예를 들어 직접 Microsoft 365 등록하거나 조직의 기업계약, Microsoft 제품 & 서비스 계약 또는 Microsoft 고객 계약에 액세스할 수 있습니다. 이러한 각 시나리오에 대해 별도의 청구 계정이 있습니다.

현재 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 관리 센터</a> 계정 유형이 지원됩니다.

- Microsoft Online Services 프로그램: 이 청구 계정은 Microsoft 365 등록할 때 만들어집니다.
- Microsoft 제품 & 서비스 계약(MPSA) 프로그램: 이 청구 계정은 조직이 소프트웨어 및 온라인 서비스를 구입하기 위해 MPSA 볼륨 라이선스 계약에 서명할 때 만들어집니다.
- Microsoft 고객 계약: 이 청구 계정은 조직이 Microsoft 담당자, 공인 파트너 또는 독립적으로 구매할 때 만들어집니다.

청구 <a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">계정 페이지에서는</a> Microsoft의 상업용 계정 보기를 제공합니다. 기본적으로 조직에는 직접 구매 시 또는 볼륨 라이선스 계약을 통해 수락되는 계약과 연결된 청구 계정이 하나 이상 있습니다.

## <a name="understand-billing-account-details"></a>청구 계정 세부 정보 이해

청구 계정 세부 **정보** 페이지의 맨 위에는 계정 프로필이 있으며 조직에 대한 법적 및 세금 정보가 포함되어 있습니다. 프로필을 업데이트하여 법적 주소와 전화 번호를 변경할 수 있습니다. 이 계정은 구매한 제품에 대해 비용을 지불하는 법인입니다.

다음 표에는 청구 계정 세부 정보 페이지에 있는 중요한 **용어가 나열됩니다.**

| 필드 이름 | 설명 |
|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 판매 주소 | 결제를 담당하고 송장에 식별된 법인입니다. 여기에 제공된 주소는 구입 중에 다른 배송 주소를 제공하지 않는 한 세율을 결정하는 데 사용됩니다. 자세한 내용은 [세금 정보](billing-and-payments/tax-information.md)를 참조하세요. |
| 세그먼트 | 조직의 비즈니스 세그먼트(상업, 교육, 정부 또는 비영리)를 식별하는 읽기 전용 필드입니다. |
| 계정 상태 | Microsoft에서 상업용 계정의 상태를 지정하는 읽기 전용 필드입니다. |
| 세금 ID | 미국 이외 지역의 경우 VAT 또는 그에 상응하는 로컬 정보를 제공해야 합니다. 자세한 내용은 [세금 정보](billing-and-payments/tax-information.md)를 참조하세요. |
| 계약 | 직접 구매 또는 볼륨 라이선싱 계약을 통해 청구 계정을 만들 때 조직의 서명자는 계정의 조건과 & 계약을 수락하거나 서명합니다. 해당하는 경우 이 보기에는 계약 기록이 나열됩니다. 업데이트된 약관에 동의해야 하는 경우 계약 승인 **링크가** 표시됩니다. |
| 청구 프로필 | 청구 프로필은 청구서를 받는 사람, 청구서 전달 방법, 결제 조건 및 PO 번호와 같은 송장 속성을 정의합니다. 조직 전체에 청구를 배포하려면 여러 청구 프로필을 만들고 구매 시 적절한 청구 프로필을 식별할 수 있습니다. 청구 프로필 및 이러한 프로필을 사용하여 조직에 보다 유연한 청구 옵션을 구축하는 방법에 대한 자세한 내용은 청구 프로필 이해 를 [참조하십시오.](billing-and-payments/manage-billing-profiles.md) |

> [!NOTE]
> 판매자 이름 또는 주소를 변경해야 하지만 편집 링크가  없는 경우 고객 [](../business-video/get-help-support.md) 지원에 문의하여 변경해야 합니다.  판매 이름 **변경을** 요청하려면 신용 검사가 필요하게 됩니다. 이 [양식을 작성하고](https://www.microsoft.com/download/details.aspx?id=102732)지원에 문의할 때 다음 문서 중 하나를 Microsoft와 공유할 수 있습니다.
>
> - 정부에서 발급한 문서 또는 등록서
> - 로컬 회사의 레지스트리에서 인쇄
>
> 지원은 고객 이름만 변경되는 이름 및 주소 변경에 도움이 될 수 있지만 엔터티는 동일합니다. 제공된 설명서에는 엔터티의 이름만 변경된 것으로 명확하게 표시됩니다. 비즈니스 판매, 제어 변경 또는 고객 계열사 매각 또는 "스핀오프"를 포함하여 거래의 결과로 변경된 경우 Microsoft 판매자에 문의하시기 바랍니다.

## <a name="shipping-addresses"></a>배송 주소

이 섹션에는 청구 계정과 연결된 배송 주소가 나열됩니다. 구매할 때 이 주소를 사용하여 구매가 배송되거나 사용되는 위치를 확인할 수 있습니다. 배송 주소를 편집할 수 있습니다. 배송 주소를 추가하거나 기존 주소를 업데이트할 수 있습니다. 이 주소는 구매에 대한 세율을 결정하는 데 사용됩니다.

## <a name="understand-access-to-billing-accounts"></a>청구 계정에 대한 액세스 이해

역할 및 사용 권한을 통해 다른 사용자에게 계정의 청구 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">계정에 Microsoft 365 관리 센터</a> 수 있습니다. 청구 계정 소유자만 청구 계정에 대한 액세스 권한을 부여할 수 있습니다. 사용자에게 다음 역할 중 하나를 할당할 수 있습니다.

- **청구 계정 소유자** &mdash; 사용 권한을 할당하고, 계정을 편집하고, 계약에 서명하고, 계정을 볼 수 있습니다.
- **청구 계정 참가자** &mdash; 계정을 편집하고 계약에 서명하고 계정을 볼 수 있습니다.
- **청구 계정 판독기** &mdash; 계정을 볼 수 있습니다.

> [!Note]
> 청구 계정 역할은 청구 계정에만 적용될 뿐 다른 Microsoft 365 관리 센터 않습니다.

## <a name="related-content"></a>관련 콘텐츠

[세금](billing-and-payments/tax-information.md) 정보(문서) \
[청구 프로필](billing-and-payments/manage-billing-profiles.md) 이해(문서)
