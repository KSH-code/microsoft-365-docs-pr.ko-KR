---
title: 장치 검색 구성
description: 기본 검색 또는 표준 검색을 사용하여 Microsoft 365 Defender 장치 검색을 구성하는 방법 학습
keywords: 기본, 표준, 끝점 검색 구성, 장치 검색
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 7125a6953b9be46af9073b50c9268ce65dc0cd30
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339532"
---
# <a name="configure-device-discovery"></a><span data-ttu-id="e05a9-104">장치 검색 구성</span><span class="sxs-lookup"><span data-stu-id="e05a9-104">Configure device discovery</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e05a9-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="e05a9-105">**Applies to:**</span></span>
- [<span data-ttu-id="e05a9-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e05a9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="e05a9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e05a9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="e05a9-108">검색은 표준 모드 또는 기본 모드로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e05a9-108">Discovery can be configured to be on standard or basic mode.</span></span> <span data-ttu-id="e05a9-109">표준 옵션을 사용하여 네트워크에서 장치를 적극적으로 찾으면 끝점 검색을 보다 잘 보장하고 더 풍부한 장치 분류를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e05a9-109">Use the standard option to actively find devices in your network, which will better guarantee the discovery of endpoints and provide richer device classification.</span></span> 

<span data-ttu-id="e05a9-110">표준 검색을 수행하는 데 사용되는 장치 목록을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e05a9-110">You can customize the list of devices that are used to perform standard discovery.</span></span> <span data-ttu-id="e05a9-111">이 기능을 지원하는 모든 온보드 디바이스(현재 - Windows 10 장치만 해당)에서 표준 검색을 사용하도록 설정하거나 장치 태그를 지정하여 장치의 하위 집합 또는 하위 집합을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e05a9-111">You can either enable standard discovery on all the onboarded devices that also support this capability (currently - Windows 10 devices only) or select a subset or subsets of your devices by specifying their device tags.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e05a9-112">미리 보기의 경우 먼저 미리 보기에서 미리 보기 기능을 켜야 Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="e05a9-112">For preview, you'll first need to turn on the Preview features in Microsoft 365 Defender.</span></span>
> <span data-ttu-id="e05a9-113">그런 다음 보안 센터에서 장치 검색 구성에 액세스할 Microsoft 365 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e05a9-113">You can then access the device discovery configuration in Microsoft 365 security center.</span></span> <span data-ttu-id="e05a9-114">관리되지 않는 장치 및 보안 권장 사항 목록은 Microsoft 365 Defender 및 Microsoft 365 보안 센터에서 사용할 수 있으며 대시보드 타일은 Microsoft 365 보안 센터에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e05a9-114">The list of unmanaged devices and security recommendations will be available in both Microsoft 365 Defender and Microsoft 365 security center, while the dashboard tiles will only be available in Microsoft 365 security center.</span></span>

<span data-ttu-id="e05a9-115">보안 센터에서 다음 구성 Microsoft 365 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e05a9-115">Take the following configuration steps in Microsoft 365 security center:</span></span>

1. <span data-ttu-id="e05a9-116">장치 **검색 설정 > 로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="e05a9-116">Navigate to **Settings > Device discovery**.</span></span>
2. <span data-ttu-id="e05a9-117">온보드 디바이스에서 사용할 검색 모드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e05a9-117">Select the discovery mode to use on your onboarded devices.</span></span>
3. <span data-ttu-id="e05a9-118">표준 검색을 사용하기로 선택한 경우 해당 장치 태그를 지정하여 활성 프로비전에 사용할 장치(모든 장치 또는 하위 집합)를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e05a9-118">If you've selected to use standard discovery, select which devices to use for active probing: all devices or on a subset by specifying their device tags.</span></span>
4. <span data-ttu-id="e05a9-119">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e05a9-119">Click **Save**.</span></span>

## <a name="exclude-devices-from-being-actively-probed-in-standard-discovery"></a><span data-ttu-id="e05a9-120">표준 검색에서 디바이스가 적극적으로 프로브되지 못하게 제외</span><span class="sxs-lookup"><span data-stu-id="e05a9-120">Exclude devices from being actively probed in standard discovery</span></span>

<span data-ttu-id="e05a9-121">네트워크에 적극적으로 검사하지 말아야 하는 장치(예: 다른 보안 도구의 허니팟으로 사용되는 장치)가 있는 경우 제외 목록을 정의하여 검사하지 못하게 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e05a9-121">If there are devices on your network which should not be actively scanned (for example, devices used as honeypots for another security tool), you can also define a list of exclusions to prevent them from being scanned.</span></span> <span data-ttu-id="e05a9-122">기본 검색 모드를 사용하여 디바이스를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e05a9-122">Note that devices can still be discovered using Basic discovery mode.</span></span> <span data-ttu-id="e05a9-123">이러한 디바이스는 수동적으로 검색되지만 적극적으로 프로브되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e05a9-123">Those devices will be passively discovered but won't be actively probed.</span></span> 

## <a name="select-networks-to-monitor"></a><span data-ttu-id="e05a9-124">모니터링할 네트워크 선택</span><span class="sxs-lookup"><span data-stu-id="e05a9-124">Select networks to monitor</span></span>

 <span data-ttu-id="e05a9-125">끝점용 Microsoft Defender는 네트워크를 분석하여 모니터링해야 하는 회사 네트워크인지 또는 무시할 수 있는 회사 네트워크가 아닌 네트워크인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e05a9-125">Microsoft Defender for Endpoint analyzes a network and determines if it is a corporate network that needs to be monitored or a non-corporate network that can be ignored.</span></span> <span data-ttu-id="e05a9-126">회사 네트워크는 일반적으로 모니터링할 수 있는 것으로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="e05a9-126">Corporate networks are typically chosen to be monitored.</span></span> <span data-ttu-id="e05a9-127">그러나 온보드 장치가 있는 회사 네트워크가 아닌 네트워크를 모니터링하기로 선택하여 이 결정을 다시 정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e05a9-127">However, you can override this decision by choosing to monitor non-corporate networks where onboarded devices are found.</span></span> 

<span data-ttu-id="e05a9-128">모니터링할 네트워크를 지정하여 장치 검색을 수행할 수 있는 위치를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e05a9-128">You can configure where device discovery can be performed by specifying which networks to monitor.</span></span> <span data-ttu-id="e05a9-129">네트워크가 모니터링될 때 디바이스 검색을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e05a9-129">When a network is monitored, device discovery can be performed on it.</span></span> 

<span data-ttu-id="e05a9-130">장치 검색을 수행할 수 있는 네트워크 목록이 모니터링된 네트워크 **페이지에 표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="e05a9-130">A list of networks where device discovery can be performed is shown in the **Monitored networks** page.</span></span> 

> [!NOTE]
> <span data-ttu-id="e05a9-131">네트워크 목록에서는 연결된 장치 수에 따라 상위 50개 네트워크만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e05a9-131">Only top 50 networks (according to the number of associated devices) will be available in the network list.</span></span> 

<span data-ttu-id="e05a9-132">모니터링된 네트워크 목록은 지난 7일 동안 네트워크에 표시된 총 장치 수를 기준으로 정렬됩니다.</span><span class="sxs-lookup"><span data-stu-id="e05a9-132">The list of monitored networks is sorted based upon the total number of devices seen on the network in the last 7 days.</span></span>

<span data-ttu-id="e05a9-133">필터를 적용하여 다음 네트워크 검색 상태 중 원하는 경우를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e05a9-133">You can apply a filter to view any of the following network discovery states:</span></span>

- <span data-ttu-id="e05a9-134">**모니터링된 네트워크** - 장치 검색이 수행되는 네트워크.</span><span class="sxs-lookup"><span data-stu-id="e05a9-134">**Monitored networks** - Networks where device discovery is performed.</span></span>
- <span data-ttu-id="e05a9-135">**무시된 네트워크** - 이 네트워크는 무시되고 디바이스 검색이 수행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e05a9-135">**Ignored networks** - This network will be ignored and device discovery will not be performed on it.</span></span>
- <span data-ttu-id="e05a9-136">**모두** - 모니터링된 네트워크와 무시된 네트워크가 모두 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e05a9-136">**All** - Both monitored and ignored networks will be displayed.</span></span>

### <a name="configure-the-network-monitor-state"></a><span data-ttu-id="e05a9-137">네트워크 모니터 상태 구성</span><span class="sxs-lookup"><span data-stu-id="e05a9-137">Configure the network monitor state</span></span>

<span data-ttu-id="e05a9-138">디바이스 검색이 진행되는 위치를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e05a9-138">You control where device discovery takes place.</span></span> <span data-ttu-id="e05a9-139">모니터링된 네트워크는 장치 검색이 수행될 위치로, 일반적으로 회사 네트워크입니다.</span><span class="sxs-lookup"><span data-stu-id="e05a9-139">Monitored networks is where device discovery will be performed and are typically corporate networks.</span></span> <span data-ttu-id="e05a9-140">네트워크를 무시하거나 상태를 수정한 후 초기 검색 분류를 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e05a9-140">You can also choose to ignore networks or select the initial discovery classification after modifying a state.</span></span>

<span data-ttu-id="e05a9-141">초기 검색 분류를 선택하면 기본 시스템 구성 네트워크 모니터 상태를 적용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e05a9-141">Choosing the initial discovery classification means applying the default system-made network monitor state.</span></span> <span data-ttu-id="e05a9-142">기본 시스템 구성 네트워크 모니터 상태를 선택하면 회사로 식별된 네트워크가 모니터링되고 회사가 아닌 것으로 식별된 네트워크는 자동으로 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e05a9-142">Selecting the default system-made network monitor state means that networks that were identified to be corporate, will be monitored, and ones identified as non-corporate, will be ignored automatically.</span></span>

1. <span data-ttu-id="e05a9-143">장치 **설정 > 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e05a9-143">Select **Settings > Device discovery**.</span></span>
2. <span data-ttu-id="e05a9-144">모니터링된 **네트워크를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e05a9-144">Select **Monitored networks**.</span></span>
3. <span data-ttu-id="e05a9-145">네트워크 목록을 시청하세요.</span><span class="sxs-lookup"><span data-stu-id="e05a9-145">View the list of networks.</span></span>
4. <span data-ttu-id="e05a9-146">네트워크 이름 옆의 세 점을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e05a9-146">Select the three dots next to the network name.</span></span>
5. <span data-ttu-id="e05a9-147">초기 검색 분류를 모니터링할지, 무시할지 또는 사용할지 여부를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e05a9-147">Choose whether you want to monitor, ignore, or use the initial discovery classification.</span></span>

    > [!WARNING]
    >
    > - <span data-ttu-id="e05a9-148">회사 네트워크로 Microsoft Defender for Endpoint에서 식별되지 않은 네트워크를 모니터링하기로 선택하면 회사 네트워크 외부에서 장치 검색이 발생할 수 있으므로 홈 또는 기타 회사용이 아닌 장치를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e05a9-148">Choosing to monitor a network that was not identified by Microsoft Defender for Endpoint as a corporate network can cause device discovery outside of your corporate network, and may therefore detect home or other non-corporate devices.</span></span>
    > - <span data-ttu-id="e05a9-149">네트워크를 무시하기로 선택하면 네트워크에서 장치 모니터링 및 검색이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="e05a9-149">Choosing to ignore a network will stop monitoring and discovering devices in that network.</span></span> <span data-ttu-id="e05a9-150">이미 검색된 장치는 인벤토리에서 제거되지 않지만 더 이상 업데이트되지 않습니다. 끝점용 Defender의 데이터 보존 기간이 만료될 때까지 세부 정보가 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="e05a9-150">Devices that were already discovered will not be removed from the inventory, but will no longer be updated, and details will be retained until the data retention period of the Defender for Endpoint expires.</span></span>
    > - <span data-ttu-id="e05a9-151">회사 네트워크가 아닌 네트워크를 모니터링하도록 선택하기 전에 해당 작업을 할 수 있는 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e05a9-151">Before choosing to monitor non-corporate networks, you must ensure you have permission to do so.</span></span>

6. <span data-ttu-id="e05a9-152">변경하려는지 확인</span><span class="sxs-lookup"><span data-stu-id="e05a9-152">Confirm that you want to make the change.</span></span> 

## <a name="explore-devices-in-the-network"></a><span data-ttu-id="e05a9-153">네트워크에서 디바이스 탐색</span><span class="sxs-lookup"><span data-stu-id="e05a9-153">Explore devices in the network</span></span>

<span data-ttu-id="e05a9-154">다음 고급 헌팅 쿼리를 사용하여 네트워크 목록에 설명된 각 네트워크 이름에 대한 더 많은 컨텍스트를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e05a9-154">You can use the following advanced hunting query to get more context about each network name described in the networks list.</span></span> <span data-ttu-id="e05a9-155">이 쿼리에는 지난 7일 이내에 특정 네트워크에 연결된 모든 온보드 장치가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="e05a9-155">The query lists all the onboarded devices that were connected to a certain network within the last 7 days.</span></span>

```kusto
DeviceNetworkInfo
| where Timestamp > ago(7d)
| summarize arg_max(Timestamp, *) by DeviceId
| where ConnectedNetworks  != ""
| extend ConnectedNetworksExp = parse_json(ConnectedNetworks)
| mv-expand bagexpansion = array ConnectedNetworks=ConnectedNetworksExp
| extend NetworkName = tostring(ConnectedNetworks ["Name"]), Description = tostring(ConnectedNetworks ["Description"]), NetworkCategory = tostring(ConnectedNetworks ["Category"])
| where NetworkName == "<your network name here>"
```

## <a name="see-also"></a><span data-ttu-id="e05a9-156">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e05a9-156">See also</span></span>

- [<span data-ttu-id="e05a9-157">장치 검색 개요</span><span class="sxs-lookup"><span data-stu-id="e05a9-157">Device discovery overview</span></span>](device-discovery.md)
- [<span data-ttu-id="e05a9-158">장치 검색 FAQ</span><span class="sxs-lookup"><span data-stu-id="e05a9-158">Device discovery FAQs</span></span>](device-discovery-faq.md)
