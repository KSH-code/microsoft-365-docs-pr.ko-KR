---
title: 기본 사용 권한을 사용하여 액세스 Microsoft Defender 보안 센터
description: 기본 권한을 사용하여 끝점 포털용 Microsoft Defender에 액세스하는 방법을 배워야 합니다.
keywords: 사용자 역할 할당, 읽기 및 쓰기 액세스 할당, 읽기 전용 액세스 할당, 사용자, 사용자 역할, 역할
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
ms.openlocfilehash: 05e9eadb9047fd4a2c8a4d01ecefc3ec2f73f9db
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60207992"
---
# <a name="use-basic-permissions-to-access-the-portal"></a>기본 권한을 사용하여 포털에 액세스

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- Azure Active Directory
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-basicaccess-abovefoldlink)

기본 사용 권한 관리를 사용하려면 아래 지침을 참조하세요.

다음 솔루션 중 하나를 사용할 수 있습니다.

- Azure PowerShell
- Azure Portal

사용 권한에 대한 세부적인 제어를 위해 역할 기반 액세스 [제어로 전환합니다.](rbac.md)

## <a name="assign-user-access-using-azure-powershell"></a>사용자를 사용하여 사용자 액세스 Azure PowerShell

다음 권한 수준 중 하나를 사용하여 사용자를 할당할 수 있습니다.

- 모든 액세스(읽기 및 쓰기)
- 읽기 전용 액세스

### <a name="before-you-begin"></a>시작하기 전에

- 설치 Azure PowerShell. 자세한 내용은 를 설치 및 구성하는 [방법을 Azure PowerShell.](https://azure.microsoft.com/documentation/articles/powershell-install-configure/)

  > [!NOTE]
  > PowerShell cmdlet은 상승된 명령줄에서 실행해야 합니다.

- 커넥트 Azure Active Directory. 자세한 내용은 [커넥트-MsolService를 참조하십시오.](/powershell/module/msonline/connect-msolservice)

  - **모든 액세스:** 모든 권한이 있는 사용자는 로그인하고, 모든 시스템 정보를 보고, 경고를 해결하고, 심층 분석을 위해 파일을 제출하고, 온보더링 패키지를 다운로드할 수 있습니다. 모든 액세스 권한을 할당하려면 사용자를 "보안 관리자" 또는 "전역 관리자" AAD 기본 제공 역할에 추가해야 합니다.
  - **읽기 전용 액세스:** 읽기 전용 액세스 권한이 있는 사용자는 로그인하고 모든 경고 및 관련 정보를 볼 수 있습니다.

    경고 상태를 변경하거나, 심층 분석을 위해 파일을 제출하거나, 상태 변경 작업을 수행할 수 없습니다.

    읽기 전용 액세스 권한을 할당하려면 사용자를 "보안 읽기 권한자" Azure AD 기본 제공 역할에 추가해야 합니다.

다음 단계에 따라 보안 역할을 할당합니다.

- 읽기 **및 쓰기 액세스의** 경우 다음 명령을 사용하여 사용자를 보안 관리자 역할에 할당합니다.

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Administrator" -RoleMemberEmailAddress "secadmin@Contoso.onmicrosoft.com"
  ```

- 읽기 **전용 액세스의** 경우 다음 명령을 사용하여 사용자를 보안 읽기 프로그램 역할에 할당합니다.

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Reader" -RoleMemberEmailAddress "reader@Contoso.onmicrosoft.com"
  ```

자세한 내용은 를 사용하여 그룹 구성원 추가 [또는 제거를 Azure Active Directory.](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

## <a name="assign-user-access-using-the-azure-portal"></a>Azure Portal을 사용하여 사용자 액세스 할당

자세한 내용은 [을(를)](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)사용할 수 있는 사용자에게 관리자 및 비 관리자 역할 할당을 Azure Active Directory.

## <a name="related-topic"></a>관련 항목

- [RBAC를 사용하여 포털 액세스 관리](rbac.md)
