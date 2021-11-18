---
title: 포털 시작 스케줄러를 사용하여 포털 시작
ms.author: jhendr
author: jhendr
manager: pamgreen
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
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
ms.openlocfilehash: 99462adb9deb19ec54d9679451877b5398c9c820
ms.sourcegitcommit: c2b5ce3150ae998e18a51bad23277cedad1f06c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2021
ms.locfileid: "61064238"
---
# <a name="launch-your-portal-using-the-sharepoint-portal-launch-scheduler"></a>포털 시작 스케줄러를 SharePoint 포털 시작

포털은 트래픽이 많은 인트라넷의 SharePoint 커뮤니케이션 사이트로, 몇 주 동안 10,000~10만 명 이상의 뷰어가 있는 사이트입니다. 포털 시작 스케줄러를 사용하여 포털을 시작하여 사용자가 새 웹 사이트 포털에 액세스할 때 원활한 보기 SharePoint 합니다.
<br>
<br>
포털 시작 스케줄러는 뷰어를 단계적으로 일괄 처리하고 새 포털에 대한 URL 리디렉션을 관리하여 단계적 롤아웃 방식을 따르는 데 도움이 하도록 디자인됩니다. 각 웨이브가 시작되는 동안 사용자 피드백을 수집하고, 포털 성능을 모니터링하고, 실행을 일시 중지하여 다음 단계로 진행하기 전에 문제를 해결할 수 있습니다. 에서 포털 시작을 계획하는 방법에 대해 [SharePoint.](/microsoft-365/Enterprise/Planportallaunchroll-out)

**리디렉션에는 두 가지 유형이 있습니다.**

- **양방향:** 새로운 최신 SharePoint 포털을 시작하여 기존 SharePoint 또는 최신 포털을 대체합니다.
- **임시 페이지로** 리디렉션: 기존 SharePoint 포털이 없는 새 최신 SharePoint 시작

사이트 사용 권한은 시작의 일부로 물결과는 별도로 설정해야 합니다. 예를 들어 조직 전체 포털을 시작하려면 사용 권한을 "외부 사용자를 제외한 모든 사용자"로 권한을 설정한 다음 보안 그룹을 사용하여 사용자를 웨이브로 구분할 수 있습니다. 보안 그룹을 웨이브에 추가하면 해당 보안 그룹이 사이트에 액세스할 수 없습니다.

