---
title: 독립 실행형 EOP에서 관리자 감사 로그 보기
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
ms.assetid: 003d7a74-3e16-4453-ae0c-9dbae51f66d1
description: 관리자는 독립 실행형 EOP (Exchange Online Protection)에서 관리자 감사 로그를 보고 검색 하는 방법을 확인할 수 있습니다.
ms.openlocfilehash: e8c12f622c4dc382b11d03424e45c33e3afe3cbf
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44613327"
---
# <a name="view-the-admin-audit-log-in-standalone-eop"></a>독립 실행형 EOP에서 관리자 감사 로그 보기

Exchange Online 사서함이 없는 독립 실행형 EOP (Exchange Online Protection) 조직에서는 EAC (Exchange 관리 센터) 또는 독립 실행형 EOP PowerShell을 사용 하 여 관리자 감사 로그의 항목을 검색 하 고 볼 수 있습니다.

관리자 감사 로그에는 관리 권한이 할당 된 관리자 및 사용자가 수행 하는 독립 실행형 EOP PowerShell cmdlet을 기반으로 하는 특정 작업이 기록 됩니다. 관리자 감사 로그의 항목은 실행 된 cmdlet, 사용 된 매개 변수, cmdlet을 실행 한 사용자 및 영향을 받은 개체에 대 한 정보를 제공 합니다.

> [!NOTE]
> <ul><li>관리자 감사 로깅은 기본적으로 사용 하도록 설정 되어 있으며 사용 하지 않도록 설정할 수 없습니다.</li><li>관리자 감사 로그는 동사 **Get**, **Search**또는 **Test**로 시작 하는 cmdlet을 기반으로 작업을 기록 하지 않습니다.</li><li>감사 로그 항목은 90 일 동안 유지 됩니다. 항목이 90 일 보다 오래 된 경우 삭제 됩니다.</li></ul>

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용

- Exchange 관리 센터를 열려면 [독립 실행형 EOP에서 exchange 관리 센터](exchange-admin-center-in-exchange-online-protection-eop.md)를 참조 하세요.

- 독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.

- 이 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다. 특히 ComplianceManagement, OrganizationManagement (global admins) 및 SecurityAdministrator 역할 그룹에 할당 되는 감사 로그 또는 보기 전용 감사 로그 역할이 기본적으로 필요 합니다. 자세한 내용은 [권한 독립 실행형 EOP의 사용 권한을](feature-permissions-in-eop.md) 참조 하 고 [EAC를 사용 하 여 역할 그룹의 구성원 목록을 수정](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)합니다.

- 이 항목의 절차에 적용할 수 있는 바로 가기 키에 대 한 자세한 내용은 [Exchange Online에서 exchange 관리 센터에 대 한 바로 가기 키](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)를 참조 하십시오.

> [!TIP]
> 문제가 있습니까? [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) 포럼에서 도움을 요청 하세요.

## <a name="use-the-eac-to-view-the-admin-audit-log"></a>EAC를 사용 하 여 관리자 감사 로그 보기

1. EAC에서 **규정 준수 관리** \> **감사**로 이동한 다음 **관리자 감사 로그 보고서 실행**을 선택 합니다.

2. **관리자 역할 그룹에 대 한 변경 내용 검색** 페이지에서 **시작 날짜** 와 **끝 날짜** (기본 범위는 2 주 전)를 선택 하 고 **검색**을 선택 합니다. 다음 정보를 사용 하 여 지정 된 기간 동안 변경 된 모든 구성 내용을 표시 하 고 정렬할 수 있습니다.

   - **날짜**: 구성을 변경한 날짜와 시간입니다. 날짜와 시간은 UTC(협정 세계시) 형식으로 저장됩니다.

   - **Cmdlet**: 구성을 변경 하는 데 사용 된 cmdlet의 이름입니다.

   - **User**: 구성을 변경한 사용자의 사용자 계정 이름입니다.

     여러 페이지에 항목이 5,000개까지 표시됩니다. 결과의 범위를 좁혀야 하는 경우 날짜 범위를 더 좁게 지정하세요. 개별 검색 결과를 선택하면 세부 정보 창에 다음 추가 정보가 표시됩니다.

   - **수정한 개체**: cmdlet에 의해 수정 된 개체입니다.

   - **Parameters (매개 변수: 값)**: 사용 된 cmdlet 매개 변수 및 매개 변수와 함께 지정 된 값

3. 특정 감사 로그 항목을 인쇄하려면 세부 정보 창의 **인쇄** 단추를 선택합니다.

## <a name="use-standalone-eop-powershell-to-view-the-admin-audit-log"></a>독립 실행형 EOP PowerShell을 사용 하 여 관리자 감사 로그 보기

독립 실행형 EOP PowerShell을 사용 하 여 지정한 기준을 충족 하는 감사 로그 항목을 검색할 수 있습니다. 다음 구문을 사용합니다.

```PowerShell
Search-AdminAuditLog [-Cmdlets <Cmdlet1,Cmdlet2,...CmdletN>] [-Parameters <Parameter1,Parameter2,...ParameterN>] [-StartDate <UTCDateTime>] [-EndDate <UTCDateTime>] [-UserIds <"User1","User2",..."UserN">] [-ObjectIds <"Object1","Object2",..."ObjectN">] [-IsSuccess <$true | $false>]
```

**참고:**

- _Parameters_ 매개 변수만 _cmdlet_ 매개 변수와 함께 사용할 수 있습니다.

