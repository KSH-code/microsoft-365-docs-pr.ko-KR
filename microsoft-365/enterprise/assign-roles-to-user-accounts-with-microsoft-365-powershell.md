---
title: PowerShell을 사용 하 여 Microsoft 365 사용자 계정에 역할 할당
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- O365ITProTrain
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: ede7598c-b5d5-4e3e-a488-195f02f26d93
description: 이 문서에서는 Microsoft 365 용 PowerShell을 빠르고 쉽게 사용 하 여 사용자 계정에 관리자 역할을 할당 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 7e3292ab26924384beb8d0c7450b7665dccd48fa
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754201"
---
# <a name="assign-admin-roles-to-microsoft-365-user-accounts-with-powershell"></a>PowerShell을 사용 하 여 Microsoft 365 사용자 계정에 관리자 역할 할당

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

Microsoft 365 용 PowerShell을 사용 하 여 사용자 계정에 쉽게 역할을 할당할 수 있습니다.

>[!Note]
>Microsoft 365 관리 센터를 사용 하 여 사용자 계정에  [관리자 역할을 할당](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) 하는 방법에 대해 알아봅니다.
>
>추가 리소스 목록은 [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/)을 참조 하십시오.
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 모듈용 Azure Active Directory PowerShell 사용하기

먼저 전역 관리자 계정을 사용 하 여 [Microsoft 365 테 넌 트에 연결](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)합니다.
  
다음으로, 역할에 추가 하려는 사용자 계정의 로그인 이름 (예: fredsm \@ contoso.com)을 식별 합니다. 이를 UPN (사용자 계정 이름)이 라고도 합니다.

다음으로, 역할 이름을 확인 합니다. [Azure Active Directory에서 관리자 역할 권한을](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)참조 하세요.

>[!Note]
>이 문서의 참고 사항에 주의 하십시오. Azure AD (Active Directory) PowerShell의 일부 역할 이름이 다릅니다. 예를 들어 Microsoft 365 관리 센터의 *Sharepoint 관리자* 역할은 Azure AD PowerShell의 *sharepoint 서비스 관리자* 입니다.
>

다음으로, 로그인 및 역할 이름을 입력 하 고 다음 명령을 실행 합니다.
  
```powershell
$userName="<sign-in name of the account>"
$roleName="<admin role name>"
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
if ($role -eq $null) {
$roleTemplate = Get-AzureADDirectoryRoleTemplate | Where {$_.displayName -eq $roleName}
Enable-AzureADDirectoryRole -RoleTemplateId $roleTemplate.ObjectId
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
}
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId (Get-AzureADUser | Where {$_.UserPrincipalName -eq $userName}).ObjectID
```

다음은 *belindan \@ contoso.com* 계정에 SharePoint 서비스 관리자 역할을 할당 하는 완성 된 명령 집합의 예입니다.
  
```powershell
$userName="belindan@contoso.com"
$roleName="SharePoint Service Administrator"
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
if ($role -eq $null) {
$roleTemplate = Get-AzureADDirectoryRoleTemplate | Where {$_.displayName -eq $roleName}
Enable-AzureADDirectoryRole -RoleTemplateId $roleTemplate.ObjectId
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
}
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId (Get-AzureADUser | Where {$_.UserPrincipalName -eq $userName}).ObjectID
```

특정 관리자 역할의 사용자 이름 목록을 표시 하려면 다음 명령을 사용 합니다.

```powershell
$roleName="<role name>"
Get-AzureADDirectoryRole | Where { $_.DisplayName -eq $roleName } | Get-AzureADDirectoryRoleMember | Ft DisplayName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell용 Microsoft Azure Active Directory 모듈 사용하기

먼저 전역 관리자 계정을 사용 하 여 [Microsoft 365 테 넌 트에 연결](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)합니다.
  
### <a name="for-a-single-role-change"></a>단일 역할 변경의 경우

사용자 계정을 지정 하는 가장 일반적인 방법은 해당 표시 이름 또는 전자 메일 이름을 사용 하 여 로그인 이름 또는 UPN (사용자 계정 이름)이 라고도 하는 것입니다.

#### <a name="display-names-of-user-accounts"></a>사용자 계정의 표시 이름

사용자 계정의 표시 이름으로 작업 하는 데 사용 되는 경우 다음 정보를 확인 합니다.
  
- 구성 하려는 사용자 계정
    
    사용자 계정을 지정 하려면 해당 표시 이름을 결정 해야 합니다. 계정의 전체 목록을 보려면 다음 명령을 사용 합니다.
    
  ```powershell
  Get-MsolUser -All | Sort DisplayName | Select DisplayName | More
  ```

    이 명령은 표시 이름별로 정렬 된 사용자 계정의 표시 이름을 한 번에 하나씩 나열 합니다. **Where** cmdlet을 사용 하 여 목록을 더 작은 집합으로 필터링 할 수 있습니다. 아래 예제를 참고하십시오.

   >[!Note]
   >PowerShell Core에서는 이름에 *Msol* 이 포함 된 Windows powershell 모듈 및 cmdlet에 대 한 Microsoft Azure Active Directory 모듈을 지원 하지 않습니다. Windows PowerShell에서 다음 cmdlet을 실행 합니다.
   >
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort DisplayName | Select DisplayName | More
  ```

    이 명령은 표시 이름이 "John"으로 시작 하는 사용자 계정만 나열 합니다.
    
