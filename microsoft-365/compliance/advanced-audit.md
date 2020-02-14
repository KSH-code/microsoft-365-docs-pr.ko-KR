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
ms.openlocfilehash: e06e7f6330a36c8f98042fcce472b7baf6ef16ff
ms.sourcegitcommit: c2a36b16e354e20db5fd6275175ca856eae55bfc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/12/2020
ms.locfileid: "41960244"
---
# <a name="advanced-audit-in-microsoft-365"></a>Microsoft 365의 고급 감사

Microsoft 365의 [통합 감사 기능](search-the-audit-log-in-security-and-compliance.md)은 조직에 Microsoft 365의 여러 서비스에서 다양한 유형의 감사 활동에 대한 가시성을 제공합니다. 이제 Microsoft 365의 고급 감사가 릴리스되면서 조직에서 법의학 및 규정 준수 조사를 수행하는 데 도움이 되는 새로운 감사 기능이 추가되었습니다.

> [!NOTE]
> Office 365 또는 Microsoft 365 Enterprise E5 구독이 있는 조직의 경우 고급 감사 기능을 사용할 수 있습니다. 또한 감사 로그의 장기 보존 및 높은 값의 감사 이벤트의 경우와 같이 고급 감사 기능에 사용자별 라이선스가 필요한 경우 Microsoft 365 E5 규정 준수 추가 기능 구독을 사용자에게 할당할 수 있습니다.

이 문서는 이러한 고급 감사 기능에 대한 개요를 제공합니다.

## <a name="long-term-retention-of-audit-logs"></a>감사 로그의 장기 보존

고급 감사는 1년 동안 모든 Exchange, SharePoint 및 Azure Active Directory 감사 레코드를 보존합니다. 이는 1년 동안의 **워크로드** 속성(활동이 발생한 서비스를 나타냄)에 대한 **Exchange**, **SharePoint ** 또는 **AzureActiveDirectory** 값을 포함하는 모든 감사 레코드를 보유하는 기본 감사 로그 보유 정책에 의해 수행됩니다. 이는 진행 중인 법의학 또는 규정 준수 조사에 도움이 됩니다. 자세한 정보는 [감사 로그 보존 정책 관리](audit-log-retention-policies.md#default-audit-log-retention-policy)의 "기본 감사 로그 보존 정책"섹션을 참조하십시오.

## <a name="audit-log-retention-policies"></a>로그 보존 정책 감사

기본 감사 로그 보존 정책에 포함되지 않은 다른 서비스에서 생성된 모든 감사 레코드(이전 섹션에서 설명)는 90일 동안 보존됩니다. 그러나 이제는 최대 1년 동안 다른 감사 레코드를 유지하기 위해 사용자 지정된 감사 로그 보존 정책을 생성할 수 있습니다. 다음 기준 중 하나 이상을 기반으로 감사 레코드를 유지하는 정책을 생성할 수 있습니다.

- 감사되는 활동이 발생하는 Microsoft 365 서비스

- 감사되는 구체적 활동

- 감사되는 활동을 수행하는 사용자

특정 정책이 다른 정책보다 우선하도록 정책 및 우선순위 수준과 일치하는 감사 레코드에 대한 보존 기간을 지정할 수도 있습니다. 또한 조직의 일부 또는 모든 사용자에 대해 Exchange, SharePoint 또는 Azure Active Directory 감사 레코드를 1년 미만 동안 유지해야하는 경우 사용자 지정 감사 로그 보존 정책이 기본 감사 보존 정책보다 우선합니다. 자세한 내용은 [감사 로그 보존 정책 관리](audit-log-retention-policies.md)를 참조하십시오.

## <a name="high-value-audit-events"></a>가치가 높은 감사 이벤트

가치가 높은 보안 및 준수 관련 감사 이벤트는 가능한 위반사항 또는 기타 법의학 관련 조사를 조사하는 데 도움이 되는 감사 이벤트입니다. Microsoft가 발표하는 첫 번째 고 가치 이벤트는 *MailItemsAccessed* 사서함 감사 이벤트입니다. 이 이벤트는 메일 프로토콜 및 클라이언트가 메일 데이터에 액세스할 때 트리거됩니다. MailItemsAccessed 이벤트는 조사자가 데이터 유출을 식별하고 손상되었을 수 있는 메시지 범위를 결정하는 데 도움이됩니다. 공격자가 전자 메일 메시지에 액세스한 경우 실제로 메시지를 읽었다는 명시적인 신호가 없는 경우에도 MailItemsAccessed 이벤트가 트리거됩니다(즉, 바인딩 또는 동기화를 통한 액세스 유형이 감사 레코드에 기록됨).

새로운 MailItemsAccessed 사서함 작업은 Exchange Online의 사서함 감사 로깅에서 MessageBind를 대체하고 다음과 같은 향상된 기능을 제공합니다.

- MessageBind는 AuditAdmin 사용자 로그온 유형에 대해서만 구성 할 수 있었습니다. 대리인 또는 소유자 조치에는 적용되지 않았습니다. MailItemsAccessed는 모든 로그온 유형에 적용됩니다.

- MessageBind는 메일 클라이언트만 액세스할 수 있었습니다. MessageBind는 동기화 활동에는 적용되지 않았습니다. MailItemsAccessed 이벤트는 바인딩 및 동기화 액세스 유형에 의해 트리거됩니다.

- MessageBind 작업은 동일한 전자 메일 메시지에 액세스할 때 여러 감사 레코드가 생성되어 "노이즈" 감사가 발생합니다. 반대로 MailItemsAccessed 이벤트는 더 적은 감사 레코드로 집계됩니다.

사서함 감사 로깅에 대한 자세한 내용은 [사서함 감사 관리](enable-mailbox-auditing.md)를 참조하십시오.

## <a name="high-bandwidth-access-to-the-office-365-management-activity-api"></a>Office 365 관리 활동 API에 대한 고 대역폭 액세스

Office 365 관리 활동 API를 통해 감사 로그에 액세스하는 조직은 게시자 수준에서 제한을 스로틀링하여 제한되었습니다. 이는 여러 고객을 대신하여 데이터를 가져 오는 게시자의 경우 모든 고객이 한도를 공유했음을 의미합니다.

고급 감사가 릴리스됨에 따라 Microsoft는 게시자 수준 제한에서 테넌트 수준 제한으로 전환하고 있습니다. 결과적으로 각 조직은 감사 데이터에 액세스하기 위해 자체 할당된 대역폭 할당량을 얻게 됩니다. 대역폭은 사전 정의된 정적 제한이 아니지만 조직의 자리 수를 포함하여 E5 조직이 E5 이외의 조직보다 더 많은 대역폭을 갖도록 여러 요인을 조합하여 모델링되었습니다.

모든 조직에는 처음에 분당 2,000건의 요청 기준이 할당됩니다. 이 한도는 조직의 라이선스 수와 라이선스 구독에 따라 동적으로 증가합니다. E5 조직은 E5 이외의 조직보다 약 2배의 대역폭을 얻게됩니다. 또한 서비스 상태를 보호하기 위해 최대 대역폭에 제한이 있습니다.

자세한 내용은 [Office 365 관리 활동 API 참조](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#api-throttling)의 "API 조절"섹션을 참조하십시오.
