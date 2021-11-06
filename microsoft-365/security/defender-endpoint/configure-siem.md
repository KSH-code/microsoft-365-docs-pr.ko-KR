---
title: 끝점용 Microsoft Defender와 SIEM 도구 통합
description: 인시던트 및 경고를 분석하고 SIEM 도구를 통합하는 방법을 학습합니다.
keywords: siem 구성, 보안 정보 및 이벤트 관리 도구, splunk, arcsight, 사용자 지정 표시기, rest api, 경고 정의, 손상 표시기
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a08aca1749e9d5dc613b97347cbb040fe9f6e40c
ms.sourcegitcommit: e110f00dc6949a7a1345187375547beeb64225b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/06/2021
ms.locfileid: "60804774"
---
# <a name="integrate-your-siem-tools-with-microsoft-defender-for-endpoint"></a>끝점용 Microsoft Defender와 SIEM 도구 통합

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)


## <a name="ingest-alerts-using-security-information-and-events-management-siem-tools"></a>SIEM(보안 정보 및 이벤트 관리) 도구를 사용하여 경고 수집

> [!NOTE]
>
> [끝점용 Microsoft Defender 경고는](alerts.md) 장치에서 발생한 하나 이상의 의심스러우거나 악의적인 이벤트와 관련 세부 정보로 구성됩니다. 끝점 경고용 Microsoft Defender 경고 API는 경고 소비를 위한 최신 API로, 각 경고에 대한 자세한 관련 증거 목록을 포함 합니다. 자세한 내용은 [Alert 메서드](alerts.md) 및 속성 및 목록 [경고를 참조하세요.](get-alerts.md)

Microsoft Defender for Endpoint는 환경에 설치된 특정 SIEM 솔루션 또는 커넥터를 나타내는 등록된 AAD 응용 프로그램에 대해 OAuth 2.0 인증 프로토콜을 사용하여 Azure Active Directory(AAD)의 엔터프라이즈 테넌트에서 정보를 수집하는 SIEM(보안 정보 및 이벤트 관리) 도구를 지원합니다. 

자세한 내용은 다음을 참조하세요.

- [끝점 API용 Microsoft Defender 라이선스 및 사용 약관](api-terms-of-use.md) 
- [엔드포인트용 Microsoft Defender API에 액세스](apis-intro.md) 
- [Hello World 예제(2016에서 응용 프로그램을 등록하는 Azure Active Directory)](api-hello-world.md)
- [응용 프로그램 컨텍스트를 사용하여 액세스](exposed-apis-create-app-webapp.md)


Microsoft Defender for Endpoint는 현재 다음과 같은 SIEM 솔루션 통합을 지원합니다. 

- [엔드포인트 인시던트 및 Microsoft Defender에서 인시던트 Microsoft 365 Defender 및 경고 REST API를 알림](#ingesting-incidents-and-alerts-from-the-microsoft-365-defender-and-microsoft-defender-for-endpoint-incidents-and-alerts-rest-apis)
- [이벤트 스트리밍 API에서 끝점 이벤트에 대한 Microsoft Defender Microsoft 365 Defender](#ingesting-microsoft-defender-for-endpoint-events-from-the-microsoft-365-defender-event-streaming-api)

## <a name="ingesting-incidents-and-alerts-from-the-microsoft-365-defender-and-microsoft-defender-for-endpoint-incidents-and-alerts-rest-apis"></a>엔드포인트 인시던트 및 Microsoft Defender에서 인시던트 Microsoft 365 Defender 및 경고 REST API를 알림

### <a name="ingesting-incidents-from-the-microsoft-365-defender-incidents-rest-api"></a>인시던트 REST API에서 Microsoft 365 Defender 인시던트 검색

인시던트 API에 대한 Microsoft 365 Defender [인시던트 메서드 및 속성을 참조하세요.](../defender/api-incident.md)

### <a name="ingesting-alerts-from-the-microsoft-defender-for-endpoint-alerts-rest-api"></a>끝점 경고 REST API에 대한 Microsoft Defender의 경고 검색

끝점 경고 API용 Microsoft Defender에 대한 자세한 내용은 경고 메서드 및 [속성을 참조하세요.](alerts.md)

## <a name="siem-tool-integration-with-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint와 SIEM 도구 통합

### <a name="splunk"></a>Splunk

다음을 Microsoft 365 Defender Splunk용 추가 기능 사용: 

- 끝점 경고에 대한 Microsoft Defender 검사 
- Splunk 내에서 끝점용 Microsoft Defender의 경고 업데이트 

Splunk용 추가 Microsoft 365 Defender 자세한 내용은 [splunkbase를 참조하세요.](https://splunkbase.splunk.com/app/4959/)

### <a name="micro-focus-arcsight"></a>마이크로 포커스 ArcSight

새로운 Microsoft 365 Defender SmartConnector는 Microsoft Defender for Endpoint를 포함하여 모든 Microsoft 365 Defender 제품의 경고를 포함하는 인시던트가 ArcSight에 추가되어 CEF(Common Event Framework)에 매핑됩니다. 

새 ArcSight SmartConnector에 대한 자세한 Microsoft 365 Defender [ArcSight 제품 설명서를 참조하세요.](https://community.microfocus.com/cyberres/productdocs/w/connector-documentation/39246/smartconnector-for-microsoft-365-defender)

SmartConnector는 이전 FlexConnector에서 이전 FlexConnector를 Microsoft 365 Defender.
  
### <a name="ibm-qradar"></a>IBM QRadar

>[!NOTE]
>
>끝점용 Microsoft Defender와 IBM QRadar의 통합은 이제 Microsoft Defender를 비롯한 Microsoft 365 Defender 제품의 스트리밍 이벤트 데이터를 수집할 수 있도록 하는 Microsoft 365 Defender [Streaming API를](../defender/streaming-api.md) 호출하는 새로운 Microsoft 365 Defender DSM(Microsoft 365 Defender 장치 지원 모듈)에서 지원됩니다. 끝점용입니다. 지원되는 이벤트 유형에 대한 자세한 내용은 지원되는 이벤트 [유형을 참조하세요.](../defender/supported-event-types.md)
새 고객은 더 이상 이전 QRadar Microsoft Defender ATP DSM(장치 지원 모듈)을 사용하여 온보딩되지 않습니다. 기존 고객은 새로운 Microsoft 365 Defender DSM을 모든 Microsoft 365 Defender 제품과의 단일 통합 지점으로 채택하는 것이 Microsoft 365 Defender 있습니다.

## <a name="ingesting-microsoft-defender-for-endpoint-events-from-the-microsoft-365-defender-event-streaming-api"></a>이벤트 스트리밍 API에서 끝점 이벤트에 대한 Microsoft Defender Microsoft 365 Defender

Microsoft 365 Defender 데이터에는 끝점용 Microsoft Defender 및 기타 Microsoft Defender 제품의 경고 및 기타 이벤트가 포함됩니다. 이러한 이벤트는 Azure Storage Azure 이벤트 허브로 스트리밍될 수 있습니다. 이벤트 허브를 통한 통합 모델은 현재 Splunk 및 IBM QRadar에서 지원됩니다.

자세한 내용은 [SIEM 통합 Microsoft 365 Defender 참조하세요.](../defender/configure-siem-defender.md)
