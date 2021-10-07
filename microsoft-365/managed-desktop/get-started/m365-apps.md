---
title: 엔터프라이즈용 Microsoft 365 앱
description: 배포 Microsoft 365 앱, 업데이트 방법 및 설정 관리 방법
keywords: 변경 내용
ms.service: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: f6df4ed3568be232927b7c427341d16eb869b7ed
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60199828"
---
# <a name="microsoft-365-apps-for-enterprise"></a>엔터프라이즈용 Microsoft 365 앱

## <a name="initial-deployment"></a>초기 배포

Microsoft Managed Desktop 엔터프라이즈용 Microsoft 365 앱64비트(64비트)가 모든 프로그램 디바이스에 이미지의 일부로 [설치되도록 합니다.](../service-description/device-list.md) 다음 응용 프로그램이 모두 전달될 때 디바이스에 제공해야 합니다.

- Word
- Excel
- PowerPoint
- Outlook
- 게시자
- Access
- 비즈니스용 Skype
- OneNote

이 접근 방식은 네트워크 영향을 최소화하고 사용자가 장치를 받는 즉시 생산성을 확보할 수 있도록 합니다. 그런 다음 관리되는 장치에 더 많은 정책을 배포하여 사용할 응용 프로그램을 설정합니다.

> [!NOTE]
> Microsoft Teams 배포할 때 엔터프라이즈용 Microsoft 365 앱 이미지에 포함되지 않습니다. 

### <a name="available-deployment-to-users"></a>사용자에게 사용 가능한 배포

어떤 이유로 Microsoft 365 앱 장치에 대한 사용자 계정이 없는 경우 패키지를 사용하여 디바이스를 예상 상태로 되 돌아올 수 있습니다. 최신 **Workplace-Office-Office365_Install** 그룹에 사용자를 추가하면 해당 그룹에서 앱을 사용할 수 회사 포털.

### <a name="microsoft-365-apps-for-enterprise-32-bit"></a>엔터프라이즈용 Microsoft 365 앱(32비트)

Microsoft Managed Desktop 32비트 버전의 엔터프라이즈용 M365 앱 배포를 지원하지 않습니다.

## <a name="updates-to-microsoft-365-apps"></a>업데이트 Microsoft 365 앱

