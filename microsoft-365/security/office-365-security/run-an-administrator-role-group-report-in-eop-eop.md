---
title: 독립 실행형 EOP에서 관리자 역할 그룹 보고서 실행
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
ms.custom:
- seo-marvel-apr2020
description: 관리자는 독립 실행형 EOP (Exchange Online Protection)에서 administrator 역할 그룹 보고서를 실행 하는 방법을 확인할 수 있습니다. 관리자가 관리 역할 그룹에서 구성원을 추가 하거나 제거할 때이 보고서가 기록 되며, EOP 각 항목에 대해 로그를 기록 합니다.
ms.openlocfilehash: 0c504460657a153aad7d3dd065c81007a68ba916
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/05/2020
ms.locfileid: "44587367"
---
# <a name="run-an-administrator-role-group-report-in-standalone-eop"></a>독립 실행형 EOP에서 관리자 역할 그룹 보고서 실행

Exchange Online 사서함이 없는 독립 실행형 EOP (Exchange Online Protection) 조직에서는 관리자가 관리 역할 그룹에 구성원을 추가 하거나 제거할 때 각 항목을 기록 합니다. 독립 실행형 EOP의 역할 그룹에 대 한 자세한 내용은 [Permissions in 독립 실행형 EOP](feature-permissions-in-eop.md)을 참조 하십시오.

EAC (Exchange 관리 센터)에서 관리자 역할 그룹 보고서를 실행 하면 항목이 검색 결과로 표시 되 고 영향을 받는 역할 그룹, 역할 그룹 구성원 자격을 변경한 사용자 및 멤버 자격 업데이트를 포함 합니다. 이 보고서를 사용하여 조직의 사용자에게 할당된 관리 권한의 변경을 모니터링할 수 있습니다.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용

- Exchange 관리 센터를 열려면 [독립 실행형 EOP에서 exchange 관리 센터](exchange-admin-center-in-exchange-online-protection-eop.md)를 참조 하세요.

- 이 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다. 특히 ComplianceManagement, OrganizationManagement (global admins) 및 SecurityAdministrator 역할 그룹에 할당 되는 감사 로그 또는 보기 전용 감사 로그 역할이 기본적으로 필요 합니다. 자세한 내용은 [권한 독립 실행형 EOP의 사용 권한을](feature-permissions-in-eop.md) 참조 하 고 [EAC를 사용 하 여 역할 그룹의 구성원 목록을 수정](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)합니다.

- 이 항목의 절차에 적용할 수 있는 바로 가기 키에 대 한 자세한 내용은 [Exchange Online에서 exchange 관리 센터에 대 한 바로 가기 키](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)를 참조 하십시오.

> [!TIP]
> 문제가 있습니까? [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) 포럼에서 도움을 요청 하세요.

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a>EAC를 사용하여 관리자 역할 그룹 보고서 실행

관리자 역할 그룹 보고서를 실행 하 여 특정 시간대 내에 조직의 관리 역할 그룹에 대 한 변경 내용을 확인 합니다.

1. EAC에서 **규정 준수 관리** \> **감사**로 이동한 다음 **관리자 역할 그룹 보고서 실행**을 선택 합니다.

2. **관리자 역할 그룹에 대 한 변경 내용 검색** 페이지에서 다음 설정을 구성 합니다.

   - **시작 날짜** 및 **종료 날짜**: 날짜 범위를 입력 합니다. 기본적으로 보고서는 지난 2주 동안의 관리자 역할 그룹 변경 내용을 검색합니다.

   - **역할 그룹 선택**: 기본적으로 모든 역할 그룹을 검색 합니다. 특정 역할 그룹별로 결과를 필터링 하려면 **역할 그룹 선택을**클릭 합니다. 대화 상자가 나타나면 역할 그룹을 선택 하 고 **추가 >** 를 클릭 합니다. 필요한 횟수 만큼이 단계를 반복한 다음, 완료 되 면 **확인을** 클릭 합니다.

