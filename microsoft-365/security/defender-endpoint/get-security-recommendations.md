---
title: 보안 권장 사항 가져오기
description: 지정한 장치 ID와 관련된 보안 권장 사항 컬렉션을 검색합니다.
keywords: api, 그래프 api, 지원되는 api, get, 목록, 파일, 정보, 장치당 보안 권장, 위협 & 취약성 관리 api, 끝점 tvm api용 Microsoft Defender
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
ms.openlocfilehash: bc209687d51b3e05bfcfd6028042ba5912b877f6
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935308"
---
# <a name="get-security-recommendations"></a><span data-ttu-id="4189e-104">보안 권장 사항 가져오기</span><span class="sxs-lookup"><span data-stu-id="4189e-104">Get security recommendations</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4189e-105">**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="4189e-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="4189e-106">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="4189e-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4189e-107">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="4189e-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="4189e-108">지정한 장치 ID와 관련된 보안 권장 사항 컬렉션을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="4189e-108">Retrieves a collection of security recommendations related to a given device ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="4189e-109">사용 권한</span><span class="sxs-lookup"><span data-stu-id="4189e-109">Permissions</span></span>
<span data-ttu-id="4189e-110">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4189e-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="4189e-111">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="4189e-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="4189e-112">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="4189e-112">Permission type</span></span> |   <span data-ttu-id="4189e-113">사용 권한</span><span class="sxs-lookup"><span data-stu-id="4189e-113">Permission</span></span>  |   <span data-ttu-id="4189e-114">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="4189e-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="4189e-115">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="4189e-115">Application</span></span> | <span data-ttu-id="4189e-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="4189e-116">SecurityRecommendation.Read.All</span></span> | <span data-ttu-id="4189e-117">'위협 및 취약성 관리 보안 권장 정보 읽기'</span><span class="sxs-lookup"><span data-stu-id="4189e-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="4189e-118">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="4189e-118">Delegated (work or school account)</span></span> | <span data-ttu-id="4189e-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="4189e-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="4189e-120">'위협 및 취약성 관리 보안 권장 정보 읽기'</span><span class="sxs-lookup"><span data-stu-id="4189e-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="4189e-121">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="4189e-121">HTTP request</span></span>
```
GET /api/machines/{machineId}/recommendations
```

## <a name="request-headers"></a><span data-ttu-id="4189e-122">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="4189e-122">Request headers</span></span>

<span data-ttu-id="4189e-123">이름</span><span class="sxs-lookup"><span data-stu-id="4189e-123">Name</span></span> | <span data-ttu-id="4189e-124">유형</span><span class="sxs-lookup"><span data-stu-id="4189e-124">Type</span></span> | <span data-ttu-id="4189e-125">설명</span><span class="sxs-lookup"><span data-stu-id="4189e-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="4189e-126">권한 부여</span><span class="sxs-lookup"><span data-stu-id="4189e-126">Authorization</span></span> | <span data-ttu-id="4189e-127">문자열</span><span class="sxs-lookup"><span data-stu-id="4189e-127">String</span></span> | <span data-ttu-id="4189e-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="4189e-128">Bearer {token}.</span></span> <span data-ttu-id="4189e-129">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="4189e-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="4189e-130">요청 본문</span><span class="sxs-lookup"><span data-stu-id="4189e-130">Request body</span></span>
<span data-ttu-id="4189e-131">비어 있음</span><span class="sxs-lookup"><span data-stu-id="4189e-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="4189e-132">응답</span><span class="sxs-lookup"><span data-stu-id="4189e-132">Response</span></span>
<span data-ttu-id="4189e-133">성공하면 이 메서드는 본문의 보안 권장 사항을 사용하여 200 OK를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4189e-133">If successful, this method returns 200 OK with the security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="4189e-134">예시</span><span class="sxs-lookup"><span data-stu-id="4189e-134">Example</span></span>

<span data-ttu-id="4189e-135">**요청**</span><span class="sxs-lookup"><span data-stu-id="4189e-135">**Request**</span></span>

<span data-ttu-id="4189e-136">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="4189e-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/recommendations
```

<span data-ttu-id="4189e-137">**응답**</span><span class="sxs-lookup"><span data-stu-id="4189e-137">**Response**</span></span>

<span data-ttu-id="4189e-138">다음은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="4189e-138">Here is an example of the response.</span></span>


```
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Recommendations",
    "value": [
        {
            "id": "va-_-git-scm-_-git",
            "productName": "git",
            "recommendationName": "Update Git to version 2.24.1.2",
            "weaknesses": 3,
            "vendor": "git-scm",
            "recommendedVersion": "2.24.1.2",
            "recommendationCategory": "Application",
            "subCategory": "",
            "severityScore": 0,
            "publicExploit": false,
            "activeAlert": false,
            "associatedThreats": [],
            "remediationType": "Update",
            "status": "Active",
            "configScoreImpact": 0,
            "exposureImpact": 0,
            "totalMachineCount": 0,
            "exposedMachinesCount": 1,
            "nonProductivityImpactedAssets": 0,
            "relatedComponent": "Git"
        },
…
}
```

## <a name="related-topics"></a><span data-ttu-id="4189e-139">관련 항목</span><span class="sxs-lookup"><span data-stu-id="4189e-139">Related topics</span></span>
- [<span data-ttu-id="4189e-140">위험 기반 위협 & 관리</span><span class="sxs-lookup"><span data-stu-id="4189e-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="4189e-141">위협 & 보안 권장</span><span class="sxs-lookup"><span data-stu-id="4189e-141">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
