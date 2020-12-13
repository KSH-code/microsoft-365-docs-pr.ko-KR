---
title: Advanced eDiscovery에서 프로세스 모듈 실행 및 데이터 로드
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
ms.assetid: c87bb0e5-301c-4d1d-958e-aabeb7990f44
description: 보안 준수 센터를 사용하여 Advanced eDiscovery에 액세스하고 사례에 대한 &amp; 프로세스 모듈을 실행하는 방법을 학습합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 64172c0198418dbb0ba4d01a5adbd5aaef4c3a3b
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662843"
---
# <a name="run-the-process-module-and-load-data-in-advanced-ediscovery-classic"></a><span data-ttu-id="c752e-103">Advanced eDiscovery(클래식)에서 프로세스 모듈 실행 및 데이터 로드</span><span class="sxs-lookup"><span data-stu-id="c752e-103">Run the Process module and load data in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="c752e-p101">Advanced eDiscovery를 사용하려면 Office 365 E3의 고급 준수 추가 기능이나 조직을 위한 E5 구독이 필요합니다. 이 요금제가 없는 상태에서 Advanced eDiscovery를 사용하려는 경우에는 [Office 365 Enterprise E5 평가판을 등록](https://go.microsoft.com/fwlink/p/?LinkID=698279)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c752e-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="c752e-106">이 섹션에서는 Advanced eDiscovery 프로세스 모듈의 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c752e-106">This section describes the functionality of the Advanced eDiscovery Process module.</span></span> 
  
<span data-ttu-id="c752e-107">파일 데이터 외에도 파일 형식, 확장명, 위치 또는 경로, 만든 날짜 및 시간, 만든 이, 관리자 및 제목과 같은 메타데이터를 Advanced eDiscovery에 로드하고 각 사례에 대해 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c752e-107">In addition to file data, metadata such as file type, extension, location or path, creation date and time, author, custodian, and subject, can be loaded into Advanced eDiscovery and saved for each case.</span></span> <span data-ttu-id="c752e-108">일부 메타데이터는 Advanced eDiscovery에 의해 계산됩니다(예: 기본 파일이 로드될 때).</span><span class="sxs-lookup"><span data-stu-id="c752e-108">Some metadata is calculated by Advanced eDiscovery, for example, when native files are loaded.</span></span> 
  
<span data-ttu-id="c752e-109">Advanced eDiscovery는 중복에 가까운 그룹화 또는 연결성 점수와 같은 시스템 메타데이터 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c752e-109">Advanced eDiscovery provides system metadata values, such as Near-duplicate groupings or Relevance scores.</span></span> <span data-ttu-id="c752e-110">파일 주석과 같은 기타 메타데이터는 관리자가 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c752e-110">Other metadata, such as file annotations, can be added by the Administrator.</span></span> 
  
## <a name="running-process"></a><span data-ttu-id="c752e-111">프로세스 실행</span><span class="sxs-lookup"><span data-stu-id="c752e-111">Running Process</span></span>

> [!NOTE]
> <span data-ttu-id="c752e-112">일괄 처리 번호는 파일 추적을 허용하기 위해 프로세스 중에 파일에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="c752e-112">Batch numbers are assigned to a file during Process to allow the tracking of files.</span></span> <span data-ttu-id="c752e-113">일괄 처리 번호를 사용하면 다시 처리 옵션에 대한 프로세스 일괄 처리를 식별할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c752e-113">The batch number also enables identification of Process batches for reprocessing options.</span></span> <span data-ttu-id="c752e-114">일괄 처리 번호 및 세션을 사용하여 필터링하는 데 추가 필터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c752e-114">Additional filters are available for filtering by batch number and sessions.</span></span> 
  
<span data-ttu-id="c752e-115">다음 단계에 따라 Process를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c752e-115">Perform the following steps to run Process.</span></span>
  
