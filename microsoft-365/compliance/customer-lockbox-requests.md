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
description: 문제가 있는 경우 Microsoft 기술 지원 엔지니어가 데이터에 액세스할 수 있는 방법을 제어할 수 있는 고객 Lockbox 요청에 대해 자세히 알아보습니다.
ms.openlocfilehash: 6a6a1d45bfbc8b7c65d9ac8d58eb246643505c4f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922712"
---
# <a name="customer-lockbox-in-office-365"></a><span data-ttu-id="b6cb6-103">Office 365의 고객 Lockbox</span><span class="sxs-lookup"><span data-stu-id="b6cb6-103">Customer Lockbox in Office 365</span></span>

<span data-ttu-id="b6cb6-104">이 문서에서는 고객 Lockbox에 대한 배포 및 구성 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-104">This article provides deployment and configuration guidance for Customer Lockbox.</span></span> <span data-ttu-id="b6cb6-105">Customer Lockbox는 Exchange Online, SharePoint Online 및 비즈니스용 OneDrive의 데이터에 액세스하기 위한 요청을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-105">Customer Lockbox supports requests to access data in Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="b6cb6-106">다른 서비스에 대한 지원을 권장하기 위해 [Office 365 UserVoice 에서 요청을 제출하십시오.](https://office365.uservoice.com/)</span><span class="sxs-lookup"><span data-stu-id="b6cb6-106">To recommend support for other services, please submit a request at [Office 365 UserVoice](https://office365.uservoice.com/).</span></span>

<span data-ttu-id="b6cb6-107">2020년 4월 1일을 포함하여 Microsoft 365 규정 준수 제품을 통해 혜택을 받을 수 있도록 사용자에게 라이선스를 제공하는 옵션을 확인 내용은 보안 및 규정 준수에 대한 [Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)라이선스 & 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-107">To see the options for licensing your users to benefit from Microsoft 365 compliance offerings, including this one, as of April 1, 2020, see the [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

<span data-ttu-id="b6cb6-108">Customer Lockbox는 Microsoft가 명시적 승인 없이는 서비스 작업을 수행하기 위해 콘텐츠에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-108">Customer Lockbox ensures that Microsoft cannot access your content to perform a service operation without your explicit approval.</span></span> <span data-ttu-id="b6cb6-109">Customer Lockbox는 콘텐츠에 액세스하기 위한 요청에 대한 승인 워크플로를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-109">Customer Lockbox brings you into the approval workflow for requests to access your content.</span></span>

<span data-ttu-id="b6cb6-110">경우에 따라 Microsoft 엔지니어는 지원 프로세스에서 보고된 고객 문제를 해결하고 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-110">Occasionally, Microsoft engineers help troubleshoot and fix customer reported issues in the support process.</span></span> <span data-ttu-id="b6cb6-111">일반적으로 문제는 Microsoft가 서비스에 대해 준비한 광범위한 원격 분석 및 디버깅 도구를 통해 해결됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-111">Usually, issues are fixed through extensive telemetry and debugging tools Microsoft has in place for its services.</span></span> <span data-ttu-id="b6cb6-112">그러나 일부 경우에는 Microsoft 엔지니어가 고객 콘텐츠에 액세스하여 근본 원인을 파악하고 문제를 해결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-112">However, some cases require a Microsoft engineer to access customer content to determine the root cause and fix the issue.</span></span> <span data-ttu-id="b6cb6-113">고객 Lockbox를 사용하려면 엔지니어가 승인 워크플로의 최종 단계로 고객의 액세스를 요청해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-113">Customer Lockbox requires the engineer to request access from the customer as a final step in the approval workflow.</span></span> <span data-ttu-id="b6cb6-114">이렇게 하면 조직에서 이러한 요청을 승인하거나 거부하고 고객에게 직접 액세스 제어를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-114">This gives organizations the option to approve or deny these requests, and provide direct-access control to the customer.</span></span>

### <a name="customer-lockbox-overview-video"></a><span data-ttu-id="b6cb6-115">고객 Lockbox 개요 비디오</span><span class="sxs-lookup"><span data-stu-id="b6cb6-115">Customer Lockbox overview video</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/8fecf10b-1f03-4849-8b67-76d3d2a43f26?autoplay=false]

## <a name="customer-lockbox-workflow"></a><span data-ttu-id="b6cb6-116">고객 Lockbox 워크플로</span><span class="sxs-lookup"><span data-stu-id="b6cb6-116">Customer Lockbox workflow</span></span>

<span data-ttu-id="b6cb6-117">다음 단계에서는 Microsoft 엔지니어가 고객 Lockbox 요청을 시작할 때의 일반적인 워크플로에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-117">The following steps outline the typical workflow when a Microsoft engineer initiates a Customer Lockbox request:</span></span>

1. <span data-ttu-id="b6cb6-118">조직의 누군가가 Microsoft 365 사서함에 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-118">Someone at an organization experiences an issue with their Microsoft 365 mailbox.</span></span>

2. <span data-ttu-id="b6cb6-119">사용자가 문제를 해결하지만 해결할 수 없는 경우 Microsoft 지원 서비스에서 지원 요청을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-119">After the user troubleshoots the issue, but can't fix it, they open a support request with Microsoft Support.</span></span>

3. <span data-ttu-id="b6cb6-120">Microsoft 지원 엔지니어가 서비스 요청을 검토하고 Exchange Online에서 문제를 복구하기 위해 조직의 테넌트에 액세스해야 하는지 여부를 판단합니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-120">A Microsoft support engineer reviews the service request and determines a need to access the organization's tenant to repair the issue in Exchange Online.</span></span>

4. <span data-ttu-id="b6cb6-121">Microsoft 기술 지원 엔지니어는 고객 Lockbox 요청 도구에 로그인하고 조직의 테넌트 이름, 서비스 요청 번호 및 엔지니어가 데이터에 액세스해야 하는 예상 시간을 포함하는 데이터 액세스 요청을 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-121">The Microsoft support engineer logs into the Customer Lockbox request tool and makes a data access request that includes the organization's tenant name, service request number, and the estimated time the engineer needs access to the data.</span></span>

5. <span data-ttu-id="b6cb6-122">Microsoft 지원 관리자가 요청을 승인하면 Customer Lockbox는 조직에서 지정된 승인자에 대해 Microsoft의 보류 중인 액세스 요청에 대한 전자 메일 알림을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-122">After a Microsoft Support manager approves the request, Customer Lockbox sends the designated approver at the organization an email notification about the pending access request from Microsoft.</span></span>

    ![고객 Lockbox 전자 메일 알림의 예](../media/CustomerLockbox1.png)

   <span data-ttu-id="b6cb6-124">Microsoft 365 관리 센터에서 [고객 Lockbox](/office365/admin/add-users/about-admin-roles) 액세스 승인자 관리자 역할이 할당된 모든 사용자는 고객 Lockbox 요청을 승인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-124">Anyone who is assigned the [Customer Lockbox access approver](/office365/admin/add-users/about-admin-roles) admin role in Microsoft 365 admin center can approve Customer Lockbox requests.</span></span>

6. <span data-ttu-id="b6cb6-125">승인자가 Microsoft 365 관리 센터에 로그인하여 요청을 승인합니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-125">The approver signs in to the Microsoft 365 admin center and approves the request.</span></span> <span data-ttu-id="b6cb6-126">이 단계에서는 감사 로그를 검색하여 사용 가능한 감사 레코드 만들기를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-126">This step triggers the creation of an audit record available by searching the audit log.</span></span> <span data-ttu-id="b6cb6-127">자세한 내용은 고객 Lockbox 요청 [감사를 참조하세요.](#auditing-customer-lockbox-requests)</span><span class="sxs-lookup"><span data-stu-id="b6cb6-127">For more information, see [Auditing Customer Lockbox requests](#auditing-customer-lockbox-requests).</span></span>

   <span data-ttu-id="b6cb6-128">고객이 요청을 거부하거나 12시간 이내에 요청을 승인하지 않는 경우 요청이 만료되고 Microsoft 엔지니어에게 액세스 권한이 부여되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-128">If the customer rejects the request or doesn't approve the request within 12 hours, the request expires and no access is granted to the Microsoft engineer.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="b6cb6-129">Microsoft는 Office 365에 로그인해야 하는 고객 Lockbox 전자 메일 알림에 링크를 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-129">Microsoft does not include any links in Customer Lockbox email notifications requiring you to sign in to Office 365.</span></span>

7. <span data-ttu-id="b6cb6-130">조직의 승인자가 요청을 승인하면 Microsoft 엔지니어가 승인 메시지를 받고 Exchange Online의 테넌트에 로그인하고 고객의 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-130">After the approver from the organization approves the request, the Microsoft engineer receives the approval message, logs into the tenant in Exchange Online, and fixes the customer's issue.</span></span> <span data-ttu-id="b6cb6-131">Microsoft 엔지니어는 액세스가 자동으로 해지되는 문제를 해결하기 위해 요청된 기간을 가집니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-131">Microsoft engineers have the requested duration to fix the issue after which the access is automatically revoked.</span></span>

> [!NOTE]
> <span data-ttu-id="b6cb6-132">Microsoft 엔지니어가 수행한 모든 작업이 감사 로그에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-132">All actions performed by a Microsoft engineer are logged in the audit log.</span></span> <span data-ttu-id="b6cb6-133">이러한 감사 레코드를 검색하고 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-133">You can search for and review these audit records.</span></span>

## <a name="turn-customer-lockbox-requests-on-or-off"></a><span data-ttu-id="b6cb6-134">고객 Lockbox 요청 켜기 또는 끄기</span><span class="sxs-lookup"><span data-stu-id="b6cb6-134">Turn Customer Lockbox requests on or off</span></span>

<span data-ttu-id="b6cb6-135">Microsoft 365 관리 센터에서 고객 Lockbox 컨트롤을 켜면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-135">You can turn on Customer Lockbox controls in the Microsoft 365 admin center.</span></span> <span data-ttu-id="b6cb6-136">고객 Lockbox를 켜면 Microsoft는 테넌트의 콘텐츠에 액세스하기 전에 조직의 승인을 얻어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-136">When you turn on Customer Lockbox, Microsoft must obtain your organization's approval before accessing any of your tenant's content.</span></span>

1. <span data-ttu-id="b6cb6-137">전역 관리자 또는 **Customer Lockbox** 액세스 승인자 역할이 할당된 직장 또는 학교 계정을 사용하여 이동하여 [https://admin.microsoft.com](https://admin.microsoft.com) 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-137">Using a work or school account that has either the global administrator or the **Customer Lockbox access approver** role assigned, go to [https://admin.microsoft.com](https://admin.microsoft.com) and sign in.</span></span>

2. <span data-ttu-id="b6cb6-138">설정 **> 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b6cb6-138">Choose **Settings > Org Settings**.</span></span>

3. <span data-ttu-id="b6cb6-139">보안 **& 개인** 정보 보호 고객 Lockbox 편집 을 선택한 다음 토글을 켜기 또는 끄기로 이동하여 기능을  >    >  켜거나 끄습니다.  </span><span class="sxs-lookup"><span data-stu-id="b6cb6-139">Select **Security & Privacy** > **Customer Lockbox** > **Edit**, and then move the toggle to **On** or **Off** to turn the feature on or off.</span></span>

    ![Require approval for Customer Lockbox](../media/CustomerLockbox4.png)

## <a name="approve-or-deny-a-customer-lockbox-request"></a><span data-ttu-id="b6cb6-141">고객 Lockbox 요청 승인 또는 거부</span><span class="sxs-lookup"><span data-stu-id="b6cb6-141">Approve or deny a Customer Lockbox request</span></span>

1. <span data-ttu-id="b6cb6-142">전역 관리자 또는 **Customer Lockbox** 액세스 승인자 역할이 할당된 직장 또는 학교 계정을 사용하여 이동하여 [https://admin.microsoft.com](https://admin.microsoft.com) 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-142">Using a work or school account that has either the global administrator or the **Customer Lockbox access approver** role assigned, go to [https://admin.microsoft.com](https://admin.microsoft.com) and sign in.</span></span>

2. <span data-ttu-id="b6cb6-143">고객 **Lockbox > 지원 을 선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="b6cb6-143">Choose **Support > Customer Lockbox Requests**.</span></span>

    ![지원을 클릭한 다음 고객 Lockbox 요청을 클릭합니다.](../media/CustomerLockbox5.png)

    <span data-ttu-id="b6cb6-145">고객 Lockbox 요청 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-145">A list of Customer Lockbox requests displays.</span></span>

    ![고객 Lockbox 요청 목록](../media/CustomerLockbox6.png)

3. <span data-ttu-id="b6cb6-147">고객 Lockbox 요청을 선택한 다음 승인 **또는** **거부를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b6cb6-147">Select a Customer Lockbox request, and then choose **Approve** or **Deny**.</span></span>

    ![고객 Lockbox 요청 승인 또는 거부](../media/CustomerLockbox7.png)

    <span data-ttu-id="b6cb6-149">고객 Lockbox 요청 승인에 대한 확인 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-149">A confirmation message about the approval of the Customer Lockbox request displays.</span></span>

    ![고객 Lockbox 요청 승인 또는 거부](../media/CustomerLockbox8.png)

> [!NOTE]
> <span data-ttu-id="b6cb6-151">Set-AccessToCustomerDataRequest cmdlet을 사용하여 Microsoft 지원 엔지니어의 사용자 데이터에 대한 액세스를 제어하는 Microsoft 365 고객 lockbox를 승인, 거부 또는 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-151">Use the Set-AccessToCustomerDataRequest cmdlet to approve, deny, or cancel Microsoft 365 customer lockbox requests that control access to your data by Microsoft support engineers.</span></span> <span data-ttu-id="b6cb6-152">자세한 내용은 [Set-AccessToCustomerDataRequest를 참조하세요.](/powershell/module/exchange/set-accesstocustomerdatarequest)</span><span class="sxs-lookup"><span data-stu-id="b6cb6-152">For more information, see [Set-AccessToCustomerDataRequest](/powershell/module/exchange/set-accesstocustomerdatarequest).</span></span>


## <a name="auditing-customer-lockbox-requests"></a><span data-ttu-id="b6cb6-153">고객 Lockbox 요청 감사</span><span class="sxs-lookup"><span data-stu-id="b6cb6-153">Auditing Customer Lockbox requests</span></span>

<span data-ttu-id="b6cb6-154">고객 Lockbox 요청에 해당하는 감사 레코드가 감사 로그에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-154">Audit records that correspond to the Customer Lockbox requests are logged in the audit log.</span></span> <span data-ttu-id="b6cb6-155">보안 및 준수 센터의 [](search-the-audit-log-in-security-and-compliance.md) 감사 로그 검색 도구를 사용하여 이러한 & 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-155">You can access these logs by using the [audit log search tool](search-the-audit-log-in-security-and-compliance.md) in the Security & Compliance Center.</span></span> <span data-ttu-id="b6cb6-156">고객 Lockbox 요청 수락 또는 거부와 관련된 작업 및 Microsoft 엔지니어가 수행한 작업(액세스 요청이 승인된 경우)도 감사 로그에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-156">Actions related to accepting or denying a Customer Lockbox request and actions performed by Microsoft engineers (when access requests are approved) are also logged in the audit log.</span></span> <span data-ttu-id="b6cb6-157">이러한 감사 레코드를 검색하고 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-157">You can search for and review these audit records.</span></span>

### <a name="search-the-audit-log-for-activity-related-to-customer-lockbox-requests"></a><span data-ttu-id="b6cb6-158">감사 로그에서 고객 Lockbox 요청과 관련된 활동 검색</span><span class="sxs-lookup"><span data-stu-id="b6cb6-158">Search the audit log for activity related to Customer Lockbox requests</span></span>

<span data-ttu-id="b6cb6-159">감사 로그를 사용하여 Customer Lockbox에 대한 요청을 추적하려면 먼저 감사 로깅을 설정하기 위해 몇 가지 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-159">Before you can use the audit log to track requests for Customer Lockbox, there are some steps you need to take to set up audit logging.</span></span> <span data-ttu-id="b6cb6-160">자세한 내용은 보안 및 준수 [센터에서 감사 & 검색을 참조하세요.](/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#before-you-begin)</span><span class="sxs-lookup"><span data-stu-id="b6cb6-160">For more information, see [Search the audit log in the Security & Compliance Center](/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#before-you-begin).</span></span> <span data-ttu-id="b6cb6-161">설치를 완료한 후 다음 단계를 사용하여 고객 Lockbox와 관련된 감사 레코드를 반환하는 감사 로그 검색 쿼리를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-161">Once you've completed setup, use these steps to create an audit log search query to return audit records related to Customer Lockbox:</span></span>

1. <span data-ttu-id="b6cb6-162">[https://protection.office.com](https://protection.office.com)으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-162">Go to [https://protection.office.com](https://protection.office.com).</span></span>
  
2. <span data-ttu-id="b6cb6-163">회사 또는 학교 계정을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-163">Sign in using your work or school account.</span></span>

3. <span data-ttu-id="b6cb6-164">In the left pane of the Security & Compliance Center, choose **Search & investigation** Audit log  >  **search**.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-164">In the left pane of the Security & Compliance Center, choose **Search & investigation** > **Audit log search**.</span></span>

    <span data-ttu-id="b6cb6-165">감사 **로그 검색 페이지가** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-165">The **Audit log search** page displays.</span></span>

    ![감사 로그 검색 페이지](../media/auditlogsearch1.png)
  
4. <span data-ttu-id="b6cb6-167">다음과 같은 검색 조건을 구성합니다. </span><span class="sxs-lookup"><span data-stu-id="b6cb6-167">Configure the following search criteria:</span></span>

    1. <span data-ttu-id="b6cb6-168">**작업** - 검색에서 모든 활동에 대한 감사 레코드를 반환할 수 있도록 이 필드를 비워 두십시오.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-168">**Activities** - Leave this field blank so that the search returns audit records for all activities.</span></span> <span data-ttu-id="b6cb6-169">이는 고객 Lockbox 요청 및 Microsoft 엔지니어가 수행한 해당 활동과 관련된 모든 감사 레코드를 반환하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-169">This is necessary to return any audit records related to Customer Lockbox requests and corresponding activity performed by Microsoft engineers.</span></span>

    1. <span data-ttu-id="b6cb6-170">**시작 날짜** 및 **종료 날짜** - 날짜 및 시간 범위를 선택하여 해당 기간 내에 발생한 이벤트를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-170">**Start date** and **End date** - Select a date and time range to display the events that occurred within that period.</span></span>

    1. <span data-ttu-id="b6cb6-171">**사용자** - 이 필드를 비워 두십시오.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-171">**Users** - Leave this field blank.</span></span>

    1. <span data-ttu-id="b6cb6-172">**파일, 폴더 또는 사이트** - 이 필드를 비워 두십시오.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-172">**File, folder, or site** - Leave this field blank.</span></span>

5. <span data-ttu-id="b6cb6-173">**검색** 을 클릭하여 검색 조건을 사용한 검색을 실행합니다. </span><span class="sxs-lookup"><span data-stu-id="b6cb6-173">Click **Search** to run the search using your search criteria.</span></span>

    <span data-ttu-id="b6cb6-174">검색 결과가 로드되고 몇 분 후에 감사 로그  검색 페이지의 결과 아래에 **표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="b6cb6-174">The search results are loaded, and after a few moments they are displayed under **Results** on the **Audit log search** page.</span></span>

6. <span data-ttu-id="b6cb6-175">검색 **결과 페이지에서** 결과 필터링을 클릭하고 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-175">Click **Filter results** on the search results page, and do one of the following things:</span></span>

   - <span data-ttu-id="b6cb6-176">조직에서 고객 Lockbox 요청을 승인 또는 거부하는 승인자와 관련된 감사 레코드를 표시하기  위해 다음을 실행합니다. 활동 열 아래에 있는 상자에 **Set-AccessToCustomerDataRequest** 를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-176">To display audit records related to an approver in your organization approving or denying a Customer Lockbox request: In the box under the **Activity** column, type **Set-AccessToCustomerDataRequest**.</span></span>

   - <span data-ttu-id="b6cb6-177">승인된 Customer Lockbox 요청에 대한 응답으로 작업을 수행하는 Microsoft 엔지니어와 관련된 감사  레코드를 표시하기 위해: 사용자 열 아래에 있는 상자에 Microsoft 연산자 를 **입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="b6cb6-177">To display audit records related to a Microsoft engineer performing actions in response to an approved Customer Lockbox request: In the box under the **User** column, type **Microsoft Operator**.</span></span> <span data-ttu-id="b6cb6-178">작업 **열에는** 엔지니어가 수행한 작업이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-178">The **Activity** column displays the action performed by the engineer.</span></span>

      ![감사 레코드를 표시하기 위해 "Microsoft Operator"를 필터링합니다.](../media/CustomerLockbox10.png)

7. <span data-ttu-id="b6cb6-180">결과 목록에서 감사 레코드를 클릭하여 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-180">In the list of results, click an audit record to display it.</span></span>

### <a name="audit-record-for-a-customer-lockbox-access-request"></a><span data-ttu-id="b6cb6-181">고객 Lockbox 액세스 요청에 대한 감사 레코드</span><span class="sxs-lookup"><span data-stu-id="b6cb6-181">Audit record for a Customer Lockbox access request</span></span>

<span data-ttu-id="b6cb6-182">조직의 사용자가 고객 Lockbox 요청을 승인하거나 거부하면 감사 레코드가 감사 로그에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-182">When a person in your organization approves or denies a Customer Lockbox request, an audit record is logged in the audit log.</span></span> <span data-ttu-id="b6cb6-183">이 레코드에는 다음 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-183">This record contains the following information.</span></span>

| <span data-ttu-id="b6cb6-184">감사 레코드 속성</span><span class="sxs-lookup"><span data-stu-id="b6cb6-184">Audit record property</span></span>| <span data-ttu-id="b6cb6-185">설명</span><span class="sxs-lookup"><span data-stu-id="b6cb6-185">Description</span></span>|
|:---------- |:----------|
| <span data-ttu-id="b6cb6-186">날짜</span><span class="sxs-lookup"><span data-stu-id="b6cb6-186">Date</span></span>       | <span data-ttu-id="b6cb6-187">고객 Lockbox 요청이 승인 또는 거부된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-187">The date and time when the Customer Lockbox request was approved or denied.</span></span>
| <span data-ttu-id="b6cb6-188">IP 주소</span><span class="sxs-lookup"><span data-stu-id="b6cb6-188">IP address</span></span> | <span data-ttu-id="b6cb6-189">승인자가 요청을 승인하거나 거부하는 데 사용한 컴퓨터의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-189">The IP address of the machine the approver used to approve or deny a request.</span></span> |
| <span data-ttu-id="b6cb6-190">사용자</span><span class="sxs-lookup"><span data-stu-id="b6cb6-190">User</span></span>       | <span data-ttu-id="b6cb6-191">service account BOXServiceAccount@ \[ customerforest \] .prod.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-191">The service account BOXServiceAccount@\[customerforest\].prod.outlook.com.</span></span>            |
| <span data-ttu-id="b6cb6-192">활동</span><span class="sxs-lookup"><span data-stu-id="b6cb6-192">Activity</span></span>   | <span data-ttu-id="b6cb6-193">Set-AccessToCustomerDataRequest; 고객 Lockbox 요청을 승인하거나 거부할 때 기록되는 감사 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-193">Set-AccessToCustomerDataRequest; this is the auditing activity that is logged when you approve or deny a Customer Lockbox request.</span></span>                                |
| <span data-ttu-id="b6cb6-194">항목</span><span class="sxs-lookup"><span data-stu-id="b6cb6-194">Item</span></span>       | <span data-ttu-id="b6cb6-195">고객 Lockbox 요청의 Guid</span><span class="sxs-lookup"><span data-stu-id="b6cb6-195">The Guid of the Customer Lockbox request</span></span>                             |

<span data-ttu-id="b6cb6-196">다음 스크린샷은 승인된 Customer Lockbox 요청에 해당하는 감사 로그 레코드의 예를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-196">The following screenshot shows an example of an audit log record that corresponds to an approved Customer Lockbox request.</span></span> <span data-ttu-id="b6cb6-197">Customer Lockbox 요청이 거부된 경우 **ApprovalDecision** 매개 변수의 값은 **Deny가 됩니다.**</span><span class="sxs-lookup"><span data-stu-id="b6cb6-197">If a Customer Lockbox request was denied, then the value of **ApprovalDecision** parameter would be **Deny**.</span></span>

![승인된 고객 Lockbox 요청에 대한 감사 레코드](../media/CustomerLockbox9.png)

> [!TIP]
> <span data-ttu-id="b6cb6-199">감사 레코드에 자세한 정보를 표시하려면 추가 정보를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b6cb6-199">To display more detailed information in an audit record, click **More information**.</span></span>

### <a name="audit-record-for-an-action-performed-by-a-microsoft-engineer"></a><span data-ttu-id="b6cb6-200">Microsoft 엔지니어가 수행한 작업의 감사 레코드</span><span class="sxs-lookup"><span data-stu-id="b6cb6-200">Audit record for an action performed by a Microsoft engineer</span></span>

<span data-ttu-id="b6cb6-201">고객 Lockbox 요청이 승인된 후(그리고 고객 콘텐츠에 액세스하게 될 수 있는) Microsoft 엔지니어가 수행한 작업은 감사 로그에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-201">The actions performed by a Microsoft engineer after a Customer Lockbox request is approved (and that may result in accessing customer content) are logged in the audit log.</span></span> <span data-ttu-id="b6cb6-202">이러한 레코드에는 다음 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-202">These records contain the following information.</span></span>

| <span data-ttu-id="b6cb6-203">감사 레코드 속성</span><span class="sxs-lookup"><span data-stu-id="b6cb6-203">Audit record property</span></span>| <span data-ttu-id="b6cb6-204">설명</span><span class="sxs-lookup"><span data-stu-id="b6cb6-204">Description</span></span>|
|:---------- |:----------|
| <span data-ttu-id="b6cb6-205">날짜</span><span class="sxs-lookup"><span data-stu-id="b6cb6-205">Date</span></span>       | <span data-ttu-id="b6cb6-206">작업이 수행된 날짜 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-206">Date time when the action was performed.</span></span> <span data-ttu-id="b6cb6-207">이 작업이 수행된 시간은 고객 Lockbox 요청이 승인된 후 4시간 이내에 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-207">Note that the time that this action was performed will be within 4 hours of when the Customer Lockbox request was approved.</span></span>              |
| <span data-ttu-id="b6cb6-208">IP 주소</span><span class="sxs-lookup"><span data-stu-id="b6cb6-208">IP address</span></span> | <span data-ttu-id="b6cb6-209">Microsoft 엔지니어가 사용한 컴퓨터의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-209">The IP Address of the machine Microsoft engineer used.</span></span> |
| <span data-ttu-id="b6cb6-210">사용자</span><span class="sxs-lookup"><span data-stu-id="b6cb6-210">User</span></span>       | <span data-ttu-id="b6cb6-211">Microsoft 연산자 이 값은 이 레코드가 Customer Lockbox 요청과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-211">Microsoft Operator; this value indicates that this record is related to a Customer Lockbox request.</span></span>                                  |
| <span data-ttu-id="b6cb6-212">활동</span><span class="sxs-lookup"><span data-stu-id="b6cb6-212">Activity</span></span>   | <span data-ttu-id="b6cb6-213">Microsoft 엔지니어가 수행한 활동의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-213">Name of the activity performed by the Microsoft engineer.</span></span>|
| <span data-ttu-id="b6cb6-214">항목</span><span class="sxs-lookup"><span data-stu-id="b6cb6-214">Item</span></span>       | \<empty\>                                             |

## <a name="frequently-asked-questions"></a><span data-ttu-id="b6cb6-215">자주 묻는 질문</span><span class="sxs-lookup"><span data-stu-id="b6cb6-215">Frequently asked questions</span></span>

#### <a name="which-microsoft-365-services-does-customer-lockbox-apply-to"></a><span data-ttu-id="b6cb6-216">Customer Lockbox는 어떤 Microsoft 365 서비스에 적용하나요?</span><span class="sxs-lookup"><span data-stu-id="b6cb6-216">Which Microsoft 365 services does Customer Lockbox apply to?</span></span>

<span data-ttu-id="b6cb6-217">Customer Lockbox는 현재 Exchange Online, SharePoint Online 및 비즈니스용 OneDrive에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-217">Customer Lockbox is currently supported in Exchange Online, SharePoint Online, and OneDrive for Business.</span></span>

#### <a name="is-customer-lockbox-available-to-all-customers"></a><span data-ttu-id="b6cb6-218">모든 고객이 고객 Lockbox를 사용할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="b6cb6-218">Is Customer Lockbox available to all customers?</span></span>

<span data-ttu-id="b6cb6-219">고객 Lockbox는 Microsoft 365 또는 Office 365 E5 구독에 포함되어 있으며 정보 보호 및 규정 준수 또는 고급 준수 추가 기능 구독을 사용하여 다른 계획에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-219">Customer Lockbox is included with the Microsoft 365 or Office 365 E5 subscriptions and can be added to other plans with an Information Protection and Compliance or an Advanced Compliance add-on subscription.</span></span> <span data-ttu-id="b6cb6-220">자세한 내용은 [요금제 및 가격을](https://products.office.com/business/office-365-enterprise-e5-business-software) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-220">Please see [Plans and pricing](https://products.office.com/business/office-365-enterprise-e5-business-software) for more information.</span></span>

#### <a name="what-is-customer-content"></a><span data-ttu-id="b6cb6-221">고객 콘텐츠란?</span><span class="sxs-lookup"><span data-stu-id="b6cb6-221">What is customer content?</span></span>

<span data-ttu-id="b6cb6-222">고객 콘텐츠는 Microsoft 365 서비스 및 응용 프로그램의 사용자가 만든 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-222">Customer content is the data created by users of Microsoft 365 services and applications.</span></span> <span data-ttu-id="b6cb6-223">고객 콘텐츠의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-223">Examples of customer content include:</span></span>

- <span data-ttu-id="b6cb6-224">전자 메일 본문 또는 전자 메일 첨부 파일</span><span class="sxs-lookup"><span data-stu-id="b6cb6-224">Email body or email attachments</span></span>

- <span data-ttu-id="b6cb6-225">SharePoint 사이트 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="b6cb6-225">SharePoint site contents</span></span>

- <span data-ttu-id="b6cb6-226">SharePoint 파일의 본문에 있는 정보</span><span class="sxs-lookup"><span data-stu-id="b6cb6-226">Information in the body of a SharePoint file</span></span>

- <span data-ttu-id="b6cb6-227">비즈니스용 Skype 프레젠테이션 파일 본문</span><span class="sxs-lookup"><span data-stu-id="b6cb6-227">Skype for Business presentation file body</span></span>

- <span data-ttu-id="b6cb6-228">IM(인스턴트 메시지) 또는 음성 대화</span><span class="sxs-lookup"><span data-stu-id="b6cb6-228">Instant messages (IM) or voice conversations</span></span>

- <span data-ttu-id="b6cb6-229">고객 생성 Blob 또는 구조화된 저장소 데이터(예: 컨테이너 SQL)</span><span class="sxs-lookup"><span data-stu-id="b6cb6-229">Customer-generated blob or structured storage data (for example, SQL Containers)</span></span>

- <span data-ttu-id="b6cb6-230">고객 소유의 보안 정보(예: 인증서, 암호화 키 및 암호)</span><span class="sxs-lookup"><span data-stu-id="b6cb6-230">Customer-owned security information (for example, certificates, encryption keys, and passwords)</span></span>

- <span data-ttu-id="b6cb6-231">고객 콘텐츠가 남아 있는 경우 유추 및 모든 후속 유추</span><span class="sxs-lookup"><span data-stu-id="b6cb6-231">Inferences, and all subsequent inferences, if customer content remains</span></span>

<span data-ttu-id="b6cb6-232">Office 365의 고객 콘텐츠에 대한 자세한 내용은 [Office 365 트러스트 센터 를 참조하세요.](https://products.office.com/business/office-365-trust-center-privacy/)</span><span class="sxs-lookup"><span data-stu-id="b6cb6-232">For additional information about customer content in Office 365, see the [Office 365 Trust Center](https://products.office.com/business/office-365-trust-center-privacy/).</span></span>

#### <a name="who-is-notified-when-there-is-a-request-to-access-my-content"></a><span data-ttu-id="b6cb6-233">내 콘텐츠에 대한 액세스 요청이 있는 경우 누구에게 알림을 제공합니까?</span><span class="sxs-lookup"><span data-stu-id="b6cb6-233">Who is notified when there is a request to access my content?</span></span>

<span data-ttu-id="b6cb6-234">전역 관리자와 고객 Lockbox 액세스 승인자 관리자 역할이 할당된 모든 사용자에게 알림을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-234">Global administrators and anyone assigned the Customer Lockbox access approver admin role are notified.</span></span> <span data-ttu-id="b6cb6-235">고객 Lockbox 요청을 승인할 수 있는 사용자도 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-235">These are also the same users who can approve for Customer Lockbox requests.</span></span>

#### <a name="who-can-approve-or-reject-these-requests-in-my-organization"></a><span data-ttu-id="b6cb6-236">조직에서 이러한 요청을 승인하거나 거부할 수 있는 사람</span><span class="sxs-lookup"><span data-stu-id="b6cb6-236">Who can approve or reject these requests in my organization?</span></span>

<span data-ttu-id="b6cb6-237">전역 관리자와 Customer Lockbox 액세스 승인자 관리자 역할이 할당된 모든 사용자는 고객 Lockbox 요청을 승인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-237">Global administrators and anyone assigned the Customer Lockbox access approver admin role can approve Customer Lockbox requests.</span></span> <span data-ttu-id="b6cb6-238">고객은 조직에서 이러한 역할 할당을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-238">Customers control these role assignments in their organizations.</span></span>

#### <a name="how-do-i-opt-in-to-customer-lockbox"></a><span data-ttu-id="b6cb6-239">고객 Lockbox에 옵트인(opt in)하는 방법</span><span class="sxs-lookup"><span data-stu-id="b6cb6-239">How do I opt in to Customer Lockbox?</span></span>

<span data-ttu-id="b6cb6-240">전역 관리자는 Microsoft 365 또는 Microsoft 365 관리 센터에서 고객 Lockbox를 사용하도록 설정하고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-240">A global administrator can enable and configure Customer Lockbox in the Microsoft 365 or Microsoft 365 admin center.</span></span>

#### <a name="if-i-approve-a-customer-lockbox-request-what-can-the-engineer-do-and-how-will-i-know-what-the-microsoft-engineer-did"></a><span data-ttu-id="b6cb6-241">고객 Lockbox 요청을 승인하는 경우 엔지니어가 할 수 있는 일과 Microsoft 엔지니어가 어떤 작업을 했는가?</span><span class="sxs-lookup"><span data-stu-id="b6cb6-241">If I approve a Customer Lockbox request, what can the engineer do and how will I know what the Microsoft engineer did?</span></span>

<span data-ttu-id="b6cb6-242">고객 Lockbox 요청을 승인한 후 Microsoft 엔지니어는 사전 승인된 cmdlet을 사용하여 고객 콘텐츠에 액세스하는 데 필요한 권한을 부여했습니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-242">After you approve a Customer Lockbox request, the Microsoft engineer granted these necessary privileges to access customer content by using pre-approved cmdlets.</span></span> <span data-ttu-id="b6cb6-243">고객 Lockbox 요청에 대한 응답으로 Microsoft 엔지니어가 수행한 작업은 보안 및 준수 센터의 감사 로그에 기록되어 & 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-243">Actions taken by Microsoft engineers in response to Customer Lockbox requests are logged and accessible in the audit log in the Security & Compliance Center.</span></span>

#### <a name="how-do-i-know-that-microsoft-follows-the-approval-process"></a><span data-ttu-id="b6cb6-244">Microsoft가 승인 프로세스를 따르는지 어떻게 알 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="b6cb6-244">How do I know that Microsoft follows the approval process?</span></span>

<span data-ttu-id="b6cb6-245">Microsoft 365 관리 센터의 고객 Lockbox 요청 기록을 사용하여 조직의 관리자 및 승인자에게 전송되는 전자 메일 승인 알림을 상호 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-245">You can cross-reference the email approval notifications sent to admins and approvers in your organization with the Customer Lockbox request history in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="b6cb6-246">Customer Lockbox는 최신 [SOC 1 SSAE 16 감사 보고서에 포함되어 있습니다.](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports)</span><span class="sxs-lookup"><span data-stu-id="b6cb6-246">Customer Lockbox is included in the latest [SOC 1 SSAE 16 audit report](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports).</span></span> <span data-ttu-id="b6cb6-247">자세한 내용은 Microsoft Service Trust Portal 에서 최신 [보고서를 찾을 수 있습니다.](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports)</span><span class="sxs-lookup"><span data-stu-id="b6cb6-247">For more details, you can find the latest reports in the [Microsoft Service Trust Portal](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports).</span></span>

#### <a name="can-microsoft-modify-the-list-of-approvers-for-my-tenant-if-not-how-is-it-prevented"></a><span data-ttu-id="b6cb6-248">Microsoft에서 내 테넌트에 대한 승인자 목록을 수정할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="b6cb6-248">Can Microsoft modify the list of approvers for my tenant?</span></span> <span data-ttu-id="b6cb6-249">그렇지 않은 경우 어떻게 방지하나요?</span><span class="sxs-lookup"><span data-stu-id="b6cb6-249">If not, how is it prevented?</span></span>

<span data-ttu-id="b6cb6-250">조직의 전역 관리자만 고객 Lockbox 요청을 승인할 수 있는 대상을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-250">Only a global administrator in your organization can specify who can approve Customer Lockbox requests.</span></span> <span data-ttu-id="b6cb6-251">즉, Azure Active Directory의 전역 관리자 그룹의 구성원만 요청을 승인할 수 있는 대상을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-251">That means only the members of the Global administrator group in Azure Active Directory can specify who can approve request.</span></span> <span data-ttu-id="b6cb6-252">Azure Active Directory에서 전역 관리자 그룹의 구성원 자격은 조직에서만 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-252">Membership of the Global administrator group in Azure Active Directory is managed only by your organization.</span></span>

#### <a name="what-if-i-need-more-information-about-a-content-access-request-to-approve-it"></a><span data-ttu-id="b6cb6-253">승인하기 위해 콘텐츠 액세스 요청에 대한 자세한 정보가 필요한 경우 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="b6cb6-253">What if I need more information about a content access request to approve it?</span></span>

<span data-ttu-id="b6cb6-254">각 고객 Lockbox 요청에는 Microsoft 365 서비스 요청 번호가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-254">Each Customer Lockbox request contains a Microsoft 365 service request number.</span></span> <span data-ttu-id="b6cb6-255">Microsoft 지원 서비스에 문의하여 이 서비스 번호를 참조하여 요청에 대한 자세한 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-255">You can contact Microsoft Support and reference this service number to get more information about the request.</span></span>

#### <a name="when-a-customer-lockbox-request-is-approved-how-long-are-the-permissions-valid"></a><span data-ttu-id="b6cb6-256">고객 Lockbox 요청이 승인되면 사용 권한이 얼마나 오래 유효한가요?</span><span class="sxs-lookup"><span data-stu-id="b6cb6-256">When a Customer Lockbox request is approved, how long are the permissions valid?</span></span>

<span data-ttu-id="b6cb6-257">현재 Microsoft 엔지니어에게 부여된 액세스 권한의 최대 기간은 4시간입니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-257">Currently, the maximum period for the access permissions granted to the Microsoft engineer is 4 hours.</span></span> <span data-ttu-id="b6cb6-258">Microsoft 엔지니어가 더 짧은 기간을 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-258">The Microsoft engineer can also request a shorter period.</span></span>

#### <a name="how-can-i-get-a-history-of-all-customer-lockbox-requests"></a><span data-ttu-id="b6cb6-259">모든 고객 Lockbox 요청에 대한 기록을 얻은 방법</span><span class="sxs-lookup"><span data-stu-id="b6cb6-259">How can I get a history of all Customer Lockbox requests?</span></span>

<span data-ttu-id="b6cb6-260">모든 고객 Lockbox 요청은 Microsoft 365 관리 센터에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-260">All Customer Lockbox requests are viewed in the Microsoft 365 admin center.</span></span>

#### <a name="how-do-i-correlate-the-content-access-requests-with-the-related-audit-logs"></a><span data-ttu-id="b6cb6-261">콘텐츠 액세스 요청과 관련 감사 로그의 상관 관계는 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="b6cb6-261">How do I correlate the content access requests with the related audit logs?</span></span>

<span data-ttu-id="b6cb6-262">준수 센터 활동 피드에는 고객 Lockbox의 로그 활동이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-262">The Compliance Center Activity Feed contains log activities of Customer Lockbox.</span></span> <span data-ttu-id="b6cb6-263">고객은 받은 전자 메일 요청에 대해 활동 피드에서 고객 Lockbox 로그 활동을 상호 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-263">Customers can cross-reference the Customer Lockbox log activities from the activity feed against the email request they receive.</span></span>

#### <a name="what-happens-when-a-customer-doesnt-respond-to-a-customer-lockbox-request"></a><span data-ttu-id="b6cb6-264">고객이 고객 Lockbox 요청에 응답하지 않는 경우 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="b6cb6-264">What happens when a customer doesn't respond to a Customer Lockbox request?</span></span>

<span data-ttu-id="b6cb6-265">고객 Lockbox 요청의 기본 기간은 12시간입니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-265">Customer Lockbox requests have a default duration of 12 hours.</span></span> <span data-ttu-id="b6cb6-266">12시간 내에 요청에 응답하지 않는 경우 요청이 만료됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-266">If you don't respond to a request within 12 hour, the request expires.</span></span>

#### <a name="what-does-microsoft-do-when-a-customer-rejects-a-customer-lockbox-request"></a><span data-ttu-id="b6cb6-267">고객이 고객 Lockbox 요청을 거부할 때 Microsoft는 어떤 작업을 하나요?</span><span class="sxs-lookup"><span data-stu-id="b6cb6-267">What does Microsoft do when a customer rejects a Customer Lockbox request?</span></span>

<span data-ttu-id="b6cb6-268">고객이 고객 Lockbox 요청을 거부하면 고객 콘텐츠에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-268">If a customer rejects a Customer Lockbox request, no access to customer content occurs.</span></span> <span data-ttu-id="b6cb6-269">조직의 사용자가 Microsoft에서 고객 콘텐츠에 액세스하여 문제를 해결해야 하는 서비스 문제가 계속 발생하면 서비스 문제가 지속될 수 있으며 Microsoft는 사용자에게 이에 대해 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-269">If a user in your organization continues to experience a service issue requiring Microsoft to access customer content to resolve the issue, then the service issue might persist and Microsoft will inform the user about this.</span></span>

#### <a name="does-customer-lockbox-protect-against-data-requests-from-law-enforcement-agencies-or-other-third-parties"></a><span data-ttu-id="b6cb6-270">고객 Lockbox가 사법 기관 또는 기타 타사의 데이터 요청으로부터 보호하나요?</span><span class="sxs-lookup"><span data-stu-id="b6cb6-270">Does Customer Lockbox protect against data requests from law enforcement agencies or other third parties?</span></span>

<span data-ttu-id="b6cb6-271">아니요.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-271">No.</span></span> <span data-ttu-id="b6cb6-272">Microsoft는 고객 데이터에 대한 타사 요청을 심각하게 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-272">Microsoft takes third-party requests for customer data seriously.</span></span> <span data-ttu-id="b6cb6-273">클라우드 서비스 공급자인 Microsoft는 고객 데이터의 개인 정보 보호를 항상 지지합니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-273">As a cloud service provider, Microsoft always advocates for the privacy of customer data.</span></span> <span data-ttu-id="b6cb6-274">소계를 받을 경우 Microsoft는 항상 제3자에 대한 리디렉션을 시도하여 정보를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-274">In the event we get a subpoena, Microsoft always attempts to redirect the third party to the customer to obtain the information.</span></span> <span data-ttu-id="b6cb6-275">(Brad Smith의 블로그: 정부 스누프로부터 고객 데이터 [보호)를 읽어 읽습니다.](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/)</span><span class="sxs-lookup"><span data-stu-id="b6cb6-275">(Read Brad Smith's blog: [Protecting customer data from government snooping](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/)).</span></span> <span data-ttu-id="b6cb6-276">Microsoft가 수신하는 [](https://www.microsoft.com/corporate-responsibility/lerr) 사법 기관 요청에 대한 자세한 정보를 주기적으로 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-276">We periodically publish [detailed information](https://www.microsoft.com/corporate-responsibility/lerr) about the law enforcement requests that Microsoft receives.</span></span>

<span data-ttu-id="b6cb6-277">자세한 내용은 타사 데이터 요청에 관한 [Microsoft](https://www.microsoft.com/trustcenter/default.aspx) 보안 센터 및 온라인 서비스 [](https://www.microsoft.com/Licensing/product-licensing/products.aspx) 약관의 "고객 데이터 공개" 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-277">See the [Microsoft Trust Center](https://www.microsoft.com/trustcenter/default.aspx) regarding third-party data requests and the "Disclosure of Customer Data" section in the [Online Services Terms](https://www.microsoft.com/Licensing/product-licensing/products.aspx) for more information.</span></span>

#### <a name="how-does-microsoft-ensure-that-a-member-of-its-staff-doesnt-have-standing-access-to-customer-content-in-office-365-applications"></a><span data-ttu-id="b6cb6-278">Microsoft는 직원의 구성원이 Office 365 응용 프로그램에서 고객 콘텐츠에 대한 정식 액세스 권한이 없는지 어떻게 보장하나요?</span><span class="sxs-lookup"><span data-stu-id="b6cb6-278">How does Microsoft ensure that a member of its staff doesn't have standing access to customer content in Office 365 applications?</span></span>

<span data-ttu-id="b6cb6-279">Microsoft는 액세스 제어 시스템을 통해 광범위한 예방 조치와 이러한 액세스 제어 시스템을 우회하려는 시도를 식별하고 해결하기 위한 감지 조치를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-279">Microsoft implements extensive preventive measures through access control systems, and detective measures to identify and address attempts to circumvent these access control systems.</span></span> <span data-ttu-id="b6cb6-280">Microsoft 365는 최소 권한 및 정시 액세스 원칙을 통해 운영됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-280">Microsoft 365 operates with the principles of least privilege and just-in-time access.</span></span> <span data-ttu-id="b6cb6-281">따라서 Microsoft 직원은 지속적인 기준에 따라 고객 콘텐츠에 액세스할 수 있는 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-281">Therefore, no Microsoft personnel have permission to access customer content on an ongoing basis.</span></span> <span data-ttu-id="b6cb6-282">권한이 부여된 경우 제한된 기간 동안만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-282">If permission is granted, it is for a limited duration.</span></span> 

<span data-ttu-id="b6cb6-283">Microsoft 365는 *Lockbox라는* 액세스 제어 시스템을 사용하여 서비스 내에서 운영 및 관리 기능을 수행할 수 있는 권한을 부여하는 사용 권한 요청을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-283">Microsoft 365 uses an access control system called *Lockbox* to process requests for permissions that grant the ability to perform operational and administrative functions within the service.</span></span> <span data-ttu-id="b6cb6-284">운영자는 Lockbox를 사용하여 고객 콘텐츠에 대한 액세스를 요청해야 합니다. 그러면 액세스 권한이 부여되기 전에 두 번째 사람이 요청에 대한 작업(예: 승인)을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-284">An operator must request access to customer content using Lockbox, which then requires a second person to take action on the request (e.g., approve it) before access is granted.</span></span> <span data-ttu-id="b6cb6-285">두 번째 사람은 요청자가 될 수 없습니다. 고객 콘텐츠에 대한 액세스를 승인할 수 있도록 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-285">That second person can't be the requestor and must be designated to approve access to customer content.</span></span> <span data-ttu-id="b6cb6-286">요청이 승인된 경우만 운영자가 고객 콘텐츠에 대한 임시 액세스를 획득합니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-286">Only if the request is approved does the operator acquire temporary access to customer content.</span></span> <span data-ttu-id="b6cb6-287">권한 상승 기간이 만료되면 Lockbox는 액세스를 해지합니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-287">After the elevation period expires, Lockbox revokes access.</span></span>

<span data-ttu-id="b6cb6-288">Microsoft 일반 보안 [사례에](https://www.microsoft.com/licensing/product-licensing/products) 대한 자세한 내용은 온라인 서비스 약관을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-288">Please refer to the [Online Services Terms](https://www.microsoft.com/licensing/product-licensing/products) for more details about Microsoft general security practices.</span></span>

#### <a name="under-what-circumstances-do-microsoft-engineers-need-access-to-my-content"></a><span data-ttu-id="b6cb6-289">Microsoft 엔지니어가 내 콘텐츠에 액세스해야 하는 상황</span><span class="sxs-lookup"><span data-stu-id="b6cb6-289">Under what circumstances do Microsoft engineers need access to my content?</span></span>

<span data-ttu-id="b6cb6-290">Microsoft 엔지니어가 고객 콘텐츠에 액세스해야 하는 가장 일반적인 시나리오는 고객이 문제 해결을 위해 액세스가 필요한 지원 요청을 하는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-290">The most common scenario where Microsoft engineers need access customer content is when the customer makes a support request requiring access for troubleshooting.</span></span> <span data-ttu-id="b6cb6-291">Microsoft 365의 기본 원칙은 Microsoft에서 고객 콘텐츠에 액세스하지 않고 서비스를 운영하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-291">A foundational principle of Microsoft 365 is that the service operates without Microsoft access to customer content.</span></span> <span data-ttu-id="b6cb6-292">Microsoft에서 수행한 거의 모든 서비스 작업은 완전히 자동화되고 사람 개입은 고객 콘텐츠에서 고도로 제어되고 추상화됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-292">Nearly all service operations performed by Microsoft are fully automated and human involvement is highly controlled and abstracted away from customer content.</span></span> <span data-ttu-id="b6cb6-293">Microsoft 365의 목표는 고객이 Microsoft 액세스에 대한 특정 요청을 승인할 때까지 서비스를 지원하기 위한 고객 콘텐츠에 액세스하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-293">The goal for Microsoft 365 is access to customer content to support the service isn't needed until the customer approves a specific request for Microsoft access.</span></span>

#### <a name="i-already-thought-my-data-was-secure-with-the-microsoft-cloud-so-why-do-i-need-customer-lockbox"></a><span data-ttu-id="b6cb6-294">Microsoft 클라우드를 사용하여 데이터가 이미 안전하다고 생각한 경우 고객 Lockbox가 필요한 이유는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="b6cb6-294">I already thought my data was secure with the Microsoft cloud, so why do I need Customer Lockbox?</span></span>

<span data-ttu-id="b6cb6-295">고객 Lockbox는 고객에게 서비스 작업에 대한 명시적 액세스 권한 부여를 제공하는 기능을 제공하여 추가 제어 계층을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-295">Customer Lockbox provides an extra layer of control by offering customers the ability to give explicit access authorization for service operations.</span></span> <span data-ttu-id="b6cb6-296">또한 Customer Lockbox는 명시적인 데이터 액세스 권한 부여를 위한 절차가 준비 중이라며, 고객이 HIPAA 및 FEDRAMP와 같은 특정 준수 의무를 이행하는 데에도 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6cb6-296">By demonstrating that procedures are in place for explicit data access authorization, Customer Lockbox also helps customers meet certain compliance obligations such as HIPAA and FEDRAMP.</span></span>