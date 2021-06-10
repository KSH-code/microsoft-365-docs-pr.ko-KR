---
title: 도메인 관련 알림 API를 얻습니다.
description: 도메인 관련 알림 다운로드 API를 사용하여 끝점용 Microsoft Defender에서 특정 도메인 주소와 관련된 경고를 검색하는 방법을 학습합니다.
keywords: api, 그래프 api, 지원되는 api, get, 도메인, 관련, 경고
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
ms.openlocfilehash: c5de779566f1aa8e53da10b9aa5bceb92f5a0a3c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772260"
---
# <a name="get-domain-related-alerts-api"></a><span data-ttu-id="ed125-104">도메인 관련 알림 API를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="ed125-104">Get domain-related alerts API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ed125-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="ed125-105">**Applies to:**</span></span>
- [<span data-ttu-id="ed125-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ed125-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ed125-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ed125-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ed125-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="ed125-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ed125-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="ed125-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="ed125-110">API 설명</span><span class="sxs-lookup"><span data-stu-id="ed125-110">API description</span></span>
<span data-ttu-id="ed125-111">지정한 도메인 주소와 관련된 [Alerts](alerts.md) 컬렉션을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="ed125-111">Retrieves a collection of [Alerts](alerts.md) related to a given domain address.</span></span>


## <a name="limitations"></a><span data-ttu-id="ed125-112">제한 사항</span><span class="sxs-lookup"><span data-stu-id="ed125-112">Limitations</span></span>
1. <span data-ttu-id="ed125-113">구성된 보존 기간에 따라 마지막으로 업데이트된 경고에 대해 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed125-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="ed125-114">이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.</span><span class="sxs-lookup"><span data-stu-id="ed125-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="ed125-115">사용 권한</span><span class="sxs-lookup"><span data-stu-id="ed125-115">Permissions</span></span>
<span data-ttu-id="ed125-116">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ed125-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="ed125-117">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="ed125-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="ed125-118">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="ed125-118">Permission type</span></span> |   <span data-ttu-id="ed125-119">사용 권한</span><span class="sxs-lookup"><span data-stu-id="ed125-119">Permission</span></span>  |   <span data-ttu-id="ed125-120">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="ed125-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="ed125-121">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="ed125-121">Application</span></span> |   <span data-ttu-id="ed125-122">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="ed125-122">Alert.Read.All</span></span> |    <span data-ttu-id="ed125-123">'모든 경고 읽기'</span><span class="sxs-lookup"><span data-stu-id="ed125-123">'Read all alerts'</span></span>
<span data-ttu-id="ed125-124">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="ed125-124">Application</span></span> |   <span data-ttu-id="ed125-125">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="ed125-125">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="ed125-126">'모든 경고 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="ed125-126">'Read and write all alerts'</span></span>
<span data-ttu-id="ed125-127">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="ed125-127">Delegated (work or school account)</span></span> | <span data-ttu-id="ed125-128">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="ed125-128">Alert.Read</span></span> | <span data-ttu-id="ed125-129">'경고 읽기'</span><span class="sxs-lookup"><span data-stu-id="ed125-129">'Read alerts'</span></span>
<span data-ttu-id="ed125-130">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="ed125-130">Delegated (work or school account)</span></span> | <span data-ttu-id="ed125-131">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="ed125-131">Alert.ReadWrite</span></span> | <span data-ttu-id="ed125-132">'경고 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="ed125-132">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="ed125-133">사용자 자격 증명을 사용하여 토큰을 얻을 때:</span><span class="sxs-lookup"><span data-stu-id="ed125-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="ed125-134">사용자에게 최소한 '데이터 보기' 역할 권한이 필요합니다(자세한 내용은 역할 [만들기](user-roles.md) 및 관리 참조).</span><span class="sxs-lookup"><span data-stu-id="ed125-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="ed125-135">응답에는 장치 그룹 설정에 따라 사용자가 액세스할 수 있는 알림만 포함됩니다(자세한 내용은 장치 그룹 [만들기](machine-groups.md) 및 관리 참조).</span><span class="sxs-lookup"><span data-stu-id="ed125-135">Response will include only alerts, associated with devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="ed125-136">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="ed125-136">HTTP request</span></span>
```http
GET /api/domains/{domain}/alerts
```

## <a name="request-headers"></a><span data-ttu-id="ed125-137">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="ed125-137">Request headers</span></span>

| <span data-ttu-id="ed125-138">머리글</span><span class="sxs-lookup"><span data-stu-id="ed125-138">Header</span></span>        | <span data-ttu-id="ed125-139">값</span><span class="sxs-lookup"><span data-stu-id="ed125-139">Value</span></span>  |
|:--------------|:-------|
| <span data-ttu-id="ed125-140">권한 부여</span><span class="sxs-lookup"><span data-stu-id="ed125-140">Authorization</span></span> | <span data-ttu-id="ed125-141">String</span><span class="sxs-lookup"><span data-stu-id="ed125-141">String</span></span> |

## <a name="request-body"></a><span data-ttu-id="ed125-142">요청 본문</span><span class="sxs-lookup"><span data-stu-id="ed125-142">Request body</span></span>
<span data-ttu-id="ed125-143">비어 있음</span><span class="sxs-lookup"><span data-stu-id="ed125-143">Empty</span></span>

## <a name="response"></a><span data-ttu-id="ed125-144">응답</span><span class="sxs-lookup"><span data-stu-id="ed125-144">Response</span></span>
<span data-ttu-id="ed125-145">성공적이고 도메인이 있는 경우 - 경고 [](alerts.md) 엔터티 목록이 있는 200 OK.</span><span class="sxs-lookup"><span data-stu-id="ed125-145">If successful and domain exists - 200 OK with list of [alert](alerts.md) entities.</span></span> <span data-ttu-id="ed125-146">도메인이 없는 경우 - 404 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ed125-146">If domain does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="ed125-147">예시</span><span class="sxs-lookup"><span data-stu-id="ed125-147">Example</span></span>

<span data-ttu-id="ed125-148">**요청**</span><span class="sxs-lookup"><span data-stu-id="ed125-148">**Request**</span></span>

<span data-ttu-id="ed125-149">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="ed125-149">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/domains/client.wns.windows.com/alerts
```
