---
title: 사용자에게 보안 및 준수 센터에 대한 액세스 권한 부여
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
f1_keywords:
- ms.o365.cc.PermissionsHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: 사용자에 게 Microsoft 365 보안 & 준수 센터에서 해당 보안 또는 규정 준수 기능을 관리할 수 있는 권한을 할당 해야 합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5d586684d44545f7aea94c30f5474b1fe5fa4651
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202810"
---
# <a name="give-users-access-to-the-security--compliance-center"></a>사용자에게 보안 및 준수 센터에 대한 액세스 권한 부여

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


사용자에 게 보안 또는 규정 준수 기능을 관리 하려면 먼저 Security & 준수 센터에서 사용 권한을 할당 받아야 합니다. 보안 & 준수 센터에 있는 전역 관리자 또는 OrganizationManagement 역할 그룹의 구성원 인 사용자에 게 이러한 사용 권한을 부여할 수 있습니다. 사용자는 액세스 권한을 부여 받은 보안 또는 규정 준수 기능만 관리할 수 있습니다.

보안 & 준수 센터에서 사용자에 게 부여할 수 있는 다양 한 사용 권한에 대 한 자세한 내용은 [보안 & 준수 센터의 사용 권한을](permissions-in-the-security-and-compliance-center.md)참조 하세요.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용

- 이 문서의 단계를 완료 하려면 전역 관리자 이거나 보안 & 준수 센터에서 OrganizationManagement 역할 그룹의 구성원 이어야 합니다.

- 보안 & 준수 센터의 역할 그룹은 Exchange Online의 역할 그룹과 유사한 이름을 사용할 수 있지만 동일 하지는 않습니다.

- 역할 그룹 구성원 자격은 Exchange Online과 보안 & 준수 센터 간에 공유 되지 않습니다.

- (AOBO) 권한이 있는 DAP (위임 된 액세스 권한) 사용 권한을 사용 하는 경우에는 보안 & 준수 센터에 액세스할 수 없습니다.

## <a name="use-the-security--compliance-center-to-give-another-user-access-to-the-security--compliance-center"></a>보안 & 준수 센터를 사용 하 여 다른 사용자에 게 보안 & 준수 센터에 대 한 액세스 권한 부여

1. 보안 & 준수 센터를 열고 <https://protection.office.com> **사용 권한**으로 이동 합니다. **사용 권한** 탭으로 바로 이동 하려면를 엽니다 <https://protection.office.com/permissions> .

2. 역할 그룹 목록에서 역할 그룹을 선택 하 고 편집 아이콘 편집을 클릭 **Edit** ![ ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) 합니다.

3. 역할 그룹의 속성 페이지 **구성원**아래에 있는 추가 아이콘 추가 **를 클릭 하** ![ ](../../media/ITPro-EAC-AddIcon.gif) 고 추가 하려는 사용자의 이름을 선택 합니다.

4. 역할 그룹에 추가 하려는 모든 사용자를 선택 했으면 **추가 \> ** 를 클릭 한 다음 **확인**을 클릭 합니다.

5. 작업을 마쳤으면 **저장**을 클릭합니다.

## <a name="use-security--compliance-center-powershell-to-give-another-user-access-to-the-security--compliance-center"></a>보안 & 준수 센터 PowerShell을 사용 하 여 다른 사용자에 게 보안 & 준수 센터에 대 한 액세스 권한 부여

1. [보안 및 준수 센터 PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)합니다.

2. 다음 구문을 사용합니다.

   ```powershell
   Add-RoleGroupMember -Identity <RoleGroup> -Member <UserIdentity>

   - _Identity_ is the role group.
   - _Member_ is the user or universal security group (USG). You can specify only one member at a time.

   This example adds MatildaS to the Organization Management role group.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

구문 및 매개 변수 문제에 대 한 자세한 내용은 [추가-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember) 를 참조 하십시오.

### <a name="how-do-you-know-this-worked"></a>작동 여부는 어떻게 확인하나요?

보안 & 준수 센터에 대 한 액세스 권한을 부여 했는지 확인 하려면 다음 단계 중 하나를 수행 합니다.

- 보안 & 준수 센터에서 **사용 권한** 으로 이동 하 여 역할 그룹을 선택 합니다. 세부 정보 플라이 아웃이 열리면 역할 그룹의 구성원을 확인 합니다. 

- 보안 & 준수 센터 PowerShell에서 \<RoleGroupName\> 역할 그룹의 이름으로 바꾸고 다음 명령을 실행 합니다.

  ```powershell
  Get-RoleGroupMember -Identity "<RoleGroupName>"
  ```

  구문 및 매개 변수에 대 한 자세한 내용은 [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember)를 참조 하십시오.
