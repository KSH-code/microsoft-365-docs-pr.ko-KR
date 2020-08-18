---
title: 고객 Lockbox 요청
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
search.appverid:
- BCS160
- MET150
- MOE150
description: 문제가 발생 하는 경우 Microsoft 지원 엔지니어가 데이터에 액세스 하는 방법을 제어할 수 있도록 하는 고객 Lockbox 요청에 대해 알아봅니다.
ms.openlocfilehash: 67662c34ed3aedb22c3462a2ba8aff9e338e07c6
ms.sourcegitcommit: 234726a1795d984c4659da68f852d30a4dda5711
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/18/2020
ms.locfileid: "46794257"
---
# <a name="customer-lockbox-in-office-365"></a><span data-ttu-id="ad0ef-103">Office 365의 고객 Lockbox</span><span class="sxs-lookup"><span data-stu-id="ad0ef-103">Customer Lockbox in Office 365</span></span>

<span data-ttu-id="ad0ef-104">이 문서에서는 고객 Lockbox에 대 한 배포 및 구성 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-104">This article provides deployment and configuration guidance for Customer Lockbox.</span></span> <span data-ttu-id="ad0ef-105">고객 Lockbox는 Exchange Online, SharePoint Online 및 비즈니스용 OneDrive의 데이터에 액세스 하기 위한 요청을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-105">Customer Lockbox supports requests to access data in Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="ad0ef-106">다른 서비스에 대 한 지원을 권장 하려면 [Office 365 UserVoice](https://office365.uservoice.com/)에서 요청을 제출 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-106">To recommend support for other services, please submit a request at [Office 365 UserVoice](https://office365.uservoice.com/).</span></span>

<span data-ttu-id="ad0ef-107">사용자에 게 라이선스를 부여 하는 데 사용할 수 있는 옵션을 보려면이 항목을 포함 하 여 Microsoft 365 준수 서비스를 제공 하는 경우 (2020), [보안 & 준수에 대 한 microsoft 365 라이선스 지침](https://aka.ms/ComplianceSD)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-107">To see the options for licensing your users to benefit from Microsoft 365 compliance offerings, including this one, as of April 1, 2020, see the [Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).</span></span>

<span data-ttu-id="ad0ef-108">고객 Lockbox는 명시적인 승인 없이 서비스 작업을 수행 하기 위해 Microsoft가 콘텐츠에 액세스할 수 없도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-108">Customer Lockbox ensures that Microsoft cannot access your content to perform a service operation without your explicit approval.</span></span> <span data-ttu-id="ad0ef-109">고객 Lockbox는 콘텐츠에 액세스 하기 위한 요청에 대 한 승인 워크플로를 사용자에 게 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-109">Customer Lockbox brings you into the approval workflow for requests to access your content.</span></span>

<span data-ttu-id="ad0ef-110">경우에 따라 Microsoft 엔지니어가 지원 프로세스에서 고객이 보고 한 문제를 해결 하 고 문제를 해결 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-110">Occasionally, Microsoft engineers help troubleshoot and fix customer reported issues in the support process.</span></span> <span data-ttu-id="ad0ef-111">일반적으로 문제는 Microsoft가 서비스를 위해 마련 된 광범위 한 원격 분석 및 디버깅 도구를 통해 수정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-111">Usually, issues are fixed through extensive telemetry and debugging tools Microsoft has in place for its services.</span></span> <span data-ttu-id="ad0ef-112">그러나 근본적인 원인을 확인 하 고 문제를 해결 하기 위해 고객 콘텐츠에 액세스 하기 위해 Microsoft 엔지니어가 필요한 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-112">However, some cases require a Microsoft engineer to access customer content to determine the root cause and fix the issue.</span></span> <span data-ttu-id="ad0ef-113">고객 Lockbox에 게는 승인 워크플로의 최종 단계로 고객의 액세스를 요청 하는 엔지니어가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-113">Customer Lockbox requires the engineer to request access from the customer as a final step in the approval workflow.</span></span> <span data-ttu-id="ad0ef-114">조직에서는 이러한 요청을 승인 하거나 거부할 수 있는 옵션을 제공 하 고 고객에 게 직접 액세스 제어 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-114">This gives organizations the option to approve or deny these requests, and provide direct-access control to the customer.</span></span>

### <a name="customer-lockbox-overview-video"></a><span data-ttu-id="ad0ef-115">고객 Lockbox 개요 비디오</span><span class="sxs-lookup"><span data-stu-id="ad0ef-115">Customer Lockbox overview video</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/8fecf10b-1f03-4849-8b67-76d3d2a43f26?autoplay=false]

## <a name="customer-lockbox-workflow"></a><span data-ttu-id="ad0ef-116">고객 Lockbox 워크플로</span><span class="sxs-lookup"><span data-stu-id="ad0ef-116">Customer Lockbox workflow</span></span>

<span data-ttu-id="ad0ef-117">다음 단계에서는 Microsoft 엔지니어가 고객 Lockbox 요청을 시작할 때의 일반적인 워크플로를 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-117">The following steps outline the typical workflow when a Microsoft engineer initiates a Customer Lockbox request:</span></span>

1. <span data-ttu-id="ad0ef-118">조직의 누군가가 Microsoft 365 사서함에 문제가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-118">Someone at an organization experiences an issue with their Microsoft 365 mailbox.</span></span>

2. <span data-ttu-id="ad0ef-119">사용자가 문제를 해결 했지만 수정할 수 없는 경우 Microsoft 지원 서비스를 통해 지원 요청을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-119">After the user troubleshoots the issue, but can't fix it, they open a support request with Microsoft Support.</span></span>

3. <span data-ttu-id="ad0ef-120">Microsoft 지원 엔지니어가 서비스 요청을 검토 하 고 Exchange Online에서 문제를 해결 하기 위해 조직의 테 넌 트에 액세스 해야 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-120">A Microsoft support engineer reviews the service request and determines a need to access the organization's tenant to repair the issue in Exchange Online.</span></span>

4. <span data-ttu-id="ad0ef-121">Microsoft 지원 엔지니어가 고객 Lockbox 요청 도구에 로그인 하 고 조직의 테 넌 트 이름, 서비스 요청 번호 및 엔지니어가 데이터에 액세스 하는 데 필요한 예상 시간을 포함 하는 데이터 액세스 요청을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-121">The Microsoft support engineer logs into the Customer Lockbox request tool and makes a data access request that includes the organization's tenant name, service request number, and the estimated time the engineer needs access to the data.</span></span>

5. <span data-ttu-id="ad0ef-122">Microsoft 지원 관리자가 요청을 승인 하면 고객 Lockbox가 조직의 지정 된 승인자에 게 Microsoft의 보류 중인 액세스 요청에 대 한 전자 메일 알림을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-122">After a Microsoft Support manager approves the request, Customer Lockbox sends the designated approver at the organization an email notification about the pending access request from Microsoft.</span></span>

    ![고객 Lockbox 전자 메일 알림의 예](../media/CustomerLockbox1.png)

   <span data-ttu-id="ad0ef-124">Microsoft 365 관리 센터에서 [고객 lockbox 액세스 승인자](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) 관리자 역할이 할당 된 모든 사용자는 고객 lockbox 요청을 승인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-124">Anyone who is assigned the [Customer Lockbox access approver](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) admin role in Microsoft 365 admin center can approve Customer Lockbox requests.</span></span>

6. <span data-ttu-id="ad0ef-125">승인자가 Microsoft 365 관리 센터에 로그인 하 고 요청을 승인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-125">The approver signs in to the Microsoft 365 admin center and approves the request.</span></span> <span data-ttu-id="ad0ef-126">이 단계에서는 감사 로그를 검색 하 여 사용할 수 있는 감사 레코드 만들기를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-126">This step triggers the creation of an audit record available by searching the audit log.</span></span> <span data-ttu-id="ad0ef-127">자세한 내용은 [고객 Lockbox 요청 감사](#auditing-customer-lockbox-requests)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-127">For more information, see [Auditing Customer Lockbox requests](#auditing-customer-lockbox-requests).</span></span>

   <span data-ttu-id="ad0ef-128">고객이 요청을 거부 하거나 12 시간 내에 요청을 승인 하지 않으면 요청이 만료 되 고 Microsoft 엔지니어에 게 액세스 권한이 부여 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-128">If the customer rejects the request or doesn't approve the request within 12 hours, the request expires and no access is granted to the Microsoft engineer.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="ad0ef-129">Microsoft는 Office 365에 로그인 해야 하는 고객 Lockbox 전자 메일 알림의 링크를 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-129">Microsoft does not include any links in Customer Lockbox email notifications requiring you to sign in to Office 365.</span></span>

7. <span data-ttu-id="ad0ef-130">조직의 승인자가 요청을 승인한 후에는 Microsoft 엔지니어가 승인 메시지를 수신 하 여 Exchange Online의 테 넌 트에 로그인 하 고 고객의 문제를 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-130">After the approver from the organization approves the request, the Microsoft engineer receives the approval message, logs into the tenant in Exchange Online, and fixes the customer's issue.</span></span> <span data-ttu-id="ad0ef-131">Microsoft 엔지니어가 문제를 해결 하기 위해 요청 된 기간이 지나면 액세스 권한이 자동으로 해지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-131">Microsoft engineers have the requested duration to fix the issue after which the access is automatically revoked.</span></span>

> [!NOTE]
> <span data-ttu-id="ad0ef-132">Microsoft 엔지니어가 수행한 모든 작업이 감사 로그에 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-132">All actions performed by a Microsoft engineer are logged in the audit log.</span></span> <span data-ttu-id="ad0ef-133">이러한 감사 레코드를 검색 하 고 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-133">You can search for and review these audit records.</span></span>

## <a name="turn-customer-lockbox-requests-on-or-off"></a><span data-ttu-id="ad0ef-134">고객 Lockbox 요청 설정 또는 해제</span><span class="sxs-lookup"><span data-stu-id="ad0ef-134">Turn Customer Lockbox requests on or off</span></span>

<span data-ttu-id="ad0ef-135">Microsoft 365 관리 센터에서 고객 Lockbox 컨트롤을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-135">You can turn on Customer Lockbox controls in the Microsoft 365 admin center.</span></span> <span data-ttu-id="ad0ef-136">고객 Lockbox를 켜면 Microsoft에서 테 넌 트의 콘텐츠를 액세스 하기 전에 조직의 승인을 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-136">When you turn on Customer Lockbox, Microsoft must obtain your organization's approval before accessing any of your tenant's content.</span></span>

1. <span data-ttu-id="ad0ef-137">전역 관리자 또는 **사용자 Lockbox 액세스 승인자** 역할이 할당 된 회사 또는 학교 계정을 사용 하 여로 이동 하 여 [https://admin.microsoft.com](https://admin.microsoft.com) 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-137">Using a work or school account that has either the global administrator or the **Customer Lockbox access approver** role assigned, go to [https://admin.microsoft.com](https://admin.microsoft.com) and sign in.</span></span>

2. <span data-ttu-id="ad0ef-138">**설정 > 조직 설정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-138">Choose **Settings > Org Settings**.</span></span>

3. <span data-ttu-id="ad0ef-139">**서비스**  >  **사용자 Lockbox**  >  **편집**을 선택한 다음 토글을 설정 또는 해제 **로** 이동 **Off** 하 여 기능을 설정 하거나 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-139">Select **Services** > **Customer Lockbox** > **Edit**, and then move the toggle to **On** or **Off** to turn the feature on or off.</span></span>

    ![Require approval for Customer Lockbox](../media/CustomerLockbox4.png)

## <a name="approve-or-deny-a-customer-lockbox-request"></a><span data-ttu-id="ad0ef-141">고객 Lockbox 요청 승인 또는 거부</span><span class="sxs-lookup"><span data-stu-id="ad0ef-141">Approve or deny a Customer Lockbox request</span></span>

1. <span data-ttu-id="ad0ef-142">전역 관리자 또는 **사용자 Lockbox 액세스 승인자** 역할이 할당 된 회사 또는 학교 계정을 사용 하 여로 이동 하 여 [https://admin.microsoft.com](https://admin.microsoft.com) 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-142">Using a work or school account that has either the global administrator or the **Customer Lockbox access approver** role assigned, go to [https://admin.microsoft.com](https://admin.microsoft.com) and sign in.</span></span>

2. <span data-ttu-id="ad0ef-143">**고객 Lockbox 요청 > 지원을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-143">Choose **Support > Customer Lockbox Requests**.</span></span>

    ![지원을 클릭 하 고 고객 Lockbox 요청을 클릭 합니다.](../media/CustomerLockbox5.png)

    <span data-ttu-id="ad0ef-145">고객 Lockbox 요청 목록이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-145">A list of Customer Lockbox requests displays.</span></span>

    ![고객 Lockbox 요청 목록](../media/CustomerLockbox6.png)

3. <span data-ttu-id="ad0ef-147">고객 Lockbox 요청을 선택한 다음 **승인** 또는 **거부**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-147">Select a Customer Lockbox request, and then choose **Approve** or **Deny**.</span></span>

    ![고객 Lockbox 요청 승인 또는 거부](../media/CustomerLockbox7.png)

    <span data-ttu-id="ad0ef-149">고객 Lockbox 요청의 승인에 대 한 확인 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-149">A confirmation message about the approval of the Customer Lockbox request displays.</span></span>

    ![고객 Lockbox 요청 승인 또는 거부](../media/CustomerLockbox8.png)

> [!NOTE]
> <span data-ttu-id="ad0ef-151">AccessToCustomerDataRequest cmdlet을 사용 하 여 Microsoft 지원 엔지니어가 데이터에 대 한 액세스를 제어 하는 Microsoft 365 고객 lockbox 요청을 승인, 거부 또는 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-151">Use the Set-AccessToCustomerDataRequest cmdlet to approve, deny, or cancel Microsoft 365 customer lockbox requests that control access to your data by Microsoft support engineers.</span></span> <span data-ttu-id="ad0ef-152">자세한 내용은 [AccessToCustomerDataRequest](https://docs.microsoft.com/powershell/module/exchange/set-accesstocustomerdatarequest?view=exchange-ps)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-152">For more information, see [Set-AccessToCustomerDataRequest](https://docs.microsoft.com/powershell/module/exchange/set-accesstocustomerdatarequest?view=exchange-ps).</span></span>


## <a name="auditing-customer-lockbox-requests"></a><span data-ttu-id="ad0ef-153">고객 Lockbox 요청 감사</span><span class="sxs-lookup"><span data-stu-id="ad0ef-153">Auditing Customer Lockbox requests</span></span>

<span data-ttu-id="ad0ef-154">고객 Lockbox 요청에 해당 하는 감사 레코드가 감사 로그에 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-154">Audit records that correspond to the Customer Lockbox requests are logged in the audit log.</span></span> <span data-ttu-id="ad0ef-155">보안 & 준수 센터에서 [감사 로그 검색 도구](search-the-audit-log-in-security-and-compliance.md) 를 사용 하 여 이러한 로그에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-155">You can access these logs by using the [audit log search tool](search-the-audit-log-in-security-and-compliance.md) in the Security & Compliance Center.</span></span> <span data-ttu-id="ad0ef-156">고객 Lockbox 요청 수락 또는 거부와 관련 된 작업 및 Microsoft 엔지니어가 수행한 작업 (액세스 요청이 승인 된 경우)이 감사 로그에도 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-156">Actions related to a accepting or denying a Customer Lockbox request and actions performed by Microsoft engineers (when access requests are approved) are also logged in the audit log.</span></span> <span data-ttu-id="ad0ef-157">이러한 감사 레코드를 검색 하 고 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-157">You can search for and review these audit records.</span></span>

### <a name="search-the-audit-log-for-activity-related-to-customer-lockbox-requests"></a><span data-ttu-id="ad0ef-158">고객 Lockbox 요청과 관련 된 작업에 대 한 감사 로그 검색</span><span class="sxs-lookup"><span data-stu-id="ad0ef-158">Search the audit log for activity related to Customer Lockbox requests</span></span>

<span data-ttu-id="ad0ef-159">감사 로그를 사용 하 여 고객 Lockbox에 대 한 요청을 추적할 수 있으므로 감사 로깅을 설정 하기 위해 몇 가지 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-159">Before you can use the audit log to track requests for Customer Lockbox, there are some steps you need to take to to set up audit logging.</span></span> <span data-ttu-id="ad0ef-160">자세한 내용은 [Security & 준수 센터에서 감사 로그 검색](https://docs.microsoft.com/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#before-you-begin)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-160">For more information, see [Search the audit log in the Security & Compliance Center](https://docs.microsoft.com/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#before-you-begin).</span></span> <span data-ttu-id="ad0ef-161">설치를 완료 한 후 다음 단계를 사용 하 여 고객 Lockbox와 관련 된 감사 레코드를 반환 하는 감사 로그 검색 쿼리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-161">Once you've completed setup, use these steps to create an audit log search query to return audit records related to Customer Lockbox:</span></span>

1. <span data-ttu-id="ad0ef-162">[https://protection.office.com](https://protection.office.com)으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-162">Go to [https://protection.office.com](https://protection.office.com).</span></span>
  
2. <span data-ttu-id="ad0ef-163">회사 또는 학교 계정을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-163">Sign in using your work or school account.</span></span>

3. <span data-ttu-id="ad0ef-164">보안 & 준수 센터의 왼쪽 창에서 **검색 & 조사**  >  **감사 로그 검색**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-164">In the left pane of the Security & Compliance Center, choose **Search & investigation** > **Audit log search**.</span></span>

    <span data-ttu-id="ad0ef-165">**감사 로그 검색** 페이지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-165">The **Audit log search** page displays.</span></span>

    ![감사 로그 검색 페이지](../media/auditlogsearch1.png)
  
4. <span data-ttu-id="ad0ef-167">다음과 같은 검색 조건을 구성합니다. </span><span class="sxs-lookup"><span data-stu-id="ad0ef-167">Configure the following search criteria:</span></span>

    <span data-ttu-id="ad0ef-168">a.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-168">a.</span></span> <span data-ttu-id="ad0ef-169">**활동** -검색에서 모든 활동에 대 한 감사 레코드를 반환 하도록이 필드를 비워 둡니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-169">**Activities** - Leave this field blank so that the search returns audit records for all activities.</span></span> <span data-ttu-id="ad0ef-170">이는 고객 Lockbox 요청과 관련 된 감사 레코드와 Microsoft 엔지니어가 수행한 해당 작업을 반환 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-170">This is necessary to return any audit records related to Customer Lockbox requests and corresponding activity performed by Microsoft engineers.</span></span>

    <span data-ttu-id="ad0ef-171">b.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-171">b.</span></span> <span data-ttu-id="ad0ef-172">**시작 날짜** 및 **종료 날짜** -해당 기간 내에 발생 한 이벤트를 표시 하려면 날짜 및 시간 범위를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-172">**Start date** and **End date** - Select a date and time range to display the events that occurred within that period.</span></span>

    <span data-ttu-id="ad0ef-173">c.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-173">c.</span></span> <span data-ttu-id="ad0ef-174">**사용자** -이 필드를 비워 둡니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-174">**Users** - Leave this field blank.</span></span>

    <span data-ttu-id="ad0ef-175">d.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-175">d.</span></span> <span data-ttu-id="ad0ef-176">**파일, 폴더 또는 사이트** -이 필드를 비워 둡니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-176">**File, folder, or site** - Leave this field blank.</span></span>

5. <span data-ttu-id="ad0ef-177">**검색**을 클릭하여 검색 조건을 사용한 검색을 실행합니다. </span><span class="sxs-lookup"><span data-stu-id="ad0ef-177">Click **Search** to run the search using your search criteria.</span></span>

    <span data-ttu-id="ad0ef-178">검색 결과가 로드 되 고 몇 분 후에 **감사 로그 검색** 페이지의 **결과** 아래에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-178">The search results are loaded, and after a few moments they are displayed under **Results** on the **Audit log search** page.</span></span>

6. <span data-ttu-id="ad0ef-179">검색 결과 페이지에서 **결과 필터링** 을 클릭 하 고 다음 작업 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-179">Click **Filter results** on the search results page, and do one of the following things:</span></span>

   - <span data-ttu-id="ad0ef-180">조직의 승인자와 관련 된 감사 레코드를 표시 하려면 다음을 수행 합니다. **활동** 열 아래의 상자에 **AccessToCustomerDataRequest**을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-180">To display audit records related to an approver in your organization approving or denying a Customer Lockbox request: In the box under the **Activity** column, type **Set-AccessToCustomerDataRequest**.</span></span>

   - <span data-ttu-id="ad0ef-181">승인 된 고객 Lockbox 요청에 대 한 응답으로 Microsoft 엔지니어의 작업을 수행 하는 데 관련 된 감사 레코드를 표시 하려면 **사용자** 열 아래의 상자에 **microsoft Operator**를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-181">To display audit records related to a Microsoft engineer performing actions in response to an approved Customer Lockbox request: In the box under the **User** column, type **Microsoft Operator**.</span></span> <span data-ttu-id="ad0ef-182">**활동** 열에는 엔지니어가 수행한 작업이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-182">The **Activity** column displays the action performed by the engineer.</span></span>

      ![감사 레코드를 표시 하는 "Microsoft 운영자"에 대 한 필터링](../media/CustomerLockbox10.png)

7. <span data-ttu-id="ad0ef-184">결과 목록에서 감사 레코드를 클릭 하 여 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-184">In the list of results, click an audit record to display it.</span></span>

### <a name="audit-record-for-a-customer-lockbox-access-request"></a><span data-ttu-id="ad0ef-185">고객 Lockbox 액세스 요청에 대 한 감사 레코드</span><span class="sxs-lookup"><span data-stu-id="ad0ef-185">Audit record for a Customer Lockbox access request</span></span>

<span data-ttu-id="ad0ef-186">조직의 사용자가 고객 Lockbox 요청을 승인 하거나 거부 하는 경우 감사 레코드가 감사 로그에 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-186">When a person in your organization approves or denies a Customer Lockbox request, an audit record is logged in the audit log.</span></span> <span data-ttu-id="ad0ef-187">이 레코드에는 다음 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-187">This record contains the following information.</span></span>

| <span data-ttu-id="ad0ef-188">Audit record 속성</span><span class="sxs-lookup"><span data-stu-id="ad0ef-188">Audit record property</span></span>| <span data-ttu-id="ad0ef-189">설명</span><span class="sxs-lookup"><span data-stu-id="ad0ef-189">Description</span></span>|
|:---------- |:----------|
| <span data-ttu-id="ad0ef-190">날짜</span><span class="sxs-lookup"><span data-stu-id="ad0ef-190">Date</span></span>       | <span data-ttu-id="ad0ef-191">고객 인증 키 저장소 요청이 승인 또는 거부 된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-191">The date and time when the Customer Lockbox request was approved or denied.</span></span>
| <span data-ttu-id="ad0ef-192">IP 주소</span><span class="sxs-lookup"><span data-stu-id="ad0ef-192">IP address</span></span> | <span data-ttu-id="ad0ef-193">승인자가 요청을 승인 하거나 거부 하는 데 사용 하는 컴퓨터의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-193">The IP address of the machine the approver used to approve or deny a request.</span></span> |
| <span data-ttu-id="ad0ef-194">사용자</span><span class="sxs-lookup"><span data-stu-id="ad0ef-194">User</span></span>       | <span data-ttu-id="ad0ef-195">서비스 계정 BOXServiceAccount@ \[ \] customerforest.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-195">The service account BOXServiceAccount@\[customerforest\].prod.outlook.com.</span></span>            |
| <span data-ttu-id="ad0ef-196">활동</span><span class="sxs-lookup"><span data-stu-id="ad0ef-196">Activity</span></span>   | <span data-ttu-id="ad0ef-197">AccessToCustomerDataRequest; 이는 고객 Lockbox 요청을 승인 하거나 거부할 때 기록 되는 감사 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-197">Set-AccessToCustomerDataRequest; this is the auditing activity that is logged when you approve or deny a Customer Lockbox request.</span></span>                                |
| <span data-ttu-id="ad0ef-198">항목</span><span class="sxs-lookup"><span data-stu-id="ad0ef-198">Item</span></span>       | <span data-ttu-id="ad0ef-199">고객 Lockbox 요청의 Guid입니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-199">The Guid of the Customer Lockbox request</span></span>                             |

<span data-ttu-id="ad0ef-200">다음 스크린샷은 승인 된 고객 Lockbox 요청에 해당 하는 감사 로그 레코드의 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-200">The following screenshot shows an example of an audit log record that corresponds to an approved Customer Lockbox request.</span></span> <span data-ttu-id="ad0ef-201">고객 Lockbox 요청이 거부 된 경우 **Approvaldecision 결정** 매개 변수의 값은 **Deny**가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-201">If a Customer Lockbox request was denied, then the value of **ApprovalDecision** parameter would be **Deny**.</span></span>

![승인 된 고객 Lockbox 요청에 대 한 감사 레코드](../media/CustomerLockbox9.png)

> [!TIP]
> <span data-ttu-id="ad0ef-203">감사 레코드에 자세한 정보를 표시 하려면 **추가 정보**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-203">To display more detailed information in an audit record, click **More information**.</span></span>

### <a name="audit-record-for-an-action-performed-by-a-microsoft-engineer"></a><span data-ttu-id="ad0ef-204">Microsoft 엔지니어가 수행한 작업에 대 한 감사 레코드</span><span class="sxs-lookup"><span data-stu-id="ad0ef-204">Audit record for an action performed by a Microsoft engineer</span></span>

<span data-ttu-id="ad0ef-205">고객 Lockbox 요청이 승인 되 고 고객 콘텐츠에 액세스할 수 있도록 하는 Microsoft 엔지니어가 수행한 작업이 감사 로그에 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-205">The actions performed by a Microsoft engineer after a Customer Lockbox request is approved (and that may result in accessing customer content) are logged in the audit log.</span></span> <span data-ttu-id="ad0ef-206">이러한 레코드에는 다음과 같은 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-206">These records contain the following information.</span></span>

| <span data-ttu-id="ad0ef-207">Audit record 속성</span><span class="sxs-lookup"><span data-stu-id="ad0ef-207">Audit record property</span></span>| <span data-ttu-id="ad0ef-208">설명</span><span class="sxs-lookup"><span data-stu-id="ad0ef-208">Description</span></span>|
|:---------- |:----------|
| <span data-ttu-id="ad0ef-209">날짜</span><span class="sxs-lookup"><span data-stu-id="ad0ef-209">Date</span></span>       | <span data-ttu-id="ad0ef-210">작업을 수행한 날짜 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-210">Date time when the action was performed.</span></span> <span data-ttu-id="ad0ef-211">이 작업을 수행한 시간은 고객 Lockbox 요청이 승인 된 경우 4 시간 이내입니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-211">Note that the time that this action was performed will be within 4 hours of when the Customer Lockbox request was approved.</span></span>              |
| <span data-ttu-id="ad0ef-212">IP 주소</span><span class="sxs-lookup"><span data-stu-id="ad0ef-212">IP address</span></span> | <span data-ttu-id="ad0ef-213">Microsoft 엔지니어가 사용 하는 컴퓨터의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-213">The IP Address of the machine Microsoft engineer used.</span></span> |
| <span data-ttu-id="ad0ef-214">사용자</span><span class="sxs-lookup"><span data-stu-id="ad0ef-214">User</span></span>       | <span data-ttu-id="ad0ef-215">Microsoft Operator; 이 값은이 레코드가 고객 Lockbox 요청과 관련 되어 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-215">Microsoft Operator; this value indicates that this record is related to a Customer Lockbox request.</span></span>                                  |
| <span data-ttu-id="ad0ef-216">활동</span><span class="sxs-lookup"><span data-stu-id="ad0ef-216">Activity</span></span>   | <span data-ttu-id="ad0ef-217">Microsoft 엔지니어가 수행한 활동의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-217">Name of the activity performed by the Microsoft engineer.</span></span>|
| <span data-ttu-id="ad0ef-218">항목</span><span class="sxs-lookup"><span data-stu-id="ad0ef-218">Item</span></span>       | \<empty\>                                             |

## <a name="frequently-asked-questions"></a><span data-ttu-id="ad0ef-219">질문과 대답</span><span class="sxs-lookup"><span data-stu-id="ad0ef-219">Frequently asked questions</span></span>

#### <a name="which-microsoft-365-services-does-customer-lockbox-apply-to"></a><span data-ttu-id="ad0ef-220">고객 Lockbox가 적용 되는 Microsoft 365 서비스는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="ad0ef-220">Which Microsoft 365 services does Customer Lockbox apply to?</span></span>

<span data-ttu-id="ad0ef-221">고객 Lockbox는 현재 Exchange Online, SharePoint Online 및 비즈니스용 OneDrive에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-221">Customer Lockbox is currently supported in Exchange Online, SharePoint Online, and OneDrive for Business.</span></span>

#### <a name="is-customer-lockbox-available-to-all-customers"></a><span data-ttu-id="ad0ef-222">고객 Lockbox가 모든 고객에 게 제공 됩니까?</span><span class="sxs-lookup"><span data-stu-id="ad0ef-222">Is Customer Lockbox available to all customers?</span></span>

<span data-ttu-id="ad0ef-223">고객 Lockbox는 Microsoft 365 또는 Office 365 E5 구독에 포함 되어 있으며, 정보 보호 및 규정 준수 또는 고급 준수 추가 기능 구독을 사용 하 여 다른 계획에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-223">Customer Lockbox is included with the Microsoft 365 or Office 365 E5 subscriptions and can be added to other plans with an Information Protection and Compliance or an Advanced Compliance add-on subscription.</span></span> <span data-ttu-id="ad0ef-224">자세한 내용은 [요금제 및 가격 책정](https://products.office.com/business/office-365-enterprise-e5-business-software)를 참조 하세요   .</span><span class="sxs-lookup"><span data-stu-id="ad0ef-224">Please see [Plans and pricing](https://products.office.com/business/office-365-enterprise-e5-business-software) for more information.</span></span>

#### <a name="what-is-customer-content"></a><span data-ttu-id="ad0ef-225">고객 콘텐츠 란?</span><span class="sxs-lookup"><span data-stu-id="ad0ef-225">What is customer content?</span></span>

<span data-ttu-id="ad0ef-226">고객 콘텐츠는 Microsoft 365 서비스 및 응용 프로그램 사용자가 만든 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-226">Customer content is the data created by users of Microsoft 365 services and applications.</span></span> <span data-ttu-id="ad0ef-227">고객 콘텐츠의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-227">Examples of customer content include:</span></span>

- <span data-ttu-id="ad0ef-228">전자 메일 본문 또는 전자 메일 첨부 파일</span><span class="sxs-lookup"><span data-stu-id="ad0ef-228">Email body or email attachments</span></span>

- <span data-ttu-id="ad0ef-229">SharePoint 사이트 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="ad0ef-229">SharePoint site contents</span></span>

- <span data-ttu-id="ad0ef-230">SharePoint 파일의 본문에 있는 정보</span><span class="sxs-lookup"><span data-stu-id="ad0ef-230">Information in the body of a SharePoint file</span></span>

- <span data-ttu-id="ad0ef-231">비즈니스용 Skype 프레젠테이션 파일 본문</span><span class="sxs-lookup"><span data-stu-id="ad0ef-231">Skype for Business presentation file body</span></span>

- <span data-ttu-id="ad0ef-232">IM (인스턴트 메시지) 또는 음성 채팅</span><span class="sxs-lookup"><span data-stu-id="ad0ef-232">Instant messages (IM) or voice conversations</span></span>

- <span data-ttu-id="ad0ef-233">고객 생성 blob 또는 구조적 저장소 데이터 (예: SQL 컨테이너)</span><span class="sxs-lookup"><span data-stu-id="ad0ef-233">Customer-generated blob or structured storage data (for example, SQL Containers)</span></span>

- <span data-ttu-id="ad0ef-234">고객 소유 보안 정보 (예: 인증서, 암호화 키 및 암호)</span><span class="sxs-lookup"><span data-stu-id="ad0ef-234">Customer-owned security information (for example, certificates, encryption keys, and passwords)</span></span>

- <span data-ttu-id="ad0ef-235">Inferences 및 모든 후속 Inferences (고객 콘텐츠가 유지 되는 경우)</span><span class="sxs-lookup"><span data-stu-id="ad0ef-235">Inferences, and all subsequent inferences, if customer content remains</span></span>

<span data-ttu-id="ad0ef-236">Office 365의 고객 콘텐츠에 대 한 자세한 내용은 [office 365 보안 센터](https://products.office.com/business/office-365-trust-center-privacy/)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-236">For additional information about customer content in Office 365, see the [Office 365 Trust Center](https://products.office.com/business/office-365-trust-center-privacy/).</span></span>

#### <a name="who-is-notified-when-there-is-a-request-to-access-my-content"></a><span data-ttu-id="ad0ef-237">콘텐츠에 액세스 하는 요청이 있을 때 사용자에 게 알림을 받는 사람은 누구 인가요?</span><span class="sxs-lookup"><span data-stu-id="ad0ef-237">Who is notified when there is a request to access my content?</span></span>

<span data-ttu-id="ad0ef-238">전역 관리자 및 고객 Lockbox 액세스 승인자 관리자 역할에 할당 된 모든 사용자에 게 알림을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-238">Global administrators and anyone assigned the Customer Lockbox access approver admin role are notified.</span></span> <span data-ttu-id="ad0ef-239">또한 이러한 사용자는 고객 Lockbox 요청에 대해 승인할 수 있는 것과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-239">These are also the same users who can approve for Customer Lockbox requests.</span></span>

#### <a name="who-can-approve-or-reject-these-requests-in-my-organization"></a><span data-ttu-id="ad0ef-240">조직에서 이러한 요청을 승인 하거나 거부할 수 있는 사람은 누구 입니까?</span><span class="sxs-lookup"><span data-stu-id="ad0ef-240">Who can approve or reject these requests in my organization?</span></span>

<span data-ttu-id="ad0ef-241">전역 관리자 및 고객 Lockbox 액세스 승인자 관리자 역할이 할당 된 모든 사용자는 고객 Lockbox 요청을 승인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-241">Global administrators and anyone assigned the Customer Lockbox access approver admin role can approve Customer Lockbox requests.</span></span> <span data-ttu-id="ad0ef-242">고객은 조직에서 이러한 역할 할당을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-242">Customers control these role assignments in their organizations.</span></span>

#### <a name="how-do-i-opt-in-to-customer-lockbox"></a><span data-ttu-id="ad0ef-243">고객 Lockbox에 옵트인 하려면 어떻게 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="ad0ef-243">How do I opt in to Customer Lockbox?</span></span>

<span data-ttu-id="ad0ef-244">전역 관리자는 Microsoft 365 또는 Microsoft 365 관리 센터에서 고객 Lockbox를 사용 하도록 설정 하 고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-244">A global administrator can enable and configure Customer Lockbox in the Microsoft 365 or Microsoft 365 admin center.</span></span>

#### <a name="if-i-approve-a-customer-lockbox-request-what-can-the-engineer-do-and-how-will-i-know-what-the-microsoft-engineer-did"></a><span data-ttu-id="ad0ef-245">고객 Lockbox 요청을 승인 하는 경우 엔지니어가 수행할 수 있는 작업과 Microsoft 엔지니어가 수행한 작업을 확인 하는 방법</span><span class="sxs-lookup"><span data-stu-id="ad0ef-245">If I approve a Customer Lockbox request, what can the engineer do and how will I know what the Microsoft engineer did?</span></span>

<span data-ttu-id="ad0ef-246">고객 Lockbox 요청을 승인 하면 Microsoft 엔지니어가 사용자에 게 사전 승인 된 cmdlet을 사용 하 여 고객 콘텐츠에 액세스 하는 데 필요한 권한이 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-246">After you approve a Customer Lockbox request, the Microsoft engineer granted these necessary privileges to access customer content by using pre-approved cmdlets.</span></span> <span data-ttu-id="ad0ef-247">고객 Lockbox 요청에 대 한 응답으로 Microsoft 엔지니어가 수행한 작업이 기록 되 고 보안 & 준수 센터의 감사 로그에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-247">Actions taken by Microsoft engineers in response to Customer Lockbox requests are logged and accessible in the audit log in the Security & Compliance Center.</span></span>

#### <a name="how-do-i-know-that-microsoft-follows-the-approval-process"></a><span data-ttu-id="ad0ef-248">Microsoft가 승인 프로세스를 팔 로우 하는지 어떻게 알 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="ad0ef-248">How do I know that Microsoft follows the approval process?</span></span>

<span data-ttu-id="ad0ef-249">조직의 관리자 및 승인자에 게 전송 되는 전자 메일 승인 알림을 Microsoft 365 관리 센터에서 고객 Lockbox 요청 기록을 사용 하 여 상호 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-249">You can cross-reference the email approval notifications sent to admins and approvers in your organization with the Customer Lockbox request history in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="ad0ef-250">고객 Lockbox는 최신 [SOC 1 SSAE 16 감사 보고서](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports)에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-250">Customer Lockbox is included in the latest [SOC 1 SSAE 16 audit report](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports).</span></span> <span data-ttu-id="ad0ef-251">자세한 내용을 보려면 [Microsoft Service Trust Portal](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports)에서 최신 보고서를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-251">For more details, you can find the latest reports in the [Microsoft Service Trust Portal](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports).</span></span>

#### <a name="can-microsoft-modify-the-list-of-approvers-for-my-tenant-if-not-how-is-it-prevented"></a><span data-ttu-id="ad0ef-252">Microsoft에서 테 넌 트에 대 한 승인자 목록을 수정할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="ad0ef-252">Can Microsoft modify the list of approvers for my tenant?</span></span> <span data-ttu-id="ad0ef-253">그렇지 않은 경우에는 어떻게 차단 됩니까?</span><span class="sxs-lookup"><span data-stu-id="ad0ef-253">If not, how is it prevented?</span></span>

<span data-ttu-id="ad0ef-254">조직의 전역 관리자만 고객 Lockbox 요청을 승인할 수 있는 사람을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-254">Only a global administrator in your organization can specify who can approve Customer Lockbox requests.</span></span> <span data-ttu-id="ad0ef-255">즉, Azure Active Directory의 전역 관리자 그룹 구성원만 요청을 승인할 수 있는 사람을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-255">That means only the members of the Global administrator group in Azure Active Directory can specify who can approve request.</span></span> <span data-ttu-id="ad0ef-256">Azure Active Directory의 전역 관리자 그룹 구성원 자격은 조직에 의해서만 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-256">Membership of the Global administrator group in Azure Active Directory is managed only by your organization.</span></span>

#### <a name="what-if-i-need-more-information-about-a-content-access-request-to-approve-it"></a><span data-ttu-id="ad0ef-257">콘텐츠 액세스 요청에 대 한 자세한 정보를 승인 하려면 어떻게 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="ad0ef-257">What if I need more information about a content access request to approve it?</span></span>

<span data-ttu-id="ad0ef-258">각 고객 Lockbox 요청에는 Microsoft 365 서비스 요청 번호가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-258">Each Customer Lockbox request contains an Microsoft 365 service request number.</span></span> <span data-ttu-id="ad0ef-259">Microsoft 지원에 문의 하 여이 서비스 번호를 참조 하 여 요청에 대 한 자세한 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-259">You can contact Microsoft Support and reference this service number to get more information about the request.</span></span>

#### <a name="when-a-customer-lockbox-request-is-approved-how-long-are-the-permissions-valid"></a><span data-ttu-id="ad0ef-260">고객 Lockbox 요청이 승인 되 면 사용 권한이 유효한 기간이 얼마나 걸립니까?</span><span class="sxs-lookup"><span data-stu-id="ad0ef-260">When a Customer Lockbox request is approved, how long are the permissions valid?</span></span>

<span data-ttu-id="ad0ef-261">현재 Microsoft 엔지니어에 게 부여 되는 액세스 권한의 최대 기간은 4 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-261">Currently, the maximum period for the access permissions granted to the Microsoft engineer is 4 hours.</span></span> <span data-ttu-id="ad0ef-262">Microsoft 엔지니어가 더 짧은 기간을 요청할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-262">The Microsoft engineer can also request a shorter period.</span></span>

#### <a name="how-can-i-get-a-history-of-all-customer-lockbox-requests"></a><span data-ttu-id="ad0ef-263">모든 고객 Lockbox 요청의 기록을 어떻게 얻을 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="ad0ef-263">How can I get a history of all Customer Lockbox requests?</span></span>

<span data-ttu-id="ad0ef-264">모든 고객 Lockbox 요청이 Microsoft 365 관리 센터에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-264">All Customer Lockbox requests are viewed in the Microsoft 365 admin center.</span></span>

#### <a name="how-do-i-correlate-the-content-access-requests-with-the-related-audit-logs"></a><span data-ttu-id="ad0ef-265">콘텐츠 액세스 요청과 관련 된 감사 로그를 상호 연관 시키는 방법은 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="ad0ef-265">How do I correlate the content access requests with the related audit logs?</span></span>

<span data-ttu-id="ad0ef-266">준수 센터 작업 피드에는 고객 Lockbox의 로그 작업이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-266">The Compliance Center Activity Feed contains log activities of Customer Lockbox.</span></span> <span data-ttu-id="ad0ef-267">고객은 수신 된 전자 메일 요청에 대해 작업 피드에서 고객 Lockbox 로그 활동을 상호 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-267">Customers can cross-reference the Customer Lockbox log activities from the activity feed against the email request they receive.</span></span>

#### <a name="what-happens-when-a-customer-doesnt-respond-to-a-customer-lockbox-request"></a><span data-ttu-id="ad0ef-268">고객이 고객 Lockbox 요청에 응답 하지 않으면 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="ad0ef-268">What happens when a customer doesn't respond to a Customer Lockbox request?</span></span>

<span data-ttu-id="ad0ef-269">고객 Lockbox 요청의 기본 기간은 12 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-269">Customer Lockbox requests have a default duration of 12 hours.</span></span> <span data-ttu-id="ad0ef-270">12 시간 내에 요청에 응답 하지 않으면 요청이 만료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-270">If you don't respond to a request within 12 hour, the request expires.</span></span>

#### <a name="what-does-microsoft-do-when-a-customer-rejects-a-customer-lockbox-request"></a><span data-ttu-id="ad0ef-271">고객이 고객 Lockbox 요청을 거부 한 경우 Microsoft에서 수행 하는 작업은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="ad0ef-271">What does Microsoft do when a customer rejects a Customer Lockbox request?</span></span>

<span data-ttu-id="ad0ef-272">고객이 고객 Lockbox 요청을 거부 하면 고객 콘텐츠에 대 한 액세스 권한이 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-272">If a customer rejects a Customer Lockbox request, no access to customer content occurs.</span></span> <span data-ttu-id="ad0ef-273">조직의 사용자가 Microsoft에 문제를 해결 하기 위해 고객 콘텐츠에 액세스 하는 데 필요한 서비스 문제가 계속 발생 하면 서비스 문제가 지속 될 수 있으며 Microsoft는이에 대해 사용자에 게이를 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-273">If a user in your organization continues to experience a service issue requiring Microsoft to access customer content to resolve the issue, then the service issue might persist and Microsoft will inform the user about this.</span></span>

#### <a name="does-customer-lockbox-protect-against-data-requests-from-law-enforcement-agencies-or-other-third-parties"></a><span data-ttu-id="ad0ef-274">고객 Lockbox가 법률 집행 기관 또는 기타 타사 로부터의 데이터 요청을 보호 합니까?</span><span class="sxs-lookup"><span data-stu-id="ad0ef-274">Does Customer Lockbox protect against data requests from law enforcement agencies or other third parties?</span></span>

<span data-ttu-id="ad0ef-275">아니요.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-275">No.</span></span> <span data-ttu-id="ad0ef-276">Microsoft는 고객 데이터에 대 한 타사 요청을 심각 하 게 받아들입니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-276">Microsoft takes third-party requests for customer data seriously.</span></span> <span data-ttu-id="ad0ef-277">클라우드 서비스 공급자는 Microsoft는 항상 고객 데이터에 대 한 개인 정보를 대표 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-277">As a cloud service provider, Microsoft always advocates for the privacy of customer data.</span></span> <span data-ttu-id="ad0ef-278">소환장가 발생 하는 경우 Microsoft는 항상 제 3 자를 고객에 게 리디렉션하여 정보를 취득 하려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-278">In the event we get a subpoena, Microsoft always attempts to redirect the third party to the customer to obtain the information.</span></span> <span data-ttu-id="ad0ef-279">(Brad Smith의 블로그, 즉 [정부 스누핑에서 고객 데이터를 보호](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/)합니다.)</span><span class="sxs-lookup"><span data-stu-id="ad0ef-279">(Read Brad Smith's blog: [Protecting customer data from government snooping](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/)).</span></span> <span data-ttu-id="ad0ef-280">Microsoft가 받는 법 집행 요청에 대 한 [자세한 정보](https://www.microsoft.com/corporate-responsibility/lerr) 를 주기적으로 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-280">We periodically publish [detailed information](https://www.microsoft.com/corporate-responsibility/lerr) about the law enforcement requests that Microsoft receives.</span></span>

<span data-ttu-id="ad0ef-281">자세한 내용은 타사 데이터 요청과 관련 된 [Microsoft 보안 센터](https://www.microsoft.com/trustcenter/default.aspx) 및 [온라인 서비스 약관](https://www.microsoft.com/Licensing/product-licensing/products.aspx) 의 "고객 데이터 공개" 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-281">See the [Microsoft Trust Center](https://www.microsoft.com/trustcenter/default.aspx) regarding third-party data requests and the "Disclosure of Customer Data" section in the [Online Services Terms](https://www.microsoft.com/Licensing/product-licensing/products.aspx) for more information.</span></span>

#### <a name="how-does-microsoft-ensure-that-a-member-of-its-staff-doesnt-have-standing-access-to-customer-content-in-office-365-applications"></a><span data-ttu-id="ad0ef-282">Microsoft는 직원 구성원이 Office 365 응용 프로그램의 고객 콘텐츠에 대 한 액세스 권한을 보유 하 고 있는지 어떻게 확인 하나요?</span><span class="sxs-lookup"><span data-stu-id="ad0ef-282">How does Microsoft ensure that a member of its staff doesn't have standing access to customer content in Office 365 applications?</span></span>

<span data-ttu-id="ad0ef-283">Microsoft는 액세스 제어 시스템을 통해 광범위 한 예방 조치를 구현 하며, 이러한 액세스 제어 시스템을 회피 하기 위한 시도를 식별 하 고 해결 하기 위한 조치를 예방용 인지 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-283">Microsoft implements extensive preventive measures through access control systems, and detective measures to identify and address attempts to circumvent these access control systems.</span></span> <span data-ttu-id="ad0ef-284">Microsoft 365는 최소 권한 및 just-in-time 액세스 원칙을 사용 하 여 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-284">Microsoft 365 operates with the principles of least privilege and just-in-time access.</span></span> <span data-ttu-id="ad0ef-285">따라서 Microsoft 직원에 게는 계속 해 서 고객 콘텐츠에 액세스할 수 있는 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-285">Therefore, no Microsoft personnel have permission to access customer content on an ongoing basis.</span></span> <span data-ttu-id="ad0ef-286">권한이 부여 된 경우에는 제한 된 기간 동안만 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-286">If permission is granted, it is for a limited duration.</span></span> 

<span data-ttu-id="ad0ef-287">Microsoft 365에서는 *Lockbox* 라는 액세스 제어 시스템을 사용 하 여 서비스 내에서 작동 및 관리 기능을 수행할 수 있는 권한을 부여 하는 사용 권한에 대 한 요청을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-287">Microsoft 365 uses an access control system called *Lockbox* to process requests for permissions that grant the ability to perform operational and administrative functions within the service.</span></span> <span data-ttu-id="ad0ef-288">운영자는 Lockbox를 사용 하 여 고객 콘텐츠에 대 한 액세스를 요청 해야 하며, 따라서 액세스 권한을 부여 하기 전에 두 번째 사용자가 요청에 대해 작업을 수행 해야 합니다 (예: 승인).</span><span class="sxs-lookup"><span data-stu-id="ad0ef-288">An operator must request access to customer content using Lockbox, which then requires a second person to take action on the request (e.g., approve it) before access is granted.</span></span> <span data-ttu-id="ad0ef-289">두 번째 사용자는 요청자가 될 수 없으며 고객 콘텐츠에 대 한 액세스를 승인 하도록 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-289">That second person can't be the requestor and must be designated to approve access to customer content.</span></span> <span data-ttu-id="ad0ef-290">요청이 승인 된 경우에만 운영자가 고객 콘텐츠에 대 한 임시 액세스 권한을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-290">Only if the request is approved does the operator acquire temporary access to customer content.</span></span> <span data-ttu-id="ad0ef-291">권한 상승 기간이 만료 되 면 Lockbox가 액세스 권한을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-291">After the elevation period expires, Lockbox revokes access.</span></span>

<span data-ttu-id="ad0ef-292">Microsoft 일반 보안 관행에 대 한 자세한 내용은 [온라인 서비스 약관](https://www.microsoft.com/licensing/product-licensing/products) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-292">Please refer to the [Online Services Terms](https://www.microsoft.com/licensing/product-licensing/products) for more details about Microsoft general security practices.</span></span>

#### <a name="under-what-circumstances-do-microsoft-engineers-need-access-to-my-content"></a><span data-ttu-id="ad0ef-293">어떤 상황에서는 Microsoft 엔지니어가 내 콘텐츠에 액세스 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="ad0ef-293">Under what circumstances do Microsoft engineers need access to my content?</span></span>

<span data-ttu-id="ad0ef-294">Microsoft 엔지니어가 고객 콘텐츠에 액세스 해야 하는 가장 일반적인 시나리오는 고객이 문제 해결에 액세스 해야 하는 지원 요청을 만들 때입니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-294">The most common scenario where Microsoft engineers need access customer content is when the customer makes a support request requiring access for troubleshooting.</span></span> <span data-ttu-id="ad0ef-295">Microsoft 365의 기본 원칙은 Microsoft가 고객 콘텐츠에 대 한 액세스 권한 없이 서비스가 작동 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-295">A foundational principle of Microsoft 365 is that the service operates without Microsoft access to customer content.</span></span> <span data-ttu-id="ad0ef-296">Microsoft에서 수행 하는 거의 모든 서비스 작업은 완전히 자동화 되 고 고객의 콘텐츠를 벗어나 추상화 되 고 고도로 통제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-296">Nearly all service operations performed by Microsoft are fully automated and human involvement is highly controlled and abstracted away from customer content.</span></span> <span data-ttu-id="ad0ef-297">Microsoft 365의 목표는 고객이 Microsoft access에 대 한 특정 요청을 승인할 때까지 해당 서비스를 지원 하기 위한 고객 콘텐츠에 대 한 액세스 권한이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-297">The goal for Microsoft 365 is access to customer content to support the service isn't needed until the customer approves a specific request for Microsoft access.</span></span>

#### <a name="i-already-thought-my-data-was-secure-with-the-microsoft-cloud-so-why-do-i-need-customer-lockbox"></a><span data-ttu-id="ad0ef-298">Microsoft 클라우드를 사용 하 여 데이터가 안전 하다 고 생각 했을 때 고객 Lockbox가 필요한 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="ad0ef-298">I already thought my data was secure with the Microsoft cloud, so why do I need Customer Lockbox?</span></span>

<span data-ttu-id="ad0ef-299">고객 Lockbox는 서비스 작업에 대 한 명시적 액세스 권한 부여를 제공 하는 기능을 고객에 게 제공 하 여 추가 제어 계층을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-299">Customer Lockbox provides an extra layer of control by offering customers the ability to give explicit access authorization for service operations.</span></span> <span data-ttu-id="ad0ef-300">고객 Lockbox는 명시적인 데이터 액세스 권한 부여를 위한 절차를 제공 하 여 사용자가 HIPAA 및 FEDRAMP와 같은 특정 준수 의무를 충족 하도록 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0ef-300">By demonstrating that procedures are in place for explicit data access authorization, Customer Lockbox also helps customers meet certain compliance obligations such as HIPAA and FEDRAMP.</span></span>
