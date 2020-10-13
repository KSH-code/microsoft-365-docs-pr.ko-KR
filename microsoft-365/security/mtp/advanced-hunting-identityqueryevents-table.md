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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: bf1c57ee93c6f0e007c1b58e73fb9371799e75c6
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48431126"
---
# <a name="identityqueryevents"></a><span data-ttu-id="e7828-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="e7828-104">IdentityQueryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e7828-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="e7828-105">**Applies to:**</span></span>
- <span data-ttu-id="e7828-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="e7828-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="e7828-107">`IdentityQueryEvents` [고급 구하기](advanced-hunting-overview.md) 스키마의 표에는 Active Directory 개체 (예: 사용자, 그룹, 장치 및 도메인)에 대해 수행 된 쿼리에 대 한 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7828-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="e7828-108">이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e7828-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="e7828-109">테이블에서 지 원하는 이벤트 유형 (값)에 대 한 자세한 내용은 `ActionType` 보안 센터에서 사용할 수 있는 [기본 제공 스키마 참조](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 를 사용 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e7828-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="e7828-110">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e7828-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="e7828-111">열 이름</span><span class="sxs-lookup"><span data-stu-id="e7828-111">Column name</span></span> | <span data-ttu-id="e7828-112">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="e7828-112">Data type</span></span> | <span data-ttu-id="e7828-113">설명</span><span class="sxs-lookup"><span data-stu-id="e7828-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="e7828-114">datetime</span><span class="sxs-lookup"><span data-stu-id="e7828-114">datetime</span></span> | <span data-ttu-id="e7828-115">이벤트가 기록된 날짜와 시간</span><span class="sxs-lookup"><span data-stu-id="e7828-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="e7828-116">문자열</span><span class="sxs-lookup"><span data-stu-id="e7828-116">string</span></span> | <span data-ttu-id="e7828-117">이벤트를 트리거한 작업의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="e7828-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="e7828-118">자세한 내용은 [portal 스키마 참조](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e7828-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="e7828-119">문자열</span><span class="sxs-lookup"><span data-stu-id="e7828-119">string</span></span> | <span data-ttu-id="e7828-120">기록 된 작업을 수행한 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="e7828-120">Application that performed the recorded action</span></span> |
| `QueryType` | <span data-ttu-id="e7828-121">문자열</span><span class="sxs-lookup"><span data-stu-id="e7828-121">string</span></span> | <span data-ttu-id="e7828-122">쿼리 유형 (예: QueryGroup, Querygroup 또는 EnumerateUsers)</span><span class="sxs-lookup"><span data-stu-id="e7828-122">Type of query, such as QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryTarget` | <span data-ttu-id="e7828-123">문자열</span><span class="sxs-lookup"><span data-stu-id="e7828-123">string</span></span> | <span data-ttu-id="e7828-124">쿼리 중인 사용자, 그룹, 장치, 도메인 또는 기타 모든 엔터티 유형의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e7828-124">Name of user, group, device, domain, or any other entity type being queried</span></span> |
| `Query` | <span data-ttu-id="e7828-125">문자열</span><span class="sxs-lookup"><span data-stu-id="e7828-125">string</span></span> | <span data-ttu-id="e7828-126">쿼리를 실행 하는 데 사용 되는 문자열</span><span class="sxs-lookup"><span data-stu-id="e7828-126">String used to run the query</span></span> |
| `Protocol` | <span data-ttu-id="e7828-127">문자열</span><span class="sxs-lookup"><span data-stu-id="e7828-127">string</span></span> | <span data-ttu-id="e7828-128">통신 중에 사용 되는 프로토콜</span><span class="sxs-lookup"><span data-stu-id="e7828-128">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="e7828-129">문자열</span><span class="sxs-lookup"><span data-stu-id="e7828-129">string</span></span> | <span data-ttu-id="e7828-130">계정의 사용자 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e7828-130">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="e7828-131">문자열</span><span class="sxs-lookup"><span data-stu-id="e7828-131">string</span></span> | <span data-ttu-id="e7828-132">계정의 도메인</span><span class="sxs-lookup"><span data-stu-id="e7828-132">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="e7828-133">문자열</span><span class="sxs-lookup"><span data-stu-id="e7828-133">string</span></span> | <span data-ttu-id="e7828-134">계정의 UPN (사용자 계정 이름)</span><span class="sxs-lookup"><span data-stu-id="e7828-134">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="e7828-135">문자열</span><span class="sxs-lookup"><span data-stu-id="e7828-135">string</span></span> | <span data-ttu-id="e7828-136">계정의 SID (보안 식별자)</span><span class="sxs-lookup"><span data-stu-id="e7828-136">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="e7828-137">문자열</span><span class="sxs-lookup"><span data-stu-id="e7828-137">string</span></span> | <span data-ttu-id="e7828-138">Azure AD의 계정에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="e7828-138">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="e7828-139">문자열</span><span class="sxs-lookup"><span data-stu-id="e7828-139">string</span></span> | <span data-ttu-id="e7828-140">주소록에 표시 되는 계정 사용자의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e7828-140">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="e7828-141">일반적으로 주어진 이름이 나 이름, 중간 시작, 성 또는 성의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="e7828-141">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="e7828-142">문자열</span><span class="sxs-lookup"><span data-stu-id="e7828-142">string</span></span> | <span data-ttu-id="e7828-143">끝점의 FQDN (정규화 된 도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="e7828-143">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="e7828-144">문자열</span><span class="sxs-lookup"><span data-stu-id="e7828-144">string</span></span> | <span data-ttu-id="e7828-145">끝점에 할당 되 고 관련 네트워크 통신 중에 사용 되는 IP 주소</span><span class="sxs-lookup"><span data-stu-id="e7828-145">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="e7828-146">문자열</span><span class="sxs-lookup"><span data-stu-id="e7828-146">string</span></span> | <span data-ttu-id="e7828-147">기록 된 작업을 처리 한 서버 응용 프로그램을 실행 하는 장치의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e7828-147">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="e7828-148">문자열</span><span class="sxs-lookup"><span data-stu-id="e7828-148">string</span></span> | <span data-ttu-id="e7828-149">기록 된 작업을 처리 한 서버 응용 프로그램을 실행 하는 장치의 IP 주소</span><span class="sxs-lookup"><span data-stu-id="e7828-149">IP address of the device running the server application that processed the recorded action</span></span> |
| `TargetDeviceName` | <span data-ttu-id="e7828-150">문자열</span><span class="sxs-lookup"><span data-stu-id="e7828-150">string</span></span> | <span data-ttu-id="e7828-151">기록 된 작업을 적용 한 장치의 FQDN (정규화 된 도메인 이름)입니다.</span><span class="sxs-lookup"><span data-stu-id="e7828-151">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="e7828-152">문자열</span><span class="sxs-lookup"><span data-stu-id="e7828-152">string</span></span> | <span data-ttu-id="e7828-153">기록 된 작업이 적용 된 계정의 UPN (사용자 계정 이름)</span><span class="sxs-lookup"><span data-stu-id="e7828-153">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="e7828-154">문자열</span><span class="sxs-lookup"><span data-stu-id="e7828-154">string</span></span> | <span data-ttu-id="e7828-155">기록 된 작업이 적용 된 계정의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e7828-155">Display name of the account that the recorded action was applied to</span></span> |
| `Location` | <span data-ttu-id="e7828-156">문자열</span><span class="sxs-lookup"><span data-stu-id="e7828-156">string</span></span> | <span data-ttu-id="e7828-157">이벤트와 관련 된 구/군/시, 국가 또는 기타 지리적 위치</span><span class="sxs-lookup"><span data-stu-id="e7828-157">City, country, or other geographic location associated with the event</span></span> |
| `ReportId` | <span data-ttu-id="e7828-158">long</span><span class="sxs-lookup"><span data-stu-id="e7828-158">long</span></span> | <span data-ttu-id="e7828-159">이벤트에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="e7828-159">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="e7828-160">문자열</span><span class="sxs-lookup"><span data-stu-id="e7828-160">string</span></span> | <span data-ttu-id="e7828-161">엔터티 또는 이벤트에 대 한 추가 정보</span><span class="sxs-lookup"><span data-stu-id="e7828-161">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="e7828-162">관련 항목</span><span class="sxs-lookup"><span data-stu-id="e7828-162">Related topics</span></span>
- [<span data-ttu-id="e7828-163">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="e7828-163">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e7828-164">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="e7828-164">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e7828-165">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="e7828-165">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="e7828-166">기기, 전자 메일, 앱 및 ID를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="e7828-166">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="e7828-167">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="e7828-167">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="e7828-168">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="e7828-168">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
