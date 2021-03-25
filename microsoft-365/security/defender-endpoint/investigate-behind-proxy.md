---
title: 정방형 proxies 뒤에 발생하는 연결 이벤트 조사
description: 프록시 대신 실제 대상을 표시하는 Microsoft Defender ATP의 네트워크 보호를 통해 고급 HTTP 수준 모니터링을 사용하는 방법을 알아보십시오.
keywords: 프록시, 네트워크 보호, 전달 프록시, 네트워크 이벤트, 감사, 차단, 도메인 이름, 도메인
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 7eaa4bb76d7607f0b55c87482d1104a0897c9d36
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186092"
---
# <a name="investigate-connection-events-that-occur-behind-forward-proxies"></a><span data-ttu-id="0be8e-104">정방형 proxies 뒤에 발생하는 연결 이벤트 조사</span><span class="sxs-lookup"><span data-stu-id="0be8e-104">Investigate connection events that occur behind forward proxies</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0be8e-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="0be8e-105">**Applies to:**</span></span>
- [<span data-ttu-id="0be8e-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="0be8e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0be8e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0be8e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="0be8e-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="0be8e-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="0be8e-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="0be8e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatemachines-abovefoldlink)

<span data-ttu-id="0be8e-110">Endpoint용 Defender는 다양한 수준의 네트워크 스택에서 네트워크 연결 모니터링을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="0be8e-110">Defender for Endpoint supports network connection monitoring from different levels of the network stack.</span></span> <span data-ttu-id="0be8e-111">어려운 경우는 네트워크에서 인터넷에 대한 게이트웨이로 전방 프록시를 사용하는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="0be8e-111">A challenging case is when the network uses a forward proxy as a gateway to the Internet.</span></span>

<span data-ttu-id="0be8e-112">프록시는 대상 끝점인 것 같은 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="0be8e-112">The proxy acts as if it was the target endpoint.</span></span>  <span data-ttu-id="0be8e-113">이러한 경우 단순 네트워크 연결 모니터는 올바른 프록시와의 연결을 감사하지만 조사 값이 더 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="0be8e-113">In these cases, simple network connection monitors will audit the connections with the proxy which is correct but has lower investigation value.</span></span> 

<span data-ttu-id="0be8e-114">Endpoint용 Defender는 네트워크 보호를 통해 고급 HTTP 수준 모니터링을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="0be8e-114">Defender for Endpoint supports advanced HTTP level monitoring through network protection.</span></span> <span data-ttu-id="0be8e-115">이 설정이 켜져 있는 경우 실제 대상 도메인 이름을 노출하는 새로운 유형의 이벤트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0be8e-115">When turned on, a new type of event is surfaced which exposes the real target domain names.</span></span>

## <a name="use-network-protection-to-monitor-network-connection-behind-a-firewall"></a><span data-ttu-id="0be8e-116">네트워크 보호를 사용하여 방화벽 뒤의 네트워크 연결 모니터링</span><span class="sxs-lookup"><span data-stu-id="0be8e-116">Use network protection to monitor network connection behind a firewall</span></span>
<span data-ttu-id="0be8e-117">네트워크 보호에서 시작된 추가 네트워크 이벤트로 인해 정방향 프록시 뒤의 네트워크 연결을 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0be8e-117">Monitoring network connection behind a forward proxy is possible due to additional network events that originate from network protection.</span></span> <span data-ttu-id="0be8e-118">장치 타임라인에서 표시하려면 네트워크 보호를 켜세요(감사 모드의 최소).</span><span class="sxs-lookup"><span data-stu-id="0be8e-118">To see them on a device timeline, turn network protection on (at the minimum in audit mode).</span></span> 

<span data-ttu-id="0be8e-119">네트워크 보호는 다음 모드를 사용하여 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0be8e-119">Network protection can be controlled using the following modes:</span></span>

- <span data-ttu-id="0be8e-120">**차단**</span><span class="sxs-lookup"><span data-stu-id="0be8e-120">**Block**</span></span> <br> <span data-ttu-id="0be8e-121">사용자 또는 앱은 위험한 도메인에 연결하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0be8e-121">Users or apps will be blocked from connecting to dangerous domains.</span></span> <span data-ttu-id="0be8e-122">Microsoft Defender 보안 센터에서 이 활동을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0be8e-122">You will be able to see this activity in Microsoft Defender Security Center.</span></span>
- <span data-ttu-id="0be8e-123">**감사**</span><span class="sxs-lookup"><span data-stu-id="0be8e-123">**Audit**</span></span> <br> <span data-ttu-id="0be8e-124">사용자 또는 앱은 위험한 도메인에 연결하지 못하게 차단되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0be8e-124">Users or apps will not be blocked from connecting to dangerous domains.</span></span> <span data-ttu-id="0be8e-125">그러나 Microsoft Defender 보안 센터에서 이 활동이 계속 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0be8e-125">However, you will still see this activity in Microsoft Defender Security Center.</span></span>


