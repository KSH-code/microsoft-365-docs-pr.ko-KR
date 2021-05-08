---
title: Microsoft Defender 바이러스 백신 배포 및 사용
description: Microsoft Intune, Microsoft Endpoint Configuration Manager, 그룹 정책, PowerShell cmdlet 또는 WMI를 통해 끝점 보호를 위해 Microsoft Defender 바이러스 백신을 배포합니다.
keywords: 배포, 사용, Microsoft Defender 바이러스 백신
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 01/06/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 88a5401818c3d6f2b35675830a38b266db9627e4
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274499"
---
# <a name="deploy-and-enable-microsoft-defender-antivirus"></a>Microsoft Defender 바이러스 백신 배포 및 사용

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

사용하는 관리 도구에 따라 Microsoft Defender 바이러스 백신 보호를 사용하도록 설정하거나 구성해야 할 수 있습니다. 

Microsoft Intune, Microsoft Endpoint Configuration Manager, 그룹 정책, Active Directory, Microsoft Azure, PowerShell cmdlet 및 WMI(Windows Management Instruction)를 사용하여 보호를 사용하도록 설정하는 방법에 대한 지침은 [Microsoft Defender](deploy-manage-report-microsoft-defender-antivirus.md#ref2) 바이러스 백신 배포, 관리 및 보고의 표를 참조하세요.

일부 시나리오에서는 VDI(가상 데스크톱 인프라) 환경과 같은 Microsoft Defender 바이러스 백신 보호를 성공적으로 배포하거나 구성하는 방법에 대한 추가 지침이 필요합니다.

이 섹션의 나머지 문서에서는 VDI 또는 [RDS(원격](deployment-vdi-microsoft-defender-antivirus.md)데스크톱 서비스) 환경에서 VM(가상 컴퓨터)에 Microsoft Defender 바이러스 백신을 설정하는 데 대한 종단적인 조언과 모범 사례를 제공합니다.

## <a name="related-articles"></a>관련 문서

- [Windows 10의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender 바이러스 백신 배포, 업데이트 관리 및 보고](deploy-manage-report-microsoft-defender-antivirus.md)
- [VDI(가상 데스크톱 인프라) 환경에서 Microsoft Defender 바이러스 백신의 배포 가이드](deployment-vdi-microsoft-defender-antivirus.md)