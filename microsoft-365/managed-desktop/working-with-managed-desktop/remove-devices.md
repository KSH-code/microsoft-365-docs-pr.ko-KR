---
title: 장치 제거
description: 장치 관리에서 Microsoft Managed Desktop 제거
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 7b51a4d9e88ffd7e3b3cfec488cd750baedb0a3ef454edce4ce3784db8c9c421
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "53807171"
---
# <a name="remove-devices"></a>장치 제거

관리 포털을 사용하여 Microsoft Managed Desktop 관리에서 장치를 제거할 수 있습니다. 이 작업은 영구적이지만 등록 단계에 따라 Microsoft Managed Desktop 다시 등록할 [수 있습니다.](../get-started/register-devices-self.md)

장치를 제거하면 다음과 같은 모든 문제가 발생합니다.

- Autopilot에서 장치를 제거합니다.
- 모든 "최신 작업 공간" 장치 그룹에서 장치를 제거합니다.
- 관리 포털의 **장치** 블레이드에서 장치를 제거합니다.

장치를 제거할 때 Azure AD(Azure AD) 및 디바이스에서 Azure Active Directory 제거할 Microsoft Intune.
 
> [!CAUTION]
> Azure AD 및 디바이스와 관련된 개체는 영구적으로 Microsoft Intune 제거됩니다. 개체를 제거하면 Intune 및 Azure Portal에서 디바이스를 보거나 관리할 수 없습니다. 장치는 회사의 회사 리소스에 액세스할 수 없습니다. 장치가 삭제된 후 로그인을 시도하면 회사 데이터가 삭제될 수 있습니다.

1. In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), select **Devices** in the left navigation pane.
2. 메뉴의  Microsoft Managed Desktop 섹션을 찾아 장치를 **선택합니다.**
3. Microsoft Managed Desktop 작업 영역에서 삭제할 장치를 선택합니다.
4. 장치 **작업을 선택한** 다음 **플라이** 인을 여는 장치 삭제를 선택하여 장치를 제거합니다.
5. 플라이 인에서 선택한 장치를 검토한 다음 장치 **제거를 선택합니다.** Azure AD 및 Intune 개체도 동시에 제거하려면 확인란을 선택합니다. 장치 제거를 완료하는 데 몇 분 정도 걸릴 수 있습니다.

> [!NOTE]
> 보류 중인 등록 상태인 디바이스는 **제거할 수** 없습니다.