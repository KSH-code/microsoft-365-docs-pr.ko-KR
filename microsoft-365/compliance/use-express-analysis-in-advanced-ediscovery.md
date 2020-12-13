---
title: Advanced eDiscovery에서 Express 분석 사용
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 50580099-3dc0-44a1-a9b6-5ca6d396316b
description: Advanced eDiscovery의 Express 분석 모드를 실행한 다음 결과를 내보내는 방법을 배워야 합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: de637df426d38da2863a65eea67c65a3f66953a7
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663327"
---
# <a name="use-express-analysis-in-advanced-ediscovery-classic"></a><span data-ttu-id="f43e7-103">Advanced eDiscovery에서 Express Analysis 사용(클래식)</span><span class="sxs-lookup"><span data-stu-id="f43e7-103">Use Express Analysis in Advanced eDiscovery (classic)</span></span> 

> [!NOTE]
> <span data-ttu-id="f43e7-p101">Advanced eDiscovery를 사용하려면 Office 365 E3의 고급 준수 추가 기능이나 조직을 위한 E5 구독이 필요합니다. 이 요금제가 없는 상태에서 Advanced eDiscovery를 사용하려는 경우에는 [Office 365 Enterprise E5 평가판을 등록](https://go.microsoft.com/fwlink/p/?LinkID=698279)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="f43e7-106">Express 분석을 **사용하여** 사례를 신속하게 분석하고 결과를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-106">You can use **Express analysis** to quickly analyze a case and export the results.</span></span> 
  
<span data-ttu-id="f43e7-107">익스프레스 분석을 사용하여 중복에 가까운 전자 메일 스레드를 계산하고 테마를 계산할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-107">You can use express analysis to calculate near-duplicates and email threads and calculate themes.</span></span> <span data-ttu-id="f43e7-108">또한 Express 분석을 위한 고급 설정에서 테마, 문서 유사성 및 내보내기 파일에 대한 특정 매개 변수를 [설정할 수도 있습니다.](use-express-analysis-in-advanced-ediscovery.md#BK_AdvancedSettings)</span><span class="sxs-lookup"><span data-stu-id="f43e7-108">You can also set certain parameters for themes, document similarity and the export files in the [Advanced settings for Express analysis](use-express-analysis-in-advanced-ediscovery.md#BK_AdvancedSettings).</span></span>
  
## <a name="run-express-analysis"></a><span data-ttu-id="f43e7-109">Express 분석 실행</span><span class="sxs-lookup"><span data-stu-id="f43e7-109">Run Express analysis</span></span>

1. <span data-ttu-id="f43e7-110">In the **Express analysis** (1) tab, select a container to enable the \*\* Express analysis \*\* (2) and **Advanced settings** buttons.</span><span class="sxs-lookup"><span data-stu-id="f43e7-110">In the **Express analysis** (1) tab, select a container to enable the \*\* Express analysis \*\* (2), and **Advanced settings** buttons.</span></span> 
    
    ![Express 분석 페이지의 스크린샷](../media/60009974-5d1f-4971-8ebe-e5ec74e7fd2a.jpg)
  
2. <span data-ttu-id="f43e7-112">Under **Analyze parameters**:</span><span class="sxs-lookup"><span data-stu-id="f43e7-112">Under **Analyze parameters**:</span></span>
    
  - <span data-ttu-id="f43e7-113">분석을 **실행하려는** 경우 중복에 가까운 전자 메일 스레드 계산을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-113">Check **Calculate near-duplicates and email threads** if you want to run the analysis.</span></span> <span data-ttu-id="f43e7-114">이 옵션은 기본적으로 선택되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-114">It is selected by default.</span></span> 
    
  - <span data-ttu-id="f43e7-115">테마 **계산을 확인하여** 모든 파일을 처리하고 테마를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-115">Check **Calculate Themes** to process all files and assign themes to them.</span></span> <span data-ttu-id="f43e7-116">이 옵션은 기본적으로 선택되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-116">It is selected by default.</span></span> 
    
3. <span data-ttu-id="f43e7-117">내보내기 **대상 아래:**</span><span class="sxs-lookup"><span data-stu-id="f43e7-117">Under **Export destination**:</span></span>
    
  - <span data-ttu-id="f43e7-118">로컬 **컴퓨터로 다운로드를 확인하여** 로컬 컴퓨터에 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-118">Check **Download to local machine** to download to your local computer.</span></span> 
    
  - <span data-ttu-id="f43e7-119">사용자 정의 **Azure Blob으로** 내보내기를 확인한 경우 컨테이너 URL 및 SAS 토큰도 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-119">If you check **Export to user-defined Azure blob** then you can also specify a container URL and SAS token.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="f43e7-120">내보내기 패키지가 사용자 정의 Azure Blob에 저장되고 나면 데이터는 Advanced eDiscovery에서 더 이상 관리되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-120">Once an export package is stored to the user defined Azure blob, the data is no longer managed by Advanced eDiscovery.</span></span> <span data-ttu-id="f43e7-121">Azure Blob에서 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-121">it is managed by the Azure blob.</span></span> <span data-ttu-id="f43e7-122">즉, 사례를 삭제하는 경우 내보낼 파일은 여전히 Azure Blob에 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-122">This means if you delete the case, the exported files will still remain on the Azure blob.</span></span> 
  
  - <span data-ttu-id="f43e7-123">**향후 내보내기** 세션에 대해 SAS 토큰 저장: 선택된 경우 SAS 토큰은 나중에 사용하기 위해 Advanced eDiscovery의 내부 데이터베이스에서 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-123">**Save SAS token for future export session**: If checked, the SAS token will be encrypted in the Advanced eDiscovery's internal database for future use.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f43e7-124">현재 SAS 토큰은 한 달 후에 만료됩니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-124">Currently the SAS token expires after a month.</span></span> <span data-ttu-id="f43e7-125">한 달 이상 후에 다운로드하려고 할 경우 마지막 세션을 취소한 다음 다시 내보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-125">If you try to download after more than a month you have to undo last session, then export again.</span></span> 
  
4. <span data-ttu-id="f43e7-126">기본 설정으로 Express 분석을 시작하려면 **Express 분석을** 선택하면 작업 상태 **페이지가** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-126">To start the express analysis with default settings, choose **Express analysis**, and the **Task status** page will display</span></span> 
    
    <span data-ttu-id="f43e7-127">작업 상태 **페이지에서** **프로세스,** 분석  및  내보내기 탭을 확장하여 Express 실행에 대한 세부 정보를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-127">On the **Task status** page you can expand the **Process**, **Analyze** and **Export** tabs to display details about the express run.</span></span> 
    
    ![Advanced eDiscovery Express 분석 작업 상태 페이지의 스크린샷](../media/bf30ab02-9828-4a6d-a485-0babc2c49ae5.jpg)
  
5. <span data-ttu-id="f43e7-129">실행에 대한 자세한 정보를 나열하는 **Express 분석** 요약 페이지를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-129">Choose the **Express analysis summary** page to list detailed information about the run.</span></span> 
    
    <span data-ttu-id="f43e7-130">Express 분석 요약  페이지의 맨 아래에서  마지막 세션 다운로드를 선택하고 로컬 컴퓨터의 분석 파일을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-130">On the bottom of the **Express analysis summary** page, choose **Download last session** to download the analysis files tp your local computer.</span></span> <span data-ttu-id="f43e7-131">먼저 eDiscovery 내보내기 도구를 다운로드하고 내보내기 키를 eDiscovery 내보내기 도구에 붙여 넣아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-131">You will first have to download eDiscovery Export tool and paste the Export key to the eDiscovery Export tool.</span></span> 
    
## <a name="advanced-settings-for-express-analysis"></a><span data-ttu-id="f43e7-132">Express 분석에 대한 고급 설정</span><span class="sxs-lookup"><span data-stu-id="f43e7-132">Advanced settings for Express analysis</span></span>
<span data-ttu-id="f43e7-133"><a name="BK_AdvancedSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="f43e7-133"><a name="BK_AdvancedSettings"> </a></span></span>

<span data-ttu-id="f43e7-134">선택적으로 고급 설정을 **설정하여** 기본 Express 분석 매개 변수를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-134">You can optionally set **Advanced settings** to change the default Express analysis parameters.</span></span> 
  
1. <span data-ttu-id="f43e7-135">분석 **섹션에서** 다음을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-135">In the **Analyze** section:</span></span> 
    
  - <span data-ttu-id="f43e7-136">중복 **항목과** 전자 메일 스레드에 **문서** 유사성 값을 입력하거나 기본값인 65%를 수락합니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-136">In the **Near duplicates and email threads**, enter the **Document similarity** value, or accept the default of 65%.</span></span> 
    
  - <span data-ttu-id="f43e7-137">최대 테마 **수에서** 만들 테마 수에 대한 값을 입력하거나 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-137">In the **Max number of themes** enter or select a value for the number of themes to create.</span></span> <span data-ttu-id="f43e7-138">기본값은 200입니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-138">The default is 200.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="f43e7-139">테마 수를 늘리면 성능과 테마를 일반화할 수 있는 능력에 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-139">Increasing the number of themes affects performance, as well as the ability of a theme to generalize.</span></span> <span data-ttu-id="f43e7-140">테마 수가 높을수록 테마 수가 세분화됩니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-140">The higher the number of themes, the more granular they are.</span></span> <span data-ttu-id="f43e7-141">예를 들어 50개 테마 집합에 "바스켓, 스퍼, 클립퍼, 호반" 같은 테마가 포함된 경우 300개의 테마에는 "Spurs", "Clippers", "Lakers"라는 별도의 테마가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-141">For example, if a set of 50 themes include a theme such as "Basketball, Spurs, Clippers, Lakers"; 300 themes may include separate themes: "Spurs", "Clippers", "Lakers".</span></span> <span data-ttu-id="f43e7-142">"바스켓"을 인식하지 못하고 ECA에 이 기능을 사용하는 경우 "바스켓"을 보는 것이 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-142">If you had no awareness of the theme "Basketball" and use this feature for ECA, seeing the theme "Basketball" could be useful.</span></span> <span data-ttu-id="f43e7-143">그러나 처리에 테마가 너무 많을 경우 "바스켓"이라는 단어가 전혀 표시되지 않을 수 있으며, 스퍼와 클립퍼가 부팅을 진행하고 머리에 사용되는 항목이 아니라 검토하기에 좋은 바스켓 테마라는 것을 알지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-143">But, if the processing had too many themes, you may never see the word "Basketball" and may not know that Spurs and Clippers are good Basketball themes to review, rather than items that go on boots and used for hair.</span></span> 
  
  - <span data-ttu-id="f43e7-144">추천 **테마에서** **테마** 처리를 제어하기 위해 테마 단어를 제안하려면 수정을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-144">In the **Suggested themes** choose **Modify** to suggest theme words to control Themes processing.</span></span> <span data-ttu-id="f43e7-145">Advanced eDiscovery는 이러한 추천 단어에 초점을 맞추고 "최대 테마 수" 설정에 따라 하나 이상의 관련 테마를 만들려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-145">Advanced eDiscovery will focus on these suggested words and try to create one or more relevant themes, based on the "Max number of themes" settings.</span></span> 
    
    <span data-ttu-id="f43e7-146">예를 들어 추천 단어가 "컴퓨터"이고 "2"를 "최대 테마 수"로 지정한 경우 Advanced eDiscovery는 단어 "computer"에 관련된 두 개의 테마를 생성하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-146">For example, if the suggested word is "computer", and you specified "2" as the "Max number of Themes", Advanced eDiscovery will try to generate two themes that relate to the word "computer".</span></span> <span data-ttu-id="f43e7-147">예를 들어 두 테마는 "컴퓨터 소프트웨어" 및 "컴퓨터 하드웨어"일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-147">The two themes might be "computer software" and "computer hardware", for example.</span></span>
    
    ![추천된 테마 추가](../media/06e9ffd3-a76c-423b-b450-9e465eb9a02f.png)
  
  - <span data-ttu-id="f43e7-149">**모드** 드롭다운 목록에서 테마 **옵션을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-149">**Mode** From the drop-down list, select a **Themes** option:</span></span> 
    
  - <span data-ttu-id="f43e7-150">**모델 만들기 및** 적용: 파일 세그먼트에서 모델별로 테마를 계산한 다음 여러 모델에 파일을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-150">**Create and apply model**: Calculates themes by models from a segment of the files and then distributes files among them.</span></span>
    
  - <span data-ttu-id="f43e7-151">**모델 만들기:** 파일 세그먼트에서 테마 모델을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-151">**Create model**: Calculates a themes model from a segment of the files.</span></span> <span data-ttu-id="f43e7-152">파일 세분화 적용 프로세스는 다른 시기에 별도로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-152">The Apply process of dividing files is done separately at another time.</span></span>
    
  - <span data-ttu-id="f43e7-153">**모델 적용**: 이 옵션은 이전에 모델을 만들 때만 표시되고 아직 적용되지 않은 경우 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-153">**Apply model**: This option is only shown if a model was created previously and not yet applied.</span></span> <span data-ttu-id="f43e7-154">이렇게 하면 테마에 따라 파일이 분할됩니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-154">This will divide the files based on the themes.</span></span>
    
2. <span data-ttu-id="f43e7-155">내보내기 **섹션에서 다음을** 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-155">In the **Export** section:</span></span> 
    
1. <span data-ttu-id="f43e7-156">내보내기 **일괄 처리 선택에서 다음을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f43e7-156">In the **Select export batch**:</span></span>
    
  - <span data-ttu-id="f43e7-157">내보내기  일괄 처리 목록에서 일괄 처리 이름을 선택하거나 결과를 내보내기 일괄 처리 01(기본 일괄 처리)으로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-157">From the **Export batch** list, select the batch name or export results to Export batch 01, (the default batch).</span></span> 
    
  - <span data-ttu-id="f43e7-158">기존 사례에 추가한 새 파일에 대한 결과를 내보내기 위해 현재 일괄 처리를 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-158">To export results for new files that you added to an existing case, continue with your current batch.</span></span> <span data-ttu-id="f43e7-159">일괄 처리에서 세션을 만들려면 동일한 일괄 처리 번호를 선택하고 내보내기 세션 만들기를 클릭합니다. 이 옵션을 사용하여 이전 일괄 처리와 동일한 매개 변수를 증분 방식으로 내보낼 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="f43e7-159">To create a session in the batch, select the same batch number and click **Create export session** You can use this option to export the same parameters as the previous batch, in an incremental manner.</span></span> 
    
  - <span data-ttu-id="f43e7-160">새 일괄 처리로  내보내려면 추가 아이콘을 클릭하고 배치 이름에 새 이름(또는 기본값을 수락)과 배치 ![ ](../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) 설명에 **설명을 입력합니다.** </span><span class="sxs-lookup"><span data-stu-id="f43e7-160">To export to a new batch, click **Add** ![add icon](../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) and enter a new name in **Batch name** (or accept the default) and a description in **Batch description**.</span></span> <span data-ttu-id="f43e7-161">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-161">Click **OK**.</span></span>
    
  - <span data-ttu-id="f43e7-162">일괄 처리 이름 또는 설명을 편집하려면 **내보내기** 일괄 처리에서 이름을 선택하고 편집 아이콘을 클릭한 다음  ![ ](../media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png) 필드를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-162">To edit a batch name or description, select the name in **Export batch**, click **Edit** ![Edit icon](../media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png), and then modify the fields.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f43e7-163">내보내기 일괄 처리에 대한 세션을 실행한 후 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-163">After you've run sessions for an export batch, they cannot be deleted.</span></span> <span data-ttu-id="f43e7-164">또한 첫 번째 세션이 실행된 후 일부 매개 변수만 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-164">In addition, only some parameters can be edited once the first session is run.</span></span> 
  
  - <span data-ttu-id="f43e7-165">중복 내보내기 일괄  처리를 만들 경우 중복 내보내기 일괄 처리 만들기 아이콘을 선택하고 패널에 중복된 일괄 처리에 대한 이름과 설명을 ![ ](../media/3f6d5f59-e842-4946-a493-473528af0119.jpg) 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-165">To create a duplicate export batch, choose **Duplicate export batch** ![Create a duplicate export batch icon](../media/3f6d5f59-e842-4946-a493-473528af0119.jpg) and enter a name and a description for the duplicate batch in the panel.</span></span> 
    
  - <span data-ttu-id="f43e7-166">내보내기 일괄 처리를 삭제하려면 **내보내기** 일괄 처리 ![ 삭제 아이콘을 선택하십시오. ](../media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg)</span><span class="sxs-lookup"><span data-stu-id="f43e7-166">To delete an export batch, choose **Delete** ![Delete an export batch icon](../media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg).</span></span>
    
  - <span data-ttu-id="f43e7-167">일괄 처리의 기록을 보고 **일괄** 처리 기록 보기 기록 ![ 아이콘을 선택 ](../media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg) 합니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-167">To view the history of a batch, choose **Batch history** ![View history icon](../media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg).</span></span>
    
2. <span data-ttu-id="f43e7-168">설명 **정의에서:** 내보내기  일괄 처리에 대한 설정을 미세 조정하려는  경우 해당 파일만 포함(해당성 잘림 점수 이상) 및/또는 내보내기 일괄 처리 구체화 선택</span><span class="sxs-lookup"><span data-stu-id="f43e7-168">Under Define p **opulation:** Select **Include only files above Relevance cut-off score** and/or **Refine export batch** if you want to fine-tune the settings for your export batch.</span></span> <span data-ttu-id="f43e7-169">해당 파일 중 하나 이상의 파일만 포함(Relevance **Cut-off score)을** 선택하면 Issue를 사용하도록 설정하고 파일의 해당 점수가 선택한 문제의 잘라 내보낼 점수보다 높은 경우 파일을 내보낼 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="f43e7-169">If you select **Include only files above Relevance cut-off score**, then the **Issue** is enabled, and if the file's relevance score is higher than the cut-off score for the selected issue, then the file is exported.</span></span> <span data-ttu-id="f43e7-170">'검토용 필터'에서 제외하지 않는 한 파일을 **내보낼 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-170">The file will be exported unless it's excluded by the ' **For review** filter.</span></span> <span data-ttu-id="f43e7-171">내보내기 일괄 처리 구체화 기능을 선택하면 **'검토용'** 필드 라디오 단추로 덤프 제거 및 필터링을 사용할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="f43e7-171">If you select **Refine export batch**, then the **De-dupe** and **Filter by 'For review' field** radio buttons are enabled.</span></span> <span data-ttu-id="f43e7-172">중복 제거를 선택하면 정의된 정책에 따라 중복 파일이 필터링됩니다. [사례 수준(기본값): 전체 사례의 모든 중복 파일 집합에서 하나의 파일을 삭제합니다. </span><span class="sxs-lookup"><span data-stu-id="f43e7-172">If you choose **De-dupe**, then duplicates files will be filtered-out according to the policy defined: [Case level (default): from every set of duplicate files in the entire case, all but one file will be de-duped.</span></span> <span data-ttu-id="f43e7-173">Custodian level: from every set of duplicate files of the same custodian, all but one file will be de-duped.</span><span class="sxs-lookup"><span data-stu-id="f43e7-173">Custodian level: from every set of duplicate files of the same custodian, all but one file will be de-duped.</span></span> <span data-ttu-id="f43e7-174">모든 중복 파일의 레코드는 내보내기 출력에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-174">A record of all duplicate files is available in export output.</span></span> <span data-ttu-id="f43e7-175">**'검토용'** 필드로 필터링을 선택하는  경우 메타데이터 아래 수정을 선택하여 **'검토용'** 필드 설정을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-175">If you choose **Filter by 'For review'** field, select **Modify under Metadata** to enter your **'For review'** field settings.</span></span> <span data-ttu-id="f43e7-176">패키지 **콘텐츠에** 원본 파일을 포함하려면 입력 파일 포함을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-176">Select **Include input files** to include source files in the package content.</span></span> <span data-ttu-id="f43e7-177">이 옵션을 선택 취소하여 내보내기 프로세스 속도를 낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-177">You can clear this option to speed up the export process.</span></span> <span data-ttu-id="f43e7-178">네이티브 파일은 어떤 경우든 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-178">Note that the Native files will be exported in any case.</span></span>
    
3. <span data-ttu-id="f43e7-179">메타데이터 **정의 아래에서** 템플릿 내보내기  목록의 다음 옵션(세션당 한 번)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-179">Under **Define metadata**, select from the following options in the **Export template** list (once per session).</span></span> 
    
  - <span data-ttu-id="f43e7-180">**표준**: 기본 데이터 항목, 메타데이터 및 속성 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-180">**Standard**: Basic set of data items, metadata, and properties.</span></span> <span data-ttu-id="f43e7-181">Advanced eDiscovery에서 가져오기 데이터가 이미 처리되어 내보내기 데이터가 이미 파일이 있는 시스템에 업로드된 경우 이 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-181">Use this option when import data was already processed in Advanced eDiscovery and export data is uploaded to a system that already contains the files.</span></span> <span data-ttu-id="f43e7-182">기본적으로 서식 파일 내보내기 열이 만들어지며 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-182">By default, export template columns are created and filled.</span></span>
    
  - <span data-ttu-id="f43e7-183">**All**: 모든 처리 데이터를 포함한 전체 표준 메타데이터 집합 및 분석 및 연결성 점수입니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-183">**All**: Full set of standard metadata including all processing data, as well as Analyze and Relevance scores.</span></span> <span data-ttu-id="f43e7-184">Advanced eDiscovery가 처리를 수행하고 파일 데이터를 외부 시스템에 처음으로 업로드할 때 이 템플릿이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-184">This template is required when Advanced eDiscovery performs the processing and file data is uploaded to an external system for the first time.</span></span>
    
  - <span data-ttu-id="f43e7-185">**문제점:** **모든 문제를 선택하거나** 만든 특정 문제를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f43e7-185">**Issues**: Select **All Issues** or select a particular issue you have created.</span></span> 
    
<span data-ttu-id="f43e7-186">확인을 선택하면 고급 설정을 저장하고 **기본값을** 사용하려면  기본값을 복원하거나 취소를 선택하면 고급 설정 설정이 취소됩니다. </span><span class="sxs-lookup"><span data-stu-id="f43e7-186">Choose **OK** to save the advanced settings, **Restore defaults** to use default values, or **Cancel** to cancel setting the advanced settings.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f43e7-187">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f43e7-187">See also</span></span>
<span data-ttu-id="f43e7-188"><a name="BK_AdvancedSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="f43e7-188"><a name="BK_AdvancedSettings"> </a></span></span>

[<span data-ttu-id="f43e7-189">고급 eDiscovery (클래식)</span><span class="sxs-lookup"><span data-stu-id="f43e7-189">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)

