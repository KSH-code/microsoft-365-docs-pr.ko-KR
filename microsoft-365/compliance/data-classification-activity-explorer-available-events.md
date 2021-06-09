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
# <a name="labeling-activities-that-are-available-in-activity-explorer"></a><span data-ttu-id="44d15-103">활동 탐색기에서 사용할 수 있는 레이블 지정 활동</span><span class="sxs-lookup"><span data-stu-id="44d15-103">Labeling activities that are available in Activity explorer</span></span>

## <a name="sensitivity-label-applied"></a><span data-ttu-id="44d15-104">적용된 민감도 레이블</span><span class="sxs-lookup"><span data-stu-id="44d15-104">Sensitivity label applied</span></span>

<span data-ttu-id="44d15-105">이 이벤트는 레이블이 지정되지 않은 문서에 레이블이 지정되거나 민감도 레이블이 있는 전자 메일을 보낼 때마다 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d15-105">This event is generated each time an unlabeled document is labeled or an email is sent with a sensitivity label.</span></span> 

- <span data-ttu-id="44d15-106">기본 응용 프로그램 및 웹 응용 프로그램에 Office 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d15-106">It is captured at the time of save in Office native applications and web applications.</span></span> 
- <span data-ttu-id="44d15-107">Azure Information Protection 추가 기능에서 발생 시 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d15-107">It is captured at the time of occurrence in Azure Information protection add-ins.</span></span> 
- <span data-ttu-id="44d15-108">레이블 이벤트 유형 필드 및 필터를 통해  레이블 업그레이드 및 다운그레이드 작업을 모니터링할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44d15-108">Upgrade and downgrade labels actions can also be monitored via the *Label event type* field and filter.</span></span>   


|<span data-ttu-id="44d15-109">원본</span><span class="sxs-lookup"><span data-stu-id="44d15-109">Source</span></span>  |<span data-ttu-id="44d15-110">활동 탐색기에서 보고</span><span class="sxs-lookup"><span data-stu-id="44d15-110">Reported in activity explorer</span></span> | <span data-ttu-id="44d15-111">참고</span><span class="sxs-lookup"><span data-stu-id="44d15-111">Note</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="44d15-112">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="44d15-112">Word, Excel, PowerPoint</span></span>|<span data-ttu-id="44d15-113">예</span><span class="sxs-lookup"><span data-stu-id="44d15-113">yes</span></span> |
|<span data-ttu-id="44d15-114">Outlook</span><span class="sxs-lookup"><span data-stu-id="44d15-114">Outlook</span></span>| <span data-ttu-id="44d15-115">예</span><span class="sxs-lookup"><span data-stu-id="44d15-115">yes</span></span> |<span data-ttu-id="44d15-116">Win 32에서</span><span class="sxs-lookup"><span data-stu-id="44d15-116">from Win 32</span></span> |
|<span data-ttu-id="44d15-117">SharePoint 온라인 OneDrive</span><span class="sxs-lookup"><span data-stu-id="44d15-117">SharePoint online, OneDrive</span></span>|<span data-ttu-id="44d15-118">예</span><span class="sxs-lookup"><span data-stu-id="44d15-118">yes</span></span> | |
|<span data-ttu-id="44d15-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="44d15-119">Exchange</span></span>        |<span data-ttu-id="44d15-120">예</span><span class="sxs-lookup"><span data-stu-id="44d15-120">yes</span></span>         | |
|<span data-ttu-id="44d15-121">AIP(Azure Information Protection) 통합 클라이언트 및 AIP 통합 스캐너</span><span class="sxs-lookup"><span data-stu-id="44d15-121">Azure Information Protection (AIP) unified client and AIP unified scanner</span></span> |<span data-ttu-id="44d15-122">예</span><span class="sxs-lookup"><span data-stu-id="44d15-122">yes</span></span> |<span data-ttu-id="44d15-123">AIP *새 레이블 동작이* 활동 탐색기에서 *적용된 레이블에* 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d15-123">the AIP *new label* action is mapped to *label applied* in activity explorer</span></span>   |
|<span data-ttu-id="44d15-124">MIP(Microsoft Information Protection) SDK</span><span class="sxs-lookup"><span data-stu-id="44d15-124">Microsoft information protection (MIP) SDK</span></span>         |<span data-ttu-id="44d15-125">예</span><span class="sxs-lookup"><span data-stu-id="44d15-125">yes</span></span>|<span data-ttu-id="44d15-126">AIP *새 레이블 동작이* 활동 탐색기에서 *적용된 레이블에* 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d15-126">the AIP *new label* action is mapped to *label applied* in activity explorer</span></span>|
|<span data-ttu-id="44d15-127">RMS(권한 관리 서비스)</span><span class="sxs-lookup"><span data-stu-id="44d15-127">Rights Management Service (RMS)</span></span>         |<span data-ttu-id="44d15-128">해당 없음</span><span class="sxs-lookup"><span data-stu-id="44d15-128">not applicable</span></span>         | |
|<span data-ttu-id="44d15-129">Power BI 및 웹</span><span class="sxs-lookup"><span data-stu-id="44d15-129">Power BI desktop and web</span></span>        | <span data-ttu-id="44d15-130">아니요</span><span class="sxs-lookup"><span data-stu-id="44d15-130">no</span></span>| <span data-ttu-id="44d15-131">감사 로그에서 Microsoft 365 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44d15-131">accessible in the Microsoft 365 audit logs</span></span>         |
|<span data-ttu-id="44d15-132">Microsoft Cloud App Security (MCAS)</span><span class="sxs-lookup"><span data-stu-id="44d15-132">Microsoft Cloud App Security (MCAS)</span></span>         |<span data-ttu-id="44d15-133">아니요</span><span class="sxs-lookup"><span data-stu-id="44d15-133">no</span></span>|         |

## <a name="sensitivity-label-changed"></a><span data-ttu-id="44d15-134">민감도 레이블 변경</span><span class="sxs-lookup"><span data-stu-id="44d15-134">Sensitivity label changed</span></span>

<span data-ttu-id="44d15-135">이 이벤트는 문서 또는 전자 메일에서 민감도 레이블이 업데이트될 때마다 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d15-135">This event is generated each time a sensitivity label is updated on the document or email.</span></span>

- <span data-ttu-id="44d15-136">AIP 통합 클라이언트, 통합 스캐너 및 MIP SDK 원본의 경우  *AIP* 업그레이드 레이블 및 다운그레이드 레이블 작업이 변경된 활동 탐색기 레이블에 *매핑됩니다.*</span><span class="sxs-lookup"><span data-stu-id="44d15-136">For the AIP Unified client, Unified Scanner and MIP SDK sources, the AIP *upgrade label* and *downgrade label* action maps to activity explorer *label changed*</span></span>

