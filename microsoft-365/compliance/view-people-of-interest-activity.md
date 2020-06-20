---
title: 관심 있는 사용자의 감사 작업 보기
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
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
description: 관심 있는 사람을 위해 작업에 액세스 하 고 검색 하 여 조사에서 관심사 관리 도구의 데이터 조사 (미리 보기)를 사용 합니다.
ms.openlocfilehash: 37a8d6bae02f1e18bdd5599d7c5472b8d42e145f
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819018"
---
# <a name="view-the-audit-activity-of-people-of-interest"></a><span data-ttu-id="3b333-103">관심 있는 사용자의 감사 작업 보기</span><span class="sxs-lookup"><span data-stu-id="3b333-103">View the audit activity of people of interest</span></span>

<span data-ttu-id="3b333-104">사용자가 특정 문서를 보았는지 또는 사서함에서 항목을 제거했는지 확인해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="3b333-104">Need to find if a user viewed a specific document or purged an item from their mailbox?</span></span> <span data-ttu-id="3b333-105">데이터 조사 (미리 보기)는 이제 보안 & 준수 센터의 기존 감사 로그 검색 도구와 통합 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-105">Data Investigations (Preview) is now integrated with the existing audit log search tool in the Security & Compliance Center.</span></span> <span data-ttu-id="3b333-106">이 포함 된 환경을 사용 하는 경우 데이터 조사 (미리 보기) 사용자의 관심 있음 관리 도구를 사용 하 여 조사 내에서 관심 있는 사용자에 대 한 활동을 쉽게 액세스 하 고 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-106">Using this embedded experience, you can use the Data Investigations (Preview) People of interest Management tool to facilitate your investigation by easily accessing and searching the activity for people of interest within your investigation.</span></span>

## <a name="get-permissions"></a><span data-ttu-id="3b333-107">사용 권한 얻기</span><span class="sxs-lookup"><span data-stu-id="3b333-107">Get permissions</span></span>

<span data-ttu-id="3b333-108">감사 로그를 검색하려면 Exchange Online에서 보기 전용 감사 로그 또는 감사 로그 역할이 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-108">You have to be assigned the View-Only Audit Logs or Audit Logs role in Exchange Online to search the audit log.</span></span> <span data-ttu-id="3b333-109">기본적으로 이러한 역할은 Exchange 관리 센터의 사용 권한 페이지에서 규정 준수 관리 및 조직 관리 역할 그룹에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-109">By default, these roles are assigned to the Compliance Management and Organization Management role groups on the Permissions page in the Exchange admin center.</span></span> <span data-ttu-id="3b333-110">사용자에 게 최소 수준의 권한으로 데이터 조사 (미리 보기) 감사 로그를 검색할 수 있는 기능을 제공 하려면 Exchange Online에서 사용자 지정 역할 그룹을 만들고 보기 전용 감사 로그 또는 감사 로그 역할을 추가한 다음 사용자를 새 역할 그룹의 구성원으로 추가 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-110">To give a user the ability to search the Data Investigations (Preview) audit log with the minimum level of privileges, you can create a custom role group in Exchange Online, add the View-Only Audit Logs or Audit Logs role, and then add the user as a member of the new role group.</span></span> <span data-ttu-id="3b333-111">자세한 내용은 Exchange Online에서 역할 그룹 관리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3b333-111">For more information, see Manage role groups in Exchange Online.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3b333-112">보안 & 준수 센터의 사용 권한 페이지에서 사용자에 게 보기 전용 감사 로그 또는 감사 로그 역할을 할당 하면 감사 로그를 검색할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-112">If you assign a user the View-Only Audit Logs or Audit Logs role on the Permissions page in the Security & Compliance Center, they won't be able to search the audit log.</span></span> <span data-ttu-id="3b333-113">Exchange Online에서 사용 권한을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-113">You have to assign the permissions in Exchange Online.</span></span> <span data-ttu-id="3b333-114">감사 로그를 검색하는 데 사용되는 기본 cmdlet이 Exchange Online cmdlet이기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-114">This is because the underlying cmdlet used to search the audit log is an Exchange Online cmdlet.</span></span>

