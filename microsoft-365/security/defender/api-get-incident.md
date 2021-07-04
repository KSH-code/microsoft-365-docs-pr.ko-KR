---
title: 인시던트 API 사용
description: 인시던트 발생 API를 사용하여 인시던트에서 단일 인시던트가 발생하게 하는 방법을 Microsoft 365 Defender.
keywords: api, 그래프 api, 지원되는 api, 다운로드, 파일, 해시
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
ms.openlocfilehash: 2e051803a4cd228e3b455ec08b30e5c2197ca9a3
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289610"
---
# <a name="get-incident-information-api"></a><span data-ttu-id="f375a-104">인시던트 정보 얻기 API</span><span class="sxs-lookup"><span data-stu-id="f375a-104">Get incident information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f375a-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="f375a-105">**Applies to:**</span></span>
- [<span data-ttu-id="f375a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f375a-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f375a-107">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="f375a-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f375a-108">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="f375a-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="f375a-109">API 설명</span><span class="sxs-lookup"><span data-stu-id="f375a-109">API description</span></span>

<span data-ttu-id="f375a-110">ID로 특정 인시던트 검색</span><span class="sxs-lookup"><span data-stu-id="f375a-110">Retrieves a specific incident by its ID</span></span>

## <a name="limitations"></a><span data-ttu-id="f375a-111">제한 사항</span><span class="sxs-lookup"><span data-stu-id="f375a-111">Limitations</span></span>

1. <span data-ttu-id="f375a-112">이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.</span><span class="sxs-lookup"><span data-stu-id="f375a-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="f375a-113">사용 권한</span><span class="sxs-lookup"><span data-stu-id="f375a-113">Permissions</span></span>

<span data-ttu-id="f375a-114">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f375a-114">One of the following permissions is required to call this API.</span></span> 

<span data-ttu-id="f375a-115">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="f375a-115">Permission type</span></span> | <span data-ttu-id="f375a-116">사용 권한</span><span class="sxs-lookup"><span data-stu-id="f375a-116">Permission</span></span> | <span data-ttu-id="f375a-117">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="f375a-117">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="f375a-118">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="f375a-118">Application</span></span> | <span data-ttu-id="f375a-119">Incident.Read.All</span><span class="sxs-lookup"><span data-stu-id="f375a-119">Incident.Read.All</span></span> | <span data-ttu-id="f375a-120">'모든 인시던트 읽기'</span><span class="sxs-lookup"><span data-stu-id="f375a-120">'Read all Incidents'</span></span>
<span data-ttu-id="f375a-121">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="f375a-121">Application</span></span> | <span data-ttu-id="f375a-122">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="f375a-122">Incident.ReadWrite.All</span></span> | <span data-ttu-id="f375a-123">'모든 인시던트 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="f375a-123">'Read and write all Incidents'</span></span>
<span data-ttu-id="f375a-124">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="f375a-124">Delegated (work or school account)</span></span> | <span data-ttu-id="f375a-125">Incident.Read</span><span class="sxs-lookup"><span data-stu-id="f375a-125">Incident.Read</span></span> | <span data-ttu-id="f375a-126">'인시던트 읽기'</span><span class="sxs-lookup"><span data-stu-id="f375a-126">'Read Incidents'</span></span>
<span data-ttu-id="f375a-127">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="f375a-127">Delegated (work or school account)</span></span> | <span data-ttu-id="f375a-128">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="f375a-128">Incident.ReadWrite</span></span> | <span data-ttu-id="f375a-129">'인시던트 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="f375a-129">'Read and write Incidents'</span></span>

> [!NOTE]
>
> <span data-ttu-id="f375a-130">사용자 자격 증명을 사용하여 토큰을 얻을 때:</span><span class="sxs-lookup"><span data-stu-id="f375a-130">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="f375a-131">사용자에게 최소한 '데이터 보기' 역할 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f375a-131">The user needs to have at least the following role permission: 'View Data'</span></span>
> - <span data-ttu-id="f375a-132">응답에는 사용자가 노출된 인시던트만 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f375a-132">The response will only include incidents that the user is exposed to</span></span>

## <a name="http-request"></a><span data-ttu-id="f375a-133">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="f375a-133">HTTP request</span></span>

```console
GET .../api/incidents/{id} 
```

## <a name="request-headers"></a><span data-ttu-id="f375a-134">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="f375a-134">Request headers</span></span>

<span data-ttu-id="f375a-135">이름</span><span class="sxs-lookup"><span data-stu-id="f375a-135">Name</span></span> | <span data-ttu-id="f375a-136">유형</span><span class="sxs-lookup"><span data-stu-id="f375a-136">Type</span></span> | <span data-ttu-id="f375a-137">설명</span><span class="sxs-lookup"><span data-stu-id="f375a-137">Description</span></span>
:---|:---|:---
<span data-ttu-id="f375a-138">권한 부여</span><span class="sxs-lookup"><span data-stu-id="f375a-138">Authorization</span></span> | <span data-ttu-id="f375a-139">문자열</span><span class="sxs-lookup"><span data-stu-id="f375a-139">String</span></span> | <span data-ttu-id="f375a-140">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="f375a-140">Bearer {token}.</span></span> <span data-ttu-id="f375a-141">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="f375a-141">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="f375a-142">요청 본문</span><span class="sxs-lookup"><span data-stu-id="f375a-142">Request body</span></span>

<span data-ttu-id="f375a-143">비어 있음</span><span class="sxs-lookup"><span data-stu-id="f375a-143">Empty</span></span>

## <a name="response"></a><span data-ttu-id="f375a-144">응답</span><span class="sxs-lookup"><span data-stu-id="f375a-144">Response</span></span>

<span data-ttu-id="f375a-145">성공하면 이 메서드는 200 OK를 반환하고 응답 본문의 인시던트 엔터티를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f375a-145">If successful, this method returns 200 OK, and the incident entity in the response body.</span></span> <span data-ttu-id="f375a-146">지정한 ID가 있는 인시던트가 발견되지 않은 경우 - 404 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f375a-146">If incident with the specified id was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="f375a-147">예제</span><span class="sxs-lookup"><span data-stu-id="f375a-147">Example</span></span>

<span data-ttu-id="f375a-148">**요청**</span><span class="sxs-lookup"><span data-stu-id="f375a-148">**Request**</span></span>

<span data-ttu-id="f375a-149">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="f375a-149">Here is an example of the request.</span></span>

```http
GET https://api.security.microsoft.com/api/incidents/{id}
```
