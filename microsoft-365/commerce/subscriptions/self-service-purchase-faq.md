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
description: 셀프 서비스 구매에 대 한 일반적인 질문과 대답을 확인할 수 있습니다.
ms.date: 08/12/2020
ms.openlocfilehash: 78a7082a966a866f18ac2aa378198dbb33d8c158
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653704"
---
# <a name="self-service-purchase-faq"></a>셀프 서비스 구매 FAQ

셀프 서비스 구매 기능을 통해 사용자는 새로운 기술을 시험해 보고 궁극적으로는 대규모 조직에 이익이 되는 솔루션을 개발할 수 있습니다. 중앙 조달 및 IT 팀은 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 관리 센터</a>를 통해 셀프 서비스 구매 솔루션을 구입 하 고 배포 하는 모든 사용자에 게 표시 됩니다. 관리자는 PowerShell을 통해 제품별로 셀프 서비스 구매를 해제할 수 있습니다. 자세한 내용은 [Use AllowSelfServicePurchase for The MSCommerce PowerShell module](allowselfservicepurchase-powershell.md)을 참조 하십시오.

셀프 서비스 구매는 전원 플랫폼 (Power BI, Power Apps 및 Power 자동화), Project 및 Visio에 사용할 수 있습니다.

> [!NOTE]
> 셀프 서비스 구매는 인도에서 사용할 수 없으며 정부 또는 교육 고객은 사용할 수 없습니다.

## <a name="making-a-self-service-purchase"></a>셀프 서비스 구매

### <a name="how-does-a-customer-make-a-self-service-purchase"></a>고객이 셀프 서비스를 구매 하는 방법은 무엇 인가요?

고객은 제품 웹 사이트 또는 앱 내 구매 음성 안내에서 온라인 셀프 서비스를 구매할 수 있습니다. 고객은 먼저 전자 메일 주소를 입력 하 여 기존 Azure AD (Active Directory) 테 넌 트에서 사용자 인지 확인 하 라는 요청을 받습니다. 다음으로, Azure AD 자격 증명을 사용 하 여 로그인 하도록 리디렉션됩니다. 로그인 한 후 고객에 게 구매할 구독 수를 선택 하 고 신용 카드 결제를 제공 하 라는 메시지가 표시 됩니다. 구매가 완료 되 면 구독 사용을 시작할 수 있습니다. 구매자는 조직의 다른 사용자에 게 제품 라이선스를 할당할 수 있는 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 관리 센터</a> 의 제한 된 보기에 대 한 액세스 권한이 있습니다.

### <a name="what-are-the-payment-options-for-self-service-purchases"></a>셀프 서비스 구매에 대 한 결제 옵션은 무엇입니까?

현재 신용 카드만 사용할 수 있는 결제 방법입니다. 송장 결제 통과는 지원 되지 않습니다.

### <a name="who-can-buy-through-self-service-purchase"></a>셀프 서비스 구매를 통해 구매할 수 있는 사람은 누구 인가요?

관리 되는 Azure AD 테 넌 트에 비 게스트 사용자 계정을 가진 모든 사용자는 셀프 서비스를 구매할 수 있습니다. 셀프 서비스 구매는 정부 또는 교육 조직에 해당 하는 테 넌 트에는 사용할 수 없습니다. 이 사항이 조직에 적용 되는 경우 셀프 서비스 구매를 제어 하기 위해 추가 작업을 수행 하지 않아도 됩니다.

셀프 서비스 구매가 적합 하지 않은 조직이 나 시장의 사용자는 IT 관리자에 게 문의 하 라는 메시지가 표시 됩니다.

### <a name="can-guest-users-buy-through-self-service-purchase"></a>게스트 사용자가 셀프 서비스 구매를 통해 구매할 수 있습니까?

아니요, 게스트 사용자는 게스트가 고 있는 테 넌 트에서 셀프 서비스 구매를 완료할 수 없습니다.

### <a name="can-users-synced-from-an-on-premises-active-directory-buy-through-self-service-purchase"></a>셀프 서비스 구매를 통해 온-프레미스 Active Directory에서 사용자를 동기화 할 수 있습니까?

사용자가 적합 한 Azure AD 테 넌 트에 활성 사용자 계정을 가진 경우 셀프 서비스 구매를 완료할 수 있습니다.

### <a name="who-can-self-service-purchasers-assign-licenses-to"></a>Purchasers에서 라이선스를 할당할 수 있는 사용자는 누구 인가요?

