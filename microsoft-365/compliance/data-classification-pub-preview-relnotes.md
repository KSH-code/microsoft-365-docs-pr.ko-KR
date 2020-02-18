---
title: 데이터 분류 미리 보기 릴리스 정보(미리 보기)
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
description: 데이터 분류 공개 미리 보기에 대한 릴리스 정보입니다.
ms.openlocfilehash: 1beae92089833327cedf6090690530d9e5457a37
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42076365"
---
# <a name="data-classification-public-preview-release-notes-preview"></a><span data-ttu-id="ee876-103">데이터 분류 공개 미리 보기 릴리스 정보(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="ee876-103">Data classification public preview release notes (preview)</span></span>

<span data-ttu-id="ee876-104">이 공개 미리 보기에는 정책 만들기 *전에* 민감한 콘텐츠와 레이블이 지정된 콘텐츠의 스캔을 시작하는 새로운 기능이 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ee876-104">This public preview introduces new functionality where scanning of your sensitive content and labeled content starts *before* you create any policies.</span></span> <span data-ttu-id="ee876-105">이를 **제로 변경 관리**라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee876-105">This is called **zero change management**.</span></span> <span data-ttu-id="ee876-106">이를 통해 모든 보존 및 민감도 레이블이 환경에 미치는 영향을 확인하고, 보호 및 관리 정책 요구 사항을 평가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee876-106">This lets you see the impact that all the retention and sensitivity labels are having in your environment and empower you to start assessing your protection and governance policy needs.</span></span>

<span data-ttu-id="ee876-107">이 공개 미리 보기를 사용하여 최상의 환경을 활용하려면 이 릴리스 정보를 검토하세요.</span><span class="sxs-lookup"><span data-stu-id="ee876-107">Please review these release notes so that you have the best experience with this public preview.</span></span> <span data-ttu-id="ee876-108">저희는 지금과 GA(일반 가용성) 사이의 이러한 점을 해결하는 작업을 진행하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee876-108">We will be working on addressing these points between now and general availability (GA).</span></span>

## <a name="permissions-for-accessing-content-explorer"></a><span data-ttu-id="ee876-109">콘텐츠 탐색기 액세스 권한</span><span class="sxs-lookup"><span data-stu-id="ee876-109">Permissions for accessing content explorer</span></span>

