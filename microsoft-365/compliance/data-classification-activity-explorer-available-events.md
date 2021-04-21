---
title: 활동 탐색기에서 보고된 레이블 지정 작업
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
description: 활동 탐색기에서 사용할 수 있는 레이블 지정 작업 목록입니다.
ms.openlocfilehash: ed51c908d6968e3aeae0adbe06d9ba55887bcf83
ms.sourcegitcommit: 1c53f114a810e7aaa2dc876b84d66348492ea36c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51902953"
---
# <a name="labeling-activities-that-are-available-in-activity-explorer"></a><span data-ttu-id="01b2c-103">활동 탐색기에서 사용할 수 있는 레이블 지정 활동</span><span class="sxs-lookup"><span data-stu-id="01b2c-103">Labeling activities that are available in Activity explorer</span></span>

## <a name="sensitivity-label-applied"></a><span data-ttu-id="01b2c-104">적용된 민감도 레이블</span><span class="sxs-lookup"><span data-stu-id="01b2c-104">Sensitivity label applied</span></span>

<span data-ttu-id="01b2c-105">이 이벤트는 레이블이 지정되지 않은 문서에 레이블이 지정되거나 전자 메일이 레이블과 함께 전송될 때마다 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="01b2c-105">This event is generated each time an unlabeled document is labeled or an email is sent with a label.</span></span> 

- <span data-ttu-id="01b2c-106">Office 네이티브 응용 프로그램 및 웹 응용 프로그램에서 저장 시에 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="01b2c-106">It is captured at the time of save in Office native applications and web applications.</span></span> 
- <span data-ttu-id="01b2c-107">Azure Information Protection 추가 기능에서 발생 시 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="01b2c-107">It is captured at the time of occurrence in Azure Information protection add-ins.</span></span> 
- <span data-ttu-id="01b2c-108">레이블 이벤트 유형 필드 및 필터를 통해  레이블 업그레이드 및 다운그레이드 작업을 모니터링할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01b2c-108">Upgrade and downgrade labels actions can also be monitored via the *Label event type* field and filter.</span></span>   


|<span data-ttu-id="01b2c-109">원본</span><span class="sxs-lookup"><span data-stu-id="01b2c-109">Source</span></span>  |<span data-ttu-id="01b2c-110">활동 탐색기에서 보고</span><span class="sxs-lookup"><span data-stu-id="01b2c-110">Reported in activity explorer</span></span> | <span data-ttu-id="01b2c-111">참고</span><span class="sxs-lookup"><span data-stu-id="01b2c-111">Note</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="01b2c-112">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="01b2c-112">Word, Excel, PowerPoint</span></span>|<span data-ttu-id="01b2c-113">예</span><span class="sxs-lookup"><span data-stu-id="01b2c-113">yes</span></span> |
|<span data-ttu-id="01b2c-114">Outlook</span><span class="sxs-lookup"><span data-stu-id="01b2c-114">Outlook</span></span>| <span data-ttu-id="01b2c-115">예</span><span class="sxs-lookup"><span data-stu-id="01b2c-115">yes</span></span> |<span data-ttu-id="01b2c-116">Win 32에서</span><span class="sxs-lookup"><span data-stu-id="01b2c-116">from Win 32</span></span> |
|<span data-ttu-id="01b2c-117">SharePoint online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="01b2c-117">SharePoint online, OneDrive</span></span>|<span data-ttu-id="01b2c-118">예</span><span class="sxs-lookup"><span data-stu-id="01b2c-118">yes</span></span> | |
|<span data-ttu-id="01b2c-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="01b2c-119">Exchange</span></span>        |<span data-ttu-id="01b2c-120">예</span><span class="sxs-lookup"><span data-stu-id="01b2c-120">yes</span></span>         | |
|<span data-ttu-id="01b2c-121">AIP(Azure Information Protection) 통합 클라이언트 및 AIP 통합 스캐너</span><span class="sxs-lookup"><span data-stu-id="01b2c-121">Azure Information Protection (AIP) unified client and AIP unified scanner</span></span> |<span data-ttu-id="01b2c-122">예</span><span class="sxs-lookup"><span data-stu-id="01b2c-122">yes</span></span> |<span data-ttu-id="01b2c-123">AIP *새 레이블 동작이* 활동 탐색기에서 *적용된 레이블에* 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="01b2c-123">the AIP *new label* action is mapped to *label applied* in activity explorer</span></span>   |
|<span data-ttu-id="01b2c-124">MIP(Microsoft Information Protection) SDK</span><span class="sxs-lookup"><span data-stu-id="01b2c-124">Microsoft information protection (MIP) SDK</span></span>         |<span data-ttu-id="01b2c-125">예</span><span class="sxs-lookup"><span data-stu-id="01b2c-125">yes</span></span>|<span data-ttu-id="01b2c-126">AIP *새 레이블 동작이* 활동 탐색기에서 *적용된 레이블에* 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="01b2c-126">the AIP *new label* action is mapped to *label applied* in activity explorer</span></span>|
|<span data-ttu-id="01b2c-127">RMS(권한 관리 서비스)</span><span class="sxs-lookup"><span data-stu-id="01b2c-127">Rights Management Service (RMS)</span></span>         |<span data-ttu-id="01b2c-128">해당 없음</span><span class="sxs-lookup"><span data-stu-id="01b2c-128">not applicable</span></span>         | |
|<span data-ttu-id="01b2c-129">Power BI 데스크톱 및 웹</span><span class="sxs-lookup"><span data-stu-id="01b2c-129">Power BI desktop and web</span></span>        | <span data-ttu-id="01b2c-130">아니요</span><span class="sxs-lookup"><span data-stu-id="01b2c-130">no</span></span>| <span data-ttu-id="01b2c-131">Microsoft 365 감사 로그에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01b2c-131">accessible in the Microsoft 365 audit logs</span></span>         |
|<span data-ttu-id="01b2c-132">Microsoft Cloud App Security (MCAS)</span><span class="sxs-lookup"><span data-stu-id="01b2c-132">Microsoft Cloud App Security (MCAS)</span></span>         |<span data-ttu-id="01b2c-133">아니요</span><span class="sxs-lookup"><span data-stu-id="01b2c-133">no</span></span>|         |

## <a name="sensitivity-label-changed"></a><span data-ttu-id="01b2c-134">민감도 레이블 변경</span><span class="sxs-lookup"><span data-stu-id="01b2c-134">Sensitivity label changed</span></span>

<span data-ttu-id="01b2c-135">이 이벤트는 문서 또는 전자 메일에서 레이블이 업데이트될 때마다 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="01b2c-135">This event is generated each time a label is updated on the document or email.</span></span>

- <span data-ttu-id="01b2c-136">AIP 통합 클라이언트, 통합 스캐너 및 MIP SDK 원본의 경우  *AIP* 업그레이드 레이블 및 다운그레이드 레이블 작업이 변경된 활동 탐색기 레이블에 *매핑됩니다.*</span><span class="sxs-lookup"><span data-stu-id="01b2c-136">For the AIP Unified client, Unified Scanner and MIP SDK sources, the AIP *upgrade label* and *downgrade label* action maps to activity explorer *label changed*</span></span>

