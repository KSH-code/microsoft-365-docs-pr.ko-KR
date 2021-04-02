---
title: Microsoft Defender ATP의 고급 헌팅 개요
description: Microsoft Defender ATP의 위협 헌팅 기능을 사용하여 네트워크에서 위협과 약점을 찾는 쿼리를 작성합니다.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, mdatp, microsoft defender atp, wdatp, 검색, 쿼리, 원격 분석, 사용자 지정 검색, schema, kusto, 표준 시간대, UTC
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4883a4f04f06774d02aa0d942edc841867eb36b6
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499515"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting"></a><span data-ttu-id="6232f-104">고급 헌팅을 통해 위협을 사전 대응</span><span class="sxs-lookup"><span data-stu-id="6232f-104">Proactively hunt for threats with advanced hunting</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6232f-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="6232f-105">**Applies to:**</span></span>
- [<span data-ttu-id="6232f-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6232f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="6232f-107">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="6232f-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6232f-108">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="6232f-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

<span data-ttu-id="6232f-109">고급 헌팅은 최대 30일간의 원시 데이터를 탐색할 수 있는 쿼리 기반의 위협 헌팅 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="6232f-109">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data.</span></span> <span data-ttu-id="6232f-110">네트워크에서 이벤트를 사전 검사하여 위협 표시기 및 엔터티를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6232f-110">You can proactively inspect events in your network to locate threat indicators and entities.</span></span> <span data-ttu-id="6232f-111">데이터에 대한 유연한 액세스를 통해 알려진 위협과 잠재적 위협 모두에 대한 제약이 없는 헌팅을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6232f-111">The flexible access to data enables unconstrained hunting for both known and potential threats.</span></span>

<span data-ttu-id="6232f-112">이 비디오를 통해 고급 헌팅에 대한 간략한 개요와 빠르게 시작할 수 있는 간단한 자습서를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6232f-112">Watch this video for a quick overview of advanced hunting and a short tutorial that will get you started fast.</span></span>
<br />
<br />

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqo]

<span data-ttu-id="6232f-113">동일한 위협 헌팅 쿼리를 사용하여 사용자 지정 탐지 규칙을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6232f-113">You can use the same threat-hunting queries to build custom detection rules.</span></span> <span data-ttu-id="6232f-114">이러한 규칙은 자동으로 실행되어 의심되는 위반 활동, 잘못 구성된 컴퓨터 및 기타 결과를 확인하고 이에 대응합니다.</span><span class="sxs-lookup"><span data-stu-id="6232f-114">These rules run automatically to check for and then respond to suspected breach activity, misconfigured machines, and other findings.</span></span>

