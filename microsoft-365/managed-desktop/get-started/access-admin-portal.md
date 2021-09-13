---
title: 관리 포털 액세스
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
description: 관리 포털을 찾아서 사용하는 방법(액세스 제어 포함)
ms.service: m365-md
ms.author: jaimeo
author: jaimeo
ms.topic: article
audience: ITPro
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.openlocfilehash: e438e9a84b86bd4c3360022c0558480f317144e7
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59192789"
---
# <a name="access-the-admin-portal"></a>관리 포털 액세스

Microsoft Managed Desktop 게이트웨이가 [Microsoft Endpoint Manager.](https://endpoint.microsoft.com/) 장치 관리를 위해 이 포털의 기능에 익숙하지 않은 경우 장치 관리를 위한 Microsoft Endpoint Manager [참조하세요.](/mem/)

> [!NOTE]
> 이 [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) 지원되는 브라우저는 다음과 같습니다.
> - Microsoft Edge(최신 버전)
> - Safari(최신 버전, Mac만 해당)
> - Chrome(최신 버전)
> - Firefox(최신 버전)

관리 계정에 특정 사용 권한이 필요하여 해당 계정의 Microsoft Managed Desktop 기능에 액세스해야 Microsoft Endpoint Manager. 역할 기반 액세스 제어를 사용하여 조직 내에서 이러한 기능에 대한 관리자 액세스를 관리할 수 있습니다. 여러 Azure Active Directory(Azure AD) 관리자 역할 및 기본 제공 Microsoft Managed Desktop 역할을 사용하여 Microsoft Managed Desktop 관리 포털 내의 여러 기능에 대해 보다 세부적으로 제어할 수 있습니다. 역할 Azure Active Directory 대한 자세한 내용은 Azure AD 기본 제공 [역할을 참조하세요.](/azure/active-directory/roles/permissions-reference) 다양한 Microsoft 제품 및 서비스에 적용되는 Azure AD 관리자 역할과 달리 기본 제공 역할은 Microsoft Managed Desktop 특정하며 이 서비스의 관리자 기능에 대한 액세스만 보장합니다. 관리자는 기본 제공 역할을 사용자에게 개별적으로 또는 Azure AD 관리자 역할과 함께 할당하여 기존 관리자 계정에 Microsoft Managed Desktop 권한을 추가할 수 있습니다.

## <a name="azure-active-directory-roles-with-microsoft-managed-desktop-access"></a>Azure Active Directory 액세스 권한이 있는 Microsoft Managed Desktop 역할

|Azure AD 역할  |Microsoft Managed Desktop 권한  |
|---------|---------|
|전역 관리자     | 이 역할이 있는  관리자는 관리자 포털의 모든 기능에 대한 읽기 및 쓰기 Microsoft Managed Desktop 있습니다.         |
|전역 읽기 권한자     | 이 역할이 있는  관리자는 관리자 포털의 모든 기능에 대한 읽기 전용 Microsoft Managed Desktop 있습니다.         |
|Intune 서비스 관리자     |  이 역할이 있는  관리자는 관리자 포털에서 보안과 관련이 없는 기능에 대한 읽기 및 쓰기 Microsoft Managed Desktop 있습니다.       |
|서비스 지원 관리자     | 이 역할이 있는  관리자는 보안과 관련이 없는 기능에  대한 읽기 전용 권한을 가지며, 관리자 포털에서 지원 요청을 Microsoft Managed Desktop 권한이 있습니다.         |
|보안 관리자 | 이 역할이 있는  관리자는 관리 포털의 모든  기능에 대한 읽기 전용 권한을 가지며, 관리자 포털의 보안 관련 기능에 Microsoft Managed Desktop 권한이 있습니다. |
|보안 읽기 권한자 |이 역할이 있는  관리자는 관리자 포털의 모든 기능에 대한 읽기 전용 Microsoft Managed Desktop 있습니다.|

역할 할당에 대한 도움이 Azure Active Directory Azure AD 기본 제공 [역할을 참조하세요.](/azure/active-directory/roles/permissions-reference)

> [!IMPORTANT]
> 전역 관리자 역할에만 조직을 등록하는 데 필요한 권한이 Microsoft Managed Desktop.  역할이 Azure Active Directory 역할은 다양한 역할에 걸쳐 사용자 계정에 권한을 Microsoft 서비스. 등록을 완료한 Microsoft Managed Desktop 다른 작업을 수행하는 데 필요한  최소 권한으로 역할을 항상 사용해야 합니다.

## <a name="built-in-roles-provided-by-microsoft-managed-desktop"></a>Microsoft Managed Desktop


|기본 제공 역할  |Microsoft Managed Desktop 권한  |
|---------|---------|
|Microsoft Managed Desktop 서비스 관리자  | 사용자에게 할당된 경우 이 역할은  관리자 포털의 보안과 관련이 없는 기능에 대한 읽기 및 쓰기 Microsoft Managed Desktop 부여합니다.  |
|Microsoft Managed Desktop 서비스 읽기 | 사용자에게 할당된 경우 이 역할은  관리자 포털의 보안과 관련이 없는 기능에 대한 읽기 전용 Microsoft Managed Desktop 부여합니다. |
|Microsoft Managed Desktop 보안 관리자 |사용자에게 할당된 경우 이 역할은  관리자 포털의 보안 관련 기능에만 읽기 Microsoft Managed Desktop 권한을 부여합니다.   |

> [!NOTE]
> 보안 기능에는 보안 관련 통신, 보안 연락처 관리, 보안 관련 지원 요청 관리, 보안 관련 보고서 액세스가 포함됩니다. 

### <a name="assigning-built-in-roles-to-user"></a>사용자에게 기본 제공 역할 할당

기본 제공 역할을 쉽게 관리하기 위해 "최신 작업 공간 역할 _-_ 역할 이름"(예: "최신 작업 공간 역할 - 보안 관리자")으로 각 사용자 지정 역할에 대한 보안 그룹이 있습니다. 사용자를 이러한 보안 그룹 중 하나에 할당하기 위해 다음 단계를 수행합니다.
1. Microsoft Endpoint Manager 포털로 이동합니다.
2. **왼쪽에서** 그룹을 선택합니다.
3. 최신 작업 **공간 역할을 검색한** 다음 할당할 역할과 연결된 그룹을 선택합니다. 
4. 왼쪽에서 **구성원을** 선택한 다음 명령 표시줄에서 **+ 구성원** 추가를 선택합니다.
5. 추가할 사람의 전자 메일을 입력합니다. 게스트인 경우 그룹을 할당하려면 먼저 게스트를 초대해야 합니다.
6. **아래쪽에서** 선택을 선택합니다.

> [!NOTE]
> 역할 할당을 위한 중첩 보안 그룹은 현재 지원되지 않습니다. 

### <a name="assigning-built-in-roles-to-groups"></a>그룹에 기본 제공 역할 할당

기본 제공 역할을 기존 그룹에 하나 이상 할당해야 하는 경우 다음 단계를 수행합니다.

1. 으로 [portal.azure.com.](https://portal.azure.com/)
2. 응용 프로그램을 **검색하고 Enterprise 를 열 수 있습니다.**
3. 응용 프로그램 유형 **필터를** _Microsoft 응용 프로그램으로 변경한_ 다음 적용 을 **선택합니다.**
4. 최신 Workplace _고객 API를 검색하고 선택합니다._
5. 왼쪽 **창에서** 사용자 및 그룹을 선택한 다음 **+ 사용자/그룹 추가를 선택합니다.**
6. 사용자 및 그룹에서 원하는 **그룹을 검색합니다.**
7. 역할 선택에서 해당 역할을 검색한 다음 선택합니다.
8. **과제** 를 선택합니다.

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Microsoft Managed Desktop을 시작하기 위한 단계

1. 관리 포털 액세스(이 문서)
1. [관리 포털의 관리자 연락처를 추가하고 확인합니다](add-admin-contacts.md).
1. [등록 후 설정을 조정합니다](conditional-access.md).
1. [Intune 회사 포털](company-portal.md)을 배포하고 할당합니다.
1. [라이선스를 할당합니다](assign-licenses.md).
1. [앱을 배포합니다](deploy-apps.md).
1. [디바이스를 설정합니다](set-up-devices.md).
1. [Autopilot 및 등록 상태 페이지의 첫 실행 환경](esp-first-run.md)을 설정합니다.
1. [사용자 지원 기능을 사용하도록 설정합니다](enable-support.md).
1. [사용자가 디바이스를 사용할 수 있도록 준비합니다](get-started-devices.md).
1. [앱 컨트롤을 시작합니다](get-started-app-control.md).