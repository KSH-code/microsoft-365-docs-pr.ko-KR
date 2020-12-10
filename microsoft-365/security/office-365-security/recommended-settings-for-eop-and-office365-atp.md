---
title: Office 365 보안 설정, 권장 사항, 보낸 사람 정책 프레임워크, 도메인 기반 메시지 보고 및 적합성, DomainKeys 식별 메일, 단계, 작동 방식, 보안 기준, EOP에 대한 기준, Office 365용 Defender 설정, Office 365용 Defender 설정, EOP 설정, Office 365용 Defender 구성, EOP 구성, EOP, 보안 구성
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: ''
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Office 365 보안 설정에 대한 EOP(Exchange Online Protection) 및 Defender에 대한 모범 사례는 무엇입니까? 표준 보호를 위한 현재 권장 사항은 무엇입니까? 더 엄격하게 사용하려는 경우 어떤 것을 사용해야 하나요? 또한 Office 365용 Defender를 사용하는 경우 어떤 추가 기능을 얻을 수 있나요?
ms.openlocfilehash: 192e37a1a9a373f7b6712600bc3c81189f7c51ad
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615963"
---
# <a name="recommended-settings-for-eop-and-microsoft-defender-for-office-365-security"></a>EOP 및 Office 365용 Microsoft Defender 보안에 대한 권장 설정

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**EOP(Exchange Online** Protection)는 Microsoft 365 구독에 대한 보안의 핵심으로, 악의적인 전자 메일이 직원의 받은 편지함으로 도달하지 못하게 합니다. 하지만 매일 새로운 더욱 정교한 공격이 나오고 있는 경우 향상된 보호가 필요한 경우가 종종 있습니다. **Office 365용 Microsoft Defender** 계획 1 또는 계획 2에는 관리자에게 더 많은 보안, 제어 및 조사 계층을 제공 하는 추가 기능이 포함되어 있습니다.

보안 관리자가 보안 설정을 사용자 지정할 수 있도록 하지만 EOP와 Office 365용 Microsoft Defender에는 표준 및 엄격의 두 가지 보안 수준이 **있습니다.**  각 고객의 환경과 요구는 서로 다르지만 이러한 수준의 필터링을 통해 대부분의 상황에서 원치 않는 메일이 직원의 받은 편지함으로 전달되지 않도록 방지할 수 있습니다.

사용자에게 표준 또는 엄격 설정을 자동으로 적용하려면 EOP 및 [Office 365용 Microsoft Defender의](preset-security-policies.md)미리 설정 보안 정책을 참조하세요.

> [!NOTE]
> 필터링이 제대로 작동하려면 사서함에서 정크 메일 규칙을 사용하도록 설정해야 합니다. 기본적으로 사용하도록 설정되어 있지만 필터링이 작동하지 않는지 확인해야 합니다. 자세한 내용은 [Office 365에서 Exchange Online 사서함에 대한 정크 메일 설정 구성하기](configure-junk-email-settings-on-exo-mailboxes.md)를 참조하세요.

이 문서에서는 기본 설정과 사용자를 보호하는 데 도움이 되는 권장 표준 및 엄격 설정에 대해 설명합니다.

> [!TIP]
> PowerShell용 Office 365 ORCA(Advanced Threat Protection 권장 구성 분석기) 모듈은 (관리자)이 이러한 설정의 현재 값을 찾는 데 도움을 줄 수 있습니다. 특히 **Get-ORCAReport** cmdlet은 스팸 방지, 피싱 방지 및 기타 메시지 예방조치 설정에 대한 평가를 생성합니다. ORCA 모듈은 에서 다운로드할 수 <https://www.powershellgallery.com/packages/ORCA/> 있습니다.

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>EOP의 스팸 방지, 맬웨어 방지 및 피싱 방지 보호 기능

스팸 방지, 맬웨어 방지 및 피싱 방지는 관리자가 구성할 수 있는 EOP 기능입니다. 다음과 같은 표준 또는 엄격 구성을 권장합니다.

### <a name="eop-anti-spam-policy-settings"></a>EOP 스팸 방지 정책 설정

스팸 방지 정책을 만들고 구성하는 내용은 [Office 365에서](configure-your-spam-filter-policies.md)스팸 방지 정책 구성을 참조합니다.

****