3. 작업이 완료 되 면 **검색**을 클릭 합니다.

지정한 조건을 사용하여 찾은 변경 내용은 결과 창에 표시됩니다. 검색 결과에서 역할 그룹을 클릭하여 세부 정보 창에서 변경 내용을 확인합니다.

## <a name="how-do-you-know-this-worked"></a>작동 여부는 어떻게 확인하나요?

관리자 역할 그룹 보고서를 성공적으로 실행한 경우 날짜 범위 내에서 변경된 역할 그룹은 검색 결과 창에 표시됩니다. 결과가 표시되지 않으면 지정된 날짜 범위 내에서 역할 그룹이 변경되지 않은 것입니다. 표시할 결과가 있다고 생각되면 날짜 범위를 변경한 다음 보고서를 다시 실행하십시오.

## <a name="monitor-changes-to-role-group-membership"></a>역할 그룹 구성원의 변경 모니터링

구성원이 역할 그룹에서 추가되거나 제거되면 세부 정보 창에 표시되는 검색 결과에서 역할 그룹 구성원이 업데이트되었음이 표시되고 현재 구성원이 표시됩니다. 이 결과에서는 추가되거나 제거된 사용자가 명시적으로 나타나지 않습니다.

사용자가 추가되었거나 제거되었는지 확인하려면 보고서에서 두 가지 항목을 비교해야 합니다. 예를 들어 **HelpDesk** 역할 그룹에 대한 다음 로그 항목을 살펴보겠습니다.

> 오후 1/27/2018 4:43 <br> 관리자 <br> 업데이트된 구성원: Administrator;annb,florencef;pilarp <br> 오전 2/06/2018 10:09 <br> 관리자 <br> 업데이트된 구성원: Administrator;annb;florencef;pilarp;tonip <br> 오후 2/19/2018 2:12 <br> 관리자 <br> 업데이트된 구성원: Administrator;annb;florencef;tonip

이 예에서 관리자 사용자 계정은 다음과 같이 변경되었습니다.

- 2/06/2018에는 사용자 tonip가 추가 되었습니다.

- 2/19/2018에서는 사용자가 pilarp를 제거 했습니다.

## <a name="use-standalone-exchange-online-powershell-to-search-for-audit-log-entries"></a>독립 실행형 Exchange Online PowerShell을 사용 하 여 감사 로그 항목 검색

Exchange Online PowerShell을 사용 하 여 지정한 기준을 충족 하는 감사 로그 항목을 검색할 수 있습니다. 검색 조건 목록은 [검색-search-adminauditlog 검색 조건을](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet)참조 하십시오. 이 절차에서는 **search-adminauditlog** cmdlet을 사용 하 고 Exchange Online PowerShell에 검색 결과를 표시 합니다. 이 cmdlet은 **New-AdminAuditLogSearch** cmdlet 또는 EAC 감사 보고 보고서에 정의된 제한을 초과하는 결과를 반환해야 할 경우에 사용할 수 있습니다.

지정한 기준을 충족하는 감사 로그를 검색하려면 다음 구문을 사용합니다.

```PowerShell
Search-AdminAuditLog - Cmdlets <cmdlet 1, cmdlet 2, ...> -Parameters <parameter 1, parameter 2, ...> -StartDate <start date> -EndDate <end date> -UserIds <user IDs> -ObjectIds <object IDs> -IsSuccess <$True | $False >
```

> [!NOTE]
> **Search-AdminAuditLog** cmdlet은 기본적으로 최대 1,000개의 로그 항목을 반환합니다. _Resultsize_ 매개 변수를 사용 하 여 최대 25만 개의 로그 항목을 지정할 수 있습니다. 또는 값을 사용 `Unlimited` 하 여 모든 항목을 반환 합니다.

이 예에서는 다음 기준을 사용하여 모든 감사 로그 항목을 검색합니다.

- **시작 날짜**: 08/04/2018

