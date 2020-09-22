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
description: Microsoft 365 데이터 센터에서 전자 메일 서버의 신뢰도를 보호 하기 위해 배달 풀을 사용 하는 방법을 알아봅니다.
ms.openlocfilehash: b3016be7c1887536fe3e742b5ab4ec598b6a5f89
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201492"
---
# <a name="outbound-delivery-pools"></a>아웃바운드 배달 풀

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Microsoft 365 데이터 센터의 전자 메일 서버가 일시적으로 스팸 메일을 guilty 수도 있습니다. 예를 들어 Microsoft 365를 통해 아웃 바운드 메일을 보내거나 Microsoft 365 계정을 손상 시킨 온-프레미스 전자 메일 조직의 맬웨어 또는 악성 스팸 공격이 발생 합니다. 또한 공격자는 Microsoft 365 전달을 통해 메시지를 릴레이 하 여 검색을 방지 합니다.

이러한 시나리오로 인해 영향을 받는 Microsoft 365 datacenter server의 IP 주소가 타사 차단 목록에 표시 될 수 있습니다. 이러한 차단 목록을 사용 하는 대상 전자 메일 조직은 해당 메시지 원본의 전자 메일을 거부 합니다.

## <a name="high-risk-delivery-pool"></a>위험성이 높은 배달 풀
이를 방지 하기 위해 스팸으로 확인 되거나 [서비스](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) 의 전송 제한을 초과 하는 Microsoft 365 datacenter servers의 모든 아웃 바운드 메시지는 _높은 위험 배달 풀_ [을 통해 전송 됩니다.](configure-the-outbound-spam-policy.md)

높은 위험 배달 풀은 "낮은 품질" 메시지 (예: 스팸 및 [백 분산](backscatter-messages-and-eop.md))를 보내는 데만 사용 되는 아웃 바운드 전자 메일에 대 한 별도의 IP 주소 풀입니다. 높은 위험 배달 풀을 사용 하면 아웃 바운드 전자 메일에 대 한 일반 IP 주소 풀이 스팸을 보내지 못합니다. 아웃 바운드 전자 메일의 일반 IP 주소 풀은 "고품질" 메시지를 보내는 신뢰도를 유지 하므로 이러한 IP 주소가 IP 차단 목록에 표시 되는 가능성이 줄어듭니다.

높은 위험 배달 풀의 IP 주소가 IP 차단 목록에 남아 있는 것은 매우 실질적인 일 이지만 이것은 의도적으로 설계 된 것입니다. 대부분의 전자 메일 조직에서는 높은 위험 배달 풀의 메시지를 수락 하지 않으므로 원하는 받는 사람에 게 배달할 수 없습니다.

자세한 내용은 [Control outbound 스팸](outbound-spam-controls.md)을 참조 하십시오.

> [!NOTE]
> 원본 전자 메일 도메인에 레코드가 없고 공용 DNS에 정의 된 MX 레코드가 없는 메시지는 항상 스팸 또는 전송 제한 처리에 관계 없이 위험성이 높은 배달 풀을 통해 라우팅됩니다.

### <a name="bounce-messages"></a>바운스 메시지

아웃 바운드 높은 위험 배달 풀은 모든 배달 못 함 보고서 (Ndr, 바운스 메시지, 배달 상태 알림 또는 Dsn)에 대 한 배달을 관리 합니다.

Ndr의 서 지에 대 한 가능한 원인은 다음과 같습니다.

- 서비스를 사용 하는 고객 중 한 명에 게 영향을 주는 스푸핑 캠페인
- 디렉터리 수집 공격입니다.
- 스팸 공격
- Rogue 전자 메일 서버

이러한 모든 문제로 인해 서비스에서 처리 하는 Ndr 수가 급격 하 게 증가할 수 있습니다. 여러 번 이러한 ndr은 다른 전자 메일 서버 및 서비스에 스팸으로 표시 됩니다 ( _[후방 산란](backscatter-messages-and-eop.md)_ 이 라고도 함).

## <a name="relay-pool"></a>릴레이 풀

최종 대상이 Microsoft 365를 실제 보낸 사람으로 간주 해서는 안 되므로 Microsoft 365에서 전달 되거나 외부에 릴레이 되는 메시지는 특수 릴레이 풀을 사용 하 여 전송 됩니다. 또한 자동 전달 또는 Microsoft 365에서 전자 메일을 릴레이 하는 잘못 된 시나리오를 제공 하기 때문에이 트래픽을 격리 하는 것이 중요 합니다. 높은 위험 수준 배달 그룹과 마찬가지로 릴레이 된 메일에는 별도의 IP 주소 풀이 사용 됩니다. 이 주소 풀은 자주 변경 될 수 있으므로 게시 되지 않습니다.

Microsoft 365에서는 전달 된 메시지를 안전 하 게 배달할 수 있도록 원래 보낸 사람이 합법적 인지 확인 해야 합니다. 이렇게 하려면 메시지가 도착 했을 때 SPF, DKIM 및 DMARC (전자 메일 인증)가 통과 해야 합니다. 보낸 사람을 인증할 수 있는 경우 보낸 사람 재작성을 사용 하 여 전달 된 메시지가 신뢰할 수 있는 원본에서 온 것 이라는 것을 수신자에 게 알립니다. 전송 도메인이 [보낸 사람 재작성 체계 (SRS)](https://docs.microsoft.com/office365/troubleshoot/antispam/sender-rewriting-scheme)에서 인증을 통과 하는지 확인 하는 데 도움이 되는 방식 및 수행 방법에 대 한 자세한 내용을 확인할 수 있습니다.
