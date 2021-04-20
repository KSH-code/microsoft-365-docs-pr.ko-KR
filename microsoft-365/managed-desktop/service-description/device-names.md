---
title: 장치 이름
description: Microsoft Managed Desktop에서 장치 이름을 관리하는 방법
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
ms.openlocfilehash: adf4809e0d8dc29f170475435b19092abf2062fd
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893893"
---
# <a name="device-names"></a>장치 이름

Microsoft Managed Desktop은 Windows Autopilot, Azure Active Directory 및 Microsoft Intune을 사용 합니다. 이러한 서비스가 원활하게 작동하려면 장치에 일관된 표준화된 이름이 필요합니다. Microsoft Managed Desktop은 장치가 등록된 경우 표준화된 이름 *형식(MMD-%RAND11* 형식)을 적용합니다. Windows Autopilot은 이러한 이름을 할당합니다. Autopilot에 대한 자세한 내용은 [Autopilot의](../get-started/esp-first-run.md)첫 실행 환경 및 등록 상태 페이지를 참조하세요.

## <a name="automated-name-changes"></a>자동 이름 변경

나중에 디바이스 이름이 변경되는 경우 Microsoft Managed Desktop에서 자동으로 표준화된 형식의 새 이름으로 이름을 바니다. 이 프로세스는 4시간마다 발생합니다. 다음에 사용자가 장치를 다시 시작할 때 이름 변경이 실행됩니다.

> [!IMPORTANT]
> 환경이 특정 장치 이름(예: 특정 네트워크 구성 지원)에 종속되는 경우 Microsoft Managed Desktop에 등록하기 전에 해당 종속성 제거 옵션을 조사해야 합니다. 이름 종속성은 유지해야 하는 경우 관리 [](../working-with-managed-desktop/admin-support.md) 포털을 통해 요청을 제출하여 이름 변경 기능을 사용하지 않도록 설정하고 원하는 이름 형식을 사용할 수 있습니다.