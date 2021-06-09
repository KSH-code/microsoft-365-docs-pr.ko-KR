---
title: 데이터 손실 방지 알림 대시보드에 대한 자세한 정보
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: 데이터 손실 방지 경고 및 경고 대시보드에 대해 자세히 알아보습니다.
ms.openlocfilehash: b6fd698e535e006149f6ce3a2a5bc57d0c92c7e2
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51760780"
---
# <a name="learn-about-the-data-loss-prevention-alerts-dashboard"></a><span data-ttu-id="a0881-103">데이터 손실 방지 알림 대시보드에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="a0881-103">Learn about the data loss prevention Alerts dashboard</span></span>

<span data-ttu-id="a0881-104">DLP(데이터 손실 방지) 정책의 기준이 사용자가 중요한 항목에 대해 수행하고 있는 작업과 일치하면 정책에서 경고를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0881-104">When the criteria in a Data loss prevention (DLP) policy is matched by the actions a user is taking on a sensitive item, the policy can generate an alert.</span></span> <span data-ttu-id="a0881-105">이로 인해 많은 경고가 생성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0881-105">This can result in a high volume of alerts.</span></span> <span data-ttu-id="a0881-106">DLP 경고는 경고 대시보드에서 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0881-106">DLP alerts are collected in the alerts dashboard.</span></span> <span data-ttu-id="a0881-107">알림 대시보드에서는 정책 일치와 관련한 모든 세부 정보를 심도 깊게 조사할 수 있는 단일 장소를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a0881-107">The alerts dashboard gives you a single place to go to perform a deep investigation of all the details regarding the policy match.</span></span>  

