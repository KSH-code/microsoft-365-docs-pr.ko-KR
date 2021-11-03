---
title: PowerShell을 Microsoft 365 사용자 계정 보기
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 07/17/2020
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
- LIL_Placement
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: bb12f49d-a85d-4f3b-ada2-5c4e33977b10
description: PowerShell을 통해 다양한 방식으로 Microsoft 365 사용자 계정을 보거나, 나열하거나, 표시하는 방법을 학습합니다.
ms.openlocfilehash: 5c434825da95fd7d90594b2424cab287305f7d26
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60667509"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a>PowerShell을 Microsoft 365 사용자 계정 보기

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

를 사용하여 Microsoft 365 관리 센터 테넌트의 계정을 볼 Microsoft 365 있습니다. PowerShell for Microsoft 365 이 기능을 사용할 수 있지만 추가 기능도 제공합니다.
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 모듈용 Azure Active Directory PowerShell 사용하기

먼저 [테넌트 Microsoft 365 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  
### <a name="view-all-accounts"></a>모든 계정 보기

전체 사용자 계정 목록을 표시하기 위해 다음 명령을 실행합니다.
  
```powershell
Get-AzureADUser
```

다음 정보를 얻을 수 있습니다.
  
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

특정 사용자 계정을 표시하려면 다음 명령을 실행합니다. UPN(사용자 계정 이름)이라고도 하는 사용자 계정의 로그인 계정 이름을 입력합니다. "<" 및 ">" 문자를 제거합니다.
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

다음은 예입니다.
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a>특정 계정에 대한 추가 속성 값 보기

기본적으로 **Get-AzureADUser** cmdlet은 계정의 *ObjectID,* *DisplayName* 및 *UserPrincipalName* 속성만 표시합니다.

표시할 속성에 대해 보다 선택적으로 선택하려면 **Get-AzureADUser**  cmdlet과 함께 Select cmdlet을 사용하세요. 두 cmdlet을 결합하기 위해 "파이프" 문자("|")를 사용하여 Azure Active Directory PowerShell에 Graph 명령의 결과를 받아 다음 명령으로 보낼 수 있습니다. 다음은 모든 사용자 계정에 대한 *DisplayName,* *Department* 및 *UsageLocation을* 표시하는 예제 명령입니다.
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

이 명령은 PowerShell에 지시합니다.
  
1. 사용자 **계정(Get-AzureADUser)에** 대한 모든 정보를 확인하여 다음 명령()으로 **|** 전송합니다.
    
1.  사용자 계정 이름, 부서 및 사용 위치만 표시합니다(**DisplayName, Department, UsageLocation 선택).**
  
특정 사용자 계정에 대한 모든 속성을 표시하려면 **Select** cmdlet 및 와일드카드 문자(*)를 사용하세요. 다음은 예입니다.
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

다른 예로 다음 명령을 실행하여 특정 사용자 계정의 사용 상태를 확인합니다.
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-account-synchronization-status"></a>계정 동기화 상태 보기

사용자 계정에는 다음 두 가지 원본이 있습니다. 

- Windows Server Active Directory(AD)는 사내 AD에서 클라우드로 동기화되는 계정입니다.

- Azure Active Directory(Azure AD) 계정이 클라우드에서 직접 생성됩니다.

다음 명령을 사용하여 사내 AD에서 동기화하는 계정을 찾을 **수** 있습니다. *DirSyncEnabled* 특성이 True로 설정된 모든 사용자를 들이지 못하게 PowerShell에 *지시합니다.* 

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -eq $true}
```

다음 명령을 사용하여 클라우드 전용 **계정을 찾을 수** 있습니다. 이 설정은 *DirSyncEnabled* 특성이 *False로* 설정되거나 설정되지 않은 모든 사용자를 하게 PowerShell에 지시합니다(*Null*).
온-프레미스 AD에서 동기화되지 않는 *계정은 DirSyncEnabled가* *Null로 설정되어 있습니다.* 처음에 온-프레미스 AD에서 동기화했지만 더 이상 동기화되지는 않지만 *DirSyncEnabled가* *False로* 설정되어 있는 계정입니다. 

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -ne $true}
```

### <a name="view-accounts-based-on-a-common-property"></a>공통 속성을 기반으로 계정 보기

표시할 계정 목록에 대해 보다 선택적으로 사용하려면 **Where** cmdlet을 **Get-AzureADUser** cmdlet과 함께 사용하면 됩니다. 두 cmdlet을 결합하기 위해 "파이프" 문자("|")를 사용하여 Azure Active Directory PowerShell에 Graph 명령의 결과를 받아 다음 명령으로 보낼 수 있습니다. 다음은 지정되지 않은 사용 위치가 있는 사용자 계정만 표시하는 예제 명령입니다.
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

