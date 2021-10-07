---
title: PowerShell을 Microsoft 365 서비스에 액세스하지 않도록 설정
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 07/27/2020
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
- Ent_Office_Other
- PowerShell
- LIL_Placement
- seo-marvel-apr2020
ms.assetid: 264f4f0d-e2cd-44da-a9d9-23bef250a720
description: 이 문서에서는 PowerShell을 사용하여 사용자에 대한 Microsoft 365 액세스를 사용하지 않도록 설정하는 방법을 학습합니다.
ms.openlocfilehash: bce02c40bf6ca99d74b8747fb0c5eb5c0b485888
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60173466"
---
# <a name="disable-access-to-microsoft-365-services-with-powershell"></a>PowerShell을 Microsoft 365 서비스에 액세스하지 않도록 설정

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

라이선스 Microsoft 365 라이선스가 할당된 경우 해당 Microsoft 365 라이선스에서 사용자에게 라이선스 서비스를 사용할 수 있습니다. 그러나 사용자가 액세스할 수 있는 Microsoft 365 서비스를 제어할 수 있습니다. 예를 들어 라이선스에서 SharePoint Online 서비스에 대한 액세스를 허용하는 경우에도 라이선스에 대한 액세스를 사용하지 않도록 설정할 수 있습니다. PowerShell을 사용하여 특정 라이선스 계획에 대해 원하는 수의 서비스에 대한 액세스를 사용하지 않도록 설정할 수 있습니다.

- 개별 계정.
- 계정 그룹입니다.
- 조직의 모든 계정

>[!Note]
>다른 Microsoft 365 사용하는 경우 지정된 서비스를 사용할 수 없는 서비스 종속성에 따라 다른 서비스가 사용되지 않도록 할 수 있습니다.
>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell용 Microsoft Azure Active Directory 모듈 사용하기

