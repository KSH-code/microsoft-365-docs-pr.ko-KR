---
title: Endpoint용 Microsoft Defender에서 불안정한 센서 수정
description: 서비스가 장치에서 데이터를 수신할 수 있도록 잘못 구성되거나 비활성으로 보고되는 장치 센서를 수정합니다.
keywords: 잘못 구성, 비활성, 센서 수정, 센서 상태, 센서 데이터 없음, 센서 데이터, 통신 장애, 통신
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
ms.date: 11/06/2020
ms.technology: mde
ms.openlocfilehash: c4cdc80170b49a111f476d2d17222c41e2b5c55f
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935368"
---
# <a name="fix-unhealthy-sensors-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="7d9b4-104">Endpoint용 Microsoft Defender에서 불안정한 센서 수정</span><span class="sxs-lookup"><span data-stu-id="7d9b4-104">Fix unhealthy sensors in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7d9b4-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="7d9b4-105">**Applies to:**</span></span>
- [<span data-ttu-id="7d9b4-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="7d9b4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="7d9b4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7d9b4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

- <span data-ttu-id="7d9b4-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="7d9b4-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7d9b4-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="7d9b4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-fixsensor-abovefoldlink)

<span data-ttu-id="7d9b4-110">잘못 구성되거나 비활성으로 분류된 장치는 다양한 원인으로 인해 플래그가 지정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d9b4-110">Devices that are categorized as misconfigured or inactive can be flagged due to varying causes.</span></span> <span data-ttu-id="7d9b4-111">이 섹션에서는 장치가 비활성 또는 잘못 구성된 것으로 분류될 수 있는 원인에 대한 몇 가지 설명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7d9b4-111">This section provides some explanations as to what might have caused a device to be categorized as inactive or misconfigured.</span></span>

## <a name="inactive-devices"></a><span data-ttu-id="7d9b4-112">비활성 장치</span><span class="sxs-lookup"><span data-stu-id="7d9b4-112">Inactive devices</span></span>

<span data-ttu-id="7d9b4-113">비활성 장치는 문제로 인해 플래그가 지정되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d9b4-113">An inactive device is not necessarily flagged due to an issue.</span></span> <span data-ttu-id="7d9b4-114">장치에서 수행한 다음 작업을 수행하면 장치가 비활성으로 분류될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d9b4-114">The following actions taken on a device can cause a device to be categorized as inactive:</span></span>

### <a name="device-is-not-in-use"></a><span data-ttu-id="7d9b4-115">디바이스가 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d9b4-115">Device is not in use</span></span>

<span data-ttu-id="7d9b4-116">어떤 이유로든 장치를 7일 이상 사용하지 않은 경우 포털에서 '비활성' 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d9b4-116">If the device has not been in use for more than seven days for any reason, it will remain in an ‘Inactive’ status in the portal.</span></span>

### <a name="device-was-reinstalled-or-renamed"></a><span data-ttu-id="7d9b4-117">장치가 다시 설치되거나 이름을 변경했습니다.</span><span class="sxs-lookup"><span data-stu-id="7d9b4-117">Device was reinstalled or renamed</span></span>
<span data-ttu-id="7d9b4-118">다시 설치되거나 이름을 변경하면 디바이스에서 새 장치 엔터티가 Microsoft Defender 보안 센터.</span><span class="sxs-lookup"><span data-stu-id="7d9b4-118">A reinstalled or renamed device will generate a new device entity in Microsoft Defender Security Center.</span></span> <span data-ttu-id="7d9b4-119">이전 장치 엔터티는 포털에서 '비활성' 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d9b4-119">The previous device entity will remain with an ‘Inactive’ status in the portal.</span></span> <span data-ttu-id="7d9b4-120">장치를 다시 설치하고 Endpoint용 Defender 패키지를 배포한 경우 새 장치 이름을 검색하여 장치가 정상적으로 보고하고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7d9b4-120">If you reinstalled a device and deployed the Defender for Endpoint package, search for the new device name to verify that the device is reporting normally.</span></span>

### <a name="device-was-offboarded"></a><span data-ttu-id="7d9b4-121">디바이스가 오프보더된 경우</span><span class="sxs-lookup"><span data-stu-id="7d9b4-121">Device was offboarded</span></span>
<span data-ttu-id="7d9b4-122">장치가 오프보더된 경우 장치 목록에 계속 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d9b4-122">If the device was offboarded, it will still appear in devices list.</span></span> <span data-ttu-id="7d9b4-123">7일이 지난 후 장치 상태는 비활성으로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d9b4-123">After seven days, the device health state should change to inactive.</span></span>

### <a name="device-is-not-sending-signals"></a><span data-ttu-id="7d9b4-124">장치가 신호를 보내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d9b4-124">Device is not sending signals</span></span>
<span data-ttu-id="7d9b4-125">장치가 잘못된 구성 장치 분류에 속하는 조건을 포함하여 어떤 이유로든 끝점 채널에 대한 Microsoft Defender에 7일 넘게 신호를 보내지 않는 경우 비활성으로 간주될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d9b4-125">If the device is not sending any signals for more than seven days to any of the Microsoft Defender for Endpoint channels for any reason including conditions that fall under misconfigured devices classification, a device can be considered inactive.</span></span> 

<span data-ttu-id="7d9b4-126">장치가 '활성' 상태일 것으로 예상하나요?</span><span class="sxs-lookup"><span data-stu-id="7d9b4-126">Do you expect a device to be in ‘Active’ status?</span></span> <span data-ttu-id="7d9b4-127">[지원 티켓 을 열 수 있습니다.](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636206786382823561)</span><span class="sxs-lookup"><span data-stu-id="7d9b4-127">[Open a support ticket](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636206786382823561).</span></span>

## <a name="misconfigured-devices"></a><span data-ttu-id="7d9b4-128">잘못 구성된 장치</span><span class="sxs-lookup"><span data-stu-id="7d9b4-128">Misconfigured devices</span></span>
<span data-ttu-id="7d9b4-129">잘못 구성된 장치는 다음으로 더 분류될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d9b4-129">Misconfigured devices can further be classified to:</span></span>
- <span data-ttu-id="7d9b4-130">통신 장애</span><span class="sxs-lookup"><span data-stu-id="7d9b4-130">Impaired communications</span></span>
- <span data-ttu-id="7d9b4-131">센서 데이터 없음</span><span class="sxs-lookup"><span data-stu-id="7d9b4-131">No sensor data</span></span>

### <a name="impaired-communications"></a><span data-ttu-id="7d9b4-132">통신 장애</span><span class="sxs-lookup"><span data-stu-id="7d9b4-132">Impaired communications</span></span>
<span data-ttu-id="7d9b4-133">이 상태는 장치와 서비스 간에 통신이 제한되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d9b4-133">This status indicates that there's limited communication between the device and the service.</span></span>

<span data-ttu-id="7d9b4-134">다음 제안된 작업은 통신 장애가 있는 잘못 구성된 장치와 관련된 문제를 해결하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d9b4-134">The following suggested actions can help fix issues related to a misconfigured device with impaired communications:</span></span>

- [<span data-ttu-id="7d9b4-135">디바이스가 인터넷에 연결되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="7d9b4-135">Ensure the device has Internet connection</span></span>](troubleshoot-onboarding.md#troubleshoot-onboarding-issues-on-the-device)</br>
  <span data-ttu-id="7d9b4-136">엔드포인트용 Microsoft Defender 센서를 사용하려면 센서 데이터를 보고하고 엔드포인트용 Microsoft Defender 서비스와 통신하기 위해 WinHTTP(Microsoft Windows HTTP)가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7d9b4-136">The Microsoft Defender for Endpoint sensor requires Microsoft Windows HTTP (WinHTTP) to report sensor data and communicate with the Microsoft Defender for Endpoint service.</span></span>

- [<span data-ttu-id="7d9b4-137">끝점 서비스 URL용 Microsoft Defender에 대한 클라이언트 연결 확인</span><span class="sxs-lookup"><span data-stu-id="7d9b4-137">Verify client connectivity to Microsoft Defender for Endpoint service URLs</span></span>](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)</br>
  <span data-ttu-id="7d9b4-138">프록시 구성이 성공적으로 완료되어 WinHTTP가 사용자 환경의 프록시 서버를 검색하고 통신할 수 있는지, 프록시 서버에서 끝점 서비스 URL에 대한 Microsoft Defender에 대한 트래픽을 허용하는지 확인</span><span class="sxs-lookup"><span data-stu-id="7d9b4-138">Verify the proxy configuration completed successfully, that WinHTTP can discover and communicate through the proxy server in your environment, and that the proxy server allows traffic to the Microsoft Defender for Endpoint service URLs.</span></span>

<span data-ttu-id="7d9b4-139">수정 작업을 수행한 경우 장치 상태가 여전히 잘못 구성된 경우 지원 [티켓 을 를 열 수 있습니다.](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409)</span><span class="sxs-lookup"><span data-stu-id="7d9b4-139">If you took corrective actions and the device status is still misconfigured, [open a support ticket](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409).</span></span>

### <a name="no-sensor-data"></a><span data-ttu-id="7d9b4-140">센서 데이터 없음</span><span class="sxs-lookup"><span data-stu-id="7d9b4-140">No sensor data</span></span>
<span data-ttu-id="7d9b4-141">'센서 데이터 없음' 상태의 잘못 구성된 장치는 서비스와 통신하지만 부분 센서 데이터만 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d9b4-141">A misconfigured device with status ‘No sensor data’ has communication with the service but can only report partial sensor data.</span></span>
<span data-ttu-id="7d9b4-142">다음 작업을 수행하여 '센서 데이터 없음' 상태의 잘못 구성된 장치와 관련된 알려진 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="7d9b4-142">Follow theses actions to correct known issues related to a misconfigured device with status ‘No sensor data’:</span></span>

- [<span data-ttu-id="7d9b4-143">디바이스가 인터넷에 연결되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="7d9b4-143">Ensure the device has Internet connection</span></span>](troubleshoot-onboarding.md#troubleshoot-onboarding-issues-on-the-device)</br>
  <span data-ttu-id="7d9b4-144">엔드포인트용 Microsoft Defender 센서를 사용하려면 센서 데이터를 보고하고 엔드포인트용 Microsoft Defender 서비스와 통신하기 위해 WinHTTP(Microsoft Windows HTTP)가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7d9b4-144">The Microsoft Defender for Endpoint sensor requires Microsoft Windows HTTP (WinHTTP) to report sensor data and communicate with the Microsoft Defender for Endpoint service.</span></span>

- [<span data-ttu-id="7d9b4-145">끝점 서비스 URL용 Microsoft Defender에 대한 클라이언트 연결 확인</span><span class="sxs-lookup"><span data-stu-id="7d9b4-145">Verify client connectivity to Microsoft Defender for Endpoint service URLs</span></span>](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)</br>
  <span data-ttu-id="7d9b4-146">프록시 구성이 성공적으로 완료되어 WinHTTP가 사용자 환경의 프록시 서버를 검색하고 통신할 수 있는지, 프록시 서버에서 끝점 서비스 URL에 대한 Microsoft Defender에 대한 트래픽을 허용하는지 확인</span><span class="sxs-lookup"><span data-stu-id="7d9b4-146">Verify the proxy configuration completed successfully, that WinHTTP can discover and communicate through the proxy server in your environment, and that the proxy server allows traffic to the Microsoft Defender for Endpoint service URLs.</span></span>

- [<span data-ttu-id="7d9b4-147">진단 데이터 서비스를 사용하도록 설정되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="7d9b4-147">Ensure the diagnostic data service is enabled</span></span>](troubleshoot-onboarding.md#ensure-the-diagnostics-service-is-enabled)</br>
<span data-ttu-id="7d9b4-148">장치가 올바르게 보고되지 않는 경우 Windows 10 진단 데이터 서비스가 자동으로 시작되고 끝점에서 실행 중인지 확인해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d9b4-148">If the devices aren't reporting correctly, you might need to check that the Windows 10 diagnostic data service is set to automatically start and is running on the endpoint.</span></span>

- [<span data-ttu-id="7d9b4-149">정책에 Microsoft Defender 바이러스 백신 사용하지 않도록 설정되어 있지 않은지 확인</span><span class="sxs-lookup"><span data-stu-id="7d9b4-149">Ensure that Microsoft Defender Antivirus is not disabled by policy</span></span>](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)</br>
<span data-ttu-id="7d9b4-150">장치에서 타사 맬웨어 방지 클라이언트를 실행하는 경우 끝점용 Defender 에이전트는 ELAM(Microsoft Defender 바이러스 백신 맬웨어 방지 조기 실행) 드라이버를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d9b4-150">If your devices are running a third-party antimalware client, the Defender for Endpoint agent needs the Microsoft Defender Antivirus Early Launch Antimalware (ELAM) driver to be enabled.</span></span>

<span data-ttu-id="7d9b4-151">수정 작업을 수행한 경우 장치 상태가 여전히 잘못 구성된 경우 지원 [티켓 을 를 열 수 있습니다.](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409)</span><span class="sxs-lookup"><span data-stu-id="7d9b4-151">If you took corrective actions and the device status is still misconfigured, [open a support ticket](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409).</span></span>

## <a name="see-also"></a><span data-ttu-id="7d9b4-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7d9b4-152">See also</span></span>
- [<span data-ttu-id="7d9b4-153">끝점에 대한 Microsoft Defender의 센서 상태 확인</span><span class="sxs-lookup"><span data-stu-id="7d9b4-153">Check sensor health state in Microsoft Defender for Endpoint</span></span>](check-sensor-status.md)
