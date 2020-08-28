---
title: 엔터프라이즈용 Microsoft 365 앱
description: Microsoft 365 앱을 배포 하는 방법, 업데이트 방식 및 설정 관리 방법
keywords: 변경 내용
ms.prod: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: b3843da0d35d78486ed22af6d057930ee4ad5bc9
ms.sourcegitcommit: 89b2ad0793c68415f178b8792a9757b9448345a6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/28/2020
ms.locfileid: "47295269"
---
# <a name="microsoft-365-apps-for-enterprise"></a>엔터프라이즈용 Microsoft 365 앱

## <a name="initial-deployment"></a>초기 배포

Microsoft Managed Desktop은 모든 [프로그램 장치](../service-description/device-list.md)에서 Microsoft 365 Apps for enterprise (64 비트)가 이미지의 일부로 설치 되도록 합니다. 다음 응용 프로그램은 제공 될 때 장치에 있어야 합니다.

- Word
- Excel
- PowerPoint
- Outlook
- Publisher
- Access
- 비즈니스용 Skype
- OneNote

이 방법을 사용 하면 네트워크 영향을 최소화 하 고 사용자가 장치를 수신 하는 즉시 생산성을 높일 수 있습니다. 그런 다음 추가 정책을 관리 되는 장치에 배포 하 여 사용할 응용 프로그램을 설정 합니다.

> [!NOTE]
> Microsoft 팀은 Microsoft 365 앱 for enterprise와 별도로 배포 되며, 기본 이미지에는 포함 되지 않습니다. 

### <a name="available-deployment-to-users"></a>사용자에 게 제공 되는 배포

어떤 이유로 든 사용자의 장치에 Microsoft 365 앱이 없는 경우 패키지를 사용 하 여 장치를 예상 상태로 되돌릴 수 있습니다. 사용자를 **최신 직장의 Office Office365_Install** 그룹에 추가 하면 회사 포털에서 해당 앱을 사용할 수 있게 됩니다.

### <a name="microsoft-365-apps-for-enterprise-32-bit"></a>Microsoft 365 Apps for enterprise (32 비트)

Microsoft Managed Desktop은 32 비트 버전의 M365 앱 배포를 지원 하지 않습니다.

## <a name="updates-to-microsoft-365-apps"></a>Microsoft 365 앱 업데이트

