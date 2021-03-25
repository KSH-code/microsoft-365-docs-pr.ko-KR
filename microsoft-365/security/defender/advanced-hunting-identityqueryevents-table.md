---
title: 고급 헌팅 스케마의 IdentityQueryEvents 테이블
description: 고급 헌팅 스케마의 IdentityQueryEvents 테이블에서 Active Directory 쿼리 이벤트에 대해 자세히 알아보십시오.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 위협 방지, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, schema reference, kusto, table, column, data type, description, IdentityQueryEvents, Azure AD, Active Directory, Azure ATP, ID, LDAP 쿼리
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
ms.technology: m365d
ms.openlocfilehash: f663a9dcc5bebd3a7fd124bbd0c0fece5dbb62e4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076356"
---
# <a name="identityqueryevents"></a><span data-ttu-id="80594-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="80594-104">IdentityQueryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="80594-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="80594-105">**Applies to:**</span></span>
- <span data-ttu-id="80594-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="80594-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="80594-107">고급 `IdentityQueryEvents` 헌팅 schema의 표에는 사용자, 그룹, 장치 및 도메인과 같은 Active Directory 개체에 대해 수행되는 쿼리에 대한 정보가 포함되어 있습니다. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="80594-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="80594-108">이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="80594-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="80594-109">테이블에서 지원하는 이벤트 유형(값)에 대한 자세한 내용은 보안 센터에서 사용할 수 있는 기본 제공 `ActionType` Schema 참조를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="80594-109">For detailed information about the events types (`ActionType` values) supported by a table, use the built-in schema reference available in the security center.</span></span>

