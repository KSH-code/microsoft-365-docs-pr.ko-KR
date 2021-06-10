---
title: 보유자 감사 활동 보기
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
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Advanced eDiscovery 관리 도구를 사용하여 사례 내에서 보호자에 대한 활동에 쉽게 액세스하고 검색할 수 있습니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f9e96d0b5dd3bf42dbba56a6e1be91014485ce98
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024768"
---
# <a name="view-custodian-audit-activity"></a><span data-ttu-id="fcf80-103">보유자 감사 활동 보기</span><span class="sxs-lookup"><span data-stu-id="fcf80-103">View custodian audit activity</span></span>

<span data-ttu-id="fcf80-104">사용자가 특정 문서를 보았는지 또는 사서함에서 항목을 제거했는지 확인해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="fcf80-104">Need to find if a user viewed a specific document or purged an item from their mailbox?</span></span> <span data-ttu-id="fcf80-105">Advanced eDiscovery 보안 및 준수 센터의 기존 감사 로그 검색 & 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-105">Advanced eDiscovery is now integrated with the existing audit log search tool in the Security & Compliance Center.</span></span> <span data-ttu-id="fcf80-106">이 포함된 환경을 사용하면 Advanced eDiscovery 관리 도구를 사용하여 사례 내에서 보호자에 대한 활동에 쉽게 액세스하고 검색하여 조사를 용이하게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-106">Using this embedded experience, you can use the Advanced eDiscovery Custodian Management tool to facilitate your investigation by easily accessing and searching the activity for custodians within your case.</span></span>

## <a name="get-permissions"></a><span data-ttu-id="fcf80-107">사용 권한 얻기</span><span class="sxs-lookup"><span data-stu-id="fcf80-107">Get permissions</span></span>

<span data-ttu-id="fcf80-108">감사 로그를 검색하려면 Exchange Online에서 보기 전용 감사 로그 또는 감사 로그 역할이 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-108">You have to be assigned the View-Only Audit Logs or Audit Logs role in Exchange Online to search the audit log.</span></span> <span data-ttu-id="fcf80-109">기본적으로 이러한 역할은 Exchange 관리 센터의 사용 권한 페이지에서 규정 준수 관리 및 조직 관리 역할 그룹에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-109">By default, these roles are assigned to the Compliance Management and Organization Management role groups on the Permissions page in the Exchange admin center.</span></span> <span data-ttu-id="fcf80-110">최소 권한 수준을 사용하여 Advanced eDiscovery 감사 로그를 검색할 수 있는 권한을 사용자에게 제공하려면 Exchange Online에서 사용자 지정 역할 그룹을 만들고, 보기 전용 감사 로그 또는 감사 로그 역할을 추가한 다음, 새 역할 그룹의 구성원으로 사용자를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-110">To give a user the ability to search the Advanced eDiscovery audit log with the minimum level of privileges, you can create a custom role group in Exchange Online, add the View-Only Audit Logs or Audit Logs role, and then add the user as a member of the new role group.</span></span> <span data-ttu-id="fcf80-111">자세한 내용은 Exchange Online에서 역할 그룹 관리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fcf80-111">For more information, see Manage role groups in Exchange Online.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fcf80-112">사용자에게 보안 View-Only 준수 센터의 사용 권한 페이지에서 감사 로그 또는 감사 로그 역할을 & 경우 감사 로그를 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-112">If you assign a user the View-Only Audit Logs or Audit Logs role on the Permissions page in the Security & Compliance Center, they won't be able to search the audit log.</span></span> <span data-ttu-id="fcf80-113">Exchange Online에서 사용 권한을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-113">You have to assign the permissions in Exchange Online.</span></span> <span data-ttu-id="fcf80-114">감사 로그를 검색하는 데 사용되는 기본 cmdlet이 Exchange Online cmdlet이기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-114">This is because the underlying cmdlet used to search the audit log is an Exchange Online cmdlet.</span></span>

