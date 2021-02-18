---
title: 전자 메일 메시지의 안전 팁
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- BCS160
ms.assetid: fb4f8e49-0468-4be2-8fa6-99501f1ad9d5
ms.collection:
- M365-security-compliance
description: 전자 메일 맨 위에 보안 팁을 추가하여 EOP 및 Office 365에서 스팸, 피싱 및 맬웨어 방지를 보호하는 방법에 대해 알아보세요.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2eae3f17d4ba9b72383bf1b8864a136cd9e7b2b8
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288564"
---
# <a name="safety-tips-in-email-messages"></a>전자 메일 메시지의 안전 팁

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

EOP(Exchange Online Protection) 및 Microsoft 365는 스팸, 피싱 및 맬웨어 방지로 보호합니다. 오늘날 이러한 공격 중 일부는 매우 잘 만들어 합법적인 것으로 보이고 있습니다. 정크 메일 폴더로 메시지를 보내는 것만으로는 충분하지 않습니다. 이제 Outlook 또는 웹상의 Outlook 또는 전자 메일 클라이언트에서 전자 메일을 확인할 때 EOP는 자동으로 보낸 사람 확인을 수행하고 전자 메일 맨 위에 보안 팁을 추가합니다.

보안 팁이 열리고 메시지 본문에 직접 삽입될 수 있기 때문에 Outlook의 보안 팁은 사용 중이 아닌 Outlook 버전에 의존하지 않습니다. 즉, 사용 하는 모든 전자 메일 클라이언트에 보안 팁이 표시 됩니다. 전자 메일 필터 수준에서 수행하며 메일 클라이언트 수준에서 렌더링되지는 않습니다. 따라서 모든 버전의 Outlook에 표시될 뿐만 아니라 모든 전자 메일 클라이언트에도 표시될 수 있습니다.

안전 팁(색으로 코딩된 메시지)은 유해할 수 있는 메시지에 대해 경고합니다. 받은 편지함의 대부분의 메시지에는 안전 팁이 없습니다. EOP 및 Microsoft 365에 스팸, 피싱 및 맬웨어 공격을 방지하는 데 필요한 정보가 있는 경우만 볼 수 있습니다. 받은 편지함에서 안전 팁이 표시될 경우 다음 예제를 사용하여 각 안전 팁 유형에 대해 자세히 알아보면 됩니다.

- 의심스러운 메일(빨간색 안전 팁)

    ![빨간색 안전 팁을 보여 주는 스크린샷입니다.](../../media/5078a0be-e556-44a1-b169-09d780d26898.png)

    전자 메일의 빨간색 안전 팁은 받은 메시지에 피싱 사기와 같은 의심스러운 정보가 포함되어 있는 것입니다. 이 종류의 전자 메일 메시지는 열지 않고 받은 편지함에서 삭제하는 것이 좋습니다.

- 안전한 메일(녹색 안전 팁)

    ![녹색 안전 팁을 보여 주는 스크린샷.](../../media/acbc11d0-f626-4848-9fbf-66eeeda3f803.png)

    안전하지 않은 메시지 외에도 안전하지 않은 안전 팁으로 신뢰하는 보낸 사람이 보낸 유효한 메시지에 대해 알려드려야 합니다. 전자 메일의 녹색 안전 팁은 메시지를 보낸 사람이 확인하여 안전한지 확인했다는 의미입니다. Microsoft는 재무 조직 및 자주 스푸핑되거나 가장되는 기타 조직을 포함하는 신뢰할 수 있는 보낸 사람 목록을 유지 관리합니다.

## <a name="working-with-safety-tips"></a>안전 팁 작업

보안 팁은 모든 메시지가 수신되지는 않는 경우에도 항상 웹용 Outlook에서 사용하도록 설정됩니다. 관리자는 Outlook과 같은 다른 전자 메일 클라이언트에 대한 보안 팁을 해제할 수 있습니다. 자세한 내용은 [Office 365의 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.

EOP에서 메시지를 분류한 방식에 동의하지 않는 경우(즉, 메시지가 스팸이 아니거나 스팸으로 표시되어 있는 경우) 분석을 위해 Microsoft에 메시지를 제출하여 환경을 개선할 수 있습니다. 자세한 내용은 [Microsoft에 메시지 및 파일 보고를 참조하세요.](report-junk-email-messages-to-microsoft.md) 보안 팁의 피드백 링크를 클릭하여 Microsoft에 직접 의견을 제출하여 개선할 수 있습니다.
