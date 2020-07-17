---
title: 고급 eDiscovery 사례에 custodians 대량 추가
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
ROBOTS: NOINDEX, NOFOLLOW
description: 대량 추가 도구를 사용 하면 고급 eDiscovery에서 여러 custodians 및 연결 된 데이터 원본을 사례에 빠르게 추가할 수 있습니다.
ms.openlocfilehash: ab9626be01814fa95a959141433b431df9bf7724
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024668"
---
# <a name="bulk-add-custodians-to-an-advanced-ediscovery-case"></a><span data-ttu-id="488b7-103">고급 eDiscovery 사례에 custodians 대량 추가</span><span class="sxs-lookup"><span data-stu-id="488b7-103">Bulk-add custodians to an Advanced eDiscovery case</span></span>

<span data-ttu-id="488b7-104">많은 수의 custodians 포함 된 고급 eDiscovery 사례의 경우 여러 custodians를 사례에 추가 하는 데 필요한 모든 정보를 포함 하는 CSV 파일을 한 번에 가져올 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="488b7-104">For Advanced eDiscovery cases that involve a lot of custodians, you can import multiple custodians at once by a CSV file that contains all the information necessary to add them to a case.</span></span>

## <a name="bulk-add-custodians"></a><span data-ttu-id="488b7-105">대량 추가 custodians</span><span class="sxs-lookup"><span data-stu-id="488b7-105">Bulk-add custodians</span></span>

1. <span data-ttu-id="488b7-106">사례를 입력 하 고 **원본** 탭으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="488b7-106">Enter case and navigate to the **Sources** tab.</span></span>

2. <span data-ttu-id="488b7-107">**가져오기 custodians** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="488b7-107">Click **Import custodians**</span></span>

3. <span data-ttu-id="488b7-108">플라이 아웃 페이지에서 **빈 서식 파일 다운로드** 를 클릭 하 여 CSV custodian 서식 파일을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="488b7-108">On the flyout page, click **Download a blank template** to download a CSV custodian template file.</span></span>

4. <span data-ttu-id="488b7-109">CSV 파일에 custodial 정보를 추가 하 고 로컬 컴퓨터에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="488b7-109">Add the custodial information to the CSV file and save it on your local computer.</span></span> <span data-ttu-id="488b7-110">CSV 파일의 속성에 대 한 자세한 내용은 다음 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="488b7-110">See the next section for information about the properties in the CSV file.</span></span>

5. <span data-ttu-id="488b7-111">**원본** 탭에서 **Custodians 가져오기를** 다시 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="488b7-111">On the **Sources** tab, click **Import Custodians** again.</span></span>

6. <span data-ttu-id="488b7-112">플라이 아웃 페이지에서 **찾아보기를** 클릭 하 고 CSV 파일을 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="488b7-112">On flyout page, click **Browse** and the upload your CSV file.</span></span>

   <span data-ttu-id="488b7-113">CSV 파일이 업로드 된 후에는 BulkAddCustodian 작업이 만들어지고 **작업** 탭에 표시 됩니다. 이 작업은 custodians의 해당 하는 데이터 원본에 대 한 유효성을 검사 한 다음 케이스의 **원본** 페이지에 있는 **custodians** 탭에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="488b7-113">After the CSV file is uploaded, a BulkAddCustodian job is created and displayed on the **Jobs** tab. The job validates the custodians and their corresponding data sources and then adds them to the **Custodians** tab on the **Sources** page of the case.</span></span>

## <a name="custodian-csv-file"></a><span data-ttu-id="488b7-114">Custodian CSV 파일</span><span class="sxs-lookup"><span data-stu-id="488b7-114">Custodian CSV file</span></span>

<span data-ttu-id="488b7-115">CSV 서식 파일을 다운로드 한 후에는 각 행에 custodians 및 해당 데이터 원본을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="488b7-115">After you download the CSV template, you can add custodians and their data source in each row.</span></span> <span data-ttu-id="488b7-116">머리글 행의 열 이름은 변경 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="488b7-116">Be sure not to change the column names in the header row.</span></span>

