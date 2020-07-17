---
title: 사용자에게 라이선스 할당
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- TopSMBIssues
- SaRA
- okr_SMB
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: 사용자에게 라이선스를 할당하는 방법을 알아봅니다.
ms.date: 07/01/2020
ms.openlocfilehash: 648a3433bf5c2bd9bb96abb90335f56ee4fb6bee
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "45015950"
---
# <a name="assign-licenses-to-users"></a>사용자에게 라이선스 할당

::: moniker range="o365-21vianet"

> [!NOTE]
> 관리 센터가 변경되고 있습니다. 사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)를 참조하세요.

::: moniker-end

::: moniker range="o365-worldwide"

**활성 사용자** 페이지 또는 **라이선스** 페이지에서 사용자에게 라이선스를 할당할 수 있습니다. 제품 라이선스를 특정 사용자에게 할당할지 아니면 사용자 라이선스를 특정 제품에 할당할지 여부에 따라 사용하는 방법이 다릅니다.

::: moniker-end

[사용자를 추가하는 동시에 라이선스를 할당하는 방법에 대해 알아봅니다.](../add-users/add-users.md)

## <a name="before-you-begin"></a>시작하기 전에 다음의 조건을 만족해야 합니다.

- 라이선스를 할당하려면 전역, 라이선스 또는 사용자 관리자여야 합니다. 자세한 내용은 [Microsoft 365 관리자 역할 정보](../add-users/about-admin-roles.md)를 참조하세요.
- [Office 365 PowerShell을 사용하여 사용자 계정에 라이선스를 할당](https://go.microsoft.com/fwlink/p/?linkid=850410)할 수 있습니다.
- 그룹 기반 라이선싱을 사용하려면 [Azure Active Directory에서 그룹 구성원으로 사용자에게 라이선스 할당](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)을 참조하세요.
- Sway와 같은 일부 서비스는 사용자에게 자동으로 할당되므로 개별적으로 할당할 필요가 없습니다.

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-assign-licenses-to-users"></a>라이선스 페이지를 사용하여 사용자에게 라이선스 할당

**라이선스** 페이지를 사용하여 라이선스를 할당하는 경우 특정 제품에 대한 라이선스를 최대 20명의 사용자에게 할당합니다. **라이선스** 페이지에는 구독하고 있는 모든 제품이 목록에 표시됩니다. 각 제품에 대한 총 라이선스 수, 할당된 라이선스 수 및 사용할 수 있는 라이선스 수를 확인할 수도 있습니다.

1. 관리 센터에서 **청구** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">라이선스</a> 페이지로 이동합니다.
2. 제품을 선택합니다.
3. 제품 세부 정보 페이지에서 **라이선스 할당**을 선택합니다.
4. **사용자에게 라이선스 할당** 창에서 이름을 입력한 다음 결과에서 해당 이름을 선택하여 목록에 추가합니다. 한 번에 최대 20명의 사용자를 추가할 수 있습니다.
5. **앱 및 서비스를 설정 또는 해제**를 선택하여 특정 항목에 대한 액세스 권한을 할당하거나 제거합니다.
6. 작업을 마치면 **할당**을 선택한 다음 **닫기**를 선택합니다.

충돌이 발생한 경우 메시지가 표시되고 문제 및 수정 방법에 대해 알 수 있습니다. 예를 들어 충돌하는 서비스를 포함하는 라이선스를 선택한 경우 각 라이선스에 포함된 서비스를 검토하라는 오류 메시지가 표시되고 다시 시도합니다.

## <a name="change-the-apps-and-services-a-user-has-access-to"></a>사용자가 액세스할 수 있는 앱 및 서비스의 변경

1. 관리 센터에서 **청구** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">라이선스</a> 페이지로 이동합니다.
2. **라이선스** 페이지에서 특정 사용자에 대한 행을 선택합니다.
3. 오른쪽 창에서 액세스 권한을 부여 또는 제거할 앱과 서비스를 선택하거나 선택 취소합니다.
4. 작업을 마치면 **저장**을 선택한 다음 **닫기**를 선택합니다.

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-assign-licenses"></a>활성 사용자 페이지를 사용하여 라이선스 할당

**활성 사용자** 페이지를 사용하여 라이선스를 할당할 때 사용자에게 제품에 대한 라이선스를 할당합니다.

### <a name="assign-licenses-to-multiple-users"></a>여러 사용자에게 라이선스 할당

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다.
2. 라이선스를 할당하려는 사용자의 이름 옆에 원을 선택합니다.
3. 맨 위에 있는 **추가 옵션 (...)** 을 선택한 다음 **제품 라이선스 관리**를 선택합니다.
4. **제품 라이선스 관리** 창에서 **기존 제품 라이선스 할당에 추가** \> **다음**을 선택합니다.
5. **기존 제품에 추가** 창에서 선택한 사용자에게 제공하려는 라이선스의 **설정** 위치로 토글합니다.
    기본적으로 해당 라이선스와 연결된 모든 서비스가 사용자에게 자동으로 할당됩니다. 사용자가 이용할 수 있는 서비스를 제한할 수 있습니다. 사용자에게 제공하지 않으려는 서비스의 **해제** 위치로 토글합니다.
6. 창의 아래쪽에서 **추가** \> **닫기**를 선택합니다.  

::: moniker-end

::: moniker range="o365-germany"

## <a name="assign-licenses-to-multiple-users"></a>여러 사용자에게 라이선스 할당

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다.
2. 라이선스를 할당하려는 사용자의 이름 옆의 확인란을 선택합니다.
3. **대량 작업** 창에서 **제품 라이선스 편집**을 선택합니다.
4. **제품 할당** 창에서 **기존 제품 라이선스 할당에 추가** \> **다음**을 선택합니다.
5. 선택한 사용자에게 제공하려는 라이선스의 **설정** 위치로 토글합니다.
    기본적으로 해당 라이선스와 연결된 모든 서비스가 사용자에게 자동으로 할당됩니다. 사용자가 이용할 수 있는 서비스를 제한할 수 있습니다. 사용자에게 제공하지 않으려는 서비스의 **해제** 위치로 토글합니다.
6. **기존 제품에 추가** 창의 아래쪽에서 **추가** \> **닫기** \> **닫기**를 선택합니다.

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="assign-licenses-to-multiple-users"></a>여러 사용자에게 라이선스 할당

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다.
2. 라이선스를 할당하려는 사용자의 이름 옆의 확인란을 선택합니다.
3. **대량 작업** 창에서 **제품 라이선스 편집**을 선택합니다.
4. **제품 할당** 창에서 **기존 제품 라이선스 할당에 추가** \> **다음**을 선택합니다.
5. 선택한 사용자에게 제공하려는 라이선스의 **설정** 위치로 토글합니다.
    기본적으로 해당 라이선스와 연결된 모든 서비스가 사용자에게 자동으로 할당됩니다. 사용자가 이용할 수 있는 서비스를 제한할 수 있습니다. 사용자에게 제공하지 않으려는 서비스의 **해제** 위치로 토글합니다.
6. **기존 제품에 추가** 창의 아래쪽에서 **추가** \> **닫기** \> **닫기**를 선택합니다.

::: moniker-end

::: moniker range="o365-worldwide"

### <a name="assign-licenses-to-one-user"></a>한 명의 사용자에게 라이선스 할당

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다..
2. 라이선스를 할당하려는 사용자의 행을 선택합니다.
3. 오른쪽 창에서 **라이선스 및 앱**를 선택합니다.
4. **라이선스** 섹션을 확장하고 할당하려는 라이선스의 확인란을 선택한 다음 **변경 내용 저장**을 선택합니다.

::: moniker-end

::: moniker range="o365-germany"

## <a name="assign-licenses-to-one-user"></a>한 명의 사용자에게 라이선스 할당

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다.
2. 라이선스를 할당하려는 사용자의 이름 옆의 확인란을 선택합니다.
3. 오른쪽 창의 **제품 라이선스** 행에서 **편집**을 선택합니다.
4. **제품 라이선스** 창에서 이 사용자에게 할당하려는 라이선스에 대해 **설정** 위치로 토글합니다.
    기본적으로 해당 라이선스와 연결된 모든 서비스가 사용자에게 자동으로 할당됩니다. 사용자가 이용할 수 있는 서비스를 제한할 수 있습니다. 사용자에게 제공하지 않으려는 서비스의 **해제** 위치로 토글합니다.
5. **제품 라이선스** 창의 아래쪽에서 **저장** \> **닫기** \> **닫기**를 선택합니다.

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="assign-licenses-to-one-user"></a>한 명의 사용자에게 라이선스 할당

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다.
2. 라이선스를 할당하려는 사용자의 이름 옆의 확인란을 선택합니다.
3. 오른쪽 창의 **제품 라이선스** 행에서 **편집**을 선택합니다.
4. **제품 라이선스** 창에서 이 사용자에게 할당하려는 라이선스에 대해 **설정** 위치로 토글합니다.
    기본적으로 해당 라이선스와 연결된 모든 서비스가 사용자에게 자동으로 할당됩니다. 사용자가 이용할 수 있는 서비스를 제한할 수 있습니다. 사용자에게 제공하지 않으려는 서비스의 **해제** 위치로 토글합니다.
5. **제품 라이선스** 창의 아래쪽에서 **저장** \> **닫기** \> **닫기**를 선택합니다.

::: moniker-end

## <a name="next-steps"></a>다음 단계

사용자가 아직 Office 앱을 설치하지 않은 경우 [직원 빠른 시작 가이드](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f)를 사용자와 공유하여 [PC 또는 Mac에서 Microsoft 365 또는 Office 2019를 다운로드하고 설치하는 방법](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) 및 [모바일 장치에서 Office 앱 및 전자 메일을 설정하는 방법](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f)과 같은 항목을 설정할 수 있습니다.

## <a name="related-content"></a>관련 콘텐츠

[구독 및 라이선스 이해](../../commerce/licenses/subscriptions-and-licenses.md) (문서)\
[사용자의 라이선스 할당 취소](remove-licenses-from-users.md) (문서)\
[구독에 대한 라이선스 구입 또는 제거](../../commerce/licenses/buy-licenses.md) (문서)