---
title: 관리자 역할 할당 Microsoft 365 관리 센터
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- okr_smb
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: eac4d046-1afd-4f1a-85fc-8219c79e1504
description: 사용자가 관리 센터에서 특정 작업을 수행할 수 있도록 비즈니스의 사용자 또는 여러 사용자에게 관리자 역할을 할당하는 방법을 설명합니다.
ms.openlocfilehash: 0eeafd8c91a9430db09713902fb55d9491dcac8d
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59185307"
---
# <a name="assign-admin-roles"></a>관리자 역할 할당

Microsoft 비즈니스 구독을 구입한 사람인 경우 전역 관리자입니다. 즉, 구독의 제품을 무제한으로 제어할 수 있으며 대부분의 데이터에 액세스할 수 있습니다.

자세한 내용은 [관리자 역할 정보](about-admin-roles.md)를 참조하세요.

새 사용자를 추가할 때 관리자 역할을 할당하지 않은 경우 해당  사용자는 사용자 역할에 있으며 Microsoft 관리 센터에 대한 관리자 권한이 없습니다. 하지만 작업을 완료하는 데 도움이 필요한 경우 사용자에게 관리자 역할을 할당할 수 있습니다. 예를 들어 암호를 다시 설정하는 데 도움이 되는 누군가가 필요한 경우 전역 관리자 역할을 할당하지 말고 암호 관리자 역할을 할당해야 합니다. 데이터 및 온라인 비즈니스에 무제한으로 액세스할 수 있는 전역 관리자가 너무 많을 경우 보안의 위험이 있습니다.

## <a name="watch-add-an-adminbrbr"></a>시청: 관리자 추가<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfO] 

이 비디오가 도움이 된 경우에는 [소규모 비즈니스 및 Microsoft 365를 처음 사용하는 사용자들을 위한 완전한 교육 시리즈](../../business-video/index.yml)를 참조하세요.

## <a name="assign-admin-roles"></a>관리자 역할 할당 

다음 두 가지 방법으로 사용자에게 역할을 할당할 수 있습니다.

- 사용자의 세부 정보 및 **역할** 관리로 이동하여 사용자에게 역할을 할당할 수 있습니다.
- 또는 역할로 **이동하여** 역할을 선택한 다음 여러 사용자를 추가할 수 있습니다.

### <a name="assign-admin-roles-to-users-using-roles"></a>역할을 사용하여 사용자에게 관리자 역할 할당

1. 관리 센터에서 역할 <a href="https://go.microsoft.com/fwlink/p/?linkid=2097861" target="_blank">**할당으로 이동하세요.**</a> Azure **AD 또는** **Intune** 탭을 선택하면 조직에서 사용할 수 있는 관리자 역할을 볼 수 있습니다.
2. 사용자를 할당할 관리자 역할을 선택합니다.
3. 할당된 **관리자 추가**  >  **를 선택합니다.**
4. 사용자의 표시 이름  또는 사용자 이름을 입력한 다음 제안 목록에서 사용자를 선택합니다.
5. 완료될 때까지 여러 사용자를 추가합니다.
6. **저장을** 선택한 다음 사용자가 할당된 관리자 목록에 추가됩니다.

### <a name="assign-a-user-to-an-admin-role-from-active-users"></a>활성 사용자의 관리자 역할에 사용자 할당

::: moniker range="o365-worldwide"

1. 관리 센터에서 사용자 활성 **사용자** > [페이지로](https://go.microsoft.com/fwlink/p/?linkid=834822) 이동합니다.

::: moniker-end

::: moniker range="o365-germany"

1. 관리 센터에서 **사용자** > <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다..

::: moniker-end

::: moniker range="o365-21vianet"

1. 관리 센터에서 **사용자** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다..

::: moniker-end

2. 활성 **사용자 페이지에서** 관리자 역할을 변경할 사용자를 선택합니다. 플라이아웃 창의 역할에서 **역할** **관리를 선택합니다.**

3. 사용자에게 할당할 관리자 역할을 선택합니다. 원하는 역할이 없는 경우 목록 맨 아래에서 **모두** 표시를 선택합니다.

## <a name="assign-admin-roles-to-multiple-users"></a>여러 사용자에게 관리자 역할 할당

PowerShell을 알고 있는 경우 PowerShell을 통해 사용자 계정에 역할 [할당을 참조합니다.](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md) 이 방법은 수백 명의 사용자에게 역할을 할당하는 경우 적합합니다.
  
수십 명의 사용자에게 역할을 할당하려면 다음 지침을 따릅니다.

## <a name="check-admin-roles-in-your-organization"></a>조직에서 관리자 역할 확인

다른 사용자에게 관리자 역할을 할당하기 위해 올바른 권한이 없는 것일 수 있습니다. 올바른 사용 권한이 있는지 확인하거나 다른 관리자에게 역할을 할당해달고 요청합니다.

다음 두 가지 방법으로 관리자 역할 권한을 확인할 수 있습니다.

- 사용자의 세부 정보로 이동하여 계정 페이지의 역할 **아래를** 볼 **수** 있습니다.
- 또는 역할로 **이동하여** 관리자 역할을 선택하고 할당된 관리자를 선택하여 할당된 사용자를 볼 수 있습니다.

## <a name="related-content"></a>관련 콘텐츠

[Microsoft 365 관리자 역할 정보](about-admin-roles.md)(문서)\
[Azure AD 기본 제공](/azure/active-directory/roles/permissions-reference) 역할(문서)\
[PowerShell을 통해](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md) 사용자 계정에 역할 할당(문서)\
[파트너 관계 승인 또는](../misc/add-partner.md) 제거(문서)