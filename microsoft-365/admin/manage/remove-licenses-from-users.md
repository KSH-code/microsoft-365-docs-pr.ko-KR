---
title: 사용자의 라이선스 할당 취소
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: sinakassaw, nicholak
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- okr_smb
- manage_licenses
- commerce_licensing
- AdminTemplateSet
search.appverid: MET150
description: 제품 라이선스를 지정하지 않는 데 사용하는 방법은 특정 사용자로부터 라이선스를 지정하지 않는지 또는 특정 제품의 라이선스를 지정하지 않는지 여부에 따라 결정됩니다.
ms.date: 06/07/2021
ms.openlocfilehash: 8a67d7e690ff07631f696a97d6ed59925bc871df
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59187139"
---
# <a name="unassign-licenses-from-users"></a>사용자의 라이선스 할당 취소

활성 사용자 페이지 또는 라이선스 페이지에서 사용자로부터  라이선스를 **배포할 수** 있습니다. 사용하는 방법은 특정 사용자의 제품 라이선스를 지정을 해지할지 아니면 특정 제품의 사용자 라이선스를 지정을 해지할지 여부에 따라 결정됩니다.

> [!NOTE]
> 관리자는 조직의 사용자가 구입한 셀프 서비스 구매 구독의 라이선스를 할당하거나 할당 취소할 수 없습니다. [셀프 서비스 구매 구독을 이어 받은 다음](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription)할당 또는 할당 취소할 수 있습니다.

## <a name="before-you-begin"></a>시작하기 전에

- 라이선스를 할당하지하려면 전역, 라이선스, 사용자 관리자 되어야 합니다. 자세한 내용은 [Microsoft 365 관리자 역할 정보](../add-users/about-admin-roles.md)를 참조하세요.
- [Office 365 PowerShell로 사용자 계정에서 라이선스를 제거](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md)할 수 있습니다.
- 라이선스가 [할당된](../add-users/delete-a-user.md) 사용자 계정을 삭제하여 다른 사용자가 라이선스를 사용할 수 있도록 할 수도 있습니다. 사용자 계정을 삭제하면 다른 사용자에게 라이선스를 즉시 할당할 수 있습니다.

## <a name="use-the-licenses-page-to-unassign-licenses"></a>라이선스 페이지를 사용하여 라이선스를 배포합니다.

라이선스 페이지를 **사용하여** 라이선스를 지정하지 않은 경우 특정 제품에 대한 라이선스를 최대 20명까지 지정하지 않습니다.

::: moniker range="o365-worldwide"

1. 관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">라이선스</a> 페이지로 이동합니다.

::: moniker-end

::: moniker range="o365-germany"

 1. 관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">라이선스</a> 페이지로 이동합니다.

::: moniker-end

::: moniker range="o365-21vianet"

 1. 관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">라이선스</a> 페이지로 이동합니다.

::: moniker-end

2. 라이선스를 해지할 제품을 선택합니다.
3. 라이선스를 배포할 사용자를 선택합니다.
4. 라이선스 **배포를 선택합니다.**
5. 라이선스의 **Unassign(라이선스)** 상자에서 **Unassign (1)을 선택합니다.**

## <a name="use-the-active-users-page-to-unassign-licenses"></a>활성 사용자 페이지를 사용하여 라이선스의 배포를 허가합니다.

활성 사용자  페이지를 사용하여 라이선스를 배포할 때 사용자로부터 제품 라이선스를 배포하지 않습니다.

### <a name="unassign-licenses-from-one-user"></a>한 사용자의 라이선스에 대한 라이선스를 배포하지 않습니다.

::: moniker range="o365-worldwide"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다..

::: moniker-end

::: moniker range="o365-germany"

 1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다..

::: moniker-end

::: moniker range="o365-21vianet"

 1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다..

::: moniker-end

2. 라이선스를 배포할 사용자의 행을 선택합니다.
3. 오른쪽 창에서 **라이선스 및 앱** 을 선택합니다.
4. 라이선스 **섹션을 확장하고,** 라이선스를 취소할 라이선스의 확인란을 선택 취소한 다음 변경 **내용 저장을 선택합니다.**

### <a name="unassign-licenses-from-multiple-users"></a>여러 사용자의 라이선스를 배정하지 않습니다.

::: moniker range="o365-worldwide"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다..

::: moniker-end

::: moniker range="o365-germany"

 1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다..

::: moniker-end

::: moniker range="o365-21vianet"

 1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다..

::: moniker-end

2. 라이선스를 배포할 사용자의 이름 옆에 있는 원을 선택합니다.
3. 맨 위에 있는 **제품 라이선스 관리** 를 선택합니다.
4. 제품 **라이선스 관리 창에서** 모든 저장 변경 **내용에** 대한 사용 안  >  **을 선택합니다.**
5. 창 아래쪽에서 완료 를 **선택합니다.**  

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a>라이선스를 제거하면 사용자의 데이터가 어떻게 하나요?

- 사용자에서 라이선스가 제거되면 해당 Exchange 연결된 온라인 데이터는 30일 동안 저장됩니다. 30일의 유예 기간이 경과하면 데이터가 삭제되고 복구할 수 없습니다.
- 사용자가 비즈니스용 OneDrive Active Directory 동기화를 통해 제거되지 않으면 Microsoft 365 관리 센터 파일이 삭제되지 않습니다. 자세한 내용은 보존 [및 OneDrive 참조하세요.](/onedrive/retention-and-deletion)
- 라이선스가 제거되면 콘텐츠 검색 또는 검색과 같은 eDiscovery 도구를 사용하여 사용자의 사서함을 더 이상 검색할 수 Advanced eDiscovery. 자세한 내용은 에서 콘텐츠 검색의 "연결이 끊어지거나 라이선스가 해제된 사서함 [검색"을 Microsoft 365.](../../compliance/content-search.md)
- E3와 같은 Enterprise Office 365 Enterprise 구독이 있는 경우 Exchange Online 비활성 사서함을 사용하여 삭제된 사용자 계정의 사서함 데이터를 보존할 [수 있습니다.](../../compliance/inactive-mailboxes-in-office-365.md) 자세한 내용은 [에서 비활성 사서함](../../compliance/create-and-manage-inactive-mailboxes.md)만들기 및 관리를 Exchange Online.
- 라이선스가 제거된 후 사용자의 Microsoft 365 액세스를 차단하는 방법과 그 이후에 데이터에 액세스하는 방법에 대한 자세한 내용은 이전 직원 [제거를 참조합니다.](../add-users/remove-former-employee.md)
- 사용자의 라이선스를 제거하고 아직 Office 앱이 설치되어 있는 경우 [](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) 라이선스가 없는 제품 및 정품 인증 오류가 Office 앱을 사용할 때 Office 표시됩니다.

## <a name="next-steps"></a>다음 단계

사용되지 않는 라이선스를 [](../../managed-desktop/get-started/assign-licenses.md)다른 사용자에게 다시 재할당하지 않을 경우 [](../../commerce/licenses/buy-licenses.md) 필요한 것보다 많은 라이선스 비용을 지불하지 않을 수 있도록 구독에서 라이선스를 제거하는 것이 있습니다.

## <a name="related-content"></a>관련 콘텐츠

[구독에서 라이선스 제거(문서)\](../../commerce/licenses/buy-licenses.md)
[사용자에게 라이선스 할당](assign-licenses-to-users.md)(문서)\
[비즈니스용 Microsoft 365 구독 및 라이선스](../../commerce/licenses/subscriptions-and-licenses.md) 이해(문서)
