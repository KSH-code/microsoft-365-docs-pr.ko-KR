---
title: 엔터프라이즈용 Microsoft 365 앱
description: Microsoft 365 앱을 배포하는 방법, 앱 업데이트 방법 및 설정 관리 방법
keywords: 변경 내용
ms.service: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: 98995084fb7de9ecb434b70b5d38793a20675f19
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840352"
---
# <a name="microsoft-365-apps-for-enterprise"></a>엔터프라이즈용 Microsoft 365 앱

## <a name="initial-deployment"></a>초기 배포

Microsoft Managed Desktop을 사용하면 엔터프라이즈용 Microsoft 365 앱(64비트)이 모든 프로그램 디바이스에 이미지의 일부로 [설치됩니다.](../service-description/device-list.md) 다음 응용 프로그램이 모두 전달될 때 디바이스에 제공해야 합니다.

- Word
- Excel
- PowerPoint
- Outlook
- 게시자
- Access
- 비즈니스용 Skype
- OneNote

이 방법은 네트워크에 미치는 영향을 최소화하고 사용자가 장치를 받는 즉시 생산성을 확보할 수 있도록 합니다. 그런 다음 사용할 응용 프로그램을 설정하기 위해 관리되는 장치에 더 많은 정책을 배포합니다.

> [!NOTE]
> Microsoft Teams는 엔터프라이즈용 Microsoft 365 앱과 별도로 배포됩니다. 기본 이미지에는 포함되지 않습니다. 

### <a name="available-deployment-to-users"></a>사용자가 사용할 수 있는 배포

사용자에게 어떤 이유로든 장치에 Microsoft 365 앱이 없는 경우 패키지를 사용하여 디바이스를 예상 상태로 되 돌아올 수 있습니다. 최신 **Workplace-Office-Office365_Install** 그룹에 사용자를 추가하면 회사 포털에서 앱을 사용할 수 있습니다.

### <a name="microsoft-365-apps-for-enterprise-32-bit"></a>엔터프라이즈용 Microsoft 365 앱(32비트)

Microsoft Managed Desktop은 엔터프라이즈용 M365 앱의 32비트 버전 배포를 지원하지 않습니다.

## <a name="updates-to-microsoft-365-apps"></a>Microsoft 365 앱 업데이트

