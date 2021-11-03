---
title: 전자 메일로 인시던트 알림 Microsoft 365 Defender
description: 2013에서 인시던트에 대한 전자 메일 알림을 받을 수 있는 규칙을 만드는 Microsoft 365 Defender
keywords: 인시던트, 전자 메일, 전자 메일 알림, 구성, 사용자, 사서함, 전자 메일, 인시던트, 분석, 응답
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 600ff555762112222769fde0372716f4a89a12b9
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2021
ms.locfileid: "60717586"
---
# <a name="get-incident-notifications-by-email"></a>전자 메일로 인시던트 알림 확인

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

새 인시던트 Microsoft 365 Defender 기존 인시던트에 대한 업데이트에 대한 전자 메일로 직원에게 알리도록 사용자 계정을 설정할 수 있습니다. 다음에 따라 알림을 하게 선택할 수 있습니다.

- 인시던트 심각도.
- 장치 그룹.
- 인시던트당 첫 번째 업데이트에만 해당합니다.

전자 메일 알림에는 인시던트 이름, 심각도, 범주 등 인시던트에 대한 중요한 세부 정보가 포함되어 있습니다. 인시던트로 바로 이동하여 분석을 바로 시작할 수도 있습니다. 자세한 내용은 인시던트 [조사를 참조하세요.](investigate-incidents.md)

전자 메일 알림에서 받는 사람을 추가하거나 제거할 수 있습니다. 새 받는 사람은 인시던트가 추가된 후 인시던트에 대한 알림을 받을 수 있습니다. 

>[!NOTE]
>전자 메일 알림 설정을 구성하려면 '보안 설정 관리' 권한이 필요합니다. 기본 사용 권한 관리를 사용하도록 선택한 경우 보안 관리자 또는 전역 관리자 역할이 있는 사용자는 자동으로 전자 메일 알림을 구성할 수 있습니다. <br> <br>
마찬가지로 조직에서 RBAC(역할 기반 액세스 제어)를 사용하는 경우 관리할 수 있는 장치 그룹에 따라 알림을 만들고, 편집하고, 삭제하고, 받을 수만 있습니다.

## <a name="create-a-rule-for-email-notifications"></a>전자 메일 알림에 대한 규칙 만들기

다음 단계에 따라 새 규칙을 만들고 전자 메일 알림 설정을 사용자 지정하세요.

1. 탐색 창에서 **인시던트 설정 > Microsoft 365 Defender > 알림을 선택합니다.**
2. 항목 **추가를 선택합니다.**
3. 기본 **페이지에서** 규칙 이름과 설명을 입력하고 다음 을 **선택합니다.**
4. 알림 **설정 페이지에서** 다음을 구성합니다.
    - **경고 심각도** - 인시던트 알림을 트리거할 경고 심각도를 선택합니다. 예를 들어 심각도 높은 인시던트에 대한 정보만 원할 경우 높음 을 **선택합니다.**
    - **장치 그룹 범위** - 모든 장치 그룹을 지정하거나 테넌트의 장치 그룹 목록에서 선택할 수 있습니다.
    - **인시던트당 첫 발생에만 알림** - 기타 선택 영역과 일치하는 첫 경고에 대해서만 알림을 받길 원하는 경우 선택합니다. 인시던트와 관련된 추후 업데이트 또는 경고에 대해서는 추가 알림이 발송되지 않습니다.
    - **전자 메일에 조직 이름 포함** - 전자 메일 알림에 조직 이름을 표시하려면 선택합니다.
    - **테넌트별 포털 링크 포함** - 전자 메일 알림에 특정 Microsoft 365 테넌트에 액세스하기 위한 테넌트 ID가 포함된 링크를 추가하려면 선택합니다.

    :::image type="content" source="../../media/get-incident-notifications/incidents-ss-email-notification-settings.png" alt-text="인시던트 전자 메일 알림에 대한 알림 설정입니다.":::

5. **다음** 을 선택합니다. 받는 **사람 페이지에서** 인시던트 알림을 받을 전자 메일 주소를 추가합니다. 각 **새 전자** 메일 주소를 입력한 후 추가를 선택합니다. 알림을 테스트하고 받는 사람이 받은 편지함으로 받는지 확인하려면 테스트 전자 메일 **보내기 를 선택합니다.** 
6. **다음** 을 선택합니다. 규칙 **검토 페이지에서** 규칙 설정을 검토한 다음 규칙 만들기 **를 선택합니다.** 받는 사람은 설정에 따라 전자 메일을 통해 인시던트 알림을 수신하기 시작할 것입니다.

기존 규칙을 편집하려면 규칙 목록에서 해당 규칙을 선택합니다. 규칙 이름이 있는 창에서 규칙  편집을 선택하고 **기본,** 알림 설정 및 받는 사람 페이지에서 **변경합니다.**

규칙을 삭제하려면 규칙 목록에서 규칙을 선택합니다. 규칙 이름이 있는 창에서 삭제를 **선택합니다.**

## <a name="see-also"></a>참고 항목
- [인시던트 개요](incidents-overview.md)
- [인시던트 우선 순위 지정](incident-queue.md)
- [인시던트 조사](investigate-incidents.md)
