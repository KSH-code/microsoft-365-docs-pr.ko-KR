---
title: 끝점용 Microsoft Defender와 다른 Microsoft 솔루션 통합
description: Id용 Microsoft Defender 및 Azure 보안 센터를 포함하여 끝점용 Microsoft Defender가 다른 Microsoft 솔루션과 통합되는 방법을 설명합니다.
author: mjcaparas
ms.author: macapara
ms.prod: m365-security
keywords: Microsoft 365 defender, 조건부 액세스, Office, 고급 위협 방지, ID에 대한 Microsoft Defender, Office용 Microsoft Defender, Azure 보안 센터, Microsoft 클라우드 앱 보안, azure sentinel
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 7d12afd27288655f4f5a82eeed24686f27171a7a
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765398"
---
# <a name="microsoft-defender-for-endpoint-and-other-microsoft-solutions"></a>끝점용 Microsoft Defender 및 기타 Microsoft 솔루션

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037) 
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 끝점용 Microsoft Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="integrate-with-other-microsoft-solutions"></a>다른 Microsoft 솔루션과 통합

끝점용 Microsoft Defender는 다양한 Microsoft 솔루션과 직접 통합됩니다.

### <a name="azure-security-center"></a>Azure Security Center
끝점용 Microsoft Defender는 Windows Server의 끝점 감지 및 응답(EDR) 기능을 포함하여 포괄적인 서버 보호 솔루션을 제공합니다.

### <a name="azure-sentinel"></a>Azure Sentinel
끝점용 Microsoft Defender 커넥터를 사용하면 끝점용 Microsoft Defender의 경고를 Azure Sentinel로 스트리밍할 수 있습니다. 이를 통해 조직 전체의 보안 이벤트를 보다 포괄적으로 분석하고 효과적이고 즉각적인 응답을 위해 플레이북을 빌드할 수 있습니다.

### <a name="azure-information-protection"></a>Azure Information Protection
Endpoint DLP 기능이 끝점 디바이스에 저장된 중요한 데이터에 대한 향상된 검색 및 보호 솔루션을 통합하여 솔루션 간의 가시성과 통합을 용이하게 하도록 지원하기 때문에 최근에 Azure Information Protection 통합이 더 이상 사용되지 않습니다. 이 사실은 다음 블로그에서 [발표했습니다.](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protecting-sensitive-information-on-devices/ba-p/2143555) 고객이 끝점 DLP를 사용하여 이동하는 것이 좋습니다.

### <a name="conditional-access"></a>조건부 액세스
끝점용 Microsoft Defender의 동적 장치 위험 점수는 조건부 액세스 평가에 통합되어 보안 장치만 리소스에 액세스할 수 있도록 합니다. 

### <a name="microsoft-cloud-app-security"></a>Microsoft Cloud App Security
Microsoft Cloud App Security는 끝점용 Microsoft Defender 끝점 신호를 활용하여 모든 끝점 모니터링 디바이스에서 지원되지 않는 클라우드 서비스(섀도 IT)를 사용하는 등 클라우드 응용 프로그램 사용을 직접 볼 수 있도록 합니다.

### <a name="microsoft-defender-for-identity"></a>ID용 Microsoft Defender
의심스러운 활동은 사용자 컨텍스트에서 실행되는 프로세스입니다. 끝점용 Microsoft Defender와 Azure ATP의 통합을 통해 활동 및 ID 간에 사이버 보안 조사를 유연하게 진행할 수 있습니다.

### <a name="microsoft-defender-for-office"></a>Microsoft Defender for Office
[Defender for Office 365는](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) ATP 안전한 링크, ATP 안전한 첨부 파일, 고급 피싱 방지 및 스푸핑 인텔리전스 기능을 통해 전자 메일 메시지 또는 파일의 맬웨어로부터 조직을 보호합니다. Office 365 ATP와 Microsoft Defender for Endpoint의 통합을 통해 보안 분석가가 공격 진입점을 조사할 수 있습니다. 위협 인텔리전스 공유를 통해 공격을 포함하고 차단할 수 있습니다. 

>[!NOTE]
> 지난 30일 이내에 이벤트에 대해 Office 365용 Defender가 표시됩니다. 경고의 경우 Office 365용 Defender 데이터가 첫 번째 활동 시간을 기준으로 표시됩니다. 그런 다음 Office 365용 Defender에서 더 이상 데이터를 사용할 수 없습니다.

### <a name="skype-for-business"></a>비즈니스용 Skype
비즈니스용 Skype 통합은 분석가가 포털에서 간단한 단추를 통해 잠재적으로 손상된 사용자 또는 장치 소유자와 통신할 수 있는 방법을 제공합니다.

## <a name="microsoft-365-defender"></a>Microsoft 365 Defender
Microsoft 365 Defender를 통해 Endpoint용 Microsoft Defender 및 다양한 Microsoft 보안 솔루션은 엔드포인트, ID, 전자 메일 및 응용 프로그램 전반에 걸쳐 기본적으로 통합되는 통합 사전 및 사후 침해 엔터프라이즈 방어 제품군을 형성하여 정교한 공격을 감지, 방지, 조사 및 자동으로 대응합니다. 
 
[Microsoft 365 Defender에 대해 자세히 알아보시고](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)


## <a name="related-topics"></a>관련 항목
- [통합 및 기타 고급 기능 구성](advanced-features.md)
- [Microsoft 365 Defender 개요](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)
- [Microsoft 365 Defender 켜기](https://docs.microsoft.com/microsoft-365/security/defender/mtp-enable)
- [조건부 액세스를 사용하여 사용자, 데이터 및 장치 보호](conditional-access.md)
