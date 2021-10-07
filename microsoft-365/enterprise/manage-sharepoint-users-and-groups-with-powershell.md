---
title: PowerShell을 사용하여 SharePoint 온라인 사용자 및 그룹 관리
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 07/17/2020
audience: Admin
ms.topic: hub-page
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
- SPO_Content
- seo-marvel-apr2020
ms.assetid: d0d3877a-831f-4744-96b0-d8167f06cca2
description: 이 문서에서는 PowerShell을 사용하여 온라인 사용자, 그룹 및 Microsoft 365 관리하기 SharePoint 방법을 학습합니다.
ms.openlocfilehash: 10991c2ac065331ab8eff3e782cecbdbcc5d034b
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60173382"
---
# <a name="manage-sharepoint-online-users-and-groups-with-powershell"></a>PowerShell을 사용하여 SharePoint 온라인 사용자 및 그룹 관리

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

대규모 사용자 계정 SharePoint 그룹과 함께 작업하며 보다 쉽게 관리할 수 있는 방법을 원하는 온라인 관리자인 경우 사용자용 PowerShell을 Microsoft 365.

시작하기 전에 이 항목의 절차를 수행하려면 SharePoint 온라인에 연결해야 합니다. 자세한 내용은 온라인 [powerShell을 커넥트 SharePoint 참조하세요.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

## <a name="get-a-list-of-sites-groups-and-users"></a>사이트, 그룹, 사용자 목록 가져오기

사용자 및 그룹 관리를 시작하려면 먼저 사이트, 그룹 및 사용자 목록을 가져와야 합니다. 그리고 나면 해당 정보를 이 문서의 예제 전반에 걸쳐 사용할 수 있습니다.

이 명령을 사용하여 테넌트의 사이트 목록을 가져옵니다.

```powershell
Get-SPOSite
```

이 명령을 사용하여 테넌트의 그룹 목록을 가져옵니다.

```powershell
Get-SPOSite | ForEach {Get-SPOSiteGroup -Site $_.Url} | Format-Table
```

이 명령을 사용하여 테넌트의 사용자 목록을 가져옵니다.

```powershell
Get-SPOSite | ForEach {Get-SPOUser -Site $_.Url}
```

## <a name="add-a-user-to-the-site-collection-administrators-group"></a>사이트 모음 관리자 그룹에 사용자 추가

이 cmdlet을 사용하여 사이트 모음의 사이트 모음 관리자 목록에 `Set-SPOUser` 사용자를 추가합니다.

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
 ```

이러한 명령을 사용하 여, 따옴표 안에 있는 모든 것을 올바른 이름으로 < > 문자를 바른 이름으로 바하십시오.

예를 들어 이 명령 집합은 Opal Castillo(사용자 이름 opalc)를 Contoso 테넌시의 ContosoTest 사이트 모음에 있는 사이트 모음 관리자 목록에 추가합니다.

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "opalc"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
```

이러한 명령을 복사하여 메모장, $tenant, $site 및 $user 변수 값을 환경의 실제 값으로 변경한 다음 SharePoint Online 관리 셸 창에 붙여 넣으면 실행할 수 있습니다.

## <a name="add-a-user-to-other-site-collection-groups"></a>다른 사이트 모음 그룹에 사용자 추가

이 작업에서는 cmdlet을 사용하여 사이트 모음의 SharePoint `Add-SPOUser` 그룹에 사용자를 추가합니다.

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site

```

예를 들어 Glen Rife(사용자 이름 glenr)를 contoso 테넌시의 ContosoTest 사이트 모음에 있는 감사자 그룹에 추가해 보겠습니다.

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "glenr"
$group = "Auditors"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="create-a-site-collection-group"></a>사이트 모음 그룹 만들기

이 cmdlet을 사용하여 새 SharePoint 그룹을 만들어 사이트 모음에 `New-SPOSiteGroup` 추가합니다.

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$group = "<group name name, such as Auditors>"
$level = "<permission level, such as View Only>"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```

권한 수준과 같은 그룹 속성은 나중에 `Set-SPOSiteGroup` cmdlet을 사용하여 업데이트할 수 있습니다.

예를 들어 보기 전용 권한이 있는 감사자 그룹을 contoso 테넌시의 contosotest 사이트 모음에 추가해 보겠습니다.

```powershell
$tenant = "contoso"
$site = "contosotest"
$group = "Auditors"
$level = "View Only"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="remove-users-from-a-group"></a>그룹에서 사용자 제거

사이트 하나 또는 모든 사이트에서 사용자를 제거해야 하는 경우가 있습니다. 직원이 사업부를 이동하거나 퇴사하는 경우를 예로 들 수 있습니다. 직원이 한 명이라면 UI에서 이 작업을 쉽게 수행할 수 있습니다. 그러나 전체 사업부를 사이트 간에 이동해야 하는 경우에는 쉽지 않습니다.

그러나 온라인 관리 SharePoint CSV 파일을 사용하여 빠르고 쉽게 사용할 수 있습니다. 이 작업에서는 Windows PowerShell을 사용하여 사이트 모음 보안 그룹에서 사용자를 제거합니다. 그런 다음 CSV 파일을 사용해 여러 사이트에서 다수의 사용자를 제거합니다.

명령 구문을 볼 수 있도록 'Remove-SPOUser' cmdlet을 사용하여 사이트 Microsoft 365 그룹에서 단일 사용자만 제거합니다. 이 작업을 위한 구문은 다음과 같습니다.

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Remove-SPOUser -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site -Group $group
```

예를 들어 contoso 테넌시의 contosotest 사이트 모음에 있는 사이트 모음 감사자 그룹에서 Bobby Overby를 제거해 보겠습니다.

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "bobbyo"
$group = "Auditors"
Remove-SPOUser -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site -Group $group
```

다음으로는 Bobby를 현재 포함되어 있는 모든 그룹에서 제거해 보겠습니다.

```powershell
$tenant = "contoso"
$user = "bobbyo"
Get-SPOSite | ForEach {Get-SPOSiteGroup –Site $_.Url} | ForEach {Remove-SPOUser -LoginName $user@$tenant.com -Site &_.Url}
```

> [!WARNING]
> 이는 예일 수 있습니다. 실제로 사용자가 퇴사하는 경우 등 모든 그룹에서 사용자를 제거해야 하는 경우가 아니면 이 명령을 실행해서는 안 됩니다.

## <a name="automate-management-of-large-lists-of-users-and-groups"></a>대형 사용자 및 그룹 목록의 관리 자동화

사이트 SharePoint 많은 계정을 추가하고 사용 권한을 부여하려면 Microsoft 365 관리 센터, 개별 PowerShell 명령 또는 PowerShell을 CSV 파일을 사용할 수 있습니다. 이중에서 CSV 파일이 작업을 자동화하는 가장 빠른 방법입니다.

기본적인 프로세스는 Windows PowerShell 스크립트에 필요한 매개 변수에 해당하는 헤더(열)가 포함된 CSV 파일을 만드는 것입니다. 목록에서 이러한 목록을 Excel CSV 파일로 내보낼 수 있습니다. 그런 다음 Windows PowerShell 스크립트를 사용하여 CSV 파일에서 레코드(행)를 반복해 사용자를 그룹에, 그룹을 사이트에 추가합니다.

예를 들어 사이트 모음, 그룹 및 사용 권한 그룹을 정의하는 CSV 파일을 만들어 보겠습니다. 다음으로는 CSV 파일을 만들어 그룹에 사용자를 채웁니다. 마지막으로 그룹을 만들고 채우는 간단한 Windows PowerShell 스크립트를 만들어 실행합니다.

다음과 같은 구조의 첫 번째 CSV 파일은 하나 이상의 그룹을 하나 이상의 사이트 모음에 추가합니다.

헤더:

```powershell
Site,Group,PermissionLevels
```

항목:

```powershell
https://tenant.sharepoint.com/sites/site,group,level
```

예제 파일은 다음과 같습니다.

```powershell
Site,Group,PermissionLevels
https://contoso.sharepoint.com/sites/contosotest,Contoso Project Leads,Full Control
https://contoso.sharepoint.com/sites/contosotest,Contoso Auditors,View Only
https://contoso.sharepoint.com/sites/contosotest,Contoso Designers,Design
https://contoso.sharepoint.com/sites/TeamSite01,XT1000 Team Leads,Full Control
https://contoso.sharepoint.com/sites/TeamSite01,XT1000 Advisors,Edit
https://contoso.sharepoint.com/sites/Blog01,Contoso Blog Designers,Design
https://contoso.sharepoint.com/sites/Blog01,Contoso Blog Editors,Edit
https://contoso.sharepoint.com/sites/Project01,Project Alpha Approvers,Full Control
```

다음과 같은 구조의 두 번째 CSV 파일은 한 명 이상의 사용자를 하나 이상의 그룹에 추가합니다.

헤더:

```powershell
Group,LoginName,Site
```

항목:

```powershell
group,login,https://tenant.sharepoint.com/sites/site
```

예제 파일은 다음과 같습니다.

```powershell
Group,LoginName,Site
Contoso Project Leads,bobbyo@contoso.com,https://contoso.sharepoint.com/sites/contosotest
Contoso Auditors,allieb@contoso.com,https://contoso.sharepoint.com/sites/contosotest
Contoso Designers,bonniek@contoso.com,https://contoso.sharepoint.com/sites/contosotest
XT1000 Team Leads,dorenap@contoso.com,https://contoso.sharepoint.com/sites/TeamSite01
XT1000 Advisors,garthf@contoso.com,https://contoso.sharepoint.com/sites/TeamSite01
Contoso Blog Designers,janets@contoso.com,https://contoso.sharepoint.com/sites/Blog01
Contoso Blog Editors,opalc@contoso.com,https://contoso.sharepoint.com/sites/Blog01
Project Alpha Approvers,robinc@contoso.com,https://contoso.sharepoint.com/sites/Project01
```

그런 다음 해당 드라이브에 CSV 파일 두 개가 저장되어 있어야 합니다. 다음은 두 CSV 파일을 모두 사용하여 사용 권한 및 그룹 구성원을 추가하는 예제 명령입니다.

```powershell
Import-Csv C:\O365Admin\GroupsAndPermissions.csv | ForEach {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
Import-Csv C:\O365Admin\Users.csv | ForEach {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
```

이 스크립트는 CSV 파일 내용을 가져오고 열의 값을 사용하여 **New-SPOSiteGroup** 및 **Add-SPOUser** 명령의 매개 변수를 채우습니다. 이 예제에서는 C 드라이브의O365Admin 폴더에 저장하지만 원하는 모든 곳에 저장할 수 있습니다.

이제 동일한 CSV 파일을 사용하여 서로 다른 사이트의 여러 그룹에 대해 여러 사용자 그룹을 제거해보아야 합니다. 예제 명령은 다음과 같습니다.

```powershell
Import-Csv C:\O365Admin\Users.csv | ForEach {Remove-SPOUser -LoginName $_.LoginName -Site $_.Site -Group $_.Group}
```

## <a name="generate-user-reports"></a>사용자 보고서 생성

사이트 몇 개에 대해 간단한 보고서를 가져와 해당 사이트의 사용자, 사용자의 사용 권한 수준 및 기타 속성을 표시할 수 있습니다. 이 작업을 위한 구문은 다음과 같습니다.

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | select * | Format-table -Wrap -AutoSize | Out-File c\UsersReport.txt -Force -Width 360 -Append
```

이 구문은 3개 사이트의 데이터를 가져와 로컬 드라이브의 텍스트 파일에 기록합니다. –Append 매개 변수는 기존 파일에 새 콘텐츠를 추가합니다.

예를 들어 Contoso1 테넌트의 ContosoTest, TeamSite01 및 Project01 사이트에 대한 보고서를 실행해 보겠습니다.

```powershell
$tenant = "contoso"
$site = "contosotest"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
$site = "TeamSite01"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site |Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
$site = "Project01"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
```

이 경우 변수 변수만 **변경해야 $site** 있습니다. $tenant  변수는 세 번의 명령 실행을 모두 통해 값을 유지할 수 있습니다.

모든 사이트에 대해 이 작업을 수행하려는 경우 다음 명령을 사용하면 모든 웹 사이트를 입력하지 않고도 작업을 수행할 수 있습니다.

```powershell
Get-SPOSite | ForEach {Get-SPOUser –Site $_.Url} | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
```

이 보고서는 매우 단순하므로 코드를 더 추가하여 더 자세한 정보를 포함하는 보고서나 보다 구체적인 보고서를 만들 수도 있습니다. 그러나 이 방법을 통해 SharePoint Online 환경에서 사용자를 관리하는 방법을 SharePoint 있습니다.

## <a name="see-also"></a>참고 항목

[커넥트 PowerShell을 SharePoint 수 있습니다.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

[PowerShell로 SharePoint 온라인 관리](create-sharepoint-sites-and-add-users-with-powershell.md)

[PowerShell로 Microsoft 365 관리](manage-microsoft-365-with-microsoft-365-powershell.md)

[Microsoft 365 용 PowerShell 시작](getting-started-with-microsoft-365-powershell.md)
