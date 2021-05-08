---
title: 차세대 보호
description: Microsoft Defender 바이러스 백신, 내장된 맬웨어 및 바이러스 방지 기능을 관리, 구성 및 사용하는 방법에 대해 알아 보세요.
keywords: Microsoft Defender Antivirus, windows defender, antimalware, scep, system center endpoint protection, system center configuration manager, virus, malware, threat, detection, protection, security
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Priority
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: c4a0e40f3f6e6728af3d8c7a6da29485f1fad3fd
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52269603"
---
# <a name="next-generation-protection"></a>차세대 보호

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

## <a name="microsoft-defender-antivirus-your-next-generation-protection"></a>Windows Defender 바이러스 백신: 차세대 보호 기능 제공

Windows Defender 바이러스 백신은 Microsoft Defender for Endpoint의 차세대 보호 구성 요소입니다. 이 기능은 머신 러닝, 빅데이터 분석, 심층 위협 방지 연구, Microsoft 클라우드 인프라를 조합해서 엔터프라이즈 조직의 디바이스를 보호합니다. 차세대 보호 서비스에는 다음과 같은 기능이 포함되어 있습니다.

- [동작 기반, 휴리스틱 및 실시간 바이러스 백신 보호](configure-protection-features-microsoft-defender-antivirus.md)는 파일 및 프로세스 동작 모니터링 및 기타 휴리스틱(*실시간 보호* 라고도 함)을 사용한 상시 검색을 포함합니다. 또한 안전하지 않다고 생각되지만 악성 프로그램으로 탐지되지 않을 수 있는 앱 탐지 및 차단도 포함됩니다.
- 새로운 위협과 새로운 위협에 대한 거의 즉각적인 탐지 및 차단을 포함하는 [클라우드 제공 보호](cloud-protection-microsoft-defender-antivirus.md)입니다.
- [전용 보호 및 제품 업데이트](manage-updates-baselines-microsoft-defender-antivirus.md)는 Microsoft Defender 바이러스 백신을 최신 상태로 유지하는 것과 관련된 업데이트를 포함합니다.

## <a name="try-a-demo"></a>데모를 사용해 보세요!

[Microsoft Defender for Endpoint 데모 웹 사이트](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)에 방문하여 다음 보호 기능이 작동하고 있는지 확인하고 데모 시나리오를 사용하여 탐색하세요.
- 클라우드 제공 보호
- BAFS(first sight 차단) 보호
- PUA(잠재적으로 원치 않는 응용 프로그램) 보호

## <a name="minimum-system-requirements"></a>시스템 최소 요구 사항

Microsoft Defender 바이러스 백신의 하드웨어 요구 사항은 Windows 10과 동일합니다. 자세한 내용은 다음 참조 자료를 참조하세요.

- [최소 하드웨어 요구 사항](/windows-hardware/design/minimum/minimum-hardware-requirements-overview)
- [하드웨어 구성 요소 지침](/windows-hardware/design/component-guidelines/components)

## <a name="configure-next-generation-protection-services"></a>차세대 보호 구성

차세대 보호 서비스를 구성하는 방법에 대한 자세한 내용은 [Microsoft Defender 바이러스 백신 기능 구성](configure-microsoft-defender-antivirus-features.md)을 참조하세요.

> [!Note]  
> 구성 및 관리는 Microsoft Defender 바이러스 백신을 실행하는 동안 Windows Server 2016과 Windows Server 2019에서 거의 동일합니다. 그러나 몇 가지 차이점이 있습니다. 자세한 내용은 [Windows Server 2016 및 2019의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-on-windows-server.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

- [Windows Server 2016 및 2019의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-on-windows-server.md)
- [Microsoft Defender 바이러스 백신 관리 및 구성](configuration-management-reference-microsoft-defender-antivirus.md)
- [Microsoft Defender 바이러스 백신 평가](evaluate-microsoft-defender-antivirus.md)
