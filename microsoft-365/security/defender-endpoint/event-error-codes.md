---
title: 이벤트 뷰어를 사용하여 이벤트 및 오류 검토
description: Microsoft Defender for Endpoint Service에서 보고하는 모든 이벤트에 대한 설명 및 추가 문제 해결 단계(필요한 경우)를 얻습니다.
keywords: 문제 해결, 이벤트 뷰어, 로그 요약, 오류 코드, 실패, 끝점용 Microsoft Defender 서비스, 시작할 수 없습니다, 중단, 시작할 수 없습니다.
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
ms.openlocfilehash: 98c0f790c228989b261b95f3b87cdc9d18e4fa76
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076620"
---
# <a name="review-events-and-errors-using-event-viewer"></a><span data-ttu-id="3978c-104">이벤트 뷰어를 사용하여 이벤트 및 오류 검토</span><span class="sxs-lookup"><span data-stu-id="3978c-104">Review events and errors using Event Viewer</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="3978c-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="3978c-105">**Applies to:**</span></span>
- <span data-ttu-id="3978c-106">이벤트 뷰어</span><span class="sxs-lookup"><span data-stu-id="3978c-106">Event Viewer</span></span>
- [<span data-ttu-id="3978c-107">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3978c-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="3978c-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3978c-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="3978c-109">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="3978c-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3978c-110">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

<span data-ttu-id="3978c-111">개별 디바이스의 이벤트 뷰어에서 이벤트 [ID를](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-111">You can review event IDs in the [Event Viewer](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) on individual devices.</span></span>

<span data-ttu-id="3978c-112">예를 들어 장치가 장치 목록에 나타나지 않는 경우 장치에서 이벤트 ID를 찾아야 할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="3978c-112">For example, if devices are not appearing in the **Devices list**, you might need to look for event IDs on the devices.</span></span> <span data-ttu-id="3978c-113">그런 다음 이 표를 사용하여 추가 문제 해결 단계를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-113">You can then use this table to determine further troubleshooting steps.</span></span>

<span data-ttu-id="3978c-114">**이벤트 뷰어를 열고 끝점용 Microsoft Defender 서비스 이벤트 로그를 찾습니다.**</span><span class="sxs-lookup"><span data-stu-id="3978c-114">**Open Event Viewer and find the Microsoft Defender for Endpoint service event log:**</span></span>

1. <span data-ttu-id="3978c-115">Windows **메뉴에서** 시작을 클릭하고 이벤트 **뷰어를 입력한** 다음 **Enter를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3978c-115">Click **Start** on the Windows menu, type **Event Viewer**, and press **Enter**.</span></span>

2. <span data-ttu-id="3978c-116">로그 목록의 **로그** 요약에서 **Microsoft-Windows-SENSE/Operational이** 표시될 때까지 스크롤합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-116">In the log list, under **Log Summary**, scroll until you see **Microsoft-Windows-SENSE/Operational**.</span></span> <span data-ttu-id="3978c-117">항목을 두 번 클릭하여 로그를 니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-117">Double-click the item to open the log.</span></span>

   <span data-ttu-id="3978c-118">a.</span><span class="sxs-lookup"><span data-stu-id="3978c-118">a.</span></span>  <span data-ttu-id="3978c-119">응용 프로그램 및 서비스 로그   >  **Microsoft**  >  **Windows**  >  **SENSE를** 확장하고 작동을 클릭하여 로그에 액세스할 수도 **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="3978c-119">You can also access the log by expanding **Applications and Services Logs** > **Microsoft** > **Windows** > **SENSE** and click on **Operational**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3978c-120">SENSE는 끝점용 Microsoft Defender의 전원을 공급하는 동작 센서를 참조하는 데 사용되는 내부 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-120">SENSE is the internal name used to refer to the behavioral sensor that powers Microsoft Defender for Endpoint.</span></span>

3. <span data-ttu-id="3978c-121">서비스에서 기록한 이벤트가 로그에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-121">Events recorded by the service will appear in the log.</span></span> <span data-ttu-id="3978c-122">서비스에서 기록하는 이벤트 목록은 다음 표를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3978c-122">See the following table for a list of events recorded by the service.</span></span>

<table>
<tbody style="vertical-align:top;">
<tr>
<th><span data-ttu-id="3978c-123">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="3978c-123">Event ID</span></span></th>
<th><span data-ttu-id="3978c-124">메시지</span><span class="sxs-lookup"><span data-stu-id="3978c-124">Message</span></span></th>
<th><span data-ttu-id="3978c-125">설명</span><span class="sxs-lookup"><span data-stu-id="3978c-125">Description</span></span></th>
<th><span data-ttu-id="3978c-126">작업</span><span class="sxs-lookup"><span data-stu-id="3978c-126">Action</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="3978c-127">1</span><span class="sxs-lookup"><span data-stu-id="3978c-127">1</span></span></td>
<td><span data-ttu-id="3978c-128">끝점용 Microsoft Defender 서비스가 <code>variable</code> 시작되었습니다(버전).</span><span class="sxs-lookup"><span data-stu-id="3978c-128">Microsoft Defender for Endpoint service started (Version <code>variable</code>).</span></span></td>
<td><span data-ttu-id="3978c-129">시스템 시작, 종료 및 온보더링 중에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-129">Occurs during system start up, shut down, and during onbboarding.</span></span></td>
<td><span data-ttu-id="3978c-130">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-130">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3978c-131">2 </span><span class="sxs-lookup"><span data-stu-id="3978c-131">2</span></span></td>
<td><span data-ttu-id="3978c-132">끝점용 Microsoft Defender 서비스 종료.</span><span class="sxs-lookup"><span data-stu-id="3978c-132">Microsoft Defender for Endpoint service shutdown.</span></span></td>
<td><span data-ttu-id="3978c-133">디바이스가 종료되거나 오프보더될 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-133">Occurs when the device is shut down or offboarded.</span></span></td>
<td><span data-ttu-id="3978c-134">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-134">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3978c-135">3 </span><span class="sxs-lookup"><span data-stu-id="3978c-135">3</span></span></td>
<td><span data-ttu-id="3978c-136">끝점용 Microsoft Defender 서비스를 시작하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-136">Microsoft Defender for Endpoint service failed to start.</span></span> <span data-ttu-id="3978c-137">오류 코드: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="3978c-137">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="3978c-138">서비스가 시작되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-138">Service did not start.</span></span></td>
<td><span data-ttu-id="3978c-139">다른 메시지를 검토하여 가능한 원인 및 문제 해결 단계를 파악합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-139">Review other messages to determine possible cause and troubleshooting steps.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3978c-140">4 </span><span class="sxs-lookup"><span data-stu-id="3978c-140">4</span></span></td>
<td><span data-ttu-id="3978c-141">끝점용 Microsoft Defender 서비스가 에 서버에 <code>variable</code> 연결했습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-141">Microsoft Defender for Endpoint service contacted the server at <code>variable</code>.</span></span></td>
<td><span data-ttu-id="3978c-142">변수 = 끝점 처리 서버용 Defender의 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-142">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="3978c-143">이 URL은 방화벽 또는 네트워크 활동에 있는 URL과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-143">This URL will match that seen in the Firewall or network activity.</span></span></td>
<td><span data-ttu-id="3978c-144">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-144">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3978c-145">5 </span><span class="sxs-lookup"><span data-stu-id="3978c-145">5</span></span></td>
<td><span data-ttu-id="3978c-146">끝점용 Microsoft Defender 서비스가 의 서버에 연결하지 <code>variable</code> 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-146">Microsoft Defender for Endpoint service failed to connect to the server at <code>variable</code>.</span></span></td>
<td><span data-ttu-id="3978c-147">변수 = 끝점 처리 서버용 Defender의 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-147">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="3978c-148">서비스가 해당 URL의 외부 처리 서버에 연결하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-148">The service could not contact the external processing servers at that URL.</span></span></td>
<td><span data-ttu-id="3978c-149">URL에 대한 연결을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-149">Check the connection to the URL.</span></span> <span data-ttu-id="3978c-150">프록시 <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">및 인터넷 연결 구성을 참조합니다.</a></span><span class="sxs-lookup"><span data-stu-id="3978c-150">See <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3978c-151">6 </span><span class="sxs-lookup"><span data-stu-id="3978c-151">6</span></span></td>
<td><span data-ttu-id="3978c-152">Microsoft Defender for Endpoint Service가 온보딩되지 않은 경우 온보딩 매개 변수를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-152">Microsoft Defender for Endpoint service is not onboarded and no onboarding parameters were found.</span></span></td>
<td><span data-ttu-id="3978c-153">장치가 올바르게 온보드되지 않았고 포털에 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-153">The device did not onboard correctly and will not be reporting to the portal.</span></span></td>
<td><span data-ttu-id="3978c-154">서비스를 시작하기 전에 온보더링을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-154">Onboarding must be run before starting the service.</span></span><br>
<span data-ttu-id="3978c-155">온보딩 설정 및 스크립트가 제대로 배포되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-155">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="3978c-156">구성 패키지를 다시 재배포해 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-156">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="3978c-157"><a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Windows 10 장치 온보드를 참조합니다.</a></span><span class="sxs-lookup"><span data-stu-id="3978c-157">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3978c-158">7 </span><span class="sxs-lookup"><span data-stu-id="3978c-158">7</span></span></td>
<td><span data-ttu-id="3978c-159">Microsoft Defender for Endpoint Service에서 온보딩 매개 변수를 읽지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-159">Microsoft Defender for Endpoint service failed to read the onboarding parameters.</span></span> <span data-ttu-id="3978c-160">실패: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="3978c-160">Failure: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="3978c-161">변수 = 자세한 오류 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-161">Variable = detailed error description.</span></span> <span data-ttu-id="3978c-162">장치가 올바르게 온보드되지 않았고 포털에 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-162">The device did not onboard correctly and will not be reporting to the portal.</span></span></td>
<td><span data-ttu-id="3978c-163">온보딩 설정 및 스크립트가 제대로 배포되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-163">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="3978c-164">구성 패키지를 다시 재배포해 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-164">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="3978c-165"><a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Windows 10 장치 온보드를 참조합니다.</a></span><span class="sxs-lookup"><span data-stu-id="3978c-165">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3978c-166">8 </span><span class="sxs-lookup"><span data-stu-id="3978c-166">8</span></span></td>
<td><span data-ttu-id="3978c-167">Microsoft Defender for Endpoint Service에서 구성을 정리하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-167">Microsoft Defender for Endpoint service failed to clean its configuration.</span></span> <span data-ttu-id="3978c-168">오류 코드: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="3978c-168">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="3978c-169"><b>온보드 중:</b> 서비스가 온보더링하는 동안 구성을 정리하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-169"><b>During onboarding:</b> The service failed to clean its configuration during the onboarding.</span></span> <span data-ttu-id="3978c-170">온보더링 프로세스가 계속됩니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-170">The onboarding process continues.</span></span> <br><br> <span data-ttu-id="3978c-171"><b>오프보더 중:</b> 서비스가 오프보더하는 동안 구성을 정리하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-171"><b>During offboarding:</b> The service failed to clean its configuration during the offboarding.</span></span> <span data-ttu-id="3978c-172">오프보더 프로세스가 완료 했지만 서비스가 계속 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-172">The offboarding process finished but the service keeps running.</span></span>
 </td>
<td><span data-ttu-id="3978c-173"><b>온보더링:</b> 필요한 작업은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-173"><b>Onboarding:</b> No action required.</span></span> <br><br> <span data-ttu-id="3978c-174"><b>오프보더링:</b> 시스템을 다시 부트합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-174"><b>Offboarding:</b> Reboot the system.</span></span><br>
<span data-ttu-id="3978c-175"><a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Windows 10 장치 온보드를 참조합니다.</a></span><span class="sxs-lookup"><span data-stu-id="3978c-175">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3978c-176">9 </span><span class="sxs-lookup"><span data-stu-id="3978c-176">9</span></span></td>
<td><span data-ttu-id="3978c-177">끝점용 Microsoft Defender 서비스가 시작 유형을 변경하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-177">Microsoft Defender for Endpoint service failed to change its start type.</span></span> <span data-ttu-id="3978c-178">오류 코드: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="3978c-178">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="3978c-179"><b>온보드 중:</b> 장치가 올바르게 온보드되지 않았고 포털에 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-179"><b>During onboarding:</b> The device did not onboard correctly and will not be reporting to the portal.</span></span> <br><br><span data-ttu-id="3978c-180"><b>오프보더 중:</b> 서비스 시작 유형을 변경하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-180"><b>During offboarding:</b> Failed to change the service start type.</span></span> <span data-ttu-id="3978c-181">오프보더 프로세스가 계속됩니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-181">The offboarding process continues.</span></span> </td>
<td><span data-ttu-id="3978c-182">온보딩 설정 및 스크립트가 제대로 배포되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-182">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="3978c-183">구성 패키지를 다시 재배포해 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-183">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="3978c-184"><a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Windows 10 장치 온보드를 참조합니다.</a></span><span class="sxs-lookup"><span data-stu-id="3978c-184">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3978c-185">10  </span><span class="sxs-lookup"><span data-stu-id="3978c-185">10</span></span></td>
<td><span data-ttu-id="3978c-186">Microsoft Defender for Endpoint Service에서 온보딩 정보를 유지하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-186">Microsoft Defender for Endpoint service failed to persist the onboarding information.</span></span> <span data-ttu-id="3978c-187">오류 코드: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="3978c-187">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="3978c-188">장치가 올바르게 온보드되지 않았고 포털에 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-188">The device did not onboard correctly and will not be reporting to the portal.</span></span></td>
<td><span data-ttu-id="3978c-189">온보딩 설정 및 스크립트가 제대로 배포되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-189">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="3978c-190">구성 패키지를 다시 재배포해 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-190">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="3978c-191"><a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Windows 10 장치 온보드를 참조합니다.</a></span><span class="sxs-lookup"><span data-stu-id="3978c-191">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3978c-192">11 </span><span class="sxs-lookup"><span data-stu-id="3978c-192">11</span></span></td>
<td><span data-ttu-id="3978c-193">Endpoint Service용 Defender의 온보딩 또는 다시 온보딩이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-193">Onboarding or re-onboarding of Defender for Endpoint service completed.</span></span></td>
<td><span data-ttu-id="3978c-194">장치가 올바르게 온보드되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-194">The device onboarded correctly.</span></span></td>
<td><span data-ttu-id="3978c-195">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-195">Normal operating notification; no action required.</span></span><br>
<span data-ttu-id="3978c-196">디바이스가 포털에 표시될 때 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-196">It may take several hours for the device to appear in the portal.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3978c-197">12 </span><span class="sxs-lookup"><span data-stu-id="3978c-197">12</span></span></td>
<td><span data-ttu-id="3978c-198">끝점용 Microsoft Defender가 기본 구성을 적용하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-198">Microsoft Defender for Endpoint failed to apply the default configuration.</span></span></td>
<td><span data-ttu-id="3978c-199">서비스가 기본 구성을 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-199">Service was unable to apply the default configuration.</span></span></td>
<td><span data-ttu-id="3978c-200">이 오류는 잠시 후에 해결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-200">This error should resolve after a short period of time.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3978c-201">13</span><span class="sxs-lookup"><span data-stu-id="3978c-201">13</span></span></td>
<td><span data-ttu-id="3978c-202">끝점용 Microsoft Defender 장치 ID 계산: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="3978c-202">Microsoft Defender for Endpoint device ID calculated: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="3978c-203">정상적인 작동 프로세스.</span><span class="sxs-lookup"><span data-stu-id="3978c-203">Normal operating process.</span></span></td>
<td><span data-ttu-id="3978c-204">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-204">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3978c-205">15 </span><span class="sxs-lookup"><span data-stu-id="3978c-205">15</span></span></td>
<td><span data-ttu-id="3978c-206">끝점용 Microsoft Defender는 URL로 명령 채널을 시작할 수 없습니다. <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="3978c-206">Microsoft Defender for Endpoint cannot start command channel with URL: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="3978c-207">변수 = 끝점 처리 서버용 Defender의 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-207">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="3978c-208">서비스가 해당 URL의 외부 처리 서버에 연결하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-208">The service could not contact the external processing servers at that URL.</span></span></td>
<td><span data-ttu-id="3978c-209">URL에 대한 연결을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-209">Check the connection to the URL.</span></span> <span data-ttu-id="3978c-210">프록시 <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">및 인터넷 연결 구성을 참조합니다.</a></span><span class="sxs-lookup"><span data-stu-id="3978c-210">See <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3978c-211">17 </span><span class="sxs-lookup"><span data-stu-id="3978c-211">17</span></span></td>
<td><span data-ttu-id="3978c-212">끝점용 Microsoft Defender 서비스가 연결된 사용자 환경 및 원격 분석 서비스 위치를 변경하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-212">Microsoft Defender for Endpoint service failed to change the Connected User Experiences and Telemetry service location.</span></span> <span data-ttu-id="3978c-213">오류 코드: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="3978c-213">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="3978c-214">Windows 원격 분석 서비스에 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-214">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="3978c-215"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">진단 데이터 서비스가 사용하도록 설정되어 있는지 확인합니다.</a></span><span class="sxs-lookup"><span data-stu-id="3978c-215"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="3978c-216">온보딩 설정 및 스크립트가 제대로 배포되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-216">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="3978c-217">구성 패키지를 다시 재배포해 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-217">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="3978c-218"><a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Windows 10 장치 온보드를 참조합니다.</a></span><span class="sxs-lookup"><span data-stu-id="3978c-218">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3978c-219">18 </span><span class="sxs-lookup"><span data-stu-id="3978c-219">18</span></span></td>
<td><span data-ttu-id="3978c-220">OOBE(Windows 시작)가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-220">OOBE (Windows Welcome) is completed.</span></span></td>
<td><span data-ttu-id="3978c-221">Windows 업데이트 설치가 완료된 후에만 서비스가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-221">Service will only start after any Windows updates have finished installing.</span></span></td>
<td><span data-ttu-id="3978c-222">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-222">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3978c-223">19</span><span class="sxs-lookup"><span data-stu-id="3978c-223">19</span></span></td>
<td><span data-ttu-id="3978c-224">OOBE(Windows 시작)가 아직 완료되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-224">OOBE (Windows Welcome) has not yet completed.</span></span></td>
<td><span data-ttu-id="3978c-225">Windows 업데이트 설치가 완료된 후에만 서비스가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-225">Service will only start after any Windows updates have finished installing.</span></span></td>
<td><span data-ttu-id="3978c-226">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-226">Normal operating notification; no action required.</span></span><br>
<span data-ttu-id="3978c-227">시스템을 다시 시작한 후에도 이 오류가 지속되면 모든 Windows 업데이트가 전체 설치가 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-227">If this error persists after a system restart, ensure all Windows updates have full installed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3978c-228">20</span><span class="sxs-lookup"><span data-stu-id="3978c-228">20</span></span></td>
<td><span data-ttu-id="3978c-229">OOBE(Windows 시작)가 완료될 때까지 기다릴 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-229">Cannot wait for OOBE (Windows Welcome) to complete.</span></span> <span data-ttu-id="3978c-230">오류 코드: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="3978c-230">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="3978c-231">내부 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-231">Internal error.</span></span></td>
<td><span data-ttu-id="3978c-232">시스템을 다시 시작한 후에도 이 오류가 지속되면 모든 Windows 업데이트가 전체 설치가 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-232">If this error persists after a system restart, ensure all Windows updates have full installed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3978c-233">25</span><span class="sxs-lookup"><span data-stu-id="3978c-233">25</span></span></td>
<td><span data-ttu-id="3978c-234">Microsoft Defender for Endpoint Service가 레지스트리에서 상태를 다시 설정하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-234">Microsoft Defender for Endpoint service failed to reset health status in the registry.</span></span> <span data-ttu-id="3978c-235">오류 코드: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="3978c-235">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="3978c-236">장치가 올바르게 온보드되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-236">The device did not onboard correctly.</span></span>
<span data-ttu-id="3978c-237">포털에 보고됩니다. 그러나 서비스가 SCCM 또는 레지스트리에 등록된 것으로 나타나지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-237">It will report to the portal, however the service may not appear as registered in SCCM or the registry.</span></span></td>
<td><span data-ttu-id="3978c-238">온보딩 설정 및 스크립트가 제대로 배포되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-238">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="3978c-239">구성 패키지를 다시 재배포해 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-239">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="3978c-240"><a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Windows 10 장치 온보드를 참조합니다.</a></span><span class="sxs-lookup"><span data-stu-id="3978c-240">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3978c-241">26</span><span class="sxs-lookup"><span data-stu-id="3978c-241">26</span></span></td>
<td><span data-ttu-id="3978c-242">Microsoft Defender for Endpoint Service가 레지스트리에서 등록 상태를 설정하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-242">Microsoft Defender for Endpoint service failed to set the onboarding status in the registry.</span></span> <span data-ttu-id="3978c-243">오류 코드: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="3978c-243">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="3978c-244">장치가 올바르게 온보드되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-244">The device did not onboard correctly.</span></span><br>
<span data-ttu-id="3978c-245">포털에 보고됩니다. 그러나 서비스가 SCCM 또는 레지스트리에 등록된 것으로 나타나지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-245">It will report to the portal, however the service may not appear as registered in SCCM or the registry.</span></span></td>
<td><span data-ttu-id="3978c-246">온보딩 설정 및 스크립트가 제대로 배포되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-246">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="3978c-247">구성 패키지를 다시 재배포해 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-247">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="3978c-248"><a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Windows 10 장치 온보드를 참조합니다.</a></span><span class="sxs-lookup"><span data-stu-id="3978c-248">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3978c-249">27</span><span class="sxs-lookup"><span data-stu-id="3978c-249">27</span></span></td>
<td><span data-ttu-id="3978c-250">Microsoft Defender for Endpoint Service가 Microsoft Defender 바이러스 백신에서 SENSE 인식 모드를 사용하도록 설정하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-250">Microsoft Defender for Endpoint service failed to enable SENSE aware mode in Microsoft Defender Antivirus.</span></span> <span data-ttu-id="3978c-251">온보더링 프로세스가 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-251">Onboarding process failed.</span></span> <span data-ttu-id="3978c-252">오류 코드: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="3978c-252">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="3978c-253">일반적으로 다른 실시간 맬웨어 방지 제품이 장치에서 제대로 실행되고 장치가 Endpoint용 Defender에 보고하는 경우 Microsoft Defender 바이러스 백신은 특별한 수동 상태가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-253">Normally, Microsoft Defender Antivirus will enter a special passive state if another real-time antimalware product is running properly on the device, and the device is reporting to Defender for Endpoint.</span></span></td>
<td><span data-ttu-id="3978c-254">온보딩 설정 및 스크립트가 제대로 배포되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-254">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="3978c-255">구성 패키지를 다시 재배포해 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-255">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="3978c-256"><a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Windows 10 장치 온보드를 참조합니다.</a></span><span class="sxs-lookup"><span data-stu-id="3978c-256">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span><br>
<span data-ttu-id="3978c-257">실시간 맬웨어 방지 보호가 제대로 실행되고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-257">Ensure real-time antimalware protection is running properly.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3978c-258">28</span><span class="sxs-lookup"><span data-stu-id="3978c-258">28</span></span></td>
<td><span data-ttu-id="3978c-259">Endpoint용 Microsoft Defender 연결된 사용자 환경 및 원격 분석 서비스 등록에 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-259">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration failed.</span></span> <span data-ttu-id="3978c-260">오류 코드: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="3978c-260">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="3978c-261">Windows 원격 분석 서비스에 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-261">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="3978c-262"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">진단 데이터 서비스가 사용하도록 설정되어 있는지 확인합니다.</a></span><span class="sxs-lookup"><span data-stu-id="3978c-262"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="3978c-263">온보딩 설정 및 스크립트가 제대로 배포되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-263">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="3978c-264">구성 패키지를 다시 재배포해 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-264">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="3978c-265"><a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Windows 10 장치 온보드를 참조합니다.</a></span><span class="sxs-lookup"><span data-stu-id="3978c-265">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3978c-266">29</span><span class="sxs-lookup"><span data-stu-id="3978c-266">29</span></span></td>
<td><span data-ttu-id="3978c-267">오프보더 매개 변수를 읽지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-267">Failed to read the offboarding parameters.</span></span> <span data-ttu-id="3978c-268">오류 유형: %1, 오류 코드: %2, 설명: %3</span><span class="sxs-lookup"><span data-stu-id="3978c-268">Error type: %1, Error code: %2, Description: %3</span></span> </td>
<td><span data-ttu-id="3978c-269">이 이벤트는 시스템에서 오프보더 매개 변수를&#39;수 있는 경우 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-269">This event occurs when the system can&#39;t read the offboarding parameters.</span></span></td>
<td><span data-ttu-id="3978c-270">장치에 인터넷 액세스 권한이 있는지 확인한 다음 전체 오프보더 프로세스를 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-270">Ensure the device has Internet access, then run the entire offboarding process again.</span></span> <span data-ttu-id="3978c-271">오프보더 패키지가 만료되지 않은지 확인</span><span class="sxs-lookup"><span data-stu-id="3978c-271">Ensure the offboarding package has not expired.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3978c-272">30</span><span class="sxs-lookup"><span data-stu-id="3978c-272">30</span></span></td>
<td><span data-ttu-id="3978c-273">Microsoft Defender for Endpoint Service가 Microsoft Defender 바이러스 백신에서 SENSE 인식 모드를 사용하지 않도록 설정하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-273">Microsoft Defender for Endpoint service failed to disable SENSE aware mode in Microsoft Defender Antivirus.</span></span> <span data-ttu-id="3978c-274">오류 코드: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="3978c-274">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="3978c-275">일반적으로 다른 실시간 맬웨어 방지 제품이 장치에서 제대로 실행되고 장치가 Endpoint용 Defender에 보고하는 경우 Microsoft Defender 바이러스 백신은 특별한 수동 상태가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-275">Normally, Microsoft Defender Antivirus will enter a special passive state if another real-time antimalware product is running properly on the device, and the device is reporting to Defender for Endpoint.</span></span></td>
<td><span data-ttu-id="3978c-276">온보딩 설정 및 스크립트가 제대로 배포되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-276">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="3978c-277">구성 패키지를 다시 재배포해 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-277">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="3978c-278"><a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Windows 10 장치 온보드 참조</a></span><span class="sxs-lookup"><span data-stu-id="3978c-278">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a></span></span><br>
<span data-ttu-id="3978c-279">실시간 맬웨어 방지 보호가 제대로 실행되고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-279">Ensure real-time antimalware protection is running properly.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3978c-280">31</span><span class="sxs-lookup"><span data-stu-id="3978c-280">31</span></span></td>
<td><span data-ttu-id="3978c-281">Endpoint용 Microsoft Defender 연결된 사용자 환경 및 원격 분석 서비스 등록이 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-281">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service unregistration failed.</span></span> <span data-ttu-id="3978c-282">오류 코드: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="3978c-282">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="3978c-283">온보더링하는 동안 Windows 원격 분석 서비스에 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-283">An error occurred with the Windows telemetry service during onboarding.</span></span> <span data-ttu-id="3978c-284">오프보더 프로세스가 계속됩니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-284">The offboarding process continues.</span></span></td>
<td><span data-ttu-id="3978c-285">Windows 원격 분석 서비스 에서 <a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">오류를 검사합니다.</a></span><span class="sxs-lookup"><span data-stu-id="3978c-285"><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">Check for errors with the Windows telemetry service</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3978c-286">32</span><span class="sxs-lookup"><span data-stu-id="3978c-286">32</span></span></td>
<td><span data-ttu-id="3978c-287">Microsoft Defender for Endpoint Service가 오프보딩 프로세스 후 자체 중지를 요청하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-287">Microsoft Defender for Endpoint service failed to request to stop itself after offboarding process.</span></span> <span data-ttu-id="3978c-288">오류 코드: %1</span><span class="sxs-lookup"><span data-stu-id="3978c-288">Failure code: %1</span></span></td>
<td><span data-ttu-id="3978c-289">오프보더하는 동안 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-289">An error occurred during offboarding.</span></span></td>
<td><span data-ttu-id="3978c-290">장치를 다시부팅합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-290">Reboot the device.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3978c-291">33</span><span class="sxs-lookup"><span data-stu-id="3978c-291">33</span></span></td>
<td><span data-ttu-id="3978c-292">Microsoft Defender for Endpoint Service에서 SENSE GUID를 유지하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-292">Microsoft Defender for Endpoint service failed to persist SENSE GUID.</span></span> <span data-ttu-id="3978c-293">오류 코드: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="3978c-293">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="3978c-294">고유 식별자는 포털에 보고되는 각 장치를 나타내는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-294">A unique identifier is used to represent each device that is reporting to the portal.</span></span><br>
<span data-ttu-id="3978c-295">식별자가 유지되지 않는 경우 동일한 장치가 포털에 두 번 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-295">If the identifier does not persist, the same device might appear twice in the portal.</span></span></td>
<td><span data-ttu-id="3978c-296">장치에서 레지스트리 권한을 확인하여 서비스가 레지스트리를 업데이트할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-296">Check registry permissions on the device to ensure the service can update the registry.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3978c-297">34</span><span class="sxs-lookup"><span data-stu-id="3978c-297">34</span></span></td>
<td><span data-ttu-id="3978c-298">끝점용 Microsoft Defender 서비스가 연결된 사용자 환경 및 원격 분석 서비스에 대한 종속성으로 추가하지 못하여 온보딩 프로세스가 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-298">Microsoft Defender for Endpoint service failed to add itself as a dependency on the Connected User Experiences and Telemetry service, causing onboarding process to fail.</span></span> <span data-ttu-id="3978c-299">오류 코드: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="3978c-299">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="3978c-300">Windows 원격 분석 서비스에 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-300">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="3978c-301"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">진단 데이터 서비스가 사용하도록 설정되어 있는지 확인합니다.</a></span><span class="sxs-lookup"><span data-stu-id="3978c-301"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="3978c-302">온보딩 설정 및 스크립트가 제대로 배포되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-302">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="3978c-303">구성 패키지를 다시 재배포해 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-303">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="3978c-304"><a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Windows 10 장치 온보드를 참조합니다.</a></span><span class="sxs-lookup"><span data-stu-id="3978c-304">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3978c-305">35</span><span class="sxs-lookup"><span data-stu-id="3978c-305">35</span></span></td>
<td><span data-ttu-id="3978c-306">Microsoft Defender for Endpoint Service가 연결된 사용자 환경 및 원격 분석 서비스에 대한 종속성으로 자체적으로 제거하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-306">Microsoft Defender for Endpoint service failed to remove itself as a dependency on the Connected User Experiences and Telemetry service.</span></span> <span data-ttu-id="3978c-307">오류 코드: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="3978c-307">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="3978c-308">오프보더 중 Windows 원격 분석 서비스에 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-308">An error occurred with the Windows telemetry service during offboarding.</span></span> <span data-ttu-id="3978c-309">오프보더 프로세스가 계속됩니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-309">The offboarding process continues.</span></span>
</td>
<td><span data-ttu-id="3978c-310">Windows 진단 데이터 서비스에서 오류를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-310">Check for errors with the Windows diagnostic data service.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3978c-311">36</span><span class="sxs-lookup"><span data-stu-id="3978c-311">36</span></span></td>
<td><span data-ttu-id="3978c-312">끝점용 Microsoft Defender 연결된 사용자 환경 및 원격 분석 서비스 등록이 성공했습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-312">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration succeeded.</span></span> <span data-ttu-id="3978c-313">완료 코드: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="3978c-313">Completion code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="3978c-314">연결된 사용자 환경 및 원격 분석 서비스에 끝점에 대한 Defender 등록이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-314">Registering Defender for Endpoint with the Connected User Experiences and Telemetry service completed successfully.</span></span></td>
<td><span data-ttu-id="3978c-315">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-315">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3978c-316">37</span><span class="sxs-lookup"><span data-stu-id="3978c-316">37</span></span></td>
<td><span data-ttu-id="3978c-317">끝점용 Microsoft Defender A 모듈이 할당량 초과됩니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-317">Microsoft Defender for Endpoint A module is about to exceed its quota.</span></span> <span data-ttu-id="3978c-318">모듈: %1, 할당량: {%2} {%3}, 할당량 사용률: %4.</span><span class="sxs-lookup"><span data-stu-id="3978c-318">Module: %1, Quota: {%2} {%3}, Percentage of quota utilization: %4.</span></span></td>
<td><span data-ttu-id="3978c-319">장치는 현재 24시간 창의 할당량에 거의 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-319">The device has almost used its allocated quota of the current 24-hour window.</span></span> <span data-ttu-id="3978c-320">이제는 스로틀이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-320">It’s about to be throttled.</span></span></td>
<td><span data-ttu-id="3978c-321">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-321">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3978c-322">38</span><span class="sxs-lookup"><span data-stu-id="3978c-322">38</span></span></td>
<td><span data-ttu-id="3978c-323">네트워크 연결은 낮음으로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-323">Network connection is identified as low.</span></span> <span data-ttu-id="3978c-324">끝점용 Microsoft Defender는 %1분마다 서버에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-324">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="3978c-325">데이터 통신 연결: %2, 인터넷 사용 가능: %3, 무료 네트워크 사용 가능: %4.</span><span class="sxs-lookup"><span data-stu-id="3978c-325">Metered connection: %2, internet available: %3, free network available: %4.</span></span></td>
<td><span data-ttu-id="3978c-326">장치가 데이터 통신/유료 네트워크를 사용하고 있으며 서버에 자주 연결하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-326">The device is using a metered/paid network and will be contacting the server less frequently.</span></span></td>
<td><span data-ttu-id="3978c-327">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-327">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3978c-328">39</span><span class="sxs-lookup"><span data-stu-id="3978c-328">39</span></span></td>
<td><span data-ttu-id="3978c-329">네트워크 연결은 정상으로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-329">Network connection is identified as normal.</span></span> <span data-ttu-id="3978c-330">끝점용 Microsoft Defender는 %1분마다 서버에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-330">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="3978c-331">데이터 통신 연결: %2, 인터넷 사용 가능: %3, 무료 네트워크 사용 가능: %4.</span><span class="sxs-lookup"><span data-stu-id="3978c-331">Metered connection: %2, internet available: %3, free network available: %4.</span></span></td>
<td><span data-ttu-id="3978c-332">장치가 데이터 데이터 연결/유료 연결을 사용하지 않는 경우 평소처럼 서버에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-332">The device is not using a metered/paid connection and will contact the server as usual.</span></span></td>
<td><span data-ttu-id="3978c-333">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-333">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3978c-334">40</span><span class="sxs-lookup"><span data-stu-id="3978c-334">40</span></span></td>
<td><span data-ttu-id="3978c-335">배터리 상태는 낮음으로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-335">Battery state is identified as low.</span></span> <span data-ttu-id="3978c-336">끝점용 Microsoft Defender는 %1분마다 서버에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-336">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="3978c-337">배터리 상태: %2.</span><span class="sxs-lookup"><span data-stu-id="3978c-337">Battery state: %2.</span></span></td>
<td><span data-ttu-id="3978c-338">디바이스의 배터리 잔량이 낮고 서버에 자주 연결하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-338">The device has low battery level and will contact the server less frequently.</span></span></td>
<td><span data-ttu-id="3978c-339">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-339">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3978c-340">41</span><span class="sxs-lookup"><span data-stu-id="3978c-340">41</span></span></td>
<td><span data-ttu-id="3978c-341">배터리 상태는 정상으로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-341">Battery state is identified as normal.</span></span> <span data-ttu-id="3978c-342">끝점용 Microsoft Defender는 %1분마다 서버에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-342">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="3978c-343">배터리 상태: %2.</span><span class="sxs-lookup"><span data-stu-id="3978c-343">Battery state: %2.</span></span></td>
<td><span data-ttu-id="3978c-344">디바이스의 배터리 수준이 낮지 않은 경우 평소처럼 서버에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-344">The device doesn’t have low battery level and will contact the server as usual.</span></span></td>
<td><span data-ttu-id="3978c-345">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-345">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3978c-346">42</span><span class="sxs-lookup"><span data-stu-id="3978c-346">42</span></span></td>
<td><span data-ttu-id="3978c-347">끝점용 Microsoft Defender WDATP 구성 요소가 작업을 수행하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-347">Microsoft Defender for Endpoint WDATP component failed to perform action.</span></span> <span data-ttu-id="3978c-348">구성 요소: %1, 작업: %2, 예외 유형: %3, 예외 메시지: %4</span><span class="sxs-lookup"><span data-stu-id="3978c-348">Component: %1, Action: %2, Exception Type: %3, Exception message: %4</span></span></td>
<td><span data-ttu-id="3978c-349">내부 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-349">Internal error.</span></span> <span data-ttu-id="3978c-350">서비스를 시작하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-350">The service failed to start.</span></span></td>
<td><span data-ttu-id="3978c-351">이 오류가 계속되면 지원에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-351">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3978c-352">43</span><span class="sxs-lookup"><span data-stu-id="3978c-352">43</span></span></td>
<td><span data-ttu-id="3978c-353">끝점용 Microsoft Defender WDATP 구성 요소가 작업을 수행하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-353">Microsoft Defender for Endpoint WDATP component failed to perform action.</span></span> <span data-ttu-id="3978c-354">구성 요소: %1, 작업: %2, 예외 유형: %3, 예외 오류: %4, 예외 메시지: %5</span><span class="sxs-lookup"><span data-stu-id="3978c-354">Component: %1, Action: %2, Exception Type: %3, Exception Error: %4, Exception message: %5</span></span></td>
<td><span data-ttu-id="3978c-355">내부 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-355">Internal error.</span></span> <span data-ttu-id="3978c-356">서비스를 시작하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-356">The service failed to start.</span></span></td>
<td><span data-ttu-id="3978c-357">이 오류가 계속되면 지원에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-357">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3978c-358">44</span><span class="sxs-lookup"><span data-stu-id="3978c-358">44</span></span></td>
<td><span data-ttu-id="3978c-359">끝점 서비스에 대한 Defender의 오프보딩이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-359">Offboarding of Defender for Endpoint service completed.</span></span></td>
<td><span data-ttu-id="3978c-360">서비스가 오프보더된 경우</span><span class="sxs-lookup"><span data-stu-id="3978c-360">The service was offboarded.</span></span></td>
<td><span data-ttu-id="3978c-361">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-361">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3978c-362">45</span><span class="sxs-lookup"><span data-stu-id="3978c-362">45</span></span></td>
<td><span data-ttu-id="3978c-363">이벤트 추적 세션 [%1]을(를) 등록하고 시작하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-363">Failed to register and to start the event trace session [%1].</span></span> <span data-ttu-id="3978c-364">오류 코드: %2</span><span class="sxs-lookup"><span data-stu-id="3978c-364">Error code: %2</span></span></td>
<td><span data-ttu-id="3978c-365">ETW 세션을 만드는 동안 서비스 시작 시 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-365">An error occurred on service startup while creating ETW session.</span></span> <span data-ttu-id="3978c-366">이로 인해 서비스 시작 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-366">This caused service start-up failure.</span></span></td>
<td><span data-ttu-id="3978c-367">이 오류가 계속되면 지원에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-367">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3978c-368">46</span><span class="sxs-lookup"><span data-stu-id="3978c-368">46</span></span></td>
<td><span data-ttu-id="3978c-369">리소스 부족으로 인해 이벤트 추적 세션 [%1]을(를) 등록하고 시작하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-369">Failed to register and start the event trace session [%1] due to lack of resources.</span></span> <span data-ttu-id="3978c-370">오류 코드: %2.</span><span class="sxs-lookup"><span data-stu-id="3978c-370">Error code: %2.</span></span> <span data-ttu-id="3978c-371">활성 이벤트 추적 세션이 너무 많기 때문에 이 가능성이 많을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-371">This is most likely because there are too many active event trace sessions.</span></span> <span data-ttu-id="3978c-372">서비스가 1분 후 다시 시도됩니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-372">The service will retry in 1 minute.</span></span></td>
<td><span data-ttu-id="3978c-373">리소스 부족으로 인해 ETW 세션을 만드는 동안 서비스 시작 시 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-373">An error occurred on service startup while creating ETW session due to lack of resources.</span></span> <span data-ttu-id="3978c-374">서비스가 시작되고 실행 중이지만 ETW 세션이 시작될 때까지 센서 이벤트를 보고하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-374">The service started and is running, but will not report any sensor event until the ETW session is started.</span></span></td>
<td><span data-ttu-id="3978c-375">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-375">Normal operating notification; no action required.</span></span> <span data-ttu-id="3978c-376">서비스가 1분마다 세션을 시작하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-376">The service will try to start the session every minute.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3978c-377">47</span><span class="sxs-lookup"><span data-stu-id="3978c-377">47</span></span></td>
<td><span data-ttu-id="3978c-378">이벤트 추적 세션을 등록하고 시작했습니다. 이전 시도가 실패한 후에 복구됩니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-378">Successfully registered and started the event trace session - recovered after previous failed attempts.</span></span></td>
<td><span data-ttu-id="3978c-379">이 이벤트는 ETW 세션을 성공적으로 시작한 후 이전 이벤트를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-379">This event follows the previous event after successfully starting of the ETW session.</span></span></td>
<td><span data-ttu-id="3978c-380">정상 작동 알림 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-380">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3978c-381">48</span><span class="sxs-lookup"><span data-stu-id="3978c-381">48</span></span></td>
<td><span data-ttu-id="3978c-382">이벤트 추적 세션 [%2]에 공급자 [%1]을(를) 추가하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-382">Failed to add a provider [%1] to event trace session [%2].</span></span> <span data-ttu-id="3978c-383">오류 코드: %3.</span><span class="sxs-lookup"><span data-stu-id="3978c-383">Error code: %3.</span></span> <span data-ttu-id="3978c-384">즉, 이 공급자의 이벤트가 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-384">This means that events from this provider will not be reported.</span></span></td>
<td><span data-ttu-id="3978c-385">ETW 세션에 공급자를 추가하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-385">Failed to add a provider to ETW session.</span></span> <span data-ttu-id="3978c-386">따라서 공급자 이벤트가 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-386">As a result, the provider events aren’t reported.</span></span></td>
<td><span data-ttu-id="3978c-387">오류 코드를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-387">Check the error code.</span></span> <span data-ttu-id="3978c-388">오류가 계속되면 고객 지원에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-388">If the error persists contact Support.</span></span></td>
</tr>
</tr>
</tbody>
</table>

><span data-ttu-id="3978c-389">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="3978c-389">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3978c-390">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="3978c-390">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-eventerrorcodes-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="3978c-391">관련 항목</span><span class="sxs-lookup"><span data-stu-id="3978c-391">Related topics</span></span>
- [<span data-ttu-id="3978c-392">Windows 10 장치 온보드</span><span class="sxs-lookup"><span data-stu-id="3978c-392">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="3978c-393">장치 프록시 및 인터넷 연결 설정 구성</span><span class="sxs-lookup"><span data-stu-id="3978c-393">Configure device proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="3978c-394">끝점용 Microsoft Defender 문제 해결</span><span class="sxs-lookup"><span data-stu-id="3978c-394">Troubleshoot Microsoft Defender for Endpoint</span></span>](troubleshoot-onboarding.md)
