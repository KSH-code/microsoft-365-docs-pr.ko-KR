---
title: 비보조 데이터 원본을 사례에 Advanced eDiscovery 추가
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
description: 비보조 데이터 원본을 Advanced eDiscovery 데이터 원본을 보류할 수 있습니다. 비관리 데이터 원본은 다시 인덱싱되어 부분적으로 인덱싱된 것으로 표시된 모든 콘텐츠는 완전히 빠르고 검색할 수 있도록 다시 처리됩니다.
ms.openlocfilehash: 467f0e1167bfebe21bd3f2bbd52acd81529b8685
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740355"
---
# <a name="add-non-custodial-data-sources-to-an-advanced-ediscovery-case"></a><span data-ttu-id="927c4-104">비보조 데이터 원본을 사례에 Advanced eDiscovery 추가</span><span class="sxs-lookup"><span data-stu-id="927c4-104">Add non-custodial data sources to an Advanced eDiscovery case</span></span>

<span data-ttu-id="927c4-105">Advanced eDiscovery 경우 데이터 원본을 보호자와 Microsoft 365 요구 사항을 항상 충족하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="927c4-105">In Advanced eDiscovery cases, it doesn't always meet your needs to associate a Microsoft 365 data source with a custodian in the case.</span></span> <span data-ttu-id="927c4-106">그러나 해당 데이터를 검색하고 검토 집합에 추가한 다음 분석 및 검토할 수 있도록 해당 데이터를 사례와 연결해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="927c4-106">But you may still need to associate that data with a case so that you can search it, add it to a review set, and analyze and review it.</span></span> <span data-ttu-id="927c4-107">Advanced eDiscovery 기능의 기능을 비보조 데이터 원본이라고 하여, 보호자에 연결하지 않고도 사례에 데이터를 추가할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="927c4-107">The feature in Advanced eDiscovery is called *non-custodial data sources* and lets you add data to a case without having to associate it to a custodian.</span></span> <span data-ttu-id="927c4-108">또한 Advanced eDiscovery 데이터에 사용할 수 있는 비보조 데이터에도 동일한 Advanced eDiscovery 기능을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="927c4-108">It also applies the same Advanced eDiscovery functionality to non-custodial data that's available for data associated with custodian.</span></span> <span data-ttu-id="927c4-109">비관리 데이터에 적용할 수 있는 가장 유용한 두 가지는 데이터를 보류하고 고급 인덱싱을 사용하여 처리하는 [것입니다.](indexing-custodian-data.md)</span><span class="sxs-lookup"><span data-stu-id="927c4-109">Two of the most useful things that you can apply to non-custodial data is placing it on hold and processing it using [Advanced indexing](indexing-custodian-data.md).</span></span>

## <a name="add-a-non-custodial-data-source"></a><span data-ttu-id="927c4-110">비보조 데이터 원본 추가</span><span class="sxs-lookup"><span data-stu-id="927c4-110">Add a non-custodial data source</span></span>

<span data-ttu-id="927c4-111">다음 단계에 따라 관리 사례에서 비관리 데이터 원본을 추가하고 Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="927c4-111">Follow these steps to add and manage non-custodial data sources in an Advanced eDiscovery case.</span></span>

1. <span data-ttu-id="927c4-112">Advanced eDiscovery **홈** 페이지에서 데이터를 추가할 사례를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="927c4-112">On the **Advanced eDiscovery** home page, click the case that you want to add the data to.</span></span>

2. <span data-ttu-id="927c4-113">데이터 원본 **탭을** 클릭한 다음 데이터 원본 추가 데이터 **위치**  >  **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="927c4-113">Click the **Data sources** tab and then click **Add data source** > **Add data locations**.</span></span>