- <span data-ttu-id="01b2c-137">Office 네이티브 응용 프로그램 및 웹 응용 프로그램에서 저장 지점에 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="01b2c-137">It is captured at the point of save in Office native applications and web applications.</span></span> 
- <span data-ttu-id="01b2c-138">Azure Information Protection 통합 클라이언트 추가 기능 및 스캐너 적용에서 발생 시 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="01b2c-138">It is captured at the time of occurrence in Azure Information protection unified client add-ins and scanner enforcements</span></span>
- <span data-ttu-id="01b2c-139">레이블 이벤트 유형 필드 및 필터를 통해  레이블 업그레이드 및 다운그레이드 작업을 모니터링할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01b2c-139">Upgrade and downgrade labels actions can also be monitored via the *Label event type* field and filter.</span></span> <span data-ttu-id="01b2c-140">사유 *텍스트는* SharePoint Online 및 OneDrive를 제외하고도 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="01b2c-140">The *justification* text is also captured except for SharePoint Online and OneDrive.</span></span>
- <span data-ttu-id="01b2c-141">Outlook의 Office 네이티브 앱에서 수행된 민감도 레이블 지정은 파일 저장/전자 메일 보내기 작업 전에 생성된 마지막 작업을 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="01b2c-141">Sensitivity labeling done in Office native apps on Outlook collects the last action that was generated before file save/email send actions.</span></span> <span data-ttu-id="01b2c-142">예를 들어 사용자가 보내기 전에 전자 메일에서 레이블을 여러 번 변경하는 경우 전자 메일이 전송될 때 찾은 마지막 레이블이 감사 로그에 캡처된 다음 활동 탐색기에서 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="01b2c-142">For example, if the user changes label on an email multiple times before sending, the last label found on the email when it is sent is captured in the audit log and then reported in activity explorer.</span></span> 


|<span data-ttu-id="01b2c-143">원본</span><span class="sxs-lookup"><span data-stu-id="01b2c-143">Source</span></span>  |<span data-ttu-id="01b2c-144">활동 탐색기에서 보고</span><span class="sxs-lookup"><span data-stu-id="01b2c-144">Reported in activity explorer</span></span>|<span data-ttu-id="01b2c-145">참고</span><span class="sxs-lookup"><span data-stu-id="01b2c-145">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="01b2c-146">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="01b2c-146">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="01b2c-147">예</span><span class="sxs-lookup"><span data-stu-id="01b2c-147">yes</span></span>         |
|<span data-ttu-id="01b2c-148">Outlook</span><span class="sxs-lookup"><span data-stu-id="01b2c-148">Outlook</span></span>         |<span data-ttu-id="01b2c-149">예</span><span class="sxs-lookup"><span data-stu-id="01b2c-149">yes</span></span>         |<span data-ttu-id="01b2c-150">Win 32</span><span class="sxs-lookup"><span data-stu-id="01b2c-150">Win 32</span></span>|
|<span data-ttu-id="01b2c-151">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="01b2c-151">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="01b2c-152">예</span><span class="sxs-lookup"><span data-stu-id="01b2c-152">yes</span></span>         |
|<span data-ttu-id="01b2c-153">Exchange</span><span class="sxs-lookup"><span data-stu-id="01b2c-153">Exchange</span></span>         |<span data-ttu-id="01b2c-154">예</span><span class="sxs-lookup"><span data-stu-id="01b2c-154">yes</span></span>         |
|<span data-ttu-id="01b2c-155">AIP 통합 클라이언트</span><span class="sxs-lookup"><span data-stu-id="01b2c-155">AIP unified client</span></span>         |<span data-ttu-id="01b2c-156">예</span><span class="sxs-lookup"><span data-stu-id="01b2c-156">yes</span></span>         |
|<span data-ttu-id="01b2c-157">AIP 통합 스캐너</span><span class="sxs-lookup"><span data-stu-id="01b2c-157">AIP unified scanner</span></span>         |<span data-ttu-id="01b2c-158">예</span><span class="sxs-lookup"><span data-stu-id="01b2c-158">yes</span></span>         |
|<span data-ttu-id="01b2c-159">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="01b2c-159">MIP SDK</span></span>         |<span data-ttu-id="01b2c-160">예</span><span class="sxs-lookup"><span data-stu-id="01b2c-160">yes</span></span>         |
|<span data-ttu-id="01b2c-161">RMS 서비스</span><span class="sxs-lookup"><span data-stu-id="01b2c-161">RMS service</span></span>         |<span data-ttu-id="01b2c-162">해당 없음</span><span class="sxs-lookup"><span data-stu-id="01b2c-162">not applicable</span></span>         |
|<span data-ttu-id="01b2c-163">Power BI 데스크톱 및 웹</span><span class="sxs-lookup"><span data-stu-id="01b2c-163">Power BI desktop and Web</span></span>         |<span data-ttu-id="01b2c-164">아니요</span><span class="sxs-lookup"><span data-stu-id="01b2c-164">no</span></span>         |<span data-ttu-id="01b2c-165">Microsoft 365 감사 로그에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01b2c-165">accessible in the Microsoft 365 audit logs</span></span> |
|<span data-ttu-id="01b2c-166">MCAS</span><span class="sxs-lookup"><span data-stu-id="01b2c-166">MCAS</span></span>     |<span data-ttu-id="01b2c-167">아니요</span><span class="sxs-lookup"><span data-stu-id="01b2c-167">no</span></span>         |         |

## <a name="sensitivity-label-removed"></a><span data-ttu-id="01b2c-168">민감도 레이블 제거됨</span><span class="sxs-lookup"><span data-stu-id="01b2c-168">Sensitivity label removed</span></span>

<span data-ttu-id="01b2c-169">이 이벤트는 파일이나 문서에서 레이블을 제거할 때마다 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="01b2c-169">This event is generated each time a label is removed from a file or document.</span></span>

- <span data-ttu-id="01b2c-170">이 이벤트는 Office 네이티브 응용 프로그램 및 웹 응용 프로그램에 저장 시 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="01b2c-170">This event is captured at the time of save in Office native applications and web applications.</span></span>
- <span data-ttu-id="01b2c-171">Azure Information Protection 추가 기능에서 발생 시 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="01b2c-171">It is captured at the time of occurrence in Azure Information protection add-ins.</span></span> 
- <span data-ttu-id="01b2c-172">Office 네이티브 MIP 레이블을 통해 민감도 레이블 지정은 파일 저장/전자 메일 보내기 작업 전에 생성된 마지막 레이블 지정 이벤트를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="01b2c-172">Sensitivity labeling, with Office native MIP label, on Outlook collects the last labeling event that was generated before file save/email send actions.</span></span>

