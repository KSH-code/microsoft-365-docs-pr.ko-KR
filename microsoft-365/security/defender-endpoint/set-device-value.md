---
title: 장치 값 설정 API
description: Microsoft Defender for Endpoint API를 사용하여 디바이스의 값을 지정하는 방법을 학습합니다.
keywords: api, 그래프 api, 지원되는 api, 태그, 컴퓨터 태그
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 76df62243db837ec91819497980ff1de2295e3b6
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498313"
---
# <a name="set-device-value-api"></a><span data-ttu-id="be281-104">장치 값 설정 API</span><span class="sxs-lookup"><span data-stu-id="be281-104">Set device value API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="be281-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="be281-105">**Applies to:**</span></span>
- [<span data-ttu-id="be281-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="be281-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="be281-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="be281-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="be281-108">**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="be281-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="be281-109">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="be281-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="be281-110">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="be281-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="be281-111">API 설명</span><span class="sxs-lookup"><span data-stu-id="be281-111">API description</span></span>

<span data-ttu-id="be281-112">특정 컴퓨터의 장치 값을 [설정합니다.](machine.md)</span><span class="sxs-lookup"><span data-stu-id="be281-112">Set the device value of a specific [Machine](machine.md).</span></span><br>
<span data-ttu-id="be281-113">자세한 [내용은 장치 값](tvm-assign-device-value.md) 할당을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="be281-113">See [assign device values](tvm-assign-device-value.md) for more information.</span></span>

## <a name="limitations"></a><span data-ttu-id="be281-114">제한 사항</span><span class="sxs-lookup"><span data-stu-id="be281-114">Limitations</span></span>

1. <span data-ttu-id="be281-115">구성된 보존 기간에 따라 마지막으로 본 장치에 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be281-115">You can post on devices last seen according to your configured retention period.</span></span>

2. <span data-ttu-id="be281-116">이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.</span><span class="sxs-lookup"><span data-stu-id="be281-116">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="be281-117">사용 권한</span><span class="sxs-lookup"><span data-stu-id="be281-117">Permissions</span></span>

<span data-ttu-id="be281-118">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="be281-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="be281-119">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="be281-119">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="be281-120">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="be281-120">Permission type</span></span> |    <span data-ttu-id="be281-121">사용 권한</span><span class="sxs-lookup"><span data-stu-id="be281-121">Permission</span></span>    |    <span data-ttu-id="be281-122">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="be281-122">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="be281-123">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="be281-123">Application</span></span> |    <span data-ttu-id="be281-124">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="be281-124">Machine.ReadWrite.All</span></span> |    <span data-ttu-id="be281-125">'모든 컴퓨터 정보 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="be281-125">'Read and write all machine information'</span></span>
<span data-ttu-id="be281-126">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="be281-126">Delegated (work or school account)</span></span> | <span data-ttu-id="be281-127">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="be281-127">Machine.ReadWrite</span></span> | <span data-ttu-id="be281-128">'컴퓨터 정보 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="be281-128">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="be281-129">사용자 자격 증명을 사용하여 토큰을 얻을 때:</span><span class="sxs-lookup"><span data-stu-id="be281-129">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="be281-130">사용자에게 최소한 '보안 설정 관리'의 역할 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="be281-130">The user needs to have at least the following role permission: 'Manage security setting'.</span></span> <span data-ttu-id="be281-131">자세한 내용은 [역할 만들기](user-roles.md) 및 관리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="be281-131">For more  (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="be281-132">사용자는 컴퓨터 그룹 설정에 따라 컴퓨터 액세스 권한이 필요합니다(자세한 내용은 컴퓨터 그룹 만들기 및 [관리](machine-groups.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="be281-132">User needs to have access to the machine, based on machine group settings (See [Create and manage machine groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="be281-133">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="be281-133">HTTP request</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/{machineId}/setDeviceValue
```

## <a name="request-headers"></a><span data-ttu-id="be281-134">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="be281-134">Request headers</span></span>

<span data-ttu-id="be281-135">이름</span><span class="sxs-lookup"><span data-stu-id="be281-135">Name</span></span> | <span data-ttu-id="be281-136">유형</span><span class="sxs-lookup"><span data-stu-id="be281-136">Type</span></span> | <span data-ttu-id="be281-137">설명</span><span class="sxs-lookup"><span data-stu-id="be281-137">Description</span></span>
:---|:---|:---
<span data-ttu-id="be281-138">권한 부여</span><span class="sxs-lookup"><span data-stu-id="be281-138">Authorization</span></span> | <span data-ttu-id="be281-139">문자열</span><span class="sxs-lookup"><span data-stu-id="be281-139">String</span></span> | <span data-ttu-id="be281-140">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="be281-140">Bearer {token}.</span></span> <span data-ttu-id="be281-141">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="be281-141">**Required**.</span></span>
<span data-ttu-id="be281-142">Content-Type</span><span class="sxs-lookup"><span data-stu-id="be281-142">Content-Type</span></span> | <span data-ttu-id="be281-143">문자열</span><span class="sxs-lookup"><span data-stu-id="be281-143">string</span></span> | <span data-ttu-id="be281-144">application/json.</span><span class="sxs-lookup"><span data-stu-id="be281-144">application/json.</span></span> <span data-ttu-id="be281-145">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="be281-145">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="be281-146">요청 본문</span><span class="sxs-lookup"><span data-stu-id="be281-146">Request body</span></span>

<span data-ttu-id="be281-147">요청 본문에 다음 매개 변수를 사용하여 JSON 개체를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="be281-147">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="be281-148">매개 변수</span><span class="sxs-lookup"><span data-stu-id="be281-148">Parameter</span></span> |    <span data-ttu-id="be281-149">유형</span><span class="sxs-lookup"><span data-stu-id="be281-149">Type</span></span>    | <span data-ttu-id="be281-150">설명</span><span class="sxs-lookup"><span data-stu-id="be281-150">Description</span></span>
:---|:---|:---
<span data-ttu-id="be281-151">DeviceValue</span><span class="sxs-lookup"><span data-stu-id="be281-151">DeviceValue</span></span> |    <span data-ttu-id="be281-152">Enum</span><span class="sxs-lookup"><span data-stu-id="be281-152">Enum</span></span> |    <span data-ttu-id="be281-153">장치 값입니다.</span><span class="sxs-lookup"><span data-stu-id="be281-153">Device value.</span></span> <span data-ttu-id="be281-154">허용되는 값은 '보통', '낮음' 및 '높음'입니다.</span><span class="sxs-lookup"><span data-stu-id="be281-154">Allowed values are: 'Normal', 'Low' and 'High'.</span></span> <span data-ttu-id="be281-155">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="be281-155">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="be281-156">응답</span><span class="sxs-lookup"><span data-stu-id="be281-156">Response</span></span>

<span data-ttu-id="be281-157">성공하면 이 메서드는 응답 본문에 200 - 확인 응답 코드와 업데이트된 Machine을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="be281-157">If successful, this method returns 200 - Ok response code and the updated Machine in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="be281-158">예제</span><span class="sxs-lookup"><span data-stu-id="be281-158">Example</span></span>

<span data-ttu-id="be281-159">**요청**</span><span class="sxs-lookup"><span data-stu-id="be281-159">**Request**</span></span>

<span data-ttu-id="be281-160">다음은 컴퓨터 태그를 추가하는 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="be281-160">Here is an example of a request that adds machine tag.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/setDeviceValue
```

```json
{
  "DeviceValue" : "High"
}
```
