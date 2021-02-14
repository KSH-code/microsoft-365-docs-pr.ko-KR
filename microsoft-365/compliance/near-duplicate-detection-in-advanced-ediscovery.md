---
title: 중복에 가까운 검색 - eDiscovery
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
description: Advanced eDiscovery에서 사례 데이터를 분석할 때 중복에 가까운 검색을 사용하여 텍스트와 유사한 문서를 그룹화합니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 255531897a1706904005034c56cab00d0032b7f3
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/26/2020
ms.locfileid: "48286024"
---
# <a name="near-duplicate-detection-in-advanced-ediscovery"></a><span data-ttu-id="7226a-103">Advanced eDiscovery의 중복에 가까운 검색</span><span class="sxs-lookup"><span data-stu-id="7226a-103">Near duplicate detection in Advanced eDiscovery</span></span>

<span data-ttu-id="7226a-104">하위 집합이 동일한 템플릿을 기반으로 하여 대부분 동일한 상용구 언어를 사용하는 문서 집합을 검토할 수 있으며 여기서 몇 가지 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-104">Consider a set of documents to be reviewed in which a subset is based on the same template and has mostly the same boilerplate language, with a few differences here and there.</span></span> <span data-ttu-id="7226a-105">검토자들이 이 하위 집합을 식별하고, 해당 하위 집합 중 하나를 철저하게 검토하고 나머지 부분의 차이점을 검토할 수 있는 경우, 모든 문서가 다루는 모든 문서를 읽는 데 몇 시간의 시간만 들이면서 고유한 정보를 놓치지 않을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-105">If a reviewer could identify this subset, review one of them thoroughly, and review the differences for the rest, they would not have missed any unique information while taking only a fraction of time that would have taken them to read all documents cover to cover.</span></span> <span data-ttu-id="7226a-106">중복에 가까운 검색 그룹은 텍스트적으로 유사한 문서를 함께 사용하여 검토 프로세스의 효율성을 높입니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-106">Near duplicate detection groups textually similar documents together to help you make your review process more efficient.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="7226a-107">작동 방식</span><span class="sxs-lookup"><span data-stu-id="7226a-107">How does it work?</span></span>

<span data-ttu-id="7226a-108">중복에 가까운 검색이 실행될 때 시스템은 모든 문서를 텍스트로 구문 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-108">When near duplicate detection is run, the system parses every document with text.</span></span> <span data-ttu-id="7226a-109">그런 다음 모든 문서를 비교하여 유사성의 설정 임계값보다 큰지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-109">Then, it compares every document against each other to determine whether their similarity is greater than the set threshold.</span></span> <span data-ttu-id="7226a-110">그룹화되어 있는 경우 문서는 함께 그룹화됩니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-110">If it is, the documents are grouped together.</span></span> <span data-ttu-id="7226a-111">모든 문서를 비교하고 그룹화하면 각 그룹의 문서가 "피벗"으로 표시됩니다. 문서를 검토할 때 먼저 피벗을 검토하고 동일한 복제본 집합의 다른 문서를 검토하여 검토할 피벗과 검토할 문서 간의 차이점에 중점을 안안을 두어 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-111">Once all documents have been compared and grouped, a document from each group is marked as the "pivot"; in reviewing your documents, you can review a pivot first and review the other documents in the same near duplicate set, focusing on the difference between the pivot and the document that is in review.</span></span>