셀프 서비스 purchasers는 동일한 Azure AD 테 넌 트의 사용자 에게만 라이선스를 할당할 수 있습니다. 구매자는 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 관리 센터</a> 의 제한 된 보기에 액세스 하 여 라이선스를 할당할 수 있습니다. Purchasers는 셀프 서비스 구매를 통해 구매한 제품에 라이선스를 할당할 수 있으며, 이러한 라이선스를 동일한 Azure AD 테 넌 트의 사용자 에게만 할당할 수 있습니다.

### <a name="where-does-the-self-service-purchaser-see-and-manage-their-purchases"></a>셀프 서비스 구매자가 구매를 확인 하 고 관리 하는 방법은 무엇 인가요?

셀프 서비스 purchasers은 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 관리 센터</a>의 제한 된 보기에서 해당 구매를 관리할 수 있습니다. Purchasers는 항상 모든 Microsoft 365 및 Dynamics online 앱에 기본적으로 제공 되는 앱 시작 **관리자 타일의 관리 센터** 에서 관리 센터로 이동할 수 있습니다. Purchasers에서는 사용자가 수행한 구매를 확인 하 고, 같은 서비스에 대 한 추가 구독을 구입 하 고, 해당 구독에 대 한 라이선스를 조직의 다른 사용자에 게 할당할 수 있습니다. 또한 purchasers에서 청구서를 보고 요금을 지불 하 고, 결제 방법을 업데이트 하 고, 구독을 취소할 수 있습니다.

## <a name="pricing"></a>산정

### <a name="what-is-the-pricing-for-self-service-purchases"></a>셀프 서비스 구매의 가격은 얼마 인가요?

Microsoft 웹 사이트에서 셀프 서비스 구매 제품 각각에 대 한 가격 산정을 사용할 수 있습니다. 가격은 사용자가 셀프 서비스를 구매 하는 경우 체크아웃 환경의 일부로도 표시 됩니다. 이러한 가격은 조직이 중앙 구매 또는 가격을 통해 제공 되는 경우 조직에서 지불 하는 가격과 다를 수 있습니다.

### <a name="who-is-responsible-for-payment"></a>지불 책임이 있는 사람은 누구 인가요?

셀프 서비스 구매를 통해 구독을 구매한 사람은 대금을 지불 하 고 구매 약관을 기준으로 결제를 담당 하는 사람입니다.

## <a name="admin-capabilities"></a>관리 기능

### <a name="what-capabilities-does-an-admin-have-for-self-service-purchases"></a>관리자가 셀프 서비스를 구매 하는 데 사용할 수 있는 기능은 무엇입니까?

관리자는 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 관리 센터</a>에서 조직에 적용 된 모든 셀프 서비스 구매를 볼 수 있습니다. 제품, 구매자 이름, 구독 구입, 만료 날짜, 주문 내역, 구매 가격 및 각 셀프 서비스 구매에 대 한 사용자 지정을 볼 수 있습니다. Power Platform 관리 센터에서는 관리자가 셀프 서비스 구매 용량을 볼 수도 있습니다. 조직에 필요한 경우 관리자는 PowerShell을 통해 제품별로 셀프 서비스 구매를 해제할 수 있습니다. 관리자는 셀프 서비스 구매 또는 중앙을 통해 구매한 제품에 대해 동일한 데이터 관리 및 액세스 정책을 사용 합니다.

관리자는 또한 조직의 사용자가 셀프 서비스 구매를 수행할 수 있는지 여부도 제어할 수 있습니다. 자세한 내용은 [Use AllowSelfServicePurchase for The MSCommerce PowerShell module](allowselfservicepurchase-powershell.md)을 참조 하십시오.

### <a name="how-is-microsoft-respecting-data-governance-and-compliance-by-enabling-self-service-purchase"></a>Microsoft는 셀프 서비스 구매를 사용 하 여 데이터를 관리 하 고 규정 준수 하는 방법을 알아봅니다.

관리자는 데이터 거 버 넌 스 및 규정 준수 요구 사항에 따라 해당 사용자의 테 넌 트 내에서 사용할 수 있는 서비스 및 제품을 제어 합니다. 조직이 설정 된 모든 데이터 관리 및 액세스 정책이 사용 가능한 셀프 서비스 구입 서비스에 적용 됩니다.

### <a name="who-owns-the-product-data-created-from-self-service-purchases"></a>셀프 서비스 구매에서 만든 제품 데이터는 누구 입니까?

