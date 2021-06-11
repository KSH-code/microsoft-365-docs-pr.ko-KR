---
title: 보안 설정에 대한 EOP 및 Defender에 Office 365 권장 사항
keywords: Office 365 보안 권장 사항, 보낸 사람 정책 프레임워크, 도메인 기반 메시지 보고 및 적합성, DomainKeys 식별된 메일, 단계, 작동 방식, EOP에 대한 보안 기준, Office 365용 Defender 기준, Office 365에 대한 Defender 설정 , EOP 설정, EOP에 대한 Defender Office 365 구성, EOP 구성, 보안 구성
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: ''
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 보안 설정에 대한 EOP(Exchange Online Protection) 및 Defender에 대한 모범 Office 365 무엇입니까? 표준 보호를 위한 현재 권장 사항은 무엇입니까? 더 엄격하게 사용하려는 경우 어떻게 해야 하나요? 또한 2016년 8월에 Defender를 사용하는 경우 어떤 추가 Office 365?
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6c126a777d50fae93efdc618a8ac474dcee7ed75
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878991"
---
# <a name="recommended-settings-for-eop-and-microsoft-defender-for-office-365-security"></a>EOP 및 Microsoft Defender 보안에 대한 Office 365 설정

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

**Exchange Online Protection(EOP)는** Microsoft 365 보안의 핵심으로, 악의적인 전자 메일이 직원의 받은 편지함으로 도달하지 못하게 합니다. 하지만 매일 새로운 더욱 정교한 공격이 나오면 향상된 보호가 필요한 경우가 종종 있습니다. **Microsoft Defender for Office 365** Plan 1 or Plan 2 contain additional features that give admins more layers of security, control, and investigation.

보안 관리자가 보안 설정을 사용자 지정할 수 있도록 지원하기는 하지만 EOP와 Microsoft Defender for  Office 365 권장되는 두 가지 보안 수준이 **있습니다.** 표준 및 엄격 . 각 고객의 환경과 요구는 서로 다르지만 이러한 필터링 수준은 대부분의 상황에서 원치 않는 메일이 직원의 받은 편지함으로 전달되지 않도록 하는 데 도움이 될 것으로 생각됩니다.

사용자에게 표준 또는 엄격한 설정을 자동으로 적용하려면 EOP의 미리 설정 보안 정책 및 Microsoft [Defender for Office 365.](preset-security-policies.md)

> [!NOTE]
> 필터링이 제대로 작동하려면 사서함에서 정크 메일 규칙을 사용하도록 설정해야 합니다. 기본적으로 사용하도록 설정되어 있지만 필터링이 작동하지 않는지 확인해야 합니다. 자세한 내용은 [Exchange Online 사서함에 대한 정크 메일 설정 구성하기](configure-junk-email-settings-on-exo-mailboxes.md)를 참조하세요.

이 문서에서는 기본 설정과 사용자를 보호하는 데 도움이 되는 권장 표준 및 엄격한 설정에 대해 설명합니다. 표에는 Microsoft 365 사서함이 없는 조직을 위한 Exchange Online PowerShell 또는 독립 실행형 PowerShell Exchange Online Protection PowerShell용 Exchange Online 설정이 포함되어 있습니다.

> [!TIP]
> PowerShell에 Office 365 ORCA(Advanced Threat Protection 권장 구성 분석기) 모듈을 통해 이러한 설정의 현재 값을 찾을 수 있습니다. 특히 **Get-ORCAReport** cmdlet은 스팸 방지, 피싱 방지 및 기타 메시지 예방조치 설정에 대한 평가를 생성합니다. 에서 ORCA 모듈을 다운로드할 수 <https://www.powershellgallery.com/packages/ORCA/> 있습니다.

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>EOP의 스팸 방지, 맬웨어 방지 및 피싱 방지 보호 기능

스팸 방지, 맬웨어 방지 및 피싱 방지는 관리자가 구성할 수 있는 EOP 기능입니다. 다음과 같은 표준 또는 엄격한 구성을 권장합니다.

### <a name="eop-anti-spam-policy-settings"></a>EOP 스팸 방지 정책 설정

스팸 방지 정책을 만들고 구성하는 내용은 [EOP에서 스팸 방지 정책 구성을 참조합니다.](configure-your-spam-filter-policies.md)

<br>

****

