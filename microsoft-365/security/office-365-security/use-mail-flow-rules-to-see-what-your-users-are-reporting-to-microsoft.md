---
title: 메일 흐름 규칙을 사용하여 사용자가 Microsoft에 보고한 내용 확인
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: 관리자는 메일 흐름 규칙(전송 규칙이라고도 함)을 사용하여 사용자가 Microsoft에 보고하는 메시지 복사본을 수신하는 방법을 학습할 수 있습니다.
ms.openlocfilehash: 1612adeefff21fa9f149de6537917dd9b8c50b00
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827388"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a>메일 흐름 규칙을 사용하여 사용자가 Microsoft에 보고한 내용 확인

Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에는 여러 가지 방법으로 Microsoft에 보고 메시지와 파일에 설명된 방식으로 Microsoft에 메시지를 [분석하도록 Microsoft에 보고할 수 있습니다.](report-junk-email-messages-to-microsoft.md)

사용자가 Microsoft에 보고하는 메시지를 찾는 메일 흐름 규칙(전송 규칙이라고도 함)을 만들 수 있고, 숨은 참조 수신자가 보고된 이러한 메시지의 복사본을 받도록 Bcc 를 구성할 수 있습니다.

EAC(Exchange 관리 센터) 및 PowerShell(Exchange Online 사서함을 사용하는 조직의 경우 Exchange Online PowerShell, Exchange Online 사서함이 없는 조직의 경우 독립 실행형 EOP PowerShell)에서 메일 흐름 규칙을 만들 수 있습니다.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- 이러한 절차를 수행하려면 먼저 Exchange Online 또는 EOP에서 사용 권한을 할당해야 합니다. 특히 조직 **관리,** 준수 관리 및 **레코드** 관리 **역할에는**할당된 전송 규칙 역할을 **할당받아도 기본적으로 할당되어** 있어야 합니다. 자세한 내용은 [Exchange Online에서 역할 그룹 관리](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)를 참조하세요.

- EAC를 열려면 [Exchange Online 또는 Exchange 관리 센터의 Exchange](https://docs.microsoft.com/Exchange/exchange-admin-center) [관리 센터(독립 실행형 EOP)를 참조하십시오.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요. 독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.

- Exchange Online 및 독립 실행형 EOP의 메일 흐름 규칙에 대한 자세한 내용은 다음 항목을 참조하십시오.

  - [Exchange Online의 메일 흐름 규칙(전송 규칙)](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Exchange Online의 메일 흐름 규칙 조건 및 예외(조건자)](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Exchange Online의 메일 흐름 규칙 동작](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>EAC를 사용하여 보고된 메시지의 복사본을 받는 메일 흐름 규칙 만들기

1. EAC에서 **메일 흐름** \> **규칙**으로 이동합니다.

2. 아이콘 **추가를** ![ 클릭한 다음 새 규칙 ](../../media/ITPro-EAC-AddIcon.png) **만들기를 선택합니다.**

3. ** 새** 규칙 페이지에서 다음 설정을 구성합니다.

   - **이름:** 규칙을 설명하는 고유한 이름을 입력합니다. 예를 들어 Microsoft에 보고된 BCC 메시지가 있습니다.

   - 기타 **옵션을 클릭합니다.**

   - **다음 단어의 경우 이**규칙 적용 : **받는** 사람 주소에 다음 단어 중 하나를 포함 합니다. 나타나는 단어 또는 구 지정 대화 상자에서 다음 값 중 하나를 입력하고, 아이콘 추가를 클릭한 후 모든 값을 입력할 때까지 \> **address includes any of these words** **Specify words or phrases** **Add** ![ ](../../media/ITPro-EAC-AddIcon.png) 반복합니다.

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     항목을 편집하려면 항목을 선택한 후 편집 **아이콘을** ![ 클릭합니다. ](../../media/ITPro-EAC-EditIcon.png) 항목을 제거하려면 항목을 선택한 다음 제거 아이콘 **제거를** ![ 클릭합니다. ](../../media/ITPro-EAC-DeleteIcon.png)

     작업을 마친 후 **확인**을 클릭합니다.

   - **다음 작업을 수행합니다.** **Add recipients** \> **숨은 참조 상자에 받는 사람 추가**상자를 선택합니다. 대화 상자가 나타나면 추가할 받는 사람을 찾아 선택합니다. 작업을 마친 후 **확인**을 클릭합니다.

4. 규칙을 감사 및 테스트하고 특정 기간 동안 규칙을 활성화하는 등 다른 설정을 추가로 선택할 수 있습니다. 규칙을 적용하기 전에 테스트하는 것이 좋습니다.

5. 작업을 마쳤으면 **저장**을 클릭합니다.

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>PowerShell을 사용하여 보고된 메시지의 복사본을 받는 메일 흐름 규칙 만들기

이 예에서는 이 항목에 설명된 방법을 사용하여 Microsoft에 보고된 전자 메일 메시지를 찾는 Microsoft에 숨은 편지함이라는 새 메일 흐름 규칙을 만들고, 숨은 참조로 laura@contoso.com 및 julia@contoso.com 추가할 수 있습니다.

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

자세한 구문 및 매개변수 정보 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule)을 참조하세요.

## <a name="how-do-you-know-this-worked"></a>작동 여부는 어떻게 확인하나요?

보고된 메시지의 복사본을 받도록 메일 흐름 규칙을 구성되었는지 확인하려면 다음 단계 중 하나를 수행합니다.

- EAC에서 메일 흐름 **Mail flow** 규칙으로 \> **이동하여 규칙** \> 편집 \> 아이콘을 선택한 **다음** ![ ](../../media/ITPro-EAC-EditIcon.png) 설정을 확인합니다.

- PowerShell에서 다음 명령을 실행하여 설정을 확인합니다.

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- 보고 전자 메일 주소 중 하나로 테스트 메시지를 보내고 결과를 확인합니다.
