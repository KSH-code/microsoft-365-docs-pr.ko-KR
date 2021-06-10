---
title: 하드웨어 기반 Windows 10)
ms.reviewer: ''
description: 맬웨어를 방지하는 데 도움이 되는 하드웨어 기반 Windows 10 대해 자세히 알아보습니다.
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.author: macapara
ms.date: 09/07/2018
ms.technology: mde
ms.openlocfilehash: b3babf858ac19e70119a2dc6a58b25359f1b05c1
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842989"
---
# <a name="hardware-based-isolation-in-windows-10"></a>Windows 10의 하드웨어 기반 격리

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 끝점용 Microsoft Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


하드웨어 기반의 고르지 Windows 10 시스템 무결성을 보호하고 끝점용 Microsoft Defender와 통합됩니다. 

| 기능 | 설명 |
|------------|-------------|
| [Windows Defender Application Guard](/windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview.md) | Application Guard는 생산성을 유지하면서 고급 공격으로부터 장치를 보호합니다. 고유한 하드웨어 기반 격리 방식을 사용하는 목적은 기본 하이퍼바이저를 통해 운영 체제와 분리된 경량 컨테이너 내에서 트러스트되지 않은 웹 사이트와 PDF 문서를 격리하는 Windows 것입니다. 트러스터가 악의적인 것으로 확인된 사이트 또는 PDF 문서는 여전히 Application Guard의 보안 컨테이너 내에 포함되어 데스크톱 PC를 보호하고 공격자가 엔터프라이즈 데이터에서 멀어지게 합니다. |
| [Windows Defender System Guard](/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows.md) | System Guard는 시스템 시작 및 실행 후 시스템의 무결성을 보호하고 유지 관리하며, 의거를 사용하여 시스템 무결성의 유효성을 검사합니다.  |

