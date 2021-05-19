---
title: 활동 탐색기에서 보고된 작업의 레이블 지정
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 활동 탐색기에서 사용할 수 있는 레이블 지정 활동 목록입니다.
ms.openlocfilehash: d4f6884ad39b16aeb0345f0c976d6ad87f03c05a
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52532257"
---
# <a name="labeling-activities-that-are-available-in-activity-explorer"></a><span data-ttu-id="6d0d7-103">활동 탐색기에서 사용할 수 있는 레이블 지정 활동</span><span class="sxs-lookup"><span data-stu-id="6d0d7-103">Labeling activities that are available in Activity explorer</span></span>

## <a name="sensitivity-label-applied"></a><span data-ttu-id="6d0d7-104">적용된 민감도 레이블</span><span class="sxs-lookup"><span data-stu-id="6d0d7-104">Sensitivity label applied</span></span>

<span data-ttu-id="6d0d7-105">이 이벤트는 레이블이 지정되지 않은 문서에 레이블이 지정되거나 민감도 레이블이 있는 전자 메일을 보낼 때마다 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d0d7-105">This event is generated each time an unlabeled document is labeled or an email is sent with a sensitivity label.</span></span> 

- <span data-ttu-id="6d0d7-106">기본 응용 프로그램 및 웹 응용 프로그램에 Office 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d0d7-106">It is captured at the time of save in Office native applications and web applications.</span></span> 
- <span data-ttu-id="6d0d7-107">Azure Information Protection 추가 기능에서 발생 시 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d0d7-107">It is captured at the time of occurrence in Azure Information protection add-ins.</span></span> 
- <span data-ttu-id="6d0d7-108">레이블 이벤트 유형 필드 및 필터를 통해  레이블 업그레이드 및 다운그레이드 작업을 모니터링할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d0d7-108">Upgrade and downgrade labels actions can also be monitored via the *Label event type* field and filter.</span></span>   


|<span data-ttu-id="6d0d7-109">원본</span><span class="sxs-lookup"><span data-stu-id="6d0d7-109">Source</span></span>  |<span data-ttu-id="6d0d7-110">활동 탐색기에서 보고</span><span class="sxs-lookup"><span data-stu-id="6d0d7-110">Reported in activity explorer</span></span> | <span data-ttu-id="6d0d7-111">참고</span><span class="sxs-lookup"><span data-stu-id="6d0d7-111">Note</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="6d0d7-112">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="6d0d7-112">Word, Excel, PowerPoint</span></span>|<span data-ttu-id="6d0d7-113">예</span><span class="sxs-lookup"><span data-stu-id="6d0d7-113">yes</span></span> |
|<span data-ttu-id="6d0d7-114">Outlook</span><span class="sxs-lookup"><span data-stu-id="6d0d7-114">Outlook</span></span>| <span data-ttu-id="6d0d7-115">예</span><span class="sxs-lookup"><span data-stu-id="6d0d7-115">yes</span></span> |<span data-ttu-id="6d0d7-116">Win 32에서</span><span class="sxs-lookup"><span data-stu-id="6d0d7-116">from Win 32</span></span> |
|<span data-ttu-id="6d0d7-117">SharePoint 온라인 OneDrive</span><span class="sxs-lookup"><span data-stu-id="6d0d7-117">SharePoint online, OneDrive</span></span>|<span data-ttu-id="6d0d7-118">예</span><span class="sxs-lookup"><span data-stu-id="6d0d7-118">yes</span></span> | |
|<span data-ttu-id="6d0d7-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="6d0d7-119">Exchange</span></span>        |<span data-ttu-id="6d0d7-120">예</span><span class="sxs-lookup"><span data-stu-id="6d0d7-120">yes</span></span>         | |
|<span data-ttu-id="6d0d7-121">AIP(Azure Information Protection) 통합 클라이언트 및 AIP 통합 스캐너</span><span class="sxs-lookup"><span data-stu-id="6d0d7-121">Azure Information Protection (AIP) unified client and AIP unified scanner</span></span> |<span data-ttu-id="6d0d7-122">예</span><span class="sxs-lookup"><span data-stu-id="6d0d7-122">yes</span></span> |<span data-ttu-id="6d0d7-123">AIP *새 레이블 동작이* 활동 탐색기에서 *적용된 레이블에* 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d0d7-123">the AIP *new label* action is mapped to *label applied* in activity explorer</span></span>   |
|<span data-ttu-id="6d0d7-124">MIP(Microsoft Information Protection) SDK</span><span class="sxs-lookup"><span data-stu-id="6d0d7-124">Microsoft information protection (MIP) SDK</span></span>         |<span data-ttu-id="6d0d7-125">예</span><span class="sxs-lookup"><span data-stu-id="6d0d7-125">yes</span></span>|<span data-ttu-id="6d0d7-126">AIP *새 레이블 동작이* 활동 탐색기에서 *적용된 레이블에* 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d0d7-126">the AIP *new label* action is mapped to *label applied* in activity explorer</span></span>|
|<span data-ttu-id="6d0d7-127">RMS(권한 관리 서비스)</span><span class="sxs-lookup"><span data-stu-id="6d0d7-127">Rights Management Service (RMS)</span></span>         |<span data-ttu-id="6d0d7-128">해당 없음</span><span class="sxs-lookup"><span data-stu-id="6d0d7-128">not applicable</span></span>         | |
|<span data-ttu-id="6d0d7-129">Power BI 및 웹</span><span class="sxs-lookup"><span data-stu-id="6d0d7-129">Power BI desktop and web</span></span>        | <span data-ttu-id="6d0d7-130">아니요</span><span class="sxs-lookup"><span data-stu-id="6d0d7-130">no</span></span>| <span data-ttu-id="6d0d7-131">감사 로그에서 Microsoft 365 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d0d7-131">accessible in the Microsoft 365 audit logs</span></span>         |
|<span data-ttu-id="6d0d7-132">Microsoft Cloud App Security (MCAS)</span><span class="sxs-lookup"><span data-stu-id="6d0d7-132">Microsoft Cloud App Security (MCAS)</span></span>         |<span data-ttu-id="6d0d7-133">아니요</span><span class="sxs-lookup"><span data-stu-id="6d0d7-133">no</span></span>|         |

## <a name="sensitivity-label-changed"></a><span data-ttu-id="6d0d7-134">민감도 레이블 변경</span><span class="sxs-lookup"><span data-stu-id="6d0d7-134">Sensitivity label changed</span></span>

<span data-ttu-id="6d0d7-135">이 이벤트는 문서 또는 전자 메일에서 민감도 레이블이 업데이트될 때마다 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d0d7-135">This event is generated each time a sensitivity label is updated on the document or email.</span></span>

- <span data-ttu-id="6d0d7-136">AIP 통합 클라이언트, 통합 스캐너 및 MIP SDK 원본의 경우  *AIP* 업그레이드 레이블 및 다운그레이드 레이블 작업이 변경된 활동 탐색기 레이블에 *매핑됩니다.*</span><span class="sxs-lookup"><span data-stu-id="6d0d7-136">For the AIP Unified client, Unified Scanner and MIP SDK sources, the AIP *upgrade label* and *downgrade label* action maps to activity explorer *label changed*</span></span>

