---
title: 차세대 보호
description: Microsoft Defender 바이러스 백신, 기본 제공 맬웨어 방지 및 바이러스 백신 보호를 관리, 구성 및 사용하는 방법을 학습합니다.
keywords: Microsoft Defender 바이러스 백신, windows defender, 맬웨어 방지, scep, system center endpoint protection, system center configuration manager, 바이러스, 맬웨어, 위협, 탐지, 보호, 보안
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: priority
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: eb7e0253b3761d05d112500c0410fffa58548221
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765422"
---
# <a name="next-generation-protection"></a>차세대 보호

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/) 

## <a name="microsoft-defender-antivirus-your-next-generation-protection"></a>Microsoft Defender 바이러스 백신: 차세대 보호

Microsoft Defender 바이러스 백신은 끝점용 Microsoft Defender의 차세대 보호 구성 요소입니다. 이 보호는 기계 학습, 빅 데이터 분석, 심층 위협 저항 연구 및 Microsoft 클라우드 인프라를 함께 사용하여 엔터프라이즈 조직의 장치를 보호합니다. 차세대 보호 서비스에는 다음 기능이 포함됩니다.

- [동작 기반,](configure-protection-features-microsoft-defender-antivirus.md)지론 및 실시간 바이러스 백신 보호 - 파일 및 프로세스 동작 모니터링 및 기타추론(실시간 보호라고도 알려지기)을 사용하는 항상 검사가 *포함됩니다.* 또한 안전하지 않은 것으로 보이지만 맬웨어로 검색되지 않을 수 있는 앱을 검색하고 차단하는 방법도 포함되어 있습니다.
- [클라우드 제공 보호](cloud-protection-microsoft-defender-antivirus.md)- 새로운 위협을 거의 즉각적으로 감지하고 차단하는 기능을 포함합니다.
- [전용 보호 및 제품 업데이트](manage-updates-baselines-microsoft-defender-antivirus.md)에는 Microsoft Defender 바이러스 백신을 최신 상태로 유지하는 데 관련된 업데이트가 포함됩니다.

## <a name="try-a-demo"></a>데모를 사용해 보세요!

[Endpoint용 Microsoft Defender 데모](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 웹 사이트를 방문하여 다음 보호 기능이 작동하고 있으며 데모 시나리오를 사용하여 탐색합니다.
- 클라우드 제공 보호
- BAFS(최초 차단) 보호
- 잠재적으로 원치 않는 응용 프로그램(PUA) 보호

## <a name="minimum-system-requirements"></a>최소 시스템 요구 사항

Microsoft Defender 바이러스 백신의 하드웨어 요구 사항은 Windows 10과 동일합니다. 자세한 내용은 다음 리소스를 참조하세요.

- [최소 하드웨어 요구 사항](/windows-hardware/design/minimum/minimum-hardware-requirements-overview)
- [하드웨어 구성 요소 지침](/windows-hardware/design/component-guidelines/components)

## <a name="configure-next-generation-protection-services"></a>차세대 보호 서비스 구성

차세대 보호 서비스를 구성하는 방법에 대한 자세한 내용은 Microsoft Defender 바이러스 백신 기능 [구성을 참조하세요.](configure-microsoft-defender-antivirus-features.md)

> [!Note]  
> 구성 및 관리는 Microsoft Defender 바이러스 백신을 실행하는 동안 Windows Server 2016 및 Windows Server 2019에서 크게 동일합니다. 그러나 몇 가지 차이점이 있습니다. 자세한 내용은 [Windows Server 2016 및 2019의 Microsoft Defender 바이러스 백신을 참조합니다.](microsoft-defender-antivirus-on-windows-server.md)

## <a name="see-also"></a>참고 항목

- [Windows Server 2016 및 2019의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-on-windows-server.md)
- [Microsoft Defender 바이러스 백신 관리 및 구성](configuration-management-reference-microsoft-defender-antivirus.md)
- [Microsoft Defender 바이러스 백신 보호 평가](evaluate-microsoft-defender-antivirus.md)