---
title: 감사 로그 레코드 내보내기, 구성 및 보기
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 0d4d0f35-390b-4518-800e-0c7ec95e946c
ms.custom: seo-marvel-apr2020
description: 이 문서에서는 Microsoft 365 감사 로그 레코드를 내보내고 구성하고 보는 방법을 배우게 됩니다.
ms.openlocfilehash: 4cea867b46d3bda7d3b3a8cd38f3d01938da8764
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906870"
---
# <a name="export-configure-and-view-audit-log-records"></a><span data-ttu-id="96ae5-103">감사 로그 레코드 내보내기, 구성 및 보기</span><span class="sxs-lookup"><span data-stu-id="96ae5-103">Export, configure, and view audit log records</span></span>

<span data-ttu-id="96ae5-104">감사 로그를 검색하고 검색 결과를 CSV 파일로 다운로드한 후 파일에는 각 이벤트에 대한 추가 정보가 포함된 **AuditData** 열이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96ae5-104">After you search the audit log and download the search results to a CSV file, the file contains a column named **AuditData**, which contains additional information about each event.</span></span> <span data-ttu-id="96ae5-105">이 열의 데이터는 *property:value* 쌍으로 구성된 여러 속성이 들어 있는 JSON 개체로 서식이 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="96ae5-105">The data in this column is formatted as a JSON object, which contains multiple properties that are configured as *property:value* pairs separated by commas.</span></span> <span data-ttu-id="96ae5-106">Excel의 파워 쿼리 편집기에서 JSON 변환 기능을 사용하여 **AuditData** 열의 JSON 개체에 있는 각 속성을 여러 열로 분할하여 각 속성에 자체 열이 있도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96ae5-106">You can use the JSON transform feature in the Power Query Editor in Excel to split each property in the JSON object in the **AuditData** column into multiple columns so that each property has its own column.</span></span> <span data-ttu-id="96ae5-107">이렇게 하면 이러한 속성 중 하나 이상을 정렬하고 필터링할 수 있으며, 이를 통해 원하는 특정 감사 데이터를 빠르게 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96ae5-107">This lets you sort and filter on one or more of these properties, which can help you quickly locate the specific auditing data you're looking for.</span></span>

## <a name="step-1-export-audit-log-search-results"></a><span data-ttu-id="96ae5-108">1단계: 감사 로그 검색 결과 내보내기</span><span class="sxs-lookup"><span data-stu-id="96ae5-108">Step 1: Export audit log search results</span></span>

<span data-ttu-id="96ae5-109">첫 번째 단계는 감사 로그를 검색한 다음 결과를 CSV(콤보로 구분된 값) 파일로 로컬 컴퓨터로 내보내는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="96ae5-109">The first step is to search the audit log and then export the results in a comma-separated value (CSV) file to your local computer.</span></span>
  
