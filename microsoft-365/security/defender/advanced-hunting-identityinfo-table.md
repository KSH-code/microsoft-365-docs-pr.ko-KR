---
title: 고급 헌팅 스위마의 IdentityInfo 테이블
description: 고급 헌팅 스위마의 IdentityInfo 표에서 사용자 계정 정보에 대해 자세히 알아보기
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 위협 방지, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, schema 참조, kusto, 표, 열, 데이터 형식, 설명, AccountInfo, IdentityInfo, 계정
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
ms.openlocfilehash: e3e5410c868336308b1ecb34ba4326bf2dc5796f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072775"
---
# <a name="identityinfo"></a><span data-ttu-id="78c6d-104">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="78c6d-104">IdentityInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="78c6d-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="78c6d-105">**Applies to:**</span></span>
- <span data-ttu-id="78c6d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="78c6d-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="78c6d-107">고급 `IdentityInfo` 헌팅 [계획의](advanced-hunting-overview.md) 표에는 Azure Active Directory를 비롯한 다양한 서비스에서 얻은 사용자 계정에 대한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78c6d-107">The `IdentityInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about user accounts obtained from various services, including Azure Active Directory.</span></span> <span data-ttu-id="78c6d-108">이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="78c6d-108">Use this reference to construct queries that return information from this table.</span></span>

>[!NOTE]
><span data-ttu-id="78c6d-109">이 테이블의 이름을 에서 `AccountInfo` 으로했습니다.</span><span class="sxs-lookup"><span data-stu-id="78c6d-109">This table was renamed from `AccountInfo`.</span></span> <span data-ttu-id="78c6d-110">이름을 변경하는 동안 포털에 저장된 모든 쿼리가 자동으로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="78c6d-110">During renames, all queries saved in the portal are automatically updated.</span></span> <span data-ttu-id="78c6d-111">다른 곳에 저장한 쿼리를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="78c6d-111">Check queries you have saved elsewhere.</span></span>

