---
title: PowerShell을 사용 하 여 Microsoft 365 사용자 계정 보기
ms.author: josephd
author: JoeDavies-MSFT
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
- LIL_Placement
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: bb12f49d-a85d-4f3b-ada2-5c4e33977b10
description: PowerShell을 사용 하 여 다양 한 방식으로 Microsoft 365 사용자 계정을 보거나, 나열 하거나, 표시 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 312e9fb983c4d1f4de8bc74586c88f1e669eb90a
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754075"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a>PowerShell을 사용 하 여 Microsoft 365 사용자 계정 보기

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

Microsoft 365 관리 센터를 사용 하 여 Microsoft 365 테 넌 트에 대 한 계정을 볼 수 있습니다. Microsoft 365 용 PowerShell을 사용 하도록 설정 하지만 추가 기능도 제공 됩니다.
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 모듈용 Azure Active Directory PowerShell 사용하기

먼저 [Microsoft 365 테 넌 트에 연결](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)합니다.
  
### <a name="view-all-accounts"></a>모든 계정 보기

사용자 계정의 전체 목록을 표시 하려면 다음 명령을 실행 합니다.
  
```powershell
Get-AzureADUser
```

다음과 같은 정보가 표시 됩니다.
  
```powershell
ObjectId                             DisplayName                                           UserPrincipalName
--------                             -----------                                           -----------------
032fc1fc-b5a2-46f1-8635-3d7dcb52c48d Adele Vance                                           AdeleV@litwareinc.OnMicr...
bd1e6af1-41e7-4f77-a2ac-5b209950135c Global Administrator                                  admin@litwareinc.onmicro...
ec37a4d6-232e-4eb7-82a5-1613490642a5 Alex Wilber                                           AlexW@litwareinc.OnMicro...
be4bdddd-c790-424c-9f96-a0cf609b7815 Allan Deyoung                                         AllanD@litwareinc.OnMicr...
598ab87b-76f0-4bf9-9538-bd46b10f4438 Christie Cline                                        ChristieC@litwareinc.OnM...
40722671-e520-4a5f-97d4-0bc9e9b2dc0f Debra Berger                                          DebraB@litwareinc.OnMicr...
```

### <a name="view-a-specific-account"></a>특정 계정 보기

특정 사용자 계정을 표시 하려면 다음 명령을 실행 합니다. UPN (사용자 계정 이름)이 라고도 하는 사용자 계정의 로그인 계정 이름을 입력 합니다. "<" 및 ">" 문자를 제거 합니다.
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

예를 들면 다음과 같습니다.
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a>특정 계정에 대 한 추가 속성 값 보기

기본적으로 **AzureADUser** cmdlet은 계정의 *ObjectID*, *DisplayName*및 *UserPrincipalName* 속성만 표시 합니다.

표시할 속성을 보다 신중 하 게 선택 하려면 **AzureADUser** cmdlet과 함께 **Select** cmdlet을 사용 하십시오. 두 cmdlet을 결합 하기 위해 Azure Active Directory PowerShell에는 그래프를 나타내는 "|" 문자를 사용 하 여 하나의 명령에 대 한 결과를 가져오고 다음 명령으로 전송 합니다. 다음은 모든 사용자 계정에 대해 *DisplayName*, *학과*및 *UsageLocation* 를 표시 하는 명령 예제입니다.
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

이 명령은 PowerShell에 다음을 지시 합니다.
  
1. 사용자 계정 (**AzureADUser**)에 대 한 모든 정보를 가져오고 다음 명령 ()으로 보냅니다 **|** .
    
1.  사용자 계정 이름, 부서 및 사용 위치만 표시 합니다 (**DisplayName, 학과, UsageLocation 선택**).
  
특정 사용자 계정에 대 한 모든 속성을 보려면 **Select** cmdlet 및 와일드 카드 문자 (*)를 사용 합니다. 예를 들면 다음과 같습니다.
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

