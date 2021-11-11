---
title: 역할 기반 액세스 제어를 사용하여 포털에 대한 세분 Microsoft 365 Defender 부여
description: 보안 작업 내에서 역할 및 그룹을 만들어 포털에 대한 액세스 권한을 부여합니다.
keywords: rbac, 역할, 기반, 액세스, 제어, 그룹, 제어, 계층, aad
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 59b7f7f9aad9406fc5575f4ada5f45a68dd81b22
ms.sourcegitcommit: 8410a49995a084e4cc9b3f7286c8d506b7a85d79
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2021
ms.locfileid: "60914443"
---
# <a name="manage-portal-access-using-role-based-access-control"></a>역할 기반 액세스 제어를 사용하여 포털 액세스 관리

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- Azure Active Directory
- Office 365

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-rbac-abovefoldlink)

RBAC(역할 기반 액세스 제어)를 사용하면 보안 작업 팀 내에 역할 및 그룹을 만들어 포털에 대한 적절한 액세스 권한을 부여할 수 있습니다. 만드는 역할 및 그룹에 따라 포털에 액세스할 수 있는 사용자가 보고 할 수 있는 작업을 세분화하여 제어할 수 있습니다. 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bJ2a]

대규모 지역 분산 보안 운영 팀은 일반적으로 계층 기반 모델을 채택하여 보안 포털에 대한 액세스를 할당하고 권한을 부여합니다. 일반적인 계층에는 다음 세 가지 수준이 포함됩니다.

계층|설명|
:---|:---|
계층 1|**로컬 보안 운영 팀/IT 팀** <br> 이 팀은 일반적으로 지리적 위치 내에 포함된 경고를 조사하고 활성 수정이 필요한 경우 계층 2로 에스컬레이터합니다.|
계층 2|**지역 보안 운영 팀** <br> 이 팀은 해당 지역의 모든 장치를 보고 수정 작업을 수행할 수 있습니다.|
계층 3|**글로벌 보안 운영 팀** <br> 이 팀은 보안 전문가로 구성하며 포털에서 모든 작업을 보고 수행할 수 있는 권한이 있습니다.|

> [!NOTE]
> 계층 0 자산의 [](/azure/active-directory/privileged-identity-management/pim-configure) 경우 보안 Privileged Identity Management 사용하여 끝점 및 데이터 관리에 대한 Microsoft Defender를 보다 세부적으로 Microsoft 365 Defender.  

Endpoint RBAC용 Defender는 선택 계층 또는 역할 기반 모델을 지원하도록 설계되었습니다. 또한 역할이 볼 수 있는 역할, 액세스할 수 있는 장치 및 수행할 수 있는 작업에 대한 세부적인 제어를 제공합니다. RBAC 프레임워크는 다음 컨트롤을 중심으로 합니다.

- **특정 작업을 취할 수 있는 사용자 제어**
  - 사용자 지정 역할을 만들고 세분성으로 액세스할 수 있는 끝점용 Defender 기능을 제어합니다.
- **특정 장치 그룹 또는 그룹에 대한 정보를 볼 수 있는 사용자 제어**
  - [이름,](machine-groups.md) 태그, 도메인 등의 특정 기준에 따라 장치 그룹을 만든 다음 특정 Azure AD(Azure AD) 사용자 그룹을 사용하여 Azure Active Directory 권한을 부여합니다.

역할 기반 액세스를 구현하려면 관리자 역할을 정의하고, 해당 권한을 할당하고, 역할에 할당된 Azure AD 사용자 그룹을 할당해야 합니다.

### <a name="before-you-begin"></a>시작하기 전에

RBAC를 사용하려면 먼저 사용 권한을 부여할 수 있는 역할과 RBAC를 켜는 경우의 결과를 이해하는 것이 중요합니다.

> [!WARNING]
> 이 기능을 사용하도록 설정하기 전에 Azure AD에서 전역 관리자 역할 또는 보안 관리자 역할을 가지며, Azure AD 그룹이 포털에서 잠겨 있는 위험을 줄일 준비가 되어 있는 것이 중요합니다. 

Microsoft 365 Defender 포털에 처음 로그인하면 모든 권한이 부여되거나 읽기 전용 액세스 권한이 부여됩니다. 모든 액세스 권한은 Azure AD에서 보안 관리자 또는 전역 관리자 역할이 있는 사용자에게 부여됩니다. 읽기 전용 액세스 권한은 Azure AD에서 보안 읽기 권한자 역할이 있는 사용자에게 부여됩니다. 

Endpoint용 Defender 전역 관리자 역할이 있는 사용자는 장치 그룹 연결 및 Azure AD 사용자 그룹 할당에 관계없이 모든 장치에 무제한으로 액세스할 수 있습니다.

> [!WARNING]
> 처음에는 Azure AD 전역 관리자 또는 보안 관리자 권한이 있는 사용자만 Microsoft 365 Defender 포털에서 역할을 만들고 할당할 수 있으므로 Azure AD에서 올바른 그룹을 준비하는 것이 중요합니다.
>
> **역할 기반 액세스 제어를 설정하면 읽기 전용 권한이 있는 사용자(예: Azure AD 보안 읽기 권한자 역할에 할당된 사용자)가 역할에 할당될 때까지 액세스 권한을 잃게 됩니다.** 
>
>관리자 권한이 있는 사용자에게는 모든 권한이 있는 기본 기본 제공 Endpoint 전역 관리자 역할이 자동으로 할당됩니다. RBAC를 사용하기로 옵트인(opt in)한 후 Azure AD Global 또는 Security Administrators가 아닌 추가 사용자를 끝점 전역 관리자 역할에 대한 Defender에 할당할 수 있습니다. 
>
> RBAC를 사용하기로 옵트인(opt in)한 후 처음 포털에 로그인할 때처럼 초기 역할로 되전할 수 없습니다.

## <a name="related-topic"></a>관련 항목

- [RBAC 역할](../office-365-security/migrate-to-defender-for-office-365-onboard.md#rbac-roles)
- [끝점용 Microsoft Defender에서 장치 그룹 만들기 및 관리](machine-groups.md)