|<span data-ttu-id="01b2c-173">원본</span><span class="sxs-lookup"><span data-stu-id="01b2c-173">Source</span></span>  |<span data-ttu-id="01b2c-174">활동 탐색기에서 보고</span><span class="sxs-lookup"><span data-stu-id="01b2c-174">Reported in activity explorer</span></span> | <span data-ttu-id="01b2c-175">참고</span><span class="sxs-lookup"><span data-stu-id="01b2c-175">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="01b2c-176">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="01b2c-176">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="01b2c-177">예</span><span class="sxs-lookup"><span data-stu-id="01b2c-177">yes</span></span>         |
|<span data-ttu-id="01b2c-178">Outlook</span><span class="sxs-lookup"><span data-stu-id="01b2c-178">Outlook</span></span>         |<span data-ttu-id="01b2c-179">예</span><span class="sxs-lookup"><span data-stu-id="01b2c-179">yes</span></span>         |<span data-ttu-id="01b2c-180">Win 32</span><span class="sxs-lookup"><span data-stu-id="01b2c-180">Win 32</span></span>|
|<span data-ttu-id="01b2c-181">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="01b2c-181">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="01b2c-182">예</span><span class="sxs-lookup"><span data-stu-id="01b2c-182">yes</span></span>         |
|<span data-ttu-id="01b2c-183">Exchange</span><span class="sxs-lookup"><span data-stu-id="01b2c-183">Exchange</span></span>         |<span data-ttu-id="01b2c-184">예</span><span class="sxs-lookup"><span data-stu-id="01b2c-184">yes</span></span>         |
|<span data-ttu-id="01b2c-185">AIP 통합 클라이언트</span><span class="sxs-lookup"><span data-stu-id="01b2c-185">AIP unified client</span></span>         |<span data-ttu-id="01b2c-186">예</span><span class="sxs-lookup"><span data-stu-id="01b2c-186">yes</span></span>         |<span data-ttu-id="01b2c-187">AIP *레이블 제거 작업은* 활동 탐색기에서 레이블 제거 *동작에* 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="01b2c-187">the AIP *remove label* action is mapped to the *label removed* action in activity explorer</span></span>|
|<span data-ttu-id="01b2c-188">AIP 통합 스캐너</span><span class="sxs-lookup"><span data-stu-id="01b2c-188">AIP unified scanner</span></span>         |<span data-ttu-id="01b2c-189">예</span><span class="sxs-lookup"><span data-stu-id="01b2c-189">yes</span></span>         |<span data-ttu-id="01b2c-190">AIP *레이블 제거 작업은* 활동 탐색기에서 레이블 제거 *동작에* 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="01b2c-190">the AIP *remove label* action is mapped to the *label removed* action in activity explorer</span></span> |
|<span data-ttu-id="01b2c-191">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="01b2c-191">MIP SDK</span></span>         |<span data-ttu-id="01b2c-192">예</span><span class="sxs-lookup"><span data-stu-id="01b2c-192">yes</span></span>         |<span data-ttu-id="01b2c-193">AIP *레이블 제거 작업은* 활동 탐색기에서 레이블 제거 *동작에* 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="01b2c-193">the AIP *remove label* action is mapped to the *label removed* action in activity explorer</span></span> |
|<span data-ttu-id="01b2c-194">RMS 서비스</span><span class="sxs-lookup"><span data-stu-id="01b2c-194">RMS service</span></span>         |<span data-ttu-id="01b2c-195">해당 없음</span><span class="sxs-lookup"><span data-stu-id="01b2c-195">not applicable</span></span>         |
|<span data-ttu-id="01b2c-196">Power BI 데스크톱 및 웹</span><span class="sxs-lookup"><span data-stu-id="01b2c-196">Power BI desktop and Web</span></span>         |<span data-ttu-id="01b2c-197">아니요</span><span class="sxs-lookup"><span data-stu-id="01b2c-197">no</span></span>         |<span data-ttu-id="01b2c-198">Microsoft 365 감사 로그에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01b2c-198">accessible in the Microsoft 365 audit logs</span></span> |
|<span data-ttu-id="01b2c-199">MCAS</span><span class="sxs-lookup"><span data-stu-id="01b2c-199">MCAS</span></span>     |<span data-ttu-id="01b2c-200">아니요</span><span class="sxs-lookup"><span data-stu-id="01b2c-200">no</span></span>         |         |
 

## <a name="sensitivity-label-file-read"></a><span data-ttu-id="01b2c-201">민감도 레이블 파일 읽기</span><span class="sxs-lookup"><span data-stu-id="01b2c-201">Sensitivity label file read</span></span>

<span data-ttu-id="01b2c-202">이 이벤트는 레이블이 지정되거나 보호된 문서를 열 때마다 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="01b2c-202">This event is generated each time a labeled or protected document is opened.</span></span>

|<span data-ttu-id="01b2c-203">원본</span><span class="sxs-lookup"><span data-stu-id="01b2c-203">Source</span></span>  |<span data-ttu-id="01b2c-204">활동 탐색기에서 보고</span><span class="sxs-lookup"><span data-stu-id="01b2c-204">Reported in activity explorer</span></span> | <span data-ttu-id="01b2c-205">참고</span><span class="sxs-lookup"><span data-stu-id="01b2c-205">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="01b2c-206">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="01b2c-206">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="01b2c-207">예</span><span class="sxs-lookup"><span data-stu-id="01b2c-207">yes</span></span>         |
|<span data-ttu-id="01b2c-208">Outlook</span><span class="sxs-lookup"><span data-stu-id="01b2c-208">Outlook</span></span>         |<span data-ttu-id="01b2c-209">아니요</span><span class="sxs-lookup"><span data-stu-id="01b2c-209">no</span></span>         |
|<span data-ttu-id="01b2c-210">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="01b2c-210">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="01b2c-211">아니요</span><span class="sxs-lookup"><span data-stu-id="01b2c-211">no</span></span>         |
|<span data-ttu-id="01b2c-212">Exchange</span><span class="sxs-lookup"><span data-stu-id="01b2c-212">Exchange</span></span>         |<span data-ttu-id="01b2c-213">아니요</span><span class="sxs-lookup"><span data-stu-id="01b2c-213">no</span></span>         |
|<span data-ttu-id="01b2c-214">AIP 통합 클라이언트</span><span class="sxs-lookup"><span data-stu-id="01b2c-214">AIP unified client</span></span>         |<span data-ttu-id="01b2c-215">예</span><span class="sxs-lookup"><span data-stu-id="01b2c-215">yes</span></span>         |<span data-ttu-id="01b2c-216">AIP *액세스 작업이* 활동 탐색기에서 *파일* 읽기 작업으로 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="01b2c-216">the AIP *access* action is mapped to the *file read* action in activity explorer</span></span>|
|<span data-ttu-id="01b2c-217">AIP 통합 스캐너</span><span class="sxs-lookup"><span data-stu-id="01b2c-217">AIP unified scanner</span></span>         |<span data-ttu-id="01b2c-218">예</span><span class="sxs-lookup"><span data-stu-id="01b2c-218">yes</span></span>         |<span data-ttu-id="01b2c-219">AIP *액세스 작업이* 활동 탐색기에서 *파일* 읽기 작업으로 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="01b2c-219">the AIP *access* action is mapped to the *file read* action in activity explorer</span></span>|
|<span data-ttu-id="01b2c-220">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="01b2c-220">MIP SDK</span></span>         |<span data-ttu-id="01b2c-221">예</span><span class="sxs-lookup"><span data-stu-id="01b2c-221">yes</span></span>         |<span data-ttu-id="01b2c-222">AIP *액세스 작업이* 활동 탐색기에서 *파일* 읽기 작업으로 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="01b2c-222">the AIP *access* action is mapped to the *file read* action in activity explorer</span></span>|
|<span data-ttu-id="01b2c-223">RMS 서비스</span><span class="sxs-lookup"><span data-stu-id="01b2c-223">RMS service</span></span>         |<span data-ttu-id="01b2c-224">예</span><span class="sxs-lookup"><span data-stu-id="01b2c-224">yes</span></span>         |<span data-ttu-id="01b2c-225">액세스 *작업이* 활동 탐색기에서 *파일 읽기* 작업으로 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="01b2c-225">the *access* action is mapped to the *file read* action in activity explorer</span></span> |
|<span data-ttu-id="01b2c-226">Power BI 데스크톱 및 웹</span><span class="sxs-lookup"><span data-stu-id="01b2c-226">Power BI desktop and Web</span></span>         |<span data-ttu-id="01b2c-227">아니요</span><span class="sxs-lookup"><span data-stu-id="01b2c-227">no</span></span>         |<span data-ttu-id="01b2c-228">Microsoft 365 감사 로그에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01b2c-228">accessible in the Microsoft 365 audit logs</span></span> |
|<span data-ttu-id="01b2c-229">MCAS</span><span class="sxs-lookup"><span data-stu-id="01b2c-229">MCAS</span></span>     |<span data-ttu-id="01b2c-230">아니요</span><span class="sxs-lookup"><span data-stu-id="01b2c-230">no</span></span>         |         |


