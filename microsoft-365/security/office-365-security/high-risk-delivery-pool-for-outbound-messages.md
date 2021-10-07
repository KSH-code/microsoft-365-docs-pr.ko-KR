---
title: 아웃바운드 배달 풀
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: 배달 풀을 사용하여 데이터 센터에서 전자 메일 서버의 신뢰를 보호하는 Microsoft 365 대해 자세히 알아보습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 75df83b5827fa3c2b5832c634c1de15ab7d619dd
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60205022"
---
# <a name="outbound-delivery-pools"></a>아웃바운드 배달 풀

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

데이터 센터의 전자 메일 Microsoft 365 일시적으로 스팸을 보내지 않을 수 있습니다. 예를 들어 맬웨어 또는 악의적인 스팸 공격은 전자 메일 계정을 통해 아웃바운드 메일을 보내는 Microsoft 365 또는 손상된 Microsoft 365 공격입니다. 또한 공격자는 메시지 전달을 통해 메시지를 릴레이하여 검색을 Microsoft 365 시도합니다.

이러한 시나리오는 영향을 받는 데이터 센터 서버의 IP Microsoft 365 차단 목록에 나타날 수 있습니다. 이러한 차단 목록을 사용하는 대상 전자 메일 조직은 해당 메시지 원본의 전자 메일을 거부합니다.

## <a name="high-risk-delivery-pool"></a>고위험 배달 풀
이를 방지하기 위해 스팸으로 확인되거나 서비스 또는 아웃바운드 스팸 정책의 전송 제한을 초과하는 [](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) Microsoft 365 데이터 [](configure-the-outbound-spam-policy.md) 센터 서버의 모든 아웃바운드 메시지가 위험도가 높은 배달 풀을 통해 _전송됩니다._

고위험 배달 풀은 "낮은 품질" 메시지(예: 스팸 및 후방 스캐터)를 보내는 데만 사용되는 아웃바운드 전자 메일에 대한 별도의 IP [주소 풀입니다.](backscatter-messages-and-eop.md) 높은 위험 배달 풀을 사용하면 아웃바운드 전자 메일의 일반 IP 주소 풀에서 스팸을 보내지 못하게 할 수 있습니다. 아웃바운드 전자 메일의 일반 IP 주소 풀은 "고품질" 메시지를 보내는 신뢰도 유지 관리로, 이러한 IP 주소가 IP 차단 목록에 표시될 가능성을 줄입니다.

고위험 배달 풀의 IP 주소가 IP 차단 목록에 배치될 가능성은 매우 높지만 이는 설계에 따라 지정됩니다. 많은 전자 메일 조직이 고위험 배달 풀의 메시지를 수락하지 못하기 때문에 의도한 받는 사람에게 배달이 보장되지 않습니다.

자세한 내용은 아웃바운드 스팸 [제어를 참조하세요.](outbound-spam-controls.md)

> [!NOTE]
> 원본 전자 메일 도메인에 A 레코드가 없는 메시지와 공용 DNS에 정의된 MX 레코드가 없는 메시지는 스팸 또는 전송 제한 처리에 관계없이 항상 위험도가 높은 배달 풀을 통해 라우팅됩니다.

### <a name="bounce-messages"></a>반송 메시지

아웃바운드 고위험 배달 풀은 모든 배달되지 않은 보고서(NDRs, 반송 메시지, 배달 상태 알림 또는 DSN)의 배달을 관리합니다.

NDRS의 급증에 대한 가능한 원인은 다음과 같습니다.

- 서비스를 사용하는 고객 중 한 명에게 영향을 주는 스푸핑 캠페인입니다.
- 디렉터리 수집 공격.
- 스팸 공격.
- Rogue 전자 메일 서버.

이러한 모든 문제로 인해 서비스에서 처리되는 NDRS 수가 갑자기 증가할 수 있습니다. 대부분의 경우 이러한 NDRS는 다른 전자 메일 서버 및 서비스(후방 스캐터라고도 하는)에 스팸인 _[것으로 나타납니다.](backscatter-messages-and-eop.md)_


### <a name="relay-pool"></a>릴레이 풀

특정 시나리오에서 Microsoft 365 전달되거나 릴레이되는 메시지는 특수 릴레이 풀을 사용하여 전송됩니다. 대상은 실제 보낸 Microsoft 365 고려하지 않습니다. 전자 메일 트래픽을 격리하는 것이 중요합니다. 전자 메일을 전자 메일이 전송되지 않은 경우 자동 전달 또는 릴레이하는 합법적인 잘못된 시나리오가 Microsoft 365. 위험이 높은 배달 풀과 마찬가지로 별도의 IP 주소 풀이 릴레이된 메일에 사용됩니다. 이 주소 풀은 자주 변경될 수 있기 때문에 게시되지 않습니다. 이 주소 풀은 해당 주소 풀에 대해 게시된 SPF 레코드에 Microsoft 365.

Microsoft 365 전달된 메시지를 배달할 수 있도록 원래 보낸 사람이 합법적인지 확인해야 합니다.

릴레이 풀을 사용하지 않도록 전달/릴레이된 메시지는 다음 조건 중 하나를 충족해야 합니다.

- 아웃바운드 보낸 사람이 허용 [도메인에 있습니다.](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)
- SPF는 메시지가 전송되면 Microsoft 365.
- 보낸 사람 도메인의 DKIM은 메시지가 전송되면 Microsoft 365.
 
아웃바운드 서버 IP(릴레이 풀은 40.95.0.0/16 범위에 해당)를 확인하거나 아웃바운드 서버 이름(이름에 "rly"이 사용)을 확인하여 메시지가 릴레이 풀을 통해 전송된 것으로 알 수 있습니다.

보낸 사람을 인증할 수 있는 경우 SRS(Sender Rewriting Scheme)를 사용하여 받는 사람 전자 메일 시스템에서 전달된 메시지가 신뢰할 수 있는 원본에서 전송된 메시지인지 알 수 있도록 합니다. 보내는 도메인이 의 [SRS(Sender Rewriting Scheme)에서](/office365/troubleshoot/antispam/sender-rewriting-scheme)인증을 통과하도록 하는 데 도움이 되는 작업과 작동 방식에 대해 자세히 Office 365.

DKIM이 작동하려면 도메인 보내기에 DKIM을 사용하도록 설정해야 합니다. 예를 들어 fabrikam.com 조직의 contoso.com 도메인에 정의되어 있습니다. 메시지 보낸 사람이 sender@fabrikam.com DKIM을 사용하도록 설정해야 fabrikam.com. DKIM을 사용하여 사용자 지정 도메인에서 보낸 아웃바운드 전자 메일의 유효성을 검사하는 방법을 읽을 [수 있습니다.](use-dkim-to-validate-outbound-email.md)

사용자 지정 도메인을 추가하려면 [Add a domain to Microsoft 365.](../../admin/setup/add-domain.md)

도메인의 MX 레코드가 타사 서비스 또는 사내 전자 메일 서버를 지정하는 경우 커넥터에 대해 향상된 필터링을 [사용해야 합니다.](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) 향상된 필터링은 인바운드 메일에 대해 SPF 유효성 검사가 올바른지 확인하며 릴레이 풀을 통해 전자 메일을 보내지 않도록 합니다.