- <span data-ttu-id="44d15-137">기본 응용 프로그램 및 웹 응용 프로그램에서 저장 Office 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d15-137">It is captured at the point of save in Office native applications and web applications.</span></span> 
- <span data-ttu-id="44d15-138">Azure Information Protection 통합 클라이언트 추가 기능 및 스캐너 적용에서 발생 시 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d15-138">It is captured at the time of occurrence in Azure Information protection unified client add-ins and scanner enforcements</span></span>
- <span data-ttu-id="44d15-139">레이블 이벤트 유형 필드 및 필터를 통해  레이블 업그레이드 및 다운그레이드 작업을 모니터링할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44d15-139">Upgrade and downgrade labels actions can also be monitored via the *Label event type* field and filter.</span></span> <span data-ttu-id="44d15-140">온라인 *및* 온라인을 제외한 SharePoint 텍스트도 OneDrive.</span><span class="sxs-lookup"><span data-stu-id="44d15-140">The *justification* text is also captured except for SharePoint Online and OneDrive.</span></span>
- <span data-ttu-id="44d15-141">Office 기본 앱에서 수행한 민감도 레이블 Outlook 파일 저장/전자 메일 보내기 작업 전에 생성된 마지막 작업을 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="44d15-141">Sensitivity labeling done in Office native apps on Outlook collects the last action that was generated before file save/email send actions.</span></span> <span data-ttu-id="44d15-142">예를 들어 사용자가 보내기 전에 전자 메일에서 레이블을 여러 번 변경하는 경우 전자 메일이 전송될 때 찾은 마지막 레이블이 감사 로그에 캡처된 다음 활동 탐색기에서 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d15-142">For example, if the user changes label on an email multiple times before sending, the last label found on the email when it is sent is captured in the audit log and then reported in activity explorer.</span></span> 


|<span data-ttu-id="44d15-143">원본</span><span class="sxs-lookup"><span data-stu-id="44d15-143">Source</span></span>  |<span data-ttu-id="44d15-144">활동 탐색기에서 보고</span><span class="sxs-lookup"><span data-stu-id="44d15-144">Reported in activity explorer</span></span>|<span data-ttu-id="44d15-145">참고</span><span class="sxs-lookup"><span data-stu-id="44d15-145">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="44d15-146">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="44d15-146">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="44d15-147">예</span><span class="sxs-lookup"><span data-stu-id="44d15-147">yes</span></span>         |
|<span data-ttu-id="44d15-148">Outlook</span><span class="sxs-lookup"><span data-stu-id="44d15-148">Outlook</span></span>         |<span data-ttu-id="44d15-149">예</span><span class="sxs-lookup"><span data-stu-id="44d15-149">yes</span></span>         |<span data-ttu-id="44d15-150">Win 32</span><span class="sxs-lookup"><span data-stu-id="44d15-150">Win 32</span></span>|
|<span data-ttu-id="44d15-151">SharePoint 온라인, OneDrive</span><span class="sxs-lookup"><span data-stu-id="44d15-151">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="44d15-152">예</span><span class="sxs-lookup"><span data-stu-id="44d15-152">yes</span></span>         |
|<span data-ttu-id="44d15-153">Exchange</span><span class="sxs-lookup"><span data-stu-id="44d15-153">Exchange</span></span>         |<span data-ttu-id="44d15-154">예</span><span class="sxs-lookup"><span data-stu-id="44d15-154">yes</span></span>         |
|<span data-ttu-id="44d15-155">AIP 통합 클라이언트</span><span class="sxs-lookup"><span data-stu-id="44d15-155">AIP unified client</span></span>         |<span data-ttu-id="44d15-156">예</span><span class="sxs-lookup"><span data-stu-id="44d15-156">yes</span></span>         |
|<span data-ttu-id="44d15-157">AIP 통합 스캐너</span><span class="sxs-lookup"><span data-stu-id="44d15-157">AIP unified scanner</span></span>         |<span data-ttu-id="44d15-158">예</span><span class="sxs-lookup"><span data-stu-id="44d15-158">yes</span></span>         |
|<span data-ttu-id="44d15-159">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="44d15-159">MIP SDK</span></span>         |<span data-ttu-id="44d15-160">예</span><span class="sxs-lookup"><span data-stu-id="44d15-160">yes</span></span>         |
|<span data-ttu-id="44d15-161">RMS 서비스</span><span class="sxs-lookup"><span data-stu-id="44d15-161">RMS service</span></span>         |<span data-ttu-id="44d15-162">해당 없음</span><span class="sxs-lookup"><span data-stu-id="44d15-162">not applicable</span></span>         |
|<span data-ttu-id="44d15-163">Power BI 및 웹</span><span class="sxs-lookup"><span data-stu-id="44d15-163">Power BI desktop and Web</span></span>         |<span data-ttu-id="44d15-164">아니요</span><span class="sxs-lookup"><span data-stu-id="44d15-164">no</span></span>         |<span data-ttu-id="44d15-165">감사 로그에서 Microsoft 365 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44d15-165">accessible in the Microsoft 365 audit logs</span></span> |
|<span data-ttu-id="44d15-166">MCAS</span><span class="sxs-lookup"><span data-stu-id="44d15-166">MCAS</span></span>     |<span data-ttu-id="44d15-167">아니요</span><span class="sxs-lookup"><span data-stu-id="44d15-167">no</span></span>         |         |

## <a name="sensitivity-label-removed"></a><span data-ttu-id="44d15-168">민감도 레이블 제거됨</span><span class="sxs-lookup"><span data-stu-id="44d15-168">Sensitivity label removed</span></span>

<span data-ttu-id="44d15-169">이 이벤트는 파일이나 문서에서 민감도 레이블을 제거할 때마다 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d15-169">This event is generated each time a sensitivity label is removed from a file or document.</span></span>

- <span data-ttu-id="44d15-170">이 이벤트는 기본 응용 프로그램 및 웹 응용 프로그램에 Office 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d15-170">This event is captured at the time of save in Office native applications and web applications.</span></span>
- <span data-ttu-id="44d15-171">Azure Information Protection 추가 기능에서 발생 시 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d15-171">It is captured at the time of occurrence in Azure Information protection add-ins.</span></span> 
- <span data-ttu-id="44d15-172">기본 MIP 레이블을 Office 민감도 레이블을 Outlook 파일 저장/전자 메일 보내기 작업 전에 생성된 마지막 레이블 지정 이벤트를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="44d15-172">Sensitivity labeling, with Office native MIP label, on Outlook collects the last labeling event that was generated before file save/email send actions.</span></span>

