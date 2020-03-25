---
title: 고급 구하기 스키마의 AccountInfo 테이블
description: 고급 구하기 스키마의 AccountInfo 테이블에 있는 사용자 계정 정보에 대해 자세히 알아보기
keywords: 고급 구하기, 위협 검색, 사이버 위협 사냥, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 스키마 참조, kusto, table, column, AlertInfo 장치, 컴퓨터, 사용자, 계정
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
ms.openlocfilehash: 9e4503ab297c7a584a548faa36ca6102c1b8dda6
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929531"
---
# <a name="accountinfo"></a><span data-ttu-id="30876-104">AccountInfo</span><span class="sxs-lookup"><span data-stu-id="30876-104">AccountInfo</span></span>

<span data-ttu-id="30876-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="30876-105">**Applies to:**</span></span>
- <span data-ttu-id="30876-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="30876-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="30876-107">`AccountInfo` [고급 구하기](advanced-hunting-overview.md) 스키마의 표에는 Azure Active Directory를 비롯 하 여 다양 한 서비스에서 가져온 사용자 계정에 대 한 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30876-107">The `AccountInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about user accounts obtained from various services, including Azure Active Directory.</span></span> <span data-ttu-id="30876-108">이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="30876-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="30876-109">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="30876-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="30876-110">열 이름</span><span class="sxs-lookup"><span data-stu-id="30876-110">Column name</span></span> | <span data-ttu-id="30876-111">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="30876-111">Data type</span></span> | <span data-ttu-id="30876-112">설명</span><span class="sxs-lookup"><span data-stu-id="30876-112">Description</span></span> |
|-------------|-----------|-------------|
| `AccountObjectId` | <span data-ttu-id="30876-113">문자열</span><span class="sxs-lookup"><span data-stu-id="30876-113">string</span></span> | <span data-ttu-id="30876-114">Azure AD의 계정에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="30876-114">Unique identifier for the account in Azure AD</span></span> |
| `AccountUpn` | <span data-ttu-id="30876-115">문자열</span><span class="sxs-lookup"><span data-stu-id="30876-115">string</span></span> | <span data-ttu-id="30876-116">계정의 UPN (사용자 계정 이름)</span><span class="sxs-lookup"><span data-stu-id="30876-116">User principal name (UPN) of the account</span></span> |
| `OnPremSid` | <span data-ttu-id="30876-117">문자열</span><span class="sxs-lookup"><span data-stu-id="30876-117">string</span></span> | <span data-ttu-id="30876-118">계정의 온-프레미스 SID (보안 식별자)</span><span class="sxs-lookup"><span data-stu-id="30876-118">On-premises security identifier (SID) of the account</span></span> |
| `CloudSid` | <span data-ttu-id="30876-119">문자열</span><span class="sxs-lookup"><span data-stu-id="30876-119">string</span></span> | <span data-ttu-id="30876-120">계정의 클라우드 보안 식별자</span><span class="sxs-lookup"><span data-stu-id="30876-120">Cloud security identifier of the account</span></span> |
| `GivenName` | <span data-ttu-id="30876-121">문자열</span><span class="sxs-lookup"><span data-stu-id="30876-121">string</span></span> | <span data-ttu-id="30876-122">계정 사용자의 이름이 나 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="30876-122">Given name or first name of the account user</span></span> |
| `Surname` | <span data-ttu-id="30876-123">문자열</span><span class="sxs-lookup"><span data-stu-id="30876-123">string</span></span> | <span data-ttu-id="30876-124">계정 사용자의 성, 패밀리 이름 또는 성</span><span class="sxs-lookup"><span data-stu-id="30876-124">Surname, family name, or last name of the account user</span></span> |
| `AccountDisplayName` | <span data-ttu-id="30876-125">문자열</span><span class="sxs-lookup"><span data-stu-id="30876-125">string</span></span> | <span data-ttu-id="30876-126">주소록에 표시 되는 계정 사용자의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="30876-126">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="30876-127">일반적으로 주어진 이름이 나 이름, 중간 시작, 성 또는 성의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="30876-127">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `Department` | <span data-ttu-id="30876-128">문자열</span><span class="sxs-lookup"><span data-stu-id="30876-128">string</span></span> | <span data-ttu-id="30876-129">계정 사용자가 속한 부서의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="30876-129">Name of the department that the account user belongs to</span></span> |
| `JobTitle` | <span data-ttu-id="30876-130">문자열</span><span class="sxs-lookup"><span data-stu-id="30876-130">string</span></span> | <span data-ttu-id="30876-131">계정 사용자의 직함</span><span class="sxs-lookup"><span data-stu-id="30876-131">Job title of the account user</span></span> |
| `AccountName` | <span data-ttu-id="30876-132">문자열</span><span class="sxs-lookup"><span data-stu-id="30876-132">string</span></span> | <span data-ttu-id="30876-133">계정의 사용자 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="30876-133">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="30876-134">문자열</span><span class="sxs-lookup"><span data-stu-id="30876-134">string</span></span> | <span data-ttu-id="30876-135">계정의 도메인</span><span class="sxs-lookup"><span data-stu-id="30876-135">Domain of the account</span></span> |
| `EmailAddress` | <span data-ttu-id="30876-136">문자열</span><span class="sxs-lookup"><span data-stu-id="30876-136">string</span></span> | <span data-ttu-id="30876-137">계정의 SMTP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="30876-137">SMTP address of the account</span></span> |
| `SipProxyAddress` | <span data-ttu-id="30876-138">문자열</span><span class="sxs-lookup"><span data-stu-id="30876-138">string</span></span> | <span data-ttu-id="30876-139">계정의 SIP (over IP) session (세션 시작 프로토콜) 주소</span><span class="sxs-lookup"><span data-stu-id="30876-139">Voice of over IP (VOIP) session initiation protocol (SIP) address of the account</span></span> |
| `City` | <span data-ttu-id="30876-140">문자열</span><span class="sxs-lookup"><span data-stu-id="30876-140">string</span></span> | <span data-ttu-id="30876-141">계정 사용자가 있는 구/군/시</span><span class="sxs-lookup"><span data-stu-id="30876-141">City where the account user is located</span></span> |
| `Country` | <span data-ttu-id="30876-142">문자열</span><span class="sxs-lookup"><span data-stu-id="30876-142">string</span></span> | <span data-ttu-id="30876-143">계정 사용자가 있는 국가/지역</span><span class="sxs-lookup"><span data-stu-id="30876-143">Country/Region where the account user is located</span></span> |
| `IsAccountEnabled` | <span data-ttu-id="30876-144">부울</span><span class="sxs-lookup"><span data-stu-id="30876-144">boolean</span></span> | <span data-ttu-id="30876-145">계정을 사용할 수 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="30876-145">Indicates whether the account is enabled or not</span></span> |

## <a name="related-topics"></a><span data-ttu-id="30876-146">관련 항목</span><span class="sxs-lookup"><span data-stu-id="30876-146">Related topics</span></span>
- [<span data-ttu-id="30876-147">사전 대응식 위협 탐지</span><span class="sxs-lookup"><span data-stu-id="30876-147">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="30876-148">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="30876-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="30876-149">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="30876-149">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="30876-150">여러 장치 및 전자 메일에서 위협을 탐지</span><span class="sxs-lookup"><span data-stu-id="30876-150">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="30876-151">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="30876-151">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="30876-152">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="30876-152">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
