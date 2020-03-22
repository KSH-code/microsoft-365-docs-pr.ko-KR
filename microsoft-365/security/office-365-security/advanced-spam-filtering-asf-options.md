---
title: Office 365의 ASF 설정
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b286f853-b484-4af0-b01f-281fffd85e7a
ms.collection:
- M365-security-compliance
description: 스팸 방지 정책 (즉, 스팸 필터 정책 또는 콘텐츠 필터 정책이 라고도 함)의 ASF (고급 스팸 필터) 설정은 관리자가 스팸에 일반적으로 사용 되는 특정 메시지 속성을 포함 하는 메시지를 식별 하는 것을 허용 합니다. 속성에 따라 ASF 검색은 메시지를 스팸 또는 높은 신뢰도 스팸으로 표시 합니다.
ms.openlocfilehash: e35279092e9d77b18eadd2af33909eda90bdd80b
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "42894255"
---
# <a name="advanced-spam-filter-asf-settings-in-office-365"></a>Office 365의 ASF (고급 스팸 필터) 설정

> [!NOTE]
> 현재 스팸 방지 정책에서 사용할 수 있는 ASF 설정에는 더 이상 사용 되지 않습니다. 스팸 방지 정책에서는 이러한 설정을 사용 하지 않는 것이 좋습니다. 이러한 ASF 설정의 기능은 필터링 스택의 다른 부분에 포함 됩니다. 자세한 내용은 [EOP 스팸 방지 정책 설정](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)항목을 참조 하십시오.

스팸 방지 정책 (즉, 스팸 필터 정책 또는 콘텐츠 필터 정책이 라고도 함)의 ASF (고급 스팸 필터) 설정은 관리자가 특정 메시지 속성을 기반으로 메시지를 스팸으로 표시 하도록 허용 합니다. ASF는 일반적으로 스팸에서 발견 되므로 이러한 속성을 대상으로 합니다. 속성에 따라 ASF 검색은 메시지를 **스팸** 또는 **높은 신뢰도 스팸으로**표시 합니다.

> [!NOTE]
> 하나 이상의 ASF 설정을 사용 하도록 설정 하는 것이 스팸 필터링에 적극적인 방법입니다. ASF로 필터링 된 메시지는 가양성으로 보고할 수 없습니다. 다음과 같은 방법으로 ASF로 필터링 된 메시지를 확인할 수 있습니다. <ul><li>주기적인 최종 사용자 스팸 격리 알림</li><li>필터링 된 메시지가 격리 상태에 있는지 여부</li><li>이 항목 `X-CustomSpam:` 에 설명 된 대로 메시지에 추가 되는 특정 X-헤더 필드입니다.</li></ul>