## <a name="step-1-create-an-data-investigations-preview-audit-log-search"></a><span data-ttu-id="3b333-115">1 단계: 데이터 조사 만들기 (미리 보기) 감사 로그 검색</span><span class="sxs-lookup"><span data-stu-id="3b333-115">Step 1: Create an Data Investigations (Preview) audit log search</span></span>

   1. <span data-ttu-id="3b333-116">**보안 & 준수 센터 > 데이터 조사 (미리 보기)** 에서 기존 조사를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-116">Select an existing investigation from the **Security & Compliance Center > Data Investigations (Preview)**.</span></span>
   
   2. <span data-ttu-id="3b333-117">**관심 있는 사용자** 탭으로 이동 하 여 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-117">Navigate to the **People of interest** tab and select a person.</span></span>
   
   3. <span data-ttu-id="3b333-118">사용자를 선택한 후에는 세부 정보 패널에서 **활동 보기** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-118">Once you have selected a person, click **View Activity** from the details panel.</span></span>
   
   4. <span data-ttu-id="3b333-119">다음과 같은 검색 조건을 구성합니다. </span><span class="sxs-lookup"><span data-stu-id="3b333-119">Configure the following search criteria:</span></span>
      
      <span data-ttu-id="3b333-120">a.</span><span class="sxs-lookup"><span data-stu-id="3b333-120">a.</span></span> <span data-ttu-id="3b333-121">**활동** -드롭다운 목록을 클릭 하 여 검색할 수 있는 활동을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-121">**Activities** - Click the drop-down list to display the activities that you can search for.</span></span> <span data-ttu-id="3b333-122">검색을 실행 한 후에는 선택한 활동에 대 한 감사 레코드만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-122">After you run the search, only the audit records for the selected activities are displayed.</span></span> <span data-ttu-id="3b333-123">**모든 작업에 대해 결과 표시** 를 선택 하면 다른 검색 조건을 충족 하는 모든 작업에 대 한 결과가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-123">Selecting **Show results for all activities** will display results for all activities that meet the other search criteria.</span></span>
      
      <span data-ttu-id="3b333-124">b.</span><span class="sxs-lookup"><span data-stu-id="3b333-124">b.</span></span> <span data-ttu-id="3b333-125">**시작 날짜 및 종료 날짜** -해당 기간 내에 발생 한 이벤트를 표시 하려면 날짜 및 시간 범위를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-125">**Start date and End date** - Select a date and time range to display the events that occurred within that period.</span></span> <span data-ttu-id="3b333-126">지난 7 일이 기본적으로 선택 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-126">The last seven days are selected by default.</span></span> <span data-ttu-id="3b333-127">날짜 및 시간은 UTC(협정 세계시) 형식으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-127">The date and time are presented in Coordinated Universal Time (UTC) format.</span></span> <span data-ttu-id="3b333-128">지정할 수 있는 최대 날짜 범위는 1 년입니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-128">The maximum date range that you can specify is one year.</span></span>
      
      <span data-ttu-id="3b333-129">c.</span><span class="sxs-lookup"><span data-stu-id="3b333-129">c.</span></span> <span data-ttu-id="3b333-130">**관심 있는 사람** -이 상자를 클릭 한 후 검색 결과를 표시할 특정 custodian 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-130">**People of interest** - Click in this box and then select a specific custodian to display search results for.</span></span> <span data-ttu-id="3b333-131">이 상자에서 선택한 사용자가 수행한 선택한 작업에 대 한 감사 레코드가 결과 목록에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-131">Audit records for the selected activity performed by the users you select in this box are displayed in the list of results.</span></span>
    
    1. <span data-ttu-id="3b333-132">**검색**을 클릭하여 검색 조건을 사용한 검색을 실행합니다. </span><span class="sxs-lookup"><span data-stu-id="3b333-132">Click **Search** to run the search using your search criteria.</span></span> <span data-ttu-id="3b333-133">검색 결과가 로드 되 고 몇 분 후에는 관심 있는 작업 검색 페이지의 결과 아래에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-133">The search results are loaded, and after a few moments they are displayed under Results on the People of interest Activities search page.</span></span> 