먼저 [테넌트 Microsoft 365 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

다음으로, 다음 명령을 사용하여 사용 가능한 라이선스 계획(AccountSkuIds라고도 합니다.

```powershell
Get-MsolAccountSku | Select AccountSkuId | Sort AccountSkuId
```

>[!Note]
>PowerShell Core는 Windows PowerShell용 Microsoft Azure Active Directory 모듈 및 이름에 **Msol** 이 있는 cmdlet을 지원하지 않습니다. 이러한 cmdlet을 계속 사용하려면 Windows PowerShell에서 이를 실행해야 합니다.
>

자세한 내용은 PowerShell을 통해 라이선스 및 [서비스 보기를 참조하세요.](view-licenses-and-services-with-microsoft-365-powershell.md)
    
이 항목의 절차의 전후 결과를 확인하려면 PowerShell을 통해 계정 라이선스 및 서비스 세부 정보 [보기를 참조하세요.](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
이 항목에서 설명하는 절차를 자동화하는 PowerShell 스크립트를 사용할 수 있습니다. 특히 이 스크립트를 사용하면 Sway를 포함하여 Microsoft 365 조직에서 서비스를 보고 사용하지 않도록 설정할 수 있습니다. 자세한 내용은 [PowerShell을 통해 Sway에 대한 액세스 사용 안 을 참조하세요.](disable-access-to-sway-with-microsoft-365-powershell.md)
    
    
### <a name="disable-specific-microsoft-365-services-for-specific-users-for-a-specific-licensing-plan"></a>특정 Microsoft 365 사용자에 대해 특정 라이선스 서비스 사용 안 하도록 설정
  
특정 라이선스 계획에 Microsoft 365 사용자에 대해 특정 Microsoft 365 서비스 집합을 사용하지 않도록 설정하기 위해 다음 단계를 수행합니다.
  
#### <a name="step-1-identify-the-undesired-services-in-the-licensing-plan-by-using-the-following-syntax"></a>1단계: 다음 구문을 사용하여 라이선싱 계획에서 원하지하는 서비스를 식별합니다.
    
```powershell
$LO = New-MsolLicenseOptions -AccountSkuId <AccountSkuId> -DisabledPlans "<UndesiredService1>", "<UndesiredService2>"...
```

다음 예제에서는 이름이 E3인 라이선스 계획에서 Office 및 SharePoint Online 서비스를 사용하지 않도록 설정하는 **LicenseOptions** 개체를 Office 365 Enterprise `litwareinc:ENTERPRISEPACK` 만듭니다.
    
```powershell
$LO = New-MsolLicenseOptions -AccountSkuId "litwareinc:ENTERPRISEPACK" -DisabledPlans "SHAREPOINTWAC", "SHAREPOINTENTERPRISE"
```

#### <a name="step-2-use-the-licenseoptions-object-from-step-1-on-one-or-more-users"></a>2단계: 하나 이상의 사용자에 대해 1단계의 **LicenseOptions** 개체를 사용합니다.
    
서비스를 사용하지 않도록 설정한 새 계정을 만들하려면 다음 구문을 사용하세요.
    
```powershell
New-MsolUser -UserPrincipalName <Account> -DisplayName <DisplayName> -FirstName <FirstName> -LastName <LastName> -LicenseAssignment <AccountSkuId> -LicenseOptions $LO -UsageLocation <CountryCode>
```

다음 예제에서는 라이선스를 할당하고 1단계에 설명된 서비스를 사용하지 않도록 설정하는 Allie Bellew에 대한 새 계정을 만듭니다.
    
```powershell
New-MsolUser -UserPrincipalName allieb@litwareinc.com -DisplayName "Allie Bellew" -FirstName Allie -LastName Bellew -LicenseAssignment litwareinc:ENTERPRISEPACK -LicenseOptions $LO -UsageLocation US
```

For more information about creating user accounts in PowerShell for Microsoft 365, [see Create user accounts with PowerShell](create-user-accounts-with-microsoft-365-powershell.md).
    
기존 라이선스 사용자에 대해 서비스를 사용하지 않도록 설정하기 위해 다음 구문을 사용 합니다.
    
```powershell
Set-MsolUserLicense -UserPrincipalName <Account> -LicenseOptions $LO
```

이 예에서는 사용자 계정의 서비스를 사용하지 않도록 BelindaN@litwareinc.com.
    
```powershell
Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -LicenseOptions $LO
```

1단계에서 설명하는 모든 기존 라이선스 사용자에 대해 설명하는 서비스를 사용하지 않도록 설정하기 위해 **Get-MsolAccountSku** cmdlet 표시에서 Microsoft 365 계획의 이름을 지정하고(예: **litwareinc:ENTERPRISEPACK)** 다음 명령을 실행합니다.
    
```powershell
$acctSKU="<AccountSkuId>"
$AllLicensed = Get-MsolUser -All | Where {$_.isLicensed -eq $true -and $_.licenses.AccountSku.SkuPartNumber -contains ($acctSKU).Substring($acctSKU.IndexOf(":")+1, $acctSKU.Length-$acctSKU.IndexOf(":")-1)}
$AllLicensed | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

 _All_ 매개 변수를 사용하지 않고 **Get-MsolUser** cmdlet을 사용하면 처음 500개 사용자 계정만 반환됩니다.

기존 사용자 그룹에 대해 서비스를 사용하지 않도록 설정하기 위해 다음 방법 중 하나를 사용하여 사용자를 식별합니다.
    
**메서드 1. 기존 계정 특성을 기준으로 계정 필터링** 

그렇게 하려면 다음 구문을 사용합니다.
    
```powershell
$x = Get-MsolUser -All <FilterableAttributes>
$x | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

다음 예에서는 미국 판매 부서의 사용자에 대해 서비스를 사용하지 않도록 설정합니다.
    
```powershell
$USSales = Get-MsolUser -All -Department "Sales" -UsageLocation "US"
$USSales | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

**방법 2: 특정 계정 목록 사용** 

이 작업을 수행 하려면 다음 단계를 수행 합니다.
    
1. 다음과 같이 각 줄에 한 계정에 포함 된 텍스트 파일을 만듭니다.
    
   ```powershell
   akol@contoso.com
   tjohnston@contoso.com
   kakers@contoso.com
   ```

   이 예제에서 텍스트 파일은 C: \\ My Documents \\Accounts.txt.
    
2. 다음 명령을 실행합니다.
    
   ```powershell
   Get-Content "C:\My Documents\Accounts.txt" | foreach {Set-MsolUserLicense -UserPrincipalName $_ -LicenseOptions $LO}
   ```

여러 라이선스 계획에 대한 서비스에 대한 액세스를 사용하지 않도록 설정하려는 경우 각 라이선스 계획에 대해 위의 지침을 반복하여 다음 사항을 보장합니다.

- 사용자 계정에 라이선스 계획이 할당되어 있습니다.
- 사용하지 않도록 설정할 서비스는 라이선스 계획에서 사용할 수 있습니다.

사용자를 Microsoft 365 라이선스 계획에 할당하는 동안 사용자에 대해 Microsoft 365 서비스를 사용하지 않도록 설정하는 경우 사용자 라이선스를 할당하는 동안 서비스에 대한 액세스 사용 안 하도록 [설정을 참조합니다.](disable-access-to-services-while-assigning-user-licenses.md)

### <a name="assign-all-services-in-a-licensing-plan-to-a-user-account"></a>사용자 계정에 라이선스 계획의 모든 서비스 할당

서비스를 사용하지 않도록 설정한 사용자 계정의 경우 다음 명령을 사용하여 특정 라이선스 계획에 대해 모든 서비스를 사용하도록 설정할 수 있습니다.

```powershell
$userUPN="<user account UPN>"
$acctSKU="<AccountSkuId>"
$LO = New-MsolLicenseOptions -AccountSkuId $acctSKU
Set-MsolUserLicense -UserPrincipalName $userUPN -LicenseOptions $LO
```

## <a name="related-topic"></a>관련 항목

[PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[PowerShell로 Microsoft 365 관리](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365 용 PowerShell 시작](getting-started-with-microsoft-365-powershell.md)
