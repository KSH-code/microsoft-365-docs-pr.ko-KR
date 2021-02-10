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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: Microsoft 365 데이터 센터에서 배달 풀을 사용하여 전자 메일 서버의 신뢰도 보호 방법에 대해 자세히 알아보습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5480916f55fc180a6f08d3c420cb92c730e4065b
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167542"
---
# <a name="outbound-delivery-pools"></a>아웃바운드 배달 풀

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender for Office 365 요금제 1 및 계획 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Microsoft 365 데이터 센터의 전자 메일 서버가 일시적으로 스팸을 보내지 않을 수 있습니다. 예를 들어 Microsoft 365 또는 손상된 Microsoft 365 계정을 통해 아웃바운드 메일을 보내는 전자 메일 조직의 맬웨어 또는 악의적인 스팸 공격이 있습니다. 또한 공격자는 Microsoft 365 전달을 통해 메시지를 릴레이하여 검색을 방지하려고 합니다.

이러한 시나리오는 영향을 받는 Microsoft 365 데이터 센터 서버의 IP 주소가 타사 차단 목록에 표시될 수 있습니다. 이러한 차단 목록을 사용하는 대상 전자 메일 조직은 해당 메시지 원본의 전자 메일을 거부합니다.

## <a name="high-risk-delivery-pool"></a>위험 위험이 높은 배달 풀
이를 방지하기 위해 스팸으로 확인되거나 서비스 또는 아웃바운드 스팸 정책의 전송 제한을 초과하는 Microsoft [](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) 365 데이터 센터 서버의 모든 아웃바운드 메시지가 위험도가 높은 배달 풀을 통해 _전송됩니다._ [](configure-the-outbound-spam-policy.md)

위험 수준 배달 풀은 "저품질" 메시지(예: 스팸 및 후방 스캐터)를 보내는 데만 사용되는 아웃바운드 전자 메일에 대한 별도의 IP 주소 [풀입니다.](backscatter-messages-and-eop.md) 위험성 배달 풀을 사용하면 아웃바운드 전자 메일의 일반 IP 주소 풀에서 스팸을 보내지 못하게 할 수 있습니다. 아웃바운드 전자 메일의 일반 IP 주소 풀은 "고품질" 메시지를 보내는 신뢰도 유지 관리로, 이러한 IP 주소가 IP 차단 목록에 표시될 가능성을 줄입니다.

고위험 배달 풀의 IP 주소가 IP 차단 목록에 배치될 가능성은 매우 높지만 이는 디자인에 따라 정해진 것입니다. 많은 전자 메일 조직이 고위험 배달 풀의 메시지를 수락하지 못하기 때문에 의도한 받는 사람에게 배달이 보장되지 않습니다.

자세한 내용은 아웃바운드 스팸 [제어를 참조하세요.](outbound-spam-controls.md)

> [!NOTE]
> 원본 전자 메일 도메인에 A 레코드가 없는 메시지와 공용 DNS에 정의된 MX 레코드가 없는 메시지는 스팸 또는 보내는 제한 처리에 관계없이 항상 높은 위험 배달 풀을 통해 라우팅됩니다.

### <a name="bounce-messages"></a>반송 메시지

아웃바운드 고위험 배달 풀은 모든 배달되지 않은 보고서(NDRS, 반송 메시지, 배달 상태 알림 또는 DSN)에 대한 배달을 관리합니다.

NDRS의 급증에 대한 가능한 원인은 다음과 같습니다.

- 서비스를 사용하는 고객 중 한 명에게 영향을 주는 스푸핑 캠페인입니다.
- 디렉터리 수집 공격.
- 스팸 공격.
- Rogue 전자 메일 서버.

이러한 모든 문제로 인해 서비스에서 처리되는 NDRS 수가 갑자기 증가할 수 있습니다. 대부분의 경우 이러한 NDRS는 다른 전자 메일 서버 및 서비스(후방 스캐터라고도 하는)에 스팸으로 _[나타납니다.](backscatter-messages-and-eop.md)_

## <a name="relay-pool"></a>릴레이 풀

Microsoft 365에서 전달되거나 릴레이되는 메시지는 특수 릴레이 풀을 사용하여 전송됩니다. 최종 대상은 Microsoft 365를 실제 보낸 사람으로 고려하지 않습니다. Microsoft 365에서 전자 메일을 자동 전달하거나 릴레이하는 합법적인 잘못된 시나리오가 있기 때문에 이 트래픽을 격리하는 것이 중요합니다. 위험이 높은 배달 풀과 마찬가지로 별도의 IP 주소 풀이 릴레이된 메일에 사용됩니다. 이 주소 풀은 자주 변경될 수 있으며 게시되지 않습니다.

Microsoft 365는 전달된 메시지를 배달할 수 있도록 원래 보낸 사람이 합법적인지 확인해야 합니다. 이를 위해 전자 메일 인증(SPF, DKIM 및 DMARC)은 메시지가 전달된 경우 전달해야 합니다. 보낸 사람 인증을 할 수 있는 경우 보낸 사람 다시 덮어기를 사용하여 수신자가 전달된 메시지가 신뢰할 수 있는 원본에서 보낸 메시지인지 알 수 있도록 합니다. 보내는 도메인이 [SRS(Sender Rewriting Scheme)에서](https://docs.microsoft.com/office365/troubleshoot/antispam/sender-rewriting-scheme)인증을 통과하도록 하는 데 도움이 되는 작업 및 작동 방식에 대해 자세히 읽을 수 있습니다.
