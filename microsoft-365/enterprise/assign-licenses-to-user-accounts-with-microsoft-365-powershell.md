---
title: PowerShell을 사용하여 사용자 계정에 Microsoft 365 라이선스 할당
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Office_Other
- LIL_Placement
- PowerShell
- O365ITProTrain
- seo-marvel-apr2020
ms.assetid: ba235f4f-e640-4360-81ea-04507a3a70be
search.appverid:
- MET150
description: 이 문서에서는 PowerShell을 사용하여 허가되지 않은 사용자에게 Microsoft 365 라이선스를 할당하는 방법을 알아봅니다.
ms.openlocfilehash: 6d7e005aff018394810082de57c68ea289057f8e
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572624"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts-with-powershell"></a>PowerShell을 사용하여 사용자 계정에 Microsoft 365 라이선스 할당

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

사용자는 라이선스 계획에서 계정이 라이선스를 할당할 때까지 Microsoft 365 서비스를 사용할 수 없습니다. PowerShell을 사용하여 라이선스를 허가되지 않은 계정에 신속하게 할당할 수 있습니다. 

사용자 계정은 먼저 위치를 할당해야 합니다. 위치를 지정하는 것은 [Microsoft 365 관리 센터에서](../admin/add-users/add-users.md)새 사용자 계정을 만드는 데 필요한 부분입니다. 

온-프레미스 Active Directory 도메인 서비스에서 동기화된 계정에는 기본적으로 지정된 위치가 없습니다. 다음 계정에서 이러한 계정에 대한 위치를 구성할 수 있습니다.

- Microsoft 365 관리 센터
 - [PowerShell](configure-user-account-properties-with-microsoft-365-powershell.md)
 - [Azure 포털(활성](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) **디렉터리**  >  **사용자** > 사용자 계정 > **프로필**  >  **연락처 정보** 국가 또는  >  **지역)입니다.**

>[!Note]
>Microsoft 365 관리 센터를 사용하여 [사용자 계정에 라이선스를 할당하는 방법을 알아보세요.](../admin/manage/assign-licenses-to-users.md) 추가 리소스 목록은 사용자 [및 그룹 관리를](../admin/add-users/index.yml)참조하십시오.
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 모듈용 Azure Active Directory PowerShell 사용하기

