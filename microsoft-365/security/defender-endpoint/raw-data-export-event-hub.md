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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8985a40c99ad4db9710dfbf9805d537a921f6c96
ms.sourcegitcommit: f0118e61e490496cb23189cc5c73b23e2ba939be
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/05/2021
ms.locfileid: "52780168"
---
# <a name="configure-microsoft-defender-for-endpoint-to-stream-advanced-hunting-events-to-your-azure-event-hubs"></a><span data-ttu-id="154ff-104">Azure 이벤트 허브에 고급 헌팅 이벤트를 스트리밍하도록 끝점에 대한 Microsoft Defender 구성</span><span class="sxs-lookup"><span data-stu-id="154ff-104">Configure Microsoft Defender for Endpoint to stream Advanced Hunting events to your Azure Event Hubs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="154ff-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="154ff-105">**Applies to:**</span></span>

- [<span data-ttu-id="154ff-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="154ff-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="154ff-107">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="154ff-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="154ff-108">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="154ff-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="before-you-begin"></a><span data-ttu-id="154ff-109">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="154ff-109">Before you begin</span></span>

1. <span data-ttu-id="154ff-110">[테넌트에서 이벤트 허브를](/azure/event-hubs/) 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="154ff-110">Create an [event hub](/azure/event-hubs/) in your tenant.</span></span>

2. <span data-ttu-id="154ff-111">[Azure](https://ms.portal.azure.com/)테넌트에 로그인하고 \*\*구독 > 구독 > 리소스 공급자> 등록 \*\*Microsoft.insights\*\*\*\*로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="154ff-111">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to \*\*Subscriptions > Your subscription > Resource Providers > Register to \*\*Microsoft.insights\*\*\*\*.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="154ff-112">원시 데이터 스트리밍 사용</span><span class="sxs-lookup"><span data-stu-id="154ff-112">Enable raw data streaming</span></span>

1. <span data-ttu-id="154ff-113">\* 전역 [Microsoft Defender 보안 센터](https://securitycenter.windows.com) **_** 또는 __\*_ 보안 관리자 \*\*로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="154ff-113">Log in to the [Microsoft Defender Security Center](https://securitycenter.windows.com) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="154ff-114">에서 [데이터 내보내기 설정](https://securitycenter.windows.com/interoperability/dataexport) 페이지로 Microsoft Defender 보안 센터.</span><span class="sxs-lookup"><span data-stu-id="154ff-114">Go to the [Data export settings page](https://securitycenter.windows.com/interoperability/dataexport) on Microsoft Defender Security Center.</span></span>

3. <span data-ttu-id="154ff-115">데이터 **내보내기 설정 추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="154ff-115">Click on **Add data export settings**.</span></span>

4. <span data-ttu-id="154ff-116">새 설정의 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="154ff-116">Choose a name for your new settings.</span></span>

5. <span data-ttu-id="154ff-117">**Azure 이벤트 허브로 이벤트 전달을 선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="154ff-117">Choose **Forward events to Azure Event Hubs**.</span></span>

6. <span data-ttu-id="154ff-118">이벤트 **허브** 이름 및 **이벤트 허브 리소스 ID를 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="154ff-118">Type your **Event Hubs name** and your **Event Hubs resource ID**.</span></span>

   <span data-ttu-id="154ff-119">이벤트 허브 리소스 **ID를** 얻기 위해 Azure > 속성 탭의 [Azure](https://ms.portal.azure.com/) 이벤트 허브 네임스페이스 페이지로 이동한 > 리소스 ID 아래 텍스트를 **복사합니다.**</span><span class="sxs-lookup"><span data-stu-id="154ff-119">In order to get your **Event Hubs resource ID**, go to your Azure Event Hubs namespace page on [Azure](https://ms.portal.azure.com/) > properties tab > copy the text under **Resource ID**:</span></span>

   ![이벤트 허브 리소스 Id1의 이미지](images/event-hub-resource-id.png)

7. <span data-ttu-id="154ff-121">스트리밍할 이벤트를 선택하고 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="154ff-121">Choose the events you want to stream and click **Save**.</span></span>

## <a name="the-schema-of-the-events-in-azure-event-hubs"></a><span data-ttu-id="154ff-122">Azure 이벤트 허브의 이벤트 스마마</span><span class="sxs-lookup"><span data-stu-id="154ff-122">The schema of the events in Azure Event Hubs</span></span>

```
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

- <span data-ttu-id="154ff-123">Azure 이벤트 허브의 각 이벤트 허브 메시지에는 레코드 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="154ff-123">Each event hub message in Azure Event Hubs contains list of records.</span></span>

- <span data-ttu-id="154ff-124">각 레코드에는 이벤트 이름, Endpoint용 Microsoft Defender에서 이벤트를 수신한 시간, 해당 레코드가 속한 테넌트(테넌트에서만 이벤트만 수신) 및 **"properties"라는** 속성의 JSON 형식 이벤트가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="154ff-124">Each record contains the event name, the time Microsoft Defender for Endpoint received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "**properties**".</span></span>

- <span data-ttu-id="154ff-125">끝점 이벤트용 Microsoft Defender 이벤트의 schema에 대한 자세한 내용은 고급 헌팅 [개요를 참조하세요.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="154ff-125">For more information about the schema of Microsoft Defender for Endpoint events, see [Advanced Hunting overview](advanced-hunting-overview.md).</span></span>

- <span data-ttu-id="154ff-126">고급 헌팅에서 **DeviceInfo** 테이블에는 장치 그룹이 포함된 **MachineGroup이라는** 열이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="154ff-126">In Advanced Hunting, the **DeviceInfo** table has a column named **MachineGroup** which contains the group of the device.</span></span> <span data-ttu-id="154ff-127">여기에서 모든 이벤트도 이 열로 장식됩니다.</span><span class="sxs-lookup"><span data-stu-id="154ff-127">Here every event will be decorated with this column as well.</span></span> <span data-ttu-id="154ff-128">자세한 [내용은 장치 그룹을](machine-groups.md) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="154ff-128">See [Device Groups](machine-groups.md) for more information.</span></span>

## <a name="data-types-mapping"></a><span data-ttu-id="154ff-129">데이터 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="154ff-129">Data types mapping</span></span>

<span data-ttu-id="154ff-130">이벤트 속성에 대한 데이터 형식을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="154ff-130">To get the data types for event properties do the following:</span></span>

1. <span data-ttu-id="154ff-131">로그인하여 [](https://securitycenter.windows.com) Microsoft Defender 보안 센터 [헌팅 페이지로 이동합니다.](https://securitycenter.windows.com/hunting-package)</span><span class="sxs-lookup"><span data-stu-id="154ff-131">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com) and go to [Advanced Hunting page](https://securitycenter.windows.com/hunting-package).</span></span>

2. <span data-ttu-id="154ff-132">다음 쿼리를 실행하여 각 이벤트에 대한 데이터 형식 매핑을 구합니다.</span><span class="sxs-lookup"><span data-stu-id="154ff-132">Run the following query to get the data types mapping for each event:</span></span>
 
   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- <span data-ttu-id="154ff-133">장치 정보 이벤트의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="154ff-133">Here is an example for Device Info event:</span></span> 

  ![이벤트 허브 리소스 Id2의 이미지](images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="154ff-135">관련 항목</span><span class="sxs-lookup"><span data-stu-id="154ff-135">Related topics</span></span>
- [<span data-ttu-id="154ff-136">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="154ff-136">Overview of Advanced Hunting</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="154ff-137">끝점 스트리밍 API용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="154ff-137">Microsoft Defender for Endpoint streaming API</span></span>](raw-data-export.md)
- [<span data-ttu-id="154ff-138">Azure 저장소 계정으로 Endpoint용 Microsoft Defender 이벤트 스트림</span><span class="sxs-lookup"><span data-stu-id="154ff-138">Stream Microsoft Defender for Endpoint events to your Azure storage account</span></span>](raw-data-export-storage.md)
- [<span data-ttu-id="154ff-139">Azure 이벤트 허브 설명서</span><span class="sxs-lookup"><span data-stu-id="154ff-139">Azure Event Hubs documentation</span></span>](/azure/event-hubs/)
- [<span data-ttu-id="154ff-140">연결 문제 해결 - Azure 이벤트 허브</span><span class="sxs-lookup"><span data-stu-id="154ff-140">Troubleshoot connectivity issues - Azure Event Hubs</span></span>](/azure/event-hubs/troubleshooting-guide)