이 명령은 다음 Azure Active Directory PowerShell에 Graph 지시합니다.
  
1. 사용자 **계정(Get-AzureADUser)에** 대한 모든 정보를 확인하여 다음 명령()으로 **|** 전송합니다.
    
1. 미지정 사용 위치가 있는 모든 사용자 **계정(Where {$ \_ 을 찾아야 합니다. UsageLocation -eq $Null}**). 중괄호 안의 명령은 PowerShell에 UsageLocation 사용자 계정 속성이 있는 계정 집합만 찾게 **$ \_ 합니다. UsageLocation**)이 지정되지 않았습니다(**-eq $Null).**
    
**UsageLocation 속성은** 사용자 계정과 연결된 여러 속성 중 하나일 뿐입니다. 특정 사용자 계정에 대한 모든 속성을 표시하려면 **Select** cmdlet 및 와일드카드 문자(*)를 사용하세요. 다음은 예입니다.
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

예를 들어 **City는** 사용자 계정 속성의 이름입니다. 다음 명령을 사용하여 런던에 거주하는 모든 사용자의 계정을 나열할 수 있습니다.
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
> 이 예제의 **Where** cmdlet에 대한 구문은 **Where {$ \_ 입니다.** [사용자 계정 속성 이름] [비교 연산자] [value] **}**.> [비교 연산자]는 **-eq가** 같음, **-ne이면** 같지 않습니다. **-lt는** 보다 작음, -gt이면 보다 크면 **-gt입니다.**  [value]는 일반적으로 문자열(문자, 숫자 및 기타 문자 시퀀스), 숫자 값  또는 지정되지 않은 $Null 값입니다. 자세한 내용은 Where 를 [참조하세요.](/powershell/module/microsoft.powershell.core/where-object)

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell용 Microsoft Azure Active Directory 모듈 사용하기

먼저 [테넌트 Microsoft 365 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

### <a name="view-all-accounts"></a>모든 계정 보기

전체 사용자 계정 목록을 표시하기 위해 다음 명령을 실행합니다.
  
```powershell
Get-MsolUser
```

>[!Note]
>PowerShell Core는 Windows PowerShell용 Microsoft Azure Active Directory 모듈 및 이름에 *Msol* 이 있는 cmdlet을 지원하지 않습니다. Windows PowerShell 이러한 cmdlet을 실행합니다.
>

다음 정보를 얻을 수 있습니다.
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BonnieK@litwareinc.onmicrosoft.com    Bonnie Kearney        True
FabriceC@litwareinc.onmicrosoft.com   Fabrice Canel         True
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
AnneWlitwareinc.onmicrosoft.com       Anne Wallace          True
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

**Get-msoluser** cmdlet에도 매개 변수 집합이 있어 표시된 사용자 계정 집합을 필터링할 수 있습니다. 예를 들어 허가되지 않은 사용자(Microsoft 365 서비스에 대한 사용이 허가되지 않은 사용자)의 목록에서 다음 명령을 실행합니다.
  
```powershell
Get-MsolUser -UnlicensedUsersOnly
```

다음 정보를 얻을 수 있습니다.
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

표시되는 사용자 계정 집합을 필터링하는 추가 매개 변수에 대한 자세한 내용은 [Get-MsolUser 를 참조하세요.](/previous-versions/azure/dn194133(v=azure.100))
  
### <a name="view-a-specific-account"></a>특정 계정 보기

특정 사용자 계정을 표시하려면 다음 명령을 실행합니다. UPN(사용자 계정 이름)이라고도 하는 사용자 계정의 로그인 이름을 입력합니다. "<" 및 ">" 문자를 제거합니다.
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-accounts-based-on-a-common-property"></a>공통 속성을 기반으로 계정 보기

표시할 계정 목록에 대해 보다 선택적으로 사용하려면 **Where** cmdlet을 **Get-MsolUser** cmdlet과 함께 사용하면 됩니다. 두 cmdlet을 결합하기 위해 PowerShell에 한 명령의 결과를 받아 다음 명령으로 보내라고 알려주는 "파이프" 문자("|")를 사용 합니다. 다음은 지정되지 않은 사용 위치가 있는 사용자 계정만 표시하는 예입니다.
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

이 명령은 PowerShell에 지시합니다.
  
1. 사용자 **계정(Get-MsolUser)에** 대한 모든 정보를 확인하여 다음 명령()으로 **|** 전송합니다.
    
1. 미지정 사용 위치가 있는 모든 사용자 **계정(Where {$ \_ 을 찾아야 합니다. UsageLocation -eq $Null}**). 중괄호 안의 명령은 PowerShell에 UsageLocation 사용자 계정 속성이 있는 계정 집합만 찾게 **$ \_ 합니다. UsageLocation**)이 지정되지 않았습니다(**-eq $Null).**
    
