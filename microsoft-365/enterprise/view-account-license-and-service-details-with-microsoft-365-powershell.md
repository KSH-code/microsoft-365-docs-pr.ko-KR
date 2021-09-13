---
title: PowerShell을 Microsoft 365 계정 라이선스 및 서비스 세부 정보 보기
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 07/17/2020
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
- PowerShell
- Ent_Office_Other
- LIL_Placement
ms.assetid: ace07d8a-15ca-4b89-87f0-abbce809b519
description: PowerShell을 사용하여 사용자에게 할당된 Microsoft 365 서비스를 확인하는 방법에 대해 설명
ms.openlocfilehash: 2c450c0697dced43f974087f6c0453e4b761914b
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59210415"
---
# <a name="view-microsoft-365-account-license-and-service-details-with-powershell"></a>PowerShell을 Microsoft 365 계정 라이선스 및 서비스 세부 정보 보기

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

Microsoft 365 라이선스 계획(SKUS 또는 Microsoft 365 계획이라고도 하는 라이선스)을 통해 사용자는 해당 계획에 대해 정의된 Microsoft 365 서비스에 액세스할 수 있습니다. 그러나 사용자는 현재 할당된 라이선스에서 사용할 수 있는 모든 서비스에 액세스하지 못할 수도 있습니다. PowerShell을 사용하여 사용자 Microsoft 365 서비스 상태를 볼 수 있습니다. 

라이선스 계획, 라이선스 및 서비스에 대한 자세한 내용은 PowerShell을 통해 라이선스 및 서비스 [보기를 참조하세요.](view-licenses-and-services-with-microsoft-365-powershell.md)

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 모듈용 Azure Active Directory PowerShell 사용하기

먼저 [테넌트 Microsoft 365 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  
다음으로, 이 명령을 사용하여 테넌트에 대한 라이선스 계획을 나열합니다.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

다음 명령을 사용하여 각 라이선스 계획에서 사용할 수 있는 서비스를 나열합니다.

```powershell
$allSKUs=Get-AzureADSubscribedSku
$licArray = @()
for($i = 0; $i -lt $allSKUs.Count; $i++)
{
$licArray += "Service Plan: " + $allSKUs[$i].SkuPartNumber
$licArray +=  Get-AzureADSubscribedSku -ObjectID $allSKUs[$i].ObjectID | Select -ExpandProperty ServicePlans
$licArray +=  ""
}
$licArray
```

다음 명령을 사용하여 사용자 계정에 할당된 라이선스를 나열합니다.

```powershell
$userUPN="<user account UPN, such as belindan@contoso.com>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell용 Microsoft Azure Active Directory 모듈 사용하기

먼저 [테넌트 Microsoft 365 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

다음으로, 이 명령을 실행하여 조직에서 사용할 수 있는 라이선스 계획을 나열합니다. 

```powershell
Get-MsolAccountSku
```
>[!Note]
>PowerShell Core는 Windows PowerShell용 Microsoft Azure Active Directory 모듈 및 이름에 **Msol** 이 있는 cmdlet을 지원하지 않습니다. 이러한 cmdlet을 계속 사용하려면 Windows PowerShell에서 이를 실행해야 합니다.
>

그런 다음 이 명령을 실행하여 각 라이선스 계획에서 사용할 수 있는 서비스와 서비스가 나열되는 순서(인덱스 번호)를 나열합니다.

```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "<AccountSkuId>"}).ServiceStatus
```
  
이 명령을 사용하여 사용자에게 할당된 라이선스와 라이선스가 나열되는 순서(인덱스 번호)를 나열합니다.

```powershell
Get-MsolUser -UserPrincipalName <user account UPN> | Format-List DisplayName,Licenses
```

### <a name="to-view-services-for-a-user-account"></a>사용자 계정에 대한 서비스를 보기 위해

사용자가 액세스할 수 있는 Microsoft 365 모든 서비스 보기 위해 다음 구문을 사용 합니다.
  
```powershell
(Get-MsolUser -UserPrincipalName <user account UPN>).Licenses[<LicenseIndexNumber>].ServiceStatus
```

이 예에서는 사용자가 액세스할 수 있는 BelindaN@litwareinc.com 보여줍니다. 사용자의 계정에 할당된 모든 라이선스와 관련된 서비스를 표시합니다.
  
```powershell
(Get-MsolUser -UserPrincipalName belindan@litwareinc.com).Licenses.ServiceStatus
```

이 예제에서는 사용자 BelindaN@litwareinc.com이 계정에 할당된 첫 번째 라이선스(인덱스 번호: 0)에서 액세스할 수 있는 서비스를 표시합니다.
  
```powershell
(Get-MsolUser -UserPrincipalName belindan@litwareinc.com).Licenses[0].ServiceStatus
```

여러 라이선스가 할당된 사용자에 대한 모든 서비스를 보고 다음 구문을 사용 합니다.

```powershell
$userUPN="<user account UPN>"
$AllLicenses=(Get-MsolUser -UserPrincipalName $userUPN).Licenses
$licArray = @()
for($i = 0; $i -lt $AllLicenses.Count; $i++)
{
$licArray += "License: " + $AllLicenses[$i].AccountSkuId
$licArray +=  $AllLicenses[$i].ServiceStatus
$licArray +=  ""
}
$licArray
```
 
## <a name="see-also"></a>참고 항목

[PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[PowerShell로 Microsoft 365 관리](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365 용 PowerShell 시작](getting-started-with-microsoft-365-powershell.md)