<span data-ttu-id="80594-110">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="80594-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="80594-111">열 이름</span><span class="sxs-lookup"><span data-stu-id="80594-111">Column name</span></span> | <span data-ttu-id="80594-112">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="80594-112">Data type</span></span> | <span data-ttu-id="80594-113">설명</span><span class="sxs-lookup"><span data-stu-id="80594-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="80594-114">datetime</span><span class="sxs-lookup"><span data-stu-id="80594-114">datetime</span></span> | <span data-ttu-id="80594-115">이벤트가 기록된 날짜와 시간</span><span class="sxs-lookup"><span data-stu-id="80594-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="80594-116">문자열</span><span class="sxs-lookup"><span data-stu-id="80594-116">string</span></span> | <span data-ttu-id="80594-117">이벤트를 트리거한 활동의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="80594-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="80594-118">자세한 내용은 포털 내 [Schema 참조를](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="80594-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="80594-119">문자열</span><span class="sxs-lookup"><span data-stu-id="80594-119">string</span></span> | <span data-ttu-id="80594-120">기록된 작업을 수행한 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="80594-120">Application that performed the recorded action</span></span> |
| `QueryType` | <span data-ttu-id="80594-121">문자열</span><span class="sxs-lookup"><span data-stu-id="80594-121">string</span></span> | <span data-ttu-id="80594-122">QueryGroup, QueryUser 또는 EnumerateUsers와 같은 쿼리 유형</span><span class="sxs-lookup"><span data-stu-id="80594-122">Type of query, such as QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryTarget` | <span data-ttu-id="80594-123">문자열</span><span class="sxs-lookup"><span data-stu-id="80594-123">string</span></span> | <span data-ttu-id="80594-124">사용자, 그룹, 장치, 도메인 또는 다른 엔터티 유형이 검색되는 이름</span><span class="sxs-lookup"><span data-stu-id="80594-124">Name of user, group, device, domain, or any other entity type being queried</span></span> |
| `Query` | <span data-ttu-id="80594-125">문자열</span><span class="sxs-lookup"><span data-stu-id="80594-125">string</span></span> | <span data-ttu-id="80594-126">쿼리를 실행하는 데 사용되는 문자열</span><span class="sxs-lookup"><span data-stu-id="80594-126">String used to run the query</span></span> |
| `Protocol` | <span data-ttu-id="80594-127">문자열</span><span class="sxs-lookup"><span data-stu-id="80594-127">string</span></span> | <span data-ttu-id="80594-128">통신 중에 사용되는 프로토콜</span><span class="sxs-lookup"><span data-stu-id="80594-128">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="80594-129">문자열</span><span class="sxs-lookup"><span data-stu-id="80594-129">string</span></span> | <span data-ttu-id="80594-130">계정의 사용자 이름</span><span class="sxs-lookup"><span data-stu-id="80594-130">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="80594-131">문자열</span><span class="sxs-lookup"><span data-stu-id="80594-131">string</span></span> | <span data-ttu-id="80594-132">계정의 도메인</span><span class="sxs-lookup"><span data-stu-id="80594-132">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="80594-133">문자열</span><span class="sxs-lookup"><span data-stu-id="80594-133">string</span></span> | <span data-ttu-id="80594-134">계정의 UPN(사용자 계정 이름)</span><span class="sxs-lookup"><span data-stu-id="80594-134">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="80594-135">문자열</span><span class="sxs-lookup"><span data-stu-id="80594-135">string</span></span> | <span data-ttu-id="80594-136">계정의 SID(보안 식별자)입니다.</span><span class="sxs-lookup"><span data-stu-id="80594-136">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="80594-137">문자열</span><span class="sxs-lookup"><span data-stu-id="80594-137">string</span></span> | <span data-ttu-id="80594-138">Azure AD에서 계정의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="80594-138">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="80594-139">문자열</span><span class="sxs-lookup"><span data-stu-id="80594-139">string</span></span> | <span data-ttu-id="80594-140">주소부에 표시된 계정 사용자의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="80594-140">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="80594-141">일반적으로 지정한 이름이나 이름, 중간 시작, 성 또는 성의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="80594-141">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="80594-142">문자열</span><span class="sxs-lookup"><span data-stu-id="80594-142">string</span></span> | <span data-ttu-id="80594-143">끝점의 FQDN(FQDN)</span><span class="sxs-lookup"><span data-stu-id="80594-143">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="80594-144">문자열</span><span class="sxs-lookup"><span data-stu-id="80594-144">string</span></span> | <span data-ttu-id="80594-145">끝점에 할당되어 관련 네트워크 통신 중에 사용되는 IP 주소</span><span class="sxs-lookup"><span data-stu-id="80594-145">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Port` | <span data-ttu-id="80594-146">문자열</span><span class="sxs-lookup"><span data-stu-id="80594-146">string</span></span> | <span data-ttu-id="80594-147">통신 중에 사용되는 TCP 포트</span><span class="sxs-lookup"><span data-stu-id="80594-147">TCP port used during communication</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="80594-148">문자열</span><span class="sxs-lookup"><span data-stu-id="80594-148">string</span></span> | <span data-ttu-id="80594-149">기록된 작업을 처리한 서버 응용 프로그램을 실행하는 장치의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="80594-149">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="80594-150">문자열</span><span class="sxs-lookup"><span data-stu-id="80594-150">string</span></span> | <span data-ttu-id="80594-151">기록된 작업을 처리한 서버 응용 프로그램을 실행하는 장치의 IP 주소</span><span class="sxs-lookup"><span data-stu-id="80594-151">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="80594-152">문자열</span><span class="sxs-lookup"><span data-stu-id="80594-152">string</span></span> | <span data-ttu-id="80594-153">관련 네트워크 통신의 대상 포트</span><span class="sxs-lookup"><span data-stu-id="80594-153">Destination port of related network communications</span></span> |
| `TargetDeviceName` | <span data-ttu-id="80594-154">문자열</span><span class="sxs-lookup"><span data-stu-id="80594-154">string</span></span> | <span data-ttu-id="80594-155">기록된 작업이 적용된 장치의 FQDN(FQDN)</span><span class="sxs-lookup"><span data-stu-id="80594-155">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="80594-156">문자열</span><span class="sxs-lookup"><span data-stu-id="80594-156">string</span></span> | <span data-ttu-id="80594-157">기록된 작업이 적용된 계정의 UPN(사용자 계정 이름)</span><span class="sxs-lookup"><span data-stu-id="80594-157">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="80594-158">문자열</span><span class="sxs-lookup"><span data-stu-id="80594-158">string</span></span> | <span data-ttu-id="80594-159">기록된 작업이 적용된 계정의 표시 이름</span><span class="sxs-lookup"><span data-stu-id="80594-159">Display name of the account that the recorded action was applied to</span></span> |
| `Location` | <span data-ttu-id="80594-160">문자열</span><span class="sxs-lookup"><span data-stu-id="80594-160">string</span></span> | <span data-ttu-id="80594-161">이벤트와 관련된 도시, 국가 또는 기타 지리적 위치</span><span class="sxs-lookup"><span data-stu-id="80594-161">City, country, or other geographic location associated with the event</span></span> |
| `ReportId` | <span data-ttu-id="80594-162">long</span><span class="sxs-lookup"><span data-stu-id="80594-162">long</span></span> | <span data-ttu-id="80594-163">이벤트의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="80594-163">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="80594-164">문자열</span><span class="sxs-lookup"><span data-stu-id="80594-164">string</span></span> | <span data-ttu-id="80594-165">엔터티 또는 이벤트에 대한 추가 정보</span><span class="sxs-lookup"><span data-stu-id="80594-165">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="80594-166">관련 항목</span><span class="sxs-lookup"><span data-stu-id="80594-166">Related topics</span></span>
- [<span data-ttu-id="80594-167">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="80594-167">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="80594-168">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="80594-168">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="80594-169">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="80594-169">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="80594-170">장치, 전자 메일, 앱 및 ID를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="80594-170">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="80594-171">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="80594-171">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="80594-172">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="80594-172">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
