---
title: 웹 위협으로부터 조직 보호
description: 끝점용 Microsoft Defender의 웹 보호와 조직을 보호하는 방법에 대해 자세히 알아보습니다.
keywords: 웹 보호, 웹 위협 방지, 웹 검색, 보안, 피싱, 맬웨어, 악용, 웹 사이트, 네트워크 보호, Edge, Internet Explorer, Chrome, Firefox, 웹 브라우저
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
ms.openlocfilehash: 0c42c05e318390741b94b6d7d1b5394fca961714
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688948"
---
# <a name="protect-your-organization-against-web-threats"></a><span data-ttu-id="80ea5-104">웹 위협으로부터 조직 보호</span><span class="sxs-lookup"><span data-stu-id="80ea5-104">Protect your organization against web threats</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="80ea5-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="80ea5-105">**Applies to:**</span></span>
- [<span data-ttu-id="80ea5-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="80ea5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="80ea5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="80ea5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="80ea5-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="80ea5-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="80ea5-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="80ea5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

<span data-ttu-id="80ea5-110">웹 위협 방지는 [](web-protection-overview.md) 끝점용 Defender의 웹 보호의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="80ea5-110">Web threat protection is part of [Web protection](web-protection-overview.md) in Defender for Endpoint.</span></span> <span data-ttu-id="80ea5-111">네트워크 [보호를 사용하여](network-protection.md) 웹 위협으로부터 장치를 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="80ea5-111">It uses [network protection](network-protection.md) to secure your devices against web threats.</span></span> <span data-ttu-id="80ea5-112">Chrome 및 firefox와 같은 Microsoft Edge 및 인기 있는 타사 브라우저와 통합하여 웹 위협 방지는 웹 프록시 없이 웹 위협을 중지하고 부재 중이나 사내에서 장치를 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80ea5-112">By integrating with Microsoft Edge and popular third-party browsers like Chrome and Firefox, web threat protection stops web threats without a web proxy and can protect devices while they are away or on premises.</span></span> <span data-ttu-id="80ea5-113">웹 위협 방지는 사용자 지정 표시기 목록에서 차단한 사이트뿐만 아니라 피싱 사이트, 맬웨어 벡터, 악용 사이트, 신뢰하지 못하거나 낮은 신뢰도의 사이트에 대한 액세스를 [중지합니다.](manage-indicators.md)</span><span class="sxs-lookup"><span data-stu-id="80ea5-113">Web threat protection stops access to phishing sites, malware vectors, exploit sites, untrusted or low-reputation sites, as well as sites that you have blocked in your [custom indicator list](manage-indicators.md).</span></span>

>[!Note]
><span data-ttu-id="80ea5-114">디바이스에서 새 사용자 지정 표시기를 받는 데 최대 1시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80ea5-114">It can take up to an hour for devices to receive new custom indicators.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="80ea5-115">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="80ea5-115">Prerequisites</span></span>
<span data-ttu-id="80ea5-116">웹 보호는 네트워크 보호를 사용하여 Microsoft Edge 및 타사 웹 브라우저에서 웹 검색 보안을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="80ea5-116">Web protection uses network protection to provide web browsing security on Microsoft Edge and third-party web browsers.</span></span>

<span data-ttu-id="80ea5-117">디바이스에서 네트워크 보호를 켜는 경우:</span><span class="sxs-lookup"><span data-stu-id="80ea5-117">To turn on network protection on your devices:</span></span>
- <span data-ttu-id="80ea5-118">Web & Network **Protection에서** 끝점용 Defender 보안 기준을 편집하여 네트워크 보호를 사용하도록 설정한 후 배포하거나 다시 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="80ea5-118">Edit the Defender for Endpoint security baseline under **Web & Network Protection** to enable network protection before deploying or redeploying it.</span></span> [<span data-ttu-id="80ea5-119">엔드포인트 보안 기준에 대한 Defender 검토 및 할당에 대해 자세히 알아보시고</span><span class="sxs-lookup"><span data-stu-id="80ea5-119">Learn about reviewing and assigning the Defender for Endpoint security baseline</span></span>](configure-machines-security-baseline.md#review-and-assign-the-microsoft-defender-for-endpoint-security-baseline)
- <span data-ttu-id="80ea5-120">Intune 장치 구성, SCCM, 그룹 정책 또는 MDM 솔루션을 사용하여 네트워크 보호를 켜십시오.</span><span class="sxs-lookup"><span data-stu-id="80ea5-120">Turn network protection on using Intune device configuration, SCCM, Group Policy, or your MDM solution.</span></span> [<span data-ttu-id="80ea5-121">네트워크 보호 사용에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="80ea5-121">Read more about enabling network protection</span></span>](enable-network-protection.md)  

>[!Note]
><span data-ttu-id="80ea5-122">네트워크 보호를 감사 전용으로 설정하면 차단을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="80ea5-122">If you set network protection to **Audit only**, blocking will be unavailable.</span></span> <span data-ttu-id="80ea5-123">또한 사용자 계정에서만 악성 및 원치 않는 웹 사이트에 액세스하려는 시도를 감지하고 Microsoft Edge 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80ea5-123">Also, you will be able to detect and log attempts to access malicious and unwanted websites on Microsoft Edge only.</span></span>

## <a name="related-topics"></a><span data-ttu-id="80ea5-124">관련 항목</span><span class="sxs-lookup"><span data-stu-id="80ea5-124">Related topics</span></span>

- [<span data-ttu-id="80ea5-125">웹 보호 개요</span><span class="sxs-lookup"><span data-stu-id="80ea5-125">Web protection overview</span></span>](web-protection-overview.md)
- [<span data-ttu-id="80ea5-126">웹 위협 방지</span><span class="sxs-lookup"><span data-stu-id="80ea5-126">Web threat protection</span></span>](web-threat-protection.md)
- [<span data-ttu-id="80ea5-127">웹 보안 모니터링</span><span class="sxs-lookup"><span data-stu-id="80ea5-127">Monitor web security</span></span>](web-protection-monitoring.md)
- [<span data-ttu-id="80ea5-128">웹 위협에 대응</span><span class="sxs-lookup"><span data-stu-id="80ea5-128">Respond to web threats</span></span>](web-protection-response.md)
- [<span data-ttu-id="80ea5-129">네트워크 보호</span><span class="sxs-lookup"><span data-stu-id="80ea5-129">Network protection</span></span>](network-protection.md)
