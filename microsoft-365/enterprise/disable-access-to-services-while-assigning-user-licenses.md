---
title: 사용자 라이선스를 할당하는 동안 Microsoft 365 서비스에 대한 액세스 사용 안 하도록 설정
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 04/24/2020
audience: Admin
ms.topic: article
ms.collection: Ent_O365
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
ms.assetid: bb003bdb-3c22-4141-ae3b-f0656fc23b9c
description: PowerShell을 사용하여 사용자 계정에 라이선스를 할당하고 특정 서비스 계획을 동시에 사용하지 않도록 설정하는 방법을 Microsoft 365.
ms.openlocfilehash: 5b7130930097970f5cfabc9a7599c211393b7c7a
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60189168"
---
# <a name="disable-access-to-microsoft-365-services-while-assigning-user-licenses"></a>사용자 라이선스를 할당하는 동안 Microsoft 365 서비스에 대한 액세스 사용 안 하도록 설정

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

Microsoft 365 구독에는 개별 서비스에 대한 서비스 계획이 함께 제공되어 있습니다. Microsoft 365 사용자에게 라이선스를 할당할 때 특정 계획을 사용하지 않도록 설정해야 하는 경우가 종종 있습니다. 이 문서의 지침에 따라 개별 사용자 계정 또는 여러 사용자 계정에 대해 PowerShell을 사용하여 특정 서비스 계획을 사용하지 Microsoft 365 라이선스를 할당할 수 있습니다.

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 모듈용 Azure Active Directory PowerShell 사용하기

먼저 [테넌트 Microsoft 365 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)


다음으로, 이 명령을 사용하여 테넌트에 대한 라이선스 계획을 나열합니다.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

그런 다음 라이선스를 추가할 계정의 로그인 이름을 UPN(사용자 계정 이름)이라고도 합니다.

그런 다음 사용하도록 설정할 서비스 목록을 컴파일합니다. 라이선스 계획(제품 이름), 포함된 서비스 계획 및 해당 식별 이름의 전체 목록은 라이선스에 대한 제품 이름 및 서비스 계획 [식별자를 참조하세요.](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)

아래 명령 블록의 경우 사용자 계정의 사용자 계정 이름, SKU 부분 번호 및 서비스 계획 목록을 입력하여 설명 텍스트와 문자를 사용하도록 설정하고 \< and > 제거합니다. 그런 다음 PowerShell 명령 프롬프트에서 결과 명령을 실행합니다.

```powershell
$userUPN="<user account UPN>"
$skuPart="<SKU part number>"
$serviceList=<double-quoted enclosed, comma-separated list of enabled services>
$user = Get-AzureADUser -ObjectID $userUPN
$skuID= (Get-AzureADSubscribedSku  | Where {$_.SkuPartNumber -eq $skuPart}).SkuID
$SkuFeaturesToEnable = @($serviceList)
$StandardLicense = Get-AzureADSubscribedSku | Where {$_.SkuId -eq $skuID}
$SkuFeaturesToDisable = $StandardLicense.ServicePlans | ForEach-Object { $_ | Where {$_.ServicePlanName -notin $SkuFeaturesToEnable }}
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = $StandardLicense.SkuId
$License.DisabledPlans = $SkuFeaturesToDisable.ServicePlanId
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $user.ObjectId -AssignedLicenses $LicensesToAssign
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell용 Microsoft Azure Active Directory 모듈 사용하기

먼저 [테넌트 Microsoft 365 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

다음으로, 다음 명령을 실행하여 현재 구독을 봐야 합니다.

```powershell
Get-MsolAccountSku
```

>[!Note]
>PowerShell Core는 Windows PowerShell용 Microsoft Azure Active Directory 모듈 및 이름에 **Msol** 이 있는 cmdlet을 지원하지 않습니다. 이러한 cmdlet을 계속 사용하려면 Windows PowerShell에서 이를 실행해야 합니다.
>

명령 표시에서  `Get-MsolAccountSku` 다음을 실행합니다.

- **AccountSkuId는** 조직의 \<OrganizationName> 구독(형식)입니다. \<Subscription> 는 조직에 등록할 때 제공한 Microsoft 365 \<OrganizationName> 고유합니다. 값은 \<Subscription> 특정 구독에 대한 것입니다. 예를 들어 litwareinc:ENTERPRISEPACK의 경우 조직 이름은 litwareinc, 구독 이름은 ENTERPRISEPACK(Office 365 Enterprise E3)입니다.

- **ActiveUnits는** 구독을 위해 구입한 라이선스 수입니다.

- **WarningUnits는** 갱신하지 않은 구독의 라이선스 수로, 30일 유예 기간 후에 만료됩니다.

- **ConsumedUnits는** 구독에 대해 사용자에게 할당한 라이선스 수입니다.

라이선스를 부여할 사용자가 Microsoft 365 구독의 AccountSkuId를 참고하십시오. 또한 할당할 수 있는 라이선스가 충분한지 **확인(ActiveUnits에서 ConsumedUnits 빼기).** 

다음으로, 다음 명령을 실행하여 모든 구독에서 사용할 수 있는 Microsoft 365 서비스 계획에 대한 세부 정보를 봐야 합니다.

```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

이 명령이 표시되어 있는 경우 사용자에게 라이선스를 할당할 때 사용하지 않도록 설정할 서비스 계획을 결정해야 합니다.

