---
title: 개요 - 고급 헌팅
description: Microsoft 365의 고급 검색 쿼리와 이를 사용하여 네트워크의 위협과 약점을 사전에 찾는 방법에 대해 알아보세요.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 위협 방지, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 사용자 지정 감지, schema, kusto, microsoft 365, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: 0338e87c103bef0f12a45277a14152ef429d0067
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076348"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-365-defender"></a><span data-ttu-id="5de5e-104">Microsoft 365 Defender에서 고급 헌팅을 통해 위협을 사전 대응</span><span class="sxs-lookup"><span data-stu-id="5de5e-104">Proactively hunt for threats with advanced hunting in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="5de5e-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="5de5e-105">**Applies to:**</span></span>
- <span data-ttu-id="5de5e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5de5e-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="5de5e-107">Microsoft 365 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="5de5e-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="5de5e-108">랩 [환경에서 평가하거나](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) 프로덕션 [환경에서 파일럿](m365d-pilot.md?ocid=cx-evalpilot)프로젝트를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5de5e-108">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>

<span data-ttu-id="5de5e-109">고급 헌팅은 최대 30일간의 원시 데이터를 탐색할 수 있는 쿼리 기반의 위협 헌팅 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="5de5e-109">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data.</span></span> <span data-ttu-id="5de5e-110">네트워크에서 이벤트를 사전 검사하여 위협 표시기 및 엔터티를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5de5e-110">You can proactively inspect events in your network to locate threat indicators and entities.</span></span> <span data-ttu-id="5de5e-111">데이터에 대한 유연한 액세스를 통해 알려진 위협과 잠재적 위협 모두에 대한 제약이 없는 헌팅을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5de5e-111">The flexible access to data enables unconstrained hunting for both known and potential threats.</span></span>
<p></p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

<span data-ttu-id="5de5e-112">동일한 위협 헌팅 쿼리를 사용하여 사용자 지정 탐지 규칙을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5de5e-112">You can use the same threat-hunting queries to build custom detection rules.</span></span> <span data-ttu-id="5de5e-113">이러한 규칙은 자동으로 실행되어 의심되는 위반 활동, 잘못 구성된 컴퓨터 및 기타 결과를 확인하고 이에 대응합니다.</span><span class="sxs-lookup"><span data-stu-id="5de5e-113">These rules run automatically to check for and then respond to suspected breach activity, misconfigured machines, and other findings.</span></span>

<span data-ttu-id="5de5e-114">이 기능은 [끝점용 Microsoft Defender의 고급 헌팅과 유사합니다.](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)</span><span class="sxs-lookup"><span data-stu-id="5de5e-114">This capability is similar to [advanced hunting in Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview).</span></span> <span data-ttu-id="5de5e-115">Microsoft 365 보안 센터에서 사용할 수 있는 이 기능은 다음에서 더 광범위한 데이터 집합을 검사하는 쿼리를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="5de5e-115">Available in Microsoft 365 security center, this capability supports queries that check a broader data set from:</span></span>

- <span data-ttu-id="5de5e-116">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="5de5e-116">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="5de5e-117">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="5de5e-117">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="5de5e-118">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="5de5e-118">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="5de5e-119">ID용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="5de5e-119">Microsoft Defender for Identity</span></span>

<span data-ttu-id="5de5e-120">고급 헌팅을 사용하 고 [Microsoft 365 Defender 를 켜야 합니다.](m365d-enable.md)</span><span class="sxs-lookup"><span data-stu-id="5de5e-120">To use advanced hunting, [turn on Microsoft 365 Defender](m365d-enable.md).</span></span>

## <a name="get-started-with-advanced-hunting"></a><span data-ttu-id="5de5e-121">고급 헌팅 시작</span><span class="sxs-lookup"><span data-stu-id="5de5e-121">Get started with advanced hunting</span></span>

<span data-ttu-id="5de5e-122">고급 헌팅을 빠르게 시작하기 위해 몇 가지 단계를 진행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5de5e-122">We recommend going through several steps to quickly get started with advanced hunting.</span></span>

