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
description: ''
ms.openlocfilehash: 9331e45619f549ea31adcfdd9316eea20e43efef
ms.sourcegitcommit: a005395165db8896f4109674443b5e5e9209861d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/31/2020
ms.locfileid: "44432441"
---
# <a name="bulk-add-custodians-to-an-advanced-ediscovery-case-preview"></a><span data-ttu-id="8ec3c-102">대량-Advanced eDiscovery 사례 (미리 보기)에 custodians 추가</span><span class="sxs-lookup"><span data-stu-id="8ec3c-102">Bulk-add custodians to an Advanced eDiscovery case (preview)</span></span>

<span data-ttu-id="8ec3c-103">많은 수의 custodians 포함 된 고급 eDiscovery 사례의 경우 여러 custodians를 사례에 추가 하는 데 필요한 모든 정보를 포함 하는 CSV 파일을 한 번에 가져올 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3c-103">For Advanced eDiscovery cases that involve a lot of custodians, you can import multiple custodians at once by a CSV file that contains all the information necessary to add them to a case.</span></span>

## <a name="bulk-add-custodians"></a><span data-ttu-id="8ec3c-104">대량 추가 custodians</span><span class="sxs-lookup"><span data-stu-id="8ec3c-104">Bulk-add custodians</span></span>

1. <span data-ttu-id="8ec3c-105">사례를 입력 하 고 **원본** 탭으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3c-105">Enter case and navigate to the **Sources** tab.</span></span>

2. <span data-ttu-id="8ec3c-106">**가져오기 custodians** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3c-106">Click **Import custodians**</span></span>

3. <span data-ttu-id="8ec3c-107">플라이 아웃 페이지에서 **빈 서식 파일 다운로드** 를 클릭 하 여 CSV custodian 서식 파일을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3c-107">On the flyout page, click **Download a blank template** to download a CSV custodian template file.</span></span>

4. <span data-ttu-id="8ec3c-108">CSV 파일에 custodial 정보를 추가 하 고 로컬 컴퓨터에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3c-108">Add the custodial information to the CSV file and save it on your local computer.</span></span> <span data-ttu-id="8ec3c-109">CSV 파일의 속성에 대 한 자세한 내용은 다음 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8ec3c-109">See the next section for information about the properties in the CSV file.</span></span>

5. <span data-ttu-id="8ec3c-110">**원본** 탭에서 **Custodians 가져오기를** 다시 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3c-110">On the **Sources** tab, click **Import Custodians** again.</span></span> 
6. <span data-ttu-id="8ec3c-111">플라이 아웃 페이지에서 **찾아보기를** 클릭 하 고 CSV 파일을 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3c-111">On flyout page, click **Browse** and the upload your CSV file.</span></span>

   <span data-ttu-id="8ec3c-112">CSV 파일이 업로드 된 후에는 BulkAddCustodian 작업이 만들어지고 **작업** 탭에 표시 됩니다. 이 작업은 custodians의 해당 하는 데이터 원본에 대 한 유효성을 검사 한 다음 케이스의 **원본** 페이지에 있는 **custodians** 탭에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3c-112">After the CSV file is uploaded, a BulkAddCustodian job is created and displayed on the **Jobs** tab. The job validates the custodians and their corresponding data sources and then adds them to the **Custodians** tab on the **Sources** page of the case.</span></span>

## <a name="custodian-csv-file"></a><span data-ttu-id="8ec3c-113">Custodian CSV 파일</span><span class="sxs-lookup"><span data-stu-id="8ec3c-113">Custodian CSV file</span></span>

<span data-ttu-id="8ec3c-114">CSV 서식 파일을 다운로드 한 후에는 각 행에 custodians 및 해당 데이터 원본을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3c-114">After you download the CSV template, you can add custodians and their data source in each row.</span></span> <span data-ttu-id="8ec3c-115">머리글 행의 열 이름은 변경 하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3c-115">Be sure not to change the column names in the the header row.</span></span>

