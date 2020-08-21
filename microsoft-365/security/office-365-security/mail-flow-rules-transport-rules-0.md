---
title: EOP의 메일 흐름 규칙
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9c2cf227-eff7-48ef-87fb-487186e47363
description: 메일 흐름 규칙(전송 규칙)을 사용하여 조직을 통과하는 메시지를 식별하고 작업을 수행할 수 있습니다.
ms.openlocfilehash: ed17ac62009f5e766772095985441fad2367edf4
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827704"
---
# <a name="mail-flow-rules-transport-rules-in-standalone-eop"></a>독립형 EOP 메일 흐름 규칙(전송 규칙)

Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서는 메일 흐름 규칙(전송 규칙이라고도 함)을 사용하여 조직을 통과하는 메시지를 식별하고 작업을 수행할 수 있습니다.

이 항목에서는 메일 흐름 규칙의 구성 요소 및 해당 규칙의 작동 방식에 대해 설명합니다.

메일 흐름 규칙을 만들고 복사하고 관리하는 단계는 [Exchange Online의 메일 흐름 규칙 관리를 참조하세요.](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules) 각 규칙에 대해 규칙을 적용하거나, 규칙을 테스트하거나, 규칙을 테스트하고 보낸 사람에게 알릴 수 있는 옵션이 제공됩니다. 테스트 옵션에 대한 자세한 내용은 Exchange [Online의 메일 흐름 규칙 및](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/test-mail-flow-rules) 정책 [팁을 참조하십시오.](https://docs.microsoft.com/exchange/security-and-compliance/data-loss-prevention/policy-tips)

해당 규칙이 적용될 때 후행 및 세90-9-7-9드가 나오는 드는 이후 처리를 통해 일치하는 [메시지에 대한 요약 및 세부 보고서를 볼 수 있습니다.](https://docs.microsoft.com/exchange/monitoring/use-mail-protection-reports)

메일 흐름 규칙을 사용해서 특정 메시징 정책을 실행하려면 다음 항목을 참조하세요.

- [메일 흐름 규칙을 사용하여 Exchange Online에서 메시지 첨부 파일 조사](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)

- [Office 365 Enterprise의 암호화 설정](../../compliance/set-up-encryption.md)

- [Exchange Online의 조직 전체의 메시지 고지 사항, 서명, 바닥글 또는 머리글](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers)

- [메일 흐름 규칙을 사용하여 메시지의 스팸 신뢰 수준(SCL) 설정](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)

- [EOP에서 차단할 보낸 사람 목록 만들기](create-block-sender-lists-in-office-365.md)

- [Exchange 온라인 보호의 첨부 파일 차단을 통한 맬웨어 위협 감소](reducing-malware-threats-through-file-attachment-blocking-in-exchange-online-pro.md)

- [Office 365에서 전자 메일 메시지를 암호화하거나 암호를 해암호화하는 규칙 정의](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)

다음 비디오에서는 독립 실행형 EOP의 메일 흐름 규칙을 설정하는 데모를 제공합니다.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/7cdcd2cb-9382-4065-98e1-81257b32a189?autoplay=false]

## <a name="mail-flow-rule-components"></a>메일 흐름 규칙 구성 요소

메일 흐름 규칙은 조건, 예외, 작업 및 속성으로 구성됩니다.

- **조건:** 작업을 적용할 메시지를 식별합니다. 받는 사람, 보낸 사람, 참조 필드 같은 메시지 헤더 필드를 검사하는 조건도 있습니다. 메시지 제목, 본문, 첨부 파일, 메시지 크기 또는 메시지 분류 같은 메시지 속성을 검사하는 조건도 있습니다. 대부분의 조건에서는 비교 연산자(예: 같음, 같지 않음, 같지 않음, 포함하는 값)를 지정하여 일치시어로 사용할 값을 지정해야 합니다. 조건이나 예외가 없는 경우 규칙이 모든 메시지에 적용됩니다.

독립 실행형 EOP의 메일 흐름 규칙 조건에 대한 자세한 내용은 Exchange Online에서 메일 흐름 규칙 조건 및 [예외(조건자)를 참조하세요.](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

- **예외:** 선택적으로 해당 작업이 적용하면 안 되는 메시지를 식별합니다. 조건에서 사용할 수 있는 동일한 메시지 식별자를 예외에서도 사용할 수 있습니다. 예외는 조건을 재정의하며, 메시지가 구성된 모든 조건과 일치하더라도 규칙 작업이 메시지에 적용되지 않도록 합니다.

- **작업:** 규칙의 조건과 일치하고 예외와는 일치하지 않는 메시지에 수행할 작업을 지정합니다. 예외는 조건보다 우선하며, 메시지가 모든 조건과 일치하더라도 작업이 전자 메일 메시지에 적용되지 않도록 합니다.

독립 실행형 EOP에서 사용할 수 있는 메일 흐름 규칙 동작에 대한 자세한 내용은 [Exchange Online의 메일 흐름 규칙 동작을 참조하세요.](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- **Properties:** Specify other rules settings that are nconditions, exceptions or actions. 예를 들어, 규칙이 적용되는 시기, 규칙 적용 또는 테스트 여부, 규칙이 활성화되는 시기를 지정합니다.

  자세한 내용은 이 항목의 [메일 흐름 규칙 속성 섹션을](#mail-flow-rule-properties) 참조하세요.

### <a name="multiple-conditions-exceptions-and-actions"></a>여러 조건, 예외 및 작업

Use a transport rule so messages can bypass Clutter

****

|구성 요소|논리|Comments|
|---|---|---|
|설명|그리고|메시지는 규칙의 모든 조건과 일치해야 합니다. 하나의 조건 또는 다른 조건과 일치해야 하는 경우 각 조건에 대해 별도의 규칙을 사용합니다. 예를 들어 특정 텍스트가 포함된 메시지와 첨부 파일이 있는 메시지에 동일한 고지 사항을 추가하려면 각 조건에 대해 하나의 규칙을 만듭니다. EAC에서 규칙을 쉽게 복사할 수 있습니다.|
|메시지는 규칙의 모든 조건과 일치해야 합니다. 하나의 조건 또는 다른 조건과 일치해야 하는 경우 각 조건에 대해 별도의 규칙을 사용합니다. 예를 들어 패턴과 일치하는 콘텐츠가 있는 메시지 및 첨부 파일이 있는 메시지에 동일한 고지 사항을 추가하려면 각 조건에 대해 하나의 규칙을 만듭니다. 규칙은 쉽게 복사할 수 있습니다.|또는|일부 조건에는 둘 이상의 값을 지정할 수 있습니다. 메시지는 지정된 값의 임의의(전체가 아무 값도 일치해야 합니다.)과 일치해야 합니다. 예를 들어 전자 메일 메시지의 제목주 가격 정보가 있고 **제목에** Contoso 또는 주식 시세가 일치하는 조건이 포함되어 있는 경우 제목에 지정된 값 중 적어도 하나 이상이 포함되어 있기 때문에 조건이 만족스됩니다.|
|일부 조건에는 둘 이상의 값을 지정할 수 있습니다. 여러 개의 값을 입력할 수 있는 조건의 경우 메시지가 해당 조건에 대해 지정된 값 중 하나에만 일치하면 됩니다. 예를 들어 전자 메일 메시지의 제목이 주가 정보이고 제목에 다음 단어 포함 조건이 Contoso 또는 주가라는 단어와 일치하도록 구성된 경우 조건 값 중 적어도 하나가 제목에 포함되어 있으므로 조건이 충족됩니다.|또는|예외 중 하나라도 메시지와 일치하면 메시지가 적용되지 않습니다. 메시지가 모든 예외와 일치할 일이 없습니다.|
|예외 중 하나라도 메시지와 일치하면 작업은 처리되지 않습니다. 메시지가 모든 예외와 일치할 필요는 없습니다.|그리고|규칙 조건에 일치하는 메시지에는 규칙에 지정된 모든 작업이 적용됩니다. 예외는 조건과 정반대의 방식으로 처리됩니다. <br/><br/> 규칙 조건에 일치하는 메시지에는 규칙에 지정된 모든 작업이 적용됩니다. 예를 들어, 메시지 제목 앞에 다음 추가 및 숨은 참조란에 받는 사람 추가 작업을 선택한 경우 두 작업 모두 메시지에 적용됩니다. 즉, 지정된 문자열이 메시지 제목 앞에 붙고 지정된 받는 사람이 숨은 참조로 추가됩니다.<br/><br/> 아주 추가 등의 일부 작업을 적용할 경우 후속 규칙이 메시지에 적용되지 않습니다. 메시지 처리 등의 다른 작업은 추가 작업을 허용하지 않습니다.|
|

### <a name="mail-flow-rule-properties"></a>메일 흐름 규칙 속성

다음 표에서는 메일 흐름 규칙에 사용할 수 있는 규칙 속성을 설명합니다.

****

|EAC의 속성 이름|PowerShell의 매개 변수 이름|설명|
|---|---|---|
|**우선 순위**|_우선 순위_|규칙이 메시지에 적용되는 순서를 나타냅니다. 기본 우선 순위는 규칙이 만들어진 기준입니다(이전 규칙에는 이전 규칙보다 우선순위가 높고 높은 우선 순위 규칙이 낮은 우선 순위 규칙보다 먼저 처리됩니다). <br/><br/> EAC에서 규칙을 규칙 목록의 위 또는 아래로 이동하여 규칙 우선 순위를 변경합니다. PowerShell에서 우선 순위 번호(0이 가장 높은 우선 순위)를 설정합니다. <br/><br/> 예를 들어 신용 카드 번호가 포함된 메시지는 거부하는 규칙과 승인을 요구하는 또 다른 규칙이 있을 때 거부 규칙이 먼저 적용되도록 한 다음 다른 규칙이 적용되지 않도록 할 수 있습니다.  |
|**Mode**|_Mode_|규칙에서 메시지를 즉시 처리할지, 메시지 배달에 영향을 주지 않고 규칙을 테스트할지(데이터 손실 방지 또는 DLP 정책 팁 포함 또는 제외) 여부를 지정할 수 있습니다. <br/><br/> 정책 설명은 Outlook 또는 웹용 Outlook에 메시지를 생성하는 사용자에게 발생할 수 있는 정책 위반에 대한 정보를 제공하는 간단한 메모를 웹용 Outlook에 표시합니다. 자세한 내용은 **정책 팁**을 참조하세요. <br/><br/> 모드에 대한 자세한 내용은 메일 흐름 **규칙 테스트를 참조하세요.**|
|**다음 날짜에 이 규칙 활성화** <br/><br/> **다음 날짜에 이 규칙 비활성화**|_ActivationDate_ <br/> _ExpiryDate_|규칙이 활성화된 날짜 범위를 지정합니다.|
|**선택되어** 있는지 또는 선택되지 않은 확인란|새 규칙: **New-TransportRule** cmdlet에서 Enabled 매개 변수를 사용하도록 설정합니다. _Enabled_ <br/><br/> 기존 규칙: **Enable-TransportRule 또는** **Disable-TransportRule cmdlet을** 사용합니다. <br/><br/> 값은 규칙의 **State** 속성에 표시됩니다.|사용 하지 않도록 설정 한 규칙을 만들고 테스트 준비가 되면 사용 하도록 설정할 수 있습니다. 또는 규칙을 삭제하지 않고도 설정을 보존하도록 사용하지 않을 수 있습니다.|
|**규칙 처리가 완료되지 않은 경우 메시지를 연기합니다.**|_RuleErrorAction_|규칙 처리를 완료할 수 없는 경우 메시지를 처리할 방법을 지정할 수 있습니다. 기본적으로는 규칙이 무시되지만, 처리를 위해 메시지를 다시 전송할 수도 있습니다.|
|**메시지에서 보낸 사람 주소 일치**|_SenderAddressLocation_|규칙이 보낸 사람의 전자 메일 주소를 검사하는 조건이나 예외를 사용하는 경우 메시지 헤더나 메시지 봉투 또는 둘 다에서 값을 찾을 수 있습니다.|
|**추가 규칙 처리 중지**|_SenderAddressLocation_|이 작업은 규칙을 위한 동작이지만 EAC에서 속성과 비슷합니다. 규칙이 메시지를 처리한 후 메시지에 추가 규칙 적용을 중지하도록 선택할 수 있습니다.|
|**Comments**|_Comments_|규칙에 대한 설명을 입력할 수 있습니다.|
|

## <a name="how-mail-flow-rules-are-applied-to-messages"></a>메시지에 메일 흐름 규칙을 적용하는 방법

조직을 통해 전송되는 모든 메시지가 조직에서 사용하도록 설정된 메일 흐름 규칙을 위하여 평가됩니다. 규칙은 EAC의 메일 흐름 규칙 페이지에 표시된 **순서** \> **Rules** 또는 PowerShell의 _해당 우선 순위 매개_ 변수 값에 따라 처리됩니다.

조직의 모든 메시지가 조직에 대해 사용하도록 설정된 전송 규칙을 기준으로 평가됩니다. 규칙은 EAC의 규칙 페이지에 표시된 순서 또는 exsdkExMSH의 Priority 매개 변수 값에 따라 처리됩니다.  이 설정은 여러 메일 흐름 규칙(메시지에 적용하려는 규칙이 무엇인 메시지의 규칙이 있을까?)의 조건과 일치하는 메시지에 중요합니다. All? 하나만))을 사용할 수 있습니다.

### <a name="differences-in-processing-based-on-message-type"></a>메시지 유형에 따른 처리 방식의 차이

조직을 통과하는 메시지 유형에는 몇 가지가 있습니다. 다음 표에는 메일 흐름 규칙에 의해 처리될 수 있는 메시지 유형이 나와 있습니다.

****

|조직을 통과하는 메시지 유형에는 몇 가지가 있습니다. 다음 표에는 전송 규칙으로 처리될 수 있는 메시지 유형이 나와 있습니다.|메시지 유형|
|---|---|
|**일반 메시지:** 단일 RTF(서식 있는 텍스트), HTML 또는 일반 텍스트 메시지 본문 또는 여러 부분으로 된 메시지 본문 집합이나 대체 메시지 본문 집합이 포함된 메시지입니다.|예|
|**Office 365 메시지 암호화:** Office 365에서 Office 365 메시지 암호화로 암호화된 메시지 자세한 내용은 [Office 365의 암호화](https://docs.microsoft.com/microsoft-365/compliance/encryption)를 참조하세요.|규칙을 사용하면 항상 봉투 헤더에 액세스하여 해당 헤더를 검사하는 조건을 바이러스립니다. <br/><br/> 규칙이 암호화된 메시지의 내용을 검사하거나 수정하려면 전송 암호 해독이 활성화되어 있는지 확인해야 합니다(필수 또는 선택 사항, 기본값은 선택 사항임). 자세한 내용은 Office 365에서 전자 메일 메시지를 암호화하거나 [암호를 해두는 규칙 정의를 참조하세요.](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)|
|**S/MIME 암호화 메시지**|규칙을 사용하여 봉투 헤더에 액세스한 다음 해당 헤더를 검사하는 조건을 바기반으로 메시지를 처리할 수 있습니다. <br/><br/> 메시지의 콘텐츠를 검사해야 하는 조건이 포함된 규칙이나 메시지 내용을 수정하는 작업은 처리할 수 없습니다.|
|**RMS로 보호된**메시지: AD RMS(Active Directory Rights Management Services) 또는 RMS(Azure 권한 관리) 정책이 적용된 메시지입니다.|규칙을 사용하면 항상 봉투 헤더에 액세스하여 해당 헤더를 검사하는 조건을 바이러스립니다. <br/><br/> RMS로 보호된 메시지의 내용을 검사하거나 수정하는 규칙을 사용하려면 전송 암호 해독이 사용하도록 설정되어 있는지 확인해야 합니다(필수 또는 선택 사항, 기본값은 옵션임).|
|**일반 텍스트 서명 메시지:** 서명되었지만 암호화되지 않은 메시지입니다.|예|
|**UM 메시지:** 음성 사서함, 팩스, 미재 전화 알림, Microsoft 큐를 사용하여 만들었거나 전달된 메시지 등 통합 메시징 서비스에서 생성 또는 처리한 메시지Outlook Voice Access.|예|
|**익명 메시지:** 익명 보낸 사람이 보낸 메시지|예|
|**읽기 보고서:** 받는 사람이 읽기 확인을 요청하는 경우에 생성되는 보고서입니다. 보고서 읽기에는 메시지 클래스를 사용하거나 사용할 `IPM.Note*.MdnRead` 수 `IPM.Note*.MdnNotRead` 있습니다.|예|
|

## <a name="what-else-should-i-know"></a>더 알아야 할 것은 무엇입니까?

- **규칙의** 버전 **또는 RuleVersion** 속성 값은 Exchange Online Protection에서 중요하지 않습니다.

- 메일 흐름 규칙을 만들거나 수정한 다음에는 새 규칙이나 업데이트된 규칙이 메시지에 적용되는 데 최대 30분이 걸릴 수 있습니다.

## <a name="for-more-information"></a>자세한 내용

[메일 흐름 규칙을 사용하여 Exchange Online에서 메시지 첨부 파일 조사](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)

[Office 365의 전자 메일 암호화](../../compliance/email-encryption.md)

[저널, 전송 및 받은 편지함 규칙 제한](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#journal-transport-and-inbox-rule-limits)