- <span data-ttu-id="6d0d7-137">기본 응용 프로그램 및 웹 응용 프로그램에서 저장 Office 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d0d7-137">It is captured at the point of save in Office native applications and web applications.</span></span> 
- <span data-ttu-id="6d0d7-138">Azure Information Protection 통합 클라이언트 추가 기능 및 스캐너 적용에서 발생 시 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d0d7-138">It is captured at the time of occurrence in Azure Information protection unified client add-ins and scanner enforcements</span></span>
- <span data-ttu-id="6d0d7-139">레이블 이벤트 유형 필드 및 필터를 통해  레이블 업그레이드 및 다운그레이드 작업을 모니터링할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d0d7-139">Upgrade and downgrade labels actions can also be monitored via the *Label event type* field and filter.</span></span> <span data-ttu-id="6d0d7-140">온라인 *및* 온라인을 제외한 SharePoint 텍스트도 OneDrive.</span><span class="sxs-lookup"><span data-stu-id="6d0d7-140">The *justification* text is also captured except for SharePoint Online and OneDrive.</span></span>
- <span data-ttu-id="6d0d7-141">Office 기본 앱에서 수행한 민감도 레이블 Outlook 파일 저장/전자 메일 보내기 작업 전에 생성된 마지막 작업을 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="6d0d7-141">Sensitivity labeling done in Office native apps on Outlook collects the last action that was generated before file save/email send actions.</span></span> <span data-ttu-id="6d0d7-142">예를 들어 사용자가 보내기 전에 전자 메일에서 레이블을 여러 번 변경하는 경우 전자 메일이 전송될 때 찾은 마지막 레이블이 감사 로그에 캡처된 다음 활동 탐색기에서 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d0d7-142">For example, if the user changes label on an email multiple times before sending, the last label found on the email when it is sent is captured in the audit log and then reported in activity explorer.</span></span> 


|<span data-ttu-id="6d0d7-143">원본</span><span class="sxs-lookup"><span data-stu-id="6d0d7-143">Source</span></span>  |<span data-ttu-id="6d0d7-144">활동 탐색기에서 보고</span><span class="sxs-lookup"><span data-stu-id="6d0d7-144">Reported in activity explorer</span></span>|<span data-ttu-id="6d0d7-145">참고</span><span class="sxs-lookup"><span data-stu-id="6d0d7-145">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="6d0d7-146">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="6d0d7-146">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="6d0d7-147">예</span><span class="sxs-lookup"><span data-stu-id="6d0d7-147">yes</span></span>         |
|<span data-ttu-id="6d0d7-148">Outlook</span><span class="sxs-lookup"><span data-stu-id="6d0d7-148">Outlook</span></span>         |<span data-ttu-id="6d0d7-149">예</span><span class="sxs-lookup"><span data-stu-id="6d0d7-149">yes</span></span>         |<span data-ttu-id="6d0d7-150">Win 32</span><span class="sxs-lookup"><span data-stu-id="6d0d7-150">Win 32</span></span>|
|<span data-ttu-id="6d0d7-151">SharePoint 온라인, OneDrive</span><span class="sxs-lookup"><span data-stu-id="6d0d7-151">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="6d0d7-152">예</span><span class="sxs-lookup"><span data-stu-id="6d0d7-152">yes</span></span>         |
|<span data-ttu-id="6d0d7-153">Exchange</span><span class="sxs-lookup"><span data-stu-id="6d0d7-153">Exchange</span></span>         |<span data-ttu-id="6d0d7-154">예</span><span class="sxs-lookup"><span data-stu-id="6d0d7-154">yes</span></span>         |
|<span data-ttu-id="6d0d7-155">AIP 통합 클라이언트</span><span class="sxs-lookup"><span data-stu-id="6d0d7-155">AIP unified client</span></span>         |<span data-ttu-id="6d0d7-156">예</span><span class="sxs-lookup"><span data-stu-id="6d0d7-156">yes</span></span>         |
|<span data-ttu-id="6d0d7-157">AIP 통합 스캐너</span><span class="sxs-lookup"><span data-stu-id="6d0d7-157">AIP unified scanner</span></span>         |<span data-ttu-id="6d0d7-158">예</span><span class="sxs-lookup"><span data-stu-id="6d0d7-158">yes</span></span>         |
|<span data-ttu-id="6d0d7-159">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="6d0d7-159">MIP SDK</span></span>         |<span data-ttu-id="6d0d7-160">예</span><span class="sxs-lookup"><span data-stu-id="6d0d7-160">yes</span></span>         |
|<span data-ttu-id="6d0d7-161">RMS 서비스</span><span class="sxs-lookup"><span data-stu-id="6d0d7-161">RMS service</span></span>         |<span data-ttu-id="6d0d7-162">해당 없음</span><span class="sxs-lookup"><span data-stu-id="6d0d7-162">not applicable</span></span>         |
|<span data-ttu-id="6d0d7-163">Power BI 및 웹</span><span class="sxs-lookup"><span data-stu-id="6d0d7-163">Power BI desktop and Web</span></span>         |<span data-ttu-id="6d0d7-164">아니요</span><span class="sxs-lookup"><span data-stu-id="6d0d7-164">no</span></span>         |<span data-ttu-id="6d0d7-165">감사 로그에서 Microsoft 365 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d0d7-165">accessible in the Microsoft 365 audit logs</span></span> |
|<span data-ttu-id="6d0d7-166">MCAS</span><span class="sxs-lookup"><span data-stu-id="6d0d7-166">MCAS</span></span>     |<span data-ttu-id="6d0d7-167">아니요</span><span class="sxs-lookup"><span data-stu-id="6d0d7-167">no</span></span>         |         |

## <a name="sensitivity-label-removed"></a><span data-ttu-id="6d0d7-168">민감도 레이블 제거됨</span><span class="sxs-lookup"><span data-stu-id="6d0d7-168">Sensitivity label removed</span></span>

<span data-ttu-id="6d0d7-169">이 이벤트는 파일이나 문서에서 민감도 레이블을 제거할 때마다 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d0d7-169">This event is generated each time a sensitivity label is removed from a file or document.</span></span>

- <span data-ttu-id="6d0d7-170">이 이벤트는 기본 응용 프로그램 및 웹 응용 프로그램에 Office 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d0d7-170">This event is captured at the time of save in Office native applications and web applications.</span></span>
- <span data-ttu-id="6d0d7-171">Azure Information Protection 추가 기능에서 발생 시 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d0d7-171">It is captured at the time of occurrence in Azure Information protection add-ins.</span></span> 
- <span data-ttu-id="6d0d7-172">기본 MIP 레이블을 Office 민감도 레이블을 Outlook 파일 저장/전자 메일 보내기 작업 전에 생성된 마지막 레이블 지정 이벤트를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="6d0d7-172">Sensitivity labeling, with Office native MIP label, on Outlook collects the last labeling event that was generated before file save/email send actions.</span></span>

