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
description: Advanced eDiscovery 경우, 부분적으로 인덱싱된 것으로 확인된 모든 콘텐츠는 완전히 검색할 수 있도록 다시 처리됩니다.
ms.openlocfilehash: 34855eb168dd10fc500e2e57fe1d57ad81449452
ms.sourcegitcommit: 2fd60871975d61e60d4827b36cd689021fd2a4c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/15/2021
ms.locfileid: "53437979"
---
# <a name="advanced-indexing-of-custodian-data"></a><span data-ttu-id="a4528-103">보유자 데이터의 고급 인덱싱</span><span class="sxs-lookup"><span data-stu-id="a4528-103">Advanced indexing of custodian data</span></span>

<span data-ttu-id="a4528-104">Advanced eDiscovery 사례에 추가된 경우 부분적으로 인덱싱되거나 인덱싱 오류가 있는 모든 콘텐츠가 완전히 검색할 수 있도록 다시 인덱싱됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4528-104">When a custodian is added to an Advanced eDiscovery case, any content that was deemed as partially indexed or had indexing errors with is reindexed to make it fully searchable.</span></span>  <span data-ttu-id="a4528-105">이 다시 인덱싱 프로세스를 *고급 인덱싱이라고 합니다.*</span><span class="sxs-lookup"><span data-stu-id="a4528-105">This reindexing process is called *Advanced indexing*.</span></span> <span data-ttu-id="a4528-106">콘텐츠가 부분적으로 인덱싱되거나 인덱싱 오류가 발생하는 이유는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4528-106">There are a number of reasons that content is partially indexed or has indexing errors.</span></span> <span data-ttu-id="a4528-107">여기에는 이미지 파일 또는 파일의 이미지 존재, 지원되지 않는 파일 형식 또는 파일 크기 인덱싱 제한이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4528-107">This includes image files or the presence of images in a file, unsupported file types, or file sized indexing limits.</span></span> <span data-ttu-id="a4528-108">파일 SharePoint 고급 인덱싱은 부분적으로 인덱싱된 것으로 표시되거나 인덱싱 오류가 있는 항목에서만 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4528-108">For SharePoint files, Advanced indexing only runs on items are marked as partially indexed or that have indexing errors.</span></span> <span data-ttu-id="a4528-109">Exchange 첨부 파일이 있는 전자 메일 메시지는 부분적으로 인덱싱되거나 인덱싱 오류가 있는 것으로 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4528-109">In Exchange, email messages that have image attachments are not marked as partially indexed or with indexing errors.</span></span> <span data-ttu-id="a4528-110">즉, 이러한 파일은 고급 인덱싱 프로세스에서 다시 인덱싱되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4528-110">This means that those files will not be reindexed by the Advanced indexing process.</span></span>

<span data-ttu-id="a4528-111">지원 및 부분적으로 인덱싱된 항목 처리에 대한 자세한 내용은 다음을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="a4528-111">To learn more about processing support and partially indexed items, see:</span></span>

- [<span data-ttu-id="a4528-112">지원되는 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="a4528-112">Supported file types in Advanced eDiscovery</span></span>](supported-filetypes-ediscovery20.md)

- [<span data-ttu-id="a4528-113">Office 365의 콘텐츠 검색에서 부분적으로 인덱싱된 항목</span><span class="sxs-lookup"><span data-stu-id="a4528-113">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)

- [<span data-ttu-id="a4528-114">Exchange 검색에서 인덱싱하는 파일 형식</span><span class="sxs-lookup"><span data-stu-id="a4528-114">File formats indexed by Exchange Search</span></span>](/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [<span data-ttu-id="a4528-115">SharePoint Server의 크롤링되는 기본 파일 이름 확장명 및 구문 분석되는 파일 형식</span><span class="sxs-lookup"><span data-stu-id="a4528-115">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="a4528-116">고급 인덱싱 결과 보기</span><span class="sxs-lookup"><span data-stu-id="a4528-116">Viewing Advanced indexing results</span></span>

<span data-ttu-id="a4528-117">고급 인덱싱 프로세스가 완료되면 다시 처리의 효율성을 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4528-117">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of reprocessing.</span></span>  <span data-ttu-id="a4528-118">사례에 대한 처리 탭의  고급 인덱싱 결과 보기에서 하이브리드 인덱스에 추가된 항목 수를 *그래프에 나열합니다.*</span><span class="sxs-lookup"><span data-stu-id="a4528-118">In the Advanced indexing results view on the **Processing** tab for a case, the graph lists the number of items added to the *hybrid index*.</span></span>  <span data-ttu-id="a4528-119">하이브리드 인덱스는 다시 Advanced eDiscovery 콘텐츠를 저장하는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="a4528-119">The hybrid index is where Advanced eDiscovery stores the reprocessed content.</span></span>

<span data-ttu-id="a4528-120">이 보기에는 수정이 필요한 항목 수와 파일 형식별로 다른 오류 그래프도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4528-120">This view  also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="a4528-121">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a4528-121">For more information, see:</span></span>

- [<span data-ttu-id="a4528-122">데이터를 처리할 때 오류 수정</span><span class="sxs-lookup"><span data-stu-id="a4528-122">Error remediation when processing data</span></span>](error-remediation-when-processing-data-in-advanced-ediscovery.md)

- [<span data-ttu-id="a4528-123">단일 항목 오류 수정</span><span class="sxs-lookup"><span data-stu-id="a4528-123">Single item error remediation</span></span>](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a><span data-ttu-id="a4528-124">수급자에 대한 고급 인덱스 업데이트</span><span class="sxs-lookup"><span data-stu-id="a4528-124">Updating the Advanced index for custodians</span></span>

<span data-ttu-id="a4528-125">관리인이 사례에 추가될 Advanced eDiscovery 부분적으로 인덱싱된 항목은 모두 다시 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4528-125">When a custodian is added to an Advanced eDiscovery case, all partially indexed items are reprocessed.</span></span> <span data-ttu-id="a4528-126">그러나 시간이 지나면 부분적으로 인덱싱된 항목이 사용자의 사서함 또는 사용자 계정에 추가될 OneDrive 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4528-126">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="a4528-127">필요한 경우 특정관리자에 대한 인덱스를 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4528-127">If necessary, you can update the index for specific custodian.</span></span> <span data-ttu-id="a4528-128">자세한 내용은 [Manage custodians in an Advanced eDiscovery 참조하세요.](manage-new-custodians.md#re-index-custodian-data)</span><span class="sxs-lookup"><span data-stu-id="a4528-128">For more information, see [Manage custodians in an Advanced eDiscovery case](manage-new-custodians.md#re-index-custodian-data).</span></span> <span data-ttu-id="a4528-129">처리 탭에서 업데이트 인덱스를 클릭하여 사례에 있는 모든 정보주에 대한 인덱스를 업데이트할 **수** 있습니다. </span><span class="sxs-lookup"><span data-stu-id="a4528-129">You can also update the index for all custodians in a case by clicking the **Update index** on the **Processing** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="a4528-130">양도인 인덱스를 업데이트하는 것은 긴 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="a4528-130">Updating custodian indexes is a long running process.</span></span> <span data-ttu-id="a4528-131">경우에 한해 하루 두 번 이상 인덱스를 업데이트하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a4528-131">It's recommended that you don't update indexes more than once a day in a case.</span></span>
