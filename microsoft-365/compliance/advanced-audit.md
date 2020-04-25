---
title: Microsoft 365의 고급 감사
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Microsoft 365의 고급 감사는 조직에서 법의학 및 규정 준수 조사를 수행하는 데 도움이 되는 새로운 감사 기능을 제공합니다.
ms.openlocfilehash: b1a79598fc49d710c54a23dc9ce92c9f2b7f5805
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632283"
---
# <a name="advanced-audit-in-microsoft-365"></a>Microsoft 365의 고급 감사

Microsoft 365의 [통합 감사 기능](search-the-audit-log-in-security-and-compliance.md)은 조직에 Microsoft 365의 여러 서비스에서 다양한 유형의 감사 활동에 대한 가시성을 제공합니다. 이제 Microsoft 365의 고급 감사가 릴리스되면서 조직에서 법의학 및 규정 준수 조사를 수행하는 데 도움이 되는 새로운 감사 기능이 추가되었습니다.

> [!NOTE]
> Office 365 E5 또는 Microsoft 365 Enterprise E5 라이선스 있는 조직의 경우 고급 감사 기능을 사용할 수 있습니다. 또한 감사 로그의 장기 보존 및 조사를 위한 중요 이벤트에 대한 액세스와 같이 고급 감사 기능에 사용자별 라이선스가 필요한 경우 Microsoft 365 E5 규정 준수 추가 기능 라이선스를 사용자에게 할당할 수 있습니다.

이 문서는 이러한 고급 감사 기능에 대한 개요를 제공합니다.

## <a name="long-term-retention-of-audit-logs"></a>감사 로그의 장기 보존