|<span data-ttu-id="6d0d7-173">원본</span><span class="sxs-lookup"><span data-stu-id="6d0d7-173">Source</span></span>  |<span data-ttu-id="6d0d7-174">활동 탐색기에서 보고</span><span class="sxs-lookup"><span data-stu-id="6d0d7-174">Reported in activity explorer</span></span> | <span data-ttu-id="6d0d7-175">참고</span><span class="sxs-lookup"><span data-stu-id="6d0d7-175">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="6d0d7-176">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="6d0d7-176">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="6d0d7-177">예</span><span class="sxs-lookup"><span data-stu-id="6d0d7-177">yes</span></span>         |
|<span data-ttu-id="6d0d7-178">Outlook</span><span class="sxs-lookup"><span data-stu-id="6d0d7-178">Outlook</span></span>         |<span data-ttu-id="6d0d7-179">예</span><span class="sxs-lookup"><span data-stu-id="6d0d7-179">yes</span></span>         |<span data-ttu-id="6d0d7-180">Win 32</span><span class="sxs-lookup"><span data-stu-id="6d0d7-180">Win 32</span></span>|
|<span data-ttu-id="6d0d7-181">SharePoint 온라인, OneDrive</span><span class="sxs-lookup"><span data-stu-id="6d0d7-181">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="6d0d7-182">예</span><span class="sxs-lookup"><span data-stu-id="6d0d7-182">yes</span></span>         |
|<span data-ttu-id="6d0d7-183">Exchange</span><span class="sxs-lookup"><span data-stu-id="6d0d7-183">Exchange</span></span>         |<span data-ttu-id="6d0d7-184">예</span><span class="sxs-lookup"><span data-stu-id="6d0d7-184">yes</span></span>         |
|<span data-ttu-id="6d0d7-185">AIP 통합 클라이언트</span><span class="sxs-lookup"><span data-stu-id="6d0d7-185">AIP unified client</span></span>         |<span data-ttu-id="6d0d7-186">예</span><span class="sxs-lookup"><span data-stu-id="6d0d7-186">yes</span></span>         |<span data-ttu-id="6d0d7-187">AIP *레이블 제거 작업은* 활동 탐색기에서 레이블 제거 *동작에* 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d0d7-187">the AIP *remove label* action is mapped to the *label removed* action in activity explorer</span></span>|
|<span data-ttu-id="6d0d7-188">AIP 통합 스캐너</span><span class="sxs-lookup"><span data-stu-id="6d0d7-188">AIP unified scanner</span></span>         |<span data-ttu-id="6d0d7-189">예</span><span class="sxs-lookup"><span data-stu-id="6d0d7-189">yes</span></span>         |<span data-ttu-id="6d0d7-190">AIP *레이블 제거 작업은* 활동 탐색기에서 레이블 제거 *동작에* 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d0d7-190">the AIP *remove label* action is mapped to the *label removed* action in activity explorer</span></span> |
|<span data-ttu-id="6d0d7-191">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="6d0d7-191">MIP SDK</span></span>         |<span data-ttu-id="6d0d7-192">예</span><span class="sxs-lookup"><span data-stu-id="6d0d7-192">yes</span></span>         |<span data-ttu-id="6d0d7-193">AIP *레이블 제거 작업은* 활동 탐색기에서 레이블 제거 *동작에* 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d0d7-193">the AIP *remove label* action is mapped to the *label removed* action in activity explorer</span></span> |
|<span data-ttu-id="6d0d7-194">RMS 서비스</span><span class="sxs-lookup"><span data-stu-id="6d0d7-194">RMS service</span></span>         |<span data-ttu-id="6d0d7-195">해당 없음</span><span class="sxs-lookup"><span data-stu-id="6d0d7-195">not applicable</span></span>         |
|<span data-ttu-id="6d0d7-196">Power BI 및 웹</span><span class="sxs-lookup"><span data-stu-id="6d0d7-196">Power BI desktop and Web</span></span>         |<span data-ttu-id="6d0d7-197">아니요</span><span class="sxs-lookup"><span data-stu-id="6d0d7-197">no</span></span>         |<span data-ttu-id="6d0d7-198">감사 로그에서 Microsoft 365 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d0d7-198">accessible in the Microsoft 365 audit logs</span></span> |
|<span data-ttu-id="6d0d7-199">MCAS</span><span class="sxs-lookup"><span data-stu-id="6d0d7-199">MCAS</span></span>     |<span data-ttu-id="6d0d7-200">아니요</span><span class="sxs-lookup"><span data-stu-id="6d0d7-200">no</span></span>         |         |
 

## <a name="sensitivity-label-file-read"></a><span data-ttu-id="6d0d7-201">민감도 레이블 파일 읽기</span><span class="sxs-lookup"><span data-stu-id="6d0d7-201">Sensitivity label file read</span></span>

<span data-ttu-id="6d0d7-202">이 이벤트는 레이블이 지정되거나 보호된 문서를 열 때마다 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d0d7-202">This event is generated each time a sensitivity labeled or protected document is opened.</span></span>

|<span data-ttu-id="6d0d7-203">원본</span><span class="sxs-lookup"><span data-stu-id="6d0d7-203">Source</span></span>  |<span data-ttu-id="6d0d7-204">활동 탐색기에서 보고</span><span class="sxs-lookup"><span data-stu-id="6d0d7-204">Reported in activity explorer</span></span> | <span data-ttu-id="6d0d7-205">참고</span><span class="sxs-lookup"><span data-stu-id="6d0d7-205">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="6d0d7-206">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="6d0d7-206">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="6d0d7-207">예</span><span class="sxs-lookup"><span data-stu-id="6d0d7-207">yes</span></span>         |
|<span data-ttu-id="6d0d7-208">Outlook</span><span class="sxs-lookup"><span data-stu-id="6d0d7-208">Outlook</span></span>         |<span data-ttu-id="6d0d7-209">아니요</span><span class="sxs-lookup"><span data-stu-id="6d0d7-209">no</span></span>         |
|<span data-ttu-id="6d0d7-210">SharePoint 온라인, OneDrive</span><span class="sxs-lookup"><span data-stu-id="6d0d7-210">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="6d0d7-211">아니요</span><span class="sxs-lookup"><span data-stu-id="6d0d7-211">no</span></span>         |
|<span data-ttu-id="6d0d7-212">Exchange</span><span class="sxs-lookup"><span data-stu-id="6d0d7-212">Exchange</span></span>         |<span data-ttu-id="6d0d7-213">아니요</span><span class="sxs-lookup"><span data-stu-id="6d0d7-213">no</span></span>         |
|<span data-ttu-id="6d0d7-214">AIP 통합 클라이언트</span><span class="sxs-lookup"><span data-stu-id="6d0d7-214">AIP unified client</span></span>         |<span data-ttu-id="6d0d7-215">예</span><span class="sxs-lookup"><span data-stu-id="6d0d7-215">yes</span></span>         |<span data-ttu-id="6d0d7-216">AIP *액세스 작업이* 활동 탐색기에서 *파일* 읽기 작업으로 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d0d7-216">the AIP *access* action is mapped to the *file read* action in activity explorer</span></span>|
|<span data-ttu-id="6d0d7-217">AIP 통합 스캐너</span><span class="sxs-lookup"><span data-stu-id="6d0d7-217">AIP unified scanner</span></span>         |<span data-ttu-id="6d0d7-218">예</span><span class="sxs-lookup"><span data-stu-id="6d0d7-218">yes</span></span>         |<span data-ttu-id="6d0d7-219">AIP *액세스 작업이* 활동 탐색기에서 *파일* 읽기 작업으로 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d0d7-219">the AIP *access* action is mapped to the *file read* action in activity explorer</span></span>|
|<span data-ttu-id="6d0d7-220">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="6d0d7-220">MIP SDK</span></span>         |<span data-ttu-id="6d0d7-221">예</span><span class="sxs-lookup"><span data-stu-id="6d0d7-221">yes</span></span>         |<span data-ttu-id="6d0d7-222">AIP *액세스 작업이* 활동 탐색기에서 *파일* 읽기 작업으로 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d0d7-222">the AIP *access* action is mapped to the *file read* action in activity explorer</span></span>|
|<span data-ttu-id="6d0d7-223">RMS 서비스</span><span class="sxs-lookup"><span data-stu-id="6d0d7-223">RMS service</span></span>         |<span data-ttu-id="6d0d7-224">예</span><span class="sxs-lookup"><span data-stu-id="6d0d7-224">yes</span></span>         |<span data-ttu-id="6d0d7-225">액세스 *작업이* 활동 탐색기에서 *파일 읽기* 작업으로 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d0d7-225">the *access* action is mapped to the *file read* action in activity explorer</span></span> |
|<span data-ttu-id="6d0d7-226">Power BI 및 웹</span><span class="sxs-lookup"><span data-stu-id="6d0d7-226">Power BI desktop and Web</span></span>         |<span data-ttu-id="6d0d7-227">아니요</span><span class="sxs-lookup"><span data-stu-id="6d0d7-227">no</span></span>         |<span data-ttu-id="6d0d7-228">감사 로그에서 Microsoft 365 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d0d7-228">accessible in the Microsoft 365 audit logs</span></span> |
|<span data-ttu-id="6d0d7-229">MCAS</span><span class="sxs-lookup"><span data-stu-id="6d0d7-229">MCAS</span></span>     |<span data-ttu-id="6d0d7-230">아니요</span><span class="sxs-lookup"><span data-stu-id="6d0d7-230">no</span></span>         |         |


