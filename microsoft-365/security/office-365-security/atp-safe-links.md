---
title: 안전한 링크
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.topic: overview
f1_keywords:
- "197503"
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- ZVO160
- ZXL160
- ZPP160
- ZWD160
ms.assetid: dd6a1fef-ec4a-4cf4-a25a-bb591c5811e3
description: 이 문서에서 관리자는 피싱 및 악의적인 URL을 사용하는 기타 공격으로부터 조직을 보호하기 위해 Office 365용 Defender의 안전 링크 보호에 대해 학습할 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 15168f2fff5ce1e4afbef5ff71a780de896f0bbf
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288696"
---
# <a name="safe-links-in-microsoft-defender-for-office-365"></a>Office 365용 Microsoft Defender의 안전한 링크

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

> [!IMPORTANT]
> 이 문서는 [Office 365용 Microsoft Defender](office-365-atp.md)가 있는 비즈니스 고객을 대상으로 합니다. Outlook.com, Microsoft 365 Family 또는 Microsoft 365 Personal을 사용 중일 때 Outlook의 Safelinks에 대한 자세한 내용은 고급 보안 Outlook.com [참조하세요.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)

안전한 링크는 [Office 365용 Defender의](office-365-atp.md) 기능으로, 메일 흐름에서 인바운드 전자 메일 메시지의 URL 검색 및 다시 기록, 클릭 시 전자 메일 메시지 및 기타 위치의 URL 및 링크 확인을 제공합니다. EOP(Exchange Online Protection)의 인바운드 전자 메일 메시지에서 일반 스팸 방지 및 맬웨어 방지 보호 기능 외에 안전한 링크 검색이 실행됩니다. [](anti-spam-and-anti-malware-protection.md) 안전한 링크 검색은 피싱 및 기타 공격에 사용되는 악의적인 링크로부터 조직을 보호하는 데 도움이 될 수 있습니다.

안전한 링크 보호는 다음 위치에서 사용할 수 있습니다.