|<span data-ttu-id="44d15-173">원본</span><span class="sxs-lookup"><span data-stu-id="44d15-173">Source</span></span>  |<span data-ttu-id="44d15-174">활동 탐색기에서 보고</span><span class="sxs-lookup"><span data-stu-id="44d15-174">Reported in activity explorer</span></span> | <span data-ttu-id="44d15-175">참고</span><span class="sxs-lookup"><span data-stu-id="44d15-175">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="44d15-176">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="44d15-176">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="44d15-177">예</span><span class="sxs-lookup"><span data-stu-id="44d15-177">yes</span></span>         |
|<span data-ttu-id="44d15-178">Outlook</span><span class="sxs-lookup"><span data-stu-id="44d15-178">Outlook</span></span>         |<span data-ttu-id="44d15-179">예</span><span class="sxs-lookup"><span data-stu-id="44d15-179">yes</span></span>         |<span data-ttu-id="44d15-180">Win 32</span><span class="sxs-lookup"><span data-stu-id="44d15-180">Win 32</span></span>|
|<span data-ttu-id="44d15-181">SharePoint 온라인, OneDrive</span><span class="sxs-lookup"><span data-stu-id="44d15-181">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="44d15-182">예</span><span class="sxs-lookup"><span data-stu-id="44d15-182">yes</span></span>         |
|<span data-ttu-id="44d15-183">Exchange</span><span class="sxs-lookup"><span data-stu-id="44d15-183">Exchange</span></span>         |<span data-ttu-id="44d15-184">예</span><span class="sxs-lookup"><span data-stu-id="44d15-184">yes</span></span>         |
|<span data-ttu-id="44d15-185">AIP 통합 클라이언트</span><span class="sxs-lookup"><span data-stu-id="44d15-185">AIP unified client</span></span>         |<span data-ttu-id="44d15-186">예</span><span class="sxs-lookup"><span data-stu-id="44d15-186">yes</span></span>         |<span data-ttu-id="44d15-187">AIP *레이블 제거 작업은* 활동 탐색기에서 레이블 제거 *동작에* 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d15-187">the AIP *remove label* action is mapped to the *label removed* action in activity explorer</span></span>|
|<span data-ttu-id="44d15-188">AIP 통합 스캐너</span><span class="sxs-lookup"><span data-stu-id="44d15-188">AIP unified scanner</span></span>         |<span data-ttu-id="44d15-189">예</span><span class="sxs-lookup"><span data-stu-id="44d15-189">yes</span></span>         |<span data-ttu-id="44d15-190">AIP *레이블 제거 작업은* 활동 탐색기에서 레이블 제거 *동작에* 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d15-190">the AIP *remove label* action is mapped to the *label removed* action in activity explorer</span></span> |
|<span data-ttu-id="44d15-191">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="44d15-191">MIP SDK</span></span>         |<span data-ttu-id="44d15-192">예</span><span class="sxs-lookup"><span data-stu-id="44d15-192">yes</span></span>         |<span data-ttu-id="44d15-193">AIP *레이블 제거 작업은* 활동 탐색기에서 레이블 제거 *동작에* 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d15-193">the AIP *remove label* action is mapped to the *label removed* action in activity explorer</span></span> |
|<span data-ttu-id="44d15-194">RMS 서비스</span><span class="sxs-lookup"><span data-stu-id="44d15-194">RMS service</span></span>         |<span data-ttu-id="44d15-195">해당 없음</span><span class="sxs-lookup"><span data-stu-id="44d15-195">not applicable</span></span>         |
|<span data-ttu-id="44d15-196">Power BI 및 웹</span><span class="sxs-lookup"><span data-stu-id="44d15-196">Power BI desktop and Web</span></span>         |<span data-ttu-id="44d15-197">아니요</span><span class="sxs-lookup"><span data-stu-id="44d15-197">no</span></span>         |<span data-ttu-id="44d15-198">감사 로그에서 Microsoft 365 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44d15-198">accessible in the Microsoft 365 audit logs</span></span> |
|<span data-ttu-id="44d15-199">MCAS</span><span class="sxs-lookup"><span data-stu-id="44d15-199">MCAS</span></span>     |<span data-ttu-id="44d15-200">아니요</span><span class="sxs-lookup"><span data-stu-id="44d15-200">no</span></span>         |         |
 

## <a name="sensitivity-label-file-read"></a><span data-ttu-id="44d15-201">민감도 레이블 파일 읽기</span><span class="sxs-lookup"><span data-stu-id="44d15-201">Sensitivity label file read</span></span>

<span data-ttu-id="44d15-202">이 이벤트는 레이블이 지정되거나 보호된 문서를 열 때마다 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d15-202">This event is generated each time a sensitivity labeled or protected document is opened.</span></span>

|<span data-ttu-id="44d15-203">원본</span><span class="sxs-lookup"><span data-stu-id="44d15-203">Source</span></span>  |<span data-ttu-id="44d15-204">활동 탐색기에서 보고</span><span class="sxs-lookup"><span data-stu-id="44d15-204">Reported in activity explorer</span></span> | <span data-ttu-id="44d15-205">참고</span><span class="sxs-lookup"><span data-stu-id="44d15-205">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="44d15-206">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="44d15-206">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="44d15-207">예</span><span class="sxs-lookup"><span data-stu-id="44d15-207">yes</span></span>         |
|<span data-ttu-id="44d15-208">Outlook</span><span class="sxs-lookup"><span data-stu-id="44d15-208">Outlook</span></span>         |<span data-ttu-id="44d15-209">아니요</span><span class="sxs-lookup"><span data-stu-id="44d15-209">no</span></span>         |
|<span data-ttu-id="44d15-210">SharePoint 온라인, OneDrive</span><span class="sxs-lookup"><span data-stu-id="44d15-210">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="44d15-211">아니요</span><span class="sxs-lookup"><span data-stu-id="44d15-211">no</span></span>         |
|<span data-ttu-id="44d15-212">Exchange</span><span class="sxs-lookup"><span data-stu-id="44d15-212">Exchange</span></span>         |<span data-ttu-id="44d15-213">아니요</span><span class="sxs-lookup"><span data-stu-id="44d15-213">no</span></span>         |
|<span data-ttu-id="44d15-214">AIP 통합 클라이언트</span><span class="sxs-lookup"><span data-stu-id="44d15-214">AIP unified client</span></span>         |<span data-ttu-id="44d15-215">예</span><span class="sxs-lookup"><span data-stu-id="44d15-215">yes</span></span>         |<span data-ttu-id="44d15-216">AIP *액세스 작업이* 활동 탐색기에서 *파일* 읽기 작업으로 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d15-216">the AIP *access* action is mapped to the *file read* action in activity explorer</span></span>|
|<span data-ttu-id="44d15-217">AIP 통합 스캐너</span><span class="sxs-lookup"><span data-stu-id="44d15-217">AIP unified scanner</span></span>         |<span data-ttu-id="44d15-218">예</span><span class="sxs-lookup"><span data-stu-id="44d15-218">yes</span></span>         |<span data-ttu-id="44d15-219">AIP *액세스 작업이* 활동 탐색기에서 *파일* 읽기 작업으로 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d15-219">the AIP *access* action is mapped to the *file read* action in activity explorer</span></span>|
|<span data-ttu-id="44d15-220">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="44d15-220">MIP SDK</span></span>         |<span data-ttu-id="44d15-221">예</span><span class="sxs-lookup"><span data-stu-id="44d15-221">yes</span></span>         |<span data-ttu-id="44d15-222">AIP *액세스 작업이* 활동 탐색기에서 *파일* 읽기 작업으로 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d15-222">the AIP *access* action is mapped to the *file read* action in activity explorer</span></span>|
|<span data-ttu-id="44d15-223">RMS 서비스</span><span class="sxs-lookup"><span data-stu-id="44d15-223">RMS service</span></span>         |<span data-ttu-id="44d15-224">예</span><span class="sxs-lookup"><span data-stu-id="44d15-224">yes</span></span>         |<span data-ttu-id="44d15-225">액세스 *작업이* 활동 탐색기에서 *파일 읽기* 작업으로 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d15-225">the *access* action is mapped to the *file read* action in activity explorer</span></span> |
|<span data-ttu-id="44d15-226">Power BI 및 웹</span><span class="sxs-lookup"><span data-stu-id="44d15-226">Power BI desktop and Web</span></span>         |<span data-ttu-id="44d15-227">아니요</span><span class="sxs-lookup"><span data-stu-id="44d15-227">no</span></span>         |<span data-ttu-id="44d15-228">감사 로그에서 Microsoft 365 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44d15-228">accessible in the Microsoft 365 audit logs</span></span> |
|<span data-ttu-id="44d15-229">MCAS</span><span class="sxs-lookup"><span data-stu-id="44d15-229">MCAS</span></span>     |<span data-ttu-id="44d15-230">아니요</span><span class="sxs-lookup"><span data-stu-id="44d15-230">no</span></span>         |         |