## <a name="step-1-search-the-audit-log-for-activities-performed-by-a-custodian"></a><span data-ttu-id="fcf80-115">1단계: 감사 로그에서 보안 주관자에 의해 수행된 활동 검색</span><span class="sxs-lookup"><span data-stu-id="fcf80-115">Step 1: Search the audit log for activities performed by a custodian</span></span>

1. <span data-ttu-id="fcf80-116">**eDiscovery > Advanced eDiscovery** 사례를 여는 것이 가장 까다로입니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-116">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>
  
2. <span data-ttu-id="fcf80-117">원본 **탭을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-117">Click the **Sources** tab.</span></span>
  
3. <span data-ttu-id="fcf80-118">**Custodians(Custodians)** 페이지의 목록에서 **custodian을** 선택한 다음 플라이아웃 페이지에서 보아 활동 보기를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-118">On the **Custodians** page, select a custodian from the list, and then click **View custodian activity** on the flyout page.</span></span>

    <span data-ttu-id="fcf80-119">Custodian 활동 검색 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-119">The Custodian activities search page is displayed.</span></span> <span data-ttu-id="fcf80-120">이전 단계에서 선택한 **custodian이 Custodian** 드롭다운 상자에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-120">Note the custodian you selected in the previous step is displayed in the **Custodian** drop-down box.</span></span> <span data-ttu-id="fcf80-121">드롭다운 상자에서 다른 보위원을 선택할 수 있지만 한 번의 보육자에 대한 활동만 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-121">You can select different custodians in the drop-down box, but you can only search for activities for one custodian at a time.</span></span>

    ![보유자 활동 검색 페이지](../media/AeDCustodianActivities1.png)
   
4. <span data-ttu-id="fcf80-123">다음과 같은 검색 조건을 구성합니다. </span><span class="sxs-lookup"><span data-stu-id="fcf80-123">Configure the following search criteria:</span></span>
      
   1. <span data-ttu-id="fcf80-124">**활동** - 드롭다운 목록을 클릭하여 검색할 수 있는 활동을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-124">**Activities** - Click the drop-down list to display the activities that you can search for.</span></span> <span data-ttu-id="fcf80-125">검색을 실행하면 선택한 활동에 대한 감사 기록만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-125">After you run the search, only the audit records for the selected activities are displayed.</span></span> <span data-ttu-id="fcf80-126">모든 **활동에** 대한 결과 표시를 선택하면 다른 검색 조건과 일치하는 보위부가 수행한 모든 활동에 대한 결과가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-126">Selecting **Show results for all activities** will display results for all activities performed by the custodian that match the other search criteria.</span></span>

      ![활동 목록](../media/CustodianActivityAudit.PNG)
      
   1. <span data-ttu-id="fcf80-128">**시작 날짜 및 종료 날짜** - 날짜 및 시간 범위를 선택하여 해당 기간 내에 발생한 이벤트를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-128">**Start date and End date** - Select a date and time range to display the events that occurred within that period.</span></span> <span data-ttu-id="fcf80-129">기본적으로 지난 7일이 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-129">The last seven days are selected by default.</span></span> <span data-ttu-id="fcf80-130">날짜 및 시간은 UTC(협정 세계시) 형식으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-130">The date and time are presented in Coordinated Universal Time (UTC) format.</span></span> <span data-ttu-id="fcf80-131">지정할 수 있는 최대 날짜 범위는 1년입니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-131">The maximum date range that you can specify is one year.</span></span>
      
   1. <span data-ttu-id="fcf80-132">**Custodians** - 이 상자를 클릭한 다음 검색 결과를 표시할 특정 수장인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-132">**Custodians** - Click in this box and then select a specific custodian to display search results for.</span></span> <span data-ttu-id="fcf80-133">이 상자에서 선택한 사용자가 수행한 선택한 활동에 대한 감사 레코드가 결과 목록에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-133">Audit records for the selected activity performed by the users you select in this box are displayed in the list of results.</span></span>
      
