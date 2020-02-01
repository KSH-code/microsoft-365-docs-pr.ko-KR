---
title: Office 365 Advanced eDiscovery에 대한 데이터 준비
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
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
ms.assetid: 2fb94c23-1846-4a0e-994d-da6d02445f15
description: 'Microsoft 365 보안 &amp; 규정 준수 센터에서 Office 365 Advanced eDiscovery를 사용하여 Office 365 데이터를 분석할 수 있도록 준비하는 방법을 알아봅니다. '
ms.openlocfilehash: 6407b6f2a2bbe9bc69842057232ec01569ef64c8
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597765"
---
# <a name="prepare-data-for-office-365-advanced-ediscovery"></a><span data-ttu-id="2b13b-103">Office 365 Advanced eDiscovery에 대한 데이터 준비</span><span class="sxs-lookup"><span data-stu-id="2b13b-103">Prepare data for Office 365 Advanced eDiscovery</span></span>

<span data-ttu-id="2b13b-104">이 항목에서는 Advanced eDiscovery에서 콘텐츠 검색 결과를 사례에 로드하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2b13b-104">This topic describes how to load the results of a Content Search in to a case in Advanced eDiscovery.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="2b13b-105">최신 버전의 Advanced eDiscovery에 계속 투자 하면 Office 365 Advanced eDiscovery ( *고급 ediscovery v 1.0*이 라고도 함)가 만료 됨을 알리는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2b13b-105">As we continue to invest in newer versions of Advanced eDiscovery, we are announcing the retirement of Office 365 Advanced eDiscovery (also known as *Advanced eDiscovery v1.0*).</span></span> <span data-ttu-id="2b13b-106">여전히 고급 eDiscovery v 1.0을 사용 중인 경우에는 가능한 한 빨리 [Advanced ediscovery v 2.0](overview-ediscovery-20.md) ( *Microsoft 365의 고급 ediscovery 솔루션*이 라고도 함)으로 전환 하세요.</span><span class="sxs-lookup"><span data-stu-id="2b13b-106">If you're still using Advanced eDiscovery v1.0, please transition to [Advanced eDiscovery v2.0](overview-ediscovery-20.md) (also known as the *Advanced eDiscovery solution in Microsoft 365*) as soon as possible.</span></span> <span data-ttu-id="2b13b-107">Advanced eDiscovery 2.0에는 Advanced eDiscovery v 1.0과 비슷한 기능이 포함 되어 있지만 custodian 관리, 통신 관리 및 검토 집합과 같은 다양 한 새로운 기능도 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b13b-107">Advanced eDiscovery 2.0 contains similar functionality found in Advanced eDiscovery v1.0, but also offers many new features such as custodian management, communications management, and review sets.</span></span> <span data-ttu-id="2b13b-108">Advanced eDiscovery v 1.0의 만료에 대 한 자세한 내용은 [레거시 ediscovery 도구 만료](legacy-ediscovery-retirement.md#advanced-ediscovery-v10)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2b13b-108">To learn more about the retirement of Advanced eDiscovery v1.0, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).</span></span>  
  
## <a name="step-1-prepare-office-365-data-for-advanced-ediscovery"></a><span data-ttu-id="2b13b-109">1단계: Advanced eDiscovery에 사용하도록 Office 365 데이터 준비</span><span class="sxs-lookup"><span data-stu-id="2b13b-109">Step 1: Prepare Office 365 data for Advanced eDiscovery</span></span>

<span data-ttu-id="2b13b-110">Advanced eDiscovery를 사용하여 데이터를 분석하려면 Microsoft 365 보안 &amp; 규정 준수 센터(Microsoft 365 보안 &amp; 규정 준수 센터의 **콘텐츠 검색** 페이지에 나열됨)에서 실행하는 콘텐츠 검색 또는 eDiscovery 케이스(보안 &amp; 규정 준수 센터의 **eDiscovery** 페이지에 나열됨)와 관련된 검색의 결과를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b13b-110">To analyze data with Advanced eDiscovery, you can use the results of a Content Search that you run in the Microsoft 365 Security &amp; Compliance Center (listed on the **Content search** page in the Microsoft 365 Security &amp; Compliance Center) or a search associated with an eDiscovery case (listed on the **eDiscovery** page in the Security &amp; Compliance Center).</span></span> 
  
