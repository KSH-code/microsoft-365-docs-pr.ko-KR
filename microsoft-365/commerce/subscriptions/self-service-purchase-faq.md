---
title: 셀프 서비스 구매 FAQ
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
- commerce
ms.custom:
- AdminSurgePortfolio
- aka.ms/self-service-purchase-faq
search.appverid:
- MET150
description: 셀프 서비스 구매에 대한 일반적인 질문과 대답을 찾아보는 것이 가장 흔합니다.
ms.date: 09/15/2020
ms.openlocfilehash: 81143dfe3794bc4f42bea879905bf08750f498b4
ms.sourcegitcommit: 9f5b136b96b3af4db4cc6f5b1f35130ae60d6b12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47816928"
---
# <a name="self-service-purchase-faq"></a>셀프 서비스 구매 FAQ

셀프 서비스 구매를 통해 사용자는 새로운 기술을 사용해 보거나 대규모 조직에 궁극적으로 혜택을 주는 솔루션을 개발할 수 있습니다. 중앙 조달 및 IT 팀은 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365</a>관리 센터를 통해 셀프 서비스 구매 솔루션을 구입하고 배포하는 모든 사용자에게 가시성을 제공합니다. 관리자는 PowerShell을 통해 제품 기준으로 셀프 서비스 구매를 해제할 수 있습니다. 자세한 내용은 [MSCommerce PowerShell 모듈에 AllowSelfServicePurchase 사용을 참조합니다.](allowselfservicepurchase-powershell.md)

셀프 서비스 구매는 Power Platform(Power BI, Power Apps 및 Power Automate), Project 및 Visio에서 사용할 수 있습니다.

> [!NOTE]
> 셀프 서비스 구매는 인도나 정부 또는 교육 고객에게는 제공되지 않습니다. 프로젝트 및 Visio는 브라질 및 민주 공화국에서 셀프 서비스 구매를 사용할 수 없습니다.

## <a name="making-a-self-service-purchase"></a>셀프 서비스 구매

### <a name="how-does-a-customer-make-a-self-service-purchase"></a>고객이 셀프 서비스 구매를 어떻게 하나요?

고객은 제품 웹 사이트 또는 앱에서도 구매 프롬프트에서 온라인으로 셀프 서비스 구매를 할 수 있습니다. 고객은 먼저 기존 Azure AD(Active Directory) 테넌트의 사용자이기 위해 전자 메일 주소를 입력하도록 요청됩니다. 다음으로 Azure AD 자격 증명을 사용하여 로그인합니다. 로그인한 후 고객은 구입하려는 구독 수를 선택하고 신용 카드 결제를 제공해야 합니다. 구매가 완료되면 구독 사용을 시작할 수 있습니다. 구매는 조직의 다른 사용자에게 제품에 라이선스를 할당할 수 있는 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365</a> 관리 센터의 제한된 보기에 액세스할 수 있습니다.

### <a name="what-are-the-payment-options-for-self-service-purchases"></a>셀프 서비스 구매에 대한 결제 옵션은 무엇입니까?

현재 신용 카드만 사용할 수 있습니다. 송장 결제는 지원되지 않습니다.

### <a name="who-can-buy-through-self-service-purchase"></a>셀프 서비스 구매를 통해 구입할 수 있는 사람

관리되는 Azure AD 테넌트에 게스트가 아닌 사용자 계정이 있는 사용자는 셀프 서비스 구매를 만들 수 있습니다. 정부 또는 교육 기관인 테넌트에서는 셀프 서비스 구매를 사용할 수 없습니다. 조직에 적용되는 경우 셀프 서비스 구매를 제어하기 위해 추가 작업이 필요하지 않습니다.

셀프 서비스 구매 자격이 없는 조직 또는 시장의 사용자는 IT 관리자에게 문의할 수 있는 메시지를 볼 수 있습니다.

### <a name="can-guest-users-buy-through-self-service-purchase"></a>게스트 사용자가 셀프 서비스 구매를 통해 구입할 수 있나요?

아니요. 게스트 사용자는 게스트인 테넌트에서 셀프 서비스 구매를 완료할 수 없습니다.

### <a name="can-users-synced-from-an-on-premises-active-directory-buy-through-self-service-purchase"></a>사용자가 셀프 서비스 구매를 통해 온라인 Active Directory에서 동기화할 수 있나요?