5. <span data-ttu-id="fcf80-134">이</span><span class="sxs-lookup"><span data-stu-id="fcf80-134">Click</span></span> ![검색 단추](../media/SearchButton.PNG)  <span data-ttu-id="fcf80-136">검색 조건을 사용하여 검색을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-136">to run the search using your search criteria.</span></span> <span data-ttu-id="fcf80-137">검색 결과가 로드되고 몇 분 후에 검색 결과가 Custodian Activities 검색 페이지의 결과 아래에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-137">The search results are loaded, and after a few moments they are displayed under Results on the Custodian Activities search page.</span></span> 

## <a name="step-2-view-the-audit-log-search-results"></a><span data-ttu-id="fcf80-138">2단계: 감사 로그 검색 결과 보기</span><span class="sxs-lookup"><span data-stu-id="fcf80-138">Step 2: View the audit log search results</span></span>

<span data-ttu-id="fcf80-139">감사 로그 검색 결과는 Custodian 감사 로그 페이지의 결과 아래에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-139">The results of an audit log search are displayed under Results on the Custodian Audit log page.</span></span> <span data-ttu-id="fcf80-140">최대 5,000개(최근) 이벤트가 150개 증분으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-140">A maximum of 5,000 (newest) events are displayed in increments of 150 events.</span></span> <span data-ttu-id="fcf80-141">이벤트를 더 표시하려면 결과 창에서 스크롤 막대를 사용하거나, Shift+End를 눌러 다음 150개의 이벤트를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-141">To display more events you can use the scroll bar in the Results pane or you can press Shift + End to display the next 150 events.</span></span>

<span data-ttu-id="fcf80-142">결과에는 검색에서 반환되는 각 이벤트에 대한 다음 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-142">The results contain the following information about each event returned by the search.</span></span>
- <span data-ttu-id="fcf80-143">**날짜**: 이벤트가 발생한 날짜 및 시간(UTC 형식)입니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-143">**Date**: The date and time (in UTC format) when the event occurred.</span></span>

- <span data-ttu-id="fcf80-144">**IP 주소**: 활동을 기록할 때 사용된 장치의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-144">**IP address**: The IP address of the device that was used when the activity was logged.</span></span> <span data-ttu-id="fcf80-145">IP 주소는 IPv4 또는 IPv6 주소 형식으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-145">The IP address is displayed in either an IPv4 or IPv6 address format.</span></span>

- <span data-ttu-id="fcf80-146">**사용자**: 이벤트를 트리거한 작업을 수행한 사용자(또는 서비스 계정)입니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-146">**User**: The user (or service account) who performed the action that triggered the event.</span></span>

- <span data-ttu-id="fcf80-147">**활동**: 사용자가 수행한 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-147">**Activity**: The activity performed by the user.</span></span> <span data-ttu-id="fcf80-148">이 값은 활동 드롭다운 목록에서 선택한 활동에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-148">This value corresponds to the activities that you selected in the Activities drop down list.</span></span> <span data-ttu-id="fcf80-149">Exchange 관리자 감사 로그의 이벤트에 대한 이 열의 값은 Exchange cmdlet입니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-149">For an event from the Exchange admin audit log, the value in this column is an Exchange cmdlet.</span></span>

- <span data-ttu-id="fcf80-150">**항목**: 해당 활동의 결과로 생성 또는 수정된 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-150">**Item**: The object that was created or modified as a result of the corresponding activity.</span></span> <span data-ttu-id="fcf80-151">예를 들어, 보거나 수정된 파일 또는 업데이트된 사용자 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-151">For example, the file that was viewed or modified or the user account that was updated.</span></span> <span data-ttu-id="fcf80-152">일부 활동은 이 열에 값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-152">Not all activities have a value in this column.</span></span>

- <span data-ttu-id="fcf80-153">**세부 정보**: 활동에 대한 추가 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-153">**Detail**: Additional detail about an activity.</span></span> <span data-ttu-id="fcf80-154">마찬가지로, 일부 활동에는 값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-154">Again, not all activities will have a value.</span></span>

