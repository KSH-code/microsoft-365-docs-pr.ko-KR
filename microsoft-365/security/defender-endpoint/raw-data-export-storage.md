---
title: Microsoft Defender for Endpoint 이벤트를 저장소 계정으로 스트리밍
description: 고급 헌팅 이벤트를 저장소 계정으로 스트리밍하도록 끝점용 Microsoft Defender를 구성하는 방법을 학습합니다.
keywords: 원시 데이터 내보내기, 스트리밍 API, API, 이벤트 허브, Azure 저장소, 저장소 계정, 고급 헌팅, 원시 데이터 공유
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
ms.openlocfilehash: 19fe0c9c3dc6f2e4226a4aa9a6cd983bc95bae3a
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688792"
---
# <a name="configure-microsoft-defender-for-endpoint-to-stream-advanced-hunting-events-to-your-storage-account"></a><span data-ttu-id="3baf2-104">고급 헌팅 이벤트를 저장소 계정으로 스트리밍하도록 끝점에 대한 Microsoft Defender 구성</span><span class="sxs-lookup"><span data-stu-id="3baf2-104">Configure Microsoft Defender for Endpoint to stream Advanced Hunting events to your Storage account</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="3baf2-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="3baf2-105">**Applies to:**</span></span>
- <span data-ttu-id="3baf2-106">[엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037) </span><span class="sxs-lookup"><span data-stu-id="3baf2-106">[Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="3baf2-107">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="3baf2-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="3baf2-108">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="3baf2-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="before-you-begin"></a><span data-ttu-id="3baf2-109">시작하기 전에 다음을 수행해야 합니다:</span><span class="sxs-lookup"><span data-stu-id="3baf2-109">Before you begin:</span></span>

1. <span data-ttu-id="3baf2-110">[테넌트에](https://docs.microsoft.com/azure/storage/common/storage-account-overview) 저장소 계정을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="3baf2-110">Create a [Storage account](https://docs.microsoft.com/azure/storage/common/storage-account-overview) in your tenant.</span></span>

2. <span data-ttu-id="3baf2-111">[Azure](https://ms.portal.azure.com/)테넌트에 로그인하고, **Microsoft.insights에 등록할 >** 구독 > 리소스 공급자로 > 로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="3baf2-111">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to **Subscriptions > Your subscription > Resource Providers > Register to Microsoft.insights**.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="3baf2-112">원시 데이터 스트리밍을 사용하도록 설정:</span><span class="sxs-lookup"><span data-stu-id="3baf2-112">Enable raw data streaming:</span></span>

1. <span data-ttu-id="3baf2-113">\* 전역 관리자 **_** 또는 _\* 보안 관리자 \*\*로 끝점 포털용 [Microsoft Defender에](https://securitycenter.windows.com) _로그인합니다._</span><span class="sxs-lookup"><span data-stu-id="3baf2-113">Log in to [Microsoft Defender for Endpoint portal](https://securitycenter.windows.com) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="3baf2-114">Microsoft Defender [보안 센터의](https://securitycenter.windows.com/interoperability/dataexport) 데이터 내보내기 설정 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3baf2-114">Go to [Data export settings page](https://securitycenter.windows.com/interoperability/dataexport) on Microsoft Defender Security Center.</span></span>

3. <span data-ttu-id="3baf2-115">데이터 **내보내기 설정 추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3baf2-115">Click on **Add data export settings**.</span></span>

4. <span data-ttu-id="3baf2-116">새 설정의 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3baf2-116">Choose a name for your new settings.</span></span>

5. <span data-ttu-id="3baf2-117">**Azure Storage에 이벤트 전달 을 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="3baf2-117">Choose **Forward events to Azure Storage**.</span></span>

6. <span data-ttu-id="3baf2-118">저장소 계정 **리소스 ID를 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="3baf2-118">Type your **Storage Account Resource ID**.</span></span> <span data-ttu-id="3baf2-119">저장소 계정 리소스 **ID를** 얻기 위해 [Azure Portal](https://ms.portal.azure.com/) > 속성 탭의 저장소 계정 페이지로 이동하여 > 리소스 ID 아래에 있는 텍스트를 **복사합니다.**</span><span class="sxs-lookup"><span data-stu-id="3baf2-119">In order to get your **Storage Account Resource ID**, go to your Storage account page on [Azure portal](https://ms.portal.azure.com/) > properties tab > copy the text under **Storage account resource ID**:</span></span>

   ![이벤트 허브 리소스 ID1의 이미지](images/storage-account-resource-id.png)

7. <span data-ttu-id="3baf2-121">스트리밍할 이벤트를 선택하고 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3baf2-121">Choose the events you want to stream and click **Save**.</span></span>

## <a name="the-schema-of-the-events-in-the-storage-account"></a><span data-ttu-id="3baf2-122">저장소 계정의 이벤트 스마마:</span><span class="sxs-lookup"><span data-stu-id="3baf2-122">The schema of the events in the Storage account:</span></span>

- <span data-ttu-id="3baf2-123">각 이벤트 유형에 대해 Blob 컨테이너가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="3baf2-123">A blob container will be created for each event type:</span></span> 

  ![이벤트 허브 리소스 ID2의 이미지](images/storage-account-event-schema.png)

- <span data-ttu-id="3baf2-125">Blob에 있는 각 행의 Schema는 다음과 같은 JSON입니다.</span><span class="sxs-lookup"><span data-stu-id="3baf2-125">The schema of each row in a blob is the following JSON:</span></span> 

  ```
  {
          "time": "<The time WDATP received the event>"
          "tenantId": "<Your tenant ID>"
          "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
          "properties": { <WDATP Advanced Hunting event as Json> }
  }               
  ```

- <span data-ttu-id="3baf2-126">각 Blob에는 여러 행이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3baf2-126">Each blob contains multiple rows.</span></span>

- <span data-ttu-id="3baf2-127">각 행에는 이벤트 이름, Endpoint용 Defender가 이벤트를 수신한 시간, 해당 이벤트가 속한 테넌트(테넌트에서 이벤트만 수신) 및 JSON 형식의 이벤트가 "properties"라는 속성으로 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3baf2-127">Each row contains the event name, the time Defender for Endpoint received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "properties".</span></span>

- <span data-ttu-id="3baf2-128">끝점 이벤트용 Microsoft Defender 이벤트의 schema에 대한 자세한 내용은 고급 헌팅 [개요를 참조하세요.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="3baf2-128">For more information about the schema of Microsoft Defender for Endpoint events, see [Advanced Hunting overview](advanced-hunting-overview.md).</span></span>

- <span data-ttu-id="3baf2-129">고급 헌팅에서 **DeviceInfo** 테이블에는 장치 그룹이 포함된 **MachineGroup이라는** 열이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3baf2-129">In Advanced Hunting, the **DeviceInfo** table has a column named **MachineGroup** which contains the group of the device.</span></span> <span data-ttu-id="3baf2-130">여기에서 모든 이벤트도 이 열로 장식됩니다.</span><span class="sxs-lookup"><span data-stu-id="3baf2-130">Here every event will be decorated with this column as well.</span></span> <span data-ttu-id="3baf2-131">자세한 [내용은 장치 그룹을](machine-groups.md) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3baf2-131">See [Device Groups](machine-groups.md) for more information.</span></span>

## <a name="data-types-mapping"></a><span data-ttu-id="3baf2-132">데이터 형식 매핑:</span><span class="sxs-lookup"><span data-stu-id="3baf2-132">Data types mapping:</span></span>

<span data-ttu-id="3baf2-133">이벤트 속성에 대한 데이터 형식을 얻기 위해 다음을 합니다.</span><span class="sxs-lookup"><span data-stu-id="3baf2-133">In order to get the data types for our events properties do the following:</span></span>

1. <span data-ttu-id="3baf2-134">[Microsoft Defender 보안 센터에 로그인하고](https://securitycenter.windows.com) 고급 헌팅 [페이지로 이동합니다.](https://securitycenter.windows.com/hunting-package)</span><span class="sxs-lookup"><span data-stu-id="3baf2-134">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com) and go to [Advanced Hunting page](https://securitycenter.windows.com/hunting-package).</span></span>

2. <span data-ttu-id="3baf2-135">다음 쿼리를 실행하여 각 이벤트에 대한 데이터 형식 매핑을 구합니다.</span><span class="sxs-lookup"><span data-stu-id="3baf2-135">Run the following query to get the data types mapping for each event:</span></span> 

   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- <span data-ttu-id="3baf2-136">장치 정보 이벤트의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3baf2-136">Here is an example for Device Info event:</span></span> 

  ![이벤트 허브 리소스 ID3의 이미지](images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="3baf2-138">관련 항목</span><span class="sxs-lookup"><span data-stu-id="3baf2-138">Related topics</span></span>
- [<span data-ttu-id="3baf2-139">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="3baf2-139">Overview of Advanced Hunting</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="3baf2-140">끝점 스트리밍 API용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3baf2-140">Microsoft Defender for Endpoint Streaming API</span></span>](raw-data-export.md)
- [<span data-ttu-id="3baf2-141">Azure 저장소 계정으로 Endpoint용 Microsoft Defender 이벤트 스트림</span><span class="sxs-lookup"><span data-stu-id="3baf2-141">Stream Microsoft Defender for Endpoint events to your Azure storage account</span></span>](raw-data-export-storage.md)
- [<span data-ttu-id="3baf2-142">Azure Storage 계정 설명서</span><span class="sxs-lookup"><span data-stu-id="3baf2-142">Azure Storage Account documentation</span></span>](https://docs.microsoft.com/azure/storage/common/storage-account-overview)
