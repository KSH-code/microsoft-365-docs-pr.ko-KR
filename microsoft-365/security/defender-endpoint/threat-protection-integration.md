---
title: 끝점용 Microsoft Defender와 다른 Microsoft 솔루션 통합
description: Id용 Microsoft Defender 및 Azure Defender를 포함하여 끝점용 Microsoft Defender가 다른 Microsoft 솔루션과 통합되는 방법을 알아보십시오.
author: mjcaparas
ms.author: macapara
ms.prod: m365-security
keywords: Microsoft 365 defender, 조건부 액세스, office, 끝점용 Microsoft Defender, ID용 Microsoft Defender, Office용 Microsoft Defender, Azure Defender, Microsoft 클라우드 앱 보안, azure sentinel
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
ms.openlocfilehash: 8f842c46f87e51d026f1e1793e3cc73d25b0739c
ms.sourcegitcommit: 4740e69326eb7f8302eec7bab5bd516d498e4492
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/16/2021
ms.locfileid: "59400645"
---
# <a name="microsoft-defender-for-endpoint-and-other-microsoft-solutions"></a>끝점용 Microsoft Defender 및 기타 Microsoft 솔루션

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="integrate-with-other-microsoft-solutions"></a>다른 Microsoft 솔루션과 통합

끝점용 Microsoft Defender는 다양한 Microsoft 솔루션과 직접 통합됩니다.

### <a name="azure-defender"></a>Azure Defender

끝점용 Microsoft Defender는 EDR 서버의 엔드포인트 감지 및 응답(EDR) 기능을 포함하여 포괄적인 서버 보호 솔루션을 Windows 제공합니다.

### <a name="azure-sentinel"></a>Azure Sentinel

끝점용 Microsoft Defender 커넥터를 사용하면 끝점용 Microsoft Defender의 경고를 Azure Sentinel로 스트리밍할 수 있습니다. 이를 통해 조직 전체의 보안 이벤트를 보다 포괄적으로 분석하고 효과적이고 즉각적인 응답을 위해 플레이북을 빌드할 수 있습니다.

### <a name="azure-information-protection"></a>Azure Information Protection

Endpoint DLP 기능이 끝점 디바이스에 저장된 중요한 데이터에 대한 향상된 검색 및 보호 솔루션을 통합하여 솔루션 간의 가시성과 통합을 용이하게 하도록 지원하기 때문에 최근에 Azure Information Protection 통합이 더 이상 사용되지 않습니다. 이 사실은 다음 블로그에서 [발표했습니다.](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protecting-sensitive-information-on-devices/ba-p/2143555) 고객이 끝점 DLP를 사용하여 이동하는 것이 좋습니다.

### <a name="conditional-access"></a>조건부 액세스

끝점용 Microsoft Defender의 동적 장치 위험 점수는 조건부 액세스 평가에 통합되어 보안 장치만 리소스에 액세스할 수 있도록 합니다.

### <a name="microsoft-cloud-app-security"></a>Microsoft Cloud App Security

Microsoft Cloud App Security Microsoft Defender for Endpoint 신호를 활용하여 엔드포인트 모니터링 장치에 대해 모든 Microsoft Defender에서 지원되지 않는 클라우드 서비스(섀도 IT)를 사용하는 등 클라우드 응용 프로그램 사용을 직접 볼 수 있도록 합니다.

### <a name="microsoft-defender-for-identity"></a>Microsoft Defender for Identity

의심스러운 활동은 사용자 컨텍스트에서 실행되는 프로세스입니다. 끝점용 Microsoft Defender와 ID용 Microsoft Defender의 통합은 활동 및 ID 간에 사이버 보안 조사를 유연하게 진행할 수 있도록 합니다.

### <a name="microsoft-defender-for-office"></a>Office 365용 Microsoft Defender

[Defender for Office 365](/office365/securitycompliance/office-365-atp) 는 전자 메일 메시지 또는 파일의 맬웨어로부터 조직을 보호하는 데 도움이 되는 금고 링크, 금고 첨부 파일, 고급 피싱 방지 및 스푸핑 인텔리전스 기능을 통해 보호합니다. Microsoft Defender for Office 365 Microsoft Defender for Endpoint를 통합하면 보안 분석가가 공격 진입점을 조사할 수 있습니다. 위협 인텔리전스 공유를 통해 공격을 포함하고 차단할 수 있습니다.

> [!NOTE]
> 데이터 Office 365 지난 30일 이내에 이벤트에 대해 표시됩니다. 경고의 경우 첫 번째 Office 365 데이터를 위한 Defender가 표시됩니다. 그런 다음에는 Defender에서 더 이상 데이터를 사용할 수 Office 365.

### <a name="skype-for-business"></a>비즈니스용 Skype

비즈니스용 Skype 통합을 통해 분석가가 포털에서 간단한 단추를 통해 잠재적으로 손상된 사용자 또는 장치 소유자와 통신할 수 있습니다.

## <a name="microsoft-365-defender"></a>Microsoft 365 Defender

Microsoft 365 Defender, Microsoft Defender for Endpoint 및 다양한 Microsoft 보안 솔루션은 엔드포인트, ID, 전자 메일 및 응용 프로그램 전반에 걸쳐 통합되는 통합 사전 및 사후 침해 엔터프라이즈 방어 제품군을 형성하여 정교한 공격을 감지, 방지, 조사 및 자동으로 대응합니다.

[자세한 내용은 Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)

## <a name="related-topics"></a>관련 항목

- [통합 및 기타 고급 기능 구성](advanced-features.md)
- [Microsoft 365 Defender 개요](/microsoft-365/security/defender/microsoft-threat-protection)
- [Microsoft 365 Defender 켜기](/microsoft-365/security/defender/mtp-enable)
- [조건부 액세스를 사용하여 사용자, 데이터 및 장치 보호](conditional-access.md)
