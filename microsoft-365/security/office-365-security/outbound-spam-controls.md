---
title: 아웃바운드 스팸 검색
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 관리자에 게 Office 365 및 EOP (Exchange Online Protection)에서 고객을 아웃 바운드 스팸으로 보호 하는 방법 및 대량 메일을 보내는 데 필요한 경우 수행할 작업에 대해 알아봅니다.
ms.openlocfilehash: ffedcf68489914865c00eb68aecfa6c74e519ee2
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033929"
---
# <a name="outbound-spam-protection"></a>아웃바운드 스팸 검색

365 Microsoft는 exchange Online 사서함 없이 Exchange online 또는 독립 실행형 EOP (exchange online Protection)가 공유 리소스 풀을 사용 하는 온라인 서비스인 경우에는 아웃 바운드 스팸을 심각 하 게 관리 합니다. Microsoft 365 고객이 고의적으로 또는 실수로 조직에서 스팸을 보내는 경우 전체 서비스의 신뢰도를 떨어뜨릴 수 있으며 다른 고객의 전자 메일 배달에 영향을 줄 수 있습니다.

이 항목에서는 아웃 바운드 스팸을 방지 하는 데 도움이 되는 컨트롤 및 알림과 대량 메일을 보내는 데 필요한 경우 수행할 수 있는 작업에 대해 설명 합니다.

## <a name="what-admins-can-do-to-control-outbound-spam"></a>아웃 바운드 스팸 제어를 위해 관리자가 수행할 수 있는 작업

- **기본 제공 알림 사용**: 사용자가 [서비스](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) 또는 [아웃 바운드 스팸 정책의](configure-the-outbound-spam-policy.md) 한도를 초과 하 여 전자 메일을 보낼 수 없는 경우 **전자 메일을 보내는 사용자가 제한** 된 기본 경고 정책이 **tenantadmins** (**Global admins**) 그룹의 구성원에 게 전자 메일 알림을 보냅니다. 이러한 알림을 받는 사람을 구성 하려면 [제한 된 사용자에 대 한 알림 설정 확인](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)을 참조 하십시오. 또한 **전자 메일 보내기 제한 초과** 및 **의심 스러운 전자 메일 보내기 패턴** 으로 인해 **tenantadmins** (**Global admins**) 그룹의 구성원에 게 전자 메일 알림이 전송 됩니다. 경고 정책에 대한 자세한 내용은 [보안 및 규정 준수 센터의 경고 정책](../../compliance/alert-policies.md)을 참조하세요.

- 타사 **전자 메일 공급자의 스팸 불만 사항 검토**: 서비스의 사용자가 Microsoft 365에서 스팸으로 전자 메일을 표시할 경우 메시지는 패키지화 되 고 검토를 위해 다시 전송 됩니다. Outlook.com에 대 한 보낸 사람 지원에 대해 자세히 알아보려면 <https://sendersupport.olc.protection.outlook.com/pm/services.aspx>로 이동 합니다.

## <a name="how-eop-controls-outbound-spam"></a>EOP에서 아웃 바운드 스팸을 제어 하는 방법

- **조각화 아웃 바운드 전자 메일 트래픽**:이 서비스를 통해 전송 되는 모든 아웃 바운드 메시지는 스팸을 검색 합니다. 메시지가 스팸으로 확인 되 면 _위험성이 높은 배달 풀_이라는 보조 신뢰할 수 없는 IP 주소 풀에서 배달 됩니다. 자세한 내용은 [Office 365에서 아웃 바운드 메시지에 대 한 위험성이 높은 배달 풀](high-risk-delivery-pool-for-outbound-messages.md)을 참조 하세요.

- **원본 IP 주소 신뢰도 모니터링**: Microsoft 365에서는 다양 한 타사 IP 차단 목록을 쿼리 합니다. 아웃 바운드 전자 메일에 사용 하는 IP 주소가 이러한 목록에 표시 되 면 경고가 생성 됩니다. 이를 통해 스팸에 대 한 신뢰가 저하 되는 경우 신속 하 게 대응할 수 있습니다. 경고가 생성 되 면 차단 목록에서 IP 주소 제거 (delisted)를 받는 방법을 설명 하는 내부 설명서가 제공 됩니다.

