---
title: Azure Defender와 통합
description: Azure Defender와 끝점 통합을 위한 Microsoft Defender에 대해 자세히 알아보시고
keywords: 통합, 서버, azure, 2012r2, 2016, 2019, 서버 온보딩, 장치 관리, 끝점 서버용 Microsoft Defender 구성, 끝점 서버용 Microsoft Defender 온보딩, 끝점 서버용 Microsoft Defender 온보딩
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: mjcaparas
ms.author: macapara
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a702585a558cf6754cbd2eaf23d5061879120ac8
ms.sourcegitcommit: be095345257225394674698beb3feeb0696ec86d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/08/2021
ms.locfileid: "60240628"
---
# <a name="integration-with-azure-defender"></a>Azure Defender와 통합

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- 엔드포인트용 Microsoft Defender
- Azure Defender

끝점용 Microsoft Defender는 Azure Defender와 통합하여 포괄적인 서버 Windows 솔루션을 제공할 수 있습니다. 이 통합을 통해 Azure Defender는 끝점용 Defender의 기능을 사용하여 서버의 위협 감지 기능을 Windows 있습니다.

이 통합에는 다음과 같은 기능이 포함됩니다.

- 자동 온보딩 - Azure Defender에 온보딩된 Windows Endpoint용 Defender 센서가 자동으로 사용하도록 설정됩니다. Azure Defender 온보딩에 대한 자세한 내용은 [통합된 끝점용 Microsoft Defender 라이선스 사용을 참조하세요.](/azure/security-center/security-center-wdatp)

    > [!NOTE]
    > 서버용 Azure Defender와 끝점용 Microsoft Defender 간의 통합은 Windows [Server 2019 및 WVD(가상 데스크톱)Windows](/azure/security-center/release-notes#microsoft-defender-for-endpoint-integration-with-azure-defender-now-supports-windows-server-2019-and-windows-10-virtual-desktop-wvd-in-preview)지원하기 위해 확장되어 있습니다.

- Windows Azure Defender가 모니터링하는 서버는 Endpoint용 Defender에서도 사용할 수 있습니다. Azure Defender는 끝점 테넌트용 Defender에 원활하게 연결하여 클라이언트와 서버 전체에서 단일 보기를 제공합니다.  또한 Azure Defender 콘솔에서 끝점용 Defender 경고를 사용할 수 있습니다.
- 서버 조사 - Azure Defender 고객은 액세스하여 Microsoft Defender 보안 센터 조사를 수행하여 잠재적인 위반 범위를 밝히는 데 사용할 수 있습니다.

> [!IMPORTANT]
> - Azure Defender를 사용하여 서버를 모니터링하면 끝점 테넌트에 대한 Defender가 자동으로 만들어집니다(미국 사용자의 경우 유럽 및 영국 사용자용 EU).<br>
Endpoint용 Defender에서 수집한 데이터는 프로비전 중에 식별된 테넌트의 지리적 위치에 저장됩니다.
> - Azure Defender를 사용하기 전에 Endpoint용 Defender를 사용하는 경우 나중에 Azure Defender와 통합하는 경우에도 테넌트를 만들 때 지정한 위치에 데이터가 저장됩니다.
> - 일단 구성되면 데이터가 저장되는 위치를 변경할 수 없습니다. 데이터를 다른 위치로 이동해야 하는 경우 Microsoft 지원에 문의하여 테넌트를 다시 설정해야 합니다. <br>
이러한 통합을 활용하는 서버 끝점 모니터링은 Office 365 GCC 사용하지 않도록 설정되어 있습니다.



## <a name="related-topics"></a>관련 항목
- [이전 버전의 Windows 온보딩](onboard-downlevel.md)
- [온보 Windows Server 2012 R2, 2016, SAC 버전 1803 및 2019](configure-server-endpoints.md)