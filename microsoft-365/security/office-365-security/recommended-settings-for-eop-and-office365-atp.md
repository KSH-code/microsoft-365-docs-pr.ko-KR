---
title: EOP 및 Office 365 ATP 보안 설정, 권장 사항, 보낸 사람 정책 프레임 워크, 도메인 기반 메시지 보고 및 적합성에 대 한 Microsoft 권장 사항, DomainKeys 식별 된 메일, 단계, 작업 방법, 보안 초기 계획, EOP, 초기 계획, 설치 ATP, 설치 EOP, ATP, 구성, 보안 구성
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: ''
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
description: EOP (Exchange Online Protection) 및 ATP (Advanced Threat Protection) 보안 설정에 대 한 모범 사례 표준 보호에 대 한 최신 권장 사항은 무엇 인가요? 보다 엄격한 기능을 사용 하려면 어떻게 해야 합니까? 또한 ATP (Advanced Threat Protection)를 사용 하는 경우에는 어떤 것을 얻게 됩니까?
ms.openlocfilehash: 542dce4d2abe9a40fcc5eef57502be5c37a34d57
ms.sourcegitcommit: 688d62a8c52e4fb0feb721bb92b535effc278f54
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2020
ms.locfileid: "45389848"
---
# <a name="recommended-settings-for-eop-and-office-365-atp-security"></a>EOP 및 Office 365 ATP 보안에 대 한 권장 설정

**EOP (Exchange Online Protection)** 는 Microsoft 365 구독의 보안 핵심으로, 악성 전자 메일이 직원의 받은 편지함에 도달 하지 못하도록 합니다. 하지만 매일 보다 정교한 공격이 새로 등장 하면서도 향상 된 보호 기능은 대개 필요 합니다. **Office 365 ATP (Advanced Threat Protection)** ATP 계획 1 또는 ATP 계획 2에는 관리자가 더 많은 보안, 제어 및 조사 계층을 제공 하는 추가 기능이 포함 되어 있습니다.

보안 관리자는 보안 설정을 사용자 지정할 수 있도록 하지만 EOP 및 Office 365 ATP에는 **표준** 및 **Strict**의 두 가지 보안 수준이 권장 됩니다. 각 고객의 환경과 요구 사항은 서로 다르지만, 이러한 수준의 메일 필터링 구성은 대부분의 상황에서 원치 않는 메일이 직원의 받은 편지함에 도달 하지 못하도록 방지 하는 데 도움이 됩니다.

사용자에 게 표준 또는 엄격한 설정을 자동으로 적용 하려면 [EOP 및 Office 365 ATP에서 미리 설정 된 보안 정책을](preset-security-policies.md)참조 하세요.

> [!IMPORTANT]
> 필터링이 제대로 작동 하려면 사서함에서 정크 메일 규칙을 사용 하도록 설정 해야 합니다. 이 기능은 기본적으로 사용 하도록 설정 되어 있지만 필터링이 작동 하지 않는 것 처럼 보이는 경우에는 확인 해야 합니다. 자세한 내용은 [Office 365에서 Exchange Online 사서함에 대한 정크 메일 설정 구성하기](configure-junk-email-settings-on-exo-mailboxes.md)를 참조하세요.

이 항목에서는 사용자를 보호 하기 위해 이러한 Microsoft 권장 설정에 대해 설명 합니다.

> [!TIP]
> 이러한 설정 중 일부를 결정 하는 데 도움이 되는 Office 365 Advanced Threat Protection 권장 구성 분석기 (ORCA) 라는 새로운 PowerShell 모듈이 있습니다. 테 넌 트에서 관리자 권한으로 실행 하는 경우 ORCAReport는 스팸 방지, 피싱 및 기타 메시지 바이러스 설정에 대 한 평가를 생성 하는 데 도움이 됩니다. 이 모듈은에서 다운로드할 수 있습니다 https://www.powershellgallery.com/packages/ORCA/ .

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>EOP의 스팸 방지, 맬웨어 방지 및 피싱 방지 보호 기능

