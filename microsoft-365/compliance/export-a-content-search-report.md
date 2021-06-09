---
title: 콘텐츠 검색 보고서 내보내기
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
f1_keywords:
- ms.o365.cc.CustomizeExportReport
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 5c8c1db6-d8ac-4dbb-8a7a-f65d452169b9
description: 콘텐츠 검색의 실제 결과를 보안 & 준수 센터에서 내보내는 Office 365 검색 결과 보고서를 내보낼 수 있습니다. 보고서에는 내보낼 각 항목에 대한 자세한 정보가 포함된 검색 결과 및 문서가 요약되어 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 094e67812b45ab1544d629ba6ddabcd86c70c633
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311576"
---
# <a name="export-a-content-search-report"></a><span data-ttu-id="7c124-104">콘텐츠 검색 보고서 내보내기</span><span class="sxs-lookup"><span data-stu-id="7c124-104">Export a Content search report</span></span>

<span data-ttu-id="7c124-105">Microsoft 365 준수 센터의 콘텐츠 검색(또는 Core eDiscovery 사례와 연결된 검색)에서 전체 검색 결과 집합을 내보내는 대신 실제 검색 결과를 내보낼 때 생성되는 동일한 보고서를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-105">Instead of exporting the full set of search results from a Content search in the Microsoft 365 compliance Center (or from a search that's associated with a Core eDiscovery case), you can export the same reports that are generated when you export the actual search results.</span></span>
  
