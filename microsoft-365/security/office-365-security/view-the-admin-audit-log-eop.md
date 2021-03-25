---
title: 독립 실행형 EOP에서 관리자 감사 로그 보기
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 003d7a74-3e16-4453-ae0c-9dbae51f66d1
description: 관리자는 독립 실행형 EOP(Exchange Online Protection)에서 관리자 감사 로그를 보고 검색하는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5ed1d1eb121c06e6f5727e8782ba1d8bc8d23a99
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205042"
---
# <a name="view-the-admin-audit-log-in-standalone-eop"></a>독립 실행형 EOP에서 관리자 감사 로그 보기

**적용 대상**
- [Exchange Online Protection 독립 실행형](exchange-online-protection-overview.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서는 EAC(Exchange 관리 센터) 또는 독립 실행형 EOP PowerShell을 사용하여 관리자 감사 로그에서 항목을 검색하고 볼 수 있습니다.

관리자 감사 로그는 독립 실행형 EOP PowerShell cmdlet을 기반으로 관리 권한이 할당된 관리자 및 사용자가 수행한 특정 작업을 기록합니다. 관리자 감사 로그의 항목은 실행된 cmdlet, 사용된 매개 변수, cmdlet을 실행한 사용자 및 영향을 받은 개체에 대한 정보를 제공합니다.

> [!NOTE]
>
> - 관리자 감사 로깅은 기본적으로 사용하도록 설정되어 있으며 사용하지 않도록 설정할 수 없습니다.
>
> - 관리자 감사 로그는 **Get,** **Search** 또는 Test 동사로 시작하는 cmdlet에 따라 작업을 기록하지 **않습니다.**
>
> - 감사 로그 항목은 90일 동안 보관됩니다. 항목이 90일보다 오래된 경우 삭제됩니다.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용

- Exchange 관리 센터를 열하려면 독립 실행형 [EOP의 Exchange 관리 센터를 참조하세요.](exchange-admin-center-in-exchange-online-protection-eop.md)

- 독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.

- 이 문서의 절차를 수행하려면 먼저 Exchange Online Protection에서 사용 권한을 할당해야 합니다. 특히 조직 관리, 준수 관리 및 보안 관리자 역할 그룹에 기본적으로 할당되는 감사 로그 또는 보기 전용 감사 로그 역할이 필요합니다.    자세한 내용은 독립 실행형 [EOP의](feature-permissions-in-eop.md) 사용 권한 및 EAC를 사용하여 역할 그룹의 구성원 목록 [수정을 참조하세요.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- 이 문서의 절차에 적용할 수 있는 바로 가기 키에 대한 자세한 내용은 Exchange Online의 Exchange 관리 센터에 대한 바로 가기 키를 [참조하세요.](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)

> [!TIP]
> 문제가 있나요? [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) 포럼에서 도움을 요청하세요.

## <a name="use-the-eac-to-view-the-admin-audit-log"></a>EAC를 사용하여 관리자 감사 로그 보기

1. EAC에서 준수 **관리** 감사로 이동한 다음 관리자 감사 로그 보고서 실행 \>  **을 선택 합니다.**

2. 관리자 **역할** 그룹 변경 내용 검색 페이지가 열리면  시작 날짜 및 종료 날짜(기본 범위는 지난 2주)를 선택한 다음 검색을 **선택합니다.**  지정된 기간 동안 변경된 모든 구성이 표시되고 다음 정보를 사용하여 정렬할 수 있습니다.

   - **날짜:** 구성이 변경된 날짜 및 시간입니다. 날짜와 시간은 UTC(협정 세계시) 형식으로 저장됩니다.

   - **cmdlet:** 구성을 변경하는 데 사용된 cmdlet의 이름입니다.

   - **사용자:** 구성을 변경한 사용자의 사용자 계정 이름입니다.

     여러 페이지에 항목이 5,000개까지 표시됩니다. 결과의 범위를 좁혀야 하는 경우 날짜 범위를 더 좁게 지정하세요. 개별 검색 결과를 선택하면 세부 정보 창에 다음 추가 정보가 표시됩니다.

   - **수정된 개체:** cmdlet에서 수정한 개체입니다.

   - **Parameters (Parameter:Value)**: 사용된 cmdlet 매개 변수 및 매개 변수로 지정된 모든 값입니다.

3. 특정 감사 로그 항목을 인쇄하려면 세부 정보 창의 **인쇄** 단추를 선택합니다.

## <a name="use-standalone-eop-powershell-to-view-the-admin-audit-log"></a>독립 실행형 EOP PowerShell을 사용하여 관리자 감사 로그 보기

독립 실행형 EOP PowerShell을 사용하여 지정한 기준을 충족하는 감사 로그 항목을 검색할 수 있습니다. 다음 구문을 사용합니다.

```PowerShell
Search-AdminAuditLog [-Cmdlets <Cmdlet1,Cmdlet2,...CmdletN>] [-Parameters <Parameter1,Parameter2,...ParameterN>] [-StartDate <UTCDateTime>] [-EndDate <UTCDateTime>] [-UserIds <"User1","User2",..."UserN">] [-ObjectIds <"Object1","Object2",..."ObjectN">] [-IsSuccess <$true | $false>]
```

**참고:**

- _Parameters_ 매개 변수는 _Cmdlets 매개 변수와 함께만 사용할 수_ 있습니다.

- _ObjectIds 매개_ 변수는 cmdlet에서 수정한 개체에 따라 결과를 필터합니다. 유효한 값은 개체가 감사 로그에 어떻게 나타내는지 여부에 따라 다를 수 있습니다. 예를 들면 다음과 같습니다.

  - 이름
  - 정식 고유 이름(예: contoso.com/Users/Akia Al-Zuhairi)

  이 cmdlet에서 다른 필터링 매개 변수를 사용하여 결과 범위를 좁히고 관심 있는 개체 유형을 식별해야 할 수 있습니다.

- _UserIds 매개_ 변수는 변경한 사용자(cmdlet을 런타임)에 따라 결과를 필터합니다.

- _StartDate_ 및 _EndDate_ 매개 변수의 경우 표준 시간대 없이 날짜/시간 값을 지정하는 경우 값은 UTC(협정 세계시)입니다. 이 매개 변수에 대한 날짜/시간값을 지정하려면 다음 옵션 중 하나를 사용하십시오.

  - UTC로 날짜/시간 값 지정. 예: "2016-05-06 14:30:00z"

  - 날짜/시간 값을 현지 표준 시간대의 날짜/시간을 UTC로 변환하는 수식으로 지정합니다(예: `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()` ). 자세한 내용은 [Get-Date](/powershell/module/microsoft.powershell.utility/get-date)를 참조하세요.

- 이 cmdlet은 기본적으로 최대 1,000개 로그 항목을 반환합니다. _ResultSize_ 매개 변수를 사용하여 최대 250,000개 로그 항목을 지정할 수 있습니다. 또는 값을 사용하여 모든 `Unlimited` 항목을 반환합니다.

이 예에서는 다음 기준을 사용하여 모든 감사 로그 항목을 검색합니다.

- **시작 날짜:** 2019년 8월 4일
- **종료 날짜:** 2019년 10월 3일
- **cmdlet**: Update-RoleGroupMember

```PowerShell
Search-AdminAuditLog -Cmdlets Update-RoleGroupMember -StartDate (Get-Date "08/04/2019").ToUniversalTime() -EndDate (Get-Date "10/03/2019").ToUniversalTime()
```

구문과 매개 변수에 대한 자세한 내용은 [Search-AdminAuditLog](/powershell/module/exchange/search-adminauditlog)를 참조하십시오.

### <a name="view-details-of-audit-log-entries"></a>감사 로그 항목의 상세 정보 보기

**Search-AdminAuditLog** cmdlet은 이 문서 부분의 감사 로그 콘텐츠 섹션에 설명된 필드를 반환합니다. [](#audit-log-contents) cmdlet에서 반환되는 필드 중 **CmdletParameters** 및 **ModifiedProperties의** 두 필드에는 기본적으로 반환되지 않는 추가 정보가 포함되어 있습니다.

**CmdletParameters** 및 **ModifiedProperties** 필드의 콘텐츠를 보려면 다음 단계를 수행합니다.

1. 검색할 기준을 정하고 **Search-AdminAuditLog** cmdlet을 실행한 후 다음 명령을 사용하여 변수에 결과를 저장합니다.

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. 각 감사 로그 항목은 변수 에 배열 요소로 `$Results` 저장됩니다. 배열 요소 인덱스를 지정하여 배열 요소를 선택할 수 있습니다. 배열 요소 인덱스는 첫 번째 배열 요소에 대해 0에서 시작합니다. 예를 들어, 인덱스가 4인 5번째 배열 요소를 검색하려면 다음 명령을 사용합니다.

    ```PowerShell
    $Results[4]
    ```

3. 이전 명령이 배열 요소 4에 저장된 로그 항목을 반환합니다. 이 로그 항목의 **CmdletParameters** 및 **ModifiedProperties** 필드의 콘텐츠를 보려면 다음 명령을 사용합니다.

    ```PowerShell
    $Results[4].CmdletParameters
    $Results[4].ModifiedProperties
    ```

4. 다른 로그 항목의 **CmdletParameters** 또는 **ModifiedParameters** 필드의 콘텐츠를 보려면 배열 요소 인덱스를 변경합니다.

## <a name="audit-log-contents"></a>감사 로그 콘텐츠

각 감사 로그 항목에는 다음 표에 설명된 정보가 포함되어 있습니다. 감사 로그에는 하나 이상의 감사 로그 항목이 포함되어 있습니다.

****

|필드|설명|
|---|---|
|`RunspaceId`|이 필드는 EOP에서 내부적으로 사용됩니다.|
|`ObjectModified`|이 필드에는 필드에 지정된 cmdlet에 의해 수정된 개체가 `CmdletName` 들어 있습니다.|
|`CmdletName`|이 필드에는 필드에서 사용자가 실행한 cmdlet의 이름이 `Caller` 들어 있습니다.|
|`CmdletParameters`|이 필드에는 필드의 cmdlet이 실행될 때 지정된 매개 `CmdletName` 변수가 포함됩니다. 또한 이 매개 변수로 지정된 값(있는 경우)은 이 필드에 저장되지만 기본 출력에서 표시되지 않습니다.|
|`ModifiedProperties`|이 필드에는 필드의 개체에서 수정된 속성이 `ObjectModified` 들어 있습니다. 또한 저장된 속성의 이전 값 및 새 값은 이 필드에 저장되지만 기본 출력에서 표시되지 않습니다.|
|`Caller`|이 필드에는 필드에서 cmdlet을런 사용자의 사용자 계정이 `CmdletName` 포함되어 있습니다.|
|`ExternalAccess`|이 필드는 EOP에서 내부적으로 사용됩니다.|
|`Succeeded`|이 필드는 필드의 cmdlet이 성공적으로 `CmdletName` 완료된 것인지 여부를 지정합니다. 값은 또는 `True` `False` 입니다.|
|`Error`|이 필드에는 필드의 cmdlet이 성공적으로 완료되지 못한 경우 생성되는 오류 `CmdletName` 메시지가 포함되어 있습니다.|
|`RunDate`|이 필드에는 필드의 cmdlet이 실행된 날짜와 `CmdletName` 시간이 포함되어 있습니다. 날짜와 시간은 UTC(협정 세계시) 형식으로 저장됩니다.|
|`OriginatingServer`|이 필드는 필드에 지정된 cmdlet이 실행된 서버를 `CmdletName` 나타냅니다.|
|`ClientIP`|이 필드는 EOP에서 내부적으로 사용됩니다.|
|`SessionId`|이 필드는 EOP에서 내부적으로 사용됩니다.|
|`AppId`|이 필드는 EOP에서 내부적으로 사용됩니다.|
|`ClientAppId`|이 필드는 EOP에서 내부적으로 사용됩니다.|
|`Identity`|이 필드는 EOP에서 내부적으로 사용됩니다.|
|`IsValid`|이 필드는 EOP에서 내부적으로 사용됩니다.|
|`ObjectState`|이 필드는 EOP에서 내부적으로 사용됩니다.|
|