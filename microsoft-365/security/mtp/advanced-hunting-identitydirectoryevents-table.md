---
title: 고급 구하기 스키마의 IdentityDirectoryEvents 테이블
description: 고급 구하기 스키마의 IdentityDirectoryEvents 테이블에 있는 도메인 컨트롤러 및 Active Directory 이벤트에 대해 자세히 알아봅니다.
keywords: 고급 구하기, 위협 검색, 사이버 위협 사냥, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 스키마 참조, kusto, table, column, IdentityDirectoryEvents, 도메인 컨트롤러, Active Directory, Azure ATP, id
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
ms.openlocfilehash: 1a65a8e78dfa09bc0a417669a1efd35320e261da
ms.sourcegitcommit: 445b249a6f0420b32e49742fd7744006c7090b2b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/18/2020
ms.locfileid: "46798790"
---
# <a name="identitydirectoryevents"></a><span data-ttu-id="9a130-104">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="9a130-104">IdentityDirectoryEvents</span></span>

<span data-ttu-id="9a130-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="9a130-105">**Applies to:**</span></span>
- <span data-ttu-id="9a130-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="9a130-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="9a130-107">`IdentityDirectoryEvents` [고급 구하기](advanced-hunting-overview.md) 스키마의 표에는 AD (Active Directory)를 실행 하는 온-프레미스 도메인 컨트롤러 관련 이벤트가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a130-107">The `IdentityDirectoryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="9a130-108">이 테이블은 암호 변경, 암호 만료, UPN (사용자 계정 이름) 변경 등의 다양 한 id 관련 이벤트를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="9a130-108">This table captures various identity-related events, like password changes, password expiration, and user principal name (UPN) changes.</span></span> <span data-ttu-id="9a130-109">또한 작업 예약 및 PowerShell 작업 같은 도메인 컨트롤러에 시스템 이벤트를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="9a130-109">It also captures system events on the domain controller, like scheduling of tasks and PowerShell activity.</span></span> <span data-ttu-id="9a130-110">이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9a130-110">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="9a130-111">테이블에서 지 원하는 이벤트 유형 (값)에 대 한 자세한 내용은 `ActionType` 보안 센터에서 사용할 수 있는 [기본 제공 스키마 참조](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 를 사용 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9a130-111">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="9a130-112">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9a130-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="9a130-113">열 이름</span><span class="sxs-lookup"><span data-stu-id="9a130-113">Column name</span></span> | <span data-ttu-id="9a130-114">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9a130-114">Data type</span></span> | <span data-ttu-id="9a130-115">설명</span><span class="sxs-lookup"><span data-stu-id="9a130-115">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="9a130-116">datetime</span><span class="sxs-lookup"><span data-stu-id="9a130-116">datetime</span></span> | <span data-ttu-id="9a130-117">이벤트가 기록된 날짜와 시간</span><span class="sxs-lookup"><span data-stu-id="9a130-117">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="9a130-118">문자열</span><span class="sxs-lookup"><span data-stu-id="9a130-118">string</span></span> | <span data-ttu-id="9a130-119">이벤트를 트리거한 작업의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="9a130-119">Type of activity that triggered the event.</span></span> <span data-ttu-id="9a130-120">자세한 내용은 [portal 스키마 참조](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9a130-120">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="9a130-121">문자열</span><span class="sxs-lookup"><span data-stu-id="9a130-121">string</span></span> | <span data-ttu-id="9a130-122">기록 된 작업을 수행한 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="9a130-122">Application that performed the recorded action</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="9a130-123">문자열</span><span class="sxs-lookup"><span data-stu-id="9a130-123">string</span></span> | <span data-ttu-id="9a130-124">기록 된 작업이 적용 된 계정의 UPN (사용자 계정 이름)</span><span class="sxs-lookup"><span data-stu-id="9a130-124">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="9a130-125">문자열</span><span class="sxs-lookup"><span data-stu-id="9a130-125">string</span></span> | <span data-ttu-id="9a130-126">기록 된 작업이 적용 된 계정의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9a130-126">Display name of the account that the recorded action was applied to</span></span> |
| `TargetDeviceName` | <span data-ttu-id="9a130-127">문자열</span><span class="sxs-lookup"><span data-stu-id="9a130-127">string</span></span> | <span data-ttu-id="9a130-128">기록 된 작업을 적용 한 장치의 FQDN (정규화 된 도메인 이름)입니다.</span><span class="sxs-lookup"><span data-stu-id="9a130-128">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="9a130-129">문자열</span><span class="sxs-lookup"><span data-stu-id="9a130-129">string</span></span> | <span data-ttu-id="9a130-130">기록 된 작업을 처리 한 서버 응용 프로그램을 실행 하는 장치의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9a130-130">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="9a130-131">문자열</span><span class="sxs-lookup"><span data-stu-id="9a130-131">string</span></span> | <span data-ttu-id="9a130-132">기록 된 작업을 처리 한 서버 응용 프로그램을 실행 하는 장치의 IP 주소</span><span class="sxs-lookup"><span data-stu-id="9a130-132">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="9a130-133">문자열</span><span class="sxs-lookup"><span data-stu-id="9a130-133">string</span></span> | <span data-ttu-id="9a130-134">활동의 대상 포트</span><span class="sxs-lookup"><span data-stu-id="9a130-134">Destination port of the activity</span></span> |
| `Protocol` | <span data-ttu-id="9a130-135">문자열</span><span class="sxs-lookup"><span data-stu-id="9a130-135">string</span></span> | <span data-ttu-id="9a130-136">통신 중에 사용 되는 프로토콜</span><span class="sxs-lookup"><span data-stu-id="9a130-136">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="9a130-137">문자열</span><span class="sxs-lookup"><span data-stu-id="9a130-137">string</span></span> | <span data-ttu-id="9a130-138">계정의 사용자 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9a130-138">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="9a130-139">문자열</span><span class="sxs-lookup"><span data-stu-id="9a130-139">string</span></span> | <span data-ttu-id="9a130-140">계정의 도메인</span><span class="sxs-lookup"><span data-stu-id="9a130-140">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="9a130-141">문자열</span><span class="sxs-lookup"><span data-stu-id="9a130-141">string</span></span> | <span data-ttu-id="9a130-142">계정의 UPN (사용자 계정 이름)</span><span class="sxs-lookup"><span data-stu-id="9a130-142">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="9a130-143">문자열</span><span class="sxs-lookup"><span data-stu-id="9a130-143">string</span></span> | <span data-ttu-id="9a130-144">계정의 SID (보안 식별자)</span><span class="sxs-lookup"><span data-stu-id="9a130-144">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="9a130-145">문자열</span><span class="sxs-lookup"><span data-stu-id="9a130-145">string</span></span> | <span data-ttu-id="9a130-146">Azure AD의 계정에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="9a130-146">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="9a130-147">문자열</span><span class="sxs-lookup"><span data-stu-id="9a130-147">string</span></span> | <span data-ttu-id="9a130-148">주소록에 표시 되는 계정 사용자의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9a130-148">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="9a130-149">일반적으로 주어진 이름이 나 이름, 중간 시작, 성 또는 성의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="9a130-149">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="9a130-150">문자열</span><span class="sxs-lookup"><span data-stu-id="9a130-150">string</span></span> | <span data-ttu-id="9a130-151">장치의 FQDN (정규화 된 도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="9a130-151">Fully qualified domain name (FQDN) of the device</span></span> |
| `IPAddress` | <span data-ttu-id="9a130-152">문자열</span><span class="sxs-lookup"><span data-stu-id="9a130-152">string</span></span> | <span data-ttu-id="9a130-153">통신 중에 장치에 할당 되는 IP 주소</span><span class="sxs-lookup"><span data-stu-id="9a130-153">IP address assigned to the device during communication</span></span> |
| `Port` | <span data-ttu-id="9a130-154">문자열</span><span class="sxs-lookup"><span data-stu-id="9a130-154">string</span></span> | <span data-ttu-id="9a130-155">통신 중에 사용 되는 TCP 포트</span><span class="sxs-lookup"><span data-stu-id="9a130-155">TCP port used during communication</span></span> |
| `Location` | <span data-ttu-id="9a130-156">문자열</span><span class="sxs-lookup"><span data-stu-id="9a130-156">string</span></span> | <span data-ttu-id="9a130-157">이벤트와 관련 된 구/군/시, 국가 또는 기타 지리적 위치</span><span class="sxs-lookup"><span data-stu-id="9a130-157">City, country, or other geographic location associated with the event</span></span> |
| `ISP` | <span data-ttu-id="9a130-158">문자열</span><span class="sxs-lookup"><span data-stu-id="9a130-158">string</span></span> | <span data-ttu-id="9a130-159">IP 주소와 연결 된 인터넷 서비스 공급자</span><span class="sxs-lookup"><span data-stu-id="9a130-159">Internet service provider associated with the IP address</span></span> |
| `ReportId` | <span data-ttu-id="9a130-160">long</span><span class="sxs-lookup"><span data-stu-id="9a130-160">long</span></span> | <span data-ttu-id="9a130-161">이벤트에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="9a130-161">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="9a130-162">문자열</span><span class="sxs-lookup"><span data-stu-id="9a130-162">string</span></span> | <span data-ttu-id="9a130-163">엔터티 또는 이벤트에 대 한 추가 정보</span><span class="sxs-lookup"><span data-stu-id="9a130-163">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="9a130-164">관련 항목</span><span class="sxs-lookup"><span data-stu-id="9a130-164">Related topics</span></span>
- [<span data-ttu-id="9a130-165">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="9a130-165">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="9a130-166">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="9a130-166">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="9a130-167">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="9a130-167">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="9a130-168">기기, 전자 메일, 앱 및 ID를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="9a130-168">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="9a130-169">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="9a130-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="9a130-170">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="9a130-170">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
