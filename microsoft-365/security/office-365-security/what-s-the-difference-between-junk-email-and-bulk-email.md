---
title: 정크 메일과 대량 전자 메일의 차이점
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
description: 이 항목에서는 정크 메일 (스팸) 및 대량 전자 메일의 차이점 및 Office 365의 관련 컨트롤에 대해 설명 합니다.
ms.openlocfilehash: 15ca00b007ef0b8470e1b30608a695a90bd638b2
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630836"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email"></a>정크 메일과 대량 전자 메일의 차이점

Exchange online 사서함이 없는 Microsoft 365 고객에 게 사서함이 있는 경우 "정크 메일 및 대량 전자 메일의 차이점은 무엇 인가요?" 라는 메시지가 표시 되는 경우가 있습니다. 이 항목에서는 차이점에 대해 설명 하 고 EOP에서 사용할 수 있는 컨트롤에 대해 설명 합니다.

- **정크 메일** 은 원치 않는, 전체적으로 원치 않는 메시지 (올바르게 식별 된 경우)입니다. 기본적으로 EOP은 원본 전자 메일 서버의 신뢰도에 따라 스팸을 거부 합니다. 메시지가 원본 IP 검사를 통과 하면 스팸 필터링으로 전송 됩니다. 메시지가 스팸 필터링에 의해 스팸으로 분류 되는 경우 메시지는 기본적으로 받는 사람에 게 배달 되 고 정크 메일 폴더로 이동 됩니다.

  - 스팸 필터링 verdicts에 대해 수행할 작업을 구성할 수 있습니다. 자세한 내용은 [Office 365에서 스팸 방지 정책 구성을](configure-your-spam-filter-policies.md)참조 하세요.

  - 스팸 필터링 결과이 만족 스 럽 지 않은 경우 [microsoft에 보고서 메시지 및 파일](report-junk-email-messages-to-microsoft.md)에 설명 된 것 처럼 스팸을 스팸 또는 스팸이 아닌 것으로 간주 하는 메시지를 microsoft에 보고할 수 있습니다.

- **대량 전자 메일** ( _회색 메일이_라고도 함)은 분류 하기가 더 어렵습니다. 스팸은 일정 한 위협이 되는 반면, 대량 전자 메일은 종종 일회성 광고 또는 마케팅 메시지입니다. 일부 사용자는 대량 전자 메일 메시지를 전송 하 고, 실제로는이를 수신 하도록 의도적으로 등록 되어 있으며, 다른 사용자가 스팸을 대량으로 전자 메일로 간주 합니다. 예를 들어 일부 사용자는 사이버 security에서 다가오는 전화 회의에 대 한 알림 메시지를 받고, 다른 사용자는 이러한 동일한 메시지를 스팸으로 간주 하려고 합니다.

  대량 전자 메일을 식별 하는 방법에 대 한 자세한 내용은 [Office 365에서 BCL (대량 불만 수준)](bulk-complaint-level-values.md)을 참조 하세요.

## <a name="how-to-manage-bulk-email"></a>대량 전자 메일을 관리하는 방법

대량 전자 메일에 대 한 여러 반응으로 인해 모든 조직에 적용 되는 범용 지침은 없습니다.

스팸 방지 정책에는 대량 전자 메일을 스팸으로 식별 하는 데 사용 되는 기본 BCL 임계값이 있습니다. 관리자가 임계값을 늘리거나 낮출 수 있습니다. 자세한 내용은 다음 항목을 참조하세요.

- [Office 365에서 스팸 방지 정책을 구성](configure-your-spam-filter-policies.md)합니다.

- [EOP 스팸 방지 정책 설정](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

간과 하기 쉬운 다른 옵션: 사용자가 대량 전자 메일 수신에 대 한 정보를 complains 메시지는 EOP의 스팸 필터링을 통과 하는 신뢰할 수 있는 보낸 사람 으로부터 온 것 이며, 사용자가 대량 전자 메일 메시지에서 구독 취소 옵션을 확인 하도록 합니다.
