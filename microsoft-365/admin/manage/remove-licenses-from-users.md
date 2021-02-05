---
title: 사용자의 라이선스 할당 취소
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
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
description: 사용자 계정에서 라이선스를 배정을 Unassigns(라이선스)하는 방법을 학습합니다.
ms.date: 07/01/2020
ms.openlocfilehash: 6fb07883fdfd4f4a837890e3e8c4c04b2411772b
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114480"
---
# <a name="unassign-licenses-from-users"></a>사용자의 라이선스 할당 취소

::: moniker range="o365-21vianet"

> [!NOTE]
> 관리 센터가 변경되고 있습니다. 사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)를 참조하세요.

::: moniker-end

::: moniker range="o365-worldwide"

활성 사용자 페이지 또는 라이선스 페이지에서 사용자로부터  라이선스를 배포할 **수** 있습니다. 사용하는 방법은 특정 사용자의 제품 라이선스를 지정을 해지할지 아니면 특정 제품의 사용자 라이선스를 지정하지 않는지 여부에 따라 결정됩니다.

::: moniker-end

## <a name="before-you-begin"></a>시작하기 전에

- 라이선스를 할당을 할당하려면 전역, 라이선스, 사용자 관리자 되어야 합니다. 자세한 내용은 [Microsoft 365 관리자 역할 정보](../add-users/about-admin-roles.md)를 참조하세요.
- [Office 365 PowerShell로 사용자 계정에서 라이선스를 제거](https://docs.microsoft.com/microsoft-365/enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell)할 수 있습니다.
- 라이선스가 [](../add-users/delete-a-user.md) 할당된 사용자 계정을 삭제하여 다른 사용자가 라이선스를 사용할 수 있도록 할 수도 있습니다. 사용자 계정을 삭제하면 해당 라이선스를 즉시 다른 사용자에게 할당할 수 있습니다.

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-unassign-licenses"></a>라이선스 페이지를 사용하여 라이선스를 배포하지 않습니다.

라이선스 페이지를 **사용하여** 라이선스를 지정하지 않는 경우 특정 제품에 대한 라이선스를 최대 20명까지 지정하지 않습니다.

1. 관리 센터에서 **청구** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">라이선스</a> 페이지로 이동합니다.
2. 라이선스를 배포할 제품을 선택합니다.
3. 라이선스를 배포할 사용자를 선택합니다.
4. 라이선스 **배포를 선택하지 않습니다.**
5. 라이선스를 배포하지 않은 **상자에서** 사용 안 을 **선택합니다.**

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-unassign-licenses"></a>활성 사용자 페이지를 사용하여 라이선스를 배포하지 않습니다.

활성 사용자  페이지를 사용하여 라이선스를 배포하지 않는 경우 사용자로부터 제품 라이선스를 배포하지 않습니다.

### <a name="unassign-licenses-from-one-user"></a>한 사용자로부터 라이선스에 대한 라이선스를 배포하지 않습니다.
  
1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다.
2. 라이선스를 배포할 사용자의 행을 선택합니다.
3. 오른쪽 창에서 **라이선스 및 앱** 를 선택합니다.
4. 라이선스 **섹션을 확장하고,** 라이선스를 취소할 라이선스의 확인란을 선택 취소한 다음 변경 내용 **저장을 선택합니다.**

::: moniker-end

::: moniker range="o365-germany"

## <a name="unassign-licenses-from-one-user"></a>한 사용자로부터 라이선스에 대한 라이선스를 배포하지 않습니다.

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다.
2. 라이선스를 배포할 사용자를 선택해야 합니다.
3. 오른쪽의 **제품** 라이선스 행에서 편집을 **선택합니다.**
4. 제품 라이선스 **창에서** 사용자에게 배포를 해제할  라이선스의 해제 위치로 토글합니다. 예를 들어 Office 365 Enterprise E3 라이선스를 해제하는 경우 해당 사용자에 대해 해당 라이선스 및 해당 라이선스에 따라 모든 서비스에 대한 라이선스를 해제합니다.
5. **제품 라이선스** 창의 아래쪽에서 **저장** \> **닫기** \> **닫기** 를 선택합니다.

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="unassign-licenses-from-one-user"></a>한 사용자로부터 라이선스에 대한 라이선스를 배포하지 않습니다.

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다.
2. 라이선스를 배포할 사용자를 선택해야 합니다.
3. 오른쪽의 **제품** 라이선스 행에서 편집을 **선택합니다.**
4. 제품 라이선스 **창에서** 사용자에게 배포를 해제할  라이선스의 해제 위치로 토글합니다. 예를 들어 Office 365 Enterprise E3 라이선스를 해제하는 경우 해당 사용자에 대해 해당 라이선스 및 해당 라이선스에 따라 모든 서비스에 대한 라이선스를 해제합니다.
5. **제품 라이선스** 창의 아래쪽에서 **저장** \> **닫기** \> **닫기** 를 선택합니다.

::: moniker-end

::: moniker range="o365-worldwide"
###  <a name="unassign-licenses-from-multiple-users"></a>여러 사용자의 라이선스를 배정하지 않습니다.

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다.
2. 라이선스를 배포할 사용자의 이름 옆에 있는 원을 선택합니다.
3. 맨 위에 있는 **추가 옵션 (...)** 을 선택한 다음 **제품 라이선스 관리** 를 선택합니다.
4. **제품 라이선스 관리** 창에서 **기존 제품 라이선스 할당 바꾸기** \> **다음** 을 선택합니다.
5. 기존 제품 바꾸기 창의 맨 아래에서 선택한 사용자에서 모든 제품 라이선스 제거 확인란을 선택한 다음 **닫기 바꾸기를**   \> **선택합니다.**

::: moniker-end

::: moniker range="o365-germany"

##  <a name="unassign-licenses-from-multiple-users"></a>여러 사용자의 라이선스를 배정하지 않습니다.

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다.
2. 모든 라이선스를 배포할 사용자의 이름 옆에 있는 확인란을 선택합니다.
3. **대량 작업** 창에서 **제품 라이선스 편집** 을 선택합니다.
4. **기존 제품 바꾸기** 창에서 **기존 제품 라이선스 할당 바꾸기** \> **다음** 을 선택합니다.
5. 기존 제품 바꾸기 창의 맨 아래에서 선택한 사용자에서 모든 제품 라이선스 제거 확인란을 선택한 다음 닫기 **바꾸기를**   \>  \> **선택합니다.**

::: moniker-end

::: moniker range="o365-21vianet"

##  <a name="unassign-licenses-from-multiple-users"></a>여러 사용자의 라이선스를 배정하지 않습니다.
  
1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다.
2. 모든 라이선스를 배포할 사용자의 이름 옆에 있는 확인란을 선택합니다.
3. **대량 작업** 창에서 **제품 라이선스 편집** 을 선택합니다.
4. **기존 제품 바꾸기** 창에서 **기존 제품 라이선스 할당 바꾸기** \> **다음** 을 선택합니다.
5. 기존 제품 바꾸기 창의 맨 아래에서 선택한 사용자에서 모든 제품 라이선스 제거 확인란을 선택한 다음 닫기 **바꾸기를**   \>  \> **선택합니다.**

::: moniker-end

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a>라이선스를 제거하면 사용자의 데이터가 어떻게 하나요?

- 라이선스가 사용자에서 제거되면 해당 계정과 연결된 데이터는 30일 동안 보전됩니다. 30일의 유예 기간이 지난 후 데이터가 삭제되고 복구할 수 없습니다.
- 사용자가 Microsoft 365 관리 센터에서 삭제되거나 Active Directory 동기화를 통해 제거되지 않는 한 비즈니스용 OneDrive에 저장된 파일은 삭제되지 않습니다. 자세한 내용은 [OneDrive 보존 및](https://docs.microsoft.com/onedrive/retention-and-deletion)삭제를 참조하세요.
- 라이선스가 제거되면 콘텐츠 검색 또는 Advanced eDiscovery와 같은 eDiscovery 도구를 사용하여 사용자의 사서함을 더 이상 검색할 수 없습니다. 자세한 내용은 [Microsoft 365의](https://docs.microsoft.com/microsoft-365/compliance/content-search#searching-disconnected-or-de-licensed-mailboxes)콘텐츠 검색에서 "연결이 끊어지거나 라이선스가 해제된 사서함 검색"을 참조하세요.
- Office 365 Enterprise E3과 같은 엔터프라이즈 구독이 있는 경우 Exchange Online에서는 비활성 사서함을 사용하여 삭제된 사용자 계정의 사서함 데이터를 보존할 [수 있습니다.](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365) 자세한 내용은 [Exchange Online에서 비활성 사서함 만들기 및 관리를 참조하세요.](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes)
- 라이선스가 제거된 후 Microsoft 365 데이터에 대한 사용자의 액세스를 차단하는 방법과 이후에 데이터에 액세스하는 방법에 대한 자세한 내용은 이전 직원 [제거를 참조합니다.](../add-users/remove-former-employee.md)
- 사용자의 라이선스를 제거하고 여전히 Office 앱이 설치되어 있는 경우 Office 앱을 사용할 때 [Office에서](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) 사용 허가되지 않은 제품 및 정품 인증 오류가 표시됩니다.

## <a name="next-steps"></a>다음 단계

사용되지 않는 라이선스를 [](../../managed-desktop/get-started/assign-licenses.md)다른 사용자에게 다시 배포하지 않을 경우 필요한 [](../../commerce/licenses/buy-licenses.md) 것보다 많은 라이선스 비용을 지불하지 않을 수 있도록 구독에서 라이선스를 제거하는 것이 있습니다.

## <a name="related-content"></a>관련 콘텐츠

[구독에서 라이선스 제거(문서)\](../../commerce/licenses/remove-licenses-from-subscription.md)
[사용자에게 라이선스 할당(문서)\](assign-licenses-to-users.md)
[비즈니스용 Microsoft 365의](../../commerce/licenses/subscriptions-and-licenses.md) 구독 및 라이선스 이해(문서)