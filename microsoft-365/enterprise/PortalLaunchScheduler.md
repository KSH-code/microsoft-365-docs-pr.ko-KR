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
ms.openlocfilehash: 929492742fd140654bd13be8165093ee10647c6d
ms.sourcegitcommit: da34ac08c7d029c2c42d4428d0bb03fd57c448be
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2020
ms.locfileid: "48999594"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a>포털 시작 스케줄러를 사용 하 여 포털 시작

새 포털에 대 한 물결을 설정 하는 테 넌 트 관리자의 기능을 먼저 확인 하 여 포털 시작 스케줄러를 사용 하 여 포털을 시작할 수 있습니다. 그런 다음 관리자는 활성 물결에 사용자가 있는지 여부에 따라 요청 리디렉션을 확인할 수 있습니다.

성공적인 포털을 시작 하는 방법에 대 한 자세한 내용은 [정상 포털 만들기, 시작 및 유지 관리](https://go.microsoft.com/fwlink/?linkid=2105838)에서 자세히 설명 하는 기본 원칙, 모범 사례 및 권장 사항을 따르세요. 

## <a name="app-setup"></a>앱 설치
1. `Microsoft.Online.SharePoint.PowerShell`제어판을 통해 컴퓨터에서 기존 프로그램이 있으면 제거 합니다.
2. PowerShell `Install-Module -Name Microsoft.Online.SharePoint.PowerShell` 통과

## <a name="connect-to-sharepoint-online"></a>SharePoint Online에 연결
1. Windows에서 [SharePoint Online 관리 셸을](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) 엽니다.
2. 관리자 권한으로 테 넌 트에 연결 합니다.
   - `Connect-SPOService -Url "https://*-admin.sharepoint.com" -Credential "username”`
3.  메시지가 표시 되 면 암호를 입력 합니다.

## <a name="command-to-get-an-existing-setup"></a>기존 설치 프로그램을 가져오기 위한 명령

기존 포털 시작 구성을 보려면 다음을 수행 합니다.

1. 통과 `Get-SPOPortalLaunchWaves  -LaunchSiteUrl  https://*.sharepoint.com/sites/newsite` 합니다.
2. `-DisplayFormat Raw`웨이브 컬렉션을 raw 입력 형식으로 서식이 지정 된 경우 추가 매개 변수를 전달 합니다.

## <a name="commands-for-bi-directional-redirection"></a>양방향 리디렉션 명령

이전 사이트 사용자를 미리 구성 된 방식으로 새 사이트로 마이그레이션하려면 다음을 수행 합니다.

1. 포털 시작 물결을 만듭니다.
   - 이 작업은 초기 릴리스 테스트 단계 에서만 적용 됩니다.
   - 변경의 영향을 즉시 테스트 하려면 첫 번째 물결이 `LaunchDateUtc` 현재 날짜로 설정 되어 있는지 확인 합니다. 이 플래그를 지정 하지 않으면 오류 메시지가 표시 됩니다. 이 오류는 프로덕션에서 시작을 최소 7 일 이상으로 예약 해야 하기 때문에 발생 합니다.

  `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/newsite" -RedirectionType Bidirectional -RedirectUrl "https://*.sharepoint.com/sites/oldsite" -ExpectedNumberOfUsers LessThan10kUsers -WaveOverrideUsers "*@microsoft.com" -Waves ' [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. 유효성 검사를 완료 합니다.
  - 리디렉션이 서비스 전체에서 구성을 완료 하는 데 최대 5 분이 걸릴 수 있으므로 계속 하기 전에 잠시 기다려 주십시오.
  - 로 지정 된 사용자에 게 로그인 하는 경우 `WaveOverrideUsers` 아무 것도 변경 되지 않습니다. 탐색 한 사이트를 그대로 두어야 합니다.
  - 보기 관리자에 게 속하는 사용자와 로그인 *합니다.*
    - 이전 사이트로 이동 하 여 새 사이트로 리디렉션됩니다.
    - 새 사이트로 이동 하 여 새 사이트를 계속 사용할 수 있습니다.
    - *VIEWER SG2* 에서 사용자에 게 로그온 하 여 이전 사이트로 이동한 후 이전 사이트를 유지 합니다.
    - 새 사이트로 이동 하 여 이전 사이트로 리디렉션됩니다.

3. 포털 시작을 일시 중지 합니다.
  - 시작 물결을 일시 중지 해야 하는 경우 "x" 일 수 동안 일시 중지할 수 있습니다. 플래그를 `Status` 일시 중지로 설정 하면 예정 된 모든 웨이브 progressions를 방지할 수 있습니다. 
  - `Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.
  - 모든 사용자가 이전 사이트로 리디렉션되는 것을 확인 합니다.

4. 포털 시작 진행을 다시 시작 합니다. 
  - `Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.
  - 리디렉션이 이제 복원 되었는지 확인 합니다.

5. 포털을 삭제 하 여 설치 프로그램을 시작 합니다.
  - `Remove-SPOPortalLaunchWaves -LaunchSiteUrl https://*.sharepoint.com/sites/NewSite`.
  - 모든 사용자에 대해 리디렉션이 발생 하지 않음을 확인 합니다.

## <a name="commands-for-redirection-to-temporary-page"></a>임시 페이지로의 리디렉션 명령

이전 사이트가 없고, 새 포털 페이지에서 웨이브에서 연결 되지 않은 사용자를 생략 하려면 다음 단계를 수행 합니다.

사이트에서 임시 페이지를 만들려면 다음을 수행 합니다.

1. 포털 시작 웨이브를 만듭니다.
   - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/NewSite" -RedirectionType ToTemporaryPage -RedirectUrl "https://*.sharepoint.com/sites/OldSite" -ExpectedNumberOfUsers From10kTo30kUsers -WaveOverrideUsers *@microsoft.com -Waves [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. 유효성 검사를 완료 합니다.

  - 5 분 정도 기다린 후에 작업을 완료 하는 데 최대 5 분까지 걸릴 수 있습니다.
  - *뷰어* \ 관리자에 게 속하는 사용자에 게 로그 하 여 다음을 수행 합니다.
     - 새 사이트로 이동 하 여 새 사이트를 계속 사용할 수 있습니다.
     - Temp 페이지로 이동 하 여 임시 페이지를 유지 해야 합니다.
  - *뷰어 SG2* 에 속하는 사용자에 게 로그 하 고 다음을 수행 합니다.
     - 새 사이트로 이동 하 여 temp 페이지로 리디렉션됩니다.
     - Temp 페이지로 이동 하 여 임시 페이지를 유지 해야 합니다.

3. 포털을 삭제 하 여 설치 프로그램을 시작 합니다.
  - `Remove-SPOPortalLaunchWaves - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.
  - 모든 사용자에 대해 리디렉션이 발생 하지 않음을 확인 합니다.

## <a name="learn-more"></a>자세히 알아보기
[SharePoint Online에서 포털 시작 롤아웃 계획 계획](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out)