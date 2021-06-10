---
title: ID API로 경고 정보 얻기
description: ID로 경고 정보 다운로드 API를 사용하여 끝점용 Microsoft Defender에서 ID로 특정 경고를 검색하는 방법을 학습합니다.
keywords: api, 그래프 api, 지원되는 api, get, alert, information, id
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
ms.openlocfilehash: b9de7645abc59849b3ca28f64904b0ba49d4eef5
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771900"
---
# <a name="get-alert-information-by-id-api"></a><span data-ttu-id="e53a3-104">ID API로 경고 정보 얻기</span><span class="sxs-lookup"><span data-stu-id="e53a3-104">Get alert information by ID API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e53a3-105">**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="e53a3-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="e53a3-106">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="e53a3-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e53a3-107">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="e53a3-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="e53a3-108">API 설명</span><span class="sxs-lookup"><span data-stu-id="e53a3-108">API description</span></span>
<span data-ttu-id="e53a3-109">ID로 [특정 경고를](alerts.md) 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="e53a3-109">Retrieves specific [Alert](alerts.md) by its ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="e53a3-110">제한 사항</span><span class="sxs-lookup"><span data-stu-id="e53a3-110">Limitations</span></span>
1. <span data-ttu-id="e53a3-111">구성된 보존 기간에 따라 마지막으로 업데이트된 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e53a3-111">You can get alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="e53a3-112">이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.</span><span class="sxs-lookup"><span data-stu-id="e53a3-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="e53a3-113">사용 권한</span><span class="sxs-lookup"><span data-stu-id="e53a3-113">Permissions</span></span>
<span data-ttu-id="e53a3-114">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e53a3-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="e53a3-115">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="e53a3-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="e53a3-116">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="e53a3-116">Permission type</span></span> |   <span data-ttu-id="e53a3-117">사용 권한</span><span class="sxs-lookup"><span data-stu-id="e53a3-117">Permission</span></span>  |   <span data-ttu-id="e53a3-118">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="e53a3-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="e53a3-119">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="e53a3-119">Application</span></span> |   <span data-ttu-id="e53a3-120">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="e53a3-120">Alert.Read.All</span></span> |    <span data-ttu-id="e53a3-121">'모든 경고 읽기'</span><span class="sxs-lookup"><span data-stu-id="e53a3-121">'Read all alerts'</span></span>
<span data-ttu-id="e53a3-122">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="e53a3-122">Application</span></span> |   <span data-ttu-id="e53a3-123">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="e53a3-123">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="e53a3-124">'모든 경고 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="e53a3-124">'Read and write all alerts'</span></span>
<span data-ttu-id="e53a3-125">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="e53a3-125">Delegated (work or school account)</span></span> | <span data-ttu-id="e53a3-126">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="e53a3-126">Alert.Read</span></span> | <span data-ttu-id="e53a3-127">'경고 읽기'</span><span class="sxs-lookup"><span data-stu-id="e53a3-127">'Read alerts'</span></span>
<span data-ttu-id="e53a3-128">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="e53a3-128">Delegated (work or school account)</span></span> | <span data-ttu-id="e53a3-129">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="e53a3-129">Alert.ReadWrite</span></span> | <span data-ttu-id="e53a3-130">'경고 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="e53a3-130">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="e53a3-131">사용자 자격 증명을 사용하여 토큰을 얻을 때:</span><span class="sxs-lookup"><span data-stu-id="e53a3-131">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="e53a3-132">사용자에게 최소한 '데이터 보기' 역할 권한이 필요합니다(자세한 내용은 역할 [만들기](user-roles.md) 및 관리 참조).</span><span class="sxs-lookup"><span data-stu-id="e53a3-132">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="e53a3-133">사용자는 장치 그룹 설정에 따라 경고와 연결된 장치에 액세스할 수 있습니다(자세한 내용은 장치 그룹 만들기 및 [관리](machine-groups.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="e53a3-133">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="e53a3-134">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="e53a3-134">HTTP request</span></span>
```
GET /api/alerts/{id}
```

## <a name="request-headers"></a><span data-ttu-id="e53a3-135">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="e53a3-135">Request headers</span></span>

<span data-ttu-id="e53a3-136">이름</span><span class="sxs-lookup"><span data-stu-id="e53a3-136">Name</span></span> | <span data-ttu-id="e53a3-137">유형</span><span class="sxs-lookup"><span data-stu-id="e53a3-137">Type</span></span> | <span data-ttu-id="e53a3-138">설명</span><span class="sxs-lookup"><span data-stu-id="e53a3-138">Description</span></span>
:---|:---|:---
<span data-ttu-id="e53a3-139">권한 부여</span><span class="sxs-lookup"><span data-stu-id="e53a3-139">Authorization</span></span> | <span data-ttu-id="e53a3-140">String</span><span class="sxs-lookup"><span data-stu-id="e53a3-140">String</span></span> | <span data-ttu-id="e53a3-141">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="e53a3-141">Bearer {token}.</span></span> <span data-ttu-id="e53a3-142">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="e53a3-142">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="e53a3-143">요청 본문</span><span class="sxs-lookup"><span data-stu-id="e53a3-143">Request body</span></span>
<span data-ttu-id="e53a3-144">비어 있음</span><span class="sxs-lookup"><span data-stu-id="e53a3-144">Empty</span></span>

## <a name="response"></a><span data-ttu-id="e53a3-145">응답</span><span class="sxs-lookup"><span data-stu-id="e53a3-145">Response</span></span>
<span data-ttu-id="e53a3-146">성공하면 이 메서드는 200 OK를 [](alerts.md) 반환하고 응답 본문의 경고 엔터티를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e53a3-146">If successful, this method returns 200 OK, and the [alert](alerts.md) entity in the response body.</span></span> <span data-ttu-id="e53a3-147">지정된 ID가 있는 알림을 찾을 수 없는 경우 - 404 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e53a3-147">If alert with the specified id was not found - 404 Not Found.</span></span>
