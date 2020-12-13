---
title: Advanced eDiscovery에서 가져온 파일을 추가하기 위한 로드 설정
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
ms.assetid: 0e0a9d04-294f-4f54-8bf1-b32d81345126
description: Advanced eDiscovery에서 해당 학습을 수행하기 전에 마지막으로 정의된 로드 또는 배치에 가져온 파일을 추가하는 단계를 검토합니다.
ms.openlocfilehash: 7cd244ba1ba516c2b7376b71e809b4c01ff5df8b
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663483"
---
# <a name="set-up-loads-to-add-imported-files-in-advanced-ediscovery-classic"></a><span data-ttu-id="05c3c-103">Advanced eDiscovery(클래식)에서 가져온 파일을 추가하기 위한 로드 설정</span><span class="sxs-lookup"><span data-stu-id="05c3c-103">Set up loads to add imported files in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="05c3c-p101">Advanced eDiscovery를 사용하려면 Office 365 E3의 고급 준수 추가 기능이나 조직을 위한 E5 구독이 필요합니다. 이 요금제가 없는 상태에서 Advanced eDiscovery를 사용하려는 경우에는 [Office 365 Enterprise E5 평가판을 등록](https://go.microsoft.com/fwlink/p/?LinkID=698279)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="05c3c-106">Advanced eDiscovery에서 로드는 사례에 추가된 파일의 새로운 배치입니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-106">In Advanced eDiscovery, a load is a new batch of files added to a case.</span></span> <span data-ttu-id="05c3c-107">기본적으로 하나의 부하가 정의되고 가져온 모든 파일이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-107">By default, one load is defined and all imported files are added to it.</span></span> <span data-ttu-id="05c3c-108">관계 교육을 수행하기 전에 가져온 파일을 로드에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-108">Before performing Relevance training, imported files must be added to the load.</span></span> 
  
<span data-ttu-id="05c3c-109">다음과 같은 시나리오를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-109">Consider the following scenarios:</span></span>
  
- <span data-ttu-id="05c3c-110">새 파일은 사례 데이터베이스에 로드된 이전 파일과 비슷하거나 이전 파일 로드가 파일 모음에서 임의로 설정된 것으로 알려져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-110">New files are known to be similar to the previous files loaded to the case database, or the previous load of files was a random set from the file collection.</span></span> <span data-ttu-id="05c3c-111">이 경우 가져온 파일을 현재 파일 로드에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-111">In this instance, add the imported files to the current file load.</span></span>
    
- <span data-ttu-id="05c3c-112">새 파일은 이전 파일과 다르거나(예: 다른 원본에서) 이전 로드와 유사하거나 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-112">New files are different from previous ones (for example, from a different source), or you have no prior knowledge that they're similar or different to the previous loads.</span></span> <span data-ttu-id="05c3c-113">이 시나리오에서는 가져온 파일을 새 파일 로드에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-113">In this scenario, add the imported files to a new file load.</span></span> <span data-ttu-id="05c3c-114">Advanced eDiscovery는 이를 롤링 로드 시나리오로 인식하고, 추가 프로세스를 호출하고, 관련성 학습 및 일괄 처리 계산을 잠그고, 새로운 부하가 통합 및 교육될 때까지 이를 잠급니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-114">Advanced eDiscovery recognizes this as a Rolling loads scenario, invokes a Catch-up process, locks Relevance training and Batch calculations until Catch-up is completed, and the new load is integrated and trained.</span></span> 
    
## <a name="adding-imported-files-to-the-current-load"></a><span data-ttu-id="05c3c-115">현재 로드에 가져온 파일 추가</span><span class="sxs-lookup"><span data-stu-id="05c3c-115">Adding imported files to the current load</span></span>

<span data-ttu-id="05c3c-116">Advanced eDiscovery에서 처리하려면 가져온 모든 파일을 로드에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-116">All imported files must be added to a load to be processed in Advanced eDiscovery.</span></span> <span data-ttu-id="05c3c-117">가져온 파일이 마지막으로 정의된 로드에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-117">Imported files are added to the last defined load.</span></span> <span data-ttu-id="05c3c-118">나중에 추가 파일을 가져오는 경우 로드에도 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-118">If you import additional files later, they also must be added to the load.</span></span>
  
1. <span data-ttu-id="05c3c-119">In the **Relevance \> Relevance setup** tab, select **Loads.**</span><span class="sxs-lookup"><span data-stu-id="05c3c-119">In the **Relevance \> Relevance setup** tab, select **Loads**.</span></span>
    
    ![관련성 설정 로드 탭](../media/278aac7f-655f-462f-852a-6baa5d818768.png)
  
