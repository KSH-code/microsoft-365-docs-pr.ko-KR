---
title: 컴퓨터 오프보드 API
description: API를 사용하여 WDATP(Advanced Threat Protection)에서 Windows Defender 방법을 학습합니다.
keywords: api, 그래프 api, 지원되는 api, 조사 패키지 수집
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
ms.openlocfilehash: 0b3fa5a5daba1aa09eef0f733c7439848ce66a2c
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187345"
---
# <a name="offboard-machine-api"></a><span data-ttu-id="791d3-104">컴퓨터 오프보드 API</span><span class="sxs-lookup"><span data-stu-id="791d3-104">Offboard machine API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="791d3-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="791d3-105">**Applies to:**</span></span>
- [<span data-ttu-id="791d3-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="791d3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="791d3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="791d3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="791d3-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="791d3-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="791d3-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="791d3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="791d3-110">API 설명</span><span class="sxs-lookup"><span data-stu-id="791d3-110">API description</span></span>
<span data-ttu-id="791d3-111">Endpoint용 Defender에서 디바이스를 오프보드합니다.</span><span class="sxs-lookup"><span data-stu-id="791d3-111">Offboard device from Defender for Endpoint.</span></span>


## <a name="limitations"></a><span data-ttu-id="791d3-112">제한 사항</span><span class="sxs-lookup"><span data-stu-id="791d3-112">Limitations</span></span>
 - <span data-ttu-id="791d3-113">이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.</span><span class="sxs-lookup"><span data-stu-id="791d3-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Machine actions note](../../includes/machineactionsnote.md)]

>[!Note]
> <span data-ttu-id="791d3-114">이 API는 Windows 10 버전 1703 이상 또는 Windows Server 2019 이상에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="791d3-114">This API is supported on Windows 10, version 1703 and later, or Windows Server 2019 and later.</span></span> <span data-ttu-id="791d3-115">이 API는 MacOS 또는 Linux 장치에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="791d3-115">This API is not supported on MacOS or Linux devices.</span></span>

## <a name="permissions"></a><span data-ttu-id="791d3-116">사용 권한</span><span class="sxs-lookup"><span data-stu-id="791d3-116">Permissions</span></span>
<span data-ttu-id="791d3-117">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="791d3-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="791d3-118">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 끝점 API에 [Defender 사용을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="791d3-118">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="791d3-119">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="791d3-119">Permission type</span></span> |   <span data-ttu-id="791d3-120">사용 권한</span><span class="sxs-lookup"><span data-stu-id="791d3-120">Permission</span></span>  |   <span data-ttu-id="791d3-121">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="791d3-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="791d3-122">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="791d3-122">Application</span></span> |   <span data-ttu-id="791d3-123">Machine.Offboard</span><span class="sxs-lookup"><span data-stu-id="791d3-123">Machine.Offboard</span></span> |  <span data-ttu-id="791d3-124">'컴퓨터 오프보드'</span><span class="sxs-lookup"><span data-stu-id="791d3-124">'Offboard machine'</span></span>
<span data-ttu-id="791d3-125">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="791d3-125">Delegated (work or school account)</span></span> |    <span data-ttu-id="791d3-126">Machine.Offboard</span><span class="sxs-lookup"><span data-stu-id="791d3-126">Machine.Offboard</span></span> |  <span data-ttu-id="791d3-127">'컴퓨터 오프보드'</span><span class="sxs-lookup"><span data-stu-id="791d3-127">'Offboard machine'</span></span>

>[!Note]
> <span data-ttu-id="791d3-128">사용자 자격 증명을 사용하여 토큰을 얻을 때:</span><span class="sxs-lookup"><span data-stu-id="791d3-128">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="791d3-129">사용자에게 '전역 관리자' AD 역할이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="791d3-129">The user needs to 'Global Admin' AD role</span></span>
>- <span data-ttu-id="791d3-130">사용자는 장치 그룹 설정에 따라 장치에 액세스할 수 있습니다(자세한 내용은 장치 그룹 만들기 및 [관리](machine-groups.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="791d3-130">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="791d3-131">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="791d3-131">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/offboard
```

## <a name="request-headers"></a><span data-ttu-id="791d3-132">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="791d3-132">Request headers</span></span>

<span data-ttu-id="791d3-133">이름</span><span class="sxs-lookup"><span data-stu-id="791d3-133">Name</span></span> | <span data-ttu-id="791d3-134">유형</span><span class="sxs-lookup"><span data-stu-id="791d3-134">Type</span></span> | <span data-ttu-id="791d3-135">설명</span><span class="sxs-lookup"><span data-stu-id="791d3-135">Description</span></span>
:---|:---|:---
<span data-ttu-id="791d3-136">권한 부여</span><span class="sxs-lookup"><span data-stu-id="791d3-136">Authorization</span></span> | <span data-ttu-id="791d3-137">문자열</span><span class="sxs-lookup"><span data-stu-id="791d3-137">String</span></span> | <span data-ttu-id="791d3-138">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="791d3-138">Bearer {token}.</span></span> <span data-ttu-id="791d3-139">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="791d3-139">**Required**.</span></span>
<span data-ttu-id="791d3-140">Content-Type</span><span class="sxs-lookup"><span data-stu-id="791d3-140">Content-Type</span></span> | <span data-ttu-id="791d3-141">문자열</span><span class="sxs-lookup"><span data-stu-id="791d3-141">string</span></span> | <span data-ttu-id="791d3-142">application/json.</span><span class="sxs-lookup"><span data-stu-id="791d3-142">application/json.</span></span> <span data-ttu-id="791d3-143">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="791d3-143">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="791d3-144">요청 본문</span><span class="sxs-lookup"><span data-stu-id="791d3-144">Request body</span></span>
<span data-ttu-id="791d3-145">요청 본문에 다음 매개 변수를 사용하여 JSON 개체를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="791d3-145">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="791d3-146">매개 변수</span><span class="sxs-lookup"><span data-stu-id="791d3-146">Parameter</span></span> | <span data-ttu-id="791d3-147">유형</span><span class="sxs-lookup"><span data-stu-id="791d3-147">Type</span></span>    | <span data-ttu-id="791d3-148">설명</span><span class="sxs-lookup"><span data-stu-id="791d3-148">Description</span></span>
:---|:---|:---
<span data-ttu-id="791d3-149">Comment</span><span class="sxs-lookup"><span data-stu-id="791d3-149">Comment</span></span> |   <span data-ttu-id="791d3-150">String</span><span class="sxs-lookup"><span data-stu-id="791d3-150">String</span></span> |    <span data-ttu-id="791d3-151">작업과 연결되는 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="791d3-151">Comment to associate with the action.</span></span> <span data-ttu-id="791d3-152">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="791d3-152">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="791d3-153">응답</span><span class="sxs-lookup"><span data-stu-id="791d3-153">Response</span></span>
<span data-ttu-id="791d3-154">성공하면 이 메서드는 응답 본문에 201 - 생성된 응답 코드 및 [컴퓨터](machineaction.md) 작업을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="791d3-154">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="791d3-155">예제</span><span class="sxs-lookup"><span data-stu-id="791d3-155">Example</span></span>

<span data-ttu-id="791d3-156">**요청**</span><span class="sxs-lookup"><span data-stu-id="791d3-156">**Request**</span></span>

<span data-ttu-id="791d3-157">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="791d3-157">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/offboard
```

```json
{
  "Comment": "Offboard machine by automation"
}
```
