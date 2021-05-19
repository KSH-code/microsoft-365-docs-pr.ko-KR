---
title: Microsoft 365 감사 솔루션
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- m365-security-compliance
- m365solution-audit
- m365initiative-compliance
- m365solution-overview
search.appverid:
- MOE150
- MET150
description: Microsoft 365 조직의 사용자와 관리자의 활동을 감사하는 방법에 대해 알아 보세요.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d8686a2cd7b1fc6e9082e85b18ba352c1fd7f830
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538521"
---
# <a name="auditing-solutions-in-microsoft-365"></a><span data-ttu-id="03e69-103">Microsoft 365의 감사 솔루션</span><span class="sxs-lookup"><span data-stu-id="03e69-103">Auditing solutions in Microsoft 365</span></span>

<span data-ttu-id="03e69-104">Microsoft 365 감사 솔루션은 조직이 보안 이벤트, 법의학적 조사, 내부 조사 및 규정 준수 의무에 효과적으로 대응할 수 있도록 지원하는 통합 솔루션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="03e69-104">Microsoft 365 auditing solutions provide an integrated solution to help organizations effectively respond to security events, forensic investigations, internal investigations, and compliance obligations.</span></span> <span data-ttu-id="03e69-105">수십 개의 Microsoft 365 서비스 및 솔루션에서 수행되는 수천 개의 사용자 및 관리 작업이 조직의 통합 감사 로그에 캡처, 기록 및 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="03e69-105">Thousands of user and admin operations performed in dozens of Microsoft 365 services and solutions are captured, recorded, and retained in your organization's unified audit log.</span></span> <span data-ttu-id="03e69-106">이러한 이벤트에 대한 감사 기록은 보안 운영자, IT 관리자, 내부자 위험 팀, 조직의 규정 준수 및 법률 조사관이 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e69-106">Audit records for these events are searchable by security ops, IT admins, insider risk teams, and compliance and legal investigators in your organization.</span></span> <span data-ttu-id="03e69-107">이 기능을 사용하면 Microsoft 365 조직 전체에서 수행되는 작업을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e69-107">This capability provides visibility into the activities performed across your Microsoft 365 organization.</span></span>

## <a name="microsoft-365-auditing-solutions"></a><span data-ttu-id="03e69-108">Microsoft 365 감사 솔루션</span><span class="sxs-lookup"><span data-stu-id="03e69-108">Microsoft 365 auditing solutions</span></span>

<span data-ttu-id="03e69-109">Microsoft 365는 기본 감사 및 고급 감사라는 두 가지 감사 솔루션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="03e69-109">Microsoft 365 provides two auditing solutions: Basic Audit and Advanced Audit.</span></span>

![기본 감사 및 고급 감사의 주요 기능](..\media\AuditingSolutionsComparison.png)

### <a name="basic-audit"></a><span data-ttu-id="03e69-111">기본 감사</span><span class="sxs-lookup"><span data-stu-id="03e69-111">Basic Audit</span></span>

<span data-ttu-id="03e69-112">기본 감사 기능은 감사된 활동을 기록 및 검색하고 법의학, IT, 규정 준수 및 법적 조사를 수행할 수 있는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="03e69-112">Basic Audit provides with you with the ability to log and search for audited activities and power your forensic, IT, compliance, and legal investigations.</span></span>

