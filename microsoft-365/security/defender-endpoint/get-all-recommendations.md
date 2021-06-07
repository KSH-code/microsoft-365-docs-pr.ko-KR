---
title: 모든 권장 사항 목록
description: 조직에 영향을 주는 모든 보안 권장 사항 목록을 검색합니다.
keywords: api, 그래프 api, 지원되는 api, 다운로드, 보안 권장 사항, Endpoint tvm api용 Microsoft Defender, 위협 및 취약성 관리, 위협 및 취약성 관리 api
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 0a58287a9bd48a4d19144a40674e1d3ad3bd256a
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52768934"
---
# <a name="list-all-recommendations"></a><span data-ttu-id="093fa-104">모든 권장 사항 목록</span><span class="sxs-lookup"><span data-stu-id="093fa-104">List all recommendations</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="093fa-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="093fa-105">**Applies to:**</span></span>
- [<span data-ttu-id="093fa-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="093fa-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="093fa-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="093fa-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="093fa-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="093fa-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="093fa-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="093fa-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="093fa-110">조직에 영향을 주는 모든 보안 권장 사항 목록을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="093fa-110">Retrieves a list of all security recommendations affecting the organization.</span></span>

## <a name="permissions"></a><span data-ttu-id="093fa-111">사용 권한</span><span class="sxs-lookup"><span data-stu-id="093fa-111">Permissions</span></span>
<span data-ttu-id="093fa-112">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="093fa-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="093fa-113">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [Use Microsoft Defender for Endpoint API](apis-intro.md) for details을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="093fa-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="093fa-114">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="093fa-114">Permission type</span></span> |   <span data-ttu-id="093fa-115">사용 권한</span><span class="sxs-lookup"><span data-stu-id="093fa-115">Permission</span></span>  |   <span data-ttu-id="093fa-116">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="093fa-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="093fa-117">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="093fa-117">Application</span></span> |   <span data-ttu-id="093fa-118">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="093fa-118">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="093fa-119">'위협 및 취약성 관리 보안 권장 정보 읽기'</span><span class="sxs-lookup"><span data-stu-id="093fa-119">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="093fa-120">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="093fa-120">Delegated (work or school account)</span></span> | <span data-ttu-id="093fa-121">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="093fa-121">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="093fa-122">'위협 및 취약성 관리 보안 권장 정보 읽기'</span><span class="sxs-lookup"><span data-stu-id="093fa-122">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="093fa-123">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="093fa-123">HTTP request</span></span>
```
GET /api/recommendations
```

## <a name="request-headers"></a><span data-ttu-id="093fa-124">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="093fa-124">Request headers</span></span>

<span data-ttu-id="093fa-125">이름</span><span class="sxs-lookup"><span data-stu-id="093fa-125">Name</span></span> | <span data-ttu-id="093fa-126">유형</span><span class="sxs-lookup"><span data-stu-id="093fa-126">Type</span></span> | <span data-ttu-id="093fa-127">설명</span><span class="sxs-lookup"><span data-stu-id="093fa-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="093fa-128">권한 부여</span><span class="sxs-lookup"><span data-stu-id="093fa-128">Authorization</span></span> | <span data-ttu-id="093fa-129">String</span><span class="sxs-lookup"><span data-stu-id="093fa-129">String</span></span> | <span data-ttu-id="093fa-130">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="093fa-130">Bearer {token}.</span></span> <span data-ttu-id="093fa-131">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="093fa-131">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="093fa-132">요청 본문</span><span class="sxs-lookup"><span data-stu-id="093fa-132">Request body</span></span>
<span data-ttu-id="093fa-133">비어 있음</span><span class="sxs-lookup"><span data-stu-id="093fa-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="093fa-134">응답</span><span class="sxs-lookup"><span data-stu-id="093fa-134">Response</span></span>
<span data-ttu-id="093fa-135">성공하면 이 메서드는 본문의 보안 권장 사항 목록과 함께 200 OK를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="093fa-135">If successful, this method returns 200 OK with the list of security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="093fa-136">예시</span><span class="sxs-lookup"><span data-stu-id="093fa-136">Example</span></span>

<span data-ttu-id="093fa-137">**요청**</span><span class="sxs-lookup"><span data-stu-id="093fa-137">**Request**</span></span>

<span data-ttu-id="093fa-138">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="093fa-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/recommendations
```

<span data-ttu-id="093fa-139">**응답**</span><span class="sxs-lookup"><span data-stu-id="093fa-139">**Response**</span></span>

<span data-ttu-id="093fa-140">다음은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="093fa-140">Here is an example of the response.</span></span>


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
## <a name="see-also"></a><span data-ttu-id="093fa-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="093fa-141">See also</span></span>
- [<span data-ttu-id="093fa-142">위험 기반 위협 & 관리</span><span class="sxs-lookup"><span data-stu-id="093fa-142">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="093fa-143">위협 & 보안 권장</span><span class="sxs-lookup"><span data-stu-id="093fa-143">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)

