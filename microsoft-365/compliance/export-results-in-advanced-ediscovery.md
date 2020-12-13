---
title: Advanced eDiscovery에서 결과 내보내기
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a9951a07-10b3-48cb-b37a-0ffaa24931ad
description: '내보내기 일괄 처리에 대한 매개 변수를 지정하는 절차를 포함하여 Advanced eDiscovery에서 결과를 내보내는 옵션을 정의하는 방법에 대해 자세히 알아보습니다. '
ms.openlocfilehash: 2929b183c7c0f3f132cc40738c18e2b4859a49a6
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662913"
---
# <a name="export-results-in-advanced-ediscovery-classic"></a><span data-ttu-id="71fd4-103">Advanced eDiscovery(클래식)로 결과 내보내기</span><span class="sxs-lookup"><span data-stu-id="71fd4-103">Export results in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="71fd4-p101">Advanced eDiscovery를 사용하려면 Office 365 E3의 고급 준수 추가 기능이나 조직을 위한 E5 구독이 필요합니다. 이 요금제가 없는 상태에서 Advanced eDiscovery를 사용하려는 경우에는 [Office 365 Enterprise E5 평가판을 등록](https://go.microsoft.com/fwlink/p/?LinkID=698279)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="71fd4-106">이 항목에서는 고급 eDiscovery 내보내기 설치 옵션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-106">This topic describes the Advanced eDiscovery Export Setup options.</span></span>
  
 <span data-ttu-id="71fd4-107">**이 항목의 내용은 다음을 참조하세요.**</span><span class="sxs-lookup"><span data-stu-id="71fd4-107">**In this topic:**</span></span>
  
