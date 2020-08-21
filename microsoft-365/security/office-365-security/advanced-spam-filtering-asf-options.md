---
title: EOP의 ASF 설정
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
search.appverid:
- MET150
ms.assetid: b286f853-b484-4af0-b01f-281fffd85e7a
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 관리자는 EOP(Exchange Online Protection)의 스팸 방지 정책에서 사용할 수 있는 ASF(고급 스팸 필터) 설정을 참조할 수 있습니다.
ms.openlocfilehash: 2a79a6721a587e3033e71e6e46856a21cffe7bcc
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827340"
---
# <a name="advanced-spam-filter-asf-settings-in-eop"></a>EOP의 ASF(고급 스팸 필터) 설정

> [!NOTE]
> 현재 스팸 방지 정책에서 사용할 수 있는 ASF 설정은 더 이상 사용되지 않습니다. 이러한 설정은 스팸 방지 정책에서 사용하지 않는 것이 좋습니다. 이러한 ASF 설정의 기능은 필터링 스택의 다른 부분에 통합됩니다. 자세한 내용은 EOP 스팸 [방지 정책 설정을 참조하세요.](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서는 관리자가 해당 메시지 속성에 기반하여 스팸 으로 메시지를 표시하도록 할 수 있습니다. ASF는 일반적으로 스팸에서 발견되므로 이러한 속성을 특별히 대상으로 지정합니다. 속성에 따라 ASF 검색에서는 메시지를 스팸 **또는** 높은 **신뢰 수준스팸으로 표시합니다.**

> [!NOTE]
> 하나 이상의 ASF 설정을 사용하는 것은 적합한 스팸 필터링 방법입니다. ASF에서 필터링한 메시지는 가양성으로 보고할 수 없습니다. 다음을 통해 ASF에 의해 필터링된 메시지를 식별할 수 있습니다.
>
> - 정기 최종 사용자 스팸 격리 알림.
>
> - 격리된 필터링된 메시지가 있는 상태입니다.
>
> - 이 항목에 `X-CustomSpam:` 설명된 바와 같이 메시지에 추가되는 특정 X-헤더 필드입니다.

다음 섹션에서는 보안 & 준수 센터와 Exchange Online PowerShell 또는 독립 실행형 EOP[PowerShell(New-HostedContentFilterPolicy 및 Set-HostedContentFilterPolicy)에서](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy) 스팸 방지 정책에 사용할 수 있는 ASF 설정 [및 옵션에 대해 설명합니다.](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy) 자세한 내용은 [EOP에서 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.

## <a name="enable-disable-or-test-asf-settings"></a>ASF 설정 사용 또는 사용 안 함 또는 테스트

각 ASF 설정에 대해 스팸 방지 정책에서 다음 옵션을 사용할 수 있습니다.

- **On**: ASF는 메시지에 해당하는 X-헤더 필드를 추가하고 **Spam** 해당 메시지를 스팸(SCL 5 또는 6, 스팸 점수 설정 늘리기) 또는 높은 **지수의** 스팸(SCL 9 - [스팸 설정으로 표시)으로 표시합니다.](#mark-as-spam-settings) [Increase spam score settings](#increase-spam-score-settings)

- **Off:** ASF 설정을 사용할 수 없습니다. 이것이 기본값이며 설정을 변경하지 않는 것이 좋습니다.

- **테스트:** ASF는 해당하는 X-헤더 필드를 메시지에 추가합니다. 메시지에 수행되는 작업은 테스트 모드*옵션(TestModeAction)* **값에** 따라 결정됩니다.

  - **None**: ASF 검색의 영향을 받지 않음 EOP에서 메시지에는 여전히 다른 유형의 필터링 및 규칙이 적용됩니다.

  - **기본 X-헤더 텍스트(*AddXHeader)*** 추가: X-헤더 `X-CustomSpam: This message was filtered by the custom spam filter option` 값이 메시지에 추가됩니다. 받은 편지함 규칙이나 메일 흐름 규칙(전송 규칙이라고도 함)에서 이 값을 사용하여 메시지의 라우팅 및 배달에 영향을 줄 수 있습니다.

  - **숨은 참조*메시지(BccMessage):*** 지정된 전자 메일 주소(PowerShell의 *TestModeBccToRecipients* 매개 변수 값)가 메시지의 숨은 참조 필드에 추가되고 이 메시지는 숨은 참조 받는 사람에게 배달됩니다. 보안 센터에서 & 주소가 여러 개인 경우 각 전자 메일 주소를 세미콜론(; )으로 구분합니다. PowerShell에서 전자 메일 주소가 여러 개인 경우 각 전자 메일 주소를 쉼표로 구분합니다.

  **참고:**

  - 다음 ASF 설정에는 테스트 모드를 사용할 수 없습니다.

    - **조건부 보낸 사람 ID 필터링: 영구** *실패(MarkAsSpamFromAddressAuthFail)*
    - **NDR 후방 분산(***MarkAsSpamNdrBackscatter)*
    - **SPF 레코드: 영구 실패(** *MarkAsSpamSpfRecordHardFail)*

  - 테스트로 설정된 모든 ASF *설정에* 동일한 테스트 모드 동작이 **적용됩니다.** 다양한 ASF 설정에 대해 다른 테스트 모드 동작을 구성할 수 없습니다.

## <a name="increase-spam-score-settings"></a>스팸 점수 설정 늘리기

다음 ASF 설정은 감지된 메시지의 SCL(스팸 지수)을 5 또는 6으로 설정합니다. 이 설정은 스팸 **필터** 결과 및 스팸 방지 정책에서 해당 작업에 해당하는 5-6으로 설정합니다.

****

|스팸 방지 정책 설정|설명|X-헤더 추가됨|
|---|---|---|
|**원격 사이트에 대한 이미지 링크** <br/><br/> *IncreaseScoreWithImageLinks*|원격 사이트(예: `<Img>` http)에 대한 HTML 태그 링크를 포함하는 메시지는 스팸으로 표시됩니다.|`X-CustomSpam: Image links to remote sites`|
|**다른 포트로 URL 리디렉션** <br/><br/> *IncreaseScoreWithRedirectToOtherPort*|80(HTTP), 8080(대체 HTTP) 또는 443(HTTPS) 이외의 TCP 포트로 리디렉션되는 하이퍼링크가 포함된 메시지는 스팸으로 표시됩니다.|`X-CustomSpam: URL redirect to other port`|
|**URL의 숫자 IP 주소** <br/><br/> *IncreaseScoreWithNumericIps*|숫자 기반 URL(일반적으로 IP 주소)이 포함된 메시지는 스팸으로 표시됩니다.|`X-CustomSpam: Numeric IP in URL`|
|**.biz 또는 .info 웹 사이트의 URL** <br/><br/> *IncreaseScoreWithBizOrInfoUrls*|메시지 본문에 .biz 또는 .info 링크가 포함된 메시지는 스팸으로 표시됩니다.|`X-CustomSpam: URL to .biz or .info websites`|
|

## <a name="mark-as-spam-settings"></a>스팸 설정으로 표시

다음 ASF 설정은 검색된 메시지의 SCL을 높은 **신뢰도스팸** 필터 결과 및 스팸 방지 정책에서 해당 작업에 해당하는 9로 설정합니다.

****

|스팸 방지 정책 설정|설명|X-헤더 추가됨|
|---|---|---|
|**빈 메시지** <br/><br/> *MarkAsSpamEmptyMessages*|제목이 없고, 메시지 본문에 내용이 없고, 첨부 파일은 높은 지수의 스팸으로 표시됩니다.|`X-CustomSpam: Empty Message`|
|**HTML의 JavaScript 또는 VBScript** <br/><br/> *MarkAsSpamJavaScriptInHtml*|HTML에서 JavaScript 또는 Visual Basic Script Edition을 사용하는 메시지는 높은 지수의 스팸으로 표시됩니다. <br/><br/> 이러한 스크립팅 언어는 전자 메일 메시지에서 특정 작업이 자동으로 수행되도록 하는 데 사용됩니다.|`X-CustomSpam: Javascript or VBscript tags in HTML`|
|**HTML의 Frame 또는 IFrame 태그** <br><br/> *MarkAsSpamFramesInHtml*|포함된 태그 `<frame>` 또는 `<iframe>` HTML 태그가 포함된 메시지는 높은 신뢰도의 스팸으로 표시됩니다. <br/><br/> 이러한 태그는 전자 메일 메시지에서 텍스트 또는 그래픽을 표시하도록 페이지 서식을 설정하는 데 사용됩니다.|`X-CustomSpam: IFRAME or FRAME in HTML`|
|**HTML의 Object 태그** <br><br/> *MarkAsSpamObjectTagsInHtml*|HTML 태그가 `<object>` 포함된 메시지는 높은 신뢰도 스팸으로 표시됩니다. <br/><br/> 이 태그를 통해 플러그 인이나 응용 프로그램을 HTML 창에서 실행할 수 있습니다.|`X-CustomSpam: Object tag in html`|
|**HTML의 Embed 태그** <br><br/> *MarkAsSpamEmbedTagsInHtml*|HTML 태그가 `<embed>` 포함된 메시지는 높은 신뢰도 스팸으로 표시됩니다. <br/><br/> 이 태그를 사용하면 HTML 문서에 데이터 형식이 다른 여러 종류의 문서(예: 사운드, 동영진, 사진 등)를 포함할 수 있습니다.|`X-CustomSpam: Embed tag in html`|
|**HTML의 Form 태그** <br><br/> *MarkAsSpamFormTagsInHtml*|HTML 태그가 `<form>` 포함된 메시지는 높은 신뢰도 스팸으로 표시됩니다. <br/><br/> 이 태그는 웹 사이트 양식을 만드는 데 사용됩니다. 전자 메일 광고에는 대개 받는 사람으로부터 정보를 얻기 위해 이 태그가 포함됩니다.|`X-CustomSpam: Form tag in html`|
|**HTML의 웹 버그** <br><br/> *MarkAsSpamWebBugsInHtml*|웹 *버그(웹* *브라우저로도*알려진 것)는 전자 메일 메시지에 메시지를 읽었는지 여부를 확인하는 데 사용되는 그래픽 요소(보통 1픽셀에서 작은 크기)입니다. <br/><br/> 웹 버그가 포함된 메시지는 높은 신뢰도의 스팸으로 표시됩니다. <br/><br/> 적법한 뉴스레터는 웹 버그를 사용할 수 있지만, 개인 정보 대신 대부분의 경우에는 이 방법을 고려합니다. |`X-CustomSpam: Web bug`|
|**민감한 단어 목록 적용** <br><br/> *MarkAsSpamSensitiveWordList*|Microsoft에서는 비속이 용도로 저하될 수 있는 메시지와 연결된 동적이면서 편집할 수 없는 단어 목록을 유지합니다. <br/><br/> 제목 또는 메시지 본문에 있는 민감한 단어 목록의 단어가 포함된 메시지는 높은 지수의 스팸으로 표시됩니다.|`X-CustomSpam: Sensitive word in subject/body`|
|**SPF 레코드: 영구 실패** <br><br/> *MarkAsSpamSpfRecordHardFail*|원본 전자 메일 도메인에 대한 DNS의 SPF SPF(Sender Policy Framework) 레코드에 지정되지 않은 IP 주소에서 전송된 메시지는 높은 지수의 스팸으로 표시됩니다. <br/><br/> 이 설정에는 테스트 모드를 사용할 수 없습니다.|`X-CustomSpam: SPF Record Fail`|
|**조건부 보낸 사람 ID 필터링: 영구 실패** <br><br/> *MarkAsSpamFromAddressAuthFail*|조건부 보낸 사람 ID 검사에서 영구 실패가 발생한 메시지는 스팸으로 표시됩니다. <br/><br/> 이 설정은 SPF 검사와 보낸 사람 ID 검사가 하나로 된 형성하여 보낸 사람이 위조된 메시지 헤더를 차단합니다. <br/><br/> 이 설정에는 테스트 모드를 사용할 수 없습니다.|`X-CustomSpam: SPF From Record Fail`|
|**NDR 후방 분산** <br><br/> *MarkAsSpamNdrBackscatter*|*후방 분산은 전자* 메일 메시지의 위조된 보낸 사람이 NDR 또는 반송 메시지라고도 함)이 필요 없는 것입니다. 자세한 내용은 [후방 분산 메시지 및 EOP를 참조하세요.](backscatter-messages-and-eop.md) <br/><br/> 다음 환경에서는 합법적인 NDR이 배달되고 후방 분산 터터가 스팸으로 표시되므로 이 설정을 구성할 필요가 없습니다. <ul><li>Exchange Online 사서함을 사용하는 Microsoft 365 조직</li><li>EOP를 통해 아웃바운드 전자 메일을 라우팅하는 *온-프레미스* 전자 메일 조직</li></ul><br/> 온-프레미스 사서함으로 인바운드 전자 메일을 보호하는 독립 실행형 EOP 환경에서 이 설정을 켜거나 해제하면 다음과 같은 결과를 가져올 수 있습니다. <ul><li> **On**: Legate NDR is delivered, and backscatter is marked as spam.</li><li>**꺼짐:** 합법적인 NDR 및 후방 분산이 일반 스팸 필터링을 통과합니다. 대부분의 합법적인 NDR은 원래 메시지 보낸 사람에게 배달됩니다. 전부는 아니지만 배터리는 높은 지수의 스팸으로 표시됩니다. 정의에 따라 후방 분산형은 원래 보낸 사람이 아라인다면 오는 스푸핑된 보낸 사람에게만 전달될 수 있습니다.</li></ul><br/> 이 설정에는 테스트 모드를 사용할 수 없습니다.|`X-CustomSpam: Backscatter NDR`|
|
