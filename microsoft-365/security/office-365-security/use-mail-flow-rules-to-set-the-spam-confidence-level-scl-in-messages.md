---
title: 메시지의 SCL에 메일 흐름 규칙 사용
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
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: 관리자는 Exchange Online Protection에서 메시지의 SCL을 설정 하는 방법을 확인할 수 있습니다.
ms.openlocfilehash: b7ea9a0f046e5a48f0de8d4ac9ae6d53821f03c0
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895098"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages"></a>메일 흐름 규칙을 사용하여 메시지의 스팸 신뢰 수준(SCL) 설정

Exchange online 사서함이 없는 Office 365 고객 또는 독립 실행형 EOP (Exchange Online Protection) 고객 인 경우 EOP에서는 스팸 방지 정책 (스팸 필터 정책 또는 콘텐츠 필터 정책이 라고도 함)을 사용 하 여 검색을 수행 합니다. 스팸에 대 한 인바운드 메시지입니다. 자세한 내용은 [Office 365의 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.

특정 메시지를 스팸으로 표시 하 여 스팸 필터링으로 검색 하거나 메시지를 표시 하 여 스팸 필터링을 건너뛰도록 하려면 메시지를 식별 하 고 SCL (스팸 지 수)을 설정 하는 메일 흐름 규칙 (전송 규칙이 라고도 함)을 만들 수 있습니다. SCL에 대 한 자세한 내용은 [Office 365에서 scl (스팸](spam-confidence-levels.md)지 수)을 참조 하세요.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- 이러한 절차를 수행 하려면 먼저 Exchange Online에서 사용 권한을 할당 받아야 합니다. 특히 **조직 관리**, **규정 준수 관리**및 **레코드 관리** 역할에 할당 되는 **전송 규칙** 역할을 기본적으로 할당 해야 합니다. 자세한 내용은 [Exchange Online에서 역할 그룹 관리](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)를 참조하세요.

- Exchange Online에서 EAC를 열려면 exchange [online의 exchange 관리 센터](https://docs.microsoft.com/Exchange/exchange-admin-center)를 참조 하세요.

- Exchange Online의 메일 흐름 규칙에 대 한 자세한 내용은 [Exchange online의 메일 흐름 규칙 (전송 규칙)](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) 을 참조 하세요.

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a>EAC를 사용 하 여 메시지의 SCL을 설정 하는 메일 흐름 규칙 만들기

1. EAC에서 **메일 흐름** \> **규칙**으로 이동합니다.

2. ![](../../media/ITPro-EAC-AddIcon.png) 추가 **아이콘 추가를 클릭 한** 다음 **새 규칙 만들기**를 선택 합니다.

3. **새 규칙** 페이지가 열리면 다음 설정을 구성 합니다.

   - **이름**: 규칙에 대 한 설명이 포함 된 고유 이름을 입력 합니다.

   - **기타 옵션**을 클릭 합니다.

   - 다음의 **경우이 규칙 적용**: 메시지를 식별할 조건을 하나 이상 선택 합니다. 자세한 내용은 [메일 흐름 규칙 조건 및 예외 (조건자)에서 Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)을 참조 하세요.

   - **다음을 수행**합니다. **메시지 속성** \> 수정을 선택 하 여 **SCL (스팸 지 수)을 설정**합니다. **SCL 지정** 대화 상자가 나타나면 다음 값 중 하나를 구성 합니다.

   - **스팸 필터링 바이패스**: 그러면 SCL이-1로 설정 되므로 메시지는 스팸 필터링을 건너뜁니다.

     > [!CAUTION]
     > 스팸 필터링을 건너뛰도록 메시지를 허용 하는 경우에 특히 주의 해야 합니다. 공격자는이 보안 문제를 사용 하 여 피싱 및 기타 악의적인 메시지를 조직에 보낼 수 있습니다. 메일 흐름 규칙은 보낸 사람의 전자 메일 주소 또는 도메인을 초과 하는 경우에만 필요 합니다. 자세한 내용은 [Office 365에서 수신 허용-보낸 사람 목록 만들기](create-safe-sender-lists-in-office-365.md)를 참조 하세요.

   - **0 ~ 4**: 추가 처리를 위해 스팸 필터링을 통해 메시지가 전송 됩니다.

   - **5 또는 6**: 메시지가 **스팸으로**표시 됩니다. 스팸 방지 정책에서 **스팸** 필터링 verdicts에 대해 구성한 작업이 메시지에 적용 됩니다 (기본값은 **정크 메일 폴더로 메시지 이동**).

   - **7-9**: 메시지가 **높은 신뢰도 스팸으로**표시 됩니다. 스팸 방지 정책에서 **높은 신뢰도의 스팸** 필터링 verdicts에 대해 구성한 작업은 메시지에 적용 됩니다 (기본값은 **정크 메일 폴더로 메시지 이동**).

4. 규칙에 대해 원하는 추가 속성을 지정 합니다. 작업을 마친 후 **저장**을 클릭합니다.

## <a name="how-do-you-know-this-worked"></a>작동 여부는 어떻게 확인하나요?

이 프로시저가 제대로 작동 하는지 확인 하려면 조직 내부의 사람에 게 전자 메일 메시지를 보내고 메시지에 대해 수행 된 작업이 예상 대로 진행 되는지 확인 합니다. 예를 들어 **SCL (스팸** 지 수)이 **스팸 필터링을 무시**하도록 설정 하는 경우 메시지를 지정 된 받는 사람의 받은 편지 함으로 보내야 합니다. 그러나 **SCL (스팸** 지 수)을 **9**로 설정 하 고 해당 콘텐츠 필터 정책에 대 한 **신뢰도가 높은 스팸** 작업을 정크 메일 폴더로 이동 하는 경우에는 해당 메시지를 지정 된 받는 사람의 정크 메일 폴더로 보내야 합니다.
