---
title: Azure Microsoft 365 Hub로 Defender 이벤트 스트림
description: 고급 헌팅 Microsoft 365 이벤트를 이벤트 허브로 스트리밍하도록 Defender를 구성하는 방법을 학습합니다.
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
ms.openlocfilehash: c62f175fc8227f64b9f18de78a2a793b2201691c
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782372"
---
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-azure-event-hub"></a><span data-ttu-id="58758-104">Azure Microsoft 365 허브로 고급 헌팅 이벤트를 스트리밍하도록 Microsoft 365 Defender 구성</span><span class="sxs-lookup"><span data-stu-id="58758-104">Configure Microsoft 365 Defender to stream Advanced Hunting events to your Azure Event Hub</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="58758-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="58758-105">**Applies to:**</span></span>
- [<span data-ttu-id="58758-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="58758-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="before-you-begin"></a><span data-ttu-id="58758-107">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="58758-107">Before you begin</span></span>

1. <span data-ttu-id="58758-108">[테넌트에서](/azure/event-hubs/) 이벤트 허브를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="58758-108">Create an [Event hub](/azure/event-hubs/) in your tenant.</span></span>

2. <span data-ttu-id="58758-109">[Azure](https://ms.portal.azure.com/)테넌트에 로그인하고, **Microsoft.Insights에** 등록할 > 구독 > 리소스 공급자로 > 로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="58758-109">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to **Subscriptions > Your subscription > Resource Providers > Register to Microsoft.Insights**.</span></span>

3. <span data-ttu-id="58758-110">이벤트 허브 네임스페이스를 만들고  이벤트 허브 네임스페이스로 이동하여 > 계층, 처리력 단위 및 예상 부하에 적합한 자동 Inflate을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="58758-110">Create an Event Hub Namespace, go to **Event Hub > Add** and select the pricing tier, throughput units and Auto-Inflate appropriate for expected load.</span></span> <span data-ttu-id="58758-111">자세한 내용은 [가격 책정 - 이벤트 허브 | Microsoft Azure.](https://azure.microsoft.com/en-us/pricing/details/event-hubs/)</span><span class="sxs-lookup"><span data-stu-id="58758-111">For more information, see [Pricing - Event Hub | Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/).</span></span>  

### <a name="add-contributor-permissions"></a><span data-ttu-id="58758-112">참가자 권한 추가</span><span class="sxs-lookup"><span data-stu-id="58758-112">Add contributor permissions</span></span> 
<span data-ttu-id="58758-113">이벤트 허브 네임스페이스가 생성되면 앱 등록 서비스 사용자를 읽기 프로그램, Azure 이벤트 허브 데이터 수신기로 추가하고 Microsoft 365 Defender에 참가자로 로그인할 사용자를 추가해야 합니다(리소스 그룹 또는 구독 수준에서도 이 작업을 수행 할 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="58758-113">Once the Event Hub namespace is created you will need to add the App Registration Service Principal as Reader, Azure Event Hub Data Receiver, and the user who will be logging into Microsoft 365 Defender as Contributor (this can also be done at Resource Group or Subscription level).</span></span> 

<span data-ttu-id="58758-114">**IAM(액세스 제어)** > 이벤트 허브 네임스페이스로 이동하여 > 할당 아래에서 추가 및 **확인을 진행합니다.**</span><span class="sxs-lookup"><span data-stu-id="58758-114">Go to **Event hubs namespace > Access control (IAM) > Add** and verify under **Role assignments**.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="58758-115">원시 데이터 스트리밍 사용</span><span class="sxs-lookup"><span data-stu-id="58758-115">Enable raw data streaming</span></span>

1. <span data-ttu-id="58758-116">\* 전역 [Microsoft 365](https://security.microsoft.com) 또는 _\* 보안 관리자 \*\*\*\*로\*\* Microsoft 365 보안 _센터에 로그인합니다._</span><span class="sxs-lookup"><span data-stu-id="58758-116">Log in to the [Microsoft 365 Defender security center](https://security.microsoft.com) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="58758-117">스트리밍 [API 설정 페이지로 이동합니다.](https://security.microsoft.com/settings/mtp_settings/raw_data_export)</span><span class="sxs-lookup"><span data-stu-id="58758-117">Go to the [Streaming API settings page](https://security.microsoft.com/settings/mtp_settings/raw_data_export).</span></span>

3. <span data-ttu-id="58758-118">추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="58758-118">Click on **Add**.</span></span>

4. <span data-ttu-id="58758-119">새 설정의 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="58758-119">Choose a name for your new settings.</span></span>

5. <span data-ttu-id="58758-120">**Azure 이벤트 허브로 이벤트 전달을 선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="58758-120">Choose **Forward events to Azure Event Hub**.</span></span>

6. <span data-ttu-id="58758-121">이벤트 데이터를 단일 이벤트 허브로 내보내거나 각 이벤트 테이블을 이벤트 허브 네임스페이스의 다른 이벤트 허브로 내보낼지 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58758-121">You can select if you want to export the event data to a single Event Hub, or to export each event table to a different event hub in your Event Hub namespace.</span></span> 

7. <span data-ttu-id="58758-122">이벤트 데이터를 단일 이벤트 허브로 내보내기  위해 이벤트 허브 이름 및 이벤트 허브 리소스 **ID 를 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="58758-122">To export the event data to a single Event Hub, enter your **Event Hub name** and your **Event Hub resource ID**.</span></span>

   <span data-ttu-id="58758-123">이벤트 허브 리소스 **ID를** 얻습니다. Azure 속성 탭의 [Azure](https://ms.portal.azure.com/)이벤트 허브 네임스페이스 페이지로 이동하여 > ID 아래 텍스트를  >   **복사합니다.**</span><span class="sxs-lookup"><span data-stu-id="58758-123">To get your **Event Hub resource ID**, go to your Azure Event Hub namespace page on [Azure](https://ms.portal.azure.com/) > **Properties** tab > copy the text under **Resource ID**:</span></span>

   ![이벤트 허브 리소스 ID1의 이미지](../defender-endpoint/images/event-hub-resource-id.png)

8. <span data-ttu-id="58758-125">스트리밍할 이벤트를 선택하고 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="58758-125">Choose the events you want to stream and click **Save**.</span></span>

## <a name="the-schema-of-the-events-in-azure-event-hub"></a><span data-ttu-id="58758-126">Azure 이벤트 허브의 이벤트 스마마</span><span class="sxs-lookup"><span data-stu-id="58758-126">The schema of the events in Azure Event Hub</span></span>

```
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

- <span data-ttu-id="58758-127">Azure 이벤트 허브의 각 이벤트 허브 메시지에는 레코드 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58758-127">Each Event Hub message in Azure Event Hub contains list of records.</span></span>

- <span data-ttu-id="58758-128">각 레코드에는 이벤트 이름, Microsoft 365 Defender에서 이벤트를 수신한 시간, 해당 레코드가 속한 테넌트(테넌트에서만 이벤트만 수신) 및 **"properties"라는** 속성의 JSON 형식 이벤트가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58758-128">Each record contains the event name, the time Microsoft 365 Defender received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "**properties**".</span></span>

- <span data-ttu-id="58758-129">Defender 이벤트의 Microsoft 365 대한 자세한 내용은 고급 헌팅 개요를 [참조하세요.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="58758-129">For more information about the schema of Microsoft 365 Defender events, see [Advanced Hunting overview](advanced-hunting-overview.md).</span></span>

- <span data-ttu-id="58758-130">고급 헌팅에서 **DeviceInfo** 테이블에는 장치 그룹이 포함된 **MachineGroup이라는** 열이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58758-130">In Advanced Hunting, the **DeviceInfo** table has a column named **MachineGroup** which contains the group of the device.</span></span> <span data-ttu-id="58758-131">여기에서 모든 이벤트도 이 열로 장식됩니다.</span><span class="sxs-lookup"><span data-stu-id="58758-131">Here every event will be decorated with this column as well.</span></span> 




## <a name="data-types-mapping"></a><span data-ttu-id="58758-132">데이터 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="58758-132">Data types mapping</span></span>

<span data-ttu-id="58758-133">이벤트 속성에 대한 데이터 형식을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="58758-133">To get the data types for event properties do the following:</span></span>

1. <span data-ttu-id="58758-134">보안 센터에 [Microsoft 365 고급](https://security.microsoft.com) 헌팅 [페이지로 이동합니다.](https://security.microsoft.com/hunting-package)</span><span class="sxs-lookup"><span data-stu-id="58758-134">Log in to [Microsoft 365 security center](https://security.microsoft.com) and go to [Advanced Hunting page](https://security.microsoft.com/hunting-package).</span></span>

2. <span data-ttu-id="58758-135">다음 쿼리를 실행하여 각 이벤트에 대한 데이터 형식 매핑을 구합니다.</span><span class="sxs-lookup"><span data-stu-id="58758-135">Run the following query to get the data types mapping for each event:</span></span>
 
   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- <span data-ttu-id="58758-136">장치 정보 이벤트의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="58758-136">Here is an example for Device Info event:</span></span> 

  ![이벤트 허브 리소스 Id2의 이미지](../defender-endpoint/images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="58758-138">관련 항목</span><span class="sxs-lookup"><span data-stu-id="58758-138">Related topics</span></span>
- [<span data-ttu-id="58758-139">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="58758-139">Overview of Advanced Hunting</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="58758-140">Microsoft 365 Defender 스트리밍 API</span><span class="sxs-lookup"><span data-stu-id="58758-140">Microsoft 365 Defender streaming API</span></span>](streaming-api.md)
- [<span data-ttu-id="58758-141">Azure Microsoft 365 Defender 이벤트 스트림</span><span class="sxs-lookup"><span data-stu-id="58758-141">Stream Microsoft 365 Defender events to your Azure storage account</span></span>](streaming-api-storage.md)
- [<span data-ttu-id="58758-142">Azure 이벤트 허브 설명서</span><span class="sxs-lookup"><span data-stu-id="58758-142">Azure Event Hub documentation</span></span>](/azure/event-hubs/)
- [<span data-ttu-id="58758-143">연결 문제 해결 - Azure 이벤트 허브</span><span class="sxs-lookup"><span data-stu-id="58758-143">Troubleshoot connectivity issues - Azure Event Hub</span></span>](/azure/event-hubs/troubleshooting-guide)
