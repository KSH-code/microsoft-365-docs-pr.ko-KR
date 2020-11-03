---
title: 고급 구하기 스키마의 AlertInfo 테이블
description: 고급 구하기 스키마의 AlertInfo 테이블에 있는 경고 생성 이벤트에 대해 자세히 알아보기
keywords: 고급 구하기, 위협 사냥 사이버 위협 검색, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 스키마 참조, kusto, table, column, AlertInfo, alert,, category, MITRE, AT&T&머리, Microsoft Defender ATP, MDATP, Office 365 ATP, Microsoft Cloud App Security, MCAS 및 Azure ATP
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 7672d974666a381a48da15e0917a46c97df88895
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847671"
---
# <a name="alertinfo"></a><span data-ttu-id="5bbc8-104">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="5bbc8-104">AlertInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="5bbc8-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="5bbc8-105">**Applies to:**</span></span>
- <span data-ttu-id="5bbc8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5bbc8-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="5bbc8-107">`AlertInfo` [고급 구하기](advanced-hunting-overview.md) 스키마의 표에는 끝점에 대 한 microsoft Defender, Microsoft defender for Office 365, Microsoft Cloud App Security 및 Identity 용 microsoft defender의 경고에 대 한 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bbc8-107">The `AlertInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about alerts from Microsoft  Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="5bbc8-108">이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="5bbc8-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="5bbc8-109">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5bbc8-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="5bbc8-110">열 이름</span><span class="sxs-lookup"><span data-stu-id="5bbc8-110">Column name</span></span> | <span data-ttu-id="5bbc8-111">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="5bbc8-111">Data type</span></span> | <span data-ttu-id="5bbc8-112">설명</span><span class="sxs-lookup"><span data-stu-id="5bbc8-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="5bbc8-113">datetime</span><span class="sxs-lookup"><span data-stu-id="5bbc8-113">datetime</span></span> | <span data-ttu-id="5bbc8-114">이벤트가 기록된 날짜와 시간</span><span class="sxs-lookup"><span data-stu-id="5bbc8-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="5bbc8-115">문자열</span><span class="sxs-lookup"><span data-stu-id="5bbc8-115">string</span></span> | <span data-ttu-id="5bbc8-116">경고의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="5bbc8-116">Unique identifier for the alert</span></span> |
| `Title` | <span data-ttu-id="5bbc8-117">문자열</span><span class="sxs-lookup"><span data-stu-id="5bbc8-117">string</span></span> | <span data-ttu-id="5bbc8-118">경고의 제목입니다.</span><span class="sxs-lookup"><span data-stu-id="5bbc8-118">Title of the alert</span></span> |
| `Category` | <span data-ttu-id="5bbc8-119">문자열</span><span class="sxs-lookup"><span data-stu-id="5bbc8-119">string</span></span> | <span data-ttu-id="5bbc8-120">경고로 식별되는 위협 표시기 또는 위반 활동 유형</span><span class="sxs-lookup"><span data-stu-id="5bbc8-120">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Severity` | <span data-ttu-id="5bbc8-121">문자열</span><span class="sxs-lookup"><span data-stu-id="5bbc8-121">string</span></span> | <span data-ttu-id="5bbc8-122">경고로 식별되는 위협 표시기 또는 위반 활동의 잠재적인 영향(높음, 중간 또는 낮음)을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5bbc8-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="5bbc8-123">문자열</span><span class="sxs-lookup"><span data-stu-id="5bbc8-123">string</span></span> | <span data-ttu-id="5bbc8-124">경고 정보를 제공한 제품 또는 서비스</span><span class="sxs-lookup"><span data-stu-id="5bbc8-124">Product or service that provided the alert information</span></span> |
| `DetectionSource` | <span data-ttu-id="5bbc8-125">문자열</span><span class="sxs-lookup"><span data-stu-id="5bbc8-125">string</span></span> | <span data-ttu-id="5bbc8-126">중요 한 구성 요소 또는 활동을 식별 한 검색 기술 또는 센서</span><span class="sxs-lookup"><span data-stu-id="5bbc8-126">Detection technology or sensor that identified the notable component or activity</span></span> |
| `AttackTechniques` | <span data-ttu-id="5bbc8-127">문자열</span><span class="sxs-lookup"><span data-stu-id="5bbc8-127">string</span></span> | <span data-ttu-id="5bbc8-128">경고를 트리거한 활동에 연결 된 MITRE AT&T&접시 헤드 기술</span><span class="sxs-lookup"><span data-stu-id="5bbc8-128">MITRE ATT&CK techniques associated with the activity that triggered the alert</span></span> |

## <a name="related-topics"></a><span data-ttu-id="5bbc8-129">관련 항목</span><span class="sxs-lookup"><span data-stu-id="5bbc8-129">Related topics</span></span>
- [<span data-ttu-id="5bbc8-130">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="5bbc8-130">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="5bbc8-131">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="5bbc8-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="5bbc8-132">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="5bbc8-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="5bbc8-133">기기, 전자 메일, 앱 및 ID를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="5bbc8-133">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="5bbc8-134">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="5bbc8-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="5bbc8-135">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="5bbc8-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
