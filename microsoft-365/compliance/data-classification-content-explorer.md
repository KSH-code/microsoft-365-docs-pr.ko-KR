---
title: 데이터 분류 콘텐츠 탐색기(미리 보기) 사용
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
ms.openlocfilehash: 6f062901acbf149f6fc56c266d10b370ed0c1112
ms.sourcegitcommit: 8ca97fa879ae4ea44468be629d6c32b429efeeec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2019
ms.locfileid: "39268604"
---
# <a name="using-data-classification-content-explorer-preview"></a><span data-ttu-id="28975-103">데이터 분류 콘텐츠 탐색기(미리 보기) 사용</span><span class="sxs-lookup"><span data-stu-id="28975-103">Using data classification content explorer (preview)</span></span>

<span data-ttu-id="28975-104">데이터 분류 콘텐츠 탐색기를 사용하여 개요 페이지에 요약된 항목을 원래 상태로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28975-104">The data classification content explorer allows you to natively view the items that were summarized on the overview page.</span></span>

## <a name="content-explorer"></a><span data-ttu-id="28975-105">콘텐츠 탐색기</span><span class="sxs-lookup"><span data-stu-id="28975-105">Content explorer</span></span>

<span data-ttu-id="28975-106">콘텐츠 탐색기는 민감도 레이블, 보존 레이블이 있거나, 조직에서 중요한 정보 유형으로 분류된 항목의 현재 스냅샷입니다.</span><span class="sxs-lookup"><span data-stu-id="28975-106">Content explorer is a current snapshot of the items that have a sensitivity label, a retention label or have been classified as a sensitive information type in your organization.</span></span>

![콘텐츠 탐색기 축소 스크린샷](media/data-classification-content-explorer-1.png)

### <a name="permissions"></a><span data-ttu-id="28975-108">사용 권한</span><span class="sxs-lookup"><span data-stu-id="28975-108">Permissions</span></span>

<span data-ttu-id="28975-109">콘텐츠 탐색기에 대한 액세스 권한을 부여하는 두 개의 역할이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28975-109">There are two roles that grant access to Content explorer:</span></span>

- <span data-ttu-id="28975-110">**콘텐츠 탐색기 목록 뷰어**: 이 역할의 멤버 자격으로 각 항목과 해당 위치를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28975-110">**Content Explorer List viewer**: Membership in this role allows you to see each item and its location.</span></span>

- <span data-ttu-id="28975-111">**콘텐츠 탐색기 콘텐츠 뷰어**:이 역할의 멤버 자격으로 목록에 있는 각 항목의 내용을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28975-111">**Content Explorer Content viewer**: Membership in this role allows you to view the contents of each item in the list.</span></span>

<span data-ttu-id="28975-112">콘텐츠 탐색기에 액세스하는 데 사용하는 계정은 역할 중 하나 또는 둘 다에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="28975-112">The account you use to access Content explorer must be in one or both of the roles.</span></span> <span data-ttu-id="28975-113">이러한 역할은 독립적인 역할이며 누적되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="28975-113">These are independent roles and are not cumulative.</span></span> <span data-ttu-id="28975-114">예를 들어 계정에 항목 및 해당 위치만 볼 수 있는 권한을 부여 하려는 경우 콘텐츠 탐색기 목록 표시기 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="28975-114">For example, if you want to grant an account the ability to view the items and their locations only, grant Content Explorer List viewer rights.</span></span> <span data-ttu-id="28975-115">동일한 계정에서 목록에 있는 항목의 내용을 볼 수 있게 하려면 콘텐츠 탐색기 콘텐츠 뷰어 권한도 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="28975-115">If you want that same account to also be able to view the contents of the items in the list, grant Content Explorer Content viewer rights as well.</span></span>

### <a name="how-to-use-content-explorer"></a><span data-ttu-id="28975-116">콘텐츠 탐색기를 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="28975-116">How to use content explorer</span></span>

1. <span data-ttu-id="28975-117">**Microsoft 365 준수 센터**  > **데이터 분류** > **콘텐츠 탐색기**</span><span class="sxs-lookup"><span data-stu-id="28975-117">Open **Microsoft 365 compliance center**  > **Data classification** > **Content explorer**.</span></span>
2. <span data-ttu-id="28975-118">레이블 이름 또는 중요한 정보 유형을 알고 있는 경우 검색 상자에 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28975-118">If you know the name of the label, or the sensitive information type, you can type that into the search box.</span></span>
3. <span data-ttu-id="28975-119">또는 레이블 유형을 확장하고 목록에서 레이블을 선택하여 항목을 찾아볼 수 있으며, 목록의 보존 레이블 영역에 포함된 항목이 아래에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="28975-119">Alternately, you can browse for the item by expanding the label type and selecting the label from the list, an item from the retention label portion of the list is show below.</span></span>
4. <span data-ttu-id="28975-120">**모든 위치**에서 위치를 선택하고 폴더 구조를 드릴다운하여 해당 항목까지 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="28975-120">Select a location under **All locations** and drill down the folder structure to the item.</span></span>
5. <span data-ttu-id="28975-121">콘텐츠 탐색기에서 기본적으로 항목을 열려면 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="28975-121">Double click to open the item natively in content explorer.</span></span>

## <a name="see-also"></a><span data-ttu-id="28975-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="28975-122">See also</span></span>

- [<span data-ttu-id="28975-123">민감도 레이블</span><span class="sxs-lookup"><span data-stu-id="28975-123">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="28975-124">보존 레이블</span><span class="sxs-lookup"><span data-stu-id="28975-124">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="28975-125">중요한 정보 유형이 찾는 항목</span><span class="sxs-lookup"><span data-stu-id="28975-125">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="28975-126">보존 정책 개요</span><span class="sxs-lookup"><span data-stu-id="28975-126">Overview of retention policies</span></span>](retention-policies.md)
