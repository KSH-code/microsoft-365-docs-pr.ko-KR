---
title: HR 데이터를 가져올 커넥터 설정
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: 관리자는 데이터 커넥터를 설정하여 조직의 HR(인사) 시스템에서 직원 데이터를 가져올 수 Microsoft 365. 이렇게 하면 내부자 위험 관리 정책의 HR 데이터를 사용하여 조직에 내부 위협을 줄 수 있는 특정 사용자의 활동을 검색할 수 있습니다.
ms.openlocfilehash: e7a5bb9a1912aff7d41968bd1c8f6c08333178c0
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60659965"
---
# <a name="set-up-a-connector-to-import-hr-data"></a>HR 데이터를 가져올 커넥터 설정

데이터 커넥터를 사용자 Microsoft 365 규정 준수 센터 작업 수준의 변경과 같은 이벤트와 관련된 HR(인사) 데이터를 가져오기 위해 데이터 커넥터를 설정할 수 있습니다. 그런 다음 내부자 위험 관리 [](insider-risk-management.md) 솔루션에서 HR 데이터를 사용하여 조직 내부 사용자에 의해 가능한 악의적인 활동이나 데이터 도용을 확인할 수 있는 위험 지표를 생성할 수 있습니다.

내부자 위험 관리 정책이 위험 지표를 생성하는 데 사용할 수 있는 HR 데이터에 대한 커넥터를 설정하는 방법은 HR 데이터가 포함된 CSV 파일을 만들고, Azure Active Directory 인증에 사용되는 앱을 만들고, Microsoft 365 규정 준수 센터에서 HR 데이터 커넥터를 만들고, 스크립트를 실행(예약된 기준)하는 것으로 구성됩니다. t는 CSV 파일의 HR 데이터를 Microsoft 클라우드로 수집하여 내부자 위험 관리 솔루션에서 사용할 수 있도록 합니다.

## <a name="before-you-begin"></a>시작하기 전에

- 가져올 HR 시나리오 및 데이터를 Microsoft 365. 이렇게 하면 만들어야 하는 CSV 파일 및 HR 커넥터의 수와 CSV 파일을 생성하고 구성하는 방법을 결정하는 데 도움이 됩니다. 가져오는 HR 데이터는 구현하려는 내부자 위험 관리 정책에 따라 결정됩니다. 자세한 내용은 1단계를 참조하세요.

- 조직의 HR 시스템에서 정기적으로 데이터를 검색하거나 내보내는 방법을 결정하고 1단계에서 만든 CSV 파일에 추가합니다. 4단계에서 실행한 스크립트는 CSV 파일의 HR 데이터를 Microsoft 클라우드에 업로드합니다.

- 3단계에서 HR 커넥터를 만드는 사용자에게 사서함 가져오기 내보내기 역할이 할당되어야 Exchange Online. 기본적으로이 역할은 Exchange Online의 어떤 역할 그룹에도 할당되지 않습니다. 사서함 가져오기 내보내기 역할을 조직의 조직 관리 역할 그룹에 추가할 수 Exchange Online. 또는 새 역할 그룹을 만들고 사서함 가져오기 내보내기 역할을 할당한 다음 해당 사용자를 구성원으로 추가할 수 있습니다. 자세한 내용은 "역할 [](/Exchange/permissions-exo/role-groups#create-role-groups) 그룹에서 [](/Exchange/permissions-exo/role-groups#modify-role-groups) 역할 그룹 관리" 문서의 역할 그룹 만들기 또는 역할 그룹 수정 섹션을 Exchange Online.

- 4단계에서 실행한 샘플 스크립트는 내부자 위험 관리 솔루션에서 사용할 수 있도록 HR 데이터를 Microsoft 클라우드에 업로드합니다. 이 샘플 스크립트는 Microsoft 표준 지원 프로그램 또는 서비스에서 지원되지 않습니다. 샘플 스크립트는 어떤 종류의 보증도 없이 그대로 제공됩니다. 또한 Microsoft는 묵시적인 모든 보증(상품성 또는 특정 목적에의 적합성에 대한 묵시적인 보증을 포함하되 이에 제한되지 않음)을 부인합니다. 샘플 스크립트 및 문서의 사용 또는 수행으로 인해 발생하는 모든 위험은 사용자의 책임입니다. 어떠한 경우에도 Microsoft, 스크립트 작성자 또는 그외 스크립트의 작성, 생산 또는 제공과 관련된 사람은 누구나 샘플 스크립트 또는 문서의 사용 또는 사용할 수 없음으로 인해 발생하는 모든 손해(수익 손실, 비즈니스 중단, 비즈니스 정보 손실 또는 기타 금전상의 손실을 포함하되 이에 제한되지 않음)에 대해 책임지지 않습니다. 이는 Microsoft가 이러한 손해가 발생할 가능성에 대해 알았더라도 마찬가지입니다.

- 이 커넥터는 미국 GCC 클라우드의 Microsoft 365 환경에서 사용할 수 있습니다. 타사 응용 프로그램 및 서비스는 Microsoft 365 인프라 외부에 있는 타사 시스템에서 조직의 고객 데이터를 저장, 전송 및 처리해야 할 수 있으므로 Microsoft 365 및 데이터 보호 약정의 적용을 Microsoft 365 수 있습니다. Microsoft는 타사 응용 프로그램에 연결하는 데 이 제품을 사용하는 것은 해당 타사 응용 프로그램이 FEDRAMP 규격임을 암시하는 표현을 사용하지 않습니다. GCC 환경에서 HR 커넥터를 설정하는 단계별 지침은 [Set up a connector to import HR data in US Government을 참조하세요.](import-hr-data-US-government.md)

