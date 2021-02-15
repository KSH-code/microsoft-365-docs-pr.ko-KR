---
title: PowerShell을 통해 Microsoft 365 사용자 계정 보기
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
description: PowerShell을 통해 다양한 방식으로 Microsoft 365 사용자 계정을 보거나, 나열하거나, 표시하는 방법을 자세히 알아보는 방법을 배워야 합니다.
ms.openlocfilehash: 312e9fb983c4d1f4de8bc74586c88f1e669eb90a
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754075"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a>PowerShell을 통해 Microsoft 365 사용자 계정 보기

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

Microsoft 365 관리 센터를 사용하여 Microsoft 365 테넌트의 계정을 볼 수 있습니다. Microsoft 365용 PowerShell에서는 이 기능을 사용할 수 있지만 추가 기능도 제공합니다.
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 모듈용 Azure Active Directory PowerShell 사용하기

먼저 [Microsoft 365 테넌트에 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  
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

예를 들면 다음과 같습니다.
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a>특정 계정에 대한 추가 속성 값 보기

기본적으로 **Get-AzureADUser** cmdlet은 계정의 *ObjectID,* *DisplayName* 및 *UserPrincipalName* 속성만 표시합니다.

표시할 속성에 대해 보다 선택적으로 선택하려면 **Get-AzureADUser**  cmdlet과 함께 Select cmdlet을 사용하세요. 두 cmdlet을 결합하기 위해 "파이프" 문자("|")를 사용하여 Graph용 Azure Active Directory PowerShell에 한 명령의 결과를 받아 다음 명령으로 전송합니다. 다음은 모든 사용자 계정에 대한 *DisplayName,* *Department* 및 *UsageLocation을* 표시하는 명령의 예입니다.
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

이 명령은 PowerShell에 지시합니다.
  
1. 사용자 **계정(Get-AzureADUser)에** 대한 모든 정보를 확인하여 다음 명령()으로 **|** 전송합니다.
    
1.  사용자 계정 이름, 부서 및 사용 **위치(DisplayName, Department, UsageLocation 선택)만 표시합니다.**
  
특정 사용자 계정에 대한 모든 속성을 표시하려면 **Select** cmdlet과 와일드카드 문자(*)를 사용하세요. 예를 들면 다음과 같습니다.
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

다른 예로, 다음 명령을 실행하여 특정 사용자 계정의 사용 상태를 확인합니다.
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-account-synchronization-status"></a>계정 동기화 상태 보기

사용자 계정에는 다음 두 가지 원본이 있습니다. 

- Windows Server AD(Active Directory) - 클라우드로의 동기화 계정입니다.

- 클라우드에서 직접 생성되는 Azure AD(Azure Active Directory) AD 계정


다음 명령은 *DirSyncEnabled* 특성이 True로 설정된 모든 사용자를 PowerShell에 *지시합니다.* 이 계정을 사용하여 이 계정을 사용하여 On-premise AD에서 동기화하는 계정을 찾을 수 있습니다.

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -eq $true}
```

다음 명령은 *DirSyncEnabled* 특성이 False로 설정된 모든 사용자를 PowerShell에 *지시합니다.* 이 계정을 사용하여 클라우드 전용 계정을 찾을 수 있습니다.

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -ne $false}
```

### <a name="view-accounts-based-on-a-common-property"></a>공통 속성을 기반으로 계정 보기

표시할 계정 목록에 대해 보다 선택적으로 선택하려면 **Where** cmdlet을 **Get-AzureADUser** cmdlet과 함께 사용하면 됩니다. 두 cmdlet을 결합하기 위해 "파이프" 문자("|")를 사용하여 Graph용 Azure Active Directory PowerShell에 한 명령의 결과를 받아 다음 명령으로 전송합니다. 다음은 지정되지 않은 사용 위치가 있는 사용자 계정만 표시하는 명령의 예입니다.
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

이 명령은 Graph용 Azure Active Directory PowerShell에 다음을 지시합니다.
  
1. 사용자 **계정(Get-AzureADUser)에** 대한 모든 정보를 확인하여 다음 명령()으로 **|** 전송합니다.
    
