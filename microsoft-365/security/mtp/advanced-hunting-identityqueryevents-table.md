---
title: 고급 구하기 스키마의 IdentityQueryEvents 테이블
description: 고급 검색 스키마의 IdentityQueryEvents 테이블에 있는 Active Directory 쿼리 이벤트에 대해 자세히 알아보기
keywords: 고급 구하기, 위협 검색, 사이버 위협 요소 검색, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 스키마 참조, kusto, table, column, IdentityQueryEvents, Azure AD, Active Directory, Azure ATP, id, LDAP 쿼리
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
ms.openlocfilehash: 436c4d7306f9f5febd614489090a0a10929ba3c9
ms.sourcegitcommit: b4119682bd3c036289e851fff56fde869c816479
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/22/2020
ms.locfileid: "45204878"
---
# <a name="identityqueryevents"></a><span data-ttu-id="16127-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="16127-104">IdentityQueryEvents</span></span>

<span data-ttu-id="16127-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="16127-105">**Applies to:**</span></span>
- <span data-ttu-id="16127-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="16127-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="16127-107">`IdentityQueryEvents` [고급 구하기](advanced-hunting-overview.md) 스키마의 표에는 Active Directory 개체 (예: 사용자, 그룹, 장치 및 도메인)에 대해 수행 된 쿼리에 대 한 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="16127-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="16127-108">이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="16127-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="16127-109">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="16127-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="16127-110">열 이름</span><span class="sxs-lookup"><span data-stu-id="16127-110">Column name</span></span> | <span data-ttu-id="16127-111">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="16127-111">Data type</span></span> | <span data-ttu-id="16127-112">설명</span><span class="sxs-lookup"><span data-stu-id="16127-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="16127-113">datetime</span><span class="sxs-lookup"><span data-stu-id="16127-113">datetime</span></span> | <span data-ttu-id="16127-114">이벤트가 기록된 날짜와 시간</span><span class="sxs-lookup"><span data-stu-id="16127-114">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="16127-115">문자열</span><span class="sxs-lookup"><span data-stu-id="16127-115">string</span></span> | <span data-ttu-id="16127-116">이벤트를 트리거한 작업의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="16127-116">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="16127-117">문자열</span><span class="sxs-lookup"><span data-stu-id="16127-117">string</span></span> | <span data-ttu-id="16127-118">기록 된 작업을 수행한 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="16127-118">Application that performed the recorded action</span></span> |
| `QueryType` | <span data-ttu-id="16127-119">문자열</span><span class="sxs-lookup"><span data-stu-id="16127-119">string</span></span> | <span data-ttu-id="16127-120">쿼리 유형 (예: QueryGroup, Querygroup 또는 EnumerateUsers)</span><span class="sxs-lookup"><span data-stu-id="16127-120">Type of query, such as QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryTarget` | <span data-ttu-id="16127-121">문자열</span><span class="sxs-lookup"><span data-stu-id="16127-121">string</span></span> | <span data-ttu-id="16127-122">쿼리 중인 사용자, 그룹, 장치, 도메인 또는 기타 모든 엔터티 유형의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="16127-122">Name of user, group, device, domain, or any other entity type being queried</span></span> |
| `Query` | <span data-ttu-id="16127-123">문자열</span><span class="sxs-lookup"><span data-stu-id="16127-123">string</span></span> | <span data-ttu-id="16127-124">쿼리를 실행 하는 데 사용 되는 문자열</span><span class="sxs-lookup"><span data-stu-id="16127-124">String used to run the query</span></span> |
| `Protocol` | <span data-ttu-id="16127-125">문자열</span><span class="sxs-lookup"><span data-stu-id="16127-125">string</span></span> | <span data-ttu-id="16127-126">통신 중에 사용 되는 프로토콜</span><span class="sxs-lookup"><span data-stu-id="16127-126">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="16127-127">문자열</span><span class="sxs-lookup"><span data-stu-id="16127-127">string</span></span> | <span data-ttu-id="16127-128">계정의 사용자 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="16127-128">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="16127-129">문자열</span><span class="sxs-lookup"><span data-stu-id="16127-129">string</span></span> | <span data-ttu-id="16127-130">계정의 도메인</span><span class="sxs-lookup"><span data-stu-id="16127-130">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="16127-131">문자열</span><span class="sxs-lookup"><span data-stu-id="16127-131">string</span></span> | <span data-ttu-id="16127-132">계정의 UPN (사용자 계정 이름)</span><span class="sxs-lookup"><span data-stu-id="16127-132">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="16127-133">문자열</span><span class="sxs-lookup"><span data-stu-id="16127-133">string</span></span> | <span data-ttu-id="16127-134">계정의 SID (보안 식별자)</span><span class="sxs-lookup"><span data-stu-id="16127-134">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="16127-135">문자열</span><span class="sxs-lookup"><span data-stu-id="16127-135">string</span></span> | <span data-ttu-id="16127-136">Azure AD의 계정에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="16127-136">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="16127-137">문자열</span><span class="sxs-lookup"><span data-stu-id="16127-137">string</span></span> | <span data-ttu-id="16127-138">주소록에 표시 되는 계정 사용자의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="16127-138">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="16127-139">일반적으로 주어진 이름이 나 이름, 중간 시작, 성 또는 성의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="16127-139">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="16127-140">문자열</span><span class="sxs-lookup"><span data-stu-id="16127-140">string</span></span> | <span data-ttu-id="16127-141">끝점의 FQDN (정규화 된 도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="16127-141">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="16127-142">문자열</span><span class="sxs-lookup"><span data-stu-id="16127-142">string</span></span> | <span data-ttu-id="16127-143">끝점에 할당 되 고 관련 네트워크 통신 중에 사용 되는 IP 주소</span><span class="sxs-lookup"><span data-stu-id="16127-143">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="16127-144">문자열</span><span class="sxs-lookup"><span data-stu-id="16127-144">string</span></span> | <span data-ttu-id="16127-145">기록 된 작업을 처리 한 서버 응용 프로그램을 실행 하는 장치의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="16127-145">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="16127-146">문자열</span><span class="sxs-lookup"><span data-stu-id="16127-146">string</span></span> | <span data-ttu-id="16127-147">기록 된 작업을 처리 한 서버 응용 프로그램을 실행 하는 장치의 IP 주소</span><span class="sxs-lookup"><span data-stu-id="16127-147">IP address of the device running the server application that processed the recorded action</span></span> |
| `TargetDeviceName` | <span data-ttu-id="16127-148">문자열</span><span class="sxs-lookup"><span data-stu-id="16127-148">string</span></span> | <span data-ttu-id="16127-149">기록 된 작업을 적용 한 장치의 FQDN (정규화 된 도메인 이름)입니다.</span><span class="sxs-lookup"><span data-stu-id="16127-149">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="16127-150">문자열</span><span class="sxs-lookup"><span data-stu-id="16127-150">string</span></span> | <span data-ttu-id="16127-151">기록 된 작업이 적용 된 계정의 UPN (사용자 계정 이름)</span><span class="sxs-lookup"><span data-stu-id="16127-151">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="16127-152">문자열</span><span class="sxs-lookup"><span data-stu-id="16127-152">string</span></span> | <span data-ttu-id="16127-153">기록 된 작업이 적용 된 계정의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="16127-153">Display name of the account that the recorded action was applied to</span></span> |
| `Location` | <span data-ttu-id="16127-154">문자열</span><span class="sxs-lookup"><span data-stu-id="16127-154">string</span></span> | <span data-ttu-id="16127-155">이벤트와 관련 된 구/군/시, 국가 또는 기타 지리적 위치</span><span class="sxs-lookup"><span data-stu-id="16127-155">City, country, or other geographic location associated with the event</span></span> |
| `ReportId` | <span data-ttu-id="16127-156">long</span><span class="sxs-lookup"><span data-stu-id="16127-156">long</span></span> | <span data-ttu-id="16127-157">이벤트에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="16127-157">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="16127-158">문자열</span><span class="sxs-lookup"><span data-stu-id="16127-158">string</span></span> | <span data-ttu-id="16127-159">엔터티 또는 이벤트에 대 한 추가 정보</span><span class="sxs-lookup"><span data-stu-id="16127-159">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="16127-160">관련 항목</span><span class="sxs-lookup"><span data-stu-id="16127-160">Related topics</span></span>
- [<span data-ttu-id="16127-161">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="16127-161">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="16127-162">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="16127-162">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="16127-163">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="16127-163">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="16127-164">여러 장치 및 전자 메일에서 위협을 탐지</span><span class="sxs-lookup"><span data-stu-id="16127-164">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="16127-165">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="16127-165">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="16127-166">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="16127-166">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
