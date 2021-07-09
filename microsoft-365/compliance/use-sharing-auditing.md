---
title: 감사 로그에서 공유 감사 사용
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- BCS160
- MET150
ms.collection:
- M365-security-compliance
- SPO_Content
ms.assetid: 50bbf89f-7870-4c2a-ae14-42635e0cfc01
description: 관리자는 조직 외부의 사용자와 공유되는 리소스를 식별하기 위해 Microsoft 365 감사 로그에서 공유 감사를 사용하는 방법을 배울 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 302ad7665c83ee9061b2e1965ef03ec25d0aab58
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341511"
---
# <a name="use-sharing-auditing-in-the-audit-log"></a><span data-ttu-id="d2014-103">감사 로그에서 공유 감사 사용</span><span class="sxs-lookup"><span data-stu-id="d2014-103">Use sharing auditing in the audit log</span></span>

<span data-ttu-id="d2014-104">공유는 SharePoint Online 및 비즈니스용 OneDrive 주요 활동으로, 조직에서 널리 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-104">Sharing is a key activity in SharePoint Online and OneDrive for Business, and it's widely used in organizations.</span></span> <span data-ttu-id="d2014-105">관리자는 감사 로그에서 공유 감사를 사용하여 조직에서 공유가 사용되는 방법을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-105">Administrators can use sharing auditing in the audit log to determine how sharing is used in their organization.</span></span> 
  
## <a name="the-sharepoint-sharing-schema"></a><span data-ttu-id="d2014-106">공유 SharePoint 공유</span><span class="sxs-lookup"><span data-stu-id="d2014-106">The SharePoint Sharing schema</span></span>

<span data-ttu-id="d2014-107">공유 이벤트(공유 정책 및 공유 링크와 관련된 이벤트는 포함하지 않는)는 한 사용자가 다른 사용자에게 영향을 미치기 위한 작업을 수행하는 한 가지 기본 방법으로 파일 및 폴더 관련 이벤트와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-107">Sharing events (not including events related to sharing policy and sharing links) are different from file- and folder-related events in one primary way: one user is performing an action that has an effect on another user.</span></span> <span data-ttu-id="d2014-108">예를 들어 리소스 사용자 A가 사용자 B에게 파일에 대한 액세스 권한을 부여할 때</span><span class="sxs-lookup"><span data-stu-id="d2014-108">For example, when a resource User A gives User B access to a file.</span></span> <span data-ttu-id="d2014-109">이 예에서 사용자 A는 행동하는 *사용자이자* 사용자 B는 대상 *사용자입니다.*</span><span class="sxs-lookup"><span data-stu-id="d2014-109">In this example, User A is the  *acting user*  and User B is the  *target user*.</span></span> <span data-ttu-id="d2014-110">파일 SharePoint 실행 사용자의 동작은 파일 자체에만 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-110">In the SharePoint File schema, the acting user's action only affects the file itself.</span></span> <span data-ttu-id="d2014-111">사용자 A가 파일을 열면 **FileAccessed** 이벤트에 필요한 유일한 정보는 역할을 하는 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-111">When User A opens a file, the only information needed in the **FileAccessed** event is the acting user.</span></span> <span data-ttu-id="d2014-112">이러한 차이를 해결하기 위해 공유 이벤트에 대한 자세한 정보를 캡처하는 SharePoint 공유 SharePoint 별도의 *schema가* 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-112">To address this difference, there is a separate schema, called the  *SharePoint Sharing schema*, that captures more information about sharing events.</span></span> <span data-ttu-id="d2014-113">이렇게 하면 관리자가 리소스를 공유한 사용자와 리소스를 공유한 사용자를 쉽게 확인하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-113">This ensures that administrators have visibility into who shared a resource and the user the resource was shared with.</span></span> 
  
<span data-ttu-id="d2014-114">공유 Schema는 공유 이벤트와 관련된 감사 레코드에 다음 두 개의 추가 필드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-114">The Sharing schema provides two additional fields in an audit record related to sharing events:</span></span> 
  
- <span data-ttu-id="d2014-115">**TargetUserOrGroupType:** 대상 사용자 또는 그룹이 구성원, 게스트, SharePointGroup, SecurityGroup 또는 Partner인지 여부를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-115">**TargetUserOrGroupType:** Identifies whether the target user or group is a Member, Guest, SharePointGroup, SecurityGroup, or Partner.</span></span>

