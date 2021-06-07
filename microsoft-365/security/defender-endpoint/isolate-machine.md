---
title: 컴퓨터 격리 API
description: 컴퓨터 격리 API를 사용하여 디바이스가 끝점용 Microsoft Defender의 외부 네트워크에 액세스하지 못하게 격리하는 방법을 학습합니다.
keywords: api, 그래프 api, 지원되는 api, 장치 격리
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
ms.openlocfilehash: 9f3313a08b072f4fb2f699148ab801207e56fc09
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772118"
---
# <a name="isolate-machine-api"></a><span data-ttu-id="8ad09-104">컴퓨터 격리 API</span><span class="sxs-lookup"><span data-stu-id="8ad09-104">Isolate machine API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="8ad09-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="8ad09-105">**Applies to:**</span></span>
- [<span data-ttu-id="8ad09-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8ad09-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8ad09-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8ad09-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="8ad09-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="8ad09-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8ad09-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="8ad09-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="8ad09-110">API 설명</span><span class="sxs-lookup"><span data-stu-id="8ad09-110">API description</span></span>
<span data-ttu-id="8ad09-111">장치가 외부 네트워크에 액세스하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ad09-111">Isolates a device from accessing external network.</span></span>


## <a name="limitations"></a><span data-ttu-id="8ad09-112">제한 사항</span><span class="sxs-lookup"><span data-stu-id="8ad09-112">Limitations</span></span>
1. <span data-ttu-id="8ad09-113">이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.</span><span class="sxs-lookup"><span data-stu-id="8ad09-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="8ad09-114">사용 권한</span><span class="sxs-lookup"><span data-stu-id="8ad09-114">Permissions</span></span>
<span data-ttu-id="8ad09-115">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8ad09-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="8ad09-116">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="8ad09-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="8ad09-117">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="8ad09-117">Permission type</span></span> |   <span data-ttu-id="8ad09-118">사용 권한</span><span class="sxs-lookup"><span data-stu-id="8ad09-118">Permission</span></span>  |   <span data-ttu-id="8ad09-119">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="8ad09-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="8ad09-120">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="8ad09-120">Application</span></span> |   <span data-ttu-id="8ad09-121">Machine.Isolate</span><span class="sxs-lookup"><span data-stu-id="8ad09-121">Machine.Isolate</span></span> |   <span data-ttu-id="8ad09-122">'컴퓨터 격리'</span><span class="sxs-lookup"><span data-stu-id="8ad09-122">'Isolate machine'</span></span>
<span data-ttu-id="8ad09-123">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="8ad09-123">Delegated (work or school account)</span></span> | <span data-ttu-id="8ad09-124">Machine.Isolate</span><span class="sxs-lookup"><span data-stu-id="8ad09-124">Machine.Isolate</span></span> |  <span data-ttu-id="8ad09-125">'컴퓨터 격리'</span><span class="sxs-lookup"><span data-stu-id="8ad09-125">'Isolate machine'</span></span>

>[!Note]
> <span data-ttu-id="8ad09-126">사용자 자격 증명을 사용하여 토큰을 얻을 때:</span><span class="sxs-lookup"><span data-stu-id="8ad09-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="8ad09-127">사용자에게 최소한 '활성 수정 작업' 역할 권한이 필요합니다(자세한 내용은 역할 [만들기](user-roles.md) 및 관리 참조).</span><span class="sxs-lookup"><span data-stu-id="8ad09-127">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="8ad09-128">사용자는 장치 그룹 설정에 따라 장치에 액세스할 수 있습니다(자세한 내용은 장치 그룹 만들기 및 [관리](machine-groups.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="8ad09-128">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>


## <a name="http-request"></a><span data-ttu-id="8ad09-129">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="8ad09-129">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/isolate
```

## <a name="request-headers"></a><span data-ttu-id="8ad09-130">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="8ad09-130">Request headers</span></span>

<span data-ttu-id="8ad09-131">이름</span><span class="sxs-lookup"><span data-stu-id="8ad09-131">Name</span></span> | <span data-ttu-id="8ad09-132">유형</span><span class="sxs-lookup"><span data-stu-id="8ad09-132">Type</span></span> | <span data-ttu-id="8ad09-133">설명</span><span class="sxs-lookup"><span data-stu-id="8ad09-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="8ad09-134">권한 부여</span><span class="sxs-lookup"><span data-stu-id="8ad09-134">Authorization</span></span> | <span data-ttu-id="8ad09-135">String</span><span class="sxs-lookup"><span data-stu-id="8ad09-135">String</span></span> | <span data-ttu-id="8ad09-136">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="8ad09-136">Bearer {token}.</span></span> <span data-ttu-id="8ad09-137">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="8ad09-137">**Required**.</span></span>
<span data-ttu-id="8ad09-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="8ad09-138">Content-Type</span></span> | <span data-ttu-id="8ad09-139">문자열</span><span class="sxs-lookup"><span data-stu-id="8ad09-139">string</span></span> | <span data-ttu-id="8ad09-140">application/json.</span><span class="sxs-lookup"><span data-stu-id="8ad09-140">application/json.</span></span> <span data-ttu-id="8ad09-141">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="8ad09-141">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="8ad09-142">요청 본문</span><span class="sxs-lookup"><span data-stu-id="8ad09-142">Request body</span></span>
<span data-ttu-id="8ad09-143">요청 본문에 다음 매개 변수를 사용하여 JSON 개체를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8ad09-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="8ad09-144">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8ad09-144">Parameter</span></span> | <span data-ttu-id="8ad09-145">유형</span><span class="sxs-lookup"><span data-stu-id="8ad09-145">Type</span></span>    | <span data-ttu-id="8ad09-146">설명</span><span class="sxs-lookup"><span data-stu-id="8ad09-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="8ad09-147">Comment</span><span class="sxs-lookup"><span data-stu-id="8ad09-147">Comment</span></span> |   <span data-ttu-id="8ad09-148">String</span><span class="sxs-lookup"><span data-stu-id="8ad09-148">String</span></span> |    <span data-ttu-id="8ad09-149">작업과 연결되는 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="8ad09-149">Comment to associate with the action.</span></span> <span data-ttu-id="8ad09-150">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="8ad09-150">**Required**.</span></span>
<span data-ttu-id="8ad09-151">IsolationType</span><span class="sxs-lookup"><span data-stu-id="8ad09-151">IsolationType</span></span>   | <span data-ttu-id="8ad09-152">String</span><span class="sxs-lookup"><span data-stu-id="8ad09-152">String</span></span> |  <span data-ttu-id="8ad09-153">Olation의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="8ad09-153">Type of the isolation.</span></span> <span data-ttu-id="8ad09-154">허용되는 값은 '전체' 또는 '선택적'입니다.</span><span class="sxs-lookup"><span data-stu-id="8ad09-154">Allowed values are: 'Full' or 'Selective'.</span></span>

<span data-ttu-id="8ad09-155">**IsolationType은** 수행할 단리 유형을 제어하며 다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ad09-155">**IsolationType** controls the type of isolation to perform and can be one of the following:</span></span>
- <span data-ttu-id="8ad09-156">전체 – 전체 고리</span><span class="sxs-lookup"><span data-stu-id="8ad09-156">Full – Full isolation</span></span>
- <span data-ttu-id="8ad09-157">선택적 – 제한된 응용 프로그램 집합만 네트워크에 [](respond-machine-alerts.md#isolate-devices-from-the-network) 액세스하지 못하도록 제한합니다(자세한 내용은 네트워크에서 장치 격리 참조).</span><span class="sxs-lookup"><span data-stu-id="8ad09-157">Selective – Restrict only limited set of applications from accessing the network (see [Isolate devices from the network](respond-machine-alerts.md#isolate-devices-from-the-network) for more details)</span></span>


## <a name="response"></a><span data-ttu-id="8ad09-158">응답</span><span class="sxs-lookup"><span data-stu-id="8ad09-158">Response</span></span>
<span data-ttu-id="8ad09-159">성공하면 이 메서드는 응답 본문에 201 - 생성된 응답 코드 및 [컴퓨터](machineaction.md) 작업을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8ad09-159">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="8ad09-160">예시</span><span class="sxs-lookup"><span data-stu-id="8ad09-160">Example</span></span>

<span data-ttu-id="8ad09-161">**요청**</span><span class="sxs-lookup"><span data-stu-id="8ad09-161">**Request**</span></span>

<span data-ttu-id="8ad09-162">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="8ad09-162">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/isolate
```

```json
{
  "Comment": "Isolate machine due to alert 1234",
  "IsolationType": "Full" 
}
```

- <span data-ttu-id="8ad09-163">장치를 고리에서 해제하려면 장치 해제를 [참조하세요.](unisolate-machine.md)</span><span class="sxs-lookup"><span data-stu-id="8ad09-163">To release a device from isolation, see [Release device from isolation](unisolate-machine.md).</span></span>
