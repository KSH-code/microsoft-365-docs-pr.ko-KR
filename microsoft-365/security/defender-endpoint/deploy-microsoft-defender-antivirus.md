---
title: Microsoft Defender 바이러스 백신 배포 및 사용
description: Microsoft Defender 바이러스 백신, 그룹 정책, Microsoft Endpoint Configuration Manager, PowerShell cmdlet 또는 WMI를 Microsoft Intune 끝점 보호를 위해 배포합니다.
keywords: 배포, 사용, Microsoft Defender 바이러스 백신
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 01/06/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: a847e65adb0402d4c5f98e19424677ccdc1011da
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59220615"
---
# <a name="deploy-and-enable-microsoft-defender-antivirus"></a>Microsoft Defender 바이러스 백신 배포 및 사용

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

사용 하는 관리 도구에 따라 특별히 사용 하도록 설정 또는 구성 해야 할 Microsoft Defender 바이러스 백신 있습니다. 

Microsoft Intune, Microsoft Defender 바이러스 백신 [](deploy-manage-report-microsoft-defender-antivirus.md#ref2) Microsoft Endpoint Configuration Manager, 그룹 정책, Active Directory, Microsoft Azure, PowerShell cmdlet 및 WMI(Windows Management Instruction)를 사용하여 보호를 사용하도록 설정하는 방법에 대한 지침은 배포, 관리 및 보고의 표를 참조하세요.

일부 시나리오에서는 VDI(가상 데스크톱 인프라) 환경과 같은 Microsoft Defender 바이러스 백신 보호를 성공적으로 배포하거나 구성하는 방법에 대한 추가 지침이 필요합니다.

이 섹션의 나머지 문서에서는 VDI 또는 [RDS(원격](deployment-vdi-microsoft-defender-antivirus.md)데스크톱 서비스) 환경에서 VM(가상 Microsoft Defender 바이러스 백신)을 설정하기 위한 전체적인 조언과 모범 사례를 제공합니다.

## <a name="related-articles"></a>관련 문서

- [Windows 10의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-in-windows-10.md)
- [업데이트 배포, 관리 및 보고서 Microsoft Defender 바이러스 백신](deploy-manage-report-microsoft-defender-antivirus.md)
- [VDI(가상 데스크톱 인프라) 환경에서 Microsoft Defender 바이러스 백신의 배포 가이드](deployment-vdi-microsoft-defender-antivirus.md)