## <a name="step-2-view-the-audit-log-search-results"></a><span data-ttu-id="3b333-134">2 단계: 감사 로그 검색 결과 보기</span><span class="sxs-lookup"><span data-stu-id="3b333-134">Step 2: View the audit log search results</span></span>

<span data-ttu-id="3b333-135">감사 로그 검색의 결과는 관심 있는 사용자 감사 로그 페이지의 결과 아래에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-135">The results of an audit log search are displayed under Results on the People of interest Audit log page.</span></span> <span data-ttu-id="3b333-136">최대 5000 (최신) 이벤트는 150 이벤트 단위로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-136">A maximum of 5,000 (newest) events are displayed in increments of 150 events.</span></span> <span data-ttu-id="3b333-137">이벤트를 더 표시하려면 결과 창에서 스크롤 막대를 사용하거나, Shift+End를 눌러 다음 150개의 이벤트를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-137">To display more events you can use the scroll bar in the Results pane or you can press Shift + End to display the next 150 events.</span></span>

<span data-ttu-id="3b333-138">결과에는 검색에서 반환 된 각 이벤트에 대 한 다음과 같은 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-138">The results contain the following information about each event returned by the search.</span></span>
- <span data-ttu-id="3b333-139">**날짜**: 이벤트가 발생한 날짜 및 시간(UTC 형식)입니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-139">**Date**: The date and time (in UTC format) when the event occurred.</span></span>

- <span data-ttu-id="3b333-140">**IP 주소**: 활동을 기록할 때 사용된 장치의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-140">**IP address**: The IP address of the device that was used when the activity was logged.</span></span> <span data-ttu-id="3b333-141">IP 주소는 IPv4 또는 IPv6 주소 형식으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-141">The IP address is displayed in either an IPv4 or IPv6 address format.</span></span>

- <span data-ttu-id="3b333-142">**사용자**: 이벤트를 트리거한 작업을 수행한 사용자(또는 서비스 계정)입니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-142">**User**: The user (or service account) who performed the action that triggered the event.</span></span>

- <span data-ttu-id="3b333-143">**활동**: 사용자가 수행한 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-143">**Activity**: The activity performed by the user.</span></span> <span data-ttu-id="3b333-144">이 값은 활동 드롭다운 목록에서 선택한 활동에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-144">This value corresponds to the activities that you selected in the Activities drop down list.</span></span> <span data-ttu-id="3b333-145">Exchange 관리자 감사 로그의 이벤트에 대한 이 열의 값은 Exchange cmdlet입니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-145">For an event from the Exchange admin audit log, the value in this column is an Exchange cmdlet.</span></span>

- <span data-ttu-id="3b333-146">**항목**: 해당 활동의 결과로 생성 또는 수정된 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-146">**Item**: The object that was created or modified as a result of the corresponding activity.</span></span> <span data-ttu-id="3b333-147">예를 들어, 보거나 수정된 파일 또는 업데이트된 사용자 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-147">For example, the file that was viewed or modified or the user account that was updated.</span></span> <span data-ttu-id="3b333-148">일부 활동은 이 열에 값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-148">Not all activities have a value in this column.</span></span>

- <span data-ttu-id="3b333-149">**세부 정보**: 활동에 대 한 추가 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-149">**Detail**: Additional detail about an activity.</span></span> <span data-ttu-id="3b333-150">다시 말하지만 모든 작업에는 값이 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-150">Again, not all activities will have a value.</span></span>

