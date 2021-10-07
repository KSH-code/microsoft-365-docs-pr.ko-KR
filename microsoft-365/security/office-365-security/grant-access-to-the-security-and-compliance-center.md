---
title: 사용자에게 보안 및 규정 준수 센터에 대한 액세스 권한 부여
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
ms.localizationpriority: medium
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: 보안 또는 규정 준수 기능을 관리하려면 Microsoft 365 & 준수 센터에서 사용 권한을 할당해야 합니다.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2dcab8a14df6266bea87b3ae876ed9bac8eea1d7
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60213472"
---
# <a name="give-users-access-to-the-security--compliance-center"></a>사용자에게 보안 및 규정 준수 센터에 대한 액세스 권한 부여

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

보안 또는 규정 준수 기능을 관리하려면 & 보안 및 준수 센터에서 사용 권한을 할당해야 합니다. 보안 및 준수 센터에서 OrganizationManagement 역할 & 전역 관리자 또는 구성원으로 이러한 권한을 사용자에게 부여할 수 있습니다. 사용자는 액세스 권한을 부여 받은 보안 또는 규정 준수 기능만 관리할 수 있습니다.

보안 및 준수 센터에서 사용자에게 부여할 수 있는 다양한 사용 권한에 대한 자세한 내용은 & 규정 준수 센터의 사용 권한을 [& 참조하십시오.](permissions-in-the-security-and-compliance-center.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 사항은 무엇인가요?

- 이 문서의 단계를 완료하려면 Security & Compliance Center에서 전역 관리자 또는 OrganizationManagement 역할 그룹의 구성원일 수 있습니다.

- 보안 & 준수 센터의 역할 그룹은 Exchange Online 역할 그룹과 유사할 수 있지만 동일하지는 않습니다.

- 역할 그룹 구성원 자격은 보안 및 준수 Exchange Online 간에 & 않습니다.

- AOBO(관리 위임된 액세스 권한) 권한이 있는 DAP(위임된 액세스 권한) 파트너는 보안 및 준수 센터에 액세스할 & 없습니다.

## <a name="use-the-security--compliance-center-to-give-another-user-access-to-the-security--compliance-center"></a>보안 및 & 센터를 사용하여 다른 사용자에게 보안 및 준수 센터에 대한 & 부여

1. 에서 보안 & 준수 센터를 <https://protection.office.com> 열고 사용 **권한으로 이동 합니다.** 사용 권한 탭으로 직접 **이동하려면** 을 을 를 니다. <https://protection.office.com/permissions>

2. 역할 그룹 목록에서 역할 그룹을 선택한 다음  편집 편집 ![ 아이콘을 ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) 클릭합니다.

3. 역할 그룹의 속성 페이지에서 구성원 **아래의** 아이콘 **추가를** ![ 클릭합니다.](../../media/ITPro-EAC-AddIcon.gif) 를 선택하고 추가할 사용자의 이름을 선택합니다.

4. 역할 그룹에 추가할 모든 사용자를 선택한 경우 **추가를 \>** 클릭한 다음 확인 을 **클릭합니다.**

5. 작업을 마쳤으면 **저장** 을 클릭합니다.

## <a name="use-security--compliance-center-powershell-to-give-another-user-access-to-the-security--compliance-center"></a>보안 & 준수 센터 PowerShell을 사용하여 다른 사용자에게 보안 및 준수 센터에 & 권한을 부여합니다.

1. [보안 및 준수 센터 PowerShell에 연결](/powershell/exchange/connect-to-scc-powershell)합니다.

2. 다음 구문을 사용합니다.

   ```powershell
   Add-RoleGroupMember -Identity <RoleGroup> -Member <UserIdentity>

   - _Identity_ is the role group.
   - _Member_ is the user or universal security group (USG). You can specify only one member at a time.

   This example adds MatildaS to the Organization Management role group.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

구문과 매개 변수 문제에 대한 자세한 내용은 [Add-RoleGroupMember를 참조합니다.](/powershell/module/exchange/add-rolegroupmember)

### <a name="how-do-you-know-this-worked"></a>작동 여부는 어떻게 확인하나요?

보안 및 준수 센터에 대한 액세스 권한이 & 다음 단계 중 하나를 수행합니다.

- 보안 및 & 센터에서 사용 권한으로 이동하여 역할 그룹을 선택합니다.  열 수 있는 세부 정보 플라이아웃에서 역할 그룹의 구성원을 확인 합니다.

- 보안 & 준수 센터 PowerShell에서 역할 그룹의 이름으로 바꾸고 \<RoleGroupName\> 다음 명령을 실행합니다.

  ```powershell
  Get-RoleGroupMember -Identity "<RoleGroupName>"
  ```

  구문과 매개 변수에 대한 자세한 내용은 [Get-RoleGroupMember 를 참조하십시오.](/powershell/module/exchange/Get-RoleGroupMember)