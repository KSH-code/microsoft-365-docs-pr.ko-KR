---
title: 자동화된 조사 및 조치 작업을 보고 승인하려면 알림 센터로 이동합니다.
description: 자동화된 검사에 대한 세부 정보를 확인하고 보류 중인 작업을 승인하도록 알림 센터를 사용합니다.
keywords: 알림 센터, 위협 방지, 조사, 경고, 보류 중, 자동, 탐지
search.appverid: met150
ms.prod: M365-security-compliance
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 950dec4c0b0a2de2bdc60a73a12f6c7895189ea4
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911488"
---
# <a name="go-to-the-action-center-to-view-remediation-actions"></a><span data-ttu-id="de155-104">알림 센터로 이동하여 조치 작업을 봅니다.</span><span class="sxs-lookup"><span data-stu-id="de155-104">Go to the Action center to view remediation actions</span></span>

<span data-ttu-id="de155-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="de155-105">**Applies to:**</span></span>
- <span data-ttu-id="de155-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="de155-106">Microsoft Threat Protection</span></span>

[!include[Prerelease information](prerelease.md)]

## <a name="a-single-pane-of-glass-experience"></a><span data-ttu-id="de155-107">"단일 창 방식" 환경</span><span class="sxs-lookup"><span data-stu-id="de155-107">A "single pane of glass" experience</span></span>

![알림 센터 ](../images/air-actioncenter.png)

<span data-ttu-id="de155-109">알림 센터를 사용하여 조직의 장치 및 사서함 전체에서 현재 및 과거 조사의 결과를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de155-109">Use the Action center to see the results of current and past investigations across your organization's devices and mailboxes.</span></span> <span data-ttu-id="de155-110">위협 유형과 [결과 판정](mtp-autoir-results.md#remediation-actions-following-automated-investigation)에 따라 수정 작업이 자동으로 수행되거나 조직의 보안 운영 팀의 승인에 따라 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="de155-110">Depending on the type of threat and [resulting verdict](mtp-autoir-results.md#remediation-actions-following-automated-investigation), remediation actions occur automatically or upon approval by your organization’s security operations team.</span></span> <span data-ttu-id="de155-111">모든 수정 작업이 승인이 보류 중이든 이미 승인되었든 알림 센터에 통합되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de155-111">All remediation actions, whether they are pending approval or were already approved, are consolidated in the Action center.</span></span> 

<span data-ttu-id="de155-112">알림 센터를 통해 다음과 같은 작업에 대한 "단일 창 방식" 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="de155-112">The Action center provides a "single pane of glass" experience for tasks, such as:</span></span>
- <span data-ttu-id="de155-113">보류 중인 수정 작업 승인.</span><span class="sxs-lookup"><span data-stu-id="de155-113">Approving pending remediation actions;</span></span>
- <span data-ttu-id="de155-114">이미 승인된 수정 작업의 감사 로그 보기. 그리고</span><span class="sxs-lookup"><span data-stu-id="de155-114">Viewing an audit log of already approved remediation actions; and</span></span>
- <span data-ttu-id="de155-115">완료된 수정 작업을 검토</span><span class="sxs-lookup"><span data-stu-id="de155-115">Reviewing completed remediation actions.</span></span>

<span data-ttu-id="de155-116">알림 센터를 통해 회사에서 Microsoft Threat Protection를 종합적으로 볼 수 있기 때문에 보안 운영팀이 보다 효과적이고 효율적으로 운영될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de155-116">Your security operations team can operate more effectively and efficiently, because the Action center provides a comprehensive view of Microsoft Threat Protection at work.</span></span>

## <a name="remediation-actions"></a><span data-ttu-id="de155-117">수정 작업</span><span class="sxs-lookup"><span data-stu-id="de155-117">Remediation actions</span></span>

<span data-ttu-id="de155-118">다음 표에는 알림 센터에서 현재 지원되는 수정 작업이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de155-118">The following table lists remediation actions that are currently supported in the Action center:</span></span> 

