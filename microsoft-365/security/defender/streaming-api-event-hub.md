---
title: Azure Microsoft 365 Defender 이벤트 스트림
description: 고급 헌팅 이벤트를 Microsoft 365 Defender 허브로 스트리밍하도록 헌팅 이벤트를 구성하는 방법을 자세히 알아보도록 합니다.
keywords: 원시 데이터 내보내기, 스트리밍 API, API, Azure 이벤트 허브, Azure 저장소, 저장소 계정, 고급 헌팅, 원시 데이터 공유
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ecfc8281c642e7240832a7c057f37f9df4caad68
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59211802"
---
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-azure-event-hub"></a>Azure Microsoft 365 Defender 고급 헌팅 이벤트를 스트리밍하도록 구성

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="before-you-begin"></a>시작하기 전에

1. [테넌트에서](/azure/event-hubs/) 이벤트 허브를 생성합니다.

2. [Azure](https://ms.portal.azure.com/)테넌트에 로그인하고, **Microsoft.>** 구독 > 리소스 공급자로 >.Insights.

3. 이벤트 허브 네임스페이스를 만들고  이벤트 허브 네임스페이스로 이동하여 > 계층, 처리력 단위 및 예상 부하에 적합한 자동 Inflate을 선택합니다. 자세한 내용은 이벤트 허브 [가격을 참조하세요.](https://azure.microsoft.com/pricing/details/event-hubs/)

### <a name="add-contributor-permissions"></a>참가자 권한 추가

이벤트 허브 네임스페이스가 생성되면 다음을 해야 합니다.

1. 참가자로 로그인할 Microsoft 365 Defender 정의합니다.

2. 응용 프로그램에 연결하는 경우 앱 등록 서비스 계정을 읽기 프로그램, Azure 이벤트 허브 데이터 수신기로 추가합니다(리소스 그룹 또는 구독 수준에서도 이행할 수 있습니다).

    **IAM(액세스 제어)** > 이벤트 허브 네임스페이스로 이동하여 > 할당 아래에서 추가 및 **확인을 진행합니다.**

## <a name="enable-raw-data-streaming"></a>원시 데이터 스트리밍 사용

1. * Microsoft 365 Defender [](https://security.microsoft.com) 보안 센터에 ***전역** 관리자 _ 또는 _* 보안 관리자 **로 _로그인합니다._

2. 스트리밍 [API 설정 페이지로 이동합니다.](https://security.microsoft.com/settings/mtp_settings/raw_data_export)

3. 추가를 **클릭합니다.**

4. 새 설정의 이름을 선택합니다.

5. **Azure 이벤트 허브로 이벤트 전달을 선택하세요.**

6. 이벤트 데이터를 단일 이벤트 허브로 내보내거나 각 이벤트 테이블을 이벤트 허브 네임스페이스의 다른 이벤트 허브로 내보낼지 선택할 수 있습니다.

7. 이벤트 데이터를 단일 이벤트 허브로 내보내기  위해 이벤트 허브 이름 및 이벤트 허브 리소스 **ID 를 입력합니다.**

   이벤트 허브 리소스 **ID를** 얻습니다. Azure 속성 탭의 [Azure](https://ms.portal.azure.com/)이벤트 허브 네임스페이스 페이지로 이동하여 > ID 아래 텍스트를  >   **복사합니다.**

   ![이벤트 허브 리소스 Id1의 이미지입니다.](../defender-endpoint/images/event-hub-resource-id.png)

8. 스트리밍할 이벤트를 선택하고 저장을 **클릭합니다.**

## <a name="the-schema-of-the-events-in-azure-event-hub"></a>Azure 이벤트 허브의 이벤트 스마마

```JSON
{
   "records": [
               {
                  "time": "<The time Microsoft 365 Defender received the event>"
                  "tenantId": "<The Id of the tenant that the event belongs to>"
                  "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
                  "properties": { <Microsoft 365 Defender Advanced Hunting event as Json> }
               }
               ...
            ]
}
```

- Azure 이벤트 허브의 각 이벤트 허브 메시지에는 레코드 목록이 포함되어 있습니다.

- 각 레코드에는 이벤트 이름, 이벤트 Microsoft 365 Defender 받은 시간, 해당 레코드가 속한 테넌트(테넌트에서 이벤트만 수신) 및 JSON 형식의 이벤트가 **"properties"라는** 속성으로 포함되어 있습니다.

- 이벤트의 SCHEMA에 대한 자세한 내용은 Microsoft 365 Defender [헌팅 개요를 참조하세요.](advanced-hunting-overview.md)

- 고급 헌팅에서 **DeviceInfo** 테이블에는 장치 그룹이 포함된 **MachineGroup이라는** 열이 있습니다. 여기에서 모든 이벤트도 이 열로 장식됩니다.

## <a name="data-types-mapping"></a>데이터 형식 매핑

이벤트 속성에 대한 데이터 형식을 얻습니다.

1. Microsoft 365 Defender [포털에 로그인하고](https://security.microsoft.com) 고급 헌팅 [페이지로 이동합니다.](https://security.microsoft.com/hunting-package)

2. 다음 쿼리를 실행하여 각 이벤트에 대한 데이터 형식 매핑을 구합니다.

   ```kusto
   {EventType}
   | getschema
   | project ColumnName, ColumnType
   ```

- 장치 정보 이벤트의 예는 다음과 같습니다.

  ![이벤트 허브 리소스 Id2의 이미지입니다.](../defender-endpoint/images/machine-info-datatype-example.png)

## <a name="related-topics"></a>관련 항목

- [고급 헌팅 개요](advanced-hunting-overview.md)
- [Microsoft 365 Defender 스트리밍 API](streaming-api.md)
- [Azure Microsoft 365 Defender 이벤트 스트림](streaming-api-storage.md)
- [Azure 이벤트 허브 설명서](/azure/event-hubs/)
- [연결 문제 해결 - Azure 이벤트 허브](/azure/event-hubs/troubleshooting-guide)