3. <span data-ttu-id="927c4-114">새 **비보조** 데이터 위치 플라이아웃 페이지에서 사례에 추가할 데이터 원본을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="927c4-114">On the **New non-custodial data locations** flyout page, choose the data sources that you want to add to the case.</span></span> <span data-ttu-id="927c4-115">사서함 또는 SharePoint 섹션을 확장한  Exchange 편집을 클릭하여 여러 사서함 및 사이트를 **추가할** 수 **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="927c4-115">You can add multiple mailboxes and sites by expanding the **SharePoint** or **Exchange** sections and then clicking **Edit**.</span></span>

   ![사이트 SharePoint 사이트 및 Exchange 비보조 데이터 원본으로 추가](../media/NonCustodialDataSources1.png)

   - <span data-ttu-id="927c4-117">**SharePoint** - **편집을 클릭하여** 사이트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="927c4-117">**SharePoint** - Click **Edit** to add sites.</span></span> <span data-ttu-id="927c4-118">목록에서 사이트를 선택하거나 검색 표시줄에 사이트의 URL을 입력하여 사이트를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="927c4-118">Select a site in the list or you can search for a site by typing the URL of the site in the search bar.</span></span> <span data-ttu-id="927c4-119">비구성 데이터 원본으로 추가할 사이트를 선택하고 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="927c4-119">Select the sites that you want to add as non-custodian data sources and click **Add**.</span></span>

   - <span data-ttu-id="927c4-120">**Exchange** - 편집을 **클릭하여** 사서함을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="927c4-120">**Exchange** - Click **Edit** to add mailboxes.</span></span> <span data-ttu-id="927c4-121">사서함 또는 메일 그룹의 검색 상자에 이름 또는 별칭(최소 3자)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="927c4-121">Type a name or alias (a minimum of three characters) in the search box for mailboxes or distribution groups.</span></span> <span data-ttu-id="927c4-122">비구성 데이터 원본으로 추가할 사서함을 선택하고 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="927c4-122">Select the mailboxes that you want to add as non-custodian data sources and click **Add**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="927c4-123">SharePoint 및  Exchange 섹션을  사용하여 팀 또는 Yammer 그룹과 연결된 사이트 및 사서함을 비구성 데이터 원본으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="927c4-123">You can use the **SharePoint** and **Exchange** sections to add sites and mailboxes associated with a Team or Yammer group as non-custodial data sources.</span></span> <span data-ttu-id="927c4-124">팀 또는 팀 그룹과 연결된 사서함 및 사이트를 별도로 Yammer 합니다.</span><span class="sxs-lookup"><span data-stu-id="927c4-124">You have to separately add the mailbox and site associated with a Team or Yammer group.</span></span>

4. <span data-ttu-id="927c4-125">비보조 데이터 원본을 추가한 후 해당 위치를 보류 또는 보류할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="927c4-125">After you add non-custodial data sources, you have the option to place those locations on hold or not.</span></span> <span data-ttu-id="927c4-126">데이터 원본 옆의  보류 확인란을 선택하거나 선택을 선택하여 보류합니다.</span><span class="sxs-lookup"><span data-stu-id="927c4-126">Select or unselect the **Hold** checkbox next to the data source to place it on hold.</span></span>

5. <span data-ttu-id="927c4-127">새 **비보조** 데이터  위치 플라이아웃 페이지의 아래쪽에서 추가를 클릭하여 사례에 데이터 원본을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="927c4-127">Click **Add** at the bottom of the **New non-custodial data locations** flyout page to add the data sources to the case.</span></span>

   <span data-ttu-id="927c4-128">추가한 각 비보조 데이터 원본이 데이터 원본 페이지에 **나열됩니다.**</span><span class="sxs-lookup"><span data-stu-id="927c4-128">Each non-custodial data source that you added is listed on the **Data sources** page.</span></span> <span data-ttu-id="927c4-129">비보조 데이터 원본은 원본 유형 열의 **데이터** 위치 **값으로 식별됩니다.**</span><span class="sxs-lookup"><span data-stu-id="927c4-129">Non-custodial data sources are identified by the **Data location** value in the **Source type** column.</span></span>

   ![데이터 원본 탭의 비보조 데이터 원본](../media/NonCustodialDataSources2.png)

