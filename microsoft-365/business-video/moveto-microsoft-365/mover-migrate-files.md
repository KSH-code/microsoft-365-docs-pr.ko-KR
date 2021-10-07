---
title: '비즈니스용 앱으로 Google Microsoft 365 마이그레이션 '
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
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
description: Mover를 사용하여 비즈니스용 앱을 Microsoft 365 Google 파일을 마이그레이션하는 방법을 학습합니다.
ms.openlocfilehash: 4bec723d024468f76bdfcc60934eb42c445fe0f5
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60194816"
---
# <a name="migrate-google-files-to-microsoft-365-for-business"></a>비즈니스용 앱으로 Google Microsoft 365 마이그레이션 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4MhaD?autoplay=false]

비즈니스용 Microsoft 365 이동하면 비즈니스용 파일에서 파일을 마이그레이션할 Google 드라이브. Mover 앱을 사용하여 개인 및 공유 드라이브에서 파일을 이동할 수 있습니다. 자세한 내용은 [Mover 클라우드 마이그레이션을 참조하세요.](/sharepointmigration/mover-plan-migration)

> [!NOTE]
> Mover는 파일의 복사본을 만들어 비즈니스용 Microsoft 365 이동합니다. 원본 파일은 Google Drives에도 그대로 있습니다.

## <a name="before-you-start"></a>시작하기 전에

모든 사용자는 비즈니스용 앱에 Microsoft 365 로그인하고 비즈니스용 응용 비즈니스용 OneDrive. 이 작업을 위해 office.com [으로](https://office.com)이동하여 비즈니스 자격 증명을 Microsoft 365 로그인한 다음 OneDrive.

## <a name="try-it"></a>사용해 보세요!

### <a name="install-mover"></a>Mover 설치

1. 에서 Google Workspace 관리 콘솔에 [admin.google.com.](https://admin.google.com)

1. 앱   >  **Google Workspace Marketplace 앱** 도메인 설치 목록에 앱  >  **추가를 선택합니다.**

1. Mover를 검색하고 선택합니다.

1. 도메인 **설치 를 선택한** 다음 계속 **을 계속합니다.**

1. 사용 권한을 검토하고 사용 약관에 동의할 확인란을 선택한 다음 **허용,** **다음,** 완료를 **선택합니다.**

### <a name="create-connectors-and-run-the-migration"></a>커넥터 만들기 및 마이그레이션 실행

1. Google **Workspace Marketplace 앱으로 돌아오기**
1. 브라우저를 새로 고치고 **Mover 앱을** 선택합니다.
1. 아래로 스크롤하여 유니버설 탐색 링크를 선택하세요.
1. 새 **커넥터 승인을 선택하고** G **Suite(관리자)를** 찾은 다음 **승인을 선택합니다.**
1. 원하는 **경우 표시 이름** 을 변경한 다음 **승인을 선택합니다.**
1. Google 관리자 계정을 선택하고 사용 권한을 검토한 다음 허용 을 **선택합니다.**

    Mover는 검색된 팀 드라이브 및 사용자 드라이브의 수를 표시합니다. 

1. 대상 **선택에서** **새** 커넥터 승인을 선택하고 Office 365 **를** 찾고 **승인을 선택합니다.**
1. 앱의 Mover 앱에 사용 권한을 부여하려면 Azure Active Directory 로 [aka.ms/Office365MoverAuth.](https://aka.ms/Office365MoverAuth)
1. Mover **Office 365** 사용 **권한**, **회사에** 대한 관리자 동의 부여를 선택합니다.
1. 계정을 선택하고 사용 권한을 검토하고 수락을 **선택합니다.**
1. 속성을 **선택하고** 사용자 할당이 **필요한지** 확인을 합니다.
1. Mover 앱으로 돌아가서 표시 이름 을 변경하고 원하는 경우 **승인을** 선택한 다음 Microsoft 관리자 계정을 선택합니다.

    Mover는 검색된 SharePoint 온라인(또는 SPO) 사이트 및 사용자 수에 대해 알릴 수 있습니다.
1. 마이그레이션 **설정 계속,** **사용자** 추가를 선택한 다음 자동으로 사용자 검색 **및 추가를 선택합니다.**

    Mover 앱은 Google의 원본 경로에서 드라이브를 앱의 대상 경로로 매핑하려고 Microsoft 365. 

    드라이브가 자동으로 매핑되지 않는 경우 대상 경로를 CSV 파일에 추가합니다. 나중에 공유 드라이브를 문서 라이브러리로 마이그레이션하는 SharePoint 합니다. 

1. 이 경우 마이그레이션된 파일이라는 SharePoint 사이트를 추가하고 문서 페이지의 URL을 기록했습니다. 
1. 그런 다음 원본 경로, 대상 경로 및 태그 형식을 사용하여 CSV 파일을 만들 수 있습니다. 

    자세한 내용은 을 [aka.ms/movercsv.](/sharepointmigration/mover-create-migration-csv)

    대상 경로 URL을 추가할 때 공유 문서 다음에 있는 모든 것을 제거합니다. 예를 들어 이 전체 URL은 작동하지 않습니다. `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`

    다음으로 변경합니다. `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`

1. CSV 파일이 준비되면 마이그레이션 **작업,** 마이그레이션에 **추가,** **업로드할 파일 선택을 선택합니다.**
1. CSV 파일로 이동하여 선택한 다음 열기 **를 선택합니다.**
1. 마이그레이션할 파일을 가진 사용자 드라이브를 선택한 다음 사용자 마이그레이션 **시작 을 선택합니다.**
1. 마이그레이션 정보를 검토하고 마이그레이션을 시작할 때를 선택하고 사용 약관에 동의한 다음 계속을 **선택합니다.**

Mover 앱은 마이그레이션 프로세스가 완료되면 알려주게 됩니다.