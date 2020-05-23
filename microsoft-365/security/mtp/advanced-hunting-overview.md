---
title: 개요-고급 구하기
description: Microsoft 365의 고급 검색 쿼리와 이를 사용하여 네트워크의 위협과 약점을 사전에 찾는 방법에 대해 알아보세요.
keywords: 고급 구하기, 위협 검색, 사이버 위협 요소 검색, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 사용자 지정 검색, 스키마, kusto, microsoft 365 및 microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3e8f83b943e83c37ecf13af1221c043d413bd6b5
ms.sourcegitcommit: 8d9509e617ede7cc5ba933c54fb9300d2d1c6344
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2020
ms.locfileid: "44347834"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-threat-protection"></a><span data-ttu-id="9745a-104">Microsoft Threat Protection의 고급 헌팅을 통한 위협에 대한 사전 대응</span><span class="sxs-lookup"><span data-stu-id="9745a-104">Proactively hunt for threats with advanced hunting in Microsoft Threat Protection</span></span>

<span data-ttu-id="9745a-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="9745a-105">**Applies to:**</span></span>
- <span data-ttu-id="9745a-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="9745a-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="9745a-107">고급 헌팅은 최대 30일간의 원시 데이터를 탐색할 수 있는 쿼리 기반의 위협 헌팅 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="9745a-107">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data.</span></span> <span data-ttu-id="9745a-108">네트워크의 이벤트를 사전에 검사하여 흥미로운 지표와 엔티티를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9745a-108">You can proactively inspect events in your network to locate interesting indicators and entities.</span></span> <span data-ttu-id="9745a-109">데이터에 대한 유연한 액세스는 알려진 위협과 잠재적 위협 모두에 대한 제한없는 헌팅을 용이하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="9745a-109">The flexible access to data facilitates unconstrained hunting for both known and potential threats.</span></span>

<span data-ttu-id="9745a-110">동일한 위협 검색 쿼리를 사용 하 여 사용자 지정 검색 규칙을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9745a-110">You can use the same threat-hunting queries to build custom detection rules.</span></span> <span data-ttu-id="9745a-111">이러한 규칙은 의심 스러운 위반 활동 및 잘못 된 컴퓨터를 포함 하 여 다양 한 이벤트 및 시스템 상태를 확인 하 고 응답 하기 위해 자동으로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9745a-111">These rules run automatically to check for and respond to various events and system states, including suspected breach activity and misconfigured machines.</span></span>

<span data-ttu-id="9745a-112">Microsoft 365 보안 센터에서 고급 구하기는 장치, 전자 메일, 앱 및 Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security 및 Azure ATP의 id에 대 한 데이터를 포함 하 여 다양 한 작업 영역의 데이터를 확인 하는 쿼리를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="9745a-112">In the Microsoft 365 security center, advanced hunting supports queries that look into data from various workspaces, including data about devices, emails, apps, and identities from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="9745a-113">고급 헌팅을 사용하려면 [Microsoft Threat Protection](mtp-enable.md)을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9745a-113">To use advanced hunting, [turn on Microsoft Threat Protection](mtp-enable.md).</span></span>

## <a name="get-started-with-advanced-hunting"></a><span data-ttu-id="9745a-114">고급 헌팅 시작</span><span class="sxs-lookup"><span data-stu-id="9745a-114">Get started with advanced hunting</span></span>

<span data-ttu-id="9745a-115">고급 헌팅을 빠르게 시작하고 실행하려면 몇가지 단계를 수행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9745a-115">We recommend going through several steps to quickly get up and running with advanced hunting.</span></span>

