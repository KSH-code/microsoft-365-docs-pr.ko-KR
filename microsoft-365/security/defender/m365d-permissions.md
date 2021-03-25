---
title: Microsoft 365 보안 센터에서 Microsoft 365 Defender 데이터에 대한 액세스 관리
description: Microsoft 365 Defender에서 데이터에 대한 사용 권한을 관리하는 방법 학습
keywords: 액세스, 사용 권한, MTP, Microsoft 위협 방지, M365, 보안, MCAS, MDATP, 클라우드 앱 보안, Microsoft Defender Advanced Threat Protection, 범위, 범위 지정, RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: e1be2cf4d5510b2a31a61f848d7d99d6a6704d49
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076652"
---
# <a name="manage-access-to-microsoft-365-defender-with-azure-active-directory-global-roles"></a>Azure Active Directory 전역 역할을 사용하여 Microsoft 365 Defender에 대한 액세스 관리

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

Microsoft 365 Defender에 대한 액세스를 관리하는 두 가지 방법이 있습니다.
- **전역 Azure AD(Active Directory) 역할**
- **사용자 지정 역할 액세스**

다음 전역 **Azure AD(Active Directory)** 역할이 할당된 계정은 Microsoft 365 Defender 기능 및 데이터에 액세스할 수 있습니다.
- 전역 관리자
- 보안 관리자
- 보안 운영자
- 전역 읽기 권한자
- 보안 읽기 권한자

이 역할을 사용하여 계정을 검토하려면 [Microsoft 365 보안 센터에서 사용 권한을 확인합니다](https://security.microsoft.com/permissions).

**사용자 지정 역할** 액세스는 Microsoft 365 Defender의 새로운 기능으로, Microsoft Defender 365의 특정 데이터, 작업 및 기능에 대한 액세스를 관리할 수 있도록 합니다. 사용자 지정 역할은 전역 Azure AD 역할보다 더 많은 제어를 제공하여 필요한 최소 허용 역할만 사용자에게 제공합니다.  전역 Azure AD 역할 외에 사용자 지정 역할을 만들 수 있습니다. [사용자 지정 역할에 대해 자세히 알아보시고 을(를) 자세히 알아보아야 합니다.](custom-roles.md)

> ! [참고] 이 문서는 전역 Azure Active Directory 역할 관리에만 적용됩니다. 사용자 지정 역할 기반 액세스 제어 사용에 대한 자세한 내용은 역할 기반 액세스 제어에 대한 사용자 지정 [역할을 참조하세요.](custom-roles.md)

## <a name="access-to-functionality"></a>기능에 대한 액세스 권한
특정 기능에 대한 액세스 권한은 [Azure AD 역할](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)에 따라 결정됩니다. 사용자 또는 사용자 그룹에 새 역할을 할당해야 하는 특정 기능에 액세스해야 하는 경우 전역 관리자에게 문의하세요.

### <a name="approve-pending-automated-tasks"></a>보류 중인 자동 작업 승인
[자동화된 검사 및 조치](m365d-autoir-actions.md)는 전자 메일, 전달 규칙, 파일, 유지 메커니즘 및 조사 중에 찾은 기타 아티팩트에 대한 조치를 취할 수 있습니다. 명시적 승인이 필요한 보류 중인 작업을 승인하거나 거부하려면 Microsoft 365에서 할당된 특정 역할이 있어야 합니다. 자세한 내용은 [작업 센터 사용 권한](m365d-action-center.md#required-permissions-for-action-center-tasks)을 참조하세요.

## <a name="access-to-data"></a>데이터에 액세스
Microsoft 365 Defender 데이터에 대한 액세스는 끝점 RBAC(역할 기반 액세스 제어)에 대한 Microsoft Defender의 사용자 그룹에 할당된 범위를 사용하여 제어할 수 있습니다. 액세스 범위가 끝점용 Defender의 특정 장치 집합으로 지정되지 않은 경우 Microsoft 365 Defender의 데이터에 대한 모든 권한이 있습니다. 그러나 계정 범위가 지정되면 해당 범위에 속한 디바이스에 대한 데이터만 표시됩니다.

예를 들어 Microsoft Defender for Endpoint 역할이 있는 사용자 그룹 하나에만 속하고 해당 사용자 그룹에 판매 장치에 대한 액세스 권한이 부여된 경우 Microsoft 365 Defender에서 판매 장치에 대한 데이터만 볼 수 있습니다. [끝점용 Microsoft Defender의 RBAC 설정에 대한 자세한 정보](/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a>Microsoft Cloud App Security 액세스 제어
미리 보기 중에 Microsoft 365 Defender는 Cloud App Security 설정에 따라 액세스 제어를 적용하지 않습니다. Microsoft 365 Defender 데이터에 대한 액세스는 이러한 설정의 영향을 받지 않습니다.

## <a name="related-topics"></a>관련 항목
- [Microsoft 365 Defender에 대한 역할 기반 액세스 제어의 사용자 지정 역할](custom-roles.md)
- [Azure AD 역할](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [끝점 RBAC용 Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [Cloud App Security 역할](/cloud-app-security/manage-admins)