스팸 방지, 맬웨어 방지 및 피싱 방지 기능은 관리자가 구성할 수 있는 EOP의 기능입니다. 다음 구성을 권장 합니다.

### <a name="eop-anti-spam-policy-settings"></a>EOP 스팸 방지 정책 설정

스팸 방지 정책을 만들고 구성 하려면 [Office 365에서 스팸 방지 정책 구성을](configure-your-spam-filter-policies.md)참조 하세요.

|보안 기능 이름|표준을|항등|댓글|
|---|---|---|---|
|**스팸** 검색 작업 <br/><br/> _SpamAction_|**정크 메일 폴더로 메시지 이동** <br/><br/> `MoveToJmf`|**메시지 격리** <br/><br/> `Quarantine`||
|**높은 정확도 스팸** 검색 작업 <br/><br/> _HighConfidenceSpamAction_|**메시지 격리** <br/><br/> `Quarantine`|**메시지 격리** <br/><br/> `Quarantine`||
|**피싱 전자 메일** 검색 작업 <br/><br/> _PhishSpamAction_|**메시지 격리** <br/><br/> `Quarantine`|**메시지 격리** <br/><br/> `Quarantine`||
|**높은 신뢰도 피싱 전자 메일** 검색 작업 <br/><br/> _HighConfidencePhishAction_|**메시지 격리** <br/><br/> `Quarantine`|**메시지 격리** <br/><br/> `Quarantine`||
|**대량 전자 메일** 검색 작업 <br/><br/> _대량 Spampaction_|**정크 메일 폴더로 메시지 이동** <br/><br/> `MoveToJmf`|**메시지 격리** <br/><br/> `Quarantine`||
|대량 전자 메일 임계값 <br/><br/> _대량 임계값_|6 |4 |기본값은 7 이지만이 값을 6으로 변경 하는 것이 좋습니다. 자세한 내용은 [Office 365의 BCL (대량 불만 수준)](bulk-complaint-level-values.md)을 참조 하세요.|
|격리 보존 기간 <br/><br/> _QuarantineRetentionPeriod_|30일|30일||
|**보안 팁** <br/><br/> _InlineSafetyTipsEnabled_|켜짐 <br/><br/> `$true`|켜짐 <br/><br/> `$true`||
|허용 된 보낸 사람 <br/><br/> _AllowedSenders 사람_|없음|없음||
|허용 된 보낸 사람 도메인 <br/><br/> _AllowedSenderDomains_|없음|없음|소유한 도메인 (허용 _도메인이_라고도 함)을 허용 된 보낸 사람 목록에 추가 하지 않아도 됩니다. 실제로는 잘못 된 행위자가 메일을 필터링 할 수 있는 기회를 만들기 때문에 높은 위험으로 간주 됩니다. **스팸 방지 설정** 페이지의 보안 & 준수 센터 [에서 스푸핑 관리자를 사용 하](learn-about-spoof-intelligence.md) 여 조직의 전자 메일 도메인에 있는 보낸 사람 전자 메일 주소를 위장 하거나 외부 도메인의 보낸 사람 전자 메일 주소를 위장 하는 모든 보낸 사람을 검토할 수 있습니다.|
|수신 거부 <br/><br/> _BlockedSenders_|없음|없음||
|차단할 보낸 사람 도메인 <br/><br/> _BlockedSenderDomains_|없음|없음||
|**최종 사용자 스팸 알림 사용** <br/><br/> _EnableEndUserSpamNotifications_|사용 <br/><br/> `$true`|사용 <br/><br/> `$true`||
|**다음 간격으로 최종 사용자 스팸 알림 보내기 (일)** <br/><br/> _EndUserSpamNotificationFrequency_|3 일|3 일||
|**스팸 ZAP** <br/><br/> _SpamZapEnabled_|사용 <br/><br/> `$true`|사용 <br/><br/> `$true`||
|**피싱 ZAP** <br/><br/> _PhishZapEnabled_|사용 <br/><br/> `$true`|사용 <br/><br/> `$true`||
|_MarkAsSpamBulkMail_|켜짐|켜짐|이 설정은 PowerShell 에서만 사용할 수 있습니다.|
|

