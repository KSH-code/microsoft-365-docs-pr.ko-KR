---
title: 끝점용 Microsoft Defender API 릴리스 정보
description: 끝점 API 집합용 Microsoft Defender에 대한 업데이트에 대한 릴리스 정보입니다.
keywords: Endpoint API 릴리스 정보, mde, API, Endpoint용 Microsoft Defender API, 업데이트, 메모, 릴리스
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 4843894638ccf119c0cadcf003e159e793c18368
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843737"
---
# <a name="microsoft-defender-for-endpoint-api-release-notes"></a><span data-ttu-id="f2fcc-104">끝점용 Microsoft Defender API 릴리스 정보</span><span class="sxs-lookup"><span data-stu-id="f2fcc-104">Microsoft Defender for Endpoint API release notes</span></span>

<span data-ttu-id="f2fcc-105">**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="f2fcc-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="f2fcc-106">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="f2fcc-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f2fcc-107">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="f2fcc-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="f2fcc-108">다음 정보에는 끝점 API용 Microsoft Defender에 대한 업데이트와 업데이트 날짜가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2fcc-108">The following information lists the updates made to the Microsoft Defender for Endpoint APIs and the dates they were made.</span></span>

> [!TIP]
> <span data-ttu-id="f2fcc-109">RSS 피드: 다음 URL을 복사하여 피드 읽기에 붙여 넣는 방법을 통해 이 페이지가 업데이트될 때 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2fcc-109">RSS feed: Get notified when this page is updated by copying and pasting the following URL into your feed reader:</span></span>
>
> ```http
> /api/search/rss?search=%22Release+notes+for+updates+made+to+the+Microsoft+Defender+for+Endpoint+set+of+APIs%22&locale=en-us&facet=&%24filter=scopes%2Fany%28t%3A+t+eq+%27Windows+10%27%29
> ```

## <a name="release-notes---newest-to-oldest-ddmmyyyy"></a><span data-ttu-id="f2fcc-110">릴리스 정보 - 가장 오래된 버전(dd.mm.yyyy)</span><span class="sxs-lookup"><span data-stu-id="f2fcc-110">Release notes - newest to oldest (dd.mm.yyyy)</span></span>

### <a name="05252021"></a><span data-ttu-id="f2fcc-111">05.25.2021</span><span class="sxs-lookup"><span data-stu-id="f2fcc-111">05.25.2021</span></span>

- <span data-ttu-id="f2fcc-112">장치당 새 API [내보내기 평가 방법 및 속성이 추가되었습니다.](get-assessment-methods-properties.md)</span><span class="sxs-lookup"><span data-stu-id="f2fcc-112">Added new API [Export assessment methods and properties per device](get-assessment-methods-properties.md).</span></span>

### <a name="03052021"></a><span data-ttu-id="f2fcc-113">03.05.2021</span><span class="sxs-lookup"><span data-stu-id="f2fcc-113">03.05.2021</span></span>

- <span data-ttu-id="f2fcc-114">새로운 API 추가: [재구성 활동 메서드 및 속성](get-remediation-methods-properties.md).</span><span class="sxs-lookup"><span data-stu-id="f2fcc-114">Added new API: [Remediation activity methods and properties](get-remediation-methods-properties.md).</span></span>

### <a name="10022021"></a><span data-ttu-id="f2fcc-115">10.02.2021</span><span class="sxs-lookup"><span data-stu-id="f2fcc-115">10.02.2021</span></span>

