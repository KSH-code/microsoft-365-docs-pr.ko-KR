---
title: 메일 흐름 규칙을 사용 하 여 대량 전자 메일 필터링
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: 관리자는 EOP (Exchange Online Protection)에서 메일 흐름 규칙 (전송 규칙)을 사용 하 여 대량 메일 (회색 메일)을 식별 하 고 필터링 하는 방법을 알 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bb305551db1e86d8d6eccf5e95cdaad29e6711ef
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208528"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-eop"></a>메일 흐름 규칙을 사용 하 여 EOP에서 대량 전자 메일 필터링

Exchange online 사서함이 없는 Microsoft 365 조직, EOP (독립 실행형 Exchange Online Protection) 조직의 사서함이 있는 EOP에서는 스팸 방지 정책 (스팸 필터 정책 또는 콘텐츠 필터 정책이 라고도 함)을 사용 하 여 스팸 및 대량 메일 (회색 메일이 라고도 함)에 대 한 인바운드 메시지를 검사 합니다. 자세한 내용은 [EOP에서 스팸 방지 정책 구성을](configure-your-spam-filter-policies.md)참조 하세요.

대량 메일을 필터링 하는 옵션을 추가로 원하는 경우 메일 흐름 규칙 (전송 규칙이 라고도 함)을 만들어 대량 메일에서 자주 발견 되는 텍스트 패턴이 나 구를 검색 하 고 해당 메시지를 스팸으로 표시할 수 있습니다. 대량 메일에 대 한 자세한 내용은 [정크 메일과 대량 전자 메일의 차이점](what-s-the-difference-between-junk-email-and-bulk-email.md) 및 [EOP의 BCL (대량 불만 수준)](bulk-complaint-level-values.md)을 참조 하세요.

이 항목에서는 EAC (exchange 관리 센터) 및 PowerShell (exchange online 사서함이 없는 조직의 경우 exchange Online의 사서함이 있는 Microsoft 365 조 직의 경우 exchange online PowerShell)에서 이러한 메일 흐름 규칙을 만드는 방법에 대해 설명 합니다.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 사항은 무엇인가요?

- 다음 절차를 수행 하려면 먼저 사용 권한을 할당 받아야 합니다.

  - Exchange Online에서 [Exchange online의](https://docs.microsoft.com/Exchange/permissions-exo/feature-permissions)"메일 흐름" 항목을 참조 하십시오.
  
  - 독립 실행형 EOP에서는 기본적으로 OrganizationManagement, ComplianceManagement 및 레코드 관리 역할에 할당 되는 전송 규칙 역할이 필요 합니다. 자세한 내용은 [권한 독립 실행형 EOP의 사용 권한을](feature-permissions-in-eop.md) 참조 하 고 [EAC를 사용 하 여 역할 그룹의 구성원 목록을 수정](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)합니다.

- Exchange Online에서 EAC를 열려면 exchange [online의 exchange 관리 센터](https://docs.microsoft.com/Exchange/exchange-admin-center)를 참조 하세요. 독립 실행형 EOP에서 EAC를 열려면 [독립 실행형 EOP에서 Exchange 관리 센터](exchange-admin-center-in-exchange-online-protection-eop.md)를 참조 하세요.

- Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결하기](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)를 참조하세요. Exchange Online Protection PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결하기](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)를 참조하세요.

