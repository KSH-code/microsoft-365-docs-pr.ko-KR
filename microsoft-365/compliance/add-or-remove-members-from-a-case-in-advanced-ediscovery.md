---
title: 사례에서 구성원 추가 또는 제거
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 사례를 관리할 때 사례에 액세스할 수 있는 구성원을 추가하거나 제거하는 방법을 Advanced eDiscovery 합니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 8e239622add6965a280e9c2b01bc00d9f2b9b0d5
ms.sourcegitcommit: 317fab13e84b2867087a6ba0a593313ecf43bbed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2021
ms.locfileid: "60364666"
---
# <a name="add-or-remove-members-from-a-case"></a>케이스에서 구성원 추가 또는 제거

케이스에 액세스할 수 있는 사용자를 관리하기 위해 구성원을 추가하거나 제거할 수 있습니다. 그러나 구성원이 Advanced eDiscovery 액세스하고 이 경우 작업을 수행하려면 먼저 구성원의 사용 권한 페이지에서 eDiscovery 관리자  역할 그룹에 사용자를 추가해야 Microsoft 365 규정 준수 센터. 자세한 내용은 [eDiscovery 권한 할당](./assign-ediscovery-permissions.md)을 참조하세요.

1. **Advanced eDiscovery** 페이지에서 구성원을 추가할 케이스로 이동합니다.

2. **설정** 탭을 클릭한 다음 **액세스 권한 및 사용 권한** 타일에서 **선택** 을 클릭합니다.

3. **구성원 관리** 에서 **추가** 를 클릭하여 구성원을 케이스에 추가합니다. 역할 그룹 관리에서 추가를 클릭하여 사례에  역할 그룹을 **추가할 수 있습니다.**

4. 케이스의 구성원으로 추가할 수 있는 인물 또는 역할 그룹 목록에서 추가할 인물 또는 역할 그룹의 이름 옆에 있는 확인란을 선택합니다.

   > [!NOTE]
   > 역할 그룹을 사례에 추가할 때 사용자가 구성원으로 있는 역할 그룹만 추가할 수 있습니다.

5. 사례의 구성원으로 추가할 사용자 또는 역할 그룹을 선택한 후 추가를 **클릭합니다.**

6. **이 케이스 관리** 플라이아웃 페이지에서 **저장** 을 클릭하여 새 케이스 구성원 목록을 저장합니다.

> [!IMPORTANT]
> 사례의 구성원으로 추가한 역할 그룹에서 역할을 추가하거나 제거하면 역할 그룹이 사례의 구성원(또는 역할 그룹이 구성원인 경우)으로 자동으로 제거됩니다. 이러한 이유는 사례의 구성원에게 추가 사용 권한을 부수적으로 제공하는 것을 방지하기 위한 것입니다. 마찬가지로 역할 그룹이 삭제되면 역할 그룹이 구성원이던 모든 경우에서 제거됩니다. 자세한 내용은 [eDiscovery 권한 할당](assign-ediscovery-permissions.md#adding-role-groups-as-members-of-ediscovery-cases)을 참조하세요.

## <a name="removing-members-from-a-case"></a>사례에서 구성원 제거

[eDiscovery](assign-ediscovery-permissions.md) 관리자만 사례에서 구성원을 제거할 수 있습니다. eDiscovery 관리자 역할 그룹에 할당되거나 처음에 사례를 만든 경우에도 eDiscovery 관리자(Administrator)가 아니면 직접 또는 다른 구성원을 사례에서 제거할 수 없습니다. 자신 또는 다른 구성원을 사례에서 제거하려면 조직의 eDiscovery 관리자에게 문의하세요.