스팸 방지 정책에는 더 이상 사용 되지 않는 여러 ASF (고급 스팸 필터) 설정이 있습니다. 이러한 기능의 감가 상각 일정에 대 한 자세한 내용은이 항목의 외부에서 제공 됩니다.

이러한 ASF 설정은 **표준** 및 **Strict** 수준에 대해 모두 **해제** 하는 것이 좋습니다. ASF 설정에 대 한 자세한 내용은 [Office 365의 asf (Advanced 스팸 필터) 설정을](advanced-spam-filtering-asf-options.md)참조 하십시오.

|보안 기능 이름|댓글|
|---|---|
|**원격 사이트에 대 한 이미지 링크** (_IncreaseScoreWithImageLinks_)||
|**URL의 숫자 IP 주소** (_IncreaseScoreWithNumericIps_)||
|**UL이 다른 포트로 리디렉션** (_IncreaseScoreWithRedirectToOtherPort_)||
|**-Biz 또는 IncreaseScoreWithBizOrInfoUrls (info websites)에 대 한 URL** _IncreaseScoreWithBizOrInfoUrls_||
|**빈 메시지** (_MarkAsSpamEmptyMessages_)||
|**JavaScript 또는 HTML의 VBScript** (_MarkAsSpamJavaScriptInHtml_)||
|**HTML의 Frame 또는 IFrame 태그** (_MarkAsSpamFramesInHtml_)||
|**HTML의 개체 태그** (_MarkAsSpamObjectTagsInHtml_)||
|**HTML로 태그 포함** (_MarkAsSpamEmbedTagsInHtml_)||
|**HTML의 양식 태그** (_MarkAsSpamFormTagsInHtml_)||
|**HTML의 웹 버그** (_MarkAsSpamWebBugsInHtml_)||
|**중요 한 단어 목록 적용** (_MarkAsSpamSensitiveWordList_)||
|**SPF 레코드: 하드 실패** (_MarkAsSpamSpfRecordHardFail_)||
|**조건부 보낸 사람 ID 필터링: 하드 실패** (_MarkAsSpamFromAddressAuthFail_)||
|**NDR 백 분산** (_MarkAsSpamNdrBackscatter_)||
|

#### <a name="eop-outbound-spam-policy-settings"></a>EOP 아웃 바운드 스팸 정책 설정

아웃 바운드 스팸 정책을 만들고 구성 하려면 [Office 365에서 아웃 바운드 스팸 필터링 구성을](configure-the-outbound-spam-policy.md)참조 하세요.

서비스의 기본 전송 제한에 대 한 자세한 내용은 [제한 보내기](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1) 를 참조 하십시오.

|보안 기능 이름|표준을|항등|댓글|
|---|---|---|---|
|**사용자 당 최대 받는 사람 수: 외부 시간 제한** <br/><br/> _RecipientLimitExternalPerHour_|500|400||
|**사용자 당 최대 받는 사람 수: 내부 시간 제한** <br/><br/> _RecipientLimitInternalPerHour_|1000|800||
|**사용자 당 최대 받는 사람 수: 일일 제한** <br/><br/> _RecipientLimitPerDay_|1000|800||
|**사용자가 제한을 초과 하는 경우의 동작** <br/><br/> _ActionWhenThresholdReached_|**사용자가 메일을 보낼 수 없도록 제한** <br/><br/> `BlockUser`|**사용자가 메일을 보낼 수 없도록 제한** <br/><br/> `BlockUser`||
|

### <a name="eop-anti-malware-policy-settings"></a>EOP 맬웨어 방지 정책 설정

