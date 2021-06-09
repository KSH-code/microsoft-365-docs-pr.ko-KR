---
title: 보시다시안을 사례로 Advanced eDiscovery 가져오기
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
description: 가져오기 도구 d를 사용하여 여러 보호자 및 관련 데이터 원본을 데이터 원본의 사례에 빠르게 Advanced eDiscovery.
ms.openlocfilehash: 98ff3690fe7fd8c956fce436585014ef0db82a26
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "50421615"
---
# <a name="import-custodians-to-an-advanced-ediscovery-case"></a><span data-ttu-id="2568a-103">보시다시안을 사례로 Advanced eDiscovery 가져오기</span><span class="sxs-lookup"><span data-stu-id="2568a-103">Import custodians to an Advanced eDiscovery case</span></span>

<span data-ttu-id="2568a-104">많은 Advanced eDiscovery 관련 사례의 경우, 사례에 추가하는 데 필요한 정보가 포함된 CSV 파일을 사용하여 여러 관리인을 동시에 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2568a-104">For Advanced eDiscovery cases that involve many custodians, you can import multiple custodians at once by using a CSV file that contains the information necessary to add them to a case.</span></span>

## <a name="import-custodians"></a><span data-ttu-id="2568a-105">Custodians 가져오기</span><span class="sxs-lookup"><span data-stu-id="2568a-105">Import custodians</span></span>

1. <span data-ttu-id="2568a-106">데이터 Advanced eDiscovery 열고 데이터 원본 **탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2568a-106">Open the Advanced eDiscovery case and select the **Data sources** tab.</span></span>

2. <span data-ttu-id="2568a-107">데이터 **원본 추가를**  >  **클릭합니다. 보호자 가져오기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="2568a-107">Click **Add data source** > **Import custodians**.</span></span>

3. <span data-ttu-id="2568a-108">가져오기 **custodians** 플라이아웃  페이지에서 빈 템플릿 다운로드를 클릭하여 custodian template CSV 파일을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="2568a-108">On the **Import custodians** flyout page, click **Download a blank template** to download a custodian template CSV file.</span></span>

   ![수장 가져오기 플라이아웃 페이지에서 CSV 템플릿 다운로드](../media/ImportCustodians1.png)

