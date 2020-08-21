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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 5a6f2d7f-d998-4f31-b4f5-f7cbf6f38578
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 관리자는 EOP(Exchange Online Protection) 및 Office 365 ATP(Office 365 Advanced Threat Protection)에서 사용할 수 있는 피싱 방지 정책에 대해 알아할 수 있습니다.
ms.openlocfilehash: f671588ff4232c6ca1c1342475f48802bf1a0076
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825104"
---
# <a name="anti-phishing-policies-in-microsoft-365"></a>Microsoft 365의 피싱 방지 정책

Exchange Online 사서함이 있는 Microsoft 365 조직, Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직 및 Office 365 ATP(Advanced Threat Protection) 조직이 사용할 수 있습니다.

ATP 피싱 방지 정책은 Office 365 ATP가 있는 조직에서만 사용할 수 있습니다. 예제:

- Microsoft 365 Enterprise E5, Microsoft 365 Education A5 등.
- [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home)
- [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business)
- [추가 기능으로서의 Office 365 ATP](https://products.office.com/exchange/advance-threat-protection)

다른 모든 조직에는 피싱 방지 정책이 있습니다.

다음 표에서는 피싱 방지 정책과 ATP 피싱 방지 정책 사이의 높은 수준의 차이를 설명합니다.

****

|기능|피싱 방지 정책|ATP 피싱 방지 정책|
|---|:---:|:---:|
|자동으로 만들어진 기본 정책|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|사용자 지정 정책 만들기|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|정책 설정<sup>\*</sup>|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|가장 설정||![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|스푸핑 설정|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|고급 피싱 임계값||![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|

<sup>\*</sup> 기본 정책에서 정책 이름 및 설명은 읽기 전용이며(설명은 비어 있음) 정책이 적용되는 대상을 지정할 수 없습니다(기본 정책은 모든 받는 사람에게 적용).

피싱 방지 정책을 구성하려면 다음 문서를 참조하십시오.

- [EOP에서 피싱 방지 정책 구성](configure-anti-phishing-policies-eop.md)

- [Microsoft 365에서 ATP 피싱 방지 정책 구성하기](configure-atp-anti-phishing-policies.md)

이 문서의 나머지 부분에서는 피싱 방지 정책 및 ATP 피싱 방지 정책에서 사용할 수 있는 설정에 대해 설명합니다.

## <a name="policy-settings"></a>정책 설정

피싱 방지 정책 및 ATP 피싱 방지 정책에서 다음 정책 설정을 사용할 수 있습니다.

- **이름:** 기본 피싱 방지 정책의 이름을 바를 수는 없지만 직접 만드는 사용자 지정 정책의 이름을 지정하고 이름을 바일 수 있습니다.

- **설명** 기본 피싱 방지 정책에 설명을 추가할 수는 없지만 직접 만드는 사용자 지정 정책에 대한 설명을 추가하고 변경할 수 있습니다.

- **적용됨:** 피싱 방지 정책이 적용되는 내부 받는 사람을 식별합니다. 이 값은 사용자 지정 정책에서 필요하며 기본 정책에서 사용할 수 없음(모든 받는 사람에게 기본 정책을 적용)합니다.

  조건이나 예외는 한 번만 사용할 수 있지만, 조건이나 예외에 대한 값을 여러 개 지정할 수 있습니다. 동일한 조건의 여러 값이나 예외는 OR 논리를 사용합니다(예: _\<recipient1\>_ 혹은 _\<recipient2\>_). 다양한 조건이나 예외는 AND 논리를 사용합니다(예: _\<recipient1\>_ 및 _\<member of group 1\>_).

  - **받는 사람은**조직에 있는 하나 이상의 사서함, 메일 사용자 또는 메일 연락처입니다.
  - **받는 사람이 조직의**그룹입니다.
  - **받는 사람 도메인은**다음을 나타냅니다. Microsoft 365에서 구성된 허용 도메인 중 하나 이상입니다.

  - **제외: 규칙의**예외입니다. 설정 및 동작은 조건과 정확히 같습니다.

    - **받는 사람은**
    - **받는 사람이 다음의 구성원임**
    - **받는 사람의 도메인이 다음과 같습니다.**

## <a name="spoof-settings"></a>스푸핑 설정

스푸핑은 전자 메일 메시지의 보낸 사람 주소(전자 메일 클라이언트에 표시된 보낸 사람 주소)가 전자 메일 원본의 도메인과 일치하지 않는 경우입니다. 스푸핑에 대한 자세한 내용은 [Microsoft 365의 스푸핑 방지 보호 기능을 참조하세요.](anti-spoofing-protection.md)

다음 스푸핑 설정은 피싱 방지 정책 및 ATP 피싱 방지 정책에서 사용할 수 있습니다.

- **스푸핑 방지 보호 기능:** 스푸핑 방지 보호 기능을 사용하거나 사용하지 않도록 설정합니다. 사용하도록 설정된 값을 그대로 두는 것이 좋습니다. 스푸핑 **인텔리전스 정책을 사용하여** 스푸핑된 특정 내부 및 외부 보낸 사람을 허용하거나 차단합니다. 자세한 내용은 [Microsoft 365에 스푸핑 인텔리전스 구성](learn-about-spoof-intelligence.md)을 참조하세요.

  > [!NOTE]
  > 스푸핑 설정은 EOP의 기본 피싱 방지 정책, 기본 ATP 피싱 방지 정책, 새로 만들 사용자 지정 피싱 방지 정책 또는 ATP 피싱 방지 정책에서 기본적으로 사용됩니다. <br/><br/> MX 레코드가 Microsoft 365를 가리키지 않는 경우 스푸핑 방지 보호를 사용하지 않을 필요가 없습니다. 대신 커넥터에 대한 향상된 필터링을 사용하도록 설정합니다. 자세한 내용은 [Exchange Online에서 커넥터에 대한 향상된 필터링을 참조하세요.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)

  수신 거부시보낸 메시지의 경우 메시지에 수행할 작업을 지정할 수 있습니다.

  - **정크 메일 폴더로 메시지 이동:** 이 것이 기본값입니다. 메시지가 사서함으로 배달되고, 정크 메일 폴더로 이동됩니다. Exchange Online에서 사서함에 정크 메일 규칙이 활성화되어 있는 경우 메시지는 정크 메일 폴더로 이동됩니다(기본적으로 활성화되어 있음). 자세한 내용은 [Microsoft 365에서 Exchange Online 사서함에 대한 정크 메일 설정 구성을 참조하세요.](configure-junk-email-settings-on-exo-mailboxes.md)

  - **메시지 격리: 메시지를**의도된 받는 사람에게 보내는 대신 격리로 보냅니다. 격리에 대한 자세한 내용은 다음 문서를 참조하세요.

    - [Microsoft 365의 격리](quarantine-email-messages.md)
    - [Microsoft 365에서 관리자 권한으로 격리된 메시지 및 파일 관리](manage-quarantined-messages-and-files.md)
    - [Microsoft 365에서 사용자로 격리된 메시지 검색 및 해제하기](find-and-release-quarantined-messages-as-a-user.md)

- **인증되지 않은 보낸 사람:** 다음 섹션에서 설명을 참조하세요.

### <a name="unauthenticated-sender"></a>인증되지 않은 보낸 사람

인증되지 않은 발신자 식별은 이전 섹션에 [Spoof settings](#spoof-settings) 설명된 바와 같이 피싱 방지 정책 및 ATP 피싱 방지 정책에서 사용할 수 있는 스푸핑 설정의 일부입니다.

인증되지 **않은 보낸 사람** 설정은 Outlook에서 확인되지 않은 보낸 사람 ID를 사용하거나 사용하지 않도록 설정합니다. 특히 다음 사항에 유의합니다.

- 메시지가 SPF 또는 DKIM 확인을 통과하지 못하고 메시지가 DMARC 또는 복합 인증을 통과하지 못한 경우 보낸 사람의 사진에 물음표(?)가 [추가됩니다.](email-validation-and-authentication.md#composite-authentication) **and**

- 보낸 사람 주소의 도메인(chris@contoso.commichelle@fabrikam.com)이 DKIM 서명 또는 MAIL FROM 주소의 도메인과 다른 경우 태그를 통한 <u>태그(chris@contoso.com)가</u> **추가됩니다.** 이러한 주소에 대한 자세한 내용은 전자 [메일 메시지 표준의 개요를 참조하십시오.](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)

특정 보낸 사람의 메시지에 이러한 식별자가 추가되지 않도록 하려면 다음 옵션을 사용합니다.

- 보낸 사람이 스푸핑 인텔리전스 정책을 스푸핑할 수 있도록 허용합니다. 자세한 지침은 [Microsoft 365에서 스푸핑 인텔리전스 구성을 참조하세요.](learn-about-spoof-intelligence.md)

- [보낸 사람 도메인에 대한](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own) 전자 메일 인증을 구성합니다.
  
  - 보낸 사람 사진의 물음표가 들어오는 경우 SPF 또는 DKIM이 가장 중요합니다.
  - For the via tag, confirm the domain in the domain in the MAIL FROM address or the **MAIL FROM** address matches(or a subdomain of) in the From address.

자세한 내용은 Outlook [및 웹용 Outlook에서 의심스러운 Outlook.com 확인](https://support.microsoft.com/office/3d44102b-6ce3-4f7c-a359-b623bec82206)

## <a name="exclusive-settings-in-atp-anti-phishing-policies"></a>ATP 피싱 방지 정책의 독점 설정

이 섹션에서는 ATP 피싱 방지 정책에서만 사용할 수 있는 정책 설정에 대해 설명합니다.

> [!NOTE]
> 기본적으로 ATP 배타적 설정은 기본 정책에서도 구성되거나 설정되지 않습니다. 이러한 기능을 이용하려면 기본 ATP 피싱 방지 정책에서 이기능을 사용하도록 설정 및 구성하거나, 사용자 지정 ATP 피싱 방지 정책을 만들고 구성해야 합니다.

### <a name="impersonation-settings-in-atp-anti-phishing-policies"></a>ATP 피싱 방지 정책의 가장 설정

가장으로, 메시지의 보낸 사람 또는 보낸 사람 전자 메일 도메인이 다른 모양으로, 다른 항목은 각 도메인으로 구성됩니다.

- 도메인 의미 가장하는 contoso.com ćóntoso.com.
- 사용자 추가 기능의 michelle@contoso.com 가장하는 michele@contoso.com.

이 경우 가장된 도메인은 느의 한도(등록된 도메인, 구성된 전자 메일 인증 레코드 등)로 간주되어도 받는 사람에게는 해당 받는 사람에게 는 해당합니다.

다음 가장 설정은 ATP 피싱 방지 정책에서만 사용할 수 있습니다.

- **사용자를 보호할**수 있습니다. 지정된 내부 또는 외부 사용자를 가장할 수 없습니다. 예를 들어 임원(내부) 및 보드 구성원(외부)을 예로 들 수 있습니다. 최대 60명의 내부 및 외부 주소를 추가할 수 있습니다. 보호되는 사용자 목록은 적용 대상 설정에 적용되는 받는 사람 목록과 **다릅니다.**

  예를 들어 Executives 그룹에 적용되는 정책에서 felipea@contoso.com(Felipe Apodaca)를 보호되는 사용자로 지정할 수 있습니다. Executives 그룹의 구성원에게 전송된 인바운드 메시지에서 Felipe Apodaca가 가장된 경우 정책에 따라 작업을 수행합니다(가장된 사용자에 대해 구성한 작업).

- **보호할**도메인: 지정된 도메인이 가장되지 않도록 합니다. 예를 들어 소유하고 있는 모든 도메인(허용 도메인)[또는 특정](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)도메인(소유인 도메인 또는 파트너 도메인)을 예로 들 수 있습니다. 보호되는 도메인 목록은 적용 대상 설정에 적용되는 도메인 목록과 **다릅니다.**

  예를 들어 tailspintoys.com 그룹의 구성원에 적용되는 정책에서 보호되는 도메인으로 바를 지정합니다. Executives 그룹의 구성원에게 tailspintoys.com 사용자가 가장하는 인바운드 메시지는 정책(가장된 도메인에 대해 구성한 작업)별로 수행됩니다.

- **보호된 사용자 또는 도메인에 대한**작업 : 인바운드 메시지 중 위임 시도를 포함하는 인바운드 메시지에 수행할 작업을 선택합니다. 보호된 사용자를 대신하여 정책에 보호된 도메인을 오는 경우 수행할 작업을 선택합니다. 보호되는 사용자를 가장할 때와 보호되는 도메인 가장을 위한 서로 다른 작업을 지정할 수 있습니다.

  - **모든 작업 적용 금지**

  - **다른 전자 메일 주소로 메시지 리디렉션**: 메시지를 받는 사람이 아닌 지정된 받는 사람에게 보냅니다.

  - **정크 메일 폴더로 메시지**이동: 메시지가 사서함으로 배달되고, 정크 메일 폴더로 이동됩니다. Exchange Online에서 사서함에 정크 메일 규칙이 활성화되어 있는 경우 메시지는 정크 메일 폴더로 이동됩니다(기본적으로 활성화되어 있음). 자세한 내용은 [Microsoft 365에서 Exchange Online 사서함에 대한 정크 메일 설정 구성을 참조하세요.](configure-junk-email-settings-on-exo-mailboxes.md)

    - **메시지 격리: 메시지를**의도된 받는 사람에게 보내는 대신 격리로 보냅니다. 격리에 대한 자세한 내용은 다음 문서를 참조하세요.

    - [Microsoft 365의 격리](quarantine-email-messages.md)
    - [Microsoft 365에서 관리자 권한으로 격리된 메시지 및 파일 관리](manage-quarantined-messages-and-files.md)
    - [Microsoft 365에서 사용자로 격리된 메시지 검색 및 해제하기](find-and-release-quarantined-messages-as-a-user.md)

  - **메시지를 배달하고 숨은 참조 줄에**다른 주소를 추가: 메시지를 받는 사람에게 배달하고 지정된 받는 사람에게 자동으로 메시지를 전달합니다.

  - **메시지가 배달되기 전에 삭제: 모든**첨부 파일을 포함하여 전체 메시지를 자동으로 삭제합니다.

- **보안 팁: 가장 검사에**실패한 메시지를 표시하는 다음 가장 안전 팁을 사용하거나 사용하지 않도록 설정합니다.

  - **가장된 사용자: 시작**주소에 보호된 사용자가 포함됩니다.
  - **가장된 도메인**: From 주소에 보호된 도메인이 포함되어 있습니다.
  - **비정상적 문자**: From 주소에 보호된 보낸 사람 또는 도메인의 비정상적 문자 집합(예: 수학 기호 및 텍스트 또는 대문자 및 소문자 혼합)이 포함됩니다.

- **사서함 인텔리전스:** 자주 연락하는 연락처와 상태의 사용자 메일 패턴을 확인하는 AI(인공 지능)를 사용하거나 사용하지 않도록 설정합니다. 이 설정을 사용하면 AI가 정당한 전자 메일과 스푸핑된 전자 메일을 해당 연락처와 복합적으로 식별할 수 있습니다. 사서함 인텔리전스는 Exchange Online 사서함에만 사용할 수 있습니다.

- **사서함 인텔리전스 기반 가장 보호**: 각 사용자의 개별 보낸 사람 맵에 기반하여 향상된 가장 결과를 사용하거나 사용하지 않도록 설정합니다. Microsoft 365에서는 이러한 인텔리전스를 통해 사용자 가장 탐지를 사용자 지정하여 가양성을 더 좋습니다. 사용자 가장이 감지되면 메시지에 대해 수행할 특정 작업을 정의할 수 있습니다.

  - **모든 작업 적용 금지**
  - **다른 전자 메일 주소로 메시지 리디렉션**
  - **정크 메일 폴더로 메시지 이동**
  - **메시지 격리**
  - **메시지 배달 및 "Bcc 줄에 다른 주소 추가**
  - **메시지를 배달하기 전에 삭제**

- **신뢰할 수 있는 보낸 사람 및**도메인: 가장 보호 설정에 대한 예외입니다. 지정된 발신자 및 보낸 사람 도메인에서 받은 메시지는 정책에 의해 가장을 기반으로 하는 공격으로 분류되지 않습니다. 즉, 보호된 보낸 사람, 보호도메인 또는 사서함 인텔리전스 보호를 위한 작업은 이러한 신뢰할 수 있는 보낸 사람 또는 보낸 사람의 도메인에 적용되지 않습니다. 이러한 목록에 대한 최대 제한은 약 1000개 항목입니다.

### <a name="advanced-phishing-thresholds-in-atp-anti-phishing-policies"></a>ATP 피싱 방지 정책의 고급 피싱 임계값

다음 고급 피싱 임계값은 피싱 프리티드 결과를 결정하기 위해 메시지에 기계 학습 모델을 적용하기 위한 민감도를 제어하는 ATP 피싱 방지 정책에서만 사용할 수 있습니다.

- **1 - 표준**: 기본값 메시지에 대해 수행된 작업의 심각도는 메시지가 피싱(낮음, 보간, 높음 또는 매우 높은 신뢰도)의 신뢰도에 따라 달라지기를 달라냅니다. 예를 들어, 신뢰도가 매우 높은 피싱으로 식별된 메시지는 심각한 동작이 적용된 동시에, 낮은 신뢰도로 확인된 메시지는 심각도가 매우 낮은 메시지만 적용합니다.

- **2 - 적극적:** 신뢰도가 높은 피싱으로 식별되는 메시지는 매우 높은 신뢰도로 식별됩니다.

- **3 - 보다 적극적:** 중간 또는 높은 신뢰도로 피싱으로 식별되는 메시지는 매우 높은 신뢰도로 식별되는 것과 같이 처리됩니다.

- **4 - 가장 최적상태:** 낮음, 중간 또는 높은 신뢰도로 피싱으로 식별되는 메시지는 매우 높은 신뢰도로 식별되는 것보다 처리됩니다.

이 설정을 늘리면 가양성(정상 메시지가 좋지 않은 것으로 표시)이 늘어나면 됩니다. 권장되는 설정에 대한 자세한 [내용은 Office ATP 피싱 방지 정책 설정을 참조하십시오.](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings)