## <a name="step-1-prepare-a-csv-file-with-your-hr-data"></a>1단계: HR 데이터를 사용하여 CSV 파일 준비

첫 번째 단계에서는 커넥터가 연결선을 가져오기 위해 가져올 HR 데이터가 포함된 CSV 파일을 Microsoft 365. 이 데이터는 내부자 위험 솔루션에서 잠재적인 위험 지표를 생성하는 데 사용됩니다. 다음 HR 시나리오에 대한 데이터를 다음 HR 시나리오로 가져올 수 Microsoft 365.

- 직원 사직. 조직을 떠났던 사용자에 대한 정보입니다.

- 작업 수준 변경 승격 및 강하와 같은 사용자에 대한 작업 수준 변경에 대한 정보입니다.

- 성능 검토. 사용자 성능에 대한 정보입니다.

- 성능 개선 계획. 사용자에 대한 성능 개선 계획에 대한 정보.

가져올 HR 데이터의 유형은 구현하려는 내부자 위험 관리 정책 및 해당 정책 템플릿에 따라 다릅니다. 다음 표에는 각 정책 템플릿에 필요한 HR 데이터 형식이 표시됩니다.

|  정책 템플릿 |  HR 데이터 형식 |
|:-----------------------------------------------|:---------------------------------------------------------------------|
| 퇴사하는 직원의 데이터 도난                   | 직원 퇴사                                                 |
| 일반적인 데이터 유출                              | 해당 사항 없음                                                        |
| 우선순위 사용자의 데이터 유출                    | 해당 사항 없음                                                        |
| 불만을 품은 사용자의 데이터 유출                 | 작업 수준 변경, 성능 검토, 성능 개선 계획 |
| 일반 보안 정책 위반              | 해당 사항 없음                                                        |
| 퇴사하는 사용자의 보안 정책 위반   | 직원 퇴사                                                 |
| 우선순위 사용자의 보안 정책 위반    | 해당 사항 없음                                                        |
| 불만을 품은 사용자의 보안 정책 위반 | 작업 수준 변경, 성능 검토, 성능 개선 계획 |
| 전자 메일의 불쾌한 언어                     | 해당 사항 없음                                                        |