또 다른 예로, 다음 명령을 실행 하 여 특정 사용자 계정의 사용 상태를 확인 합니다.
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-account-synchronization-status"></a>계정 동기화 상태 보기

사용자 계정에는 다음과 같은 두 가지 원본이 있습니다. 

- Windows Server AD (Active Directory)-온-프레미스 AD에서 클라우드로 동기화 되는 계정입니다.

- Azure AD (Active Directory) AD 계정 (클라우드에서 직접 만들어짐)


다음 명령은 *Dirsyncenabled* 특성이 *True*로 설정 된 모든 사용자를 가져오기 위해 PowerShell에 지시 합니다. 이를 사용 하 여 온-프레미스 AD와 동기화 되는 계정을 찾을 수 있습니다.

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -eq $true}
```

다음 명령은 *Dirsyncenabled* 특성이 *False*로 설정 된 모든 사용자를 가져오기 위해 PowerShell에 지시 합니다. 이를 사용 하 여 클라우드 전용 계정을 찾을 수 있습니다.

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -ne $false}
```

### <a name="view-accounts-based-on-a-common-property"></a>공통 속성을 기준으로 계정 보기

표시할 계정 목록을 보다 신중 하 게 선택 하려면 **Where** Cmdlet을 **AzureADUser** cmdlet과 함께 사용 하면 됩니다. 두 cmdlet을 결합 하기 위해 Azure Active Directory PowerShell에는 그래프를 나타내는 "|" 문자를 사용 하 여 하나의 명령에 대 한 결과를 가져오고 다음 명령으로 전송 합니다. 다음은 사용 위치가 지정 되지 않은 사용자 계정만 표시 하는 명령입니다.
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

이 명령은 다음과 같은 그래프에 Azure Active Directory PowerShell을 지시 합니다.
  
1. 사용자 계정 (**AzureADUser**)에 대 한 모든 정보를 가져오고 다음 명령 ()으로 보냅니다 **|** .
    
1. 사용 위치 (**여기서 {$)가 지정 되지 않은 모든 사용자 계정을 찾습니다 \_ . UsageLocation-eq $Null}**). 중괄호 내에서이 명령은 PowerShell에 UsageLocation 사용자 계정 속성 (을 사용 하는 경우에만 해당 계정 집합을 찾습니다** $ \_ . UsageLocation**)이 지정 되지 않았습니다 (**-eq $Null**).
    
**UsageLocation** 속성은 사용자 계정에 연결 된 여러 속성 중 하나에 불과합니다. 특정 사용자 계정에 대 한 모든 속성을 표시 하려면 **Select** cmdlet 및 와일드 카드 문자 (*)를 사용 합니다. 예를 들면 다음과 같습니다.
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

예를 들어 **도시명** 은 사용자 계정 속성의 이름입니다. 다음 명령을 사용 하 여 London에 거주 하는 모든 사용자의 계정을 나열할 수 있습니다.
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  이러한 예의 **where** cmdlet에 대 한 구문은 여기에 해당 합니다 ** \_ .** [사용자 계정 속성 이름] [비교 연산자] 가치 **}**. > [비교 연산자]는 equals의 경우- **eq** , **-ne** = 같지 않음,-a = 부등호, **-lt** for a,- **gt** = 보다 작음, 기타 보다 작거나 같습니다.  [값]은 일반적으로 문자열 (문자, 숫자 및 기타 문자의 시퀀스), 숫자 값 또는 **$Null** 지정 되지 않음에 해당 합니다. 자세한 내용은 [위치](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7)를 참조 하세요.
  

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell용 Microsoft Azure Active Directory 모듈 사용하기

먼저 [Microsoft 365 테 넌 트에 연결](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)합니다.

### <a name="view-all-accounts"></a>모든 계정 보기

사용자 계정의 전체 목록을 표시 하려면 다음 명령을 실행 합니다.
  
```powershell
Get-MsolUser
```

