---
title: 하이브리드 환경에서 EOP을 정크 스팸으로 구성
f1.keywords:
- NOCSH
ms.author: chrisda
author: MSFTTracyP
manager: chrisda
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: 관리자는 하이브리드 환경에서 독립 실행형 EOP (Exchange Online Protection)를 사용 하는 경우 온-프레미스 사용자의 정크 메일 폴더로 스팸을 라우팅하기 위해 온-프레미스 Exchange 환경을 구성 하는 방법을 확인할 수 있습니다.
ms.openlocfilehash: 8a3887d1cc7390e75b7708d2167372e976923e01
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "42893721"
---
# <a name="configure-standalone-eop-to-deliver-spam-to-the-junk-email-folder-in-hybrid-environments"></a>하이브리드 환경의 정크 메일 폴더에 스팸을 배달 하도록 독립 실행형 EOP 구성

> [!IMPORTANT]
> 이 항목은 독립 실행형 EOP 고객을 위한 하이브리드 환경의 경우에만 해당 합니다. 이 항목은 Exchange Online 사서함이 있는 Office 365 고객에 게는 적용 되지 않습니다.

하이브리드 환경에서 독립 실행형 EOP (Exchange Online Protection) 고객 인 경우 온-프레미스 Exchange 조직에서 EOP의 스팸 필터링 verdicts를 인식 하 고 번역 하도록 구성 해야 합니다. 정크 메일 폴더로 메시지를 이동할 수 있습니다.

특히 다음 EOP 및 스팸 지 수의 헤더 및 값을 사용 하 여 메시지를 검색 하는 조건이 있는 온-프레미스 Exchange 조직에 메일 흐름 규칙 (전송 규칙이 라고도 함)을 만들어야 합니다 ( SCL)에서 해당 메시지의 최대 6 개:

- `X-Forefront-Antispam-Report: SFV:SPM`(스팸 필터링을 통해 스팸으로 표시 된 메시지)

- `X-Forefront-Antispam-Report: SFV:SKS`(스팸 필터링 전에 EOP의 메일 흐름 규칙에 따라 스팸으로 표시 된 메시지)

- `X-Forefront-Antispam-Report: SFV:SKB`보낸 사람의 전자 메일 주소 또는 전자 메일 도메인이 EOP의 차단 된 보낸 사람 목록에 있거나 차단 된 도메인 목록에 있기 때문에 스팸 필터링에 의해 스팸으로 표시 됩니다.

이러한 헤더 값에 대 한 자세한 내용은 [스팸 방지 메시지 헤더](anti-spam-message-headers.md)를 참조 하십시오.

이 항목에서는 Exchange 관리 센터 (EAC) 및 온-프레미스 Exchange 조직의 exchange 관리 셸 (exchange PowerShell)에서 이러한 메일 흐름 규칙을 만드는 방법에 대해 설명 합니다.