<span data-ttu-id="2b13b-111">Advanced eDiscovery에서 분석할 수 있도록 검색 결과를 준비하는 방법에 대한 자세한 내용은 [Office 365 Advanced eDiscovery에 사용하도록 검색 결과 준비](prepare-search-results-for-advanced-ediscovery.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2b13b-111">For the detailed steps on preparing search results for analysis in Advanced eDiscovery, see [Prepare search results for Office 365 Advanced eDiscovery](prepare-search-results-for-advanced-ediscovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="2b13b-112">Office 365 외부에 데이터가 있고 Advanced eDiscovery에서 이 데이터를 준비하고 분석할 수 있도록 Office 365로 가져오려면 [Office 365로 PST 파일을 가져오는 방법에 대한 개요](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84) 및 [Office 365에 타사 데이터 보관](https://go.microsoft.com/fwlink/p/?linkid=716918)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2b13b-112">If you have data outside of Office 365 and want to import it to Office 365 so that you can prepare and analyze it in Advanced eDiscovery, a see [Overview of importing PST files to Office 365](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84) and [Archiving third-party data in Office 365](https://go.microsoft.com/fwlink/p/?linkid=716918).</span></span> 
  
## <a name="step-2-load-search-result-data-in-to-a-case-in-advanced-ediscovery"></a><span data-ttu-id="2b13b-113">2단계: Advanced eDiscovery에서 사례에 검색 결과 데이터 로드</span><span class="sxs-lookup"><span data-stu-id="2b13b-113">Step 2: Load search result data in to a case in Advanced eDiscovery</span></span>

<span data-ttu-id="2b13b-114">분석을 위해 보안 &amp; 규정 준수 센터의 검색 결과를 준비한 후, 다음 단계는 Advanced eDiscovery에서 케이스에 검색 결과를 로드하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2b13b-114">After you prepare the search results in the Security &amp; Compliance Center for analysis, the next step is to load the search results in to a case in Advanced eDiscovery.</span></span> <span data-ttu-id="2b13b-115">자세한 내용은 [프로세스 모듈 실행](run-the-process-module-in-advanced-ediscovery.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2b13b-115">For more detailed information, see [Run the Process module](run-the-process-module-in-advanced-ediscovery.md).</span></span>
  
1. <span data-ttu-id="2b13b-116">[https://protection.office.com](https://protection.office.com)으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="2b13b-116">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="2b13b-117">회사 또는 학교 계정을 사용하여 Office 365에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="2b13b-117">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="2b13b-118">보안 및 준수 센터에서 **검색 &amp; 조사** \> **eDiscovery**를 클릭하여 조직의 사례 목록을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2b13b-118">In the Security &amp; Compliance Center, click **Search &amp; investigation** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
4. <span data-ttu-id="2b13b-119">Advanced eDiscovery에서 데이터를 로드할 사례 옆에 있는 **열기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2b13b-119">Click **Open** next to the case that you want to load data in to in Advanced eDiscovery.</span></span> 
    
5. <span data-ttu-id="2b13b-120">사례에 대한 **홈** 페이지에서 **Advanced eDiscovery**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2b13b-120">On the **Home** page for the case, click **Advanced eDiscovery**.</span></span> 
    
    ![Advanced eDiscovery로 전환을 클릭하여 Advanced eDiscovery에서 케이스를 엽니다.](media/8e34ba23-62e3-4e68-a530-b6ece39b54be.png)
  
    <span data-ttu-id="2b13b-122">**Advanced eDiscovery에 연결하는 중** 진행률 표시줄이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b13b-122">The **Connecting to Advanced eDiscovery** progress bar is displayed.</span></span> <span data-ttu-id="2b13b-123">Advanced eDiscovery에 연결되면 컨테이너 목록이 해당 케이스의 설정 페이지에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b13b-123">When you're connected to Advanced eDiscovery, a list of containers is displayed on the setup page for the case.</span></span> 
    
    ![케이스가 Advanced eDiscovery에 표시됩니다.](media/8036e152-70dc-4bb7-9379-61c1ed8326b4.png)
  
     <span data-ttu-id="2b13b-125">이러한 컨테이너는 1단계 동안 Advanced eDiscovery에서 분석을 위해 준비한 검색 결과를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2b13b-125">These containers represent the search results that you prepared for analysis in Advanced eDiscovery in Step 1.</span></span> <span data-ttu-id="2b13b-126">컨테이너의 이름에는 보안 &amp; 규정 준수 센터의 사례에 있는 콘텐츠 검색과 동일한 이름이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b13b-126">Note that the name of the container has the same name as the Content Search in the case in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="2b13b-127">목록에서 컨테이너는 사용자가 준비한 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="2b13b-127">The containers in the list are the ones that you prepared.</span></span> <span data-ttu-id="2b13b-128">다른 사용자가 Advanced eDiscovery에 사용하도록 검색 결과를 준비한 경우, 해당 컨테이너가 목록에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b13b-128">If a different user prepared search results for Advanced eDiscovery, the corresponding containers won't be included in the list.</span></span> 
    
6. <span data-ttu-id="2b13b-129">Advanced eDiscovery에서 컨테이너에 있는 검색 결과 데이터를 사례에 로드하려면 컨테이너를 선택한 다음 **처리**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2b13b-129">To load the search result data from a container in to the case in Advanced eDiscovery, select a container and then click **Process**.</span></span>
    
<span data-ttu-id="2b13b-130">Advanced eDiscovery에서 보안 &amp; 규정 준수 센터의 검색 결과를 사례에 추가한 후, 다음 단계는 Advanced eDiscovery의 도구를 사용하여 사례와 관련된 데이터를 분석하고 선별하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2b13b-130">After the search results from the Security &amp; Compliance Center are added to the case in Advanced eDiscovery, the next step is to use the tools in Advanced eDiscovery to analyze and cull the data that's relevant to the case.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="2b13b-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2b13b-131">See also</span></span>

[<span data-ttu-id="2b13b-132">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="2b13b-132">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="2b13b-133">사용자 및 사례 설정</span><span class="sxs-lookup"><span data-stu-id="2b13b-133">Set up users and cases</span></span>](set-up-users-and-cases-in-advanced-ediscovery.md)
  
[<span data-ttu-id="2b13b-134">사례 데이터 분석</span><span class="sxs-lookup"><span data-stu-id="2b13b-134">Analyzing case data</span></span>](analyze-case-data-with-advanced-ediscovery.md)
  
[<span data-ttu-id="2b13b-135">관련성 설정 관리</span><span class="sxs-lookup"><span data-stu-id="2b13b-135">Managing Relevance setup</span></span>](manage-relevance-setup-in-advanced-ediscovery.md)
  
[<span data-ttu-id="2b13b-136">관련성 모듈 사용</span><span class="sxs-lookup"><span data-stu-id="2b13b-136">Using the Relevance module</span></span>](use-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="2b13b-137">사례 데이터 내보내기</span><span class="sxs-lookup"><span data-stu-id="2b13b-137">Exporting case data</span></span>](export-case-data-in-advanced-ediscovery.md)