- Exchange Online 및 독립 실행형 EOP의 메일 흐름 규칙에 대 한 자세한 내용은 다음 항목을 참조 하십시오.

  - [Exchange Online의 메일 흐름 규칙 (전송 규칙)](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [메일 흐름 규칙 조건 및 예외 (조건자)가 Exchange Online에 있습니다.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Exchange Online의 메일 흐름 규칙 동작](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- 예를 들어 대량 메일을 식별 하는 데 사용 되는 단어 및 텍스트 패턴 목록은 포괄적이 아닙니다. 필요에 따라 항목을 추가 및 제거할 수 있습니다. 그러나이를 통해 시작 하는 것이 좋습니다.

- ASCII 텍스트의 SMTP 서버 간에 바이너리 메시지를 전송하는 데 사용되는 MIME 콘텐츠 전송 인코딩 메서드에서 메시지가 디코딩된 *후* 메시지의 제목이나 다른 머리글 필드에 있는 단어 또는 텍스트 패턴이 검색됩니다. 조건이나 예외를 사용하여 메시지의 제목이나 다른 머리글 필드에 있는 원시(일반적으로, Base64) 인코딩된 값을 검색할 수 없습니다.

- 다음 절차에서는 대량 메시지를 전체 조직에 대 한 스팸으로 표시 합니다. 그러나 다른 조건을 추가 하 여 이러한 규칙을 특정 받는 사람 에게만 적용할 수 있으므로, 사용자의 나머지 (대부분 등록 된 대량 전자 메일을 가장 많이 받는)에서는 영향을 받지 않습니다.

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a>EAC를 사용 하 여 대량 전자 메일을 필터링 하는 메일 흐름 규칙 만들기

1. EAC에서 **메일 흐름** \> **규칙**으로 이동합니다.

2. 추가 아이콘 추가를 **클릭 한** ![ ](../../media/ITPro-EAC-AddIcon.png) 다음 **새 규칙 만들기**를 선택 합니다.

3. **새 규칙** 페이지가 열리면 다음 설정을 구성 합니다.

   - **이름**: 규칙에 대 한 설명이 포함 된 고유 이름을 입력 합니다.

   - **기타 옵션**을 클릭 합니다.

   - 다음의 **경우이 규칙 적용**: 정규식 (RegEx) 또는 단어 또는 구를 사용 하 여 메시지의 콘텐츠를 찾도록 다음 설정 중 하나를 구성 합니다.

     - **제목 또는 본문** \> **제목 또는 본문이 다음 텍스트 패턴과 일치**하는 경우: **단어 또는 구 지정** 대화 상자가 나타나면 다음 값 중 하나를 입력 하 고 추가 아이콘 **추가** ![ 를 클릭 ](../../media/ITPro-EAC-AddIcon.png) 한 다음 모든 값을 입력할 때까지 반복 합니다.

       - `If you are unable to view the content of this email\, please`
       - `\>(safe )?unsubscribe( here)?\</a\>`
       - `If you do not wish to receive further communications like this\, please`
       - `\<img height\="?1"? width\="?1"? sr\c=.?http\://`
       - `To stop receiving these+emails\:http\://`
       - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`
       - `no longer (wish )?(to )?(be sent|receive) w+ email`
       - `If you are unable to view the content of this email\, please click here`
       - `To ensure you receive (your daily deals|our e-?mails)\, add`
       - `If you no longer wish to receive these emails`
       - `to change your (subscription preferences|preferences or unsubscribe)`
       - `click (here to|the) unsubscribe`

      항목을 편집 하려면 선택 하 고 편집 아이콘 **편집** 을 클릭 ![ ](../../media/ITPro-EAC-EditIcon.png) 합니다. 항목을 제거 하려면 선택 하 고 제거 아이콘 **제거** 를 클릭 ![ ](../../media/ITPro-EAC-DeleteIcon.png) 합니다.

       작업을 마친 후 **확인**을 클릭합니다.

     - **제목 또는 본문** \> **제목 또는 본문에 다음 단어 포함** **대화 상자가** 나타나면 다음 값 중 하나를 입력 하 고 추가 아이콘 **추가** ![ 를 클릭 ](../../media/ITPro-EAC-AddIcon.png) 한 다음 모든 값을 입력할 때까지 반복 합니다.

       - `to change your preferences or unsubscribe`
       - `Modify email preferences or unsubscribe`
       - `This is a promotional email`
       - `You are receiving this email because you requested a subscription`
       - `click here to unsubscribe`
       - `You have received this email because you are subscribed`
       - `If you no longer wish to receive our email newsletter`
       - `to unsubscribe from this newsletter`
       - `If you have trouble viewing this email`
       - `This is an advertisement`
       - `you would like to unsubscribe or change your`
       - `view this email as a webpage`
       - `You are receiving this email because you are subscribed`

      항목을 편집 하려면 선택 하 고 편집 아이콘 **편집** 을 클릭 ![ ](../../media/ITPro-EAC-EditIcon.png) 합니다. 항목을 제거 하려면 선택 하 고 제거 아이콘 **제거** 를 클릭 ![ ](../../media/ITPro-EAC-DeleteIcon.png) 합니다.

       작업을 마친 후 **확인**을 클릭합니다.

   - **다음을 수행**합니다. **메시지 속성 수정을** 선택 하 여 \> **SCL (스팸 지 수)을 설정**합니다. **SCL 지정** 대화 상자가 나타나면 다음 설정 중 하나를 구성 합니다.

     - 메시지를 **스팸으로**표시 하려면 **6**을 선택 합니다. 스팸 방지 정책에서 **스팸** 필터링 verdicts에 대해 구성한 작업이 메시지에 적용 됩니다 (기본값은 **정크 메일 폴더로 메시지 이동**).

     - 메시지를 **높은 신뢰도 스팸으로** 표시 하려면 **9**를 선택 합니다. 스팸 방지 정책에서 **높은 신뢰도의 스팸** 필터링 verdicts에 대해 구성한 작업은 메시지에 적용 됩니다 (기본값은 **정크 메일 폴더로 메시지 이동**).

    SCL 값에 대 한 자세한 내용은 [EOP의 scl (스팸](spam-confidence-levels.md)지 수)을 참조 하십시오.

   작업이 끝나면 **저장** 을 클릭 합니다.

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a>PowerShell을 사용 하 여 대량 전자 메일을 필터링 하는 메일 흐름 규칙 만들기

다음 구문을 사용 하 여 메일 흐름 규칙 (정규식과 단어 비교) 중 하나 또는 둘 다를 만들 수 있습니다.

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPrhase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

이 예에서는 메시지를 **스팸으로**설정 하기 위해 이전 항목과 동일한 정규식 목록을 사용 하는 "대량 전자 메일 필터링-RegEx" 라는 새 규칙을 만듭니다.

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? sr\c=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

이 예에서는 메시지를 **높은 신뢰도 스팸으로**설정 하기 위해 이전 항목과 동일한 단어 목록을 사용 하는 "대량 전자 메일 필터링-단어" 라는 새 규칙을 만듭니다.

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

자세한 구문 및 매개변수 정보 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule)을 참조하세요.

## <a name="how-do-you-know-this-worked"></a>작동 여부는 어떻게 확인하나요?

대량 전자 메일을 필터링 하도록 메일 흐름 규칙을 구성 했는지 확인 하려면 다음 단계 중 하나를 수행 합니다.

- EAC에서 **메일 흐름** \> **규칙** 을 \> 선택 하 \> **Edit** ![ 고 편집 아이콘 편집 ](../../media/ITPro-EAC-EditIcon.png) 을 클릭 한 다음 설정을 확인 합니다.

- PowerShell에서 \< 규칙 이름을 \> 규칙 이름으로 바꾸고 다음 명령을 실행 하 여 설정을 확인 합니다.

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- 외부 계정에서 구 또는 텍스트 패턴 중 하나를 포함 하는 해당 받는 사람에 게 테스트 메시지를 보낸 다음 결과를 확인 합니다.
