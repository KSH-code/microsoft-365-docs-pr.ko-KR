---
title: IP 및 URL/도메인에 대한 지표 만들기
ms.reviewer: ''
description: 엔터티의 검색, 방지 및 제외를 정의하는 IP 및 URL/도메인에 대한 표시기를 만들 수 있습니다.
keywords: ip, url, domain, manage, allowed, blocked, clean, malicious, file hash, ip address, urls, domain
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
ms.openlocfilehash: e7dc11fe709a6d04b6309706df90f0ebbc177e25
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841069"
---
# <a name="create-indicators-for-ips-and-urlsdomains"></a><span data-ttu-id="2cc05-104">IP 및 URL/도메인에 대한 지표 만들기</span><span class="sxs-lookup"><span data-stu-id="2cc05-104">Create indicators for IPs and URLs/domains</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2cc05-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="2cc05-105">**Applies to:**</span></span>
- [<span data-ttu-id="2cc05-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2cc05-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2cc05-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2cc05-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)



> [!TIP]
> <span data-ttu-id="2cc05-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="2cc05-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2cc05-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc05-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)


<span data-ttu-id="2cc05-110">Endpoint용 Defender는 Microsoft 브라우저용 Windows Defender SmartScreen 및 Microsoft가 아닌 다른 브라우저 또는 브라우저 외부에서 걸린 통화에 대한 네트워크 보호를 통해 Microsoft가 악성 IP/URL로 생각되는 것을 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc05-110">Defender for Endpoint can block what Microsoft deems as malicious IPs/URLs, through Windows Defender SmartScreen for Microsoft browsers, and through Network Protection for non-Microsoft browsers or calls made outside of a browser.</span></span>

<span data-ttu-id="2cc05-111">이 위협 인텔리전스 데이터 집합은 Microsoft에서 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc05-111">The threat intelligence data set for this has been managed by Microsoft.</span></span>

<span data-ttu-id="2cc05-112">이제 자신의 위협 인텔리전스를 기반으로 하여 IPS, URL 또는 도메인을 허용하거나 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc05-112">By creating indicators for IPs and URLs or domains, you can now allow or block IPs, URLs, or domains based on your own threat intelligence.</span></span> <span data-ttu-id="2cc05-113">특정 그룹이 다른 그룹보다 위험에 더 높거나 적은 것으로 생각되는 경우 설정 페이지 또는 컴퓨터 그룹을 통해 이 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc05-113">You can do this through the settings page or by machine groups if you deem certain groups to be more or less at risk than others.</span></span>

> [!NOTE]
> <span data-ttu-id="2cc05-114">IP 주소에 Inter-Domain CIDR(Classless Inter-Domain Routing) 상용화는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc05-114">Classless Inter-Domain Routing (CIDR) notation for IP addresses is not supported.</span></span> 