다음 섹션에서는 Office 365 보안 & 준수 센터의 스팸 방지 정책에서 사용할 수 있는 ASF 설정 및 옵션 및 Exchange Online PowerShell 또는 독립 실행형 Exchange Online Protection PowerShell ([get-hostedcontentfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedcontentfilterpolicy) 및 [get-hostedcontentfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy))에 대해 설명 합니다. 자세한 내용은 [Office 365의 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.

## <a name="enable-disable-or-test-asf-settings"></a>ASF 설정 사용, 사용 안 함 또는 테스트

다음은 각 ASF 설정에 대해 스팸 방지 정책에서 사용할 수 있는 옵션입니다.

- **켜기**: ASF는 해당 하는 X-헤더 필드를 메시지에 추가 하 고 메시지를 **스팸으로** 표시 합니다 (scl 5 또는 6 [스팸 점수 설정 증가](#increase-spam-score-settings)) 또는 **높은 신뢰도 스팸** (scl 9 to [스팸 설정으로 표시](#mark-as-spam-settings))

- **Off**: ASF 설정이 사용 하지 않도록 설정 되었습니다. 이 값은 기본값 이므로 변경 하지 않는 것이 좋습니다.

- **Test**: ASF는 해당 하는 X-헤더 필드를 메시지에 추가 합니다. 메시지에 대해 수행 되는 작업은 **테스트 모드 옵션** (*testmodeaction*) 값에 따라 결정 됩니다.

  - **없음**: 메시지 라우팅과 배달은 ASF 감지가 영향을 받지 않습니다. 메시지에 여전히 EOP의 다른 필터링 및 규칙 유형이 적용 됩니다.

  - **기본 X-헤더 텍스트 추가 (*Addxheader*)**: X-헤더 값 `X-CustomSpam: This message was filtered by the custom spam filter option` 이 메시지에 추가 됩니다. 받은 편지함 규칙 또는 메일 흐름 규칙 (전송 규칙이 라고도 함)에서이 값을 사용 하 여 메시지의 라우팅 및 배달에 영향을 줄 수 있습니다.

  - **Bcc 메시지 보내기 (*Bccmessage*)**: 지정 된 전자 메일 주소 (PowerShell의 *TestModeBccToRecipients* 매개 변수 값)가 메시지의 숨은 참조 필드에 추가 되 고 해당 메시지는 숨은 참조 받는 사람에 게 배달 됩니다. Office 365 보안 & 준수 센터에서는 여러 전자 메일 주소를 세미콜론 (;)으로 구분 합니다. PowerShell에서는 여러 전자 메일 주소를 쉼표로 구분 합니다.

  **참고:**

  - 다음 ASF 설정에는 테스트 모드를 사용할 수 없습니다.

    - **조건부 보낸 사람 ID 필터링: 하드 실패** (*MarkAsSpamFromAddressAuthFail*)

    - **NDR 백 분산**(*MarkAsSpamNdrBackscatter*)

    - **SPF 레코드: 하드 실패** (*MarkAsSpamSpfRecordHardFail*)

  - **테스트**하도록 설정 된 *모든* ASF 설정에 동일한 테스트 모드 작업이 적용 됩니다. 서로 다른 ASF 설정에 대해 서로 다른 테스트 모드 작업을 구성할 수 없습니다.

## <a name="increase-spam-score-settings"></a>스팸 점수 설정 증가

다음 ASF 설정은 검색 된 메시지의 SCL (스팸 지 수)을 5 또는 6으로 설정 하며,이는 스팸 **필터 결과** 에 해당 하 고 스팸 방지 정책에서 해당 작업에 해당 합니다.

||||
|:-----|:-----|:-----|
|**스팸 방지 정책 설정**|**설명**|**X-헤더 추가 됨**|
|**원격 사이트에 대한 이미지 링크** <br/><br/> *IncreaseScoreWithImageLinks*|Http를 사용 `<Img>` 하는 등의 원격 사이트에 대 한 HTML 태그를 포함 하는 메시지는 스팸으로 표시 됩니다.|`X-CustomSpam: Image links to remote sites`|
|**다른 포트로 URL 리디렉션** <br/><br/> *IncreaseScoreWithRedirectToOtherPort*|80 (HTTP), 8080 (대체 HTTP) 또는 443 (HTTPS) 이외의 TCP 포트로 리디렉션되는 하이퍼링크를 포함 하는 메시지는 스팸으로 표시 됩니다.|`X-CustomSpam: URL redirect to other port`|
|**URL의 숫자 IP 주소** <br/><br/> *IncreaseScoreWithNumericIps*|숫자 기반 Url (대개 IP 주소)이 포함 된 메시지는 스팸으로 표시 됩니다.|`X-CustomSpam: Numeric IP in URL`|
|**.biz 또는 .info 웹 사이트의 URL** <br/><br/> *IncreaseScoreWithBizOrInfoUrls*|메시지 본문에 있는. t a t e t/.|`X-CustomSpam: URL to .biz or .info websites`|
|

## <a name="mark-as-spam-settings"></a>스팸 설정으로 표시

다음 ASF 설정은 검색 된 메시지의 SCL을 전자 스팸 방지 정책 결과 및 해당 작업에 해당 **하는 9** 로 설정 합니다.

||||
|:-----|:-----|:-----|
|**스팸 방지 정책 설정**|**설명**|**X-헤더 추가 됨**|
|**빈 메시지** <br/><br/> *MarkAsSpamEmptyMessages*|제목이 없고 메시지 본문에 콘텐츠가 없으며, 첨부 파일이 높은 신뢰도 스팸으로 표시 되지 않은 메시지입니다.|`X-CustomSpam: Empty Message`|
|**HTML의 JavaScript 또는 VBScript** <br/><br/> *MarkAsSpamJavaScriptInHtml*|HTML에서 JavaScript 또는 Visual Basic Script Edition을 사용 하는 메시지는 신뢰도가 높은 스팸으로 표시 됩니다. <br/><br/> 이러한 스크립팅 언어는 특정 동작이 자동으로 발생 하도록 하는 전자 메일 메시지에 사용 됩니다.|`X-CustomSpam: Javascript or VBscript tags in HTML`|
|**HTML의 Frame 또는 IFrame 태그** <br><br/> *MarkAsSpamFramesInHtml*|또는 `<iframe>` HTML 태그 `<frame>` 를 포함 하는 메시지는 신뢰도가 높은 스팸으로 표시 됩니다. <br/><br/> 이러한 태그는 전자 메일 메시지에서 텍스트나 그래픽을 표시 하도록 페이지 서식을 지정 하는 데 사용 됩니다.|`X-CustomSpam: IFRAME or FRAME in HTML`|
|**HTML의 Object 태그** <br><br/> *MarkAsSpamObjectTagsInHtml*|HTML 태그를 `<object>` 포함 하는 메시지는 신뢰도가 높은 스팸으로 표시 됩니다. <br/><br/> 이 태그를 사용 하면 플러그 인 또는 응용 프로그램을 HTML 창에서 실행할 수 있습니다.|`X-CustomSpam: Object tag in html`|
|**HTML의 Embed 태그** <br><br/> *MarkAsSpamEmbedTagsInHtml*|HTML 태그를 `<embed>` 포함 하는 메시지는 신뢰도가 높은 스팸으로 표시 됩니다. <br/><br/> 이 태그를 사용 하면 소리, 동영상 또는 그림 같은 HTML 문서에 다양 한 데이터 형식으로 다양 한 유형의 문서를 포함할 수 있습니다.|`X-CustomSpam: Embed tag in html`|
|**HTML의 Form 태그** <br><br/> *MarkAsSpamFormTagsInHtml*|HTML 태그를 `<form>` 포함 하는 메시지는 신뢰도가 높은 스팸으로 표시 됩니다. <br/><br/> 이 태그는 웹 사이트 양식을 만드는 데 사용 됩니다. 전자 메일 광고에는 대개 받는 사람으로부터 정보를 얻기 위해 이 태그가 포함됩니다.|`X-CustomSpam: Form tag in html`|
|**HTML의 웹 버그** <br><br/> *MarkAsSpamWebBugsInHtml*|Web *bug* ( *웹 탐지 장치*라고도 함)는 전자 메일 메시지에서 메시지를 읽었는지 여부를 확인 하는 데 사용 되는 그래픽 요소 (대개 1 픽셀씩 작은 픽셀)입니다. <br/><br/> 웹 버그가 포함 된 메시지는 신뢰도가 높은 스팸으로 표시 됩니다. <br/><br/> 합법적인 뉴스레터에는 웹 버그가 있을 수 있지만, 대부분의 개인 정보 보호에 대 한 invasion 고려해 야 합니다. |`X-CustomSpam: Web bug`|
|**민감한 단어 목록 적용** <br><br/> *MarkAsSpamSensitiveWordList*|Microsoft는 잠재적으로 유해한 메시지와 연결 된 동적이 고 편집이 불가능 한 단어 목록을 유지 관리 합니다. <br/><br/> 제목 또는 메시지 본문에 있는 중요 한 단어 목록의 단어를 포함 하는 메시지는 신뢰도가 높은 스팸으로 표시 됩니다.|`X-CustomSpam: Sensitive word in subject/body`|
|**SPF 레코드: 영구 실패** <br><br/> *MarkAsSpamSpfRecordHardFail*|원본 전자 메일 도메인에 대 한 DNS의 SPF (SPF Sender Policy Framework) 레코드에 지정 되지 않은 IP 주소에서 보낸 메시지는 신뢰도가 높은 스팸으로 표시 됩니다. <br/><br/> 이 설정에 대해 테스트 모드를 사용할 수 없습니다.|`X-CustomSpam: SPF Record Fail`|
|**조건부 보낸 사람 ID 필터링: 영구 실패** <br><br/> *MarkAsSpamFromAddressAuthFail*|조건부 보낸 사람 ID 확인을 수행 하지 못하는 메시지는 스팸으로 표시 됩니다. <br/><br/> 이 설정은 보낸 사람을 포함 하는 메시지 헤더 로부터 보호 하는 데 도움이 되도록 SPF 검사와 Sender ID 확인을 결합 합니다. <br/><br/> 이 설정에 대해 테스트 모드를 사용할 수 없습니다.|`X-CustomSpam: SPF From Record Fail`|
|**NDR 후방 분산** <br><br/> *MarkAsSpamNdrBackscatter*|*Backscatter* 은 전자 메일 메시지의 위조 된 보낸 사람에 의해 발생 하는 쓸모 없는 배달 못 함 보고서 (ndr 또는 바운스 메시지로도 알려짐)입니다. 자세한 내용은 [Backscatter 메시지 및 EOP](backscatter-messages-and-eop.md)을 참조 하십시오. <br/><br/> 합법적인 ndr이 배달 되 고 후방 산란이 스팸으로 표시 되므로 다음 환경에서는이 설정을 구성할 필요가 없습니다. <ul><li>Exchange Online 사서함이 있는 Office 365 조직</li><li>EOP를 통해 *아웃 바운드* 전자 메일을 라우팅하는 온-프레미스 전자 메일 조직</li></ul><br/> 온-프레미스 사서함에 대 한 인바운드 전자 메일을 보호 하는 독립 실행형 EOP 환경에서는이 설정을 사용 하거나 사용 하지 않도록 설정 하면 다음과 같은 결과가 반환 됩니다. <ul><li> **켜기**: 합법적인 ndr이 배달 되 고, 백 산이 스팸으로 표시 됩니다.</li><li>**Off**: 합법적인 ndr 및 백 분산은 일반 스팸 필터링을 통해 진행 됩니다. 대부분의 합법적인 Ndr은 원본 메시지 보낸 사람에 게 배달 됩니다. 일부는 아니지만, 모든 백 산은 신뢰도가 높은 스팸으로 표시 됩니다. 정의에 따라 후방 산란은 원래 보낸 사람이 아닌 스푸핑된 보낸 사람 에게만 배달 될 수 있습니다.</li></ul><br/> 이 설정에 대해 테스트 모드를 사용할 수 없습니다.|`X-CustomSpam: Backscatter NDR`|
|