적격 Azure AD 테넌트에서 활성 사용자 계정이 있는 사용자는 셀프 서비스 구매를 완료할 수 있습니다.

### <a name="who-can-self-service-purchasers-assign-licenses-to"></a>셀프 서비스 구매자가 라이선스를 할당할 수 있는 사람

셀프 서비스 구매자는 동일한 Azure AD 테넌트의 사용자에게만 라이선스를 할당할 수 있습니다. 구매는 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365</a> 관리 센터의 제한된 보기에 액세스하여 라이선스를 할당할 수 있습니다. 구매자는 셀프 서비스 구매를 통해 구입한 제품에 라이선스를 할당할 수 있으며 동일한 Azure AD 테넌트의 사용자에게만 라이선스를 할당할 수 있습니다.

### <a name="where-does-the-self-service-purchaser-see-and-manage-their-purchases"></a>셀프 서비스 구매는 어디에서 구매를 보고 관리하나요?

셀프 서비스 구매자는 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365</a>관리 센터의 제한된 보기에서 구매를 관리할 수 있습니다. 구매자는 항상 모든 Microsoft 365 및 Dynamics 온라인 앱에 기본 제공되는 앱 시작 관리자의 관리 타일에서 관리 센터에 액세스할 수 있습니다.  구매자는 구입한 구매를 보고, 동일한 서비스에 대한 추가 구독을 구입하고, 해당 구독에 대한 라이선스를 조직의 다른 사용자에게 할당할 수 있습니다. 또한 구매자는 청구서를 보고 결제하고, 결제 방법을 업데이트하고, 구독을 취소할 수 있습니다.

## <a name="pricing"></a>가격 책정

### <a name="what-is-the-pricing-for-self-service-purchases"></a>셀프 서비스 구매 가격은 어떻게 하나요?

셀프 서비스 구매 제품에 대한 가격은 Microsoft 웹 사이트에서 확인할 수 있습니다. 가격은 사용자가 셀프 서비스 구매를 할 때 체크 아웃 환경의 일부로도 표시됩니다. 이러한 가격은 조직이 파트너를 통해 중앙 구매 또는 가격을 제공한 경우 지불하는 가격과 다를 수 있습니다.

### <a name="who-is-responsible-for-payment"></a>지불 책임은 누구인가요?

셀프 서비스 구매를 통해 구독을 구입하는 사람은 청구된 사람이고 구매 약관 및 가격에 따라 결제를 담당하는 사람입니다.

## <a name="admin-capabilities"></a>관리자 기능

### <a name="what-capabilities-does-an-admin-have-for-self-service-purchases"></a>관리자가 셀프 서비스 구매를 위해 어떤 기능을 사용할 수 있나요?

관리자는 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365</a>관리 센터에서 조직에서 만든 모든 셀프 서비스 구매를 볼 수 있습니다. 각 셀프 서비스 구매에 대한 제품, 구매자 이름, 구독, 만료 날짜, 주문 내역, 구매 가격 및 할당된 사용자를 볼 수 있습니다. Power Platform 관리 센터에서 관리자는 셀프 서비스 구매 용량을 볼 수도 있습니다. 조직에 필요한 경우 관리자는 PowerShell을 통해 제품 기준으로 셀프 서비스 구매를 해제할 수 있습니다. 관리자는 셀프 서비스 구매를 통해 구입하거나 중앙에서 구입한 제품에 대해 동일한 데이터 관리 및 액세스 정책을 하게 됩니다.

관리자는 조직의 사용자가 셀프 서비스 구매를 할 수 있는지 여부를 제어할 수도 있습니다. 자세한 내용은 [MSCommerce PowerShell 모듈에 AllowSelfServicePurchase 사용을 참조하세요.](allowselfservicepurchase-powershell.md)

### <a name="how-is-microsoft-respecting-data-governance-and-compliance-by-enabling-self-service-purchase"></a>Microsoft는 셀프 서비스 구매를 통해 데이터 거버넌스 및 규정 준수를 어떻게 준수하나요?

관리자는 데이터 거버넌스 및 규정 준수 요구 사항에 따라 테넌트 내에서 사용할 수 있는 서비스 및 제품을 제어합니다. 조직에서 설정한 모든 데이터 관리 및 액세스 정책은 사용 가능한 셀프 서비스 구매 서비스에 적용됩니다.

