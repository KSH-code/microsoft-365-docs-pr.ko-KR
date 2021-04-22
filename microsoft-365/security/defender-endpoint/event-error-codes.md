---
title: 이벤트 뷰어를 사용하여 이벤트 및 오류 검토
description: Microsoft Defender for Endpoint Service에서 보고하는 모든 이벤트에 대한 설명 및 추가 문제 해결 단계(필요한 경우)를 얻습니다.
keywords: 문제 해결, 이벤트 뷰어, 로그 요약, 오류 코드, 실패, 끝점 서비스용 Microsoft Defender를 시작할 수 없습니다. 중단, 시작할 수 없습니다.
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
ms.date: 05/21/2018
ms.technology: mde
ms.openlocfilehash: a8b7268e89470a85a34015967b69abb1818fe64f
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933844"
---
# <a name="review-events-and-errors-using-event-viewer"></a><span data-ttu-id="361b3-104">이벤트 뷰어를 사용하여 이벤트 및 오류 검토</span><span class="sxs-lookup"><span data-stu-id="361b3-104">Review events and errors using Event Viewer</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="361b3-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="361b3-105">**Applies to:**</span></span>
- <span data-ttu-id="361b3-106">이벤트 뷰어</span><span class="sxs-lookup"><span data-stu-id="361b3-106">Event Viewer</span></span>
- <span data-ttu-id="361b3-107">[엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037) </span><span class="sxs-lookup"><span data-stu-id="361b3-107">[Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>
- [<span data-ttu-id="361b3-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="361b3-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="361b3-109">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="361b3-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="361b3-110">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

<span data-ttu-id="361b3-111">개별 디바이스의 이벤트 뷰어에서 이벤트 [ID를](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-111">You can review event IDs in the [Event Viewer](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) on individual devices.</span></span>

<span data-ttu-id="361b3-112">예를 들어 장치가 장치 목록에 나타나지 않는 경우 디바이스에서 이벤트 ID를 찾아야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-112">For example, if devices aren't appearing in the **Devices list**, you might need to look for event IDs on the devices.</span></span> <span data-ttu-id="361b3-113">그런 다음 이 표를 사용하여 추가 문제 해결 단계를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-113">You can then use this table to determine further troubleshooting steps.</span></span>

<span data-ttu-id="361b3-114">**이벤트 뷰어를 열고 끝점용 Microsoft Defender 서비스 이벤트 로그를 찾습니다.**</span><span class="sxs-lookup"><span data-stu-id="361b3-114">**Open Event Viewer and find the Microsoft Defender for Endpoint service event log:**</span></span>

1. <span data-ttu-id="361b3-115">Windows **메뉴에서** 시작을 클릭하고 이벤트 **뷰어를 입력한** 다음 **Enter를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="361b3-115">Click **Start** on the Windows menu, type **Event Viewer**, and press **Enter**.</span></span>

2. <span data-ttu-id="361b3-116">로그 목록의 **로그** 요약에서 **Microsoft-Windows-SENSE/Operational이** 표시될 때까지 스크롤합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-116">In the log list, under **Log Summary**, scroll until you see **Microsoft-Windows-SENSE/Operational**.</span></span> <span data-ttu-id="361b3-117">항목을 두 번 클릭하여 로그를 니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-117">Double-click the item to open the log.</span></span>

   <span data-ttu-id="361b3-118">a.</span><span class="sxs-lookup"><span data-stu-id="361b3-118">a.</span></span>  <span data-ttu-id="361b3-119">응용 프로그램 및 서비스 로그   >  **Microsoft**  >  **Windows**  >  **SENSE를** 확장하고 작동을 클릭하여 로그에 액세스할 수도 **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="361b3-119">You can also access the log by expanding **Applications and Services Logs** > **Microsoft** > **Windows** > **SENSE** and click on **Operational**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="361b3-120">SENSE는 끝점용 Microsoft Defender의 전원을 공급하는 동작 센서를 참조하는 데 사용되는 내부 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-120">SENSE is the internal name used to refer to the behavioral sensor that powers Microsoft Defender for Endpoint.</span></span>

3. <span data-ttu-id="361b3-121">서비스에서 기록한 이벤트가 로그에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-121">Events recorded by the service will appear in the log.</span></span> <span data-ttu-id="361b3-122">서비스에서 기록하는 이벤트 목록은 다음 표를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="361b3-122">See the following table for a list of events recorded by the service.</span></span>

<table>
<tbody style="vertical-align:top;">
<tr>
<th><span data-ttu-id="361b3-123">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="361b3-123">Event ID</span></span></th>
<th><span data-ttu-id="361b3-124">메시지</span><span class="sxs-lookup"><span data-stu-id="361b3-124">Message</span></span></th>
<th><span data-ttu-id="361b3-125">설명</span><span class="sxs-lookup"><span data-stu-id="361b3-125">Description</span></span></th>
<th><span data-ttu-id="361b3-126">작업</span><span class="sxs-lookup"><span data-stu-id="361b3-126">Action</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="361b3-127">1</span><span class="sxs-lookup"><span data-stu-id="361b3-127">1</span></span></td>
<td><span data-ttu-id="361b3-128">끝점용 Microsoft Defender 서비스가 <code>variable</code> 시작되었습니다(버전).</span><span class="sxs-lookup"><span data-stu-id="361b3-128">Microsoft Defender for Endpoint service started (Version <code>variable</code>).</span></span></td>
<td><span data-ttu-id="361b3-129">시스템 시작, 종료 및 온보더링 중에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-129">Occurs during system startup, shut down, and during onboarding.</span></span></td>
<td><span data-ttu-id="361b3-130">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-130">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="361b3-131">2</span><span class="sxs-lookup"><span data-stu-id="361b3-131">2</span></span></td>
<td><span data-ttu-id="361b3-132">끝점용 Microsoft Defender 서비스 종료.</span><span class="sxs-lookup"><span data-stu-id="361b3-132">Microsoft Defender for Endpoint service shutdown.</span></span></td>
<td><span data-ttu-id="361b3-133">디바이스가 종료되거나 오프보더될 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-133">Occurs when the device is shut down or offboarded.</span></span></td>
<td><span data-ttu-id="361b3-134">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-134">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="361b3-135">3</span><span class="sxs-lookup"><span data-stu-id="361b3-135">3</span></span></td>
<td><span data-ttu-id="361b3-136">끝점용 Microsoft Defender 서비스를 시작하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-136">Microsoft Defender for Endpoint service failed to start.</span></span> <span data-ttu-id="361b3-137">오류 코드: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="361b3-137">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="361b3-138">서비스가 시작되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-138">Service didn't start.</span></span></td>
<td><span data-ttu-id="361b3-139">다른 메시지를 검토하여 가능한 원인 및 문제 해결 단계를 파악합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-139">Review other messages to determine possible cause and troubleshooting steps.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="361b3-140">4 </span><span class="sxs-lookup"><span data-stu-id="361b3-140">4</span></span></td>
<td><span data-ttu-id="361b3-141">끝점용 Microsoft Defender 서비스가 에 서버에 <code>variable</code> 연결했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-141">Microsoft Defender for Endpoint service contacted the server at <code>variable</code>.</span></span></td>
<td><span data-ttu-id="361b3-142">변수 = 끝점 처리 서버용 Defender의 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-142">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="361b3-143">이 URL은 방화벽 또는 네트워크 활동에 있는 URL과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-143">This URL will match that seen in the Firewall or network activity.</span></span></td>
<td><span data-ttu-id="361b3-144">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-144">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="361b3-145">5 </span><span class="sxs-lookup"><span data-stu-id="361b3-145">5</span></span></td>
<td><span data-ttu-id="361b3-146">끝점용 Microsoft Defender 서비스가 의 서버에 연결하지 <code>variable</code> 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-146">Microsoft Defender for Endpoint service failed to connect to the server at <code>variable</code>.</span></span></td>
<td><span data-ttu-id="361b3-147">변수 = 끝점 처리 서버용 Defender의 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-147">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="361b3-148">서비스가 해당 URL의 외부 처리 서버에 연결하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-148">The service couldn't contact the external processing servers at that URL.</span></span></td>
<td><span data-ttu-id="361b3-149">URL에 대한 연결을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-149">Check the connection to the URL.</span></span> <span data-ttu-id="361b3-150">프록시 <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">및 인터넷 연결 구성을 참조합니다.</a></span><span class="sxs-lookup"><span data-stu-id="361b3-150">See <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="361b3-151">6 </span><span class="sxs-lookup"><span data-stu-id="361b3-151">6</span></span></td>
<td><span data-ttu-id="361b3-152">Microsoft Defender for Endpoint Service가 온보딩되지 않은 경우 온보딩 매개 변수를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-152">Microsoft Defender for Endpoint service is not onboarded and no onboarding parameters were found.</span></span></td>
<td><span data-ttu-id="361b3-153">장치가 올바르게 온보드되지 않았고 포털에 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-153">The device didn't onboard correctly and won't be reporting to the portal.</span></span></td>
<td><span data-ttu-id="361b3-154">서비스를 시작하기 전에 온보더링을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-154">Onboarding must be run before starting the service.</span></span><br>
<span data-ttu-id="361b3-155">온보딩 설정 및 스크립트가 제대로 배포되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-155">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="361b3-156">구성 패키지를 다시 재배포해 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-156">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="361b3-157"><a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Windows 10 장치 온보드를 참조합니다.</a></span><span class="sxs-lookup"><span data-stu-id="361b3-157">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="361b3-158">7 </span><span class="sxs-lookup"><span data-stu-id="361b3-158">7</span></span></td>
<td><span data-ttu-id="361b3-159">Microsoft Defender for Endpoint Service에서 온보딩 매개 변수를 읽지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-159">Microsoft Defender for Endpoint service failed to read the onboarding parameters.</span></span> <span data-ttu-id="361b3-160">실패: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="361b3-160">Failure: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="361b3-161">변수 = 자세한 오류 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-161">Variable = detailed error description.</span></span> <span data-ttu-id="361b3-162">장치가 올바르게 온보드되지 않았고 포털에 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-162">The device didn't onboard correctly and won't be reporting to the portal.</span></span></td>
<td><span data-ttu-id="361b3-163">온보딩 설정 및 스크립트가 제대로 배포되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-163">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="361b3-164">구성 패키지를 다시 재배포해 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-164">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="361b3-165"><a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Windows 10 장치 온보드를 참조합니다.</a></span><span class="sxs-lookup"><span data-stu-id="361b3-165">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="361b3-166">8 </span><span class="sxs-lookup"><span data-stu-id="361b3-166">8</span></span></td>
<td><span data-ttu-id="361b3-167">Microsoft Defender for Endpoint Service에서 구성을 정리하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-167">Microsoft Defender for Endpoint service failed to clean its configuration.</span></span> <span data-ttu-id="361b3-168">오류 코드: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="361b3-168">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="361b3-169"><b>온보드 중:</b> 서비스가 온보더링하는 동안 구성을 정리하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-169"><b>During onboarding:</b> The service failed to clean its configuration during the onboarding.</span></span> <span data-ttu-id="361b3-170">온보더링 프로세스가 계속됩니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-170">The onboarding process continues.</span></span> <br><br> <span data-ttu-id="361b3-171"><b>오프보더 중:</b> 서비스가 오프보더하는 동안 구성을 정리하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-171"><b>During offboarding:</b> The service failed to clean its configuration during the offboarding.</span></span> <span data-ttu-id="361b3-172">오프보더 프로세스가 완료 했지만 서비스가 계속 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-172">The offboarding process finished but the service keeps running.</span></span>
 </td>
<td><span data-ttu-id="361b3-173"><b>온보더링:</b> 필요한 작업은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-173"><b>Onboarding:</b> No action required.</span></span> <br><br> <span data-ttu-id="361b3-174"><b>오프보더링:</b> 시스템을 다시 부트합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-174"><b>Offboarding:</b> Reboot the system.</span></span><br>
<span data-ttu-id="361b3-175"><a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Windows 10 장치 온보드를 참조합니다.</a></span><span class="sxs-lookup"><span data-stu-id="361b3-175">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="361b3-176">9 </span><span class="sxs-lookup"><span data-stu-id="361b3-176">9</span></span></td>
<td><span data-ttu-id="361b3-177">끝점용 Microsoft Defender 서비스가 시작 유형을 변경하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-177">Microsoft Defender for Endpoint service failed to change its start type.</span></span> <span data-ttu-id="361b3-178">오류 코드: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="361b3-178">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="361b3-179"><b>온보드 중:</b> 장치가 올바르게 온보드되지 않았고 포털에 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-179"><b>During onboarding:</b> The device didn't onboard correctly and won't be reporting to the portal.</span></span> <br><br><span data-ttu-id="361b3-180"><b>오프보더 중:</b> 서비스 시작 유형을 변경하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-180"><b>During offboarding:</b> Failed to change the service start type.</span></span> <span data-ttu-id="361b3-181">오프보더 프로세스가 계속됩니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-181">The offboarding process continues.</span></span> </td>
<td><span data-ttu-id="361b3-182">온보딩 설정 및 스크립트가 제대로 배포되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-182">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="361b3-183">구성 패키지를 다시 재배포해 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-183">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="361b3-184"><a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Windows 10 장치 온보드를 참조합니다.</a></span><span class="sxs-lookup"><span data-stu-id="361b3-184">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="361b3-185">10  </span><span class="sxs-lookup"><span data-stu-id="361b3-185">10</span></span></td>
<td><span data-ttu-id="361b3-186">Microsoft Defender for Endpoint Service에서 온보딩 정보를 유지하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-186">Microsoft Defender for Endpoint service failed to persist the onboarding information.</span></span> <span data-ttu-id="361b3-187">오류 코드: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="361b3-187">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="361b3-188">장치가 올바르게 온보드되지 않았고 포털에 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-188">The device didn't onboard correctly and won't be reporting to the portal.</span></span></td>
<td><span data-ttu-id="361b3-189">온보딩 설정 및 스크립트가 제대로 배포되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-189">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="361b3-190">구성 패키지를 다시 재배포해 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-190">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="361b3-191"><a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Windows 10 장치 온보드를 참조합니다.</a></span><span class="sxs-lookup"><span data-stu-id="361b3-191">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="361b3-192">11 </span><span class="sxs-lookup"><span data-stu-id="361b3-192">11</span></span></td>
<td><span data-ttu-id="361b3-193">Endpoint Service용 Defender의 온보딩 또는 다시 온보딩이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-193">Onboarding or re-onboarding of Defender for Endpoint service completed.</span></span></td>
<td><span data-ttu-id="361b3-194">장치가 올바르게 온보드되었습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-194">The device onboarded correctly.</span></span></td>
<td><span data-ttu-id="361b3-195">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-195">Normal operating notification; no action required.</span></span><br>
<span data-ttu-id="361b3-196">디바이스가 포털에 표시될 때 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-196">It may take several hours for the device to appear in the portal.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="361b3-197">12 </span><span class="sxs-lookup"><span data-stu-id="361b3-197">12</span></span></td>
<td><span data-ttu-id="361b3-198">끝점용 Microsoft Defender가 기본 구성을 적용하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-198">Microsoft Defender for Endpoint failed to apply the default configuration.</span></span></td>
<td><span data-ttu-id="361b3-199">서비스가 기본 구성을 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-199">Service was unable to apply the default configuration.</span></span></td>
<td><span data-ttu-id="361b3-200">이 오류는 잠시 후에 해결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-200">This error should resolve after a short period of time.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="361b3-201">13</span><span class="sxs-lookup"><span data-stu-id="361b3-201">13</span></span></td>
<td><span data-ttu-id="361b3-202">끝점용 Microsoft Defender 장치 ID 계산: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="361b3-202">Microsoft Defender for Endpoint device ID calculated: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="361b3-203">정상적인 작동 프로세스.</span><span class="sxs-lookup"><span data-stu-id="361b3-203">Normal operating process.</span></span></td>
<td><span data-ttu-id="361b3-204">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-204">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="361b3-205">15 </span><span class="sxs-lookup"><span data-stu-id="361b3-205">15</span></span></td>
<td><span data-ttu-id="361b3-206">끝점용 Microsoft Defender는 URL로 명령 채널을 시작할 수 없습니다. <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="361b3-206">Microsoft Defender for Endpoint cannot start command channel with URL: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="361b3-207">변수 = 끝점 처리 서버용 Defender의 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-207">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="361b3-208">서비스가 해당 URL의 외부 처리 서버에 연결하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-208">The service couldn't contact the external processing servers at that URL.</span></span></td>
<td><span data-ttu-id="361b3-209">URL에 대한 연결을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-209">Check the connection to the URL.</span></span> <span data-ttu-id="361b3-210">프록시 <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">및 인터넷 연결 구성을 참조합니다.</a></span><span class="sxs-lookup"><span data-stu-id="361b3-210">See <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="361b3-211">17 </span><span class="sxs-lookup"><span data-stu-id="361b3-211">17</span></span></td>
<td><span data-ttu-id="361b3-212">끝점용 Microsoft Defender 서비스가 연결된 사용자 환경 및 원격 분석 서비스 위치를 변경하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-212">Microsoft Defender for Endpoint service failed to change the Connected User Experiences and Telemetry service location.</span></span> <span data-ttu-id="361b3-213">오류 코드: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="361b3-213">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="361b3-214">Windows 원격 분석 서비스에 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-214">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="361b3-215"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">진단 데이터 서비스가 사용하도록 설정되어 있는지 확인합니다.</a></span><span class="sxs-lookup"><span data-stu-id="361b3-215"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="361b3-216">온보딩 설정 및 스크립트가 제대로 배포되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-216">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="361b3-217">구성 패키지를 다시 재배포해 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-217">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="361b3-218"><a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Windows 10 장치 온보드를 참조합니다.</a></span><span class="sxs-lookup"><span data-stu-id="361b3-218">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="361b3-219">18 </span><span class="sxs-lookup"><span data-stu-id="361b3-219">18</span></span></td>
<td><span data-ttu-id="361b3-220">OOBE(Windows 시작)가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-220">OOBE (Windows Welcome) is completed.</span></span></td>
<td><span data-ttu-id="361b3-221">Windows 업데이트 설치가 완료된 후에만 서비스가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-221">Service will only start after any Windows updates have finished installing.</span></span></td>
<td><span data-ttu-id="361b3-222">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-222">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="361b3-223">19</span><span class="sxs-lookup"><span data-stu-id="361b3-223">19</span></span></td>
<td><span data-ttu-id="361b3-224">OOBE(Windows 시작)가 아직 완료되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-224">OOBE (Windows Welcome) has not yet completed.</span></span></td>
<td><span data-ttu-id="361b3-225">Windows 업데이트 설치가 완료된 후에만 서비스가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-225">Service will only start after any Windows updates have finished installing.</span></span></td>
<td><span data-ttu-id="361b3-226">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-226">Normal operating notification; no action required.</span></span><br>
<span data-ttu-id="361b3-227">시스템을 다시 시작한 후에도 이 오류가 지속되면 모든 Windows 업데이트가 전체 설치가 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-227">If this error persists after a system restart, ensure all Windows updates have full installed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="361b3-228">20</span><span class="sxs-lookup"><span data-stu-id="361b3-228">20</span></span></td>
<td><span data-ttu-id="361b3-229">OOBE(Windows 시작)가 완료될 때까지 기다릴 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-229">Cannot wait for OOBE (Windows Welcome) to complete.</span></span> <span data-ttu-id="361b3-230">오류 코드: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="361b3-230">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="361b3-231">내부 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-231">Internal error.</span></span></td>
<td><span data-ttu-id="361b3-232">시스템을 다시 시작한 후에도 이 오류가 지속되면 모든 Windows 업데이트가 전체 설치가 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-232">If this error persists after a system restart, ensure all Windows updates have full installed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="361b3-233">25</span><span class="sxs-lookup"><span data-stu-id="361b3-233">25</span></span></td>
<td><span data-ttu-id="361b3-234">Microsoft Defender for Endpoint Service가 레지스트리에서 상태를 다시 설정하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-234">Microsoft Defender for Endpoint service failed to reset health status in the registry.</span></span> <span data-ttu-id="361b3-235">오류 코드: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="361b3-235">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="361b3-236">장치가 올바르게 온보드되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-236">The device didn't onboard correctly.</span></span>
<span data-ttu-id="361b3-237">포털에 보고됩니다. 그러나 서비스가 SCCM 또는 레지스트리에 등록된 것으로 나타나지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-237">It will report to the portal, however the service may not appear as registered in SCCM or the registry.</span></span></td>
<td><span data-ttu-id="361b3-238">온보딩 설정 및 스크립트가 제대로 배포되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-238">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="361b3-239">구성 패키지를 다시 재배포해 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-239">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="361b3-240"><a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Windows 10 장치 온보드를 참조합니다.</a></span><span class="sxs-lookup"><span data-stu-id="361b3-240">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="361b3-241">26</span><span class="sxs-lookup"><span data-stu-id="361b3-241">26</span></span></td>
<td><span data-ttu-id="361b3-242">Microsoft Defender for Endpoint Service가 레지스트리에서 등록 상태를 설정하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-242">Microsoft Defender for Endpoint service failed to set the onboarding status in the registry.</span></span> <span data-ttu-id="361b3-243">오류 코드: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="361b3-243">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="361b3-244">장치가 올바르게 온보드되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-244">The device didn't onboard correctly.</span></span><br>
<span data-ttu-id="361b3-245">포털에 보고됩니다. 그러나 서비스가 SCCM 또는 레지스트리에 등록된 것으로 나타나지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-245">It will report to the portal, however the service may not appear as registered in SCCM or the registry.</span></span></td>
<td><span data-ttu-id="361b3-246">온보딩 설정 및 스크립트가 제대로 배포되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-246">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="361b3-247">구성 패키지를 다시 재배포해 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-247">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="361b3-248"><a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Windows 10 장치 온보드를 참조합니다.</a></span><span class="sxs-lookup"><span data-stu-id="361b3-248">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="361b3-249">27</span><span class="sxs-lookup"><span data-stu-id="361b3-249">27</span></span></td>
<td><span data-ttu-id="361b3-250">Microsoft Defender for Endpoint Service가 Microsoft Defender 바이러스 백신에서 SENSE 인식 모드를 사용하도록 설정하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-250">Microsoft Defender for Endpoint service failed to enable SENSE aware mode in Microsoft Defender Antivirus.</span></span> <span data-ttu-id="361b3-251">온보더링 프로세스가 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-251">Onboarding process failed.</span></span> <span data-ttu-id="361b3-252">오류 코드: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="361b3-252">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="361b3-253">일반적으로 다른 실시간 맬웨어 방지 제품이 장치에서 제대로 실행되고 장치가 Endpoint용 Defender에 보고하는 경우 Microsoft Defender 바이러스 백신은 특별한 수동 상태가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-253">Normally, Microsoft Defender Antivirus will enter a special passive state if another real-time antimalware product is running properly on the device, and the device is reporting to Defender for Endpoint.</span></span></td>
<td><span data-ttu-id="361b3-254">온보딩 설정 및 스크립트가 제대로 배포되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-254">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="361b3-255">구성 패키지를 다시 재배포해 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-255">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="361b3-256"><a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Windows 10 장치 온보드를 참조합니다.</a></span><span class="sxs-lookup"><span data-stu-id="361b3-256">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span><br>
<span data-ttu-id="361b3-257">실시간 맬웨어 방지 보호가 제대로 실행되고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-257">Ensure real-time antimalware protection is running properly.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="361b3-258">28</span><span class="sxs-lookup"><span data-stu-id="361b3-258">28</span></span></td>
<td><span data-ttu-id="361b3-259">Endpoint용 Microsoft Defender 연결된 사용자 환경 및 원격 분석 서비스 등록에 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-259">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration failed.</span></span> <span data-ttu-id="361b3-260">오류 코드: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="361b3-260">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="361b3-261">Windows 원격 분석 서비스에 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-261">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="361b3-262"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">진단 데이터 서비스가 사용하도록 설정되어 있는지 확인합니다.</a></span><span class="sxs-lookup"><span data-stu-id="361b3-262"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="361b3-263">온보딩 설정 및 스크립트가 제대로 배포되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-263">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="361b3-264">구성 패키지를 다시 재배포해 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-264">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="361b3-265"><a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Windows 10 장치 온보드를 참조합니다.</a></span><span class="sxs-lookup"><span data-stu-id="361b3-265">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="361b3-266">29</span><span class="sxs-lookup"><span data-stu-id="361b3-266">29</span></span></td>
<td><span data-ttu-id="361b3-267">오프보더 매개 변수를 읽지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-267">Failed to read the offboarding parameters.</span></span> <span data-ttu-id="361b3-268">오류 유형: %1, 오류 코드: %2, 설명: %3</span><span class="sxs-lookup"><span data-stu-id="361b3-268">Error type: %1, Error code: %2, Description: %3</span></span> </td>
<td><span data-ttu-id="361b3-269">이 이벤트는 시스템에서 오프보더 매개 변수를&#39;수 있는 경우 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-269">This event occurs when the system can&#39;t read the offboarding parameters.</span></span></td>
<td><span data-ttu-id="361b3-270">장치에 인터넷 액세스 권한이 있는지 확인한 다음 전체 오프보더 프로세스를 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-270">Ensure the device has Internet access, then run the entire offboarding process again.</span></span> <span data-ttu-id="361b3-271">오프보더 패키지가 만료되지 않은지 확인</span><span class="sxs-lookup"><span data-stu-id="361b3-271">Ensure the offboarding package hasn't expired.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="361b3-272">30</span><span class="sxs-lookup"><span data-stu-id="361b3-272">30</span></span></td>
<td><span data-ttu-id="361b3-273">Microsoft Defender for Endpoint Service가 Microsoft Defender 바이러스 백신에서 SENSE 인식 모드를 사용하지 않도록 설정하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-273">Microsoft Defender for Endpoint service failed to disable SENSE aware mode in Microsoft Defender Antivirus.</span></span> <span data-ttu-id="361b3-274">오류 코드: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="361b3-274">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="361b3-275">일반적으로 다른 실시간 맬웨어 방지 제품이 장치에서 제대로 실행되고 장치가 Endpoint용 Defender에 보고하는 경우 Microsoft Defender 바이러스 백신은 특별한 수동 상태가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-275">Normally, Microsoft Defender Antivirus will enter a special passive state if another real-time antimalware product is running properly on the device, and the device is reporting to Defender for Endpoint.</span></span></td>
<td><span data-ttu-id="361b3-276">온보딩 설정 및 스크립트가 제대로 배포되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-276">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="361b3-277">구성 패키지를 다시 재배포해 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-277">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="361b3-278"><a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Windows 10 장치 온보드 참조</a></span><span class="sxs-lookup"><span data-stu-id="361b3-278">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a></span></span><br>
<span data-ttu-id="361b3-279">실시간 맬웨어 방지 보호가 제대로 실행되고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-279">Ensure real-time antimalware protection is running properly.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="361b3-280">31</span><span class="sxs-lookup"><span data-stu-id="361b3-280">31</span></span></td>
<td><span data-ttu-id="361b3-281">Endpoint용 Microsoft Defender 연결된 사용자 환경 및 원격 분석 서비스 등록이 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-281">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service unregistration failed.</span></span> <span data-ttu-id="361b3-282">오류 코드: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="361b3-282">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="361b3-283">온보더링하는 동안 Windows 원격 분석 서비스에 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-283">An error occurred with the Windows telemetry service during onboarding.</span></span> <span data-ttu-id="361b3-284">오프보더 프로세스가 계속됩니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-284">The offboarding process continues.</span></span></td>
<td><span data-ttu-id="361b3-285">Windows 원격 분석 서비스 에서 <a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">오류를 검사합니다.</a></span><span class="sxs-lookup"><span data-stu-id="361b3-285"><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">Check for errors with the Windows telemetry service</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="361b3-286">32</span><span class="sxs-lookup"><span data-stu-id="361b3-286">32</span></span></td>
<td><span data-ttu-id="361b3-287">Microsoft Defender for Endpoint Service가 오프보딩 프로세스 후 자체 중지를 요청하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-287">Microsoft Defender for Endpoint service failed to request to stop itself after offboarding process.</span></span> <span data-ttu-id="361b3-288">오류 코드: %1</span><span class="sxs-lookup"><span data-stu-id="361b3-288">Failure code: %1</span></span></td>
<td><span data-ttu-id="361b3-289">오프보더하는 동안 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-289">An error occurred during offboarding.</span></span></td>
<td><span data-ttu-id="361b3-290">장치를 다시부팅합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-290">Reboot the device.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="361b3-291">33</span><span class="sxs-lookup"><span data-stu-id="361b3-291">33</span></span></td>
<td><span data-ttu-id="361b3-292">Microsoft Defender for Endpoint Service에서 SENSE GUID를 유지하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-292">Microsoft Defender for Endpoint service failed to persist SENSE GUID.</span></span> <span data-ttu-id="361b3-293">오류 코드: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="361b3-293">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="361b3-294">고유 식별자는 포털에 보고되는 각 장치를 나타내는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-294">A unique identifier is used to represent each device that is reporting to the portal.</span></span><br>
<span data-ttu-id="361b3-295">식별자가 유지되지 않는 경우 동일한 장치가 포털에 두 번 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-295">If the identifier doesn't persist, the same device might appear twice in the portal.</span></span></td>
<td><span data-ttu-id="361b3-296">장치에서 레지스트리 권한을 확인하여 서비스가 레지스트리를 업데이트할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-296">Check registry permissions on the device to ensure the service can update the registry.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="361b3-297">34</span><span class="sxs-lookup"><span data-stu-id="361b3-297">34</span></span></td>
<td><span data-ttu-id="361b3-298">끝점용 Microsoft Defender 서비스가 연결된 사용자 환경 및 원격 분석 서비스에 대한 종속성으로 추가하지 못하여 온보딩 프로세스가 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-298">Microsoft Defender for Endpoint service failed to add itself as a dependency on the Connected User Experiences and Telemetry service, causing onboarding process to fail.</span></span> <span data-ttu-id="361b3-299">오류 코드: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="361b3-299">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="361b3-300">Windows 원격 분석 서비스에 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-300">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="361b3-301"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">진단 데이터 서비스가 사용하도록 설정되어 있는지 확인합니다.</a></span><span class="sxs-lookup"><span data-stu-id="361b3-301"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="361b3-302">온보딩 설정 및 스크립트가 제대로 배포되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-302">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="361b3-303">구성 패키지를 다시 재배포해 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-303">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="361b3-304"><a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Windows 10 장치 온보드를 참조합니다.</a></span><span class="sxs-lookup"><span data-stu-id="361b3-304">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="361b3-305">35</span><span class="sxs-lookup"><span data-stu-id="361b3-305">35</span></span></td>
<td><span data-ttu-id="361b3-306">Microsoft Defender for Endpoint Service가 연결된 사용자 환경 및 원격 분석 서비스에 대한 종속성으로 자체적으로 제거하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-306">Microsoft Defender for Endpoint service failed to remove itself as a dependency on the Connected User Experiences and Telemetry service.</span></span> <span data-ttu-id="361b3-307">오류 코드: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="361b3-307">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="361b3-308">오프보더 중 Windows 원격 분석 서비스에 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-308">An error occurred with the Windows telemetry service during offboarding.</span></span> <span data-ttu-id="361b3-309">오프보더 프로세스가 계속됩니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-309">The offboarding process continues.</span></span>
</td>
<td><span data-ttu-id="361b3-310">Windows 진단 데이터 서비스에서 오류를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-310">Check for errors with the Windows diagnostic data service.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="361b3-311">36</span><span class="sxs-lookup"><span data-stu-id="361b3-311">36</span></span></td>
<td><span data-ttu-id="361b3-312">끝점용 Microsoft Defender 연결된 사용자 환경 및 원격 분석 서비스 등록이 성공했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-312">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration succeeded.</span></span> <span data-ttu-id="361b3-313">완료 코드: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="361b3-313">Completion code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="361b3-314">연결된 사용자 환경 및 원격 분석 서비스에 끝점에 대한 Defender 등록이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-314">Registering Defender for Endpoint with the Connected User Experiences and Telemetry service completed successfully.</span></span></td>
<td><span data-ttu-id="361b3-315">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-315">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="361b3-316">37</span><span class="sxs-lookup"><span data-stu-id="361b3-316">37</span></span></td>
<td><span data-ttu-id="361b3-317">끝점용 Microsoft Defender A 모듈이 할당량 초과됩니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-317">Microsoft Defender for Endpoint A module is about to exceed its quota.</span></span> <span data-ttu-id="361b3-318">모듈: %1, 할당량: {%2} {%3}, 할당량 사용률: %4.</span><span class="sxs-lookup"><span data-stu-id="361b3-318">Module: %1, Quota: {%2} {%3}, Percentage of quota utilization: %4.</span></span></td>
<td><span data-ttu-id="361b3-319">장치는 현재 24시간 창의 할당량에 거의 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-319">The device has almost used its allocated quota of the current 24-hour window.</span></span> <span data-ttu-id="361b3-320">이제는 스로틀이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-320">It’s about to be throttled.</span></span></td>
<td><span data-ttu-id="361b3-321">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-321">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="361b3-322">38</span><span class="sxs-lookup"><span data-stu-id="361b3-322">38</span></span></td>
<td><span data-ttu-id="361b3-323">네트워크 연결은 낮음으로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-323">Network connection is identified as low.</span></span> <span data-ttu-id="361b3-324">끝점용 Microsoft Defender는 %1분마다 서버에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-324">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="361b3-325">데이터 통신 연결: %2, 인터넷 사용 가능: %3, 무료 네트워크 사용 가능: %4.</span><span class="sxs-lookup"><span data-stu-id="361b3-325">Metered connection: %2, internet available: %3, free network available: %4.</span></span></td>
<td><span data-ttu-id="361b3-326">장치가 데이터 통신/유료 네트워크를 사용하고 있으며 서버에 자주 연결하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-326">The device is using a metered/paid network and will be contacting the server less frequently.</span></span></td>
<td><span data-ttu-id="361b3-327">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-327">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="361b3-328">39</span><span class="sxs-lookup"><span data-stu-id="361b3-328">39</span></span></td>
<td><span data-ttu-id="361b3-329">네트워크 연결은 정상으로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-329">Network connection is identified as normal.</span></span> <span data-ttu-id="361b3-330">끝점용 Microsoft Defender는 %1분마다 서버에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-330">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="361b3-331">데이터 통신 연결: %2, 인터넷 사용 가능: %3, 무료 네트워크 사용 가능: %4.</span><span class="sxs-lookup"><span data-stu-id="361b3-331">Metered connection: %2, internet available: %3, free network available: %4.</span></span></td>
<td><span data-ttu-id="361b3-332">장치가 데이터 데이터 연결/유료 연결을 사용하지 않는 경우 평소처럼 서버에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-332">The device isn't using a metered/paid connection and will contact the server as usual.</span></span></td>
<td><span data-ttu-id="361b3-333">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-333">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="361b3-334">40</span><span class="sxs-lookup"><span data-stu-id="361b3-334">40</span></span></td>
<td><span data-ttu-id="361b3-335">배터리 상태는 낮음으로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-335">Battery state is identified as low.</span></span> <span data-ttu-id="361b3-336">끝점용 Microsoft Defender는 %1분마다 서버에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-336">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="361b3-337">배터리 상태: %2.</span><span class="sxs-lookup"><span data-stu-id="361b3-337">Battery state: %2.</span></span></td>
<td><span data-ttu-id="361b3-338">디바이스의 배터리 잔량이 낮고 서버에 자주 연결하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-338">The device has low battery level and will contact the server less frequently.</span></span></td>
<td><span data-ttu-id="361b3-339">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-339">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="361b3-340">41</span><span class="sxs-lookup"><span data-stu-id="361b3-340">41</span></span></td>
<td><span data-ttu-id="361b3-341">배터리 상태는 정상으로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-341">Battery state is identified as normal.</span></span> <span data-ttu-id="361b3-342">끝점용 Microsoft Defender는 %1분마다 서버에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-342">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="361b3-343">배터리 상태: %2.</span><span class="sxs-lookup"><span data-stu-id="361b3-343">Battery state: %2.</span></span></td>
<td><span data-ttu-id="361b3-344">디바이스의 배터리 수준이 낮지 않은 경우 평소처럼 서버에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-344">The device doesn’t have low battery level and will contact the server as usual.</span></span></td>
<td><span data-ttu-id="361b3-345">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-345">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="361b3-346">42</span><span class="sxs-lookup"><span data-stu-id="361b3-346">42</span></span></td>
<td><span data-ttu-id="361b3-347">끝점용 Microsoft Defender 구성 요소가 작업을 수행하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-347">Microsoft Defender for Endpoint component failed to perform action.</span></span> <span data-ttu-id="361b3-348">구성 요소: %1, 작업: %2, 예외 유형: %3, 예외 메시지: %4</span><span class="sxs-lookup"><span data-stu-id="361b3-348">Component: %1, Action: %2, Exception Type: %3, Exception message: %4</span></span></td>
<td><span data-ttu-id="361b3-349">내부 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-349">Internal error.</span></span> <span data-ttu-id="361b3-350">서비스를 시작하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-350">The service failed to start.</span></span></td>
<td><span data-ttu-id="361b3-351">이 오류가 계속되면 지원에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-351">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="361b3-352">43</span><span class="sxs-lookup"><span data-stu-id="361b3-352">43</span></span></td>
<td><span data-ttu-id="361b3-353">끝점용 Microsoft Defender 구성 요소가 작업을 수행하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-353">Microsoft Defender for Endpoint component failed to perform action.</span></span> <span data-ttu-id="361b3-354">구성 요소: %1, 작업: %2, 예외 유형: %3, 예외 오류: %4, 예외 메시지: %5</span><span class="sxs-lookup"><span data-stu-id="361b3-354">Component: %1, Action: %2, Exception Type: %3, Exception Error: %4, Exception message: %5</span></span></td>
<td><span data-ttu-id="361b3-355">내부 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-355">Internal error.</span></span> <span data-ttu-id="361b3-356">서비스를 시작하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-356">The service failed to start.</span></span></td>
<td><span data-ttu-id="361b3-357">이 오류가 계속되면 지원에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-357">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="361b3-358">44</span><span class="sxs-lookup"><span data-stu-id="361b3-358">44</span></span></td>
<td><span data-ttu-id="361b3-359">끝점 서비스에 대한 Defender의 오프보딩이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-359">Offboarding of Defender for Endpoint service completed.</span></span></td>
<td><span data-ttu-id="361b3-360">서비스가 오프보더된 경우</span><span class="sxs-lookup"><span data-stu-id="361b3-360">The service was offboarded.</span></span></td>
<td><span data-ttu-id="361b3-361">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-361">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="361b3-362">45</span><span class="sxs-lookup"><span data-stu-id="361b3-362">45</span></span></td>
<td><span data-ttu-id="361b3-363">이벤트 추적 세션 [%1]을(를) 등록하고 시작하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-363">Failed to register and to start the event trace session [%1].</span></span> <span data-ttu-id="361b3-364">오류 코드: %2</span><span class="sxs-lookup"><span data-stu-id="361b3-364">Error code: %2</span></span></td>
<td><span data-ttu-id="361b3-365">ETW 세션을 만드는 동안 서비스 시작 시 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-365">An error occurred on service startup while creating ETW session.</span></span> <span data-ttu-id="361b3-366">이로 인해 서비스 시작 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-366">This caused service start-up failure.</span></span></td>
<td><span data-ttu-id="361b3-367">이 오류가 계속되면 지원에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-367">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="361b3-368">46</span><span class="sxs-lookup"><span data-stu-id="361b3-368">46</span></span></td>
<td><span data-ttu-id="361b3-369">리소스 부족으로 인해 이벤트 추적 세션 [%1]을(를) 등록하고 시작하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-369">Failed to register and start the event trace session [%1] due to lack of resources.</span></span> <span data-ttu-id="361b3-370">오류 코드: %2.</span><span class="sxs-lookup"><span data-stu-id="361b3-370">Error code: %2.</span></span> <span data-ttu-id="361b3-371">활성 이벤트 추적 세션이 너무 많기 때문에 이 가능성이 많을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-371">This is most likely because there are too many active event trace sessions.</span></span> <span data-ttu-id="361b3-372">서비스가 1분 후 다시 시도됩니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-372">The service will retry in 1 minute.</span></span></td>
<td><span data-ttu-id="361b3-373">리소스 부족으로 인해 ETW 세션을 만드는 동안 서비스 시작 시 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-373">An error occurred on service startup while creating ETW session due to lack of resources.</span></span> <span data-ttu-id="361b3-374">서비스가 시작되고 실행 중이지만 ETW 세션이 시작될 때까지 센서 이벤트를 보고하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-374">The service started and is running, but won't report any sensor event until the ETW session is started.</span></span></td>
<td><span data-ttu-id="361b3-375">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-375">Normal operating notification; no action required.</span></span> <span data-ttu-id="361b3-376">서비스가 1분마다 세션을 시작하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-376">The service will try to start the session every minute.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="361b3-377">47</span><span class="sxs-lookup"><span data-stu-id="361b3-377">47</span></span></td>
<td><span data-ttu-id="361b3-378">이벤트 추적 세션을 등록하고 시작했습니다. 이전 시도가 실패한 후에 복구됩니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-378">Successfully registered and started the event trace session - recovered after previous failed attempts.</span></span></td>
<td><span data-ttu-id="361b3-379">이 이벤트는 ETW 세션을 성공적으로 시작한 후 이전 이벤트를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-379">This event follows the previous event after successfully starting of the ETW session.</span></span></td>
<td><span data-ttu-id="361b3-380">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-380">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="361b3-381">48</span><span class="sxs-lookup"><span data-stu-id="361b3-381">48</span></span></td>
<td><span data-ttu-id="361b3-382">이벤트 추적 세션 [%2]에 공급자 [%1]을(를) 추가하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-382">Failed to add a provider [%1] to event trace session [%2].</span></span> <span data-ttu-id="361b3-383">오류 코드: %3.</span><span class="sxs-lookup"><span data-stu-id="361b3-383">Error code: %3.</span></span> <span data-ttu-id="361b3-384">즉, 이 공급자의 이벤트가 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-384">This means that events from this provider will not be reported.</span></span></td>
<td><span data-ttu-id="361b3-385">ETW 세션에 공급자를 추가하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-385">Failed to add a provider to ETW session.</span></span> <span data-ttu-id="361b3-386">따라서 공급자 이벤트가 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-386">As a result, the provider events aren’t reported.</span></span></td>
<td><span data-ttu-id="361b3-387">오류 코드를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-387">Check the error code.</span></span> <span data-ttu-id="361b3-388">오류가 계속되면 고객 지원에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-388">If the error persists contact Support.</span></span></td>
</tr>
</tr>
<tr>
   <td><span data-ttu-id="361b3-389">49</span><span class="sxs-lookup"><span data-stu-id="361b3-389">49</span></span></td>
   <td><span data-ttu-id="361b3-390">잘못된 클라우드 구성 명령이 수신 및 무시되었습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-390">Invalid cloud configuration command received and ignored.</span></span> <span data-ttu-id="361b3-391">버전: %1, 상태: %2, 오류 코드: %3, 메시지: %4</span><span class="sxs-lookup"><span data-stu-id="361b3-391">Version: %1, status: %2, error code: %3, message: %4</span></span></td>
   <td><span data-ttu-id="361b3-392">클라우드 서비스에서 무시된 잘못된 구성 파일을 수신했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-392">Received an invalid configuration file from the cloud service that was ignored.</span></span></td>
   <td><span data-ttu-id="361b3-393">이 오류가 계속되면 지원에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-393">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="361b3-394">50</span><span class="sxs-lookup"><span data-stu-id="361b3-394">50</span></span></td>
   <td><span data-ttu-id="361b3-395">새 클라우드 구성이 성공적으로 적용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-395">New cloud configuration applied successfully.</span></span> <span data-ttu-id="361b3-396">버전: %1.</span><span class="sxs-lookup"><span data-stu-id="361b3-396">Version: %1.</span></span></td>
   <td><span data-ttu-id="361b3-397">클라우드 서비스에서 새 구성을 적용했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-397">Successfully applied a new configuration from the cloud service.</span></span></td>
   <td><span data-ttu-id="361b3-398">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-398">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="361b3-399">51</span><span class="sxs-lookup"><span data-stu-id="361b3-399">51</span></span></td>
   <td><span data-ttu-id="361b3-400">새 클라우드 구성을 적용하지 못했습니다. 버전: %1.</span><span class="sxs-lookup"><span data-stu-id="361b3-400">New cloud configuration failed to apply, version: %1.</span></span> <span data-ttu-id="361b3-401">마지막으로 알려진 양호한 구성 버전 %2을(를) 적용했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-401">Successfully applied the last known good configuration, version %2.</span></span></td>
   <td><span data-ttu-id="361b3-402">클라우드 서비스에서 잘못된 구성 파일을 수신했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-402">Received a bad configuration file from the cloud service.</span></span> <span data-ttu-id="361b3-403">마지막으로 알려진 양호한 구성이 성공적으로 적용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-403">Last known good configuration was applied successfully.</span></span></td>
   <td><span data-ttu-id="361b3-404">이 오류가 계속되면 지원에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-404">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="361b3-405">52</span><span class="sxs-lookup"><span data-stu-id="361b3-405">52</span></span></td>
   <td><span data-ttu-id="361b3-406">새 클라우드 구성을 적용하지 못했습니다. 버전: %1.</span><span class="sxs-lookup"><span data-stu-id="361b3-406">New cloud configuration failed to apply, version: %1.</span></span> <span data-ttu-id="361b3-407">또한 마지막으로 알려진 양호한 구성 버전 %2을(를) 적용하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-407">Also failed to apply last known good configuration, version %2.</span></span> <span data-ttu-id="361b3-408">기본 구성을 적용했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-408">Successfully applied the default configuration.</span></span></td>
   <td><span data-ttu-id="361b3-409">클라우드 서비스에서 잘못된 구성 파일을 수신했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-409">Received a bad configuration file from the cloud service.</span></span> <span data-ttu-id="361b3-410">마지막으로 알려진 양호한 구성을 적용하지 못했습니다. 기본 구성이 적용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-410">Failed to apply the last known good configuration - and the default configuration was applied.</span></span></td>
   <td><span data-ttu-id="361b3-411">서비스가 5분 이내에 새 구성 파일을 다운로드하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-411">The service will attempt to download a new configuration file within 5 minutes.</span></span> <span data-ttu-id="361b3-412">이벤트가 없는 경우 #50 - 지원에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-412">If you don't see event #50 - contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="361b3-413">53</span><span class="sxs-lookup"><span data-stu-id="361b3-413">53</span></span></td>
   <td><span data-ttu-id="361b3-414">영구 저장소, 버전: %1에서 로드된 클라우드 구성.</span><span class="sxs-lookup"><span data-stu-id="361b3-414">Cloud configuration loaded from persistent storage, version: %1.</span></span></td>
   <td><span data-ttu-id="361b3-415">구성이 서비스 시작 시 영구 저장소에서 로드되었습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-415">The configuration was loaded from persistent storage on service startup.</span></span></td>
   <td><span data-ttu-id="361b3-416">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-416">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="361b3-417">55</span><span class="sxs-lookup"><span data-stu-id="361b3-417">55</span></span></td>
   <td><span data-ttu-id="361b3-418">보안 ETW 자동 로거를 만들지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-418">Failed to create the Secure ETW autologger.</span></span> <span data-ttu-id="361b3-419">오류 코드: %1</span><span class="sxs-lookup"><span data-stu-id="361b3-419">Failure code: %1</span></span></td>
   <td><span data-ttu-id="361b3-420">보안 ETW 로거를 만들지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-420">Failed to create the secure ETW logger.</span></span></td>
   <td><span data-ttu-id="361b3-421">장치를 다시부팅합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-421">Reboot the device.</span></span> <span data-ttu-id="361b3-422">이 오류가 계속되면 지원에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-422">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="361b3-423">56</span><span class="sxs-lookup"><span data-stu-id="361b3-423">56</span></span></td>
   <td><span data-ttu-id="361b3-424">보안 ETW 자동 로거를 제거하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-424">Failed to remove the Secure ETW autologger.</span></span> <span data-ttu-id="361b3-425">오류 코드: %1</span><span class="sxs-lookup"><span data-stu-id="361b3-425">Failure code: %1</span></span></td>
   <td><span data-ttu-id="361b3-426">오프보더에서 보안 ETW 세션을 제거하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-426">Failed to remove the secure ETW session on offboarding.</span></span></td>
   <td><span data-ttu-id="361b3-427">고객 지원에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-427">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="361b3-428">57</span><span class="sxs-lookup"><span data-stu-id="361b3-428">57</span></span></td>
   <td><span data-ttu-id="361b3-429">문제 해결을 위해 컴퓨터의 스냅숏 캡처</span><span class="sxs-lookup"><span data-stu-id="361b3-429">Capturing a snapshot of the machine for troubleshooting purposes.</span></span></td>
   <td><span data-ttu-id="361b3-430">포렌식 패키지라고도 하는 조사 패키지가 수집되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-430">An investigation package, also known as forensics package, is being collected.</span></span></td>
   <td><span data-ttu-id="361b3-431">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-431">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="361b3-432">59</span><span class="sxs-lookup"><span data-stu-id="361b3-432">59</span></span></td>
   <td><span data-ttu-id="361b3-433">시작 명령: %1</span><span class="sxs-lookup"><span data-stu-id="361b3-433">Starting command: %1</span></span></td>
   <td><span data-ttu-id="361b3-434">응답 명령 실행 시작</span><span class="sxs-lookup"><span data-stu-id="361b3-434">Starting response command execution.</span></span></td>
   <td><span data-ttu-id="361b3-435">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-435">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="361b3-436">60</span><span class="sxs-lookup"><span data-stu-id="361b3-436">60</span></span></td>
   <td><span data-ttu-id="361b3-437">%1 명령을 실행하지 못했습니다. 오류: %2.</span><span class="sxs-lookup"><span data-stu-id="361b3-437">Failed to run command %1, error: %2.</span></span></td>
   <td><span data-ttu-id="361b3-438">응답 명령을 실행하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-438">Failed to execute response command.</span></span></td>
   <td><span data-ttu-id="361b3-439">이 오류가 계속되면 지원에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-439">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="361b3-440">61</span><span class="sxs-lookup"><span data-stu-id="361b3-440">61</span></span></td>
   <td><span data-ttu-id="361b3-441">데이터 수집 명령 매개 변수가 잘못되었습니다. SasUri: %1, compressionLevel: %2.</span><span class="sxs-lookup"><span data-stu-id="361b3-441">Data collection command parameters are invalid: SasUri: %1, compressionLevel: %2.</span></span></td>
   <td><span data-ttu-id="361b3-442">데이터 수집 명령 인수를 읽거나 구문 분석하지 못했습니다(잘못된 인수).</span><span class="sxs-lookup"><span data-stu-id="361b3-442">Failed to read or parse the data collection command arguments (invalid arguments).</span></span></td>
   <td><span data-ttu-id="361b3-443">이 오류가 계속되면 지원에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-443">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="361b3-444">62</span><span class="sxs-lookup"><span data-stu-id="361b3-444">62</span></span></td>
   <td><span data-ttu-id="361b3-445">연결된 사용자 환경 및 원격 분석 서비스를 시작하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-445">Failed to start Connected User Experiences and Telemetry service.</span></span> <span data-ttu-id="361b3-446">오류 코드: %1</span><span class="sxs-lookup"><span data-stu-id="361b3-446">Failure code: %1</span></span></td>
   <td><span data-ttu-id="361b3-447">연결된 사용자 환경 및 원격 분석(diagtrack) 서비스를 시작하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-447">Connected User Experiences and Telemetry (diagtrack) service failed to start.</span></span> <span data-ttu-id="361b3-448">끝점 원격 분석용 Microsoft Defender가 아닌 다른 원격 분석은 이 컴퓨터로부터 전송되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-448">Non-Microsoft Defender for Endpoint telemetry won't be sent from this machine.</span></span></td>
   <td><span data-ttu-id="361b3-449">이벤트 로그에서 Microsoft-Windows-UniversalTelemetryClient/Operational 문제 해결 힌트를 찾아 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-449">Look for more troubleshooting hints in the event log: Microsoft-Windows-UniversalTelemetryClient/Operational.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="361b3-450">63</span><span class="sxs-lookup"><span data-stu-id="361b3-450">63</span></span></td>
   <td><span data-ttu-id="361b3-451">외부 서비스의 시작 유형을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-451">Updating the start type of external service.</span></span> <span data-ttu-id="361b3-452">이름: %1, 실제 시작 유형: %2, 예상 시작 유형: %3, 종료 코드: %4</span><span class="sxs-lookup"><span data-stu-id="361b3-452">Name: %1, actual start type: %2, expected start type: %3, exit code: %4</span></span></td>
   <td><span data-ttu-id="361b3-453">외부 서비스의 시작 유형이 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-453">Updated start type of the external service.</span></span></td>
   <td><span data-ttu-id="361b3-454">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-454">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="361b3-455">64</span><span class="sxs-lookup"><span data-stu-id="361b3-455">64</span></span></td>
   <td><span data-ttu-id="361b3-456">중지된 외부 서비스 시작</span><span class="sxs-lookup"><span data-stu-id="361b3-456">Starting stopped external service.</span></span> <span data-ttu-id="361b3-457">이름: %1, 종료 코드: %2</span><span class="sxs-lookup"><span data-stu-id="361b3-457">Name: %1, exit code: %2</span></span></td>
   <td><span data-ttu-id="361b3-458">외부 서비스 시작</span><span class="sxs-lookup"><span data-stu-id="361b3-458">Starting an external service.</span></span></td>
   <td><span data-ttu-id="361b3-459">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-459">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="361b3-460">65</span><span class="sxs-lookup"><span data-stu-id="361b3-460">65</span></span></td>
   <td><span data-ttu-id="361b3-461">Microsoft 보안 이벤트 구성 요소 미니 필터 드라이버를 로드하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-461">Failed to load Microsoft Security Events Component Minifilter driver.</span></span> <span data-ttu-id="361b3-462">오류 코드: %1</span><span class="sxs-lookup"><span data-stu-id="361b3-462">Failure code: %1</span></span></td>
   <td><span data-ttu-id="361b3-463">파일 MsSecFlt.sys 로드하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-463">Failed to load MsSecFlt.sys filesystem minifilter.</span></span></td>
   <td><span data-ttu-id="361b3-464">장치를 다시부팅합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-464">Reboot the device.</span></span> <span data-ttu-id="361b3-465">이 오류가 계속되면 지원에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-465">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="361b3-466">66</span><span class="sxs-lookup"><span data-stu-id="361b3-466">66</span></span></td>
   <td><span data-ttu-id="361b3-467">정책 업데이트: 대기 시간 모드 - %1</span><span class="sxs-lookup"><span data-stu-id="361b3-467">Policy update: Latency mode - %1</span></span></td>
   <td><span data-ttu-id="361b3-468">C&C 연결 빈도 정책이 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-468">The C&C connection frequency policy was updated.</span></span></td>
   <td><span data-ttu-id="361b3-469">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-469">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="361b3-470">68</span><span class="sxs-lookup"><span data-stu-id="361b3-470">68</span></span></td>
   <td><span data-ttu-id="361b3-471">서비스의 시작 유형이 예기치 않습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-471">The start type of the service is unexpected.</span></span> <span data-ttu-id="361b3-472">서비스 이름: %1, 실제 시작 유형: %2, 예상 시작 유형: %3</span><span class="sxs-lookup"><span data-stu-id="361b3-472">Service name: %1, actual start type: %2, expected start type: %3</span></span></td>
   <td><span data-ttu-id="361b3-473">예기치 않은 외부 서비스 시작 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-473">Unexpected external service start type.</span></span></td>
   <td><span data-ttu-id="361b3-474">외부 서비스 시작 유형을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-474">Fix the external service start type.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="361b3-475">69</span><span class="sxs-lookup"><span data-stu-id="361b3-475">69</span></span></td>
   <td><span data-ttu-id="361b3-476">서비스가 중지되었습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-476">The service is stopped.</span></span> <span data-ttu-id="361b3-477">서비스 이름: %1</span><span class="sxs-lookup"><span data-stu-id="361b3-477">Service name: %1</span></span></td>
   <td><span data-ttu-id="361b3-478">외부 서비스가 중지되었습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-478">The external service is stopped.</span></span></td>
   <td><span data-ttu-id="361b3-479">외부 서비스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-479">Start the external service.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="361b3-480">70</span><span class="sxs-lookup"><span data-stu-id="361b3-480">70</span></span></td>
   <td><span data-ttu-id="361b3-481">정책 업데이트: 샘플 수집 허용 - %1</span><span class="sxs-lookup"><span data-stu-id="361b3-481">Policy update: Allow sample collection - %1</span></span></td>
   <td><span data-ttu-id="361b3-482">샘플 수집 정책이 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-482">The sample collection policy was updated.</span></span></td>
   <td><span data-ttu-id="361b3-483">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-483">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="361b3-484">71</span><span class="sxs-lookup"><span data-stu-id="361b3-484">71</span></span></td>
   <td><span data-ttu-id="361b3-485">명령 실행 성공: %1</span><span class="sxs-lookup"><span data-stu-id="361b3-485">Succeeded to run command: %1</span></span></td>
   <td><span data-ttu-id="361b3-486">명령이 성공적으로 실행된 경우</span><span class="sxs-lookup"><span data-stu-id="361b3-486">The command was executed successfully.</span></span></td>
   <td><span data-ttu-id="361b3-487">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-487">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="361b3-488">72</span><span class="sxs-lookup"><span data-stu-id="361b3-488">72</span></span></td>
   <td><span data-ttu-id="361b3-489">첫 번째 전체 컴퓨터 프로필 보고서를 보내려고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-489">Tried to send first full machine profile report.</span></span> <span data-ttu-id="361b3-490">결과 코드: %1</span><span class="sxs-lookup"><span data-stu-id="361b3-490">Result code: %1</span></span></td>
   <td><span data-ttu-id="361b3-491">정보 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-491">Informational only.</span></span></td>
   <td><span data-ttu-id="361b3-492">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-492">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="361b3-493">73</span><span class="sxs-lookup"><span data-stu-id="361b3-493">73</span></span></td>
   <td><span data-ttu-id="361b3-494">플랫폼 시작 센스: %1</span><span class="sxs-lookup"><span data-stu-id="361b3-494">Sense starting for platform: %1</span></span></td>
   <td><span data-ttu-id="361b3-495">정보 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-495">Informational only.</span></span></td>
   <td><span data-ttu-id="361b3-496">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-496">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="361b3-497">74</span><span class="sxs-lookup"><span data-stu-id="361b3-497">74</span></span></td>
   <td><span data-ttu-id="361b3-498">레지스트리의 장치 태그가 길이 제한을 초과합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-498">Device tag in registry exceeds length limit.</span></span> <span data-ttu-id="361b3-499">태그 이름: %2.</span><span class="sxs-lookup"><span data-stu-id="361b3-499">Tag name: %2.</span></span> <span data-ttu-id="361b3-500">길이 제한: %1.</span><span class="sxs-lookup"><span data-stu-id="361b3-500">Length limit: %1.</span></span></td>
   <td><span data-ttu-id="361b3-501">장치 태그가 길이 제한을 초과합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-501">The device tag exceeds the length limit.</span></span></td>
   <td><span data-ttu-id="361b3-502">더 짧은 장치 태그를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-502">Use a shorter device tag.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="361b3-503">81</span><span class="sxs-lookup"><span data-stu-id="361b3-503">81</span></span></td>
   <td><span data-ttu-id="361b3-504">Endpoint ETW autologger용 Microsoft Defender를 만들지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-504">Failed to create Microsoft Defender for Endpoint ETW autologger.</span></span> <span data-ttu-id="361b3-505">오류 코드: %1</span><span class="sxs-lookup"><span data-stu-id="361b3-505">Failure code: %1</span></span></td>
   <td><span data-ttu-id="361b3-506">ETW 세션을 만들지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-506">Failed to create the ETW session.</span></span></td>
   <td><span data-ttu-id="361b3-507">장치를 다시부팅합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-507">Reboot the device.</span></span> <span data-ttu-id="361b3-508">이 오류가 계속되면 지원에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-508">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="361b3-509">82</span><span class="sxs-lookup"><span data-stu-id="361b3-509">82</span></span></td>
   <td><span data-ttu-id="361b3-510">Endpoint ETW autologger용 Microsoft Defender를 제거하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-510">Failed to remove Microsoft Defender for Endpoint ETW autologger.</span></span> <span data-ttu-id="361b3-511">오류 코드: %1</span><span class="sxs-lookup"><span data-stu-id="361b3-511">Failure code: %1</span></span></td>
   <td><span data-ttu-id="361b3-512">ETW 세션을 삭제하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-512">Failed to delete the ETW session.</span></span></td>
   <td><span data-ttu-id="361b3-513">고객 지원에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-513">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="361b3-514">84</span><span class="sxs-lookup"><span data-stu-id="361b3-514">84</span></span></td>
   <td><span data-ttu-id="361b3-515">바이러스 Windows Defender 모드로 설정</span><span class="sxs-lookup"><span data-stu-id="361b3-515">Set Windows Defender Antivirus running mode.</span></span> <span data-ttu-id="361b3-516">수동 모드 강제: %1, 결과 코드: %2.</span><span class="sxs-lookup"><span data-stu-id="361b3-516">Force passive mode: %1, result code: %2.</span></span></td>
   <td><span data-ttu-id="361b3-517">Defender 실행 모드(활성 또는 수동)를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-517">Set defender running mode (active or passive).</span></span></td>
   <td><span data-ttu-id="361b3-518">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-518">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="361b3-519">85</span><span class="sxs-lookup"><span data-stu-id="361b3-519">85</span></span></td>
   <td><span data-ttu-id="361b3-520">끝점 실행을 위해 Microsoft Defender를 트리거하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-520">Failed to trigger Microsoft Defender for Endpoint executable.</span></span> <span data-ttu-id="361b3-521">오류 코드: %1</span><span class="sxs-lookup"><span data-stu-id="361b3-521">Failure code: %1</span></span></td>
   <td><span data-ttu-id="361b3-522">센스IR 실행을 실행하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-522">Starring SenseIR executable failed.</span></span></td>
   <td><span data-ttu-id="361b3-523">장치를 다시부팅합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-523">Reboot the device.</span></span> <span data-ttu-id="361b3-524">이 오류가 계속되면 지원에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-524">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="361b3-525">86</span><span class="sxs-lookup"><span data-stu-id="361b3-525">86</span></span></td>
   <td><span data-ttu-id="361b3-526">다시 시작해야 하는 외부 서비스가 중지되었습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-526">Starting again stopped external service that should be up.</span></span> <span data-ttu-id="361b3-527">이름: %1, 종료 코드: %2</span><span class="sxs-lookup"><span data-stu-id="361b3-527">Name: %1, exit code: %2</span></span></td>
   <td><span data-ttu-id="361b3-528">외부 서비스를 다시 시작하십시오.</span><span class="sxs-lookup"><span data-stu-id="361b3-528">Starting the external service again.</span></span></td>
   <td><span data-ttu-id="361b3-529">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-529">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="361b3-530">87</span><span class="sxs-lookup"><span data-stu-id="361b3-530">87</span></span></td>
   <td><span data-ttu-id="361b3-531">외부 서비스를 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-531">Cannot start the external service.</span></span> <span data-ttu-id="361b3-532">이름: %1</span><span class="sxs-lookup"><span data-stu-id="361b3-532">Name: %1</span></span></td>
   <td><span data-ttu-id="361b3-533">외부 서비스를 시작하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-533">Failed to start the external service.</span></span></td>
   <td><span data-ttu-id="361b3-534">고객 지원에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-534">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="361b3-535">88</span><span class="sxs-lookup"><span data-stu-id="361b3-535">88</span></span></td>
   <td><span data-ttu-id="361b3-536">외부 서비스의 시작 유형을 다시 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-536">Updating the start type of external service again.</span></span> <span data-ttu-id="361b3-537">이름: %1, 실제 시작 유형: %2, 예상 시작 유형: %3, 종료 코드: %4</span><span class="sxs-lookup"><span data-stu-id="361b3-537">Name: %1, actual start type: %2, expected start type: %3, exit code: %4</span></span></td>
   <td><span data-ttu-id="361b3-538">외부 서비스의 시작 유형을 업데이트했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-538">Updated the start type of the external service.</span></span></td>
   <td><span data-ttu-id="361b3-539">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-539">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="361b3-540">89</span><span class="sxs-lookup"><span data-stu-id="361b3-540">89</span></span></td>
   <td><span data-ttu-id="361b3-541">외부 서비스의 시작 유형을 업데이트할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-541">Cannot update the start type of external service.</span></span> <span data-ttu-id="361b3-542">이름: %1, 실제 시작 유형: %2, 예상 시작 유형: %3</span><span class="sxs-lookup"><span data-stu-id="361b3-542">Name: %1, actual start type: %2, expected start type: %3</span></span></td>
   <td><span data-ttu-id="361b3-543">외부 서비스의 시작 유형을 업데이트할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-543">Can't update the start type of the external service.</span></span></td>
   <td><span data-ttu-id="361b3-544">고객 지원에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-544">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="361b3-545">90</span><span class="sxs-lookup"><span data-stu-id="361b3-545">90</span></span></td>
   <td><span data-ttu-id="361b3-546">지리적 지역 %1의 클라우드 서비스에 연결하도록 System Guard 런타임 모니터를 구성하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-546">Failed to configure System Guard Runtime Monitor to connect to cloud service in geo-region %1.</span></span> <span data-ttu-id="361b3-547">오류 코드: %2</span><span class="sxs-lookup"><span data-stu-id="361b3-547">Failure code: %2</span></span></td>
   <td><span data-ttu-id="361b3-548">System Guard 런타임 모니터는 클라우드 서비스에 의거 데이터를 전송하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-548">System Guard Runtime Monitor won't send attestation data to the cloud service.</span></span></td>
   <td><span data-ttu-id="361b3-549">등록 경로에 대한 사용 권한을 검사합니다. "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span><span class="sxs-lookup"><span data-stu-id="361b3-549">Check the permissions on register path: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span></span> <span data-ttu-id="361b3-550">문제가 없는 경우 지원에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-550">If no issues spotted, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="361b3-551">91</span><span class="sxs-lookup"><span data-stu-id="361b3-551">91</span></span></td>
   <td><span data-ttu-id="361b3-552">System Guard 런타임 모니터 지리적 지역 정보를 제거하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-552">Failed to remove System Guard Runtime Monitor geo-region information.</span></span> <span data-ttu-id="361b3-553">오류 코드: %1</span><span class="sxs-lookup"><span data-stu-id="361b3-553">Failure code: %1</span></span></td>
   <td><span data-ttu-id="361b3-554">System Guard 런타임 모니터는 클라우드 서비스에 의거 데이터를 전송하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-554">System Guard Runtime Monitor won't send attestation data to the cloud service.</span></span></td>
   <td><span data-ttu-id="361b3-555">등록 경로에 대한 사용 권한을 검사합니다. "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span><span class="sxs-lookup"><span data-stu-id="361b3-555">Check the permissions on register path: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span></span> <span data-ttu-id="361b3-556">문제가 없는 경우 지원에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-556">If no issues spotted, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="361b3-557">92</span><span class="sxs-lookup"><span data-stu-id="361b3-557">92</span></span></td>
   <td><span data-ttu-id="361b3-558">데이터 할당량 초과로 센서 사이버 데이터 할당량 보내기 중지</span><span class="sxs-lookup"><span data-stu-id="361b3-558">Stopping sending sensor cyber data quota because data quota is exceeded.</span></span> <span data-ttu-id="361b3-559">할당량 기간이 지나면 보내기 다시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-559">Will resume sending once quota period passes.</span></span> <span data-ttu-id="361b3-560">상태 마스크: %1</span><span class="sxs-lookup"><span data-stu-id="361b3-560">State Mask: %1</span></span></td>
   <td><span data-ttu-id="361b3-561">제한 한도를 초과합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-561">Exceed throttling limit.</span></span></td>
   <td><span data-ttu-id="361b3-562">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-562">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="361b3-563">93</span><span class="sxs-lookup"><span data-stu-id="361b3-563">93</span></span></td>
   <td><span data-ttu-id="361b3-564">센서 사이버 데이터 보내기 다시.</span><span class="sxs-lookup"><span data-stu-id="361b3-564">Resuming sending sensor cyber data.</span></span> <span data-ttu-id="361b3-565">상태 마스크: %1</span><span class="sxs-lookup"><span data-stu-id="361b3-565">State Mask: %1</span></span></td>
   <td><span data-ttu-id="361b3-566">사이버 데이터 제출을 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-566">Resume cyber data submission.</span></span></td>
   <td><span data-ttu-id="361b3-567">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-567">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="361b3-568">94</span><span class="sxs-lookup"><span data-stu-id="361b3-568">94</span></span></td>
   <td><span data-ttu-id="361b3-569">끝점용 Microsoft Defender 실행이 시작된 경우</span><span class="sxs-lookup"><span data-stu-id="361b3-569">Microsoft Defender for Endpoint executable has started</span></span></td>
   <td><span data-ttu-id="361b3-570">SenseCE 실행이 시작된 경우</span><span class="sxs-lookup"><span data-stu-id="361b3-570">The SenseCE executable has started.</span></span></td>
   <td><span data-ttu-id="361b3-571">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-571">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="361b3-572">95</span><span class="sxs-lookup"><span data-stu-id="361b3-572">95</span></span></td>
   <td><span data-ttu-id="361b3-573">끝점용 Microsoft Defender 실행이 종료된 경우</span><span class="sxs-lookup"><span data-stu-id="361b3-573">Microsoft Defender for Endpoint executable has ended</span></span></td>
   <td><span data-ttu-id="361b3-574">SenseCE 실행이 끝났습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-574">The SenseCE executable has ended.</span></span></td>
   <td><span data-ttu-id="361b3-575">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-575">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="361b3-576">96</span><span class="sxs-lookup"><span data-stu-id="361b3-576">96</span></span></td>
   <td><span data-ttu-id="361b3-577">끝점용 Microsoft Defender Init이 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-577">Microsoft Defender for Endpoint Init has called.</span></span> <span data-ttu-id="361b3-578">결과 코드: %2</span><span class="sxs-lookup"><span data-stu-id="361b3-578">Result code: %2</span></span></td>
   <td><span data-ttu-id="361b3-579">SenseCE 실행을 MCE 초기화라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-579">The SenseCE executable has called MCE initialization.</span></span></td>
   <td><span data-ttu-id="361b3-580">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-580">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="361b3-581">97</span><span class="sxs-lookup"><span data-stu-id="361b3-581">97</span></span></td>
   <td><span data-ttu-id="361b3-582">DLP 시나리오를 위해 클라우드에 대한 연결 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-582">There are connectivity issues to the Cloud for the DLP scenario</span></span></td>
   <td><span data-ttu-id="361b3-583">DLP 분류 흐름에 영향을 주는 네트워크 연결 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-583">There are network connectivity issues that affect the DLP classification flow.</span></span></td>
   <td><span data-ttu-id="361b3-584">네트워크 연결을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-584">Check the network connectivity.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="361b3-585">98</span><span class="sxs-lookup"><span data-stu-id="361b3-585">98</span></span></td>
   <td><span data-ttu-id="361b3-586">DLP 시나리오를 위한 클라우드 연결이 복원되었습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-586">The connectivity to the Cloud for the DLP scenario has been restored</span></span></td>
   <td><span data-ttu-id="361b3-587">네트워크에 대한 연결이 복원되고 DLP 분류 흐름이 계속될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-587">The connectivity to the network was restored and the DLP classification flow can continue.</span></span></td>
   <td><span data-ttu-id="361b3-588">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-588">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="361b3-589">99</span><span class="sxs-lookup"><span data-stu-id="361b3-589">99</span></span></td>
   <td><span data-ttu-id="361b3-590">서버와 통신하는 동안 센스에서 다음 오류가 발생했습니다. (%1).</span><span class="sxs-lookup"><span data-stu-id="361b3-590">Sense has encountered the following error while communicating with server: (%1).</span></span> <span data-ttu-id="361b3-591">결과: (%2)</span><span class="sxs-lookup"><span data-stu-id="361b3-591">Result: (%2)</span></span></td>
   <td><span data-ttu-id="361b3-592">통신 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-592">A communication error occurred.</span></span></td>
   <td><span data-ttu-id="361b3-593">자세한 내용은 이벤트 로그에서 다음 이벤트를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="361b3-593">Check the following events in the event log for further details.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="361b3-594">100</span><span class="sxs-lookup"><span data-stu-id="361b3-594">100</span></span></td>
   <td><span data-ttu-id="361b3-595">끝점용 Microsoft Defender 실행을 시작하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-595">Microsoft Defender for Endpoint executable failed to start.</span></span> <span data-ttu-id="361b3-596">오류 코드: %1</span><span class="sxs-lookup"><span data-stu-id="361b3-596">Failure code: %1</span></span></td>
   <td><span data-ttu-id="361b3-597">SenseCE 실행을 시작하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-597">The SenseCE executable has failed to start.</span></span></td>
   <td><span data-ttu-id="361b3-598">장치를 다시부팅합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-598">Reboot the device.</span></span> <span data-ttu-id="361b3-599">이 오류가 계속되면 지원에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-599">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="361b3-600">102</span><span class="sxs-lookup"><span data-stu-id="361b3-600">102</span></span></td>
   <td><span data-ttu-id="361b3-601">끝점 네트워크 검색 및 응답 실행용 Microsoft Defender가 시작</span><span class="sxs-lookup"><span data-stu-id="361b3-601">Microsoft Defender for Endpoint Network Detection and Response executable has started</span></span></td>
   <td><span data-ttu-id="361b3-602">SenseNdr 실행이 시작된 경우</span><span class="sxs-lookup"><span data-stu-id="361b3-602">The SenseNdr executable has started.</span></span></td>
   <td><span data-ttu-id="361b3-603">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-603">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="361b3-604">103</span><span class="sxs-lookup"><span data-stu-id="361b3-604">103</span></span></td>
   <td><span data-ttu-id="361b3-605">끝점 네트워크 검색 및 응답 실행용 Microsoft Defender가 종료된 경우</span><span class="sxs-lookup"><span data-stu-id="361b3-605">Microsoft Defender for Endpoint Network Detection and Response executable has ended</span></span></td>
   <td><span data-ttu-id="361b3-606">SenseNdr 실행이 종료된 경우</span><span class="sxs-lookup"><span data-stu-id="361b3-606">The SenseNdr executable has ended.</span></span></td>
   <td><span data-ttu-id="361b3-607">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-607">Normal operating notification; no action required.</span></span></td>
</tr>
</tbody>
</table>

><span data-ttu-id="361b3-608">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="361b3-608">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="361b3-609">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="361b3-609">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-eventerrorcodes-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="361b3-610">관련 항목</span><span class="sxs-lookup"><span data-stu-id="361b3-610">Related topics</span></span>
- [<span data-ttu-id="361b3-611">그룹 정책을 통한 Windows 10 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="361b3-611">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="361b3-612">장치 프록시 및 인터넷 연결 설정 구성</span><span class="sxs-lookup"><span data-stu-id="361b3-612">Configure device proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="361b3-613">엔드포인트용 Microsoft Defender 문제 해결</span><span class="sxs-lookup"><span data-stu-id="361b3-613">Troubleshoot Microsoft Defender for Endpoint</span></span>](troubleshoot-onboarding.md)
