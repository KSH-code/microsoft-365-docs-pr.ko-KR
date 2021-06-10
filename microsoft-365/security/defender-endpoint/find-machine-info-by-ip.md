---
title: 내부 IP API로 장치 정보 찾기
description: 이 API를 사용하여 내부 IP로 특정 타임스탬프를 중심으로 장치 항목을 찾는 데 관련된 호출을 만들 수 있습니다.
keywords: ip, api, 그래프 api, 지원되는 api, 장치 찾기, 장치 정보
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: fa1973d1c53048b04c9135a72e55ec4759412b18
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167142"
---
# <a name="find-device-information-by-internal-ip-api"></a><span data-ttu-id="555d9-104">내부 IP API로 장치 정보 찾기</span><span class="sxs-lookup"><span data-stu-id="555d9-104">Find device information by internal IP API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="555d9-105">**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="555d9-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>

- <span data-ttu-id="555d9-106">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="555d9-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="555d9-107">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="555d9-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="555d9-108">내부 IP로 디바이스를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="555d9-108">Find a device by internal IP.</span></span>

>[!NOTE]
><span data-ttu-id="555d9-109">타임스탬프는 지난 30일 이내에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="555d9-109">The timestamp must be within the last 30 days.</span></span>

## <a name="permissions"></a><span data-ttu-id="555d9-110">사용 권한</span><span class="sxs-lookup"><span data-stu-id="555d9-110">Permissions</span></span>
<span data-ttu-id="555d9-111">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="555d9-111">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="555d9-112">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="555d9-112">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="555d9-113">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="555d9-113">Permission type</span></span> | <span data-ttu-id="555d9-114">사용 권한</span><span class="sxs-lookup"><span data-stu-id="555d9-114">Permission</span></span> | <span data-ttu-id="555d9-115">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="555d9-115">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="555d9-116">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="555d9-116">Application</span></span> | <span data-ttu-id="555d9-117">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="555d9-117">Machine.Read.All</span></span> | <span data-ttu-id="555d9-118">'모든 컴퓨터 프로필 읽기'</span><span class="sxs-lookup"><span data-stu-id="555d9-118">'Read all machine profiles'</span></span>
<span data-ttu-id="555d9-119">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="555d9-119">Application</span></span> | <span data-ttu-id="555d9-120">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="555d9-120">Machine.ReadWrite.All</span></span> | <span data-ttu-id="555d9-121">'모든 컴퓨터 정보 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="555d9-121">'Read and write all machine information'</span></span>

## <a name="http-request"></a><span data-ttu-id="555d9-122">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="555d9-122">HTTP request</span></span>
```
GET /api/machines/find(timestamp={time},key={IP})
```

## <a name="request-headers"></a><span data-ttu-id="555d9-123">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="555d9-123">Request headers</span></span>

<span data-ttu-id="555d9-124">이름</span><span class="sxs-lookup"><span data-stu-id="555d9-124">Name</span></span> | <span data-ttu-id="555d9-125">유형</span><span class="sxs-lookup"><span data-stu-id="555d9-125">Type</span></span> | <span data-ttu-id="555d9-126">설명</span><span class="sxs-lookup"><span data-stu-id="555d9-126">Description</span></span>
:---|:---|:---
<span data-ttu-id="555d9-127">권한 부여</span><span class="sxs-lookup"><span data-stu-id="555d9-127">Authorization</span></span> | <span data-ttu-id="555d9-128">String</span><span class="sxs-lookup"><span data-stu-id="555d9-128">String</span></span> | <span data-ttu-id="555d9-129">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="555d9-129">Bearer {token}.</span></span> <span data-ttu-id="555d9-130">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="555d9-130">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="555d9-131">요청 본문</span><span class="sxs-lookup"><span data-stu-id="555d9-131">Request body</span></span>
<span data-ttu-id="555d9-132">비어 있음</span><span class="sxs-lookup"><span data-stu-id="555d9-132">Empty</span></span>

## <a name="response"></a><span data-ttu-id="555d9-133">응답</span><span class="sxs-lookup"><span data-stu-id="555d9-133">Response</span></span>
<span data-ttu-id="555d9-134">성공적이고 컴퓨터의 경우 - 200 OK.</span><span class="sxs-lookup"><span data-stu-id="555d9-134">If successful and machine exists - 200 OK.</span></span>
<span data-ttu-id="555d9-135">찾을 수 있는 컴퓨터가 없는 경우 - 404 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="555d9-135">If no machine found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="555d9-136">예시</span><span class="sxs-lookup"><span data-stu-id="555d9-136">Example</span></span>

<span data-ttu-id="555d9-137">**요청**</span><span class="sxs-lookup"><span data-stu-id="555d9-137">**Request**</span></span>

<span data-ttu-id="555d9-138">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="555d9-138">Here is an example of the request.</span></span>

```
GET https://graph.microsoft.com/testwdatppreview/machines/find(timestamp=2018-06-19T10:00:00Z,key='10.166.93.61')
Content-type: application/json
```

<span data-ttu-id="555d9-139">**응답**</span><span class="sxs-lookup"><span data-stu-id="555d9-139">**Response**</span></span>

<span data-ttu-id="555d9-140">다음은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="555d9-140">Here is an example of the response.</span></span>

<span data-ttu-id="555d9-141">응답은 타임스탬프 이전 및 이후 16분 이내에 이 IP 주소를 보고한 모든 장치의 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="555d9-141">The response will return a list of all devices that reported this IP address within sixteen minutes prior and after the timestamp.</span></span> 

```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://graph.microsoft.com/testwdatppreview/$metadata#Machines",
    "value": [
        {
            "id": "04c99d46599f078f1c3da3783cf5b95f01ac61bb",
            "computerDnsName": "",
            "firstSeen": "2017-07-06T01:25:04.9480498Z",
            "osPlatform": "Windows10",
…
}
```
