---
title: Defender Microsoft 365 스트림
description: 고급 헌팅 이벤트를 이벤트 허브 Microsoft 365 Azure 저장소 계정으로 스트리밍하도록 Defender를 구성하는 방법을 설명합니다.
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
ms.openlocfilehash: 971cc757dcbd0a190917d2a5f11eb7f68b758008
ms.sourcegitcommit: 83df0be7144c9c5d606f70b4efa65369e86693d2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/05/2021
ms.locfileid: "52778200"
---
# <a name="streaming-api"></a><span data-ttu-id="b7f49-104">스트리밍 API</span><span class="sxs-lookup"><span data-stu-id="b7f49-104">Streaming API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b7f49-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="b7f49-105">**Applies to:**</span></span>
- [<span data-ttu-id="b7f49-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b7f49-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a><span data-ttu-id="b7f49-107">고급 헌팅 이벤트를 이벤트 허브 및/또는 Azure 저장소 계정으로 스트리밍합니다.</span><span class="sxs-lookup"><span data-stu-id="b7f49-107">Stream Advanced Hunting events to Event Hubs and/or Azure storage account.</span></span>

<span data-ttu-id="b7f49-108">Microsoft 365 Defender는 고급 헌팅을 [](../defender/advanced-hunting-overview.md) 통해 사용할 수 있는 모든 이벤트를 이벤트 [허브](/azure/event-hubs/) 및/또는 Azure 저장소 계정으로 [스트리밍할 수 있도록 지원합니다.](/azure/event-hubs/)</span><span class="sxs-lookup"><span data-stu-id="b7f49-108">Microsoft 365 Defender supports streaming all the events available through [Advanced Hunting](../defender/advanced-hunting-overview.md) to an [Event Hubs](/azure/event-hubs/) and/or [Azure storage account](/azure/event-hubs/).</span></span>



## <a name="in-this-section"></a><span data-ttu-id="b7f49-109">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="b7f49-109">In this section</span></span>

<span data-ttu-id="b7f49-110">항목</span><span class="sxs-lookup"><span data-stu-id="b7f49-110">Topic</span></span> | <span data-ttu-id="b7f49-111">설명</span><span class="sxs-lookup"><span data-stu-id="b7f49-111">Description</span></span>
:---|:---
[<span data-ttu-id="b7f49-112">Azure 이벤트 허브로 이벤트 스트림</span><span class="sxs-lookup"><span data-stu-id="b7f49-112">Stream events to Azure Event Hubs</span></span>](raw-data-export-event-hub.md)| <span data-ttu-id="b7f49-113">테넌트에서 스트리밍 API를 사용하도록 설정하는 방법을 알아보고 고급 [](../defender/advanced-hunting-overview.md) 헌팅을 이벤트 허브로 Microsoft 365 Defender를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b7f49-113">Learn about enabling the streaming API in your tenant and configure Microsoft 365 Defender to stream [Advanced Hunting](../defender/advanced-hunting-overview.md) to Event Hubs.</span></span>
[<span data-ttu-id="b7f49-114">Azure 저장소 계정으로 이벤트 스트림</span><span class="sxs-lookup"><span data-stu-id="b7f49-114">Stream events to your Azure storage account</span></span>](raw-data-export-storage.md)| <span data-ttu-id="b7f49-115">테넌트에서 스트리밍 API를 사용하도록 설정하는 방법을 알아보고 Azure [](../defender/advanced-hunting-overview.md) Microsoft 365 고급 헌팅을 스트리밍하도록 Defender를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b7f49-115">Learn about enabling the streaming API in your tenant and configure Microsoft 365 Defender to stream [Advanced Hunting](../defender/advanced-hunting-overview.md) to your Azure storage account.</span></span>


## <a name="related-topics"></a><span data-ttu-id="b7f49-116">관련 항목</span><span class="sxs-lookup"><span data-stu-id="b7f49-116">Related topics</span></span>
- [<span data-ttu-id="b7f49-117">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="b7f49-117">Overview of Advanced Hunting</span></span>](../defender/advanced-hunting-overview.md)
- [<span data-ttu-id="b7f49-118">Azure 이벤트 허브 설명서</span><span class="sxs-lookup"><span data-stu-id="b7f49-118">Azure Event Hubs documentation</span></span>](/azure/event-hubs/)
- [<span data-ttu-id="b7f49-119">Azure Storage 계정 설명서</span><span class="sxs-lookup"><span data-stu-id="b7f49-119">Azure Storage Account documentation</span></span>](/azure/storage/common/storage-account-overview)