## <a name="files-discovered"></a><span data-ttu-id="6d0d7-231">검색된 파일</span><span class="sxs-lookup"><span data-stu-id="6d0d7-231">Files discovered</span></span>

<span data-ttu-id="6d0d7-232">이 이벤트는 AIP 스캐너를 사용하여 여러 위치에서 중요한 데이터를 검색하고 파일을 찾을 때마다 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d0d7-232">This event is generated each time files are discovered when AIP Scanner is used for scanning sensitive data in various locations and finds files.</span></span>

|<span data-ttu-id="6d0d7-233">원본</span><span class="sxs-lookup"><span data-stu-id="6d0d7-233">Source</span></span>  |<span data-ttu-id="6d0d7-234">활동 탐색기에서 보고</span><span class="sxs-lookup"><span data-stu-id="6d0d7-234">Reported in activity explorer</span></span> | <span data-ttu-id="6d0d7-235">참고</span><span class="sxs-lookup"><span data-stu-id="6d0d7-235">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="6d0d7-236">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="6d0d7-236">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="6d0d7-237">해당 없음</span><span class="sxs-lookup"><span data-stu-id="6d0d7-237">not applicable</span></span>         |
|<span data-ttu-id="6d0d7-238">Outlook</span><span class="sxs-lookup"><span data-stu-id="6d0d7-238">Outlook</span></span>         |<span data-ttu-id="6d0d7-239">해당 없음</span><span class="sxs-lookup"><span data-stu-id="6d0d7-239">not applicable</span></span>         |
|<span data-ttu-id="6d0d7-240">SharePoint 온라인, OneDrive</span><span class="sxs-lookup"><span data-stu-id="6d0d7-240">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="6d0d7-241">해당 없음</span><span class="sxs-lookup"><span data-stu-id="6d0d7-241">not applicable</span></span>         |
|<span data-ttu-id="6d0d7-242">Exchange</span><span class="sxs-lookup"><span data-stu-id="6d0d7-242">Exchange</span></span>         |<span data-ttu-id="6d0d7-243">해당 없음</span><span class="sxs-lookup"><span data-stu-id="6d0d7-243">not applicable</span></span>         |
|<span data-ttu-id="6d0d7-244">AIP 통합 클라이언트</span><span class="sxs-lookup"><span data-stu-id="6d0d7-244">AIP unified client</span></span>         |<span data-ttu-id="6d0d7-245">해당 없음</span><span class="sxs-lookup"><span data-stu-id="6d0d7-245">not applicable</span></span>       |
|<span data-ttu-id="6d0d7-246">AIP 통합 스캐너</span><span class="sxs-lookup"><span data-stu-id="6d0d7-246">AIP unified scanner</span></span>         |<span data-ttu-id="6d0d7-247">예</span><span class="sxs-lookup"><span data-stu-id="6d0d7-247">yes</span></span>         |<span data-ttu-id="6d0d7-248">AIP *검색 작업이* 활동 탐색기에서 검색된 파일에 매핑됩니다. </span><span class="sxs-lookup"><span data-stu-id="6d0d7-248">the AIP *discover* action is mapped to the *files discovered* action in activity explorer</span></span>|
|<span data-ttu-id="6d0d7-249">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="6d0d7-249">MIP SDK</span></span>         |<span data-ttu-id="6d0d7-250">예</span><span class="sxs-lookup"><span data-stu-id="6d0d7-250">yes</span></span>         |<span data-ttu-id="6d0d7-251">AIP *검색 작업이* 활동 탐색기에서 검색된 파일에 매핑됩니다. </span><span class="sxs-lookup"><span data-stu-id="6d0d7-251">the AIP *discover* action is mapped to the *file discovered* action in activity explorer</span></span>|
|<span data-ttu-id="6d0d7-252">RMS 서비스</span><span class="sxs-lookup"><span data-stu-id="6d0d7-252">RMS service</span></span>         |<span data-ttu-id="6d0d7-253">해당 없음</span><span class="sxs-lookup"><span data-stu-id="6d0d7-253">not applicable</span></span>         |
|<span data-ttu-id="6d0d7-254">Power BI 및 웹</span><span class="sxs-lookup"><span data-stu-id="6d0d7-254">Power BI desktop and Web</span></span>         |<span data-ttu-id="6d0d7-255">해당 없음</span><span class="sxs-lookup"><span data-stu-id="6d0d7-255">not applicable</span></span>         |
|<span data-ttu-id="6d0d7-256">MCAS</span><span class="sxs-lookup"><span data-stu-id="6d0d7-256">MCAS</span></span>     |<span data-ttu-id="6d0d7-257">해당 없음</span><span class="sxs-lookup"><span data-stu-id="6d0d7-257">not applicable</span></span>         |         |


## <a name="sensitivity-label-file-renamed"></a><span data-ttu-id="6d0d7-258">민감도 레이블 파일 이름 변경</span><span class="sxs-lookup"><span data-stu-id="6d0d7-258">Sensitivity label file renamed</span></span>

<span data-ttu-id="6d0d7-259">이 이벤트는 민감도 레이블이 있는 문서의 이름을 변경할 때마다 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d0d7-259">This event is generated each time a document with a sensitivity label is renamed.</span></span> 