2. <span data-ttu-id="05c3c-121">**파일 포함:** 포함할 파일 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-121">**Include files**: Select an option for files to include.</span></span> <span data-ttu-id="05c3c-122">기본적으로 현재 부하에 파일을 추가하는 것은 "모든 파일" 인구를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-122">By default, adding files to the current load is based on the "All files" population.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="05c3c-123">사용 가능한 모든 컬링된 파일을 다른 파일에 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-123">Load all available culled files into Relevance.</span></span> <span data-ttu-id="05c3c-124">사용 가능한 파일의 하위 집합만 로드하려면 먼저 지원에 문의하시기 바랍니다. 하위 집합을 로드하면 관련성 교육에 부정적인 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-124">If you plan to load only a subset of the available files, please first consult with Support, as loading subsets can adversely affect Relevance training.</span></span> 
  
3. <span data-ttu-id="05c3c-125">Loads **관리에서** 부하를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-125">In **Loads management**, select a load.</span></span>
    
4. <span data-ttu-id="05c3c-126">파일 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="05c3c-126">Click **Add files**.</span></span> <span data-ttu-id="05c3c-127">파일이 로드에 추가되고 확인 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-127">The files are added to the load and a confirmation message is displayed.</span></span> 
    
5. <span data-ttu-id="05c3c-128">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-128">Click **OK**.</span></span>
    
<span data-ttu-id="05c3c-129">이제 파일을 고급 eDiscovery에서 처리하여 파일을 학습할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-129">The files can now be processed in Advanced eDiscovery Relevance for training the files.</span></span>
  
## <a name="editing-a-load-name-within-a-case"></a><span data-ttu-id="05c3c-130">사례 내에서 로드 이름 편집</span><span class="sxs-lookup"><span data-stu-id="05c3c-130">Editing a load name within a case</span></span>

<span data-ttu-id="05c3c-131">로드 이름을 변경하는 경우 사례에 중요한 이름을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-131">If changing the load name, it is recommended to use a name that is significant to the case.</span></span>
  
1. <span data-ttu-id="05c3c-132">In the **Relevance \> Relevance setup** tab, select **Loads.**</span><span class="sxs-lookup"><span data-stu-id="05c3c-132">In the **Relevance \> Relevance setup** tab, select **Loads**.</span></span>
    
2. <span data-ttu-id="05c3c-133">Loads **관리** 목록에서 로드를 선택하고 편집 **아이콘을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-133">From the **Loads management** list, select a load and click the **Edit** icon.</span></span> <span data-ttu-id="05c3c-134">로드 편집 창이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-134">The Edit load window is displayed.</span></span> 
    
3. <span data-ttu-id="05c3c-135">변경 내용을 입력하고 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="05c3c-135">Enter the changes, and then click **OK**.</span></span>
    
## <a name="adding-imported-files-to-a-new-load"></a><span data-ttu-id="05c3c-136">가져온 파일을 새 로드에 추가</span><span class="sxs-lookup"><span data-stu-id="05c3c-136">Adding imported files to a new load</span></span>

<span data-ttu-id="05c3c-137">해당 교육을 시작하거나 일괄 계산을 수행한 후 추가 파일 집합을 가져와서 처리해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-137">After starting Relevance training or performing Batch calculation, you may want to import and process an additional set of files.</span></span> 
  
<span data-ttu-id="05c3c-138">Catch-up 중에 Up 집합을 만들고 태그를 지정하고 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-138">During Catch-up, you can create, tag, and analyze the Catch-up set.</span></span> <span data-ttu-id="05c3c-139">Advanced eDiscovery는 새 부하의 관련 파일 및 비관용 파일에 대한 평가를 이전 로드의 파일과 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-139">Advanced eDiscovery compares its assessment of Relevant and Non-Relevant files in the new load to those in previous loads.</span></span> <span data-ttu-id="05c3c-140">결과에 따라 필요한 경우 추가 결정을 내릴지 묻는 메시지가 표시될 수 있으며, Advanced eDiscovery는 누적된 관련성 정보를 기반으로 권장 사항을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-140">Based on the results, you are prompted to make Catch-up decisions, if necessary, and Advanced eDiscovery provides recommendations based on the accrued Relevance information.</span></span> 
  
<span data-ttu-id="05c3c-141">롤링 로드 및 추가 기능은 다음과 같이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-141">Rolling Loads and Catch-up functionality varies as follows:</span></span> 
  
