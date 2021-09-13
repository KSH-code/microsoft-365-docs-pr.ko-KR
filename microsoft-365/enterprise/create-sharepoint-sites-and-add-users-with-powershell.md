---
title: PowerShell을 SharePoint 온라인 사이트 만들기 및 사용자 추가
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
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
description: '요약: PowerShell을 사용하여 온라인 SharePoint 새 사이트를 만든 다음 해당 사이트에 사용자 및 그룹을 추가합니다.'
ms.openlocfilehash: c9a55c6373e2ecc81c59b2e1bf2d1b8850dd1c13
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59218605"
---
# <a name="create-sharepoint-online-sites-and-add-users-with-powershell"></a>PowerShell을 SharePoint 온라인 사이트 만들기 및 사용자 추가

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

Microsoft 365 PowerShell을 사용하여 SharePoint 온라인 사이트를 만들고 사용자를 추가할 때 작업 실행 속도보다 훨씬 빠르고 반복적으로 작업을 Microsoft 365 관리 센터. 또한 작업 실행에서 수행할 수 없는 작업을 수행할 Microsoft 365 관리 센터.

## <a name="connect-to-sharepoint-online"></a>SharePoint Online에 연결

이 항목의 절차를 수행하려면 온라인에서 SharePoint 합니다. 자세한 내용은 온라인 [powerShell을 커넥트 SharePoint 참조하세요.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

## <a name="step-1-create-new-site-collections-using-powershell"></a>1단계: PowerShell을 사용하여 새 사이트 모음 만들기

PowerShell 및 .csv 예제 코드를 사용하여 만든 사이트와 예제 파일을 사용하여 여러 사이트를 메모장. 이 절차에서는 괄호로 표시된 자리 표시자 정보를 자체 사이트 및 테넌트 관련 정보로 바꾸게 됩니다. 이 프로세스를 통해 단일 파일을 만들고 해당 파일을 사용하는 단일 PowerShell 명령을 실행할 수 있습니다. 이렇게 하면 반복 및 이식 가능 작업을 모두 수행할 수 있으며, 긴 명령을 SharePoint 경우 발생할 수 있는 많은 오류가 제거됩니다. 이 절차에는 두 부분으로 구성됩니다. 먼저 .csv 파일을 만든 다음 PowerShell을 사용하여 해당 .csv 해당 파일을 참조합니다. 이 파일을 사용하여 사이트를 만들게 됩니다.

PowerShell cmdlet은 .csv 파일을 가져와 파일의 첫 줄을 열 머리더로 읽는 중괄호 안의 루프에 파이프합니다. 그런 다음 PowerShell cmdlet은 나머지 레코드를 계속 진행하고 각 레코드에 대해 새 사이트 모음을 만들고 열 머리더에 따라 사이트 모음의 속성을 할당합니다.

### <a name="create-a-csv-file"></a>.csv 파일 만들기

> [!NOTE]
> 리소스 할당량 매개 변수는 클래식 사이트에서만 작동합니다. 최신 사이트에서 이 매개 변수를 사용하는 경우 더이상 사용되지 않을 것 같은 경고 메시지가 표시될 수 있습니다.

1. 메모장을 열고 다음 텍스트 블록을 붙여 넣습니다.

   ```powershell
   Owner,StorageQuota,Url,ResourceQuota,Template,TimeZoneID,Name
   owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/TeamSite01,25,EHS#1,10,Contoso Team Site
   owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/Blog01,25,BLOG#0,10,Contoso Blog
   owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Project01,25,PROJECTSITE#0,10,Project Alpha
   owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Community01,25,COMMUNITY#0,10,Community Site
   ```

   여기서 *테넌트는* 테넌트의  이름이고 소유자는 기본 사이트 모음 관리자의 역할을 부여할 테넌트에 있는 사용자의 사용자 이름입니다.

   Ctrl+H를 누를 경우 Ctrl+H를 메모장 빠르게 바꿀 수 있습니다.

2. 바탕 화면에 파일을 100으로 **SiteCollections.csv.**

> [!TIP]
> 이 또는 다른 .csv Windows PowerShell 파일을 사용하기 전에 관련이 없는 문자나 인쇄할 수 없는 문자가 없는지 확인하는 것이 좋습니다. 이렇게 하려면 Word에서 파일을 열고 리본 메뉴에서 단락 아이콘을 클릭하여 인쇄할 수 없는 문자를 표시합니다. 불필요한 인쇄할 수 없는 문자가 없어야 합니다. 예를 들어 파일 끝의 마지막 단락 표시 뒤에는 단락 표시가 없어야 합니다.

### <a name="run-the-windows-powershell-command"></a>Windows PowerShell 명령 실행

1. 메시지 Windows PowerShell 다음 명령을 입력하거나 복사하여 붙여넣고 Enter를 누를 수 있습니다.

   ```powershell
   Import-Csv C:\users\MyAlias\desktop\SiteCollections.csv | ForEach-Object {New-SPOSite -Owner $_.Owner -StorageQuota $_.StorageQuota -Url $_.Url -NoWait -ResourceQuota $_.ResourceQuota -Template $_.Template -TimeZoneID $_.TimeZoneID -Title $_.Name}
   ```

   여기서 *MyAlias는* 사용자 별칭과 동일합니다.

2. 메시지 메시지가 Windows PowerShell 때까지 기다렸다가 다시 표시될 때까지 기다렸다가 1~2분 정도 걸릴 수 있습니다.

3. 메시지 Windows PowerShell 다음 cmdlet을 입력하거나 복사하여 붙여넣고 Enter 키로 입력합니다.

   ```powershell
   Get-SPOSite -Detailed | Format-Table -AutoSize
   ```

4. 목록의 새 사이트 모음을 확인합니다. 예제 CSV 파일을 사용하면 **TeamSite01, Blog01,** **Project01** 및  **Community01** 사이트 모음이 표시됩니다.

그거에요. 만든 파일과 단일 .csv 명령을 사용하여 여러 사이트 모음을 Windows PowerShell 있습니다. 이제 사용자를 만들고 이러한 사이트에 할당할 준비가 완료되었습니다.

## <a name="step-2-add-users-and-groups"></a>2단계: 사용자 및 그룹 추가

이제 사용자를 만들어 사이트 모음 그룹에 추가할 수 있습니다. 그런 다음 .csv 파일을 사용하여 새 그룹 및 사용자를 대량 업로드합니다.

다음 절차에서는 예제 사이트 TeamSite01, Blog01, Project01 및 Community01을 계속 사용하고 있습니다.

### <a name="create-csv-and-ps1-files"></a>.csv 및 .ps1 파일 만들기

1. 메모장을 열고 다음 텍스트 블록을 붙여 넣습니다.

   ```powershell
   Site,Group,PermissionLevels
   https://tenant.sharepoint.com/sites/Community01,Contoso Project Leads,Full Control
   https://tenant.sharepoint.com/sites/Community01,Contoso Auditors,View Only
   https://tenant.sharepoint.com/sites/Community01,Contoso Designers,Design
   https://tenant.sharepoint.com/sites/TeamSite01,XT1000 Team Leads,Full Control
   https://tenant.sharepoint.com/sites/TeamSite01,XT1000 Advisors,Edit
   https://tenant.sharepoint.com/sites/Blog01,Contoso Blog Designers,Design
   https://tenant.sharepoint.com/sites/Blog01,Contoso Blog Editors,Edit
   https://tenant.sharepoint.com/sites/Project01,Project Alpha Approvers,Full Control
   ```

   여기서 *테넌트는* 테넌트 이름과 동일합니다.

2. 바탕 화면에 파일을 100으로 **GroupsAndPermissions.csv.**

3. 새 메모장 인스턴스를 열고 다음 텍스트 블록을 붙여 넣습니다.

   ```powershell
   Group,LoginName,Site
   Contoso Project Leads,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Community01
   Contoso Auditors,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Community01
   Contoso Designers,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Community01
   XT1000 Team Leads,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/TeamSite01
   XT1000 Advisors,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/TeamSite01
   Contoso Blog Designers,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Blog01
   Contoso Blog Editors,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Blog01
   Project Alpha Approvers,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Project01
   ```

   여기서 *테넌트는* 테넌트 이름과 같고 *사용자 이름은* 기존 사용자의 사용자 이름과 동일합니다.

4. 바탕 화면에 파일을 100으로 **Users.csv.**

5. 새 메모장 인스턴스를 열고 다음 텍스트 블록을 붙여 넣습니다.

   ```powershell
   Import-Csv C:\users\MyAlias\desktop\GroupsAndPermissions.csv | ForEach-Object {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
   Import-Csv C:\users\MyAlias\desktop\Users.csv | where {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
   ```

   여기서 MyAlias는 현재 로그온한 사용자의 사용자 이름과 동일합니다.

6. 바탕 화면에 파일을 100으로 **UsersAndGroups.ps1.** 이 스크립트는 간단한 Windows PowerShell 스크립트입니다.

이제 UsersAndGroup.ps1 스크립트를 실행하여 사용자와 그룹을 여러 사이트 모음에 추가할 수 있습니다.

### <a name="run-usersandgroupsps1-script"></a>UsersAndGroups.ps1 스크립트 실행

1. SharePoint Online 관리 셸로 돌아갑니다.

2. 메시지 Windows PowerShell 다음 줄을 입력하거나 복사하여 붙여넣고 Enter를 누르고 있습니다.

   ```powershell
   Set-ExecutionPolicy Bypass
   ```

3. 확인 프롬프트에서 **Y를 누르고 있습니다.**

4. 메시지 Windows PowerShell 다음을 입력하거나 복사하여 붙여넣고 Enter를 누르고 다음을 입력합니다.

   ```powershell
   c:\users\MyAlias\desktop\UsersAndGroups.ps1
   ```

   여기서 *MyAlias는* 사용자 이름과 동일합니다.

5. 프롬프트가 반환될 때까지 기다렸다가 계속 진행합니다. 먼저 작성된 그룹이 표시되고, 사용자를 추가하면 그룹 목록이 반복적으로 표시됩니다.

## <a name="see-also"></a>참고 항목

[커넥트 PowerShell을 SharePoint 수 있습니다.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

[PowerShell을 SharePoint 온라인 사이트 그룹 관리](manage-sharepoint-site-groups-with-powershell.md)

[PowerShell로 Microsoft 365 관리](manage-microsoft-365-with-microsoft-365-powershell.md)

[Microsoft 365 용 PowerShell 시작](getting-started-with-microsoft-365-powershell.md)
