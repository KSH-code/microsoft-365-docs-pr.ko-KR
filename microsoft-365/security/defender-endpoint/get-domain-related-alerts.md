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
ms.technology: mde
ms.openlocfilehash: f8de54072c0b0ebef69b8e5586fee058b971c51f
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166866"
---
# <a name="get-domain-related-alerts-api"></a><span data-ttu-id="643ed-104">도메인 관련 알림 API를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="643ed-104">Get domain-related alerts API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="643ed-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="643ed-105">**Applies to:**</span></span>
- [<span data-ttu-id="643ed-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="643ed-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="643ed-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="643ed-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="643ed-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="643ed-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="643ed-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="643ed-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="643ed-110">API 설명</span><span class="sxs-lookup"><span data-stu-id="643ed-110">API description</span></span>
<span data-ttu-id="643ed-111">지정한 도메인 주소와 관련된 [Alerts](alerts.md) 컬렉션을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="643ed-111">Retrieves a collection of [Alerts](alerts.md) related to a given domain address.</span></span>


## <a name="limitations"></a><span data-ttu-id="643ed-112">제한 사항</span><span class="sxs-lookup"><span data-stu-id="643ed-112">Limitations</span></span>
1. <span data-ttu-id="643ed-113">구성된 보존 기간에 따라 마지막으로 업데이트된 경고에 대해 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="643ed-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="643ed-114">이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.</span><span class="sxs-lookup"><span data-stu-id="643ed-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="643ed-115">사용 권한</span><span class="sxs-lookup"><span data-stu-id="643ed-115">Permissions</span></span>
<span data-ttu-id="643ed-116">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="643ed-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="643ed-117">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="643ed-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="643ed-118">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="643ed-118">Permission type</span></span> |   <span data-ttu-id="643ed-119">사용 권한</span><span class="sxs-lookup"><span data-stu-id="643ed-119">Permission</span></span>  |   <span data-ttu-id="643ed-120">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="643ed-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="643ed-121">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="643ed-121">Application</span></span> |   <span data-ttu-id="643ed-122">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="643ed-122">Alert.Read.All</span></span> |    <span data-ttu-id="643ed-123">'모든 경고 읽기'</span><span class="sxs-lookup"><span data-stu-id="643ed-123">'Read all alerts'</span></span>
<span data-ttu-id="643ed-124">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="643ed-124">Application</span></span> |   <span data-ttu-id="643ed-125">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="643ed-125">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="643ed-126">'모든 경고 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="643ed-126">'Read and write all alerts'</span></span>
<span data-ttu-id="643ed-127">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="643ed-127">Delegated (work or school account)</span></span> | <span data-ttu-id="643ed-128">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="643ed-128">Alert.Read</span></span> | <span data-ttu-id="643ed-129">'경고 읽기'</span><span class="sxs-lookup"><span data-stu-id="643ed-129">'Read alerts'</span></span>
<span data-ttu-id="643ed-130">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="643ed-130">Delegated (work or school account)</span></span> | <span data-ttu-id="643ed-131">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="643ed-131">Alert.ReadWrite</span></span> | <span data-ttu-id="643ed-132">'경고 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="643ed-132">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="643ed-133">사용자 자격 증명을 사용하여 토큰을 얻을 때:</span><span class="sxs-lookup"><span data-stu-id="643ed-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="643ed-134">사용자에게 최소한 '데이터 보기' 역할 권한이 필요합니다(자세한 내용은 역할 [만들기](user-roles.md) 및 관리 참조).</span><span class="sxs-lookup"><span data-stu-id="643ed-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="643ed-135">응답에는 장치 그룹 설정에 따라 사용자가 액세스할 수 있는 알림만 포함됩니다(자세한 내용은 장치 그룹 [만들기](machine-groups.md) 및 관리 참조).</span><span class="sxs-lookup"><span data-stu-id="643ed-135">Response will include only alerts, associated with devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="643ed-136">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="643ed-136">HTTP request</span></span>
```http
GET /api/domains/{domain}/alerts
```

## <a name="request-headers"></a><span data-ttu-id="643ed-137">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="643ed-137">Request headers</span></span>

| <span data-ttu-id="643ed-138">머리글</span><span class="sxs-lookup"><span data-stu-id="643ed-138">Header</span></span>        | <span data-ttu-id="643ed-139">값</span><span class="sxs-lookup"><span data-stu-id="643ed-139">Value</span></span>  |
|:--------------|:-------|
| <span data-ttu-id="643ed-140">권한 부여</span><span class="sxs-lookup"><span data-stu-id="643ed-140">Authorization</span></span> | <span data-ttu-id="643ed-141">문자열</span><span class="sxs-lookup"><span data-stu-id="643ed-141">String</span></span> |

## <a name="request-body"></a><span data-ttu-id="643ed-142">요청 본문</span><span class="sxs-lookup"><span data-stu-id="643ed-142">Request body</span></span>
<span data-ttu-id="643ed-143">비어 있음</span><span class="sxs-lookup"><span data-stu-id="643ed-143">Empty</span></span>

## <a name="response"></a><span data-ttu-id="643ed-144">응답</span><span class="sxs-lookup"><span data-stu-id="643ed-144">Response</span></span>
<span data-ttu-id="643ed-145">성공적이고 도메인이 있는 경우 - 경고 [](alerts.md) 엔터티 목록이 있는 200 OK.</span><span class="sxs-lookup"><span data-stu-id="643ed-145">If successful and domain exists - 200 OK with list of [alert](alerts.md) entities.</span></span> <span data-ttu-id="643ed-146">도메인이 없는 경우 - 404 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="643ed-146">If domain does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="643ed-147">예제</span><span class="sxs-lookup"><span data-stu-id="643ed-147">Example</span></span>

<span data-ttu-id="643ed-148">**요청**</span><span class="sxs-lookup"><span data-stu-id="643ed-148">**Request**</span></span>

<span data-ttu-id="643ed-149">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="643ed-149">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/domains/client.wns.windows.com/alerts
```
