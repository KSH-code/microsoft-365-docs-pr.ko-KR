---
title: Microsoft 365 ISO 27001 작업 계획 - 처음 30일, 90일 및 그 이상 기간에 대한 최고 우선 순위 지정
description: ISO(국제 표준화 기구) 요구 사항을 준수하기 위해 작업할 때 따라야 하는 우선 순위가 지정된 작업 계획
keywords: Microsoft 365, Microsoft 365 Education, Microsoft 365 설명서, ISO, ISO 27001
author: BrendaCarter
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
manager: laurawi
audience: itpro
ms.collection:
- M365-security-compliance
ms.openlocfilehash: 3f81ad10d4549f9f28b5df4a0e090fb38a54bf6f
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283460"
---
# <a name="microsoft-365-iso-27001-action-plan--top-priorities-for-your-first-30-days-90-days-and-beyond"></a>Microsoft 365 ISO 27001 작업 계획 - 처음 30일, 90일 및 그 이상 기간에 대한 최고 우선 순위 지정

ISO(국제 표준화 기구)는 자발적 국제 표준의 독립적인 비정부 개발 기구입니다. IEC(국제 전기 표준 회의)는 전자, 전기 및 관련 기술에 대한 국제 표준의 준비와 발표를 진행합니다. ISO/IEC 27000 표준 제품군은 정보 자산의 보안 유지에 도움이 되는 컨트롤 및 메커니즘을 규정합니다.

ISO/IEC 27001은 ISMS(정보 보안 관리 시스템)를 구현하기 위한 국제 표준입니다. ISMS는 사용되는 필수 방법과 각종 조직의 정보 자산 보안에 대한 안전한 관리에 필수적인 요건과 관련된 증거를 기술합니다.  

