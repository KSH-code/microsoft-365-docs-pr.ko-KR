---
title: 메시지에서 SCL에 메일 흐름 규칙 사용
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: Exchange Online Protection에서 메시지를 식별하고 메시지의 SCL(스팸 지수)을 설정하는 메일 흐름 규칙(전송 규칙)을 만드는 방법을 알아보세요.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1d7d1de194d8529fd3cf3e2d1da68c1f928ffcfa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921135"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages-in-eop"></a>메일 흐름 규칙을 사용하여 EOP의 메시지에서 SCL(스팸 지수) 설정

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서 EOP는 스팸 방지 정책(스팸 필터 정책 또는 콘텐츠 필터 정책)을 사용하여 인바운드 메시지에서 스팸을 검색합니다. 자세한 내용은 [EOP에서 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.

스팸 필터링을 통해 검색되기 전에 특정 메시지를 스팸으로 표시하거나 스팸 필터링을 건너뛰게 하려는 경우 메일 흐름 규칙(전송 규칙)을 만들어 메시지를 식별하고 SCL(스팸 지수)을 설정할 수 있습니다. SCL에 대한 자세한 내용은 [EOP의 SCL(스팸 지수)을 참조하세요.](spam-confidence-levels.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- 이 문서의 절차를 수행하려면 먼저 Exchange Online 또는 Exchange Online Protection에서 사용 권한을 할당해야 합니다. 특히 조직 관리, 준수 관리(전역 관리자) 및  레코드 관리 역할 그룹에  기본적으로 할당되는 전송 규칙 역할이 필요합니다. 

  자세한 내용은 아래 항목을 참조하세요.

  - [Exchange Online의 사용 권한](/exchange/permissions-exo/permissions-exo)
  - [독립 실행형 EOP의 사용 권한](feature-permissions-in-eop.md)
  - [EAC를 사용하여 역할 그룹의 구성원 목록 수정](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Exchange Online에서 EAC를 열하려면 [Exchange Online의 Exchange 관리 센터를 참조하세요.](/Exchange/exchange-admin-center) 독립 실행형 EOP에서 EAC를 열하려면 독립 실행형 [EOP의 Exchange 관리 센터를 참조하세요.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요. 독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.

- Exchange Online 및 Exchange Online Protection의 메일 흐름 규칙에 대한 자세한 내용은 Exchange Online의 메일 흐름 [규칙(전송 규칙)을 참조하세요.](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a>EAC를 사용하여 메시지의 SCL을 설정하는 메일 흐름 규칙 만들기

1. EAC에서 **메일 흐름** \> **규칙** 으로 이동합니다.

2. 추가 **아이콘** ![ 추가를 ](../../media/ITPro-EAC-AddIcon.png) 클릭한 다음 새 규칙 만들기 **를 선택합니다.**

3. 새 **규칙** 페이지가 열리면 다음 설정을 구성합니다.

   - **이름:** 규칙에 대한 설명이 있는 고유한 이름을 입력합니다.

   - 다른 **옵션을 클릭합니다.**

   - **다음의 경우** 이 규칙을 적용합니다. 메시지를 식별하는 조건을 하나 이상 선택합니다. 자세한 내용은 Exchange Online의 메일 흐름 규칙 조건 및 [예외(조건자)를 참조하세요.](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

   - **다음 작업을 합니다.** **메시지 속성** 수정 \> **SCL(스팸 지수)** 설정을 선택합니다. 나타나는 **SCL 지정** 대화 상자에서 다음 값 중 하나를 구성합니다.

   - **스팸 필터링 무시:** 메시지는 스팸 필터링을 건너뜁합니다.

     > [!CAUTION]
     > 메시지가 스팸 필터링을 건너뛸 수 있도록 허용하는 데 주의해야 합니다. 공격자는 이 취약성을 사용하여 피싱 및 기타 악성 메시지를 조직으로 보낼 수 있습니다. 메일 흐름 규칙에는 보낸 사람 전자 메일 주소 또는 도메인 이상이 필요합니다. 자세한 내용은 EOP에서 수신이 가능한 보낸 사람 [목록 만들기를 참조하세요.](create-safe-sender-lists-in-office-365.md)

   - **0~4:** 추가 처리를 위해 메시지가 스팸 필터링을 통해 전송됩니다.

   - **5 또는 6**: 메시지가 스팸으로 **표시됩니다.** 스팸 방지 정책에서 스팸  필터링 판정에 대해 구성한 작업이 메시지에 적용됩니다(기본값은 정크 메일 폴더로 메시지 **이동).**

   - **7 ~9:** 메시지가 높은 지수 **스팸으로 표시됩니다.** 스팸 방지 정책에서 높은  지수의 스팸 필터링 판정에 대해 구성한 작업이 메시지에 적용됩니다(기본값은 정크 메일 폴더로 메시지 **이동).**

4. 규칙에 사용할 추가 속성을 지정합니다. 작업을 마쳤으면 **저장** 을 클릭합니다.

## <a name="how-do-you-know-this-worked"></a>작동 여부는 어떻게 확인하나요?

이 절차가 올바르게 작동하고 있는지 확인하려면 조직 내부의 사람에게 전자 메일 메시지를 보내고 메시지에 대해 수행된 작업이 예상대로 수행된지 확인합니다. 예를 들어 **SCL(스팸** 지수)을 스팸 필터링 무시로 설정한 경우 메시지를 지정된 받는 사람의 받은 편지함으로 보내야 합니다. 그러나 **SCL(스팸** 지수)을 **9로** 설정하고  해당 스팸 방지 정책에 대한 높은 지수 스팸 작업이 메시지를 정크 메일 폴더로 이동하는 경우 지정된 받는 사람의 정크 메일 폴더로 메시지를 보내야 합니다.