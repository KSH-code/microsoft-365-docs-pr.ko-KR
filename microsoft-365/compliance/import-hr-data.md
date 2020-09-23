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
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: 관리자는 조직의 HR (인적 자원) 시스템에서 직원 데이터를 Microsoft 365로 가져오는 데이터 커넥터를 설정할 수 있습니다. 이를 통해 참가자 위험 관리 정책에 HR 데이터를 사용 하 여 조직에 내부적인 위협을 초래할 수 있는 특정 사용자의 작업을 검색 하는 데 도움을 받을 수 있습니다.
ms.openlocfilehash: 31afa01a518028e7ec25116e947b4e0d6dc94dac
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201547"
---
# <a name="set-up-a-connector-to-import-hr-data"></a>HR 데이터를 가져올 커넥터 설정

Microsoft 365 준수 센터에서 데이터 커넥터를 설정 하 여 사용자의 resignation 또는 사용자의 작업 수준 변경 같은 이벤트와 관련 된 HR (인적 자원) 데이터를 가져올 수 있습니다. 그런 다음 [참가자 위험 관리 솔루션](insider-risk-management.md) 에서 HR 데이터를 사용 하 여 조직 내부의 사용자가 악의적 활동 또는 데이터 절도를 식별 하는 데 도움이 되는 위험 지표를 생성할 수 있습니다.

참가자가 위험 지표를 생성 하는 데 사용할 수 있는 HR 데이터에 대 한 커넥터를 설정 하는 작업은 HR 데이터를 포함 하는 CSV 파일을 만드는 것으로 구성 됩니다. 인증에 사용 되는 Azure Active Directory에서 응용 프로그램을 만들고, Microsoft 365 준수 센터에서 HR 데이터 커넥터를 만든 다음, ingests에서 사용할 수 있도록 CSV 파일의 HR 데이터를 Microsoft 클라우드에 보내도록 스크립트 (예약 된 방식으로)를 실행 합니다. 위험 관리 솔루션

## <a name="before-you-begin"></a>시작하기 전에

- Microsoft 365로 가져올 HR 시나리오 및 데이터를 결정 합니다. 이를 통해 만들려는 CSV 파일 및 HR 커넥터의 수와 CSV 파일 생성 및 구조화 방법을 결정 하는 데 도움이 됩니다. 가져올 HR 데이터는 구현 하려는 참가자 위험 관리 정책에 따라 결정 됩니다. 자세한 내용은 1 단계를 참조 하십시오.

- 조직의 HR 시스템에서 데이터를 검색 하거나 내보내는 방법 (및 정기적으로)을 결정 하 고 1 단계에서 만든 CSV 파일에 추가 합니다. 4 단계에서 실행 하는 스크립트는 CSV 파일의 HR 데이터를 Microsoft 클라우드에 업로드 합니다.

- 조직에서는 Office 365 가져오기 서비스가 조직의 데이터에 액세스 하도록 허용 하는 데 동의 해야 합니다. 이 요청에 동의 하려면 [이 페이지로](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)이동 하 여 Microsoft 365 전역 관리자의 자격 증명으로 로그인 한 다음 요청을 수락 합니다. 3 단계에서 HR 커넥터를 성공적으로 만들기 전에이 단계를 완료 해야 합니다.

