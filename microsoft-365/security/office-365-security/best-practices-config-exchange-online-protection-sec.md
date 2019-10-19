---
title: 구성 모범 사례 EOP 및 Office 365 ATP 보안, 모범 사례, 설정, 권장 사항, 보낸 사람 정책 프레임 워크, 도메인 기반 메시지 보고 및 적합성, DomainKeys 식별 된 메일, 단계, 작동 방식
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/18/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
description: EOP (Exchange Online Protection) 및 ATP (Advanced Threat Protection) 보안 설정에 대 한 모범 사례 권장 사항 적극적으로 어떤 작업을 수행 해야 하나요? 또한 ATP (Advanced Threat Protection)를 사용 하는 경우에는 어떤 것을 얻게 됩니까?
ms.openlocfilehash: b40b4189ed996e1b2f671b77602630f2a98966a5
ms.sourcegitcommit: ffdf576fbc62c4c316f6d8061d2bd973e7df9f56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2019
ms.locfileid: "37598302"
---
# <a name="best-practices-for-configuring-eop-and-office-365-atp-security"></a>EOP 및 Office 365 ATP 보안 구성을 위한 모범 사례

EOP (Exchange Online Protection)는 E3 Office 365 구독의 보안 핵심입니다. 또한 E3 고객이 Office 365 ATP (Advanced Threat Protection)로의 구독을 구입 하는 것이 좋습니다 (예: 권장 사항). ATP 계획 1 또는 ATP 계획 2-E5 Office 365 구독에서 사용할 수 있는 추가 된 보안을 활용 하기 위해

Microsoft에서는 두 보안 수준에서 기능을 사용 하는 방법에 대 한 설명을 포함 하 여 EOP에서 권장 및 적극적 이라는 두 가지 보안 수준에 대해 설명 합니다. 이 섹션은 전자 메일 유효성 검사 및 인증으로 시작 되며,이는 Office 365의 일부 tinkering, DNS에서, 아웃 바운드 메일의 보안을 사용 하 여 메일을 보내는 리소스에 테 넌 트 좋은 시민을 만드는 것입니다. 이러한 설정은 구독을 가장 효과적으로 보호 합니다.


## <a name="email-authentication"></a>전자 메일 인증

SPF, DKIM 및 DMARC는 보낸 사람 정책 프레임 워크, DomainKeys 식별 된 메일, 도메인 기반 메시지 인증, 보고 및 적합성 (매우 중요 한 mouthful)에 대 한 머리글자어 이며 전자 메일 인증 및 유효성 검사의 기초가 됩니다.

