---
title: 자동화된 조사 및 조치 작업을 보고 승인하려면 알림 센터로 이동합니다.
description: 자동화된 검사에 대한 세부 정보를 확인하고 보류 중인 작업을 승인하도록 알림 센터를 사용합니다.
keywords: 알림 센터, 위협 방지, 조사, 경고, 보류 중, 자동, 탐지
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 09/16/2020
ms.openlocfilehash: 651beeff6326e6cab898c4297bcd50edc241a9d4
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413689"
---
# <a name="the-action-center"></a><span data-ttu-id="571e9-104">알림 센터</span><span class="sxs-lookup"><span data-stu-id="571e9-104">The Action center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="571e9-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="571e9-105">**Applies to:**</span></span>
- <span data-ttu-id="571e9-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="571e9-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="571e9-107">알림 센터를 사용하여 조직의 장치 및 사서함 전체에서 현재 및 과거 조사의 결과를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="571e9-107">Use the Action center to see the results of current and past investigations across your organization's devices and mailboxes.</span></span> <span data-ttu-id="571e9-108">위협 유형 및 결과 결과에 따라 [업데이트 관리 작업](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) 은 조직의 보안 운영 팀의 승인을 받을 때 자동으로 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="571e9-108">Depending on the type of threat and resulting verdict, [remediation actions](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) occur automatically or upon approval by your organization's security operations team.</span></span> <span data-ttu-id="571e9-109">모든 수정 작업이 승인이 보류 중이든 이미 승인되었든 알림 센터에 통합되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="571e9-109">All remediation actions, whether they are pending approval or were already approved, are consolidated in the Action center.</span></span> 

![알림 센터 ](../../media/air-actioncenter.png)

## <a name="a-single-pane-of-glass-experience"></a><span data-ttu-id="571e9-111">"단일 창 방식" 환경</span><span class="sxs-lookup"><span data-stu-id="571e9-111">A "single pane of glass" experience</span></span>

<span data-ttu-id="571e9-112">알림 센터를 통해 다음과 같은 작업에 대한 "단일 창 방식" 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="571e9-112">The Action center provides a "single pane of glass" experience for tasks, such as:</span></span>
- <span data-ttu-id="571e9-113">보류 중인 수정 작업 승인.</span><span class="sxs-lookup"><span data-stu-id="571e9-113">Approving pending remediation actions;</span></span>
- <span data-ttu-id="571e9-114">이미 승인된 수정 작업의 감사 로그 보기. 그리고</span><span class="sxs-lookup"><span data-stu-id="571e9-114">Viewing an audit log of already approved remediation actions; and</span></span>
- <span data-ttu-id="571e9-115">완료된 수정 작업을 검토</span><span class="sxs-lookup"><span data-stu-id="571e9-115">Reviewing completed remediation actions.</span></span>

<span data-ttu-id="571e9-116">알림 센터를 통해 회사에서 Microsoft Threat Protection를 종합적으로 볼 수 있기 때문에 보안 운영팀이 보다 효과적이고 효율적으로 운영될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="571e9-116">Your security operations team can operate more effectively and efficiently, because the Action center provides a comprehensive view of Microsoft Threat Protection at work.</span></span>

## <a name="go-to-the-action-center"></a><span data-ttu-id="571e9-117">알림 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="571e9-117">Go to the Action center</span></span>

