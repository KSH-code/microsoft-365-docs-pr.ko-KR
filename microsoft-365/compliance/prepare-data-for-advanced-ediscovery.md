---
title: Advanced eDiscovery를 위한 데이터 준비
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
description: '보안 및 준수 센터를 사용 하 여 &amp; 고급 eDiscovery로 분석을 위한 데이터를 준비 하는 방법을 알아봅니다. '
ms.openlocfilehash: 31bf002c275b228de12b7ff9e39fabf7c72be74d
ms.sourcegitcommit: 1c90bcc5c56f24895f01c3e0423c3f6b73715c13
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44214286"
---
# <a name="prepare-data-for-advanced-ediscovery-classic"></a><span data-ttu-id="dab80-103">고급 eDiscovery에 대 한 데이터 준비 (클래식)</span><span class="sxs-lookup"><span data-stu-id="dab80-103">Prepare data for Advanced eDiscovery (classic)</span></span>

<span data-ttu-id="dab80-104">이 항목에서는 Advanced eDiscovery (클래식)에서 사례에 대 한 콘텐츠 검색 결과를 로드 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="dab80-104">This topic describes how to load the results of a Content Search in to a case in Advanced eDiscovery (classic).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="dab80-105">최신 버전의 Advanced eDiscovery에 계속 투자함에 따라, Advanced eDiscovery(*Advanced eDiscovery(클래식)* 또는 *Advanced eDiscovery v1.0*이라고도 함)를 발표합니다.</span><span class="sxs-lookup"><span data-stu-id="dab80-105">As we continue to invest in newer versions of Advanced eDiscovery, we are announcing the retirement of Advanced eDiscovery, also known as *Advanced eDiscovery (classic)* or *Advanced eDiscovery v1.0*.</span></span> <span data-ttu-id="dab80-106">Advanced eDiscovery v1.0을 계속 사용하고 있는 경우 [Advanced eDiscovery v2.0](overview-ediscovery-20.md)(*Advanced eDiscovery solution in Microsoft 365*라고도 함)으로 전환하세요.</span><span class="sxs-lookup"><span data-stu-id="dab80-106">If you're still using Advanced eDiscovery v1.0, please transition to [Advanced eDiscovery v2.0](overview-ediscovery-20.md) (also known as the *Advanced eDiscovery solution in Microsoft 365*) as soon as possible.</span></span> <span data-ttu-id="dab80-107">Advanced eDiscovery 2.0에는 Advanced eDiscovery v1.0에 있는 유사한 기능이 포함되어 있습니다. 또한 보유자 관리, 통신 관리, 검토 집합 등의 새로운 기능도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dab80-107">Advanced eDiscovery 2.0 contains similar functionality found in Advanced eDiscovery v1.0, but also offers many new features such as custodian management, communications management, and review sets.</span></span> <span data-ttu-id="dab80-108">Advanced eDiscovery v1.0의 사용 중지에 대한 자세한 내용은 [레거시 eDiscovery 도구의 사용 중지](legacy-ediscovery-retirement.md#advanced-ediscovery-v10)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dab80-108">To learn more about the retirement of Advanced eDiscovery v1.0, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).</span></span>  
  
## <a name="step-1-prepare-data-for-advanced-ediscovery"></a><span data-ttu-id="dab80-109">1 단계: 고급 eDiscovery에 대 한 데이터 준비</span><span class="sxs-lookup"><span data-stu-id="dab80-109">Step 1: Prepare data for Advanced eDiscovery</span></span>

<span data-ttu-id="dab80-110">Advanced eDiscovery를 사용하여 데이터를 분석하려면 Microsoft 365 보안 &amp; 규정 준수 센터(Microsoft 365 보안 &amp; 규정 준수 센터의 **콘텐츠 검색** 페이지에 나열됨)에서 실행하는 콘텐츠 검색 또는 eDiscovery 케이스(보안 &amp; 규정 준수 센터의 **eDiscovery** 페이지에 나열됨)와 관련된 검색의 결과를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dab80-110">To analyze data with Advanced eDiscovery, you can use the results of a Content Search that you run in the Microsoft 365 Security &amp; Compliance Center (listed on the **Content search** page in the Microsoft 365 Security &amp; Compliance Center) or a search associated with an eDiscovery case (listed on the **eDiscovery** page in the Security &amp; Compliance Center).</span></span> 
  
