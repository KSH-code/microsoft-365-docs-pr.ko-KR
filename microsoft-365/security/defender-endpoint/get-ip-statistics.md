---
title: IP 통계 API를 얻습니다.
description: 끝점용 Microsoft Defender를 사용하여 IP에 대한 최신 통계를 얻습니다.
keywords: api, 그래프 api, 지원되는 api, get, ip, 통계, 보전
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c47a5e58b1888447a4428fad78e71b85cfe79b69
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167185"
---
# <a name="get-ip-statistics-api"></a><span data-ttu-id="2f4df-104">IP 통계 API를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="2f4df-104">Get IP statistics API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2f4df-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="2f4df-105">**Applies to:**</span></span>
- [<span data-ttu-id="2f4df-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2f4df-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2f4df-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2f4df-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2f4df-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="2f4df-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2f4df-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="2f4df-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="2f4df-110">API 설명</span><span class="sxs-lookup"><span data-stu-id="2f4df-110">API description</span></span>
<span data-ttu-id="2f4df-111">지정한 IP에 대한 통계를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="2f4df-111">Retrieves the statistics for the given IP.</span></span>

## <a name="limitations"></a><span data-ttu-id="2f4df-112">제한 사항</span><span class="sxs-lookup"><span data-stu-id="2f4df-112">Limitations</span></span>
1. <span data-ttu-id="2f4df-113">이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.</span><span class="sxs-lookup"><span data-stu-id="2f4df-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="2f4df-114">사용 권한</span><span class="sxs-lookup"><span data-stu-id="2f4df-114">Permissions</span></span>
<span data-ttu-id="2f4df-115">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2f4df-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="2f4df-116">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="2f4df-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="2f4df-117">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="2f4df-117">Permission type</span></span> |   <span data-ttu-id="2f4df-118">사용 권한</span><span class="sxs-lookup"><span data-stu-id="2f4df-118">Permission</span></span>  |   <span data-ttu-id="2f4df-119">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="2f4df-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="2f4df-120">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="2f4df-120">Application</span></span> |   <span data-ttu-id="2f4df-121">Ip.Read.All</span><span class="sxs-lookup"><span data-stu-id="2f4df-121">Ip.Read.All</span></span> |   <span data-ttu-id="2f4df-122">'IP 주소 프로필 읽기'</span><span class="sxs-lookup"><span data-stu-id="2f4df-122">'Read IP address profiles'</span></span>
<span data-ttu-id="2f4df-123">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="2f4df-123">Delegated (work or school account)</span></span> | <span data-ttu-id="2f4df-124">Ip.Read.All</span><span class="sxs-lookup"><span data-stu-id="2f4df-124">Ip.Read.All</span></span> |  <span data-ttu-id="2f4df-125">'IP 주소 프로필 읽기'</span><span class="sxs-lookup"><span data-stu-id="2f4df-125">'Read IP address profiles'</span></span>

>[!NOTE]
> <span data-ttu-id="2f4df-126">사용자 자격 증명을 사용하여 토큰을 얻을 때:</span><span class="sxs-lookup"><span data-stu-id="2f4df-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="2f4df-127">사용자에게 최소한 '데이터 보기' 역할 권한이 필요합니다(자세한 내용은 역할 [만들기](user-roles.md) 및 관리 참조).</span><span class="sxs-lookup"><span data-stu-id="2f4df-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="2f4df-128">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="2f4df-128">HTTP request</span></span>

```http
GET /api/ips/{ip}/stats
```

## <a name="request-headers"></a><span data-ttu-id="2f4df-129">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="2f4df-129">Request headers</span></span>

<span data-ttu-id="2f4df-130">이름</span><span class="sxs-lookup"><span data-stu-id="2f4df-130">Name</span></span> | <span data-ttu-id="2f4df-131">유형</span><span class="sxs-lookup"><span data-stu-id="2f4df-131">Type</span></span> | <span data-ttu-id="2f4df-132">설명</span><span class="sxs-lookup"><span data-stu-id="2f4df-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="2f4df-133">권한 부여</span><span class="sxs-lookup"><span data-stu-id="2f4df-133">Authorization</span></span> | <span data-ttu-id="2f4df-134">문자열</span><span class="sxs-lookup"><span data-stu-id="2f4df-134">String</span></span> | <span data-ttu-id="2f4df-135">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="2f4df-135">Bearer {token}.</span></span> <span data-ttu-id="2f4df-136">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="2f4df-136">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="2f4df-137">요청 URI 매개 변수</span><span class="sxs-lookup"><span data-stu-id="2f4df-137">Request URI parameters</span></span>

<span data-ttu-id="2f4df-138">이름</span><span class="sxs-lookup"><span data-stu-id="2f4df-138">Name</span></span> | <span data-ttu-id="2f4df-139">유형</span><span class="sxs-lookup"><span data-stu-id="2f4df-139">Type</span></span> | <span data-ttu-id="2f4df-140">설명</span><span class="sxs-lookup"><span data-stu-id="2f4df-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="2f4df-141">lookBackHours</span><span class="sxs-lookup"><span data-stu-id="2f4df-141">lookBackHours</span></span> | <span data-ttu-id="2f4df-142">Int32</span><span class="sxs-lookup"><span data-stu-id="2f4df-142">Int32</span></span> | <span data-ttu-id="2f4df-143">통계를 얻기 위해 다시 검색하는 시간을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2f4df-143">Defines the hours we search back to get the statistics.</span></span> <span data-ttu-id="2f4df-144">기본값은 30일입니다.</span><span class="sxs-lookup"><span data-stu-id="2f4df-144">Defaults to 30 days.</span></span> <span data-ttu-id="2f4df-145">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="2f4df-145">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="2f4df-146">요청 본문</span><span class="sxs-lookup"><span data-stu-id="2f4df-146">Request body</span></span>
<span data-ttu-id="2f4df-147">비어 있음</span><span class="sxs-lookup"><span data-stu-id="2f4df-147">Empty</span></span>

## <a name="response"></a><span data-ttu-id="2f4df-148">응답</span><span class="sxs-lookup"><span data-stu-id="2f4df-148">Response</span></span>
<span data-ttu-id="2f4df-149">성공 및 ip가 있는 경우 - 본문에 통계 데이터가 있는 200 OK.</span><span class="sxs-lookup"><span data-stu-id="2f4df-149">If successful and ip exists - 200 OK with statistical data in the body.</span></span> <span data-ttu-id="2f4df-150">IP가 존재하지 않습니다. 404 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2f4df-150">IP do not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="2f4df-151">예제</span><span class="sxs-lookup"><span data-stu-id="2f4df-151">Example</span></span>

<span data-ttu-id="2f4df-152">**요청**</span><span class="sxs-lookup"><span data-stu-id="2f4df-152">**Request**</span></span>

<span data-ttu-id="2f4df-153">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="2f4df-153">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/ips/10.209.67.177/stats?lookBackHours=48
```

<span data-ttu-id="2f4df-154">**응답**</span><span class="sxs-lookup"><span data-stu-id="2f4df-154">**Response**</span></span>

<span data-ttu-id="2f4df-155">다음은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="2f4df-155">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgIPStats",
    "ipAddress": "10.209.67.177",
    "orgPrevalence": "63515",
    "orgFirstSeen": "2017-07-30T13:36:06Z",
    "orgLastSeen": "2017-08-29T13:32:59Z"
}
```


| <span data-ttu-id="2f4df-156">이름</span><span class="sxs-lookup"><span data-stu-id="2f4df-156">Name</span></span> | <span data-ttu-id="2f4df-157">설명</span><span class="sxs-lookup"><span data-stu-id="2f4df-157">Description</span></span> |
| :--- | :---------- |
| <span data-ttu-id="2f4df-158">Org 보전</span><span class="sxs-lookup"><span data-stu-id="2f4df-158">Org prevalence</span></span> | <span data-ttu-id="2f4df-159">이 IP에 대한 네트워크 연결을 연 장치의 고유한 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2f4df-159">the distinct count of devices that opened network connection to this IP.</span></span> |
| <span data-ttu-id="2f4df-160">처음으로 본 Org</span><span class="sxs-lookup"><span data-stu-id="2f4df-160">Org first seen</span></span> | <span data-ttu-id="2f4df-161">조직에서 이 IP에 대한 첫 번째 연결입니다.</span><span class="sxs-lookup"><span data-stu-id="2f4df-161">the first connection for this IP in the organization.</span></span> |
| <span data-ttu-id="2f4df-162">마지막으로 본 Org</span><span class="sxs-lookup"><span data-stu-id="2f4df-162">Org last seen</span></span>  | <span data-ttu-id="2f4df-163">조직에서 이 IP에 대한 마지막 연결입니다.</span><span class="sxs-lookup"><span data-stu-id="2f4df-163">the last connection for this IP in the organization.</span></span> |

> [!NOTE]
> <span data-ttu-id="2f4df-164">이 통계 정보는 지난 30일간의 데이터를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f4df-164">This statistic information is based on data from the past 30 days.</span></span> 
