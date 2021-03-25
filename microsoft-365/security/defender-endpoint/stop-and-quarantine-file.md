---
title: 파일 API 중지 및 검사
description: 장치에서 파일 실행을 중지하고 끝점용 Microsoft Defender에서 파일을 삭제하는 방법을 학습합니다. 예제를 참조합니다.
keywords: api, 그래프 api, 지원되는 api, 파일 중지 및 검사
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
ms.openlocfilehash: 670282f0f87092437bb1f3c6bf7be908e4649042
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199732"
---
# <a name="stop-and-quarantine-file-api"></a><span data-ttu-id="f6136-105">파일 API 중지 및 검사</span><span class="sxs-lookup"><span data-stu-id="f6136-105">Stop and quarantine file API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f6136-106">**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="f6136-106">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="f6136-107">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="f6136-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f6136-108">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="f6136-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="f6136-109">API 설명</span><span class="sxs-lookup"><span data-stu-id="f6136-109">API description</span></span>
<span data-ttu-id="f6136-110">장치에서 파일 실행을 중지하고 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="f6136-110">Stop execution of a file on a device and delete it.</span></span>


## <a name="limitations"></a><span data-ttu-id="f6136-111">제한 사항</span><span class="sxs-lookup"><span data-stu-id="f6136-111">Limitations</span></span>
1. <span data-ttu-id="f6136-112">이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.</span><span class="sxs-lookup"><span data-stu-id="f6136-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="f6136-113">사용 권한</span><span class="sxs-lookup"><span data-stu-id="f6136-113">Permissions</span></span>
<span data-ttu-id="f6136-114">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f6136-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="f6136-115">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="f6136-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="f6136-116">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="f6136-116">Permission type</span></span> |   <span data-ttu-id="f6136-117">사용 권한</span><span class="sxs-lookup"><span data-stu-id="f6136-117">Permission</span></span>  |   <span data-ttu-id="f6136-118">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="f6136-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="f6136-119">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="f6136-119">Application</span></span> |   <span data-ttu-id="f6136-120">Machine.StopAndQuarantine</span><span class="sxs-lookup"><span data-stu-id="f6136-120">Machine.StopAndQuarantine</span></span> | <span data-ttu-id="f6136-121">'중지 및 Quarantine'</span><span class="sxs-lookup"><span data-stu-id="f6136-121">'Stop And Quarantine'</span></span>
<span data-ttu-id="f6136-122">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="f6136-122">Delegated (work or school account)</span></span> | <span data-ttu-id="f6136-123">Machine.StopAndQuarantine</span><span class="sxs-lookup"><span data-stu-id="f6136-123">Machine.StopAndQuarantine</span></span> | <span data-ttu-id="f6136-124">'중지 및 Quarantine'</span><span class="sxs-lookup"><span data-stu-id="f6136-124">'Stop And Quarantine'</span></span>

>[!Note]
> <span data-ttu-id="f6136-125">사용자 자격 증명을 사용하여 토큰을 얻을 때:</span><span class="sxs-lookup"><span data-stu-id="f6136-125">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="f6136-126">사용자에게 최소한 '활성 수정 작업' 역할 권한이 필요합니다(자세한 내용은 역할 [만들기](user-roles.md) 및 관리 참조).</span><span class="sxs-lookup"><span data-stu-id="f6136-126">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="f6136-127">사용자는 장치 그룹 설정에 따라 장치에 액세스할 수 있습니다(자세한 내용은 장치 그룹 만들기 및 [관리](machine-groups.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="f6136-127">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="f6136-128">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="f6136-128">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/StopAndQuarantineFile
```

## <a name="request-headers"></a><span data-ttu-id="f6136-129">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="f6136-129">Request headers</span></span>

<span data-ttu-id="f6136-130">이름</span><span class="sxs-lookup"><span data-stu-id="f6136-130">Name</span></span> | <span data-ttu-id="f6136-131">유형</span><span class="sxs-lookup"><span data-stu-id="f6136-131">Type</span></span> | <span data-ttu-id="f6136-132">설명</span><span class="sxs-lookup"><span data-stu-id="f6136-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="f6136-133">권한 부여</span><span class="sxs-lookup"><span data-stu-id="f6136-133">Authorization</span></span> | <span data-ttu-id="f6136-134">문자열</span><span class="sxs-lookup"><span data-stu-id="f6136-134">String</span></span> | <span data-ttu-id="f6136-135">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="f6136-135">Bearer {token}.</span></span> <span data-ttu-id="f6136-136">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="f6136-136">**Required**.</span></span>
<span data-ttu-id="f6136-137">Content-Type</span><span class="sxs-lookup"><span data-stu-id="f6136-137">Content-Type</span></span> | <span data-ttu-id="f6136-138">문자열</span><span class="sxs-lookup"><span data-stu-id="f6136-138">string</span></span> | <span data-ttu-id="f6136-139">application/json.</span><span class="sxs-lookup"><span data-stu-id="f6136-139">application/json.</span></span> <span data-ttu-id="f6136-140">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="f6136-140">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="f6136-141">요청 본문</span><span class="sxs-lookup"><span data-stu-id="f6136-141">Request body</span></span>
<span data-ttu-id="f6136-142">요청 본문에 다음 매개 변수를 사용하여 JSON 개체를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f6136-142">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="f6136-143">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f6136-143">Parameter</span></span> | <span data-ttu-id="f6136-144">유형</span><span class="sxs-lookup"><span data-stu-id="f6136-144">Type</span></span>    | <span data-ttu-id="f6136-145">설명</span><span class="sxs-lookup"><span data-stu-id="f6136-145">Description</span></span>
:---|:---|:---
<span data-ttu-id="f6136-146">Comment</span><span class="sxs-lookup"><span data-stu-id="f6136-146">Comment</span></span> |   <span data-ttu-id="f6136-147">String</span><span class="sxs-lookup"><span data-stu-id="f6136-147">String</span></span> |    <span data-ttu-id="f6136-148">작업과 연결되는 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="f6136-148">Comment to associate with the action.</span></span> <span data-ttu-id="f6136-149">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="f6136-149">**Required**.</span></span>
<span data-ttu-id="f6136-150">Sha1</span><span class="sxs-lookup"><span data-stu-id="f6136-150">Sha1</span></span> |  <span data-ttu-id="f6136-151">문자열</span><span class="sxs-lookup"><span data-stu-id="f6136-151">String</span></span>   | <span data-ttu-id="f6136-152">디바이스에서 중지하고 검지할 파일의 Sha1입니다.</span><span class="sxs-lookup"><span data-stu-id="f6136-152">Sha1 of the file to stop and quarantine on the device.</span></span> <span data-ttu-id="f6136-153">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="f6136-153">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="f6136-154">응답</span><span class="sxs-lookup"><span data-stu-id="f6136-154">Response</span></span>
<span data-ttu-id="f6136-155">성공하면 이 메서드는 응답 본문에 201 - 생성된 응답 코드 및 [컴퓨터](machineaction.md) 작업을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f6136-155">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="f6136-156">예제</span><span class="sxs-lookup"><span data-stu-id="f6136-156">Example</span></span>

<span data-ttu-id="f6136-157">**요청**</span><span class="sxs-lookup"><span data-stu-id="f6136-157">**Request**</span></span>

<span data-ttu-id="f6136-158">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="f6136-158">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/StopAndQuarantineFile 
```

```json
{
  "Comment": "Stop and quarantine file on machine due to alert 441688558380765161_2136280442",
  "Sha1": "87662bc3d60e4200ceaf7aae249d1c343f4b83c9"
}

```
