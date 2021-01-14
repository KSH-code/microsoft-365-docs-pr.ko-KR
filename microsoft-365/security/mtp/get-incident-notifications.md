---
title: Microsoft 365 Defender에서 인시던트 알림 다운로드
description: Microsoft 365 Defender에서 인시던트에 대한 전자 메일 알림을 받을 수 있는 규칙을 만드는 방법을 학습
keywords: 인시던트, 전자 메일, 전자 메일 알림, 구성, 사용자, 사서함, 전자 메일, 인시던트
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
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
ms.openlocfilehash: f25be4de3f25db869957474c3cb32b20e9f7aa53
ms.sourcegitcommit: 88d358d778804b26d5e41c53b4f725d01a78112b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49848894"
---
# <a name="get-incident-notifications-by-email"></a>전자 메일로 인시던트 알림 확인

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

새로운 인시던트 또는 기존 인시던트에 대한 새 업데이트가 있는 경우 전자 메일로 알려도록 Microsoft 365 Defender를 설정할 수 있습니다. 

인시던트 심각도에 따라 또는 장치 그룹으로 알림을 받을 수 있습니다. 인시던트당 첫 번째 업데이트에서만 알림을 하게 선택할 수도 있습니다.

전자 메일 알림에서 받는 사람을 추가하거나 제거할 수 있습니다. 새로 추가된 받는 사람은 인시던트가 추가된 후 알림을 받을 수 있습니다. 

전자 메일 알림에는 인시던트 이름, 심각도, 범주 등 인시던트에 대한 중요한 세부 정보가 포함되어 있습니다. 또한 인시던트로 바로 이동하여 조사를 바로 시작할 수 있습니다. 인시던트 조사에 대한 자세한 내용은 [Microsoft 365 Defender에서](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)인시던트 조사를 참조합니다.

>[!NOTE]
>전자 메일 알림 설정을 구성하려면 '보안 설정 관리' 권한이 필요합니다. 기본 사용 권한 관리를 사용하도록 선택한 경우 보안 관리자 또는 전역 관리자 역할이 있는 사용자가 자동으로 전자 메일 알림을 구성할 수 있습니다. <br> <br>
마찬가지로 조직에서 RBAC(역할 기반 액세스 제어)를 사용하는 경우 관리할 수 있는 장치 그룹에 따라 알림을 만들고, 편집하고, 삭제하고, 받을 수 있습니다.

## <a name="create-rules-for-incident-notifications"></a>문제 알림에 대한 규칙 만들기

인시던트에 대한 첫 번째 전자 메일 알림을 설정하려면 새 규칙을 만들고 전자 메일 알림 설정을 사용자 지정합니다.

1. 탐색 창에서 설정 **인시던트**  >  **전자 메일 알림을 선택합니다.**
2. 항목 **추가를 선택합니다.**
3. 이름에 규칙 이름을 **지정하고 설명을** **입력합니다.**

    ![문제 전자 메일 알림에 대한 규칙 창 만들기](../../media/incidentemailnotif1.png) 
4. **다음을** 선택하여 알림 **설정으로 이동합니다.** 여기서 다음을 지정할 수 있습니다.
    - **경고 심각도** - 인시던트 알림을 트리거하는 경고 심각도 선택 예를 들어 심각도 높은 인시던트에 대한 정보만 원할 경우 높음(High)을 선택합니다.
    - **장치 그룹 범위** - 이 드롭다운에는 사용자가 액세스할 수 있는 모든 장치 그룹이 표시됩니다. 인시던트 알림 규칙을 만들 장치 그룹을 선택합니다.
    - **인시던트당 첫** 번째 발생 시만 알림 - 이 옵션을 선택하면 다른 선택과 일치하는 첫 번째 경고에서만 전자 메일 알림이 전송됩니다. 나중에 인시던트와 관련된 업데이트 또는 경고는 알림을 트리거하지 않습니다.
    - **조직 이름 포함** - 고객 이름이 전자 메일 알림에 나타나는지 여부를 나타냅니다.
    - **테넌트별** 포털 링크 포함 - 테넌트 ID가 포함된 링크를 추가하여 특정 테넌트에 대한 액세스를 허용합니다.
    
    ![문제 전자 메일 알림에 대한 설정 창 알림](../../media/incidentemailnotif2.png)
5. 받는 **사람 섹션으로** 이동하려면 **다음을** 선택합니다. 여기서 인시던트 전자 메일 알림을 받을 전자 메일 주소를 지정할 수 있습니다. 모든 **전자 메일 주소를** 입력한 후 받는 사람 추가를 선택합니다.

    ![인시던트 전자 메일 알림에 대한 받는 사람 창 추가](../../media/incidentemailnotif3.png) 

6. 마지막으로 새 **규칙과** 연결된  모든 설정을 볼 수 있도록 검토 규칙으로 이동하려면 다음을 선택합니다. 받는 사람은 설정에 따라 전자 메일을 통해 문제 알림 수신을 시작하게 됩니다.

## <a name="see-also"></a>참고 항목
- [Microsoft 365 Defender의 인시던트 개요](https://docs.microsoft.com/microsoft-365/security/mtp/incidents-overview)
- [Microsoft 365 Defender에서 인시던트 우선 순위 지정](https://docs.microsoft.com/microsoft-365/security/mtp/incident-queue)
- [Microsoft 365 Defender에서 인시던트 조사](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)