## <a name="files-discovered"></a><span data-ttu-id="44d15-231">검색된 파일</span><span class="sxs-lookup"><span data-stu-id="44d15-231">Files discovered</span></span>

<span data-ttu-id="44d15-232">이 이벤트는 AIP 스캐너를 사용하여 여러 위치에서 중요한 데이터를 검색하고 파일을 찾을 때마다 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d15-232">This event is generated each time files are discovered when AIP Scanner is used for scanning sensitive data in various locations and finds files.</span></span>

|<span data-ttu-id="44d15-233">원본</span><span class="sxs-lookup"><span data-stu-id="44d15-233">Source</span></span>  |<span data-ttu-id="44d15-234">활동 탐색기에서 보고</span><span class="sxs-lookup"><span data-stu-id="44d15-234">Reported in activity explorer</span></span> | <span data-ttu-id="44d15-235">참고</span><span class="sxs-lookup"><span data-stu-id="44d15-235">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="44d15-236">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="44d15-236">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="44d15-237">해당 없음</span><span class="sxs-lookup"><span data-stu-id="44d15-237">not applicable</span></span>         |
|<span data-ttu-id="44d15-238">Outlook</span><span class="sxs-lookup"><span data-stu-id="44d15-238">Outlook</span></span>         |<span data-ttu-id="44d15-239">해당 없음</span><span class="sxs-lookup"><span data-stu-id="44d15-239">not applicable</span></span>         |
|<span data-ttu-id="44d15-240">SharePoint 온라인, OneDrive</span><span class="sxs-lookup"><span data-stu-id="44d15-240">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="44d15-241">해당 없음</span><span class="sxs-lookup"><span data-stu-id="44d15-241">not applicable</span></span>         |
|<span data-ttu-id="44d15-242">Exchange</span><span class="sxs-lookup"><span data-stu-id="44d15-242">Exchange</span></span>         |<span data-ttu-id="44d15-243">해당 없음</span><span class="sxs-lookup"><span data-stu-id="44d15-243">not applicable</span></span>         |
|<span data-ttu-id="44d15-244">AIP 통합 클라이언트</span><span class="sxs-lookup"><span data-stu-id="44d15-244">AIP unified client</span></span>         |<span data-ttu-id="44d15-245">해당 없음</span><span class="sxs-lookup"><span data-stu-id="44d15-245">not applicable</span></span>       |
|<span data-ttu-id="44d15-246">AIP 통합 스캐너</span><span class="sxs-lookup"><span data-stu-id="44d15-246">AIP unified scanner</span></span>         |<span data-ttu-id="44d15-247">예</span><span class="sxs-lookup"><span data-stu-id="44d15-247">yes</span></span>         |<span data-ttu-id="44d15-248">AIP *검색 작업이* 활동 탐색기에서 검색된 파일에 매핑됩니다. </span><span class="sxs-lookup"><span data-stu-id="44d15-248">the AIP *discover* action is mapped to the *files discovered* action in activity explorer</span></span>|
|<span data-ttu-id="44d15-249">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="44d15-249">MIP SDK</span></span>         |<span data-ttu-id="44d15-250">예</span><span class="sxs-lookup"><span data-stu-id="44d15-250">yes</span></span>         |<span data-ttu-id="44d15-251">AIP *검색 작업이* 활동 탐색기에서 검색된 파일에 매핑됩니다. </span><span class="sxs-lookup"><span data-stu-id="44d15-251">the AIP *discover* action is mapped to the *file discovered* action in activity explorer</span></span>|
|<span data-ttu-id="44d15-252">RMS 서비스</span><span class="sxs-lookup"><span data-stu-id="44d15-252">RMS service</span></span>         |<span data-ttu-id="44d15-253">해당 없음</span><span class="sxs-lookup"><span data-stu-id="44d15-253">not applicable</span></span>         |
|<span data-ttu-id="44d15-254">Power BI 및 웹</span><span class="sxs-lookup"><span data-stu-id="44d15-254">Power BI desktop and Web</span></span>         |<span data-ttu-id="44d15-255">해당 없음</span><span class="sxs-lookup"><span data-stu-id="44d15-255">not applicable</span></span>         |
|<span data-ttu-id="44d15-256">MCAS</span><span class="sxs-lookup"><span data-stu-id="44d15-256">MCAS</span></span>     |<span data-ttu-id="44d15-257">해당 없음</span><span class="sxs-lookup"><span data-stu-id="44d15-257">not applicable</span></span>         |         |


## <a name="sensitivity-label-file-renamed"></a><span data-ttu-id="44d15-258">민감도 레이블 파일 이름 변경</span><span class="sxs-lookup"><span data-stu-id="44d15-258">Sensitivity label file renamed</span></span>

<span data-ttu-id="44d15-259">이 이벤트는 민감도 레이블이 있는 문서의 이름을 변경할 때마다 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d15-259">This event is generated each time a document with a sensitivity label is renamed.</span></span> 

