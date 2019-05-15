---
title: 설정 개요
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Microsoft 365 Business에 대 한 설정 단계 개요입니다.
ms.openlocfilehash: efa4d352b00ebba0cb9754c93e773d1ddaef19df
ms.sourcegitcommit: 720881c1a9c5f708e1b4adf7e5ea4ff8da48ea99
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "33970455"
---
# <a name="overview-of-setup"></a>설치 개요

설정 단계 대부분은 설치 마법사에서 수행할 수 있지만 다른 옵션도 나열 됩니다.


## <a name="step-1-add-your-domain-and-users"></a>1 단계: 도메인 및 사용자 추가

   - **[도메인 추가](set-up.md#add-your-domain-to-personalize-sign-in)** ( [등록](sign-up.md)중에 도메인을 구매한 경우에는이 단계가 이미 완료 되었습니다.)

    - **사용자를 추가**합니다. 다음 세 가지 방법 중 하나를 통해이 작업을 수행할 수 있습니다.
        - [마법사](set-up.md#add-users-in-the-wizard)에서
        - 온-프레미스 Active directory가 있는 경우 디렉터리 동기화를 사용 하 여 [AZURE AD Connect를 사용 하 여 사용자를 추가](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) 합니다.
        - 나중에 관리 센터에서 [사용자를 추가할](add-users-m365b.md) 수도 있습니다.
## <a name="step-2-set-up-security-policies-and-configure-devices"></a>2 단계: 보안 정책 설정 및 장치 구성 

  - [설치 마법사](set-up.md#set-up-security-policies-and-device-configurations) 를 사용 하 여 장치 및 보안 정책을 구성 합니다. 
  - [관리 센터](view-policies-and-devices.md) 및 [Intune 포털](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal)에서 나중에 추가 하거나 편집할 수도 있습니다.
  - 설치 마법사의 보안 설정 외에도 다음 설정을 추가 하 여 보안을 강화할 수 있습니다.

      - **전자 메일 맬웨어 방지**
      - **ATP (Advanced Threat Protection) 안전한 링크**
      - **ATP 안전한 첨부 파일**
      - **ATP 피싱 방지**
      - **Exchange Online Archiving**
      - **Data Loss Prevention (DLP)**
      - **Azure Information Protection (Plan1**)

          시작 하려면 [고급 보안 정책을 설정](set-up-advanced-security.md)합니다 .를 참조 하세요.

        모범 보안 관행 로드맵에 대해서는 [Microsoft 365 Business의 보안을 위한 상위 10 가지 방법](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) 도 참조 하세요.

## <a name="step-3-set-up-and-manage-windows-10-devices"></a>3 단계: Windows 10 장치 설정 및 관리

   Windows 10 장치를 Azure AD에 가입 하면 [2 단계](#step-2-set-up-security-policies-and-configure-devices) 에서 설정한 정책이 적용 됩니다.

   - Windows 10 Pro는 Microsoft 365 Business에 대 한 [필수](pre-requisites-for-data-protection.md) 구성 요소 지만, Windows 7 Pro, Windows 8 Pro 또는 Windows 8.1 pro가 있는 경우 구독을 통해 [windows 10 Pro로 업그레이드할](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update)수 있습니다.
    - [설치 마법사](set-up.md#set-up-security-policies-and-device-configurations) 를 사용 하 여 Windows 10 장치에 대 한 정책을 구성 합니다.

## <a name="stes-4-install-office-365-business"></a>Stes 4: Office 365 Business 설치
- [설치 마법사](set-up.md#deploy-office-365-client-apps)를 사용 하 여 Windows 장치에 Office를 자동으로 설치할 수 있습니다.
- 관리 센터에서 Office를 자동으로 [설치](auto-install-or-uninstall-office.md) 합니다.
- 사용자가 Windows 및 장치용 [Office 앱을 설치할](https://docs.microsoft.com/office365/admin/setup/install-applications) 수 있도록 합니다.
     
## <a name="advanced"></a>고급
- **Autopilot을 사용 하 여 새 장치 설정**
            
     [Windows Autopilot](add-autopilot-devices-and-profile.md) 를 사용 하 여 사용자에 대해 **새** Windows 10 장치를 자동으로 미리 구성할 수 있지만,이 작업을 대신 수행할 수 있는 [파트너](https://www.microsoft.com/solution-providers/search) 를 가져오는 것이 더 쉬울 수 있습니다. [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) 로 이동 하 여 클라우드 기술 전문가가 사용자를 위해 구입한 새 장치를 설정 하 게 할 수도 있습니다.

- **온-프레미스 리소스에 액세스**

     - 조직에서 Windows Server Active Directory 온-프레미스를 사용 하는 경우에는 Microsoft 365 Business를 설정 하 여 Windows 10 장치를 보호 하 되, 로컬 인증을 필요로 하는 온-프레미스 리소스에 대 한 액세스를 계속 유지할 수 있습니다. 이를 설정 하려면 [도메인에 가입 된 Windows 10 장치를 Microsoft 365 Business에서 관리할 수 있도록 설정](manage-windows-devices.md) 의 단계를 수행 합니다. 이 상태에서 기본 설정 방법 및 장치를 하이브리드 Azure AD 가입 장치 라고 합니다.

    - 회사에 일부 온-프레미스 리소스 (예: 파일 공유 및 프린터)가 포함 된 로컬 Active Directory가 있는 경우 여기에 나와 있는 단계에 따라 Azure AD 조인 장치에 이러한 리소스에 대 한 액세스 권한을 부여할 수 있습니다. [ Azure AD-가입 된 장치 (Microsoft 365 Business)](access-resources.md)입니다.

  