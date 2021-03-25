---
title: 파일 정보 다운로드 API
description: 파일 정보 다운로드 API를 사용하여 끝점용 Microsoft Defender에서 Sha1, Sha256 또는 MD5 식별자에 의해 파일을 다운로드하는 방법을 학습합니다.
keywords: api, 그래프 api, 지원되는 api, get, 파일, 정보, sha1, sha256, md5
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
ms.openlocfilehash: 181d808b465bfbf26eeff48a564e231b00a9a77f
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166854"
---
# <a name="get-file-information-api"></a><span data-ttu-id="91a4f-104">파일 정보 다운로드 API</span><span class="sxs-lookup"><span data-stu-id="91a4f-104">Get file information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="91a4f-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="91a4f-105">**Applies to:**</span></span>
- [<span data-ttu-id="91a4f-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="91a4f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="91a4f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="91a4f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="91a4f-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="91a4f-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="91a4f-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="91a4f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="91a4f-110">API 설명</span><span class="sxs-lookup"><span data-stu-id="91a4f-110">API description</span></span>
<span data-ttu-id="91a4f-111">식별자 [](files.md) Sha1 또는 Sha256으로 파일 검색</span><span class="sxs-lookup"><span data-stu-id="91a4f-111">Retrieves a [File](files.md) by identifier Sha1, or Sha256</span></span>


## <a name="limitations"></a><span data-ttu-id="91a4f-112">제한 사항</span><span class="sxs-lookup"><span data-stu-id="91a4f-112">Limitations</span></span>
1. <span data-ttu-id="91a4f-113">이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.</span><span class="sxs-lookup"><span data-stu-id="91a4f-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="91a4f-114">사용 권한</span><span class="sxs-lookup"><span data-stu-id="91a4f-114">Permissions</span></span>
<span data-ttu-id="91a4f-115">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="91a4f-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="91a4f-116">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="91a4f-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="91a4f-117">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="91a4f-117">Permission type</span></span> |   <span data-ttu-id="91a4f-118">사용 권한</span><span class="sxs-lookup"><span data-stu-id="91a4f-118">Permission</span></span>  |   <span data-ttu-id="91a4f-119">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="91a4f-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="91a4f-120">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="91a4f-120">Application</span></span> |   <span data-ttu-id="91a4f-121">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="91a4f-121">File.Read.All</span></span> | <span data-ttu-id="91a4f-122">'모든 파일 프로필 읽기'</span><span class="sxs-lookup"><span data-stu-id="91a4f-122">'Read all file profiles'</span></span>
<span data-ttu-id="91a4f-123">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="91a4f-123">Delegated (work or school account)</span></span> | <span data-ttu-id="91a4f-124">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="91a4f-124">File.Read.All</span></span> |    <span data-ttu-id="91a4f-125">'모든 파일 프로필 읽기'</span><span class="sxs-lookup"><span data-stu-id="91a4f-125">'Read all file profiles'</span></span>

>[!Note]
> <span data-ttu-id="91a4f-126">사용자 자격 증명을 사용하여 토큰을 얻을 때:</span><span class="sxs-lookup"><span data-stu-id="91a4f-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="91a4f-127">사용자에게 최소한 '데이터 보기' 역할 권한이 필요합니다(자세한 내용은 역할 [만들기](user-roles.md) 및 관리 참조).</span><span class="sxs-lookup"><span data-stu-id="91a4f-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="91a4f-128">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="91a4f-128">HTTP request</span></span>
```
GET /api/files/{id}
```

## <a name="request-headers"></a><span data-ttu-id="91a4f-129">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="91a4f-129">Request headers</span></span>

<span data-ttu-id="91a4f-130">이름</span><span class="sxs-lookup"><span data-stu-id="91a4f-130">Name</span></span> | <span data-ttu-id="91a4f-131">유형</span><span class="sxs-lookup"><span data-stu-id="91a4f-131">Type</span></span> | <span data-ttu-id="91a4f-132">설명</span><span class="sxs-lookup"><span data-stu-id="91a4f-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="91a4f-133">권한 부여</span><span class="sxs-lookup"><span data-stu-id="91a4f-133">Authorization</span></span> | <span data-ttu-id="91a4f-134">문자열</span><span class="sxs-lookup"><span data-stu-id="91a4f-134">String</span></span> | <span data-ttu-id="91a4f-135">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="91a4f-135">Bearer {token}.</span></span> <span data-ttu-id="91a4f-136">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="91a4f-136">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="91a4f-137">요청 본문</span><span class="sxs-lookup"><span data-stu-id="91a4f-137">Request body</span></span>
<span data-ttu-id="91a4f-138">비어 있음</span><span class="sxs-lookup"><span data-stu-id="91a4f-138">Empty</span></span>

## <a name="response"></a><span data-ttu-id="91a4f-139">응답</span><span class="sxs-lookup"><span data-stu-id="91a4f-139">Response</span></span>
<span data-ttu-id="91a4f-140">성공적이고 파일이 있는 경우 - 본문에 파일 엔터티가 있는 200 OK. [](files.md)</span><span class="sxs-lookup"><span data-stu-id="91a4f-140">If successful and file exists - 200 OK with the [file](files.md) entity in the body.</span></span> <span data-ttu-id="91a4f-141">파일이 없는 경우 - 404 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="91a4f-141">If file does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="91a4f-142">예제</span><span class="sxs-lookup"><span data-stu-id="91a4f-142">Example</span></span>

<span data-ttu-id="91a4f-143">**요청**</span><span class="sxs-lookup"><span data-stu-id="91a4f-143">**Request**</span></span>

<span data-ttu-id="91a4f-144">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="91a4f-144">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/files/4388963aaa83afe2042a46a3c017ad50bdcdafb3
```

<span data-ttu-id="91a4f-145">**응답**</span><span class="sxs-lookup"><span data-stu-id="91a4f-145">**Response**</span></span>

<span data-ttu-id="91a4f-146">다음은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="91a4f-146">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Files/$entity",
    "sha1": "4388963aaa83afe2042a46a3c017ad50bdcdafb3",
    "sha256": "413c58c8267d2c8648d8f6384bacc2ae9c929b2b96578b6860b5087cd1bd6462",
    "globalPrevalence": 180022,
    "globalFirstObserved": "2017-09-19T03:51:27.6785431Z",
    "globalLastObserved": "2020-01-06T03:59:21.3229314Z",
    "size": 22139496,
    "fileType": "APP",
    "isPeFile": true,
    "filePublisher": "CHENGDU YIWO Tech Development Co., Ltd.",
    "fileProductName": "EaseUS MobiSaver for Android",
    "signer": "CHENGDU YIWO Tech Development Co., Ltd.",
    "issuer": "VeriSign Class 3 Code Signing 2010 CA",
    "signerHash": "6c3245d4a9bc0244d99dff27af259cbbae2e2d16",
    "isValidCertificate": false,
    "determinationType": "Pua",
    "determinationValue": "PUA:Win32/FusionCore"
}
```