### <a name="who-owns-the-product-data-created-from-self-service-purchases"></a>셀프 서비스 구매로 만든 제품 데이터를 누가 소유하고 있나요?

셀프 서비스 구매를 통해 구입한 제품에서 만든 데이터는 조직에서 소유하고 제어합니다.

### <a name="how-do-i-centralize-the-purchases-made-through-self-service-purchase"></a>셀프 서비스 구매를 통해 구매한 제품을 중앙 집중화하는 방법

관리자는 셀프 서비스 구매에 할당된 사용자의 기존 계약 및 가격을 통해 기존 라이선스를 할당하거나 셀프 서비스 구매 제품의 추가 구독을 구입할 수 있습니다. 중앙에서 구매한 라이선스를 할당한 후 관리자는 구매자에 기존 구독을 취소할 수 있도록 요청할 수 있습니다.

### <a name="where-does-the-admin-see-self-service-purchases"></a>관리자에게 셀프 서비스 구매는 어디에서 표시하나요?

전역 및 대금 청구 관리자는   >   <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365</a>관리 센터에서 제품 청구에서 셀프 서비스 구매를 통해 구입한 구독을 볼 수 있습니다. 중앙 조달을 통해 구매한 구독만 표시하거나 셀프 서비스 구매를 통해 구입한 구독을 포함하기 위해 제품 목록을 필터링할 수 있습니다.

관리자는 제품, 구매자 이름, 구독 구매, 만료 날짜, 주문 내역, 구매 가격 및 할당된 사용자를 볼 수 있습니다.

## <a name="support-and-training"></a>지원 및 교육

### <a name="are-customers-it-departments-or-partners-expected-to-support-products-bought-through-self-service-purchase"></a>고객의 IT 부서 또는 파트너가 셀프 서비스 구매를 통해 구입한 제품을 지원할 것으로 예상하나요?

IT 부서 및 파트너는 셀프 서비스 구매를 통해 구입한 제품에 대한 지원을 제공할 것으로 예상되지 않습니다. Microsoft는 셀프 서비스 구매자에 대한 표준 지원을 제공합니다.

### <a name="if-a-self-service-purchaser-calls-support-does-that-use-the-customers-premier-support-incidents"></a>셀프 서비스 구매자가 지원을 요청하는 경우 고객의 프리미어 지원 인시던트가 사용하나요?

셀프 서비스 구매자는 셀프 서비스 구매에 대한 지원을 받는 데 고객의 프리미어 지원 인시던트가 사용되지 않습니다.

### <a name="how-are-users-expected-to-receive-training-on-the-products-they-buy-through-self-service-purchase"></a>셀프 서비스 구매를 통해 구입하는 제품에 대한 교육은 어떻게 받을 것으로 예상하나요?

사용자에 대한 광범위한 교육은 제품 웹 사이트에서 제공됩니다. 제품에는 다른 사용자로부터 직접 답변과 팁을 얻을 수 있도록 학습, 설명서, 샘플 및 강력한 커뮤니티가 제공되고 있습니다.

### <a name="what-happens-to-a-self-service-purchase-if-a-user-leaves-the-organization"></a>사용자가 조직을 떠날 경우 셀프 서비스 구매는 어떻게 하나요?

원래 셀프 서비스 구매 제품을 구입한 사람이 조직을 떠나도 유효한 사용자는 구독 기간 동안 제품을 계속 완전하게 사용할 수 있습니다. 구독은 고객이 직접 취소하거나 관리자가 고객 지원을 통해 구독 취소를 요청할 때까지 활성 상태로 남아 있습니다. 관리자는 중앙에서 구입한 라이선스를 취소된 구독 사용자에게 할당할 수도 있습니다.

## <a name="partners"></a>파트너

### <a name="whats-the-role-of-microsofts-partners-in-self-service-purchases"></a>셀프 서비스 구매에서 Microsoft 파트너의 역할은 무엇입니까?

관리 권한을 위임한 파트너는 관리자와 마찬가지로 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365</a>관리 센터에서 셀프 서비스 구매를 볼 수 있습니다. 파트너는 셀프 서비스 구매를 통해 구입한 제품을 중앙 집중화하려는 조직을 지원할 수 있습니다. 또한 파트너는 셀프 서비스 구매 기능을 확장하는 솔루션을 제공할 수 있습니다.