먼저 [Microsoft 365 테넌트에 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  

다음으로 이 명령을 통해 테넌트의 라이센스 계획을 나열합니다.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

그런 다음 사용자 주이름(UPN)이라고도 하는 라이선스를 추가할 계정의 로그인 이름을 가져옵니다.

다음으로 사용자 계정에 사용 위치가 할당되어 있는지 확인합니다.

```powershell
Get-AzureADUser -ObjectID <user sign-in name (UPN)> | Select DisplayName, UsageLocation
```

사용 위치가 할당되지 않은 경우 다음 명령을 가진 위치를 할당할 수 있습니다.

```powershell
$userUPN="<user sign-in name (UPN)>"
$userLoc="<ISO 3166-1 alpha-2 country code>"
Set-AzureADUser -ObjectID $userUPN -UsageLocation $userLoc
```

마지막으로 사용자 로그인 이름 및 라이센스 계획 이름을 지정하고 이러한 명령을 실행합니다.

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell용 Microsoft Azure Active Directory 모듈 사용하기

이 모듈의 기능이 Graph 모듈의 최신 [Azure Active Directory PowerShell에서](/powershell/azuread/v2/azureactivedirectory) 사용할 수 있는 경우 이 모듈을 비하하기 시작합니다. 새 PowerShell 스크립트를 만드는 고객에게 이 모듈 대신 최신 모듈을 사용하는 것이 좋습니다.

먼저 [Microsoft 365 테넌트에 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

명령을 `Get-MsolAccountSku` 실행하여 사용 가능한 라이선스 계획과 조직의 각 계획에서 사용 가능한 라이선스 수를 확인합니다. 각 플랜에서 사용 가능한 라이센스 수는 **ActiveUnits**  -  **경고단위**  -  **사용 단위입니다.** 라이선스 계획, 라이센스 및 서비스에 대한 자세한 내용은 [PowerShell을 사용해 라이선스 및 서비스 보기를](view-licenses-and-services-with-microsoft-365-powershell.md)참조하세요.

>[!Note]
>PowerShell Core는 Windows PowerShell용 Microsoft Azure Active Directory 모듈 및 이름에 **Msol** 이 있는 cmdlet을 지원하지 않습니다. 이러한 cmdlet을 계속 사용하려면 Windows PowerShell에서 이를 실행해야 합니다.
>

조직에서 허가되지 않은 계정을 찾으려면 이 명령을 실행합니다.

```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

**사용 위치** 속성이 유효한 ISO 3166-1 알파-2 국가 코드로 설정된 사용자 계정에만 라이선스를 할당할 수 있습니다. 예를 들어, 미국에 대 한 미국, 그리고 프랑스에 대 한 FR. 일부 Microsoft 365 서비스는 특정 국가에서 사용할 수 없습니다. 자세한 내용은 [라이센스 제한 정보 참조.](https://go.microsoft.com/fwlink/p/?LinkId=691730)
    
**사용 위치** 값이 없는 계정을 찾으려면 이 명령을 실행합니다.

```powershell
Get-MsolUser -All | where {$_.UsageLocation -eq $null}
```

계정에서 **사용 위치** 값을 설정하려면 이 명령을 실행합니다.

```powershell
Set-MsolUser -UserPrincipalName "<Account>" -UsageLocation <CountryCode>
```

예시:

```powershell
Set-MsolUser -UserPrincipalName "belindan@litwareinc.com" -UsageLocation US
```
    
**-All** 매개 변수를 사용하지 않고 **Get-MsolUser** cmdlet을 사용하는 경우 처음 500개의 계정만 반환됩니다.

### <a name="assigning-licenses-to-user-accounts"></a>사용자 계정에 라이선스 할당
    
사용자에게 라이선스를 할당하려면 PowerShell에서 다음 명령을 사용합니다.
  
```powershell
Set-MsolUserLicense -UserPrincipalName "<Account>" -AddLicenses "<AccountSkuId>"
```

이 예제에서는 **litwareinc:ENTERPRISEPACK(Office 365 Enterprise** E3) 라이선스 계획에서 라이선스를 라이선스가 없는 사용자 **벨린단 \@ litwareinc.com 할당합니다.**
  
```powershell
Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"
```

허가되지 않은 모든 사용자에게 라이선스를 할당하려면 이 명령을 실행합니다.
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly [<FilterableAttributes>] | Set-MsolUserLicense -AddLicenses "<AccountSkuId>"
```
  
>[!Note]
>동일한 라이센스 제도에서 여러 라이센스 사용자 지정할 수 없습니다. 반환 하는 순서 대로 사용자에 게 라이선스 할당 된 충분 한 사용 가능한 라이센스를 설정 하지 않은 경우는 **Get-MsolUser** cmdlet 사용 가능한 라이센스가 실행 될 때까지.
>

이 예제에서는 **litwareinc:ENTERPRISEPACK(Office 365 Enterprise** E3) 라이선스 계획의 라이선스를 모든 무면허 사용자에게 할당합니다.
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```

이 예제에서는 미국 영업 부서의 라이선스가 없는 사용자에게 동일한 라이선스를 할당합니다.
  
```powershell
Get-MsolUser -All -Department "Sales" -UsageLocation "US" -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```
  
## <a name="move-a-user-to-a-different-subscription-license-plan-with-the-azure-active-directory-powershell-for-graph-module"></a>Graph 모듈에 대한 Azure Active Directory PowerShell을 사용하여 사용자를 다른 구독(라이센스 계획)으로 이동합니다.

먼저 [Microsoft 365 테넌트에 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  
그런 다음 사용자 주이름(UPN)이라고도 하는 구독을 전환하려는 사용자 계정의 로그인 이름을 가져옵니다.

다음으로 이 명령을 가진 테넌트의 구독(라이센스 계획)을 나열합니다.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

그런 다음 사용자 계정이 현재 이러한 명령과 함께 있는 구독을 나열합니다.

```powershell
$userUPN="<user account UPN>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

사용자가 현재 가지고 있는 구독(FROM 구독) 및 사용자가 이동하는 구독(TO 구독)을 식별합니다.

마지막으로 TO 및 FROM 구독 이름(SKU 부품 번호)을 지정하고 이러한 명령을 실행합니다.

```powershell
$subscriptionFrom="<SKU part number of the current subscription>"
$subscriptionTo="<SKU part number of the new subscription>"
# Unassign
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$license.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionFrom -EQ).SkuID
$licenses.AddLicenses = $license
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
$licenses.AddLicenses = @()
$licenses.RemoveLicenses =  (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionFrom -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
# Assign
$license.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionTo -EQ).SkuID
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$licenses.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
```

이러한 명령을 통해 사용자 계정의 구독 변경 사항을 확인할 수 있습니다.

```powershell
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="see-also"></a>참고 항목

[PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[PowerShell로 Microsoft 365 관리](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365 용 PowerShell 시작](getting-started-with-microsoft-365-powershell.md)