1. 미지정 사용 위치(Where {$)가 있는 모든 사용자 **계정을 찾아야 \_ 합니다. UsageLocation -eq $Null}**). 중괄호 안에 있는 명령은 UsageLocation 사용자 계정 속성(.**$ \_ UsageLocation**)이 지정되지 **않았습니다(-eq $Null).**
    
**UsageLocation 속성은** 사용자 계정과 연결된 여러 속성 중 하나일 뿐입니다. 특정 사용자 계정에 대한 모든 속성을 표시하려면 **Select** cmdlet과 와일드카드 문자(*)를 사용하세요. 예를 들면 다음과 같습니다.
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

예를 들어 **City는** 사용자 계정 속성의 이름입니다. 다음 명령을 사용하여 런던에 거주하는 모든 사용자의 계정을 나열할 수 있습니다.
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  이 예제의 **Where** cmdlet 구문은 **Where {$ \_ 입니다.** [사용자 계정 속성 이름] [비교 연산자] [value] **}**.> [비교 연산자]는 **-eq이고,** 같지 않은 경우 **-ne,** **-lt이면 -lt,** 보다 크면 **-gt입니다.**  [value]는 일반적으로 문자열(문자, 숫자 및 기타 문자 시퀀스), 숫자 값  또는 지정되지 않은 $Null 값입니다. 자세한 내용은 [Where를 참조하세요.](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7)
  

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell용 Microsoft Azure Active Directory 모듈 사용하기

먼저 [Microsoft 365 테넌트에 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

### <a name="view-all-accounts"></a>모든 계정 보기

전체 사용자 계정 목록을 표시하기 위해 다음 명령을 실행합니다.
  
```powershell
Get-MsolUser
```

>[!Note]
>PowerShell Core는 Windows PowerShell용 Microsoft Azure Active Directory 모듈 및 이름에 *Msol* 이 있는 cmdlet을 지원하지 않습니다. Windows PowerShell에서 이러한 cmdlet을 실행합니다.
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

**Get-msoluser** cmdlet에도 매개 변수 집합이 있어 표시된 사용자 계정 집합을 필터링할 수 있습니다. 예를 들어 허가되지 않은 사용자(Microsoft 365에 추가했지만 서비스를 사용할 수 있는 라이선스가 아직 부여되지 않은 사용자)의 경우 다음 명령을 실행합니다.
  
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

표시되는 사용자 계정 집합을 필터링하는 추가 매개 변수에 대한 자세한 내용은 [Get-MsolUser를 참조하십시오.](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100))
  
### <a name="view-a-specific-account"></a>특정 계정 보기

특정 사용자 계정을 표시하려면 다음 명령을 실행합니다. UPN(사용자 계정 이름)이라고도 하는 사용자 계정의 로그인 이름을 입력합니다. "<" 및 ">" 문자를 제거합니다.
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-accounts-based-on-a-common-property"></a>공통 속성을 기반으로 계정 보기

표시할 계정 목록에 대해 보다 선택적으로 선택하려면 **Where** cmdlet을 **Get-MsolUser** cmdlet과 함께 사용하면 됩니다. 두 cmdlet을 결합하기 위해 PowerShell에 한 명령의 결과를 받아 다음 명령으로 보내라고 하는 "파이프" 문자("|")를 사용 합니다. 다음은 지정되지 않은 사용 위치가 있는 사용자 계정만 표시하는 예입니다.
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

이 명령은 PowerShell에 지시합니다.
  
1. 사용자 **계정(Get-MsolUser)에** 대한 모든 정보를 확인하여 다음 명령()으로 **|** 전송합니다.
    
1. 미지정 사용 위치(Where {$)가 있는 모든 **사용자 계정을 찾아야 \_ 합니다. UsageLocation -eq $Null}**). 중괄호 안에 있는 명령은 UsageLocation 사용자 계정 속성(.**$ \_ UsageLocation**)이 지정되지 **않았습니다(-eq $Null).**
    
다음 정보를 얻을 수 있습니다.
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

