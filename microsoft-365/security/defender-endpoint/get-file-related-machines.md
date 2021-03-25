---
title: 파일 관련 컴퓨터 다운로드 API
description: 파일 관련 컴퓨터 다운로드 API를 사용하여 끝점용 Microsoft Defender에서 파일 해시와 관련된 컴퓨터 컬렉션을 다운로드하는 방법을 학습합니다.
keywords: api, 그래프 api, 지원되는 api, get, 장치, 해시
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
ms.openlocfilehash: 051bdad362e142446d248e90fad608fe5c0f016f
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166818"
---
# <a name="get-file-related-machines-api"></a><span data-ttu-id="d1e70-104">파일 관련 컴퓨터 다운로드 API</span><span class="sxs-lookup"><span data-stu-id="d1e70-104">Get file-related machines API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d1e70-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="d1e70-105">**Applies to:**</span></span>
- [<span data-ttu-id="d1e70-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d1e70-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d1e70-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d1e70-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d1e70-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="d1e70-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d1e70-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="d1e70-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="d1e70-110">API 설명</span><span class="sxs-lookup"><span data-stu-id="d1e70-110">API description</span></span>
<span data-ttu-id="d1e70-111">지정한 파일 해시와 관련된 [컴퓨터](machine.md) 컬렉션을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="d1e70-111">Retrieves a collection of [Machines](machine.md) related to a given file hash.</span></span>


## <a name="limitations"></a><span data-ttu-id="d1e70-112">제한 사항</span><span class="sxs-lookup"><span data-stu-id="d1e70-112">Limitations</span></span>
1. <span data-ttu-id="d1e70-113">이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.</span><span class="sxs-lookup"><span data-stu-id="d1e70-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="d1e70-114">사용 권한</span><span class="sxs-lookup"><span data-stu-id="d1e70-114">Permissions</span></span>
<span data-ttu-id="d1e70-115">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d1e70-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="d1e70-116">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="d1e70-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="d1e70-117">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="d1e70-117">Permission type</span></span> |   <span data-ttu-id="d1e70-118">사용 권한</span><span class="sxs-lookup"><span data-stu-id="d1e70-118">Permission</span></span>  |   <span data-ttu-id="d1e70-119">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="d1e70-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="d1e70-120">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="d1e70-120">Application</span></span> |   <span data-ttu-id="d1e70-121">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="d1e70-121">Machine.Read.All</span></span> |  <span data-ttu-id="d1e70-122">'모든 컴퓨터 프로필 읽기'</span><span class="sxs-lookup"><span data-stu-id="d1e70-122">'Read all machine profiles'</span></span>
<span data-ttu-id="d1e70-123">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="d1e70-123">Application</span></span> |   <span data-ttu-id="d1e70-124">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="d1e70-124">Machine.ReadWrite.All</span></span> | <span data-ttu-id="d1e70-125">'모든 컴퓨터 정보 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="d1e70-125">'Read and write all machine information'</span></span>
<span data-ttu-id="d1e70-126">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="d1e70-126">Delegated (work or school account)</span></span> | <span data-ttu-id="d1e70-127">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="d1e70-127">Machine.Read</span></span> | <span data-ttu-id="d1e70-128">'컴퓨터 정보 읽기'</span><span class="sxs-lookup"><span data-stu-id="d1e70-128">'Read machine information'</span></span>
<span data-ttu-id="d1e70-129">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="d1e70-129">Delegated (work or school account)</span></span> | <span data-ttu-id="d1e70-130">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="d1e70-130">Machine.ReadWrite</span></span> | <span data-ttu-id="d1e70-131">'컴퓨터 정보 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="d1e70-131">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="d1e70-132">사용자 자격 증명을 사용하여 토큰을 얻을 때:</span><span class="sxs-lookup"><span data-stu-id="d1e70-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="d1e70-133">사용자에게 최소한 '데이터 보기' 역할 권한이 필요합니다(자세한 내용은 역할 [만들기](user-roles.md) 및 관리 참조).</span><span class="sxs-lookup"><span data-stu-id="d1e70-133">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="d1e70-134">응답에는 장치 그룹 설정에 따라 사용자가 액세스할 수 있는 장치만 포함됩니다(자세한 내용은 장치 그룹 [만들기](machine-groups.md) 및 관리 참조).</span><span class="sxs-lookup"><span data-stu-id="d1e70-134">Response will include only devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="d1e70-135">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="d1e70-135">HTTP request</span></span>
```
GET /api/files/{id}/machines
```

## <a name="request-headers"></a><span data-ttu-id="d1e70-136">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="d1e70-136">Request headers</span></span>

<span data-ttu-id="d1e70-137">이름</span><span class="sxs-lookup"><span data-stu-id="d1e70-137">Name</span></span> | <span data-ttu-id="d1e70-138">유형</span><span class="sxs-lookup"><span data-stu-id="d1e70-138">Type</span></span> | <span data-ttu-id="d1e70-139">설명</span><span class="sxs-lookup"><span data-stu-id="d1e70-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="d1e70-140">권한 부여</span><span class="sxs-lookup"><span data-stu-id="d1e70-140">Authorization</span></span> | <span data-ttu-id="d1e70-141">문자열</span><span class="sxs-lookup"><span data-stu-id="d1e70-141">String</span></span> | <span data-ttu-id="d1e70-142">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="d1e70-142">Bearer {token}.</span></span> <span data-ttu-id="d1e70-143">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="d1e70-143">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="d1e70-144">요청 본문</span><span class="sxs-lookup"><span data-stu-id="d1e70-144">Request body</span></span>
<span data-ttu-id="d1e70-145">비어 있음</span><span class="sxs-lookup"><span data-stu-id="d1e70-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="d1e70-146">응답</span><span class="sxs-lookup"><span data-stu-id="d1e70-146">Response</span></span>
<span data-ttu-id="d1e70-147">성공 및 파일이 있는 경우 - 본문에 [](machine.md) 컴퓨터 엔터티 목록이 있는 200 OK.</span><span class="sxs-lookup"><span data-stu-id="d1e70-147">If successful and file exists - 200 OK with list of [machine](machine.md) entities in the body.</span></span> <span data-ttu-id="d1e70-148">파일이 없는 경우 - 404 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d1e70-148">If file does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="d1e70-149">예제</span><span class="sxs-lookup"><span data-stu-id="d1e70-149">Example</span></span>

<span data-ttu-id="d1e70-150">**요청**</span><span class="sxs-lookup"><span data-stu-id="d1e70-150">**Request**</span></span>

<span data-ttu-id="d1e70-151">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="d1e70-151">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/files/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/machines
```
