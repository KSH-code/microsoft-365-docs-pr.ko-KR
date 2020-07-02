---
title: 사용자의 라이선스 할당 취소
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: 사용자 계정에서 라이선스를 할당 해제 하는 방법에 대해 알아봅니다.
ms.date: 07/01/2020
ms.openlocfilehash: 29dbdb89550d5bd9bd13071b184ffe1ca340f2a6
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "45015938"
---
# <a name="unassign-licenses-from-users"></a>사용자의 라이선스 할당 취소

::: moniker range="o365-21vianet"

> [!NOTE]
> 관리 센터가 변경되고 있습니다. 사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)를 참조하세요.

::: moniker-end

::: moniker range="o365-worldwide"

**활성 사용자** 페이지 또는 **라이선스** 페이지에서 사용자의 라이선스 할당을 해제할 수 있습니다. 특정 사용자의 제품 라이선스 할당을 취소할 것인지 아니면 특정 제품에서 사용자 라이선스를 할당 하지 않을 지를 결정 하는 데 사용 하는 방법에 따라 다릅니다.

::: moniker-end

## <a name="before-you-begin"></a>시작하기 전에

- 라이선스 할당을 취소 하려면 전역, 라이선스, 사용자 관리자 여야 합니다. 자세한 내용은 [Microsoft 365 관리자 역할 정보](../add-users/about-admin-roles.md)를 참조하세요.
- [Office 365 PowerShell로 사용자 계정에서 라이선스를 제거](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)할 수 있습니다.
- 라이선스가 할당 된 [사용자 계정을 삭제](../add-users/delete-a-user.md) 하 여 다른 사용자가 라이선스를 사용할 수 있도록 할 수도 있습니다. 사용자 계정을 삭제 하면 해당 라이선스를 즉시 다른 사람에 게 할당할 수 있습니다.

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-unassign-licenses"></a>라이선스 페이지를 사용 하 여 라이선스 할당 해제

**라이선스** 페이지를 사용 하 여 라이선스 할당을 취소 하는 경우 최대 20 명의 사용자에 대 한 특정 제품의 라이선스 할당을 취소 합니다.

1. 관리 센터에서 **청구** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">라이선스</a> 페이지로 이동 합니다.
2. 라이선스의 할당을 취소할 제품을 선택 합니다.
3. 라이선스의 할당을 취소할 사용자를 선택 합니다.
4. **라이선스 할당**해제를 선택 합니다.
5. **라이선스 할당** 해제 상자에서 **할당**해제를 선택 합니다.

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-unassign-licenses"></a>활성 사용자 페이지를 사용 하 여 라이선스 할당 해제

**활성 사용자** 페이지를 사용 하 여 라이선스 할당을 취소 하는 경우 사용자 로부터 제품 라이선스 할당을 취소 합니다.

### <a name="unassign-licenses-from-one-user"></a>한 사용자의 라이선스 할당 해제
  
1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다.
2. 라이선스를 할당 해제할 사용자의 행을 선택 합니다.
3. 오른쪽 창에서 **라이선스 및 앱**를 선택합니다.
4. **라이선스** 섹션을 확장 하 고 할당을 취소할 라이선스에 대 한 확인란의 선택을 취소 한 다음 **변경 내용 저장**을 선택 합니다.

::: moniker-end

::: moniker range="o365-germany"

## <a name="unassign-licenses-from-one-user"></a>한 사용자의 라이선스 할당 해제

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다.
2. 라이선스의 할당을 취소할 사용자를 선택 합니다.
3. 오른쪽의 **제품 라이선스** 행에서 **편집**을 선택 합니다.
4. **제품 라이선스** 창에서 사용자에 대해 할당을 취소할 라이선스에 대 한 설정/ **해제** 위치로 전환 합니다. 예를 들어 Office 365 Enterprise E3 라이선스를 해제 하면 해당 라이선스 및 해당 사용자의 해당 라이선스에 있는 모든 서비스에 할당 되지 않습니다.
5. **제품 라이선스** 창의 아래쪽에서 **저장** \> **닫기** \> **닫기**를 선택합니다.

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="unassign-licenses-from-one-user"></a>한 사용자의 라이선스 할당 해제

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다.
2. 라이선스의 할당을 취소할 사용자를 선택 합니다.
3. 오른쪽의 **제품 라이선스** 행에서 **편집**을 선택 합니다.
4. **제품 라이선스** 창에서 사용자에 대해 할당을 취소할 라이선스에 대 한 설정/ **해제** 위치로 전환 합니다. 예를 들어 Office 365 Enterprise E3 라이선스를 해제 하면 해당 라이선스 및 해당 사용자의 해당 라이선스에 있는 모든 서비스에 할당 되지 않습니다.
5. **제품 라이선스** 창의 아래쪽에서 **저장** \> **닫기** \> **닫기**를 선택합니다.

::: moniker-end

