---
title: 관리 사례에서 Advanced eDiscovery 관리
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
description: 사례에서 세부 정보를 보고, 편집하고, 대량으로 편집하는 방법을 Advanced eDiscovery.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a1e9e9d481073c8bb2827d5d65537dbf2b63ef1f
ms.sourcegitcommit: 555b200b618085706dabf8648d27fb6d6427cfce
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/30/2020
ms.locfileid: "49739871"
---
# <a name="manage-custodians-in-an-advanced-ediscovery-case"></a><span data-ttu-id="916d7-103">관리 사례에서 Advanced eDiscovery 관리</span><span class="sxs-lookup"><span data-stu-id="916d7-103">Manage custodians in an Advanced eDiscovery case</span></span>

<span data-ttu-id="916d7-104">Advanced eDiscovery 사례의 원본 탭에  있는 Custodians 페이지에는 사례에 추가된 모든 정보 근로자 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="916d7-104">The Custodians page on the **Sources** tab in an Advanced eDiscovery case contains a list of all custodians that have been added to the case.</span></span> <span data-ttu-id="916d7-105">사례에 보아를 추가하고 나면 각 보위부에 대한 세부 정보가 Azure Active Directory 자동으로 수집되며 Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="916d7-105">After you add custodians to a case, details about each custodian are automatically collected from Azure Active Directory and are viewable in Advanced eDiscovery.</span></span>

![Custodians 관리](../media/CustodianDetails.PNG)

## <a name="view-custodian-details"></a><span data-ttu-id="916d7-107">보아도 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="916d7-107">View custodian details</span></span>

<span data-ttu-id="916d7-108">수장에 대한 세부 정보를 보려면 Custodians 탭의 목록에서 **custodian을** 클릭합니다. 플라이아웃 페이지가 표시되고 보호자에 대한 다음 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="916d7-108">To view the details about a custodian, click the custodian from the list on the **Custodians** tab. A flyout page is displayed and contains the following information about the custodian:</span></span>

- <span data-ttu-id="916d7-109">연락처 정보</span><span class="sxs-lookup"><span data-stu-id="916d7-109">Contact information</span></span>

  - <span data-ttu-id="916d7-110">**표시 이름** - 보스니아어의 주소부에 표시되는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="916d7-110">**Display Name** - The name displayed in the address book for the custodian.</span></span> <span data-ttu-id="916d7-111">일반적으로 이 이름은 보아의 이름, 중간 이니셜 및 성의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="916d7-111">This is usually the combination of the custodian's first name, middle initial, and last name.</span></span>
  
   - <span data-ttu-id="916d7-112">**메일/SMTP** - 예를 들어, brianj@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="916d7-112">**Mail/SMTP** - The primary SMTP address for the custodian, for example, brianj@contoso.onmicrosoft.com.</span></span> <span data-ttu-id="916d7-113">또한 해당 사용자의 UPN(사용자 계정 이름)도 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="916d7-113">The custodian's user principal name (UPN) is also listed.</span></span>

  - <span data-ttu-id="916d7-114">**Title** - 보아의 직위입니다.</span><span class="sxs-lookup"><span data-stu-id="916d7-114">**Title** - The custodian's job title.</span></span>

  - <span data-ttu-id="916d7-115">**Department** - 보위부가 작업하는 부서의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="916d7-115">**Department** - The name for the department in which the custodian works.</span></span>

  - <span data-ttu-id="916d7-116">**Manager** - 관리자.</span><span class="sxs-lookup"><span data-stu-id="916d7-116">**Manager** - The custodian's manager.</span></span> <span data-ttu-id="916d7-117">지정된 관리자는 이 관리자에 대한 에스컬레이터 통신을 받게됩니다.</span><span class="sxs-lookup"><span data-stu-id="916d7-117">The designated manager will receive any escalation communications for this custodian.</span></span>
  
