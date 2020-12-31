---
title: Advanced eDiscovery 사례에서 관리
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
description: Advanced eDiscovery 사례에서 정보 보기, 편집 및 대량 편집하는 방법을 자세히 알아보고, 편집하고, 대량으로 편집합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a1e9e9d481073c8bb2827d5d65537dbf2b63ef1f
ms.sourcegitcommit: 555b200b618085706dabf8648d27fb6d6427cfce
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/30/2020
ms.locfileid: "49739871"
---
# <a name="manage-custodians-in-an-advanced-ediscovery-case"></a><span data-ttu-id="51fc4-103">Advanced eDiscovery 사례에서 관리</span><span class="sxs-lookup"><span data-stu-id="51fc4-103">Manage custodians in an Advanced eDiscovery case</span></span>

<span data-ttu-id="51fc4-104">Advanced eDiscovery 사례의  원본 탭에 있는 Custodians 페이지에는 사례에 추가된 모든 상주자 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51fc4-104">The Custodians page on the **Sources** tab in an Advanced eDiscovery case contains a list of all custodians that have been added to the case.</span></span> <span data-ttu-id="51fc4-105">사례에 관리인을 추가하면 각 관리자에 대한 세부 정보가 Azure Active Directory에서 자동으로 수집되며 Advanced eDiscovery에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51fc4-105">After you add custodians to a case, details about each custodian are automatically collected from Azure Active Directory and are viewable in Advanced eDiscovery.</span></span>

![Custodians 관리](../media/CustodianDetails.PNG)

## <a name="view-custodian-details"></a><span data-ttu-id="51fc4-107">양도자 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="51fc4-107">View custodian details</span></span>

<span data-ttu-id="51fc4-108">양도자에 대한 세부 정보를 보려면 Custodians 탭의 목록에서 **custodian을** 클릭합니다. 플라이아웃 페이지가 표시되고 해당 보호자에 대한 다음 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51fc4-108">To view the details about a custodian, click the custodian from the list on the **Custodians** tab. A flyout page is displayed and contains the following information about the custodian:</span></span>

- <span data-ttu-id="51fc4-109">연락처 정보</span><span class="sxs-lookup"><span data-stu-id="51fc4-109">Contact information</span></span>

  - <span data-ttu-id="51fc4-110">**표시 이름** - 보금주의 주소부에 표시되는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="51fc4-110">**Display Name** - The name displayed in the address book for the custodian.</span></span> <span data-ttu-id="51fc4-111">일반적으로 이 이름은 양도자 이름, 중간 이니셜 및 성의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="51fc4-111">This is usually the combination of the custodian's first name, middle initial, and last name.</span></span>
  
   - <span data-ttu-id="51fc4-112">**메일/SMTP** - 예를 들어, brianj@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="51fc4-112">**Mail/SMTP** - The primary SMTP address for the custodian, for example, brianj@contoso.onmicrosoft.com.</span></span> <span data-ttu-id="51fc4-113">또한 양도자 UPN(사용자 계정 이름)도 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="51fc4-113">The custodian's user principal name (UPN) is also listed.</span></span>

  - <span data-ttu-id="51fc4-114">**title** - 양도자 직위입니다.</span><span class="sxs-lookup"><span data-stu-id="51fc4-114">**Title** - The custodian's job title.</span></span>

  - <span data-ttu-id="51fc4-115">**Department** - 양도인이 작업하는 부서의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="51fc4-115">**Department** - The name for the department in which the custodian works.</span></span>

  - <span data-ttu-id="51fc4-116">**관리자** - 상사입니다.</span><span class="sxs-lookup"><span data-stu-id="51fc4-116">**Manager** - The custodian's manager.</span></span> <span data-ttu-id="51fc4-117">지정된 관리자는 이 관리자에 대한 에스컬레이터 통신을 받게됩니다.</span><span class="sxs-lookup"><span data-stu-id="51fc4-117">The designated manager will receive any escalation communications for this custodian.</span></span>
  
