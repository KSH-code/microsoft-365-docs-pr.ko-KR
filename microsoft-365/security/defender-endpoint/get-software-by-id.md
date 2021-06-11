---
title: ID로 소프트웨어 다운로드
description: 장치 그룹당 노출 점수 목록을 검색합니다.
keywords: api, 그래프 api, 지원되는 api, get, software, Endpoint tvm api용 Microsoft Defender
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
ms.openlocfilehash: d9a7d97cea96f919f1ec7cd1e37e7a8f27042c79
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845093"
---
# <a name="get-software-by-id"></a><span data-ttu-id="3e1b7-104">ID로 소프트웨어 다운로드</span><span class="sxs-lookup"><span data-stu-id="3e1b7-104">Get software by Id</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3e1b7-105">**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="3e1b7-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="3e1b7-106">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="3e1b7-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3e1b7-107">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="3e1b7-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="3e1b7-108">ID로 소프트웨어 세부 정보를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="3e1b7-108">Retrieves software details by ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="3e1b7-109">사용 권한</span><span class="sxs-lookup"><span data-stu-id="3e1b7-109">Permissions</span></span>
<span data-ttu-id="3e1b7-110">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3e1b7-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="3e1b7-111">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [Use Microsoft Defender for Endpoint API](apis-intro.md) for details을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="3e1b7-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="3e1b7-112">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="3e1b7-112">Permission type</span></span> |   <span data-ttu-id="3e1b7-113">사용 권한</span><span class="sxs-lookup"><span data-stu-id="3e1b7-113">Permission</span></span>  |   <span data-ttu-id="3e1b7-114">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="3e1b7-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="3e1b7-115">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="3e1b7-115">Application</span></span> | <span data-ttu-id="3e1b7-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="3e1b7-116">Software.Read.All</span></span> | <span data-ttu-id="3e1b7-117">'위협 및 취약성 관리 소프트웨어 정보 읽기'</span><span class="sxs-lookup"><span data-stu-id="3e1b7-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="3e1b7-118">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="3e1b7-118">Delegated (work or school account)</span></span> | <span data-ttu-id="3e1b7-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="3e1b7-119">Software.Read</span></span> | <span data-ttu-id="3e1b7-120">'위협 및 취약성 관리 소프트웨어 정보 읽기'</span><span class="sxs-lookup"><span data-stu-id="3e1b7-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="3e1b7-121">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="3e1b7-121">HTTP request</span></span>
```
GET /api/Software/{Id}
```

## <a name="request-headers"></a><span data-ttu-id="3e1b7-122">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="3e1b7-122">Request headers</span></span>

| <span data-ttu-id="3e1b7-123">이름</span><span class="sxs-lookup"><span data-stu-id="3e1b7-123">Name</span></span>        | <span data-ttu-id="3e1b7-124">유형</span><span class="sxs-lookup"><span data-stu-id="3e1b7-124">Type</span></span> | <span data-ttu-id="3e1b7-125">설명</span><span class="sxs-lookup"><span data-stu-id="3e1b7-125">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="3e1b7-126">권한 부여</span><span class="sxs-lookup"><span data-stu-id="3e1b7-126">Authorization</span></span> | <span data-ttu-id="3e1b7-127">String</span><span class="sxs-lookup"><span data-stu-id="3e1b7-127">String</span></span> | <span data-ttu-id="3e1b7-128">Bearer {token}. **필수 .**</span><span class="sxs-lookup"><span data-stu-id="3e1b7-128">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="3e1b7-129">요청 본문</span><span class="sxs-lookup"><span data-stu-id="3e1b7-129">Request body</span></span>
<span data-ttu-id="3e1b7-130">비어 있음</span><span class="sxs-lookup"><span data-stu-id="3e1b7-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="3e1b7-131">응답</span><span class="sxs-lookup"><span data-stu-id="3e1b7-131">Response</span></span>
<span data-ttu-id="3e1b7-132">성공하면 이 메서드는 본문에 지정된 소프트웨어 데이터를 사용하여 200 OK를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="3e1b7-132">If successful, this method returns 200 OK with the specified software data in the body.</span></span> 


## <a name="example"></a><span data-ttu-id="3e1b7-133">예시</span><span class="sxs-lookup"><span data-stu-id="3e1b7-133">Example</span></span>

<span data-ttu-id="3e1b7-134">**요청**</span><span class="sxs-lookup"><span data-stu-id="3e1b7-134">**Request**</span></span>

<span data-ttu-id="3e1b7-135">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="3e1b7-135">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge
```

<span data-ttu-id="3e1b7-136">**응답**</span><span class="sxs-lookup"><span data-stu-id="3e1b7-136">**Response**</span></span>

<span data-ttu-id="3e1b7-137">다음은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="3e1b7-137">Here is an example of the response.</span></span>

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Software/$entity",
    "id": "microsoft-_-edge",
    "name": "edge",
    "vendor": "microsoft",
    "weaknesses": 467,
    "publicExploit": true,
    "activeAlert": false,
    "exposedMachines": 172,
    "impactScore": 2.39947438
}
```

## <a name="related-topics"></a><span data-ttu-id="3e1b7-138">관련 항목</span><span class="sxs-lookup"><span data-stu-id="3e1b7-138">Related topics</span></span>
- [<span data-ttu-id="3e1b7-139">위험 기반 위협 & 관리</span><span class="sxs-lookup"><span data-stu-id="3e1b7-139">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="3e1b7-140">위협 & 소프트웨어 인벤토리</span><span class="sxs-lookup"><span data-stu-id="3e1b7-140">Threat & Vulnerability software inventory</span></span>](/microsoft-365/security/defender-endpoint/tvm-software-inventory)
