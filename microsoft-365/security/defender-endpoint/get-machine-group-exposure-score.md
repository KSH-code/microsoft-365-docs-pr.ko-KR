---
title: 장치 그룹당 노출 점수 나열
description: 장치 그룹당 노출 점수 목록을 검색합니다.
keywords: api, 그래프 api, 지원되는 api, get, 노출 점수, 장치 그룹, 장치 그룹 노출 점수
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: dansimp
ms.author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 71daccdbcb223ac48d80721bf0a296d9c1a7c98c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770100"
---
# <a name="list-exposure-score-by-device-group"></a><span data-ttu-id="9b4d8-104">장치 그룹당 노출 점수 나열</span><span class="sxs-lookup"><span data-stu-id="9b4d8-104">List exposure score by device group</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9b4d8-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="9b4d8-105">**Applies to:**</span></span>
- [<span data-ttu-id="9b4d8-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="9b4d8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9b4d8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9b4d8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="9b4d8-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="9b4d8-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="9b4d8-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="9b4d8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="9b4d8-110">지정한 도메인 주소와 관련된 경고 컬렉션을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="9b4d8-110">Retrieves a collection of alerts related to a given domain address.</span></span>

## <a name="permissions"></a><span data-ttu-id="9b4d8-111">사용 권한</span><span class="sxs-lookup"><span data-stu-id="9b4d8-111">Permissions</span></span>

<span data-ttu-id="9b4d8-112">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9b4d8-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="9b4d8-113">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="9b4d8-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="9b4d8-114">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="9b4d8-114">Permission type</span></span> |   <span data-ttu-id="9b4d8-115">사용 권한</span><span class="sxs-lookup"><span data-stu-id="9b4d8-115">Permission</span></span>  |   <span data-ttu-id="9b4d8-116">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="9b4d8-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="9b4d8-117">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="9b4d8-117">Application</span></span> | <span data-ttu-id="9b4d8-118">Score.Read.All</span><span class="sxs-lookup"><span data-stu-id="9b4d8-118">Score.Read.All</span></span> | <span data-ttu-id="9b4d8-119">'위협 및 취약성 관리 점수 읽기'</span><span class="sxs-lookup"><span data-stu-id="9b4d8-119">'Read Threat and Vulnerability Management score'</span></span>
<span data-ttu-id="9b4d8-120">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="9b4d8-120">Delegated (work or school account)</span></span> | <span data-ttu-id="9b4d8-121">Score.Read</span><span class="sxs-lookup"><span data-stu-id="9b4d8-121">Score.Read</span></span> | <span data-ttu-id="9b4d8-122">'위협 및 취약성 관리 점수 읽기'</span><span class="sxs-lookup"><span data-stu-id="9b4d8-122">'Read Threat and Vulnerability Management score'</span></span>

## <a name="http-request"></a><span data-ttu-id="9b4d8-123">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="9b4d8-123">HTTP request</span></span>

```
GET /api/exposureScore/ByMachineGroups
```

## <a name="request-headers"></a><span data-ttu-id="9b4d8-124">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="9b4d8-124">Request headers</span></span>

| <span data-ttu-id="9b4d8-125">이름</span><span class="sxs-lookup"><span data-stu-id="9b4d8-125">Name</span></span>        | <span data-ttu-id="9b4d8-126">유형</span><span class="sxs-lookup"><span data-stu-id="9b4d8-126">Type</span></span> | <span data-ttu-id="9b4d8-127">설명</span><span class="sxs-lookup"><span data-stu-id="9b4d8-127">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="9b4d8-128">권한 부여</span><span class="sxs-lookup"><span data-stu-id="9b4d8-128">Authorization</span></span> | <span data-ttu-id="9b4d8-129">String</span><span class="sxs-lookup"><span data-stu-id="9b4d8-129">String</span></span> | <span data-ttu-id="9b4d8-130">Bearer {token}. **필수 .**</span><span class="sxs-lookup"><span data-stu-id="9b4d8-130">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="9b4d8-131">요청 본문</span><span class="sxs-lookup"><span data-stu-id="9b4d8-131">Request body</span></span>

<span data-ttu-id="9b4d8-132">비어 있음</span><span class="sxs-lookup"><span data-stu-id="9b4d8-132">Empty</span></span>

## <a name="response"></a><span data-ttu-id="9b4d8-133">응답</span><span class="sxs-lookup"><span data-stu-id="9b4d8-133">Response</span></span>

<span data-ttu-id="9b4d8-134">성공하면 이 메서드는 응답 본문의 장치 그룹 데이터당 노출 점수 목록을 사용하여 200 OK를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9b4d8-134">If successful, this method returns 200 OK, with a list of exposure score per device group data in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="9b4d8-135">예시</span><span class="sxs-lookup"><span data-stu-id="9b4d8-135">Example</span></span>

### <a name="request"></a><span data-ttu-id="9b4d8-136">요청</span><span class="sxs-lookup"><span data-stu-id="9b4d8-136">Request</span></span>

<span data-ttu-id="9b4d8-137">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="9b4d8-137">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/exposureScore/ByMachineGroups
```

### <a name="response"></a><span data-ttu-id="9b4d8-138">응답</span><span class="sxs-lookup"><span data-stu-id="9b4d8-138">Response</span></span>

<span data-ttu-id="9b4d8-139">다음은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="9b4d8-139">Here is an example of the response.</span></span>

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ExposureScore",
    "value": [
        {
            "time": "2019-12-03T09:51:28.214338Z",
            "score": 41.38041766305988,
            "rbacGroupName": "GroupOne"
        },
        {
            "time": "2019-12-03T09:51:28.2143399Z",
            "score": 37.403726933165366,
            "rbacGroupName": "GroupTwo"
        }
        ...
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="9b4d8-140">관련 항목</span><span class="sxs-lookup"><span data-stu-id="9b4d8-140">Related topics</span></span>

- [<span data-ttu-id="9b4d8-141">위험 기반 위협 & 관리</span><span class="sxs-lookup"><span data-stu-id="9b4d8-141">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="9b4d8-142">위협 & 노출 점수</span><span class="sxs-lookup"><span data-stu-id="9b4d8-142">Threat & Vulnerability exposure score</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-exposure-score)
