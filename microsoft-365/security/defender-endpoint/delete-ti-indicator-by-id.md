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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 1541e1d6e177416d77d768cef04d2524e6907ab5
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289922"
---
# <a name="delete-indicator-api"></a><span data-ttu-id="9979c-104">표시기 삭제 API</span><span class="sxs-lookup"><span data-stu-id="9979c-104">Delete Indicator API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9979c-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="9979c-105">**Applies to:**</span></span>
- [<span data-ttu-id="9979c-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="9979c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9979c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9979c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="9979c-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="9979c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="9979c-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="9979c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)  

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="9979c-110">API 설명</span><span class="sxs-lookup"><span data-stu-id="9979c-110">API description</span></span>

<span data-ttu-id="9979c-111">ID로 [Indicator](ti-indicator.md) 엔터티를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="9979c-111">Deletes an [Indicator](ti-indicator.md) entity by ID.</span></span>

## <a name="limitations"></a><span data-ttu-id="9979c-112">제한 사항</span><span class="sxs-lookup"><span data-stu-id="9979c-112">Limitations</span></span>

<span data-ttu-id="9979c-113">이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.</span><span class="sxs-lookup"><span data-stu-id="9979c-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="9979c-114">사용 권한</span><span class="sxs-lookup"><span data-stu-id="9979c-114">Permissions</span></span>

<span data-ttu-id="9979c-115">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9979c-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="9979c-116">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [시작을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="9979c-116">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="9979c-117">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="9979c-117">Permission type</span></span> | <span data-ttu-id="9979c-118">사용 권한</span><span class="sxs-lookup"><span data-stu-id="9979c-118">Permission</span></span> | <span data-ttu-id="9979c-119">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="9979c-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="9979c-120">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="9979c-120">Application</span></span> | <span data-ttu-id="9979c-121">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="9979c-121">Ti.ReadWrite</span></span> | <span data-ttu-id="9979c-122">'TI 지표 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="9979c-122">'Read and write TI Indicators'</span></span>
<span data-ttu-id="9979c-123">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="9979c-123">Application</span></span> | <span data-ttu-id="9979c-124">Ti.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="9979c-124">Ti.ReadWrite.All</span></span> | <span data-ttu-id="9979c-125">'읽기 및 쓰기 표시기'</span><span class="sxs-lookup"><span data-stu-id="9979c-125">'Read and write Indicators'</span></span>

## <a name="http-request"></a><span data-ttu-id="9979c-126">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="9979c-126">HTTP request</span></span>

```http
Delete https://api.securitycenter.microsoft.com/api/indicators/{id}
```

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="request-headers"></a><span data-ttu-id="9979c-127">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="9979c-127">Request headers</span></span>

<span data-ttu-id="9979c-128">이름</span><span class="sxs-lookup"><span data-stu-id="9979c-128">Name</span></span> | <span data-ttu-id="9979c-129">유형</span><span class="sxs-lookup"><span data-stu-id="9979c-129">Type</span></span> | <span data-ttu-id="9979c-130">설명</span><span class="sxs-lookup"><span data-stu-id="9979c-130">Description</span></span>
:---|:---|:---
<span data-ttu-id="9979c-131">권한 부여</span><span class="sxs-lookup"><span data-stu-id="9979c-131">Authorization</span></span> | <span data-ttu-id="9979c-132">문자열</span><span class="sxs-lookup"><span data-stu-id="9979c-132">String</span></span> | <span data-ttu-id="9979c-133">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="9979c-133">Bearer {token}.</span></span> <span data-ttu-id="9979c-134">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="9979c-134">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="9979c-135">요청 본문</span><span class="sxs-lookup"><span data-stu-id="9979c-135">Request body</span></span>

<span data-ttu-id="9979c-136">비어 있음</span><span class="sxs-lookup"><span data-stu-id="9979c-136">Empty</span></span>

## <a name="response"></a><span data-ttu-id="9979c-137">응답</span><span class="sxs-lookup"><span data-stu-id="9979c-137">Response</span></span>

<span data-ttu-id="9979c-138">Indicator가 존재하고 삭제된 경우 - 콘텐츠가 없는 204 OK.</span><span class="sxs-lookup"><span data-stu-id="9979c-138">If Indicator exist and deleted successfully - 204 OK without content.</span></span>

<span data-ttu-id="9979c-139">지정한 ID가 있는 Indicator를 찾을 수 없는 경우 - 404 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9979c-139">If Indicator with the specified id was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="9979c-140">예제</span><span class="sxs-lookup"><span data-stu-id="9979c-140">Example</span></span>

### <a name="request"></a><span data-ttu-id="9979c-141">요청</span><span class="sxs-lookup"><span data-stu-id="9979c-141">Request</span></span>

<span data-ttu-id="9979c-142">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="9979c-142">Here is an example of the request.</span></span>

```http
DELETE https://api.securitycenter.microsoft.com/api/indicators/995
```
