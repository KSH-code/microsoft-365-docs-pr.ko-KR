---
title: 분석을 위해 Microsoft에 수동으로 메시지 전송
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: '귀하와 사용자는 분석을 위해 Microsoft에 허위 네거티브 및 가양성 스팸 메시지를 제출할 수 있습니다. '
ms.openlocfilehash: 13b2e42f749b54e0c2b71fe095c077992560ea8c
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/28/2020
ms.locfileid: "43032807"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a>분석을 위해 Microsoft에 수동으로 메시지 전송

> [!NOTE]
> Exchange Online 사서함을 사용 하는 Office 365 조직의 관리자는 Office 365 보안 & 준수 센터의 전송 포털을 사용 하는 것이 좋습니다. 자세한 내용은 [관리자 제출을 사용 하 여 의심 스러운 스팸, 피싱, url 및 파일을 Microsoft에 제출](admin-submission.md)합니다 .를 참조 하세요.

조직의 사용자가 받은 편지함에서 정크 메시지 (스팸) 나 피싱 메시지를 받거나, 정크로 표시 되어 합법적인 전자 메일 메시지를 받지 못하는 경우에는 혼란을 가져올 수 있습니다. Microsoft는 스팸 필터를 보다 정확 하 게 미세 조정 하 고 있습니다.

귀하와 사용자는 가양성 (잘못 된 것으로 표시 된 전자 메일), 거짓 네거티브 (잘못 된 메일 허용), 분석을 위해 Microsoft에 피싱 메시지를 제출 하 여이 프로세스를 지원할 수 있습니다.

> [!NOTE]
> 수신 되는 전송 양이 많기 때문에 분석을 위해 모든 요청에 응답 하지 못할 수 있습니다.

## <a name="submit-false-negatives-to-microsoft"></a>Microsoft에 거짓 네거티브 전송

> [!TIP]
> 다음 절차를 사용 하 여 거짓 네거티브를 보고 하는 대신 Outlook 및 웹용 Outlook (이전의 Outlook Web App)에 있는 사용자가 Microsoft Outlook 용 보고서 메시지 추가 기능을 사용할 수 있습니다. 이 도구를 설치 하 고 사용 하는 방법에 대 한 자세한 내용은 [보고서 메시지 추가 기능을 사용 하도록 설정을](enable-the-report-message-add-in.md)참조 하십시오.

스팸 또는 피싱으로 식별 되어야 하는 스팸 필터링을 통해 전달 된 메시지를 수신 하는 경우 Microsoft 스팸 분석 및 Microsoft 피싱 분석 팀에 적절 하 게 메시지를 제출할 수 있습니다. 분석가는 메시지를 검토 하 고 해당 메시지가 분류 기준을 충족 하는 경우 서비스 전체 필터에 추가 합니다.

1. 다음 받는 사람 중 하 나와의 비어 있는 새 전자 메일 메시지를 만듭니다.

   - **정크 메일**:`junk@office365.microsoft.com`

   - **피싱**:`phish@office365.microsoft.com`

2. 정크 또는 피싱 메시지를 새 메시지에 끌어서 놓습니다. 이렇게 하면 정크 또는 피싱 메시지가 새 메시지에 첨부 파일로 저장 됩니다. 메시지의 내용을 복사 하 여 붙여넣거나 메시지를 전달 하지 않습니다 (메시지 헤더를 검사할 수 있도록 원본 메시지가 필요 함).

   > [!NOTE]
   > <ul><li>새 메시지에 여러 메시지를 첨부할 수 있습니다. 모든 메시지의 유형 (피싱 사기 메시지 또는 정크 메일 메시지)이 동일한 지 확인 합니다.</li><li>새 메시지의 본문은 비워 둡니다.<li></li>첨부 된 메시지의 형식은 .msg (기본 Outlook 형식) 또는 .eml (기본 outlook 형식) 중 하나를 사용 합니다.</li></ul>