::: moniker range="o365-worldwide"
###  <a name="unassign-licenses-from-multiple-users"></a>여러 사용자의 라이선스 할당 해제

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다.
2. 라이선스를 할당 하지 않을 사용자의 이름 옆에 있는 원을 선택 합니다.
3. 맨 위에 있는 **추가 옵션 (...)** 을 선택한 다음 **제품 라이선스 관리**를 선택합니다.
4. **제품 라이선스 관리** 창에서 **기존 제품 라이선스 할당 바꾸기** \> **다음**을 선택합니다.
5. **기존 제품 바꾸기** 창의 맨 아래에서 **선택한 사용자의 모든 제품 라이선스 제거** 확인란을 선택 하 고 **Replace** \> **닫기**바꾸기를 선택 합니다.

::: moniker-end

::: moniker range="o365-germany"

##  <a name="unassign-licenses-from-multiple-users"></a>여러 사용자의 라이선스 할당 해제

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다.
2. 모든 라이선스의 할당을 취소할 사용자의 이름 옆에 있는 상자를 선택 합니다.
3. **대량 작업** 창에서 **제품 라이선스 편집**을 선택합니다.
4. **기존 제품 바꾸기** 창에서 **기존 제품 라이선스 할당 바꾸기** \> **다음**을 선택합니다.
5. **기존 제품 바꾸기** 창의 맨 아래에서 **선택한 사용자의 모든 제품 라이선스 제거** 확인란을 선택 하 **고 닫기 닫기를 선택** \> **Close** \> **Close**합니다.

::: moniker-end

::: moniker range="o365-21vianet"

##  <a name="unassign-licenses-from-multiple-users"></a>여러 사용자의 라이선스 할당 해제
  
1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다.
2. 모든 라이선스의 할당을 취소할 사용자의 이름 옆에 있는 상자를 선택 합니다.
3. **대량 작업** 창에서 **제품 라이선스 편집**을 선택합니다.
4. **기존 제품 바꾸기** 창에서 **기존 제품 라이선스 할당 바꾸기** \> **다음**을 선택합니다.
5. **기존 제품 바꾸기** 창의 맨 아래에서 **선택한 사용자의 모든 제품 라이선스 제거** 확인란을 선택 하 **고 닫기 닫기를 선택** \> **Close** \> **Close**합니다.

::: moniker-end

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a>라이선스를 제거할 때 사용자의 데이터는 어떻게 되나요?

- 사용자가 라이선스를 제거 하면 해당 계정과 연결 된 데이터가 30 일 동안 보관 됩니다. 30 일 유예 기간이 지나면 데이터는 삭제 되며 복구할 수 없습니다.
- 비즈니스용 OneDrive에 저장 된 파일은 사용자가 Microsoft 365 관리 센터에서 삭제 되거나 Active Directory 동기화를 통해 제거 되지 않으면 삭제 되지 않습니다. 자세한 내용은 [OneDrive 보존 및 삭제](https://docs.microsoft.com/onedrive/retention-and-deletion)를 참조 하세요.
- 라이선스를 제거 하면 콘텐츠 검색 또는 고급 eDiscovery와 같은 eDiscovery 도구를 사용 하 여 사용자의 사서함을 더 이상 검색할 수 없습니다. 자세한 내용은 [Microsoft 365의 콘텐츠 검색](https://docs.microsoft.com/microsoft-365/compliance/content-search#searching-disconnected-or-de-licensed-mailboxes)에서 "연결이 끊어지거나 사용이 허가 되지 않은 사서함 검색"을 참조 하세요.
- Office 365 Enterprise E3와 같은 엔터프라이즈 구독을 사용 하는 경우 Exchange Online에서는 [비활성 사서함](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365)을 통해 삭제 된 사용자 계정의 사서함 데이터를 보존할 수 있습니다. 자세한 내용은 [Exchange Online에서 비활성 사서함 만들기 및 관리](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes)를 참조 하세요.
- 라이선스가 제거 된 후 Microsoft 365 데이터에 대 한 사용자의 액세스를 차단 하는 방법 및 나중에 데이터에 액세스 하는 방법에 대 한 자세한 내용은 [이전 직원 제거](../add-users/remove-former-employee.md)를 참조 하세요.
- 사용자의 라이선스를 제거 해도 여전히 Office 앱이 설치 되어 있으면 office 앱을 사용할 때 [office에서 허가 되지 않은 제품 및 정품 인증 오류가](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) 표시 됩니다.

## <a name="next-steps"></a>다음 단계

[사용 되지 않은 라이선스를 다른 사용자에 게 다시 할당](../../managed-desktop/get-started/assign-licenses.md)하지 않을 경우에는 라이선스를 사용자가 필요한 것 보다 더 많은 라이선스를 지불 하지 않도록 [구독에서 제거](../../commerce/licenses/buy-licenses.md) 하는 것이 좋습니다.

## <a name="related-content"></a>관련 콘텐츠

[구독에서 라이선스 제거](../../commerce/licenses/remove-licenses-from-subscription.md) (문서) \
[사용자에 게 라이선스 할당](assign-licenses-to-users.md) (문서) \
[Microsoft 365 for business의 구독 및 라이선스 이해](../../commerce/licenses/subscriptions-and-licenses.md) (문서)