---
title: 독립 실행형 EOP에서 관리자 역할 그룹 보고서 실행
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
ms.custom:
- seo-marvel-apr2020
description: 관리자는 독립 실행형 EOP(Exchange Online Protection)에서 관리자 역할 그룹 보고서를 실행하는 방법을 알아보세요. 이 보고서는 관리자가 구성원을 관리자 역할 그룹에 추가하거나 구성원을 제거하는 경우 EOP가 각 작업을 기록합니다.
ms.openlocfilehash: db1934c7865209d358d164ff5165bb23026589cc
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827508"
---
# <a name="run-an-administrator-role-group-report-in-standalone-eop"></a><span data-ttu-id="1e2d6-104">독립 실행형 EOP에서 관리자 역할 그룹 보고서 실행</span><span class="sxs-lookup"><span data-stu-id="1e2d6-104">Run an administrator role group report in standalone EOP</span></span>

<span data-ttu-id="1e2d6-105">Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서 관리자가 구성원을 관리 역할 그룹에 추가하거나 그룹에서 구성원을 제거하면 서비스는 각 작업을 로열합니다.</span><span class="sxs-lookup"><span data-stu-id="1e2d6-105">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, when an admin adds members to or removes members from administrative role groups, the service logs each occurrence.</span></span> <span data-ttu-id="1e2d6-106">독립 실행형 EOP의 역할 그룹에 대한 자세한 내용은 독립 실행형 [EOP의 사용 권한을 참조하십시오.](feature-permissions-in-eop.md)</span><span class="sxs-lookup"><span data-stu-id="1e2d6-106">For more information about role groups in standalone EOP, see [Permissions in standalone EOP](feature-permissions-in-eop.md).</span></span>