<span data-ttu-id="ee876-110">콘텐츠 탐색기에 대한 액세스는 검사된 파일의 내용을 읽을 수 있기 때문에 매우 제한적입니다.</span><span class="sxs-lookup"><span data-stu-id="ee876-110">Access to content explorer is highly restricted because it lets you read the contents of scanned files.</span></span> <span data-ttu-id="ee876-111">콘텐츠 탐색기에 액세스하려면 **콘텐츠 탐색기 목록 뷰어**와 **콘텐츠 탐색기 콘텐츠 뷰어**에서 구성원 자격이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ee876-111">Access to content explorer requires membership in the **Content Explorer List Viewer**, and **Content Explorer Content Viewer** role groups.</span></span> <span data-ttu-id="ee876-112">기본적으로는 어떤 계정에서도 콘텐츠 탐색기에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ee876-112">No account has access to content explorer by default.</span></span> <span data-ttu-id="ee876-113">[데이터 분류 콘텐츠 탐색기(미리 보기) 사용](data-classification-content-explorer.md#permissions)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ee876-113">See, [Using data classification content explorer (preview)](data-classification-content-explorer.md#permissions).</span></span> <span data-ttu-id="ee876-114">전역 관리자, 준수 관리자 또는 데이터 관리자는 필요한 **콘텐츠 탐색기 목록 뷰어**와 **콘텐츠 탐색기 콘텐츠 뷰어** 역할 그룹 구성원 자격을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee876-114">A Global admin, Compliance admin, or Data admin can assign the necessary **Content Explorer List Viewer**, and **Content Explorer Content Viewer** role group membership.</span></span>

> [!TIP]
> <span data-ttu-id="ee876-115">**콘텐츠 탐색기 목록 뷰어**와 **콘텐츠 탐색기 콘텐츠 뷰어** 역할 그룹은 RBAC(역할 기반 엑세스 제어)가 세계적으로 배포되는 동안에는 사용 권한 페이지에 표시되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee876-115">The **Content Explorer List Viewer**, and the **Content Explorer Content Viewer** role groups may not appear on the permissions page while the Role Based Access Controls (RBAC) are being deployed worldwide.</span></span> <span data-ttu-id="ee876-116">이들이 사용 권한 페이지에 표시되지 않는 경우 사용자 지정 역할 그룹을 만들고 사용자 지정 역할 그룹에 `data classification list viewer` 역할이나 `data classification content viewer` 역할을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee876-116">If they aren't appearing on the permissions page, you must create a custom role group and assign the `data classification list viewer` role and or the `data classification content viewer` roles to your custom role group.</span></span>

## <a name="exchange-mailbox-count"></a><span data-ttu-id="ee876-117">Exchange 사서함 수</span><span class="sxs-lookup"><span data-stu-id="ee876-117">Exchange mailbox count</span></span>

<span data-ttu-id="ee876-118">Exchange 사서함을 드릴 다운하면 작은 도구 설명이 표시되는 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee876-118">You will notice a small tool tip appear when you drill into Exchange mailboxes.</span></span> <span data-ttu-id="ee876-119">중요한 정보 유형, 민감도 레이블 및 보존 레이블에 대해 표시되는 집계 수가 사서함 내에서 찾을 수 있는 항목 수와 정확히 일치하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee876-119">This is to call out the fact that the aggregate count displayed for sensitive information type, sensitivity label and retention label may not exactly match the number of items that you will find inside the mailbox.</span></span> <span data-ttu-id="ee876-120">이는 폴더로 드릴 다운하면 집계된 카운트가 계산되는 동안 분류된 콘텐츠의 라이브 뷰를 가져오기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="ee876-120">This is because the drill down into the folder fetches the live view of content, which is classified, while the aggregated count is calculated.</span></span>

## <a name="seeing-guids-instead-of-label-names"></a><span data-ttu-id="ee876-121">레이블 이름 대신 GUID 보기</span><span class="sxs-lookup"><span data-stu-id="ee876-121">Seeing GUIDs instead of label names</span></span>

<span data-ttu-id="ee876-122">비공개 미리보기 고객은 콘텐츠를 마이그레이션하거나 컨텐츠가 이미 스탬핑된 레이블을 삭제할 경우, 레이블 이름 대신 컨텐츠 탐색기 및 활동 탐색기에서 32비트 GUID가 되는 인스턴스를 보았습니다.</span><span class="sxs-lookup"><span data-stu-id="ee876-122">Private preview customers have seen instances where the migrated labels or deletion of a label that content has already been stamped with results in label names resolving to a 32-bit GUID in content explorer and activity explorer instead of the label name.</span></span> 

## <a name="rendering-of-encrypted-documents"></a><span data-ttu-id="ee876-123">암호화된 문서 렌더링</span><span class="sxs-lookup"><span data-stu-id="ee876-123">Rendering of encrypted documents</span></span>

<span data-ttu-id="ee876-124">암호화되는 SharePoint, Exchange 및 OneDrive 파일은 콘텐츠 탐색기에서 렌더링되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ee876-124">SharePoint, Exchange, and OneDrive files that are encrypted will not render in the content explorer.</span></span> <span data-ttu-id="ee876-125">이는 콘텐츠 탐색기에서 파일 콘텐츠를 확인할 필요와 콘텐츠를 암호화된 상태로 유지할 필요 사이에 균형을 요구하는 중요한 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="ee876-125">This is a sensitive issue that requires a balance between the need to see file contents in content explorer and the need to keep the contents encrypted.</span></span> <span data-ttu-id="ee876-126">**콘텐츠 탐색기 목록 뷰어** 및 **콘텐츠 탐색기 콘텐츠 뷰어** 역할 그룹에서 부여한 권한으로 파일, 파일, 메타 데이터, 웹 클라이언트를 통해 컨텐츠에 액세스하는 데 사용할 수 있는 링크의 목록 보기를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee876-126">With the permissions granted by **Content Explorer List Viewer**, and **Content Explorer Content Viewer** role groups, you will see a list view of the files, the file  metadata, and a link you can use to access the content via the web client.</span></span>

## <a name="supported-characters-in-retention-label-names-in-sharepoint-search"></a><span data-ttu-id="ee876-127">SharePoint 검색의 보존 레이블 이름에 지원되는 문자</span><span class="sxs-lookup"><span data-stu-id="ee876-127">Supported characters in retention label names in SharePoint search</span></span>

<span data-ttu-id="ee876-128">SharePoint 검색은 `-` 또는 `_`이(가) 포함된 보존 레이블 이름을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ee876-128">SharePoint search does not support retention label names with `-`, or `_` in them.</span></span> <span data-ttu-id="ee876-129">예를 들어 `Label-MIP` 및 `Label_MIP`은(는) 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ee876-129">For example `Label-MIP` and `Label_MIP` are not supported.</span></span> <span data-ttu-id="ee876-130">SharePoint 검색에서는 민감도 레이블 이름 및 중요한 정보 유형 이름의 문자를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ee876-130">SharePoint search does support those characters in sensitivity label names and sensitive information type names.</span></span>

## <a name="see-also"></a><span data-ttu-id="ee876-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ee876-131">See also</span></span>

- [<span data-ttu-id="ee876-132">데이터 분류 시작(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="ee876-132">Get started with data classification (preview)</span></span>](data-classification-overview.md)
- [<span data-ttu-id="ee876-133">레이블 활동 보기(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="ee876-133">View label activity (preview)</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="ee876-134">레이블이 지정된 콘텐츠 보기(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="ee876-134">View labeled content (preview)</span></span>](data-classification-content-explorer.md)
- [<span data-ttu-id="ee876-135">민감도 레이블</span><span class="sxs-lookup"><span data-stu-id="ee876-135">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="ee876-136">보존 레이블</span><span class="sxs-lookup"><span data-stu-id="ee876-136">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="ee876-137">중요한 정보 유형이 찾는 항목</span><span class="sxs-lookup"><span data-stu-id="ee876-137">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