- <span data-ttu-id="05c3c-142">일괄 계산 후 새 파일 로드를 가져올 때 Advanced eDiscovery는 파일이 다음 범주 중 하나에 속하는 정도를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-142">When you import a new file load after Batch calculation, Advanced eDiscovery determines to what extent the files fall into one of the following categories:</span></span>
    
  - <span data-ttu-id="05c3c-143">유사(동종): 새로운 사용자 지정관련 교육이 필요하지 않습니다. 이전 부하에서 누적된 지식은 새 부하에 "있는 것"으로 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-143">Similar (homogeneous): A new, custom round of Relevance training is not required and the knowledge accrued from the previous load can be applied "as is" to the new load.</span></span> 
    
  - <span data-ttu-id="05c3c-144">고유(이기종): 새로운 사용자 지정관련성 교육이 필요하며 이전 부하에서 누적된 지식은 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-144">Distinct (heterogeneous): A new, custom round of Relevance training is required, and the knowledge accrued from the previous load cannot be applied.</span></span> 
    
    <span data-ttu-id="05c3c-145">이러한 용어는 로드 간 파일 유사성 수준을 참조하며 로드 내에 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-145">These terms refer to the level of similarity of files between loads and not within the loads.</span></span> 
    
- <span data-ttu-id="05c3c-146">일괄 처리 계산 전과 같은 기간 동안 새 파일 로드를 가져올 때 추가 기능을 사용하면 연합 파일 집합에 대한 업데이트 교육을 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-146">When importing a new file load during Relevance training (before Batch calculation), Catch-up enables you to continue Relevance training on the united file set.</span></span> <span data-ttu-id="05c3c-147">Advanced eDiscovery는 새 부하가 이전 부하와 유사하거나 다른지 여부를 예측하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-147">Advanced eDiscovery does not estimate whether the new load is similar to or distinct from the previous load.</span></span> <span data-ttu-id="05c3c-148">새 부하에 대한 정보를 수집하기만 하면 관련성 교육을 새 파일 및 이전 파일 집합에서 계속 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-148">It simply collects information about the new load and enables Relevance training to continue on the new and previous sets of files.</span></span> 
    
- <span data-ttu-id="05c3c-149">관련성 학습에 여러 문제와 일괄 계산 후 문제가 있는 경우 모든 문제에 대해 Catch-up 프로세스가 한 번 수행되고 각 문제에 대해 결과가 계산되고 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-149">When there are multiple issues in Relevance training as well as issues after Batch calculation, the Catch-up process is performed once for all issues, and the results are calculated and displayed for each issue.</span></span>
    
> [!NOTE]
> <span data-ttu-id="05c3c-150">Catch-up 샘플의 크기는 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-150">The size of the Catch-up sample may vary.</span></span> <span data-ttu-id="05c3c-151">이전 부하를 상대로 새 부하의 크기와 새 부하를 추가하기 전에 완료된 샘플 수에 따라 달라 니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-151">It depends on the size of the new load relative to the previous loads, and on the number of samples completed before adding the new load.</span></span> <span data-ttu-id="05c3c-152">Catch-up 샘플은 일반적으로 새 로드에서 200~2,000개 파일 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-152">The Catch-up sample is typically a set of 200 to 2,000 files from the new load.</span></span> 
  
> [!TIP]
> <span data-ttu-id="05c3c-153">Catch-up stops any other tasks and requires individual file tagging and review.</span><span class="sxs-lookup"><span data-stu-id="05c3c-153">Catch-up stops any other tasks and requires individual file tagging and review.</span></span> <span data-ttu-id="05c3c-154">따라서 큰 일괄 처리에 새 파일을 추가할 때 오버헤드를 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-154">Therefore, you can reduce overhead when you add new files in large batches.</span></span> 
  
## <a name="adding-a-new-file-load-using-catch-up-and-rolling-loads"></a><span data-ttu-id="05c3c-155">Up 및 Rolling 로드를 사용하여 새 파일 로드 추가</span><span class="sxs-lookup"><span data-stu-id="05c3c-155">Adding a new file load using Catch-up and Rolling loads</span></span>

1. <span data-ttu-id="05c3c-156">In the **Relevance \> Relevance setup** tab, select **Loads.**</span><span class="sxs-lookup"><span data-stu-id="05c3c-156">In the **Relevance \> Relevance setup** tab, select **Loads**.</span></span>
    
2. <span data-ttu-id="05c3c-157">Loads **관리에서** 아이콘을 클릭하여 **+** 로드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-157">Under **Loads management**, click the **+** icon to add a load.</span></span> <span data-ttu-id="05c3c-158">확인 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-158">A confirmation message is displayed.</span></span> 
    