이 문서에는 ISO/IEC 27001 요구 사항을 준수하기 위해 작업할 때 따라야 하는 우선 순위가 지정된 작업 계획이 포함되어 있습니다. 이 작업 계획은 규정 준수 전문 업체인 Microsoft 파트너, Protiviti와 협력하여 개발되었습니다. Maithili Dandige(Microsoft) 및 Antonio Maio(Protiviti)가 발표한 [Microsoft 365 준수 경로 및 정보 보호 전략 차트](https://myignite.techcommunity.microsoft.com/sessions/65720?source=sessions) 세션에 참석하여 Microsoft Ignite에서 이 작업 계획을 사용하는 방법을 알아보세요.


## <a name="action-plan-outcomes"></a>작업 계획 결과
논리적 순서에 따라 3단계로 구성된 권장 사항과 결과는 다음과 같습니다. 

|||
|:-----|:-----|
|**작업 단계**|**결과**|
|30일|**ISO 27001 거버넌스 및 준수 요구 사항을 파악합니다.**<br>• 위험 평가를 수행하고 해당 평가 결과에 맞춰 위험 관리 및 완화를 진행합니다.<br>•  Microsoft 준수 관리자를 사용하여 준수 위험을 평가하고 관리합니다.<br>• 14개의 각 ISO 27001 그룹에 대한 SOP(표준 운영 절차)를 설정합니다.<br><br>**사용자가 중요한 데이터 및 자산을 식별, 분류 및 보호하는 데 도움을 주기 위해 조직에 정보 분류 및 보존 정책과 도구를 롤아웃할 계획을 세웁니다.**<br>• 어떻게 Azure Information Protection 응용 프로그램 및 정책을 통해 사용자가 문서 및 전자 메일에 시각적인 중요 표시 및 메타데이터를 쉽게 적용할 수 있는지 알아봅니다. 교육 및 롤아웃 계획과 함께 조직의 정보 분류 스키마를 개발합니다.<br>•   사용자가 보존 및 보호 정책을 콘텐츠에 쉽게 적용할 수 있도록 하기 위해 조직에 Office 365 레이블을 롤아웃하는 것이 좋습니다. 교육 및 롤아웃 계획과 함께 정보 기록 보존에 대한 법적 요구 사항에 따라 조직의 레이블을 계획합니다.<br><br>**SOP(표준 운영 절차)의 일부로 감사 및 책임 정책을 만들어 정보 보안과 관련된 기록을 손실, 삭제, 수정 또는 무단 액세스로부터 보호합니다.**<br>•  365 감사 로깅(사서함 감사 포함)을 사용하도록 설정하여 Office 365에서 잠재적으로 악의적인 활동이 있는지 모니터링하고 데이터 위반에 대한 법정 분석을 설정합니다.<br>•   정규 흐름에서 Office 365 테넌트의 감사 로그를 검색하여 테넌트의 구성 설정에 적용된 변경 내용을 검토합니다.<br>• 사용자 계정에 대한 권한 상승과 같은 중요한 활동에 대해 경고 정책을 사용하도록 설정합니다.<br>•  Office 365 감사 로그 데이터를 장기간 저장하는 경우 Office 365 관리 활동 API 참조를 사용하여 SIEM(보안 정보 및 이벤트 관리) 도구와 통합합니다.<br><br>**책임 분리와 관련된 정책과 함께 조직에 대해 관리 및 보안 역할을 정의합니다.**<br>•    Office 365 관리 역할을 활용하여 관리 임무 분할을 사용하도록 설정합니다.<br>• 권한을 분할하여 단일 관리자가 필요한 수준보다 더 많은 액세스 권한을 갖지 않도록 합니다.
|90일|**Microsoft 365 보안 기능을 사용하여 환경에 대한 액세스를 제어하고, 정의된 SOP(표준 운영 절차)에 따라 조직 정보 및 자산을 보호합니다.**<br>•   Multi-Factor Authentication 및 최신 인증과 같은 ID 및 인증 솔루션을 사용하도록 설정하여 관리자 및 최종 사용자 계정을 보호합니다.<br>•  강력한 암호 정책을 설정하여 사용자 계정 자격 증명을 관리하고 보호합니다.<br>• 메시지 암호화 기능을 구성 및 롤아웃하여 전자 메일을 통해 중요한 데이터를 보낼 때 최종 사용자가 조직의 SOP를 준수하도록 도와줍니다.<br>•   악성 코드로부터 보호하고 데이터 위반 방지 및 응답 절차를 구현합니다.<br>•  중요한 데이터에 대한 액세스를 식별, 보호 및 제어하도록 DLP(데이터 손실 방지) 정책을 구성합니다.<br>• 회사 정책에 따라 중요한 데이터가 저장되고 액세스되도록 합니다.<br>• 악의적인 링크 및 첨부 파일이 들어 있는 피싱 전자 메일 및 Office 문서를 포함하는 가장 일반적인 공격 벡터를 방지합니다.
|90일 초과|**Microsoft 365 고급 데이터 거버넌스 도구 및 정보 보호를 사용하여 개인 데이터에 대한 지속적인 거버넌스 프로그램을 구현합니다.**<br>•    문서 및 전자 메일에서 개인 정보를 자동으로 식별합니다.<br>•   조직 전체의 모바일 장치에서 저장 및 액세스되는 중요한 데이터를 보호하고, 데이터에 액세스할 때 규격 회사 장치를 사용하도록 합니다.<br><br>**Microsoft 365 및 기타 클라우드 응용 프로그램에서 지속적인 준수를 모니터링합니다.**<br>•    SOP(표준 작업 절차)에 대한 성능을 평가하려면 Microsoft 준수 관리자를 사용하여 조직의 정보 보안 정책 및 해당 구현을 정기적으로 평가합니다.<br>•    정보 보안 관리 시스템을 지속적으로 검토 및 모니터링합니다.<br>•    높은 수준의 권한을 가진 모든 사용자 및 그룹(예: 권한 있는 사용자 또는 관리 사용자)의 정기적인 검토를 제어하고 수행합니다.<br>•  권한 있는 ID를 보호하고 권한 있는 액세스를 엄격히 제어하기 위한  Microsoft 365 기능을 배포하고 구성합니다.<br>•   SOP(표준 운영 절차)의 일부로, Office 365 감사 로그를 검색하여 테넌트 구성 설정의 변경, 최종 사용자 권한 상승 및 위험한 사용자 활동을 검토합니다.<br>•   조직의 클라우드 응용 프로그램 사용을 모니터링하고 고급 경고 정책을 구현합니다.<br>•  위험한 활동을 추적하여 잠재적으로 악의적인 관리자를 식별하거나, 데이터 위반을 조사하거나, 준수 요구 사항이 충족되지 않는지 확인합니다.




## <a name="30-days--powerful-quick-wins"></a>30일 - 빠른 조치의 강력한 효과
이러한 태스크는 빠르게 완료될 수 있으며 사용자에게 많은 영향을 미치지 않습니다.

|||
|:-----|:-----|
|**영역**|**태스크**|
|ISO 27001 거버넌스 및 준수 요구 사항을 파악합니다.|•    [Microsoft STP(Service Trust Portal)](https://support.office.com/article/get-started-with-the-microsoft-service-trust-portal-f30e2353-0bd6-41ed-8347-eea1fb8d2662) 내에서 [Microsoft 준수 관리자](https://support.office.com/article/use-compliance-manager-to-help-meet-data-protection-and-regulatory-requirements-when-using-microsoft-cloud-services-429e686f-d8a6-455e-a2b6-3791d763f000)를 사용하여 조직에 대한 ISO 27001:2013 평가를 수행함으로써 준수 위험을 평가하고 관리합니다. 각 14개 ISO 27001 그룹에 대해 SOP(표준 운영 절차)를 설정합니다.
|사용자가 중요한 데이터 및 자산을 식별, 분류 및 보호하는 데 도움을 주기 위해 조직에 정보 분류 및 보존 정책과 도구를 롤아웃할 계획을 세웁니다.|•  분류 정책 및 [Azure Information Protection](https://docs.microsoft.com/azure/information-protection/what-is-information-protection) 응용 프로그램을 롤아웃하여 사용자가 정보 보호 정책 및 SOP(표준 운영 절차)에 따라 중요한 데이터를 쉽게 식별 및 분류할 수 있도록 합니다. 교육 및 롤아웃 계획과 함께 조직의 정보 분류 스키마(정책)를 개발합니다.<br>•   사용자가 조직에 [Office 365 레이블](https://support.office.com/article/overview-of-labels-af398293-c69d-465e-a249-d74561552d30)을 롤아웃하여 보존 및 보호 정책을 콘텐츠에 쉽게 적용할 수 있도록 합니다. 교육 및 롤아웃 계획과 함께 정보 기록 보존에 대한 법적 요구 사항에 따라 조직의 레이블을 계획합니다.
|SOP(표준 운영 절차)의 일부로 감사 및 책임 정책을 만들어 정보 보안과 관련된 기록을 손실, 삭제, 수정 또는 무단 액세스로부터 보호합니다.|•  [Office 365 감사 로깅](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c) 및 [사서함 감사](https://support.office.com/article/Enable-mailbox-auditing-in-Office-365-aaca8987-5b62-458b-9882-c28476a66918)(모든 Exchange 사서함)를 사용하도록 설정하여 Office 365에서 잠재적으로 악의적인 활동이 있는지 모니터링하고 데이터 위반에 대한 법정 분석을 설정합니다.<br>• 정규 흐름에서 Office 365 테넌트의 감사 로그를 검색하여 테넌트의 구성 설정에 적용된 변경 내용을 검토합니다.<br>• 사용자 계정에 대해 권한 상승과 같은 중요한 활동이 수행될 때 Microsoft 365 또는 규정 준수 센터에서 [Office 365 경고 정책](https://support.office.com/article/alert-policies-in-the-office-365-security-compliance-center-8927b8b9-c5bc-45a8-a9f9-96c732e58264)을 사용하도록 설정합니다.<br>• Office 365 감사 로그 데이터를 장기간 저장하는 경우 [Office 365 관리 활동 API 참조](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)를 사용하여 SIEM(보안 정보 및 이벤트 관리) 도구와 통합합니다.
|책임 분리와 관련된 정책과 함께 조직에 대해 관리 및 보안 역할을 정의합니다.|• [Office 365 관리 역할](https://support.office.com/article/understanding-administrative-roles-52f29955-6a60-435f-aba9-eb69c898606a)을 사용하여 관리 책임의 분리를 설정합니다. 참고: Exchange Online, SharePoint Online 및 비즈니스용 Skype Online에도 Office 365의 관리자 역할에 해당하는 역할이 있습니다.<br>•  권한을 분할하여 단일 관리자가 필요한 수준보다 더 많은 액세스 권한을 갖지 않도록 합니다.|




## <a name="90-days--enhanced-protections"></a>90일 - 향상된 보호 
이러한 태스크는 계획하고 구현하는 데 다소 시간이 소요되지만 보안 태세를 갖추는 데 큰 도움이 됩니다. 

|||
|:-----|:-----|
|**영역**|**태스크**|
|Microsoft 365 보안 기능을 사용하여 환경에 대한 액세스를 제어하고, 정의된 SOP(표준 운영 절차)에 따라 조직 정보 및 자산을 보호합니다.|•  모든 사용자 계정에 대해 MFA(Multi-Factor Authentication)와 모든 앱에 대해 최신 인증을 사용하도록 설정하는 것을 포함하여 [ID 및 장치 액세스 정책](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-policies-configurations)을 구현하여 관리자 및 최종 사용자 계정을 보호합니다.<br>•    [강력한 암호 정책](https://www.microsoft.com/research/publication/password-guidance/)을 설정하여 사용자 계정 자격 증명을 관리하고 보호합니다.<br>•    [OME(Office 365 메시지 암호화)](https://support.office.com/article/office-365-message-encryption-f87cb016-7876-4317-ae3c-9169b311ff8a)를 설정하여 전자 메일을 통해 중요한 데이터를 보낼 때 최종 사용자가 조직의 SOP를 준수하도록 도와줍니다.<br>•  데이터 위반 방지 및 응답뿐만 아니라 악성 코드에 대한 보호를 위해 모든 데스크톱에 [Windows Defender ATP(Advanced Threat Protection)](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)를 배포합니다.<br>•  [Office 365 DLP(데이터 손실 방지) 정책](https://docs.microsoft.com/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)을 구성, 테스트 및 배포하여 재무, 의료 및 개인 식별 가능 정보를 포함하여 문서 및 전자 메일 내에 포함된 80가지가 넘는 중요한 데이터 유형을 식별, 모니터링 및 [자동으로 보호](https://docs.microsoft.com/office365/enterprise/apply-protection-to-personal-data-in-office-365)합니다.<br>•   [정책 팁](https://docs.microsoft.com/exchange/security-and-compliance/data-loss-prevention/policy-tips)을 구성하여 전자 메일 보낸 사람이 잘못된 메시지를 보내기 전에 정책을 위반할 수 있다는 사실을 자동으로 알립니다. Outlook, 웹용 Outlook 및 장치용 OWA에서 메시지 생성 동안 정책 위반 가능성에 대한 정보를 제공하는 간단한 노트를 표시하도록 정책 팁을 구성할 수 있습니다.<br>•    [Office 365 ATP(Advanced Threat Protection)](https://support.office.com/article/office-365-advanced-threat-protection-e100fe7c-f2a1-4b7d-9e08-622330b83653)를 구현하여 악의적인 링크 및 첨부 파일이 들어 있는 피싱 전자 메일 및 Office 문서를 포함하는 가장 일반적인 공격 벡터를 방지합니다.|



## <a name="beyond-90-days--ongoing-security-data-governance-and-reporting"></a>90일 - 지속적인 보안, 데이터 거버넌스 및 보고
미사용 개인 데이터 및 전송 중인 개인 데이터를 보호하고, 데이터 위반을 감지 및 대응하고, 보안 조치의 정기적인 테스트를 지원합니다. 이러한 작업은 이전 업무를 토대로 구축된 중요한 보안 조치입니다.  


|||
|:-----|:-----|
|**영역**|**태스크**|
|Microsoft 365 고급 데이터 거버넌스 도구 및 정보 보호를 사용하여 개인 데이터에 대한 지속적인 거버넌스 프로그램을 구현합니다.|•  [Office 365 고급 데이터 거버넌스](https://docs.microsoft.com/office365/enterprise/apply-labels-to-personal-data-in-office-365)를 사용하여 Office 365 레이블을 자동으로 적용함으로써 문서 및 전자 메일의 개인 정보를 식별합니다.<br>•   [Microsoft Intune](https://docs.microsoft.com/intune/)을 사용하여 조직 전체의 모바일 장치에서 저장 및 액세스되는 중요한 데이터를 보호하고, 데이터에 액세스할 때 규격 회사 장치를 사용하도록 합니다.|
|Microsoft 365 및 기타 클라우드 응용 프로그램에서 지속적인 준수를 모니터링합니다.|•    SOP(표준 작업 절차)에 대한 성능을 평가하려면 지속적으로 [Microsoft 준수 관리자](https://support.office.com/article/use-compliance-manager-to-help-meet-data-protection-and-regulatory-requirements-when-using-microsoft-cloud-services-429e686f-d8a6-455e-a2b6-3791d763f000)를 사용하여 조직의 정보 보안 정책 및 해당 구현에 대해 정기적인 ISO 27001:2013 평가를 실시합니다.<br>•  정보 보안 관리 시스템을 지속적으로 검토 및 모니터링합니다.<br>•    [Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-configure)를 사용하여 높은 수준의 권한을 가진 모든 사용자 및 그룹(예: 권한 있는 사용자 또는 관리 사용자)의 정기적인 검토를 제어하고 수행합니다.<br>• [Office 365에서 권한이 부여된 액세스 관리](https://docs.microsoft.com/office365/enterprise/privileged-access-management-in-office-365)를 배포 및 구성하여 Office 365에서 권한이 부여된 관리 태스크에 대해 세부적인 액세스 제어를 제공합니다. 일단 사용되도록 설정되면 사용자는 JIT(Just-In-Time) 액세스를 요청하여 범위 및 시간이 제한된 승인 워크플로를 통해 관리자 권한의 태스크 및 권한이 부여된 태스크를 완료해야 합니다.<br>• SOP(표준 운영 절차)의 일부로, Office 365 감사 로그를 검색하여 테넌트 구성 설정의 변경, 최종 사용자 권한 상승 및 위험한 사용자 활동을 검토합니다.<br>•   [비소유자 사서함 액세스](https://docs.microsoft.com/Exchange/policy-and-compliance/non-owner-mailbox-access-reports)를 감사하여 잠재적인 정보 누수를 확인하고 모든 Exchange Online 사서함에 대한 비소유자 액세스를 자동으로 검토합니다.<br>•   [Office 365 경고 정책, 데이터 손실 방지 보고서 및 Microsoft Cloud App Security](https://docs.microsoft.com/office365/enterprise/monitor-for-leaks-of-personal-data)를 사용하여 조직의 클라우드 응용 프로그램 사용 현황을 모니터링하고 추론 및 사용자 활동을 토대로 고급 경고 정책을 구현합니다.<br>• [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)를 사용하여 위험한 활동을 추적하여 잠재적으로 악의적인 관리자를 식별하거나, 데이터 위반을 조사하거나, 준수 요구 사항이 충족되지 않는지 확인합니다.|







## <a name="learn-more"></a>자세한 정보

Microsoft 보안 센터: [ISO/IEC 27001:2013 정보 보안 관리 표준](https://www.microsoft.com/TrustCenter/Compliance/ISO-IEC-27001)

[Microsoft 보안 센터](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)


