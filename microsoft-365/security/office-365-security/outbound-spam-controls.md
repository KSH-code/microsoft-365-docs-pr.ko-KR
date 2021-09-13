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
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 관리자는 EOP(Exchange Online Protection)의 아웃바운드 스팸 컨트롤과 대량 메일을 보내야 하는 경우 어떻게 해야 하는지 알 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0fb6bfe5d83c551c0a93cc7b453b27a2d7b476bc
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59214312"
---
# <a name="outbound-spam-protection-in-eop"></a>EOP의 아웃바운드 스팸 보호

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft 365 사서함이 없는 Exchange Online 또는 EOP(독립 실행형 Exchange Online Protection)Exchange Online 조직에서는 아웃바운드 스팸을 심각하게 관리합니다. 한 고객이 의도적으로 또는 의도하지 않은로 조직에서 스팸을 보내도 해당 작업은 전체 서비스의 신뢰도 저하와 다른 고객의 전자 메일 배달에 영향을 줄 수 있습니다.

이 문서에서는 아웃바운드 스팸을 방지하도록 설계된 컨트롤 및 알림과 대량 메일을 보내야 하는 경우 할 수 있는 작업을 설명합니다.

## <a name="what-admins-can-do-to-control-outbound-spam"></a>관리자가 아웃바운드 스팸을 제어하기 위해 할 수 있는 일

- 기본 제공 알림 사용: 사용자가 서비스 또는 아웃바운드 [](configure-the-outbound-spam-policy.md) 스팸 정책의 전송 제한을 초과하고 전자 메일을 보내지 않는 경우 전자 메일을 보내지 않는 **User라는** 기본 경고 정책이 **TenantAdmins(전역** 관리자) 그룹의 구성원에게 전자 메일 알림을 전송합니다.  [](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)  이러한 알림을 받는 다른 사용자를 구성하려면 제한된 사용자에 대한 경고 [설정 확인을 참조하세요.](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users) 또한 이름이 **Email sending limit exceeded** and **Suspicious email sending patterns detected** email notifications to members of the **TenantAdmins** (**Global admins**) group. 경고 정책에 대한 자세한 내용은 [Microsoft 365의 경고 정책](../../compliance/alert-policies.md)을 참조하세요.

- 타사 전자 메일 공급자의 스팸 불만 사항 **검토:** Outlook.com, Yahoo 및 AOL과 같은 많은 전자 메일 서비스는 서비스 사용자가 Microsoft 365 전자 메일을 스팸으로 표시하는 피드백 루프를 제공합니다. 여기서 메시지는 패키지로 작성되어 검토를 위해 다시 전송됩니다. Outlook.com에 대한 보낸 사람 지원에 대한 자세한 내용은 로 이동 <https://sendersupport.olc.protection.outlook.com/pm/services.aspx> 합니다.

## <a name="how-eop-controls-outbound-spam"></a>EOP에서 아웃바운드 스팸을 제어하는 방법

- **아웃바운드 전자** 메일 트래픽의 분류: 서비스를 통해 전송된 모든 아웃바운드 메시지에서 스팸이 검색됩니다. 메시지가 스팸으로 확인되면 고위험 배달 풀이라는 덜 덜 악의적인 보조 IP 주소 _풀에서 배달됩니다._ 자세한 내용은 [아웃바운드 메시지의 고위험 전송 풀](high-risk-delivery-pool-for-outbound-messages.md)을 참조하세요.

- **원본 IP 주소 신뢰도** 모니터링 : Microsoft 365 타사 IP 차단 목록을 쿼리합니다. 아웃바운드 전자 메일에 사용하는 IP 주소가 이러한 목록에 표시될 경우 경고가 생성됩니다. 이 모니터링을 통해 스팸으로 인해 신뢰도 저하가 발생할 때 신속하게 대응할 수 있습니다. 경고가 생성될 때 차단 목록에서 IP 주소를 제거하는 방법을 간략하게 설명하는 내부 설명서가 있습니다.

- **스팸을 너무** 많이 보내는 계정 사용 안 하도록 설정: 아웃바운드 스팸을 고위험 배달 풀로 분류하는 경우에도 계정(종종 손상된 계정)이 스팸을 무기한 보내지 못하도록 허용할 <sup>\*</sup> 수 없습니다. 스팸을 보내는 계정을 모니터링하며, 공개되지 않은 제한을 초과하면 해당 계정이 전자 메일을 보내지 차단됩니다. 개별 사용자와 전체 테넌트에 대해 서로 다른 임계값이 있습니다.

- **너무 빨리** 전자 메일을 보내는 계정을 사용할 수 없습니다. 스팸으로 표시된 메시지를 검색하는 제한 외에도 아웃바운드 메시지의 스팸 필터링 판정에 관계없이 전체 아웃바운드 메시지 제한에 도달할 때 계정을 차단하는 제한도 <sup>\*</sup> 있습니다. 손상된 계정은 스팸 필터에서 누락된 제로 데이(이전에 인식할 수 없는) 스팸을 보낼 수 있습니다. 합법적인 대량 메일 캠페인과 스팸 캠페인을 식별하기가 어려울 수 있기 때문에 이러한 제한은 잠재적인 손상을 최소화하는 데 도움이 됩니다.

<sup>\*</sup> 스태머가 시스템을 게임할 수 없는 정확한 제한을 보급하지 않습니다. 따라서 필요한 경우 제한을 늘리거나 낮출 수 있습니다. 이 제한은 평균 비즈니스 사용자가 해당 제한을 초과하지 못하도록 할 만큼 높고 스위머로 인한 손상을 포함할 수 있을 만큼 낮습니다.

## <a name="recommendations-for-customers-who-want-to-send-mass-mailings-through-eop"></a>권장 사항 메일을 보내고자 하는 고객을 위한 서비스입니다.

대량의 전자 메일을 보내고자 하는 고객과 받는 사람 취득 관행이 좋지 않은 대량 전자 메일 보낸 사람으로부터 서비스를 보호하는 것은 어려운 일입니다. 타사 IP 차단 Microsoft 365 전자 메일 원본에 액세스하는 비용이 너무 많은 전자 메일을 보내는 사용자를 차단하는 것보다 많습니다.

Exchange Online [서비스](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)설명에 설명된 바와 같이 EOP를 사용하여 대량 전자 메일을 보내는 것은 서비스의 지원되는 사용이 아니며 "최선의" 기준으로만 허용됩니다. 대량 전자 메일을 보내고자 하는 고객의 경우 다음 솔루션을 권장합니다.

- 사내 전자 메일 서버를 통해 대량 전자 메일 **보내기:** 고객은 대량 메일에 대한 자체 전자 메일 인프라를 유지 관리합니다.

- **타사 대량** 전자 메일 공급자 사용: 대량 메일을 보내는 데 사용할 수 있는 여러 타사 대량 전자 메일 솔루션 공급자가 있습니다. 이러한 회사는 좋은 전자 메일 전송 사례를 보장하기 위해 고객과 협력하는 데 많은 관심이 있습니다.

메시징, 모바일, 맬웨어 방지 작업 그룹(MAAWG)은 에 해당 멤버 자격명을 <https://www.maawg.org/about/roster> 게시합니다. 여러 대량 전자 메일 공급자가 목록에 있으며 인터넷 시민을 담당하는 것으로 알려져 있습니다.