> [!NOTE]
>
> - 이 기능은 설정 사이트의  홈 페이지에 있는 SharePoint 액세스할 수 있습니다.
> - 이 기능은 사이트 페이지를 사용하는 최신 SharePoint 사이트에서만 사용할 수 있습니다. 이 기능은 포털에 사용할 기본 권장 유형이기 때문에 사용할 수 있습니다.
> - 포털 시작을 사용자 지정하고 예약하려면 사이트에 대한 사이트 소유자 권한이 있어야 합니다.
> - 시작은 최소 7일 전에 예약해야 합니다. 각 웨이브는 1~7일 동안 지속될 수 있습니다.
> - 필요한 물결 수는 예상되는 사용자 수에 따라 자동으로 결정됩니다.
> - 포털 시작을 시작하기 전에 사이트 홈 페이지가 [정상 SharePoint](https://aka.ms/perftool) 도구에 대한 페이지 진단을 실행해야 합니다.
> - 시작이 끝나면 사이트에 대한 사용 권한이 있는 모든 사용자가 새 사이트에 액세스할 수 있습니다.
> - 조직에서 [Viva Connections를](/SharePoint/viva-connections)사용하는 경우 사용자는 Microsoft Teams 앱 바에서 조직의 아이콘을 볼 수 있습니다. 그러나 아이콘을 선택하면 사용자가 웨이브가 시작될 때까지 포털에 액세스할 수 없습니다.
> - 독일, Office 365 21Vianet에서 운영하는 Office 365(중국) 또는 미국 정부 Microsoft 365 사용할 수 없습니다.

## <a name="understand-the-differences-between-portal-launch-scheduler-options"></a>포털 시작 스케줄러 옵션 간의 차이점을 이해합니다.

이전의 포털 시작은 PowerShell을 통해서만 SharePoint 수 있습니다. 이제 포털 시작을 예약하고 관리하는 데 도움이 되는 두 가지 옵션이 있습니다. 두 도구의 주요 차이점에 대해 자세히 알아보습니다.

**SharePoint PowerShell 버전:**

- PowerShell을 사용하려면 관리자 [자격 SharePoint 필요합니다.](/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell)
- 한 웨이브의 최소 요구 사항
- UTC(협정 세계시) 표준 시간대에 따라 시작 예약

**제품 내 버전:**

- 사이트 소유자 자격 증명 필요
- 두 가지 파도의 최소 요구 사항
- 지역 설정에 표시된 포털의 현지 표준 시간대를 기준으로 시작 예약

## <a name="get-started-using-the-portal-launch-scheduler"></a>포털 시작 스케줄러 사용 시작

1. 포털 시작 스케줄러 도구를 사용하려면 먼저 사이트 [소유자,](https://support.microsoft.com/office/share-a-site-958771a8-d041-4eb8-b51c-afea2eae3658) 사이트  구성원 또는 방문자로 사이트 권한을 통해 이 사이트에 액세스해야 하는 모든 사용자를 추가합니다.

2. 그런 다음 다음 두 가지 방법 중 하나를 통해 포털 시작 스케줄러에 액세스하여 포털 시작 일정을 예약합니다.

   **옵션 1:** 처음 몇 번(또는 홈페이지 버전 3.0까지) 홈 페이지에 대한 변경 내용을 편집하고 다시 게시하는 경우 포털 시작 스케줄러 도구를 사용할지 묻는 메시지가 표시됩니다. 예약을 **통해** 시작 예약을 선택하여 앞으로 이동할 수 있습니다. 또는 **다시 게시를 선택하여** 시작을 설정하지 않고 페이지 편집을 다시 게시합니다.

   ![홈 페이지를 다시 게시할 때 포털 시작 스케줄러를 사용할지 묻는 메시지의 이미지입니다.](../media/portal-launch-republish-2.png)

   **옵션 2:** 원하는 경우 SharePoint 커뮤니케이션 사이트 홈 페이지로 이동하여 설정 사이트  실행 예약을 선택하여 포털의 시작을 예약할 수 있습니다. 

   ![사이트 설정 예약이 강조 표시된 사이트 창의 이미지입니다.](../media/portal-launch-settings-2.png)

3. 다음으로 포털의 상태 점수를 확인하고 필요한 경우 포털에서 정상 [](https://aka.ms/perftool) 점수를 받을 때까지 SharePoint 페이지 진단 도구를 사용하여 포털을 **개선합니다.** 그런 후 **다음** 을 선택합니다.

   ![포털 시작 스케줄러 도구의 이미지입니다.](../media/portal-launch-panel-2.png)

   > [!NOTE]
   > 사이트 이름 및 설명은 포털 시작 스케줄러에서 편집할 수 없습니다. 대신  홈 페이지에서 사이트  설정 정보를 선택하여 변경할 수 있습니다.

4. **드롭다운에서** 예상 사용자 수를 선택합니다. 이 그림은 사이트에 액세스해야 하는 사용자 수를 나타내고 있습니다. 포털 시작 스케줄러는 예상되는 사용자에 따라 다음을 자동으로 결정하게 됩니다.

   - 사용자 수가 10k명 미만: 2회
   - 10k ~ 30k 사용자: 세 가지 파도
   - 30k+ ~ 100k 사용자: 5회
   - 사용자 수가 100k명 이상인 경우 포털 시작 섹션에 나열된 단계를 통해 5개의 단계로 Microsoft 지원에 문의하세요.

5. 그런 다음 필요한 **리디렉션 유형을** 파악합니다.

   **옵션 1: 기존** SharePoint 페이지로 사용자 보내기 ( 양방향) – 새 최신 SharePoint 포털을 시작하여 기존 SharePoint 포털을 대체할 때 이 옵션을 사용합니다. 활성 웨이브의 사용자는 이전 사이트로 이동하는지 새 사이트로 이동하는지 여부에 관계없이 새 사이트로 리디렉션됩니다. 새 사이트에 액세스하려고 하는 시작되지 않은 웨이브의 사용자는 해당 웨이브가 시작될 때까지 이전 사이트로 다시 리디렉션됩니다.

   > [!NOTE]
   > 양방향 옵션을 사용하는 경우 시작을 위한 사용자도 다른 사이트 포털에 대한 사이트 소유자 SharePoint 있어야 합니다.

   **옵션 2: 사용자를** 자동게이트된 임시 페이지(임시 페이지 리디렉션)로 보내기 - 기존 사이트 포털이 없는 경우 임시 페이지 리디렉션을 SharePoint 합니다. 사용자는 새로운 최신 SharePoint 포털로 이동되고 사용자가 아직 시작되지 않은 상태이면 임시 페이지로 리디렉션됩니다.

   **옵션 3: 외부** 페이지로 사용자 보내기 - 사용자의 웨이브가 시작될 때까지 임시 방문 페이지 환경으로 외부 URL을 제공합니다.

6. 대상을 파도로 끊습니다. 웨이브당 최대 20개 보안 그룹을 추가합니다. 각 웨이브가 시작될 때까지 웨이브 세부 정보를 편집할 수 있습니다. 각 웨이브는 최소 1일(24시간) 및 최대 7일 동안 지속될 수 있습니다. 따라서 SharePoint 환경과 사용자들이 많은 사이트 사용자를 익고 확장할 수 있습니다. UI를 통해 시작을 계획할 때 표준 시간대는 사이트의 국가별 설정을 기반으로 합니다.

   > [!NOTE]
   >
   > - 포털 시작 스케줄러는 자동으로 최소 2회의 웨이브로 기본 설정됩니다. 그러나 이 도구의 PowerShell 버전은 1파일을 허용합니다.
   > - Microsoft 365 이 버전의 포털 시작 스케줄러에서 지원되지 않는 그룹입니다.

7. 사이트를 바로 보아야 하는 사용자를 결정하고 사용자가 파도에서 제외된 사용자 필드에 정보를 **입력합니다.** 이러한 사용자는 웨이브에서 제외되기 때문에 시작 전, 실행 중 또는 이후에 리디렉션되지 않습니다.


    >[!NOTE]
    > 최대 50개의 고유한 사용자 또는 보안 그룹을 추가할 수 있습니다. 파도가 시작되기 전에 50명 이상의 사용자가 포털에 액세스해야 하는 경우 보안 그룹을 사용 합니다. 

8.  포털 시작 세부 정보를 확인하고 일정 을 **선택합니다.** 시작이 예약된 후 SharePoint 포털 홈 페이지에 대한 모든 변경 내용은 포털 시작이 다시 시작되기 전에 정상 진단 결과를 수신해야 합니다.


### <a name="launch-a-portal-with-over-100k-users"></a>100k 사용자가 있는 포털 시작

사용자가 10만 명 이상인 포털을 시작해야 하는 경우 아래 나열된 단계에 따라 지원 요청을 제출합니다. 요청된 모든 정보를 포함해야 합니다.

> [!NOTE]
>
> - 이 프로세스는 다음 요구 사항을 충족하는 경우에만 따라야 합니다.
> - 시작 페이지가 완료되었습니다.
> - [포털 상태 지침이](https://aka.ms/portalhealth) 따랐습니다.
> - 시작 날짜는 14일 이내입니다.

**다음 단계를 따릅니다.**

1. 관리자는 관리 센터에서 도움말 쿼리를 채우는 다음 링크를 클릭합니다. 

[100k SharePoint 포털 시작](https://admin.microsoft.com/AdminPortal/?searchSolutions=Launch%20SharePoint%20Portal%20with%20100k%20users)

2. 창 맨 아래에서 **지원 문의** 를 선택한 다음 **새 서비스 요청** 을 선택합니다. 

3. 설명 **아래에서**"100k SharePoint 포털 시작"을 입력합니다. 

4. 나머지 정보를 입력하고 **연락 받기** 를 선택합니다.

5. 티켓이 생성되면 다음과 같은 정보를 고객 지원팀으로 보내주세요.
   - 포털 URL
   - 필요한 사용자 수
   - 예상 시작 일정(웨이브 크기 자세히 설명)
   - 페이지 진단 도구를 사용하여 시작 페이지의 "HAR 파일 내보내기" 및 지원과 파일 공유

## <a name="make-changes-to-a-scheduled-portal-launch"></a>예약된 포털 시작 변경

시작 세부 정보는 웨이브가 시작된 날짜까지 각 웨이브에 대해 편집할 수 있습니다.

1. 포털 시작 세부 정보를 편집하려면 사이트 설정 시작 **예약을 선택합니다.** 
2. 그런 다음 편집 **을 선택합니다.**
3. 편집을 마치면 업데이트를 **선택합니다.**

## <a name="delete-a-scheduled-portal-launch"></a>예약된 포털 시작 삭제

일부 웨이브가 이미 시작된 경우에도 포털 시작 스케줄러 도구를 사용하여 예약된 시작을 취소하거나 삭제할 수 있습니다.

1. 포털의 시작을 취소하기 위해 사이트 설정 **실행** **예약으로 이동합니다.**

2. 그런 다음 **삭제를** 선택하고 아래 메시지가 표시되면 다시 **삭제를** 선택합니다.

   ![예약된 실행을 삭제할지 또는 유지할지 묻는 프롬프트 이미지입니다.](../media/portal-launch-delete-2.png)

## <a name="use-the-powershell-portal-launch-scheduler"></a>PowerShell 포털 시작 스케줄러 사용

SharePoint 포털 시작 스케줄러 도구는 원래 SharePoint [PowerShell을](/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell) 통해서만 사용할 수 있으며 이 방법을 선호하는 고객을 위해 PowerShell을 통해 계속 지원됩니다. 이 문서의 시작에 있는 동일한 메모는 두 버전의 포털 시작 스케줄러에 모두 적용됩니다.

> [!NOTE]
> PowerShell을 사용하려면 관리자 권한이 SharePoint 합니다.
> PowerShell에서 만든 시작에 대한 포털 시작 세부 정보가 표시되고 이 도구의 새 포털 시작 스케줄러 도구에서 관리할 SharePoint.

### <a name="app-setup-and-connecting-to-sharepoint-online"></a>앱 설치 및 SharePoint 온라인에 연결

1. [최신 SharePoint Online 관리 셸 다운로드](https://go.microsoft.com/fwlink/p/?LinkId=255251)

    > [!NOTE]
    > 이전 버전의 SharePoint Online 관리 셸을 설치한 경우 프로그램 추가/제거로 이동하여 "SharePoint Online 관리 셸"을 제거합니다.
    > 
    > 다운로드 센터 페이지에서 언어를 선택하고 다운로드 단추를 클릭합니다. x64 및 x86 .msi 파일 다운로드 중에서 선택하라는 메시지가 표시됩니다. 64 비트 버전의 Windows를 실행하는 경우 x64 파일을, 32 비트 버전을 실행하는 경우 x86 파일을 다운로드합니다. 버전을 모르는 경우에는 [어떠한 Windows 운영 체제 버전을 실행 중인가요?](https://support.microsoft.com/help/13443/windows-which-operating-system)를 참조하세요. 파일을 다운로드한 후 파일을 실행하고 설정 마법사의 단계를 따릅니다.

2. Microsoft 365에서 [전역 관리자 또는 SharePoint 관리자](/sharepoint/sharepoint-admin-role)로 SharePoint에 연결합니다. 방법을 알아보려면 [SharePoint Online Management Shell 시작하기](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)를 참조하세요.

### <a name="view-any-existing-portal-launch-setups"></a>기존 포털 시작 설정 보기

기존 포털 시작 구성이 있는지 확인하려면

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

### <a name="schedule-a-portal-launch-on-the-site"></a>사이트에서 포털 시작 예약

필요한 파도 수는 예상되는 시작 크기에 따라 다를 수 있습니다.

- 10k 사용자 미만: 한 웨이브
- 10k ~ 30k 사용자: 세 가지 파도 
- 30k+ ~ 100k 사용자: 5회
- 100k 사용자 이상: 5개의 물결표로 Microsoft 계정 팀에 문의

#### <a name="steps-for-bidirectional-redirection"></a>양방향 리디렉션 단계

양방향 리디렉션에는 기존 SharePoint 또는 최신 포털을 대체하는 새로운 최신 SharePoint 포털을 시작해야 합니다. 활성 웨이브의 사용자는 이전 사이트로 이동하는지 새 사이트로 이동하는지 여부에 관계없이 새 사이트로 리디렉션됩니다. 새 사이트에 액세스하려고 하는 시작되지 않은 웨이브의 사용자는 해당 웨이브가 시작될 때까지 이전 사이트로 다시 리디렉션됩니다.

이전 사이트의 기본 홈 페이지와 새 사이트의 기본 홈 페이지 간 리디렉션만 지원됩니다. 리디렉션되지 않고 이전 및 새 사이트에 액세스해야 하는 관리자 또는 소유자가 있는 경우 매개 변수를 사용하여 나열해야 `WaveOverrideUsers` 합니다.

기존 SharePoint 사이트에서 새 SharePoint 사이트로 사용자를 마이그레이션하려면 다음을 단계적으로 진행합니다.

1. 다음 명령을 실행하여 포털 시작 웨이브를 지정합니다.

   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType Bidirectional -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
   ```

   예:

   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType Bidirectional -RedirectUrl "https://contoso.sharepoint.com/teams/oldsite" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
   [{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
   {Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"},
   {Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. 유효성 검사를 완료합니다. 리디렉션이 서비스 전체에서 구성을 완료하는 데 5-10분 정도 걸릴 수 있습니다.

#### <a name="steps-for-redirection-to-temporary-page"></a>임시 페이지로 리디렉션하는 단계

기존 사이트 포털이 없는 경우 임시 페이지 리디렉션을 SharePoint 합니다. 사용자는 새로운 최신 SharePoint 온라인 포털로 이동됩니다. 사용자가 시작되지 않은 웨이브에 있는 경우 임시 페이지(모든 URL)로 리디렉션됩니다.

1. 다음 명령을 실행하여 포털 시작 웨이브를 지정합니다.

   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType ToTemporaryPage -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
   ```

   예:

   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType ToTemporaryPage -RedirectUrl "https://portal.contoso.com/UnderConstruction.aspx" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
   [{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
   {Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"},
   {Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. 유효성 검사를 완료합니다. 리디렉션이 서비스 전체에서 구성을 완료하는 데 5-10분 정도 걸릴 수 있습니다.

### <a name="pause-or-restart-a-portal-launch-on-the-site"></a>사이트에서 포털 시작 일시 중지 또는 다시 시작

1. 진행 중 포털 시작을 일시 중지하고 예정된 물결 진행이 발생하지 않도록 일시적으로 차단하기 위해 다음 명령을 실행합니다.

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```

2. 모든 사용자가 이전 사이트로 리디렉션되는지 검사합니다.

3. 일시 중지된 포털 시작을 다시 시작하려면 다음 명령을 실행합니다.

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```

4. 이제 리디렉션이 복원되어 있는지 유효성을 검사합니다.

### <a name="delete-a-portal-launch-on-the-site"></a>사이트에서 포털 시작 삭제

1. 다음 명령을 실행하여 사이트에 대해 예약되거나 진행 중인 포털 시작을 삭제합니다.

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

2. 모든 사용자에 대해 리디렉션이 진행되지 않은지 유효성을 검사합니다.

## <a name="learn-more"></a>자세히 알아보기

[SharePoint Online에서 포털 시작 롤아웃 계획](./planportallaunchroll-out.md)

[커뮤니케이션 사이트 계획](https://support.microsoft.com/office/plan-your-sharepoint-communication-site-35d9adfe-d5cc-462f-a63a-bae7f2529182)