맬웨어 방지 정책을 만들고 구성 하려면 [Office 365에서 맬웨어 방지 정책 구성을](configure-anti-malware-policies.md)참조 하세요.

|보안 기능 이름|표준을|항등|댓글|
|---|---|---|---|
|**메시지가 격리 된 경우 받는 사람에 게 알릴지 여부** <br/><br/> _작업_|아니요 <br/><br/> _DeleteMessage_|아니요 <br/><br/> _DeleteMessage_|전자 메일 첨부 파일에서 맬웨어가 검색 되 면 메시지가 격리 되며 관리자만 해제할 수 있습니다.|
|**일반 첨부 파일 형식 필터** <br/><br/> _EnableFileFilter_|켜짐 <br/><br/> `$true`|켜짐 <br/><br/> `$true`|이 설정은 첨부 파일 내용에 상관 없이 설정별 첨부 파일이 들어 있는 메시지의 형식을 설정 합니다.|
|**맬웨어 제로 시간 자동 삭제** <br/><br/> _ZapEnabled_|켜짐 <br/><br/> `$true`|켜짐 <br/><br/> `$true`||
|배달 되지 않은 메시지의 **내부 보낸 사람에 게 알림** <br/><br/> _EnableInternalSenderNotifications_|사용 안 함 <br/><br/> `$false`|사용 안 함 <br/><br/> `$false`||
|배달 되지 않은 메시지의 **외부 보낸 사람에 게 알림** <br/><br/> _EnableExternalSenderNotifications_|사용 안 함 <br/><br/> `$false`|사용 안 함 <br/><br/> `$false`||
|

### <a name="eop-default-anti-phishing-policy-settings"></a>EOP 기본 피싱 방지 정책 설정