3. <span data-ttu-id="05c3c-159">계속하려면 **예** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-159">Click **Yes** to continue.</span></span> <span data-ttu-id="05c3c-160">새 **로드 추가** 대화 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-160">The **Add new load** dialog is displayed.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="05c3c-161">이전 부하에 작업이 수행된 경우 새 부하만 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-161">You can only add a new load if actions were performed to the previous load.</span></span> 
  
4. <span data-ttu-id="05c3c-162">새 로드 추가 **대화** 상자에서  로드  이름 및 설명에 정보를 입력하고 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="05c3c-162">In the **Add new load** dialog, type information in **Load name** and **Description** and then click **OK**.</span></span> <span data-ttu-id="05c3c-163">Advanced eDiscovery는 새 부하를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-163">Advanced eDiscovery adds a new load.</span></span>
    
5. <span data-ttu-id="05c3c-164">새 로드 파일을 가져오려면 파일 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="05c3c-164">To import the new load file, click **Add files**.</span></span> <span data-ttu-id="05c3c-165">모든 새 파일이 이 로드에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-165">All new files are added to this load.</span></span> <span data-ttu-id="05c3c-166">Advanced eDiscovery가 파일을 가져온 후 롤링 로드 시나리오를 인식하고 추가 기능을 다음 단계로 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-166">After Advanced eDiscovery imports the files, it recognizes the Rolling loads scenario and indicates Catch-up as the next step.</span></span>
    
6. <span data-ttu-id="05c3c-167">대화 **상자 아래쪽에서** 추가를 클릭하여 시나리오를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-167">Click **Catch-up** at the bottom of the dialog to run the scenario.</span></span> 
    
    <span data-ttu-id="05c3c-168">동시 파일 태그 지정을 허용하기 위해 모든 문제에 대해 일반적으로 새 부하에서 200~2,000개 파일을 포함하는 단일 Catch-up 집합이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-168">A single Catch-up set, typically containing 200 to 2,000 files from the new load, is created for all issues to allow concurrent file tagging.</span></span>
    
    <span data-ttu-id="05c3c-169">부하가 유사하거나 구분되어 있는지 여부, Advanced eDiscovery가 부하를 자동으로 병합 또는 분할하는지 여부, 그리고 다음 단계의 처리에 대한 정보가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-169">Details are provided about whether loads are similar or distinct, whether Advanced eDiscovery merged or split the loads automatically, and information regarding processing in the next step.</span></span>
    
    <span data-ttu-id="05c3c-170">그런 다음 파일에 태그를 지정하고 계산 작업을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-170">You can then tag files and run a calculate operation.</span></span> <span data-ttu-id="05c3c-171">태그를 지정하면 로드가 유사하거나 고유한지 여부를 확인할 수 있으며 새 파일 집합에서 작업을 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-171">The tagging enables Relevance to determine if loads are similar or distinct and enables you to continue working on the new set of files.</span></span>
    
7. <span data-ttu-id="05c3c-172">Catch-up set is reviewed, view **Relevance \> Track** for the Catch-up results.</span><span class="sxs-lookup"><span data-stu-id="05c3c-172">After the Catch-up set is reviewed, view **Relevance \> Track** for the Catch-up results.</span></span> 
    
1. <span data-ttu-id="05c3c-173">관련성 학습 중에 새 파일 로드가 추가된 경우(즉, 문제가 아직 일괄 계산을 거치지 않은 **경우)** 추가 결과에 관계없이 교육을 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-173">If the new file load was added during Relevance training (meaning, the issue has not yet gone through Batch calculation), **Continue training** is the next step, regardless of the Catch-up results.</span></span> 
    
    <span data-ttu-id="05c3c-174">새 부하와 이전 부하는 하나의 부하로 처리되고, 연합 집합에서 계속된관련성 교육이 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-174">The new and previous loads are processed as one load and Relevance training continues on the united set.</span></span> <span data-ttu-id="05c3c-175">이제 이 절차를 완료하고 관련성 교육을 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-175">You are now finished with this procedure and can continue Relevance training.</span></span> 
    
2. <span data-ttu-id="05c3c-176">새 부하가 일괄 처리 계산 후에 추가된 경우 다음 단계로 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-176">If the new load was added after Batch calculation, proceed to the following steps.</span></span>
    
