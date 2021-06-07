---
title: 조사 개체 GET API
description: 이 API를 사용하여 조사 개체 얻기와 관련된 호출 만들기
keywords: api, 그래프 api, 지원되는 api, 조사 개체
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
ms.openlocfilehash: 001b8dcf4b0bfd2550f41454fc840602a6e4361f
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770136"
---
# <a name="get-investigation-api"></a><span data-ttu-id="b95b1-104">조사 API를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="b95b1-104">Get Investigation API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b95b1-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="b95b1-105">**Applies to:**</span></span>
- [<span data-ttu-id="b95b1-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b95b1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b95b1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b95b1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b95b1-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="b95b1-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b95b1-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="b95b1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="b95b1-110">API 설명</span><span class="sxs-lookup"><span data-stu-id="b95b1-110">API description</span></span>
<span data-ttu-id="b95b1-111">ID로 [특정 조사를](investigation.md) 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="b95b1-111">Retrieves specific [Investigation](investigation.md) by its ID.</span></span>
<br> <span data-ttu-id="b95b1-112">ID는 조사 ID 또는 경고 ID를 트리거하는 조사일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b95b1-112">ID can be the investigation ID or the investigation triggering alert ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="b95b1-113">제한 사항</span><span class="sxs-lookup"><span data-stu-id="b95b1-113">Limitations</span></span>
1. <span data-ttu-id="b95b1-114">이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.</span><span class="sxs-lookup"><span data-stu-id="b95b1-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="b95b1-115">사용 권한</span><span class="sxs-lookup"><span data-stu-id="b95b1-115">Permissions</span></span>
<span data-ttu-id="b95b1-116">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b95b1-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="b95b1-117">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="b95b1-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="b95b1-118">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="b95b1-118">Permission type</span></span> |   <span data-ttu-id="b95b1-119">사용 권한</span><span class="sxs-lookup"><span data-stu-id="b95b1-119">Permission</span></span>  |   <span data-ttu-id="b95b1-120">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="b95b1-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="b95b1-121">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="b95b1-121">Application</span></span> |   <span data-ttu-id="b95b1-122">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="b95b1-122">Alert.Read.All</span></span> |    <span data-ttu-id="b95b1-123">'모든 경고 읽기'</span><span class="sxs-lookup"><span data-stu-id="b95b1-123">'Read all alerts'</span></span>
<span data-ttu-id="b95b1-124">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="b95b1-124">Application</span></span> |   <span data-ttu-id="b95b1-125">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="b95b1-125">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="b95b1-126">'모든 경고 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="b95b1-126">'Read and write all alerts'</span></span>
<span data-ttu-id="b95b1-127">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="b95b1-127">Delegated (work or school account)</span></span> | <span data-ttu-id="b95b1-128">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="b95b1-128">Alert.Read</span></span> | <span data-ttu-id="b95b1-129">'경고 읽기'</span><span class="sxs-lookup"><span data-stu-id="b95b1-129">'Read alerts'</span></span>
<span data-ttu-id="b95b1-130">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="b95b1-130">Delegated (work or school account)</span></span> | <span data-ttu-id="b95b1-131">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="b95b1-131">Alert.ReadWrite</span></span> | <span data-ttu-id="b95b1-132">'경고 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="b95b1-132">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="b95b1-133">사용자 자격 증명을 사용하여 토큰을 얻을 때:</span><span class="sxs-lookup"><span data-stu-id="b95b1-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="b95b1-134">사용자에게 최소한 '데이터 보기' 역할 권한이 필요합니다(자세한 내용은 역할 [만들기](user-roles.md) 및 관리 참조).</span><span class="sxs-lookup"><span data-stu-id="b95b1-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="b95b1-135">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="b95b1-135">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/investigations/{id}
```

## <a name="request-headers"></a><span data-ttu-id="b95b1-136">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="b95b1-136">Request headers</span></span>

<span data-ttu-id="b95b1-137">이름</span><span class="sxs-lookup"><span data-stu-id="b95b1-137">Name</span></span> | <span data-ttu-id="b95b1-138">유형</span><span class="sxs-lookup"><span data-stu-id="b95b1-138">Type</span></span> | <span data-ttu-id="b95b1-139">설명</span><span class="sxs-lookup"><span data-stu-id="b95b1-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="b95b1-140">권한 부여</span><span class="sxs-lookup"><span data-stu-id="b95b1-140">Authorization</span></span> | <span data-ttu-id="b95b1-141">String</span><span class="sxs-lookup"><span data-stu-id="b95b1-141">String</span></span> | <span data-ttu-id="b95b1-142">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="b95b1-142">Bearer {token}.</span></span> <span data-ttu-id="b95b1-143">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="b95b1-143">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="b95b1-144">요청 본문</span><span class="sxs-lookup"><span data-stu-id="b95b1-144">Request body</span></span>
<span data-ttu-id="b95b1-145">비어 있음</span><span class="sxs-lookup"><span data-stu-id="b95b1-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="b95b1-146">응답</span><span class="sxs-lookup"><span data-stu-id="b95b1-146">Response</span></span>
<span data-ttu-id="b95b1-147">성공하면 이 메서드는 [Investigations](investigation.md) 엔터티가 있는 200, 확인 응답 코드를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b95b1-147">If successful, this method returns 200, Ok response code with a [Investigations](investigation.md) entity.</span></span>