이러한 설정에 대 한 자세한 내용은 [스푸핑 설정](set-up-anti-phishing-policies.md#spoof-settings)항목을 참조 하십시오. 이러한 설정을 구성 하려면 [EOP에서 피싱 방지 정책 구성을](configure-anti-phishing-policies-eop.md)참조 하십시오.

|보안 기능 이름|표준을|항등|댓글|
|---|---|---|---|
|**스푸핑 방지 보호 사용** <br/><br/> _EnableAntispoofEnforcement_|켜짐 <br/><br/> `$true`|켜짐 <br/><br/> `$true`||
|**인증 되지 않은 보낸 사람 사용** <br/><br/> _EnableUnauthenticatedSender_|켜짐 <br/><br/> `$true`|켜짐 <br/><br/> `$true`|알 수 없는 스푸핑된 보낸 사람에 대 한 Outlook의 보낸 사람 사진에 물음표 (?)를 추가 합니다. 자세한 내용은 [피싱 방지 정책에서 스푸핑 설정을](set-up-anti-phishing-policies.md)참조 하십시오.|
|**도메인을 스푸핑할 수 없는 사용자가 전자 메일을 보낸 경우** <br/><br/> _AuthenticationFailAction_|**받는 사람의 정크 메일 폴더로 메시지 이동** <br/><br/> `MoveToJmf`|**메시지 격리** <br/><br/> `Quarantine`|이 정보는 [스푸핑 인텔리전스](learn-about-spoof-intelligence.md)에서 수신 거부에 적용 됩니다.|
|

## <a name="office-365-advanced-threat-protection-security"></a>Office 365 Advanced Threat Protection 보안

추가 보안 이점은 Office 365의 ATP (Advanced Threat Protection) 구독에서 제공 됩니다. 최신 뉴스 및 정보에 대 한 [Office 365 ATP의 새로운 기능](whats-new-in-office-365-atp.md)을 확인할 수 있습니다.

Office 365 ATP에는 악의적인 첨부 파일이 있는 전자 메일이 배달 되지 않도록 하 고 사용자가 안전 하지 않을 수 있는 Url을 클릭 하지 못하도록 하기 위한 안전한 첨부 파일 및 안전한 링크 정책이 포함 되어 있습니다.

> [!IMPORTANT]
> 고급 피싱 방지는 Office 365 ATP 구독의 혜택 중 하나입니다. 기본적으로 사용 하도록 설정 되어 있지만 메일 필터링을 시작 하려면 먼저 하나 이상의 피싱 방지 정책을 구성 ***해야 합니다*** . 피싱 방지 정책을 구성 하지 않으면 사용자가 위험한 전자 메일에 노출 될 수 있습니다. Office 365 ATP 구독을 추가한 후에는 피싱 방지 정책을 구성 해야 합니다.

EOP에 Office 365 ATP 구독을 추가한 경우에는 다음 구성을 설정 합니다.

### <a name="office-atp-anti-phishing-policy-settings"></a>Office ATP 피싱 방지 정책 설정

EOP 고객은 앞에서 설명한 것 처럼 기본 피싱 방지를 제공 하지만 Office 365 ATP에는 공격을 방지, 감지 및 수정 하는 데 도움이 되는 다양 한 기능 및 제어가 포함 되어 있습니다. 이러한 정책을 만들고 구성 하려면 [Office 365에서 ATP 피싱 방지 정책 구성을](configure-atp-anti-phishing-policies.md)참조 하세요.

#### <a name="impersonation-settings-in-atp-anti-phishing-policies"></a>ATP 피싱 방지 정책의 가장 설정

이러한 설정에 대 한 자세한 내용은 [ATP 피싱 방지 정책에서 가장 설정을](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)참조 하십시오. 이러한 설정을 구성 하려면 [ATP 피싱 방지 정책 구성을](configure-atp-anti-phishing-policies.md)참조 하십시오.

|보안 기능 이름|표준을|항등|댓글|
|---|---|---|---|
|보호 된 사용자: **보호를 위해 사용자 추가** <br/><br/> _EnableTargetedUserProtection_ <br/><br/> _TargetedUsersToProtect_|켜짐 <br/><br/> `$true` <br/><br/> \<list of users\>|켜짐 <br/><br/> `$true` <br/><br/> \<list of users\>|조직에 따라 다르지만 주요 역할에 사용자를 추가 하는 것이 좋습니다. 내부적으로는 CEO, CFO 및 기타 선임 리더가 될 수 있습니다. 외부에는 council 구성원 또는 이사회의 보드가 포함 될 수 있습니다.|
|보호 된 도메인: **내가 소유한 도메인을 자동으로 포함** <br/><br/> _EnableOrganizationDomainsProtection_|켜짐 <br/><br/> `$true`|켜짐 <br/><br/> `$true`||
|보호 된 도메인: **사용자 지정 도메인 포함** <br/><br/> _EnableTargetedDomainsProtection_ <br/><br/> _TargetedDomainsToProtect_|켜짐 <br/><br/> `$true` <br/><br/> \<list of domains\>|켜짐 <br/><br/> `$true` <br/><br/> \<list of domains\>|조직에 따라 다르지만 사용자가 소유 하지 않은 경우에도 자주 상호 작용 하는 도메인을 추가 하는 것이 좋습니다.|
|보호 된 사용자: **가장 된 사용자가 전자 메일을 보낸 경우** <br/><br/> _TargetedUserProtectionAction_|**메시지 격리** <br/><br/> `Quarantine`|**메시지 격리** <br/><br/> `Quarantine`||
|보호 된 도메인: **가장 된 도메인에서 전자 메일을 보내는 경우** <br/><br/> _TargetedDomainProtectionAction_|**메시지 격리** <br/><br/> `Quarantine`|**메시지 격리** <br/><br/> `Quarantine`||
|**가장 한 사용자에 대 한 팁 표시** <br/><br/> _EnableSimilarUsersSafetyTips_|켜짐 <br/><br/> `$true`|켜짐 <br/><br/> `$true`||
|**가장 한 도메인에 대 한 팁 표시** <br/><br/> _EnableSimilarDomainsSafetyTips_|켜짐 <br/><br/> `$true`|켜짐 <br/><br/> `$true`||
|**비정상적 캐릭터에 대 한 팁 표시** <br/><br/> _EnableUnusualCharactersSafetyTips_|켜짐 <br/><br/> `$true`|켜짐 <br/><br/> `$true`||
|**사서함 인텔리전스 사용 가능 여부** <br/><br/> _EnableMailboxIntelligence_|켜짐 <br/><br/> `$true`|켜짐 <br/><br/> `$true`||
|**사서함 인텔리전스 기반 가장 보호를 사용 하도록 설정** <br/><br/> _EnableMailboxIntelligenceProtection_|켜짐 <br/><br/> `$true`|켜짐 <br/><br/> `$true`||
|**사서함 인텔리전스를 통해 보호 되는 가장 된 사용자가 전자 메일을 보낸 경우** <br/><br/> _MailboxIntelligenceProtectionAction_|**받는 사람의 정크 메일 폴더로 메시지 이동** <br/><br/> `MoveToJmf`|**메시지 격리** <br/><br/> `Quarantine`||
|**신뢰할 수 있는 보낸 사람** <br/><br/> _ExcludedSenders_|없음|없음|조직에 따라 다르지만, 가장을 제외 하 고 다른 필터를 제외 하 고는 피싱으로 표시 된 사용자를 추가 하는 것이 좋습니다.|
|**신뢰할 수 있는 도메인** <br/><br/> _ExcludedDomains_|없음|없음|조직에 따라 다르지만 가장을 제외 하 고는 피싱로 표시 된 도메인을 추가 하는 것이 좋습니다.|
|

#### <a name="spoof-settings-in-atp-anti-phishing-policies"></a>ATP 피싱 방지 정책의 스푸핑 설정

이러한 설정은 [EOP의 스팸 방지 정책 설정](#eop-anti-spam-policy-settings)에서 사용할 수 있는 설정과 동일 합니다.

|보안 기능 이름|표준을|항등|댓글|
|---|---|---|---|
|**스푸핑 방지 보호 사용** <br/><br/> _EnableAntispoofEnforcement_|켜짐 <br/><br/> `$true`|켜짐 <br/><br/> `$true`||
|**인증 되지 않은 보낸 사람 사용** <br/><br/> _EnableUnauthenticatedSender_|켜짐 <br/><br/> `$true`|켜짐 <br/><br/> `$true`|알 수 없는 스푸핑된 보낸 사람에 대 한 Outlook의 보낸 사람 사진에 물음표 (?)를 추가 합니다. 자세한 내용은 [피싱 방지 정책에서 스푸핑 설정을](set-up-anti-phishing-policies.md)참조 하십시오.|
|**도메인을 스푸핑할 수 없는 사용자가 전자 메일을 보낸 경우** <br/><br/> _AuthenticationFailAction_|**받는 사람의 정크 메일 폴더로 메시지 이동** <br/><br/> `MoveToJmf`|**메시지 격리** <br/><br/> `Quarantine`|이 정보는 [스푸핑 인텔리전스](learn-about-spoof-intelligence.md)에서 수신 거부에 적용 됩니다.|
|

#### <a name="advanced-settings-in-atp-anti-phishing-policies"></a>ATP 피싱 방지 정책의 고급 설정

이 설정에 대 한 자세한 내용은 [ATP 피싱 방지 정책에서 Advanced 피싱 임계값](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)을 참조 하십시오. 이 설정을 구성 하려면 [ATP 피싱 방지 정책 구성을](configure-atp-anti-phishing-policies.md)참조 하십시오.

|보안 기능 이름|표준을|항등|댓글|
|---|---|---|---|
|**고급 피싱 임계값** <br/><br/> _PhishThresholdLevel_|**2-적극적인** <br/><br/> `2`|**3-적극적인** <br/><br/> `3`||

### <a name="atp-safe-links-policy-settings"></a>ATP 안전한 링크 정책 설정

이러한 설정을 구성 하려면 [Office 365 ATP 안전한 링크 정책 설정](set-up-atp-safe-links-policies.md)을 참조 하십시오.

#### <a name="safe-links-policy-settings-in-the-default-policy-for-all-users"></a>모든 사용자에 대 한 기본 정책의 안전한 링크 정책 설정

**참고**: PowerShell에서는 이러한 설정에 대해 [AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365) cmdlet을 사용 합니다.

|보안 기능 이름|표준을|항등|댓글|
|---|---|---|---|
|**에서 안전한 링크 사용: Office 365 응용 프로그램** <br/><br/> _EnableSafeLinksForO365Clients_|켜짐 <br/><br/> `$true`|켜짐 <br/><br/> `$true`|Office 365 Apps, iOS 및 Android의 ATP 안전한 링크를 사용 합니다.|
|**사용자가 안전 링크를 클릭 하는 경우 추적 안 함** <br/><br/> _가을 클릭 하면_|해제 <br/><br/> `$true`|해제 <br/><br/> `$true`||
|**사용자가 원본 URL에 대 한 안전한 링크를 클릭 하는 것을 허용 하지 않음** <br/><br/> _AllowClickThrough 광고_|켜짐 <br/><br/> `$false`|켜짐 <br/><br/> `$false`||
|

#### <a name="safe-links-policy-settings-in-custom-policies-for-specific-users"></a>특정 사용자에 대 한 사용자 지정 정책의 안전한 링크 정책 설정

**참고**: PowerShell에서는 이러한 설정에 대해 [Get-safelinkspolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy) 및 [get-safelinkspolicy] (] cmdlet을 사용 https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy 합니다.

|보안 기능 이름|표준을|항등|댓글|
|---|---|---|---|
|**메시지에서 알 수 없는 잠재적 악성 Url에 대 한 작업 선택** <br/><br/> _IsEnabled_|켜짐 <br/><br/> `$true`|켜짐 <br/><br/> `$true`||
|**Microsoft 팀 내에서 알 수 없거나 잠재적으로 악성 Url에 대 한 작업 선택** <br/><br/> _EnableSafeLinksForTeams_|켜짐 <br/><br/> `$true`|켜짐 <br/><br/> `$true`||
|**의심 스러운 링크에 대 한 실시간 URL 검사 및 파일을 가리키는 링크를 적용 합니다.** <br/><br/> _ScanUrls_|켜짐 <br/><br/> `$true`|켜짐 <br/><br/> `$true`||
|**메시지를 배달 하기 전에 URL 검색이 완료 될 때까지 기다립니다.** <br/><br/> _배달 Messageafterscan_|켜짐 <br/><br/> `$true`|켜짐 <br/><br/> `$true`||
|**조직 내에서 전송 된 전자 메일 메시지에 안전한 링크 적용** <br/><br/> _EnableForInternalSenders 사람_|켜짐 <br/><br/> `$true`|켜짐 <br/><br/> `$true`||
|**사용자가 안전 링크를 클릭 하는 경우 추적 안 함** <br/><br/> _DoNotTrackUserClicks_|해제 <br/><br/> `$false`|해제 <br/><br/> `$false`|
|**사용자가 원본 URL에 대 한 안전한 링크를 클릭 하는 것을 허용 하지 않음** <br/><br/> _DoNotAllowClickThrough_|켜짐 <br/><br/> `$true`|켜짐 <br/><br/> `$true`||
|

### <a name="atp-safe-attachments-policy-settings"></a>ATP 안전한 첨부 파일 정책 설정

이러한 설정을 구성 하려면 [Office 365 ATP 안전 첨부 파일 정책을 설정](set-up-atp-safe-attachments-policies.md)합니다 .를 참조 하십시오.

#### <a name="safe-attachments-policy-settings-in-the-default-policy-for-all-users"></a>모든 사용자에 대 한 기본 정책의 안전한 첨부 파일 정책 설정

**참고**: PowerShell에서는 이러한 설정에 대해 [AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365) cmdlet을 사용 합니다.

|보안 기능 이름|표준을|항등|댓글|
|---|---|---|---|
|**SharePoint, OneDrive 및 Microsoft Teams의 ATP 켜기** <br/><br/> _EnableATPForSPOTeamsODB_|켜짐 <br/><br/> `$true`|켜짐 <br/><br/> `$true`||
|**Office 클라이언트에 대 한 안전 문서 설정**<bt/><br/> _EnableSafeDocs_|켜짐 <br/><br/> `$true`|켜짐 <br/><br/> `$true`||이 설정은 Microsoft 365 E5 또는 Microsoft 365 E5 보안 라이선스 에서만 사용할 수 있습니다. 자세한 내용은 [Office 365 Advanced Threat Protection의 안전한 문서](safe-docs.md)를 참조 하세요.|
|**안전한 문서에 악성 프로그램으로 확인 된 안전 문서가 있는 경우에도 제한 됨 보기를 클릭 하도록 허용**<bt/><br/> _AllowSafeDocsOpen_|해제 <br/><br/> `$false`|해제 <br/><br/> `$false`||
|

#### <a name="safe-attachments-policy-settings-in-custom-policies-for-specific-users"></a>특정 사용자에 대 한 사용자 지정 정책의 안전한 첨부 파일 정책 설정

**참고**: PowerShell에서는 이러한 설정에 대해 [get-safeattachmentpolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy) 및 [get-safeattachmentpolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy) cmdlet을 사용 합니다.

|보안 기능 이름|표준을|항등|댓글|
|---|---|---|---|
|**안전한 첨부 파일 알 수 없는 맬웨어 응답** <br/><br/> _작업_|정책의 <br/><br/> `Block`|정책의 <br/><br/> `Block`||
|**검색 시 첨부 파일 리디렉션** : **리디렉션 사용** <br/><br/> _리디렉션_ <br/><br/> _RedirectAddress_|전자 메일 주소를 지정 합니다. <br/><br/> `$true` <br/><br/> 전자 메일 주소|전자 메일 주소를 지정 합니다. <br/><br/> `$true` <br/><br/> 전자 메일 주소|검토를 위해 보안 관리자에 게 메시지를 리디렉션합니다.|
|**첨부 파일에 대 한 맬웨어 검사 시간이 초과 되거나 오류가 발생 하는 경우 위의 선택 사항을 적용 합니다.** <br/><br/> _ActionOnError_|켜짐 <br/><br/> `$true`|켜짐 <br/><br/> `$true`||
|

## <a name="related-topics"></a>관련 항목

- **Exchange 메일 흐름/Exchange 전송 규칙**에 대 한 모범 사례를 찾으십니까? 자세한 내용은 [이 문서](https://docs.microsoft.com/microsoft-365/security/office-365-security/best-practices-for-configuring-eop) 를 참조 하세요.

- 관리자 및 사용자는 가양성 (잘못 된 것으로 표시 된 좋은 전자 메일)과 거짓 네거티브 (잘못 된 전자 메일 허용)를 분석을 위해 Microsoft에 제출할 수 있습니다. 자세한 내용은 [Microsoft에 메시지와 파일 보고](report-junk-email-messages-to-microsoft.md)를 참조하세요.

- [EOP 서비스](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-your-eop-service)를 **설정** 하는 방법에 대 한 정보를 보려면 다음 링크를 사용 하 고, [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)을 **구성** 합니다. ('[Office 365의 위협 으로부터 보호](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)하는 방법에 대 한 유용한 지침은 참조 하세요.)

- GPO/온-프레미스 옵션 및 Intune 기반 [보안에 대](https://docs.microsoft.com/intune/protect/security-baselines)한 **Windows 용 보안 기준을** [여기](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines) 에서 찾을 수 있습니다. 마지막으로 Microsoft의 ATP (Advanced Threat Protection) 및 Windows Intune 보안 기준을 [여기](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines)에서 확인할 수 있습니다.