|보안 기능 이름|기본|Standard|Strict|댓글|
|---|:---:|:---:|:---:|---|
|**스팸** 검색 작업 <p> _SpamAction_|**정크 메일 폴더로 메시지 이동** <p> `MoveToJmf`|**정크 메일 폴더로 메시지 이동** <p> `MoveToJmf`|**메시지에 대한 검소리** <p> `Quarantine`||
|**높은 신뢰도 스팸** 검색 작업 <p> _HighConfidenceSpamAction_|**정크 메일 폴더로 메시지 이동** <p> `MoveToJmf`|**메시지에 대한 검소리** <p> `Quarantine`|**메시지에 대한 검소리** <p> `Quarantine`||
|**피싱 전자 메일** 검색 작업 <p> _PhishSpamAction_|**정크 메일 폴더로 메시지 이동** <p> `MoveToJmf`|**메시지에 대한 검소리** <p> `Quarantine`|**메시지에 대한 검소리** <p> `Quarantine`||
|**높은 신뢰도 피싱 전자 메일** 검색 작업 <p> _HighConfidencePhishAction_|**메시지에 대한 검소리** <p> `Quarantine`|**메시지에 대한 검소리** <p> `Quarantine`|**메시지에 대한 검소리** <p> `Quarantine`||
|**대량 전자 메일** 검색 작업 <p> _BulkSpamAction_|**정크 메일 폴더로 메시지 이동** <p> `MoveToJmf`|**정크 메일 폴더로 메시지 이동** <p> `MoveToJmf`|**메시지에 대한 검소리** <p> `Quarantine`||
|대량 전자 메일 임계값 <p> _BulkThreshold_|7 |6 |4 |자세한 내용은 [Office 365의 BCL(대량 불만 수준)을 참조합니다.](bulk-complaint-level-values.md)|
|보존 기간 <p> _QuarantineRetentionPeriod_|15일|30일|30일||
|**보안 팁** <p> _InlineSafetyTipsEnabled_|켜짐 <p> `$true`|켜짐 <p> `$true`|켜짐 <p> `$true`||
|허용된 보낸 사람 <p> _AllowedSenders_|없음|없음|없음||
|허용된 보낸 사람 도메인 <p> _AllowedSenderDomains_|없음|없음|없음|허용된 보낸 사람 목록에 도메인을 추가하는 것은 매우 좋지 않습니다. 공격자는 다른 경우 필터링되는 전자 메일을 보낼 수 있습니다. <p> 스팸 [](learn-about-spoof-intelligence.md) 방지 설정 페이지의 보안 & 준수 센터에서  스푸핑 인텔리전스를 사용하여 조직의 전자 메일 도메인에서 보낸 사람 전자 메일 주소를 스푸핑하거나 외부 도메인의 보낸 사람 전자 메일 주소를 스푸핑하는 모든 보낸 사람 검토|
|수신 차단된 보낸 사람 <p> _BlockedSenders_|없음|없음|없음||
|차단된 보낸 사람 도메인 <p> _BlockedSenderDomains_|없음|없음|없음||
|**최종 사용자 스팸 알림 사용** <p> _EnableEndUserSpamNotifications_|사용 안 함 <p> `$false`|사용 <p> `$true`|사용 <p> `$true`||
|**최종 사용자 스팸 알림 보내기(일)** <p> _EndUserSpamNotificationFrequency_|3일|3일|3일||
|**스팸 ZAP** <p> _SpamZapEnabled_|사용 <p> `$true`|사용 <p> `$true`|사용 <p> `$true`||
|**피싱 ZAP** <p> _PhishZapEnabled_|사용 <p> `$true`|사용 <p> `$true`|사용 <p> `$true`||
|_MarkAsSpamBulkMail_|켜짐|켜짐|켜짐|이 설정은 PowerShell에서만 사용할 수 있습니다.|
|

스팸 방지 정책에는 사용되지 않습니다. 이러한 기능의 정가 하한에 대한 타임라인에 대한 자세한 내용은 이 문서 외부에 전달될 것입니다.

표준 수준과 Strict 수준  모두에  대해 이러한 ASF 설정을 **해제하는 것이** 좋습니다. ASF 설정에 대한 자세한 내용은 [Office 365의 ASF(고급](advanced-spam-filtering-asf-options.md)스팸 필터) 설정을 참조하세요.

