---
title: Microsoft 365 Defender 고급 헌팅의 이름 변경 사항
description: 고급 헌팅chema에서 이름 변경 테이블 및 열 추적 및 검토
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 위협 방지, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, schema reference, kusto, table, data, naming changes, rename, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 483fedd1fb152e3df5311c981b305e621ec2aec3
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932205"
---
# <a name="advanced-hunting-schema---naming-changes"></a><span data-ttu-id="1f0e2-104">고급 헌팅 스마 - 이름 변경</span><span class="sxs-lookup"><span data-stu-id="1f0e2-104">Advanced hunting schema - Naming changes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1f0e2-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="1f0e2-105">**Applies to:**</span></span>
- <span data-ttu-id="1f0e2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1f0e2-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="1f0e2-107">고급 [헌팅 스마는](advanced-hunting-schema-tables.md) 정기적으로 업데이트되어 새 테이블과 열을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1f0e2-107">The [advanced hunting schema](advanced-hunting-schema-tables.md) is updated regularly to add new tables and columns.</span></span> <span data-ttu-id="1f0e2-108">사용자 환경을 개선하기 위해 기존 열 이름을 바꾸거나 바꾸는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f0e2-108">In some cases, existing columns names are renamed or replaced to improve the user experience.</span></span> <span data-ttu-id="1f0e2-109">이 문서를 참조하여 쿼리에 영향을 줄 수 있는 이름 변경 내용을 검토하세요.</span><span class="sxs-lookup"><span data-stu-id="1f0e2-109">Refer to this article to review naming changes that could impact your queries.</span></span>

<span data-ttu-id="1f0e2-110">사용자 지정 검색 규칙에 사용되는 쿼리를 포함하여 보안 센터에 저장된 쿼리에 이름 변경 내용이 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f0e2-110">Naming changes are automatically applied to queries that are saved in the security center, including queries used by custom detection rules.</span></span> <span data-ttu-id="1f0e2-111">이러한 쿼리를 수동으로 업데이트할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1f0e2-111">You don't need to update these queries manually.</span></span> <span data-ttu-id="1f0e2-112">그러나 다음 쿼리를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f0e2-112">However, you will need to update the following queries:</span></span>
- <span data-ttu-id="1f0e2-113">API를 사용하여 실행된 쿼리</span><span class="sxs-lookup"><span data-stu-id="1f0e2-113">Queries that are run using the API</span></span>
- <span data-ttu-id="1f0e2-114">보안 센터 외부에 저장된 쿼리</span><span class="sxs-lookup"><span data-stu-id="1f0e2-114">Queries that are saved elsewhere outside the security center</span></span>

## <a name="december-2020"></a><span data-ttu-id="1f0e2-115">2020년 12월</span><span class="sxs-lookup"><span data-stu-id="1f0e2-115">December 2020</span></span>

| <span data-ttu-id="1f0e2-116">테이블 이름</span><span class="sxs-lookup"><span data-stu-id="1f0e2-116">Table name</span></span> | <span data-ttu-id="1f0e2-117">원래 열 이름</span><span class="sxs-lookup"><span data-stu-id="1f0e2-117">Original column name</span></span> | <span data-ttu-id="1f0e2-118">새 열 이름</span><span class="sxs-lookup"><span data-stu-id="1f0e2-118">New column name</span></span> | <span data-ttu-id="1f0e2-119">변경 이유</span><span class="sxs-lookup"><span data-stu-id="1f0e2-119">Reason for change</span></span>
|--|--|--|--|
| [<span data-ttu-id="1f0e2-120">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="1f0e2-120">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="1f0e2-121">FinalEmailAction</span><span class="sxs-lookup"><span data-stu-id="1f0e2-121">FinalEmailAction</span></span> | <span data-ttu-id="1f0e2-122">EmailAction</span><span class="sxs-lookup"><span data-stu-id="1f0e2-122">EmailAction</span></span> | <span data-ttu-id="1f0e2-123">고객 피드백</span><span class="sxs-lookup"><span data-stu-id="1f0e2-123">Customer feedback</span></span> |
| [<span data-ttu-id="1f0e2-124">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="1f0e2-124">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="1f0e2-125">FinalEmailActionPolicy</span><span class="sxs-lookup"><span data-stu-id="1f0e2-125">FinalEmailActionPolicy</span></span> | <span data-ttu-id="1f0e2-126">EmailActionPolicy</span><span class="sxs-lookup"><span data-stu-id="1f0e2-126">EmailActionPolicy</span></span> | <span data-ttu-id="1f0e2-127">고객 피드백</span><span class="sxs-lookup"><span data-stu-id="1f0e2-127">Customer feedback</span></span> |
| [<span data-ttu-id="1f0e2-128">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="1f0e2-128">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="1f0e2-129">FinalEmailActionPolicyGuid</span><span class="sxs-lookup"><span data-stu-id="1f0e2-129">FinalEmailActionPolicyGuid</span></span> | <span data-ttu-id="1f0e2-130">EmailActionPolicyGuid</span><span class="sxs-lookup"><span data-stu-id="1f0e2-130">EmailActionPolicyGuid</span></span> | <span data-ttu-id="1f0e2-131">고객 피드백</span><span class="sxs-lookup"><span data-stu-id="1f0e2-131">Customer feedback</span></span> |

## <a name="related-topics"></a><span data-ttu-id="1f0e2-132">관련 항목</span><span class="sxs-lookup"><span data-stu-id="1f0e2-132">Related topics</span></span>
- [<span data-ttu-id="1f0e2-133">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="1f0e2-133">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="1f0e2-134">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="1f0e2-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)