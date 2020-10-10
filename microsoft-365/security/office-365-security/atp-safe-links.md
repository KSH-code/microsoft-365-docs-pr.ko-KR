---
title: 안전한 링크
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.article: overview
f1_keywords:
- "197503"
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- m365-initiative-defender-office365
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
description: 이 문서에서는 관리자가 악성 Url을 사용 하는 피싱 및 기타 공격 으로부터 조직을 보호 하기 위해 Office 365 ATP (Advanced Threat Protection)의 안전한 링크 보호에 대해 알아볼 수 있습니다.
ms.openlocfilehash: c933ce48483f0263650d0af2994023dfcb24fadf
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/09/2020
ms.locfileid: "48414121"
---
# <a name="safe-links-in-office-365-atp"></a>Office 365 ATP의 안전한 링크

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> 이 문서는 [Office 365 ATP (Advanced Threat Protection)](office-365-atp.md)가 있는 비즈니스 고객을 위한 것입니다. Outlook.com, Microsoft 365 제품군 또는 Microsoft 365 Personal을 사용 하 고 있고 Outlook의 Safelinks에 대 한 정보를 찾으려는 경우 [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)를 참조 하세요.

안전한 링크는 메일 흐름에서 인바운드 전자 메일 메시지에 대 한 URL 검색 및 다시 쓰기를 제공 하 고 전자 메일 메시지와 기타 위치의 Url 및 링크에 대 한 클릭 하는 방법으로, [Office 365 Advanced Threat Protection](office-365-atp.md) 의 기능입니다. 안전한 링크 검색은 EOP (Exchange Online Protection)의 인바운드 전자 메일 메시지에 있는 일반 [스팸 방지 및 맬웨어 방지 보호 기능](anti-spam-and-anti-malware-protection.md) 외에도 발생 합니다. 안전한 링크 검색 기능은 피싱 및 기타 공격에 사용 되는 악의적인 링크 로부터 조직을 보호 하는 데 도움이 될 수 있습니다.

안전한 링크 보호는 다음 위치에서 사용할 수 있습니다.

