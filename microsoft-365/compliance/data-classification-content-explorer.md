---
title: 데이터 분류 콘텐츠 탐색기(미리 보기) 사용
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
search.appverid:
- MOE150
- MET150
description: 콘텐츠 탐색기를 사용하여 레이블이 지정된 항목을 원래 상태로 볼 수 있습니다.
ms.openlocfilehash: 2d9be42c00940bf9d37d1fdeb9b15b071aa412ac
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42076433"
---
# <a name="using-data-classification-content-explorer-preview"></a><span data-ttu-id="51fc1-103">데이터 분류 콘텐츠 탐색기(미리 보기) 사용</span><span class="sxs-lookup"><span data-stu-id="51fc1-103">Using data classification content explorer (preview)</span></span>

<span data-ttu-id="51fc1-104">데이터 분류 콘텐츠 탐색기를 사용하여 개요 페이지에 요약된 항목을 원래 상태로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51fc1-104">The data classification content explorer allows you to natively view the items that were summarized on the overview page.</span></span>

## <a name="content-explorer"></a><span data-ttu-id="51fc1-105">콘텐츠 탐색기</span><span class="sxs-lookup"><span data-stu-id="51fc1-105">Content explorer</span></span>

<span data-ttu-id="51fc1-106">콘텐츠 탐색기는 민감도 레이블, 보존 레이블이 있거나, 조직에서 중요한 정보 유형으로 분류된 항목의 현재 스냅샷을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="51fc1-106">Content explorer shows a current snapshot of the items that have a sensitivity label, a retention label or have been classified as a sensitive information type in your organization.</span></span>

### <a name="sensitive-information-types"></a><span data-ttu-id="51fc1-107">중요한 정보 유형</span><span class="sxs-lookup"><span data-stu-id="51fc1-107">Sensitive information types</span></span>

<span data-ttu-id="51fc1-108">[DLP 정책](data-loss-prevention-policies.md)은 **중요한 정보 유형**으로 정의되어 있는 중요한 정보를 보호하는 데 도움을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51fc1-108">A [DLP policy](data-loss-prevention-policies.md) can help protect sensitive information, which is defined as a **sensitive information type**.</span></span> <span data-ttu-id="51fc1-109">Microsoft 365는 사용자가 사용할 수 있는 많은 지역에서 [흔한 중요한 정보 유형에 대한 정의](what-the-sensitive-information-types-look-for.md)를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="51fc1-109">Microsoft 365 includes [definitions for many common sensitive information types](what-the-sensitive-information-types-look-for.md) across many different regions that are ready for you to use.</span></span> <span data-ttu-id="51fc1-110">예를 들면 신용 카드 번호, 은행 계좌 번호, 국가 ID 번호 그리고 Windows Live ID 서비스 번호 등이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51fc1-110">For example, a credit card number, bank account numbers, national ID numbers, and Windows Live ID service numbers.</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="51fc1-111">민감도 레이블</span><span class="sxs-lookup"><span data-stu-id="51fc1-111">Sensitivity labels</span></span>

<span data-ttu-id="51fc1-112">[민감도 레이블](sensitivity-labels.md)은 단순히 조직에 항목의 값을 나타내는 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="51fc1-112">A [sensitivity label](sensitivity-labels.md) is simply a tag that indicates the value of the item to your organization.</span></span> <span data-ttu-id="51fc1-113">이는 수동으로 또는 자동으로 적용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51fc1-113">It can be applied manually, or automatically.</span></span> <span data-ttu-id="51fc1-114">적용한 후에는 문서에 포함이 되고 문서가 이동하는 곳마다 따르게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="51fc1-114">Once applied it gets embedded in the document and will follow it everywhere it goes.</span></span> <span data-ttu-id="51fc1-115">민감도 레이블은 필수 워터마크 또는 암호화와 같은 다양한 보호 작용을 가능하도록 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="51fc1-115">A sensitivity label enables various protective behaviors, such as mandatory watermarking or encryption.</span></span> <span data-ttu-id="51fc1-116">엔드포인트 보호를 사용하도록 설정한 경우 항목이 조직의 컨트롤을 벗어나지 않도록 방지할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51fc1-116">With end point protection enabled you can even prevent an item from leaving your organizational control.</span></span>

<span data-ttu-id="51fc1-117">데이터 분류 페이지에서 해당 데이터를 표시하려면 SharePoint 및 OneDrive에 있는 파일에 민감도 레이블을 사용하도록 설정되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51fc1-117">Sensitivity labels must be enabled for files that are in SharePoint and OneDrive in order for the corresponding data to surface in the data classification page.</span></span> <span data-ttu-id="51fc1-118">자세한 내용은 [SharePoint 및 OneDrive에서 Office 파일에 대한 민감도 레이블 사용(공개 미리 보기)](sensitivity-labels-sharepoint-onedrive-files.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="51fc1-118">For more information, see [Enable sensitivity labels for Office files in SharePoint and OneDrive (public preview)](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

### <a name="retention-labels"></a><span data-ttu-id="51fc1-119">보존 레이블</span><span class="sxs-lookup"><span data-stu-id="51fc1-119">Retention labels</span></span>

<span data-ttu-id="51fc1-120">[보존 레이블](labels.md)을 사용하여 레이블이 부착된 항목이 보관되는 기간 및 삭제하기 전에 수행해야 할 단계를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51fc1-120">A [retention label](labels.md) allows you to define how long a labeled item is kept and the steps to be taken prior to deleting it.</span></span> <span data-ttu-id="51fc1-121">이들은 수동으로 또는 자동으로 정책을 통해 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="51fc1-121">They are applied manually or automatically via policies.</span></span> <span data-ttu-id="51fc1-122">이들은 조직이 법적 그리고 규제적 요구 사항을 계속 준수하는데 도움이 되는 역할을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51fc1-122">They can play a role in helping your organization stay in compliance with legal and regulatory requirements.</span></span>