## <a name="step-3-filter-the-search-results"></a><span data-ttu-id="fcf80-155">3단계: 검색 결과 필터링</span><span class="sxs-lookup"><span data-stu-id="fcf80-155">Step 3: Filter the search results</span></span>

<span data-ttu-id="fcf80-156">정렬 외에도 감사 로그 검색 결과를 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-156">In addition to sorting, you can also filter the results of an audit log search.</span></span> <span data-ttu-id="fcf80-157">이를 통해 특정 사용자 또는 활동에 대한 결과를 빠르게 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-157">This can help you quickly filter the results for a specific user or activity.</span></span> 

<span data-ttu-id="fcf80-158">결과를 필터링하려면</span><span class="sxs-lookup"><span data-stu-id="fcf80-158">To filter the results:</span></span>

 1. <span data-ttu-id="fcf80-159">감사 로그 검색을 만들고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-159">Create and run an audit log search.</span></span>
  
2. <span data-ttu-id="fcf80-160">결과가 표시되면 **결과 필터링** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-160">When the results are displayed, click **Filter results**.</span></span>
 
3. <span data-ttu-id="fcf80-161">각 열 머리글 아래에 키워드 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-161">Keyword boxes are displayed under each column header.</span></span>
  
4. <span data-ttu-id="fcf80-162">열 머리글 아래에 있는 상자 중 하나를 클릭하고 필터링할 열에 따라 단어 또는 구를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-162">Click one of the boxes under a column header and type a word or phrase, depending on the column you're filtering on.</span></span> <span data-ttu-id="fcf80-163">결과가 동적으로 다시 조정되어 필터와 일치하는 이벤트를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-163">The results will dynamically readjust to display the events that match your filter.</span></span>
  
5. <span data-ttu-id="fcf80-164">필터를 선택 취소하려면 필터 상자에서 **X를** 클릭하거나 필터링 **숨기기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="fcf80-164">To clear a filter, click the **X** in the filter box or just click **Hide filtering**.</span></span>

## <a name="export-the-search-results-to-a-file"></a><span data-ttu-id="fcf80-165">파일로 검색 결과 내보내기</span><span class="sxs-lookup"><span data-stu-id="fcf80-165">Export the search results to a file</span></span>

<span data-ttu-id="fcf80-166">감사 로그 검색 결과를 로컬 컴퓨터의 CSV(콤보로 구분된 값) 파일로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-166">You can export the results of an audit log search to a comma separated value (CSV) file on your local computer.</span></span> <span data-ttu-id="fcf80-167">이 파일은 여러 열에서 열 수 Microsoft Excel 단일 열(다중값 셀 포함)을 검색, 정렬, 필터링 및 분할하는 등의 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-167">You can open this file in Microsoft Excel and use features such as search, sorting, filtering, and splitting a single column (that contains multi-value cells) into multiple columns.</span></span>

1. <span data-ttu-id="fcf80-168">감사 로그 검색을 실행한 다음 원하는 결과를 얻을 때까지 검색 조건을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-168">Run an audit log search, and then revise the search criteria until you have the desired results.</span></span>
  