8. <span data-ttu-id="05c3c-177">일괄 계산 후 추가된 새 부하의 경우 Advanced eDiscovery는 새 부하가 이전 부하와 유사하거나 이전 부하와 유사한지, 아니면 다른지 여부를 다음과 같이 파악합니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-177">For new loads added after Batch calculation, Advanced eDiscovery determines if the new load is similar to or distinct from previous loads, as follows:</span></span>
    
1. <span data-ttu-id="05c3c-178">부하가 비슷한 것으로 발견된 경우: 추가적인관련성 교육이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-178">If loads were found to be similar: No additional Relevance training is necessary.</span></span> <span data-ttu-id="05c3c-179">대시보드는 \*\*일괄 계산 \*\* 다시 실행하여 새 부하에 대한 해당성 점수를 계산하는 것이 권장되는 다음 단계를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-179">The dashboard shows the recommended next step is to run \*\* Batch calculation \*\* again to calculate Relevance scores for the new load.</span></span> <span data-ttu-id="05c3c-180">로드는 유사하기 때문에 이전 분류자 분석을 새 파일에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-180">Loads were found to be similar, so the previous classifier analysis can be run on the new files.</span></span> 
    
2. <span data-ttu-id="05c3c-181">부하가 고유한 것으로 발견된 경우: 더 많은 타당성 교육이 필요하며 다음 단계는 추가 결정입니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-181">If loads were found to be distinct: More Relevance training is necessary and the next step is Catch-up decision.</span></span> <span data-ttu-id="05c3c-182">다음과 같이 추가 결정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-182">Select a Catch-up decision as follows:</span></span>
    
    <span data-ttu-id="05c3c-183">부하 **병합을** 선택하면 고급 eDiscovery가 이전 및 새 로드를 교육 집합에 병합합니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-183">If you select **Merge loads**, Advanced eDiscovery merges previous and new loads for the training set.</span></span> <span data-ttu-id="05c3c-184">첫 번째 부하가 일괄 계산을 통과한 것이지만 추가 교육이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-184">Although the first load went through Batch calculation, more training is needed.</span></span> <span data-ttu-id="05c3c-185">새 부하와 이전 부하를 함께 교육을 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-185">Continue training new and previous loads together.</span></span> <span data-ttu-id="05c3c-186">그런 다음 일괄 처리 계산이 다시 실행되고 이전의 일괄 계산 점수는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-186">Batch calculation will then run again and the previous Batch calculation scores should be ignored.</span></span> <span data-ttu-id="05c3c-187">기존 로드에 대한 관련성 점수를 다시 계산할 수 있는 경우(예: 기존 파일 로드 검토가 시작되지 않은 경우) 이 선택을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-187">Choose this selection when Relevance scores for existing loads can be recalculated, for example, when review of existing file loads has not started.</span></span>
    
    <span data-ttu-id="05c3c-188">분할 **부하를** 선택하는 경우 새 부하에만 대한관련성 교육을 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-188">If you select **Split loads**, continue Relevance training only on the new load.</span></span> <span data-ttu-id="05c3c-189">이 경우 이전 일괄 처리 계산 점수는 그대로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-189">In this instance, previous Batch calculation scores will remain as is.</span></span> <span data-ttu-id="05c3c-190">기존 부하에 대한 기존 관련성 점수를 다시 계산할 수 없는 경우(예: 기존 부하 검토가 이미 시작된 경우) 이 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-190">Choose this option when existing Relevance scores for existing loads cannot be recalculated, for example, if review of existing loads has already started.</span></span> <span data-ttu-id="05c3c-191">관련성 점수는 이 시점부터 별도로 관리되고 병합할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="05c3c-191">Relevance scores are managed separately from this point onward and cannot be merged.</span></span>
    
3. <span data-ttu-id="05c3c-192">교육 **계속을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="05c3c-192">Click **Continue training**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="05c3c-193">참고 항목</span><span class="sxs-lookup"><span data-stu-id="05c3c-193">See also</span></span>

[<span data-ttu-id="05c3c-194">고급 eDiscovery (클래식)</span><span class="sxs-lookup"><span data-stu-id="05c3c-194">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="05c3c-195">문제 정의 및 사용자 할당</span><span class="sxs-lookup"><span data-stu-id="05c3c-195">Defining issues and assigning users</span></span>](define-issues-and-assign-users.md)
  
[<span data-ttu-id="05c3c-196">강조 표시된 키워드 및 고급 옵션 정의</span><span class="sxs-lookup"><span data-stu-id="05c3c-196">Defining highlighted keywords and advanced options</span></span>](define-highlighted-keywords-and-advanced-options.md)