|<span data-ttu-id="44d15-260">원본</span><span class="sxs-lookup"><span data-stu-id="44d15-260">Source</span></span>  | <span data-ttu-id="44d15-261">활동 탐색기에서 보고</span><span class="sxs-lookup"><span data-stu-id="44d15-261">Reported in activity explorer</span></span> | <span data-ttu-id="44d15-262">참고</span><span class="sxs-lookup"><span data-stu-id="44d15-262">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="44d15-263">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="44d15-263">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="44d15-264">예</span><span class="sxs-lookup"><span data-stu-id="44d15-264">yes</span></span>         |
|<span data-ttu-id="44d15-265">Outlook</span><span class="sxs-lookup"><span data-stu-id="44d15-265">Outlook</span></span>         |<span data-ttu-id="44d15-266">해당 없음</span><span class="sxs-lookup"><span data-stu-id="44d15-266">not applicable</span></span>         |
|<span data-ttu-id="44d15-267">SharePoint 온라인, OneDrive</span><span class="sxs-lookup"><span data-stu-id="44d15-267">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="44d15-268">아니요</span><span class="sxs-lookup"><span data-stu-id="44d15-268">no</span></span>        |
|<span data-ttu-id="44d15-269">Exchange</span><span class="sxs-lookup"><span data-stu-id="44d15-269">Exchange</span></span>         |<span data-ttu-id="44d15-270">해당 없음</span><span class="sxs-lookup"><span data-stu-id="44d15-270">not applicable</span></span>         |
|<span data-ttu-id="44d15-271">AIP 통합 클라이언트</span><span class="sxs-lookup"><span data-stu-id="44d15-271">AIP unified client</span></span>         |<span data-ttu-id="44d15-272">아니요</span><span class="sxs-lookup"><span data-stu-id="44d15-272">no</span></span>         |
|<span data-ttu-id="44d15-273">AIP 통합 스캐너</span><span class="sxs-lookup"><span data-stu-id="44d15-273">AIP unified scanner</span></span>         |<span data-ttu-id="44d15-274">아니요</span><span class="sxs-lookup"><span data-stu-id="44d15-274">no</span></span>         |
|<span data-ttu-id="44d15-275">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="44d15-275">MIP SDK</span></span>         |<span data-ttu-id="44d15-276">아니요</span><span class="sxs-lookup"><span data-stu-id="44d15-276">no</span></span>         |
|<span data-ttu-id="44d15-277">RMS 서비스</span><span class="sxs-lookup"><span data-stu-id="44d15-277">RMS service</span></span>         |<span data-ttu-id="44d15-278">아니요</span><span class="sxs-lookup"><span data-stu-id="44d15-278">no</span></span>      |
|<span data-ttu-id="44d15-279">Power BI 및 웹</span><span class="sxs-lookup"><span data-stu-id="44d15-279">Power BI desktop and Web</span></span>         |<span data-ttu-id="44d15-280">아니요</span><span class="sxs-lookup"><span data-stu-id="44d15-280">no</span></span>         |
|<span data-ttu-id="44d15-281">MCAS</span><span class="sxs-lookup"><span data-stu-id="44d15-281">MCAS</span></span>     |<span data-ttu-id="44d15-282">아니요</span><span class="sxs-lookup"><span data-stu-id="44d15-282">no</span></span>         |         |


## <a name="file-removed"></a><span data-ttu-id="44d15-283">파일 제거됨</span><span class="sxs-lookup"><span data-stu-id="44d15-283">File removed</span></span>

<span data-ttu-id="44d15-284">이 이벤트는 AIP 스캐너가 이전에 검색한 파일이 제거된 것으로 감지될 때마다 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d15-284">This event is generated each time the AIP scanner detects that a previously scanned file has been removed.</span></span>

|<span data-ttu-id="44d15-285">원본</span><span class="sxs-lookup"><span data-stu-id="44d15-285">Source</span></span>  |<span data-ttu-id="44d15-286">활동 탐색기에서 보고</span><span class="sxs-lookup"><span data-stu-id="44d15-286">Reported in activity explorer</span></span> | <span data-ttu-id="44d15-287">참고</span><span class="sxs-lookup"><span data-stu-id="44d15-287">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="44d15-288">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="44d15-288">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="44d15-289">해당 없음</span><span class="sxs-lookup"><span data-stu-id="44d15-289">not applicable</span></span>         |
|<span data-ttu-id="44d15-290">Outlook</span><span class="sxs-lookup"><span data-stu-id="44d15-290">Outlook</span></span>         |<span data-ttu-id="44d15-291">해당 없음</span><span class="sxs-lookup"><span data-stu-id="44d15-291">not applicable</span></span>         |
|<span data-ttu-id="44d15-292">SharePoint 온라인, OneDrive</span><span class="sxs-lookup"><span data-stu-id="44d15-292">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="44d15-293">해당 없음</span><span class="sxs-lookup"><span data-stu-id="44d15-293">not applicable</span></span>           |
|<span data-ttu-id="44d15-294">Exchange</span><span class="sxs-lookup"><span data-stu-id="44d15-294">Exchange</span></span>         |<span data-ttu-id="44d15-295">해당 없음</span><span class="sxs-lookup"><span data-stu-id="44d15-295">not applicable</span></span>         |
|<span data-ttu-id="44d15-296">AIP 통합 클라이언트</span><span class="sxs-lookup"><span data-stu-id="44d15-296">AIP unified client</span></span>         |<span data-ttu-id="44d15-297">해당 없음</span><span class="sxs-lookup"><span data-stu-id="44d15-297">not applicable</span></span>            |
|<span data-ttu-id="44d15-298">AIP 통합 스캐너</span><span class="sxs-lookup"><span data-stu-id="44d15-298">AIP unified scanner</span></span>         |<span data-ttu-id="44d15-299">예</span><span class="sxs-lookup"><span data-stu-id="44d15-299">yes</span></span>         |
|<span data-ttu-id="44d15-300">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="44d15-300">MIP SDK</span></span>         |<span data-ttu-id="44d15-301">해당 없음</span><span class="sxs-lookup"><span data-stu-id="44d15-301">not applicable</span></span>            |
|<span data-ttu-id="44d15-302">RMS 서비스</span><span class="sxs-lookup"><span data-stu-id="44d15-302">RMS service</span></span>         |<span data-ttu-id="44d15-303">해당 없음</span><span class="sxs-lookup"><span data-stu-id="44d15-303">not applicable</span></span>         |
|<span data-ttu-id="44d15-304">Power BI 및 웹</span><span class="sxs-lookup"><span data-stu-id="44d15-304">Power BI desktop and Web</span></span>         |<span data-ttu-id="44d15-305">해당 없음</span><span class="sxs-lookup"><span data-stu-id="44d15-305">not applicable</span></span>  |
|<span data-ttu-id="44d15-306">MCAS</span><span class="sxs-lookup"><span data-stu-id="44d15-306">MCAS</span></span>     |<span data-ttu-id="44d15-307">해당 없음</span><span class="sxs-lookup"><span data-stu-id="44d15-307">not applicable</span></span>        |         |

### <a name="protection-applied"></a><span data-ttu-id="44d15-308">적용된 보호</span><span class="sxs-lookup"><span data-stu-id="44d15-308">Protection applied</span></span>

<span data-ttu-id="44d15-309">이 이벤트는 레이블이 없는 항목에 처음 보호가 수동으로 추가될 때 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d15-309">This event is generated the first-time protection is added manually to an item that does not have a label.</span></span>