*UsageLocation 속성은* 사용자 계정과 연결된 여러 속성 중 하나일 뿐입니다. 사용자 계정에 대한 모든 속성을 표시하려면 **Select** cmdlet 및 와일드카드 문자(*)를 사용하여 특정 사용자 계정에 대한 모든 속성을 표시합니다. 예를 들면 다음과 같습니다.
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

예를 들어 *City는* 사용자 계정 속성의 이름입니다. 다음 명령을 사용하여 런던에 거주하는 사용자의 모든 사용자 계정을 나열할 수 있습니다.
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  이 예제의 **Where** cmdlet 구문은 **Where {$ \_ 입니다.** [사용자 계정 속성 이름] [비교 연산자] [value] **}**.  [비교 연산자]는 **-eq(같음)** - **ne이면** 같음, **-lt는** 작음, **-gt는** 보다 크면 등입니다.  [value]는 일반적으로 문자열(문자, 숫자 및 기타 문자 시퀀스), 숫자 값  또는 지정되지 않은 $Null 값입니다. 자세한 내용은 [Where를 참조하세요.](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7)
  
사용자 계정의 차단된 상태를 확인하려면 다음 명령을 사용하세요.
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a>계정에 대한 추가 속성 값 보기

기본적으로 **Get-MsolUser** cmdlet은 사용자 계정의 다음 세 가지 속성을 표시합니다.
  
- UserPrincipalName
    
- DisplayName
    
- isLicensed
    
사용자가 작업하는 부서, Microsoft 365 서비스를 사용하는 국가/지역 등의 추가 속성이 필요한 경우 Select cmdlet과 함께  **Get-MsolUser를** 실행하여 사용자 계정 속성 목록을 지정할 수 있습니다. 예를 들면 다음과 같습니다.
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

이 명령은 PowerShell에 지시합니다.
  
1. 사용자 **계정(Get-MsolUser)에** 대한 모든 정보를 확인하여 다음 명령()으로 **|** 전송합니다.
    
1. 사용자 계정 이름, 부서 및 사용 **위치(DisplayName, Department, UsageLocation 선택)만 표시합니다.**
    
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

Select  cmdlet을 사용하면 표시할 속성을 선택할 수 있습니다. 특정 사용자 계정에 대한 모든 속성을 표시하려면 와일드카드 문자(*)를 사용하세요. 예를 들면 다음과 같습니다.
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

표시할 계정 목록에 대해 보다 선택적으로 선택하려면 **Where** cmdlet을 사용할 수도 있습니다. 다음은 지정되지 않은 사용 위치가 있는 사용자 계정만 표시하는 명령의 예입니다.
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

이 명령은 PowerShell에 지시합니다.
  
1. 사용자 **계정(Get-MsolUser)에** 대한 모든 정보를 확인하여 다음 명령()으로 **|** 전송합니다.
    
1. 미지정 사용 위치(Where {$)가 있는 모든 **사용자 계정을 찾아야 \_ 합니다. UsageLocation -eq $Null}를** 사용하여 다음 명령()에 결과 정보를 **|** 전송합니다. 중괄호 안에 있는 명령은 UsageLocation 사용자 계정 속성(.**$ \_ UsageLocation**)이 지정되지 **않았습니다(-eq $Null).**
    
1. 사용자 계정 이름, 부서 및 사용 **위치(DisplayName, Department, UsageLocation 선택)만 표시합니다.**
    
다음 정보를 얻을 수 있습니다.
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

디렉터리 동기화를 사용하여 Microsoft 365 사용자를 만들고 관리하는 경우 Microsoft 365 사용자가 프로젝트된 로컬 계정을 표시할 수 있습니다. 다음 예제에서는 다음을 가정합니다.

- Azure AD Connect는 ObjectGUID의 기본 원본 앵커를 사용하도록 구성됩니다. 원본 앵커 구성에 대한 자세한 내용은 [Azure AD Connect: 디자인 개념을 참조하세요.](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)
- PowerShell용 Active Directory 도메인 서비스 모듈이 [설치되었습니다(RSAT 도구 참조).](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a>참고 항목

[PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[PowerShell로 Microsoft 365 관리](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365용 PowerShell 시작](getting-started-with-microsoft-365-powershell.md)
