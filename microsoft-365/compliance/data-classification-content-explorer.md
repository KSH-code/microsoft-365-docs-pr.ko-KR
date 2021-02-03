---
title: 콘텐츠 탐색기 시작하기
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 콘텐츠 탐색기를 사용하여 레이블이 지정된 항목을 원래 상태로 볼 수 있습니다.
ms.openlocfilehash: 19ad68d3c32046754e366919e8c4e66336945624
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080727"
---
# <a name="get-started-with-content-explorer"></a><span data-ttu-id="eae4f-103">콘텐츠 탐색기 시작하기</span><span class="sxs-lookup"><span data-stu-id="eae4f-103">Get started with content explorer</span></span>

<span data-ttu-id="eae4f-104">데이터 분류 콘텐츠 탐색기를 사용하여 개요 페이지에 요약된 항목을 원래 상태로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eae4f-104">The data classification content explorer allows you to natively view the items that were summarized on the overview page.</span></span>

![콘텐츠 탐색기 축소 스크린샷](../media/data-classification-content-explorer-1.png)

## <a name="prerequisites"></a><span data-ttu-id="eae4f-106">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="eae4f-106">Prerequisites</span></span>

<span data-ttu-id="eae4f-107">테이터 분류에 액세스하고 이를 사용하는 모든 계정에는 다음 구독 중 하나에서 할당된 라이선스가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eae4f-107">Every account that accesses and uses data classification must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="eae4f-108">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="eae4f-108">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="eae4f-109">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="eae4f-109">Office 365 (E5)</span></span>
- <span data-ttu-id="eae4f-110">고급 규정 준수 (E5) 추가 기능</span><span class="sxs-lookup"><span data-stu-id="eae4f-110">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="eae4f-111">고급 위협 인텔리전스 (E5) 추가 기능</span><span class="sxs-lookup"><span data-stu-id="eae4f-111">Advanced Threat Intelligence (E5) add-on</span></span>
- <span data-ttu-id="eae4f-112">Microsoft 365 E5/A5 정보 보호 및 거버넌스</span><span class="sxs-lookup"><span data-stu-id="eae4f-112">Microsoft 365 E5/A5 Info Protection & Governance</span></span>
- <span data-ttu-id="eae4f-113">Microsoft 365 E5/A5 규정 준수</span><span class="sxs-lookup"><span data-stu-id="eae4f-113">Microsoft 365 E5/A5 Compliance</span></span>


### <a name="permissions"></a><span data-ttu-id="eae4f-114">권한</span><span class="sxs-lookup"><span data-stu-id="eae4f-114">Permissions</span></span>

<span data-ttu-id="eae4f-115">콘텐츠 탐색기 탭에 액세스하려면 계정에 다음 역할이나 역할 그룹 중 하나의 구성원 자격이 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eae4f-115">In order to get access to the content explorer tab, an account must be assigned membership in any one of these roles or role groups.</span></span> 

<span data-ttu-id="eae4f-116">**Microsoft 365 역할 그룹**</span><span class="sxs-lookup"><span data-stu-id="eae4f-116">**Microsoft 365 role groups**</span></span>

- <span data-ttu-id="eae4f-117">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="eae4f-117">Global administrator</span></span>
- <span data-ttu-id="eae4f-118">준수 관리자</span><span class="sxs-lookup"><span data-stu-id="eae4f-118">Compliance administrator</span></span>
- <span data-ttu-id="eae4f-119">보안 관리자</span><span class="sxs-lookup"><span data-stu-id="eae4f-119">Security administrator</span></span>
- <span data-ttu-id="eae4f-120">규정 준수 데이터 관리자</span><span class="sxs-lookup"><span data-stu-id="eae4f-120">Compliance data administrator</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eae4f-121">이러한 역할 그룹의 구성원은 콘텐츠 탐색기의 항목 목록을 보거나 콘텐츠 탐색기의 항목 내용을 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eae4f-121">Membership in these role groups does not allow you to view the list of items in content explorer or to view the contents of the items in content explorer.</span></span>