|<span data-ttu-id="44d15-310">원본</span><span class="sxs-lookup"><span data-stu-id="44d15-310">Source</span></span>  |<span data-ttu-id="44d15-311">활동 탐색기에서 보고</span><span class="sxs-lookup"><span data-stu-id="44d15-311">Reported in activity explorer</span></span> | <span data-ttu-id="44d15-312">참고</span><span class="sxs-lookup"><span data-stu-id="44d15-312">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="44d15-313">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="44d15-313">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="44d15-314">아니요</span><span class="sxs-lookup"><span data-stu-id="44d15-314">no</span></span>         |
|<span data-ttu-id="44d15-315">Outlook</span><span class="sxs-lookup"><span data-stu-id="44d15-315">Outlook</span></span>         |<span data-ttu-id="44d15-316">아니요</span><span class="sxs-lookup"><span data-stu-id="44d15-316">no</span></span>         |
|<span data-ttu-id="44d15-317">SharePoint 온라인, OneDrive</span><span class="sxs-lookup"><span data-stu-id="44d15-317">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="44d15-318">해당 없음</span><span class="sxs-lookup"><span data-stu-id="44d15-318">not applicable</span></span>           |
|<span data-ttu-id="44d15-319">Exchange</span><span class="sxs-lookup"><span data-stu-id="44d15-319">Exchange</span></span>         |<span data-ttu-id="44d15-320">아니요</span><span class="sxs-lookup"><span data-stu-id="44d15-320">no</span></span>       |
|<span data-ttu-id="44d15-321">AIP 통합 클라이언트</span><span class="sxs-lookup"><span data-stu-id="44d15-321">AIP unified client</span></span>         |<span data-ttu-id="44d15-322">예</span><span class="sxs-lookup"><span data-stu-id="44d15-322">yes</span></span>            |
|<span data-ttu-id="44d15-323">AIP 통합 스캐너</span><span class="sxs-lookup"><span data-stu-id="44d15-323">AIP unified scanner</span></span>         |<span data-ttu-id="44d15-324">해당 없음</span><span class="sxs-lookup"><span data-stu-id="44d15-324">not applicable</span></span>         |
|<span data-ttu-id="44d15-325">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="44d15-325">MIP SDK</span></span>         |<span data-ttu-id="44d15-326">예</span><span class="sxs-lookup"><span data-stu-id="44d15-326">yes</span></span>            |
|<span data-ttu-id="44d15-327">RMS 서비스</span><span class="sxs-lookup"><span data-stu-id="44d15-327">RMS service</span></span>         |<span data-ttu-id="44d15-328">해당 없음</span><span class="sxs-lookup"><span data-stu-id="44d15-328">not applicable</span></span>         |
|<span data-ttu-id="44d15-329">Power BI 및 웹</span><span class="sxs-lookup"><span data-stu-id="44d15-329">Power BI desktop and Web</span></span>         |<span data-ttu-id="44d15-330">해당 없음</span><span class="sxs-lookup"><span data-stu-id="44d15-330">not applicable</span></span>            |
|<span data-ttu-id="44d15-331">MCAS</span><span class="sxs-lookup"><span data-stu-id="44d15-331">MCAS</span></span>     |<span data-ttu-id="44d15-332">해당 없음</span><span class="sxs-lookup"><span data-stu-id="44d15-332">not applicable</span></span>        |         |

## <a name="protection-changed"></a><span data-ttu-id="44d15-333">보호가 변경된 경우</span><span class="sxs-lookup"><span data-stu-id="44d15-333">Protection changed</span></span>

<span data-ttu-id="44d15-334">이 이벤트는 기록되지 않은 문서의 보호가 수동으로 변경될 때마다 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d15-334">This event is generated each time the protection on an unlabeled document is changed manually.</span></span>

|<span data-ttu-id="44d15-335">원본</span><span class="sxs-lookup"><span data-stu-id="44d15-335">Source</span></span>  |<span data-ttu-id="44d15-336">활동 탐색기에서 보고</span><span class="sxs-lookup"><span data-stu-id="44d15-336">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="44d15-337">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="44d15-337">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="44d15-338">아니요</span><span class="sxs-lookup"><span data-stu-id="44d15-338">no</span></span>         |
|<span data-ttu-id="44d15-339">Outlook</span><span class="sxs-lookup"><span data-stu-id="44d15-339">Outlook</span></span>         |<span data-ttu-id="44d15-340">아니요</span><span class="sxs-lookup"><span data-stu-id="44d15-340">no</span></span>         |
|<span data-ttu-id="44d15-341">SharePoint 온라인, OneDrive</span><span class="sxs-lookup"><span data-stu-id="44d15-341">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="44d15-342">해당 없음</span><span class="sxs-lookup"><span data-stu-id="44d15-342">not applicable</span></span>           |
|<span data-ttu-id="44d15-343">Exchange</span><span class="sxs-lookup"><span data-stu-id="44d15-343">Exchange</span></span>         |<span data-ttu-id="44d15-344">아니요</span><span class="sxs-lookup"><span data-stu-id="44d15-344">no</span></span>       |
|<span data-ttu-id="44d15-345">AIP 통합 클라이언트</span><span class="sxs-lookup"><span data-stu-id="44d15-345">AIP unified client</span></span>         |<span data-ttu-id="44d15-346">예</span><span class="sxs-lookup"><span data-stu-id="44d15-346">yes</span></span>            |
|<span data-ttu-id="44d15-347">AIP 통합 스캐너</span><span class="sxs-lookup"><span data-stu-id="44d15-347">AIP unified scanner</span></span>         |<span data-ttu-id="44d15-348">해당 없음</span><span class="sxs-lookup"><span data-stu-id="44d15-348">not applicable</span></span>         |
|<span data-ttu-id="44d15-349">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="44d15-349">MIP SDK</span></span>         |<span data-ttu-id="44d15-350">예</span><span class="sxs-lookup"><span data-stu-id="44d15-350">yes</span></span>            |
|<span data-ttu-id="44d15-351">RMS 서비스</span><span class="sxs-lookup"><span data-stu-id="44d15-351">RMS service</span></span>         |<span data-ttu-id="44d15-352">해당 없음</span><span class="sxs-lookup"><span data-stu-id="44d15-352">not applicable</span></span>         |
|<span data-ttu-id="44d15-353">Power BI 및 웹</span><span class="sxs-lookup"><span data-stu-id="44d15-353">Power BI desktop and Web</span></span>         |<span data-ttu-id="44d15-354">해당 없음</span><span class="sxs-lookup"><span data-stu-id="44d15-354">not applicable</span></span>            |
|<span data-ttu-id="44d15-355">MCAS</span><span class="sxs-lookup"><span data-stu-id="44d15-355">MCAS</span></span>     |<span data-ttu-id="44d15-356">해당 없음</span><span class="sxs-lookup"><span data-stu-id="44d15-356">not applicable</span></span>        |

## <a name="protection-removed"></a><span data-ttu-id="44d15-357">보호 제거됨</span><span class="sxs-lookup"><span data-stu-id="44d15-357">Protection removed</span></span>

<span data-ttu-id="44d15-358">이 이벤트는 기록되지 않은 문서의 보호가 수동으로 변경될 때마다 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d15-358">This event is generated each time the protection on an unlabeled document is changed manually.</span></span>

