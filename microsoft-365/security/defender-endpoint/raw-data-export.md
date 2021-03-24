---
title: Endpoint용 Microsoft Defender 이벤트 스트림
description: 고급 헌팅 이벤트를 이벤트 허브 또는 Azure 저장소 계정으로 스트리밍하도록 Microsoft Defender ATP를 구성하는 방법을 설명합니다.
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
ms.openlocfilehash: 22f4e4c974b60e291273eb9bebfa34583f4e2fb7
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071884"
---
# <a name="raw-data-streaming-api"></a><span data-ttu-id="e059f-104">원시 데이터 스트리밍 API</span><span class="sxs-lookup"><span data-stu-id="e059f-104">Raw Data Streaming API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e059f-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="e059f-105">**Applies to:**</span></span>
- [<span data-ttu-id="e059f-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e059f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="e059f-107">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="e059f-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e059f-108">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="e059f-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a><span data-ttu-id="e059f-109">고급 헌팅 이벤트를 이벤트 허브 및/또는 Azure 저장소 계정으로 스트리밍합니다.</span><span class="sxs-lookup"><span data-stu-id="e059f-109">Stream Advanced Hunting events to Event Hubs and/or Azure storage account.</span></span>

<span data-ttu-id="e059f-110">Endpoint용 Defender는 고급 헌팅을 통해 사용할 수 있는 모든 이벤트를 이벤트 [허브](https://docs.microsoft.com/azure/event-hubs/) 및/또는 Azure 저장소 계정으로 [스트리밍할 수 있도록 지원합니다.](https://docs.microsoft.com/azure/event-hubs/) [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="e059f-110">Defender for Endpoint supports streaming all the events available through [Advanced Hunting](advanced-hunting-overview.md) to an [Event Hubs](https://docs.microsoft.com/azure/event-hubs/) and/or [Azure storage account](https://docs.microsoft.com/azure/event-hubs/).</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4ga]


## <a name="in-this-section"></a><span data-ttu-id="e059f-111">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="e059f-111">In this section</span></span>

<span data-ttu-id="e059f-112">항목</span><span class="sxs-lookup"><span data-stu-id="e059f-112">Topic</span></span> | <span data-ttu-id="e059f-113">설명</span><span class="sxs-lookup"><span data-stu-id="e059f-113">Description</span></span>
:---|:---
[<span data-ttu-id="e059f-114">Azure 이벤트 허브로 끝점용 Microsoft Defender 이벤트 스트림</span><span class="sxs-lookup"><span data-stu-id="e059f-114">Stream Microsoft Defender for Endpoint events to Azure Event Hubs</span></span>](raw-data-export-event-hub.md)| <span data-ttu-id="e059f-115">테넌트에서 스트리밍 API를 사용하도록 설정하는 방법을 알아보고 [](advanced-hunting-overview.md) 고급 헌팅을 이벤트 허브로 스트리밍하도록 끝점용 Defender를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="e059f-115">Learn about enabling the streaming API in your tenant and configure Defender for Endpoint to stream [Advanced Hunting](advanced-hunting-overview.md) to Event Hubs.</span></span>
[<span data-ttu-id="e059f-116">Azure 저장소 계정으로 끝점 이벤트용 Stream Defender</span><span class="sxs-lookup"><span data-stu-id="e059f-116">Stream Defender for Endpoint events to your Azure storage account</span></span>](raw-data-export-storage.md)| <span data-ttu-id="e059f-117">테넌트에서 스트리밍 API를 사용하도록 설정하는 방법을 알아보고 [](advanced-hunting-overview.md) Azure 저장소 계정으로 고급 헌팅을 스트리밍하도록 끝점용 Defender를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="e059f-117">Learn about enabling the streaming API in your tenant and configure Defender for Endpoint to stream [Advanced Hunting](advanced-hunting-overview.md) to your Azure storage account.</span></span>


## <a name="related-topics"></a><span data-ttu-id="e059f-118">관련 항목</span><span class="sxs-lookup"><span data-stu-id="e059f-118">Related topics</span></span>
- [<span data-ttu-id="e059f-119">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="e059f-119">Overview of Advanced Hunting</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e059f-120">Azure 이벤트 허브 설명서</span><span class="sxs-lookup"><span data-stu-id="e059f-120">Azure Event Hubs documentation</span></span>](https://docs.microsoft.com/azure/event-hubs/)
- [<span data-ttu-id="e059f-121">Azure Storage 계정 설명서</span><span class="sxs-lookup"><span data-stu-id="e059f-121">Azure Storage Account documentation</span></span>](https://docs.microsoft.com/azure/storage/common/storage-account-overview)