고급 감사는 1년 동안 모든 Exchange, SharePoint 및 Azure Active Directory 감사 레코드를 보존합니다. 이는 1년 동안의 **워크로드** 속성(활동이 발생한 서비스를 나타냄)에 대한 **Exchange**, **SharePoint ** 또는 **AzureActiveDirectory** 값을 포함하는 모든 감사 레코드를 보유하는 기본 감사 로그 보유 정책에 의해 수행됩니다. 이는 진행 중인 법의학 또는 규정 준수 조사에 도움이 됩니다. 자세한 정보는 [감사 로그 보존 정책 관리](audit-log-retention-policies.md#default-audit-log-retention-policy)의 "기본 감사 로그 보존 정책"섹션을 참조하십시오.

## <a name="audit-log-retention-policies"></a>로그 보존 정책 감사

기본 감사 로그 보존 정책에 포함되지 않은 다른 서비스에서 생성된 모든 감사 레코드(이전 섹션에서 설명)는 90일 동안 보존됩니다. 그러나 이제는 최대 1년 동안 다른 감사 레코드를 유지하기 위해 사용자 지정된 감사 로그 보존 정책을 생성할 수 있습니다. 다음 기준 중 하나 이상을 기반으로 감사 레코드를 유지하는 정책을 생성할 수 있습니다.

- 감사되는 활동이 발생하는 Microsoft 365 서비스

- 감사되는 구체적 활동

- 감사되는 활동을 수행하는 사용자

특정 정책이 다른 정책보다 우선하도록 정책 및 우선순위 수준과 일치하는 감사 레코드에 대한 보존 기간을 지정할 수도 있습니다. 또한 조직의 일부 또는 모든 사용자에 대해 Exchange, SharePoint 또는 Azure Active Directory 감사 레코드를 1년 미만 동안 유지해야하는 경우 사용자 지정 감사 로그 보존 정책이 기본 감사 보존 정책보다 우선합니다. 자세한 내용은 [감사 로그 보존 정책 관리](audit-log-retention-policies.md)를 참조하십시오.

## <a name="access-to-crucial-events-for-investigations"></a>조사에 대한 중요 이벤트 액세스

중요한 보안 및 준수 관련 감사 이벤트는 가능한 위반사항 또는 기타 법의학 관련 조사를 조사하는 데 도움이 되는 감사 이벤트입니다. Microsoft가 발표하는 첫 번째 중요한 이벤트는 *MailItemsAccessed* 사서함 감사 작업입니다. 이 작업은 메일 프로토콜 및 메일 클라이언트가 메일 데이터에 액세스할 때 트리거됩니다. MailItemsAccessed 작업은 조사자가 데이터 유출을 식별하고 손상되었을 수 있는 메시지 범위를 결정하는 데 도움이 됩니다. 공격자가 전자 메일 메시지에 액세스한 경우 실제로 메시지를 읽었다는 명시적인 신호가 없는 경우에도 MailItemsAccessed 작업이 트리거됩니다(즉, 바인딩 또는 동기화를 통한 액세스 유형이 감사 레코드에 기록됨).

새로운 MailItemsAccessed 사서함 작업은 Exchange Online의 사서함 감사 로깅에서 MessageBind를 대체하고 다음과 같은 향상된 기능을 제공합니다.

- MessageBind는 AuditAdmin 사용자 로그온 유형에 대해서만 구성 할 수 있었습니다. 대리인 또는 소유자 조치에는 적용되지 않았습니다. MailItemsAccessed는 모든 로그온 유형에 적용됩니다.

- MessageBind는 메일 클라이언트만 액세스할 수 있었습니다. MessageBind는 동기화 활동에는 적용되지 않았습니다. MailItemsAccessed 이벤트는 바인딩 및 동기화 액세스 유형에 의해 트리거됩니다.

- MessageBind 작업은 동일한 전자 메일 메시지에 액세스할 때 여러 감사 레코드가 생성되어 "노이즈" 감사가 발생합니다. 반대로 MailItemsAccessed 이벤트는 더 적은 감사 레코드로 집계됩니다.

MailItemsAccessed 액세스 활동의 감사 레코드에 대한 자세한 내용은 [고급 감사를 사용하여 손상된 계정 조사](mailitemsaccessed-forensics-investigations.md)를 참조하세요.

### <a name="search-for-mailitemsaccessed-audit-records"></a>MailItemsAccessed 감사 레코드 검색

MailItemsAccessed 감사 레코드를 검색하려면 보안 및 준수 센터의 [감사 로그 검색 도구](search-the-audit-log-in-security-and-compliance.md)의 **Exchange 사서함 활동** 드롭다운 목록에서 **액세된한 사서함 항목** 활동을 검색할 수 있습니다.

![감사 로그 검색 도구에서 MailItemsAccessed 작업 검색](../media/MailItemsAccessedSCC1.png)

Exchange Online PowerShell에서 [Search-UnifiedAuditLog -Operations MailItemsAccessed](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog) 또는 [Search-MailboxAuditLog -Operations MailItemsAccessed](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-mailboxauditlog) 명령을 실행할 수도 있습니다.

## <a name="high-bandwidth-access-to-the-office-365-management-activity-api"></a>Office 365 관리 활동 API에 대한 고 대역폭 액세스

Office 365 관리 활동 API를 통해 감사 로그에 액세스하는 조직은 게시자 수준에서 제한을 스로틀링하여 제한되었습니다. 이는 여러 고객을 대신하여 데이터를 가져 오는 게시자의 경우 모든 고객이 한도를 공유했음을 의미합니다.

고급 감사가 릴리스됨에 따라 Microsoft는 게시자 수준 제한에서 테넌트 수준 제한으로 전환하고 있습니다. 결과적으로 각 조직은 감사 데이터에 액세스하기 위해 자체 할당된 대역폭 할당량을 얻게 됩니다. 대역폭은 사전 정의된 정적 제한이 아니지만 조직의 자리 수를 포함하여 E5 조직이 E5 이외의 조직보다 더 많은 대역폭을 갖도록 여러 요인을 조합하여 모델링되었습니다.

모든 조직에는 처음에 분당 2,000건의 요청 기준이 할당됩니다. 이 한도는 조직의 라이선스 수와 라이선스 구독에 따라 동적으로 증가합니다. E5 조직은 E5 이외의 조직보다 약 2배의 대역폭을 얻게됩니다. 또한 서비스 상태를 보호하기 위해 최대 대역폭에 제한이 있습니다.

자세한 내용은 [Office 365 관리 활동 API 참조](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#api-throttling)의 "API 조절"섹션을 참조하십시오.

## <a name="faqs-for-advanced-audit"></a>고급 감사를 위한 FAQ

**고급 감사는 어디서 액세스할 수 있나요?**

고급 감사가 조직에 배포된 후에 [보안 및 준수 센터](https://protection.office.com)의 감사 로그 검색 도구를 사용하여 감사 로그 보존 정책을 만들고 MailItemsAccessed 감사 레코드를 검색할 수 있습니다. 몇 주 안에 [Microsoft 365 규정 준수 센터](https://compliance.microsoft.com)에 고급 감사를 배포하기 위해 노력하고 있습니다.

**고급 감사를 활용하려면 모든 사용자에게 E5 라이선스가 필요한가요?**

사용자 수준 고급 감사 기능을 활용하려면 사용자에게 E5 라이선스가 할당되어야 합니다. 사용자에게 기능을 표시하기 위해 적절한 라이선스를 확인하는 몇 가지 기능이 있습니다. 예를 들어, 90일 이상 E5 라이선스가 할당되지 않은 사용자에 대한 감사 레코드를 보존하려고 하면 시스템에서 오류 메시지가 반환됩니다.

**E5 구독과 E5 라이선스가 할당된 사용자가 있지만 조직에서 고급 감사를 볼 수 없는 이유는 무엇인가요?**

적합한 라이선스가 있더라도 고급 감사 기능(예: 감사 로그 보존 정책을 만드는 기능 및 MailItemsAccessed 감사 레코드 로깅)을 조직에서 사용할 수 없는 경우가 있을 수 있습니다. 이 문제가 발생하는 경우에는 고급 감사 패키지가 아직 조직에 배포되지 않았기 때문입니다. 이것은 다음 몇 주 안에 영향을 받는 조직에서 해결해야 하는 일시적인 라이선스 백필 문제입니다. 이 문제를 완화하려면 각 E5 사용자에 대해 다음 단계를 수행하세요.

1. Microsoft 365 관리 센터에서 **사용자 > 활성 사용자**로 이동하여 사용자를 선택합니다.

2. 사용자 속성 플라이아웃 페이지에서 **라이선스 및 앱**을 클릭합니다.

3. **앱** 섹션을 확장한 후 다음 중 하나를 수행합니다.

   a. **Microsoft 365 고급 감사** 확인란이 선택되어 있지 않은 경우 확인란을 선택하고 **변경 내용을 저장**을 클릭합니다. 이 사용자의 MailItemsAccessed 작업에 대한 감사 레코드는 24시간 이내에 검색할 수 있어야 합니다.

   b. **Microsoft 365 고급 감사** 확인란이 선택되어 있는 경우 선택을 취소하고 **변경 내용을 저장**을 클릭합니다. 4단계를 참조하세요.

4. 3단계에서 확인란의 선택을 취소한 경우 60분 정도 기다린 다음 3a 단계를 반복하여 Microsoft 365 고급 감사 앱을 설정합니다.

**조직이 감사 기록을 1년간 보유하는 비공개 미리 보기에 있는 경우 어떻게 되나요?**

미리 보기 프로그램의 감사 보존 정책은 사용자 지정 감사 보존 정책으로 재정의하고 변경하지 않는 한 유지됩니다.

**조직에서 1년보다 오래 감사 로그를 보존하려면 어떻게 하나요?**

감사 레코드에 더 긴 보존 기간을 제공하는 방법에 대한 옵션을 탐색하고 있습니다. [Office 365 User Voice](https://office365.uservoice.com/forums/289138-office-365-security-compliance?category_id=137187)에서 더 오래 감사 레코드가 보존에 대한 피드백을 제공할 수 있습니다.

**조직에 E5 구독이 있습니다. MailItemsAccessed 이벤트에 대한 감사 레코드 액세스 권한을 얻으려면 어떤 작업을 수행해야 하나요?**

적격 고객에게는 MailItemsAccessed 이벤트에 대한 액세스를 얻기 위한 조치가 없습니다. 그러나 앞서 이 항목에서 설명한 것처럼 라이선스 백필 문제 때문에 발생하는 대기 시간으로 인해 MailItemsAccessed 이벤트에 대한 감사 레코드가 감사 로그 검색에 반환되지 않을 수 있습니다. 이 경우에는 MailItemsAccessed 감사 레코드 검색 섹션의 지침을 따르세요.

**올해 추가 이벤트를 릴리스할 계획인가요?**

예, 앞으로 몇 달 안에 조사에 중요한 새 이벤트를 출시할 계획입니다. 이 새 이벤트에 대한 정보는 릴리스 날짜가 가까워지면 [Microsoft 365 로드맵](https://www.microsoft.com/microsoft-365/roadmap)에 게시하겠습니다.

**고급 감사의 새 이벤트는 Office 365 관리 작업 API에서 사용할 수 있나요?**

예. 적절한 라이선스가 있는 사용자에 대한 감사 레코드가 생성되는 한 Office 365 관리 작업 API를 통해 이러한 레코드에 액세스할 수 있습니다.

**대역폭이 높을수록 지연 시간이 개선되거나 더 높은 SLA를 의미하나요?**

현재 높은 대역폭을 사용하면 더 나은 파이프라인을 제공하고 특히 감사 신호가 많고 상당한 소비 패턴을 보유하고 있는 조직에 적합합니다. 이로 인해 대기 시간이 개선될 수 있습니다. 그러나 고대역폭과 관련된 SLA는 없습니다. 표준 대기 시간이 문서화되어 있으면 고급 감사를 릴리스와 함께 변경되지 않습니다.
