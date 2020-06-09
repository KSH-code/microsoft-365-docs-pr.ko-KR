---
title: 메일 흐름 규칙을 사용하여 사용자가 Microsoft에 보고한 내용 확인
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
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: 관리자는 메일 흐름 규칙 (전송 규칙이 라고도 함)을 사용 하 여 사용자가 Microsoft에 보고 하는 메시지의 복사본을 수신 하는 방법을 확인할 수 있습니다.
ms.openlocfilehash: d50a0f02dd3d65b8576261fc2332aba86d55df56
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44616793"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a>메일 흐름 규칙을 사용하여 사용자가 Microsoft에 보고한 내용 확인

Exchange online 사서함이 없는 Microsoft 365 조직의 EOP (exchange online Protection) 조직에 사서함이 있는 경우 사용자가 [보고서 메시지 및 파일](report-junk-email-messages-to-microsoft.md)에 설명 된 대로 microsoft에 분석을 위해 microsoft에 메시지를 보고 하는 여러 가지 방법이 있습니다.

사용자가 Microsoft에 보고 하는 메시지를 찾는 메일 흐름 규칙 (전송 규칙이 라고도 함)을 만들 수 있으며, 이러한 보고 된 메시지의 복사본을 받도록 숨은 참조 받는 사람을 구성할 수 있습니다.

EAC (exchange 관리 센터) 및 PowerShell (exchange online 사서함이 없는 조직에 대 한 사서함이 있는 Microsoft 365 조 직의 경우 exchange online PowerShell을 사용 하는 경우, 독립 실행형 EOP PowerShell)에서 메일 흐름 규칙을 만들 수 있습니다.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용

- 이러한 절차를 수행 하려면 먼저 Exchange Online 또는 EOP에서 사용 권한을 할당 받아야 합니다. 특히 **조직 관리**, **규정 준수 관리**및 **레코드 관리** 역할에 할당 되는 **전송 규칙** 역할을 기본적으로 할당 해야 합니다. 자세한 내용은 [Exchange Online에서 역할 그룹 관리](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)를 참조하세요.

- EAC를 열려면 [독립 실행형 EOP에서 Exchange Online 또는 exchange 관리 센터](exchange-admin-center-in-exchange-online-protection-eop.md) [의 exchange 관리 센터](https://docs.microsoft.com/Exchange/exchange-admin-center) 를 참조 하세요.

- Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요. 독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.

- Exchange Online 및 독립 실행형 EOP의 메일 흐름 규칙에 대 한 자세한 내용은 다음 항목을 참조 하십시오.

  - [Exchange Online의 메일 흐름 규칙 (전송 규칙)](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [메일 흐름 규칙 조건 및 예외 (조건자)가 Exchange Online에 있습니다.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Exchange Online의 메일 흐름 규칙 동작](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>EAC를 사용 하 여 보고 된 메시지의 복사본을 수신 하는 메일 흐름 규칙 만들기

1. EAC에서 **메일 흐름** \> **규칙**으로 이동합니다.

2. 추가 아이콘 추가를 **클릭 한** ![ ](../../media/ITPro-EAC-AddIcon.png) 다음 **새 규칙 만들기**를 선택 합니다.

3. **새 규칙** 페이지가 열리면 다음 설정을 구성 합니다.

   - **이름**: 규칙에 대 한 설명이 포함 된 고유 이름을 입력 합니다. 예를 들어 숨은 참조 메시지는 Microsoft에 보고 됩니다.

   - **기타 옵션**을 클릭 합니다.

   - 다음의 **경우에이 규칙 적용**: 표시 되 **는 단어** \> **address includes any of these words** **또는 구 지정** 대화 상자에 다음 값 중 하나를 입력 하 고 추가 아이콘 **추가** ![ 를 클릭 ](../../media/ITPro-EAC-AddIcon.png) 한 다음 모든 값을 입력할 때까지 반복 합니다.

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     항목을 편집 하려면 선택 하 고 편집 아이콘 **편집** 을 클릭 ![ ](../../media/ITPro-EAC-EditIcon.png) 합니다. 항목을 제거 하려면 선택 하 고 제거 아이콘 **제거** 를 클릭 ![ ](../../media/ITPro-EAC-DeleteIcon.png) 합니다.

     작업을 마친 후 **확인**을 클릭합니다.

   - **다음을 수행**합니다. **Add recipients** \> **숨은 참조 상자에**받는 사람 추가를 선택 합니다. 대화 상자가 나타나면 추가 하려는 받는 사람을 찾아 선택 합니다. 작업을 마친 후 **확인**을 클릭합니다.

4. 규칙을 감사 하 고 규칙을 테스트 하며 특정 기간 동안 규칙을 활성화 하 고 기타 설정을 선택할 수 있습니다. 규칙을 적용 하기 전에 테스트 하는 것이 좋습니다.

5. 작업을 마쳤으면 **저장**을 클릭합니다.

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>PowerShell을 사용 하 여 보고 된 메시지의 복사본을 수신 하는 메일 흐름 규칙 만들기

이 예에서는이 항목에 설명 된 방법을 사용 하 여 Microsoft에 보고 되는 전자 메일 메시지를 찾아서 사용자 laura@contoso.com 및 julia@contoso.com를 숨은 참조 받는 사람으로 추가 하는 숨은 참조 메시지 라는 이름의 새 메일 흐름 규칙을 만듭니다.

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

자세한 구문 및 매개변수 정보 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule)을 참조하세요.

## <a name="how-do-you-know-this-worked"></a>작동 여부는 어떻게 확인하나요?

보고 된 메시지의 복사본을 수신 하도록 메일 흐름 규칙을 구성 했는지 확인 하려면 다음 단계 중 하나를 수행 합니다.

- EAC에서 **메일 흐름** \> **규칙** 을 \> 선택 하 \> **Edit** ![ 고 편집 아이콘 편집 ](../../media/ITPro-EAC-EditIcon.png) 을 클릭 한 다음 설정을 확인 합니다.

- PowerShell에서 다음 명령을 실행 하 여 설정을 확인 합니다.

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- 보고 전자 메일 주소 중 하나로 테스트 메시지를 보내 결과를 확인 합니다.
