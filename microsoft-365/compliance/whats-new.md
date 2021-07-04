---
title: Microsoft 365 규정 준수의 새로운 기능
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: 규정 준수 센터에 새 솔루션을 추가하거나, 피드백에 따라 기존 기능을 업데이트하거나, 최신 문서와 업데이트된 설명서를 롤아웃하는지 여부에 Microsoft 365 규정 준수 환경의 최신 기능을 유지하도록 지원합니다. 이번 달까지의 정보를 찾아보아야 합니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: aec9135a00b53f504d19a80e428d52f21b92cf9c
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288134"
---
# <a name="whats-new-in-microsoft-365-compliance"></a>Microsoft 365 규정 준수의 새로운 기능

새 솔루션을 Microsoft 365 규정 준수 센터, 피드백에 따라 기존 기능을 업데이트하거나, 최신 문서와 업데이트된 설명서를 롤아웃하는지 여부에 Microsoft 365 규정 준수 환경이 계속 변화하는 규정 준수 환경의 맨 위에 유지될 수 있습니다. [](microsoft-365-compliance-center.md) 아래에서 규정 준수의 새로운 Microsoft 365 확인하세요.

> [!NOTE]
> 일부 규정 준수 기능은 고객에게 다른 속도로 롤아웃됩니다. 아직 기능이 없는 경우 대상 릴리스에 자신을 [추가해 보세요.](/office365/admin/manage/release-options-in-office-365)