Microsoft 365 앱은 [월별 엔터프라이즈 채널](https://docs.microsoft.com/deployoffice/overview-update-channels#monthly-enterprise-channel-overview)에서 업데이트 되도록 설정 됩니다. 이 방법을 사용 하면 매달 새로운 Office 기능을 제공할 수 있지만 예측 가능한 릴리스 일정에는 월별 업데이트가 하나씩만 제공 될 예정입니다. 업데이트는 해당 월의 두 번째 화요일에 릴리스됩니다. 이러한 업데이트에는 기능, 보안 및 품질 업데이트가 포함 될 수 있습니다. 이러한 업데이트는 자동으로 실행 되며 해당 특정 채널에 대 한 Office CDN에서 직접 가져옵니다.

Microsoft Managed Desktop은 각 staggers 해당 환경에서 발생할 수 있는 문제를 식별 합니다. Microsoft 365 앱 제품 그룹의 릴리스 28 일 후에 출시 될 예정입니다. Microsoft Managed Desktop은 다음과 같은 유효성 검사 및 테스트에 대 한 시간을 허용 하도록 다른 그룹으로 릴리스를 업데이트 합니다. 

- 테스트: 0 일
- 먼저: 0 일
- 빠름: 7 일
- 광범위: 21 일

Microsoft Managed Desktop은 장치에 대 한 7 일 동안의 [업데이트 마감 날짜](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) 를 설정 합니다. 업데이트를 사용할 수 있게 되 면 7 일 이내에 설치 해야 합니다. 사용자에 [게는 여러](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) 위치 (응용 프로그램)에서 최종 기한 이전의 시스템 용지함 12 시간에 대 한 업데이트가 필요 하며 기한 이전의 15 분 경고가 표시 됩니다. 업데이트를 완료 하려면 모든 Microsoft 365 앱을 닫아야 합니다.

### <a name="pausing-or-rolling-back-an-update"></a>업데이트 일시 중지 또는 롤백

어떤 이유로 든 Microsoft 365 앱 업데이트를 일시 중지 하거나 롤백해야 하는 경우 Microsoft Managed Desktop portal을 통해 [관리자 지원 요청](../working-with-managed-desktop/admin-support.md) 을 파일에 저장 합니다.

릴리스 중에 Microsoft Managed Desktop은 모든 Microsoft 365 앱의 오류율을 모니터링 합니다. 새 릴리스와 이전 버전의 선행 작업과 중요 한 품질이 큰 차이를 확인 하는 경우 Microsoft Managed Desktop Administration portal을 통해 사용자에 게 연락할 수 있습니다. 심각도에 따라 릴리스를 일시 중지할 것인지, 아니면 문제를 완화 하기 위해 조치를 취하는 것을 알려줍니다. 

### <a name="delivery-optimization"></a>배달 최적화

배달 최적화는 Windows 10에서 사용할 수 있는 피어 투 피어 배포 기술입니다. 이를 통해 장치에서 인터넷을 통해 Microsoft 로부터 다운로드 한 콘텐츠 (예: 업데이트)를 공유할 수 있습니다. 따라서 장치는 Microsoft에서 완전히 업데이트를 다운로드 하는 대신 로컬 네트워크의 다른 장치에서 업데이트의 일부를 가져올 수 있으므로 네트워크 대역폭을 줄이는 데 도움이 될 수 있습니다.

Windows 10 Enterprise 또는 Windows 10 교육용 버전을 실행 하는 장치에서 [배달 최적화](https://docs.microsoft.com/deployoffice/delivery-optimization) 가 기본적으로 사용 되도록 설정 됩니다. 

## <a name="settings-managed-by-microsoft-managed-desktop"></a>Microsoft Managed Desktop에서 관리 하는 설정

Microsoft는 일부 설정을 서비스의 일부로 관리 합니다. Microsoft Managed Desktop은 Office 보안 기준을 관리 하지 않지만 사용자가 [관리 하는 설정](#settings-you-manage) 섹션의 지침에 따라 직접 설정할 수 있습니다.

### <a name="update-settings"></a>업데이트 설정

Microsoft Managed Desktop은 관리 장치에 대 한 모든 [업데이트 설정을](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) 유지 관리 하며, 이러한 설정을 수정 해야 합니다.

### <a name="set-updates-to-occur-automatically"></a>자동으로 실행하도록 업데이트 설정

**기본값**: Enabled

이 정책은 모든 Office 장치를 클라우드에서 최신 상태로 유지할 수 있도록 하기 위해 구성 됩니다. 

### <a name="set-a-deadline-when-updates-have-to-be-applied"></a>업데이트를 적용 해야 하는 마감 날짜 설정

**기본값**: 7 일

**Updatedeadline** policy는 사용자가 장치에 업데이트를 적용 하기 전에 보유 하는 유예 기간을 구성 하는 데 사용 됩니다. 또한이 기한 정책은 사용자에 게 장치에서 필요한 변경 사항을 알리는 [알림을](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) 트리거합니다.  

### <a name="defer-updates-on-a-device-for-a-period"></a>일정 기간 동안 장치에 대 한 업데이트 지연

이 정책은 각 업데이트 관리 장치 그룹에 대해 서로 다른 방식으로 구성 되며 Microsoft Managed Desktop이 해당 업데이트 목표를 충족 하는 데 필요 합니다.  

- 테스트: 0 일
- 먼저: 0 일
- Fast 7 일
- 광범위: 21 일

### <a name="update-notifications-settings"></a>알림 설정 업데이트

**기본값**: False

Microsoft Managed Desktop 장치에서 "업데이트 알림 숨기기" 설정이 **False** 로 설정 되어 있으면 업데이트가 필요한 경우 사용자 [에 게 최적의](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) 업데이트 환경이 제공 됩니다.

### <a name="specify-a-location-to-look-for-updates"></a>업데이트를 찾을 위치 지정

**기본값**: 월별 엔터프라이즈 채널

업데이트 일정을 달성 하기 위해 필요한 경우 **Updatepath** 및 **UpdateChannel** 정책의 조합이 사용 됩니다. 이러한 정책은 모든 Office 장치에서 월별 엔터프라이즈 채널에 대 한 CDN에서 직접 업데이트를 받도록 설정 되어 있습니다.

### <a name="specify-the-target-version-of-microsoft-365-apps"></a>Microsoft 365 앱의 대상 버전 지정

특정 Office 버전을 롤백하거나 고정 하기 위해 Microsoft Managed Desktop에서 대상 버전 정책을 사용 하는 경우가 있습니다. 


### <a name="hide-the-option-to-enable-or-disable-office-automatic-updates"></a>Office 자동 업데이트를 사용 하거나 사용 하지 않도록 설정 하는 옵션 숨기기

**기본값**: Enabled

이 설정은 microsoft Managed Desktop이 Microsoft 365 응용 프로그램에 대 한 업데이트 목표를 충족 하기 위해 필요 합니다. 

### <a name="first-run-settings"></a>첫 번째 실행 설정 

Office를 처음 실행할 때의 동작에 영향을 주는 몇 가지 설정이 있습니다.

### <a name="accept-the-license-terms-on-behalf-of-the-end-user"></a>최종 사용자 대신 사용 조건에 동의 합니다.

**기본값**: 사용 안 함

사용자가 Microsoft 365 앱을 처음 열 때 사용권 조항에 동의 하 라는 메시지가 표시 됩니다. 사용자 대신 사용 조건에 동의 하려면 Microsoft Managed Desktop Operations 팀을 통해 서비스 요청을 사용 하도록 설정 하 라는 메시지를 파일에 입력 해야 합니다. 

### <a name="suppress-outlook-mobile-check-box"></a>Outlook 모바일 확인란 표시 안 함

**기본값**: 사용 안 함

사용자가 Outlook을 처음 열 때 Outlook Mobile을 설치 하 라는 메시지가 표시 됩니다. 사용자가 해당 확인란을 볼 수 없도록 하려면 Microsoft Managed Desktop Operations 팀을 통해 서비스 요청이 장치에 대해 사용 하도록 설정 되어 있는지 묻습니다. 

## <a name="other-settings"></a>기타 설정

Microsoft Managed Desktop에서 사용자 대신 선택적으로 구성할 수 있는 기타 Microsoft 365 앱 설정이 있습니다. 

### <a name="disable-personal-onedrive"></a>개인 OneDrive 사용 안 함

**기본값**: 사용 안 함

일부 조직에서는 사용자가 자신의 장치에서 회사 및 개인 파일에 모두 액세스 하는 것을 걱정 하 고 있습니다. 이 설정을 사용 하도록 설정 하려면 Microsoft Managed Desktop Operations 팀과 서비스 요청을 파일에 추가할 수 있습니다. 

## <a name="settings-you-manage"></a>관리 하는 설정

Microsoft Managed Desktop이 서비스의 일부로 아직 설정 되지 않은 다른 여러 정책이 있습니다. [Office 클라우드 정책](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) 서비스를 사용 하는 Microsoft Intune을 사용 하 여 이러한 구성을 구성할 수 있습니다. 이렇게 하려면 다음과 같이 하십시오.

1.  Microsoft Endpoint Manager 관리 센터에 로그인 합니다.
2.  **Office 앱에 대 한 앱 > 정책 > 만들기를 선택 합니다** .
3.  정책 구성 **만들기** 페이지에서 다음을 수행 합니다.
    - 이름을 입력 합니다.
    - 설명을 입력 합니다 (선택 사항).
    - **할당**에서이 정책이 Microsoft 365 앱 enterprise 용 모든 사용자에 게 적용 되는지, 아니면 웹을 사용 하 여 Office를 통해 문서에 익명으로 액세스 하는 사용자에 게 적용할지를 선택 합니다.
    - 정책 구성에 할당 된 AAD 기반 보안 그룹을 선택 합니다. 각 정책 구성은 하나의 그룹에만 할당할 수 있으며 각 그룹에는 하나의 정책 구성만 할당할 수 있습니다.
    - 정책 구성에 포함할 정책 설정을 구성 합니다. 정책 설정 이름을 검색 하 여 구성할 정책 설정을 찾을 수 있습니다. 또한 정책이 권장 되는 보안 기준 인지 여부 및 정책이 구성 되었는지 여부에 따라 응용 프로그램에서 필터링 할 수 있습니다. Platform 열에는 정책이 Windows 장치용 엔터프라이즈 용 Microsoft 365 앱, 웹을 위한 Office 또는 모두에 적용 되는지 여부를 나타냅니다.
4.  선택한 후 **만들기**를 선택 합니다.

> [!NOTE]
> Office 구성 정책만 사용자 기반 배포를 지원 합니다.
