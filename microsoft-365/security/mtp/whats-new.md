---
title: Microsoft 365 Defender의 새로운 기능
description: Microsoft 365 Defender의 새로운 기능을 나열합니다.
keywords: Microsoft 위협 방지, ga, 일반적으로 사용 가능, 기능, 사용 가능, 새로운 기능의 새로운 기능
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 4e065ff4da80b50ea11ff2069e8938c59f16f962
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165994"
---
# <a name="whats-new-in-microsoft-365-defender"></a><span data-ttu-id="76b0e-104">Microsoft 365 Defender의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="76b0e-104">What's new in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> <span data-ttu-id="76b0e-105">Microsoft 365 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="76b0e-105">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="76b0e-106">랩 [환경에서 평가하거나](https://aka.ms/mtp-trial-lab) 프로덕션 환경에서 파일럿 프로젝트를 [실행할 수 있습니다.](https://aka.ms/m365d-pilotplaybook)</span><span class="sxs-lookup"><span data-stu-id="76b0e-106">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>

<span data-ttu-id="76b0e-107">다음 기능은 Microsoft 365 Defender의 최신 릴리스에서 일반적으로 사용할 수 있습니다(GA).</span><span class="sxs-lookup"><span data-stu-id="76b0e-107">The following features are generally available (GA) in the latest release of Microsoft 365 Defender.</span></span>

<span data-ttu-id="76b0e-108">RSS 피드: 다음 URL을 복사하여 피드 읽기에 붙여 넣는 방법을 통해 이 페이지가 업데이트될 때 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76b0e-108">RSS feed: Get notified when this page is updated by copying and pasting the following URL into your feed reader:</span></span>
```http
https://docs.microsoft.com/api/search/rss?search=%22Lists+the+new+features+and+functionality+in+Microsoft+Threat+Protection%22&locale=en-us
```