|보안 기능 이름|기본값|Standard|Strict|Comment|
|---|:---:|:---:|:---:|---|
|**스팸** 검색 작업 <p> _SpamAction_|**정크 메일 폴더로 메시지 이동** <p> `MoveToJmf`|**정크 메일 폴더로 메시지 이동** <p> `MoveToJmf`|**메시지 검량** <p> `Quarantine`||
|**높은 지수 스팸** 감지 작업 <p> _HighConfidenceSpamAction_|**정크 메일 폴더로 메시지 이동** <p> `MoveToJmf`|**메시지 검량** <p> `Quarantine`|**메시지 검량** <p> `Quarantine`||
|**피싱 감지** 작업 <p> _PhishSpamAction_|**정크 메일 폴더로 메시지 이동** <p> `MoveToJmf`|**메시지 검량** <p> `Quarantine`|**메시지 검량** <p> `Quarantine`||
|**높은 신뢰도 피싱 감지** 작업 <p> _HighConfidencePhishAction_|**메시지 검량** <p> `Quarantine`|**메시지 검량** <p> `Quarantine`|**메시지 검량** <p> `Quarantine`||
|**대량** 검색 작업 <p> _BulkSpamAction_|**정크 메일 폴더로 메시지 이동** <p> `MoveToJmf`|**정크 메일 폴더로 메시지 이동** <p> `MoveToJmf`|**메시지 검량** <p> `Quarantine`||
|**대량 전자 메일 임계값** <p> _BulkThreshold_|7 |6 |4 |자세한 내용은 [EOP의 BCL(대량 불만 수준)을 참조합니다.](bulk-complaint-level-values.md)|
|_MarkAsSpamBulkMail_|켜짐|켜짐|켜짐|이 설정은 PowerShell에서만 사용할 수 있습니다.|
|**이 며칠 동안 스팸을 검지에서 보존** <p> _QuarantineRetentionPeriod_|15일|30일|30일||
|**스팸 보안 팁 사용** <p> _InlineSafetyTipsEnabled_|켜짐 <p> `$true`|켜짐 <p> `$true`|켜짐 <p> `$true`||
|허용된 보낸 사람 <p> _AllowedSenders_|없음|없음|없음||
|허용된 보낸 사람 도메인 <p> _AllowedSenderDomains_|없음|없음|없음|허용된 보낸 사람 목록에 도메인을 추가하는 것은 매우 좋지 않습니다. 공격자는 다른 경우 필터링되는 전자 메일을 보낼 수 있습니다. <p> [스푸핑](learn-about-spoof-intelligence.md) 인텔리전스 인사이트 및 테넌트 [허용/차단](tenant-allow-block-list.md) 목록을 사용하여 조직의 전자 메일 도메인에서 보낸 사람 전자 메일 주소를 스푸핑하거나 외부 도메인의 보낸 사람 전자 메일 주소를 스푸핑하는 모든 보낸 사람 검토|
|수신이 차단된 보낸 사람 <p> _BlockedSenders_|없음|없음|없음||
|차단된 보낸 사람 도메인 <p> _BlockedSenderDomains_|없음|없음|없음||
|**최종 사용자 스팸 알림 사용** <p> _EnableEndUserSpamNotifications_|사용 안 함 <p> `$false`|사용 <p> `$true`|사용 <p> `$true`||
|**최종 사용자 스팸 알림 보내기(일)** <p> _EndUserSpamNotificationFrequency_|3일|3일|3일||
|피싱 메시지에 ZAP(제로 아워 자동 제거)를 사용하도록 설정 <p> _PhishZapEnabled_|사용 <p> `$true`|사용 <p> `$true`|사용 <p> `$true`||
|스팸 메시지에 ZAP 사용 <p> _SpamZapEnabled_|사용 <p> `$true`|사용 <p> `$true`|사용 <p> `$true`||
|

스팸 방지 정책에는 사용되지 않습니다. 이러한 기능의 정가 하한 일정에 대한 자세한 내용은 이 문서 외부에 전달될 것입니다.

표준 및 엄격한 수준 모두에  대해  다음 ASF 설정을 **해제하는 것이** 좋습니다. ASF 설정에 대한 자세한 내용은 [EOP의 ASF(고급 스팸 필터) 설정을 참조하세요.](advanced-spam-filtering-asf-options.md)

<br>

****

