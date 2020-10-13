---
title: Microsoft Threat Protection의 새로운 기능
description: Microsoft Threat Protection의 새로운 기능을 소개 합니다.
keywords: microsoft threat protection의 새로운 기능, ga, 일반적으로 사용 가능, 기능, 사용 가능, 신규
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: secure
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.openlocfilehash: 1b3cc273b61fcdff3c01b30c9ef64619a0e7a368
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430400"
---
# <a name="whats-new-in-microsoft-threat-protection"></a><span data-ttu-id="f9281-104">Microsoft Threat Protection의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="f9281-104">What's new in Microsoft Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f9281-105">일반적으로 Microsoft Threat Protection의 최신 릴리스에서는 다음 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9281-105">The following features are generally available (GA) in the latest release of Microsoft Threat Protection.</span></span>

<span data-ttu-id="f9281-106">RSS 피드: 다음 URL을 복사 하 여 피드 판독기에 붙여 넣어이 페이지를 업데이트 하면 알림을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="f9281-106">RSS feed: Get notified when this page is updated by copying and pasting the following URL into your feed reader:</span></span>
```http
https://docs.microsoft.com/api/search/rss?search=%22Lists+the+new+features+and+functionality+in+Microsoft+Threat+Protection%22&locale=en-us
```
## <a name="september-2020"></a><span data-ttu-id="f9281-107">2020년 9월</span><span class="sxs-lookup"><span data-stu-id="f9281-107">September 2020</span></span>
- [<span data-ttu-id="f9281-108">IdentityDirectoryEvents 테이블</span><span class="sxs-lookup"><span data-stu-id="f9281-108">IdentityDirectoryEvents table</span></span>](advanced-hunting-identitydirectoryevents-table.md) <br> <span data-ttu-id="f9281-109">AD (Active Directory)를 실행 하는 온-프레미스 도메인 컨트롤러를 포함 하는 이벤트를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="f9281-109">Find events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="f9281-110">이 [고급 구하기](advanced-hunting-overview.md) 스키마 테이블은 도메인 컨트롤러의 id 관련 이벤트 및 시스템 이벤트 범위를 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="f9281-110">This [advanced hunting](advanced-hunting-overview.md) schema table covers a range of identity-related events and system events on the domain controller.</span></span>
- [<span data-ttu-id="f9281-111">AssignedIPAddresses () 함수</span><span class="sxs-lookup"><span data-stu-id="f9281-111">AssignedIPAddresses() function</span></span>](advanced-hunting-assignedipaddresses-function.md) <br> <span data-ttu-id="f9281-112">고급 구하기 쿼리에이 함수를 사용 하 여 특정 시간에 장치에 할당 된 최신 IP 주소 또는 가장 최근 IP 주소를 빠르게 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9281-112">Use this function in your advanced hunting queries to quickly obtain the latest IP addresses assigned to a device or the most recent IP addresses from a specific time.</span></span>

## <a name="july-2020"></a><span data-ttu-id="f9281-113">2020년 7월</span><span class="sxs-lookup"><span data-stu-id="f9281-113">July 2020</span></span>
- [<span data-ttu-id="f9281-114">FileProfile () 함수</span><span class="sxs-lookup"><span data-stu-id="f9281-114">FileProfile() function</span></span>](advanced-hunting-fileprofile-function.md) <br> <span data-ttu-id="f9281-115">고급 구하기 쿼리에서이 함수를 사용 하 여 광범위 한 파일 정보가 포함 된 결과를 보강 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9281-115">Use this function in your advanced hunting queries to enrich results with comprehensive file information.</span></span>
- [<span data-ttu-id="f9281-116">Identity 및 app 테이블</span><span class="sxs-lookup"><span data-stu-id="f9281-116">Identity and app tables</span></span>](advanced-hunting-schema-tables.md)<br> <span data-ttu-id="f9281-117">고급 구하기 스키마에서 [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md), [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)및 [appfileevents](advanced-hunting-appfileevents-table.md) 테이블을 사용 하 여 인증 이벤트, Active Directory 쿼리 및 앱 관련 작업에 대 한 가시성을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9281-117">Get visibility into authentication events, Active Directory queries, and app-related activity with the [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md), [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md), and [AppFileEvents](advanced-hunting-appfileevents-table.md) tables in the advanced hunting schema.</span></span>
- [<span data-ttu-id="f9281-118">탐색</span><span class="sxs-lookup"><span data-stu-id="f9281-118">Go hunt</span></span>](advanced-hunting-go-hunt.md)<br> <span data-ttu-id="f9281-119">고급 사냥에서 특정 이벤트, 사용자, 장치 또는 기타 엔터티 유형을 검사 하는 인시던트를 조사 하는 것을 빠르게 피벗 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9281-119">Quickly pivot from investigating an incident to inspecting a specific event, a user, a device, or other entity types on advanced hunting.</span></span>

