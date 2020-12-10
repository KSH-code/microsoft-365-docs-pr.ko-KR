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
description: 관리자는 EOP(Exchange Online Protection)의 스팸 방지 정책에서 사용할 수 있는 ASF(고급 스팸 필터) 설정에 대해 학습할 수 있습니다.
ms.openlocfilehash: 3ac2b45cc03327f47bd73efe54e78312cbda4bb6
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615255"
---
# <a name="advanced-spam-filter-asf-settings-in-eop"></a>EOP의 ASF(고급 스팸 필터) 설정

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> 현재 스팸 방지 정책에서 사용할 수 있는 ASF 설정은 사용되지 않습니다. 스팸 방지 정책에서는 이러한 설정을 사용하지 않는 것이 좋습니다. 이러한 ASF 설정의 기능은 필터링 스택의 다른 부분에 통합되고 있습니다. 자세한 내용은 EOP 스팸 [방지 정책 설정을 참조하세요.](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

모든 Microsoft 365 조직에서 EOP의 스팸 방지 정책에 있는 ASF(고급 스팸 필터) 설정을 사용하면 관리자가 특정 메시지 속성에 따라 메시지를 스팸으로 표시하도록 할 수 있습니다. ASF는 스팸에서 일반적으로 발견되는 속성이기 때문에 이러한 속성을 구체적으로 대상으로 합니다. 속성에 따라 ASF 검색은 메시지를 스팸 또는  높은 신뢰도 스팸으로 **표시합니다.**

> [!NOTE]
> 하나 이상의 ASF 설정을 사용하도록 설정하는 것은 스팸 필터링에 대한 적극적인 접근 방식입니다. ASF로 필터링된 메시지는 가짓 긍정으로 보고할 수 없습니다. 다음을 통해 ASF로 필터링된 메시지를 식별할 수 있습니다.
>
> - 주기적인 최종 사용자 스팸 차단 알림.
>
> - 필터링된 메시지가 있는 경우
>
> - 이 항목에 설명된 바와 같이 메시지에 추가되는 특정 `X-CustomSpam:` X-헤더 필드입니다.

다음 섹션에서는 보안 및 준수 센터 및 Exchange Online PowerShell 또는 독립 실행형 EOP[PowerShell(New-HostedContentFilterPolicy 및 Set-HostedContentFilterPolicy)의](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy) 스팸 방지 정책에서 사용할 수 있는 AS & F 설정 및 옵션에 대해 설명합니다. [](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy) 자세한 내용은 [EOP에서 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.

## <a name="enable-disable-or-test-asf-settings"></a>ASF 설정 사용, 비활성화 또는 테스트

각 ASF 설정에 대해 다음 옵션을 스팸 방지 정책에서 사용할 수 있습니다.

- **On**: ASF는 메시지에 해당 X-헤더 필드를 추가하고 메시지를  스팸(스팸 점수 설정 증가의 경우 SCL  5 또는 6) [](#mark-as-spam-settings) [](#increase-spam-score-settings)또는 높은 지수 스팸(스팸으로 표시 설정의 경우 SCL 9)으로 표시합니다.

- **끄기**: ASF 설정을 사용할 수 없습니다. 이 값은 기본값으로, 변경하지 않는 것이 좋습니다.

- **Test**: ASF는 메시지에 해당 X-헤더 필드를 추가합니다. 메시지는 테스트 모드 옵션(TestModeAction) 값에 따라 결정됩니다.  

  - **없음:** ASF 검색의 영향을 받지 않습니다. 메시지에는 여전히 EOP의 다른 유형의 필터링 및 규칙이 적용될 수 있습니다.

  - **기본 X-헤더 텍스트 *추가(AddXHeader*)**: X-헤더 값이 `X-CustomSpam: This message was filtered by the custom spam filter option` 메시지에 추가됩니다. 받은 편지함 규칙 또는 메일 흐름 규칙(전송 규칙)에서 이 값을 사용하여 메시지 배달에 영향을 줄 수 있습니다.

  - **Bcc 메시지 *보내기(BccMessage*)**: 지정된 전자 메일 주소(PowerShell의 *TestModeBccToRecipients* 매개 변수 값)가 메시지의 Bcc 필드에 추가되어 추가 Bcc 받는 사람에게 메시지가 배달됩니다. 보안 & 준수 센터에서는 전자 메일 주소가 여러 개인 경우 세미코론(;). PowerShell에서는 전자 메일 주소가 여러 개인 경우 각 주소를 콤보로 구분합니다.

  **참고**:

  - 다음 ASF 설정에는 테스트 모드를 사용할 수 없습니다.

    - **조건부 보낸 사람 ID 필터링: 하드** *실패(MarkAsSpamFromAddressAuthFail)*
    - **NDR** 후방산자(MarkAsSpamNdrBackscatter)
    - **SPF 레코드: 하드** *실패(MarkAsSpamSpfRecordHardFail)*

  - Test로 설정된 *모든* ASF 설정에 동일한 테스트 모드 작업이 **적용됩니다.** ASF 설정마다 다른 테스트 모드 작업을 구성할 수 없습니다.

## <a name="increase-spam-score-settings"></a>스팸 점수 설정 늘리기

다음 ASF 설정은 검색된 메시지의 SCL(스팸 지수)을 스팸 필터 판정  및 스팸 방지 정책의 해당 동작에 해당하는 5 또는 6으로 설정합니다.

****

|스팸 방지 정책 설정|설명|추가된 X-헤더|
|---|---|---|
|**원격 사이트에 대한 이미지 링크** <p> *IncreaseScoreWithImageLinks*|원격 사이트에 대한 HTML 태그 링크가 포함된 메시지(예: http 사용)는 `<Img>` 스팸으로 표시됩니다.|`X-CustomSpam: Image links to remote sites`|
|**다른 포트로 URL 리디렉션** <p> *IncreaseScoreWithRedirectToOtherPort*|80(HTTP), 8080(대체 HTTP) 또는 443(HTTPS) 외의 TCP 포트로 리디렉션하는 하이퍼링크가 포함된 메시지는 스팸으로 표시됩니다.|`X-CustomSpam: URL redirect to other port`|
|**URL의 숫자 IP 주소** <p> *IncreaseScoreWithNumericIps*|숫자 기반 URL(일반적으로 IP 주소)이 포함된 메시지는 스팸으로 표시됩니다.|`X-CustomSpam: Numeric IP in URL`|
|**.biz 또는 .info 웹 사이트의 URL** <p> *IncreaseScoreWithBizOrInfoUrls*|메시지 본문에 포함되거나 링크가 포함된 메시지는 `.biz` `.info` 스팸으로 표시됩니다.|`X-CustomSpam: URL to .biz or .info websites`|
|

## <a name="mark-as-spam-settings"></a>스팸 설정으로 표시

다음 ASF 설정은 검색된 메시지의 SCL을 9로 설정하며, 이 SCL은 스팸 방지 정책의 높은 지수 스팸 필터 판정 및 해당 동작에 해당합니다. 

****

|스팸 방지 정책 설정|설명|추가된 X-헤더|
|---|---|---|
|**빈 메시지** <p> *MarkAsSpamEmptyMessages*|제목이 없는 메시지, 메시지 본문의 콘텐츠 및 첨부 파일이 없는 메시지는 높은 신뢰도 스팸으로 표시됩니다.|`X-CustomSpam: Empty Message`|
|**HTML의 JavaScript 또는 VBScript** <p> *MarkAsSpamJavaScriptInHtml*|HTML에서 JavaScript 또는 Visual Basic Script Edition을 사용하는 메시지는 높은 신뢰도 스팸으로 표시됩니다. <p> 이러한 스크립팅 언어는 전자 메일 메시지에서 특정 작업이 자동으로 수행될 수 있도록 하는 데 사용됩니다.|`X-CustomSpam: Javascript or VBscript tags in HTML`|
|**HTML의 Frame 또는 IFrame 태그** <p> *MarkAsSpamFramesInHtml*|HTML 태그가 포함된 `<frame>` `<iframe>` 메시지는 높은 신뢰도 스팸으로 표시됩니다. <p> 이러한 태그는 전자 메일 메시지에서 텍스트 또는 그래픽을 표시하기 위해 페이지의 서식을 지정하는 데 사용됩니다.|`X-CustomSpam: IFRAME or FRAME in HTML`|
|**HTML의 Object 태그** <p> *MarkAsSpamObjectTagsInHtml*|HTML 태그가 포함된 메시지는 높은 신뢰도 `<object>` 스팸으로 표시됩니다. <p> 이 태그를 사용하면 플러그 인 또는 응용 프로그램이 HTML 창에서 실행될 수 있습니다.|`X-CustomSpam: Object tag in html`|
|**HTML의 Embed 태그** <p> *MarkAsSpamEmbedTagsInHtml*|`<embed>`HTML 태그가 포함된 메시지는 높은 신뢰도 스팸으로 표시됩니다. <p> 이 태그를 사용하면 HTML 문서에 다양한 종류의 문서(예: 사운드, 비디오 또는 그림)를 함께 사용할 수 있습니다.|`X-CustomSpam: Embed tag in html`|
|**HTML의 Form 태그** <p> *MarkAsSpamFormTagsInHtml*|HTML 태그가 포함된 메시지는 높은 신뢰도 `<form>` 스팸으로 표시됩니다. <p> 이 태그는 웹 사이트 양식을 만드는 데 사용됩니다. 전자 메일 광고에는 대개 받는 사람으로부터 정보를 얻기 위해 이 태그가 포함됩니다.|`X-CustomSpam: Form tag in html`|
|**HTML의 웹 버그** <p> *MarkAsSpamWebBugsInHtml*|웹  버그(웹 알림)는 받는 사람이 메시지를 읽은지 여부를 확인하는 데 사용되는 그래픽 요소(대개 1픽셀 x 1픽셀)입니다.  <p> 웹 버그가 포함된 메시지는 높은 신뢰도 스팸으로 표시됩니다. <p> 합법적인 뉴스레터는 웹 버그를 사용할 수 있습니다. 그러나 많은 뉴스레터는 이를 개인 정보 침해로 고려합니다. |`X-CustomSpam: Web bug`|
|**민감한 단어 목록 적용** <p> *MarkAsSpamSensitiveWordList*|Microsoft는 잠재적으로 공격적인 메시지와 연관된 동적이지만 편집할 수 없는 단어 목록을 유지 관리합니다. <p> 제목 또는 메시지 본문에 있는 중요한 단어 목록의 단어가 포함된 메시지는 높은 신뢰도 스팸으로 표시됩니다.|`X-CustomSpam: Sensitive word in subject/body`|
|**SPF 레코드: 영구 실패** <p> *MarkAsSpamSpfRecordHardFail*|원본 전자 메일 도메인에 대한 DNS의 SPF(Sender Policy Framework) 레코드에 지정되지 않은 IP 주소에서 보낸 메시지는 높은 신뢰도 스팸으로 표시됩니다. <p> 이 설정에는 테스트 모드를 사용할 수 없습니다.|`X-CustomSpam: SPF Record Fail`|
|**조건부 보낸 사람 ID 필터링: 영구 실패** <p> *MarkAsSpamFromAddressAuthFail*|조건부 보낸 사람 ID 검사를 하드 실패한 메시지는 스팸으로 표시됩니다. <p> 이 설정은 SPF 검사와 보낸 사람 ID 검사를 결합하여 보낸 사람이 포함된 메시지 헤더를 보호합니다. <p> 이 설정에는 테스트 모드를 사용할 수 없습니다.|`X-CustomSpam: SPF From Record Fail`|
|**NDR 후방 분산** <p> *MarkAsSpamNdrBackscatter*|*후방산은* 전자 메일 메시지의 보낸 사람에 의해 발생된 NDRs 또는 반송 메시지라고도 하는, 사용하지 않는 배달되지 않는 보고서입니다. 자세한 내용은 후방산자 메시지 및 [EOP를 참조하세요.](backscatter-messages-and-eop.md) <p> 합법적인 NDRS가 배달되어 후방 스캐터가 스팸으로 표시되어 있기 때문에 다음 환경에서는 이 설정을 구성할 필요가 없습니다. <ul><li>Exchange Online 사서함이 있는 Microsoft 365 조직</li><li>EOP를 통해 아웃바운드 전자 메일을 라우팅하는 On-premises  전자 메일 조직</li></ul> <p> 인바운드 전자 메일을온-프레미스 사서함으로 보호하는 독립 실행형 EOP 환경에서 이 설정을 켜거나 끄면 다음과 같은 결과가 나타납니다. <ul><li> **On**: 합법적인 NDRS가 배달되어 후방 스캐터가 스팸으로 표시됩니다.</li><li>**해제:** 합법적인 NDRS 및 후방 스캐터는 일반적인 스팸 필터링을 거치게 됩니다. 대부분의 합법적인 NDRS는 원본 메시지 보낸 사람에 배달됩니다. 일부 후방 스캐터는 높은 신뢰도 스팸으로 표시됩니다. 정의에 따라 후방산자는 원래 보낸 사람이 아니라 스푸핑된 보낸 사람만 배달할 수 있습니다.</li></ul> <p> 이 설정에는 테스트 모드를 사용할 수 없습니다.|`X-CustomSpam: Backscatter NDR`|
|
