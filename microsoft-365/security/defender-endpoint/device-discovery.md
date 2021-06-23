---
title: 장치 검색 개요
description: 네트워크에서 관리되지 않는 장치를 찾기 위해 Microsoft 365 Defender 끝점 검색을 활용하는 방법에 대해 자세히 알아보기
keywords: 장치 검색, 검색, 수동, 사전, 네트워크, 표시 여부, 서버, Workstation, 온보드, 관리되지 않는 장치
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
ms.openlocfilehash: 16baaa6fd9865140d42c0ca3a566427f761a28c2
ms.sourcegitcommit: d34cac68537d6e1c65be757956646e73dea6e1ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/22/2021
ms.locfileid: "53062218"
---
# <a name="device-discovery-overview"></a><span data-ttu-id="9c399-104">장치 검색 개요</span><span class="sxs-lookup"><span data-stu-id="9c399-104">Device discovery overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9c399-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="9c399-105">**Applies to:**</span></span>
- [<span data-ttu-id="9c399-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="9c399-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="9c399-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9c399-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="9c399-108">환경을 보호하려면 네트워크에 있는 장치의 인벤토리를 보유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c399-108">Protecting your environment requires taking inventory of the devices that are in your network.</span></span> <span data-ttu-id="9c399-109">그러나 네트워크에서 디바이스 매핑은 비용이 많이 들고, 어렵고, 시간이 많이 소요될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c399-109">However, mapping devices in a network can often be expensive, challenging, and time-consuming.</span></span> 

<span data-ttu-id="9c399-110">Microsoft Defender for Endpoint는 추가 어플라이언스 또는 번거로운 프로세스 변경 없이도 회사 네트워크에 연결된 관리되지 않는 장치를 찾는 데 도움이 되는 장치 검색 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9c399-110">Microsoft Defender for Endpoint provides a device discovery capability that helps you find unmanaged devices connected to your corporate network without the need for extra appliances or cumbersome process changes.</span></span>


<span data-ttu-id="9c399-111">디바이스 검색 기능을 사용하여 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c399-111">The device discovery capability allows you to:</span></span>

- <span data-ttu-id="9c399-112">**회사 네트워크에 연결된 엔터프라이즈 끝점 검색**</span><span class="sxs-lookup"><span data-stu-id="9c399-112">**Discover enterprise endpoints connected to your corporate network**</span></span> <br>
<span data-ttu-id="9c399-113">기본 또는 표준 검색 옵션을 사용하여 아직 끝점용 Microsoft Defender에 온보딩되지 않은 작업, 서버 및 모바일 끝점을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c399-113">Using either basic or standard discovery options, you can discover workstations, servers, and mobile endpoints that are not yet onboarded to Microsoft Defender for Endpoint.</span></span>  

- <span data-ttu-id="9c399-114">**검색된 끝점 온보드**</span><span class="sxs-lookup"><span data-stu-id="9c399-114">**Onboard discovered endpoints**</span></span><br>
<span data-ttu-id="9c399-115">네트워크에서 관리되지 않는 끝점은 네트워크에 취약성 및 위험을 도입합니다.</span><span class="sxs-lookup"><span data-stu-id="9c399-115">Unmanaged endpoints in your network introduce vulnerabilities and risks to your network.</span></span> <span data-ttu-id="9c399-116">서비스를 온보더링하면 서비스에 대한 보안 가시성을 강화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c399-116">Onboarding them to the service can increase the security visibility on them.</span></span> 

<span data-ttu-id="9c399-117">이 기능과 함께, 기존 위협 및 취약성 관리 환경의 일부로 끝점용 Microsoft Defender에 장치를 온보딩하기 위한 새로운 보안 권장을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c399-117">In conjunction with this capability, a new security recommendation to onboard devices to Microsoft Defender for Endpoint will be available as part of the existing Threat and Vulnerability Management experience.</span></span>



## <a name="discovery-methods"></a><span data-ttu-id="9c399-118">검색 방법</span><span class="sxs-lookup"><span data-stu-id="9c399-118">Discovery methods</span></span>
<span data-ttu-id="9c399-119">검색 모드에는 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c399-119">There are two modes of discovery:</span></span> 

-   <span data-ttu-id="9c399-120">기본 검색</span><span class="sxs-lookup"><span data-stu-id="9c399-120">Basic discovery</span></span> 
-   <span data-ttu-id="9c399-121">표준 검색(권장)</span><span class="sxs-lookup"><span data-stu-id="9c399-121">Standard discovery (recommended)</span></span> 


> [!IMPORTANT]
> <span data-ttu-id="9c399-122">검색이 기본 모드로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c399-122">Discovery is set to basic mode.</span></span> <span data-ttu-id="9c399-123">설정 페이지를 통해 이 구성을 보존할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c399-123">You can choose to retain this configuration through the settings page.</span></span> <span data-ttu-id="9c399-124">표준 검색은 이 날짜 전에 설정 페이지를 통해 수정하지 않는 한 2021년 7월 19일부터 모든 고객의 기본 모드가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c399-124">Standard discovery will be the default mode for all customers starting July 19, 2021 - unless modified through the settings page before this date.</span></span>

### <a name="basic-discovery"></a><span data-ttu-id="9c399-125">기본 검색</span><span class="sxs-lookup"><span data-stu-id="9c399-125">Basic discovery</span></span> 

<span data-ttu-id="9c399-126">이 모드에서 끝점은 네트워크에서 수동적으로 이벤트를 수집하고 해당 네트워크에서 장치 정보를 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="9c399-126">In this mode, endpoints will passively collect events in your network and extract device information from them.</span></span> <span data-ttu-id="9c399-127">기본 검색에서는 수동 SenseNDR.exe 이진 파일을 사용하며 네트워크 트래픽은 시작되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c399-127">Basic discovery uses the SenseNDR.exe binary for passive network data collection and no network traffic will be initiated.</span></span> <span data-ttu-id="9c399-128">끝점은 단순히 온보더된 장치에서 볼 수 있는 모든 네트워크 트래픽에서 데이터를 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="9c399-128">Endpoints will simply extract data from every network traffic that is seen by an onboarded device.</span></span> 

### <a name="standard-discovery"></a><span data-ttu-id="9c399-129">표준 검색</span><span class="sxs-lookup"><span data-stu-id="9c399-129">Standard discovery</span></span> 

<span data-ttu-id="9c399-130">이 모드를 사용하면 끝점에서 네트워크에서 관찰된 디바이스를 적극적으로 프로브하여 수집된 데이터를 강화할 수 있습니다. 이를 통해 신뢰할 수 있고 확실한 장치 인벤토리를 구축할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c399-130">This mode allows endpoints to actively probe observed devices in the network to enrich collected data - helping you build a reliable and coherent device inventory.</span></span> <span data-ttu-id="9c399-131">표준 모드는 스마트하고 활성 프로비전을 사용하여 관찰된 장치에 대한 더 많은 정보를 검색하여 기존 장치 정보를 보강합니다.</span><span class="sxs-lookup"><span data-stu-id="9c399-131">Standard mode uses smart, active probing to discover even more information about observed devices to enrich existing device information.</span></span>  

<span data-ttu-id="9c399-132">표준 모드를 사용하도록 설정하면 조직의 네트워크 모니터링 도구에서 검색 센서에 의해 생성된 최소한의 무시할 수 있는 네트워크 활동이 관찰될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c399-132">When Standard mode is enabled, minimal and negligible network activity generated by the discovery sensor might be observed by network monitoring tools in your organization.</span></span>  

 <span data-ttu-id="9c399-133">이 모드를 사용하도록 설정하지 않는 경우 네트워크에서 관리되지 않는 끝점만 제한적으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c399-133">If you choose not to enable this mode, you will only gain limited visibility of unmanaged endpoints in your network.</span></span>

<span data-ttu-id="9c399-134">표준 검색은 다양한 PowerShell 스크립트를 사용하여 네트워크에서 장치를 능동적으로 프로브합니다.</span><span class="sxs-lookup"><span data-stu-id="9c399-134">Standard discovery uses various PowerShell scripts to actively probe devices in the network.</span></span> <span data-ttu-id="9c399-135">이러한 PowerShell 스크립트는 Microsoft에 서명되고 다음 위치에서 `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\*.ps` 실행됩니다. .</span><span class="sxs-lookup"><span data-stu-id="9c399-135">Those PowerShell scripts are Microsoft signed and are executed from the following location: `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\*.ps`.</span></span> <span data-ttu-id="9c399-136">예를 들면 `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\UnicastScannerV1.1.0.ps1`와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9c399-136">For example, `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\UnicastScannerV1.1.0.ps1`.</span></span>

<span data-ttu-id="9c399-137">검색 설정을 변경하고 사용자 지정할 수 있습니다. 자세한 내용은 장치 검색 [구성을 참조하세요.](configure-device-discovery.md)</span><span class="sxs-lookup"><span data-stu-id="9c399-137">You can change and customize your discovery settings, for more information see [Configure device discovery](configure-device-discovery.md).</span></span>

> [!NOTE]
> <span data-ttu-id="9c399-138">검색 엔진은 회사 네트워크에서 수신되는 네트워크 이벤트와 회사 네트워크 외부에서 수신되는 네트워크 이벤트를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="9c399-138">The discovery engine distinguishes between network events that are received in the corporate network versus outside of the corporate network.</span></span> <span data-ttu-id="9c399-139">회사 네트워크에 연결되지 않은 장치는 장치 인벤토리에서 검색되거나 나열되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c399-139">Devices that are not connected to corporate networks will not be discovered or listed in the device inventory.</span></span> 



## <a name="device-inventory"></a><span data-ttu-id="9c399-140">디바이스 인벤토리</span><span class="sxs-lookup"><span data-stu-id="9c399-140">Device Inventory</span></span> 
<span data-ttu-id="9c399-141">검색했지만 아직 끝점용 Microsoft Defender에 의해 온보딩 및 보호되지 않은 장치는 끝점 탭의 장치 인벤토리에 나열됩니다. 이제 다음 값을 사용할 수 있는 온보더링 상태라는 장치 인벤토리 목록에서 새 필터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c399-141">Devices that have been discovered but have not yet been onboarded and secured by Microsoft Defender for Endpoint will be listed in Device Inventory within the Endpoints tab. You can now use a new filter in the device inventory list called Onboarding status which can have any of the following values:</span></span>

- <span data-ttu-id="9c399-142">온보딩 – 끝점이 끝점용 Microsoft Defender에 온보딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c399-142">Onboarded – The endpoint is onboarded to Microsoft Defender for Endpoint.</span></span>
- <span data-ttu-id="9c399-143">온보딩할 수 있습니다. 끝점이 네트워크에서 검색되었습니다. 운영 체제는 끝점용 Microsoft Defender에서 지원되는 끝점으로 식별했지만 현재는 온보딩되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="9c399-143">Can be onboarded – The endpoint was discovered in the network and the Operating System was identified as one that is supported by Microsoft Defender for Endpoint, but it is not currently onboarded.</span></span> <span data-ttu-id="9c399-144">이러한 장치를 온보드하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9c399-144">We highly recommend onboarding these devices.</span></span>
- <span data-ttu-id="9c399-145">지원되지 않습니다. 끝점은 네트워크에서 검색했지만 끝점용 Microsoft Defender에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c399-145">Unsupported – The endpoint was discovered in the network but is not supported by Microsoft Defender for Endpoint.</span></span>
- <span data-ttu-id="9c399-146">정보 부족 - 시스템에서 장치의 지원 여부를 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9c399-146">Insufficient info – The system could not determine the supportability of the device.</span></span> <span data-ttu-id="9c399-147">네트워크의 더 많은 장치에서 표준 검색을 사용하도록 설정하면 검색된 특성을 강화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c399-147">Enabling standard discovery on more devices in the network can enrich the discovered attributes.</span></span> 
 

![장치 인벤토리 대시보드의 이미지](images/2b62255cd3a9dd42f3219e437b956fb9.png)

> [!TIP]
> <span data-ttu-id="9c399-149">항상 필터를 적용하여 관리되지 않는 장치를 장치 인벤토리 목록에서 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c399-149">You can always apply filters to exclude unmanaged devices from the device inventory list.</span></span> <span data-ttu-id="9c399-150">API 쿼리의 등록 상태 열을 사용하여 관리되지 않는 장치를 필터링할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c399-150">You can also use the onboarding status column on API queries to filter out unmanaged devices.</span></span> 

## <a name="vulnerability-assessment-on-discovered-devices"></a><span data-ttu-id="9c399-151">검색된 장치에 대한 취약점 평가</span><span class="sxs-lookup"><span data-stu-id="9c399-151">Vulnerability assessment on discovered devices</span></span>
<span data-ttu-id="9c399-152">네트워크에서 검색된 다른 관리되지 않는 장치뿐만 아니라 장치의 취약성 및 위험은 "보안 권장 사항"에 따라 현재 TVM 흐름의 일부로 포털의 엔터티 페이지에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c399-152">Vulnerabilities and risks on your devices as well as other discovered unmanaged devices in the network are part of the current TVM flows under "Security Recommendations" and represented in entity pages across the portal.</span></span> <span data-ttu-id="9c399-153">"SSH" 관련 보안 권장 사항을 검색하여 관리되지 않는 장치 및 관리되는 장치와 관련된 SSH 취약성을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="9c399-153">Search for "SSH" related security recommendations to find SSH vulnerabilities that are related for unmanaged and managed devices.</span></span> 

![보안 권장 사항 대시보드의 이미지](images/1156c82ffadd356ce329d1cf551e806c.png)  

## <a name="use-advanced-hunting-on-discovered-devices"></a><span data-ttu-id="9c399-155">검색된 장치에서 고급 헌팅 사용</span><span class="sxs-lookup"><span data-stu-id="9c399-155">Use Advanced Hunting on discovered devices</span></span>
<span data-ttu-id="9c399-156">고급 헌팅 쿼리를 사용하여 검색된 디바이스를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c399-156">You can use Advanced Hunting queries to gain visibility on discovered devices.</span></span>
<span data-ttu-id="9c399-157">DeviceInfo 테이블에서 검색된 끝점에 대한 세부 정보 또는 DeviceNetworkInfo 테이블에서 해당 장치에 대한 네트워크 관련 정보를 찾아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c399-157">Find details about discovered Endpoints in the DeviceInfo table, or network-related information about those devices in the DeviceNetworkInfo table.</span></span>
  

![고급 헌팅 사용 이미지](images/f48ba1779eddee9872f167453c24e5c9.png)


<span data-ttu-id="9c399-159">장치 검색은 네트워크 데이터 원본으로 끝점용 Microsoft Defender를 네트워크 데이터 원본으로 활용하여 활동을 비보딩된 장치에 특성화합니다.</span><span class="sxs-lookup"><span data-stu-id="9c399-159">Device discovery leverages Microsoft Defender for Endpoint onboarded devices as a network data source to attribute activities to non-onboarded devices.</span></span> <span data-ttu-id="9c399-160">즉, 온보딩되지 않은 장치와 통신한 끝점용 Microsoft Defender 온보딩 디바이스의 경우 온보딩되지 않은 장치의 활동은 타임라인 및 고급 헌팅 DeviceNetworkEvents 테이블을 통해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c399-160">This means that if a Microsoft Defender for Endpoint onboarded device communicated with a non-onboarded device, activities on the non-onboarded device can be seen on the timeline and through the Advanced hunting DeviceNetworkEvents table.</span></span> 



<span data-ttu-id="9c399-161">새 이벤트는 TCP(Transmission Control Protocol) 연결 기반 이벤트로, 현재 DeviceNetworkEvents 스키마에 맞습니다.</span><span class="sxs-lookup"><span data-stu-id="9c399-161">New events are Transmission Control Protocol (TCP) connections-based and will fit to the current DeviceNetworkEvents scheme.</span></span> <span data-ttu-id="9c399-162">TCP는 끝점 사용이 가능한 비 Microsoft Defender에서 끝점용 Microsoft Defender 사용 디바이스로 다시 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="9c399-162">TCP ingress to the Microsoft Defender for Endpoint enabled device from a non-Microsoft Defender for Endpoint enabled.</span></span>  

<span data-ttu-id="9c399-163">다음 작업 유형도 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9c399-163">The following action types have also been added:</span></span>  

- <span data-ttu-id="9c399-164">ConnectionAttempt - TCP 연결(syn)을 설정하려는 시도</span><span class="sxs-lookup"><span data-stu-id="9c399-164">ConnectionAttempt - An attempt to establish a TCP connection (syn)</span></span>  
- <span data-ttu-id="9c399-165">ConnectionAcknowledged - TCP 연결이 수락되었습니다(syn\ack)</span><span class="sxs-lookup"><span data-stu-id="9c399-165">ConnectionAcknowledged - An acknowledgment that a TCP connection was accepted (syn\ack)</span></span>  

<span data-ttu-id="9c399-166">다음 예제 쿼리를 시도할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c399-166">You can try this example query:</span></span>  

```
DeviceNetworkEvents  
| where ActionType == "ConnectionAcknowledged" or ActionType == "ConnectionAttempt"  
| take 10  
```


## <a name="changed-behavior"></a><span data-ttu-id="9c399-167">변경된 동작</span><span class="sxs-lookup"><span data-stu-id="9c399-167">Changed behavior</span></span>
<span data-ttu-id="9c399-168">다음 섹션에서는 이 기능을 사용하는 경우 Microsoft Defender for Endpoint 및/또는 Microsoft 365 보안 센터에서 관찰할 변경 내용을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="9c399-168">The following section lists the changes you'll observe in Microsoft Defender for Endpoint and/or Microsoft 365 Security Center when this capability is enabled.</span></span> 
 
1.  <span data-ttu-id="9c399-169">Microsoft Defender에서 끝점으로 온보딩되지 않은 장치는 장치 인벤토리, 고급 헌팅 및 API 쿼리에 표시될 것으로 예상됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c399-169">Devices that are not onboarded to Microsoft Defender to Endpoint are expected to appear in the device inventory, advanced hunting, and API queries.</span></span> <span data-ttu-id="9c399-170">이렇게 하여 쿼리 결과의 크기가 크게 증가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c399-170">This may significantly increase the size of query results.</span></span> 
    1. <span data-ttu-id="9c399-171">고급 헌팅의 "DeviceInfo" 및 "DeviceNetworkInfo" 테이블은 이제 검색된 장치를 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="9c399-171">"DeviceInfo" and "DeviceNetworkInfo" tables in Advanced Hunting will now hold discovered device.</span></span> <span data-ttu-id="9c399-172">"OnboardingStatus" 특성을 사용하여 이러한 장치를 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c399-172">You can filter out those devices by using “OnboardingStatus” attribute.</span></span>

    2. <span data-ttu-id="9c399-173">검색된 장치는 스트리밍 API 쿼리 결과에 표시될 것으로 예상됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c399-173">Discovered devices are expected to appear in Streaming API query results.</span></span> <span data-ttu-id="9c399-174">쿼리에서 필터를 사용하여 이러한 장치를 `OnboardingStatus` 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c399-174">You can filter out those devices by using the `OnboardingStatus` filter in your query.</span></span> 

2.  <span data-ttu-id="9c399-175">관리되지 않는 장치는 정의된 기준에 따라 기존 장치 그룹에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c399-175">Unmanaged devices will be assigned to existing device groups based on the defined criteria.</span></span> 
3.  <span data-ttu-id="9c399-176">드문 경우지만 표준 검색은 네트워크 모니터 또는 보안 도구에서 경고를 트리거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c399-176">In rare cases, Standard discovery might trigger alerts on network monitors or security tools.</span></span> <span data-ttu-id="9c399-177">이러한 이벤트가 재발하지 않도록 피드백을 제공하세요.</span><span class="sxs-lookup"><span data-stu-id="9c399-177">Please provide feedback, if you experience such events, to help prevent these issues from recurring.</span></span> <span data-ttu-id="9c399-178">특정 대상 또는 전체 서브넷이 Standard 검색에 의해 적극적으로 프로브되는 것을 명시적으로 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c399-178">You can explicitly exclude specific targets or entire subnets from being actively probed by Standard discovery.</span></span> 



## <a name="next-steps"></a><span data-ttu-id="9c399-179">다음 단계</span><span class="sxs-lookup"><span data-stu-id="9c399-179">Next steps</span></span>
- [<span data-ttu-id="9c399-180">장치 검색 구성</span><span class="sxs-lookup"><span data-stu-id="9c399-180">Configure device discovery</span></span>](configure-device-discovery.md)
- [<span data-ttu-id="9c399-181">장치 검색 FAQ</span><span class="sxs-lookup"><span data-stu-id="9c399-181">Device discovery FAQs</span></span>](device-discovery-faq.md)
