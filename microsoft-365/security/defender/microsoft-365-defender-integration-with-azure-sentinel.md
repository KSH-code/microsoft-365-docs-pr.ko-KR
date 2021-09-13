---
title: Microsoft 365 Defender와 Azure Sentinel 통합
description: Azure Sentinel을 인시던트 및 이벤트에 대한 SIEM으로 Microsoft 365 Defender 사용하세요.
keywords: 인시던트, 경고, 조사, 분석, 대응, 상관 관계, 공격, 컴퓨터, 장치, 사용자, ID, ID, 사서함, 전자 메일, 365, Microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: d7982e8a8c320336a47cd64152b5477be7ae51f5
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59185683"
---
# <a name="microsoft-365-defender-integration-with-azure-sentinel"></a>Microsoft 365 Defender와 Azure Sentinel 통합

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**적용 대상:**
- Microsoft 365 Defender

Azure Sentinel용 Microsoft 365 Defender 커넥터(미리 보기)는 모든 Microsoft 365 Defender 인시던트 및 경고 정보를 Azure Sentinel로 보내고 인시던트가 동기화된 상태입니다. 

커넥터를 추가하고 나면 Endpoint용 Microsoft Defender, ID용 Microsoft Defender, Office 365용 Microsoft Defender 및 Microsoft Cloud App Security에서 받은 모든 관련 경고, 엔터티 및 관련 정보가 포함된 인시던트가 Azure &mdash; Sentinel에 SIEM(보안 정보 및 이벤트 관리) 데이터로 스트리밍되어 Azure Sentinel을 통해 평가 및 인시던트 대응을 수행할 수 있는 컨텍스트를 &mdash; 제공합니다. Microsoft 365 Defender 

Azure Sentinel에서 인시던트는 Microsoft 365 Defender 양방향으로 동기화된 상태로 유지되므로 인시던트 조사 및 대응을 위해 Azure Portal에서 Microsoft 365 Defender 포털 및 Azure Sentinel의 이점을 활용할 수 있습니다.

Azure Sentinel과 Azure Sentinel의 통합에 대한 이 Microsoft 365 Defender(4분)를 시청하세요.

<br>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWFIRo]


작동 방식은 다음과 있습니다.

:::image type="content" source="../../media/microsoft-365-defender-integration-with-azure-sentinel/microsoft-365-defender-integration-with-azure-sentinel.png" alt-text="Azure Sentinel과 Azure Sentinel 간의 인시던트 Microsoft 365 Defender 흐름 및 공유":::

## <a name="next-steps"></a>다음 단계

1. [Azure Sentinel과 Microsoft 365 Defender 통합에 대한 심층적인 이해를 얻습니다.](/azure/sentinel/microsoft-365-defender-sentinel-integration)
2. [커넥트 Azure Sentinel Microsoft 365 Defender 데이터를 저장합니다.](/azure/sentinel/connect-microsoft-365-defender)

## <a name="see-also"></a>참고 항목

- [계획의 인시던트 Microsoft 365 Defender](incidents-overview.md)
- [Azure Sentinel로 인시던트 조사](/azure/sentinel/tutorial-investigate-cases)
