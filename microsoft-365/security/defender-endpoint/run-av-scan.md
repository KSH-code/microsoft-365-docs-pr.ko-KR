---
title: 바이러스 백신 검사 실행 API
description: 이 API를 사용하여 장치에서 바이러스 백신 검사 실행과 관련된 호출을 만들 수 있습니다.
keywords: api, 그래프 api, 지원되는 api, 장치 분리
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
ms.openlocfilehash: d0db45daa786c1a44272e4d02153af3fe658e781
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200212"
---
# <a name="run-antivirus-scan-api"></a><span data-ttu-id="2e096-104">바이러스 백신 검사 실행 API</span><span class="sxs-lookup"><span data-stu-id="2e096-104">Run antivirus scan API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2e096-105">**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="2e096-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="2e096-106">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="2e096-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2e096-107">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="2e096-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="2e096-108">API 설명</span><span class="sxs-lookup"><span data-stu-id="2e096-108">API description</span></span>
<span data-ttu-id="2e096-109">장치에서 Microsoft Defender 바이러스 백신 검사 시작</span><span class="sxs-lookup"><span data-stu-id="2e096-109">Initiate Microsoft Defender Antivirus scan on a device.</span></span>


## <a name="limitations"></a><span data-ttu-id="2e096-110">제한 사항</span><span class="sxs-lookup"><span data-stu-id="2e096-110">Limitations</span></span>
1. <span data-ttu-id="2e096-111">이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.</span><span class="sxs-lookup"><span data-stu-id="2e096-111">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="2e096-112">사용 권한</span><span class="sxs-lookup"><span data-stu-id="2e096-112">Permissions</span></span>
<span data-ttu-id="2e096-113">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2e096-113">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="2e096-114">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="2e096-114">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="2e096-115">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="2e096-115">Permission type</span></span> |   <span data-ttu-id="2e096-116">사용 권한</span><span class="sxs-lookup"><span data-stu-id="2e096-116">Permission</span></span>  |   <span data-ttu-id="2e096-117">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="2e096-117">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="2e096-118">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="2e096-118">Application</span></span> |   <span data-ttu-id="2e096-119">Machine.Scan</span><span class="sxs-lookup"><span data-stu-id="2e096-119">Machine.Scan</span></span> |  <span data-ttu-id="2e096-120">'스캔 컴퓨터'</span><span class="sxs-lookup"><span data-stu-id="2e096-120">'Scan machine'</span></span>
<span data-ttu-id="2e096-121">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="2e096-121">Delegated (work or school account)</span></span> |    <span data-ttu-id="2e096-122">Machine.Scan</span><span class="sxs-lookup"><span data-stu-id="2e096-122">Machine.Scan</span></span> |  <span data-ttu-id="2e096-123">'스캔 컴퓨터'</span><span class="sxs-lookup"><span data-stu-id="2e096-123">'Scan machine'</span></span>