- <span data-ttu-id="03e69-113">**기본적으로 사용 설정** 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03e69-113">**Enabled by default**.</span></span> <span data-ttu-id="03e69-114">기본 감사는 해당 구독이 있는 모든 조직에 대해 기본적으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="03e69-114">Basic Audit is turned on by default for all organizations with the appropriate subscription.</span></span> <span data-ttu-id="03e69-115">이는 감사된 활동에 대한 기록을 캡처하고 검색할 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="03e69-115">That means records for audited activities will be captured and searchable.</span></span> <span data-ttu-id="03e69-116">필요한 유일한 설정은 감사 로그 검색 도구(및 해당 cmdlet)에 액세스하는 데 필요한 사용 권한을 할당하고 사용자의 에 고급 감사 기능에 올바른 라이선스가 할당되었는지 확인하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="03e69-116">The only setup that required is to assign the necessary permissions to access the audit log search tool (and the corresponding cmdlet) and make sure that user's are assigned the right license for Advanced Audit features.</span></span>
- <span data-ttu-id="03e69-117">**수천 개의 검색 가능한 감사 이벤트**.</span><span class="sxs-lookup"><span data-stu-id="03e69-117">**Thousands of searchable audit events**.</span></span> <span data-ttu-id="03e69-118">조직의 대부분의 Microsoft 365 서비스에서 발생하는 광범위한 감사 활동을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e69-118">You can search for a wide-range of audited activities that occur is most of the Microsoft 365 services in your organization.</span></span> <span data-ttu-id="03e69-119">검색할 수 있는 작업의 일부 목록은 [감사 활동](search-the-audit-log-in-security-and-compliance.md#audited-activities)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="03e69-119">For a partial list of the activities you can search for, see [Audited activities](search-the-audit-log-in-security-and-compliance.md#audited-activities).</span></span> <span data-ttu-id="03e69-120">감사된 작업을 지원하는 서비스 및 기능 목록은 [감사 로그 레코드 유형](/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="03e69-120">For a list of the services and features that support audited activities, see [Audit log record type](/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype).</span></span>
- <span data-ttu-id="03e69-121">**Microsoft 365 규정 준수 센터의 감사 검색 도구**.</span><span class="sxs-lookup"><span data-stu-id="03e69-121">**Audit search tool in the Microsoft 365 compliance center**.</span></span> <span data-ttu-id="03e69-122">Microsoft 365 규정 준수 센터의 감사 로그 검색 도구를 사용하여 감사 레코드를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="03e69-122">Use the Audit log search tool in the Microsoft 365 compliance center to search for audit records.</span></span> <span data-ttu-id="03e69-123">특정 활동, 특정 사용자가 수행한 활동 및 날짜 범위로 발생한 활동을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e69-123">You can search for specific activities, for activities performed by specific users, and activities that occurred with a date range.</span></span> <span data-ttu-id="03e69-124">다음은 규정 준수 센터에 있는 감사 검색 도구의 스크린샷입니다.</span><span class="sxs-lookup"><span data-stu-id="03e69-124">Here's a screenshot of the Audit search tool in the compliance center.</span></span>

   ![Microsoft 365 규정 준수 센터의 감사 로그 검색 도구](../media/AuditLogSearchToolMCC.png)

- <span data-ttu-id="03e69-126">**Search-UnifiedAuditLog cmdlet**.</span><span class="sxs-lookup"><span data-stu-id="03e69-126">**Search-UnifiedAuditLog cmdlet**.</span></span> <span data-ttu-id="03e69-127">Exchange Online PowerShell의 **Search-UnifiedAuditLog** cmdlet(검색 도구의 기본 cmdlet)을 사용하여 감사 이벤트를 검색하거나 스크립트에서 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e69-127">You can also use the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell (the underlying cmdlet for the search tool) to search for audit events or to use in a script.</span></span> <span data-ttu-id="03e69-128">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="03e69-128">For more information, see:</span></span>

  - [<span data-ttu-id="03e69-129">Search-UnifiedAuditLog cmdlet 참조</span><span class="sxs-lookup"><span data-stu-id="03e69-129">Search-UnifiedAuditLog cmdlet reference</span></span>](/powershell/module/exchange/search-unifiedauditlog)
  - [<span data-ttu-id="03e69-130">PowerShell 스크립트를 사용하여 감사 로그 검색</span><span class="sxs-lookup"><span data-stu-id="03e69-130">Use a PowerShell script to search the audit log</span></span>](audit-log-search-script.md)

