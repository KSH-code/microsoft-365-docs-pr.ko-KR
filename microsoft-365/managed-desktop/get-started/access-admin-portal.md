---
title: 관리 포털 액세스
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
ms.author: jaimeo
author: jaimeo
ms.topic: article
audience: ITPro
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.openlocfilehash: f57911276d74c6945027077404e1f83c2f5072fd
ms.sourcegitcommit: eb905c5b4d7e71fc930a207357295b0160c4f065
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/19/2020
ms.locfileid: "48137038"
---
# <a name="access-the-admin-portal"></a>관리 포털 액세스

Microsoft Managed Desktop service에 대 한 게이트웨이는 Microsoft [Azure portal](https://portal.azure.com)입니다. Azure portal 환경을 사용 하 고 사용자 지정 하는 방법에 대 한 자세한 내용은 [azure portal 설명서](https://docs.microsoft.com/azure/azure-portal/)를 참조 하세요. 지금 미리 보기에서 사용할 수 있음 [Microsoft Endpoint Manager](https://endpoint.microsoft.com/)에서 Microsoft Managed Desktop도 찾을 수 있습니다. 장치 관리에 대 한이 포털의 기능에 익숙하지 않은 경우 [Microsoft Endpoint Manager 설명서](https://docs.microsoft.com/mem/)를 참조 하세요.

> [!NOTE]
> 그러나 [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) 또는 [Azure portal](https://portal.azure.com)에서 Accesss Microsoft Managed Desktop을 선택 하면 다음과 같은 브라우저가 지원 됩니다.
> - Microsoft Edge (최신 버전)
> - Microsoft Internet Explorer 11
> - Safari (최신 버전, Mac에만 해당)
> - Chrome (최신 버전)
> - Firefox (최신 버전)

Azure portal 또는 Microsoft Endpoint Manager에서 Microsoft Managed Desktop 관리 기능에 액세스 하려면 관리 계정에 특정 권한이 필요 합니다. RBAC (역할 기반 액세스 제어)를 사용 하 여 조직 내에서 이러한 기능에 대 한 관리자 액세스를 관리할 수 있습니다. 여러 Azure Active Directory (Azure AD) 관리자 역할 및 기본 제공 사용자 지정 역할을 사용 하 여 Microsoft Managed Desktop Admin 포털 내의 다양 한 기능을 보다 세부적으로 제어할 수 있습니다. Azure Active Directory 역할에 대 한 자세한 내용은 [Azure Active directory에서 관리자 역할 권한을](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)참조 하세요. 다양 한 Microsoft 제품 및 서비스에 적용 되는 Azure AD 관리자 역할과 달리, 사용자 지정 역할은 Microsoft Managed Desktop에 한정 되며이 서비스에 대 한 관리 기능에만 액세스할 수 있습니다. 관리자는 사용자에 게 사용자 지정 역할을 개별적으로 또는 Azure AD 관리자 역할과 함께 할당 하 여 기존 관리자 계정에 Microsoft Managed Desktop 사용 권한을 추가할 수 있습니다.

아래에 나와 있는 각 역할을 할당 하 여 다양 한 수준의 액세스를 제공할 수 있습니다.

|Azure AD 역할  |Microsoft Managed Desktop 사용 권한  |
|---------|---------|
|전역 관리자     | 이 역할을 가진 관리자에 게는 Microsoft Managed Desktop Admin 포털의 모든 기능에 대 한 **읽기 및 쓰기 권한이** 있습니다.         |
|전역 읽기 권한자     | 이 역할을 가진 관리자에 게는 Microsoft Managed Desktop Admin 포털의 모든 기능에 대 한 **읽기 전용 권한이** 부여 됩니다.         |
|Intune 서비스 관리자     |  이 역할을 가진 관리자에 게는 Microsoft Managed Desktop Admin 포털의 모든 기능에 대 한 **읽기 및 쓰기 권한이** 있습니다. **변경 내용:** 이 역할을 가진 관리자가 2020 년 9 월부터 Microsoft Managed Desktop 보안 기능에 액세스할 수 없습니다.       |
|서비스 지원 관리자     | 이 역할을 가진 관리자에 게는 Microsoft Managed Desktop Admin 포털의 모든 기능에 대 한 **읽기 및 쓰기 권한이** 있습니다. **변경 내용:** 이 역할을 가진 관리자가 2020 년 9 월부터 Microsoft Managed Desktop 보안 기능에 액세스할 수 없습니다.         |
|보안 관리자 | **(Preview 년 9 월 2020 일)** 이 역할을 가진 관리자는 관리 포털의 Microsoft Managed Desktop에 있는 보안 관련 기능에 대 한 모든 기능 및 쓰기 권한에 대 한 읽기 전용 권한을 갖게 됩니다. |
|보안 읽기 권한자 | **(Preview 년 9 월 2020 일)**  이 역할을 가진 관리자에 게는 Microsoft Managed Desktop Admin 포털의 모든 기능에 대 한 읽기 전용 권한이 부여 됩니다.|

> [!IMPORTANT]
> 전역 관리자 역할에만 Microsoft Managed Desktop에서 조직을 *등록* 하는 데 필요한 사용 권한이 있습니다. Azure Active Directory 역할은 다양 한 Microsoft 서비스에서 사용자 계정 권한을 제공 합니다. Microsoft Managed Desktop을 사용한 등록을 완료 한 후에는 항상 다른 작업을 수행 하는 데 필요한 *최소* 권한으로 역할을 사용 해야 합니다.

 
|사용자 지정 역할  |Microsoft Managed Desktop 사용 권한  |
|---------|---------|
|Microsoft Managed Desktop Service 관리자  | **(Preview 년 9 월 2020 일)** 사용자에 게 할당 되 면이 역할은 Microsoft Managed Desktop Admin 포털의 **보안과 관련이 없는 기능에 대 한 쓰기 권한을** 관리자에 게 부여 & 합니다.  |
|Microsoft Managed Desktop 서비스 읽기 권한자 | **(Preview 년 9 월 2020 일)** 사용자에 게 할당 되 면이 역할은 Microsoft Managed Desktop Admin 포털의 **보안과 관련이 없는 기능에 대 한 읽기 전용 권한을** 관리자에 게 부여 합니다. |
|Microsoft Managed Desktop Security Manager | **(Preview 년 9 월 2020 일)** 사용자에 게 할당 되 면이 역할은 관리자에 게 Microsoft Managed Desktop Admin 포털의 **보안 관련 기능에 대 한 읽기 권한만 & 쓰기 권한을** 부여 합니다.   |

> [!NOTE]
> 보안 기능에는 보안 관련 통신, 보안 연락처 관리, 보안 관련 지원 요청 관리, 보안 관련 보고서에 대 한 액세스 등이 포함 됩니다. 

## <a name="assigning-roles-to-administrators"></a>관리자에 게 역할 할당

Azure Active Directory 역할을 할당 하는 데 도움이 필요한 경우 [Azure Active directory에서 관리자 역할 권한을](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)참조 하세요.

기본 제공 역할을 쉽게 관리 하기 위해 각 사용자 지정 역할에 대 한 보안 그룹 (예: "현대 직장 역할-보안 관리자")을 만들었습니다. 사용자를 보안 그룹 중 하나에 할당 하려면 다음 단계를 수행 합니다.
1.  Azure portal로 이동 하 여 Azure Active Directory 블레이드에서 이동 합니다.
2.  왼쪽에서 그룹을 선택 합니다.
3.  최신 작업 공간 역할을 검색 한 다음 할당 하려는 역할과 연결 된 그룹을 선택 합니다. 
4.  왼쪽에서 구성원을 선택 하 고 명령 모음에서 + 구성원 추가를 선택 합니다.
5.  추가할 사용자의 전자 메일을 입력 합니다. 외부 사용자의 경우에는 그룹을 할당 하기 전에 초대 해야 합니다.
6.  아래쪽에서 선택을 선택 합니다.

> [!NOTE]
> 역할 할당에 대 한 보안 그룹 중첩은 현재 지원 되지 않습니다. 
