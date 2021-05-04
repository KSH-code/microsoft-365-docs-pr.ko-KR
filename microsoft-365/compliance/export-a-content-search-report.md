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
ms.openlocfilehash: fec6e441458ad7429067a1314a7aec3824aff11a
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760156"
---
# <a name="export-a-content-search-report"></a><span data-ttu-id="0c36d-104">콘텐츠 검색 보고서 내보내기</span><span class="sxs-lookup"><span data-stu-id="0c36d-104">Export a Content Search report</span></span>

<span data-ttu-id="0c36d-105">보안 & 준수 센터의 콘텐츠 검색 및 eDiscovery 사례와 연결된 콘텐츠 검색에서 전체 검색 결과 집합을 내보내는 대신 검색 결과를 내보낼 때 생성되는 동일한 보고서를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-105">Instead of exporting the full set of search results from a Content Search in the Security & Compliance Center (and from a Content Search that's associated with an eDiscovery case), you can export the same reports that are generated when you export search results.</span></span>
  
<span data-ttu-id="0c36d-106">보고서를 내보낼 때 콘텐츠 검색과 이름이 같지만 에 추가된 폴더로 *_ReportsOnly.*</span><span class="sxs-lookup"><span data-stu-id="0c36d-106">When you export a report, it's downloaded to a folder that has the same name as the Content Search, but that's appended with *_ReportsOnly*.</span></span> <span data-ttu-id="0c36d-107">예를 들어 콘텐츠 검색의 이름이 *ContosoCase0815이면* 보고서가 이라는 폴더로 *ContosoCase0815_ReportsOnly.*</span><span class="sxs-lookup"><span data-stu-id="0c36d-107">For example, if the Content Search is named  *ContosoCase0815*, then the report is downloaded to a folder named *ContosoCase0815_ReportsOnly*.</span></span> <span data-ttu-id="0c36d-108">보고서에 포함된 문서 목록은 보고서에 포함된 항목 을 [참조하세요.](#whats-included-in-the-report)</span><span class="sxs-lookup"><span data-stu-id="0c36d-108">For a list of documents that are included in the report, see [What's included in the report](#whats-included-in-the-report).</span></span>

## <a name="assign-roles-and-check-system-requirements"></a><span data-ttu-id="0c36d-109">역할 할당 및 시스템 요구 사항 확인</span><span class="sxs-lookup"><span data-stu-id="0c36d-109">Assign roles and check system requirements</span></span>

- <span data-ttu-id="0c36d-110">콘텐츠 검색 보고서를 내보내기 위해 보안 및 준수 센터에서 준수 검색 관리 & 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-110">To export a Content Search report, you have to be assigned the Compliance Search management role in the Security & Compliance Center.</span></span> <span data-ttu-id="0c36d-111">이 역할은 기본적으로 기본 제공 eDiscovery 관리자 및 조직 관리 역할 그룹에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-111">This role is assigned by default to the built-in eDiscovery Manager and Organization Management role groups.</span></span> <span data-ttu-id="0c36d-112">자세한 내용은 [eDiscovery 권한 할당](assign-ediscovery-permissions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0c36d-112">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="0c36d-113">보고서를 내보낼 때 데이터는 로컬 컴퓨터로 다운로드되기 Azure Storage Microsoft 클라우드의 고유한 Azure Storage 영역에 일시적으로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-113">When you export a report, the data is temporarily stored in a unique Azure Storage area in the Microsoft cloud before it's downloaded to your local computer.</span></span> <span data-ttu-id="0c36d-114">조직에서 **\* .blob.core.windows.net** Azure의 끝점에 연결할 수 있는지 확인(와일드카드는 내보내기 고유 식별자를 나타임)</span><span class="sxs-lookup"><span data-stu-id="0c36d-114">Be sure that your organization can connect to the endpoint in Azure, which is **\*.blob.core.windows.net** (the wildcard represents a unique identifier for your export).</span></span> <span data-ttu-id="0c36d-115">검색 결과 데이터는 생성된 Azure Storage 영역에서 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-115">The search results data is deleted from the Azure Storage area two weeks after it's created.</span></span>

- <span data-ttu-id="0c36d-116">검색 결과를 PST 파일로 내보내는 데 사용하는 컴퓨터는 다음과 같은 시스템 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-116">The computer you use to export the search results has to meet the following system requirements:</span></span>

  - <span data-ttu-id="0c36d-117">최신 버전의 Windows(32비트 또는 64비트)</span><span class="sxs-lookup"><span data-stu-id="0c36d-117">Latest version of Windows (32-bit or 64-bit)</span></span>

  - <span data-ttu-id="0c36d-118">Microsoft .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="0c36d-118">Microsoft .NET Framework 4.7</span></span>

- <span data-ttu-id="0c36d-119">eDiscovery 내보내기 도구 1을 실행하려면 다음 지원되는 브라우저 중<sup>하나를 사용해야 합니다.</sup></span><span class="sxs-lookup"><span data-stu-id="0c36d-119">You have to use one of the following supported browsers to run the eDiscovery Export Tool<sup>1</sup>:</span></span>

  - <span data-ttu-id="0c36d-120">Microsoft Edge <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="0c36d-120">Microsoft Edge <sup>2</sup></span></span>

    <span data-ttu-id="0c36d-121">또는</span><span class="sxs-lookup"><span data-stu-id="0c36d-121">OR</span></span>

  - <span data-ttu-id="0c36d-122">Microsoft Internet Explorer 10 이상 버전</span><span class="sxs-lookup"><span data-stu-id="0c36d-122">Microsoft Internet Explorer 10 and later versions</span></span>

  > [!NOTE]
  > <span data-ttu-id="0c36d-123"><sup>1</sup> Microsoft는 타사 응용 프로그램용 타사 확장 또는 추가 ClickOnce 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-123"><sup>1</sup> Microsoft doesn't manufacture third-party extensions or add-ons for ClickOnce applications.</span></span> <span data-ttu-id="0c36d-124">타사 확장 또는 추가 기능이 있는 지원되지 않는 브라우저를 사용하여 검색 결과를 내보낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-124">Exporting search results using an unsupported browser with third-party extensions or add-ons isn't supported.</span></span><br/>
  > <span data-ttu-id="0c36d-125"><sup>2</sup> 최신 변경으로 인해 Microsoft Edge ClickOnce 기본적으로 지원이 설정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-125"><sup>2</sup> As a result of recent changes to Microsoft Edge, ClickOnce support is no longer enabled by default.</span></span> <span data-ttu-id="0c36d-126">Edge에서 ClickOnce 지원을 사용하도록 설정하는 방법에 대한 지침은 에서 [eDiscovery 내보내기 도구 Microsoft Edge.](configure-edge-to-export-search-results.md)</span><span class="sxs-lookup"><span data-stu-id="0c36d-126">For instructions on enabling ClickOnce support in Edge, see [Use the eDiscovery Export Tool in Microsoft Edge](configure-edge-to-export-search-results.md).</span></span>

- <span data-ttu-id="0c36d-127">콘텐츠 검색에서 반환된 결과의 예상 총 크기가 2 TB를 초과하면 보고서를 내보내지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-127">If the estimated total size of the results returned by a Content Search exceeds 2 TB, exporting the report fails.</span></span> <span data-ttu-id="0c36d-128">보고서를 내보낼 수 있도록 범위 범위를 좁히고 결과의 예상 크기가 2 TB 미만이 있도록 검색을 다시 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-128">To successfully export the report, try to narrow the scope and rerun the search so the estimated size of the results is less than 2 TB.</span></span>

- <span data-ttu-id="0c36d-129">콘텐츠 검색 보고서 내보내기에서는 동시에 실행되는 최대 내보내기 수와 단일 사용자가 실행할 수 있는 최대 내보내기 수를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-129">Exporting Content Search reports counts against the maximum number of exports running at the same time and the maximum number of exports that a single user can run.</span></span> <span data-ttu-id="0c36d-130">내보내기 제한에 대한 자세한 내용은 콘텐츠 검색 결과 [내보내기 를 참조하세요.](export-search-results.md#export-limits)</span><span class="sxs-lookup"><span data-stu-id="0c36d-130">For more information about export limits, see [Export Content Search results](export-search-results.md#export-limits).</span></span>

## <a name="generate-and-download-a-content-search-report"></a><span data-ttu-id="0c36d-131">콘텐츠 검색 보고서 생성 및 다운로드</span><span class="sxs-lookup"><span data-stu-id="0c36d-131">Generate and download a Content Search report</span></span>

<span data-ttu-id="0c36d-132">콘텐츠 검색 보고서를 생성하고 다운로드하는 단계는 실제로 검색 결과를 내보내는 단계와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-132">The steps to generate and download a Content Search report are similar to actually exporting search results.</span></span>
  
## <a name="step-1-generate-the-report-for-export"></a><span data-ttu-id="0c36d-133">1단계: 내보내기용 보고서 생성</span><span class="sxs-lookup"><span data-stu-id="0c36d-133">Step 1: Generate the report for export</span></span>

<span data-ttu-id="0c36d-134">첫 번째 단계는 내보낼 컴퓨터로 다운로드할 보고서를 준비하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-134">The first step is to prepare the report for downloading to your computer exporting.</span></span> <span data-ttu-id="0c36d-135">보고서를 사용하면 보고서 문서가 Microsoft 클라우드의 Azure Storage 영역으로 업로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-135">When you the report, the report documents are uploaded to an Azure Storage area in the Microsoft cloud.</span></span>
  
1. <span data-ttu-id="0c36d-136">[https://protection.office.com](https://protection.office.com)으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-136">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="0c36d-137">회사 또는 학교 계정을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-137">Sign in using your work or school account.</span></span>
    
3. <span data-ttu-id="0c36d-138">보안 및 준수 센터의 왼쪽 & 콘텐츠 검색을  \> **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0c36d-138">In the left pane of the Security & Compliance Center, click **Search** \> **Content search**.</span></span>
    
4. <span data-ttu-id="0c36d-139">콘텐츠 **검색 페이지에서** 검색을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-139">On the **Content search** page, select a search.</span></span> 
    
5. <span data-ttu-id="0c36d-140">세부 정보 창의 **컴퓨터로 보고서** 내보내기에서 보고서 **생성을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0c36d-140">In the details pane, under **Export report to a computer**, click **Generate report**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0c36d-141">검색 결과 7 일 보다 오래 된 경우 검색 결과 업데이트 하 라는 메시지가 표시.</span><span class="sxs-lookup"><span data-stu-id="0c36d-141">If the results for a search are older than 7 days, you are prompted to update the search results.</span></span> <span data-ttu-id="0c36d-142">이 경우 내보내기 취소,  선택한 검색에 대한 세부 정보 창에서 검색 결과 업데이트를 클릭한 다음 결과가 업데이트된 후 보고서 내보내기 다시 시작을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-142">If this happens, cancel the export, click **Update search results** in the details pane for the selected search, and then start the report export again after the results are updated.</span></span> 
  
6. <span data-ttu-id="0c36d-143">보고서 **내보내기 페이지의** **검색에서** 다음 항목 포함에서 다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-143">On the **Export a report** page, under **Include these items from the search**, choose one of the following options:</span></span>
    
    - <span data-ttu-id="0c36d-144">인덱싱된 항목만 내보내기</span><span class="sxs-lookup"><span data-stu-id="0c36d-144">Export only indexed items</span></span>
    
    - <span data-ttu-id="0c36d-145">인덱싱 및 인덱싱되지 않은 항목 내보내기</span><span class="sxs-lookup"><span data-stu-id="0c36d-145">Export indexed and unindexed items</span></span>
    
    - <span data-ttu-id="0c36d-146">인덱싱되지 않은 항목만 내보내기</span><span class="sxs-lookup"><span data-stu-id="0c36d-146">Export only unindexed items</span></span>
    
    <span data-ttu-id="0c36d-147">인덱싱되지 않은 항목에 대한 자세한 내용은 콘텐츠 검색에서 [부분적으로 인덱싱된 항목을 참조하세요.](partially-indexed-items-in-content-search.md)</span><span class="sxs-lookup"><span data-stu-id="0c36d-147">For more information about unindexed items, see [Partially indexed items in Content Search](partially-indexed-items-in-content-search.md).</span></span>
    
7. <span data-ttu-id="0c36d-148">모든 버전의 문서에 대한 검색 SharePoint 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-148">Choose to include search statistics for all versions of SharePoint documents.</span></span> <span data-ttu-id="0c36d-149">이 옵션은 검색의 콘텐츠 원본에 사이트 또는 사이트가 포함된 SharePoint 비즈니스용 OneDrive 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-149">This option appears only if the content sources of the search include SharePoint or OneDrive for Business sites.</span></span>
    
8. <span data-ttu-id="0c36d-150">보고서 **생성 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0c36d-150">Click **Generate report**.</span></span>
    
    <span data-ttu-id="0c36d-151">검색 결과 보고서는 다운로드할 준비가 되어 있습니다. 즉, 보고서 문서가 Microsoft 클라우드의 Azure Storage 영역으로 업로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-151">The search results report is prepared for downloading, which means the report documents will be uploaded to the Azure Storage area in the Microsoft cloud.</span></span> <span data-ttu-id="0c36d-152">보고서를 다운로드할 준비가 되면  보고서 다운로드 링크가 세부 정보 창의 컴퓨터로 보고서 내보내기 아래에 표시됩니다. </span><span class="sxs-lookup"><span data-stu-id="0c36d-152">When the report is ready for download, the **Download report** link is displayed under **Export report to a computer** in the details pane.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="0c36d-153">eDiscovery 사례와 연결된 콘텐츠 검색에 대한 보고서를 내보낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-153">You can also export a report for a Content Search that's associated with an eDiscovery case.</span></span> <span data-ttu-id="0c36d-154">이렇게하려면 **eDiscovery** \> **eDiscovery로** 이동하여 사례를 선택하고  편집 편집 ![ 아이콘을 ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-154">To do this, go to **eDiscovery** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span> <span data-ttu-id="0c36d-155">검색 **페이지에서** 검색을 선택한 다음 검색  결과 내보내기 내보내기 ![ 아이콘 보고서 ](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **내보내기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0c36d-155">On the **Searches** page, select a search, and then click **Export** ![Export search results icon](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **Export a report**.</span></span> 
  
## <a name="step-2-download-the-report"></a><span data-ttu-id="0c36d-156">2단계: 보고서 다운로드</span><span class="sxs-lookup"><span data-stu-id="0c36d-156">Step 2: Download the report</span></span>

<span data-ttu-id="0c36d-157">다음 단계는 보고서 영역의 보고서를 로컬 Azure Storage 다운로드하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-157">The next step is to download the report from the Azure Storage area to your local computer.</span></span>
  
1. <span data-ttu-id="0c36d-158">보고서를 생성한 검색에 대한 세부 정보 창의 **컴퓨터로** 보고서 내보내기 아래에서 보고서 **다운로드를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0c36d-158">In the details pane for the search that you generated the report for, under **Export report to a computer**, click **Download report**.</span></span>
    
    <span data-ttu-id="0c36d-159">보고서 **다운로드** 페이지가 표시되고 컴퓨터에 다운로드된 보고서에 대한 다음 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-159">The **Download report** page is displayed and contains the following information about the report that's downloaded to your computer.</span></span> 
    
    - <span data-ttu-id="0c36d-160">다운로드될 항목의 수</span><span class="sxs-lookup"><span data-stu-id="0c36d-160">The number of items that will be downloaded.</span></span>
    
    - <span data-ttu-id="0c36d-161">다운로드될 항목의 예상 총 크기</span><span class="sxs-lookup"><span data-stu-id="0c36d-161">The estimated total size of the items that will be downloaded.</span></span>
    
    - <span data-ttu-id="0c36d-162">인덱싱 여부 또는 인덱싱되지 않은 내보낼지 여부</span><span class="sxs-lookup"><span data-stu-id="0c36d-162">Whether indexed or unindexed will be exported.</span></span> <span data-ttu-id="0c36d-163">인덱싱되지 않은 항목은 인식된 형식이거나 암호화되거나 다른 이유로 인덱싱되지 않은 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-163">Unindexed items are items that have a recognized format, are encrypted, or weren't indexed for other reasons.</span></span>
    
    - <span data-ttu-id="0c36d-164">문서의 SharePoint 다운로드할지 여부</span><span class="sxs-lookup"><span data-stu-id="0c36d-164">Whether versions of SharePoint documents will be downloaded.</span></span>
    
    - <span data-ttu-id="0c36d-165">보고서 내보내기 프로세스의 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-165">The status of the report export process.</span></span> <span data-ttu-id="0c36d-166">보고서 준비가 완료되지 않은 경우에도 보고서 다운로드를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-166">You can start downloading the report even if the preparation of the report isn't complete.</span></span>
    
2. <span data-ttu-id="0c36d-167">**내보내기 키** 에서 **클립보드로 복사** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-167">Under **Export key**, click **Copy to clipboard**.</span></span> <span data-ttu-id="0c36d-168">5단계에서 이 키를 사용하여 보고서를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-168">You use this key in step 5 to download the report.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="0c36d-169">누구나 eDiscovery 내보내기 도구를 설치하고 시작한 다음 이 키를 사용하여 검색 보고서를 다운로드할 수 있기 때문에 암호 또는 기타 보안 관련 정보를 보호하는 경우처럼 주의하여 이 키를 보호해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-169">Because anyone can install and start the eDiscovery Export tool, and then use this key to download the search report, be sure to take precautions to protect this key just like you would protect passwords or other security-related information.</span></span> 
  
3. <span data-ttu-id="0c36d-170">보고서 **다운로드를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0c36d-170">Click **Download report**.</span></span>
    
4. <span data-ttu-id="0c36d-171">**eDiscovery** 내보내기 도구를 설치하라는 메시지가 표시될 경우 설치를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0c36d-171">If you're prompted to install the **eDiscovery Export Tool**, click **Install**.</span></span>
    
5. <span data-ttu-id="0c36d-172">**eDiscovery 내보내기 도구** 에서 5단계에서 복사한 내보내기 키를 해당 상자에 붙여 넣습니다. </span><span class="sxs-lookup"><span data-stu-id="0c36d-172">In the **eDiscovery Export Tool**, paste the export key that you copied in step 2 in the appropriate box.</span></span>
    
6. <span data-ttu-id="0c36d-173">**찾아보기를** 클릭하여 보고서를 다운로드할 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-173">Click **Browse** to specify the location where you want to download the report.</span></span> 
    
7. <span data-ttu-id="0c36d-174">**시작** 을 클릭하여 컴퓨터에 검색 결과를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-174">Click **Start** to download the search results to your computer.</span></span> 
    
    <span data-ttu-id="0c36d-175">**eDiscovery 내보내기 도구** 는 다운로드할 남은 항목의 예상 개수(크기)를 포함하여 내보내기 프로세스에 대한 상태 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-175">The **eDiscovery Export Tool** displays status information about the export process, including an estimate of the number (and size) of the remaining items to be downloaded.</span></span> <span data-ttu-id="0c36d-176">내보내기 프로세스가 완료되면 다운로드된 위치에 있는 파일에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-176">When the export process is complete, you can access the files in the location where they were downloaded.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="0c36d-177">eDiscovery 사례와 연결된 콘텐츠 검색에 대한 보고서를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-177">You can download the report for a Content Search that's associated with an eDiscovery case.</span></span> <span data-ttu-id="0c36d-178">이렇게하려면 **eDiscovery** \> **eDiscovery로** 이동하여 사례를 선택하고  편집 편집 ![ 아이콘을 ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-178">To do this, go to **eDiscovery** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span> <span data-ttu-id="0c36d-179">내보내기 **페이지에서** 보고서 내보내기 를 선택한  다음 세부 정보 창에서 보고서 다운로드를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-179">On the **Exports** page, select an report export, and then click **Download report** in the details pane.</span></span> 
  
## <a name="whats-included-in-the-report"></a><span data-ttu-id="0c36d-180">보고서에 포함된 것</span><span class="sxs-lookup"><span data-stu-id="0c36d-180">What's included in the report</span></span>

<span data-ttu-id="0c36d-181">콘텐츠 검색 결과에 대한 보고서를 생성하고 내보내면 다음 문서가 다운로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-181">When you generate and export a report about the results of a Content Search, the following documents are downloaded:</span></span>
  
- <span data-ttu-id="0c36d-182">**내보내기 요약:** 내보내기 Excel 포함된 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-182">**Export Summary:** An Excel document that contains a summary of the export.</span></span> <span data-ttu-id="0c36d-183">여기에는 검색된 콘텐츠 원본 수, 각 콘텐츠 위치의 검색 결과 수, 예상 항목 수, 내보낼 실제 항목 수, 내보낼 항목의 예상 및 실제 크기 등의 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-183">This includes information such as the number of content sources that were searched, the number of search results from each content location, the estimated number of items, the actual number of items that would be exported, and the estimated and actual size of items that would be exported.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="0c36d-184">보고서를 내보낼 때 인덱서되지 않은 항목을 포함하면 예상 검색 결과의 총 수와 내보내기 요약 보고서에 나열된 다운로드된 총 검색 결과 수에 인덱서되지 않은 항목 수가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-184">If you include unindexed items when exporting the report, the number of unindexed items are included in the total number of estimated search results and in the total number of downloaded search results (if you were to export the search results) that are listed in the Export Summary report.</span></span> <span data-ttu-id="0c36d-185">즉, 다운로드되는 총 항목 수는 예상 결과의 총 수와 인덱서되지 않은 총 항목 수와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-185">In other words, the total number of items that would be downloaded is equal to the total number of estimated results and the total number of unindexed items.</span></span> 
  
- <span data-ttu-id="0c36d-186">**매니페스트:** 검색 결과에 포함된 각 항목에 대한 정보가 포함된 매니페스트 파일(XML 형식)입니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-186">**Manifest:** A manifest file (in XML format) that contains information about each item included in the search results.</span></span> 
    
- <span data-ttu-id="0c36d-187">**결과:** 검색 Excel 내보낼 인덱싱된 각 항목에 대한 정보가 포함된 행이 포함된 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-187">**Results:** An Excel document that contains a row with information about each indexed item that would be exported with the search results.</span></span> <span data-ttu-id="0c36d-188">전자 메일의 경우 결과 로그에는 다음을 비롯한 각 메시지에 대한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-188">For email, the result log contains information about each message, including:</span></span> 
    
  - <span data-ttu-id="0c36d-189">원본 사서함에 있는 메시지의 위치 (포함 여부는 주 메시지는 보관 사서함 또는).</span><span class="sxs-lookup"><span data-stu-id="0c36d-189">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
    
  - <span data-ttu-id="0c36d-190">메시지가 전송된 날짜</span><span class="sxs-lookup"><span data-stu-id="0c36d-190">The date the message was sent or received.</span></span>
    
  - <span data-ttu-id="0c36d-191">메시지의 제목 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-191">The Subject line from the message.</span></span>
    
  - <span data-ttu-id="0c36d-192">보낸 사람 및 메시지 받는 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-192">The sender and recipients of the message.</span></span>
    
    <span data-ttu-id="0c36d-193">사이트 및 SharePoint 비즈니스용 OneDrive 문서의 경우 결과 로그에는 다음을 비롯한 각 문서에 대한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-193">For documents from SharePoint and OneDrive for Business sites, the Results log contains information about each document, including:</span></span>
    
  - <span data-ttu-id="0c36d-194">문서에 대 한 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-194">The URL for the document.</span></span>
    
  - <span data-ttu-id="0c36d-195">문서가 있는 사이트 모음의 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-195">The URL for the site collection where the document is located.</span></span>
    
  - <span data-ttu-id="0c36d-196">문서를 마지막으로 수정한 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-196">The date that the document was last modified.</span></span>
    
  - <span data-ttu-id="0c36d-197">이름 (에 있는 제목 열 결과 로그에서) 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-197">The name of the document (which is located in the Subject column in the result log).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0c36d-198">결과 보고서의 행  수는 전체 검색 결과 수에서 인덱서되지 않은 항목 보고서에 나열된 총 항목 수를 운운하는 개수와 **같아야** 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-198">The number of rows in the **Results** report should be equal to the total number of search results minus the total number of items listed in the **Unindexed Items** report.</span></span> 
  
- <span data-ttu-id="0c36d-199">**인덱서되지 않은 항목:** 검색 Excel 인덱서되지 않은 항목에 대한 정보가 포함된 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-199">**Unindexed Items:** An Excel document that contains information about any unindexed items included in the search results.</span></span> <span data-ttu-id="0c36d-200">검색 결과 보고서를 생성할 때 인덱서되지 않은 항목을 포함하지 않는 경우 이 보고서는 계속 다운로드되지만 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c36d-200">If you don't include unindexed items when you generate the search results report, this report will still be downloaded, but will be empty.</span></span>