1. <span data-ttu-id="571e9-118">[https://security.microsoft.com](https://security.microsoft.com)으로 이동하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="571e9-118">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="571e9-119">탐색 창에서 **작업 센터**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="571e9-119">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="571e9-120">작업 센터에는 **보류 중** 및 **기록**이라는 두 개의 탭이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="571e9-120">In the Action center, you'll see two tabs: **Pending** and **History**.</span></span>

    - <span data-ttu-id="571e9-121">**보류 중** 탭에는 보안 운영팀의 누군가가 계속 진행하기 위해 검토하고 승인해야 하는 조사가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="571e9-121">The **Pending** tab lists investigations that require review and approval by someone in your security operations team to continue.</span></span> <span data-ttu-id="571e9-122">여기에 표시되는 보류 중인 항목을 검토하여 조치를 취해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="571e9-122">Make sure to review and take action on pending items you see here.</span></span>

    - <span data-ttu-id="571e9-123">**기록** 탭에는 자동으로 수행된 과거 조사와 수정 작업이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="571e9-123">The **History** tab lists past investigations and remediation actions that were taken automatically.</span></span> <span data-ttu-id="571e9-124">지난 일, 주, 월 또는 6개월에 대한 데이터를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="571e9-124">You can view data for the past day, week, month, or six months.</span></span>

4. <span data-ttu-id="571e9-125">원하는 열만 표시하려면 **열 사용자 정의**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="571e9-125">To show only the columns you want to see, select **Customize columns**.</span></span><br/><span data-ttu-id="571e9-126">![Microsoft Threat Protection의 알림 센터](../../media/mtp-action-center.png)</span><span class="sxs-lookup"><span data-stu-id="571e9-126">![Action Center in Microsoft Threat Protection](../../media/mtp-action-center.png)</span></span>

5. <span data-ttu-id="571e9-127">목록에서 항목을 선택하여 조사에 대한 자세한 정보를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="571e9-127">Select an item in the list to view more details about an investigation.</span></span> <span data-ttu-id="571e9-128">조사 세부 정보 보기가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="571e9-128">The investigation details view opens.</span></span><br/>![조사 세부 정보](../../media/mtp-air-investdetails.png)

    - <span data-ttu-id="571e9-130">조사가 전자 메일 콘텐츠와 관련 된 경우 (예: 엔터티가 사서함 인 경우) 보안 & 준수 센터 ()에서 조사 세부 정보를 엽니다 [https://protection.office.com/threatinvestigation](https://protection.office.com/threatinvestigation) .</span><span class="sxs-lookup"><span data-stu-id="571e9-130">If the investigation pertains to email content (such as, the entity is a mailbox), investigation details open in the Security & Compliance Center ([https://protection.office.com/threatinvestigation](https://protection.office.com/threatinvestigation)).</span></span> 

    - <span data-ttu-id="571e9-131">조사가 장치에 관련된 경우 조사 세부 정보는 보안 센터([https://security.microsoft.com](https://security.microsoft.com))에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="571e9-131">If the investigation involves a device, investigation details open in the security center ([https://security.microsoft.com](https://security.microsoft.com)).</span></span> 

> [!TIP]
> <span data-ttu-id="571e9-132">Microsoft Threat Protection의 자동화 된 조사 및 응답 기능을 통해 누락 되었거나 지워지는이 감지 되었다고 생각 되 면 알려주세요.</span><span class="sxs-lookup"><span data-stu-id="571e9-132">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft Threat Protection, let us know!</span></span> <span data-ttu-id="571e9-133">[Microsoft Threat Protection에서 자동 조사 및 응답 (AIR) 기능을 통해 허위 긍정/네거티브를 보고 하는 방법을](mtp-autoir-report-false-positives-negatives.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="571e9-133">See [How to report false positives/negatives in automated investigation and response (AIR) capabilities in Microsoft Threat Protection](mtp-autoir-report-false-positives-negatives.md).</span></span>

## <a name="available-actions"></a><span data-ttu-id="571e9-134">사용 가능한 작업</span><span class="sxs-lookup"><span data-stu-id="571e9-134">Available actions</span></span>

<span data-ttu-id="571e9-135">재구성 작업이 수행 됨에 따라 작업 센터의 히스토리 탭에 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="571e9-135">As remediation actions are taken, they're listed on the History tab in the Action center.</span></span> <span data-ttu-id="571e9-136">이러한 작업에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="571e9-136">Such actions include the following:</span></span>

- <span data-ttu-id="571e9-137">수집 조사 패키지</span><span class="sxs-lookup"><span data-stu-id="571e9-137">Collect investigation package</span></span> 
- <span data-ttu-id="571e9-138">장치 격리 (이 작업은 실행 취소할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="571e9-138">Isolate device (this action can be undone)</span></span> 
- <span data-ttu-id="571e9-139">Offboard 컴퓨터</span><span class="sxs-lookup"><span data-stu-id="571e9-139">Offboard machine</span></span> 
- <span data-ttu-id="571e9-140">릴리스 코드 실행</span><span class="sxs-lookup"><span data-stu-id="571e9-140">Release code execution</span></span> 
- <span data-ttu-id="571e9-141">격리에서 릴리스</span><span class="sxs-lookup"><span data-stu-id="571e9-141">Release from quarantine</span></span> 
- <span data-ttu-id="571e9-142">요청 샘플</span><span class="sxs-lookup"><span data-stu-id="571e9-142">Request sample</span></span> 
- <span data-ttu-id="571e9-143">코드 실행 제한 (이 작업을 실행 취소할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="571e9-143">Restrict code execution (this action can be undone)</span></span> 
- <span data-ttu-id="571e9-144">바이러스 검사 실행</span><span class="sxs-lookup"><span data-stu-id="571e9-144">Run antivirus scan</span></span> 
- <span data-ttu-id="571e9-145">중지 및 격리</span><span class="sxs-lookup"><span data-stu-id="571e9-145">Stop and quarantine</span></span> 

## <a name="required-permissions-for-action-center-tasks"></a><span data-ttu-id="571e9-146">알림 센터 작업에 필요한 사용 권한</span><span class="sxs-lookup"><span data-stu-id="571e9-146">Required permissions for Action center tasks</span></span>

<span data-ttu-id="571e9-147">알림 센터에서 보류 중인 작업을 승인하거나 거부하려면 다음 표에 나열된 대로 사용 권한이 할당되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="571e9-147">To approve or reject pending actions in the Action center, you must have permissions assigned as listed in the following table:</span></span>

|<span data-ttu-id="571e9-148">수정 작업</span><span class="sxs-lookup"><span data-stu-id="571e9-148">Remediation action</span></span> |<span data-ttu-id="571e9-149">필요한 역할 및 사용 권한 할당</span><span class="sxs-lookup"><span data-stu-id="571e9-149">Required roles and permissions</span></span> |
|--|----|
|<span data-ttu-id="571e9-150">Microsoft Defender ATP 수정(장치)</span><span class="sxs-lookup"><span data-stu-id="571e9-150">Microsoft Defender ATP remediation (devices)</span></span> |<span data-ttu-id="571e9-151">Azure Active Directory([https://portal.azure.com](https://portal.azure.com)) 또는 Microsoft 365 관리 센터([https://admin.microsoft.com](https://admin.microsoft.com))에 할당된 보안 관리자 역할</span><span class="sxs-lookup"><span data-stu-id="571e9-151">Security Administrator role assigned in either Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) or the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com))</span></span><br/><span data-ttu-id="571e9-152">--- 또는 ---</span><span class="sxs-lookup"><span data-stu-id="571e9-152">--- or ---</span></span><br/><span data-ttu-id="571e9-153">Microsoft Defender ATP에서 할당된 활성 수정 작업 역할</span><span class="sxs-lookup"><span data-stu-id="571e9-153">Active remediation actions role assigned in Microsoft Defender ATP</span></span> <br/> <br/> <span data-ttu-id="571e9-154">자세한 내용은 다음 리소스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="571e9-154">To learn more, see the following resources:</span></span> <br/><span data-ttu-id="571e9-155">- [Azure Active Directory의 관리자 역할 권한](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="571e9-155">- [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span></span><br/><span data-ttu-id="571e9-156">- [역할 기반 액세스 제어(Microsoft Defender ATP)를 위한 역할 만들기 및 관리](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)</span><span class="sxs-lookup"><span data-stu-id="571e9-156">- [Create and manage roles for role-based access control (Microsoft Defender ATP)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)</span></span>  |
|<span data-ttu-id="571e9-157">Office 365 ATP 수정(Office 콘텐츠 및 전자 메일)</span><span class="sxs-lookup"><span data-stu-id="571e9-157">Office 365 ATP remediation (Office content and email)</span></span>  |<span data-ttu-id="571e9-158">Azure Active Directory([https://portal.azure.com](https://portal.azure.com)) 또는 Microsoft 365 관리 센터([https://admin.microsoft.com](https://admin.microsoft.com))에 할당된 보안 관리자 역할</span><span class="sxs-lookup"><span data-stu-id="571e9-158">Security Administrator role assigned in either Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) or the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com))</span></span><br/><span data-ttu-id="571e9-159">--- 및 ---</span><span class="sxs-lookup"><span data-stu-id="571e9-159">--- and ---</span></span> <br/><span data-ttu-id="571e9-160">보안 & 준수 센터 ()가 할당 된 검색 및 제거 역할 [https://protection.office.com](https://protection.office.com)</span><span class="sxs-lookup"><span data-stu-id="571e9-160">Search and Purge role assigned the Security & Compliance Center ([https://protection.office.com](https://protection.office.com))</span></span> <br/><br/><span data-ttu-id="571e9-161">**중요**: 보안 관리자 역할이 보안 & 준수 센터에만 할당 된 경우에는 작업 센터 또는 Microsoft Threat Protection 기능에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="571e9-161">**IMPORTANT**: If you have the Security Administrator role assigned only in the Security & Compliance Center, you will not be able to access the Action center or Microsoft Threat Protection capabilities.</span></span> <span data-ttu-id="571e9-162">Azure Active Directory 또는 Microsoft 365 관리 센터에 할당된 보안 관리자 역할이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="571e9-162">You must have the Security Administrator role assigned in Azure Active Directory or the Microsoft 365 admin center.</span></span> <br/><br/><span data-ttu-id="571e9-163">자세한 내용은 다음 리소스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="571e9-163">To learn more, see the following resources:</span></span> <br/><span data-ttu-id="571e9-164">- [Azure Active Directory의 관리자 역할 권한](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="571e9-164">- [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span></span><br/><span data-ttu-id="571e9-165">- [보안 & 준수 센터의 사용 권한](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)</span><span class="sxs-lookup"><span data-stu-id="571e9-165">- [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)</span></span> |

> [!NOTE]
> <span data-ttu-id="571e9-166">Azure Active Directory에서 전역 관리자 역할이 할당된 사용자는 알림 센터에서 대기 중인 모든 작업을 승인하거나 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="571e9-166">Users who have the Global Administrator role assigned in Azure Active Directory can approve or reject any pending action in the Action center.</span></span> <span data-ttu-id="571e9-167">그러나 조직에서 전역 관리자 역할이 할당된 사용자 수를 제한하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="571e9-167">However, as a best practice, your organization should limit the number of people who have the Global Administrator role assigned.</span></span> <span data-ttu-id="571e9-168">알림 센터 사용 권한에 대해 위에 나열한 보안 관리자, 활성 수정 작업, 검색 및 제거 역할을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="571e9-168">We recommend using the Security Administrator, Active remediation actions, and Search and Purge roles listed above for Action center permissions.</span></span>

## <a name="next-steps"></a><span data-ttu-id="571e9-169">다음 단계</span><span class="sxs-lookup"><span data-stu-id="571e9-169">Next steps</span></span> 

- [<span data-ttu-id="571e9-170">자동화 된 조사에 따라 보류 중인 작업 승인 또는 거부</span><span class="sxs-lookup"><span data-stu-id="571e9-170">Approve or reject pending actions following an automated investigation</span></span>](mtp-autoir-actions.md)
- [<span data-ttu-id="571e9-171">자동화된 조사 결과 보기</span><span class="sxs-lookup"><span data-stu-id="571e9-171">View the results of an automated investigation</span></span>](mtp-autoir-results.md)

