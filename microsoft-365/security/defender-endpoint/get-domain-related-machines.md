---
title: 도메인 관련 컴퓨터 확인 API
description: 도메인 관련 컴퓨터 다운로드 API를 사용하여 끝점용 Microsoft Defender의 도메인과 통신한 컴퓨터를 다운로드하는 방법을 학습합니다.
keywords: api, 그래프 api, 지원되는 api, get, 도메인, 관련, 장치
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
ms.openlocfilehash: 362e3db0ed89924c58fa9662f7acbbe0c16c37c6
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772224"
---
# <a name="get-domain-related-machines-api"></a><span data-ttu-id="88ec9-104">도메인 관련 컴퓨터 확인 API</span><span class="sxs-lookup"><span data-stu-id="88ec9-104">Get domain related machines API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="88ec9-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="88ec9-105">**Applies to:**</span></span>
- [<span data-ttu-id="88ec9-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="88ec9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="88ec9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="88ec9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="88ec9-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="88ec9-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="88ec9-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="88ec9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="88ec9-110">API 설명</span><span class="sxs-lookup"><span data-stu-id="88ec9-110">API description</span></span>
<span data-ttu-id="88ec9-111">특정 도메인 [주소와](machine.md) 통신한 컴퓨터 컬렉션을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="88ec9-111">Retrieves a collection of [Machines](machine.md) that have communicated to or from a given domain address.</span></span>


## <a name="limitations"></a><span data-ttu-id="88ec9-112">제한 사항</span><span class="sxs-lookup"><span data-stu-id="88ec9-112">Limitations</span></span>
1. <span data-ttu-id="88ec9-113">구성된 보존 기간에 따라 마지막으로 업데이트된 장치에서 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88ec9-113">You can query on devices last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="88ec9-114">이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.</span><span class="sxs-lookup"><span data-stu-id="88ec9-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="88ec9-115">사용 권한</span><span class="sxs-lookup"><span data-stu-id="88ec9-115">Permissions</span></span>
<span data-ttu-id="88ec9-116">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="88ec9-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="88ec9-117">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="88ec9-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="88ec9-118">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="88ec9-118">Permission type</span></span> |   <span data-ttu-id="88ec9-119">사용 권한</span><span class="sxs-lookup"><span data-stu-id="88ec9-119">Permission</span></span>  |   <span data-ttu-id="88ec9-120">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="88ec9-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="88ec9-121">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="88ec9-121">Application</span></span> |   <span data-ttu-id="88ec9-122">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="88ec9-122">Machine.Read.All</span></span> |  <span data-ttu-id="88ec9-123">'모든 컴퓨터 프로필 읽기'</span><span class="sxs-lookup"><span data-stu-id="88ec9-123">'Read all machine profiles'</span></span>
<span data-ttu-id="88ec9-124">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="88ec9-124">Application</span></span> |   <span data-ttu-id="88ec9-125">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="88ec9-125">Machine.ReadWrite.All</span></span> | <span data-ttu-id="88ec9-126">'모든 컴퓨터 정보 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="88ec9-126">'Read and write all machine information'</span></span>
<span data-ttu-id="88ec9-127">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="88ec9-127">Delegated (work or school account)</span></span> | <span data-ttu-id="88ec9-128">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="88ec9-128">Machine.Read</span></span> | <span data-ttu-id="88ec9-129">'컴퓨터 정보 읽기'</span><span class="sxs-lookup"><span data-stu-id="88ec9-129">'Read machine information'</span></span>
<span data-ttu-id="88ec9-130">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="88ec9-130">Delegated (work or school account)</span></span> | <span data-ttu-id="88ec9-131">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="88ec9-131">Machine.ReadWrite</span></span> | <span data-ttu-id="88ec9-132">'컴퓨터 정보 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="88ec9-132">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="88ec9-133">사용자 자격 증명을 사용하여 토큰을 얻을 때:</span><span class="sxs-lookup"><span data-stu-id="88ec9-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="88ec9-134">사용자에게 최소한 '데이터 보기' 역할 권한이 필요합니다(자세한 내용은 역할 [만들기](user-roles.md) 및 관리 참조).</span><span class="sxs-lookup"><span data-stu-id="88ec9-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="88ec9-135">응답에는 장치 그룹 설정에 따라 사용자가 액세스할 수 있는 장치만 포함됩니다(자세한 내용은 장치 그룹 만들기 및 [관리](machine-groups.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="88ec9-135">Response will include only devices that the user can access, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="88ec9-136">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="88ec9-136">HTTP request</span></span>
```http
GET /api/domains/{domain}/machines
```

## <a name="request-headers"></a><span data-ttu-id="88ec9-137">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="88ec9-137">Request headers</span></span>

<span data-ttu-id="88ec9-138">이름</span><span class="sxs-lookup"><span data-stu-id="88ec9-138">Name</span></span> | <span data-ttu-id="88ec9-139">유형</span><span class="sxs-lookup"><span data-stu-id="88ec9-139">Type</span></span> | <span data-ttu-id="88ec9-140">설명</span><span class="sxs-lookup"><span data-stu-id="88ec9-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="88ec9-141">권한 부여</span><span class="sxs-lookup"><span data-stu-id="88ec9-141">Authorization</span></span> | <span data-ttu-id="88ec9-142">String</span><span class="sxs-lookup"><span data-stu-id="88ec9-142">String</span></span> | <span data-ttu-id="88ec9-143">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="88ec9-143">Bearer {token}.</span></span> <span data-ttu-id="88ec9-144">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="88ec9-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="88ec9-145">요청 본문</span><span class="sxs-lookup"><span data-stu-id="88ec9-145">Request body</span></span>
<span data-ttu-id="88ec9-146">비어 있음</span><span class="sxs-lookup"><span data-stu-id="88ec9-146">Empty</span></span>

## <a name="response"></a><span data-ttu-id="88ec9-147">응답</span><span class="sxs-lookup"><span data-stu-id="88ec9-147">Response</span></span>
<span data-ttu-id="88ec9-148">성공 및 도메인이 있는 경우 - 컴퓨터 [](machine.md) 엔터티 목록이 있는 200 OK.</span><span class="sxs-lookup"><span data-stu-id="88ec9-148">If successful and domain exists - 200 OK with list of [machine](machine.md) entities.</span></span> <span data-ttu-id="88ec9-149">도메인이 존재하지 않는 경우 - 404 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="88ec9-149">If domain do not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="88ec9-150">예시</span><span class="sxs-lookup"><span data-stu-id="88ec9-150">Example</span></span>

<span data-ttu-id="88ec9-151">**요청**</span><span class="sxs-lookup"><span data-stu-id="88ec9-151">**Request**</span></span>

<span data-ttu-id="88ec9-152">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="88ec9-152">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/domains/api.securitycenter.microsoft.com/machines
```
