---
title: 'Microsoft Threat Protection 고급 헌팅의 공유 쿼리 사용 '
description: 미리 정의된 쿼리 및 공유 쿼리를 사용하여 위협 요소를 즉시 헌팅합니다. 쿼리를 공용 또는 조직에 공유합니다.
keywords: 고급 구하기, 위협 검색, 사이버 위협 사냥, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 사용자 지정 감지, 스키마, kusto, github 리포지토리, 내 쿼리, 공유 쿼리
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 64c9b07dad0f109698222d3f3f079a4f3318273a
ms.sourcegitcommit: 5b8e9935fe7bfcb96b8f8356119ce23152bd16a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2020
ms.locfileid: "41210313"
---
# <a name="use-shared-queries-in-advanced-hunting"></a><span data-ttu-id="bf253-105">고급 헌팅에서 공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="bf253-105">Use shared queries in advanced hunting</span></span>

<span data-ttu-id="bf253-106">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="bf253-106">**Applies to:**</span></span>
- <span data-ttu-id="bf253-107">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="bf253-107">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="bf253-108">[고급 헌팅](advanced-hunting-overview.md) 쿼리는 동일한 조직에 있는 사용자들 간에 공유될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf253-108">[Advanced hunting](advanced-hunting-overview.md) queries can be shared among users in the same organization.</span></span> <span data-ttu-id="bf253-109">GitHub에서 공개적으로 공유되는 쿼리를 찾을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf253-109">You can also find queries shared publicly on GitHub.</span></span> <span data-ttu-id="bf253-110">이러한 쿼리를 사용하여 쿼리를 처음부터 작성하지 않고도 특정 위협 요소를 신속하게 파악할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf253-110">These queries let you quickly pursue specific threat hunting scenarios without having to write queries from scratch.</span></span>

![공유 쿼리 이미지](../images/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a><span data-ttu-id="bf253-112">쿼리 저장, 수정 및 공유</span><span class="sxs-lookup"><span data-stu-id="bf253-112">Save, modify, and share a query</span></span>
<span data-ttu-id="bf253-113">새로운 쿼리나 기존 쿼리를 저장하여 조직의 다른 사용자와 공유하거나 해당 쿼리를 액세스하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf253-113">You can save a new or existing query so that it is only accessible to you or shared with other users in your organization.</span></span> 

1. <span data-ttu-id="bf253-114">쿼리 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="bf253-114">Create or modify a query.</span></span> 

2. <span data-ttu-id="bf253-115">**쿼리 저장** 드롭다운 단추를 클릭하고 **다른 이름으로 저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bf253-115">Click the **Save query** drop-down button and select **Save as**.</span></span>
    
3. <span data-ttu-id="bf253-116">쿼리 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="bf253-116">Enter a name for the query.</span></span> 

   ![쿼리 저장의 이미지](../images/advanced-hunting-save-query.png)

4. <span data-ttu-id="bf253-118">쿼리를 저장할 폴더를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bf253-118">Select the folder where you'd like to save the query.</span></span>
    - <span data-ttu-id="bf253-119">**공유 쿼리** — 조직에 있는 모든 사용자에게 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="bf253-119">**Shared queries** — shared to all users your organization</span></span>
    - <span data-ttu-id="bf253-120">**나의 쿼리** — 사용자 본인만 액세스 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="bf253-120">**My queries** — accessible only to you</span></span>
    
5. <span data-ttu-id="bf253-121">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bf253-121">Select **Save**.</span></span> 

## <a name="delete-or-rename-a-query"></a><span data-ttu-id="bf253-122">쿼리 삭제 또는 이름 바꾸기</span><span class="sxs-lookup"><span data-stu-id="bf253-122">Delete or rename a query</span></span>
1. <span data-ttu-id="bf253-123">이름을 바꾸거나 삭제하려는 쿼리를 마우스 오른쪽 단추로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bf253-123">Right-click on a query you want to rename or delete.</span></span>

    ![쿼리 삭제의 이미지](../images/advanced_hunting_delete_rename.png)

2. <span data-ttu-id="bf253-125">**삭제** 선택하고 삭제를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="bf253-125">Select **Delete** and confirm deletion.</span></span> <span data-ttu-id="bf253-126">또는 **이름 바꾸기**를 선택하고 쿼리의 새 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="bf253-126">Or select **Rename** and provide a new name for the query.</span></span>

## <a name="access-queries-in-the-github-repository"></a><span data-ttu-id="bf253-127">GitHub 리포지토리의 쿼리에 액세스</span><span class="sxs-lookup"><span data-stu-id="bf253-127">Access queries in the GitHub repository</span></span>  
<span data-ttu-id="bf253-128">Microsoft 보안 연구원은 [GitHub의 지정된 공용 저장소](https://github.com/microsoft/MTP-AHQ)에서 고급 헌팅 쿼리를 정기적으로 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf253-128">Microsoft security researchers regularly share advanced hunting queries in a [designated public repository on GitHub](https://github.com/microsoft/MTP-AHQ).</span></span> <span data-ttu-id="bf253-129">이 리포지토리는 참가 기회가 열려 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf253-129">This repository is open to contributions.</span></span> <span data-ttu-id="bf253-130">참가하려면 [무료로 GitHub에 가입](https://github.com/)하세요.</span><span class="sxs-lookup"><span data-stu-id="bf253-130">To contribute, [join GitHub for free](https://github.com/).</span></span>

>[!tip]
><span data-ttu-id="bf253-131">또한 Microsoft 보안 연구원들은 최신 위협과 관련 된 활동과 지표를 찾는 데 사용할 수 있는 고급 검색 쿼리를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bf253-131">Microsoft security researchers also provide advanced hunting queries that you can use to locate activities and indicators associated with emerging threats.</span></span> <span data-ttu-id="bf253-132">이러한 쿼리는 Microsoft Defender 보안 센터의 [위협 분석](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) 보고서의 일부로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf253-132">These queries are provided as part of the [threat analytics](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) reports in Microsoft Defender Security Center.</span></span>

## <a name="related-topics"></a><span data-ttu-id="bf253-133">관련 항목</span><span class="sxs-lookup"><span data-stu-id="bf253-133">Related topics</span></span>
- [<span data-ttu-id="bf253-134">사전 대응식 위협 탐지</span><span class="sxs-lookup"><span data-stu-id="bf253-134">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="bf253-135">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="bf253-135">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="bf253-136">여러 장치 및 전자 메일에서 위협을 탐지</span><span class="sxs-lookup"><span data-stu-id="bf253-136">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="bf253-137">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="bf253-137">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="bf253-138">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="bf253-138">Apply query best practices</span></span>](advanced-hunting-best-practices.md)