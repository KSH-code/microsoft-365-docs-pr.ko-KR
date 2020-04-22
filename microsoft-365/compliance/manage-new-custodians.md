---
title: Advanced eDiscovery 사례에서 custodians 관리
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
description: 고급 eDiscovery 사례에서 custodians를 관리 합니다.
ms.openlocfilehash: b497aef50c2bafd58e3b9cf8643a1ecc038520a4
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635898"
---
# <a name="manage-custodians-in-an-advanced-ediscovery-case"></a><span data-ttu-id="83169-103">Advanced eDiscovery 사례에서 custodians 관리</span><span class="sxs-lookup"><span data-stu-id="83169-103">Manage custodians in an Advanced eDiscovery case</span></span>

<span data-ttu-id="83169-104">Advanced eDiscovery의 Custodians 탭에는 사례에 추가 된 모든 Custodians의 목록이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83169-104">The Custodians tab in Advanced eDiscovery contains a list of all custodians that have been added to the case.</span></span> <span data-ttu-id="83169-105">Custodians를 사례에 추가 하 고 나면 각 custodian에 대 한 세부 정보는 Azure Active Directory에서 자동으로 수집 되며 고급 eDiscovery로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83169-105">After you add custodians to a case, details about each custodian are automatically collected from Azure Active Directory and are viewable in Advanced eDiscovery.</span></span>

![Custodians 관리](../media/CustodianDetails.PNG)

## <a name="view-custodian-details"></a><span data-ttu-id="83169-107">Custodian 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="83169-107">View custodian details</span></span>

<span data-ttu-id="83169-108">Custodian에 대 한 세부 정보를 보려면 **Custodians** 탭의 목록에서 custodian을 클릭 합니다. 플라이 아웃 페이지가 표시 되 고 custodian에 대 한 다음 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83169-108">To view the details about a custodian, click the custodian from the list on the **Custodians** tab. A flyout page is displayed and contains the following information about the custodian:</span></span>

- <span data-ttu-id="83169-109">연락처 정보</span><span class="sxs-lookup"><span data-stu-id="83169-109">Contact information</span></span>

  - <span data-ttu-id="83169-110">**표시 이름** -custodian 주소록에 표시 되는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="83169-110">**Display Name** - The name displayed in the address book for the custodian.</span></span> <span data-ttu-id="83169-111">일반적으로 custodian 이름, 중간 이니셜 및 성의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="83169-111">This is usually the combination of the custodian’s first name, middle initial, and last name.</span></span>
  
   - <span data-ttu-id="83169-112">**Mail/SMTP** -custodian의 기본 SMTP 주소 (예: brianj@contoso.onmicrosoft.com)입니다.</span><span class="sxs-lookup"><span data-stu-id="83169-112">**Mail/SMTP** - The primary SMTP address for the custodian, for example, brianj@contoso.onmicrosoft.com.</span></span> <span data-ttu-id="83169-113">Custodian의 UPN (사용자 계정 이름)도 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83169-113">The custodian's user principal name (UPN) is also listed.</span></span>

  - <span data-ttu-id="83169-114">**Title** -custodian의 직함입니다.</span><span class="sxs-lookup"><span data-stu-id="83169-114">**Title** - The custodian’s job title.</span></span>

  - <span data-ttu-id="83169-115">**부서** -custodian가 작동 하는 부서의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="83169-115">**Department** - The name for the department in which the custodian works.</span></span>

  - <span data-ttu-id="83169-116">**Manager** -custodian의 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="83169-116">**Manager** - The custodian’s manager.</span></span> <span data-ttu-id="83169-117">지정 된 관리자가이 custodian에 대 한 에스컬레이션 통신을 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="83169-117">The designated manager will receive any escalation communications for this custodian.</span></span>
  