- <span data-ttu-id="916d7-118">위치 정보</span><span class="sxs-lookup"><span data-stu-id="916d7-118">Location information</span></span>

  - <span data-ttu-id="916d7-119">**City** - 보위부가 있는 도시입니다.</span><span class="sxs-lookup"><span data-stu-id="916d7-119">**City** - The city in which the custodian is located.</span></span>

  - <span data-ttu-id="916d7-120">**State** - 보전원 주소의 시 또는 도입니다.</span><span class="sxs-lookup"><span data-stu-id="916d7-120">**State** - The state or province in the custodian's address.</span></span>

  - <span data-ttu-id="916d7-121">**국가/지역** - 보위부가 있는 국가/지역입니다.</span><span class="sxs-lookup"><span data-stu-id="916d7-121">**Country/Region** - The country/region where the custodian is located.</span></span>

  - <span data-ttu-id="916d7-122">**Office** - 보직원의 업무 장소에 있는 사무실 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="916d7-122">**Office** - The office location in the custodian's place of business.</span></span>

- <span data-ttu-id="916d7-123">케이스 정보</span><span class="sxs-lookup"><span data-stu-id="916d7-123">Case information</span></span>

  - <span data-ttu-id="916d7-124">**보류 상태** - 보유자에 대한 보류 상태 표시</span><span class="sxs-lookup"><span data-stu-id="916d7-124">**Hold status** - Indicates if the custodian has been placed on hold.</span></span> 

  - <span data-ttu-id="916d7-125">**통신 상태:** 보유자에 대한 보류 알림이 발행된 경우를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="916d7-125">**Communication status**: Indicates if the custodian has been issued a hold notice.</span></span> <span data-ttu-id="916d7-126">보호자에 알림이 발행된 경우 이 속성의 이 값은 **Published입니다.**</span><span class="sxs-lookup"><span data-stu-id="916d7-126">If the custodian has been issued a notice, this value of this property is **Published**.</span></span> <span data-ttu-id="916d7-127">보지 않은 경우 상태는 **게시되지 않은 입니다.**</span><span class="sxs-lookup"><span data-stu-id="916d7-127">If the custodian has not been issued a notice, the status is **Un-published**.</span></span> 

  - <span data-ttu-id="916d7-128">**Status** - 사례 내의 보위자 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="916d7-128">**Status** - The status of the custodian within the case.</span></span> <span data-ttu-id="916d7-129">Active **상태는** 해당 보위부가 사례의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="916d7-129">A status of **Active** indicates that the custodian is part of the case.</span></span> <span data-ttu-id="916d7-130">사례에서 custodian이 릴리스된 경우 상태는 릴리스 로 **변경됩니다.**</span><span class="sxs-lookup"><span data-stu-id="916d7-130">If a custodian is released from a case, the status is changed to **Released**.</span></span> 

- <span data-ttu-id="916d7-131">데이터 원본 및 인덱싱 정보</span><span class="sxs-lookup"><span data-stu-id="916d7-131">Data sources and indexing information</span></span>

    - <span data-ttu-id="916d7-132">**데이터 원본** - 보호자와 연결되어 있으며 사례에 속하는 데이터 원본(사서함Teams 사이트 및 데이터 원본)의 수와 유형을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="916d7-132">**Data sources** - Shows the count and type of data sources (mailboxes, sites, and Teams) that are associated with the custodian and are part of the case.</span></span>

    - <span data-ttu-id="916d7-133">**인덱스 업데이트 시간** - 고급 인덱싱 작업이 마지막으로 트리거된 시간 및 날짜를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="916d7-133">**Index updated time** - Indicates the time and date for when the advanced indexing job was last triggered.</span></span> <span data-ttu-id="916d7-134">이 속성은 고급 인덱싱 프로세스가 현재 진행 중인 경우도 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="916d7-134">This property will also indicate when the advanced indexing process is currently in progress.</span></span>


## <a name="edit-a-custodian"></a><span data-ttu-id="916d7-135">수정자 편집</span><span class="sxs-lookup"><span data-stu-id="916d7-135">Edit a custodian</span></span>

<span data-ttu-id="916d7-136">사례가 진행될 때 사례와 관련된 추가 데이터 원본이 있을 & 있습니다.</span><span class="sxs-lookup"><span data-stu-id="916d7-136">As your case progresses, you may discover that there may be additional data sources relevant to a specific custodian & your case.</span></span> <span data-ttu-id="916d7-137">다른 시나리오에서는 검토되고 관련이 없는 것으로 확인된 특정 데이터 원본을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="916d7-137">In other scenarios, you may want to remove certain data sources that have been reviewed and deemed as not relevant.</span></span>