| <span data-ttu-id="9745a-116">학습 목표</span><span class="sxs-lookup"><span data-stu-id="9745a-116">Learning goal</span></span> | <span data-ttu-id="9745a-117">설명</span><span class="sxs-lookup"><span data-stu-id="9745a-117">Description</span></span> | <span data-ttu-id="9745a-118">리소스</span><span class="sxs-lookup"><span data-stu-id="9745a-118">Resource</span></span> |
|--|--|--|
| <span data-ttu-id="9745a-119">**언어에 대한 느낌을 받아보세요.**</span><span class="sxs-lookup"><span data-stu-id="9745a-119">**Get a feel for the language**</span></span> | <span data-ttu-id="9745a-120">고급 헌팅은 [Kusto 쿼리 언어](https://docs.microsoft.com/azure/kusto/query/)을 기반으로 하며, 동일한 구문 및 연산자를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="9745a-120">Advanced hunting is based on the [Kusto query language](https://docs.microsoft.com/azure/kusto/query/), supporting the same syntax and operators.</span></span> <span data-ttu-id="9745a-121">첫 번째 쿼리를 실행하여 쿼리 언어 학습을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="9745a-121">Start learning the query language by running your first query.</span></span> | [<span data-ttu-id="9745a-122">쿼리 언어 개요</span><span class="sxs-lookup"><span data-stu-id="9745a-122">Query language overview</span></span>](advanced-hunting-query-language.md) |
| <span data-ttu-id="9745a-123">**쿼리 결과 사용 방법 알아보기**</span><span class="sxs-lookup"><span data-stu-id="9745a-123">**Learn how to use the query results**</span></span> | <span data-ttu-id="9745a-124">결과를 보거나 내보낼 수 있는 다양 한 방법과 차트에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="9745a-124">Learn about charts and various ways you can view or export your results.</span></span> <span data-ttu-id="9745a-125">쿼리를 신속 하 게 조정 하 고 드릴 다운 하 여 보다 다양 한 정보를 얻을 수 있는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="9745a-125">Explore how you can quickly tweak queries and drill down to get richer information.</span></span> | [<span data-ttu-id="9745a-126">쿼리 결과 작업</span><span class="sxs-lookup"><span data-stu-id="9745a-126">Work with query results</span></span>](advanced-hunting-query-results.md) |
| <span data-ttu-id="9745a-127">**스키마의 이해**</span><span class="sxs-lookup"><span data-stu-id="9745a-127">**Understand the schema**</span></span> | <span data-ttu-id="9745a-128">스키마와 해당 열에 있는 테이블에 대한 이해를 높이세요.</span><span class="sxs-lookup"><span data-stu-id="9745a-128">Get a good, high-level understanding of the tables in the schema and their columns.</span></span> <span data-ttu-id="9745a-129">이는 데이터를 찾을 위치와 쿼리를 구성하는 방법을 결정하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9745a-129">This will help you determine where to look for data and how to construct your queries.</span></span> | [<span data-ttu-id="9745a-130">스키마 참조</span><span class="sxs-lookup"><span data-stu-id="9745a-130">Schema reference</span></span>](advanced-hunting-schema-tables.md) |
| <span data-ttu-id="9745a-131">**미리 정의 된 쿼리 활용**</span><span class="sxs-lookup"><span data-stu-id="9745a-131">**Leverage predefined queries**</span></span> | <span data-ttu-id="9745a-132">다양한 위협 헌팅 시나리오를 다루는 미리 정의된 쿼리 모음을 탐색합니다.</span><span class="sxs-lookup"><span data-stu-id="9745a-132">Explore collections of predefined queries covering different threat hunting scenarios.</span></span> | [<span data-ttu-id="9745a-133">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="9745a-133">Use shared queries</span></span>](advanced-hunting-shared-queries.md) |
| <span data-ttu-id="9745a-134">**쿼리 최적화**</span><span class="sxs-lookup"><span data-stu-id="9745a-134">**Optimize queries**</span></span> | <span data-ttu-id="9745a-135">전자 메일 및 장치에서 데이터를 결합하는 효율적인 쿼리 및 쿼리를 만드는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="9745a-135">Understand how to create efficient queries and queries that combine data from emails and devices.</span></span> | <span data-ttu-id="9745a-136">- [쿼리 모범 사례](advanced-hunting-shared-queries.md)</span><span class="sxs-lookup"><span data-stu-id="9745a-136">- [Query best practices](advanced-hunting-shared-queries.md)</span></span> <br><span data-ttu-id="9745a-137">- [장치 및 전자 메일 간 헌트](advanced-hunting-best-practices.md)</span><span class="sxs-lookup"><span data-stu-id="9745a-137">- [Hunt across devices and emails](advanced-hunting-best-practices.md)</span></span> |
| <span data-ttu-id="9745a-138">**사용자 지정 검색 규칙 만들기**</span><span class="sxs-lookup"><span data-stu-id="9745a-138">**Create custom detection rules**</span></span> | <span data-ttu-id="9745a-139">고급 구하기 쿼리를 사용 하 여 알림을 트리거하고 응답 작업을 자동으로 적용 하는 방법을 이해 합니다.</span><span class="sxs-lookup"><span data-stu-id="9745a-139">Understand how you can use advanced hunting queries to trigger alerts and apply response actions automatically.</span></span> | <span data-ttu-id="9745a-140">- [사용자 지정 검색 개요](custom-detections-overview.md)</span><span class="sxs-lookup"><span data-stu-id="9745a-140">- [Custom detections overview](custom-detections-overview.md)</span></span><br><span data-ttu-id="9745a-141">- [사용자 지정 검색 규칙](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="9745a-141">- [Custom detection rules](custom-detection-rules.md)</span></span> |

## <a name="get-access"></a><span data-ttu-id="9745a-142">액세스 권한</span><span class="sxs-lookup"><span data-stu-id="9745a-142">Get access</span></span>
<span data-ttu-id="9745a-143">고급 구하기 또는 기타 [Microsoft 위협 방지](microsoft-threat-protection.md) 기능을 사용 하려면 Azure AD에서 적절 한 역할을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9745a-143">To use advanced hunting or other [Microsoft Threat Protection](microsoft-threat-protection.md) capabilities, you need to be assigned an appropriate role in Azure AD.</span></span> <span data-ttu-id="9745a-144">끝점 데이터에 대 한 액세스는 Microsoft Defender ATP에서 역할 기반 액세스 제어 설정의 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="9745a-144">Note that your access to endpoint data is influenced by role-based access control settings in Microsoft Defender ATP.</span></span> [<span data-ttu-id="9745a-145">Microsoft Threat Protection 액세스 관리에 대해 자세히 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="9745a-145">Read about managing access to Microsoft Threat Protection</span></span>](mtp-permissions.md)

## <a name="get-help-as-you-write-queries"></a><span data-ttu-id="9745a-146">쿼리 작성시 도움말 보기</span><span class="sxs-lookup"><span data-stu-id="9745a-146">Get help as you write queries</span></span>
<span data-ttu-id="9745a-147">다음 기능을 활용하여 쿼리를 더 빠르게 작성하세요.</span><span class="sxs-lookup"><span data-stu-id="9745a-147">Take advantage of the following functionality to write queries faster:</span></span>
- <span data-ttu-id="9745a-148">**Autosuggest** -쿼리를 작성할 때 고급 사냥은 IntelliSense의 추천 단어를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9745a-148">**Autosuggest** — as you write queries, advanced hunting provides suggestions from IntelliSense.</span></span> 
- <span data-ttu-id="9745a-149">**스키마 참조** — 테이블 및 해당 열 목록이 포함된 스키마 참조가 작업 영역 옆에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="9745a-149">**Schema reference** — a schema reference that includes the list of tables and their columns is provided next to your working area.</span></span> <span data-ttu-id="9745a-150">자세한 내용을 보려면 항목 위로 마우스를 가져갑니다.</span><span class="sxs-lookup"><span data-stu-id="9745a-150">For more information, hover over an item.</span></span> <span data-ttu-id="9745a-151">항목을 두 번 클릭하여 쿼리 편집기에 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="9745a-151">Double-click an item to insert it to the query editor.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9745a-152">관련 항목</span><span class="sxs-lookup"><span data-stu-id="9745a-152">Related topics</span></span>
- [<span data-ttu-id="9745a-153">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="9745a-153">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="9745a-154">쿼리 결과 작업</span><span class="sxs-lookup"><span data-stu-id="9745a-154">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="9745a-155">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="9745a-155">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="9745a-156">여러 장치 및 전자 메일에서 위협을 탐지</span><span class="sxs-lookup"><span data-stu-id="9745a-156">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="9745a-157">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="9745a-157">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="9745a-158">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="9745a-158">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="9745a-159">사용자 지정 검색 개요</span><span class="sxs-lookup"><span data-stu-id="9745a-159">Custom detections overview</span></span>](custom-detections-overview.md)
