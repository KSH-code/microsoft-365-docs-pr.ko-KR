---
title: Core eDiscovery 사례에서 콘텐츠 내보내기 및 다운로드
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 핵심 eDiscovery 사례에서 콘텐츠를 내보내고 다운로드하는 방법을 Microsoft 365.
ms.openlocfilehash: 8eb54e23369ef682e8aa1ebf7e681eb34444f1cd
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2021
ms.locfileid: "52310845"
---
# <a name="export-content-from-a-core-ediscovery-case"></a><span data-ttu-id="1c981-103">Core eDiscovery 케이스에서 콘텐츠 내보내기</span><span class="sxs-lookup"><span data-stu-id="1c981-103">Export content from a Core eDiscovery case</span></span>

<span data-ttu-id="1c981-104">Core eDiscovery 사례와 연결된 검색이 성공적으로 실행된 후 검색 결과를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c981-104">After a search associated with a Core eDiscovery case is successfully run, you can export the search results.</span></span> <span data-ttu-id="1c981-105">검색 결과를 내보내면 사서함 항목이 PST 파일 또는 개별 메시지로 다운로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c981-105">When you export search results, mailbox items are downloaded in PST files or as individual messages.</span></span> <span data-ttu-id="1c981-106">사이트 및 SharePoint 비즈니스용 OneDrive 내보낼 때 기본 Office 문서 및 기타 문서의 복사본을 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c981-106">When you export content from SharePoint and OneDrive for Business sites, copies of native Office documents and other documents are exported.</span></span> <span data-ttu-id="1c981-107">내보내는 Results.csv 대한 정보가 포함된 파일과 모든 검색 결과에 대한 정보가 포함된 매니페스트 파일(XML 형식)도 내보내기됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c981-107">A Results.csv file that contains information about every item that's exported and a manifest file (in XML format) that contains information about every search result is also exported.</span></span>
  
## <a name="export-search-results"></a><span data-ttu-id="1c981-108">검색 결과 내보내기</span><span class="sxs-lookup"><span data-stu-id="1c981-108">Export search results</span></span>