- **전자 메일 메시지:** 전자 메일 메시지의 링크에 대한 안전한 링크 보호는 안전한 링크 정책에 의해 제어됩니다. 기본 안전 링크 정책은 없습니다. 따라서 전자 메일 메시지의 안전한 링크 보호를 위해 하나 이상의 안전한 링크 정책을 **만들어야 합니다.** 자세한 내용은 [Office 365용 Microsoft Defender에서 안전한](set-up-atp-safe-links-policies.md)링크 정책 설정을 참조하세요.

  전자 메일 메시지의 안전한 링크 보호에 [](#safe-links-settings-for-email-messages) 대한 자세한 내용은 이 문서 부분의 전자 메일 메시지에 대한 안전 링크 설정을 참조하세요.

- **Microsoft Teams(현재** TAP 미리 보기에서): Teams 대화, 그룹 채팅 또는 채널의 링크에 대한 안전한 링크 보호도 안전한 링크 정책에 의해 제어됩니다. 기본 안전 링크 정책은 없습니다. 따라서 Teams에서 안전한 링크 보호를 위해 하나 이상의 안전한 링크 정책을 **만들어야 합니다.**

  Teams의 안전한 링크 보호에 대한 자세한 내용은 이 문서 부분의 [Microsoft Teams에](#safe-links-settings-for-microsoft-teams) 대한 안전 링크 설정을 참조하세요.

- **Office 365 앱:** Office 365 앱에 대한 안전한 링크 보호는 지원되는 데스크톱, 모바일 및 웹 aps에서 사용할 수 있습니다. 안전 **링크** 정책 외부의 전역 설정에서 Office 365 앱에 대해 안전한 링크 보호를 구성합니다.  자세한 내용은 [Office 365용 Microsoft Defender에서](configure-global-settings-for-safe-links.md)안전한 링크 설정에 대한 전역 설정 구성을 참조하세요.

  그러나 Office 365 앱에 대한  안전한 링크 보호는 활성 안전 링크 정책에 포함된 사용자에게만 적용됩니다. 사용자가 활성 안전 링크 정책에 포함되지 않은 경우 사용자는 지원되는 Office 365 앱에서 안전 링크 보호를 받을 수 없습니다.

  Office 365 앱의 안전한 링크 보호에 대한 자세한 내용은 이 문서의 부분에 있는 [Office 365](#safe-links-settings-for-office-365-apps) 앱에 대한 안전 링크 설정을 참조하세요.

이 문서에는 다음과 같은 유형의 안전 링크 설정에 대한 자세한 설명이 포함되어 있습니다.

- **안전한 링크** 정책의 설정: 이러한 설정은 특정 정책에 포함된 사용자에게만 적용될 수 있으며 정책 간에 설정이 다를 수 있습니다. 이러한 설정은 다음과 같습니다.

  - [전자 메일 메시지에 대한 안전한 링크 설정](#safe-links-settings-for-email-messages)
  - [Microsoft Teams의 안전한 링크 설정](#safe-links-settings-for-microsoft-teams)
  - [안전한 링크 정책에서 "다음 URL을 다시 덮어치지 않습니다." 목록](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)

- **전역 안전 링크 설정:** 이러한 설정은 안전한 링크 정책이 아니라 전역으로 구성됩니다. 그러나 설정은 활성 안전 링크 정책에 포함된 사용자에게만 적용됩니다. 이러한 설정은 다음과 같습니다.

  - [Office 365 앱의 안전한 링크 설정](#safe-links-settings-for-office-365-apps)
  - [안전한 링크에 대해 "다음 URL 차단" 목록](#block-the-following-urls-list-for-safe-links)

다음 표에서는 Office 365용 Defender를 포함 하는 Microsoft 365 및 Office 365 조직의 안전 링크에 대 한 시나리오에 설명 합니다(즉, 라이선스 부족은 예에서 문제가 아닙니다).

****

|시나리오|결과|
|---|---|
|지민은 마케팅 부서의 구성원입니다. Office 365 앱에 대한 안전한 링크 보호는 안전한 링크에 대한 전역 설정에서 켜져 있으며 마케팅 부서의 구성원에게 적용되는 안전한 링크 정책이 존재합니다. 전자 메일 메시지에 PowerPoint 프레젠테이션이 열리면 프레젠테이션의 URL을 클릭합니다.|도장은 안전한 링크로 보호됩니다. <p> 보관은 안전한 링크 정책에 포함되어 있으며 Office 365 앱에 대한 안전한 링크 보호가 켜져 있습니다. <p> Office 365 앱에서 안전한 링크 보호를 위한 요구 사항에 대한 자세한 내용은 이 문서 부분의 [Office 365](#safe-links-settings-for-office-365-apps) 앱에 대한 안전 링크 설정을 참조하세요.|
|Chris의 Microsoft 365 E5 조직에는 안전한 링크 정책이 구성되어 없습니다. Chris는 최종적으로 클릭하는 악성 웹 사이트에 대한 URL이 포함된 외부 보낸 사람으로부터 전자 메일을 수신합니다.|Chris는 안전한 링크로 보호되지 않습니다. <p> 관리자는 인바운드 전자 메일 메시지에서 안전한 링크 보호를 받을 수 있도록 모든 사용자에 대해 하나 이상의 안전 링크 정책을 만들어야 합니다. Chris는 안전한 링크 보호를 위해 정책 조건에 포함되어야 합니다.|
|Pat의 조직에서는 관리자가 안전한 링크 정책을 만들지 않지만 Office 365 앱에 대한 안전한 링크 보호가 켜져 있습니다. Pat에서 Word 문서를 열고 파일의 URL을 클릭합니다.|Pat는 안전한 링크로 보호되지 않습니다. <p> Office 365 앱에 대한 안전한 링크 보호는 전역으로 설정되어 있습니다. 그러나 Pat는 활성 안전 링크 정책에 포함되지 않습니다. 따라서 보호를 적용할 수 없습니다.|
|이민호의 조직에서 안전한 링크에 대한 전역 설정의 다음 URL 차단 목록에서 `https://tailspintoys.com` 구성됩니다.  이민호를 포함하는 안전한 링크 정책이 이미 있습니다. 이민호는 URL이 포함된 전자 메일 메시지를 `https://tailspintoys.com/aboutus/trythispage` 수신합니다. 이민호는 URL을 클릭합니다.|이민호의 URL이 자동으로 차단될 수 있습니다. 이 설정은 목록의 URL 항목과 이진호가 사용한 전자 메일 클라이언트에 따라 다를 수 있습니다. 자세한 내용은 이 문서 부분의 안전 링크 섹션에 대한 ["다음 URL 차단"](#block-the-following-urls-list-for-safe-links) 목록을 참조하세요.|
|Jamie와 Julia는 둘 다 contoso.com. 오래 전에 관리자는 Jamie와 Julia 모두에 적용되는 안전 링크 정책을 구성했습니다. Jamie는 전자 메일에 악의적인 URL이 포함되어 있는 것을 알지 못하고 조지민 에게 전자 메일을 전송합니다.|조지민 의원에게  적용되는 안전한 링크 정책이 내부 받는 사람 간의 메시지에 적용하도록 구성된 경우 Julia는 안전한 링크로 보호됩니다. 자세한 내용은 이 [](#safe-links-settings-for-email-messages) 문서 부분의 전자 메일 메시지에 대한 안전한 링크 설정을 참조하세요.|

## <a name="safe-links-settings-for-email-messages"></a>전자 메일 메시지에 대한 안전한 링크 설정

안전한 링크는 들어오는 전자 메일에서 알려진 악성 하이퍼링크를 검색합니다. 검사된 URL은 다음 Microsoft 표준 URL prefix를 사용하여 다시 덮어 `https://nam01.safelinks.protection.outlook.com` 습니다. 링크를 다시 덮어 입력하면 잠재적으로 악의적인 콘텐츠가 분석됩니다.

안전한 링크에서 URL을 다시 덮어도 메시지가 내부 및 외부  받는 사람에게 수동으로 전달되거나 답장된 경우에도 URL이 다시 덮어지지 않습니다. 전달되거나 메시지에 해당되는 추가 링크는 다시 덮어지지 않습니다. 그러나 받은 편지함  규칙이나 SMTP 전달에 의해 자동 전달되는 경우 수신자가 안전한 링크로 보호되거나 이전 통신에서 이미 URL을 다시 써야만 최종 받는 사람을 위한 메시지에서 URL이 다시 써지지 않습니다.  

전자 메일 메시지에 적용되는 안전한 링크 정책의 설정은 다음 목록에 설명되어 있습니다.

- **메시지에서** 알 수 없는 악의적인 URL에 대한 작업을 선택합니다. 전자 메일 메시지에서 안전한 링크 검색을 사용 또는 사용하지 않도록 설정 권장되는 값은 **On입니다.** 이 설정을 켜면 다음 작업이 수행됩니다.

  - 안전 링크 검사는 Windows의 Outlook(C2R)에서 사용하도록 설정됩니다.
  - URL이 다시 덮어 들이고 사용자가 메시지에서 URL을 클릭할 때 안전한 링크 보호를 통해 라우팅됩니다.
  - 클릭하면 알려진 악성 URL 목록 및 "다음 URL 차단" 목록에 대해 URL이 [확인됩니다.](#block-the-following-urls-list-for-safe-links)
  - 유효한 신뢰도에 없는 URL은 백그라운드에서 비동기적으로 확인됩니다.

- **파일을** 지정하는 의심스러운 링크 및 링크에 대한 실시간 URL 검색을 적용합니다. 다운로드 가능한 콘텐츠를 지정하는 전자 메일 메시지의 링크를 포함하여 링크를 실시간으로 검색할 수 있습니다. 권장되는 값은 사용하도록 설정되어 있습니다.

  - **메시지를 배달하기 전에 URL 검색이 완료될 때까지 기다릴 수 있습니다.**

    - 사용: URL이 포함된 메시지는 검사가 완료될 때까지 보류됩니다. 메시지는 URL이 안전한 것으로 확인된 후에만 배달됩니다. 이 값은 권장 값입니다.
    - 사용 안 하세요: URL 검색을 완료할 수 없는 경우 메시지를 배달합니다.

- **조직 내에서** 보낸 전자 메일 메시지에 안전한 링크 적용: 동일한 Exchange Online 조직 내의 내부 보낸 사람 및 내부 받는 사람 간에 전송된 메시지에 대해 안전한 링크 검색을 사용 또는 사용하지 않도록 설정 권장되는 값은 사용하도록 설정되어 있습니다.

- **사용자 클릭 추적** 안 하세요. 전자 메일 메시지에서 클릭한 URL에 대한 안전한 링크 클릭 데이터를 저장하거나 저장하지 않도록 합니다. 권장 값은 이 설정을 선택하지 않은(사용자 클릭 추적)하는 것입니다.

  내부 보낸 사람과 내부 받는 사람 간에 전송된 전자 메일 메시지의 링크에 대한 URL 클릭 추적은 현재 지원되지 않습니다.

- **사용자가 원래 URL을 클릭할** 수 있도록 허용하지 않습니다. [](#warning-pages-from-safe-links) 사용자가 원래 URL에 대한 경고 페이지를 클릭할 수 있도록 허용하거나 차단합니다. 권장 값을 사용하도록 설정합니다.

- **다음 URL을** 다시 덮어치지 않습니다. URL을 그대로 떠날 수 있습니다. 검사할 필요가 없는 안전한 URL의 사용자 지정 목록을 보관합니다. 이 목록은 각 안전 링크 정책에 대해 고유합니다. 다음 URL 목록을  다시 덮어 두지 않는 목록에 대한 자세한 내용은 이 문서 부분의 안전 링크 정책 섹션에서 ["다음 URL을](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies) 다시 덮어치지 않습니다." 목록을 참조하십시오.

안전 링크 정책에 대한 표준 및 엄격한 정책 설정에 대한 권장 값에 대한 자세한 내용은 안전 링크 정책 설정을 [참조하세요.](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)

- **받는 사람 필터:** 정책을 적용하는 사람을 결정하는 받는 사람 조건 및 예외를 지정해야 합니다. 조건 및 예외에 대해 다음 속성을 사용할 수 있습니다.

  - **받는 사람이 다음과 같음**
  - **받는 사람 도메인**
  - **받는 사람이 다음의 구성원임**

  조건 또는 예외는 한 번만 사용할 수 있지만 조건 또는 예외에 여러 값이 포함될 수 있습니다. 동일한 조건의 여러 값이나 예외는 OR 논리를 사용합니다(예: _\<recipient1\>_ 혹은 _\<recipient2\>_). 다양한 조건이나 예외는 AND 논리를 사용합니다(예: _\<recipient1\>_ 및 _\<member of group 1\>_).

- **우선** 순위: 여러 정책을 만드는 경우 정책이 적용되는 순서를 지정할 수 있습니다. 두 정책의 우선순위는 동일 할 수 없으며, 첫 번째 정책이 적용된 후에는 정책 처리가 중지됩니다.

  우선순위 및 여러 정책을 평가하고 적용하는 방법에 대 한 자세한 내용은 전자 메일의 [전자 메일의 우선순위 및 보호](how-policies-and-protections-are-combined.md)를 참조하세요.

### <a name="how-safe-links-works-in-email-messages"></a>전자 메일 메시지에서 안전한 링크가 작동하는 방식

높은 수준에서 안전한 링크 보호가 전자 메일 메시지의 URL에서 작동하는 방식은 다음과 같습니다.

1. 모든 전자 메일은 메시지가 받는 사람의 사서함으로 배달되기 전에 IP(인터넷 프로토콜) 및 봉투 필터, 서명 기반 맬웨어 보호, 스팸 방지 및 맬웨어 방지 필터가 있는 EOP를 통과합니다.

2. 사용자가 사서함에서 메시지를 열고 메시지의 URL을 클릭합니다.

3. 안전한 링크는 웹 사이트를 열기 전에 URL을 즉시 확인합니다.

   - URL이 다음 URL  차단 목록에 포함되어 있는 경우 차단된 [URL 경고가](#blocked-url-warning) 열립니다.

   - URL이 악성으로 확인된 웹 사이트를 표시하면 [](#malicious-website-warning) 악성 웹 사이트 경고 페이지(또는 다른 경고 페이지)가 열립니다.

   - URL이 다운로드 가능한 파일을 지정하고 파일 설정을 지정하는 실시간 **URL** 적용 검색이 사용자에게 적용되는 정책에서 사용하도록 설정되어 있는 경우 다운로드 가능한 파일이 확인됩니다.

   - URL이 안전한 것으로 확인되면 웹 사이트가 열립니다.

## <a name="safe-links-settings-for-microsoft-teams"></a>Microsoft Teams의 안전한 링크 설정

> [!IMPORTANT]
> 2020년 3월 현재 이 기능은 미리 보기로 제공된 기능으로, TAP(Microsoft Teams Technology Adoption Program)의 구성원만 사용할 수 있습니다. 릴리스 일정에 대한 자세한 내용은 [Microsoft 365 로드맵을 참조하십시오.](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=&searchterms=Safe%2CLinks%2CProtection%2Cfor%2CMicrosoft%2CTeams)

안전한 링크 정책에서 Microsoft Teams에 대한 안전 링크 보호를 사용하도록 설정하거나 사용하지 않도록 설정할 수 있습니다. 특히 Microsoft Teams 설정 내에서 알 수 없는 URL이나 악의적인 **URL에** 대한 선택 작업을 사용할 수 있습니다. 권장되는 값은 **On입니다.**

전자 메일 메시지의 링크에 적용되는 안전한 링크 정책의 다음 설정은 Teams의 링크에도 적용됩니다.

- **파일을 지정하는 의심스러운 링크 및 링크에 대한 실시간 URL 검사 적용**
- **사용자 클릭 추적 안 하도록 설정**
- **사용자가 원래 URL을 클릭할 수 있도록 허용 안 하세요.**

이러한 설정은 전자 메일 메시지에 대한 이전 안전 링크 설정 [섹션에서 설명합니다.](#safe-links-settings-for-email-messages)

Microsoft Teams에 대해 안전한 링크 보호를 켜면 보호된 사용자가 링크를 클릭할 때 Teams의 URL이 알려진 악성 링크 목록에 대해 확인됩니다(클릭 시간 보호). URL은 다시 덮어지지 않습니다. 링크가 악성으로 확인된 경우 사용자는 다음과 같은 경험을 하게 됩니다.

- 링크가 Teams 대화, 그룹 채팅 또는 채널에서 클릭된 경우 아래 스크린샷에 표시된 경고 페이지가 기본 웹 브라우저에 표시됩니다.
- 고정된 탭에서 링크를 클릭한 경우 해당 탭 내의 Teams 인터페이스에 경고 페이지가 표시됩니다. 보안상의 이유로 웹 브라우저에서 링크를 여는 옵션을 사용할 수 없습니다.
- 사용자가 정책의 원래 URL 설정을 클릭할 수 있도록 허용하지 않는 방법에 따라 사용자는 원래 **URL(스크린샷에서** 권장되지 않음)을 클릭할 수 있는지 또는 클릭할 수 없습니다. 사용자가 원래 **URL을** 클릭할 수 있도록 사용자가 원래 URL 설정을 클릭하지 못하도록 허용하지 않는 것이 좋습니다.

링크를 보낸 사용자가 Teams 보호가 설정된 안전한 링크 정책에 포함되지 않은 경우 사용자는 컴퓨터 또는 장치의 원래 URL을 클릭할 수 있습니다.

![악의적인 링크를 보고하는 Teams의 안전한 링크입니다.](../../media/tp-safe-links-for-teams-malicious.png)

경고 페이지에서 **뒤로 이동** 단추를 클릭하면 사용자가 원래 컨텍스트 또는 URL 위치로 돌아갈 수 있습니다. 그러나 원래 링크를 다시 클릭하면 안전한 링크가 URL을 다시 검색할 수 있으므로 경고 페이지가 다시 나타납니다.

### <a name="how-safe-links-works-in-teams"></a>Teams에서 안전한 링크가 작동하는 방식

Microsoft Teams의 URL에 대해 안전한 링크 보호가 작동하는 방식은 다음과 같습니다.

1. 사용자가 Teams 앱을 시작합니다.

2. Microsoft 365는 사용자의 조직에 Office 365용 Microsoft Defender가 포함되어 있으며 Microsoft Teams에 대한 보호가 설정된 활성 안전 링크 정책에 해당 사용자가 포함되어 있는지 확인합니다.

3. 채팅, 그룹 채팅, 채널 및 탭에서 사용자를 클릭할 때 URL의 유효성이 검사됩니다.

## <a name="safe-links-settings-for-office-365-apps"></a>Office 365 앱의 안전한 링크 설정

Office 365 앱의 안전한 링크 보호는 전자 메일 메시지의 링크가 아닌 Office 문서의 링크를 검사합니다(문서가 열리면 전자 메일 메시지에 첨부된 Office 문서의 링크를 확인할 수 있습니다).

Office 365 앱의 안전한 링크 보호에는 다음과 같은 클라이언트 요구 사항이 있습니다.

- Microsoft 365 앱 또는 Microsoft 365 Business Premium
  - Windows, Mac 또는 웹 브라우저의 현재 버전의 Word, Excel 및 PowerPoint.
  - iOS 또는 Android 장치의 Office 앱.
  - Windows의 Visio.
  - 웹 브라우저의 OneNote.

- Office 365 앱은 최신 인증을 사용하도록 구성됩니다. 자세한 내용은 [Office 2013, Office 2016 및 Office 2019](../../enterprise/modern-auth-for-office-2013-and-2016.md)클라이언트 앱에 대해 최신 인증이 작동하는 방법을 참조하세요.

- 사용자가 자신의 직장 또는 학교 계정을 사용하여 로그인합니다. 자세한 내용은 [Office에 로그인을 참조하세요.](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426)

안전한 링크 정책이 아니라 안전한 링크에 대한 전역 설정에서 Office 365 앱에 대한 안전한 링크 보호를 구성합니다. 그러나 Office 365 앱에 대한 안전한 링크 보호를 적용하려면 Office 문서를 열고 링크를 클릭하는 사용자가 활성 안전 링크 정책에 포함되어야 합니다.

Office 365 앱에서 사용할 수 있는 안전한 링크 설정은 다음과 같습니다.

- **Office 365 응용 프로그램:** 지원되는 Office 365 앱에서 안전한 링크 검색을 활성화 또는 비활성화합니다. 기본값과 권장 값은 **On입니다.**

- **사용자가 안전한** 링크를 클릭하는 경우를 추적하지 않습니다. 데스크톱 버전 Word, Excel, PowerPoint 및 Visio에서 클릭한 URL에 대한 안전한 링크 클릭 데이터를 저장하거나 저장하지 않도록 합니다. 권장되는 값은 **Off입니다.** 즉, 사용자 클릭이 추적됩니다.

- **사용자가 원래 URL에** 대한 안전한 링크를 클릭할 수 있도록 허용하지 않습니다. 사용자가 데스크톱 버전 Word, Excel, PowerPoint 및 Visio에서 원래 URL에 대한 경고 페이지를 클릭하지 못하게 허용하거나 차단합니다. [](#warning-pages-from-safe-links) 기본값과 권장 값은 **On입니다.**

Office 365 앱에 대한 안전한 링크 설정을 구성하려면 Office 365 앱에 대한 안전한 링크 보호 [구성을 참조하세요.](configure-global-settings-for-safe-links.md#configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center)

표준 및 엄격 정책 설정의 권장 값에 대한 자세한 내용은 안전 링크에 대한 전역 설정을 [참조하세요.](recommended-settings-for-eop-and-office365-atp.md#global-settings-for-safe-links)

### <a name="how-safe-links-works-in-office-365-apps"></a>Office 365 앱에서 안전한 링크가 작동하는 방식

Office 365 앱에서 URL에 대해 안전한 링크 보호가 작동하는 방식은 다음과 같은 높은 수준에서 다를 수 있습니다. 지원되는 Office 365 앱은 이전 섹션에 설명되어 있습니다.

1. 사용자가 Microsoft 365 앱 또는 Microsoft 365 Business Premium을 포함하는 조직에서 직장 또는 학교 계정을 사용하여 로그인합니다.

2. 사용자가 지원되는 Office 앱에서 Office 문서를 열고 링크를 클릭합니다.

3. 안전한 링크는 대상 웹 사이트를 열기 전에 URL을 즉시 확인합니다.

   - 안전한 링크 검색(다음 URL 목록 **차단)을** 건너뛰는 목록에 URL이 포함되어 있는 경우 [차단된 URL](#blocked-url-warning) 경고 페이지가 열립니다.

   - URL이 악성으로 확인된 웹 사이트를 표시하면 [](#malicious-website-warning) 악성 웹 사이트 경고 페이지(또는 다른 경고 페이지)가 열립니다.

   - URL이 다운로드 가능한 파일을, 그리고 사용자에게 적용되는 안전한 링크 정책이 다운로드 가능한 콘텐츠에 대한 링크를 검색하도록 구성되어 있는 경우(의심스러운 링크 및 파일을 지정하는 링크를 위한 실시간 **URL** 검색 적용), 다운로드 가능한 파일이 확인됩니다.

   - URL이 안전한 것으로 간주되는 경우 사용자는 웹 사이트로 이동됩니다.

   - 안전한 링크 검색을 완료할 수 없는 경우 안전한 링크 보호가 트리거되지 않습니다. Office 데스크톱 클라이언트에서는 대상 웹 사이트로 이동하기 전에 사용자에게 경고가 표시됩니다.

> [!NOTE]
> 각 세션이 시작될 때 사용자에게 Office용 안전 링크가 설정되어 있는지 확인하는 데 몇 초 정도 걸릴 수 있습니다.

## <a name="block-the-following-urls-list-for-safe-links"></a>안전한 링크에 대해 "다음 URL 차단" 목록

다음 URL 차단 **목록은** 다음 위치에서 안전 링크 검색에 의해 항상 차단되는 링크를 정의합니다.

- 전자 메일 메시지입니다.
- Windows 및 Mac의 Office 365 앱에 있는 문서.
- iOS 및 Android용 Office의 문서.

활성 안전 링크 정책의 사용자가 지원되는 앱에서 차단된 링크를 클릭하면 차단된 URL 경고 [페이지로 이동됩니다.](#blocked-url-warning)

안전한 링크에 대한 전역 설정에서 URL 목록을 구성합니다. 자세한 내용은 ["다음 URL 차단" 목록](configure-global-settings-for-safe-links.md#configure-the-block-the-following-urls-list-in-the-security--compliance-center)구성을 참조하세요.

**참고:**

- 모든 곳에서 차단되는 URL의 진정한 범용 목록은 테넌트 [허용/차단 목록 관리를 참조하세요.](tenant-allow-block-list.md)

- 제한:
  - 최대 항목 수는 500개입니다.
  - 항목의 최대 길이는 128자입니다.
  - 모든 항목은 10,000자까지 입력할 수 있습니다.

- URL의 끝에 `/` 슬래시()를 포함하지 않습니다. 예를 들어 `https://www.contoso.com` 다음을 사용하지 `https://www.contoso.com/` 않습니다.

- 도메인 전용 URL(예: 또는 )은 도메인이 포함된 `contoso.com` `tailspintoys.com` 모든 URL을 차단합니다.

- 전체 도메인을 차단하지 않고 하위 도메인을 차단할 수 있습니다. 예를 들어 하위 도메인이 포함된 URL은 차단하지만 전체 도메인을 포함하는 `toys.contoso.com*` URL은 차단하지 `contoso.com` 않습니다.

- URL 항목당 와일드카드()를 `*` 세 개까지 포함할 수 있습니다.

### <a name="entry-syntax-for-the-block-the-following-urls-list"></a>"다음 URL 차단" 목록에 대한 항목 구문

다음 표에는 입력할 수 있는 값과 해당 결과가 설명되어 있습니다.

****

|값|결과|
|---|---|
|`contoso.com` <p> 또는 <p> `*contoso.com*`|도메인, 하위 도메인 및 경로를 차단합니다. 예를 들어 `https://www.contoso.com` `https://sub.contoso.com` `https://contoso.com/abc` 차단됩니다.|
|`https://contoso.com/a`|처럼 `https://contoso.com/a` 추가 하위 경로는 차단하지만 차단하지는 `https://contoso.com/a/b` 않습니다.|
|`https://contoso.com/a*`|처럼 `https://contoso.com/a` 블록 및 추가 하위 `https://contoso.com/a/b` 경로|
|`https://toys.contoso.com*`|하위 도메인(이 예의 경우)을 차단하지만 다른 도메인 URL(예: 또는 )을 클릭할 수 `toys` `https://contoso.com` `https://home.contoso.com` 있습니다.|
|

## <a name="do-not-rewrite-the-following-urls-lists-in-safe-links-policies"></a>안전한 링크 정책에서 "다음 URL을 다시 덮어치지 않습니다." 목록

> [!NOTE]
> 조직에서 안전한 링크 정책을  사용하는 경우 다음 URL 목록을 다시 기록하지 않는 것이 타사 피싱 테스트에 대해 지원되는 유일한 방법입니다.

각 안전 링크  정책에는 안전 링크 검색으로 다시 덮어지지 않는 URL을 지정하는 데 사용할 수 있는 다음 URL 목록을 다시 덮어 들이지 않습니다. 즉, 이 목록을 사용하면 정책에 포함된 사용자가 안전한 링크로 차단되는 지정된 URL에 액세스할 수 있습니다. 서로 다른 안전 링크 정책에서 서로 다른 목록을 구성할 수 있습니다. 정책 처리는 사용자에게 첫 번째(우선 순위가 가장 높은) 정책이 적용된 후 중지됩니다. 따라서 여러 활성 안전 링크 정책에 포함된 사용자에게는 다음 **URL** 목록을 다시 만들지 않습니다.

새 정책 또는 기존 안전 링크 정책의 [](set-up-atp-safe-links-policies.md#use-the-security--compliance-center-to-create-safe-links-policies) 목록에 항목을 추가하려면 안전 링크 정책 만들기 또는 안전 링크 수정 [정책을 참조하세요.](set-up-atp-safe-links-policies.md#use-the-security--compliance-center-to-modify-safe-links-policies)

**참고:**

- 다음 클라이언트는 안전 링크 정책에서 다음 **URL** 목록을 다시 덮어 들이지 못합니다. 이러한 클라이언트에서 안전한 링크 검색 결과를 기반으로 하여, 보안에 포함된 사용자는 URL에 액세스하지 않을 수 있습니다.

  - Microsoft Teams
  - Office Web Apps

  모든 곳에서 허용되는 진정한 범용 URL 목록은 테넌트 [허용/차단 목록 관리를 참조하세요.](tenant-allow-block-list.md)

- 사용자 환경을 개선하기 위해 일반적으로 사용되는 내부 URL을 목록에 추가하는 것이 있습니다. 예를 들어 비즈니스용 Skype 또는 SharePoint와 같은 프레미스 서비스가 있는 경우 해당 URL을 추가하여 검색에서 제외할 수 있습니다.

- 안전 링크 정책에서 다음 **URL** 항목을 이미 다시 작성하지 않은 경우 목록을 검토하고 필요한 경우 와일드카드를 추가해야 합니다. 예를 들어 목록에 다음과 같은 항목이 있으며 나중에 다음과 같은 하위 `https://contoso.com/a` 경로가 포함될 수 `https://contoso.com/a/b` 있습니다. 새 항목을 추가하는 대신 기존 항목에 와일드카드를 추가하면 와일드카드가 `https://contoso.com/a/*` 됩니다.

- URL 항목당 와일드카드()를 `*` 세 개까지 포함할 수 있습니다. 와일드카드에는 명시적으로 prefixes 또는 subdomains가 포함됩니다. 예를 들어 사용자가 지정된 도메인의 하위 도메인 및 경로를 방문할 수 있기 때문에 항목은 `contoso.com` `*.contoso.com/*` `*.contoso.com/*` 동일하지 않습니다.

### <a name="entry-syntax-for-the-do-not-rewrite-the-following-urls-list"></a>"다음 URL을 다시 덮어치지 않습니다." 목록에 대한 항목 구문

다음 표에는 입력할 수 있는 값과 해당 결과가 설명되어 있습니다.

****

|값|결과|
|---|---|
|`contoso.com`|하위omain 또는 경로에는 액세스할 수 있지만 액세스할 `https://contoso.com` 수 없습니다.|
|`*.contoso.com/*`|도메인, 하위 도메인 및 경로(예: , 또는 )에 대한 액세스를 `https://www.contoso.com` `https://www.contoso.com` `https://maps.contoso.com` `https://www.contoso.com/a` 허용합니다. <p> 이 항목은 다음 항목보다 본질적으로 더 좋습니다. 이러한 항목은 또는 `*contoso.com*` `https://www.falsecontoso.com``https://www.false.contoso.completelyfalse.com`|
|`https://contoso.com/a`|하위 경로에 대한 액세스를 허용하지만 하위 경로는 `https://contoso.com/a` 허용하지 않습니다. `https://contoso.com/a/b`|
|`https://contoso.com/a/*`|같은 하위 경로 `https://contoso.com/a` 및 액세스 허용 `https://contoso.com/a/b`|
|

## <a name="warning-pages-from-safe-links"></a>안전한 링크의 경고 페이지

이 섹션에는 URL을 클릭할 때 안전한 링크 보호에 의해 트리거되는 다양한 경고 페이지의 예가 포함되어 있습니다.

여러 경고 페이지가 업데이트되었습니다. 업데이트된 페이지가 아직 없는 경우 곧 업데이트됩니다. 업데이트된 페이지에는 새로운 색 구성표, 세부 정보 및 제공된 경고 및 권장 사항에도 불구하고 사이트로 진행할 수 있는 능력이 포함되어 있습니다.

### <a name="scan-in-progress-notification"></a>검사 진행 중 알림

클릭한 URL이 안전한 링크로 검색되고 있습니다. 링크를 다시 시도하기 전에 몇 분 정도 기다려야 할 수 있습니다.

!["링크가 검사 중입니다." 알림](../../media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png)

원래 알림 페이지는 다음과 같이 표시했습니다.

![원래 "링크가 검색되고 있습니다." 알림](../../media/04368763-763f-43d6-94a4-a48291d36893.png)

### <a name="suspicious-message-warning"></a>의심스러운 메시지 경고

클릭한 URL이 다른 의심스러운 메시지와 유사한 전자 메일 메시지에 있습니다. 사이트로 진행하기 전에 전자 메일 메시지를 다시 검사하는 것이 좋습니다.

!["의심스러운 메시지에서 링크를 클릭했습니다." 경고](../../media/33f57923-23e3-4b0f-838b-6ad589ba897b.png)

### <a name="phishing-attempt-warning"></a>피싱 시도 경고

클릭한 URL은 피싱 공격으로 식별된 전자 메일 메시지에 있습니다. 따라서 전자 메일 메시지의 모든 URL이 차단됩니다. 사이트로 진행하지 않는 것이 좋습니다.

!["링크가 피싱 메시지에서 클릭된 경우" 경고](../../media/6e544a28-0604-4821-aba6-d5a57bb917e5.png)

### <a name="malicious-website-warning"></a>악성 웹 사이트 경고

클릭한 URL은 악의적인 것으로 확인된 사이트를 지정합니다. 사이트로 진행하지 않는 것이 좋습니다.

!["이 웹 사이트는 악성으로 분류됩니다." 경고](../../media/058883c8-23f0-4672-9c1c-66b084796177.png)

원래 경고 페이지는 다음과 같이 표시했습니다.

![원래 "이 웹 사이트가 악성으로 분류" 경고](../../media/b9efda09-6dd8-46ef-82cb-56e4d538b8f5.png)

### <a name="blocked-url-warning"></a>차단된 URL 경고

클릭한 URL은 조직의 관리자가 수동으로 차단했습니다(안전한 링크에 대한 전역 설정의 다음 **URL** 차단 목록). 링크가 수동으로 차단된 것이기 때문에 안전한 링크에서 링크를 검색하지 못했습니다.

관리자가 특정 URL을 수동으로 차단하는 몇 가지 이유가 있습니다. 사이트가 차단되지 않을 것으로 생각되는 경우 관리자에게 문의하세요.

!["이 웹 사이트가 관리자가 차단했습니다." 경고](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

원래 경고 페이지는 다음과 같이 표시했습니다.

![원래 "이 웹 사이트가 조직의 URL 정책에 따라 차단했습니다." 경고](../../media/3d6ba028-30bf-45fc-958e-d3aad3defc83.png)

### <a name="error-warning"></a>오류 경고

일부 오류가 발생하여 URL을 열 수 없습니다.

!["액세스하려는 페이지를 로드할 수 없습니다." 경고](../../media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png)

원래 경고 페이지는 다음과 같이 표시했습니다.

![원래 "이 웹 페이지를 로드할 수 없습니다." 경고](../../media/9aaa4383-2f23-48be-bdaa-8efbcb2acc70.png)