다음 정보를 얻을 수 있습니다.
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

*UsageLocation 속성은* 사용자 계정과 연결된 여러 속성 중 하나일 뿐입니다. 사용자 계정에 대한 모든 속성을 표시하려면 **Select** cmdlet 및 와일드카드 문자(*)를 사용하여 특정 사용자 계정에 대한 모든 속성을 표시합니다. 다음은 예입니다.
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

예를 들어 *City는* 사용자 계정 속성의 이름입니다. 다음 명령을 사용하여 런던에 거주하는 사용자의 모든 사용자 계정을 나열할 수 있습니다.
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
> 이 예제의 **Where** cmdlet에 대한 구문은 **Where {$ \_ 입니다.** [사용자 계정 속성 이름] [비교 연산자] [value] **}**.  [비교 연산자]는 **-eq가** 같음, **-ne이면** 같지 않습니다. **-lt는** 보다 작음, -gt 보다 크면 **-gt입니다.**  [value]는 일반적으로 문자열(문자, 숫자 및 기타 문자 시퀀스), 숫자 값  또는 지정되지 않은 $Null 값입니다. 자세한 내용은 Where 를 [참조하세요.](/powershell/module/microsoft.powershell.core/where-object)
  
사용자 계정의 차단 상태를 확인하려면 다음 명령을 사용하세요.
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a>계정에 대한 추가 속성 값 보기

기본적으로 **Get-MsolUser** cmdlet은 사용자 계정의 다음 세 가지 속성을 표시합니다.
  
- UserPrincipalName

- DisplayName

- isLicensed

사용자가 작업하는 부서 및 Microsoft 365 서비스를 사용하는 국가/지역과 같은 추가 속성이 필요한 경우 **Get-MsolUser를** **Select** cmdlet과 함께 실행하여 사용자 계정 속성 목록을 지정할 수 있습니다. 다음은 예입니다.
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

이 명령은 PowerShell에 지시합니다.
  
1. 사용자 **계정(Get-MsolUser)에** 대한 모든 정보를 확인하여 다음 명령( )으로 **|** 전송합니다.
    
1. 사용자 계정 이름, 부서 및 사용 위치만 표시합니다(**DisplayName, Department, UsageLocation 선택).**
    
다음 정보를 얻을 수 있습니다.
  
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

Select  cmdlet을 사용하면 표시할 속성을 선택할 수 있습니다. 특정 사용자 계정에 대한 모든 속성을 표시하려면 와일드카드 문자(*)를 사용하세요. 다음은 예입니다.
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

표시할 계정 목록에 대해 보다 선택적으로 선택하려면 **Where** cmdlet을 사용할 수도 있습니다. 다음은 지정되지 않은 사용 위치가 있는 사용자 계정만 표시하는 예제 명령입니다.
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

이 명령은 PowerShell에 지시합니다.
  
1. 사용자 **계정(Get-MsolUser)에** 대한 모든 정보를 확인하여 다음 명령( )으로 **|** 전송합니다.
    
1. 미지정 사용 위치가 있는 모든 사용자 **계정(Where {$ \_ 을 찾아야 합니다. UsageLocation -eq $Null}**) 및 다음 명령()에 결과 정보를 **|** 전송합니다. 중괄호 안의 명령은 PowerShell에 UsageLocation 사용자 계정 속성이 있는 계정 집합만 찾게 **$ \_ 합니다. UsageLocation**)이 지정되지 않았습니다(**-eq $Null).**
    
1. 사용자 계정 이름, 부서 및 사용 위치만 표시합니다(**DisplayName, Department, UsageLocation 선택).**
    
다음 정보를 얻을 수 있습니다.
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

디렉터리 동기화를 사용하여 Microsoft 365 사용자를 만들고 관리하는 경우 Microsoft 365 로컬 계정을 표시할 수 있습니다. 다음 예제에서는 다음을 가정합니다.

- Azure AD 커넥트 ObjectGUID의 기본 원본 앵커를 사용하도록 구성됩니다. 원본 앵커 구성에 대한 자세한 내용은 [Azure AD 커넥트: 디자인 개념을 참조하세요.](/azure/active-directory/hybrid/plan-connect-design-concepts)
- PowerShell용 Active Directory 도메인 서비스 모듈이 [설치되었습니다(RSAT 도구 참조).](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a>참고 항목

[PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[PowerShell로 Microsoft 365 관리](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365용 PowerShell 시작](getting-started-with-microsoft-365-powershell.md)