| <span data-ttu-id="8ec3c-116">열 이름</span><span class="sxs-lookup"><span data-stu-id="8ec3c-116">Column name</span></span>|<span data-ttu-id="8ec3c-117">설명</span><span class="sxs-lookup"><span data-stu-id="8ec3c-117">Description</span></span>|
|:------- |:------------------------------------------------------------|
|<span data-ttu-id="8ec3c-118">**Custodian ContactEmail**</span><span class="sxs-lookup"><span data-stu-id="8ec3c-118">**Custodian ContactEmail**</span></span>     | <span data-ttu-id="8ec3c-119">Custodian의 UPN 전자 메일입니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3c-119">UPN email of custodian.</span></span> <span data-ttu-id="8ec3c-120">예: sarad@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8ec3c-120">Example: sarad@onmicrosoft.contoso.com</span></span>           |
|<span data-ttu-id="8ec3c-121">**Exchange 사용**</span><span class="sxs-lookup"><span data-stu-id="8ec3c-121">**Exchange Enabled**</span></span> | <span data-ttu-id="8ec3c-122">Custodian의 사서함을 추가할지 여부에 대 한 TRUE/FALSE 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3c-122">TRUE/FALSE value on whether to add custodian's mailbox.</span></span>      |
|<span data-ttu-id="8ec3c-123">**OneDrive 사용**</span><span class="sxs-lookup"><span data-stu-id="8ec3c-123">**OneDrive Enabled**</span></span> | <span data-ttu-id="8ec3c-124">Custodian의 비즈니스용 OneDrive 계정을 추가할지 여부에 대 한 TRUE/FALSE 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3c-124">TRUE/FALSE value on whether to add custodian's OneDrive for Business account.</span></span> |
|<span data-ttu-id="8ec3c-125">**OnHold**</span><span class="sxs-lookup"><span data-stu-id="8ec3c-125">**Is OnHold**</span></span>        | <span data-ttu-id="8ec3c-126">Custodian을 보류할 지 여부에 해당 하는 TRUE/FALSE 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3c-126">TRUE/FALSE value on whether to place custodian on hold.</span></span>       |
|<span data-ttu-id="8ec3c-127">**Workload1 형식**</span><span class="sxs-lookup"><span data-stu-id="8ec3c-127">**Workload1 Type**</span></span>         | <span data-ttu-id="8ec3c-128">Custodian와 연결할 데이터 원본의 형식을 나타내는 문자열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3c-128">String value indicating the type of data source to associate with the custodian.</span></span> <br /><span data-ttu-id="8ec3c-129">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3c-129">Possible values include:</span></span> <br /><span data-ttu-id="8ec3c-130">ExchangeMailbox, SharePointSite, TeamsMailbox, Teamsmailbox, YammerMailbox, YammerSite</span><span class="sxs-lookup"><span data-stu-id="8ec3c-130">ExchangeMailbox, SharePointSite, TeamsMailbox, TeamsSite, YammerMailbox, YammerSite</span></span> |
|<span data-ttu-id="8ec3c-131">**Workload1 위치**</span><span class="sxs-lookup"><span data-stu-id="8ec3c-131">**Workload1 Location**</span></span>     | <span data-ttu-id="8ec3c-132">작업 유형에 따라 작업의 데이터 위치 (예: Exchange 사서함의 전자 메일 주소 또는 SharePoint 사이트의 URL)가 여기에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3c-132">Depending on your workload type, this would be the data location of your workload (for example, the email address of an Exchange mailbox or the URL for a SharePoint site).</span></span> |
|||

<span data-ttu-id="8ec3c-133">다음은 custodian 정보를 포함 하는 CSV 파일의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3c-133">Here's an example of a CSV file with custodian information:</span></span>  

| <span data-ttu-id="8ec3c-134">ContactEmail</span><span class="sxs-lookup"><span data-stu-id="8ec3c-134">ContactEmail</span></span>      | <span data-ttu-id="8ec3c-135">Exchange 사용</span><span class="sxs-lookup"><span data-stu-id="8ec3c-135">Exchange Enabled</span></span> | <span data-ttu-id="8ec3c-136">OneDrive 사용</span><span class="sxs-lookup"><span data-stu-id="8ec3c-136">OneDrive Enabled</span></span> | <span data-ttu-id="8ec3c-137">OnHold</span><span class="sxs-lookup"><span data-stu-id="8ec3c-137">Is OnHold</span></span> | <span data-ttu-id="8ec3c-138">Workload1 형식</span><span class="sxs-lookup"><span data-stu-id="8ec3c-138">Workload1 Type</span></span> | <span data-ttu-id="8ec3c-139">Workload1 위치</span><span class="sxs-lookup"><span data-stu-id="8ec3c-139">Workload1 Location</span></span>             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|<span data-ttu-id="8ec3c-140">sarad@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8ec3c-140">sarad@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="8ec3c-141">TRUE</span><span class="sxs-lookup"><span data-stu-id="8ec3c-141">TRUE</span></span>             | <span data-ttu-id="8ec3c-142">TRUE</span><span class="sxs-lookup"><span data-stu-id="8ec3c-142">TRUE</span></span>             | <span data-ttu-id="8ec3c-143">TRUE</span><span class="sxs-lookup"><span data-stu-id="8ec3c-143">TRUE</span></span>      | <span data-ttu-id="8ec3c-144">SharePointSite</span><span class="sxs-lookup"><span data-stu-id="8ec3c-144">SharePointSite</span></span> | https://contoso.sharepoint.com |
|<span data-ttu-id="8ec3c-145">pillarp@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8ec3c-145">pillarp@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="8ec3c-146">TRUE</span><span class="sxs-lookup"><span data-stu-id="8ec3c-146">TRUE</span></span>             | <span data-ttu-id="8ec3c-147">TRUE</span><span class="sxs-lookup"><span data-stu-id="8ec3c-147">TRUE</span></span>             | <span data-ttu-id="8ec3c-148">TRUE</span><span class="sxs-lookup"><span data-stu-id="8ec3c-148">TRUE</span></span>      | |  |
||||||

## <a name="custodian-and-data-source-validation"></a><span data-ttu-id="8ec3c-149">Custodian 및 데이터 원본 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="8ec3c-149">Custodian and data source validation</span></span>

