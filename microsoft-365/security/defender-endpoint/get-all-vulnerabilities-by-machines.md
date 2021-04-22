---
title: 컴퓨터 및 소프트웨어로 모든 취약성 확인
description: Machine and Software로 조직에 영향을 주는 모든 취약점 목록을 검색합니다.
keywords: api, 그래프 api, 지원되는 api, get, 취약성 정보, Endpoint tvm api용 Microsoft Defender
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
ms.openlocfilehash: 229c1f9e77a0cb85744155e82934b48dd63052b2
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933412"
---
# <a name="list-vulnerabilities-by-machine-and-software"></a><span data-ttu-id="1d847-104">컴퓨터 및 소프트웨어별 취약성 목록</span><span class="sxs-lookup"><span data-stu-id="1d847-104">List vulnerabilities by machine and software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1d847-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="1d847-105">**Applies to:**</span></span>
- [<span data-ttu-id="1d847-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1d847-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1d847-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1d847-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1d847-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="1d847-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1d847-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="1d847-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="1d847-110">컴퓨터 및 소프트웨어당 조직에 영향을 주는 모든 취약점 [목록을](machine.md) [검색합니다.](software.md)</span><span class="sxs-lookup"><span data-stu-id="1d847-110">Retrieves a list of all the vulnerabilities affecting the organization per [machine](machine.md) and [software](software.md).</span></span>
- <span data-ttu-id="1d847-111">취약성에 수정 KB가 있는 경우 응답에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d847-111">If the vulnerability has a fixing KB, it will appear in the response.</span></span>
- <span data-ttu-id="1d847-112">[OData V4 쿼리를 지원합니다.](https://www.odata.org/documentation/)</span><span class="sxs-lookup"><span data-stu-id="1d847-112">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
- <span data-ttu-id="1d847-113">OData는 ```$filter``` 모든 속성에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d847-113">The OData ```$filter``` is supported on all properties.</span></span>

>[!Tip]
><span data-ttu-id="1d847-114">이는 Power BI 통합을 위한 [좋은 API입니다.](api-power-bi.md)</span><span class="sxs-lookup"><span data-stu-id="1d847-114">This is great API for [Power BI integration](api-power-bi.md).</span></span>

## <a name="permissions"></a><span data-ttu-id="1d847-115">사용 권한</span><span class="sxs-lookup"><span data-stu-id="1d847-115">Permissions</span></span>
<span data-ttu-id="1d847-116">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1d847-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="1d847-117">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [Use Microsoft Defender for Endpoint API](apis-intro.md) for details을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="1d847-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="1d847-118">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="1d847-118">Permission type</span></span> |   <span data-ttu-id="1d847-119">사용 권한</span><span class="sxs-lookup"><span data-stu-id="1d847-119">Permission</span></span>  |   <span data-ttu-id="1d847-120">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="1d847-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="1d847-121">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="1d847-121">Application</span></span> |   <span data-ttu-id="1d847-122">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="1d847-122">Vulnerability.Read.All</span></span> |    <span data-ttu-id="1d847-123">'위협 및 취약성 관리 취약성 정보 읽기'</span><span class="sxs-lookup"><span data-stu-id="1d847-123">'Read Threat and Vulnerability Management vulnerability information'</span></span>
<span data-ttu-id="1d847-124">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="1d847-124">Delegated (work or school account)</span></span> | <span data-ttu-id="1d847-125">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="1d847-125">Vulnerability.Read</span></span> |   <span data-ttu-id="1d847-126">'위협 및 취약성 관리 취약성 정보 읽기'</span><span class="sxs-lookup"><span data-stu-id="1d847-126">'Read Threat and Vulnerability Management vulnerability information'</span></span>

## <a name="http-request"></a><span data-ttu-id="1d847-127">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="1d847-127">HTTP request</span></span>
```
GET /api/vulnerabilities/machinesVulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="1d847-128">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="1d847-128">Request headers</span></span>

<span data-ttu-id="1d847-129">이름</span><span class="sxs-lookup"><span data-stu-id="1d847-129">Name</span></span> | <span data-ttu-id="1d847-130">유형</span><span class="sxs-lookup"><span data-stu-id="1d847-130">Type</span></span> | <span data-ttu-id="1d847-131">설명</span><span class="sxs-lookup"><span data-stu-id="1d847-131">Description</span></span>
:---|:---|:---
<span data-ttu-id="1d847-132">권한 부여</span><span class="sxs-lookup"><span data-stu-id="1d847-132">Authorization</span></span> | <span data-ttu-id="1d847-133">문자열</span><span class="sxs-lookup"><span data-stu-id="1d847-133">String</span></span> | <span data-ttu-id="1d847-134">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="1d847-134">Bearer {token}.</span></span> <span data-ttu-id="1d847-135">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="1d847-135">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="1d847-136">요청 본문</span><span class="sxs-lookup"><span data-stu-id="1d847-136">Request body</span></span>
<span data-ttu-id="1d847-137">비어 있음</span><span class="sxs-lookup"><span data-stu-id="1d847-137">Empty</span></span>

## <a name="response"></a><span data-ttu-id="1d847-138">응답</span><span class="sxs-lookup"><span data-stu-id="1d847-138">Response</span></span>
<span data-ttu-id="1d847-139">성공하면 이 메서드는 본문의 취약점 목록과 함께 200 OK를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1d847-139">If successful, this method returns 200 OK with the list of vulnerabilities in the body.</span></span>


## <a name="example"></a><span data-ttu-id="1d847-140">예시</span><span class="sxs-lookup"><span data-stu-id="1d847-140">Example</span></span>

<span data-ttu-id="1d847-141">**요청**</span><span class="sxs-lookup"><span data-stu-id="1d847-141">**Request**</span></span>

<span data-ttu-id="1d847-142">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="1d847-142">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/vulnerabilities/machinesVulnerabilities
```

<span data-ttu-id="1d847-143">**응답**</span><span class="sxs-lookup"><span data-stu-id="1d847-143">**Response**</span></span>

<span data-ttu-id="1d847-144">다음은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="1d847-144">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicAssetVulnerabilityDto)",
    "value": [
        {
            "id": "5afa3afc92a7c63d4b70129e0a6f33f63a427e21-_-CVE-2020-6494-_-microsoft-_-edge_chromium-based-_-81.0.416.77-_-",
            "cveId": "CVE-2020-6494",
            "machineId": "5afa3afc92a7c63d4b70129e0a6f33f63a427e21",
            "fixingKbId": null,
            "productName": "edge_chromium-based",
            "productVendor": "microsoft",
            "productVersion": "81.0.416.77",
            "severity": "Low"
        },
        {
            "id": "7a704e17d1c2977c0e7b665fb18ae6e1fe7f3283-_-CVE-2016-3348-_-microsoft-_-windows_server_2012_r2-_-6.3.9600.19728-_-3185911",
            "cveId": "CVE-2016-3348",
            "machineId": "7a704e17d1c2977c0e7b665fb18ae6e1fe7f3283",
            "fixingKbId": "3185911",
            "productName": "windows_server_2012_r2",
            "productVendor": "microsoft",
            "productVersion": "6.3.9600.19728",
            "severity": "Low"
        },
        ...
    ]

}
```

## <a name="see-also"></a><span data-ttu-id="1d847-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1d847-145">See also</span></span>

- [<span data-ttu-id="1d847-146">위험 기반 위협 및 취약성 관리</span><span class="sxs-lookup"><span data-stu-id="1d847-146">Risk-based threat and vulnerability management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="1d847-147">조직의 취약성</span><span class="sxs-lookup"><span data-stu-id="1d847-147">Vulnerabilities in your organization</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-weaknesses)
