---
title: 경고 관련 IP 정보 얻기
description: 끝점용 Microsoft Defender를 사용하여 특정 경고와 관련된 모든 IP를 검색합니다.
keywords: api, 그래프 api, 지원되는 api, 경고 정보, 경고 정보, 관련 ip
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
ms.openlocfilehash: 970f82038bd7feb4f0c568ed13b285f75bf1ab19
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167058"
---
# <a name="get-alert-related-ips-information-api"></a><span data-ttu-id="95497-104">경고 관련 IPS 정보 얻기 API</span><span class="sxs-lookup"><span data-stu-id="95497-104">Get alert related IPs information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="95497-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="95497-105">**Applies to:**</span></span>
- [<span data-ttu-id="95497-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="95497-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="95497-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="95497-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="95497-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="95497-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="95497-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="95497-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="95497-110">API 설명</span><span class="sxs-lookup"><span data-stu-id="95497-110">API description</span></span>
<span data-ttu-id="95497-111">특정 경고와 관련된 모든 IP를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="95497-111">Retrieves all IPs related to a specific alert.</span></span>


## <a name="limitations"></a><span data-ttu-id="95497-112">제한 사항</span><span class="sxs-lookup"><span data-stu-id="95497-112">Limitations</span></span>
1. <span data-ttu-id="95497-113">구성된 보존 기간에 따라 마지막으로 업데이트된 경고에 대해 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95497-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="95497-114">이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.</span><span class="sxs-lookup"><span data-stu-id="95497-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="95497-115">사용 권한</span><span class="sxs-lookup"><span data-stu-id="95497-115">Permissions</span></span>
<span data-ttu-id="95497-116">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="95497-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="95497-117">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="95497-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="95497-118">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="95497-118">Permission type</span></span> |   <span data-ttu-id="95497-119">사용 권한</span><span class="sxs-lookup"><span data-stu-id="95497-119">Permission</span></span>  |   <span data-ttu-id="95497-120">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="95497-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="95497-121">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="95497-121">Application</span></span> |   <span data-ttu-id="95497-122">Ip.Read.All</span><span class="sxs-lookup"><span data-stu-id="95497-122">Ip.Read.All</span></span> |   <span data-ttu-id="95497-123">'IP 주소 프로필 읽기'</span><span class="sxs-lookup"><span data-stu-id="95497-123">'Read IP address profiles'</span></span>
<span data-ttu-id="95497-124">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="95497-124">Delegated (work or school account)</span></span> | <span data-ttu-id="95497-125">Ip.Read.All</span><span class="sxs-lookup"><span data-stu-id="95497-125">Ip.Read.All</span></span> |  <span data-ttu-id="95497-126">'IP 주소 프로필 읽기'</span><span class="sxs-lookup"><span data-stu-id="95497-126">'Read IP address profiles'</span></span>

>[!Note]
> <span data-ttu-id="95497-127">사용자 자격 증명을 사용하여 토큰을 얻을 때:</span><span class="sxs-lookup"><span data-stu-id="95497-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="95497-128">사용자에게 최소한 '데이터 보기' 역할 권한이 필요합니다(자세한 내용은 역할 [만들기](user-roles.md) 및 관리 참조).</span><span class="sxs-lookup"><span data-stu-id="95497-128">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="95497-129">사용자는 장치 그룹 설정에 따라 경고와 연결된 장치에 액세스할 수 있습니다(자세한 내용은 장치 그룹 만들기 및 [관리](machine-groups.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="95497-129">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="95497-130">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="95497-130">HTTP request</span></span>
```
GET /api/alerts/{id}/ips
```

## <a name="request-headers"></a><span data-ttu-id="95497-131">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="95497-131">Request headers</span></span>

<span data-ttu-id="95497-132">이름</span><span class="sxs-lookup"><span data-stu-id="95497-132">Name</span></span> | <span data-ttu-id="95497-133">유형</span><span class="sxs-lookup"><span data-stu-id="95497-133">Type</span></span> | <span data-ttu-id="95497-134">설명</span><span class="sxs-lookup"><span data-stu-id="95497-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="95497-135">권한 부여</span><span class="sxs-lookup"><span data-stu-id="95497-135">Authorization</span></span> | <span data-ttu-id="95497-136">문자열</span><span class="sxs-lookup"><span data-stu-id="95497-136">String</span></span> | <span data-ttu-id="95497-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="95497-137">Bearer {token}.</span></span> <span data-ttu-id="95497-138">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="95497-138">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="95497-139">요청 본문</span><span class="sxs-lookup"><span data-stu-id="95497-139">Request body</span></span>
<span data-ttu-id="95497-140">비어 있음</span><span class="sxs-lookup"><span data-stu-id="95497-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="95497-141">응답</span><span class="sxs-lookup"><span data-stu-id="95497-141">Response</span></span>
<span data-ttu-id="95497-142">성공 및 알림 및 IP가 있는 경우 - 200 OK.</span><span class="sxs-lookup"><span data-stu-id="95497-142">If successful and alert and an IP exist - 200 OK.</span></span> <span data-ttu-id="95497-143">알림을 찾을 수 없는 경우 - 404 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="95497-143">If alert not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="95497-144">예제</span><span class="sxs-lookup"><span data-stu-id="95497-144">Example</span></span>

<span data-ttu-id="95497-145">**요청**</span><span class="sxs-lookup"><span data-stu-id="95497-145">**Request**</span></span>

<span data-ttu-id="95497-146">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="95497-146">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/alerts/636688558380765161_2136280442/ips
```

<span data-ttu-id="95497-147">**응답**</span><span class="sxs-lookup"><span data-stu-id="95497-147">**Response**</span></span>

<span data-ttu-id="95497-148">다음은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="95497-148">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/$metadata#Ips",    
    "value": [
                {
                    "id": "104.80.104.128"
                },
                {
                    "id": "23.203.232.228   
                }
                ...
    ]
}
 
```
