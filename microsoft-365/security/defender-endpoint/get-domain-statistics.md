---
title: 도메인 통계 얻기 API
description: 도메인 통계 다운로드 API를 사용하여 끝점용 Microsoft Defender에서 지정한 도메인에 대한 통계를 검색하는 방법을 학습합니다.
keywords: api, 그래프 api, 지원되는 api, get, 도메인, 도메인 관련 장치
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
ms.openlocfilehash: 50b05b98ba507e120bbd6a3dc09f4633dac3a005
ms.sourcegitcommit: 787fb30fdae6d49347a87f4baae3cd140067e573
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2021
ms.locfileid: "52998779"
---
# <a name="get-domain-statistics-api"></a><span data-ttu-id="82066-104">도메인 통계 얻기 API</span><span class="sxs-lookup"><span data-stu-id="82066-104">Get domain statistics API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="82066-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="82066-105">**Applies to:**</span></span>
- [<span data-ttu-id="82066-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="82066-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="82066-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="82066-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="82066-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="82066-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="82066-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="82066-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="82066-110">API 설명</span><span class="sxs-lookup"><span data-stu-id="82066-110">API description</span></span>
<span data-ttu-id="82066-111">지정한 도메인에 대한 통계를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="82066-111">Retrieves the statistics on the given domain.</span></span>


## <a name="limitations"></a><span data-ttu-id="82066-112">제한 사항</span><span class="sxs-lookup"><span data-stu-id="82066-112">Limitations</span></span>
1. <span data-ttu-id="82066-113">이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.</span><span class="sxs-lookup"><span data-stu-id="82066-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="82066-114">사용 권한</span><span class="sxs-lookup"><span data-stu-id="82066-114">Permissions</span></span>
<span data-ttu-id="82066-115">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="82066-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="82066-116">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="82066-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="82066-117">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="82066-117">Permission type</span></span> |   <span data-ttu-id="82066-118">사용 권한</span><span class="sxs-lookup"><span data-stu-id="82066-118">Permission</span></span>  |   <span data-ttu-id="82066-119">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="82066-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="82066-120">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="82066-120">Application</span></span> |   <span data-ttu-id="82066-121">URL. Read.All</span><span class="sxs-lookup"><span data-stu-id="82066-121">URL.Read.All</span></span> |  <span data-ttu-id="82066-122">'URL 읽기'</span><span class="sxs-lookup"><span data-stu-id="82066-122">'Read URLs'</span></span>
<span data-ttu-id="82066-123">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="82066-123">Delegated (work or school account)</span></span> | <span data-ttu-id="82066-124">URL. Read.All</span><span class="sxs-lookup"><span data-stu-id="82066-124">URL.Read.All</span></span> | <span data-ttu-id="82066-125">'URL 읽기'</span><span class="sxs-lookup"><span data-stu-id="82066-125">'Read URLs'</span></span>

>[!Note]
> <span data-ttu-id="82066-126">사용자 자격 증명을 사용하여 토큰을 얻을 때:</span><span class="sxs-lookup"><span data-stu-id="82066-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="82066-127">사용자에게 최소한 '데이터 보기' 역할 권한이 필요합니다(자세한 내용은 역할 [만들기](user-roles.md) 및 관리 참조).</span><span class="sxs-lookup"><span data-stu-id="82066-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="82066-128">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="82066-128">HTTP request</span></span>
```
GET /api/domains/{domain}/stats
```

## <a name="request-headers"></a><span data-ttu-id="82066-129">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="82066-129">Request headers</span></span>

<span data-ttu-id="82066-130">헤더</span><span class="sxs-lookup"><span data-stu-id="82066-130">Header</span></span> | <span data-ttu-id="82066-131">값</span><span class="sxs-lookup"><span data-stu-id="82066-131">Value</span></span> 
:---|:---
<span data-ttu-id="82066-132">권한 부여</span><span class="sxs-lookup"><span data-stu-id="82066-132">Authorization</span></span> | <span data-ttu-id="82066-133">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="82066-133">Bearer {token}.</span></span> <span data-ttu-id="82066-134">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="82066-134">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="82066-135">요청 URI 매개 변수</span><span class="sxs-lookup"><span data-stu-id="82066-135">Request URI parameters</span></span>

<span data-ttu-id="82066-136">이름</span><span class="sxs-lookup"><span data-stu-id="82066-136">Name</span></span> | <span data-ttu-id="82066-137">유형</span><span class="sxs-lookup"><span data-stu-id="82066-137">Type</span></span> | <span data-ttu-id="82066-138">설명</span><span class="sxs-lookup"><span data-stu-id="82066-138">Description</span></span>
:---|:---|:---
<span data-ttu-id="82066-139">lookBackHours</span><span class="sxs-lookup"><span data-stu-id="82066-139">lookBackHours</span></span> | <span data-ttu-id="82066-140">Int32</span><span class="sxs-lookup"><span data-stu-id="82066-140">Int32</span></span> | <span data-ttu-id="82066-141">통계를 얻기 위해 다시 검색하는 시간을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="82066-141">Defines the hours we search back to get the statistics.</span></span> <span data-ttu-id="82066-142">기본값은 30일입니다.</span><span class="sxs-lookup"><span data-stu-id="82066-142">Defaults to 30 days.</span></span> <span data-ttu-id="82066-143">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="82066-143">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="82066-144">요청 본문</span><span class="sxs-lookup"><span data-stu-id="82066-144">Request body</span></span>
<span data-ttu-id="82066-145">비어 있음</span><span class="sxs-lookup"><span data-stu-id="82066-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="82066-146">응답</span><span class="sxs-lookup"><span data-stu-id="82066-146">Response</span></span>
<span data-ttu-id="82066-147">성공 및 도메인이 있는 경우 - 응답 본문에 statistics 개체가 있는 200 OK.</span><span class="sxs-lookup"><span data-stu-id="82066-147">If successful and domain exists - 200 OK, with statistics object in the response body.</span></span> <span data-ttu-id="82066-148">도메인이 없는 경우 - 404 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="82066-148">If domain does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="82066-149">예시</span><span class="sxs-lookup"><span data-stu-id="82066-149">Example</span></span>

<span data-ttu-id="82066-150">**요청**</span><span class="sxs-lookup"><span data-stu-id="82066-150">**Request**</span></span>

<span data-ttu-id="82066-151">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="82066-151">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/domains/example.com/stats?lookBackHours=48
```

<span data-ttu-id="82066-152">**응답**</span><span class="sxs-lookup"><span data-stu-id="82066-152">**Response**</span></span>

<span data-ttu-id="82066-153">다음은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="82066-153">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgDomainStats",
    "host": "example.com",
    "organizationPrevalence": 4070,
    "orgFirstSeen": "2017-07-30T13:23:48Z",
    "orgLastSeen": "2017-08-29T13:09:05Z"
}
```
