---
title: PowerShell을 Microsoft 365 사용자 계정에 역할 할당
ms.author: kvice
author: kelleyvice-msft
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
description: 이 문서에서는 PowerShell을 사용하여 사용자 계정에 관리자 역할을 Microsoft 365 방법을 알아보습니다.
ms.openlocfilehash: 4174877bed9accacc3a61de576fa6e54060678bf
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59213865"
---
# <a name="assign-admin-roles-to-microsoft-365-user-accounts-with-powershell"></a>PowerShell을 통해 사용자 Microsoft 365 관리자 역할 할당

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

PowerShell을 사용하여 사용자 계정에 역할을 쉽게 할당할 수 Microsoft 365.

>[!Note]
>사용자 계정을 [통해](../admin/add-users/assign-admin-roles.md) 관리자 역할을 할당하는 방법을 Microsoft 365 관리 센터.
>
>추가 리소스 목록은 사용자 및 그룹 [관리를 참조하세요.](../admin/add-users/index.yml)
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 모듈용 Azure Active Directory PowerShell 사용하기

먼저 Azure **AD DC 관리자,** 클라우드 응용  프로그램 관리자 또는 전역 관리자 계정을 사용하여  [테넌트에 Microsoft 365 합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
 
자세한 내용은 [관리자 역할 정보](/microsoft-365/admin/add-users/about-admin-roles?)를 참조하세요.

그런 다음 역할에 추가할 사용자 계정의 로그인 이름(예: fredsm \@ contoso.com)을 식별합니다. 이를 UPN(사용자 계정 이름)이라고도 합니다.

그런 다음 역할의 이름을 확인 합니다. [Azure AD 기본 제공 역할을 참조하세요.](/azure/active-directory/roles/permissions-reference)

>[!Note]
>이 문서의 메모에 주의하세요. 일부 역할 이름은 Azure AD Azure Active Directory PowerShell과 다릅니다. 예를 들어 SharePoint *관리자* 역할은 Microsoft 365 관리 센터 PowerShell의 SharePoint *관리자입니다.*
>

그런 다음 로그인 및 역할 이름을 입력하고 다음 명령을 실행합니다.
  
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

다음은 SharePoint 서비스 관리자 역할을 *belindan \@* contoso.com 명령 집합의 예입니다.
  
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

특정 관리자 역할의 사용자 이름 목록을 표시하려면 다음 명령을 사용하세요.

```powershell
$roleName="<role name>"
Get-AzureADDirectoryRole | Where { $_.DisplayName -eq $roleName } | Get-AzureADDirectoryRoleMember | Ft DisplayName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell용 Microsoft Azure Active Directory 모듈 사용하기

먼저 전역 관리자 계정을 사용하여 Microsoft 365 [테넌트에 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)
  
### <a name="for-a-single-role-change"></a>단일 역할 변경의 경우

사용자 계정을 지정하는 가장 일반적인 방법은 표시 이름 또는 해당 전자 메일 이름(로그인 이름 또는 UPN(사용자 계정 이름)이라고도 하는)을 사용하는 것입니다.

#### <a name="display-names-of-user-accounts"></a>사용자 계정의 이름 표시

사용자 계정의 표시 이름을 사용하는 경우 다음 정보를 결정하십시오.
  
- 구성할 사용자 계정
    
    사용자 계정을 지정하려면 해당 표시 이름을 결정해야 합니다. 계정의 전체 목록을 표시하기 위해 다음 명령을 사용하세요.
    
  ```powershell
  Get-MsolUser -All | Sort DisplayName | Select DisplayName | More
  ```

    이 명령은 사용자 계정의 표시 이름을 표시 이름별로 정렬하여 한 화면씩 나열합니다. **Where** cmdlet을 사용하여 목록을 더 작은 집합으로 필터링할 수 있습니다. 아래 예제를 참고하십시오.

   >[!Note]
   >PowerShell Core는 Windows PowerShell용 Microsoft Azure Active Directory 모듈 및 이름에 *Msol* 이 있는 cmdlet을 지원하지 않습니다. Windows PowerShell에서 이러한 cmdlet을 실행합니다.
   >
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort DisplayName | Select DisplayName | More
  ```

    이 명령은 표시 이름이 "John"으로 시작하는 사용자 계정만 나열합니다.
    
- 할당할 역할
    
    사용자 계정에 할당할 수 있는 사용 가능한 관리자 역할 목록을 표시하려면 다음 명령을 사용하세요.
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

계정의 표시 이름과 역할 이름을 확인한 후 다음 명령을 사용하여 계정에 역할을 할당합니다.
  
```powershell
$dispName="<The Display Name of the account>"
$roleName="<The admin role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

명령을 명령에 붙여 메모장. $dispName *$roleName* *변수의* 경우 설명 텍스트를 해당 값으로 바 사용합니다. 문자를 \< and > 제거하 고 인용 부호를 유지 합니다. 수정된 줄을 실행하기 위해 Microsoft Azure Active Directory 모듈에 Windows PowerShell 붙여 넣습니다. 또는 ISE(통합 스크립트 Windows PowerShell)를 사용할 수 있습니다.
  
완성된 명령 집합의 예는 다음과 같습니다.
  
```powershell
$dispName="Scott Wallace"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

#### <a name="sign-in-names-of-user-accounts"></a>사용자 계정의 로그인 이름

사용자 계정의 로그인 이름 또는 UPNS로 작업하는 데 사용되는 경우 다음 정보를 결정하십시오.
  
- 사용자 계정의 UPN
    
    UPN을 모르는 경우 다음 명령을 사용 합니다.
    
  ```powershell
  Get-MsolUser -All | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    이 명령은 사용자 계정의 UPN을 UPN별로 정렬하여 한 화면씩 나열합니다. Where cmdlet을 **사용하여** 목록을 필터링할 수 있습니다. 다음은 예입니다.
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    이 명령은 표시 이름이 "John"으로 시작하는 사용자 계정만 나열합니다.
    
- 할당할 역할
    
    사용자 계정에 할당할 수 있는 사용 가능한 역할 목록을 표시하기 위해 다음 명령을 사용하세요.
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

계정의 UPN과 역할 이름을 지정한 후 다음 명령을 사용하여 계정에 역할을 할당합니다.
  
```powershell
$upnName="<The UPN of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

명령을 복사하여 명령에 붙여 메모장. 변수 **및 $upnName** **$roleName.** 설명 텍스트를 해당 값으로 바 대체합니다. 문자를 \< and > 제거하 고 인용 부호를 유지 합니다. 수정된 줄을 실행하기 위해 Microsoft Azure Active Directory 모듈에 Windows PowerShell 붙여 넣습니다. 또는 ISE를 사용하여 WINDOWS POWERSHELL 있습니다.
  
완성된 명령 집합의 예는 다음과 같습니다.
  
```powershell
$upnName="scottw@contoso.com"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

### <a name="multiple-role-changes"></a>여러 역할 변경

여러 역할 변경의 경우 다음 정보를 결정하십시오.
  
- 구성할 사용자 계정 이전 섹션의 메서드를 사용하여 표시 이름 또는 UPNS 집합을 수집할 수 있습니다.
    
- 각 사용자 계정에 할당할 역할 사용자 계정에 할당할 수 있는 사용 가능한 역할 목록을 표시하기 위해 다음 명령을 사용하세요.
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

그런 다음 표시 이름 또는 UPN 및 역할 이름 필드가 있는 CSV(콤보로 구분된 값) 텍스트 파일을 생성합니다. 이 작업을 쉽게 할 수 있는 Microsoft Excel.

표시 이름의 예는 다음과 같습니다.
  
```powershell
DisplayName,RoleName
"Belinda Newman","Billing Administrator"
"Scott Wallace","SharePoint Service Administrator"
```

그런 다음 CSV 파일의 위치를 입력하고 PowerShell 명령 프롬프트에서 결과 명령을 실행합니다.
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach {Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser | Where DisplayName -eq $_.DisplayName).UserPrincipalName -RoleName $_.RoleName }

```

UPNS의 예는 다음과 같습니다.
  
```powershell
UserPrincipalName,RoleName
"belindan@contoso.com","Billing Administrator"
"scottw@contoso.com","SharePoint Service Administrator"
```

그런 다음 CSV 파일의 위치를 입력하고 PowerShell 명령 프롬프트에서 결과 명령을 실행합니다.
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach { Add-MsolRoleMember -RoleMemberEmailAddress $_.UserPrincipalName -RoleName $_.RoleName }

```

## <a name="see-also"></a>참고 항목

- [PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
- [PowerShell로 Microsoft 365 관리](manage-microsoft-365-with-microsoft-365-powershell.md)
- [Microsoft 365용 PowerShell 시작](getting-started-with-microsoft-365-powershell.md)
