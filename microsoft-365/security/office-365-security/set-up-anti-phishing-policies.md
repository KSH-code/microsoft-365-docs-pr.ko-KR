---
title: 피싱 방지 정책
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
ms.assetid: 5a6f2d7f-d998-4f31-b4f5-f7cbf6f38578
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 관리자는 EOP(Exchange Online Protection) 및 Office 365용 Microsoft Defender에서 사용할 수 있는 피싱 방지 정책에 대해 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: eeb15040f0e47f7d51852dadf68c4b0c37de0975
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929231"
---
# <a name="anti-phishing-policies-in-microsoft-365"></a>Microsoft 365의 피싱 방지 정책

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

피싱 방지 보호 설정을 구성하는 정책은 Exchange Online 사서함이 있는 Microsoft 365 조직, Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직 및 Office 365용 Microsoft Defender 조직에서 사용할 수 있습니다.

Microsoft Defender for Office 365의 피싱 방지 정책은 Office 365용 Defender가 있는 조직에서만 사용할 수 있습니다. 예를 들어 다음과 같습니다.

- Microsoft 365 Enterprise E5, Microsoft 365 Education A5 등
- [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home)
- [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business)
- [추가 기능으로 Office 365용 Microsoft Defender](https://products.office.com/exchange/advance-threat-protection)

다음 표에서는 EOP의 피싱 방지 정책과 Office 365용 Microsoft Defender의 피싱 방지 정책 간 높은 수준의 차이에 대해 설명되어 있습니다.

****

|기능|EOP의 피싱 방지 정책|Microsoft Defender for Office 365의 피싱 방지 정책|
|---|:---:|:---:|
|자동으로 만들어진 기본 정책|![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)|
|사용자 지정 정책 만들기|![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)|
|정책 설정<sup>\*</sup>|![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)|
|가장 설정||![확인 표시](../../media/checkmark.png)|
|스푸핑 설정|![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)|
|고급 피싱 임계값||![확인 표시](../../media/checkmark.png)|
|

<sup>\*</sup> 기본 정책에서 정책 이름과 설명은 읽기 전용(설명은 비어 있습니다)으로, 정책을 적용하는 사람을 지정할 수 없습니다(기본 정책은 모든 받는 사람에게 적용).

피싱 방지 정책을 구성하기 위해 다음 문서를 참조합니다.

- [EOP에서 스팸 방지 정책 구성하기](configure-anti-phishing-policies-eop.md)

- [Microsoft Defender for Office 365에서 피싱 방지 정책 구성](configure-atp-anti-phishing-policies.md)

이 문서의 나머지부분에서는 EOP 및 Office 365용 Defender의 피싱 방지 정책에서 사용할 수 있는 설정에 대해 설명하고 있습니다.

## <a name="policy-settings"></a>정책 설정

다음 정책 설정은 EOP의 피싱 방지 정책 및 Office 365용 Microsoft Defender에서 사용할 수 있습니다.

- **이름:** 기본 피싱 방지 정책의 이름을 변경할 수 없습니다. 사용자 지정 피싱 방지 정책을 만든 후 보안 및 준수 센터에서 정책의 이름을 & 수 없습니다.

- **설명** 기본 피싱 방지 정책에는 설명을 추가할 수 없지만 만드는 사용자 지정 정책에 대한 설명을 추가하고 변경할 수 있습니다.

- **적용 대상:** 피싱 방지 정책이 적용되는 내부 받는 사람을 식별합니다. 이 값은 사용자 지정 정책에 필요하며 기본 정책에서는 사용할 수 없습니다(기본 정책은 모든 받는 사람에게 적용).

  조건이나 예외는 한 번만 사용할 수 있지만, 조건이나 예외에 대한 값을 여러 개 지정할 수 있습니다. 동일한 조건의 여러 값이나 예외는 OR 논리를 사용합니다(예: _\<recipient1\>_ 혹은 _\<recipient2\>_). 다양한 조건이나 예외는 AND 논리를 사용합니다(예: _\<recipient1\>_ 및 _\<member of group 1\>_).

  - **받는 사람:** 조직에 있는 하나 이상의 사서함, 메일 사용자 또는 메일 연락처입니다.
  - **받는 사람이 조직에** 있는 하나 이상의 그룹 구성원입니다.
  - **받는 사람 도메인:** Microsoft 365에서 구성된 허용 도메인 중 하나 이상입니다.

  - **예외:** 규칙에 대한 예외입니다. 설정 및 동작은 조건과 정확히 같습니다.

    - **받는 사람은**
    - **받는 사람이 다음의 구성원인 경우**
    - **받는 사람 도메인**

  > [!NOTE]
  > 적용 **대상** 설정은 사용자 지정 피싱 방지 정책에서  정책이 적용되는 메시지 받는 사람을 <u>식별하는 데 필요합니다.</u> Microsoft Defender for Office 365의 피싱 [](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 방지 정책에는 이 문서 의 2부에서 설명하는 <u></u> 가장 보호를 받을 개별 보낸 사람 전자 메일 주소 또는 보낸 사람 도메인을 지정할 수 있는 가장 설정도 있습니다.

## <a name="spoof-settings"></a>스푸핑 설정

스푸핑은 전자 메일 메시지의 보낸 사람 주소(전자 메일 클라이언트에 표시하는 보낸 사람 주소)가 전자 메일 원본의 도메인과 일치하지 않는 경우입니다. 스푸핑에 대한 자세한 내용은 [Microsoft 365의](anti-spoofing-protection.md)스푸핑 방지 보호 기능을 참조하세요.

다음 스푸핑 설정은 EOP의 피싱 방지 정책 및 Office 365용 Microsoft Defender에서 사용할 수 있습니다.

- **스푸핑** 방지 보호: 스푸핑 방지 보호 기능을 활성화하거나 사용하지 않도록 합니다. 사용하도록 설정한 그대로 두는 것이 좋습니다. 스푸핑 인텔리전스 **정책을** 사용하여 스푸핑된 특정 내부 및 외부 보낸 사람이 허용하거나 차단할 수 있습니다. 자세한 내용은 [Microsoft 365에 스푸핑 인텔리전스 구성](learn-about-spoof-intelligence.md)을 참조하세요.

  > [!NOTE]
  >
  > - 스푸핑 방지 보호는 기본적으로 기본 피싱 방지 정책과 새로 만드는 사용자 지정 피싱 방지 정책에서 사용하도록 설정됩니다.
  >
  > - MX 레코드가 Microsoft 365를 사용하지 않는 경우 스푸핑 방지 보호 기능을 사용하지 않도록 설정할 필요가 없습니다. 대신 커넥터에 대해 향상된 필터링을 사용하도록 설정할 수 있습니다. 자세한 내용은 Exchange Online에서 커넥터에 대한 [향상된 필터링을 참조하세요.](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)
  >
  > - 스푸핑 방지 보호 기능을 사용하지 않도록 설정하면 복합 인증 검사에서 암시적 스푸핑 보호 기능만 [사용할 수](email-validation-and-authentication.md#composite-authentication) 있습니다. 보낸 사람이 정책이 quarantine 또는 reject로 설정된 위치를 [명시적 DMARC](use-dmarc-to-validate-email.md) 검사에 실패하면 메시지는 여전히 검리되거나 거부됩니다.

  차단된 스푸핑된 보낸 사람이 보낸 메시지의 경우 메시지에 대해 취할 작업을 지정할 수도 있습니다.

  - **정크 메일 폴더로** 메시지 이동: 이 값은 기본값입니다. 메시지가 사서함으로 배달된 후 정크 메일 폴더로 이동됩니다. Exchange Online에서는 사서함에서 정크 메일 규칙이 사용하도록 설정된 경우(기본적으로 사용하도록 설정되어 있는 경우) 메시지가 정크 메일 폴더로 이동됩니다. 자세한 내용은 [Microsoft 365에서 Exchange Online](configure-junk-email-settings-on-exo-mailboxes.md)사서함에 대한 정크 메일 설정 구성을 참조하세요.

  - **메시지 Quarantine the message**: Sends the message to quarantine instead of the intended recipients. 검사에 대한 자세한 내용은 다음 문서를 참조하십시오.

    - [Microsoft 365의 Quarantine](quarantine-email-messages.md)
    - [Microsoft 365에서 관리자로 고지된 메시지 및 파일 관리](manage-quarantined-messages-and-files.md)
    - [Microsoft 365에서 사용자로 고지된 메시지 찾기 및 릴리스](find-and-release-quarantined-messages-as-a-user.md)

- **Unauthenticated Sender:** 다음 섹션의 정보를 참조하세요.

### <a name="unauthenticated-sender"></a>비인식 보낸 사람

등록되지 않은 보낸 사람 ID는 이전 [](#spoof-settings) 섹션에 설명된 EOP 및 Office 365용 Microsoft Defender의 피싱 방지 정책에서 사용할 수 있는 스푸핑 설정의 일부입니다.

**Unauthenticated Sender** 설정은 Outlook에서 확인되지 않은 보낸 사람 ID를 설정하거나 사용하지 않도록 합니다. 특히 다음 사항에 유의합니다.

- 메시지가 SPF 또는 DKIM 검사를 통과하지 못하고 메시지가 DMARC 또는 복합  인증을 통과하지 못하면 보낸 사람 사진에 물음표(?)가 [추가됩니다.](email-validation-and-authentication.md#composite-authentication) 확인되지 않은 보낸 사람 ID를 사용 안 하게 하면 보낸 사람 사진에 물음표가 추가되지 않습니다.

- chris@contoso.com 보낸 사람 주소의 <u></u> 도메인(전자 메일 클라이언트에 표시되는 메시지 보낸 사람)이 DKIM 서명의 도메인 또는 **MAIL FROM** 주소의 도메인과 다른 경우(fabrikam.com 통해) via 태그(fabrikam.com)가 추가됩니다. 이러한 주소에 대한 자세한 내용은 전자 메일 메시지 표준 [개요를 참조하세요.](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)

  보낸 사람 주소의 도메인이 DKIM 서명 또는 MAIL FROM 주소의 도메인과 다른 경우, 확인되지 않은 보낸 사람 ID를 사용할 수 없는 경우 via 태그가 추가되는 것을 방지하지 않습니다.

물음표 또는 태그를 통해 특정 보낸 사람이 보낸 메시지에 추가되지 않도록 설정하기 위해 다음 옵션을 사용할 수 있습니다.

- 보낸 사람이 스푸핑 인텔리전스 정책에서 스푸핑하도록 허용합니다. 이 작업은 비인증된 보낸 사람 ID를 사용하지 않도록 설정한 경우 보낸 사람이 보낸 메시지에 via 태그가 나타나지 않도록 합니다. 자세한 내용은 [Microsoft 365에서 스푸핑 인텔리전스 구성을 참조하세요.](learn-about-spoof-intelligence.md)

- [보낸 사람 도메인에](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own) 대한 전자 메일 인증을 구성합니다.
  - 보낸 사람 사진의 물음표에 대해 SPF 또는 DKIM이 가장 중요합니다.
  - via 태그의 경우 DKIM 서명의 도메인 또는 **MAIL FROM** 주소가 보낸 편지함 주소의 도메인과 일치하는지(또는 해당 도메인의 하위 도메인인 경우) 확인

자세한 내용은 Outlook.com Outlook에서 의심스러운 메시지 [식별을 참조하세요.](https://support.microsoft.com/office/3d44102b-6ce3-4f7c-a359-b623bec82206)

## <a name="exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365의 피싱 방지 정책에 대한 단독 설정

이 섹션에서는 Microsoft Defender for Office 365의 피싱 방지 정책에서만 사용할 수 있는 정책 설정에 대해 설명합니다.

> [!NOTE]
> Microsoft Defender for Office 365의 기본 피싱 [](set-up-anti-phishing-policies.md#spoof-settings) 방지 정책은 모든 받는 사람에 대해 스푸핑 보호 및 사서함 인텔리전스를 제공합니다. 그러나 사용 가능한 [](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 다른 가장 보호 [](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 기능 및 고급 설정은 기본 정책에서 구성되거나 사용하도록 설정되지 않습니다. 모든 보호 기능을 사용하도록 설정하려면 기본 피싱 방지 정책을 수정하거나 추가 피싱 방지 정책을 만들 수 있습니다.

### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365의 피싱 방지 정책의 가장 설정

가장은 메시지의 보낸 사람 또는 보낸 사람 전자 메일 도메인이 실제 보낸 사람 또는 도메인과 유사하게 보이는 위치입니다.

- 도메인 contoso.com의 가장 예는 ćóntoso.com입니다.
- 사용자 michelle@contoso.com의 가장 예는 michele@contoso.com입니다.

가장된 도메인은 받는 사람을 속이려는 의도가 있다는 것을 제외하고 합법적(등록된 도메인, 구성한 전자 메일 인증 기록 등)으로 간주될 수 있습니다.

다음 가장 설정은 Office 365용 Microsoft Defender의 피싱 방지 정책에서만 사용할 수 있습니다.

- **보호할 사용자:** 지정된 내부 또는 외부 전자 메일 주소가 메시지 보낸 사람으로 **가장되지 않도록 합니다.** 예를 들어 회사의 부사장에게 내부 회사 정보를 보내달라는 전자 메일 메시지를 받게 됩니다. 이 작업을 하나요? 많은 사람들이 생각하지 않고 회신을 보내고 있습니다.

  보호된 사용자를 사용하여 내부 및 외부 보낸 사람 전자 메일 주소를 추가하여 가장으로부터 보호할 수 있습니다. 사용자 가장으로부터 보호되는 보낸 사람 목록은 정책이 적용되는 받는  사람 목록과 다릅니다(기본 정책의 모든 받는 사람, 정책 설정 섹션의 적용 대상 [](#policy-settings) 설정에 구성된 특정 받는 사람).  

  > [!NOTE]
  >
  > - 각 피싱 방지 정책에서 보호되는 사용자(보낸 사람 전자 메일 주소)를 최대 60명까지 지정할 수 있습니다. 동일한 보호된 사용자를 여러 정책에 지정할 수 없습니다. 따라서 받는 사람에게 적용되는 정책의 수에 관계없이 각 개별 받는 사람에 대해 보호되는 사용자(보낸 사람 전자 메일 주소)의 최대 수는 60개입니다. 정책 우선 순위 및 첫 번째 정책이 적용된 후 정책 처리가 중지되는 방법에 대한 자세한 내용은 전자 메일 보호의 순서 및 우선 [순위를 참조하세요.](how-policies-and-protections-are-combined.md)
  >
  > - 보낸 사람 및 받는 사람이 이전에 전자 메일을 통해 통신한 경우 사용자 가장 보호가 작동하지 않습니다. 보낸 사람 및 받는 사람이 전자 메일을 통해 통신한 적이 없는 경우 가장 시도로 메시지가 식별됩니다.

  기본적으로 사용자가 보호할 가장 보호를 위해 보낸 사람 전자 메일 주소는 **구성되지 않습니다.** 따라서 기본적으로 기본 정책이나 사용자 지정 정책에서 보낸 사람 전자 메일 주소에 가장 보호가 적용되지 않습니다.

  사용자 목록에 내부 또는 외부  전자 메일 주소를 추가하여  보호할 경우 해당 보낸 사람이 보낸 메시지에 가장 보호 검사가 적용됩니다. 메시지가 정책이 적용되는 받는 사람(기본 정책의 모든  받는 사람)에게 메시지를 보낼 경우 가장이 확인됩니다.  **사용자 지정 정책의** 받는 사람에게 적용됩니다. 보낸 사람 전자 메일 주소에서 가장이 감지되면 사용자에 대한 가장 보호 작업이 메시지에 적용됩니다(메시지로 수행할 작업, 가장된 사용자 보안 팁 표시 여부 등).

- **보호할 도메인:** 지정된 도메인이 메시지 보낸 사람 도메인에서 가장되지 **않도록 합니다.** 예를 들어 소유한 모든 도메인(허용[도메인)](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)또는 특정 도메인(소유한 도메인 또는 파트너 도메인)입니다. 가장으로부터  보호되는 보낸 사람 도메인 목록은 정책이 적용되는 받는 사람 목록과 다릅니다(기본 정책의 모든 받는 사람, 정책 설정 섹션의  적용 대상 [](#policy-settings) 설정에 구성된 특정 받는 사람). 

  > [!NOTE]
  > 모든 피싱 방지 정책에서 정의할 수 있는 보호된 도메인의 최대 수는 50개입니다.

  기본적으로 보호할 도메인의 가장 보호를 위해 보낸 사람 도메인은 **구성되지 않습니다.** 따라서 기본적으로 보낸 사람 도메인은 기본 정책이나 사용자 지정 정책에서 가장 보호가 적용되지 않습니다.

  도메인에 도메인을 추가하여 목록을 보호하면 해당  도메인의 보낸 사람이 보낸 메시지에 가장 보호 검사가 적용됩니다.  메시지가 정책이 적용되는 받는 사람(기본 정책의 모든  받는 사람)에게 메시지를 보낼 경우 가장이 확인됩니다.  **사용자 지정 정책의** 받는 사람에게 적용됩니다. 보낸 사람 도메인에서 가장이 감지되면 도메인에 대한 가장 보호 작업이 메시지에 적용됩니다(메시지로 수행할 작업, 가장된 사용자 보안 팁 표시 여부 등).

- **보호된** 사용자 또는 도메인에 대한 작업: 정책의 보호된 사용자 및 보호된 도메인에 대한 가장 시도가 포함된 인바운드 메시지에 대해 수행할 작업을 선택하십시오. 보호된 사용자 가장과 보호된 도메인의 가장에 대해 서로 다른 작업을 지정할 수 있습니다.

  - **어떤 작업도 적용하지 않습니다.**

  - **메시지를 다른** 전자 메일 주소로 리디렉션: 지정된 받는 사람이 아닌 지정된 받는 사람에게 메시지를 보냅니다.

  - **정크** 메일 폴더로 메시지 이동: 메시지가 사서함으로 배달된 후 정크 메일 폴더로 이동됩니다. Exchange Online에서는 사서함에서 정크 메일 규칙이 사용하도록 설정된 경우(기본적으로 사용하도록 설정되어 있는 경우) 메시지가 정크 메일 폴더로 이동됩니다. 자세한 내용은 [Microsoft 365에서 Exchange Online](configure-junk-email-settings-on-exo-mailboxes.md)사서함에 대한 정크 메일 설정 구성을 참조하세요.

    - **메시지 Quarantine the message**: Sends the message to quarantine instead of the intended recipients. 검사에 대한 자세한 내용은 다음 문서를 참조하십시오.

    - [Microsoft 365의 Quarantine](quarantine-email-messages.md)
    - [Microsoft 365에서 관리자로 고지된 메시지 및 파일 관리](manage-quarantined-messages-and-files.md)
    - [Microsoft 365에서 사용자로 고지된 메시지 찾기 및 릴리스](find-and-release-quarantined-messages-as-a-user.md)

  - **메시지를 배달하고 Bcc** 줄에 다른 주소를 추가합니다. 메시지를 의도된 받는 사람에게 배달하고 지정된 받는 사람에게 자동으로 배달합니다.

  - **배달되기** 전에 메시지 삭제: 모든 첨부 파일을 포함하여 전체 메시지를 자동으로 삭제합니다.

- **안전 팁:** 가장 검사에 실패한 메시지를 표시하는 다음과 같은 가장 안전 팁을 활성화 또는 비활성화합니다.

  - **가장된 사용자:** 시작 주소에 보호된 사용자가 포함되어 있습니다.
  - **가장된 도메인:** 시작 주소에 보호된 도메인이 포함되어 있습니다.
  - **비정상 문자:** 보낸 사람 주소에는 보호된 보낸 사람 또는 도메인의 비정상적인 문자 집합(예: 수학 기호 및 텍스트 또는 대문자 및 소문자 혼합)이 포함되어 있습니다.


  > [!IMPORTANT]
  >
  > 보낸 사람 및 받는 사람 간의 첫 번째 접촉 중에 나타나는 보안 팁을 사용하도록 설정하는 데 권장 사항: 가장  보안 팁이 꺼져 있어도 메일 흐름 규칙(전송 규칙)을 사용하여 **X-MS-Exchange-EnableFirstContactSafetyTip이라는** 메시지 헤더를 메시지에 사용할 수 있는 값과 함께 추가하는 것이 좋습니다.   보안 팁은 보낸 사람이 메시지를 처음 받을 때 또는 보낸 사람에게 메시지를 자주 수신하지 않는 경우 받는 사람에게 알릴 것입니다. 이 기능을 통해 잠재적인 가장 공격으로부터 보안을 강화할 수 있습니다. 
  > :::image type="content" source="../../media/safety-tip-first-contact-multiple-recipients.png" alt-text="여러 받는 사람이 있는 가장 보호를 위한 안전 팁 텍스트입니다.":::

- **사서함 인텔리전스:** 자주 연락하는 사용자 전자 메일 패턴을 결정하는 인공 지능(AI)을 활성화하거나 비활성화합니다. 이 설정은 AI가 합법적인 전자 메일과 스푸핑된 전자 메일을 해당 연락처와 구분하는 데 도움이 됩니다. 사서함 인텔리전스는 Exchange Online 사서함에만 사용할 수 있습니다.

- **사서함 인텔리전스 기반** 가장 보호: 각 사용자의 개별 보낸 사람 맵에 따라 향상된 가장 결과를 설정하거나 해제합니다. 이 인텔리전스를 통해 Microsoft 365는 사용자 가장 검색을 사용자 지정하고 가짓 긍정을 보다 잘 처리할 수 있습니다. 사용자 가장이 감지되면 메시지에 대해 취할 특정 작업을 정의할 수 있습니다.

  - **어떤 작업도 적용하지 않습니다.**
  - **메시지를 다른 전자 메일 주소로 리디렉션**
  - **정크 메일 폴더로 메시지 이동**
  - **메시지 Quarantine the message**
  - **메시지를 배달하고 Bcc 줄에 다른 주소를 추가합니다.**
  - **배달되기 전에 메시지 삭제**

- **신뢰할 수 있는 보낸 사람 및 도메인:** 가장 보호 설정에 대한 예외입니다. 지정된 보낸 사람 및 보낸 사람 도메인의 메시지는 정책에 의해 가장 기반 공격으로 분류되지 않습니다. 즉, 보호된 보낸 사람, 보호된 도메인 또는 사서함 인텔리전스 보호에 대한 작업은 이러한 신뢰할 수 있는 보낸 사람 또는 보낸 사람 도메인에 적용되지 않습니다. 이러한 목록의 최대 제한은 약 1,000개 항목입니다.

### <a name="advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365의 피싱 방지 정책의 고급 피싱 임계값

다음 고급 피싱 임계값은 Microsoft Defender for Office 365의 피싱 방지 정책에서만 사용할 수 있습니다. 이러한 임계값은 피싱 판정을 결정하기 위해 메시지에 기계 학습 모델을 적용하기 위한 민감도를 제어합니다.

- **1 - 표준:** 이 값은 기본값입니다. 메시지에 수행되는 작업의 심각도는 메시지의 피싱 신뢰도(낮음, 보통, 높음 또는 매우 높은 신뢰도)에 따라 달라 습니다. 예를 들어 신뢰도가 매우 높은 피싱으로 식별된 메시지에는 가장 심각한 작업이 적용되고 신뢰도가 낮은 피싱으로 식별된 메시지는 심각도가 낮은 작업이 적용되지 않습니다.

- **2 - 적극적**: 신뢰도가 높은 피싱으로 식별된 메시지는 매우 높은 신뢰도로 식별된 것으로 간주됩니다.

- **3 -** 보다 적극적인 : 보통 또는 높은 수준의 신뢰도로 피싱으로 식별된 메시지는 매우 높은 신뢰도로 식별된 것으로 간주됩니다.

- **4 -** 가장 적극적: 낮은 신뢰도, 보통 또는 높은 신뢰도로 피싱으로 식별된 메시지는 매우 높은 신뢰도로 식별된 것으로 처리됩니다.

이 설정을 늘리면 가음성(양호한 것으로 표시된 양호한 메시지)의 가능성이 증가합니다. 권장 설정에 대한 자세한 내용은 [Microsoft Defender for Office 365 설정의 피싱 방지 정책을 참조하세요.](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)