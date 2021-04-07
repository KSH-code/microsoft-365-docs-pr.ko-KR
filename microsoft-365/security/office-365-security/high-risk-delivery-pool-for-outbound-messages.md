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
ms.openlocfilehash: ac3469150ef5cf5c1040fcddf7f0bc95e7a18805
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599914"
---
# <a name="outbound-delivery-pools"></a>아웃바운드 배달 풀

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft 365 데이터 센터의 전자 메일 서버가 일시적으로 스팸을 보내지 않을 수 있습니다. 예를 들어 Microsoft 365를 통해 아웃바운드 메일을 전송하거나 손상된 Microsoft 365 계정을 보내는 사내 전자 메일 조직의 맬웨어 또는 악의적인 스팸 공격이 있습니다. 또한 공격자는 Microsoft 365 전달을 통해 메시지를 릴레이하여 검색을 방지하려고 합니다.

이러한 시나리오는 영향을 받는 Microsoft 365 데이터 센터 서버의 IP 주소가 타사 차단 목록에 나타날 수 있습니다. 이러한 차단 목록을 사용하는 대상 전자 메일 조직은 해당 메시지 원본의 전자 메일을 거부합니다.

## <a name="high-risk-delivery-pool"></a>고위험 배달 풀
이를 방지하기 위해 스팸으로 확인되거나 서비스 또는 아웃바운드 스팸 정책의 전송 제한을 초과하는 Microsoft [](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) 365 데이터 센터 서버의 모든 아웃바운드 메시지가 위험도가 높은 배달 풀을 통해 _전송됩니다._ [](configure-the-outbound-spam-policy.md)

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
