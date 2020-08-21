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
description: 사용자는 Microsoft 365 보안 및 규정 준수 & Microsoft 365 보안 정책에서 권한을 할당 받아야만 해당 보안 또는 규정 준수 기능을 관리할 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d21fef9458c02bd09d6d5ce2129b95571e0f8371
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826604"
---
# <a name="give-users-access-to-the-security--compliance-center"></a>사용자에게 보안 및 준수 센터에 대한 액세스 권한 부여

사용자는 보안 또는 규정 준수 기능을 & 보안 센터에서 권한을 할당 받아야 합니다. 보안 그룹 준수 센터에서 OrganizationManagement 역할 그룹의 전역 관리자 또는 & 사용자에게 이러한 사용 권한을 부여할 수 있습니다. 사용자는 액세스 권한을 부여 받은 보안 또는 규정 준수 기능만 관리할 수 있습니다.

보안 대시보드 준수 센터에서 사용자에게 부여할 수 있는 다양한 권한에 & 대한 자세한 내용은 보안 정책 [준수 센터에서 사용 권한을 & 확인하십시오.](permissions-in-the-security-and-compliance-center.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- 이 문서의 단계를 완료하려면 보안 & 관리 센터에서 OrganizationManagement 역할 그룹의 구성원이어야 합니다.

- 보안 그룹 규정 준수 센터의 & 그룹은 Exchange Online의 역할 그룹과 이름이 비슷할 수 있지만 같은 그렇지는 않습니다.

- 역할 그룹 구성원은 Exchange Online과 준수 센터의 보안 서비스 & 공유되지 않습니다.

- AOBO(관리<token>Exister On Behalf Of) 권한이 있는 DAP(위임된 액세스 권한) 파트너는 Security &amp; 있습니다.

## <a name="use-the-admin-center-to-give-another-user-access-to-the-security--compliance-center"></a>관리 센터를 사용하여 다른 사용자에게 보안 업데이트 준수 센터에 대한 액세스 권한 & 제공

1. [로그인하고 관리 센터로 이동합니다.](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center)

2. Microsoft 365 관리 센터에서 관리 **센터를 연 다음 보안** 교육 **& 클릭합니다.**

3. In the Security & Compliance Center, go to **Permissions.**

4. 목록에서 사용자를 추가할 역할 그룹을 선택하고 편집 아이콘을 **Edit** ![ ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) 클릭합니다.

5. Members 아래의 역할 그룹의 속성 **Add** **페이지에서** ![ 아이콘 추가를 ](../../media/ITPro-EAC-AddIcon.gif) 클릭하고 추가할 사용자의 이름을 선택합니다.

6. 역할 그룹에 추가할 모든 사용자를 선택한 후 추가를 클릭한 다음 **확인을 \> ** **클릭합니다.**

7. **저장**을 클릭하여 역할 그룹에 대한 변경 내용을 저장합니다.

### <a name="how-do-you-know-this-worked"></a>작동 여부는 어떻게 확인합니까?

1. In the Security & Compliance Center, go to **Permissions.**

2. 목록에서 구성원을 볼 역할 그룹을 선택합니다.

3. 오른쪽에 있는 역할 그룹 세부 정보에서 역할 그룹의 구성원을 볼 수 있습니다.

## <a name="use-powershell-to-give-another-user-access-to-the-security--compliance-center"></a>PowerShell을 사용하여 다른 사용자에게 보안 서비스 응용 프로그램 준수 & 부여

1. [보안 및 준수 센터 PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)합니다.

2. 다음 예와 같이 **Add-RoleGroupMember** 명령을 사용하여 사용자를 조직 관리 역할에 추가합니다.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

   **매개 변수**:

   - _ID는_ 구성원을 추가할 역할 그룹입니다.

   - _구성원은_ 역할 그룹에 추가할 사서함, USG(유니버설 보안 그룹) 또는 컴퓨터입니다. 구성원은 한 번에 하나만 지정할 수 있습니다.

구문 및 매개 변수에 대한 자세한 내용은 [Add-RoleGroupMember를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/Add-RoleGroupMember)

### <a name="how-do-you-know-this-worked"></a>작동 여부는 어떻게 확인하나요?

사용자에게 보안 & 준수 센터에 대한 액세스 권한을 부여받을 것인지 확인하려면 다음 예와 같이 **Get-RoleGroupMember** cmdlet을 사용하여 조직 관리 역할 그룹의 구성원을 확인합니다.

```PowerShell
Get-RoleGroupMember -Identity "Organization Management"
```

구문과 매개 변수에 대한 자세한 내용은 [Get-RoleGroupMember를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember)
