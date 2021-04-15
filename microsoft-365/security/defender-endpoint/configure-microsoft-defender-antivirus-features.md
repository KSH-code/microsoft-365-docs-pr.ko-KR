---
title: Microsoft Defender 바이러스 백신 기능 구성
description: Intune, Microsoft Endpoint Configuration Manager, 그룹 정책 및 PowerShell을 사용하여 Microsoft Defender 바이러스 백신 기능을 구성할 수 있습니다.
keywords: Microsoft Defender 바이러스 백신, 맬웨어 방지, 보안, defender, 구성, 구성, Config Manager, Microsoft Endpoint Configuration Manager, SCCM, Intune, MDM, 모바일 장치 관리, GP, 그룹 정책, PowerShell
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/18/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 8503bb5bdd6337ec60390ef1d8e59f6f506fbce2
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765170"
---
# <a name="configure-microsoft-defender-antivirus-features"></a>Microsoft Defender 바이러스 백신 기능 구성

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/) 

다음을 비롯한 다양한 도구를 사용하여 Microsoft Defender 바이러스 백신을 구성할 수 있습니다.

- Microsoft Intune
- Microsoft Endpoint Configuration Manager
- 그룹 정책
- PowerShell cmdlet
- WMI(Windows Management Instrumentation)

다음과 같은 광범위한 기능 범주를 구성할 수 있습니다.

- 클라우드 제공 보호
- 동작, 학습 및 기계 학습 기반 보호를 비롯한 항상 실시간 보호
- 최종 사용자가 개별 끝점에서 클라이언트와 상호 작용하는 방법

다음 문서에서는 Microsoft Defender 바이러스 백신을 구성할 때 주요 작업을 수행하는 방법을 설명합니다. 각 문서에는 해당 구성 도구(또는 도구)에 대한 지침이 포함되어 있습니다.

|문서  |설명  |
|---------|---------|
|[Microsoft 클라우드 제공 Microsoft Defender 바이러스 백신 보호 활용](cloud-protection-microsoft-defender-antivirus.md)     | 빠르고 강력한 바이러스 백신 탐지를 위해 클라우드 제공 보호를 사용 합니다.        |
|[동작,추론적 및 실시간 보호 구성](configure-protection-features-microsoft-defender-antivirus.md)     |동작 기반,추론적 및 실시간 바이러스 백신 보호를 사용하도록 설정         |
|[Microsoft Defender 바이러스 백신과 최종 사용자 상호 작용 구성](configure-end-user-interaction-microsoft-defender-antivirus.md) | 조직의 최종 사용자가 Microsoft Defender 바이러스 백신과 상호 작용하는 방법, 사용자에게 어떤 알림이 표시될지, 설정을 오버라이드할 수 있는지 여부를 구성합니다. |

> [!TIP]
> 또한 관리 및 구성 도구에 대한 [참조](configuration-management-reference-microsoft-defender-antivirus.md) 항목을 검토하여 각 도구에 대한 개요와 추가 도움말에 대한 링크를 확인할 수 있습니다.