이러한 방법은 Office 365의 아웃 바운드 전자 메일을 처리 하 고 대상 시스템에서 사용자 도메인의 전자 메일이 유효한 지를 신뢰 합니다. 사용자는 DNS에서 Office 365 *외부* 의 구성을 수행 하는 것이 가장 좋은 방법입니다. 특정 구성 단계는 목차의 보안 및 준수 표에 있는 [전자 메일 유효성 검사 및 인증](https://docs.microsoft.com/office365/securitycompliance/how-office-365-uses-spf-to-prevent-spoofing) 섹션을 참조 하세요.


|보안 기능 이름  |권장 |업그레이드  |설명  |
|---------|---------|---------|---------|
|[SPF 레코드 만들기](https://docs.microsoft.com/office365/securitycompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)    | 예        |    예     |   -      |
|[도메인에 대해 DKIM 서명 구성](https://docs.microsoft.com/office365/securitycompliance/use-dkim-to-validate-outbound-email)     |  예       |    예     |  -       |
|[거부 또는 격리 작업을 사용 하 여 DMARC 구현](https://docs.microsoft.com/office365/securitycompliance/use-dmarc-to-validate-email)     |   예      |     예    |   Use action = no for 권장 및 작업 = 취소에 대해 거부를 사용 합니다.     |

> [!IMPORTANT]
> 보안 역할 및 사용 권한으로 작업 하려면 Office 365 또는 보안 및 준수 센터에서 적절 한 역할을 보유 하 고 있어야 합니다. Azure Active Directory의 *보안 관리자* 인 경우, Office 365의 *전역 관리자* 이거나 Exchange Online/Exchange Online Powershell에서 *exchange online 조직 관리자* 인 경우에는 준비가 완료 된 것입니다.

## <a name="anti-spam-anti-malware-and-anti-phishing"></a>스팸 방지, 맬웨어 방지 및 피싱 방지

스팸 방지 및 맬웨어 방지 기능은 모두 EOP의 기능입니다. 스팸 필터링은 기본적으로 Office 365에서 모든 메일을 검색 하 고 각 메일에 SCL (스팸 지 수) 번호 값을 할당 합니다. 명확 하 게 설명 하기 위해,이는 메일이 스팸이 되는 것이 확실 함을 열거 하기 위한 것입니다. 낮은 값 (예를 들어,-1)은 수신 허용-보낸 사람 으로부터 스팸이 아니고 사용자의 받은 편지함에 있습니다. 7, 8, 9 같은 높은 점수는 높은 주의 대상 이거나, 사용자의 정크 메일에 대 한 알려진 스팸 발송자 및 헤드 또는 관리자가 액세스할 수 있는 격리입니다.

맬웨어 필터링은 Office 365 에서도 기본적으로 설정 되어 있습니다. 스팸 방지 필터링과 마찬가지로 맬웨어 방지 필터는 인바운드와 아웃 바운드 메일에서 모두 작동 합니다. 두 경우 모두 관리자가이 보호 기능을 보다 적합 하 게 구성할 수 있습니다.

피싱 보고 필터는 Office 365에서 기본적으로 설정 되어 있지만 보다 적합 하 게 구성 해야 합니다. EOP에서 피싱 방지를 위해 권장 되는 사항은 다음과 같습니다.

### <a name="anti-spam"></a>스팸 방지

|보안 기능 이름  |권장 |업그레이드  |설명  |
|---------|---------|---------|---------|
|격리 보존 기간    |   예      |     예    |   30일   |
|최종 사용자 스팸 알림 빈도   |   예      |     예    |   3 일   |
|제로 시간 Autopurge 사용 하도록 설정 해야 합니다.   |   예      |     예    |   참  |
|스팸 검색 작업을 보낼 대상 | JMF | 격리 | - |
|높은 정확도 스팸 검색 작업을 다음에 전송 | 격리 | 격리| - |
|대량 검색 작업은 다음으로 설정 해야 합니다. | JMF | 격리 | - |
|대량 전자 메일 임계값을 다음으로 설정 | 번 | 1-4 | - |
|보안 팁을 사용 하도록 설정 해야 합니다.| 참 | 참 | - |
|최종 사용자 스팸 알림 사용| 참 | False | - |
|허용 된 보낸 사람 | 없음 | 없음 | - |
|허용 된 보낸 사람 도메인 | 없음 | 없음 | - |
|수신 거부 | 없음 | 없음 | - |
|수신 거부 도메인 | 없음 | 없음 | - |
|아웃 바운드 스팸 정책 RRL | 500 | 500 | - |

권장 수준과 적극적인 수준 **모두에서 사용할 것을 권장** 합니다.

|보안 기능 이름  |
|---------|
|IncreaseScoreWithImageLinks|
|IncreaseScoreWithNumericIps|
|IncreaseScoreWithRedirectToOtherPort|
|IncreaseScoreWithBizOrInfoUrls|
|MarkAsSpamEmptyMessages|
|MarkAsSpamJavaScriptInHtml|
|MarkAsSpamFramesInHtml|
|MarkAsSpamObjectTagsInHtml|
|MarkAsSpamEmbedTagsInHtml|
|MarkAsSpamFormTagsInHtml|
|MarkAsSpamWebBugsInHtml|
|MarkAsSpamSensitiveWordList|
|MarkAsSpamFromAddressAuthFail|
|MarkAsSpamNdrBackscatter|

권장 수준과 적극적인 수준 모두 **에 대해 권장** 됩니다.

|보안 기능 이름  |
|---------|
|MarkAsSpamSpfRecordHardFail|
|MarkAsSpamBulkMail|

### <a name="anti-malware"></a>맬웨어 방지

|보안 기능 이름  |권장 |업그레이드  |설명  |
|---------|---------|---------|---------|
|내부 원본에 대 한 맬웨어 알림 구성 |예 |예 |- |
|맬웨어 검색의 외부 보낸 사람에 게 알림 사용 안 함 |예 |예 |- |
|"일반 첨부 파일 형식 필터"를 사용 하 여 의심 스러운 파일 형식 차단 | 예 |예 |- |
|맬웨어 ZAP |참 |참 |- |
|맬웨어 작업 |정책의 |정책의 |- |

### <a name="anti-phishing"></a>피싱 방지

|보안 기능 이름  |권장 |업그레이드  |설명  |
|---------|---------|---------|---------|
|제로 시간 Autopurge을 사용 하도록 설정 해야 함-피싱| 참 | 참 | - | 
|피싱 검색 작업을 다음으로 설정 해야 합니다. | 격리-요청 | 격리-관리자 | - |
|High 신뢰도 피싱 검색 작업을 다음으로 설정 해야 합니다. | 격리-관리자 | 격리-관리자 | - |
|EnableMailboxIntelligence | 참 | 참 | - |
|EnableSimilarUsersSafetyTips | 참 | 참 | - |
|EnableSimilarDomainsSafetyTips | 참 | 참 | - |
|EnableUnusualCharactersSafetyTips | 참 | 참 | - |
|TargetedUserProtectionAction |NoAction |정책의 | - |
|MailboxIntelligenceProtectionAction |NoAction |정책의 | - |
|TargetedDomainProtectionAction |NoAction |정책의 | - |
|AuthenticationFailAction |MoveToJmf |격리 | - |
|AntiSpoofEnforcementType |높음 |높음 | - |
|EnableAuthenticationSafetyTip |False |참 | - |
|EnableAntiSpoofEnforcement |참 |참 | - |
|EnableUnauthenticatedSender |참 |참 | - |
|EnableAuthenticationSoftPassSafetyTip |False |참 | - |
|TreatSoftPassAsAuthenticated |참 |False | - |
|EnableSuspiciousSafetyTip |참 |참 | - |

## <a name="office-365-advanced-threat-protection-atp-security"></a>Office 365 ATP (Advanced Threat Protection) 보안

이전에는 E3 구독을 사용 하 여 Office 365 ATP 계획 1 또는 완전히 실현 된 ATP 계획 2를 추가 하는 것이 좋습니다. 고급 피싱 방지는 이유 중 하나입니다. 사용 하도록 설정 기본적으로는 작동 하도록 정책을 사용 하 여 피싱 방지를 구성 ***해야 합니다*** . 피싱 방지 정책을 구성 하지 않으면 사용자가 위험에 노출 되므로 ATP 구독을 추가한 후-2 단계를 진행 해야 합니다.

> [!IMPORTANT]
>  E5 구독이 있는 경우 현재 [ATP 계획 2](https://products.office.com/exchange/advance-threat-protection)가 있습니다. [ATP의 새로운 기능](https://review.docs.microsoft.com/microsoft-365/security/office-365-security/whats-new-in-office-365-atp?branch=oatp-newstuff)을 확인 하려면이 링크를 선택 합니다.

### <a name="advanced-anti-phishing"></a>고급 피싱 방지

피싱은 신용 카드 번호, 컴퓨터 또는 장치 pin 또는 암호와 같은 개인 정보를 도용 하기 위해 신뢰할 수 있는 회사나 사람에 게 위장 하기 위한 것입니다. 피싱에는 다음이 포함 됩니다.

- **스푸핑**(여기서 spoofers은 도메인에서 특정 대상을 대신 하 여 메일을 보내려고 시도 합니다 (예: ellar@2020litware.com에 대 한 메일을 보내려는 ellar@2020contoso.com (시나리오 전자 메일 인증 방법에 도움이 될 수 있음). 

- **가장**: 보낸 사람이 대상 도메인 또는 사용자 이름과 같은 시각적으로 유사 하거나 눈에 보이는 메일을 받은 위치입니다. 여기에서 잘못 된 행위자를 지정 하 여 특정 사용자 이름에 모방 하거나 pretends를 대상 도메인에서 메일을 보낼 수 있습니다. Pretense 도메인은 ellar @ 2020 | itware 이며, 여기에는 ellαr @ 2020litware .com (도메인 및 사용자 가장을 확인 하기 위해 도메인 및 사용자 이름에 자세히 나와 있습니다.)가 있습니다.

EOP에 Office 365 ATP 구독을 추가한 경우에는 다음 구성을 설정 해야 합니다.

|보안 기능 이름  |권장 |업그레이드  |설명  |
|---------|---------|---------|---------|
|고급 피싱 임계값을 다음으로 설정 | 2 | 1-4 | - |
|가장 방지 된 보호 사용 | 예 | 예 | - |
|가장 된 정책에서 사서함 인텔리전스 사용 | 예 | 예 | - |
|사서함 인텔리전스 기반 가장 보호 사용 | 예 | 예 | - |
|도메인 가장 작업은 | JMF | 격리 | - |
|사용자 가장 작업은 | JMF | Qur앤틸리스 | - |
|사서함 인텔리전스 기반 가장 보호 작업은 |설명은  |JMF | - |

### <a name="safe-links-and-safe-attachments"></a>안전한 링크 및 안전한 첨부 파일

 ATP에는 유해한 첨부 파일이 있는 전자 메일이 배달 되지 않도록 하 고 사용자가 잠재적으로 안전 하지 않은 Url로 클릭 하 고 이동할 수 없도록 하는 안전한 첨부 파일 및 안전한 링크 정책이 포함 되어 있습니다.

#### <a name="safe-links"></a>안전한 링크

|보안 기능 이름  |권장 |업그레이드  |설명  |
|---------|---------|---------|---------|
|ATP 안전한 링크는 사용자 클릭에 대 한 응답을 추적 해야 합니다. |예 |예 |- |
|Office 응용 프로그램에 대해 ATP 안전한 링크를 사용 하도록 설정 해야 합니다. |예 |예 |- |
|ATP 안전한 링크는 도메인 내에서 사용 하도록 설정 해야 합니다. |예 |예 |- |
|ATP Safe 링크는 의심 스러운 링크 및 파일을 가리키는 링크에 대해 실시간 URL 검색을 적용 해야 합니다. |예 |예 |- |
|ATP Safe 링크는 메시지를 배달 하기 전에 URL 검색이 완료 될 때까지 기다려야 합니다. |예 |예 |- |
<!--
|URLs to block | | | |
|URLs not to wrap | | | |-->

#### <a name="safe-attachments"></a>안전한 첨부 파일

|보안 기능 이름  |권장 |업그레이드  |설명  |
|---------|---------|---------|---------|
|ATP 안전한 첨부 파일 정책 작업을 수행 해야 함 |격리 |격리 |- |
|ATP 보호는 OneDrive, SharePoint 및 팀에서 사용 하도록 설정 해야 합니다. |예 |예 |- |
<!--
|Allowed file hashes | | | |
|Blocked file hashes | | | |
-->

## <a name="miscellaneous-settings"></a>기타 설정

이러한 설정은 위의 특정 범주에 적합 하지 않을 수도 있는 다양 한 기능을 포함 합니다. 여기 에서도 1 일부 설정을 찾을 수 있습니다.

보안 기능 이름  |권장 |업그레이드  |설명  |
|---------|---------|---------|---------|
|SPF 레코드 만들기 |예 |예 |- |
|도메인에 대해 DKIM 서명 구성 |예 |예 |- |
|거부 또는 격리 작업을 사용 하 여 도메인 기반 메시지 보고 및 적합성 (DMARC) 구현 |동작 = 없음 |동작 = 거부 | |
|보고서 메시지 추가 기능을 배포 하 여 최종 사용자가 의심 스러운 전자 메일 보고 기능을 개선 합니다. |예 |예 |- |
|맬웨어 및 스팸 보고서 예약 |예 |예 |- |
|외부 도메인에 대 한 자동 fowarding 허용 하거나 모니터링 해야 합니다. |- |예 |- |
|통합 감사를 사용 하도록 설정 해야 함 |예 |예 |- |
|필요한 경우 IMAP를 사용 하지 않도록 설정 해야 합니다. |- |있지 |- |
|필요 하지 않은 경우 POP를 사용 하지 않도록 설정 해야 합니다. |- |있지 |- |
|응용 프로그램에 필요 하지 않은 경우 SMTP 인증 된 전송을 해제 해야 합니다. |- |있지 |- |
|EWS를 사용 하지 않도록 설정 해야 합니다. |- |있지 |- |
|PowerShell |- |있지 |- |
|보낸 사람 정책 프레임 워크에서 하드 오류를 구성 합니다. |-모두 |-모두 |- |
|가능한 경우 위장 인텔리전스를 사용 하 여 보낸 사람에 게 허용 목록 |예 |예 |- |
|DBEB (디렉터리 기반 Edge 차단) |사용 |사용 |도메인 유형 = 신뢰할 수 있음 |