## <a name="sensitivity-label-files-discovered"></a><span data-ttu-id="01b2c-231">검색된 민감도 레이블 파일</span><span class="sxs-lookup"><span data-stu-id="01b2c-231">Sensitivity label files discovered</span></span>

<span data-ttu-id="01b2c-232">이 이벤트는 AIP 스캐너를 사용하여 여러 위치에서 중요한 데이터를 검색하고 파일을 찾을 때마다 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="01b2c-232">This event is generated each time files are discovered when AIP Scanner is used for scanning sensitive data in various locations and finds files.</span></span>

|<span data-ttu-id="01b2c-233">원본</span><span class="sxs-lookup"><span data-stu-id="01b2c-233">Source</span></span>  |<span data-ttu-id="01b2c-234">활동 탐색기에서 보고</span><span class="sxs-lookup"><span data-stu-id="01b2c-234">Reported in activity explorer</span></span> | <span data-ttu-id="01b2c-235">참고</span><span class="sxs-lookup"><span data-stu-id="01b2c-235">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="01b2c-236">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="01b2c-236">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="01b2c-237">해당 없음</span><span class="sxs-lookup"><span data-stu-id="01b2c-237">not applicable</span></span>         |
|<span data-ttu-id="01b2c-238">Outlook</span><span class="sxs-lookup"><span data-stu-id="01b2c-238">Outlook</span></span>         |<span data-ttu-id="01b2c-239">해당 없음</span><span class="sxs-lookup"><span data-stu-id="01b2c-239">not applicable</span></span>         |
|<span data-ttu-id="01b2c-240">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="01b2c-240">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="01b2c-241">해당 없음</span><span class="sxs-lookup"><span data-stu-id="01b2c-241">not applicable</span></span>         |
|<span data-ttu-id="01b2c-242">Exchange</span><span class="sxs-lookup"><span data-stu-id="01b2c-242">Exchange</span></span>         |<span data-ttu-id="01b2c-243">해당 없음</span><span class="sxs-lookup"><span data-stu-id="01b2c-243">not applicable</span></span>         |
|<span data-ttu-id="01b2c-244">AIP 통합 클라이언트</span><span class="sxs-lookup"><span data-stu-id="01b2c-244">AIP unified client</span></span>         |<span data-ttu-id="01b2c-245">해당 없음</span><span class="sxs-lookup"><span data-stu-id="01b2c-245">not applicable</span></span>       |
|<span data-ttu-id="01b2c-246">AIP 통합 스캐너</span><span class="sxs-lookup"><span data-stu-id="01b2c-246">AIP unified scanner</span></span>         |<span data-ttu-id="01b2c-247">예</span><span class="sxs-lookup"><span data-stu-id="01b2c-247">yes</span></span>         |<span data-ttu-id="01b2c-248">AIP *검색 작업이* 활동 탐색기에서 검색된 파일에 매핑됩니다. </span><span class="sxs-lookup"><span data-stu-id="01b2c-248">the AIP *discover* action is mapped to the *files discovered* action in activity explorer</span></span>|
|<span data-ttu-id="01b2c-249">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="01b2c-249">MIP SDK</span></span>         |<span data-ttu-id="01b2c-250">예</span><span class="sxs-lookup"><span data-stu-id="01b2c-250">yes</span></span>         |<span data-ttu-id="01b2c-251">AIP *검색 작업이* 활동 탐색기에서 검색된 파일에 매핑됩니다. </span><span class="sxs-lookup"><span data-stu-id="01b2c-251">the AIP *discover* action is mapped to the *file discovered* action in activity explorer</span></span>|
|<span data-ttu-id="01b2c-252">RMS 서비스</span><span class="sxs-lookup"><span data-stu-id="01b2c-252">RMS service</span></span>         |<span data-ttu-id="01b2c-253">해당 없음</span><span class="sxs-lookup"><span data-stu-id="01b2c-253">not applicable</span></span>         |
|<span data-ttu-id="01b2c-254">Power BI 데스크톱 및 웹</span><span class="sxs-lookup"><span data-stu-id="01b2c-254">Power BI desktop and Web</span></span>         |<span data-ttu-id="01b2c-255">해당 없음</span><span class="sxs-lookup"><span data-stu-id="01b2c-255">not applicable</span></span>         |
|<span data-ttu-id="01b2c-256">MCAS</span><span class="sxs-lookup"><span data-stu-id="01b2c-256">MCAS</span></span>     |<span data-ttu-id="01b2c-257">해당 없음</span><span class="sxs-lookup"><span data-stu-id="01b2c-257">not applicable</span></span>         |         |


## <a name="sensitivity-label-file-renamed"></a><span data-ttu-id="01b2c-258">민감도 레이블 파일 이름 변경</span><span class="sxs-lookup"><span data-stu-id="01b2c-258">Sensitivity label file renamed</span></span>

<span data-ttu-id="01b2c-259">이 이벤트는 민감도 레이블이 있는 문서의 이름을 변경할 때마다 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="01b2c-259">This event is generated each time a document with a sensitivity label is renamed.</span></span> 

