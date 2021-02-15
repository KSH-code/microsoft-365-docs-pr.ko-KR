---
title: 사용자 및 장치 액세스 보호
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 4/17/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: Microsoft 365 데이터 및 서비스에 대한 사용자 및 장치 액세스를 보호하고 데이터 손실을 방지하는 방법을 학습합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 64baa2c9e49a9b24841ec50db3e5592ba3d7d55d
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/09/2020
ms.locfileid: "48399027"
---
# <a name="protect-user-and-device-access"></a>사용자 및 장치 액세스 보호

Microsoft 365 데이터 및 서비스에 대한 액세스를 보호하는 것은 사이버 공격으로부터 보호하고 데이터 손실을 방지하는 데 중요합니다. 환경의 다른 SaaS 응용 프로그램과 Azure Active Directory 응용 프로그램 프록시를 사용하여 게시된 On-Premises 응용 프로그램에도 동일한 보호를 적용할 수 있습니다.
  
## <a name="step-1-review-recommendations"></a>1단계: 권장 사항 검토

Azure AD 애플리케이션 프록시를 사용하여 게시한 온-프레미스 응용 프로그램, Office 365 및 다른 SaaS 서비스에 액세스하는 ID 및 디바이스를 보호하기 위해 권장되는 기능입니다.
  
[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [더 많은 언어](https://www.microsoft.com/download/details.aspx?id=55032)
  
## <a name="step-2-protect-administrator-accounts-and-access"></a>2단계: 관리자 계정 및 액세스 보호
Microsoft 365 환경을 관리하는 데 사용하는 관리 계정에는 상승된 권한이 포함됩니다. 이는 해커와 사이버 공격자에 대한 중요한 대상입니다. 

먼저 관리자 계정에만 관리합니다. 관리자는 관리되지 않는 일반 사용에 대해 별도의 사용자 계정을 사용할 수 있으며, 필요한 경우 해당 관리 계정만 사용하여 해당 작업 기능과 관련된 작업을 완료해야 합니다.

다단계 인증 및 조건부 액세스를 통해 관리자 계정을 보호합니다. 자세한 내용은 관리자 계정 [보호를 참조하십시오.](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-prerequisites#protecting-administrator-accounts) 

다음으로, Office 365에서 권한이 부여된 액세스 관리를 구성합니다. 권한이 부여된 액세스 관리를 사용하면 Office 365의 권한 있는 관리 작업을 세부적인 액세스 제어가 허용됩니다. 중요한 데이터에 대한 액세스 또는 중요한 구성 설정에 대한 액세스 권한이 있는 기존 권한 있는 관리자 계정을 사용할 수 있는 위반으로부터 조직을 보호하는 데 도움이 될 수 있습니다.

- [권한 있는 액세스 관리 개요](privileged-access-management-overview.md)
- [권한이 부여된 액세스 관리 구성](privileged-access-management-configuration.md)

또 다른 권장하는 또 다른 권장은 관리 작업을 위해 특별히 구성된 workstations를 사용하는 것입니다. 관리 작업에만 사용되는 전용 장치입니다. 권한이 [부여된 액세스 보안 참조.](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access)

마지막으로 테넌트에 둘 이상의 긴급 액세스 계정을 만들어 관리 액세스 권한이 부재 중일 경우의 영향을 완화할 수 있습니다. [Azure AD에서 긴급 액세스 계정 관리 참조.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access) 

## <a name="step-3-configure-recommended-identity-and-device-access-policies"></a>3단계: 권장되는 ID 및 장치 액세스 정책 구성
MFA(다단계 인증) 및 조건부 액세스 정책은 손상된 계정 및 무단 액세스를 완화하는 강력한 도구입니다. 함께 테스트된 정책 집합을 구현하는 것이 좋습니다. 배포 단계를 비롯한 자세한 내용은 ID 및 장치 [액세스 구성을 참조하세요.](../security/office-365-security/microsoft-365-policies-configurations.md)

 이러한 정책은 다음과 같은 기능을 구현합니다.
- Mult-factor authentication
- 조건부 액세스
- Intune 앱 보호(디바이스의 앱 및 데이터 보호)
- Intune 장치 규정 준수 상태
- Azure AD ID 보호

Intune 장치 준수를 구현하려면 장치 등록이 필요합니다. 장치를 관리하면 해당 장치가 환경의 리소스에 액세스할 수 있도록 허용하기 전에 정상 및 규정 준수를 보장할 수 있습니다. [Intune에서 관리를 위해](https://docs.microsoft.com/intune-classic/deploy-use/enroll-devices-in-microsoft-intune) 장치 등록 참조

## <a name="step-4-configure-sharepoint-device-access-policies"></a>4단계: SharePoint 장치 액세스 정책 구성

장치 액세스 제어를 사용하여 중요하고 높은 규제 대상 콘텐츠를 사용하여 SharePoint 사이트의 콘텐츠를 보호하는 것이 좋습니다. 자세한 내용은 SharePoint 사이트 및 파일 보안에 대한 정책 [권장 사항을 참조하세요.](../security/office-365-security/sharepoint-file-access-policies.md)



    