<!-- [Microsoft 365 compliance center](https://compliance.microsoft.com/)-->

## <a name="workloads"></a><span data-ttu-id="a0881-108">워크로드</span><span class="sxs-lookup"><span data-stu-id="a0881-108">Workloads</span></span>

<span data-ttu-id="a0881-109">Microsoft 365 규정 준수 센터의 [DLP](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts)경고 관리 [대시보드는](https://compliance.microsoft.com/)다음 워크로드에 대한 DLP 정책에 대한 경고를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="a0881-109">The [DLP alert management dashboard](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts), in the [Microsoft 365 compliance center](https://compliance.microsoft.com/), shows alerts for DLP policies on these workloads:</span></span>

- <span data-ttu-id="a0881-110">Exchange</span><span class="sxs-lookup"><span data-stu-id="a0881-110">Exchange</span></span>
- <span data-ttu-id="a0881-111">SharePoint</span><span class="sxs-lookup"><span data-stu-id="a0881-111">SharePoint</span></span>
- <span data-ttu-id="a0881-112">OneDrive</span><span class="sxs-lookup"><span data-stu-id="a0881-112">OneDrive</span></span>
- <span data-ttu-id="a0881-113">Teams</span><span class="sxs-lookup"><span data-stu-id="a0881-113">Teams</span></span>
- <span data-ttu-id="a0881-114">Windows 10 장치</span><span class="sxs-lookup"><span data-stu-id="a0881-114">Windows 10 devices</span></span> 

> [!TIP]
> <span data-ttu-id="a0881-115">Teams DLP를 사용할 수 있는 끝점 [DLP를](endpoint-dlp-learn-about.md) 사용하는 고객에게는 끝점 DLP 정책 경고 및 [DLP](dlp-microsoft-teams.md) Teams 관리 대시보드에서 DLP 정책 경고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0881-115">Customers who use [Endpoint DLP](endpoint-dlp-learn-about.md) who are eligible for [Teams DLP](dlp-microsoft-teams.md) will see their endpoint DLP policy alerts and Teams DLP policy alerts in the DLP alert management dashboard.</span></span>

## <a name="single-alert-and-aggregate-alert"></a><span data-ttu-id="a0881-116">단일 경고 및 집계 경고</span><span class="sxs-lookup"><span data-stu-id="a0881-116">Single alert and aggregate alert</span></span>

<span data-ttu-id="a0881-117">DLP 정책에서 구성할 수 있는 두 가지 유형의 경고가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0881-117">There are two types of alerts that can be configured in DLP policies.</span></span>

<span data-ttu-id="a0881-118">**단일 이벤트** 경고는 일반적으로 조직 외부로 10개 이상의 고객 신용 카드 번호가 전송되는 단일 전자 메일과 같이 낮은 볼륨으로 발생하는 매우 중요한 이벤트를 모니터링하는 정책에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0881-118">**Single-event alerts** are typically used in policies that monitor for highly sensitive events that occur in a low volume, like a single email with 10 or more customer credit card numbers being sent outside your organization.</span></span>

<span data-ttu-id="a0881-119">**집계 이벤트 경고는** 일반적으로 일정 기간 동안 더 많은 볼륨으로 발생하는 이벤트를 모니터링하는 정책에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0881-119">**Aggregate-event alerts** are typically used in policies that monitor for events that occur in a higher volume over a period of time.</span></span> <span data-ttu-id="a0881-120">예를 들어 48시간 넘게 고객 신용 카드 번호가 하나인 개별 전자 메일 10개가 각각 48시간 넘게 전송되면 집계 경고가 트리거될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0881-120">For example, an aggregate alert can be triggered when 10 individual emails each with one customer credit card number is sent outside your org over 48 hours.</span></span>

## <a name="types-of-events"></a><span data-ttu-id="a0881-121">이벤트 유형</span><span class="sxs-lookup"><span data-stu-id="a0881-121">Types of events</span></span>

<span data-ttu-id="a0881-122">다음은 경고와 관련된 몇 가지 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="a0881-122">Here are some of the events associated with an alert.</span></span> <span data-ttu-id="a0881-123">UI에서 특정 이벤트를 선택하면 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0881-123">In the UI, you can choose a particular event to view its details.</span></span> 

### <a name="event-details"></a><span data-ttu-id="a0881-124">이벤트 세부 정보</span><span class="sxs-lookup"><span data-stu-id="a0881-124">Event details</span></span>

|<span data-ttu-id="a0881-125">속성 이름</span><span class="sxs-lookup"><span data-stu-id="a0881-125">Property name</span></span>  |<span data-ttu-id="a0881-126">설명</span><span class="sxs-lookup"><span data-stu-id="a0881-126">Description</span></span>  |<span data-ttu-id="a0881-127">이벤트 유형</span><span class="sxs-lookup"><span data-stu-id="a0881-127">Event types</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="a0881-128">ID</span><span class="sxs-lookup"><span data-stu-id="a0881-128">ID</span></span> |<span data-ttu-id="a0881-129">이벤트와 연결된 고유 ID</span><span class="sxs-lookup"><span data-stu-id="a0881-129">unique ID associated with the event</span></span> |<span data-ttu-id="a0881-130">모든 이벤트</span><span class="sxs-lookup"><span data-stu-id="a0881-130">all events</span></span> |
|<span data-ttu-id="a0881-131">위치</span><span class="sxs-lookup"><span data-stu-id="a0881-131">Location</span></span> |<span data-ttu-id="a0881-132">이벤트가 검색된 워크로드</span><span class="sxs-lookup"><span data-stu-id="a0881-132">workload where the event was detected</span></span>|<span data-ttu-id="a0881-133">모든 이벤트</span><span class="sxs-lookup"><span data-stu-id="a0881-133">all events</span></span> |
|<span data-ttu-id="a0881-134">활동 시간</span><span class="sxs-lookup"><span data-stu-id="a0881-134">time of activity</span></span>     |<span data-ttu-id="a0881-135">DLP 정책의 조건과 일치하는 사용자 활동의 시간</span><span class="sxs-lookup"><span data-stu-id="a0881-135">time of the user activity that matched the criteria of the DLP policy</span></span> |

### <a name="impacted-entities"></a><span data-ttu-id="a0881-136">영향을 미치는 엔터티</span><span class="sxs-lookup"><span data-stu-id="a0881-136">Impacted entities</span></span>

|<span data-ttu-id="a0881-137">속성 이름</span><span class="sxs-lookup"><span data-stu-id="a0881-137">Property name</span></span> |<span data-ttu-id="a0881-138">설명</span><span class="sxs-lookup"><span data-stu-id="a0881-138">Description</span></span>| <span data-ttu-id="a0881-139">이벤트 유형</span><span class="sxs-lookup"><span data-stu-id="a0881-139">Event types</span></span>|
|---------|---------|---------|
|<span data-ttu-id="a0881-140">사용자</span><span class="sxs-lookup"><span data-stu-id="a0881-140">user</span></span> | <span data-ttu-id="a0881-141">정책 일치를 유발한 작업을 수행한 사용자</span><span class="sxs-lookup"><span data-stu-id="a0881-141">user who took the action that caused the policy match</span></span> | <span data-ttu-id="a0881-142">모든 이벤트</span><span class="sxs-lookup"><span data-stu-id="a0881-142">all events</span></span>|
|<span data-ttu-id="a0881-143">hostname</span><span class="sxs-lookup"><span data-stu-id="a0881-143">hostname</span></span> | <span data-ttu-id="a0881-144">DLP 정책 일치가 발생한 컴퓨터의 호스트 이름</span><span class="sxs-lookup"><span data-stu-id="a0881-144">host name of the computer where the DLP policy match occurred</span></span> | <span data-ttu-id="a0881-145">장치 이벤트</span><span class="sxs-lookup"><span data-stu-id="a0881-145">device events</span></span>|
|<span data-ttu-id="a0881-146">IP 주소</span><span class="sxs-lookup"><span data-stu-id="a0881-146">IP address</span></span> | <span data-ttu-id="a0881-147">DLP 정책 일치가 발생한 컴퓨터의 IP 주소</span><span class="sxs-lookup"><span data-stu-id="a0881-147">IP address of the computer where the DLP policy match occurred</span></span> | <span data-ttu-id="a0881-148">장치 이벤트</span><span class="sxs-lookup"><span data-stu-id="a0881-148">device events</span></span>|
|<span data-ttu-id="a0881-149">sha1</span><span class="sxs-lookup"><span data-stu-id="a0881-149">sha1</span></span> |<span data-ttu-id="a0881-150">파일의 SHA-1 해시</span><span class="sxs-lookup"><span data-stu-id="a0881-150">SHA-1 hash of the file</span></span> | <span data-ttu-id="a0881-151">장치 이벤트</span><span class="sxs-lookup"><span data-stu-id="a0881-151">device events</span></span>|
|<span data-ttu-id="a0881-152">sha256</span><span class="sxs-lookup"><span data-stu-id="a0881-152">sha256</span></span> | <span data-ttu-id="a0881-153">파일의 SHA-256 해시</span><span class="sxs-lookup"><span data-stu-id="a0881-153">SHA-256 hash of the file</span></span> | <span data-ttu-id="a0881-154">장치 이벤트</span><span class="sxs-lookup"><span data-stu-id="a0881-154">device events</span></span>|
|<span data-ttu-id="a0881-155">MDATP 장치 ID</span><span class="sxs-lookup"><span data-stu-id="a0881-155">MDATP device ID</span></span> | <span data-ttu-id="a0881-156">끝점 장치 MDATP ID</span><span class="sxs-lookup"><span data-stu-id="a0881-156">endpoint device MDATP ID</span></span>|
|<span data-ttu-id="a0881-157">파일 크기</span><span class="sxs-lookup"><span data-stu-id="a0881-157">file size</span></span> | <span data-ttu-id="a0881-158">파일의 크기</span><span class="sxs-lookup"><span data-stu-id="a0881-158">size of the file</span></span>| <span data-ttu-id="a0881-159">SharePoint, OneDrive 및 장치 이벤트</span><span class="sxs-lookup"><span data-stu-id="a0881-159">SharePoint, OneDrive, and device events</span></span>|
|<span data-ttu-id="a0881-160">파일 경로</span><span class="sxs-lookup"><span data-stu-id="a0881-160">file path</span></span> | <span data-ttu-id="a0881-161">DLP 정책 일치와 관련된 항목의 절대 경로</span><span class="sxs-lookup"><span data-stu-id="a0881-161">the absolute path of the item involved with the DLP policy match</span></span> | <span data-ttu-id="a0881-162">SharePoint, OneDrive 및 장치 이벤트</span><span class="sxs-lookup"><span data-stu-id="a0881-162">SharePoint, OneDrive, and devices events</span></span>|
|<span data-ttu-id="a0881-163">전자 메일 받는 사람</span><span class="sxs-lookup"><span data-stu-id="a0881-163">email recipients</span></span> |<span data-ttu-id="a0881-164">전자 메일이 DLP 정책과 일치하는 중요한 항목인 경우 이 필드에는 해당 전자 메일의 받는 사람이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0881-164">if an email was the sensitive item that matched the DLP policy, this field includes the recipients of that email</span></span>| <span data-ttu-id="a0881-165">Exchange 이벤트</span><span class="sxs-lookup"><span data-stu-id="a0881-165">Exchange events</span></span>|
|<span data-ttu-id="a0881-166">전자 메일 제목</span><span class="sxs-lookup"><span data-stu-id="a0881-166">email subject</span></span> |<span data-ttu-id="a0881-167">DLP 정책과 일치하는 전자 메일의 제목</span><span class="sxs-lookup"><span data-stu-id="a0881-167">subject of the email that matched the DLP policy</span></span> |<span data-ttu-id="a0881-168">Exchange 이벤트</span><span class="sxs-lookup"><span data-stu-id="a0881-168">Exchange events</span></span>|
|<span data-ttu-id="a0881-169">전자 메일 첨부 파일</span><span class="sxs-lookup"><span data-stu-id="a0881-169">email attachments</span></span> | <span data-ttu-id="a0881-170">DLP 정책과 일치하는 전자 메일의 첨부 파일 이름</span><span class="sxs-lookup"><span data-stu-id="a0881-170">names of the attachments in the email that matched the DLP policy</span></span>| <span data-ttu-id="a0881-171">Exchange 이벤트</span><span class="sxs-lookup"><span data-stu-id="a0881-171">Exchange events</span></span>|
|<span data-ttu-id="a0881-172">사이트 소유자</span><span class="sxs-lookup"><span data-stu-id="a0881-172">site owner</span></span> |<span data-ttu-id="a0881-173">사이트 소유자의 이름</span><span class="sxs-lookup"><span data-stu-id="a0881-173">name of the site owner</span></span>| <span data-ttu-id="a0881-174">SharePoint 및 OneDrive 이벤트</span><span class="sxs-lookup"><span data-stu-id="a0881-174">SharePoint and OneDrive events</span></span>|
|<span data-ttu-id="a0881-175">사이트 URL</span><span class="sxs-lookup"><span data-stu-id="a0881-175">site URL</span></span> |<span data-ttu-id="a0881-176">DLP 정책이 일치하는 SharePoint OneDrive 사이트의 URL 전체</span><span class="sxs-lookup"><span data-stu-id="a0881-176">full of the URL of the SharePoint or OneDrive site where the DLP policy match occurred</span></span> |<span data-ttu-id="a0881-177">SharePoint 및 OneDrive 이벤트</span><span class="sxs-lookup"><span data-stu-id="a0881-177">SharePoint and OneDrive events</span></span>|
|<span data-ttu-id="a0881-178">만든 파일</span><span class="sxs-lookup"><span data-stu-id="a0881-178">file created</span></span> |<span data-ttu-id="a0881-179">DLP 정책과 일치하는 파일을 만들 때의 시간</span><span class="sxs-lookup"><span data-stu-id="a0881-179">time of creation of the file that matched the DLP policy</span></span> |<span data-ttu-id="a0881-180">SharePoint 및 OneDrive 이벤트</span><span class="sxs-lookup"><span data-stu-id="a0881-180">SharePoint and OneDrive events</span></span>|
|<span data-ttu-id="a0881-181">마지막으로 수정한 파일</span><span class="sxs-lookup"><span data-stu-id="a0881-181">file last modified</span></span> | <span data-ttu-id="a0881-182">DLP 정책과 일치하는 파일이 마지막으로 변경된 시간</span><span class="sxs-lookup"><span data-stu-id="a0881-182">the last time that the file that matched the DLP policy was changed</span></span> | <span data-ttu-id="a0881-183">SharePoint 및 OneDrive 이벤트</span><span class="sxs-lookup"><span data-stu-id="a0881-183">SharePoint and OneDrive events</span></span>|
|<span data-ttu-id="a0881-184">파일 크기</span><span class="sxs-lookup"><span data-stu-id="a0881-184">file size</span></span> | <span data-ttu-id="a0881-185">DLP 정책과 일치하는 파일의 크기</span><span class="sxs-lookup"><span data-stu-id="a0881-185">size of the file that matched the DLP policy</span></span> |<span data-ttu-id="a0881-186">SharePoint 및 OneDrive 이벤트</span><span class="sxs-lookup"><span data-stu-id="a0881-186">SharePoint and OneDrive events</span></span>|
|<span data-ttu-id="a0881-187">파일 소유자</span><span class="sxs-lookup"><span data-stu-id="a0881-187">file owner</span></span> |<span data-ttu-id="a0881-188">DLP 정책과 일치하는 파일의 소유자</span><span class="sxs-lookup"><span data-stu-id="a0881-188">owner of the file that matched the DLP policy</span></span> |<span data-ttu-id="a0881-189">SharePoint 및 OneDrive 이벤트</span><span class="sxs-lookup"><span data-stu-id="a0881-189">SharePoint and OneDrive events</span></span>|  

### <a name="policy-details"></a><span data-ttu-id="a0881-190">정책 세부 정보</span><span class="sxs-lookup"><span data-stu-id="a0881-190">Policy details</span></span>

|<span data-ttu-id="a0881-191">속성 이름</span><span class="sxs-lookup"><span data-stu-id="a0881-191">Property name</span></span> |<span data-ttu-id="a0881-192">설명</span><span class="sxs-lookup"><span data-stu-id="a0881-192">Description</span></span> |<span data-ttu-id="a0881-193">이벤트 유형</span><span class="sxs-lookup"><span data-stu-id="a0881-193">Event types</span></span> |
|---------|---------|---------|
|<span data-ttu-id="a0881-194">일치하는 DLP 정책</span><span class="sxs-lookup"><span data-stu-id="a0881-194">DLP policy matched</span></span> |<span data-ttu-id="a0881-195">일치하는 DLP 정책의 이름</span><span class="sxs-lookup"><span data-stu-id="a0881-195">name of the matched DLP policy</span></span> |<span data-ttu-id="a0881-196">모든 이벤트</span><span class="sxs-lookup"><span data-stu-id="a0881-196">all events</span></span>|
|<span data-ttu-id="a0881-197">일치하는 규칙</span><span class="sxs-lookup"><span data-stu-id="a0881-197">rule matched</span></span> |<span data-ttu-id="a0881-198">일치하는 DLP 정책 규칙의 이름</span><span class="sxs-lookup"><span data-stu-id="a0881-198">name of the matched DLP policy rule</span></span> |<span data-ttu-id="a0881-199">모든 이벤트</span><span class="sxs-lookup"><span data-stu-id="a0881-199">all events</span></span>|
|<span data-ttu-id="a0881-200">SIT(중요한 정보 유형) 검색</span><span class="sxs-lookup"><span data-stu-id="a0881-200">sensitive information types (SIT) detected</span></span>|<span data-ttu-id="a0881-201">DLP 정책 일치의 일부로 검색된 SITS</span><span class="sxs-lookup"><span data-stu-id="a0881-201">SITs that were detected as part of the DLP policy match</span></span> |<span data-ttu-id="a0881-202">모든 이벤트</span><span class="sxs-lookup"><span data-stu-id="a0881-202">all events</span></span>|
|<span data-ttu-id="a0881-203">수행한 작업</span><span class="sxs-lookup"><span data-stu-id="a0881-203">actions taken</span></span> |<span data-ttu-id="a0881-204">DLP 정책 일치를 유발한 작업을 수행했습니다.</span><span class="sxs-lookup"><span data-stu-id="a0881-204">actions that were taken that caused the DLP policy match</span></span>| <span data-ttu-id="a0881-205">모든 이벤트</span><span class="sxs-lookup"><span data-stu-id="a0881-205">all events</span></span>|
|<span data-ttu-id="a0881-206">위반 작업</span><span class="sxs-lookup"><span data-stu-id="a0881-206">violating action</span></span> | <span data-ttu-id="a0881-207">DLP 경고를 발생한 끝점 장치에 대한 작업</span><span class="sxs-lookup"><span data-stu-id="a0881-207">action on the endpoint device that raised the DLP alert</span></span>| <span data-ttu-id="a0881-208">장치 이벤트</span><span class="sxs-lookup"><span data-stu-id="a0881-208">device events</span></span> | 
|<span data-ttu-id="a0881-209">사용자 과도 정책</span><span class="sxs-lookup"><span data-stu-id="a0881-209">user overrode policy</span></span> |<span data-ttu-id="a0881-210">사용자가 정책 팁을 통해 정책을 오버라이드했기</span><span class="sxs-lookup"><span data-stu-id="a0881-210">did the user override the policy via a policy tip</span></span> | <span data-ttu-id="a0881-211">모든 이벤트</span><span class="sxs-lookup"><span data-stu-id="a0881-211">all events</span></span>|
|<span data-ttu-id="a0881-212">의회 정당성에 대한 사용</span><span class="sxs-lookup"><span data-stu-id="a0881-212">use override justification</span></span> |<span data-ttu-id="a0881-213">사용자가 해당 이유에 대해 제공한 이유 텍스트</span><span class="sxs-lookup"><span data-stu-id="a0881-213">the text of the reason provided by the user for the override</span></span> | <span data-ttu-id="a0881-214">모든 이벤트</span><span class="sxs-lookup"><span data-stu-id="a0881-214">all events</span></span>|   

## <a name="see-also"></a><span data-ttu-id="a0881-215">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a0881-215">See Also</span></span>

- [<span data-ttu-id="a0881-216">데이터 손실 방지 경고 대시보드 시작</span><span class="sxs-lookup"><span data-stu-id="a0881-216">Get started with the data loss prevention alert dashboard</span></span>](dlp-alerts-dashboard-get-started.md)
- [<span data-ttu-id="a0881-217">데이터 손실 방지로 시작하는 위치</span><span class="sxs-lookup"><span data-stu-id="a0881-217">Where to start with data loss prevention</span></span>](create-test-tune-dlp-policy.md#where-to-start-with-data-loss-prevention)