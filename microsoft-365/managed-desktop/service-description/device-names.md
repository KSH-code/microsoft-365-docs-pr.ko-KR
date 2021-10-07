---
title: 디바이스 이름
description: 장치 Microsoft Managed Desktop 관리하는 방법
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: aaf364d4244afaff86f532486597e864cd77209b
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60150369"
---
# <a name="device-names"></a>디바이스 이름

Microsoft Managed Desktop Autopilot, Windows, Azure Active Directory 및 Microsoft Intune. 이러한 서비스가 원활하게 작동하려면 장치에 일관된 표준화된 이름이 필요합니다. Microsoft Managed Desktop 등록할 때 표준화된 이름 *형식(MMD-%RAND11* 형식)이 적용됩니다. Windows Autopilot은 이러한 이름을 할당합니다. Autopilot에 대한 자세한 내용은 [Autopilot의](../get-started/esp-first-run.md)첫 실행 환경 및 등록 상태 페이지를 참조하세요.

## <a name="automated-name-changes"></a>자동 이름 변경

나중에 디바이스 이름이 변경되는 경우 Microsoft Managed Desktop 형식의 새 이름으로 자동으로 이름을 바니다. 이 프로세스는 4시간마다 발생합니다. 다음에 사용자가 장치를 다시 시작할 때 이름 변경이 실행됩니다.

> [!IMPORTANT]
> 환경이 특정 장치 이름(예: 특정 네트워크 구성을 지원하기 위해)에 의존하는 경우 해당 종속성에 등록하기 전에 해당 종속성 제거 옵션을 조사해야 Microsoft Managed Desktop. 이름 종속성은 유지해야 하는 경우 관리 [](../working-with-managed-desktop/admin-support.md) 포털을 통해 요청을 제출하여 이름 변경 기능을 사용하지 않도록 설정하고 원하는 이름 형식을 사용할 수 있습니다.