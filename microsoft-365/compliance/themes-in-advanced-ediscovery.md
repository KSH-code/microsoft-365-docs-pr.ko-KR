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
description: 각 문서에서 Advanced eDiscovery 테마를 찾아 검토 집합을 구성할 수 있습니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3dfc0dca0c6ed62e3ce8384efa2fd3ea407c3ce8
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285534"
---
# <a name="themes-in-advanced-ediscovery"></a><span data-ttu-id="8489d-103">Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="8489d-103">Themes in Advanced eDiscovery</span></span>

<span data-ttu-id="8489d-104">사람이 문서를 작성하는 방법</span><span class="sxs-lookup"><span data-stu-id="8489d-104">How does a person write a document?</span></span> <span data-ttu-id="8489d-105">일반적으로 문서에 전달하려는 하나 이상의 아이디어로 시작하고 아이디어에 부합하는 단어를 사용하여 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="8489d-105">They generally start with one or more ideas they want to convey in the document, and compose using words that align with the ideas.</span></span> <span data-ttu-id="8489d-106">아이디어가 더 많이 사용될수록 아이디어와 관련된 단어가 더 자주 사용되는 경향이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8489d-106">The more prevalent an idea is, the more frequent the words that are related to that idea tend to be.</span></span> <span data-ttu-id="8489d-107">이렇게 하면 문서 사용 방법도 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8489d-107">This informs how people consume documents as well.</span></span> <span data-ttu-id="8489d-108">문서 읽기에서 이해해야 할 중요한 점은 문서가 전달하려는 아이디어, 어디에 어떤 아이디어가 나타나는지, 아이디어 간의 관계입니다.</span><span class="sxs-lookup"><span data-stu-id="8489d-108">The important thing to understand from reading a document is the ideas that the document is trying to convey, which ideas appear where, and what the relationships between the ideas are.</span></span>

<span data-ttu-id="8489d-109">이러한 방식은 문서 집합을 사용하려는 사용자로 확장될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8489d-109">This can be extended to how a person wants to consume a set of documents.</span></span> <span data-ttu-id="8489d-110">집합에 있는 아이디어와 해당 아이디어에 대해 이야기하는 문서를 보고자 합니다.</span><span class="sxs-lookup"><span data-stu-id="8489d-110">They want to see which ideas are present in the sets, and which documents are talking about those ideas.</span></span> <span data-ttu-id="8489d-111">또한 관심 있는 특정 문서를 찾으면 유사한 아이디어를 논의하는 문서를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8489d-111">Also, if they find a particular document of interest, they want to be able to see documents that discuss similar ideas.</span></span>

<span data-ttu-id="8489d-112">이 문서의 테마 Advanced eDiscovery 검토 집합에 설명된 테마를 분석하고 검토 집합의 문서에 테마를 할당하여 문서에 대한 사람의 이유를 모방하려고 합니다. </span><span class="sxs-lookup"><span data-stu-id="8489d-112">The Themes functionality in Advanced eDiscovery attempts to mimic how humans reason about documents, by analyzing the *themes* that are discussed in a review set and assigning a theme to documents in the review set.</span></span> <span data-ttu-id="8489d-113">이 Advanced eDiscovery 테마는 한 단계 더 진행하고  각 문서의 주 테마를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="8489d-113">In Advanced eDiscovery, Themes goes one step further and identifies the *dominant theme* in each document.</span></span> <span data-ttu-id="8489d-114">가장 자주 나타나는 테마는 문서에서 가장 자주 나타나는 테마입니다.</span><span class="sxs-lookup"><span data-stu-id="8489d-114">The dominant theme is the one that appears the most often in a document.</span></span>

## <a name="how-does-themes-work"></a><span data-ttu-id="8489d-115">테마 작동 방식</span><span class="sxs-lookup"><span data-stu-id="8489d-115">How does Themes work?</span></span>

<span data-ttu-id="8489d-116">테마 기능은 검토 집합의 모든 문서에 걸쳐 나타나는 일반적인 테마를 구문 분석하기 위해 검토 집합의 텍스트로 문서를 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="8489d-116">The Themes functionality analyzes documents with text in a review set to parse out common themes that appear across all the documents in the review set.</span></span> <span data-ttu-id="8489d-117">고급 eDiscovery에서는 해당 테마가 나타나는 문서에 해당 테마를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="8489d-117">Advanced eDiscovery assigns those themes to the documents in which they appear.</span></span> <span data-ttu-id="8489d-118">또한 각 테마에 테마를 대표하는 문서에서 사용된 단어로 레이블을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8489d-118">It also labels each theme with the words used in the documents that are representative of the theme.</span></span> <span data-ttu-id="8489d-119">문서에 다양한 유형의 주제가 포함될 수 있기 때문에 고급 eDiscovery에서는 문서에 여러 테마를 할당하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8489d-119">Because a document can contain various types of subject matter, Advanced eDiscovery often assigns multiple themes to documents.</span></span> <span data-ttu-id="8489d-120">문서에서 가장 눈에 띄게 나타나는 테마는 주로 나타나는 테마로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="8489d-120">The theme that appears most prominently in a document is designated as its dominant theme.</span></span>