<span data-ttu-id="7c124-106">보고서를 내보낼 때 보고서 파일은 콘텐츠 검색과 이름이 같은 로컬 컴퓨터의 폴더로 다운로드되지만 이 폴더는 에 *_ReportsOnly.*</span><span class="sxs-lookup"><span data-stu-id="7c124-106">When you export a report, the report files are downloaded to a folder on your local computer that has the same name as the Content Search, but that's appended with *_ReportsOnly*.</span></span> <span data-ttu-id="7c124-107">예를 들어 콘텐츠 검색의 이름이 *ContosoCase0815이면* 보고서가 이라는 폴더로 *ContosoCase0815_ReportsOnly.*</span><span class="sxs-lookup"><span data-stu-id="7c124-107">For example, if the Content Search is named  *ContosoCase0815*, then the report is downloaded to a folder named *ContosoCase0815_ReportsOnly*.</span></span> <span data-ttu-id="7c124-108">보고서에 포함된 문서 목록은 보고서에 포함된 항목 을 [참조하세요.](#whats-included-in-the-report)</span><span class="sxs-lookup"><span data-stu-id="7c124-108">For a list of documents that are included in the report, see [What's included in the report](#whats-included-in-the-report).</span></span>

## <a name="before-you-export-a-search-report"></a><span data-ttu-id="7c124-109">검색 보고서를 내보내기 전에</span><span class="sxs-lookup"><span data-stu-id="7c124-109">Before you export a search report</span></span>

- <span data-ttu-id="7c124-110">검색 보고서를 내보내기 위해 Security & Compliance Center에서 준수 검색 관리 역할을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-110">To export a search report, you have to be assigned the Compliance Search management role in Security & Compliance Center.</span></span> <span data-ttu-id="7c124-111">이 역할은 기본적으로 기본 제공 eDiscovery 관리자 및 조직 관리 역할 그룹에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-111">This role is assigned by default to the built-in eDiscovery Manager and Organization Management role groups.</span></span> <span data-ttu-id="7c124-112">자세한 내용은 [eDiscovery 권한 할당](assign-ediscovery-permissions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7c124-112">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="7c124-113">보고서를 내보낼 때 데이터는 로컬 컴퓨터로 Azure Storage Microsoft 클라우드의 임시 위치에 일시적으로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-113">When you export a report, the data is temporarily stored in an Azure Storage location in the Microsoft cloud before it's downloaded to your local computer.</span></span> <span data-ttu-id="7c124-114">조직에서 **\* .blob.core.windows.net** Azure의 끝점에 연결할 수 있는지 확인(와일드카드는 내보내기 고유 식별자를 나타임)</span><span class="sxs-lookup"><span data-stu-id="7c124-114">Be sure that your organization can connect to the endpoint in Azure, which is **\*.blob.core.windows.net** (the wildcard represents a unique identifier for your export).</span></span> <span data-ttu-id="7c124-115">검색 결과 데이터는 생성된 Azure Storage 위치에서 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-115">The search results data is deleted from the Azure Storage location two weeks after it's created.</span></span>

- <span data-ttu-id="7c124-116">검색 결과를 PST 파일로 내보내는 데 사용하는 컴퓨터는 다음과 같은 시스템 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-116">The computer you use to export the search results has to meet the following system requirements:</span></span>

  - <span data-ttu-id="7c124-117">최신 버전의 Windows(32비트 또는 64비트)</span><span class="sxs-lookup"><span data-stu-id="7c124-117">Latest version of Windows (32-bit or 64-bit)</span></span>

  - <span data-ttu-id="7c124-118">Microsoft .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="7c124-118">Microsoft .NET Framework 4.7</span></span>

- <span data-ttu-id="7c124-119">eDiscovery 내보내기 도구 1을 실행하려면 다음 지원되는 브라우저 중<sup>하나를 사용해야 합니다.</sup></span><span class="sxs-lookup"><span data-stu-id="7c124-119">You have to use one of the following supported browsers to run the eDiscovery Export Tool<sup>1</sup>:</span></span>

  - <span data-ttu-id="7c124-120">Microsoft Edge <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="7c124-120">Microsoft Edge <sup>2</sup></span></span>

    <span data-ttu-id="7c124-121">또는</span><span class="sxs-lookup"><span data-stu-id="7c124-121">OR</span></span>

  - <span data-ttu-id="7c124-122">Microsoft Internet Explorer 10 이상 버전</span><span class="sxs-lookup"><span data-stu-id="7c124-122">Microsoft Internet Explorer 10 and later versions</span></span>

  > [!NOTE]
  > <span data-ttu-id="7c124-123"><sup>1</sup> Microsoft는 타사 응용 프로그램용 타사 확장 또는 추가 ClickOnce 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-123"><sup>1</sup> Microsoft doesn't manufacture third-party extensions or add-ons for ClickOnce applications.</span></span> <span data-ttu-id="7c124-124">타사 확장 또는 추가 기능이 있는 지원되지 않는 브라우저를 사용하여 검색 결과를 내보낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-124">Exporting search results using an unsupported browser with third-party extensions or add-ons isn't supported.</span></span><br/>
  > <span data-ttu-id="7c124-125"><sup>2</sup> 최신 변경으로 인해 Microsoft Edge ClickOnce 기본적으로 지원이 설정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-125"><sup>2</sup> As a result of recent changes to Microsoft Edge, ClickOnce support is no longer enabled by default.</span></span> <span data-ttu-id="7c124-126">Edge에서 ClickOnce 지원을 사용하도록 설정하는 방법에 대한 지침은 에서 [eDiscovery 내보내기 도구 Microsoft Edge.](configure-edge-to-export-search-results.md)</span><span class="sxs-lookup"><span data-stu-id="7c124-126">For instructions on enabling ClickOnce support in Edge, see [Use the eDiscovery Export Tool in Microsoft Edge](configure-edge-to-export-search-results.md).</span></span>

- <span data-ttu-id="7c124-127">검색에서 반환된 결과의 예상 총 크기가 2 TB를 초과하면 보고서를 내보내지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-127">If the estimated total size of the results returned by search exceeds 2 TB, exporting the reports fails.</span></span> <span data-ttu-id="7c124-128">보고서를 내보낼 수 있도록 범위 범위를 좁히고 결과의 예상 크기가 2 TB 미만이 있도록 검색을 다시 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-128">To successfully export the reports, try to narrow the scope and rerun the search so the estimated size of the results is less than 2 TB.</span></span>

- <span data-ttu-id="7c124-129">검색 결과가 7일보다 오래된 경우 내보내기 보고서 작업을 제출하면 검색을 다시 시작하여 검색 결과를 업데이트하라는 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-129">If the results of a search are older than 7 days and you submit an export report job, an error message is displayed prompting you to rerun the search to update the search results.</span></span> <span data-ttu-id="7c124-130">이 경우 내보내기 작업을 취소하고 검색을 다시 시작한 다음 내보내기 작업을 다시 시작하십시오.</span><span class="sxs-lookup"><span data-stu-id="7c124-130">If this happens, cancel the export, rerun the search, and then start the export again.</span></span>

- <span data-ttu-id="7c124-131">검색 보고서 내보내기에서는 동시에 실행되는 최대 내보내기 수와 단일 사용자가 실행할 수 있는 최대 내보내기 수를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-131">Exporting search reports counts against the maximum number of exports running at the same time and the maximum number of exports that a single user can run.</span></span> <span data-ttu-id="7c124-132">내보내기 제한에 대한 자세한 내용은 콘텐츠 검색 결과 [내보내기 를 참조하세요.](export-search-results.md#export-limits)</span><span class="sxs-lookup"><span data-stu-id="7c124-132">For more information about export limits, see [Export Content search results](export-search-results.md#export-limits).</span></span>
  
## <a name="step-1-generate-the-report-for-export"></a><span data-ttu-id="7c124-133">1단계: 내보내기용 보고서 생성</span><span class="sxs-lookup"><span data-stu-id="7c124-133">Step 1: Generate the report for export</span></span>

<span data-ttu-id="7c124-134">첫 번째 단계는 내보낼 컴퓨터로 다운로드할 보고서를 준비하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-134">The first step is to prepare the report for downloading to your computer exporting.</span></span> <span data-ttu-id="7c124-135">보고서를 내보내면 보고서 문서가 Microsoft 클라우드의 Azure Storage 영역으로 업로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-135">When you export the report, the report documents are uploaded to an Azure Storage area in the Microsoft cloud.</span></span>
  
1. <span data-ttu-id="7c124-136">준수 Microsoft 365 센터에서 보고서를 내보낼 콘텐츠 검색을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-136">In the Microsoft 365 compliance center, select the Content search that you want to export the report from.</span></span>
  
2. <span data-ttu-id="7c124-137">검색 **플라이아웃** 페이지의 아래쪽에 있는 작업 메뉴에서 보고서 **내보내기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7c124-137">On the **Actions** menu at the bottom of the search flyout page, click **Export report**.</span></span>

   ![작업 메뉴에서 보고서 내보내기 옵션](../media/ActionMenuExportReport.png)

   <span data-ttu-id="7c124-139">보고서 **내보내기** 플라이아웃 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-139">The **Export report** flyout page is displayed.</span></span> <span data-ttu-id="7c124-140">검색에 대한 정보를 내보내는 데 사용할 수 있는 내보내기 보고서 옵션은 검색 결과가 사서함에 있는지 사이트인지 아니면 둘의 조합인지에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-140">The export report options available to export information about the search depend on whether search results are located in mailboxes or sites or a combination of both.</span></span>
  
3. <span data-ttu-id="7c124-141">출력 **옵션에서** 다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-141">Under **Output options**, choose one of the following options:</span></span>
  
   ![출력 옵션 내보내기](../media/ExportOutputOptions.png)

    - <span data-ttu-id="7c124-143">**인식할** 수 없는 형식의 항목을 제외한 모든 항목은 암호화되거나 다른 이유로 인덱싱되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-143">**All items, excluding ones that have unrecognized format, are encrypted, or weren't indexed for other reasons**.</span></span> <span data-ttu-id="7c124-144">이 옵션은 인덱싱된 항목에 대한 정보만 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-144">This option only exports information about indexed items.</span></span>
  
    - <span data-ttu-id="7c124-145">인식할 수 없는 형식을 포함한 모든 항목은 암호화되거나 다른 이유로 인덱싱되지 **않은 항목입니다.**</span><span class="sxs-lookup"><span data-stu-id="7c124-145">**All items, including ones that have unrecognized format, are encrypted, or weren't indexed for other reasons**.</span></span> <span data-ttu-id="7c124-146">이 옵션은 인덱싱된 항목과 인덱싱되지 않은 항목에 대한 정보를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-146">This option exports information about indexed and unindexed items.</span></span>
  
    - <span data-ttu-id="7c124-147">**인식할 수 없는** 형식의 항목만 암호화되거나 다른 이유로 인덱싱되지 않은 항목만</span><span class="sxs-lookup"><span data-stu-id="7c124-147">**Only items that have an unrecognized format, are encrypted, or weren't indexed for other reasons**.</span></span> <span data-ttu-id="7c124-148">이 옵션은 인덱서되지 않은 항목에 대한 정보만 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-148">This option only exports information about unindexed items.</span></span>

4. <span data-ttu-id="7c124-149">콘텐츠에 대해 중복 **제거 사용 Exchange 구성합니다.**</span><span class="sxs-lookup"><span data-stu-id="7c124-149">Configure the **Enable de-duplication for Exchange content** option.</span></span>
  
   - <span data-ttu-id="7c124-150">이 옵션을 선택하면 중복 제거 전 및 중복 제거 후의 중복 메시지 수가 내보내기 요약 보고서에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-150">If you select this option, the count of duplicate messages (before de-duplication and after de-duplication) is included in the export summary report.</span></span> <span data-ttu-id="7c124-151">또한 메시지 복사본은 메시지의 복사본 하나만 manifest.xml 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-151">Also, only one copy of a message will be included in the manifest.xml file.</span></span> <span data-ttu-id="7c124-152">그러나 내보내기 결과 보고서에는 중복 메시지의 복사본이 포함된 사서함을 식별할 수 있도록 중복 메시지의 모든 복사본에 대한 행이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-152">But the export results report will contain a row for every copy of a duplicate message so that you can identify the mailboxes that contain a copy of the duplicate message.</span></span> <span data-ttu-id="7c124-153">내보낼 보고서에 대한 자세한 내용은 [What's included in the report을 참조하십시오.](#whats-included-in-the-report)</span><span class="sxs-lookup"><span data-stu-id="7c124-153">For more information about the exported reports, see [What's included in the report](#whats-included-in-the-report).</span></span>

   - <span data-ttu-id="7c124-154">이 옵션을 선택하지 않은 경우 내보내기 보고서에는 중복 항목을 포함하여 검색에서 반환된 모든 메시지에 대한 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-154">If you don't select this option, the export reports will contain information about all messages returned by the search, including duplicates.</span></span>

     <span data-ttu-id="7c124-155">중복 제거 및 중복 항목을 식별하는 방법에 대한 자세한 내용은 [eDiscovery](de-duplication-in-ediscovery-search-results.md)검색 결과에서 중복 제거를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7c124-155">For more information about de-duplication and how duplicate items are identified, see [De-duplication in eDiscovery search results](de-duplication-in-ediscovery-search-results.md).</span></span>

5. <span data-ttu-id="7c124-156">보고서 **생성 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7c124-156">Click **Generate report**.</span></span>

   <span data-ttu-id="7c124-157">검색 보고서는 다운로드할 수 있습니다. 즉, 보고서 문서가 Microsoft 클라우드의 Azure Storage 위치로 업로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-157">The search reports are prepared for downloading, which means the report documents are uploaded to an Azure Storage location in the Microsoft cloud.</span></span> <span data-ttu-id="7c124-158">이 작업에는 몇 분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-158">This may take several minutes.</span></span>

<span data-ttu-id="7c124-159">내보낼 검색 보고서를 다운로드하는 방법에 대한 지침은 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7c124-159">See the next section for instructions to download the exported search reports.</span></span>
  
## <a name="step-2-download-the-report"></a><span data-ttu-id="7c124-160">2단계: 보고서 다운로드</span><span class="sxs-lookup"><span data-stu-id="7c124-160">Step 2: Download the report</span></span>

<span data-ttu-id="7c124-161">다음 단계는 보고서 영역의 보고서를 로컬 Azure Storage 다운로드하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-161">The next step is to download the report from the Azure Storage area to your local computer.</span></span>

1. <span data-ttu-id="7c124-162">준수 **센터의** 콘텐츠 Microsoft 365 **내보내기 탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-162">On the **Content search** page in the Microsoft 365 compliance center, select the **Exports** tab</span></span>
  
   <span data-ttu-id="7c124-163">새로 고침을 **클릭하여** 만든 내보내기 작업이 표시될 수 있도록 내보내기 작업 목록을 업데이트해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-163">You may have to click **Refresh** to update the list of export jobs so that it shows the export job you created.</span></span> <span data-ttu-id="7c124-164">보고서 내보내기 작업은 검색 이름에 추가된 _ReportsOnly 검색과 이름이 동일합니다. </span><span class="sxs-lookup"><span data-stu-id="7c124-164">Export report jobs have the same name as the corresponding search with **_ReportsOnly** appended to the search name.</span></span>
  
2. <span data-ttu-id="7c124-165">1단계에서 만든 내보내기 작업을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-165">Select the export job that you created in Step 1.</span></span>

3. <span data-ttu-id="7c124-166">보고서 **내보내기** 플라이아웃 페이지의 **내보내기** 키 아래의 **클립보드에 복사를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7c124-166">On the **Export report** flyout page under **Export key**, click **Copy to clipboard**.</span></span> <span data-ttu-id="7c124-167">6단계에서 이 키를 사용하여 검색 결과를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-167">You use this key in step 6 to download the search results.</span></span>
  
   > [!IMPORTANT]
   > <span data-ttu-id="7c124-168">누구나 eDiscovery 내보내기 도구를 설치하고 시작한 다음 이 키를 사용하여 검색 보고서를 다운로드할 수 있기 때문에 암호 또는 기타 보안 관련 정보를 보호하는 경우처럼 주의하여 이 키를 보호해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-168">Because anyone can install and start the eDiscovery Export tool, and then use this key to download the search report, be sure to take precautions to protect this key just like you would protect passwords or other security-related information.</span></span>

4. <span data-ttu-id="7c124-169">플라이아웃 페이지 위쪽에서 결과 다운로드 **를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7c124-169">At the top of the flyout page, click **Download results**.</span></span>

5. <span data-ttu-id="7c124-170">**eDiscovery** 내보내기 도구를 설치하라는 메시지가 표시될 경우 설치를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7c124-170">If you're prompted to install the **eDiscovery Export Tool**, click **Install**.</span></span>

6. <span data-ttu-id="7c124-171">**eDiscovery 내보내기 도구에서** 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-171">In the **eDiscovery Export Tool**, do the following:</span></span>

   ![eDiscovery 내보내기 도구](../media/eDiscoveryExportTool.png)

   1. <span data-ttu-id="7c124-173">3단계에서 복사한 내보내기 키를 해당 상자에 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-173">Paste the export key that you copied in step 3 in the appropriate box.</span></span>
  
   2. <span data-ttu-id="7c124-174">**찾아보기를** 클릭하여 검색 보고서 파일을 다운로드할 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-174">Click **Browse** to specify the location where you want to download the search report files.</span></span>

7. <span data-ttu-id="7c124-175">**시작** 을 클릭하여 컴퓨터에 검색 결과를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-175">Click **Start** to download the search results to your computer.</span></span>
  
    <span data-ttu-id="7c124-176">**eDiscovery 내보내기 도구** 는 다운로드할 남은 항목의 예상 개수(크기)를 포함하여 내보내기 프로세스에 대한 상태 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-176">The **eDiscovery Export Tool** displays status information about the export process, including an estimate of the number (and size) of the remaining items to be downloaded.</span></span> <span data-ttu-id="7c124-177">내보내기 프로세스가 완료되면 다운로드된 위치에 있는 파일에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-177">When the export process is complete, you can access the files in the location where they were downloaded.</span></span>
  
## <a name="whats-included-in-the-report"></a><span data-ttu-id="7c124-178">보고서에 포함된 것</span><span class="sxs-lookup"><span data-stu-id="7c124-178">What's included in the report</span></span>

<span data-ttu-id="7c124-179">콘텐츠 검색 결과에 대한 보고서를 생성하고 내보내면 다음 문서가 다운로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-179">When you generate and export a report about the results of a Content search, the following documents are downloaded:</span></span>
  
- <span data-ttu-id="7c124-180">**내보내기 요약:** 내보내기 Excel 포함된 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-180">**Export summary:** An Excel document that contains a summary of the export.</span></span> <span data-ttu-id="7c124-181">여기에는 검색된 콘텐츠 원본 수, 각 콘텐츠 위치의 검색 결과 수, 예상 항목 수, 내보낼 실제 항목 수, 내보낼 항목의 예상 및 실제 크기 등의 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-181">This includes information such as the number of content sources that were searched, the number of search results from each content location, the estimated number of items, the actual number of items that would be exported, and the estimated and actual size of items that would be exported.</span></span>

   <span data-ttu-id="7c124-182">보고서를 내보낼 때 인덱서되지 않은 항목을 포함하면 예상 검색 결과의 총 수와 내보내기 요약 보고서에 나열된 다운로드된 총 검색 결과 수(검색 결과를 내보낼 경우)에 인덱서되지 않은 항목 수가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-182">If you include unindexed items when exporting the report, the number of unindexed items are included in the total number of estimated search results and in the total number of downloaded search results (if you were to export the search results) that are listed in the export summary report.</span></span> <span data-ttu-id="7c124-183">즉, 다운로드되는 총 항목 수는 예상 결과의 총 수와 인덱서되지 않은 총 항목 수와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-183">In other words, the total number of items that would be downloaded is equal to the total number of estimated results and the total number of unindexed items.</span></span>
  
- <span data-ttu-id="7c124-184">**매니페스트:** 검색 결과에 포함된 각 항목에 대한 정보가 포함된 매니페스트 파일(XML 형식)입니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-184">**Manifest:** A manifest file (in XML format) that contains information about each item included in the search results.</span></span> <span data-ttu-id="7c124-185">중복 제거 옵션을 사용하도록 설정한 경우 중복 메시지가 매니페스트 파일에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-185">If you enabled the de-duplication option, duplicate message are not included in the manifest file.</span></span>

- <span data-ttu-id="7c124-186">**결과:** 검색 Excel 내보낼 인덱싱된 각 항목에 대한 정보가 포함된 행이 포함된 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-186">**Results:** An Excel document that contains a row with information about each indexed item that would be exported with the search results.</span></span> <span data-ttu-id="7c124-187">전자 메일의 경우 결과 로그에는 다음을 비롯한 각 메시지에 대한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-187">For email, the result log contains information about each message, including:</span></span> 

  - <span data-ttu-id="7c124-188">원본 사서함에 있는 메시지의 위치 (포함 여부는 주 메시지는 보관 사서함 또는).</span><span class="sxs-lookup"><span data-stu-id="7c124-188">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>

  - <span data-ttu-id="7c124-189">메시지가 전송된 날짜</span><span class="sxs-lookup"><span data-stu-id="7c124-189">The date the message was sent or received.</span></span>

  - <span data-ttu-id="7c124-190">메시지의 제목 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-190">The Subject line from the message.</span></span>

  - <span data-ttu-id="7c124-191">보낸 사람 및 메시지 받는 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-191">The sender and recipients of the message.</span></span>

  <span data-ttu-id="7c124-192">사이트 및 SharePoint 비즈니스용 OneDrive 문서의 경우 결과 로그에는 다음을 비롯한 각 문서에 대한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-192">For documents from SharePoint and OneDrive for Business sites, the results log contains information about each document, including:</span></span>

  - <span data-ttu-id="7c124-193">문서에 대 한 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-193">The URL for the document.</span></span>

  - <span data-ttu-id="7c124-194">문서가 있는 사이트 모음의 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-194">The URL for the site collection where the document is located.</span></span>

  - <span data-ttu-id="7c124-195">문서를 마지막으로 수정한 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-195">The date that the document was last modified.</span></span>

  - <span data-ttu-id="7c124-196">이름 (에 있는 제목 열 결과 로그에서) 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-196">The name of the document (which is located in the Subject column in the result log).</span></span>

  > [!NOTE]
  > <span data-ttu-id="7c124-197">결과 보고서의 행  수는 전체 검색 결과 수에서 인덱서되지 않은 항목 보고서에 나열된 총 항목 수를 운운하는 개수와 **같아야** 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-197">The number of rows in the **Results** report should be equal to the total number of search results minus the total number of items listed in the **Unindexed Items** report.</span></span>
  
- <span data-ttu-id="7c124-198">**Trace.log**: 내보내기 프로세스에 대한 자세한 로깅 정보를 포함하며 내보내기 중에 문제를 쉽게 언게 할 수 있는 추적 로그입니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-198">**Trace.log**: A trace log that contains detailed logging information about the export process and can help uncover issues during export.</span></span> <span data-ttu-id="7c124-199">검색 보고서 내보내기와 관련된 문제와 관련된 Microsoft 지원 티켓을 여는 경우 이 추적 로그를 제공해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-199">If you open a ticket with Microsoft Support about an issue related to exporting search reports, you may be asked to provide this trace log.</span></span>

- <span data-ttu-id="7c124-200">**인덱서되지 않은 항목:** 검색 Excel 인덱서되지 않은 항목에 대한 정보가 포함된 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-200">**Unindexed items:** An Excel document that contains information about any unindexed items included in the search results.</span></span> <span data-ttu-id="7c124-201">검색 결과 보고서를 생성할 때 인덱서되지 않은 항목을 포함하지 않는 경우 이 보고서는 계속 다운로드되지만 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c124-201">If you don't include unindexed items when you generate the search results report, this report will still be downloaded, but will be empty.</span></span>
