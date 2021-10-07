---
title: 비즈니스용 Microsoft 365 설정 계획
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_O365_Setup
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- MET150
- MOE150
ms.assetid: eb926624-018b-4486-bf11-5fba6ee4d645
description: 비즈니스용 앱으로 이동하기 위한 요구 사항 및 고려 Microsoft 365 대해 자세히 알아보습니다.
ms.openlocfilehash: 7e7d3a56d58c19e36372a4e3d8f32788bf19771d
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60193832"
---
# <a name="plan-your-setup-of-microsoft-365-for-business"></a>비즈니스용 Microsoft 365 설정 계획

이 문서는 비즈니스용 Microsoft 365 구독한 사람용입니다.
  
조직을 이전 Microsoft 365 충족해야 하는 요구 사항, 필요한 정보 및 결정해야 하는 사항이 있습니다.


  
## <a name="info-to-have-on-hand-before-you-run-the-setup-wizard"></a>설치 마법사를 실행하기 전에 준비해야 할 정보

설치 마법사를 실행하고 도메인을 Microsoft 365 준비되면 다음 정보를 준비해야 합니다.
  
- 사용자 목록에 추가할 사용자 Microsoft 365. 이미 도메인에 추가한 경우에도 Microsoft 365 정보를 업데이트하는 경우 여기에 해당 이름을 입력해야 합니다.

- 로그인할 수 있도록 직원에게 사용자 ID와 암호를 알리는 방법 정보를 사용하여 전화를 걸 것입니까? 또는 개인 전자 메일 주소로 보내시겠습니까? 전자 메일에 액세스할 수 없습니다. 따라서 사용할 수 없습니다.

- 조직의 도메인 이름(예: contoso.com)이 있으며 Microsoft  전자 메일을 사용하려면 도메인이 등록된 위치를 알아야 합니다. 로그인 정보가 있습니다.

## <a name="what-happens-when-you-run-the-microsoft-365-setup-wizard"></a>설치 마법사를 실행하면 Microsoft 365 발생

설치 마법사는 컴퓨터에 Microsoft 365 앱을 설치하고, 도메인을 추가 및 확인하고, 사용자를 추가하고, 라이선스를 할당하고, 도메인을 연결하는 방법을 안내합니다.

> [!NOTE]
> 마법사에서 [](../add-users/assign-admin-roles.md) 추가한 사용자에게 비즈니스용 Microsoft 365 관리자 역할을 할당해야 하는 경우 나중에 사용자 페이지에서 할당할 **수** 있습니다. 
  
