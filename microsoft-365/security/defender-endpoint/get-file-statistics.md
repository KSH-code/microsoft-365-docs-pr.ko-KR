---
title: 파일 통계 다운로드 API
description: 파일 통계 다운로드 API를 사용하여 끝점용 Microsoft Defender에서 지정한 파일에 대한 통계를 검색하는 방법을 학습합니다.
keywords: api, 그래프 api, 지원되는 api, 다운로드, 파일, 통계
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
ms.openlocfilehash: 826b2ff25363f1d9a6276e1a42a10c1cf4995904
ms.sourcegitcommit: 787fb30fdae6d49347a87f4baae3cd140067e573
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2021
ms.locfileid: "52998815"
---
# <a name="get-file-statistics-api"></a><span data-ttu-id="f8f42-104">파일 통계 다운로드 API</span><span class="sxs-lookup"><span data-stu-id="f8f42-104">Get file statistics API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f8f42-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="f8f42-105">**Applies to:**</span></span>
- [<span data-ttu-id="f8f42-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f8f42-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f8f42-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f8f42-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f8f42-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="f8f42-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f8f42-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="f8f42-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="f8f42-110">API 설명</span><span class="sxs-lookup"><span data-stu-id="f8f42-110">API description</span></span>
<span data-ttu-id="f8f42-111">지정한 파일에 대한 통계를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="f8f42-111">Retrieves the statistics for the given file.</span></span>


## <a name="limitations"></a><span data-ttu-id="f8f42-112">제한 사항</span><span class="sxs-lookup"><span data-stu-id="f8f42-112">Limitations</span></span>
1. <span data-ttu-id="f8f42-113">이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.</span><span class="sxs-lookup"><span data-stu-id="f8f42-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="f8f42-114">사용 권한</span><span class="sxs-lookup"><span data-stu-id="f8f42-114">Permissions</span></span>
<span data-ttu-id="f8f42-115">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f8f42-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="f8f42-116">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="f8f42-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="f8f42-117">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="f8f42-117">Permission type</span></span> |   <span data-ttu-id="f8f42-118">사용 권한</span><span class="sxs-lookup"><span data-stu-id="f8f42-118">Permission</span></span>  |   <span data-ttu-id="f8f42-119">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="f8f42-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="f8f42-120">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="f8f42-120">Application</span></span> |   <span data-ttu-id="f8f42-121">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="f8f42-121">File.Read.All</span></span> | <span data-ttu-id="f8f42-122">'파일 프로필 읽기'</span><span class="sxs-lookup"><span data-stu-id="f8f42-122">'Read file profiles'</span></span>
<span data-ttu-id="f8f42-123">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="f8f42-123">Delegated (work or school account)</span></span> | <span data-ttu-id="f8f42-124">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="f8f42-124">File.Read.All</span></span> | <span data-ttu-id="f8f42-125">'파일 프로필 읽기'</span><span class="sxs-lookup"><span data-stu-id="f8f42-125">'Read file profiles'</span></span>

>[!Note]
> <span data-ttu-id="f8f42-126">사용자 자격 증명을 사용하여 토큰을 얻을 때:</span><span class="sxs-lookup"><span data-stu-id="f8f42-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="f8f42-127">사용자에게 최소한 '데이터 보기' 역할 권한이 필요합니다(자세한 내용은 역할 [만들기](user-roles.md) 및 관리 참조).</span><span class="sxs-lookup"><span data-stu-id="f8f42-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="f8f42-128">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="f8f42-128">HTTP request</span></span>
```
GET /api/files/{id}/stats
```

## <a name="request-headers"></a><span data-ttu-id="f8f42-129">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="f8f42-129">Request headers</span></span>

<span data-ttu-id="f8f42-130">이름</span><span class="sxs-lookup"><span data-stu-id="f8f42-130">Name</span></span> | <span data-ttu-id="f8f42-131">유형</span><span class="sxs-lookup"><span data-stu-id="f8f42-131">Type</span></span> | <span data-ttu-id="f8f42-132">설명</span><span class="sxs-lookup"><span data-stu-id="f8f42-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="f8f42-133">권한 부여</span><span class="sxs-lookup"><span data-stu-id="f8f42-133">Authorization</span></span> | <span data-ttu-id="f8f42-134">String</span><span class="sxs-lookup"><span data-stu-id="f8f42-134">String</span></span> | <span data-ttu-id="f8f42-135">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="f8f42-135">Bearer {token}.</span></span> <span data-ttu-id="f8f42-136">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="f8f42-136">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="f8f42-137">요청 URI 매개 변수</span><span class="sxs-lookup"><span data-stu-id="f8f42-137">Request URI parameters</span></span>

<span data-ttu-id="f8f42-138">이름</span><span class="sxs-lookup"><span data-stu-id="f8f42-138">Name</span></span> | <span data-ttu-id="f8f42-139">유형</span><span class="sxs-lookup"><span data-stu-id="f8f42-139">Type</span></span> | <span data-ttu-id="f8f42-140">설명</span><span class="sxs-lookup"><span data-stu-id="f8f42-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="f8f42-141">lookBackHours</span><span class="sxs-lookup"><span data-stu-id="f8f42-141">lookBackHours</span></span> | <span data-ttu-id="f8f42-142">Int32</span><span class="sxs-lookup"><span data-stu-id="f8f42-142">Int32</span></span> | <span data-ttu-id="f8f42-143">통계를 얻기 위해 다시 검색하는 시간을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f8f42-143">Defines the hours we search back to get the statistics.</span></span> <span data-ttu-id="f8f42-144">기본값은 30일입니다.</span><span class="sxs-lookup"><span data-stu-id="f8f42-144">Defaults to 30 days.</span></span> <span data-ttu-id="f8f42-145">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="f8f42-145">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="f8f42-146">요청 본문</span><span class="sxs-lookup"><span data-stu-id="f8f42-146">Request body</span></span>
<span data-ttu-id="f8f42-147">비어 있음</span><span class="sxs-lookup"><span data-stu-id="f8f42-147">Empty</span></span>

## <a name="response"></a><span data-ttu-id="f8f42-148">응답</span><span class="sxs-lookup"><span data-stu-id="f8f42-148">Response</span></span>
<span data-ttu-id="f8f42-149">성공 및 파일이 있는 경우 - 본문에 통계 데이터가 있는 200 OK.</span><span class="sxs-lookup"><span data-stu-id="f8f42-149">If successful and file exists - 200 OK with statistical data in the body.</span></span> <span data-ttu-id="f8f42-150">파일이 없는 경우 - 404 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f8f42-150">If file do not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="f8f42-151">예시</span><span class="sxs-lookup"><span data-stu-id="f8f42-151">Example</span></span>

<span data-ttu-id="f8f42-152">**요청**</span><span class="sxs-lookup"><span data-stu-id="f8f42-152">**Request**</span></span>

<span data-ttu-id="f8f42-153">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="f8f42-153">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/files/0991a395da64e1c5fbe8732ed11e6be064081d9f/stats?lookBackHours=48
```

<span data-ttu-id="f8f42-154">**응답**</span><span class="sxs-lookup"><span data-stu-id="f8f42-154">**Response**</span></span>

<span data-ttu-id="f8f42-155">다음은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="f8f42-155">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgFileStats",
    "sha1": "0991a395da64e1c5fbe8732ed11e6be064081d9f",
    "organizationPrevalence": 14850,
    "orgFirstSeen": "2019-12-07T13:44:16Z",
    "orgLastSeen": "2020-01-06T13:39:36Z",
    "globallyPrevalence": 705012,
    "globalFirstObserved": "2015-03-19T12:20:07.3432441Z",
    "globalLastObserved": "2020-01-06T13:39:36Z",
    "topFileNames": [
        "MREC.exe"
    ]
}

```