<span data-ttu-id="78c6d-112">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="78c6d-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="78c6d-113">열 이름</span><span class="sxs-lookup"><span data-stu-id="78c6d-113">Column name</span></span> | <span data-ttu-id="78c6d-114">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="78c6d-114">Data type</span></span> | <span data-ttu-id="78c6d-115">설명</span><span class="sxs-lookup"><span data-stu-id="78c6d-115">Description</span></span> |
|-------------|-----------|-------------|
| `AccountObjectId` | <span data-ttu-id="78c6d-116">문자열</span><span class="sxs-lookup"><span data-stu-id="78c6d-116">string</span></span> | <span data-ttu-id="78c6d-117">Azure AD에서 계정의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="78c6d-117">Unique identifier for the account in Azure AD</span></span> |
| `AccountUpn` | <span data-ttu-id="78c6d-118">문자열</span><span class="sxs-lookup"><span data-stu-id="78c6d-118">string</span></span> | <span data-ttu-id="78c6d-119">계정의 UPN(사용자 계정 이름)</span><span class="sxs-lookup"><span data-stu-id="78c6d-119">User principal name (UPN) of the account</span></span> |
| `OnPremSid` | <span data-ttu-id="78c6d-120">문자열</span><span class="sxs-lookup"><span data-stu-id="78c6d-120">string</span></span> | <span data-ttu-id="78c6d-121">계정의 SID(사내 보안 식별자)입니다.</span><span class="sxs-lookup"><span data-stu-id="78c6d-121">On-premises security identifier (SID) of the account</span></span> |
| `CloudSid` | <span data-ttu-id="78c6d-122">문자열</span><span class="sxs-lookup"><span data-stu-id="78c6d-122">string</span></span> | <span data-ttu-id="78c6d-123">계정의 클라우드 보안 식별자</span><span class="sxs-lookup"><span data-stu-id="78c6d-123">Cloud security identifier of the account</span></span> |
| `GivenName` | <span data-ttu-id="78c6d-124">문자열</span><span class="sxs-lookup"><span data-stu-id="78c6d-124">string</span></span> | <span data-ttu-id="78c6d-125">계정 사용자의 이름 또는 지정한 이름</span><span class="sxs-lookup"><span data-stu-id="78c6d-125">Given name or first name of the account user</span></span> |
| `Surname` | <span data-ttu-id="78c6d-126">문자열</span><span class="sxs-lookup"><span data-stu-id="78c6d-126">string</span></span> | <span data-ttu-id="78c6d-127">계정 사용자의 성, 가족 이름 또는 성</span><span class="sxs-lookup"><span data-stu-id="78c6d-127">Surname, family name, or last name of the account user</span></span> |
| `AccountDisplayName` | <span data-ttu-id="78c6d-128">문자열</span><span class="sxs-lookup"><span data-stu-id="78c6d-128">string</span></span> | <span data-ttu-id="78c6d-129">주소부에 표시된 계정 사용자의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="78c6d-129">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="78c6d-130">일반적으로 지정한 이름이나 이름, 중간 시작, 성 또는 성의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="78c6d-130">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `Department` | <span data-ttu-id="78c6d-131">문자열</span><span class="sxs-lookup"><span data-stu-id="78c6d-131">string</span></span> | <span data-ttu-id="78c6d-132">계정 사용자가 속한 부서의 이름</span><span class="sxs-lookup"><span data-stu-id="78c6d-132">Name of the department that the account user belongs to</span></span> |
| `JobTitle` | <span data-ttu-id="78c6d-133">문자열</span><span class="sxs-lookup"><span data-stu-id="78c6d-133">string</span></span> | <span data-ttu-id="78c6d-134">계정 사용자의 직위</span><span class="sxs-lookup"><span data-stu-id="78c6d-134">Job title of the account user</span></span> |
| `AccountName` | <span data-ttu-id="78c6d-135">문자열</span><span class="sxs-lookup"><span data-stu-id="78c6d-135">string</span></span> | <span data-ttu-id="78c6d-136">계정의 사용자 이름</span><span class="sxs-lookup"><span data-stu-id="78c6d-136">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="78c6d-137">문자열</span><span class="sxs-lookup"><span data-stu-id="78c6d-137">string</span></span> | <span data-ttu-id="78c6d-138">계정의 도메인</span><span class="sxs-lookup"><span data-stu-id="78c6d-138">Domain of the account</span></span> |
| `EmailAddress` | <span data-ttu-id="78c6d-139">문자열</span><span class="sxs-lookup"><span data-stu-id="78c6d-139">string</span></span> | <span data-ttu-id="78c6d-140">계정의 SMTP 주소</span><span class="sxs-lookup"><span data-stu-id="78c6d-140">SMTP address of the account</span></span> |
| `SipProxyAddress` | <span data-ttu-id="78c6d-141">문자열</span><span class="sxs-lookup"><span data-stu-id="78c6d-141">string</span></span> | <span data-ttu-id="78c6d-142">계정의 VOIP(Voice over IP) SIP(Session Initiation Protocol) 주소</span><span class="sxs-lookup"><span data-stu-id="78c6d-142">Voice over IP (VOIP) session initiation protocol (SIP) address of the account</span></span> |
| `City` | <span data-ttu-id="78c6d-143">문자열</span><span class="sxs-lookup"><span data-stu-id="78c6d-143">string</span></span> | <span data-ttu-id="78c6d-144">계정 사용자가 있는 구</span><span class="sxs-lookup"><span data-stu-id="78c6d-144">City where the account user is located</span></span> |
| `Country` | <span data-ttu-id="78c6d-145">문자열</span><span class="sxs-lookup"><span data-stu-id="78c6d-145">string</span></span> | <span data-ttu-id="78c6d-146">계정 사용자가 있는 국가/지역</span><span class="sxs-lookup"><span data-stu-id="78c6d-146">Country/Region where the account user is located</span></span> |
| `IsAccountEnabled` | <span data-ttu-id="78c6d-147">부울</span><span class="sxs-lookup"><span data-stu-id="78c6d-147">boolean</span></span> | <span data-ttu-id="78c6d-148">계정이 활성화되어 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="78c6d-148">Indicates whether the account is enabled or not</span></span> |

## <a name="related-topics"></a><span data-ttu-id="78c6d-149">관련 항목</span><span class="sxs-lookup"><span data-stu-id="78c6d-149">Related topics</span></span>
- [<span data-ttu-id="78c6d-150">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="78c6d-150">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="78c6d-151">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="78c6d-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="78c6d-152">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="78c6d-152">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="78c6d-153">장치, 전자 메일, 앱 및 ID를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="78c6d-153">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="78c6d-154">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="78c6d-154">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="78c6d-155">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="78c6d-155">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