>[!Note]
> <span data-ttu-id="2e096-124">사용자 자격 증명을 사용하여 토큰을 얻을 때:</span><span class="sxs-lookup"><span data-stu-id="2e096-124">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="2e096-125">사용자에게 최소한 '활성 수정 작업' 역할 권한이 필요합니다(자세한 내용은 역할 [만들기](user-roles.md) 및 관리 참조).</span><span class="sxs-lookup"><span data-stu-id="2e096-125">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="2e096-126">사용자는 장치 그룹 설정에 따라 장치에 액세스할 수 있습니다(자세한 내용은 장치 그룹 만들기 및 [관리](machine-groups.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="2e096-126">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="2e096-127">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="2e096-127">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/runAntiVirusScan
```

## <a name="request-headers"></a><span data-ttu-id="2e096-128">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="2e096-128">Request headers</span></span>

<span data-ttu-id="2e096-129">이름</span><span class="sxs-lookup"><span data-stu-id="2e096-129">Name</span></span> | <span data-ttu-id="2e096-130">유형</span><span class="sxs-lookup"><span data-stu-id="2e096-130">Type</span></span> | <span data-ttu-id="2e096-131">설명</span><span class="sxs-lookup"><span data-stu-id="2e096-131">Description</span></span>
:---|:---|:---
<span data-ttu-id="2e096-132">권한 부여</span><span class="sxs-lookup"><span data-stu-id="2e096-132">Authorization</span></span> | <span data-ttu-id="2e096-133">문자열</span><span class="sxs-lookup"><span data-stu-id="2e096-133">String</span></span> | <span data-ttu-id="2e096-134">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="2e096-134">Bearer {token}.</span></span> <span data-ttu-id="2e096-135">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="2e096-135">**Required**.</span></span>
<span data-ttu-id="2e096-136">Content-Type</span><span class="sxs-lookup"><span data-stu-id="2e096-136">Content-Type</span></span> | <span data-ttu-id="2e096-137">문자열</span><span class="sxs-lookup"><span data-stu-id="2e096-137">string</span></span> | <span data-ttu-id="2e096-138">application/json</span><span class="sxs-lookup"><span data-stu-id="2e096-138">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="2e096-139">요청 본문</span><span class="sxs-lookup"><span data-stu-id="2e096-139">Request body</span></span>
<span data-ttu-id="2e096-140">요청 본문에 다음 매개 변수를 사용하여 JSON 개체를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2e096-140">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="2e096-141">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2e096-141">Parameter</span></span> | <span data-ttu-id="2e096-142">유형</span><span class="sxs-lookup"><span data-stu-id="2e096-142">Type</span></span>    | <span data-ttu-id="2e096-143">설명</span><span class="sxs-lookup"><span data-stu-id="2e096-143">Description</span></span>
:---|:---|:---
<span data-ttu-id="2e096-144">Comment</span><span class="sxs-lookup"><span data-stu-id="2e096-144">Comment</span></span> |   <span data-ttu-id="2e096-145">String</span><span class="sxs-lookup"><span data-stu-id="2e096-145">String</span></span> | <span data-ttu-id="2e096-146">작업과 연결되는 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="2e096-146">Comment to associate with the action.</span></span> <span data-ttu-id="2e096-147">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="2e096-147">**Required**.</span></span>
<span data-ttu-id="2e096-148">ScanType</span><span class="sxs-lookup"><span data-stu-id="2e096-148">ScanType</span></span>|   <span data-ttu-id="2e096-149">문자열</span><span class="sxs-lookup"><span data-stu-id="2e096-149">String</span></span>  | <span data-ttu-id="2e096-150">스캔 유형을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2e096-150">Defines the type of the Scan.</span></span> <span data-ttu-id="2e096-151">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="2e096-151">**Required**.</span></span>

<span data-ttu-id="2e096-152">**ScanType은** 수행할 검사 유형을 제어하며 다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e096-152">**ScanType** controls the type of scan to perform and can be one of the following:</span></span>

- <span data-ttu-id="2e096-153">**빠른** – 장치에서 빠른 검사 수행</span><span class="sxs-lookup"><span data-stu-id="2e096-153">**Quick** – Perform quick scan on the device</span></span>
- <span data-ttu-id="2e096-154">**전체** – 장치에서 전체 검사 수행</span><span class="sxs-lookup"><span data-stu-id="2e096-154">**Full** – Perform full scan on the device</span></span>



## <a name="response"></a><span data-ttu-id="2e096-155">응답</span><span class="sxs-lookup"><span data-stu-id="2e096-155">Response</span></span>
<span data-ttu-id="2e096-156">성공하면 이 메서드는 응답 본문에 201, 만든 응답 코드 및 _MachineAction_ 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="2e096-156">If successful, this method returns 201, Created response code and _MachineAction_ object in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="2e096-157">예제</span><span class="sxs-lookup"><span data-stu-id="2e096-157">Example</span></span>

<span data-ttu-id="2e096-158">**요청**</span><span class="sxs-lookup"><span data-stu-id="2e096-158">**Request**</span></span>

<span data-ttu-id="2e096-159">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="2e096-159">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/runAntiVirusScan 
```

```json
{
  "Comment": "Check machine for viruses due to alert 3212",
  "ScanType": "Full"
}
```

