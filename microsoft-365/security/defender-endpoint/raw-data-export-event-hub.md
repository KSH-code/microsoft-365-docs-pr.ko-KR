---
title: Azure 이벤트 허브로 끝점용 Microsoft Defender 이벤트 스트림
description: 고급 헌팅 이벤트를 이벤트 허브로 스트리밍하도록 끝점용 Microsoft Defender를 구성하는 방법을 학습합니다.
keywords: 원시 데이터 내보내기, 스트리밍 API, API, Azure 이벤트 허브, Azure 저장소, 저장소 계정, 고급 헌팅, 원시 데이터 공유
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
ms.custom: api
ms.openlocfilehash: ac97d7a4210d1f498fa82453eb66e01398718c37
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60209264"
---
# <a name="configure-microsoft-defender-for-endpoint-to-stream-advanced-hunting-events-to-your-azure-event-hubs"></a>Azure 이벤트 허브에 고급 헌팅 이벤트를 스트리밍하도록 끝점에 대한 Microsoft Defender 구성

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**

- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configuresiem-abovefoldlink)

## <a name="before-you-begin"></a>시작하기 전에

1. [테넌트에서 이벤트 허브를](/azure/event-hubs/) 생성합니다.

2. [Azure](https://ms.portal.azure.com/)테넌트에 로그인하고 **구독 > 구독 > 리소스 공급자> 등록 **Microsoft.insights****로 이동하세요.

## <a name="enable-raw-data-streaming"></a>원시 데이터 스트리밍 사용

1. * 전역 [Microsoft Defender 보안 센터](https://securitycenter.windows.com) **_** 또는 __*_ 보안 관리자 **로 로그인합니다.

2. 에서 [데이터 내보내기 설정](https://securitycenter.windows.com/interoperability/dataexport) 페이지로 Microsoft Defender 보안 센터.

3. 데이터 **내보내기 설정 추가를 클릭합니다.**

4. 새 설정의 이름을 선택합니다.

5. **Azure 이벤트 허브로 이벤트 전달을 선택하세요.**

6. 이벤트 **허브** 이름 및 **이벤트 허브 리소스 ID를 입력합니다.**

   이벤트 허브 리소스 **ID를** 얻기 위해 Azure > 속성 탭의 [Azure](https://ms.portal.azure.com/) 이벤트 허브 네임스페이스 페이지로 이동하여 리소스 ID 아래 텍스트를 \> **복사합니다.**

   ![이벤트 허브 리소스 Id1의 이미지입니다.](images/event-hub-resource-id.png)

7. 스트리밍할 이벤트를 선택하고 저장을 **클릭합니다.**

## <a name="the-schema-of-the-events-in-azure-event-hubs"></a>Azure 이벤트 허브의 이벤트 스마마

```text
{
    "records": [
                    {
                        "time": "<The time WDATP received the event>"
                        "tenantId": "<The Id of the tenant that the event belongs to>"
                        "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
                        "properties": { <WDATP Advanced Hunting event as Json> }
                    }
                    ...
                ]
}
```

- Azure 이벤트 허브의 각 이벤트 허브 메시지에는 레코드 목록이 포함되어 있습니다.

- 각 레코드에는 이벤트 이름, Endpoint용 Microsoft Defender에서 이벤트를 수신한 시간, 해당 레코드가 속한 테넌트(테넌트에서만 이벤트만 수신) 및 **"properties"라는** 속성의 JSON 형식 이벤트가 포함되어 있습니다.

- 끝점 이벤트용 Microsoft Defender 이벤트의 schema에 대한 자세한 내용은 고급 헌팅 [개요를 참조하세요.](advanced-hunting-overview.md)

- 고급 헌팅에서 **DeviceInfo** 테이블에는 장치 그룹이 포함된 **MachineGroup이라는** 열이 있습니다. 여기에서 모든 이벤트도 이 열로 장식됩니다. 자세한 [내용은 장치 그룹을](machine-groups.md) 참조하세요.

## <a name="data-types-mapping"></a>데이터 형식 매핑

이벤트 속성에 대한 데이터 형식을 얻습니다.

1. 로그인하여 [](https://securitycenter.windows.com) Microsoft Defender 보안 센터 [헌팅 페이지로 이동합니다.](https://securitycenter.windows.com/hunting-package)

2. 다음 쿼리를 실행하여 각 이벤트에 대한 데이터 형식 매핑을 구합니다.

   ```text
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- 장치 정보 이벤트의 예는 다음과 같습니다.

  ![이벤트 허브 리소스 Id2의 이미지입니다.](images/machine-info-datatype-example.png)

## <a name="related-topics"></a>관련 항목

- [고급 헌팅 개요](advanced-hunting-overview.md)
- [끝점 스트리밍 API용 Microsoft Defender](raw-data-export.md)
- [Azure 저장소 계정으로 Endpoint용 Microsoft Defender 이벤트 스트림](raw-data-export-storage.md)
- [Azure 이벤트 허브 설명서](/azure/event-hubs/)
- [연결 문제 해결 - Azure 이벤트 허브](/azure/event-hubs/troubleshooting-guide)