|<span data-ttu-id="6d0d7-260">원본</span><span class="sxs-lookup"><span data-stu-id="6d0d7-260">Source</span></span>  | <span data-ttu-id="6d0d7-261">활동 탐색기에서 보고</span><span class="sxs-lookup"><span data-stu-id="6d0d7-261">Reported in activity explorer</span></span> | <span data-ttu-id="6d0d7-262">참고</span><span class="sxs-lookup"><span data-stu-id="6d0d7-262">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="6d0d7-263">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="6d0d7-263">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="6d0d7-264">예</span><span class="sxs-lookup"><span data-stu-id="6d0d7-264">yes</span></span>         |
|<span data-ttu-id="6d0d7-265">Outlook</span><span class="sxs-lookup"><span data-stu-id="6d0d7-265">Outlook</span></span>         |<span data-ttu-id="6d0d7-266">해당 없음</span><span class="sxs-lookup"><span data-stu-id="6d0d7-266">not applicable</span></span>         |
|<span data-ttu-id="6d0d7-267">SharePoint 온라인, OneDrive</span><span class="sxs-lookup"><span data-stu-id="6d0d7-267">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="6d0d7-268">아니요</span><span class="sxs-lookup"><span data-stu-id="6d0d7-268">no</span></span>        |
|<span data-ttu-id="6d0d7-269">Exchange</span><span class="sxs-lookup"><span data-stu-id="6d0d7-269">Exchange</span></span>         |<span data-ttu-id="6d0d7-270">해당 없음</span><span class="sxs-lookup"><span data-stu-id="6d0d7-270">not applicable</span></span>         |
|<span data-ttu-id="6d0d7-271">AIP 통합 클라이언트</span><span class="sxs-lookup"><span data-stu-id="6d0d7-271">AIP unified client</span></span>         |<span data-ttu-id="6d0d7-272">아니요</span><span class="sxs-lookup"><span data-stu-id="6d0d7-272">no</span></span>         |
|<span data-ttu-id="6d0d7-273">AIP 통합 스캐너</span><span class="sxs-lookup"><span data-stu-id="6d0d7-273">AIP unified scanner</span></span>         |<span data-ttu-id="6d0d7-274">아니요</span><span class="sxs-lookup"><span data-stu-id="6d0d7-274">no</span></span>         |
|<span data-ttu-id="6d0d7-275">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="6d0d7-275">MIP SDK</span></span>         |<span data-ttu-id="6d0d7-276">아니요</span><span class="sxs-lookup"><span data-stu-id="6d0d7-276">no</span></span>         |
|<span data-ttu-id="6d0d7-277">RMS 서비스</span><span class="sxs-lookup"><span data-stu-id="6d0d7-277">RMS service</span></span>         |<span data-ttu-id="6d0d7-278">아니요</span><span class="sxs-lookup"><span data-stu-id="6d0d7-278">no</span></span>      |
|<span data-ttu-id="6d0d7-279">Power BI 및 웹</span><span class="sxs-lookup"><span data-stu-id="6d0d7-279">Power BI desktop and Web</span></span>         |<span data-ttu-id="6d0d7-280">아니요</span><span class="sxs-lookup"><span data-stu-id="6d0d7-280">no</span></span>         |
|<span data-ttu-id="6d0d7-281">MCAS</span><span class="sxs-lookup"><span data-stu-id="6d0d7-281">MCAS</span></span>     |<span data-ttu-id="6d0d7-282">아니요</span><span class="sxs-lookup"><span data-stu-id="6d0d7-282">no</span></span>         |         |


## <a name="file-removed"></a><span data-ttu-id="6d0d7-283">파일 제거됨</span><span class="sxs-lookup"><span data-stu-id="6d0d7-283">File removed</span></span>

<span data-ttu-id="6d0d7-284">이 이벤트는 AIP 스캐너가 이전에 검색한 파일이 제거된 것으로 감지될 때마다 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d0d7-284">This event is generated each time the AIP scanner detects that a previously scanned file has been removed.</span></span>

|<span data-ttu-id="6d0d7-285">원본</span><span class="sxs-lookup"><span data-stu-id="6d0d7-285">Source</span></span>  |<span data-ttu-id="6d0d7-286">활동 탐색기에서 보고</span><span class="sxs-lookup"><span data-stu-id="6d0d7-286">Reported in activity explorer</span></span> | <span data-ttu-id="6d0d7-287">참고</span><span class="sxs-lookup"><span data-stu-id="6d0d7-287">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="6d0d7-288">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="6d0d7-288">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="6d0d7-289">해당 없음</span><span class="sxs-lookup"><span data-stu-id="6d0d7-289">not applicable</span></span>         |
|<span data-ttu-id="6d0d7-290">Outlook</span><span class="sxs-lookup"><span data-stu-id="6d0d7-290">Outlook</span></span>         |<span data-ttu-id="6d0d7-291">해당 없음</span><span class="sxs-lookup"><span data-stu-id="6d0d7-291">not applicable</span></span>         |
|<span data-ttu-id="6d0d7-292">SharePoint 온라인, OneDrive</span><span class="sxs-lookup"><span data-stu-id="6d0d7-292">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="6d0d7-293">해당 없음</span><span class="sxs-lookup"><span data-stu-id="6d0d7-293">not applicable</span></span>           |
|<span data-ttu-id="6d0d7-294">Exchange</span><span class="sxs-lookup"><span data-stu-id="6d0d7-294">Exchange</span></span>         |<span data-ttu-id="6d0d7-295">해당 없음</span><span class="sxs-lookup"><span data-stu-id="6d0d7-295">not applicable</span></span>         |
|<span data-ttu-id="6d0d7-296">AIP 통합 클라이언트</span><span class="sxs-lookup"><span data-stu-id="6d0d7-296">AIP unified client</span></span>         |<span data-ttu-id="6d0d7-297">해당 없음</span><span class="sxs-lookup"><span data-stu-id="6d0d7-297">not applicable</span></span>            |
|<span data-ttu-id="6d0d7-298">AIP 통합 스캐너</span><span class="sxs-lookup"><span data-stu-id="6d0d7-298">AIP unified scanner</span></span>         |<span data-ttu-id="6d0d7-299">예</span><span class="sxs-lookup"><span data-stu-id="6d0d7-299">yes</span></span>         |
|<span data-ttu-id="6d0d7-300">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="6d0d7-300">MIP SDK</span></span>         |<span data-ttu-id="6d0d7-301">해당 없음</span><span class="sxs-lookup"><span data-stu-id="6d0d7-301">not applicable</span></span>            |
|<span data-ttu-id="6d0d7-302">RMS 서비스</span><span class="sxs-lookup"><span data-stu-id="6d0d7-302">RMS service</span></span>         |<span data-ttu-id="6d0d7-303">해당 없음</span><span class="sxs-lookup"><span data-stu-id="6d0d7-303">not applicable</span></span>         |
|<span data-ttu-id="6d0d7-304">Power BI 및 웹</span><span class="sxs-lookup"><span data-stu-id="6d0d7-304">Power BI desktop and Web</span></span>         |<span data-ttu-id="6d0d7-305">해당 없음</span><span class="sxs-lookup"><span data-stu-id="6d0d7-305">not applicable</span></span>  |
|<span data-ttu-id="6d0d7-306">MCAS</span><span class="sxs-lookup"><span data-stu-id="6d0d7-306">MCAS</span></span>     |<span data-ttu-id="6d0d7-307">해당 없음</span><span class="sxs-lookup"><span data-stu-id="6d0d7-307">not applicable</span></span>        |         |

### <a name="protection-applied"></a><span data-ttu-id="6d0d7-308">적용된 보호</span><span class="sxs-lookup"><span data-stu-id="6d0d7-308">Protection applied</span></span>

<span data-ttu-id="6d0d7-309">이 이벤트는 레이블이 없는 항목에 처음 보호가 수동으로 추가될 때 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d0d7-309">This event is generated the first-time protection is added manually to an item that does not have a label.</span></span>