| <span data-ttu-id="488b7-117">열 이름</span><span class="sxs-lookup"><span data-stu-id="488b7-117">Column name</span></span>|<span data-ttu-id="488b7-118">설명</span><span class="sxs-lookup"><span data-stu-id="488b7-118">Description</span></span>|
|:------- |:------------------------------------------------------------|
|<span data-ttu-id="488b7-119">**Custodian ContactEmail**</span><span class="sxs-lookup"><span data-stu-id="488b7-119">**Custodian ContactEmail**</span></span>     | <span data-ttu-id="488b7-120">Custodian의 UPN 전자 메일입니다.</span><span class="sxs-lookup"><span data-stu-id="488b7-120">UPN email of custodian.</span></span> <span data-ttu-id="488b7-121">예: sarad@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="488b7-121">Example: sarad@onmicrosoft.contoso.com</span></span>           |
|<span data-ttu-id="488b7-122">**Exchange 사용**</span><span class="sxs-lookup"><span data-stu-id="488b7-122">**Exchange Enabled**</span></span> | <span data-ttu-id="488b7-123">Custodian의 사서함을 추가할지 여부에 대 한 TRUE/FALSE 값입니다.</span><span class="sxs-lookup"><span data-stu-id="488b7-123">TRUE/FALSE value on whether to add custodian's mailbox.</span></span>      |
|<span data-ttu-id="488b7-124">**OneDrive 사용**</span><span class="sxs-lookup"><span data-stu-id="488b7-124">**OneDrive Enabled**</span></span> | <span data-ttu-id="488b7-125">Custodian의 비즈니스용 OneDrive 계정을 추가할지 여부에 대 한 TRUE/FALSE 값입니다.</span><span class="sxs-lookup"><span data-stu-id="488b7-125">TRUE/FALSE value on whether to add custodian's OneDrive for Business account.</span></span> |
|<span data-ttu-id="488b7-126">**OnHold**</span><span class="sxs-lookup"><span data-stu-id="488b7-126">**Is OnHold**</span></span>        | <span data-ttu-id="488b7-127">Custodian을 보류할 지 여부에 해당 하는 TRUE/FALSE 값입니다.</span><span class="sxs-lookup"><span data-stu-id="488b7-127">TRUE/FALSE value on whether to place custodian on hold.</span></span>       |
|<span data-ttu-id="488b7-128">**Workload1 형식**</span><span class="sxs-lookup"><span data-stu-id="488b7-128">**Workload1 Type**</span></span>         | <span data-ttu-id="488b7-129">Custodian와 연결할 데이터 원본의 형식을 나타내는 문자열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="488b7-129">String value indicating the type of data source to associate with the custodian.</span></span> <br /><span data-ttu-id="488b7-130">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="488b7-130">Possible values include:</span></span> <br /><span data-ttu-id="488b7-131">ExchangeMailbox, SharePointSite, TeamsMailbox, Teamsmailbox, YammerMailbox, YammerSite</span><span class="sxs-lookup"><span data-stu-id="488b7-131">ExchangeMailbox, SharePointSite, TeamsMailbox, TeamsSite, YammerMailbox, YammerSite</span></span> |
|<span data-ttu-id="488b7-132">**Workload1 위치**</span><span class="sxs-lookup"><span data-stu-id="488b7-132">**Workload1 Location**</span></span>     | <span data-ttu-id="488b7-133">작업 유형에 따라 작업의 데이터 위치 (예: Exchange 사서함의 전자 메일 주소 또는 SharePoint 사이트의 URL)가 여기에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="488b7-133">Depending on your workload type, this would be the data location of your workload (for example, the email address of an Exchange mailbox or the URL for a SharePoint site).</span></span> |
|||

<span data-ttu-id="488b7-134">다음은 custodian 정보를 포함 하는 CSV 파일의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="488b7-134">Here's an example of a CSV file with custodian information:</span></span>  

| <span data-ttu-id="488b7-135">ContactEmail</span><span class="sxs-lookup"><span data-stu-id="488b7-135">ContactEmail</span></span>      | <span data-ttu-id="488b7-136">Exchange 사용</span><span class="sxs-lookup"><span data-stu-id="488b7-136">Exchange Enabled</span></span> | <span data-ttu-id="488b7-137">OneDrive 사용</span><span class="sxs-lookup"><span data-stu-id="488b7-137">OneDrive Enabled</span></span> | <span data-ttu-id="488b7-138">OnHold</span><span class="sxs-lookup"><span data-stu-id="488b7-138">Is OnHold</span></span> | <span data-ttu-id="488b7-139">Workload1 형식</span><span class="sxs-lookup"><span data-stu-id="488b7-139">Workload1 Type</span></span> | <span data-ttu-id="488b7-140">Workload1 위치</span><span class="sxs-lookup"><span data-stu-id="488b7-140">Workload1 Location</span></span>             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|<span data-ttu-id="488b7-141">sarad@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="488b7-141">sarad@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="488b7-142">TRUE</span><span class="sxs-lookup"><span data-stu-id="488b7-142">TRUE</span></span>             | <span data-ttu-id="488b7-143">TRUE</span><span class="sxs-lookup"><span data-stu-id="488b7-143">TRUE</span></span>             | <span data-ttu-id="488b7-144">TRUE</span><span class="sxs-lookup"><span data-stu-id="488b7-144">TRUE</span></span>      | <span data-ttu-id="488b7-145">SharePointSite</span><span class="sxs-lookup"><span data-stu-id="488b7-145">SharePointSite</span></span> | https://contoso.sharepoint.com |
|<span data-ttu-id="488b7-146">pillarp@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="488b7-146">pillarp@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="488b7-147">TRUE</span><span class="sxs-lookup"><span data-stu-id="488b7-147">TRUE</span></span>             | <span data-ttu-id="488b7-148">TRUE</span><span class="sxs-lookup"><span data-stu-id="488b7-148">TRUE</span></span>             | <span data-ttu-id="488b7-149">TRUE</span><span class="sxs-lookup"><span data-stu-id="488b7-149">TRUE</span></span>      | |  |
||||||

