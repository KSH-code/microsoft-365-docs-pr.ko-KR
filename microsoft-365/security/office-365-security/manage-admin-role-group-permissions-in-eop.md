---
title: EOP에서 역할 그룹 관리
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: 관리자는 Exchange Online Protection의 EAC (Exchange 관리 센터)에서 사용 권한을 할당 하거나 제거 하는 방법을 확인할 수 있습니다.
ms.openlocfilehash: fb1e0979b77c38d852f35817e01135af888eac68
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201904"
---
# <a name="manage-role-groups-in-standalone-eop"></a>독립 실행형 EOP에서 역할 그룹 관리

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Exchange Online 사서함이 없는 독립 실행형 EOP (Exchange Online Protection) 조직에서는 EAC (Exchange 관리 센터)를 사용 하 여 역할 그룹에 사용자를 추가할 수 있습니다. 역할 그룹에 사용자를 추가 하면 특정 관리 작업을 수행할 수 있는 권한이 사용자에 게 제공 됩니다. 역할 그룹에서 사용자를 제거할 수도 있습니다.

역할 및 역할 그룹에 대 한 자세한 내용은 [Permissions in 독립 실행형 EOP](feature-permissions-in-eop.md)을 참조 하십시오.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용

- EAC (Exchange 관리 센터)를 열려면 [독립 실행형 EOP에서 exchange 관리 센터](exchange-admin-center-in-exchange-online-protection-eop.md)를 참조 하세요.

