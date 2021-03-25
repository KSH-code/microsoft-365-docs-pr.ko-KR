---
title: 표시기 API 삭제.
description: 지표 삭제 API를 사용하여 끝점용 Microsoft Defender에서 ID로 표시기 엔터티를 삭제하는 방법을 학습합니다.
keywords: api, 공개 api, 지원되는 api, 삭제, ti 표시기, 엔터티, ID
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 1305be897dff6932713cf294eb4e5cd53692681c
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167106"
---
# <a name="delete-indicator-api"></a><span data-ttu-id="5a3ec-104">표시기 삭제 API</span><span class="sxs-lookup"><span data-stu-id="5a3ec-104">Delete Indicator API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5a3ec-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="5a3ec-105">**Applies to:**</span></span>
- [<span data-ttu-id="5a3ec-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="5a3ec-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5a3ec-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5a3ec-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="5a3ec-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="5a3ec-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5a3ec-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3ec-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)  

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="5a3ec-110">API 설명</span><span class="sxs-lookup"><span data-stu-id="5a3ec-110">API description</span></span>
<span data-ttu-id="5a3ec-111">ID로 [Indicator](ti-indicator.md) 엔터티를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3ec-111">Deletes an [Indicator](ti-indicator.md) entity by ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="5a3ec-112">제한 사항</span><span class="sxs-lookup"><span data-stu-id="5a3ec-112">Limitations</span></span>
1. <span data-ttu-id="5a3ec-113">이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.</span><span class="sxs-lookup"><span data-stu-id="5a3ec-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="5a3ec-114">사용 권한</span><span class="sxs-lookup"><span data-stu-id="5a3ec-114">Permissions</span></span>
<span data-ttu-id="5a3ec-115">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3ec-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="5a3ec-116">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [시작을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="5a3ec-116">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="5a3ec-117">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="5a3ec-117">Permission type</span></span> |   <span data-ttu-id="5a3ec-118">사용 권한</span><span class="sxs-lookup"><span data-stu-id="5a3ec-118">Permission</span></span>  |   <span data-ttu-id="5a3ec-119">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="5a3ec-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="5a3ec-120">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="5a3ec-120">Application</span></span> |   <span data-ttu-id="5a3ec-121">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="5a3ec-121">Ti.ReadWrite</span></span> |  <span data-ttu-id="5a3ec-122">'TI 지표 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="5a3ec-122">'Read and write TI Indicators'</span></span>
<span data-ttu-id="5a3ec-123">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="5a3ec-123">Application</span></span> |   <span data-ttu-id="5a3ec-124">Ti.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="5a3ec-124">Ti.ReadWrite.All</span></span> |  <span data-ttu-id="5a3ec-125">'읽기 및 쓰기 표시기'</span><span class="sxs-lookup"><span data-stu-id="5a3ec-125">'Read and write Indicators'</span></span>


## <a name="http-request"></a><span data-ttu-id="5a3ec-126">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="5a3ec-126">HTTP request</span></span>
```
Delete https://api.securitycenter.microsoft.com/api/indicators/{id}
```

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="request-headers"></a><span data-ttu-id="5a3ec-127">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="5a3ec-127">Request headers</span></span>

<span data-ttu-id="5a3ec-128">이름</span><span class="sxs-lookup"><span data-stu-id="5a3ec-128">Name</span></span> | <span data-ttu-id="5a3ec-129">유형</span><span class="sxs-lookup"><span data-stu-id="5a3ec-129">Type</span></span> | <span data-ttu-id="5a3ec-130">설명</span><span class="sxs-lookup"><span data-stu-id="5a3ec-130">Description</span></span>
:---|:---|:---
<span data-ttu-id="5a3ec-131">권한 부여</span><span class="sxs-lookup"><span data-stu-id="5a3ec-131">Authorization</span></span> | <span data-ttu-id="5a3ec-132">문자열</span><span class="sxs-lookup"><span data-stu-id="5a3ec-132">String</span></span> | <span data-ttu-id="5a3ec-133">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="5a3ec-133">Bearer {token}.</span></span> <span data-ttu-id="5a3ec-134">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="5a3ec-134">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="5a3ec-135">요청 본문</span><span class="sxs-lookup"><span data-stu-id="5a3ec-135">Request body</span></span>
<span data-ttu-id="5a3ec-136">비어 있음</span><span class="sxs-lookup"><span data-stu-id="5a3ec-136">Empty</span></span>

## <a name="response"></a><span data-ttu-id="5a3ec-137">응답</span><span class="sxs-lookup"><span data-stu-id="5a3ec-137">Response</span></span>
<span data-ttu-id="5a3ec-138">Indicator가 존재하고 삭제된 경우 - 콘텐츠가 없는 204 OK.</span><span class="sxs-lookup"><span data-stu-id="5a3ec-138">If Indicator exist and deleted successfully - 204 OK without content.</span></span>
<span data-ttu-id="5a3ec-139">지정한 ID가 있는 Indicator를 찾을 수 없는 경우 - 404 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5a3ec-139">If Indicator with the specified id was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="5a3ec-140">예제</span><span class="sxs-lookup"><span data-stu-id="5a3ec-140">Example</span></span>

<span data-ttu-id="5a3ec-141">**요청**</span><span class="sxs-lookup"><span data-stu-id="5a3ec-141">**Request**</span></span>

<span data-ttu-id="5a3ec-142">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="5a3ec-142">Here is an example of the request.</span></span>

```http
DELETE https://api.securitycenter.microsoft.com/api/indicators/995
```