****

|보안 기능 이름|댓글|
|---|---|
|**원격 사이트에 대한** 이미지 _링크(IncreaseScoreWithImageLinks)_||
|**URL의 숫자 IP** 주소(IncreaseScoreWithNumericIps)||
|**다른 포트로 UL** _리디렉션(IncreaseScoreWithRedirectToOtherPort)_||
|**.biz 또는 .info 웹 사이트의** URL(IncreaseScoreWithBizOrInfoUrls)||
|**빈** _메시지(MarkAsSpamEmptyMessages)_||
|**HTML의 JavaScript** 또는 _VBScript(MarkAsSpamJavaScriptInHtml)_||
|**HTML의 프레임 또는 IFrame** 태그(MarkAsSpamFramesInHtml)||
|**HTML의** 개체 태그(_MarkAsSpamObjectTagsInHtml)_||
|**HTML에 태그를** _Embed(MarkAsSpamEmbedTagsInHtml)_||
|**HTML의 양식** _태그(MarkAsSpamFormTagsInHtml)_||
|**HTML의 웹** _버그(MarkAsSpamWebBugsInHtml)_||
|**중요한 단어 목록** 적용(MarkAsSpamSensitiveWordList)||
|**SPF 레코드: 하드** _실패(MarkAsSpamSpfRecordHardFail)_||
|**조건부 보낸 사람 ID 필터링: 하드** _실패(MarkAsSpamFromAddressAuthFail)_||
|**NDR** 후방산자(MarkAsSpamNdrBackscatter)||
|

#### <a name="eop-outbound-spam-policy-settings"></a>EOP 아웃바운드 스팸 정책 설정

아웃바운드 스팸 정책을 만들고 구성하는 내용은 [Office 365에서](configure-the-outbound-spam-policy.md)아웃바운드 스팸 필터링 구성을 참조합니다.

서비스의 기본 전송 제한에 대한 자세한 내용은 보내기 [제한을 참조하세요.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)

****

|보안 기능 이름|기본|Standard|Strict|댓글|
|---|:---:|:---:|:---:|---|
|**사용자당 최대 받는 사람 수: 외부 시간 제한** <p> _RecipientLimitExternalPerHour_|0|500|400|기본값 0은 서비스 기본값을 사용하는 것입니다.|
|**사용자당 최대 받는 사람 수: 내부 시간 제한** <p> _RecipientLimitInternalPerHour_|0|1000|800|기본값 0은 서비스 기본값을 사용하는 것입니다.|
|**사용자당 최대 받는 사람 수: 일별 제한** <p> _RecipientLimitPerDay_|0|1000|800|기본값 0은 서비스 기본값을 사용하는 것입니다.|
|**사용자가 제한을 초과하는 경우의 작업** <p> _ActionWhenThresholdReached_|**사용자가 다음 날까지 메일을 보내지 못하도록 제한** <p> `BlockUserForToday`|**사용자가 메일을 보낼 수 있도록 제한** <p> `BlockUser`|**사용자가 메일을 보낼 수 있도록 제한** <p> `BlockUser`||
|

### <a name="eop-anti-malware-policy-settings"></a>EOP 맬웨어 방지 정책 설정

맬웨어 방지 정책을 만들고 구성하는 내용은 [Office 365에서 맬웨어](configure-anti-malware-policies.md)방지 정책 구성을 참조합니다.

****

|보안 기능 이름|기본|Standard|Strict|댓글|
|---|:---:|:---:|:---:|---|
|**받는 사람의 메시지가 각기 다른 경우 받는 사람에게 알리시겠습니까?** <p> _작업_|아니요 <p> _DeleteMessage_|아니요 <p> _DeleteMessage_|아니요 <p> _DeleteMessage_|맬웨어가 전자 메일 첨부 파일에서 감지된 경우 메시지는 고지되고 관리자만 릴리스할 수 있습니다.|
|**일반 첨부 파일 형식 필터** <p> _EnableFileFilter_|해제 <p> `$false`|켜짐 <p> `$true`|켜짐 <p> `$true`|이 설정은 첨부 파일 콘텐츠에 관계없이 파일 형식에 따라 실행 파일이 포함된 메시지를 검지합니다.|
|**맬웨어 제로 아워 자동 제거** <p> _ZapEnabled_|켜짐 <p> `$true`|켜짐 <p> `$true`|켜짐 <p> `$true`||
|**내부 보낸 사람에** 대해 알릴 수 없는 메시지 <p> _EnableInternalSenderNotifications_|사용 안 함 <p> `$false`|사용 안 함 <p> `$false`|사용 안 함 <p> `$false`||
|**외부 보낸 사람에** 대해 알릴 수 없는 메시지 <p> _EnableExternalSenderNotifications_|사용 안 함 <p> `$false`|사용 안 함 <p> `$false`|사용 안 함 <p> `$false`||
|

