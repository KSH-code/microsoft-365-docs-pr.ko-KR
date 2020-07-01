---
title: 고급 eDiscovery 빠른 설정
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
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: d7ccd944-9698-41c7-a21b-677dc62973c4
description: 보안 &amp; 준수 센터에서 Advanced eDiscovery에 액세스하는 방법을 알아보고 Advanced eDiscovery를 사용하기 위한 일반적인 워크플로를 검토합니다.
ms.openlocfilehash: 5bd183f0f5f1c2f091fb374aab1e54f191665ce6
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936261"
---
# <a name="quick-setup-advanced-ediscovery-classic"></a><span data-ttu-id="80f85-103">고급 eDiscovery 빠른 설정(클래식)</span><span class="sxs-lookup"><span data-stu-id="80f85-103">Quick setup Advanced eDiscovery (classic)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="80f85-104">최신 버전의 Advanced eDiscovery에 계속 투자함에 따라, Advanced eDiscovery(*Advanced eDiscovery(클래식)* 또는 *Advanced eDiscovery v1.0*이라고도 함)를 발표합니다.</span><span class="sxs-lookup"><span data-stu-id="80f85-104">As we continue to invest in newer versions of Advanced eDiscovery, we are announcing the retirement of Advanced eDiscovery, also known as *Advanced eDiscovery (classic)* or *Advanced eDiscovery v1.0*.</span></span> <span data-ttu-id="80f85-105">Advanced eDiscovery v1.0을 계속 사용하고 있는 경우 [Advanced eDiscovery v2.0](overview-ediscovery-20.md)(*Advanced eDiscovery solution in Microsoft 365*라고도 함)으로 전환하세요.</span><span class="sxs-lookup"><span data-stu-id="80f85-105">If you're still using Advanced eDiscovery v1.0, please transition to [Advanced eDiscovery v2.0](overview-ediscovery-20.md) (also known as the *Advanced eDiscovery solution in Microsoft 365*) as soon as possible.</span></span> <span data-ttu-id="80f85-106">Advanced eDiscovery 2.0에는 Advanced eDiscovery v1.0에 있는 유사한 기능이 포함되어 있습니다. 또한 보유자 관리, 통신 관리, 검토 집합 등의 새로운 기능도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="80f85-106">Advanced eDiscovery 2.0 contains similar functionality found in Advanced eDiscovery v1.0, but also offers many new features such as custodian management, communications management, and review sets.</span></span> <span data-ttu-id="80f85-107">Advanced eDiscovery v1.0의 사용 중지에 대한 자세한 내용은 [레거시 eDiscovery 도구의 사용 중지](legacy-ediscovery-retirement.md#advanced-ediscovery-v10)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="80f85-107">To learn more about the retirement of Advanced eDiscovery v1.0, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).</span></span> 

<span data-ttu-id="80f85-108">이 설정 섹션에는 Advanced eDiscovery를 시작하는 방법에 대한 Microsoft 365 보안 &amp; 준수 센터 eDiscovery 관리자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="80f85-108">This setup section shows an Microsoft 365 Security &amp; Compliance Center eDiscovery manager how to get started with Advanced eDiscovery.</span></span> <span data-ttu-id="80f85-109">사용자에게 두 기능에 대한 작업 지식이 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="80f85-109">A working knowledge of both is assumed.</span></span>
  
## <a name="accessing-a-case-in-advanced-ediscovery"></a><span data-ttu-id="80f85-110">Advanced eDiscovery에서 사례에 액세스</span><span class="sxs-lookup"><span data-stu-id="80f85-110">Accessing a case in Advanced eDiscovery</span></span>

<span data-ttu-id="80f85-111">You access Advanced eDiscovery from the Security &amp; Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="80f85-111">You access Advanced eDiscovery from the Security &amp; Compliance Center.</span></span> <span data-ttu-id="80f85-112">You have to be a member of an eDiscovery case in the Security &amp; Compliance Center to access the case in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="80f85-112">You have to be a member of an eDiscovery case in the Security &amp; Compliance Center to access the case in Advanced eDiscovery.</span></span> <span data-ttu-id="80f85-113">For instructions about assigning eDiscovery case permissions and adding users to an eDiscovery case, see [Manage eDiscovery cases in Office 365](ediscovery-cases.md).</span><span class="sxs-lookup"><span data-stu-id="80f85-113">For instructions about assigning eDiscovery case permissions and adding users to an eDiscovery case, see [Manage eDiscovery cases in Office 365](ediscovery-cases.md).</span></span> 
  
<span data-ttu-id="80f85-114">Advanced eDiscovery에서 사례로 이동하려면</span><span class="sxs-lookup"><span data-stu-id="80f85-114">To go to a case in Advanced eDiscovery:</span></span> 
  
