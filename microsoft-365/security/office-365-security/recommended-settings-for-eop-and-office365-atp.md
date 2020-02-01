---
title: EOP 및 Office 365 ATP 보안 설정, 권장 사항, 보낸 사람 정책 프레임 워크, 도메인 기반 메시지 보고 및 적합성에 대 한 Microsoft 권장 사항, DomainKeys 식별 된 메일, 단계, 작업 방법, 보안 기준, EOP에 대 한 초기 계획 ATP, 설치 ATP, 설치 EOP, ATP 구성, 구성 EOP, 보안 구성
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 12/12/2019
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
ms.openlocfilehash: fd2b1fdbb0356cfc2cea080f15bf696d8073fc10
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598645"
---
# <a name="recommended-settings-for-eop-and-office-365-atp-security"></a>EOP 및 Office 365 ATP 보안에 대 한 권장 설정

**EOP (Exchange Online Protection)** 는 Office 365 구독의 보안 핵심으로, 악의적인 전자 메일이 직원의 받은 편지함에 도달 하지 못하도록 합니다. 하지만 매일 보다 정교한 공격이 새로 등장 하면서도 향상 된 보호 기능은 대개 필요 합니다. **Office 365 ATP (Advanced Threat Protection)** ATP 계획 1 또는 ATP 계획 2에는 관리자가 더 많은 보안, 제어 및 조사 계층을 제공 하는 추가 기능이 포함 되어 있습니다.

보안 관리자는 보안 설정을 사용자 지정할 수 있도록 하지만 EOP 및 Office 365 ATP에는 **표준** 및 **Strict**의 두 가지 보안 수준이 권장 됩니다. 각 고객의 환경과 요구 사항은 서로 다르지만, 이러한 수준의 메일 필터링 구성은 대부분의 상황에서 원치 않는 메일이 직원의 받은 편지함에 도달 하지 못하도록 방지 하는 데 도움이 됩니다.

> [!IMPORTANT]
> 필터링이 제대로 작동 하려면 사서함에서 정크 메일 구성을 사용 하도록 설정 해야 합니다. 이 옵션은 기본적으로 사용 하도록 설정 되어 있지만 필터링이 작동 하지 않는 것 처럼 보이는 경우에는 확인 해야 합니다. 자세한 내용은 [set-mailboxjunkemailconfiguration](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-mailboxjunkemailconfiguration) 를 참조 하십시오. 

이 항목에서는 Office 365 사용자를 보호 하기 위해 이러한 Microsoft 권장 설정에 대해 설명 합니다.

> [!TIP]
> 이러한 설정 중 일부를 결정 하는 데 도움이 되는 Office 365 Advanced Threat Protection 권장 구성 분석기 (ORCA) 라는 새로운 PowerShell 모듈이 있습니다. 테 넌 트에서 관리자 권한으로 실행 하는 경우 ORCAReport는 스팸 방지, 피싱 및 기타 메시지 바이러스 설정에 대 한 평가를 생성 하는 데 도움이 됩니다. 이 모듈은에서 https://www.powershellgallery.com/packages/ORCA/다운로드할 수 있습니다.

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>EOP의 스팸 방지, 맬웨어 방지 및 피싱 방지 보호 기능

스팸 방지, 맬웨어 방지 및 피싱 방지 기능은 관리자가 구성할 수 있는 EOP의 기능입니다. 다음 구성을 권장 합니다.

### <a name="eop-anti-spam-policy-settings"></a>EOP 스팸 방지 정책 설정