### <a name="before-you-begin"></a><span data-ttu-id="2cc05-115">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="2cc05-115">Before you begin</span></span>
<span data-ttu-id="2cc05-116">IPS, URL 또는 도메인에 대한 표시기를 만들기 전에 다음의 선행 구성 요소에 대해 이해하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc05-116">It's important to understand the following prerequisites prior to creating indicators for IPS, URLs, or domains:</span></span>
- <span data-ttu-id="2cc05-117">URL/IP 허용 및 차단은 차단 모드에서 사용하도록 설정하기 위해 끝점 구성 요소 네트워크 보호에 대한 Defender를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc05-117">URL/IP allow and block relies on the Defender for Endpoint component Network Protection to be enabled in block mode.</span></span> <span data-ttu-id="2cc05-118">네트워크 보호 및 구성 지침에 대한 자세한 내용은 네트워크 보호 사용 [을 참조하세요.](enable-network-protection.md)</span><span class="sxs-lookup"><span data-stu-id="2cc05-118">For more information on Network Protection and configuration instructions, see [Enable network protection](enable-network-protection.md).</span></span>
- <span data-ttu-id="2cc05-119">맬웨어 방지 클라이언트 버전은 4.18.1906.x 이상입니다.</span><span class="sxs-lookup"><span data-stu-id="2cc05-119">The Antimalware client version must be 4.18.1906.x or later.</span></span> 
- <span data-ttu-id="2cc05-120">버전 1709 Windows 10 컴퓨터의 경우 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cc05-120">Supported on machines on Windows 10, version 1709 or later.</span></span> 
- <span data-ttu-id="2cc05-121">고급 **기능 에서** 사용자 지정 **네트워크 표시기가 Microsoft Defender 보안 센터 > 설정 > 확인합니다.**</span><span class="sxs-lookup"><span data-stu-id="2cc05-121">Ensure that **Custom network indicators** is enabled in **Microsoft Defender Security Center > Settings > Advanced features**.</span></span> <span data-ttu-id="2cc05-122">자세한 내용은 고급 기능을 [참조하세요.](advanced-features.md)</span><span class="sxs-lookup"><span data-stu-id="2cc05-122">For more information, see [Advanced features](advanced-features.md).</span></span>
- <span data-ttu-id="2cc05-123">iOS의 지표 지원은 사용자 지정 표시기 [구성을 참조합니다.](/microsoft-365/security/defender-endpoint/ios-configure-features#configure-custom-indicators)</span><span class="sxs-lookup"><span data-stu-id="2cc05-123">For support of indicators on iOS, see [Configure custom indicators](/microsoft-365/security/defender-endpoint/ios-configure-features#configure-custom-indicators).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="2cc05-124">외부 IP만 표시기 목록에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc05-124">Only external IPs can be added to the indicator list.</span></span> <span data-ttu-id="2cc05-125">내부 IP에 대한 표시기를 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc05-125">Indicators cannot be created for internal IPs.</span></span>
> <span data-ttu-id="2cc05-126">웹 보호 시나리오의 경우 기본 제공 기능을 사용하는 것이 Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="2cc05-126">For web protection scenarios, we recommend using the built-in capabilities in Microsoft Edge.</span></span> <span data-ttu-id="2cc05-127">Microsoft Edge [보호를](network-protection.md) 활용하여 네트워크 트래픽을 검사하고 TCP, HTTP 및 HTTPS(TLS)에 대한 블록을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc05-127">Microsoft Edge leverages [Network Protection](network-protection.md) to inspect network traffic and allows blocks for TCP, HTTP, and HTTPS (TLS).</span></span> <span data-ttu-id="2cc05-128">충돌하는 URL 표시기 정책이 있는 경우 더 긴 경로가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cc05-128">If there are conflicting URL indicator policies, the longer path is applied.</span></span> <span data-ttu-id="2cc05-129">예를 들어 URL 표시기 정책이 URL 표시기 정책보다 `https:\\support.microsoft.com/en-us/office` `https:\\support.microsoft.com` 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc05-129">For example, the URL indicator policy `https:\\support.microsoft.com/en-us/office` takes precedence over the URL indicator policy `https:\\support.microsoft.com`.</span></span>

> [!NOTE]
> <span data-ttu-id="2cc05-130">다른 모든 프로세스에서 웹 보호 시나리오는 검사 및 적용을 위해 네트워크 보호를 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc05-130">For all other processes, web protection scenarios leverage Network Protection for inspection and enforcement:</span></span> 
> - <span data-ttu-id="2cc05-131">세 가지 프로토콜 모두에 대해 IP가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cc05-131">IP is supported for all three protocols</span></span>
> - <span data-ttu-id="2cc05-132">단일 IP 주소만 지원됩니다(CIDR 블록 또는 IP 범위 없음).</span><span class="sxs-lookup"><span data-stu-id="2cc05-132">Only single IP addresses are supported (no CIDR blocks or IP ranges)</span></span>
> - <span data-ttu-id="2cc05-133">암호화된 URL(전체 경로)은 첫 번째 브라우저에서만 차단할 수 있습니다(Internet Explorer, Edge).</span><span class="sxs-lookup"><span data-stu-id="2cc05-133">Encrypted URLs (full path) can only be blocked on first party browsers (Internet Explorer, Edge)</span></span>
> - <span data-ttu-id="2cc05-134">암호화된 URL(FQDN만 해당)은 자사 브라우저 외부에서 차단할 수 있습니다(Internet Explorer, Edge).</span><span class="sxs-lookup"><span data-stu-id="2cc05-134">Encrypted URLS (FQDN only) can be blocked outside of first party browsers (Internet Explorer, Edge)</span></span>
> - <span data-ttu-id="2cc05-135">전체 URL 경로 블록을 도메인 수준 및 암호화되지 않은 모든 URL에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc05-135">Full URL path blocks can be applied on the domain level and all unencrypted URLs</span></span>
 
> [!NOTE]
> <span data-ttu-id="2cc05-136">작업을 수행한 시간과 차단되는 URL 및 IP 사이에 최대 2시간의 대기 시간이 있을 수 있습니다(일반적으로 적음).</span><span class="sxs-lookup"><span data-stu-id="2cc05-136">There may be up to 2 hours of latency (usually less) between the time the action is taken, and the URL and IP being blocked.</span></span> 

### <a name="create-an-indicator-for-ips-urls-or-domains-from-the-settings-page"></a><span data-ttu-id="2cc05-137">설정 페이지에서 IPS, URL 또는 도메인에 대한 표시기 만들기</span><span class="sxs-lookup"><span data-stu-id="2cc05-137">Create an indicator for IPs, URLs, or domains from the settings page</span></span>

1. <span data-ttu-id="2cc05-138">탐색 창에서 **표시기 설정**  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2cc05-138">In the navigation pane, select **Settings** > **Indicators**.</span></span>  

2. <span data-ttu-id="2cc05-139">IP 주소 **또는 URL/도메인 탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc05-139">Select the **IP addresses or URLs/Domains** tab.</span></span>

3. <span data-ttu-id="2cc05-140">항목 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2cc05-140">Select **Add item**.</span></span>

4. <span data-ttu-id="2cc05-141">다음 세부 정보를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc05-141">Specify the following details:</span></span>
   - <span data-ttu-id="2cc05-142">Indicator - 엔터티 세부 정보를 지정하고 표시기 만료를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc05-142">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
   - <span data-ttu-id="2cc05-143">작업 - 수행될 작업을 지정하고 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc05-143">Action - Specify the action to be taken and provide a description.</span></span>
   - <span data-ttu-id="2cc05-144">범위 - 컴퓨터 그룹의 범위를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc05-144">Scope - Define the scope of the machine group.</span></span>

5. <span data-ttu-id="2cc05-145">요약 탭에서 세부 정보를 검토한 다음 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="2cc05-145">Review the details in the Summary tab, then click **Save**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2cc05-146">관련 항목</span><span class="sxs-lookup"><span data-stu-id="2cc05-146">Related topics</span></span>
- [<span data-ttu-id="2cc05-147">지표 만들기</span><span class="sxs-lookup"><span data-stu-id="2cc05-147">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="2cc05-148">파일에 대한 지표 만들기</span><span class="sxs-lookup"><span data-stu-id="2cc05-148">Create indicators for files</span></span>](indicator-file.md)
- [<span data-ttu-id="2cc05-149">인증서를 기반으로 표시기 만들기</span><span class="sxs-lookup"><span data-stu-id="2cc05-149">Create indicators based on certificates</span></span>](indicator-certificates.md)
- [<span data-ttu-id="2cc05-150">지표 관리</span><span class="sxs-lookup"><span data-stu-id="2cc05-150">Manage indicators</span></span>](indicator-manage.md)