### <a name="eop-default-anti-phishing-policy-settings"></a>EOP 기본 피싱 방지 정책 설정

이러한 설정에 대한 자세한 내용은 [스푸핑 설정을 참조하세요.](set-up-anti-phishing-policies.md#spoof-settings) 이러한 설정을 구성하려면 EOP에서 피싱 방지 정책 [구성을 참조하세요.](configure-anti-phishing-policies-eop.md)

****

|보안 기능 이름|기본|Standard|Strict|댓글|
|---|:---:|:---:|:---:|---|
|**스푸핑 방지 보호 사용** <p> _EnableAntispoofEnforcement_|켜짐 <p> `$true`|켜짐 <p> `$true`|켜짐 <p> `$true`||
|**비인식 보낸 사람 사용** <p> _EnableUnauthenticatedSender_|켜짐 <p> `$true`|켜짐 <p> `$true`|켜짐 <p> `$true`|확인되지 않은 스푸핑된 보낸 사람에 대해 Outlook에서 보낸 사람 사진에 물음표(?)를 추가합니다. 자세한 내용은 피싱 방지 정책의 [스푸핑 설정을 참조하세요.](set-up-anti-phishing-policies.md)|
|**도메인을 스푸핑할 수 없는 사람이 전자 메일을 보낸 경우** <p> _AuthenticationFailAction_|**받는 사람의 정크 메일 폴더로 메시지 이동** <p> `MoveToJmf`|**받는 사람의 정크 메일 폴더로 메시지 이동** <p> `MoveToJmf`|**메시지 Quarantine the message** <p> `Quarantine`|이 설정은 스푸핑 인텔리전스에서 수신이 차단된 보낸 [사람에 적용됩니다.](learn-about-spoof-intelligence.md)|
|

## <a name="microsoft-defender-for-office-365-security"></a>Microsoft Defender for Office 365 보안

추가 보안 혜택은 Office 365용 Microsoft Defender 구독과 함께 제공합니다. 최신 뉴스 및 정보는 Office [365용 Defender의](whats-new-in-office-365-atp.md)새로운 소식을 볼 수 있습니다.

> [!IMPORTANT]
>
> - Microsoft Defender for Office 365의 기본 피싱 [](set-up-anti-phishing-policies.md#spoof-settings) 방지 정책은 모든 받는 사람에 대해 스푸핑 방지 및 사서함 인텔리전스를 제공합니다. 그러나 사용 가능한 [](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 다른 가장 보호 기능 및 [고급](#advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 설정은 기본 정책에서 구성되거나 사용되지 않습니다. 모든 보호 기능을 사용하도록 설정하려면 기본 피싱 방지 정책을 수정하거나 추가 피싱 방지 정책을 만들 수 있습니다.
>
> - 조직의 모든 받는 사람을 자동으로 보호하는 기본 안전 링크 정책 또는 안전 첨부 파일 정책은 없습니다. 보호 기능을 사용하려면 하나 이상의 안전 링크 정책 및 안전 첨부 파일 정책을 만들어야 합니다.
>
> - [SharePoint, OneDrive 및 Microsoft Teams](atp-for-spo-odb-and-teams.md) 보호 및 [안전한](safe-docs.md) 문서 보호를 위한 ATP는 안전한 링크 정책에 종속되는 것이 없습니다.

구독에 Microsoft Defender for Office 365가 포함되어 있는 경우 또는 Office 365용 Defender를 추가 기능으로 구입한 경우 다음 표준 또는 Strict 구성을 설정하세요.

### <a name="anti-phishing-policy-settings-in-microsoft-defender-for-office-365"></a>Office 365용 Microsoft Defender의 피싱 방지 정책 설정

EOP 고객은 앞서 설명한 기본적인 피싱 방지 기능을 제공하지만 Office 365용 Microsoft Defender에는 공격을 방지, 감지 및 수정하는 데 도움이 되는 추가 기능과 제어 기능이 포함되어 있습니다. 이러한 정책을 만들고 구성하기 위해 [Office 365용 Defender에서](configure-atp-anti-phishing-policies.md)피싱 방지 정책 구성을 참조합니다.

#### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365의 피싱 방지 정책의 가장 설정

이러한 설정에 대한 자세한 내용은 [Microsoft Defender for Office 365의](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)피싱 방지 정책에서 가장 설정을 참조하세요. 이러한 설정을 구성하려면 [Office 365용 Defender에서](configure-atp-anti-phishing-policies.md)피싱 방지 정책 구성을 참조하세요.

****

|보안 기능 이름|기본|Standard|Strict|댓글|
|---|:---:|:---:|:---:|---|
|보호된 사용자: **보호할 사용자 추가** <p> _EnableTargetedUserProtection_ <p> _TargetedUsersToProtect_|해제 <p> `$false` <p> 없음|켜짐 <p> `$true` <p> \<list of users\>|켜짐 <p> `$true` <p> \<list of users\>|조직에 따라 주요 역할에 사용자(메시지 보낸 사람)를 추가하는 것이 좋습니다. 내부적으로 보호된 보낸 사람이 CEO, CFO 및 기타 고위 리더일 수 있습니다. 외부적으로 보호된 보낸 사람에는 평의회 구성원이나 이사진이 포함되어 있을 수 있습니다.|
|보호된 도메인: **소유한 도메인 자동 포함** <p> _EnableOrganizationDomainsProtection_|해제 <p> `$false`|켜짐 <p> `$true`|켜짐 <p> `$true`||
|보호된 도메인: **사용자 지정 도메인 포함** <p> _EnableTargetedDomainsProtection_ <p> _TargetedDomainsToProtect_|해제 <p> `$false` <p> 없음|켜짐 <p> `$true` <p> \<list of domains\>|켜짐 <p> `$true` <p> \<list of domains\>|조직에 따라 소유하지 않는 도메인(보낸 사람 도메인)을 추가하는 것이 되지만 자주 상호 작용합니다.|
|보호된 사용자: **가장된** 사용자가 전자 메일을 보낸 경우 <p> _TargetedUserProtectionAction_|**아무 작업도 적용하지 않습니다.** <p> `NoAction`|**메시지 Quarantine the message** <p> `Quarantine`|**메시지 Quarantine the message** <p> `Quarantine`||
|보호된 도메인: **가장된** 도메인에서 전자 메일을 보낸 경우 <p> _TargetedDomainProtectionAction_|**아무 작업도 적용하지 않습니다.** <p> `NoAction`|**메시지 Quarantine the message** <p> `Quarantine`|**메시지 Quarantine the message** <p> `Quarantine`||
|**가장된 사용자를 위한 팁 표시** <p> _EnableSimilarUsersSafetyTips_|해제 <p> `$false`|켜짐 <p> `$true`|켜짐 <p> `$true`||
|**가장된 도메인에 대한 팁 표시** <p> _EnableSimilarDomainsSafetyTips_|해제 <p> `$false`|켜짐 <p> `$true`|켜짐 <p> `$true`||
|**비정상적인 문자에 대한 팁 표시** <p> _EnableUnusualCharactersSafetyTips_|해제 <p> `$false`|켜짐 <p> `$true`|켜짐 <p> `$true`||
|**사서함 인텔리전스를 사용하도록 설정하나요?** <p> _EnableMailboxIntelligence_|켜짐 <p> `$true`|켜짐 <p> `$true`|켜짐 <p> `$true`||
|**사서함 인텔리전스 기반 가장 보호를 사용하도록 설정하나요?** <p> _EnableMailboxIntelligenceProtection_|해제 <p> `$false`|켜짐 <p> `$true`|켜짐 <p> `$true`||
|**사서함 인텔리전스로 보호된 가장된 사용자가 전자 메일을 보낸 경우** <p> _MailboxIntelligenceProtectionAction_|**아무 작업도 적용하지 않습니다.** <p> `NoAction`|**받는 사람의 정크 메일 폴더로 메시지 이동** <p> `MoveToJmf`|**메시지 Quarantine the message** <p> `Quarantine`||
|**신뢰할 수 있는 보낸 사람** <p> _ExcludedSenders_|없음|없음|없음|조직에 따라 다른 필터가 아니라 가장으로 인해 피싱으로 잘못 표시된 사용자를 추가하는 것이 좋습니다.|
|**신뢰할 수 있는 도메인** <p> _ExcludedDomains_|없음|없음|없음|조직에 따라 다른 필터가 아니라 가장으로 인해 피싱으로 잘못 표시된 도메인을 추가하는 것이 좋습니다.|
|

#### <a name="spoof-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365의 피싱 방지 정책의 스푸핑 설정

이러한 설정은 EOP의 스팸 방지 정책 설정에서 사용할 수 있는 [설정과 동일합니다.](#eop-anti-spam-policy-settings)

****

|보안 기능 이름|기본|Standard|Strict|댓글|
|---|---|---|---|---|
|**스푸핑 방지 보호 사용** <p> _EnableAntispoofEnforcement_|켜짐 <p> `$true`|켜짐 <p> `$true`|켜짐 <p> `$true`||
|**비인식 보낸 사람 사용** <p> _EnableUnauthenticatedSender_|켜짐 <p> `$true`|켜짐 <p> `$true`|켜짐 <p> `$true`|확인되지 않은 스푸핑된 보낸 사람에 대해 Outlook에서 보낸 사람 사진에 물음표(?)를 추가합니다. 자세한 내용은 피싱 방지 정책의 [스푸핑 설정을 참조하세요.](set-up-anti-phishing-policies.md)|
|**도메인을 스푸핑할 수 없는 사람이 전자 메일을 보낸 경우** <p> _AuthenticationFailAction_|**받는 사람의 정크 메일 폴더로 메시지 이동** <p> `MoveToJmf`|**받는 사람의 정크 메일 폴더로 메시지 이동** <p> `MoveToJmf`|**메시지 Quarantine the message** <p> `Quarantine`|이 설정은 스푸핑 인텔리전스에서 수신이 차단된 보낸 [사람에 적용됩니다.](learn-about-spoof-intelligence.md)|
|

#### <a name="advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365의 피싱 방지 정책의 고급 설정

이 설정에 대한 자세한 내용은 [Microsoft Defender for Office 365의](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)피싱 방지 정책에서 고급 피싱 임계값을 참조하세요. 이 설정을 구성하기 위해 [Office 365용 Defender에서](configure-atp-anti-phishing-policies.md)피싱 방지 정책 구성을 참조합니다.

****

|보안 기능 이름|기본|Standard|Strict|댓글|
|---|:---:|:---:|:---:|---|
|**고급 피싱 임계값** <p> _PhishThresholdLevel_|**1 - 표준** <p> `1`|**2 - 적극적** <p> `2`|**3 - 보다 적극적인** <p> `3`||
|

### <a name="safe-links-settings"></a>안전한 링크 설정

Office 365용 Defender의 안전한 링크에는 활성 안전 링크 정책에 포함된 모든 사용자에게 적용되는 전역 설정과 각 안전 링크 정책에 대한 설정이 포함되어 있습니다. 자세한 내용은 [Office 365용 Defender의 안전한 링크를 참조하세요.](atp-safe-links.md)

#### <a name="global-settings-for-safe-links"></a>안전한 링크에 대한 전역 설정

이러한 설정을 구성하려면 [Office 365용 Defender에서](configure-global-settings-for-safe-links.md)안전한 링크에 대한 전역 설정 구성을 참조하세요.

PowerShell에서는 이러한 설정에 [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365) cmdlet을 사용합니다.

****

|보안 기능 이름|기본|Standard|Strict|댓글|
|---|:---:|:---:|:---:|---|
|**안전한 링크 사용: Office 365 응용 프로그램** <p> _EnableSafeLinksForO365Clients_|켜짐 <p> `$true`|켜짐 <p> `$true`|켜짐 <p> `$true`|지원되는 Office 365 데스크톱 및 모바일(iOS 및 Android) 앱에서 안전한 링크를 사용하세요. 자세한 내용은 [Office 365](atp-safe-links.md#safe-links-settings-for-office-365-apps)앱에 대한 안전한 링크 설정을 참조하세요.|
|**사용자가 안전한 링크를 클릭하는 경우 추적하지 않습니다.** <p> _TrackClicks_|켜짐 <p> `$false`|해제 <p> `$true`|해제 <p> `$true`|이 설정을 _끄면(TrackClicks를_ 설정) 지원되는 Office 365 앱에서 사용자 클릭을 `$true` 추적합니다.|
|**사용자가 원래 URL에 대한 안전한 링크를 클릭할 수 없습니다.** <p> _AllowClickThrough_|켜짐 <p> `$false`|켜짐 <p> `$false`|켜짐 <p> `$false`|이 설정을 _켜면(AllowClickThrough를_ 설정) 지원되는 Office 365 앱에서 원래 URL을 클릭할 `$false` 수 없습니다.|
|

#### <a name="safe-links-policy-settings"></a>안전한 링크 정책 설정

이러한 설정을 구성하려면 [Office 365용 Microsoft Defender에서 안전한](set-up-atp-safe-links-policies.md)링크 정책 설정을 참조하세요.

PowerShell에서는 이러한 설정에 [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy) 및 [Set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy) cmdlet을 사용합니다.

> [!NOTE]
> 앞에서 설명한 대로 기본 안전 링크 정책은 없습니다. 기본 열의 값은 새로 만드는 안전 링크 정책의 기본값입니다.

****

|보안 기능 이름|기본|Standard|Strict|댓글|
|---|:---:|:---:|:---:|---|
|**메시지의 알 수 없는 악의적인 URL에 대한 작업 선택** <p> _IsEnabled_|해제 <p> `$false`|켜짐 <p> `$true`|켜짐 <p> `$true`||
|**Microsoft Teams 내에서 알 수 없는 URL 또는 잠재적으로 악의적인 URL에 대한 작업 선택** <p> _EnableSafeLinksForTeams_|해제 <p> `$false`|켜짐 <p> `$true`|켜짐 <p> `$true`||
|**파일을 지정하는 의심스러운 링크 및 링크에 대한 실시간 URL 검사 적용** <p> _ScanUrls_|해제 <p> `$false`|켜짐 <p> `$true`|켜짐 <p> `$true`||
|**URL 검색이 완료될 때까지 기다렸다가 메시지를 배달합니다.** <p> _DeliverMessageAfterScan_|해제 <p> `$false`|켜짐 <p> `$true`|켜짐 <p> `$true`||
|**조직 내에서 보낸 전자 메일 메시지에 안전한 링크 적용** <p> _EnableForInternalSenders_|해제 <p> `$false`|켜짐 <p> `$true`|켜짐 <p> `$true`||
|**사용자 클릭 추적 안 하도록 설정** <p> _DoNotTrackUserClicks_|해제 <p> `$false`|해제 <p> `$false`|해제 <p> `$false`|이 설정을 _끄면(DoNotTrackUserClicks를_ 설정) 사용자 `$false` 클릭을 추적합니다.|
|**사용자가 원래 URL을 클릭할 수 있도록 허용 안 하세요.** <p> _DoNotAllowClickThrough_|해제 <p> `$false`|켜짐 <p> `$true`|켜짐 <p> `$true`|이 설정을 _켜면(DoNotAllowClickThrough를_ 설정) 원래 URL을 클릭할 `$true` 수 없습니다.|
|

### <a name="safe-attachments-settings"></a>안전한 첨부 파일 설정

Microsoft Defender for Office 365의 안전 첨부 파일에는 안전 첨부 파일 정책과 관계가 없는 전역 설정과 각 안전 링크 정책에 대한 설정이 포함되어 있습니다. 자세한 내용은 [Office 365용 Defender의 안전 첨부 파일을 참조하세요.](atp-safe-attachments.md)

#### <a name="global-settings-for-safe-attachments"></a>안전한 첨부 파일에 대한 전역 설정

이러한 설정을 구성하려면 [Microsoft 365 E5에서](safe-docs.md) [SharePoint, OneDrive](turn-on-atp-for-spo-odb-and-teams.md) 및 Microsoft Teams 및 안전한 문서에 대한 ATP 켜기를 참조하세요.

PowerShell에서는 이러한 설정에 [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365) cmdlet을 사용합니다.

****

|보안 기능 이름|기본|Standard|Strict|댓글|
|---|:---:|:---:|:---:|---|
|**SharePoint, OneDrive 및 Microsoft Teams의 ATP 켜기** <p> _EnableATPForSPOTeamsODB_|켜짐 <p> `$true`|켜짐 <p> `$true`||
|**Office 클라이언트에 대해 안전한 문서 설정** <p> _EnableSafeDocs_|켜짐 <p> `$true`|켜짐 <p> `$true`|이 설정은 Microsoft 365 E5 또는 Microsoft 365 E5 보안 라이선스에서만 사용할 수 있습니다. 자세한 내용은 [Office 365용 Microsoft Defender의](safe-docs.md)안전한 문서를 참조하세요.|
|**안전한 문서에서 파일을 악성으로 식별한 경우에도 사용자가 보호된 보기를 클릭할 수 있도록 허용** <p> _AllowSafeDocsOpen_|해제 <p> `$false`|해제 <p> `$false`|이 설정은 안전한 문서와 관련이 있습니다.|
|

#### <a name="safe-attachments-policy-settings"></a>안전 첨부 파일 정책 설정

이러한 설정을 구성하려면 [Office 365용 Defender에서 안전](set-up-atp-safe-attachments-policies.md)첨부 파일 정책 설정을 참조하세요.

PowerShell에서는 이러한 설정에 [New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy) 및 [Set-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy) cmdlet을 사용합니다.

> [!NOTE]
> 앞에서 설명한 대로 기본 안전 첨부 파일 정책은 없습니다. 기본 열의 값은 새로 만드는 안전 첨부 파일 정책의 기본값입니다.

****

|보안 기능 이름|기본|Standard|Strict|댓글|
|---|:---:|:---:|:---:|---|
|**안전한 첨부 파일 알 수 없는 맬웨어 응답** <p> _작업_|차단 <p> `Block`|차단 <p> `Block`|차단 <p> `Block`||
|**검색 시 첨부 파일 리디렉션** : 리디렉션 **사용** <p> _리디렉션_ <p> _RedirectAddress_|끄고 전자 메일 주소를 지정하지 않습니다. <p> `$true` <p> 없음|을 사용하여 전자 메일 주소를 지정합니다. <p> `$true` <p> 전자 메일 주소|을 사용하여 전자 메일 주소를 지정합니다. <p> `$true` <p> 전자 메일 주소|검토를 위해 보안 관리자에게 메시지를 리디렉션합니다.|
|**첨부 파일에 대한 맬웨어 검색이 시간보다 멀거나 오류가 발생하는 경우 위의 선택을 적용합니다.** <p> _ActionOnError_|켜짐 <p> `$true`|켜짐 <p> `$true`|켜짐 <p> `$true`||
|

## <a name="related-articles"></a>관련 문서

- Exchange 메일 흐름 규칙(전송 규칙)에 대한 모범 사례를 **찾고 있습니까?** Exchange Online에서 메일 흐름 규칙을 구성하는 모범 [사례를 참조하세요.](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/configuration-best-practices)

- 관리자와 사용자는 분석을 위해 가음성(양호한 전자 메일)과 거짓 부정(잘못된 전자 메일 허용)을 Microsoft에 제출할 수 있습니다. 자세한 내용은 [Microsoft에 메시지와 파일 보고](report-junk-email-messages-to-microsoft.md)를 참조하세요.

- 다음 링크를 사용하여 [EOP](set-up-your-eop-service.md)서비스를 설정하고 Office  [365용 Microsoft Defender를](office-365-atp.md)구성하는 방법에 대한 정보를 제공합니다.  'Office[365의](protect-against-threats.md)위협으로부터 보호'의 유용한 방향을 잊지 마세요.

- **Windows에** 대한 보안 기준은 어디에서 얻을 수 [있나요?](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines) GPO/프레미스 옵션의 경우 보안 기준을 사용할 수 있으며, Intune 기반 보안을 위해 [Intune에서 Windows 10](https://docs.microsoft.com/intune/protect/security-baselines) 장치를 구성하는 데 보안 기준을 사용할 수 있습니다. 마지막으로 끝점용 Microsoft Defender와 Microsoft Intune 보안 기준 간의 비교는 [끝점용 Microsoft Defender와 Windows Intune](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines)보안 기준 비교에서 사용할 수 있습니다.