|<span data-ttu-id="de155-119">끝점 수정 작업</span><span class="sxs-lookup"><span data-stu-id="de155-119">Endpoints remediation actions</span></span>  |<span data-ttu-id="de155-120">전자 메일 수정 작업</span><span class="sxs-lookup"><span data-stu-id="de155-120">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="de155-121">파일 격리</span><span class="sxs-lookup"><span data-stu-id="de155-121">Quarantine file</span></span><br/><span data-ttu-id="de155-122">레지스트리 키 추가</span><span class="sxs-lookup"><span data-stu-id="de155-122">Remove registry key</span></span><br/><span data-ttu-id="de155-123">프로세스 중단</span><span class="sxs-lookup"><span data-stu-id="de155-123">Kill process</span></span> <br/><span data-ttu-id="de155-124">서비스 중지</span><span class="sxs-lookup"><span data-stu-id="de155-124">Stop the service application</span></span> <br/><span data-ttu-id="de155-125">레지스트리 키 추가</span><span class="sxs-lookup"><span data-stu-id="de155-125">Remove registry key</span></span> <br/><span data-ttu-id="de155-126">드라이버 해제</span><span class="sxs-lookup"><span data-stu-id="de155-126">Disable driver</span></span> <br/><span data-ttu-id="de155-127">예약된 작업 제거</span><span class="sxs-lookup"><span data-stu-id="de155-127">Remove scheduled task</span></span>      |<span data-ttu-id="de155-128">전자 메일 메시지 또는 클러스터의 일시 삭제</span><span class="sxs-lookup"><span data-stu-id="de155-128">Soft delete email messages or clusters</span></span><br/><span data-ttu-id="de155-129">차단 URL(클릭 시간)</span><span class="sxs-lookup"><span data-stu-id="de155-129">Block URL (time-of-click)</span></span><br/><span data-ttu-id="de155-130">외부 메일 전달 해제</span><span class="sxs-lookup"><span data-stu-id="de155-130">Turn off external mail forwarding</span></span>          |

## <a name="go-to-the-action-center"></a><span data-ttu-id="de155-131">알림 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="de155-131">Go to the admin center.</span></span>