![콘텐츠 탐색기 축소 스크린샷](../media/data-classification-content-explorer-1.png)

### <a name="permissions"></a><span data-ttu-id="51fc1-124">사용 권한</span><span class="sxs-lookup"><span data-stu-id="51fc1-124">Permissions</span></span>

<span data-ttu-id="51fc1-125">콘텐츠 탐색기에 대한 액세스 권한을 부여하는 두 개의 역할이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51fc1-125">There are two roles that grant access to content explorer:</span></span>

- <span data-ttu-id="51fc1-126">**콘텐츠 탐색기 목록 뷰어**: 이 역할 그룹의 멤버 자격으로 각 항목과 해당 위치를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51fc1-126">**Content Explorer List viewer**: Membership in this role group allows you to see each item and its location.</span></span> <span data-ttu-id="51fc1-127">`data classification list viewer` 역할이 사전에 이 역할 그룹에 할당되었습니다.</span><span class="sxs-lookup"><span data-stu-id="51fc1-127">The `data classification list viewer` role has been pre-assigned to this role group.</span></span>

- <span data-ttu-id="51fc1-128">**콘텐츠 탐색기 콘텐츠 뷰어**:이 역할 그룹의 멤버 자격으로 목록에 있는 각 항목의 내용을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51fc1-128">**Content Explorer Content viewer**: Membership in this role group allows you to view the contents of each item in the list.</span></span> <span data-ttu-id="51fc1-129">`data classification content viewer` 역할이 사전에 이 역할 그룹에 할당되었습니다.</span><span class="sxs-lookup"><span data-stu-id="51fc1-129">The `data classification content viewer` role has been pre-assigned to this role group.</span></span>

<span data-ttu-id="51fc1-130">콘텐츠 탐색기에 액세스하는 데 사용하는 계정은 역할 그룹 중 하나 또는 둘 다에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51fc1-130">The account you use to access content explorer must be in one or both of the role groups.</span></span> <span data-ttu-id="51fc1-131">이러한 역할은 독립적인 역할 그룹이며 누적되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="51fc1-131">These are independent role groups and are not cumulative.</span></span> <span data-ttu-id="51fc1-132">예를 들어 계정에 항목 및 해당 위치만 볼 수 있는 권한을 부여 하려는 경우 콘텐츠 탐색기 목록 표시기 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="51fc1-132">For example, if you want to grant an account the ability to view the items and their locations only, grant Content Explorer List viewer rights.</span></span> <span data-ttu-id="51fc1-133">동일한 계정에서 목록에 있는 항목의 내용을 볼 수 있게 하려면 콘텐츠 탐색기 콘텐츠 뷰어 권한도 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="51fc1-133">If you want that same account to also be able to view the contents of the items in the list, grant Content Explorer Content viewer rights as well.</span></span>

<span data-ttu-id="51fc1-134">사용자 지정 역할 그룹에 역할 중 하나 또는 둘 다를 할당하여 콘텐츠 탐색기에 대한 액세스를 조정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51fc1-134">You can also assign either or both of the roles to a custom role group to tailor access to content explorer.</span></span>

### <a name="how-to-use-content-explorer"></a><span data-ttu-id="51fc1-135">콘텐츠 탐색기를 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="51fc1-135">How to use content explorer</span></span>

1. <span data-ttu-id="51fc1-136">**Microsoft 365 준수 센터**  > **데이터 분류** > **콘텐츠 탐색기**</span><span class="sxs-lookup"><span data-stu-id="51fc1-136">Open **Microsoft 365 compliance center**  > **Data classification** > **Content explorer**.</span></span>
2. <span data-ttu-id="51fc1-137">레이블 이름 또는 중요한 정보 유형을 알고 있는 경우 검색 상자에 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51fc1-137">If you know the name of the label, or the sensitive information type, you can type that into the search box.</span></span>
3. <span data-ttu-id="51fc1-138">또는 레이블 유형을 확장하고 목록에서 레이블을 선택하여 항목을 찾아볼 수 있으며, 목록의 보존 레이블 영역에 포함된 항목이 아래에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="51fc1-138">Alternately, you can browse for the item by expanding the label type and selecting the label from the list, an item from the retention label portion of the list is show below.</span></span>
4. <span data-ttu-id="51fc1-139">**모든 위치**에서 위치를 선택하고 폴더 구조를 드릴다운하여 해당 항목까지 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="51fc1-139">Select a location under **All locations** and drill down the folder structure to the item.</span></span>
5. <span data-ttu-id="51fc1-140">콘텐츠 탐색기에서 기본적으로 항목을 열려면 두 번 클릭을 합니다.</span><span class="sxs-lookup"><span data-stu-id="51fc1-140">Double-click to open the item natively in content explorer.</span></span>

## <a name="see-also"></a><span data-ttu-id="51fc1-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="51fc1-141">See also</span></span>

- [<span data-ttu-id="51fc1-142">민감도 레이블</span><span class="sxs-lookup"><span data-stu-id="51fc1-142">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="51fc1-143">보존 레이블</span><span class="sxs-lookup"><span data-stu-id="51fc1-143">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="51fc1-144">중요한 정보 유형이 찾는 항목</span><span class="sxs-lookup"><span data-stu-id="51fc1-144">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="51fc1-145">보존 정책 개요</span><span class="sxs-lookup"><span data-stu-id="51fc1-145">Overview of retention policies</span></span>](retention-policies.md)
- [<span data-ttu-id="51fc1-146">데이터 손실 방지의 개요</span><span class="sxs-lookup"><span data-stu-id="51fc1-146">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