1. <span data-ttu-id="1c981-109">으로 이동한 후 적절한 eDiscovery 권한이 할당된 사용자 계정의 자격 증명을 [https://compliance.microsoft.com](https://compliance.microsoft.com) 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="1c981-109">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and sign in using the credentials for user account that has been assigned the appropriate eDiscovery permissions.</span></span>

2. <span data-ttu-id="1c981-110">Microsoft 365 규정 준수 센터의 왼쪽 탐색 창에서 모두 표시를 클릭한 다음 **eDiscovery**> 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1c981-110">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Core**.</span></span>

3. <span data-ttu-id="1c981-111">Core **eDiscovery** 페이지에서 보류를 만들 사례의 이름을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1c981-111">On the **Core eDiscovery** page, click the name of the case that you want to create the hold in.</span></span>

4. <span data-ttu-id="1c981-112">사례에 **대한 홈** 페이지에서 검색 **탭을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1c981-112">On the **Home** page for the case, click the **Searches** tab.</span></span>

5. <span data-ttu-id="1c981-113">**플라이아웃** 페이지의 아래쪽에 있는 작업 메뉴에서 결과 **내보내기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="1c981-113">On the **Actions** menu at the bottom of the flyout page, click **Export results**.</span></span>

   ![작업 메뉴에서 결과 내보내기 옵션](../media/ActionMenuExportResults.png)

   <span data-ttu-id="1c981-115">Core eDiscovery 사례와 연결된 검색 결과를 내보내는 워크플로는 콘텐츠 검색 페이지에서 검색 결과를 내보내는 워크플로와 **동일합니다.**</span><span class="sxs-lookup"><span data-stu-id="1c981-115">The workflow to export the results of a search associated with a Core eDiscovery case is that same as exporting the search results for a search on the **Content search** page.</span></span> <span data-ttu-id="1c981-116">단계별 지침은 콘텐츠 검색 결과 [내보내기 를 참조하세요.](export-search-results.md)</span><span class="sxs-lookup"><span data-stu-id="1c981-116">For step-by-step instructions, see [Export content search results](export-search-results.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="1c981-117">검색 결과를 내보낼 때 동일한 메시지의 여러 인스턴스가 검색된 사서함에 있을 수 있는 경우에도 전자 메일 메시지의 복사본 하나만 내보낼 수 있도록 중복 제거를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c981-117">When you export search results, you have the option to enable de-duplication so that only one copy of an email message is exported even though multiple instances of the same message might have been found in the mailboxes that were searched.</span></span> <span data-ttu-id="1c981-118">중복 제거 및 중복 항목을 식별하는 방법에 대한 자세한 내용은 [eDiscovery](de-duplication-in-ediscovery-search-results.md)검색 결과에서 중복 제거를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c981-118">For more information about de-duplication and how duplicate items are identified, see [De-duplication in eDiscovery search results](de-duplication-in-ediscovery-search-results.md).</span></span>

   <span data-ttu-id="1c981-119">내보내기 시작하면 검색 결과가 다운로드할 수 있습니다. 즉, 검색 결과가 Microsoft 클라우드의 Microsoft 제공 Azure Storage 위치로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c981-119">After you start the export, the search results are prepared for downloading, which means they are transferred to a Microsoft-provided Azure Storage location in the Microsoft cloud.</span></span>
  
6. <span data-ttu-id="1c981-120">이 경우 **내보내기** 탭을 클릭하여 내보내기 작업 목록을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="1c981-120">Click the **Exports** tab in the case to display the list of export jobs.</span></span>
  
   ![Core eDiscovery 사례의 내보내기 탭에서 작업 내보내기](../media/CoreeDiscoveryExport.png)

   <span data-ttu-id="1c981-122">새로 고침을 **클릭하여** 만든 내보내기 작업이 표시될 수 있도록 내보내기 작업 목록을 업데이트해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c981-122">You may have to click **Refresh** to update the list of export jobs so that it shows the export job you created.</span></span> <span data-ttu-id="1c981-123">내보내기 작업의 이름은 검색 이름에  추가된 _Export 검색과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="1c981-123">Export jobs have the same name as the corresponding search with **_Export** appended to the search name.</span></span>

7. <span data-ttu-id="1c981-124">만든 내보내기 작업을 클릭하여 플라이아웃 페이지에 상태 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="1c981-124">Click the export job you created to display status information on the flyout page.</span></span> <span data-ttu-id="1c981-125">이 정보에는 이전 위치로 전송된 항목의 Azure Storage 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c981-125">This information includes the percentage of items that have been transferred to the Azure Storage location.</span></span>

8. <span data-ttu-id="1c981-126">모든 항목이 전송된 후  결과 다운로드를 클릭하여 검색 결과를 로컬 컴퓨터에 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="1c981-126">After all items have been transferred, click **Download results** to download the search results to your local computer.</span></span> <span data-ttu-id="1c981-127">검색 결과를 다운로드하는 자세한 내용은 콘텐츠 검색 결과 내보내기에서 [2단계를 참조하세요.](export-search-results.md#step-2-download-the-search-results)</span><span class="sxs-lookup"><span data-stu-id="1c981-127">For more information downloading search results, see Step 2 in [Export content search results](export-search-results.md#step-2-download-the-search-results)</span></span>

### <a name="more-information-about-exporting-searches-from-a-case"></a><span data-ttu-id="1c981-128">사례에서 검색 내보내기에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="1c981-128">More information about exporting searches from a case</span></span>

- <span data-ttu-id="1c981-129">검색 결과를 내보낼 때 포함된 파일 내보내기에 대한 자세한 내용은 콘텐츠 검색 보고서 [내보내기 를 참조하세요.](export-a-content-search-report.md#whats-included-in-the-report)</span><span class="sxs-lookup"><span data-stu-id="1c981-129">For more information about the export files that are included when you export search results, see [Export a Content search report](export-a-content-search-report.md#whats-included-in-the-report).</span></span>

- <span data-ttu-id="1c981-130">내보내기 작업을 다시 시작하는 경우 내보내기 작업을 만드는 검색의 쿼리에 대한 변경 내용은 검색된 검색 결과에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c981-130">If you restart the export, any changes to the queries of the searches that make up the export job won't affect the search results that are retrieved.</span></span> <span data-ttu-id="1c981-131">내보내기 작업을 다시 시작하면 내보내기 작업을 만들 때 실행된 동일한 결합된 검색 쿼리 작업이 다시 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c981-131">When you restart an export, the same combined search query job that was run when the export job was created will be run again.</span></span>

- <span data-ttu-id="1c981-132">또한 내보내기 기능을 다시 시작하면 해당 위치로 복사된 검색 Azure Storage 이전 결과를 덮어 덮어 매기게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c981-132">Also, if you restart an export, the search results that are copied to the Azure Storage location overwrites the previous results.</span></span> <span data-ttu-id="1c981-133">복사한 이전 결과는 다운로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1c981-133">The previous results that were copied won't be available to be downloaded.</span></span>
