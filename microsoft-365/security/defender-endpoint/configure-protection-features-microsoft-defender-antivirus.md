---
title: Microsoft Defender 바이러스 백신 보호 기능 사용 및 구성
description: Microsoft Defender AV에서 동작 기반, 방어적 및 실시간 보호를 사용하도록 설정할 수 있습니다.
keywords: 맬웨어 방지, 기계 학습, 동작 모니터, 실시간 보호, 항상 사용, Microsoft Defender 바이러스 백신, 맬웨어 방지, 보안, Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 7a0e0571445e8ec753c3813a81dbcca9c698e7df
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690880"
---
# <a name="configure-behavioral-heuristic-and-real-time-protection"></a>동작,추론적 및 실시간 보호 구성

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/) 

Microsoft Defender 바이러스 백신은 여러 가지 방법을 사용하여 위협 방지를 제공합니다.

- 새로운 위협의 거의 즉각적인 탐지 및 차단을 위한 클라우드 제공 보호
- 파일 및 프로세스 동작 모니터링 및 기타추론("실시간 보호"라고도 알려지기)을 사용하는 항상 검사
- 기계 학습, 인간 및 자동화된 대규모 데이터 분석 그리고 심층 위협 저항 연구를 기반으로 하는 전용 보호 업데이트

Microsoft Defender 바이러스 백신에서 그룹 정책, System Center Configuration Manage, PowerShell cmdlet 및 WMI(Windows Management Instrumentation)를 사용하여 이러한 방법을 사용하는 방법을 구성할 수 있습니다.

이 섹션에서는 안전하지 않은 것으로 보이지만 맬웨어로 검색되지 않을 수 있는 앱을 검색하고 차단하는 방법을 포함하여 항상 실행되는 검사에 대한 구성에 대해 설명합니다.

Microsoft Defender 바이러스 백신 클라우드 제공 보호를 사용하도록 설정하고 구성하는 방법에 대한 자세한 내용은 클라우드 제공 보호를 통해 차세대 [Microsoft Defender](cloud-protection-microsoft-defender-antivirus.md) 바이러스 백신 기술 사용을 참조합니다.

## <a name="in-this-section"></a>이 섹션의 내용

 항목 | 설명
---|---
[잠재적으로 원치 않는 응용 프로그램 검색 및 차단](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md) | 애드웨어, 브라우저 수정자 및 도구 모음, 악성 또는 가짜 바이러스 백신 앱 등 네트워크에서 원치 않는 앱을 검색하고 차단합니다.
[Microsoft Defender 바이러스 백신 보호 기능 사용 및 구성](configure-real-time-protection-microsoft-defender-antivirus.md) | 실시간 보호,추론 및 기타 항상 Microsoft Defender 바이러스 백신 모니터링 기능 사용 및 구성