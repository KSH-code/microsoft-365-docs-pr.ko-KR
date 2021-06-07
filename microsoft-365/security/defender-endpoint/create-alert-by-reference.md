---
title: 이벤트 API에서 경고 만들기
description: 경고 만들기 API를 사용하여 끝점용 Microsoft Defender의 이벤트 위에 새 경고를 만드는 방법을 학습합니다.
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
ms.openlocfilehash: 8b05dde015bc96e1ccd3f80e25c416a371e03199
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772392"
---
# <a name="create-alert-api"></a><span data-ttu-id="866f7-104">경고 API 만들기</span><span class="sxs-lookup"><span data-stu-id="866f7-104">Create alert API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="866f7-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="866f7-105">**Applies to:**</span></span>
- [<span data-ttu-id="866f7-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="866f7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="866f7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="866f7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

- <span data-ttu-id="866f7-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="866f7-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="866f7-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="866f7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="866f7-110">API 설명</span><span class="sxs-lookup"><span data-stu-id="866f7-110">API description</span></span>
<span data-ttu-id="866f7-111">이벤트 의 [맨](alerts.md) 위에 새 **경고를 만듭니다.**</span><span class="sxs-lookup"><span data-stu-id="866f7-111">Creates new [Alert](alerts.md) on top of **Event**.</span></span>
<br><span data-ttu-id="866f7-112">**경고를 생성하려면 Microsoft Defender for Endpoint** 이벤트가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="866f7-112">**Microsoft Defender for Endpoint Event** is required for the alert creation.</span></span>
<br><span data-ttu-id="866f7-113">요청에서 이벤트의 매개 변수 3개(이벤트 **시간,** 컴퓨터 ID 및 **보고서 ID)를 제공해야 합니다.** </span><span class="sxs-lookup"><span data-stu-id="866f7-113">You will need to supply 3 parameters from the Event in the request: **Event Time**, **Machine ID** and **Report ID**.</span></span> <span data-ttu-id="866f7-114">아래 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="866f7-114">See example below.</span></span>
<br><span data-ttu-id="866f7-115">고급 헌팅 API 또는 포털에 있는 이벤트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="866f7-115">You can use an event found in Advanced Hunting API or Portal.</span></span>
<br><span data-ttu-id="866f7-116">동일한 Title을 사용하여 동일한 디바이스에 열려 있는 경고가 기존에 있는 경우 새로 만든 경고가 해당 경고와 병합됩니다.</span><span class="sxs-lookup"><span data-stu-id="866f7-116">If there existing an open alert on the same Device with the same Title, the new created alert will be merged with it.</span></span>
<br><span data-ttu-id="866f7-117">API를 통해 생성된 경고에 대한 자동 조사가 자동으로 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="866f7-117">An automatic investigation starts automatically on alerts created via the API.</span></span>


## <a name="limitations"></a><span data-ttu-id="866f7-118">제한 사항</span><span class="sxs-lookup"><span data-stu-id="866f7-118">Limitations</span></span>
1. <span data-ttu-id="866f7-119">이 API에 대한 속도 제한은 분당 15개 호출입니다.</span><span class="sxs-lookup"><span data-stu-id="866f7-119">Rate limitations for this API are 15 calls per minute.</span></span>


## <a name="permissions"></a><span data-ttu-id="866f7-120">사용 권한</span><span class="sxs-lookup"><span data-stu-id="866f7-120">Permissions</span></span>

<span data-ttu-id="866f7-121">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="866f7-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="866f7-122">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="866f7-122">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="866f7-123">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="866f7-123">Permission type</span></span> |   <span data-ttu-id="866f7-124">사용 권한</span><span class="sxs-lookup"><span data-stu-id="866f7-124">Permission</span></span>  |   <span data-ttu-id="866f7-125">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="866f7-125">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="866f7-126">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="866f7-126">Application</span></span> |   <span data-ttu-id="866f7-127">Alerts.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="866f7-127">Alerts.ReadWrite.All</span></span> |  <span data-ttu-id="866f7-128">'모든 경고 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="866f7-128">'Read and write all alerts'</span></span>
<span data-ttu-id="866f7-129">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="866f7-129">Delegated (work or school account)</span></span> | <span data-ttu-id="866f7-130">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="866f7-130">Alert.ReadWrite</span></span> | <span data-ttu-id="866f7-131">'경고 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="866f7-131">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="866f7-132">사용자 자격 증명을 사용하여 토큰을 얻을 때:</span><span class="sxs-lookup"><span data-stu-id="866f7-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="866f7-133">사용자에게 최소한 '경고 조사'와 같은 역할 권한이 필요합니다(자세한 내용은 역할 [만들기](user-roles.md) 및 관리 참조).</span><span class="sxs-lookup"><span data-stu-id="866f7-133">The user needs to have at least the following role permission: 'Alerts investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="866f7-134">사용자는 장치 그룹 설정에 따라 경고와 연결된 장치에 액세스할 수 있습니다(자세한 내용은 장치 그룹 만들기 및 [관리](machine-groups.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="866f7-134">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="866f7-135">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="866f7-135">HTTP request</span></span>

```
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

## <a name="request-headers"></a><span data-ttu-id="866f7-136">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="866f7-136">Request headers</span></span>

<span data-ttu-id="866f7-137">이름</span><span class="sxs-lookup"><span data-stu-id="866f7-137">Name</span></span> | <span data-ttu-id="866f7-138">유형</span><span class="sxs-lookup"><span data-stu-id="866f7-138">Type</span></span> | <span data-ttu-id="866f7-139">설명</span><span class="sxs-lookup"><span data-stu-id="866f7-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="866f7-140">권한 부여</span><span class="sxs-lookup"><span data-stu-id="866f7-140">Authorization</span></span> | <span data-ttu-id="866f7-141">String</span><span class="sxs-lookup"><span data-stu-id="866f7-141">String</span></span> | <span data-ttu-id="866f7-142">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="866f7-142">Bearer {token}.</span></span> <span data-ttu-id="866f7-143">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="866f7-143">**Required**.</span></span>
<span data-ttu-id="866f7-144">Content-Type</span><span class="sxs-lookup"><span data-stu-id="866f7-144">Content-Type</span></span> | <span data-ttu-id="866f7-145">String</span><span class="sxs-lookup"><span data-stu-id="866f7-145">String</span></span> | <span data-ttu-id="866f7-146">application/json.</span><span class="sxs-lookup"><span data-stu-id="866f7-146">application/json.</span></span> <span data-ttu-id="866f7-147">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="866f7-147">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="866f7-148">요청 본문</span><span class="sxs-lookup"><span data-stu-id="866f7-148">Request body</span></span>

<span data-ttu-id="866f7-149">요청 본문에 다음 값을 제공합니다(모두 필수).</span><span class="sxs-lookup"><span data-stu-id="866f7-149">In the request body, supply the following values (all are required):</span></span>

<span data-ttu-id="866f7-150">속성</span><span class="sxs-lookup"><span data-stu-id="866f7-150">Property</span></span> | <span data-ttu-id="866f7-151">유형</span><span class="sxs-lookup"><span data-stu-id="866f7-151">Type</span></span> | <span data-ttu-id="866f7-152">설명</span><span class="sxs-lookup"><span data-stu-id="866f7-152">Description</span></span>
:---|:---|:---
<span data-ttu-id="866f7-153">eventTime</span><span class="sxs-lookup"><span data-stu-id="866f7-153">eventTime</span></span> | <span data-ttu-id="866f7-154">DateTime(UTC)</span><span class="sxs-lookup"><span data-stu-id="866f7-154">DateTime(UTC)</span></span> | <span data-ttu-id="866f7-155">고급 헌팅에서 얻은 이벤트의 정확한 시간(문자열)입니다.</span><span class="sxs-lookup"><span data-stu-id="866f7-155">The precise time of the event as string, as obtained from advanced hunting.</span></span> <span data-ttu-id="866f7-156">예: 필수 ```2018-08-03T16:45:21.7115183Z``` .</span><span class="sxs-lookup"><span data-stu-id="866f7-156">e.g. ```2018-08-03T16:45:21.7115183Z``` **Required**.</span></span>
<span data-ttu-id="866f7-157">reportId</span><span class="sxs-lookup"><span data-stu-id="866f7-157">reportId</span></span> | <span data-ttu-id="866f7-158">String</span><span class="sxs-lookup"><span data-stu-id="866f7-158">String</span></span> | <span data-ttu-id="866f7-159">고급 헌팅에서 얻은 이벤트의 reportId입니다.</span><span class="sxs-lookup"><span data-stu-id="866f7-159">The reportId of the event, as obtained from advanced hunting.</span></span> <span data-ttu-id="866f7-160">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="866f7-160">**Required**.</span></span>
<span data-ttu-id="866f7-161">machineId</span><span class="sxs-lookup"><span data-stu-id="866f7-161">machineId</span></span> | <span data-ttu-id="866f7-162">String</span><span class="sxs-lookup"><span data-stu-id="866f7-162">String</span></span> | <span data-ttu-id="866f7-163">이벤트를 식별한 장치의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="866f7-163">Id of the device on which the event was identified.</span></span> <span data-ttu-id="866f7-164">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="866f7-164">**Required**.</span></span>
<span data-ttu-id="866f7-165">심각도</span><span class="sxs-lookup"><span data-stu-id="866f7-165">severity</span></span> | <span data-ttu-id="866f7-166">String</span><span class="sxs-lookup"><span data-stu-id="866f7-166">String</span></span> | <span data-ttu-id="866f7-167">경고의 심각도입니다.</span><span class="sxs-lookup"><span data-stu-id="866f7-167">Severity of the alert.</span></span> <span data-ttu-id="866f7-168">속성 값은 'Low', 'Medium' 및 'High'입니다.</span><span class="sxs-lookup"><span data-stu-id="866f7-168">The property values are: 'Low', 'Medium' and 'High'.</span></span> <span data-ttu-id="866f7-169">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="866f7-169">**Required**.</span></span>
<span data-ttu-id="866f7-170">title</span><span class="sxs-lookup"><span data-stu-id="866f7-170">title</span></span> | <span data-ttu-id="866f7-171">String</span><span class="sxs-lookup"><span data-stu-id="866f7-171">String</span></span> | <span data-ttu-id="866f7-172">경고의 제목입니다.</span><span class="sxs-lookup"><span data-stu-id="866f7-172">Title for the alert.</span></span> <span data-ttu-id="866f7-173">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="866f7-173">**Required**.</span></span>
<span data-ttu-id="866f7-174">설명</span><span class="sxs-lookup"><span data-stu-id="866f7-174">description</span></span> | <span data-ttu-id="866f7-175">String</span><span class="sxs-lookup"><span data-stu-id="866f7-175">String</span></span> | <span data-ttu-id="866f7-176">경고에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="866f7-176">Description of the alert.</span></span> <span data-ttu-id="866f7-177">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="866f7-177">**Required**.</span></span>
<span data-ttu-id="866f7-178">recommendedAction</span><span class="sxs-lookup"><span data-stu-id="866f7-178">recommendedAction</span></span>| <span data-ttu-id="866f7-179">String</span><span class="sxs-lookup"><span data-stu-id="866f7-179">String</span></span> | <span data-ttu-id="866f7-180">경고를 분석할 때 보안 담당자가 권장하는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="866f7-180">Action that is recommended to be taken by security officer when analyzing the alert.</span></span> <span data-ttu-id="866f7-181">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="866f7-181">**Required**.</span></span>
<span data-ttu-id="866f7-182">category</span><span class="sxs-lookup"><span data-stu-id="866f7-182">category</span></span>| <span data-ttu-id="866f7-183">String</span><span class="sxs-lookup"><span data-stu-id="866f7-183">String</span></span> | <span data-ttu-id="866f7-184">경고 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="866f7-184">Category of the alert.</span></span> <span data-ttu-id="866f7-185">속성 값은 "General", "CommandAndControl", "Collection", "CredentialAccess", "DefenseEvasion", "Discovery", "Exfiltration", "Exploit", "Execution", "InitialAccess", "LateralMovement", "Malware", "Persistence", "PrivilegeEscalation", "Ransomware", "SuspiciousActivity" **Required입니다.**</span><span class="sxs-lookup"><span data-stu-id="866f7-185">The property values are: "General", "CommandAndControl", "Collection", "CredentialAccess", "DefenseEvasion", "Discovery", "Exfiltration", "Exploit", "Execution", "InitialAccess", "LateralMovement", "Malware", "Persistence", "PrivilegeEscalation", "Ransomware", "SuspiciousActivity" **Required**.</span></span>

## <a name="response"></a><span data-ttu-id="866f7-186">응답</span><span class="sxs-lookup"><span data-stu-id="866f7-186">Response</span></span>

<span data-ttu-id="866f7-187">성공하면 이 메서드는 200 OK를 [](alerts.md) 반환하고 응답 본문에 새 경고 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="866f7-187">If successful, this method returns 200 OK, and a new [alert](alerts.md) object in the response body.</span></span> <span data-ttu-id="866f7-188">지정된 _속성(reportId,_ _eventTime_ 및 _machineId)이_ 있는 이벤트를 찾을 수 없는 경우 - 404 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="866f7-188">If event with the specified properties (_reportId_, _eventTime_ and _machineId_) was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="866f7-189">예시</span><span class="sxs-lookup"><span data-stu-id="866f7-189">Example</span></span>

<span data-ttu-id="866f7-190">**요청**</span><span class="sxs-lookup"><span data-stu-id="866f7-190">**Request**</span></span>

<span data-ttu-id="866f7-191">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="866f7-191">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

```json
{
    "machineId": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
    "severity": "Low",
    "title": "example",
    "description": "example alert",
    "recommendedAction": "nothing",
    "eventTime": "2018-08-03T16:45:21.7115183Z",
    "reportId": "20776",
    "category": "Exploit"
}
```