|보안 기능 이름|표준을|항등|Comment|
|---------|---------|---------|---------|
|스팸 검색 작업|정크 메일 폴더로 메시지 이동|메시지 격리||
|높은 정확도 스팸 검색 작업|메시지 격리|메시지 격리||
|피싱 전자 메일 검색 작업|메시지 격리|메시지 격리||
|높은 신뢰도 피싱 전자 메일 검색 작업|메시지 격리|메시지 격리||
|대량 전자 메일 검색 작업|정크 메일 폴더로 메시지 이동|메시지 격리||
|대량 전자 메일 임계값을 다음으로 설정|6 |4 |기본값은 7 이지만이 값을 6으로 변경 하는 것이 좋습니다. 자세한 내용은 [대량 불만 수준 값](bulk-complaint-level-values.md)을 참조 하십시오.|
|격리 보존 기간|30일|30일||
|보안 팁|켜짐|켜짐||
|허용 된 보낸 사람|없음|없음||
|허용 된 보낸 사람 도메인|없음|없음|소유한 도메인 (허용 _도메인이_라고도 함)을 허용 된 보낸 사람 목록에 추가 하지 않아도 됩니다. 실제로는 잘못 된 행위자가 메일을 필터링 할 수 있는 기회를 만들기 때문에 높은 위험으로 간주 됩니다. **스팸 방지 설정** 페이지의 보안 & 준수 센터 [에서 스푸핑 정보를 사용 하](learn-about-spoof-intelligence.md) 여 조직의 일부인 도메인을 스푸핑 하는 모든 보낸 사람을 검토 하거나 외부 도메인을 위장 합니다.|
|수신 거부|없음|없음||
|수신 거부 도메인|없음|없음||
|최종 사용자 스팸 알림 빈도|사용|사용|3 일|
|제로 시간 자동 삭제|켜짐|켜짐|스팸 및 피싱 ZAP에 대해|
|MarkAsSpamBulkMail|켜짐|켜짐|이 설정은 PowerShell 에서만 사용할 수 있습니다.|

스팸 방지 정책에는 더 이상 사용 되지 않는 고급 스팸 필터 (ASF) 라는 몇 가지 다른 매개 변수가 있습니다. 이러한 기능의 감가 상각 일정에 대 한 자세한 내용은이 항목의 외부에서 제공 됩니다.
 
 표준 수준과 엄격한 수준에 대해 이러한 설정을 **해제** 하는 것이 좋습니다.

|보안 기능 이름|설명|
|---------|---------|
|IncreaseScoreWithImageLinks||
|IncreaseScoreWithNumericIps||
|IncreaseScoreWithRedirectToOtherPort||
|IncreaseScoreWithBizOrInfoUrls||
|MarkAsSpamEmptyMessages||
|MarkAsSpamJavaScriptInHtml||
|MarkAsSpamFramesInHtml||
|MarkAsSpamObjectTagsInHtml||
|MarkAsSpamEmbedTagsInHtml||
|MarkAsSpamFormTagsInHtml||
|MarkAsSpamWebBugsInHtml||
|MarkAsSpamSensitiveWordList||
|MarkAsSpamFromAddressAuthFail||
|MarkAsSpamNdrBackscatter||
|MarkAsSpamSpfRecordHardFail||

#### <a name="eop-outbound-spam-filter-policy-settings"></a>EOP 아웃 바운드 스팸 필터 정책 설정

|보안 기능 이름|표준을|항등|Comment|
|---------|---------|---------|---------|
|아웃 바운드 스팸 정책 받는 사람 제한-외부 시간 제한|500|400||
|아웃 바운드 스팸 정책 받는 사람 제한-내부 시간 제한|1000|800||
|아웃 바운드 스팸 정책 받는 사람 제한-일별 제한|1000|800||
|사용자가 제한을 초과 하는 경우의 동작|사용자가 메일을 보낼 수 없도록 제한|사용자가 메일을 보낼 수 없도록 제한||

### <a name="eop-anti-malware-policy-settings"></a>EOP 맬웨어 방지 정책 설정

|보안 기능 이름|표준을|항등|Comment|
|---------|---------|---------|---------|
|맬웨어 검색 응답|아니요|아니요|전자 메일 첨부 파일에서 맬웨어가 검색 되 면 메시지가 격리 되며 관리자만 해제할 수 있습니다.|
|의심 스러운 파일 형식 차단에 대 한 "일반 첨부 파일 형식 필터"|켜짐|켜짐||
|맬웨어 제로 시간 자동 삭제|켜짐|켜짐||
|배달 되지 않은 메시지의 내부 보낸 사람에 게 알림|사용 안 함|사용 안 함||
|배달 되지 않은 메시지의 외부 보낸 사람에 게 알림|사용 안 함|사용 안 함||

### <a name="eop-anti-phishing-policy-settings"></a>EOP 피싱 방지 정책 설정

