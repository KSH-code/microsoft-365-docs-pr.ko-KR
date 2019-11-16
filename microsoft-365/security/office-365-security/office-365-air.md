---
title: Office 365의 위협에 대한 자동 조사 및 응답
keywords: AIR, autoIR, ATP, 자동화, 조사, 대응, 재구성, 위협, 고급, 위협, 보호
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 11/15/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Office 365 Advanced Threat Protection 계획 2의 자동 보안 문제 대응 기능 사용을 시작 하세요.
ms.openlocfilehash: 13f7e95829b8cf3adf17a40cf7b02c5322b15ea7
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2019
ms.locfileid: "38673424"
---
# <a name="automatically-investigate-and-respond-to-threats-in-office-365"></a><span data-ttu-id="e81b3-104">Office 365의 위협에 대한 자동 조사 및 응답</span><span class="sxs-lookup"><span data-stu-id="e81b3-104">Automatically investigate and respond to threats in Office 365</span></span>

## <a name="overview"></a><span data-ttu-id="e81b3-105">개요</span><span class="sxs-lookup"><span data-stu-id="e81b3-105">Overview</span></span>

<span data-ttu-id="e81b3-106">구독에 따라 [Office 365 Advanced Threat Protection](office-365-atp.md) 에는 경고 및 위협 처리에 대 한 보안 작업 팀의 시간과 노력을 절감할 수 있는 자동화 된 문제 대응 (AIR) 기능이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e81b3-106">Depending on your subscription, [Office 365 Advanced Threat Protection](office-365-atp.md) can include automated incident response (AIR) capabilities that can save your security operations team time and effort in dealing with alerts and threats.</span></span>

