---
title: Microsoft 365 기본 감사 설정
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
ms.collection:
- M365-security-compliance
- m365solution-audit
- m365initiative-compliance
- m365solution-scenario
search.appverid:
- MOE150
- MET150
description: 이 문서에서는 조직의 사용자와 관리자가 수행하는 감사 활동을 검색할 수 있도록 기본 감사를 설정하는 방법에 대해 설명합니다.
ms.openlocfilehash: 59b5c85003ef0e19f7d3dd7417f764f446244652
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52564832"
---
# <a name="set-up-basic-audit-in-microsoft-365"></a><span data-ttu-id="b98ae-103">Microsoft 365 기본 감사 설정</span><span class="sxs-lookup"><span data-stu-id="b98ae-103">Set up Basic Audit in Microsoft 365</span></span>

<span data-ttu-id="b98ae-104">Microsoft 365 기본 감사를 사용하면 사용자와 관리자가 다른 Microsoft 365 서비스에서 수행되는 활동에 대한 감사 기록을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b98ae-104">Basic Audit in Microsoft 365 lets you search for audit records for activities performed in the different Microsoft 365 services by users and admins.</span></span> <span data-ttu-id="b98ae-105">기본 감사는 대부분의 Microsoft 365 및 Office 365 조직에 대해 기본적으로 활성화되므로 조직의 다른 사용자가 감사 로그를 검색하기 전에 수행해야 하는 일은 몇 가지일 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="b98ae-105">Because Basic Audit is enabled by default for most Microsoft 365 and Office 365 organizations, there's only a few things you need to do before you and others in your organization can search the audit log.</span></span>

<span data-ttu-id="b98ae-106">이 문서에서는 기본 감사를 설정하는 데 필요한 다음 단계에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b98ae-106">This article discusses the following steps necessary to set up Basic Audit.</span></span>

![기본 감사를 설정하는 단계](../media/BasicAuditingWorkflow.png)

<span data-ttu-id="b98ae-108">이러한 단계에는 감사 기록을 생성 및 보존하는 데 필요한 적절한 조직 구독 및 사용자 라이선스를 보장하고 감사 로그를 검색할 수 있도록 보안 운영, IT, 규정 준수 및 법률 팀의 팀 구성원에게 권한을 할당하는 것이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b98ae-108">These steps include ensuring the proper organizational subscriptions and user licensing required to generate and preserve audit records and assigning permissions to team members of your security operations, IT, compliance, and legal teams so that can search the audit log.</span></span>

