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
description: 등록에서 도메인 및 사용자 추가, 보안 정책 설정 등 Microsoft 365 Business Premium의 설정 단계를 자세히 알아보십시오.
ms.openlocfilehash: 749acbfdbde92ad97b09dc720c85dd850b76c9cf
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579937"
---
# <a name="overview-of-setup"></a>설정 개요

Microsoft 365 Business Premium 설정에 대한 짧은 비디오를 시청합니다.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

이 비디오가 도움이 된 경우에는 [소규모 비즈니스와 Microsoft 365를 처음 사용하는 사용자를 위한 전체 교육 시리즈](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)를 참조하세요.

대부분의 설치 단계는 안내 설치에서 수행될 수 있지만 다른 옵션도 나열되어 있습니다.

## <a name="step-1-add-your-domain-and-users"></a>1단계: 도메인 및 사용자 추가

   - **[도메인을 추가합니다(등록하는](set-up.md#add-your-domain-to-personalize-sign-in)** 동안 도메인을 [구입한](sign-up.md)경우 이 단계는 이미 완료된 것입니다.)

   - **사용자를 추가합니다.** 다음 세 가지 방법으로 사용자를 추가할 수 있습니다.
        - 안내 [설치에서 을(를) 설치합니다.](set-up.md#add-users-in-the-wizard)
        - 디렉터리 동기화를 사용하여 [Azure AD Connect를](../enterprise/set-up-directory-synchronization.md) 사용하여 사용자를 추가합니다(프레미스 Active Directory가 있는 경우).
        - 나중에 관리 [센터에서 사용자를](../admin/add-users/add-users.md) 추가할 수도 있습니다.
## <a name="step-2-set-up-security-policies-and-configure-devices"></a>2단계: 보안 정책 설정 및 장치 구성 

  - 안내 [설치를 사용하여](set-up.md#protect-your-organization) 장치 정책을 구성합니다. 
  - 나중에 관리 센터 및 [Intune](/intune/tutorial-walkthrough-intune-portal)포털에서 추가하거나 편집할 수도 있습니다. [](view-policies-and-devices.md)
  - 또한 설치 마법사는 기본 위협 방지 및 데이터 손실 방지 설정도 설치합니다.
  
  설치 마법사의 보안 설정 외에도 다음 설정을 추가하여 보안을 강화할 수 있습니다.

- **전자 메일 맬웨어 보호**
- **Defender for Office 365의 피싱 방지**
- **Exchange Online Archiving**
- **Azure Information Protection(계획1)**

시작을 위해 위협 [](increase-threat-protection.md) 방지 강화 및 준수 [기능 설정 을 참조합니다.](set-up-compliance.md)

모범 보안 사례에 대한 로드맵을 확인하여 [Microsoft 365 Business Premium을](/office365/admin/security-and-compliance/secure-your-business-data) 보호하는 상위 10가지 방법도 참조합니다.

## <a name="step-3-set-up-and-manage-windows-10-devices"></a>3단계: Windows 10 장치 설정 및 관리

안내 설치를 완료한 후 조직의 모든 Windows 10 컴퓨터를 보호할 수 있습니다.
  
- Windows 10 Pro는 Microsoft 365 Business Premium의 선행 필요합니다. 그러나 Windows 7 Pro, Windows 8 Pro 또는 Windows 8.1 Pro가 있는 경우 구독을 통해 [Windows 10 Pro로](./upgrade-to-windows-pro-creators-update.md)업그레이드할 수 있습니다. [](pre-requisites-for-data-protection.md)
- 보안 Windows [10 PC의](secure-win-10-pcs.md) 단계에 따라 Windows 10 장치에 대한 정책을 설정할 수 있습니다.

Windows 10 장치를 Azure AD에 가입하면 Windows 10 컴퓨터에 대해 설정한 정책이 해당 장치에 적용됩니다. 자세한 내용은 Microsoft 365 사용자를 위한 Windows 장치 [설정 을 참조하세요.](set-up-windows-devices.md)

## <a name="step-4-install-microsoft-365-apps-for-business"></a>4단계: 비즈니스용 Microsoft 365 앱 설치
- 설치 마법사를 사용하여 Windows 장치에 Office를 자동으로 설치할 [수 있습니다.](set-up.md#deploy-office-365-client-apps)
- 사용자가 [Windows 및 디바이스용 Office](/office365/admin/setup/install-applications) 앱을 설치할 수 있도록 합니다.
     
## <a name="advanced"></a>고급
- **Autopilot을 사용하여 새 장치 설정**
            
     [Windows Autopilot을](add-autopilot-devices-and-profile.md) 사용하여 사용자를 위해 새 **Windows** 10 장치를 자동으로 미리 구성할 [](https://www.microsoft.com/solution-providers/search) 수 있지만 이 작업을 할 수 있는 파트너를 추가하는 것이 더 쉬워집니다. [Microsoft](https://go.microsoft.com/fwlink/?linkid=874598)Store로 이동하여 클라우드 기술 전문가에게 구매한 새 디바이스를 설정할 수 있습니다.

- **온-프레미스 리소스 액세스**

     - 조직에서 Windows Server Active Directory를 사용하는 경우 Microsoft 365 Business Premium을 설정하여 Windows 10 장치를 보호하는 동시에 로컬 인증이 필요한 사내 리소스에 대한 액세스는 유지 관리합니다. 도메인에 가입된 [Windows 10 장치를 Microsoft 365 Business Premium에서](manage-windows-devices.md) 관리하도록 설정의 단계에 따라 이 설정을 수행합니다. 이 방법이 기본 설정 방법으로, 이 상태의 장치를 하이브리드 Azure AD 가입 장치라고 합니다.

    - 비즈니스에 일부 사내 리소스(예: 파일 공유 및 프린터)가 포함된 로컬 Active Directory가 있는 경우 [Microsoft 365 Business Premium의 Azure AD](access-resources.md)가입 장치에서의 On-premises resources에 액세스의 단계에 따라 Azure AD 가입 장치에 이러한 리소스에 대한 액세스 권한을 부여할 수 있습니다.

## <a name="see-also"></a>참고 항목

[Microsoft 365 Business 교육 비디오](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)