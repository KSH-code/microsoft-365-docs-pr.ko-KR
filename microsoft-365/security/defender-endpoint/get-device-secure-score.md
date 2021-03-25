---
title: 장치 보안 점수 얻기
description: 조직 장치 보안 점수를 검색합니다.
keywords: api, 그래프 api, 지원되는 api, get, alerts, recent
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: levinec
ms.author: ellevin
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 921334c937e3f211b032a5d24d4244d9a6fb3d61
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166885"
---
# <a name="get-device-secure-score"></a><span data-ttu-id="a86ff-104">장치 보안 점수 얻기</span><span class="sxs-lookup"><span data-stu-id="a86ff-104">Get device secure score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a86ff-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="a86ff-105">**Applies to:**</span></span>
- [<span data-ttu-id="a86ff-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a86ff-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a86ff-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a86ff-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="a86ff-108">**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="a86ff-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="a86ff-109">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="a86ff-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a86ff-110">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="a86ff-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="a86ff-111">장치에 [대한 Microsoft 보안 점수를 검색합니다.](tvm-microsoft-secure-score-devices.md)</span><span class="sxs-lookup"><span data-stu-id="a86ff-111">Retrieves your [Microsoft Secure Score for Devices](tvm-microsoft-secure-score-devices.md).</span></span> <span data-ttu-id="a86ff-112">장치에 대한 Microsoft 보안 점수가 높을수록 끝점이 사이버 보안 위협 공격으로부터 더 탄력적입니다.</span><span class="sxs-lookup"><span data-stu-id="a86ff-112">A higher Microsoft Secure Score for Devices means your endpoints are more resilient from cybersecurity threat attacks.</span></span> 

## <a name="permissions"></a><span data-ttu-id="a86ff-113">사용 권한</span><span class="sxs-lookup"><span data-stu-id="a86ff-113">Permissions</span></span>

<span data-ttu-id="a86ff-114">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a86ff-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="a86ff-115">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [Use Microsoft Defender for Endpoint API](apis-intro.md) for details을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="a86ff-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="a86ff-116">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="a86ff-116">Permission type</span></span> |   <span data-ttu-id="a86ff-117">사용 권한</span><span class="sxs-lookup"><span data-stu-id="a86ff-117">Permission</span></span>  |   <span data-ttu-id="a86ff-118">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="a86ff-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="a86ff-119">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="a86ff-119">Application</span></span> |   <span data-ttu-id="a86ff-120">Score.Read.Alll</span><span class="sxs-lookup"><span data-stu-id="a86ff-120">Score.Read.Alll</span></span> |   <span data-ttu-id="a86ff-121">'위협 및 취약성 관리 점수 읽기'</span><span class="sxs-lookup"><span data-stu-id="a86ff-121">'Read Threat and Vulnerability Management score'</span></span>
<span data-ttu-id="a86ff-122">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="a86ff-122">Delegated (work or school account)</span></span> | <span data-ttu-id="a86ff-123">Score.Read</span><span class="sxs-lookup"><span data-stu-id="a86ff-123">Score.Read</span></span> | <span data-ttu-id="a86ff-124">'위협 및 취약성 관리 점수 읽기'</span><span class="sxs-lookup"><span data-stu-id="a86ff-124">'Read Threat and Vulnerability Management score'</span></span>

## <a name="http-request"></a><span data-ttu-id="a86ff-125">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="a86ff-125">HTTP request</span></span>

```
GET /api/configurationScore
```

## <a name="request-headers"></a><span data-ttu-id="a86ff-126">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="a86ff-126">Request headers</span></span>

<span data-ttu-id="a86ff-127">이름</span><span class="sxs-lookup"><span data-stu-id="a86ff-127">Name</span></span> | <span data-ttu-id="a86ff-128">유형</span><span class="sxs-lookup"><span data-stu-id="a86ff-128">Type</span></span> | <span data-ttu-id="a86ff-129">설명</span><span class="sxs-lookup"><span data-stu-id="a86ff-129">Description</span></span>
:---|:---|:---
<span data-ttu-id="a86ff-130">권한 부여</span><span class="sxs-lookup"><span data-stu-id="a86ff-130">Authorization</span></span> | <span data-ttu-id="a86ff-131">문자열</span><span class="sxs-lookup"><span data-stu-id="a86ff-131">String</span></span> | <span data-ttu-id="a86ff-132">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="a86ff-132">Bearer {token}.</span></span> <span data-ttu-id="a86ff-133">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="a86ff-133">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="a86ff-134">요청 본문</span><span class="sxs-lookup"><span data-stu-id="a86ff-134">Request body</span></span>

<span data-ttu-id="a86ff-135">비어 있음</span><span class="sxs-lookup"><span data-stu-id="a86ff-135">Empty</span></span>

## <a name="response"></a><span data-ttu-id="a86ff-136">응답</span><span class="sxs-lookup"><span data-stu-id="a86ff-136">Response</span></span>

<span data-ttu-id="a86ff-137">성공하면 이 메서드는 응답 본문에 장치 보안 점수 데이터를 사용하여 200 OK를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a86ff-137">If successful, this method returns 200 OK, with the device secure score data in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="a86ff-138">예제</span><span class="sxs-lookup"><span data-stu-id="a86ff-138">Example</span></span>

### <a name="request"></a><span data-ttu-id="a86ff-139">요청</span><span class="sxs-lookup"><span data-stu-id="a86ff-139">Request</span></span>

<span data-ttu-id="a86ff-140">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="a86ff-140">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/configurationScore
```

### <a name="response"></a><span data-ttu-id="a86ff-141">응답</span><span class="sxs-lookup"><span data-stu-id="a86ff-141">Response</span></span>

<span data-ttu-id="a86ff-142">다음은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="a86ff-142">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="a86ff-143">여기에 표시된 응답 목록은 표시가 까다로우면 자르기될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a86ff-143">The response list shown here may be truncated for brevity.</span></span> 

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ConfigurationScore/$entity",
    "time": "2019-12-03T09:15:58.1665846Z",
    "score": 340
}
```

## <a name="see-also"></a><span data-ttu-id="a86ff-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a86ff-144">See also</span></span>

- [<span data-ttu-id="a86ff-145">끝점용 Microsoft Defender를 사용하여 OData 쿼리</span><span class="sxs-lookup"><span data-stu-id="a86ff-145">OData queries with Microsoft Defender for Endpoint</span></span>](exposed-apis-odata-samples.md)
