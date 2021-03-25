---
title: 표시기 리소스 유형
description: 엔터티 세부 정보를 지정하고 끝점용 Microsoft Defender를 사용하여 표시기 만료를 정의합니다.
keywords: api, 지원되는 api, get, TiIndicator, Indicator, recent
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
ms.openlocfilehash: bbd908c15f4d65d4923c088261c92de6d2d3cc35
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187313"
---
# <a name="indicator-resource-type"></a><span data-ttu-id="2a395-104">표시기 리소스 유형</span><span class="sxs-lookup"><span data-stu-id="2a395-104">Indicator resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2a395-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="2a395-105">**Applies to:**</span></span>
- [<span data-ttu-id="2a395-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2a395-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2a395-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2a395-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2a395-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="2a395-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2a395-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="2a395-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


- <span data-ttu-id="2a395-110">포털에서 [](https://securitycenter.windows.com/preferences2/custom_ti_indicators/files) 해당 지표 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2a395-110">See the corresponding [Indicators page](https://securitycenter.windows.com/preferences2/custom_ti_indicators/files) in the portal.</span></span> 

<span data-ttu-id="2a395-111">메서드</span><span class="sxs-lookup"><span data-stu-id="2a395-111">Method</span></span>|<span data-ttu-id="2a395-112">반환 형식</span><span class="sxs-lookup"><span data-stu-id="2a395-112">Return Type</span></span> |<span data-ttu-id="2a395-113">설명</span><span class="sxs-lookup"><span data-stu-id="2a395-113">Description</span></span>
:---|:---|:---
[<span data-ttu-id="2a395-114">목록 표시기</span><span class="sxs-lookup"><span data-stu-id="2a395-114">List Indicators</span></span>](get-ti-indicators-collection.md) | <span data-ttu-id="2a395-115">[표시기](ti-indicator.md) 컬렉션</span><span class="sxs-lookup"><span data-stu-id="2a395-115">[Indicator](ti-indicator.md) Collection</span></span> | <span data-ttu-id="2a395-116">[표시기](ti-indicator.md) 엔터티를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="2a395-116">List [Indicator](ti-indicator.md) entities.</span></span>
[<span data-ttu-id="2a395-117">제출 표시기</span><span class="sxs-lookup"><span data-stu-id="2a395-117">Submit Indicator</span></span>](post-ti-indicator.md) | [<span data-ttu-id="2a395-118">표시기</span><span class="sxs-lookup"><span data-stu-id="2a395-118">Indicator</span></span>](ti-indicator.md) | <span data-ttu-id="2a395-119">표시기 [엔터티를 제출하거나](ti-indicator.md) 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="2a395-119">Submit or update [Indicator](ti-indicator.md) entity.</span></span>
[<span data-ttu-id="2a395-120">표시기 가져오기</span><span class="sxs-lookup"><span data-stu-id="2a395-120">Import Indicators</span></span>](import-ti-indicators.md) | <span data-ttu-id="2a395-121">[표시기](ti-indicator.md) 컬렉션</span><span class="sxs-lookup"><span data-stu-id="2a395-121">[Indicator](ti-indicator.md) Collection</span></span> | <span data-ttu-id="2a395-122">표시기 [엔터티를 제출하거나](ti-indicator.md) 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="2a395-122">Submit or update [Indicators](ti-indicator.md) entities.</span></span>
[<span data-ttu-id="2a395-123">표시기 삭제</span><span class="sxs-lookup"><span data-stu-id="2a395-123">Delete Indicator</span></span>](delete-ti-indicator-by-id.md) | <span data-ttu-id="2a395-124">콘텐츠 없음</span><span class="sxs-lookup"><span data-stu-id="2a395-124">No Content</span></span> | <span data-ttu-id="2a395-125">표시기 [엔터티를](ti-indicator.md) 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="2a395-125">Deletes [Indicator](ti-indicator.md) entity.</span></span>


## <a name="properties"></a><span data-ttu-id="2a395-126">속성</span><span class="sxs-lookup"><span data-stu-id="2a395-126">Properties</span></span>
<span data-ttu-id="2a395-127">속성</span><span class="sxs-lookup"><span data-stu-id="2a395-127">Property</span></span> |  <span data-ttu-id="2a395-128">유형</span><span class="sxs-lookup"><span data-stu-id="2a395-128">Type</span></span>    |   <span data-ttu-id="2a395-129">설명</span><span class="sxs-lookup"><span data-stu-id="2a395-129">Description</span></span>
:---|:---|:---
<span data-ttu-id="2a395-130">id</span><span class="sxs-lookup"><span data-stu-id="2a395-130">id</span></span> | <span data-ttu-id="2a395-131">문자열</span><span class="sxs-lookup"><span data-stu-id="2a395-131">String</span></span> | <span data-ttu-id="2a395-132">Indicator [엔터티의 ID입니다.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="2a395-132">Identity of the [Indicator](ti-indicator.md) entity.</span></span>
<span data-ttu-id="2a395-133">indicatorValue</span><span class="sxs-lookup"><span data-stu-id="2a395-133">indicatorValue</span></span> | <span data-ttu-id="2a395-134">문자열</span><span class="sxs-lookup"><span data-stu-id="2a395-134">String</span></span> | <span data-ttu-id="2a395-135">표시기 [값입니다.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="2a395-135">The value of the [Indicator](ti-indicator.md).</span></span>
<span data-ttu-id="2a395-136">indicatorType</span><span class="sxs-lookup"><span data-stu-id="2a395-136">indicatorType</span></span> | <span data-ttu-id="2a395-137">Enum</span><span class="sxs-lookup"><span data-stu-id="2a395-137">Enum</span></span> | <span data-ttu-id="2a395-138">표시기 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="2a395-138">Type of the indicator.</span></span> <span data-ttu-id="2a395-139">가능한 값은 "FileSha1", "FileSha256", "IpAddress", "DomainName" 및 "Url"입니다.</span><span class="sxs-lookup"><span data-stu-id="2a395-139">Possible values are: "FileSha1", "FileSha256", "IpAddress", "DomainName" and "Url".</span></span>
<span data-ttu-id="2a395-140">application</span><span class="sxs-lookup"><span data-stu-id="2a395-140">application</span></span> | <span data-ttu-id="2a395-141">문자열</span><span class="sxs-lookup"><span data-stu-id="2a395-141">String</span></span> | <span data-ttu-id="2a395-142">표시기와 연결된 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="2a395-142">The application associated with the indicator.</span></span> 
<span data-ttu-id="2a395-143">조치</span><span class="sxs-lookup"><span data-stu-id="2a395-143">action</span></span> | <span data-ttu-id="2a395-144">Enum</span><span class="sxs-lookup"><span data-stu-id="2a395-144">Enum</span></span> | <span data-ttu-id="2a395-145">표시기가 조직에서 검색되는 경우 수행되는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="2a395-145">The action that will be taken if the indicator will be discovered in the organization.</span></span> <span data-ttu-id="2a395-146">가능한 값은 "Alert", "AlertAndBlock" 및 "Allowed"입니다.</span><span class="sxs-lookup"><span data-stu-id="2a395-146">Possible values are: "Alert", "AlertAndBlock", and "Allowed".</span></span>
<span data-ttu-id="2a395-147">sourceType</span><span class="sxs-lookup"><span data-stu-id="2a395-147">sourceType</span></span> | <span data-ttu-id="2a395-148">Enum</span><span class="sxs-lookup"><span data-stu-id="2a395-148">Enum</span></span> | <span data-ttu-id="2a395-149">사용자가 만든 표시기(예: 포털에서)가 API를 통해 자동화된 응용 프로그램을 사용하여 제출한 경우 "사용자"입니다.</span><span class="sxs-lookup"><span data-stu-id="2a395-149">"User" in case the Indicator created by a user (e.g. from the portal), "AadApp" in case it submitted using automated application via the API.</span></span>
<span data-ttu-id="2a395-150">source</span><span class="sxs-lookup"><span data-stu-id="2a395-150">source</span></span> | <span data-ttu-id="2a395-151">문자열</span><span class="sxs-lookup"><span data-stu-id="2a395-151">string</span></span> | <span data-ttu-id="2a395-152">표시기를 제출한 사용자/응용 프로그램의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2a395-152">The name of the user/application that submitted the indicator.</span></span>
<span data-ttu-id="2a395-153">createdBy</span><span class="sxs-lookup"><span data-stu-id="2a395-153">createdBy</span></span> | <span data-ttu-id="2a395-154">문자열</span><span class="sxs-lookup"><span data-stu-id="2a395-154">String</span></span> | <span data-ttu-id="2a395-155">표시기를 제출한 사용자/응용 프로그램의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="2a395-155">Unique identity of the user/application that submitted the indicator.</span></span>
<span data-ttu-id="2a395-156">lastUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="2a395-156">lastUpdatedBy</span></span> | <span data-ttu-id="2a395-157">문자열</span><span class="sxs-lookup"><span data-stu-id="2a395-157">String</span></span> | <span data-ttu-id="2a395-158">표시기를 마지막으로 업데이트한 사용자/응용 프로그램의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="2a395-158">Identity of the user/application that last updated the indicator.</span></span>
<span data-ttu-id="2a395-159">creationTimeDateTimeUtc</span><span class="sxs-lookup"><span data-stu-id="2a395-159">creationTimeDateTimeUtc</span></span> | <span data-ttu-id="2a395-160">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="2a395-160">DateTimeOffset</span></span> | <span data-ttu-id="2a395-161">표시기를 만든 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="2a395-161">The date and time when the indicator was created.</span></span>
<span data-ttu-id="2a395-162">expirationTime</span><span class="sxs-lookup"><span data-stu-id="2a395-162">expirationTime</span></span> | <span data-ttu-id="2a395-163">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="2a395-163">DateTimeOffset</span></span> | <span data-ttu-id="2a395-164">표시기 만료 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="2a395-164">The expiration time of the indicator.</span></span>
<span data-ttu-id="2a395-165">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="2a395-165">lastUpdateTime</span></span> | <span data-ttu-id="2a395-166">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="2a395-166">DateTimeOffset</span></span> | <span data-ttu-id="2a395-167">표시기가 마지막으로 업데이트된 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="2a395-167">The last time the indicator was updated.</span></span>
<span data-ttu-id="2a395-168">심각도</span><span class="sxs-lookup"><span data-stu-id="2a395-168">severity</span></span> | <span data-ttu-id="2a395-169">Enum</span><span class="sxs-lookup"><span data-stu-id="2a395-169">Enum</span></span> | <span data-ttu-id="2a395-170">표시기 심각도입니다.</span><span class="sxs-lookup"><span data-stu-id="2a395-170">The severity of the indicator.</span></span> <span data-ttu-id="2a395-171">가능한 값은 "Informational", "Low", "Medium" 및 "High"입니다.</span><span class="sxs-lookup"><span data-stu-id="2a395-171">possible values are: "Informational", "Low", "Medium" and "High".</span></span>
<span data-ttu-id="2a395-172">title</span><span class="sxs-lookup"><span data-stu-id="2a395-172">title</span></span> | <span data-ttu-id="2a395-173">문자열</span><span class="sxs-lookup"><span data-stu-id="2a395-173">String</span></span> | <span data-ttu-id="2a395-174">표시기 제목입니다.</span><span class="sxs-lookup"><span data-stu-id="2a395-174">Indicator title.</span></span>
<span data-ttu-id="2a395-175">설명</span><span class="sxs-lookup"><span data-stu-id="2a395-175">description</span></span> | <span data-ttu-id="2a395-176">문자열</span><span class="sxs-lookup"><span data-stu-id="2a395-176">String</span></span> | <span data-ttu-id="2a395-177">표시기 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="2a395-177">Description of the indicator.</span></span>
<span data-ttu-id="2a395-178">recommendedActions</span><span class="sxs-lookup"><span data-stu-id="2a395-178">recommendedActions</span></span> | <span data-ttu-id="2a395-179">문자열</span><span class="sxs-lookup"><span data-stu-id="2a395-179">String</span></span> | <span data-ttu-id="2a395-180">표시기를 위한 권장 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="2a395-180">Recommended actions for the indicator.</span></span>
<span data-ttu-id="2a395-181">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="2a395-181">rbacGroupNames</span></span> | <span data-ttu-id="2a395-182">문자열 목록</span><span class="sxs-lookup"><span data-stu-id="2a395-182">List of strings</span></span> | <span data-ttu-id="2a395-183">표시기가 노출되어 활성 상태인 RBAC 장치 그룹 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2a395-183">RBAC device group names where the indicator is exposed and active.</span></span> <span data-ttu-id="2a395-184">모든 장치에 노출되는 경우 빈 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="2a395-184">Empty list in case it exposed to all devices.</span></span>


## <a name="json-representation"></a><span data-ttu-id="2a395-185">Json 표현</span><span class="sxs-lookup"><span data-stu-id="2a395-185">Json representation</span></span>

```json
{
    "id": "994",
    "indicatorValue": "881c0f10c75e64ec39d257a131fcd531f47dd2cff2070ae94baa347d375126fd",
    "indicatorType": "FileSha256",
    "action": "AlertAndBlock",
    "application": null,
    "source": "user@contoso.onmicrosoft.com",
    "sourceType": "User",
    "createdBy": "user@contoso.onmicrosoft.com",
    "severity": "Informational",
    "title": "Michael test",
    "description": "test",
    "recommendedActions": "nothing",
    "creationTimeDateTimeUtc": "2019-12-19T09:09:46.9139216Z",
    "expirationTime": null,
    "lastUpdateTime": "2019-12-19T09:09:47.3358111Z",
    "lastUpdatedBy": null,
    "rbacGroupNames": ["team1"]
}
```