3. 작업이 완료 되 면 **보내기를**클릭 합니다.

> [!TIP]
> 관리자는 스팸으로 잘못 식별 되어는 특정 메시지를 차단 하는 여러 가지 방법을 제공 합니다. 자세한 내용은 [Office 365에서 차단 된 보낸 사람 목록 만들기](create-block-sender-lists-in-office-365.md)를 참조 하십시오.

## <a name="submit-false-positives-to-microsoft"></a>Microsoft에 가양성 제출

> [!TIP]
> 다음 절차를 사용 하 여 가양성을 보고 하는 대신 Outlook 및 웹용 Outlook의 사용자가 Microsoft Outlook 용 보고서 메시지 추가 기능을 사용할 수 있습니다. 이 도구를 설치 하 고 사용 하는 방법에 대 한 자세한 내용은 [보고서 메시지 추가 기능을 사용 하도록 설정을](enable-the-report-message-add-in.md)참조 하십시오.

메시지가 스팸으로 잘못 식별 된 경우 Microsoft 스팸 분석 팀에 메시지를 제출할 수 있습니다. 분석가는 메시지를 평가 하 고, 분석 결과에 따라, 서비스 전체 필터를 통해 메시지를 통과 하도록 조정할 수 있습니다.

1. 받는 사람이 다음과 같은 비어 있는 `not_junk@office365.microsoft.com` 새 전자 메일 메시지를 만듭니다.

2. 잘못 식별 되어 메시지를 끌어서 새 메시지에 놓습니다. 이렇게 하면 잘못 식별 되어 메시지가 새 메시지에 첨부 파일로 저장 됩니다. 메시지의 내용을 복사 하 여 붙여넣거나 메시지를 전달 하지 않습니다 (메시지 헤더를 검사할 수 있도록 원본 메시지가 필요 함).

   > [!NOTE]
   > <ul><li>새 메시지에 여러 메시지를 첨부할 수 있습니다. 모든 메시지의 유형 (피싱 사기 메시지 또는 정크 메일 메시지)이 동일한 지 확인 합니다.</li><li>새 메시지의 본문은 비워 둡니다.<li></li>첨부 된 메시지의 형식은 .msg (기본 Outlook 형식) 또는 .eml (기본 outlook 형식) 중 하나를 사용 합니다.</li></ul>

3. 작업이 완료 되 면 **보내기를**클릭 합니다.

> [!TIP]
> 관리자는 특정 메시지에서 스팸 필터링을 건너뛰는 여러 가지 방법을 사용할 수 있습니다. 자세한 내용은 [Office 365에서 수신 허용-보낸 사람 목록 만들기](create-safe-sender-lists-in-office-365.md)를 참조 하십시오.

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a>Microsoft에 보고 되는 메시지의 복사본을 수신 하는 메일 흐름 규칙 만들기

이 항목에서 설명 하는 방법을 사용 하 여 Microsoft에 보고 되는 전자 메일 메시지를 찾는 메일 흐름 규칙 (전송 규칙이 라고도 함)을 만들 수 있으며, 이러한 보고 된 메시지의 복사본을 받도록 숨은 참조 받는 사람을 구성할 수 있습니다.

EAC (Exchange 관리 센터) 및 PowerShell (Office 365 고객을 위한 Exchange Online PowerShell)에서 메일 흐름 규칙을 만들 수 있습니다. 독립 실행형 EOP 고객을 위한 Exchange Online Protection PowerShell

### <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- 이러한 절차를 수행 하려면 먼저 Exchange Online에서 사용 권한을 할당 받아야 합니다. 특히 **조직 관리**, **규정 준수 관리**및 **레코드 관리** 역할에 할당 되는 **전송 규칙** 역할을 기본적으로 할당 해야 합니다. 자세한 내용은 [Exchange Online에서 역할 그룹 관리](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)를 참조하세요.

