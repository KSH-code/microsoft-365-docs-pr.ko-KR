---
title: 경고 관련 도메인 정보 가져오기
description: 끝점용 Microsoft Defender를 사용하여 특정 경고와 관련된 모든 도메인을 검색합니다.
keywords: api, 그래프 api, 지원되는 api, 경고 정보, 경고 정보, 관련 도메인
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
ms.openlocfilehash: a5f3db65b42d8dc98c11f2ef2c3c5d509340e386
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771264"
---
# <a name="get-alert-related-domain-information-api"></a><span data-ttu-id="2d0e9-104">경고 관련 도메인 정보 얻기 API</span><span class="sxs-lookup"><span data-stu-id="2d0e9-104">Get alert related domain information API</span></span>

<span data-ttu-id="2d0e9-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="2d0e9-105">**Applies to:**</span></span> 
- [<span data-ttu-id="2d0e9-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2d0e9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

- <span data-ttu-id="2d0e9-107">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="2d0e9-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2d0e9-108">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="2d0e9-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="2d0e9-109">API 설명</span><span class="sxs-lookup"><span data-stu-id="2d0e9-109">API description</span></span>
<span data-ttu-id="2d0e9-110">특정 경고와 관련된 모든 도메인을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="2d0e9-110">Retrieves all domains related to a specific alert.</span></span>


## <a name="limitations"></a><span data-ttu-id="2d0e9-111">제한 사항</span><span class="sxs-lookup"><span data-stu-id="2d0e9-111">Limitations</span></span>
1. <span data-ttu-id="2d0e9-112">구성된 보존 기간에 따라 마지막으로 업데이트된 경고에 대해 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0e9-112">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="2d0e9-113">이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.</span><span class="sxs-lookup"><span data-stu-id="2d0e9-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="2d0e9-114">사용 권한</span><span class="sxs-lookup"><span data-stu-id="2d0e9-114">Permissions</span></span>
<span data-ttu-id="2d0e9-115">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2d0e9-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="2d0e9-116">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="2d0e9-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="2d0e9-117">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="2d0e9-117">Permission type</span></span> | <span data-ttu-id="2d0e9-118">사용 권한</span><span class="sxs-lookup"><span data-stu-id="2d0e9-118">Permission</span></span> | <span data-ttu-id="2d0e9-119">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="2d0e9-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="2d0e9-120">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="2d0e9-120">Application</span></span> | <span data-ttu-id="2d0e9-121">URL. Read.All</span><span class="sxs-lookup"><span data-stu-id="2d0e9-121">URL.Read.All</span></span> | <span data-ttu-id="2d0e9-122">'URL 읽기'</span><span class="sxs-lookup"><span data-stu-id="2d0e9-122">'Read URLs'</span></span>
<span data-ttu-id="2d0e9-123">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="2d0e9-123">Delegated (work or school account)</span></span> | <span data-ttu-id="2d0e9-124">URL. Read.All</span><span class="sxs-lookup"><span data-stu-id="2d0e9-124">URL.Read.All</span></span> | <span data-ttu-id="2d0e9-125">'URL 읽기'</span><span class="sxs-lookup"><span data-stu-id="2d0e9-125">'Read URLs'</span></span>

>[!Note]
> <span data-ttu-id="2d0e9-126">사용자 자격 증명을 사용하여 토큰을 얻을 때:</span><span class="sxs-lookup"><span data-stu-id="2d0e9-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="2d0e9-127">사용자에게 최소한 '데이터 보기' 역할 권한이 필요합니다(자세한 내용은 역할 [만들기](user-roles.md) 및 관리 참조).</span><span class="sxs-lookup"><span data-stu-id="2d0e9-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="2d0e9-128">사용자는 장치 그룹 설정에 따라 경고와 연결된 장치에 액세스할 수 있습니다(자세한 내용은 장치 그룹 만들기 및 [관리](machine-groups.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="2d0e9-128">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="2d0e9-129">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="2d0e9-129">HTTP request</span></span>
```
GET /api/alerts/{id}/domains
```

## <a name="request-headers"></a><span data-ttu-id="2d0e9-130">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="2d0e9-130">Request headers</span></span>

<span data-ttu-id="2d0e9-131">이름</span><span class="sxs-lookup"><span data-stu-id="2d0e9-131">Name</span></span> | <span data-ttu-id="2d0e9-132">유형</span><span class="sxs-lookup"><span data-stu-id="2d0e9-132">Type</span></span> | <span data-ttu-id="2d0e9-133">설명</span><span class="sxs-lookup"><span data-stu-id="2d0e9-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="2d0e9-134">권한 부여</span><span class="sxs-lookup"><span data-stu-id="2d0e9-134">Authorization</span></span> | <span data-ttu-id="2d0e9-135">String</span><span class="sxs-lookup"><span data-stu-id="2d0e9-135">String</span></span> | <span data-ttu-id="2d0e9-136">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="2d0e9-136">Bearer {token}.</span></span> <span data-ttu-id="2d0e9-137">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="2d0e9-137">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="2d0e9-138">요청 본문</span><span class="sxs-lookup"><span data-stu-id="2d0e9-138">Request body</span></span>
<span data-ttu-id="2d0e9-139">비어 있음</span><span class="sxs-lookup"><span data-stu-id="2d0e9-139">Empty</span></span>

## <a name="response"></a><span data-ttu-id="2d0e9-140">응답</span><span class="sxs-lookup"><span data-stu-id="2d0e9-140">Response</span></span>
<span data-ttu-id="2d0e9-141">성공적이고 경고와 도메인이 있는 경우 - 200 OK.</span><span class="sxs-lookup"><span data-stu-id="2d0e9-141">If successful and alert and domain exist - 200 OK.</span></span> <span data-ttu-id="2d0e9-142">알림을 찾을 수 없는 경우 - 404 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0e9-142">If alert not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="2d0e9-143">예시</span><span class="sxs-lookup"><span data-stu-id="2d0e9-143">Example</span></span>

<span data-ttu-id="2d0e9-144">**요청**</span><span class="sxs-lookup"><span data-stu-id="2d0e9-144">**Request**</span></span>

<span data-ttu-id="2d0e9-145">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="2d0e9-145">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/alerts/636688558380765161_2136280442/domains
```

<span data-ttu-id="2d0e9-146">**응답**</span><span class="sxs-lookup"><span data-stu-id="2d0e9-146">**Response**</span></span>

<span data-ttu-id="2d0e9-147">다음은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="2d0e9-147">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/$metadata#Domains",
    "value": [
        {
            "host": "www.example.com"
        },
        {
            "host": "www.example2.com"
        }
        ...
    ]
}

```