- **전자 메일 메시지**: 전자 메일 메시지의 링크에 대 한 안전한 링크 보호는 안전한 링크 정책에 의해 제어 됩니다. 안전한 링크 정책 없이도 **전자 메일 메시지의 안전한 링크를 보호 하려면 하나 이상의 안전한 링크 정책을 만들어야**합니다. 자세한 내용은 [ATP에서 안전한 링크 정책 설정을](set-up-atp-safe-links-policies.md)참조 하십시오.

  전자 메일 메시지에 대 한 안전한 링크 보호에 대 한 자세한 내용은이 문서 뒷부분의 [전자 메일 메시지에 대 한 안전한 링크 설정](#safe-links-settings-for-email-messages) 섹션을 참조 하십시오.

- **Microsoft 팀** (현재 탭 미리 보기): 팀 대화, 그룹 채팅 또는 채널의 링크에 대 한 안전한 링크 보호도 안전한 링크 정책에 의해 제어 됩니다. 안전한 링크 정책이 없는 경우 **팀의 안전한 링크를 보호 하려면 하나 이상의 안전한 링크 정책을 만들어야**합니다.

  팀의 안전한 링크 보호에 대 한 자세한 내용은이 항목 뒷부분의 [Microsoft 팀에 대 한 안전한 링크 설정](#safe-links-settings-for-microsoft-teams) 섹션을 참조 하십시오.

- **Office 365 앱**: office 365 앱에 대 한 안전한 링크 보호는 지원 되는 데스크톱, 모바일 및 웹 ap에서 사용할 수 있습니다. 안전한 링크 정책을 **벗어나는** 전역 설정에서 Office 365 앱에 대 한 안전한 링크 보호를 **구성** 합니다. 자세한 내용은 [Office 365 ATP에서 안전한 링크 설정에 대 한 전역 설정 구성을](configure-global-settings-for-safe-links.md)참조 하십시오.

  그러나 Office 365 앱에 대 한 안전한 링크 보호는 활성 안전한 링크 정책에 포함 된 사용자 에게만 **적용** 됩니다. 활성 안전한 링크 정책에 사용자가 포함 되어 있지 않으면 사용자가 지원 되는 Office 365 앱에서 안전한 링크 보호를 받지 않습니다.

  Office 365 앱의 안전한 링크 보호에 대 한 자세한 내용은이 문서 뒷부분에 있는 [office 365 앱에 대 한 안전한 링크 설정](#safe-links-settings-for-office-365-apps) 섹션을 참조 하십시오.

이 문서에는 다음과 같은 유형의 안전한 링크 설정에 대 한 자세한 설명이 포함 되어 있습니다.

- **안전한 링크 정책의 설정**: 이러한 설정은 특정 정책에 포함 된 사용자 에게만 적용 되며 정책 간에는 설정이 다를 수 있습니다. 이러한 설정은 다음과 같습니다.

  - [전자 메일 메시지에 대 한 안전한 링크 설정](#safe-links-settings-for-email-messages)
  - [Microsoft 팀에 대 한 안전한 링크 설정](#safe-links-settings-for-microsoft-teams)
  - [안전한 링크 정책의 "다음 Url을 다시 쓰지 않음" 목록](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)

- **전역 안전 링크 설정**: 이러한 설정은 안전한 링크 정책이 아닌 전역적으로 구성 됩니다. 그러나이 설정은 활성 안전한 링크 정책에 포함 된 사용자 에게만 적용 됩니다. 이러한 설정은 다음과 같습니다.

  - [Office 365 앱에 대 한 안전한 링크 설정](#safe-links-settings-for-office-365-apps)
  - [안전한 링크에 대 한 "다음 Url 차단" 목록](#block-the-following-urls-list-for-safe-links)

다음 표에서는 ATP를 포함 하는 Microsoft 365 및 Office 365 조 직의 안전한 링크에 대 한 시나리오를 설명 합니다 (즉, 라이선스 부족은 해당 예에서 문제가 되지 않음).

****

|시나리오|결과|
|---|---|
|Jean은 마케팅 부서의 구성원입니다. 안전한 링크 보호 Office 365 앱은 안전한 링크에 대 한 전역 설정에 설정 되어 있으며, 마케팅 부서의 구성원에 게 적용 되는 안전한 링크 정책이 있습니다. Jean에서 PowerPoint 프레젠테이션을 전자 메일 메시지로 열고 프레젠테이션에서 URL을 클릭 합니다.|Jean는 안전한 링크로 보호 됩니다. <br/><br/> Jean는 안전한 링크 정책에 포함 되어 있으며 Office 365 앱에 대 한 안전한 링크 보호 기능이 설정 되어 있습니다. <br/><br/> Office 365 앱의 안전한 링크 보호 요구 사항에 대 한 자세한 내용은이 문서 뒷부분의 [office 365 apps에 대 한 안전한 링크 설정](#safe-links-settings-for-office-365-apps) 섹션을 참조 하십시오.|
|Chris의 Microsoft 365 E5 조직에는 구성 된 안전한 링크 정책이 없습니다. Chris는 궁극적으로 클릭 하는 악성 웹 사이트에 대 한 URL이 포함 된 외부 보낸 사람의 전자 메일을 받습니다.|Chris가 안전한 링크를 통해 보호 되지 않습니다. <br/><br/> 관리자는 인바운드 전자 메일 메시지에서 안전한 링크 보호를 가져올 수 있도록 모든 사용자에 대해 하나 이상의 안전한 링크 정책을 만들어야 합니다. 안전한 링크 보호를 얻으려면 정책 조건에 Chris가 포함 되어야 합니다.|
|Pat의 조직에서는 관리자가 안전한 링크 정책을 만들지 않았지만 Office 365 앱에 대 한 안전한 링크 보호가 설정 되어 있습니다. Word 문서를 열고 파일의 URL을 클릭 합니다.|Pat가 안전한 링크로 보호 되지 않습니다. <br/><br/> Office 365 앱에 대 한 안전한 링크 보호 기능은 전역적으로 켜져 있지만, Pat는 활성 안전한 링크 정책에 포함 되어 있지 않으므로 보호 기능을 적용할 수 없습니다.|
|Lee 조직의 조직에서 `https://tailspintoys.com` 안전한 링크에 대 한 전역 설정의 **다음 url 차단** 목록에 구성 되어 있습니다. Lee이 포함 된 안전한 링크 정책이 이미 있습니다. Lee에서 URL을 포함 하는 전자 메일 메시지를 받습니다 `https://tailspintoys.com/aboutus/trythispage` . Lee에서 URL을 클릭 합니다.|URL이 Lee에 대해 자동으로 차단 될 수 있습니다. 이는 목록의 URL 항목과 사용 되는 전자 메일 클라이언트 Lee에 따라 달라 집니다. 자세한 내용은이 항목 뒷부분에 나오는 ["다음 Url 차단" 안전한 링크에 대 한 목록](#block-the-following-urls-list-for-safe-links) 보기 섹션을 참조 하십시오.|
|Contoso.com에 대해 작업자와 줄리아가 모두 작동 합니다. 오랜 시간 전에 관리자가 구성한 안전한 링크 정책이 김 및 줄리아 모두에 적용 됩니다. 이 전자 메일에 악성 URL이 포함 되어 있다는 것을 모르는 경우에는 전자 메일이 줄리아로 전송 됩니다.|줄리아는 안전한 링크 정책이 내부 받는 사람 간의 메시지에 적용 되도록 구성 된 **경우** 안전 링크에 의해 보호 됩니다. 자세한 내용은이 항목 뒷부분에 나오는 [전자 메일 메시지에 대 한 안전한 링크 설정](#safe-links-settings-for-email-messages) 섹션을 참조 하십시오.|

## <a name="safe-links-settings-for-email-messages"></a>전자 메일 메시지에 대 한 안전한 링크 설정

안전한 링크는 들어오는 전자 메일에서 알려진 악성 하이퍼링크를 검사 합니다. 검사 된 Url은 Microsoft 표준 URL 접두사:을 사용 하 여 다시 쓰여집니다. `https://nam01.safelinks.protection.outlook.com` 링크를 다시 쓴 후에는 잠재적으로 악의적인 콘텐츠를 분석 합니다.

안전한 링크에서 URL을 다시 작성 한 후에는 메시지가 전달 되거나 회신 되는 경우에도 URL이 다시 기록 됩니다. 전달 되거나 회신 된 메시지에 추가 되는 추가 링크는 다시 쓰여지지 않습니다.

전자 메일 메시지에 적용 되는 안전 링크 정책의 설정은 다음 목록에 설명 되어 있습니다.

- **메시지에서 알 수 없는 잠재적 악성 url에 대 한 작업 선택**: 전자 메일 메시지에서 안전한 링크 검색을 사용 하거나 사용 하지 않도록 설정 합니다. 권장 값은 **On**입니다. 이 설정을 켜면 다음과 같은 동작이 발생 합니다.

  - Windows의 Outlook (C2R)에서 안전한 링크 검색이 사용 되도록 설정 됩니다.
  - Url이 다시 작성 되 고 사용자가 메시지의 Url을 클릭할 때 안전한 링크 보호를 통해 라우팅됩니다.
  - 이 단추를 클릭 하면 알려진 악성 Url 목록과 ["다음 Url 차단" 목록](#block-the-following-urls-list-for-safe-links)에 대해 url을 확인 합니다.
  - 유효한 신뢰도가 없는 Url은 백그라운드에서 비동기적으로 열.

- **의심 스러운 링크 및 파일을 가리키는 링크에 대해 실시간 URL 검사 적용**: 다운로드 가능한 콘텐츠를 가리키는 전자 메일 메시지의 링크를 비롯 한 실시간 링크 검색을 사용 하도록 설정 합니다. 권장 값은 사용 하도록 설정 되어 있습니다.

  - **메시지를 배달 하기 전에 URL 검색이 완료 될 때까지 기다립니다**.

    - Enabled: 검색이 완료 될 때까지 Url이 포함 된 메시지가 저장 됩니다. 메시지는 Url이 안전한 것으로 확인 된 후에만 배달 됩니다. 권장 값은 다음과 같습니다.
    - 사용 안 함: URL 검색을 완료할 수 없는 경우 메시지를 배달 합니다.

- **조직 내에서 전송 되는 전자 메일 메시지에 안전한 링크 적용**: 같은 Exchange Online 조직 내에서 내부 보낸 사람과 내부 받는 사람 간에 전송 되는 메시지에 대해 안전한 링크 검색을 사용 하거나 사용 하지 않도록 설정 합니다. 권장 값은 사용 하도록 설정 되어 있습니다.

- **사용자 클릭 추적 안 함**: 안전한 링크 저장을 사용 하거나 사용 하지 않도록 설정 전자 메일 메시지에서 클릭 한 url의 데이터를 클릭 합니다. 권장 값은 사용자 클릭을 추적 하기 위해이 설정을 선택 하지 않은 채로 두는 것입니다.

  URL 내부 보낸 사람과 내부 받는 사람 간에 전송 되는 전자 메일 메시지의 링크를 클릭 하는 것은 현재 지원 되지 않습니다.

- **사용자가 원래 url로 클릭 하도록 허용 안 함**: 사용자가 [경고 페이지](#warning-pages-from-safe-links) 를 통해 원래 url을 클릭 하지 못하도록 차단 합니다. 권장 값은 사용 하도록 설정 되어 있습니다.

- Url은 그대로 유지 **하 고 다음 url은 다시 쓰지**않습니다. 검색 하지 않아도 되는 안전한 Url의 사용자 지정 목록을 보관 합니다. 이 목록은 각 안전한 링크 정책에 대해 고유 합니다. **다음 url에 다시 쓰지** 않음 목록에 대 한 자세한 내용은이 문서 뒷부분의 ["안전한 링크 정책에서 다음 url을 다시 쓰지 않음"](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies) 항목을 참조 하십시오.

안전한 링크 정책의 표준 및 엄격한 정책 설정에 대 한 권장 값에 대 한 자세한 내용은 [안전한 링크 정책 설정을](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)참조 하십시오.

- **받는 사람 필터**: 정책을 적용할 사람을 결정 하는 예외 및 받는 사람 조건을 지정 해야 합니다. 다음 속성을 사용 하 여 조건 및 예외를 확인할 수 있습니다.

  - **받는 사람이 다음과 같음**
  - **받는 사람 도메인**
  - **받는 사람이 다음의 구성원임**

  조건 또는 예외는 한 번만 사용할 수 있지만 조건 또는 예외에 여러 값이 포함 될 수 있습니다. 동일한 조건의 여러 값이나 예외는 OR 논리를 사용합니다(예: _\<recipient1\>_ 혹은 _\<recipient2\>_). 다양한 조건이나 예외는 AND 논리를 사용합니다(예: _\<recipient1\>_ 및 _\<member of group 1\>_).

- **우선 순위**: 여러 정책을 만드는 경우 적용 되는 순서를 지정할 수 있습니다. 두 정책의 우선순위는 동일 할 수 없으며, 첫 번째 정책이 적용된 후에는 정책 처리가 중지됩니다.

  우선순위 및 여러 정책을 평가하고 적용하는 방법에 대 한 자세한 내용은 전자 메일의 [전자 메일의 우선순위 및 보호](how-policies-and-protections-are-combined.md)를 참조하세요.

### <a name="how-safe-links-works-in-email-messages"></a>전자 메일 메시지에서 안전한 링크가 작동 하는 방법

다음은 전자 메일 메시지의 Url에 대 한 안전한 링크 보호 작동 수준입니다.

1. 모든 전자 메일은 메시지가 받는 사람의 사서함으로 배달 되기 전에 IP (인터넷 프로토콜) 및 봉투 필터, 서명 기반 맬웨어 방지, 스팸 방지 및 맬웨어 방지 필터를 제공 하는 EOP를 통해 진행 됩니다.

2. 사용자가 사서함에서 메시지를 열고 메시지의 URL을 클릭 합니다.

3. 안전한 링크는 웹 사이트를 열기 전에 즉시 URL을 확인 합니다.

   - URL이 **다음 Url 차단** 목록에 포함 되어 있는 경우 [차단 된 url 경고가](#blocked-url-warning) 열립니다.

   - URL이 악의적인 것으로 확인 된 웹 사이트를 가리키는 경우 [악의 있는 웹 사이트 경고](#malicious-website-warning) 페이지 (또는 다른 경고 페이지)가 열립니다.

   - URL이 다운로드 가능한 파일을 가리키며 해당 **링크에 대해 실시간 URL 검색 및 파일을 가리키는 링크** 를 사용자에 게 적용 되는 정책에서 사용 하도록 설정 된 경우 다운로드 가능한 파일이 검사 됩니다.

   - URL이 안전한 것으로 확인 되 면 웹 사이트가 열립니다.

## <a name="safe-links-settings-for-microsoft-teams"></a>Microsoft 팀에 대 한 안전한 링크 설정

> [!IMPORTANT]
> 3 월 2020 현재까지이 기능은 미리 보기 상태 이며 Microsoft 팀 기술 채택 프로그램의 구성원만 사용할 수 있습니다 (탭).

안전한 링크 정책에서 Microsoft 팀에 대 한 안전한 링크 보호를 사용 하거나 사용 하지 않도록 설정 합니다. 특히 **Microsoft 팀 내에서 알 수 없거나 악성 url에 대 한 작업 선택** 설정을 사용 합니다. 권장 값은 **On**입니다.

전자 메일 메시지의 링크에 적용 되는 안전한 링크 정책에서 팀의 링크에도 적용 되는 다음 설정은 다음과 같습니다.

- **의심 스러운 링크에 대 한 실시간 URL 검사 및 파일을 가리키는 링크를 적용 합니다.**
- **사용자 클릭 추적 안 함**
- **사용자가 원래 URL로 클릭 하도록 허용 안 함**

이러한 설정은 [전자 메일 메시지에 대 한 이전 안전한 링크 설정](#safe-links-settings-for-email-messages) 섹션에 설명 되어 있습니다.

Microsoft 팀에 대 한 안전한 링크 보호를 설정한 후에는 보호 된 사용자가 링크를 클릭할 때 알려진 악성 링크 목록 (팀의 Url)이 확인 됩니다 (클릭 시간 보호). Url은 다시 작성 되지 않습니다. 링크가 악성 인 경우 사용자는 다음과 같은 환경을 사용할 수 있습니다.

- 팀 대화, 그룹 채팅 또는 채널에서 링크를 클릭 한 경우 아래 스크린샷에 표시 된 경고 페이지가 기본 웹 브라우저에 표시 됩니다.
- 고정 된 탭에서 링크를 클릭 한 경우에는 해당 탭 내의 팀 인터페이스에 경고 페이지가 표시 됩니다. 보안상의 이유로 링크를 웹 브라우저에서 여는 옵션은 사용 하지 않도록 설정 되어 있습니다.
- **사용자가 정책의 원래 url을 클릭** 하는 것을 허용 하지 않음 설정이 구성 된 방법에 따라 사용자는 원래 url (스크린샷에서는**계속 됨)** 을 클릭할 수 있습니다. 사용자가 원래 url로 이동할 수 없도록 **하려면 사용자가 원래 url로 클릭 하도록 허용 안 함** 설정을 사용 하도록 설정 하는 것이 좋습니다.

링크를 보낸 사용자가 팀 보호를 사용할 수 있는 안전한 링크 정책에 포함 되어 있지 않은 경우 사용자는 자신의 컴퓨터나 장치에서 원래 URL로 이동할 수 있습니다.

![악성 링크를 보고 하는 팀에 대 한 안전한 링크 페이지입니다.](../../media/tp-safe-links-for-teams-malicious.png)

경고 페이지에서 **뒤로 이동** 단추를 클릭 하면 페이지가 닫히고 사용자가 닫을 수 있는 빈 페이지가 표시 될 수 있습니다. 그러나 원래 링크를 다시 클릭 하면 안전 링크를 통해 URL이 검사 되므로 경고 페이지가 나타납니다.

### <a name="how-safe-links-works-in-teams"></a>팀에서의 안전한 링크 작동 방식

다음은 Microsoft 팀의 Url에 대 한 안전한 링크 보호 작동 수준입니다.

1. 사용자가 팀 앱을 시작 합니다.

2. Microsoft 365에서는 사용자의 조직에 Office 365 ATP가 포함 되어 있고 사용자가 Microsoft 팀에 대 한 보호가 사용 하도록 설정 된 활성 안전한 링크 정책에 포함 되어 있는지 확인 합니다.

3. Url은 대화방, 그룹 채팅, 채널 및 탭에서 사용자를 클릭 하는 시점에 유효성을 검사 합니다.

## <a name="safe-links-settings-for-office-365-apps"></a>Office 365 앱에 대 한 안전한 링크 설정

안전한 링크 보호 Office 365 앱은 전자 메일 메시지의 링크가 아니라 Office 문서의 링크를 확인 하지만 문서를 연 후 전자 메일 메시지에서 첨부 된 Office 문서의 링크를 확인할 수 있습니다.

Office 365 앱에 대 한 안전한 링크 보호는 다음과 같은 클라이언트 요구 사항을 충족 합니다.

- Microsoft 365 앱 또는 Microsoft 365 Business Premium
  - Windows, Mac 또는 웹 브라우저에서 현재 버전의 Word, Excel 및 PowerPoint입니다.
  - IOS 또는 Android 장치에 대 한 Office 앱
  - Windows의 Visio
  - 웹 브라우저의 OneNote

- Office 365 앱은 최신 인증을 사용 하도록 구성 됩니다. 자세한 내용은 [office 2013, office 2016 및 office 2019 클라이언트 앱에 대 한 최신 인증이 작동 하는 방법을](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016)참조 하세요.

- 사용자가 회사 또는 학교 계정을 사용 하 여 로그인 되어 있습니다. 자세한 내용은 [Office에 로그인](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426)를 참조 하세요.

안전한 링크 정책이 아닌 안전한 링크에 대 한 전역 설정에서 Office 365 앱에 대 한 안전한 링크 보호를 구성 합니다. 그러나 Office 365 앱에 대 한 안전한 링크 보호를 적용 하려면 Office 문서를 열고 링크를 클릭 하는 사용자가 활성 안전한 링크 정책에 포함 되어 있어야 합니다.

Office 365 앱에 대해 다음과 같은 안전한 링크 설정을 사용할 수 있습니다.

- **Office 365 응용 프로그램**: 지원 되는 Office 365 앱에서 안전한 링크 검색을 사용 하거나 사용 하지 않도록 설정 합니다. 기본값 및 권장 값이 **설정**되어 있습니다.

- **사용자가 안전한 링크를 클릭 하는 경우를 추적 하지 않음**: 안전한 링크 저장 사용 또는 사용 안 함 데스크톱 버전 Word, Excel, PowerPoint 및 Visio에서 클릭 한 url의 데이터를 클릭 합니다. 권장 값은 **Off**이며, 사용자 클릭이 추적 됨을 의미 합니다.

- **사용자가 원본 url에 대 한 안전한 링크를 클릭**하는 것을 허용 하지 않음: 사용자가 데스크톱 버전 Word, Excel, PowerPoint 및 Visio의 원래 url로 [경고 페이지](#warning-pages-from-safe-links) 를 클릭 하는 것을 허용 하거나 차단 합니다. 기본값 및 권장 값이 **설정**되어 있습니다.

Office 365 앱에 대 한 안전한 링크 설정을 구성 하려면 [office 365 앱에 대 한 안전한 링크 보호 구성](configure-global-settings-for-safe-links.md#configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center)를 참조 하세요.

표준 및 엄격한 정책 설정에 대 한 권장 값에 대 한 자세한 내용은 [안전한 링크에 대 한 전역 설정을](recommended-settings-for-eop-and-office365-atp.md#global-settings-for-safe-links)참조 하십시오.

### <a name="how-safe-links-works-in-office-365-apps"></a>Office 365 앱에서 안전한 링크가 작동 하는 방식

다음은 Office 365 앱의 Url에 대 한 안전한 링크 보호 작동 수준입니다. 지원 되는 Office 365 앱은 이전 섹션에 설명 되어 있습니다.

1. 사용자는 Microsoft 365 앱 또는 Microsoft 365 Business Premium이 포함 된 조직의 회사 또는 학교 계정을 사용 하 여 로그인 합니다.

2. 사용자가 지원 되는 Office 앱에서 Office 문서 링크를 열고 클릭 합니다.

3. 안전한 링크는 대상 웹 사이트를 열기 전에 즉시 URL을 확인 합니다.

   - 안전한 링크 검색을 건너뛰는 목록에 URL이 포함 되어 있는 경우 ( **다음 url 목록 차단** ) [차단 된 url 경고](#blocked-url-warning) 페이지가 열립니다.

   - URL이 악의적인 것으로 확인 된 웹 사이트를 가리키는 경우 [악의 있는 웹 사이트 경고](#malicious-website-warning) 페이지 (또는 다른 경고 페이지)가 열립니다.

   - URL이 다운로드 가능한 파일을 가리키고 사용자에 게 적용 되는 안전 링크 정책이 다운로드 가능한 콘텐츠에 대 한 링크를 검색 하도록 구성 된 경우 (**의심 스러운 링크 및 파일을 가리키는 링크에 대해 실시간 URL 검색 적용**) 다운로드 가능한 파일이 검사 됩니다.

   - URL이 안전한 것으로 간주 되 면 사용자는 웹 사이트로 이동 됩니다.

   - 안전한 링크 검색을 완료할 수 없는 경우 안전한 링크 보호가 트리거되지 않습니다. Office 데스크톱 클라이언트에서는 대상 웹 사이트로 진행 하기 전에 사용자에 게 경고가 표시 됩니다.

> [!NOTE]
> 각 세션이 시작 되는 동안 사용자가 Office에 대 한 안전한 링크를 사용 하도록 설정 되어 있는지 확인 하는 데 몇 초 정도 걸릴 수 있습니다.

## <a name="block-the-following-urls-list-for-safe-links"></a>안전한 링크에 대 한 "다음 Url 차단" 목록

**다음 Url 차단** 목록에서는 다음 위치에 있는 안전한 링크 검색에서 항상 차단 되는 링크를 정의 합니다.

- 전자 메일 메시지
- Windows 및 Mac의 Office 365 앱에 있는 문서입니다.
- IOS 및 Android 용 Office의 문서입니다.

활성 안전한 링크 정책의 사용자가 지원 되는 앱에서 차단 된 링크를 클릭 하면 [차단 된 URL 경고](#blocked-url-warning) 페이지로 이동 합니다.

안전한 링크에 대 한 전역 설정에서 Url 목록을 구성 합니다. 자세한 내용은 Configure the ["다음 Url 차단" 목록을](configure-global-settings-for-safe-links.md#configure-the-block-the-following-urls-list-in-the-security--compliance-center)참조 하세요.

**참고**:

- 모든 범위에서 차단 되는 Url의 진정한 범용 목록은 [테 넌 트 허용/차단 목록에서 Url 관리](tenant-allow-block-list.md)를 참조 하십시오.

- 크기
  - 최대 항목 수는 500입니다.
  - 항목의 최대 길이는 128 자입니다.
  - 모든 항목은 1만 자를 초과할 수 없습니다.

- URL의 끝에 슬래시 ()를 포함 하지 마십시오 `/` . 예를 들어 `https://www.contoso.com` ,를 사용 `https://www.contoso.com/` 합니다.

- 도메인 전용-URL (예: `contoso.com` 또는 `tailspintoys.com` )은 도메인을 포함 하는 모든 url을 차단 합니다.

- 전체 도메인을 차단 하지 않고 하위 도메인을 차단할 수 있습니다. 예를 `toys.contoso.com*` 들어 하위 도메인이 포함 된 모든 url을 차단 하지만 전체 도메인을 포함 하는 url은 차단 되지 않습니다 `contoso.com` .

- URL 항목당 최대 3 개의 와일드 카드 ()를 포함할 수 있습니다 `*` .

### <a name="entry-syntax-for-the-block-the-following-urls-list"></a>"다음 Url 차단" 목록의 항목 구문

입력할 수 있는 값과 결과에 대 한 예는 다음 표에 설명 되어 있습니다.

****

|값|결과|
|---|---|
|`contoso.com` <br/> 또는 <br/> `*contoso.com*`|Domain, 하위 도메인 및 경로를 차단 합니다. 예를 들어 `https://www.contoso.com` `https://sub.contoso.com` and `https://contoso.com/abc` 는 차단 됩니다.|
|`https://contoso.com/a`|블록 `https://contoso.com/a` 이지만 추가 하위 경로는 `https://contoso.com/a/b` 아닙니다.|
|`https://contoso.com/a*`|블록과 `https://contoso.com/a` 추가 하위 경로를 선택 `https://contoso.com/a/b` 합니다.|
|`https://toys.contoso.com*`|하위 도메인 ( `toys` 이 예에서)을 차단 하지만 클릭이 다른 도메인 url (예: `https://contoso.com` 또는 `https://home.contoso.com` )을 허용 합니다.|
|

## <a name="do-not-rewrite-the-following-urls-lists-in-safe-links-policies"></a>안전한 링크 정책의 "다음 Url을 다시 쓰지 않음" 목록

> [!NOTE]
> 조직에서 안전한 링크 정책을 사용 하는 경우 타사 피싱 테스트 **에서는 다음 url** 목록만 지원 됩니다.

각 안전 링크 정책에는 안전한 링크 검색을 통해 다시 쓰지 않는 Url을 지정 하는 데 사용할 수 있는 **다음 url** 목록이 포함 되어 있습니다. 즉,이 목록을 사용 하면 정책에 포함 된 사용자가 안전한 링크에 의해 차단 되는 지정 된 Url에 액세스할 수 있습니다. 서로 다른 안전한 링크 정책에서 서로 다른 목록을 구성할 수 있습니다. 사용자에 게 첫 번째 (우선 순위가 가장 높은) 정책이 적용 된 후에는 정책 처리가 중지 됩니다. 따라서 여러 활성 안전한 링크 정책에 포함 된 사용자에 게는 **다음 url 목록을 다시 쓰지** 않습니다.

새 또는 기존 안전한 링크 정책에서 목록에 항목을 추가 하려면 [안전한 링크 정책 만들기](set-up-atp-safe-links-policies.md#use-the-security--compliance-center-to-create-safe-links-policies) 또는 [안전한 링크 정책 수정을](set-up-atp-safe-links-policies.md#use-the-security--compliance-center-to-modify-safe-links-policies)참조 하십시오.

**참고**:

- 다음 클라이언트는 안전한 링크 정책에서 **다음 url 목록을 다시 쓰지 않습니다** .를 인식 하지 못합니다. 정책에 포함 된 사용자는 다음 클라이언트에서 안전한 링크 검색 결과에 따라 Url에 액세스 하지 못하도록 차단할 수 있습니다.

  - Microsoft Teams
  - Office web apps

  모든 위치에서 허용 되는 진정한 범용 Url 목록은 [테 넌 트 허용/차단 목록에서 Url 관리](tenant-allow-block-list.md)를 참조 하십시오.

- 일반적으로 사용 되는 내부 Url을 목록에 추가 하 여 사용자 환경을 개선 하는 것이 좋습니다. 예를 들어 비즈니스용 Skype 또는 SharePoint와 같은 온-프레미스 서비스를 사용 하는 경우 해당 Url을 추가 하 여 검색에서 제외할 수 있습니다.

- 안전한 링크 정책에서 **다음 url 항목을 이미 다시 작성 하지** 않은 경우에는 목록을 검토 하 고 필요에 따라 와일드 카드를 추가 해야 합니다. 예를 들어 목록에 항목이 있고 `https://contoso.com/a` 나중에 하위 경로를 포함 하기로 결정 하는 경우를 예로 들 수 있습니다 `https://contoso.com/a/b` . 새 항목을 추가 하는 대신 기존 항목에 와일드 카드를 추가 하 여 해당 항목이 되도록 `https://contoso.com/a/*` 합니다.

- URL 항목당 최대 3 개의 와일드 카드 ()를 포함할 수 있습니다 `*` . 와일드 카드에 접두사 또는 하위 도메인이 명시적으로 포함 됩니다. 예를 들어 항목은 `contoso.com` `*.contoso.com/*` `*.contoso.com/*` 지정 된 도메인의 하위 도메인과 경로를 방문 하도록 허용 하므로와는 다릅니다.

### <a name="entry-syntax-for-the-do-not-rewrite-the-following-urls-list"></a>"다음 Url을 다시 쓰지 않음" 목록의 항목 구문

입력할 수 있는 값과 결과에 대 한 예는 다음 표에 설명 되어 있습니다.

****

|값|결과|
|---|---|
|`contoso.com`|하위 `https://contoso.com` 도메인 이나 경로가 아닌 액세스를 허용 합니다.|
|`*.contoso.com/*`|도메인, 하위 도메인 및 경로 (예:,, 또는)에 대 한 액세스를 허용 `https://www.contoso.com` `https://www.contoso.com` `https://maps.contoso.com` `https://www.contoso.com/a` 합니다. <br/><br/> 이 항목은 `*contoso.com*` 다음과 같이 잠재적으로 사기성 사이트를 허용 하지 않기 때문에 보다 안전 합니다. `https://www.falsecontoso.com``https://www.false.contoso.completelyfalse.com`|
|`https://contoso.com/a`|경로 액세스를 허용 `https://contoso.com/a` 하지만 `https://contoso.com/a/b`|
|`https://contoso.com/a/*`|같은 액세스 및 하위 경로를 사용할 수 있습니다. `https://contoso.com/a``https://contoso.com/a/b`|
|

## <a name="warning-pages-from-safe-links"></a>안전한 링크의 경고 페이지

이 섹션에는 URL을 클릭 했을 때 안전한 링크 보호에 의해 트리거되는 다양 한 경고 페이지 예제가 포함 되어 있습니다.

여러 개의 경고 페이지가 업데이트 되었습니다. 업데이트 된 페이지가 표시 되지 않으면 곧 제공 될 예정입니다. 업데이트 된 페이지에는 지정 된 경고 및 권장 사항에도 불구 하 고 사이트를 계속 진행 하는 기능 및 새로운 색 구성표가 포함 되어 있습니다.

### <a name="scan-in-progress-notification"></a>검색 진행 중 알림

클릭 한 URL을 안전한 링크에서 검색 하 고 있습니다. 잠시 기다린 후에 링크를 다시 시도해 야 할 수 있습니다.

!["링크를 검색 하 고 있습니다." 알림](../../media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png)

원래 알림 페이지는 다음과 같습니다.

![원본 "링크를 검색 하 고 있습니다." 알림](../../media/04368763-763f-43d6-94a4-a48291d36893.png)

### <a name="suspicious-message-warning"></a>의심 스러운 메시지 경고

클릭 한 URL이 다른 의심 스러운 메시지와 비슷한 전자 메일 메시지에 있습니다. 사이트를 진행 하기 전에 전자 메일 메시지를 두 번 확인 하는 것이 좋습니다.

!["의심 스러운 메시지에서 링크를 클릭 했습니다." 경고](../../media/33f57923-23e3-4b0f-838b-6ad589ba897b.png)

### <a name="phishing-attempt-warning"></a>피싱 시도 경고

클릭 한 URL이 피싱 공격으로 식별 된 전자 메일 메시지에 있습니다. 따라서 전자 메일 메시지의 모든 Url이 차단 됩니다. 해당 사이트로 이동 하지 않는 것이 좋습니다.

!["피싱 메시지에서 링크 클릭 됨" 경고](../../media/6e544a28-0604-4821-aba6-d5a57bb917e5.png)

### <a name="malicious-website-warning"></a>악의적인 웹 사이트 경고

클릭 한 URL이 악성으로 식별 된 사이트를 가리킵니다. 해당 사이트로 이동 하지 않는 것이 좋습니다.

!["이 웹 사이트가 악성으로 분류 되어 있습니다." 경고](../../media/058883c8-23f0-4672-9c1c-66b084796177.png)

원래 경고 페이지는 다음과 같이 표시 됩니다.

![원본 "이 웹 사이트가 악의적인 것으로 분류 됨" 경고](../../media/b9efda09-6dd8-46ef-82cb-56e4d538b8f5.png)

### <a name="blocked-url-warning"></a>차단 된 URL 경고

조직의 관리자가 클릭 한 URL을 수동으로 차단 했습니다 (안전한 링크에 대 한 전역 설정에서 **다음 url 목록 차단** ). 링크가 수동으로 차단 되었기 때문에 안전한 링크에서 검색 되지 않았습니다.

관리자가 특정 Url을 수동으로 차단 하는 이유에는 여러 가지가 있습니다. 사이트를 차단 하지 않을 것으로 생각 되 면 관리자에 게 문의 하세요.

!["이 웹 사이트가 관리자에 의해 차단 되었습니다." 경고](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

원래 경고 페이지는 다음과 같이 표시 됩니다.

![원본 "이 웹 사이트가 조직의 URL 정책에 따라 차단 되었습니다." 경고](../../media/3d6ba028-30bf-45fc-958e-d3aad3defc83.png)

### <a name="error-warning"></a>오류 경고

오류가 발생 하 여 URL을 열 수 없습니다.

!["액세스 하려는 페이지를 로드할 수 없습니다." 경고](../../media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png)

원래 경고 페이지는 다음과 같이 표시 됩니다.

![원본 "이 웹 페이지를 로드할 수 없습니다." 경고](../../media/9aaa4383-2f23-48be-bdaa-8efbcb2acc70.png)
