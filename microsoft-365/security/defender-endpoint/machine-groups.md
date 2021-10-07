---
title: 끝점용 Microsoft Defender에서 장치 그룹 만들기 및 관리
description: 그룹에 적용되는 규칙을 확인하여 장치 그룹을 만들고 자동화된 수정 수준을 설정
keywords: 장치 그룹, 그룹, 수정, 수준, 규칙, aad 그룹, 역할, 할당, 순위
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
ms.openlocfilehash: a9576470b029ac97660868341c46ecda82662b36
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60152024"
---
# <a name="create-and-manage-device-groups"></a>장치 그룹 만들기 및 관리

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**
- Azure Active Directory
- Office 365

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

엔터프라이즈 시나리오에서는 보안 운영 팀에 일반적으로 장치 집합이 할당됩니다. 이러한 장치는 도메인, 컴퓨터 이름 또는 지정된 태그와 같은 특성 집합에 따라 그룹화됩니다.

끝점용 Microsoft Defender에서 장치 그룹을 만들고 이를 사용하여 다음을 할 수 있습니다.

- 할당된 [RBAC](rbac.md) 역할이 있는 특정 Azure AD 사용자 그룹으로 관련 경고 및 데이터에 대한 액세스 제한
- 여러 장치 집합에 대해 다른 자동 수정 설정 구성
- 자동화된 조사 중에 적용할 특정 수정 수준 할당
- 조사에서 그룹 필터를 사용하여 **장치** 목록을 특정 장치 그룹으로 **필터링합니다.**

RBAC(역할 기반 액세스)의 컨텍스트에서 장치 그룹을 만들어 특정 작업을 수행하거나 사용자 그룹에 장치 그룹을 할당하여 정보를 볼 수 있는 사용자를 제어할 수 있습니다. 자세한 내용은 역할 기반 액세스 제어를 사용하여 포털 액세스 [관리를 참조하세요.](rbac.md)

> [!TIP]
> RBAC 응용 프로그램을 포괄적으로 살펴보기 위해 [SOC가 RBAC를 통해 평평하게 실행 중인지 확인을 읽어야 합니다.](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Is-your-SOC-running-flat-with-limited-RBAC/ba-p/320015)

디바이스 그룹을 만드는 프로세스의 일부로 다음을 할 수 있습니다.

- 이 그룹에 대한 자동화된 수정 수준을 설정합니다. 수정 수준에 대한 자세한 내용은 자동화된 조사를 사용하여 위협 조사 및 [수정을 참조하세요.](automated-investigations.md)
- 장치 이름, 도메인, 태그 및 OS 플랫폼에 따라 그룹에 속하는 장치 그룹을 결정하는 일치 규칙을 지정합니다. 장치가 다른 그룹과도 일치하면 가장 높은 순위의 장치 그룹에만 추가됩니다.
- 디바이스 그룹에 대한 액세스 권한이 있는 Azure AD 사용자 그룹을 선택합니다.
- 장치 그룹을 만든 후 다른 그룹을 상대로 순위를 정합니다.

> [!NOTE]
> Azure AD 그룹을 할당하지 않은 경우 모든 사용자가 디바이스 그룹에 액세스할 수 있습니다.

## <a name="create-a-device-group"></a>장치 그룹 만들기

1. 탐색 창에서 **끝점 사용 설정** 장치 그룹 \> **을** \>  \> **선택합니다.**

2. 장치 **그룹 추가를 클릭합니다.**

3. 그룹 이름 및 자동화 설정을 입력하고 그룹에 속하는 장치를 결정하는 일치 규칙을 지정합니다. 자동화된 [조사가 시작되는 방법을 참조합니다.](automated-investigations.md#how-the-automated-investigation-starts)

    > [!TIP]
    > 조직 구성 단위로 장치를 그룹화하려는 경우 그룹 소속에 대한 레지스트리 키를 구성할 수 있습니다. 장치 태그 지정에 대한 자세한 내용은 장치 태그 [만들기 및 관리를 참조하세요.](machine-tags.md)

4. 이 규칙에 따라 일치하게 될 여러 장치를 미리 본다. 규칙에 만족하면 사용자 액세스 **탭을** 클릭합니다.

5. 만든 장치 그룹에 액세스할 수 있는 사용자 그룹을 할당합니다.

    > [!NOTE]
    > RBAC 역할에 할당된 Azure AD 사용자 그룹에만 액세스 권한을 부여할 수 있습니다.

6. **닫기** 를 클릭합니다. 구성 변경 내용이 적용됩니다.

## <a name="manage-device-groups"></a>장치 그룹 관리

일치하는 동안 우선 순위가 더 높거나 낮게 부여될 수 있도록 장치 그룹의 순위를 승격하거나 강등할 수 있습니다. 장치가 두 개 이상의 그룹에 일치하면 가장 높은 순위의 그룹에만 추가됩니다. 그룹을 편집하고 삭제할 수도 있습니다.

> [!WARNING]
> 장치 그룹을 삭제하면 전자 메일 알림 규칙에 영향을 줄 수 있습니다. 장치 그룹이 전자 메일 알림 규칙에 따라 구성된 경우 해당 규칙에서 제거됩니다. 장치 그룹이 전자 메일 알림에 대해 구성된 유일한 그룹인 경우 해당 전자 메일 알림 규칙이 장치 그룹과 함께 삭제됩니다.

기본적으로 디바이스 그룹은 포털 액세스 권한이 있는 모든 사용자가 액세스할 수 있습니다. Azure AD 사용자 그룹을 장치 그룹에 할당하여 기본 동작을 변경할 수 있습니다.

그룹과 일치하지 않는 장치는 그룹이 없는 장치(기본값) 그룹에 추가됩니다. 이 그룹의 순위를 변경하거나 삭제할 수 없습니다. 그러나 이 그룹의 수정 수준을 변경하고 이 그룹에 액세스할 수 있는 Azure AD 사용자 그룹을 정의할 수 있습니다.

> [!NOTE]
> 장치 그룹 구성에 변경 내용을 적용하는 데 최대 몇 분 정도 걸릴 수 있습니다.

### <a name="add-device-group-definitions"></a>장치 그룹 정의 추가

장치 그룹 정의에는 각 조건에 대한 여러 값도 포함할 수 있습니다. 여러 태그, 장치 이름 및 도메인을 단일 장치 그룹의 정의로 설정할 수 있습니다.

1. 새 장치 그룹을 만든 다음 장치 **탭을** 선택합니다.
2. 조건 중 하나에 대한 첫 번째 값을 추가합니다.
3. 같은 속성 형식의 행을 더 추가하려면 `+` 선택합니다.

> [!TIP]
> 속성당 여러 값을 허용하는 동일한 조건 유형의 행 사이에 'OR' 연산자를 사용합니다.
>
> 태그, 장치 이름, 도메인 등 각 속성 유형에 대해 최대 10개 행(값)을 추가할 수 있습니다.

장치 그룹 정의에 연결하는 데 대한 자세한 내용은 장치 그룹 - 보안 Microsoft 365 [참조하세요.](https://sip.security.microsoft.com/homepage)

## <a name="related-topics"></a>관련 항목

- [역할 기반 액세스 제어를 사용하여 포털 액세스 관리](rbac.md)
- [장치 태그 만들기 및 관리](machine-tags.md)
- [테넌트 API를 사용하여 테넌트 Graph 목록](/graph/api/device-list-memberof)