- **스팸이 너무 많이 전송 되는 계정을 사용 하지 않도록 설정**<sup>\*</sup>합니다. 아웃 바운드 스팸을 높은 위험 배달 풀로 분리 하더라도 계정 (대개 손상 된 계정)을 허용 하 여 스팸을 무한정 보낼 수는 없습니다. 스팸 메일을 보내는 계정을 모니터링 하 고 사용자가 undisclosed 한도를 초과 하는 경우 해당 계정에 전자 메일이 전송 되지 않도록 차단 됩니다. 개별 사용자와 전체 테 넌 트에 대 한 임계값이 서로 다릅니다.

- **너무 많은 전자 메일을 전송 하는 계정을 사용 하지 않도록 설정 하는**<sup>\*</sup>경우 스팸으로 표시 된 메시지를 찾는 제한 외에, 아웃 바운드 메시지에 대 한 스팸 필터링 결과에 관계 없이 전체 아웃 바운드 메시지 제한에 도달할 때 계정을 차단 하는 제한도 있습니다. 손상 된 계정은 스팸 필터에서 누락 된 0 일 (이전에는 인식할 수 없는) 스팸 메일을 보낼 수 있습니다. 합법적인 대량 메일 캠페인과 스팸 캠페인을 식별 하기가 어려울 수 있으므로 이러한 제한은 잠재적인 손상을 최소화 하는 데 도움이 됩니다.

<sup>\*</sup>정확한 제한을 알리지 않으며, 스팸 발송자가 시스템을 게임을 할 수 없으며, 필요에 따라 제한을 늘리거나 줄일 수도 있습니다. 이 제한은 평균 비즈니스 사용자가이를 초과 하지 못하도록 하기에 충분 하며, 스팸 발송자에 게 초래 되는 피해를 줄이기 위해 충분히 부족 합니다.

## <a name="recommendations-for-customers-who-want-to-send-mass-mailings-through-eop"></a>EOP를 통해 대량 메일을 전송 하려는 고객을 위한 권장 사항

많은 수의 전자 메일을 보내려고 하는 고객 간의 균형을 맞추기 하기 어렵고, 손상 된 계정 및 대량 전자 메일 보낸 사람에 게는 적절 하지 않은 받는 사람 가져오기 방법으로 서비스를 보호 합니다. 타사 IP 차단 목록에서 Microsoft 365 전자 메일 원본의 방문 비용은 너무 많은 전자 메일을 보내는 사용자를 차단 하는 것 보다 더 큽니다.

[Exchange Online 서비스 설명](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)에 설명 된 것 처럼 EOP을 사용 하 여 대량 전자 메일을 보내는 것은 지원 되는 서비스 사용이 아니며, "최고 작업량" 으로만 허용 됩니다. 대량 전자 메일을 보내는 고객의 경우 다음 솔루션을 권장 합니다.

- **온-프레미스 전자 메일 서버를 통해 대량 전자 메일 보내기**: 즉, 고객은 대량 우편물에 대해 자체 전자 메일 인프라를 유지 관리 해야 합니다.

- 타사 **대량 전자 메일 공급자 사용**: 대량 우편물을 보내는 데 사용할 수 있는 세 개의 타사 대량 전자 메일 솔루션 공급자가 있습니다. 이러한 회사에서는 전자 메일 보내기 모범 사례를 보장 하기 위해 고객과 협력 하는 데 관심을 vested 합니다.

MAAWG (메시징, 모바일, 맬웨어 남용 작업 그룹)는에 <https://www.maawg.org/about/roster>구성원 명단을 게시 합니다. 여러 대량 전자 메일 공급자가 목록에 있으며 인터넷 시민이 담당 하는 것으로 알려져 있습니다.