<span data-ttu-id="916d7-138">보호자와 연결된 데이터 원본을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="916d7-138">To update the data sources that are associated with a custodian:</span></span>

1. <span data-ttu-id="916d7-139">**eDiscovery > Advanced eDiscovery** 사례를 여는 것이 가장 까다로입니다.</span><span class="sxs-lookup"><span data-stu-id="916d7-139">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>
  
2. <span data-ttu-id="916d7-140">원본 **탭을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="916d7-140">Click the **Sources** tab.</span></span>
  
3. <span data-ttu-id="916d7-141">**Custodians** 페이지에서 목록에서 Custodian를 선택하고 플라이아웃 페이지에서 편집을 클릭합니다. </span><span class="sxs-lookup"><span data-stu-id="916d7-141">On the **Custodians** page, select a custodian from the list and click **Edit** on the flyout page.</span></span>

    ![데이터 원본 편집](../media/EditCustodianDataSource.PNG)
  
4. <span data-ttu-id="916d7-143">데이터 **원본** 선택 탭을 클릭하여 보호자 사서함 및 Exchange 계정의 설정을 변경하고 OneDrive 원본 **선택을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="916d7-143">Click **Choose data sources** tab to change the settings for the custodian's Exchange mailbox and OneDrive account, click **Choose data sources**.</span></span>
  
5. <span data-ttu-id="916d7-144">추가 **데이터** 원본 선택 탭을 클릭하여 Teams, SharePoint 또는 Exchange 사서함을 추가하거나 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="916d7-144">Click the **Select additional data sources** tab to add or remove Teams, SharePoint, or Exchange mailboxes associated with the custodian.</span></span> 

    <span data-ttu-id="916d7-145">보호자와 연결된 데이터 원본에 대한 자세한 내용은 [사례에 custodians](add-custodians-to-case.md)추가를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="916d7-145">For more information about data sources associated with a custodian, see [Add custodians to a case](add-custodians-to-case.md).</span></span> 
  
6. <span data-ttu-id="916d7-146">**보유자에** 대한 보류를 활성화 또는 비활성화하려면 보유 보류를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="916d7-146">Click **Place custodial holds** to enable or disable the hold for the custodian.</span></span>

## <a name="re-index-custodian-data"></a><span data-ttu-id="916d7-147">Custodian 데이터 다시 인덱싱</span><span class="sxs-lookup"><span data-stu-id="916d7-147">Re-index custodian data</span></span>

<span data-ttu-id="916d7-148">법적 조사를 위한 대부분의 eDiscovery 워크플로에서는 법적 사례에 보호자 데이터가 추가된 후 보호자 데이터의 하위 집합을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="916d7-148">In most eDiscovery workflows for legal investigations, a subset of a custodian's data is searched after the custodian is added to a legal case.</span></span> <span data-ttu-id="916d7-149">파일 크기가 매우 크거나 데이터가 손상될 수 있기 때문에, 보호자에 연결된 데이터 원본의 일부 항목이 부분적으로 인덱싱될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="916d7-149">Because of very large file sizes or possible data corruption, some items in the data sources associated with a custodian may be partially indexed.</span></span> <span data-ttu-id="916d7-150">[인덱싱 기능의 고급](indexing-custodian-data.md) 인덱싱 기능을 Advanced eDiscovery 부분적으로 인덱싱된 항목은 대부분 이러한 항목을 요구 시 다시 인덱싱하여 자동으로 수정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="916d7-150">Using the [advanced indexing](indexing-custodian-data.md) capability in the Advanced eDiscovery, most partially indexed items can be automatically remediated by re-indexing these items on demand.</span></span>

