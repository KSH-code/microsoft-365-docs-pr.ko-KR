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
ms.openlocfilehash: ac149ca7263b8ef8bb37a7dd18bf0787a3114b37
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201306"
---
# <a name="incident-resource-type"></a><span data-ttu-id="1409e-104">문제 리소스 종류</span><span class="sxs-lookup"><span data-stu-id="1409e-104">Incident resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1409e-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="1409e-105">**Applies to:**</span></span>
- <span data-ttu-id="1409e-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="1409e-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="1409e-107">일부 정보는 상업적으로 출시 되기 전에 크게 수정 될 수 있는 prereleased 제품과 관련 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1409e-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="1409e-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="1409e-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="methods"></a><span data-ttu-id="1409e-109">메서드</span><span class="sxs-lookup"><span data-stu-id="1409e-109">Methods</span></span>

<span data-ttu-id="1409e-110">메서드</span><span class="sxs-lookup"><span data-stu-id="1409e-110">Method</span></span> |<span data-ttu-id="1409e-111">반환 형식</span><span class="sxs-lookup"><span data-stu-id="1409e-111">Return Type</span></span> |<span data-ttu-id="1409e-112">설명</span><span class="sxs-lookup"><span data-stu-id="1409e-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="1409e-113">인시던트 열거</span><span class="sxs-lookup"><span data-stu-id="1409e-113">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="1409e-114">[인시던트](api-incident.md) 목록</span><span class="sxs-lookup"><span data-stu-id="1409e-114">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="1409e-115">인시던트 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1409e-115">Get a list of incidents.</span></span>
[<span data-ttu-id="1409e-116">인시던트 업데이트</span><span class="sxs-lookup"><span data-stu-id="1409e-116">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="1409e-117">문제점</span><span class="sxs-lookup"><span data-stu-id="1409e-117">Incident</span></span>](api-incident.md) | <span data-ttu-id="1409e-118">특정 인시던트를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="1409e-118">Update specific incident.</span></span>


## <a name="properties"></a><span data-ttu-id="1409e-119">속성</span><span class="sxs-lookup"><span data-stu-id="1409e-119">Properties</span></span>

