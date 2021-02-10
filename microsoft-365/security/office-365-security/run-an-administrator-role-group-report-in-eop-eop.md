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
localization_priority: Normal
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
ms.custom:
- seo-marvel-apr2020
description: 관리자는 독립 실행형 EOP(Exchange Online Protection)에서 관리자 역할 그룹 보고서를 실행하는 방법을 배울 수 있습니다. 이 보고서는 관리자가 구성원을 관리자 역할 그룹에 추가하거나 관리자 역할 그룹에 구성원을 제거할 때 기록됩니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 507fbe6fb6c99677cf91b6eb824bf110f1c826f3
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166630"
---
# <a name="run-an-administrator-role-group-report-in-standalone-eop"></a><span data-ttu-id="84a35-104">독립 실행형 EOP에서 관리자 역할 그룹 보고서 실행</span><span class="sxs-lookup"><span data-stu-id="84a35-104">Run an administrator role group report in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="84a35-105">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="84a35-105">**Applies to**</span></span>
-  [<span data-ttu-id="84a35-106">Exchange Online Protection 독립 실행형</span><span class="sxs-lookup"><span data-stu-id="84a35-106">Exchange Online Protection standalone</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)

<span data-ttu-id="84a35-107">Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서는 관리자가 관리 역할 그룹에 구성원을 추가하거나 관리 역할 그룹에서 구성원을 제거하면 서비스가 각 발생을 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="84a35-107">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, when an admin adds members to or removes members from administrative role groups, the service logs each occurrence.</span></span> <span data-ttu-id="84a35-108">독립 실행형 EOP의 역할 그룹에 대한 자세한 내용은 독립 실행형 [EOP의 사용 권한을 참조하세요.](feature-permissions-in-eop.md)</span><span class="sxs-lookup"><span data-stu-id="84a35-108">For more information about role groups in standalone EOP, see [Permissions in standalone EOP](feature-permissions-in-eop.md).</span></span>

