---
title: Microsoft 365 감사 솔루션
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- m365-security-compliance
- m365solution-audit
- m365initiative-compliance
- m365solution-overview
search.appverid:
- MOE150
- MET150
description: Microsoft 365 조직의 사용자와 관리자의 활동을 감사하는 방법에 대해 알아 보세요.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fbd00bdff46bebb73535f2b24c1b0bfa997dd55a
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60163435"
---
# <a name="auditing-solutions-in-microsoft-365"></a>Microsoft 365의 감사 솔루션

Microsoft 365 감사 솔루션은 조직이 보안 이벤트, 법의학적 조사, 내부 조사 및 규정 준수 의무에 효과적으로 대응할 수 있도록 지원하는 통합 솔루션을 제공합니다. 수십 개의 Microsoft 365 서비스 및 솔루션에서 수행되는 수천 개의 사용자 및 관리 작업이 조직의 통합 감사 로그에 캡처, 기록 및 보존됩니다. 이러한 이벤트에 대한 감사 기록은 보안 운영자, IT 관리자, 내부자 위험 팀, 조직의 규정 준수 및 법률 조사관이 검색할 수 있습니다. 이 기능을 사용하면 Microsoft 365 조직 전체에서 수행되는 작업을 볼 수 있습니다.

## <a name="microsoft-365-auditing-solutions"></a>Microsoft 365 감사 솔루션

Microsoft 365는 기본 감사 및 고급 감사라는 두 가지 감사 솔루션을 제공합니다.

![기본 감사 및 고급 감사의 주요 기능.](..\media\AuditingSolutionsComparison.png)

### <a name="basic-audit"></a>기본 감사

기본 감사 기능은 감사된 활동을 기록 및 검색하고 법의학, IT, 규정 준수 및 법적 조사를 수행할 수 있는 기능을 제공합니다.