<span data-ttu-id="1e2d6-107">EAC(Exchange 관리 센터)에서 관리자 역할 그룹 보고서를 실행하면 항목은 검색 결과로 표시되며 해당하는 역할 그룹, 역할 그룹 구성원을 변경한 사람과 시간, 구성원 업데이트 내용이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e2d6-107">When you run an administrator role group report in the Exchange admin center (EAC), entries are displayed as search results and include the role groups affected, who changed the role group membership and when, and what membership updates were made.</span></span> <span data-ttu-id="1e2d6-108">이 보고서를 사용하여 조직의 사용자에게 할당된 관리 권한의 변경을 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e2d6-108">Use this report to monitor changes to the administrative permissions assigned to users in your organization.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1e2d6-109">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="1e2d6-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="1e2d6-110">Exchange 관리 센터를 열려면 독립 실행형 [EOP의 Exchange 관리 센터를 참조하십시오.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="1e2d6-110">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="1e2d6-111">이 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e2d6-111">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="1e2d6-112">특히 ComplianceManagement, OrganizationManagement(전역 관리자) 및 SecurityAdministrator 역할 그룹에 할당된 감사 로그 또는 보기 전용 감사 로그 역할이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1e2d6-112">Specifically, you need the Audit Logs or View-Only Audit Logs role, which are assigned to the ComplianceManagement, OrganizationManagement (global admins), and SecurityAdministrator role groups by default.</span></span> <span data-ttu-id="1e2d6-113">자세한 내용은 독립 [실행형 EOP의 사용 권한을 참조하고](feature-permissions-in-eop.md) [EAC를 사용하여 역할 그룹의 구성원 목록을 수정합니다.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)</span><span class="sxs-lookup"><span data-stu-id="1e2d6-113">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="1e2d6-114">이 항목의 절차에 적용할 수 있는 바로 가기 키에 대한 자세한 내용은 [Exchange Online에서 Exchange 관리 센터에 대 한 바로 가기 키를 참조 하십시오.](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)</span><span class="sxs-lookup"><span data-stu-id="1e2d6-114">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="1e2d6-115">문제가 있나요?</span><span class="sxs-lookup"><span data-stu-id="1e2d6-115">Having problems?</span></span> <span data-ttu-id="1e2d6-116">[Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) 포럼에서 도움을 요청하세요.</span><span class="sxs-lookup"><span data-stu-id="1e2d6-116">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a><span data-ttu-id="1e2d6-117">EAC를 사용하여 관리자 역할 그룹 보고서 실행</span><span class="sxs-lookup"><span data-stu-id="1e2d6-117">Use the EAC to run an administrator role group report</span></span>

<span data-ttu-id="1e2d6-118">관리자 역할 그룹 보고서를 실행하면 특정 시간 내 조직의 관리 역할 그룹 변경 내용을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e2d6-118">Run the administrator role group report to find the changes to management role groups in your organization within a particular time frame.</span></span>

1. <span data-ttu-id="1e2d6-119">EAC에서 준수 관리 **감사로** \> **이동한 후**관리자 역할 그룹 보고서 **실행을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1e2d6-119">In the EAC, go to **Compliance management** \> **Auditing**, and then choose **Run an administrator role group report**.</span></span>

2. <span data-ttu-id="1e2d6-120">**열리는 관리자 역할 그룹 의 변경 내용** 검색 페이지에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="1e2d6-120">In the **Search for changes to administrator role groups** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="1e2d6-121">**시작 날짜** 및 **종료 날짜:** 날짜 범위를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1e2d6-121">**Start date** and **End date**: Enter a date range.</span></span> <span data-ttu-id="1e2d6-122">기본적으로 보고서는 지난 2주 동안의 관리자 역할 그룹 변경 내용을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="1e2d6-122">By default, the report searches for changes made to administrator role groups in the past two weeks.</span></span>

   - <span data-ttu-id="1e2d6-123">**역할 그룹 선택:** 기본적으로 모든 역할 그룹이 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e2d6-123">**Select role groups**: By default, all role groups are searched.</span></span> <span data-ttu-id="1e2d6-124">특정 역할 그룹별로 결과를 필터링하려면 역할 그룹 **Select를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="1e2d6-124">To filter the results by specific role groups, click **Select role groups**.</span></span> <span data-ttu-id="1e2d6-125">나타나는 대화 상자에서 역할 그룹을 선택한 다음 추가 \*\*-mpa->. \*\*</span><span class="sxs-lookup"><span data-stu-id="1e2d6-125">In the dialog that appears, select a role group and click **add ->**.</span></span> <span data-ttu-id="1e2d6-126">필요한 만큼 이 단계를 반복한 다음 **완료되면** 확인을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1e2d6-126">Repeat this step as many times as necessary, and then click **OK** when you're finished.</span></span>

3. <span data-ttu-id="1e2d6-127">**검색**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1e2d6-127">When you're finished, click **Search**.</span></span>

<span data-ttu-id="1e2d6-p108">지정한 조건을 사용하여 찾은 변경 내용은 결과 창에 표시됩니다. 검색 결과에서 역할 그룹을 클릭하여 세부 정보 창에서 변경 내용을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1e2d6-p108">If any changes are found using the criteria you specified, they will appear in the results pane. Click a role group in the search results to see the changes in the details pane.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="1e2d6-130">작동 여부는 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="1e2d6-130">How do you know this worked?</span></span>

<span data-ttu-id="1e2d6-p109">관리자 역할 그룹 보고서를 성공적으로 실행한 경우 날짜 범위 내에서 변경된 역할 그룹은 검색 결과 창에 표시됩니다. 결과가 표시되지 않으면 지정된 날짜 범위 내에서 역할 그룹이 변경되지 않은 것입니다. 표시할 결과가 있다고 생각되면 날짜 범위를 변경한 다음 보고서를 다시 실행하십시오.</span><span class="sxs-lookup"><span data-stu-id="1e2d6-p109">If you've successfully run an administrator role group report, role groups that have been changed within the date range are displayed in the search results pane. If there are no results, then no changes to role groups have taken place within the specified date range. If you think there should be results, change the date range and then run the report again.</span></span>

## <a name="monitor-changes-to-role-group-membership"></a><span data-ttu-id="1e2d6-134">역할 그룹 구성원의 변경 모니터링</span><span class="sxs-lookup"><span data-stu-id="1e2d6-134">Monitor changes to role group membership</span></span>

<span data-ttu-id="1e2d6-p110">구성원이 역할 그룹에서 추가되거나 제거되면 세부 정보 창에 표시되는 검색 결과에서 역할 그룹 구성원이 업데이트되었음이 표시되고 현재 구성원이 표시됩니다. 이 결과에서는 추가되거나 제거된 사용자가 명시적으로 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1e2d6-p110">When members are added to or removed from a role group, the search results displayed in the details pane indicate that the role group membership was updated and lists the current members. The results don't explicitly state which user was added or removed.</span></span>

<span data-ttu-id="1e2d6-p111">사용자가 추가되었거나 제거되었는지 확인하려면 보고서에서 두 가지 항목을 비교해야 합니다. 예를 들어 **HelpDesk** 역할 그룹에 대한 다음 로그 항목을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="1e2d6-p111">To determine if a user was added or removed, you have to compare two separate entries in the report. For example, let's look at the following log entries for the **HelpDesk** role group:</span></span>

> <span data-ttu-id="1e2d6-139">1/27/2018 4:43 PM</span><span class="sxs-lookup"><span data-stu-id="1e2d6-139">1/27/2018 4:43 PM</span></span> <br> <span data-ttu-id="1e2d6-140">관리자</span><span class="sxs-lookup"><span data-stu-id="1e2d6-140">Administrator</span></span> <br> <span data-ttu-id="1e2d6-141">업데이트된 구성원: Administrator;annb,florencef;pilarp</span><span class="sxs-lookup"><span data-stu-id="1e2d6-141">Updated members: Administrator;annb,florencef;pilarp</span></span> <br> <span data-ttu-id="1e2d6-142">2/06/2018 오전 10:09 AM</span><span class="sxs-lookup"><span data-stu-id="1e2d6-142">2/06/2018 10:09 AM</span></span> <br> <span data-ttu-id="1e2d6-143">관리자</span><span class="sxs-lookup"><span data-stu-id="1e2d6-143">Administrator</span></span> <br> <span data-ttu-id="1e2d6-144">업데이트된 구성원: Administrator;annb;florencef;pilarp;tonip</span><span class="sxs-lookup"><span data-stu-id="1e2d6-144">Updated members: Administrator;annb;florencef;pilarp;tonip</span></span> <br> <span data-ttu-id="1e2d6-145">2018/2/19 오전 2시 12분</span><span class="sxs-lookup"><span data-stu-id="1e2d6-145">2/19/2018 2:12 PM</span></span> <br> <span data-ttu-id="1e2d6-146">관리자</span><span class="sxs-lookup"><span data-stu-id="1e2d6-146">Administrator</span></span> <br> <span data-ttu-id="1e2d6-147">업데이트된 구성원: Administrator;annb;florencef;tonip</span><span class="sxs-lookup"><span data-stu-id="1e2d6-147">Updated members: Administrator;annb;florencef;tonip</span></span>

<span data-ttu-id="1e2d6-148">이 예에서 관리자 사용자 계정은 다음과 같이 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1e2d6-148">In this example, the Administrator user account made the following changes:</span></span>

- <span data-ttu-id="1e2d6-149">2018년 2월 6일에 사용자 tonip을 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="1e2d6-149">On 2/06/2018, they added the user tonip.</span></span>

- <span data-ttu-id="1e2d6-150">2018년 2월 19일에 사용자 pilarp를 제거했습니다.</span><span class="sxs-lookup"><span data-stu-id="1e2d6-150">On 2/19/2018, they removed the user pilarp.</span></span>

## <a name="use-standalone-exchange-online-powershell-to-search-for-audit-log-entries"></a><span data-ttu-id="1e2d6-151">독립 실행형 Exchange Online PowerShell을 사용하여 감사 로그 항목 검색</span><span class="sxs-lookup"><span data-stu-id="1e2d6-151">Use standalone Exchange Online PowerShell to search for audit log entries</span></span>

<span data-ttu-id="1e2d6-152">Exchange Online PowerShell을 사용하여 지정하는 기준을 충족하는 감사 로그 항목을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e2d6-152">You can use Exchange Online PowerShell to search for audit log entries that meet the criteria you specify.</span></span> <span data-ttu-id="1e2d6-153">검색 조건 목록은 [Search-AdminAuditLog 검색 조건을 참조하십시오.](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet)</span><span class="sxs-lookup"><span data-stu-id="1e2d6-153">For a list of search criteria, see [Search-AdminAuditLog search criteria](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet).</span></span> <span data-ttu-id="1e2d6-154">이 절차에서는 **Search-AdminAuditLog cmdlet을** 사용하고 Exchange Online PowerShell의 검색 결과를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="1e2d6-154">This procedure uses the **Search-AdminAuditLog** cmdlet and displays search results in Exchange Online PowerShell.</span></span> <span data-ttu-id="1e2d6-155">이 cmdlet은 **New-AdminAuditLogSearch** cmdlet 또는 EAC 감사 보고 보고서에 정의된 제한을 초과하는 결과를 반환해야 할 경우에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e2d6-155">You can use this cmdlet when you need to return a set of results that exceeds the limits defined on the **New-AdminAuditLogSearch** cmdlet or in the EAC Audit Reporting reports.</span></span>

<span data-ttu-id="1e2d6-156">지정한 기준을 충족하는 감사 로그를 검색하려면 다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1e2d6-156">To search the audit log for criteria you specify, use the following syntax.</span></span>

```PowerShell
Search-AdminAuditLog - Cmdlets <cmdlet 1, cmdlet 2, ...> -Parameters <parameter 1, parameter 2, ...> -StartDate <start date> -EndDate <end date> -UserIds <user IDs> -ObjectIds <object IDs> -IsSuccess <$True | $False >
```

> [!NOTE]
> <span data-ttu-id="1e2d6-157">**Search-AdminAuditLog** cmdlet은 기본적으로 최대 1,000개의 로그 항목을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1e2d6-157">The **Search-AdminAuditLog** cmdlet returns a maximum of 1,000 log entries by default.</span></span> <span data-ttu-id="1e2d6-158">_ResultSize 매개 변수를_ 사용하여 최대 250,000개의 로그 항목을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e2d6-158">Use the _ResultSize_ parameter to specify up to 250,000 log entries.</span></span> <span data-ttu-id="1e2d6-159">또는 이 값을 사용하여 모든 `Unlimited` 항목을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e2d6-159">Or, use the value `Unlimited` to return all entries.</span></span>

<span data-ttu-id="1e2d6-160">이 예에서는 다음 기준을 사용하여 모든 감사 로그 항목을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="1e2d6-160">This example performs a search for all audit log entries with the following criteria:</span></span>

- <span data-ttu-id="1e2d6-161">**시작 날짜:** 2018년 8월 4일</span><span class="sxs-lookup"><span data-stu-id="1e2d6-161">**Start date**: 08/04/2018</span></span>

- <span data-ttu-id="1e2d6-162">**종료 날짜:** 2018년 10월 10일</span><span class="sxs-lookup"><span data-stu-id="1e2d6-162">**End date**: 10/03/2018</span></span>

- <span data-ttu-id="1e2d6-163">**사용자 ID**: davids, chrisd, kima</span><span class="sxs-lookup"><span data-stu-id="1e2d6-163">**User IDs**: davids, chrisd, kima</span></span>

- <span data-ttu-id="1e2d6-164">**Cmdlet:** **Set-Mailbox**</span><span class="sxs-lookup"><span data-stu-id="1e2d6-164">**Cmdlets**: **Set-Mailbox**</span></span>

- <span data-ttu-id="1e2d6-165">**매개 변수**: _ProhibitSendQuota,_ _ProhibitSendReceiveQuota,_ _IssueWarningQuota,_ _MaxSendSize,_ _MaxReceiveSize_</span><span class="sxs-lookup"><span data-stu-id="1e2d6-165">**Parameters**: _ProhibitSendQuota_, _ProhibitSendReceiveQuota_, _IssueWarningQuota_, _MaxSendSize_, _MaxReceiveSize_</span></span>

```PowerShell
Search-AdminAuditLog -Cmdlets Set-Mailbox -Parameters ProhibitSendQuota,ProhibitSendReceiveQuota,IssueWarningQuota,MaxSendSize,MaxReceiveSize -StartDate 08/04/2018 -EndDate 10/03/2018 -UserIds davids,chrisd,kima
```

<span data-ttu-id="1e2d6-p114">이 예에서는 특정 사서함에 대한 변경 내용을 검색합니다. 문제를 해결하거나 조사에 필요한 정보를 제공해야 할 경우에 유용합니다. 다음과 같은 기준이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e2d6-p114">This example searches for changes made to a specific mailbox. This is useful if you're troubleshooting or you need to provide information for an investigation. The following criteria are used:</span></span>

- <span data-ttu-id="1e2d6-169">**시작 날짜:** 05/01/2018</span><span class="sxs-lookup"><span data-stu-id="1e2d6-169">**Start date**: 05/01/2018</span></span>

- <span data-ttu-id="1e2d6-170">**종료 날짜:** 2018년 10월 10일</span><span class="sxs-lookup"><span data-stu-id="1e2d6-170">**End date**: 10/03/2018</span></span>

- <span data-ttu-id="1e2d6-171">**개체 ID**: contoso.com/Users/DavidS</span><span class="sxs-lookup"><span data-stu-id="1e2d6-171">**Object ID**: contoso.com/Users/DavidS</span></span>

```PowerShell
Search-AdminAuditLog -StartDate 05/01/2018 -EndDate 10/03/2018 -ObjectID contoso.com/Users/DavidS
```

<span data-ttu-id="1e2d6-172">검색 결과 여러 로그 항목이 반환될 경우 Exchange Online PowerShell을 사용하여 감사 로그 항목을 검색하고 결과를 받는 사람에게 이 항목의 **뒷부분에 있는 받는 사람에게** 전송하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1e2d6-172">If your searches return many log entries, we recommend that you use the procedure provided in **Use Exchange Online PowerShell to search for audit log entries and send results to a recipient** later in this topic.</span></span> <span data-ttu-id="1e2d6-173">해당 섹션의 절차는 지정한 받는 사람에게 XML 파일을 전자 메일 첨부 파일로 전송하므로 관심 있는 데이터를 더 쉽게 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e2d6-173">The procedure in that section sends an XML file as an email attachment to the recipients you specify, enabling you to more easily extract the data you're interested in.</span></span>

<span data-ttu-id="1e2d6-174">구문과 매개 변수에 대한 자세한 내용은 [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1e2d6-174">For detailed syntax and parameter information, see [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).</span></span>

### <a name="view-details-of-audit-log-entries"></a><span data-ttu-id="1e2d6-175">감사 로그 항목의 상세 정보 보기</span><span class="sxs-lookup"><span data-stu-id="1e2d6-175">View details of audit log entries</span></span>

<span data-ttu-id="1e2d6-176">**Search-AdminAuditLog** cmdlet은 감사 로그 콘텐츠에 설명된 [필드를 반환합니다.](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents)</span><span class="sxs-lookup"><span data-stu-id="1e2d6-176">The **Search-AdminAuditLog** cmdlet returns the fields described in [Audit log contents](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents).</span></span> <span data-ttu-id="1e2d6-177">cmdlet에 의해 반환된 필드 중에서 **CmdletParameters** 및 **ModifiedProperties** 의 두 필드에는 기본적으로 볼 수 없는 추가 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e2d6-177">Of the fields returned by the cmdlet, two fields, **CmdletParameters** and **ModifiedProperties**, contain additional information that isn't viewable by default.</span></span>

<span data-ttu-id="1e2d6-178">**CmdletParameters** 및 **ModifiedProperties** 필드의 콘텐츠를 보려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="1e2d6-178">To view the contents of the **CmdletParameters** and **ModifiedProperties** fields, use the following steps.</span></span> <span data-ttu-id="1e2d6-179">또는 **Exchange Online PowerShell을** 사용하 며 이 항목의 뒷부분에 있는 받는 사람에게 결과를 전송하여 XML 파일을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e2d6-179">Or, you can use the procedure in **Use Exchange Online PowerShell to search for audit log entries and send results to a recipient** later in this topic to create an XML file.</span></span>

<span data-ttu-id="1e2d6-180">이 절차에서는 다음 개념을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1e2d6-180">This procedure uses the following concepts:</span></span>

- [<span data-ttu-id="1e2d6-181">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="1e2d6-181">about_Arrays</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_arrays)

- [<span data-ttu-id="1e2d6-182">about_Variables</span><span class="sxs-lookup"><span data-stu-id="1e2d6-182">about_Variables</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_variables)

1. <span data-ttu-id="1e2d6-183">검색할 기준을 정하고 **Search-AdminAuditLog** cmdlet을 실행한 후 다음 명령을 사용하여 변수에 결과를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="1e2d6-183">Decide the criteria you want to search for, run the **Search-AdminAuditLog** cmdlet, and store the results in a variable using the following command.</span></span>

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. <span data-ttu-id="1e2d6-184">각 감사 로그 항목은 변수에 배열 요소로 `$Results` 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e2d6-184">Each audit log entry is stored as an array element in the variable `$Results`.</span></span> <span data-ttu-id="1e2d6-185">배열 요소 인덱스를 지정하여 배열 요소를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e2d6-185">You can select an array element by specifying its array element index.</span></span> <span data-ttu-id="1e2d6-186">배열 요소 인덱스는 첫 번째 배열 요소에 대해 0에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="1e2d6-186">Array element indexes start at zero (0) for the first array element.</span></span> <span data-ttu-id="1e2d6-187">예를 들어, 인덱스가 4인 5번째 배열 요소를 검색하려면 다음 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1e2d6-187">For example, to retrieve the 5th array element, which has an index of 4, use the following command.</span></span>

    ```PowerShell
    $Results[4]
    ```

3. <span data-ttu-id="1e2d6-p119">이전 명령이 배열 요소 4에 저장된 로그 항목을 반환합니다. 이 로그 항목의 **CmdletParameters** 및 **ModifiedProperties** 필드의 콘텐츠를 보려면 다음 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1e2d6-p119">The previous command returns the log entry stored in array element 4. To see the contents of the **CmdletParameters** and **ModifiedProperties** fields for this log entry, use the following commands.</span></span>

    ```PowerShell
    $Results[4].CmdletParameters
    $Results[4].ModifiedProperties
    ```

4. <span data-ttu-id="1e2d6-190">다른 로그 항목의 **CmdletParameters** 또는 **ModifiedParameters** 필드의 콘텐츠를 보려면 배열 요소 인덱스를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="1e2d6-190">To view the contents of the **CmdletParameters** or **ModifiedParameters** fields in another log entry, change the array element index.</span></span>
