---
title: 메일 흐름 규칙을 사용하여 사용자가 Microsoft에 보고한 내용 확인
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: 관리자는 메일 흐름 규칙(전송 규칙)을 사용하여 사용자가 Microsoft에 보고하는 메시지의 복사본을 받는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 40e87fec3bfd8ed4402713ca7ec45499bb50c68e
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287608"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a>메일 흐름 규칙을 사용하여 사용자가 Microsoft에 보고한 내용 확인

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Exchange Online 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에 사서함이 있는 Microsoft 365 조직에서는 사용자가 Microsoft에 메시지 및 파일 보고서에 설명된 바와 같이 분석을 위해 Microsoft에 메시지를 보고할 수 있는 여러 가지 방법이 [있습니다.](report-junk-email-messages-to-microsoft.md)

사용자가 Microsoft에 보고하는 메시지를 받도록 메일 흐름 규칙(전송 규칙)을 만들 수 있으며, 이러한 보고된 메시지의 복사본을 받도록 Bcc 받는 사람을 구성할 수 있습니다.

EAC(Exchange 관리 센터) 및 PowerShell(Exchange Online 사서함이 있는 Microsoft 365 조직용 Exchange Online PowerShell, Exchange Online 사서함이 없는 조직의 독립 실행형 EOP PowerShell)에서 메일 흐름 규칙을 만들 수 있습니다.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 사항은 무엇인가요?

- 이 문서의 절차를 수행하려면 먼저 Exchange Online 또는 Exchange Online Protection에서 사용 권한을 할당해야 합니다. 특히 조직 관리,  준수 관리(전역 관리자) 및  **레코드** 관리 역할 그룹에 기본적으로 할당되는 전송 규칙 역할이 필요합니다.

  자세한 내용은 아래 항목을 참조하세요.

  - [Exchange Online의 사용 권한](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)
  - [독립 실행형 EOP의 사용 권한](feature-permissions-in-eop.md)
  - [EAC를 사용하여 역할 그룹의 구성원 목록 수정](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Exchange Online에서 EAC를 열하려면 [Exchange Online의 Exchange 관리 센터를 참조하세요.](https://docs.microsoft.com/Exchange/exchange-admin-center) 독립 실행형 EOP에서 EAC를 열하려면 독립 실행형 [EOP의 Exchange 관리 센터를 참조하세요.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요. 독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.

- Exchange Online 및 독립 실행형 EOP의 메일 흐름 규칙에 대한 자세한 내용은 다음 항목을 참조하세요.
  - [Exchange Online의 메일 흐름 규칙(전송 규칙)](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
  - [Exchange Online의 메일 흐름 규칙 조건 및 예외(조건자)](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)
  - [Exchange Online의 메일 흐름 규칙 작업](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>EAC를 사용하여 보고된 메시지의 복사본을 받는 메일 흐름 규칙 만들기

1. EAC에서 **메일 흐름** \> **규칙** 으로 이동합니다.

2. 추가 **아이콘을** 클릭한 다음 새 규칙 ![ ](../../media/ITPro-EAC-AddIcon.png) **만들기를 선택합니다.**

3. 새 **규칙** 페이지가 열리면 다음 설정을 구성합니다.

   - **이름:** 규칙에 대해 설명하는 고유한 이름을 입력합니다. 예를 들어 Microsoft에 Bcc 메시지 보고

   - 다른 **옵션을 클릭합니다.**

   - **다음의** 경우 이  규칙을 적용합니다. 받는 사람 주소에 다음 단어가 포함된 경우 선택: 나타나는 단어 또는 구 지정 대화 상자에서 다음 값 중 하나를 입력하고 아이콘 추가를 클릭한 다음 모든 값을 입력할 때까지 \>    ![ ](../../media/ITPro-EAC-AddIcon.png) 반복합니다.

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `not_junk@office365.microsoft.com`

     항목을 편집하려면 해당 항목을  선택하고 편집 ![ 아이콘을 ](../../media/ITPro-EAC-EditIcon.png) 클릭합니다. 항목을 제거하려면 해당 항목을 선택하고 **제거** ![ 아이콘을 ](../../media/ITPro-EAC-DeleteIcon.png) 클릭합니다.

     작업을 마친 후 **확인** 을 클릭합니다.

   - **다음을 선택합니다.** Bcc 상자에  \> **받는 사람 추가를 선택합니다.** 대화 상자가 나타나면 추가할 받는 사람을 찾아 선택합니다. 작업을 마친 후 **확인** 을 클릭합니다.

4. 규칙을 감사하고, 규칙을 테스트하고, 특정 기간 동안 규칙을 활성화하고, 기타 설정을 추가로 선택하도록 할 수 있습니다. 규칙을 적용하기 전에 규칙을 테스트하는 것이 좋습니다.

5. 작업을 마쳤으면 **저장** 을 클릭합니다.

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>PowerShell을 사용하여 보고된 메시지의 복사본을 받는 메일 흐름 규칙 만들기

이 예에서는 이 문서에 설명된 방법을 사용하여 Microsoft에 보고되는 전자 메일 메시지를 헌트하는 Bcc Messages Reported라는 새 메일 흐름 규칙을 만들고, Bcc 받는 사람으로 laura@contoso.com julia@contoso.com 추가합니다.

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

자세한 구문 및 매개변수 정보 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule)을 참조하세요.

## <a name="how-do-you-know-this-worked"></a>작동 여부는 어떻게 확인하나요?

보고된 메시지의 복사본을 받도록 메일 흐름 규칙을 구성한지 확인하기 위해 다음 단계를 수행합니다.

- EAC에서 메일 흐름 **규칙으로** 이동하여 편집 아이콘을 클릭하는 규칙을 선택하고 \>  \> 설정을 \>  ![ ](../../media/ITPro-EAC-EditIcon.png) 확인합니다.

- PowerShell에서 다음 명령을 실행하여 설정을 확인합니다.

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- 테스트 메시지를 보고 전자 메일 주소 중 하나에 보내고 결과를 검증합니다.