<span data-ttu-id="84a35-109">EAC(Exchange 관리 센터)에서 관리자 역할 그룹 보고서를 실행하면 항목이 검색 결과로 표시되고 영향을 받는 역할 그룹, 역할 그룹 구성원을 변경한 사용자 및 언제, 구성원 업데이트가 적용된지가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="84a35-109">When you run an administrator role group report in the Exchange admin center (EAC), entries are displayed as search results and include the role groups affected, who changed the role group membership and when, and what membership updates were made.</span></span> <span data-ttu-id="84a35-110">이 보고서를 사용하여 조직의 사용자에게 할당된 관리 권한의 변경을 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84a35-110">Use this report to monitor changes to the administrative permissions assigned to users in your organization.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="84a35-111">시작하기 전에 알아야 할 사항은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="84a35-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="84a35-112">Exchange 관리 센터를 열하려면 독립 실행형 [EOP에서 Exchange 관리 센터를 참조하세요.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="84a35-112">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="84a35-113">이 문서의 절차를 수행하려면 먼저 Exchange Online Protection에서 사용 권한을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84a35-113">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="84a35-114">특히 조직 관리, 준수 관리 및 보안 관리자 역할 그룹에 기본적으로 할당되는 감사 로그 또는 보기 전용 감사 로그 역할이 필요합니다.   </span><span class="sxs-lookup"><span data-stu-id="84a35-114">Specifically, you need the **Audit Logs** or **View-Only Audit Logs** role, which are assigned to the **Organization Management**, **Compliance Management**, and **Security Administrator** role groups by default.</span></span> <span data-ttu-id="84a35-115">자세한 내용은 독립 실행형 [EOP의](feature-permissions-in-eop.md) 사용 권한을 참조하고 EAC를 사용하여 역할 그룹의 구성원 목록을 [수정합니다.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)</span><span class="sxs-lookup"><span data-stu-id="84a35-115">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="84a35-116">이 문서의 절차에 적용할 수 있는 바로 가기 키에 대한 자세한 내용은 [Exchange Online의 Exchange](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)관리 센터에 대한 바로 가기 키를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="84a35-116">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="84a35-117">문제가 있나요?</span><span class="sxs-lookup"><span data-stu-id="84a35-117">Having problems?</span></span> <span data-ttu-id="84a35-118">[Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) 포럼에서 도움을 요청하세요.</span><span class="sxs-lookup"><span data-stu-id="84a35-118">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a><span data-ttu-id="84a35-119">EAC를 사용하여 관리자 역할 그룹 보고서 실행</span><span class="sxs-lookup"><span data-stu-id="84a35-119">Use the EAC to run an administrator role group report</span></span>

<span data-ttu-id="84a35-120">관리자 역할 그룹 보고서를 실행하여 특정 기간 내에 관리 역할 그룹에 대한 변경 내용을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84a35-120">Run the administrator role group report to find the changes to management role groups within a particular time frame.</span></span>

1. <span data-ttu-id="84a35-121">EAC에서 준수 관리  감사로 이동한 다음 관리자 역할 그룹 보고서 \>  **실행을 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="84a35-121">In the EAC, go to **Compliance management** \> **Auditing**, and then choose **Run an administrator role group report**.</span></span>

2. <span data-ttu-id="84a35-122">관리자 **역할 그룹** 변경 내용 검색 페이지가 열리면 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="84a35-122">In the **Search for changes to administrator role groups** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="84a35-123">**시작 날짜** 및 **종료 날짜:** 날짜 범위를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="84a35-123">**Start date** and **End date**: Enter a date range.</span></span> <span data-ttu-id="84a35-124">기본적으로 보고서는 지난 2주 동안의 관리자 역할 그룹 변경 내용을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="84a35-124">By default, the report searches for changes made to administrator role groups in the past two weeks.</span></span>

   - <span data-ttu-id="84a35-125">**역할 그룹 선택:** 기본적으로 모든 역할 그룹이 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="84a35-125">**Select role groups**: By default, all role groups are searched.</span></span> <span data-ttu-id="84a35-126">특정 역할 그룹으로 결과를 필터링하려면 역할 그룹 **선택을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="84a35-126">To filter the results by specific role groups, click **Select role groups**.</span></span> <span data-ttu-id="84a35-127">나타나는 대화 상자에서 역할 그룹을 선택하고 **->.**</span><span class="sxs-lookup"><span data-stu-id="84a35-127">In the dialog that appears, select a role group and click **add ->**.</span></span> <span data-ttu-id="84a35-128">이 단계를 필요한 수만큼 반복하고 완료되면 **확인을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="84a35-128">Repeat this step as many times as necessary, and then click **OK** when you're finished.</span></span>

3. <span data-ttu-id="84a35-129">완료되면 검색을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="84a35-129">When you're finished, click **Search**.</span></span>

<span data-ttu-id="84a35-p108">지정한 조건을 사용하여 찾은 변경 내용은 결과 창에 표시됩니다. 검색 결과에서 역할 그룹을 클릭하여 세부 정보 창에서 변경 내용을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="84a35-p108">If any changes are found using the criteria you specified, they will appear in the results pane. Click a role group in the search results to see the changes in the details pane.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="84a35-132">작동 여부는 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="84a35-132">How do you know this worked?</span></span>

<span data-ttu-id="84a35-p109">관리자 역할 그룹 보고서를 성공적으로 실행한 경우 날짜 범위 내에서 변경된 역할 그룹은 검색 결과 창에 표시됩니다. 결과가 표시되지 않으면 지정된 날짜 범위 내에서 역할 그룹이 변경되지 않은 것입니다. 표시할 결과가 있다고 생각되면 날짜 범위를 변경한 다음 보고서를 다시 실행하십시오.</span><span class="sxs-lookup"><span data-stu-id="84a35-p109">If you've successfully run an administrator role group report, role groups that have been changed within the date range are displayed in the search results pane. If there are no results, then no changes to role groups have taken place within the specified date range. If you think there should be results, change the date range and then run the report again.</span></span>

## <a name="monitor-changes-to-role-group-membership"></a><span data-ttu-id="84a35-136">역할 그룹 구성원의 변경 모니터링</span><span class="sxs-lookup"><span data-stu-id="84a35-136">Monitor changes to role group membership</span></span>

<span data-ttu-id="84a35-p110">구성원이 역할 그룹에서 추가되거나 제거되면 세부 정보 창에 표시되는 검색 결과에서 역할 그룹 구성원이 업데이트되었음이 표시되고 현재 구성원이 표시됩니다. 이 결과에서는 추가되거나 제거된 사용자가 명시적으로 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84a35-p110">When members are added to or removed from a role group, the search results displayed in the details pane indicate that the role group membership was updated and lists the current members. The results don't explicitly state which user was added or removed.</span></span>

<span data-ttu-id="84a35-p111">사용자가 추가되었거나 제거되었는지 확인하려면 보고서에서 두 가지 항목을 비교해야 합니다. 예를 들어 **HelpDesk** 역할 그룹에 대한 다음 로그 항목을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="84a35-p111">To determine if a user was added or removed, you have to compare two separate entries in the report. For example, let's look at the following log entries for the **HelpDesk** role group:</span></span>

> <span data-ttu-id="84a35-141">2018/1/27 오후 4:43</span><span class="sxs-lookup"><span data-stu-id="84a35-141">1/27/2018 4:43 PM</span></span> <br> <span data-ttu-id="84a35-142">관리자</span><span class="sxs-lookup"><span data-stu-id="84a35-142">Administrator</span></span> <br> <span data-ttu-id="84a35-143">업데이트된 구성원: Administrator;annb,florencef;pilarp</span><span class="sxs-lookup"><span data-stu-id="84a35-143">Updated members: Administrator;annb,florencef;pilarp</span></span> <br> <span data-ttu-id="84a35-144">2/06/2018 10:09 AM</span><span class="sxs-lookup"><span data-stu-id="84a35-144">2/06/2018 10:09 AM</span></span> <br> <span data-ttu-id="84a35-145">관리자</span><span class="sxs-lookup"><span data-stu-id="84a35-145">Administrator</span></span> <br> <span data-ttu-id="84a35-146">업데이트된 구성원: Administrator;annb;florencef;pilarp;tonip</span><span class="sxs-lookup"><span data-stu-id="84a35-146">Updated members: Administrator;annb;florencef;pilarp;tonip</span></span> <br> <span data-ttu-id="84a35-147">2018/2/19 오후 2:12</span><span class="sxs-lookup"><span data-stu-id="84a35-147">2/19/2018 2:12 PM</span></span> <br> <span data-ttu-id="84a35-148">관리자</span><span class="sxs-lookup"><span data-stu-id="84a35-148">Administrator</span></span> <br> <span data-ttu-id="84a35-149">업데이트된 구성원: Administrator;annb;florencef;tonip</span><span class="sxs-lookup"><span data-stu-id="84a35-149">Updated members: Administrator;annb;florencef;tonip</span></span>

<span data-ttu-id="84a35-150">이 예에서 관리자 사용자 계정은 다음과 같이 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="84a35-150">In this example, the Administrator user account made the following changes:</span></span>

- <span data-ttu-id="84a35-151">2018년 2월 6일에는 사용자 tonip을 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="84a35-151">On 2/06/2018, they added the user tonip.</span></span>
- <span data-ttu-id="84a35-152">2018년 2월 19일에는 사용자 pilarp를 제거했습니다.</span><span class="sxs-lookup"><span data-stu-id="84a35-152">On 2/19/2018, they removed the user pilarp.</span></span>

## <a name="use-standalone-exchange-online-powershell-to-search-for-audit-log-entries"></a><span data-ttu-id="84a35-153">독립 실행형 Exchange Online PowerShell을 사용하여 감사 로그 항목 검색</span><span class="sxs-lookup"><span data-stu-id="84a35-153">Use standalone Exchange Online PowerShell to search for audit log entries</span></span>

<span data-ttu-id="84a35-154">Exchange Online PowerShell을 사용하여 지정한 기준을 충족하는 감사 로그 항목을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84a35-154">You can use Exchange Online PowerShell to search for audit log entries that meet the criteria you specify.</span></span> <span data-ttu-id="84a35-155">검색 조건 목록은 [Search-AdminAuditLog](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet)검색 조건을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="84a35-155">For a list of search criteria, see [Search-AdminAuditLog search criteria](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet).</span></span> <span data-ttu-id="84a35-156">이 절차에서는 **Search-AdminAuditLog** cmdlet을 사용하여 Exchange Online PowerShell에 검색 결과를 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="84a35-156">This procedure uses the **Search-AdminAuditLog** cmdlet and displays search results in Exchange Online PowerShell.</span></span> <span data-ttu-id="84a35-157">이 cmdlet은 **New-AdminAuditLogSearch** cmdlet 또는 EAC 감사 보고 보고서에 정의된 제한을 초과하는 결과를 반환해야 할 경우에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84a35-157">You can use this cmdlet when you need to return a set of results that exceeds the limits defined on the **New-AdminAuditLogSearch** cmdlet or in the EAC Audit Reporting reports.</span></span>

<span data-ttu-id="84a35-158">지정한 기준을 충족하는 감사 로그를 검색하려면 다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="84a35-158">To search the audit log for criteria you specify, use the following syntax.</span></span>

```PowerShell
Search-AdminAuditLog - Cmdlets <cmdlet 1, cmdlet 2, ...> -Parameters <parameter 1, parameter 2, ...> -StartDate <start date> -EndDate <end date> -UserIds <user IDs> -ObjectIds <object IDs> -IsSuccess <$True | $False >
```

> [!NOTE]
> <span data-ttu-id="84a35-159">**Search-AdminAuditLog** cmdlet은 기본적으로 최대 1,000개의 로그 항목을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="84a35-159">The **Search-AdminAuditLog** cmdlet returns a maximum of 1,000 log entries by default.</span></span> <span data-ttu-id="84a35-160">_ResultSize_ 매개 변수를 사용하여 최대 250,000개 로그 항목을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="84a35-160">Use the _ResultSize_ parameter to specify up to 250,000 log entries.</span></span> <span data-ttu-id="84a35-161">또는 값을 사용하여 모든 `Unlimited` 항목을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="84a35-161">Or, use the value `Unlimited` to return all entries.</span></span>

<span data-ttu-id="84a35-162">이 예에서는 다음 기준을 사용하여 모든 감사 로그 항목을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="84a35-162">This example performs a search for all audit log entries with the following criteria:</span></span>

- <span data-ttu-id="84a35-163">**시작 날짜**: 2018/08/04</span><span class="sxs-lookup"><span data-stu-id="84a35-163">**Start date**: 08/04/2018</span></span>
- <span data-ttu-id="84a35-164">**종료 날짜**: 2018년 10월 3일</span><span class="sxs-lookup"><span data-stu-id="84a35-164">**End date**: 10/03/2018</span></span>
- <span data-ttu-id="84a35-165">**사용자 ID**: `davids` , `chrisd` , `kima`</span><span class="sxs-lookup"><span data-stu-id="84a35-165">**User IDs**: `davids`, `chrisd`, `kima`</span></span>
- <span data-ttu-id="84a35-166">**Cmdlet:** **Set-Mailbox**</span><span class="sxs-lookup"><span data-stu-id="84a35-166">**Cmdlets**: **Set-Mailbox**</span></span>
- <span data-ttu-id="84a35-167">**매개** 변수 : _ProhibitSendQuota,_ _ProhibitSendReceiveQuota,_ _IssueWarningQuota,_ _MaxSendSize,_ _MaxReceiveSize_</span><span class="sxs-lookup"><span data-stu-id="84a35-167">**Parameters**: _ProhibitSendQuota_, _ProhibitSendReceiveQuota_, _IssueWarningQuota_, _MaxSendSize_, _MaxReceiveSize_</span></span>

```PowerShell
Search-AdminAuditLog -Cmdlets Set-Mailbox -Parameters ProhibitSendQuota,ProhibitSendReceiveQuota,IssueWarningQuota,MaxSendSize,MaxReceiveSize -StartDate 08/04/2018 -EndDate 10/03/2018 -UserIds davids,chrisd,kima
```

<span data-ttu-id="84a35-p114">이 예에서는 특정 사서함에 대한 변경 내용을 검색합니다. 문제를 해결하거나 조사에 필요한 정보를 제공해야 할 경우에 유용합니다. 다음과 같은 기준이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="84a35-p114">This example searches for changes made to a specific mailbox. This is useful if you're troubleshooting or you need to provide information for an investigation. The following criteria are used:</span></span>

- <span data-ttu-id="84a35-171">**시작 날짜**: 2018/05/01</span><span class="sxs-lookup"><span data-stu-id="84a35-171">**Start date**: 05/01/2018</span></span>
- <span data-ttu-id="84a35-172">**종료 날짜**: 2018년 10월 3일</span><span class="sxs-lookup"><span data-stu-id="84a35-172">**End date**: 10/03/2018</span></span>
- <span data-ttu-id="84a35-173">**개체 ID:** contoso.com/Users/DavidS</span><span class="sxs-lookup"><span data-stu-id="84a35-173">**Object ID**: contoso.com/Users/DavidS</span></span>

```PowerShell
Search-AdminAuditLog -StartDate 05/01/2018 -EndDate 10/03/2018 -ObjectID contoso.com/Users/DavidS
```

<span data-ttu-id="84a35-174">검색 시 많은 로그 항목이 반환될 경우 **Exchange Online PowerShell** 사용에 제공된 절차를 사용하여 감사 로그 항목을 검색하고 이 문서의 부분에 있는 받는 사람에게 결과를 보내는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="84a35-174">If your searches return many log entries, we recommend that you use the procedure provided in **Use Exchange Online PowerShell to search for audit log entries and send results to a recipient** later in this article.</span></span> <span data-ttu-id="84a35-175">해당 섹션의 절차는 지정한 받는 사람에게 XML 파일을 전자 메일 첨부 파일로 전송하므로 관심 있는 데이터를 더 쉽게 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84a35-175">The procedure in that section sends an XML file as an email attachment to the recipients you specify, enabling you to more easily extract the data you're interested in.</span></span>

<span data-ttu-id="84a35-176">구문과 매개 변수에 대한 자세한 내용은 [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="84a35-176">For detailed syntax and parameter information, see [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).</span></span>

### <a name="view-details-of-audit-log-entries"></a><span data-ttu-id="84a35-177">감사 로그 항목의 상세 정보 보기</span><span class="sxs-lookup"><span data-stu-id="84a35-177">View details of audit log entries</span></span>

<span data-ttu-id="84a35-178">**Search-AdminAuditLog** cmdlet은 감사 로그 내용에 설명된 [필드를 반환합니다.](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents)</span><span class="sxs-lookup"><span data-stu-id="84a35-178">The **Search-AdminAuditLog** cmdlet returns the fields described in [Audit log contents](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents).</span></span> <span data-ttu-id="84a35-179">cmdlet에 의해 반환된 필드 중에서 **CmdletParameters** 및 **ModifiedProperties** 의 두 필드에는 기본적으로 볼 수 없는 추가 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="84a35-179">Of the fields returned by the cmdlet, two fields, **CmdletParameters** and **ModifiedProperties**, contain additional information that isn't viewable by default.</span></span>

<span data-ttu-id="84a35-180">**CmdletParameters** 및 **ModifiedProperties** 필드의 콘텐츠를 보려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="84a35-180">To view the contents of the **CmdletParameters** and **ModifiedProperties** fields, use the following steps.</span></span> <span data-ttu-id="84a35-181">또는 **Exchange Online PowerShell** 사용의 절차에 따라 감사 로그 항목을 검색하고 이 문서의 부분에 있는 받는 사람에게 결과를 보내 XML 파일을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84a35-181">Or, you can use the procedure in **Use Exchange Online PowerShell to search for audit log entries and send results to a recipient** later in this article to create an XML file.</span></span>

<span data-ttu-id="84a35-182">이 절차에서는 다음 개념을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="84a35-182">This procedure uses the following concepts:</span></span>

- [<span data-ttu-id="84a35-183">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="84a35-183">about_Arrays</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_arrays)

- [<span data-ttu-id="84a35-184">about_Variables</span><span class="sxs-lookup"><span data-stu-id="84a35-184">about_Variables</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_variables)

1. <span data-ttu-id="84a35-185">검색할 기준을 정하고 **Search-AdminAuditLog** cmdlet을 실행한 후 다음 명령을 사용하여 변수에 결과를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="84a35-185">Decide the criteria you want to search for, run the **Search-AdminAuditLog** cmdlet, and store the results in a variable using the following command.</span></span>

   ```PowerShell
   $Results = Search-AdminAuditLog <search criteria>
   ```

2. <span data-ttu-id="84a35-186">각 감사 로그 항목은 변수에 배열 요소로 `$Results` 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="84a35-186">Each audit log entry is stored as an array element in the variable `$Results`.</span></span> <span data-ttu-id="84a35-187">배열 요소 인덱스를 지정하여 배열 요소를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84a35-187">You can select an array element by specifying its array element index.</span></span> <span data-ttu-id="84a35-188">배열 요소 인덱스는 첫 번째 배열 요소에 대해 0에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="84a35-188">Array element indexes start at zero (0) for the first array element.</span></span> <span data-ttu-id="84a35-189">예를 들어, 인덱스가 4인 5번째 배열 요소를 검색하려면 다음 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="84a35-189">For example, to retrieve the 5th array element, which has an index of 4, use the following command.</span></span>

   ```PowerShell
   $Results[4]
   ```

3. <span data-ttu-id="84a35-p119">이전 명령이 배열 요소 4에 저장된 로그 항목을 반환합니다. 이 로그 항목의 **CmdletParameters** 및 **ModifiedProperties** 필드의 콘텐츠를 보려면 다음 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="84a35-p119">The previous command returns the log entry stored in array element 4. To see the contents of the **CmdletParameters** and **ModifiedProperties** fields for this log entry, use the following commands.</span></span>

   ```PowerShell
   $Results[4].CmdletParameters
   $Results[4].ModifiedProperties
   ```

4. <span data-ttu-id="84a35-192">다른 로그 항목의 **CmdletParameters** 또는 **ModifiedParameters** 필드의 콘텐츠를 보려면 배열 요소 인덱스를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="84a35-192">To view the contents of the **CmdletParameters** or **ModifiedParameters** fields in another log entry, change the array element index.</span></span>
