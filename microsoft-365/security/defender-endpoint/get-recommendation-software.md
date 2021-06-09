---
title: 소프트웨어별 권장 사항 가져오기
description: 특정 소프트웨어와 관련된 보안 권장을 검색합니다.
keywords: api, 그래프 api, 지원되는 api, 다운로드, 보안 권장, 소프트웨어에 대한 보안 권장, 위협 및 취약성 관리, 위협 및 취약성 관리 api
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
ms.openlocfilehash: 9227987544e1cee1eeb4b65b5ae6bbf719558dd4
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845213"
---
# <a name="get-recommendation-by-software"></a><span data-ttu-id="1119a-104">소프트웨어별 권장 사항 가져오기</span><span class="sxs-lookup"><span data-stu-id="1119a-104">Get recommendation by software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1119a-105">**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="1119a-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="1119a-106">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="1119a-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1119a-107">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="1119a-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="1119a-108">특정 소프트웨어와 관련된 보안 권장을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="1119a-108">Retrieves a security recommendation related to a specific software.</span></span>

## <a name="permissions"></a><span data-ttu-id="1119a-109">사용 권한</span><span class="sxs-lookup"><span data-stu-id="1119a-109">Permissions</span></span>
<span data-ttu-id="1119a-110">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1119a-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="1119a-111">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [Use Microsoft Defender for Endpoint API](apis-intro.md) for details을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="1119a-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="1119a-112">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="1119a-112">Permission type</span></span> |   <span data-ttu-id="1119a-113">사용 권한</span><span class="sxs-lookup"><span data-stu-id="1119a-113">Permission</span></span>  |   <span data-ttu-id="1119a-114">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="1119a-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="1119a-115">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="1119a-115">Application</span></span> |   <span data-ttu-id="1119a-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="1119a-116">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="1119a-117">'위협 및 취약성 관리 보안 권장 정보 읽기'</span><span class="sxs-lookup"><span data-stu-id="1119a-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="1119a-118">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="1119a-118">Delegated (work or school account)</span></span> | <span data-ttu-id="1119a-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="1119a-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="1119a-120">'위협 및 취약성 관리 보안 권장 정보 읽기'</span><span class="sxs-lookup"><span data-stu-id="1119a-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="1119a-121">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="1119a-121">HTTP request</span></span>
```
GET /api/recommendations/{id}/software
```

## <a name="request-headers"></a><span data-ttu-id="1119a-122">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="1119a-122">Request headers</span></span>

<span data-ttu-id="1119a-123">이름</span><span class="sxs-lookup"><span data-stu-id="1119a-123">Name</span></span> | <span data-ttu-id="1119a-124">유형</span><span class="sxs-lookup"><span data-stu-id="1119a-124">Type</span></span> | <span data-ttu-id="1119a-125">설명</span><span class="sxs-lookup"><span data-stu-id="1119a-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="1119a-126">권한 부여</span><span class="sxs-lookup"><span data-stu-id="1119a-126">Authorization</span></span> | <span data-ttu-id="1119a-127">String</span><span class="sxs-lookup"><span data-stu-id="1119a-127">String</span></span> | <span data-ttu-id="1119a-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="1119a-128">Bearer {token}.</span></span> <span data-ttu-id="1119a-129">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="1119a-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="1119a-130">요청 본문</span><span class="sxs-lookup"><span data-stu-id="1119a-130">Request body</span></span>
<span data-ttu-id="1119a-131">비어 있음</span><span class="sxs-lookup"><span data-stu-id="1119a-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="1119a-132">응답</span><span class="sxs-lookup"><span data-stu-id="1119a-132">Response</span></span>
<span data-ttu-id="1119a-133">성공하면 이 메서드는 본문의 보안 권장 사항과 연결된 소프트웨어를 사용하여 200 OK를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1119a-133">If successful, this method returns 200 OK with the software associated with the security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="1119a-134">예시</span><span class="sxs-lookup"><span data-stu-id="1119a-134">Example</span></span>

<span data-ttu-id="1119a-135">**요청**</span><span class="sxs-lookup"><span data-stu-id="1119a-135">**Request**</span></span>

<span data-ttu-id="1119a-136">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="1119a-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome/software 
```

<span data-ttu-id="1119a-137">**응답**</span><span class="sxs-lookup"><span data-stu-id="1119a-137">**Response**</span></span>

<span data-ttu-id="1119a-138">다음은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="1119a-138">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Analytics.Contracts.PublicAPI.PublicProductDto",
    "id": "google-_-chrome",
    "name": "chrome",
    "vendor": "google",
    "weaknesses": 38,
    "publicExploit": false,
    "activeAlert": false,
    "exposedMachines": 5,
    "impactScore": 3.94418621
}
```

## <a name="related-topics"></a><span data-ttu-id="1119a-139">관련 항목</span><span class="sxs-lookup"><span data-stu-id="1119a-139">Related topics</span></span>
- [<span data-ttu-id="1119a-140">위험 기반 위협 & 관리</span><span class="sxs-lookup"><span data-stu-id="1119a-140">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="1119a-141">위협 & 보안 권장</span><span class="sxs-lookup"><span data-stu-id="1119a-141">Threat & Vulnerability security recommendation</span></span>](/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
