---
title: 디바이스 프로필 이해
description: 관리자가 디바이스에 할당할 수 있는 다양한 프로필
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
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
ms.openlocfilehash: 9f2d0d20d9df68cb10a5a84d6f2ba07d11a4e478
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60210116"
---
# <a name="device-profiles"></a>장치 프로필

장치에 서로 다른 미리 설정된 구성("장치 프로필")을 할당할 수 있습니다. 각 구성은 특정 유형의 사용자 요구에 최적화되어 있습니다. 세 개의 장치 프로필을 사용할 수 있습니다.

- Standard
- 중요한 데이터
- 파워 사용자

장치 프로필은 장치 구성 옵션 계층 구조의 일부로 생각할 수 있습니다.

:::image type="content" source="../../media/mmd-profile-options-heirarchy.png" alt-text="피라미드로 표시된 장치 구성. 설명은 다음과 같습니다.":::

기본적으로 모든 Microsoft Managed Desktop 장치에는 표준 보안 기준, 규정 준수 정책, Windows 설정 및 그룹을 포함하는 기초가 있습니다. 이 Microsoft Managed Desktop 사용하려면 모든 디바이스에 이러한 요소가 모두 포함되어야 합니다. 이러한 요소는 관리자의 요청 없이는 변경할 수 Microsoft Managed Desktop.

장치 프로필은 한 단계 더 높은 수준에 표시됩니다. 모든 Microsoft Managed Desktop 디바이스에는 하나만 할당된 프로필이 있어야 합니다. 관리자는 디바이스가 할당된 프로필을 선택할 수 있습니다.

여전히 더 높은 수준에서는 추가 [사용자 지정이 있습니다.](customizing.md) 각 디바이스에는 하나 이상의 사용자 지정이(또는 아니요) 있습니다. 하위 계층(장치 프로필 또는 기본 구성)을 수정하거나 표준 구성 위에 계층화된 완전히 새로운 요청이 될 수 있습니다.

맨 위에는 네트워크 세부 정보 또는 응용 프로그램과 같은 자체 수정 내용이 있습니다. 장치에는 이러한 수정 내용이 있을 수 있습니다. 이러한 수정은 해당 수정 내용에 의해 관리되거나 차단되지 Microsoft Managed Desktop.


## <a name="device-profile-details"></a>장치 프로필 세부 정보

다음 표에는 장치 프로필에 의해 구성된 각 설정의 설정과 해당 기본값이 요약되어 있습니다. (장면 뒤에서 이러한 설정은 OMA-URIs 사용자 지정 구성 프로필을 사용하여 구성됩니다Microsoft Endpoint Manager.

<br>

****

|기능|중요한 데이터|Power User|Standard|
|---|:---:|:---:|:---:|
|**외부 웹 Storage**|예|예|아니요|
|**[클라우드 차단 수준](/graph/api/resources/intune-deviceconfig-defendercloudblockleveltype)**|높음|높음|높음|
|**Microsoft 계정을 사용하지 않도록 설정**|예|예|아니요|
|**개인 정보 보호 OneDrive**|예|예|아니요|
|**권한 상승을 위해 보안 데스크톱으로 전환**|아니요|예|아니요|
|**끝점 장치 태그용 Microsoft Defender**|M365Managed-SensitiveData|M365Managed-PowerUser|M365Managed-Standard|
|**디바이스의 관리자인가요?**|아니요|예|아니요|
|**Autopilot 프로필**|MMD Standard|MMD Power User|MMD Standard|
|**AppLocker**|예|아니요|아니요|
|**공용 저장소 차단**|예|예|아니요|
|

각 장치 프로필에는 다음 항목도 관련됩니다.

- AAD(동적 구성원 Azure Active Directory 그룹)
- 정적 구성원 AAD 장치 그룹
- 구성 Microsoft Endpoint Manager 프로필

> [!IMPORTANT]
> 이러한 그룹의 구성원 자격을 직접 수정하지 않습니다. 프로필 다시 재배치에 설명된 인터페이스를 [사용합니다.](../working-with-managed-desktop/change-device-profile.md)

## <a name="limitations"></a>제한 사항

다른 정책과 같은 장치 프로필 및 해당 세부 정보의 예외를 요청할 수 있습니다. 조직에서 각 장치 프로필("테넌트")Azure Active Directory 수 있습니다. 예를 들어 중요한 데이터 장치 프로필에서 일부 사용자에 대해 AppLocker를 사용하지 않도록 설정할 것을 요청할 수 없습니다. 중요한 데이터 프로필이 있는 모든 디바이스의 구성이 동일해야 합니다.

각 디바이스에는 프로필이 하나만 있습니다. 여러 사용자가 특정 디바이스를 사용하는 경우 해당 장치의 모든 사용자가 동일한 구성을 하게 됩니다.
