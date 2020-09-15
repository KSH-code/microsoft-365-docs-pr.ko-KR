---
title: Microsoft Threat Protection API의 문제 리소스 종류
description: Microsoft Threat Protection에서 문제 리소스 유형의 방법 및 속성에 대해 자세히 알아보기
keywords: 인시던트, 사건, api
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 310e3105c973223ea79373d770eb10f7753b917e
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650456"
---
# <a name="incident-resource-type"></a><span data-ttu-id="f59ac-104">문제 리소스 종류</span><span class="sxs-lookup"><span data-stu-id="f59ac-104">Incident resource type</span></span>

<span data-ttu-id="f59ac-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="f59ac-105">**Applies to:**</span></span>
- <span data-ttu-id="f59ac-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="f59ac-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="f59ac-107">일부 정보는 상업적으로 출시 되기 전에 크게 수정 될 수 있는 prereleased 제품과 관련 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f59ac-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="f59ac-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="f59ac-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="methods"></a><span data-ttu-id="f59ac-109">메서드</span><span class="sxs-lookup"><span data-stu-id="f59ac-109">Methods</span></span>

<span data-ttu-id="f59ac-110">메서드</span><span class="sxs-lookup"><span data-stu-id="f59ac-110">Method</span></span> |<span data-ttu-id="f59ac-111">반환 형식</span><span class="sxs-lookup"><span data-stu-id="f59ac-111">Return Type</span></span> |<span data-ttu-id="f59ac-112">설명</span><span class="sxs-lookup"><span data-stu-id="f59ac-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="f59ac-113">인시던트 목록</span><span class="sxs-lookup"><span data-stu-id="f59ac-113">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="f59ac-114">[인시던트](api-incident.md) 목록</span><span class="sxs-lookup"><span data-stu-id="f59ac-114">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="f59ac-115">인시던트 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f59ac-115">Get a list of incidents.</span></span>
[<span data-ttu-id="f59ac-116">인시던트 업데이트</span><span class="sxs-lookup"><span data-stu-id="f59ac-116">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="f59ac-117">문제점</span><span class="sxs-lookup"><span data-stu-id="f59ac-117">Incident</span></span>](api-incident.md) | <span data-ttu-id="f59ac-118">특정 인시던트를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="f59ac-118">Update specific incident.</span></span>


## <a name="properties"></a><span data-ttu-id="f59ac-119">속성</span><span class="sxs-lookup"><span data-stu-id="f59ac-119">Properties</span></span>

