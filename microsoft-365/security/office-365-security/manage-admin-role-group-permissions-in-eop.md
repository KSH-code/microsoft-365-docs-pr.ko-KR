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
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: 관리자는 Exchange Online Protection의 EAC(Exchange 관리 센터)에서 사용 권한을 할당하거나 제거하는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b53023521f477b5e864424ec648ccf7e5b749d0c
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166990"
---
# <a name="manage-role-groups-in-standalone-eop"></a>독립 실행형 EOP에서 역할 그룹 관리

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
-  [Exchange Online Protection 독립 실행형](https://go.microsoft.com/fwlink/?linkid=2148611)

Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서는 EAC(Exchange 관리 센터)를 사용하여 역할 그룹에 사용자를 추가할 수 있습니다. 역할 그룹에 사용자를 추가하면 사용자에게 특정 관리 작업을 수행할 수 있는 권한이 부여됩니다. 역할 그룹에서 사용자를 제거할 수 있습니다.

역할 및 역할 그룹에 대한 자세한 내용은 독립 실행형 [EOP의 사용 권한을 참조하세요.](feature-permissions-in-eop.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 사항은 무엇인가요?

- EAC(Exchange 관리 센터)를 열하려면 독립 실행형 [EOP에서 Exchange 관리 센터를 참조하세요.](exchange-admin-center-in-exchange-online-protection-eop.md)

- 독립 실행형 EOP PowerShell을 열기 위해 [Exchange Online Protection PowerShell에 연결합니다.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)

- 이 문서의 절차를 수행하려면 먼저 Exchange Online Protection에서 사용 권한을 할당해야 합니다. 특히 조직 관리  역할 그룹에 기본적으로 할당되는  역할 관리 역할이 필요합니다. 자세한 내용은 독립 실행형 [EOP의](feature-permissions-in-eop.md) 사용 권한을 참조하고 EAC를 사용하여 역할 그룹의 구성원 목록을 [수정합니다.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- 이 문서의 절차에 적용할 수 있는 바로 가기 키에 대한 자세한 내용은 [Exchange Online의 Exchange](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)관리 센터에 대한 바로 가기 키를 참조하십시오.

> [!TIP]
> 문제가 있나요? [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) 포럼에서 도움을 요청하세요.

## <a name="use-the-eac-to-manage-role-groups"></a>EAC를 사용하여 역할 그룹 관리

### <a name="use-the-eac-to-view-role-groups"></a>EAC를 사용하여 역할 그룹 보기

1. EAC에서 **사용** 권한 관리자 \> **역할로 이동하세요.** 조직의 모든 역할 그룹이 여기에 나열됩니다.

2. 역할 그룹을 선택합니다. 세부 정보 창에는 역할 그룹의 **이름,** **설명,** **할당된** 역할 및 관리 **역할이** 표시됩니다. 편집 아이콘을 클릭하여 이 정보를 **볼** ![ 수도 ](../../media/ITPro-EAC-EditIcon.png) 있습니다.

### <a name="use-the-eac-to-create-role-groups"></a>EAC를 사용하여 역할 그룹 만들기

새 역할 그룹을 만들 때 모든 설정을 직접 구성할 수 있습니다(그룹을 만드는 동안 또는 이후에). 또는 기존 역할 그룹을 복사하여 수정할 수 있습니다.

1. EAC에서 **사용** 권한 관리자 역할로 이동한 다음 다음 단계 중 \> 하나를 수행합니다.

   - **새 역할 그룹을 수동으로** 만들기 : **추가** ![ 아이콘을 ](../../media/ITPro-EAC-AddIcon.png) 클릭합니다.

   - **기존 역할 그룹** 복사 : 복사할 역할 그룹을 선택한  다음 복사 아이콘을 ![ ](../../media/ITPro-EAC-CopyIcon.png) 클릭합니다.

2. 새 역할 **그룹** 창이 나타나면 다음 설정을 구성합니다.

    - **이름**: 역할 그룹의 고유 이름을 입력합니다.

    - **설명:** 역할 그룹에 대한 선택적 설명을 입력합니다.

    - **역할:** **추가 아이콘** 또는 제거 아이콘을 클릭하여 역할 그룹에 할당된 역할을 선택하거나 ![ ](../../media/ITPro-EAC-AddIcon.png)  ![ ](../../media/ITPro-EAC-RemoveIcon.gif) 수정합니다.

    - **구성원:** **추가 아이콘 또는** 제거 아이콘을 클릭하여 역할 그룹 ![ ](../../media/ITPro-EAC-AddIcon.png)  ![ ](../../media/ITPro-EAC-RemoveIcon.gif) 구성원을 수정합니다.

3. 완료되면 저장을 클릭하여 역할  그룹을 만드시다.

### <a name="use-the-eac-to-modify-role-groups"></a>EAC를 사용하여 역할 그룹 수정

EAC에서 **사용** 권한 관리 역할로 이동하여 수정할 역할 그룹을 선택한 다음 편집 \>   ![ 아이콘을 ](../../media/ITPro-EAC-EditIcon.png) 클릭합니다.

역할 그룹을 만들 때와 역할 그룹을 수정할 때도 동일한 옵션을 사용할 수 있습니다. 다음을 수행할 수 있습니다.

- 이름과 설명을 변경합니다.

- 관리 역할을 추가 및 제거합니다(역할 할당 만들기 또는 제거).

- 구성원을 추가 및 제거합니다.

**참고:** 조직 관리와 같은 일부 역할 그룹은 그룹에서 제거할 수 있는 역할을 제한합니다.

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a>EAC를 사용하여 역할 그룹의 구성원 목록 수정

1. EAC에서 **사용** 권한 관리 역할로 이동하여 수정할 역할 그룹을 선택한 다음 편집 \>   ![ 아이콘을 ](../../media/ITPro-EAC-EditIcon.png) 클릭합니다.

2. 열 수 있는 역할 그룹 속성 페이지의 **Members** 섹션에서 다음 단계 중 하나를 수행합니다.

   - 아이콘 **추가를** ![ ](../../media/ITPro-EAC-AddIcon.png) 클릭합니다. 나타나는 페이지에서 wou를 추가할 사용자를 찾은 다음 **->.** 사용자를 선택하고 필요한 >**->** 추가를 클릭합니다. 작업을 마친 후 **확인** 을 클릭합니다.

   - 제거할 사용자를 선택하고 **제거** ![ 아이콘을 ](../../media/ITPro-EAC-RemoveIcon.gif) 클릭합니다.

3. 작업을 마쳤으면 **저장** 을 클릭합니다.

   > [!NOTE]
   > 구성원을 역할 그룹에 추가하거나 역할 그룹에서 제거한 후 사용자가 관리 권한 변경 내용을 확인하려면 로그아웃했다가 다시 로그인해야 할 수 있습니다.

### <a name="use-the-eac-to-remove-role-groups"></a>EAC를 사용하여 역할 그룹 제거

기본 제공 역할 그룹은 제거할 수 없지만 만든 사용자 지정 역할 그룹을 제거할 수 있습니다.

1. EAC에서 **사용** 권한 관리자 \> **역할로 이동하세요.**

2. 제거할 역할 그룹을 선택하고 삭제 **아이콘을** ![ ](../../media/ITPro-EAC-DeleteIcon.png) 클릭합니다.

3. 확인 **창이** 나타나면 예를 클릭합니다.

## <a name="use-powershell-to-manage-role-groups"></a>PowerShell을 사용하여 역할 그룹 관리

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a>독립 실행형 EOP PowerShell을 사용하여 역할 그룹 보기

역할 그룹을 보기 위해 다음 구문을 사용 합니다.

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

이 예에서는 모든 역할 그룹의 요약 목록을 반환합니다.

```PowerShell
Get-RoleGroup
```

이 예에서는 Recipient Administrators 역할 그룹에 대한 자세한 정보를 반환합니다.

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

이 예에서는 사용자 Julia가 구성원인 모든 역할 그룹을 반환합니다. 다음 명령을 실행하여 찾을 수 있는 Julia에 DN(DistinguishedName) 값을 사용해야 `Get-User -Identity Julia | Format-List DistinguishedName` 합니다.

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

구문과 매개 변수에 대한 자세한 내용은 [Get-RoleGroup을 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup)

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a>독립 실행형 EOP PowerShell을 사용하여 역할 그룹 만들기

새 역할 그룹을 만들 때 그룹을 만드는 동안 또는 이후에 모든 설정을 수동으로 구성할 수 있습니다. 또는 기존 역할 그룹을 복사하여 수정할 수 있습니다.

- 새 역할 그룹을 수동으로 만들하려면 다음 구문을 사용하세요.

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - Roles _매개_ 변수는 다음 구문을 사용하여 역할 그룹에 할당할 관리 역할을 `"Role1","Role1",..."RoleN"` 지정합니다. **Get-ManagementRole** cmdlet을 사용하여 사용 가능한 역할을 볼 수 있습니다.

  - Members  매개 변수는 다음 구문을 사용하여 역할 그룹의 구성원을 `"Member1","Member2",..."MemberN"` 지정합니다. 사용자, 메일 사용이 가능한 USG(유니버설 보안 그룹) 또는 기타 역할 그룹(보안 주체)을 지정할 수 있습니다.

  이 예에서는 다음 설정을 사용하여 "Limited Recipient Management"라는 새 역할 그룹을 만듭니다.

  - 역할 그룹에는 Mail Recipients 역할이 할당됩니다.

  - 사용자 Kim과 Martin이 구성원으로 추가됩니다.

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- 기존 역할 그룹을 복사하기 위해 다음 단계를 수행합니다.

  1. 다음 구문을 사용하여 복사할 역할 그룹을 변수에 저장합니다.

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. 다음 구문을 사용하여 새 역할 그룹을 만들 수 있습니다.

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     Members  매개 변수는 다음 구문을 사용하여 역할 그룹의 구성원을 `"Member1","Member2",..."MemberN"` 지정합니다. 사용자, 메일 사용이 가능한 USG(유니버설 보안 그룹) 또는 기타 역할 그룹(보안 주체)을 지정할 수 있습니다.

     이 예에서는 조직 관리 역할 그룹을 "Limited Organization Management"라는 새 역할 그룹에 복사합니다. 역할 그룹 구성원은 Isabelle, Carter 및 Lukas입니다.

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

구문과 매개 변수에 대한 자세한 내용은 [New-RoleGroup.](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup)

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a>독립 실행형 EOP PowerShell을 사용하여 역할 그룹의 구성원 목록 수정

- **Add-RoleGroupMember** 및 **Remove-RoleGroupMember** cmdlet은 개별 구성원을 한 번씩 추가하거나 제거합니다. **Update-RoleGroupMember** cmdlet은 기존 구성원 목록을 대체하거나 수정할 수 있습니다.

- 역할 그룹의 구성원은 사용자, 메일 사용이 가능한 USG(유니버설 보안 그룹) 또는 기타 역할 그룹(보안 주체)일 수 있습니다.

역할 그룹의 구성원을 수정하려면 다음 구문을 사용 합니다.

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- 기존 _구성원_ 목록을 지정한 값으로 바꾸기 위해 다음 구문을 `"Member1","Member2",..."MemberN"` 사용합니다.

- 기존 _구성원 목록을_ 선택적으로 수정하려면 다음 구문을 사용하세요. `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}`

이 예에서는 Help Desk 역할 그룹의 모든 현재 구성원을 지정된 사용자로 바 대체합니다.

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

이 예에서는 Daigoro Akai를 추가하고 Help Desk 역할 그룹의 구성원 목록에서 발레리아 Barrio를 제거합니다.

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

구문과 매개 변수에 대한 자세한 내용은 [Update-RoleGroupMember를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember)

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a>독립 실행형 EOP PowerShell을 사용하여 역할 그룹 제거

기본 제공 역할 그룹은 제거할 수 없지만 만든 사용자 지정 역할 그룹을 제거할 수 있습니다.

사용자 지정 역할 그룹을 제거하려면 다음 구문을 사용 합니다.

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

이 예에서는 Training Administrators 역할 그룹을 제거합니다.

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

구문과 매개 변수에 대한 자세한 내용은 [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup)를 참조하십시오.

### <a name="how-do-you-know-these-procedures-worked"></a>이 절차가 제대로 수행되었는지 어떻게 확인하나요?

역할 그룹을 성공적으로 복사한 경우 다음 단계 중 하나를 수행합니다.

- EAC에서 **사용** 권한 관리자 역할로 이동한 다음 역할 그룹이 나열되어 있는지 \> 또는 나열되지 않는지 확인해야 합니다. 역할 그룹을 선택하고 세부 정보 창의 설정을 확인하거나  편집 아이콘을 클릭하여 설정을 ![ ](../../media/ITPro-EAC-EditIcon.png) 확인합니다.

- Exchange Online PowerShell에서 역할 그룹의 이름으로 바꾸고 다음 명령을 실행하여 역할 그룹이 존재하거나 존재하지 않는지 확인하고 설정을 \<Role Group Name\> 확인합니다.

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
