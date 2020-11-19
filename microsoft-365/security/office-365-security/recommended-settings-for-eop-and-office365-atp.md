---
title: Microsoft의 EOP 및 Defender for Office 365 보안 설정, 권장 사항, 보낸 사람 정책 프레임 워크, 도메인 기반 메시지 보고 및 적합성, DomainKeys 식별 된 메일, 단계, 작업 방법, 보안 초기 계획, EOP의 초기 계획, office for a 365 Defender for office 365, set up EOP, Office 365 구성 EOP, 보안 구성
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
description: EOP (Exchange Online Protection) 및 Defender for Office 365 보안 설정에 대 한 모범 사례는 무엇 인가요? 표준 보호에 대 한 최신 권장 사항은 무엇 인가요? 보다 엄격한 기능을 사용 하려면 어떻게 해야 합니까? 또한 Office 365 용으로 Defender를 사용 하는 경우에는 어떤 것을 얻게 됩니까?
ms.openlocfilehash: af741e1af412d535c53beb83c36c0cbe3fcd617b
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357124"
---
# <a name="recommended-settings-for-eop-and-microsoft-defender-for-office-365-security"></a>EOP 및 Office 용 Microsoft Defender 365 보안에 대 한 권장 설정

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**EOP (Exchange Online Protection)** 는 Microsoft 365 구독의 보안 핵심으로, 악성 전자 메일이 직원의 받은 편지함에 도달 하지 못하도록 합니다. 하지만 매일 보다 정교한 공격이 새로 등장 하면서도 향상 된 보호 기능은 대개 필요 합니다. **Microsoft Defender For Office 365** 계획 1 또는 계획 2에는 관리자가 더 많은 보안, 제어 및 조사 계층을 제공 하는 추가 기능이 포함 되어 있습니다.

보안 관리자는 보안 설정을 사용자 지정 하는 데 사용할 수 있지만 EOP에는 두 가지 보안 수준인 Office 365 용 Microsoft Defender와 권장 되는 **표준** 및 **Strict** 가 있습니다. 각 고객의 환경과 요구 사항은 다르지만, 이러한 필터링 수준을 통해 대부분의 상황에서 원치 않는 메일이 직원의 받은 편지함에 도달 하는 것을 방지할 수 있습니다.

사용자에 게 표준 또는 엄격한 설정을 자동으로 적용 하려면 [미리 설정 된 보안 정책 EOP 및 Office 365 용 Microsoft Defender](preset-security-policies.md)를 참조 하세요.

> [!NOTE]
> 필터링이 제대로 작동 하려면 사서함에서 정크 메일 규칙을 사용 하도록 설정 해야 합니다. 이 기능은 기본적으로 사용 하도록 설정 되어 있지만 필터링이 작동 하지 않는 것 처럼 보이는 경우에는 확인 해야 합니다. 자세한 내용은 [Office 365에서 Exchange Online 사서함에 대한 정크 메일 설정 구성하기](configure-junk-email-settings-on-exo-mailboxes.md)를 참조하세요.

이 문서에서는 기본 설정 및 사용자를 보호 하기 위한 권장 표준 및 엄격한 설정에 대해서도 설명 합니다.

> [!TIP]
> PowerShell 용 Office 365 Advanced Threat Protection 권장 구성 분석기 (ORCA) 모듈은 관리자가 이러한 설정의 현재 값을 찾는 데 도움이 될 수 있습니다. 특히 **ORCAReport** cmdlet은 스팸 방지, 피싱 방지 및 기타 메시지 바이러스 설정에 대 한 평가를 생성 합니다. 에서 ORCA 모듈을 다운로드할 수 있습니다 <https://www.powershellgallery.com/packages/ORCA/> .

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>EOP의 스팸 방지, 맬웨어 방지 및 피싱 방지 보호 기능

스팸 방지, 맬웨어 방지 및 피싱 방지는 관리자가 구성할 수 있는 EOP 기능입니다. 다음 표준 또는 엄격한 구성을 권장 합니다.

### <a name="eop-anti-spam-policy-settings"></a>EOP 스팸 방지 정책 설정