- 3 단계에서 HR 커넥터를 만드는 사용자에 게 Exchange Online의 사서함 가져오기 내보내기 역할이 할당 되어야 합니다. 기본적으로이 역할은 Exchange Online의 어떤 역할 그룹에도 할당되지 않습니다. Exchange Online의 조직 관리 역할 그룹에 사서함 가져오기 내보내기 역할을 추가할 수 있습니다. 또는 새 역할 그룹을 만들고 사서함 가져오기 내보내기 역할을 할당 한 다음 해당 사용자를 구성원으로 추가할 수 있습니다. 자세한 내용은 "Exchange Online에서 역할 그룹 관리" 문서의 [역할 그룹 만들기](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 또는 [역할 그룹 수정](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 섹션을 참조 하세요.

- 4 단계에서 실행 하는 예제 스크립트는 참가자 위험 관리 솔루션에서 사용할 수 있도록 HR 데이터를 Microsoft 클라우드에 업로드 합니다. 이 샘플 스크립트는 Microsoft standard 지원 프로그램 또는 서비스에서 지원 되지 않습니다. 예제 스크립트는 어떤 종류의 보증도 없이 있는 그대로 제공 됩니다. 또한 Microsoft는 묵시적인 모든 보증(상품성 또는 특정 목적에의 적합성에 대한 묵시적인 보증을 포함하되 이에 제한되지 않음)을 부인합니다. 샘플 스크립트 및 설명서의 사용 또는 성능으로 인해 발생 하는 전체 위험은 사용자에 게 남아 있습니다. 어떠한 경우에도 Microsoft, 스크립트 작성자 또는 그외 스크립트의 작성, 생산 또는 제공과 관련된 사람은 누구나 샘플 스크립트 또는 문서의 사용 또는 사용할 수 없음으로 인해 발생하는 모든 손해(수익 손실, 비즈니스 중단, 비즈니스 정보 손실 또는 기타 금전상의 손실을 포함하되 이에 제한되지 않음)에 대해 책임지지 않습니다. 이는 Microsoft가 이러한 손해가 발생할 가능성에 대해 알았더라도 마찬가지입니다.

## <a name="step-1-prepare-a-csv-file-with-your-hr-data"></a>1 단계: HR 데이터를 사용 하 여 CSV 파일 준비

첫 번째 단계는 커넥터가 Microsoft 365로 가져올 HR 데이터를 포함 하는 CSV 파일을 만드는 것입니다. 이 데이터는 참가자 위험 솔루션에서 잠재적 위험 지표를 생성 하는 데 사용 됩니다. 다음 HR 시나리오에 대 한 데이터를 Microsoft 365로 가져올 수 있습니다.

- 직원 resignation 조직을 떠난 사용자에 대 한 정보입니다.

- 작업 수준 변경 승격 및 강등와 같은 사용자의 작업 수준 변경에 대 한 정보입니다.

- 성과 검토 사용자 성능에 대 한 정보입니다.

- 성능 개선 계획 사용자를 위한 성능 향상 계획에 대 한 정보

가져올 HR 데이터의 유형은 참가자 위험 관리 정책 및 구현할 해당 하는 정책 템플릿에 따라 달라 집니다. 다음 표에는 각 정책 템플릿에 필요한 HR 데이터 형식이 나와 있습니다.

| **정책 템플릿**| **HR 데이터 형식**|
|:-----------------------------------------------|:---------------------------------------------------------------------|
| Departing 사용자의 데이터 도난                   | 직원 resignations                                                 |
| 일반 데이터 누수                              | 해당 사항 없음                                                        |
| 우선 순위 사용자 별 데이터 유출                    | 해당 사항 없음                                                        |
| 불만 사용자에의 한 데이터 유출                 | 작업 수준 변경, 성능 검토, 성능 개선 계획 |
| 일반 보안 정책 위반              | 해당 사항 없음                                                        |
| Departing 사용자의 보안 정책 위반   | 직원 resignations                                                 |
| 우선 순위 사용자 별 보안 정책 위반    | 해당 사항 없음                                                        |
| 불만 사용자에의 한 보안 정책 위반 | 작업 수준 변경, 성능 검토, 성능 개선 계획 |
| 전자 메일의 공격적인 언어                     | 해당 사항 없음                                                        |

참가자 위험 관리의 정책 템플릿에 대 한 자세한 내용은 [참가자 위험 관리 정책을](insider-risk-management-policies.md#policy-templates)참조 하세요.

각 HR 시나리오에서 해당 하는 HR 데이터를 하나 이상의 CSV 파일에 제공 해야 합니다. 사용자의 참가자 위험 관리 구현에 사용할 CSV 파일의 수는이 섹션의 뒷부분에서 설명 합니다.

필요한 HR 데이터로 CSV 파일을 만든 후에는 4 단계에서 스크립트를 실행 하는 로컬 컴퓨터에 저장 합니다. 또한 스크립트를 실행 하는 모든 작업을 위해 CSV 파일에 항상 최신 정보가 포함 되도록 하기 위해 업데이트 전략을 구현 해야 하며, 가장 최근 HR 데이터는 Microsoft 클라우드에 업로드 되 고 참가자 위험 관리 솔루션에 액세스할 수 있도록 합니다.

> [!IMPORTANT]
> 다음 섹션에서 설명 하는 열 이름은 필수 매개 변수로, 예제 일 뿐입니다. CSV 파일에는 모든 열 이름을 사용할 수 있습니다. 그러나 3 단계에서 HR 커넥터를 만들 때 CSV 파일에서 사용 하는 열 이름은 데이터 형식에 매핑되어야 *합니다* . 또한 다음 섹션의 예제 CSV 파일은 메모장 보기에 표시 됩니다. Microsoft Excel에서 CSV 파일을 확인 하 고 편집 하는 것이 훨씬 더 쉽습니다.

다음 섹션에서는 각 HR 시나리오에 필요한 CSV 데이터에 대해 설명 합니다.

### <a name="csv-file-for-employee-resignation-data"></a>직원 resignation 데이터에 대 한 CSV 파일

다음은 employee resignation 데이터에 대 한 CSV 파일의 예입니다.

```text
EmailAddress,ResignationDate,LastWorkingDate
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,2019-04-29T15:18:02.4675041+05:30
pilarp@contoso.com,2019-04-24T09:15:49Z,2019-04-29T15:18:02.7117540
```

다음 표에는 employee resignation 데이터의 CSV 파일에 있는 각 열에 대 한 설명이 나와 있습니다.

| **열**  |  **설명**|
|:------------|:----------------|
|**EmailAddress**| 종료 된 사용자의 전자 메일 주소 (UPN)를 지정 합니다.|
| **ResignationDate** | 사용자의 고용 기한을 조직에서 공식적으로 종료 한 날짜를 지정 합니다. 예를 들어이는 사용자가 조직 내 상태에 대 한 알림을 받은 날짜 일 수 있습니다. 이 날짜는 사용자가 마지막으로 작업 한 날짜와 다를 수 있습니다. 다음 날짜 형식 ( `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` [ISO 8601 날짜 및 시간 형식](https://www.iso.org/iso-8601-date-and-time-format.html))을 사용 합니다.|
| **LastWorkingDate** | 종료 된 사용자에 대 한 마지막 작업 날짜를 지정 합니다. 다음 날짜 형식 ( `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` [ISO 8601 날짜 및 시간 형식](https://www.iso.org/iso-8601-date-and-time-format.html))을 사용 합니다.|
|||

### <a name="csv-file-for-job-level-changes-data"></a>작업 수준 변경 데이터에 대 한 CSV 파일

다음은 작업 수준 변경 데이터에 대 한 CSV 파일의 예입니다.

```text
EmailAddress,EffectiveDate,OldLevel,NewLevel
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,Level 61 – Sr. Manager,Level 60- Manager
pillar@contoso.com,2019-04-23T15:18:02.4675041+05:30,Level 62 – Director,Level 60- Sr. Manager
```

다음 표에는 작업 수준 변경 데이터에 대 한 CSV 파일의 각 열에 대 한 설명이 나와 있습니다.

| **열**|**설명**|
|:--------- |:------------- |
| **EmailAddress**  | 사용자의 전자 메일 주소 (UPN)를 지정 합니다.|
| **EffectiveDate** | 사용자의 작업 수준이 공식적으로 변경 된 날짜를 지정 합니다. 다음 날짜 형식 ( `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` [ISO 8601 날짜 및 시간 형식](https://www.iso.org/iso-8601-date-and-time-format.html))을 사용 합니다.|
| **설명**| 평가기에서 작업 수준 변경에 대해 제공한 주의 사항을 지정 합니다. 200 자 제한을 입력할 수 있습니다. 이 매개 변수는 선택 사항입니다. CSV 파일에는이를 포함할 필요가 없습니다.|
| **OldLevel**| 사용자가 변경 되기 전에 작업 수준을 지정 합니다. 이것은 자유 텍스트 매개 변수 이며 조직의 계층적 분류를 포함할 수 있습니다. 이 매개 변수는 선택 사항입니다. CSV 파일에는이를 포함할 필요가 없습니다.|
| **새 수준**| 변경 후 사용자의 작업 수준을 지정 합니다. 이것은 자유 텍스트 매개 변수 이며 조직의 계층적 분류를 포함할 수 있습니다. 이 매개 변수는 선택 사항입니다. CSV 파일에는이를 포함할 필요가 없습니다.|
|||

### <a name="csv-file-for-performance-review-data"></a>성과 검토 데이터에 대 한 CSV 파일

다음은 성능 데이터에 대 한 CSV 파일의 예입니다.

```text
EmailAddress,EffectiveDate,Remarks,Rating
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,Met expectations but bad attitude,2-Below expectation
pillar@contoso.com,2019-04-23T15:18:02.4675041+05:30, Multiple conflicts with the team
```

다음 표에는 성능 검토 데이터에 대 한 CSV 파일의 각 열에 대 한 설명이 나와 있습니다.

| **열**|**설명**|
|:----------|:--------------|
| **EmailAddress**  | 사용자의 전자 메일 주소 (UPN)를 지정 합니다.|
| **EffectiveDate** | 사용자가 성과 검토 결과에 대해 공식적으로 정보가 제공 된 날짜를 지정 합니다. 이는 성과 검토 주기가 종료 된 날짜 일 수 있습니다. 다음 날짜 형식 ( `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` [ISO 8601 날짜 및 시간 형식](https://www.iso.org/iso-8601-date-and-time-format.html))을 사용 합니다.|
| **설명**| 평가자가 성과 검토를 위해 사용자에 게 제공 하는 비고를 지정 합니다. 200 자 제한이 있는 텍스트 매개 변수입니다. 이 매개 변수는 선택 사항입니다. CSV 파일에는이를 포함할 필요가 없습니다.|
| **점으로**| 성과 검토에 제공 되는 등급을 지정 합니다. 이는 텍스트 매개 변수 이며 조직에서 평가를 인식 하는 데 사용 하는 자유 형식 텍스트를 포함할 수 있습니다. 예를 들어 "3 개 예상 기대치" 또는 "2 미만 평균"을 예로 들 있습니다. 이 매개 변수는 25 자로 제한 되는 문자입니다. 이 매개 변수는 선택 사항입니다. CSV 파일에는이를 포함할 필요가 없습니다.|
|||

### <a name="csv-file-for-performance-improvement-plan-data"></a>성능 개선 계획 데이터에 대 한 CSV 파일

다음은 성능 향상 계획 데이터에 대 한 데이터에 대 한 CSV 파일의 예입니다.

```text
EmailAddress,EffectiveDate,ImprovementRemarks,PerformanceRating
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,Met expectation but bad attitude,2-Below expectation
pillar@contoso.com,2019-04-23T15:18:02.4675041+05:30, Multiple conflicts with the team
```

다음 표에는 성능 검토 데이터에 대 한 CSV 파일의 각 열에 대 한 설명이 나와 있습니다.

| **열**| **설명**|
|:----------|:---------------|
| **EmailAddress**  | 사용자의 전자 메일 주소 (UPN)를 지정 합니다.|
| **EffectiveDate** | 사용자가 성능 개선 계획에 대해 공식적으로 정보를 받은 날짜를 지정 합니다. `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` [ISO 8601 날짜 및 시간 형식인와](https://www.iso.org/iso-8601-date-and-time-format.html)같은 날짜 형식을 사용 해야 합니다.|
| **설명**| 평가기에서 성능 개선 계획에 대해 제공한 모든 주의 사항을 지정 합니다. 200 자 제한이 있는 텍스트 매개 변수입니다. 선택적 매개 변수입니다. CSV 파일에는이를 포함할 필요가 없습니다. |
| **점으로**| 성과 검토와 관련 된 등급이 나 기타 정보를 지정 합니다. 성능 개선 계획 이는 텍스트 매개 변수 이며 조직에서 평가를 인식 하는 데 사용 하는 무료 양식 텍스트가 포함 될 수 있습니다. 예를 들어 "3 개 예상 기대치" 또는 "2 미만 평균"을 예로 들 있습니다. 이 매개 변수는 25 자로 제한 되는 문자입니다. 선택적 매개 변수입니다. CSV 파일에는이를 포함할 필요가 없습니다.|
|||

### <a name="determining-how-many-csv-files-to-use-for-hr-data"></a>HR 데이터에 사용할 CSV 파일 수 결정

3 단계에서는 각 HR 데이터 형식에 대해 별도의 커넥터를 만들도록 선택 하거나, 모든 데이터 형식에 대해 단일 커넥터를 만들도록 선택할 수 있습니다. 한 가지 HR 시나리오 (이전 섹션에서 설명한 CSV 파일 예제)에 대 한 데이터가 포함 된 별도의 CSV 파일을 사용할 수 있습니다. 또는 두 개 이상의 HR 시나리오에 대 한 데이터를 포함 하는 단일 CSV 파일을 사용할 수 있습니다. 다음은 HR 데이터에 사용할 CSV 파일의 수를 결정 하는 데 도움이 되는 몇 가지 지침입니다.

- 구현 하려는 참가자 위험 관리 정책에 여러 HR 데이터 형식이 필요한 경우 필요한 모든 데이터 형식을 포함 하는 단일 CSV 파일을 사용 하는 것이 좋습니다.

- HR 데이터를 생성 하거나 수집 하는 방법에 따라 CSV 파일의 수가 결정 될 수 있습니다. 예를 들어 HR 커넥터를 구성 하는 데 사용 되는 다양 한 HR 데이터 유형이 조직의 단일 HR 시스템에 있는 경우 데이터를 단일 CSV 파일로 내보낼 수 있습니다. 그러나 데이터가 서로 다른 HR 시스템에 분산 되어 있는 경우에는 데이터를 다른 CSV 파일로 내보내는 것이 더 쉬울 수 있습니다. 예를 들어 직원 resignation 데이터는 작업 수준 또는 성과 검토 데이터와는 다른 HR 시스템에 있을 수 있습니다. 이 경우에는 데이터를 단일 CSV 파일에 수동으로 결합 하지 않고 별도의 CSV 파일을 사용할 수 있는 것이 더 쉽습니다. 따라서 HR 시스템에서 데이터를 검색 하거나 내보내는 방법에 따라 CSV 파일의 수를 결정할 수 있습니다.

- 일반적으로 만드는 데 필요한 HR 커넥터의 수는 CSV 파일의 데이터 형식에 따라 결정 됩니다. 예를 들어, 사용자의 참가자 위험 관리 구현을 지 원하는 데 필요한 모든 데이터 형식이 CSV 파일에 포함 되어 있는 경우 HR 커넥터는 하나만 있으면 됩니다. 그러나 각각 단일 데이터 형식을 포함 하는 두 개의 별도 CSV 파일이 있는 경우에는 두 개의 HR 커넥터를 만들어야 합니다. 단,이는 CSV 파일에 **Hrscenario** 열을 추가 하는 경우 (다음 섹션 참조) 다른 CSV 파일을 처리할 수 있는 단일 HR 커넥터를 구성할 수 있다는 것입니다.

### <a name="configuring-a-single-csv-file-for-multiple-hr-data-types"></a>여러 HR 데이터 형식에 대 한 단일 CSV 파일 구성

여러 HR 데이터 형식을 단일 CSV 파일에 추가할 수 있습니다. 이 기능은 구현 하는 참가자 위험 관리 솔루션에 여러 HR 데이터 형식이 필요 하거나 데이터 형식이 조직의 단일 HR 시스템에 있는 경우에 유용 합니다. CSV 파일의 수가 적으면 항상 만들고 관리할 HR 커넥터 수를 줄여 줍니다.

다음은 여러 데이터 형식을 사용 하 여 CSV 파일을 구성 하기 위한 요구 사항입니다.

- 각 데이터 형식 및 머리글 행의 해당 열 이름에 필요한 열 (및 사용 하는 경우에는 선택적)을 추가 해야 합니다. 데이터 형식이 열에 해당 하지 않는 경우에는이 값을 비워 둘 수 있습니다.

- 여러 유형의 HR 데이터와 함께 CSV 파일을 사용 하려면 HR 커넥터는 CSV 파일에서 HR 데이터를 입력할 수 있는 행을 파악 해야 합니다. 이 작업은 CSV 파일에 **Hrscenario** 열을 추가 하 여 수행 합니다. 이 열의 값은 각 행의 HR 데이터 유형을 식별 합니다. 예를 들어 4 개의 HR 시나리오에 해당 하는 값은 \` Resignation \` , \` 작업 수준 변경 \` , \` 성과 검토 \` 및 \` 성능 개선 계획 \` 일 수 있습니다.

- HRScenario * * 열이 포함 된 CSV 파일이 여러 개 있는 경우 각 파일에서 특정 HR 시나리오를 식별 하는 동일한 열 이름과 동일한 값을 사용 해야 합니다.

다음은 **Hrscenario** 열이 포함 된 CSV 파일을 보여 주는 예제입니다. HRScenario 열의 값은 해당 행의 데이터 형식을 식별 합니다.

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
> 사용자는 CSV 파일의 열 이름을 3 단계에서 커넥터를 설정할 때 HR 데이터 형식을 식별 하는 열로 매핑하도록 하기 때문에 HR 데이터 형식을 식별 하는 열에 임의의 이름을 사용할 수 있습니다. 또한 연결선을 설정할 때 데이터 형식 열에 사용 되는 값을 매핑합니다.

### <a name="adding-the-hrscenario-column-to-a-csv-file-that-contains-a-single-data-type"></a>단일 데이터 형식이 포함 된 CSV 파일에 HRScenario 열 추가

조직의 HR 시스템 및 HR 데이터를 CSV 파일로 내보내는 방법을 기반으로 단일 HR 데이터 형식을 포함 하는 여러 CSV 파일을 만들어야 할 수 있습니다. 이 경우에도 다른 CSV 파일에서 데이터를 가져오기 위한 HR 커넥터를 하나만 만들 수 있습니다. 이 작업을 수행 하려면 CSV 파일에 HRScenario 열을 추가 하 고 HR 데이터 형식을 지정 하기만 하면 됩니다. 그런 다음 각 CSV 파일에 대해 스크립트를 실행할 수 있지만 커넥터에 동일한 작업 ID를 사용 합니다. [4 단계](#step-4-run-the-sample-script-to-upload-your-hr-data)를 참조 하세요.

## <a name="step-2-create-an-app-in-azure-active-directory"></a>2 단계: Azure Active Directory에 앱 만들기

다음 단계에서는 Azure Active Directory (Azure AD)에서 새 앱을 만들고 등록 합니다. 이 앱은 3 단계에서 만든 HR 커넥터에 해당 합니다. 이 앱을 만들면 Azure AD가를 실행 하 여 조직에 액세스 하려고 할 때 HR 커넥터를 인증할 수 있습니다. 이 앱은 Microsoft 클라우드로 HR 데이터를 업로드 하는 4 단계에서 실행 하는 스크립트를 인증 하는 데에도 사용 됩니다. 이 Azure AD 앱을 만드는 동안 다음 정보를 저장 해야 합니다. 이러한 값은 3 단계와 4 단계에서 사용 됩니다.

- Azure AD 응용 프로그램 ID ( *앱 id* 또는 *클라이언트 ID*라고도 함)

- Azure AD 응용 프로그램 암호 ( *클라이언트 비밀이*라고도 함)

- 테 넌 트 Id ( *디렉터리 Id*라고도 함)

Azure AD에서 앱을 만드는 단계별 지침은 [Microsoft id 플랫폼을 사용 하 여 응용 프로그램 등록](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)을 참조 하세요.

## <a name="step-3-create-the-hr-connector"></a>3 단계: HR 커넥터 만들기

다음 단계는 Microsoft 365 준수 센터에서 HR 커넥터를 만드는 것입니다. 4 단계에서 스크립트를 실행 하면 사용자가 만든 HR 커넥터가 CSV 파일의 HR 데이터를 Microsoft 365 조직으로 수집 합니다. 커넥터를 만들기 전에 HR 시나리오 목록과 각 항목에 해당 하는 CSV 열 이름을 포함 해야 합니다. 커넥터를 구성할 때 각 시나리오에 필요한 데이터를 CSV 파일의 실제 열 이름에 매핑해야 합니다. 또는 커넥터를 구성할 때 예제 CSV 파일을 업로드 하 고 마법사를 통해 필요한 데이터 형식에 열 이름을 매핑할 수 있습니다.

이 단계를 완료 한 후 커넥터를 만들 때 생성 되는 작업 ID를 복사 해야 합니다. 스크립트를 실행할 때 작업 ID를 사용 합니다.

1. 로 이동한 [https://compliance.microsoft.com](https://compliance.microsoft.com/) 후 왼쪽 탐색 창에서 **데이터 커넥터** 를 클릭 합니다.

2. **데이터 커넥터** 페이지의 **HR**에서 **보기**를 클릭 합니다.

3. **HR 사용자 지정** 페이지에서 **커넥터 추가**를 클릭 합니다.

4. **연결 설정** 페이지에서 다음을 수행한 후 **다음**을 클릭 합니다.

   a. 2 단계에서 만든 Azure 앱에 대 한 Azure AD 응용 프로그램 ID를 입력 하거나 붙여넣습니다.

   b. HR 커넥터의 이름을 입력 합니다.

5. HR 시나리오 페이지에서 데이터를 가져올 HR 시나리오를 하나 이상 선택 하 고 **다음**을 클릭 합니다.

6. 파일 매핑 방법 페이지에서 다음 옵션 중 하나를 선택 하 고 **다음**을 클릭 합니다.

   - **샘플 파일을 업로드**합니다. 이 옵션을 선택 하는 경우 **예제 파일 업로드** 를 클릭 하 여 1 단계에서 준비한 CSV 파일을 업로드 합니다. 이 옵션을 사용 하면 드롭다운 목록에서 CSV 파일의 열 이름을 빠르게 선택 하 여 이전에 선택한 HR 시나리오의 데이터 형식에 매핑할 수 있습니다.

   또는

   - **매핑 세부 정보를 수동으로 입력**합니다. 이 옵션을 선택 하는 경우에는 CSV 파일에 열 이름을 입력 해야 이전에 선택한 HR 시나리오의 데이터 형식에 매핑할 수 있습니다.

7. 파일 매핑 세부 정보 페이지에서 예제 CSV 파일을 업로드 했는지와 단일 HR 시나리오에 대 한 커넥터를 구성 하는지 또는 여러 시나리오에 따라 다음 중 하나를 수행 합니다. 샘플 파일을 업로드 한 경우에는 열 이름을 입력할 필요가 없습니다. 드롭다운 목록에서 선택 합니다.

    - 이전 단계에서 단일 HR 시나리오를 선택한 경우 1 단계에서 만든 CSV 파일의 열 머리글 이름 ( *매개 변수*라고도 함)을 해당 하는 각 상자에 입력 합니다. 입력 하는 열 이름은 대/소문자를 구분 하지 않지만 CSV 파일의 열 이름에 공백이 포함 되어 있으면 공백을 포함 해야 합니다. 앞에서 설명한 것 처럼 이러한 상자에 입력 하는 이름은 CSV 파일의 매개 변수 이름과 일치 해야 합니다. 예를 들어 다음 스크린샷에서는 1 단계에 나와 있는 employee resignation HR 시나리오에 대 한 예제 CSV 파일의 매개 변수 이름을 보여 줍니다.

    - 위 단계에서 여러 데이터 형식을 선택한 경우에는 CSV 파일에서 HR 데이터 형식을 식별 하는 식별자 열 이름을 입력 해야 합니다. Id 열 이름을 입력 한 후에는이 HR 데이터 형식을 식별 하는 값을 입력 하 고 선택한 각 데이터 형식에 대 한 각각의 해당 상자에서 1 단계에서 만든 CSV 파일에서 선택한 데이터 형식에 대 한 열 헤더 이름을 입력 합니다. 앞에서 설명한 것 처럼 이러한 상자에 입력 하는 이름은 CSV 파일의 열 이름과 일치 해야 합니다.

8. **검토** 페이지에서 설정을 검토 하 고 **마침을** 클릭 하 여 커넥터를 만듭니다.

   커넥터를 만들었는지 확인 하는 상태 페이지가 표시 됩니다. 이 페이지에는 예제 스크립트를 실행 하 여 HR 데이터를 업로드 하기 위해 다음 단계를 완료 하는 데 필요한 두 가지 중요 한 사항이 포함 되어 있습니다.

   ![작업 ID가 포함 된 검토 페이지 및 샘플 스크립트에 대 한 github에 대 한 링크](../media/HRConnector_Confirmation.png)

   a. **작업 ID입니다.** 다음 단계에서 스크립트를 실행 하려면이 작업 ID가 필요 합니다. 이 페이지 또는 커넥터 플라이 아웃 페이지에서이를 복사할 수 있습니다.

   b. **예제 스크립트에 연결 됩니다.** **다음** 링크를 클릭 하 여 GitHub 사이트로 이동 하 여 예제 스크립트에 액세스 합니다 (새 창을 여는 링크). 4 단계에서 스크립트를 복사할 수 있도록이 창을 열어 둡니다. 또는 스크립트를 실행할 때 대상에 책갈피를 추가한 다음 다시 액세스할 수 있도록 URL을 복사할 수 있습니다. 이 링크는 커넥터 플라이 아웃 페이지 에서도 사용할 수 있습니다.

9. **완료**를 클릭합니다.

   새 커넥터가 **커넥터** 탭의 목록에 표시 됩니다.

10. 방금 만든 HR 커넥터를 클릭 하 여 커넥터에 대 한 속성 및 기타 정보를 포함 하는 플라이 아웃 페이지를 표시 합니다.

   ![새 HR 커넥터에 대 한 플라이 아웃 페이지](../media/HRConnectorWizard7.png)

아직 수행 하지 않은 경우 **Azure 앱 id** 및 **커넥터 작업 id**의 값을 복사할 수 있습니다. 스크립트를 실행 하려면 다음 단계에서이를 수행 해야 합니다. 또한 플라이 아웃 페이지에서 스크립트를 다운로드 하거나 다음 단계에 있는 링크를 사용 하 여 다운로드할 수 있습니다.

**편집** 을 클릭 하 여 AZURE 앱 ID 또는 **파일 매핑** 페이지에서 정의한 열 머리글 이름을 변경할 수도 있습니다.

## <a name="step-4-run-the-sample-script-to-upload-your-hr-data"></a>4 단계: 예제 스크립트를 실행 하 여 HR 데이터 업로드

HR 커넥터를 설정 하는 마지막 단계에서는 1 단계에서 만든 CSV 파일의 HR 데이터를 Microsoft 클라우드에 업로드 하는 예제 스크립트를 실행 합니다. 특히 스크립트는 데이터를 HR 커넥터에 업로드 합니다. 스크립트를 실행 하면 3 단계에서 만든 HR 커넥터가 Microsoft 365 조직에 게 HR 데이터를 가져오고,이는 참가자 위험 관리 솔루션과 같은 다른 규정 준수 도구에서 액세스할 수 있습니다. 스크립트를 실행 한 후에는 가장 최근 직원 종료 데이터가 Microsoft 클라우드에 업로드 되도록 매일 자동으로 실행 되는 작업을 예약 하는 것이 좋습니다. [스크립트를 자동으로 실행 하도록 예약을](#optional-step-6-schedule-the-script-to-run-automatically)참조 하십시오.

1. 이전 단계에서 연 창으로 이동 하 여 샘플 스크립트를 사용 하 여 GitHub 사이트에 액세스 합니다. 또는 책갈피가 설정 된 사이트를 열거나 복사한 URL을 사용 합니다.

2. **Raw** 단추를 클릭 하 여 스크립트를 텍스트 보기로 표시 합니다.

3. 예제 스크립트의 모든 줄을 복사한 다음 텍스트 파일에 저장 합니다.

4. 필요한 경우 조직에 대 한 예제 스크립트를 수정 합니다.

5. 파일 이름 접미사를 사용 하 여 텍스트 파일을 Windows PowerShell 스크립트 파일로 저장 `.ps1` 합니다 (예:) `HRConnector.ps1` .

6. 로컬 컴퓨터에서 명령 프롬프트를 열고 스크립트를 저장 한 디렉터리로 이동 합니다.

7. 다음 명령을 실행 하 여 CSV 파일의 HR 데이터를 Microsoft 클라우드에 업로드 합니다. 예를 들어:

    ```powershell
    .\HRConnector.ps1 -tenantId <tenantId> -appId <appId>  -appSecret <appSecret>  -jobId <jobId>  -csvFilePath '<csvFilePath>'
    ```

   다음 표에서는이 스크립트와 함께 사용 하는 매개 변수와 해당 필수 값에 대해 설명 합니다. 위의 단계에서 얻은 정보는 이러한 매개 변수의 값에 사용 됩니다.

   |**매개 변수**|**설명**
   |:-----|:-----|:-----|
   |`tenantId`|이는 2 단계에서 구한 Microsoft 365 조직의 Id입니다. Azure AD 관리 센터의 **개요** 블레이드에서 조직에 대 한 테 넌 트 Id를 가져올 수도 있습니다. 이는 조직을 식별 하는 데 사용 됩니다.|
   |`appId` |이는 2 단계에서 Azure AD에 만든 앱의 Azure AD 응용 프로그램 Id입니다. 스크립트에서 Microsoft 365 조직에 액세스 하려고 할 때 인증을 위해 Azure AD에서 사용 됩니다. | 
   |`appSecret`|이는 2 단계에서 Azure AD에 만든 앱에 대 한 Azure AD 응용 프로그램 비밀입니다. 인증에도 사용 됩니다.|
   |`jobId`|3 단계에서 만든 HR 커넥터의 작업 ID입니다. 이는 HR 커넥터를 사용 하 여 Microsoft 클라우드에 업로드 된 HR 데이터를 연결 하는 데 사용 됩니다.|
   |`csvFilePath`|1 단계에서 만든 CSV 파일 (스크립트와 같은 시스템에 저장 됨)의 파일 경로입니다. 파일 경로에 공백이 생기지 않도록 합니다. 그렇지 않으면 작은따옴표를 사용 합니다.|
   |||

   다음은 각 매개 변수에 대 한 실제 값을 사용 하는 HR connector 스크립트의 구문 예입니다.

   ```powershell
    .\HRConnector.ps1 -tenantId d5723623-11cf-4e2e-b5a5-01d1506273g9 -appId 29ee526e-f9a7-4e98-a682-67f41bfd643e -appSecret MNubVGbcQDkGCnn -jobId b8be4a7d-e338-43eb-a69e-c513cd458eba -csvFilePath 'C:\Users\contosoadmin\Desktop\Data\employee_termination_data.csv'
    ```

   업로드가 성공 하면 스크립트에서 **업로드 성공** 메시지를 표시 합니다.

   > [!NOTE]
   > 실행 정책으로 인해 이전 명령을 실행 하는 데 문제가 있는 경우 [에](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies) 는 실행 정책 및 [ExecutionPolicy](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy) for the execution 정책만 설정에 대 한 지침을 참조 하십시오.

## <a name="step-5-monitor-the-hr-connector"></a>5 단계: HR 커넥터 모니터링

HR 커넥터를 만들고 스크립트를 실행 하 여 HR 데이터를 업로드 한 후에는 Microsoft 365 준수 센터에서 커넥터 및 업로드 상태를 볼 수 있습니다. 스크립트를 정기적으로 실행 하도록 예약 하는 경우 마지막으로 스크립트를 실행 한 후 현재 상태를 볼 수 있습니다.

1. 으로 이동 하 여 [https://compliance.microsoft.com](https://compliance.microsoft.com) 왼쪽 탐색 창에서 **데이터 커넥터** 를 클릭 합니다.

2. **커넥터 탭을** 클릭 한 다음 HR 커넥터를 선택 하 여 커넥터에 대 한 속성 및 정보가 포함 된 플라이 아웃 페이지를 표시 합니다.

   ![속성 및 상태가 포함 된 HR 커넥터 플라이 아웃 페이지](../media/HRConnectorFlyout1.png)

3. **진행 중**에서 **로그 다운로드** 링크를 클릭 하 여 커넥터의 상태 로그를 열거나 저장 합니다. 이 로그는 스크립트가 실행 될 때마다 정보를 포함 하며 CSV 파일의 데이터를 Microsoft 클라우드에 업로드 합니다. 

   ![HR 커넥터 로그 파일은 업로드 된 CSV 파일의 번호 행을 표시 합니다.](../media/HRConnectorLogFile.png)

   이 `RecordsSaved` 필드에는 CSV 파일에서 업로드 된 행의 수가 표시 됩니다. 예를 들어 CSV 파일에 행이 4 개 있는 경우 `RecordsSaved` 스크립트가 csv 파일의 모든 행을 성공적으로 업로드 한 경우 필드 값은 4가 됩니다.

4 단계에서 스크립트를 실행 하지 않은 경우 스크립트를 다운로드 하기 위한 링크가 **마지막 가져오기**아래에 표시 됩니다. 스크립트를 다운로드 한 다음 단계에 따라 스크립트를 실행할 수 있습니다.

## <a name="optional-step-6-schedule-the-script-to-run-automatically"></a>반드시 6 단계: 스크립트가 자동으로 실행 되도록 예약

조직의 최신 HR 데이터를 참가자 위험 관리 솔루션과 같은 도구로 사용할 수 있도록 하려면 하루에 한 번과 같이 반복 하 여 스크립트를 자동으로 실행 하도록 예약 하는 것이 좋습니다. 또한이 경우에는 동일한 일정에 따라 CSV 파일의 HR 데이터를 업데이트 해야 조직에서 탈퇴 하는 직원에 대 한 최신 정보가 포함 됩니다. HR 커넥터가 참가자 위험 관리 솔루션에서 사용할 수 있도록 최신 HR 데이터를 업로드 하는 것이 목표입니다.

Windows의 작업 스케줄러 응용 프로그램에서 매일 자동으로 스크립트를 실행할 수 있습니다.

1. 로컬 컴퓨터에서 Windows **시작** 단추를 클릭 한 다음 **작업 스케줄러**를 입력 합니다.

2. **작업 스케줄러** 앱을 클릭 하 여 엽니다.

3. **작업** 섹션에서 **작업 만들기**를 클릭 합니다.

4. **일반** 탭에서 예약 된 작업에 대 한 설명이 포함 된 이름을 입력 합니다. 예를 들어 **HR 커넥터 스크립트**를 예로 들 있습니다. 선택적 설명도 추가할 수 있습니다.

5. **보안 옵션**에서 다음을 수행 합니다.

   a. 컴퓨터에 로그온 하거나 로그온 할 때 스크립트를 실행 하는 경우에만 실행할지를 결정 합니다.

   b. **가장 높은 권한으로 실행** 확인란이 선택 되어 있는지 확인 합니다.

6. **트리거** 탭을 선택 하 고 **새로 만들기**를 클릭 한 후 다음 작업을 수행 합니다.

   a. **설정**에서 **매일** 옵션을 선택한 다음 스크립트를 처음 실행할 날짜와 시간을 선택 합니다. 스크립트는 매일 같은 시간에 지정 됩니다.

   b. **고급 설정**에서 **사용** 확인란이 선택 되어 있는지 확인 합니다.

   c. **확인을**클릭 합니다.

7. **작업** 탭을 선택 하 고 **새로 만들기**를 클릭 한 후 다음 작업을 수행 합니다.

   ![HR 커넥터 스크립트에 대해 새로 예약 된 작업을 만들기 위한 작업 설정](../media/HRConnectorScheduleTask1.png)

   a. **작업** 드롭다운 목록에서 **프로그램 시작** 을 선택 했는지 확인 합니다.

   b. **프로그램/스크립트** 상자에서 **찾아보기를**클릭 하 고 다음 위치로 이동 하 여 경로를 상자에 표시 하도록 선택 `C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe` 합니다.

   c. **인수 추가 (선택 사항)** 상자에 4 단계에서 실행 한 것과 동일한 스크립트 명령을 붙여 넣습니다. 예를 들어 `.\HRConnector.ps1 -tenantId "d5723623-11cf-4e2e-b5a5-01d1506273g9" -appId "c12823b7-b55a-4989-faba-02de41bb97c3" -appSecret "MNubVGbcQDkGCnn"  -jobId "e081f4f4-3831-48d6-7bb3-fcfab1581458" -csvFilePath "C:\Users\contosoadmin\Desktop\Data\employee_termination_data.csv"`

   d. 시작 위치 **(선택 사항)** 상자에 4 단계에서 실행 한 스크립트의 폴더를 붙여 넣습니다. 예를 들면 `C:\Users\contosoadmin\Desktop\Scripts`와 같습니다.

   e. **확인** 을 클릭 하 여 새 작업에 대 한 설정을 저장 합니다.

8. **작업 만들기** 창에서 **확인** 을 클릭 하 여 예약 된 작업을 저장 합니다. 사용자 계정 자격 증명을 입력 하 라는 메시지가 표시 될 수 있습니다.

   새 작업이 작업 스케줄러 라이브러리에 표시 됩니다.

   ![새 작업이 작업 스케줄러 라이브러리에 표시 됨](../media/HRConnectorTaskSchedulerLibrary.png)

   스크립트를 마지막으로 실행 했을 때와 실행할 예약 된 다음 시간을 표시 합니다. 작업을 두 번 클릭 하 여 편집할 수 있습니다.

   또한 준수 센터의 해당 HR 커넥터에 대 한 플라이 아웃 페이지에서 스크립트를 마지막으로 실행 한 시간을 확인할 수 있습니다.

## <a name="existing-hr-connectors"></a>기존 HR 커넥터

2020 년 7 월 20 일에 HR 커넥터에서 지 원하는 추가 시나리오가 출시 되었습니다. 이 문서에서 이전에 설명한 HR 시나리오는 다음과 같습니다. 이 날짜 이전에 만들어진 HR 커넥터는 Employee resignation 시나리오를 지원 합니다. 2020 년 7 월 20 일 이전에 HR 커넥터를 만든 경우 HR 데이터를 Microsoft 클라우드로 마이그레이션하기 위해이를 마이그레이션 했습니다. 이 기능을 유지 관리 하기 위해 별도의 작업을 수행할 필요가 없습니다. 중단 없이 커넥터를 계속 사용할 수 있습니다.

추가 HR 시나리오를 구현 하려는 경우에는 새 HR 커넥터를 만들고 릴리스된 추가 HR 시나리오에 맞게 구성 하십시오. 또한 추가 HR 시나리오를 지원 하기 위한 데이터를 포함 하는 하나 이상의 새 CSV 파일을 만들어야 합니다. 새 HR 커넥터를 만든 후에는 추가 HR 시나리오에 대 한 데이터와 함께 새 커넥터의 작업 ID와 CSV 파일을 사용 하 여 스크립트를 실행 합니다.
