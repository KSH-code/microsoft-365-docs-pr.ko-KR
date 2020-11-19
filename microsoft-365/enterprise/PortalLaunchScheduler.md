---
title: 포털 시작 스케줄러를 사용 하 여 포털 시작
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
description: 이 문서에서는 포털 시작 스케줄러를 사용 하 여 포털을 시작 하는 방법에 대해 설명 합니다.
ms.openlocfilehash: e5e5850fa7e74f3e3b342e9bb28d17f65b491664
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/19/2020
ms.locfileid: "49356670"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a>포털 시작 스케줄러를 사용 하 여 포털 시작

포털은 사이트에서 콘텐츠를 사용하는 다수의 사이트 방문자를 보유하는 인트라넷 상의 SharePoint 사이트입니다. 물결에서 포털을 시작 하는 것은 사용자에 게 새 SharePoint Online 포털에 쉽게 액세스할 수 있도록 하는 데 있어 중요 한 요소입니다. 

물결에서 시작 하는 것은 [SharePoint Online에서 포털 시작 롤아웃 계획 계획](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide)에 설명 된 것 처럼 포털을 롤아웃 하는 핵심 방법입니다. 포털 시작 스케줄러는 새 포털의 리디렉션을 관리 하 여 웨이브/단계적 롤아웃 방식에 따라 진행 하는 데 도움을 주기 위한 것입니다. 각 물결 중에는 각 배포 전파가 진행 되는 동안 사용자 의견을 수집 하 고 성능을 모니터링할 수 있습니다. 이렇게 하면 다음 웨이브를 계속 진행 하기 전에 문제를 일시 중지 및 해결 하 고 궁극적으로 사용자에 게 긍정적인 환경을 유지 하는 옵션이 제공 됩니다. 

리디렉션에는 다음과 같은 두 가지 유형이 있습니다. 
- 양방향 작업: 새로운 최신 SharePoint Online 포털을 시작 하 여 기존 SharePoint 클래식 또는 최신 포털을 교체 합니다. 
- 임시 페이지 리디렉션: 기존 SharePoint 포털을 사용 하지 않고 새로운 최신 SharePoint Online 포털 시작