스팸 방지 정책을 만들고 구성 하려면 [Office 365에서 스팸 방지 정책 구성을](configure-your-spam-filter-policies.md)참조 하세요.

****

|보안 기능 이름|기본|Standard|항등|댓글|
|---|:---:|:---:|:---:|---|
|**스팸** 검색 작업 <p> _SpamAction_|**정크 메일 폴더로 메시지 이동** <p> `MoveToJmf`|**정크 메일 폴더로 메시지 이동** <p> `MoveToJmf`|**메시지 격리** <p> `Quarantine`||
|**높은 정확도 스팸** 검색 작업 <p> _HighConfidenceSpamAction_|**정크 메일 폴더로 메시지 이동** <p> `MoveToJmf`|**메시지 격리** <p> `Quarantine`|**메시지 격리** <p> `Quarantine`||
|**피싱 전자 메일** 검색 작업 <p> _PhishSpamAction_|**정크 메일 폴더로 메시지 이동** <p> `MoveToJmf`|**메시지 격리** <p> `Quarantine`|**메시지 격리** <p> `Quarantine`||
|**높은 신뢰도 피싱 전자 메일** 검색 작업 <p> _HighConfidencePhishAction_|**메시지 격리** <p> `Quarantine`|**메시지 격리** <p> `Quarantine`|**메시지 격리** <p> `Quarantine`||
|**대량 전자 메일** 검색 작업 <p> _대량 Spampaction_|**정크 메일 폴더로 메시지 이동** <p> `MoveToJmf`|**정크 메일 폴더로 메시지 이동** <p> `MoveToJmf`|**메시지 격리** <p> `Quarantine`||
|대량 전자 메일 임계값 <p> _대량 임계값_|7 |6 |4 |자세한 내용은 [Office 365의 BCL (대량 불만 수준)](bulk-complaint-level-values.md)을 참조 하세요.|
|격리 보존 기간 <p> _QuarantineRetentionPeriod_|15일|30일|30일||
|**보안 팁** <p> _InlineSafetyTipsEnabled_|켜짐 <p> `$true`|켜짐 <p> `$true`|켜짐 <p> `$true`||
|허용 된 보낸 사람 <p> _AllowedSenders 사람_|없음|없음|없음||
|허용 된 보낸 사람 도메인 <p> _AllowedSenderDomains_|없음|없음|없음|허용 된 보낸 사람 목록에 도메인을 추가 하는 것은 매우 좋지 않습니다. 공격자는 필터링 되지 않는 전자 메일을 보낼 수 있습니다. <p> **스팸 방지 설정** 페이지의 보안 & 준수 센터 [에서 스푸핑 관리자를 사용 하](learn-about-spoof-intelligence.md) 여 조직의 전자 메일 도메인에 있는 보낸 사람 전자 메일 주소를 위장 하거나 외부 도메인의 보낸 사람 전자 메일 주소를 위장 하는 모든 보낸 사람을 검토할 수 있습니다.|
|수신 거부 <p> _BlockedSenders_|없음|없음|없음||
|차단할 보낸 사람 도메인 <p> _BlockedSenderDomains_|없음|없음|없음||
|**최종 사용자 스팸 알림 사용** <p> _EnableEndUserSpamNotifications_|사용 안 함 <p> `$false`|사용 <p> `$true`|사용 <p> `$true`||
|**다음 간격으로 최종 사용자 스팸 알림 보내기 (일)** <p> _EndUserSpamNotificationFrequency_|3 일|3 일|3 일||
|**스팸 ZAP** <p> _SpamZapEnabled_|사용 <p> `$true`|사용 <p> `$true`|사용 <p> `$true`||
|**피싱 ZAP** <p> _PhishZapEnabled_|사용 <p> `$true`|사용 <p> `$true`|사용 <p> `$true`||
|_MarkAsSpamBulkMail_|켜짐|켜짐|켜짐|이 설정은 PowerShell 에서만 사용할 수 있습니다.|
|

스팸 방지 정책에는 더 이상 사용 되지 않는 여러 ASF (고급 스팸 필터) 설정이 있습니다. 이러한 기능의 감가 상각 일정에 대 한 자세한 내용은이 문서에서 다루지 않습니다.