>[!Note]
>PowerShell Core에서는 이름에 *Msol* 이 포함 된 Windows powershell 모듈 및 cmdlet에 대 한 Microsoft Azure Active Directory 모듈을 지원 하지 않습니다. Windows PowerShell에서 다음 cmdlet을 실행 합니다.
>

다음과 같은 정보가 표시 됩니다.
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BonnieK@litwareinc.onmicrosoft.com    Bonnie Kearney        True
FabriceC@litwareinc.onmicrosoft.com   Fabrice Canel         True
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
AnneWlitwareinc.onmicrosoft.com       Anne Wallace          True
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

**Get-msoluser** cmdlet에도 매개 변수 집합이 있어 표시된 사용자 계정 집합을 필터링할 수 있습니다. 예를 들어 라이선스가 없는 사용자 목록 (Microsoft 365에 추가 되었지만 아직 어떤 서비스를 사용 하도록 허가 되지 않은 사용자)의 경우에는 다음 명령을 실행 합니다.
  
```powershell
Get-MsolUser -UnlicensedUsersOnly
```

다음과 같은 정보가 표시 됩니다.
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

표시 되는 사용자 계정 집합을 필터링 하기 위한 추가 매개 변수에 대 한 자세한 내용은 [get-msoluser](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100))를 참조 하십시오.
  
### <a name="view-a-specific-account"></a>특정 계정 보기

특정 사용자 계정을 표시 하려면 다음 명령을 실행 합니다. UPN (사용자 계정 이름)이 라고도 하는 사용자 계정의 로그인 이름을 입력 합니다. "<" 및 ">" 문자를 제거 합니다.
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-accounts-based-on-a-common-property"></a>공통 속성을 기준으로 계정 보기

표시할 계정 목록을 보다 신중 하 게 선택 하려면 **Where** Cmdlet을 **get-msoluser** cmdlet과 함께 사용 하면 됩니다. 두 cmdlet을 결합 하려면 "파이프" 문자 ("|")를 사용 하 여 PowerShell에 한 명령의 결과를 가져오고 다음 명령에 전송 하도록 지시 합니다. 다음은 사용 위치가 지정 되지 않은 사용자 계정만 표시 하는 예제입니다.
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

이 명령은 PowerShell에 다음을 지시 합니다.
  
1. 사용자 계정 (**get-msoluser**)에 대 한 모든 정보를 가져오고 다음 명령 ()으로 보냅니다 **|** .
    
1. 사용 위치 (**여기서 {$)가 지정 되지 않은 모든 사용자 계정을 찾습니다. \_ UsageLocation-eq $Null}**). 중괄호 내에서이 명령은 PowerShell에 UsageLocation 사용자 계정 속성 (을 사용 하는 경우에만 사용 되는 계정 집합을 찾습니다** $ \_ . UsageLocation**)이 지정 되지 않았습니다 (**-eq $Null**).
    
다음과 같은 정보가 표시 됩니다.
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

*UsageLocation* 속성은 사용자 계정에 연결 된 여러 속성 중 하나에 불과합니다. 사용자 계정에 대 한 모든 속성을 보려면 **Select** cmdlet 및 와일드 카드 문자 (*)를 사용 하 여 특정 사용자 계정에 대해 모두 표시 합니다. 예를 들면 다음과 같습니다.
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

예를 들어 *도시명* 은 사용자 계정 속성의 이름입니다. 다음 명령을 사용 하 여 London에 거주 하는 사용자에 대 한 모든 사용자 계정을 나열할 수 있습니다.
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  이러한 예의 **where** cmdlet에 대 한 구문은 여기에 해당 합니다 ** \_ .** [사용자 계정 속성 이름] [비교 연산자] 가치 **}**.  [비교 연산자]는 equals의 경우- **eq** , **-ne** : 같지 않음,-a = 부등호, **-** a = 보다 작음,- **gt** for = 및 기타입니다.  [값]은 일반적으로 문자열 (문자, 숫자 및 기타 문자의 시퀀스), 숫자 값 또는 **$Null** 지정 되지 않음에 해당 합니다. 자세한 내용은 [위치](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7)를 참조 하세요.
  
