---
title: PowerShell을 사용 하 여 Microsoft 365 사용자 계정 속성 구성
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
- O365ITProTrain
- Ent_Office_Other
- PowerShell
ms.assetid: 30813f8d-b08d-444b-98c1-53df7c29b4d7
description: Microsoft 365 용 PowerShell을 사용 하 여 Microsoft 365 테 넌 트에서 개별 또는 여러 사용자 계정에 대 한 속성을 구성 합니다.
ms.openlocfilehash: 830cede93a6c14db2dcc5626d41d0dd296b9ac29
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754331"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a>PowerShell을 사용 하 여 Microsoft 365 사용자 계정 속성 구성

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

Microsoft 365 관리 센터를 사용 하 여 Microsoft 365 테 넌 트의 사용자 계정에 대 한 속성을 구성할 수 있습니다. 또한 PowerShell에서이 작업을 수행할 수도 있고 관리 센터에서 수행할 수 없는 다른 작업도 할 수도 있습니다.
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 모듈용 Azure Active Directory PowerShell 사용하기

Graph 모듈에 대 한 Azure Active Directory PowerShell의 사용자 계정에 대 한 속성을 구성 하려면 [**AzureADUser**](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) cmdlet을 사용 하 고 설정 하거나 변경할 속성을 지정 합니다.

먼저 [Microsoft 365 테 넌 트에 연결](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)합니다.
   
### <a name="change-properties-for-a-specific-user-account"></a>특정 사용자 계정에 대 한 속성 변경

*-ObjectID* 매개 변수를 사용 하 여 계정을 식별 하 고 추가 매개 변수를 사용 하 여 특정 속성을 설정 하거나 변경 합니다. 다음은 가장 일반적인 매개 변수 목록입니다.
  
- -부서 " \<department name> "
    
- -DisplayName " \<full user name> "
    
- -FacsimilieTelephoneNumber " \<fax number> "
    
- -GivenName " \<user first name> "
    
- -성 " \<user last name> "
    
- -Mobile " \<mobile phone number> "
    
- -JobTitle " \<job title> "
    
- -PreferredLanguage " \<language> "
    
- -StreetAddress " \<street address> "
    
- -구/군/시 " \<city name> "
    
- -State " \<state name> "
    
- -PostalCode " \<postal code> "
    
- -Country " \<country name> "
    
- -TelephoneNumber " \<office phone number> "
    
- -UsageLocation " \<2-character country or region code> "
    
    ISO 3166-1 alpha-2 (A2) 두 자리 국가 또는 지역 코드입니다.
    
추가 매개 변수에 대 한 자세한 내용은 [AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) 를 참조 하십시오.

>[!Note]
>사용자 계정에 라이선스를 할당 하려면 사용 위치를 할당 해야 합니다.
>

사용자 계정의 사용자 계정 이름을 표시 하려면 다음 명령을 실행 합니다.
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

이 명령은 PowerShell에 다음을 지시 합니다.
  
1. 사용자 계정 (**AzureADUser**)에 대 한 모든 정보를 가져오고 다음 명령 ()으로 보냅니다 **|** .
    
1. 사용자 계정 이름 목록을 사전순 (**Sort UserPrincipalName**)으로 정렬 하 고 다음 명령 ()으로 보냅니다 **|** .
    
1. 각 계정에 대해 사용자 계정 이름 속성을 표시 합니다 (**UserPrincipalName 선택**).

1. 한**화면을 한**번에 한 화면씩 표시 합니다.
    
표시 이름 (이름과 성)을 기준으로 계정의 사용자 계정 이름을 표시 하려면 다음 명령을 실행 합니다. *$UserName* 변수를 채우고 해당 문자를 제거 합니다 \< and > .
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

이 예에서는 표시 이름이 *Caleb 창턱*인 사용자 계정에 대 한 사용자 보안 주체 이름을 표시 합니다.
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

*$Upn* 변수를 사용 하 여 개별 계정을 표시 이름에 따라 변경할 수 있습니다. 다음은 *Belinda Newman*의 사용 위치를 프랑스로 설정 하는 예입니다. 하지만 사용자 계정 이름이 아닌 표시 이름을 지정 합니다.
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a>모든 사용자 계정에 대 한 속성 변경

모든 사용자에 대 한 속성을 변경 하려면 **AzureADUser** 및 **AzureADUser** cmdlet을 조합 하 여 사용할 수 있습니다. 다음은 모든 사용자의 사용 위치를 *프랑스*로 변경 하는 예제입니다.
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

이 명령은 PowerShell에 다음을 지시 합니다.
  
1. 사용자 계정 (**AzureADUser**)에 대 한 모든 정보를 가져오고 다음 명령 ()으로 전송 **|** 합니다.
    
1. 사용자 위치를 프랑스 (**AzureADUser-UsageLocation "FR"**)로 설정 합니다.
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a>특정 사용자 계정 집합의 속성 변경

특정 사용자 계정 집합의 속성을 변경 하려면 **AzureADUser**, **Where**및 **AzureADUser** cmdlet을 조합 하 여 사용할 수 있습니다. 다음 예에서는 회계 부서에 있는 모든 사용자의 사용 위치를 *프랑스*로 변경 합니다.
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

이 명령은 PowerShell에 다음을 지시 합니다.
  
1. 사용자 계정 (**AzureADUser**)에 대 한 모든 정보를 가져오고 다음 명령 ()으로 보냅니다 **|** .
    
1.  *부서* 속성이 "회계"로 설정 된 모든 사용자 계정을 찾습니다 (**여기서 {$ _. 부서-eq "Accounting"}**)를 사용 하 고 결과 정보를 다음 명령 ()으로 보냅니다 **|** .
    
