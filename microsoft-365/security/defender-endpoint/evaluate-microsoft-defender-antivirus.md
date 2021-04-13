---
title: Microsoft Defender 바이러스 백신 평가
description: 모든 크기의 기업은 이 가이드를 사용하여 Windows 10에서 Microsoft Defender 바이러스 백신이 제공하는 보호를 평가하고 테스트할 수 있습니다.
keywords: Microsoft Defender 바이러스 백신, 클라우드 보호, 클라우드, 맬웨어 방지, 보안, defender, 평가, 테스트, 보호, 비교, 실시간 보호
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: de9c7e845188f47ab5b8e1f9d97871ea36340d19
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691469"
---
# <a name="evaluate-microsoft-defender-antivirus"></a>Microsoft Defender 바이러스 백신 평가

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/) 

이 가이드를 사용하여 Microsoft Defender 바이러스 백신이 바이러스, 맬웨어 및 잠재적으로 원치 않는 응용 프로그램으로부터 보호하는 방법을 확인할 수 있습니다.

>[!TIP]
>Microsoft Defender for [Endpoint](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 데모 웹 사이트를 방문하여 demo.wd.microsoft.com 작동을 확인하고 작동 방법을 확인할 수 있습니다.
>- 클라우드 제공 보호
>- 빠른 학습(신속한 차단 포함)
>- 잠재적으로 원치 않는 응용 프로그램 차단

또한 중소기업과 대기업 둘 다에서 사용할 수 있는 Microsoft Defender 바이러스 백신의 중요한 차세대 보호 기능과 네트워크에서 맬웨어 감지 및 보호를 강화하는 방법에 대해 설명하고 있습니다.

각 설정을 독립적으로 구성 및 평가하도록 선택하거나 한 번씩 모두 평가할 수 있습니다. 일반적인 평가 시나리오에 따라 유사한 설정을 그룹화하고 PowerShell을 사용하여 설정을 사용하도록 설정하기 위한 지침을 포함합니다.

이 가이드는 오프라인에서 볼 수 있도록 PDF 형식으로 제공됩니다.

- [PDF 형식으로 가이드 다운로드](https://www.microsoft.com/download/details.aspx?id=54795)

가이드에 설명된 모든 설정을 자동으로 사용하도록 설정하는 PowerShell을 다운로드할 수 있습니다. 위의 PDF 다운로드와 함께 또는 PowerShell 갤러리에서 개별적으로 스크립트를 얻을 수 있습니다.

- [PowerShell 스크립트를 다운로드하여 설정 자동 구성](https://www.powershellgallery.com/packages/WindowsDefender_InternalEvaluationSettings)

> [!IMPORTANT]
> 이 가이드는 현재 Microsoft Defender 바이러스 백신의 단일 컴퓨터 평가를 위한 것입니다. 이 가이드의 모든 설정을 사용하도록 설정하는 것은 실제 배포에 적합하지 않을 수 있습니다.
>
> 네트워크에서 Microsoft Defender 바이러스 백신의 실제 배포 및 모니터링에 대한 최신 권장 사항은 Microsoft Defender 바이러스 백신 [배포를 참조하세요.](deploy-manage-report-microsoft-defender-antivirus.md)

## <a name="related-topics"></a>관련 항목

- [Windows 10의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender 바이러스 백신 배포](deploy-manage-report-microsoft-defender-antivirus.md)