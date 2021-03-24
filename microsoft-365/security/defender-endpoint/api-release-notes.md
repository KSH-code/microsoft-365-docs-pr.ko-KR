---
title: 끝점용 Microsoft Defender API 릴리스 정보
description: 끝점 API 집합용 Microsoft Defender에 대한 업데이트에 대한 릴리스 정보입니다.
keywords: 끝점 api 릴리스 정보, mde, api, mdatp api, 업데이트, 메모, 릴리스용 microsoft defender
search.product: eADQiWindows 10XVcnh
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
ms.openlocfilehash: e37841fa17a5998c431c6a76b878f20ef1b06d10
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51069844"
---
# <a name="microsoft-defender-for-endpoint-api-release-notes"></a><span data-ttu-id="19afd-104">끝점용 Microsoft Defender API 릴리스 정보</span><span class="sxs-lookup"><span data-stu-id="19afd-104">Microsoft Defender for Endpoint API release notes</span></span>

<span data-ttu-id="19afd-105">**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="19afd-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="19afd-106">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="19afd-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="19afd-107">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="19afd-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="19afd-108">다음 정보에는 끝점 API용 Microsoft Defender에 대한 업데이트와 업데이트 날짜가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="19afd-108">The following information lists the updates made to the Microsoft Defender for Endpoint APIs and the dates they were made.</span></span>


> [!TIP]
> <span data-ttu-id="19afd-109">RSS 피드: 다음 URL을 복사하여 피드 읽기에 붙여 넣는 방법을 통해 이 페이지가 업데이트될 때 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19afd-109">RSS feed: Get notified when this page is updated by copying and pasting the following URL into your feed reader:</span></span> 
>```
>https://docs.microsoft.com/api/search/rss?search=%22Release+notes+for+updates+made+to+the+Microsoft+Defender+for+Endpoint+set+of+APIs%22&locale=en-us&facet=&%24filter=scopes%2Fany%28t%3A+t+eq+%27Windows+10%27%29
>```


### <a name="10022021"></a><span data-ttu-id="19afd-110">10.02.2021</span><span class="sxs-lookup"><span data-stu-id="19afd-110">10.02.2021</span></span>
<hr>

- <span data-ttu-id="19afd-111">새 API 추가: [일괄 업데이트 경고 .](batch-update-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="19afd-111">Added new API: [Batch update alerts](batch-update-alerts.md).</span></span> 

<br>

### <a name="25012021"></a><span data-ttu-id="19afd-112">25.01.2021</span><span class="sxs-lookup"><span data-stu-id="19afd-112">25.01.2021</span></span>
<hr>

- <span data-ttu-id="19afd-113">고급 헌팅 [API에](run-advanced-query-api.md) 대한 속도 제한이 분당 15개에서 45회로 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="19afd-113">Updated rate limitations for [Advanced Hunting API](run-advanced-query-api.md) from 15 to 45 requests per minute.</span></span> 

<br>

### <a name="21012021"></a><span data-ttu-id="19afd-114">21.01.2021</span><span class="sxs-lookup"><span data-stu-id="19afd-114">21.01.2021</span></span>
<hr>

- <span data-ttu-id="19afd-115">새 API 추가: [태그로 장치 찾기.](machine-tags.md)</span><span class="sxs-lookup"><span data-stu-id="19afd-115">Added new API: [Find devices by tag](machine-tags.md).</span></span> 
- <span data-ttu-id="19afd-116">새 API 추가: [가져오기 표시기](import-ti-indicators.md).</span><span class="sxs-lookup"><span data-stu-id="19afd-116">Added new API: [Import Indicators](import-ti-indicators.md).</span></span> 

<br>

### <a name="03012021"></a><span data-ttu-id="19afd-117">03.01.2021</span><span class="sxs-lookup"><span data-stu-id="19afd-117">03.01.2021</span></span>
<hr>

- <span data-ttu-id="19afd-118">업데이트된 경고 증거: ***detectionStatus** _, _*_parentProcessFilePath_*_ 및 _ *_parentProcessFileName_** 속성이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="19afd-118">Updated Alert evidence: added ***detectionStatus** _, _*_parentProcessFilePath_*_ and _ *_parentProcessFileName_** properties.</span></span>
- <span data-ttu-id="19afd-119">경고 엔터티 [업데이트:](alerts.md) ***detectorId 속성이 추가되었습니다.***</span><span class="sxs-lookup"><span data-stu-id="19afd-119">Updated [Alert entity](alerts.md): added ***detectorId*** property.</span></span>

<br>

### <a name="15122020"></a><span data-ttu-id="19afd-120">15.12.2020</span><span class="sxs-lookup"><span data-stu-id="19afd-120">15.12.2020</span></span>
<hr>

- <span data-ttu-id="19afd-121">업데이트된 [장치](machine.md) 엔터티: ***IpInterfaces 목록이 추가되었습니다.***</span><span class="sxs-lookup"><span data-stu-id="19afd-121">Updated [Device](machine.md) entity: added ***IpInterfaces*** list.</span></span> <span data-ttu-id="19afd-122">장치 [목록 을 참조하세요.](get-machines.md)</span><span class="sxs-lookup"><span data-stu-id="19afd-122">See [List devices](get-machines.md).</span></span>

<br>

### <a name="04112020"></a><span data-ttu-id="19afd-123">04.11.2020</span><span class="sxs-lookup"><span data-stu-id="19afd-123">04.11.2020</span></span>
<hr>

- <span data-ttu-id="19afd-124">새 API 추가: [장치 값 설정](set-device-value.md).</span><span class="sxs-lookup"><span data-stu-id="19afd-124">Added new API: [Set device value](set-device-value.md).</span></span>
- <span data-ttu-id="19afd-125">장치 [엔터티](machine.md) 업데이트: ***deviceValue 속성이 추가되었습니다.***</span><span class="sxs-lookup"><span data-stu-id="19afd-125">Updated [Device](machine.md) entity: added ***deviceValue*** property.</span></span>

<br>

### <a name="01092020"></a><span data-ttu-id="19afd-126">01.09.2020</span><span class="sxs-lookup"><span data-stu-id="19afd-126">01.09.2020</span></span>
<hr>

- <span data-ttu-id="19afd-127">관련 증거를 사용하여 경고 엔터티를 확장하는 옵션이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="19afd-127">Added option to expand the Alert entity with its related Evidence.</span></span> <span data-ttu-id="19afd-128">경고 [목록 을 참조하세요.](get-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="19afd-128">See [List Alerts](get-alerts.md).</span></span>

<br>
<br>