<span data-ttu-id="916d7-151">보안 주가 사례에 추가될 때, 고급 인덱싱 프로세스에 의해, 보호자와 연결된 데이터 원본에 있는 데이터가 자동으로 다시 인덱싱됩니다.</span><span class="sxs-lookup"><span data-stu-id="916d7-151">When a custodian is added to a case, the data located in the data sources associated with the custodian is automatically re-indexed (by the advanced indexing process).</span></span> <span data-ttu-id="916d7-152">즉, 데이터를 다운로드하여 수정한 다음 오프라인으로 검색하는 대신 데이터를 현재 상태로 두면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="916d7-152">This means you can leave the data in-place instead of having to download and remediate it and then search it offline).</span></span> <span data-ttu-id="916d7-153">그러나 법률 사례의 수명 주기 동안 새 데이터 원본이 보호자와 연결될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="916d7-153">However, during the lifecycle of a legal case new data sources might be associated with a custodian.</span></span> <span data-ttu-id="916d7-154">이 경우 고급 인덱싱 프로세스를 다시 실행하여 부분적으로 인덱싱된 항목을 수정하고 관리자 데이터에 대한 인덱스를 업데이트하여 보호자 데이터를 다시 인덱싱할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="916d7-154">In this case, you can re-index the custodian's data by re-running the advanced indexing process to remediate any partially indexed items and update the index for the custodian's data.</span></span>

<span data-ttu-id="916d7-155">부분적으로 인덱싱된 항목을 처리하기 위해 다시 인덱싱 프로세스를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="916d7-155">To trigger the re-indexing process to address partially indexed items:</span></span>

1. <span data-ttu-id="916d7-156">**eDiscovery > Advanced eDiscovery** 사례를 여는 것이 가장 까다로입니다.</span><span class="sxs-lookup"><span data-stu-id="916d7-156">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>

2. <span data-ttu-id="916d7-157">원본 **탭을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="916d7-157">Click the **Sources** tab.</span></span>

3. <span data-ttu-id="916d7-158">**Custodians 페이지에서** 데이터를 다시 인덱서해야 하는 보호자(custodian)를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="916d7-158">On the **Custodians** page, select a custodian whose data must be reindexed.</span></span>

4. <span data-ttu-id="916d7-159">플라이아웃 페이지에서 인덱스 **업데이트를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="916d7-159">On the flyout page, click **Update index**.</span></span>

   <span data-ttu-id="916d7-160">인덱스 작업이 만들어졌다는 대화 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="916d7-160">A dialog is displayed saying the index job has been created.</span></span>

<span data-ttu-id="916d7-161">보호자 데이터를 다시 인덱싱하는 과정은 오래 지속됩니다. 생성된 해당 작업의 이름은 다시 인덱싱 **custodian 데이터입니다.**</span><span class="sxs-lookup"><span data-stu-id="916d7-161">Re-indexing custodian data is a long-running process; the corresponding job that's created is named **Re-indexing custodian data**.</span></span> <span data-ttu-id="916d7-162">인덱싱 작업 상태  열의 상태를  모니터링하여 작업 탭 또는 관리 탭에서 진행 상황을 추적할 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="916d7-162">You can track the progress on the **Jobs** tab or on the **Custodians** tab by monitoring the status in the **Indexing job status** column.</span></span>

<span data-ttu-id="916d7-163">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="916d7-163">For more information, see:</span></span>

- [<span data-ttu-id="916d7-164">오류 처리 작업</span><span class="sxs-lookup"><span data-stu-id="916d7-164">Work with processing errors</span></span>](processing-data-for-case.md)

- [<span data-ttu-id="916d7-165">작업 관리</span><span class="sxs-lookup"><span data-stu-id="916d7-165">Manage jobs</span></span>](managing-jobs-ediscovery20.md)

## <a name="release-a-custodian-from-a-case"></a><span data-ttu-id="916d7-166">사례에서 custodian 릴리스</span><span class="sxs-lookup"><span data-stu-id="916d7-166">Release a custodian from a case</span></span>

<span data-ttu-id="916d7-167">양도인은 사례가 마감되거나, 양도인이 더 이상 사례에 대한 콘텐츠를 보존할 의무가 없는 경우 또는 해당 사례와 더 이상 관련이 없는 것으로 판단되는 경우에 릴리스됩니다.</span><span class="sxs-lookup"><span data-stu-id="916d7-167">A custodian is released in situations where a case is closed, the custodian is no longer under obligation to preserve content for a case, or when the custodian is deemed to no longer be relevant to the case.</span></span> 

