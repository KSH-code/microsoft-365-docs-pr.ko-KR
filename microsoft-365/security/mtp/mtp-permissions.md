---
title: Microsoft 365 보안 센터에서 Microsoft 365 Defender 데이터에 대 한 액세스 관리
description: Microsoft 365 Defender에서 데이터에 대 한 사용 권한을 관리 하는 방법을 알아봅니다.
keywords: 액세스, 사용 권한, MTP, Microsoft 위협 방지, M365, 보안, MCAS, MDATP, 클라우드 앱 보안, Microsoft Defender Advanced Threat Protection, 범위, 범위 지정, RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 55b7b8c5755b773a4d53c95017a0a17a85495dee
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847251"
---
# <a name="manage-access-to-microsoft-365-defender"></a>Microsoft 365 Defender에 대 한 액세스 관리

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

다음 Azure AD (Active Directory) 역할이 할당 된 계정은 Microsoft 365 Defender 기능 및 데이터에 액세스할 수 있습니다.
- 전역 관리자
- 보안 관리자
- 보안 운영자
- 전역 읽기 권한자
- 보안 읽기 권한자

이 역할을 사용하여 계정을 검토하려면 [Microsoft 365 보안 센터에서 사용 권한을 확인합니다](https://security.microsoft.com/permissions).

## <a name="access-to-functionality"></a>기능에 대한 액세스 권한
특정 기능에 대한 액세스 권한은 [Azure AD 역할](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)에 따라 결정됩니다. 사용자 또는 사용자 그룹에 새 역할을 할당해야 하는 특정 기능에 액세스해야 하는 경우 전역 관리자에게 문의하세요.

### <a name="approve-pending-automated-tasks"></a>보류 중인 자동 작업 승인
[자동화된 검사 및 조치](mtp-autoir-actions.md)는 전자 메일, 전달 규칙, 파일, 유지 메커니즘 및 조사 중에 찾은 기타 아티팩트에 대한 조치를 취할 수 있습니다. 명시적 승인이 필요한 보류 중인 작업을 승인하거나 거부하려면 Microsoft 365에서 할당된 특정 역할이 있어야 합니다. 자세한 내용은 [작업 센터 사용 권한](mtp-action-center.md#required-permissions-for-action-center-tasks)을 참조하세요.

## <a name="access-to-data"></a>데이터에 액세스
Microsoft 365 Defender 데이터에 대 한 액세스는 Endpoint (역할 기반 액세스 제어)에 대 한 Microsoft Defender의 사용자 그룹에 할당 된 범위를 사용 하 여 제어할 수 있습니다. 액세스 권한이 Defender for Endpoint의 특정 장치 집합으로 범위가 지정 되지 않은 경우 Microsoft 365 Defender의 데이터에 대 한 모든 권한을 갖게 됩니다. 그러나 계정 범위가 지정되면 해당 범위에 속한 디바이스에 대한 데이터만 표시됩니다.

예를 들어 사용자 그룹에 게 Microsoft Defender for Endpoint 역할을 사용 하는 사용자 그룹이 있고, 해당 사용자나 영업 장치에 대 한 액세스 권한만 부여 된 경우 Microsoft 365 Defender의 판매 장치에 대 한 데이터만 표시 됩니다. [끝점에 대 한 Microsoft Defender의 RBAC 설정에 대 한 자세한 정보](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a>Microsoft Cloud App Security 액세스 제어
미리 보기 중에 Microsoft 365 Defender에서는 Cloud App Security 설정에 따라 액세스 제어를 적용 하지 않습니다. Microsoft 365 Defender 데이터에 대 한 액세스는 이러한 설정의 영향을 받지 않습니다.

## <a name="related-topics"></a>관련 항목

- [Azure AD 역할](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [Endpoint RBAC 용 Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [Cloud App Security 역할](https://docs.microsoft.com/cloud-app-security/manage-admins)