사용자 계정의 차단 상태를 확인 하려면 다음 명령을 사용 합니다.
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a>계정의 추가 속성 값 보기

기본적으로 **get-msoluser** cmdlet은 다음과 같은 세 가지 사용자 계정 속성을 표시 합니다.
  
- UserPrincipalName
    
- DisplayName
    
- isLicensed
    
사용자가 근무 하는 부서와 Microsoft 365 서비스를 사용 하는 국가/지역이 같은 추가 속성이 필요한 경우 **get-msoluser** 를 **Select** cmdlet과 함께 실행 하 여 사용자 계정 속성 목록을 지정할 수 있습니다. 예를 들면 다음과 같습니다.
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

이 명령은 PowerShell에 다음을 지시 합니다.
  
1. 사용자 계정 (**get-msoluser**)에 대 한 모든 정보를 가져오고 다음 명령 ()으로 전송 **|** 합니다.
    
1. 사용자 계정 이름, 부서 및 사용 위치만 표시 합니다 (**DisplayName, 학과, UsageLocation 선택**).
    
다음과 같은 정보가 표시 됩니다.
  
```powershell
DisplayName             Department                       UsageLocation
-----------             ----------                       -------------
Bonnie Kearney          Sales & Marketing                    US
Fabrice Canel           Legal                                US
Brian Johnson
Anne Wallace            Executive Management                 US
Alex Darrow             Sales & Marketing                    US
Scott Wallace           Operations
```

**Select** cmdlet을 사용 하 여 표시할 속성을 선택할 수 있습니다. 특정 사용자 계정에 대 한 모든 속성을 표시 하려면 와일드 카드 문자 (*)를 사용 합니다. 예를 들면 다음과 같습니다.
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

표시할 계정 목록에 대해 보다 신중 하 게 선택 하려면 **Where** cmdlet을 사용할 수도 있습니다. 다음은 사용 위치가 지정 되지 않은 사용자 계정만 표시 하는 명령입니다.
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

이 명령은 PowerShell에 다음을 지시 합니다.
  
1. 사용자 계정 (**get-msoluser**)에 대 한 모든 정보를 가져오고 다음 명령 ()으로 전송 **|** 합니다.
    
1. 사용 위치 (**여기서 {$)가 지정 되지 않은 모든 사용자 계정을 찾습니다. \_ UsageLocation-eq $Null}**)를 만들고 결과 정보를 다음 명령 ()로 보냅니다 **|** . 중괄호 내에서이 명령은 PowerShell에 UsageLocation 사용자 계정 속성 (을 사용 하는 경우에만 해당 계정 집합을 찾습니다** $ \_ . UsageLocation**)이 지정 되지 않았습니다 (**-eq $Null**).
    
1. 사용자 계정 이름, 부서 및 사용 위치만 표시 합니다 (**DisplayName, 학과, UsageLocation 선택**).
    
다음과 같은 정보가 표시 됩니다.
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

디렉터리 동기화를 사용 하 여 Microsoft 365 사용자를 만들고 관리 하는 경우 Microsoft 365 사용자가 투영 된 로컬 계정을 표시할 수 있습니다. 다음 예제에서는 다음을 가정 합니다.

- Azure AD Connect는 ObjectGUID의 기본 원본 앵커를 사용 하도록 구성 됩니다. 원본 앵커를 구성 하는 방법에 대 한 자세한 내용은 [AZURE AD Connect: Design 개념도](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)를 참조 하십시오.
- PowerShell 용 Active Directory 도메인 서비스 모듈이 설치 되었습니다 ( [RSAT tools](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)참조).

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a>참고 항목

[PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[PowerShell로 Microsoft 365 관리](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365용 PowerShell 시작](getting-started-with-microsoft-365-powershell.md)
