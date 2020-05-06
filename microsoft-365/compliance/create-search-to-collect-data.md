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
description: 고급 eDiscovery 사례에서 검색을 위한 custodians 및 custodial 위치를 만들고, 정의 하 고, 선택 하는 방법에 대해 알아봅니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1d9051824ff3f28484d0750b982edd70334a9b88
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035770"
---
# <a name="create-a-search"></a><span data-ttu-id="5f93b-103">검색 만들기</span><span class="sxs-lookup"><span data-stu-id="5f93b-103">Create a search</span></span>

<span data-ttu-id="5f93b-104">사례에 있는 **검색** 탭에서 **새 검색** 을 클릭 하 고 마법사를 수행 하 여 새 검색을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f93b-104">On the **Searches** tab in your case, you can create a new search by clicking **New search** and following the wizard.</span></span>

![고급 eDiscovery 사례의 검색 마법사](../media/AeDSearch1.png)

## <a name="name-the-search-and-give-it-a-description"></a><span data-ttu-id="5f93b-106">검색의 이름을 지정 하 고 설명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f93b-106">Name the search and give it a description</span></span>

<span data-ttu-id="5f93b-107">케이스가 포함 된 각 검색의 이름은 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f93b-107">Each search with a case should have a unique name.</span></span> <span data-ttu-id="5f93b-108">선택적으로 검색에 대 한 설명을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f93b-108">You can optionally provide a description for your search.</span></span> 

## <a name="choose-the-custodians-and-custodial-locations-to-search"></a><span data-ttu-id="5f93b-109">검색할 custodians 및 custodial 위치 선택</span><span class="sxs-lookup"><span data-stu-id="5f93b-109">Choose the custodians and custodial locations to search</span></span>

<span data-ttu-id="5f93b-110">사례에 추가한 custodians를 지정 하 여 custodian 콘텐츠 위치를 검색 하도록 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f93b-110">Choose custodian content locations to search by specifying that custodians you have added to the case.</span></span> <span data-ttu-id="5f93b-111">Custodian를 선택 하 여 custodian에 매핑된 모든 데이터 원본에 대해 검색을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f93b-111">By selecting a custodian, you will run the search against all data sources mapped to the custodian.</span></span> <span data-ttu-id="5f93b-112">또한 각 custodian에 대해 선택한 데이터 원본으로 검색 범위를 좁히는 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f93b-112">You also have the option to narrow the search to selected data sources for each custodian.</span></span> <span data-ttu-id="5f93b-113">Custodians을 추가 하 고 데이터 원본을 관리 하는 방법에 대 한 자세한 내용은 [Work with custodians](managing-custodians.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5f93b-113">For more information about how to add custodians and manage their data sources, see [Work with custodians](managing-custodians.md).</span></span>

## <a name="choose-non-custodial-locations"></a><span data-ttu-id="5f93b-114">비 custodial 위치 선택</span><span class="sxs-lookup"><span data-stu-id="5f93b-114">Choose non-custodial locations</span></span>

<span data-ttu-id="5f93b-115">Custodian와 연결 되지 않은 데이터 원본을 검색 해야 하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f93b-115">In some cases, you may want to search data sources that are not associated with a custodian.</span></span> <span data-ttu-id="5f93b-116">이 경우 검색할 위치를 지정 하거나, 모든 Exchange 사서함 또는 모든 SharePoint 사이트 및 OneDrive 계정을 검색 하는 등의 특정 Microsoft 서비스에 대 한 모든 콘텐츠 위치를 검색 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f93b-116">In this case, you can specify the locations you want to search, or choose to search all content locations for a specific Microsoft service (such as searching all Exchange mailboxes or all SharePoint sites and OneDrive accounts).</span></span>

## <a name="define-the-search-query-and-conditions"></a><span data-ttu-id="5f93b-117">검색 쿼리 및 조건 정의</span><span class="sxs-lookup"><span data-stu-id="5f93b-117">Define the search query and conditions</span></span>

<span data-ttu-id="5f93b-118">미리 작성 된 조건 카드를 사용 하거나 KQL (키워드 쿼리 언어)를 사용 하 여 검색에 대 한 키워드 쿼리 및 조건을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f93b-118">You can define the keywords query and any conditions for the search by using the pre-built condition cards or using Keyword Query Language (KQL).</span></span> <span data-ttu-id="5f93b-119">자세한 내용은 [빌드 검색 쿼리](building-search-queries.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5f93b-119">For more information, see [Build search queries](building-search-queries.md).</span></span>