- <span data-ttu-id="f2fcc-116">새 API 추가: [일괄 업데이트 경고 .](batch-update-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="f2fcc-116">Added new API: [Batch update alerts](batch-update-alerts.md).</span></span>

### <a name="25012021"></a><span data-ttu-id="f2fcc-117">25.01.2021</span><span class="sxs-lookup"><span data-stu-id="f2fcc-117">25.01.2021</span></span>

- <span data-ttu-id="f2fcc-118">고급 헌팅 [API에](run-advanced-query-api.md) 대한 속도 제한이 분당 15개에서 45회로 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f2fcc-118">Updated rate limitations for [Advanced Hunting API](run-advanced-query-api.md) from 15 to 45 requests per minute.</span></span>

### <a name="21012021"></a><span data-ttu-id="f2fcc-119">21.01.2021</span><span class="sxs-lookup"><span data-stu-id="f2fcc-119">21.01.2021</span></span>

- <span data-ttu-id="f2fcc-120">새 API 추가: [태그로 장치 찾기.](machine-tags.md)</span><span class="sxs-lookup"><span data-stu-id="f2fcc-120">Added new API: [Find devices by tag](machine-tags.md).</span></span>
- <span data-ttu-id="f2fcc-121">새 API 추가: [가져오기 표시기](import-ti-indicators.md).</span><span class="sxs-lookup"><span data-stu-id="f2fcc-121">Added new API: [Import Indicators](import-ti-indicators.md).</span></span>

### <a name="03012021"></a><span data-ttu-id="f2fcc-122">03.01.2021</span><span class="sxs-lookup"><span data-stu-id="f2fcc-122">03.01.2021</span></span>

- <span data-ttu-id="f2fcc-123">업데이트된 경고 증거: ***detectionStatus** _, _*_parentProcessFilePath_*_ 및 _ *_parentProcessFileName_** 속성이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f2fcc-123">Updated Alert evidence: added ***detectionStatus** _, _*_parentProcessFilePath_*_ and _ *_parentProcessFileName_** properties.</span></span>
- <span data-ttu-id="f2fcc-124">경고 엔터티 [업데이트:](alerts.md) ***detectorId 속성이 추가되었습니다.***</span><span class="sxs-lookup"><span data-stu-id="f2fcc-124">Updated [Alert entity](alerts.md): added ***detectorId*** property.</span></span>

### <a name="15122020"></a><span data-ttu-id="f2fcc-125">15.12.2020</span><span class="sxs-lookup"><span data-stu-id="f2fcc-125">15.12.2020</span></span>

- <span data-ttu-id="f2fcc-126">업데이트된 [장치](machine.md) 엔터티: ***IpInterfaces 목록이 추가되었습니다.***</span><span class="sxs-lookup"><span data-stu-id="f2fcc-126">Updated [Device](machine.md) entity: added ***IpInterfaces*** list.</span></span> <span data-ttu-id="f2fcc-127">장치 [목록 을 참조하세요.](get-machines.md)</span><span class="sxs-lookup"><span data-stu-id="f2fcc-127">See [List devices](get-machines.md).</span></span>

### <a name="04112020"></a><span data-ttu-id="f2fcc-128">04.11.2020</span><span class="sxs-lookup"><span data-stu-id="f2fcc-128">04.11.2020</span></span>

- <span data-ttu-id="f2fcc-129">새 API 추가: [장치 값 설정](set-device-value.md).</span><span class="sxs-lookup"><span data-stu-id="f2fcc-129">Added new API: [Set device value](set-device-value.md).</span></span>
- <span data-ttu-id="f2fcc-130">장치 [엔터티](machine.md) 업데이트: ***deviceValue 속성이 추가되었습니다.***</span><span class="sxs-lookup"><span data-stu-id="f2fcc-130">Updated [Device](machine.md) entity: added ***deviceValue*** property.</span></span>

### <a name="01092020"></a><span data-ttu-id="f2fcc-131">01.09.2020</span><span class="sxs-lookup"><span data-stu-id="f2fcc-131">01.09.2020</span></span>

- <span data-ttu-id="f2fcc-132">관련 증거를 사용하여 경고 엔터티를 확장하는 옵션이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f2fcc-132">Added option to expand the Alert entity with its related Evidence.</span></span> <span data-ttu-id="f2fcc-133">경고 [목록 을 참조하세요.](get-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="f2fcc-133">See [List Alerts](get-alerts.md).</span></span>