|<span data-ttu-id="01b2c-260">원본</span><span class="sxs-lookup"><span data-stu-id="01b2c-260">Source</span></span>  | <span data-ttu-id="01b2c-261">활동 탐색기에서 보고</span><span class="sxs-lookup"><span data-stu-id="01b2c-261">Reported in activity explorer</span></span> | <span data-ttu-id="01b2c-262">참고</span><span class="sxs-lookup"><span data-stu-id="01b2c-262">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="01b2c-263">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="01b2c-263">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="01b2c-264">예</span><span class="sxs-lookup"><span data-stu-id="01b2c-264">yes</span></span>         |
|<span data-ttu-id="01b2c-265">Outlook</span><span class="sxs-lookup"><span data-stu-id="01b2c-265">Outlook</span></span>         |<span data-ttu-id="01b2c-266">해당 없음</span><span class="sxs-lookup"><span data-stu-id="01b2c-266">not applicable</span></span>         |
|<span data-ttu-id="01b2c-267">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="01b2c-267">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="01b2c-268">아니요</span><span class="sxs-lookup"><span data-stu-id="01b2c-268">no</span></span>        |
|<span data-ttu-id="01b2c-269">Exchange</span><span class="sxs-lookup"><span data-stu-id="01b2c-269">Exchange</span></span>         |<span data-ttu-id="01b2c-270">해당 없음</span><span class="sxs-lookup"><span data-stu-id="01b2c-270">not applicable</span></span>         |
|<span data-ttu-id="01b2c-271">AIP 통합 클라이언트</span><span class="sxs-lookup"><span data-stu-id="01b2c-271">AIP unified client</span></span>         |<span data-ttu-id="01b2c-272">아니요</span><span class="sxs-lookup"><span data-stu-id="01b2c-272">no</span></span>         |
|<span data-ttu-id="01b2c-273">AIP 통합 스캐너</span><span class="sxs-lookup"><span data-stu-id="01b2c-273">AIP unified scanner</span></span>         |<span data-ttu-id="01b2c-274">아니요</span><span class="sxs-lookup"><span data-stu-id="01b2c-274">no</span></span>         |
|<span data-ttu-id="01b2c-275">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="01b2c-275">MIP SDK</span></span>         |<span data-ttu-id="01b2c-276">아니요</span><span class="sxs-lookup"><span data-stu-id="01b2c-276">no</span></span>         |
|<span data-ttu-id="01b2c-277">RMS 서비스</span><span class="sxs-lookup"><span data-stu-id="01b2c-277">RMS service</span></span>         |<span data-ttu-id="01b2c-278">아니요</span><span class="sxs-lookup"><span data-stu-id="01b2c-278">no</span></span>      |
|<span data-ttu-id="01b2c-279">Power BI 데스크톱 및 웹</span><span class="sxs-lookup"><span data-stu-id="01b2c-279">Power BI desktop and Web</span></span>         |<span data-ttu-id="01b2c-280">아니요</span><span class="sxs-lookup"><span data-stu-id="01b2c-280">no</span></span>         |
|<span data-ttu-id="01b2c-281">MCAS</span><span class="sxs-lookup"><span data-stu-id="01b2c-281">MCAS</span></span>     |<span data-ttu-id="01b2c-282">아니요</span><span class="sxs-lookup"><span data-stu-id="01b2c-282">no</span></span>         |         |


## <a name="sensitivity-label-file-removed"></a><span data-ttu-id="01b2c-283">민감도 레이블 파일 제거</span><span class="sxs-lookup"><span data-stu-id="01b2c-283">Sensitivity label file removed</span></span>

<span data-ttu-id="01b2c-284">이 이벤트는 AIP 스캐너가 이전에 검색한 파일이 제거된 것으로 감지될 때마다 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="01b2c-284">This event is generated each time the AIP scanner detects that a previously scanned file has been removed.</span></span>

|<span data-ttu-id="01b2c-285">원본</span><span class="sxs-lookup"><span data-stu-id="01b2c-285">Source</span></span>  |<span data-ttu-id="01b2c-286">활동 탐색기에서 보고</span><span class="sxs-lookup"><span data-stu-id="01b2c-286">Reported in activity explorer</span></span> | <span data-ttu-id="01b2c-287">참고</span><span class="sxs-lookup"><span data-stu-id="01b2c-287">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="01b2c-288">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="01b2c-288">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="01b2c-289">해당 없음</span><span class="sxs-lookup"><span data-stu-id="01b2c-289">not applicable</span></span>         |
|<span data-ttu-id="01b2c-290">Outlook</span><span class="sxs-lookup"><span data-stu-id="01b2c-290">Outlook</span></span>         |<span data-ttu-id="01b2c-291">해당 없음</span><span class="sxs-lookup"><span data-stu-id="01b2c-291">not applicable</span></span>         |
|<span data-ttu-id="01b2c-292">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="01b2c-292">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="01b2c-293">해당 없음</span><span class="sxs-lookup"><span data-stu-id="01b2c-293">not applicable</span></span>           |
|<span data-ttu-id="01b2c-294">Exchange</span><span class="sxs-lookup"><span data-stu-id="01b2c-294">Exchange</span></span>         |<span data-ttu-id="01b2c-295">해당 없음</span><span class="sxs-lookup"><span data-stu-id="01b2c-295">not applicable</span></span>         |
|<span data-ttu-id="01b2c-296">AIP 통합 클라이언트</span><span class="sxs-lookup"><span data-stu-id="01b2c-296">AIP unified client</span></span>         |<span data-ttu-id="01b2c-297">해당 없음</span><span class="sxs-lookup"><span data-stu-id="01b2c-297">not applicable</span></span>            |
|<span data-ttu-id="01b2c-298">AIP 통합 스캐너</span><span class="sxs-lookup"><span data-stu-id="01b2c-298">AIP unified scanner</span></span>         |<span data-ttu-id="01b2c-299">예</span><span class="sxs-lookup"><span data-stu-id="01b2c-299">yes</span></span>         |
|<span data-ttu-id="01b2c-300">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="01b2c-300">MIP SDK</span></span>         |<span data-ttu-id="01b2c-301">해당 없음</span><span class="sxs-lookup"><span data-stu-id="01b2c-301">not applicable</span></span>            |
|<span data-ttu-id="01b2c-302">RMS 서비스</span><span class="sxs-lookup"><span data-stu-id="01b2c-302">RMS service</span></span>         |<span data-ttu-id="01b2c-303">해당 없음</span><span class="sxs-lookup"><span data-stu-id="01b2c-303">not applicable</span></span>         |
|<span data-ttu-id="01b2c-304">Power BI 데스크톱 및 웹</span><span class="sxs-lookup"><span data-stu-id="01b2c-304">Power BI desktop and Web</span></span>         |<span data-ttu-id="01b2c-305">해당 없음</span><span class="sxs-lookup"><span data-stu-id="01b2c-305">not applicable</span></span>  |
|<span data-ttu-id="01b2c-306">MCAS</span><span class="sxs-lookup"><span data-stu-id="01b2c-306">MCAS</span></span>     |<span data-ttu-id="01b2c-307">해당 없음</span><span class="sxs-lookup"><span data-stu-id="01b2c-307">not applicable</span></span>        |         |

### <a name="sensitivity-label-protection-applied"></a><span data-ttu-id="01b2c-308">민감도 레이블 보호 적용</span><span class="sxs-lookup"><span data-stu-id="01b2c-308">Sensitivity label protection applied</span></span>

<span data-ttu-id="01b2c-309">이 이벤트는 레이블이 없는 항목에 처음 보호가 수동으로 추가될 때 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="01b2c-309">This event is generated the first-time protection is added manually to an item that does not have a label.</span></span>

