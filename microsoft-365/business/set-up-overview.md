---
title: 설정 개요
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: 등록, Microsoft 365 Business Premium 도메인 및 사용자 추가, 보안 정책 설정에 대한 설정 단계에 대해 자세히 알아보십시오.
ms.openlocfilehash: 7c09dca354781bf92f6bbecca0f3fb9875fb654515fe35c2f96cc780a894a764
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "53803225"
---
# <a name="overview-of-setup"></a>설정 개요

설치에 대한 짧은 Microsoft 365 Business Premium 시청합니다.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

이 비디오가 도움이 된 경우에는 [소규모 비즈니스와 Microsoft 365를 처음 사용하는 사용자를 위한 전체 교육 시리즈](../business-video/index.yml)를 참조하세요.

대부분의 설치 단계는 안내 설치에서 수행될 수 있지만 다른 옵션도 나열되어 있습니다.

## <a name="step-1-add-your-domain-and-users"></a>1단계: 도메인 및 사용자 추가

   - **[도메인을 추가합니다(등록하는](set-up.md#add-your-domain-to-personalize-sign-in)** 동안 도메인을 [구입한](sign-up.md)경우 이 단계는 이미 완료된 것입니다.)

   - **사용자를 추가합니다.** 다음 세 가지 방법으로 사용자를 추가할 수 있습니다.
        - 안내 [설치에서 을(를) 설치합니다.](set-up.md#add-users-in-the-wizard)
        - 디렉터리 동기화를 사용하여 [Azure AD](../enterprise/set-up-directory-synchronization.md) 커넥트 디렉터리가 있는 경우 사용자를 추가합니다.
        - 나중에 관리 [센터에서 사용자를](../admin/add-users/add-users.md) 추가할 수도 있습니다.
## <a name="step-2-set-up-security-policies-and-configure-devices"></a>2단계: 보안 정책 설정 및 장치 구성 

  - 안내 [설치를 사용하여](set-up.md#protect-your-organization) 장치 정책을 구성합니다. 
  - 나중에 관리 센터 및 [Intune](/intune/tutorial-walkthrough-intune-portal)포털에서 추가하거나 편집할 수도 있습니다. [](view-policies-and-devices.md)
  - 또한 설치 마법사는 기본 위협 방지 및 데이터 손실 방지 설정도 설치합니다.
  
  설치 마법사의 보안 설정 외에도 다음 설정을 추가하여 보안을 강화할 수 있습니다.

- **전자 메일 맬웨어 보호**
- **Defender for Office 365**
- **Exchange Online Archiving**
- **Azure Information Protection(계획1)**

시작을 위해 위협 [](increase-threat-protection.md) 방지 강화 및 준수 [기능 설정 을 참조합니다.](set-up-compliance.md)

모범 보안 모범 사례에 대한 로드맵을 Microsoft 365 Business Premium [10가지](/office365/admin/security-and-compliance/secure-your-business-data) 방법도 참조합니다.

## <a name="step-3-set-up-and-manage-windows-10-devices"></a>3단계: 장치 설정 Windows 10 관리

안내 설치를 완료한 후 조직의 모든 Windows 10 보호할 수 있습니다.
  
- Windows 10 Pro 는 Microsoft 365 Business Premium [](pre-requisites-for-data-protection.md) Windows 대한 선행 Microsoft 365 Business Premium, Pro, Windows 8 Pro 또는 Windows 8.1 Pro 7개가 있는 경우 구독에서 [Windows 10 Pro.](./upgrade-to-windows-pro-creators-update.md)
- PC의 보안 [Windows 10](secure-win-10-pcs.md) 단계에 따라 장치용 정책을 Windows 10.

Azure AD에 Windows 10 장치를 가입하면 Windows 10 정책이 적용됩니다. 자세한 내용은 [Set up Windows devices for Microsoft 365 참조하세요.](set-up-windows-devices.md)

## <a name="step-4-install-microsoft-365-apps-for-business"></a>4단계: 설치 비즈니스용 Microsoft 365 앱
- 설치 마법사를 사용하여 Office 디바이스에 Windows 수 [있습니다.](set-up.md#deploy-office-365-client-apps)
- 사용자가 앱 [및 Office 앱을](/office365/admin/setup/install-applications) Windows 수 있습니다.
     
## <a name="advanced"></a>고급
- **Autopilot을 사용하여 새 장치 설정**
            
     [Autopilot을](add-autopilot-devices-and-profile.md) Windows 사용자를 위해 새 Windows 10  장치를 자동으로 미리 구성할 수 있지만 이 작업을 할 [](https://www.microsoft.com/solution-providers/search) 수 있는 파트너를 추가하는 것이 더 쉬워집니다. 또한 으로 [이동하여](https://go.microsoft.com/fwlink/?linkid=874598)Microsoft Store 클라우드 기술 전문가에게 구매한 새 디바이스를 설정할 수 있습니다.

- **온-프레미스 리소스 액세스**

     - 조직에서 Windows Server Active Directory 사용하는 경우 Microsoft 365 Business Premium 장치를 보호하는 동시에 로컬 인증이 필요한 Windows 10 리소스에 대한 액세스는 유지 관리하도록 설정할 수 있습니다. 도메인에 가입된 Windows 10 장치를 관리하도록 설정의 단계를 Microsoft 365 Business Premium 설정하세요. [](manage-windows-devices.md) 이 방법이 기본 설정 방법으로, 이 상태의 장치를 하이브리드 Azure AD 가입 장치라고 합니다.

    - 비즈니스에 일부 사내 리소스(예: 파일 공유 및 프린터)가 포함된 로컬 Active Directory가 있는 경우 다음 단계를 수행하여 Azure AD 가입 장치에 이러한 리소스에 대한 액세스 권한을 부여할 수 있습니다. 액세스의 [Azure AD](access-resources.md)가입 장치에서는 Microsoft 365 Business Premium.

## <a name="related-content"></a>관련 콘텐츠

[Microsoft 365 Business 교육 비디오](../business-video/index.yml)(링크 페이지)