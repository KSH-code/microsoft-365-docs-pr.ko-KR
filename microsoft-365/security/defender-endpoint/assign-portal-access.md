---
title: 사용자 액세스 권한을 Microsoft Defender 보안 센터
description: 끝점용 Microsoft Defender 포털에 대한 읽기 및 쓰기 또는 읽기 전용 권한을 할당합니다.
keywords: 사용자 역할 할당, 읽기 및 쓰기 액세스 할당, 읽기 전용 액세스 할당, 사용자, 사용자 역할, 역할
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.date: 11/28/2018
ms.technology: mde
ms.openlocfilehash: 7ea8fd8a87e15291f0f65e6f21bb452efe72383c
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60207106"
---
# <a name="assign-user-access-to-microsoft-defender-security-center"></a>사용자 액세스 권한을 Microsoft Defender 보안 센터

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**
- Azure Active Directory
- Office 365
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

Endpoint용 Defender는 사용 권한을 관리하는 두 가지 방법을 지원합니다.

- **기본 사용 권한 관리:** 모든 권한 또는 읽기 전용으로 사용 권한을 설정합니다.
- **RBAC(역할** 기반 액세스 제어) : 역할을 정의하고, 역할에 Azure AD 사용자 그룹을 할당하고, 사용자 그룹에 장치 그룹에 대한 액세스 권한을 부여하여 세분화된 사용 권한을 설정할 수 있습니다. RBAC에 대한 자세한 내용은 역할 기반 액세스 제어를 사용하여 포털 [액세스 관리를 참조하세요.](rbac.md)

> [!NOTE]
> 기본 권한을 이미 할당한 경우 언제든지 RBAC로 전환할 수 있습니다. 전환하기 전에 다음을 고려하십시오.
>
> - 모든 권한이 있는 사용자(Azure AD에서 전역 관리자 또는 보안 관리자 디렉터리 역할이 할당된 사용자)에는 자동으로 끝점 관리자 역할에 대한 기본 Defender가 할당되며, 이 사용자에게는 모든 액세스 권한도 부여됩니다. RBAC로 전환한 후 추가 Azure AD 사용자 그룹을 끝점용 Defender 관리자 역할에 할당할 수 있습니다. Endpoint 관리자 역할에 대한 Defender 관리자 역할에 할당된 사용자만 RBAC를 사용하여 사용 권한을 관리할 수 있습니다. 
> - 읽기 전용 액세스 권한이 있는 사용자(보안 읽기 권한이 있는 사용자)는 역할이 할당될 때까지 포털에 액세스할 수 없습니다. Azure AD 사용자 그룹만 RBAC에서 역할을 할당할 수 있습니다.
> - RBAC로 전환한 후 기본 사용 권한 관리를 사용하여 다시 전환할 수 없습니다.

## <a name="related-topics"></a>관련 항목

- [기본 권한을 사용하여 포털에 액세스](basic-permissions.md)
- [RBAC를 사용하여 포털 액세스 관리](rbac.md)
