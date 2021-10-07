---
title: 중앙 집중식 배포 PowerShell cmdlet을 사용하여 추가 기능 관리
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 1/24/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BCS160
f1.keywords:
- NOCSH
ms.assetid: 94f4e86d-b8e5-42dd-b558-e6092f830ec9
ms.custom:
- seo-marvel-apr2020
description: 중앙 집중식 배포 PowerShell cmdlet을 사용하여 조직에 대한 Office 추가 기능을 배포하고 Microsoft 365 있습니다.
ms.openlocfilehash: 6d99b3867560f7eba0f143933d996e4e30b8c7c4
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60173226"
---
# <a name="use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins"></a>중앙 집중식 배포 PowerShell cmdlet을 사용하여 추가 기능 관리

전역 Microsoft 365 중앙 집중식 배포 기능을 통해 Office 추가 기능을 배포할 수 있습니다(관리 센터에서 Office 추가 기능 배포 [참조).](../admin/manage/manage-deployment-of-add-ins.md) 추가 기능을 Office 추가 기능을 배포하는 Microsoft 365 관리 센터 Microsoft PowerShell을 사용할 수 있습니다. 에 대한 [O365](https://www.powershellgallery.com/packages/O365CentralizedAddInDeployment)중앙 집중식 Add-In 배포 모듈을 Windows PowerShell. 

모듈을 다운로드한 후 일반 Windows PowerShell 열고 다음 cmdlet을 실행합니다.

```powershell
 Import-Module -Name O365CentralizedAddInDeployment
```
    
## <a name="connect-using-your-admin-credentials"></a>커넥트 자격 증명 사용

중앙 집중식 배포 cmdlet을 사용하려면 먼저 로그인해야 합니다.
  
1. PowerShell을 시작 합니다.
    
2. 커넥트 자격 증명을 사용하여 PowerShell에 연결합니다. 다음 cmdlet을 실행합니다.
    
  ```powershell
  Connect-OrganizationAddInService
  ```

3. 자격 **증명 입력 페이지에서** 사용자 Microsoft 365 또는 전역 관리자 자격 **증명을 입력합니다.** 또는 cmdlet에 자격 증명을 직접 입력할 수 있습니다. 
    
    회사 관리자 자격 증명을 PSCredential 개체로 지정하는 다음 cmdlet을 실행합니다.
    
  ```powershell
  $secpasswd = ConvertTo-SecureString "MyPassword" -AsPlainText -Force
  $mycredentials = New-Object System.Management.Automation.PSCredential ("serviceaccount@contoso.com", $secpasswd)
  Connect-OrganizationAddInService -Credential $mycredentials
  ```

> [!NOTE]
> PowerShell 사용에 대한 자세한 내용은 PowerShell을 사용하여 커넥트 [Microsoft 365 참조하세요.](./connect-to-microsoft-365-powershell.md) 
  
## <a name="upload-an-add-in-manifest"></a>업로드 매니페스트

**New-OrganizationAdd-In** cmdlet을 실행하여 파일 위치 또는 URL일 수 있는 경로에서 추가 기능 매니페스트를 업로드합니다. 다음 예제에서는  _ManifestPath_ 매개 변수의 값에 대한 파일 위치를 보여 제공합니다. 
  
```powershell
New-OrganizationAddIn -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US'
```

다음 예와 같이 **New-OrganizationAdd-In** cmdlet을 실행하여 추가 기능을 업로드하고  _Members_ 매개 변수를 사용하여 사용자 또는 그룹에 직접 할당할 수도 있습니다. 구성원의 전자 메일 주소를 콤보로 구분합니다. 
  
```powershell
New-OrganizationAddIn -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US' -Members  'KathyBonner@contoso.com', 'MaxHargrave@contoso.com'
```

## <a name="upload-an-add-in-from-the-office-store"></a>업로드 스토어에서 추가 Office 추가 기능

**New-OrganizationAddIn** cmdlet을 실행하여 Office 스토어에서 매니페스트를 업로드합니다.
  
다음 예제에서 **New-OrganizationAddIn** cmdlet은 미국 위치 및 콘텐츠 시장용 추가 기능의 AssetId를 지정합니다.
  
```powershell
New-OrganizationAddIn -AssetId 'WA104099688' -Locale 'en-US' -ContentMarket 'en-US'
```

_AssetId_ 매개 변수의 값을 확인하기 위해 추가 기능의 Store 웹 Office URL에서 복사하면 됩니다. AssetIds는 항상 "WA"로 시작하고 그 다음에 숫자가 오게 됩니다. 예를 들어 이전 예제에서 ASSETId 값 WA104099688의 원본은 추가 기능의 Office Store 웹 페이지 URL입니다. [https://store.office.com/en-001/app.aspx?assetid=WA104099688](https://store.office.com/en-001/app.aspx?assetid=WA104099688)
  
_Locale_ 매개 변수 및 _ContentMarket_ 매개 변수의 값은 동일하며 추가 기능을 설치하려는 국가/지역을 나타냅니다. 형식은 en-US, fr-FR입니다. 등입니다. 
  
> [!NOTE]
> Office 스토어에서 업로드한 추가 기능은 Office 스토어에서 사용할 수 있는 최신 업데이트로부터 며칠 내에 자동으로 업데이트됩니다. 
  
## <a name="get-details-of-an-add-in"></a>추가 기능 세부 정보 확인

아래와 같이 **Get-OrganizationAddIn** cmdlet을 실행하여 테넌트에 업로드된 모든 추가 기능, 추가 기능의 제품 ID에 대한 세부 정보를 확인하세요.
  
```powershell
Get-OrganizationAddIn
```

_ProductId_ 매개 변수의 값과 함께 **Get-OrganizationAddIn** cmdlet을 실행하여 세부 정보를 검색할 추가 기능을 지정합니다. 
  
```powershell
Get-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122
```

모든 추가 기능 및 할당된 사용자 및 그룹에 대한 전체 세부 정보를 얻습니다. 다음 예와 같이 **Get-OrganizationAddIn** cmdlet의 출력을 Format-List cmdlet으로 파이프합니다.
  
```powershell
foreach($G in (Get-organizationAddIn)){Get-OrganizationAddIn -ProductId $G.ProductId | Format-List}
```

## <a name="turn-on-or-turn-off-an-add-in"></a>추가 기능 켜기 또는 끄기

추가 기능을 해제하여 할당된 사용자 및 그룹에 더 이상 액세스 권한이 부여되지 않습니다. 다음 예와 같이 _ProductId_ 매개 변수와 _Enabled_ 매개 변수를 로 설정하여 **Set-OrganizationAddIn** cmdlet을 `$false` 실행합니다.
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Enabled $false
```

추가 기능을 다시 켜기 위해 Enabled 매개 변수가 로 설정된  _동일한_ cmdlet을  `$true` 실행합니다.
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Enabled $true
```

## <a name="add-or-remove-users-from-an-add-in"></a>추가 기능에서 사용자 추가 또는 제거

사용자 및 그룹을 특정 추가 기능에 추가하기 위해 _ProductId,_ _Add_ 및 Members 매개 변수를 사용하여 **Set-OrganizationAddInAssignments** cmdlet을 _실행합니다._ 구성원의 전자 메일 주소를 콤보로 구분합니다. 
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Add -Members 'KathyBonner@contoso.com','sales@contoso.com'
```

사용자 및 그룹을 제거하려면 Remove 매개 변수를 사용하여 동일한 cmdlet을 _실행합니다._ 
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Remove -Members 'KathyBonner@contoso.com','sales@contoso.com'
```

테넌트의 모든 사용자에게 추가 기능을 할당하기 위해 값이 로 설정된  _AssignToEveryone_ 매개 변수를 사용하여 동일한 cmdlet을  `$true` 실행합니다.
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -AssignToEveryone $true
```

모든 사용자에게 추가 기능을 할당하지 말고 이전에 할당된 사용자 및 그룹으로 되 돌리기 위해 동일한 cmdlet을 실행하고 해당 값을 로 설정하여  _AssignToEveryone_ 매개 변수를 해제할 수  `$false` 있습니다.
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -AssignToEveryone $false
```

## <a name="update-an-add-in"></a>추가 기능 업데이트

매니페스트에서 추가 기능을 업데이트하기 위해 다음 예제와 같이 _ProductId,_ _ManifestPath_ 및 _Locale_ 매개 변수를 사용하여 **Set-OrganizationAddIn** cmdlet을 실행합니다. 
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US'
```

> [!NOTE]
> Office 스토어에서 업로드한 추가 기능은 Office 스토어에서 사용할 수 있는 최신 업데이트로부터 며칠 내에 자동으로 업데이트됩니다. 
  
## <a name="delete-an-add-in"></a>추가 기능 삭제

추가 기능을 삭제하려면 다음 예와 같이 _ProductId_ 매개 변수를 사용하여 **Remove-OrganizationAddIn** cmdlet을 실행합니다. 
  
```powershell
Remove-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122
```

<!--
## Customize Microsoft Store add-ins for your organization

You must customize the add-in before you deploy it to your organization. Add-ins older than version 1.1 are not supported by this feature. 

We recommend that you deploy a customized add-in  to yourself first to make sure it works as expected before you deploy it to your entire organization.

Note also the following restrictions:
- All URLs must be absolute (include http or https) and valid.
- *DisplayName* must not exceed 125 characters 
- *DisplayName*, *Resources* and *AppDomains* must not include the following characters: 
 
    - \<
    -  \>
    -  ;
    -  =   

If you want to customize an add-in that has been deployed, you have to uninstall it in the admin center, and see [remove an add-in from local cache](#remove-an-add-in-from-local-cache) for steps to remove it from each computer it has been deployed to.

To customize an add-in, run the **Set –OrganizationAddInOverrides** cmdlet with the *ProductId* as a parameter, followed by the tag you want to overwrite and the new value. To find out how to get the *ProductId* see [get details of an add-in](#get-details-of-an-add-in) in this article. For example:

```powershell
 Set-OrganizationAddInOverrides -ProductId 5b31b349-2c41-4f94-b720-6ee40349d391 -IconUrl "https://site.com/img.jpg" 
```
To customize multiple tags for an add-in, add those tags to the commandline:

```powershell
Set-OrganizationAddInOverrides -ProductId 5b31b349-2c41-4f94-b720-6ee40349d391 -Hosts h1, 2 -DisplayName "New DocuSign W" -IconUrl "https://site.com/img.jpg" 
```

> [!IMPORTANT]
> You must apply multiple customized tags to one add-in as one command. If you customize tags one by one, only the last customization will be applied. Additionally, if you customize a tag by mistake, you must remove all customizations and start over.

### Tags you can customize

| Tag                  | Description          |
| :------------------- | :------------------- |
| \<IconURL>   </br>| The URL of the image used as the add-in’s icon (in admin center). </br> |
| \<DisplayName>| The title of the add-in  (in admin center).|
| \<Hosts>| List of apps that will support the add-in.|
| \<SourceLocation> | The source URL that the add-in will connect to.| 
| \<AppDomains> | A list of domains that the add-in can connect with. | 
| \<SupportURL>| The URL users can use to access help and support. | 
| \<Resources>  | This tag contains a number of elements including titles, tooltips, and icons of different sizes.| 
|
### Customize Resources tag

Any element in the <Resources> tag of the manifest can be customized dynamically. You first need to check the manifest to find the element id to which you want to assign a new value. The <Resources> tag looks like this:

```
<Resources>  
    <bt:Images> 
          <bt:Image id=”img16icon” DefaultValue=”https://site.com/img.jpg” 
    </bt:Images> 
</Resources> 
``` 
In this case, the element id for the image is “img16icon” and the value associated with it is “http:<i></i>//site.<i></i>com/img.jpg.”

Once you have identified the elements you want to customize, use the following command in Powershell to assign new values to the elements:

```powershell
Set-OrganizationAddInOverrides -Resources @{“ElementID” = “New Value”; “NextElementID” = “Next New Value”} 
```

You can customize as many elements with the command as you need to.

### Remove customization from an add-in

The only option currently available for deleting customizations is to delete all of them at once:

```powershell
Remove-OrganizationAddInOverrides -ProductId 5b31b349-2c41-4f94-b720-6ee40349d391 
```

### View add-in customizations

To view a list of applied customizations, run the **Get-OrganizationAddInOverrides** cmdlet. If **Get-OrganizationAddInOverrides** is run without a *ProductId* then a list of all add-ins with applied overrides are returned.  

```powershell
Get-OrganizationAddInOverrides 
```
If ProductId is specified, then a list of overrides applied to that add-in is returned. 

```powershell
Get-OrganizationAddInOverrides -ProductId 5b31b349-2c41-4f94-b720-6ee40349d391 
```

### Remove an add-in from local cache

If an add-in has been deployed, it has to be removed from the cache in each computer before it can be customized. To remive an add-in from cache:

1. Navigate to the “Users” folder in C:\ 
1. Go to your user folder
1. Navigate to AppData\Local\Microsoft\Office and select the folder associated with your version of Office
1. In the *Wef* folder delete the *Manifests* folder.

-->

## <a name="get-detailed-help-for-each-cmdlet"></a>각 cmdlet에 대한 자세한 도움말 확인

Get-help cmdlet을 사용하여 각 cmdlet에 대한 자세한 도움말을 볼 수 있습니다. 예를 들어 다음 cmdlet은 cmdlet에 대한 자세한 Remove-OrganizationAddIn 제공합니다.
  
```powershell
Get-help Remove-OrganizationAddIn -Full
```
