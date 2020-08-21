---
title: 정크 &apos; 메일과 대량 전자 메일의 차이점
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
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 관리자는 EOP(Exchange Online Protection)에서 정크 메일(스팸)과 대량 전자 메일(회색 메일) 간의 차이점을 알아보을 수 있습니다.
ms.openlocfilehash: 17e6223175013678f389c0d7624cc4e4f4476f98
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826732"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a>EOP의 정크 메일과 대량 전자 메일의 차이점

Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서 고객이 "정크 메일과 대량 전자 메일은 어떻게 다릅니까?"로 문의합니다. 이 항목에서는 차이점에 대해 설명하고 EOP에서 사용할 수 있는 컨트롤에 대해 설명합니다.

- **정크 메일은** 스팸이며 이 스팸이며 스팸이며 스팸이며 올바르게 확인되어야 하는 경우에 도용됩니다. 기본적으로 EOP는 원본 전자 메일 서버의 신뢰도에 따라 스팸을 거부합니다. 메시지가 원본 IP 검사를 통과하면 스팸 필터링으로 전송됩니다. 스팸 필터링에 의해 메시지가 스팸으로 분류된 경우 메시지는 기본적으로 지정된 받는 사람에게 배달되며 정크 메일 폴더로 이동됩니다.

  - 스팸 필터링 명령에 수행할 작업을 구성할 수 있습니다. 자세한 내용은 [EOP에서 스팸 방지 정책 구성을 참조하세요.](configure-your-spam-filter-policies.md)

  - 스팸 필터링 결과와 이에 동의하면 Microsoft에 보고 메시지 및 파일에 설명된 여러 가지 방법으로 Microsoft에 스팸 또는 스팸이 아닌 메시지를 [보고할 수 있습니다.](report-junk-email-messages-to-microsoft.md)

- **대량 전자** 메일(회색 _메일이라고도_함)은 더욱 어렵습니다. 스팸은 지속적 위협인 경우 대개 일대성 광고 또는 마케팅 메시지입니다. 일부 사용자는 대량 전자 메일 메시지(사실상 이러한 전자 메일을 받도록 의도적으로 등록하여)를 사용하고 있는 사용자도 대량 전자 메일을 스팸으로 간주합니다. 예를 들어 어떤 사용자는 Contoso Corporation에서 광고 메시지를 받거나, 동시 보안이 지출될 예정인 회의의 초대를 받기를 고리키고, 또 어떤 사용자는 이와 동일한 메시지를 스팸으로 간주합니다.

  대량 전자 메일을 식별하는 방법에 대한 자세한 내용은 [EOP의 BCL(대량 부합 수준)을 참조하세요.](bulk-complaint-level-values.md)

## <a name="how-to-manage-bulk-email"></a>대량 전자 메일을 관리하는 방법

대량 전자 메일에 대한 혼합 형제 대조치로 인해 모든 조직에 적용되는 유니버설 지침은 없습니다.

스팸 방지 정책에는 대량 전자 메일을 스팸으로 식별하는 데 사용되는 기본 BCL 임계값이 있습니다. 관리자는 임계값을 늘리거나 낮게 될 수 있습니다. 자세한 내용은 아래 항목을 참조하세요.

- [EOP에서 스팸 방지 정책을 구성합니다.](configure-your-spam-filter-policies.md)

- [EOP 스팸 방지 정책 설정](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

간과할 수 있는 다른 옵션: 사용자가 대량 전자 메일 수신에 대해 사용자가 대량 전자 메일 수신에 대해 만나는 경우 EOP의 스팸 필터링을 통과하는 평소수의 보낸 사람이 보낸 메시지의 경우 사용자가 대량 전자 메일 메시지에서 구독 해제 옵션을 확인하도록 합니다.
