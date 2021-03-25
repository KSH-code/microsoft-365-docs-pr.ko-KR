---
title: 소프트웨어 버전 배포 목록
description: 조직의 소프트웨어 버전 배포 목록을 검색합니다.
keywords: api, 그래프 api, 지원되는 api, get, 소프트웨어 버전 배포, mdatp tvm api
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
ms.openlocfilehash: 88f446ddd87768817099c1a206bab17aa8be5b7b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198580"
---
# <a name="list-software-version-distribution"></a><span data-ttu-id="fa7ae-104">소프트웨어 버전 배포 목록</span><span class="sxs-lookup"><span data-stu-id="fa7ae-104">List software version distribution</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="fa7ae-105">**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="fa7ae-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="fa7ae-106">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="fa7ae-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="fa7ae-107">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="fa7ae-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="fa7ae-108">조직의 소프트웨어 버전 배포 목록을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="fa7ae-108">Retrieves a list of your organization's software version distribution.</span></span> 

## <a name="permissions"></a><span data-ttu-id="fa7ae-109">사용 권한</span><span class="sxs-lookup"><span data-stu-id="fa7ae-109">Permissions</span></span>
<span data-ttu-id="fa7ae-110">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="fa7ae-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="fa7ae-111">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [Use Microsoft Defender for Endpoint API](apis-intro.md) for details을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="fa7ae-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="fa7ae-112">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="fa7ae-112">Permission type</span></span> |   <span data-ttu-id="fa7ae-113">사용 권한</span><span class="sxs-lookup"><span data-stu-id="fa7ae-113">Permission</span></span>  |   <span data-ttu-id="fa7ae-114">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="fa7ae-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="fa7ae-115">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="fa7ae-115">Application</span></span> | <span data-ttu-id="fa7ae-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="fa7ae-116">Software.Read.All</span></span> | <span data-ttu-id="fa7ae-117">'위협 및 취약성 관리 소프트웨어 정보 읽기'</span><span class="sxs-lookup"><span data-stu-id="fa7ae-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="fa7ae-118">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="fa7ae-118">Delegated (work or school account)</span></span> | <span data-ttu-id="fa7ae-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="fa7ae-119">Software.Read</span></span> | <span data-ttu-id="fa7ae-120">'위협 및 취약성 관리 소프트웨어 정보 읽기'</span><span class="sxs-lookup"><span data-stu-id="fa7ae-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="fa7ae-121">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="fa7ae-121">HTTP request</span></span>
```
GET /api/Software/{Id}/distributions
```

## <a name="request-headers"></a><span data-ttu-id="fa7ae-122">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="fa7ae-122">Request headers</span></span>

| <span data-ttu-id="fa7ae-123">이름</span><span class="sxs-lookup"><span data-stu-id="fa7ae-123">Name</span></span>        | <span data-ttu-id="fa7ae-124">유형</span><span class="sxs-lookup"><span data-stu-id="fa7ae-124">Type</span></span> | <span data-ttu-id="fa7ae-125">설명</span><span class="sxs-lookup"><span data-stu-id="fa7ae-125">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="fa7ae-126">권한 부여</span><span class="sxs-lookup"><span data-stu-id="fa7ae-126">Authorization</span></span> | <span data-ttu-id="fa7ae-127">문자열</span><span class="sxs-lookup"><span data-stu-id="fa7ae-127">String</span></span> | <span data-ttu-id="fa7ae-128">Bearer {token}. **필수 .**</span><span class="sxs-lookup"><span data-stu-id="fa7ae-128">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="fa7ae-129">요청 본문</span><span class="sxs-lookup"><span data-stu-id="fa7ae-129">Request body</span></span>
<span data-ttu-id="fa7ae-130">비어 있음</span><span class="sxs-lookup"><span data-stu-id="fa7ae-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="fa7ae-131">응답</span><span class="sxs-lookup"><span data-stu-id="fa7ae-131">Response</span></span>
<span data-ttu-id="fa7ae-132">성공하면 이 메서드는 본문에 소프트웨어 배포 데이터 목록이 있는 200 OK를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="fa7ae-132">If successful, this method returns 200 OK with a list of software distributions data in the body.</span></span> 


## <a name="example"></a><span data-ttu-id="fa7ae-133">예제</span><span class="sxs-lookup"><span data-stu-id="fa7ae-133">Example</span></span>

<span data-ttu-id="fa7ae-134">**요청**</span><span class="sxs-lookup"><span data-stu-id="fa7ae-134">**Request**</span></span>

<span data-ttu-id="fa7ae-135">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="fa7ae-135">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/distributions
```

<span data-ttu-id="fa7ae-136">**응답**</span><span class="sxs-lookup"><span data-stu-id="fa7ae-136">**Response**</span></span>

<span data-ttu-id="fa7ae-137">다음은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="fa7ae-137">Here is an example of the response.</span></span>

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Distributions",
    "value": [
        {
            "version": "11.0.17134.1039",
            "installations": 1,
            "vulnerabilities": 11
        },
        {
            "version": "11.0.18363.535",
            "installations": 750,
            "vulnerabilities": 0
        }
        ...
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="fa7ae-138">관련 항목</span><span class="sxs-lookup"><span data-stu-id="fa7ae-138">Related topics</span></span>
- [<span data-ttu-id="fa7ae-139">위험 기반 위협 & 관리</span><span class="sxs-lookup"><span data-stu-id="fa7ae-139">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="fa7ae-140">위협 & 소프트웨어 인벤토리</span><span class="sxs-lookup"><span data-stu-id="fa7ae-140">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
