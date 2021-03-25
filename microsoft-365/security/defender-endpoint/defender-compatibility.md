---
title: Endpoint용 Defender와의 Microsoft Defender 바이러스 백신 호환성
description: Microsoft Defender for Windows Defender 작동하는 방법과 타사 맬웨어 방지 클라이언트를 사용할 때 해당 기능이 작동하는 방법에 대해 자세히 알아보습니다.
keywords: windows defender 호환성, defender, Microsoft Defender atp, 끝점용 defender, 바이러스 백신, mde
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 63dca2694dae5dee924c9a0a02a660003907c42b
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165961"
---
# <a name="microsoft-defender-antivirus-compatibility-with-microsoft-defender-for-endpoint"></a>끝점용 Microsoft Defender와의 Microsoft Defender 바이러스 백신 호환성

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Endpoint용 Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-defendercompat-abovefoldlink)

끝점용 Microsoft Defender 에이전트는 파일 검색과 같은 일부 기능에 대해 Microsoft Defender 바이러스 백신에 의존합니다.

>[!IMPORTANT]
>Endpoint용 Defender는 Microsoft Defender 바이러스 백신 제외 설정을 준수하지 않습니다. 

Microsoft Defender 바이러스 백신이 활성 맬웨어 방지인지 여부에 관계 없는 경우 끝점 장치용 Defender에서 보안 인텔리전스 업데이트를 구성해야 합니다. 자세한 내용은 Microsoft Defender 바이러스 백신 업데이트 관리 및 [기준 적용을 참조하세요.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus.md)

타사 맬웨어 방지 클라이언트에 의해 온보딩된 장치가 보호되는 경우 해당 끝점의 Microsoft Defender 바이러스 백신이 수동 모드로 전환됩니다.

Microsoft Defender *바이러스* 백신은 계속 업데이트를 수신하며mspeng.exe프로세스는 실행 중인 서비스로 나열되지만 검색을 수행하지는 못하며 실행 중인 타사 맬웨어 방지 클라이언트를 대체하지 않습니다.

Microsoft Defender 바이러스 백신 인터페이스가 비활성화되어 장치의 사용자가 Microsoft Defender 바이러스 백신을 사용하여 요구 시 검사 또는 대부분의 옵션을 구성할 수 없습니다.

자세한 내용은 Microsoft [Defender 바이러스 백신 및 Endpoint 호환성을 위한 Defender 항목을 참조하세요.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)
