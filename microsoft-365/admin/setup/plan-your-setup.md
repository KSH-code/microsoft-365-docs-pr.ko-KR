---
title: 비즈니스용 Microsoft 365 설정 계획
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- MET150
- MOE150
ms.assetid: eb926624-018b-4486-bf11-5fba6ee4d645
description: 비즈니스용 Microsoft 365로 이동하기 위한 요구 사항 및 고려 사항에 대해 자세히 알아보고
ms.openlocfilehash: 9158ad5a56b78fd8173ae81a2e9e4a5bd51633ca
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926825"
---
# <a name="plan-your-setup-of-microsoft-365-for-business"></a>비즈니스용 Microsoft 365 설정 계획

이 문서는 비즈니스용 Microsoft 365 요금제에 가입한 사용자용입니다.
  
조직을 Microsoft 365로 이동하기 전에 충족해야 하는 요구 사항, 필요한 정보 및 결정해야 하는 사항이 있습니다.


  
## <a name="info-to-have-on-hand-before-you-run-the-setup-wizard"></a>설정 마법사를 실행하기 전에 준비해야 할 정보

설치 마법사를 실행하고 도메인을 Microsoft 365로 이동할 준비가 되면 다음과 같은 정보를 준비해야 합니다.
  
- Microsoft 365에 추가할 사용자 목록입니다. Microsoft 365에 이미 추가한 경우에도 도메인 정보를 업데이트하는 경우 여기에 해당 이름을 입력해야 합니다.

- 로그인할 수 있도록 직원에게 사용자 ID와 암호를 알리는 방법 정보를 사용하여 호출하나요? 또는 개인 전자 메일 주소로 보내시겠습니까? 전자 메일에 액세스할 수 없습니다. 따라서 사용할 수 없습니다.

- 조직의 도메인 이름(예: contoso.com)이 있는 경우  Microsoft 전자 메일을 사용하려면 도메인이 등록된 위치를 알아야 합니다.

## <a name="what-happens-when-you-run-the-microsoft-365-setup-wizard"></a>Microsoft 365 설치 마법사를 실행할 때 발생하는 일

설치 마법사는 컴퓨터에 Microsoft 365 앱을 설치하고, 도메인을 추가 및 확인하고, 사용자를 추가하고, 라이선스를 할당하고, 도메인을 연결하는 방법을 안내합니다.

> [!NOTE]
> 마법사에서 추가한 사용자에게 비즈니스용 [Microsoft 365의](../add-users/assign-admin-roles.md) 관리자 역할을 할당해야 하는 경우 나중에 사용자 페이지에서 할당할 **수** 있습니다. 
  
