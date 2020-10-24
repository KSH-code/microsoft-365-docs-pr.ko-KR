---
title: PowerShell을 사용 하 여 Microsoft 365 사용자 계정 만들기
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
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
- O365ITProTrain
- seo-marvel-apr2020
ms.assetid: 6770c5fa-b886-4512-8c67-ffd53226589e
description: PowerShell을 사용 하 여 개별 또는 여러 Microsoft 365 사용자 계정을 만드는 방법
ms.openlocfilehash: d96de72ca3e7c4a439665c3ebf751a8fe25ce572
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754213"
---
# <a name="create-microsoft-365-user-accounts-with-powershell"></a>PowerShell을 사용 하 여 Microsoft 365 사용자 계정 만들기

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

Microsoft 365 용 PowerShell을 사용 하 여 여러 계정을 포함 하는 사용자 계정을 효율적으로 만들 수 있습니다.

PowerShell에서 사용자 계정을 만드는 경우에는 특정 계정 속성이 항상 필요 합니다. 다른 속성은 필요 하지 않지만 중요 합니다. 다음 표를 참고하십시오.
  
|**속성 이름**|**필수 여부**|**설명**|
|:-----|:-----|:-----|
|**DisplayName** <br/> |예  <br/> |Microsoft 365 서비스에서 사용 되는 표시 이름입니다. 예를 들면 *Caleb 창턱*입니다. <br/> |
|**UserPrincipalName** <br/> |예  <br/> |Microsoft 365 서비스에 로그인 하는 데 사용 되는 계정 이름입니다. 예를 들면 *CalebS \@ contoso.onmicrosoft.com*입니다.  <br/> |
|**FirstName** <br/> |아니요  <br/> ||
|**LastName** <br/> |아니요  <br/> ||
|**LicenseAssignment** <br/> |아니요  <br/> |사용 가능한 라이선스가 사용자 계정에 할당 되는 라이선스 계획 (라이선스 요금제 또는 SKU 라고도 함)입니다. 라이선스는 계정에 사용할 수 있는 Microsoft 365 서비스를 정의 합니다. 계정을 만들 때 사용자에 게 라이선스를 할당할 필요가 없지만 계정에 Microsoft 365 서비스에 액세스 하기 위한 라이선스가 있어야 합니다. 30 일 내에 사용자 계정을 만든 후 라이선스를 허가 해야 합니다. |
|**Password** <br/> |아니요  <br/> | 암호를 지정 하지 않으면 사용자 계정에 임의의 암호를 할당 하 고 암호는 명령의 결과에 표시 됩니다. 암호를 지정 하는 경우에는 소문자, 대문자, 숫자 및 기호 유형의 ASCII 텍스트 문자 8 개까지 사용할 수 있습니다.<br/> |
|**UsageLocation** <br/> |아니요  <br/> |유효한 ISO 3166-1 alpha-2 국가 코드입니다. 예를 들어 미국, 프랑스의 경우 *FR* *을 들* 을 있습니다. 일부 Microsoft 365 서비스는 특정 국가에서 사용할 수 없으므로이 값을 제공 하는 것이 중요 합니다. 계정에이 값이 구성 되어 있지 않으면 사용자 계정에 라이선스를 할당할 수 없습니다. 자세한 내용은 [사용권 제한 정보](https://go.microsoft.com/fwlink/p/?LinkId=691730)를 참조 하세요.<br/> |

>[!Note]
>Microsoft 365 관리 센터를 사용 하 여 [사용자 계정을 만드는 방법을 설명](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) 합니다.
> 
> 추가 리소스 목록은 [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/)을 참조 하십시오.
>   

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 모듈용 Azure Active Directory PowerShell 사용하기

먼저 [Microsoft 365 테 넌 트에 연결](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)합니다.

연결한 후 다음 구문을 사용 하 여 개별 계정을 만듭니다.
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="<user account password>"
New-AzureADUser -DisplayName "<display name>" -GivenName "<first name>" -SurName "<last name>" -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -MailNickName <mailbox name> -PasswordProfile $PasswordProfile -AccountEnabled $true
```

이 예에서는 US 사용자 *Caleb 창턱*에 대 한 계정을 만듭니다.
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="3Rv0y1q39/chsy"
New-AzureADUser -DisplayName "Caleb Sills" -GivenName "Caleb" -SurName "Sills" -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -MailNickName calebs -PasswordProfile $PasswordProfile -AccountEnabled $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell용 Microsoft Azure Active Directory 모듈 사용하기

먼저 [Microsoft 365 테 넌 트에 연결](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)합니다.

### <a name="create-an-individual-user-account"></a>개별 사용자 계정 만들기

개별 계정을 만들려면 다음 구문을 사용합니다.
  
```powershell
New-MsolUser -DisplayName <display name> -FirstName <first name> -LastName <last name> -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -LicenseAssignment <licensing plan name> [-Password <Password>]
```

>[!Note]
>PowerShell Core는 Windows PowerShell 모듈에 대 한 Microsoft Azure Active Directory 모듈 및 이름에 *Msol* 이 있는 cmdlet을 지원 하지 않습니다. Windows PowerShell에서 다음 cmdlet을 실행 합니다.
>

사용 가능한 라이선스 계획 이름을 열거하려면 이 명령을  사용합니다:

````powershell
Get-MsolAccountSku
````

이 예에서는 US 사용자 *Caleb 창턱*에 대 한 계정을 만들고 `contoso:ENTERPRISEPACK` (Office 365 Enterprise E3) 라이선스 계획에서 라이선스를 할당 합니다.
  
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
   >CSV 파일의 첫 번째 행에 있는 열 이름과 해당 순서는 임의로 지정한 것입니다. 하지만 파일의 나머지 부분에 있는 데이터 순서가 열 이름의 순서와 일치 하는지 확인 합니다. 다음 PowerShell for Microsoft 365 명령에 있는 매개 변수 값의 열 이름을 사용 합니다.
    
2. 다음 구문을 사용합니다.
    
    ```powershell
     Import-Csv -Path <Input CSV File Path and Name> | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId [-Password $_.Password]} | Export-Csv -Path <Output CSV File Path and Name>
    ```

   이 예제에서는 *C:\My Documents\NewAccounts.csv* 파일에서 사용자 계정을 만들고 *C:\My Documents\NewAccountResults.csv*이라는 파일에 결과를 기록 합니다.
    
    ```powershell
    Import-Csv -Path "C:\My Documents\NewAccounts.csv" | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId} | Export-Csv -Path "C:\My Documents\NewAccountResults.csv"
    ```

3. 결과 볼 수 있는 출력 파일을 검토 합니다. 암호를 지정 하지 않았으므로 Microsoft 365이 생성 하는 임의의 암호가 출력 파일에 표시 됩니다.
    
## <a name="see-also"></a>참고 항목

[PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[PowerShell로 Microsoft 365 관리](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365 용 PowerShell 시작](getting-started-with-microsoft-365-powershell.md)