- **기본적으로 사용 설정** 됩니다. 기본 감사는 해당 구독이 있는 모든 조직에 대해 기본적으로 설정됩니다. 이는 감사된 활동에 대한 기록을 캡처하고 검색할 수 있음을 의미합니다. 필요한 유일한 설정은 감사 로그 검색 도구(및 해당 cmdlet)에 액세스하는 데 필요한 사용 권한을 할당하고 사용자의 에 고급 감사 기능에 올바른 라이선스가 할당되었는지 확인하는 것입니다.
- **수천 개의 검색 가능한 감사 이벤트**. 조직의 대부분의 Microsoft 365 서비스에서 발생하는 광범위한 감사 활동을 검색할 수 있습니다. 검색할 수 있는 작업의 일부 목록은 [감사 활동](search-the-audit-log-in-security-and-compliance.md#audited-activities)을 참조하세요. 감사된 작업을 지원하는 서비스 및 기능 목록은 [감사 로그 레코드 유형](/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype)을 참조하세요.
- **Microsoft 365 규정 준수 센터의 감사 검색 도구**. Microsoft 365 규정 준수 센터의 감사 로그 검색 도구를 사용하여 감사 레코드를 검색합니다. 특정 활동, 특정 사용자가 수행한 활동 및 날짜 범위로 발생한 활동을 검색할 수 있습니다. 다음은 규정 준수 센터에 있는 감사 검색 도구의 스크린샷입니다.

   ![Microsoft 365 규정 준수 센터의 감사 로그 검색 도구.](../media/AuditLogSearchToolMCC.png)

- **Search-UnifiedAuditLog cmdlet**. Exchange Online PowerShell의 **Search-UnifiedAuditLog** cmdlet(검색 도구의 기본 cmdlet)을 사용하여 감사 이벤트를 검색하거나 스크립트에서 사용할 수도 있습니다. 자세한 정보는 다음을 참조하세요.

  - [Search-UnifiedAuditLog cmdlet 참조](/powershell/module/exchange/search-unifiedauditlog)
  - [PowerShell 스크립트를 사용하여 감사 로그 검색](audit-log-search-script.md)

- **감사 레코드를 CSV 파일로 내보내기**. 규정 준수 센터에서 감사 로그 검색 도구를 실행한 후 검색에 의해 반환된 감사 레코드를 CSV 파일로 내보낼 수 있습니다. 이렇게 하면 Microsoft Excel 정렬 및 필터 기능을 여러 감사 레코드 속성에서 사용할 수 있습니다. Excel 파워 쿼리 변환 기능을 사용하여 AuditData JSON 개체의 각 속성을 자체 열로 분할할 수도 있습니다. 이렇게 하면 서로 다른 이벤트에 대한 유사한 데이터를 효과적으로 보고 비교할 수 있습니다. 자세한 내용은 [감사 로그 레코드 내보내기, 구성 및 보기](export-view-audit-log-records.md)를 참조하세요.

- **Office 365 Management Activity API를 통해 감사 로그에 액세스**. 감사 레코드를 액세스하고 검색하는 세 번째 방법은 Office 365 Management Activity API를 사용하는 것입니다. 이를 통해 조직은 감사 데이터를 기본 90일보다 오랜 기간 동안 보존하고 감사 데이터를 SIEM 솔루션으로 가져올 수 있습니다. 자세한 내용은 [Office 365 관리 작업 API 참조](/office/office-365-management-api/office-365-management-activity-api-reference)를 참조하세요.

- **90일 감사 로그 보존 기간**. 사용자 또는 관리자가 감사되는 활동을 수행하면 감사 레코드가 생성되어 조직의 감사 로그에 저장됩니다. 기본 감사에서 레코드는 90일 동안 유지되므로 지난 3개월 내에 발생한 활동을 검색할 수 있습니다.

### <a name="advanced-audit"></a>고급 감사

고급 감사는 감사 로그 보존 정책, 감사 기록의 장기 보존, 고부가가치 중요 이벤트 및 Office 365 Management Activity API에 대한 높은 대역폭 액세스 기능을 제공함으로써 기본 감사 기능을 기반으로 합니다.

- **감사 로그 보존 정책**. 사용자 정의된 감사 로그 보존 정책을 생성하여 감사 레코드를 최대 1년(필요한 추가 기능 라이선스를 가진 사용자의 경우 최대 10년)까지 더 오래 유지할 수 있습니다. 감사된 활동이 발생하는 서비스, 특정 감사된 활동 또는 감사된 활동을 수행하는 사용자를 기준으로 감사 레코드를 보관하는 정책을 만들 수 있습니다.

- **더 길어진 감사 레코드의 보존** Exchange, SharePoint 및 Azure Active Directory 감사 레코드는 기본적으로 1년 동안 유지됩니다. 다른 모든 활동에 대한 감사 레코드는 기본적으로 90일 동안 보존되거나 감사 로그 보존 정책을 사용하여 더 긴 보존 기간을 구성할 수 있습니다.

- **가치가 높고 중요한 고급 감사 이벤트**. 중요한 이벤트에 대한 감사 레코드는 전자 메일 항목에 액세스한 시점, 전자 메일 항목에 대한 회신 및 전달 시점, Exchange 온라인 및 SharePoint 온라인에서 사용자가 검색한 시기와 내용과 같은 이벤트에 대한 가시성을 제공하여 조직이 법의학 및 규정 준수 조사를 수행하는 데 도움이 될 수 있습니다. 이러한 중요한 이벤트는 가능한 위반을 조사하고 절충 범위를 결정하는 데 도움이 될 수 있습니다.

- **Office 365 관리 활동 API에 대한 고 대역폭**. 고급 감사는 Office 365 관리 활동 API를 통해 감사 로그에 액세스할 수 있는 더 많은 대역폭을 조직에 제공합니다. 기본 감사 또는 고급 감사 기능이 있는 모든 조직에는 처음에는 분당 2,000개의 요청이 할당되지만, 이 제한은 조직의 좌석 수와 라이선스 가입에 따라 동적으로 증가합니다. 따라서 고급 감사 기능이 있는 조직은 기본 감사 기능이 있는 조직보다 약 두 배 더 많은 대역폭을 얻게 됩니다.

고급 감사 기능에 대한 자세한 내용은 [Microsoft 365의 고급 감사](advanced-audit.md)를 참조하세요.

## <a name="comparison-of-key-capabilities"></a>주요 기능 비교

다음 표에서는 기본 감사와 고급 감사에서 사용할 수 있는 주요 기능을 비교합니다. 모든 기본 감사 기능은 고급 감사에 포함됩니다.

|기능|기본 감사|고급 감사|
|:------|:-------------|:-------------|
|기본적으로 사용|![지원됨.](../media/check-mark.png)|![지원됨.](../media/check-mark.png)|
|수천 개의 검색 가능한 감사 이벤트|![지원됨.](../media/check-mark.png)|![지원됨.](../media/check-mark.png)|
|Microsoft 365 규정 준수 센터의 감사 검색 도구|![지원됨.](../media/check-mark.png)|![지원됨.](../media/check-mark.png)|
|Search-UnifiedAuditLog cmdlet|![지원됨.](../media/check-mark.png)|![지원됨.](../media/check-mark.png)|
|CSV 파일로 감사 레코드 내보내기|![지원됨.](../media/check-mark.png)|![지원됨.](../media/check-mark.png)|
|Office 365 관리 작업 API를 통해 감사 로그에 액세스<sup>1</sup>.|![지원됨.](../media/check-mark.png)|![지원됨.](../media/check-mark.png)</sup>|
|90일 감사 로그 보존|![지원됨.](../media/check-mark.png)|![지원됨.](../media/check-mark.png)|
|1년 감사 로그 보존||![지원됨.](../media/check-mark.png)|
|10년 감사 로그 보존 기간 <sup>2</sup>||![지원](../media/check-mark.png)|
|로그 보존 정책 감사||![지원](../media/check-mark.png)|
|가치가 높고 중요한 이벤트||![지원](../media/check-mark.png)|
||||
> [!NOTE]
> <sup>1</sup> 고급 감사에는 감사 데이터에 대한 더 빠른 액세스를 제공하는 Office 365 관리 활동 API에 대한 더 높은 대역폭 액세스가 포함됩니다.<br/><sup>2</sup> 고급 감사에 필요한 라이선스(다음 섹션에서 설명) 외에 감사 레코드를 10년 동안 유지하려면 사용자에게 라이선스에 10년 감사 로그 보존 추가가 할당되어야 합니다.

## <a name="licensing-requirements"></a>라이선스 요구사항

다음 섹션에서는 기본 감사 및 고급 감사에 대한 라이선싱 요구 사항을 식별합니다. 기본 감사 기능은 고급 감사에 포함됩니다.

### <a name="basic-audit"></a>기본 감사

- Microsoft 365 Enterprise E3 구독
- Microsoft 365 Business Premium
- Microsoft 365 Education A3 구독
- Microsoft 365 Government G3 구독
- Microsoft 365 Government G1 구독
- Microsoft 365 Frontline F1 또는 F3 구독 또는 F5 보안 추가 기능
- Office 365 Enterprise E3 구독
- Office 365 Enterprise E1 구독
- Office 365 Education A1 구독
- Office 365 Education A3 구독

### <a name="advanced-audit"></a>고급 감사

- Microsoft 365 Enterprise E5 구독
- Microsoft 365 Enterprise E3 구독 + Microsoft 365 E5 규정 준수 추가 기능
- Microsoft 365 Enterprise E3 구독 + Microsoft 365 E5 eDiscovery 및 감사 추가 기능
- Microsoft 365 Education A5 구독
- Microsoft 365 Education A3 구독 + Microsoft 365 A5 규정 준수 추가 기능
- Microsoft 365 Education A3 구독 + Microsoft 365 A5 eDiscovery 및 감사 추가 기능
- Microsoft 365 Government G5 구독
- Microsoft 365 Government G5 구독 + Microsoft 365 G5 규정 준수 추가 기능
- Microsoft 365 Government G5 구독 + Microsoft 365 G5 eDiscovery 및 감사 추가 기능
- Microsoft 365 Frontline F5 규정 준수 또는 F5 보안 및 규정 준수 추가 기능
- Office 365 Enterprise E5 구독
- Office 365 Education A5 구독
- Office 365 Enterprise E3 구독 + Office 365 Advanced Compliance 추가 기능(더 이상 새 구독에는 사용할 수 없음)

## <a name="set-up-microsoft-365-auditing-solutions"></a>Microsoft 365 감사 솔루션 설정

Microsoft 365의 감사 솔루션 사용을 시작하려면 다음 설정 지침을 참조하세요.

### <a name="set-up-basic-audit"></a>기본 감사 설정

첫 번째 단계는 기본 감사를 설정한 다음 감사 로그 검색 실행을 시작하는 것입니다.

![기본 감사 설정 워크플로.](../media/BasicAuditingWorkflow.png)

1. 조직에 기본 감사를 지원하는 구독이 있는지와 해당되는 경우 고급 감사를 지원하는 구독이 있는지 확인해야 합니다.

2. Microsoft 365 규정 준수 센터에서 감사 로그 검색 도구를 사용하거나 **Search-UnifiedAuditLog** cmdlet를 사용할 조직의 사용자에게 Exchange Online의 사용 권한을 할당합니다. 특히, Exchange Online에서 보기 전용 감사 로그 또는 감사 로그 역할이 할당되어야 합니다.

3. 감사 로그를 검색합니다. 1단계와 2단계를 완료한 후 조직의 사용자는 감사 로그 검색 도구(또는 해당 cmdlet)를 사용하여 감사된 활동을 검색할 수 있습니다.

자세한 지침은 [기본 감사 설정](set-up-basic-audit.md)을 참고하세요.

### <a name="set-up-advanced-audit"></a>고급 감사 설정

조직에 고급 감사를 지원하는 구독이 있는 경우 다음 단계를 수행하여 고급 감사의 추가 기능을 설정하고 사용하세요.

![고급 감사 설정 워크플로.](../media/AdvancedAuditWorkflow.png)

1. 사용자에 대한 고급 감사 설정 이 단계는 다음과 같은 작업으로 구성됩니다.

   - 사용자에게 고급 감사에 대한 적절한 라이선스 또는 추가 기능 라이선스가 할당되어 있는지 확인
  
   - 해당 사용자에 대해 고급 감사 앱/서비스 계획을 켜야 합니다.
  
   - 중요한 이벤트에 대한 감사를 활성화한 다음 해당 사용자에 대해 고급 감사 앱/서비스 계획을 켜면 됩니다.

2. 사용자가 Exchange Online 및 SharePoint Online에서 검색을 수행할 때 고급 감사 이벤트를 기록할 수 있도록 설정합니다.

3. 감사 로그 보존 정책을 설정합니다. Exchange, SharePoint 및 Azure AD 감사 레코드를 1년 동안 유지하는 기본 정책에 더해 조직의 보안 작업, IT 및 규정 준수 팀의 요구 사항을 충족하는 추가 감사 로그 보존 정책을 만들 수 있습니다.

4. 법의학 조사를 수행할 때 중요한 고급 감사 이벤트 및 기타 활동을 검색합니다. 1단계와 2단계를 완료한 후 손상된 계정 및 기타 유형의 보안 또는 규정 준수 조사를 수행하는 동안 감사 로그를 검색하여 고급 감사 이벤트 및 기타 활동을 확인할 수 있습니다.

자세한 지침은 [고급 감사 설정](set-up-advanced-audit.md)을 참고하세요.

## <a name="training"></a>교육

기본 감사 및 고급 감사의 기본 사항에서 보안 운영 팀, IT 관리자 및 규정 준수 조사 팀을 교육하면 감사 기능을 사용하여 조사를 보다 신속하게 시작할 수 있습니다. Microsoft 365는 조직의 이러한 사용자가 감사를 시작하는 데 도움이 되는 다음과 같은 리소스를 제공합니다. [Microsoft 365의 eDiscovery 및 감사 기능에 대해 설명합니다](/learn/modules/describe-ediscovery-capabilities-of-microsoft-365).