- <span data-ttu-id="e81b3-107">Office 365의 AIR 기능 사용을 시작 하려면이 문서를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e81b3-107">To get started using AIR capabilities in Office 365, use this article.</span></span> 
- <span data-ttu-id="e81b3-108">AIR의 작동 방식에 대 한 개요를 보려면 [Office 365에서 자동 인시던트 응답 (AIR)](automated-investigation-response-office.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e81b3-108">To get an overview of how AIR works, see [Automated incident response (AIR) in Office 365](automated-investigation-response-office.md).</span></span>

<span data-ttu-id="e81b3-109">AIR을 사용 하 여 특정 알림이 트리거되면 하나 이상의 보안 playbook가 시작 되 고 자동 조사가 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e81b3-109">With AIR, when certain alerts are triggered, one or more security playbooks initiate, and automated investigation begins.</span></span> <span data-ttu-id="e81b3-110">자동화 된 조사 프로세스 중 및 후에 관리자와 보안 운영 팀은 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e81b3-110">During and after an automated investigation process, your administrators and security operations team can:</span></span>

- [<span data-ttu-id="e81b3-111">조사 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="e81b3-111">View the details of an investigation</span></span>](#view-details-of-an-investigation)
- [<span data-ttu-id="e81b3-112">조사 결과로 작업 검토 및 승인</span><span class="sxs-lookup"><span data-stu-id="e81b3-112">Review and approve actions as a result of an investigation</span></span>](#review-and-approve-actions) 
- [<span data-ttu-id="e81b3-113">조사와 관련 된 경고에 대 한 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="e81b3-113">View details about an alert related to an investigation</span></span>](#view-details-about-an-alert-related-to-an-investigation)

> [!NOTE]
> <span data-ttu-id="e81b3-114">이 문서에서 설명 하는 작업을 수행 하려면 적절 한 사용 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e81b3-114">You must have appropriate permissions to perform the tasks described in this article.</span></span> <span data-ttu-id="e81b3-115">예를 들어 myst는 전역 관리자, 보안 관리자, 보안 운영자 또는 보안 판독기입니다.</span><span class="sxs-lookup"><span data-stu-id="e81b3-115">For example, you myst be a global administrator, security administrator, security operator, or security reader.</span></span> <span data-ttu-id="e81b3-116">[Microsoft 365 보안 센터 역할 및 권한에](https://docs.microsoft.com/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions)대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="e81b3-116">[Learn more about Microsoft 365 security center roles and permissions](https://docs.microsoft.com/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions).</span></span>

<span data-ttu-id="e81b3-117">AIR은 다음 구독에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e81b3-117">AIR is included in the following subscriptions:</span></span>
- <span data-ttu-id="e81b3-118">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="e81b3-118">Microsoft 365 E5</span></span>
- <span data-ttu-id="e81b3-119">Microsoft 365 E5 Security</span><span class="sxs-lookup"><span data-stu-id="e81b3-119">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="e81b3-120">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="e81b3-120">Office 365 E5</span></span>
- <span data-ttu-id="e81b3-121">Office 365 Advanced Threat Protection Plan 2</span><span class="sxs-lookup"><span data-stu-id="e81b3-121">Office 365 Advanced Threat Protection Plan 2</span></span>

<span data-ttu-id="e81b3-122">이러한 구독 중 하나가 없으면 [무료 평가판을 시작](https://go.microsoft.com/fwlink/p/?LinkID=698279)합니다.</span><span class="sxs-lookup"><span data-stu-id="e81b3-122">If you don't have one of these subscriptions, [start a free trial](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span>

## <a name="view-details-of-an-investigation"></a><span data-ttu-id="e81b3-123">조사 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="e81b3-123">View details of an investigation</span></span>

1. <span data-ttu-id="e81b3-124">Office 365 전역 관리자, 보안 관리자 또는 보안 독자 (으 [https://protection.office.com](https://protection.office.com) )로 이동 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e81b3-124">As an Office 365 global administrator, security administrator, or security reader, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="e81b3-125">그러면 보안 & 준수 센터로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e81b3-125">This takes you to the the Security & Compliance Center.</span></span>

2. <span data-ttu-id="e81b3-126">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e81b3-126">Do one of the following:</span></span>

    - <span data-ttu-id="e81b3-127">**위협 관리** > **대시보드로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e81b3-127">Go to **Threat management** > **Dashboard**.</span></span> <span data-ttu-id="e81b3-128">그러면 [보안 대시보드가](security-dashboard.md)이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e81b3-128">This takes you to the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="e81b3-129">[보안 대시보드](security-dashboard.md)위쪽에 AIR widget이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e81b3-129">Your AIR widgets appear across the top of the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="e81b3-130">**조사 요약과**같은 위젯을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e81b3-130">Select a widget, such as **Investigations summary**.</span></span>

    - <span data-ttu-id="e81b3-131">**위협 관리** > **조사**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e81b3-131">Go to **Threat management** > **Investigations**.</span></span> 

    <span data-ttu-id="e81b3-132">어느 방법을 사용 하 든 조사 목록이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e81b3-132">Either method takes you to a list of investigations.</span></span>

    ![AIR의 주 조사 페이지](../media/air-maininvestigationpage.png) 

3. <span data-ttu-id="e81b3-134">조사 목록에서 **ID** 열의 항목을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e81b3-134">In the list of investigations, select an item in the **ID** column.</span></span> <span data-ttu-id="e81b3-135">그러면 보기의 조사 그래프부터 시작 하 여 조사 세부 정보 페이지가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="e81b3-135">This opens investigation details page, starting with the investigation graph in view.</span></span>

    ![AIR 조사 그래프 페이지](../media/air-investigationgraphpage.png)

4. <span data-ttu-id="e81b3-137">여러 탭을 사용 하 여 조사에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="e81b3-137">Use the various tabs to learn more about the investigation.</span></span>

## <a name="review-and-approve-actions"></a><span data-ttu-id="e81b3-138">작업 검토 및 승인</span><span class="sxs-lookup"><span data-stu-id="e81b3-138">Review and approve actions</span></span>

<span data-ttu-id="e81b3-139">Office 365에서 자동화 된 조사는 일반적으로 하나 이상의 권장 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e81b3-139">In Office 365, automated investigations typically result in one or more recommended actions.</span></span> <span data-ttu-id="e81b3-140">그러나 보안 운영 팀이 승인 해야 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e81b3-140">However, no actions are taken until they are approved by your security operations team.</span></span> <span data-ttu-id="e81b3-141">다음 절차에 따라 작업을 검토 하 고 승인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e81b3-141">Use the following procedure to review and approve actions.</span></span>

1. <span data-ttu-id="e81b3-142">Office 365 전역 관리자, 보안 관리자 또는 보안 독자 (으 [https://protection.office.com](https://protection.office.com) )로 이동 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e81b3-142">As an Office 365 global administrator, security administrator, or security reader, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> 

2. <span data-ttu-id="e81b3-143">**위협 관리** > **조사**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e81b3-143">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="e81b3-144">조사 목록에서 **ID** 열의 항목을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e81b3-144">In the list of investigations, select an item in the **ID** column.</span></span> 

3. <span data-ttu-id="e81b3-145">조사 세부 정보 보기에서 **작업** 탭을 선택 합니다. 승인 보류 중인 모든 작업은 여기에 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e81b3-145">On the investigation details view, select the **Actions** tab. Any actions that are pending approval are listed here.</span></span>

4. <span data-ttu-id="e81b3-146">목록에서 항목을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e81b3-146">Select an item in the list.</span></span>

5. <span data-ttu-id="e81b3-147">권장 작업을 수행 하려면 **승인** 을 선택 하 고 아니면 작업을 수행 하지 않고 조사를 닫기 위해 **거부** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e81b3-147">Select **Approve** to take the recommended action (or **Reject** to close the investigation without taking action).</span></span>

## <a name="view-details-about-an-alert-related-to-an-investigation"></a><span data-ttu-id="e81b3-148">조사와 관련 된 경고에 대 한 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="e81b3-148">View details about an alert related to an investigation</span></span>

<span data-ttu-id="e81b3-149">특정 유형의 경고는 Office 365에서 자동화 된 조사를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="e81b3-149">Certain kinds of alerts trigger automated investigation in Office 365.</span></span> <span data-ttu-id="e81b3-150">자세한 내용은 [Alerts](automated-investigation-response-office.md#alerts)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e81b3-150">To learn more, see [Alerts](automated-investigation-response-office.md#alerts).</span></span> <span data-ttu-id="e81b3-151">다음 절차에 따라 자동화 된 조사에 연결 된 경고에 대 한 세부 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e81b3-151">Use the following procedure to view details about an alert that is associated with an automated investigation.</span></span>

1. <span data-ttu-id="e81b3-152">Office 365 전역 관리자, 보안 관리자 또는 보안 독자 (으 [https://protection.office.com](https://protection.office.com) )로 이동 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e81b3-152">As an Office 365 global administrator, security administrator, or security reader, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="e81b3-153">그러면 보안 & 준수 센터로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e81b3-153">This takes you to the the Security & Compliance Center.</span></span>

2. <span data-ttu-id="e81b3-154">**위협 관리** > **조사**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e81b3-154">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="e81b3-155">조사 목록에서 **ID** 열의 항목을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e81b3-155">In the list of investigations, select an item in the **ID** column.</span></span> 

4. <span data-ttu-id="e81b3-156">조사에 대 한 세부 정보를 연 상태에서 **알림** 탭을 선택 합니다. 조사를 트리거한 모든 경고가 여기에 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e81b3-156">With details of an investigation open, select the **Alerts** tab. Any alerts that triggered the investigation are listed here.</span></span>

5. <span data-ttu-id="e81b3-157">목록에서 항목을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e81b3-157">Select an item in the list.</span></span> <span data-ttu-id="e81b3-158">플라이 아웃이 열리고 경고에 대 한 세부 정보와 추가 정보 및 작업에 대 한 링크가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e81b3-158">A flyout opens, with details about the alert and links to additional information and actions.</span></span>

6. <span data-ttu-id="e81b3-159">플라이 아웃에 대 한 정보를 검토 하 고, 특정 경고에 따라 사용자에 대 한 **해결**, **억제**또는 **알림**등의 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e81b3-159">Review the information on the flyout, and, depending on the particular alert, take an action, such as **Resolve**, **Suppress**, or **Notify users**.</span></span> 

    - <span data-ttu-id="e81b3-160">**확인** 은 경고를 닫는 것과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="e81b3-160">**Resolve** is equivalent to closing an alert</span></span>
    
    - <span data-ttu-id="e81b3-161">정책이 지정 된 기간에 대해 알림을 트리거하지 **않도록 설정 합니다** .</span><span class="sxs-lookup"><span data-stu-id="e81b3-161">**Suppress** causes a policy to not trigger alerts for a specified period of time</span></span>
    
    - <span data-ttu-id="e81b3-162">**사용자에** 게 사용자의 전자 메일 주소가 이미 입력 된 전자 메일을 시작 하 고, 보안 운영 팀에서 해당 사용자에 게 메시지를 입력할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e81b3-162">**Notify users** starts an email with users' email addresses already entered, and enables your security operations team to type a message to those users.</span></span> <span data-ttu-id="e81b3-163">이는 [위협 탐색기](threat-explorer.md)를 사용 하 여 받는 사람에 게 메시지를 보내는 것과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="e81b3-163">(This is similar to sending a message to recipients using [Threat Explorer](threat-explorer.md).)</span></span>  

## <a name="use-the-office-365-management-activity-api-for-custom-or-third-party-reporting-solutions"></a><span data-ttu-id="e81b3-164">사용자 지정 또는 타사 보고 솔루션에 Office 365 관리 활동 API 사용</span><span class="sxs-lookup"><span data-stu-id="e81b3-164">Use the Office 365 Management Activity API for custom or third-party reporting solutions</span></span>

<span data-ttu-id="e81b3-165">조직에서 사용자 지정 또는 타사 보고 솔루션을 사용 하는 경우에는 Office 365 관리 활동 API를 사용 하 여 해당 솔루션의 자동화 된 조사에 대 한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e81b3-165">If your organization is using a custom or third-party reporting solution, you can view information about automated investigations in that solution by using the Office 365 Management Activity API.</span></span>

<span data-ttu-id="e81b3-166">다음 리소스를 사용 하 여이를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e81b3-166">Use the following resources to set this up:</span></span>

|<span data-ttu-id="e81b3-167">리소스</span><span class="sxs-lookup"><span data-stu-id="e81b3-167">Resource</span></span>  |<span data-ttu-id="e81b3-168">설명</span><span class="sxs-lookup"><span data-stu-id="e81b3-168">Description</span></span>  |
|---------|---------|
|[<span data-ttu-id="e81b3-169">Office 365 관리 Api 개요</span><span class="sxs-lookup"><span data-stu-id="e81b3-169">Office 365 Management APIs overview</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)     |<span data-ttu-id="e81b3-170">Office 365 관리 활동 API는 Office 365 및 Azure Active Directory 활동 로그에서 다양 한 사용자, 관리자, 시스템 및 정책 작업과 이벤트에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e81b3-170">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Office 365 and Azure Active Directory activity logs.</span></span>         |
|[<span data-ttu-id="e81b3-171">Office 365 관리 Api 시작 하기</span><span class="sxs-lookup"><span data-stu-id="e81b3-171">Get started with Office 365 Management APIs</span></span>](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)     |<span data-ttu-id="e81b3-172">Office 365 관리 API는 Azure AD를 사용 하 여 응용 프로그램에서 Office 365 데이터에 액세스 하는 데 필요한 인증 서비스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e81b3-172">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Office 365 data.</span></span> <span data-ttu-id="e81b3-173">이 문서에서 설명 하는 단계에 따라 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e81b3-173">Follow the steps in this article to set this up.</span></span>          |
|[<span data-ttu-id="e81b3-174">Office 365 관리 활동 API 참조</span><span class="sxs-lookup"><span data-stu-id="e81b3-174">Office 365 Management Activity API reference</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)     |<span data-ttu-id="e81b3-175">Office 365 관리 활동 API를 사용 하 여 Office 365 및 Azure AD 활동 로그에서 사용자, 관리자, 시스템 및 정책 작업과 이벤트에 대 한 정보를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e81b3-175">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Office 365 and Azure AD activity logs.</span></span> <span data-ttu-id="e81b3-176">이 문서를 읽으면 작동 방식에 대해 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e81b3-176">Read this article to learn more about how this works.</span></span>        |
|[<span data-ttu-id="e81b3-177">Office 365 관리 활동 API 스키마</span><span class="sxs-lookup"><span data-stu-id="e81b3-177">Office 365 Management Activity API schema</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)     |<span data-ttu-id="e81b3-178">Office 365 관리 활동 API를 통해 사용할 수 있는 특정 종류의 데이터에 대 한 자세한 내용은 [일반 스키마](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) 및 [Office 365 ATP 및 위협 조사 및 응답 스키마](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) 개요를 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="e81b3-178">Get an overview of the [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Office 365 ATP and threat investigation and response schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>         |

## <a name="next-steps"></a><span data-ttu-id="e81b3-179">다음 단계</span><span class="sxs-lookup"><span data-stu-id="e81b3-179">Next steps</span></span>

[<span data-ttu-id="e81b3-180">알림에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="e81b3-180">Learn more about alerts</span></span>](../../compliance/alert-policies.md)

[<span data-ttu-id="e81b3-181">Office 365에서 제공 된 악성 전자 메일을 수동으로 찾아서 조사</span><span class="sxs-lookup"><span data-stu-id="e81b3-181">Manually find and investigate malicious email that was delivered in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)

[<span data-ttu-id="e81b3-182">Microsoft Defender ATP의 AIR에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="e81b3-182">Learn about AIR in Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

[<span data-ttu-id="e81b3-183">Microsoft 365 로드맵를 방문 하 여 곧 제공 되는 항목을 확인 하 고 롤아웃</span><span class="sxs-lookup"><span data-stu-id="e81b3-183">Visit the Microsoft 365 Roadmap to see what's coming soon and rolling out</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)