---
title: 고급 구하기 스키마의 AppFileEvents 테이블
description: 고급 구하기 스키마의 AppFileEvents 테이블에 있는 클라우드 앱 및 서비스와 연결 된 파일 관련 이벤트에 대해 자세히 알아봅니다.
keywords: 고급 구하기, 위협 검색, 사이버 위협 검색, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 스키마 참조, kusto, table, column, data type, description, AppFileEvents, Cloud App Security, MCAS
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
ms.openlocfilehash: da3b331d4f607aa0961e275db9444aadbec4fcf2
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899342"
---
# <a name="appfileevents"></a><span data-ttu-id="56933-104">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="56933-104">AppFileEvents</span></span>

<span data-ttu-id="56933-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="56933-105">**Applies to:**</span></span>
- <span data-ttu-id="56933-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="56933-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="56933-107">`AppFileEvents` [고급 구하기](advanced-hunting-overview.md) 스키마의 표에는 Microsoft cloud App Security에서 모니터링 하는 클라우드 앱 및 서비스의 파일 관련 작업에 대 한 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56933-107">The `AppFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file-related activities in cloud apps and services monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="56933-108">이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="56933-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="56933-109">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="56933-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="56933-110">열 이름</span><span class="sxs-lookup"><span data-stu-id="56933-110">Column name</span></span> | <span data-ttu-id="56933-111">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="56933-111">Data type</span></span> | <span data-ttu-id="56933-112">설명</span><span class="sxs-lookup"><span data-stu-id="56933-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="56933-113">datetime</span><span class="sxs-lookup"><span data-stu-id="56933-113">datetime</span></span> | <span data-ttu-id="56933-114">이벤트가 기록된 날짜와 시간</span><span class="sxs-lookup"><span data-stu-id="56933-114">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="56933-115">문자열</span><span class="sxs-lookup"><span data-stu-id="56933-115">string</span></span> | <span data-ttu-id="56933-116">이벤트를 트리거한 작업의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="56933-116">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="56933-117">문자열</span><span class="sxs-lookup"><span data-stu-id="56933-117">string</span></span> | <span data-ttu-id="56933-118">기록 된 작업을 수행한 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="56933-118">Application that performed the recorded action</span></span> |
| `FileName` | <span data-ttu-id="56933-119">문자열</span><span class="sxs-lookup"><span data-stu-id="56933-119">string</span></span> | <span data-ttu-id="56933-120">기록된 조치가 적용된 파일의 이름</span><span class="sxs-lookup"><span data-stu-id="56933-120">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="56933-121">문자열</span><span class="sxs-lookup"><span data-stu-id="56933-121">string</span></span> | <span data-ttu-id="56933-122">기록 된 작업이 적용 된 파일을 포함 하는 폴더</span><span class="sxs-lookup"><span data-stu-id="56933-122">Folder containing the file that the recorded action was applied to</span></span> |
| `PreviousFileName` | <span data-ttu-id="56933-123">문자열</span><span class="sxs-lookup"><span data-stu-id="56933-123">string</span></span> | <span data-ttu-id="56933-124">동작의 결과로 이름이 바뀐 파일의 원래 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="56933-124">Original name of the file that was renamed as a result of the action</span></span> |
| `AccountName` | <span data-ttu-id="56933-125">문자열</span><span class="sxs-lookup"><span data-stu-id="56933-125">string</span></span> | <span data-ttu-id="56933-126">계정의 사용자 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="56933-126">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="56933-127">문자열</span><span class="sxs-lookup"><span data-stu-id="56933-127">string</span></span> | <span data-ttu-id="56933-128">계정의 도메인</span><span class="sxs-lookup"><span data-stu-id="56933-128">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="56933-129">문자열</span><span class="sxs-lookup"><span data-stu-id="56933-129">string</span></span> | <span data-ttu-id="56933-130">계정의 UPN (사용자 계정 이름)</span><span class="sxs-lookup"><span data-stu-id="56933-130">User principal name (UPN) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="56933-131">문자열</span><span class="sxs-lookup"><span data-stu-id="56933-131">string</span></span> | <span data-ttu-id="56933-132">Azure AD의 계정에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="56933-132">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="56933-133">문자열</span><span class="sxs-lookup"><span data-stu-id="56933-133">string</span></span> | <span data-ttu-id="56933-134">주소록에 표시 되는 계정 사용자의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="56933-134">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="56933-135">일반적으로 주어진 이름이 나 이름, 중간 시작, 성 또는 성의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="56933-135">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `IPAddress` | <span data-ttu-id="56933-136">문자열</span><span class="sxs-lookup"><span data-stu-id="56933-136">string</span></span> | <span data-ttu-id="56933-137">끝점에 할당 되 고 관련 네트워크 통신 중에 사용 되는 IP 주소</span><span class="sxs-lookup"><span data-stu-id="56933-137">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Location` | <span data-ttu-id="56933-138">문자열</span><span class="sxs-lookup"><span data-stu-id="56933-138">string</span></span> | <span data-ttu-id="56933-139">이벤트와 관련 된 구/군/시, 국가 또는 기타 지리적 위치</span><span class="sxs-lookup"><span data-stu-id="56933-139">City, country, or other geographic location associated with the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="56933-140">관련 항목</span><span class="sxs-lookup"><span data-stu-id="56933-140">Related topics</span></span>
- [<span data-ttu-id="56933-141">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="56933-141">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="56933-142">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="56933-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="56933-143">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="56933-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="56933-144">여러 장치 및 전자 메일에서 위협을 탐지</span><span class="sxs-lookup"><span data-stu-id="56933-144">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="56933-145">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="56933-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="56933-146">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="56933-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
