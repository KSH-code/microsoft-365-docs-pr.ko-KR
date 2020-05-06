---
title: 조사를 위한 데이터의 고급 인덱싱
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 고급 인덱싱을 사용 하 여 검색에서 조사 하려는 모든 데이터를 캡처 하는지 확인 하는 방법을 알아봅니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: dc7d73c233aa48b88e9dce32fad613ccc5e19333
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035064"
---
# <a name="advanced-indexing-of-data-for-an-investigation"></a><span data-ttu-id="65a62-103">조사를 위한 데이터의 고급 인덱싱</span><span class="sxs-lookup"><span data-stu-id="65a62-103">Advanced indexing of data for an investigation</span></span>

<span data-ttu-id="65a62-104">라이브 시스템의 콘텐츠는 이미지의 존재, 지원 되지 않는 파일 형식 또는 파일 크기 제한에 도달 하는 경우를 비롯 하 여 몇 가지 이유로 인해 부분적으로 인덱싱될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65a62-104">Content in the live system can be partially indexed for a number of reasons including the existence of images, unsupported file types or when indexing file size limits are encountered.</span></span> <span data-ttu-id="65a62-105">높은 위험 수준 데이터 분산을 처리 하는 경우 검색에서 조사 하려는 모든 데이터를 캡처 했는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65a62-105">When you are dealing with high risk data spill, you want to make sure that your search captured all data that you want to investigate.</span></span> <span data-ttu-id="65a62-106">관심 있는 사용자가 데이터 조사에 추가 되 면 부분적으로 인덱싱된 콘텐츠가 완벽 하 게 검색 가능 하도록 다시 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="65a62-106">When a person of interest is added to a Data investigation, any content that was deemed as partially indexed is re-processed to make it fully searchable.</span></span> <span data-ttu-id="65a62-107">이 프로세스를 *고급 인덱싱*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="65a62-107">This process is called *Advanced indexing*.</span></span> 

<span data-ttu-id="65a62-108">처리 지원 및 부분적으로 인덱싱된 항목에 대 한 자세한 내용은 다음 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="65a62-108">To learn more about processing support and partially indexed items, see:</span></span>

- [<span data-ttu-id="65a62-109">데이터 조사에서 지원 되는 파일 형식</span><span class="sxs-lookup"><span data-stu-id="65a62-109">Supported file types in Data Investigations</span></span>](supported-filetypes-datainvestigations.md)

- [<span data-ttu-id="65a62-110">Office 365의 콘텐츠 검색에서 부분적으로 인덱싱된 항목</span><span class="sxs-lookup"><span data-stu-id="65a62-110">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)

- [<span data-ttu-id="65a62-111">Exchange 검색에서 인덱싱하는 파일 형식</span><span class="sxs-lookup"><span data-stu-id="65a62-111">File formats indexed by Exchange Search</span></span>](https://docs.microsoft.com/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [<span data-ttu-id="65a62-112">SharePoint Server의 크롤링되는 기본 파일 이름 확장명 및 구문 분석되는 파일 형식</span><span class="sxs-lookup"><span data-stu-id="65a62-112">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="65a62-113">고급 인덱싱 결과 보기</span><span class="sxs-lookup"><span data-stu-id="65a62-113">Viewing Advanced indexing results</span></span>

<span data-ttu-id="65a62-114">고급 인덱싱 프로세스가 완료 되 면 다시 처리할 때의 효과를 이해 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65a62-114">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of re-processing.</span></span>  <span data-ttu-id="65a62-115">관심 있는 사용자 보기에서 그래프에는 *하이브리드 인덱스*에 추가 된 모든 항목이 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="65a62-115">In the People of interest indexing view, the graph lists all items added to the *hybrid index*.</span></span>  <span data-ttu-id="65a62-116">하이브리드 인덱스는 데이터 조사 (미리 보기)에 다시 처리 된 콘텐츠가 저장 되는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="65a62-116">The hybrid index is where Data Investigations (Preview) stores the re-processed content.</span></span>

<span data-ttu-id="65a62-117">또한 그래프에는 수정이 필요한 항목 수와 파일 형식별로 다른 오류 그래프가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65a62-117">The graph also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="65a62-118">자세한 내용은 [데이터를 처리할 때 오류 수정을](error-remediation.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="65a62-118">For more information, see [Error remediation when processing data](error-remediation.md).</span></span>

## <a name="updating-advanced-indexes-for-people-of-interest"></a><span data-ttu-id="65a62-119">관심 있는 사용자를 위해 고급 인덱스 업데이트</span><span class="sxs-lookup"><span data-stu-id="65a62-119">Updating Advanced indexes for people of interest</span></span>

<span data-ttu-id="65a62-120">관심 있는 사용자가 데이터 조사에 추가 되 면 부분적으로 인덱싱된 모든 항목이 다시 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="65a62-120">When a person of interest is added to a data investigation, all partially indexed items are re-processed.</span></span> <span data-ttu-id="65a62-121">그러나 시간 경과에 따라 보다 부분적으로 인덱싱된 항목이 사용자의 사서함 또는 OneDrive 계정에 추가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65a62-121">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="65a62-122">필요한 경우 인덱스를 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65a62-122">When needed, you can update the indexes.</span></span>

> [!NOTE]
> <span data-ttu-id="65a62-123">관심 있는 인덱스 사용자를 업데이트 하는 것은 장기 실행 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="65a62-123">Updating people of interest indexes is a long running process.</span></span> <span data-ttu-id="65a62-124">조사에서 하루에 한 번 이상 인덱스를 업데이트 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="65a62-124">It's recommended that you don't update indexes more than once per day in an investigation.</span></span>