## <a name="february-2021"></a><span data-ttu-id="76b0e-109">2021년 2월</span><span class="sxs-lookup"><span data-stu-id="76b0e-109">February 2021</span></span>
- <span data-ttu-id="76b0e-110">(미리 보기) 향상된 [Microsoft 365 보안 https://security.microsoft.com) 센터(이제](https://security.microsoft.com) 공개 미리 보기에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76b0e-110">(Preview) The enhanced [Microsoft 365 security center (https://security.microsoft.com)](https://security.microsoft.com) is now available in public preview.</span></span> <span data-ttu-id="76b0e-111">이 새로운 환경은 끝점용 Defender 및 Office 365용 Defender를 중앙에 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="76b0e-111">This new experience brings Defender for Endpoint and Defender for Office 365 to the center.</span></span> <span data-ttu-id="76b0e-112">[변경된 내용을 자세히 알아보는 것이 있습니다.](https://docs.microsoft.com/microsoft-365/security/mtp/overview-security-center)</span><span class="sxs-lookup"><span data-stu-id="76b0e-112">[Learn more about what's changed](https://docs.microsoft.com/microsoft-365/security/mtp/overview-security-center).</span></span>

## <a name="september-2020"></a><span data-ttu-id="76b0e-113">2020년 9월</span><span class="sxs-lookup"><span data-stu-id="76b0e-113">September 2020</span></span>
- [<span data-ttu-id="76b0e-114">IdentityDirectoryEvents 테이블</span><span class="sxs-lookup"><span data-stu-id="76b0e-114">IdentityDirectoryEvents table</span></span>](advanced-hunting-identitydirectoryevents-table.md) <br> <span data-ttu-id="76b0e-115">AD(Active Directory)를 실행하는 On-프레미스 도메인 컨트롤러와 관련된 이벤트를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="76b0e-115">Find events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="76b0e-116">이 [고급 헌팅](advanced-hunting-overview.md) 체계표에는 도메인 컨트롤러의 ID 관련 이벤트 및 시스템 이벤트가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="76b0e-116">This [advanced hunting](advanced-hunting-overview.md) schema table covers a range of identity-related events and system events on the domain controller.</span></span>
- [<span data-ttu-id="76b0e-117">AssignedIPAddresses() 함수</span><span class="sxs-lookup"><span data-stu-id="76b0e-117">AssignedIPAddresses() function</span></span>](advanced-hunting-assignedipaddresses-function.md) <br> <span data-ttu-id="76b0e-118">고급 헌팅 쿼리에서 이 기능을 사용하여 장치에 할당된 최신 IP 주소 또는 특정 시간의 최신 IP 주소를 빠르게 구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76b0e-118">Use this function in your advanced hunting queries to quickly obtain the latest IP addresses assigned to a device or the most recent IP addresses from a specific time.</span></span>

## <a name="july-2020"></a><span data-ttu-id="76b0e-119">2020년 7월</span><span class="sxs-lookup"><span data-stu-id="76b0e-119">July 2020</span></span>
- [<span data-ttu-id="76b0e-120">FileProfile() 함수</span><span class="sxs-lookup"><span data-stu-id="76b0e-120">FileProfile() function</span></span>](advanced-hunting-fileprofile-function.md) <br> <span data-ttu-id="76b0e-121">고급 헌팅 쿼리에서 이 기능을 사용하여 포괄적인 파일 정보로 결과를 향상합니다.</span><span class="sxs-lookup"><span data-stu-id="76b0e-121">Use this function in your advanced hunting queries to enrich results with comprehensive file information.</span></span>
- [<span data-ttu-id="76b0e-122">ID 및 앱 테이블</span><span class="sxs-lookup"><span data-stu-id="76b0e-122">Identity and app tables</span></span>](advanced-hunting-schema-tables.md)<br> <span data-ttu-id="76b0e-123">고급 헌팅 계획에서 [IdentityLogonEvents, IdentityQueryEvents](advanced-hunting-identitylogonevents-table.md)및 [AppFileEvents](advanced-hunting-appfileevents-table.md) 테이블을 사용하여 인증 이벤트, Active Directory 쿼리 및 앱 관련 활동을 확인할 수 있습니다. [](advanced-hunting-identityqueryevents-table.md)</span><span class="sxs-lookup"><span data-stu-id="76b0e-123">Get visibility into authentication events, Active Directory queries, and app-related activity with the [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md), [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md), and [AppFileEvents](advanced-hunting-appfileevents-table.md) tables in the advanced hunting schema.</span></span>
- [<span data-ttu-id="76b0e-124">탐색</span><span class="sxs-lookup"><span data-stu-id="76b0e-124">Go hunt</span></span>](advanced-hunting-go-hunt.md)<br> <span data-ttu-id="76b0e-125">인시던트 조사에서 고급 헌팅에 대한 특정 이벤트, 사용자, 장치 또는 기타 엔터티 유형을 검사하는 데 신속하게 피벗합니다.</span><span class="sxs-lookup"><span data-stu-id="76b0e-125">Quickly pivot from investigating an incident to inspecting a specific event, a user, a device, or other entity types on advanced hunting.</span></span>

## <a name="june-2020"></a><span data-ttu-id="76b0e-126">2020년 6월</span><span class="sxs-lookup"><span data-stu-id="76b0e-126">June 2020</span></span>
- <span data-ttu-id="76b0e-127">Twitter 피드</span><span class="sxs-lookup"><span data-stu-id="76b0e-127">Twitter feed</span></span> <br> <span data-ttu-id="76b0e-128">대시보드 내에서 최신 보안 연구, 위협 인텔리전스, 제품 뉴스 등 자세한 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76b0e-128">Get the latest security research, threat intelligence, product news, and more - right inside the dashboard.</span></span>
- [<span data-ttu-id="76b0e-129">EmailPostDeliveryEvents schema 테이블</span><span class="sxs-lookup"><span data-stu-id="76b0e-129">EmailPostDeliveryEvents schema table</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) <br> <span data-ttu-id="76b0e-130">고급 헌팅 쿼리에서 전자 메일 메시지에 대해 수행된 배달 후 작업에 대한 정보를 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="76b0e-130">Incorporate information about post-delivery actions taken on email messages in your advanced hunting queries.</span></span>
- [<span data-ttu-id="76b0e-131">고급 헌팅의 레코드 검사</span><span class="sxs-lookup"><span data-stu-id="76b0e-131">Inspect records in advanced hunting</span></span>](advanced-hunting-query-results.md#drill-down-from-query-results) <br> <span data-ttu-id="76b0e-132">새 세부 정보 패널을 사용하여 쿼리 결과의 레코드를 빠르게 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="76b0e-132">Quickly inspect records in your query results with the new details panel.</span></span>

## <a name="may-2020"></a><span data-ttu-id="76b0e-133">2020년 5월</span><span class="sxs-lookup"><span data-stu-id="76b0e-133">May 2020</span></span>
- [<span data-ttu-id="76b0e-134">사용자 지정 검색</span><span class="sxs-lookup"><span data-stu-id="76b0e-134">Custom detections</span></span>](custom-detections-overview.md) <br> <span data-ttu-id="76b0e-135">고급 헌팅 쿼리를 사용하여 보안 이벤트 및 시스템 상태의 자동으로 모니터링 및 응답하는 사용자 지정 검색 규칙을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76b0e-135">Use advanced hunting queries to create custom detection rules that automatically monitor for and respond to security events and system states.</span></span>

## <a name="february-2020"></a><span data-ttu-id="76b0e-136">2020년 2월</span><span class="sxs-lookup"><span data-stu-id="76b0e-136">February 2020</span></span>
- [<span data-ttu-id="76b0e-137">인시던트</span><span class="sxs-lookup"><span data-stu-id="76b0e-137">Incidents</span></span>](incidents-overview.md) <br> <span data-ttu-id="76b0e-138">공격이 시작된 위치와 공격의 범위를 보는 데 도움이 되는 기타 세부 정보를 정확하게 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76b0e-138">Know exactly where an attack started and other details to help you see the extent of the attack.</span></span>
- [<span data-ttu-id="76b0e-139">자동화된 조사 및 응답</span><span class="sxs-lookup"><span data-stu-id="76b0e-139">Automated investigation and response</span></span>](mtp-autoir.md) <br> <span data-ttu-id="76b0e-140">AIR을 사용하면 보안 운영팀에서 보안 경고와 인시던트를 처리하는 조직의 용량을 획기적으로 늘릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76b0e-140">AIR enables your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span>
- [<span data-ttu-id="76b0e-141">고급 헌팅 기능 향상</span><span class="sxs-lookup"><span data-stu-id="76b0e-141">Advanced hunting enhancements</span></span>](advanced-hunting-overview.md) <br> <span data-ttu-id="76b0e-142">Kusto 쿼리 언어 및 보안 최적화된 schema를 사용하여 최신 작업 영역의 위협을 사전 예방적으로 헌팅합니다.</span><span class="sxs-lookup"><span data-stu-id="76b0e-142">Proactively hunt for threats across the modern workspace with Kusto Query Language and a security-optimized schema.</span></span>

## <a name="march-2019"></a><span data-ttu-id="76b0e-143">2019년 3월</span><span class="sxs-lookup"><span data-stu-id="76b0e-143">March 2019</span></span>
- <span data-ttu-id="76b0e-144">고급 헌팅</span><span class="sxs-lookup"><span data-stu-id="76b0e-144">Advanced hunting</span></span> <br> <span data-ttu-id="76b0e-145">전자 메일 및 데이터, 장치 및 ID에 영향을 주는 위협을 사전 예방적으로 찾을 수 있는 다양한 헌팅 기능에 대한 방문 페이지입니다.</span><span class="sxs-lookup"><span data-stu-id="76b0e-145">Landing page to various hunting capabilities that let you proactively find threats affecting email and data, devices, and identities.</span></span>
- [<span data-ttu-id="76b0e-146">Microsoft 보안 점수</span><span class="sxs-lookup"><span data-stu-id="76b0e-146">Microsoft Secure Score</span></span>](microsoft-secure-score.md) <br> <span data-ttu-id="76b0e-147">개선 작업이 더 많이 수행되었음을 나타내는 수치가 높은 조직의 보안 자세를 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="76b0e-147">Measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="76b0e-148">보안 점수 권장 사항을 따라 조직을 위협으로부터 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76b0e-148">Following the Security Score recommendations can protect your organization from threats.</span></span> 
- [<span data-ttu-id="76b0e-149">보고서</span><span class="sxs-lookup"><span data-stu-id="76b0e-149">Reports</span></span>](monitoring-and-reporting.md) <br>  <span data-ttu-id="76b0e-150">보안 분석가와 관리자가 매일 작업의 일부로 추적하는 다양한 영역을 다루는 카드 호스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="76b0e-150">Features a host of cards covering a variety of areas that security analysts and administrators track as part of their day-to-day operations.</span></span>