|보안 기능 이름|Comment|
|---|---|
|**원격 사이트에 대한** 이미지 링크(_IncreaseScoreWithImageLinks_)||
|**URL의 숫자 IP 주소(** _IncreaseScoreWithNumericIps_)||
|**다른 포트로 URL 리디렉션(** _IncreaseScoreWithRedirectToOtherPort_)||
|**.biz 또는 .info** 웹 사이트에 대한 링크(_IncreaseScoreWithBizOrInfoUrls)_||
|**빈 메시지(** _MarkAsSpamEmptyMessages_)||
|**HTML에** 태그를 추가합니다(_MarkAsSpamEmbedTagsInHtml_)||
|**HTML의 JavaScript 또는 VBScript(** _MarkAsSpamJavaScriptInHtml_)||
|**HTML의** 양식 태그(_MarkAsSpamFormTagsInHtml_)||
|**HTML의 프레임** 또는 iframe 태그(_MarkAsSpamFramesInHtml_)||
|**HTML의 웹** 버그(_MarkAsSpamWebBugsInHtml_)||
|**HTML의** 개체 태그(_MarkAsSpamObjectTagsInHtml_)||
|**중요한 단어(** _MarkAsSpamSensitiveWordList)_||
|**SPF 레코드: 하드 실패(** _MarkAsSpamSpfRecordHardFail_)||
|**보낸 사람 ID 필터링 하드 실패(** _MarkAsSpamFromAddressAuthFail_)||
|**후방산자(** _MarkAsSpamNdrBackscatter_)||
|

#### <a name="eop-outbound-spam-policy-settings"></a>EOP 아웃바운드 스팸 정책 설정

아웃바운드 스팸 정책을 만들고 구성하는 내용은 [EOP에서 아웃바운드 스팸 필터링 구성을 참조합니다.](configure-the-outbound-spam-policy.md)

서비스의 기본 전송 제한에 대한 자세한 내용은 [보내기 제한을 참조하세요.](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)

<br>

****

|보안 기능 이름|기본값|Standard|Strict|Comment|
|---|:---:|:---:|:---:|---|
|**외부 메시지 제한 설정** <p> _RecipientLimitExternalPerHour_|0|500|400|기본값 0은 서비스 기본값을 사용하는 것입니다.|
|**내부 메시지 제한 설정** <p> _RecipientLimitInternalPerHour_|0|1000|800|기본값 0은 서비스 기본값을 사용하는 것입니다.|
|**일별 메시지 제한 설정** <p> _RecipientLimitPerDay_|0|1000|800|기본값 0은 서비스 기본값을 사용하는 것입니다.|
|**메시지 제한에 도달한 사용자에게 적용된 제한 사항** <p> _ActionWhenThresholdReached_|**사용자가 다음 날까지 메일을 보내지 못하도록 제한** <p> `BlockUserForToday`|**사용자가 메일을 보낼 수 있도록 제한** <p> `BlockUser`|**사용자가 메일을 보낼 수 있도록 제한** <p> `BlockUser`||
|**자동 전달 규칙** <p> _AutoForwardingMode_|**자동 - 시스템 제어** <p> `Automatic`|**자동 - 시스템 제어** <p> `Automatic`|**자동 - 시스템 제어** <p> `Automatic`|
|

### <a name="eop-anti-malware-policy-settings"></a>EOP 맬웨어 방지 정책 설정

맬웨어 방지 정책을 만들고 구성하는 내용은 EOP에서 맬웨어 방지 [정책 구성을 참조합니다.](configure-anti-malware-policies.md)

<br>

****

|보안 기능 이름|기본값|Standard|Strict|Comment|
|---|:---:|:---:|:---:|---|
|**메시지가 맬웨어로 차단된 경우 받는 사람에게 알림** <p> _작업_|아니요 <p> _DeleteMessage_|아니요 <p> _DeleteMessage_|아니요 <p> _DeleteMessage_|전자 메일 첨부 파일에서 맬웨어가 검색된 경우 메시지는 검지되고 관리자만 릴리스할 수 있습니다.|
|**공통 첨부 파일 필터 사용** <p> _EnableFileFilter_|해제 <p> `$false`|켜짐 <p> `$true`|켜짐 <p> `$true`|이 설정은 첨부 파일 콘텐츠에 관계없이 파일 형식에 따라 실행 파일이 포함된 메시지를 검지합니다.|
|**맬웨어에 대해 제로 아워 자동 제거 사용** <p> _ZapEnabled_|켜짐 <p> `$true`|켜짐 <p> `$true`|켜짐 <p> `$true`||
|**메시지가 맬웨어로 검색된 경우 내부 보낸 사람에 알림** <p> _EnableInternalSenderNotifications_|사용 안 함 <p> `$false`|사용 안 함 <p> `$false`|사용 안 함 <p> `$false`||
|**메시지가 맬웨어로 차단된 경우 외부 보낸 사람에 알림** <p> _EnableExternalSenderNotifications_|사용 안 함 <p> `$false`|사용 안 함 <p> `$false`|사용 안 함 <p> `$false`||
|