- [<span data-ttu-id="71fd4-108">내보내기 일괄 처리 및 세션 정의</span><span class="sxs-lookup"><span data-stu-id="71fd4-108">Defining export batches and sessions</span></span>](export-results-in-advanced-ediscovery.md#BK_Define)
    
- [<span data-ttu-id="71fd4-109">증분 및 추가 내보내기</span><span class="sxs-lookup"><span data-stu-id="71fd4-109">Incremental and additional exports</span></span>](export-results-in-advanced-ediscovery.md#BK_IncrementalReports)
    
- [<span data-ttu-id="71fd4-110">일괄 내보내기 매개 변수 설정</span><span class="sxs-lookup"><span data-stu-id="71fd4-110">Set up batch export parameters</span></span>](export-results-in-advanced-ediscovery.md#BK_SetUpExport)
    
- [<span data-ttu-id="71fd4-111">보고서 출력 파일 내보내기</span><span class="sxs-lookup"><span data-stu-id="71fd4-111">Export report output files</span></span>](export-results-in-advanced-ediscovery.md#BK_ExportOutputFIles)
    
## <a name="defining-export-batches-and-sessions"></a><span data-ttu-id="71fd4-112">내보내기 일괄 처리 및 세션 정의</span><span class="sxs-lookup"><span data-stu-id="71fd4-112">Defining export batches and sessions</span></span>
<span data-ttu-id="71fd4-113"><a name="BK_Define"> </a></span><span class="sxs-lookup"><span data-stu-id="71fd4-113"><a name="BK_Define"> </a></span></span>

<span data-ttu-id="71fd4-114">내보내기 일괄 처리는 정의된 매개 변수 집합을 사용하여 내보내기 처리를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-114">An export batch allows export processing using a set of defined parameters.</span></span> <span data-ttu-id="71fd4-115">Advanced eDiscovery를 사용하면 일괄 처리를 정의하여 각 내보내기 기능을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-115">Advanced eDiscovery enables you to define batches to customize each export.</span></span>
  
<span data-ttu-id="71fd4-116">매개 변수는 내보내기 일괄 처리에 따라 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-116">Parameters are defined per export batch.</span></span> <span data-ttu-id="71fd4-117">사례의 첫 번째 배치에 대해 "내보내기 일괄 처리 01"이라는 일괄 처리가 기본적으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-117">A batch named "Export batch 01" is created by default for the first batch of a case.</span></span> <span data-ttu-id="71fd4-118">일괄 처리 이름과 설명을 편집할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-118">You can also edit the batch name and description.</span></span>
  
<span data-ttu-id="71fd4-119">내보내기 세션은 내보내기 일괄 처리 내에서 Advanced eDiscovery 내보내기 실행입니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-119">An export session is an execution of Advanced eDiscovery Export within an export batch.</span></span>
  
## <a name="incremental-and-additional-exports"></a><span data-ttu-id="71fd4-120">증분 및 추가 내보내기</span><span class="sxs-lookup"><span data-stu-id="71fd4-120">Incremental and additional exports</span></span>
<span data-ttu-id="71fd4-121"><a name="BK_IncrementalReports"> </a></span><span class="sxs-lookup"><span data-stu-id="71fd4-121"><a name="BK_IncrementalReports"> </a></span></span>

<span data-ttu-id="71fd4-122">내보내기 일괄 처리 내에서 여러 내보내기 세션을 실행하여 동일한 내보내기 템플릿 및 매개 변수를 기반으로 일관된 결과를 보장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-122">You can run multiple export sessions within an export batch, to ensure consistent results based on the same export template and parameters.</span></span> <span data-ttu-id="71fd4-123">일괄 처리 내의 각 세션에 대해 새로 처리된 사례 데이터에 대한 분석을 내보내고 각 "증분"을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-123">For each session within a batch, you can export analytics for newly processed case data and process each "incrementally."</span></span>
  
<span data-ttu-id="71fd4-124">다른 매개 변수 집합을 사용하여 내보내기 위해서는 먼저 새 일괄 처리를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-124">In order to export using a different set of parameters, you first need to create a new batch.</span></span> <span data-ttu-id="71fd4-125">새 일괄 처리의 첫 번째 세션은 이러한 파일을 하나 또는 여러 개의 가져오기에서 가져와서 처리한 것인지 여부에 따라 지금까지 사례에서 처리된 파일에 대한 결과를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-125">The first session in the new batch will produce results for files processed in the case so far, whether or not these files were imported and processed over one or multiple Imports.</span></span> <span data-ttu-id="71fd4-126">각 일괄 처리는 피벗, 유사성, 포함 등을 다시 계산합니다. 세션은 일괄 처리에 정의된 매개 변수를 사용하며 각 세션 실행에 대해 피벗, 유사성, 포함 등을 다시 계산하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-126">Each batch recalculates pivots, similarity, inclusives, etc. Sessions use the parameters defined for the batch and do not recalculate pivots, similarity, inclusives, etc. for each session execution.</span></span>
  
<span data-ttu-id="71fd4-127">예를 들어 사례를 가져와 데이터를 분석했다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-127">For example, assume a case was imported and its data analyzed.</span></span> <span data-ttu-id="71fd4-128">증분 데이터에 대한 중복 항목 및 전자 메일 스레딩 결과를  검색하려면 이전에 데이터를 내보내는 데 사용한 일괄 처리에서 내보내기 세션 만들기를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-128">In order to retrieve Near-duplicates and Email Threading results for the incremental data, click **Create export session** in the same batch that was previously used to export data.</span></span> 
  
## <a name="set-up-batch-export-parameters"></a><span data-ttu-id="71fd4-129">일괄 내보내기 매개 변수 설정</span><span class="sxs-lookup"><span data-stu-id="71fd4-129">Set up batch export parameters</span></span>
<span data-ttu-id="71fd4-130"><a name="BK_SetUpExport"> </a></span><span class="sxs-lookup"><span data-stu-id="71fd4-130"><a name="BK_SetUpExport"> </a></span></span>

<span data-ttu-id="71fd4-131">eDiscovery 내보내기 도구는 Advanced eDiscovery에서 로컬 컴퓨터로 검색 결과를 내보내는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-131">The eDiscovery Export Tool is used to export search results from Advanced eDiscovery to your local computer.</span></span>
  
1. <span data-ttu-id="71fd4-132">Advanced eDiscovery에서 사례를 선택하고  설치 \> **내보내기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="71fd4-132">In Advanced eDiscovery, select a Case and click **Export** \> **Setup**.</span></span>
    
    - <span data-ttu-id="71fd4-133">내보내기  일괄 처리 목록에서 일괄 처리 이름을 선택하거나 결과를 내보내기 일괄 처리 01(기본 일괄 처리)으로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-133">From the **Export batch** list, select the batch name or export results to Export batch 01, (the default batch).</span></span> 
    
    - <span data-ttu-id="71fd4-134">기존 사례에 추가한 새 파일에 대한 결과를 내보내기 위해 현재 일괄 처리를 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-134">To export results for new files that you added to an existing case, continue with your current batch.</span></span> <span data-ttu-id="71fd4-135">일괄 처리에서 세션을 만들려면 동일한 일괄 처리 번호를 선택하고 내보내기 세션 만들기를 클릭합니다. 이 옵션을 사용하여 이전 일괄 처리와 동일한 매개 변수를 증분 방식으로 내보낼 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="71fd4-135">To create a session in the batch, select the same batch number and click **Create export session** You can use this option to export the same parameters as the previous batch, in an incremental manner.</span></span> 
    
    - <span data-ttu-id="71fd4-136">새 일괄 처리로  내보내려면 추가 아이콘을 클릭하고 배치 이름에 새 이름(또는 기본값을 수락)과 배치 ![ ](../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) 설명에 **설명을 입력합니다.** </span><span class="sxs-lookup"><span data-stu-id="71fd4-136">To export to a new batch, click **Add** ![add icon](../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png)and enter a new name in **Batch name** (or accept the default) and a description in **Batch description**.</span></span> <span data-ttu-id="71fd4-137">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-137">Click **OK**.</span></span>
    
    - <span data-ttu-id="71fd4-138">일괄 처리 이름 또는 설명을 편집하려면 **내보내기** 일괄 처리에서 이름을 선택하고 편집 아이콘을 클릭한 다음  ![ ](../media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png) 필드를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-138">To edit a batch name or description, select the name in **Export batch**, click **Edit** ![Edit icon](../media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png), and then modify the fields.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="71fd4-139">내보내기 일괄 처리에 대한 세션을 실행한 후 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-139">After you've run sessions for an export batch, they cannot be deleted.</span></span> <span data-ttu-id="71fd4-140">또한 첫 번째 세션이 실행된 후 일부 매개 변수만 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-140">In addition, only some parameters can be edited once the first session is run.</span></span> 
  
    - <span data-ttu-id="71fd4-141">중복 내보내기 일괄  처리를 만들 경우 중복 내보내기 일괄 처리 만들기 아이콘을 선택하고 패널에 중복된 일괄 처리에 대한 이름과 설명을 ![ ](../media/3f6d5f59-e842-4946-a493-473528af0119.jpg) 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-141">To create a duplicate export batch, choose **Duplicate export batch** ![Create a duplicate export batch icon](../media/3f6d5f59-e842-4946-a493-473528af0119.jpg) and enter a name and a description for the duplicate batch in the panel.</span></span> 
    
    - <span data-ttu-id="71fd4-142">내보내기 일괄 처리를 삭제하려면 **내보내기** 일괄 처리 ![ 삭제 아이콘을 선택하십시오. ](../media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg)</span><span class="sxs-lookup"><span data-stu-id="71fd4-142">To delete an export batch, choose **Delete** ![Delete an export batch icon](../media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg).</span></span>
    
    - <span data-ttu-id="71fd4-143">일괄 처리의 기록을 보고 **일괄** 처리 기록 보기 기록 ![ 아이콘을 선택 ](../media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg) 합니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-143">To view the history of a batch, choose **Batch history** ![View history icon](../media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg).</span></span>
    
2. <span data-ttu-id="71fd4-144">**Population에서** 내보내기 일괄 처리에 대한 설정을 미세 조정하려는 경우 해당 파일만 포함(해당성 잘라 내기 점수 이상) 및/또는 내보내기 일괄 처리 구체화(Refine export batch)를 선택합니다.  </span><span class="sxs-lookup"><span data-stu-id="71fd4-144">Under **Population**, select **Include only files above Relevance cut-off score** and/or **Refine export batch** if you want to fine-tune the settings for your export batch.</span></span> 
    
3. <span data-ttu-id="71fd4-145">해당 점수보다 높은 파일만 포함(Relevance **Cut-off** score)을 선택하면 **문제가** 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-145">If you select **Include only files above Relevance cut-off score**, then the **Issue** is enabled.</span></span> <span data-ttu-id="71fd4-146">파일의 해당 점수가 선택한 문제의 잘라 내기 점수보다 높은 경우 '검토용' 필터에서 제외하지 않는 한 파일이 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-146">If the file's relevance score is higher than the cut-off score for the selected issue, the file will be exported unless it's excluded by the 'For review' filter.</span></span> 
  
    <span data-ttu-id="71fd4-147">내보내기 일괄 처리 구체화 기능을 선택하면 '검토용' 필드 라디오 단추로 덤프 제거 및 필터를 사용할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="71fd4-147">If you select **Refine export batch**, the **De-dupe** and Filter by 'For review' field radio buttons are enabled.</span></span> <span data-ttu-id="71fd4-148">덤프 제거를 선택하면 전체 사례에 있는 모든 중복 파일 집합에서 정의된 정책에 따라 중복 파일이 필터링됩니다.(기본값). 전체 사례의 모든 중복 파일 집합에서 파일 하나만 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-148">If you choose **De-dupe**, then duplicate files will be filtered out according to the policy defined [Case level (default): from every set of duplicate files in the entire case, all but one file will be de-duped.</span></span> <span data-ttu-id="71fd4-149">Custodian 수준: 동일한 양도자에 있는 모든 중복 파일 집합에서 하나의 파일을 삭제합니다.] 내보내기 출력에는 모든 중복 파일의 레코드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-149">Custodian level: from every set of duplicate files of the same custodian, all but one file will be de-duped.] The export output contains a record of all duplicate files.</span></span> <span data-ttu-id="71fd4-150">**'검토용'** 필드로 필터링을 선택하는  경우 메타데이터 아래 수정을 선택하여 **'검토용'** 필드 설정을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-150">If you choose **Filter by 'For review'** field, select **Modify under Metadata** to enter your **'For review'** field settings.</span></span> <span data-ttu-id="71fd4-151">패키지 **콘텐츠에** 원본 파일을 포함하려면 입력 파일 포함을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-151">Select **Include input files** to include source files in the package content.</span></span> <span data-ttu-id="71fd4-152">이 설정을 지우면 내보내기 프로세스의 속도를 낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-152">You can clear this setting to speed up the export process.</span></span> <span data-ttu-id="71fd4-153">네이티브 파일은 어떤 경우든 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-153">Note that the Native files will be exported in any case.</span></span> 
    
4. <span data-ttu-id="71fd4-154">메타데이터 **아래에서** 템플릿 내보내기 목록(세션당 한 **번)의** 다음 옵션에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-154">Under **Metadata**, select from the following options in the **Export template** list (once per session).</span></span> 
    
    - <span data-ttu-id="71fd4-155">**표준**: 기본 데이터 항목, 메타데이터 및 속성 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-155">**Standard**: Basic set of data items, metadata, and properties.</span></span> <span data-ttu-id="71fd4-156">Advanced eDiscovery에서 가져오기 데이터가 이미 처리되어 내보내기 데이터가 이미 파일이 있는 시스템에 업로드된 경우 이 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-156">Use this option when import data was already processed in Advanced eDiscovery and export data is uploaded to a system that already contains the files.</span></span> <span data-ttu-id="71fd4-157">기본적으로 서식 파일 내보내기 열이 만들어지며 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-157">By default, export template columns are created and filled.</span></span>
    
    - <span data-ttu-id="71fd4-158">**All**: 모든 처리 데이터를 포함한 전체 표준 메타데이터 집합 및 분석 및 연결성 점수입니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-158">**All**: Full set of standard metadata including all processing data, as well as Analyze and Relevance scores.</span></span> <span data-ttu-id="71fd4-159">Advanced eDiscovery가 처리를 수행하고 파일 데이터를 외부 시스템에 처음으로 업로드할 때 이 템플릿이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-159">This template is required when Advanced eDiscovery performs the processing and file data is uploaded to an external system for the first time.</span></span>
    
    - <span data-ttu-id="71fd4-160">**문제점:** **모든 문제를 선택하거나** 만든 특정 문제를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-160">**Issues**: Select **All Issues** or select a particular issue you have created.</span></span> 
    
5. <span data-ttu-id="71fd4-161">대상 **아래:**</span><span class="sxs-lookup"><span data-stu-id="71fd4-161">Under **Destination**:</span></span>
    
    - <span data-ttu-id="71fd4-162">**로컬 컴퓨터로 다운로드**</span><span class="sxs-lookup"><span data-stu-id="71fd4-162">**Download to local machine**</span></span>
    
    - <span data-ttu-id="71fd4-163">**사용자 정의 Azure Blob으로** 내보내기: 이 옵션을 검사하는 경우 컨테이너 URL 및 SAS 토큰을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-163">**Export to user-defined Azure blob**: If this is checked, you can specify a container URL and SAS token.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="71fd4-164">내보내기 패키지가 사용자 정의 Azure Blob에 저장되고 나면 데이터는 Advanced eDiscovery에서 더 이상 관리되지 않습니다. Azure Blob에서 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-164">Once an export package is stored to the user defined Azure blob, the data is no longer managed by Advanced eDiscovery; it's managed by the Azure blob.</span></span> <span data-ttu-id="71fd4-165">즉, 사례를 삭제하는 경우 내보낼 파일은 여전히 Azure Blob에 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-165">This means if you delete the case, the exported files will still remain on the Azure blob.</span></span> 
  
    - <span data-ttu-id="71fd4-166">**향후 내보내기** 세션에 대해 SAS 토큰 저장: 선택된 경우 SAS 토큰은 나중에 사용하기 위해 Advanced eDiscovery의 내부 데이터베이스에서 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-166">**Save SAS token for future export session**: If checked, the SAS token will be encrypted in the Advanced eDiscovery's internal database for future use.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="71fd4-167">현재 SAS 토큰은 한 달 후에 만료됩니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-167">Currently the SAS token expires after a month.</span></span> <span data-ttu-id="71fd4-168">한 달 이상 후에 다운로드하려고 할 경우 마지막 세션을 취소한 다음 다시 내보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-168">If you try to download after more than a month you have to undo last session, then export again.</span></span> 
  
6. <span data-ttu-id="71fd4-169">**수정을** 클릭하여 '검토용' 필드 설정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-169">Click **Modify** to set the 'for review' field settings.</span></span> 
    
    ![내보내기 일괄 처리에 대한 검토 필드 설정 설정](../media/39451aba-f6fe-4a01-8ed0-0be6a6ce889a.png)
  
   - <span data-ttu-id="71fd4-171">검토 **필드 설정의**  경우 시나리오 풀다운 선택 목록에서 검토의 시나리오 및 범위를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-171">Under **For review field settings**, in **Select scenario** pull-down list, select the scenario and scope of the review.</span></span> <span data-ttu-id="71fd4-172">설정은 선택에 따라 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-172">The settings are displayed based on your selection.</span></span>
    
      - <span data-ttu-id="71fd4-173">**모두** 검토(기본값): 모든 전자 메일, 첨부 파일 및 문서가 기본적으로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-173">**Review all** (default): All emails, attachments, and documents are selected by default.</span></span> 
    
      - <span data-ttu-id="71fd4-174">**집합의** 모든 고유 콘텐츠 검토: 포괄 및 고유한 포함 복사본, 전자 메일 집합 수준의 고유한 첨부 파일, 정확한 중복 항목 집합의 담당자</span><span class="sxs-lookup"><span data-stu-id="71fd4-174">**Review all unique content in a set**: Inclusives and unique inclusive copies, unique attachments in email set level, representative from every set of exact duplicates.</span></span>
    
      - <span data-ttu-id="71fd4-175">집합의 모든 고유 콘텐츠를 **검토합니다.** 포괄 복사본 없음 : 전자 메일 집합 수준의 고유한 첨부 파일, 정확한 중복 항목 집합의 담당자</span><span class="sxs-lookup"><span data-stu-id="71fd4-175">**Review all unique content in a set - no inclusive copies**: Inclusives, unique attachments in email set level, representative from every set of exact duplicates.</span></span>
    
      - <span data-ttu-id="71fd4-176">**모든 고유 콘텐츠** 및 관련 패밀리 파일을 검토합니다. 포함, 전자 메일 집합 수준의 고유한 첨부 파일, 정확한 중복 항목 집합의 대표, 가족 파일을 포함하기 위해 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-176">**Review all unique content and related family files**: Inclusives, unique attachments in email set level, representative from every set of exact duplicates, expand to include family files.</span></span>
    
      - <span data-ttu-id="71fd4-177">**사용자** 지정(대화 상자의 옵션을 정의할 수 있도록 허용): 기본값은 현재 선택을 유지하고 모든 대화 상자 옵션을 사용하도록 설정하여 선택을 허용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-177">**Custom** (allows you to define the options in the dialog): The default is to keep current selections and enable all dialog options, to allow their selection.</span></span> <span data-ttu-id="71fd4-178">이 옵션을 선택하는 경우 전자 메일, 문서, 첨부 파일 및 기타에 대한 설정을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-178">If you select this option, you can then customize the settings for emails, documents, attachments and miscellaneous.</span></span>
    
    - <span data-ttu-id="71fd4-179">Under **Emails,** select the emails you want to export.</span><span class="sxs-lookup"><span data-stu-id="71fd4-179">Under **Emails**, select the emails you want to export.</span></span>
    
      - <span data-ttu-id="71fd4-180">**모든 전자 메일**: (기본값) 모든 전자 메일이 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-180">**All emails**: (default) All emails are selected.</span></span>
    
      - <span data-ttu-id="71fd4-181">**포함:** 포괄 전자 메일은 스레드의 마지막 전자 메일로, 스레드의 다른 모든 전자 메일을 포함하는 전자 메일입니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-181">**Inclusives**: An inclusive email is a last email of a thread, and it contains all the other emails from the thread.</span></span>
    
      - <span data-ttu-id="71fd4-182">**포괄** 및 고유 포괄 복사본: 동일한 제목, 본문 및 첨부 파일이 있는 포괄 복사본 및 포함 고유한 포괄 복사본은 이러한 전자 메일의 고유한 복사본입니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-182">**Inclusives and unique inclusive copies**: Inclusive copies and inclusives with the same subject, body and attachments; unique inclusive copies are unique copies of these emails .</span></span>
    
    - <span data-ttu-id="71fd4-183">문서 **아래에서** 내보낼 문서를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-183">Under **Documents**, select the documents you want to export.</span></span> 
    
      - <span data-ttu-id="71fd4-184">**모든 문서**: (기본값) 모든 문서가 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-184">**All documents**: (default) All documents are selected.</span></span>
    
      - <span data-ttu-id="71fd4-185">**피벗**: 중복에 가까운 집합을 대표하여 선택한 파일로, 일반적으로 집합을 검토할 때 기준으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-185">**Pivots**: A file chosen as representative of near-duplicates set, which is typically used as the baseline when reviewing the set.</span></span>
    
      - <span data-ttu-id="71fd4-186">**정확한 중복 항목** 집합의 담당자: 중복에 가까운 고유한 파일(피벗 포함)입니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-186">**Representative from every set of exact duplicates**: Unique near-duplicate files (including the pivot).</span></span>
    
    - <span data-ttu-id="71fd4-187">첨부 **파일 아래에서** 내보낼 첨부 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-187">Under **Attachments**, select the attachments you want to export.</span></span> 
    
      - <span data-ttu-id="71fd4-188">**모든 첨부 파일**: (기본값) 모든 첨부 파일이 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-188">**All attachments**: (default) All attachments are selected.</span></span>
    
      - <span data-ttu-id="71fd4-189">**대/중 고유한 첨부 파일 수준**: 지정된 사례 내의 고유한 첨부 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-189">**Unique attachment in case level**: Unique attachment files within the specified case.</span></span>
    
      - <span data-ttu-id="71fd4-190">**전자 메일 집합 수준의** 고유한 첨부 파일 : 지정된 전자 메일 사례 내의 고유한 첨부 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-190">**Unique attachment in email set level**: Unique attachment files within the specified email case.</span></span>
    
   - <span data-ttu-id="71fd4-191">**Micellaneous에서** 첨부 파일을 문서로 처리하거나, 전자 메일을 문서로 취급하거나, 확장하여 패밀리 파일을 포함하게 선택할 수 **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="71fd4-191">Under **Micellaneous**, you can choose to **Treat attachments as documents**, **Treat emails as documents**, or **Expand to include family files**.</span></span> <span data-ttu-id="71fd4-192">확장을 **선택하면** 검토 플래그가 지정되는 각 파일에 대해 동일한 패밀리의 모든 파일도 플래그가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-192">When you choose **Expand to include family files**, for each file that is flagged for review, all files of the same family will also be flagged.</span></span>
    
7. <span data-ttu-id="71fd4-193">**저장을** 선택해 설정을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-193">Choose **Save** to save the settings.</span></span> 
    
8. <span data-ttu-id="71fd4-194">내보내기 매개 변수를 지정한 후 내보내기 일괄 처리를 시작하려면 내보내기 **세션 만들기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="71fd4-194">After you specify export parameters, to start export batch, click **Create export session**.</span></span>
    
    <span data-ttu-id="71fd4-195">내보내기 중에 상태가 작업 상태에 **표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="71fd4-195">During export, the status is displayed in **Task status**.</span></span> <span data-ttu-id="71fd4-196">결과는 내보내기 **요약에 표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="71fd4-196">The results are displayed in **Export summary**.</span></span>
    
9. <span data-ttu-id="71fd4-197">파일 다운로드 **창에서** 클립보드에 복사를 **클릭하여** 내보내기 키를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-197">In the **Download files** window, click **Copy to clipboard** to copy the Export key.</span></span> 
    
    ![파일 다운로드](../media/99cf2c13-4954-479f-9741-80d7458c1a15.png)
  
10. <span data-ttu-id="71fd4-199">**닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-199">Click **Close**.</span></span> 
    
    <span data-ttu-id="71fd4-200">eDiscovery 내보내기 도구가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-200">The eDiscovery Export Tool is started.</span></span>
    
    ![eDiscovery 내보내기](../media/705756ca-ee97-4d24-b70f-8b23513f6d11.gif)
  
11. <span data-ttu-id="71fd4-202">**eDiscovery 내보내기 도구에서 다음을 실행합니다.**</span><span class="sxs-lookup"><span data-stu-id="71fd4-202">In the **eDiscovery Export Tool**:</span></span>
    
    -  <span data-ttu-id="71fd4-203">**원본에** 연결하는 데 사용할 공유 액세스 서명을 붙여넣고 7단계에서 클립보드에 복사한 Export 키를 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-203">In **Paste the Shared Access Signature that will be used to connect to the source**, paste the Export key that you copied to the clipboard in step 7.</span></span>
    
    - <span data-ttu-id="71fd4-204">**찾아보기를** 클릭하여 다운로드한 내보내기 파일을 로컬 컴퓨터에서 저장할 대상 위치를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-204">Click **Browse** to select the target location for storing the downloaded export files on the local machine.</span></span> 
    
    - <span data-ttu-id="71fd4-205">시작을 **클릭합니다.** 내보내기 파일은 로컬 컴퓨터로 다운로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-205">Click **Start**.The export files are downloaded to the local machine.</span></span> <span data-ttu-id="71fd4-206">4단계에서 사용자 정의 **Azure Blob으로** 내보내기를 선택한 경우 세션이 선택한 Blob Storage URL 대상으로 내보내기됩니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-206">If you chose **Export to user-defined Azure blob** in step 4, the session is exported to a Blob storage URL destination of your choosing.</span></span>
    
<span data-ttu-id="71fd4-207">내보내기 보고서의 필드에 대한 전체 설명은 보고서 내보내기 [필드를 참조하세요.](export-report-fields-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="71fd4-207">For a full description of the fields in the export report, see [Export report fields](export-report-fields-in-advanced-ediscovery.md).</span></span>
  
## <a name="export-report-output-files"></a><span data-ttu-id="71fd4-208">보고서 출력 파일 내보내기</span><span class="sxs-lookup"><span data-stu-id="71fd4-208">Export report output files</span></span>
<span data-ttu-id="71fd4-209"><a name="BK_ExportOutputFIles"> </a></span><span class="sxs-lookup"><span data-stu-id="71fd4-209"><a name="BK_ExportOutputFIles"> </a></span></span>

<span data-ttu-id="71fd4-210">다음 표에는 내보내기 일괄 처리를 실행할 때 생성되는 출력 파일이 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-210">The following table lists the output files that are generated when you run an Export batch.</span></span>
  
|<span data-ttu-id="71fd4-211">**파일 이름**</span><span class="sxs-lookup"><span data-stu-id="71fd4-211">**File name**</span></span>|<span data-ttu-id="71fd4-212">**파일 형식**</span><span class="sxs-lookup"><span data-stu-id="71fd4-212">**File type**</span></span>|<span data-ttu-id="71fd4-213">**설명**</span><span class="sxs-lookup"><span data-stu-id="71fd4-213">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="71fd4-214">요약 내보내기</span><span class="sxs-lookup"><span data-stu-id="71fd4-214">Export summary</span></span>  <br/> |<span data-ttu-id="71fd4-215">csv</span><span class="sxs-lookup"><span data-stu-id="71fd4-215">csv</span></span>  <br/> |<span data-ttu-id="71fd4-216">eDiscovery 내보내기 도구에서 생성된 로그 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-216">A log file generated by the eDiscovery Export Tool.</span></span>  <br/> |
|<span data-ttu-id="71fd4-217">Trace</span><span class="sxs-lookup"><span data-stu-id="71fd4-217">Trace</span></span>  <br/> |<span data-ttu-id="71fd4-218">txt</span><span class="sxs-lookup"><span data-stu-id="71fd4-218">txt</span></span>  <br/> |<span data-ttu-id="71fd4-219">eDiscovery 내보내기 도구에서 생성된 로그 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-219">A log file generated by the eDiscovery Export Tool.</span></span>  <br/> |
|<span data-ttu-id="71fd4-220">추출된 텍스트 파일</span><span class="sxs-lookup"><span data-stu-id="71fd4-220">Extracted text files</span></span>  <br/> |<span data-ttu-id="71fd4-221">파일 폴더</span><span class="sxs-lookup"><span data-stu-id="71fd4-221">File folder</span></span>  <br/> |<span data-ttu-id="71fd4-222">내보낼 파일의 추출된 텍스트 파일이 들어 있는 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-222">Folder that contains the extracted text files of the exported files.</span></span>  <br/> |
|<span data-ttu-id="71fd4-223">입력 파일 또는 기본 파일</span><span class="sxs-lookup"><span data-stu-id="71fd4-223">Input or native files</span></span>  <br/> |<span data-ttu-id="71fd4-224">파일 폴더</span><span class="sxs-lookup"><span data-stu-id="71fd4-224">File folder</span></span>  <br/> |<span data-ttu-id="71fd4-225">내보낼 파일의 기본 및 입력 파일이 들어 있는 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-225">Folder that contains the native and input files of the exported files.</span></span>  <br/> |
|<span data-ttu-id="71fd4-226">목록 내보내기</span><span class="sxs-lookup"><span data-stu-id="71fd4-226">Export list</span></span>  <br/> |<span data-ttu-id="71fd4-227">xlsx</span><span class="sxs-lookup"><span data-stu-id="71fd4-227">xlsx</span></span>  <br/> |<span data-ttu-id="71fd4-228">xlsx 형식의 내보낼 파일 메타데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-228">Exported files metadata in xlsx format.</span></span> <span data-ttu-id="71fd4-229">파일의 필드는 사용자가 내보낼 서식 파일에 따라 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-229">Fields in files are according to template user selects to export.</span></span> <span data-ttu-id="71fd4-230">필요한 경우 여러 개의 파일이 만들어지며 각 파일에는 100-150K 행이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-230">If needed, several files are created, each contains 100-150K rows.</span></span> <span data-ttu-id="71fd4-231">특정 값에 Excel 셀에 포함할 수 있는 문자 수보다 많은 문자가 포함되어 있는 경우(현재 제한은 32,767자) 값이 허용되는 최대 길이로 잘리게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-231">If a certain value contains more characters than an Excel cell can contain (currently the limit is 32,767 characters), then the value will be trimmed to the maximum length allowed.</span></span> <span data-ttu-id="71fd4-232">값이 잘리면 셀의 배경색이 빨강으로 표시됩니다." 전자 메일 참가자"는 전자 메일이 큰 배포로 전송된 경우 길이 제한을 초과할 수 있는 필드의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-232">If a value is trimmed, the cell's background color is red to indicate this to the user."Email participants" is an example of a field that can exceed the length limit, if the email was sent to a large distribution.</span></span> <span data-ttu-id="71fd4-233">출력 [필드에 대한](export-report-fields-in-advanced-ediscovery.md) 자세한 내용은 보고서 내보내기 필드를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-233">See [Export report fields](export-report-fields-in-advanced-ediscovery.md) for details about the output fields.</span></span>  <br/> |
|<span data-ttu-id="71fd4-234">파일 로드</span><span class="sxs-lookup"><span data-stu-id="71fd4-234">Load file</span></span>  <br/> |<span data-ttu-id="71fd4-235">csv</span><span class="sxs-lookup"><span data-stu-id="71fd4-235">csv</span></span>  <br/> |<span data-ttu-id="71fd4-236">다른 응용 프로그램으로 로드하기 위해 csv 형식으로 파일 메타데이터를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-236">Exported files metadata in csv format for loading into a different application.</span></span> <span data-ttu-id="71fd4-237">파일의 필드는 사용자가 내보낼 서식 파일에 따라 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-237">Fields in files are according to template user selects to export.</span></span>  <br/> |
|<span data-ttu-id="71fd4-238">성공 표시기</span><span class="sxs-lookup"><span data-stu-id="71fd4-238">Success indicator</span></span>  <br/> |<span data-ttu-id="71fd4-239">txt</span><span class="sxs-lookup"><span data-stu-id="71fd4-239">txt</span></span>  <br/> |<span data-ttu-id="71fd4-240">제3자 Azure Blob으로 내보낼 때만 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-240">Only created when exporting to a 3rd party Azure blob.</span></span> <span data-ttu-id="71fd4-241">내보내기가 완전히 성공하면 파일이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-241">If export succeed completely, the file will be created.</span></span> <span data-ttu-id="71fd4-242">오류가 발생하거나 부분적으로 성공한 경우 파일이 만들어지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-242">In case of failure, or partial success the file will not be created.</span></span> <span data-ttu-id="71fd4-243">파일이 루트 폴더에 만들어지며, 다른 내보내기 일괄 처리/세션 상태에 대한 자동화된 추적이 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-243">File will be created in the root folder, allowing automated tracking on different Export batches/sessions statuses.</span></span> <span data-ttu-id="71fd4-244">이 파일은 빈 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="71fd4-244">This is an empty file.</span></span> <span data-ttu-id="71fd4-245">이름: TenantId_CaseId_ExternalCaseId_CaseName_ExportBatchId_SessionId_DateTime.txt.</span><span class="sxs-lookup"><span data-stu-id="71fd4-245">Its name is: TenantId_CaseId_ExternalCaseId_CaseName_ExportBatchId_SessionId_DateTime.txt.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="71fd4-246">참고 항목</span><span class="sxs-lookup"><span data-stu-id="71fd4-246">See also</span></span>

[<span data-ttu-id="71fd4-247">고급 eDiscovery (클래식)</span><span class="sxs-lookup"><span data-stu-id="71fd4-247">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="71fd4-248">일괄 처리 기록 보기 및 지난 결과 내보내기</span><span class="sxs-lookup"><span data-stu-id="71fd4-248">Viewing batch history and exporting past results</span></span>](view-batch-history-and-export-past-results.md)
  
[<span data-ttu-id="71fd4-249">고급 eDiscovery 빠른 설정</span><span class="sxs-lookup"><span data-stu-id="71fd4-249">Quick setup for Advanced eDiscovery</span></span>](quick-setup-for-advanced-ediscovery.md)

[<span data-ttu-id="71fd4-250">보고서 필드 내보내기</span><span class="sxs-lookup"><span data-stu-id="71fd4-250">Export report fields</span></span>](export-report-fields-in-advanced-ediscovery.md)