<span data-ttu-id="dab80-111">고급 eDiscovery에서 분석에 대 한 검색 결과를 준비 하는 방법에 대 한 자세한 단계는 [Advanced ediscovery에 대 한 검색 결과 준비](prepare-search-results-for-advanced-ediscovery.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="dab80-111">For the detailed steps on preparing search results for analysis in Advanced eDiscovery, see [Prepare search results for Advanced eDiscovery](prepare-search-results-for-advanced-ediscovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="dab80-112">Microsoft 365 외부에 있는 데이터를 Microsoft 365로 가져와서 고급 eDiscovery에서이를 준비 하 고 분석할 수 있도록 하려는 경우에는 [PST 파일을 microsoft 365로 가져오기](https://docs.microsoft.com/microsoft-365/compliance/importing-pst-files-to-office-365) , [타사 데이터 보관](https://www.microsoft.com/?ref=go)에 대 한 개요를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dab80-112">If you have data outside of Microsoft 365 and want to import it to Microsoft 365 so that you can prepare and analyze it in Advanced eDiscovery, a see [Overview of importing PST files to Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/importing-pst-files-to-office-365) and [Archiving third-party data](https://www.microsoft.com/?ref=go).</span></span> 
  
## <a name="step-2-load-search-result-data-in-to-a-case-in-advanced-ediscovery"></a><span data-ttu-id="dab80-113">2단계: Advanced eDiscovery에서 사례에 검색 결과 데이터 로드</span><span class="sxs-lookup"><span data-stu-id="dab80-113">Step 2: Load search result data in to a case in Advanced eDiscovery</span></span>

<span data-ttu-id="dab80-114">분석을 위해 보안 &amp; 규정 준수 센터의 검색 결과를 준비한 후, 다음 단계는 Advanced eDiscovery에서 케이스에 검색 결과를 로드하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="dab80-114">After you prepare the search results in the Security &amp; Compliance Center for analysis, the next step is to load the search results in to a case in Advanced eDiscovery.</span></span> <span data-ttu-id="dab80-115">자세한 내용은 [프로세스 모듈 실행](run-the-process-module-in-advanced-ediscovery.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dab80-115">For more detailed information, see [Run the Process module](run-the-process-module-in-advanced-ediscovery.md).</span></span>
  
1. <span data-ttu-id="dab80-116">[https://protection.office.com](https://protection.office.com)으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="dab80-116">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="dab80-117">회사 또는 학교 계정을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="dab80-117">Sign in using your work or school account.</span></span>
    
3. <span data-ttu-id="dab80-118">보안 및 준수 센터에서 **검색 &amp; 조사** \> **eDiscovery**를 클릭하여 조직의 사례 목록을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="dab80-118">In the Security &amp; Compliance Center, click **Search &amp; investigation** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
4. <span data-ttu-id="dab80-119">Advanced eDiscovery에서 데이터를 로드할 사례 옆에 있는 **열기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dab80-119">Click **Open** next to the case that you want to load data in to in Advanced eDiscovery.</span></span> 
    
5. <span data-ttu-id="dab80-120">사례에 대한 **홈** 페이지에서 **Advanced eDiscovery**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dab80-120">On the **Home** page for the case, click **Advanced eDiscovery**.</span></span> 
    
    ![Advanced eDiscovery로 전환을 클릭하여 Advanced eDiscovery에서 케이스를 엽니다.](../media/8e34ba23-62e3-4e68-a530-b6ece39b54be.png)
  
    <span data-ttu-id="dab80-122">**Advanced eDiscovery에 연결하는 중** 진행률 표시줄이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dab80-122">The **Connecting to Advanced eDiscovery** progress bar is displayed.</span></span> <span data-ttu-id="dab80-123">Advanced eDiscovery에 연결되면 컨테이너 목록이 해당 케이스의 설정 페이지에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dab80-123">When you're connected to Advanced eDiscovery, a list of containers is displayed on the setup page for the case.</span></span> 
    
    ![케이스가 Advanced eDiscovery에 표시됩니다.](../media/8036e152-70dc-4bb7-9379-61c1ed8326b4.png)
  
     <span data-ttu-id="dab80-125">이러한 컨테이너는 1단계 동안 Advanced eDiscovery에서 분석을 위해 준비한 검색 결과를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dab80-125">These containers represent the search results that you prepared for analysis in Advanced eDiscovery in Step 1.</span></span> <span data-ttu-id="dab80-126">컨테이너의 이름에는 보안 &amp; 규정 준수 센터의 사례에 있는 콘텐츠 검색과 동일한 이름이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dab80-126">Note that the name of the container has the same name as the Content Search in the case in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="dab80-127">목록에서 컨테이너는 사용자가 준비한 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="dab80-127">The containers in the list are the ones that you prepared.</span></span> <span data-ttu-id="dab80-128">다른 사용자가 Advanced eDiscovery에 사용하도록 검색 결과를 준비한 경우, 해당 컨테이너가 목록에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dab80-128">If a different user prepared search results for Advanced eDiscovery, the corresponding containers won't be included in the list.</span></span> 
    
6. <span data-ttu-id="dab80-129">Advanced eDiscovery에서 컨테이너에 있는 검색 결과 데이터를 사례에 로드하려면 컨테이너를 선택한 다음 **처리**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dab80-129">To load the search result data from a container in to the case in Advanced eDiscovery, select a container and then click **Process**.</span></span>
    
<span data-ttu-id="dab80-130">Advanced eDiscovery에서 보안 &amp; 규정 준수 센터의 검색 결과를 사례에 추가한 후, 다음 단계는 Advanced eDiscovery의 도구를 사용하여 사례와 관련된 데이터를 분석하고 선별하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="dab80-130">After the search results from the Security &amp; Compliance Center are added to the case in Advanced eDiscovery, the next step is to use the tools in Advanced eDiscovery to analyze and cull the data that's relevant to the case.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="dab80-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dab80-131">See also</span></span>

[<span data-ttu-id="dab80-132">고급 eDiscovery (클래식)</span><span class="sxs-lookup"><span data-stu-id="dab80-132">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="dab80-133">사용자 및 사례 설정</span><span class="sxs-lookup"><span data-stu-id="dab80-133">Set up users and cases</span></span>](set-up-users-and-cases-in-advanced-ediscovery.md)
  
[<span data-ttu-id="dab80-134">사례 데이터 분석</span><span class="sxs-lookup"><span data-stu-id="dab80-134">Analyzing case data</span></span>](analyze-case-data-with-advanced-ediscovery.md)
  
[<span data-ttu-id="dab80-135">관련성 설정 관리</span><span class="sxs-lookup"><span data-stu-id="dab80-135">Managing Relevance setup</span></span>](manage-relevance-setup-in-advanced-ediscovery.md)
  
[<span data-ttu-id="dab80-136">관련성 모듈 사용</span><span class="sxs-lookup"><span data-stu-id="dab80-136">Using the Relevance module</span></span>](use-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="dab80-137">사례 데이터 내보내기</span><span class="sxs-lookup"><span data-stu-id="dab80-137">Exporting case data</span></span>](export-case-data-in-advanced-ediscovery.md)

