---
title: 고급 헌팅에서 공유 쿼리 사용
description: 미리 정의된 쿼리 및 공유 쿼리를 사용하여 위협 요소를 즉시 헌팅합니다. 쿼리를 공용 또는 조직에 공유합니다.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, mdatp, microsoft defender atp, wdatp 검색, 쿼리, 원격 분석, 사용자 지정 검색, schema, kusto, github 리포지타이저, 내 쿼리, 공유 쿼리
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 78a532167e4256e3453803f1a0b4a9e4875771cf
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499420"
---
# <a name="use-shared-queries-in-advanced-hunting"></a><span data-ttu-id="8b9d6-105">고급 헌팅에서 공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="8b9d6-105">Use shared queries in advanced hunting</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8b9d6-106">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="8b9d6-106">**Applies to:**</span></span>
- [<span data-ttu-id="8b9d6-107">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8b9d6-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="8b9d6-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="8b9d6-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8b9d6-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="8b9d6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

<span data-ttu-id="8b9d6-110">[고급 헌팅](advanced-hunting-overview.md) 쿼리는 동일한 조직에 있는 사용자들 간에 공유될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b9d6-110">[Advanced hunting](advanced-hunting-overview.md) queries can be shared among users in the same organization.</span></span> <span data-ttu-id="8b9d6-111">GitHub에서 공개적으로 공유되는 쿼리를 찾을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b9d6-111">You can also find queries shared publicly on GitHub.</span></span> <span data-ttu-id="8b9d6-112">이러한 쿼리를 사용하여 쿼리를 처음부터 작성하지 않고도 특정 위협 요소를 신속하게 파악할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b9d6-112">These queries let you quickly pursue specific threat hunting scenarios without having to write queries from scratch.</span></span>

![공유 쿼리 이미지](images/atp-advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a><span data-ttu-id="8b9d6-114">쿼리 저장, 수정 및 공유</span><span class="sxs-lookup"><span data-stu-id="8b9d6-114">Save, modify, and share a query</span></span>
<span data-ttu-id="8b9d6-115">새로운 쿼리나 기존 쿼리를 저장하여 조직의 다른 사용자와 공유하거나 해당 쿼리를 액세스하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b9d6-115">You can save a new or existing query so that it is only accessible to you or shared with other users in your organization.</span></span>

1. <span data-ttu-id="8b9d6-116">새 쿼리를 입력하거나 공유 쿼리 또는 내 **쿼리에서** 기존 쿼리를 **로드합니다.**</span><span class="sxs-lookup"><span data-stu-id="8b9d6-116">Type a new query or load an existing one from under **Shared queries** or **My queries**.</span></span>

2. <span data-ttu-id="8b9d6-117">저장 **옵션에서** **다른 사용자로** 저장 또는 저장을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8b9d6-117">Select **Save** or **Save as** from the save options.</span></span> <span data-ttu-id="8b9d6-118">기존 쿼리를 덮어 작성하지 않도록 방지하기 위해 다른 로 **저장을 선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="8b9d6-118">To avoid overwriting an existing query, choose **Save as**.</span></span>

3. <span data-ttu-id="8b9d6-119">쿼리 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8b9d6-119">Enter a name for the query.</span></span>

   ![쿼리 저장의 이미지](images/advanced-hunting-save-query.png)

4. <span data-ttu-id="8b9d6-121">쿼리를 저장할 폴더를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8b9d6-121">Select the folder where you'd like to save the query.</span></span>
    - <span data-ttu-id="8b9d6-122">**공유 쿼리** - 조직의 모든 사용자에게 공유</span><span class="sxs-lookup"><span data-stu-id="8b9d6-122">**Shared queries** — shared to all users in your organization</span></span>
    - <span data-ttu-id="8b9d6-123">**나의 쿼리** — 사용자 본인만 액세스 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="8b9d6-123">**My queries** — accessible only to you</span></span>
    
5. <span data-ttu-id="8b9d6-124">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8b9d6-124">Select **Save**.</span></span>

## <a name="delete-or-rename-a-query"></a><span data-ttu-id="8b9d6-125">쿼리 삭제 또는 이름 바꾸기</span><span class="sxs-lookup"><span data-stu-id="8b9d6-125">Delete or rename a query</span></span>
1. <span data-ttu-id="8b9d6-126">이름을 바꾸거나 삭제하려는 쿼리를 마우스 오른쪽 단추로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8b9d6-126">Right-click on a query you want to rename or delete.</span></span>

    ![쿼리 삭제의 이미지](images/atp_advanced_hunting_delete_rename.png)

2. <span data-ttu-id="8b9d6-128">**삭제** 선택하고 삭제를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8b9d6-128">Select **Delete** and confirm deletion.</span></span> <span data-ttu-id="8b9d6-129">또는 **이름 바꾸기** 를 선택하고 쿼리의 새 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8b9d6-129">Or select **Rename** and provide a new name for the query.</span></span>

## <a name="create-a-direct-link-to-a-query"></a><span data-ttu-id="8b9d6-130">쿼리에 대한 직접 링크 만들기</span><span class="sxs-lookup"><span data-stu-id="8b9d6-130">Create a direct link to a query</span></span>
<span data-ttu-id="8b9d6-131">고급 헌팅 쿼리 편집기에서 쿼리를 직접 여는 링크를 생성하려면 쿼리를 마무리하고 링크 **공유 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8b9d6-131">To generate a link that opens your query directly in the advanced hunting query editor, finalize your query and select **Share link**.</span></span>

## <a name="access-queries-in-the-github-repository"></a><span data-ttu-id="8b9d6-132">GitHub 리포지토리의 쿼리에 액세스</span><span class="sxs-lookup"><span data-stu-id="8b9d6-132">Access queries in the GitHub repository</span></span>  
<span data-ttu-id="8b9d6-133">Microsoft 보안 연구원은 [GitHub의 지정된 공용 저장소](https://github.com/Microsoft/WindowsDefenderATP-Hunting-Queries)에서 고급 헌팅 쿼리를 정기적으로 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b9d6-133">Microsoft security researchers regularly share advanced hunting queries in a [designated public repository on GitHub](https://github.com/Microsoft/WindowsDefenderATP-Hunting-Queries).</span></span> <span data-ttu-id="8b9d6-134">이 리포지토리는 참가 기회가 열려 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b9d6-134">This repository is open to contributions.</span></span> <span data-ttu-id="8b9d6-135">참가하려면 [무료로 GitHub에 가입](https://github.com/)하세요.</span><span class="sxs-lookup"><span data-stu-id="8b9d6-135">To contribute, [join GitHub for free](https://github.com/).</span></span> 

>[!TIP]
><span data-ttu-id="8b9d6-136">또한 Microsoft 보안 연구원들은 최신 위협과 관련 된 활동과 지표를 찾는 데 사용할 수 있는 고급 검색 쿼리를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8b9d6-136">Microsoft security researchers also provide advanced hunting queries that you can use to locate activities and indicators associated with emerging threats.</span></span> <span data-ttu-id="8b9d6-137">이러한 쿼리는 Microsoft Defender 보안 센터의 [위협 분석](threat-analytics.md) 보고서의 일부로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b9d6-137">These queries are provided as part of the [threat analytics](threat-analytics.md) reports in Microsoft Defender Security Center.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8b9d6-138">관련 항목</span><span class="sxs-lookup"><span data-stu-id="8b9d6-138">Related topics</span></span>
- [<span data-ttu-id="8b9d6-139">지능형 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="8b9d6-139">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="8b9d6-140">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="8b9d6-140">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="8b9d6-141">쿼리 결과로 작업</span><span class="sxs-lookup"><span data-stu-id="8b9d6-141">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="8b9d6-142">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="8b9d6-142">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="8b9d6-143">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="8b9d6-143">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="8b9d6-144">사용자 지정 검색 개요</span><span class="sxs-lookup"><span data-stu-id="8b9d6-144">Custom detections overview</span></span>](overview-custom-detections.md)
