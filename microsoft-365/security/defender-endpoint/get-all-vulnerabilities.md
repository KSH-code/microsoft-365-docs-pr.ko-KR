---
title: 모든 취약성 확인
description: 조직에 영향을 주는 모든 취약점 목록을 검색합니다.
keywords: api, 그래프 api, 지원되는 api, get, 취약성 정보, mdatp tvm api
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
ms.openlocfilehash: c97b70b682351e5ad9d92435068b97622032f769
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166897"
---
# <a name="list-vulnerabilities"></a><span data-ttu-id="19aac-104">취약성 목록</span><span class="sxs-lookup"><span data-stu-id="19aac-104">List vulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="19aac-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="19aac-105">**Applies to:**</span></span>
- [<span data-ttu-id="19aac-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="19aac-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="19aac-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="19aac-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="19aac-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="19aac-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="19aac-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="19aac-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="19aac-110">조직에 영향을 주는 모든 취약점 목록을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="19aac-110">Retrieves a list of all the vulnerabilities affecting the organization.</span></span>

## <a name="permissions"></a><span data-ttu-id="19aac-111">사용 권한</span><span class="sxs-lookup"><span data-stu-id="19aac-111">Permissions</span></span>
<span data-ttu-id="19aac-112">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="19aac-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="19aac-113">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [Use Microsoft Defender for Endpoint API](apis-intro.md) for details을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="19aac-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="19aac-114">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="19aac-114">Permission type</span></span> |   <span data-ttu-id="19aac-115">사용 권한</span><span class="sxs-lookup"><span data-stu-id="19aac-115">Permission</span></span>  |   <span data-ttu-id="19aac-116">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="19aac-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="19aac-117">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="19aac-117">Application</span></span> |   <span data-ttu-id="19aac-118">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="19aac-118">Vulnerability.Read.All</span></span> |    <span data-ttu-id="19aac-119">'위협 및 취약성 관리 취약성 정보 읽기'</span><span class="sxs-lookup"><span data-stu-id="19aac-119">'Read Threat and Vulnerability Management vulnerability information'</span></span>
<span data-ttu-id="19aac-120">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="19aac-120">Delegated (work or school account)</span></span> | <span data-ttu-id="19aac-121">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="19aac-121">Vulnerability.Read</span></span> |   <span data-ttu-id="19aac-122">'위협 및 취약성 관리 취약성 정보 읽기'</span><span class="sxs-lookup"><span data-stu-id="19aac-122">'Read Threat and Vulnerability Management vulnerability information'</span></span>

## <a name="http-request"></a><span data-ttu-id="19aac-123">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="19aac-123">HTTP request</span></span>
```
GET /api/vulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="19aac-124">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="19aac-124">Request headers</span></span>

<span data-ttu-id="19aac-125">이름</span><span class="sxs-lookup"><span data-stu-id="19aac-125">Name</span></span> | <span data-ttu-id="19aac-126">유형</span><span class="sxs-lookup"><span data-stu-id="19aac-126">Type</span></span> | <span data-ttu-id="19aac-127">설명</span><span class="sxs-lookup"><span data-stu-id="19aac-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="19aac-128">권한 부여</span><span class="sxs-lookup"><span data-stu-id="19aac-128">Authorization</span></span> | <span data-ttu-id="19aac-129">문자열</span><span class="sxs-lookup"><span data-stu-id="19aac-129">String</span></span> | <span data-ttu-id="19aac-130">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="19aac-130">Bearer {token}.</span></span> <span data-ttu-id="19aac-131">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="19aac-131">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="19aac-132">요청 본문</span><span class="sxs-lookup"><span data-stu-id="19aac-132">Request body</span></span>
<span data-ttu-id="19aac-133">비어 있음</span><span class="sxs-lookup"><span data-stu-id="19aac-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="19aac-134">응답</span><span class="sxs-lookup"><span data-stu-id="19aac-134">Response</span></span>
<span data-ttu-id="19aac-135">성공하면 이 메서드는 본문의 취약점 목록과 함께 200 OK를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="19aac-135">If successful, this method returns 200 OK with the list of vulnerabilities in the body.</span></span>


## <a name="example"></a><span data-ttu-id="19aac-136">예제</span><span class="sxs-lookup"><span data-stu-id="19aac-136">Example</span></span>

<span data-ttu-id="19aac-137">**요청**</span><span class="sxs-lookup"><span data-stu-id="19aac-137">**Request**</span></span>

<span data-ttu-id="19aac-138">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="19aac-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/Vulnerabilities
```

<span data-ttu-id="19aac-139">**응답**</span><span class="sxs-lookup"><span data-stu-id="19aac-139">**Response**</span></span>

<span data-ttu-id="19aac-140">다음은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="19aac-140">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Vulnerabilities",
    "value": [
        {
            "id": "CVE-2019-0608",
            "name": "CVE-2019-0608",
            "description": "A spoofing vulnerability exists when Microsoft Browsers does not properly parse HTTP content. An attacker who successfully exploited this vulnerability could impersonate a user request by crafting HTTP queries. The specially crafted website could either spoof content or serve as a pivot to chain an attack with other vulnerabilities in web services.To exploit the vulnerability, the user must click a specially crafted URL. In an email attack scenario, an attacker could send an email message containing the specially crafted URL to the user in an attempt to convince the user to click it.In a web-based attack scenario, an attacker could host a specially crafted website designed to appear as a legitimate website to the user. However, the attacker would have no way to force the user to visit the specially crafted website. The attacker would have to convince the user to visit the specially crafted website, typically by way of enticement in an email or instant message, and then convince the user to interact with content on the website.The update addresses the vulnerability by correcting how Microsoft Browsers parses HTTP responses.",
            "severity": "Medium",
            "cvssV3": 4.3,
            "exposedMachines": 4,
            "publishedOn": "2019-10-08T00:00:00Z",
            "updatedOn": "2019-12-16T16:20:00Z",
            "publicExploit": false,
            "exploitVerified": false,
            "exploitInKit": false,
            "exploitTypes": [],
            "exploitUris": []
        }
        ...
    ]

}
```

## <a name="see-also"></a><span data-ttu-id="19aac-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="19aac-141">See also</span></span>
- [<span data-ttu-id="19aac-142">위험 기반 위협 & 관리</span><span class="sxs-lookup"><span data-stu-id="19aac-142">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="19aac-143">조직의 취약성</span><span class="sxs-lookup"><span data-stu-id="19aac-143">Vulnerabilities in your organization</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-weaknesses)
