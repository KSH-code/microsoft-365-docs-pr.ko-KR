---
title: SIEM 도구를 사용자와 Microsoft 365 Defender
description: REST API를 사용하는 방법을 알아보고 검색을 수신하고 끌어오도록 지원되는 보안 정보 및 이벤트 관리 도구를 구성합니다.
keywords: siem 구성, 보안 정보 및 이벤트 관리 도구, splunk, arcsight, 사용자 지정 표시기, rest api, 경고 정의, 손상 표시기
search.product: eADQiWindows 10XVcnh
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
ms.openlocfilehash: e4f67bed002c1864403be9458aae230eac0e7340
ms.sourcegitcommit: e110f00dc6949a7a1345187375547beeb64225b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/06/2021
ms.locfileid: "60805018"
---
# <a name="integrate-your-siem-tools-with-microsoft-365-defender"></a>SIEM 도구를 사용자와 Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="pull-microsoft-365-defender-incidents-and-streaming-event-data-using-security-information-and-events-management-siem-tools"></a>SIEM(Microsoft 365 Defender 및 이벤트 관리) 도구를 사용하여 인시던트 및 스트리밍 이벤트 데이터 끌어오기

> [!NOTE]
>
> - [Microsoft 365 Defender 인시던트는](incident-queue.md) 상호 관련 경고 및 해당 증거 모음으로 구성됩니다.
> - [Microsoft 365 Defender API는](streaming-api.md) 이벤트 Microsoft 365 Defender 또는 Azure 저장소 계정으로 이벤트 데이터를 스트리밍합니다.

Microsoft 365 Defender 설치된 특정 SIEM 솔루션 또는 커넥터를 나타내는 등록된 AAD 응용 프로그램에 대해 OAuth 2.0 인증 프로토콜을 사용하여 Azure Active Directory(AAD)의 엔터프라이즈 테넌트에서 정보를 수집하는 SIEM(보안 정보 및 이벤트 관리) 도구가 지원됩니다. environment. 

자세한 내용은 다음을 참조하세요.

- [Microsoft 365 Defender API 라이선스 및 사용 약관](api-terms.md)
- [MICROSOFT 365 DEFENDER API에 액세스](api-access.md)
- [Hello World 예제](api-hello-world.md)
- [응용 프로그램 컨텍스트를 사용하여 액세스](api-create-app-web.md)

보안 정보를 수집하는 데는 두 가지 기본 모델이 있습니다. 

1.  인시던트 Microsoft 365 Defender Azure의 REST API에서 포함된 경고를 검색합니다. 

2.  Azure 이벤트 허브 또는 사용자 계정을 통해 스트리밍 이벤트 Azure Storage 수집합니다. 

Microsoft 365 Defender 현재 다음과 같은 SIEM 솔루션 통합을 지원합니다. 

- [인시던트 REST API에서 인시던트 검색](#ingesting-incidents-from-the-incidents-rest-api)
- [이벤트 허브를 통해 스트리밍 이벤트 데이터 수집](#ingesting-streaming-event-data-via-event-hubs)

## <a name="ingesting-incidents-from-the-incidents-rest-api"></a>인시던트 REST API에서 인시던트 검색

### <a name="incident-schema"></a>인시던트 schema
포함된 경고 및 Microsoft 365 Defender 엔터티 메타데이터를 포함하여 인시던트 속성에 대한 자세한 내용은 [Schema mapping을 참조하세요.](../defender/api-list-incidents.md#schema-mapping)

### <a name="splunk"></a>Splunk

다음을 Microsoft 365 Defender Splunk용 추가 기능 사용: 

- Splunk의 CIM(일반 정보 모델)에 매핑되는 다음 제품의 경고가 포함된 인시던트 수집:  
  - Microsoft 365 Defender 
  - 끝점용 Microsoft Defender 
  - ID 보호를 위한 Microsoft Defender & Azure Active Directory 보호 
  - Microsoft Cloud App Security 

- Splunk 내에서 Microsoft 365 Defender 인시던트 업데이트 

- 끝점 경고에 대한 Defender 알림(끝점의 Azure 끝점용 Defender)을 생성하고 이러한 경고 업데이트 

Splunk용 추가 Microsoft 365 Defender 자세한 내용은 [splunkbase를 참조하세요.](https://splunkbase.splunk.com/app/4959/)

  

### <a name="micro-focus-arcsight"></a>마이크로 포커스 ArcSight

새 SmartConnector를 Microsoft 365 Defender ArcSight로 인시던트가 인시던트와 매핑되어 CEF(Common Event Framework)에 매핑됩니다. 

새 ArcSight SmartConnector에 대한 자세한 Microsoft 365 Defender [ArcSight 제품 설명서를 참조하세요.](https://community.microfocus.com/cyberres/productdocs/w/connector-documentation/39246/smartconnector-for-microsoft-365-defender)

SmartConnector는 끝점용 Microsoft Defender의 이전 FlexConnector를 대체합니다.
  

## <a name="ingesting-streaming-event-data-via-event-hubs"></a>이벤트 허브를 통해 스트리밍 이벤트 데이터 수집

먼저 테넌트에서 이벤트 허브 또는 AAD 계정으로 이벤트를 Azure Storage 합니다. 자세한 내용은 [스트리밍 API를 참조하세요.](../defender/streaming-api.md)

스트리밍 API에서 지원하는 이벤트 유형에 대한 자세한 내용은 지원되는 스트리밍 이벤트 [유형을 참조하세요.](../defender/supported-event-types.md)

### <a name="splunk"></a>Splunk
Microsoft 클라우드 서비스에 대한 Splunk 추가 기능을 사용하여 Azure 이벤트 허브에서 이벤트를 인제스트합니다.  


Microsoft 클라우드 서비스용 Splunk 추가 기능에 대한 자세한 내용은 [splunkbase 를 참조하세요.](https://splunkbase.splunk.com/app/3110/)
  

### <a name="ibm-qradar"></a>IBM QRadar
>Microsoft 365 Defender 제품의 스트리밍 이벤트 데이터를 수집할 수 있도록 하는 Microsoft 365 Defender Streaming [API를](streaming-api.md) 호출하는 새로운 IBM QRadar Microsoft 365 Defender DSM(장치 지원 모듈)을 사용합니다. 지원되는 이벤트 유형에 대한 자세한 내용은 지원되는 이벤트 [유형을 참조하세요.](supported-event-types.md)