<span data-ttu-id="927c4-131">비보조 데이터 원본을 사례에 추가하고 나면 비보안 데이터 *다시* 인덱서라는 작업이 만들어지며 사례의  작업 탭에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="927c4-131">After you add non-custodial data sources to the case, a job named *Reindexing non-custodial data* is created and displayed on the **Jobs** tab of the case.</span></span> <span data-ttu-id="927c4-132">작업을 만든 후 고급 인덱싱 프로세스가 시작된 후 데이터 원본을 다시 인덱싱합니다.</span><span class="sxs-lookup"><span data-stu-id="927c4-132">After the job is created, the Advanced indexing process in initiated and the data sources are reindexed.</span></span>

## <a name="manage-the-hold-for-non-custodial-data-sources"></a><span data-ttu-id="927c4-133">비관리 데이터 원본에 대한 보류 관리</span><span class="sxs-lookup"><span data-stu-id="927c4-133">Manage the hold for non-custodial data sources</span></span>

<span data-ttu-id="927c4-134">비보류 데이터 원본에 대해 보류를 설정하면 해당 사례에 대한 비보류 데이터 원본을 포함하는 보류 정책이 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="927c4-134">After you place a hold on a non-custodial data source, a hold policy that contains the non-custodial data sources for the case is automatically created.</span></span> <span data-ttu-id="927c4-135">다른 비보류 데이터 원본을 보류하면 해당 데이터 원본이 이 보류 정책에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="927c4-135">When you place other non-custodial data sources on hold, they are added to this hold policy.</span></span>

1. <span data-ttu-id="927c4-136">사례 Advanced eDiscovery 열고 **보류 탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="927c4-136">Open the Advanced eDiscovery case and select the **Hold** tab.</span></span>

2. <span data-ttu-id="927c4-137">**NCDSHold- \<GUID\>** 를 클릭합니다. 여기서 GUID 값은 사례에 고유합니다.</span><span class="sxs-lookup"><span data-stu-id="927c4-137">Click **NCDSHold-\<GUID\>**, where the GUID value is unique to the case.</span></span>

   <span data-ttu-id="927c4-138">플라이아웃 페이지에는 보류 중이 아닌 데이터 원본에 대한 정보 및 통계가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="927c4-138">The flyout page display information and statistics about the non-custodial data sources on hold.</span></span>

   ![비보조 데이터 원본 보류에 대한 플라이아웃 페이지에 통계가 표시됩니다.](../media/NonCustodialDataSourcesHoldFlyout.png)

3. <span data-ttu-id="927c4-140">보류 **편집을** 클릭하여 보류된 비관리 데이터 원본을 보고 다음 관리 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="927c4-140">Click **Edit hold** to view the non-custodial data sources placed on hold and perform the following management tasks:</span></span>

   - <span data-ttu-id="927c4-141">위치 **페이지에서** 비보류 데이터 원본을 보류에서 제거하여 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="927c4-141">On the **Locations** page, you can release a non-custodial data source by removing it from the hold.</span></span> <span data-ttu-id="927c4-142">데이터 원본을 공개해도 해당 사례에서 비보조 데이터 원본은 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="927c4-142">Releasing a data source doesn't remove the non-custodial data source from the case.</span></span> <span data-ttu-id="927c4-143">데이터 원본에 배치된 보류만 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="927c4-143">It only removes the hold that was placed on the data source.</span></span>

   - <span data-ttu-id="927c4-144">쿼리 **페이지에서** 보류를 편집하여 모든 tha 비보조 데이터 원본에 적용되는 쿼리 기반 보류를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="927c4-144">On the **Query** page, you can edit the hold to create a query-based hold that is applied to all tha non-custodial data sources in the case.</span></span>
