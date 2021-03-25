---
title: 목록 소프트웨어
description: 소프트웨어 인벤토리 목록을 검색합니다.
keywords: api, 그래프 api, 지원되는 api, get, 목록, 파일, 정보, 소프트웨어 인벤토리, 위협 & 취약성 관리 api, mdatp tvm api
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
ms.openlocfilehash: 867fb57f61bd98b7c0afabd20b27e68d6bf45ef7
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198568"
---
# <a name="list-software-inventory-api"></a><span data-ttu-id="9f7a4-104">소프트웨어 인벤토리 목록 API</span><span class="sxs-lookup"><span data-stu-id="9f7a4-104">List software inventory API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9f7a4-105">**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="9f7a4-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="9f7a4-106">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="9f7a4-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9f7a4-107">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="9f7a4-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="9f7a4-108">조직 소프트웨어 인벤토리를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="9f7a4-108">Retrieves the organization software inventory.</span></span>

## <a name="permissions"></a><span data-ttu-id="9f7a4-109">사용 권한</span><span class="sxs-lookup"><span data-stu-id="9f7a4-109">Permissions</span></span>
<span data-ttu-id="9f7a4-110">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9f7a4-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="9f7a4-111">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [Use Microsoft Defender for Endpoint API](apis-intro.md) for details을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="9f7a4-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="9f7a4-112">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="9f7a4-112">Permission type</span></span> |   <span data-ttu-id="9f7a4-113">사용 권한</span><span class="sxs-lookup"><span data-stu-id="9f7a4-113">Permission</span></span>  |   <span data-ttu-id="9f7a4-114">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="9f7a4-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="9f7a4-115">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="9f7a4-115">Application</span></span> |<span data-ttu-id="9f7a4-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="9f7a4-116">Software.Read.All</span></span> |    <span data-ttu-id="9f7a4-117">'위협 및 취약성 관리 소프트웨어 정보 읽기'</span><span class="sxs-lookup"><span data-stu-id="9f7a4-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="9f7a4-118">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="9f7a4-118">Delegated (work or school account)</span></span> | <span data-ttu-id="9f7a4-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="9f7a4-119">Software.Read</span></span> |    <span data-ttu-id="9f7a4-120">'위협 및 취약성 관리 소프트웨어 정보 읽기'</span><span class="sxs-lookup"><span data-stu-id="9f7a4-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="9f7a4-121">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="9f7a4-121">HTTP request</span></span>
```
GET /api/Software
```

## <a name="request-headers"></a><span data-ttu-id="9f7a4-122">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="9f7a4-122">Request headers</span></span>

<span data-ttu-id="9f7a4-123">이름</span><span class="sxs-lookup"><span data-stu-id="9f7a4-123">Name</span></span> | <span data-ttu-id="9f7a4-124">유형</span><span class="sxs-lookup"><span data-stu-id="9f7a4-124">Type</span></span> | <span data-ttu-id="9f7a4-125">설명</span><span class="sxs-lookup"><span data-stu-id="9f7a4-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="9f7a4-126">권한 부여</span><span class="sxs-lookup"><span data-stu-id="9f7a4-126">Authorization</span></span> | <span data-ttu-id="9f7a4-127">문자열</span><span class="sxs-lookup"><span data-stu-id="9f7a4-127">String</span></span> | <span data-ttu-id="9f7a4-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="9f7a4-128">Bearer {token}.</span></span> <span data-ttu-id="9f7a4-129">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="9f7a4-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="9f7a4-130">요청 본문</span><span class="sxs-lookup"><span data-stu-id="9f7a4-130">Request body</span></span>
<span data-ttu-id="9f7a4-131">비어 있음</span><span class="sxs-lookup"><span data-stu-id="9f7a4-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="9f7a4-132">응답</span><span class="sxs-lookup"><span data-stu-id="9f7a4-132">Response</span></span>
<span data-ttu-id="9f7a4-133">성공하면 이 메서드는 본문에 소프트웨어 인벤토리가 있는 200 OK를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9f7a4-133">If successful, this method returns 200 OK with the software inventory in the body.</span></span>


## <a name="example"></a><span data-ttu-id="9f7a4-134">예제</span><span class="sxs-lookup"><span data-stu-id="9f7a4-134">Example</span></span>

<span data-ttu-id="9f7a4-135">**요청**</span><span class="sxs-lookup"><span data-stu-id="9f7a4-135">**Request**</span></span>

<span data-ttu-id="9f7a4-136">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="9f7a4-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software
```

<span data-ttu-id="9f7a4-137">**응답**</span><span class="sxs-lookup"><span data-stu-id="9f7a4-137">**Response**</span></span>

<span data-ttu-id="9f7a4-138">다음은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="9f7a4-138">Here is an example of the response.</span></span>


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

## <a name="related-topics"></a><span data-ttu-id="9f7a4-139">관련 항목</span><span class="sxs-lookup"><span data-stu-id="9f7a4-139">Related topics</span></span>
- [<span data-ttu-id="9f7a4-140">위험 기반 위협 & 관리</span><span class="sxs-lookup"><span data-stu-id="9f7a4-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="9f7a4-141">위협 & 소프트웨어 인벤토리</span><span class="sxs-lookup"><span data-stu-id="9f7a4-141">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