>[!TIP]
><span data-ttu-id="6232f-115">[Microsoft Threat Protection의](https://docs.microsoft.com/microsoft-365/security/defender/advanced-hunting-overview) 고급 헌팅을 사용하여 끝점용 Defender, Office 365용 Microsoft Defender, Microsoft Cloud App Security 및 ID용 Microsoft Defender의 데이터를 사용하여 위협을 헌팅합니다.</span><span class="sxs-lookup"><span data-stu-id="6232f-115">Use [advanced hunting in Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/defender/advanced-hunting-overview) to hunt for threats using data from Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> [<span data-ttu-id="6232f-116">Microsoft 365 Defender 켜기</span><span class="sxs-lookup"><span data-stu-id="6232f-116">Turn on Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/defender/mtp-enable)

## <a name="get-started-with-advanced-hunting"></a><span data-ttu-id="6232f-117">고급 헌팅 시작</span><span class="sxs-lookup"><span data-stu-id="6232f-117">Get started with advanced hunting</span></span>

<span data-ttu-id="6232f-118">다음 단계에 따라 고급 헌팅 지식을 쌓아가세요.</span><span class="sxs-lookup"><span data-stu-id="6232f-118">Go through the following steps to ramp up your advanced hunting knowledge.</span></span>

<span data-ttu-id="6232f-119">고급 헌팅을 빠르게 시작하고 실행하려면 몇가지 단계를 수행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6232f-119">We recommend going through several steps to quickly get up and running with advanced hunting.</span></span>

| <span data-ttu-id="6232f-120">학습 목표</span><span class="sxs-lookup"><span data-stu-id="6232f-120">Learning goal</span></span> | <span data-ttu-id="6232f-121">설명</span><span class="sxs-lookup"><span data-stu-id="6232f-121">Description</span></span> | <span data-ttu-id="6232f-122">리소스</span><span class="sxs-lookup"><span data-stu-id="6232f-122">Resource</span></span> |
|--|--|--|
| <span data-ttu-id="6232f-123">**언어 학습**</span><span class="sxs-lookup"><span data-stu-id="6232f-123">**Learn the language**</span></span> | <span data-ttu-id="6232f-124">고급 헌팅은 [Kusto](https://docs.microsoft.com/azure/kusto/query/)쿼리 언어를 기반으로 하여 동일한 구문과 연산자를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="6232f-124">Advanced hunting is based on [Kusto query language](https://docs.microsoft.com/azure/kusto/query/), supporting the same syntax and operators.</span></span> <span data-ttu-id="6232f-125">첫 번째 쿼리를 실행하여 쿼리 언어 학습을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="6232f-125">Start learning the query language by running your first query.</span></span> | [<span data-ttu-id="6232f-126">쿼리 언어 개요</span><span class="sxs-lookup"><span data-stu-id="6232f-126">Query language overview</span></span>](advanced-hunting-query-language.md) |
| <span data-ttu-id="6232f-127">**쿼리 결과 사용 방법 학습**</span><span class="sxs-lookup"><span data-stu-id="6232f-127">**Learn how to use the query results**</span></span> | <span data-ttu-id="6232f-128">결과를 보거나 내보낼 수 있는 차트 및 다양한 방법에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="6232f-128">Learn about charts and various ways you can view or export your results.</span></span> <span data-ttu-id="6232f-129">보다 풍부한 정보를 얻을 수 있도록 쿼리를 빠르게 조정하고 드릴다운하는 방법을 살펴보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6232f-129">Explore how you can quickly tweak queries and drill down to get richer information.</span></span> | [<span data-ttu-id="6232f-130">쿼리 결과로 작업</span><span class="sxs-lookup"><span data-stu-id="6232f-130">Work with query results</span></span>](advanced-hunting-query-results.md) |
| <span data-ttu-id="6232f-131">**스키마의 이해**</span><span class="sxs-lookup"><span data-stu-id="6232f-131">**Understand the schema**</span></span> | <span data-ttu-id="6232f-132">스키마와 해당 열에 있는 테이블에 대한 이해를 높이세요.</span><span class="sxs-lookup"><span data-stu-id="6232f-132">Get a good, high-level understanding of the tables in the schema and their columns.</span></span> <span data-ttu-id="6232f-133">쿼리를 구성할 때 데이터를 검색할 위치를 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="6232f-133">Learn where to look for data when constructing your queries.</span></span> | [<span data-ttu-id="6232f-134">스키마 참조</span><span class="sxs-lookup"><span data-stu-id="6232f-134">Schema reference</span></span>](advanced-hunting-schema-reference.md) |
| <span data-ttu-id="6232f-135">**미리 정의된 쿼리 사용**</span><span class="sxs-lookup"><span data-stu-id="6232f-135">**Use predefined queries**</span></span> | <span data-ttu-id="6232f-136">다양한 위협 헌팅 시나리오를 다루는 미리 정의된 쿼리 모음을 탐색합니다.</span><span class="sxs-lookup"><span data-stu-id="6232f-136">Explore collections of predefined queries covering different threat hunting scenarios.</span></span> | [<span data-ttu-id="6232f-137">공유 쿼리</span><span class="sxs-lookup"><span data-stu-id="6232f-137">Shared queries</span></span>](advanced-hunting-shared-queries.md) |
| <span data-ttu-id="6232f-138">**쿼리 최적화 및 오류 처리**</span><span class="sxs-lookup"><span data-stu-id="6232f-138">**Optimize queries and handle errors**</span></span> | <span data-ttu-id="6232f-139">효율적이고 오류가 없는 쿼리를 만드는 방법을 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="6232f-139">Understand how to create efficient and error-free queries.</span></span> | <span data-ttu-id="6232f-140">- [쿼리 모범 사례](advanced-hunting-best-practices.md)</span><span class="sxs-lookup"><span data-stu-id="6232f-140">- [Query best practices](advanced-hunting-best-practices.md)</span></span><br><span data-ttu-id="6232f-141">- [오류 처리](advanced-hunting-errors.md)</span><span class="sxs-lookup"><span data-stu-id="6232f-141">- [Handle errors](advanced-hunting-errors.md)</span></span> |
| <span data-ttu-id="6232f-142">**가장 완전한 적용 범위 얻기**</span><span class="sxs-lookup"><span data-stu-id="6232f-142">**Get the most complete coverage**</span></span> | <span data-ttu-id="6232f-143">감사 설정을 사용하여 조직에 더 나은 데이터 범위를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6232f-143">Use audit settings to provide better data coverage for your organization.</span></span> | <span data-ttu-id="6232f-144">- [고급 헌팅 범위 확장](advanced-hunting-extend-data.md)</span><span class="sxs-lookup"><span data-stu-id="6232f-144">- [Extend advanced hunting coverage](advanced-hunting-extend-data.md)</span></span> |
| <span data-ttu-id="6232f-145">**빠른 조사 실행**</span><span class="sxs-lookup"><span data-stu-id="6232f-145">**Run a quick investigation**</span></span> | <span data-ttu-id="6232f-146">고급 헌팅 쿼리를 빠르게 실행하여 의심스러운 활동을 조사합니다.</span><span class="sxs-lookup"><span data-stu-id="6232f-146">Quickly run an advanced hunting query to investigate suspicious activity.</span></span> | <span data-ttu-id="6232f-147">- [이동 헌트로 엔터티 또는 이벤트 정보를 빠르게 *헌팅*](advanced-hunting-go-hunt.md)</span><span class="sxs-lookup"><span data-stu-id="6232f-147">- [Quickly hunt for entity or event information with *go hunt*](advanced-hunting-go-hunt.md)</span></span> |
| <span data-ttu-id="6232f-148">**위협 및 해결 손상 포함**</span><span class="sxs-lookup"><span data-stu-id="6232f-148">**Contain threats and address compromises**</span></span> | <span data-ttu-id="6232f-149">파일을 검색하고, 앱 실행을 제한하고, 기타 작업을 수행하여 공격에 대응</span><span class="sxs-lookup"><span data-stu-id="6232f-149">Respond to attacks by quarantining files, restricting app execution, and other actions</span></span> | <span data-ttu-id="6232f-150">- [고급 헌팅 쿼리 결과에 대한 작업 수행](advanced-hunting-take-action.md)</span><span class="sxs-lookup"><span data-stu-id="6232f-150">- [Take action on advanced hunting query results](advanced-hunting-take-action.md)</span></span> |
| <span data-ttu-id="6232f-151">**사용자 지정 검색 규칙 만들기**</span><span class="sxs-lookup"><span data-stu-id="6232f-151">**Create custom detection rules**</span></span> | <span data-ttu-id="6232f-152">고급 헌팅 쿼리를 사용하여 경고를 트리거하고 응답 작업을 자동으로 수행할 수 있는 방법을 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="6232f-152">Understand how you can use advanced hunting queries to trigger alerts and take response actions automatically.</span></span> | <span data-ttu-id="6232f-153">- [사용자 지정 검색 개요](overview-custom-detections.md)</span><span class="sxs-lookup"><span data-stu-id="6232f-153">- [Custom detections overview](overview-custom-detections.md)</span></span><br><span data-ttu-id="6232f-154">- [사용자 지정 검색 규칙](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="6232f-154">- [Custom detection rules](custom-detection-rules.md)</span></span> |

## <a name="data-freshness-and-update-frequency"></a><span data-ttu-id="6232f-155">데이터 최신성 및 업데이트 빈도</span><span class="sxs-lookup"><span data-stu-id="6232f-155">Data freshness and update frequency</span></span>

<span data-ttu-id="6232f-156">고급 헌팅 데이터는 서로 다른 두 가지 유형으로 분류할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6232f-156">Advanced hunting data can be categorized into two distinct types, each consolidated differently.</span></span>

- <span data-ttu-id="6232f-157">**이벤트 또는 활동 데이터**- 경고, 보안 이벤트, 시스템 이벤트 및 일상적인 평가에 대한 테이블을 채우습니다.</span><span class="sxs-lookup"><span data-stu-id="6232f-157">**Event or activity data**—populates tables about alerts, security events, system events, and routine assessments.</span></span> <span data-ttu-id="6232f-158">고급 헌팅은 이를 수집하는 센서가 끝점용 Defender로 성공적으로 전송된 직후에 이 데이터를 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="6232f-158">Advanced hunting receives this data almost immediately after the sensors that collect them successfully transmit them to Defender for Endpoint.</span></span>
- <span data-ttu-id="6232f-159">**엔터티 데이터**- 사용자 및 장치에 대한 통합 정보로 테이블을 채우는 경우</span><span class="sxs-lookup"><span data-stu-id="6232f-159">**Entity data**—populates tables with consolidated information about users and devices.</span></span> <span data-ttu-id="6232f-160">이 데이터는 Active Directory 항목 및 이벤트 로그와 같은 비교적 정적 데이터 원본과 동적 원본 모두에서 온 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6232f-160">This data comes from both relatively static data sources and dynamic sources, such as Active Directory entries and event logs.</span></span> <span data-ttu-id="6232f-161">새 데이터를 제공하기 위해 표는 15분마다 모든 새 정보로 업데이트되어 완전히 채워지지 않을 수 있는 행을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6232f-161">To provide fresh data, tables are updated with any new information every 15 minutes, adding rows that might not be fully populated.</span></span> <span data-ttu-id="6232f-162">24시간마다 데이터가 통합되어 각 엔터티에 대한 가장 포괄적인 최신 데이터 집합이 포함된 레코드를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="6232f-162">Every 24 hours, data is consolidated to insert a record that contains the latest, most comprehensive data set about each entity.</span></span>

## <a name="time-zone"></a><span data-ttu-id="6232f-163">표준 시간대</span><span class="sxs-lookup"><span data-stu-id="6232f-163">Time zone</span></span>

<span data-ttu-id="6232f-164">고급 헌팅의 시간 정보는 현재 UTC 표준 시간대에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6232f-164">Time information in advanced hunting is currently in the UTC time zone.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6232f-165">관련 항목</span><span class="sxs-lookup"><span data-stu-id="6232f-165">Related topics</span></span>

- [<span data-ttu-id="6232f-166">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="6232f-166">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="6232f-167">쿼리 결과로 작업</span><span class="sxs-lookup"><span data-stu-id="6232f-167">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="6232f-168">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="6232f-168">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="6232f-169">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="6232f-169">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="6232f-170">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="6232f-170">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="6232f-171">사용자 지정 검색 개요</span><span class="sxs-lookup"><span data-stu-id="6232f-171">Custom detections overview</span></span>](overview-custom-detections.md)