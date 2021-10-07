---
title: 보안 강화를 위해 Microsoft 365 테넌트 구성
f1.keywords:
- NOCSH
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 10/11/2018
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- Strat_O365_IP
- M365-security-compliance
search.appverid: MET150
ms.assetid: 8d274fe3-db51-4107-ba64-865e7155b355
ms.custom:
- seo-marvel-apr2020
description: 이 항목에서는 사용자 환경의 보안에 영향을 주는 테넌트 전체 설정에 대한 권장 구성을 Microsoft 365 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b095d328a6582e93e79a2e6a76afe61ca59862cb
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60199348"
---
# <a name="configure-your-microsoft-365-tenant-for-increased-security"></a>보안 강화를 위해 Microsoft 365 테넌트 구성

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

이 항목에서는 사용자 환경의 보안에 영향을 주는 테넌트 전체 설정에 대한 권장 구성을 Microsoft 365 있습니다. 보안 요구에 따라 보안이 더 많이 또는 적게 필요할 수 있습니다. 이러한 권장 사항을 시작점으로 사용하세요.

## <a name="check-office-365-secure-score"></a>보안 Office 365 확인

Office 365 보안 점수는 정기적인 활동 및 보안 설정에 따라 조직의 보안을 분석하고 점수를 할당합니다. 먼저 현재 점수를 기록해 넣습니다. 일부 테넌트 전체 설정을 조정하면 점수가 증가합니다. 목표는 최대 점수를 달성하는 것이 아니라 사용자의 생산성에 부정적인 영향을 주지 않는 환경을 보호할 기회를 인식하는 것입니다. [Microsoft 보안 점수를 참조합니다.](../defender/microsoft-secure-score.md)

## <a name="tune-threat-management-policies-in-the-microsoft-365-defender-portal"></a>보안 포털에서 위협 Microsoft 365 Defender 조정

Microsoft 365 Defender 포털에는 환경을 보호하는 기능이 포함되어 있습니다. 또한 모니터링하고 조치를 취하는 데 사용할 수 있는 보고서 및 대시보드도 포함됩니다. 일부 영역에는 기본 정책 구성이 있습니다. 일부 영역에는 기본 정책이나 규칙이 포함되어 있지 않습니다. 전자 메일 & **공동** 작업 정책 & 규칙 위협 정책에서 이러한 정책을 방문하여 보다 안전한 환경을 위해 위협 관리 설정을 \>  \>  조정합니다.

<br>

****