- <span data-ttu-id="03e69-131">**감사 레코드를 CSV 파일로 내보내기**.</span><span class="sxs-lookup"><span data-stu-id="03e69-131">**Export audit records to a CSV file**.</span></span> <span data-ttu-id="03e69-132">규정 준수 센터에서 감사 로그 검색 도구를 실행한 후 검색에 의해 반환된 감사 레코드를 CSV 파일로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e69-132">After running the Audit log search tool in the compliance center, you can export the audit records returned by the search to a CSV file.</span></span> <span data-ttu-id="03e69-133">이렇게 하면 Microsoft Excel 정렬 및 필터 기능을 여러 감사 레코드 속성에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e69-133">This lets you use Microsoft Excel sort and filter on different audit record properties.</span></span> <span data-ttu-id="03e69-134">Excel 파워 쿼리 변환 기능을 사용하여 AuditData JSON 개체의 각 속성을 자체 열로 분할할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e69-134">You can also use Excel Power Query transform functionality to split each property in the AuditData JSON object into its own column.</span></span> <span data-ttu-id="03e69-135">이렇게 하면 서로 다른 이벤트에 대한 유사한 데이터를 효과적으로 보고 비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e69-135">This lets you effectively view and compare similar data for different events.</span></span> <span data-ttu-id="03e69-136">자세한 내용은 [감사 로그 레코드 내보내기, 구성 및 보기](export-view-audit-log-records.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="03e69-136">For more information, see [Export, configure, and view audit log records](export-view-audit-log-records.md).</span></span>

- <span data-ttu-id="03e69-137">**Office 365 Management Activity API를 통해 감사 로그에 액세스**.</span><span class="sxs-lookup"><span data-stu-id="03e69-137">**Access to audit logs via Office 365 Management Activity API**.</span></span> <span data-ttu-id="03e69-138">감사 레코드를 액세스하고 검색하는 세 번째 방법은 Office 365 Management Activity API를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="03e69-138">A third method for accessing and retrieving audit records is to use the Office 365 Management Activity API.</span></span> <span data-ttu-id="03e69-139">이를 통해 조직은 감사 데이터를 기본 90일보다 오랜 기간 동안 보존하고 감사 데이터를 SIEM 솔루션으로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e69-139">This lets organizations retain auditing data for longer periods than the default 90 days and lets them import their auditing data to a SIEM solution.</span></span> <span data-ttu-id="03e69-140">자세한 내용은 [Office 365 관리 작업 API 참조](/office/office-365-management-api/office-365-management-activity-api-reference)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="03e69-140">For more information, see [Office 365 Management Activity API reference](/office/office-365-management-api/office-365-management-activity-api-reference).</span></span>

- <span data-ttu-id="03e69-141">**90일 감사 로그 보존 기간**.</span><span class="sxs-lookup"><span data-stu-id="03e69-141">**90-day audit log retention**.</span></span> <span data-ttu-id="03e69-142">사용자 또는 관리자가 감사되는 활동을 수행하면 감사 레코드가 생성되어 조직의 감사 로그에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="03e69-142">When an audited activity is performed by a user or admin, an audit record is generated and stored in the audit log for your organization.</span></span> <span data-ttu-id="03e69-143">기본 감사에서 레코드는 90일 동안 유지되므로 지난 3개월 내에 발생한 활동을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e69-143">In Basic Audit, records are retained for 90 days, which means you can search for activities that occurred within the past three months.</span></span>

### <a name="advanced-audit"></a><span data-ttu-id="03e69-144">고급 감사</span><span class="sxs-lookup"><span data-stu-id="03e69-144">Advanced Audit</span></span>

<span data-ttu-id="03e69-145">고급 감사는 감사 로그 보존 정책, 감사 기록의 장기 보존, 고부가가치 중요 이벤트 및 Office 365 Management Activity API에 대한 높은 대역폭 액세스 기능을 제공함으로써 기본 감사 기능을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e69-145">Advanced Audit builds on the capabilities of Basic Audit by providing audit log retention policies, longer retention of audit records, high-value crucial events, and higher bandwidth access to the Office 365 Management Activity API.</span></span>

- <span data-ttu-id="03e69-146">**감사 로그 보존 정책**.</span><span class="sxs-lookup"><span data-stu-id="03e69-146">**Audit log retention policies**.</span></span> <span data-ttu-id="03e69-147">사용자 정의된 감사 로그 보존 정책을 생성하여 감사 레코드를 최대 1년(필요한 추가 기능 라이선스를 가진 사용자의 경우 최대 10년)까지 더 오래 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e69-147">You can create customized audit log retention policies to retain audit records for longer periods of time up to one year (and up to 10 years for users with required add-on license).</span></span> <span data-ttu-id="03e69-148">감사된 활동이 발생하는 서비스, 특정 감사된 활동 또는 감사된 활동을 수행하는 사용자를 기준으로 감사 레코드를 보관하는 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e69-148">You can create a policy to retain audit records based the service where the audited activities occur, specific audited activities, or the user who performs an audited activity.</span></span>

- <span data-ttu-id="03e69-149">**더 길어진 감사 레코드의 보존**</span><span class="sxs-lookup"><span data-stu-id="03e69-149">**Longer retention of audit records**.</span></span> <span data-ttu-id="03e69-150">Exchange, SharePoint 및 Azure Active Directory 감사 레코드는 기본적으로 1년 동안 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="03e69-150">Exchange, SharePoint, and Azure Active Directory audit records are retained for one year by default.</span></span> <span data-ttu-id="03e69-151">다른 모든 활동에 대한 감사 레코드는 기본적으로 90일 동안 보존되거나 감사 로그 보존 정책을 사용하여 더 긴 보존 기간을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e69-151">Audit records for all other activities are retained for 90 days by default, or you can use audit log retention policies to configure longer retention periods.</span></span>

- <span data-ttu-id="03e69-152">**높은 값, 중요한 이벤트**.</span><span class="sxs-lookup"><span data-stu-id="03e69-152">**High-value, crucial events**.</span></span> <span data-ttu-id="03e69-153">중요한 이벤트에 대한 감사 레코드는 메일 항목에 액세스한 시기, 메일 항목에 회신 및 회송된 시기 또는 Exchange Online 및 SharePoint Online에서 사용자가 검색한 시기 및 내용과 같은 이벤트에 대한 가시성을 제공하여 조직이 법의학적 조사 및 규정 준수 조사를 수행하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e69-153">Audit records for crucial events can help your organization conduct forensic and compliance investigations by providing visibility to events such as when mail items were accessed, or when mail items were replied to and forwarded, or when and what a user searched for in Exchange Online and SharePoint Online.</span></span> <span data-ttu-id="03e69-154">이러한 주요 이벤트는 발생 가능성이 있는 위반을 조사하고 손상 범위를 결정 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e69-154">These crucial events can help you investigate possible breaches and determine the scope of compromise.</span></span>

- <span data-ttu-id="03e69-155">**Office 365 관리 활동 API에 대한 고 대역폭**.</span><span class="sxs-lookup"><span data-stu-id="03e69-155">**Higher bandwidth to the Office 365 Management Activity API**.</span></span> <span data-ttu-id="03e69-156">고급 감사는 Office 365 관리 활동 API를 통해 감사 로그에 액세스할 수 있는 더 많은 대역폭을 조직에 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="03e69-156">Advanced Audit provides organizations with more bandwidth to access auditing logs through the Office 365 Management Activity API.</span></span> <span data-ttu-id="03e69-157">기본 감사 또는 고급 감사 기능이 있는 모든 조직에는 처음에는 분당 2,000개의 요청이 할당되지만, 이 제한은 조직의 좌석 수와 라이선스 가입에 따라 동적으로 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="03e69-157">Although all organizations (that have Basic Audit or Advanced Audit) are initially allocated a baseline of 2,000 requests per minute, this limit will dynamically increase depending on an organization's seat count and their licensing subscription.</span></span> <span data-ttu-id="03e69-158">따라서 고급 감사 기능이 있는 조직은 기본 감사 기능이 있는 조직보다 약 두 배 더 많은 대역폭을 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03e69-158">This results in organizations with Advanced Audit getting about twice the bandwidth as organizations with Basic Audit.</span></span>

<span data-ttu-id="03e69-159">고급 감사 기능에 대한 자세한 내용은 [Microsoft 365의 고급 감사](advanced-audit.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="03e69-159">For more detailed information about Advanced Audit features, see [Advanced Audit in Microsoft 365](advanced-audit.md).</span></span>

## <a name="comparison-of-key-capabilities"></a><span data-ttu-id="03e69-160">주요 기능 비교</span><span class="sxs-lookup"><span data-stu-id="03e69-160">Comparison of key capabilities</span></span>

<span data-ttu-id="03e69-161">다음 표에서는 기본 감사와 고급 감사에서 사용할 수 있는 주요 기능을 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="03e69-161">The following table compares the key capabilities available in Basic Audit and Advanced Audit.</span></span> <span data-ttu-id="03e69-162">모든 기본 감사 기능은 고급 감사에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="03e69-162">All Basic Audit functionality is included in Advanced Audit.</span></span>

|<span data-ttu-id="03e69-163">기능</span><span class="sxs-lookup"><span data-stu-id="03e69-163">Capability</span></span>|<span data-ttu-id="03e69-164">기본 감사</span><span class="sxs-lookup"><span data-stu-id="03e69-164">Basic Audit</span></span>|<span data-ttu-id="03e69-165">고급 감사</span><span class="sxs-lookup"><span data-stu-id="03e69-165">Advanced Audit</span></span>|
|:------|:-------------|:-------------|
|<span data-ttu-id="03e69-166">기본적으로 사용</span><span class="sxs-lookup"><span data-stu-id="03e69-166">Enabled by default</span></span>|![지원](../media/check-mark.png)|![지원](../media/check-mark.png)|
|<span data-ttu-id="03e69-169">수천 개의 검색 가능한 감사 이벤트</span><span class="sxs-lookup"><span data-stu-id="03e69-169">Thousands of searchable audit events</span></span>|![지원](../media/check-mark.png)|![지원](../media/check-mark.png)|
|<span data-ttu-id="03e69-172">Microsoft 365 규정 준수 센터의 감사 검색 도구</span><span class="sxs-lookup"><span data-stu-id="03e69-172">Audit search tool in the Microsoft 365 compliance center</span></span>|![지원](../media/check-mark.png)|![지원](../media/check-mark.png)|
|<span data-ttu-id="03e69-175">Search-UnifiedAuditLog cmdlet</span><span class="sxs-lookup"><span data-stu-id="03e69-175">Search-UnifiedAuditLog cmdlet</span></span>|![지원](../media/check-mark.png)|![지원](../media/check-mark.png)|
|<span data-ttu-id="03e69-178">CSV 파일로 감사 레코드 내보내기</span><span class="sxs-lookup"><span data-stu-id="03e69-178">Export audit records to CSV file</span></span>|![지원](../media/check-mark.png)|![지원](../media/check-mark.png)|
|<span data-ttu-id="03e69-181">Office 365 Management Activity API를 통해 감사 로그에 액세스<sup>1</sup>.</span><span class="sxs-lookup"><span data-stu-id="03e69-181">Access to audit logs via Office 365 Management Activity API <sup>1</sup></span></span>|![지원](../media/check-mark.png)|<span data-ttu-id="03e69-183">![지원](../media/check-mark.png)</sup></span><span class="sxs-lookup"><span data-stu-id="03e69-183">![Supported](../media/check-mark.png)</sup></span></span>|
|<span data-ttu-id="03e69-184">90일 감사 로그 보존</span><span class="sxs-lookup"><span data-stu-id="03e69-184">90-day audit log retention</span></span>|![지원](../media/check-mark.png)|![지원](../media/check-mark.png)|
|<span data-ttu-id="03e69-187">1년 감사 로그 보존</span><span class="sxs-lookup"><span data-stu-id="03e69-187">1-year audit log retention</span></span>||![지원](../media/check-mark.png)|
|<span data-ttu-id="03e69-189">10년 감사 로그 보존 기간 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="03e69-189">10-year audit log retention <sup>2</sup></span></span>||![지원](../media/check-mark.png)|
|<span data-ttu-id="03e69-191">로그 보존 정책 감사</span><span class="sxs-lookup"><span data-stu-id="03e69-191">Audit log retention policies</span></span>||![지원](../media/check-mark.png)|
|<span data-ttu-id="03e69-193">가치가 높고 중요한 이벤트</span><span class="sxs-lookup"><span data-stu-id="03e69-193">High-value, crucial events</span></span>||![지원](../media/check-mark.png)|
||||
> [!NOTE]
> <span data-ttu-id="03e69-195"><sup>1</sup> 고급 감사에는 감사 데이터에 대한 더 빠른 액세스를 제공하는 Office 365 관리 활동 API에 대한 더 높은 대역폭 액세스가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="03e69-195"><sup>1</sup> Advanced Audit includes higher bandwidth access to the Office 365 Management Activity API, which provides faster access to audit data.</span></span><br/><span data-ttu-id="03e69-196"><sup>2</sup> 고급 감사에 필요한 라이선스(다음 섹션에서 설명) 외에 감사 레코드를 10년 동안 유지하려면 사용자에게 라이선스에 10년 감사 로그 보존 추가가 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e69-196"><sup>2</sup> In addition to the required licensing for Advanced Audit (described in the next section), a user must be assigned a 10-Year Audit Log Retention add on license to retain their audit records for 10 years.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="03e69-197">라이선스 요구사항</span><span class="sxs-lookup"><span data-stu-id="03e69-197">Licensing requirements</span></span>

<span data-ttu-id="03e69-198">다음 섹션에서는 기본 감사 및 고급 감사에 대한 라이선싱 요구 사항을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="03e69-198">The following sections identify the licensing requirements for Basic Audit and Advanced Audit.</span></span> <span data-ttu-id="03e69-199">기본 감사 기능은 고급 감사에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="03e69-199">Basic Audit functionality is included with Advanced Auditing.</span></span>

### <a name="basic-audit"></a><span data-ttu-id="03e69-200">기본 감사</span><span class="sxs-lookup"><span data-stu-id="03e69-200">Basic Audit</span></span>

- <span data-ttu-id="03e69-201">Microsoft 365 Enterprise E3 구독</span><span class="sxs-lookup"><span data-stu-id="03e69-201">Microsoft 365 Enterprise E3 subscription</span></span>
- <span data-ttu-id="03e69-202">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="03e69-202">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="03e69-203">Microsoft 365 Education A3 구독</span><span class="sxs-lookup"><span data-stu-id="03e69-203">Microsoft 365 Education A3 subscription</span></span>
- <span data-ttu-id="03e69-204">Microsoft 365 Government G3 구독</span><span class="sxs-lookup"><span data-stu-id="03e69-204">Microsoft 365 Government G3 subscription</span></span>
- <span data-ttu-id="03e69-205">Microsoft 365 Government G1 구독</span><span class="sxs-lookup"><span data-stu-id="03e69-205">Microsoft 365 Government G1 subscription</span></span>
- <span data-ttu-id="03e69-206">Office 365 Enterprise E3 구독</span><span class="sxs-lookup"><span data-stu-id="03e69-206">Office 365 Enterprise E3 subscription</span></span>
- <span data-ttu-id="03e69-207">Office 365 Enterprise E1 구독</span><span class="sxs-lookup"><span data-stu-id="03e69-207">Office 365 Enterprise E1 subscription</span></span>
- <span data-ttu-id="03e69-208">Office 365 Education A1 구독</span><span class="sxs-lookup"><span data-stu-id="03e69-208">Office 365 Education A1 subscription</span></span>
- <span data-ttu-id="03e69-209">Office 365 Education A3 구독</span><span class="sxs-lookup"><span data-stu-id="03e69-209">Office 365 Education A3 subscription</span></span>

### <a name="advanced-audit"></a><span data-ttu-id="03e69-210">고급 감사</span><span class="sxs-lookup"><span data-stu-id="03e69-210">Advanced Audit</span></span>

- <span data-ttu-id="03e69-211">Microsoft 365 Enterprise E5 구독</span><span class="sxs-lookup"><span data-stu-id="03e69-211">Microsoft 365 Enterprise E5 subscription</span></span>
- <span data-ttu-id="03e69-212">Microsoft 365 Enterprise E3 구독 + Microsoft 365 E5 규정 준수 추가 기능</span><span class="sxs-lookup"><span data-stu-id="03e69-212">Microsoft 365 Enterprise E3 subscription + the Microsoft 365 E5 Compliance add-on</span></span>
- <span data-ttu-id="03e69-213">Microsoft 365 Enterprise E3 구독 + Microsoft 365 E5 eDiscovery 및 감사 추가 기능</span><span class="sxs-lookup"><span data-stu-id="03e69-213">Microsoft 365 Enterprise E3 subscription + the Microsoft 365 E5 eDiscovery and Audit add-on</span></span>
- <span data-ttu-id="03e69-214">Microsoft 365 Education A5 구독</span><span class="sxs-lookup"><span data-stu-id="03e69-214">Microsoft 365 Education A5 subscription</span></span>
- <span data-ttu-id="03e69-215">Microsoft 365 Education A3 구독 + Microsoft 365 A5 규정 준수 추가 기능</span><span class="sxs-lookup"><span data-stu-id="03e69-215">Microsoft 365 Education A3 subscription + the Microsoft 365 A5 Compliance add-on</span></span>
- <span data-ttu-id="03e69-216">Microsoft 365 Education A3 구독 + Microsoft 365 A5 eDiscovery 및 감사 추가 기능</span><span class="sxs-lookup"><span data-stu-id="03e69-216">Microsoft 365 Education A3 subscription + the Microsoft 365 A5 eDiscovery and Audit add-on</span></span>
- <span data-ttu-id="03e69-217">Microsoft 365 Government G5 구독</span><span class="sxs-lookup"><span data-stu-id="03e69-217">Microsoft 365 Government G5 subscription</span></span>
- <span data-ttu-id="03e69-218">Microsoft 365 Government G5 구독 + Microsoft 365 G5 규정 준수 추가 기능</span><span class="sxs-lookup"><span data-stu-id="03e69-218">Microsoft 365 Government G5 subscription + the Microsoft 365 G5 Compliance add-on</span></span>
- <span data-ttu-id="03e69-219">Microsoft 365 Government G5 구독 + Microsoft 365 G5 eDiscovery 및 감사 추가 기능</span><span class="sxs-lookup"><span data-stu-id="03e69-219">Microsoft 365 Government G5 subscription + the Microsoft 365 G5 eDiscovery and Audit add-on</span></span>
- <span data-ttu-id="03e69-220">Office 365 Enterprise E5 구독</span><span class="sxs-lookup"><span data-stu-id="03e69-220">Office 365 Enterprise E5 subscription</span></span>
- <span data-ttu-id="03e69-221">Office 365 Education A5 구독</span><span class="sxs-lookup"><span data-stu-id="03e69-221">Office 365 Education A5 subscription</span></span>
- <span data-ttu-id="03e69-222">Office 365 Enterprise E3 구독 + Office 365 Advanced Compliance 추가 기능(더 이상 새 구독에는 사용할 수 없음)</span><span class="sxs-lookup"><span data-stu-id="03e69-222">Office 365 Enterprise E3 subscription + the Office 365 Advanced Compliance add-on (no longer available for new subscriptions)</span></span>

## <a name="set-up-microsoft-365-auditing-solutions"></a><span data-ttu-id="03e69-223">Microsoft 365 감사 솔루션 설정</span><span class="sxs-lookup"><span data-stu-id="03e69-223">Set up Microsoft 365 auditing solutions</span></span>

<span data-ttu-id="03e69-224">Microsoft 365의 감사 솔루션 사용을 시작하려면 다음 설정 지침을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="03e69-224">To get started using the auditing solutions in Microsoft 365, see the following setup guidance.</span></span>

### <a name="set-up-basic-audit"></a><span data-ttu-id="03e69-225">기본 감사 설정</span><span class="sxs-lookup"><span data-stu-id="03e69-225">Set up Basic Audit</span></span>

<span data-ttu-id="03e69-226">첫 번째 단계는 기본 감사를 설정한 다음 감사 로그 검색 실행을 시작하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="03e69-226">The first step is to set up Basic Audit and then start running audit log searches.</span></span>

![기본 감사 설정 워크플로](../media/BasicAuditingWorkflow.png)

1. <span data-ttu-id="03e69-228">조직에 기본 감사를 지원하는 구독이 있는지와 해당되는 경우 고급 감사를 지원하는 구독이 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e69-228">Verify that your organization has a subscription that supports Basic Audit and if applicable, a subscription that supports Advanced Audit.</span></span>

2. <span data-ttu-id="03e69-229">Microsoft 365 규정 준수 센터에서 감사 로그 검색 도구를 사용하거나 **Search-UnifiedAuditLog** cmdlet를 사용할 조직의 사용자에게 Exchange Online의 사용 권한을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="03e69-229">Assign permissions in Exchange Online to people in your organization who will use the audit log search tool in the Microsoft 365 compliance center or use the **Search-UnifiedAuditLog** cmdlet.</span></span> <span data-ttu-id="03e69-230">특히, Exchange Online에서 보기 전용 감사 로그 또는 감사 로그 역할이 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e69-230">Specifically, users must be assigned the View-Only Audit Logs or Audit Logs role in Exchange Online.</span></span>

3. <span data-ttu-id="03e69-p116">감사 로그를 검색합니다. 1단계와 2단계를 완료한 후 조직의 사용자는 감사 로그 검색 도구(또는 해당 cmdlet)를 사용하여 감사된 활동을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e69-p116">Search the audit log. After completing step 1 and step 2, users in your organization can use the audit log search tool (or corresponding cmdlet) to search for audited activities.</span></span>

<span data-ttu-id="03e69-233">자세한 지침은 [기본 감사 설정](set-up-basic-audit.md)을 참고하세요.</span><span class="sxs-lookup"><span data-stu-id="03e69-233">For more detailed instructions, see [Set up Basic Audit](set-up-basic-audit.md).</span></span>

### <a name="set-up-advanced-audit"></a><span data-ttu-id="03e69-234">고급 감사 설정</span><span class="sxs-lookup"><span data-stu-id="03e69-234">Set up Advanced Audit</span></span>

<span data-ttu-id="03e69-235">조직에 고급 감사를 지원하는 구독이 있는 경우 다음 단계를 수행하여 고급 감사의 추가 기능을 설정하고 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="03e69-235">If your organization has a subscription that supports Advanced Audit, perform the following steps to set up and use the additional capabilities in Advanced Audit.</span></span>

![고급 감사 설정 워크플로](../media/AdvancedAuditWorkflow.png)

1. <span data-ttu-id="03e69-237">사용자에 대한 고급 감사 설정</span><span class="sxs-lookup"><span data-stu-id="03e69-237">Set up Advanced Audit for users.</span></span> <span data-ttu-id="03e69-238">이 단계는 다음과 같은 작업으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="03e69-238">This step consists of the following tasks:</span></span>

   - <span data-ttu-id="03e69-239">사용자에게 고급 감사에 대한 적절한 라이선스 또는 추가 기능 라이선스가 할당되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="03e69-239">Verifying that users are assigned the appropriate license or add-on license for Advanced Audit.</span></span>
  
   - <span data-ttu-id="03e69-240">해당 사용자에 대해 고급 감사 앱/서비스 계획을 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e69-240">Turning on the Advanced Audit app/service plan must be for those users.</span></span>
  
   - <span data-ttu-id="03e69-241">중요한 이벤트에 대한 감사를 활성화한 다음 해당 사용자에 대해 고급 감사 앱/서비스 계획을 켜면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03e69-241">Enabling the auditing of crucial events and then turning on the Advanced Auditing app/service plan for those users.</span></span>

2. <span data-ttu-id="03e69-242">사용자가 Exchange Online 및 SharePoint Online에서 검색을 수행할 때 중요한 이벤트를 기록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e69-242">Enable crucial events to be logged when users perform searches in Exchange Online and SharePoint Online.</span></span>

3. <span data-ttu-id="03e69-p118">감사 로그 보존 정책을 설정합니다. Exchange, SharePoint 및 Azure AD 감사 레코드를 1년 동안 유지하는 기본 정책에 더해 조직의 보안 작업, IT 및 규정 준수 팀의 요구 사항을 충족하는 추가 감사 로그 보존 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e69-p118">Set up audit log retention policies. In additional to the default policy that retains Exchange, SharePoint, and Azure AD audit records for one year, you can create additional audit log retention policies to meet the requirements of your organization's security operations, IT, and compliance teams.</span></span>

4. <span data-ttu-id="03e69-p119">법의학 조사를 수행할 때 중요한 이벤트 및 기타 활동을 검색합니다. 1단계와 2단계를 완료한 후 손상된 계정 및 기타 유형의 보안 또는 규정 준수 조사를 수행하는 동안 감사 로그를 검색하여 중요한 이벤트 및 기타 활동을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e69-p119">Search for crucial events and other activities when conducting forensic investigations. After completing step 1 and step 2, you can search the audit log for crucial events and other activities during forensic investigations of compromised accounts and other types of security or compliance investigations.</span></span>

<span data-ttu-id="03e69-247">자세한 지침은 [고급 감사 설정](set-up-advanced-audit.md)을 참고하세요.</span><span class="sxs-lookup"><span data-stu-id="03e69-247">For more detailed instructions, see [Set up Advanced Audit](set-up-advanced-audit.md).</span></span>

## <a name="training"></a><span data-ttu-id="03e69-248">교육</span><span class="sxs-lookup"><span data-stu-id="03e69-248">Training</span></span>

<span data-ttu-id="03e69-249">기본 감사 및 고급 감사에서 보안 운영 팀, IT 관리자 및 규정 준수 조사 팀을 교육하면 감사 기능을 사용하여 조사를 보다 신속하게 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e69-249">Training your security operations team, IT administrators, and compliance investigators team in Basic Audit and Advanced Audit can help your organization get started more quickly using auditing to help with your investigations.</span></span> <span data-ttu-id="03e69-250">Microsoft 365는 조직의 이러한 사용자가 감사를 시작하는 데 도움이 되는 다음과 같은 리소스를 제공합니다. [Microsoft 365의 감사 기능에 대해 설명합니다](/learn/modules/describe-audit-capabilities-microsoft-365).</span><span class="sxs-lookup"><span data-stu-id="03e69-250">Microsoft 365 provides the following resource to help these users in your organization getting started with auditing: [Describe the audit capabilities in Microsoft 365](/learn/modules/describe-audit-capabilities-microsoft-365).</span></span>
