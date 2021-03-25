---
title: 내부 IP API로 장치 찾기
description: 요청된 내부 IP가 제공된 타임스탬프 이전 및 이후 15분의 시간 범위에 있는 장치 찾기
keywords: api, 그래프 api, 지원되는 api, get, 장치, IP, 찾기, 장치 찾기, ip, ip
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
ms.openlocfilehash: fa523a7f9b997f3a8d36dff42d10c1229e7a467f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200440"
---
# <a name="find-devices-by-internal-ip-api"></a><span data-ttu-id="903c6-104">내부 IP API로 장치 찾기</span><span class="sxs-lookup"><span data-stu-id="903c6-104">Find devices by internal IP API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="903c6-105">**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="903c6-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="903c6-106">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="903c6-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="903c6-107">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="903c6-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="903c6-108">API 설명</span><span class="sxs-lookup"><span data-stu-id="903c6-108">API description</span></span>
<span data-ttu-id="903c6-109">[요청된](machine.md) 내부 IP가 제공된 타임스탬프 이전 및 이후 15분의 시간 범위에 있는 컴퓨터를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="903c6-109">Find [Machines](machine.md) seen with the requested internal IP in the time range of 15 minutes prior and after a given timestamp.</span></span>


## <a name="limitations"></a><span data-ttu-id="903c6-110">제한 사항</span><span class="sxs-lookup"><span data-stu-id="903c6-110">Limitations</span></span>
1. <span data-ttu-id="903c6-111">주어진 타임스탬프는 지난 30일 동안의 기간이 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="903c6-111">The given timestamp must be in the past 30 days.</span></span>
2. <span data-ttu-id="903c6-112">이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.</span><span class="sxs-lookup"><span data-stu-id="903c6-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="903c6-113">사용 권한</span><span class="sxs-lookup"><span data-stu-id="903c6-113">Permissions</span></span>
<span data-ttu-id="903c6-114">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="903c6-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="903c6-115">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="903c6-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="903c6-116">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="903c6-116">Permission type</span></span> |   <span data-ttu-id="903c6-117">사용 권한</span><span class="sxs-lookup"><span data-stu-id="903c6-117">Permission</span></span>  |   <span data-ttu-id="903c6-118">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="903c6-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="903c6-119">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="903c6-119">Application</span></span> |   <span data-ttu-id="903c6-120">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="903c6-120">Machine.Read.All</span></span> |  <span data-ttu-id="903c6-121">'모든 컴퓨터 프로필 읽기'</span><span class="sxs-lookup"><span data-stu-id="903c6-121">'Read all machine profiles'</span></span>
<span data-ttu-id="903c6-122">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="903c6-122">Application</span></span> |   <span data-ttu-id="903c6-123">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="903c6-123">Machine.ReadWrite.All</span></span> | <span data-ttu-id="903c6-124">'모든 컴퓨터 정보 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="903c6-124">'Read and write all machine information'</span></span>
<span data-ttu-id="903c6-125">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="903c6-125">Delegated (work or school account)</span></span> | <span data-ttu-id="903c6-126">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="903c6-126">Machine.Read</span></span> | <span data-ttu-id="903c6-127">'컴퓨터 정보 읽기'</span><span class="sxs-lookup"><span data-stu-id="903c6-127">'Read machine information'</span></span>
<span data-ttu-id="903c6-128">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="903c6-128">Delegated (work or school account)</span></span> | <span data-ttu-id="903c6-129">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="903c6-129">Machine.ReadWrite</span></span> | <span data-ttu-id="903c6-130">'컴퓨터 정보 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="903c6-130">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="903c6-131">사용자 자격 증명을 사용하여 토큰을 얻을 때:</span><span class="sxs-lookup"><span data-stu-id="903c6-131">When obtaining a token using user credentials:</span></span>
> - <span data-ttu-id="903c6-132">응답에는 사용자가 장치 그룹 설정에 따라 액세스할 수 있는 장치만 포함됩니다(자세한 내용은 장치 그룹 만들기 및 [관리](machine-groups.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="903c6-132">Response will include only devices that the user have access to based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>
> - <span data-ttu-id="903c6-133">사용자에게 최소한 '데이터 보기' 역할 권한이 필요합니다(자세한 내용은 역할 [만들기](user-roles.md) 및 관리 참조).</span><span class="sxs-lookup"><span data-stu-id="903c6-133">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
> - <span data-ttu-id="903c6-134">응답에는 사용자가 장치 그룹 설정에 따라 액세스할 수 있는 장치만 포함됩니다(자세한 내용은 장치 그룹 만들기 및 [관리](machine-groups.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="903c6-134">Response will include only devices that the user have access to based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="903c6-135">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="903c6-135">HTTP request</span></span>
```
GET /api/machines/findbyip(ip='{IP}',timestamp={TimeStamp})
```

## <a name="request-headers"></a><span data-ttu-id="903c6-136">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="903c6-136">Request headers</span></span>

<span data-ttu-id="903c6-137">이름</span><span class="sxs-lookup"><span data-stu-id="903c6-137">Name</span></span> | <span data-ttu-id="903c6-138">유형</span><span class="sxs-lookup"><span data-stu-id="903c6-138">Type</span></span> | <span data-ttu-id="903c6-139">설명</span><span class="sxs-lookup"><span data-stu-id="903c6-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="903c6-140">권한 부여</span><span class="sxs-lookup"><span data-stu-id="903c6-140">Authorization</span></span> | <span data-ttu-id="903c6-141">문자열</span><span class="sxs-lookup"><span data-stu-id="903c6-141">String</span></span> | <span data-ttu-id="903c6-142">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="903c6-142">Bearer {token}.</span></span> <span data-ttu-id="903c6-143">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="903c6-143">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="903c6-144">요청 본문</span><span class="sxs-lookup"><span data-stu-id="903c6-144">Request body</span></span>
<span data-ttu-id="903c6-145">비어 있음</span><span class="sxs-lookup"><span data-stu-id="903c6-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="903c6-146">응답</span><span class="sxs-lookup"><span data-stu-id="903c6-146">Response</span></span>
<span data-ttu-id="903c6-147">성공적이면 - 응답 본문에 컴퓨터 목록이 있는 200 OK.</span><span class="sxs-lookup"><span data-stu-id="903c6-147">If successful - 200 OK with list of the machines in the response body.</span></span>
<span data-ttu-id="903c6-148">타임스탬프가 지난 30일 ( 400 잘못된 요청)에 있지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="903c6-148">If the timestamp is not in the past 30 days - 400 Bad Request.</span></span>

## <a name="example"></a><span data-ttu-id="903c6-149">예제</span><span class="sxs-lookup"><span data-stu-id="903c6-149">Example</span></span>

<span data-ttu-id="903c6-150">**요청**</span><span class="sxs-lookup"><span data-stu-id="903c6-150">**Request**</span></span>

<span data-ttu-id="903c6-151">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="903c6-151">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/findbyip(ip='10.248.240.38',timestamp=2019-09-22T08:44:05Z)
```