|<span data-ttu-id="44d15-359">원본</span><span class="sxs-lookup"><span data-stu-id="44d15-359">Source</span></span>  |<span data-ttu-id="44d15-360">활동 탐색기에서 보고</span><span class="sxs-lookup"><span data-stu-id="44d15-360">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="44d15-361">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="44d15-361">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="44d15-362">아니요</span><span class="sxs-lookup"><span data-stu-id="44d15-362">no</span></span>         |
|<span data-ttu-id="44d15-363">Outlook</span><span class="sxs-lookup"><span data-stu-id="44d15-363">Outlook</span></span>         |<span data-ttu-id="44d15-364">아니요</span><span class="sxs-lookup"><span data-stu-id="44d15-364">no</span></span>         |
|<span data-ttu-id="44d15-365">SharePoint 온라인, OneDrive</span><span class="sxs-lookup"><span data-stu-id="44d15-365">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="44d15-366">해당 없음</span><span class="sxs-lookup"><span data-stu-id="44d15-366">not applicable</span></span>           |
|<span data-ttu-id="44d15-367">Exchange</span><span class="sxs-lookup"><span data-stu-id="44d15-367">Exchange</span></span>         |<span data-ttu-id="44d15-368">아니요</span><span class="sxs-lookup"><span data-stu-id="44d15-368">no</span></span>       |
|<span data-ttu-id="44d15-369">AIP 통합 클라이언트</span><span class="sxs-lookup"><span data-stu-id="44d15-369">AIP unified client</span></span>         |<span data-ttu-id="44d15-370">예</span><span class="sxs-lookup"><span data-stu-id="44d15-370">yes</span></span>            |
|<span data-ttu-id="44d15-371">AIP 통합 스캐너</span><span class="sxs-lookup"><span data-stu-id="44d15-371">AIP unified scanner</span></span>         |<span data-ttu-id="44d15-372">해당 없음</span><span class="sxs-lookup"><span data-stu-id="44d15-372">not applicable</span></span>         |
|<span data-ttu-id="44d15-373">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="44d15-373">MIP SDK</span></span>         |<span data-ttu-id="44d15-374">예</span><span class="sxs-lookup"><span data-stu-id="44d15-374">yes</span></span>            |
|<span data-ttu-id="44d15-375">RMS 서비스</span><span class="sxs-lookup"><span data-stu-id="44d15-375">RMS service</span></span>         |<span data-ttu-id="44d15-376">해당 없음</span><span class="sxs-lookup"><span data-stu-id="44d15-376">not applicable</span></span>         |
|<span data-ttu-id="44d15-377">Power BI 및 웹</span><span class="sxs-lookup"><span data-stu-id="44d15-377">Power BI desktop and Web</span></span>         |<span data-ttu-id="44d15-378">해당 없음</span><span class="sxs-lookup"><span data-stu-id="44d15-378">not applicable</span></span>            |
|<span data-ttu-id="44d15-379">MCAS</span><span class="sxs-lookup"><span data-stu-id="44d15-379">MCAS</span></span>     |<span data-ttu-id="44d15-380">해당 없음</span><span class="sxs-lookup"><span data-stu-id="44d15-380">not applicable</span></span>        |

## <a name="dlp-policy-matched"></a><span data-ttu-id="44d15-381">일치하는 DLP 정책</span><span class="sxs-lookup"><span data-stu-id="44d15-381">DLP policy matched</span></span>

<span data-ttu-id="44d15-382">이 이벤트는 문서 또는 전자 메일에서 DLP 정책이 일치할 때마다 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d15-382">This event is generated each time a DLP policy is matched on a document or an email.</span></span>

|<span data-ttu-id="44d15-383">원본</span><span class="sxs-lookup"><span data-stu-id="44d15-383">Source</span></span>  |<span data-ttu-id="44d15-384">활동 탐색기에서 보고</span><span class="sxs-lookup"><span data-stu-id="44d15-384">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="44d15-385">Exchange</span><span class="sxs-lookup"><span data-stu-id="44d15-385">Exchange</span></span>         |<span data-ttu-id="44d15-386">예</span><span class="sxs-lookup"><span data-stu-id="44d15-386">yes</span></span>       |
|<span data-ttu-id="44d15-387">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="44d15-387">SharePoint Online</span></span>|<span data-ttu-id="44d15-388">예</span><span class="sxs-lookup"><span data-stu-id="44d15-388">yes</span></span>          |
|<span data-ttu-id="44d15-389">OneDrive</span><span class="sxs-lookup"><span data-stu-id="44d15-389">OneDrive</span></span> |<span data-ttu-id="44d15-390">예</span><span class="sxs-lookup"><span data-stu-id="44d15-390">yes</span></span>|
|<span data-ttu-id="44d15-391">Teams</span><span class="sxs-lookup"><span data-stu-id="44d15-391">Teams</span></span> |<span data-ttu-id="44d15-392">예</span><span class="sxs-lookup"><span data-stu-id="44d15-392">yes</span></span>   |
|<span data-ttu-id="44d15-393">Windows 10 장치</span><span class="sxs-lookup"><span data-stu-id="44d15-393">Windows 10 devices</span></span>         |<span data-ttu-id="44d15-394">예</span><span class="sxs-lookup"><span data-stu-id="44d15-394">yes</span></span> |
|<span data-ttu-id="44d15-395">MAC</span><span class="sxs-lookup"><span data-stu-id="44d15-395">MAC</span></span>         |<span data-ttu-id="44d15-396">아니요</span><span class="sxs-lookup"><span data-stu-id="44d15-396">no</span></span>     |
|<span data-ttu-id="44d15-397">On-premises</span><span class="sxs-lookup"><span data-stu-id="44d15-397">on-premises</span></span>         |<span data-ttu-id="44d15-398">아니요</span><span class="sxs-lookup"><span data-stu-id="44d15-398">no</span></span>|
|<span data-ttu-id="44d15-399">MCAS</span><span class="sxs-lookup"><span data-stu-id="44d15-399">MCAS</span></span>     |<span data-ttu-id="44d15-400">아니요</span><span class="sxs-lookup"><span data-stu-id="44d15-400">no</span></span>        | 

<span data-ttu-id="44d15-401">끝점 DLP(Windows 10 장치)에 대한 이벤트는 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="44d15-401">The events for Windows 10 Devices (Endpoint DLP) are:</span></span>

- <span data-ttu-id="44d15-402">파일이 삭제되었습니다.</span><span class="sxs-lookup"><span data-stu-id="44d15-402">file deleted</span></span>
- <span data-ttu-id="44d15-403">만든 파일</span><span class="sxs-lookup"><span data-stu-id="44d15-403">file created</span></span>
- <span data-ttu-id="44d15-404">파일을 클립보드로 복사함</span><span class="sxs-lookup"><span data-stu-id="44d15-404">file copied to clipboard</span></span>
- <span data-ttu-id="44d15-405">파일 수정</span><span class="sxs-lookup"><span data-stu-id="44d15-405">file modified</span></span>
- <span data-ttu-id="44d15-406">파일 읽기</span><span class="sxs-lookup"><span data-stu-id="44d15-406">file read</span></span>
- <span data-ttu-id="44d15-407">인쇄된 파일</span><span class="sxs-lookup"><span data-stu-id="44d15-407">file printed</span></span>
- <span data-ttu-id="44d15-408">파일 이름 변경</span><span class="sxs-lookup"><span data-stu-id="44d15-408">file renamed</span></span>
- <span data-ttu-id="44d15-409">파일을 네트워크 공유에 복사함</span><span class="sxs-lookup"><span data-stu-id="44d15-409">file copied to network share</span></span>
- <span data-ttu-id="44d15-410">허용되지 않은 앱에서 액세스하는 파일</span><span class="sxs-lookup"><span data-stu-id="44d15-410">file accessed by unallowed app</span></span>


