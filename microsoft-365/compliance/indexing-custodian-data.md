---
title: 보유자 데이터의 고급 인덱싱
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
description: 고급 eDiscovery 사례에 custodian을 추가 하면 부분적으로 인덱싱된 것으로 간주 되는 Office 365의 콘텐츠가 완벽 하 게 검색 가능 하도록 다시 처리 됩니다.
ms.openlocfilehash: 3c1bead5f853a39410a6a018f170ee637dfcf84e
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42072895"
---
# <a name="advanced-indexing-of-custodian-data"></a><span data-ttu-id="9f357-103">보유자 데이터의 고급 인덱싱</span><span class="sxs-lookup"><span data-stu-id="9f357-103">Advanced indexing of custodian data</span></span>

<span data-ttu-id="9f357-104">고급 eDiscovery 사례에 custodian을 추가 하면 부분적으로 인덱싱된 것으로 간주 되는 Office 365의 콘텐츠가 완벽 하 게 검색 가능 하도록 다시 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f357-104">When a custodian is added to an Advanced eDiscovery case, any content in Office 365 that was deemed as partially indexed is re-processed to make it fully searchable.</span></span>  <span data-ttu-id="9f357-105">이 프로세스를 *고급 인덱싱*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f357-105">This process is called *Advanced indexing*.</span></span> <span data-ttu-id="9f357-106">이미지의 존재 여부, 지원 되지 않는 파일 형식 또는 파일 크기 제한에 도달 하는 경우에는 여러 가지 이유로 인해 콘텐츠를 부분적으로 인덱싱할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f357-106">Content can be partially indexed for a number of reasons including the existence of images, unsupported file types or when indexing file size limits are encountered.</span></span>

<span data-ttu-id="9f357-107">Office 365 및 부분적으로 인덱싱된 항목의 처리 지원에 대 한 자세한 내용은 다음을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9f357-107">To learn more about processing support in Office 365 and partially indexed items, see:</span></span>

- [<span data-ttu-id="9f357-108">고급 eDiscovery에서 지원 되는 파일 형식</span><span class="sxs-lookup"><span data-stu-id="9f357-108">Supported file types in Advanced eDiscovery</span></span>](supported-filetypes-ediscovery20.md)

- [<span data-ttu-id="9f357-109">Office 365의 콘텐츠 검색에서 부분적으로 인덱싱된 항목</span><span class="sxs-lookup"><span data-stu-id="9f357-109">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)

- [<span data-ttu-id="9f357-110">Exchange 검색에서 인덱싱하는 파일 형식</span><span class="sxs-lookup"><span data-stu-id="9f357-110">File formats indexed by Exchange Search</span></span>](https://docs.microsoft.com/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [<span data-ttu-id="9f357-111">SharePoint Server의 크롤링되는 기본 파일 이름 확장명 및 구문 분석되는 파일 형식</span><span class="sxs-lookup"><span data-stu-id="9f357-111">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="9f357-112">고급 인덱싱 결과 보기</span><span class="sxs-lookup"><span data-stu-id="9f357-112">Viewing Advanced indexing results</span></span>

<span data-ttu-id="9f357-113">고급 인덱싱 프로세스가 완료 되 면 다시 처리할 때의 효과를 이해 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f357-113">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of re-processing.</span></span>  <span data-ttu-id="9f357-114">사례에 대 한 **처리** 탭의 고급 인덱싱 결과 보기에서 그래프에는 *하이브리드 인덱스*에 추가 된 항목 수가 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f357-114">In the Advanced indexing results view on the **Processing** tab for a case, the graph lists the number of items added to the *hybrid index*.</span></span>  <span data-ttu-id="9f357-115">하이브리드 인덱스는 고급 eDiscovery가 다시 처리 된 콘텐츠를 저장 하는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="9f357-115">The hybrid index is where Advanced eDiscovery stores the re-processed content.</span></span>

<span data-ttu-id="9f357-116">이 보기에는 수정 해야 하는 항목 수와 파일 형식별로 또 다른 오류 그래프가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f357-116">This view  also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="9f357-117">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9f357-117">For more information, see:</span></span>

- [<span data-ttu-id="9f357-118">데이터를 처리할 때 오류 수정</span><span class="sxs-lookup"><span data-stu-id="9f357-118">Error remediation when processing data</span></span>](error-remediation.md)

- [<span data-ttu-id="9f357-119">단일 항목 오류 수정</span><span class="sxs-lookup"><span data-stu-id="9f357-119">Single item error remediation</span></span>](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a><span data-ttu-id="9f357-120">Custodians에 대 한 고급 인덱스 업데이트</span><span class="sxs-lookup"><span data-stu-id="9f357-120">Updating the Advanced index for custodians</span></span>

<span data-ttu-id="9f357-121">고급 eDiscovery 사례에 custodian을 추가 하면 부분적으로 인덱싱된 항목이 모두 다시 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f357-121">When a custodian is added to an Advanced eDiscovery case, all partially indexed items are re-processed.</span></span> <span data-ttu-id="9f357-122">그러나 시간 경과에 따라 보다 부분적으로 인덱싱된 항목이 사용자의 사서함 또는 OneDrive 계정에 추가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f357-122">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="9f357-123">필요한 경우 특정 custodian에 대 한 인덱스를 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f357-123">If necessary, you can update the index for specific custodian.</span></span> <span data-ttu-id="9f357-124">자세한 내용은 [Advanced eDiscovery 사례에서 Custodians 관리](manage-new-custodians.md#re-index-custodian-data)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9f357-124">For more information, see [Manage custodians in an Advanced eDiscovery case](manage-new-custodians.md#re-index-custodian-data).</span></span> <span data-ttu-id="9f357-125">**처리** 탭에서 **업데이트 인덱스** 를 클릭 하 여 모든 custodians에 대 한 인덱스를 업데이트할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f357-125">You can also update the index for all custodians in a case by clicking the **Update index** on the **Processing** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="9f357-126">Custodian 인덱스를 업데이트 하는 과정은 장기 실행 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="9f357-126">Updating custodian indexes is a long running process.</span></span> <span data-ttu-id="9f357-127">인덱스를 하루에 두 번 이상 업데이트 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9f357-127">It's recommended that you don't update indexes more than once a day in a case.</span></span>