## <a name="step-3-filter-the-search-results"></a><span data-ttu-id="3b333-151">3단계: 검색 결과 필터링</span><span class="sxs-lookup"><span data-stu-id="3b333-151">Step 3: Filter the search results</span></span>

<span data-ttu-id="3b333-152">정렬 외에도 감사 로그 검색 결과를 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-152">In addition to sorting, you can also filter the results of an audit log search.</span></span> <span data-ttu-id="3b333-153">이를 통해 특정 사용자 또는 활동에 대 한 결과를 빠르게 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-153">This can help you quickly filter the results for a specific user or activity.</span></span> 

<span data-ttu-id="3b333-154">결과를 필터링하려면</span><span class="sxs-lookup"><span data-stu-id="3b333-154">To filter the results:</span></span>

 1. <span data-ttu-id="3b333-155">감사 로그 검색을 만들어 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-155">Create and run an audit log search.</span></span>
  
2. <span data-ttu-id="3b333-156">결과가 표시되면 **결과 필터링**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-156">When the results are displayed, click **Filter results**.</span></span>
 
3. <span data-ttu-id="3b333-157">각 열 머리글 아래에 키워드 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-157">Keyword boxes are displayed under each column header.</span></span>
  
4. <span data-ttu-id="3b333-158">열 머리글 아래에 있는 상자 중 하나를 클릭하고 필터링할 열에 따라 단어 또는 구를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-158">Click one of the boxes under a column header and type a word or phrase, depending on the column you're filtering on.</span></span> <span data-ttu-id="3b333-159">결과가 동적으로 다시 조정되어 필터와 일치하는 이벤트를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-159">The results will dynamically readjust to display the events that match your filter.</span></span>
  
5. <span data-ttu-id="3b333-160">필터를 지우려면 필터 상자에서 **X** 를 클릭 하거나 **필터링 숨기기**를 클릭 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-160">To clear a filter, click the **X** in the filter box or just click **Hide filtering**.</span></span>

## <a name="export-the-search-results-to-a-file"></a><span data-ttu-id="3b333-161">검색 결과를 파일로 내보내기</span><span class="sxs-lookup"><span data-stu-id="3b333-161">Export the search results to a file</span></span>

<span data-ttu-id="3b333-162">감사 로그 검색 결과를 로컬 컴퓨터의 CSV (쉼표로 구분 된 값) 파일로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-162">You can export the results of an audit log search to a comma separated value (CSV) file on your local computer.</span></span> <span data-ttu-id="3b333-163">Microsoft Excel에서이 파일을 열고, 검색, 정렬, 필터링, 다중 값 셀이 포함 된 단일 열을 여러 열로 분할 등의 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-163">You can open this file in Microsoft Excel and use features such as search, sorting, filtering, and splitting a single column (that contains multi-value cells) into multiple columns.</span></span>

1. <span data-ttu-id="3b333-164">감사 로그 검색을 실행한 다음 원하는 결과를 얻을 때까지 검색 조건을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-164">Run an audit log search, and then revise the search criteria until you have the desired results.</span></span>
  
