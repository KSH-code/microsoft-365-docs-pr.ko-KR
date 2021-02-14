---
title: 테마 - eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Advanced eDiscovery의 테마를 사용하여 각 문서에서 주 테마를 찾아 검토 집합을 구성합니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3dfc0dca0c6ed62e3ce8384efa2fd3ea407c3ce8
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285534"
---
# <a name="themes-in-advanced-ediscovery"></a><span data-ttu-id="02558-103">Advanced eDiscovery의 테마</span><span class="sxs-lookup"><span data-stu-id="02558-103">Themes in Advanced eDiscovery</span></span>

<span data-ttu-id="02558-104">사람이 문서를 작성하는 방법</span><span class="sxs-lookup"><span data-stu-id="02558-104">How does a person write a document?</span></span> <span data-ttu-id="02558-105">일반적으로는 문서에 전달하려는 하나 이상의 아이디어로 시작하고 아이디어에 부합하는 단어를 사용하여 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="02558-105">They generally start with one or more ideas they want to convey in the document, and compose using words that align with the ideas.</span></span> <span data-ttu-id="02558-106">아이디어가 더 많이 사용될수록 아이디어와 관련된 단어가 더 자주 사용되는 경향이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02558-106">The more prevalent an idea is, the more frequent the words that are related to that idea tend to be.</span></span> <span data-ttu-id="02558-107">이렇게 하면 문서 사용 방식도 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02558-107">This informs how people consume documents as well.</span></span> <span data-ttu-id="02558-108">문서를 읽을 때 이해해야 할 중요한 점은 문서가 전달하려는 아이디어, 어디에 어떤 아이디어가 표시되어 있으며, 아이디어 간의 관계입니다.</span><span class="sxs-lookup"><span data-stu-id="02558-108">The important thing to understand from reading a document is the ideas that the document is trying to convey, which ideas appear where, and what the relationships between the ideas are.</span></span>

<span data-ttu-id="02558-109">이 방식은 문서 집합을 사용하려는 방법까지 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02558-109">This can be extended to how a person wants to consume a set of documents.</span></span> <span data-ttu-id="02558-110">집합에 있는 아이디어와 이러한 아이디어에 대해 대화하는 문서를 보고자 합니다.</span><span class="sxs-lookup"><span data-stu-id="02558-110">They want to see which ideas are present in the sets, and which documents are talking about those ideas.</span></span> <span data-ttu-id="02558-111">또한 관심 있는 특정 문서를 찾은 경우 유사한 아이디어를 논의하는 문서를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02558-111">Also, if they find a particular document of interest, they want to be able to see documents that discuss similar ideas.</span></span>

<span data-ttu-id="02558-112">Advanced eDiscovery의 테마 기능은 검토 집합에 설명된 테마를 분석하고 검토  집합의 문서에 테마를 할당하여 문서에 대한 사람의 이유와 모방하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="02558-112">The Themes functionality in Advanced eDiscovery attempts to mimic how humans reason about documents, by analyzing the *themes* that are discussed in a review set and assigning a theme to documents in the review set.</span></span> <span data-ttu-id="02558-113">Advanced eDiscovery에서 테마는 한 단계 더  진행하고 각 문서의 주 테마를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="02558-113">In Advanced eDiscovery, Themes goes one step further and identifies the *dominant theme* in each document.</span></span> <span data-ttu-id="02558-114">주된 테마는 문서에서 가장 자주 나타나는 테마입니다.</span><span class="sxs-lookup"><span data-stu-id="02558-114">The dominant theme is the one that appears the most often in a document.</span></span>

## <a name="how-does-themes-work"></a><span data-ttu-id="02558-115">테마 작동 방식</span><span class="sxs-lookup"><span data-stu-id="02558-115">How does Themes work?</span></span>

<span data-ttu-id="02558-116">테마 기능은 검토 집합에 텍스트가 있는 문서를 분석하여 검토 집합의 모든 문서에 걸쳐 나타나는 일반적인 테마를 구문 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="02558-116">The Themes functionality analyzes documents with text in a review set to parse out common themes that appear across all the documents in the review set.</span></span> <span data-ttu-id="02558-117">Advanced eDiscovery는 해당 테마가 나타나는 문서에 해당 테마를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="02558-117">Advanced eDiscovery assigns those themes to the documents in which they appear.</span></span> <span data-ttu-id="02558-118">또한 문서에서 사용된 단어가 테마를 대표하는 단어로 각 테마에 레이블을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="02558-118">It also labels each theme with the words used in the documents that are representative of the theme.</span></span> <span data-ttu-id="02558-119">문서에는 다양한 유형의 주제가 포함될 수 있기 때문에 Advanced eDiscovery는 문서에 여러 테마를 할당하는 경우가 종종 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02558-119">Because a document can contain various types of subject matter, Advanced eDiscovery often assigns multiple themes to documents.</span></span> <span data-ttu-id="02558-120">문서에서 가장 두드러진 것으로 나타나는 테마는 해당 주된 테마로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="02558-120">The theme that appears most prominently in a document is designated as its dominant theme.</span></span>