### <a name="eop-anti-phishing-policy-settings"></a>EOP 피싱 방지 정책 설정

이러한 설정에 대한 자세한 내용은 [스푸핑 설정 을 참조하세요.](set-up-anti-phishing-policies.md#spoof-settings) 이러한 설정을 구성하려면 EOP에서 피싱 방지 [정책 구성을 참조하세요.](configure-anti-phishing-policies-eop.md)

<br>

****

|보안 기능 이름|기본값|Standard|Strict|Comment|
|---|:---:|:---:|:---:|---|
|**스푸핑 인텔리전스 사용** <p> _EnableSpoofIntelligence_|켜짐 <p> `$true`|켜짐 <p> `$true`|켜짐 <p> `$true`||
|**전자 메일이 스푸핑으로 검색된 경우** <p> _AuthenticationFailAction_|**받는 사람의 정크 메일 폴더로 메시지 이동** <p> `MoveToJmf`|**받는 사람의 정크 메일 폴더로 메시지 이동** <p> `MoveToJmf`|**메시지 Quarantine the message** <p> `Quarantine`|이 설정은 스푸핑 인텔리전스 인사이트에 표시된 [](learn-about-spoof-intelligence.md) 것 같이 자동으로 차단되거나 테넌트 허용/차단 목록에서 수동으로 차단된 스푸핑된 보낸 [사람에 적용됩니다.](tenant-allow-block-list.md)|
|**스푸핑을 위해 확인되지 않은 보낸 사람에 대한 표시(?)** <p> _EnableUnauthenticatedSender_|켜짐 <p> `$true`|켜짐 <p> `$true`|켜짐 <p> `$true`|미확인 스푸핑된 보낸 사람에 대한 보낸 Outlook 사진에 물음표(?)를 추가합니다. 자세한 내용은 [피싱 방지 정책의 스푸핑 설정](set-up-anti-phishing-policies.md)을 참조하세요.|
|**"via" 태그 표시** <p> _EnableViaTag_|켜짐 <p> `$true`|켜짐 <p> `$true`|켜짐 <p> `$true`|DKIM 서명의 도메인 또는 MAIL FROM 주소의 도메인과 다른 경우 보낸 chris@contoso.com (fabrikam.com 통해) 태그를 보낸사용자 주소에 **추가합니다.** <p> 이 설정을 사용할 수 없는 경우 물음표와 via 태그는 모두 조직에서 스푸핑에 대한 확인되지 않은 보낸 사람에 대한 표시(?)에 의해 제어됩니다.  |
|

## <a name="microsoft-defender-for-office-365-security"></a>Microsoft Defender for Office 365 보안

추가 보안 혜택은 Microsoft Defender for Office 365 함께 제공합니다. 최신 뉴스 및 정보는 에 대한 [Defender의](whats-new-in-defender-for-office-365.md)새로운 Office 365.

> [!IMPORTANT]
>
> - Microsoft Defender for Office 365 피싱 방지 정책은 모든 [](set-up-anti-phishing-policies.md#spoof-settings) 받는 사람에게 스푸핑 보호 및 사서함 인텔리전스를 제공합니다. 그러나 사용 가능한 [](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 다른 가장 보호 [](#advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 기능 및 고급 설정은 기본 정책에서 구성되거나 사용하도록 설정되지 않습니다. 모든 보호 기능을 사용하도록 설정하려면 기본 피싱 방지 정책을 수정하거나 추가 피싱 방지 정책을 만들 수 있습니다.
>
> - 조직의 모든 받는 사람을 자동으로 보호하는 기본 안전 링크 정책 또는 안전한 첨부 파일 정책은 없습니다. 보호를 위해 하나 이상의 안전한 링크 정책 및 안전한 첨부 파일 정책을 만들어야 합니다.
>
> - [SharePoint,](mdo-for-spo-odb-and-teams.md) OneDrive 및 Microsoft Teams 보호 및 안전한 문서 보호를 위한 [](safe-docs.md) 안전한 첨부 파일은 안전한 링크 정책에 종속되는 것이 없습니다.

구독에 microsoft Defender for Office 365 추가 기능으로 Office 365 Defender를 구매한 경우 다음 표준 또는 엄격 구성을 설정하세요.

### <a name="anti-phishing-policy-settings-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365

EOP 고객은 앞서 설명한 기본적인 피싱 방지 기능을 사용하지만, Microsoft Defender for Office 365 공격을 방지, 감지 및 수정하는 데 도움이 되는 더 많은 기능과 제어 기능이 포함되어 있습니다. 이러한 정책을 만들고 구성하는 내용은 [Configure anti-phishing policies in Defender for Office 365.](configure-atp-anti-phishing-policies.md)

#### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365

이러한 설정에 대한 자세한 내용은 Microsoft Defender for Office 365 피싱 방지 정책의 가장 [설정을 Office 365.](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 이러한 설정을 구성하려면 [Configure anti-phishing policies in Defender for Office 365.](configure-atp-anti-phishing-policies.md)

<br>

****

|보안 기능 이름|기본값|Standard|Strict|Comment|
|---|:---:|:---:|:---:|---|
|보호된 사용자(보낸 사람): **사용자가 보호할 수 있도록 설정** <p> _EnableTargetedUserProtection_ <p> _TargetedUsersToProtect_|해제 <p> `$false` <p> 없음|켜짐 <p> `$true` <p> \<list of users\>|켜짐 <p> `$true` <p> \<list of users\>|조직에 따라 주요 역할에 사용자(메시지 보낸 사람)를 추가하는 것이 좋습니다. 내부적으로 보호된 보낸 사람이 CEO, CFO 및 기타 고위 리더일 수 있습니다. 외부적으로 보호되는 보낸 사람에는 위원회 구성원이나 해당 이사진이 포함됩니다.|
|보호된 사용자: **가장된** 사용자로 메시지가 검색된 경우 <p> _TargetedUserProtectionAction_|**어떤 작업도 적용하지 않습니다.** <p> `NoAction`|**메시지 Quarantine the message** <p> `Quarantine`|**메시지 Quarantine the message** <p> `Quarantine`||
|보호된 도메인: **소유한 도메인 포함** <p> _EnableOrganizationDomainsProtection_|해제 <p> `$false`|켜짐 <p> `$true`|켜짐 <p> `$true`||
|보호된 도메인: **사용자 지정 도메인 포함** <p> _EnableTargetedDomainsProtection_ <p> _TargetedDomainsToProtect_|해제 <p> `$false` <p> 없음|켜짐 <p> `$true` <p> \<list of domains\>|켜짐 <p> `$true` <p> \<list of domains\>|조직에 따라 소유하지 않는 도메인(보낸 사람 도메인)을 추가하는 것이 되지만 자주 상호 작용합니다.|
|보호된 도메인: 메시지가 가장된 도메인으로 **검색된 경우** <p> _TargetedDomainProtectionAction_|**어떤 작업도 적용하지 않습니다.** <p> `NoAction`|**메시지 Quarantine the message** <p> `Quarantine`|**메시지 Quarantine the message** <p> `Quarantine`||
|**신뢰할 수 있는 발신자 및 도메인 추가** <p> _ExcludedSenders_ <p> _ExcludedDomains_|없음|없음|없음|조직에 따라 가장 시도로 잘못 식별된 보낸 사람 또는 도메인을 추가하는 것이 좋습니다.|
|**사서함 인텔리전스 사용** <p> _EnableMailboxIntelligence_|켜짐 <p> `$true`|켜짐 <p> `$true`|켜짐 <p> `$true`||
|**가장 보호를 위한 인텔리전스 사용** <p> _EnableMailboxIntelligenceProtection_|해제 <p> `$false`|켜짐 <p> `$true`|켜짐 <p> `$true`|이 설정을 사용하면 사서함 인텔리전스에서 가장 검색에 대해 지정된 작업을 허용합니다.|
|**사서함 인텔리전스에서 사용자를 검색하고 가장한 경우** <p> _MailboxIntelligenceProtectionAction_|**어떤 작업도 적용하지 않습니다.** <p> `NoAction`|**받는 사람의 정크 메일 폴더로 메시지 이동** <p> `MoveToJmf`|**메시지 Quarantine the message** <p> `Quarantine`||
|**사용자 가장 표시 보안 팁** <p> _EnableSimilarUsersSafetyTips_|해제 <p> `$false`|켜짐 <p> `$true`|켜짐 <p> `$true`||
|**도메인 가장 표시 보안 팁** <p> _EnableSimilarDomainsSafetyTips_|해제 <p> `$false`|켜짐 <p> `$true`|켜짐 <p> `$true`||
|**사용자 가장 비정상 문자 표시 보안 팁** <p> _EnableUnusualCharactersSafetyTips_|해제 <p> `$false`|켜짐 <p> `$true`|켜짐 <p> `$true`||
|

#### <a name="spoof-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365

이러한 설정은 EOP의 스팸 방지 정책 설정에서 사용할 수 있는 [설정과 동일합니다.](#eop-anti-spam-policy-settings)

<br>

****

|보안 기능 이름|기본값|Standard|Strict|Comment|
|---|:---:|:---:|:---:|---|
|**스푸핑 인텔리전스 사용** <p> _EnableSpoofIntelligence_|켜짐 <p> `$true`|켜짐 <p> `$true`|켜짐 <p> `$true`||
|**전자 메일이 스푸핑으로 검색된 경우** <p> _AuthenticationFailAction_|**받는 사람의 정크 메일 폴더로 메시지 이동** <p> `MoveToJmf`|**받는 사람의 정크 메일 폴더로 메시지 이동** <p> `MoveToJmf`|**메시지 Quarantine the message** <p> `Quarantine`|이 설정은 스푸핑 인텔리전스 인사이트에 표시된 [](learn-about-spoof-intelligence.md) 것 같이 자동으로 차단되거나 테넌트 허용/차단 목록에서 수동으로 차단된 스푸핑된 보낸 [사람에 적용됩니다.](tenant-allow-block-list.md)|
|**스푸핑을 위해 확인되지 않은 보낸 사람에 대한 표시(?)** <p> _EnableUnauthenticatedSender_|켜짐 <p> `$true`|켜짐 <p> `$true`|켜짐 <p> `$true`|미확인 스푸핑된 보낸 사람에 대한 보낸 Outlook 사진에 물음표(?)를 추가합니다. 자세한 내용은 [피싱 방지 정책의 스푸핑 설정](set-up-anti-phishing-policies.md)을 참조하세요.|
|**"via" 태그 표시** <p> _EnableViaTag_|켜짐 <p> `$true`|켜짐 <p> `$true`|켜짐 <p> `$true`|DKIM 서명의 도메인 또는 MAIL FROM 주소의 도메인과 다른 경우 보낸 chris@contoso.com (fabrikam.com 통해) 태그를 보낸사용자 주소에 **추가합니다.** <p> 이 설정을 사용할 수 없는 경우 물음표와 via 태그는 모두 조직에서 스푸핑에 대한 확인되지 않은 보낸 사람에 대한 표시(?)에 의해 제어됩니다.  |
|

#### <a name="advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365

이 설정에 대한 자세한 내용은 Microsoft Defender for [Office 365.](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 이 설정을 구성하는 내용은 [Configure anti-phishing policies in Defender for Office 365.](configure-atp-anti-phishing-policies.md)

<br>

****

|보안 기능 이름|기본값|Standard|Strict|Comment|
|---|:---:|:---:|:---:|---|
|**피싱 전자 메일 임계값** <p> _PhishThresholdLevel_|**1 - 표준** <p> `1`|**2 - 적극적** <p> `2`|**3 - 보다 적극적** <p> `3`||
|

### <a name="safe-links-settings"></a>안전한 링크 설정

Defender for Office 365 안전한 링크에는 활성 안전 링크 정책에 포함된 모든 사용자에게 적용되는 전역 설정과 각 안전 링크 정책과 관련한 설정이 포함되어 있습니다. 자세한 내용은 에 [대한 Defender의](safe-links.md)안전한 Office 365.

#### <a name="global-settings-for-safe-links"></a>안전한 링크에 대한 전역 설정

이러한 설정을 구성하려면 [Configure global settings for Safe Links in Defender for Office 365.](configure-global-settings-for-safe-links.md)

PowerShell에서는 이러한 설정에 [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365) cmdlet을 사용합니다.

<br>

****

|보안 기능 이름|기본값|Standard|Strict|Comment|
|---|:---:|:---:|:---:|---|
|**안전한 링크 사용: Office 365 앱** <p> _EnableSafeLinksForO365Clients_|켜짐 <p> `$true`|켜짐 <p> `$true`|켜짐 <p> `$true`|지원되는 데스크톱 및 모바일(iOS Office 365 및 Android) 앱에서 안전한 링크를 사용하세요. 자세한 내용은 앱의 안전한 링크 [Office 365 참조하세요.](safe-links.md#safe-links-settings-for-office-365-apps)|
|**사용자가 앱의 보호된 링크를 클릭하는 Office 365 추적하지 않습니다.** <p> _TrackClicks_|켜짐 <p> `$false`|해제 <p> `$true`|해제 <p> `$true`|이 설정을 _끄면(TrackClicks를_ 로 설정) 지원되는 앱의 사용자 `$true` 클릭을 Office 365 추적합니다.|
|**사용자가 앱의 원래 URL을 클릭할 Office 365 안 하세요.** <p> _AllowClickThrough_|켜짐 <p> `$false`|켜짐 <p> `$false`|켜짐 <p> `$false`|이 설정을 _켜면(AllowClickThrough를_ 로 설정) 지원되는 앱의 원래 `$false` URL을 클릭할 Office 365 없습니다.|
|

#### <a name="safe-links-policy-settings"></a>안전한 링크 정책 설정

이러한 설정을 구성하려면 [Set up Safe Links policies in Microsoft Defender for Office 365.](set-up-safe-links-policies.md)

PowerShell에서는 이러한 설정에 [New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy) 및 [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy) cmdlet을 사용합니다.

> [!NOTE]
> 앞에서 설명한 대로 기본 안전 링크 정책은 없습니다. 기본값 열의 값은 새로 만드는 안전 링크 정책의 기본값입니다.

<br>

****

|보안 기능 이름|기본값|Standard|Strict|Comment|
|---|:---:|:---:|:---:|---|
|**메시지에서 알 수 없는 악의적인 URL에 대한 작업 선택** <p> _IsEnabled_|해제 <p> `$false`|켜짐 <p> `$true`|켜짐 <p> `$true`||
|**알 수 없는 URL 또는 잠재적으로 악의적인 URL에 대한 작업을 Microsoft Teams** <p> _EnableSafeLinksForTeams_|해제 <p> `$false`|켜짐 <p> `$true`|켜짐 <p> `$true`||
|**파일을 지정하는 의심스러운 링크 및 링크에 대한 실시간 URL 검사 적용** <p> _ScanUrls_|해제 <p> `$false`|켜짐 <p> `$true`|켜짐 <p> `$true`||
|**메시지를 배달하기 전에 URL 검색이 완료될 때까지 기다렸다가** <p> _DeliverMessageAfterScan_|해제 <p> `$false`|켜짐 <p> `$true`|켜짐 <p> `$true`||
|**조직 내에서 보낸 전자 메일 메시지에 안전한 링크 적용** <p> _EnableForInternalSenders_|해제 <p> `$false`|켜짐 <p> `$true`|켜짐 <p> `$true`||
|**사용자 클릭 추적 안 하도록 설정** <p> _DoNotTrackUserClicks_|해제 <p> `$false`|해제 <p> `$false`|해제 <p> `$false`|이 설정을 _끄면(DoNotTrackUserClicks를_ 로 설정) 사용자 `$false` 클릭이 추적됩니다.|
|**사용자가 원래 URL을 클릭할 수 있도록 허용 안 하세요.** <p> _DoNotAllowClickThrough_|해제 <p> `$false`|켜짐 <p> `$true`|켜짐 <p> `$true`|이 _설정(DoNotAllowClickThrough를_ 로 설정)을 설정하면 원래 URL을 클릭할 `$true` 수 없습니다.|
|

### <a name="safe-attachments-settings"></a>안전한 첨부 파일 설정

Microsoft Defender for Office 365 안전 첨부 파일에는 안전 첨부 파일 정책과 관련이 없는 전역 설정과 각 안전 링크 정책과 관련한 설정이 포함되어 있습니다. 자세한 내용은 에 [대한 Defender의](safe-attachments.md)안전한 첨부 Office 365.

#### <a name="global-settings-for-safe-attachments"></a>안전한 첨부 파일에 대한 전역 설정

이러한 설정을 구성하려면 에서 [SharePoint,](turn-on-mdo-for-spo-odb-and-teams.md) OneDrive 및 Microsoft Teams 안전한 문서에 대해 안전한 첨부 [파일 Microsoft 365 E5.](safe-docs.md)

PowerShell에서는 이러한 설정에 [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365) cmdlet을 사용합니다.

<br>

****

|보안 기능 이름|기본값|Standard|Strict|Comment|
|---|:---:|:---:|:---:|---|
|**SharePoint, OneDrive 및 Microsoft Teams에 대해 Office 365용 Defender 켜기** <p> _EnableATPForSPOTeamsODB_|켜짐 <p> `$true`|켜짐 <p> `$true`||
|**클라이언트에 대해 안전한 Office 켜기** <p> _EnableSafeDocs_|켜짐 <p> `$true`|켜짐 <p> `$true`|이 설정은 Microsoft 365 E5 또는 Microsoft 365 E5 Security 사용할 수 있습니다. 자세한 내용은 Microsoft [Defender for Office 365.](safe-docs.md)|
|**안전한 문서에서 파일을 악성으로 식별한 경우에도 사용자가 보호된 보기를 클릭할 수 있도록 허용** <p> _AllowSafeDocsOpen_|해제 <p> `$false`|해제 <p> `$false`|이 설정은 안전한 문서와 관련이 있습니다.|
|

#### <a name="safe-attachments-policy-settings"></a>안전 첨부 파일 정책 설정

이러한 설정을 구성하려면 [Set up Safe Attachments policies in Defender for Office 365.](set-up-safe-attachments-policies.md)

PowerShell에서는 이러한 설정에 [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy) 및 [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safelinkspolicy) cmdlet을 사용합니다.

> [!NOTE]
> 앞에서 설명한 대로 기본 안전 첨부 파일 정책은 없습니다. 기본값 열의 값은 새로 만드는 안전 첨부 파일 정책의 기본값입니다.

<br>

****

|보안 기능 이름|기본값|Standard|Strict|Comment|
|---|:---:|:---:|:---:|---|
|**안전한 첨부 파일 알 수 없는 맬웨어 응답** <p> _작업_|차단 <p> `Block`|차단 <p> `Block`|차단 <p> `Block`||
|**검색 시 첨부 파일 리디렉션:** **리디렉션 사용** <p> _리디렉션_ <p> _RedirectAddress_|꺼지며 전자 메일 주소가 지정되지 않습니다. <p> `$true` <p> 없음|을 사용하여 전자 메일 주소를 지정합니다. <p> `$true` <p> 전자 메일 주소|을 사용하여 전자 메일 주소를 지정합니다. <p> `$true` <p> 전자 메일 주소|검토를 위해 보안 관리자에게 메시지를 리디렉션합니다.|
|**첨부 파일에 대한 맬웨어 검색이 시간 외 또는 오류가 발생하는 경우 위의 선택을 적용합니다.** <p> _ActionOnError_|켜짐 <p> `$true`|켜짐 <p> `$true`|켜짐 <p> `$true`||
|

## <a name="related-articles"></a>관련 문서

- 메일 흐름 규칙(전송 **규칙)Exchange 모범 사례를 찾고 있습니까?** 에서 메일 흐름 규칙을 구성하는 모범 사례를 [Exchange Online.](/exchange/security-and-compliance/mail-flow-rules/configuration-best-practices)

- 관리자와 사용자는 분석을 위해 가음성(양호한 전자 메일로 표시) 및 거짓 부정(잘못된 전자 메일 허용)을 Microsoft에 제출할 수 있습니다. 자세한 내용은 [Microsoft에 메시지와 파일 보고](report-junk-email-messages-to-microsoft.md)를 참조하세요.

- [EOP](/exchange/standalone-eop/set-up-your-eop-service)서비스를 설정하는  방법에 대한 자세한 내용은  다음 링크를 사용하여 에서 에 대해 [Microsoft Defender를 Office 365.](defender-for-office-365.md) ' Protect Against Threats in[Office 365'의](protect-against-threats.md)유용한 Office 365.

-  Windows 보안 기준은 GPO/Windows 보안 기준을 어디서 얻을 수 [있나요?](/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines) 및 Intune 기반 보안을 위해 [Intune에서](/intune/protect/security-baselines) Windows 10 장치를 구성하는 보안 기준을 사용할 수 있습니다. 마지막으로 끝점용 Microsoft Defender와 Microsoft Intune 보안 기준 비교는 [Endpoint용 Microsoft Defender 및 Windows Intune](/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines)보안 기준 비교에서 사용할 수 있습니다.
