---
title: 소프트웨어 목록
description: 소프트웨어 인벤토리 목록을 검색합니다.
keywords: api, 그래프 api, 지원되는 api, get, 목록, 파일, 정보, 소프트웨어 인벤토리, 위협 & 취약성 관리 api, 끝점 tvm api용 Microsoft Defender
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
ms.openlocfilehash: 2b7375f04094cdb56b0801adf2c1c0b7a8ab3098
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844277"
---
# <a name="list-software-inventory-api"></a><span data-ttu-id="c8965-104">소프트웨어 인벤토리 목록 API</span><span class="sxs-lookup"><span data-stu-id="c8965-104">List software inventory API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c8965-105">**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="c8965-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="c8965-106">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="c8965-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c8965-107">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="c8965-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="c8965-108">조직 소프트웨어 인벤토리를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="c8965-108">Retrieves the organization software inventory.</span></span>

## <a name="permissions"></a><span data-ttu-id="c8965-109">사용 권한</span><span class="sxs-lookup"><span data-stu-id="c8965-109">Permissions</span></span>
<span data-ttu-id="c8965-110">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c8965-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="c8965-111">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [Use Microsoft Defender for Endpoint API](apis-intro.md) for details을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="c8965-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="c8965-112">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="c8965-112">Permission type</span></span> |   <span data-ttu-id="c8965-113">사용 권한</span><span class="sxs-lookup"><span data-stu-id="c8965-113">Permission</span></span>  |   <span data-ttu-id="c8965-114">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="c8965-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="c8965-115">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="c8965-115">Application</span></span> |<span data-ttu-id="c8965-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="c8965-116">Software.Read.All</span></span> |    <span data-ttu-id="c8965-117">'위협 및 취약성 관리 소프트웨어 정보 읽기'</span><span class="sxs-lookup"><span data-stu-id="c8965-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="c8965-118">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="c8965-118">Delegated (work or school account)</span></span> | <span data-ttu-id="c8965-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="c8965-119">Software.Read</span></span> |    <span data-ttu-id="c8965-120">'위협 및 취약성 관리 소프트웨어 정보 읽기'</span><span class="sxs-lookup"><span data-stu-id="c8965-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="c8965-121">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="c8965-121">HTTP request</span></span>
```
GET /api/Software
```

## <a name="request-headers"></a><span data-ttu-id="c8965-122">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="c8965-122">Request headers</span></span>

<span data-ttu-id="c8965-123">이름</span><span class="sxs-lookup"><span data-stu-id="c8965-123">Name</span></span> | <span data-ttu-id="c8965-124">유형</span><span class="sxs-lookup"><span data-stu-id="c8965-124">Type</span></span> | <span data-ttu-id="c8965-125">설명</span><span class="sxs-lookup"><span data-stu-id="c8965-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="c8965-126">권한 부여</span><span class="sxs-lookup"><span data-stu-id="c8965-126">Authorization</span></span> | <span data-ttu-id="c8965-127">String</span><span class="sxs-lookup"><span data-stu-id="c8965-127">String</span></span> | <span data-ttu-id="c8965-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="c8965-128">Bearer {token}.</span></span> <span data-ttu-id="c8965-129">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="c8965-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="c8965-130">요청 본문</span><span class="sxs-lookup"><span data-stu-id="c8965-130">Request body</span></span>
<span data-ttu-id="c8965-131">비어 있음</span><span class="sxs-lookup"><span data-stu-id="c8965-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="c8965-132">응답</span><span class="sxs-lookup"><span data-stu-id="c8965-132">Response</span></span>
<span data-ttu-id="c8965-133">성공하면 이 메서드는 본문에 소프트웨어 인벤토리가 있는 200 OK를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c8965-133">If successful, this method returns 200 OK with the software inventory in the body.</span></span>


## <a name="example"></a><span data-ttu-id="c8965-134">예시</span><span class="sxs-lookup"><span data-stu-id="c8965-134">Example</span></span>

<span data-ttu-id="c8965-135">**요청**</span><span class="sxs-lookup"><span data-stu-id="c8965-135">**Request**</span></span>

<span data-ttu-id="c8965-136">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="c8965-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software
```

<span data-ttu-id="c8965-137">**응답**</span><span class="sxs-lookup"><span data-stu-id="c8965-137">**Response**</span></span>

<span data-ttu-id="c8965-138">다음은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="c8965-138">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Software",
    "value": [
            {
                "id": "microsoft-_-edge",
                "name": "edge",
                "vendor": "microsoft",
                "weaknesses": 467,
                "publicExploit": true,
                "activeAlert": false,
                "exposedMachines": 172,
                "impactScore": 2.39947438
            }
            ...
        ]
}
```

## <a name="related-topics"></a><span data-ttu-id="c8965-139">관련 항목</span><span class="sxs-lookup"><span data-stu-id="c8965-139">Related topics</span></span>
- [<span data-ttu-id="c8965-140">위험 기반 위협 & 관리</span><span class="sxs-lookup"><span data-stu-id="c8965-140">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="c8965-141">위협 & 소프트웨어 인벤토리</span><span class="sxs-lookup"><span data-stu-id="c8965-141">Threat & Vulnerability software inventory</span></span>](/microsoft-365/security/defender-endpoint/tvm-software-inventory)