1. <span data-ttu-id="80f85-115">[보안 &amp; 준수 센터로 이동](go-to-the-securitycompliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="80f85-115">[Go to the Security &amp; Compliance Center](go-to-the-securitycompliance-center.md) .</span></span> 
    
2. <span data-ttu-id="80f85-116">보안 및 준수 센터에서 **검색 &amp; 조사** \> **eDiscovery**를 클릭하여 조직의 사례 목록을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="80f85-116">In the Security &amp; Compliance Center, click **Search &amp; investigation** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
3. <span data-ttu-id="80f85-117">**eDiscovery** 페이지에서 Advanced eDiscovery의 이동하려는 사례 옆에 있는 **열기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="80f85-117">On the **eDiscovery** page, click **Open** next to the case that you want to go to in Advanced eDiscovery.</span></span>
    
4. <span data-ttu-id="80f85-118">사례에 대한 **홈** 페이지에서 **Advanced eDiscovery로 전환**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="80f85-118">On the **Home** page for the case, click **Switch to Advanced eDiscovery**.</span></span>
    
    <span data-ttu-id="80f85-119">The **Connecting to Advanced eDiscovery** progress bar is displayed.</span><span class="sxs-lookup"><span data-stu-id="80f85-119">The **Connecting to Advanced eDiscovery** progress bar is displayed.</span></span> <span data-ttu-id="80f85-120">When you're connected, the case is opened in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="80f85-120">When you're connected, the case is opened in Advanced eDiscovery.</span></span> 
    
## <a name="workflow"></a><span data-ttu-id="80f85-121">워크플로</span><span class="sxs-lookup"><span data-stu-id="80f85-121">Workflow</span></span>

<span data-ttu-id="80f85-122">다음 다이어그램에서는 보안 및 인증 센터와 Advanced eDiscovery에서 사례를 관리 및 사용하기 위한 일반적인 워크플로를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="80f85-122">The following diagram illustrates the common workflow for managing and using eDiscovery cases in the Security &amp; Compliance Center and Advanced eDiscovery.</span></span>
  
![다이어그램은 사용자 &amp; 사례 설정, 사례 데이터 식별, 내보내기 및 처리를 포함하는 4가지 설정 단계와 분석 및 로컬 시스템으로 내보내기 단계를 포함하는 Advanced eDiscovery 워크플로를 표시합니다.](../media/76589ccc-789d-4581-b3a8-98d339b05979.png)
  
<span data-ttu-id="80f85-124">This setup section describes the first four steps in the workflow.</span><span class="sxs-lookup"><span data-stu-id="80f85-124">This setup section describes the first four steps in the workflow.</span></span> <span data-ttu-id="80f85-125">For a description of the other steps in the workflow, see the following.</span><span class="sxs-lookup"><span data-stu-id="80f85-125">For a description of the other steps in the workflow, see the following.</span></span>
  
## <a name="analyze"></a><span data-ttu-id="80f85-126">분석</span><span class="sxs-lookup"><span data-stu-id="80f85-126">Analyze</span></span>

<span data-ttu-id="80f85-127">[Analyzing case data](analyze-case-data-with-advanced-ediscovery.md) Identifies and organizes the files by various parameters, enables the use of Themes, and displays the results.</span><span class="sxs-lookup"><span data-stu-id="80f85-127">[Analyzing case data](analyze-case-data-with-advanced-ediscovery.md) Identifies and organizes the files by various parameters, enables the use of Themes, and displays the results.</span></span> <span data-ttu-id="80f85-128">Analyze functionality can be customized by the user in order to achieve enhanced results.</span><span class="sxs-lookup"><span data-stu-id="80f85-128">Analyze functionality can be customized by the user in order to achieve enhanced results.</span></span> 
  
## <a name="relevance-setup-and-relevance"></a><span data-ttu-id="80f85-129">관련성 설정 및 관련성</span><span class="sxs-lookup"><span data-stu-id="80f85-129">Relevance Setup and Relevance</span></span>

<span data-ttu-id="80f85-130">[Relevance Setup](manage-relevance-setup-in-advanced-ediscovery.md) and [Using the Relevance module](use-relevance-in-advanced-ediscovery.md) Enables assessment and relevance training based on a random sample of files and uses them to apply decisions to the predictive coding process.</span><span class="sxs-lookup"><span data-stu-id="80f85-130">[Relevance Setup](manage-relevance-setup-in-advanced-ediscovery.md) and [Using the Relevance module](use-relevance-in-advanced-ediscovery.md) Enables assessment and relevance training based on a random sample of files and uses them to apply decisions to the predictive coding process.</span></span> <span data-ttu-id="80f85-131">Calculates and displays interim results while monitoring statistical validity of the process.</span><span class="sxs-lookup"><span data-stu-id="80f85-131">Calculates and displays interim results while monitoring statistical validity of the process.</span></span> <span data-ttu-id="80f85-132">Displays the results to facilitate in making review decisions.</span><span class="sxs-lookup"><span data-stu-id="80f85-132">Displays the results to facilitate in making review decisions.</span></span> 
  
## <a name="export"></a><span data-ttu-id="80f85-133">내보내기</span><span class="sxs-lookup"><span data-stu-id="80f85-133">Export</span></span>

<span data-ttu-id="80f85-134">[사례 데이터 내보내기](export-case-data-in-advanced-ediscovery.md) 외부 검토를 위해 Advanced eDiscovery 콘텐츠 및 결과를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80f85-134">[Exporting case data](export-case-data-in-advanced-ediscovery.md) Enables the exporting of Advanced eDiscovery content and results for external review.</span></span> 
  
## <a name="report"></a><span data-ttu-id="80f85-135">보고서</span><span class="sxs-lookup"><span data-stu-id="80f85-135">Report</span></span>

<span data-ttu-id="80f85-136">[보고서 실행](run-reports-in-advanced-ediscovery.md) Advanced eDiscovery 처리와 관련해서 선택한 보고서를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80f85-136">[Running reports](run-reports-in-advanced-ediscovery.md) Enables the generation of selected reports related to Advanced eDiscovery processing.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="80f85-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="80f85-137">See also</span></span>

[<span data-ttu-id="80f85-138">고급 eDiscovery (클래식)</span><span class="sxs-lookup"><span data-stu-id="80f85-138">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="80f85-139">사용자 및 사례 설정</span><span class="sxs-lookup"><span data-stu-id="80f85-139">Setting up users and cases</span></span>](set-up-users-and-cases-in-advanced-ediscovery.md)
  
[<span data-ttu-id="80f85-140">데이터 준비</span><span class="sxs-lookup"><span data-stu-id="80f85-140">Preparing data</span></span>](prepare-data-for-advanced-ediscovery.md)

