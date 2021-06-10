---
title: 앱 실행 제한 API
description: 이 API를 사용하여 응용 프로그램 실행 제한과 관련된 호출을 만들 수 있습니다.
keywords: api, 그래프 api, 지원되는 api, 조사 패키지 수집
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
ms.openlocfilehash: 7195e91a3a9b7aef6977c925f2c8689d3e461815
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771576"
---
# <a name="restrict-app-execution-api"></a><span data-ttu-id="25b0d-104">앱 실행 제한 API</span><span class="sxs-lookup"><span data-stu-id="25b0d-104">Restrict app execution API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="25b0d-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="25b0d-105">**Applies to:**</span></span>
- [<span data-ttu-id="25b0d-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="25b0d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="25b0d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="25b0d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="25b0d-108">**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="25b0d-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="25b0d-109">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="25b0d-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="25b0d-110">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="25b0d-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="25b0d-111">API 설명</span><span class="sxs-lookup"><span data-stu-id="25b0d-111">API description</span></span>
<span data-ttu-id="25b0d-112">미리 정의한 집합을 제외한 장치의 모든 응용 프로그램 실행을 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="25b0d-112">Restrict execution of all applications on the device except a predefined set.</span></span>


## <a name="limitations"></a><span data-ttu-id="25b0d-113">제한 사항</span><span class="sxs-lookup"><span data-stu-id="25b0d-113">Limitations</span></span>
1. <span data-ttu-id="25b0d-114">이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.</span><span class="sxs-lookup"><span data-stu-id="25b0d-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="25b0d-115">사용 권한</span><span class="sxs-lookup"><span data-stu-id="25b0d-115">Permissions</span></span>
<span data-ttu-id="25b0d-116">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="25b0d-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="25b0d-117">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="25b0d-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="25b0d-118">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="25b0d-118">Permission type</span></span> |   <span data-ttu-id="25b0d-119">사용 권한</span><span class="sxs-lookup"><span data-stu-id="25b0d-119">Permission</span></span>  |   <span data-ttu-id="25b0d-120">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="25b0d-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="25b0d-121">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="25b0d-121">Application</span></span> |   <span data-ttu-id="25b0d-122">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="25b0d-122">Machine.RestrictExecution</span></span> | <span data-ttu-id="25b0d-123">'코드 실행 제한'</span><span class="sxs-lookup"><span data-stu-id="25b0d-123">'Restrict code execution'</span></span>
<span data-ttu-id="25b0d-124">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="25b0d-124">Delegated (work or school account)</span></span> | <span data-ttu-id="25b0d-125">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="25b0d-125">Machine.RestrictExecution</span></span> | <span data-ttu-id="25b0d-126">'코드 실행 제한'</span><span class="sxs-lookup"><span data-stu-id="25b0d-126">'Restrict code execution'</span></span>

>[!Note]
> <span data-ttu-id="25b0d-127">사용자 자격 증명을 사용하여 토큰을 얻을 때:</span><span class="sxs-lookup"><span data-stu-id="25b0d-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="25b0d-128">사용자에게 최소한 '활성 수정 작업' 역할 권한이 필요합니다(자세한 내용은 역할 [만들기](user-roles.md) 및 관리 참조).</span><span class="sxs-lookup"><span data-stu-id="25b0d-128">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="25b0d-129">사용자는 장치 그룹 설정에 따라 장치에 액세스할 수 있습니다(자세한 내용은 장치 그룹 만들기 및 [관리](machine-groups.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="25b0d-129">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="25b0d-130">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="25b0d-130">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/restrictCodeExecution
```

## <a name="request-headers"></a><span data-ttu-id="25b0d-131">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="25b0d-131">Request headers</span></span>

<span data-ttu-id="25b0d-132">이름</span><span class="sxs-lookup"><span data-stu-id="25b0d-132">Name</span></span> | <span data-ttu-id="25b0d-133">유형</span><span class="sxs-lookup"><span data-stu-id="25b0d-133">Type</span></span> | <span data-ttu-id="25b0d-134">설명</span><span class="sxs-lookup"><span data-stu-id="25b0d-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="25b0d-135">권한 부여</span><span class="sxs-lookup"><span data-stu-id="25b0d-135">Authorization</span></span> | <span data-ttu-id="25b0d-136">String</span><span class="sxs-lookup"><span data-stu-id="25b0d-136">String</span></span> | <span data-ttu-id="25b0d-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="25b0d-137">Bearer {token}.</span></span> <span data-ttu-id="25b0d-138">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="25b0d-138">**Required**.</span></span>
<span data-ttu-id="25b0d-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="25b0d-139">Content-Type</span></span> | <span data-ttu-id="25b0d-140">문자열</span><span class="sxs-lookup"><span data-stu-id="25b0d-140">string</span></span> | <span data-ttu-id="25b0d-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="25b0d-141">application/json.</span></span> <span data-ttu-id="25b0d-142">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="25b0d-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="25b0d-143">요청 본문</span><span class="sxs-lookup"><span data-stu-id="25b0d-143">Request body</span></span>
<span data-ttu-id="25b0d-144">요청 본문에 다음 매개 변수를 사용하여 JSON 개체를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="25b0d-144">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="25b0d-145">매개 변수</span><span class="sxs-lookup"><span data-stu-id="25b0d-145">Parameter</span></span> | <span data-ttu-id="25b0d-146">유형</span><span class="sxs-lookup"><span data-stu-id="25b0d-146">Type</span></span>    | <span data-ttu-id="25b0d-147">설명</span><span class="sxs-lookup"><span data-stu-id="25b0d-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="25b0d-148">Comment</span><span class="sxs-lookup"><span data-stu-id="25b0d-148">Comment</span></span> |   <span data-ttu-id="25b0d-149">String</span><span class="sxs-lookup"><span data-stu-id="25b0d-149">String</span></span> |    <span data-ttu-id="25b0d-150">작업과 연결되는 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="25b0d-150">Comment to associate with the action.</span></span> <span data-ttu-id="25b0d-151">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="25b0d-151">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="25b0d-152">응답</span><span class="sxs-lookup"><span data-stu-id="25b0d-152">Response</span></span>
<span data-ttu-id="25b0d-153">성공하면 이 메서드는 응답 본문에 201 - 생성된 응답 코드 및 [컴퓨터](machineaction.md) 작업을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="25b0d-153">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="25b0d-154">예시</span><span class="sxs-lookup"><span data-stu-id="25b0d-154">Example</span></span>

<span data-ttu-id="25b0d-155">**요청**</span><span class="sxs-lookup"><span data-stu-id="25b0d-155">**Request**</span></span>

<span data-ttu-id="25b0d-156">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="25b0d-156">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/restrictCodeExecution 
```

```json
{
  "Comment": "Restrict code execution due to alert 1234"
}

```

- <span data-ttu-id="25b0d-157">장치에서 코드 실행 제한을 제거하려면 앱 제한 [제거를 참조하세요.](unrestrict-code-execution.md)</span><span class="sxs-lookup"><span data-stu-id="25b0d-157">To remove code execution restriction from a device, see [Remove app restriction](unrestrict-code-execution.md).</span></span>