Microsoft 365 앱 월별 채널에서 업데이트할 Enterprise [있습니다.](/deployoffice/overview-update-channels#monthly-enterprise-channel-overview) 이 방법을 사용하면 매월 새로운 Office 기능을 제공하지만 예측 가능한 릴리스 일정에 따라 매월 하나의 업데이트만 받게 됩니다. 업데이트는 두 번째 화요일에 릴리스됩니다. 이러한 업데이트에는 기능, 보안 및 품질 업데이트가 포함됩니다. 이러한 업데이트는 자동으로 발생하며 해당 특정 채널에 대한 Office CDN 직접 끌어오게 됩니다.

Microsoft Managed Desktop 각 릴리스에 시차를 두어 작업 환경에서 발생할 수 있는 문제를 식별할 수 있습니다. 앱 제품 그룹에서 릴리스 후 28일 후에 Microsoft 365 완료합니다. Microsoft Managed Desktop 그룹으로 업데이트 릴리스를 예약하여 다음과 같이 유효성 검사 및 테스트에 필요한 시간을 허용할 수 있습니다. 

- 테스트: 제로 일
- 첫 번째: 제로 일
- 빠르기: 3일
- 광범위: 7일

Microsoft Managed Desktop 업데이트 기한을 [7일로](/deployoffice/configure-update-settings-microsoft-365-apps) 설정하는 데 사용됩니다. 업데이트를 사용할 수 있는 경우 7일 이내에 설치해야 합니다. 마감일 [](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) 12시간 전에 응용 프로그램, 시스템 트레이의 여러 위치에서 업데이트가 필요하다는 알림을 받고 마감일 이전에 15분간 경고를 받게 됩니다. 모든 Microsoft 365 앱 완료하려면 닫아야 합니다.

### <a name="pausing-or-rolling-back-an-update"></a>업데이트의 페이스킹 또는 롤백

어떤 이유로든 앱 업데이트를 일시 중지하거나 롤백해야 Microsoft 365 [](../working-with-managed-desktop/admin-support.md) 포털을 통해 관리자 지원 요청을 Microsoft Managed Desktop 합니다.

릴리스 중에는 Microsoft Managed Desktop 오류율을 모니터링할 수 Microsoft 365 앱. 새 릴리스와 그 선행 버전 간 품질이 크게 다를 경우 Microsoft Managed Desktop 관리 포털을 통해 연락을 Microsoft Managed Desktop 있습니다. 심각도에 따라 릴리스를 일시 중지할지 묻거나 문제를 완화하기 위해 조치를 취했다고 알려드릴 것입니다. 

### <a name="delivery-optimization"></a>배달 최적화

배달 최적화는 다양한 기능에서 사용할 수 있는 피어 투 피어 Windows 10. 이 기능을 사용하면 장치가 인터넷을 통해 Microsoft에서 다운로드한 업데이트와 같은 콘텐츠를 공유할 수 있습니다. 장치를 사용하면 Microsoft에서 업데이트를 완전히 다운로드하지 않고도 로컬 네트워크의 다른 장치에서 업데이트의 일부를 다운로드할 수 있기 때문에 네트워크 대역폭을 줄이는 데 도움이 될 수 있습니다.

[배달 최적화는](/deployoffice/delivery-optimization) Windows 10 Enterprise 또는 Windows 10 Education 사용하도록 설정되어 있습니다. 

## <a name="settings-managed-by-microsoft-managed-desktop"></a>설정 관리되는 Microsoft Managed Desktop

Microsoft는 서비스의 일부로 일부 설정을 관리합니다. Microsoft Managed Desktop 보안 기준은 관리하지 않지만 Office 관리 섹션의 지침에 따라 직접 설정할 [설정](#settings-you-manage) 있습니다.

### <a name="update-settings"></a>설정 업데이트

Microsoft Managed Desktop [장치에](/deployoffice/configure-update-settings-microsoft-365-apps) 대한 모든 업데이트 설정을 유지 관리하며 이러한 설정을 수정해야 합니다.

### <a name="set-updates-to-occur-automatically"></a>자동으로 실행하도록 업데이트 설정

**기본값:** 사용

이 정책은 모든 Office 클라우드에서 최신으로 유지될 수 있도록 구성됩니다. 

### <a name="set-a-deadline-when-updates-have-to-be-applied"></a>업데이트를 적용해야 하는 마감일 설정

**기본값:** 7일

**UpdateDeadline** 정책은 장치에 업데이트가 적용되기 전에 사용자가 가지는 유예 기간을 구성하는 데 사용됩니다. 또한 이 마감일 [](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) 정책은 사용자에게 알림을 트리거하여 장치에 필요한 변경 내용을 알릴 수 있습니다.  

### <a name="defer-updates-on-a-device-for-a-period"></a>장치에 대한 업데이트 지연 기간

이 정책은 각 업데이트 관리 장치 그룹에 대해 다르게 구성됩니다. 이 정책은 Microsoft Managed Desktop 대상을 충족하는 데 필요합니다.  

- 테스트: 제로 일
- 첫 번째: 제로 일
- 빠른 7일
- 광범위: 21일

### <a name="update-notifications-settings"></a>알림 설정 업데이트

**기본값:** False

"업데이트 알림 숨기기" 설정은 Microsoft Managed Desktop 업데이트가 필요한 경우 사용자에게 알리는 [](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) 최상의 업데이트 환경을 제공하기 위해 모든 장치에서 **False로** 설정됩니다.

### <a name="specify-a-location-to-look-for-updates"></a>업데이트를 찾을 위치 지정

**기본값: 월별** Enterprise 채널

**UpdatePath** 및 **UpdateChannel** 정책의 조합은 업데이트 일정을 달성하기 위해 필요한 경우 사용됩니다. 이러한 정책은 모든 Office 장치가 월별 채널의 CDN 업데이트를 Enterprise 설정됩니다.

### <a name="specify-the-target-version-of-microsoft-365-apps"></a>대상 버전의 사용자 지정 Microsoft 365 앱

대상 버전 정책은 경우에 따라 특정 Microsoft Managed Desktop 버전을 롤백하거나 고정하기 위해 Office. 


### <a name="hide-the-option-to-enable-or-disable-office-automatic-updates"></a>자동 업데이트를 사용하도록 설정하거나 사용하지 않도록 설정하는 Office 숨기기

**기본값:** 사용

이 설정은 Microsoft Managed Desktop 응용 프로그램에 대한 업데이트 대상을 충족하는 Microsoft 365 필요합니다. 

### <a name="first-run-settings"></a>첫 실행 설정 

처음 실행될 때 동작에 영향을 주는 몇 가지 Office 있습니다.

### <a name="accept-the-license-terms-on-behalf-of-the-end-user"></a>최종 사용자를 대신하여 사용 조건에 동의합니다.

**기본값:** 사용 안 하게

사용자가 Microsoft 365 앱을 처음 열면 사용 조건에 동의하라는 메시지가 표시됩니다. 사용자를 대신하여 사용 조건에 동의하려는 경우 Microsoft Managed Desktop Operations 팀에 이 설정을 사용하도록 요청하는 서비스 요청을 제출합니다. 

### <a name="suppress-outlook-mobile-check-box"></a>모바일 Outlook 확인란 표시 안 함

**기본값:** 사용 안 하게

사용자가 모바일을 처음으로 Outlook 모바일을 설치하라는 메시지가 Outlook 합니다. 사용자에게 해당 확인란을 표시하지 못하게 하려는 경우 Microsoft Managed Desktop Operations 팀에 이 설정을 사용하도록 설정해달고 요청하여 서비스 요청을 제출합니다. 

## <a name="other-settings"></a>기타 설정

사용자 대신 Microsoft 365 구성할 Microsoft Managed Desktop 수 있는 다른 앱 설정이 있습니다. 

### <a name="disable-personal-onedrive"></a>개인 정보 보호 OneDrive

**기본값:** 사용 안 하게

일부 조직에서는 사용자가 장치에서 회사 파일과 개인 파일에 모두 액세스할 수 있는 사용자가 우려합니다. 이 설정을 사용하도록 요청하는 Microsoft Managed Desktop 작업 팀에 서비스 요청을 제출할 수 있습니다. 

## <a name="settings-you-manage"></a>설정 관리

다른 여러 정책이 Microsoft Managed Desktop 아직 서비스의 일부로 설정되지 않았습니다. 클라우드 정책 서비스를 사용하는 Microsoft Intune 사용하여 이러한 정책을 Office [수](/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) 있습니다. 이러한 정책을 설정하기 위해 다음 단계를 수행합니다.

1. Microsoft Endpoint Manager 센터에 로그인합니다.
2. 앱 **앱 > 정책 Office 만들기를 > 선택합니다.**
3. 정책 **구성 만들기** 페이지에서 다음을 클릭합니다.
    - 이름을 입력합니다.
    - 설명을 제공합니다(선택 사항).
    - **할당에서** 해당 정책을 모든 사용자 또는 엔터프라이즈용 Microsoft 365 앱 익명으로 액세스하는 사용자에게만 해당 정책을 적용하는지 웹용 Office.
    - 정책 구성에 할당된 AAD 기반 보안 그룹을 선택합니다. 각 정책 구성은 하나의 그룹에만 할당할 수 있으며 각 그룹에는 하나의 정책 구성만 할당할 수 있습니다.
    - 정책 구성에 포함될 정책 설정을 구성합니다. 정책 설정 이름을 검색하여 구성할 정책 설정을 찾을 수 있습니다. 또한 응용 프로그램, 정책이 권장되는 보안 기준인지 여부 및 정책이 구성되어 있는지 여부를 필터링할 수 있습니다. 플랫폼 열은 정책이 엔터프라이즈용 Microsoft 365 앱 장치, Windows 또는 모두에 웹용 Office 나타냅니다.
4. 선택한 후 만들기 를 **선택합니다.**

> [!NOTE]
> Office 구성 정책은 사용자 기반 배포만 지원
