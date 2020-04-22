---
title: 설치 개요
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Microsoft 365 Business Premium, 구독에서 도메인 및 사용자 추가, 보안 정책 설정 등에 대 한 설정 단계를 알아봅니다.
ms.openlocfilehash: 8b26d423d4f62ee8f9ea4a61eb8f7efa72ee26cb
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633358"
---
# <a name="overview-of-setup"></a>설치 개요

Microsoft 365 Business Premium 설치에 대 한 간단한 비디오를 시청 하세요.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

이 비디오가 도움이 된 경우에는 [소규모 비즈니스 및 Microsoft 365를 처음 사용하는 사용자들을 위한 완전한 교육 시리즈](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)를 참조하세요.

대부분의 설치 단계는 설치 마법사에서 수행할 수 있지만 다른 옵션도 나열 됩니다.

## <a name="step-1-add-your-domain-and-users"></a>1 단계: 도메인 및 사용자 추가

   - **[도메인 추가](set-up.md#add-your-domain-to-personalize-sign-in)** ( [등록](sign-up.md)중에 도메인을 구매한 경우이 단계는 이미 완료 됨)

    - **사용자를 추가**합니다. 다음 세 가지 방법 중 하나를 통해 사용자를 추가할 수 있습니다.
        - [마법사](set-up.md#add-users-in-the-wizard)에서
        - 온-프레미스 Active directory가 있는 경우 디렉터리 동기화를 사용 하 여 [AZURE AD Connect를 사용 하 여 사용자를 추가](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) 합니다.
        - 나중에 관리 센터에서 [사용자를 추가할](add-users-m365b.md) 수도 있습니다.
## <a name="step-2-set-up-security-policies-and-configure-devices"></a>2 단계: 보안 정책 설정 및 장치 구성 

  - [설치 마법사](set-up.md#protect-your-organization) 를 사용 하 여 장치 정책을 구성 합니다. 
  - [관리 센터](view-policies-and-devices.md) 및 [Intune 포털](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal)에서 나중에 추가 하거나 편집할 수도 있습니다.
  - 또한 설정 마법사는 기본 위협 보호 및 데이터 손실 방지 설정을 설정 합니다.
  
  설치 마법사의 보안 설정 외에도 다음 설정을 추가 하 여 보안을 강화할 수 있습니다.

- **전자 메일 맬웨어 방지**
- **ATP 피싱 방지**
- **Exchange Online Archiving**
- **Azure Information Protection (Plan1**)

시작 하려면 [위협 방지 강화](increase-threat-protection.md) 및 [규정 준수 기능](set-up-compliance.md)을 참조 하세요.

모범 사례에 대 한 로드맵을 제공 하기 위해 [Microsoft 365 Business Premium을 보호 하는 상위 10 가지 방법](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) 에 대해서도 알아봅니다.

## <a name="step-3-set-up-and-manage-windows-10-devices"></a>3 단계: Windows 10 장치 설정 및 관리

설정 마법사를 실행 한 후에는 조직의 모든 Windwos 10 컴퓨터를 다시 사용할 수 있습니다.
  
- Windows 10 Pro는 Microsoft 365 Business Premium에 대 한 [필수 구성 요소](pre-requisites-for-data-protection.md) 지만, Windows 7 Pro, Windows 8 Pro 또는 Windows 8.1 pro가 있는 경우 구독을 통해 [windows 10 Pro로 업그레이드할](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update)수 통해.
- Windows 10 용 정책 정책을 설정 하는 windows 10 [pc 보안](secure-win-10-pcs.md) 의 단계를 수행 합니다.

Windows 10 장치를 Azure AD에 가입 하면 Windows 10 컴퓨터에 대해 설정한 정책이 적용 됩니다. 자세한 내용은 [Windows 장치 설정 Microsoft 365 사용자](set-up-windows-devices.md)를 참조 하세요.

## <a name="step-4-install-microsoft-365-apps-for-business"></a>4 단계: 비즈니스용 Microsoft 365 앱 설치
- [설치 마법사](set-up.md#deploy-office-365-client-apps)를 사용 하 여 Windows 장치에 Office를 자동으로 설치할 수 있습니다.
- 사용자가 Windows 및 장치용 [Office 앱을 설치할](https://docs.microsoft.com/office365/admin/setup/install-applications) 수 있도록 합니다.
     
## <a name="advanced"></a>고급
- **Autopilot을 사용 하 여 새 장치 설정**
            
     [Windows Autopilot](add-autopilot-devices-and-profile.md) 를 사용 하 여 사용자에 대해 **새** Windows 10 장치를 자동으로 미리 구성할 수 있지만,이 작업을 대신 수행할 수 있는 [파트너](https://www.microsoft.com/solution-providers/search) 를 가져오는 것이 더 쉬울 수 있습니다. [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598)로 이동한 후 클라우드 기술 전문가에 게 구매한 새 장치를 설치 하도록 요청할 수도 있습니다.

- **온-프레미스 리소스 액세스**

     - 조직에서 Windows Server Active Directory 온-프레미스를 사용 하는 경우에는 Microsoft 365 Business Premium을 설정 하 여 Windows 10 장치를 보호 하 고 로컬 인증을 필요로 하는 온-프레미스 리소스에 대 한 액세스를 계속 유지할 수 있습니다. 이를 설정 하려면 [도메인에 가입 된 Windows 10 장치를 Microsoft 365 Business Premium에서 관리할 수 있도록 설정](manage-windows-devices.md) 의 단계를 수행 합니다. 이는 기본 설정 방법 이며,이 상태에 있는 장치를 하이브리드 Azure AD 가입 장치 라고 합니다.

    - 회사에 일부 온-프레미스 리소스 (예: 파일 공유 및 프린터)가 포함 된 로컬 Active Directory가 있는 경우 Azure ad 가입 장치에서 [Microsoft 365 Business Premium의 AZURE ad 조인 장치 로부터 온-프레미스 리소스에 액세스](access-resources.md)하 여 이러한 리소스에 대 한 액세스 권한을 부여할 수 있습니다.

## <a name="see-also"></a>참고 항목

[Microsoft 365 for business 교육용 비디오](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