|<span data-ttu-id="01b2c-310">원본</span><span class="sxs-lookup"><span data-stu-id="01b2c-310">Source</span></span>  |<span data-ttu-id="01b2c-311">활동 탐색기에서 보고</span><span class="sxs-lookup"><span data-stu-id="01b2c-311">Reported in activity explorer</span></span> | <span data-ttu-id="01b2c-312">참고</span><span class="sxs-lookup"><span data-stu-id="01b2c-312">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="01b2c-313">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="01b2c-313">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="01b2c-314">아니요</span><span class="sxs-lookup"><span data-stu-id="01b2c-314">no</span></span>         |
|<span data-ttu-id="01b2c-315">Outlook</span><span class="sxs-lookup"><span data-stu-id="01b2c-315">Outlook</span></span>         |<span data-ttu-id="01b2c-316">아니요</span><span class="sxs-lookup"><span data-stu-id="01b2c-316">no</span></span>         |
|<span data-ttu-id="01b2c-317">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="01b2c-317">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="01b2c-318">해당 없음</span><span class="sxs-lookup"><span data-stu-id="01b2c-318">not applicable</span></span>           |
|<span data-ttu-id="01b2c-319">Exchange</span><span class="sxs-lookup"><span data-stu-id="01b2c-319">Exchange</span></span>         |<span data-ttu-id="01b2c-320">아니요</span><span class="sxs-lookup"><span data-stu-id="01b2c-320">no</span></span>       |
|<span data-ttu-id="01b2c-321">AIP 통합 클라이언트</span><span class="sxs-lookup"><span data-stu-id="01b2c-321">AIP unified client</span></span>         |<span data-ttu-id="01b2c-322">예</span><span class="sxs-lookup"><span data-stu-id="01b2c-322">yes</span></span>            |
|<span data-ttu-id="01b2c-323">AIP 통합 스캐너</span><span class="sxs-lookup"><span data-stu-id="01b2c-323">AIP unified scanner</span></span>         |<span data-ttu-id="01b2c-324">해당 없음</span><span class="sxs-lookup"><span data-stu-id="01b2c-324">not applicable</span></span>         |
|<span data-ttu-id="01b2c-325">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="01b2c-325">MIP SDK</span></span>         |<span data-ttu-id="01b2c-326">예</span><span class="sxs-lookup"><span data-stu-id="01b2c-326">yes</span></span>            |
|<span data-ttu-id="01b2c-327">RMS 서비스</span><span class="sxs-lookup"><span data-stu-id="01b2c-327">RMS service</span></span>         |<span data-ttu-id="01b2c-328">해당 없음</span><span class="sxs-lookup"><span data-stu-id="01b2c-328">not applicable</span></span>         |
|<span data-ttu-id="01b2c-329">Power BI 데스크톱 및 웹</span><span class="sxs-lookup"><span data-stu-id="01b2c-329">Power BI desktop and Web</span></span>         |<span data-ttu-id="01b2c-330">해당 없음</span><span class="sxs-lookup"><span data-stu-id="01b2c-330">not applicable</span></span>            |
|<span data-ttu-id="01b2c-331">MCAS</span><span class="sxs-lookup"><span data-stu-id="01b2c-331">MCAS</span></span>     |<span data-ttu-id="01b2c-332">해당 없음</span><span class="sxs-lookup"><span data-stu-id="01b2c-332">not applicable</span></span>        |         |

## <a name="sensitivity-label-protection-changed"></a><span data-ttu-id="01b2c-333">민감도 레이블 보호 변경</span><span class="sxs-lookup"><span data-stu-id="01b2c-333">Sensitivity label protection changed</span></span>

<span data-ttu-id="01b2c-334">이 이벤트는 기록되지 않은 문서의 보호가 수동으로 변경될 때마다 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="01b2c-334">This event is generated each time the protection on an unlabeled document is changed manually.</span></span>

|<span data-ttu-id="01b2c-335">원본</span><span class="sxs-lookup"><span data-stu-id="01b2c-335">Source</span></span>  |<span data-ttu-id="01b2c-336">활동 탐색기에서 보고</span><span class="sxs-lookup"><span data-stu-id="01b2c-336">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="01b2c-337">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="01b2c-337">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="01b2c-338">아니요</span><span class="sxs-lookup"><span data-stu-id="01b2c-338">no</span></span>         |
|<span data-ttu-id="01b2c-339">Outlook</span><span class="sxs-lookup"><span data-stu-id="01b2c-339">Outlook</span></span>         |<span data-ttu-id="01b2c-340">아니요</span><span class="sxs-lookup"><span data-stu-id="01b2c-340">no</span></span>         |
|<span data-ttu-id="01b2c-341">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="01b2c-341">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="01b2c-342">해당 없음</span><span class="sxs-lookup"><span data-stu-id="01b2c-342">not applicable</span></span>           |
|<span data-ttu-id="01b2c-343">Exchange</span><span class="sxs-lookup"><span data-stu-id="01b2c-343">Exchange</span></span>         |<span data-ttu-id="01b2c-344">아니요</span><span class="sxs-lookup"><span data-stu-id="01b2c-344">no</span></span>       |
|<span data-ttu-id="01b2c-345">AIP 통합 클라이언트</span><span class="sxs-lookup"><span data-stu-id="01b2c-345">AIP unified client</span></span>         |<span data-ttu-id="01b2c-346">예</span><span class="sxs-lookup"><span data-stu-id="01b2c-346">yes</span></span>            |
|<span data-ttu-id="01b2c-347">AIP 통합 스캐너</span><span class="sxs-lookup"><span data-stu-id="01b2c-347">AIP unified scanner</span></span>         |<span data-ttu-id="01b2c-348">해당 없음</span><span class="sxs-lookup"><span data-stu-id="01b2c-348">not applicable</span></span>         |
|<span data-ttu-id="01b2c-349">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="01b2c-349">MIP SDK</span></span>         |<span data-ttu-id="01b2c-350">예</span><span class="sxs-lookup"><span data-stu-id="01b2c-350">yes</span></span>            |
|<span data-ttu-id="01b2c-351">RMS 서비스</span><span class="sxs-lookup"><span data-stu-id="01b2c-351">RMS service</span></span>         |<span data-ttu-id="01b2c-352">해당 없음</span><span class="sxs-lookup"><span data-stu-id="01b2c-352">not applicable</span></span>         |
|<span data-ttu-id="01b2c-353">Power BI 데스크톱 및 웹</span><span class="sxs-lookup"><span data-stu-id="01b2c-353">Power BI desktop and Web</span></span>         |<span data-ttu-id="01b2c-354">해당 없음</span><span class="sxs-lookup"><span data-stu-id="01b2c-354">not applicable</span></span>            |
|<span data-ttu-id="01b2c-355">MCAS</span><span class="sxs-lookup"><span data-stu-id="01b2c-355">MCAS</span></span>     |<span data-ttu-id="01b2c-356">해당 없음</span><span class="sxs-lookup"><span data-stu-id="01b2c-356">not applicable</span></span>        |

## <a name="sensitivity-label-protection-removed"></a><span data-ttu-id="01b2c-357">민감도 레이블 보호 제거됨</span><span class="sxs-lookup"><span data-stu-id="01b2c-357">Sensitivity label protection removed</span></span>

<span data-ttu-id="01b2c-358">이 이벤트는 기록되지 않은 문서의 보호가 수동으로 변경될 때마다 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="01b2c-358">This event is generated each time the protection on an unlabeled document is changed manually.</span></span>