- <span data-ttu-id="51fc4-118">위치 정보</span><span class="sxs-lookup"><span data-stu-id="51fc4-118">Location information</span></span>

  - <span data-ttu-id="51fc4-119">**city** - 양도인이 있는 도시입니다.</span><span class="sxs-lookup"><span data-stu-id="51fc4-119">**City** - The city in which the custodian is located.</span></span>

  - <span data-ttu-id="51fc4-120">**state** - 양도자 주소의 시 또는 시입니다.</span><span class="sxs-lookup"><span data-stu-id="51fc4-120">**State** - The state or province in the custodian's address.</span></span>

  - <span data-ttu-id="51fc4-121">**국가/지역** - 양도인이 있는 국가/지역입니다.</span><span class="sxs-lookup"><span data-stu-id="51fc4-121">**Country/Region** - The country/region where the custodian is located.</span></span>

  - <span data-ttu-id="51fc4-122">**Office** - 양도자 장소의 사무실 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="51fc4-122">**Office** - The office location in the custodian's place of business.</span></span>

- <span data-ttu-id="51fc4-123">사례 정보</span><span class="sxs-lookup"><span data-stu-id="51fc4-123">Case information</span></span>

  - <span data-ttu-id="51fc4-124">**보류 상태** - 보유자에 대한 보류 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="51fc4-124">**Hold status** - Indicates if the custodian has been placed on hold.</span></span> 

  - <span data-ttu-id="51fc4-125">**통신 상태:** 보유자에 대한 보류 알림이 발급된 경우를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="51fc4-125">**Communication status**: Indicates if the custodian has been issued a hold notice.</span></span> <span data-ttu-id="51fc4-126">보호자에 알림이 발행된 경우 이 속성의 이 값은 **게시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="51fc4-126">If the custodian has been issued a notice, this value of this property is **Published**.</span></span> <span data-ttu-id="51fc4-127">양도자에 알림이 발급되지 않은 경우 상태는 **게시되지 않은 상태입니다.**</span><span class="sxs-lookup"><span data-stu-id="51fc4-127">If the custodian has not been issued a notice, the status is **Un-published**.</span></span> 

  - <span data-ttu-id="51fc4-128">**status** - 사례 내의 보금자 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="51fc4-128">**Status** - The status of the custodian within the case.</span></span> <span data-ttu-id="51fc4-129">활성 **상태는** 양도인이 사례의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="51fc4-129">A status of **Active** indicates that the custodian is part of the case.</span></span> <span data-ttu-id="51fc4-130">양도인이 사례에서 릴리스된 경우 상태가 릴리스된 것으로 **변경됩니다.**</span><span class="sxs-lookup"><span data-stu-id="51fc4-130">If a custodian is released from a case, the status is changed to **Released**.</span></span> 

- <span data-ttu-id="51fc4-131">데이터 원본 및 인덱싱 정보</span><span class="sxs-lookup"><span data-stu-id="51fc4-131">Data sources and indexing information</span></span>

    - <span data-ttu-id="51fc4-132">**데이터 원본** - 보호자와 연결되어 있으며 사례에 속하는 데이터 원본(사서함, 사이트 및 Teams)의 수와 유형을 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="51fc4-132">**Data sources** - Shows the count and type of data sources (mailboxes, sites, and Teams) that are associated with the custodian and are part of the case.</span></span>

    - <span data-ttu-id="51fc4-133">**인덱스 업데이트 시간** - 고급 인덱싱 작업이 마지막으로 트리거된 시간 및 날짜를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="51fc4-133">**Index updated time** - Indicates the time and date for when the advanced indexing job was last triggered.</span></span> <span data-ttu-id="51fc4-134">이 속성은 고급 인덱싱 프로세스가 현재 진행 중인 경우도 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="51fc4-134">This property will also indicate when the advanced indexing process is currently in progress.</span></span>


## <a name="edit-a-custodian"></a><span data-ttu-id="51fc4-135">양도자 편집</span><span class="sxs-lookup"><span data-stu-id="51fc4-135">Edit a custodian</span></span>

<span data-ttu-id="51fc4-136">사례가 진행될 때 사례와 관련된 추가 데이터 원본이 있을 & 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51fc4-136">As your case progresses, you may discover that there may be additional data sources relevant to a specific custodian & your case.</span></span> <span data-ttu-id="51fc4-137">다른 시나리오에서는 검토되고 관련이 없는 것으로 확인된 특정 데이터 원본을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51fc4-137">In other scenarios, you may want to remove certain data sources that have been reviewed and deemed as not relevant.</span></span>