### <a name="required-permissions-to-access-items-in-content-explorer"></a><span data-ttu-id="eae4f-122">콘텐츠 탐색기에서 항목에 액세스하는 데 필요한 권한</span><span class="sxs-lookup"><span data-stu-id="eae4f-122">Required permissions to access items in content explorer</span></span>

<span data-ttu-id="eae4f-123">콘텐츠 탐색기에 대한 액세스는 검사된 파일의 내용을 읽을 수 있기 때문에 매우 제한적입니다.</span><span class="sxs-lookup"><span data-stu-id="eae4f-123">Access to content explorer is highly restricted because it lets you read the contents of scanned files.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eae4f-124">이러한 권한은 해당 항목에 로컬로 할당되는 권한을 대체하여 콘텐츠를 볼 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="eae4f-124">These permissions supercede permissions that are locally assigned to the items, which allows viewing of the content.</span></span> 

<span data-ttu-id="eae4f-125">콘텐츠 탐색기에는 액세스 권한을 부여하는 두 가지 역할이 있으며 [Microsoft 보안 및 준수 센터](https://protection.office.com/permissions)를 사용하여 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="eae4f-125">There are two roles that grant access to content explorer and it is granted using the [Microsoft Security & Compliance Center](https://protection.office.com/permissions):</span></span>

- <span data-ttu-id="eae4f-126">**콘텐츠 탐색기 목록 뷰어**: 이 역할 그룹의 구성원 자격으로 목록 보기에서 각 항목과 해당 위치를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eae4f-126">**Content Explorer List viewer**: Membership in this role group allows you to see each item and its location in list view.</span></span> <span data-ttu-id="eae4f-127">`data classification list viewer` 역할이 사전에 이 역할 그룹에 할당되었습니다.</span><span class="sxs-lookup"><span data-stu-id="eae4f-127">The `data classification list viewer` role has been pre-assigned to this role group.</span></span>

- <span data-ttu-id="eae4f-128">**콘텐츠 탐색기 콘텐츠 뷰어**:이 역할 그룹의 멤버 자격으로 목록에 있는 각 항목의 내용을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eae4f-128">**Content Explorer Content viewer**: Membership in this role group allows you to view the contents of each item in the list.</span></span> <span data-ttu-id="eae4f-129">`data classification content viewer` 역할이 사전에 이 역할 그룹에 할당되었습니다.</span><span class="sxs-lookup"><span data-stu-id="eae4f-129">The `data classification content viewer` role has been pre-assigned to this role group.</span></span>

<span data-ttu-id="eae4f-130">콘텐츠 탐색기에 액세스하는 데 사용하는 계정은 역할 그룹 중 하나 또는 둘 다에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eae4f-130">The account you use to access content explorer must be in one or both of the role groups.</span></span> <span data-ttu-id="eae4f-131">이러한 역할은 독립적인 역할 그룹이며 누적되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eae4f-131">These are independent role groups and are not cumulative.</span></span> <span data-ttu-id="eae4f-132">예를 들어 계정에 항목 및 해당 위치만 볼 수 있는 권한을 부여 하려는 경우 콘텐츠 탐색기 목록 표시기 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="eae4f-132">For example, if you want to grant an account the ability to view the items and their locations only, grant Content Explorer List viewer rights.</span></span> <span data-ttu-id="eae4f-133">동일한 계정에서 목록에 있는 항목의 내용을 볼 수 있게 하려면 콘텐츠 탐색기 콘텐츠 뷰어 권한도 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="eae4f-133">If you want that same account to also be able to view the contents of the items in the list, grant Content Explorer Content viewer rights as well.</span></span>

<span data-ttu-id="eae4f-134">사용자 지정 역할 그룹에 역할 중 하나 또는 둘 다를 할당하여 콘텐츠 탐색기에 대한 액세스를 조정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eae4f-134">You can also assign either or both of the roles to a custom role group to tailor access to content explorer.</span></span>

<span data-ttu-id="eae4f-135">전역 관리자, 준수 관리자 또는 데이터 관리자는 필요한 콘텐츠 탐색기 목록 뷰어와 콘텐츠 탐색기 콘텐츠 뷰어 역할 그룹 구성원 자격을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eae4f-135">A Global admin, Compliance admin, or Data admin can assign the necessary Content Explorer List Viewer, and Content Explorer Content Viewer role group membership.</span></span>

## <a name="content-explorer"></a><span data-ttu-id="eae4f-136">콘텐츠 탐색기</span><span class="sxs-lookup"><span data-stu-id="eae4f-136">Content explorer</span></span>

<span data-ttu-id="eae4f-137">콘텐츠 탐색기는 민감도 레이블, 보존 레이블이 있거나, 조직에서 중요한 정보 유형으로 분류된 항목의 현재 스냅샷을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="eae4f-137">Content explorer shows a current snapshot of the items that have a sensitivity label, a retention label or have been classified as a sensitive information type in your organization.</span></span>

### <a name="sensitive-information-types"></a><span data-ttu-id="eae4f-138">중요한 정보 유형</span><span class="sxs-lookup"><span data-stu-id="eae4f-138">Sensitive information types</span></span>

<span data-ttu-id="eae4f-139">[DLP 정책](data-loss-prevention-policies.md)은 **중요한 정보 유형** 으로 정의되어 있는 중요한 정보를 보호하는 데 도움을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eae4f-139">A [DLP policy](data-loss-prevention-policies.md) can help protect sensitive information, which is defined as a **sensitive information type**.</span></span> <span data-ttu-id="eae4f-140">Microsoft 365는 사용자가 사용할 수 있는 많은 지역에서 [흔한 중요한 정보 유형에 대한 정의](sensitive-information-type-entity-definitions.md)를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="eae4f-140">Microsoft 365 includes [definitions for many common sensitive information types](sensitive-information-type-entity-definitions.md) from across many different regions that are ready for you to use.</span></span> <span data-ttu-id="eae4f-141">예를 들면 신용 카드 번호, 은행 계좌 번호, 국가 ID 번호 그리고 Windows Live ID 서비스 번호 등이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eae4f-141">For example, a credit card number, bank account numbers, national ID numbers, and Windows Live ID service numbers.</span></span>

> [!NOTE]
> <span data-ttu-id="eae4f-142">현재 콘텐츠 탐색기에서는 Exchange Online의 중요한 정보 유형을 검사하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eae4f-142">Content explorer doesn't currently scan for sensitive information types in Exchange Online.</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="eae4f-143">민감도 레이블</span><span class="sxs-lookup"><span data-stu-id="eae4f-143">Sensitivity labels</span></span>

<span data-ttu-id="eae4f-144">[민감도 레이블](sensitivity-labels.md)은 단순히 조직에 항목의 값을 나타내는 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="eae4f-144">A [sensitivity label](sensitivity-labels.md) is simply a tag that indicates the value of the item to your organization.</span></span> <span data-ttu-id="eae4f-145">이는 수동으로 또는 자동으로 적용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eae4f-145">It can be applied manually, or automatically.</span></span> <span data-ttu-id="eae4f-146">적용한 후에는 문서에 포함이 되고 문서가 이동하는 곳마다 따르게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eae4f-146">Once applied it gets embedded in the document and will follow it everywhere it goes.</span></span> <span data-ttu-id="eae4f-147">민감도 레이블은 필수 워터마크 또는 암호화와 같은 다양한 보호 작용을 가능하도록 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="eae4f-147">A sensitivity label enables various protective behaviors, such as mandatory watermarking or encryption.</span></span>

<span data-ttu-id="eae4f-148">데이터 분류 페이지에서 해당 데이터를 표시하려면 SharePoint 및 OneDrive에 있는 파일에 민감도 레이블을 사용하도록 설정되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eae4f-148">Sensitivity labels must be enabled for files that are in SharePoint and OneDrive in order for the corresponding data to surface in the data classification page.</span></span> <span data-ttu-id="eae4f-149">자세한 내용은 [SharePoint 및 OneDrive에서 Office 파일에 대한 민감도 레이블 사용](sensitivity-labels-sharepoint-onedrive-files.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eae4f-149">For more information, see [Enable sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

### <a name="retention-labels"></a><span data-ttu-id="eae4f-150">보존 레이블</span><span class="sxs-lookup"><span data-stu-id="eae4f-150">Retention labels</span></span>

<span data-ttu-id="eae4f-151">[보존 레이블](retention.md)을 사용하여 레이블이 부착된 항목이 보관되는 기간 및 삭제하기 전에 수행해야 할 단계를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eae4f-151">A [retention label](retention.md) allows you to define how long a labeled item is kept and the steps to be taken prior to deleting it.</span></span> <span data-ttu-id="eae4f-152">이들은 수동으로 또는 자동으로 정책을 통해 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="eae4f-152">They are applied manually or automatically via policies.</span></span> <span data-ttu-id="eae4f-153">이들은 조직이 법적 그리고 규제적 요구 사항을 계속 준수하는데 도움이 되는 역할을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eae4f-153">They can play a role in helping your organization stay in compliance with legal and regulatory requirements.</span></span>

### <a name="how-to-use-content-explorer"></a><span data-ttu-id="eae4f-154">콘텐츠 탐색기를 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="eae4f-154">How to use content explorer</span></span>

1. <span data-ttu-id="eae4f-155">**Microsoft 365 준수 센터**  > **데이터 분류** > **콘텐츠 탐색기**</span><span class="sxs-lookup"><span data-stu-id="eae4f-155">Open **Microsoft 365 compliance center**  > **Data classification** > **Content explorer**.</span></span>
2. <span data-ttu-id="eae4f-156">레이블 이름 또는 중요한 정보 유형을 알고 있는 경우 필터 상자에 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eae4f-156">If you know the name of the label, or the sensitive information type, you can type that into the filter box.</span></span>
3. <span data-ttu-id="eae4f-157">또는 레이블 유형을 확장하고 목록에서 레이블을 선택하여 항목을 찾아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eae4f-157">Alternately, you can browse for the item by expanding the label type and selecting the label from the list.</span></span>
4. <span data-ttu-id="eae4f-158">**모든 위치** 에서 위치를 선택하고 폴더 구조를 드릴다운하여 해당 항목까지 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="eae4f-158">Select a location under **All locations** and drill down the folder structure to the item.</span></span>
5. <span data-ttu-id="eae4f-159">콘텐츠 탐색기에서 기본적으로 항목을 열려면 두 번 클릭을 합니다.</span><span class="sxs-lookup"><span data-stu-id="eae4f-159">Double-click to open the item natively in content explorer.</span></span>

### <a name="export"></a><span data-ttu-id="eae4f-160">내보내기</span><span class="sxs-lookup"><span data-stu-id="eae4f-160">Export</span></span>
<span data-ttu-id="eae4f-161">**내보내기** 컨트롤은 **모든 위치** 창에 표시되는 모든 항목의 목록을 포함하는 .csv 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="eae4f-161">The **export** control will create a .csv file that contains a listing of whatever is showing in the **All locations** pane.</span></span>

![데이터 분류 내보내기 관리](../media/data_classification_export_control.png)


### <a name="search"></a><span data-ttu-id="eae4f-163">검색</span><span class="sxs-lookup"><span data-stu-id="eae4f-163">Search</span></span>

<span data-ttu-id="eae4f-164">Exchange 폴더나 SharePoint 또는 OneDrive 사이트와 같은 위치로 드릴다운하면 **검색** 도구가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="eae4f-164">When you drill down into a location, such as an Exchange folder, or a SharePoint or OneDrive site, the **search** tool appears.</span></span>

![콘텐츠 탐색기 검색 도구](../media/data_classification_search_tool.png)


<span data-ttu-id="eae4f-166">검색 도구의 범위는 **모든 위치** 창에 표시되는 내용이며 검색 가능한 항목은 선택한 위치에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="eae4f-166">The scope of the search tool is what is displaying in the **All locations** pane and what you can search on varies depending on the selected location.</span></span> 

<span data-ttu-id="eae4f-167">**Exchange** 가 선택된 위치인 경우 사서함의 전체 전자 메일 주소(예: `user@domainname.com`)를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eae4f-167">When **Exchange** is the selected location, you can search on the full email address of the mailbox, for example `user@domainname.com`.</span></span>

<span data-ttu-id="eae4f-168">**SharePoint** 또는 **OneDrive** 가 선택된 위치인 경우 사이트 이름, 폴더 및 파일로 드릴다운하면 검색 도구가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eae4f-168">When either **SharePoint** or **OneDrive** are selected location, the search tool will appear when you drill down to site names, folders and files.</span></span> 

> [!NOTE]
> <span data-ttu-id="eae4f-169">**OneDrive** 미리 보기 프로그램 동안 OneDrive 통합에 대한 유용한 피드백을 잘 들었습니다.</span><span class="sxs-lookup"><span data-stu-id="eae4f-169">**OneDrive** We have listened to your valuable feedback on OneDrive integration during our preview program.</span></span> <span data-ttu-id="eae4f-170">해당 피드백에 따라 OneDrive 기능은 모든 수정 내용이 적용될 때까지 미리 보기에 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="eae4f-170">Based on that feedback, the OneDrive functionality will remain in preview till all fixes are in place.</span></span> <span data-ttu-id="eae4f-171">테넌트에 따라 일부 고객의 경우 OneDrive를 위치로 보지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eae4f-171">Depending on your tenant, some customers may not see OneDrive as a location.</span></span> <span data-ttu-id="eae4f-172">이에 대한 귀하의 지속적인 지원에 감사드립니다.</span><span class="sxs-lookup"><span data-stu-id="eae4f-172">We appreciate your continued support on this.</span></span>

<span data-ttu-id="eae4f-173">다음을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eae4f-173">You can search on:</span></span>


|<span data-ttu-id="eae4f-174">값</span><span class="sxs-lookup"><span data-stu-id="eae4f-174">value</span></span>|<span data-ttu-id="eae4f-175">예</span><span class="sxs-lookup"><span data-stu-id="eae4f-175">example</span></span>  |
|---------|---------|
|<span data-ttu-id="eae4f-176">전체 사이트 이름</span><span class="sxs-lookup"><span data-stu-id="eae4f-176">full site name</span></span>    |`https://contoso.onmicrosoft.com/sites/sitename`    |
|<span data-ttu-id="eae4f-177">루트 폴더 이름 - 모든 하위 폴더를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="eae4f-177">root folder name - gets all subfolders</span></span>    | `/sites`        |
|<span data-ttu-id="eae4f-178">파일 이름</span><span class="sxs-lookup"><span data-stu-id="eae4f-178">file name</span></span>    |    `RES_Resume_1234.txt`     |
|<span data-ttu-id="eae4f-179">파일 이름 시작 부분에 있는 텍스트</span><span class="sxs-lookup"><span data-stu-id="eae4f-179">text at the beginning of file name</span></span>| `RES`|
|<span data-ttu-id="eae4f-180">파일 이름에서 밑줄 문자(_) 다음에 오는 텍스트</span><span class="sxs-lookup"><span data-stu-id="eae4f-180">text after an underscore character ( _ ) in file name</span></span>|<span data-ttu-id="eae4f-181">`Resume` 또는 `1234`</span><span class="sxs-lookup"><span data-stu-id="eae4f-181">`Resume` or `1234`</span></span>| 
|<span data-ttu-id="eae4f-182">파일 확장명</span><span class="sxs-lookup"><span data-stu-id="eae4f-182">file extension</span></span>|`txt`|


## <a name="see-also"></a><span data-ttu-id="eae4f-183">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eae4f-183">See also</span></span>

- [<span data-ttu-id="eae4f-184">민감도 레이블에 대해 알아보기</span><span class="sxs-lookup"><span data-stu-id="eae4f-184">Learn about sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="eae4f-185">보존 정책 및 보존 레이블에 대해 알아보기</span><span class="sxs-lookup"><span data-stu-id="eae4f-185">Learn about retention policies and retention labels</span></span>](retention.md)
- [<span data-ttu-id="eae4f-186">중요한 정보 유형 엔터티 정의.md</span><span class="sxs-lookup"><span data-stu-id="eae4f-186">Sensitive information type entity definitions.md</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="eae4f-187">데이터 손실 방지의 개요</span><span class="sxs-lookup"><span data-stu-id="eae4f-187">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
