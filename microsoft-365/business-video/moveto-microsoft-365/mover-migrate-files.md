---
title: '비즈니스용 Microsoft 365로 Google 파일 마이그레이션 '
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Mover를 사용하여 Google 파일을 비즈니스용 Microsoft 365로 마이그레이션하는 방법을 학습합니다.
ms.openlocfilehash: 72ea81ad86a20e01b4650915fef96a713b207c3b
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166162"
---
# <a name="migrate-google-files-to-microsoft-365-for-business"></a>비즈니스용 Microsoft 365로 Google 파일 마이그레이션 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4MhaD?autoplay=false]

비즈니스용 Microsoft 365로 이동하면 Google Drive에서 파일을 마이그레이션할 수 있습니다. Mover 앱을 사용하여 개인 및 공유 드라이브에서 파일을 이동할 수 있습니다. 자세한 내용은 [Mover 클라우드 마이그레이션을 참조하세요.](https://docs.microsoft.com/sharepointmigration/mover-plan-migration)

> [!NOTE]
> Mover는 파일의 복사본을 만들어 비즈니스용 Microsoft 365로 이동합니다. 원본 파일은 Google Drives에도 그대로 있습니다.

## <a name="before-you-start"></a>시작하기 전에

모든 사용자는 비즈니스용 Microsoft 365에 로그인하고 비즈니스용 OneDrive를 설정해야 합니다. 이렇게 해야 office.com [](https://office.com)Microsoft 365 비즈니스 에디티브 자격 증명으로 로그인한 다음 OneDrive를 선택해야 합니다.

## <a name="try-it"></a>사용해 보세요!

### <a name="install-mover"></a>Mover 설치

1. 에서 Google Workspace 관리 콘솔에 [admin.google.com.](https://admin.google.com)

1. Choose **Apps**  >  **Google Workspace Marketplace apps** Add app to Domain Install  >  **list.**

1. Mover를 검색하고 선택합니다.

1. 도메인 **설치를 선택한** 다음 **계속합니다.**

1. 사용 권한을 검토하고 사용 약관에 동의할 확인란을 선택한 다음 **허용,** **다음,** 완료를 **선택합니다.**

### <a name="create-connectors-and-run-the-migration"></a>커넥터 만들기 및 마이그레이션 실행

1. Google **Workspace Marketplace 앱으로 돌아가기**
1. 브라우저를 새로 고치고 **Mover 앱을** 선택합니다.
1. 아래로 스크롤하여 유니버설 탐색 링크를 선택하세요.
1. 새 **커넥터 승인을 선택하고** G **Suite(관리자)를 찾은** 다음 **승인을 선택합니다.**
1. 표시 이름을 **변경하고** 원하는 경우 **승인을 선택합니다.**
1. Google 관리자 계정을 선택하고 사용 권한을 검토한 다음 허용을 **선택합니다.**

    Mover는 검색된 팀 드라이브 및 사용자 드라이브의 수를 표시합니다. 

1. 대상 **선택에서** **새** 커넥터 승인을 선택하고 **Office 365를** 찾은 다음 **승인을 선택합니다.**
1. Azure Active Directory의 Mover 앱에 대한 사용 권한을 부여하려면 다음 [aka.ms/Office365MoverAuth.](https://aka.ms/Office365MoverAuth)
1. Select **Office 365 Mover,** **Permissions,** **Grant admin consent for your company.**
1. 계정을 선택하고 사용 권한을 검토한 다음 수락을 **선택합니다.**
1. 속성을 **선택하고** **사용자** 할당이 필요한지 확인하려면 설정해야 합니다.
1. Mover 앱으로 돌아가 표시 이름을 **변경합니다.** 원하는 경우 승인을 선택한 다음 Microsoft 관리자 계정을 선택합니다.

    Mover는 검색된 SharePoint Online(또는 SPO) 사이트 및 사용자 수에 대해 알릴 것입니다.
1. 마이그레이션 **설치 계속,** 사용자 **추가를** 선택한 다음 자동으로 **사용자 검색 및 추가를 선택합니다.**

    Mover 앱은 Google의 원본 경로에서 Microsoft 365의 대상 경로로 드라이브를 매핑하려고 합니다. 

    드라이브가 자동으로 매핑되지 않는 경우 대상 경로를 CSV 파일에 추가합니다. 이 경로는 나중에 공유 드라이브를 SharePoint 문서 라이브러리로 마이그레이션하는 데 사용할 것입니다. 

1. 이 경우 마이그레이션된 파일이라는 SharePoint 사이트를 추가하고 문서 페이지의 URL을 기록해 두십시오. 
1. 그런 다음 원본 경로, 대상 경로 및 태그 형식을 사용하여 CSV 파일을 만들 수 있습니다. 

    자세한 내용은 [다음](https://docs.microsoft.com/sharepointmigration/mover-create-migration-csv)aka.ms/movercsv.

    대상 경로 URL을 추가할 때 공유 문서 다음에 있는 모든 것을 제거합니다. 예를 들어 이 전체 URL은 작동하지 않습니다. `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`

    다음으로 변경합니다. `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`

1. CSV 파일이 준비되면 마이그레이션 **작업,** 마이그레이션에 **추가,** 업로드할 **파일 선택을 선택합니다.**
1. CSV 파일로 이동하여 선택한 다음 **열기 를 선택합니다.**
1. 파일을 마이그레이션할 사용자 드라이브를 선택한 다음 사용자 마이그레이션 **시작을 선택합니다.**
1. 마이그레이션 정보를 검토하고 마이그레이션을 시작할 때를 선택하고 사용 약관에 동의한 다음 **계속을** **선택합니다.**

Mover 앱은 마이그레이션 프로세스가 완료된 경우 알려 드리며,