<span data-ttu-id="51fc4-138">보호자와 연결된 데이터 원본을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="51fc4-138">To update the data sources that are associated with a custodian:</span></span>

1. <span data-ttu-id="51fc4-139">Advanced  **eDiscovery를 > eDiscovery를 통해 eDiscovery로** 이동한 후 사례를 여는 것이 가장 까다로우며,</span><span class="sxs-lookup"><span data-stu-id="51fc4-139">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>
  
2. <span data-ttu-id="51fc4-140">원본 **탭을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="51fc4-140">Click the **Sources** tab.</span></span>
  
3. <span data-ttu-id="51fc4-141">**Custodians** 페이지에서 목록에서 보금을 선택하고 플라이아웃  페이지에서 편집을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="51fc4-141">On the **Custodians** page, select a custodian from the list and click **Edit** on the flyout page.</span></span>

    ![데이터 원본 편집](../media/EditCustodianDataSource.PNG)
  
4. <span data-ttu-id="51fc4-143">데이터 **원본** 선택 탭을 클릭하여 관리인의 Exchange 사서함 및 OneDrive 계정에 대한 설정을 변경하고 데이터 원본 **선택을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="51fc4-143">Click **Choose data sources** tab to change the settings for the custodian's Exchange mailbox and OneDrive account, click **Choose data sources**.</span></span>
  
5. <span data-ttu-id="51fc4-144">추가 **데이터** 원본 선택 탭을 클릭하여 거래소와 연결된 Teams, SharePoint 또는 Exchange 사서함을 추가하거나 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="51fc4-144">Click the **Select additional data sources** tab to add or remove Teams, SharePoint, or Exchange mailboxes associated with the custodian.</span></span> 

    <span data-ttu-id="51fc4-145">보호자와 연결된 데이터 원본에 대한 자세한 내용은 사례에 보호자 추가를 [참조하세요.](add-custodians-to-case.md)</span><span class="sxs-lookup"><span data-stu-id="51fc4-145">For more information about data sources associated with a custodian, see [Add custodians to a case](add-custodians-to-case.md).</span></span> 
  
6. <span data-ttu-id="51fc4-146">**보유자에** 대한 보류를 활성화 또는 비활성화하려면 장소 보유를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="51fc4-146">Click **Place custodial holds** to enable or disable the hold for the custodian.</span></span>

## <a name="re-index-custodian-data"></a><span data-ttu-id="51fc4-147">보호자 데이터 다시 인덱싱</span><span class="sxs-lookup"><span data-stu-id="51fc4-147">Re-index custodian data</span></span>

<span data-ttu-id="51fc4-148">법적 조사를 위한 대부분의 eDiscovery 워크플로에서는 법적 사례에 양도인이 추가된 후 보호자 데이터의 하위 집합을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="51fc4-148">In most eDiscovery workflows for legal investigations, a subset of a custodian's data is searched after the custodian is added to a legal case.</span></span> <span data-ttu-id="51fc4-149">파일 크기가 매우 크거나 데이터 손상이 있을 수 있기 때문에, 보호자와 연결된 데이터 원본의 일부 항목이 부분적으로 인덱싱될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51fc4-149">Because of very large file sizes or possible data corruption, some items in the data sources associated with a custodian may be partially indexed.</span></span> <span data-ttu-id="51fc4-150">Advanced [](indexing-custodian-data.md) eDiscovery의 고급 인덱싱 기능을 사용하여 대부분의 부분적으로 인덱싱된 항목은 이러한 항목을 요구 시 다시 인덱싱하여 자동으로 수정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51fc4-150">Using the [advanced indexing](indexing-custodian-data.md) capability in the Advanced eDiscovery, most partially indexed items can be automatically remediated by re-indexing these items on demand.</span></span>