- _ObjectIds_ 매개 변수는 cmdlet에 의해 수정 된 개체를 기준으로 결과를 필터링 합니다. 유효한 값은 감사 로그에서 개체가 표시 되는 방식에 따라 달라 집니다. 예시:

  - 이름
  - 정식 고유 이름 (예: contoso.com/Users/Akia Al-Zuhairi)

  이 cmdlet에서는 다른 필터링 매개 변수를 사용 하 여 결과의 범위를 좁히고 관심이 있는 개체의 유형을 식별 해야 합니다.

- _UserIds_ 매개 변수는 변경 작업을 수행한 사용자 (cmdlet을 실행 한 사람) 별로 결과를 필터링 합니다.

- 날짜/시간 값을 표준 시간대 없이 지정 하면 _date 및_ _EndDate_ 매개 변수의 경우 값은 utc (협정 세계시)를 사용 합니다. 이 매개 변수에 대한 날짜/시간값을 지정하려면 다음 옵션 중 하나를 사용하십시오.

  - UTC로 날짜/시간 값 지정. 예: "2016-05-06 14:30:00z"

  - 날짜/시간 값을 현지 표준 시간대의 날짜/시간을 UTC로 변환 하는 수식으로 지정 합니다 (예:) `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()` . 자세한 내용은 [Get-Date](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date)를 참조하세요.

- 이 cmdlet은 기본적으로 최대 1000 개의 로그 항목을 반환 합니다. _Resultsize_ 매개 변수를 사용 하 여 최대 25만 개의 로그 항목을 지정할 수 있습니다. 또는 값을 사용 `Unlimited` 하 여 모든 항목을 반환 합니다.

이 예에서는 다음 기준을 사용하여 모든 감사 로그 항목을 검색합니다.

- **시작 날짜**: 8 월 4 일, 2019
- **종료 날짜**: 2019 년 10 월 3 일
- **Cmdlet**: 업데이트-RoleGroupMember

```PowerShell
Search-AdminAuditLog -Cmdlets Update-RoleGroupMember -StartDate (Get-Date "08/04/2019").ToUniversalTime() -EndDate (Get-Date "10/03/2019").ToUniversalTime()
```

구문과 매개 변수에 대한 자세한 내용은 [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog)를 참조하십시오.

### <a name="view-details-of-audit-log-entries"></a>감사 로그 항목의 상세 정보 보기

**Search-adminauditlog** cmdlet은이 항목의 뒷부분에 나오는 [감사 로그 내용](#audit-log-contents) 섹션에 설명 된 필드를 반환 합니다. Cmdlet에 의해 반환 된 필드 중 두 개의 필드, **Cmdletparameters** 및 **ModifiedProperties**에는 기본적으로 반환 되지 않는 추가 정보가 포함 됩니다.

**CmdletParameters** 및 **ModifiedProperties** 필드의 콘텐츠를 보려면 다음 단계를 수행합니다.

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

## <a name="audit-log-contents"></a>감사 로그 내용

각 감사 로그 항목에는 다음 표에 설명된 정보가 포함되어 있습니다. 감사 로그에는 하나 이상의 감사 로그 항목이 포함되어 있습니다.

|||
|---|---|
|**필드**|**설명**|
|`RunspaceId`|이 필드는 EOP에서 내부적으로 사용 합니다.|
|`ObjectModified`|이 필드에는 필드에 지정 된 cmdlet에 의해 수정 된 개체가 포함 `CmdletName` 됩니다.|
|`CmdletName`|이 필드에는 필드에 사용자가 실행 한 cmdlet의 이름이 포함 `Caller` 됩니다.|
|`CmdletParameters`|이 필드에는 필드의 cmdlet을 실행할 때 지정한 매개 변수가 포함 `CmdletName` 됩니다. 또한 이 매개 변수로 지정된 값(있는 경우)은 이 필드에 저장되지만 기본 출력에서 표시되지 않습니다.|
|`ModifiedProperties`|이 필드에는 필드에서 개체에 대해 수정 된 속성이 포함 되어 있습니다 `ObjectModified` . 또한 저장된 속성의 이전 값 및 새 값은 이 필드에 저장되지만 기본 출력에서 표시되지 않습니다.|
|`Caller`|이 필드에는 필드에서 cmdlet을 실행 한 사용자의 사용자 계정이 포함 `CmdletName` 됩니다.|
|`ExternalAccess`|이 필드는 EOP에서 내부적으로 사용 합니다.|
|`Succeeded`|이 필드는 필드의 cmdlet이 성공적으로 실행 되었는지 여부를 지정 합니다 `CmdletName` . 값은 `True` 또는 `False` 입니다.|
|`Error`|이 필드에는 필드의 cmdlet이 성공적으로 완료 되지 않은 경우 생성 되는 오류 메시지가 포함 됩니다 `CmdletName` .|
|`RunDate`|이 필드에는 필드의 cmdlet을 실행 한 날짜와 시간이 포함 `CmdletName` 됩니다. 날짜와 시간은 UTC(협정 세계시) 형식으로 저장됩니다.|
|`OriginatingServer`|이 필드는 필드에 지정 된 cmdlet이 실행 된 서버를 나타냅니다 `CmdletName` .|
|`ClientIP`|이 필드는 EOP에서 내부적으로 사용 합니다.|
|`SessionId`|이 필드는 EOP에서 내부적으로 사용 합니다.|
|`AppId`|이 필드는 EOP에서 내부적으로 사용 합니다.|
|`ClientAppId`|이 필드는 EOP에서 내부적으로 사용 합니다.|
|`Identity`|이 필드는 EOP에서 내부적으로 사용 합니다.|
|`IsValid`|이 필드는 EOP에서 내부적으로 사용 합니다.|
|`ObjectState`|이 필드는 EOP에서 내부적으로 사용 합니다.|
|
