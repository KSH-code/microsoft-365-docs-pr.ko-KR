---
title: 정크 메일과 대량 전자 &apos; 메일의 차이점은 무엇입니까?
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
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 관리자는 EOP(전자 메일)에서 정크 메일(스팸)과 대량 전자 메일(회색 메일) 간의 차이점에 대해 Exchange Online Protection 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e8a896ac3360ccf799dbe34c7e298f76140ee6d5
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60154305"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a>EOP에서 정크 메일과 대량 전자 메일의 차이점은 무엇입니까?

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft 365 사서함이 없는 Exchange Online 또는 EOP(독립 실행형 Exchange Online Protection) 조직에서 고객이 "정크 메일과 대량 전자 메일의 차이점"을 Exchange Online 있습니다. 이 항목에서는 차이점에 대해 설명하고 EOP에서 사용할 수 있는 컨트롤에 대해 설명합니다.

- **정크 메일은** 원치 않는 보편적으로 원치 않는 메시지(올바르게 식별된 경우)인 스팸입니다. 기본적으로 EOP는 원본 전자 메일 서버의 신뢰도에 따라 스팸을 거부합니다. 메시지가 원본 IP 검사를 통과하면 스팸 필터링으로 전송됩니다. 메시지가 스팸 필터링을 통해 스팸으로 분류되는 경우 메시지는 기본적으로 의도한 받는 사람에게 배달되어 정크 메일 폴더로 이동됩니다.

  - 스팸 필터링 판정에 대해 수행할 작업을 구성할 수 있습니다. 자세한 내용은 [EOP에서 스팸 방지 정책 구성을 참조하세요.](configure-your-spam-filter-policies.md)

  - 스팸 필터링 결과와 동의하지 않는 경우 Microsoft에 메시지 및 파일 보고에 설명된 바와 같이 스팸 또는 스팸이 아닌 것으로 고려되는 메시지를 Microsoft에 여러 가지 방법으로 보고할 수 [있습니다.](report-junk-email-messages-to-microsoft.md)

- **대량 전자** 메일(회색 _메일)은_ 분류하기가 더 어렵습니다. 스팸은 지속적인 위협인 반면 대량 전자 메일은 일회성 광고 또는 마케팅 메시지인 경우가 종종 있습니다. 일부 사용자는 대량 전자 메일 메시지를 원하고(실제로는 이를 받기 위해 고의로 등록한 경우) 다른 사용자는 대량 전자 메일을 스팸으로 고려합니다. 예를 들어 일부 사용자는 Contoso Corporation에서 광고 메시지를 받거나 사이버 보안에 대한 예정된 회의에 대한 초대를 받으며, 다른 사용자는 이러한 동일한 메시지를 스팸으로 고려합니다.

  대량 전자 메일을 식별하는 방법에 대한 자세한 내용은 [EOP의 BCL(대량 불만 수준)을 참조하세요.](bulk-complaint-level-values.md)

## <a name="how-to-manage-bulk-email"></a>대량 전자 메일을 관리하는 방법

대량 전자 메일에 대한 혼합된 반응 때문에 모든 조직에 적용되는 범용 지침이 없습니다.

스팸 방지 정책에는 대량 전자 메일을 스팸으로 식별하는 데 사용되는 기본 BCL 임계값이 있습니다. 관리자는 임계값을 늘리거나 낮출 수 있습니다. 자세한 내용은 아래 항목을 참조하세요.

- [EOP에서 스팸 방지 정책을 구성합니다.](configure-your-spam-filter-policies.md)

- [EOP 스팸 방지 정책 설정](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)

간과하기 쉬운 또 다른 옵션: 사용자가 대량 전자 메일 수신에 대해 불만을 표시하지만 EOP에서 스팸 필터링을 통과하는 메시지를 보낸 사람이 보낸 메시지인 경우 사용자는 대량 전자 메일 메시지에서 구독 취소 옵션을 확인하도록 합니다.
