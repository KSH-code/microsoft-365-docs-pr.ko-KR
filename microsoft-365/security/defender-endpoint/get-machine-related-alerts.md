---
title: 컴퓨터 관련 경고 API를 얻습니다.
description: 컴퓨터 관련 알림 다운로드 API를 사용하여 끝점용 Microsoft Defender의 특정 장치와 관련된 모든 경고를 검색하는 방법을 학습합니다.
keywords: api, 그래프 api, 지원되는 api, get, 장치, 관련, 경고
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: bf445332fed7b8661c510bf60f36088b79e2d8df
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770028"
---
# <a name="get-machine-related-alerts--api"></a><span data-ttu-id="4003e-104">컴퓨터 관련 경고 API를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="4003e-104">Get machine related alerts  API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4003e-105">**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="4003e-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="4003e-106">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="4003e-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4003e-107">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="4003e-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="4003e-108">API 설명</span><span class="sxs-lookup"><span data-stu-id="4003e-108">API description</span></span>
<span data-ttu-id="4003e-109">특정 [장치와](alerts.md) 관련된 모든 경고를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="4003e-109">Retrieves all [Alerts](alerts.md) related to a specific device.</span></span>


## <a name="limitations"></a><span data-ttu-id="4003e-110">제한 사항</span><span class="sxs-lookup"><span data-stu-id="4003e-110">Limitations</span></span>
1. <span data-ttu-id="4003e-111">구성된 보존 기간에 따라 마지막으로 업데이트된 장치에서 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4003e-111">You can query on devices last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="4003e-112">이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.</span><span class="sxs-lookup"><span data-stu-id="4003e-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


<span data-ttu-id="4003e-113">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="4003e-113">Permission type</span></span> |   <span data-ttu-id="4003e-114">사용 권한</span><span class="sxs-lookup"><span data-stu-id="4003e-114">Permission</span></span>  |   <span data-ttu-id="4003e-115">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="4003e-115">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="4003e-116">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="4003e-116">Application</span></span> |   <span data-ttu-id="4003e-117">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="4003e-117">Alert.Read.All</span></span> |    <span data-ttu-id="4003e-118">'모든 경고 읽기'</span><span class="sxs-lookup"><span data-stu-id="4003e-118">'Read all alerts'</span></span>
<span data-ttu-id="4003e-119">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="4003e-119">Application</span></span> |   <span data-ttu-id="4003e-120">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="4003e-120">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="4003e-121">'모든 경고 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="4003e-121">'Read and write all alerts'</span></span>
<span data-ttu-id="4003e-122">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="4003e-122">Delegated (work or school account)</span></span> | <span data-ttu-id="4003e-123">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="4003e-123">Alert.Read</span></span> | <span data-ttu-id="4003e-124">'경고 읽기'</span><span class="sxs-lookup"><span data-stu-id="4003e-124">'Read alerts'</span></span>
<span data-ttu-id="4003e-125">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="4003e-125">Delegated (work or school account)</span></span> | <span data-ttu-id="4003e-126">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="4003e-126">Alert.ReadWrite</span></span> | <span data-ttu-id="4003e-127">'경고 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="4003e-127">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="4003e-128">사용자 자격 증명을 사용하여 토큰을 얻을 때:</span><span class="sxs-lookup"><span data-stu-id="4003e-128">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="4003e-129">사용자에게 최소한 '데이터 보기' 역할 권한이 필요합니다(자세한 내용은 역할 [만들기](user-roles.md) 및 관리 참조).</span><span class="sxs-lookup"><span data-stu-id="4003e-129">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="4003e-130">사용자는 장치 그룹 설정에 따라 장치에 액세스할 수 있습니다(자세한 내용은 장치 그룹 만들기 및 [관리](machine-groups.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="4003e-130">User needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="4003e-131">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="4003e-131">HTTP request</span></span>
```http
GET /api/machines/{id}/alerts
```

## <a name="request-headers"></a><span data-ttu-id="4003e-132">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="4003e-132">Request headers</span></span>

<span data-ttu-id="4003e-133">이름</span><span class="sxs-lookup"><span data-stu-id="4003e-133">Name</span></span> | <span data-ttu-id="4003e-134">유형</span><span class="sxs-lookup"><span data-stu-id="4003e-134">Type</span></span> | <span data-ttu-id="4003e-135">설명</span><span class="sxs-lookup"><span data-stu-id="4003e-135">Description</span></span>
:---|:---|:---
<span data-ttu-id="4003e-136">권한 부여</span><span class="sxs-lookup"><span data-stu-id="4003e-136">Authorization</span></span> | <span data-ttu-id="4003e-137">String</span><span class="sxs-lookup"><span data-stu-id="4003e-137">String</span></span> | <span data-ttu-id="4003e-138">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="4003e-138">Bearer {token}.</span></span> <span data-ttu-id="4003e-139">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="4003e-139">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="4003e-140">요청 본문</span><span class="sxs-lookup"><span data-stu-id="4003e-140">Request body</span></span>
<span data-ttu-id="4003e-141">비어 있음</span><span class="sxs-lookup"><span data-stu-id="4003e-141">Empty</span></span>

## <a name="response"></a><span data-ttu-id="4003e-142">응답</span><span class="sxs-lookup"><span data-stu-id="4003e-142">Response</span></span>
<span data-ttu-id="4003e-143">성공 및 장치가 있는 경우 - 본문에 [](alerts.md) 경고 엔터티 목록이 있는 200 OK.</span><span class="sxs-lookup"><span data-stu-id="4003e-143">If successful and device exists - 200 OK with list of [alert](alerts.md) entities in the body.</span></span> <span data-ttu-id="4003e-144">장치를 찾을 수 없는 경우 - 404 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4003e-144">If device was not found - 404 Not Found.</span></span>