내부자 위험 관리를 위한 정책 템플릿에 대한 자세한 내용은 [Insider risk management policies 을 참조하세요.](insider-risk-management-policies.md#policy-templates)

각 HR 시나리오에 대해 하나 이상의 CSV 파일에 해당 HR 데이터를 제공해야 합니다. 내부자 위험 관리 구현에 사용할 CSV 파일의 수는 이 섹션의 부분에서 설명합니다.

필요한 HR 데이터를 사용하여 CSV 파일을 만든 후 4단계에서 스크립트를 실행한 로컬 컴퓨터에 저장합니다. 또한 CSV 파일에 항상 최신 정보가 포함되는 업데이트 전략을 구현하여 스크립트를 실행할 때 최신 HR 데이터가 Microsoft 클라우드에 업로드되어 내부자 위험 관리 솔루션에서 액세스할 수 있도록 해야 합니다.

> [!IMPORTANT]
> 다음 섹션에 설명된 열 이름은 필수 매개 변수가 아니라 예제입니다. CSV 파일에 열 이름을 사용할 수 있습니다. 그러나 3단계에서 HR 커넥터를  만들 때 CSV 파일에서 사용하는 열 이름은 데이터 형식에 매핑되어야 합니다. 또한 다음 섹션의 예제 CSV 파일은 메모장 보기에 표시됩니다. It's much easier to view and edit CSV files in Microsoft Excel.

다음 섹션에서는 각 HR 시나리오에 필요한 CSV 데이터에 대해 설명합니다.

### <a name="csv-file-for-employee-resignation-data"></a>직원 퇴사 데이터를 위한 CSV 파일

다음은 직원 퇴사 데이터에 대한 CSV 파일의 예입니다.

```text
EmailAddress,ResignationDate,LastWorkingDate
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,2019-04-29T15:18:02.4675041+05:30
pilarp@contoso.com,2019-04-24T09:15:49Z,2019-04-29T15:18:02.7117540
```

다음 표에서는 CSV 파일의 직원 퇴사 데이터에 대한 각 열에 대해 설명하고 있습니다.

|  열   |   설명 |
|:------------|:----------------|
|**EmailAddress**| 종료된 사용자의 UPN(전자 메일 주소)을 지정합니다.|
| **ResignationDate** | 조직에서 사용자의 고용이 공식적으로 종료된 날짜를 지정합니다. 예를 들어 이 날짜는 사용자가 조직을 떠나는 것을 공지한 날짜일입니다. 이 날짜는 작업의 마지막 날과 다를 수 있습니다. 다음 날짜 형식을 사용 합니다. `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` [는 ISO 8601 날짜 및 시간 형식 입니다.](https://www.iso.org/iso-8601-date-and-time-format.html)|
| **LastWorkingDate** | 종료된 사용자의 작업 마지막 날을 지정합니다. 다음 날짜 형식을 사용 합니다. `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` [는 ISO 8601 날짜 및 시간 형식 입니다.](https://www.iso.org/iso-8601-date-and-time-format.html)|
|||

### <a name="csv-file-for-job-level-changes-data"></a>작업 수준 변경 데이터를 위한 CSV 파일

다음은 작업 수준 변경 데이터를 위한 CSV 파일의 예입니다.

```text
EmailAddress,EffectiveDate,OldLevel,NewLevel
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,Level 61 – Sr. Manager,Level 60- Manager
pillar@contoso.com,2019-04-23T15:18:02.4675041+05:30,Level 62 – Director,Level 60- Sr. Manager
```

다음 표에서는 작업 수준 변경 데이터를 위한 CSV 파일의 각 열에 대해 설명하고 있습니다.

|  열 | 설명 |
|:--------- |:------------- |
| **EmailAddress**  | 사용자의 UPN(전자 메일 주소)을 지정합니다.|
| **EffectiveDate** | 사용자의 작업 수준이 공식적으로 변경된 날짜를 지정합니다. 다음 날짜 형식을 사용 합니다. `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` [는 ISO 8601 날짜 및 시간 형식 입니다.](https://www.iso.org/iso-8601-date-and-time-format.html)|
| **설명**| 작업 수준 변경에 대해 평가자에서 제공한 비고를 지정합니다. 200자까지 입력할 수 있습니다. 이 매개 변수는 선택 사항입니다. CSV 파일에 포함하지는 않습니다.|
| **OldLevel**| 변경되기 전에 사용자의 작업 수준을 지정합니다. 이 매개 변수는 자유 텍스트 매개 변수이며 조직에 대한 계층적 구성을 포함할 수 있습니다. 이 매개 변수는 선택 사항입니다. CSV 파일에 포함하지는 않습니다.|
| **NewLevel**| 변경된 후 사용자의 작업 수준을 지정합니다. 이 매개 변수는 자유 텍스트 매개 변수이며 조직에 대한 계층적 구성을 포함할 수 있습니다. 이 매개 변수는 선택 사항입니다. CSV 파일에 포함하지는 않습니다.|
|||

### <a name="csv-file-for-performance-review-data"></a>성능 검토 데이터를 위한 CSV 파일

다음은 성능 데이터를 위한 CSV 파일의 예입니다.

```text
EmailAddress,EffectiveDate,Remarks,Rating
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,Met expectations but bad attitude,2-Below expectation
pillar@contoso.com,2019-04-23T15:18:02.4675041+05:30, Multiple conflicts with the team
```

다음 표에서는 성능 검토 데이터를 위한 CSV 파일의 각 열에 대해 설명하고 있습니다.

|  열 | 설명 |
|:----------|:--------------|
| **EmailAddress**  | 사용자의 UPN(전자 메일 주소)을 지정합니다.|
| **EffectiveDate** | 사용자에게 성능 검토 결과를 공식적으로 알리는 날짜를 지정합니다. 이 날짜는 성능 검토 주기가 종료된 날짜일 수 있습니다. 다음 날짜 형식을 사용 합니다. `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` [는 ISO 8601 날짜 및 시간 형식 입니다.](https://www.iso.org/iso-8601-date-and-time-format.html)|
| **설명**| 성능 검토를 위해 평가자에서 사용자에게 제공한 모든 비고를 지정합니다. 이 매개 변수는 200자로 제한된 텍스트 매개 변수입니다. 이 매개 변수는 선택 사항입니다. CSV 파일에 포함하지는 않습니다.|
| **평점**| 성능 검토를 위해 제공된 등급을 지정합니다. 이 매개 변수는 텍스트 매개 변수이며 조직에서 평가를 인식하는 데 사용하는 자유 형식 텍스트를 포함할 수 있습니다. 예를 들어 "3 충족 기대치" 또는 "2 미만 평균"입니다. 이 매개 변수는 25자로 제한된 텍스트 매개 변수입니다. 이 매개 변수는 선택 사항입니다. CSV 파일에 포함하지는 않습니다.|
|||

### <a name="csv-file-for-performance-improvement-plan-data"></a>성능 개선 계획 데이터를 위한 CSV 파일

다음은 성능 개선 계획 데이터에 대한 데이터에 대한 CSV 파일의 예입니다.

```text
EmailAddress,EffectiveDate,ImprovementRemarks,PerformanceRating
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,Met expectation but bad attitude,2-Below expectation
pillar@contoso.com,2019-04-23T15:18:02.4675041+05:30, Multiple conflicts with the team
```

다음 표에서는 성능 검토 데이터를 위한 CSV 파일의 각 열에 대해 설명하고 있습니다.

|  열 |  설명 |
|:----------|:---------------|
| **EmailAddress**  | 사용자의 UPN(전자 메일 주소)을 지정합니다.|
| **EffectiveDate** | 사용자에게 성능 개선 계획을 공식적으로 알릴 날짜를 지정합니다. ISO 8601 날짜 및 시간 형식인 날짜 형식 `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` [을 사용해야 합니다.](https://www.iso.org/iso-8601-date-and-time-format.html)|
| **설명**| 성능 개선 계획에 대해 평가자에서 제공한 모든 비고를 지정합니다. 이 매개 변수는 200자로 제한된 텍스트 매개 변수입니다. 이 매개 변수는 선택적 매개 변수입니다. CSV 파일에 포함하지는 않습니다. |
| **평점**| 성능 검토와 관련된 평점 또는 기타 정보를 지정합니다. 성능 개선 계획. 이 매개 변수는 텍스트 매개 변수이며 조직에서 평가를 인식하는 데 사용하는 무료 양식 텍스트를 포함할 수 있습니다. 예를 들어 "3 충족 기대치" 또는 "2 미만 평균"입니다. 이 매개 변수는 25자로 제한된 텍스트 매개 변수입니다. 이 매개 변수는 선택적 매개 변수입니다. CSV 파일에 포함하지는 않습니다.|
|||

### <a name="determining-how-many-csv-files-to-use-for-hr-data"></a>HR 데이터에 사용할 CSV 파일 수 결정

3단계에서는 각 HR 데이터 형식에 대해 별도의 커넥터를 만들거나 모든 데이터 형식에 대해 단일 커넥터를 만들 수 있습니다. 이전 섹션에 설명된 CSV 파일의 예와 같이 하나의 HR 시나리오에 대한 데이터가 포함된 별도의 CSV 파일을 사용할 수 있습니다. 또는 둘 이상의 HR 시나리오에 대한 데이터를 포함하는 단일 CSV 파일을 사용할 수 있습니다. HR 데이터에 사용할 CSV 파일의 수를 결정하는 데 도움이 되는 몇 가지 지침은 다음과 같습니다.

- 구현하려는 내부자 위험 관리 정책에 여러 HR 데이터 형식이 필요한 경우 필요한 모든 데이터 형식이 포함된 단일 CSV 파일을 사용하는 것이 고려됩니다.

- HR 데이터를 생성하거나 수집하는 방법은 CSV 파일 수를 결정할 수 있습니다. 예를 들어 HR 커넥터를 구성하는 데 사용되는 다양한 유형의 HR 데이터가 조직의 단일 HR 시스템에 있는 경우 데이터를 단일 CSV 파일로 내보낼 수 있습니다. 그러나 데이터가 서로 다른 HR 시스템에 분산되어 있는 경우 데이터를 다른 CSV 파일로 내보내는 것이 더 쉬워질 수 있습니다. 예를 들어 직원 퇴사 데이터는 작업 수준 또는 성과 검토 데이터와 다른 HR 시스템에 있을 수 있습니다. 이 경우 데이터를 수동으로 단일 CSV 파일로 결합하는 대신 별도의 CSV 파일을 가지는 것이 더 쉬워집니다. 따라서 HR 시스템에서 데이터를 검색하거나 내보내는 방법에 따라 필요한 CSV 파일 수가 결정될 수 있습니다.

- 일반적으로 만들어야 하는 HR 커넥터 수는 CSV 파일의 데이터 형식에 따라 결정됩니다. 예를 들어 CSV 파일에 내부자 위험 관리 구현을 지원하는 데 필요한 모든 데이터 형식이 포함되어 있는 경우 HR 커넥터는 하나만 필요합니다. 그러나 각각 하나의 데이터 형식을 포함하는 별도의 CSV 파일이 두 개 있는 경우 두 개의 HR 커넥터를 만들어야 합니다. 단, **CSV 파일에 HRScenario** 열을 추가하는 경우(다음 섹션 참조) 다른 CSV 파일을 처리하도록 단일 HR 커넥터를 구성할 수 있습니다.

### <a name="configuring-a-single-csv-file-for-multiple-hr-data-types"></a>여러 HR 데이터 형식에 대해 단일 CSV 파일 구성

단일 CSV 파일에 여러 HR 데이터 형식을 추가할 수 있습니다. 이 기능은 구현하는 내부자 위험 관리 솔루션에 여러 HR 데이터 형식이 필요하거나 데이터 형식이 조직의 단일 HR 시스템에 있는 경우 유용합니다. CSV 파일이 적을수록 생성 및 관리할 HR 커넥터 수가 항상 적습니다.

여러 데이터 형식의 CSV 파일을 구성하기 위한 요구 사항은 다음과 같습니다.

- 헤더 행의 각 데이터 형식 및 해당 열 이름에 필요한 열을 추가해야 합니다(필요한 경우 해당 열을 사용하는 경우 선택 사항). 데이터 형식이 열에 해당하지 않는 경우 값을 비워 두면 됩니다.

- 여러 유형의 HR 데이터와 함께 CSV 파일을 사용하기 위해 HR 커넥터는 CSV 파일의 어떤 행이 HR 데이터를 포함하는지 알아야 합니다. 이 작업을 수행하기 위해 **CSV 파일에 HRScenario** 열을 더 추가합니다. 이 열의 값은 각 행의 HR 데이터 형식을 식별합니다. 예를 들어 4개의 HR 시나리오에 해당하는 값은 \` Resignation, \` Job level change , Performance review 및 Performance improvement \` \` \` \` \` plan일 수 \` 있습니다.

- HRScenario** 열을 포함하는 CSV 파일이 여러 개 있는 경우 각 파일이 특정 HR 시나리오를 식별하는 동일한 열 이름과 값을 사용하는지 확인해야 합니다.

다음 예제에서는 **HRScenario** 열이 포함된 CSV 파일을 보여 제공합니다. HRScenario 열의 값은 해당 행의 데이터 형식을 식별합니다.

```text
HRScenario,EmailAddress,ResignationDate,LastWorkingDate,EffectiveDate,Remarks,Rating,OldLevel,NewLevel
Resignation,sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,2019-04-29T15:18:02.4675041+05:30,,,,
Resignation,pilarp@contoso.com,2019-04-24T09:15:49Z,2019-04-29T15:18:02.7117540,,,,
Job level change,sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,,,,,Level 61 Sr. Manager, Level 60 Manager
Job level change,pillarp@contoso.com,2019-04-23T15:18:02.4675041+05:30,,,,,Level 62 Director,Level 60 Sr Manager
Performance review,sarad@contoso.com,,,2019-04-23T15:18:02.4675041+05:30,Met expectation but bad attitude,2 Below expectations,,
Performance review,pillarp@contoso.com,,,2019-04-23T15:18:02.4675041+05:30, Multiple conflicts with the team,,
Performance improvement plan,sarad@contoso.com,,,2019-04-23T15:18:02.4675041+05:30,Met expectations but bad attitude,2 Below expectations,,
Performance improvement plan,pillarp@contoso.com,,,2019-04-23T15:18:02.4675041+05:30,Multiple conflicts with the team,,
```

> [!NOTE]
> 3단계에서 커넥터를 설정할 때 CSV 파일의 열 이름을 HR 데이터 형식을 식별하는 열로 매핑하기 때문에 HR 데이터 형식을 식별하는 열의 이름을 사용할 수 있습니다. 또한 커넥터를 설정할 때 데이터 형식 열에 사용되는 값을 매핑합니다.

### <a name="adding-the-hrscenario-column-to-a-csv-file-that-contains-a-single-data-type"></a>단일 데이터 형식을 포함하는 CSV 파일에 HRScenario 열 추가

조직의 HR 시스템 및 HR 데이터를 CSV 파일로 내보내는 방법에 따라 단일 HR 데이터 형식을 포함하는 여러 CSV 파일을 만들어야 할 수 있습니다. 이 경우 다른 CSV 파일에서 데이터를 가져오는 단일 HR 커넥터를 만들 수 있습니다. 이 작업을 위해 CSV 파일에 HRScenario 열을 추가하고 HR 데이터 형식을 지정하기만하면 됩니다. 그런 다음 각 CSV 파일에 대해 스크립트를 실행하지만 커넥터에 대해 동일한 작업 ID를 사용할 수 있습니다. [4단계를 참조합니다.](#step-4-run-the-sample-script-to-upload-your-hr-data)

## <a name="step-2-create-an-app-in-azure-active-directory"></a>2단계: 앱에서 앱 Azure Active Directory

다음 단계는 Azure AD(Azure AD)에서 새 Azure Active Directory 등록하는 것입니다. 앱은 3단계에서 만든 HR 커넥터에 해당합니다. 이 앱을 만들면 Azure AD에서 HR 커넥터를 실행하고 조직에 액세스하려고 할 때 인증할 수 있습니다. 이 앱은 4단계에서 실행하여 Microsoft 클라우드에 HR 데이터를 업로드하는 스크립트를 인증하는 데도 사용됩니다. 이 Azure AD 앱을 만들 때 다음 정보를 저장해야 합니다. 이러한 값은 3단계 및 4단계에서 사용됩니다.

- Azure AD 응용 프로그램 ID(앱 ID 또는 *클라이언트 ID라고도 합니다.* 

- Azure AD 응용 프로그램 비밀(클라이언트 *비밀이라고도 합니다.*

- 테넌트 ID(디렉터리 *ID라고도 합니다.*

Azure AD에서 앱을 만드는 단계별 지침은 응용 프로그램 등록을 [Microsoft ID 플랫폼.](/azure/active-directory/develop/quickstart-register-app)

## <a name="step-3-create-the-hr-connector"></a>3단계: HR 커넥터 만들기

다음 단계는 서버의 HR 커넥터를 Microsoft 365 규정 준수 센터. 4단계에서 스크립트를 실행한 후 만든 HR 커넥터는 CSV 파일의 HR 데이터를 Microsoft 365 조직에 수집합니다. 커넥터를 만들기 전에 HR 시나리오 목록과 각 시나리오에 해당하는 CSV 열 이름이 있는지 확인해야 합니다. 커넥터를 구성할 때 각 시나리오에 필요한 데이터를 CSV 파일의 실제 열 이름에 매핑해야 합니다. 또는 커넥터를 구성할 때 샘플 CSV 파일을 업로드할 수 있으며 마법사를 통해 열 이름을 필요한 데이터 형식에 매핑할 수 있습니다.

이 단계를 완료한 후 커넥터를 만들 때 생성되는 작업 ID를 복사해야 합니다. 스크립트를 실행할 때 작업 ID를 사용하게 됩니다.

1. 으로 이동한 다음 왼쪽 [https://compliance.microsoft.com](https://compliance.microsoft.com/) **네비게이트에서 데이터** 커넥터를 클릭합니다.

2. 데이터 커넥터 **페이지에서** **HR** 아래의 보기를 **클릭합니다.**

3. **HR 사용자 지정 페이지에서** 커넥터 **추가를 클릭합니다.**

4. 연결 **설정 페이지에서** 다음을 실행하고 다음을 **클릭합니다.**

   1. 2단계에서 만든 Azure 앱의 Azure AD 응용 프로그램 ID를 입력하거나 붙여넣습니다.

   1. HR 커넥터의 이름을 입력합니다.

5. HR 시나리오 페이지에서 데이터를 가져올 하나 이상의 HR 시나리오를 선택하고 다음 을 **클릭합니다.**

6. 파일 매핑 방법 페이지에서 다음 옵션 중 하나를 선택하고 다음 을 **클릭합니다.**

   - **업로드 파일을 저장합니다.** 이 옵션을 선택하는 경우 샘플 **업로드** 클릭하여 1단계에서 준비한 CSV 파일을 업로드합니다. 이 옵션을 사용하면 드롭다운 목록에서 CSV 파일의 열 이름을 빠르게 선택하여 이전에 선택한 HR 시나리오의 데이터 형식에 매핑할 수 있습니다.

   또는

   - **매핑 세부 정보를 수동으로 제공합니다.** 이 옵션을 선택하는 경우 CSV 파일의 열 이름을 입력하여 이전에 선택한 HR 시나리오의 데이터 형식에 매핑해야 합니다.

7. 파일 매핑 세부 정보 페이지에서 샘플 CSV 파일을 업로드한지 여부와 단일 HR 시나리오 또는 여러 시나리오에 대해 커넥터를 구성하는지 여부에 따라 다음 중 하나를 실행합니다. 샘플 파일을 업로드한 경우 열 이름을 입력할 수 없습니다. 드롭다운 목록에서 선택합니다.

    - 이전 단계에서 단일 HR 시나리오를 선택한 경우 각 해당 상자에 1단계에서 만든 CSV 파일에서 열 머리더 이름(매개 변수라고도 합니다.)을 입력합니다. 입력하는 열 이름은 대소문자 구분이 없지만 CSV 파일의 열 이름에 공백이 포함된 경우 공백을 포함해야 합니다. 앞서 설명한 것처럼 이러한 상자에 입력하는 이름은 CSV 파일의 매개 변수 이름과 일치해야 합니다. 예를 들어 다음 스크린샷은 1단계에 표시된 직원 재직 HR 시나리오에 대한 예제 CSV 파일의 매개 변수 이름을 보여 줍니다.

    - 위의 단계에서 여러 데이터 형식을 선택한 경우 CSV 파일의 HR 데이터 형식을 식별하는 식별자 열 이름을 입력해야 합니다. 식별자 열 이름을 입력한 후 이 HR 데이터 형식을 식별하는 값을 입력하고 선택한 각 데이터 형식에 대해 적절한 각 상자에 1단계에서 만든 CSV 파일에서 선택한 데이터 형식의 열 헤더 이름을 입력합니다. 앞서 설명한 것처럼 이러한 상자에 입력하는 이름은 CSV 파일의 열 이름과 일치해야 합니다.

8. 검토 **페이지에서** 설정을 검토한 다음 **마친을** 클릭하여 커넥터를 만드십시오.

   커넥터가 만들어졌다는 확인 상태 페이지가 표시됩니다. 이 페이지에는 HR 데이터를 업로드하기 위해 샘플 스크립트를 실행하기 위해 다음 단계를 완료해야 하는 두 가지 중요한 것이 포함되어 있습니다.

   ![작업 ID가 있는 페이지를 검토하고 샘플 스크립트를 위해 github에 연결합니다.](../media/HRConnector_Confirmation.png)

   1. **작업 ID입니다.** 다음 단계에서 스크립트를 실행하려면 이 작업 ID가 필요합니다. 이 페이지 또는 커넥터 플라이아웃 페이지에서 복사할 수 있습니다.

   2. **샘플 스크립트에 연결합니다.** 샘플 **스크립트에** 액세스하려면 여기를 클릭하고 GitHub 사이트로 이동하십시오.(링크가 새 창이 열립니다). 4단계에서 스크립트를 복사할 수 있도록 이 창을 열어 두십시오. 또는 스크립트를 실행할 때 다시 액세스할 수 있도록 대상에 책갈피를 지정하거나 URL을 복사할 수 있습니다. 이 링크는 커넥터 플라이아웃 페이지에서도 사용할 수 있습니다.

9. **완료** 를 클릭합니다.

   새 커넥터가 커넥터 탭의 목록에 **표시됩니다.**

10. 방금 만든 HR 커넥터를 클릭하여 커넥터에 대한 속성 및 기타 정보가 포함된 플라이아웃 페이지를 표시합니다.

   ![새 HR 커넥터에 대한 플라이아웃 페이지입니다.](../media/HRConnectorWizard7.png)

아직 복사하지 않은 경우 Azure 앱 ID 및 **커넥터** 작업 ID 값을 **복사할 수 있습니다.** 다음 단계에서 스크립트를 실행하려면 이러한 단계가 필요합니다. 플라이아웃 페이지에서 스크립트를 다운로드하거나 다음 단계의 링크를 사용하여 다운로드할 수도 있습니다.

편집을 **클릭하여** 파일 매핑 페이지에서 정의한 Azure 앱 ID 또는 열 헤더 이름을 변경할 **수도** 있습니다.

## <a name="step-4-run-the-sample-script-to-upload-your-hr-data"></a>4단계: 샘플 스크립트를 실행하여 HR 데이터 업로드

HR 커넥터를 설정하는 마지막 단계는 CSV 파일(1단계에서 만든)의 HR 데이터를 Microsoft 클라우드에 업로드하는 샘플 스크립트를 실행하는 것입니다. 특히 스크립트는 데이터를 HR 커넥터에 업로드합니다. 스크립트를 실행한 후 3단계에서 만든 HR 커넥터는 내부자 위험 관리 솔루션과 같은 다른 규정 준수 도구에서 액세스할 수 있는 Microsoft 365 조직으로 HR 데이터를 가져오게 됩니다. 스크립트를 실행한 후 가장 최근의 직원 종료 데이터가 Microsoft 클라우드에 업로드될 수 있도록 작업을 매일 자동으로 실행하기 위한 작업을 계획하는 것이 좋습니다. 스크립트가 [자동으로 실행될 예약을 참조합니다.](#optional-step-6-schedule-the-script-to-run-automatically)

1. 이전 단계에서 열린 창으로 이동하여 샘플 스크립트를 사용하여 GitHub 사이트에 액세스합니다. 또는 책갈피로 지정한 사이트를 열거나 복사한 URL을 사용합니다. 여기에서 스크립트에 액세스할 수도 [있습니다.](https://github.com/microsoft/m365-hrconnector-sample-scripts/blob/master/upload_termination_records.ps1)

2. 원시 **단추를** 클릭하여 텍스트 보기에 스크립트를 표시합니다.

3. 샘플 스크립트의 모든 줄을 복사한 다음 텍스트 파일에 저장합니다.

4. 필요한 경우 조직의 샘플 스크립트를 수정합니다.

5. 파일 이름 접미사 (Windows PowerShell)를 사용하여 텍스트 파일을 스크립트 파일로 저장합니다( 예: `.ps1` `HRConnector.ps1` ). 또는 스크립트에 대한 GitHub 파일 이름()을 사용할 수 `upload_termination_records.ps1` 있습니다.

6. 로컬 컴퓨터에서 명령 프롬프트를 열고 스크립트를 저장한 디렉터리로 이동하십시오.

7. 다음 명령을 실행하여 CSV 파일의 HR 데이터를 Microsoft 클라우드에 업로드합니다. 예를 들어:

    ```powershell
    .\HRConnector.ps1 -tenantId <tenantId> -appId <appId>  -appSecret <appSecret>  -jobId <jobId>  -csvFilePath '<csvFilePath>'
    ```

   다음 표에서는 이 스크립트와 함께 사용할 매개 변수와 필요한 값에 대해 설명합니다. 이전 단계에서 얻은 정보는 이러한 매개 변수의 값에 사용됩니다.

   | 매개 변수 | 설명 |
   |:-----|:-----|:-----|
   |`tenantId`|2단계에서 획득한 Microsoft 365 조직의 ID입니다. Azure AD 관리 센터의 개요 블레이드에서  조직의 테넌트 ID를 얻을 수도 있습니다. 이는 조직을 식별하는 데 사용됩니다.|
   |`appId` |2단계에서 Azure AD에서 만든 앱의 Azure AD 응용 프로그램 ID입니다. 스크립트가 사용자 조직에 액세스하려고 할 때 Azure AD에서 Microsoft 365 사용됩니다. | 
   |`appSecret`|2단계에서 Azure AD에서 만든 앱의 Azure AD 응용 프로그램 비밀입니다. 이는 인증에도 사용됩니다.|
   |`jobId`|3단계에서 만든 HR 커넥터의 작업 ID입니다. 이는 Microsoft 클라우드에 업로드된 HR 데이터를 HR 커넥터와 연결하기 위해 사용됩니다.|
   |`csvFilePath`|1단계에서 만든 CSV 파일의 파일 경로입니다(스크립트와 동일한 시스템에 저장). 파일 경로의 공백을 방지합니다. 그렇지 않으면 인용 부호를 하나만 사용할 수 있습니다.|
   |||

   다음은 각 매개 변수에 대해 실제 값을 사용하는 HR 커넥터 스크립트 구문의 예입니다.

   ```powershell
    .\HRConnector.ps1 -tenantId d5723623-11cf-4e2e-b5a5-01d1506273g9 -appId 29ee526e-f9a7-4e98-a682-67f41bfd643e -appSecret MNubVGbcQDkGCnn -jobId b8be4a7d-e338-43eb-a69e-c513cd458eba -csvFilePath 'C:\Users\contosoadmin\Desktop\Data\employee_termination_data.csv'
    ```

   업로드가 성공하면 스크립트에 성공한 업로드 **표시됩니다.**

   > [!NOTE]
   > 실행 정책 때문에 이전 명령을 실행하는 데 문제가 있는 경우 실행 정책 설정에 대한 지침은 [실행](/powershell/module/microsoft.powershell.core/about/about_execution_policies) 정책 정보 및 [Set-ExecutionPolicy를](/powershell/module/microsoft.powershell.security/set-executionpolicy) 참조하세요.

## <a name="step-5-monitor-the-hr-connector"></a>5단계: HR 커넥터 모니터링

HR 커넥터를 만들고 스크립트를 실행하여 HR 데이터를 업로드한 후 연결기에서 커넥터를 보고 업로드 상태를 Microsoft 365 규정 준수 센터. 스크립트가 정기적으로 자동으로 실행될 수 있는 경우 스크립트가 마지막으로 실행된 후 현재 상태를 볼 수도 있습니다.

1. 으로 [https://compliance.microsoft.com](https://compliance.microsoft.com) 이동하여 왼쪽 **nav에서 데이터** 커넥터를 클릭합니다.

2. 커넥터 **탭을** 클릭한 다음 HR 커넥터를 선택하여 플라이아웃 페이지를 표시합니다. 이 페이지에는 커넥터에 대한 속성과 정보가 포함되어 있습니다.

   ![속성 및 상태가 있는 HR 커넥터 플라이아웃 페이지입니다.](../media/HRConnectorFlyout1.png)

3. 진행 **중에서**  로그 다운로드 링크를 클릭하여 커넥터의 상태 로그를 열거나 저장합니다. 이 로그에는 스크립트를 실행하고 CSV 파일의 데이터를 Microsoft 클라우드에 업로드할 때마다 대한 정보가 포함되어 있습니다. 

   ![HR 커넥터 로그 파일에는 업로드된 CSV 파일의 숫자 행이 표시됩니다.](../media/HRConnectorLogFile.png)

   필드는 업로드한 CSV 파일의 행 `RecordsSaved` 수를 나타냅니다. 예를 들어 CSV 파일에 4개의 행이 포함되어 있는 경우 스크립트가 CSV 파일의 모든 행을 업로드한 경우 필드 값은 `RecordsSaved` 4입니다.

4단계에서 스크립트를 실행하지 않은 경우 마지막 가져오기 아래에 스크립트를 다운로드하는 **링크가 표시됩니다.** 스크립트를 다운로드한 다음 단계에 따라 스크립트를 실행할 수 있습니다.

## <a name="optional-step-6-schedule-the-script-to-run-automatically"></a>(선택 사항) 6단계: 스크립트가 자동으로 실행 예약

조직의 최신 HR 데이터를 내부자 위험 관리 솔루션과 같은 도구에서 사용할 수 있도록 하는 경우 스크립트가 매일 한 번과 같이 정기적으로 자동으로 실행될 수 있도록 예약하는 것이 좋습니다. 또한 조직을 떠나는 직원에 대한 최신 정보를 포함하려면 CSV 파일의 HR 데이터를 유사한 일정(같지 않은 경우)으로 업데이트해야 합니다. 목표는 내부자 위험 관리 솔루션에서 HR 커넥터를 사용할 수 있도록 가장 최근의 HR 데이터를 업로드하는 것입니다.

작업 스케줄러 앱을 사용자 Windows 자동으로 스크립트를 실행할 수 있습니다.

1. 로컬 컴퓨터에서 시작 Windows **클릭한** 다음 작업 스케줄러 **를 입력합니다.**

2. 작업 **스케줄러 앱을 클릭하여** 열립니다.

3. 작업 **섹션에서** 작업 **만들기 를 클릭합니다.**

4. 일반 **탭에서** 예약된 작업에 대한 설명적인 이름을 입력합니다. 예: **HR 커넥터 스크립트**. 선택적 설명을 추가할 수도 있습니다.

5. 보안 **옵션 에서** 다음을 합니다.

   1. 컴퓨터에 로그온할 때만 스크립트를 실행할지 로그온할 때 스크립트를 실행할지 여부를 결정하십시오.

   1. 가장 높은 **권한으로** 실행 확인란이 선택되어 있는지 확인 합니다.

6. 트리거 **탭을** 선택하고 새로 **고치기를** 클릭한 후 다음을 실행합니다.

   1. 이 **설정** 에서 일별 옵션을 선택한 다음 처음으로 스크립트를 실행할 날짜와 시간을 선택합니다.  스크립트는 매일 같은 지정된 시간으로 실행됩니다.

   1. 고급 **설정에서** 사용 **확인란이** 선택되어 있는지 확인합니다.

   1. 확인을 **클릭합니다.**

7. 작업 **탭을** 선택하고 새로 **고치기를** 클릭한 후 다음을 수행하십시오.

   ![HR 커넥터 스크립트에 대한 새 예약된 작업을 만들기 위한 작업 설정](../media/HRConnectorScheduleTask1.png)

   1. 작업 **드롭다운** 목록에서 프로그램 시작이 선택되어 **있는지** 확인 합니다.

   1. **프로그램/스크립트 상자에서** 찾아보기를 클릭하고 다음 위치로 이동한 다음 상자에 경로를 표시하려면 을  `C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe` 선택합니다.

   1. 인수 **추가(선택 사항)** 상자에 4단계에서 실행한 동일한 스크립트 명령을 붙여 넣습니다. 예를 들어 `.\HRConnector.ps1 -tenantId "d5723623-11cf-4e2e-b5a5-01d1506273g9" -appId "c12823b7-b55a-4989-faba-02de41bb97c3" -appSecret "MNubVGbcQDkGCnn"  -jobId "e081f4f4-3831-48d6-7bb3-fcfab1581458" -csvFilePath "C:\Users\contosoadmin\Desktop\Data\employee_termination_data.csv"`

   1. 시작 **위치(선택 사항)** 상자에 4단계에서 실행한 스크립트의 폴더 위치를 붙여 넣습니다. 예를 들면 `C:\Users\contosoadmin\Desktop\Scripts`와 같습니다.

   1. **확인을** 클릭하여 새 작업의 설정을 저장합니다.

8. 작업 **만들기 창에서** **확인을** 클릭하여 예약된 작업을 저장합니다. 사용자 계정 자격 증명을 입력하라는 메시지가 표시될 수 있습니다.

   새 작업이 작업 스케줄러 라이브러리에 표시됩니다.

   ![새 작업이 작업 스케줄러 라이브러리에 표시됩니다.](../media/HRConnectorTaskSchedulerLibrary.png)

   스크립트가 마지막으로 실행된 시간 및 다음에 실행 예약이 표시됩니다. 작업을 두 번 클릭하여 편집할 수 있습니다.

   또한 준수 센터에서 해당 HR 커넥터의 플라이아웃 페이지에서 스크립트가 마지막으로 실행된 시간을 확인할 수도 있습니다.

## <a name="existing-hr-connectors"></a>기존 HR 커넥터

2020년 7월 20일, HR 커넥터에서 지원하는 추가 시나리오를 출시했습니다. 이 문서에서 이전에 설명한 HR 시나리오입니다. 이 날짜 전에 만든 모든 HR 커넥터는 직원 퇴사 시나리오만 지원됩니다. 2020년 7월 20일 전에 HR 커넥터를 만든 경우 HR 데이터를 Microsoft 클라우드로 계속 마이그레이션할 수 있도록 HR 커넥터를 마이그레이션했습니다. 이 기능을 유지 관리하기 위해 아무 것도 할 것이 없습니다. 중단 없이 커넥터를 계속 사용할 수 있습니다.

추가 HR 시나리오를 구현하려는 경우 새 HR 커넥터를 만들고 릴리스된 추가 HR 시나리오에 맞게 구성하십시오. 또한 추가 HR 시나리오를 지원하기 위해 데이터가 포함된 하나 이상의 새 CSV 파일을 만들어야 합니다. 새 HR 커넥터를 만든 후 추가 HR 시나리오에 대한 데이터와 함께 새 커넥터 및 CSV 파일의 작업 ID를 사용하여 스크립트를 실행합니다.