## <a name="retention-label-applied"></a><span data-ttu-id="44d15-411">적용된 보존 레이블</span><span class="sxs-lookup"><span data-stu-id="44d15-411">Retention label applied</span></span> 

<span data-ttu-id="44d15-412">이 이벤트는 레이블이 지정되지 않은 문서에 레이블이 지정되거나 보존 레이블이 있는 전자 메일을 보낼 때마다 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d15-412">This event is generated each time an unlabeled document is labeled or an email is sent with a retention label.</span></span>

- <span data-ttu-id="44d15-413">이 문서는 문서 저장 시와 전자 메일 전송 시에 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d15-413">It is captured at the time of save for a document and at time of sending for an email.</span></span>

|<span data-ttu-id="44d15-414">원본</span><span class="sxs-lookup"><span data-stu-id="44d15-414">Source</span></span>  |<span data-ttu-id="44d15-415">활동 탐색기에서 보고</span><span class="sxs-lookup"><span data-stu-id="44d15-415">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="44d15-416">Exchange</span><span class="sxs-lookup"><span data-stu-id="44d15-416">Exchange</span></span>         |<span data-ttu-id="44d15-417">아니요</span><span class="sxs-lookup"><span data-stu-id="44d15-417">no</span></span>       |
|<span data-ttu-id="44d15-418">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="44d15-418">SharePoint Online</span></span>|<span data-ttu-id="44d15-419">예</span><span class="sxs-lookup"><span data-stu-id="44d15-419">yes</span></span>          |
|<span data-ttu-id="44d15-420">OneDrive</span><span class="sxs-lookup"><span data-stu-id="44d15-420">OneDrive</span></span> |<span data-ttu-id="44d15-421">예</span><span class="sxs-lookup"><span data-stu-id="44d15-421">yes</span></span>|

## <a name="retention-label-changed"></a><span data-ttu-id="44d15-422">보존 레이블 변경</span><span class="sxs-lookup"><span data-stu-id="44d15-422">Retention label changed</span></span>

<span data-ttu-id="44d15-423">이 이벤트는 문서 또는 전자 메일에서 레이블이 업데이트될 때마다 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d15-423">This event is generated each time a label is updated on a document or email.</span></span>

- <span data-ttu-id="44d15-424">이 문서는 문서 저장 시와 전자 메일 전송 시에 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d15-424">It is captured at the time of save for a document and at time of sending for an email.</span></span>

|<span data-ttu-id="44d15-425">원본</span><span class="sxs-lookup"><span data-stu-id="44d15-425">Source</span></span>  |<span data-ttu-id="44d15-426">활동 탐색기에서 보고</span><span class="sxs-lookup"><span data-stu-id="44d15-426">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="44d15-427">Exchange</span><span class="sxs-lookup"><span data-stu-id="44d15-427">Exchange</span></span>         |<span data-ttu-id="44d15-428">아니요</span><span class="sxs-lookup"><span data-stu-id="44d15-428">no</span></span>       |
|<span data-ttu-id="44d15-429">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="44d15-429">SharePoint Online</span></span>|<span data-ttu-id="44d15-430">예</span><span class="sxs-lookup"><span data-stu-id="44d15-430">yes</span></span>          |
|<span data-ttu-id="44d15-431">OneDrive</span><span class="sxs-lookup"><span data-stu-id="44d15-431">OneDrive</span></span> |<span data-ttu-id="44d15-432">예</span><span class="sxs-lookup"><span data-stu-id="44d15-432">yes</span></span>|
 
## <a name="retention-label-removed"></a><span data-ttu-id="44d15-433">보존 레이블 제거됨</span><span class="sxs-lookup"><span data-stu-id="44d15-433">Retention label removed</span></span>

<span data-ttu-id="44d15-434">이 이벤트는 파일이나 문서에서 레이블을 제거할 때마다 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d15-434">This event is generated each time a label is removed from a file or document.</span></span>

- <span data-ttu-id="44d15-435">이 문서는 문서 저장 시와 전자 메일 전송 시에 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d15-435">It is captured at the time of save for a document and at time of sending for an email.</span></span>

|<span data-ttu-id="44d15-436">원본</span><span class="sxs-lookup"><span data-stu-id="44d15-436">Source</span></span>  |<span data-ttu-id="44d15-437">활동 탐색기에서 보고</span><span class="sxs-lookup"><span data-stu-id="44d15-437">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="44d15-438">Exchange</span><span class="sxs-lookup"><span data-stu-id="44d15-438">Exchange</span></span>         |<span data-ttu-id="44d15-439">아니요</span><span class="sxs-lookup"><span data-stu-id="44d15-439">no</span></span>       |
|<span data-ttu-id="44d15-440">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="44d15-440">SharePoint Online</span></span>|<span data-ttu-id="44d15-441">예</span><span class="sxs-lookup"><span data-stu-id="44d15-441">yes</span></span>          |
|<span data-ttu-id="44d15-442">OneDrive</span><span class="sxs-lookup"><span data-stu-id="44d15-442">OneDrive</span></span> |<span data-ttu-id="44d15-443">예</span><span class="sxs-lookup"><span data-stu-id="44d15-443">yes</span></span>|


## <a name="known-issues"></a><span data-ttu-id="44d15-444">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="44d15-444">Known issues</span></span>
  
- <span data-ttu-id="44d15-445">최종 사용자에게 권장 레이블 도구 팁이 표시되어 있는 경우 캡처되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44d15-445">When the recommended label tool tip is shown to an end user, it is not captured.</span></span> <span data-ttu-id="44d15-446">그러나 사용자가 권장 레이블을 적용하도록 선택한 경우 레이블은  적용 방법 필드에 *권장으로 표시됩니다.*</span><span class="sxs-lookup"><span data-stu-id="44d15-446">But if the user chooses to apply the recommended label, the label will be shown under the *How applied* field as *Recommended*</span></span>  

- <span data-ttu-id="44d15-447">현재 Sharepoint 및 2013에서 민감도 레이블 다운그레이드에 사유 텍스트를 사용할 수 OneDrive.</span><span class="sxs-lookup"><span data-stu-id="44d15-447">Justification text is not currently available on sensitivity label downgrade from Sharepoint and OneDrive.</span></span>  

- <span data-ttu-id="44d15-448">중요한 정보 유형은 현재 Word, Excel, PowerPoint, Outlook, SharePoint Online 및 OneDrive.</span><span class="sxs-lookup"><span data-stu-id="44d15-448">Sensitive information types are currently not available for autolabeling activities from Word, Excel, PowerPoint, and Outlook, as well as SharePoint Online, and OneDrive.</span></span>