2. <span data-ttu-id="fcf80-169">결과 내보내기를 클릭하고 다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-169">Click Export results and select one of the following options:</span></span>

    - <span data-ttu-id="fcf80-170">**로드된 결과를 저장합니다.** 이 옵션을 선택하면 **Custodian**  감사 로그 검색 페이지의 결과 아래에 표시되는 항목만 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-170">**Save loaded results:** Choose this option to export only the entries that are displayed under **Results** on the **Custodian Audit log search** page.</span></span> <span data-ttu-id="fcf80-171">다운로드한 CSV 파일에는 페이지에 표시되는 것과 동일한 열(날짜, 사용자, 활동, 항목 및 세부 정보) 및 데이터가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-171">The CSV file that is downloaded contains the same columns (and data) displayed on the page (Date, User, Activity, Item, and Details).</span></span> <span data-ttu-id="fcf80-172">감사 로그 항목의 추가 정보가 포함된 추가 열(기타)이 CSV 파일에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-172">An additional column (titled **More**) is included in the CSV file that contains more information from the audit log entry.</span></span> <span data-ttu-id="fcf80-173">감사 로그 검색 페이지에 로드되어 표시되는 것과 동일한 결과를 내보내기 때문에 최대 5,000개의 항목이 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-173">Because you're exporting the same results that are loaded (and viewable) on the Audit log search page, a maximum of 5,000 entries are exported.</span></span>
        
    - <span data-ttu-id="fcf80-174">**모든 결과를 다운로드합니다.** 감사 로그에서 검색 조건을 충족하는 모든 항목을 내보내면 이 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-174">**Download all results:** Choose this option to export all entries from the audit log that meet the search criteria.</span></span> <span data-ttu-id="fcf80-175">대규모 검색 결과 집합의 경우 감사 로그에서 모든 항목을 다운로드하려면 이 옵션을 선택하고, **Custodian** 감사 로그 검색 페이지에 표시할 수 있는 5,000개 결과 외에 모든 항목을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-175">For a large set of search results, choose this option to download all entries from the audit log in addition to the 5,000 results that can be displayed on the **Custodian Audit log** search page.</span></span> <span data-ttu-id="fcf80-176">이 옵션은 감사 로그에서 CSV 파일로 원시 데이터를 다운로드하고 AuditData 열에 있는 감사 로그 항목의 추가 정보를 포함하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-176">This option will download the raw data from the audit log to a CSV file, and contains additional information from the audit log entry in a column named AuditData.</span></span> <span data-ttu-id="fcf80-177">파일이 다른 옵션을 선택할 경우 다운로드되는 파일보다 훨씬 더 클 수 있기 때문에 이 내보내기 옵션을 선택할 경우 파일을 다운로드하는 데 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-177">It may take longer to download the file if you choose this export option because the file may be much larger than the one that's downloaded if you choose the other option.</span></span>
    
      > [!IMPORTANT]
      > <span data-ttu-id="fcf80-178">단일 감사 로그 검색에서 최대 50,000의 항목을 CSV 파일로 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-178">You can download a maximum of 50,000 entries to a CSV file from a single audit log search.</span></span> <span data-ttu-id="fcf80-179">50,000개의 항목이 CSV 파일로 다운로드되면 검색 조건에 맞는 이벤트가 50,000개 이상 있다고 가정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-179">If 50,000 entries are downloaded to the CSV file, you can probably assume there are more than 50,000 events that met the search criteria.</span></span> <span data-ttu-id="fcf80-180">이 제한보다 많은 항목을 내보내려면 날짜 범위를 사용하여 감사 로그 항목 수를 줄이세요.</span><span class="sxs-lookup"><span data-stu-id="fcf80-180">To export more than this limit, try using a date range to reduce the number of audit log entries.</span></span> <span data-ttu-id="fcf80-181">50,000개 이상의 항목을 내보내기 위해 더 작은 날짜 범위로 여러 번 검색을 실행해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-181">You might have to run multiple searches with smaller date ranges to export more than 50,000 entries.</span></span>
        

3. <span data-ttu-id="fcf80-182">내보내기 옵션을 선택하면 CSV 파일을 열거나 다운로드 폴더에 저장하거나 특정 폴더에 저장하라는 메시지가 창 아래쪽에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcf80-182">After you select an export option, a message is displayed at the bottom of the window that prompts you to open the CSV file, save it to the Downloads folder, or save it to a specific folder</span></span>

<span data-ttu-id="fcf80-183">감사 로그 검색 결과를 보거나 필터링하거나 내보내는 데 대한 자세한 내용은 Security & Compliance Center에서 감사 [로그 검색을 참조하세요.](search-the-audit-log-in-security-and-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="fcf80-183">For more information about viewing, filtering, or exporting audit log search results, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>