|<span data-ttu-id="6d0d7-310">원본</span><span class="sxs-lookup"><span data-stu-id="6d0d7-310">Source</span></span>  |<span data-ttu-id="6d0d7-311">활동 탐색기에서 보고</span><span class="sxs-lookup"><span data-stu-id="6d0d7-311">Reported in activity explorer</span></span> | <span data-ttu-id="6d0d7-312">참고</span><span class="sxs-lookup"><span data-stu-id="6d0d7-312">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="6d0d7-313">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="6d0d7-313">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="6d0d7-314">아니요</span><span class="sxs-lookup"><span data-stu-id="6d0d7-314">no</span></span>         |
|<span data-ttu-id="6d0d7-315">Outlook</span><span class="sxs-lookup"><span data-stu-id="6d0d7-315">Outlook</span></span>         |<span data-ttu-id="6d0d7-316">아니요</span><span class="sxs-lookup"><span data-stu-id="6d0d7-316">no</span></span>         |
|<span data-ttu-id="6d0d7-317">SharePoint 온라인, OneDrive</span><span class="sxs-lookup"><span data-stu-id="6d0d7-317">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="6d0d7-318">해당 없음</span><span class="sxs-lookup"><span data-stu-id="6d0d7-318">not applicable</span></span>           |
|<span data-ttu-id="6d0d7-319">Exchange</span><span class="sxs-lookup"><span data-stu-id="6d0d7-319">Exchange</span></span>         |<span data-ttu-id="6d0d7-320">아니요</span><span class="sxs-lookup"><span data-stu-id="6d0d7-320">no</span></span>       |
|<span data-ttu-id="6d0d7-321">AIP 통합 클라이언트</span><span class="sxs-lookup"><span data-stu-id="6d0d7-321">AIP unified client</span></span>         |<span data-ttu-id="6d0d7-322">예</span><span class="sxs-lookup"><span data-stu-id="6d0d7-322">yes</span></span>            |
|<span data-ttu-id="6d0d7-323">AIP 통합 스캐너</span><span class="sxs-lookup"><span data-stu-id="6d0d7-323">AIP unified scanner</span></span>         |<span data-ttu-id="6d0d7-324">해당 없음</span><span class="sxs-lookup"><span data-stu-id="6d0d7-324">not applicable</span></span>         |
|<span data-ttu-id="6d0d7-325">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="6d0d7-325">MIP SDK</span></span>         |<span data-ttu-id="6d0d7-326">예</span><span class="sxs-lookup"><span data-stu-id="6d0d7-326">yes</span></span>            |
|<span data-ttu-id="6d0d7-327">RMS 서비스</span><span class="sxs-lookup"><span data-stu-id="6d0d7-327">RMS service</span></span>         |<span data-ttu-id="6d0d7-328">해당 없음</span><span class="sxs-lookup"><span data-stu-id="6d0d7-328">not applicable</span></span>         |
|<span data-ttu-id="6d0d7-329">Power BI 및 웹</span><span class="sxs-lookup"><span data-stu-id="6d0d7-329">Power BI desktop and Web</span></span>         |<span data-ttu-id="6d0d7-330">해당 없음</span><span class="sxs-lookup"><span data-stu-id="6d0d7-330">not applicable</span></span>            |
|<span data-ttu-id="6d0d7-331">MCAS</span><span class="sxs-lookup"><span data-stu-id="6d0d7-331">MCAS</span></span>     |<span data-ttu-id="6d0d7-332">해당 없음</span><span class="sxs-lookup"><span data-stu-id="6d0d7-332">not applicable</span></span>        |         |

## <a name="protection-changed"></a><span data-ttu-id="6d0d7-333">보호가 변경된 경우</span><span class="sxs-lookup"><span data-stu-id="6d0d7-333">Protection changed</span></span>

<span data-ttu-id="6d0d7-334">이 이벤트는 기록되지 않은 문서의 보호가 수동으로 변경될 때마다 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d0d7-334">This event is generated each time the protection on an unlabeled document is changed manually.</span></span>

|<span data-ttu-id="6d0d7-335">원본</span><span class="sxs-lookup"><span data-stu-id="6d0d7-335">Source</span></span>  |<span data-ttu-id="6d0d7-336">활동 탐색기에서 보고</span><span class="sxs-lookup"><span data-stu-id="6d0d7-336">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="6d0d7-337">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="6d0d7-337">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="6d0d7-338">아니요</span><span class="sxs-lookup"><span data-stu-id="6d0d7-338">no</span></span>         |
|<span data-ttu-id="6d0d7-339">Outlook</span><span class="sxs-lookup"><span data-stu-id="6d0d7-339">Outlook</span></span>         |<span data-ttu-id="6d0d7-340">아니요</span><span class="sxs-lookup"><span data-stu-id="6d0d7-340">no</span></span>         |
|<span data-ttu-id="6d0d7-341">SharePoint 온라인, OneDrive</span><span class="sxs-lookup"><span data-stu-id="6d0d7-341">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="6d0d7-342">해당 없음</span><span class="sxs-lookup"><span data-stu-id="6d0d7-342">not applicable</span></span>           |
|<span data-ttu-id="6d0d7-343">Exchange</span><span class="sxs-lookup"><span data-stu-id="6d0d7-343">Exchange</span></span>         |<span data-ttu-id="6d0d7-344">아니요</span><span class="sxs-lookup"><span data-stu-id="6d0d7-344">no</span></span>       |
|<span data-ttu-id="6d0d7-345">AIP 통합 클라이언트</span><span class="sxs-lookup"><span data-stu-id="6d0d7-345">AIP unified client</span></span>         |<span data-ttu-id="6d0d7-346">예</span><span class="sxs-lookup"><span data-stu-id="6d0d7-346">yes</span></span>            |
|<span data-ttu-id="6d0d7-347">AIP 통합 스캐너</span><span class="sxs-lookup"><span data-stu-id="6d0d7-347">AIP unified scanner</span></span>         |<span data-ttu-id="6d0d7-348">해당 없음</span><span class="sxs-lookup"><span data-stu-id="6d0d7-348">not applicable</span></span>         |
|<span data-ttu-id="6d0d7-349">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="6d0d7-349">MIP SDK</span></span>         |<span data-ttu-id="6d0d7-350">예</span><span class="sxs-lookup"><span data-stu-id="6d0d7-350">yes</span></span>            |
|<span data-ttu-id="6d0d7-351">RMS 서비스</span><span class="sxs-lookup"><span data-stu-id="6d0d7-351">RMS service</span></span>         |<span data-ttu-id="6d0d7-352">해당 없음</span><span class="sxs-lookup"><span data-stu-id="6d0d7-352">not applicable</span></span>         |
|<span data-ttu-id="6d0d7-353">Power BI 및 웹</span><span class="sxs-lookup"><span data-stu-id="6d0d7-353">Power BI desktop and Web</span></span>         |<span data-ttu-id="6d0d7-354">해당 없음</span><span class="sxs-lookup"><span data-stu-id="6d0d7-354">not applicable</span></span>            |
|<span data-ttu-id="6d0d7-355">MCAS</span><span class="sxs-lookup"><span data-stu-id="6d0d7-355">MCAS</span></span>     |<span data-ttu-id="6d0d7-356">해당 없음</span><span class="sxs-lookup"><span data-stu-id="6d0d7-356">not applicable</span></span>        |

## <a name="protection-removed"></a><span data-ttu-id="6d0d7-357">보호 제거됨</span><span class="sxs-lookup"><span data-stu-id="6d0d7-357">Protection removed</span></span>

<span data-ttu-id="6d0d7-358">이 이벤트는 기록되지 않은 문서의 보호가 수동으로 변경될 때마다 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d0d7-358">This event is generated each time the protection on an unlabeled document is changed manually.</span></span>