Microsoft 365 앱은 월별 엔터프라이즈 채널에서 [업데이트로 설정됩니다.](https://docs.microsoft.com/deployoffice/overview-update-channels#monthly-enterprise-channel-overview) 이 방법은 매월 사용자에게 새로운 Office 기능을 제공하지만 예측 가능한 릴리스 일정에 따라 매월 하나의 업데이트만 받게 됩니다. 업데이트는 두 번째 화요일에 릴리스됩니다. 이러한 업데이트에는 기능, 보안 및 품질 업데이트가 포함됩니다. 이러한 업데이트는 자동으로 발생하며 해당 특정 채널에 대한 Office CDN에서 직접 끌어오게 됩니다.

Microsoft Managed Desktop은 각 릴리스에 시차를 두어 환경의 잠재적인 문제를 식별합니다. Microsoft 365 앱 제품 그룹에서 릴리스된 후 28일 후에 출시를 완료합니다. Microsoft Managed Desktop은 다음과 같이 유효성 검사 및 테스트 시간을 허용하기 위해 서로 다른 그룹으로 업데이트 릴리스를 예약합니다. 

- 테스트: 제로 일
- 첫 번째: 제로 일
- 빠르기: 7일
- 광범위: 21일

Microsoft Managed Desktop은 장치에 [](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) 대한 업데이트 마감일을 7일로 설정합니다. 업데이트를 사용할 수 있는 경우 7일 이내에 설치해야 합니다. 마감일 [](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) 12시간 전에 응용 프로그램, 시스템 트레이의 여러 위치에서 업데이트가 필요하다는 알림을 받게 되고 마감일 이전에 15분 동안 경고가 표시됩니다. 업데이트를 완료하려면 모든 Microsoft 365 앱을 닫아야 합니다.

### <a name="pausing-or-rolling-back-an-update"></a>업데이트의 페이스킹 또는 롤백

어떤 이유로든 Microsoft 365 앱 업데이트를 일시 중지하거나 [](../working-with-managed-desktop/admin-support.md) 롤백해야 하는 경우 Microsoft Managed Desktop 포털을 통해 관리자 지원 요청을 제출합니다.

릴리스 중에 Microsoft Managed Desktop은 모든 Microsoft 365 앱의 오류 비율을 모니터링합니다. 새 릴리스와 새 릴리스의 선행 버전 간 품질이 크게 다른 경우 Microsoft Managed Desktop Admin 포털을 통해 연락할 수 있습니다. 심각도에 따라 릴리스를 일시 중지할지 묻거나 문제를 완화하기 위한 조치를 취했다고 알려드릴 것입니다. 

### <a name="delivery-optimization"></a>배달 최적화

배달 최적화는 Windows 10에서 사용할 수 있는 피어 투 피어 배포 기술입니다. 장치가 인터넷을 통해 Microsoft에서 다운로드한 업데이트와 같은 콘텐츠를 공유할 수 있습니다. 장치를 사용하면 Microsoft에서 업데이트를 완전히 다운로드하지 않고도 로컬 네트워크의 다른 장치에서 업데이트의 일부를 얻을 수 있기 때문에 네트워크 대역폭을 줄이는 데 도움이 될 수 있습니다.

[배달 최적화는](https://docs.microsoft.com/deployoffice/delivery-optimization) Windows 10 Enterprise 또는 Windows 10 Education 에디션을 실행하는 디바이스에서 기본적으로 사용하도록 설정됩니다. 

## <a name="settings-managed-by-microsoft-managed-desktop"></a>Microsoft Managed Desktop에서 관리되는 설정

Microsoft는 서비스의 일부로 일부 설정을 관리합니다. Microsoft Managed Desktop은 Office 보안 기준을 관리하지 않지만 관리 섹션의 지침에 따라 직접 설정할 [수](#settings-you-manage) 있습니다.

### <a name="update-settings"></a>설정 업데이트

Microsoft Managed Desktop은 [관리되는](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) 장치에 대한 모든 업데이트 설정을 유지 관리하며 이러한 설정을 수정해야 합니다.

### <a name="set-updates-to-occur-automatically"></a>자동으로 실행하도록 업데이트 설정

**기본값:** 사용

이 정책은 모든 Office 장치를 클라우드에서 최신으로 유지하도록 구성됩니다. 

### <a name="set-a-deadline-when-updates-have-to-be-applied"></a>업데이트를 적용해야 하는 마감일 설정

**기본값:** 7일

**UpdateDeadline** 정책은 장치에 업데이트가 적용되기 전에 사용자가 가지는 유예 기간을 구성하는 데 사용됩니다. 또한 이 마감일 [](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) 정책은 사용자에게 알림을 트리거하여 장치에 필요한 변경 내용을 알릴 수 있습니다.  

### <a name="defer-updates-on-a-device-for-a-period"></a>장치에서 기간 동안 업데이트 연기

이 정책은 각 업데이트 관리 장치 그룹에 대해 다르게 구성되고 Microsoft Managed Desktop이 업데이트 대상을 충족하는 데 필요합니다.  

- 테스트: 제로 일
- 첫 번째: 제로 일
- 빠른 7일
- 광범위: 21일

### <a name="update-notifications-settings"></a>알림 설정 업데이트

**기본값:** False

"업데이트 알림 숨기기" 설정은 Microsoft Managed Desktop 장치에서 **False로** 설정되어 [](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) 업데이트가 필요한 경우 사용자에게 알림하여 사용자에게 최상의 업데이트 환경을 제공합니다.

### <a name="specify-a-location-to-look-for-updates"></a>업데이트를 찾을 위치 지정

**기본값:** 월별 엔터프라이즈 채널

**UpdatePath** 및 **UpdateChannel** 정책의 조합은 업데이트 일정을 달성하는 데 필요한 경우 사용됩니다. 이러한 정책은 모든 Office 장치가 월별 엔터프라이즈 채널에 대한 CDN에서 직접 업데이트를 받게 하도록 설정됩니다.

### <a name="specify-the-target-version-of-microsoft-365-apps"></a>Microsoft 365 앱의 대상 버전 지정

대상 버전 정책은 특정 버전의 Office를 롤백하거나 고정하기 위해 Microsoft Managed Desktop에서 때때로 사용됩니다. 


### <a name="hide-the-option-to-enable-or-disable-office-automatic-updates"></a>Office 자동 업데이트를 사용 또는 사용하지 않도록 설정하는 옵션 숨기기

**기본값:** 사용

이 설정은 Microsoft Managed Desktop이 Microsoft 365 응용 프로그램에 대한 업데이트 대상을 충족하는 데 필요합니다. 

### <a name="first-run-settings"></a>첫 실행 설정 

Office를 처음 실행할 때 동작에 영향을 주는 몇 가지 설정이 있습니다.

### <a name="accept-the-license-terms-on-behalf-of-the-end-user"></a>최종 사용자를 대신하여 사용 조건에 동의합니다.

**기본값:** 사용 안

사용자가 Microsoft 365 앱을 처음 열면 사용 조건에 동의하라는 메시지가 사용자에게 표시됩니다. 사용자를 대신하여 사용 조건에 동의하려는 경우 Microsoft Managed Desktop Operations 팀에 이 설정을 사용하도록 요청하는 서비스 요청을 제출합니다. 

### <a name="suppress-outlook-mobile-check-box"></a>Outlook 모바일 표시 안 함 확인란

**기본값:** 사용 안

사용자가 Outlook을 처음 열면 Outlook Mobile을 설치하라는 메시지가 표시됩니다. 사용자에게 해당 확인란을 표시하지 못하게 하려는 경우 Microsoft Managed Desktop Operations 팀에 장치에 대해 이 설정을 사용하도록 설정해달고 요청하는 서비스 요청을 제출합니다. 

## <a name="other-settings"></a>기타 설정

Microsoft Managed Desktop이 선택적으로 사용자 대신 구성할 수 있는 다른 Microsoft 365 앱 설정이 있습니다. 

### <a name="disable-personal-onedrive"></a>개인 OneDrive를 사용하지 않도록 설정

**기본값:** 사용 안

일부 조직에서는 사용자가 장치에서 회사 파일과 개인 파일에 모두 액세스할 수 있는 사용자가 우려합니다. 이 설정을 사용하도록 설정해달는 Microsoft Managed Desktop Operations 팀에 서비스 요청을 제출할 수 있습니다. 

## <a name="settings-you-manage"></a>관리하는 설정

Microsoft Managed Desktop이 아직 서비스의 일부로 설정하지 않은 다른 많은 정책이 있습니다. Office 클라우드 정책 서비스를 사용하는 Microsoft Intune을 사용하여 이러한 정책을 [구성할 수](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) 있습니다. 이러한 정책을 설정하기 위해 다음 단계를 수행합니다.

1.  Microsoft Endpoint Manager 관리 센터에 로그인합니다.
2.  만들기 **> Office 앱에** 대한 앱 > 선택
3.  정책 구성 **만들기 페이지에서** 다음을 합니다.
    - 이름을 입력합니다.
    - 설명을 입력합니다(선택 사항).
    - **할당에서** 엔터프라이즈용 Microsoft 365 앱의 모든 사용자에게 해당 정책을 적용하는지 또는 웹용 Office를 사용하여 문서에 익명으로 액세스하는 사용자에게만 해당 정책을 적용하는지 여부를 선택하십시오.
    - 정책 구성에 할당된 AAD 기반 보안 그룹을 선택합니다. 각 정책 구성은 하나의 그룹에만 할당할 수 있으며 각 그룹에는 하나의 정책 구성만 할당할 수 있습니다.
    - 정책 구성에 포함될 정책 설정을 구성합니다. 정책 설정 이름을 검색하여 구성할 정책 설정을 찾을 수 있습니다. 또한 응용 프로그램, 정책이 권장되는 보안 기준인지 여부 및 정책이 구성되어 있는지 여부를 필터링할 수 있습니다. 플랫폼 열은 Windows 장치용 Microsoft 365 앱, 웹용 Office 또는 모든 엔터프라이즈용 Microsoft 365 앱에 정책이 적용되는지 여부를 나타냅니다.
4.  선택한 후 만들기를 **선택합니다.**

> [!NOTE]
> Office 구성 정책은 사용자 기반 배포만 지원
