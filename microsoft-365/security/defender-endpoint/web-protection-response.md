---
title: 끝점용 Microsoft Defender의 웹 위협에 대응
description: 악성 및 원치 않는 웹 사이트와 관련된 경고에 응답합니다. 웹 위협 방지가 최종 사용자에게 웹 브라우저 및 알림 메시지를 Windows 방법 이해
keywords: 웹 보호, 웹 위협 방지, 웹 검색, 경고, 응답, 보안, 피싱, 맬웨어, 악용, 웹 사이트, 네트워크 보호, Edge, Internet Explorer, Chrome, Firefox, 웹 브라우저, 알림, 최종 사용자, Windows 알림, 차단 페이지,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 110b379863b4c6e23c947c56faf831e136231237
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688480"
---
# <a name="respond-to-web-threats"></a><span data-ttu-id="e8783-105">웹 위협에 대응</span><span class="sxs-lookup"><span data-stu-id="e8783-105">Respond to web threats</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e8783-106">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="e8783-106">**Applies to:**</span></span>
- [<span data-ttu-id="e8783-107">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e8783-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e8783-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e8783-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="e8783-109">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="e8783-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e8783-110">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="e8783-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

<span data-ttu-id="e8783-111">끝점용 Microsoft Defender의 웹 보호를 사용하면 사용자 지정 표시기 목록에서 악성 웹 사이트 및 웹 사이트와 관련된 경고를 효율적으로 조사하고 대응할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8783-111">Web protection in Microsoft Defender for Endpoint lets you efficiently investigate and respond to alerts related to malicious websites and websites in your custom indicator list.</span></span>

## <a name="view-web-threat-alerts"></a><span data-ttu-id="e8783-112">웹 위협 경고 보기</span><span class="sxs-lookup"><span data-stu-id="e8783-112">View web threat alerts</span></span>
<span data-ttu-id="e8783-113">끝점용 Microsoft Defender는 [](manage-alerts.md) 악성 또는 의심스러운 웹 활동에 대해 다음 경고를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e8783-113">Microsoft Defender for Endpoint generates the following [alerts](manage-alerts.md) for malicious or suspicious web activity:</span></span>
- <span data-ttu-id="e8783-114">**네트워크 보호로** 차단된 의심스러운 연결 - 이 경고는 차단 모드에서 네트워크 보호에 의해 사용자  지정 표시기 목록의 악성 웹 사이트 또는 웹 사이트에 액세스하려는 시도가 중지될 때 *생성됩니다.*</span><span class="sxs-lookup"><span data-stu-id="e8783-114">**Suspicious connection blocked by network protection** — this alert is generated when an attempt to access a malicious website or a website in your custom indicator list is *stopped* by network protection in *block* mode</span></span>
- <span data-ttu-id="e8783-115">**네트워크 보호에서** 감지된 의심스러운 연결 - 이 경고는 감사 전용 모드에서 네트워크 보호에 의해 사용자 지정 표시기 목록의 악성 웹 사이트 또는 웹 사이트에 액세스하려고 시도할 때 *생성됩니다.*</span><span class="sxs-lookup"><span data-stu-id="e8783-115">**Suspicious connection detected by network protection** — this alert is generated when an attempt to access a malicious website or a website in your custom indicator list is detected by network protection in *audit only* mode</span></span>

<span data-ttu-id="e8783-116">각 경고는 다음 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e8783-116">Each alert provides the following information:</span></span> 
- <span data-ttu-id="e8783-117">차단된 웹 사이트에 액세스하려고 시도한 장치</span><span class="sxs-lookup"><span data-stu-id="e8783-117">Device that attempted to access the blocked website</span></span>
- <span data-ttu-id="e8783-118">웹 요청을 보내는 데 사용되는 응용 프로그램 또는 프로그램</span><span class="sxs-lookup"><span data-stu-id="e8783-118">Application or program used to send the web request</span></span>
- <span data-ttu-id="e8783-119">사용자 지정 표시기 목록의 악의적인 URL 또는 URL</span><span class="sxs-lookup"><span data-stu-id="e8783-119">Malicious URL or URL in the custom indicator list</span></span>
- <span data-ttu-id="e8783-120">응답자에 대한 권장 작업</span><span class="sxs-lookup"><span data-stu-id="e8783-120">Recommended actions for responders</span></span>

![웹 위협 방지와 관련된 경고 이미지](images/wtp-alert.png)

>[!Note]
><span data-ttu-id="e8783-122">경고 볼륨을 줄이기 위해 끝점용 Microsoft Defender는 매일 동일한 장치에서 동일한 도메인에 대한 웹 위협 감지를 단일 경고로 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="e8783-122">To reduce the volume of alerts, Microsoft Defender for Endpoint consolidates web threat detections for the same domain on the same device each day to a single alert.</span></span> <span data-ttu-id="e8783-123">하나의 경고만 생성되어 웹 보호 보고서 [에 계산됩니다.](web-protection-monitoring.md)</span><span class="sxs-lookup"><span data-stu-id="e8783-123">Only one alert is generated and counted into the [web protection report](web-protection-monitoring.md).</span></span>

## <a name="inspect-website-details"></a><span data-ttu-id="e8783-124">웹 사이트 세부 정보 검사</span><span class="sxs-lookup"><span data-stu-id="e8783-124">Inspect website details</span></span>
<span data-ttu-id="e8783-125">경고에서 웹 사이트의 URL 또는 도메인을 선택하여 더 깊이 있는 검색을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8783-125">You can dive deeper by selecting the URL or domain of the website in the alert.</span></span> <span data-ttu-id="e8783-126">그러면 다음을 비롯한 다양한 정보가 있는 해당 특정 URL 또는 도메인에 대한 페이지가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="e8783-126">This opens a page about that particular URL or domain with various information, including:</span></span>
- <span data-ttu-id="e8783-127">웹 사이트에 액세스하려고 시도한 장치</span><span class="sxs-lookup"><span data-stu-id="e8783-127">Devices that attempted to access website</span></span>
- <span data-ttu-id="e8783-128">웹 사이트와 관련된 인시던트 및 알림</span><span class="sxs-lookup"><span data-stu-id="e8783-128">Incidents and alerts related to the website</span></span>
- <span data-ttu-id="e8783-129">조직의 이벤트에 웹 사이트가 얼마나 자주 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8783-129">How frequent the website was seen in events in your organization</span></span>

    ![도메인 또는 URL 엔터티 세부 정보 페이지의 이미지](images/wtp-website-details.png)

[<span data-ttu-id="e8783-131">URL 또는 도메인 엔터티 페이지에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="e8783-131">Learn more about URL or domain entity pages</span></span>](investigate-domain.md)

## <a name="inspect-the-device"></a><span data-ttu-id="e8783-132">장치 검사</span><span class="sxs-lookup"><span data-stu-id="e8783-132">Inspect the device</span></span>
<span data-ttu-id="e8783-133">차단된 URL에 액세스하려고 시도한 장치를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8783-133">You can also check the device that attempted to access a blocked URL.</span></span> <span data-ttu-id="e8783-134">경고 페이지에서 디바이스 이름을 선택하면 장치에 대한 포괄적인 정보가 있는 페이지가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="e8783-134">Selecting the name of the device on the alert page opens a page with comprehensive information about the device.</span></span>

[<span data-ttu-id="e8783-135">장치 엔터티 페이지에 대한 자세한 내용은</span><span class="sxs-lookup"><span data-stu-id="e8783-135">Learn more about device entity pages</span></span>](investigate-machines.md)

## <a name="web-browser-and-windows-notifications-for-end-users"></a><span data-ttu-id="e8783-136">웹 브라우저 및 Windows 사용자에 대한 알림</span><span class="sxs-lookup"><span data-stu-id="e8783-136">Web browser and Windows notifications for end users</span></span>

<span data-ttu-id="e8783-137">Endpoint용 Microsoft Defender의 웹 보호를 통해 최종 사용자는 웹 사이트 또는 기타 브라우저를 사용하여 악성 또는 원치 않는 웹 Microsoft Edge 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8783-137">With web protection in Microsoft Defender for Endpoint, your end users will be prevented from visiting malicious or unwanted websites using Microsoft Edge or other browsers.</span></span> <span data-ttu-id="e8783-138">차단은 네트워크 보호에서 [수행하기](network-protection.md)때문에 웹 브라우저에서 일반 오류가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8783-138">Because blocking is performed by [network protection](network-protection.md), they will see a generic error from the web browser.</span></span> <span data-ttu-id="e8783-139">또한 사용자로부터 알림이 Windows.</span><span class="sxs-lookup"><span data-stu-id="e8783-139">They will also see a notification from Windows.</span></span>

<span data-ttu-id="e8783-140">![403 Microsoft Edge 웹 위협이 차단된 Windows 웹 위협을 보여 Microsoft Edge ](images/wtp-browser-blocking-page.png)
 </span><span class="sxs-lookup"><span data-stu-id="e8783-140">![Image of Microsoft Edge showing a 403 error and the Windows notification](images/wtp-browser-blocking-page.png)
*Web threat blocked on Microsoft Edge*</span></span>

<span data-ttu-id="e8783-141">![보안 연결 경고 및 Chrome에서 차단된 보안 Windows 웹 위협을 표시하는 Chrome 웹 ](images/wtp-chrome-browser-blocking-page.png)
 *브라우저의 이미지*</span><span class="sxs-lookup"><span data-stu-id="e8783-141">![Image of Chrome web browser showing a secure connection warning and the Windows notification](images/wtp-chrome-browser-blocking-page.png)
*Web threat blocked on Chrome*</span></span>

## <a name="related-topics"></a><span data-ttu-id="e8783-142">관련 항목</span><span class="sxs-lookup"><span data-stu-id="e8783-142">Related topics</span></span>
- [<span data-ttu-id="e8783-143">웹 보호 개요</span><span class="sxs-lookup"><span data-stu-id="e8783-143">Web protection overview</span></span>](web-protection-overview.md)
- [<span data-ttu-id="e8783-144">웹 컨텐츠 필터링</span><span class="sxs-lookup"><span data-stu-id="e8783-144">Web content filtering</span></span>](web-content-filtering.md)
- [<span data-ttu-id="e8783-145">웹 위협 방지</span><span class="sxs-lookup"><span data-stu-id="e8783-145">Web threat protection</span></span>](web-threat-protection.md)
- [<span data-ttu-id="e8783-146">웹 보안 모니터링</span><span class="sxs-lookup"><span data-stu-id="e8783-146">Monitor web security</span></span>](web-protection-monitoring.md)