<span data-ttu-id="916d7-168">보류 알림이 게시된 후 보유자 해제 시 릴리스 알림이 보유자에게 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="916d7-168">If you release a custodian after a hold notice was published, a release notice will be sent to the custodian.</span></span> <span data-ttu-id="916d7-169">또한 보유자와 연결된 데이터 원본에 배치된 보류도 모두 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="916d7-169">Additionally, any holds placed on data sources that were associated with the custodian are removed.</span></span> <span data-ttu-id="916d7-170">법적 보유 알림을 발급하지 않은 자동 보류를 설정한 경우, 릴리스 알림은 전송되지 않지만 해당 보유자와 연결된 데이터 원본에 대한 보류는 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="916d7-170">If the custodian was placed on a *silent hold*, where they weren't issued any legal hold notifications, a release notice will not be sent but any holds placed on data sources that were associated with that custodian are removed.</span></span>

<span data-ttu-id="916d7-171">보전을 해제하는 경우:</span><span class="sxs-lookup"><span data-stu-id="916d7-171">To release a custodian:</span></span> 

1. <span data-ttu-id="916d7-172">**eDiscovery > Advanced eDiscovery** 사례를 여는 것이 가장 까다로입니다.</span><span class="sxs-lookup"><span data-stu-id="916d7-172">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>

2. <span data-ttu-id="916d7-173">원본 **탭을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="916d7-173">Click the **Sources** tab.</span></span>

3. <span data-ttu-id="916d7-174">**Custodians** 페이지에서 사례에서 릴리스되는 양부인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="916d7-174">On the **Custodians** page, and then select the custodian who is being released from the case.</span></span>

4. <span data-ttu-id="916d7-175">플라이아웃 페이지에서 **Custodian 릴리스를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="916d7-175">On the flyout page, click **Release custodian**.</span></span>

   <span data-ttu-id="916d7-176">보유자에 연결된 데이터 원본에 보류가 적용되면 보류가 제거되고 다른 Advanced eDiscovery 사례와 연결된 다른 모든 보류가 계속 적용됨을 설명하는 경고 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="916d7-176">A warning page is displayed explaining that if a hold is placed on a data source associated with the custodian, the hold will be removed, and that any other hold associated with a different Advanced eDiscovery case will still apply.</span></span> <span data-ttu-id="916d7-177">여기에는 보존 정책과 같은 다른 유형의 보존 Microsoft 365 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="916d7-177">That includes other types of preservation and retention features (such as a Microsoft 365 retention policy).</span></span>

5. <span data-ttu-id="916d7-178">예를 **클릭하여** custodian를 해제할지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="916d7-178">Click **Yes** to confirm that you want to release the custodian.</span></span> 

    <span data-ttu-id="916d7-179">보유자 탭에서 이  사용자의 상태가 릴리스로 설정되어  있으며 플라이아웃 페이지의 보류 상태가 **False로 변경됩니다.** </span><span class="sxs-lookup"><span data-stu-id="916d7-179">The status for this user on the **Custodians** tab is set to **Released** and the **Hold status** on the flyout page is changed to **False**.</span></span> 

> [!NOTE]
> <span data-ttu-id="916d7-180">여러 법률 사례에서 보호자도 동시에 관련될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="916d7-180">A custodian might be simultaneously involved in several legal cases.</span></span> <span data-ttu-id="916d7-181">보유자도 사례에서 릴리스된 경우 다른 문제의 보류 및 알림은 영향을 드리지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="916d7-181">When a custodian is released from a case, the holds and notifications across other matters won't be impacted.</span></span>

## <a name="bulk-edit-custodians"></a><span data-ttu-id="916d7-182">보전자 대량 편집</span><span class="sxs-lookup"><span data-stu-id="916d7-182">Bulk-edit custodians</span></span>

<span data-ttu-id="916d7-183">대량 편집기를 사용하여 동시에 여러 관리인을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="916d7-183">You can use the bulk editor to edit multiple custodians as the same time.</span></span> <span data-ttu-id="916d7-184">이렇게하려면 관리 탭에서 두 개 이상의 관리인을  선택하여 대량 편집기를 표시한 다음 작업 중 하나를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="916d7-184">To do this, just select two or more custodians on the **Custodians** tab to display the bulk editor and then click one of tasks.</span></span>

![여러 보호자 설정을 편집하는 플라이아웃 페이지](../media/AeDBulkEditCustodians.png)
