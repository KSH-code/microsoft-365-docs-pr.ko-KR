---
title: 이벤트 Microsoft 365 Defender 스트림 저장소 계정으로
description: 고급 헌팅 이벤트를 Microsoft 365 Defender 헌팅 이벤트를 사용자 계정으로 스트리밍하도록 구성하는 저장소 대해 자세히 알아보도록 합니다.
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
ms.openlocfilehash: fa61e2fd0591d375a17bad6e166a76c1ca40862e
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028898"
---
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-storage-account"></a><span data-ttu-id="4c69b-104">고급 Microsoft 365 Defender 헌팅 이벤트를 사용자 계정으로 저장소 구성</span><span class="sxs-lookup"><span data-stu-id="4c69b-104">Configure Microsoft 365 Defender to stream Advanced Hunting events to your Storage account</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="4c69b-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="4c69b-105">**Applies to:**</span></span>
- [<span data-ttu-id="4c69b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4c69b-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]


## <a name="before-you-begin"></a><span data-ttu-id="4c69b-107">시작하기 전에 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c69b-107">Before you begin:</span></span>

1. <span data-ttu-id="4c69b-108">[테넌트에서 저장소 계정을](/azure/storage/common/storage-account-overview) 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c69b-108">Create a [Storage account](/azure/storage/common/storage-account-overview) in your tenant.</span></span>

2. <span data-ttu-id="4c69b-109">[Azure](https://ms.portal.azure.com/)테넌트에 로그인하고, **Microsoft.>** 구독 > 리소스 공급자로 >.Insights.</span><span class="sxs-lookup"><span data-stu-id="4c69b-109">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to **Subscriptions > Your subscription > Resource Providers > Register to Microsoft.Insights**.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="4c69b-110">원시 데이터 스트리밍을 사용하도록 설정:</span><span class="sxs-lookup"><span data-stu-id="4c69b-110">Enable raw data streaming:</span></span>

1. <span data-ttu-id="4c69b-111">\* Microsoft 365 Defender [](https://security.microsoft.com) 보안 센터에 ***전역** 관리자 _ 또는 _* 보안 관리자 \*\*로 _로그인합니다._</span><span class="sxs-lookup"><span data-stu-id="4c69b-111">Log in to [Microsoft 365 Defender security center](https://security.microsoft.com) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="4c69b-112">에서 [데이터 내보내기 설정](https://security.microsoft.com/settings/mtp_settings/raw_data_export) 페이지로 Microsoft Defender 보안 센터.</span><span class="sxs-lookup"><span data-stu-id="4c69b-112">Go to [Data export settings page](https://security.microsoft.com/settings/mtp_settings/raw_data_export) in Microsoft Defender Security Center.</span></span>

3. <span data-ttu-id="4c69b-113">데이터 **내보내기 설정 추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="4c69b-113">Click on **Add data export settings**.</span></span>

4. <span data-ttu-id="4c69b-114">새 설정의 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4c69b-114">Choose a name for your new settings.</span></span>

5. <span data-ttu-id="4c69b-115">에 **전달 이벤트를 Azure 저장소.**</span><span class="sxs-lookup"><span data-stu-id="4c69b-115">Choose **Forward events to Azure Storage**.</span></span>

6. <span data-ttu-id="4c69b-116">저장소 **계정 리소스 ID를 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="4c69b-116">Type your **Storage Account Resource ID**.</span></span> <span data-ttu-id="4c69b-117">계정 리소스 **ID를 저장소하려면** Azure > [Portal](https://ms.portal.azure.com/) 저장소 속성 탭의 저장소 계정 페이지로 이동하고 > 계정 리소스 ID 아래에 있는 저장소 **복사합니다.**</span><span class="sxs-lookup"><span data-stu-id="4c69b-117">In order to get your **Storage Account Resource ID**, go to your Storage account page on [Azure portal](https://ms.portal.azure.com/) > properties tab > copy the text under **Storage Account Resource ID**:</span></span>

   ![이벤트 허브 리소스 ID1의 이미지](../defender-endpoint/images/storage-account-resource-id.png)

7. <span data-ttu-id="4c69b-119">스트리밍할 이벤트를 선택하고 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="4c69b-119">Choose the events you want to stream and click **Save**.</span></span>

## <a name="the-schema-of-the-events-in-the-storage-account"></a><span data-ttu-id="4c69b-120">이벤트 계정의 이벤트 저장소:</span><span class="sxs-lookup"><span data-stu-id="4c69b-120">The schema of the events in the Storage account:</span></span>

- <span data-ttu-id="4c69b-121">각 이벤트 유형에 대해 Blob 컨테이너가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="4c69b-121">A blob container will be created for each event type:</span></span> 

  ![이벤트 허브 리소스 ID2의 이미지](../defender-endpoint/images/storage-account-event-schema.png)

- <span data-ttu-id="4c69b-123">Blob에 있는 각 행의 Schema는 다음과 같은 JSON입니다.</span><span class="sxs-lookup"><span data-stu-id="4c69b-123">The schema of each row in a blob is the following JSON:</span></span> 

  ```
  {
          "time": "<The time Microsoft 365 Defender received the event>"
          "tenantId": "<Your tenant ID>"
          "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
          "properties": { <Microsoft 365 Defender Advanced Hunting event as Json> }
  }               
  ```

- <span data-ttu-id="4c69b-124">각 Blob에는 여러 행이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c69b-124">Each blob contains multiple rows.</span></span>

- <span data-ttu-id="4c69b-125">각 행에는 이벤트 이름, Endpoint용 Defender가 이벤트를 수신한 시간, 해당 이벤트가 속한 테넌트(테넌트에서 이벤트만 수신) 및 JSON 형식의 이벤트가 "properties"라는 속성으로 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c69b-125">Each row contains the event name, the time Defender for Endpoint received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "properties".</span></span>

- <span data-ttu-id="4c69b-126">이벤트의 SCHEMA에 대한 자세한 내용은 Microsoft 365 Defender [헌팅 개요를 참조하세요.](../defender/advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="4c69b-126">For more information about the schema of Microsoft 365 Defender events, see [Advanced Hunting overview](../defender/advanced-hunting-overview.md).</span></span>


## <a name="data-types-mapping"></a><span data-ttu-id="4c69b-127">데이터 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="4c69b-127">Data types mapping</span></span>

<span data-ttu-id="4c69b-128">이벤트 속성에 대한 데이터 형식을 얻기 위해 다음을 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c69b-128">In order to get the data types for our events properties do the following:</span></span>

1. <span data-ttu-id="4c69b-129">보안 센터에 [Microsoft 365 고급](https://security.microsoft.com) 헌팅 [페이지로 이동합니다.](https://security.microsoft.com/hunting-package)</span><span class="sxs-lookup"><span data-stu-id="4c69b-129">Log in to [Microsoft 365 security center](https://security.microsoft.com) and go to [Advanced Hunting page](https://security.microsoft.com/hunting-package).</span></span>

2. <span data-ttu-id="4c69b-130">다음 쿼리를 실행하여 각 이벤트에 대한 데이터 형식 매핑을 구합니다.</span><span class="sxs-lookup"><span data-stu-id="4c69b-130">Run the following query to get the data types mapping for each event:</span></span> 

   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- <span data-ttu-id="4c69b-131">장치 정보 이벤트의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4c69b-131">Here is an example for Device Info event:</span></span> 

  ![이벤트 허브 리소스 ID3의 이미지](../defender-endpoint/images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="4c69b-133">관련 항목</span><span class="sxs-lookup"><span data-stu-id="4c69b-133">Related topics</span></span>
- [<span data-ttu-id="4c69b-134">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="4c69b-134">Overview of Advanced Hunting</span></span>](../defender/advanced-hunting-overview.md)
- [<span data-ttu-id="4c69b-135">Microsoft 365 Defender 스트리밍 API</span><span class="sxs-lookup"><span data-stu-id="4c69b-135">Microsoft 365 Defender Streaming API</span></span>](streaming-api.md)
- [<span data-ttu-id="4c69b-136">Azure Microsoft 365 Defender 이벤트 스트림</span><span class="sxs-lookup"><span data-stu-id="4c69b-136">Stream Microsoft 365 Defender events to your Azure storage account</span></span>](streaming-api-storage.md)
- [<span data-ttu-id="4c69b-137">Azure 저장소 계정 설명서</span><span class="sxs-lookup"><span data-stu-id="4c69b-137">Azure Storage Account documentation</span></span>](/azure/storage/common/storage-account-overview)
