---
title: 점수 방법 및 속성
description: 장치 그룹당 조직의 노출 점수, 장치 보안 점수 및 노출 점수를 검색합니다.
keywords: api, 그래프 api, 지원되는 api, 점수, 노출 점수, 장치 보안 점수, 장치 그룹당 노출 점수
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 1c287a72318cfb2e6e4e3860ac90a90e561040fe
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500951"
---
# <a name="score-resource-type"></a><span data-ttu-id="d6ed8-104">점수 리소스 유형</span><span class="sxs-lookup"><span data-stu-id="d6ed8-104">Score resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d6ed8-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="d6ed8-105">**Applies to:**</span></span>
- [<span data-ttu-id="d6ed8-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d6ed8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="d6ed8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d6ed8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d6ed8-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="d6ed8-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d6ed8-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="d6ed8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a><span data-ttu-id="d6ed8-110">메서드</span><span class="sxs-lookup"><span data-stu-id="d6ed8-110">Methods</span></span>

<span data-ttu-id="d6ed8-111">메서드</span><span class="sxs-lookup"><span data-stu-id="d6ed8-111">Method</span></span> |<span data-ttu-id="d6ed8-112">반환 형식</span><span class="sxs-lookup"><span data-stu-id="d6ed8-112">Return Type</span></span> |<span data-ttu-id="d6ed8-113">설명</span><span class="sxs-lookup"><span data-stu-id="d6ed8-113">Description</span></span>
:---|:---|:---
[<span data-ttu-id="d6ed8-114">노출 점수 가져오기</span><span class="sxs-lookup"><span data-stu-id="d6ed8-114">Get exposure score</span></span>](get-exposure-score.md) | [<span data-ttu-id="d6ed8-115">점수</span><span class="sxs-lookup"><span data-stu-id="d6ed8-115">Score</span></span>](score.md) | <span data-ttu-id="d6ed8-116">조직 노출 점수를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="d6ed8-116">Get the organizational exposure score.</span></span>
[<span data-ttu-id="d6ed8-117">장치 보안 점수 가져오기</span><span class="sxs-lookup"><span data-stu-id="d6ed8-117">Get device secure score</span></span>](get-device-secure-score.md) | [<span data-ttu-id="d6ed8-118">점수</span><span class="sxs-lookup"><span data-stu-id="d6ed8-118">Score</span></span>](score.md) | <span data-ttu-id="d6ed8-119">조직 장치 보안 점수를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="d6ed8-119">Get the organizational device secure score.</span></span>
[<span data-ttu-id="d6ed8-120">장치 그룹당 노출 점수 나열</span><span class="sxs-lookup"><span data-stu-id="d6ed8-120">List exposure score by device group</span></span>](get-machine-group-exposure-score.md)| [<span data-ttu-id="d6ed8-121">점수</span><span class="sxs-lookup"><span data-stu-id="d6ed8-121">Score</span></span>](score.md) | <span data-ttu-id="d6ed8-122">장치 그룹당 점수를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="d6ed8-122">List scores by device group.</span></span>

## <a name="properties"></a><span data-ttu-id="d6ed8-123">속성</span><span class="sxs-lookup"><span data-stu-id="d6ed8-123">Properties</span></span>

<span data-ttu-id="d6ed8-124">속성</span><span class="sxs-lookup"><span data-stu-id="d6ed8-124">Property</span></span> |  <span data-ttu-id="d6ed8-125">유형</span><span class="sxs-lookup"><span data-stu-id="d6ed8-125">Type</span></span>    |   <span data-ttu-id="d6ed8-126">설명</span><span class="sxs-lookup"><span data-stu-id="d6ed8-126">Description</span></span>
:---|:---|:---
<span data-ttu-id="d6ed8-127">점수</span><span class="sxs-lookup"><span data-stu-id="d6ed8-127">Score</span></span> | <span data-ttu-id="d6ed8-128">실수</span><span class="sxs-lookup"><span data-stu-id="d6ed8-128">Double</span></span> | <span data-ttu-id="d6ed8-129">현재 점수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6ed8-129">The current score.</span></span>
<span data-ttu-id="d6ed8-130">시간</span><span class="sxs-lookup"><span data-stu-id="d6ed8-130">Time</span></span> | <span data-ttu-id="d6ed8-131">DateTime</span><span class="sxs-lookup"><span data-stu-id="d6ed8-131">DateTime</span></span> | <span data-ttu-id="d6ed8-132">이 API를 호출한 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="d6ed8-132">The date and time in which the call for this API was made.</span></span>
<span data-ttu-id="d6ed8-133">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="d6ed8-133">RbacGroupName</span></span> | <span data-ttu-id="d6ed8-134">문자열</span><span class="sxs-lookup"><span data-stu-id="d6ed8-134">String</span></span> | <span data-ttu-id="d6ed8-135">장치 그룹 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d6ed8-135">The device group name.</span></span>