<span data-ttu-id="0be8e-126">네트워크 보호를 끄면 사용자 또는 앱이 위험한 도메인에 연결하지 못하게 차단되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0be8e-126">If you turn network protection off, users or apps will not be blocked from connecting to dangerous domains.</span></span> <span data-ttu-id="0be8e-127">Microsoft Defender 보안 센터에서 네트워크 활동이 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0be8e-127">You will not see any network activity in Microsoft Defender Security Center.</span></span>

<span data-ttu-id="0be8e-128">구성하지 않은 경우 기본적으로 네트워크 차단이 꺼집니다.</span><span class="sxs-lookup"><span data-stu-id="0be8e-128">If you do not configure it, network blocking will be turned off by default.</span></span>

<span data-ttu-id="0be8e-129">자세한 내용은 네트워크 보호 사용 [을 참조하세요.](enable-network-protection.md)</span><span class="sxs-lookup"><span data-stu-id="0be8e-129">For more information, see [Enable network protection](enable-network-protection.md).</span></span>

## <a name="investigation-impact"></a><span data-ttu-id="0be8e-130">조사 영향</span><span class="sxs-lookup"><span data-stu-id="0be8e-130">Investigation impact</span></span>
<span data-ttu-id="0be8e-131">네트워크 보호가 켜져 있는 경우 장치의 타임라인에 실제 대상 주소가 표시되어 있는 동안 IP 주소가 계속 프록시를 나타내는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0be8e-131">When network protection is turned on, you'll see that on a device's timeline the IP address will keep representing the proxy, while the real target address shows up.</span></span>

![디바이스 타임라인의 네트워크 이벤트 이미지](images/atp-proxy-investigation.png)

<span data-ttu-id="0be8e-133">이제 네트워크 보호 계층에 의해 트리거된 추가 이벤트를 사용하여 프록시 뒤에도 실제 도메인 이름을 표면화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0be8e-133">Additional events triggered by the network protection layer are now available to surface the real domain names even behind a proxy.</span></span>

<span data-ttu-id="0be8e-134">이벤트의 정보:</span><span class="sxs-lookup"><span data-stu-id="0be8e-134">Event's information:</span></span>

![단일 네트워크 이벤트의 이미지](images/atp-proxy-investigation-event.png)



## <a name="hunt-for-connection-events-using-advanced-hunting"></a><span data-ttu-id="0be8e-136">고급 헌팅을 사용하여 연결 이벤트 헌팅</span><span class="sxs-lookup"><span data-stu-id="0be8e-136">Hunt for connection events using advanced hunting</span></span> 
<span data-ttu-id="0be8e-137">모든 새 연결 이벤트를 사용하여 고급 헌팅을 통해 헌팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0be8e-137">All new connection events are available for you to hunt on through advanced hunting as well.</span></span> <span data-ttu-id="0be8e-138">이러한 이벤트는 연결 이벤트이기 때문에 작업 유형 아래 DeviceNetworkEvents 테이블에서 찾을 `ConnecionSuccess` 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0be8e-138">Since these events are connection events, you can find them under the DeviceNetworkEvents table under the `ConnecionSuccess` action type.</span></span>

<span data-ttu-id="0be8e-139">이 간단한 쿼리를 사용하면 모든 관련 이벤트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0be8e-139">Using this simple query will show you all the relevant events:</span></span>

```
DeviceNetworkEvents
| where ActionType == "ConnectionSuccess" 
| take 10
```

![고급 헌팅 쿼리의 이미지](images/atp-proxy-investigation-ah.png)

<span data-ttu-id="0be8e-141">프록시 자체에 대한 연결과 관련된 이벤트를 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0be8e-141">You can also filter out  events that are related to connection to the proxy itself.</span></span> 

<span data-ttu-id="0be8e-142">다음 쿼리를 사용하여 프록시에 대한 연결을 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="0be8e-142">Use the following query to filter out the connections to the proxy:</span></span>

```
DeviceNetworkEvents
| where ActionType == "ConnectionSuccess" and RemoteIP != "ProxyIP"  
| take 10
```



## <a name="related-topics"></a><span data-ttu-id="0be8e-143">관련 항목</span><span class="sxs-lookup"><span data-stu-id="0be8e-143">Related topics</span></span>
- [<span data-ttu-id="0be8e-144">GP를 통해 네트워크 보호 적용 - 정책 CSP</span><span class="sxs-lookup"><span data-stu-id="0be8e-144">Applying network protection with GP - policy CSP</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection)
