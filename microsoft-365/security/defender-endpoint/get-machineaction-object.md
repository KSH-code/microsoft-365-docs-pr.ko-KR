---
title: MachineAction 개체 GET API
description: MachineAction API를 사용하여 끝점용 Microsoft Defender에서 ID로 특정 컴퓨터 작업을 검색하는 방법을 학습합니다.
keywords: api, 그래프 api, 지원되는 api, machineaction 개체
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: 180179d5b1362ad4952618148b11007aa9efe91c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200068"
---
# <a name="get-machineaction-api"></a><span data-ttu-id="9ea36-104">machineAction API 사용</span><span class="sxs-lookup"><span data-stu-id="9ea36-104">Get machineAction API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9ea36-105">**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="9ea36-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="9ea36-106">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="9ea36-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9ea36-107">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea36-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="9ea36-108">API 설명</span><span class="sxs-lookup"><span data-stu-id="9ea36-108">API description</span></span>
<span data-ttu-id="9ea36-109">ID로 특정 [컴퓨터 작업을](machineaction.md) 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea36-109">Retrieves specific [Machine Action](machineaction.md) by its ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="9ea36-110">제한 사항</span><span class="sxs-lookup"><span data-stu-id="9ea36-110">Limitations</span></span>
1. <span data-ttu-id="9ea36-111">이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.</span><span class="sxs-lookup"><span data-stu-id="9ea36-111">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="9ea36-112">사용 권한</span><span class="sxs-lookup"><span data-stu-id="9ea36-112">Permissions</span></span>
<span data-ttu-id="9ea36-113">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea36-113">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="9ea36-114">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 끝점 API에 [Defender 사용을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="9ea36-114">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="9ea36-115">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="9ea36-115">Permission type</span></span> |   <span data-ttu-id="9ea36-116">사용 권한</span><span class="sxs-lookup"><span data-stu-id="9ea36-116">Permission</span></span>  |   <span data-ttu-id="9ea36-117">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="9ea36-117">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="9ea36-118">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="9ea36-118">Application</span></span> |   <span data-ttu-id="9ea36-119">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="9ea36-119">Machine.Read.All</span></span> |  <span data-ttu-id="9ea36-120">'모든 컴퓨터 프로필 읽기'</span><span class="sxs-lookup"><span data-stu-id="9ea36-120">'Read all machine profiles'</span></span>
<span data-ttu-id="9ea36-121">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="9ea36-121">Application</span></span> |   <span data-ttu-id="9ea36-122">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="9ea36-122">Machine.ReadWrite.All</span></span> | <span data-ttu-id="9ea36-123">'모든 컴퓨터 정보 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="9ea36-123">'Read and write all machine information'</span></span>
<span data-ttu-id="9ea36-124">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="9ea36-124">Delegated (work or school account)</span></span> | <span data-ttu-id="9ea36-125">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="9ea36-125">Machine.Read</span></span> | <span data-ttu-id="9ea36-126">'컴퓨터 정보 읽기'</span><span class="sxs-lookup"><span data-stu-id="9ea36-126">'Read machine information'</span></span>
<span data-ttu-id="9ea36-127">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="9ea36-127">Delegated (work or school account)</span></span> | <span data-ttu-id="9ea36-128">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="9ea36-128">Machine.ReadWrite</span></span> | <span data-ttu-id="9ea36-129">'컴퓨터 정보 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="9ea36-129">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="9ea36-130">사용자 자격 증명을 사용하여 토큰을 얻을 때:</span><span class="sxs-lookup"><span data-stu-id="9ea36-130">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="9ea36-131">사용자에게 최소한 '데이터 보기' 역할 권한이 필요합니다(자세한 내용은 역할 [만들기](user-roles.md) 및 관리 참조).</span><span class="sxs-lookup"><span data-stu-id="9ea36-131">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="9ea36-132">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="9ea36-132">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/machineactions/{id}
```

## <a name="request-headers"></a><span data-ttu-id="9ea36-133">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="9ea36-133">Request headers</span></span>

<span data-ttu-id="9ea36-134">이름</span><span class="sxs-lookup"><span data-stu-id="9ea36-134">Name</span></span> | <span data-ttu-id="9ea36-135">유형</span><span class="sxs-lookup"><span data-stu-id="9ea36-135">Type</span></span> | <span data-ttu-id="9ea36-136">설명</span><span class="sxs-lookup"><span data-stu-id="9ea36-136">Description</span></span>
:---|:---|:---
<span data-ttu-id="9ea36-137">권한 부여</span><span class="sxs-lookup"><span data-stu-id="9ea36-137">Authorization</span></span> | <span data-ttu-id="9ea36-138">문자열</span><span class="sxs-lookup"><span data-stu-id="9ea36-138">String</span></span> | <span data-ttu-id="9ea36-139">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="9ea36-139">Bearer {token}.</span></span> <span data-ttu-id="9ea36-140">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="9ea36-140">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="9ea36-141">요청 본문</span><span class="sxs-lookup"><span data-stu-id="9ea36-141">Request body</span></span>
<span data-ttu-id="9ea36-142">비어 있음</span><span class="sxs-lookup"><span data-stu-id="9ea36-142">Empty</span></span>

## <a name="response"></a><span data-ttu-id="9ea36-143">응답</span><span class="sxs-lookup"><span data-stu-id="9ea36-143">Response</span></span>
<span data-ttu-id="9ea36-144">성공하면 이 메서드는 Machine Action 엔터티가 있는 200, 확인 응답 [코드를 반환합니다.](machineaction.md)</span><span class="sxs-lookup"><span data-stu-id="9ea36-144">If successful, this method returns 200, Ok response code with a [Machine Action](machineaction.md) entity.</span></span> <span data-ttu-id="9ea36-145">지정된 ID가 있는 컴퓨터 작업 엔터티를 찾을 수 없는 경우 - 404 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9ea36-145">If machine action entity with the specified id was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="9ea36-146">예제</span><span class="sxs-lookup"><span data-stu-id="9ea36-146">Example</span></span>

<span data-ttu-id="9ea36-147">**요청**</span><span class="sxs-lookup"><span data-stu-id="9ea36-147">**Request**</span></span>

<span data-ttu-id="9ea36-148">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="9ea36-148">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machineactions/2e9da30d-27f6-4208-81f2-9cd3d67893ba
```

<span data-ttu-id="9ea36-149">**응답**</span><span class="sxs-lookup"><span data-stu-id="9ea36-149">**Response**</span></span>

<span data-ttu-id="9ea36-150">다음은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="9ea36-150">Here is an example of the response.</span></span>


```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions/$entity",
    "id": "5382f7ea-7557-4ab7-9782-d50480024a4e",
    "type": "Isolate",
    "scope": "Selective",
    "requestor": "Analyst@TestPrd.onmicrosoft.com",
    "requestorComment": "test for docs",
    "status": "Succeeded",
    "machineId": "7b1f4967d9728e5aa3c06a9e617a22a4a5a17378",
    "computerDnsName": "desktop-test",
    "creationDateTimeUtc": "2019-01-02T14:39:38.2262283Z",
    "lastUpdateDateTimeUtc": "2019-01-02T14:40:44.6596267Z",
    "relatedFileInfo": null
}


```
