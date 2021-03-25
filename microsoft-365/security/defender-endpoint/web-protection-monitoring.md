---
title: Microsoft Defender ATP에서 웹 검색 보안 모니터링
description: Microsoft Defender ATP의 웹 보호를 사용하여 웹 검색 보안 모니터링
keywords: 웹 보호, 웹 위협 방지, 웹 검색, 모니터링, 보고서, 카드, 도메인 목록, 보안, 피싱, 맬웨어, 악용, 웹 사이트, 네트워크 보호, Edge, Internet Explorer, Chrome, Firefox, 웹 브라우저
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 326e508fbf5a0e968e890f5727a6ae542de437c2
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186008"
---
# <a name="monitor-web-browsing-security"></a><span data-ttu-id="e949b-104">웹 검색 보안 모니터링</span><span class="sxs-lookup"><span data-stu-id="e949b-104">Monitor web browsing security</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e949b-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="e949b-105">**Applies to:**</span></span>
- [<span data-ttu-id="e949b-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e949b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e949b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e949b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="e949b-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="e949b-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e949b-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="e949b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

<span data-ttu-id="e949b-110">웹 보호를 사용하면 Microsoft Defender 보안 센터의 보고서 및 웹 보호에 > 통해 조직의 웹 **검색** 보안을 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e949b-110">Web protection lets you monitor your organization’s web browsing security through reports under **Reports > Web protection** in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="e949b-111">이 보고서에는 웹 위협 감지 통계를 제공하는 카드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e949b-111">The report contains cards that provide web threat detection statistics.</span></span>

- <span data-ttu-id="e949b-112">**시간 경과에** 대한 웹 위협 방지 감지 - 이 추세 카드는 선택한 기간(지난 30일, 지난 3개월, 지난 6개월) 동안 유형별로 검색된 웹 위협 수를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="e949b-112">**Web threat protection detections over time** - this trending card displays the number of web threats detected by type during the selected time period (Last 30 days, Last 3 months, Last 6 months)</span></span>
 
    ![시간이 지날 때 웹 위협 방지 감지를 보여주는 카드 이미지](images/wtp-blocks-over-time.png)

- <span data-ttu-id="e949b-114">**웹 위협 방지** 요약 - 이 카드는 지난 30일 동안의 총 웹 위협 감지를 표시하여 다양한 유형의 웹 위협에 대한 배포를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="e949b-114">**Web threat protection summary** - this card displays the total web threat detections in the past 30 days, showing distribution across the different types of web threats.</span></span> <span data-ttu-id="e949b-115">조각을 선택하면 악성 또는 원치 않는 웹 사이트에서 발견된 도메인 목록이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="e949b-115">Selecting a slice opens the list of the domains that were found with malicious or unwanted websites.</span></span>

    ![웹 위협 방지 요약을 보여주는 카드 이미지](images/wtp-summary.png)

>[!Note]
><span data-ttu-id="e949b-117">블록이 카드 또는 도메인 목록에 반영되기까지 최대 12시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e949b-117">It can take up to 12 hours before a block is reflected in the cards or the domain list.</span></span>

## <a name="types-of-web-threats"></a><span data-ttu-id="e949b-118">웹 위협 유형</span><span class="sxs-lookup"><span data-stu-id="e949b-118">Types of web threats</span></span>

<span data-ttu-id="e949b-119">웹 보호는 악성 및 원치 않는 웹 사이트를 다음과 같은 분류합니다.</span><span class="sxs-lookup"><span data-stu-id="e949b-119">Web protection categorizes malicious and unwanted websites as:</span></span>

- <span data-ttu-id="e949b-120">**피싱** - 사용자가 자격 증명 및 기타 중요한 정보를 유출하도록 설계된 스푸핑된 웹 양식 및 기타 피싱 메커니즘을 포함하는 웹 사이트</span><span class="sxs-lookup"><span data-stu-id="e949b-120">**Phishing** - websites that contain spoofed web forms and other phishing mechanisms designed to trick users into divulging credentials and other sensitive information</span></span>
- <span data-ttu-id="e949b-121">**악성** - 맬웨어를 호스트하고 코드를 악용하는 웹 사이트</span><span class="sxs-lookup"><span data-stu-id="e949b-121">**Malicious** - websites that host malware and exploit code</span></span>
- <span data-ttu-id="e949b-122">**사용자 지정 표시기** - 차단을 위해 사용자 지정 표시기 목록에 추가한 URL 또는 [도메인](manage-indicators.md) 웹 사이트</span><span class="sxs-lookup"><span data-stu-id="e949b-122">**Custom indicator** - websites whose URLs or domains you've added to your [custom indicator list](manage-indicators.md) for blocking</span></span>

## <a name="view-the-domain-list"></a><span data-ttu-id="e949b-123">도메인 목록 보기</span><span class="sxs-lookup"><span data-stu-id="e949b-123">View the domain list</span></span>

<span data-ttu-id="e949b-124">웹 위협 방지 요약  카드에서 특정 웹 위협 범주를 선택하여 도메인 페이지를 **열** 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e949b-124">Select a specific web threat category in the **Web threat protection summary** card to open the **Domains** page.</span></span> <span data-ttu-id="e949b-125">이 페이지에는 해당 위협 범주의 도메인 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e949b-125">This page displays the list of the domains under that threat category.</span></span> <span data-ttu-id="e949b-126">이 페이지에서는 각 도메인에 대해 다음 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e949b-126">The page provides the following information for each domain:</span></span>

- <span data-ttu-id="e949b-127">**액세스 횟수** - 도메인의 URL에 대한 요청 수</span><span class="sxs-lookup"><span data-stu-id="e949b-127">**Access count** - number of requests for URLs in the domain</span></span>
- <span data-ttu-id="e949b-128">**블록** - 요청이 차단된 횟수</span><span class="sxs-lookup"><span data-stu-id="e949b-128">**Blocks** - number of times requests were blocked</span></span>
- <span data-ttu-id="e949b-129">**액세스 추세** - 액세스 시도 횟수 변경</span><span class="sxs-lookup"><span data-stu-id="e949b-129">**Access trend** - change in number of access attempts</span></span>
- <span data-ttu-id="e949b-130">**위협 범주** - 웹 위협 유형</span><span class="sxs-lookup"><span data-stu-id="e949b-130">**Threat category** - type of web threat</span></span>
- <span data-ttu-id="e949b-131">**장치** - 액세스 시도가 있는 장치 수</span><span class="sxs-lookup"><span data-stu-id="e949b-131">**Devices** - number of devices with access attempts</span></span>

<span data-ttu-id="e949b-132">해당 도메인의 URL에 액세스하려고 시도한 장치 목록과 URL 목록을 확인하려면 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e949b-132">Select a domain to view the list of devices that have attempted to access URLs in that domain and the list of URLs.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e949b-133">관련 항목</span><span class="sxs-lookup"><span data-stu-id="e949b-133">Related topics</span></span>

- [<span data-ttu-id="e949b-134">웹 보호 개요</span><span class="sxs-lookup"><span data-stu-id="e949b-134">Web protection overview</span></span>](web-protection-overview.md)
- [<span data-ttu-id="e949b-135">웹 콘텐츠 필터링</span><span class="sxs-lookup"><span data-stu-id="e949b-135">Web content filtering</span></span>](web-content-filtering.md)
- [<span data-ttu-id="e949b-136">웹 위협 방지</span><span class="sxs-lookup"><span data-stu-id="e949b-136">Web threat protection</span></span>](web-threat-protection.md)
- [<span data-ttu-id="e949b-137">웹 위협에 대응</span><span class="sxs-lookup"><span data-stu-id="e949b-137">Respond to web threats</span></span>](web-protection-response.md)