- **종료 날짜**: 10/03/2018

- **사용자 id**: davids, chrisd, kima

- **Cmdlet**: **Set-Mailbox**

- **매개 변수**: _ProhibitSendQuota_, _ProhibitSendReceiveQuota_, _IssueWarningQuota_, _maxsendsize_, _MaxReceiveSize_

```PowerShell
Search-AdminAuditLog -Cmdlets Set-Mailbox -Parameters ProhibitSendQuota,ProhibitSendReceiveQuota,IssueWarningQuota,MaxSendSize,MaxReceiveSize -StartDate 08/04/2018 -EndDate 10/03/2018 -UserIds davids,chrisd,kima
```

이 예에서는 특정 사서함에 대한 변경 내용을 검색합니다. 문제를 해결하거나 조사에 필요한 정보를 제공해야 할 경우에 유용합니다. 다음과 같은 기준이 사용됩니다.

- **시작 날짜**: 05/01/2018

- **종료 날짜**: 10/03/2018

- **개체 ID**: contoso.com/Users/DavidS

```PowerShell
Search-AdminAuditLog -StartDate 05/01/2018 -EndDate 10/03/2018 -ObjectID contoso.com/Users/DavidS
```

검색에서 많은 로그 항목이 반환 되는 경우이 항목의 뒷부분에 나오는 사용 중인 **Exchange Online PowerShell을 사용 하 여 감사 로그 항목을 검색 하 고 결과를 받는 사람에 게 전송** 하는 것이 좋습니다. 해당 섹션의 절차는 지정한 받는 사람에게 XML 파일을 전자 메일 첨부 파일로 전송하므로 관심 있는 데이터를 더 쉽게 추출할 수 있습니다.

구문과 매개 변수에 대한 자세한 내용은 [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog)를 참조하십시오.

### <a name="view-details-of-audit-log-entries"></a>감사 로그 항목의 상세 정보 보기

**Search-adminauditlog** Cmdlet은 [감사 로그 내용](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents)에 설명 된 필드를 반환 합니다. cmdlet에 의해 반환된 필드 중에서 **CmdletParameters** 및 **ModifiedProperties** 의 두 필드에는 기본적으로 볼 수 없는 추가 정보가 포함됩니다.

**CmdletParameters** 및 **ModifiedProperties** 필드의 콘텐츠를 보려면 다음 단계를 수행합니다. 또는 **Exchange Online PowerShell 사용의 절차를 사용 하 여 감사 로그 항목을 검색 하 고이 항목의 뒷부분에 있는 받는 사람에 게 결과를 보내** XML 파일을 만들 수 있습니다.

이 절차에서는 다음 개념을 사용합니다.

- [about_Arrays](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_arrays)

- [about_Variables](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_variables)

1. 검색할 기준을 정하고 **Search-AdminAuditLog** cmdlet을 실행한 후 다음 명령을 사용하여 변수에 결과를 저장합니다.

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. 각 감사 로그 항목은 변수에 배열 요소로 저장 됩니다 `$Results` . 배열 요소 인덱스를 지정하여 배열 요소를 선택할 수 있습니다. 배열 요소 인덱스는 첫 번째 배열 요소에 대해 0에서 시작합니다. 예를 들어, 인덱스가 4인 5번째 배열 요소를 검색하려면 다음 명령을 사용합니다.

    ```PowerShell
    $Results[4]
    ```

3. 이전 명령이 배열 요소 4에 저장된 로그 항목을 반환합니다. 이 로그 항목의 **CmdletParameters** 및 **ModifiedProperties** 필드의 콘텐츠를 보려면 다음 명령을 사용합니다.

    ```PowerShell
    $Results[4].CmdletParameters
    $Results[4].ModifiedProperties
    ```

4. 다른 로그 항목의 **CmdletParameters** 또는 **ModifiedParameters** 필드의 콘텐츠를 보려면 배열 요소 인덱스를 변경합니다.