포털 시작 스케줄러는 최신 SharePoint Online 포털 (예: 커뮤니케이션 사이트)을 실행 하는 경우에만 사용할 수 있습니다. 시작을 7 일 이상 미리 예약 해야 합니다. 필요한 물결 수는 예상 사용자 수에 따라 결정 됩니다. 포털 시작을 예약 하기 전에 포털의 홈 페이지가 정상 인지 확인 하기 위해 [SharePoint 용 페이지 진단을](https://aka.ms/perftool) 실행 해야 합니다. 포털 시작이 끝나면 사이트에 대 한 사용 권한이 있는 모든 사용자가 새 사이트에 액세스할 수 있습니다. 

성공적인 포털을 시작 하는 방법에 대 한 자세한 내용은 [정상 포털을 만들고, 시작 하 고, 유지 관리](https://docs.microsoft.com/sharepoint/portal-health)하는 방법에 대해 설명 하는 기본 원칙, 모범 사례 및 권장 사항을 따르세요. 

> [!NOTE]
> 이 기능은 Office 365 독일, 21Vianet에서 운영 하는 Office 365 (중국) 또는 Microsoft 365 US 정부 요금제에는 사용할 수 없습니다.

## <a name="app-setup-and-connecting-to-sharepoint-online"></a>앱 설치 및 SharePoint Online에 연결
1. [최신 SharePoint Online 관리 셸 다운로드](https://go.microsoft.com/fwlink/p/?LinkId=255251)

    > [!NOTE]
    > 이전 버전의 SharePoint Online 관리 셸을 설치한 경우 프로그램 추가/제거로 이동하여 "SharePoint Online 관리 셸"을 제거합니다.<br>다운로드 센터 페이지에서 언어를 선택하고 다운로드 단추를 클릭합니다. x64 및 x86 .msi 파일 다운로드 중에서 선택하라는 메시지가 표시됩니다. 64 비트 버전의 Windows를 실행하는 경우 x64 파일을, 32 비트 버전을 실행하는 경우 x86 파일을 다운로드합니다. 버전을 모르는 경우에는 [어떠한 Windows 운영 체제 버전을 실행 중인가요?](https://support.microsoft.com/help/13443/windows-which-operating-system)를 참조하세요. 파일을 다운로드한 후 파일을 실행하고 설정 마법사의 단계를 따릅니다.

2. Microsoft 365에서 [전역 관리자 또는 SharePoint 관리자](/sharepoint/sharepoint-admin-role)로 SharePoint에 연결합니다. 자세한 방법은 [SharePoint Online 관리 셸 시작](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)을 참조하세요.


## <a name="view-any-existing-portal-launch-setups"></a>기존 포털 시작 프로그램 보기

기존 포털 시작 구성이 있는지 확인 하려면 다음을 수행 합니다.

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

## <a name="schedule-a-portal-launch-on-the-site"></a>사이트에서 포털 시작 예약

필요한 물결 수는 예상 되는 시작 크기에 따라 달라 집니다. 
- 10k 미만의 사용자: 웨이브 1 개
- 10k ~ 30k 사용자: 3 개의 물결 
- 30k + 10만 명의 사용자: 5 물결
- 10만 명 이상: 5 개의 물결 및 Microsoft 계정 팀에 문의

### <a name="steps-for-bidirectional-redirection"></a>양방향 리디렉션 단계

양방향 리디렉션에는 기존 SharePoint 클래식 또는 최신 포털을 대체 하기 위해 최신 SharePoint Online 포털을 새로 시작 하는 작업이 포함 됩니다. 활성 물결의 사용자가 이전 사이트 또는 새 사이트로 이동 하는지 여부에 관계 없이 새 사이트로 리디렉션됩니다. 시작 되지 않은 웨이브의 사용자가 새 사이트에 액세스 하려고 하면 해당 물결이 시작 될 때까지 이전 사이트로 다시 리디렉션됩니다. 

이전 및 새 사이트를 리디렉션하지 않고 액세스 해야 하는 관리자 또는 소유자가 있는 경우에는 매개 변수를 사용 하 여 나열 되는지 확인 합니다 `WaveOverrideUsers` . 이전 사이트의 기본 홈 페이지와 새 사이트의 기본 홈 페이지 간 리디렉션을 지원 합니다.

기존 SharePoint 사이트의 사용자를 미리 구성 된 방식으로 새 SharePoint 사이트로 마이그레이션하려면 다음을 수행 합니다.

1. 다음 명령을 실행 하 여 포털 시작 물결을 지정 합니다.
   
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

2. 유효성 검사를 완료 합니다. 리디렉션이 서비스 전체에서 구성을 완료 하는 데 5-10 분 정도 걸릴 수 있습니다. 

### <a name="steps-for-redirection-to-temporary-page"></a>임시 페이지로 리디렉션하는 단계

기존 SharePoint 포털이 없는 경우 임시 페이지 리디렉션을 사용 해야 합니다. 사용자는 미리 구성 된 새로운 SharePoint Online 포털을 미리 안내 합니다. 사용자가 아직 시작 되지 않은 웨이브에 있는 경우에는 임시 페이지 (모든 URL)로 리디렉션됩니다. 

1. 다음 명령을 실행 하 여 포털 시작 물결을 지정 합니다.
   
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

2. 유효성 검사를 완료 합니다. 리디렉션이 서비스 전체에서 구성을 완료 하는 데 5-10 분 정도 걸릴 수 있습니다. 
   - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/newsite" -RedirectionType Bidirectional -RedirectUrl "https://*.sharepoint.com/sites/oldsite" -ExpectedNumberOfUsers LessThan10kUsers -WaveOverrideUsers "*@microsoft.com" -Waves ' [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

## <a name="pause-or-restart-a-portal-launch-on-the-site"></a>사이트에서 포털 시작 일시 중지 또는 다시 시작

1. 진행 중인 포털 시작을 일시 중지 하 고 예정 된 웨이브 progressions 발생 하는 것을 일시적으로 방지 하려면 다음 명령을 실행 합니다.

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```
2. 모든 사용자가 이전 사이트로 리디렉션되도록 확인 합니다. 

3. 일시 중지 된 포털 시작을 다시 시작 하려면 다음 명령을 실행 합니다.

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```
   
4. 리디렉션이 이제 복원 되었는지 확인 합니다. 

## <a name="delete-a-portal-launch-on-the-site"></a>사이트에서 포털 시작을 삭제 합니다.
1. 포털 시작 웨이브를 만듭니다.
  - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/NewSite" -RedirectionType ToTemporaryPage -RedirectUrl "https://*.sharepoint.com/sites/OldSite" -ExpectedNumberOfUsers From10kTo30kUsers -WaveOverrideUsers *@microsoft.com -Waves [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. 다음 명령을 실행 하 여 사이트에 대해 예약 되거나 진행 중인 포털 시작을 삭제 합니다.

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

3. 모든 사용자에 대해 리디렉션이 발생 하지 않음을 확인 합니다.

## <a name="learn-more"></a>자세히 알아보기
[SharePoint Online에서 포털 시작 롤아웃 계획 계획](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out)