- 할당 하려는 역할
    
    사용자 계정에 할당할 수 있는 사용 가능한 관리자 역할 목록을 표시 하려면 다음 명령을 사용 합니다.
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

계정의 표시 이름과 역할 이름을 확인 한 후에는 다음 명령을 사용 하 여 계정에 역할을 할당 합니다.
  
```powershell
$dispName="<The Display Name of the account>"
$roleName="<The admin role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

메모장에 명령을 붙여 넣습니다. *$DispName* 및 *$roleName* 변수에 대해 설명 텍스트를 해당 값으로 바꿉니다. 문자를 제거 \< and > 하 되 따옴표는 그대로 둡니다. 수정 된 줄을 Windows PowerShell 용 Microsoft Azure Active Directory 모듈 창에 붙여 넣어 실행 합니다. 또는 Windows PowerShell ISE (통합 스크립트 환경)를 사용할 수 있습니다.
  
다음은 완성 된 명령 집합의 예입니다.
  
```powershell
$dispName="Scott Wallace"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

#### <a name="sign-in-names-of-user-accounts"></a>사용자 계정의 로그인 이름

사용자 계정의 로그인 이름 또는 Upn으로 작업 하는 데 사용 되는 경우 다음 정보를 확인 합니다.
  
- 사용자 계정의 UPN
    
    UPN을 모르는 경우 다음 명령을 사용 합니다.
    
  ```powershell
  Get-MsolUser -All | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    이 명령은 UPN에 따라 정렬 된 사용자 계정의 UPN을 한 번에 하나씩 나열 합니다. **Where** cmdlet을 사용 하 여 목록을 필터링 할 수 있습니다. 예를 들면 다음과 같습니다.
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    이 명령은 표시 이름이 "John"으로 시작 하는 사용자 계정만 나열 합니다.
    
- 할당 하려는 역할
    
    사용자 계정에 할당할 수 있는 사용 가능한 역할 목록을 표시 하려면 다음 명령을 사용 합니다.
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

계정의 UPN과 역할 이름을 받은 후에는 다음 명령을 사용 하 여 계정에 역할을 할당 합니다.
  
```powershell
$upnName="<The UPN of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

명령을 복사 하 여 메모장에 붙여 넣습니다. **$UpnName** 및 **$roleName** 변수 설명 텍스트를 해당 값으로 바꿉니다. 문자를 제거 \< and > 하 되 따옴표는 그대로 둡니다. 수정 된 줄을 Windows PowerShell 용 Microsoft Azure Active Directory 모듈 창에 붙여 넣어 실행 합니다. 또는 Windows PowerShell ISE를 사용할 수 있습니다.
  
다음은 완성 된 명령 집합의 예입니다.
  
```powershell
$upnName="scottw@contoso.com"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

### <a name="multiple-role-changes"></a>여러 역할 변경

여러 역할 변경의 경우 다음 정보를 확인 합니다.
  
- 구성 하려는 사용자 계정 이전 섹션의 방법을 사용 하 여 표시 이름 또는 Upn 집합을 수집할 수 있습니다.
    
- 각 사용자 계정에 할당 하려는 역할 사용자 계정에 할당할 수 있는 사용 가능한 역할 목록을 표시 하려면 다음 명령을 사용 합니다.
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

다음으로 표시 이름이 나 UPN 및 role name 필드가 있는 CSV (쉼표로 구분 된 값) 텍스트 파일을 만듭니다. Microsoft Excel에서이 작업을 쉽게 수행할 수 있습니다.

다음은 표시 이름에 대 한 예입니다.
  
```powershell
DisplayName,RoleName
"Belinda Newman","Billing Administrator"
"Scott Wallace","SharePoint Service Administrator"
```

다음으로, CSV 파일의 위치를 입력 하 고 PowerShell 명령 프롬프트에서 결과 명령을 실행 합니다.
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach {Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser | Where DisplayName -eq $_.DisplayName).UserPrincipalName -RoleName $_.RoleName }

```

Upn의 예는 다음과 같습니다.
  
```powershell
UserPrincipalName,RoleName
"belindan@contoso.com","Billing Administrator"
"scottw@contoso.com","SharePoint Service Administrator"
```

다음으로, CSV 파일의 위치를 입력 하 고 PowerShell 명령 프롬프트에서 결과 명령을 실행 합니다.
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach { Add-MsolRoleMember -RoleMemberEmailAddress $_.UserPrincipalName -RoleName $_.RoleName }

```

## <a name="see-also"></a>참고 항목

- [PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
- [PowerShell로 Microsoft 365 관리](manage-microsoft-365-with-microsoft-365-powershell.md)
- [Microsoft 365용 PowerShell 시작](getting-started-with-microsoft-365-powershell.md)
