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
description: 고급 eDiscovery 사례에 custodian을 추가하면 부분적으로 인덱싱된 것으로 확인된 모든 콘텐츠는 완전히 검색할 수 있도록 다시 처리됩니다.
ms.openlocfilehash: 904c8fe626ce8ece8f4b48bd5504e4011e9f4fb2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911212"
---
# <a name="advanced-indexing-of-custodian-data"></a><span data-ttu-id="0068f-103">보유자 데이터의 고급 인덱싱</span><span class="sxs-lookup"><span data-stu-id="0068f-103">Advanced indexing of custodian data</span></span>

<span data-ttu-id="0068f-104">고급 eDiscovery 사례에 custodian을 추가하면 부분적으로 인덱싱된 것으로 확인된 모든 콘텐츠는 완전히 검색할 수 있도록 다시 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="0068f-104">When a custodian is added to an Advanced eDiscovery case, any content that was deemed as partially indexed is reprocessed to make it fully searchable.</span></span>  <span data-ttu-id="0068f-105">이 프로세스를 고급 *인덱싱이라고 합니다.*</span><span class="sxs-lookup"><span data-stu-id="0068f-105">This process is called *Advanced indexing*.</span></span> <span data-ttu-id="0068f-106">이미지가 존재하거나, 지원되지 않는 파일 형식이나 인덱싱 파일 크기 제한이 발생하는 경우를 포함하여 여러 가지 이유로 콘텐츠를 부분적으로 인덱싱할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0068f-106">Content can be partially indexed for a number of reasons including the existence of images, unsupported file types or when indexing file size limits are encountered.</span></span>

<span data-ttu-id="0068f-107">지원 및 부분적으로 인덱싱된 항목 처리에 대한 자세한 내용은 다음을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="0068f-107">To learn more about processing support and partially indexed items, see:</span></span>

- [<span data-ttu-id="0068f-108">Advanced eDiscovery에서 지원되는 파일 형식</span><span class="sxs-lookup"><span data-stu-id="0068f-108">Supported file types in Advanced eDiscovery</span></span>](supported-filetypes-ediscovery20.md)

- [<span data-ttu-id="0068f-109">Office 365의 콘텐츠 검색에서 부분적으로 인덱싱된 항목</span><span class="sxs-lookup"><span data-stu-id="0068f-109">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)

- [<span data-ttu-id="0068f-110">Exchange 검색에서 인덱싱하는 파일 형식</span><span class="sxs-lookup"><span data-stu-id="0068f-110">File formats indexed by Exchange Search</span></span>](/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [<span data-ttu-id="0068f-111">SharePoint Server의 크롤링되는 기본 파일 이름 확장명 및 구문 분석되는 파일 형식</span><span class="sxs-lookup"><span data-stu-id="0068f-111">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="0068f-112">고급 인덱싱 결과 보기</span><span class="sxs-lookup"><span data-stu-id="0068f-112">Viewing Advanced indexing results</span></span>

<span data-ttu-id="0068f-113">고급 인덱싱 프로세스가 완료되면 다시 처리의 효율성을 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0068f-113">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of reprocessing.</span></span>  <span data-ttu-id="0068f-114">사례에 대한 처리 탭의  고급 인덱싱 결과 보기에서 하이브리드 인덱스에 추가된 항목 수를 *그래프에 나열합니다.*</span><span class="sxs-lookup"><span data-stu-id="0068f-114">In the Advanced indexing results view on the **Processing** tab for a case, the graph lists the number of items added to the *hybrid index*.</span></span>  <span data-ttu-id="0068f-115">하이브리드 인덱스는 Advanced eDiscovery에서 다시 처리된 콘텐츠를 저장하는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="0068f-115">The hybrid index is where Advanced eDiscovery stores the reprocessed content.</span></span>

<span data-ttu-id="0068f-116">이 보기에는 수정이 필요한 항목 수와 파일 형식별로 다른 오류 그래프도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0068f-116">This view  also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="0068f-117">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0068f-117">For more information, see:</span></span>

- [<span data-ttu-id="0068f-118">데이터를 처리할 때 오류 수정</span><span class="sxs-lookup"><span data-stu-id="0068f-118">Error remediation when processing data</span></span>](error-remediation-when-processing-data-in-advanced-ediscovery.md)

- [<span data-ttu-id="0068f-119">단일 항목 오류 수정</span><span class="sxs-lookup"><span data-stu-id="0068f-119">Single item error remediation</span></span>](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a><span data-ttu-id="0068f-120">수급자에 대한 고급 인덱스 업데이트</span><span class="sxs-lookup"><span data-stu-id="0068f-120">Updating the Advanced index for custodians</span></span>

<span data-ttu-id="0068f-121">고급 eDiscovery 사례에 custodian을 추가하면 부분적으로 인덱싱된 모든 항목이 다시 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="0068f-121">When a custodian is added to an Advanced eDiscovery case, all partially indexed items are reprocessed.</span></span> <span data-ttu-id="0068f-122">그러나 시간이 지나면 부분적으로 인덱싱된 항목이 사용자의 사서함 또는 OneDrive 계정에 추가될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0068f-122">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="0068f-123">필요한 경우 특정관리자에 대한 인덱스를 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0068f-123">If necessary, you can update the index for specific custodian.</span></span> <span data-ttu-id="0068f-124">자세한 내용은 [Manage custodians in an Advanced eDiscovery case를 참조하세요.](manage-new-custodians.md#re-index-custodian-data)</span><span class="sxs-lookup"><span data-stu-id="0068f-124">For more information, see [Manage custodians in an Advanced eDiscovery case](manage-new-custodians.md#re-index-custodian-data).</span></span> <span data-ttu-id="0068f-125">처리 탭에서 업데이트 인덱스를 클릭하여 사례에 있는 모든 정보주에 대한 인덱스를 업데이트할 **수** 있습니다. </span><span class="sxs-lookup"><span data-stu-id="0068f-125">You can also update the index for all custodians in a case by clicking the **Update index** on the **Processing** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="0068f-126">양도인 인덱스를 업데이트하는 것은 긴 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="0068f-126">Updating custodian indexes is a long running process.</span></span> <span data-ttu-id="0068f-127">경우에 한해 하루 두 번 이상 인덱스를 업데이트하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0068f-127">It's recommended that you don't update indexes more than once a day in a case.</span></span>