|<span data-ttu-id="01b2c-359">원본</span><span class="sxs-lookup"><span data-stu-id="01b2c-359">Source</span></span>  |<span data-ttu-id="01b2c-360">활동 탐색기에서 보고</span><span class="sxs-lookup"><span data-stu-id="01b2c-360">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="01b2c-361">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="01b2c-361">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="01b2c-362">아니요</span><span class="sxs-lookup"><span data-stu-id="01b2c-362">no</span></span>         |
|<span data-ttu-id="01b2c-363">Outlook</span><span class="sxs-lookup"><span data-stu-id="01b2c-363">Outlook</span></span>         |<span data-ttu-id="01b2c-364">아니요</span><span class="sxs-lookup"><span data-stu-id="01b2c-364">no</span></span>         |
|<span data-ttu-id="01b2c-365">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="01b2c-365">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="01b2c-366">해당 없음</span><span class="sxs-lookup"><span data-stu-id="01b2c-366">not applicable</span></span>           |
|<span data-ttu-id="01b2c-367">Exchange</span><span class="sxs-lookup"><span data-stu-id="01b2c-367">Exchange</span></span>         |<span data-ttu-id="01b2c-368">아니요</span><span class="sxs-lookup"><span data-stu-id="01b2c-368">no</span></span>       |
|<span data-ttu-id="01b2c-369">AIP 통합 클라이언트</span><span class="sxs-lookup"><span data-stu-id="01b2c-369">AIP unified client</span></span>         |<span data-ttu-id="01b2c-370">예</span><span class="sxs-lookup"><span data-stu-id="01b2c-370">yes</span></span>            |
|<span data-ttu-id="01b2c-371">AIP 통합 스캐너</span><span class="sxs-lookup"><span data-stu-id="01b2c-371">AIP unified scanner</span></span>         |<span data-ttu-id="01b2c-372">해당 없음</span><span class="sxs-lookup"><span data-stu-id="01b2c-372">not applicable</span></span>         |
|<span data-ttu-id="01b2c-373">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="01b2c-373">MIP SDK</span></span>         |<span data-ttu-id="01b2c-374">예</span><span class="sxs-lookup"><span data-stu-id="01b2c-374">yes</span></span>            |
|<span data-ttu-id="01b2c-375">RMS 서비스</span><span class="sxs-lookup"><span data-stu-id="01b2c-375">RMS service</span></span>         |<span data-ttu-id="01b2c-376">해당 없음</span><span class="sxs-lookup"><span data-stu-id="01b2c-376">not applicable</span></span>         |
|<span data-ttu-id="01b2c-377">Power BI 데스크톱 및 웹</span><span class="sxs-lookup"><span data-stu-id="01b2c-377">Power BI desktop and Web</span></span>         |<span data-ttu-id="01b2c-378">해당 없음</span><span class="sxs-lookup"><span data-stu-id="01b2c-378">not applicable</span></span>            |
|<span data-ttu-id="01b2c-379">MCAS</span><span class="sxs-lookup"><span data-stu-id="01b2c-379">MCAS</span></span>     |<span data-ttu-id="01b2c-380">해당 없음</span><span class="sxs-lookup"><span data-stu-id="01b2c-380">not applicable</span></span>        |

## <a name="sensitivity-label-dlp-policy-matched"></a><span data-ttu-id="01b2c-381">민감도 레이블 일치 DLP 정책</span><span class="sxs-lookup"><span data-stu-id="01b2c-381">Sensitivity label DLP policy matched</span></span>

<span data-ttu-id="01b2c-382">이 이벤트는 DLP 정책이 일치할 때마다 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="01b2c-382">This event is generated each time a DLP policy is matched.</span></span>

|<span data-ttu-id="01b2c-383">원본</span><span class="sxs-lookup"><span data-stu-id="01b2c-383">Source</span></span>  |<span data-ttu-id="01b2c-384">활동 탐색기에서 보고</span><span class="sxs-lookup"><span data-stu-id="01b2c-384">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="01b2c-385">Exchange</span><span class="sxs-lookup"><span data-stu-id="01b2c-385">Exchange</span></span>         |<span data-ttu-id="01b2c-386">예</span><span class="sxs-lookup"><span data-stu-id="01b2c-386">yes</span></span>       |
|<span data-ttu-id="01b2c-387">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="01b2c-387">SharePoint Online</span></span>|<span data-ttu-id="01b2c-388">예</span><span class="sxs-lookup"><span data-stu-id="01b2c-388">yes</span></span>          |
|<span data-ttu-id="01b2c-389">OneDrive</span><span class="sxs-lookup"><span data-stu-id="01b2c-389">OneDrive</span></span> |<span data-ttu-id="01b2c-390">예</span><span class="sxs-lookup"><span data-stu-id="01b2c-390">yes</span></span>|
|<span data-ttu-id="01b2c-391">Teams</span><span class="sxs-lookup"><span data-stu-id="01b2c-391">Teams</span></span> |<span data-ttu-id="01b2c-392">예</span><span class="sxs-lookup"><span data-stu-id="01b2c-392">yes</span></span>   |
|<span data-ttu-id="01b2c-393">Windows 10 장치</span><span class="sxs-lookup"><span data-stu-id="01b2c-393">Windows 10 devices</span></span>         |<span data-ttu-id="01b2c-394">예</span><span class="sxs-lookup"><span data-stu-id="01b2c-394">yes</span></span> |
|<span data-ttu-id="01b2c-395">MAC</span><span class="sxs-lookup"><span data-stu-id="01b2c-395">MAC</span></span>         |<span data-ttu-id="01b2c-396">아니요</span><span class="sxs-lookup"><span data-stu-id="01b2c-396">no</span></span>     |
|<span data-ttu-id="01b2c-397">On-premises</span><span class="sxs-lookup"><span data-stu-id="01b2c-397">on-premises</span></span>         |<span data-ttu-id="01b2c-398">아니요</span><span class="sxs-lookup"><span data-stu-id="01b2c-398">no</span></span>|
|<span data-ttu-id="01b2c-399">MCAS</span><span class="sxs-lookup"><span data-stu-id="01b2c-399">MCAS</span></span>     |<span data-ttu-id="01b2c-400">아니요</span><span class="sxs-lookup"><span data-stu-id="01b2c-400">no</span></span>        | 

<span data-ttu-id="01b2c-401">Windows 10 장치(끝점 DLP)에 대한 이벤트는 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="01b2c-401">The events for Windows 10 Devices (Endpoint DLP) are:</span></span>

- <span data-ttu-id="01b2c-402">파일이 삭제되었습니다.</span><span class="sxs-lookup"><span data-stu-id="01b2c-402">file deleted</span></span>
- <span data-ttu-id="01b2c-403">만든 파일</span><span class="sxs-lookup"><span data-stu-id="01b2c-403">file created</span></span>
- <span data-ttu-id="01b2c-404">파일을 클립보드로 복사함</span><span class="sxs-lookup"><span data-stu-id="01b2c-404">file copied to clipboard</span></span>
- <span data-ttu-id="01b2c-405">파일 수정</span><span class="sxs-lookup"><span data-stu-id="01b2c-405">file modified</span></span>
- <span data-ttu-id="01b2c-406">파일 읽기</span><span class="sxs-lookup"><span data-stu-id="01b2c-406">file read</span></span>
- <span data-ttu-id="01b2c-407">인쇄된 파일</span><span class="sxs-lookup"><span data-stu-id="01b2c-407">file printed</span></span>
- <span data-ttu-id="01b2c-408">파일 이름 변경</span><span class="sxs-lookup"><span data-stu-id="01b2c-408">file renamed</span></span>
- <span data-ttu-id="01b2c-409">파일을 네트워크 공유에 복사함</span><span class="sxs-lookup"><span data-stu-id="01b2c-409">file copied to network share</span></span>
- <span data-ttu-id="01b2c-410">허용되지 않은 앱에서 액세스하는 파일</span><span class="sxs-lookup"><span data-stu-id="01b2c-410">file accessed by unallowed app</span></span>


