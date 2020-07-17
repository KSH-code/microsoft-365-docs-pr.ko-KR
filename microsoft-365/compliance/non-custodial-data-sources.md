---
title: 고급 eDiscovery 사례에 비 custodial 데이터 원본 추가
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
description: 고급 eDiscovery 사례에 custodial 되지 않은 데이터 원본을 추가 하 고 데이터 원본을 유지할 수 있습니다. Custodial이 아닌 데이터 원본은 reindexed 이므로 부분적으로 인덱싱된 콘텐츠가 완전히 검색 가능 하도록 다시 처리 됩니다.
ms.openlocfilehash: 2009a8cc82dc9407e9871409e85cdcd321ea9bb0
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024748"
---
# <a name="add-non-custodial-data-sources-to-an-advanced-ediscovery-case"></a><span data-ttu-id="631f8-104">고급 eDiscovery 사례에 비 custodial 데이터 원본 추가</span><span class="sxs-lookup"><span data-stu-id="631f8-104">Add non-custodial data sources to an Advanced eDiscovery case</span></span>

<span data-ttu-id="631f8-105">고급 eDiscovery 사례에서는 경우에 따라 Microsoft 365 데이터 원본을 custodian에 연결 하는 사용자의 요구 사항을 충족 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="631f8-105">In Advanced eDiscovery cases, it doesn't always meet your needs to associate a Microsoft 365 data source with a custodian in the case.</span></span> <span data-ttu-id="631f8-106">그러나 데이터를 검색 하 고, 검토 집합에 추가한 다음 검토할 수 있도록 반드시 사례와 연결 해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="631f8-106">But you may still need to associate that data with a case so that you search it, add it to review set, and review it.</span></span> <span data-ttu-id="631f8-107">*Custodial이 아닌 데이터 원본을* 호출 하는 새로운 기능을 사용 하면 데이터를 custodian에 연결 하지 않고도 사례에 데이터를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="631f8-107">The new feature called *non-custodial data sources* lets you add data to a case without having to associate the data to a custodian.</span></span> <span data-ttu-id="631f8-108">또한 custodian와 연결 된 데이터에 사용할 수 있는 custodial 데이터에 동일한 고급 eDiscovery 기능이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="631f8-108">It also applies the same Advanced eDiscovery functionality to non-custodial data that's available for data associated with custodian.</span></span> <span data-ttu-id="631f8-109">Custodial 되지 않은 데이터에 적용할 수 있는 가장 유용한 두 가지 기능은 보류 상태로 설정 하 고 [고급 인덱싱을](indexing-custodian-data.md)사용 하 여 처리 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="631f8-109">Two of the most useful features that you can apply to non-custodial data is placing it on hold and processing it using [Advanced indexing](indexing-custodian-data.md).</span></span>

## <a name="add-a-non-custodial-data-source"></a><span data-ttu-id="631f8-110">비 custodial 데이터 원본 추가</span><span class="sxs-lookup"><span data-stu-id="631f8-110">Add a non-custodial data source</span></span>

<span data-ttu-id="631f8-111">고급 eDiscovery 사례에서 custodial가 아닌 데이터 원본을 추가 하 고 관리 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="631f8-111">Follow these steps to add and manage non-custodial data sources in an Advanced eDiscovery case.</span></span>

1. <span data-ttu-id="631f8-112">**고급 eDiscovery** 홈 페이지에서 데이터를 추가 하려는 사례를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="631f8-112">On the **Advanced eDiscovery** home page, click the case that you want to add the data to.</span></span>

2. <span data-ttu-id="631f8-113">**원본** 페이지에서 **데이터 위치** 탭을 클릭 한 다음 **데이터 위치 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="631f8-113">On the **Sources** page, click the **Data locations** tab, and then click **Add data location**.</span></span>

3. <span data-ttu-id="631f8-114">**데이터 위치 추가** 를 클릭 하 고 사례에 추가할 데이터 원본을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="631f8-114">Click **Add data location** and choose the data sources that you want to add to the case.</span></span> <span data-ttu-id="631f8-115">사서함과 사이트를 여러 개 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="631f8-115">You can add multiple mailboxes and sites.</span></span>

4. <span data-ttu-id="631f8-116">마법사의 **위치 선택** 페이지에서 사서함 이나 사이트 (또는 둘 다)를 사례에 custodial 하지 않는 데이터 원본으로 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="631f8-116">On the **Choose locations** page in the wizard, add mailboxes or sites (or both) as non-custodial data sources to the case.</span></span>

