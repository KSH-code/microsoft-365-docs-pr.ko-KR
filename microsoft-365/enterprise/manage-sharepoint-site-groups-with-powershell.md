---
title: PowerShell을 사용하여 SharePoint Online 사이트 그룹 관리
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/17/2019
audience: Admin
ms.topic: hub-page
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
- SPO_Content
- seo-marvel-apr2020
ms.assetid: d0d3877a-831f-4744-96b0-d8167f06cca2
description: 이 문서에서는 Microsoft 365용 PowerShell을 사용하여 SharePoint Online 사이트 그룹을 관리하는 절차를 찾아야 합니다.
ms.openlocfilehash: fa9aff769ff84f8567c45b20c7b6c8a078b4a70c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692748"
---
# <a name="manage-sharepoint-online-site-groups-with-powershell"></a>PowerShell을 사용하여 SharePoint Online 사이트 그룹 관리

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

Microsoft 365 관리 센터를 사용할 수 있는 경우 Microsoft 365용 PowerShell을 사용하여 SharePoint Online 사이트 그룹을 관리할 수도 있습니다.

## <a name="before-you-begin"></a>시작하기 전에

이 문서의 절차를 수행하려면 SharePoint Online에 연결해야 합니다. 자세한 내용은 [SharePoint Online PowerShell에 연결합니다.](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

## <a name="view-sharepoint-online-with-powershell-for-microsoft-365"></a>Microsoft 365용 PowerShell을 통해 SharePoint Online 보기

SharePoint Online 관리 센터에는 사이트 그룹을 관리하기 위한 몇 가지 사용이 간편한 방법이 있습니다. 예를 들어 사이트에 대한 그룹 및 그룹 구성원을 살펴보는 경우를 `https://litwareinc.sharepoint.com/sites/finance` 가정해 보겠습니다. 다음과 같은 작업을 해야 합니다.

1. SharePoint 관리 센터에서 활성 사이트를 클릭한 다음 사이트의 URL을 클릭합니다.
2. 사이트 페이지에서 설정 아이콘(페이지의 오른쪽 위 모서리에 있는)을 클릭한 다음 사이트 **권한을 클릭합니다.** 

확인하려는 다음 사이트에 대해 프로세스를 반복합니다.

Microsoft 365용 PowerShell을 사용하여 그룹 목록을 얻습니다. 다음 명령을 사용할 수 있습니다.

```powershell
$siteURL = "https://litwareinc.sharepoint.com/sites/finance"
$x = Get-SPOSiteGroup -Site $siteURL
foreach ($y in $x)
    {
        Write-Host $y.Title -ForegroundColor "Yellow"
        Get-SPOSiteGroup -Site $siteURL -Group $y.Title | Select-Object -ExpandProperty Users
        Write-Host
    }
```

SharePoint Online 관리 셸 명령 프롬프트에서 다음 두 가지 방법으로 이 명령 집합을 실행할 수 있습니다.

- 명령을 메모장(또는 다른 텍스트 편집기)에 **복사하고, $siteURL** 변수의 값을 수정하고, 명령을 선택한 다음 SharePoint Online 관리 셸 명령 프롬프트에 붙여 넣습니다. 그러면 PowerShell이 프롬프트에서 **>>** 중지됩니다. Enter를 눌러 명령을 `foreach` 실행합니다.<br/>
- 명령을 메모장(또는 다른 텍스트 편집기)에 복사하고 **$siteURL** 변수의 값을 수정한 다음 이 텍스트 파일을 적절한 폴더에 이름과 .ps1 확장명으로 저장합니다. 그런 다음 해당 경로와 파일 이름을 지정하여 SharePoint Online 관리 셸 명령 프롬프트에서 스크립트를 실행합니다. 예제 명령은 다음과 같습니다.

```powershell
C:\Scripts\SiteGroupsAndUsers.ps1
```

두 경우 모두 이와 유사한 것을 볼 수 있습니다.

![SharePoint Online 사이트 그룹](../media/SPO-site-groups.png)

이러한 그룹은 사이트에 대해 만들어진 모든 그룹과 해당 그룹에 할당된 `https://litwareinc.sharepoint.com/sites/finance` 모든 사용자입니다. 그룹 이름은 구성원과 그룹 이름을 구분하는 데 도움이 있도록 노란색으로 표시됩니다.

또 다른 예로, 모든 SharePoint Online 사이트에 대한 그룹 및 모든 그룹 구성원을 나열하는 명령 집합이 있습니다.

```powershell
$x = Get-SPOSite
foreach ($y in $x)
    {
        Write-Host $y.Url -ForegroundColor "Yellow"
        $z = Get-SPOSiteGroup -Site $y.Url
        foreach ($a in $z)
            {
                 $b = Get-SPOSiteGroup -Site $y.Url -Group $a.Title 
                 Write-Host $b.Title -ForegroundColor "Cyan"
                 $b | Select-Object -ExpandProperty Users
                 Write-Host
            }
    }
```
    
## <a name="see-also"></a>참고 항목

[SharePoint Online PowerShell에 연결](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[PowerShell을 사용하여 SharePoint Online 사이트 만들기 및 사용자 추가](create-sharepoint-sites-and-add-users-with-powershell.md)

[PowerShell을 사용하여 SharePoint Online 사용자 및 그룹 관리](manage-sharepoint-users-and-groups-with-powershell.md)

[PowerShell로 Microsoft 365 관리](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365 용 PowerShell 시작](getting-started-with-microsoft-365-powershell.md)

