---
title: 비즈니스용 Office 365 설정 계획
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- MET150
- MOE150
ms.assetid: eb926624-018b-4486-bf11-5fba6ee4d645
description: 비즈니스용 Office 365을 설정 하기 위해 수행 해야 하는 작업에 대해 알아봅니다.
ms.openlocfilehash: 3b38f0092b323175c6a12170105e781fab21934d
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42247839"
---
# <a name="plan-your-setup-of-office-365-for-business"></a>비즈니스용 Office 365 설정 계획

이 문서는 Office 365 비즈니스 요금제를 구독한 사용자용입니다.
  
조직을 Office 365으로 이동 하기 전에 결정 해야 할 몇 가지 사항 및 정보를 제공 해야 합니다.
  
## <a name="info-to-have-on-hand-before-you-run-the-office-365-setup-wizard"></a>Office 365 설정 마법사를 실행하기 전에 알아야 할 정보

Office 365 설정 마법사를 실행하고 Office 365로 도메인을 이동할 준비가 되면 아래 정보를 알아둬야 합니다.
  
- Office 365에 추가하려는 사용자의 목록. Office 365에 이미 사용자를 추가했더라도 도메인 정보를 업그레이드하려면 여기에 이름을 입력해야 합니다.

- 로그인할 수 있도록 직원들에게 Office 365 사용자 ID와 암호를 알릴 방법. 전화로 정보를 알리거나 개인 전자 메일 주소로 정보를 보낼 계획이세요? 직원들은 Office 365 전자 메일에 액세스할 수 없으므로 전자 메일 주소로 보낼 수 없습니다.

- 조직에 대 한 도메인 이름 (예: contoso.com)이 **있고** Office 365 전자 메일을 사용 하려는 경우 도메인을 등록 하 고 로그인 정보를 확인 해야 합니다.

## <a name="what-happens-when-you-run-the-office-365-setup-wizard"></a>Office 365 설정 마법사를 실행하는 경우

설치 마법사는 컴퓨터에 Office 365 앱을 설치 하 고, 도메인을 추가 및 확인 하 고, 사용자를 추가 및 할당 하 고, 도메인에 연결 하는 과정을 안내 합니다.

> [!NOTE]
> [비즈니스용 Office 365의 관리자 역할](../add-users/assign-admin-roles.md) 을 마법사에서 추가 하는 사용자에 게 할당 해야 하는 경우 나중에 **사용자** 페이지에서이 작업을 수행할 수 있습니다. 
  