4. <span data-ttu-id="2568a-110">CSV 파일에 custodial 정보를 추가하고 로컬 컴퓨터에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="2568a-110">Add the custodial information to the CSV file and save it to your local computer.</span></span> <span data-ttu-id="2568a-111">CSV 파일의 필수 속성에 대한 자세한 내용은 [Custodian CSV](#custodian-csv-file) 파일 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2568a-111">See the [Custodian CSV file](#custodian-csv-file) section for information about the required properties in the CSV file.</span></span>

5. <span data-ttu-id="2568a-112">cstodian 정보를 사용하여 CSV 파일을 준비한 후 데이터  원본 탭으로 돌아가서 데이터 원본 추가를 다시  >   클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2568a-112">After you've prepared the CSV file with the custodian information, go back to the **Data sources** tab, and click **Add data source** > **Import custodians** again.</span></span>

6. <span data-ttu-id="2568a-113">보호자  가져오기 플라이아웃 페이지에서 찾아보기를 클릭한 다음, 보호자 정보가 포함된 CSV 파일을 업로드합니다. </span><span class="sxs-lookup"><span data-stu-id="2568a-113">On the **Import custodians** flyout page, click **Browse** and then upload the CSV file that contains the custodian information.</span></span>

   <span data-ttu-id="2568a-114">CSV 파일을 업로드하면 **BulkAddCustodian이라는** 작업이 만들어지며 작업 **탭에** 표시됩니다. 이 작업은 보호자 및 관련 데이터 원본의 유효성을 검사한 다음 사례의 데이터 원본 페이지에 추가합니다. </span><span class="sxs-lookup"><span data-stu-id="2568a-114">After the CSV file is uploaded, a job named **BulkAddCustodian** is created and displayed on the **Jobs** tab. The job validates the custodians and their associated data sources and then adds them to the **Data sources** page of the case.</span></span>

## <a name="custodian-csv-file"></a><span data-ttu-id="2568a-115">Custodian CSV 파일</span><span class="sxs-lookup"><span data-stu-id="2568a-115">Custodian CSV file</span></span>

<span data-ttu-id="2568a-116">CSV custodian 템플릿을 다운로드한 후 각 행에 보호자 및 해당 데이터 원본을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2568a-116">After you download the CSV custodian template, you can add custodians and their data source in each row.</span></span> <span data-ttu-id="2568a-117">머리줄 행의 열 이름은 변경하지 말아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2568a-117">Be sure not to change the column names in the header row.</span></span> <span data-ttu-id="2568a-118">작업 유형 및 작업 위치 열을 사용하여 다른 데이터 원본을 보호자에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="2568a-118">Use the workload type and workload location columns to associate other data sources to a custodian.</span></span>

| <span data-ttu-id="2568a-119">열 이름</span><span class="sxs-lookup"><span data-stu-id="2568a-119">Column name</span></span>|<span data-ttu-id="2568a-120">설명</span><span class="sxs-lookup"><span data-stu-id="2568a-120">Description</span></span>|
|:------- |:------------------------------------------------------------|
|<span data-ttu-id="2568a-121">**Custodian contactEmail**</span><span class="sxs-lookup"><span data-stu-id="2568a-121">**Custodian contactEmail**</span></span>     |<span data-ttu-id="2568a-122">Custodian의 UPN 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="2568a-122">The custodian's UPN email address.</span></span> <span data-ttu-id="2568a-123">예를 들어 sarad@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="2568a-123">For example, sarad@contoso.onmicrosoft.com.</span></span>           |
|<span data-ttu-id="2568a-124">**Exchange 사용**</span><span class="sxs-lookup"><span data-stu-id="2568a-124">**Exchange Enabled**</span></span> | <span data-ttu-id="2568a-125">CUSTODian의 사서함을 포함하거나 포함하지 않을 TRUE/FALSE 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2568a-125">TRUE/FALSE value to include or not include the custodian's mailbox.</span></span>      |
|<span data-ttu-id="2568a-126">**OneDrive 사용**</span><span class="sxs-lookup"><span data-stu-id="2568a-126">**OneDrive Enabled**</span></span> | <span data-ttu-id="2568a-127">TRUE/FALSE 값으로, 관리인 계정이 포함되거나 포함되지 비즈니스용 OneDrive 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2568a-127">TRUE/FALSE value to include or not included the custodian's OneDrive for Business account.</span></span> |
|<span data-ttu-id="2568a-128">**Is OnHold**</span><span class="sxs-lookup"><span data-stu-id="2568a-128">**Is OnHold**</span></span>        | <span data-ttu-id="2568a-129">보유자 데이터 원본을 보류할지 여부를 나타내는 TRUE/FALSE 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2568a-129">TRUE/FALSE value to indicate whether to place the custodian data sources on hold.</span></span> <span data-ttu-id="2568a-130"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="2568a-130"><sup>1</sup></span></span>     |
|<span data-ttu-id="2568a-131">**Workload1 유형**</span><span class="sxs-lookup"><span data-stu-id="2568a-131">**Workload1 Type**</span></span>         |<span data-ttu-id="2568a-132">보호자에 연결되는 데이터 원본의 유형을 나타내는 문자열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2568a-132">String value indicating the type of data source to associate with the custodian.</span></span> <span data-ttu-id="2568a-133">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2568a-133">Possible values include:</span></span> <br/><span data-ttu-id="2568a-134">- ExchangeMailbox</span><span class="sxs-lookup"><span data-stu-id="2568a-134">- ExchangeMailbox</span></span><br/> <span data-ttu-id="2568a-135">- SharePointSite</span><span class="sxs-lookup"><span data-stu-id="2568a-135">- SharePointSite</span></span><br/><span data-ttu-id="2568a-136">- TeamsMailbox</span><span class="sxs-lookup"><span data-stu-id="2568a-136">- TeamsMailbox</span></span><br/><span data-ttu-id="2568a-137">- TeamsSite</span><span class="sxs-lookup"><span data-stu-id="2568a-137">- TeamsSite</span></span><br/> <span data-ttu-id="2568a-138">- YammerMailbox</span><span class="sxs-lookup"><span data-stu-id="2568a-138">- YammerMailbox</span></span><br/><span data-ttu-id="2568a-139">- YammerSite</span><span class="sxs-lookup"><span data-stu-id="2568a-139">- YammerSite</span></span> |
|<span data-ttu-id="2568a-140">**Workload1 Location**</span><span class="sxs-lookup"><span data-stu-id="2568a-140">**Workload1 Location**</span></span>     | <span data-ttu-id="2568a-141">작업 유형에 따라 데이터 원본의 위치가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2568a-141">Depending on your workload type, this would be the location of the data source.</span></span> <span data-ttu-id="2568a-142">예를 들어 Exchange 사서함의 전자 메일 주소 또는 SharePoint 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2568a-142">For example, the email address for an Exchange mailbox or the URL for a SharePoint site.</span></span> |
|||

> [!NOTE]
> <span data-ttu-id="2568a-143"><sup>1</sup> 보유자 가져오기 프로세스 및 CSV 파일을 사용하여 최대 1,000개 사서함과 100개 사이트를 보류할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2568a-143"><sup>1</sup> You can place a maximum of 1,000 mailboxes and 100 sites on hold by using the custodian import process and CSV file.</span></span> <span data-ttu-id="2568a-144">이 프로세스를 사용하여 사례에 1,000명 이상의 보유자 추가를 할 수 있지만 보류 제한은 계속 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2568a-144">You can use this process to add more than 1,000 custodians to a case, but the hold limits still apply.</span></span> <span data-ttu-id="2568a-145">보류 제한에 대한 자세한 내용은 [에서 제한을 Advanced eDiscovery.](limits-ediscovery20.md#hold-limits)</span><span class="sxs-lookup"><span data-stu-id="2568a-145">For more information about hold limits, see [Limits in Advanced eDiscovery](limits-ediscovery20.md#hold-limits).</span></span>

<span data-ttu-id="2568a-146">다음은 보호자 정보가 있는 CSV 파일의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="2568a-146">Here's an example of a CSV file with custodian information:</span></span><br/><br/>

|<span data-ttu-id="2568a-147">Custodian contactEmail</span><span class="sxs-lookup"><span data-stu-id="2568a-147">Custodian contactEmail</span></span>      | <span data-ttu-id="2568a-148">Exchange 사용</span><span class="sxs-lookup"><span data-stu-id="2568a-148">Exchange Enabled</span></span> | <span data-ttu-id="2568a-149">OneDrive 사용</span><span class="sxs-lookup"><span data-stu-id="2568a-149">OneDrive Enabled</span></span> | <span data-ttu-id="2568a-150">Is OnHold</span><span class="sxs-lookup"><span data-stu-id="2568a-150">Is OnHold</span></span> | <span data-ttu-id="2568a-151">Workload1 유형</span><span class="sxs-lookup"><span data-stu-id="2568a-151">Workload1 Type</span></span> | <span data-ttu-id="2568a-152">Workload1 Location</span><span class="sxs-lookup"><span data-stu-id="2568a-152">Workload1 Location</span></span>             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|<span data-ttu-id="2568a-153">robinc@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2568a-153">robinc@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="2568a-154">TRUE</span><span class="sxs-lookup"><span data-stu-id="2568a-154">TRUE</span></span>             | <span data-ttu-id="2568a-155">TRUE</span><span class="sxs-lookup"><span data-stu-id="2568a-155">TRUE</span></span>             | <span data-ttu-id="2568a-156">TRUE</span><span class="sxs-lookup"><span data-stu-id="2568a-156">TRUE</span></span>      | <span data-ttu-id="2568a-157">SharePointSite</span><span class="sxs-lookup"><span data-stu-id="2568a-157">SharePointSite</span></span> | https://contoso.sharepoint.com |
|<span data-ttu-id="2568a-158">pillarp@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2568a-158">pillarp@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="2568a-159">TRUE</span><span class="sxs-lookup"><span data-stu-id="2568a-159">TRUE</span></span>             | <span data-ttu-id="2568a-160">TRUE</span><span class="sxs-lookup"><span data-stu-id="2568a-160">TRUE</span></span>             | <span data-ttu-id="2568a-161">TRUE</span><span class="sxs-lookup"><span data-stu-id="2568a-161">TRUE</span></span>      | |  |
||||||

## <a name="custodian-and-data-source-validation"></a><span data-ttu-id="2568a-162">보호자 및 데이터 원본 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="2568a-162">Custodian and data source validation</span></span>

<span data-ttu-id="2568a-163">cstodian CSV 파일을 업로드한 후 Advanced eDiscovery 다음을 합니다.</span><span class="sxs-lookup"><span data-stu-id="2568a-163">After you upload the custodian CSV file, Advanced eDiscovery does the following things:</span></span>

1. <span data-ttu-id="2568a-164">보호자 및 데이터 원본의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="2568a-164">Validates the custodians and their data sources.</span></span>

2. <span data-ttu-id="2568a-165">각 보유자에 대한 모든 데이터 원본을 인덱싱하고 보류합니다(CSV 파일의 **Is OnHold** 속성이 TRUE로 설정된 경우).</span><span class="sxs-lookup"><span data-stu-id="2568a-165">Indexes all data sources for each custodian and places them on hold (if the **Is OnHold** property in the CSV file is set to TRUE).</span></span>

### <a name="custodian-validation"></a><span data-ttu-id="2568a-166">Custodian validation</span><span class="sxs-lookup"><span data-stu-id="2568a-166">Custodian validation</span></span>

<span data-ttu-id="2568a-167">현재는 조직의 Azure AD(조직 관리)에 포함된 Azure Active Directory 가져오기만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="2568a-167">Currently, we only support importing custodians that are included in your organization's Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="2568a-168">custodian 가져오기 도구는 CSV 파일의 **Custodian contactEmail** 열에 있는 UPN 값을 사용하여 관리인을 찾고 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="2568a-168">The custodian import tool finds and validates custodians using the UPN value in the **Custodian contactEmail** column in the CSV file.</span></span> <span data-ttu-id="2568a-169">유효성이 검사된 보호자는 사례에 자동으로 추가되고 사례의 데이터 원본 **탭에** 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="2568a-169">Custodians that are validated are automatically added to the case and listed on the **Data sources** tab of the case.</span></span> <span data-ttu-id="2568a-170">보직의 유효성을 검사할 수 없는 경우 해당 사례의 작업 탭에 나열된 BulkAddCustodian  작업의 오류 로그에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="2568a-170">If a custodian can't be validated, they are listed in the error log for the BulkAddCustodian job that is listed on the **Jobs** tab in the case.</span></span> <span data-ttu-id="2568a-171">미확인된 보호자는 사례에 추가되거나 데이터 원본 탭에 **나열되지** 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2568a-171">Unvalidated custodians are not added to the case or listed on the **Data sources** tab.</span></span>

### <a name="data-source-validation"></a><span data-ttu-id="2568a-172">데이터 원본 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="2568a-172">Data source validation</span></span>

<span data-ttu-id="2568a-173">관리인이 유효성을 검사하고 사례에 추가하면, OneDrive 연결된 각 기본 사서함 및 OneDrive 계정이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="2568a-173">After custodians are validated and added to the case, each primary mailbox and OneDrive account that's associated with a custodian is added.</span></span>

<span data-ttu-id="2568a-174">그러나 보호자에 연결된 다른 데이터 원본(예: SharePoint 사이트, Microsoft Teams, Microsoft 365 그룹 또는 Yammer 그룹)을 찾을 수 없는 경우 해당 데이터 원본이 보호자에 할당되지 않은 경우 유효성 검사되지 않은 값이 데이터  원본 탭의 보호자 옆에 있는  상태 열에 표시됩니다. </span><span class="sxs-lookup"><span data-stu-id="2568a-174">However, if any of the other data sources (such as SharePoint sites, Microsoft Teams, Microsoft 365 Groups, or Yammer groups) associated with a custodian can't be found, none of them are assigned to the custodian and the value **Not validated** is displayed in the **Status** column next to the custodian on the **Data sources** tab.</span></span>

<span data-ttu-id="2568a-175">보호자에 대해 유효성이 검사된 데이터 원본을 추가하는 경우:</span><span class="sxs-lookup"><span data-stu-id="2568a-175">To add validated data sources for a custodian:</span></span>

1. <span data-ttu-id="2568a-176">데이터 원본 **탭에서** 유효성이 검사되지 않은 데이터 원본이 포함된 보호기를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2568a-176">On the **Data sources** tab, select a custodian that contains data sources that aren't validated.</span></span>

2. <span data-ttu-id="2568a-177">보호자 플라이아웃 페이지에서 **Custodial 위치** 섹션으로 스크롤하여 보호자와 연결된 유효성이 검사된 데이터 원본과 미확인 데이터 원본을 모두 니다.</span><span class="sxs-lookup"><span data-stu-id="2568a-177">On the custodian flyout page, scroll to the **Custodial locations** section to view both validated and unvalidated data sources that are associated with custodian.</span></span>

3. <span data-ttu-id="2568a-178">**플라이아웃** 페이지 위쪽에서 편집을 클릭하여 잘못된 데이터 원본을 제거하거나 새 데이터 원본을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2568a-178">Click **Edit** at the top of the flyout page to remove invalid data sources or add new ones.</span></span>

4. <span data-ttu-id="2568a-179">미확인 데이터 원본을 제거하거나 새 데이터 원본을 추가하면  **데이터** 원본 탭의 보위원에 대한 상태 열에 Active 값이 **표시됩니다.** 이전에 유효하지 않은 것으로 나타난 원본을 추가하려면 아래 수정 단계에 따라 관리인에게 수동으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2568a-179">After you remove unvalidated data sources or add a new one, the value **Active** is displayed in **Status** column for the custodian on the **Data sources** tab. To add sources that previously appeared to be invalid, follow the remediation steps below to manually add them to a custodian.</span></span>

### <a name="remediating-invalid-data-sources"></a><span data-ttu-id="2568a-180">잘못된 데이터 원본 수정</span><span class="sxs-lookup"><span data-stu-id="2568a-180">Remediating invalid data sources</span></span>

<span data-ttu-id="2568a-181">이전에 유효하지 않은 데이터 원본을 수동으로 추가하고 연결하려면</span><span class="sxs-lookup"><span data-stu-id="2568a-181">To manually add and associate a data source that was previously invalid:</span></span>

1. <span data-ttu-id="2568a-182">데이터 원본 **탭에서** 이전에 유효하지 않은 데이터 원본을 수동으로 추가하고 연결하기 위해 보호 기능을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2568a-182">On the **Data sources** tab, select a custodian to manually add and associate a data source that was previously invalid.</span></span>

2. <span data-ttu-id="2568a-183">**플라이아웃** 페이지 위쪽에서 편집을 클릭하여 사서함, 사이트, Teams 또는 Yammer 그룹을 보아에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="2568a-183">Click **Edit** at the top of the flyout page to associate mailboxes, sites, Teams, or Yammer groups to the custodian.</span></span> <span data-ttu-id="2568a-184">해당 데이터 위치 유형 옆에 있는 **편집을** 클릭하여 이 작업을 합니다.</span><span class="sxs-lookup"><span data-stu-id="2568a-184">Do this by clicking **Edit** next to the appropriate data location type.</span></span>

3. <span data-ttu-id="2568a-185">다음을 클릭하여 보류 설정 페이지를 **표시하고** 추가한 데이터 원본에 대한 보류 설정을 구성합니다. </span><span class="sxs-lookup"><span data-stu-id="2568a-185">Click **Next** to display the **Hold settings** page and configure the hold setting for the data sources you added.</span></span>

4. <span data-ttu-id="2568a-186">**다음을** 클릭하여 보호자 검토 **페이지를** 표시한 다음  제출을 클릭하여 변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="2568a-186">Click **Next** to display the **Review custodians** page, and then click **Submit** to save your changes.</span></span>