|<span data-ttu-id="6d0d7-359">원본</span><span class="sxs-lookup"><span data-stu-id="6d0d7-359">Source</span></span>  |<span data-ttu-id="6d0d7-360">활동 탐색기에서 보고</span><span class="sxs-lookup"><span data-stu-id="6d0d7-360">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="6d0d7-361">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="6d0d7-361">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="6d0d7-362">아니요</span><span class="sxs-lookup"><span data-stu-id="6d0d7-362">no</span></span>         |
|<span data-ttu-id="6d0d7-363">Outlook</span><span class="sxs-lookup"><span data-stu-id="6d0d7-363">Outlook</span></span>         |<span data-ttu-id="6d0d7-364">아니요</span><span class="sxs-lookup"><span data-stu-id="6d0d7-364">no</span></span>         |
|<span data-ttu-id="6d0d7-365">SharePoint 온라인, OneDrive</span><span class="sxs-lookup"><span data-stu-id="6d0d7-365">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="6d0d7-366">해당 없음</span><span class="sxs-lookup"><span data-stu-id="6d0d7-366">not applicable</span></span>           |
|<span data-ttu-id="6d0d7-367">Exchange</span><span class="sxs-lookup"><span data-stu-id="6d0d7-367">Exchange</span></span>         |<span data-ttu-id="6d0d7-368">아니요</span><span class="sxs-lookup"><span data-stu-id="6d0d7-368">no</span></span>       |
|<span data-ttu-id="6d0d7-369">AIP 통합 클라이언트</span><span class="sxs-lookup"><span data-stu-id="6d0d7-369">AIP unified client</span></span>         |<span data-ttu-id="6d0d7-370">예</span><span class="sxs-lookup"><span data-stu-id="6d0d7-370">yes</span></span>            |
|<span data-ttu-id="6d0d7-371">AIP 통합 스캐너</span><span class="sxs-lookup"><span data-stu-id="6d0d7-371">AIP unified scanner</span></span>         |<span data-ttu-id="6d0d7-372">해당 없음</span><span class="sxs-lookup"><span data-stu-id="6d0d7-372">not applicable</span></span>         |
|<span data-ttu-id="6d0d7-373">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="6d0d7-373">MIP SDK</span></span>         |<span data-ttu-id="6d0d7-374">예</span><span class="sxs-lookup"><span data-stu-id="6d0d7-374">yes</span></span>            |
|<span data-ttu-id="6d0d7-375">RMS 서비스</span><span class="sxs-lookup"><span data-stu-id="6d0d7-375">RMS service</span></span>         |<span data-ttu-id="6d0d7-376">해당 없음</span><span class="sxs-lookup"><span data-stu-id="6d0d7-376">not applicable</span></span>         |
|<span data-ttu-id="6d0d7-377">Power BI 및 웹</span><span class="sxs-lookup"><span data-stu-id="6d0d7-377">Power BI desktop and Web</span></span>         |<span data-ttu-id="6d0d7-378">해당 없음</span><span class="sxs-lookup"><span data-stu-id="6d0d7-378">not applicable</span></span>            |
|<span data-ttu-id="6d0d7-379">MCAS</span><span class="sxs-lookup"><span data-stu-id="6d0d7-379">MCAS</span></span>     |<span data-ttu-id="6d0d7-380">해당 없음</span><span class="sxs-lookup"><span data-stu-id="6d0d7-380">not applicable</span></span>        |

## <a name="dlp-policy-matched"></a><span data-ttu-id="6d0d7-381">일치하는 DLP 정책</span><span class="sxs-lookup"><span data-stu-id="6d0d7-381">DLP policy matched</span></span>

<span data-ttu-id="6d0d7-382">이 이벤트는 문서 또는 전자 메일에서 DLP 정책이 일치할 때마다 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d0d7-382">This event is generated each time a DLP policy is matched on a document or an email.</span></span>

|<span data-ttu-id="6d0d7-383">원본</span><span class="sxs-lookup"><span data-stu-id="6d0d7-383">Source</span></span>  |<span data-ttu-id="6d0d7-384">활동 탐색기에서 보고</span><span class="sxs-lookup"><span data-stu-id="6d0d7-384">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="6d0d7-385">Exchange</span><span class="sxs-lookup"><span data-stu-id="6d0d7-385">Exchange</span></span>         |<span data-ttu-id="6d0d7-386">예</span><span class="sxs-lookup"><span data-stu-id="6d0d7-386">yes</span></span>       |
|<span data-ttu-id="6d0d7-387">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="6d0d7-387">SharePoint Online</span></span>|<span data-ttu-id="6d0d7-388">예</span><span class="sxs-lookup"><span data-stu-id="6d0d7-388">yes</span></span>          |
|<span data-ttu-id="6d0d7-389">OneDrive</span><span class="sxs-lookup"><span data-stu-id="6d0d7-389">OneDrive</span></span> |<span data-ttu-id="6d0d7-390">예</span><span class="sxs-lookup"><span data-stu-id="6d0d7-390">yes</span></span>|
|<span data-ttu-id="6d0d7-391">Teams</span><span class="sxs-lookup"><span data-stu-id="6d0d7-391">Teams</span></span> |<span data-ttu-id="6d0d7-392">예</span><span class="sxs-lookup"><span data-stu-id="6d0d7-392">yes</span></span>   |
|<span data-ttu-id="6d0d7-393">Windows 10 장치</span><span class="sxs-lookup"><span data-stu-id="6d0d7-393">Windows 10 devices</span></span>         |<span data-ttu-id="6d0d7-394">예</span><span class="sxs-lookup"><span data-stu-id="6d0d7-394">yes</span></span> |
|<span data-ttu-id="6d0d7-395">MAC</span><span class="sxs-lookup"><span data-stu-id="6d0d7-395">MAC</span></span>         |<span data-ttu-id="6d0d7-396">아니요</span><span class="sxs-lookup"><span data-stu-id="6d0d7-396">no</span></span>     |
|<span data-ttu-id="6d0d7-397">On-premises</span><span class="sxs-lookup"><span data-stu-id="6d0d7-397">on-premises</span></span>         |<span data-ttu-id="6d0d7-398">아니요</span><span class="sxs-lookup"><span data-stu-id="6d0d7-398">no</span></span>|
|<span data-ttu-id="6d0d7-399">MCAS</span><span class="sxs-lookup"><span data-stu-id="6d0d7-399">MCAS</span></span>     |<span data-ttu-id="6d0d7-400">아니요</span><span class="sxs-lookup"><span data-stu-id="6d0d7-400">no</span></span>        | 

<span data-ttu-id="6d0d7-401">끝점 DLP(Windows 10 장치)에 대한 이벤트는 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="6d0d7-401">The events for Windows 10 Devices (Endpoint DLP) are:</span></span>

- <span data-ttu-id="6d0d7-402">파일이 삭제되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6d0d7-402">file deleted</span></span>
- <span data-ttu-id="6d0d7-403">만든 파일</span><span class="sxs-lookup"><span data-stu-id="6d0d7-403">file created</span></span>
- <span data-ttu-id="6d0d7-404">파일을 클립보드로 복사함</span><span class="sxs-lookup"><span data-stu-id="6d0d7-404">file copied to clipboard</span></span>
- <span data-ttu-id="6d0d7-405">파일 수정</span><span class="sxs-lookup"><span data-stu-id="6d0d7-405">file modified</span></span>
- <span data-ttu-id="6d0d7-406">파일 읽기</span><span class="sxs-lookup"><span data-stu-id="6d0d7-406">file read</span></span>
- <span data-ttu-id="6d0d7-407">인쇄된 파일</span><span class="sxs-lookup"><span data-stu-id="6d0d7-407">file printed</span></span>
- <span data-ttu-id="6d0d7-408">파일 이름 변경</span><span class="sxs-lookup"><span data-stu-id="6d0d7-408">file renamed</span></span>
- <span data-ttu-id="6d0d7-409">파일을 네트워크 공유에 복사함</span><span class="sxs-lookup"><span data-stu-id="6d0d7-409">file copied to network share</span></span>
- <span data-ttu-id="6d0d7-410">허용되지 않은 앱에서 액세스하는 파일</span><span class="sxs-lookup"><span data-stu-id="6d0d7-410">file accessed by unallowed app</span></span>