- <span data-ttu-id="83169-118">위치 정보</span><span class="sxs-lookup"><span data-stu-id="83169-118">Location information</span></span>

  - <span data-ttu-id="83169-119">**구/** 군/시-custodian가 있는 구/군/시입니다.</span><span class="sxs-lookup"><span data-stu-id="83169-119">**City** - The city in which the custodian is located.</span></span>

  - <span data-ttu-id="83169-120">**State** -custodian 주소의 시/도입니다.</span><span class="sxs-lookup"><span data-stu-id="83169-120">**State** - The state or province in the custodian’s address.</span></span>

  - <span data-ttu-id="83169-121">**국가/지역** -custodian가 있는 국가/지역입니다.</span><span class="sxs-lookup"><span data-stu-id="83169-121">**Country/Region** - The country/region where the custodian is located.</span></span>

  - <span data-ttu-id="83169-122">**Office** -custodian의 비즈니스 장소에 있는 사무실 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="83169-122">**Office** - The office location in the custodian’s place of business.</span></span>

- <span data-ttu-id="83169-123">사례 정보</span><span class="sxs-lookup"><span data-stu-id="83169-123">Case information</span></span>

  - <span data-ttu-id="83169-124">**보류 상태** -custodian를 보류 했는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="83169-124">**Hold status** - Indicates if the custodian has been placed on hold.</span></span> 

  - <span data-ttu-id="83169-125">**통신 상태**: custodian에 보류 알림이 발급 되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="83169-125">**Communication status**: Indicates if the custodian has been issued a hold notice.</span></span> <span data-ttu-id="83169-126">Custodian에 알림이 발급 된 경우이 속성의 값이 **게시**됩니다.</span><span class="sxs-lookup"><span data-stu-id="83169-126">If the custodian has been issued a notice, this value of this property is **Published**.</span></span> <span data-ttu-id="83169-127">Custodian에 알림이 발급 되지 않은 경우 상태가 **게시 취소**됩니다.</span><span class="sxs-lookup"><span data-stu-id="83169-127">If the custodian has not been issued a notice, the status is **Un-published**.</span></span> 

  - <span data-ttu-id="83169-128">**Status** -사례 내에 있는 custodian의 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="83169-128">**Status** - The status of the custodian within the case.</span></span> <span data-ttu-id="83169-129">상태가 **활성** 이면 custodian가 사례에 포함 됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="83169-129">A status of **Active** indicates that the custodian is part of the case.</span></span> <span data-ttu-id="83169-130">Custodian가 사례에서 해제 되 면 상태가 ' **릴리즈됨**'으로 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83169-130">If a custodian is released from a case, the status is changed to **Released**.</span></span> 

- <span data-ttu-id="83169-131">데이터 원본 및 인덱싱 정보</span><span class="sxs-lookup"><span data-stu-id="83169-131">Data sources and indexing information</span></span>

    - <span data-ttu-id="83169-132">**데이터 원본** -custodian와 연결 된 데이터 원본 수와 유형 (사서함, 사이트 및 팀)을 표시 하며 사례에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83169-132">**Data sources** - Shows the count and type of data sources (mailboxes, sites, and Teams) that are associated with the custodian and are part of the case.</span></span>

    - <span data-ttu-id="83169-133">**인덱스 업데이트 시간** -고급 인덱싱 작업이 마지막으로 트리거된 시간 및 날짜를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="83169-133">**Index updated time** - Indicates the time and date for when the advanced indexing job was last triggered.</span></span> <span data-ttu-id="83169-134">이 속성은 고급 인덱싱 프로세스가 현재 진행 되 고 있는 경우에도 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83169-134">This property will also indicate when the advanced indexing process is currently in progress.</span></span>


## <a name="edit-a-custodian"></a><span data-ttu-id="83169-135">Custodian 편집</span><span class="sxs-lookup"><span data-stu-id="83169-135">Edit a custodian</span></span>

<span data-ttu-id="83169-136">사례가 진행 됨에 따라 해당 사례 & 특정 custodian 관련 된 추가 데이터 원본이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83169-136">As your case progresses, you may discover that there may be additional data sources relevant to a specific custodian & your case.</span></span> <span data-ttu-id="83169-137">다른 시나리오에서는 검토 되었으며 관련성이 없는 것으로 간주 되는 특정 데이터 원본을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83169-137">In other scenarios, you may want to remove certain data sources that have been reviewed and deemed as not relevant.</span></span>

<span data-ttu-id="83169-138">Custodian와 연결 된 데이터 원본을 업데이트 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="83169-138">To update the data sources that are associated with a custodian:</span></span>

1. <span data-ttu-id="83169-139">**Ediscovery > Advanced ediscovery** 로 이동 하 여 사례를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="83169-139">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>
  
2. <span data-ttu-id="83169-140">**Custodians** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="83169-140">Click the **Custodians** tab.</span></span>
  
3. <span data-ttu-id="83169-141">목록에서 custodian를 선택 하 고 플라이 아웃 페이지에서 **편집** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="83169-141">Select a custodian from the list and click **Edit** on the flyout page.</span></span>

    ![데이터 원본 편집](../media/EditCustodianDataSource.PNG)
  
4. <span data-ttu-id="83169-143">**데이터 원본 선택** 탭을 클릭 하 여 Custodian의 Exchange 사서함 및 OneDrive 계정에 대 한 설정을 변경 하 고 **데이터 원본 선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="83169-143">Click **Choose data sources** tab to change the settings for the custodian's Exchange mailbox and OneDrive account, click **Choose data sources**.</span></span>
  
5. <span data-ttu-id="83169-144">**추가 데이터 원본 선택** 탭을 클릭 하 여 custodian에 연결 된 팀, SharePoint 또는 Exchange 사서함을 추가 하거나 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="83169-144">Click the **Select additional data sources** tab to add or remove Teams, SharePoint, or Exchange mailboxes associated with the custodian.</span></span> 

    <span data-ttu-id="83169-145">Custodian와 연결 된 데이터 원본에 대 한 자세한 내용은 [Add custodians](add-custodians-to-case.md#step-3-associate-additional-data-sources-to-a-custodian)in a custodian에서 "3 단계: 추가 데이터 원본을 a에 연결 합니다."를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="83169-145">For more information about data sources associated with a custodian, see "Step 3: Associate additional data sources to a custodian" in [Add custodians to a case](add-custodians-to-case.md#step-3-associate-additional-data-sources-to-a-custodian).</span></span> 
  
6. <span data-ttu-id="83169-146">Custodian에 대해 보류를 사용 하거나 사용 하지 않도록 설정 하려면 **custodial 보존** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="83169-146">Click **Place custodial holds** to enable or disable the hold for the custodian.</span></span>

## <a name="re-index-custodian-data"></a><span data-ttu-id="83169-147">Custodian 데이터 다시 인덱싱</span><span class="sxs-lookup"><span data-stu-id="83169-147">Re-index custodian data</span></span>

<span data-ttu-id="83169-148">법적 조사를 위한 대부분의 eDiscovery 워크플로에서 custodian가 법적 사례에 추가 된 후 custodian 데이터의 하위 집합을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="83169-148">In most eDiscovery workflows for legal investigations, a subset of a custodian's data is searched after the custodian is added to a legal case.</span></span> <span data-ttu-id="83169-149">파일 크기나 데이터 손상 가능성이 매우 크므로 custodian과 연결 된 데이터 원본에 있는 일부 항목을 부분적으로 인덱싱할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83169-149">Because of very large file sizes or possible data corruption, some items in the data sources associated with a custodian may be partially indexed.</span></span> <span data-ttu-id="83169-150">고급 eDiscovery의 [고급 인덱싱](indexing-custodian-data.md) 기능을 사용 하는 경우에는 이러한 항목을 요청 시 다시 인덱싱하여 대부분의 부분적으로 인덱싱된 항목을 자동으로 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83169-150">Using the [advanced indexing](indexing-custodian-data.md) capability in the Advanced eDiscovery, most partially indexed items can be automatically remediated by re-indexing these items on demand.</span></span>

<span data-ttu-id="83169-151">Custodian가 사례에 추가 되 면 custodian와 연결 된 데이터 원본에 있는 데이터는 고급 인덱싱 프로세스에 의해 자동으로 다시 인덱싱됩니다.</span><span class="sxs-lookup"><span data-stu-id="83169-151">When a custodian is added to a case, the data located in the data sources associated with the custodian is automatically re-indexed (by the advanced indexing process).</span></span> <span data-ttu-id="83169-152">즉, 데이터를 다운로드 하 여 수정 하 고 오프 라인으로 검색할 필요 없이 전체 위치에 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83169-152">This means you can leave the data in-place instead of having to download and remediate it and then search it offline).</span></span> <span data-ttu-id="83169-153">그러나 법적 사례의 수명 주기 중 새 데이터 원본은 custodian와 연결 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83169-153">However, during the lifecycle of a legal case new data sources might be associated with a custodian.</span></span> <span data-ttu-id="83169-154">이 경우에는 고급 인덱싱 프로세스를 다시 실행 하 여 custodian의 데이터를 다시 인덱싱하여 부분적으로 인덱싱된 항목을 수정 하 고 custodian의 데이터에 대 한 인덱스를 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83169-154">In this case, you can re-index the custodian's data by re-running the advanced indexing process to remediate any partially indexed items and update the index for the custodian's data.</span></span>

<span data-ttu-id="83169-155">재 인덱싱 프로세스를 트리거하여 부분적으로 인덱싱된 항목을 처리 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="83169-155">To trigger the re-indexing process to address partially indexed items:</span></span>

1. <span data-ttu-id="83169-156">**Ediscovery > Advanced ediscovery** 로 이동 하 여 사례를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="83169-156">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>

2. <span data-ttu-id="83169-157">**Custodians 탭**을 클릭 한 다음 데이터를 reindexed 해야 하는 custodian을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="83169-157">Click to **Custodians tab**, and then select a custodian whose data must be reindexed.</span></span> 

3. <span data-ttu-id="83169-158">플라이 아웃 페이지에서 **인덱스 업데이트**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="83169-158">On the flyout page, click **Update index**.</span></span>

   <span data-ttu-id="83169-159">인덱스 작업을 만들었기를 알리는 대화 상자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83169-159">A dialog is displayed saying the index job has been created.</span></span>

<span data-ttu-id="83169-160">Custodian 데이터를 다시 인덱싱하려면 장기 실행 프로세스입니다. 만들어진 해당 작업을 **custodian 데이터 다시 인덱싱**이라는 이름이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83169-160">Re-indexing custodian data is a long-running process; the corresponding job that's created is named **Re-indexing custodian data**.</span></span> <span data-ttu-id="83169-161">**인덱싱 작업 상태** 열에서 상태를 모니터링 하 여 **작업** 탭 이나 **Custodians** 탭의 진행 상황을 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83169-161">You can track the progress on the **Jobs** tab or on the **Custodians** tab by monitoring the status in the **Indexing job status** column.</span></span>

<span data-ttu-id="83169-162">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="83169-162">For more information, see:</span></span>

- [<span data-ttu-id="83169-163">오류 처리 작업</span><span class="sxs-lookup"><span data-stu-id="83169-163">Work with processing errors</span></span>](processing-data-for-case.md)

- [<span data-ttu-id="83169-164">작업 관리</span><span class="sxs-lookup"><span data-stu-id="83169-164">Manage jobs</span></span>](managing-jobs-ediscovery20.md)

## <a name="release-a-custodian-from-a-case"></a><span data-ttu-id="83169-165">사례에서 custodian 릴리스</span><span class="sxs-lookup"><span data-stu-id="83169-165">Release a custodian from a case</span></span>

<span data-ttu-id="83169-166">사례가 마감 되거나, custodian가 사례에 대 한 콘텐츠를 보존 하기 위해 더 이상 의무를 받지 않거나, custodian이 사례와 더 이상 관련이 없는 것으로 간주 되는 경우에 custodian이 릴리스됩니다.</span><span class="sxs-lookup"><span data-stu-id="83169-166">A custodian is released in situations where a case is closed, the custodian is no longer under obligation to preserve content for a case, or when the custodian is deemed to no longer be relevant to the case.</span></span> 

<span data-ttu-id="83169-167">보존 공지가 게시 된 후에 custodian를 해제 하면 릴리스 알림이 custodian로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83169-167">If you release a custodian after a hold notice was published, a release notice will be sent to the custodian.</span></span> <span data-ttu-id="83169-168">또한 custodian와 연결 된 데이터 원본에 대해 저장 된 모든 보류는 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83169-168">Additionally, any holds placed on data sources that were associated with the custodian are removed.</span></span> <span data-ttu-id="83169-169">Custodian이 *자동 보존 상태로*설정 되 면 법적 보존 알림이 실행 되지 않은 경우 릴리스 알림이 전송 되지 않지만 해당 custodian와 연결 된 데이터 원본에 적용 되는 모든 보류는 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83169-169">If the custodian was placed on a *silent hold*, where they weren't issued any legal hold notifications, a release notice will not be sent but any holds placed on data sources that were associated with that custodian are removed.</span></span>

<span data-ttu-id="83169-170">Custodian를 해제 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="83169-170">To release a custodian:</span></span> 

1. <span data-ttu-id="83169-171">**Ediscovery > Advanced ediscovery** 로 이동 하 여 사례를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="83169-171">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>

2.  <span data-ttu-id="83169-172">**Custodians** 탭으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="83169-172">Go to the **Custodians** tab.</span></span>

3.  <span data-ttu-id="83169-173">**Custodians 탭**을 클릭 한 다음 사례에서 출시 되는 custodian을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="83169-173">Click to **Custodians tab**, and then select the custodian who is being released from the case.</span></span>

4. <span data-ttu-id="83169-174">플라이 아웃 페이지에서 **Custodian 릴리스**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="83169-174">On the flyout page, click **Release custodian**.</span></span>

   <span data-ttu-id="83169-175">Custodian과 연결 된 데이터 원본에 보류가 설정 되 고 보류가 제거 되 고 다른 고급 eDiscovery 사례와 관련 된 다른 보류에도 적용 되는 경우를 설명 하는 경고 페이지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83169-175">A warning page is displayed explaining that if a hold is placed on a data source associated with the custodian, the hold will be removed, and that any other hold associated with a different Advanced eDiscovery case will still apply.</span></span> <span data-ttu-id="83169-176">여기에는 기타 유형의 보존 및 보존 기능 (예: Microsoft 365 보존 정책)이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83169-176">That includes other types of preservation and retention features (such as a Microsoft 365 retention policy).</span></span>

5. <span data-ttu-id="83169-177">**예** 를 클릭 하 여 custodian 릴리스를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="83169-177">Click **Yes** to confirm that you want to release the custodian.</span></span> 

    <span data-ttu-id="83169-178">**Custodians** 탭에서이 사용자의 상태는 **릴리즈됨** 으로 설정 되 고 플라이 아웃 페이지의 **보류 상태** 는 **False**로 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83169-178">The status for this user on the **Custodians** tab is set to **Released** and the **Hold status** on the flyout page is changed to **False**.</span></span> 

> [!NOTE]
> <span data-ttu-id="83169-179">Custodian는 몇 가지 법적 사례와 동시에 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83169-179">A custodian might be simultaneously involved in several legal cases.</span></span> <span data-ttu-id="83169-180">Custodian가 사례에서 해제 되 면 다른 중요 한 보존 및 알림에는 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83169-180">When a custodian is released from a case, the holds and notifications across other matters won't be impacted.</span></span>

## <a name="bulk-edit-custodians"></a><span data-ttu-id="83169-181">Custodians 대량 편집</span><span class="sxs-lookup"><span data-stu-id="83169-181">Bulk-edit custodians</span></span>

<span data-ttu-id="83169-182">대량 편집기를 사용 하 여 여러 custodians을 동시에 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83169-182">You can use the bulk editor to edit multiple custodians as the same time.</span></span> <span data-ttu-id="83169-183">이 작업을 수행 하려면 **custodians** 탭에서 custodians를 두 개 이상 선택 하 여 벌크 편집기를 표시 한 다음 작업 중 하나를 클릭 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83169-183">To do this, just select two or more custodians on the **Custodians** tab to display the bulk editor and then click one of tasks.</span></span>

![여러 custodians 설정을 편집 하기 위한 플라이 아웃 페이지](../media/AeDBulkEditCustodians.png)
