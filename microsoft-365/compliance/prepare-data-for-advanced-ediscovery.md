---
title: Office 365 Advanced eDiscovery에 대한 데이터 준비
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 2fb94c23-1846-4a0e-994d-da6d02445f15
description: 'Microsoft 365 보안 &amp; 규정 준수 센터에서 Office 365 Advanced eDiscovery를 사용하여 Office 365 데이터를 분석할 수 있도록 준비하는 방법을 알아봅니다. '
ms.openlocfilehash: be778acb3356071e9575ed708623a0b94e2b3c7a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37088555"
---
# <a name="prepare-data-for-office-365-advanced-ediscovery"></a><span data-ttu-id="945c8-103">Office 365 Advanced eDiscovery에 대한 데이터 준비</span><span class="sxs-lookup"><span data-stu-id="945c8-103">Prepare search results for Office 365 Advanced eDiscovery</span></span>

<span data-ttu-id="945c8-104">이 항목에서는 Advanced eDiscovery에서 콘텐츠 검색 결과를 사례에 로드하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="945c8-104">This topic describes how to load the results of a Content Search in to a case in Advanced eDiscovery.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="945c8-p101">Advanced eDiscovery를 사용하려면 Office 365 E3의 고급 준수 추가 기능이나 조직을 위한 E5 구독이 필요합니다. 이 요금제가 없는 상태에서 Advanced eDiscovery를 사용하려는 경우에는 [Office 365 Enterprise E5 평가판을 등록](https://go.microsoft.com/fwlink/p/?LinkID=698279)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="945c8-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="step-1-prepare-office-365-data-for-advanced-ediscovery"></a><span data-ttu-id="945c8-107">1단계: Advanced eDiscovery에 사용하도록 Office 365 데이터 준비</span><span class="sxs-lookup"><span data-stu-id="945c8-107">Step 1: Prepare Office 365 data for Advanced eDiscovery</span></span>

<span data-ttu-id="945c8-108">Advanced eDiscovery를 사용하여 데이터를 분석하려면 Microsoft 365 보안 &amp; 규정 준수 센터(Microsoft 365 보안 &amp; 규정 준수 센터의 **콘텐츠 검색** 페이지에 나열됨)에서 실행하는 콘텐츠 검색 또는 eDiscovery 케이스(보안 &amp; 규정 준수 센터의 **eDiscovery** 페이지에 나열됨)와 관련된 검색의 결과를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="945c8-108">To analyze data with Advanced eDiscovery, you can use the results of a Content Search that you run in the Microsoft 365 Security &amp; Compliance Center (listed on the **Content search** page in the Microsoft 365 Security &amp; Compliance Center) or a search associated with an eDiscovery case (listed on the **eDiscovery** page in the Security &amp; Compliance Center).</span></span> 
  
<span data-ttu-id="945c8-109">Advanced eDiscovery에서 분석할 수 있도록 검색 결과를 준비하는 방법에 대한 자세한 내용은 [Office 365 Advanced eDiscovery에 사용하도록 검색 결과 준비](prepare-search-results-for-advanced-ediscovery.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="945c8-109">For the detailed steps on preparing search results for analysis in Advanced eDiscovery, see [Prepare search results for Office 365 Advanced eDiscovery](prepare-search-results-for-advanced-ediscovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="945c8-110">Office 365 외부에 데이터가 있고 Advanced eDiscovery에서 이 데이터를 준비하고 분석할 수 있도록 Office 365로 가져오려면 [Office 365로 PST 파일을 가져오는 방법에 대한 개요](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84) 및 [Office 365에 타사 데이터 보관](https://go.microsoft.com/fwlink/p/?linkid=716918)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="945c8-110">If you have data outside of Office 365 and want to import it to Office 365 so that you can prepare and analyze it in Advanced eDiscovery, a see [Overview of importing PST files to Office 365](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84) and [Archiving third-party data in Office 365](https://go.microsoft.com/fwlink/p/?linkid=716918).</span></span> 
  
## <a name="step-2-load-search-result-data-in-to-a-case-in-advanced-ediscovery"></a><span data-ttu-id="945c8-111">2단계: Advanced eDiscovery에서 사례에 검색 결과 데이터 로드</span><span class="sxs-lookup"><span data-stu-id="945c8-111">Step 2: Load search result data in to a case in Advanced eDiscovery</span></span>

<span data-ttu-id="945c8-112">분석을 위해 보안 &amp; 규정 준수 센터의 검색 결과를 준비한 후, 다음 단계는 Advanced eDiscovery에서 케이스에 검색 결과를 로드하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="945c8-112">After you prepare the search results in the Security &amp; Compliance Center for analysis, the next step is to load the search results in to a case in Advanced eDiscovery.</span></span> <span data-ttu-id="945c8-113">자세한 내용은 [프로세스 모듈 실행](run-the-process-module-in-advanced-ediscovery.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="945c8-113">For more detailed information, see [Run the Process module](run-the-process-module-in-advanced-ediscovery.md).</span></span>
  
1. <span data-ttu-id="945c8-114">[https://protection.office.com](https://protection.office.com)으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="945c8-114">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="945c8-115">회사 또는 학교 계정을 사용하여 Office 365에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="945c8-115">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="945c8-116">보안 및 준수 센터에서 **검색 &amp; 조사** \> **eDiscovery**를 클릭하여 조직의 사례 목록을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="945c8-116">In the Security &amp; Compliance Center, click **Search &amp; investigation** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
4. <span data-ttu-id="945c8-117">Advanced eDiscovery에서 데이터를 로드할 사례 옆에 있는 **열기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="945c8-117">On the **eDiscovery page, click Open** next to the case that you want to go to in Advanced eDiscovery.</span></span> 
    
5. <span data-ttu-id="945c8-118">사례에 대한 **홈** 페이지에서 **Advanced eDiscovery**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="945c8-118">On the **Home** page for the case, click **Advanced eDiscovery**.</span></span> 
    
    ![Advanced eDiscovery로 전환을 클릭하여 Advanced eDiscovery에서 케이스를 엽니다.](media/8e34ba23-62e3-4e68-a530-b6ece39b54be.png)
  
    <span data-ttu-id="945c8-120">**Advanced eDiscovery에 연결하는 중** 진행률 표시줄이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="945c8-120">The **Connecting to Advanced eDiscovery** progress bar is displayed. When you're connected, the case is opened in Advanced eDiscovery.</span></span> <span data-ttu-id="945c8-121">Advanced eDiscovery에 연결되면 컨테이너 목록이 해당 케이스의 설정 페이지에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="945c8-121">When you're connected to Advanced eDiscovery, a list of containers is displayed on the setup page for the case.</span></span> 
    
    ![케이스가 Advanced eDiscovery에 표시됩니다.](media/8036e152-70dc-4bb7-9379-61c1ed8326b4.png)
  
     <span data-ttu-id="945c8-123">이러한 컨테이너는 1단계 동안 Advanced eDiscovery에서 분석을 위해 준비한 검색 결과를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="945c8-123">These containers represent the search results that you prepared for analysis in Advanced eDiscovery in Step 1.</span></span> <span data-ttu-id="945c8-124">컨테이너의 이름에는 보안 &amp; 규정 준수 센터의 사례에 있는 콘텐츠 검색과 동일한 이름이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="945c8-124">Note that the name of the container has the same name as the Content Search in the case in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="945c8-125">목록에서 컨테이너는 사용자가 준비한 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="945c8-125">The containers in the list are the ones that you prepared.</span></span> <span data-ttu-id="945c8-126">다른 사용자가 Advanced eDiscovery에 사용하도록 검색 결과를 준비한 경우, 해당 컨테이너가 목록에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="945c8-126">If a different user prepared search results for Advanced eDiscovery, the corresponding containers won't be included in the list.</span></span> 
    
6. <span data-ttu-id="945c8-127">Advanced eDiscovery에서 컨테이너에 있는 검색 결과 데이터를 사례에 로드하려면 컨테이너를 선택한 다음 **처리**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="945c8-127">To load the search result data from a container in to the case in Advanced eDiscovery, select a container and then click **Process**.</span></span>
    
<span data-ttu-id="945c8-128">Advanced eDiscovery에서 보안 &amp; 규정 준수 센터의 검색 결과를 사례에 추가한 후, 다음 단계는 Advanced eDiscovery의 도구를 사용하여 사례와 관련된 데이터를 분석하고 선별하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="945c8-128">After the search results from the Security &amp; Compliance Center are added to the case in Advanced eDiscovery, the next step is to use the tools in Advanced eDiscovery to analyze and cull the data that's relevant to the case.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="945c8-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="945c8-129">See also</span></span>

[<span data-ttu-id="945c8-130">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="945c8-130">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="945c8-131">사용자 및 사례 설정</span><span class="sxs-lookup"><span data-stu-id="945c8-131">Setting up users and cases</span></span>](set-up-users-and-cases-in-advanced-ediscovery.md)
  
[<span data-ttu-id="945c8-132">사례 데이터 분석</span><span class="sxs-lookup"><span data-stu-id="945c8-132">Analyzing case data</span></span>](analyze-case-data-with-advanced-ediscovery.md)
  
[<span data-ttu-id="945c8-133">관련성 설정 관리</span><span class="sxs-lookup"><span data-stu-id="945c8-133">Managing Relevance setup</span></span>](manage-relevance-setup-in-advanced-ediscovery.md)
  
[<span data-ttu-id="945c8-134">관련성 모듈 사용</span><span class="sxs-lookup"><span data-stu-id="945c8-134">Using the Relevance module</span></span>](use-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="945c8-135">사례 데이터 내보내기</span><span class="sxs-lookup"><span data-stu-id="945c8-135">Exporting case data</span></span>](export-case-data-in-advanced-ediscovery.md)

