---
title: ID로 권장 사용
description: ID로 보안 권장을 검색합니다.
keywords: api, 그래프 api, 지원되는 api, get, 보안 권장, ID로 보안 권장, 위협 및 취약성 관리, 위협 및 취약성 관리 api
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 4ec4758453f43cb211143918ed5fe8fe83e91c3f
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771804"
---
# <a name="get-recommendation-by-id"></a><span data-ttu-id="084b0-104">ID별 권장 사항 가져오기</span><span class="sxs-lookup"><span data-stu-id="084b0-104">Get recommendation by ID</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="084b0-105">**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="084b0-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="084b0-106">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="084b0-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="084b0-107">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="084b0-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="084b0-108">ID로 보안 권장을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="084b0-108">Retrieves a security recommendation by its ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="084b0-109">사용 권한</span><span class="sxs-lookup"><span data-stu-id="084b0-109">Permissions</span></span>
<span data-ttu-id="084b0-110">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="084b0-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="084b0-111">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [Use Microsoft Defender for Endpoint API](apis-intro.md) for details을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="084b0-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="084b0-112">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="084b0-112">Permission type</span></span> |   <span data-ttu-id="084b0-113">사용 권한</span><span class="sxs-lookup"><span data-stu-id="084b0-113">Permission</span></span>  |   <span data-ttu-id="084b0-114">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="084b0-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="084b0-115">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="084b0-115">Application</span></span> |   <span data-ttu-id="084b0-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="084b0-116">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="084b0-117">'위협 및 취약성 관리 보안 권장 정보 읽기'</span><span class="sxs-lookup"><span data-stu-id="084b0-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="084b0-118">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="084b0-118">Delegated (work or school account)</span></span> | <span data-ttu-id="084b0-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="084b0-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="084b0-120">'위협 및 취약성 관리 보안 권장 정보 읽기'</span><span class="sxs-lookup"><span data-stu-id="084b0-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="084b0-121">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="084b0-121">HTTP request</span></span>
```
GET /api/recommendations/{id}
```

## <a name="request-headers"></a><span data-ttu-id="084b0-122">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="084b0-122">Request headers</span></span>

<span data-ttu-id="084b0-123">이름</span><span class="sxs-lookup"><span data-stu-id="084b0-123">Name</span></span> | <span data-ttu-id="084b0-124">유형</span><span class="sxs-lookup"><span data-stu-id="084b0-124">Type</span></span> | <span data-ttu-id="084b0-125">설명</span><span class="sxs-lookup"><span data-stu-id="084b0-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="084b0-126">권한 부여</span><span class="sxs-lookup"><span data-stu-id="084b0-126">Authorization</span></span> | <span data-ttu-id="084b0-127">String</span><span class="sxs-lookup"><span data-stu-id="084b0-127">String</span></span> | <span data-ttu-id="084b0-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="084b0-128">Bearer {token}.</span></span> <span data-ttu-id="084b0-129">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="084b0-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="084b0-130">요청 본문</span><span class="sxs-lookup"><span data-stu-id="084b0-130">Request body</span></span>
<span data-ttu-id="084b0-131">비어 있음</span><span class="sxs-lookup"><span data-stu-id="084b0-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="084b0-132">응답</span><span class="sxs-lookup"><span data-stu-id="084b0-132">Response</span></span>
<span data-ttu-id="084b0-133">성공하면 이 메서드는 본문의 보안 권장 사항을 사용하여 200 OK를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="084b0-133">If successful, this method returns 200 OK with the security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="084b0-134">예시</span><span class="sxs-lookup"><span data-stu-id="084b0-134">Example</span></span>

<span data-ttu-id="084b0-135">**요청**</span><span class="sxs-lookup"><span data-stu-id="084b0-135">**Request**</span></span>

<span data-ttu-id="084b0-136">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="084b0-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome
```

<span data-ttu-id="084b0-137">**응답**</span><span class="sxs-lookup"><span data-stu-id="084b0-137">**Response**</span></span>

<span data-ttu-id="084b0-138">다음은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="084b0-138">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Recommendations/$entity",
    "id": "va-_-google-_-chrome",
    "productName": "chrome",
    "recommendationName": "Update Chrome",
    "weaknesses": 38,
    "vendor": "google",
    "recommendedVersion": "",
    "recommendationCategory": "Application",
    "subCategory": "",
    "severityScore": 0,
    "publicExploit": false,
    "activeAlert": false,
    "associatedThreats": [],
    "remediationType": "Update",
    "status": "Active",
    "configScoreImpact": 0,
    "exposureImpact": 3.9441860465116285,
    "totalMachineCount": 6,
    "exposedMachinesCount": 5,
    "nonProductivityImpactedAssets": 0,
    "relatedComponent": "Chrome"
}
```

## <a name="related-topics"></a><span data-ttu-id="084b0-139">관련 항목</span><span class="sxs-lookup"><span data-stu-id="084b0-139">Related topics</span></span>
- [<span data-ttu-id="084b0-140">위험 기반 위협 & 관리</span><span class="sxs-lookup"><span data-stu-id="084b0-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="084b0-141">위협 & 보안 권장</span><span class="sxs-lookup"><span data-stu-id="084b0-141">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
