---
title: Mac용 끝점용 Microsoft Defender의 라이선스 문제 해결
description: Mac용 끝점용 Microsoft Defender의 라이선스 문제를 해결합니다.
keywords: microsoft, defender, atp, mac, 성능
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 3fb351d9ce8e9beef812e6aaa7d463161a6af8df
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2021
ms.locfileid: "51862190"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-on-macos"></a>macOS에서 끝점용 Microsoft Defender의 라이선스 문제 해결

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**

- [Microsoft Defender for Endpoint(macOS용)](microsoft-defender-endpoint-mac.md)
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 끝점용 Microsoft Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[macOS의 끝점용 Microsoft Defender](microsoft-defender-endpoint-mac.md) 및 [](mac-install-manually.md) 수동 배포 테스트 또는 PoC(개념 증명)를 진행하는 동안 다음 오류가 발생할 수 있습니다.

![라이선스 오류 이미지](images/no-license-found.png)

**메시지:** 

라이선스를 찾을 수 없음

조직에 Microsoft 365 Enterprise 구독에 대한 라이선스가 없는 것 같아야 합니다.

관리자에게 문의하십시오.

**원인:** 

MacOS 패키지("설치 패키지 다운로드")에 끝점용 Microsoft Defender를 배포 및/또는 설치했지만 구성 스크립트("온보딩 패키지 다운로드")를 실행한 것일 수 있습니다.

**해결 방법:**

클라이언트 구성에 MicrosoftDefenderATPOnboardingMacOs.py [지침에 따릅니다.](mac-install-manually.md#client-configuration)