## <a name="retention-label-applied"></a><span data-ttu-id="01b2c-411">적용된 보존 레이블</span><span class="sxs-lookup"><span data-stu-id="01b2c-411">Retention label applied</span></span> 

<span data-ttu-id="01b2c-412">이 이벤트는 레이블이 지정되지 않은 문서에 레이블이 지정되거나 전자 메일이 레이블과 함께 전송될 때마다 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="01b2c-412">This event is generated each time an unlabeled document is labeled or an email is sent with a label.</span></span>

- <span data-ttu-id="01b2c-413">Office 네이티브 응용 프로그램 및 웹 응용 프로그램에서 저장 시에 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="01b2c-413">It is captured at the time of save in Office native applications and web applications.</span></span>

|<span data-ttu-id="01b2c-414">원본</span><span class="sxs-lookup"><span data-stu-id="01b2c-414">Source</span></span>  |<span data-ttu-id="01b2c-415">활동 탐색기에서 보고</span><span class="sxs-lookup"><span data-stu-id="01b2c-415">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="01b2c-416">Exchange</span><span class="sxs-lookup"><span data-stu-id="01b2c-416">Exchange</span></span>         |<span data-ttu-id="01b2c-417">아니요</span><span class="sxs-lookup"><span data-stu-id="01b2c-417">no</span></span>       |
|<span data-ttu-id="01b2c-418">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="01b2c-418">SharePoint Online</span></span>|<span data-ttu-id="01b2c-419">예</span><span class="sxs-lookup"><span data-stu-id="01b2c-419">yes</span></span>          |
|<span data-ttu-id="01b2c-420">OneDrive</span><span class="sxs-lookup"><span data-stu-id="01b2c-420">OneDrive</span></span> |<span data-ttu-id="01b2c-421">예</span><span class="sxs-lookup"><span data-stu-id="01b2c-421">yes</span></span>|

## <a name="retention-label-changed"></a><span data-ttu-id="01b2c-422">보존 레이블 변경</span><span class="sxs-lookup"><span data-stu-id="01b2c-422">Retention label changed</span></span>

<span data-ttu-id="01b2c-423">이 이벤트는 문서 또는 전자 메일에서 레이블이 업데이트될 때마다 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="01b2c-423">This event is generated each time a label is updated on a document or email.</span></span>

- <span data-ttu-id="01b2c-424">저장 시에 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="01b2c-424">It is captured at the time of save.</span></span>

|<span data-ttu-id="01b2c-425">원본</span><span class="sxs-lookup"><span data-stu-id="01b2c-425">Source</span></span>  |<span data-ttu-id="01b2c-426">활동 탐색기에서 보고</span><span class="sxs-lookup"><span data-stu-id="01b2c-426">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="01b2c-427">Exchange</span><span class="sxs-lookup"><span data-stu-id="01b2c-427">Exchange</span></span>         |<span data-ttu-id="01b2c-428">아니요</span><span class="sxs-lookup"><span data-stu-id="01b2c-428">no</span></span>       |
|<span data-ttu-id="01b2c-429">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="01b2c-429">SharePoint Online</span></span>|<span data-ttu-id="01b2c-430">예</span><span class="sxs-lookup"><span data-stu-id="01b2c-430">yes</span></span>          |
|<span data-ttu-id="01b2c-431">OneDrive</span><span class="sxs-lookup"><span data-stu-id="01b2c-431">OneDrive</span></span> |<span data-ttu-id="01b2c-432">예</span><span class="sxs-lookup"><span data-stu-id="01b2c-432">yes</span></span>|
 
## <a name="retention-label-removed"></a><span data-ttu-id="01b2c-433">보존 레이블 제거됨</span><span class="sxs-lookup"><span data-stu-id="01b2c-433">Retention label removed</span></span>

<span data-ttu-id="01b2c-434">이 이벤트는 파일이나 문서에서 레이블을 제거할 때마다 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="01b2c-434">This event is generated each time a label is removed from a file or document.</span></span>

- <span data-ttu-id="01b2c-435">저장 시에 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="01b2c-435">It is captured at the time of save.</span></span>

|<span data-ttu-id="01b2c-436">원본</span><span class="sxs-lookup"><span data-stu-id="01b2c-436">Source</span></span>  |<span data-ttu-id="01b2c-437">활동 탐색기에서 보고</span><span class="sxs-lookup"><span data-stu-id="01b2c-437">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="01b2c-438">Exchange</span><span class="sxs-lookup"><span data-stu-id="01b2c-438">Exchange</span></span>         |<span data-ttu-id="01b2c-439">아니요</span><span class="sxs-lookup"><span data-stu-id="01b2c-439">no</span></span>       |
|<span data-ttu-id="01b2c-440">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="01b2c-440">SharePoint Online</span></span>|<span data-ttu-id="01b2c-441">예</span><span class="sxs-lookup"><span data-stu-id="01b2c-441">yes</span></span>          |
|<span data-ttu-id="01b2c-442">OneDrive</span><span class="sxs-lookup"><span data-stu-id="01b2c-442">OneDrive</span></span> |<span data-ttu-id="01b2c-443">예</span><span class="sxs-lookup"><span data-stu-id="01b2c-443">yes</span></span>|


## <a name="known-issues"></a><span data-ttu-id="01b2c-444">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="01b2c-444">Known issues</span></span>
  
- <span data-ttu-id="01b2c-445">최종 사용자에게 권장 레이블 도구 팁이 표시되어 있는 경우 캡처되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="01b2c-445">When the recommended label tool tip is shown to an end user, it is not captured.</span></span> <span data-ttu-id="01b2c-446">그러나 사용자가 권장 레이블을 적용하도록 선택한 경우 레이블은  적용 방법 필드에 *권장으로 표시됩니다.*</span><span class="sxs-lookup"><span data-stu-id="01b2c-446">But if the user chooses to apply the recommended label, the label will be shown under the *How applied* field as *Recommended*</span></span>  

- <span data-ttu-id="01b2c-447">사유 텍스트는 현재 Sharepoint 및 OneDrive에서 민감도 레이블 다운그레이드에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="01b2c-447">Justification text is not currently available on sensitivity label downgrade from Sharepoint and OneDrive.</span></span>  

- <span data-ttu-id="01b2c-448">중요한 정보 유형은 현재 Word, Excel, PowerPoint 및 Outlook뿐만 아니라 SharePoint Online 및 OneDrive의 자동레이블 활동에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="01b2c-448">Sensitive information types are currently not available for autolabeling activities from Word, Excel, PowerPoint, and Outlook, as well as SharePoint Online, and OneDrive.</span></span>
