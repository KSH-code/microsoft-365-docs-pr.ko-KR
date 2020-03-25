---
title: 고급 구하기 스키마의 IdentityQueryEvents 테이블
description: 고급 검색 스키마의 IdentityQueryEvents 테이블에 있는 Active Directory 쿼리 이벤트에 대해 자세히 알아보기
keywords: 고급 구하기, 위협 검색, 사이버 위협 사냥, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 스키마 참조, kusto, table, description, IdentityQueryEvents, Azure AD, Active Directory, Azure ATP, id, LDAP 쿼리
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
ms.openlocfilehash: b2fc94d6ac6606c97b4824bc556b7299a2bd8ec7
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929272"
---
# <a name="identityqueryevents"></a><span data-ttu-id="ea8bf-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="ea8bf-104">IdentityQueryEvents</span></span>

<span data-ttu-id="ea8bf-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="ea8bf-105">**Applies to:**</span></span>
- <span data-ttu-id="ea8bf-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="ea8bf-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="ea8bf-107">`IdentityQueryEvents` [고급 구하기](advanced-hunting-overview.md) 스키마의 표에는 Active Directory 개체 (예: 사용자, 그룹, 장치 및 도메인)에 대해 수행 된 쿼리에 대 한 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea8bf-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="ea8bf-108">이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ea8bf-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="ea8bf-109">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ea8bf-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="ea8bf-110">열 이름</span><span class="sxs-lookup"><span data-stu-id="ea8bf-110">Column name</span></span> | <span data-ttu-id="ea8bf-111">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="ea8bf-111">Data type</span></span> | <span data-ttu-id="ea8bf-112">설명</span><span class="sxs-lookup"><span data-stu-id="ea8bf-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="ea8bf-113">datetime</span><span class="sxs-lookup"><span data-stu-id="ea8bf-113">datetime</span></span> | <span data-ttu-id="ea8bf-114">이벤트가 기록된 날짜와 시간</span><span class="sxs-lookup"><span data-stu-id="ea8bf-114">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="ea8bf-115">문자열</span><span class="sxs-lookup"><span data-stu-id="ea8bf-115">string</span></span> | <span data-ttu-id="ea8bf-116">이벤트를 트리거한 작업의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="ea8bf-116">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="ea8bf-117">문자열</span><span class="sxs-lookup"><span data-stu-id="ea8bf-117">string</span></span> | <span data-ttu-id="ea8bf-118">기록 된 작업을 수행한 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="ea8bf-118">Application that performed the recorded action</span></span> |
| `Query` | <span data-ttu-id="ea8bf-119">문자열</span><span class="sxs-lookup"><span data-stu-id="ea8bf-119">string</span></span> | <span data-ttu-id="ea8bf-120">쿼리 유형: QueryGroup, Querygroup 또는 EnumerateUsers</span><span class="sxs-lookup"><span data-stu-id="ea8bf-120">Type of query: QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryObject` | <span data-ttu-id="ea8bf-121">문자열</span><span class="sxs-lookup"><span data-stu-id="ea8bf-121">string</span></span> | <span data-ttu-id="ea8bf-122">쿼리 중인 사용자, 그룹, 장치, 도메인 또는 기타 모든 엔터티 유형의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ea8bf-122">Name of the user, group, device, domain, or any other entity type being queried</span></span> |
| `Protocol` | <span data-ttu-id="ea8bf-123">문자열</span><span class="sxs-lookup"><span data-stu-id="ea8bf-123">string</span></span> | <span data-ttu-id="ea8bf-124">통신 중에 사용 되는 프로토콜</span><span class="sxs-lookup"><span data-stu-id="ea8bf-124">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="ea8bf-125">문자열</span><span class="sxs-lookup"><span data-stu-id="ea8bf-125">string</span></span> | <span data-ttu-id="ea8bf-126">계정의 사용자 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ea8bf-126">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="ea8bf-127">문자열</span><span class="sxs-lookup"><span data-stu-id="ea8bf-127">string</span></span> | <span data-ttu-id="ea8bf-128">계정의 도메인</span><span class="sxs-lookup"><span data-stu-id="ea8bf-128">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="ea8bf-129">문자열</span><span class="sxs-lookup"><span data-stu-id="ea8bf-129">string</span></span> | <span data-ttu-id="ea8bf-130">계정의 UPN (사용자 계정 이름)</span><span class="sxs-lookup"><span data-stu-id="ea8bf-130">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="ea8bf-131">문자열</span><span class="sxs-lookup"><span data-stu-id="ea8bf-131">string</span></span> | <span data-ttu-id="ea8bf-132">계정의 SID (보안 식별자)</span><span class="sxs-lookup"><span data-stu-id="ea8bf-132">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="ea8bf-133">문자열</span><span class="sxs-lookup"><span data-stu-id="ea8bf-133">string</span></span> | <span data-ttu-id="ea8bf-134">Azure AD의 계정에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="ea8bf-134">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="ea8bf-135">문자열</span><span class="sxs-lookup"><span data-stu-id="ea8bf-135">string</span></span> | <span data-ttu-id="ea8bf-136">주소록에 표시 되는 계정 사용자의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ea8bf-136">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="ea8bf-137">일반적으로 주어진 이름이 나 이름, 중간 시작, 성 또는 성의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="ea8bf-137">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="ea8bf-138">문자열</span><span class="sxs-lookup"><span data-stu-id="ea8bf-138">string</span></span> | <span data-ttu-id="ea8bf-139">끝점의 FQDN (정규화 된 도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="ea8bf-139">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="ea8bf-140">문자열</span><span class="sxs-lookup"><span data-stu-id="ea8bf-140">string</span></span> | <span data-ttu-id="ea8bf-141">끝점에 할당 되 고 관련 네트워크 통신 중에 사용 되는 IP 주소</span><span class="sxs-lookup"><span data-stu-id="ea8bf-141">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Location` | <span data-ttu-id="ea8bf-142">문자열</span><span class="sxs-lookup"><span data-stu-id="ea8bf-142">string</span></span> | <span data-ttu-id="ea8bf-143">이벤트와 관련 된 구/군/시, 국가 또는 기타 지리적 위치</span><span class="sxs-lookup"><span data-stu-id="ea8bf-143">City, country, or other geographic location associated with the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="ea8bf-144">관련 항목</span><span class="sxs-lookup"><span data-stu-id="ea8bf-144">Related topics</span></span>
- [<span data-ttu-id="ea8bf-145">사전 대응식 위협 탐지</span><span class="sxs-lookup"><span data-stu-id="ea8bf-145">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ea8bf-146">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="ea8bf-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="ea8bf-147">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="ea8bf-147">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="ea8bf-148">여러 장치 및 전자 메일에서 위협을 탐지</span><span class="sxs-lookup"><span data-stu-id="ea8bf-148">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="ea8bf-149">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="ea8bf-149">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="ea8bf-150">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="ea8bf-150">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