다음은 서비스 계획 및 해당 서비스 계획의 일부 Microsoft 365 있습니다.

다음 표에는 서비스 Microsoft 365 가장 일반적인 서비스에 대한 이름 및 서비스 계획이 표시됩니다. 서비스 계획 목록이 다를 수도 있습니다.

|**서비스 계획**|**설명**|
|:-----|:-----|
| `SWAY` <br/> |Sway  <br/> |
| `TEAMS1` <br/> |Microsoft Teams  <br/> |
| `YAMMER_ENTERPRISE` <br/> |Yammer  <br/> |
| `RMS_S_ENTERPRISE` <br/> |RMS(Azure 권한 관리)  <br/> |
| `OFFICESUBSCRIPTION` <br/> |*엔터프라이즈용 Microsoft 365 앱(이전에는 Office 365 ProPlus)*  <br/> |
| `MCOSTANDARD` <br/> |비즈니스용 Skype Online  <br/> |
| `SHAREPOINTWAC` <br/> |Office   <br/> |
| `SHAREPOINTENTERPRISE` <br/> |SharePoint Online  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |Exchange Online 계획 2  <br/> |

라이선스 계획(제품 이름), 포함된 서비스 계획 및 해당 식별 이름의 전체 목록은 라이선스에 대한 제품 이름 및 서비스 계획 [식별자를 참조하세요.](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)

이제 사용하지 않도록 설정할 AccountSkuId 및 서비스 계획이 준비되어 있습니다. 개별 사용자 또는 여러 사용자에 대해 라이선스를 할당할 수 있습니다.

### <a name="for-a-single-user"></a>단일 사용자의 경우

단일 사용자의 경우 사용자 계정의 사용자 계정 이름, AccountSkuId 및 서비스 계획 목록을 입력하여 설명 텍스트와 문자를 사용하지 않도록 설정하고 \< and > 제거합니다. 그런 다음 PowerShell 명령 프롬프트에서 결과 명령을 실행합니다.

```powershell
$userUPN="<the user's account name in email format>"
$accountSkuId="<the AccountSkuId from the Get-MsolAccountSku command>"
$planList=@( <comma-separated, double-quote enclosed list of the service plans to disable> )
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
Set-MsolUserLicense -UserPrincipalName $userUpn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
Sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $userUpn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
```

다음은 belindan@contoso.com 계정, contoso:ENTERPRISEPACK 라이선스에 대한 명령 블록의 예입니다. 사용하지 않도록 설정할 서비스 계획은 RMS_S_ENTERPRISE, SWAY, INTUNE_O365 및 YAMMER_ENTERPRISE.

```powershell
$userUPN="belindan@contoso.com"
$accountSkuId="contoso:ENTERPRISEPACK"
$planList=@( "RMS_S_ENTERPRISE","SWAY","INTUNE_O365","YAMMER_ENTERPRISE" )
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
Set-MsolUserLicense -UserPrincipalName $userUpn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
Sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $userUpn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
```

### <a name="for-multiple-users"></a>여러 사용자의 경우

여러 사용자에 대해 이 관리 작업을 수행하기 위해 UserPrincipalName 및 UsageLocation 필드가 포함된 CSV(콤보로 구분된 값) 텍스트 파일을 만들어야 합니다. 예를 들면 다음과 같습니다.

```powershell
UserPrincipalName,UsageLocation
ClaudeL@contoso.onmicrosoft.com,FR
LynneB@contoso.onmicrosoft.com,US
ShawnM@contoso.onmicrosoft.com,US
```

다음으로, 입력 및 출력 CSV 파일의 위치, 계정 SKU ID 및 사용하지 않도록 설정할 서비스 계획 목록을 입력한 다음 PowerShell 명령 프롬프트에서 결과 명령을 실행합니다.

```powershell
$inFileName="<path and file name of the input CSV file that contains the users, example: C:\admin\Users2License.CSV>"
$outFileName="<path and file name of the output CSV file that records the results, example: C:\admin\Users2License-Done.CSV>"
$accountSkuId="<the AccountSkuId from the Get-MsolAccountSku command>"
$planList=@( <comma-separated, double-quote enclosed list of the plans to disable> )
$users=Import-Csv $inFileName
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
ForEach ($user in $users)
{
$user.Userprincipalname
$upn=$user.UserPrincipalName
Set-MsolUserLicense -UserPrincipalName $upn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $upn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
$users | Get-MsolUser | Select UserPrincipalName, Islicensed,Usagelocation | Export-Csv $outFileName
}
```

이 PowerShell 명령 블록:

- 각 사용자의 사용자 계정 이름을 표시됩니다.

- 사용자 지정된 라이선스를 각 사용자에게 할당합니다.

- 처리된 모든 사용자와 함께 CSV 파일을 만들고 라이선스 상태를 보여줍니다.

## <a name="see-also"></a>참고 항목

[PowerShell을 Microsoft 365 서비스에 액세스하지 않도록 설정](disable-access-to-services-with-microsoft-365-powershell.md)

[PowerShell을 통해 Sway에 액세스하지 않도록 설정](disable-access-to-sway-with-microsoft-365-powershell.md)

[PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)

[PowerShell로 Microsoft 365 관리](manage-microsoft-365-with-microsoft-365-powershell.md)