<span data-ttu-id="51fc4-151">보안 주관이 사례에 추가될 경우, 고급 인덱싱 프로세스에 의해 보호자와 연결된 데이터 원본에 있는 데이터가 자동으로 다시 인덱싱됩니다.</span><span class="sxs-lookup"><span data-stu-id="51fc4-151">When a custodian is added to a case, the data located in the data sources associated with the custodian is automatically re-indexed (by the advanced indexing process).</span></span> <span data-ttu-id="51fc4-152">즉, 데이터를 다운로드하여 수정한 다음 오프라인으로 검색하는 대신 데이터를 현재 상태로 두면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="51fc4-152">This means you can leave the data in-place instead of having to download and remediate it and then search it offline).</span></span> <span data-ttu-id="51fc4-153">그러나 법률 사례의 수명 주기 동안 새 데이터 원본이 보호자와 연결될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51fc4-153">However, during the lifecycle of a legal case new data sources might be associated with a custodian.</span></span> <span data-ttu-id="51fc4-154">이 경우 고급 인덱싱 프로세스를 다시 실행하여 부분적으로 인덱싱된 항목을 수정하고 관리자 데이터에 대한 인덱스를 업데이트하여 보호자 데이터를 다시 인덱싱할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51fc4-154">In this case, you can re-index the custodian's data by re-running the advanced indexing process to remediate any partially indexed items and update the index for the custodian's data.</span></span>

<span data-ttu-id="51fc4-155">부분적으로 인덱싱된 항목을 해결하기 위해 다시 인덱싱 프로세스를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="51fc4-155">To trigger the re-indexing process to address partially indexed items:</span></span>

1. <span data-ttu-id="51fc4-156">Advanced  **eDiscovery를 > eDiscovery를 통해 eDiscovery로** 이동한 후 사례를 여는 것이 가장 까다로우며,</span><span class="sxs-lookup"><span data-stu-id="51fc4-156">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>

2. <span data-ttu-id="51fc4-157">원본 **탭을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="51fc4-157">Click the **Sources** tab.</span></span>

3. <span data-ttu-id="51fc4-158">**Custodians** 페이지에서 데이터를 다시 인덱서해야 하는 보호자(custodian)를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="51fc4-158">On the **Custodians** page, select a custodian whose data must be reindexed.</span></span>

4. <span data-ttu-id="51fc4-159">플라이아웃 페이지에서 인덱스 **업데이트를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="51fc4-159">On the flyout page, click **Update index**.</span></span>

   <span data-ttu-id="51fc4-160">인덱스 작업이 만들어졌다는 대화 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="51fc4-160">A dialog is displayed saying the index job has been created.</span></span>

<span data-ttu-id="51fc4-161">재인덱싱은 장기적인 프로세스입니다. 생성된 해당 작업의 이름은 재인덱싱 보호자 **데이터입니다.**</span><span class="sxs-lookup"><span data-stu-id="51fc4-161">Re-indexing custodian data is a long-running process; the corresponding job that's created is named **Re-indexing custodian data**.</span></span> <span data-ttu-id="51fc4-162">인덱싱 작업 상태  열의 상태를  모니터링하여 작업 탭 또는 관리 탭에서 진행 상황을 **추적할 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51fc4-162">You can track the progress on the **Jobs** tab or on the **Custodians** tab by monitoring the status in the **Indexing job status** column.</span></span>

<span data-ttu-id="51fc4-163">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="51fc4-163">For more information, see:</span></span>

- [<span data-ttu-id="51fc4-164">오류 처리 작업</span><span class="sxs-lookup"><span data-stu-id="51fc4-164">Work with processing errors</span></span>](processing-data-for-case.md)

- [<span data-ttu-id="51fc4-165">작업 관리</span><span class="sxs-lookup"><span data-stu-id="51fc4-165">Manage jobs</span></span>](managing-jobs-ediscovery20.md)

## <a name="release-a-custodian-from-a-case"></a><span data-ttu-id="51fc4-166">사례에서 양도자 해제</span><span class="sxs-lookup"><span data-stu-id="51fc4-166">Release a custodian from a case</span></span>

<span data-ttu-id="51fc4-167">양도인은 사례가 마감되거나, 양도인이 더 이상 사례에 대한 콘텐츠를 보존할 의무가 없는 경우 또는 해당 사례와 더 이상 관련이 없는 것으로 판단되는 경우에 릴리스됩니다.</span><span class="sxs-lookup"><span data-stu-id="51fc4-167">A custodian is released in situations where a case is closed, the custodian is no longer under obligation to preserve content for a case, or when the custodian is deemed to no longer be relevant to the case.</span></span> 