셀프 서비스 구매를 통해 구매한 제품에서 생성 된 데이터는 조직에서 소유 하 고 제어 합니다.

### <a name="how-do-i-centralize-the-purchases-made-through-self-service-purchase"></a>셀프 서비스 구매를 통한 구매를 중앙 집중화 하는 방법은 무엇 인가요?

관리자가 기존 라이선스를 할당 하거나 셀프 서비스 구매에 할당 된 사용자에 대 한 기존 계약 및 가격 산정을 통해 셀프 서비스 구매 제품의 추가 구독을 구매할 수 있습니다. 중앙에서 구매한 라이선스를 할당 한 후 관리자는 purchasers에서 기존 구독을 취소 하도록 요청할 수 있습니다.

### <a name="where-does-the-admin-see-self-service-purchases"></a>관리자가 셀프 서비스 구매를 참조 하는 위치

전역 및 대금 청구 관리자 **Billing**  >  는 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 관리 센터</a>에서**제품을** 대금 청구 하 여 셀프 서비스 구매를 통해 구매한 구독을 볼 수 있습니다. 제품 목록을 필터링 하 여 중앙 조달을 통해 구매한 구독을 표시 하거나 셀프 서비스 구매를 통해 구입한 구독을 포함할 수 있습니다.

관리자는 제품, 구매자 이름, 구독 구입, 만료 날짜, 주문 내역, 구매 가격 및 할당 된 사용자를 볼 수 있습니다.

## <a name="support-and-training"></a>지원 및 교육

### <a name="are-customers-it-departments-or-partners-expected-to-support-products-bought-through-self-service-purchase"></a>고객의 IT 부서 또는 파트너가 셀프 서비스 구매를 통해 구매한 제품을 지원 하기를 기대 하나요?

IT 부서 및 파트너가 셀프 서비스 구매를 통해 구매한 제품에 대 한 지원을 제공 하지 않을 것으로 예상 됩니다. Microsoft는 셀프 서비스 purchasers에 대 한 표준 지원을 제공 합니다.

### <a name="if-a-self-service-purchaser-calls-support-does-that-use-the-customers-premier-support-incidents"></a>셀프 서비스 구매자가 지원을 요청 하는 경우 고객의 프리미어 지원 인시던트를 사용 합니까?

셀프 서비스 purchasers 고객의 프리미어 지원 인시던트를 사용 하 여 셀프 서비스 구매 지원을 받을 수 없습니다.

### <a name="how-are-users-expected-to-receive-training-on-the-products-they-buy-through-self-service-purchase"></a>사용자가 셀프 서비스 구매를 통해 구입한 제품에 대 한 교육을 받을 것으로 예상 되는 이유는 무엇 인가요?

사용자에 대 한 광범위 한 교육은 제품 웹 사이트에서 제공 됩니다. 제품에는 안내 학습, 설명서, 샘플 및 강력한 커뮤니티를 통해 다른 사용자 로부터 직접 응답과 팁을 얻을 수 있습니다.

### <a name="what-happens-to-a-self-service-purchase-if-a-user-leaves-the-organization"></a>사용자가 조직을 떠나는 경우 셀프 서비스 구매는 어떻게 되나요?

원래 셀프 서비스 구매 제품을 구매한 사용자가 조직을 벗어나면 유효한 사용자는 구독 기간 동안 제품을 완전히 사용 하 게 됩니다. 구독은 구매자가 직접 취소 하거나 고객 지원을 통해 구독에 대 한 관리자 요청 취소를 취소할 때까지 활성 상태로 유지 됩니다. 또한 관리자는 취소 된 구독 사용자에 게 중앙에서 구매한 라이선스를 할당 하도록 선택할 수도 있습니다.

## <a name="partners"></a>파트너

### <a name="whats-the-role-of-microsofts-partners-in-self-service-purchases"></a>셀프 서비스 구매에서의 Microsoft 파트너 역할은 무엇 인가요?

관리 권한을 위임 받은 파트너는 관리자와 마찬가지로 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 관리 센터</a>에서 셀프 서비스 구매를 볼 수 있습니다. 파트너는 셀프 서비스 구매를 통해 구매한 제품을 중앙 집중식으로 관리 하려는 조직을 지 원하는 데 도움이 될 수 있습니다. 또한 파트너는 셀프 서비스 구매 기능을 확장 하는 솔루션을 제공할 수 있습니다.