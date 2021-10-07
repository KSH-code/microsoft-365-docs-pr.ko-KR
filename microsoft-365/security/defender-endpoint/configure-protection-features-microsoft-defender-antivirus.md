---
title: 보안 보호 Microsoft Defender 바이러스 백신 사용 및 구성
description: Microsoft Defender AV에서 동작 기반, 방어적 및 실시간 보호를 사용하도록 설정할 수 있습니다.
keywords: 맬웨어 방지, 기계 학습, 동작 모니터, 실시간 보호, 무중단, Microsoft Defender 바이러스 백신, 맬웨어 방지, 보안, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.collection: M365-security-compliance
ms.openlocfilehash: beb7b022bd8e0dbd9296e18cbc4befa19690e492
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60212560"
---
# <a name="configure-behavioral-heuristic-and-real-time-protection"></a>동작, 추론 및 실시간 보호 구성


**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

Microsoft Defender 바이러스 백신 여러 가지 방법을 사용하여 위협 방지를 제공합니다.

- 새로운 위협의 거의 즉각적인 탐지 및 차단을 위한 클라우드 보호
- 파일 및 프로세스 동작 모니터링 및 기타추론("실시간 보호"라고도 알려지기)을 사용하는 항상 검사
- 기계 학습, 인간 및 자동화된 대규모 데이터 분석 그리고 심층 위협 저항 연구를 기반으로 하는 전용 보호 업데이트

그룹 정책, Microsoft Defender 바이러스 백신, PowerShell cmdlet 및 WMI(System Center Management Instrumentation)를 사용하여 이러한 Windows 구성할 수 있습니다.

이 섹션에서는 안전하지 않은 것으로 보이지만 맬웨어로 검색되지 않을 수 있는 앱을 검색하고 차단하는 방법을 포함하여 항상 실행되는 검사에 대한 구성에 대해 설명합니다.

클라우드 [보호를 사용하도록 설정하고 구성하는 Microsoft Defender 바이러스 백신](cloud-protection-microsoft-defender-antivirus.md) 클라우드 보호를 통해 차세대 Microsoft Defender 바이러스 백신 사용을 참조합니다.

## <a name="in-this-section"></a>이 섹션의 내용

| 항목|설명 |
|---|---|
| [잠재적으로 원하지 않는 응용 프로그램 검색 및 차단](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md)| 애드웨어, 브라우저 수정자 및 도구 모음, 악성 또는 가짜 바이러스 백신 앱 등 네트워크에서 원치 않는 앱을 검색하고 차단합니다. |
| [보안 보호 기능 Microsoft Defender 바이러스 백신 사용 및 구성](configure-real-time-protection-microsoft-defender-antivirus.md)|실시간 보호,추론 및 기타 상시 모니터링 기능 사용 Microsoft Defender 바이러스 백신 구성 |