<span data-ttu-id="f59ac-120">속성</span><span class="sxs-lookup"><span data-stu-id="f59ac-120">Property</span></span> |    <span data-ttu-id="f59ac-121">유형</span><span class="sxs-lookup"><span data-stu-id="f59ac-121">Type</span></span>    |    <span data-ttu-id="f59ac-122">설명</span><span class="sxs-lookup"><span data-stu-id="f59ac-122">Description</span></span>
:---|:---|:---
<span data-ttu-id="f59ac-123">incidentId</span><span class="sxs-lookup"><span data-stu-id="f59ac-123">incidentId</span></span> | <span data-ttu-id="f59ac-124">long</span><span class="sxs-lookup"><span data-stu-id="f59ac-124">long</span></span> | <span data-ttu-id="f59ac-125">인시던트 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="f59ac-125">Incident unique ID.</span></span>
<span data-ttu-id="f59ac-126">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="f59ac-126">redirectIncidentId</span></span> | <span data-ttu-id="f59ac-127">nullable long</span><span class="sxs-lookup"><span data-stu-id="f59ac-127">nullable long</span></span> | <span data-ttu-id="f59ac-128">현재 인시던트가 병합 된 인시던트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="f59ac-128">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="f59ac-129">incidentName</span><span class="sxs-lookup"><span data-stu-id="f59ac-129">incidentName</span></span> | <span data-ttu-id="f59ac-130">문자열</span><span class="sxs-lookup"><span data-stu-id="f59ac-130">string</span></span> | <span data-ttu-id="f59ac-131">인시던트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f59ac-131">The name of the Incident.</span></span>
<span data-ttu-id="f59ac-132">createdTime</span><span class="sxs-lookup"><span data-stu-id="f59ac-132">createdTime</span></span> | <span data-ttu-id="f59ac-133">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="f59ac-133">DateTimeOffset</span></span> | <span data-ttu-id="f59ac-134">인시던트가 만들어진 날짜 및 시간 (UTC)입니다.</span><span class="sxs-lookup"><span data-stu-id="f59ac-134">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="f59ac-135">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="f59ac-135">lastUpdateTime</span></span> | <span data-ttu-id="f59ac-136">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="f59ac-136">DateTimeOffset</span></span> | <span data-ttu-id="f59ac-137">인시던트가 마지막으로 업데이트 된 날짜 및 시간 (UTC)입니다.</span><span class="sxs-lookup"><span data-stu-id="f59ac-137">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="f59ac-138">assignedTo</span><span class="sxs-lookup"><span data-stu-id="f59ac-138">assignedTo</span></span> | <span data-ttu-id="f59ac-139">문자열</span><span class="sxs-lookup"><span data-stu-id="f59ac-139">string</span></span> | <span data-ttu-id="f59ac-140">인시던트의 소유자입니다.</span><span class="sxs-lookup"><span data-stu-id="f59ac-140">Owner of the Incident.</span></span>
<span data-ttu-id="f59ac-141">이상인</span><span class="sxs-lookup"><span data-stu-id="f59ac-141">severity</span></span> | <span data-ttu-id="f59ac-142">열거할</span><span class="sxs-lookup"><span data-stu-id="f59ac-142">Enum</span></span> | <span data-ttu-id="f59ac-143">인시던트의 심각도입니다.</span><span class="sxs-lookup"><span data-stu-id="f59ac-143">Severity of the Incident.</span></span> <span data-ttu-id="f59ac-144">가능한 값은 ```UnSpecified``` , ```Informational``` , ```Low``` ```Medium``` 및 ```High``` 입니다.</span><span class="sxs-lookup"><span data-stu-id="f59ac-144">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium``` and ```High```.</span></span>
<span data-ttu-id="f59ac-145">상태별</span><span class="sxs-lookup"><span data-stu-id="f59ac-145">status</span></span> | <span data-ttu-id="f59ac-146">열거할</span><span class="sxs-lookup"><span data-stu-id="f59ac-146">Enum</span></span> | <span data-ttu-id="f59ac-147">인시던트의 현재 상태를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f59ac-147">Specifies the current status of the incident.</span></span> <span data-ttu-id="f59ac-148">가능한 값은 ```Active``` ```Resolved``` 및 ```Redirected``` 입니다.</span><span class="sxs-lookup"><span data-stu-id="f59ac-148">Possible values are: ```Active```, ```Resolved``` and ```Redirected```.</span></span>
<span data-ttu-id="f59ac-149">유형을</span><span class="sxs-lookup"><span data-stu-id="f59ac-149">classification</span></span> | <span data-ttu-id="f59ac-150">열거할</span><span class="sxs-lookup"><span data-stu-id="f59ac-150">Enum</span></span> | <span data-ttu-id="f59ac-151">인시던트 사양입니다.</span><span class="sxs-lookup"><span data-stu-id="f59ac-151">Specification of the incident.</span></span> <span data-ttu-id="f59ac-152">가능한 값은 ```Unknown``` , ```FalsePositive``` 및 ```TruePositive``` 입니다.</span><span class="sxs-lookup"><span data-stu-id="f59ac-152">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="f59ac-153">가져옴을</span><span class="sxs-lookup"><span data-stu-id="f59ac-153">determination</span></span> | <span data-ttu-id="f59ac-154">열거할</span><span class="sxs-lookup"><span data-stu-id="f59ac-154">Enum</span></span> | <span data-ttu-id="f59ac-155">문제에 대 한 결정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f59ac-155">Specifies the determination of the incident.</span></span> <span data-ttu-id="f59ac-156">가능한 값은 ```NotAvailable``` ,, ```Apt``` ```Malware``` , ```SecurityPersonnel``` , ```SecurityTesting``` , ```UnwantedSoftware``` , ```Other``` 입니다.</span><span class="sxs-lookup"><span data-stu-id="f59ac-156">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="f59ac-157">사이</span><span class="sxs-lookup"><span data-stu-id="f59ac-157">tags</span></span> | <span data-ttu-id="f59ac-158">문자열 목록</span><span class="sxs-lookup"><span data-stu-id="f59ac-158">string List</span></span> | <span data-ttu-id="f59ac-159">인시던트 태그의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="f59ac-159">List of Incident tags.</span></span>
<span data-ttu-id="f59ac-160">경고가</span><span class="sxs-lookup"><span data-stu-id="f59ac-160">alerts</span></span> | <span data-ttu-id="f59ac-161">알림 목록</span><span class="sxs-lookup"><span data-stu-id="f59ac-161">Alert List</span></span> | <span data-ttu-id="f59ac-162">관련 경고 목록</span><span class="sxs-lookup"><span data-stu-id="f59ac-162">List of related alerts.</span></span> <span data-ttu-id="f59ac-163">[List 인시던트](api-list-incidents.md) API 설명서의 예를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f59ac-163">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>