## <a name="june-2020"></a><span data-ttu-id="f9281-120">2020년 6월</span><span class="sxs-lookup"><span data-stu-id="f9281-120">June 2020</span></span>
- <span data-ttu-id="f9281-121">Twitter 피드</span><span class="sxs-lookup"><span data-stu-id="f9281-121">Twitter feed</span></span> <br> <span data-ttu-id="f9281-122">대시보드 내에서 최신 보안 연구, 위협 인텔리전스, 제품 소식 등을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="f9281-122">Get the latest security research, threat intelligence, product news, and more - right inside the dashboard.</span></span>
- [<span data-ttu-id="f9281-123">EmailPostDeliveryEvents schema 테이블</span><span class="sxs-lookup"><span data-stu-id="f9281-123">EmailPostDeliveryEvents schema table</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) <br> <span data-ttu-id="f9281-124">고급 구하기 쿼리의 전자 메일 메시지에 대해 수행 된 배달 후 작업에 대 한 정보를 통합 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9281-124">Incorporate information about post-delivery actions taken on email messages in your advanced hunting queries.</span></span>
- [<span data-ttu-id="f9281-125">고급 구하기에서 레코드 검사</span><span class="sxs-lookup"><span data-stu-id="f9281-125">Inspect records in advanced hunting</span></span>](advanced-hunting-query-results.md#drill-down-from-query-results) <br> <span data-ttu-id="f9281-126">새 세부 정보 패널을 사용 하 여 쿼리 결과의 레코드를 빠르게 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9281-126">Quickly inspect records in your query results with the new details panel.</span></span>

## <a name="may-2020"></a><span data-ttu-id="f9281-127">2020년 5월</span><span class="sxs-lookup"><span data-stu-id="f9281-127">May 2020</span></span>
- [<span data-ttu-id="f9281-128">사용자 지정 검색</span><span class="sxs-lookup"><span data-stu-id="f9281-128">Custom detections</span></span>](custom-detections-overview.md) <br> <span data-ttu-id="f9281-129">고급 검색 쿼리를 사용 하 여 보안 이벤트 및 시스템 상태에 대해 자동으로 모니터링 하 고 응답 하는 사용자 지정 검색 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f9281-129">Use advanced hunting queries to create custom detection rules that automatically monitor for and respond to security events and system states.</span></span>

## <a name="february-2020"></a><span data-ttu-id="f9281-130">2020년 2월</span><span class="sxs-lookup"><span data-stu-id="f9281-130">February 2020</span></span>
- [<span data-ttu-id="f9281-131">인시던트</span><span class="sxs-lookup"><span data-stu-id="f9281-131">Incidents</span></span>](incidents-overview.md) <br> <span data-ttu-id="f9281-132">공격이 시작 된 위치와 공격 범위를 확인 하는 데 도움이 되는 기타 세부 정보를 정확히 파악 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9281-132">Know exactly where an attack started and other details to help you see the extent of the attack.</span></span>
- [<span data-ttu-id="f9281-133">자동화된 조사 및 응답</span><span class="sxs-lookup"><span data-stu-id="f9281-133">Automated investigation and response</span></span>](mtp-autoir.md) <br> <span data-ttu-id="f9281-134">AIR을 사용하면 보안 운영팀에서 보안 경고와 인시던트를 처리하는 조직의 용량을 획기적으로 늘릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9281-134">AIR enables your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span>
- [<span data-ttu-id="f9281-135">고급 구하기 향상</span><span class="sxs-lookup"><span data-stu-id="f9281-135">Advanced hunting enhancements</span></span>](advanced-hunting-overview.md) <br> <span data-ttu-id="f9281-136">현재 작업 영역에서 Kusto 쿼리 언어 및 보안 최적화 스키마를 통해 위협을 사전에 사냥 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9281-136">Proactively hunt for threats across the modern workspace with Kusto Query Language and a security-optimized schema.</span></span>

## <a name="march-2019"></a><span data-ttu-id="f9281-137">2019년 3월</span><span class="sxs-lookup"><span data-stu-id="f9281-137">March 2019</span></span>
- <span data-ttu-id="f9281-138">고급 헌팅</span><span class="sxs-lookup"><span data-stu-id="f9281-138">Advanced hunting</span></span> <br> <span data-ttu-id="f9281-139">전자 메일 및 데이터, 장치 및 id에 영향을 주는 위협을 사전에 찾을 수 있게 해 주는 다양 한 검색 기능에 대 한 랜딩 페이지입니다.</span><span class="sxs-lookup"><span data-stu-id="f9281-139">Landing page to various hunting capabilities that let you proactively find threats affecting email and data, devices, and identities.</span></span>
- [<span data-ttu-id="f9281-140">Microsoft 보안 점수</span><span class="sxs-lookup"><span data-stu-id="f9281-140">Microsoft Secure Score</span></span>](microsoft-secure-score.md) <br> <span data-ttu-id="f9281-141">더 많은 향상 작업을 나타내는 더 높은 번호를 사용 하 여 조직의 보안 상황 측정</span><span class="sxs-lookup"><span data-stu-id="f9281-141">Measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="f9281-142">보안 점수 권장 사항을 따르면 위협 으로부터 조직을 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9281-142">Following the Security Score recommendations can protect your organization from threats.</span></span> 
- [<span data-ttu-id="f9281-143">보고서</span><span class="sxs-lookup"><span data-stu-id="f9281-143">Reports</span></span>](monitoring-and-reporting.md) <br>  <span data-ttu-id="f9281-144">기능은 보안 분석가와 관리자가 일상 작업의 일부로 추적 하는 다양 한 영역을 다루는 카드의 호스트입니다.</span><span class="sxs-lookup"><span data-stu-id="f9281-144">Features a host of cards covering a variety of areas that security analysts and administrators track as part of their day-to-day operations.</span></span>
