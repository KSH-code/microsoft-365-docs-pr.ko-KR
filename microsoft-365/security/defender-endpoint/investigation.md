---
title: 조사 리소스 유형
description: 끝점 조사 엔터티용 Microsoft Defender.
keywords: api, 그래프 api, 지원되는 api, get, 경고, 조사
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 3872976717a5b472ab8d471db7eff9975dbc2258
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587686"
---
# <a name="investigation-resource-type"></a><span data-ttu-id="09a55-104">조사 리소스 유형</span><span class="sxs-lookup"><span data-stu-id="09a55-104">Investigation resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="09a55-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="09a55-105">**Applies to:**</span></span>
- <span data-ttu-id="09a55-106">[엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037) </span><span class="sxs-lookup"><span data-stu-id="09a55-106">[Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>
- [<span data-ttu-id="09a55-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="09a55-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="09a55-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="09a55-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="09a55-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="09a55-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="09a55-110">끝점용 Defender의 자동화된 조사 엔터티를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="09a55-110">Represent an Automated Investigation entity in Defender for Endpoint.</span></span>
<br> <span data-ttu-id="09a55-111">자세한 [내용은 자동화된](automated-investigations.md) 조사 개요를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="09a55-111">See [Overview of automated investigations](automated-investigations.md) for more information.</span></span>

## <a name="methods"></a><span data-ttu-id="09a55-112">메서드</span><span class="sxs-lookup"><span data-stu-id="09a55-112">Methods</span></span>
<span data-ttu-id="09a55-113">메서드</span><span class="sxs-lookup"><span data-stu-id="09a55-113">Method</span></span>|<span data-ttu-id="09a55-114">반환 형식</span><span class="sxs-lookup"><span data-stu-id="09a55-114">Return Type</span></span> |<span data-ttu-id="09a55-115">설명</span><span class="sxs-lookup"><span data-stu-id="09a55-115">Description</span></span>
:---|:---|:---
[<span data-ttu-id="09a55-116">조사 목록</span><span class="sxs-lookup"><span data-stu-id="09a55-116">List Investigations</span></span>](get-investigation-collection.md) | <span data-ttu-id="09a55-117">조사 컬렉션</span><span class="sxs-lookup"><span data-stu-id="09a55-117">Investigation collection</span></span> | <span data-ttu-id="09a55-118">조사 컬렉션을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="09a55-118">Get collection of Investigation</span></span>
[<span data-ttu-id="09a55-119">단일 조사하기</span><span class="sxs-lookup"><span data-stu-id="09a55-119">Get single Investigation</span></span>](get-investigation-object.md) | <span data-ttu-id="09a55-120">조사 엔터티</span><span class="sxs-lookup"><span data-stu-id="09a55-120">Investigation entity</span></span> | <span data-ttu-id="09a55-121">단일 조사 엔터티를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="09a55-121">Gets single Investigation entity.</span></span>
[<span data-ttu-id="09a55-122">조사 시작</span><span class="sxs-lookup"><span data-stu-id="09a55-122">Start Investigation</span></span>](initiate-autoir-investigation.md) | <span data-ttu-id="09a55-123">조사 엔터티</span><span class="sxs-lookup"><span data-stu-id="09a55-123">Investigation entity</span></span> | <span data-ttu-id="09a55-124">장치에서 조사를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="09a55-124">Starts Investigation on a device.</span></span>


## <a name="properties"></a><span data-ttu-id="09a55-125">속성</span><span class="sxs-lookup"><span data-stu-id="09a55-125">Properties</span></span>
<span data-ttu-id="09a55-126">속성</span><span class="sxs-lookup"><span data-stu-id="09a55-126">Property</span></span> |  <span data-ttu-id="09a55-127">유형</span><span class="sxs-lookup"><span data-stu-id="09a55-127">Type</span></span>    |   <span data-ttu-id="09a55-128">설명</span><span class="sxs-lookup"><span data-stu-id="09a55-128">Description</span></span>
:---|:---|:---
<span data-ttu-id="09a55-129">id</span><span class="sxs-lookup"><span data-stu-id="09a55-129">id</span></span> | <span data-ttu-id="09a55-130">문자열</span><span class="sxs-lookup"><span data-stu-id="09a55-130">String</span></span> | <span data-ttu-id="09a55-131">조사 엔터티의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="09a55-131">Identity of the investigation entity.</span></span> 
<span data-ttu-id="09a55-132">startTime</span><span class="sxs-lookup"><span data-stu-id="09a55-132">startTime</span></span> | <span data-ttu-id="09a55-133">DateTime Nullable</span><span class="sxs-lookup"><span data-stu-id="09a55-133">DateTime Nullable</span></span> | <span data-ttu-id="09a55-134">조사를 만든 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="09a55-134">The date and time when the investigation was created.</span></span> 
<span data-ttu-id="09a55-135">endTime</span><span class="sxs-lookup"><span data-stu-id="09a55-135">endTime</span></span> | <span data-ttu-id="09a55-136">DateTime Nullable</span><span class="sxs-lookup"><span data-stu-id="09a55-136">DateTime Nullable</span></span> | <span data-ttu-id="09a55-137">조사가 완료된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="09a55-137">The date and time when the investigation was completed.</span></span> 
<span data-ttu-id="09a55-138">cancelledBy</span><span class="sxs-lookup"><span data-stu-id="09a55-138">cancelledBy</span></span> | <span data-ttu-id="09a55-139">문자열</span><span class="sxs-lookup"><span data-stu-id="09a55-139">String</span></span> | <span data-ttu-id="09a55-140">해당 조사를 취소한 사용자/응용 프로그램의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="09a55-140">The ID of the user/application that canceled that investigation.</span></span> 
<span data-ttu-id="09a55-141">investigationState</span><span class="sxs-lookup"><span data-stu-id="09a55-141">investigationState</span></span> | <span data-ttu-id="09a55-142">Enum</span><span class="sxs-lookup"><span data-stu-id="09a55-142">Enum</span></span> | <span data-ttu-id="09a55-143">조사의 현재 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="09a55-143">The current state of the investigation.</span></span> <span data-ttu-id="09a55-144">가능한 값은 '알 수 없음', 'Terminated', 'SuccessfullyRemediated', 'Benign', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.</span><span class="sxs-lookup"><span data-stu-id="09a55-144">Possible values are: 'Unknown', 'Terminated', 'SuccessfullyRemediated', 'Benign', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.</span></span>
<span data-ttu-id="09a55-145">statusDetails</span><span class="sxs-lookup"><span data-stu-id="09a55-145">statusDetails</span></span> | <span data-ttu-id="09a55-146">문자열</span><span class="sxs-lookup"><span data-stu-id="09a55-146">String</span></span> | <span data-ttu-id="09a55-147">조사 상태 관련 추가 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="09a55-147">Additional information about the state of the investigation.</span></span>
<span data-ttu-id="09a55-148">machineId</span><span class="sxs-lookup"><span data-stu-id="09a55-148">machineId</span></span> | <span data-ttu-id="09a55-149">문자열</span><span class="sxs-lookup"><span data-stu-id="09a55-149">String</span></span> | <span data-ttu-id="09a55-150">조사가 실행되는 장치의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="09a55-150">The ID of the device on which the investigation is executed.</span></span>
<span data-ttu-id="09a55-151">computerDnsName</span><span class="sxs-lookup"><span data-stu-id="09a55-151">computerDnsName</span></span> | <span data-ttu-id="09a55-152">문자열</span><span class="sxs-lookup"><span data-stu-id="09a55-152">String</span></span> | <span data-ttu-id="09a55-153">조사가 실행되는 장치의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="09a55-153">The name of the device on which the investigation is executed.</span></span>
<span data-ttu-id="09a55-154">triggeringAlertId</span><span class="sxs-lookup"><span data-stu-id="09a55-154">triggeringAlertId</span></span> | <span data-ttu-id="09a55-155">문자열</span><span class="sxs-lookup"><span data-stu-id="09a55-155">String</span></span> | <span data-ttu-id="09a55-156">조사를 트리거한 경고의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="09a55-156">The ID of the alert that triggered the investigation.</span></span>


## <a name="json-representation"></a><span data-ttu-id="09a55-157">Json 표현</span><span class="sxs-lookup"><span data-stu-id="09a55-157">Json representation</span></span>

```json
{
    "id": "63004",
    "startTime": "2020-01-06T13:05:15Z",
    "endTime": null,
    "state": "Running",
    "cancelledBy": null,
    "statusDetails": null,
    "machineId": "e828a0624ed33f919db541065190d2f75e50a071",
    "computerDnsName": "desktop-test123",
    "triggeringAlertId": "da637139127150012465_1011995739"
}
```
