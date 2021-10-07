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
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: 데이터 및 서비스에 대한 사용자 및 장치 Microsoft 365 보호하고 데이터 손실을 방지하는 방법을 학습합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6f7d3c8af6526e5766086c7db5f6a7285f215162
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60172254"
---
# <a name="protect-user-and-device-access"></a>사용자 및 장치 액세스 보호

데이터 및 서비스에 Microsoft 365 보호하는 것은 사이버 공격으로부터 보호하고 데이터 손실을 방지하는 데 중요합니다. 환경의 다른 SaaS 응용 프로그램과 응용 프로그램 프록시를 사용하여 게시된 사내 응용 프로그램에도 동일한 보호를 적용할 Azure Active Directory 있습니다.
  
## <a name="step-1-review-recommendations"></a>1단계: 권장 사항 검토

Azure AD 애플리케이션 프록시를 사용하여 게시한 온-프레미스 응용 프로그램, Office 365 및 다른 SaaS 서비스에 액세스하는 ID 및 디바이스를 보호하기 위해 권장되는 기능입니다.
  
[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [더 많은 언어](https://www.microsoft.com/download/details.aspx?id=55032)
  
## <a name="step-2-protect-administrator-accounts-and-access"></a>2단계: 관리자 계정 및 액세스 보호
사용자 환경 관리에 사용하는 관리 계정에는 Microsoft 365 권한이 포함됩니다. 이는 해커와 사이버 공격자에 대한 중요한 대상입니다. 

먼저 관리자 계정에만 관리합니다. 관리자는 관리가 아닌 일반 사용에 대해 별도의 사용자 계정이 필요하며, 필요한 경우 해당 작업 기능과 관련된 작업을 완료하는 데만 관리 계정을 사용해야 합니다.

다단계 인증 및 조건부 액세스를 통해 관리자 계정을 보호합니다. 자세한 내용은 관리자 계정 [보호를 참조하세요.](../security/office-365-security/identity-access-prerequisites.md#protecting-administrator-accounts) 

다음으로, 2016에서 권한 있는 액세스 관리를 Office 365. 권한 있는 액세스 관리를 사용하면 Office 365에서 권한 있는 관리자가 실행할 수 있는 작업에 대해 세부적인 액세스 제어를 할 수 있습니다. 중요한 데이터에 대한 액세스 또는 중요한 구성 설정에 대한 액세스 권한이 있는 기존 권한 있는 관리자 계정을 사용할 수 있는 침해로부터 조직을 보호하는 데 도움이 될 수 있습니다.

- [권한 있는 액세스 관리 개요](privileged-access-management-overview.md)
- [권한이 부여된 액세스 관리 구성](privileged-access-management-configuration.md)

또 다른 권장할 점은 관리 작업을 위해 특별히 구성된 Workstation을 사용하는 것입니다. 관리 작업에만 사용되는 전용 장치입니다. 권한이 [부여된 액세스 보안 을 참조합니다.](/windows-server/identity/securing-privileged-access/securing-privileged-access)

마지막으로 테넌트에 긴급 액세스 계정을 두 개 이상 만들어 관리 액세스 권한이 없는 경우의 영향을 완화할 수 있습니다. [Azure AD에서 긴급 액세스 계정 관리를 참조하세요.](/azure/active-directory/users-groups-roles/directory-emergency-access) 

## <a name="step-3-configure-recommended-identity-and-device-access-policies"></a>3단계: 권장 ID 및 장치 액세스 정책 구성
MFA(다단계 인증) 및 조건부 액세스 정책은 손상된 계정 및 무단 액세스를 완화하는 강력한 도구입니다. 함께 테스트된 정책 집합을 구현하는 것이 좋습니다. 배포 단계를 비롯한 자세한 내용은 ID 및 장치 액세스 [구성을 참조하세요.](../security/office-365-security/microsoft-365-policies-configurations.md)

 이러한 정책은 다음 기능을 구현합니다.
- Mult-factor authentication
- 조건부 액세스
- Intune 앱 보호(디바이스의 앱 및 데이터 보호)
- Intune 장치 규정 준수 상태
- Azure AD ID 보호

Intune 장치 준수를 구현하려면 장치 등록이 필요합니다. 장치를 관리하면 해당 장치가 환경의 리소스에 액세스할 수 있도록 허용하기 전에 정상 및 규정 준수를 보장할 수 있습니다. [Intune에서 관리를 위해](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune) 장치 등록을 참조

## <a name="step-4-configure-sharepoint-device-access-policies"></a>4단계: SharePoint 액세스 정책 구성

장치 액세스 제어를 사용하여 SharePoint 높은 규제 대상 콘텐츠를 사용하여 사이트 내 콘텐츠를 보호하는 것이 좋습니다. 자세한 내용은 사이트 및 파일 보호를 [위한 SharePoint 권장 사항을 참조하세요.](../security/office-365-security/sharepoint-file-access-policies.md)