2. <span data-ttu-id="3b333-165">결과 내보내기를 클릭하고 다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-165">Click Export results and select one of the following options:</span></span>

    - <span data-ttu-id="3b333-166">**로드 된 결과 저장:** **관심 있는 감사 로그 검색** 페이지의 **결과** 에 표시 되는 항목만 내보내려면이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-166">**Save loaded results:** Choose this option to export only the entries that are displayed under **Results** on the **People of interest Audit log search** page.</span></span> <span data-ttu-id="3b333-167">다운로드한 CSV 파일에는 페이지에 표시되는 것과 동일한 열(날짜, 사용자, 활동, 항목 및 세부 정보) 및 데이터가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-167">The CSV file that is downloaded contains the same columns (and data) displayed on the page (Date, User, Activity, Item, and Details).</span></span> <span data-ttu-id="3b333-168">CSV 파일에는 감사 로그 항목에서 더 많은 정보가 포함 된 추가 열 ( **더 자세히**)이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-168">An additional column (titled **More**) is included in the CSV file that contains more information from the audit log entry.</span></span> <span data-ttu-id="3b333-169">감사 로그 검색 페이지에 로드되어 표시되는 것과 동일한 결과를 내보내기 때문에 최대 5,000개의 항목이 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-169">Because you're exporting the same results that are loaded (and viewable) on the Audit log search page, a maximum of 5,000 entries are exported.</span></span>
        
    - <span data-ttu-id="3b333-170">**모든 결과를 다운로드 합니다.** 검색 조건을 충족 하는 감사 로그의 모든 항목을 내보내려면이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-170">**Download all results:** Choose this option to export all entries from the audit log that meet the search criteria.</span></span> <span data-ttu-id="3b333-171">많은 검색 결과 집합의 경우 감사 로그의 모든 항목을 다운로드 하려면이 옵션을 선택 하 고, **관심 있는 감사 로그** 검색 페이지에 표시할 수 있는 5000 결과를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-171">For a large set of search results, choose this option to download all entries from the audit log in addition to the 5,000 results that can be displayed on the **People of interest Audit log** search page.</span></span> <span data-ttu-id="3b333-172">이 옵션은 감사 로그의 원시 데이터를 CSV 파일로 다운로드 하 고 감사 로그 항목에서 AuditData 라는 열에 대 한 추가 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-172">This option will download the raw data from the audit log to a CSV file, and contains additional information from the audit log entry in a column named AuditData.</span></span> <span data-ttu-id="3b333-173">파일이 다른 옵션을 선택할 경우 다운로드되는 파일보다 훨씬 더 클 수 있기 때문에 이 내보내기 옵션을 선택할 경우 파일을 다운로드하는 데 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-173">It may take longer to download the file if you choose this export option because the file may be much larger than the one that's downloaded if you choose the other option.</span></span>
    
      > [!IMPORTANT]
      > <span data-ttu-id="3b333-174">단일 감사 로그 검색에서 최대 50,000의 항목을 CSV 파일로 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-174">You can download a maximum of 50,000 entries to a CSV file from a single audit log search.</span></span> <span data-ttu-id="3b333-175">50,000개의 항목이 CSV 파일로 다운로드되면 검색 조건에 맞는 이벤트가 50,000개 이상 있다고 가정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-175">If 50,000 entries are downloaded to the CSV file, you can probably assume there are more than 50,000 events that met the search criteria.</span></span> <span data-ttu-id="3b333-176">이 제한보다 많은 항목을 내보내려면 날짜 범위를 사용하여 감사 로그 항목 수를 줄이세요.</span><span class="sxs-lookup"><span data-stu-id="3b333-176">To export more than this limit, try using a date range to reduce the number of audit log entries.</span></span> <span data-ttu-id="3b333-177">50,000개 이상의 항목을 내보내기 위해 더 작은 날짜 범위로 여러 번 검색을 실행해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-177">You might have to run multiple searches with smaller date ranges to export more than 50,000 entries.</span></span>
        

3. <span data-ttu-id="3b333-178">내보내기 옵션을 선택한 후에는 CSV 파일을 열거나 다운로드 폴더에 저장 하거나 특정 폴더에 저장 하 라는 메시지를 창 아래쪽에 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b333-178">After you select an export option, a message is displayed at the bottom of the window that prompts you to open the CSV file, save it to the Downloads folder, or save it to a specific folder</span></span>

<span data-ttu-id="3b333-179">감사 로그 검색 결과를 보거나 필터링 하거나 내보내는 방법에 대 한 자세한 내용은 [search the audit log In Office 365](search-the-audit-log-in-security-and-compliance.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3b333-179">For more information about viewing, filtering, or exporting audit log search results, see [Search the audit log in the Office 365](search-the-audit-log-in-security-and-compliance.md).</span></span>
