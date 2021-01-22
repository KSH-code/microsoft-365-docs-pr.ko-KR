---
title: 고급 헌팅chema의 AlertInfo 표
description: 고급 헌팅 스마의 AlertInfo 표에서 경고 생성 이벤트에 대해 자세히 알아보기
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 위협 방지, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, schema reference, kusto, 표, 열, 데이터 형식, 설명, AlertInfo, 경고, 심각도, 범주, MITRE, ATT&CK, Microsoft Defender ATP, MDATP, Office 365 ATP, Microsoft Cloud App Security, MCAS 및 Azure ATP
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: ac1e28987a944a8f7786af4f10a85362f2f92a80
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929973"
---
# <a name="alertinfo"></a><span data-ttu-id="01a12-104">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="01a12-104">AlertInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="01a12-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="01a12-105">**Applies to:**</span></span>
- <span data-ttu-id="01a12-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="01a12-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="01a12-107">고급 헌팅의 표에는 `AlertInfo` 끝점용 Microsoft Defender, Office 365용 Microsoft Defender, Microsoft Cloud App Security 및 ID용 Microsoft Defender의 경고에 대한 정보가 포함되어 있습니다. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="01a12-107">The `AlertInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about alerts from Microsoft  Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="01a12-108">이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="01a12-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="01a12-109">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="01a12-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="01a12-110">열 이름</span><span class="sxs-lookup"><span data-stu-id="01a12-110">Column name</span></span> | <span data-ttu-id="01a12-111">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="01a12-111">Data type</span></span> | <span data-ttu-id="01a12-112">설명</span><span class="sxs-lookup"><span data-stu-id="01a12-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="01a12-113">datetime</span><span class="sxs-lookup"><span data-stu-id="01a12-113">datetime</span></span> | <span data-ttu-id="01a12-114">이벤트가 기록된 날짜와 시간</span><span class="sxs-lookup"><span data-stu-id="01a12-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="01a12-115">문자열</span><span class="sxs-lookup"><span data-stu-id="01a12-115">string</span></span> | <span data-ttu-id="01a12-116">경고의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="01a12-116">Unique identifier for the alert</span></span> |
| `Title` | <span data-ttu-id="01a12-117">문자열</span><span class="sxs-lookup"><span data-stu-id="01a12-117">string</span></span> | <span data-ttu-id="01a12-118">경고의 제목입니다.</span><span class="sxs-lookup"><span data-stu-id="01a12-118">Title of the alert</span></span> |
| `Category` | <span data-ttu-id="01a12-119">문자열</span><span class="sxs-lookup"><span data-stu-id="01a12-119">string</span></span> | <span data-ttu-id="01a12-120">경고로 식별되는 위협 표시기 또는 위반 활동 유형</span><span class="sxs-lookup"><span data-stu-id="01a12-120">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Severity` | <span data-ttu-id="01a12-121">문자열</span><span class="sxs-lookup"><span data-stu-id="01a12-121">string</span></span> | <span data-ttu-id="01a12-122">경고로 식별되는 위협 표시기 또는 위반 활동의 잠재적인 영향(높음, 중간 또는 낮음)을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="01a12-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="01a12-123">문자열</span><span class="sxs-lookup"><span data-stu-id="01a12-123">string</span></span> | <span data-ttu-id="01a12-124">경고 정보를 제공한 제품 또는 서비스</span><span class="sxs-lookup"><span data-stu-id="01a12-124">Product or service that provided the alert information</span></span> |
| `DetectionSource` | <span data-ttu-id="01a12-125">문자열</span><span class="sxs-lookup"><span data-stu-id="01a12-125">string</span></span> | <span data-ttu-id="01a12-126">중요한 구성 요소 또는 활동을 식별한 감지 기술 또는 센서</span><span class="sxs-lookup"><span data-stu-id="01a12-126">Detection technology or sensor that identified the notable component or activity</span></span> |
| `AttackTechniques` | <span data-ttu-id="01a12-127">문자열</span><span class="sxs-lookup"><span data-stu-id="01a12-127">string</span></span> | <span data-ttu-id="01a12-128">MITRE ATT&트리거한 활동과 관련된 CK 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="01a12-128">MITRE ATT&CK techniques associated with the activity that triggered the alert</span></span> |

## <a name="related-topics"></a><span data-ttu-id="01a12-129">관련 항목</span><span class="sxs-lookup"><span data-stu-id="01a12-129">Related topics</span></span>
- [<span data-ttu-id="01a12-130">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="01a12-130">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="01a12-131">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="01a12-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="01a12-132">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="01a12-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="01a12-133">장치, 전자 메일, 앱 및 ID를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="01a12-133">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="01a12-134">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="01a12-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="01a12-135">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="01a12-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