5. <span data-ttu-id="631f8-117">데이터 원본을 추가한 후 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="631f8-117">After adding the data sources, click **Next**.</span></span>

6. <span data-ttu-id="631f8-118">**위치 유지** 페이지에서 관련 확인란을 선택 하거나 선택을 취소 하 여 보류 상태로 설정할 데이터 원본을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="631f8-118">On the **Place holds** page, choose which data sources you want to place on hold by selecting or unselecting the associated checkbox.</span></span>

7. <span data-ttu-id="631f8-119">보류 선택을 확인 한 후 **제출을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="631f8-119">Verify the hold selections and then click **Submit**.</span></span>

   <span data-ttu-id="631f8-120">추가한 각 custodial 데이터 원본이 **데이터 원본** 페이지에 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="631f8-120">Each non-custodial data source that you added is listed on the **Data sources** page.</span></span>

   <span data-ttu-id="631f8-121">또한, 대/소문자를 구분 **하는 작업 탭에** 는 *Custodial 데이터 다시 인덱스* 라는 작업이 만들어지고 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="631f8-121">Also, a job named *Reindexing non-custodial data* is created and displayed on the **Jobs** tab of the case.</span></span> <span data-ttu-id="631f8-122">작업을 만든 후에는 초기화 된 고급 인덱싱 프로세스와 데이터 원본의 reindexed 됩니다.</span><span class="sxs-lookup"><span data-stu-id="631f8-122">After the job is created, the Advanced indexing process in initiated and the data sources are reindexed.</span></span>

## <a name="managing-the-hold-on-non-custodial-data-sources"></a><span data-ttu-id="631f8-123">비 custodial 데이터 원본에 대 한 보류 관리</span><span class="sxs-lookup"><span data-stu-id="631f8-123">Managing the hold on non-custodial data sources</span></span>

<span data-ttu-id="631f8-124">Custodial이 아닌 데이터 원본에 대 한 보류를 설정 하면 사례에 대 한 custodial 데이터 원본이 모두 포함 된 보류 정책이 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="631f8-124">After you place a hold on a non-custodial data source, a hold policy that contains all non-custodial data sources for the case is automatically created.</span></span> <span data-ttu-id="631f8-125">Custodial 되지 않은 추가 데이터 원본을 보존 하면이 보류 정책에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="631f8-125">When you place additional non-custodial data sources on hold, they are added to this hold policy.</span></span>

1. <span data-ttu-id="631f8-126">사례 **홈** 페이지에서 **보류** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="631f8-126">On the **Home** page of the case, click the **Holds** tab.</span></span>

2. <span data-ttu-id="631f8-127">**보류** 페이지에서 \*\*Ncdshold- \<GUID\> \*\*를 클릭 하 고 GUID 값은 사례에 대해 고유 합니다.</span><span class="sxs-lookup"><span data-stu-id="631f8-127">On the **Holds** page, and click **NCDSHold-\<GUID\>**, where the GUID value is unique to the case.</span></span>

3. <span data-ttu-id="631f8-128">플라이 아웃 페이지에서 **보류 편집** 을 클릭 하 여 보류 중인 custodial 않은 모든 데이터 원본을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="631f8-128">On the flyout page, click **Edit hold** to view all the non-custodial data sources that are placed on hold.</span></span>

<span data-ttu-id="631f8-129">Custodial이 아닌 데이터 원본에 대해 수행할 수 있는 관리 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="631f8-129">You can perform the following management task on non-custodial data sources:</span></span>

- <span data-ttu-id="631f8-130">이 보류를 편집 하 여 사례에서 모든 비 custodial 데이터 원본에 적용 되는 쿼리 기반 보존을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="631f8-130">You can edit the hold to create a query-based hold that is applied to all non-custodial data sources in the case.</span></span>

- <span data-ttu-id="631f8-131">보류에서 custodial가 아닌 데이터 원본을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="631f8-131">You can release a non-custodial data source from the hold.</span></span> <span data-ttu-id="631f8-132">데이터 원본을 해제 해도 비 custodial 데이터 원본이 사례에서 제거 되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="631f8-132">Releasing a data source doesn't remove the non-custodial data source from the case.</span></span> <span data-ttu-id="631f8-133">데이터 원본에 있던 보류만 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="631f8-133">It only removes the hold that was placed on the data source.</span></span>