## <a name="retention-label-applied"></a><span data-ttu-id="6d0d7-411">적용된 보존 레이블</span><span class="sxs-lookup"><span data-stu-id="6d0d7-411">Retention label applied</span></span> 

<span data-ttu-id="6d0d7-412">이 이벤트는 레이블이 지정되지 않은 문서에 레이블이 지정되거나 보존 레이블이 있는 전자 메일을 보낼 때마다 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d0d7-412">This event is generated each time an unlabeled document is labeled or an email is sent with a retention label.</span></span>

- <span data-ttu-id="6d0d7-413">이 문서는 문서 저장 시와 전자 메일 전송 시에 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d0d7-413">It is captured at the time of save for a document and at time of sending for an email.</span></span>

|<span data-ttu-id="6d0d7-414">원본</span><span class="sxs-lookup"><span data-stu-id="6d0d7-414">Source</span></span>  |<span data-ttu-id="6d0d7-415">활동 탐색기에서 보고</span><span class="sxs-lookup"><span data-stu-id="6d0d7-415">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="6d0d7-416">Exchange</span><span class="sxs-lookup"><span data-stu-id="6d0d7-416">Exchange</span></span>         |<span data-ttu-id="6d0d7-417">아니요</span><span class="sxs-lookup"><span data-stu-id="6d0d7-417">no</span></span>       |
|<span data-ttu-id="6d0d7-418">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="6d0d7-418">SharePoint Online</span></span>|<span data-ttu-id="6d0d7-419">예</span><span class="sxs-lookup"><span data-stu-id="6d0d7-419">yes</span></span>          |
|<span data-ttu-id="6d0d7-420">OneDrive</span><span class="sxs-lookup"><span data-stu-id="6d0d7-420">OneDrive</span></span> |<span data-ttu-id="6d0d7-421">예</span><span class="sxs-lookup"><span data-stu-id="6d0d7-421">yes</span></span>|

## <a name="retention-label-changed"></a><span data-ttu-id="6d0d7-422">보존 레이블 변경</span><span class="sxs-lookup"><span data-stu-id="6d0d7-422">Retention label changed</span></span>

<span data-ttu-id="6d0d7-423">이 이벤트는 문서 또는 전자 메일에서 레이블이 업데이트될 때마다 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d0d7-423">This event is generated each time a label is updated on a document or email.</span></span>

- <span data-ttu-id="6d0d7-424">이 문서는 문서 저장 시와 전자 메일 전송 시에 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d0d7-424">It is captured at the time of save for a document and at time of sending for an email.</span></span>

|<span data-ttu-id="6d0d7-425">원본</span><span class="sxs-lookup"><span data-stu-id="6d0d7-425">Source</span></span>  |<span data-ttu-id="6d0d7-426">활동 탐색기에서 보고</span><span class="sxs-lookup"><span data-stu-id="6d0d7-426">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="6d0d7-427">Exchange</span><span class="sxs-lookup"><span data-stu-id="6d0d7-427">Exchange</span></span>         |<span data-ttu-id="6d0d7-428">아니요</span><span class="sxs-lookup"><span data-stu-id="6d0d7-428">no</span></span>       |
|<span data-ttu-id="6d0d7-429">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="6d0d7-429">SharePoint Online</span></span>|<span data-ttu-id="6d0d7-430">예</span><span class="sxs-lookup"><span data-stu-id="6d0d7-430">yes</span></span>          |
|<span data-ttu-id="6d0d7-431">OneDrive</span><span class="sxs-lookup"><span data-stu-id="6d0d7-431">OneDrive</span></span> |<span data-ttu-id="6d0d7-432">예</span><span class="sxs-lookup"><span data-stu-id="6d0d7-432">yes</span></span>|
 
## <a name="retention-label-removed"></a><span data-ttu-id="6d0d7-433">보존 레이블 제거됨</span><span class="sxs-lookup"><span data-stu-id="6d0d7-433">Retention label removed</span></span>

<span data-ttu-id="6d0d7-434">이 이벤트는 파일이나 문서에서 레이블을 제거할 때마다 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d0d7-434">This event is generated each time a label is removed from a file or document.</span></span>

- <span data-ttu-id="6d0d7-435">이 문서는 문서 저장 시와 전자 메일 전송 시에 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d0d7-435">It is captured at the time of save for a document and at time of sending for an email.</span></span>

|<span data-ttu-id="6d0d7-436">원본</span><span class="sxs-lookup"><span data-stu-id="6d0d7-436">Source</span></span>  |<span data-ttu-id="6d0d7-437">활동 탐색기에서 보고</span><span class="sxs-lookup"><span data-stu-id="6d0d7-437">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="6d0d7-438">Exchange</span><span class="sxs-lookup"><span data-stu-id="6d0d7-438">Exchange</span></span>         |<span data-ttu-id="6d0d7-439">아니요</span><span class="sxs-lookup"><span data-stu-id="6d0d7-439">no</span></span>       |
|<span data-ttu-id="6d0d7-440">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="6d0d7-440">SharePoint Online</span></span>|<span data-ttu-id="6d0d7-441">예</span><span class="sxs-lookup"><span data-stu-id="6d0d7-441">yes</span></span>          |
|<span data-ttu-id="6d0d7-442">OneDrive</span><span class="sxs-lookup"><span data-stu-id="6d0d7-442">OneDrive</span></span> |<span data-ttu-id="6d0d7-443">예</span><span class="sxs-lookup"><span data-stu-id="6d0d7-443">yes</span></span>|


## <a name="known-issues"></a><span data-ttu-id="6d0d7-444">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="6d0d7-444">Known issues</span></span>
  
- <span data-ttu-id="6d0d7-445">최종 사용자에게 권장 레이블 도구 팁이 표시되어 있는 경우 캡처되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6d0d7-445">When the recommended label tool tip is shown to an end user, it is not captured.</span></span> <span data-ttu-id="6d0d7-446">그러나 사용자가 권장 레이블을 적용하도록 선택한 경우 레이블은  적용 방법 필드에 *권장으로 표시됩니다.*</span><span class="sxs-lookup"><span data-stu-id="6d0d7-446">But if the user chooses to apply the recommended label, the label will be shown under the *How applied* field as *Recommended*</span></span>  

- <span data-ttu-id="6d0d7-447">현재 Sharepoint 및 2013에서 민감도 레이블 다운그레이드에 사유 텍스트를 사용할 수 OneDrive.</span><span class="sxs-lookup"><span data-stu-id="6d0d7-447">Justification text is not currently available on sensitivity label downgrade from Sharepoint and OneDrive.</span></span>  

- <span data-ttu-id="6d0d7-448">중요한 정보 유형은 현재 Word, Excel, PowerPoint, Outlook, SharePoint Online 및 OneDrive.</span><span class="sxs-lookup"><span data-stu-id="6d0d7-448">Sensitive information types are currently not available for autolabeling activities from Word, Excel, PowerPoint, and Outlook, as well as SharePoint Online, and OneDrive.</span></span>