이러한 ASF 설정은 **표준** 및 **Strict** 수준에 대해 모두 **해제** 하는 것이 좋습니다. ASF 설정에 대 한 자세한 내용은 [Office 365의 asf (Advanced 스팸 필터) 설정을](advanced-spam-filtering-asf-options.md)참조 하십시오.

****

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

서비스의 기본 전송 제한에 대 한 자세한 내용은 [제한 보내기를](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)참조 하십시오.

****

|보안 기능 이름|기본|Standard|항등|댓글|
|---|:---:|:---:|:---:|---|
|**사용자 당 최대 받는 사람 수: 외부 시간 제한** <p> _RecipientLimitExternalPerHour_|개|500|400|기본값 0은 서비스 기본값을 사용 함을 의미 합니다.|
|**사용자 당 최대 받는 사람 수: 내부 시간 제한** <p> _RecipientLimitInternalPerHour_|개|1000|800|기본값 0은 서비스 기본값을 사용 함을 의미 합니다.|
|**사용자 당 최대 받는 사람 수: 일일 제한** <p> _RecipientLimitPerDay_|개|1000|800|기본값 0은 서비스 기본값을 사용 함을 의미 합니다.|
|**사용자가 제한을 초과 하는 경우의 동작** <p> _ActionWhenThresholdReached_|**다음 날까지 사용자가 메일을 보낼 수 없도록 제한** <p> `BlockUserForToday`|**사용자가 메일을 보낼 수 없도록 제한** <p> `BlockUser`|**사용자가 메일을 보낼 수 없도록 제한** <p> `BlockUser`||
|

### <a name="eop-anti-malware-policy-settings"></a>EOP 맬웨어 방지 정책 설정

맬웨어 방지 정책을 만들고 구성 하려면 [Office 365에서 맬웨어 방지 정책 구성을](configure-anti-malware-policies.md)참조 하세요.

****

|보안 기능 이름|기본|Standard|항등|댓글|
|---|:---:|:---:|:---:|---|
|**메시지가 격리 된 경우 받는 사람에 게 알릴지 여부** <p> _작업_|아니요 <p> _DeleteMessage_|아니요 <p> _DeleteMessage_|아니요 <p> _DeleteMessage_|전자 메일 첨부 파일에서 맬웨어가 검색 되 면 메시지가 격리 되며 관리자만 해제할 수 있습니다.|
|**일반 첨부 파일 형식 필터** <p> _EnableFileFilter_|해제 <p> `$false`|켜짐 <p> `$true`|켜짐 <p> `$true`|이 설정은 첨부 파일 내용에 상관 없이 설정별 첨부 파일이 들어 있는 메시지의 형식을 설정 합니다.|
|**맬웨어 제로 시간 자동 삭제** <p> _ZapEnabled_|켜짐 <p> `$true`|켜짐 <p> `$true`|켜짐 <p> `$true`||
|배달 되지 않은 메시지의 **내부 보낸 사람에 게 알림** <p> _EnableInternalSenderNotifications_|사용 안 함 <p> `$false`|사용 안 함 <p> `$false`|사용 안 함 <p> `$false`||
|배달 되지 않은 메시지의 **외부 보낸 사람에 게 알림** <p> _EnableExternalSenderNotifications_|사용 안 함 <p> `$false`|사용 안 함 <p> `$false`|사용 안 함 <p> `$false`||
|

### <a name="eop-default-anti-phishing-policy-settings"></a>EOP 기본 피싱 방지 정책 설정