<span data-ttu-id="b98ae-109">자세한 내용은 [Microsoft 365 기본 감사를](auditing-solutions-overview.md#basic-audit)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b98ae-109">For more information, see [Basic Audit in Microsoft 365](auditing-solutions-overview.md#basic-audit).</span></span>

## <a name="step-1-verify-organization-subscription-and-user-licensing"></a><span data-ttu-id="b98ae-110">1단계: 조직 구독 및 사용자 라이선스 확인</span><span class="sxs-lookup"><span data-stu-id="b98ae-110">Step 1: Verify organization subscription and user licensing</span></span>

<span data-ttu-id="b98ae-111">기본 감사에 대한 라이선스에는 감사 기록 및 유지에 필요한 감사 로그 검색 도구 및 사용자별 라이선스에 대한 액세스를 제공하는 적절한 조직 구독이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b98ae-111">Licensing for Basic Audit requires the appropriate organization subscription that provides access to audit log search tool and per-user licensing that's required to log and retain audit records.</span></span>

<span data-ttu-id="b98ae-112">사용자 또는 관리자가 감사되는 활동을 수행하면 감사 레코드가 생성되어 조직의 감사 로그에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="b98ae-112">When an audited activity is performed by a user or admin, an audit record is generated and stored in the audit log for your organization.</span></span> <span data-ttu-id="b98ae-113">기본 감사에서는 감사 기록이 90일 동안 감사 로그에서 보관되고 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b98ae-113">In Basic Audit, audit records are retained and searchable in the audit log for 90 days.</span></span>

<span data-ttu-id="b98ae-114">기본 감사에 대한 구독 및 라이선스 요구 사항 목록은 [Microsoft 365 감사 솔루션을](auditing-solutions-overview.md#licensing-requirements)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b98ae-114">For a list of subscription and licensing requirements for Basic Audit, see [Auditing solutions in Microsoft 365](auditing-solutions-overview.md#licensing-requirements).</span></span>

## <a name="step-2-assign-permissions-to-search-the-audit-log"></a><span data-ttu-id="b98ae-115">2단계: 감사 로그를 검색할 수 있는 권한을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="b98ae-115">Step 2: Assign permissions to search the audit log</span></span>

<span data-ttu-id="b98ae-116">관리자와 조사 팀의 구성원은 감사 로그를 검색하기 위해 Exchange Online View-Only 감사 로그 또는 감사 로그 역할을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b98ae-116">Admins and members of investigation teams must be assigned the View-Only Audit Logs or Audit Logs role in Exchange Online to search the audit log.</span></span> <span data-ttu-id="b98ae-117">기본적으로 이러한 역할은 Exchange 관리 센터의 **사용 권한** 페이지에서 규정 준수 관리 및 조직 관리 역할 그룹에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="b98ae-117">By default, these roles are assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="b98ae-118">Office 365 및 Microsoft 365 글로벌 관리자는 Exchange Online 조직 관리 역할 그룹의 구성원으로 자동으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="b98ae-118">Global administrators in Office 365 and Microsoft 365 are automatically added as members of the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="b98ae-119">최소 권한 수준을 사용하여 감사 로그를 검색할 수 있는 권한을 사용자에게 제공하려면 Exchange Online에서 사용자 지정 역할 그룹을 만들고, 보기 전용 감사 로그 또는 감사 로그 역할을 추가한 다음, 새 역할 그룹의 구성원으로 사용자를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b98ae-119">To give a user the ability to search the audit log with the minimum level of privileges, you can create a custom role group in Exchange Online, add the View-Only Audit Logs or Audit Logs role, and then add the user as a member of the new role group.</span></span> <span data-ttu-id="b98ae-120">자세한 내용은 [Exchange Online에서 역할 그룹 관리](/Exchange/permissions-exo/role-groups)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b98ae-120">For more information, see [Manage role groups in Exchange Online](/Exchange/permissions-exo/role-groups).</span></span>

<span data-ttu-id="b98ae-121">다음 스크린샷에는 Exchange 관리 센터의 조직 관리 역할 그룹에 할당된 두 개의 감사 관련 역할이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b98ae-121">The following screenshot shows the two audit-related roles assigned to the Organization Management role group in the Exchange admin center.</span></span>

![Exchange Online 역할 그룹에 할당된 감사 역할](../media/EACAuditRoles.png)

## <a name="step-3-search-the-audit-log"></a><span data-ttu-id="b98ae-123">3단계: 감사 기록 검색</span><span class="sxs-lookup"><span data-stu-id="b98ae-123">Step 3: Search the audit log</span></span>

<span data-ttu-id="b98ae-124">이제 Microsoft 365 규정 준수 센터에서 감사 로그를 검색할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b98ae-124">Now you're ready to search the audit log in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="b98ae-125">적절한 <https://compliance.microsoft.com> 감사 권한이 할당된 계정을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="b98ae-125">Go to <https://compliance.microsoft.com> and sign in using an account that has been assigned the appropriate audit permissions.</span></span>

2. <span data-ttu-id="b98ae-126">Microsoft 365 규정 준수 센터의 왼쪽 탐색 창에서 **모든 표시를** 클릭한 다음 **감사를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b98ae-126">In the left navigation pane of the Microsoft 365 compliance center, click **Show all** and then click **Audit**.</span></span>

3. <span data-ttu-id="b98ae-127">**감사** 페이지에서 **검색** 탭에서 다음 조건을 사용하여 검색을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b98ae-127">On the **Audit** page, configure the search using the following conditions on the **Search** tab.</span></span> 

   ![감사 로그 검색을 위한 구성 설정](../media/AuditLogSearchToolMCCCallouts.png)

   1. <span data-ttu-id="b98ae-129">**날짜 및 시간 범위**.</span><span class="sxs-lookup"><span data-stu-id="b98ae-129">**Date and time range**.</span></span> <span data-ttu-id="b98ae-130">날짜 및 시간 범위를 선택하여 해당 기간 내에 발생한 이벤트를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="b98ae-130">Select a date and time range to display the events that occurred within that period.</span></span> <span data-ttu-id="b98ae-131">날짜 및 시간은 현지 시간으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b98ae-131">The date and time are presented in local time.</span></span> <span data-ttu-id="b98ae-132">마지막 7일은 기본적으로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="b98ae-132">The last seven days are selected by default.</span></span>
  
   2. <span data-ttu-id="b98ae-133">**활동**.</span><span class="sxs-lookup"><span data-stu-id="b98ae-133">**Activities**.</span></span> <span data-ttu-id="b98ae-134">검색할 활동을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b98ae-134">Select the activities to search for.</span></span> <span data-ttu-id="b98ae-135">검색 상자를 사용하여 목록에 추가할 활동을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="b98ae-135">Use the search box to search for activities to add to the list.</span></span> <span data-ttu-id="b98ae-136">감사된 활동의 일부 목록은 [감사된 활동을](search-the-audit-log-in-security-and-compliance.md#audited-activities)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b98ae-136">For a partial list of audited activities, see [Audited activities](search-the-audit-log-in-security-and-compliance.md#audited-activities).</span></span> <span data-ttu-id="b98ae-137">이 상자를 비워 모든 감사된 활동에 대한 항목을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b98ae-137">Leave this box blank to return entries for all audited activities.</span></span>
  
   3. <span data-ttu-id="b98ae-138">**사용자**.</span><span class="sxs-lookup"><span data-stu-id="b98ae-138">**Users**.</span></span>  <span data-ttu-id="b98ae-139">이 상자를 클릭하고 사용자 이름을 입력하여 검색 결과를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="b98ae-139">Click in this box and start typing the name of users to display search results for.</span></span> <span data-ttu-id="b98ae-140">이 상자에서 선택한 사용자가 수행하는 선택한 활동에 대한 감사 로그 항목이 결과 목록에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b98ae-140">The audit log entries for the selected activities performed by the users you select in this box are displayed in the list of results.</span></span> <span data-ttu-id="b98ae-141">조직의 모든 사용자(및 서비스 계정)에 대한 항목을 반환하려면 이 상자를 비워 둡니다.</span><span class="sxs-lookup"><span data-stu-id="b98ae-141">Leave this box blank to return entries for all users (and service accounts) in your organization.</span></span>
  
   4. <span data-ttu-id="b98ae-142">**파일, 폴더 또는 사이트**.</span><span class="sxs-lookup"><span data-stu-id="b98ae-142">**File, folder, or site**.</span></span> <span data-ttu-id="b98ae-143">지정된 키워드가 포함된 폴더 파일과 관련된 활동을 검색하려면 파일 또는 폴더 이름의 일부 또는 전부를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b98ae-143">Type some or all of a file or folder name to search for activity related to the file of folder that contains the specified keyword.</span></span> <span data-ttu-id="b98ae-144">파일 또는 폴더의 URL을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b98ae-144">You can also specify a URL of a file or folder.</span></span> <span data-ttu-id="b98ae-145">파일 이나 폴더의 URL을 사용 하는 경우, 전체 URL 경로 형식 또는 URL의 일부를 입력 하는 경우 특별 한 문자 또는 공백을 포함 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="b98ae-145">If you use a URL of a file or folder, be sure the type the full URL path or if you type a portion of the URL, don't include any special characters or spaces.</span></span> <span data-ttu-id="b98ae-146">조직의 모든 파일 및 폴더에 대한 항목을 반환하려면 이 상자를 비워 둡니다.</span><span class="sxs-lookup"><span data-stu-id="b98ae-146">Leave this box blank to return entries for all files and folders in your organization.</span></span>

4. <span data-ttu-id="b98ae-147">**검색을** 클릭하여 검색을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b98ae-147">Click **Search** to run the search.</span></span>

<span data-ttu-id="b98ae-148">감사 로그 검색이 실행 중임을 보여주는 새 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b98ae-148">A new page is display that shows the audit log search is running.</span></span> <span data-ttu-id="b98ae-149">검색이 완료되면 감사 레코드가 페이지에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b98ae-149">When the search is completed, audit records are displayed on the page.</span></span> <span data-ttu-id="b98ae-150">레코드를 클릭하여 자세한 속성이 있는 플라이아웃 페이지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="b98ae-150">Click a record to display a flyout page with detailed properties.</span></span>

<span data-ttu-id="b98ae-151">자세한 지침은 규정 [준수 센터에서 감사 로그 검색을](search-the-audit-log-in-security-and-compliance.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b98ae-151">For more detailed instructions, see [Search the audit log in the compliance center](search-the-audit-log-in-security-and-compliance.md).</span></span>
