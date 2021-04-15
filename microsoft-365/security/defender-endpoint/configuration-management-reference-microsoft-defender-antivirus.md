---
title: 비즈니스 Windows Defender 관리
description: 그룹 정책, Configuration Manager, PowerShell, WMI, Intune 및 명령줄을 사용하여 Microsoft Defender AV를 관리하는 방법을 학습합니다.
keywords: 그룹 정책, gpo, 구성 관리자, sccm, scep, powershell, wmi, intune, defender, 바이러스 백신, 맬웨어 방지, 보안, 보호
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/16/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 6b9845812763f9e3f1fdecf5566824eb76971dad
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764870"
---
# <a name="manage-microsoft-defender-antivirus-in-your-business"></a>비즈니스에서 Microsoft Defender 바이러스 백신 관리

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/) 

다음 도구를 사용하여 Microsoft Defender 바이러스 백신을 관리하고 구성할 수 있습니다.

- [Microsoft Intune(현재](/mem/intune/protect/endpoint-security-antivirus-policy) Microsoft Endpoint Manager의 일부)
- [Microsoft Endpoint Configuration Manager(현재](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) Microsoft Endpoint Manager의 일부)
- [그룹 정책](./use-group-policy-microsoft-defender-antivirus.md)
- [PowerShell cmdlet](./use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [WMI(Windows Management Instrumentation)](./use-wmi-microsoft-defender-antivirus.md)
- [Microsoft 맬웨어 보호 명령줄 유틸리티(mpcmdrun.exe](./command-line-arguments-microsoft-defender-antivirus.md) 유틸리티라고도 합니다. 

다음 문서에서는 이러한 도구를 사용하여 Microsoft Defender 바이러스 백신을 관리 및 구성하기 위한 추가 정보, 링크 및 리소스를 제공합니다.

| 문서 | 설명 |
|:---|:---|
|[Microsoft Intune 및 Microsoft Endpoint Configuration Manager를 사용하여 Microsoft Defender 바이러스 백신 관리](use-intune-config-manager-microsoft-defender-antivirus.md)|Intune 및 Configuration Manager를 사용하여 Microsoft Defender 바이러스 백신 배포, 관리, 보고 및 구성에 대한 정보 |
|[그룹 정책 설정을 사용하여 Microsoft Defender 바이러스 백신 관리](use-group-policy-microsoft-defender-antivirus.md)|ADMX 템플릿에 있는 모든 그룹 정책 설정 목록 |
|[PowerShell cmdlet을 사용하여 Microsoft Defender 바이러스 백신 관리](use-powershell-cmdlets-microsoft-defender-antivirus.md)|PowerShell cmdlet을 사용하여 Microsoft Defender 바이러스 백신을 관리하기 위한 지침과 모든 cmdlet 및 허용되는 매개 변수에 대한 설명서 링크 |
|[WMI(Windows Management Instrumentation)를 사용하여 Microsoft Defender 바이러스 백신 관리](use-wmi-microsoft-defender-antivirus.md)| WMI를 사용하여 Microsoft Defender 바이러스 백신을 관리하는 지침과 WMIv2 API에 대한 설명서 링크(모든 클래스, 메서드 및 속성 포함) |
|[명령줄 도구를 사용하여 Microsoft Defender mpcmdrun.exe 관리](command-line-arguments-microsoft-defender-antivirus.md)|전용 명령줄 도구를 사용하여 Microsoft Defender 바이러스 백신 관리 및 사용 지침 |