<span data-ttu-id="1409e-120">속성</span><span class="sxs-lookup"><span data-stu-id="1409e-120">Property</span></span> |    <span data-ttu-id="1409e-121">유형</span><span class="sxs-lookup"><span data-stu-id="1409e-121">Type</span></span>    |    <span data-ttu-id="1409e-122">설명</span><span class="sxs-lookup"><span data-stu-id="1409e-122">Description</span></span>
:---|:---|:---
<span data-ttu-id="1409e-123">incidentId</span><span class="sxs-lookup"><span data-stu-id="1409e-123">incidentId</span></span> | <span data-ttu-id="1409e-124">long</span><span class="sxs-lookup"><span data-stu-id="1409e-124">long</span></span> | <span data-ttu-id="1409e-125">인시던트 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="1409e-125">Incident unique ID.</span></span>
<span data-ttu-id="1409e-126">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="1409e-126">redirectIncidentId</span></span> | <span data-ttu-id="1409e-127">nullable long</span><span class="sxs-lookup"><span data-stu-id="1409e-127">nullable long</span></span> | <span data-ttu-id="1409e-128">현재 인시던트가 병합 된 인시던트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="1409e-128">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="1409e-129">incidentName</span><span class="sxs-lookup"><span data-stu-id="1409e-129">incidentName</span></span> | <span data-ttu-id="1409e-130">문자열</span><span class="sxs-lookup"><span data-stu-id="1409e-130">string</span></span> | <span data-ttu-id="1409e-131">인시던트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1409e-131">The name of the Incident.</span></span>
<span data-ttu-id="1409e-132">createdTime</span><span class="sxs-lookup"><span data-stu-id="1409e-132">createdTime</span></span> | <span data-ttu-id="1409e-133">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="1409e-133">DateTimeOffset</span></span> | <span data-ttu-id="1409e-134">인시던트가 만들어진 날짜 및 시간 (UTC)입니다.</span><span class="sxs-lookup"><span data-stu-id="1409e-134">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="1409e-135">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="1409e-135">lastUpdateTime</span></span> | <span data-ttu-id="1409e-136">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="1409e-136">DateTimeOffset</span></span> | <span data-ttu-id="1409e-137">인시던트가 마지막으로 업데이트 된 날짜 및 시간 (UTC)입니다.</span><span class="sxs-lookup"><span data-stu-id="1409e-137">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="1409e-138">assignedTo</span><span class="sxs-lookup"><span data-stu-id="1409e-138">assignedTo</span></span> | <span data-ttu-id="1409e-139">문자열</span><span class="sxs-lookup"><span data-stu-id="1409e-139">string</span></span> | <span data-ttu-id="1409e-140">인시던트의 소유자입니다.</span><span class="sxs-lookup"><span data-stu-id="1409e-140">Owner of the Incident.</span></span>
<span data-ttu-id="1409e-141">이상인</span><span class="sxs-lookup"><span data-stu-id="1409e-141">severity</span></span> | <span data-ttu-id="1409e-142">열거할</span><span class="sxs-lookup"><span data-stu-id="1409e-142">Enum</span></span> | <span data-ttu-id="1409e-143">인시던트의 심각도입니다.</span><span class="sxs-lookup"><span data-stu-id="1409e-143">Severity of the Incident.</span></span> <span data-ttu-id="1409e-144">가능한 값은 ```UnSpecified``` , ```Informational``` , ```Low``` ```Medium``` 및 ```High``` 입니다.</span><span class="sxs-lookup"><span data-stu-id="1409e-144">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium``` and ```High```.</span></span>
<span data-ttu-id="1409e-145">상태별</span><span class="sxs-lookup"><span data-stu-id="1409e-145">status</span></span> | <span data-ttu-id="1409e-146">열거할</span><span class="sxs-lookup"><span data-stu-id="1409e-146">Enum</span></span> | <span data-ttu-id="1409e-147">인시던트의 현재 상태를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1409e-147">Specifies the current status of the incident.</span></span> <span data-ttu-id="1409e-148">가능한 값은 ```Active``` ```Resolved``` 및 ```Redirected``` 입니다.</span><span class="sxs-lookup"><span data-stu-id="1409e-148">Possible values are: ```Active```, ```Resolved``` and ```Redirected```.</span></span>
<span data-ttu-id="1409e-149">유형을</span><span class="sxs-lookup"><span data-stu-id="1409e-149">classification</span></span> | <span data-ttu-id="1409e-150">열거할</span><span class="sxs-lookup"><span data-stu-id="1409e-150">Enum</span></span> | <span data-ttu-id="1409e-151">인시던트 사양입니다.</span><span class="sxs-lookup"><span data-stu-id="1409e-151">Specification of the incident.</span></span> <span data-ttu-id="1409e-152">가능한 값은 ```Unknown``` , ```FalsePositive``` 및 ```TruePositive``` 입니다.</span><span class="sxs-lookup"><span data-stu-id="1409e-152">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="1409e-153">가져옴을</span><span class="sxs-lookup"><span data-stu-id="1409e-153">determination</span></span> | <span data-ttu-id="1409e-154">열거할</span><span class="sxs-lookup"><span data-stu-id="1409e-154">Enum</span></span> | <span data-ttu-id="1409e-155">문제에 대 한 결정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1409e-155">Specifies the determination of the incident.</span></span> <span data-ttu-id="1409e-156">가능한 값은 ```NotAvailable``` ,, ```Apt``` ```Malware``` , ```SecurityPersonnel``` , ```SecurityTesting``` , ```UnwantedSoftware``` , ```Other``` 입니다.</span><span class="sxs-lookup"><span data-stu-id="1409e-156">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="1409e-157">사이</span><span class="sxs-lookup"><span data-stu-id="1409e-157">tags</span></span> | <span data-ttu-id="1409e-158">문자열 목록</span><span class="sxs-lookup"><span data-stu-id="1409e-158">string List</span></span> | <span data-ttu-id="1409e-159">인시던트 태그의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="1409e-159">List of Incident tags.</span></span>
<span data-ttu-id="1409e-160">경고가</span><span class="sxs-lookup"><span data-stu-id="1409e-160">alerts</span></span> | <span data-ttu-id="1409e-161">알림 목록</span><span class="sxs-lookup"><span data-stu-id="1409e-161">Alert List</span></span> | <span data-ttu-id="1409e-162">관련 경고 목록</span><span class="sxs-lookup"><span data-stu-id="1409e-162">List of related alerts.</span></span> <span data-ttu-id="1409e-163">[List 인시던트](api-list-incidents.md) API 설명서의 예를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1409e-163">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>
