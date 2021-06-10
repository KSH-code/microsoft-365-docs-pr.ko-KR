---
title: Microsoft Defender AV 이벤트 ID 및 오류 코드
description: 이벤트 MICROSOFT DEFENDER 바이러스 백신 오류의 원인 및 해결 방법 찾아 보기
keywords: 이벤트, 오류 코드, siem, 로깅, 문제 해결, wef, Windows 이벤트 전달
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/11/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: cd222760f3a5cc005c679bf28365237cc70e8950
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275351"
---
# <a name="review-event-logs-and-error-codes-to-troubleshoot-issues-with-microsoft-defender-antivirus"></a><span data-ttu-id="c9697-104">이벤트 로그 및 오류 코드를 검토하여 Microsoft Defender 바이러스 백신 문제 해결</span><span class="sxs-lookup"><span data-stu-id="c9697-104">Review event logs and error codes to troubleshoot issues with Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="c9697-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="c9697-105">**Applies to:**</span></span>

- [<span data-ttu-id="c9697-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="c9697-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="c9697-107">이 항목에 문제가 Microsoft Defender 바이러스 백신 이 항목의 표를 검색하여 일치하는 문제 및 잠재적인 해결 방법을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-107">If you encounter a problem with Microsoft Defender Antivirus, you can search the tables in this topic to find a matching issue and potential solution.</span></span>

<span data-ttu-id="c9697-108">표 목록에는 다음이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-108">The tables list:</span></span>

- <span data-ttu-id="c9697-109">[Microsoft Defender 바이러스 백신 이벤트 ID(Windows 10](#windows-defender-av-ids) 및 Windows Server 2016)</span><span class="sxs-lookup"><span data-stu-id="c9697-109">[Microsoft Defender Antivirus event IDs](#windows-defender-av-ids) (these apply to both Windows 10 and Windows Server 2016)</span></span>
- [<span data-ttu-id="c9697-110">Microsoft Defender 바이러스 백신 오류 코드</span><span class="sxs-lookup"><span data-stu-id="c9697-110">Microsoft Defender Antivirus client error codes</span></span>](#error-codes)
- [<span data-ttu-id="c9697-111">내부 Microsoft Defender 바이러스 백신 클라이언트 오류 코드(개발 및 테스트 중에 Microsoft에서 사용)</span><span class="sxs-lookup"><span data-stu-id="c9697-111">Internal Microsoft Defender Antivirus client error codes (used by Microsoft during development and testing)</span></span>](#internal-error-codes)

> [!TIP]
> <span data-ttu-id="c9697-112">Microsoft Defender for Endpoint 데모 웹 [사이트를](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 방문하여 demo.wd.microsoft.com 작동을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-112">You can also visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following features are working:</span></span>
> 
> - <span data-ttu-id="c9697-113">클라우드 제공 보호</span><span class="sxs-lookup"><span data-stu-id="c9697-113">Cloud-delivered protection</span></span>
> - <span data-ttu-id="c9697-114">빠른 학습(신속한 차단 포함)</span><span class="sxs-lookup"><span data-stu-id="c9697-114">Fast learning (including Block at first sight)</span></span>
> - <span data-ttu-id="c9697-115">잠재적으로 원치 않는 응용 프로그램 차단</span><span class="sxs-lookup"><span data-stu-id="c9697-115">Potentially unwanted application blocking</span></span>

<a id="windows-defender-av-ids"></a>
## <a name="microsoft-defender-antivirus-event-ids"></a><span data-ttu-id="c9697-116">Microsoft Defender 바이러스 백신 이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="c9697-116">Microsoft Defender Antivirus event IDs</span></span>

<span data-ttu-id="c9697-117">Microsoft Defender 바이러스 백신 로그에 이벤트 WINDOWS 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-117">Microsoft Defender Antivirus records event IDs in the Windows event log.</span></span>

<span data-ttu-id="c9697-118">이벤트 로그를 직접 보거나 타사 SIEM(보안 정보 및 이벤트 관리) 도구가 있는 [](troubleshoot-microsoft-defender-antivirus.md#windows-defender-av-ids) 경우 Microsoft Defender 바이러스 백신 클라이언트 이벤트 MICROSOFT DEFENDER 바이러스 백신 끝점에서 특정 이벤트 및 오류를 검토할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-118">You can directly view the event log, or if you have a third-party security information and event management (SIEM) tool, you can also consume [Microsoft Defender Antivirus client event IDs](troubleshoot-microsoft-defender-antivirus.md#windows-defender-av-ids) to review specific events and errors from your endpoints.</span></span>

<span data-ttu-id="c9697-119">이 섹션의 표에는 기본 Microsoft Defender 바이러스 백신 이벤트 MICROSOFT DEFENDER 바이러스 백신 나열되어 있으며 가능한 경우 오류를 수정하거나 해결하기 위한 권장 해결 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-119">The table in this section lists the main Microsoft Defender Antivirus event IDs and, where possible, provides suggested solutions to fix or resolve the error.</span></span> 

## <a name="to-view-a-microsoft-defender-antivirus-event"></a><span data-ttu-id="c9697-120">이벤트 Microsoft Defender 바이러스 백신 보기</span><span class="sxs-lookup"><span data-stu-id="c9697-120">To view a Microsoft Defender Antivirus event</span></span>

1.  <span data-ttu-id="c9697-121">이벤트 **뷰어 를 열 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="c9697-121">Open **Event Viewer**.</span></span>
2.  <span data-ttu-id="c9697-122">콘솔 트리에서 **응용** 프로그램 및 서비스 **로그,** **Microsoft** 를 확장한 다음 를 Windows **를** Windows Defender.</span><span class="sxs-lookup"><span data-stu-id="c9697-122">In the console tree, expand **Applications and Services Logs**, then **Microsoft**, then **Windows**, then **Windows Defender**.</span></span>
3.  <span data-ttu-id="c9697-123">작동 을 두 **번 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c9697-123">Double-click on **Operational**.</span></span>
4.  <span data-ttu-id="c9697-124">세부 정보 창에서 개별 이벤트 목록을 보고 이벤트를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-124">In the details pane, view the list of individual events to find your event.</span></span>
5.  <span data-ttu-id="c9697-125">이벤트를 클릭하여 아래쪽 창의 일반 및 세부 정보 탭에서  이벤트에 대한 특정 세부 **정보를** 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-125">Click the event to see specific details about an event in the lower pane, under the **General** and **Details** tabs.</span></span>

<table> 
<tr>
<th colspan="2" ><span data-ttu-id="c9697-126">이벤트 ID: 1000</span><span class="sxs-lookup"><span data-stu-id="c9697-126">Event ID: 1000</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-127">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-127">Symbolic name:</span></span>
</td>
<td><span data-ttu-id="c9697-128">
<b>MALWAREPROTECTION_SCAN_STARTED</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-128">
<b>MALWAREPROTECTION_SCAN_STARTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-129">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-129">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-130">
<b>맬웨어 방지 검사가 시작된 경우 </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-130">
<b>An antimalware scan started. </b>
</span></span></td>
</tr>
<tr>
<td >
<span data-ttu-id="c9697-131">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-131">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="c9697-132">
<dt>검사 ID: &lt; 관련 검사의 ID &gt; 번호입니다.</dt> 
<dt> 검사 유형: &lt; 검사 &gt; 유형, 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-132">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="c9697-133">바이러스 검사</span><span class="sxs-lookup"><span data-stu-id="c9697-133">Antivirus</span></span></li>
<li><span data-ttu-id="c9697-134">스파이웨어 방지</span><span class="sxs-lookup"><span data-stu-id="c9697-134">Antispyware</span></span></li>
<li><span data-ttu-id="c9697-135">맬웨어 방지</span><span class="sxs-lookup"><span data-stu-id="c9697-135">Antimalware</span></span></li>
</ul><span data-ttu-id="c9697-136">
</dt>
<dt>검사 매개 변수: &lt; 검사 매개 &gt; 변수, 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-136">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="c9697-137">전체 검사</span><span class="sxs-lookup"><span data-stu-id="c9697-137">Full scan</span></span></li>
<li><span data-ttu-id="c9697-138">빠른 검사</span><span class="sxs-lookup"><span data-stu-id="c9697-138">Quick scan</span></span></li>
<li><span data-ttu-id="c9697-139">고객 검사</span><span class="sxs-lookup"><span data-stu-id="c9697-139">Customer scan</span></span></li>
</ul><span data-ttu-id="c9697-140">
</dt>
<dt>리소스 검사: &lt; 검사된 리소스(예: 파일/directories/BHO)입니다. &gt; </dt> 
<dt>사용자: &lt; 도메인 &gt; \& lt; 사용자 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="c9697-140">
</dt>
<dt>Scan Resources: &lt;Resources (such as files/directories/BHO) that were scanned.&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-141">이벤트 ID: 1001</span><span class="sxs-lookup"><span data-stu-id="c9697-141">Event ID: 1001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-142">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-142">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-143">
<b>MALWAREPROTECTION_SCAN_COMPLETED</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-143">
<b>MALWAREPROTECTION_SCAN_COMPLETED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-144">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-144">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-145">
<b>맬웨어 방지 검사가 완료된 경우</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-145">
<b>An antimalware scan finished.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-146">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-146">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="c9697-147">
<dt>검사 ID: &lt; 관련 검사의 ID &gt; 번호입니다.</dt> 
<dt> 검사 유형: &lt; 검사 &gt; 유형, 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-147">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="c9697-148">바이러스 검사</span><span class="sxs-lookup"><span data-stu-id="c9697-148">Antivirus</span></span></li>
<li><span data-ttu-id="c9697-149">스파이웨어 방지</span><span class="sxs-lookup"><span data-stu-id="c9697-149">Antispyware</span></span></li>
<li><span data-ttu-id="c9697-150">맬웨어 방지</span><span class="sxs-lookup"><span data-stu-id="c9697-150">Antimalware</span></span></li>
</ul><span data-ttu-id="c9697-151">
</dt>
<dt>검사 매개 변수: &lt; 검사 매개 &gt; 변수, 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-151">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="c9697-152">전체 검사</span><span class="sxs-lookup"><span data-stu-id="c9697-152">Full scan</span></span></li>
<li><span data-ttu-id="c9697-153">빠른 검사</span><span class="sxs-lookup"><span data-stu-id="c9697-153">Quick scan</span></span></li>
<li><span data-ttu-id="c9697-154">고객 검사</span><span class="sxs-lookup"><span data-stu-id="c9697-154">Customer scan</span></span></li>
</ul><span data-ttu-id="c9697-155">
</dt>
<dt>사용자: &lt; 도메인 &gt; \& lt; 사용자 &gt; </dt>
<dt>검사 시간: &lt; 검사 &gt; 기간입니다.</dt>
</span><span class="sxs-lookup"><span data-stu-id="c9697-155">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Scan Time: &lt;The duration of a scan.&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-156">이벤트 ID: 1002</span><span class="sxs-lookup"><span data-stu-id="c9697-156">Event ID: 1002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-157">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-157">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-158">
<b>MALWAREPROTECTION_SCAN_CANCELLED </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-158">
<b>MALWAREPROTECTION_SCAN_CANCELLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-159">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-159">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-160">
<b>맬웨어 방지 검사가 완료되기 전에 중지되었습니다. </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-160">
<b>An antimalware scan was stopped before it finished. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-161">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-161">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="c9697-162">
<dt>검사 ID: &lt; 관련 검사의 ID &gt; 번호입니다.</dt> 
<dt> 검사 유형: &lt; 검사 &gt; 유형, 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-162">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="c9697-163">바이러스 검사</span><span class="sxs-lookup"><span data-stu-id="c9697-163">Antivirus</span></span></li>
<li><span data-ttu-id="c9697-164">스파이웨어 방지</span><span class="sxs-lookup"><span data-stu-id="c9697-164">Antispyware</span></span></li>
<li><span data-ttu-id="c9697-165">맬웨어 방지</span><span class="sxs-lookup"><span data-stu-id="c9697-165">Antimalware</span></span></li>
</ul><span data-ttu-id="c9697-166">
</dt>
<dt>검사 매개 변수: &lt; 검사 매개 &gt; 변수, 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-166">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="c9697-167">전체 검사</span><span class="sxs-lookup"><span data-stu-id="c9697-167">Full scan</span></span></li>
<li><span data-ttu-id="c9697-168">빠른 검사</span><span class="sxs-lookup"><span data-stu-id="c9697-168">Quick scan</span></span></li>
<li><span data-ttu-id="c9697-169">고객 검사</span><span class="sxs-lookup"><span data-stu-id="c9697-169">Customer scan</span></span></li>
</ul><span data-ttu-id="c9697-170">
</dt>
<dt>사용자: &lt; 도메인 &gt; &amp; lt; 사용자 &gt; </dt>
<dt>검사 시간: &lt; 검사 &gt; 기간입니다.</dt>
</span><span class="sxs-lookup"><span data-stu-id="c9697-170">
</dt>
<dt>User: &lt;Domain&gt;&amp;lt;User&gt;</dt>
<dt>Scan Time: &lt;The duration of a scan.&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-171">이벤트 ID: 1003</span><span class="sxs-lookup"><span data-stu-id="c9697-171">Event ID: 1003</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-172">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-172">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-173">
<b>MALWAREPROTECTION_SCAN_PAUSED </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-173">
<b>MALWAREPROTECTION_SCAN_PAUSED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-174">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-174">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-175">
<b>맬웨어 방지 검사가 일시 중지된 경우 </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-175">
<b>An antimalware scan was paused. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-176">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-176">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="c9697-177">
<dt>검사 ID: &lt; 관련 검사의 ID &gt; 번호입니다.</dt> 
<dt> 검사 유형: &lt; 검사 &gt; 유형, 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-177">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="c9697-178">바이러스 검사</span><span class="sxs-lookup"><span data-stu-id="c9697-178">Antivirus</span></span></li>
<li><span data-ttu-id="c9697-179">스파이웨어 방지</span><span class="sxs-lookup"><span data-stu-id="c9697-179">Antispyware</span></span></li>
<li><span data-ttu-id="c9697-180">맬웨어 방지</span><span class="sxs-lookup"><span data-stu-id="c9697-180">Antimalware</span></span></li>
</ul><span data-ttu-id="c9697-181">
</dt>
<dt>검사 매개 변수: &lt; 검사 매개 &gt; 변수, 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-181">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="c9697-182">전체 검사</span><span class="sxs-lookup"><span data-stu-id="c9697-182">Full scan</span></span></li>
<li><span data-ttu-id="c9697-183">빠른 검사</span><span class="sxs-lookup"><span data-stu-id="c9697-183">Quick scan</span></span></li>
<li><span data-ttu-id="c9697-184">고객 검사</span><span class="sxs-lookup"><span data-stu-id="c9697-184">Customer scan</span></span></li>
</ul><span data-ttu-id="c9697-185">
</dt>
<dt>사용자: &lt; 도메인 &gt; \& lt; 사용자&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="c9697-185">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-186">이벤트 ID: 1004</span><span class="sxs-lookup"><span data-stu-id="c9697-186">Event ID: 1004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-187">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-187">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-188">
<b>MALWAREPROTECTION_SCAN_RESUMED </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-188">
<b>MALWAREPROTECTION_SCAN_RESUMED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-189">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-189">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-190">
<b>맬웨어 방지 검사가 다시 시작된 경우 </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-190">
<b>An antimalware scan was resumed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-191">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-191">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="c9697-192">
<dt>검사 ID: &lt; 관련 검사의 ID &gt; 번호입니다.</dt> 
<dt> 검사 유형: &lt; 검사 &gt; 유형, 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-192">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="c9697-193">바이러스 검사</span><span class="sxs-lookup"><span data-stu-id="c9697-193">Antivirus</span></span></li>
<li><span data-ttu-id="c9697-194">스파이웨어 방지</span><span class="sxs-lookup"><span data-stu-id="c9697-194">Antispyware</span></span></li>
<li><span data-ttu-id="c9697-195">맬웨어 방지</span><span class="sxs-lookup"><span data-stu-id="c9697-195">Antimalware</span></span></li>
</ul><span data-ttu-id="c9697-196">
</dt>
<dt>검사 매개 변수: &lt; 검사 매개 &gt; 변수, 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-196">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="c9697-197">전체 검사</span><span class="sxs-lookup"><span data-stu-id="c9697-197">Full scan</span></span></li>
<li><span data-ttu-id="c9697-198">빠른 검사</span><span class="sxs-lookup"><span data-stu-id="c9697-198">Quick scan</span></span></li>
<li><span data-ttu-id="c9697-199">고객 검사</span><span class="sxs-lookup"><span data-stu-id="c9697-199">Customer scan</span></span></li>
</ul><span data-ttu-id="c9697-200">
</dt>
<dt>사용자: &lt; 도메인 &gt; \& lt; 사용자&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="c9697-200">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-201">이벤트 ID: 1005</span><span class="sxs-lookup"><span data-stu-id="c9697-201">Event ID: 1005</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-202">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-202">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-203">
<b>MALWAREPROTECTION_SCAN_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-203">
<b>MALWAREPROTECTION_SCAN_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-204">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-204">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-205">
<b>맬웨어 방지 검사가 실패했습니다. </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-205">
<b>An antimalware scan failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-206">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-206">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="c9697-207">
<dt>검사 ID: &lt; 관련 검사의 ID &gt; 번호입니다.</dt> 
<dt> 검사 유형: &lt; 검사 &gt; 유형, 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-207">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="c9697-208">바이러스 검사</span><span class="sxs-lookup"><span data-stu-id="c9697-208">Antivirus</span></span></li>
<li><span data-ttu-id="c9697-209">스파이웨어 방지</span><span class="sxs-lookup"><span data-stu-id="c9697-209">Antispyware</span></span></li>
<li><span data-ttu-id="c9697-210">맬웨어 방지</span><span class="sxs-lookup"><span data-stu-id="c9697-210">Antimalware</span></span></li>
</ul><span data-ttu-id="c9697-211">
</dt>
<dt>검사 매개 변수: &lt; 검사 매개 &gt; 변수, 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-211">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="c9697-212">전체 검사</span><span class="sxs-lookup"><span data-stu-id="c9697-212">Full scan</span></span></li>
<li><span data-ttu-id="c9697-213">빠른 검사</span><span class="sxs-lookup"><span data-stu-id="c9697-213">Quick scan</span></span></li>
<li><span data-ttu-id="c9697-214">고객 검사</span><span class="sxs-lookup"><span data-stu-id="c9697-214">Customer scan</span></span></li>
</ul><span data-ttu-id="c9697-215">
</dt>
<dt>사용자: &lt; 도메인 &gt; \& lt; 사용자 &gt; </dt>오류 코드: 오류 코드 위협
<dt> &lt; &gt; 상태와 관련된 결과 코드입니다. 표준 HRESULT 값입니다.</dt> 
<dt>오류 설명: &lt; 오류 설명 &gt; 오류에 대한 설명입니다.</dt>
</span><span class="sxs-lookup"><span data-stu-id="c9697-215">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-216">사용자 작업:</span><span class="sxs-lookup"><span data-stu-id="c9697-216">User action:</span></span>
</td>
<td >
<span data-ttu-id="c9697-217">바이러스 백신 클라이언트에서 오류가 발생하고 현재 검사가 중지되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-217">The antivirus client encountered an error, and the current scan has stopped.</span></span> <span data-ttu-id="c9697-218">클라이언트 쪽 문제로 인해 검사가 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-218">The scan might fail due to a client-side issue.</span></span> <span data-ttu-id="c9697-219">이 이벤트 레코드에는 검사 ID, 검사 유형(Microsoft Defender 바이러스 백신, 스파이웨어 방지, 맬웨어 방지), 검사 매개 변수, 검색을 시작한 사용자, 오류 코드 및 오류 설명이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-219">This event record includes the scan ID, type of scan (Microsoft Defender Antivirus, antispyware, antimalware), scan parameters, the user that started the scan, the error code, and a description of the error.</span></span>
<span data-ttu-id="c9697-220">이 이벤트를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-220">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="c9697-221">검색을 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-221">Run the scan again.</span></span></li>
<li><span data-ttu-id="c9697-222">같은 방식으로 오류가 발생하면 <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft</a>지원 사이트로 이동하여 검색 상자에 오류 번호를 입력하여 오류 코드를 찾아야 합니다. <b></b></span><span class="sxs-lookup"><span data-stu-id="c9697-222">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="c9697-223"><a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft 기술 지원</a>에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-223">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-224">이벤트 ID: 1006</span><span class="sxs-lookup"><span data-stu-id="c9697-224">Event ID: 1006</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-225">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-225">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-226">
<b>MALWAREPROTECTION_MALWARE_DETECTED </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-226">
<b>MALWAREPROTECTION_MALWARE_DETECTED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-227">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-227">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-228">
<b>맬웨어 방지 엔진이 맬웨어 또는 사용자 원치 않는 기타 소프트웨어를 발견했습니다. </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-228">
<b>The antimalware engine found malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-229">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-229">Description:</span></span>
</td>
<td >
<span data-ttu-id="c9697-230">자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c9697-230">For more information, see the following:</span></span>
<dl><span data-ttu-id="c9697-231">
<dt>이름: &lt; 위협 &gt; 이름</dt>
<dt>ID: &lt; 위협 &gt; ID</dt> 
<dt> 심각도: &lt; &gt; 심각도, 예:</span><span class="sxs-lookup"><span data-stu-id="c9697-231">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="c9697-232">낮음</span><span class="sxs-lookup"><span data-stu-id="c9697-232">Low</span></span></li>
<li><span data-ttu-id="c9697-233">보통</span><span class="sxs-lookup"><span data-stu-id="c9697-233">Moderate</span></span></li>
<li><span data-ttu-id="c9697-234">높음</span><span class="sxs-lookup"><span data-stu-id="c9697-234">High</span></span></li>
<li><span data-ttu-id="c9697-235">심각</span><span class="sxs-lookup"><span data-stu-id="c9697-235">Severe</span></span></li>
</ul><span data-ttu-id="c9697-236">
</dt>
<dt>범주: &lt; 범주 설명 &gt; 입니다(예: 위협 또는 맬웨어 유형).</dt> 
<dt>경로: &lt; 파일 &gt; 경로</dt> 
<dt> 검색 원본: &lt; 검색 원본 , 예를 들면 다음과 &gt; 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-236">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span><ul>
<li><span data-ttu-id="c9697-237">알 수 없음</span><span class="sxs-lookup"><span data-stu-id="c9697-237">Unknown</span></span></li>
<li><span data-ttu-id="c9697-238">로컬 컴퓨터</span><span class="sxs-lookup"><span data-stu-id="c9697-238">Local computer</span></span></li>
<li><span data-ttu-id="c9697-239">네트워크 공유</span><span class="sxs-lookup"><span data-stu-id="c9697-239">Network share</span></span></li>
<li><span data-ttu-id="c9697-240">인터넷</span><span class="sxs-lookup"><span data-stu-id="c9697-240">Internet</span></span></li>
<li><span data-ttu-id="c9697-241">들어오는 트래픽</span><span class="sxs-lookup"><span data-stu-id="c9697-241">Incoming traffic</span></span></li>
<li><span data-ttu-id="c9697-242">아웃보이스 트래픽</span><span class="sxs-lookup"><span data-stu-id="c9697-242">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="c9697-243">
</dt>
<dt>검색 유형: &lt; 검색 &gt; 유형, 예:</span><span class="sxs-lookup"><span data-stu-id="c9697-243">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="c9697-244">Heuristics</span><span class="sxs-lookup"><span data-stu-id="c9697-244">Heuristics</span></span></li>
<li><span data-ttu-id="c9697-245">일반</span><span class="sxs-lookup"><span data-stu-id="c9697-245">Generic</span></span></li>
<li><span data-ttu-id="c9697-246">구체적</span><span class="sxs-lookup"><span data-stu-id="c9697-246">Concrete</span></span></li>
<li><span data-ttu-id="c9697-247">동적 서명</span><span class="sxs-lookup"><span data-stu-id="c9697-247">Dynamic signature</span></span></li>
</ul><span data-ttu-id="c9697-248">
</dt>
<dt>검색 원본: &lt; 검색 &gt; 원본: 예:</span><span class="sxs-lookup"><span data-stu-id="c9697-248">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="c9697-249">사용자: 사용자가 시작한 경우</span><span class="sxs-lookup"><span data-stu-id="c9697-249">User: user initiated</span></span></li>
<li><span data-ttu-id="c9697-250">시스템: 시스템이 시작된 경우</span><span class="sxs-lookup"><span data-stu-id="c9697-250">System: system initiated</span></span></li>
<li><span data-ttu-id="c9697-251">실시간: 실시간 구성 요소가 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-251">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="c9697-252">IOAV: IE 다운로드 및 Outlook Express 첨부 파일 시작</span><span class="sxs-lookup"><span data-stu-id="c9697-252">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="c9697-253">NIS: 네트워크 검사 시스템</span><span class="sxs-lookup"><span data-stu-id="c9697-253">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="c9697-254">IEPROTECT: IE - IExtensionValidation; 이렇게 하여 악의적인 웹 페이지 컨트롤로부터 보호</span><span class="sxs-lookup"><span data-stu-id="c9697-254">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="c9697-255">ELAM(맬웨어 방지 조기 실행).</span><span class="sxs-lookup"><span data-stu-id="c9697-255">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="c9697-256">여기에는 부팅 시퀀스에서 검색된 맬웨어가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-256">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="c9697-257">원격 attestation</span><span class="sxs-lookup"><span data-stu-id="c9697-257">Remote attestation</span></span></li>
</ul><span data-ttu-id="c9697-258">AMSI(맬웨어 방지 검사 인터페이스).</span><span class="sxs-lookup"><span data-stu-id="c9697-258">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="c9697-259">제3자도 호출할 수 있는 스크립트(PS, VBS)를 보호하는 데 주로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-259">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="c9697-260">UAC </dt> 
<dt>상태: &lt; 상태 &gt; </dt>
<dt>사용자: &lt; 도메인 &gt; \& lt; 사용자 &gt; </dt>
<dt>프로세스 이름: &lt; PID &gt; </dt>서명 버전의
<dt>프로세스: &lt; &gt; </dt>정의 버전 엔진 버전: Antimalware Engine
<dt> &lt; 버전 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="c9697-260">UAC</dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-261">이벤트 ID: 1007</span><span class="sxs-lookup"><span data-stu-id="c9697-261">Event ID: 1007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-262">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-262">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-263">
<b>MALWAREPROTECTION_MALWARE_ACTION_TAKEN </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-263">
<b>MALWAREPROTECTION_MALWARE_ACTION_TAKEN </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-264">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-264">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-265">
<b>맬웨어 방지 플랫폼은 맬웨어 또는 사용자 원치 않는 기타 소프트웨어로부터 시스템을 보호하기 위한 작업을 수행했습니다. </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-265">
<b>The antimalware platform performed an action to protect your system from malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-266">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-266">Description:</span></span>
</td>
<td >
<span data-ttu-id="c9697-267">Microsoft Defender 바이러스 백신 맬웨어 또는 사용자 원치 않는 기타 소프트웨어로부터 이 머신을 보호하기 위해 작업을 수행했습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-267">Microsoft Defender Antivirus has taken action to protect this machine from malware or other potentially unwanted software.</span></span> <span data-ttu-id="c9697-268">자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c9697-268">For more information, see the following:</span></span>
<dl><span data-ttu-id="c9697-269">
<dt>사용자: &lt; 도메인 &gt; \& lt; 사용자 &gt; </dt>
<dt>이름: &lt; 위협 이름 &gt; </dt>
<dt>ID: 위협 &lt; ID &gt; </dt> 
<dt> 심각도: &lt; 심각도, &gt; 예:</span><span class="sxs-lookup"><span data-stu-id="c9697-269">
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="c9697-270">낮음</span><span class="sxs-lookup"><span data-stu-id="c9697-270">Low</span></span></li>
<li><span data-ttu-id="c9697-271">보통</span><span class="sxs-lookup"><span data-stu-id="c9697-271">Moderate</span></span></li>
<li><span data-ttu-id="c9697-272">높음</span><span class="sxs-lookup"><span data-stu-id="c9697-272">High</span></span></li>
<li><span data-ttu-id="c9697-273">심각</span><span class="sxs-lookup"><span data-stu-id="c9697-273">Severe</span></span></li>
</ul><span data-ttu-id="c9697-274">
</dt>
<dt>범주: &lt; 범주 설명 &gt; 입니다(예: 위협 또는 맬웨어 유형).</dt> 
<dt> 작업: &lt; &gt; 작업, 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-274">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="c9697-275">정리: 리소스가 정리된 경우</span><span class="sxs-lookup"><span data-stu-id="c9697-275">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="c9697-276">Quarantine: Resource was quarantined</span><span class="sxs-lookup"><span data-stu-id="c9697-276">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="c9697-277">제거: 리소스가 삭제되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-277">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="c9697-278">허용: 리소스가 실행/존재할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-278">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="c9697-279">사용자 정의: 사용자가 지정한 작업 목록에서 일반적으로 하나인 사용자 정의 작업</span><span class="sxs-lookup"><span data-stu-id="c9697-279">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="c9697-280">작업 없음: 아무 작업도 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-280">No action: No action</span></span></li>
<li><span data-ttu-id="c9697-281">차단: 리소스가 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-281">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="c9697-282">
</dt>
<dt>상태: &lt; 상태 &gt; </dt>
<dt>서명 버전: &lt; 정의 버전 &gt; </dt>엔진
<dt> &lt; 버전: &gt; </dt> Antimalware Engine 버전
</span><span class="sxs-lookup"><span data-stu-id="c9697-282">
</dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-283">이벤트 ID: 1008</span><span class="sxs-lookup"><span data-stu-id="c9697-283">Event ID: 1008</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-284">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-284">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-285">
<b>MALWAREPROTECTION_MALWARE_ACTION_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-285">
<b>MALWAREPROTECTION_MALWARE_ACTION_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-286">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-286">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-287">
<b>맬웨어 방지 플랫폼이 맬웨어 또는 사용자 원치 않는 기타 소프트웨어로부터 시스템을 보호하기 위한 작업을 수행하려고 했지만 작업이 실패했습니다.</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-287">
<b>The antimalware platform attempted to perform an action to protect your system from malware or other potentially unwanted software, but the action failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-288">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-288">Description:</span></span>
</td>
<td >
<span data-ttu-id="c9697-289">Microsoft Defender 바이러스 백신 또는 사용자 원치 않는 기타 소프트웨어에 대해 조치를 취할 때 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-289">Microsoft Defender Antivirus has encountered an error when taking action on malware or other potentially unwanted software.</span></span> <span data-ttu-id="c9697-290">자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c9697-290">For more information, see the following:</span></span>
<dl><span data-ttu-id="c9697-291">
<dt>사용자: &lt; 도메인 &gt; \& lt; 사용자 &gt; </dt>
<dt>이름: &lt; 위협 이름 &gt; </dt>
<dt>ID: 위협 &lt; ID &gt; </dt> 
<dt> 심각도: &lt; 심각도, &gt; 예:</span><span class="sxs-lookup"><span data-stu-id="c9697-291">
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="c9697-292">낮음</span><span class="sxs-lookup"><span data-stu-id="c9697-292">Low</span></span></li>
<li><span data-ttu-id="c9697-293">보통</span><span class="sxs-lookup"><span data-stu-id="c9697-293">Moderate</span></span></li>
<li><span data-ttu-id="c9697-294">높음</span><span class="sxs-lookup"><span data-stu-id="c9697-294">High</span></span></li>
<li><span data-ttu-id="c9697-295">심각</span><span class="sxs-lookup"><span data-stu-id="c9697-295">Severe</span></span></li>
</ul><span data-ttu-id="c9697-296">
</dt>
<dt>범주: &lt; 범주 설명 &gt; 입니다(예: 위협 또는 맬웨어 유형).</dt> 
<dt>경로: &lt; 파일 &gt; 경로</dt> 
<dt> 동작: &lt; 동작 , 예를 들면 &gt; 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-296">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="c9697-297">정리: 리소스가 정리된 경우</span><span class="sxs-lookup"><span data-stu-id="c9697-297">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="c9697-298">Quarantine: Resource was quarantined</span><span class="sxs-lookup"><span data-stu-id="c9697-298">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="c9697-299">제거: 리소스가 삭제되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-299">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="c9697-300">허용: 리소스가 실행/존재할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-300">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="c9697-301">사용자 정의: 사용자가 지정한 작업 목록에서 일반적으로 하나인 사용자 정의 작업</span><span class="sxs-lookup"><span data-stu-id="c9697-301">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="c9697-302">작업 없음: 아무 작업도 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-302">No action: No action</span></span></li>
<li><span data-ttu-id="c9697-303">차단: 리소스가 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-303">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="c9697-304">
</dt>
<dt>오류 코드: &lt; 오류 코드 &gt; 위협 상태와 관련된 결과 코드입니다. 표준 HRESULT 값입니다. </dt> 
<dt>오류 설명: &lt; 오류 설명 &gt; 오류에 대한 설명입니다.</dt> 
<dt>상태: &lt; 상태 &gt; </dt>
<dt>서명 버전: &lt; 정의 버전 &gt; </dt>엔진
<dt> &lt; 버전: &gt; </dt> Antimalware Engine 버전
</span><span class="sxs-lookup"><span data-stu-id="c9697-304">
</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values. </dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-305">이벤트 ID: 1009</span><span class="sxs-lookup"><span data-stu-id="c9697-305">Event ID: 1009</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-306">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-306">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-307">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-307">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-308">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-308">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-309">
<b>맬웨어 방지 플랫폼이 항목을 검지에서 복원했습니다. </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-309">
<b>The antimalware platform restored an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-310">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-310">Description:</span></span>
</td>
<td >
<span data-ttu-id="c9697-311">Microsoft Defender 바이러스 백신 항목을 복원했습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-311">Microsoft Defender Antivirus has restored an item from quarantine.</span></span> <span data-ttu-id="c9697-312">자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c9697-312">For more information, see the following:</span></span>
<dl><span data-ttu-id="c9697-313">
<dt>이름: &lt; 위협 &gt; 이름</dt>
<dt>ID: &lt; 위협 &gt; ID</dt> 
<dt> 심각도: &lt; &gt; 심각도, 예:</span><span class="sxs-lookup"><span data-stu-id="c9697-313">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="c9697-314">낮음</span><span class="sxs-lookup"><span data-stu-id="c9697-314">Low</span></span></li>
<li><span data-ttu-id="c9697-315">보통</span><span class="sxs-lookup"><span data-stu-id="c9697-315">Moderate</span></span></li>
<li><span data-ttu-id="c9697-316">높음</span><span class="sxs-lookup"><span data-stu-id="c9697-316">High</span></span></li>
<li><span data-ttu-id="c9697-317">심각</span><span class="sxs-lookup"><span data-stu-id="c9697-317">Severe</span></span></li>
</ul><span data-ttu-id="c9697-318">
</dt>
<dt>범주: &lt; 범주 설명 &gt; 입니다(예: 위협 또는 맬웨어 유형).</dt> 
<dt>경로: &lt; 파일 &gt; 경로</dt>
<dt>사용자: &lt; 도메인 &gt; \& lt; 사용자 &gt; </dt>
<dt>서명 버전: &lt; 정의 버전 &gt; </dt>엔진 버전: Antimalware Engine
<dt> &lt; 버전 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="c9697-318">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-319">이벤트 ID: 1010</span><span class="sxs-lookup"><span data-stu-id="c9697-319">Event ID: 1010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-320">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-320">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-321">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-321">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-322">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-322">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-323">
<b>맬웨어 방지 플랫폼에서 항목을 검지에서 복원할 수 없습니다. </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-323">
<b>The antimalware platform could not restore an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-324">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-324">Description:</span></span>
</td>
<td >
<span data-ttu-id="c9697-325">Microsoft Defender 바이러스 백신 항목을 복구하는 중 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-325">Microsoft Defender Antivirus has encountered an error trying to restore an item from quarantine.</span></span> <span data-ttu-id="c9697-326">자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c9697-326">For more information, see the following:</span></span>
<dl><span data-ttu-id="c9697-327">
<dt>이름: &lt; 위협 &gt; 이름</dt>
<dt>ID: &lt; 위협 &gt; ID</dt> 
<dt> 심각도: &lt; &gt; 심각도, 예:</span><span class="sxs-lookup"><span data-stu-id="c9697-327">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="c9697-328">낮음</span><span class="sxs-lookup"><span data-stu-id="c9697-328">Low</span></span></li>
<li><span data-ttu-id="c9697-329">보통</span><span class="sxs-lookup"><span data-stu-id="c9697-329">Moderate</span></span></li>
<li><span data-ttu-id="c9697-330">높음</span><span class="sxs-lookup"><span data-stu-id="c9697-330">High</span></span></li>
<li><span data-ttu-id="c9697-331">심각</span><span class="sxs-lookup"><span data-stu-id="c9697-331">Severe</span></span></li>
</ul><span data-ttu-id="c9697-332">
</dt>
<dt>범주: &lt; 범주 설명 &gt; 입니다(예: 위협 또는 맬웨어 유형).</dt> 
<dt>경로: &lt; 파일 &gt; 경로</dt>
<dt>사용자: &lt; 도메인 &gt; \& lt; 사용자 &gt; </dt>오류 코드: 오류 코드 위협
<dt> &lt; &gt; 상태와 관련된 결과 코드입니다. 표준 HRESULT 값입니다. </dt> 
<dt>오류 설명: &lt; 오류 설명 &gt; 오류에 대한 설명입니다.</dt> 
<dt>서명 버전: &lt; 정의 &gt; 버전</dt>
<dt>엔진 버전: Antimalware Engine &lt; 버전 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="c9697-332">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values. </dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-333">이벤트 ID: 1011</span><span class="sxs-lookup"><span data-stu-id="c9697-333">Event ID: 1011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-334">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-334">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-335">
<b>MALWAREPROTECTION_QUARANTINE_DELETE</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-335">
<b>MALWAREPROTECTION_QUARANTINE_DELETE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-336">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-336">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-337">
<b>맬웨어 방지 플랫폼에서 항목을 삭제했습니다. </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-337">
<b>The antimalware platform deleted an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-338">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-338">Description:</span></span>
</td>
<td >
<span data-ttu-id="c9697-339">Microsoft Defender 바이러스 백신 항목을 삭제했습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-339">Microsoft Defender Antivirus has deleted an item from quarantine.</span></span><br/><span data-ttu-id="c9697-340">자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c9697-340">For more information, see the following:</span></span>
<dl><span data-ttu-id="c9697-341">
<dt>이름: &lt; 위협 &gt; 이름</dt>
<dt>ID: &lt; 위협 &gt; ID</dt> 
<dt> 심각도: &lt; &gt; 심각도, 예:</span><span class="sxs-lookup"><span data-stu-id="c9697-341">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="c9697-342">낮음</span><span class="sxs-lookup"><span data-stu-id="c9697-342">Low</span></span></li>
<li><span data-ttu-id="c9697-343">보통</span><span class="sxs-lookup"><span data-stu-id="c9697-343">Moderate</span></span></li>
<li><span data-ttu-id="c9697-344">높음</span><span class="sxs-lookup"><span data-stu-id="c9697-344">High</span></span></li>
<li><span data-ttu-id="c9697-345">심각</span><span class="sxs-lookup"><span data-stu-id="c9697-345">Severe</span></span></li>
</ul><span data-ttu-id="c9697-346">
</dt>
<dt>범주: &lt; 범주 설명 &gt; 입니다(예: 위협 또는 맬웨어 유형).</dt> 
<dt>경로: &lt; 파일 &gt; 경로</dt>
<dt>사용자: &lt; 도메인 &gt; \& lt; 사용자 &gt; </dt>
<dt>서명 버전: &lt; 정의 버전 &gt; </dt>엔진 버전: Antimalware Engine
<dt> &lt; 버전 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="c9697-346">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-347">이벤트 ID: 1012</span><span class="sxs-lookup"><span data-stu-id="c9697-347">Event ID: 1012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-348">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-348">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-349">
<b>MALWAREPROTECTION_QUARANTINE_DELETE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-349">
<b>MALWAREPROTECTION_QUARANTINE_DELETE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-350">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-350">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-351">
<b>맬웨어 방지 플랫폼에서 항목을 검지에서 삭제할 수 없습니다.</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-351">
<b>The antimalware platform could not delete an item from quarantine.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-352">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-352">Description:</span></span>
</td>
<td >
<span data-ttu-id="c9697-353">Microsoft Defender 바이러스 백신 항목을 삭제하는 중 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-353">Microsoft Defender Antivirus has encountered an error trying to delete an item from quarantine.</span></span>
<span data-ttu-id="c9697-354">자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c9697-354">For more information, see the following:</span></span>
<dl><span data-ttu-id="c9697-355">
<dt>이름: &lt; 위협 &gt; 이름</dt>
<dt>ID: &lt; 위협 &gt; ID</dt> 
<dt> 심각도: &lt; &gt; 심각도, 예:</span><span class="sxs-lookup"><span data-stu-id="c9697-355">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="c9697-356">낮음</span><span class="sxs-lookup"><span data-stu-id="c9697-356">Low</span></span></li>
<li><span data-ttu-id="c9697-357">보통</span><span class="sxs-lookup"><span data-stu-id="c9697-357">Moderate</span></span></li>
<li><span data-ttu-id="c9697-358">높음</span><span class="sxs-lookup"><span data-stu-id="c9697-358">High</span></span></li>
<li><span data-ttu-id="c9697-359">심각</span><span class="sxs-lookup"><span data-stu-id="c9697-359">Severe</span></span></li>
</ul><span data-ttu-id="c9697-360">
</dt>
<dt>범주: &lt; 범주 설명 &gt; 입니다(예: 위협 또는 맬웨어 유형).</dt> 
<dt>경로: &lt; 파일 &gt; 경로</dt>
<dt>사용자: &lt; 도메인 &gt; \& lt; 사용자 &gt; </dt>오류 코드: 오류 코드 위협
<dt> &lt; &gt; 상태와 관련된 결과 코드입니다. 표준 HRESULT 값입니다. </dt> 
<dt>오류 설명: &lt; 오류 설명 &gt; 오류에 대한 설명입니다.</dt> 
<dt>서명 버전: &lt; 정의 &gt; 버전</dt>
<dt>엔진 버전: Antimalware Engine &lt; 버전 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="c9697-360">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values. </dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-361">이벤트 ID: 1013</span><span class="sxs-lookup"><span data-stu-id="c9697-361">Event ID: 1013</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-362">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-362">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-363">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-363">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-364">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-364">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-365">
<b>맬웨어 방지 플랫폼에서 맬웨어 및 사용자 원치 않는 기타 소프트웨어 기록을 삭제했습니다.</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-365">
<b>The antimalware platform deleted history of malware and other potentially unwanted software.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-366">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-366">Description:</span></span>
</td>
<td >
<span data-ttu-id="c9697-367">Microsoft Defender 바이러스 백신 맬웨어 및 사용자 원치 않는 기타 소프트웨어에 대한 기록이 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-367">Microsoft Defender Antivirus has removed history of malware and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="c9697-368">Time: 이벤트가 발생한 시간(예: 기록이 
<dt>제거된 시간)입니다. 이 매개 변수는 위협 이벤트에서 사용되지 않습니다. 따라서 재구성 시간인지 감염 시간인지에 대한 혼동을 피할 수 있습니다. 이러한 경우 이러한</dt> 작업을 작업 시간 또는 검색 시간으로 특별히 호출합니다. 
<dt>사용자: &lt; 도메인 &gt; \& lt; 사용자 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="c9697-368">
<dt>Time: The time when the event occurred, for example when the history is purged. This parameter is not used in threat events so that there is no confusion regarding whether it is remediation time or infection time. For those, we specifically call them as Action Time or Detection Time.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-369">이벤트 ID: 1014</span><span class="sxs-lookup"><span data-stu-id="c9697-369">Event ID: 1014</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-370">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-370">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-371">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-371">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-372">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-372">Message:</span></span>
</td>
<td >
<span data-ttu-id="c9697-373">맬웨어 방지 플랫폼에서 맬웨어 및 사용자 원치 않는 기타 소프트웨어 기록을 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-373">The antimalware platform could not delete history of malware and other potentially unwanted software.</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-374">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-374">Description:</span></span>
</td>
<td >
<span data-ttu-id="c9697-375">Microsoft Defender 바이러스 백신 맬웨어 및 사용자 원치 않는 기타 소프트웨어의 기록을 제거하려고 하는 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-375">Microsoft Defender Antivirus has encountered an error trying to remove history of malware and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="c9697-376">Time: 이벤트가 발생한 시간(예: 기록이 
<dt>제거된 시간)입니다. 이 매개 변수는 위협 이벤트에서 사용되지 않습니다. 따라서 재구성 시간인지 감염 시간인지에 대한 혼동을 피할 수 있습니다. 이러한 경우 이러한</dt> 작업을 작업 시간 또는 검색 시간으로 특별히 호출합니다. 
<dt>사용자: &lt; 도메인 &gt; \& lt; 사용자 &gt; </dt>오류 코드: 오류 코드 위협
<dt> &lt; &gt; 상태와 관련된 결과 코드입니다. 표준 HRESULT 값입니다. </dt> 
<dt>오류 설명: &lt; 오류 설명 &gt; 오류에 대한 설명입니다.</dt>
</span><span class="sxs-lookup"><span data-stu-id="c9697-376">
<dt>Time: The time when the event occurred, for example when the history is purged. This parameter is not used in threat events so that there is no confusion regarding whether it is remediation time or infection time. For those, we specifically call them as Action Time or Detection Time.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values. </dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-377">이벤트 ID: 1015</span><span class="sxs-lookup"><span data-stu-id="c9697-377">Event ID: 1015</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-378">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-378">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-379">
<b>MALWAREPROTECTION_BEHAVIOR_DETECTED </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-379">
<b>MALWAREPROTECTION_BEHAVIOR_DETECTED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-380">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-380">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-381">
<b>맬웨어 방지 플랫폼에서 의심스러운 동작을 감지했습니다.</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-381">
<b>The antimalware platform detected suspicious behavior.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-382">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-382">Description:</span></span>
</td>
<td >
<span data-ttu-id="c9697-383">Microsoft Defender 바이러스 백신 의심스러운 동작을 감지했습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-383">Microsoft Defender Antivirus has detected a suspicious behavior.</span></span><br/><span data-ttu-id="c9697-384">자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c9697-384">For more information, see the following:</span></span>
<dl><span data-ttu-id="c9697-385">
<dt>이름: &lt; 위협 &gt; 이름</dt>
<dt>ID: &lt; 위협 &gt; ID</dt> 
<dt> 심각도: &lt; &gt; 심각도, 예:</span><span class="sxs-lookup"><span data-stu-id="c9697-385">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="c9697-386">낮음</span><span class="sxs-lookup"><span data-stu-id="c9697-386">Low</span></span></li>
<li><span data-ttu-id="c9697-387">보통</span><span class="sxs-lookup"><span data-stu-id="c9697-387">Moderate</span></span></li>
<li><span data-ttu-id="c9697-388">높음</span><span class="sxs-lookup"><span data-stu-id="c9697-388">High</span></span></li>
<li><span data-ttu-id="c9697-389">심각</span><span class="sxs-lookup"><span data-stu-id="c9697-389">Severe</span></span></li>
</ul><span data-ttu-id="c9697-390">
</dt>
<dt>범주: &lt; 범주 설명 &gt; 입니다(예: 위협 또는 맬웨어 유형).</dt> 
<dt>경로: &lt; 파일 &gt; 경로</dt> 
<dt> 검색 원본: &lt; 검색 원본 , 예를 들면 다음과 &gt; 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-390">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="c9697-391">알 수 없음</span><span class="sxs-lookup"><span data-stu-id="c9697-391">Unknown</span></span></li>
<li><span data-ttu-id="c9697-392">로컬 컴퓨터</span><span class="sxs-lookup"><span data-stu-id="c9697-392">Local computer</span></span></li>
<li><span data-ttu-id="c9697-393">네트워크 공유</span><span class="sxs-lookup"><span data-stu-id="c9697-393">Network share</span></span></li>
<li><span data-ttu-id="c9697-394">인터넷</span><span class="sxs-lookup"><span data-stu-id="c9697-394">Internet</span></span></li>
<li><span data-ttu-id="c9697-395">들어오는 트래픽</span><span class="sxs-lookup"><span data-stu-id="c9697-395">Incoming traffic</span></span></li>
<li><span data-ttu-id="c9697-396">아웃보이스 트래픽</span><span class="sxs-lookup"><span data-stu-id="c9697-396">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="c9697-397">
</dt>
<dt>검색 유형: &lt; 검색 &gt; 유형, 예:</span><span class="sxs-lookup"><span data-stu-id="c9697-397">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="c9697-398">Heuristics</span><span class="sxs-lookup"><span data-stu-id="c9697-398">Heuristics</span></span></li>
<li><span data-ttu-id="c9697-399">일반</span><span class="sxs-lookup"><span data-stu-id="c9697-399">Generic</span></span></li>
<li><span data-ttu-id="c9697-400">구체적</span><span class="sxs-lookup"><span data-stu-id="c9697-400">Concrete</span></span></li>
<li><span data-ttu-id="c9697-401">동적 서명</span><span class="sxs-lookup"><span data-stu-id="c9697-401">Dynamic signature</span></span></li>
</ul><span data-ttu-id="c9697-402">
</dt>
<dt>검색 원본: &lt; 검색 &gt; 원본: 예:</span><span class="sxs-lookup"><span data-stu-id="c9697-402">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="c9697-403">사용자: 사용자가 시작한 경우</span><span class="sxs-lookup"><span data-stu-id="c9697-403">User: user initiated</span></span></li>
<li><span data-ttu-id="c9697-404">시스템: 시스템이 시작된 경우</span><span class="sxs-lookup"><span data-stu-id="c9697-404">System: system initiated</span></span></li>
<li><span data-ttu-id="c9697-405">실시간: 실시간 구성 요소가 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-405">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="c9697-406">IOAV: IE 다운로드 및 Outlook Express 첨부 파일 시작</span><span class="sxs-lookup"><span data-stu-id="c9697-406">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="c9697-407">NIS: 네트워크 검사 시스템</span><span class="sxs-lookup"><span data-stu-id="c9697-407">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="c9697-408">IEPROTECT: IE - IExtensionValidation; 이렇게 하여 악의적인 웹 페이지 컨트롤로부터 보호</span><span class="sxs-lookup"><span data-stu-id="c9697-408">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="c9697-409">ELAM(맬웨어 방지 조기 실행).</span><span class="sxs-lookup"><span data-stu-id="c9697-409">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="c9697-410">여기에는 부팅 시퀀스에서 검색된 맬웨어가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-410">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="c9697-411">원격 attestation</span><span class="sxs-lookup"><span data-stu-id="c9697-411">Remote attestation</span></span></li>
</ul><span data-ttu-id="c9697-412">AMSI(맬웨어 방지 검사 인터페이스).</span><span class="sxs-lookup"><span data-stu-id="c9697-412">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="c9697-413">제3자도 호출할 수 있는 스크립트(PS, VBS)를 보호하는 데 주로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-413">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="c9697-414">UAC </dt> 
<dt>상태: &lt; 상태 &gt; </dt>
<dt>사용자: &lt; 도메인 &gt; \& lt; 사용자 &gt; </dt>
<dt>프로세스 이름: &lt; PID &gt; </dt>서명 ID의 프로세스: 심각도와
<dt>일치하는 열입니다.</dt> 
<dt>서명 버전: &lt; 정의 &gt; 버전</dt>
<dt>엔진 &lt; &gt; 버전:</dt>Antimalware Engine 버전
<dt>화질 레이블:</dt>대상 파일 이름: 파일
<dt>이름 파일의 &lt; &gt; 이름입니다.</dt>
</span><span class="sxs-lookup"><span data-stu-id="c9697-414">UAC</dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Signature ID: Enumeration matching severity.</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
<dt>Fidelity Label:</dt>
<dt>Target File Name: &lt;File name&gt; Name of the file.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-415">이벤트 ID: 1116</span><span class="sxs-lookup"><span data-stu-id="c9697-415">Event ID: 1116</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-416">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-416">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-417">
<b>MALWAREPROTECTION_STATE_MALWARE_DETECTED</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-417">
<b>MALWAREPROTECTION_STATE_MALWARE_DETECTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-418">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-418">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-419">
<b>맬웨어 방지 플랫폼에서 맬웨어 또는 사용자 원치 않는 기타 소프트웨어를 검색했습니다. </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-419">
<b>The antimalware platform detected malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-420">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-420">Description:</span></span>
</td>
<td >
<span data-ttu-id="c9697-421">Microsoft Defender 바이러스 백신 맬웨어 또는 사용자 원치 않는 기타 소프트웨어가 검색되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-421">Microsoft Defender Antivirus has detected malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="c9697-422">자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c9697-422">For more information, see the following:</span></span>
<dl><span data-ttu-id="c9697-423">
<dt>이름: &lt; 위협 &gt; 이름</dt>
<dt>ID: &lt; 위협 &gt; ID</dt> 
<dt> 심각도: &lt; &gt; 심각도, 예:</span><span class="sxs-lookup"><span data-stu-id="c9697-423">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="c9697-424">낮음</span><span class="sxs-lookup"><span data-stu-id="c9697-424">Low</span></span></li>
<li><span data-ttu-id="c9697-425">보통</span><span class="sxs-lookup"><span data-stu-id="c9697-425">Moderate</span></span></li>
<li><span data-ttu-id="c9697-426">높음</span><span class="sxs-lookup"><span data-stu-id="c9697-426">High</span></span></li>
<li><span data-ttu-id="c9697-427">심각</span><span class="sxs-lookup"><span data-stu-id="c9697-427">Severe</span></span></li>
</ul><span data-ttu-id="c9697-428">
</dt>
<dt>범주: &lt; 범주 설명 &gt; 입니다(예: 위협 또는 맬웨어 유형).</dt> 
<dt>경로: &lt; 파일 &gt; 경로</dt> 
<dt> 검색 원본: &lt; 검색 원본 , 예를 들면 다음과 &gt; 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-428">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="c9697-429">알 수 없음</span><span class="sxs-lookup"><span data-stu-id="c9697-429">Unknown</span></span></li>
<li><span data-ttu-id="c9697-430">로컬 컴퓨터</span><span class="sxs-lookup"><span data-stu-id="c9697-430">Local computer</span></span></li>
<li><span data-ttu-id="c9697-431">네트워크 공유</span><span class="sxs-lookup"><span data-stu-id="c9697-431">Network share</span></span></li>
<li><span data-ttu-id="c9697-432">인터넷</span><span class="sxs-lookup"><span data-stu-id="c9697-432">Internet</span></span></li>
<li><span data-ttu-id="c9697-433">들어오는 트래픽</span><span class="sxs-lookup"><span data-stu-id="c9697-433">Incoming traffic</span></span></li>
<li><span data-ttu-id="c9697-434">아웃보이스 트래픽</span><span class="sxs-lookup"><span data-stu-id="c9697-434">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="c9697-435">
</dt>
<dt>검색 유형: &lt; 검색 &gt; 유형, 예:</span><span class="sxs-lookup"><span data-stu-id="c9697-435">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="c9697-436">Heuristics</span><span class="sxs-lookup"><span data-stu-id="c9697-436">Heuristics</span></span></li>
<li><span data-ttu-id="c9697-437">일반</span><span class="sxs-lookup"><span data-stu-id="c9697-437">Generic</span></span></li>
<li><span data-ttu-id="c9697-438">구체적</span><span class="sxs-lookup"><span data-stu-id="c9697-438">Concrete</span></span></li>
<li><span data-ttu-id="c9697-439">동적 서명</span><span class="sxs-lookup"><span data-stu-id="c9697-439">Dynamic signature</span></span></li>
</ul><span data-ttu-id="c9697-440">
</dt>
<dt>검색 원본: &lt; 검색 &gt; 원본: 예:</span><span class="sxs-lookup"><span data-stu-id="c9697-440">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="c9697-441">사용자: 사용자가 시작한 경우</span><span class="sxs-lookup"><span data-stu-id="c9697-441">User: user initiated</span></span></li>
<li><span data-ttu-id="c9697-442">시스템: 시스템이 시작된 경우</span><span class="sxs-lookup"><span data-stu-id="c9697-442">System: system initiated</span></span></li>
<li><span data-ttu-id="c9697-443">실시간: 실시간 구성 요소가 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-443">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="c9697-444">IOAV: IE 다운로드 및 Outlook Express 첨부 파일 시작</span><span class="sxs-lookup"><span data-stu-id="c9697-444">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="c9697-445">NIS: 네트워크 검사 시스템</span><span class="sxs-lookup"><span data-stu-id="c9697-445">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="c9697-446">IEPROTECT: IE - IExtensionValidation; 이렇게 하여 악의적인 웹 페이지 컨트롤로부터 보호</span><span class="sxs-lookup"><span data-stu-id="c9697-446">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="c9697-447">ELAM(맬웨어 방지 조기 실행).</span><span class="sxs-lookup"><span data-stu-id="c9697-447">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="c9697-448">여기에는 부팅 시퀀스에서 검색된 맬웨어가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-448">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="c9697-449">원격 attestation</span><span class="sxs-lookup"><span data-stu-id="c9697-449">Remote attestation</span></span></li>
</ul><span data-ttu-id="c9697-450">AMSI(맬웨어 방지 검사 인터페이스).</span><span class="sxs-lookup"><span data-stu-id="c9697-450">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="c9697-451">제3자도 호출할 수 있는 스크립트(PS, VBS)를 보호하는 데 주로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-451">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="c9697-452">UAC </dt> 
<dt>사용자: &lt; 도메인 &gt; \& lt; 사용자 &gt; </dt>
<dt>프로세스 이름: &lt; PID &gt; </dt>서명 버전의
<dt>프로세스: &lt; &gt; </dt>정의 버전 엔진 버전: Antimalware Engine
<dt> &lt; 버전 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="c9697-452">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-453">사용자 작업:</span><span class="sxs-lookup"><span data-stu-id="c9697-453">User action:</span></span>
</td>
<td >
<span data-ttu-id="c9697-454">필요한 작업은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-454">No action is required.</span></span> <span data-ttu-id="c9697-455">Microsoft Defender 바이러스 백신 일시 중단하고 이 위협에 대한 일상적인 조치를 취할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-455">Microsoft Defender Antivirus can suspend and take routine action on this threat.</span></span> <span data-ttu-id="c9697-456">위협을 수동으로 제거하려면 Microsoft Defender 바이러스 백신 컴퓨터 <b>정리를 클릭합니다.</b></span><span class="sxs-lookup"><span data-stu-id="c9697-456">If you want to remove the threat manually, in the Microsoft Defender Antivirus interface, click <b>Clean Computer</b>.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-457">이벤트 ID: 1117</span><span class="sxs-lookup"><span data-stu-id="c9697-457">Event ID: 1117</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-458">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-458">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-459">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_TAKEN </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-459">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_TAKEN </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-460">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-460">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-461">
<b>맬웨어 방지 플랫폼은 맬웨어 또는 사용자 원치 않는 기타 소프트웨어로부터 시스템을 보호하기 위한 작업을 수행했습니다. </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-461">
<b>The antimalware platform performed an action to protect your system from malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-462">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-462">Description:</span></span>
</td>
<td >
<span data-ttu-id="c9697-463">Microsoft Defender 바이러스 백신 맬웨어 또는 사용자 원치 않는 기타 소프트웨어로부터 이 머신을 보호하기 위해 작업을 수행했습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-463">Microsoft Defender Antivirus has taken action to protect this machine from malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="c9697-464">자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c9697-464">For more information, see the following:</span></span>
<dl><span data-ttu-id="c9697-465">
<dt>이름: &lt; 위협 &gt; 이름</dt>
<dt>ID: &lt; 위협 &gt; ID</dt> 
<dt> 심각도: &lt; &gt; 심각도, 예:</span><span class="sxs-lookup"><span data-stu-id="c9697-465">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="c9697-466">낮음</span><span class="sxs-lookup"><span data-stu-id="c9697-466">Low</span></span></li>
<li><span data-ttu-id="c9697-467">보통</span><span class="sxs-lookup"><span data-stu-id="c9697-467">Moderate</span></span></li>
<li><span data-ttu-id="c9697-468">높음</span><span class="sxs-lookup"><span data-stu-id="c9697-468">High</span></span></li>
<li><span data-ttu-id="c9697-469">심각</span><span class="sxs-lookup"><span data-stu-id="c9697-469">Severe</span></span></li>
</ul><span data-ttu-id="c9697-470">
</dt>
<dt>범주: &lt; 범주 설명 &gt; 입니다(예: 위협 또는 맬웨어 유형).</dt> 
<dt>경로: &lt; 파일 &gt; 경로</dt> 
<dt> 검색 원본: &lt; 검색 원본 , 예를 들면 다음과 &gt; 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-470">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="c9697-471">알 수 없음</span><span class="sxs-lookup"><span data-stu-id="c9697-471">Unknown</span></span></li>
<li><span data-ttu-id="c9697-472">로컬 컴퓨터</span><span class="sxs-lookup"><span data-stu-id="c9697-472">Local computer</span></span></li>
<li><span data-ttu-id="c9697-473">네트워크 공유</span><span class="sxs-lookup"><span data-stu-id="c9697-473">Network share</span></span></li>
<li><span data-ttu-id="c9697-474">인터넷</span><span class="sxs-lookup"><span data-stu-id="c9697-474">Internet</span></span></li>
<li><span data-ttu-id="c9697-475">들어오는 트래픽</span><span class="sxs-lookup"><span data-stu-id="c9697-475">Incoming traffic</span></span></li>
<li><span data-ttu-id="c9697-476">아웃보이스 트래픽</span><span class="sxs-lookup"><span data-stu-id="c9697-476">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="c9697-477">
</dt>
<dt>검색 유형: &lt; 검색 &gt; 유형, 예:</span><span class="sxs-lookup"><span data-stu-id="c9697-477">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="c9697-478">Heuristics</span><span class="sxs-lookup"><span data-stu-id="c9697-478">Heuristics</span></span></li>
<li><span data-ttu-id="c9697-479">일반</span><span class="sxs-lookup"><span data-stu-id="c9697-479">Generic</span></span></li>
<li><span data-ttu-id="c9697-480">구체적</span><span class="sxs-lookup"><span data-stu-id="c9697-480">Concrete</span></span></li>
<li><span data-ttu-id="c9697-481">동적 서명</span><span class="sxs-lookup"><span data-stu-id="c9697-481">Dynamic signature</span></span></li>
</ul><span data-ttu-id="c9697-482">
</dt>
<dt>검색 원본: &lt; 검색 &gt; 원본: 예:</span><span class="sxs-lookup"><span data-stu-id="c9697-482">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="c9697-483">사용자: 사용자가 시작한 경우</span><span class="sxs-lookup"><span data-stu-id="c9697-483">User: user initiated</span></span></li>
<li><span data-ttu-id="c9697-484">시스템: 시스템이 시작된 경우</span><span class="sxs-lookup"><span data-stu-id="c9697-484">System: system initiated</span></span></li>
<li><span data-ttu-id="c9697-485">실시간: 실시간 구성 요소가 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-485">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="c9697-486">IOAV: IE 다운로드 및 Outlook Express 첨부 파일 시작</span><span class="sxs-lookup"><span data-stu-id="c9697-486">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="c9697-487">NIS: 네트워크 검사 시스템</span><span class="sxs-lookup"><span data-stu-id="c9697-487">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="c9697-488">IEPROTECT: IE - IExtensionValidation; 이렇게 하여 악의적인 웹 페이지 컨트롤로부터 보호</span><span class="sxs-lookup"><span data-stu-id="c9697-488">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="c9697-489">ELAM(맬웨어 방지 조기 실행).</span><span class="sxs-lookup"><span data-stu-id="c9697-489">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="c9697-490">여기에는 부팅 시퀀스에서 검색된 맬웨어가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-490">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="c9697-491">원격 attestation</span><span class="sxs-lookup"><span data-stu-id="c9697-491">Remote attestation</span></span></li>
</ul><span data-ttu-id="c9697-492">AMSI(맬웨어 방지 검사 인터페이스).</span><span class="sxs-lookup"><span data-stu-id="c9697-492">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="c9697-493">제3자도 호출할 수 있는 스크립트(PS, VBS)를 보호하는 데 주로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-493">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="c9697-494">UAC </dt> 
<dt>사용자: &lt; 도메인 &gt; \& lt; 사용자 &gt; </dt>
<dt>프로세스 이름: &lt; PID &gt; </dt> 
<dt> 작업의 프로세스: &lt; 작업 , 예를 들면 다음과 &gt; 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-494">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="c9697-495">정리: 리소스가 정리된 경우</span><span class="sxs-lookup"><span data-stu-id="c9697-495">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="c9697-496">Quarantine: Resource was quarantined</span><span class="sxs-lookup"><span data-stu-id="c9697-496">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="c9697-497">제거: 리소스가 삭제되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-497">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="c9697-498">허용: 리소스가 실행/존재할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-498">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="c9697-499">사용자 정의: 사용자가 지정한 작업 목록에서 일반적으로 하나인 사용자 정의 작업</span><span class="sxs-lookup"><span data-stu-id="c9697-499">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="c9697-500">작업 없음: 아무 작업도 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-500">No action: No action</span></span></li>
<li><span data-ttu-id="c9697-501">차단: 리소스가 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-501">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="c9697-502">
</dt>
<dt>작업 상태: &lt; 추가 작업에 &gt; 대한 설명</dt>오류 코드: 오류 코드 위협 상태와 관련된 결과
<dt> &lt; &gt; 코드입니다. 표준 HRESULT 값입니다.</dt> 
<dt>오류 설명: &lt; 오류 설명 &gt; 오류에 대한 설명입니다.</dt> 
<dt>서명 버전: &lt; 정의 &gt; 버전</dt>
<dt>엔진 버전: &lt; &gt; </dt> Antimalware Engine 버전 참고: Microsoft Defender 바이러스 백신, Microsoft Security Essentials, 악성 소프트웨어 제거 도구 또는 System Center Endpoint Protection 맬웨어를 검색할 때마다 맬웨어가 변경될 수 있는 다음과 같은 시스템 설정 및 서비스를 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-502">
</dt>
<dt>Action Status: &lt;Description of additional actions&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt> NOTE: Whenever Microsoft Defender Antivirus, Microsoft Security Essentials, Malicious Software Removal Tool, or System Center Endpoint Protection detects a malware, it will restore the following system settings and services that the malware might have changed:</span></span><ul>
<li><span data-ttu-id="c9697-503">기본 Internet Explorer 또는 Microsoft Edge 설정</span><span class="sxs-lookup"><span data-stu-id="c9697-503">Default Internet Explorer or Microsoft Edge setting</span></span></li>
<li><span data-ttu-id="c9697-504">사용자 액세스 제어 설정</span><span class="sxs-lookup"><span data-stu-id="c9697-504">User Access Control settings</span></span></li>
<li><span data-ttu-id="c9697-505">Chrome 설정</span><span class="sxs-lookup"><span data-stu-id="c9697-505">Chrome settings</span></span></li>
<li><span data-ttu-id="c9697-506">부팅 제어 데이터</span><span class="sxs-lookup"><span data-stu-id="c9697-506">Boot Control Data</span></span></li>
<li><span data-ttu-id="c9697-507">Regedit 및 작업 관리자 레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="c9697-507">Regedit and Task Manager registry settings</span></span></li>
<li><span data-ttu-id="c9697-508">Windows 업데이트, Background Intelligent Transfer Service 및 원격 프로시저 호출 서비스</span><span class="sxs-lookup"><span data-stu-id="c9697-508">Windows Update, Background Intelligent Transfer Service, and Remote Procedure Call service</span></span></li>
<li><span data-ttu-id="c9697-509">Windows 운영 체제 파일</span><span class="sxs-lookup"><span data-stu-id="c9697-509">Windows Operating System files</span></span></li></ul>
<span data-ttu-id="c9697-510">위의 컨텍스트는 다음 클라이언트 및 서버 버전에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-510">The above context applies to the following client and server versions:</span></span>
<table>
<tr>
<th><span data-ttu-id="c9697-511">운영 체제</span><span class="sxs-lookup"><span data-stu-id="c9697-511">Operating system</span></span></th>
<th><span data-ttu-id="c9697-512">운영 체제 버전</span><span class="sxs-lookup"><span data-stu-id="c9697-512">Operating system version</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-513">클라이언트 운영 체제</span><span class="sxs-lookup"><span data-stu-id="c9697-513">Client Operating System</span></span>
</td>
<td>
<span data-ttu-id="c9697-514">Windows Vista(서비스 팩 1 또는 서비스 팩 2), Windows 7 이상</span><span class="sxs-lookup"><span data-stu-id="c9697-514">Windows Vista (Service Pack 1, or Service Pack 2), Windows 7 and later</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-515">서버 운영 체제</span><span class="sxs-lookup"><span data-stu-id="c9697-515">Server Operating System</span></span>
</td>
<td>
<span data-ttu-id="c9697-516">Windows Server 2008, Windows Server 2008 R2, Windows Server 2012 및 Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="c9697-516">Windows Server 2008, Windows Server 2008 R2, Windows Server 2012, and Windows Server 2016</span></span>
</td>
</tr>
</table>
</dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-517">사용자 작업:</span><span class="sxs-lookup"><span data-stu-id="c9697-517">User action:</span></span>
</td>
<td >
<span data-ttu-id="c9697-518">필요한 작업은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-518">No action is necessary.</span></span> <span data-ttu-id="c9697-519">Microsoft Defender 바이러스 백신 제거하거나 위협을 무단으로 제거했습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-519">Microsoft Defender Antivirus removed or quarantined a threat.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-520">이벤트 ID: 1118</span><span class="sxs-lookup"><span data-stu-id="c9697-520">Event ID: 1118</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-521">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-521">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-522">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-522">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-523">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-523">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-524">
<b>맬웨어 방지 플랫폼이 맬웨어 또는 사용자 원치 않는 기타 소프트웨어로부터 시스템을 보호하기 위한 작업을 수행하려고 했지만 작업이 실패했습니다. </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-524">
<b>The antimalware platform attempted to perform an action to protect your system from malware or other potentially unwanted software, but the action failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-525">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-525">Description:</span></span>
</td>
<td >
<span data-ttu-id="c9697-526">Microsoft Defender 바이러스 백신 또는 사용자 원치 않는 기타 소프트웨어에 대해 조치를 취할 때 중요하지 않은 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-526">Microsoft Defender Antivirus has encountered a non-critical error when taking action on malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="c9697-527">자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c9697-527">For more information, see the following:</span></span>
<dl><span data-ttu-id="c9697-528">
<dt>이름: &lt; 위협 &gt; 이름</dt>
<dt>ID: &lt; 위협 &gt; ID</dt> 
<dt> 심각도: &lt; &gt; 심각도, 예:</span><span class="sxs-lookup"><span data-stu-id="c9697-528">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="c9697-529">낮음</span><span class="sxs-lookup"><span data-stu-id="c9697-529">Low</span></span></li>
<li><span data-ttu-id="c9697-530">보통</span><span class="sxs-lookup"><span data-stu-id="c9697-530">Moderate</span></span></li>
<li><span data-ttu-id="c9697-531">높음</span><span class="sxs-lookup"><span data-stu-id="c9697-531">High</span></span></li>
<li><span data-ttu-id="c9697-532">심각</span><span class="sxs-lookup"><span data-stu-id="c9697-532">Severe</span></span></li>
</ul><span data-ttu-id="c9697-533">
</dt>
<dt>범주: &lt; 범주 설명 &gt; 입니다(예: 위협 또는 맬웨어 유형).</dt> 
<dt>경로: &lt; 파일 &gt; 경로</dt> 
<dt> 검색 원본: &lt; 검색 원본 , 예를 들면 다음과 &gt; 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-533">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="c9697-534">알 수 없음</span><span class="sxs-lookup"><span data-stu-id="c9697-534">Unknown</span></span></li>
<li><span data-ttu-id="c9697-535">로컬 컴퓨터</span><span class="sxs-lookup"><span data-stu-id="c9697-535">Local computer</span></span></li>
<li><span data-ttu-id="c9697-536">네트워크 공유</span><span class="sxs-lookup"><span data-stu-id="c9697-536">Network share</span></span></li>
<li><span data-ttu-id="c9697-537">인터넷</span><span class="sxs-lookup"><span data-stu-id="c9697-537">Internet</span></span></li>
<li><span data-ttu-id="c9697-538">들어오는 트래픽</span><span class="sxs-lookup"><span data-stu-id="c9697-538">Incoming traffic</span></span></li>
<li><span data-ttu-id="c9697-539">아웃보이스 트래픽</span><span class="sxs-lookup"><span data-stu-id="c9697-539">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="c9697-540">
</dt>
<dt>검색 유형: &lt; 검색 &gt; 유형, 예:</span><span class="sxs-lookup"><span data-stu-id="c9697-540">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="c9697-541">Heuristics</span><span class="sxs-lookup"><span data-stu-id="c9697-541">Heuristics</span></span></li>
<li><span data-ttu-id="c9697-542">일반</span><span class="sxs-lookup"><span data-stu-id="c9697-542">Generic</span></span></li>
<li><span data-ttu-id="c9697-543">구체적</span><span class="sxs-lookup"><span data-stu-id="c9697-543">Concrete</span></span></li>
<li><span data-ttu-id="c9697-544">동적 서명</span><span class="sxs-lookup"><span data-stu-id="c9697-544">Dynamic signature</span></span></li>
</ul><span data-ttu-id="c9697-545">
</dt>
<dt>검색 원본: &lt; 검색 &gt; 원본: 예:</span><span class="sxs-lookup"><span data-stu-id="c9697-545">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="c9697-546">사용자: 사용자가 시작한 경우</span><span class="sxs-lookup"><span data-stu-id="c9697-546">User: user initiated</span></span></li>
<li><span data-ttu-id="c9697-547">시스템: 시스템이 시작된 경우</span><span class="sxs-lookup"><span data-stu-id="c9697-547">System: system initiated</span></span></li>
<li><span data-ttu-id="c9697-548">실시간: 실시간 구성 요소가 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-548">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="c9697-549">IOAV: IE 다운로드 및 Outlook Express 첨부 파일 시작</span><span class="sxs-lookup"><span data-stu-id="c9697-549">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="c9697-550">NIS: 네트워크 검사 시스템</span><span class="sxs-lookup"><span data-stu-id="c9697-550">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="c9697-551">IEPROTECT: IE - IExtensionValidation; 이렇게 하여 악의적인 웹 페이지 컨트롤로부터 보호</span><span class="sxs-lookup"><span data-stu-id="c9697-551">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="c9697-552">ELAM(맬웨어 방지 조기 실행).</span><span class="sxs-lookup"><span data-stu-id="c9697-552">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="c9697-553">여기에는 부팅 시퀀스에서 검색된 맬웨어가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-553">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="c9697-554">원격 attestation</span><span class="sxs-lookup"><span data-stu-id="c9697-554">Remote attestation</span></span></li>
</ul><span data-ttu-id="c9697-555">AMSI(맬웨어 방지 검사 인터페이스).</span><span class="sxs-lookup"><span data-stu-id="c9697-555">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="c9697-556">제3자도 호출할 수 있는 스크립트(PS, VBS)를 보호하는 데 주로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-556">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="c9697-557">UAC </dt> 
<dt>사용자: &lt; 도메인 &gt; \& lt; 사용자 &gt; </dt>
<dt>프로세스 이름: &lt; PID &gt; </dt> 
<dt> 작업의 프로세스: &lt; 작업 , 예를 들면 다음과 &gt; 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-557">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="c9697-558">정리: 리소스가 정리된 경우</span><span class="sxs-lookup"><span data-stu-id="c9697-558">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="c9697-559">Quarantine: Resource was quarantined</span><span class="sxs-lookup"><span data-stu-id="c9697-559">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="c9697-560">제거: 리소스가 삭제되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-560">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="c9697-561">허용: 리소스가 실행/존재할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-561">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="c9697-562">사용자 정의: 사용자가 지정한 작업 목록에서 일반적으로 하나인 사용자 정의 작업</span><span class="sxs-lookup"><span data-stu-id="c9697-562">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="c9697-563">작업 없음: 아무 작업도 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-563">No action: No action</span></span></li>
<li><span data-ttu-id="c9697-564">차단: 리소스가 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-564">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="c9697-565">
</dt>
<dt>작업 상태: &lt; 추가 작업에 &gt; 대한 설명</dt>오류 코드: 오류 코드 위협 상태와 관련된 결과
<dt> &lt; &gt; 코드입니다. 표준 HRESULT 값입니다.</dt> 
<dt>오류 설명: &lt; 오류 설명 &gt; 오류에 대한 설명입니다.</dt> 
<dt>서명 버전: &lt; 정의 &gt; 버전</dt>
<dt>엔진 버전: Antimalware Engine &lt; 버전 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="c9697-565">
</dt>
<dt>Action Status: &lt;Description of additional actions&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-566">사용자 작업:</span><span class="sxs-lookup"><span data-stu-id="c9697-566">User action:</span></span>
</td>
<td >
<span data-ttu-id="c9697-567">필요한 작업은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-567">No action is necessary.</span></span> <span data-ttu-id="c9697-568">Microsoft Defender 바이러스 백신 수정과 관련된 작업을 완료하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-568">Microsoft Defender Antivirus failed to complete a task related to the malware remediation.</span></span> <span data-ttu-id="c9697-569">이 오류는 심각한 오류는 아니며,</span><span class="sxs-lookup"><span data-stu-id="c9697-569">This is not a critical failure.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-570">이벤트 ID: 1119</span><span class="sxs-lookup"><span data-stu-id="c9697-570">Event ID: 1119</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-571">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-571">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-572">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_CRITICALLY_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-572">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_CRITICALLY_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-573">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-573">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-574">
<b>맬웨어 방지 플랫폼에서 맬웨어 또는 사용자 원치 않는 기타 소프트웨어에 대한 작업을 수행하려고 할 때 심각한 오류가 발생했습니다. 이벤트 메시지에 자세한 정보가 있습니다.</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-574">
<b>The antimalware platform encountered a critical error when trying to take action on malware or other potentially unwanted software. There are more details in the event message.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-575">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-575">Description:</span></span>
</td>
<td >
<span data-ttu-id="c9697-576">Microsoft Defender 바이러스 백신 또는 사용자 원치 않는 기타 소프트웨어에 대해 조치를 취할 때 심각한 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-576">Microsoft Defender Antivirus has encountered a critical error when taking action on malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="c9697-577">자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c9697-577">For more information, see the following:</span></span>
<dl><span data-ttu-id="c9697-578">
<dt>이름: &lt; 위협 &gt; 이름</dt>
<dt>ID: &lt; 위협 &gt; ID</dt> 
<dt> 심각도: &lt; &gt; 심각도, 예:</span><span class="sxs-lookup"><span data-stu-id="c9697-578">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="c9697-579">낮음</span><span class="sxs-lookup"><span data-stu-id="c9697-579">Low</span></span></li>
<li><span data-ttu-id="c9697-580">보통</span><span class="sxs-lookup"><span data-stu-id="c9697-580">Moderate</span></span></li>
<li><span data-ttu-id="c9697-581">높음</span><span class="sxs-lookup"><span data-stu-id="c9697-581">High</span></span></li>
<li><span data-ttu-id="c9697-582">심각</span><span class="sxs-lookup"><span data-stu-id="c9697-582">Severe</span></span></li>
</ul><span data-ttu-id="c9697-583">
</dt>
<dt>범주: &lt; 범주 설명 &gt; 입니다(예: 위협 또는 맬웨어 유형).</dt> 
<dt>경로: &lt; 파일 &gt; 경로</dt> 
<dt> 검색 원본: &lt; 검색 원본 , 예를 들면 다음과 &gt; 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-583">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="c9697-584">알 수 없음</span><span class="sxs-lookup"><span data-stu-id="c9697-584">Unknown</span></span></li>
<li><span data-ttu-id="c9697-585">로컬 컴퓨터</span><span class="sxs-lookup"><span data-stu-id="c9697-585">Local computer</span></span></li>
<li><span data-ttu-id="c9697-586">네트워크 공유</span><span class="sxs-lookup"><span data-stu-id="c9697-586">Network share</span></span></li>
<li><span data-ttu-id="c9697-587">인터넷</span><span class="sxs-lookup"><span data-stu-id="c9697-587">Internet</span></span></li>
<li><span data-ttu-id="c9697-588">들어오는 트래픽</span><span class="sxs-lookup"><span data-stu-id="c9697-588">Incoming traffic</span></span></li>
<li><span data-ttu-id="c9697-589">아웃보이스 트래픽</span><span class="sxs-lookup"><span data-stu-id="c9697-589">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="c9697-590">
</dt>
<dt>검색 유형: &lt; 검색 &gt; 유형, 예:</span><span class="sxs-lookup"><span data-stu-id="c9697-590">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="c9697-591">Heuristics</span><span class="sxs-lookup"><span data-stu-id="c9697-591">Heuristics</span></span></li>
<li><span data-ttu-id="c9697-592">일반</span><span class="sxs-lookup"><span data-stu-id="c9697-592">Generic</span></span></li>
<li><span data-ttu-id="c9697-593">구체적</span><span class="sxs-lookup"><span data-stu-id="c9697-593">Concrete</span></span></li>
<li><span data-ttu-id="c9697-594">동적 서명</span><span class="sxs-lookup"><span data-stu-id="c9697-594">Dynamic signature</span></span></li>
</ul><span data-ttu-id="c9697-595">
</dt>
<dt>검색 원본: &lt; 검색 &gt; 원본: 예:</span><span class="sxs-lookup"><span data-stu-id="c9697-595">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="c9697-596">사용자: 사용자가 시작한 경우</span><span class="sxs-lookup"><span data-stu-id="c9697-596">User: user initiated</span></span></li>
<li><span data-ttu-id="c9697-597">시스템: 시스템이 시작된 경우</span><span class="sxs-lookup"><span data-stu-id="c9697-597">System: system initiated</span></span></li>
<li><span data-ttu-id="c9697-598">실시간: 실시간 구성 요소가 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-598">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="c9697-599">IOAV: IE 다운로드 및 Outlook Express 첨부 파일 시작</span><span class="sxs-lookup"><span data-stu-id="c9697-599">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="c9697-600">NIS: 네트워크 검사 시스템</span><span class="sxs-lookup"><span data-stu-id="c9697-600">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="c9697-601">IEPROTECT: IE - IExtensionValidation; 이렇게 하여 악의적인 웹 페이지 컨트롤로부터 보호</span><span class="sxs-lookup"><span data-stu-id="c9697-601">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="c9697-602">ELAM(맬웨어 방지 조기 실행).</span><span class="sxs-lookup"><span data-stu-id="c9697-602">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="c9697-603">여기에는 부팅 시퀀스에서 검색된 맬웨어가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-603">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="c9697-604">원격 attestation</span><span class="sxs-lookup"><span data-stu-id="c9697-604">Remote attestation</span></span></li>
</ul><span data-ttu-id="c9697-605">AMSI(맬웨어 방지 검사 인터페이스).</span><span class="sxs-lookup"><span data-stu-id="c9697-605">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="c9697-606">제3자도 호출할 수 있는 스크립트(PS, VBS)를 보호하는 데 주로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-606">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="c9697-607">UAC </dt> 
<dt>사용자: &lt; 도메인 &gt; \& lt; 사용자 &gt; </dt>
<dt>프로세스 이름: &lt; PID &gt; </dt> 
<dt> 작업의 프로세스: &lt; 작업 , 예를 들면 다음과 &gt; 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-607">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="c9697-608">정리: 리소스가 정리된 경우</span><span class="sxs-lookup"><span data-stu-id="c9697-608">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="c9697-609">Quarantine: Resource was quarantined</span><span class="sxs-lookup"><span data-stu-id="c9697-609">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="c9697-610">제거: 리소스가 삭제되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-610">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="c9697-611">허용: 리소스가 실행/존재할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-611">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="c9697-612">사용자 정의: 사용자가 지정한 작업 목록에서 일반적으로 하나인 사용자 정의 작업</span><span class="sxs-lookup"><span data-stu-id="c9697-612">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="c9697-613">작업 없음: 아무 작업도 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-613">No action: No action</span></span></li>
<li><span data-ttu-id="c9697-614">차단: 리소스가 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-614">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="c9697-615">
</dt>
<dt>작업 상태: &lt; 추가 작업에 &gt; 대한 설명</dt>오류 코드: 오류 코드 위협 상태와 관련된 결과
<dt> &lt; &gt; 코드입니다. 표준 HRESULT 값입니다.</dt> 
<dt>오류 설명: &lt; 오류 설명 &gt; 오류에 대한 설명입니다.</dt> 
<dt>서명 버전: &lt; 정의 &gt; 버전</dt>
<dt>엔진 버전: Antimalware Engine &lt; 버전 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="c9697-615">
</dt>
<dt>Action Status: &lt;Description of additional actions&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-616">사용자 작업:</span><span class="sxs-lookup"><span data-stu-id="c9697-616">User action:</span></span>
</td>
<td >
<span data-ttu-id="c9697-617">Microsoft Defender 바이러스 백신 클라이언트에서 중요한 문제로 인해 이 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-617">The Microsoft Defender Antivirus client encountered this error due to critical issues.</span></span> <span data-ttu-id="c9697-618">끝점이 보호되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-618">The endpoint might not be protected.</span></span> <span data-ttu-id="c9697-619">오류 설명을 검토한 다음 아래의 관련 <b>사용자 작업 단계를</b> 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-619">Review the error description then follow the relevant <b>User action</b> steps below.</span></span>
<table>
<tr>
<th><span data-ttu-id="c9697-620">조치</span><span class="sxs-lookup"><span data-stu-id="c9697-620">Action</span></span></th>
<th><span data-ttu-id="c9697-621">사용자 작업</span><span class="sxs-lookup"><span data-stu-id="c9697-621">User action</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="c9697-622">
<b>제거</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-622">
<b>Remove</b>
</span></span></td>
<td>
<span data-ttu-id="c9697-623">정의를 업데이트한 다음 제거가 성공적이지 확인</span><span class="sxs-lookup"><span data-stu-id="c9697-623">Update the definitions then verify that the removal was successful.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="c9697-624">
<b>정리</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-624">
<b>Clean</b>
</span></span></td>
<td>
<span data-ttu-id="c9697-625">정의를 업데이트한 다음 수정이 성공적이지 확인</span><span class="sxs-lookup"><span data-stu-id="c9697-625">Update the definitions then verify that the remediation was successful.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="c9697-626">
<b>Quarantine</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-626">
<b>Quarantine</b>
</span></span></td>
<td>
<span data-ttu-id="c9697-627">정의를 업데이트하고 사용자에게 필요한 리소스에 액세스할 수 있는 권한이 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-627">Update the definitions and verify that the user has permission to access the necessary resources.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="c9697-628">
<b>허용</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-628">
<b>Allow</b>
</span></span></td>
<td>
<span data-ttu-id="c9697-629">사용자에게 필요한 리소스에 액세스할 수 있는 권한이 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="c9697-629">Verify that the user has permission to access the necessary resources.</span></span>
</td>
</tr>
</table>

<span data-ttu-id="c9697-630">이 이벤트가 지속되는 경우:</span><span class="sxs-lookup"><span data-stu-id="c9697-630">If this event persists:</span></span><ol>
<li><span data-ttu-id="c9697-631">검색을 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-631">Run the scan again.</span></span></li>
<li><span data-ttu-id="c9697-632">같은 방식으로 오류가 발생하면 <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft</a>지원 사이트로 이동하여 검색 상자에 오류 번호를 입력하여 오류 코드를 찾아야 합니다. <b></b></span><span class="sxs-lookup"><span data-stu-id="c9697-632">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="c9697-633"><a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft 기술 지원</a>에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-633">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-634">이벤트 ID: 1120</span><span class="sxs-lookup"><span data-stu-id="c9697-634">Event ID: 1120</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-635">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-635">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-636">
<b>MALWAREPROTECTION_THREAT_HASH</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-636">
<b>MALWAREPROTECTION_THREAT_HASH</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-637">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-637">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-638">
<b>Microsoft Defender 바이러스 백신 리소스에 대한 해시를 유인했습니다.</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-638">
<b>Microsoft Defender Antivirus has deduced the hashes for a threat resource.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-639">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-639">Description:</span></span>
</td>
<td >
<span data-ttu-id="c9697-640">Microsoft Defender 바이러스 백신 클라이언트가 정상 상태로 실행되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-640">Microsoft Defender Antivirus client is up and running in a healthy state.</span></span>
<dl><span data-ttu-id="c9697-641">
<dt>현재 플랫폼 버전: &lt; 현재 플랫폼 &gt; 버전</dt>
<dt>위협 리소스 경로: &lt; 경로 &gt; </dt>
<dt>해시: &lt; 해시 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="c9697-641">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
<dt>Threat Resource Path: &lt;Path&gt;</dt>
<dt>Hashes: &lt;Hashes&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td></td>
<td >
<div class="alert"><span data-ttu-id="c9697-642"><b>참고: 이 이벤트는 <b>ThreatFileHashLogging unsigned</b>정책을 설정한 경우만 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-642"><b>Note: This event will only be logged if the following policy is set: <b>ThreatFileHashLogging     unsigned</b>.</span></span></div>
<div> </div>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-643">이벤트 ID: 1150</span><span class="sxs-lookup"><span data-stu-id="c9697-643">Event ID: 1150</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-644">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-644">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-645">
<b>MALWAREPROTECTION_SERVICE_HEALTHY</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-645">
<b>MALWAREPROTECTION_SERVICE_HEALTHY</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-646">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-646">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-647">
<b>맬웨어 방지 플랫폼이 모니터링 플랫폼에 상태를 보고하는 경우 이 이벤트는 맬웨어 방지 플랫폼이 실행되고 있으며 정상 상태를 나타냅니다. </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-647">
<b>If your antimalware platform reports status to a monitoring platform, this event indicates that the antimalware platform is running and in a healthy state. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-648">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-648">Description:</span></span>
</td>
<td >
<span data-ttu-id="c9697-649">Microsoft Defender 바이러스 백신 클라이언트가 정상 상태로 실행되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-649">Microsoft Defender Antivirus client is up and running in a healthy state.</span></span>
<dl><span data-ttu-id="c9697-650">
<dt>플랫폼 버전: &lt; 현재 플랫폼 &gt; 버전</dt>
<dt>서명 버전: 정의 &lt; 버전 &gt; </dt>엔진 버전: Antimalware Engine
<dt> &lt; 버전 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="c9697-650">
<dt>Platform Version: &lt;Current platform version&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-651">사용자 작업:</span><span class="sxs-lookup"><span data-stu-id="c9697-651">User action:</span></span>
</td>
<td >
<span data-ttu-id="c9697-652">필요한 작업은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-652">No action is necessary.</span></span> <span data-ttu-id="c9697-653">클라이언트 Microsoft Defender 바이러스 백신 정상 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-653">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="c9697-654">이 이벤트는 시간당 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-654">This event is reported on an hourly basis.</span></span>
</td>
</tr>

<tr>
<th colspan="2"><span data-ttu-id="c9697-655">이벤트 ID: 1151</span><span class="sxs-lookup"><span data-stu-id="c9697-655">Event ID: 1151</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-656">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-656">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-657">
<b>MALWAREPROTECTION_SERVICE_HEALTH_REPORT</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-657">
<b>MALWAREPROTECTION_SERVICE_HEALTH_REPORT</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-658">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-658">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-659">
<b>Endpoint Protection 상태 보고서(UTC의 시간)</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-659">
<b>Endpoint Protection client health report (time in UTC) </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-660">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-660">Description:</span></span>
</td>
<td >
<span data-ttu-id="c9697-661">바이러스 백신 클라이언트 상태 보고서.</span><span class="sxs-lookup"><span data-stu-id="c9697-661">Antivirus client health report.</span></span>
<dl><span data-ttu-id="c9697-662">
<dt>플랫폼 버전: &lt; 현재 플랫폼 &gt; </dt>버전 엔진
<dt>버전: &lt; &gt; </dt>Antimalware Engine 버전 네트워크 실시간 검사 엔진
<dt>버전: &lt; &gt; </dt>네트워크 실시간 검사 엔진 버전 바이러스 백신 서명
<dt>버전: &lt; 바이러스 &gt; </dt>백신 서명 버전 스파이웨어 방지 서명
<dt> &lt; &gt; 버전:</dt>스파이웨어 방지 서명 버전 네트워크 실시간 검사 서명
<dt>버전: 네트워크 실시간 &lt; 검사 &gt; </dt>서명 버전
<dt>RTP 상태: &lt; 실시간 보호 &gt; 상태(사용</dt>또는 사용 안 하게)
<dt>OA 상태: &lt; On Access state &gt; (Enabled or Disabled)</dt>
<dt>IOAV state: &lt; IE Downloads and Outlook Express Attachments state &gt; (Enabled or Disabled)</dt>
<dt>BM state: &lt; Behavior Monitoring state &gt; (Enabled or Disabled)</dt>Antivirus signature
<dt>age: Antivirus signature age &lt; &gt; (in days) </dt> 
<dt>Antispyware signature age: &lt; Antispyware signature age &gt; (in days)</dt>
<dt>Last quick scan age: Last quick scan &lt; age &gt; (in days)</dt>Last full
<dt>scan age: Last full scan age &lt; &gt; (in days)</dt>
<dt>Antivirus signature creation time: ? &lt; 바이러스 백신 &gt; 서명 생성 시간</dt>스파이웨어 방지 서명
<dt>생성 시간: ? &lt; 스파이웨어 방지 서명 생성 &gt; 시간</dt>
<dt>마지막 빠른 검사 시작 시간: ? &lt; 마지막 빠른 검사 &gt; 시작 시간</dt>
<dt>마지막 빠른 검사 종료 시간: ? &lt; 마지막 빠른 검사 &gt; </dt>종료 시간 마지막 빠른 검사 원본: 마지막 빠른 검사 원본(0 =&#39;
<dt> &lt; &gt; 실행하지 않았음, 1 = 사용자가 시작한, 2 =</dt>시스템 시작) 마지막 전체 검사 시작
<dt>시간: ? &lt; 마지막 전체 검사 &gt; 시작 시간</dt>
<dt>마지막 전체 검사 종료 시간: ? &lt; 마지막 전체 검사 &gt; </dt>종료 시간 마지막 전체 검사 원본: 마지막 전체 검사 원본(0 =&#39;
<dt> &lt; &gt; 실행되지 않았음, 1 = 사용자가 시작한, 2 =</dt>시스템 시작) 제품 상태: 내부 문제 
<dt> 해결</span><span class="sxs-lookup"><span data-stu-id="c9697-662">
<dt>Platform Version: &lt;Current platform version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
<dt>Network Realtime Inspection engine version: &lt;Network Realtime Inspection engine version&gt;</dt>
<dt>Antivirus signature version: &lt;Antivirus signature version&gt;</dt>
<dt>Antispyware signature version: &lt;Antispyware signature version&gt;</dt>
<dt>Network Realtime Inspection signature version: &lt;Network Realtime Inspection signature version&gt;</dt>
<dt>RTP state: &lt;Realtime protection state&gt; (Enabled or Disabled)</dt>
<dt>OA state: &lt;On Access state&gt; (Enabled or Disabled)</dt>
<dt>IOAV state: &lt;IE Downloads and Outlook Express Attachments state&gt; (Enabled or Disabled)</dt>
<dt>BM state: &lt;Behavior Monitoring state&gt; (Enabled or Disabled)</dt>
<dt>Antivirus signature age: &lt;Antivirus signature age&gt; (in days)</dt>
<dt>Antispyware signature age: &lt;Antispyware signature age&gt; (in days)</dt>
<dt>Last quick scan age: &lt;Last quick scan age&gt; (in days)</dt>
<dt>Last full scan age: &lt;Last full scan age&gt; (in days)</dt>
<dt>Antivirus signature creation time: ?&lt;Antivirus signature creation time&gt;</dt>
<dt>Antispyware signature creation time: ?&lt;Antispyware signature creation time&gt;</dt>
<dt>Last quick scan start time: ?&lt;Last quick scan start time&gt;</dt>
<dt>Last quick scan end time: ?&lt;Last quick scan end time&gt;</dt>
<dt>Last quick scan source: &lt;Last quick scan source&gt; (0 = scan didn&#39;t run, 1 = user initiated, 2 = system initiated)</dt>
<dt>Last full scan start time: ?&lt;Last full scan start time&gt;</dt>
<dt>Last full scan end time: ?&lt;Last full scan end time&gt;</dt>
<dt>Last full scan source: &lt;Last full scan source&gt; (0 = scan didn&#39;t run, 1 = user initiated, 2 = system initiated)</dt>
<dt>Product status: For internal troubleshooting</span></span>
</dl>
</td>
</tr>

<tr><span data-ttu-id="c9697-663">
<th colspan="2">이벤트 ID: 2000</span><span class="sxs-lookup"><span data-stu-id="c9697-663">
<th colspan="2">Event ID: 2000</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-664">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-664">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-665">
<b>MALWAREPROTECTION_SIGNATURE_UPDATED </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-665">
<b>MALWAREPROTECTION_SIGNATURE_UPDATED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-666">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-666">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-667">
<b>맬웨어 방지 정의가 성공적으로 업데이트되었습니다. </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-667">
<b>The antimalware definitions updated successfully. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-668">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-668">Description:</span></span>
</td>
<td >
<span data-ttu-id="c9697-669">바이러스 백신 서명 버전이 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-669">Antivirus signature version has been updated.</span></span>
<dl><span data-ttu-id="c9697-670">
<dt>현재 서명 버전: &lt; 현재 서명 &gt; 버전 이전</dt>
<dt>서명 버전: 이전 서명 &lt; 버전 &gt; </dt>서명 
<dt> 유형: 서명 &lt; &gt; 유형, 예:</span><span class="sxs-lookup"><span data-stu-id="c9697-670">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Previous Signature Version: &lt;Previous signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="c9697-671">바이러스 검사</span><span class="sxs-lookup"><span data-stu-id="c9697-671">Antivirus</span></span></li>
<li><span data-ttu-id="c9697-672">스파이웨어 방지</span><span class="sxs-lookup"><span data-stu-id="c9697-672">Antispyware</span></span></li>
<li><span data-ttu-id="c9697-673">맬웨어 방지</span><span class="sxs-lookup"><span data-stu-id="c9697-673">Antimalware</span></span></li>
<li><span data-ttu-id="c9697-674">네트워크 검사 시스템</span><span class="sxs-lookup"><span data-stu-id="c9697-674">Network Inspection System</span></span></li>
</ul><span data-ttu-id="c9697-675">
</dt>
<dt>업데이트 유형: &lt; 업데이트 &gt; 유형( 전체 또는 델타)입니다.</dt> 
<dt>사용자: &lt; 도메인 &gt; \& lt; 사용자 &gt; </dt>
<dt>현재 엔진 버전: &lt; 현재 엔진 버전 &gt; </dt>이전 엔진
<dt>버전: 이전 엔진 &lt; 버전 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="c9697-675">
</dt>
<dt>Update Type: &lt;Update type&gt;, either Full or Delta.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Previous Engine Version: &lt;Previous engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-676">사용자 작업:</span><span class="sxs-lookup"><span data-stu-id="c9697-676">User action:</span></span>
</td>
<td >
<span data-ttu-id="c9697-677">필요한 작업은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-677">No action is necessary.</span></span> <span data-ttu-id="c9697-678">클라이언트 Microsoft Defender 바이러스 백신 정상 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-678">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="c9697-679">이 이벤트는 서명이 성공적으로 업데이트될 때 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-679">This event is reported when signatures are successfully updated.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-680">이벤트 ID: 2001</span><span class="sxs-lookup"><span data-stu-id="c9697-680">Event ID: 2001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-681">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-681">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-682">
<b>MALWAREPROTECTION_SIGNATURE_UPDATE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-682">
<b>MALWAREPROTECTION_SIGNATURE_UPDATE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-683">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-683">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-684">
<b>보안 인텔리전스 업데이트가 실패했습니다. </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-684">
<b>The security intelligence update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-685">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-685">Description:</span></span>
</td>
<td >
<span data-ttu-id="c9697-686">Microsoft Defender 바이러스 백신 서명을 업데이트하는 중 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-686">Microsoft Defender Antivirus has encountered an error trying to update signatures.</span></span>
<dl><span data-ttu-id="c9697-687">
<dt>새 보안 인텔리전스 버전: &lt; 새 버전 &gt; 번호 이전</dt>
<dt>보안 인텔리전스 버전: &lt; 이전 &gt; 버전</dt>업데이트 
<dt> 원본: 업데이트 &lt; &gt; 원본, 예:</span><span class="sxs-lookup"><span data-stu-id="c9697-687">
<dt>New security intelligence version: &lt;New version number&gt;</dt>
<dt>Previous security intelligence version: &lt;Previous version&gt;</dt>
<dt>Update Source: &lt;Update source&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="c9697-688">보안 인텔리전스 업데이트 폴더</span><span class="sxs-lookup"><span data-stu-id="c9697-688">Security intelligence update folder</span></span></li>
<li><span data-ttu-id="c9697-689">내부 보안 인텔리전스 업데이트 서버</span><span class="sxs-lookup"><span data-stu-id="c9697-689">Internal security intelligence update server</span></span></li>
<li><span data-ttu-id="c9697-690">Microsoft Update Server</span><span class="sxs-lookup"><span data-stu-id="c9697-690">Microsoft Update Server</span></span></li>
<li><span data-ttu-id="c9697-691">파일 공유</span><span class="sxs-lookup"><span data-stu-id="c9697-691">File share</span></span></li>
<li><span data-ttu-id="c9697-692">Microsoft 맬웨어 보호 센터(MMPC)</span><span class="sxs-lookup"><span data-stu-id="c9697-692">Microsoft Malware Protection Center (MMPC)</span></span></li>
</ul><span data-ttu-id="c9697-693">
</dt>
<dt>업데이트 단계: &lt; 업데이트 &gt; 단계, 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-693">
</dt>
<dt>Update Stage: &lt;Update stage&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="c9697-694">검색</span><span class="sxs-lookup"><span data-stu-id="c9697-694">Search</span></span></li>
<li><span data-ttu-id="c9697-695">다운로드</span><span class="sxs-lookup"><span data-stu-id="c9697-695">Download</span></span></li>
<li><span data-ttu-id="c9697-696">설치</span><span class="sxs-lookup"><span data-stu-id="c9697-696">Install</span></span></li>
</ul><span data-ttu-id="c9697-697">
</dt>
<dt>원본 경로: UNC(범용 명명 규칙)의 파일 공유 이름, WSUS(Windows Server Update Services)/Microsoft Update/ADL의 서버 이름입니다.</dt> 
<dt> 서명 유형: &lt; 서명 &gt; 유형, 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-697">
</dt>
<dt>Source Path: File share name for Universal Naming Convention (UNC), server name for Windows Server Update Services (WSUS)/Microsoft Update/ADL.</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="c9697-698">바이러스 검사</span><span class="sxs-lookup"><span data-stu-id="c9697-698">Antivirus</span></span></li>
<li><span data-ttu-id="c9697-699">스파이웨어 방지</span><span class="sxs-lookup"><span data-stu-id="c9697-699">Antispyware</span></span></li>
<li><span data-ttu-id="c9697-700">맬웨어 방지</span><span class="sxs-lookup"><span data-stu-id="c9697-700">Antimalware</span></span></li>
<li><span data-ttu-id="c9697-701">네트워크 검사 시스템</span><span class="sxs-lookup"><span data-stu-id="c9697-701">Network Inspection System</span></span></li>
</ul><span data-ttu-id="c9697-702">
</dt>
<dt>업데이트 유형: &lt; 업데이트 &gt; 유형( 전체 또는 델타)입니다.</dt> 
<dt>사용자: &lt; 도메인 &gt; \& lt; 사용자 &gt; </dt>
<dt>현재 엔진 버전: &lt; 현재 엔진 버전 &gt; </dt>이전
<dt> &lt; &gt; 엔진 버전: 이전 엔진</dt>버전 오류 코드: 오류 코드 위협 상태와 관련된 결과
<dt> &lt; &gt; 코드입니다. 표준 HRESULT 값입니다.</dt> 
<dt>오류 설명: &lt; 오류 설명 &gt; 오류에 대한 설명입니다.</dt>
</span><span class="sxs-lookup"><span data-stu-id="c9697-702">
</dt>
<dt>Update Type: &lt;Update type&gt;, either Full or Delta.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Previous Engine Version: &lt;Previous engine version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-703">사용자 작업:</span><span class="sxs-lookup"><span data-stu-id="c9697-703">User action:</span></span>
</td>
<td >
<span data-ttu-id="c9697-704">정의를 업데이트하는 데 문제가 있는 경우 이 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-704">This error occurs when there is a problem updating definitions.</span></span>
<span data-ttu-id="c9697-705">이 이벤트를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-705">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="c9697-706"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">정의를 업데이트하고</a> 끝점에서 직접 다시 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-706"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Update definitions</a> and force a rescan directly on the endpoint.</span></span></li>
<li><span data-ttu-id="c9697-707">이 오류에 대한 자세한 내용은 %Windir%\WindowsUpdate.log 파일의 항목을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-707">Review the entries in the %Windir%\WindowsUpdate.log file for more information about this error.</span></span></li>
<li><span data-ttu-id="c9697-708"><a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft 기술 지원</a>에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-708">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-709">이벤트 ID: 2002</span><span class="sxs-lookup"><span data-stu-id="c9697-709">Event ID: 2002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-710">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-710">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-711">
<b>MALWAREPROTECTION_ENGINE_UPDATED</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-711">
<b>MALWAREPROTECTION_ENGINE_UPDATED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-712">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-712">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-713">
<b>맬웨어 방지 엔진이 업데이트되었습니다. </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-713">
<b>The antimalware engine updated successfully. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-714">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-714">Description:</span></span>
</td>
<td >
<span data-ttu-id="c9697-715">Microsoft Defender 바이러스 백신 엔진 버전이 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-715">Microsoft Defender Antivirus engine version has been updated.</span></span>
<dl><span data-ttu-id="c9697-716">
<dt>현재 엔진 버전: &lt; 현재 엔진 &gt; 버전</dt>
<dt>이전 엔진 버전: 이전 엔진 &lt; 버전 &gt; </dt>엔진 유형: 엔진 유형, 맬웨어 방지 엔진 또는
<dt>네트워크 검사 시스템 &lt; &gt; 엔진.</dt> 
<dt>사용자: &lt; 도메인 &gt; \& lt; 사용자 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="c9697-716">
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Previous Engine Version: &lt;Previous engine version&gt;</dt>
<dt>Engine Type: &lt;Engine type&gt;, either antimalware engine or Network Inspection System engine.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-717">사용자 작업:</span><span class="sxs-lookup"><span data-stu-id="c9697-717">User action:</span></span>
</td>
<td >
<span data-ttu-id="c9697-718">필요한 작업은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-718">No action is necessary.</span></span> <span data-ttu-id="c9697-719">클라이언트 Microsoft Defender 바이러스 백신 정상 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-719">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="c9697-720">이 이벤트는 맬웨어 방지 엔진이 성공적으로 업데이트될 때 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-720">This event is reported when the antimalware engine is successfully updated.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-721">이벤트 ID: 2003</span><span class="sxs-lookup"><span data-stu-id="c9697-721">Event ID: 2003</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-722">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-722">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-723">
<b>MALWAREPROTECTION_ENGINE_UPDATE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-723">
<b>MALWAREPROTECTION_ENGINE_UPDATE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-724">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-724">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-725">
<b>맬웨어 방지 엔진 업데이트가 실패했습니다. </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-725">
<b>The antimalware engine update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-726">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-726">Description:</span></span>
</td>
<td >
<span data-ttu-id="c9697-727">Microsoft Defender 바이러스 백신 엔진을 업데이트하는 동안 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-727">Microsoft Defender Antivirus has encountered an error trying to update the engine.</span></span>
<dl><span data-ttu-id="c9697-728">
<dt>새 엔진 버전:</dt>이전 엔진 버전: 이전
<dt>엔진 &lt; 버전 &gt; </dt>
<dt>엔진 유형: 엔진 &lt; &gt; 유형, 맬웨어 방지</dt> 엔진 또는 네트워크 검사 시스템 엔진. 
<dt>사용자: &lt; 도메인 &gt; \& lt; 사용자 &gt; </dt>오류 코드: 오류 코드 위협
<dt> &lt; &gt; 상태와 관련된 결과 코드입니다. 표준 HRESULT 값입니다.</dt> 
<dt>오류 설명: &lt; 오류 설명 &gt; 오류에 대한 설명입니다.</dt>
</span><span class="sxs-lookup"><span data-stu-id="c9697-728">
<dt>New Engine Version:</dt>
<dt>Previous Engine Version: &lt;Previous engine version&gt;</dt>
<dt>Engine Type: &lt;Engine type&gt;, either antimalware engine or Network Inspection System engine.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-729">사용자 작업:</span><span class="sxs-lookup"><span data-stu-id="c9697-729">User action:</span></span>
</td>
<td >
<span data-ttu-id="c9697-730">클라이언트 Microsoft Defender 바이러스 백신 업데이트하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-730">The Microsoft Defender Antivirus client update failed.</span></span> <span data-ttu-id="c9697-731">이 이벤트는 클라이언트가 자체 업데이트에 실패할 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-731">This event occurs when the client fails to update itself.</span></span> <span data-ttu-id="c9697-732">이 이벤트는 일반적으로 업데이트 중에 네트워크 연결이 중단되어 발생하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-732">This event is usually due to an interruption in network connectivity during an update.</span></span>
<span data-ttu-id="c9697-733">이 이벤트를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-733">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="c9697-734"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">정의를 업데이트하고</a> 끝점에서 직접 다시 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-734"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Update definitions</a> and force a rescan directly on the endpoint.</span></span></li>
<li><span data-ttu-id="c9697-735"><a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft 기술 지원</a>에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-735">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-736">이벤트 ID: 2004</span><span class="sxs-lookup"><span data-stu-id="c9697-736">Event ID: 2004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-737">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-737">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-738">
<b>MALWAREPROTECTION_SIGNATURE_REVERSION</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-738">
<b>MALWAREPROTECTION_SIGNATURE_REVERSION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-739">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-739">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-740">
<b>맬웨어 방지 정의를 로드하는 데 문제가 발생했습니다. 맬웨어 방지 엔진이 마지막으로 알려진 정의 집합을 로드하려고 합니다.</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-740">
<b>There was a problem loading antimalware definitions. The antimalware engine will attempt to load the last-known good set of definitions.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-741">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-741">Description:</span></span>
</td>
<td >
<span data-ttu-id="c9697-742">Microsoft Defender 바이러스 백신 로드하는 중 오류가 발생하여 알려진 서명 집합으로 되돌리려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-742">Microsoft Defender Antivirus has encountered an error trying to load signatures and will attempt reverting back to a known-good set of signatures.</span></span>
<dl><span data-ttu-id="c9697-743">
<dt>서명 시도:</dt>오류 코드: 오류 코드 위협
<dt> &lt; &gt; 상태와 관련된 결과 코드입니다. 표준 HRESULT 값입니다.</dt> 
<dt>오류 설명: &lt; 오류 설명 &gt; 오류에 대한 설명입니다.</dt> 
<dt>서명 버전: &lt; 정의 &gt; 버전</dt>
<dt>엔진 버전: &lt; 맬웨어 &gt; </dt> 방지 엔진 버전
</span><span class="sxs-lookup"><span data-stu-id="c9697-743">
<dt>Signatures Attempted:</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-744">사용자 작업:</span><span class="sxs-lookup"><span data-stu-id="c9697-744">User action:</span></span>
</td>
<td >
<span data-ttu-id="c9697-745">Microsoft Defender 바이러스 백신 클라이언트가 최신 정의 파일을 다운로드하여 설치하려고 했지만 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-745">The Microsoft Defender Antivirus client attempted to download and install the latest definitions file and failed.</span></span> <span data-ttu-id="c9697-746">이 오류는 정의를 로드하는 동안 클라이언트에서 오류가 발생하거나 파일이 손상된 경우 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-746">This error can occur when the client encounters an error while trying to load the definitions, or if the file is corrupt.</span></span> <span data-ttu-id="c9697-747">Microsoft Defender 바이러스 백신 정의 집합으로 되돌리려 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-747">Microsoft Defender Antivirus will attempt to revert back to a known-good set of definitions.</span></span>
<span data-ttu-id="c9697-748">이 이벤트를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-748">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="c9697-749">컴퓨터를 다시 시작하고 다시 시도하십시오.</span><span class="sxs-lookup"><span data-stu-id="c9697-749">Restart the computer and try again.</span></span></li>
<li><span data-ttu-id="c9697-750">사이트 에서 최신 <a href="https://aka.ms/wdsi">정의를 Microsoft 보안 인텔리전스 다운로드합니다.</a></span><span class="sxs-lookup"><span data-stu-id="c9697-750">Download the latest definitions from the <a href="https://aka.ms/wdsi">Microsoft Security Intelligence site</a>.</span></span>
<span data-ttu-id="c9697-751">참고: 사이트에서 다운로드한 정의 파일의 크기는 60MB를 초과할 수 있으며 정의를 업데이트하기 위한 장기 솔루션으로 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-751">Note: The size of the definitions file downloaded from the site can exceed 60 MB and should not be used as a long-term solution for updating definitions.</span></span>
</li>
<li><span data-ttu-id="c9697-752"><a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft 기술 지원</a>에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-752">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-753">이벤트 ID: 2005</span><span class="sxs-lookup"><span data-stu-id="c9697-753">Event ID: 2005</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-754">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-754">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-755">
<b>MALWAREPROTECTION_ENGINE_UPDATE_PLATFORMOUTOFDATE</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-755">
<b>MALWAREPROTECTION_ENGINE_UPDATE_PLATFORMOUTOFDATE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-756">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-756">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-757">
<b>맬웨어 방지 플랫폼이 최신이기 때문에 맬웨어 방지 엔진이 로드되지 못했습니다. 맬웨어 방지 플랫폼은 마지막으로 알려진 맬웨어 방지 엔진을 로드하고 업데이트를 시도합니다.</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-757">
<b>The antimalware engine failed to load because the antimalware platform is out of date. The antimalware platform will load the last-known good antimalware engine and attempt to update.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-758">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-758">Description:</span></span>
</td>
<td >
<span data-ttu-id="c9697-759">Microsoft Defender 바이러스 백신 플랫폼 버전이 지원되지 않는 경우 맬웨어 방지 엔진을 로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-759">Microsoft Defender Antivirus could not load antimalware engine because current platform version is not supported.</span></span> <span data-ttu-id="c9697-760">Microsoft Defender 바이러스 백신 마지막으로 알려진 엔진으로 되돌아가면 플랫폼 업데이트가 시도됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-760">Microsoft Defender Antivirus will revert back to the last known-good engine and a platform update will be attempted.</span></span>
<dl><span data-ttu-id="c9697-761">
<dt>현재 플랫폼 버전: &lt; 현재 플랫폼 버전&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="c9697-761">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-762">이벤트 ID: 2006</span><span class="sxs-lookup"><span data-stu-id="c9697-762">Event ID: 2006</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-763">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-763">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-764">
<b>MALWAREPROTECTION_PLATFORM_UPDATE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-764">
<b>MALWAREPROTECTION_PLATFORM_UPDATE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-765">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-765">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-766">
<b>플랫폼 업데이트가 실패했습니다. </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-766">
<b>The platform update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-767">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-767">Description:</span></span>
</td>
<td >
<span data-ttu-id="c9697-768">Microsoft Defender 바이러스 백신 플랫폼을 업데이트하는 중 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-768">Microsoft Defender Antivirus has encountered an error trying to update the platform.</span></span>
<dl><span data-ttu-id="c9697-769">
<dt>현재 플랫폼 버전: &lt; 현재 플랫폼 &gt; 버전</dt>오류 코드: 오류 코드 위협
<dt> &lt; &gt; 상태와 관련된 결과 코드입니다. 표준 HRESULT 값입니다.</dt> 
<dt>오류 설명: &lt; 오류 설명 &gt; 오류에 대한 설명입니다.</dt>
</span><span class="sxs-lookup"><span data-stu-id="c9697-769">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-770">이벤트 ID: 2007</span><span class="sxs-lookup"><span data-stu-id="c9697-770">Event ID: 2007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-771">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-771">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-772">
<b>MALWAREPROTECTION_PLATFORM_ALMOSTOUTOFDATE</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-772">
<b>MALWAREPROTECTION_PLATFORM_ALMOSTOUTOFDATE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-773">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-773">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-774">
<b>플랫폼이 곧 최신이 됩니다. 최신 보호를 유지하기 위해 최신 플랫폼을 다운로드합니다.</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-774">
<b>The platform will soon be out of date. Download the latest platform to maintain up-to-date protection.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-775">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-775">Description:</span></span>
</td>
<td >
<span data-ttu-id="c9697-776">Microsoft Defender 바이러스 백신 맬웨어 방지 엔진의 이후 버전을 지원하려면 곧 최신 플랫폼 버전이 필요할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-776">Microsoft Defender Antivirus will soon require a newer platform version to support future versions of the antimalware engine.</span></span> <span data-ttu-id="c9697-777">최신 Microsoft Defender 바이러스 백신 플랫폼을 다운로드하여 사용 가능한 최상의 보호 수준을 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-777">Download the latest Microsoft Defender Antivirus platform to maintain the best level of protection available.</span></span>
<dl><span data-ttu-id="c9697-778">
<dt>현재 플랫폼 버전: &lt; 현재 플랫폼 버전&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="c9697-778">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-779">이벤트 ID: 2010</span><span class="sxs-lookup"><span data-stu-id="c9697-779">Event ID: 2010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-780">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-780">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-781">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATED </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-781">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-782">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-782">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-783">
<b>맬웨어 방지 엔진은 동적 서명 서비스를 사용하여 추가 정의를 얻습니다. </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-783">
<b>The antimalware engine used the Dynamic Signature Service to get additional definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-784">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-784">Description:</span></span>
</td>
<td >
<span data-ttu-id="c9697-785">Microsoft Defender 바이러스 백신 데 <i>도움이</i> 되는 추가 서명을 검색하는 데 동적 서명 서비스를 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-785">Microsoft Defender Antivirus used <i>Dynamic Signature Service</i> to retrieve additional signatures to help protect your machine.</span></span>
<dl><span data-ttu-id="c9697-786">
<dt>현재 서명 버전: &lt; 현재 서명 &gt; 버전</dt> 
<dt> 서명 유형: 서명 &lt; &gt; 유형, 예:</span><span class="sxs-lookup"><span data-stu-id="c9697-786">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="c9697-787">바이러스 검사</span><span class="sxs-lookup"><span data-stu-id="c9697-787">Antivirus</span></span></li>
<li><span data-ttu-id="c9697-788">스파이웨어 방지</span><span class="sxs-lookup"><span data-stu-id="c9697-788">Antispyware</span></span></li>
<li><span data-ttu-id="c9697-789">맬웨어 방지</span><span class="sxs-lookup"><span data-stu-id="c9697-789">Antimalware</span></span></li>
<li><span data-ttu-id="c9697-790">네트워크 검사 시스템</span><span class="sxs-lookup"><span data-stu-id="c9697-790">Network Inspection System</span></span></li>
</ul><span data-ttu-id="c9697-791">
</dt>
<dt>현재 엔진 버전: &lt; 현재 엔진 &gt; 버전</dt> 
<dt> 동적 서명 유형: 동적 서명 &lt; &gt; 유형, 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-791">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="c9697-792">Version</span><span class="sxs-lookup"><span data-stu-id="c9697-792">Version</span></span></li>
<li><span data-ttu-id="c9697-793">타임스탬프</span><span class="sxs-lookup"><span data-stu-id="c9697-793">Timestamp</span></span></li>
<li><span data-ttu-id="c9697-794">제한 없음</span><span class="sxs-lookup"><span data-stu-id="c9697-794">No limit</span></span></li>
<li><span data-ttu-id="c9697-795">기간</span><span class="sxs-lookup"><span data-stu-id="c9697-795">Duration</span></span></li>
</ul><span data-ttu-id="c9697-796">
</dt>
<dt>지속성 경로: &lt; 경로 &gt; </dt>
<dt>동적 서명 버전: &lt; 버전 번호 &gt; </dt>동적 서명 컴파일
<dt>타임스탬프: &lt; 타임스탬프 &gt; </dt> 
<dt> 지속성 제한 유형: &lt; 지속성 제한 &gt; 유형, 예:</span><span class="sxs-lookup"><span data-stu-id="c9697-796">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="c9697-797">VDM 버전</span><span class="sxs-lookup"><span data-stu-id="c9697-797">VDM version</span></span></li>
<li><span data-ttu-id="c9697-798">타임스탬프</span><span class="sxs-lookup"><span data-stu-id="c9697-798">Timestamp</span></span></li>
<li><span data-ttu-id="c9697-799">제한 없음</span><span class="sxs-lookup"><span data-stu-id="c9697-799">No limit</span></span></li>
</ul><span data-ttu-id="c9697-800">
</dt>
<dt>지속성 제한: fastpath 서명의 지속성 제한.</dt>
</span><span class="sxs-lookup"><span data-stu-id="c9697-800">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-801">이벤트 ID: 2011</span><span class="sxs-lookup"><span data-stu-id="c9697-801">Event ID: 2011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-802">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-802">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-803">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-803">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-804">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-804">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-805">
<b>동적 서명 서비스가 기한이 지난 동적 정의를 삭제했습니다. </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-805">
<b>The Dynamic Signature Service deleted the out-of-date dynamic definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-806">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-806">Description:</span></span>
</td>
<td >
<span data-ttu-id="c9697-807">Microsoft Defender 바이러스 백신 <i>서명을</i> 삭제하기 위해 동적 서명 서비스를 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-807">Microsoft Defender Antivirus used <i>Dynamic Signature Service</i> to discard obsolete signatures.</span></span>
<dl><span data-ttu-id="c9697-808">
<dt>현재 서명 버전: &lt; 현재 서명 &gt; 버전</dt> 
<dt> 서명 유형: 서명 &lt; &gt; 유형, 예:</span><span class="sxs-lookup"><span data-stu-id="c9697-808">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="c9697-809">바이러스 검사</span><span class="sxs-lookup"><span data-stu-id="c9697-809">Antivirus</span></span></li>
<li><span data-ttu-id="c9697-810">스파이웨어 방지</span><span class="sxs-lookup"><span data-stu-id="c9697-810">Antispyware</span></span></li>
<li><span data-ttu-id="c9697-811">맬웨어 방지</span><span class="sxs-lookup"><span data-stu-id="c9697-811">Antimalware</span></span></li>
<li><span data-ttu-id="c9697-812">네트워크 검사 시스템</span><span class="sxs-lookup"><span data-stu-id="c9697-812">Network Inspection System</span></span></li>
</ul><span data-ttu-id="c9697-813">
</dt>
<dt>현재 엔진 버전: &lt; 현재 엔진 &gt; 버전</dt> 
<dt> 동적 서명 유형: 동적 서명 &lt; &gt; 유형, 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-813">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="c9697-814">Version</span><span class="sxs-lookup"><span data-stu-id="c9697-814">Version</span></span></li>
<li><span data-ttu-id="c9697-815">타임스탬프</span><span class="sxs-lookup"><span data-stu-id="c9697-815">Timestamp</span></span></li>
<li><span data-ttu-id="c9697-816">제한 없음</span><span class="sxs-lookup"><span data-stu-id="c9697-816">No limit</span></span></li>
<li><span data-ttu-id="c9697-817">기간</span><span class="sxs-lookup"><span data-stu-id="c9697-817">Duration</span></span></li>
</ul><span data-ttu-id="c9697-818">
</dt>
<dt>지속성 경로: &lt; 경로 &gt; </dt>
<dt>동적 서명 버전: &lt; 버전 번호 &gt; </dt>동적 서명 컴파일
<dt>타임스탬프: &lt; 타임스탬프 &gt; </dt>제거
<dt>이유:</dt> 
<dt> 지속성 제한 유형: 지속성 제한 &lt; &gt; 유형, 예:</span><span class="sxs-lookup"><span data-stu-id="c9697-818">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Removal Reason:</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="c9697-819">VDM 버전</span><span class="sxs-lookup"><span data-stu-id="c9697-819">VDM version</span></span></li>
<li><span data-ttu-id="c9697-820">타임스탬프</span><span class="sxs-lookup"><span data-stu-id="c9697-820">Timestamp</span></span></li>
<li><span data-ttu-id="c9697-821">제한 없음</span><span class="sxs-lookup"><span data-stu-id="c9697-821">No limit</span></span></li>
</ul><span data-ttu-id="c9697-822">
</dt>
<dt>지속성 제한: fastpath 서명의 지속성 제한.</dt>
</span><span class="sxs-lookup"><span data-stu-id="c9697-822">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-823">사용자 작업:</span><span class="sxs-lookup"><span data-stu-id="c9697-823">User action:</span></span>
</td>
<td >
<span data-ttu-id="c9697-824">필요한 작업은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-824">No action is necessary.</span></span> <span data-ttu-id="c9697-825">클라이언트 Microsoft Defender 바이러스 백신 정상 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-825">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="c9697-826">이 이벤트는 동적 서명 서비스가 기한이 지난 동적 정의를 성공적으로 삭제할 때 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-826">This event is reported when the Dynamic Signature Service successfully deletes out-of-date dynamic definitions.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-827">이벤트 ID: 2012</span><span class="sxs-lookup"><span data-stu-id="c9697-827">Event ID: 2012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-828">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-828">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-829">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-829">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-830">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-830">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-831">
<b>동적 서명 서비스를 사용하려고 할 때 맬웨어 방지 엔진에서 오류가 발생했습니다. </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-831">
<b>The antimalware engine encountered an error when trying to use the Dynamic Signature Service. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-832">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-832">Description:</span></span>
</td>
<td >
<span data-ttu-id="c9697-833">Microsoft Defender 바이러스 백신 서명 서비스를 사용하려고 하는 중 오류가 <i>발생했습니다.</i></span><span class="sxs-lookup"><span data-stu-id="c9697-833">Microsoft Defender Antivirus has encountered an error trying to use <i>Dynamic Signature Service</i>.</span></span>
<dl><span data-ttu-id="c9697-834">
<dt>현재 서명 버전: &lt; 현재 서명 &gt; 버전</dt> 
<dt> 서명 유형: 서명 &lt; &gt; 유형, 예:</span><span class="sxs-lookup"><span data-stu-id="c9697-834">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="c9697-835">바이러스 검사</span><span class="sxs-lookup"><span data-stu-id="c9697-835">Antivirus</span></span></li>
<li><span data-ttu-id="c9697-836">스파이웨어 방지</span><span class="sxs-lookup"><span data-stu-id="c9697-836">Antispyware</span></span></li>
<li><span data-ttu-id="c9697-837">맬웨어 방지</span><span class="sxs-lookup"><span data-stu-id="c9697-837">Antimalware</span></span></li>
<li><span data-ttu-id="c9697-838">네트워크 검사 시스템</span><span class="sxs-lookup"><span data-stu-id="c9697-838">Network Inspection System</span></span></li>
</ul><span data-ttu-id="c9697-839">
</dt>
<dt>현재 엔진 버전: &lt; 현재 엔진 &gt; 버전</dt>오류 코드: 오류 코드 위협
<dt> &lt; &gt; 상태와 관련된 결과 코드입니다. 표준 HRESULT 값입니다.</dt> 
<dt>오류 설명: &lt; 오류 설명 &gt; 오류에 대한 설명입니다.</dt> 
<dt> 동적 서명 유형: &lt; 동적 서명 &gt; 유형, 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-839">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="c9697-840">Version</span><span class="sxs-lookup"><span data-stu-id="c9697-840">Version</span></span></li>
<li><span data-ttu-id="c9697-841">타임스탬프</span><span class="sxs-lookup"><span data-stu-id="c9697-841">Timestamp</span></span></li>
<li><span data-ttu-id="c9697-842">제한 없음</span><span class="sxs-lookup"><span data-stu-id="c9697-842">No limit</span></span></li>
<li><span data-ttu-id="c9697-843">기간</span><span class="sxs-lookup"><span data-stu-id="c9697-843">Duration</span></span></li>
</ul><span data-ttu-id="c9697-844">
</dt>
<dt>지속성 경로: &lt; 경로 &gt; </dt>
<dt>동적 서명 버전: &lt; 버전 번호 &gt; </dt>동적 서명 컴파일
<dt>타임스탬프: &lt; 타임스탬프 &gt; </dt> 
<dt> 지속성 제한 유형: &lt; 지속성 제한 &gt; 유형, 예:</span><span class="sxs-lookup"><span data-stu-id="c9697-844">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="c9697-845">VDM 버전</span><span class="sxs-lookup"><span data-stu-id="c9697-845">VDM version</span></span></li>
<li><span data-ttu-id="c9697-846">타임스탬프</span><span class="sxs-lookup"><span data-stu-id="c9697-846">Timestamp</span></span></li>
<li><span data-ttu-id="c9697-847">제한 없음</span><span class="sxs-lookup"><span data-stu-id="c9697-847">No limit</span></span></li>
</ul><span data-ttu-id="c9697-848">
</dt>
<dt>지속성 제한: fastpath 서명의 지속성 제한.</dt>
</span><span class="sxs-lookup"><span data-stu-id="c9697-848">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-849">사용자 작업:</span><span class="sxs-lookup"><span data-stu-id="c9697-849">User action:</span></span>
</td>
<td >
<span data-ttu-id="c9697-850">인터넷 연결 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-850">Check your Internet connectivity settings.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-851">이벤트 ID: 2013</span><span class="sxs-lookup"><span data-stu-id="c9697-851">Event ID: 2013</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-852">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-852">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-853">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED_ALL </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-853">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED_ALL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-854">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-854">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-855">
<b>동적 서명 서비스가 모든 동적 정의를 삭제했습니다. </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-855">
<b>The Dynamic Signature Service deleted all dynamic definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-856">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-856">Description:</span></span>
</td>
<td >
<span data-ttu-id="c9697-857">Microsoft Defender 바이러스 백신 서명을 모두 <i>삭제해야</i> 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-857">Microsoft Defender Antivirus discarded all <i>Dynamic Signature Service</i> signatures.</span></span>
<dl><span data-ttu-id="c9697-858">
<dt>현재 서명 버전: &lt; 현재 서명 버전&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="c9697-858">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-859">이벤트 ID: 2020</span><span class="sxs-lookup"><span data-stu-id="c9697-859">Event ID: 2020</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-860">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-860">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-861">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOADED </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-861">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOADED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-862">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-862">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-863">
<b>맬웨어 방지 엔진이 클린 파일을 다운로드했습니다. </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-863">
<b>The antimalware engine downloaded a clean file. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-864">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-864">Description:</span></span>
</td>
<td >
<span data-ttu-id="c9697-865">Microsoft Defender 바이러스 백신 파일을 다운로드했습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-865">Microsoft Defender Antivirus downloaded a clean file.</span></span>
<dl><span data-ttu-id="c9697-866">
<dt>파일 이름: &lt; 파일 이름 &gt; 파일의 이름입니다.</dt> 
<dt>현재 서명 버전: &lt; 현재 서명 &gt; 버전</dt>
<dt>현재 엔진 버전: 현재 엔진 &lt; 버전 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="c9697-866">
<dt>Filename: &lt;File name&gt; Name of the file.</dt>
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-867">이벤트 ID: 2021</span><span class="sxs-lookup"><span data-stu-id="c9697-867">Event ID: 2021</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-868">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-868">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-869">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOAD_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-869">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOAD_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-870">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-870">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-871">
<b>맬웨어 방지 엔진이 클린 파일을 다운로드하지 못했습니다. </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-871">
<b>The antimalware engine failed to download a clean file. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-872">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-872">Description:</span></span>
</td>
<td >
<span data-ttu-id="c9697-873">Microsoft Defender 바이러스 백신 파일을 다운로드하는 동안 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-873">Microsoft Defender Antivirus has encountered an error trying to download a clean file.</span></span>
<dl><span data-ttu-id="c9697-874">
<dt>파일 이름: &lt; 파일 이름 &gt; 파일의 이름입니다.</dt> 
<dt>현재 서명 버전: &lt; 현재 서명 &gt; 버전</dt>
<dt>현재 엔진 버전: 현재 엔진 &lt; 버전 &gt; </dt>오류 코드: 오류 코드 위협 상태와 관련된 결과
<dt> &lt; &gt; 코드입니다. 표준 HRESULT 값입니다.</dt> 
<dt>오류 설명: &lt; 오류 설명 &gt; 오류에 대한 설명입니다.</dt>
</span><span class="sxs-lookup"><span data-stu-id="c9697-874">
<dt>Filename: &lt;File name&gt; Name of the file.</dt>
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-875">사용자 작업:</span><span class="sxs-lookup"><span data-stu-id="c9697-875">User action:</span></span>
</td>
<td >
<span data-ttu-id="c9697-876">인터넷 연결 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-876">Check your Internet connectivity settings.</span></span>
<span data-ttu-id="c9697-877">이 Microsoft Defender 바이러스 백신 동적 서명 서비스를 사용하여 특정 위협에 최신 정의를 다운로드할 때 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-877">The Microsoft Defender Antivirus client encountered an error when using the Dynamic Signature Service to download the latest definitions to a specific threat.</span></span> <span data-ttu-id="c9697-878">이 오류는 네트워크 연결 문제로 인해 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-878">This error is likely caused by a network connectivity issue.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-879">이벤트 ID: 2030</span><span class="sxs-lookup"><span data-stu-id="c9697-879">Event ID: 2030</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-880">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-880">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-881">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALLED</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-881">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-882">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-882">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-883">
<b>맬웨어 방지 엔진이 다운로드된 후 다음 시스템 다시 시작 시 오프라인으로 실행하도록 구성됩니다.</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-883">
<b>The antimalware engine was downloaded and is configured to run offline on the next system restart.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-884">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-884">Description:</span></span>
</td>
<td >
<span data-ttu-id="c9697-885">Microsoft Defender 바이러스 백신 다시 시작 시 실행될 오프라인 바이러스 백신을 다운로드하고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-885">Microsoft Defender Antivirus downloaded and configured offline antivirus to run on the next reboot.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-886">이벤트 ID: 2031</span><span class="sxs-lookup"><span data-stu-id="c9697-886">Event ID: 2031</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-887">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-887">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-888">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALL_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-888">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALL_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-889">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-889">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-890">
<b>맬웨어 방지 엔진이 오프라인 검색을 다운로드하고 구성할 수 없습니다.</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-890">
<b>The antimalware engine was unable to download and configure an offline scan.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-891">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-891">Description:</span></span>
</td>
<td >
<span data-ttu-id="c9697-892">Microsoft Defender 바이러스 백신 바이러스 백신을 다운로드하고 구성하는 동안 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-892">Microsoft Defender Antivirus has encountered an error trying to download and configure offline antivirus.</span></span>
<dl><span data-ttu-id="c9697-893">
<dt>오류 코드: &lt; 오류 코드 &gt; 위협 상태와 관련된 결과 코드입니다. 표준 HRESULT 값입니다.</dt> 
<dt>오류 설명: &lt; 오류 설명 &gt; 오류에 대한 설명입니다.</dt>
</span><span class="sxs-lookup"><span data-stu-id="c9697-893">
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-894">이벤트 ID: 2040</span><span class="sxs-lookup"><span data-stu-id="c9697-894">Event ID: 2040</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-895">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-895">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-896">
<b>MALWAREPROTECTION_OS_EXPIRING </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-896">
<b>MALWAREPROTECTION_OS_EXPIRING </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-897">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-897">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-898">
<b>이 운영 체제 버전에 대한 맬웨어 방지 지원이 곧 종료됩니다. </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-898">
<b>Antimalware support for this operating system version will soon end. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-899">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-899">Description:</span></span>
</td>
<td >
<span data-ttu-id="c9697-900">운영 체제에 대한 지원이 곧 만료됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-900">The support for your operating system will expire shortly.</span></span> <span data-ttu-id="c9697-901">지원 Microsoft Defender 바이러스 백신 운영 체제에서 데이터를 실행하는 것은 위협으로부터 보호하기에 적절한 솔루션이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-901">Running Microsoft Defender Antivirus on an out of support operating system is not an adequate solution to protect against threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-902">이벤트 ID: 2041</span><span class="sxs-lookup"><span data-stu-id="c9697-902">Event ID: 2041</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-903">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-903">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-904">
<b>MALWAREPROTECTION_OS_EOL </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-904">
<b>MALWAREPROTECTION_OS_EOL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-905">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-905">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-906">
<b>이 운영 체제에 대한 맬웨어 방지 지원이 종료됩니다. 지원을 계속하려면 운영 체제를 업그레이드해야 합니다. </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-906">
<b>Antimalware support for this operating system has ended. You must upgrade the operating system for continued support. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-907">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-907">Description:</span></span>
</td>
<td >
<span data-ttu-id="c9697-908">운영 체제에 대한 지원이 만료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-908">The support for your operating system has expired.</span></span> <span data-ttu-id="c9697-909">지원 Microsoft Defender 바이러스 백신 운영 체제에서 데이터를 실행하는 것은 위협으로부터 보호하기에 적절한 솔루션이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-909">Running Microsoft Defender Antivirus on an out of support operating system is not an adequate solution to protect against threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-910">이벤트 ID: 2042</span><span class="sxs-lookup"><span data-stu-id="c9697-910">Event ID: 2042</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-911">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-911">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-912">
<b>MALWAREPROTECTION_PROTECTION_EOL </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-912">
<b>MALWAREPROTECTION_PROTECTION_EOL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-913">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-913">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-914">
<b>맬웨어 방지 엔진은 더 이상 이 운영 체제를 지원하지하며 더 이상 맬웨어로부터 시스템을 보호하지 않습니다. </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-914">
<b>The antimalware engine no longer supports this operating system, and is no longer protecting your system from malware. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-915">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-915">Description:</span></span>
</td>
<td >
<span data-ttu-id="c9697-916">운영 체제에 대한 지원이 만료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-916">The support for your operating system has expired.</span></span> <span data-ttu-id="c9697-917">Microsoft Defender 바이러스 백신 운영 체제에서 더 이상 지원되지 않는 경우, 작동이 중지되어 맬웨어 위협으로부터 보호되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-917">Microsoft Defender Antivirus is no longer supported on your operating system, has stopped functioning, and is not protecting against malware threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-918">이벤트 ID: 3002</span><span class="sxs-lookup"><span data-stu-id="c9697-918">Event ID: 3002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-919">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-919">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-920">
<b>MALWAREPROTECTION_RTP_FEATURE_FAILURE </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-920">
<b>MALWAREPROTECTION_RTP_FEATURE_FAILURE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-921">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-921">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-922">
<b>실시간 보호에 오류가 발생하여 오류가 발생했습니다.</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-922">
<b>Real-time protection encountered an error and failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-923">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-923">Description:</span></span>
</td>
<td >
<span data-ttu-id="c9697-924">Microsoft Defender 바이러스 백신 Real-Time 보호 기능에 오류가 발생하여 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-924">Microsoft Defender Antivirus Real-Time Protection feature has encountered an error and failed.</span></span>
<dl><span data-ttu-id="c9697-925">
<dt>기능: &lt; &gt; 기능, 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-925">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="c9697-926">On Access</span><span class="sxs-lookup"><span data-stu-id="c9697-926">On Access</span></span></li>
<li><span data-ttu-id="c9697-927">Internet Explorer 다운로드 및 Microsoft Outlook Express 첨부 파일</span><span class="sxs-lookup"><span data-stu-id="c9697-927">Internet Explorer downloads and Microsoft Outlook Express attachments</span></span></li>
<li><span data-ttu-id="c9697-928">동작 모니터링</span><span class="sxs-lookup"><span data-stu-id="c9697-928">Behavior monitoring</span></span></li>
<li><span data-ttu-id="c9697-929">네트워크 검사 시스템</span><span class="sxs-lookup"><span data-stu-id="c9697-929">Network Inspection System</span></span></li>
</ul><span data-ttu-id="c9697-930">
</dt>
<dt>오류 코드: &lt; 오류 코드 &gt; 위협 상태와 관련된 결과 코드입니다. 표준 HRESULT 값입니다.</dt> 
<dt>오류 설명: &lt; 오류 설명 &gt; 오류에 대한 설명입니다.</dt> 
<dt>이유: 실시간 Microsoft Defender 바이러스 백신 기능이 다시 시작된 이유입니다.</dt>
</span><span class="sxs-lookup"><span data-stu-id="c9697-930">
</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Reason: The reason Microsoft Defender Antivirus real-time protection has restarted a feature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-931">사용자 작업:</span><span class="sxs-lookup"><span data-stu-id="c9697-931">User action:</span></span>
</td>
<td >
<span data-ttu-id="c9697-932">시스템을 다시 시작한 다음 전체&#39;보호되지 않을 수 있기 때문에 전체 검색을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-932">You should restart the system then run a full scan because it&#39;s possible the system was not protected for some time.</span></span>
<span data-ttu-id="c9697-933">이 Microsoft Defender 바이러스 백신 서비스&#39;시작하지 못했기 때문에 실시간 보호 기능을 사용할 때 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-933">The Microsoft Defender Antivirus client&#39;s real-time protection feature encountered an error because one of the services failed to start.</span></span> <span data-ttu-id="c9697-934">그 다음에 3007 이벤트 ID가 발생하면 오류가 일시적으로 발생하고 맬웨어 방지 클라이언트가 오류에서 복구됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-934">If it is followed by a 3007 event ID, the failure was temporary and the antimalware client recovered from the failure.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-935">이벤트 ID: 3007</span><span class="sxs-lookup"><span data-stu-id="c9697-935">Event ID: 3007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-936">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-936">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-937">
<b>MALWAREPROTECTION_RTP_FEATURE_RECOVERED</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-937">
<b>MALWAREPROTECTION_RTP_FEATURE_RECOVERED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-938">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-938">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-939">
<b>오류로부터 실시간 보호를 복구했습니다. 이 오류가 표시되는 경우 전체 시스템 검색을 실행하는 것이 좋습니다. </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-939">
<b>Real-time protection recovered from a failure. We recommend running a full system scan when you see this error. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-940">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-940">Description:</span></span>
</td>
<td >
<span data-ttu-id="c9697-941">Microsoft Defender 바이러스 백신 실시간 보호가 기능을 다시 시작했습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-941">Microsoft Defender Antivirus Real-time Protection has restarted a feature.</span></span> <span data-ttu-id="c9697-942">전체 시스템 검색을 실행하여 이 에이전트가 다운된 동안 누락된 항목을 검색하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-942">It is recommended that you run a full system scan to detect any items that may have been missed while this agent was down.</span></span>
<dl><span data-ttu-id="c9697-943">
<dt>기능: &lt; &gt; 기능, 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-943">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="c9697-944">On Access</span><span class="sxs-lookup"><span data-stu-id="c9697-944">On Access</span></span></li>
<li><span data-ttu-id="c9697-945">IE 다운로드 및 Outlook Express 첨부 파일</span><span class="sxs-lookup"><span data-stu-id="c9697-945">IE downloads and Outlook Express attachments</span></span></li>
<li><span data-ttu-id="c9697-946">동작 모니터링</span><span class="sxs-lookup"><span data-stu-id="c9697-946">Behavior monitoring</span></span></li>
<li><span data-ttu-id="c9697-947">네트워크 검사 시스템</span><span class="sxs-lookup"><span data-stu-id="c9697-947">Network Inspection System</span></span></li>
</ul><span data-ttu-id="c9697-948">
</dt>
<dt>이유: 실시간 Microsoft Defender 바이러스 백신 기능이 다시 시작된 이유입니다.</dt>
</span><span class="sxs-lookup"><span data-stu-id="c9697-948">
</dt>
<dt>Reason: The reason Microsoft Defender Antivirus real-time protection has restarted a feature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-949">사용자 작업:</span><span class="sxs-lookup"><span data-stu-id="c9697-949">User action:</span></span>
</td>
<td >
<span data-ttu-id="c9697-950">실시간 보호 기능이 다시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-950">The real-time protection feature has restarted.</span></span> <span data-ttu-id="c9697-951">이 이벤트가 다시 발생하면 <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft 기술 지원에 문의하세요.</a></span><span class="sxs-lookup"><span data-stu-id="c9697-951">If this event happens again, contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-952">이벤트 ID: 5000</span><span class="sxs-lookup"><span data-stu-id="c9697-952">Event ID: 5000</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-953">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-953">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-954">
<b>MALWAREPROTECTION_RTP_ENABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-954">
<b>MALWAREPROTECTION_RTP_ENABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-955">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-955">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-956">
<b>실시간 보호가 사용됩니다. </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-956">
<b>Real-time protection is enabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-957">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-957">Description:</span></span>
</td>
<td >
<span data-ttu-id="c9697-958">Microsoft Defender 바이러스 백신 사용자 없이 설치될 수 있는 기타 소프트웨어에 대한 실시간 보호 검사가 사용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-958">Microsoft Defender Antivirus real-time protection scanning for malware and other potentially unwanted software was enabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-959">이벤트 ID: 5001</span><span class="sxs-lookup"><span data-stu-id="c9697-959">Event ID: 5001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-960">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-960">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-961">
<b>MALWAREPROTECTION_RTP_DISABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-961">
<b>MALWAREPROTECTION_RTP_DISABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-962">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-962">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-963">
<b>실시간 보호가 사용되지 않습니다. </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-963">
<b>Real-time protection is disabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-964">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-964">Description:</span></span>
</td>
<td >
<span data-ttu-id="c9697-965">Microsoft Defender 바이러스 백신 사용자 없이 설치될 수 있는 기타 소프트웨어에 대한 실시간 보호 검사가 사용되지 않도록 설정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-965">Microsoft Defender Antivirus real-time protection scanning for malware and other potentially unwanted software was disabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-966">이벤트 ID: 5004</span><span class="sxs-lookup"><span data-stu-id="c9697-966">Event ID: 5004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-967">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-967">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-968">
<b>MALWAREPROTECTION_RTP_FEATURE_CONFIGURED </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-968">
<b>MALWAREPROTECTION_RTP_FEATURE_CONFIGURED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-969">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-969">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-970">
<b>실시간 보호 구성이 변경되었습니다. </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-970">
<b>The real-time protection configuration changed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-971">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-971">Description:</span></span>
</td>
<td >
<span data-ttu-id="c9697-972">Microsoft Defender 바이러스 백신 실시간 보호 기능 구성이 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-972">Microsoft Defender Antivirus real-time protection feature configuration has changed.</span></span>
<dl><span data-ttu-id="c9697-973">
<dt>기능: &lt; &gt; 기능, 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-973">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="c9697-974">On Access</span><span class="sxs-lookup"><span data-stu-id="c9697-974">On Access</span></span></li>
<li><span data-ttu-id="c9697-975">IE 다운로드 및 Outlook Express 첨부 파일</span><span class="sxs-lookup"><span data-stu-id="c9697-975">IE downloads and Outlook Express attachments</span></span></li>
<li><span data-ttu-id="c9697-976">동작 모니터링</span><span class="sxs-lookup"><span data-stu-id="c9697-976">Behavior monitoring</span></span></li>
<li><span data-ttu-id="c9697-977">네트워크 검사 시스템</span><span class="sxs-lookup"><span data-stu-id="c9697-977">Network Inspection System</span></span></li>
</ul><span data-ttu-id="c9697-978">
</dt>
<dt>구성: </dt>
</span><span class="sxs-lookup"><span data-stu-id="c9697-978">
</dt>
<dt>Configuration: </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-979">이벤트 ID: 5007</span><span class="sxs-lookup"><span data-stu-id="c9697-979">Event ID: 5007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-980">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-980">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-981">
<b>MALWAREPROTECTION_CONFIG_CHANGED </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-981">
<b>MALWAREPROTECTION_CONFIG_CHANGED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-982">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-982">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-983">
<b>맬웨어 방지 플랫폼 구성이 변경되었습니다.</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-983">
<b>The antimalware platform configuration changed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-984">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-984">Description:</span></span>
</td>
<td >
<span data-ttu-id="c9697-985">Microsoft Defender 바이러스 백신 구성이 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-985">Microsoft Defender Antivirus configuration has changed.</span></span> <span data-ttu-id="c9697-986">이 이벤트가 예기치 않은 이벤트인 경우 맬웨어의 결과일 수 있는 설정을 검토해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-986">If this is an unexpected event, you should review the settings as this may be the result of malware.</span></span>
<dl><span data-ttu-id="c9697-987">
<dt>이전 값: &lt; 이전 값 번호 &gt; 이전 바이러스 백신 구성 값입니다.</dt> 
<dt>새 값: &lt; 새 값 번호 &gt; 새 바이러스 백신 구성 값입니다.</dt>
</span><span class="sxs-lookup"><span data-stu-id="c9697-987">
<dt>Old value: &lt;Old value number&gt; Old antivirus configuration value.</dt>
<dt>New value: &lt;New value number&gt; New antivirus configuration value.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-988">이벤트 ID: 5008</span><span class="sxs-lookup"><span data-stu-id="c9697-988">Event ID: 5008</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-989">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-989">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-990">
<b>MALWAREPROTECTION_ENGINE_FAILURE</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-990">
<b>MALWAREPROTECTION_ENGINE_FAILURE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-991">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-991">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-992">
<b>맬웨어 방지 엔진에서 오류가 발생하여 오류가 발생했습니다.</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-992">
<b>The antimalware engine encountered an error and failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-993">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-993">Description:</span></span>
</td>
<td >
<span data-ttu-id="c9697-994">Microsoft Defender 바이러스 백신 오류로 인해 엔진이 종료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-994">Microsoft Defender Antivirus engine has been terminated due to an unexpected error.</span></span>
<dl><span data-ttu-id="c9697-995">
<dt>오류 유형: &lt; 오류 &gt; 유형, 예: 크래시 또는</dt>중단 예외
<dt>코드: 오류 &lt; 코드 &gt; </dt>
<dt>리소스: &lt; 리소스 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="c9697-995">
<dt>Failure Type: &lt;Failure type&gt;, for example: Crash or Hang</dt>
<dt>Exception Code: &lt;Error code&gt;</dt>
<dt>Resource: &lt;Resource&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-996">사용자 작업:</span><span class="sxs-lookup"><span data-stu-id="c9697-996">User action:</span></span>
</td>
<td >
<span data-ttu-id="c9697-997">이 이벤트를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-997">To troubleshoot this event:</span></span><ol>
<li><span data-ttu-id="c9697-998">서비스를 다시 시작하십시오.</span><span class="sxs-lookup"><span data-stu-id="c9697-998">Try to restart the service.</span></span><ul>
<li><span data-ttu-id="c9697-999">맬웨어 방지, 바이러스 백신 및 스파이웨어의 경우 상승된 명령 프롬프트에 <b>net stop msmpsvc를</b>입력한 다음 <b>net start msmpsvc를</b> 입력하여 맬웨어 방지 엔진을 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-999">For antimalware, antivirus and spyware, at an elevated command prompt, type <b>net stop msmpsvc</b>, and then type <b>net start msmpsvc</b> to restart the antimalware engine.</span></span></li>
<li><span data-ttu-id="c9697-1000">네트워크 <i></i>검사 시스템의 경우 승격된 명령 프롬프트에 <b>net start nissrv를</b>입력한 다음 <i></i> <b>net start nissrv를</b> 입력하여 네트워크 검사 시스템 엔진을 다시 NiSSRV.exe.</span><span class="sxs-lookup"><span data-stu-id="c9697-1000">For the <i>Network Inspection System</i>, at an elevated command prompt, type <b>net start nissrv</b>, and then type <b>net start nissrv</b> to restart the <i>Network Inspection System</i> engine by using the NiSSRV.exe file.</span></span>
</li>
</ul>
</li>
<li><span data-ttu-id="c9697-1001">같은 방식으로 오류가 발생하면 <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft</a> 지원 사이트에 액세스하고 검색 상자에 오류 번호를 입력하여 오류 코드를 찾아 Microsoft 기술 지원 에 <a href="https://go.microsoft.com/fwlink/?LinkId=215491">문의하세요.</a> <b></b></span><span class="sxs-lookup"><span data-stu-id="c9697-1001">If it fails in the same way, look up the error code by accessing the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support Site</a>  and entering the error number in the <b>Search</b> box, and contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span></li>
</ol>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-1002">사용자 작업:</span><span class="sxs-lookup"><span data-stu-id="c9697-1002">User action:</span></span>
</td>
<td >
<span data-ttu-id="c9697-1003">예기치 Microsoft Defender 바이러스 백신 때문에 클라이언트 엔진이 중지되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-1003">The Microsoft Defender Antivirus client engine stopped due to an unexpected error.</span></span>
<span data-ttu-id="c9697-1004">이 이벤트를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-1004">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="c9697-1005">검색을 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-1005">Run the scan again.</span></span></li>
<li><span data-ttu-id="c9697-1006">같은 방식으로 오류가 발생하면 <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft</a>지원 사이트로 이동하여 검색 상자에 오류 번호를 입력하여 오류 코드를 찾아야 합니다. <b></b></span><span class="sxs-lookup"><span data-stu-id="c9697-1006">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="c9697-1007"><a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft 기술 지원</a>에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-1007">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-1008">이벤트 ID: 5009</span><span class="sxs-lookup"><span data-stu-id="c9697-1008">Event ID: 5009</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-1009">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-1009">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-1010">
<b>MALWAREPROTECTION_ANTISPYWARE_ENABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1010">
<b>MALWAREPROTECTION_ANTISPYWARE_ENABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-1011">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-1011">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-1012">
<b>맬웨어 및 사용자 원치 않는 기타 소프트웨어에 대한 검사가 사용하도록 설정되어 있습니다. </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1012">
<b>Scanning for malware and other potentially unwanted software is enabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-1013">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-1013">Description:</span></span>
</td>
<td >
<span data-ttu-id="c9697-1014">Microsoft Defender 바이러스 백신 소프트웨어 및 사용자 원치 않는 기타 소프트웨어에 대한 검색이 활성화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-1014">Microsoft Defender Antivirus scanning for malware and other potentially unwanted software has been enabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-1015">이벤트 ID: 5010</span><span class="sxs-lookup"><span data-stu-id="c9697-1015">Event ID: 5010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-1016">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-1016">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-1017">
<b>MALWAREPROTECTION_ANTISPYWARE_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1017">
<b>MALWAREPROTECTION_ANTISPYWARE_DISABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-1018">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-1018">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-1019">
<b>맬웨어 및 사용자 원치 않는 기타 소프트웨어에 대한 검사가 사용되지 않도록 설정되었습니다.</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1019">
<b>Scanning for malware and other potentially unwanted software is disabled.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-1020">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-1020">Description:</span></span>
</td>
<td >
<span data-ttu-id="c9697-1021">Microsoft Defender 바이러스 백신 소프트웨어 및 사용자 원치 않는 기타 소프트웨어에 대한 검색이 사용되지 않도록 설정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-1021">Microsoft Defender Antivirus scanning for malware and other potentially unwanted software is disabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-1022">이벤트 ID: 5011</span><span class="sxs-lookup"><span data-stu-id="c9697-1022">Event ID: 5011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-1023">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-1023">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-1024">
<b>MALWAREPROTECTION_ANTIVIRUS_ENABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1024">
<b>MALWAREPROTECTION_ANTIVIRUS_ENABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-1025">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-1025">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-1026">
<b>바이러스 검사가 사용하도록 설정되어 있습니다.</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1026">
<b>Scanning for viruses is enabled.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-1027">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-1027">Description:</span></span>
</td>
<td >
<span data-ttu-id="c9697-1028">Microsoft Defender 바이러스 백신 검사가 사용하도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-1028">Microsoft Defender Antivirus scanning for viruses has been enabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-1029">이벤트 ID: 5012</span><span class="sxs-lookup"><span data-stu-id="c9697-1029">Event ID: 5012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-1030">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-1030">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-1031">
<b>MALWAREPROTECTION_ANTIVIRUS_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1031">
<b>MALWAREPROTECTION_ANTIVIRUS_DISABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-1032">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-1032">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-1033">
<b>바이러스 검사가 사용되지 않습니다. </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1033">
<b>Scanning for viruses is disabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-1034">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-1034">Description:</span></span>
</td>
<td >
<span data-ttu-id="c9697-1035">Microsoft Defender 바이러스 백신 검사가 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-1035">Microsoft Defender Antivirus scanning for viruses is disabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-1036">이벤트 ID: 5100</span><span class="sxs-lookup"><span data-stu-id="c9697-1036">Event ID: 5100</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-1037">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-1037">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-1038">
<b>MALWAREPROTECTION_EXPIRATION_WARNING_STATE </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1038">
<b>MALWAREPROTECTION_EXPIRATION_WARNING_STATE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-1039">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-1039">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-1040">
<b>맬웨어 방지 플랫폼이 곧 만료됩니다. </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1040">
<b>The antimalware platform will expire soon. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-1041">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-1041">Description:</span></span>
</td>
<td >
<span data-ttu-id="c9697-1042">Microsoft Defender 바이러스 백신 유예 기간이 시작되고 곧 만료됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-1042">Microsoft Defender Antivirus has entered a grace period and will soon expire.</span></span> <span data-ttu-id="c9697-1043">만료 후 이 프로그램은 바이러스, 스파이웨어 및 사용자 원치 않는 기타 소프트웨어에 대한 보호를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-1043">After expiration, this program will disable protection against viruses, spyware, and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="c9697-1044">
<dt>만료 이유: 만료 Microsoft Defender 바이러스 백신 이유입니다.</dt> 
<dt>만료 날짜: Microsoft Defender 바이러스 백신 날짜입니다.</dt>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1044">
<dt>Expiration Reason: The reason Microsoft Defender Antivirus will expire.</dt>
<dt>Expiration Date: The date Microsoft Defender Antivirus will expire.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-1045">이벤트 ID: 5101</span><span class="sxs-lookup"><span data-stu-id="c9697-1045">Event ID: 5101</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="c9697-1046">기호 이름:</span><span class="sxs-lookup"><span data-stu-id="c9697-1046">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="c9697-1047">
<b>MALWAREPROTECTION_DISABLED_EXPIRED_STATE </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1047">
<b>MALWAREPROTECTION_DISABLED_EXPIRED_STATE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-1048">메시지:</span><span class="sxs-lookup"><span data-stu-id="c9697-1048">Message:</span></span>
</td>
<td ><span data-ttu-id="c9697-1049">
<b>맬웨어 방지 플랫폼이 만료되었습니다. </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1049">
<b>The antimalware platform is expired. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-1050">설명:</span><span class="sxs-lookup"><span data-stu-id="c9697-1050">Description:</span></span>
</td>
<td >
<span data-ttu-id="c9697-1051">Microsoft Defender 바이러스 백신 유예 기간이 만료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-1051">Microsoft Defender Antivirus grace period has expired.</span></span> <span data-ttu-id="c9697-1052">바이러스, 스파이웨어 및 사용자 원치 않는 기타 소프트웨어에 대한 보호가 사용되지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-1052">Protection against viruses, spyware, and other potentially unwanted software is disabled.</span></span>
<dl><span data-ttu-id="c9697-1053">
<dt>만료 이유:</dt>
<dt>만료 날짜: </dt>오류 코드: 오류 코드 위협 상태와 관련된 결과 
<dt> &lt; &gt; 코드입니다. 표준 HRESULT 값입니다.</dt> 
<dt>오류 설명: &lt; 오류 설명 &gt; 오류에 대한 설명입니다.</dt>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1053">
<dt>Expiration Reason:</dt>
<dt>Expiration Date: </dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr><span data-ttu-id="c9697-1054">
</table>

<a id="error-codes"></a>
##Microsoft Defender 바이러스 백신 클라이언트 오류 코드 Microsoft Defender 바이러스 백신 문제가 발생하는 경우 일반적으로 문제를 해결하는 데 도움이 되는 오류 코드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-1054">
</table>

<a id="error-codes"></a>
## Microsoft Defender Antivirus client error codes If Microsoft Defender Antivirus experiences any issues it will usually give you an error code to help you troubleshoot the issue.</span></span> <span data-ttu-id="c9697-1055">대부분의 오류는 업데이트를 설치하는 데 문제가 발생했다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-1055">Most often an error means there was a problem installing an update.</span></span>
<span data-ttu-id="c9697-1056">이 섹션에서는 클라이언트 오류와 관련한 Microsoft Defender 바이러스 백신 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-1056">This section provides the following information about Microsoft Defender Antivirus client errors.</span></span>
<span data-ttu-id="c9697-1057">-   오류 코드 오류에 대한 가능한 -   이유 -   지금 할 일에 대한 조언</span><span class="sxs-lookup"><span data-stu-id="c9697-1057">-   The error code -   The possible reason for the error -   Advice on what to do now</span></span>

<span data-ttu-id="c9697-1058">다음 표의 정보를 사용하여 오류 코드 문제를 Microsoft Defender 바이러스 백신 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-1058">Use the information in these tables to help troubleshoot Microsoft Defender Antivirus error codes.</span></span>


<table> 
<tr>
<th colspan="2"><span data-ttu-id="c9697-1059">오류 코드: 0x80508007</span><span class="sxs-lookup"><span data-stu-id="c9697-1059">Error code: 0x80508007</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="c9697-1060">메시지</span><span class="sxs-lookup"><span data-stu-id="c9697-1060">Message</span></span></td>
<td><span data-ttu-id="c9697-1061">
<b>ERR_MP_NO_MEMORY </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1061">
<b>ERR_MP_NO_MEMORY </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-1062">가능한 이유</span><span class="sxs-lookup"><span data-stu-id="c9697-1062">Possible reason</span></span>
</td>
<td>
<span data-ttu-id="c9697-1063">이 오류는 메모리가 부족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-1063">This error indicates that you might have run out of memory.</span></span> 
</td>
</tr>
<tr>
<td><span data-ttu-id="c9697-1064">해결 방법</span><span class="sxs-lookup"><span data-stu-id="c9697-1064">Resolution</span></span></td>
<td>
<ol>
<li><span data-ttu-id="c9697-1065">장치에서 사용 가능한 메모리를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-1065">Check the available memory on your device.</span></span></li>
<li><span data-ttu-id="c9697-1066">장치에서 메모리를 비우기 위해 실행 중인 사용되지 않는 응용 프로그램을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-1066">Close any unused applications that are running to free up memory on your device.</span></span></li>
<li><span data-ttu-id="c9697-1067">장치를 다시 시작하고 스캔을 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-1067">Restart the device and run the scan again.</span></span> 
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-1068">오류 코드: 0x8050800C</span><span class="sxs-lookup"><span data-stu-id="c9697-1068">Error code: 0x8050800C</span></span></th>
</tr><tr><td><span data-ttu-id="c9697-1069">메시지</span><span class="sxs-lookup"><span data-stu-id="c9697-1069">Message</span></span></td>
<td><span data-ttu-id="c9697-1070"><b>ERR_MP_BAD_INPUT_DATA</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1070"><b>ERR_MP_BAD_INPUT_DATA</b>
</span></span></td></tr><tr><td><span data-ttu-id="c9697-1071">가능한 이유</span><span class="sxs-lookup"><span data-stu-id="c9697-1071">Possible reason</span></span></td>
<td>
<span data-ttu-id="c9697-1072">이 오류는 보안 제품에 문제가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-1072">This error indicates that there might be a problem with your security product.</span></span>
</td>
</tr><tr><td><span data-ttu-id="c9697-1073">해결 방법</span><span class="sxs-lookup"><span data-stu-id="c9697-1073">Resolution</span></span></td><td>
<ol>
<li><span data-ttu-id="c9697-1074">정의를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-1074">Update the definitions.</span></span> <span data-ttu-id="c9697-1075">중 하나:</span><span class="sxs-lookup"><span data-stu-id="c9697-1075">Either:</span></span><ol>
<li><span data-ttu-id="c9697-1076">업데이트 <b>탭의</b> 정의 업데이트 <b></b> 단추를 Microsoft Defender 바이러스 백신.</span><span class="sxs-lookup"><span data-stu-id="c9697-1076">Click the <b>Update definitions</b> button on the <b>Update</b> tab in Microsoft Defender Antivirus.</span></span> <img src="images/defender-updatedefs2.png" alt="Update definitions in Microsoft Defender Antivirus"/><span data-ttu-id="c9697-1077">또는</span><span class="sxs-lookup"><span data-stu-id="c9697-1077">Or,</span></span>
</li>
<li><span data-ttu-id="c9697-1078">사이트 에서 최신 <a href="https://aka.ms/wdsi">정의를 Microsoft 보안 인텔리전스 다운로드합니다.</a></span><span class="sxs-lookup"><span data-stu-id="c9697-1078">Download the latest definitions from the <a href="https://aka.ms/wdsi">Microsoft Security Intelligence site</a>.</span></span>
<span data-ttu-id="c9697-1079">참고: 사이트에서 다운로드한 정의 파일의 크기는 60MB를 초과할 수 있으며 정의를 업데이트하기 위한 장기 솔루션으로 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-1079">Note: The size of the definitions file downloaded from the site can exceed 60 MB and should not be used as a long-term solution for updating definitions.</span></span>
</li>
</ol>
</li>
<li><span data-ttu-id="c9697-1080">전체 검색을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-1080">Run a full scan.</span></span>
</li>
<li><span data-ttu-id="c9697-1081">장치를 다시 시작하고 다시 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-1081">Restart the device and try again.</span></span></li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-1082">오류 코드: 0x80508020</span><span class="sxs-lookup"><span data-stu-id="c9697-1082">Error code: 0x80508020</span></span></th>
</tr><tr><td><span data-ttu-id="c9697-1083">메시지</span><span class="sxs-lookup"><span data-stu-id="c9697-1083">Message</span></span></td>
<td><span data-ttu-id="c9697-1084"><b>ERR_MP_BAD_CONFIGURATION </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1084"><b>ERR_MP_BAD_CONFIGURATION </b>
</span></span></td></tr><tr><td><span data-ttu-id="c9697-1085">가능한 이유</span><span class="sxs-lookup"><span data-stu-id="c9697-1085">Possible reason</span></span></td>
<td>
<span data-ttu-id="c9697-1086">이 오류는 엔진 구성 오류가 있을 수 있습니다. 일반적으로 이는 엔진이 제대로 작동할 수 없는 입력 데이터와 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-1086">This error indicates that there might be an engine configuration error; commonly, this is related to input data that does not allow the engine to function properly.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-1087">오류 코드: 0x805080211</span><span class="sxs-lookup"><span data-stu-id="c9697-1087">Error code: 0x805080211</span></span>
</th>
</tr><tr><td><span data-ttu-id="c9697-1088">메시지</span><span class="sxs-lookup"><span data-stu-id="c9697-1088">Message</span></span></td>
<td><span data-ttu-id="c9697-1089"><b>ERR_MP_QUARANTINE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1089"><b>ERR_MP_QUARANTINE_FAILED </b>
</span></span></td></tr><tr><td><span data-ttu-id="c9697-1090">가능한 이유</span><span class="sxs-lookup"><span data-stu-id="c9697-1090">Possible reason</span></span></td>
<td>
<span data-ttu-id="c9697-1091">이 오류는 Microsoft Defender 바이러스 백신 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-1091">This error indicates that Microsoft Defender Antivirus failed to quarantine a threat.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-1092">오류 코드: 0x80508022</span><span class="sxs-lookup"><span data-stu-id="c9697-1092">Error code: 0x80508022</span></span>
</th>
</tr><tr><td><span data-ttu-id="c9697-1093">메시지</span><span class="sxs-lookup"><span data-stu-id="c9697-1093">Message</span></span></td>
<td><span data-ttu-id="c9697-1094"><b>ERR_MP_REBOOT_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1094"><b>ERR_MP_REBOOT_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="c9697-1095">가능한 이유</span><span class="sxs-lookup"><span data-stu-id="c9697-1095">Possible reason</span></span></td>
<td>
<span data-ttu-id="c9697-1096">이 오류는 위협 제거를 완료하기 위해 재부팅이 필요하다는 메시지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-1096">This error indicates that a reboot is required to complete threat removal.</span></span> 
</td>
</tr>
<tr>
<th colspan="2">
<span data-ttu-id="c9697-1097">0x80508023</span><span class="sxs-lookup"><span data-stu-id="c9697-1097">0x80508023</span></span>
</th>
</tr><tr><td><span data-ttu-id="c9697-1098">메시지</span><span class="sxs-lookup"><span data-stu-id="c9697-1098">Message</span></span></td>
<td><span data-ttu-id="c9697-1099"><b>ERR_MP_THREAT_NOT_FOUND </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1099"><b>ERR_MP_THREAT_NOT_FOUND </b>
</span></span></td></tr><tr><td><span data-ttu-id="c9697-1100">가능한 이유</span><span class="sxs-lookup"><span data-stu-id="c9697-1100">Possible reason</span></span></td>
<td>
<span data-ttu-id="c9697-1101">이 오류는 위협이 미디어에 더 이상 존재하지 않을 수도, 맬웨어가 장치 검색을 중지하고 있을 수 있다는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-1101">This error indicates that the threat might no longer be present on the media, or malware might be stopping you from scanning your device.</span></span> 
</tr><tr><td><span data-ttu-id="c9697-1102">해결 방법</span><span class="sxs-lookup"><span data-stu-id="c9697-1102">Resolution</span></span>
</td>
<td>
<span data-ttu-id="c9697-1103">보안 <a href="https://www.microsoft.com/security/scanner/default.aspx">Microsoft 보안 검사</a> 실행한 다음 보안 소프트웨어를 업데이트하고 다시 시도하세요.</span><span class="sxs-lookup"><span data-stu-id="c9697-1103">Run the <a href="https://www.microsoft.com/security/scanner/default.aspx">Microsoft Safety Scanner</a> then update your security software and try again.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-1104">오류 코드: 0x80508024</span><span class="sxs-lookup"><span data-stu-id="c9697-1104">Error code: 0x80508024</span></span> </th></tr>
<tr>
<td><span data-ttu-id="c9697-1105">메시지</span><span class="sxs-lookup"><span data-stu-id="c9697-1105">Message</span></span></td>
<td><span data-ttu-id="c9697-1106"><b>ERR_MP_FULL_SCAN_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1106"><b>ERR_MP_FULL_SCAN_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="c9697-1107">가능한 이유</span><span class="sxs-lookup"><span data-stu-id="c9697-1107">Possible reason</span></span></td>
<td>
<span data-ttu-id="c9697-1108">이 오류는 전체 시스템 검사가 필요한 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-1108">This error indicates that a full system scan might be required.</span></span> 
</td></tr>
<tr>
<td><span data-ttu-id="c9697-1109">해결 방법</span><span class="sxs-lookup"><span data-stu-id="c9697-1109">Resolution</span></span></td><td>
<span data-ttu-id="c9697-1110">전체 시스템 검색을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-1110">Run a full system scan.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-1111">오류 코드: 0x80508025</span><span class="sxs-lookup"><span data-stu-id="c9697-1111">Error code: 0x80508025</span></span>
</th>
</tr><tr><td><span data-ttu-id="c9697-1112">메시지</span><span class="sxs-lookup"><span data-stu-id="c9697-1112">Message</span></span></td>
<td><span data-ttu-id="c9697-1113"><b>ERR_MP_MANUAL_STEPS_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1113"><b>ERR_MP_MANUAL_STEPS_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="c9697-1114">가능한 이유</span><span class="sxs-lookup"><span data-stu-id="c9697-1114">Possible reason</span></span></td>
<td>
<span data-ttu-id="c9697-1115">이 오류는 위협 제거를 완료하는 데 수동 단계가 필요하다는 메시지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-1115">This error indicates that manual steps are required to complete threat removal.</span></span> 
</td></tr><tr><td><span data-ttu-id="c9697-1116">해결 방법</span><span class="sxs-lookup"><span data-stu-id="c9697-1116">Resolution</span></span></td><td>
<span data-ttu-id="c9697-1117">Microsoft 맬웨어 보호 백과사전 에 설명된 수동 <a href="https://www.microsoft.com/security/portal/threat/Threats.aspx">수정 단계를 따릅니다.</a></span><span class="sxs-lookup"><span data-stu-id="c9697-1117">Follow the manual remediation steps outlined in the <a href="https://www.microsoft.com/security/portal/threat/Threats.aspx">Microsoft Malware Protection Encyclopedia</a>.</span></span> <span data-ttu-id="c9697-1118">이벤트 기록에서 위협 관련 링크를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-1118">You can find a threat-specific link in the event history.</span></span><br/></td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-1119">오류 코드: 0x80508026</span><span class="sxs-lookup"><span data-stu-id="c9697-1119">Error code: 0x80508026</span></span>
</th>
</tr><tr><td><span data-ttu-id="c9697-1120">메시지</span><span class="sxs-lookup"><span data-stu-id="c9697-1120">Message</span></span></td>
<td><span data-ttu-id="c9697-1121"><b>ERR_MP_REMOVE_NOT_SUPPORTED </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1121"><b>ERR_MP_REMOVE_NOT_SUPPORTED </b>
</span></span></td></tr><tr><td><span data-ttu-id="c9697-1122">가능한 이유</span><span class="sxs-lookup"><span data-stu-id="c9697-1122">Possible reason</span></span></td>
<td>
<span data-ttu-id="c9697-1123">이 오류는 컨테이너 유형 내에서 제거가 지원되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-1123">This error indicates that removal inside the container type might not be not supported.</span></span> 
</td></tr><tr><td><span data-ttu-id="c9697-1124">해결 방법</span><span class="sxs-lookup"><span data-stu-id="c9697-1124">Resolution</span></span></td><td>
<span data-ttu-id="c9697-1125">Microsoft Defender 바이러스 백신 내부에서 감지된 위협을 수정하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-1125">Microsoft Defender Antivirus is not able to remediate threats detected inside the archive.</span></span> <span data-ttu-id="c9697-1126">검색된 리소스를 수동으로 제거하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-1126">Consider manually removing the detected resources.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-1127">오류 코드: 0x80508027</span><span class="sxs-lookup"><span data-stu-id="c9697-1127">Error code: 0x80508027</span></span>
</th>
</tr><tr><td><span data-ttu-id="c9697-1128">메시지</span><span class="sxs-lookup"><span data-stu-id="c9697-1128">Message</span></span></td>
<td><span data-ttu-id="c9697-1129"><b>ERR_MP_REMOVE_LOW_MEDIUM_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1129"><b>ERR_MP_REMOVE_LOW_MEDIUM_DISABLED </b>
</span></span></td></tr><tr><td><span data-ttu-id="c9697-1130">가능한 이유</span><span class="sxs-lookup"><span data-stu-id="c9697-1130">Possible reason</span></span></td>
<td>
<span data-ttu-id="c9697-1131">이 오류는 낮음 및 중간 위협 제거가 사용하지 않도록 설정되어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-1131">This error indicates that removal of low and medium threats might be disabled.</span></span> 
</td></tr><tr><td><span data-ttu-id="c9697-1132">해결 방법</span><span class="sxs-lookup"><span data-stu-id="c9697-1132">Resolution</span></span></td><td>
<span data-ttu-id="c9697-1133">감지된 위협을 확인하고 필요한 경우 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-1133">Check the detected threats and resolve them as required.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-1134">오류 코드: 0x80508029</span><span class="sxs-lookup"><span data-stu-id="c9697-1134">Error code: 0x80508029</span></span>
</th>
</tr><tr><td><span data-ttu-id="c9697-1135">메시지</span><span class="sxs-lookup"><span data-stu-id="c9697-1135">Message</span></span></td>
<td><span data-ttu-id="c9697-1136"><b>ERROR_MP_RESCAN_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1136"><b>ERROR_MP_RESCAN_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="c9697-1137">가능한 이유</span><span class="sxs-lookup"><span data-stu-id="c9697-1137">Possible reason</span></span></td>
<td>
<span data-ttu-id="c9697-1138">이 오류는 위협을 다시 검색해야 하다는 메시지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-1138">This error indicates a rescan of the threat is required.</span></span> 
</td></tr><tr><td><span data-ttu-id="c9697-1139">해결 방법</span><span class="sxs-lookup"><span data-stu-id="c9697-1139">Resolution</span></span></td><td>
<span data-ttu-id="c9697-1140">전체 시스템 검색을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-1140">Run a full system scan.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-1141">오류 코드: 0x80508030</span><span class="sxs-lookup"><span data-stu-id="c9697-1141">Error code: 0x80508030</span></span>
</th>
</tr><tr><td><span data-ttu-id="c9697-1142">메시지</span><span class="sxs-lookup"><span data-stu-id="c9697-1142">Message</span></span></td>
<td><span data-ttu-id="c9697-1143"><b>ERROR_MP_CALLISTO_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1143"><b>ERROR_MP_CALLISTO_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="c9697-1144">가능한 이유</span><span class="sxs-lookup"><span data-stu-id="c9697-1144">Possible reason</span></span></td>
<td>
<span data-ttu-id="c9697-1145">이 오류는 오프라인 검사가 필요를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-1145">This error indicates that an offline scan is required.</span></span> 
</td></tr><tr><td><span data-ttu-id="c9697-1146">해결 방법</span><span class="sxs-lookup"><span data-stu-id="c9697-1146">Resolution</span></span></td><td>
<span data-ttu-id="c9697-1147">오프라인으로 Microsoft Defender 바이러스 백신.</span><span class="sxs-lookup"><span data-stu-id="c9697-1147">Run offline Microsoft Defender Antivirus.</span></span> <span data-ttu-id="c9697-1148">오프라인 문서 에서 이 작업을 하는 <a href="https://windows.microsoft.com/windows/what-is-windows-defender-offline">방법에 대해 Microsoft Defender 바이러스 백신 있습니다.</a></span><span class="sxs-lookup"><span data-stu-id="c9697-1148">You can read about how to do this in the <a href="https://windows.microsoft.com/windows/what-is-windows-defender-offline">offline Microsoft Defender Antivirus article</a>.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="c9697-1149">오류 코드: 0x80508031</span><span class="sxs-lookup"><span data-stu-id="c9697-1149">Error code: 0x80508031</span></span>
</th>
</tr><tr><td><span data-ttu-id="c9697-1150">메시지</span><span class="sxs-lookup"><span data-stu-id="c9697-1150">Message</span></span></td>
<td><span data-ttu-id="c9697-1151"><b>ERROR_MP_PLATFORM_OUTDATED</span><span class="sxs-lookup"><span data-stu-id="c9697-1151"><b>ERROR_MP_PLATFORM_OUTDATED</span></span><br/></b>
</td></tr><tr><td><span data-ttu-id="c9697-1152">가능한 이유</span><span class="sxs-lookup"><span data-stu-id="c9697-1152">Possible reason</span></span></td>
<td>
<span data-ttu-id="c9697-1153">이 오류는 Microsoft Defender 바이러스 백신 플랫폼의 현재 버전을 지원하지 않는 새 버전의 플랫폼이 필요하다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-1153">This error indicates that Microsoft Defender Antivirus does not support the current version of the platform and requires a new version of the platform.</span></span> 
</td></tr><tr><td><span data-ttu-id="c9697-1154">해결 방법</span><span class="sxs-lookup"><span data-stu-id="c9697-1154">Resolution</span></span></td><td>
<span data-ttu-id="c9697-1155">이 경우 해당 Microsoft Defender 바이러스 백신 사용할 수 Windows 10.</span><span class="sxs-lookup"><span data-stu-id="c9697-1155">You can only use Microsoft Defender Antivirus in Windows 10.</span></span> <span data-ttu-id="c9697-1156">Windows 8 7과 Windows Vista의 Windows 를 사용할 <a href="https://www.microsoft.com/server-cloud/system-center/endpoint-protection-2012.aspx">System Center Endpoint Protection.</a></span><span class="sxs-lookup"><span data-stu-id="c9697-1156">For Windows 8, Windows 7 and Windows Vista, you can use <a href="https://www.microsoft.com/server-cloud/system-center/endpoint-protection-2012.aspx">System Center Endpoint Protection</a>.</span></span><br/></td>
</tr>
</table><span data-ttu-id="c9697-1157">

<a id="internal-error-codes"></a>다음 오류 코드는 내부 테스트 중에 Microsoft Defender 바이러스 백신.</span><span class="sxs-lookup"><span data-stu-id="c9697-1157">

<a id="internal-error-codes"></a> The following error codes are used during internal testing of Microsoft Defender Antivirus.</span></span>

<span data-ttu-id="c9697-1158">이러한 오류가 표시될 경우 정의를 [](manage-updates-baselines-microsoft-defender-antivirus.md) 업데이트하고 끝점에서 직접 다시 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-1158">If you see these errors, you can try to [update definitions](manage-updates-baselines-microsoft-defender-antivirus.md) and force a rescan directly on the endpoint.</span></span>


<table> 
<tr>
<th colspan="3"><span data-ttu-id="c9697-1159">내부 오류 코드</span><span class="sxs-lookup"><span data-stu-id="c9697-1159">Internal error codes</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="c9697-1160"><b>오류 코드</b></span><span class="sxs-lookup"><span data-stu-id="c9697-1160"><b>Error code</b></span></span></th>
<th><span data-ttu-id="c9697-1161">메시지 표시</span><span class="sxs-lookup"><span data-stu-id="c9697-1161">Message displayed</span></span></th>
<th><span data-ttu-id="c9697-1162">가능한 오류 및 해결 이유</span><span class="sxs-lookup"><span data-stu-id="c9697-1162">Possible reason for error and resolution</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-1163">0x80501004</span><span class="sxs-lookup"><span data-stu-id="c9697-1163">0x80501004</span></span>
</td>
<td><span data-ttu-id="c9697-1164">
<b>ERROR_MP_NO_INTERNET_CONN </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1164">
<b>ERROR_MP_NO_INTERNET_CONN </b>
</span></span></td>
<td>
<span data-ttu-id="c9697-1165">인터넷 연결을 확인한 다음 검사를 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-1165">Check your Internet connection, then run the scan again.</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-1166">0x80501000</span><span class="sxs-lookup"><span data-stu-id="c9697-1166">0x80501000</span></span>
</td>
<td><span data-ttu-id="c9697-1167">
<b>ERROR_MP_UI_CONSOLIDATION_BAS</b> E</span><span class="sxs-lookup"><span data-stu-id="c9697-1167">
<b>ERROR_MP_UI_CONSOLIDATION_BAS</b>E</span></span>
</td>
<td rowspan="34">
<span data-ttu-id="c9697-1168">내부 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-1168">This is an internal error.</span></span> <span data-ttu-id="c9697-1169">원인은 명확히 정의되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-1169">The cause is not clearly defined.</span></span>
</td>
<td rowspan="36">

</td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-1170">0x80501001</span><span class="sxs-lookup"><span data-stu-id="c9697-1170">0x80501001</span></span>
</td>
<td><span data-ttu-id="c9697-1171">
<b>ERROR_MP_ACTIONS_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1171">
<b>ERROR_MP_ACTIONS_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-1172">0x80501002</span><span class="sxs-lookup"><span data-stu-id="c9697-1172">0x80501002</span></span>
</td>
<td><span data-ttu-id="c9697-1173">
<b>ERROR_MP_NOENGINE</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1173">
<b>ERROR_MP_NOENGINE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-1174">0x80501003</span><span class="sxs-lookup"><span data-stu-id="c9697-1174">0x80501003</span></span>
</td>
<td><span data-ttu-id="c9697-1175">
<b>ERROR_MP_ACTIVE_THREATS</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1175">
<b>ERROR_MP_ACTIVE_THREATS</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-1176">0x805011011</span><span class="sxs-lookup"><span data-stu-id="c9697-1176">0x805011011</span></span>
</td>
<td><span data-ttu-id="c9697-1177">
<b>MP_ERROR_CODE_LUA_CANCELLED </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1177">
<b>MP_ERROR_CODE_LUA_CANCELLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-1178">0x80501101</span><span class="sxs-lookup"><span data-stu-id="c9697-1178">0x80501101</span></span>
</td>
<td><span data-ttu-id="c9697-1179">
<b>ERROR_LUA_CANCELLATION </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1179">
<b>ERROR_LUA_CANCELLATION </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-1180">0x80501102</span><span class="sxs-lookup"><span data-stu-id="c9697-1180">0x80501102</span></span>
</td>
<td><span data-ttu-id="c9697-1181">
<b>MP_ERROR_CODE_ALREADY_SHUTDOWN</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1181">
<b>MP_ERROR_CODE_ALREADY_SHUTDOWN</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-1182">0x80501103</span><span class="sxs-lookup"><span data-stu-id="c9697-1182">0x80501103</span></span>
</td>
<td><span data-ttu-id="c9697-1183">
<b>MP_ERROR_CODE_RDEVICE_S_ASYNC_CALL_PENDING </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1183">
<b>MP_ERROR_CODE_RDEVICE_S_ASYNC_CALL_PENDING </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-1184">0x80501104</span><span class="sxs-lookup"><span data-stu-id="c9697-1184">0x80501104</span></span>
</td>
<td><span data-ttu-id="c9697-1185">
<b>MP_ERROR_CODE_CANCELLED</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1185">
<b>MP_ERROR_CODE_CANCELLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-1186">0x80501105</span><span class="sxs-lookup"><span data-stu-id="c9697-1186">0x80501105</span></span>
</td>
<td><span data-ttu-id="c9697-1187">
<b>MP_ERROR_CODE_NO_TARGETOS</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1187">
<b>MP_ERROR_CODE_NO_TARGETOS</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-1188">0x80501106</span><span class="sxs-lookup"><span data-stu-id="c9697-1188">0x80501106</span></span>
</td>
<td><span data-ttu-id="c9697-1189">
<b>MP_ERROR_CODE_BAD_REGEXP</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1189">
<b>MP_ERROR_CODE_BAD_REGEXP</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-1190">0x80501107</span><span class="sxs-lookup"><span data-stu-id="c9697-1190">0x80501107</span></span>
</td>
<td><span data-ttu-id="c9697-1191">
<b>MP_ERROR_TEST_INDUCED_ERROR</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1191">
<b>MP_ERROR_TEST_INDUCED_ERROR</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-1192">0x80501108</span><span class="sxs-lookup"><span data-stu-id="c9697-1192">0x80501108</span></span>
</td>
<td><span data-ttu-id="c9697-1193">
<b>MP_ERROR_SIG_BACKUP_DISABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1193">
<b>MP_ERROR_SIG_BACKUP_DISABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-1194">0x80508001</span><span class="sxs-lookup"><span data-stu-id="c9697-1194">0x80508001</span></span>
</td>
<td><span data-ttu-id="c9697-1195">
<b>ERR_MP_BAD_INIT_MODULES</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1195">
<b>ERR_MP_BAD_INIT_MODULES</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-1196">0x80508002</span><span class="sxs-lookup"><span data-stu-id="c9697-1196">0x80508002</span></span>
</td>
<td><span data-ttu-id="c9697-1197">
<b>ERR_MP_BAD_DATABASE</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1197">
<b>ERR_MP_BAD_DATABASE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-1198">0x80508004</span><span class="sxs-lookup"><span data-stu-id="c9697-1198">0x80508004</span></span>
</td>
<td><span data-ttu-id="c9697-1199">
<b>ERR_MP_BAD_UFS </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1199">
<b>ERR_MP_BAD_UFS </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-1200">0x8050800C</span><span class="sxs-lookup"><span data-stu-id="c9697-1200">0x8050800C</span></span>
</td>
<td><span data-ttu-id="c9697-1201">
<b>ERR_MP_BAD_INPUT_DATA</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1201">
<b>ERR_MP_BAD_INPUT_DATA</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-1202">0x8050800D</span><span class="sxs-lookup"><span data-stu-id="c9697-1202">0x8050800D</span></span>
</td>
<td><span data-ttu-id="c9697-1203">
<b>ERR_MP_BAD_GLOBAL_STORAGE</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1203">
<b>ERR_MP_BAD_GLOBAL_STORAGE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-1204">0x8050800E</span><span class="sxs-lookup"><span data-stu-id="c9697-1204">0x8050800E</span></span>
</td>
<td><span data-ttu-id="c9697-1205">
<b>ERR_MP_OBSOLETE</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1205">
<b>ERR_MP_OBSOLETE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-1206">0x8050800F</span><span class="sxs-lookup"><span data-stu-id="c9697-1206">0x8050800F</span></span>
</td>
<td><span data-ttu-id="c9697-1207">
<b>ERR_MP_NOT_SUPPORTED</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1207">
<b>ERR_MP_NOT_SUPPORTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-1208">0x8050800F 0x80508010</span><span class="sxs-lookup"><span data-stu-id="c9697-1208">0x8050800F 0x80508010</span></span>
</td>
<td><span data-ttu-id="c9697-1209">
<b>ERR_MP_NO_MORE_ITEMS </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1209">
<b>ERR_MP_NO_MORE_ITEMS </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-1210">0x80508011</span><span class="sxs-lookup"><span data-stu-id="c9697-1210">0x80508011</span></span>
</td>
<td><span data-ttu-id="c9697-1211">
<b>ERR_MP_DUPLICATE_SCANID</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1211">
<b>ERR_MP_DUPLICATE_SCANID</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-1212">0x80508012</span><span class="sxs-lookup"><span data-stu-id="c9697-1212">0x80508012</span></span>
</td>
<td><span data-ttu-id="c9697-1213">
<b>ERR_MP_BAD_SCANID</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1213">
<b>ERR_MP_BAD_SCANID</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-1214">0x80508013</span><span class="sxs-lookup"><span data-stu-id="c9697-1214">0x80508013</span></span>
</td>
<td><span data-ttu-id="c9697-1215">
<b>ERR_MP_BAD_USERDB_VERSION</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1215">
<b>ERR_MP_BAD_USERDB_VERSION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-1216">0x80508014</span><span class="sxs-lookup"><span data-stu-id="c9697-1216">0x80508014</span></span>
</td>
<td><span data-ttu-id="c9697-1217">
<b>ERR_MP_RESTORE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1217">
<b>ERR_MP_RESTORE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-1218">0x80508016</span><span class="sxs-lookup"><span data-stu-id="c9697-1218">0x80508016</span></span>
</td>
<td><span data-ttu-id="c9697-1219">
<b>ERR_MP_BAD_ACTION</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1219">
<b>ERR_MP_BAD_ACTION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-1220">0x80508019</span><span class="sxs-lookup"><span data-stu-id="c9697-1220">0x80508019</span></span>
</td>
<td><span data-ttu-id="c9697-1221">
<b>ERR_MP_NOT_FOUND</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1221">
<b>ERR_MP_NOT_FOUND</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-1222">0x80509001</span><span class="sxs-lookup"><span data-stu-id="c9697-1222">0x80509001</span></span>
</td>
<td><span data-ttu-id="c9697-1223">
<b>ERR_RELO_BAD_EHANDLE</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1223">
<b>ERR_RELO_BAD_EHANDLE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-1224">0x80509003</span><span class="sxs-lookup"><span data-stu-id="c9697-1224">0x80509003</span></span>
</td>
<td><span data-ttu-id="c9697-1225">
<b>ERR_RELO_KERNEL_NOT_LOADED</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1225">
<b>ERR_RELO_KERNEL_NOT_LOADED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-1226">0x8050A001</span><span class="sxs-lookup"><span data-stu-id="c9697-1226">0x8050A001</span></span>
</td>
<td><span data-ttu-id="c9697-1227">
<b>ERR_MP_BADDB_OPEN</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1227">
<b>ERR_MP_BADDB_OPEN</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-1228">0x8050A002</span><span class="sxs-lookup"><span data-stu-id="c9697-1228">0x8050A002</span></span>
</td>
<td><span data-ttu-id="c9697-1229">
<b>ERR_MP_BADDB_HEADER</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1229">
<b>ERR_MP_BADDB_HEADER</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-1230">0x8050A003</span><span class="sxs-lookup"><span data-stu-id="c9697-1230">0x8050A003</span></span>
</td>
<td><span data-ttu-id="c9697-1231">
<b>ERR_MP_BADDB_OLDENGINE</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1231">
<b>ERR_MP_BADDB_OLDENGINE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-1232">0x8050A004</span><span class="sxs-lookup"><span data-stu-id="c9697-1232">0x8050A004</span></span>
</td>
<td><span data-ttu-id="c9697-1233">
<b>ERR_MP_BADDB_CONTENT </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1233">
<b>ERR_MP_BADDB_CONTENT </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-1234">0x8050A005</span><span class="sxs-lookup"><span data-stu-id="c9697-1234">0x8050A005</span></span>
</td>
<td><span data-ttu-id="c9697-1235">
<b>ERR_MP_BADDB_NOTSIGNED</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1235">
<b>ERR_MP_BADDB_NOTSIGNED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-1236">0x8050801</span><span class="sxs-lookup"><span data-stu-id="c9697-1236">0x8050801</span></span>
</td>
<td><span data-ttu-id="c9697-1237">
<b>ERR_MP_REMOVE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1237">
<b>ERR_MP_REMOVE_FAILED</b>
</span></span></td>
<td>
<span data-ttu-id="c9697-1238">내부 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-1238">This is an internal error.</span></span> <span data-ttu-id="c9697-1239">맬웨어 제거가 성공하지 못하면 트리거될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-1239">It might be triggered when malware removal is not successful.</span></span> 
</td>
</tr>
<tr>
<td>
<span data-ttu-id="c9697-1240">0x80508018</span><span class="sxs-lookup"><span data-stu-id="c9697-1240">0x80508018</span></span>
</td>
<td><span data-ttu-id="c9697-1241">
<b>ERR_MP_SCAN_ABORTED </b>
</span><span class="sxs-lookup"><span data-stu-id="c9697-1241">
<b>ERR_MP_SCAN_ABORTED </b>
</span></span></td>
<td>
<span data-ttu-id="c9697-1242">내부 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-1242">This is an internal error.</span></span> <span data-ttu-id="c9697-1243">검사가 완료되지 않을 때 트리거될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9697-1243">It might have triggered when a scan fails to complete.</span></span> 
</td>
</tr>
</table>

## <a name="related-topics"></a><span data-ttu-id="c9697-1244">관련 항목</span><span class="sxs-lookup"><span data-stu-id="c9697-1244">Related topics</span></span>

- [<span data-ttu-id="c9697-1245">Microsoft Defender 바이러스 백신 보호에 대한 보고</span><span class="sxs-lookup"><span data-stu-id="c9697-1245">Report on Microsoft Defender Antivirus protection</span></span>](report-monitor-microsoft-defender-antivirus.md)
- [<span data-ttu-id="c9697-1246">Windows 10의 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="c9697-1246">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)