|보안 기능 이름|표준을|항등|Comment|
|---------|---------|---------|---------|
|스푸핑 방지 보호 사용|켜짐|켜짐||
|인증 되지 않은 보낸 사람 (태깅) 사용|켜짐|켜짐||
|도메인을 스푸핑할 수 없는 사용자가 전자 메일을 보낸 경우|받는 사람의 정크 메일 폴더로 메시지 이동|메시지 격리||

## <a name="office-365-advanced-threat-protection-security"></a>Office 365 Advanced Threat Protection 보안

추가 보안 이점은 Office 365의 ATP (Advanced Threat Protection) 구독에서 제공 됩니다. 최신 뉴스 및 정보에 대 한 [Office 365 ATP의 새로운 기능](whats-new-in-office-365-atp.md)을 확인할 수 있습니다.

Office 365 ATP에는 악의적인 첨부 파일이 있는 전자 메일이 배달 되지 않도록 하 고 사용자가 안전 하지 않을 수 있는 Url을 클릭 하지 못하도록 하기 위한 안전한 첨부 파일 및 안전한 링크 정책이 포함 되어 있습니다.

> [!IMPORTANT]
> 고급 피싱 방지는 Office 365 ATP 구독의 혜택 중 하나입니다. 기본적으로 사용 하도록 설정 되어 있지만 메일 필터링을 시작 하려면 먼저 하나 이상의 피싱 방지 정책을 구성 ***해야 합니다*** . 피싱 방지 정책을 구성 하지 않으면 사용자가 위험한 전자 메일에 노출 될 수 있습니다. Office 365 ATP 구독을 추가한 후에는 피싱 방지 정책을 구성 해야 합니다.

EOP에 Office 365 ATP 구독을 추가한 경우에는 다음 구성을 설정 합니다.

### <a name="office-atp-anti-phishing-policy-settings"></a>Office ATP 피싱 방지 정책 설정

EOP 고객은 앞에서 설명한 것 처럼 기본 피싱 방지를 제공 하지만 Office 365 ATP에는 공격을 방지, 감지 및 수정 하는 데 도움이 되는 다양 한 기능 및 제어가 포함 되어 있습니다.

|가장 보안 기능 이름|표준을|항등|Comment|
|---------|---------|---------|---------|
|(가장 정책 편집) 보호할 사용자 추가|켜짐|켜짐|조직에 따라 다르지만 주요 역할에 사용자를 추가 하는 것이 좋습니다. 내부적으로는 CEO, CFO 및 기타 선임 리더가 될 수 있습니다. 외부에는 council 구성원 또는 이사회의 보드가 포함 될 수 있습니다.|
|(가장 정책 편집) 소유한 도메인을 자동으로 포함|켜짐|켜짐||
|(가장 정책 편집) 사용자 지정 도메인 포함|켜짐|켜짐|조직에 따라 다르지만 사용자가 소유 하지 않은 대부분의 도메인과 상호 작용 하는 도메인을 추가 하는 것이 좋습니다.|
|지정한 가장 한 사용자가 전자 메일을 보낸 경우|메시지 격리|메시지 격리||
|지정한 가장 한 도메인에서 전자 메일을 보낸 경우|메시지 격리|메시지 격리||
|가장 한 사용자에 대 한 팁 표시|켜짐|켜짐||
|가장 한 도메인에 대 한 팁 표시|켜짐|켜짐||
|비정상적 캐릭터에 대 한 팁 표시|켜짐|켜짐||
|사서함 인텔리전스 사용|켜짐|켜짐||
|사서함 인텔리전스 기반 가장 보호 사용|켜짐|켜짐||
|사서함 인텔리전스를 통해 보호 되는 가장 된 사용자가 전자 메일을 보낸 경우|받는 사람의 정크 메일 폴더로 메시지 이동|메시지 격리||
|(가장 정책 편집) 신뢰할 수 있는 보낸 사람 및 도메인 추가|없음|없음|조직에 따라 다르지만 가장을 제외 하 고는 피싱으로 표시 되는 사용자 또는 도메인을 추가 하는 것이 좋습니다.|

