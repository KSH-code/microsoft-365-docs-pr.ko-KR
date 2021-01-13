---
title: 관리 포털 액세스
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
description: 관리 포털에 대한 액세스 제어를 포함하여 관리 포털을 찾아 사용하는 방법
ms.service: m365-md
ms.author: jaimeo
author: jaimeo
ms.topic: article
audience: ITPro
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.openlocfilehash: 09427d163b8b5e47911b6df26e5acf0fcd1f3524
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841354"
---
# <a name="access-the-admin-portal"></a>관리 포털 액세스

Microsoft Managed Desktop 서비스에 대한 게이트웨이는 Microsoft [Azure Portal입니다.](https://portal.azure.com) 일반적으로 Azure Portal 환경을 사용하고 사용자 지정하는 데 대한 자세한 내용은 [Azure Portal 설명서를 참조하세요.](https://docs.microsoft.com/azure/azure-portal/) 지금 미리 보기에서 사용할 수 있습니다. Microsoft [Endpoint Manager에서 Microsoft](https://endpoint.microsoft.com/)Managed Desktop을 찾을 수 있습니다. 장치 관리를 위해 이 포털의 기능을 익숙하지 않은 경우 [Microsoft Endpoint Manager](https://docs.microsoft.com/mem/)설명서를 참조하십시오.

> [!NOTE]
> 그러나 Microsoft [Endpoint Manager](https://endpoint.microsoft.com/) 또는 [Azure Portal에서](https://portal.azure.com)Microsoft Managed Desktop에 액세스하기로 선택한 경우 다음 브라우저가 지원됩니다.
> - Microsoft Edge(최신 버전)
> - Microsoft Internet Explorer 11
> - Safari(최신 버전, Mac에만 해당)
> - Chrome(최신 버전)
> - Firefox(최신 버전)

관리 계정에 Azure Portal 또는 Microsoft Endpoint Manager에서 Microsoft Managed Desktop 관리 기능에 액세스하려면 특정 권한이 필요합니다. RBAC(역할 기반 액세스 제어)를 사용하여 조직 내에서 이러한 기능에 대한 관리자 액세스를 관리할 수 있습니다. 여러 Azure AD(Azure Active Directory) 관리자 역할 및 기본 제공 사용자 지정 역할을 사용하여 Microsoft Managed Desktop Admin 포털 내의 여러 기능에 대해 보다 세부적으로 제어할 수 있습니다. Azure Active Directory 역할에 대한 자세한 내용은 Azure Active Directory의 관리자 역할 [권한을 참조하세요.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) 다양한 Microsoft 제품 및 서비스에 적용되는 Azure AD 관리자 역할과 달리 사용자 지정 역할은 Microsoft Managed Desktop과 관련이 있으며 이 서비스의 관리자 기능에 대한 액세스만 보장합니다. 관리자는 사용자에게 개별적으로 또는 Azure AD 관리자 역할과 함께 사용자 지정 역할을 할당하여 기존 관리자 계정에 Microsoft Managed Desktop 권한을 추가할 수 있습니다.

아래 각 역할을 할당하여 서로 다른 수준의 액세스를 제공할 수 있습니다.

|Azure AD 역할  |Microsoft Managed Desktop 권한  |
|---------|---------|
|전역 관리자     | 이 역할이 있는  관리자는 Microsoft Managed Desktop Admin 포털의 모든 기능에 대한 읽기 및 쓰기 권한이 있습니다.         |
|전역 읽기 권한자     | 이 역할이 있는  관리자는 Microsoft Managed Desktop Admin 포털의 모든 기능에 대한 읽기 전용 권한을 하게 됩니다.         |
|Intune 서비스 관리자     |  이 역할이 있는  관리자는 Microsoft Managed Desktop Admin 포털의 보안과 관련이 없는 기능에 대한 읽기 및 쓰기 권한이 있습니다.       |
|서비스 지원 관리자     | 이 역할이 있는  관리자는 Microsoft Managed Desktop Admin 포털에서 지원 요청을 관리하기 위한 보안 및 쓰기 권한과 관련이 없는 기능에 대한 읽기 전용 사용 권한을 하게 됩니다.          |
|보안 관리자 | 이 역할이 있는  관리자는 관리 포털에서 Microsoft  Managed Desktop의 보안 관련 기능에 대한 읽기 전용 권한을 가지며 모든 기능에 대한 쓰기 권한이 있습니다. |
|보안 읽기 권한자 |이 역할이 있는  관리자는 Microsoft Managed Desktop Admin 포털의 모든 기능에 대한 읽기 전용 권한을 하게 됩니다.|

> [!IMPORTANT]
> 전역 관리자 역할만 Microsoft Managed  Desktop에서 조직을 등록하는 데 필요한 권한이 있습니다. Azure Active Directory 역할은 다양한 Microsoft 서비스에서 사용자 계정에 권한을 부여합니다. Microsoft Managed Desktop 등록을 완료한 후 다른 작업을  수행하는 데 필요한 최소 권한으로 항상 역할을 사용해야 합니다.

 
|사용자 지정 역할  |Microsoft Managed Desktop 사용 권한  |
|---------|---------|
|Microsoft Managed Desktop Service 관리자  | 사용자에게 할당된 경우 이 역할은  Microsoft Managed Desktop Admin 포털의 보안과 관련이 없는 기능에 대한 읽기 및 쓰기 권한을 관리자에게 부여합니다.  |
|Microsoft Managed Desktop Service Reader | 사용자에게 할당된 경우 이 역할은  Microsoft Managed Desktop Admin 포털의 보안과 관련이 없는 기능에 대한 읽기 전용 권한을 관리자에게 부여합니다. |
|Microsoft Managed Desktop Security Manager |사용자에게 할당된 경우 이 역할은  해당 관리자에게 Microsoft Managed Desktop Admin 포털의 보안 관련 기능에 대한 읽기 및 쓰기 권한만 부여합니다.   |

> [!NOTE]
> 보안 기능에는 보안 관련 통신, 보안 연락처 관리, 보안 관련 지원 요청 관리, 보안 관련 보고서 액세스가 포함됩니다. 

## <a name="assigning-roles-to-administrators"></a>관리자에게 역할 할당

Azure Active Directory 역할 할당에 대한 도움이 필요한 경우 Azure Active Directory에서 관리자 역할 [권한을 참조하세요.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)

기본 제공 역할을 쉽게 관리하기 위해 각 사용자 지정 역할에 대한 보안 그룹(예: "최신 작업 공간 역할 - 보안 관리자")이 있습니다. 사용자를 보안 그룹 중 하나에 할당하기 위해 다음 단계를 수행합니다.
1.  Microsoft Endpoint Manager 포털로 이동합니다.
2.  **왼쪽에서** 그룹을 선택합니다.
3.  최신 작업 **공간** 역할을 검색한 다음 할당할 역할과 연결된 그룹을 선택합니다. 
4.  **왼쪽에서** 구성원을 선택한 다음 **명령** 표시줄에서 + 구성원 추가를 선택합니다.
5.  추가할 사람의 전자 메일을 입력합니다. 게스트인 경우 그룹을 할당하려면 먼저 게스트를 초대해야 합니다.
6.  **아래쪽에서** 선택을 선택합니다.

> [!NOTE]
> 역할 할당을 위한 중첩 보안 그룹은 현재 지원되지 않습니다. 