> [!TIP]
> 다른 관리 센터의 진행 상황에 관심이 있나요? 다음 문서를 확인해보아야 합니다.
>
> - [새로운 Microsoft 365 관리 센터](/office365/admin/whats-new-in-preview)
> - [SharePoint 관리 센터의 새로운](/sharepoint/what-s-new-in-admin-center)
> - [Microsoft 365 Defender의 새로운 기능](../security/defender/whats-new.md)
>
> 또한 Microsoft 365 [](https://www.microsoft.com/microsoft-365/roadmap) 로드맵을 방문하여 Microsoft 365, 개발 중, 취소 또는 이전에 릴리스된 Microsoft 365 기능에 대해 자세히 알아보습니다.

## <a name="may-2021"></a>2021년 5월

### <a name="data-loss-prevention"></a>데이터 손실 방지

- 데이터 손실 [방지 전략을 계획하기 위한 새로운](dlp-overview-plan-for-dlp.md) 지침입니다.

### <a name="retention-and-records-management"></a>보존 및 레코드 관리

- SharePoint 사이트 또는 OneDrive 계정에서 보존 정책을 해제하는 경우 더 이상 30일 유예 기간 동안 기다렸다가 사이트 또는 계정을 삭제할 수 있습니다. 고객의 인기 있는 요청으로, 이제 모든 테넌트에 대해 이 변경이 완료되었습니다.
- 미리 **보기에서** 다단계 분해 검토: 이제 관리자는 보존 레이블에 대한 최대 [](disposition.md) 5개의 연속된 삭제 검토 단계에 추가할 수 있으며, 검토자는 다른 사용자를 해당 삭제 검토 단계에 추가할 수 있습니다. 또한 전자 메일 알림 및 미리 알림을 사용자 지정할 수 있습니다.

### <a name="sensitive-information-types"></a>중요한 정보 유형

- 키워드 사전을 수정하는 데 도움이 되는 [새로운 정보입니다.](sit-modify-keyword-dictionary.md)

### <a name="sensitivity-labels"></a>민감도 레이블

- 미리 보기에서 이제  그룹 및 사이트에 대해 민감도 레이블을 구성할 때 인증 컨텍스트에 대한 새 설정을 [사용할 수 있습니다.](sensitivity-labels-teams-groups-sites.md) 이 옵션은 Azure AD 조건부 액세스 정책과 함께 작동하여 사용자가 레이블이 적용된 SharePoint 사이트에 액세스할 때 더 엄격한 조건을 적용합니다. 이 설정을 구성하기 전에 종속성 및 [제한](sensitivity-labels-teams-groups-sites.md#more-information-about-the-dependencies-for-the-authentication-context-option) 사항을 읽어야 합니다.
- [현재 사용자에](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange) 대해 구성된 자동 레이블 지정 정책은 Exchange 전달 금지 또는  추가 옵션에 대한 사용 권한을 할당하도록 허용을 통해 암호화를 적용하는 민감도 레이블을 Encrypt-Only 있습니다.
- [필수 레이블 지정은](sensitivity-labels-office-apps.md#require-users-to-apply-a-label-to-their-email-and-documents) 이제 모든 플랫폼의 모든 Office 앱에서 일반적으로 사용할 수 있습니다.

## <a name="april-2021"></a>2021년 4월

### <a name="advanced-ediscovery"></a>Advanced eDiscovery

- [의 제한 Advanced eDiscovery.](/microsoft-365/compliance/limits-ediscovery20#export-limits---final-export-out-of-review-set) 이제 조직은 검토 집합에서 항목의 단일 내보내기에서 최대 500만 개 항목 또는 500MB(더 작은 항목)를 내보낼 수 있습니다.

### <a name="data-classification"></a>데이터 분류

- [활동 탐색기에서 사용할 수 있는 레이블 지정 활동](/microsoft-365/compliance/data-classification-activity-explorer-available-events)

### <a name="data-connectors"></a>데이터 커넥터

- [Oracle 데이터에 Cisco Jabber를 보관할 커넥터 설정](/microsoft-365/compliance/archive-ciscojabberonoracle-data)
- [PostgreSQL 데이터에 Cisco Jabber를 보관할 커넥터 설정](/microsoft-365/compliance/archive-ciscojabberonpostgresql-data)

### <a name="data-loss-prevention"></a>데이터 손실 방지

- 데이터 손실 방지 정책 [팁 참조에 대한 새 항목입니다.](/microsoft-365/compliance/dlp-policy-tips-reference)
- 데이터 손실 [방지에 대한 새로운 항목입니다.](/microsoft-365/compliance/dlp-learn-about-dlp)
- 데이터 손실 방지 경고 대시보드 시작에 [대한 새 항목입니다.](/microsoft-365/compliance/dlp-alerts-dashboard-get-started)

### <a name="retention-policies-and-retention-label-policies"></a>보존 정책 및 보존 레이블 정책

- Microsoft 365 그룹 위치는 *이제 Applications* 매개 변수와 함께 [Set-RetentionCompliancePolicy PowerShell](/powershell/module/exchange/set-retentioncompliancepolicy) cmdlet을 사용하여 Microsoft 365 사서함 또는 연결된 SharePoint 사이트에 보존 설정을 적용할 수 있습니다.

### <a name="sensitivity-labels"></a>민감도 레이블

Outlook 릴리스 및 업데이트:

- [이제 기본 레이블 및](sensitivity-labels-office-apps.md#outlook-specific-options-for-default-label-and-mandatory-labeling) 필수 레이블 지정에 대한 다양한 설정이 기본 제공 레이블 지정에 지원됩니다. 이전에는 AIP 통합 레이블 지정 클라이언트에서만 이러한 설정을 지원했습니다.
- [암호화 전용은](encryption-sensitivity-labels.md#let-users-assign-permissions) 이제 macOS, iOS 및 Android에서 지원됩니다.
- [필수 레이블은](sensitivity-labels-office-apps.md#require-users-to-apply-a-label-to-their-email-and-documents) 나머지 플랫폼에 롤아웃됩니다.
- [모든 변수가](sensitivity-labels-office-apps.md#dynamic-markings-with-variables) 있는 동적 표시는 모든 클라이언트에서 Outlook 지원됩니다.

## <a name="march-2021"></a>2021년 3월

다음은 3월 한 달 동안 Microsoft 365 솔루션 및 콘텐츠에 대한 몇 가지 변경 내용입니다.

### <a name="advanced-ediscovery"></a>Advanced eDiscovery

- **Advanced eDiscovery 컬렉션에서** 새 컬렉션 도구 및 [워크플로를 지원하게 됩니다.](/microsoft-365/compliance/collections-overview) 다른 새 항목에는 초안 컬렉션 [만들기,](/microsoft-365/compliance/create-draft-collection)검토 [집합에](/microsoft-365/compliance/commit-draft-collection)초안 컬렉션 커밋, 컬렉션 통계 및 보고서가 [있습니다.](/microsoft-365/compliance/collection-statistics-reports)
- **검토 집합의** 문서를 Azure Storage 계정으로 [내보낼](/microsoft-365/compliance/download-export-jobs) 수 있습니다.
- **에 대한** 예측 코딩 Advanced eDiscovery. 먼저 사용 중지된 [Relevance](/microsoft-365/compliance/predictive-coding-overview) 모듈을 대체하는 새로운 예측 코딩 기능을 살펴 봐야 합니다.

### <a name="data-classification"></a>데이터 분류

- **데이터 분류 탐색기**. [데이터 분류 탐색기를](/microsoft-365/compliance/data-classification-activity-explorer) 시작하십시오.

### <a name="data-connectors"></a>데이터 커넥터

- **개인 키**. 개인 키에 대한 지원이 [Bloomberg 메시지](/microsoft-365/compliance/archive-bloomberg-message-data#set-up-a-connector-using-public-keys) 데이터, [ICE 채팅](/microsoft-365/compliance/archive-icechat-data#set-up-a-connector-using-public-keys) 데이터 및 [Instant Bloomberg](/microsoft-365/compliance/archive-instant-bloomberg-data#set-up-a-connector-using-public-keys) 데이터 커넥터에 추가되었습니다.

### <a name="data-loss-prevention"></a>데이터 손실 방지

- **Microsoft Teams 지원.** 데이터 손실 방지 지원은 [Microsoft Teams.](/microsoft-365/compliance/dlp-teams-default-policy)
- **Microsoft 규정 준수 확장**. Microsoft 준수 [확장을 시작 합니다.](/microsoft-365/compliance/dlp-chrome-get-started)

### <a name="encryption"></a>암호화

- **에 대한 고객 Microsoft 365.** [테넌트](/microsoft-365/compliance/customer-key-tenant-level) 수준의 고객 Microsoft 365(공개 미리 보기)에 대한 개요입니다.
- **이중 키 암호화**. 자세한 내용은 레이블이 [지정되어](/microsoft-365/compliance/double-key-encryption) 있는 문서 및 보호된 문서에 대한 지원을 사용하도록 설정하는 방법을 SharePoint 비즈니스용 OneDrive.

### <a name="insider-risk-management"></a>내부자 위험 관리

다음 내부자 위험 관리 기능 업데이트는 3월에 공개 미리 보기를 위해 릴리스되었습니다.

- 내부자 위험 정책을 만들기 전에 위험을 식별하기 위한 새로운 분석 기능
- 새로운 위험 활동 시퀀스 검색 지원 및 관리
- 새로운 누적 유출 감지 지원
- 새로운 앱 내 정책 상태 보고 및 권장 지원
- 새로운 감사 로그 기능 및 보고
- 정책 만들기 마법사의 향상된 기능
- 콘텐츠 탐색기 업데이트
- 새 사용자 관리 프로세스/지원(정책에서 사용자 추가/제거)
- AAD 통합에 대한 새로운 지원(사용자 정책 지원이 떠났음)
- 정책에서 도메인 지원 업데이트(REGEX)
- 정책 템플릿의 향상된 기능 및 개선 사항

다음 항목은 이러한 새로운 기능을 지원하기 위해 업데이트되거나 추가되었습니다.

- [내부자 위험 관리에 대해 알아보기](/microsoft-365/compliance/insider-risk-management)
- [내부자 위험 관리 계획](/microsoft-365/compliance/insider-risk-management-plan)
- [내부자 위험 관리 설정 시작](/microsoft-365/compliance/insider-risk-management-settings)
- [내부자 위험 관리 시작](/microsoft-365/compliance/insider-risk-management-configure)
- [내부자 위험 정책 만들기 및 관리](/microsoft-365/compliance/insider-risk-management-policies)
- [내부자 위험 경고 조사](/microsoft-365/compliance/insider-risk-management-alerts)
- [내부자 위험 사례에 대한 작업 수행](/microsoft-365/compliance/insider-risk-management-cases)
- [내부자 위험 감사 로그를 사용하여 활동 검토](/microsoft-365/compliance/insider-risk-management-audit-log)
- [내부자 위험 콘텐츠 탐색기를 사용하여 데이터 검토](/microsoft-365/compliance/insider-risk-management-content-explorer)
- [사용자 대시보드를 사용하여 워크플로 관리](/microsoft-365/compliance/insider-risk-management-users)

### <a name="records-management"></a>레코드 관리

- **파일 계획 개선.** 파일 계획에 [대한 업데이트는](file-plan-manager.md) 가져오기 이전 길이 제한을 제거하거나 개선합니다.
- **레코드에 대한 보존 레이블을 삭제합니다.** 미리 보기 릴리스에서는 항목을 [](create-apply-retention-labels.md#deleting-retention-labels) 레코드로 표시하는 보존 레이블을 삭제할 수 있습니다.

### <a name="sensitive-information-types"></a>중요한 정보 유형

다음 항목에서 콘텐츠가 추가되거나 업데이트되었습니다.

- [사용자 지정 중요한 정보 유형 시작](/microsoft-365/compliance/create-a-custom-sensitive-information-type)
- [중요한 정보 유형에 대해 알아보기](/microsoft-365/compliance/sensitive-information-type-learn-about)
- [분류에 기반한 정확한 데이터 매치를 사용한 사용자 지정 중요한 정보 유형 만들기](/microsoft-365/compliance/create-custom-sensitive-information-types-with-exact-data-match-based-classification)
- [정확한 데이터 일치 활동에 대한 알림 만들기](/microsoft-365/compliance/sit-edm-notifications-activities)
- [중요한 정보 유형 엔터티 정의](/microsoft-365/compliance/sensitive-information-type-entity-definitions)
- [PowerShell을 사용하여 사용자 지정 중요한 정보 유형 만들기](/microsoft-365/compliance/create-a-custom-sensitive-information-type-in-scc-powershell)
- [키워드 사전 만들기](/microsoft-365/compliance/create-a-keyword-dictionary)

### <a name="sensitivity-labels"></a>민감도 레이블

- **DoD 지원**. DoD 환경을 지원하는 미국 정부 테넌트 지원.
- **에 대한 암호화만 Outlook.** 사용자에 대한 Outlook 이제 사용자가 Encrypt-Only 할당할 수 있도록 허용을 선택하면 암호화 [옵션이 포함됩니다.](encryption-sensitivity-labels.md#let-users-assign-permissions)
- 앱에 기본 제공 **레이블을 Office.** Azure [](sensitivity-labels-office-apps.md#office-built-in-labeling-client-and-the-azure-information-protection-client) Information Protection 통합 레이블 지정 클라이언트가 설치되어 있는 경우 Office 앱에서 기본 제공 레이블을 적용하는 방법에 대한 지침이 업데이트되었습니다.

## <a name="february-2021"></a>2021년 2월

다음은 2월 한 달 동안 Microsoft 365 규정 준수 솔루션 및 콘텐츠에 대한 몇 가지 변경 내용입니다.

### <a name="auditing"></a>감사

- **감사 로그 보존 정책 관리.** 새 감사 보존 정책 [대시보드에 대해 자세히 알아보습니다.](/microsoft-365/compliance/audit-log-retention-policies#manage-audit-log-retention-policies-1)
- **감사 로그를 검색합니다.** [PowerShell 스크립트를 사용하여 감사 로그를 검색합니다.](/microsoft-365/compliance/audit-log-search-script)

### <a name="data-classification-content-explorer"></a>데이터 분류 콘텐츠 탐색기

다음 항목에서 콘텐츠가 추가되거나 업데이트되었습니다.

- [콘텐츠 탐색기로 시작](/microsoft-365/compliance/data-classification-content-explorer)
- [데이터 분류 릴리스 정보](/microsoft-365/compliance/data-classification-pub-preview-relnotes)

### <a name="data-loss-prevention"></a>데이터 손실 방지

다음 항목에서 콘텐츠가 추가되거나 업데이트되었습니다.

- [끝점 DLP에 대해 자세히](/microsoft-365/compliance/endpoint-dlp-learn-about)
- [DLP 정책에 대한 전자 메일 알림 보내기 및 정책 팁 표시](/microsoft-365/compliance/use-notifications-and-policy-tips)
- [데이터 손실 Microsoft 365 스캐너에 대해 자세히 알아보시고](/microsoft-365/compliance/dlp-on-premises-scanner-learn)
- [데이터 손실 방지 On-premises 스캐너 시작](/microsoft-365/compliance/dlp-on-premises-scanner-get-started)
- [FCI 또는 기타 속성을 갖는 문서를 보호하는 DLP 정책 만들기](/microsoft-365/compliance/protect-documents-that-have-fci-or-other-properties)
- [엔드포인트 데이터 손실 방지 사용](/microsoft-365/compliance/endpoint-dlp-using)
- [끝점 데이터 손실 방지 시작](/microsoft-365/compliance/endpoint-dlp-getting-started)

### <a name="ediscovery"></a>eDiscovery

다음 항목에서 콘텐츠가 추가되거나 업데이트되었습니다.

- [eDiscovery Microsoft 365 암호 해독](/microsoft-365/compliance/ediscovery-decryption)
- [키워드 쿼리 및 검색 조건](/microsoft-365/compliance/keyword-queries-and-search-conditions#limitations-for-searching-sensitive-data-types)
- [2016년 12월에 대한 Advanced eDiscovery](/microsoft-365/compliance/relevance-module-retirement)
- [스크립트를 사용하여 Core eDiscovery 사례에서 보류에 사용자 추가](/microsoft-365/compliance/use-a-script-to-add-users-to-a-hold-in-ediscovery)

### <a name="encryption"></a>암호화

다음 항목에서 콘텐츠가 추가되거나 업데이트되었습니다.

#### <a name="azure-rights-management-service-rms"></a>Azure RMS(권한 관리 서비스)

- [고객 관리 암호화 기능](/microsoft-365/compliance/office-365-customer-managed-encryption-features)
- [Exchange Online 를 사용하여 메일 암호화를 사용합니다.](/microsoft-365/compliance/information-rights-management-in-exchange-online) 이 서비스에 대한 지원은 사용되지 않습니다. 하이브리드 환경에서는 더 이상 AD RMS를 사용할 Exchange 없습니다. 대신 Azure RMS로 마이그레이션합니다.

#### <a name="customer-key"></a>고객 키

- [테넌트 Microsoft 365 대한 고객 키](/microsoft-365/compliance/customer-key-tenant-level)
- [보안 및 규정 준수 개요](/microsoftteams/security-compliance-overview)

#### <a name="information-rights-management-irm"></a>IRM(정보 권한 관리)

- [목록 또는 라이브러리에 IRM(정보 권한 관리)을 적용합니다.](/microsoft-365/compliance/configure-irm-to-use-an-on-premises-ad-rms-server) 이러한 국가 클라우드는 이 설정을 지원하지 않습니다.
  - Microsoft Cloud for US Government
  - Microsoft 클라우드 독일
  - Azure 및 Microsoft 365 중국의 21Vianet에서 운영)
- [프레미스 AD RMS 서버를 사용하도록 IRM을 구성합니다.](/microsoft-365/compliance/configure-irm-to-use-an-on-premises-ad-rms-server) 하이브리드 환경에서 이 서비스에 Exchange 더는 사용되지 않습니다.

### <a name="sensitive-information-types"></a>중요한 정보 유형

다음 항목에서 콘텐츠가 추가되거나 업데이트되었습니다.

- [중요한 정보 유형에 대해 알아보기](/microsoft-365/compliance/sensitive-information-type-learn-about)
- [PowerShell을 사용한 사용자 지정 중요한 정보 유형 만들기](/microsoft-365/compliance/create-a-custom-sensitive-information-type-in-scc-powershell)
- [정확한 데이터 매치 기반 분류를 사용하여 사용자 지정 중요한 정보 유형 만들기](/microsoft-365/compliance/create-custom-sensitive-information-types-with-exact-data-match-based-classification)
- [중요한 정보 유형 엔터티 정의](/microsoft-365/compliance/sensitive-information-type-entity-definitions)

### <a name="sensitivity-labels"></a>민감도 레이블

다음 항목에서 콘텐츠가 추가되거나 업데이트되었습니다.

- **SharePoint 공유를 구성합니다.** 컨테이너 [레이블의 경우](sensitivity-labels-teams-groups-sites.md) 현재 사이트로부터의 외부 공유에 SharePoint 사용할 수 있는 옵션이 출시되었습니다. 또한 이제 Microsoft 365 관리 센터 및 Planner는 이러한 민감도 레이블 적용을 지원하고 있습니다. 
- **공동 작성 및 자동 작성**. 암호화된 [파일에 대한](sensitivity-labels-coauthoring.md) 공동 작성 및 자동 저장 지원은 프로덕션이 아닌 테넌트에서 테스트를 위해 미리 보기로 릴리스됩니다.

## <a name="january-2021"></a>2021년 1월

### <a name="support-for-card-content-in-teams"></a>카드 콘텐츠에 대한 Teams

다음 Microsoft 365 규정 준수 솔루션은 이제 메시지에서 앱을 통해 생성된 카드 콘텐츠의 Teams 지원합니다. [](/microsoftteams/platform/task-modules-and-cards/what-are-cards)

- **Core 및 Advanced eDiscovery**. 이제 카드 콘텐츠를 [](create-ediscovery-holds.md#preserve-card-content) 보류하거나 검색에 포함될 수 있습니다(콘텐츠 검색에도 적용). [](/microsoftteams/ediscovery-investigation#search-for-card-content)
- **감사**. 이제 카드 활동이 감사 [로그에 기록됩니다.](/microsoftteams/audit-log-events#teams-activities)
- **보존 정책**. 이제 보존 정책을 사용하여 카드 콘텐츠를 [보존하고 삭제할 수 있습니다.](retention-policies-teams.md#whats-included-for-retention-and-deletion)

### <a name="information-governance-and-records-management"></a>정보 거버넌스 및 레코드 관리

[정보](retention-regulatory-requirements.md#new-zealand-public-records-act) 거버넌스 및 레코드 관리를 사용하여 뉴질랜드 공용 레코드 법에 대한 규정 준수 의무를 충족하는 데 도움이 되는 새로운 평가입니다.

### <a name="sensitivity-labels"></a>민감도 레이블

- 이제 미국 정부 테넌트(GCC 및 GCC-H)에 대해 민감도 레이블이 지원됩니다.
- [macOS에 대한 새로운](sensitivity-labels-office-apps.md) 자동 레이블 지정 지원.

## <a name="december-2020"></a>2020년 12월

### <a name="spotlight-new-content-for-insider-risk-solutions"></a>스포트라이트: 내부자 위험 솔루션에 대한 새 콘텐츠

Microsoft 365 규정 준수 콘텐츠 팀은 규정 준수 기능을 함께 사용하여 규정 준수 목표를 달성하는 방법을 홍보하기 위해 '콘텐츠 솔루션' docs를 만들기 위해 노력합니다.

먼저 커뮤니케이션 규정 준수, 내부자 위험 관리, 정보 장벽 및 권한 있는 액세스 관리와 같은 내부자 위험 솔루션을 함께 연계하는 콘텐츠입니다. 다음은 찾을 수 있는 정보를 한 가지 예입니다.

- [내부자 위험 솔루션에 대한 새 방문 페이지입니다.](insider-risk-solution-overview.md) 솔루션이 완화하는 데 도움이 될 수 있는 위험에 대한 세부 정보, 라이선스 요구 사항, 배포 시퀀스, 아키텍처 일러스트레이션, 교육 리소스 등
- 각 내부자 위험 솔루션에 대한 새로운 개요 문서입니다. 각 솔루션을 학습, 계획, 배포 및 관리하는 데 도움이 되는 문서에 대한 지침 및 링크:
  - [커뮤니케이션 규정 준수](communication-compliance-solution-overview.md)
  - [내부자 위험 관리](insider-risk-management-solution-overview.md)
  - [정보 장벽](information-barriers-solution-overview.md)
  - [권한이 부여된 액세스 관리](privileged-access-management-solution-overview.md)

곧 더 많은 콘텐츠 솔루션 docs가 제공될 예정입니다!

### <a name="advanced-ediscovery"></a>Advanced eDiscovery

관리인 및 비보조 데이터 원본을 추가하는 워크플로 및 기능이 Advanced eDiscovery 있습니다. [](add-custodians-to-case.md) [](non-custodial-data-sources.md)

### <a name="data-connectors"></a>데이터 커넥터

[4개의 새로운 Veritas](archiving-third-party-data.md#third-party-data-connectors)커넥터가 출시되었습니다. Redtail Speak, Salesforce Chatter, ServiceNow 및 Yieldbroker.

### <a name="encryption"></a>암호화

테넌트 수준에서 [Microsoft 365 고객 키를 소개합니다.](customer-key-tenant-level.md) 제공한 키를 사용하여 DEP(데이터 암호화 정책)를 만들어 테넌트에 할당할 수 있습니다. DEP는 이러한 워크로드에 대해 테넌트 전체의 데이터를 암호화합니다.

- Teams 채팅 메시지(1:1 채팅, 그룹 채팅, 모임 채팅 및 채널 대화)
- Teams 미디어 메시지(이미지, 코드, 비디오, 위키 이미지)
- Teams 저장소에 저장된 통화 및 모임 Teams 기록
- Teams 알림
- Teams 채팅 제안을 Cortana
- Teams 메시지 표시
- 사용자 및 사용자에 대한 Exchange Online

### <a name="records-management"></a>레코드 관리

레코드 [관리 관리 역할 그룹은](get-started-with-records-management.md#permissions-required-for-records-management) 이제 모든 레코드 관리 기능에 대한 사용 권한을 부여합니다(삭제 검토 포함).

### <a name="sensitivity-labels"></a>민감도 레이블

- [Azure Purview(미리](/azure/purview/create-sensitivity-label)보기)에서 자동으로 데이터에 레이블을 지정합니다. 이제 Azure Blob Storage의 파일 및 Azure의 데이터베이스 열과 같은 Azure Purview의 자산에 민감도 레이블을 만들고 자동으로 적용할 수 SQL Server.
- [사용자에게 항목에 레이블을 적용해야 합니다.](sensitivity-labels-office-apps.md#require-users-to-apply-a-label-to-their-email-and-documents) '필수 레이블 지정'으로도 알려진 이 새 옵션을 사용하려면 사용자가 특정 시나리오에서 민감도 레이블을 선택하고 적용해야 합니다.
