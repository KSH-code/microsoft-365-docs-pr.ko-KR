---
title: 포털 시작 스케줄러를 사용하여 포털 시작
ms.author: jhendr
author: jhendr
manager: pamgreen
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
description: 이 문서에서는 포털 시작 스케줄러를 사용하여 포털을 시작 하는 방법을 설명 합니다.
ms.openlocfilehash: 66912f5730c580bd75282a64124fefcdf262d738
ms.sourcegitcommit: cc354fd54400be0ff0401f60bbe68ed975b69cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2021
ms.locfileid: "49864879"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a>포털 시작 스케줄러를 사용하여 포털 시작

포털은 사이트에서 콘텐츠를 사용하는 다수의 사이트 방문자를 보유하는 인트라넷 상의 SharePoint 사이트입니다. 사용자가 새 SharePoint Online 포털에 액세스하는 원활하고 원활하게 작업할 수 있도록 하는 중요한 부분으로 포털을 시작해야 합니다. 

SharePoint Online에서 포털 시작 롤아웃 계획에 자세히 설명된 포털을 롤아웃하는 핵심적인 방법 중 한 [가지가 있습니다.](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide) 포털 시작 스케줄러는 새 포털에 대한 리디렉션을 관리하여 단계적/단계적 롤아웃 접근 방식을 따르는 데 도움이 하도록 디자인됩니다. 각 단계가 진행되는 동안 사용자 피드백을 수집하고 각 배포 단계 동안 성능을 모니터링할 수 있습니다. 이 경우 포털을 느리게 도입하여 다음 단계로 진행하기 전에 문제를 일시 중지하고 해결할 수 있으며 궁극적으로 사용자에게 긍정적인 환경을 보장할 수 있는 이점이 있습니다. 

리디렉션에는 두 가지 유형이 있습니다. 
- 양방향: 기존 SharePoint 클래식 또는 최신 포털을 대체하는 새로운 최신 SharePoint Online 포털 시작 
- 임시 페이지 리디렉션: 기존 SharePoint 포털이 없는 새로운 최신 SharePoint Online 포털 시작