1. 사용자 위치를 프랑스 (**AzureADUser-UsageLocation "FR"**)로 설정 합니다.
    
## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell용 Microsoft Azure Active Directory 모듈 사용하기

Windows PowerShell 용 Microsoft Azure Active Directory 모듈을 사용 하 여 사용자 계정에 대 한 속성을 구성 하려면 **get-msoluser** cmdlet을 사용 하 고 설정 하거나 변경할 속성을 지정 합니다.

먼저 [Microsoft 365 테 넌 트에 연결](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)합니다.
  
>[!Note]
>PowerShell Core에서는 이름에 *Msol* 이 포함 된 Windows powershell 모듈 및 cmdlet에 대 한 Microsoft Azure Active Directory 모듈을 지원 하지 않습니다. Windows PowerShell에서 다음 cmdlet을 실행 합니다.
>

### <a name="change-properties-for-a-specific-user-account"></a>특정 사용자 계정에 대 한 속성 변경

특정 사용자 계정에 대 한 속성을 구성 하려면 [**get-msoluser**](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) cmdlet을 사용 하 고 설정 하거나 변경할 속성을 지정 합니다. 

*-UserPrincipalName* 매개 변수를 사용 하 여 계정을 식별 하 고 추가 매개 변수를 사용 하 여 특정 속성을 설정 하거나 변경 합니다. 가장 일반적인 매개 변수 목록은 다음과 같습니다.
  
- -구/군/시 " \<city name> "
    
- -Country " \<country name> "
    
- -부서 " \<department name> "
    
- -DisplayName " \<full user name> "
    
- -Fax " \<fax number> "
    
- -FirstName " \<user first name> "
    
- -LastName " \<user last name> "
    
- -MobilePhone " \<mobile phone number> "
    
- -Office " \<office location> "
    
- -PhoneNumber " \<office phone number> "
    
- -PostalCode " \<postal code> "
    
- -PreferredLanguage " \<language> "
    
- -State " \<state name> "
    
- -StreetAddress " \<street address> "
    
- -Title " \<title name> "
    
- -UsageLocation " \<2-character country or region code> "
    
    ISO 3166-1 alpha-2 (A2) 두 자리 국가 또는 지역 코드입니다.
    
추가 매개 변수에 대 한 자세한 내용은 [get-msoluser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100))를 참조 하십시오.

모든 사용자의 사용자 계정 이름을 보려면 다음 명령을 실행 합니다.
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

이 명령은 PowerShell에 다음을 지시 합니다.
  
1. 사용자 계정 (**get-msoluser**)에 대 한 모든 정보를 가져오고 다음 명령 ()으로 보냅니다 **|** .
    
1. 사용자 계정 이름 목록을 사전순 (**Sort UserPrincipalName**)으로 정렬 하 고 다음 명령 ()으로 보냅니다 **|** .
    
1. 각 계정에 대해 사용자 계정 이름 속성을 표시 합니다 (**UserPrincipalName 선택**).
    
1. 한**화면을 한**번에 한 화면씩 표시 합니다.
    
표시 이름 (이름과 성)을 기준으로 계정의 사용자 계정 이름을 표시 하려면 다음 명령을 실행 합니다. *$UserName* 변수를 채우고 해당 문자를 제거 \< and > 합니다.
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

이 예제에서는 Caleb 창턱 라는 사용자에 대 한 사용자 계정 이름을 표시 합니다.
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

*$Upn* 변수를 사용 하 여 개별 계정을 표시 이름에 따라 변경할 수 있습니다. 다음은 *Belinda Newman*의 사용 위치를 *프랑스*로 설정 하지만 사용자 계정 이름이 아닌 표시 이름을 지정 하는 예제입니다.
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a>모든 사용자 계정에 대 한 속성 변경

모든 사용자에 대 한 속성을 변경 하려면 **get-msoluser** 및 **get-msoluser** cmdlet을 조합 하 여 사용 합니다. 다음은 모든 사용자의 사용 위치를 *프랑스*로 변경 하는 예제입니다.
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

이 명령은 PowerShell에 다음을 지시 합니다.
  
1. 사용자 계정 (**get-msoluser**)에 대 한 모든 정보를 가져오고 다음 명령 ()으로 보냅니다 **|** .
    
1. 사용자 위치를 프랑스 (**get-msoluser-UsageLocation "FR"**)로 설정 합니다.
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a>특정 사용자 계정 집합의 속성 변경

특정 사용자 계정 집합의 속성을 변경 하려면 **get-msoluser**, **Where**및 **get-msoluser** cmdlet을 조합 하 여 사용할 수 있습니다. 다음 예에서는 회계 부서에 있는 모든 사용자의 사용 위치를 *프랑스*로 변경 합니다.
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

이 명령은 PowerShell에 다음을 지시 합니다.
  
1. 사용자 계정 (**get-msoluser**)에 대 한 모든 정보를 가져오고 다음 명령 ()으로 보냅니다 **|** .
    
1. *부서* 속성이 "회계"로 설정 된 모든 사용자 계정을 찾습니다 (**여기서 {$ _. 부서-eq "Accounting"}**)를 사용 하 고 결과 정보를 다음 명령 ( **|** )으로 보냅니다.
    
1. 사용자 위치를 프랑스 (**get-msoluser-UsageLocation "FR"**)로 설정 합니다.

## <a name="see-also"></a>참고 항목

[PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[PowerShell로 Microsoft 365 관리](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365용 PowerShell 시작](getting-started-with-microsoft-365-powershell.md)
