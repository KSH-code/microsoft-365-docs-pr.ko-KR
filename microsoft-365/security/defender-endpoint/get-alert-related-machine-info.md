---
title: 경고 관련 컴퓨터 정보 얻기
description: 끝점용 Microsoft Defender를 사용하여 특정 경고와 관련된 모든 장치를 검색합니다.
keywords: api, 그래프 api, 지원되는 api, 경고 정보, 경고 정보, 관련 장치
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: ef10d2bd7193fc7b4a1604658f496ef38ef33555
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772349"
---
# <a name="get-alert-related-machine-information-api"></a><span data-ttu-id="2552b-104">경고 관련 컴퓨터 정보 얻기 API</span><span class="sxs-lookup"><span data-stu-id="2552b-104">Get alert related machine information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="2552b-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="2552b-105">**Applies to:**</span></span>
- [<span data-ttu-id="2552b-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2552b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2552b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2552b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="2552b-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="2552b-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2552b-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="2552b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="2552b-110">API 설명</span><span class="sxs-lookup"><span data-stu-id="2552b-110">API description</span></span>
<span data-ttu-id="2552b-111">특정 [경고와](machine.md) 관련된 장치를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="2552b-111">Retrieves [Device](machine.md) related to a specific alert.</span></span>


## <a name="limitations"></a><span data-ttu-id="2552b-112">제한 사항</span><span class="sxs-lookup"><span data-stu-id="2552b-112">Limitations</span></span>
1. <span data-ttu-id="2552b-113">구성된 보존 기간에 따라 마지막으로 업데이트된 경고에 대해 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2552b-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="2552b-114">이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.</span><span class="sxs-lookup"><span data-stu-id="2552b-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="2552b-115">사용 권한</span><span class="sxs-lookup"><span data-stu-id="2552b-115">Permissions</span></span>
<span data-ttu-id="2552b-116">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2552b-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="2552b-117">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="2552b-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="2552b-118">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="2552b-118">Permission type</span></span> |   <span data-ttu-id="2552b-119">사용 권한</span><span class="sxs-lookup"><span data-stu-id="2552b-119">Permission</span></span>  |   <span data-ttu-id="2552b-120">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="2552b-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="2552b-121">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="2552b-121">Application</span></span> |   <span data-ttu-id="2552b-122">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="2552b-122">Machine.Read.All</span></span> |  <span data-ttu-id="2552b-123">'모든 컴퓨터 정보 읽기'</span><span class="sxs-lookup"><span data-stu-id="2552b-123">'Read all machine information'</span></span>
<span data-ttu-id="2552b-124">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="2552b-124">Application</span></span> |   <span data-ttu-id="2552b-125">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="2552b-125">Machine.ReadWrite.All</span></span> | <span data-ttu-id="2552b-126">'모든 컴퓨터 정보 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="2552b-126">'Read and write all machine information'</span></span>
<span data-ttu-id="2552b-127">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="2552b-127">Delegated (work or school account)</span></span> | <span data-ttu-id="2552b-128">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="2552b-128">Machine.Read</span></span> | <span data-ttu-id="2552b-129">'컴퓨터 정보 읽기'</span><span class="sxs-lookup"><span data-stu-id="2552b-129">'Read machine information'</span></span>
<span data-ttu-id="2552b-130">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="2552b-130">Delegated (work or school account)</span></span> | <span data-ttu-id="2552b-131">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="2552b-131">Machine.ReadWrite</span></span> | <span data-ttu-id="2552b-132">'컴퓨터 정보 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="2552b-132">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="2552b-133">사용자 자격 증명을 사용하여 토큰을 얻을 때:</span><span class="sxs-lookup"><span data-stu-id="2552b-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="2552b-134">사용자에게 최소한 '데이터 보기' 역할 권한이 필요합니다(자세한 내용은 역할 [만들기](user-roles.md) 및 관리 참조).</span><span class="sxs-lookup"><span data-stu-id="2552b-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="2552b-135">사용자는 장치 그룹 설정에 따라 경고와 연결된 장치에 액세스할 수 있습니다(자세한 내용은 장치 그룹 만들기 및 [관리](machine-groups.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="2552b-135">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="2552b-136">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="2552b-136">HTTP request</span></span>

```http
GET /api/alerts/{id}/machine
```

## <a name="request-headers"></a><span data-ttu-id="2552b-137">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="2552b-137">Request headers</span></span>

<span data-ttu-id="2552b-138">이름</span><span class="sxs-lookup"><span data-stu-id="2552b-138">Name</span></span> | <span data-ttu-id="2552b-139">유형</span><span class="sxs-lookup"><span data-stu-id="2552b-139">Type</span></span> | <span data-ttu-id="2552b-140">설명</span><span class="sxs-lookup"><span data-stu-id="2552b-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="2552b-141">권한 부여</span><span class="sxs-lookup"><span data-stu-id="2552b-141">Authorization</span></span> | <span data-ttu-id="2552b-142">String</span><span class="sxs-lookup"><span data-stu-id="2552b-142">String</span></span> | <span data-ttu-id="2552b-143">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="2552b-143">Bearer {token}.</span></span> <span data-ttu-id="2552b-144">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="2552b-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="2552b-145">요청 본문</span><span class="sxs-lookup"><span data-stu-id="2552b-145">Request body</span></span>
<span data-ttu-id="2552b-146">비어 있음</span><span class="sxs-lookup"><span data-stu-id="2552b-146">Empty</span></span>

## <a name="response"></a><span data-ttu-id="2552b-147">응답</span><span class="sxs-lookup"><span data-stu-id="2552b-147">Response</span></span>
<span data-ttu-id="2552b-148">성공적이고 알림 및 장치가 있는 경우 - 200 OK.</span><span class="sxs-lookup"><span data-stu-id="2552b-148">If successful and alert and device exist - 200 OK.</span></span> <span data-ttu-id="2552b-149">알림을 찾을 수 없는 경우 또는 장치를 찾을 수 없는 경우 - 404 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2552b-149">If alert not found or device not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="2552b-150">예시</span><span class="sxs-lookup"><span data-stu-id="2552b-150">Example</span></span>

<span data-ttu-id="2552b-151">**요청**</span><span class="sxs-lookup"><span data-stu-id="2552b-151">**Request**</span></span>

<span data-ttu-id="2552b-152">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="2552b-152">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts/636688558380765161_2136280442/machine
```

<span data-ttu-id="2552b-153">**응답**</span><span class="sxs-lookup"><span data-stu-id="2552b-153">**Response**</span></span>

<span data-ttu-id="2552b-154">다음은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="2552b-154">Here is an example of the response.</span></span>


```json
{
    "id": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
    "computerDnsName": "mymachine1.contoso.com",
    "firstSeen": "2018-08-02T14:55:03.7791856Z",
    "lastSeen": "2021-01-25T07:27:36.052313Z",
    "osPlatform": "Windows10",
    "osProcessor": "x64",
    "version": "1901",
    "lastIpAddress": "10.166.113.46",
    "lastExternalIpAddress": "167.220.203.175",
    "osBuild": 19042,
    "healthStatus": "Active",
    "deviceValue": "Normal",
    "rbacGroupName": "The-A-Team",
    "riskScore": "Low",
    "exposureLevel": "Low",
    "aadDeviceId": "fd2e4d29-7072-4195-aaa5-1af139b78028",
    "machineTags": [
        "Tag1",
        "Tag2"
    ],
    "ipAddresses": [
        {
            "ipAddress": "10.166.113.47",
            "macAddress": "8CEC4B897E73",
            "operationalStatus": "Up"
        },
        {
            "ipAddress": "2a01:110:68:4:59e4:3916:3b3e:4f96",
            "macAddress": "8CEC4B897E73",
            "operationalStatus": "Up"
        }
    ]
}
```