|스푸핑 보안 기능 이름|표준을|항등|Comment|
|---------|---------|---------|---------|
|스푸핑 방지 보호 사용|켜짐|켜짐||
|인증 되지 않은 보낸 사람 (태깅) 사용|켜짐|켜짐||
|도메인을 스푸핑할 수 없는 사용자가 전자 메일을 보낸 경우|받는 사람의 정크 메일 폴더로 메시지 이동|메시지 격리||
|EnableAuthenticationSafetyTip|참|참|이 설정은 PowerShell 에서만 사용할 수 있습니다.|
|EnableAuthenticationSoftPassSafetyTip|False|참|이 설정은 PowerShell 에서만 사용할 수 있습니다.|
|EnableSuspiciousSafetyTip|False|참|이 설정은 PowerShell 에서만 사용할 수 있습니다.|
|TreatSoftPassAsAuthenticated|참|False|이 설정은 PowerShell 에서만 사용할 수 있습니다.|

|고급 설정 보안 기능 이름|표준을|항등|Comment|
|---------|---------|---------|---------|
|고급 피싱 임계값|2-적극적인|3-적극적인||

### <a name="safe-links-settings"></a>안전한 링크 설정

|보안 기능 이름|표준을|항등|Comment|
|---------|---------|---------|---------|
|Office 365 앱, iOS 및 Android 용 Office에서 ATP 안전한 링크 사용|사용|사용|이는 전체 조직에 적용 되는 ATP 안전한 링크 정책에 속합니다.|
사용자가 안전 링크를 클릭 하는 경우 추적 안 함|사용 안 함|사용 안 함|전체 조직에 적용 되는 정책과 특정 받는 사람에 게 적용 되는 모든 정책을 위한 것입니다.|
|사용자가 원본 URL에 대 한 안전한 링크를 클릭 하는 것을 허용 하지 않음|사용|사용|이 작업은 전체 조직에 적용 되는 정책과 특정 받는 사람에 게 적용 되는 모든 정책에 대 한 것입니다.|
|메시지의 알려지지 않은 악성 Url에 대 한 작업|켜짐|켜짐||
|의심 스러운 링크에 대 한 실시간 URL 검사 및 파일을 가리키는 링크를 적용 합니다.|사용|사용||
|메시지를 배달 하기 전에 URL 검색이 완료 될 때까지 기다립니다.|사용|사용||
|조직 내에서 전송 된 전자 메일 메시지에 안전한 링크 적용|사용|사용||

### <a name="safe-attachments"></a>안전한 첨부 파일

|보안 기능 이름|표준을|항등|Comment|
|---------|---------|---------|---------|
|SharePoint, OneDrive 및 Microsoft Teams에 대한 ATP 켜기|사용|사용||
|ATP 안전한 첨부 파일 알 수 없는 맬웨어 응답|정책의|정책의||
|검색 시 첨부 파일 리디렉션|사용|사용|첨부 파일이 맬웨어 인지 여부를 확인 하는 방법을 알고 있는 보안 관리자의 전자 메일 주소로 리디렉션|
|ATP 안전한 첨부 파일 응답에 대 한 맬웨어 검색 시간이 초과 되거나 오류가 발생 하는 경우|사용|사용||


## <a name="related-topics"></a>관련 항목

- **Exchange 메일 흐름/Exchange 전송 규칙**에 대 한 모범 사례를 찾으십니까? 자세한 내용은 [이 문서](https://docs.microsoft.com/microsoft-365/security/office-365-security/best-practices-for-configuring-eop) 를 참조 하세요.

- 의심 스러운 우편, 의심 스러운 스팸, 피싱 또는 Url을 검색을 위해 Microsoft에 전송 합니다. [이 문서의](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission) **관리자 전송** 지침을 사용 합니다.

- [EOP 서비스](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-your-eop-service)를 **설정** 하는 방법에 대 한 정보를 보려면 다음 링크를 사용 하 고, [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)을 **구성** 합니다. ('[Office 365의 위협 으로부터 보호](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)하는 방법에 대 한 유용한 지침은 참조 하세요.)

- GPO/온-프레미스 옵션 및 Intune 기반 [보안에 대](https://docs.microsoft.com/intune/protect/security-baselines)한 **Windows 용 보안 기준을** [여기](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines) 에서 찾을 수 있습니다. 마지막으로 Microsoft의 ATP (Advanced Threat Protection) 및 Windows Intune 보안 기준을 [여기](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines)에서 확인할 수 있습니다.
