---
title: Endpoint용 Defender와의 바이러스 백신 솔루션 호환성
description: Microsoft Defender for endpoint에서 Windows Defender 작동하는 방법에 대해 자세히 알아보습니다. 또한 타사 맬웨어 방지 클라이언트를 사용할 때 Endpoint용 Defender가 작동하는 방식도 알아보아야 합니다.
keywords: windows defender 호환성, defender, Endpoint용 Microsoft Defender, 끝점용 Defender, 바이러스 백신, mde
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.date: 05/06/2021
ms.technology: mde
ms.openlocfilehash: f4fd2046e9fdeb7e0832577effb8d445232bb543
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60150261"
---
# <a name="antivirus-solution-compatibility-with-microsoft-defender-for-endpoint"></a>Endpoint용 Microsoft Defender와의 바이러스 백신 솔루션 호환성

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-defendercompat-abovefoldlink)

끝점용 Microsoft Defender 에이전트는 파일 Microsoft Defender 바이러스 백신 같은 일부 기능에 대한 지원 여부에 따라 달라 습니다.

> [!IMPORTANT]
> Endpoint용 Defender는 제외 Microsoft Defender 바이러스 백신 준수하지 않습니다.

맬웨어 방지가 활성 상태인지 여부에 Microsoft Defender 바이러스 백신용 Defender에서 보안 인텔리전스 업데이트를 구성해야 합니다. 자세한 내용은 업데이트 관리 [및 Microsoft Defender 바이러스 백신 적용을 참조하세요.](manage-updates-baselines-microsoft-defender-antivirus.md)

타사 맬웨어 방지 클라이언트로 온보드 장치를 보호하는 경우 해당 끝점에서 Microsoft Defender 바이러스 백신 수동 모드로 전환됩니다.

Microsoft Defender 바이러스 백신 업데이트가 계속 수신되고mspeng.exe 프로세스가 실행 중인 서비스로 나열됩니다. 그러나 검색을 수행하지는 못하며 실행 중인 타사 맬웨어 방지 클라이언트를 대체하지 않습니다.

이 Microsoft Defender 바이러스 백신 사용하지 않도록 설정됩니다. 장치의 사용자는 이 장치를 사용하여 Microsoft Defender 바이러스 백신 또는 대부분의 옵션을 구성할 수 없습니다.

자세한 내용은 끝점 호환성 [Microsoft Defender 바이러스 백신 및 Defender를 참조하세요.](microsoft-defender-antivirus-compatibility.md)