1. <span data-ttu-id="96ae5-110">감사 로그 [검색을 실행하고](search-the-audit-log-in-security-and-compliance.md#search-the-audit-log) 필요한 경우 원하는 결과가 표시될 때까지 검색 기준을 다시 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="96ae5-110">Run an [audit log search](search-the-audit-log-in-security-and-compliance.md#search-the-audit-log) and revise the search criteria if necessary until you have the desired results.</span></span>

2. <span data-ttu-id="96ae5-111">결과 **내보내기 를** 클릭하고 모든 결과 **다운로드를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="96ae5-111">Click **Export results** and select **Download all results**.</span></span> 

   ![모든 결과 다운로드를 클릭합니다.](../media/ExportAuditSearchResults.png)

   <span data-ttu-id="96ae5-113">이 옵션은 1단계에서 시작한 감사 로그 검색에서 모든 감사 레코드를 내보내고 감사 로그에서 CSV 파일로 원시 데이터를 다운로드하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="96ae5-113">This option to exports all the audit records from the audit log search you ran in step 1, and downloads the raw data from the audit log to a CSV file.</span></span> 

   <span data-ttu-id="96ae5-114">창 아래쪽에 CSV 파일을 열거나 저장할지 묻는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="96ae5-114">A message is displayed at the bottom of the window that prompts you to open or save the CSV file.</span></span> 

3. <span data-ttu-id="96ae5-115">다른 **> 저장을** 클릭하고 CSV 파일을 로컬 컴퓨터에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="96ae5-115">Click **Save > Save as** and save the CSV file to your local computer.</span></span> <span data-ttu-id="96ae5-116">많은 검색 결과를 다운로드하는 데는 시간이 오래 걸리게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96ae5-116">It takes a while to download many search results.</span></span> <span data-ttu-id="96ae5-117">일반적으로 모든 활동 또는 광범위한 날짜 범위를 검색할 때 이 경우에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="96ae5-117">This is typically the case when searching for all activities or a broad date range.</span></span> <span data-ttu-id="96ae5-118">CSV 파일 다운로드가 완료되면 창 아래쪽에 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="96ae5-118">A message at the bottom of the windows is displayed when the CSV file is finished downloading.</span></span>

   ![CSV 파일 다운로드가 완료될 때 표시되는 메시지](../media/ExportAuditSearchResultsFinish.png)

> [!NOTE]
  > <span data-ttu-id="96ae5-120">단일 감사 로그 검색에서 최대 50,000의 항목을 CSV 파일로 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96ae5-120">You can download a maximum of 50,000 entries to a CSV file from a single audit log search.</span></span> <span data-ttu-id="96ae5-121">50,000개의 항목이 CSV 파일로 다운로드되면 검색 조건에 맞는 이벤트가 50,000개 이상 있다고 가정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96ae5-121">If 50,000 entries are downloaded to the CSV file, you can probably assume there are more than 50,000 events that met the search criteria.</span></span> <span data-ttu-id="96ae5-122">이 제한을 초과하여 내보내기하려면 날짜 범위를 사용하여 감사 로그 레코드 수를 줄이려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="96ae5-122">To export more than this limit, try using a date range to reduce the number of audit log records.</span></span> <span data-ttu-id="96ae5-123">50,000개 이상의 항목을 내보내기 위해 더 작은 날짜 범위로 여러 번 검색을 실행해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96ae5-123">You might have to run multiple searches with smaller date ranges to export more than 50,000 entries.</span></span>

## <a name="step-2-format-the-exported-audit-log-using-the-power-query-editor"></a><span data-ttu-id="96ae5-124">2단계: 파워 쿼리 편집기를 사용하여 내보낼 감사 로그 서식 지정</span><span class="sxs-lookup"><span data-stu-id="96ae5-124">Step 2: Format the exported audit log using the Power Query Editor</span></span>

<span data-ttu-id="96ae5-125">다음 단계는 Excel의 파워 쿼리 편집기에서 JSON 변환 기능을 사용하여 **AuditData** 열에 있는 JSON 개체의 각 속성을 자체 열로 분할하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="96ae5-125">The next step is to use the JSON transform feature in the Power Query Editor in Excel to split each property in the JSON object in the **AuditData** column into its own column.</span></span> <span data-ttu-id="96ae5-126">그런 다음 열을 필터링하여 특정 속성의 값에 따라 레코드를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96ae5-126">Then you filter columns to view records based on the values of specific properties.</span></span> <span data-ttu-id="96ae5-127">이를 통해 원하는 특정 감사 데이터를 빠르게 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96ae5-127">This can help you quickly locate the specific auditing data you're looking for.</span></span>

1. <span data-ttu-id="96ae5-128">Office 365, Excel 2019 또는 Excel 2016용 Excel에서 빈 통합 문서 열기</span><span class="sxs-lookup"><span data-stu-id="96ae5-128">Open a blank workbook in Excel for Office 365, Excel 2019, or Excel 2016.</span></span>

2. <span data-ttu-id="96ae5-129">데이터 **탭의** 데이터 변환 데이터 **&** 그룹에서 **텍스트/CSV 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="96ae5-129">On the **Data** tab, in the **Get & Transform Data** ribbon group, click **From Text/CSV**.</span></span>

    ![데이터 탭에서 텍스트/CSV를 클릭합니다.](../media/JSONTransformOpenCSVFile.png)

3. <span data-ttu-id="96ae5-131">1단계에서 다운로드한 CSV 파일을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96ae5-131">Open the CSV file that you downloaded in Step 1.</span></span>

4. <span data-ttu-id="96ae5-132">표시되는 창에서 데이터 **변환을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="96ae5-132">In the window that's displayed, click **Transform Data**.</span></span>

   ![데이터 변환을 클릭합니다.](../media/JSONOpenPowerQuery.png)

   <span data-ttu-id="96ae5-134">CSV 파일이 쿼리 **편집기 에서 열립니다.**</span><span class="sxs-lookup"><span data-stu-id="96ae5-134">The CSV file is opened in the **Query Editor**.</span></span> <span data-ttu-id="96ae5-135">열에는 **CreationDate,** **UserIds,** **Operations** 및 **AuditData의** 네 개의 열이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96ae5-135">There are four columns: **CreationDate**, **UserIds**, **Operations**, and **AuditData**.</span></span> <span data-ttu-id="96ae5-136">**AuditData 열은** 여러 속성을 포함하는 JSON 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="96ae5-136">The **AuditData** column is a JSON object that contains multiple properties.</span></span> <span data-ttu-id="96ae5-137">다음 단계에서는 JSON 개체의 각 속성에 대한 열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="96ae5-137">The next step is to create a column for each property in the JSON object.</span></span>

5. <span data-ttu-id="96ae5-138">**AuditData** 열에서 제목을 마우스 오른쪽 단추로 클릭하고 **변환을** 클릭한 다음 **JSON 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="96ae5-138">Right-click the title in the **AuditData** column, click **Transform**, and then click **JSON**.</span></span> 

   ![AuditData 열을 마우스 오른쪽 단추로 클릭하고 변환을 클릭한 다음 JSON을 선택합니다.](../media/JSONTransform.png)

6. <span data-ttu-id="96ae5-140">**AuditData** 열의 오른쪽 위 모서리에서 확장 아이콘을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="96ae5-140">In the upper-right corner of the **AuditData** column, click the expand icon.</span></span>

   ![AuditData 열에서 확장 아이콘을 클릭합니다.](../media/JSONTransformExpandIcon.png)

   <span data-ttu-id="96ae5-142">**AuditData** 열의 JSON 개체에 있는 속성의 일부 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="96ae5-142">A partial list of the properties in the JSON objects in the **AuditData** column is displayed.</span></span>

7. <span data-ttu-id="96ae5-143">자세한 **정보 로드를** 클릭하여 **AuditData** 열의 JSON 개체에 있는 모든 속성을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="96ae5-143">Click **Load more** to display all properties in the JSON objects in the **AuditData** column.</span></span>

   ![JSON 개체의 모든 속성을 표시하려면 더 로드를 클릭합니다.](../media/JSONTransformLoadJSONProperties.png)

   <span data-ttu-id="96ae5-145">포함하지 않는 속성 옆의 확인란을 선택하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96ae5-145">You can unselect the checkbox next to any property that you don't want to include.</span></span> <span data-ttu-id="96ae5-146">조사에 유용하지 않은 열을 제거하면 감사 로그에 표시되는 데이터 양을 줄이는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="96ae5-146">Eliminating columns that aren't useful for your investigation is a good way to reduce the amount of data displayed in the audit log.</span></span> 

   > [!NOTE]
   > <span data-ttu-id="96ae5-147">이전 스크린샷에 표시된 JSON 속성(더 로드를 클릭한 후)은 CSV 파일의 처음 1,000개 행에서 **AuditData** 열에 있는 속성을 기반으로 합니다. </span><span class="sxs-lookup"><span data-stu-id="96ae5-147">The JSON properties displayed in the previous screenshot (after you click **Load more**) are based on the properties found in the **AuditData** column from the first 1,000 rows in the CSV file.</span></span> <span data-ttu-id="96ae5-148">처음 1,000개 행 다음에 레코드에 서로 다른 JSON 속성이 있는 경우 **AuditData** 열이 여러 열로 분할될 때 이러한 속성과 해당 열이 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96ae5-148">If there are different JSON properties in records after the first 1,000 rows, these properties (and a corresponding column) won't be included when the **AuditData** column is split into multiple columns.</span></span> <span data-ttu-id="96ae5-149">이를 방지하려면 감사 로그 검색을 다시 실행하고 반환되는 레코드 수를 줄이면 검색 조건을 좁힐 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96ae5-149">To help prevent this, consider re-running the audit log search and narrow the search criteria so that fewer records are returned.</span></span> <span data-ttu-id="96ae5-150">또 다른 해결 작업은 **AuditData** 열에서 JSON 개체를 변환하기 전에 위의 5단계를 수행하기 전에 **Operations** 열의 항목을 필터링하여 행 수를 줄이는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="96ae5-150">Another workaround is to filter items in the **Operations** column to reduce the number of rows (before you perform step 5 above) before transforming the JSON object in the **AuditData** column.</span></span>

   > [!TIP]
   > <span data-ttu-id="96ae5-151">AuditData.AffectedItems와 같은 목록 내에서 특성을 보려면  특성을 끌어올 열의 오른쪽 위 모서리에 있는 확장 아이콘을 클릭한 다음 새 행으로 확장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="96ae5-151">To view an attribute within a list such as AuditData.AffectedItems, click the **Expand** icon in the upper right corner of the column you want to pull an attribute from, and then select **Expand to New Row**.</span></span>  <span data-ttu-id="96ae5-152">이 목록에서 레코드가 표시되고 열의 오른쪽 위 모서리에 있는 확장 아이콘을 클릭하고 특성을 확인한 다음 보거나 추출할 레코드를 선택할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="96ae5-152">From there it will be a record and you can click the **Expand** icon in the upper right corner of the column, view the attributes, and select the one you want to view or extract.</span></span>

8. <span data-ttu-id="96ae5-153">선택한 각 JSON 속성에 대해 추가된 열의 제목 서식을 지정하기 위해 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="96ae5-153">Do one of the following things to format the title of the columns that are added for each JSON property that's selected.</span></span>

    - <span data-ttu-id="96ae5-154">JSON 속성의 이름을 열 이름으로 사용하기 위해 원래 열 이름을 **prefix로** 사용 확인란의 선택을 언합니다. 예를 들어 **RecordType 또는** **SourceFileName입니다.**</span><span class="sxs-lookup"><span data-stu-id="96ae5-154">Unselect the **Use original column name as prefix** checkbox to use the name of the JSON property as the column names; for example, **RecordType** or **SourceFileName**.</span></span>

    - <span data-ttu-id="96ae5-155">열 이름에 AuditData prefix를 추가하기 위해 원래 열 이름을 **prefix로** 사용 확인란을 선택된 그대로 두고, 열 이름에 AuditData를 추가합니다. 예를 들어 **AuditData.RecordType 또는** **AuditData.SourceFileName입니다.**</span><span class="sxs-lookup"><span data-stu-id="96ae5-155">Leave the **Use original column name as prefix** checkbox selected to add the AuditData prefix to the column names; for example, **AuditData.RecordType** or **AuditData.SourceFileName**.</span></span>

9. <span data-ttu-id="96ae5-156">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="96ae5-156">Click **OK**.</span></span>

    <span data-ttu-id="96ae5-157">**AuditData 열은** 여러 열로 분할됩니다.</span><span class="sxs-lookup"><span data-stu-id="96ae5-157">The **AuditData** column is split into multiple columns.</span></span> <span data-ttu-id="96ae5-158">각 새 열은 AuditData JSON 개체의 속성에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="96ae5-158">Each new column corresponds to a property in the AuditData JSON object.</span></span> <span data-ttu-id="96ae5-159">열의 각 행에는 속성 값이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96ae5-159">Each row in the column contains the value for the property.</span></span> <span data-ttu-id="96ae5-160">속성에 값이 없는 경우 *null* 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="96ae5-160">If the property doesn't contain a value, the *null* value is displayed.</span></span> <span data-ttu-id="96ae5-161">Excel에서 null 값이 있는 셀은 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96ae5-161">In Excel, cells with null values are empty.</span></span>
  
10. <span data-ttu-id="96ae5-162">홈 **탭에서** 로드  & 닫기를 클릭하여 파워 쿼리 편집기를 닫고 Excel 통합 문서에서 변환된 CSV 파일을 니다.</span><span class="sxs-lookup"><span data-stu-id="96ae5-162">On the **Home** tab, click **Close & Load** to close the Power Query Editor and open the transformed CSV file in an Excel workbook.</span></span>

## <a name="use-powershell-to-search-and-export-audit-log-records"></a><span data-ttu-id="96ae5-163">PowerShell을 사용하여 감사 로그 레코드 검색 및 내보내기</span><span class="sxs-lookup"><span data-stu-id="96ae5-163">Use PowerShell to search and export audit log records</span></span>

<span data-ttu-id="96ae5-164">보안 & 준수 센터의 감사 로그 검색 도구를 사용하는 대신 Exchange Online PowerShell에서 [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) cmdlet을 사용하여 감사 로그 검색 결과를 CSV 파일로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96ae5-164">Instead of using the audit log search tool in the Security & Compliance Center, you can use the [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) cmdlet in Exchange Online PowerShell to export the results of an audit log search to a CSV file.</span></span> <span data-ttu-id="96ae5-165">그런 다음 2단계에 설명된 절차에 따라 Power Query 편집기를 사용하여 감사 로그의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="96ae5-165">Then you can follow the same procedure described in Step 2 to format the audit log using the Power Query editor.</span></span> <span data-ttu-id="96ae5-166">PowerShell cmdlet을 사용할 때의 한 가지 이점은 *RecordType* 매개 변수를 사용하여 특정 서비스에서 이벤트를 검색할 수 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="96ae5-166">One advantage of using the PowerShell cmdlet is that you can search for events from a specific service by using the *RecordType* parameter.</span></span> <span data-ttu-id="96ae5-167">다음은 PowerShell을 사용하여 감사 레코드를 CSV 파일로 내보내는 몇 가지 예로, Power Query 편집기를 사용하여 2단계에 설명된 바와 같이 **AuditData** 열의 JSON 개체를 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96ae5-167">Here are few examples of using PowerShell to export audit records to a CSV file so you can use the Power Query editor to transform the JSON object in the **AuditData** column as described in Step 2.</span></span>

<span data-ttu-id="96ae5-168">이 예제에서는 다음 명령을 실행하여 SharePoint 공유 작업과 관련된 모든 레코드를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="96ae5-168">In this example, run the following commands to return all records related to SharePoint sharing operations.</span></span>

```powershell
$auditlog = Search-UnifiedAuditLog -StartDate 06/01/2019 -EndDate 06/30/2019 -RecordType SharePointSharingOperation
```

```powershell
$auditlog | Select-Object -Property CreationDate,UserIds,RecordType,AuditData | Export-Csv -Path c:\AuditLogs\PowerShellAuditlog.csv -NoTypeInformation
```

<span data-ttu-id="96ae5-169">검색 결과는 CreationDate, UserIds, RecordType, AuditData의 네 개의 열을 포함하는 *PowerShellAuditlog라는* CSV 파일로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96ae5-169">The search results are exported to a CSV file named *PowerShellAuditlog* that contains four columns: CreationDate, UserIds, RecordType, AuditData).</span></span>

<span data-ttu-id="96ae5-170">레코드 형식의 이름 또는 열어 값도 *RecordType* 매개 변수의 값으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96ae5-170">You can also use the name or enum value for the record type as the value for the *RecordType* parameter.</span></span> <span data-ttu-id="96ae5-171">레코드 유형 이름 및 해당 열문 값 목록은 Office 365 관리 활동 API schema의 *AuditLogRecordType* [테이블을 참조하세요.](/office/office-365-management-api/office-365-management-activity-api-schema#enum-auditlogrecordtype---type-edmint32)</span><span class="sxs-lookup"><span data-stu-id="96ae5-171">For a list of record type names and their corresponding enum values, see the *AuditLogRecordType* table in [Office 365 Management Activity API schema](/office/office-365-management-api/office-365-management-activity-api-schema#enum-auditlogrecordtype---type-edmint32).</span></span>

<span data-ttu-id="96ae5-172">*RecordType* 매개 변수에는 단일 값만 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96ae5-172">You can only include a single value for the *RecordType* parameter.</span></span> <span data-ttu-id="96ae5-173">다른 레코드 유형에 대한 감사 레코드를 검색하기 위해 이전의 두 명령을 다시 실행하여 다른 레코드 유형을 지정하고 원본 CSV 파일에 해당 결과를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96ae5-173">To search for audit records for other record types, you have to run the two previous commands again to specify a different record type and append those results to the original CSV file.</span></span> <span data-ttu-id="96ae5-174">예를 들어 다음 두 명령을 실행하여 동일한 날짜 범위의 SharePoint 파일 활동을 PowerShellAuditlog.csv 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96ae5-174">For example, you would run the following two commands to add SharePoint file activities from the same date range to the PowerShellAuditlog.csv file.</span></span>

```powershell
$auditlog = Search-UnifiedAuditLog -StartDate 06/01/2019 -EndDate 06/30/2019 -RecordType SharePointFileOperation
```

```powershell
$auditlog | Select-Object -Property CreationDate,UserIds,RecordType,AuditData | Export-Csv -Append -Path c:\AuditLogs\PowerShellAuditlog.csv -NoTypeInformation
```

## <a name="tips-for-exporting-and-viewing-the-audit-log"></a><span data-ttu-id="96ae5-175">감사 로그 내보내기 및 보기 팁</span><span class="sxs-lookup"><span data-stu-id="96ae5-175">Tips for exporting and viewing the audit log</span></span>

<span data-ttu-id="96ae5-176">다음은 JSON 변환 기능을 사용하여 **AuditData** 열을 여러 열로 분할하기 전과 후에 감사 로그를 내보내고 보는 몇 가지 팁과 예입니다.</span><span class="sxs-lookup"><span data-stu-id="96ae5-176">Here are some tips and examples of exporting and viewing the audit log before and after you use the JSON transform feature to split the **AuditData** column into multiple columns.</span></span>

- <span data-ttu-id="96ae5-177">**RecordType 열을 필터링하여** 특정 서비스 또는 기능 영역의 레코드만 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="96ae5-177">Filter the **RecordType** column to display only the records from a specific service or functional area.</span></span> <span data-ttu-id="96ae5-178">예를 들어 SharePoint 공유와 관련된 이벤트를 표시하려면 **14(SharePoint** 공유 활동에서 트리거된 레코드의 열어 값)를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="96ae5-178">For example, to show events related to SharePoint sharing, you would select **14** (the enum value for records triggered by SharePoint sharing activities).</span></span> <span data-ttu-id="96ae5-179">**RecordType** 열에 표시되는 열 열 값에 해당하는 서비스 목록은 감사 로그의 [자세한 속성을 참조하세요.](detailed-properties-in-the-office-365-audit-log.md)</span><span class="sxs-lookup"><span data-stu-id="96ae5-179">For a list of the services that correspond to the enum values displayed in the **RecordType** column, see [Detailed properties in the audit log](detailed-properties-in-the-office-365-audit-log.md).</span></span>

- <span data-ttu-id="96ae5-180">작업 **열을 필터링하여** 특정 작업에 대한 레코드를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="96ae5-180">Filter the **Operations** column to display the records for specific activities.</span></span> <span data-ttu-id="96ae5-181">보안 & 준수 센터의 감사 로그 검색 도구에서 검색 가능한 작업에 해당하는 대부분의 작업 목록은 보안 및 준수 센터에서 감사 로그 검색의 ["감사된 활동" 섹션을 & 참조하세요.](search-the-audit-log-in-security-and-compliance.md#audited-activities)</span><span class="sxs-lookup"><span data-stu-id="96ae5-181">For a list of most operations that correspond to a searchable activity in the audit log search tool in the Security & Compliance Center, see the "Audited activities" section in [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#audited-activities).</span></span>