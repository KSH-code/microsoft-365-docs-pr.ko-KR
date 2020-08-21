---
title: 메시지에서 SCL로 메일 전송 규칙 사용
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: Exchange Online Protection에서 메일 흐름 규칙(전송 규칙)을 사용하여 메시지를 식별하고 메시지의 SCL(스팸 지수)을 설정하는 방법을 설명합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 67a4c25a1006e9b1554cf8ffbc2d5e29b4063752
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827376"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages-in-eop"></a>메일 흐름 규칙을 사용하여 EOP 메시지의 스팸 신뢰 수준(SCL) 설정

Exchange Online 사서함이 있는 Microsoft 365 조직에서 EOP는 스팸 방지 정책(스팸 필터 정책 또는 콘텐츠 필터 정책)을 사용하여 인바운드 메시지에서 스팸을 검사합니다. 자세한 내용은 [EOP에서 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.

특정 메시지가 스팸 필터링으로 검색되기 전에 도와도 스팸으로 표시하거나 스팸 필터링을 건너뛰기 위해 메시지를 표시하려는 경우 메일 흐름 규칙(전송 규칙이라고도 함)을 만들고 메시지를 식별하고 SCL(스팸 지수)을 설정할 수 있습니다. SCL에 대한 자세한 내용은 [EOP의 SCL(스팸 지수)을 참조하세요.](spam-confidence-levels.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- 이러한 절차를 수행하려면 Exchange Online에서 사용 권한을 할당해야 합니다. 특히 조직 **관리,** 준수 관리 및 **레코드** 관리 **역할에는**할당된 전송 규칙 역할을 **할당받아도 기본적으로 할당되어** 있어야 합니다. 자세한 내용은 [Exchange Online에서 역할 그룹 관리](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)를 참조하세요.

- Exchange Online에서 EAC를 열려면 Exchange Online의 [Exchange 관리 센터를 참조하세요.](https://docs.microsoft.com/Exchange/exchange-admin-center)

- Exchange Online의 메일 흐름 규칙에 대한 자세한 내용은 Exchange [Online의 메일 흐름 규칙(전송 규칙)을 참조하세요.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a>EAC를 사용하여 메시지의 SCL을 설정하는 메일 흐름 규칙 만들기

1. EAC에서 **메일 흐름** \> **규칙**으로 이동합니다.

2. 아이콘 **추가를** ![ 클릭한 다음 새 규칙 ](../../media/ITPro-EAC-AddIcon.png) **만들기를 선택합니다.**

3. ** 새** 규칙 페이지에서 다음 설정을 구성합니다.

   - **이름:** 규칙을 설명하는 고유한 이름을 입력합니다.

   - 기타 **옵션을 클릭합니다.**

   - **다음의 경우 이 규칙을**적용하려면 하나 이상의 조건을 선택하여 메시지를 식별합니다. 자세한 내용은 [Exchange Online에서 메일 흐름 규칙 조건 및 예외(조건자)를 참조하세요.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

   - **다음 단계를** **수행합니다. 메시지** \> **속성을 선택하면 SCL(스팸 지수)이 설정되었습니다.** **나타나는 SCL** 지정 대화 상자에서 다음 값 중 하나를 구성합니다.

   - **스팸 필터링 무시**: 메시지가 스팸 필터링을 건너뜁니다.

     > [!CAUTION]
     > 메시지가 스팸 필터링을 건너뛸 수 있도록 하는 경우 매우 주의해야 합니다. 공격자는 이 취약성을 사용하여 피싱 및 기타 악성 메시지를 조직에 보낼 수 있습니다. 메일 흐름 규칙에는 보낸 사람의 전자 메일 주소 또는 도메인 만 둘 이상이 필요합니다. 자세한 내용은 [EOP에서 수신 허용 - 보낸 사람 목록 만들기를 참조하세요.](create-safe-sender-lists-in-office-365.md)

   - **0 ~ 4:** 메시지가 추가 처리를 위해 스팸 필터링을 통해 전송됩니다.

   - **5 또는 6**: 메시지가 스팸으로 **표시됩니다.** 스팸 방지 정책에서 스팸 필터링 **결과에** 대해 구성한 작업은 메시지에 적용됩니다(기본값은 **메시지를 정크 메일 폴더로 이동).**

   - **7~9:** 메시지가 높은 **신뢰도의 스팸으로 표시됩니다.** 스팸 방지 정책에서 높은 **스팸** 필터링 결과에 대해 구성한 작업은 메시지에 적용됩니다(기본값은 **메시지를 정크 메일 폴더로 이동).**

4. 규칙에 사용할 추가 속성을 지정합니다. 작업을 마쳤으면 **저장**을 클릭합니다.

## <a name="how-do-you-know-this-worked"></a>작동 여부는 어떻게 확인하나요?

이 절차가 제대로 작동하는지 확인하려면 조직 내부의 누재자에게 전자 메일 메시지를 보내고 메시지에 대해 수행된 작업이 예상대로 수행되는지 확인합니다. 예를 들어 **스팸 필터링 무시하도록 SCL(스팸 지수)을** **설정한**경우 해당 메시지는 지정된 받는 사람의 받은 편지함으로 보내지게 됩니다. 그러나 해당 스팸 방지 정책에 대한 스팸 지수(SCL)를 **High confidence spam** **9로**설정하고 해당 스팸 방지 정책에 대한 높은 신뢰도 스팸 작업을 설정한 경우 지정된 받는 사람의 정크 메일 폴더로 메시지가 전송됩니다. **set the spam confidence level (SCL)**
