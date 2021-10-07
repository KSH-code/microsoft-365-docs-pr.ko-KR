---
title: PowerShell을 Microsoft 365 사용자 계정 만들기
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
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
- O365ITProTrain
- seo-marvel-apr2020
ms.assetid: 6770c5fa-b886-4512-8c67-ffd53226589e
description: PowerShell을 사용하여 사용자 계정을 개별적으로 또는 여러 개 Microsoft 365 방법
ms.openlocfilehash: 7396e98e597491910b639e5a0d0c57b8f685bc02
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60172002"
---
# <a name="create-microsoft-365-user-accounts-with-powershell"></a>PowerShell을 Microsoft 365 사용자 계정 만들기

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

PowerShell을 사용하여 여러 계정을 Microsoft 365 효율적으로 사용자 계정을 만들 수 있습니다.

PowerShell에서 사용자 계정을 만들 때 특정 계정 속성은 항상 필요합니다. 다른 속성은 필수는 아니며 중요합니다. 다음 표를 참고하십시오.
  
|**속성 이름**|**필수 여부**|**설명**|
|:-----|:-----|:-----|
|**DisplayName** <br/> |예  <br/> |이 이름은 Microsoft 365 서비스에서 사용되는 표시 이름입니다. 예를 들어 *Caleb Sills와 같습니다.* <br/> |
|**UserPrincipalName** <br/> |예  <br/> |이 이름은 Microsoft 365 서비스에 로그인하는 데 사용되는 계정 이름입니다. 예를 들어 *CalebS는 \@ contoso.onmicrosoft.com.*  <br/> |
|**FirstName** <br/> |아니요  <br/> ||
|**LastName** <br/> |아니요  <br/> ||
|**LicenseAssignment** <br/> |아니요  <br/> |사용 가능한 라이선스가 사용자 계정에 할당되는 라이선스 계획(라이선스 계획 또는 SKU라고도 알려지기)입니다. 라이선스는 Microsoft 365 사용할 수 있는 서비스를 정의합니다. 계정을 만들 때 사용자에게 라이선스를 할당할 수 없지만 계정에는 Microsoft 365 액세스하는 라이선스가 있어야 합니다. 사용자 계정을 만든 후 30일 동안 라이선스를 부여해야 합니다. |
|**Password** <br/> |아니요  <br/> | 암호를 지정 하지 않으면 사용자 계정에 임의의 암호를 할당 하 고 암호는 명령의 결과에 표시 됩니다. 암호를 지정하는 경우 소문자, 대문자, 숫자 및 기호 형식의 8~16개 ASCII 텍스트 문자를 지정해야 합니다.<br/> |
|**UsageLocation** <br/> |아니요  <br/> |유효한 ISO 3166-1 alpha-2 국가 코드입니다. 예를 들어 *미국은 미국,* *프랑스의 경우 FR입니다.* 일부 Microsoft 365 서비스를 특정 국가에서 사용할 수 없는 경우에는 이 값을 제공하는 것이 중요합니다. 계정이 이 값을 구성하지 않으면 사용자 계정에 라이선스를 할당할 수 없습니다. 자세한 내용은 라이선스 제한 [정보를 참조하세요.](https://go.microsoft.com/fwlink/p/?LinkId=691730)<br/> |

>[!Note]
>[다음을 사용하여 사용자](../admin/add-users/add-users.md) 계정을 만드는 방법을 Microsoft 365 관리 센터.
> 
> 추가 리소스 목록은 사용자 및 그룹 [관리를 참조하세요.](/admin)
>   

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 모듈용 Azure Active Directory PowerShell 사용하기

먼저 [테넌트 Microsoft 365 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)

연결한 후 다음 구문을 사용하여 개별 계정을 만들 수 있습니다.
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="<user account password>"
New-AzureADUser -DisplayName "<display name>" -GivenName "<first name>" -SurName "<last name>" -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -MailNickName <mailbox name> -PasswordProfile $PasswordProfile -AccountEnabled $true
```

이 예에서는 미국 사용자 *Caleb Sills에* 대한 계정을 만듭니다.
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="3Rv0y1q39/chsy"
New-AzureADUser -DisplayName "Caleb Sills" -GivenName "Caleb" -SurName "Sills" -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -MailNickName calebs -PasswordProfile $PasswordProfile -AccountEnabled $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell용 Microsoft Azure Active Directory 모듈 사용하기

먼저 [테넌트 Microsoft 365 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

### <a name="create-an-individual-user-account"></a>개별 사용자 계정 만들기

개별 계정을 만들려면 다음 구문을 사용합니다.
  
```powershell
New-MsolUser -DisplayName <display name> -FirstName <first name> -LastName <last name> -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -LicenseAssignment <licensing plan name> [-Password <Password>]
```

>[!Note]
>PowerShell Core는 이름에 *Msol이* Microsoft Azure Active Directory cmdlet을 Windows PowerShell 모듈용 Windows PowerShell 모듈을 지원하지 않습니다. Windows PowerShell에서 이러한 cmdlet을 실행합니다.
>

사용 가능한 라이선스 계획 이름을 열거하려면 이 명령을  사용합니다:

````powershell
Get-MsolAccountSku
````

이 예에서는 미국 사용자 *Caleb Sills에* 대한 계정을 만들고 (Office 365 Enterprise E3) 라이선스 계획에서 라이선스를 `contoso:ENTERPRISEPACK` 할당합니다.
  
```powershell
New-MsolUser -DisplayName "Caleb Sills" -FirstName Caleb -LastName Sills -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -LicenseAssignment contoso:ENTERPRISEPACK
```

### <a name="create-multiple-user-accounts"></a>다중 사용자 계정 만들기

1. 필요한 사용자 계정 정보를 포함하는 쉼표로 구분 된 값(CSV) 파일을 만듭니다. 예를 들면 다음과 같습니다.

     ```powershell
     UserPrincipalName,FirstName,LastName,DisplayName,UsageLocation,AccountSkuId
     ClaudeL@contoso.onmicrosoft.com,Claude,Loiselle,Claude Loiselle,US,contoso:ENTERPRISEPACK
     LynneB@contoso.onmicrosoft.com,Lynne,Baxter,Lynne Baxter,US,contoso:ENTERPRISEPACK
     ShawnM@contoso.onmicrosoft.com,Shawn,Melendez,Shawn Melendez,US,contoso:ENTERPRISEPACK
     ```

   >[!NOTE]
   >CSV 파일의 첫 번째 행에서 열 이름과 순서는 임의로 표시됩니다. 그러나 파일의 나머지에 있는 데이터의 순서가 열 이름의 순서와 일치하는지 확인하십시오. PowerShell에서 매개 변수 값에 대한 열 이름을 Microsoft 365 있습니다.
    
2. 다음 구문을 사용합니다.
    
    ```powershell
     Import-Csv -Path <Input CSV File Path and Name> | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId [-Password $_.Password]} | Export-Csv -Path <Output CSV File Path and Name>
    ```

   이 예에서는 *C:\My* Documents\NewAccounts.csv파일에서 사용자 계정을 만들고 결과를 *C:\My* Documents\NewAccountResults.csv.
    
    ```powershell
    Import-Csv -Path "C:\My Documents\NewAccounts.csv" | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId} | Export-Csv -Path "C:\My Documents\NewAccountResults.csv"
    ```

3. 결과 볼 수 있는 출력 파일을 검토 합니다. 암호를 지정하지 않았기 때문에 생성된 임의 암호가 Microsoft 365 파일에 표시됩니다.
    
## <a name="see-also"></a>참고 항목

[PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[PowerShell로 Microsoft 365 관리](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365 용 PowerShell 시작](getting-started-with-microsoft-365-powershell.md)