<span data-ttu-id="51fc4-168">보류 알림이 게시된 후 보유를 해제하면 보유자에게 릴리스 알림이 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="51fc4-168">If you release a custodian after a hold notice was published, a release notice will be sent to the custodian.</span></span> <span data-ttu-id="51fc4-169">또한 보유자와 연결된 데이터 원본에 배치된 보류도 모두 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="51fc4-169">Additionally, any holds placed on data sources that were associated with the custodian are removed.</span></span> <span data-ttu-id="51fc4-170">법적 보유 알림이 발급되지 않은 자동 보류를 설정한 경우, 릴리스 알림은 전송되지 않지만 해당 보유자에 연결된 데이터 원본에 대한 보류는 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="51fc4-170">If the custodian was placed on a *silent hold*, where they weren't issued any legal hold notifications, a release notice will not be sent but any holds placed on data sources that were associated with that custodian are removed.</span></span>

<span data-ttu-id="51fc4-171">양도인을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="51fc4-171">To release a custodian:</span></span> 

1. <span data-ttu-id="51fc4-172">Advanced  **eDiscovery를 > eDiscovery를 통해 eDiscovery로** 이동한 후 사례를 여는 것이 가장 까다로우며,</span><span class="sxs-lookup"><span data-stu-id="51fc4-172">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>

2. <span data-ttu-id="51fc4-173">원본 **탭을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="51fc4-173">Click the **Sources** tab.</span></span>

3. <span data-ttu-id="51fc4-174">**Custodians** 페이지에서 사례에서 릴리스되는 양도인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="51fc4-174">On the **Custodians** page, and then select the custodian who is being released from the case.</span></span>

4. <span data-ttu-id="51fc4-175">플라이아웃 페이지에서 **Custodian 릴리스를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="51fc4-175">On the flyout page, click **Release custodian**.</span></span>

   <span data-ttu-id="51fc4-176">보유자에 연결된 데이터 원본에 보류가 적용되면 보류가 제거되고 다른 Advanced eDiscovery 사례와 연결된 다른 모든 보류가 계속 적용됨을 설명하는 경고 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="51fc4-176">A warning page is displayed explaining that if a hold is placed on a data source associated with the custodian, the hold will be removed, and that any other hold associated with a different Advanced eDiscovery case will still apply.</span></span> <span data-ttu-id="51fc4-177">여기에는 다른 유형의 보존 및 보존 기능(예: Microsoft 365 보존 정책)이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="51fc4-177">That includes other types of preservation and retention features (such as a Microsoft 365 retention policy).</span></span>

5. <span data-ttu-id="51fc4-178">**예를** 클릭하여 양도인을 해제할지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51fc4-178">Click **Yes** to confirm that you want to release the custodian.</span></span> 

    <span data-ttu-id="51fc4-179">보유자 탭에서 이  사용자의 상태가 릴리스로 설정되어  있으며 플라이아웃 페이지의 보류 상태가 **False로 변경됩니다.** </span><span class="sxs-lookup"><span data-stu-id="51fc4-179">The status for this user on the **Custodians** tab is set to **Released** and the **Hold status** on the flyout page is changed to **False**.</span></span> 

> [!NOTE]
> <span data-ttu-id="51fc4-180">여러 법적 사건에 양도권이 동시에 관련될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51fc4-180">A custodian might be simultaneously involved in several legal cases.</span></span> <span data-ttu-id="51fc4-181">보유자도 사례에서 릴리스될 경우 다른 문제의 보류 및 알림은 영향을 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="51fc4-181">When a custodian is released from a case, the holds and notifications across other matters won't be impacted.</span></span>

## <a name="bulk-edit-custodians"></a><span data-ttu-id="51fc4-182">양도자 대량 편집</span><span class="sxs-lookup"><span data-stu-id="51fc4-182">Bulk-edit custodians</span></span>

<span data-ttu-id="51fc4-183">대량 편집기를 사용하여 동시에 여러 관리인을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51fc4-183">You can use the bulk editor to edit multiple custodians as the same time.</span></span> <span data-ttu-id="51fc4-184">이렇게하려면 양도자 탭에서 두 개 이상의 관리인을 선택하여 대량 편집기를 표시한 다음 작업 중 하나를 클릭합니다. </span><span class="sxs-lookup"><span data-stu-id="51fc4-184">To do this, just select two or more custodians on the **Custodians** tab to display the bulk editor and then click one of tasks.</span></span>

![여러 보호자 설정을 편집하는 플라이아웃 페이지](../media/AeDBulkEditCustodians.png)