> [!TIP]
> 온-프레미스 사용자의 정크 메일 폴더로 메시지를 배달 하는 대신 EOP에서 스팸 방지 정책을 구성 하 여 EOP의 스팸 메시지를 격리할 수 있습니다. 자세한 내용은 [Office 365의 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- 이러한 절차를 수행 하려면 먼저 온-프레미스 Exchange 환경에서 사용 권한을 할당 받아야 합니다. 특히 **조직 관리**, **규정 준수 관리**및 **레코드 관리** 역할에 할당 되는 **전송 규칙** 역할을 기본적으로 할당 해야 합니다. 자세한 내용은 [역할 그룹에 구성원을 추가 합니다.](https://docs.microsoft.com/Exchange/permissions/role-group-members?view=exchserver-2019#add-members-to-a-role-group)를 참조하세요.

- 온-프레미스 Exchange 조직의 정크 메일 폴더로 배달 되는 메시지는 다음 설정을 조합 하 여 제어 합니다.

  - Exchange 관리 셸에서 [set-organizationconfig](https://docs.microsoft.com/powershell/module/exchange/organization/set-organizationconfig) cmdlet에 대 한 _SCLJunkThreshold_ 매개 변수 값입니다. 기본값은 4 이며이 값은 SCL 5 이상이 사용자의 정크 메일 폴더로 메시지를 배달 하는 것을 의미 합니다.

  - Exchange 관리 셸에서 [설정 된 사서함](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) Cmdlet의 _SCLJunkThreshold_ 매개 변수 값입니다. 기본값은 비어 있음 ($null) 이며,이 값은 조직 설정이 사용 됨을 의미 합니다.

  자세한 내용은 [EXCHANGE SCL (스팸 지 수) 임계값](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl)을 참조 하십시오.

  - 사서함에서 정크 메일 규칙을 사용할 수 있는지 여부 (Exchange 관리 셸에서 [set-mailboxjunkemailconfiguration](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-mailboxjunkemailconfiguration) Cmdlet의 _enabled_ 매개 변수 값이 $true) 배달 후 실제로 메시지를 정크 메일 폴더로 이동 하는 정크 메일 규칙입니다. 기본적으로 사서함에서는 정크 메일 규칙이 사용 되도록 설정 됩니다. 자세한 내용은 [사서함에 대 한 Exchange 스팸 방지 설정 구성을](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings)참조 하세요.
  
- Exchange 서버에서 EAC를 열려면 exchange [server의 exchange 관리 센터](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center)를 참조 하세요. Exchange 관리 셸을 열려면를 참조 [https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell)하세요.

- 온-프레미스 Exchange의 메일 흐름 규칙에 대 한 자세한 내용은 다음 항목을 참조 하십시오.

  - [Exchange Server의 메일 흐름 규칙](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Exchange Server의 메일 흐름 규칙 조건 및 예외 (조건자)](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Exchange Server의 메일 흐름 규칙 동작](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/actions)

## <a name="use-the-eac-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>EAC를 사용 하 여 EOP 스팸 메시지의 SCL을 설정 하는 메일 흐름 규칙 만들기

1. EAC에서 **메일 흐름** \> **규칙**으로 이동합니다.

2. ![](../../media/ITPro-EAC-AddIcon.png) 추가 **아이콘 추가를 클릭 하** 고 표시 되는 드롭다운에서 **새 규칙 만들기** 를 선택 합니다.

3. **새 규칙** 페이지가 열리면 다음 설정을 구성 합니다.

   - **이름**: 규칙에 대 한 설명이 포함 된 고유 이름을 입력 합니다. 예시:

     - EOP SFV:, SCL 6에 게 SPM

     - EOP SFV: SKS-SCL 6

     - EOP SFV: SKB-SCL 6

   - **기타 옵션**을 클릭 합니다.

   - 다음의 **경우이 규칙 적용**: **메시지 헤더** \> 에 **다음 단어 포함**을 선택 합니다.

     **입력 텍스트 헤더** 에 표시 되는 단어 문장 입력에 다음 단계를 수행 합니다.

     - **텍스트 입력**을 클릭 합니다. 표시 되는 **헤더 이름 지정** 대화 상자에서 **스팸 방지-Report** 를 입력 한 다음 **확인**을 클릭 합니다.

     - **단어 입력**을 클릭 합니다. **단어 또는 구 지정** 대화 상자가 나타나면 EOP 스팸 헤더 값 (**sfv: SPM**, **sfv: SKS**또는 **sfv: SKB**) 중 하나를 입력 하 **고 추가 아이콘** ![](../../media/ITPro-EAC-AddIcon.png)추가를 클릭 한 다음 **확인**을 클릭 합니다.

   - **다음을 수행**합니다. **메시지 속성** \> 수정을 선택 하 여 **SCL (스팸 지 수)을 설정**합니다.

     **SCL 지정** 대화 상자가 나타나면 **6** (기본값은 **5**)을 선택 합니다.

   작업이 끝나면 **저장** 을 클릭 합니다.

남은 EOP 스팸 결과 값 (**Sfv: SPM**, **SFV: SKS**또는 **sfv: SKB**)에 대해이 단계를 반복 합니다.

## <a name="use-the-exchange-management-shell-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>Exchange 관리 셸을 사용 하 여 EOP 스팸 메시지의 SCL을 설정 하는 메일 흐름 규칙 만들기

세 가지 메일 흐름 규칙을 만들려면 다음 구문을 사용 합니다.

```Powershell
New-TransportRule -Name "<RuleName>" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "<EOPSpamFilteringVerdict>" -SetSCL 6
```

예시:

```Powershell
New-TransportRule -Name "EOP SFV:SPM to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKS to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKB to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
```

자세한 구문 및 매개변수 정보 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule)을 참조하세요.

## <a name="how-do-you-know-this-worked"></a>작동 여부는 어떻게 확인하나요?

하이브리드 환경의 정크 메일 폴더에 스팸을 배달 하도록 독립 실행형 EOP를 구성 했는지 확인 하려면 다음 단계 중 하나를 수행 합니다.

- EAC에서 **메일 흐름** \> **규칙**으로 이동 하 고 규칙을 선택한 다음 편집 아이콘 **Edit** ![](../../media/ITPro-EAC-EditIcon.png) 편집을 클릭 하 여 설정을 확인 합니다.

- Exchange 관리 셸에서 Msrtcsip-rulename \<\> 을 메일 흐름 규칙의 이름으로 바꾸고 rul 다음 명령을 사용 하 여 설정을 확인 합니다.

  ```powershell
  Get-TransportRule -Identity "<RuleName>" | Format-List
  ```

- **스팸 메일에 대 한 아웃 바운드 메시지를 검사 하지**않는 외부 전자 메일 시스템에서, 해당 받는 사람에 게 요청 하지 않은 대량 전자 메일 (gtube) 메시지에 대 한 일반 테스트를 보낸 다음 해당 메시지가 정크 메일 폴더로 배달 되는지 확인 합니다. GTUBE 메시지는 맬웨어 설정을 테스트 하기 위한 EICAR (Computer Antivirus Research) 텍스트 파일에 대 한 유럽 협회와 비슷합니다.

  GTUBE 메시지를 보내려면 전자 메일 메시지 본문에 공백이 나 줄 바꿈 없이 다음 텍스트를 포함 합니다.

  ```text
  XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
  ```