- 독립 실행형 EOP PowerShell을 열려면 [Exchange Online Protection PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조 하세요.

- 이 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다. 특히 OrganizationManagement (전역 관리자) 역할 그룹에 기본적으로 할당 되는 역할 관리 역할이 필요 합니다. 자세한 내용은 [권한 독립 실행형 EOP의 사용 권한을](feature-permissions-in-eop.md) 참조 하 고 [EAC를 사용 하 여 역할 그룹의 구성원 목록을 수정](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)합니다.

- 이 항목의 절차에 적용할 수 있는 바로 가기 키에 대 한 자세한 내용은 [Exchange Online에서 exchange 관리 센터에 대 한 바로 가기 키](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)를 참조 하십시오.

> [!TIP]
> 문제가 있나요? [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) 포럼에서 도움을 요청하세요.

## <a name="use-the-eac-to-manage-role-groups"></a>EAC를 사용 하 여 역할 그룹 관리

### <a name="use-the-eac-to-view-role-groups"></a>EAC를 사용 하 여 역할 그룹 보기

1. EAC에서 **사용 권한** \> **관리자 역할로**이동 합니다. 조직의 모든 역할 그룹이 여기에 나열됩니다.

2. 역할 그룹을 선택 합니다. 세부 정보 창에는 역할 그룹에 따라 이름, **설명**, **할당 된 역할**및 **관리 되** 는 **이름이**표시 됩니다. 편집 아이콘 **편집** 을 클릭 하 여이 정보를 볼 수도 있습니다 ![ ](../../media/ITPro-EAC-EditIcon.png) .

### <a name="use-the-eac-to-create-role-groups"></a>EAC를 사용 하 여 역할 그룹 만들기

새 역할 그룹을 만들 때는 그룹을 만드는 중 또는 이후에 모든 설정을 직접 구성할 수 있습니다. 또는 기존 역할 그룹을 복사 하 여 수정할 수도 있습니다.

1. EAC에서 **사용 권한** \> **관리자 역할로**이동한 후 다음 단계 중 하나를 수행 합니다.

   - **새 역할 그룹을 수동으로 만들기**: 추가 아이콘 **추가** 를 클릭 ![ ](../../media/ITPro-EAC-AddIcon.png) 합니다.

   - **기존 역할 그룹 복사**: 복사할 역할 그룹을 선택한 다음 복사본 복사 아이콘 **를 클릭** ![ ](../../media/ITPro-EAC-CopyIcon.png) 합니다.

2. **새 역할 그룹** 창이 나타나면 다음 설정을 구성 합니다.

    - **이름**: 역할 그룹의 고유한 이름을 입력 합니다.

    - **설명**: 역할 그룹에 대 한 설명을 입력 합니다 (선택 사항).

    - **역할**: **추가** ![ 아이콘 추가 ](../../media/ITPro-EAC-AddIcon.png) 또는ITPro-EAC-RemoveIcon.gif**제거** ![ 를 클릭 하 여 ](../../media/ITPro-EAC-RemoveIcon.gif) 역할 그룹에 할당 된 역할을 선택 하거나 수정 합니다.

    - **구성원**: **추가** ![ 아이콘 추가 ](../../media/ITPro-EAC-AddIcon.png) 또는ITPro-EAC-RemoveIcon.gif**제거** ![ 를 클릭 하 여 ](../../media/ITPro-EAC-RemoveIcon.gif) 역할 그룹 구성원을 수정 합니다.

3. 작업이 끝나면 **저장** 을 클릭 하 여 역할 그룹을 만듭니다.

### <a name="use-the-eac-to-modify-role-groups"></a>EAC를 사용 하 여 역할 그룹 수정

EAC에서 **사용 권한** \> **관리자 역할로**이동 하 여 수정 하려는 역할 그룹을 선택한 다음 편집 아이콘 **편집** 을 클릭 ![ ](../../media/ITPro-EAC-EditIcon.png) 합니다.

역할 그룹을 만들 때와 마찬가지로 역할 그룹을 수정 하는 경우에도 동일한 옵션을 사용할 수 있습니다. 다음을 수행할 수 있습니다.

- 이름 및 설명을 변경 합니다.

- 관리 역할 추가 및 제거 (역할 할당 만들기 또는 제거)

- 구성원을 추가 및 제거 합니다.

**참고**: 조직 관리와 같은 일부 역할 그룹은 그룹에서 제거할 수 있는 역할을 제한 합니다.

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a>EAC를 사용 하 여 역할 그룹의 구성원 목록 수정

1. EAC에서 **사용 권한** \> **관리자 역할로**이동 하 여 수정 하려는 역할 그룹을 선택한 다음 편집 아이콘 **편집** 을 클릭 ![ ](../../media/ITPro-EAC-EditIcon.png) 합니다.

2. 역할 그룹 속성 페이지가 열리면 **구성원** 섹션에서 다음 단계 중 하나를 수행 합니다.

   - **Add** ![ 추가 아이콘 추가를 클릭 ](../../media/ITPro-EAC-AddIcon.png) 합니다. 표시 된 페이지에서 wou를 추가 하려는 사용자를 찾은 다음 **추가 >** 를 클릭 합니다. 사용자를 선택 하 고 필요에 따라 **추가->** 여러 번을 클릭 합니다. 작업을 마친 후 **확인**을 클릭합니다.

   - 제거할 사용자를 선택 하 고 제거 아이콘 **제거** 를 클릭 ![ ](../../media/ITPro-EAC-RemoveIcon.gif) 합니다.

3. 작업을 마쳤으면 **저장**을 클릭합니다.

   > [!NOTE]
   > 구성원을 역할 그룹에 추가하거나 역할 그룹에서 제거한 후 사용자가 관리 권한 변경 내용을 확인하려면 로그아웃했다가 다시 로그인해야 할 수 있습니다.

### <a name="use-the-eac-to-remove-role-groups"></a>EAC를 사용 하 여 역할 그룹 제거

기본 제공 역할 그룹을 제거할 수는 없지만 만든 사용자 지정 역할 그룹을 제거할 수도 있습니다.

1. EAC에서 **사용 권한** \> **관리자 역할로**이동 합니다.

2. 제거할 역할 그룹을 선택한 다음 삭제 아이콘 삭제를 클릭 **Delete** ![ ](../../media/ITPro-EAC-DeleteIcon.png) 합니다.

3. 확인 창이 나타나면 **예** 를 클릭 합니다.

## <a name="use-powershell-to-manage-role-groups"></a>PowerShell을 사용 하 여 역할 그룹 관리

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a>독립 실행형 EOP PowerShell을 사용 하 여 역할 그룹 보기

역할 그룹을 보려면 다음 구문을 사용 합니다.

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

이 예에서는 모든 역할 그룹의 요약 목록을 반환 합니다.

```PowerShell
Get-RoleGroup
```

이 예에서는 받는 사람 관리자 라는 역할 그룹에 대 한 자세한 정보를 반환 합니다.

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

이 예제에서는 사용자 줄리아가 구성원 인 모든 역할 그룹을 반환 합니다. 다음 명령을 실행 하 여 찾을 수 있는 줄리아에는 DistinguishedName (DN) 값을 사용 해야 `Get-User -Identity Julia | Format-List DistinguishedName` 합니다.

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

구문과 매개 변수에 대 한 자세한 내용은 ' [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup)'을 참조 하십시오.

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a>독립 실행형 EOP PowerShell을 사용 하 여 역할 그룹 만들기

새 역할 그룹을 만들 때 모든 설정을 수동으로 구성할 수 있습니다 (그룹을 만드는 동안 또는 이후에). 또는 기존 역할 그룹을 복사 하 여 수정할 수도 있습니다.

- 새 역할 그룹을 수동으로 만들려면 다음 구문을 사용 합니다.

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - _Roles_ 매개 변수는 다음 구문을 사용 하 여 역할 그룹에 할당할 관리 역할을 지정 합니다 `"Role1","Role1",..."RoleN"` . **Get-ManagementRole** cmdlet을 사용 하 여 사용 가능한 역할을 볼 수 있습니다.

  - _Members_ 매개 변수는 다음 구문을 사용 하 여 역할 그룹의 구성원을 지정 합니다 `"Member1","Member2",..."MemberN"` . 사용자, 메일 사용이 가능한 유니버설 보안 그룹 (Usg) 또는 기타 역할 그룹 (보안 주체)을 지정할 수 있습니다.

  이 예에서는 다음 설정을 사용 하 여 "제한 된 받는 사람 관리" 라는 새 역할 그룹을 만듭니다.

  - 역할 그룹에는 Mail Recipients 역할이 할당됩니다.

  - 사용자 Kim 및 Martin는 구성원으로 추가 됩니다.

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- 기존 역할 그룹을 복사 하려면 다음 단계를 수행 합니다.

  1. 다음 구문을 사용 하 여 복사할 역할 그룹을 변수에 저장 합니다.

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. 다음 구문을 사용 하 여 새 역할 그룹을 만듭니다.

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     _Members_ 매개 변수는 다음 구문을 사용 하 여 역할 그룹의 구성원을 지정 합니다 `"Member1","Member2",..."MemberN"` . 사용자, 메일 사용이 가능한 유니버설 보안 그룹 (Usg) 또는 기타 역할 그룹 (보안 주체)을 지정할 수 있습니다.

     이 예에서는 조직 관리 역할 그룹을 "제한 된 조직 관리" 라는 새 역할 그룹으로 복사 합니다. 역할 그룹 구성원은 Isabelle, Carter 및 Lukas입니다.

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

구문 및 매개 변수에 대 한 자세한 내용은 [새-RoleGroup를 사용](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup)하십시오.

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a>독립 실행형 EOP PowerShell 사용 역할 그룹의 구성원 목록을 수정 합니다.

- **추가-rolegroupmember** 및 **Remove-rolegroupmember** cmdlet은 한 번에 하나씩 개별 구성원을 추가 하거나 제거 합니다. **업데이트-RoleGroupMember** cmdlet은 기존 구성원 목록을 대체 하거나 수정할 수 있습니다.

- 역할 그룹의 구성원은 사용자, 메일 사용이 가능한 유니버설 보안 그룹 (Usg) 또는 다른 역할 그룹 (보안 주체)이 될 수 있습니다.

역할 그룹의 구성원을 수정 하려면 다음 구문을 사용 합니다.

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- 기존 구성원 목록을 지정한 값으로 _바꾸려면_ 다음 구문을 사용 `"Member1","Member2",..."MemberN"` 합니다.

- 기존 구성원 목록을 _선택적으로 수정_ 하려면 다음 구문을 사용 `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` 합니다.

이 예에서는 Help Desk 역할 그룹의 현재 구성원을 모두 지정한 사용자로 바꿉니다.

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

이 예에서는 Daigoro Akai를 추가 하 고 Help Desk 역할 그룹의 구성원 목록에서 Valeria Barrio를 제거 합니다.

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

구문 및 매개 변수에 대 한 자세한 내용은 [업데이트-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember)를 참조 하십시오.

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a>독립 실행형 EOP PowerShell을 사용 하 여 역할 그룹 제거

기본 제공 역할 그룹을 제거할 수는 없지만 만든 사용자 지정 역할 그룹을 제거할 수도 있습니다.

사용자 지정 역할 그룹을 제거 하려면 다음 구문을 사용 합니다.

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

이 예에서는 Training Administrators 역할 그룹을 제거합니다.

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

구문과 매개 변수에 대한 자세한 내용은 [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup)를 참조하십시오.

### <a name="how-do-you-know-these-procedures-worked"></a>이 절차가 제대로 수행되었는지 어떻게 확인하나요?

역할 그룹이 성공적으로 복사 되었는지 확인 하려면 다음 단계 중 하나를 수행 합니다.

- EAC에서 **사용 권한** \> **관리자 역할로**이동 하 여 해당 역할 그룹이 나열 되는지 확인 합니다 (또는 나열 되지 않음). 역할 그룹을 선택 하 고 세부 정보 창에서 설정을 확인 하거나 편집 아이콘 **편집** ![ 을 클릭 ](../../media/ITPro-EAC-EditIcon.png) 하 여 설정을 확인 합니다.

- Exchange Online PowerShell에서 \<Role Group Name\> 역할 그룹의 이름으로 바꾸고 다음 명령을 실행 하 여 역할 그룹이 존재 하는지 확인 하 고 (또는 존재 하지 않음) 설정을 확인 합니다.

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