설정 마법사를 완료 하지 않으면 [관리 센터](https://go.microsoft.com/fwlink/p/?linkid=2024339) > **설치**에서 언제 든 지 설치 작업을 완료할 수 있습니다. 여기서는 다른 전자 메일 서비스에서 전자 메일 및 연락처를 마이그레이션하고, 관리자 계정의 도메인을 변경 하 고, 청구 정보를 관리 하 고, 사용자를 추가 또는 제거 하 고, 암호를 재설정 하 고, 기타 비즈니스 기능을 수행할 수 있습니다. 설치 마법사와 **설정** 페이지 간의 차이점에 대 한 자세한 내용은 [Office 365 설치 마법사와 설치 페이지 간의 차이점](o365-setup-wizard-and-setup-page.md)을 참조 하십시오.

문제가 발생하면 Microsoft에 문의하세요. [Microsoft에서 도와드리겠습니다.](../contact-support-for-business-products.md)
  
## <a name="when-not-to-use-the-setup-wizard-active-directory-synchronization-and-hybrid-environments"></a>설정 마법사를 사용하면 안 되는 경우: Active Directory 동기화 및 하이브리드 환경

온-프레미스 환경에서 데이터 나 사용자를 마이그레이션하거나 디렉터리 동기화를 포함 하는 하이브리드 시스템을 설정 하는 두 가지 시나리오가 있습니다. 두 범주 중 하나에 해당 하는 경우 다음 문서의 지침을 따릅니다.
  
- 온-프레미스 Active Directory와 디렉터리 동기화를 설정하려면 [Office 365에서 디렉터리 동기화 설정](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization)을 참조하고 Office 365의 다른 ID 모델을 이해하려면 [Office 365 ID 및 Azure Active Directory 이해](https://docs.microsoft.com/office365/enterprise/about-office-365-identity)를 참조하세요.

- Exchange 하이브리드를 설정하려면 다음에서 하이브리드 Exchange를 설정(DNS 레코드 설정 포함)하는 여러 다른 방법을 모두 안내하는 전체 지침 집합을 찾을 수 있습니다. [Exchange Server 배포 도우미](https://aka.ms/exdeploy)

- SharePoint 하이브리드, 특히 하이브리드 검색 및 사이트 기능을 설정하려면 [SharePoint의 하이브리드 검색](https://docs.microsoft.com/SharePoint/hybrid/hybrid-search-in-sharepoint)을 참조하세요.

## <a name="move-to-office-365-all-at-once-or-in-stages"></a>한 번에 또는 단계적으로 Office 365으로 이동

- **조직을 Office 365로 한 번에 이동 하 시겠습니까?** 그렇다면 도메인을 Office 365 바로 이동 하도록 계획 합니다. Office 365 설치 마법사를 실행 하 여 시작 합니다. 도메인을 설정 하 라는 메시지가 표시 됩니다.

- **Office 365으로 점진적으로 이동 하 고 싶으십니까?** 단계적으로 Office 365로 이전하려는 경우 Office 365 설정 마법사를 실행하지 말고 다음 순서에 따라 Office 365 기능을 채택하는 것이 좋습니다.

    1. [Office 365에 직원을 추가](../add-users/add-users.md) 하여 직원들이 Office 앱을 다운로드하고 설치할 수 있도록 합니다.

    2. [Office 앱을 다운로드 및 설치](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658.aspx)하여 컴퓨터와 장치에서 Word, Excel 및 PowerPoint를 사용합니다.

    3. 모임에 사용할 [Microsoft 팀을 설정](#plan-for-teams) 합니다.

    4. [콘텐츠를 Office 365 클라우드 저장소로 이동](set-up-file-storage-and-sharing.md) 합니다 (OneDrive 또는 SharePoint 팀 사이트).

    5. 준비가 되 면 [관리 센터](https://go.microsoft.com/fwlink/p/?linkid=2024339)의 왼쪽 탐색 창에서 **설치** 를 선택 하 고 **설정** 페이지를 사용 하 여 [도메인 및 전자 메일을 이동](add-domain.md)합니다.

## <a name="check-that-your-devices-meet-system-requirements"></a>장치가 시스템 요구 사항을 충족하는지 확인

조직의 각 사용자는 최대 5 대의 Pc 및 Mac에 Office 2016 앱 제품군 (Word, Excel, PowerPoint 등)을 설치할 수 있습니다. 비즈니스용 [Office 2016 제품군](https://go.microsoft.com/fwlink/?LinkId=534827) 설치에 대한 운영 체제 및 컴퓨터 요구 사항을 확인하세요.
  
모바일 앱은 iOS, Android 및 Windows 장치에 설치할 수 있습니다. [Office의 시스템 요구 사항](https://go.microsoft.com/fwlink/?LinkId=534827)에서 모바일 장치 및 브라우저 지원에 관한 정보를 찾을 수 있습니다.
  
## <a name="plan-for-email"></a>전자 메일에 대한 계획

기존 전자 메일 서비스에서 Office 365로 이동 하려는 경우에는 일반적으로 2 일 이내에 전환을 수행 해야 합니다.
  
### <a name="plan-for-email-downtime"></a>전자 메일 가동 중지 시간 계획
  
전자 메일에 대해 Office 365를 사용하려는 경우:
  
- 회사 전자 메일 주소 (예: *rob@contoso.com*)를 다른 전자 메일 서비스에서 Office 365으로 이동 하려면 메일이 새 Office 365 사서함으로 배달 되도록 해야 합니다. 이 작업은 도메인 호스트에서 수행 해야 하는 업데이트를 단계별로 안내 하는 **설정** 페이지에서 **사용자 데이터 마이그레이션을** 선택 하 여 수행 합니다.

- 도메인 호스트를 업데이트하면 일반적으로 1~2시간 이내에 변경 사항이 적용됩니다. 하지만 인터넷에서 변경 사항을 업데이트 하는 데 최대 72 시간이 걸릴 수 있다는 점을 염두에 두어야 합니다.

- 전자 메일 가동 중지 시간이 있을 수 있으므로 전자 메일을 조금 수신하는 저녁이나 주말 동안 Office 365 전자 메일로 전환하는 것이 좋습니다.

### <a name="plan-to-move-your-existing-email-contacts-and-calendar"></a>기존 전자 메일, 연락처 및 일정 이동 계획
  
전자 메일 계정에 대해 Office 365를 사용하려는 경우 기존 전자 메일, 연락처 및 일정을 가져올 수 있습니다. **설정** 페이지에서는 대부분의 시나리오에서 기존 전자 메일 및 연락처를 이동할 수 있습니다. 하나 이상의 사서함으로 이동하는 단계별 지침도 제공합니다.
  
|**사서함이 몇 개인가요?**|**권장 사항**|
|:-----|:-----|
|몇 개  <br/> |**설정** 페이지를 사용 하 여 사서함을 마이그레이션하지 않으려면 사서함 소유자가 자신의 전자 메일 및 연락처를 마이그레이션하도록 할 수 있습니다. [비즈니스용 Office 365로 전자 메일 및 연락처 마이그레이션](migrate-email-and-contacts-admin.md)을 참조하세요.  <br/> |
|여러 개  <br/> |Gmail에서 마이그레이션하는 경우 [Office 365로 G Suite 사서함 마이그레이션을](https://docs.microsoft.com/Exchange/mailbox-migration/migrating-imap-mailboxes/migrate-g-suite-mailboxes)참조 하세요.  <br/> Exchange를 포함 하 여 다른 전자 메일 공급자에서 마이그레이션하는 경우 [여러 전자 메일 계정을 Office 365로 마이그레이션하는 방법을](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)참조 하세요.  <br/> |

## <a name="plan-for-file-storage-and-migration"></a>파일 저장소 및 마이그레이션 계획

Office 365에서는 개인, 소규모 조직 및 기업을 위한 클라우드 저장소를 제공 합니다. 저장 위치에 대한 지침은 [Office 365에서 문서를 저장할 수 있는 위치](https://support.office.com/article/c7c20284-bc94-47f4-9728-d28e9daf0790.aspx)를 참조하세요.
  
- **수백 개의 파일** 을 [OneDrive](https://support.office.com/article/45114744-6D42-45CD-8975-F9617819BDEB.aspx) 로 이동 하거나 [SharePoint 팀 사이트로](https://support.office.com/article/da549fb1-1fcb-4167-87d0-4693e93cb7a0.aspx#__toc384119242)이동할 수 있습니다. You can upload 100 files at a time. Avoid uploading files larger than 2GB, which is the maximum file size by default.
  
- **Office 365 저장소로 수천 개의 파일을 이동하려는 경우**[SharePoint Online 제한](https://go.microsoft.com/fwlink/p/?LinkID=856113)을 검토하세요. 마이그레이션 도구를 사용하거나 마이그레이션을 도와줄 [파트너](https://go.microsoft.com/fwlink/?linkid=391089)를 고용하는 것이 좋습니다. 많은 수의 파일을 마이그레이션하는 방법에 대한 자세한 내용은 [SharePoint Online 및 OneDrive 마이그레이션 사용자 가이드](https://go.microsoft.com/fwlink/?LinkId=723574)를 참조하세요.
  
## <a name="plan-for-teams"></a>팀 계획

Microsoft 팀을 사용 하 여 조직의 다른 사용자에 게 구독을 요청할 수 있습니다. 예를 들어 조직에 사용자가 10 명 있는 경우 특별 한 설정 없이 팀을 사용 하 여 서로 전화를 걸어 IM을 사용할 수 있습니다. 자세한 내용은 [Microsoft 팀 시작](https://docs.microsoft.com/MicrosoftTeams/get-started-with-teams-quick-start)을 참조 하세요.

대규모 조직의 경우 또는 비즈니스용 Skype, 온-프레미스 또는 하이브리드 배포를 시작 하 [는 경우 Microsoft 팀을 롤아웃하는 방법을](https://docs.microsoft.com/MicrosoftTeams/how-to-roll-out-teams)참조 하세요.
  
## <a name="plan-for-integration-with-active-directory-or-other-software"></a>Active Directory 또는 다른 소프트웨어와 통합 계획

- **온-프레미스 Active Directory와 통합하길 원하세요?** Azure Active Directory Connect를 사용하여 온-프레미스 Active Directory와 Office 365를 통합할 수 있습니다. 해당 지침은 [Office 365에서 디렉터리 동기화 설정](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization)을 참조하세요.
  
- **Office 365를 타사 소프트웨어와 통합하길 원하세요?** Office 365을 조직의 다른 소프트웨어와 통합 해야 하는 경우 배포를 도와줄 [파트너를 고용 하는](https://go.microsoft.com/fwlink/?linkid=391089) 것이 좋습니다.
  
## <a name="do-you-want-someone-to-help-you-set-up-office-365"></a>다른 사람이 Office 365 설정을 도와주기를 원하시나요?

- **직원 수가 50명 미만인 경우:**

  - **도움을 요청 하 고 사용자에 게 전화를 걸어 보세요**. Office 365를 구매한 후에는 관리 센터에 액세스할 수 있습니다 (설치 프로그램을 실행 하 여 해당 파일에 액세스 하지 않아도 됩니다). 관리 센터 아래쪽에서 **도움이 필요 하세요?** 를 선택 합니다. 문제를 설명 하 고 사용자에 게 전화를 걸 것입니다. 
  - **질문을 통해 [비즈니스용 Office 365에](../contact-support-for-business-products.md) **문의 하세요. 언제든지 도와드리겠습니다! 
  - **[Microsoft 파트너](https://go.microsoft.com/fwlink/?linkid=391089)** 를 고용해 보세요. 시간이 부족하거나 고급 요구 사항(Office 365 클라우드 저장소에 수천 개의 파일 이동 또는 다른 소프트웨어와 통합)이 있는 경우, 숙련된 파트너가 많은 도움을 줄 수 있습니다. 

- **직원 수가 50명 이상인 경우**[FastTrack 온보딩 센터](https://go.microsoft.com/fwlink/?LinkId=517115)에서 배포를 도와줄 수 있습니다. 