이러한 설정에 대 한 자세한 내용은 [스푸핑 설정](set-up-anti-phishing-policies.md#spoof-settings)항목을 참조 하십시오. 이러한 설정을 구성 하려면 [EOP에서 피싱 방지 정책 구성을](configure-anti-phishing-policies-eop.md)참조 하십시오.

****

|보안 기능 이름|기본|Standard|항등|댓글|
|---|:---:|:---:|:---:|---|
|**스푸핑 방지 보호 사용** <p> _EnableAntispoofEnforcement_|켜짐 <p> `$true`|켜짐 <p> `$true`|켜짐 <p> `$true`||
|**인증 되지 않은 보낸 사람 사용** <p> _EnableUnauthenticatedSender_|켜짐 <p> `$true`|켜짐 <p> `$true`|켜짐 <p> `$true`|알 수 없는 스푸핑된 보낸 사람에 대 한 Outlook의 보낸 사람 사진에 물음표 (?)를 추가 합니다. 자세한 내용은 [피싱 방지 정책에서 스푸핑 설정을](set-up-anti-phishing-policies.md)참조 하십시오.|
|**도메인을 스푸핑할 수 없는 사용자가 전자 메일을 보낸 경우** <p> _AuthenticationFailAction_|**받는 사람의 정크 메일 폴더로 메시지 이동** <p> `MoveToJmf`|**받는 사람의 정크 메일 폴더로 메시지 이동** <p> `MoveToJmf`|**메시지 격리** <p> `Quarantine`|이 설정은 [위장 인텔리전스](learn-about-spoof-intelligence.md)에서 수신 거부에 적용 됩니다.|
|

## <a name="microsoft-defender-for-office-365-security"></a>Microsoft Defender for Office 365 보안

추가 보안 혜택은 Microsoft Defender for Office 365 구독에서 제공 됩니다. 최신 뉴스 및 정보를 보려면 [Defender For Office 365의 새로운 기능](whats-new-in-office-365-atp.md)을 확인 하세요.

> [!IMPORTANT]
>
> - Microsoft Defender for Office 365의 기본 피싱 방지 정책은 모든 받는 사람에 대해 [스푸핑 보호](set-up-anti-phishing-policies.md#spoof-settings) 및 사서함 인텔리전스를 제공 합니다. 그러나 기본 정책에서는 다른 사용 가능한 [가장 보호](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 기능 및 [고급 설정이](#advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 구성 되거나 사용 하도록 설정 되지 않습니다. 모든 보호 기능을 사용 하도록 설정 하려면 기본 피싱 방지 정책을 수정 하거나 추가 피싱 방지 정책을 만듭니다.
>
> - 조직의 모든 받는 사람을 자동으로 보호 하는 기본 안전 링크 정책 또는 안전한 첨부 파일 정책이 없습니다. 보호를 받으려면 하나 이상의 안전한 링크 정책 및 안전한 첨부 파일 정책을 만들어야 합니다.
>
> - [SharePoint, OneDrive 및 Microsoft 팀](atp-for-spo-odb-and-teams.md) 보호 및 [안전한 문서](safe-docs.md) 보호를 위한 ATP는 안전한 링크 정책에 종속 되지 않습니다.

구독에 Office 365 용 Microsoft Defender가 포함 되어 있거나 추가 기능으로 Office 365 용 Defender를 구매한 경우에는 다음 표준 또는 엄격한 구성을 설정 합니다.

### <a name="anti-phishing-policy-settings-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365의 피싱 방지 정책 설정

EOP 고객은 앞에서 설명한 것 처럼 기본 피싱 방지 기능을 사용할 수 있지만 Microsoft Defender for Office 365에는 공격을 방지, 감지 및 수정 하는 데 도움이 되는 다양 한 기능과 제어가 포함 되어 있습니다. 이러한 정책을 만들고 구성 하려면 [Defender에서 피싱 방지 정책 구성 Office 365](configure-atp-anti-phishing-policies.md)를 참조 하세요.

#### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Office 용 Microsoft Defender의 피싱 방지 정책에서 가장 설정 365

이러한 설정에 대 한 자세한 내용은 [피싱 방지 정책에서 Office 용 Microsoft Defender 365의 가장 설정을](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)참조 하세요. 이러한 설정을 구성 하려면 [Defender의 피싱 방지 정책 구성에서 Office 365](configure-atp-anti-phishing-policies.md)를 참조 하세요.

****

|보안 기능 이름|기본|Standard|항등|댓글|
|---|:---:|:---:|:---:|---|
|보호 된 사용자: **보호를 위해 사용자 추가** <p> _EnableTargetedUserProtection_ <p> _TargetedUsersToProtect_|해제 <p> `$false` <p> 없음|켜짐 <p> `$true` <p> \<list of users\>|켜짐 <p> `$true` <p> \<list of users\>|조직에 따라 주요 역할에 사용자 (메시지 보낸 사람)를 추가 하는 것이 좋습니다. 내부적으로 보호 된 보낸 사람은 CEO, CFO 및 기타 선임 리더가 될 수 있습니다. 외부적으로 보호 된 보낸 사람은 council 구성원 또는 이사회의 보드를 포함할 수 있습니다.|
|보호 된 도메인: **내가 소유한 도메인을 자동으로 포함** <p> _EnableOrganizationDomainsProtection_|해제 <p> `$false`|켜짐 <p> `$true`|켜짐 <p> `$true`||
|보호 된 도메인: **사용자 지정 도메인 포함** <p> _EnableTargetedDomainsProtection_ <p> _TargetedDomainsToProtect_|해제 <p> `$false` <p> 없음|켜짐 <p> `$true` <p> \<list of domains\>|켜짐 <p> `$true` <p> \<list of domains\>|조직에 따라 소유 하지 않지만 자주 상호 작용 하는 도메인 (보낸 사람 도메인)을 추가 하는 것이 좋습니다.|
|보호 된 사용자: **가장 된 사용자가 전자 메일을 보낸 경우** <p> _TargetedUserProtectionAction_|**작업 적용 안 함** <p> `NoAction`|**메시지 격리** <p> `Quarantine`|**메시지 격리** <p> `Quarantine`||
|보호 된 도메인: **가장 된 도메인에서 전자 메일을 보내는 경우** <p> _TargetedDomainProtectionAction_|**작업 적용 안 함** <p> `NoAction`|**메시지 격리** <p> `Quarantine`|**메시지 격리** <p> `Quarantine`||
|**가장 한 사용자에 대 한 팁 표시** <p> _EnableSimilarUsersSafetyTips_|해제 <p> `$false`|켜짐 <p> `$true`|켜짐 <p> `$true`||
|**가장 한 도메인에 대 한 팁 표시** <p> _EnableSimilarDomainsSafetyTips_|해제 <p> `$false`|켜짐 <p> `$true`|켜짐 <p> `$true`||
|**비정상적 캐릭터에 대 한 팁 표시** <p> _EnableUnusualCharactersSafetyTips_|해제 <p> `$false`|켜짐 <p> `$true`|켜짐 <p> `$true`||
|**사서함 인텔리전스 사용 가능 여부** <p> _EnableMailboxIntelligence_|켜짐 <p> `$true`|켜짐 <p> `$true`|켜짐 <p> `$true`||
|**사서함 인텔리전스 기반 가장 보호를 사용 하도록 설정** <p> _EnableMailboxIntelligenceProtection_|해제 <p> `$false`|켜짐 <p> `$true`|켜짐 <p> `$true`||
|**사서함 인텔리전스를 통해 보호 되는 가장 된 사용자가 전자 메일을 보낸 경우** <p> _MailboxIntelligenceProtectionAction_|**작업 적용 안 함** <p> `NoAction`|**받는 사람의 정크 메일 폴더로 메시지 이동** <p> `MoveToJmf`|**메시지 격리** <p> `Quarantine`||
|**신뢰할 수 있는 보낸 사람** <p> _ExcludedSenders_|없음|없음|없음|조직에 따라 가장을 제외 하 고 다른 필터는 제외 하 고는 전용으로 피싱로 표시 된 사용자를 추가 하는 것이 좋습니다.|
|**신뢰할 수 있는 도메인** <p> _ExcludedDomains_|없음|없음|없음|조직에 따라 가장을 제외 하 고는 다른 필터를 제외 하 고는 전용으로 피싱로 표시 된 도메인을 추가 하는 것이 좋습니다.|
|

#### <a name="spoof-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender의 피싱 방지 정책에서 스푸핑 설정 (Office 365 용)

이러한 설정은 [EOP의 스팸 방지 정책 설정](#eop-anti-spam-policy-settings)에서 사용할 수 있는 설정과 동일 합니다.

****

|보안 기능 이름|기본|Standard|항등|댓글|
|---|---|---|---|---|
|**스푸핑 방지 보호 사용** <p> _EnableAntispoofEnforcement_|켜짐 <p> `$true`|켜짐 <p> `$true`|켜짐 <p> `$true`||
|**인증 되지 않은 보낸 사람 사용** <p> _EnableUnauthenticatedSender_|켜짐 <p> `$true`|켜짐 <p> `$true`|켜짐 <p> `$true`|알 수 없는 스푸핑된 보낸 사람에 대 한 Outlook의 보낸 사람 사진에 물음표 (?)를 추가 합니다. 자세한 내용은 [피싱 방지 정책에서 스푸핑 설정을](set-up-anti-phishing-policies.md)참조 하십시오.|
|**도메인을 스푸핑할 수 없는 사용자가 전자 메일을 보낸 경우** <p> _AuthenticationFailAction_|**받는 사람의 정크 메일 폴더로 메시지 이동** <p> `MoveToJmf`|**받는 사람의 정크 메일 폴더로 메시지 이동** <p> `MoveToJmf`|**메시지 격리** <p> `Quarantine`|이 설정은 [위장 인텔리전스](learn-about-spoof-intelligence.md)에서 수신 거부에 적용 됩니다.|
|

#### <a name="advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Office 용 Microsoft Defender의 피싱 방지 정책에서 고급 설정 365

이 설정에 대 한 자세한 내용은 [Microsoft Defender For Office 365의 피싱 방지 정책에서 Advanced 피싱 임계값](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)을 참조 하세요. 이 설정을 구성 하려면 [Defender의 피싱 방지 정책 구성에서 Office 365](configure-atp-anti-phishing-policies.md)를 참조 하세요.

****

|보안 기능 이름|기본|Standard|항등|댓글|
|---|:---:|:---:|:---:|---|
|**고급 피싱 임계값** <p> _PhishThresholdLevel_|**1-표준** <p> `1`|**2-적극적인** <p> `2`|**3-적극적인** <p> `3`||
|

### <a name="safe-links-settings"></a>안전한 링크 설정

Defender for Office 365의 안전한 링크는 활성 안전한 링크 정책에 포함 된 모든 사용자에 게 적용 되는 전역 설정 및 각 안전한 링크 정책과 관련 된 설정을 포함 합니다. 자세한 내용은 [Defender For Office 365의 안전한 링크](atp-safe-links.md)를 참조 하세요.

#### <a name="global-settings-for-safe-links"></a>안전한 링크에 대 한 전역 설정

이러한 설정을 구성 하려면 [Defender For Office 365의 안전한 링크에 대 한 전역 설정 구성을](configure-global-settings-for-safe-links.md)참조 하십시오.

PowerShell에서는 이러한 설정에 대해 [AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365) cmdlet을 사용 합니다.

****

|보안 기능 이름|기본|Standard|항등|댓글|
|---|:---:|:---:|:---:|---|
|**에서 안전한 링크 사용: Office 365 응용 프로그램** <p> _EnableSafeLinksForO365Clients_|켜짐 <p> `$true`|켜짐 <p> `$true`|켜짐 <p> `$true`|지원 되는 Office 365 desktop 및 mobile (iOS 및 Android) 앱의 안전한 링크를 사용 합니다. 자세한 내용은 [Office 365 앱에 대 한 안전한 링크 설정](atp-safe-links.md#safe-links-settings-for-office-365-apps)를 참조 하세요.|
|**사용자가 안전 링크를 클릭 하는 경우 추적 안 함** <p> _가을 클릭 하면_|켜짐 <p> `$false`|해제 <p> `$true`|해제 <p> `$true`|이 설정을 해제 하면 _TrackClicks_ `$true` 지원 되는 Office 365 앱에서 사용자가 클릭을 추적 합니다.|
|**사용자가 원본 URL에 대 한 안전한 링크를 클릭 하는 것을 허용 하지 않음** <p> _AllowClickThrough 광고_|켜짐 <p> `$false`|켜짐 <p> `$false`|켜짐 <p> `$false`|이 설정을 켜면 ( _allowclickthrough_ 로 설정 `$false` )을 클릭 하면 지원 되는 Office 365 앱의 원본 URL로 이동할 수 없습니다.|
|

#### <a name="safe-links-policy-settings"></a>안전한 링크 정책 설정

이러한 설정을 구성 하려면 [Office 용 Microsoft Defender 365에서 안전한 링크 정책 설정](set-up-atp-safe-links-policies.md)를 참조 하세요.

PowerShell에서는 이러한 설정에 대해 [get-safelinkspolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy) 및 [get-safelinkspolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy) cmdlet을 사용 합니다.

> [!NOTE]
> 앞에서 설명한 것 처럼 기본 안전 링크 정책은 없습니다. 기본 열의 값은 새로 만든 안전한 링크 정책의 기본값입니다.

****

|보안 기능 이름|기본|Standard|항등|댓글|
|---|:---:|:---:|:---:|---|
|**메시지에서 알 수 없는 잠재적 악성 Url에 대 한 작업 선택** <p> _IsEnabled_|해제 <p> `$false`|켜짐 <p> `$true`|켜짐 <p> `$true`||
|**Microsoft 팀 내에서 알 수 없거나 잠재적으로 악성 Url에 대 한 작업 선택** <p> _EnableSafeLinksForTeams_|해제 <p> `$false`|켜짐 <p> `$true`|켜짐 <p> `$true`||
|**의심 스러운 링크에 대 한 실시간 URL 검사 및 파일을 가리키는 링크를 적용 합니다.** <p> _ScanUrls_|해제 <p> `$false`|켜짐 <p> `$true`|켜짐 <p> `$true`||
|**메시지를 배달 하기 전에 URL 검색이 완료 될 때까지 기다립니다.** <p> _배달 Messageafterscan_|해제 <p> `$false`|켜짐 <p> `$true`|켜짐 <p> `$true`||
|**조직 내에서 전송 된 전자 메일 메시지에 안전한 링크 적용** <p> _EnableForInternalSenders 사람_|해제 <p> `$false`|켜짐 <p> `$true`|켜짐 <p> `$true`||
|**사용자 클릭 추적 안 함** <p> _DoNotTrackUserClicks_|해제 <p> `$false`|해제 <p> `$false`|해제 <p> `$false`|이 설정을 해제 하면 사용자가 클릭 하는 _DoNotTrackUserClicks_ 를 `$false` 추적 합니다.|
|**사용자가 원래 URL로 클릭 하도록 허용 안 함** <p> _DoNotAllowClickThrough_|해제 <p> `$false`|켜짐 <p> `$true`|켜짐 <p> `$true`|이 설정을 켜면 ( _DoNotAllowClickThrough_ to to 설정 `$true` )을 클릭 하면 원래 URL로 이동 하지 않습니다.|
|

### <a name="safe-attachments-settings"></a>안전한 첨부 파일 설정

Microsoft Defender for Office 365의 안전한 첨부 파일에는 안전한 첨부 파일 정책과 관계가 없는 전역 설정 및 각 안전한 링크 정책과 관련 된 설정이 포함 됩니다. 자세한 내용은 [Defender For Office 365의 안전한 첨부 파일](atp-safe-attachments.md)을 참조 하세요.

#### <a name="global-settings-for-safe-attachments"></a>안전한 첨부 파일에 대 한 전역 설정

이러한 설정을 구성 하려면 [microsoft 365 E5의](safe-docs.md) [SharePoint, OneDrive 및 Microsoft 팀 및 안전한 문서에 대 한 ATP 끄기를](turn-on-atp-for-spo-odb-and-teams.md) 참조 하세요.

PowerShell에서는 이러한 설정에 대해 [AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365) cmdlet을 사용 합니다.

****

|보안 기능 이름|기본|Standard|항등|댓글|
|---|:---:|:---:|:---:|---|
|**SharePoint, OneDrive 및 Microsoft Teams의 ATP 켜기** <p> _EnableATPForSPOTeamsODB_|켜짐 <p> `$true`|켜짐 <p> `$true`||
|**Office 클라이언트에 대 한 안전 문서 설정**<bt/><br/> _EnableSafeDocs_|켜짐 <p> `$true`|켜짐 <p> `$true`|이 설정은 Microsoft 365 E5 또는 Microsoft 365 E5 보안 라이선스 에서만 사용할 수 있습니다. 자세한 내용은 [Microsoft Defender For Office 365의 안전 문서](safe-docs.md)를 참조 하세요.|
|**안전한 문서에 악성 프로그램으로 확인 된 안전 문서가 있는 경우에도 제한 됨 보기를 클릭 하도록 허용**<bt/><br/> _AllowSafeDocsOpen_|해제 <p> `$false`|해제 <p> `$false`|이 설정은 안전한 문서와 관련이 있습니다.|
|

#### <a name="safe-attachments-policy-settings"></a>안전한 첨부 파일 정책 설정

이러한 설정을 구성 하려면 [Defender For Safe Attachments 정책만 For Office 365](set-up-atp-safe-attachments-policies.md)을 참조 하십시오.

PowerShell에서는 이러한 설정에 대해 [get-safeattachmentpolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy) 및 [get-safeattachmentpolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy) cmdlet을 사용 합니다.

> [!NOTE]
> 앞에서 설명한 것 처럼 기본 안전 첨부 파일 정책은 없습니다. 기본 열의 값은 새로 만든 안전한 첨부 파일 정책의 기본값입니다.

****

|보안 기능 이름|기본|Standard|항등|댓글|
|---|:---:|:---:|:---:|---|
|**안전한 첨부 파일 알 수 없는 맬웨어 응답** <p> _작업_|차단 <p> `Block`|차단 <p> `Block`|차단 <p> `Block`||
|**검색 시 첨부 파일 리디렉션** : **리디렉션 사용** <p> _리디렉션_ <p> _RedirectAddress_|Off 및 지정 된 전자 메일 주소가 없습니다. <p> `$true` <p> 없음|설정 및 전자 메일 주소를 지정 합니다. <p> `$true` <p> 전자 메일 주소|설정 및 전자 메일 주소를 지정 합니다. <p> `$true` <p> 전자 메일 주소|검토를 위해 보안 관리자에 게 메시지를 리디렉션합니다.|
|**첨부 파일에 대 한 맬웨어 검사 시간이 초과 되거나 오류가 발생 하는 경우 위의 선택 사항을 적용 합니다.** <p> _ActionOnError_|켜짐 <p> `$true`|켜짐 <p> `$true`|켜짐 <p> `$true`||
|

## <a name="related-articles"></a>관련 문서

- **Exchange 메일 흐름 규칙 (전송 규칙이 라고도 함**)에 대 한 모범 사례를 찾으십니까? [Exchange Online에서 메일 흐름 규칙을 구성 하기 위한 모범 사례](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/configuration-best-practices)를 참조 하세요.

- 관리자 및 사용자는 가양성 (잘못 된 것으로 표시 된 좋은 전자 메일)과 거짓 네거티브 (잘못 된 전자 메일 허용)를 분석을 위해 Microsoft에 제출할 수 있습니다. 자세한 내용은 [Microsoft에 메시지와 파일 보고](report-junk-email-messages-to-microsoft.md)를 참조하세요.

- [EOP 서비스](set-up-your-eop-service.md)를 **설정** 하는 방법에 대 한 정보를 보려면 다음 링크를 사용 하 고 [Office 365 용 Microsoft Defender](office-365-atp.md)를 **구성** 합니다. '[Office 365의 위협 으로부터 보호](protect-against-threats.md)'에서 도움이 되는 지침을 잊지 마십시오.

- **Windows 용 보안 기준은** 여기에서 찾을 수 있습니다. GPO/온-프레미스 옵션에 대 한 보안 기준을 제공 하 고 [보안 기준을 사용 하 여 Intune 기반 보안용 intune에서 Windows 10 장치를 구성 하](https://docs.microsoft.com/intune/protect/security-baselines) [는 방법을 알아봅니다](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines) . 마지막으로 microsoft defender for Endpoint 및 Microsoft Intune 보안 기준을 비교 하 여 [끝점 및 Windows intune 보안 기준을 비교해](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines)볼 수 있습니다.
