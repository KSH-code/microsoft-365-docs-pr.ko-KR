---
title: 검색 만들기
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
description: 특정 사례에서 검색을 위해 Advanced eDiscovery, 정의 및 선택하는 방법에 대해 자세히 알아보습니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1d9051824ff3f28484d0750b982edd70334a9b88
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035770"
---
# <a name="create-a-search"></a><span data-ttu-id="44873-103">검색 만들기</span><span class="sxs-lookup"><span data-stu-id="44873-103">Create a search</span></span>

<span data-ttu-id="44873-104">사례의 **검색** 탭에서 새 검색을 클릭하고 마법사를  따라 새 검색을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44873-104">On the **Searches** tab in your case, you can create a new search by clicking **New search** and following the wizard.</span></span>

![검색 사례의 Advanced eDiscovery 마법사](../media/AeDSearch1.png)

## <a name="name-the-search-and-give-it-a-description"></a><span data-ttu-id="44873-106">검색 이름을 지정하고 설명 제공</span><span class="sxs-lookup"><span data-stu-id="44873-106">Name the search and give it a description</span></span>

<span data-ttu-id="44873-107">사례가 있는 각 검색에는 고유한 이름이 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44873-107">Each search with a case should have a unique name.</span></span> <span data-ttu-id="44873-108">원하는 경우 검색에 대한 설명을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44873-108">You can optionally provide a description for your search.</span></span> 

## <a name="choose-the-custodians-and-custodial-locations-to-search"></a><span data-ttu-id="44873-109">검색할 양도자 및 양도 위치 선택</span><span class="sxs-lookup"><span data-stu-id="44873-109">Choose the custodians and custodial locations to search</span></span>

<span data-ttu-id="44873-110">사례에 추가한 수장인을 지정하여 검색할 수 있는 콘텐츠 위치를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="44873-110">Choose custodian content locations to search by specifying that custodians you have added to the case.</span></span> <span data-ttu-id="44873-111">보호자 를 선택하면 보호자에 매핑된 모든 데이터 원본에 대해 검색을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="44873-111">By selecting a custodian, you will run the search against all data sources mapped to the custodian.</span></span> <span data-ttu-id="44873-112">또한 각 보호자에 대해 선택한 데이터 원본으로 검색 범위를 좁힐 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44873-112">You also have the option to narrow the search to selected data sources for each custodian.</span></span> <span data-ttu-id="44873-113">관리인을 추가하고 데이터 원본을 관리하는 방법에 대한 자세한 내용은 보호자에 대한 작업을 [참조하세요.](managing-custodians.md)</span><span class="sxs-lookup"><span data-stu-id="44873-113">For more information about how to add custodians and manage their data sources, see [Work with custodians](managing-custodians.md).</span></span>

## <a name="choose-non-custodial-locations"></a><span data-ttu-id="44873-114">비보조 위치 선택</span><span class="sxs-lookup"><span data-stu-id="44873-114">Choose non-custodial locations</span></span>

<span data-ttu-id="44873-115">경우에 따라 보호자와 연결되지 않은 데이터 원본을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44873-115">In some cases, you may want to search data sources that are not associated with a custodian.</span></span> <span data-ttu-id="44873-116">이 경우 검색할 위치를 지정하거나 특정 Microsoft 서비스의 모든 콘텐츠 위치(예: 모든 Exchange 사서함 또는 모든 SharePoint 사이트 및 OneDrive 계정 검색)를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44873-116">In this case, you can specify the locations you want to search, or choose to search all content locations for a specific Microsoft service (such as searching all Exchange mailboxes or all SharePoint sites and OneDrive accounts).</span></span>

## <a name="define-the-search-query-and-conditions"></a><span data-ttu-id="44873-117">검색 쿼리 및 조건 정의</span><span class="sxs-lookup"><span data-stu-id="44873-117">Define the search query and conditions</span></span>

<span data-ttu-id="44873-118">미리 작성된 조건 카드 또는 KQL(키워드 쿼리 언어)을 사용하여 키워드 쿼리 및 검색 조건을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44873-118">You can define the keywords query and any conditions for the search by using the pre-built condition cards or using Keyword Query Language (KQL).</span></span> <span data-ttu-id="44873-119">자세한 내용은 검색 쿼리 [작성을 참조하세요.](building-search-queries.md)</span><span class="sxs-lookup"><span data-stu-id="44873-119">For more information, see [Build search queries](building-search-queries.md).</span></span>
