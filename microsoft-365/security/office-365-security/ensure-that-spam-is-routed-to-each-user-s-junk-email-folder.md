---
title: 하이브리드 환경에서 정크 스팸으로 EOP 구성
f1.keywords:
- NOCSH
ms.author: chrisda
author: MSFTTracyP
manager: chrisda
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: 관리자는 Exchange Online Protection 하이브리드 환경에서 스팸을 사용자 정크 메일 폴더로 라우팅하는 방법을 배울 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 926ac6dec33bf00fc8f0dcd292229e20ccc2b93f
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167122"
---
# <a name="configure-standalone-eop-to-deliver-spam-to-the-junk-email-folder-in-hybrid-environments"></a>하이브리드 환경의 정크 메일 폴더에 스팸을 배달하도록 독립 실행형 EOP 구성

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
-  [Exchange Online Protection 독립 실행형](https://go.microsoft.com/fwlink/?linkid=2148611)

> [!IMPORTANT]
> 이 항목은 하이브리드 환경의 독립 실행형 EOP 고객에게만 해당됩니다. 이 항목은 Exchange Online 사서함이 있는 Microsoft 365 고객에게는 적용되지 않습니다.

하이브리드 환경의 독립 실행형 EOP(Exchange Online Protection) 고객인 경우 EOP의 스팸 필터링 판정을 인식하고 번역하도록 전자 메일 조직을 구성해야 합니다. 따라서 메시지를 정크 메일 폴더로 이동할 수 있도록 EOP의 스팸 필터링 규칙을 구성해야 합니다.

특히, 다음 EOP 스팸 방지 헤더 및 값이 있는 메시지를 찾는 조건과 해당 메시지의 SCL(스팸 지수)을 6으로 설정하는 작업을 사용하여 메일 흐름 규칙(전송 규칙)을 만들어야 합니다.

- `X-Forefront-Antispam-Report: SFV:SPM` (스팸 필터링에 의해 스팸으로 표시된 메시지)

- `X-Forefront-Antispam-Report: SFV:SKS` (스팸 필터링 전에 EOP에서 메일 흐름 규칙에 의해 스팸으로 표시된 메시지)

- `X-Forefront-Antispam-Report: SFV:SKB` (보낸 사람 전자 메일 주소 또는 전자 메일 도메인이 차단된 보낸 사람 목록 또는 EOP의 차단된 도메인 목록에 있는 경우 스팸 필터링에 의해 스팸으로 표시된 메시지)

이러한 헤더 값에 대한 자세한 내용은 스팸 방지 [메시지 헤더를 참조하십시오.](anti-spam-message-headers.md)

이 항목에서는 EAC(Exchange 관리 센터) 및 Exchange 관리 셸(Exchange PowerShell)에서 이러한 메일 흐름 규칙을 만드는 방법에 대해 설명하고 있습니다.

> [!TIP]
> 메시지를 EOP의 정크 메일 폴더로 배달하는 대신 EOP에서 스팸 방지 정책을 구성하여 EOP에서 스팸 메시지를 차단할 수 있습니다. 자세한 내용은 [EOP에서 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 사항은 무엇인가요?

- 이러한 절차를 수행하려면 먼저 사용 권한을 할당해야 합니다. 특히 조직 관리, 준수  관리 및 레코드 관리 역할에 기본적으로 할당되는 전송 규칙 역할을 할당해야 합니다.   자세한 내용은 [역할 그룹에 구성원을 추가 합니다.](https://docs.microsoft.com/Exchange/permissions/role-group-members#add-members-to-a-role-group)를 참조하세요.

- 메시지가 다음 설정의 조합으로 제어되는 경우 및 메시지가 정크 메일 조직의 정크 메일 폴더로 배달되는 경우와 그에 따라 제어됩니다.

  - Exchange 관리 셸의 [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) cmdlet에 대한 _SCLJunkThreshold_ 매개 변수 값입니다. 기본값은 4로, SCL이 5 이상이면 메시지를 사용자의 정크 메일 폴더로 배달해야 합니다.

  - Exchange 관리 셸의 [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox) cmdlet에 대한 _SCLJunkThreshold_ 매개 변수 값입니다. 기본값은 비어 있습니다($null) 즉, 조직 설정이 사용됩니다.

  자세한 내용은 [Exchange SCL(스팸 지수) 임계값을 참조하세요.](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl)

  - 사서함에서 정크 메일 규칙을 사용할 수 있는지 _여부(Enabled_ 매개 $true Exchange 관리 셸의 [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration) cmdlet에 적용됩니다. 배달 후 실제로 메시지를 정크 메일 폴더로 이동하는 정크 메일 규칙입니다. 기본적으로 정크 메일 규칙은 사서함에서 사용하도록 설정됩니다. 자세한 내용은 [사서함에 대해 Exchange Antispam 설정 구성을 참조하십시오.](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings)

- EAC를 전자 메일 Exchange Server [Exchange 관리 센터에서](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center)Exchange Server. Exchange 관리 셸을 여는 방법을 확인하려면 [Exchange 관리 셸 열기](https://docs.microsoft.com/powershell/exchange/open-the-exchange-management-shell)를 참조하세요.

- On-premises Exchange의 메일 흐름 규칙에 대한 자세한 내용은 다음 항목을 참조하십시오.

  - [서버의 메일 흐름 Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rules)

  - [메일 흐름 규칙 조건 및 예외(조건자)는 Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [서버의 메일 흐름 규칙 Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/actions)

## <a name="use-the-eac-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>EAC를 사용하여 EOP 스팸 메시지의 SCL을 설정하는 메일 흐름 규칙 만들기

1. EAC에서 **메일 흐름** \> **규칙** 으로 이동합니다.

2. 추가 **아이콘을** 클릭하고 나타나는 드롭다운에서 새 규칙 ![ ](../../media/ITPro-EAC-AddIcon.png) 만들기를 선택합니다. 

3. 새 **규칙** 페이지가 열리면 다음 설정을 구성합니다.

   - **이름:** 규칙에 대해 설명하는 고유한 이름을 입력합니다. 예:

     - EOP SFV:SPM에서 SCL 6으로

     - EOP SFV:SKS에서 SCL 6으로

     - EOP SFV:SKB에서 SCL 6으로

   - 다른 **옵션을 클릭합니다.**

   - **다음의 경우** 이 규칙을 적용합니다. **다음** 단어가 포함된 메시지 헤더를 \> **선택합니다.**

     Enter **텍스트 헤더에 나타나는** 단어 입력 문장이 포함되어 있습니다. 다음 단계를 수행합니다.

     - 텍스트 **입력을 클릭합니다.** 나타나는 **헤더 이름 지정** 대화 상자에서 **X-Forefront-Antispam-Report를** 입력하고 확인을 **클릭합니다.**

     - 단어 **입력을 클릭합니다.** 나타나는  단어 또는 구 지정 대화 상자에서 EOP 스팸 헤더 **값(SFV:SPM,** **SFV:SKS** 또는 **SFV:SKB)** 중 하나를 입력하고 추가 아이콘을 클릭한 다음 확인을  ![ ](../../media/ITPro-EAC-AddIcon.png) 클릭합니다. 

   - **다음을 선택합니다.** 메시지 속성 수정을 **선택하여** \> **SCL(스팸 지수)을 설정할 수 있습니다.**

     SCL **지정 대화** 상자가 나타나면 **6을** **선택합니다(기본값은 5).**

   완료되면 **저장을 클릭합니다.**

나머지 EOP 스팸 판정 **값(SFV:SPM,** **SFV:SKS** 또는 **SFV:SKB)에** 대해 이 단계를 반복합니다.

## <a name="use-the-exchange-management-shell-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>Exchange 관리 셸을 사용하여 EOP 스팸 메시지의 SCL을 설정하는 메일 흐름 규칙 만들기

다음 구문을 사용하여 세 가지 메일 흐름 규칙을 만들 수 있습니다.

```Powershell
New-TransportRule -Name "<RuleName>" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "<EOPSpamFilteringVerdict>" -SetSCL 6
```

예:

```Powershell
New-TransportRule -Name "EOP SFV:SPM to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKS to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKB to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
```

자세한 구문 및 매개변수 정보 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule)을 참조하세요.

## <a name="how-do-you-know-this-worked"></a>작동 여부는 어떻게 확인하나요?

하이브리드 환경의 정크 메일 폴더로 스팸을 배달하도록 독립 실행형 EOP를 성공적으로 구성한 경우 다음 단계를 수행합니다.

- EAC에서 메일 흐름 **규칙으로** 이동하여 규칙을 선택한 다음 편집 아이콘을 클릭하여 설정을 \>   ![ ](../../media/ITPro-EAC-EditIcon.png) 확인합니다.

- Exchange 관리 셸에서 메일 흐름 규칙의 이름으로 바꾸고 다음 명령을 실행하여 설정을 \<RuleName\> 확인합니다.

  ```powershell
  Get-TransportRule -Identity "<RuleName>" | Format-List
  ```

- 아웃바운드 메시지에서 스팸을 검색하지 않는 외부 전자 메일 시스템에서 해당 받는 사람에게 GTUBE(원치 않는 대량 전자 메일) 메시지에 대한 일반 테스트를 보낸 다음 해당 정크 메일 폴더로 배달된지 확인합니다. GTUBE 메시지는 맬웨어 설정을 테스트하기 위한 EICAR(European Institute for Computer Antivirus Research) 텍스트 파일과 유사합니다.

  GTUBE 메시지를 보내기 위해 공백이나 줄을 끊지 않고 전자 메일 메시지 본문에 다음 텍스트를 한 줄에 포함합니다.

  ```text
  XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
  ```
