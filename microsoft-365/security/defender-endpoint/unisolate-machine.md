---
title: 장치 해제(Isolation API)
description: 이 API를 사용하여 장치를 해제할 때와 관련된 호출을 만들 수 있습니다.
keywords: api, 그래프 api, 지원되는 api, 장치 분리
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
ms.openlocfilehash: 3ed2e7968464320e41e47ad734026bdd9b323ceb
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771276"
---
# <a name="release-device-from-isolation-api"></a><span data-ttu-id="b6d57-104">장치 해제(Isolation API)</span><span class="sxs-lookup"><span data-stu-id="b6d57-104">Release device from isolation API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b6d57-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="b6d57-105">**Applies to:**</span></span> 
- [<span data-ttu-id="b6d57-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b6d57-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="b6d57-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b6d57-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

- <span data-ttu-id="b6d57-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="b6d57-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b6d57-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="b6d57-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="b6d57-110">API 설명</span><span class="sxs-lookup"><span data-stu-id="b6d57-110">API description</span></span>
<span data-ttu-id="b6d57-111">디바이스의 고르지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="b6d57-111">Undo isolation of a device.</span></span>


## <a name="limitations"></a><span data-ttu-id="b6d57-112">제한 사항</span><span class="sxs-lookup"><span data-stu-id="b6d57-112">Limitations</span></span>
1. <span data-ttu-id="b6d57-113">이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.</span><span class="sxs-lookup"><span data-stu-id="b6d57-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="b6d57-114">사용 권한</span><span class="sxs-lookup"><span data-stu-id="b6d57-114">Permissions</span></span>
<span data-ttu-id="b6d57-115">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b6d57-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="b6d57-116">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="b6d57-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="b6d57-117">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="b6d57-117">Permission type</span></span> |   <span data-ttu-id="b6d57-118">사용 권한</span><span class="sxs-lookup"><span data-stu-id="b6d57-118">Permission</span></span>  |   <span data-ttu-id="b6d57-119">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="b6d57-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="b6d57-120">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="b6d57-120">Application</span></span> |   <span data-ttu-id="b6d57-121">Machine.Isolate</span><span class="sxs-lookup"><span data-stu-id="b6d57-121">Machine.Isolate</span></span> |   <span data-ttu-id="b6d57-122">'컴퓨터 격리'</span><span class="sxs-lookup"><span data-stu-id="b6d57-122">'Isolate machine'</span></span>
<span data-ttu-id="b6d57-123">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="b6d57-123">Delegated (work or school account)</span></span> |    <span data-ttu-id="b6d57-124">Machine.Isolate</span><span class="sxs-lookup"><span data-stu-id="b6d57-124">Machine.Isolate</span></span> |   <span data-ttu-id="b6d57-125">'컴퓨터 격리'</span><span class="sxs-lookup"><span data-stu-id="b6d57-125">'Isolate machine'</span></span>

>[!Note]
> <span data-ttu-id="b6d57-126">사용자 자격 증명을 사용하여 토큰을 얻을 때:</span><span class="sxs-lookup"><span data-stu-id="b6d57-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="b6d57-127">사용자에게 최소한 '활성 수정 작업' 역할 권한이 필요합니다(자세한 내용은 역할 [만들기](user-roles.md) 및 관리 참조).</span><span class="sxs-lookup"><span data-stu-id="b6d57-127">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="b6d57-128">사용자는 장치 그룹 설정에 따라 장치에 액세스할 수 있습니다(자세한 내용은 장치 그룹 만들기 및 [관리](machine-groups.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="b6d57-128">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="b6d57-129">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="b6d57-129">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/unisolate
```

## <a name="request-headers"></a><span data-ttu-id="b6d57-130">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="b6d57-130">Request headers</span></span>

<span data-ttu-id="b6d57-131">이름</span><span class="sxs-lookup"><span data-stu-id="b6d57-131">Name</span></span> | <span data-ttu-id="b6d57-132">유형</span><span class="sxs-lookup"><span data-stu-id="b6d57-132">Type</span></span> | <span data-ttu-id="b6d57-133">설명</span><span class="sxs-lookup"><span data-stu-id="b6d57-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="b6d57-134">권한 부여</span><span class="sxs-lookup"><span data-stu-id="b6d57-134">Authorization</span></span> | <span data-ttu-id="b6d57-135">String</span><span class="sxs-lookup"><span data-stu-id="b6d57-135">String</span></span> | <span data-ttu-id="b6d57-136">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="b6d57-136">Bearer {token}.</span></span> <span data-ttu-id="b6d57-137">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="b6d57-137">**Required**.</span></span>
<span data-ttu-id="b6d57-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="b6d57-138">Content-Type</span></span> | <span data-ttu-id="b6d57-139">문자열</span><span class="sxs-lookup"><span data-stu-id="b6d57-139">string</span></span> | <span data-ttu-id="b6d57-140">application/json.</span><span class="sxs-lookup"><span data-stu-id="b6d57-140">application/json.</span></span> <span data-ttu-id="b6d57-141">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="b6d57-141">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="b6d57-142">요청 본문</span><span class="sxs-lookup"><span data-stu-id="b6d57-142">Request body</span></span>
<span data-ttu-id="b6d57-143">요청 본문에 다음 매개 변수를 사용하여 JSON 개체를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b6d57-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="b6d57-144">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b6d57-144">Parameter</span></span> | <span data-ttu-id="b6d57-145">유형</span><span class="sxs-lookup"><span data-stu-id="b6d57-145">Type</span></span>    | <span data-ttu-id="b6d57-146">설명</span><span class="sxs-lookup"><span data-stu-id="b6d57-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="b6d57-147">Comment</span><span class="sxs-lookup"><span data-stu-id="b6d57-147">Comment</span></span> |   <span data-ttu-id="b6d57-148">String</span><span class="sxs-lookup"><span data-stu-id="b6d57-148">String</span></span> |    <span data-ttu-id="b6d57-149">작업과 연결되는 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="b6d57-149">Comment to associate with the action.</span></span> <span data-ttu-id="b6d57-150">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="b6d57-150">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="b6d57-151">응답</span><span class="sxs-lookup"><span data-stu-id="b6d57-151">Response</span></span>
<span data-ttu-id="b6d57-152">성공하면 이 메서드는 응답 본문에 201 - 생성된 응답 코드 및 [컴퓨터](machineaction.md) 작업을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b6d57-152">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="b6d57-153">예시</span><span class="sxs-lookup"><span data-stu-id="b6d57-153">Example</span></span>

<span data-ttu-id="b6d57-154">**요청**</span><span class="sxs-lookup"><span data-stu-id="b6d57-154">**Request**</span></span>

<span data-ttu-id="b6d57-155">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="b6d57-155">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/unisolate 
```

```json
{
  "Comment": "Unisolate machine since it was clean and validated"
}

```


- <span data-ttu-id="b6d57-156">장치를 격리하려면 장치 [격리를 참조하세요.](isolate-machine.md)</span><span class="sxs-lookup"><span data-stu-id="b6d57-156">To isolate a device, see [Isolate device](isolate-machine.md).</span></span>

