---
title: 테마
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
description: ''
ms.openlocfilehash: 4387c5e8fc199f0f8642041473d5f28f2f9b401b
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601385"
---
# <a name="themes"></a><span data-ttu-id="12f44-102">테마</span><span class="sxs-lookup"><span data-stu-id="12f44-102">Themes</span></span>

<span data-ttu-id="12f44-103">사용자가 문서를 작성 하는 방법은 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="12f44-103">How does a person write a document?</span></span> <span data-ttu-id="12f44-104">일반적으로 문서에서 전달 하려는 하나 이상의 아이디어를 시작 하 고 아이디어와 일치 하는 단어를 사용 하 여 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="12f44-104">They generally start with one or more ideas they want to convey in the document, and compose using words that align with the ideas.</span></span> <span data-ttu-id="12f44-105">가장 많이 알려진 개념은 해당 아이디어와 관련 된 단어의 빈도가 가장 많습니다.</span><span class="sxs-lookup"><span data-stu-id="12f44-105">The more prevalent an idea is, the more frequent the words that are related to that idea tend to be.</span></span> <span data-ttu-id="12f44-106">사용자가 문서를 사용 하는 방법에 대해 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="12f44-106">This informs how people consume documents as well.</span></span> <span data-ttu-id="12f44-107">문서를 읽을 때 이해 해야 하는 중요 한 사항은 문서에서 전달을 시도 하는 내용, 해당 위치에 표시 되는 개념 및 아이디어 간의 관계입니다.</span><span class="sxs-lookup"><span data-stu-id="12f44-107">The important thing to understand from reading a document is the ideas that the document is trying to convey, which ideas appear where, and what the relationships between the ideas are.</span></span>

<span data-ttu-id="12f44-108">이를 통해 사용자가 문서 집합을 사용 하는 방법으로 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12f44-108">This can be extended to how a person wants to consume a set of documents.</span></span> <span data-ttu-id="12f44-109">이러한 사용자는 집합에 있는 아이디어와 이러한 아이디어에 대해 어떤 문서를 말하고 있는지 확인 하고자 합니다.</span><span class="sxs-lookup"><span data-stu-id="12f44-109">They want to see which ideas are present in the sets, and which documents are talking about those ideas.</span></span> <span data-ttu-id="12f44-110">또한 관심 있는 특정 문서를 찾으면 비슷한 내용을 설명 하는 문서를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12f44-110">Also, if they find a particular document of interest, they want to be able to see documents that discuss similar ideas.</span></span>

<span data-ttu-id="12f44-111">고급 eDiscovery의 테마 기능은 검토 집합에 설명 되어 있는 *테마* 를 분석 하 고 검토 집합의 문서에 테마를 지정 하 여 문서에 대 한 이유를 모방 합니다.</span><span class="sxs-lookup"><span data-stu-id="12f44-111">The Themes functionality in Advanced eDiscovery attempts to mimic how humans reason about documents, by analyzing the *themes* that are discussed in a review set and assigning a theme to documents in the review set.</span></span> <span data-ttu-id="12f44-112">고급 eDiscovery에서 테마는 한 단계 더 나아가 각 문서에서 *기준 테마* 를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="12f44-112">In Advanced eDiscovery, Themes goes one step further and identifies the *dominant theme* in each document.</span></span> <span data-ttu-id="12f44-113">주요 테마는 문서에서 가장 자주 표시 되는 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="12f44-113">The dominant theme is the one that appears the most often in a document.</span></span>

## <a name="how-does-themes-work"></a><span data-ttu-id="12f44-114">테마는 어떻게 작동 하나요?</span><span class="sxs-lookup"><span data-stu-id="12f44-114">How does Themes work?</span></span>

<span data-ttu-id="12f44-115">테마 기능은 검토 집합의 텍스트를 사용 하 여 문서를 분석 하 여 검토 집합의 모든 문서에 표시 되는 일반적인 테마를 구문 분석 합니다.</span><span class="sxs-lookup"><span data-stu-id="12f44-115">The Themes functionality analyzes documents with text in a review set to parse out common themes that appear across all the documents in the review set.</span></span> <span data-ttu-id="12f44-116">Advanced eDiscovery는 해당 테마를 표시 되는 문서에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="12f44-116">Advanced eDiscovery assigns those themes to the documents in which they appear.</span></span> <span data-ttu-id="12f44-117">또한 테마를 대표 하는 문서에 사용 된 단어와 각 테마에 레이블을 붙입니다.</span><span class="sxs-lookup"><span data-stu-id="12f44-117">It also labels each theme with the words used in the documents that are representative of the theme.</span></span> <span data-ttu-id="12f44-118">문서에는 다양 한 유형의 주제가 포함 될 수 있으므로 고급 eDiscovery에서는 문서에 여러 테마를 할당 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="12f44-118">Because a document can contain various types of subject matter, Advanced eDiscovery often assigns multiple themes to documents.</span></span> <span data-ttu-id="12f44-119">문서에서 가장 두드러지게 표시 되는 테마는 기준 테마로 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="12f44-119">The theme that appears most prominently in a document is designated as its dominant theme.</span></span>