<span data-ttu-id="8ec3c-150">Custodian CSV 파일을 업로드 하는 경우 Advanced eDiscovery는 다음 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3c-150">When you upload the custodian CSV file, Advanced eDiscovery does the following things:</span></span>

1. <span data-ttu-id="8ec3c-151">Custodians 및 해당 데이터 원본의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3c-151">Validates the custodians and their data sources.</span></span> 

2. <span data-ttu-id="8ec3c-152">각 custodian에 대 한 모든 데이터 원본을 인덱싱하고이를 보류 합니다 (OnHold property가 TRUE로 설정 된 경우).</span><span class="sxs-lookup"><span data-stu-id="8ec3c-152">Indexes all data sources for each custodian and places them on hold (if the Is OnHold property is set to TRUE).</span></span>

### <a name="custodian-validation"></a><span data-ttu-id="8ec3c-153">Custodian 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="8ec3c-153">Custodian validation</span></span>

<span data-ttu-id="8ec3c-154">현재는 AAD (Azure Active Directory)에 있는 custodians 가져오기를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3c-154">Currently, we only support importing custodians that are in Azure Active Directory (AAD).</span></span>

<span data-ttu-id="8ec3c-155">CSV 파일의 **담당자 전자 메일** 열에서 UPN 값을 사용 하 여 custodians를 확인 하 고 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3c-155">We validate and find custodians using the UPN value in the **Contact Email** column in the CSV file.</span></span> <span data-ttu-id="8ec3c-156">유효성이 검사 된 Custodians 사례에 자동으로 추가 되 고 케이스의 **원본** 페이지에 있는 **Custodian** 탭에 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3c-156">Custodians that are validated are automatically added to the case and listed on the **Custodian** tab on the **Sources** page of the case.</span></span> <span data-ttu-id="8ec3c-157">Custodian의 유효성을 검사할 수 없는 경우 서비스 케이스의 **작업** 탭에 나열 된 BulkAddCustodian 작업에 대 한 오류 로그에 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3c-157">If a custodian can't be validated, they are listed in the error log for the BulkAddCustodian job that is listed on the **Jobs** tab in the case.</span></span> <span data-ttu-id="8ec3c-158">Unvalidated custodians가 사례에 추가 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3c-158">Unvalidated custodians are not added to the case.</span></span>

### <a name="data-source-validation"></a><span data-ttu-id="8ec3c-159">데이터 원본 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="8ec3c-159">Data source validation</span></span>

<span data-ttu-id="8ec3c-160">Custodians가 유효성을 검사 하 고 사례에 추가 된 후에는 custodian와 연결 된 각 데이터 원본의 유효성이 검사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3c-160">After custodians are validated and added to the case, each data source that's associated with a custodian is validated.</span></span> <span data-ttu-id="8ec3c-161">Custodian에 대 한 데이터 원본을 찾을 수 없는 경우 **유효성을 검사 하지 않은** 값은 해당 Custodian의 **custodian** 탭에 있는 **유효성이 검사** 된 열에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3c-161">If any data source for a custodian can't be found, the value **Not validated** would be displayed in the **Validated** column on the **Custodian** tab for that custodian.</span></span>

### <a name="remediating-unvalidated-data-sources"></a><span data-ttu-id="8ec3c-162">수정 unvalidated 데이터 원본</span><span class="sxs-lookup"><span data-stu-id="8ec3c-162">Remediating unvalidated data sources</span></span>

<span data-ttu-id="8ec3c-163">Unvalidated 데이터 원본을 사용 하 여 custodians을 재구성 하려면:</span><span class="sxs-lookup"><span data-stu-id="8ec3c-163">To remediate custodians with unvalidated data sources:</span></span> 

1. <span data-ttu-id="8ec3c-164">**Custodian** 탭에서 유효성이 검사 되지 않은 Custodian을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3c-164">On the **Custodian** tab, select a custodian who isn't validated.</span></span>

2. <span data-ttu-id="8ec3c-165">Custodian 플라이 아웃 페이지에서 **데이터 원본** 섹션으로 스크롤하여 custodian에 연결 된 데이터 원본을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3c-165">On the custodian flyout page, scroll to the **Data sources** section to view the data sources that are associated with custodian.</span></span> <span data-ttu-id="8ec3c-166">유효성이 검사 되 고 unvalidated 데이터 원본이 모두 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3c-166">Both validated and unvalidated data sources are listed.</span></span>

3. <span data-ttu-id="8ec3c-167">**데이터 원본** 섹션에서 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3c-167">In the **Data sources** section, click **Edit**.</span></span>

4. <span data-ttu-id="8ec3c-168">**Custodial 위치 선택** 페이지에서 unvalidated 데이터 원본을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3c-168">On the **Choose custodial locations** page, remove an unvalidated data source.</span></span>

5. <span data-ttu-id="8ec3c-169">**추가 위치 선택** 페이지에서 **업데이트** 를 클릭 하 여 custodian에 대 한 데이터 원본을 더 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec3c-169">On the **Select additional locations** page, click **Update** to add additional data sources for a custodian.</span></span>
