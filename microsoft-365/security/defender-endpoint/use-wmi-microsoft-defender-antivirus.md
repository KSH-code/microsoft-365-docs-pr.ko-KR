---
title: WMI를 통해 Microsoft Defender 바이러스 백신 구성
description: WMI 스크립트를 사용하여 끝점용 Microsoft Defender의 설정을 검색, 수정 및 업데이트하여 Microsoft Defender 바이러스 백신을 구성하고 관리하는 방법을 학습합니다.
keywords: wmi, 스크립트, Windows 관리 계측, 구성
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 8d24a08ae3b8db710ca1727821690e5c87f056c3
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691163"
---
# <a name="use-windows-management-instrumentation-wmi-to-configure-and-manage-microsoft-defender-antivirus"></a>WMI(Windows Management Instrumentation)를 사용하여 Microsoft Defender 바이러스 백신 구성 및 관리

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/) 

WMI(Windows Management Instrumentation)는 설정을 검색, 수정 및 업데이트할 수 있는 스크립팅 인터페이스입니다.

WMI에 대한 자세한 내용은 시스템 Microsoft Developer Network [라이브러리를 읽어 보십시오.](/windows/win32/wmisdk/wmi-start-page)

Microsoft Defender 바이러스 백신에는 그룹 정책 및 기타 관리 도구와 동일한 대부분의 기능을 수행하는 데 사용할 수 있는 다양한 특정 WMI 클래스가 있습니다. 대부분의 클래스는 [Defender PowerShell cmdlet과 유사합니다.](use-powershell-cmdlets-microsoft-defender-antivirus.md)

[MSDN Windows Defender WMIv2 공급자](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) 참조 라이브러리에는 Microsoft Defender 바이러스 백신에 사용할 수 있는 WMI 클래스가 나열되어 있으며 예제 스크립트가 포함되어 있습니다.

WMI를 사용하여 변경한 내용은 변경 내용이 배포되거나 적용된 끝점의 로컬 설정에 영향을 미치게 됩니다. 즉, 그룹 정책, Microsoft Endpoint Configuration Manager 또는 Microsoft Intune을 사용하여 정책을 배포하면 WMI로 변경한 내용을 덮어 사용할 수 있습니다. 

로컬 정책 다시 설정으로 로컬로 다시 정할 수 있는 설정을 [구성할 수 있습니다.](configure-local-policy-overrides-microsoft-defender-antivirus.md)

## <a name="related-topics"></a>관련 항목

- [관리 및 구성 도구에 대한 참조 항목](configuration-management-reference-microsoft-defender-antivirus.md)
- [Windows 10의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-in-windows-10.md)