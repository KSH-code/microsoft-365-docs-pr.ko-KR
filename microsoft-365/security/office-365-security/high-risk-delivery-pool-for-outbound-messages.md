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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: 배달 풀을 사용하여 Microsoft 365 데이터 센터에서 전자 메일 서버의 신뢰도를 보호하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 83ea21a9230240f1339513efc75587f3d84733cb
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827740"
---
# <a name="outbound-delivery-pools"></a>아웃바운드 배달 풀

Microsoft 365 데이터 센터의 전자 메일 서버는 스팸 보내기가 일시적으로 잘못 될 수 있습니다. 예를 들어, 온-프레미스 전자 메일 조직의 맬웨어 또는 악의적인 스팸 공격이 Microsoft 365로 아웃바운드 메일을 보내거나 Microsoft 365 계정으로 보호됩니다. 또한 공격자는 Microsoft 365 전달을 통해 메시지를 릴레이하여 검색을 방지하려고 시도합니다.

이러한 시나리오를 통해 영향을 받는 Microsoft 365 데이터 센터 서버의 IP 주소가 타사 차단 목록에 나타나고 있습니다. 이러한 차단 목록을 사용하는 대상 전자 메일 조직은 해당 메시지 원본의 전자 메일을 거부합니다.

## <a name="high-risk-delivery-pool"></a>높은 위험 배달 풀
이를 방지하려면 스팸으로 확인된 Microsoft 365 데이터 센터 서버의 모든 아웃바운드 메시지가 서비스나 아웃바운드 [the service](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) 스팸 정책의 보내기 한도를 [초과하는](configure-the-outbound-spam-policy.md) 모든 아웃바운드 메시지는 _위험성이 높은 배달 풀을 통해 전송됩니다._

위험성이 높은 배달 풀은 "저품질" 메시지(예: 스팸 및 후방 분산)를 보내는 데에만 사용되는 아웃바운드 전자 [메일의 IP 주소 풀로,](backscatter-messages-and-eop.md) 위험성이 높은 배달 풀을 사용하면 아웃바운드 전자 메일에 대한 일반 IP 주소 풀이 스팸을 보내지 않도록 할 수 있습니다. 아웃바운드 전자 메일에 대한 일반 IP 주소 풀에서는 "높은 품질" 메시지의 신뢰도를 유지하므로 이러한 IP 주소가 IP 차단 목록에 표시될 수 있는 확률이 줄어듭니다.

수있어 매우 위험한 배달 풀의 IP 주소가 IP 차단 목록에 남아 있을 수 있지만 의도적으로 많은 전자 메일 조직은 고위험 배달 풀의 메시지를 수락하지 않기 때문에 의도한 받는 사람에게 배달되는 것은 보절되지 않습니다.

자세한 내용은 컨트롤 아웃바운드 [스팸을 참조하세요.](outbound-spam-controls.md)

> [!NOTE]
> 원본 전자 메일 도메인에 A 레코드가 없고 공용 DNS에 정의된 MX 레코드가 없는 메시지는 스팸이나 처리 제한에 관계없이 항상 위험성이 높은 배달 풀을 통해 라우팅됩니다.

### <a name="bounce-messages"></a>반송 메시지

아웃바운드 고위험 배달 풀은 모든 배달 못 함 보고서(NDR, 바운스 메시지, 배달 상태 알림 또는 DSN이라고도 함)에 대한 배달을 관리합니다.

NDR에서 가속화의 가능한 원인은 다음과 같습니다.

- 서비스 사용 고객 중 한 명에 영향을 주는 스푸핑 캠페인입니다.
- 디렉터리 도전 공격입니다.
- 스팸 공격
- Rogue 전자 메일 서버

이러한 모든 문제로 인해 서비스에서 처리하는 NDR의 수가 급증할 수 있습니다. 많은 경우 이러한 NDR은 다른 전자 메일 서버 및 서비스에 스팸(후방 분산이라고도 _[함)으로 나타납니다.](backscatter-messages-and-eop.md)_

## <a name="relay-pool"></a>릴레이 풀

최종 대상은 Microsoft 365를 실제 보낸 사람으로 간주하지 말므로 Microsoft 365에서 전달되거나 릴레이되는 메시지는 특수 릴레이 풀을 사용하여 전송됩니다. 또한 Microsoft 365에서 전자 메일 자동 전달 또는 릴레이와 같은 합법적이고 릴레이하는 데 적합한 시나리오가 있기 때문에 이 트래픽을 격리하는 것이 중요합니다. 높은 위험 배달 풀과 마찬가지로 별도의 IP 주소 풀이 릴레이된 메일에 사용됩니다. 이 주소 풀은 자간 변경될 수 있기 때문에 게시되지 않습니다.

Microsoft 365는 전달된 메시지를 전달할 수 있도록 원래 보낸 사람이 합법적인지 확인해야 합니다. 이러한 작업을 수행하려면 메시지가 Microsoft에 오면 전자 메일 인증(SPF, DKIM, DMARC)을 통과해야 합니다. 보낸 사람 인증이 가능한 경우 Microsoft는 보낸 사람 다시 쓰기를 사용하여 전달된 메시지를 신뢰할 수 있는 곳에서 온 것이라는 사실을 받는 사람을 알릴 수 있도록 합니다. 이 작업 을 수행하는 방법 및 보내는 도메인이 [SRS(Sender Rewriting Scheme)에서 인증을](https://docs.microsoft.com/office365/troubleshoot/antispam/sender-rewriting-scheme)전달하는 데 도움이 되는 작업에 대해 자세한 내용을 읽어보시기 바라며,
