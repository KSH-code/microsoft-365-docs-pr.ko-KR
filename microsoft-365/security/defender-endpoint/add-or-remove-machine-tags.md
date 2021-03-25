---
title: 컴퓨터 태그 API 추가 또는 제거
description: 컴퓨터 태그 추가 또는 제거 API를 사용하여 끝점용 Microsoft Defender에서 컴퓨터의 태그를 추가하거나 제거하는 방법을 학습합니다.
keywords: api, 그래프 api, 지원되는 api, 태그, 컴퓨터 태그
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
ms.openlocfilehash: 98dd513cc66683ff1b95f66d6d7b89916ce54bab
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199780"
---
# <a name="add-or-remove-machine-tags-api"></a><span data-ttu-id="518af-104">컴퓨터 태그 API 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="518af-104">Add or Remove Machine Tags API</span></span>

<span data-ttu-id="518af-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="518af-105">**Applies to:**</span></span>

- [<span data-ttu-id="518af-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="518af-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

> <span data-ttu-id="518af-107">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="518af-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="518af-108">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="518af-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="518af-109">API 설명</span><span class="sxs-lookup"><span data-stu-id="518af-109">API description</span></span>

<span data-ttu-id="518af-110">특정 Machine 에 태그를 추가하거나 [제거합니다.](machine.md)</span><span class="sxs-lookup"><span data-stu-id="518af-110">Adds or remove tag to a specific [Machine](machine.md).</span></span>

## <a name="limitations"></a><span data-ttu-id="518af-111">제한 사항</span><span class="sxs-lookup"><span data-stu-id="518af-111">Limitations</span></span>

1. <span data-ttu-id="518af-112">구성된 보존 기간에 따라 마지막으로 본 컴퓨터를 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="518af-112">You can post on machines last seen according to your configured retention period.</span></span>

2. <span data-ttu-id="518af-113">이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.</span><span class="sxs-lookup"><span data-stu-id="518af-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="518af-114">사용 권한</span><span class="sxs-lookup"><span data-stu-id="518af-114">Permissions</span></span>

<span data-ttu-id="518af-115">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="518af-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="518af-116">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 끝점 API에 [Defender 사용을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="518af-116">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="518af-117">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="518af-117">Permission type</span></span> |    <span data-ttu-id="518af-118">사용 권한</span><span class="sxs-lookup"><span data-stu-id="518af-118">Permission</span></span>    |    <span data-ttu-id="518af-119">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="518af-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="518af-120">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="518af-120">Application</span></span> |    <span data-ttu-id="518af-121">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="518af-121">Machine.ReadWrite.All</span></span> |    <span data-ttu-id="518af-122">'모든 컴퓨터 정보 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="518af-122">'Read and write all machine information'</span></span>
<span data-ttu-id="518af-123">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="518af-123">Delegated (work or school account)</span></span> | <span data-ttu-id="518af-124">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="518af-124">Machine.ReadWrite</span></span> | <span data-ttu-id="518af-125">'컴퓨터 정보 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="518af-125">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="518af-126">사용자 자격 증명을 사용하여 토큰을 얻을 때:</span><span class="sxs-lookup"><span data-stu-id="518af-126">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="518af-127">사용자에게 최소한 '보안 설정 관리'의 역할 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="518af-127">The user needs to have at least the following role permission: 'Manage security setting'.</span></span> <span data-ttu-id="518af-128">자세한 내용은 [역할 만들기](user-roles.md) 및 관리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="518af-128">For more  (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="518af-129">사용자는 컴퓨터 그룹 설정에 따라 컴퓨터 액세스 권한이 필요합니다(자세한 내용은 컴퓨터 그룹 만들기 및 [관리](machine-groups.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="518af-129">User needs to have access to the machine, based on machine group settings (See [Create and manage machine groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="518af-130">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="518af-130">HTTP request</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/{id}/tags
```

## <a name="request-headers"></a><span data-ttu-id="518af-131">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="518af-131">Request headers</span></span>

<span data-ttu-id="518af-132">이름</span><span class="sxs-lookup"><span data-stu-id="518af-132">Name</span></span> | <span data-ttu-id="518af-133">유형</span><span class="sxs-lookup"><span data-stu-id="518af-133">Type</span></span> | <span data-ttu-id="518af-134">설명</span><span class="sxs-lookup"><span data-stu-id="518af-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="518af-135">권한 부여</span><span class="sxs-lookup"><span data-stu-id="518af-135">Authorization</span></span> | <span data-ttu-id="518af-136">문자열</span><span class="sxs-lookup"><span data-stu-id="518af-136">String</span></span> | <span data-ttu-id="518af-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="518af-137">Bearer {token}.</span></span> <span data-ttu-id="518af-138">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="518af-138">**Required**.</span></span>
<span data-ttu-id="518af-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="518af-139">Content-Type</span></span> | <span data-ttu-id="518af-140">문자열</span><span class="sxs-lookup"><span data-stu-id="518af-140">string</span></span> | <span data-ttu-id="518af-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="518af-141">application/json.</span></span> <span data-ttu-id="518af-142">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="518af-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="518af-143">요청 본문</span><span class="sxs-lookup"><span data-stu-id="518af-143">Request body</span></span>

<span data-ttu-id="518af-144">요청 본문에 다음 매개 변수를 사용하여 JSON 개체를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="518af-144">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="518af-145">매개 변수</span><span class="sxs-lookup"><span data-stu-id="518af-145">Parameter</span></span> |    <span data-ttu-id="518af-146">유형</span><span class="sxs-lookup"><span data-stu-id="518af-146">Type</span></span>    | <span data-ttu-id="518af-147">설명</span><span class="sxs-lookup"><span data-stu-id="518af-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="518af-148">값</span><span class="sxs-lookup"><span data-stu-id="518af-148">Value</span></span> |    <span data-ttu-id="518af-149">문자열</span><span class="sxs-lookup"><span data-stu-id="518af-149">String</span></span> |    <span data-ttu-id="518af-150">태그 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="518af-150">The tag name.</span></span> <span data-ttu-id="518af-151">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="518af-151">**Required**.</span></span>
<span data-ttu-id="518af-152">작업</span><span class="sxs-lookup"><span data-stu-id="518af-152">Action</span></span>    | <span data-ttu-id="518af-153">Enum</span><span class="sxs-lookup"><span data-stu-id="518af-153">Enum</span></span> |    <span data-ttu-id="518af-154">추가 또는 제거.</span><span class="sxs-lookup"><span data-stu-id="518af-154">Add or Remove.</span></span> <span data-ttu-id="518af-155">허용되는 값은 '추가' 또는 '제거'입니다.</span><span class="sxs-lookup"><span data-stu-id="518af-155">Allowed values are: 'Add' or 'Remove'.</span></span> <span data-ttu-id="518af-156">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="518af-156">**Required**.</span></span>


## <a name="response"></a><span data-ttu-id="518af-157">응답</span><span class="sxs-lookup"><span data-stu-id="518af-157">Response</span></span>

<span data-ttu-id="518af-158">성공하면 이 메서드는 응답 본문에 200 - 확인 응답 코드와 업데이트된 Machine을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="518af-158">If successful, this method returns 200 - Ok response code and the updated Machine in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="518af-159">예제</span><span class="sxs-lookup"><span data-stu-id="518af-159">Example</span></span>

<span data-ttu-id="518af-160">**요청**</span><span class="sxs-lookup"><span data-stu-id="518af-160">**Request**</span></span>

<span data-ttu-id="518af-161">다음은 컴퓨터 태그를 추가하는 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="518af-161">Here is an example of a request that adds machine tag.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/tags
```

```json
{
  "Value" : "test Tag 2",
  "Action": "Add"
}
```

- <span data-ttu-id="518af-162">컴퓨터 태그를 제거하려면 요청 본문에서 동작이 '추가' 대신 '제거'로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="518af-162">To remove machine tag, set the Action to 'Remove' instead of 'Add' in the request body.</span></span>