- <span data-ttu-id="d2014-116">**TargetUserOrGroupName:** 리소스가 공유된 대상 사용자 또는 그룹의 UPN 또는 이름을 저장합니다(이전 예제의 사용자 B).</span><span class="sxs-lookup"><span data-stu-id="d2014-116">**TargetUserOrGroupName:** Stores the UPN or name of the target user or group that a resource was shared with (User B in the previous example).</span></span> 

<span data-ttu-id="d2014-117">이러한 두 필드는 사용자, 작업 및 날짜와 같은 감사 로그 스마마의 다른  속성 외에도  누가  누구와 언제 어떤 리소스를 공유한 사용자에 대한 전체 스토리를 알려 *주어질 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="d2014-117">These two fields, in addition to other properties from the audit log schema such as User, Operation, and Date can tell the full story about  *which*  user shared  *what*  resource with  *whom*  and  *when*.</span></span> 
  
<span data-ttu-id="d2014-118">공유 스토리에 중요한 또 다른 schema 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-118">There's another schema property that's important to the sharing story.</span></span> <span data-ttu-id="d2014-119">감사 로그 검색 결과를 내보낼 때 내보낼 CSV 파일의 **AuditData** 열에는 공유 이벤트에 대한 정보가 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-119">When you export audit log search results, the **AuditData** column in the exported CSV file stores information about sharing events.</span></span> <span data-ttu-id="d2014-120">예를 들어 사용자가 다른 사용자와 사이트를 공유하는 경우 이 작업을 수행하기 위해 대상 사용자를 SharePoint 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-120">For example, when a user shares a site with another user, this is accomplished by adding the target user to a SharePoint group.</span></span> <span data-ttu-id="d2014-121">**AuditData 열은** 이 정보를 캡처하여 관리자에게 컨텍스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-121">The **AuditData** column captures this information to provide context for administrators.</span></span> <span data-ttu-id="d2014-122">**AuditData** 열의 정보를 구문 분석하는 방법에 대한 지침은 [2단계를](#step-2-use-the-powerquery-editor-to-format-the-exported-audit-log) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d2014-122">See [Step 2](#step-2-use-the-powerquery-editor-to-format-the-exported-audit-log) for instructions on how to parse the information in the **AuditData** column.</span></span>

## <a name="sharepoint-sharing-events"></a><span data-ttu-id="d2014-123">SharePoint 공유 이벤트</span><span class="sxs-lookup"><span data-stu-id="d2014-123">SharePoint sharing events</span></span>

<span data-ttu-id="d2014-124">공유는 사용자(작업하는 사용자)가 다른 사용자(대상 사용자)와 리소스를 공유하려는 경우 *정의됩니다.* </span><span class="sxs-lookup"><span data-stu-id="d2014-124">Sharing is defined by when a user (the *acting* user) wants to share a resource with another user (the *target* user).</span></span> <span data-ttu-id="d2014-125">외부 사용자(조직 외부에 있으며 조직의 Azure Active Directory에 게스트 계정이 없는 사용자)와 리소스를 공유하는 데 관련된 감사 레코드는 감사 로그에 기록되는 다음 이벤트로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-125">Audit records related to sharing a resource with an external user (a user who is outside of your organization and doesn't have a guest account in your organization's Azure Active Directory) are identified by the following events, which are logged in the audit log:</span></span>

- <span data-ttu-id="d2014-126">**SharingInvitationCreated:** 조직의 사용자가 외부 사용자와 리소스(사이트)를 공유하려고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-126">**SharingInvitationCreated:** A user in your organization tried to share a resource (likely a site) with an external user.</span></span> <span data-ttu-id="d2014-127">그러면 대상 사용자에게 외부 공유 초대가 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-127">This results in an external sharing invitation sent to the target user.</span></span> <span data-ttu-id="d2014-128">이때 리소스에 대한 액세스 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-128">No access to the resource is granted at this point.</span></span>

- <span data-ttu-id="d2014-129">**SharingInvitationAccepted:** 외부 사용자가 작업 사용자가 보낸 공유 초대를 수락하고 이제 리소스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-129">**SharingInvitationAccepted:** The external user has accepted the sharing invitation sent by the acting user and now has access to the resource.</span></span>

- <span data-ttu-id="d2014-130">**AnonymousLinkCreated:** 리소스에 대해 익명 링크("모든 사용자" 링크)가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-130">**AnonymousLinkCreated:** An anonymous link (also called an "Anyone" link) is created for a resource.</span></span> <span data-ttu-id="d2014-131">익명 링크를 만든 다음 복사할 수 있기 때문에 익명 링크가 있는 문서가 대상 사용자와 공유된 것으로 가정하는 것이 타당합니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-131">Because an anonymous link can be created and then copied, it's reasonable to assume that any document that has an anonymous link has been shared with a target user.</span></span>

- <span data-ttu-id="d2014-132">**AnonymousLinkUsed:** 이름에서 알 수 있는 것 처럼 이 이벤트는 리소스에 액세스하는 데 익명 링크를 사용할 때 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-132">**AnonymousLinkUsed:** As the name implies, this event is logged when an anonymous link is used to access a resource.</span></span> 

- <span data-ttu-id="d2014-133">**SecureLinkCreated:** 사용자가 특정 사용자와 리소스를 공유하기 위한 "특정 사용자 링크"를 만들었다고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-133">**SecureLinkCreated:** A user has created a "specific people link" to share a resource with a specific person.</span></span> <span data-ttu-id="d2014-134">이 대상 사용자는 조직 외부의 사용자일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-134">This target user may be someone who is external to your organization.</span></span> <span data-ttu-id="d2014-135">리소스가 공유되는 사람은 **AddedToSecureLink** 이벤트에 대한 감사 레코드에서 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-135">The person that the resource is shared with is identified in the audit record for the **AddedToSecureLink** event.</span></span> <span data-ttu-id="d2014-136">이 두 이벤트의 타임스탬프는 거의 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-136">The time stamps for these two events are nearly identical.</span></span>

- <span data-ttu-id="d2014-137">**AddedToSecureLink:** 사용자가 특정 사용자 링크에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-137">**AddedToSecureLink:** A user was added to a specific people link.</span></span> <span data-ttu-id="d2014-138">이 **이벤트의 TargetUserOrGroupName** 필드를 사용하여 해당 특정 사용자 링크에 추가된 사용자를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-138">Use the **TargetUserOrGroupName** field in this event to identify the user added to the corresponding specific people link.</span></span> <span data-ttu-id="d2014-139">이 대상 사용자는 조직 외부의 사용자일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-139">This target user may be someone who is external to your organization.</span></span>

## <a name="sharing-auditing-work-flow"></a><span data-ttu-id="d2014-140">감사 작업 흐름 공유</span><span class="sxs-lookup"><span data-stu-id="d2014-140">Sharing auditing work flow</span></span>
  
<span data-ttu-id="d2014-141">사용자(작업하는 사용자)가 다른 사용자(대상 사용자)와 리소스를 공유하려는 경우 SharePoint(또는 비즈니스용 OneDrive)는 먼저 대상 사용자의 전자 메일 주소가 조직의 디렉터리에 있는 사용자 계정과 이미 연결되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-141">When a user (the acting user) wants to share a resource with another user (the target user), SharePoint (or OneDrive for Business) first checks if the email address of the target user is already associated with a user account in the organization's directory.</span></span> <span data-ttu-id="d2014-142">대상 사용자가 디렉터리에 있으며 해당 게스트 사용자 계정을 SharePoint 다음을 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-142">If the target user is in the directory (and has a corresponding guest user account), SharePoint does the following things:</span></span>
  
-  <span data-ttu-id="d2014-143">적절한 SharePoint 그룹에 대상 사용자를 추가하여 리소스에 액세스할 수 있는 권한을 대상 사용자에게 즉시 할당하고 **AddedToGroup** 이벤트를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-143">Immediately assigns the target user permissions to access the resource by adding the target user to the appropriate SharePoint group, and logs an **AddedToGroup** event.</span></span> 
    
- <span data-ttu-id="d2014-144">대상 사용자의 전자 메일 주소로 공유 알림을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-144">Sends a sharing notification to the email address of the target user.</span></span>
    
- <span data-ttu-id="d2014-145">**SharingSet 이벤트를 기록합니다.**</span><span class="sxs-lookup"><span data-stu-id="d2014-145">Logs a **SharingSet** event.</span></span> <span data-ttu-id="d2014-146">이 이벤트에는 감사 로그 검색 도구의 활동 선택기에서 공유 및 액세스 요청 활동 아래에 "공유 파일, 폴더 또는 사이트"라는 이름이 있습니다. </span><span class="sxs-lookup"><span data-stu-id="d2014-146">This event has a friendly name of "Shared file, folder, or site" under **Sharing and access request activities** in the activities picker of the audit log search tool.</span></span> <span data-ttu-id="d2014-147">1단계의 [스크린샷을 참조하세요.](#step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file)</span><span class="sxs-lookup"><span data-stu-id="d2014-147">See the screenshot in [Step 1](#step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file).</span></span> 
    
<span data-ttu-id="d2014-148">대상 사용자에 대한 사용자 계정이 디렉터리에 없는 경우 다음 SharePoint 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-148">If a user account for the target user isn't in the directory, SharePoint does the following:</span></span> 
    
   - <span data-ttu-id="d2014-149">리소스가 공유되는 방식에 따라 다음 이벤트 중 하나를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-149">Logs one of the following events, based on how the resource is shared:</span></span>
   
      - <span data-ttu-id="d2014-150">**AnonymousLinkCreated**</span><span class="sxs-lookup"><span data-stu-id="d2014-150">**AnonymousLinkCreated**</span></span>
   
      - <span data-ttu-id="d2014-151">**SecureLinkCreated**</span><span class="sxs-lookup"><span data-stu-id="d2014-151">**SecureLinkCreated**</span></span>
   
      - <span data-ttu-id="d2014-152">**AddedToSecureLink**</span><span class="sxs-lookup"><span data-stu-id="d2014-152">**AddedToSecureLink**</span></span> 

      - <span data-ttu-id="d2014-153">**SharingInvitationCreated(이** 이벤트는 공유 리소스가 사이트인 경우만 기록)</span><span class="sxs-lookup"><span data-stu-id="d2014-153">**SharingInvitationCreated** (this event is logged only when the shared resource is a site)</span></span>
    
   - <span data-ttu-id="d2014-154">대상 사용자가 초대의 링크를 클릭하여 전송된 공유 초대를 수락하면 SharePoint **SharingInvitationAccepted** 이벤트를 기록하고 리소스에 액세스하기 위한 대상 사용자 권한을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-154">When the target user accepts the sharing invitation that's sent to them (by clicking the link in the invitation), SharePoint logs a **SharingInvitationAccepted** event and assigns the target user permissions to access the resource.</span></span> <span data-ttu-id="d2014-155">대상 사용자가 익명 링크를 보내면 대상 사용자가 링크를 사용하여 리소스에 액세스한 후 **AnonymousLinkUsed** 이벤트가 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-155">If the target user is sent an anonymous link, the **AnonymousLinkUsed** event is logged after the target user uses the link to access the resource.</span></span> <span data-ttu-id="d2014-156">보안 링크의 경우 외부 사용자가 링크를 사용하여 리소스에 액세스할 때 **FileAccessed** 이벤트가 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-156">For secure links, a **FileAccessed** event is logged when an external user uses the link to access the resource.</span></span>

<span data-ttu-id="d2014-157">초대를 수락하는 사용자의 ID 및 초대를 수락한 사용자의 ID 등 대상 사용자에 대한 추가 정보도 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-157">Additional information about the target user is also logged, such as the identity of the user the invitation is to and the user who accepts the invitation.</span></span> <span data-ttu-id="d2014-158">경우에 따라 이러한 사용자(또는 전자 메일 주소)가 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-158">In some case, these users (or email addresses) can be different.</span></span> 

## <a name="how-to-identify-resources-shared-with-external-users"></a><span data-ttu-id="d2014-159">외부 사용자와 공유되는 리소스를 식별하는 방법</span><span class="sxs-lookup"><span data-stu-id="d2014-159">How to identify resources shared with external users</span></span>

<span data-ttu-id="d2014-160">관리자의 일반적인 요구 사항은 조직 외부의 사용자와 공유된 모든 리소스 목록을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-160">A common requirement for administrators is creating a list of all resources that have been shared with users outside of the organization.</span></span> <span data-ttu-id="d2014-161">관리자가 공유 감사를 사용하여 Office 365 목록을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-161">By using sharing auditing in Office 365, administrators can generate this list.</span></span> <span data-ttu-id="d2014-162">이 작업을 수행하는 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-162">Here's how.</span></span>
  
### <a name="step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file"></a><span data-ttu-id="d2014-163">1단계: 공유 이벤트 검색 및 CSV 파일로 결과 내보내기</span><span class="sxs-lookup"><span data-stu-id="d2014-163">Step 1: Search for sharing events and export the results to a CSV file</span></span>

<span data-ttu-id="d2014-164">첫 번째 단계는 감사 로그에서 공유 이벤트를 검색하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-164">The first step is to search the audit log for sharing events.</span></span> <span data-ttu-id="d2014-165">감사 로그 검색에 대한 자세한 내용은 (필요한 사용 권한 포함) 보안 및 준수 센터에서 감사 [로그 & 참조하세요.](search-the-audit-log-in-security-and-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="d2014-165">For more information (including the required permissions) about searching the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>
  
1. <span data-ttu-id="d2014-166"><https://compliance.microsoft.com>으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-166">Go to <https://compliance.microsoft.com>.</span></span>

2. <span data-ttu-id="d2014-167">회사 또는 학교 계정을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-167">Sign in using your work or school account.</span></span>

3. <span data-ttu-id="d2014-168">창의 왼쪽 창에서 Microsoft 365 규정 준수 센터 **를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d2014-168">In the left pane of the Microsoft 365 compliance center, click **Audit**.</span></span>

    <span data-ttu-id="d2014-169">**감사** 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-169">The **Audit** page is displayed.</span></span>

4. <span data-ttu-id="d2014-170">**활동에서** 공유 **및** 액세스 요청 활동을 클릭하여 공유 관련 이벤트를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-170">Under **Activities**, click **Sharing and access request activities** to search for sharing-related events.</span></span> 

    ![활동에서 공유 및 액세스 요청 활동 선택](../media/46bb25b7-1eb2-4adf-903a-cc9ab58639f9.png)
  
5. <span data-ttu-id="d2014-172">날짜 및 시간 범위를 선택하여 해당 기간 내에 발생한 공유 이벤트를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-172">Select a date and time range to find the sharing events that occurred within that period.</span></span> 

6. <span data-ttu-id="d2014-173">검색을 **클릭하여** 검색을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-173">Click **Search** to run the search.</span></span> 

7. <span data-ttu-id="d2014-174">검색 실행이 완료되고 결과가 표시되면 결과 내보내기 **모든** 결과 \> **다운로드 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d2014-174">When the search is finished running and the results are displayed, click **Export results** \> **Download all results**.</span></span>

    <span data-ttu-id="d2014-175">내보내기 옵션을 선택하면 창 아래쪽에 CSV 파일을 열거나 저장하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-175">After you select the export option, a message at the bottom of the window prompts you to open or save the CSV file.</span></span>

8. <span data-ttu-id="d2014-176">다른  \> **파일로 저장을** 클릭하고 CSV 파일을 로컬 컴퓨터의 폴더에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-176">Click **Save** \> **Save as** and save the CSV file to a folder on your local computer.</span></span> 

### <a name="step-2-use-the-powerquery-editor-to-format-the-exported-audit-log"></a><span data-ttu-id="d2014-177">2단계: PowerQuery 편집기를 사용하여 내보낼 감사 로그 형식 지정</span><span class="sxs-lookup"><span data-stu-id="d2014-177">Step 2: Use the PowerQuery Editor to format the exported audit log</span></span>

<span data-ttu-id="d2014-178">다음 단계는 다중 속성 JSON 개체로 구성된 **AuditData** 열의 각 속성을 Excel 쿼리 편집기에서 JSON 변환 기능을 사용하여 자체 열로 분할하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-178">The next step is to use the JSON transform feature in the Power Query Editor in Excel to split each property in the **AuditData** column (which consists of a multi-property JSON object) into its own column.</span></span> <span data-ttu-id="d2014-179">이렇게 하면 열을 필터링하여 공유와 관련된 레코드를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-179">This lets you filter columns to view records related to sharing</span></span>

<span data-ttu-id="d2014-180">단계별 지침을 보려면 [감사 로그 레코드 내보내기, 구성 및 보기](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor)의 “2단계: 파워 쿼리 편집기를 사용하여 내보낸 감사 로그의 서식 지정”을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d2014-180">For step-by-step instructions, see "Step 2: Format the exported audit log using the Power Query Editor" in [Export, configure, and view audit log records](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor).</span></span>

### <a name="step-3-filter-the-csv-file-for-resources-shared-with-external-users"></a><span data-ttu-id="d2014-181">3단계: 외부 사용자와 공유되는 리소스에 대해 CSV 파일 필터링</span><span class="sxs-lookup"><span data-stu-id="d2014-181">Step 3: Filter the CSV file for resources shared with external users</span></span>

<span data-ttu-id="d2014-182">다음 단계는 이전에 SharePoint 공유 이벤트 섹션에서 설명한 다른 공유 관련 이벤트에 대해 CSV를 [필터링하는](#sharepoint-sharing-events) 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-182">The next step is to filter the CSV for the different sharing-related events that were previously described in the [SharePoint sharing events](#sharepoint-sharing-events) section.</span></span> <span data-ttu-id="d2014-183">또는 **TargetUserOrGroupType** 열을 필터링하여 이 속성 값이 Guest인 모든 레코드를 표시할 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="d2014-183">Alternatively, you can filter the **TargetUserOrGroupType** column to display all records where the value of this property is **Guest**.</span></span> 

<span data-ttu-id="d2014-184">이전 단계의 지침을 따라 PowerQuery 편집기를 사용하여 CSV 파일을 준비한 후 다음을 수행하십시오.</span><span class="sxs-lookup"><span data-stu-id="d2014-184">After you've followed the instructions in the previous step to prepare the CSV file by using the PowerQuery editor, do the following:</span></span>
    
1. <span data-ttu-id="d2014-185">2단계에서 Excel 파일을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-185">Open the Excel file that you created in Step 2.</span></span> 

2. <span data-ttu-id="d2014-186">홈 **탭에서** 정렬 **필터를 &** 클릭한 다음 필터 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d2014-186">On the **Home** tab, click **Sort & Filter**, and then click **Filter**.</span></span>
    
3. <span data-ttu-id="d2014-187">작업 **열의** 정렬 & 필터 드롭다운  목록에서 모든 선택을 취소한 다음 다음 공유 관련 이벤트를 하나 이상 선택한 다음 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d2014-187">In the **Sort & Filter** dropdown list on the **Operations** column, clear all selections, then select one or more the following sharing-related events and then click **Ok**.</span></span>
 
   - <span data-ttu-id="d2014-188">**SharingInvitationCreated**</span><span class="sxs-lookup"><span data-stu-id="d2014-188">**SharingInvitationCreated**</span></span>
   
   - <span data-ttu-id="d2014-189">**AnonymousLinkCreated**</span><span class="sxs-lookup"><span data-stu-id="d2014-189">**AnonymousLinkCreated**</span></span>
   
   - <span data-ttu-id="d2014-190">**SecureLinkCreated**</span><span class="sxs-lookup"><span data-stu-id="d2014-190">**SecureLinkCreated**</span></span>
   
   - <span data-ttu-id="d2014-191">**AddedToSecureLink**</span><span class="sxs-lookup"><span data-stu-id="d2014-191">**AddedToSecureLink**</span></span> 
    
    <span data-ttu-id="d2014-192">Excel 선택한 이벤트의 행이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-192">Excel displays the rows for the events you selected.</span></span>
    
4. <span data-ttu-id="d2014-193">**TargetUserOrGroupType** 열로 이동하여 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-193">Go to the column named **TargetUserOrGroupType** and select it.</span></span> 
    
5. <span data-ttu-id="d2014-194">정렬 & **필터** 드롭다운 목록에서 모든 선택을 지운 다음 **TargetUserOrGroupType:Guest를** 선택하고 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d2014-194">In the **Sort & Filter** dropdown list, clear all selections, then select **TargetUserOrGroupType:Guest**, and click **Ok**.</span></span>
    
    <span data-ttu-id="d2014-195">이제 Excel 외부 사용자가 **TargetUserOrGroupType:Guest** 값으로 식별되어 이벤트 및 대상 사용자가 조직 외부에 있는 위치를 공유하기 위한 행이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-195">Now Excel displays the rows for sharing events AND where the target user is outside of your organization, because external users are identified by the value **TargetUserOrGroupType:Guest**.</span></span> 
  
> [!TIP]
> <span data-ttu-id="d2014-196">표시되는 감사 레코드의 경우 **ObjectId** 열은 대상 사용자와 공유된 리소스를 식별합니다. 예를 들면  `ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx` 입니다.</span><span class="sxs-lookup"><span data-stu-id="d2014-196">For the audit records that are displayed, the **ObjectId** column identifies the resource that was shared with the target user; for example  `ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx`.</span></span>