1. <span data-ttu-id="de155-132">[https://security.microsoft.com](https://security.microsoft.com)으로 이동하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="de155-132">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in with an admin account.</span></span> 

2. <span data-ttu-id="de155-133">탐색 창에서 **알림 센터**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="de155-133">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="de155-134">알림 센터에는 **보류 중**과 **기록**이라는 두 개의 탭이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="de155-134">In the Action center, you’ll see two tabs: **Pending** and **History**.</span></span>

    - <span data-ttu-id="de155-135">**보류 중** 탭에는 보안 운영팀의 누군가가 계속 진행하기 위해 검토하고 승인해야 하는 조사가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="de155-135">The **Pending** tab lists investigations that require review and approval by someone in your security operations team to continue.</span></span> <span data-ttu-id="de155-136">여기에 표시되는 보류 중인 항목을 검토하여 조치를 취해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de155-136">Make sure to review and take action on pending items you see here.</span></span>

    - <span data-ttu-id="de155-137">**기록** 탭에는 자동으로 수행된 과거 조사와 수정 작업이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="de155-137">The **History** tab lists past investigations and remediation actions that were taken automatically.</span></span> <span data-ttu-id="de155-138">지난 일, 주, 월 또는 6개월에 대한 데이터를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de155-138">You can view data for the past day, week, month, or six months.</span></span>

4. <span data-ttu-id="de155-139">원하는 열만 표시하려면 **열 사용자 정의**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="de155-139">To show only the columns you want to see, select **Customize columns**.</span></span><br/><span data-ttu-id="de155-140">![Microsoft Threat Protection의 알림 센터](../images/mtp-action-center.png)</span><span class="sxs-lookup"><span data-stu-id="de155-140">![Action Center in Microsoft Threat Protection](../images/mtp-action-center.png)</span></span>

5. <span data-ttu-id="de155-141">목록에서 항목을 선택하여 조사에 대한 자세한 정보를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="de155-141">Select an item in the list to view more details about an investigation.</span></span> <span data-ttu-id="de155-142">조사 세부 정보 보기가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="de155-142">The investigation details view opens.</span></span><br/>![조사 세부 정보](../images/mtp-air-investdetails.png)

    - <span data-ttu-id="de155-144">조사가 전자 메일 콘텐츠와 관련된 경우(예: 엔터티가 사서함인 경우) 조사 세부 정보는 Office 365 보안 및 준수 센터([https://protection.office.com/threatinvestigation](https://protection.office.com/threatinvestigation))에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="de155-144">If the investigation pertains to email content (such as, the entity is a mailbox), investigation details open in the Office 365 Security & Compliance Center ([https://protection.office.com/threatinvestigation](https://protection.office.com/threatinvestigation)).</span></span> 

    - <span data-ttu-id="de155-145">조사가 장치에 관련된 경우 조사 세부 정보는 보안 센터([https://security.microsoft.com](https://security.microsoft.com))에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="de155-145">If the investigation involves a device, investigation details open in the security center ([https://security.microsoft.com](https://security.microsoft.com)).</span></span> 

## <a name="required-permissions-for-action-center-tasks"></a><span data-ttu-id="de155-146">알림 센터 작업에 필요한 사용 권한</span><span class="sxs-lookup"><span data-stu-id="de155-146">Required permissions for Action center tasks</span></span>

<span data-ttu-id="de155-147">알림 센터에서 보류 중인 작업을 승인하거나 거부하려면 다음 표에 나열된 대로 사용 권한이 할당되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de155-147">To approve or reject pending actions in the Action center, you must have permissions assigned as listed in the following table:</span></span>

|<span data-ttu-id="de155-148">수정 작업</span><span class="sxs-lookup"><span data-stu-id="de155-148">Remediation action</span></span> |<span data-ttu-id="de155-149">필요한 역할 및 사용 권한 할당</span><span class="sxs-lookup"><span data-stu-id="de155-149">Required licenses and permissions</span></span> |
|--|----|
|<span data-ttu-id="de155-150">Microsoft Defender ATP 수정(장치)</span><span class="sxs-lookup"><span data-stu-id="de155-150">Microsoft Defender ATP remediation (devices)</span></span> |<span data-ttu-id="de155-151">Azure Active Directory([https://portal.azure.com](https://portal.azure.com)) 또는 Microsoft 365 관리 센터([https://admin.microsoft.com](https://admin.microsoft.com))에 할당된 **보안 관리자** 역할</span><span class="sxs-lookup"><span data-stu-id="de155-151">**Security Administrator** role assigned in either Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) or the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com))</span></span><br/><span data-ttu-id="de155-152">--- 또는 ---</span><span class="sxs-lookup"><span data-stu-id="de155-152">“+” or “-”</span></span><br/><span data-ttu-id="de155-153">Microsoft Defender ATP에서 할당된 **활성 수정 작업** 역할</span><span class="sxs-lookup"><span data-stu-id="de155-153">**Active remediation actions** role assigned in Microsoft Defender ATP</span></span> <br/> <br/> <span data-ttu-id="de155-154">자세한 내용은 다음 리소스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="de155-154">To learn more, see the following resources:</span></span> <br/><span data-ttu-id="de155-155">- [Azure Active Directory의 관리자 역할 권한](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="de155-155">Administrator role permissions in Azure Active Directory</span></span><br/><span data-ttu-id="de155-156">- [역할 기반 액세스 제어(Microsoft Defender ATP)를 위한 역할 만들기 및 관리](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)</span><span class="sxs-lookup"><span data-stu-id="de155-156">- [Create and manage roles for role-based access control (Microsoft Defender ATP)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)</span></span>  |
|<span data-ttu-id="de155-157">Office 365 ATP 수정(Office 콘텐츠 및 전자 메일)</span><span class="sxs-lookup"><span data-stu-id="de155-157">Office 365 ATP remediation (Office content and email)</span></span>  |<span data-ttu-id="de155-158">Azure Active Directory([https://portal.azure.com](https://portal.azure.com)) 또는 Microsoft 365 관리 센터([https://admin.microsoft.com](https://admin.microsoft.com))에 할당된 **보안 관리자** 역할</span><span class="sxs-lookup"><span data-stu-id="de155-158">**Security Administrator** role assigned in either Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) or the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com))</span></span><br/><span data-ttu-id="de155-159">--- 및 ---</span><span class="sxs-lookup"><span data-stu-id="de155-159">“{” and “}”</span></span> <br/><span data-ttu-id="de155-160">Office 365 보안 및 규정 준수 센터([https://protection.office.com](https://protection.office.com))에 할당된 **검색 및 제거** 역할</span><span class="sxs-lookup"><span data-stu-id="de155-160">Search and Purge (this is assigned only in the Office 365 Security & Compliance Center)</span></span> <br/><br/><span data-ttu-id="de155-161">**중요**: 보안 관리자 역할이 Office 365 보안 및 준수 센터에만 할당되어 있는 경우에는 알림 센터 또는 Microsoft Threat Protection 기능에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="de155-161">**IMPORTANT**: If you have the Security Administrator role assigned only in the Office 365 Security & Compliance Center, you will not be able to access the Action center or Microsoft Threat Protection capabilities.</span></span> <span data-ttu-id="de155-162">Azure Active Directory 또는 Microsoft 365 관리 센터에 할당된 보안 관리자 역할이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de155-162">You must have the Security Administrator role assigned in Azure Active Directory or the Microsoft 365 admin center.</span></span> <br/><br/><span data-ttu-id="de155-163">자세한 내용은 다음 리소스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="de155-163">To learn more, see the following resources:</span></span> <br/><span data-ttu-id="de155-164">- [Azure Active Directory의 관리자 역할 권한](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="de155-164">Administrator role permissions in Azure Active Directory</span></span><br/><span data-ttu-id="de155-165">- [Office 365 보안 및 준수 센터의 사용 권한](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)</span><span class="sxs-lookup"><span data-stu-id="de155-165">Permissions in the Office 365 Security & Compliance Center</span></span> |

> [!NOTE]
> <span data-ttu-id="de155-166">Azure Active Directory에서 **전역 관리자** 역할이 할당된 사용자는 알림 센터에서 대기 중인 모든 작업을 승인하거나 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de155-166">Users who have the **Global Administrator** role assigned in Azure Active Directory can approve or reject any pending action in the Action center.</span></span> <span data-ttu-id="de155-167">그러나 조직에서 전역 관리자 역할이 할당된 사용자 수를 제한하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="de155-167">However, as a best practice, your organization should limit the number of people who have the Global Administrator role assigned.</span></span> <span data-ttu-id="de155-168">알림 센터 사용 권한에 대해 위에 나열한 **보안 관리자**, **활성 수정 작업**, **검색 및 제거** 역할을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="de155-168">We recommend using the **Security Administrator**, **Active remediation actions**, and **Search and Purge** roles listed above for Action center permissions.</span></span>

## <a name="next-steps"></a><span data-ttu-id="de155-169">다음 단계</span><span class="sxs-lookup"><span data-stu-id="de155-169">Next steps</span></span> 

- [<span data-ttu-id="de155-170">Microsoft Threat Protection에 관해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="de155-170">Learn more about incidents in Microsoft Threat Protection</span></span>](incidents-overview.md)
- [<span data-ttu-id="de155-171">자동화된 조사 결과 보기</span><span class="sxs-lookup"><span data-stu-id="de155-171">View the results of an automated investigation</span></span>](mtp-autoir-results.md)
- [<span data-ttu-id="de155-172">Microsoft Threat Protection의 헌팅에 대해 알아보기</span><span class="sxs-lookup"><span data-stu-id="de155-172">Learn about hunting in Microsoft Threat Protection</span></span>](advanced-hunting-overview.md)

