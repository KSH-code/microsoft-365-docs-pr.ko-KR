---
title: 노출 점수 가져오기
description: 조직 노출 점수를 검색합니다.
keywords: api, 그래프 api, 지원되는 api, get, 노출 점수, 조직 노출 점수
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.openlocfilehash: 071b0e7597d334fe06d5045e06a5c4d82dd65609
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845393"
---
# <a name="get-exposure-score"></a><span data-ttu-id="438c8-104">노출 점수 가져오기</span><span class="sxs-lookup"><span data-stu-id="438c8-104">Get exposure score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="438c8-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="438c8-105">**Applies to:**</span></span>
- [<span data-ttu-id="438c8-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="438c8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="438c8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="438c8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="438c8-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="438c8-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="438c8-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="438c8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="438c8-110">조직 노출 점수를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="438c8-110">Retrieves the organizational exposure score.</span></span>

## <a name="permissions"></a><span data-ttu-id="438c8-111">사용 권한</span><span class="sxs-lookup"><span data-stu-id="438c8-111">Permissions</span></span>

<span data-ttu-id="438c8-112">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="438c8-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="438c8-113">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="438c8-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="438c8-114">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="438c8-114">Permission type</span></span> | <span data-ttu-id="438c8-115">사용 권한</span><span class="sxs-lookup"><span data-stu-id="438c8-115">Permission</span></span> | <span data-ttu-id="438c8-116">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="438c8-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="438c8-117">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="438c8-117">Application</span></span> | <span data-ttu-id="438c8-118">Score.Read.All</span><span class="sxs-lookup"><span data-stu-id="438c8-118">Score.Read.All</span></span> | <span data-ttu-id="438c8-119">'위협 및 취약성 관리 점수 읽기'</span><span class="sxs-lookup"><span data-stu-id="438c8-119">'Read Threat and Vulnerability Management score'</span></span>
<span data-ttu-id="438c8-120">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="438c8-120">Delegated (work or school account)</span></span> | <span data-ttu-id="438c8-121">Score.Read</span><span class="sxs-lookup"><span data-stu-id="438c8-121">Score.Read</span></span> | <span data-ttu-id="438c8-122">'위협 및 취약성 관리 점수 읽기'</span><span class="sxs-lookup"><span data-stu-id="438c8-122">'Read Threat and Vulnerability Management score'</span></span>

## <a name="http-request"></a><span data-ttu-id="438c8-123">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="438c8-123">HTTP request</span></span>

```
GET /api/exposureScore
```

## <a name="request-headers"></a><span data-ttu-id="438c8-124">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="438c8-124">Request headers</span></span>

<span data-ttu-id="438c8-125">이름</span><span class="sxs-lookup"><span data-stu-id="438c8-125">Name</span></span> | <span data-ttu-id="438c8-126">유형</span><span class="sxs-lookup"><span data-stu-id="438c8-126">Type</span></span> | <span data-ttu-id="438c8-127">설명</span><span class="sxs-lookup"><span data-stu-id="438c8-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="438c8-128">권한 부여</span><span class="sxs-lookup"><span data-stu-id="438c8-128">Authorization</span></span> | <span data-ttu-id="438c8-129">String</span><span class="sxs-lookup"><span data-stu-id="438c8-129">String</span></span> | <span data-ttu-id="438c8-130">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="438c8-130">Bearer {token}.</span></span> <span data-ttu-id="438c8-131">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="438c8-131">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="438c8-132">요청 본문</span><span class="sxs-lookup"><span data-stu-id="438c8-132">Request body</span></span>

<span data-ttu-id="438c8-133">비어 있음</span><span class="sxs-lookup"><span data-stu-id="438c8-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="438c8-134">응답</span><span class="sxs-lookup"><span data-stu-id="438c8-134">Response</span></span>

<span data-ttu-id="438c8-135">성공하면 이 메서드는 응답 본문의 노출 데이터를 사용하여 200 OK를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="438c8-135">If successful, this method returns 200 OK, with the exposure data in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="438c8-136">예시</span><span class="sxs-lookup"><span data-stu-id="438c8-136">Example</span></span>

### <a name="request"></a><span data-ttu-id="438c8-137">요청</span><span class="sxs-lookup"><span data-stu-id="438c8-137">Request</span></span>

<span data-ttu-id="438c8-138">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="438c8-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/exposureScore
```

### <a name="response"></a><span data-ttu-id="438c8-139">응답</span><span class="sxs-lookup"><span data-stu-id="438c8-139">Response</span></span>

<span data-ttu-id="438c8-140">다음은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="438c8-140">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="438c8-141">여기에 표시된 응답 목록은 표시가 까다로우면 자르기될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="438c8-141">The response list shown here may be truncated for brevity.</span></span> 

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ExposureScore/$entity",
    "time": "2019-12-03T07:23:53.280499Z",
    "score": 33.491554051195706
}

```

## <a name="see-also"></a><span data-ttu-id="438c8-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="438c8-142">See also</span></span>

- [<span data-ttu-id="438c8-143">위험 기반 위협 & 관리</span><span class="sxs-lookup"><span data-stu-id="438c8-143">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="438c8-144">위협 & 노출 점수</span><span class="sxs-lookup"><span data-stu-id="438c8-144">Threat & Vulnerability exposure score</span></span>](/microsoft-365/security/defender-endpoint/tvm-exposure-score)
