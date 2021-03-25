---
title: 모든 권장 사항 나열
description: 조직에 영향을 주는 모든 보안 권장 사항 목록을 검색합니다.
keywords: api, 그래프 api, 지원되는 api, get, 보안 권장 사항, mdatp tvm api, 위협 및 취약성 관리, 위협 및 취약성 관리 api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: mde
ms.openlocfilehash: 5fb68572ee1b154be1db5eb5a092013a1c1a257e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166914"
---
# <a name="list-all-recommendations"></a><span data-ttu-id="189f6-104">모든 권장 사항 나열</span><span class="sxs-lookup"><span data-stu-id="189f6-104">List all recommendations</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="189f6-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="189f6-105">**Applies to:**</span></span>
- [<span data-ttu-id="189f6-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="189f6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="189f6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="189f6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="189f6-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="189f6-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="189f6-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="189f6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="189f6-110">조직에 영향을 주는 모든 보안 권장 사항 목록을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="189f6-110">Retrieves a list of all security recommendations affecting the organization.</span></span>

## <a name="permissions"></a><span data-ttu-id="189f6-111">사용 권한</span><span class="sxs-lookup"><span data-stu-id="189f6-111">Permissions</span></span>
<span data-ttu-id="189f6-112">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="189f6-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="189f6-113">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [Use Microsoft Defender for Endpoint API](apis-intro.md) for details을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="189f6-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="189f6-114">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="189f6-114">Permission type</span></span> |   <span data-ttu-id="189f6-115">사용 권한</span><span class="sxs-lookup"><span data-stu-id="189f6-115">Permission</span></span>  |   <span data-ttu-id="189f6-116">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="189f6-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="189f6-117">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="189f6-117">Application</span></span> |   <span data-ttu-id="189f6-118">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="189f6-118">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="189f6-119">'위협 및 취약성 관리 보안 권장 정보 읽기'</span><span class="sxs-lookup"><span data-stu-id="189f6-119">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="189f6-120">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="189f6-120">Delegated (work or school account)</span></span> | <span data-ttu-id="189f6-121">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="189f6-121">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="189f6-122">'위협 및 취약성 관리 보안 권장 정보 읽기'</span><span class="sxs-lookup"><span data-stu-id="189f6-122">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="189f6-123">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="189f6-123">HTTP request</span></span>
```
GET /api/recommendations
```

## <a name="request-headers"></a><span data-ttu-id="189f6-124">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="189f6-124">Request headers</span></span>

<span data-ttu-id="189f6-125">이름</span><span class="sxs-lookup"><span data-stu-id="189f6-125">Name</span></span> | <span data-ttu-id="189f6-126">유형</span><span class="sxs-lookup"><span data-stu-id="189f6-126">Type</span></span> | <span data-ttu-id="189f6-127">설명</span><span class="sxs-lookup"><span data-stu-id="189f6-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="189f6-128">권한 부여</span><span class="sxs-lookup"><span data-stu-id="189f6-128">Authorization</span></span> | <span data-ttu-id="189f6-129">문자열</span><span class="sxs-lookup"><span data-stu-id="189f6-129">String</span></span> | <span data-ttu-id="189f6-130">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="189f6-130">Bearer {token}.</span></span> <span data-ttu-id="189f6-131">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="189f6-131">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="189f6-132">요청 본문</span><span class="sxs-lookup"><span data-stu-id="189f6-132">Request body</span></span>
<span data-ttu-id="189f6-133">비어 있음</span><span class="sxs-lookup"><span data-stu-id="189f6-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="189f6-134">응답</span><span class="sxs-lookup"><span data-stu-id="189f6-134">Response</span></span>
<span data-ttu-id="189f6-135">성공하면 이 메서드는 본문의 보안 권장 사항 목록과 함께 200 OK를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="189f6-135">If successful, this method returns 200 OK with the list of security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="189f6-136">예제</span><span class="sxs-lookup"><span data-stu-id="189f6-136">Example</span></span>

<span data-ttu-id="189f6-137">**요청**</span><span class="sxs-lookup"><span data-stu-id="189f6-137">**Request**</span></span>

<span data-ttu-id="189f6-138">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="189f6-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/recommendations
```

<span data-ttu-id="189f6-139">**응답**</span><span class="sxs-lookup"><span data-stu-id="189f6-139">**Response**</span></span>

<span data-ttu-id="189f6-140">다음은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="189f6-140">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Recommendations",
    "value": [
        {
            "id": "va-_-microsoft-_-windows_10",
            "productName": "windows_10",
            "recommendationName": "Update Windows 10",
            "weaknesses": 397,
            "vendor": "microsoft",
            "recommendedVersion": "",
            "recommendationCategory": "Application",
            "subCategory": "",
            "severityScore": 0,
            "publicExploit": true,
            "activeAlert": false,
            "associatedThreats": [
                "3098b8ef-23b1-46b3-aed4-499e1928f9ed",
                "40c189d5-0330-4654-a816-e48c2b7f9c4b",
                "4b0c9702-9b6c-4ca2-9d02-1556869f56f8",
                "e8fc2121-3cf3-4dd2-9ea0-87d7e1d2b29d",
                "94b6e94b-0c1d-4817-ac06-c3b8639be3ab"
            ],
            "remediationType": "Update",
            "status": "Active",
            "configScoreImpact": 0,
            "exposureImpact": 7.674418604651163,
            "totalMachineCount": 37,
            "exposedMachinesCount": 7,
            "nonProductivityImpactedAssets": 0,
            "relatedComponent": "Windows 10"
        }
        ...
     ]
}
```
## <a name="see-also"></a><span data-ttu-id="189f6-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="189f6-141">See also</span></span>
- [<span data-ttu-id="189f6-142">위험 기반 위협 & 관리</span><span class="sxs-lookup"><span data-stu-id="189f6-142">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="189f6-143">위협 & 보안 권장</span><span class="sxs-lookup"><span data-stu-id="189f6-143">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)