|영역|기본 정책?|권장 사항|
|---|---|---|
|**피싱 방지**|예|EOP에서 피싱 방지 보호 설정 구성 및 에 설명된 기본 피싱 방지 정책을 [Office 365.](protect-against-threats.md#part-2---anti-phishing-protection-in-eop-and-defender-for-office-365) <p> 추가 정보: <ul><li>[2016년 8월의 피싱 Microsoft 365](set-up-anti-phishing-policies.md)</li><li>[Microsoft Defender for Office 365](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)</li><li> [가장 인사이트](impersonation-insight.md)</li><li>[EOP의 스푸핑 인텔리전스 정보](learn-about-spoof-intelligence.md)</li><li>[테넌트 허용/차단 목록을 관리합니다.](tenant-allow-block-list.md)</li></ul>|
|**맬웨어 방지 엔진**|예|EOP에서 맬웨어 방지 보호 설정 구성에 설명된 기본 맬웨어 방지 정책을 [구성합니다.](protect-against-threats.md#part-1---anti-malware-protection-in-eop) <p> 추가 정보: <ul><li>[맬웨어 방지 보호 기능](anti-malware-protection.md)</li><li>[권장되는 맬웨어 방지 정책 설정](recommended-settings-for-eop-and-office365.md#eop-anti-malware-policy-settings)</li><li>[맬웨어 방지 정책 구성](configure-anti-malware-policies.md)</li></ul>|
|**Defender for Office 365의 안전한 첨부 파일**|아니요|금고 첨부 파일에 대한 전역 설정을 구성하고 다음에 설명된 금고 첨부 파일 정책을 만들 수 있습니다. [Configure 금고 Attachments settings in Microsoft Defender for Office 365.](protect-against-threats.md#safe-attachments-policies-in-microsoft-defender-for-office-365) <p> 추가 정보: <ul><li>[권장 금고 첨부 파일 설정](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)</li><li>[금고 Microsoft Defender for Office 365](safe-attachments.md)</li><li>[안전한 첨부 파일 정책 설정](set-up-safe-attachments-policies.md)</li><li>[SharePoint, OneDrive 및 Microsoft Teams용 안전한 첨부 파일](mdo-for-spo-odb-and-teams.md)</li><li>[Microsoft 365 E5에서 안전한 문서](safe-docs.md)</li></ul>|
|**금고 Microsoft Defender for Office 365**|아니요|금고 링크에 대한 전역 설정을 구성하고 금고 링크에 대한 Microsoft [Defender의](protect-against-threats.md#safe-links-policies-in-microsoft-defender-for-office-365)금고 링크 설정 구성에 설명된 Office 365. <p> 추가 정보: <ul><li>[권장 금고 링크 설정](recommended-settings-for-eop-and-office365.md#safe-links-settings)</li><li>[안전한 링크 정책 설정](set-up-safe-links-policies.md)</li><li>[금고 Microsoft Defender for Office 365](safe-links.md)</li><li>[Microsoft Defender에서 금고 링크에 대한 전역 설정 Office 365](configure-global-settings-for-safe-links.md)</li></ul>|
|**스팸 방지(메일 필터링)**|예|[EOP에서](protect-against-threats.md#part-3---anti-spam-protection-in-eop) 스팸 방지 보호 설정 구성에 설명된 기본 스팸 방지 정책 구성 <p> 추가 정보: <ul><li>[권장 스팸 방지 정책 설정](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)</li><li>[EOP의 스팸 방지 보호 기능](anti-spam-protection.md)</li><li>[EOP에서 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)</li></ul>|
|***전자 메일 인증***|예|전자 메일 인증에서는 DNS 레코드를 사용하여 메시지 원본 및 보낸 사람에 대한 확인 가능한 정보를 전자 메일 메시지에 추가합니다. Microsoft 365 기본 도메인(onmicrosoft.com)에 대해 전자 메일 인증을 자동으로 구성하지만 Microsoft 365 사용자 지정 도메인에 대해 전자 메일 인증을 구성할 수도 있습니다. 세 가지 인증 방법이 사용됩니다. <ul><li>보낸 사람 정책 프레임워크(또는 SPF)</li><ul><li>설치에 대한 자세한 내용은 스푸핑을 Microsoft 365 SPF 설정을 [참조합니다.](set-up-spf-in-office-365-to-help-prevent-spoofing.md)</li></ul> <li>DomainKeys 식별 메일(DKIM)</li><ul><li>DKIM을 사용하여 사용자 지정 도메인에서 보낸 [아웃바운드 전자 메일의 유효성 검사를 참조하세요.](use-dkim-to-validate-outbound-email.md)</li><li>DKIM을 구성한 후 Microsoft 365 Defender 포털에서 사용하도록 설정합니다.</li></ul><li>도메인 기반 메시지 인증, 보고 및 적합성(DMARC)</li><ul><li>DMARC 설치의 경우 DMARC를 사용하여 에서 전자 [메일의 유효성을 Microsoft 365.](use-dmarc-to-validate-email.md)</li></ul></ul>|
|

> [!NOTE]
> 비표준 SPF 배포, 하이브리드 배포 및 문제 해결: Microsoft 365 [SPF(Sender Policy Framework)를](how-office-365-uses-spf-to-prevent-spoofing.md)사용하여 스푸핑을 방지하는 방법

## <a name="view-dashboards-and-reports-in-the-microsoft-365-defender-portal"></a>사이트 포털에서 대시보드 및 Microsoft 365 Defender 보기

이러한 보고서 및 대시보드를 방문하여 환경의 상태에 대해 자세히 알아보면 됩니다. 조직에서 서비스를 사용할 때 이러한 보고서의 데이터는 더 Office 365 있습니다. 지금은 모니터링하고 조치를 취할 수 있는 기능을 잘 알고 있습니다.

<br>

****

|대시보드|설명|
|---|---|
|전자 메일 보안 보고서|이러한 보고서는 각 보고서에서 Exchange Online Protection. 자세한 내용은 Microsoft 365 Defender 포털에서 전자 [메일 보안 보고서 보기를 참조하세요.](view-email-security-reports.md)|
|Defender for Office 365 보고서|보고서는 Defender에서만 사용할 수 Office 365. 자세한 내용은 view [Defender for Office 365 portal에서 Microsoft 365 Defender 참조하세요.](view-reports-for-mdo.md)|
|메일 흐름 보고서 및 인사이트|이러한 보고서 및 인사이트는 EAC(Exchange 관리 센터)에서 사용할 수 있습니다. 자세한 내용은 [메일](/exchange/monitoring/mail-flow-reports/mail-flow-reports) 흐름 보고서 및 메일 흐름 [정보 를 참조하세요.](/exchange/monitoring/mail-flow-insights/mail-flow-insights)|
|[위협 탐색기 (또는 실시간 검출)](threat-explorer.md)|테넌트에 대한 공격을 조사하거나 경험하는 경우 탐색기(또는 실시간 검색)를 사용하여 위협을 분석합니다. 탐색기(및 실시간 검색 보고서)는 시간이 지날수록 공격의 양을 보여 주며 위협 패밀리, 공격자 인프라 등에서 이 데이터를 분석할 수 있습니다. 인시던트 목록에 의심스러운 전자 메일을 표시할 수도 있습니다.|
|

## <a name="configure-additional-exchange-online-tenant-wide-settings"></a>테넌트 Exchange Online 설정 추가 구성

다음은 권장되는 몇 가지 추가 설정입니다.

<br>

****

|영역|권장 사항|
|---|---|
|**메일 흐름 규칙(전송** 규칙)|매크로가 포함된 파일 형식 및 실행 파일 형식을 차단하여 랜섬웨어를 Office 메일 흐름 규칙을 추가합니다. 자세한 내용은 [Use mail flow rules to inspect message attachments in Exchange Online.](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments) <p> 다음 추가 항목을 참조하세요. <ul><li>[랜섬웨어로부터 보호](../../admin/security-and-compliance/secure-your-business-data.md#5-protect-against-ransomware)</li><li>[맬웨어 및 랜섬웨어 Microsoft 365](/compliance/assurance/assurance-malware-and-ransomware-protection)</li><li>[랜섬웨어 공격으로부터 Office 365](recover-from-ransomware.md)</li></ul> <p> 메일 흐름 규칙을 만들어 전자 메일을 외부 도메인으로 자동 전달하지 못하게 합니다. 자세한 내용은 보안 점수를 사용하여 클라이언트 [외부 전달 규칙 완화를 참조하세요.](/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score) <p> 추가 정보: 메일 [흐름 규칙(전송 규칙) Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)|
|**최신 인증**|최신 인증은 MFA(다단계 인증)를 사용하기 위한 선행 요소입니다. MFA는 전자 메일을 비롯한 클라우드 리소스에 대한 액세스를 보안하는 데 권장됩니다. <p> 다음 항목을 참조하세요. <ul><li>[Exchange Online에서 최신 인증 사용 여부 설정](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)</li><li>[비즈니스용 Skype 온라인: 최신 인증을 위해 테넌트 사용](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)</li></ul> <p> 최신 인증은 Office, SharePoint Online 및 비즈니스용 OneDrive. <p> 추가 정보: [Office 2013](../../enterprise/modern-auth-for-office-2013-and-2016.md) 및 Office 클라이언트 앱에 대해 최신 인증이 작동하는 방식|
|

## <a name="configure-tenant-wide-sharing-policies-in-sharepoint-admin-center"></a>SharePoint 관리 센터에서 테넌트 전체 공유 정책 구성

기준 보호부터 시작하여 SharePoint 수준으로 팀 사이트를 구성하기 위한 Microsoft 권장 사항입니다. 자세한 내용은 사이트 및 파일 보호를 [위한 SharePoint 권장 사항을 참조하세요.](sharepoint-file-access-policies.md)

SharePoint 수준에서 구성된 팀 사이트를 사용하면 익명 액세스 링크를 사용하여 외부 사용자와 파일을 공유할 수 있습니다. 이 방법은 전자 메일로 파일을 보내는 대신 권장됩니다.

기준 보호 목표를 지원하기 위해 여기에 권장되는 테넌트 전체 공유 정책을 구성합니다. 개별 사이트에 대한 공유 설정은 이 테넌트 전체 정책보다 더 제한적일 수 있지만 더 제한적일 수 없습니다.

<br>

****

|영역|기본 정책 포함|권장 사항|
|---|---|---|
|**공유(SharePoint** Online 및 비즈니스용 OneDrive)|예|외부 공유는 기본적으로 사용하도록 설정되어 있습니다. 이러한 설정은 다음을 권장합니다. <ul><li>인증된 외부 사용자와 익명 액세스 링크 사용(기본 설정)에 대한 공유를 허용합니다.</li><li>익명 액세스 링크는 며칠 후에 만료됩니다. 원하는 경우 30일과 같은 숫자를 입력합니다.</li><li>기본 링크 유형 - 내부(조직의 사용자만 해당)를 선택합니다. 익명 링크를 사용하여 공유하려면 공유 메뉴에서 이 옵션을 선택해야 합니다.</li></ul> <p> 추가 정보: [외부 공유 개요](/sharepoint/external-sharing-overview)|
|

SharePoint 센터 및 비즈니스용 OneDrive 센터에 동일한 설정이 포함됩니다. 두 관리 센터의 설정이 모두 적용됩니다.

## <a name="configure-settings-in-azure-active-directory"></a>2016에서 설정 Azure Active Directory

보다 안전한 환경을 위해 테넌트 Azure Active Directory 설정을 완료하려면 이 두 영역을 방문해야 합니다.

### <a name="configure-named-locations-under-conditional-access"></a>명명된 위치 구성(조건부 액세스에서)

조직에 보안 네트워크 액세스 권한이 있는 사무실이 포함되어 있는 경우 신뢰할 수 있는 IP 주소 범위를 Azure Active Directory 위치로 추가합니다. 이 기능은 로그인 위험 이벤트에 대해 보고된 가짓 긍정 수를 줄이는 데 도움이 됩니다.

자세한 내용은 [다음을 참조하세요Azure Active Directory](/azure/active-directory/active-directory-named-locations)

### <a name="block-apps-that-dont-support-modern-authentication"></a>최신 인증을 지원하지 않는 앱 차단

다단계 인증을 사용하려면 최신 인증을 지원하는 앱이 필요합니다. 최신 인증을 지원하지 않는 앱은 조건부 액세스 규칙을 사용하여 차단할 수 없습니다.

보안 환경의 경우 최신 인증을 지원하지 않는 앱에 대해 인증을 사용하지 않도록 설정해야 합니다. 이 작업을 곧 Azure Active Directory 컨트롤을 사용하여 이 작업을 할 수 있습니다.

그동안 Online 및 SharePoint 다음 방법 중 하나를 비즈니스용 OneDrive.

- PowerShell 사용, ADAL(최신 인증)을 사용하지 않는 [앱 차단을 참조하세요.](/mem/intune/protect/app-modern-authentication-block)
- "장치 액세스" SharePoint 센터에서 "최신 인증을 사용하지 않는 앱의 액세스 제어"에서 이 설정을 구성합니다. 차단을 선택 합니다.

## <a name="get-started-with-cloud-app-security-or-office-365-cloud-app-security"></a>시작 Cloud App Security 또는 Office 365 Cloud App Security

이 Office 365 Cloud App Security 사용하여 위험을 평가하고 의심스러운 활동에 대해 경고하며 자동으로 조치를 취합니다. 계획 Office 365 E5 필요합니다.

또는 Microsoft Cloud App Security 권한을 부여받은 후에도 보다 자세한 가시성을 확보하고, 포괄적 제어를 획득하고, 모든 클라우드 응용 프로그램에 대한 향상된 보호 기능을 Office 365.

이 솔루션에서는 EMS E5 계획을 사용하는 것이 까다로울 것이 까다로울 Cloud App Security 환경의 다른 SaaS 응용 프로그램에서 사용할 수 있도록 하는 것이 좋습니다. 기본 정책 및 설정으로 시작

추가 정보:

- [Cloud App Security 배포](/cloud-app-security/getting-started-with-cloud-app-security)
- [Microsoft Cloud App Security에 대한 자세한 정보](https://www.microsoft.com/cloud-platform/cloud-app-security)
- [Cloud App Security란 무엇인가요?](/cloud-app-security/what-is-cloud-app-security)

![Cloud App Security 대시보드를 선택합니다.](../../media/1fb2aa65-54b8-4746-9f5e-c187d339e9f5.png)

## <a name="additional-resources"></a>추가 리소스

이러한 문서 및 가이드는 사용자 환경의 보안에 대한 추가 Microsoft 365 제공합니다.

- [정치적 캠페인, 비영리](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) 조직 및 기타 Agile 조직을 위한 Microsoft 보안 지침(모든 환경, 특히 클라우드 전용 환경에서 사용할 수 있습니다.

- [ID 및](microsoft-365-policies-configurations.md) 장치에 대한 권장 보안 정책 및 구성(이러한 권장 사항에는 AD FS 환경에 대한 도움말 포함)