- Exchange Online에서 EAC를 열려면 exchange [online의 exchange 관리 센터](https://docs.microsoft.com/Exchange/exchange-admin-center)를 참조 하세요.

- Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결하기](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)를 참조하세요. Exchange Online Protection PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결하기](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)를 참조하세요.

- Exchange Online 및 독립 실행형 EOP의 메일 흐름 규칙에 대 한 자세한 내용은 다음 항목을 참조 하십시오.

  - [Exchange Online의 메일 흐름 규칙 (전송 규칙)](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [메일 흐름 규칙 조건 및 예외 (조건자)가 Exchange Online에 있습니다.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Exchange Online의 메일 흐름 규칙 동작](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

### <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>EAC를 사용 하 여 보고 된 메시지의 복사본을 수신 하는 메일 흐름 규칙 만들기

1. EAC에서 **메일 흐름** \> **규칙**으로 이동합니다.

2. ![](../../media/ITPro-EAC-AddIcon.png) 추가 **아이콘 추가를 클릭 한** 다음 **새 규칙 만들기**를 선택 합니다.

3. **새 규칙** 페이지가 열리면 다음 설정을 구성 합니다.

   - **이름**: 규칙에 대 한 설명이 포함 된 고유 이름을 입력 합니다. 예를 들어 숨은 참조 메시지는 Microsoft에 보고 됩니다.

   - **기타 옵션**을 클릭 합니다.

   - 다음 **의** **경우에이 규칙 적용**: \> 표시 **되는 단어** **또는 구 지정** 대화 상자에 다음 값 중 하나를 입력 하 고 추가 아이콘](../../media/ITPro-EAC-AddIcon.png) **추가** ![를 클릭 한 다음 모든 값을 입력할 때까지 반복 합니다.

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     항목을 편집 하려면 선택 하 고 편집](../../media/ITPro-EAC-EditIcon.png)아이콘 **편집** ![을 클릭 합니다. 항목을 제거 하려면 선택 하 고 제거](../../media/ITPro-EAC-DeleteIcon.png)아이콘 **제거** ![를 클릭 합니다.

     작업을 마친 후 **확인**을 클릭합니다.

   - **다음을 수행**합니다. \> **숨은 참조 상자에** **받는 사람 추가** 를 선택 합니다. 대화 상자가 나타나면 추가 하려는 받는 사람을 찾아 선택 합니다. 작업을 마친 후 **확인**을 클릭합니다.

4. 규칙을 감사 하 고 규칙을 테스트 하며 특정 기간 동안 규칙을 활성화 하 고 기타 설정을 선택할 수 있습니다. 규칙을 적용 하기 전에 테스트 하는 것이 좋습니다.

5. 작업을 마쳤으면 **저장**을 클릭합니다.

### <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>PowerShell을 사용 하 여 보고 된 메시지의 복사본을 수신 하는 메일 흐름 규칙 만들기

이 예에서는이 항목에 설명 된 방법을 사용 하 여 Microsoft에 보고 되는 전자 메일 메시지를 찾아서 사용자 laura@contoso.com 및 julia@contoso.com를 숨은 참조 받는 사람으로 추가 하는 숨은 참조 메시지 라는 이름의 새 메일 흐름 규칙을 만듭니다.

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

자세한 구문 및 매개변수 정보 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule)을 참조하세요.

### <a name="how-do-you-know-this-worked"></a>작동 여부는 어떻게 확인하나요?

보고 된 메시지의 복사본을 수신 하도록 메일 흐름 규칙을 구성 했는지 확인 하려면 다음 단계 중 하나를 수행 합니다.

- EAC에서 **메일 흐름** \> **규칙** \> 을 선택 하 고 편집 아이콘 **Edit** ![](../../media/ITPro-EAC-EditIcon.png)편집 \> 을 클릭 한 다음 설정을 확인 합니다.

- PowerShell에서 다음 명령을 실행 하 여 설정을 확인 합니다.

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- 보고 전자 메일 주소 중 하나로 테스트 메시지를 보내 결과를 확인 합니다.