설치 마법사를 완료하지 않은 경우 관리 센터 설치에서 원하는 경우 설치 작업을 [완료할 수](https://go.microsoft.com/fwlink/p/?linkid=2024339)  >  **있습니다.** 여기에서 다른 전자 메일 서비스의 전자 메일 및 연락처를 마이그레이션하고, 관리자 계정의 도메인을 변경하고, 청구 정보를 관리하고, 사용자를 추가 또는 제거하고, 암호를 재설정하고, 기타 비즈니스 기능을 할 수 있습니다. 설치 마법사와 설치 페이지 간의 차이점에 대한 자세한 내용은 Microsoft 365 설치 마법사와 설치 페이지 간의 [차이점을 참조하세요.](o365-setup-wizard-and-setup-page.md) 

문제가 발생하면 Microsoft에 문의하세요. [Microsoft에서 도와드리겠습니다.](../contact-support-for-business-products.md)
  
## <a name="when-not-to-use-the-setup-wizard-active-directory-synchronization-and-hybrid-environments"></a>설정 마법사를 사용하면 안 되는 경우: Active Directory 동기화 및 하이브리드 환경

데이터 또는 사용자를온-프레미스 환경에서 마이그레이션하거나 디렉터리 동기화를 포함하는 하이브리드 시스템을 설정하는 시나리오는 몇 가지가 있습니다. 두 범주 중 하나에 속하는 경우 다음 문서의 지침을 따르세요.
  
- Microsoft 365의 디렉터리 동기화를 설정하고 [Microsoft 365의](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)다양한 ID 모델을 이해하기 위해 Microsoft 365 Active Directory와 디렉터리 동기화를 설정하는 방법을 참조하세요. Microsoft [365 ID](https://docs.microsoft.com/microsoft-365/enterprise/about-microsoft-365-identity)및 Azure Active Directory 이해를 참조하세요.

- Exchange 하이브리드를 설정하려면 다음에서 하이브리드 Exchange를 설정(DNS 레코드 설정 포함)하는 여러 다른 방법을 모두 안내하는 전체 지침 집합을 찾을 수 있습니다. [Exchange Server 배포 도우미](https://aka.ms/exdeploy)

- SharePoint 하이브리드, 특히 하이브리드 검색 및 사이트 기능을 설정하려면 [SharePoint의 하이브리드 검색](https://docs.microsoft.com/SharePoint/hybrid/hybrid-search-in-sharepoint)을 참조하세요.

## <a name="move-to-microsoft-365-all-at-once-or-in-stages"></a>한 번 또는 단계에 따라 Microsoft 365로 이동

- **조직을 Microsoft 365로 한 번만 이동하고 싶나요?** 그렇다면 도메인을 Microsoft 365로 바로 이동하기 위한 계획을 세우는 것이 좋습니다. 먼저 Microsoft 365 설치 마법사를 실행합니다. 도메인을 설정하라는 메시지가 표시됩니다.

- **점진적으로 Microsoft 365로 이동하고 싶나요?** 단계적 Microsoft 365로 이동하려는 경우 Microsoft 365 설치 마법사 실행을 건너뛰고 다음 순서로 Microsoft 365 기능을 채택하는 것이 좋습니다.

    1. Office 앱을 다운로드하고 설치할 수 있도록 [직원을 Microsoft 365에](../add-users/add-users.md) 추가합니다.

    2. [Office 앱을 다운로드 및 설치](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)하여 컴퓨터와 장치에서 Word, Excel 및 PowerPoint를 사용합니다.

    3. [모임에 사용할 Microsoft Teams를](#plan-for-teams) 설정합니다.

    4. [콘텐츠를 Microsoft 365](set-up-file-storage-and-sharing.md) 클라우드 저장소(OneDrive 또는 SharePoint 팀 사이트)로 이동

    5. 준비가 되면 관리 센터의 왼쪽  탐색 창에서 설치를 선택하고 설치  페이지를 사용하여 도메인 및 전자 메일을 [이동합니다.](add-domain.md) [](https://go.microsoft.com/fwlink/p/?linkid=2024339)

## <a name="check-that-your-devices-meet-system-requirements"></a>장치가 시스템 요구 사항을 충족하는지 확인

조직의 각 사람은 최대 5대의 PC 및 Mac에 Office 2016 앱 제품군(Word, Excel, PowerPoint 등)을 설치할 수 있습니다. 비즈니스용 [Office 2016 제품군](https://go.microsoft.com/fwlink/?LinkId=534827) 설치에 대한 운영 체제 및 컴퓨터 요구 사항을 확인하세요.
  
모바일 앱은 iOS, Android 및 Windows 장치에 설치할 수 있습니다. [Office의 시스템 요구 사항](https://go.microsoft.com/fwlink/?LinkId=534827)에서 모바일 장치 및 브라우저 지원에 관한 정보를 찾을 수 있습니다.
  
## <a name="plan-for-email"></a>전자 메일에 대한 계획

기존 전자 메일 서비스에서 Microsoft 365로 이동하는 경우 일반적으로 전환하는 데 2일이 소요됩니다.
  
### <a name="plan-for-email-downtime"></a>전자 메일 가동 중지 시간 계획
  
전자 메일에 Microsoft 365를 사용하게 될 경우:
  
- 비즈니스 전자 메일 주소(예: *rob \@ contoso.com)를* 다른 전자 메일 서비스에서 Microsoft 365로 이동하려면 메일을 새 Microsoft 365 사서함으로 배달해야 합니다. 설치 페이지에서 사용자  데이터 마이그레이션을 선택하여 이  작업을 진행합니다. 여기서 도메인 호스트에서 필요한 업데이트를 단계적으로 안내합니다.

- 도메인 호스트를 업데이트하면 일반적으로 1~2시간 이내에 변경 사항이 적용됩니다. 그러나 인터넷을 통해 변경 내용이 업데이트되는 데 최대 72시간이 걸릴 수 있습니다.

- 전자 메일의 다운타임이 있을 수 있기 때문에 전자 메일이 적을 때 오후 또는 주말에 Microsoft 전자 메일로 전환하는 것이 좋습니다.

### <a name="plan-to-move-your-existing-email-contacts-and-calendar"></a>기존 전자 메일, 연락처 및 일정 이동 계획
  
전자 메일 계정에 Microsoft 365를 사용하려면 기존 전자 메일, 연락처 및 일정을 가져올 수 있습니다. 설치 **페이지를** 사용하면 대부분의 시나리오에서 기존 전자 메일과 연락처를 이동할 수 있습니다. 하나 이상의 사서함으로 이동하는 단계별 지침도 제공합니다.
  
|**사서함이 몇 개인가요?**|**권장 사항**|
|:-----|:-----|
|몇 개  <br/> |설치 페이지를 사용하여 사서함을  마이그레이션하지 않도록 하려는 경우 사서함 소유자가 자신의 전자 메일 및 연락처를 마이그레이션할 수 있습니다. 비즈니스용 [Microsoft 365로 전자](migrate-email-and-contacts-admin.md)메일 및 연락처 마이그레이션을 참조하세요.  <br/> |
|여러 개  <br/> |Gmail에서 마이그레이션하는 경우 G Suite 사서함을 [Microsoft 365로 마이그레이션을 참조하세요.](https://docs.microsoft.com/Exchange/mailbox-migration/migrating-imap-mailboxes/migrate-g-suite-mailboxes)  <br/> Exchange를 비롯한 다른 전자 메일 공급자에서 마이그레이션하는 경우 여러 전자 메일 계정을 [Microsoft 365로](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)마이그레이션하는 방법을 참조하세요.  <br/> |

## <a name="plan-for-file-storage-and-migration"></a>파일 저장소 및 마이그레이션 계획

Microsoft 365는 개인, 소규모 조직 및 대기업을 위한 클라우드 저장소를 제공합니다. 저장할 장소에 대한 지침은 [Microsoft 365에서](https://support.microsoft.com/office/c7c20284-bc94-47f4-9728-d28e9daf0790)문서를 저장할 수 있는 위치를 참조하세요.
  
- **수백 개의 파일을** [OneDrive](https://support.microsoft.com/office/45114744-6D42-45CD-8975-F9617819BDEB) 또는 SharePoint 팀 [사이트로 이동할 수 있습니다.](https://support.microsoft.com/office/da549fb1-1fcb-4167-87d0-4693e93cb7a0#__toc384119242) You can upload 100 files at a time. Avoid uploading files larger than 2GB, which is the maximum file size by default.
  
- **수천 개의** 파일을 Microsoft 365 저장소로 이동하려면 SharePoint Online 제한을 [검토하세요.](https://go.microsoft.com/fwlink/p/?LinkID=856113) 마이그레이션 도구를 사용하거나 마이그레이션을 도와줄 [파트너](https://go.microsoft.com/fwlink/?linkid=391089)를 고용하는 것이 좋습니다. 많은 수의 파일을 마이그레이션하는 방법에 대한 자세한 내용은 [SharePoint Online 및 OneDrive 마이그레이션 사용자 가이드](https://go.microsoft.com/fwlink/?LinkId=723574)를 참조하세요.
  
## <a name="plan-for-teams"></a>Teams 계획

Microsoft Teams를 사용하여 구독에 있는 조직의 다른 사용자와 통화할 수 있습니다. 예를 들어 조직에 10명이 있는 경우 특별한 설정 없이 Teams를 사용하여 서로 전화를 걸고 IM을 할 수 있습니다. 자세한 내용은 Microsoft Teams 시작을 [참조하세요.](https://docs.microsoft.com/MicrosoftTeams/get-started-with-teams-quick-start)

대규모 조직 또는 비즈니스용 Skype, 프레미스 또는 하이브리드 배포를 시작하는 경우 Microsoft Teams를 배포하는 [방법을 참조하세요.](https://docs.microsoft.com/MicrosoftTeams/how-to-roll-out-teams)
  
## <a name="plan-for-integration-with-active-directory-or-other-software"></a>Active Directory 또는 다른 소프트웨어와 통합 계획

- **온-프레미스 Active Directory와 통합하길 원하세요?** Azure Active Directory Connect를 사용하여 Microsoft 365와 Microsoft 365를 통합할 수 있습니다. 자세한 내용은 [Microsoft 365에 대한 디렉터리 동기화 설정을 참조하세요.](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)
  
- **Microsoft 365를 다른 회사에서 만든 소프트웨어와 통합하고 싶나요?** Microsoft 365를 조직의 다른 소프트웨어와 통합해야 하는 경우 [](https://go.microsoft.com/fwlink/?linkid=391089) 배포에 도움이 되는 파트너를 고용하는 것이 좋습니다.
  
## <a name="do-you-want-someone-to-help-you-set-up-microsoft-365"></a>다른 사용자가 Microsoft 365를 설정하는 데 도움을 주시겠습니까?

- **직원 수가 50명 미만인 경우:**

  - **도움을 요청하면 전화를 걸게 될 것입니다.** Microsoft 365를 구입한 후 관리 센터에 액세스할 수 있습니다(설치를 실행하기 위해 설치를 실행할 필요가 없습니다). At the bottom of the admin center, select **Need help?** 문제를 설명하고 문의해 드시겠습니다. 
  - **질문과 [함께 비즈니스용 Microsoft 365](../contact-support-for-business-products.md) 지원에 문의하세요.** We're here to help! 
  - **[Microsoft 파트너](https://go.microsoft.com/fwlink/?linkid=391089)** 를 고용해 보세요. 시간이 부족하거나 고급 요구 사항(예: 수천 개의 파일을 Microsoft 365 클라우드 저장소로 이동하거나 다른 소프트웨어와 통합)이 있는 경우 숙련된 파트너가 큰 도움이 될 수 있습니다. 

- **직원 수가 50명 이상인 경우**[FastTrack 온보딩 센터](https://go.microsoft.com/fwlink/?LinkId=517115)에서 배포를 도와줄 수 있습니다. 
