---
title: PowerShell을 사용하여 Microsoft 365 계정에서 라이선스 제거
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/23/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
- LIL_Placement
- O365ITProTrain
ms.assetid: e7e4dc5e-e299-482c-9414-c265e145134f
description: PowerShell을 사용하여 이전에 사용자에게 할당된 Microsoft 365 라이선스를 제거하는 방법에 대해 설명
ms.openlocfilehash: 4aa40b4405dda07eea34151bd2fddcde0030e8b8
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60214144"
---
# <a name="remove-microsoft-365-licenses-from-user-accounts-with-powershell"></a>PowerShell을 사용하여 Microsoft 365 계정에서 라이선스 제거

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

>[!Note]
>[사용자 계정에서](../admin/manage/remove-licenses-from-users.md) 라이선스를 제거하는 방법을 Microsoft 365 관리 센터. 추가 리소스 목록은 사용자 및 그룹 [관리를 참조하세요.](/admin)
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 모듈용 Azure Active Directory PowerShell 사용하기

먼저 [테넌트 Microsoft 365 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)

다음으로, 이 명령을 사용하여 테넌트에 대한 라이선스 계획을 나열합니다.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

그런 다음 라이선스를 제거할 계정의 로그인 이름을 UPN(사용자 계정 이름)이라고도 합니다.

마지막으로 사용자 로그인 및 라이선스 계획 이름을 지정하고 "<" 및 ">" 문자를 제거한 다음 이러한 명령을 실행합니다.

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$License.RemoveLicenses = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $license
```

특정 사용자 계정에 대한 모든 라이선스를 제거하려면 사용자 로그인 이름을 지정하고 "<" 및 ">" 문자를 제거한 다음 다음 명령을 실행합니다.

```powershell
$userUPN="<user sign-in name (UPN)>"
$userList = Get-AzureADUser -ObjectID $userUPN
$Skus = $userList | Select -ExpandProperty AssignedLicenses | Select SkuID
if($userList.Count -ne 0) {
    if($Skus -is [array])
    {
        $licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
        for ($i=0; $i -lt $Skus.Count; $i++) {
            $Licenses.RemoveLicenses +=  (Get-AzureADSubscribedSku | Where-Object -Property SkuID -Value $Skus[$i].SkuId -EQ).SkuID   
        }
        Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
    } else {
        $licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
        $Licenses.RemoveLicenses =  (Get-AzureADSubscribedSku | Where-Object -Property SkuID -Value $Skus.SkuId -EQ).SkuID
        Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
    }
}
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell용 Microsoft Azure Active Directory 모듈 사용하기

먼저 [테넌트 Microsoft 365 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)
   
라이센스 계획 (**AccountSkuID**) 조직에 대 한 정보는 다음 항목을 참조.
    
  - [PowerShell을 통해 라이선스 및 서비스 보기](view-licenses-and-services-with-microsoft-365-powershell.md)
    
  - [PowerShell을 통해 계정 라이선스 및 서비스 세부 정보 보기](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
_-All_ 매개 변수를 사용하지 않고 **Get-MsolUser** cmdlet을 사용하는 경우 처음 500개의 계정만 반환됩니다.
    
### <a name="removing-licenses-from-user-accounts"></a>사용자 계정에서 라이선스 제거

기존 사용자 계정에서 라이센스를 제거 하려면 다음 구문을 사용 합니다.
  
```powershell
Set-MsolUserLicense -UserPrincipalName <Account> -RemoveLicenses "<AccountSkuId1>", "<AccountSkuId2>"...
```

>[!Note]
>PowerShell Core는 Windows PowerShell용 Microsoft Azure Active Directory 모듈 및 이름에 **Msol** 이 있는 cmdlet을 지원하지 않습니다. 이러한 cmdlet을 계속 사용하려면 Windows PowerShell에서 이를 실행해야 합니다.
>

이 예에서는 사용자 계정에서 **litwareinc:ENTERPRISEPACK(Office 365 Enterprise** E3) 라이선스를 BelindaN@litwareinc.com.
  
```powershell
Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -RemoveLicenses "litwareinc:ENTERPRISEPACK"
```

>[!Note]
>이 cmdlet을 사용하여 취소된 라이선스에서 사용자를 `Set-MsolUserLicense` 배포 *취소할* 수는 없습니다. 사용자 계정의 각 사용자 계정에 대해 개별적으로 이 작업을 Microsoft 365 관리 센터.
>

기존 라이선스 사용자 그룹에서 모든 라이선스를 제거하려면 다음 방법 중 하나를 사용 합니다.
  
- **기존 계정 특성을 기준으로 계정 필터링** 이 작업을 위해 다음 구문을 사용 합니다.
    
```powershell
$userArray = Get-MsolUser -All <FilterableAttributes> | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

이 예에서는 미국 판매 부서의 모든 사용자 계정에서 모든 라이선스를 제거합니다.
    
```powershell
$userArray = Get-MsolUser -All -Department "Sales" -UsageLocation "US" | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

- **특정 라이선스에 대해 특정 계정 목록 사용** 이 작업을 수행하기 위해 다음 단계를 수행합니다.
    
1. 만들고 다음과 같이 각 줄에 한 계정에 포함 된 텍스트 파일을 저장 합니다.
    
  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

2. 다음 구문을 사용합니다.
    
  ```powershell
  $x=Get-Content "<FileNameAndPath>"
  for ($i=0; $i -lt $x.Count; $i++)
  {
  Set-MsolUserLicense -UserPrincipalName $x[$i] -RemoveLicenses "<AccountSkuId1>","<AccountSkuId2>"...
  }
  ```
이 예제에서는 텍스트 파일 C:\My Office 365 Enterprise에 정의된 사용자 계정에서 **litwareinc:ENTERPRISEPACK(Office 365 Enterprise** E3) 라이선스를 Documents\Accounts.txt.
    
  ```powershell
  $x=Get-Content "C:\My Documents\Accounts.txt"
  for ($i=0; $i -lt $x.Count; $i++)
  {
  Set-MsolUserLicense -UserPrincipalName $x[$i] -RemoveLicenses "litwareinc:ENTERPRISEPACK"
  }
  ```

모든 기존 사용자 계정에서 모든 라이선스를 제거하려면 다음 구문을 사용 합니다.
  
```powershell
$userArray = Get-MsolUser -All | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

라이선스를 회수하는 또 다른 방법은 사용자 계정을 삭제하는 것입니다. 자세한 내용은 [PowerShell을 통해 사용자 계정](delete-and-restore-user-accounts-with-microsoft-365-powershell.md)삭제 및 복원을 참조하세요.
  
## <a name="see-also"></a>참고 항목

[PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[PowerShell로 Microsoft 365 관리](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365 용 PowerShell 시작](getting-started-with-microsoft-365-powershell.md)