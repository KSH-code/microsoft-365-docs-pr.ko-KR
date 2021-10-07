---
title: SIEM 솔루션과의 통신 규정 준수
description: SIEM 솔루션과의 통신 준수 통합에 대해 자세히 알아보십시오.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: 54c2cffe50c8f0943595e90fd8bf66c63a6f5027
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60179298"
---
# <a name="communication-compliance-with-siem-solutions"></a>SIEM 솔루션과의 통신 규정 준수

[커뮤니케이션 규정](communication-compliance.md) 준수는 조직의 부적절한 메시지를 Microsoft 365, 캡처 및 처리하여 통신 위험을 최소화하는 데 도움이 되는 조직의 내부자 위험 솔루션입니다. [Azure Sentinel](https://azure.microsoft.com/services/azure-sentinel) 또는 [Splunk와](https://www.splunk.com/) 같은 SIEM(보안 정보 및 이벤트 관리) 솔루션은 일반적으로 조직 내에서 위협을 집계하고 추적하는 데 사용됩니다.

조직에 대한 일반적인 요구는 통신 준수 경고와 이러한 SIEM 솔루션을 통합하는 것입니다. 이러한 통합을 통해 조직은 SIEM 솔루션에서 통신 준수 경고를 보고 통신 준수 워크플로 및 사용자 환경 내에서 경고를 재구성할 수 있습니다. 예를 들어 직원이 다른 직원에게 공격 메시지를 보내고 해당 메시지는 비방 언어에 대한 통신 규정 준수 정책 모니터링에서 검색됩니다. 이러한 이벤트는 통신 준수 솔루션에 의해 Microsoft 365 감사("통합 감사 로그"라고도 알려지음)에서 추적되고 SIEM 솔루션으로 가져올 수 있습니다. 그런 다음 조직에 대한 SIEM 솔루션에서 통신 준수 경고와 관련된 Microsoft 365 감사에서 모니터링되는 이벤트에서 경고가 트리거됩니다. 조사자는 SIEM 솔루션에서 경고를 알리고 통신 준수 솔루션에서 경고를 조사하고 수정합니다.

## <a name="communication-compliance-alerts-in-the-microsoft-365-audit"></a>감사 감사의 통신 Microsoft 365 알림

모든 통신 준수 정책 일치는 감사 Microsoft 365 캡처됩니다. 다음 예에서는 선택한 통신 준수 정책 일치 활동에 사용할 수 있는 세부 정보를 보여 주며,

**공격 언어 정책 템플릿 일치에 대한 감사 로그 항목의 예는 다음과 같습니다.**

```xml
RunspaceId: 5c7bc9b0-7672-4091-a112-0635bd5f7732
RecordType: ComplianceSupervisionExchange
CreationDate: 7/7/2021 5:30:11 AM
UserIds: user1@contoso.onmicrosoft.com
Operations: SupervisionRuleMatch
AuditData: {"CreationTime":"2021-07-07T05:30:11","Id":"44e98a7e-57fd-4f89-79b8-08d941084a35","Operation":"SupervisionRuleMatch","OrganizationId":"338397e6\-697e-4dbe-a66b-2ea3497ef15c","RecordType":68,"ResultStatus":"{\\"ItemClass\\":\\"IPM.Note\\",\\"CcsiResults\\":\\"\\"}","UserKey":"SupervisionStoreDeliveryAgent","UserType":0,"Version":1,"Workload":"Exchange","ObjectId":"\<HE1P190MB04600526C0524C75E5750C5AC61A9@HE1P190MB0460.EURP190.PROD.OUTLOOK.COM\>","UserId":"user1@contoso.onmicrosoft.com","IsPolicyHit":true,"SRPolicyMatchDetails":{"SRPolicyId":"53be0bf4-75ee-4315-b65d-17d63bdd53ae","SRPolicyName":"Adult images","SRRuleMatchDetails":\[\]}}
ResultIndex: 24
ResultCount: 48
Identity: 44e98a7e-57fd-4f89-79b8-08d941084a35
IsValid: True
ObjectState: Unchanged
```

**사용자 지정 Microsoft 365 일치하는 정책에 대한 감사 로그 항목(사용자 지정 중요한 정보 유형)의 예:**

```xml
RunspaceId: 5c7bc9b0-7672-4091-a112-0635bd5f7732
RecordType: ComplianceSupervisionExchange
CreationDate: 7/6/2021 9:50:12 PM
UserIds: user2@contoso.onmicrosoft.com
Operations: SupervisionRuleMatch
AuditData: {"CreationTime":"2021-07-06T21:50:12","Id":"5c61aae5-26fc-4c8e-0791-08d940c8086f","Operation":"SupervisionRuleMatch","OrganizationId":"338397e6\-697e-4dbe-a66b-2ea3497ef15c","RecordType":68,"ResultStatus":"{\\"ItemClass\\":\\"IPM.Note\\",\\"CcsiResults\\":\\"public\\"}","UserKey":"SupervisionStoreDeliveryAgent","UserType":0,"Version":1,"Workload":"Exchange","ObjectId":"\<20210706174831.24375086.807067@sailthru.com\>","UserId":"user2@contoso.onmicrosoft.com","IsPolicyHit":true,"SRPolicyMatchDetails":{"SRPolicyId":"a97cf128-c0fc-42a1-88e3-fd3b88af9941","SRPolicyName":"Insiders","SRRuleMatchDetails":\[{"SRCategoryName":"New insiders lexicon"}\]}}
ResultIndex: 46
ResultCount: 48
Identity: 5c61aae5-26fc-4c8e-0791-08d940c8086f
IsValid: True
ObjectState: Unchanged
```

> [!NOTE]
> 현재 정책 일치가 Microsoft 365 감사에 기록되는 시간과 통신 규정 준수에서 정책 일치를 조사할 수 있는 시간 사이에는 최대 24시간이 지연될 수 있습니다.

## <a name="configure-communication-compliance-and-azure-sentinel-integration"></a>통신 규정 준수 및 Azure Sentinel 통합 구성

Azure Sentinel을 사용하여 통신 준수 정책 일치를 집계하는 경우 Sentinel은 Microsoft 365 감사를 데이터 원본으로 사용하게 됩니다. 통신 준수 경고를 Sentinel과 통합하기 위해 다음 단계를 완료합니다.

1. [Azure Sentinel에 온보드합니다.](/azure/sentinel/quickstart-onboard) 온보더링 프로세스의 일부로 데이터 원본을 구성합니다.
2. Azure Sentinel [](/azure/sentinel/data-connectors-reference#microsoft-office-365) 데이터 Microsoft Office 365 구성하고 커넥터 구성에서 를 *Exchange.*
3. 통신 준수 경고를 검색하도록 검색 쿼리를 구성합니다. 예제:

    *| OfficeActivity | 여기서 OfficeWorkload == "Exchange" 및 Operation == "SupervisionRuleMatch" | TimeGenerated별로 정렬*

    특정 사용자를 필터링하기 위해 다음 쿼리 형식을 사용합니다.

    *| OfficeActivity | 여기서 OfficeWorkload == "Exchange" 및 Operation == "SupervisionRuleMatch" 및 UserId == "User1@Contoso.com" | TimeGenerated별로 정렬*

Azure Sentinel에서 Microsoft 365 감사 로그에 대한 Office 365 대한 자세한 내용은 [Azure Monitor Logs reference 를 참조하세요.](/azure/azure-monitor/reference/tables/OfficeActivity)

## <a name="configure-communication-compliance-and-splunk-integration"></a>통신 규정 준수 및 Splunk 통합 구성

통신 준수 경고를 Splunk와 통합하기 위해 다음 단계를 완료합니다.

1. [Splunk Add-on for Microsoft Office 365](https://docs.splunk.com/Documentation/AddOns/released/MSO365/ConfigureinputsmanagementAPI)
2. Azure AD에서 Splunk 추가 기능을 위한 통합 응용 Microsoft Office 365
3. Splunk 솔루션에서 검색 쿼리를 구성합니다. 다음 검색 예제를 사용하여 모든 통신 준수 경고를 식별합니다.

    *index= \* sourcetype="o365:management:activity" Workload=Exchange Operation=SupervisionRuleMatch*

특정 통신 준수 정책에 대한 결과를 필터링하기 위해 *SRPolicyMatchDetails.SRPolicyName* 매개 변수를 사용할 수 있습니다.

예를 들어 다음 검색 예제에서는 공격적 언어라는 통신 준수 정책과 일치하는 *경고를 반환합니다.*

  *index= \* sourcetype='o365:management:activity' Workload=Exchange Operation=SupervisionRuleMatch SRPolicyMatchDetails.SRPolicyName=\<Offensive language\>*

다음 표에는 다양한 정책 유형에 대한 샘플 검색 결과가 표시됩니다.

| 정책 유형 | 검색 결과 예제 |
| :------------------ | :--------------------------------------- |
| 사용자 지정 중요한 정보 유형 키워드 목록을 검색하는 정책 | { <br> CreationTime: 2021-09-17T16:29:57 <br> ID: 4b9ce23d-ee60-4f66-f38d-08d979f8631f <br> IsPolicyHit: true <br> ObjectId: <CY1PR05MB27158B96AF7F3AFE62E1F762CFDD9@CY1PR05MB2715.namprd05.prod.outlook.com> <br> 작업: SupervisionRuleMatch <br> OrganizationId: d6a06676-95e8-4632-b949-44bc00f0793f <br> RecordType: 68 <br> ResultStatus: {"ItemClass":"IPM. 참고","CcsiResults":"leak"} <br> SRPolicyMatchDetails: { [+] } <br> UserId: user1@contoso. OnMicrosoft.com <br> UserKey: SupervisionStoreDeliveryAgent <br> UserType: 0 <br> 버전: 1 <br> 작업량: Exchange <br> } |
| 부적절한 언어를 검색하는 정책 | { <br> CreationTime: 2021-09-17T23:44:35 <br> ID: e0ef6f54-9a52-4e4c-9584-08d97a351ad0 <br> IsPolicyHit: true <br> ObjectId: <BN6PR05MB3571AD9FBB85C4E12C1F66B4CCDD9@BN6PR05MB3571.namprd05.prod.outlook.com> <br> 작업: SupervisionRuleMatch <br> OrganizationId: d6a06676-95e8-4632-b949-44bc00f0793f <br> RecordType: 68 <br> ResultStatus: {"ItemClass":"IPM.Yammer. Message","CcsiResults":""} <br> SRPolicyMatchDetails: { [+] } <br> UserId: user1@contoso.com <br> UserKey: SupervisionStoreDeliveryAgent <br> UserType: 0 <br> 버전: 1 <br> }  |

## <a name="configure-communication-compliance-with-other-siem-solutions"></a>다른 SIEM 솔루션과의 통신 준수 구성

Microsoft 365 감사에서 통신 준수 정책 일치를 검색하기 위해 PowerShell 또는 Office 365 [관리 API를 사용할 수 있습니다.](/office/office-365-management-api/office-365-management-activity-api-reference)

PowerShell을 사용하는 경우 **Search-UnifiedAuditLog** cmdlet과 함께 이러한 매개 변수 중 하나를 사용하여 통신 준수 활동에 대한 감사 로그 이벤트를 필터링할 수 있습니다.

| 감사 로그 매개 변수 | 통신 준수 매개 변수 값 |
| :------------------ | :--------------------------------------- |
| 작업          | SupervisionRuleMatch                     |
| RecordType          | ComplianceSupervisionExchange            |

예를 들어 다음은 **Operations** 매개 변수와 *SupervisionRuleMatch* 값을 사용하는 샘플 검색입니다.

```powershell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -Operations SupervisionRuleMatch | ft CreationDate,UserIds,AuditData
```
다음은 **RecordsType** 매개 변수와 *ComplianceSupervisionExchange* 값을 사용하는 샘플 검색입니다.

```powershell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -RecordType ComplianceSuperVisionExchange | ft CreationDate,UserIds,AuditData
```
## <a name="resources"></a>리소스

- [통신 준수 감사](communication-compliance-feature-reference.md#audit)
- [Microsoft 365의 고급 감사](advanced-audit.md)
- [Office 365 관리 작업 API 참고자료](/office/office-365-management-api/office-365-management-activity-api-reference)