설치 마법사를 완료하지 않은 경우 관리 센터 설치 에서 설치 작업을 원하는 [시간으로 완료할 수](https://go.microsoft.com/fwlink/p/?linkid=2024339)  >  **있습니다.** 여기에서 다른 전자 메일 서비스에서 전자 메일 및 연락처를 마이그레이션하고, 관리자 계정의 도메인을 변경하고, 청구 정보를 관리하고, 사용자를 추가 또는 제거하고, 암호를 재설정하고, 기타 비즈니스 기능을 할 수 있습니다. 설치 마법사와 설치 페이지 간의 차이점에 대한 자세한 내용은 Microsoft 365 설치 마법사와 설치 페이지 [간의 차이점을 참조하세요.](o365-setup-wizard-and-setup-page.md) 

문제가 발생하면 Microsoft에 문의하세요. [Microsoft에서 도와드리겠습니다.](../../business-video/get-help-support.md)
  
## <a name="when-not-to-use-the-setup-wizard-active-directory-synchronization-and-hybrid-environments"></a>설정 마법사를 사용하면 안 되는 경우: Active Directory 동기화 및 하이브리드 환경

데이터 또는 사용자를온-프레미스 환경에서 마이그레이션하거나 디렉터리 동기화를 포함하는 하이브리드 시스템을 설정하는 시나리오는 몇 가지가 있습니다. 두 범주 중 하나에 속하는 경우 다음 문서의 지침을 따르세요.
  
- 디렉터리 동기화를 On-프레미스 Active Directory와 설정하는 자세한 [내용은 set up directory synchronization for Microsoft 365](../../enterprise/set-up-directory-synchronization.md)을 참조하고 Microsoft 365 ID 및 id Microsoft 365 [이해를 Azure Active Directory.](../../enterprise/about-microsoft-365-identity.md)

- Exchange 하이브리드를 설정하려면 다음에서 하이브리드 Exchange를 설정(DNS 레코드 설정 포함)하는 여러 다른 방법을 모두 안내하는 전체 지침 집합을 찾을 수 있습니다. [Exchange Server 배포 도우미](/exchange/exchange-deployment-assistant)

- SharePoint 하이브리드, 특히 하이브리드 검색 및 사이트 기능을 설정하려면 [SharePoint의 하이브리드 검색](/SharePoint/hybrid/hybrid-search-in-sharepoint)을 참조하세요.

## <a name="move-to-microsoft-365-all-at-once-or-in-stages"></a>한 Microsoft 365 단계로 이동

- **조직을 한 Microsoft 365 이동하고 싶나요?** 그렇다면 도메인을 바로 Microsoft 365 계획을 세우는 것이 좋습니다. 먼저 설치 Microsoft 365 실행합니다. 도메인을 설정하라는 메시지가 표시됩니다.

- **점진적으로 이동하고 Microsoft 365?** 단계적으로 Microsoft 365 이동하려면 Microsoft 365 설치 마법사 실행을 건너뛰고 다음 순서로 Microsoft 365 기능을 채택하는 것이 좋습니다.

    1. [직원을 앱에](../add-users/add-users.md) Microsoft 365 다운로드하고 설치할 수 있도록 Office 추가합니다.

    2. [Office 앱을 다운로드 및 설치](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)하여 컴퓨터와 장치에서 Word, Excel 및 PowerPoint를 사용합니다.

    3. [모임에 사용할](#plan-for-teams) Microsoft Teams 설정

    4. [콘텐츠를 클라우드 저장소(Microsoft 365 또는](set-up-file-storage-and-sharing.md) 팀 OneDrive SharePoint 이동하세요.

    5. 준비가 되면 관리 센터의 왼쪽  탐색 창에서 설치를 선택하고 설치  페이지를 사용하여 도메인 및 전자 메일을 [이동합니다.](add-domain.md) [](https://go.microsoft.com/fwlink/p/?linkid=2024339)

## <a name="check-that-your-devices-meet-system-requirements"></a>장치가 시스템 요구 사항을 충족하는지 확인

조직의 각 사람은 최대 5대의 PC 및 Mac에 Office 2016 제품군(Word, Excel, PowerPoint 등)을 설치할 수 있습니다. 비즈니스용 [Office 2016 제품군](https://go.microsoft.com/fwlink/?LinkId=534827) 설치에 대한 운영 체제 및 컴퓨터 요구 사항을 확인하세요.
  
모바일 앱은 iOS, Android 및 모바일 장치에 설치할 Windows 있습니다. [Office의 시스템 요구 사항](https://go.microsoft.com/fwlink/?LinkId=534827)에서 모바일 장치 및 브라우저 지원에 관한 정보를 찾을 수 있습니다.
  
## <a name="plan-for-email"></a>전자 메일에 대한 계획

기존 전자 메일 서비스에서 전자 메일 서비스로 Microsoft 365 전환하는 데 일반적으로 2일이 소요됩니다.
  
### <a name="plan-for-email-downtime"></a>전자 메일 가동 중지 시간 계획
  
전자 메일에 대해 Microsoft 365 경우:
  
- 비즈니스 전자 메일 주소(예: *rob \@ contoso.com*)를 다른 전자 메일 서비스에서 Microsoft 365 이동하려면 메일을 새 Microsoft 365 사서함으로 배달해야 합니다. 설치 페이지에서 사용자  데이터 마이그레이션을 선택하여 이  작업을 진행합니다. 여기서 도메인 호스트에서 필요한 업데이트를 단계적으로 안내합니다.

- 도메인 호스트를 업데이트하면 일반적으로 1~2시간 이내에 변경 사항이 적용됩니다. 그러나 인터넷을 통해 변경 내용이 업데이트되는 데 최대 72시간이 걸릴 수 있습니다.

- 전자 메일의 다운타임이 있을 수 있기 때문에 전자 메일을 더 적게 받을 때 저녁이나 주말에 Microsoft 전자 메일로 전환하는 것이 좋습니다.

### <a name="plan-to-move-your-existing-email-contacts-and-calendar"></a>기존 전자 메일, 연락처 및 일정 이동 계획
  
전자 메일 계정에 Microsoft 365 경우 기존 전자 메일, 연락처 및 일정을 가져올 수 있습니다. 설치 **페이지에서는** 대부분의 시나리오에서 기존 전자 메일과 연락처를 이동할 수 있습니다. 하나 이상의 사서함으로 이동하는 단계별 지침도 제공합니다.
  
|**사서함이 몇 개인가요?**|**권장 사항**|
|:-----|:-----|
|몇 개  <br/> |설치 페이지를 사용하여 사서함을  마이그레이션하지 않는 경우 사서함 소유자가 자신의 전자 메일 및 연락처를 마이그레이션할 수 있습니다. 비즈니스용 전자 메일 및 연락처를 비즈니스용 Microsoft 365 [마이그레이션을 참조하세요.](migrate-email-and-contacts-admin.md)  <br/> |
|여러 개  <br/> |Gmail에서 마이그레이션하는 경우 [Migrate G Suite mailboxes to Microsoft 365.](/Exchange/mailbox-migration/migrating-imap-mailboxes/migrate-g-suite-mailboxes)  <br/> 마이그레이션을 비롯한 다른 전자 메일 공급자에서 마이그레이션하는 Exchange 여러 전자 메일 계정을 마이그레이션하는 방법을 [Microsoft 365.](/Exchange/mailbox-migration/mailbox-migration)  <br/> |

## <a name="plan-for-file-storage-and-migration"></a>파일 저장소 및 마이그레이션 계획

Microsoft 365, 소규모 조직 및 기업을 위한 클라우드 저장소를 제공합니다. 저장할 위치와 관련한 지침은 의 에 문서를 저장할 수 있는 [Microsoft 365.](../../business-video/store-files.md)
  
- **수백 개의** 파일을 OneDrive [팀](https://support.microsoft.com/office/45114744-6D42-45CD-8975-F9617819BDEB) 사이트로 SharePoint [있습니다.](https://support.microsoft.com/office/da549fb1-1fcb-4167-87d0-4693e93cb7a0#__toc384119242) You can upload 100 files at a time. Avoid uploading files larger than 2GB, which is the maximum file size by default.
  
- **수천 개의 파일을** 저장소로 이동하려면 Microsoft 365 온라인 제한 SharePoint [검토하세요.](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits) 마이그레이션 도구를 사용하거나 마이그레이션을 도와줄 [파트너](https://go.microsoft.com/fwlink/?linkid=391089)를 고용하는 것이 좋습니다. 많은 수의 파일을 마이그레이션하는 방법에 대한 자세한 내용은 [SharePoint Online 및 OneDrive 마이그레이션 사용자 가이드](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets)를 참조하세요.
  
## <a name="plan-for-teams"></a>계획 Teams

구독을 Microsoft Teams 조직의 다른 사용자와 통화할 수 있습니다. 예를 들어 조직에 10명이 있는 경우 특별한 설정 없이 조직에서 전화를 걸고 Teams 수 있습니다. 자세한 내용은 Get [started with Microsoft Teams.](/MicrosoftTeams/get-started-with-teams-quick-start)

대규모 조직 또는 비즈니스용 Skype, 비즈니스용 Skype 또는 하이브리드 배포를 시작하는 경우 를 배포하는 [방법을 Microsoft Teams.](/MicrosoftTeams/how-to-roll-out-teams)
  
## <a name="plan-for-integration-with-active-directory-or-other-software"></a>Active Directory 또는 다른 소프트웨어와 통합 계획

- **온-프레미스 Active Directory와 통합하길 원하세요?** 이 기능을 사용하여 프레미스 Active Directory와 Microsoft 365 통합할 수 Azure Active Directory 커넥트. 자세한 내용은 [Set up directory synchronization for Microsoft 365.](../../enterprise/set-up-directory-synchronization.md)
  
- **다른 회사에서 만든 소프트웨어와 Microsoft 365 통합하고 싶나요?** 조직의 다른 소프트웨어와 Microsoft 365 통합해야 하는 경우 배포를 [](https://go.microsoft.com/fwlink/?linkid=391089) 지원하기 위해 파트너를 고용하는 것이 좋습니다.
  
## <a name="do-you-want-someone-to-help-you-set-up-microsoft-365"></a>다른 사용자가 사용자 설정에 도움을 Microsoft 365?

- **직원 수가 50명 미만인 경우:**

  - **도움을 요청하면 에 전화가 걸리게 될 것입니다.** After you buy Microsoft 365, you can access the admin center (you don't need to run setup to get it). At the bottom of the admin center, select **Need help?** 문제를 설명하고 문의할 것입니다. 
  - **문의 [Microsoft 365 비즈니스 지원에](../../business-video/get-help-support.md) 문의하세요.** We're here to help! 
  - **[Microsoft 파트너](https://go.microsoft.com/fwlink/?linkid=391089)** 를 고용해 보세요. 시간이 부족하거나 고급 요구 사항이 있는 경우(예: 수천 개의 파일을 클라우드 저장소로 이동하거나 Microsoft 365 소프트웨어와 통합) 숙련된 파트너가 큰 도움이 될 수 있습니다. 

- **직원 수가 50명 이상인 경우**[FastTrack 온보딩 센터](https://go.microsoft.com/fwlink/?LinkId=517115)에서 배포를 도와줄 수 있습니다.