포털 시작 스케줄러는 최신 SharePoint Online 포털(예: 커뮤니케이션 사이트)을 시작해야만 사용할 수 있습니다. 시작은 최소 7일 전에 예약해야 합니다. 필요한 파도 수는 예상되는 사용자 수에 따라 결정됩니다. 포털 시작을 설정하기 전에 [SharePoint용](https://aka.ms/perftool) 페이지 진단 도구를 실행하여 포털의 홈 페이지가 정상 상태인지 확인해야 합니다. 포털을 시작하면 사이트에 대한 사용 권한이 있는 모든 사용자가 새 사이트에 액세스할 수 있습니다. 

성공적인 포털을 시작하는 데 대한 자세한 내용은 건전한 포털 만들기, 시작 및 유지 관리에 자세히 설명된 기본 원칙, 사례 및 권장 사항을 [따르하세요.](https://docs.microsoft.com/sharepoint/portal-health) 

> [!NOTE]
> 이 기능은 Office 365 Germany, 21Vianet에서 운영하는 Office 365(중국) 또는 Microsoft 365 Government 계획에서는 사용할 수 없습니다.

## <a name="app-setup-and-connecting-to-sharepoint-online"></a>앱 설치 및 SharePoint Online에 연결
1. [최신 SharePoint Online 관리 셸 다운로드](https://go.microsoft.com/fwlink/p/?LinkId=255251)

    > [!NOTE]
    > 이전 버전의 SharePoint Online 관리 셸을 설치한 경우 프로그램 추가/제거로 이동하여 "SharePoint Online 관리 셸"을 제거합니다.<br>다운로드 센터 페이지에서 언어를 선택하고 다운로드 단추를 클릭합니다. x64 및 x86 .msi 파일 다운로드 중에서 선택하라는 메시지가 표시됩니다. 64 비트 버전의 Windows를 실행하는 경우 x64 파일을, 32 비트 버전을 실행하는 경우 x86 파일을 다운로드합니다. 버전을 모르는 경우에는 [어떠한 Windows 운영 체제 버전을 실행 중인가요?](https://support.microsoft.com/help/13443/windows-which-operating-system)를 참조하세요. 파일을 다운로드한 후 파일을 실행하고 설정 마법사의 단계를 따릅니다.

2. Microsoft 365에서 [전역 관리자 또는 SharePoint 관리자](/sharepoint/sharepoint-admin-role)로 SharePoint에 연결합니다. 자세한 방법은 [SharePoint Online 관리 셸 시작](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)을 참조하세요.


## <a name="view-any-existing-portal-launch-setups"></a>기존 포털 시작 설정 보기

기존 포털 시작 구성이 있는지 확인하려면

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

## <a name="schedule-a-portal-launch-on-the-site"></a>사이트에서 포털 시작 예약

필요한 파도 수는 예상되는 시작 크기에 따라 다를 수 있습니다. 
- 사용자 수가 10k 미만: 1회
- 10k에서 30k 사용자: 3파일 
- 30k+ ~ 100k 사용자: 5파일
- 사용자 수가 100k명 이상: 5회 진행하여 Microsoft 계정 팀에 문의

### <a name="steps-for-bidirectional-redirection"></a>양방향 리디렉션 단계

양방향 리디렉션에는 기존 SharePoint 클래식 또는 최신 포털을 대체하는 새로운 최신 SharePoint Online 포털을 시작해야 합니다. 활성 상태의 사용자는 이전 사이트 또는 새 사이트로 이동하는지 여부에 관계없이 새 사이트로 리디렉션됩니다. 새 사이트에 액세스하려고 하는 시작되지 않은 물결의 사용자는 파도가 시작될 때까지 이전 사이트로 다시 리디렉션됩니다. 

이전 사이트의 기본 홈 페이지와 새 사이트의 기본 홈 페이지 간 리디렉션만 지원됩니다. 리디렉션되지 않고 이전 및 새 사이트에 액세스해야 하는 관리자 또는 소유자가 있는 경우 매개 변수를 사용하여 나열해야 `WaveOverrideUsers` 합니다.

기존 SharePoint 사이트에서 새 SharePoint 사이트로 사용자를 단계적 방식으로 마이그레이션하려면

1. 다음 명령을 실행하여 포털 시작 파도를 지정합니다.
   
   ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType Bidirectional -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

예제:
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType Bidirectional -RedirectUrl "https://contoso.sharepoint.com/teams/oldsite" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. 유효성 검사를 완료합니다. 리디렉션이 서비스 전체에서 구성을 완료하는 데 5-10분 정도 걸릴 수 있습니다. 

### <a name="steps-for-redirection-to-temporary-page"></a>임시 페이지로 리디렉션하는 단계

기존 SharePoint 포털이 없는 경우 임시 페이지 리디렉션을 사용해야 합니다. 사용자는 단계적 방식으로 새로운 최신 SharePoint Online 포털로 이동됩니다. 사용자가 시작되지 않은 상태인 경우 해당 사용자는 임시 페이지(모든 URL)로 리디렉션됩니다. 

1. 다음 명령을 실행하여 포털 시작 파도를 지정합니다.
   
      ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType ToTemporaryPage -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

예제:
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType ToTemporaryPage -RedirectUrl "https://portal.contoso.com/UnderConstruction.aspx" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. 유효성 검사를 완료합니다. 리디렉션이 서비스 전체에서 구성을 완료하는 데 5-10분 정도 걸릴 수 있습니다. 

## <a name="pause-or-restart-a-portal-launch-on-the-site"></a>사이트에서 포털 시작 일시 중지 또는 다시 시작

1. 진행 중 포털 시작을 일시 중지하고 예정된 물결 진행이 일시적으로 발생하지 않도록 방지하기 위해 다음 명령을 실행합니다.

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```
2. 모든 사용자가 이전 사이트로 리디렉션되는지 검사합니다. 

3. 일시 중지된 포털 시작을 다시 시작하려면 다음 명령을 실행합니다.

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```
   
4. 이제 리디렉션이 복원되어 있는지 유효성을 검사합니다. 

## <a name="delete-a-portal-launch-on-the-site"></a>사이트에서 포털 시작 삭제

1. 다음 명령을 실행하여 사이트에 대해 예약되거나 진행 중인 포털 시작을 삭제합니다.

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

2. 모든 사용자에 대해 리디렉션이 진행되지 않은지 검사합니다.

## <a name="learn-more"></a>자세한 정보
[SharePoint Online에서 포털 시작 롤아웃 계획](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out)