## <a name="custodian-and-data-source-validation"></a><span data-ttu-id="488b7-150">Custodian 및 데이터 원본 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="488b7-150">Custodian and data source validation</span></span>

<span data-ttu-id="488b7-151">Custodian CSV 파일을 업로드 하는 경우 Advanced eDiscovery는 다음 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="488b7-151">When you upload the custodian CSV file, Advanced eDiscovery does the following things:</span></span>

1. <span data-ttu-id="488b7-152">Custodians 및 해당 데이터 원본의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="488b7-152">Validates the custodians and their data sources.</span></span> 

2. <span data-ttu-id="488b7-153">각 custodian에 대 한 모든 데이터 원본을 인덱싱하고이를 보류 합니다 (OnHold property가 TRUE로 설정 된 경우).</span><span class="sxs-lookup"><span data-stu-id="488b7-153">Indexes all data sources for each custodian and places them on hold (if the Is OnHold property is set to TRUE).</span></span>

### <a name="custodian-validation"></a><span data-ttu-id="488b7-154">Custodian 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="488b7-154">Custodian validation</span></span>

<span data-ttu-id="488b7-155">현재는 AAD (Azure Active Directory)에 있는 custodians 가져오기를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="488b7-155">Currently, we only support importing custodians that are in Azure Active Directory (AAD).</span></span>

<span data-ttu-id="488b7-156">CSV 파일의 **담당자 전자 메일** 열에서 UPN 값을 사용 하 여 custodians를 확인 하 고 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="488b7-156">We validate and find custodians using the UPN value in the **Contact Email** column in the CSV file.</span></span> <span data-ttu-id="488b7-157">유효성이 검사 된 Custodians 사례에 자동으로 추가 되 고 케이스의 **원본** 페이지에 있는 **Custodian** 탭에 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="488b7-157">Custodians that are validated are automatically added to the case and listed on the **Custodian** tab on the **Sources** page of the case.</span></span> <span data-ttu-id="488b7-158">Custodian의 유효성을 검사할 수 없는 경우 서비스 케이스의 **작업** 탭에 나열 된 BulkAddCustodian 작업에 대 한 오류 로그에 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="488b7-158">If a custodian can't be validated, they are listed in the error log for the BulkAddCustodian job that is listed on the **Jobs** tab in the case.</span></span> <span data-ttu-id="488b7-159">Unvalidated custodians가 사례에 추가 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="488b7-159">Unvalidated custodians are not added to the case.</span></span>

### <a name="data-source-validation"></a><span data-ttu-id="488b7-160">데이터 원본 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="488b7-160">Data source validation</span></span>

<span data-ttu-id="488b7-161">Custodians가 유효성을 검사 하 고 사례에 추가 된 후에는 custodian와 연결 된 각 데이터 원본의 유효성이 검사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="488b7-161">After custodians are validated and added to the case, each data source that's associated with a custodian is validated.</span></span> <span data-ttu-id="488b7-162">Custodian에 대 한 데이터 원본을 찾을 수 없는 경우 **유효성을 검사 하지 않은** 값은 해당 Custodian의 **custodian** 탭에 있는 **유효성이 검사** 된 열에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="488b7-162">If any data source for a custodian can't be found, the value **Not validated** would be displayed in the **Validated** column on the **Custodian** tab for that custodian.</span></span>

### <a name="remediating-unvalidated-data-sources"></a><span data-ttu-id="488b7-163">수정 unvalidated 데이터 원본</span><span class="sxs-lookup"><span data-stu-id="488b7-163">Remediating unvalidated data sources</span></span>

<span data-ttu-id="488b7-164">Unvalidated 데이터 원본을 사용 하 여 custodians을 재구성 하려면:</span><span class="sxs-lookup"><span data-stu-id="488b7-164">To remediate custodians with unvalidated data sources:</span></span> 

1. <span data-ttu-id="488b7-165">**Custodian** 탭에서 유효성이 검사 되지 않은 Custodian을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="488b7-165">On the **Custodian** tab, select a custodian who isn't validated.</span></span>

2. <span data-ttu-id="488b7-166">Custodian 플라이 아웃 페이지에서 **데이터 원본** 섹션으로 스크롤하여 custodian에 연결 된 데이터 원본을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="488b7-166">On the custodian flyout page, scroll to the **Data sources** section to view the data sources that are associated with custodian.</span></span> <span data-ttu-id="488b7-167">유효성이 검사 되 고 unvalidated 데이터 원본이 모두 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="488b7-167">Both validated and unvalidated data sources are listed.</span></span>

3. <span data-ttu-id="488b7-168">**데이터 원본** 섹션에서 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="488b7-168">In the **Data sources** section, click **Edit**.</span></span>

4. <span data-ttu-id="488b7-169">**Custodial 위치 선택** 페이지에서 unvalidated 데이터 원본을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="488b7-169">On the **Choose custodial locations** page, remove an unvalidated data source.</span></span>

5. <span data-ttu-id="488b7-170">**추가 위치 선택** 페이지에서 **업데이트** 를 클릭 하 여 custodian에 대 한 데이터 원본을 더 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="488b7-170">On the **Select additional locations** page, click **Update** to add additional data sources for a custodian.</span></span>