1. <span data-ttu-id="c752e-116">[보안 열기 &amp; 준수 센터.](go-to-the-securitycompliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="c752e-116">[Open the Security &amp; Compliance Center](go-to-the-securitycompliance-center.md) .</span></span> 
    
2. <span data-ttu-id="c752e-117">검색 **조사 &amp;** \> **eDiscovery로 이동한** 다음 **Advanced eDiscovery로 이동을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c752e-117">Go to **Search &amp; investigation** \> **eDiscovery** and then click **Go to Advanced eDiscovery**.</span></span>
    
3. <span data-ttu-id="c752e-118">Advanced eDiscovery에서 표시된 사례 페이지에서  적절한 사례를 선택하고 사례로 **이동을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c752e-118">In Advanced eDiscovery, select the appropriate case in the displayed **Cases** page and click **Go to case**.</span></span>
    
4. <span data-ttu-id="c752e-119">프로세스 **설치** \> **준비에서** 사용 가능한 컨테이너 목록에서 \> 컨테이너를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c752e-119">In **Prepare** \> **Process** \> **Setup**, select a container from the list of available containers.</span></span>
    
    ![프로세스를 클릭하여 사례에 검색 결과 추가](../media/50bdc55c-d378-4881-b302-31ef785fa359.png)
  
5. <span data-ttu-id="c752e-121">고급 **설정을 클릭합니다.** 컨테이너를 시드 파일 또는 미리 태그가 지정한 파일로 추가하려는 경우</span><span class="sxs-lookup"><span data-stu-id="c752e-121">Click **Advanced settings...** if you want to add the container as seed files or as pre-tagged files.</span></span> 
    
    <span data-ttu-id="c752e-122">시드 파일을 사용하여 부족한 문제(일반적으로 2% 이하)에 대한 교육을 가속화합니다.</span><span class="sxs-lookup"><span data-stu-id="c752e-122">Use seed files to accelerate training for issues with low richness (usually 2%, or less).</span></span> <span data-ttu-id="c752e-123">시드 파일의 경우 다양한 고유의 관련 파일을 선택하고 문제당 약 20-50개의 시드를 처리하는 것이 좋습니다(너무 많은 시드 파일이 관련성 결과를 오인할 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="c752e-123">For seed files, it is recommended that you select a variety of distinctly relevant files and process about 20-50 seeds per issue (too many seed files can skew Relevance results).</span></span> <span data-ttu-id="c752e-124">시드 파일은 문제를 교육할 동일한 사람이 검토해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c752e-124">Seed files should be reviewed by the same person who will train the issue.</span></span>
    
    <span data-ttu-id="c752e-125">사전 태그가 지정한 파일을 사용하여관련성 교육을 자동화합니다.</span><span class="sxs-lookup"><span data-stu-id="c752e-125">Use pre-tagged files to automate Relevance training.</span></span> <span data-ttu-id="c752e-126">적어도 1,500개 파일에 태그를 지정하고 관련성이 없는 파일의 비율을 관련성에 추가된 컬렉션과 동일하게 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c752e-126">You should tag at least 1,500 files, and keep the proportion of relevant to non-relevant files the same as in the collection added to Relevance.</span></span> <span data-ttu-id="c752e-127">이러한 파일은 수동으로 태그를 지정해야 하며 태그 지정 품질을 확신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c752e-127">These files should be manually tagged, and you should be confident in the quality of tagging.</span></span>
    
    ![일괄 처리 파일을 처리하기 위한 고급 설정 페이지의 스크린샷](../media/3c25cb78-4484-41e5-bd34-3753c7ab6cf2.jpg)
  
  - <span data-ttu-id="c752e-129">시드 **섹션에서 다음을** 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c752e-129">In the **Seed** section:</span></span> 
    
    <span data-ttu-id="c752e-130">컨테이너를 시드 파일로 **표시하려면** 시드 파일로 표시를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="c752e-130">Choose **Mark as seed files** to mark the container as seed files.</span></span> <span data-ttu-id="c752e-131">또한 For 문제 드롭다운에서 문제당 **할당을** 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c752e-131">You also need choose to assign them per issue from the **For issue** drop-down.</span></span> <span data-ttu-id="c752e-132">태그 **드롭다운에서** 관련성 또는 **관련이** 없습니다. </span><span class="sxs-lookup"><span data-stu-id="c752e-132">Choose either **Relevant** or **Not relevant** from the **Tag** drop-down.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="c752e-133">파일을 시드로 설정하면 미리 태그가 지정되어 있는 것으로 **표시될 수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="c752e-133">Once you set files as **Seed**, you cannot mark them as **Pre-tagged**.</span></span> 
  
  - <span data-ttu-id="c752e-134">미리 태그가 **지정한 파일 섹션에서 다음을** 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c752e-134">In the **Pre-tagged files** section:</span></span> 
    
    <span data-ttu-id="c752e-135">**컨테이너를** 미리 태그가 지정한 파일로 표시하려면 미리 태그가 지정한 파일로 표시를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="c752e-135">Choose **Mark as pre-tagged files** to mark the container as pre-tagged files.</span></span> <span data-ttu-id="c752e-136">또한 For 문제 드롭다운에서 문제당 **할당해야** 합니다.</span><span class="sxs-lookup"><span data-stu-id="c752e-136">You also need to assign them per issue from the **For issue** drop-down.</span></span> <span data-ttu-id="c752e-137">태그 **드롭다운에서** 관련성 또는 **관련이** 없습니다. </span><span class="sxs-lookup"><span data-stu-id="c752e-137">Choose either **Relevant** or **Not relevant** from the **Tag** drop-down.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="c752e-138">미리 태그가 **지정한** 파일을 설정하면 파일을 시드로 표시하지 **않습니다.**</span><span class="sxs-lookup"><span data-stu-id="c752e-138">Once you set files as **Pre-tagged**, you cannot mark them as **Seed**.</span></span> 
  
  - <span data-ttu-id="c752e-139">전자 **메일 태그 지정 섹션에서**</span><span class="sxs-lookup"><span data-stu-id="c752e-139">In the **Email tagging** section.</span></span> <span data-ttu-id="c752e-140">처리된 전자 메일 중 시드 또는 사전 태그로 표시될 부분을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c752e-140">set which part of a processed email are to be marked as Seed or Pre-tagged.</span></span> 
    
6. <span data-ttu-id="c752e-141">시작하려면 **프로세스를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c752e-141">To begin, click **Process**.</span></span> <span data-ttu-id="c752e-142">완료되면 프로세스 결과가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c752e-142">When completed, the Process results are displayed.</span></span>
    
7. <span data-ttu-id="c752e-143">(선택 사항) 특정 관리인에게 데이터 원본을 할당해야 하는 경우, **Custodians** Manage 및 assign \> **custodians** **Assign에서** 보호자 이름을 추가하고 편집할 수 \> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c752e-143">(Optional) If you need to assign data sources to a specific custodian, you can add and edit custodian names in **Custodians** \> **Manage** and assign custodians in **Custodians** \> **Assign**.</span></span> 
    
<span data-ttu-id="c752e-144">사례에 추가하는 경우 다시 처리하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c752e-144">If you add to the case, then you can process again.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="c752e-145">관련 항목</span><span class="sxs-lookup"><span data-stu-id="c752e-145">Related topics</span></span>

[<span data-ttu-id="c752e-146">고급 eDiscovery (클래식)</span><span class="sxs-lookup"><span data-stu-id="c752e-146">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="c752e-147">프로세스 모듈 결과 보기</span><span class="sxs-lookup"><span data-stu-id="c752e-147">Viewing Process module results</span></span>](view-process-module-results-in-advanced-ediscovery.md)