| <span data-ttu-id="5de5e-123">학습 목표</span><span class="sxs-lookup"><span data-stu-id="5de5e-123">Learning goal</span></span> | <span data-ttu-id="5de5e-124">설명</span><span class="sxs-lookup"><span data-stu-id="5de5e-124">Description</span></span> | <span data-ttu-id="5de5e-125">리소스</span><span class="sxs-lookup"><span data-stu-id="5de5e-125">Resource</span></span> |
|--|--|--|
| <span data-ttu-id="5de5e-126">**언어 학습**</span><span class="sxs-lookup"><span data-stu-id="5de5e-126">**Learn the language**</span></span> | <span data-ttu-id="5de5e-127">고급 헌팅은 [Kusto](/azure/kusto/query/)쿼리 언어를 기반으로 하여 동일한 구문과 연산자를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="5de5e-127">Advanced hunting is based on [Kusto query language](/azure/kusto/query/), supporting the same syntax and operators.</span></span> <span data-ttu-id="5de5e-128">첫 번째 쿼리를 실행하여 쿼리 언어 학습을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="5de5e-128">Start learning the query language by running your first query.</span></span> | [<span data-ttu-id="5de5e-129">쿼리 언어 개요</span><span class="sxs-lookup"><span data-stu-id="5de5e-129">Query language overview</span></span>](advanced-hunting-query-language.md) |
| <span data-ttu-id="5de5e-130">**쿼리 결과 사용 방법 학습**</span><span class="sxs-lookup"><span data-stu-id="5de5e-130">**Learn how to use the query results**</span></span> | <span data-ttu-id="5de5e-131">결과를 보거나 내보낼 수 있는 차트 및 다양한 방법에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="5de5e-131">Learn about charts and various ways you can view or export your results.</span></span> <span data-ttu-id="5de5e-132">쿼리를 빠르게 조정하고, 드릴다운하여 더 풍부한 정보를 얻고, 응답 작업을 수행할 수 있는 방법을 살펴보고,</span><span class="sxs-lookup"><span data-stu-id="5de5e-132">Explore how you can quickly tweak queries, drill down to get richer information, and take response actions.</span></span> | <span data-ttu-id="5de5e-133">- [쿼리 결과 작업](advanced-hunting-query-results.md)</span><span class="sxs-lookup"><span data-stu-id="5de5e-133">- [Work with query results](advanced-hunting-query-results.md)</span></span><br><span data-ttu-id="5de5e-134">- [쿼리 결과에 대한 작업 수행](advanced-hunting-take-action.md)</span><span class="sxs-lookup"><span data-stu-id="5de5e-134">- [Take action on query results](advanced-hunting-take-action.md)</span></span> |
| <span data-ttu-id="5de5e-135">**스키마의 이해**</span><span class="sxs-lookup"><span data-stu-id="5de5e-135">**Understand the schema**</span></span> | <span data-ttu-id="5de5e-136">스키마와 해당 열에 있는 테이블에 대한 이해를 높이세요.</span><span class="sxs-lookup"><span data-stu-id="5de5e-136">Get a good, high-level understanding of the tables in the schema and their columns.</span></span> <span data-ttu-id="5de5e-137">쿼리를 구성할 때 데이터를 검색할 위치를 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="5de5e-137">Learn where to look for data when constructing your queries.</span></span> | <span data-ttu-id="5de5e-138">- [Schema reference](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="5de5e-138">- [Schema reference](advanced-hunting-schema-tables.md)</span></span><br><span data-ttu-id="5de5e-139">- [끝점용 Microsoft Defender에서 전환](advanced-hunting-migrate-from-mde.md)</span><span class="sxs-lookup"><span data-stu-id="5de5e-139">- [Transition from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mde.md)</span></span> |
| <span data-ttu-id="5de5e-140">**전문가 팁 및 예제 보기**</span><span class="sxs-lookup"><span data-stu-id="5de5e-140">**Get expert tips and examples**</span></span> | <span data-ttu-id="5de5e-141">Microsoft 전문가의 가이드를 통해 무료로 교육합니다.</span><span class="sxs-lookup"><span data-stu-id="5de5e-141">Train for free with guides from Microsoft experts.</span></span> <span data-ttu-id="5de5e-142">다양한 위협 헌팅 시나리오를 다루는 미리 정의된 쿼리 모음을 탐색합니다.</span><span class="sxs-lookup"><span data-stu-id="5de5e-142">Explore collections of predefined queries covering different threat hunting scenarios.</span></span> | <span data-ttu-id="5de5e-143">- [전문가 교육을 받을 수 있습니다.](advanced-hunting-expert-training.md)</span><span class="sxs-lookup"><span data-stu-id="5de5e-143">- [Get expert training](advanced-hunting-expert-training.md)</span></span><br><span data-ttu-id="5de5e-144">- [공유 쿼리 사용](advanced-hunting-shared-queries.md)</span><span class="sxs-lookup"><span data-stu-id="5de5e-144">- [Use shared queries](advanced-hunting-shared-queries.md)</span></span><br><span data-ttu-id="5de5e-145">- [이동 헌트](advanced-hunting-go-hunt.md)</span><span class="sxs-lookup"><span data-stu-id="5de5e-145">- [Go hunt](advanced-hunting-go-hunt.md)</span></span><br><span data-ttu-id="5de5e-146">- [장치, 전자 메일, 앱 및 ID에서 위협을 찾기](advanced-hunting-query-emails-devices.md)</span><span class="sxs-lookup"><span data-stu-id="5de5e-146">- [Hunt for threats across devices, emails, apps, and identities](advanced-hunting-query-emails-devices.md)</span></span> |
| <span data-ttu-id="5de5e-147">**쿼리 최적화 및 오류 처리**</span><span class="sxs-lookup"><span data-stu-id="5de5e-147">**Optimize queries and handle errors**</span></span> | <span data-ttu-id="5de5e-148">효율적이고 오류가 없는 쿼리를 만드는 방법을 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="5de5e-148">Understand how to create efficient and error-free queries.</span></span> | <span data-ttu-id="5de5e-149">- [쿼리 모범 사례](advanced-hunting-best-practices.md)</span><span class="sxs-lookup"><span data-stu-id="5de5e-149">- [Query best practices](advanced-hunting-best-practices.md)</span></span><br><span data-ttu-id="5de5e-150">- [오류 처리](advanced-hunting-errors.md)</span><span class="sxs-lookup"><span data-stu-id="5de5e-150">- [Handle errors](advanced-hunting-errors.md)</span></span> |
| <span data-ttu-id="5de5e-151">**사용자 지정 검색 규칙 만들기**</span><span class="sxs-lookup"><span data-stu-id="5de5e-151">**Create custom detection rules**</span></span> | <span data-ttu-id="5de5e-152">고급 헌팅 쿼리를 사용하여 경고를 트리거하고 응답 작업을 자동으로 수행할 수 있는 방법을 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="5de5e-152">Understand how you can use advanced hunting queries to trigger alerts and take response actions automatically.</span></span> | <span data-ttu-id="5de5e-153">- [사용자 지정 검색 개요](custom-detections-overview.md)</span><span class="sxs-lookup"><span data-stu-id="5de5e-153">- [Custom detections overview](custom-detections-overview.md)</span></span><br><span data-ttu-id="5de5e-154">- [사용자 지정 검색 규칙](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="5de5e-154">- [Custom detection rules](custom-detection-rules.md)</span></span> |

## <a name="get-access"></a><span data-ttu-id="5de5e-155">액세스 액세스</span><span class="sxs-lookup"><span data-stu-id="5de5e-155">Get access</span></span>
<span data-ttu-id="5de5e-156">고급 헌팅 또는 [기타 Microsoft 365 Defender](microsoft-365-defender.md) 기능을 사용하려면 Azure Active Directory에서 적절한 역할이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5de5e-156">To use advanced hunting or other [Microsoft 365 Defender](microsoft-365-defender.md) capabilities, you need an appropriate role in Azure Active Directory.</span></span> <span data-ttu-id="5de5e-157">또한 끝점 데이터에 대한 액세스는 끝점용 Microsoft Defender의 RBAC(역할 기반 액세스 제어) 설정에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="5de5e-157">Also, your access to endpoint data is determined by role-based access control (RBAC) settings in Microsoft Defender for Endpoint.</span></span> [<span data-ttu-id="5de5e-158">Microsoft 365 Defender에 대한 액세스 관리에 대한 읽기</span><span class="sxs-lookup"><span data-stu-id="5de5e-158">Read about managing access to Microsoft 365 Defender</span></span>](m365d-permissions.md)

## <a name="data-freshness-and-update-frequency"></a><span data-ttu-id="5de5e-159">데이터 최신성 및 업데이트 빈도</span><span class="sxs-lookup"><span data-stu-id="5de5e-159">Data freshness and update frequency</span></span>
<span data-ttu-id="5de5e-160">고급 헌팅 데이터는 서로 다른 두 가지 유형으로 분류할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5de5e-160">Advanced hunting data can be categorized into two distinct types, each consolidated differently.</span></span>

- <span data-ttu-id="5de5e-161">**이벤트 또는 활동 데이터**- 경고, 보안 이벤트, 시스템 이벤트 및 일상적인 평가에 대한 테이블을 채우습니다.</span><span class="sxs-lookup"><span data-stu-id="5de5e-161">**Event or activity data**—populates tables about alerts, security events, system events, and routine assessments.</span></span> <span data-ttu-id="5de5e-162">고급 헌팅은 해당 데이터를 수집하는 센서가 해당 클라우드 서비스로 성공적으로 전송된 직후에 이 데이터를 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="5de5e-162">Advanced hunting receives this data almost immediately after the sensors that collect them successfully transmit them to the corresponding cloud services.</span></span> <span data-ttu-id="5de5e-163">예를 들어 끝점용 Microsoft Defender 및 ID용 Microsoft Defender에서 사용할 수 있는 직후에, 또는 도메인 컨트롤러 또는 작업장에서 정상 센서의 이벤트 데이터를 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5de5e-163">For example, you can query event data from healthy sensors on workstations or domain controllers almost immediately after they are available on Microsoft Defender for Endpoint and Microsoft Defender for Identity.</span></span>
- <span data-ttu-id="5de5e-164">**엔터티 데이터**- 사용자 및 장치에 대한 정보로 테이블을 채우는 경우</span><span class="sxs-lookup"><span data-stu-id="5de5e-164">**Entity data**—populates tables with information about users and devices.</span></span> <span data-ttu-id="5de5e-165">이 데이터는 Active Directory 항목 및 이벤트 로그와 같은 비교적 정적 데이터 원본과 동적 원본 모두에서 온 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5de5e-165">This data comes from both relatively static data sources and dynamic sources, such as Active Directory entries and event logs.</span></span> <span data-ttu-id="5de5e-166">새 데이터를 제공하기 위해 표는 15분마다 모든 새 정보로 업데이트되어 완전히 채워지지 않을 수 있는 행을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5de5e-166">To provide fresh data, tables are updated with any new information every 15 minutes, adding rows that might not be fully populated.</span></span> <span data-ttu-id="5de5e-167">24시간마다 데이터가 통합되어 각 엔터티에 대한 가장 포괄적인 최신 데이터 집합이 포함된 레코드를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="5de5e-167">Every 24 hours, data is consolidated to insert a record that contains the latest, most comprehensive data set about each entity.</span></span>

## <a name="time-zone"></a><span data-ttu-id="5de5e-168">표준 시간대</span><span class="sxs-lookup"><span data-stu-id="5de5e-168">Time zone</span></span>
<span data-ttu-id="5de5e-169">고급 헌팅의 시간 정보는 UTC 표준 시간대에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5de5e-169">Time information in advanced hunting is in the UTC time zone.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5de5e-170">관련 항목</span><span class="sxs-lookup"><span data-stu-id="5de5e-170">Related topics</span></span>
- [<span data-ttu-id="5de5e-171">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="5de5e-171">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="5de5e-172">전문가 교육 받기</span><span class="sxs-lookup"><span data-stu-id="5de5e-172">Get expert training</span></span>](advanced-hunting-expert-training.md)
- [<span data-ttu-id="5de5e-173">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="5de5e-173">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="5de5e-174">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="5de5e-174">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="5de5e-175">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="5de5e-175">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="5de5e-176">사용자 지정 검색 개요</span><span class="sxs-lookup"><span data-stu-id="5de5e-176">Custom detections overview</span></span>](custom-detections-overview.md)