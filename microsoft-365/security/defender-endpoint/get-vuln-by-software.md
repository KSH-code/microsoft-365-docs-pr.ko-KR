---
title: 소프트웨어별 취약성 목록
description: 설치된 소프트웨어의 취약성 목록을 검색합니다.
keywords: api, 그래프 api, 지원되는 api, get, 취약성 목록, Endpoint tvm api용 Microsoft Defender
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
ms.openlocfilehash: c28417d9782d14d890e771ed401f8ee5d3c26bc0
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932766"
---
# <a name="list-vulnerabilities-by-software"></a><span data-ttu-id="81eab-104">소프트웨어별 취약성 목록</span><span class="sxs-lookup"><span data-stu-id="81eab-104">List vulnerabilities by software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="81eab-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="81eab-105">**Applies to:**</span></span>
- [<span data-ttu-id="81eab-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="81eab-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="81eab-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="81eab-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="81eab-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="81eab-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="81eab-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="81eab-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="81eab-110">설치된 소프트웨어의 취약성 목록을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="81eab-110">Retrieve a list of vulnerabilities in the installed software.</span></span> 

## <a name="permissions"></a><span data-ttu-id="81eab-111">사용 권한</span><span class="sxs-lookup"><span data-stu-id="81eab-111">Permissions</span></span>
<span data-ttu-id="81eab-112">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="81eab-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="81eab-113">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [Use Microsoft Defender for Endpoint API](apis-intro.md) for details을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="81eab-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="81eab-114">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="81eab-114">Permission type</span></span> |   <span data-ttu-id="81eab-115">사용 권한</span><span class="sxs-lookup"><span data-stu-id="81eab-115">Permission</span></span>  |   <span data-ttu-id="81eab-116">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="81eab-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="81eab-117">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="81eab-117">Application</span></span> | <span data-ttu-id="81eab-118">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="81eab-118">Software.Read.All</span></span> | <span data-ttu-id="81eab-119">'위협 및 취약성 관리 소프트웨어 정보 읽기'</span><span class="sxs-lookup"><span data-stu-id="81eab-119">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="81eab-120">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="81eab-120">Delegated (work or school account)</span></span> | <span data-ttu-id="81eab-121">Software.Read</span><span class="sxs-lookup"><span data-stu-id="81eab-121">Software.Read</span></span> | <span data-ttu-id="81eab-122">'위협 및 취약성 관리 소프트웨어 정보 읽기'</span><span class="sxs-lookup"><span data-stu-id="81eab-122">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="81eab-123">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="81eab-123">HTTP request</span></span>
```
GET /api/Software/{Id}/vulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="81eab-124">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="81eab-124">Request headers</span></span>

| <span data-ttu-id="81eab-125">이름</span><span class="sxs-lookup"><span data-stu-id="81eab-125">Name</span></span>        | <span data-ttu-id="81eab-126">유형</span><span class="sxs-lookup"><span data-stu-id="81eab-126">Type</span></span> | <span data-ttu-id="81eab-127">설명</span><span class="sxs-lookup"><span data-stu-id="81eab-127">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="81eab-128">권한 부여</span><span class="sxs-lookup"><span data-stu-id="81eab-128">Authorization</span></span> | <span data-ttu-id="81eab-129">문자열</span><span class="sxs-lookup"><span data-stu-id="81eab-129">String</span></span> | <span data-ttu-id="81eab-130">Bearer {token}. **필수 .**</span><span class="sxs-lookup"><span data-stu-id="81eab-130">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="81eab-131">요청 본문</span><span class="sxs-lookup"><span data-stu-id="81eab-131">Request body</span></span>
<span data-ttu-id="81eab-132">비어 있음</span><span class="sxs-lookup"><span data-stu-id="81eab-132">Empty</span></span>

## <a name="response"></a><span data-ttu-id="81eab-133">응답</span><span class="sxs-lookup"><span data-stu-id="81eab-133">Response</span></span>
<span data-ttu-id="81eab-134">성공하면 이 메서드는 지정된 소프트웨어에 의해 노출된 취약점 목록과 함께 200 OK를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="81eab-134">If successful, this method returns 200 OK with a list of vulnerabilities exposed by the specified software.</span></span> 


## <a name="example"></a><span data-ttu-id="81eab-135">예시</span><span class="sxs-lookup"><span data-stu-id="81eab-135">Example</span></span>

<span data-ttu-id="81eab-136">**요청**</span><span class="sxs-lookup"><span data-stu-id="81eab-136">**Request**</span></span>

<span data-ttu-id="81eab-137">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="81eab-137">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/vulnerabilities 
```

<span data-ttu-id="81eab-138">**응답**</span><span class="sxs-lookup"><span data-stu-id="81eab-138">**Response**</span></span>

<span data-ttu-id="81eab-139">다음은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="81eab-139">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(Analytics.Contracts.PublicAPI.PublicVulnerabilityDto)",
    "value": [
            {
                "id": "CVE-2017-0140",
                "name": "CVE-2017-0140",
                "description": "A security feature bypass vulnerability exists when Microsoft Edge improperly handles requests of different origins. The vulnerability allows Microsoft Edge to bypass Same-Origin Policy (SOP) restrictions, and to allow requests that should otherwise be ignored. An attacker who successfully exploited the vulnerability could force the browser to send data that would otherwise be restricted.In a web-based attack scenario, an attacker could host a specially crafted website that is designed to exploit the vulnerability through Microsoft Edge and then convince a user to view the website. The attacker could also take advantage of compromised websites, and websites that accept or host user-provided content or advertisements. These websites could contain specially crafted content that could exploit the vulnerability.The security update addresses the vulnerability by modifying how affected Microsoft Edge handles different-origin requests.",
                "severity": "Medium",
                "cvssV3": 4.2,
                "exposedMachines": 1,
                "publishedOn": "2017-03-14T00:00:00Z",
                "updatedOn": "2019-10-03T00:03:00Z",
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

