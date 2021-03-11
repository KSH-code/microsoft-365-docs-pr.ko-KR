---
title: 고급 헌팅Chema의 IdentityDirectoryEvents 테이블
description: 고급 헌팅 구조의 IdentityDirectoryEvents 테이블에서 도메인 컨트롤러 및 Active Directory 이벤트에 대해 자세히 알아보십시오.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 위협 방지, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 스마마 참조, kusto, 표, 열, 데이터 형식, 설명, IdentityDirectoryEvents, 도메인 컨트롤러, Active Directory, Azure ATP, ID
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
ms.openlocfilehash: d4e119bc0a2e600d5203231eb196cf201469bfd2
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712369"
---
# <a name="identitydirectoryevents"></a><span data-ttu-id="7b0c3-104">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="7b0c3-104">IdentityDirectoryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7b0c3-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="7b0c3-105">**Applies to:**</span></span>
- <span data-ttu-id="7b0c3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7b0c3-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="7b0c3-107">고급 헌팅 계획의 표에는 AD(Active Directory)를 실행하는 사내 도메인 컨트롤러와 관련된 `IdentityDirectoryEvents` 이벤트가 포함되어 [](advanced-hunting-overview.md) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b0c3-107">The `IdentityDirectoryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="7b0c3-108">이 표에서는 암호 변경, 암호 만료 및 UPN(사용자 계정 이름) 변경과 같은 다양한 ID 관련 이벤트를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="7b0c3-108">This table captures various identity-related events, like password changes, password expiration, and user principal name (UPN) changes.</span></span> <span data-ttu-id="7b0c3-109">또한 작업 일정 및 PowerShell 활동과 같은 도메인 컨트롤러의 시스템 이벤트를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="7b0c3-109">It also captures system events on the domain controller, like scheduling of tasks and PowerShell activity.</span></span> <span data-ttu-id="7b0c3-110">이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7b0c3-110">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="7b0c3-111">테이블에서 지원하는 이벤트 유형(값)에 대한 자세한 내용은 보안 센터에서 사용할 수 있는 기본 제공 `ActionType` Schema 참조를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7b0c3-111">For detailed information about the events types (`ActionType` values) supported by a table, use the built-in schema reference available in the security center.</span></span>

<span data-ttu-id="7b0c3-112">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7b0c3-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="7b0c3-113">열 이름</span><span class="sxs-lookup"><span data-stu-id="7b0c3-113">Column name</span></span> | <span data-ttu-id="7b0c3-114">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="7b0c3-114">Data type</span></span> | <span data-ttu-id="7b0c3-115">설명</span><span class="sxs-lookup"><span data-stu-id="7b0c3-115">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="7b0c3-116">datetime</span><span class="sxs-lookup"><span data-stu-id="7b0c3-116">datetime</span></span> | <span data-ttu-id="7b0c3-117">이벤트가 기록된 날짜와 시간</span><span class="sxs-lookup"><span data-stu-id="7b0c3-117">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="7b0c3-118">문자열</span><span class="sxs-lookup"><span data-stu-id="7b0c3-118">string</span></span> | <span data-ttu-id="7b0c3-119">이벤트를 트리거한 활동의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="7b0c3-119">Type of activity that triggered the event.</span></span> <span data-ttu-id="7b0c3-120">자세한 내용은 포털 내 [Schema 참조를](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="7b0c3-120">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="7b0c3-121">문자열</span><span class="sxs-lookup"><span data-stu-id="7b0c3-121">string</span></span> | <span data-ttu-id="7b0c3-122">기록된 작업을 수행한 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="7b0c3-122">Application that performed the recorded action</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="7b0c3-123">문자열</span><span class="sxs-lookup"><span data-stu-id="7b0c3-123">string</span></span> | <span data-ttu-id="7b0c3-124">기록된 작업이 적용된 계정의 UPN(사용자 계정 이름)</span><span class="sxs-lookup"><span data-stu-id="7b0c3-124">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="7b0c3-125">문자열</span><span class="sxs-lookup"><span data-stu-id="7b0c3-125">string</span></span> | <span data-ttu-id="7b0c3-126">기록된 작업이 적용된 계정의 표시 이름</span><span class="sxs-lookup"><span data-stu-id="7b0c3-126">Display name of the account that the recorded action was applied to</span></span> |
| `TargetDeviceName` | <span data-ttu-id="7b0c3-127">문자열</span><span class="sxs-lookup"><span data-stu-id="7b0c3-127">string</span></span> | <span data-ttu-id="7b0c3-128">기록된 작업이 적용된 장치의 FQDN(FQDN)</span><span class="sxs-lookup"><span data-stu-id="7b0c3-128">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="7b0c3-129">문자열</span><span class="sxs-lookup"><span data-stu-id="7b0c3-129">string</span></span> | <span data-ttu-id="7b0c3-130">기록된 작업을 처리한 서버 응용 프로그램을 실행하는 장치의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7b0c3-130">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="7b0c3-131">문자열</span><span class="sxs-lookup"><span data-stu-id="7b0c3-131">string</span></span> | <span data-ttu-id="7b0c3-132">기록된 작업을 처리한 서버 응용 프로그램을 실행하는 장치의 IP 주소</span><span class="sxs-lookup"><span data-stu-id="7b0c3-132">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="7b0c3-133">문자열</span><span class="sxs-lookup"><span data-stu-id="7b0c3-133">string</span></span> | <span data-ttu-id="7b0c3-134">활동의 대상 포트</span><span class="sxs-lookup"><span data-stu-id="7b0c3-134">Destination port of the activity</span></span> |
| `Protocol` | <span data-ttu-id="7b0c3-135">문자열</span><span class="sxs-lookup"><span data-stu-id="7b0c3-135">string</span></span> | <span data-ttu-id="7b0c3-136">통신 중에 사용되는 프로토콜</span><span class="sxs-lookup"><span data-stu-id="7b0c3-136">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="7b0c3-137">문자열</span><span class="sxs-lookup"><span data-stu-id="7b0c3-137">string</span></span> | <span data-ttu-id="7b0c3-138">계정의 사용자 이름</span><span class="sxs-lookup"><span data-stu-id="7b0c3-138">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="7b0c3-139">문자열</span><span class="sxs-lookup"><span data-stu-id="7b0c3-139">string</span></span> | <span data-ttu-id="7b0c3-140">계정의 도메인</span><span class="sxs-lookup"><span data-stu-id="7b0c3-140">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="7b0c3-141">문자열</span><span class="sxs-lookup"><span data-stu-id="7b0c3-141">string</span></span> | <span data-ttu-id="7b0c3-142">계정의 UPN(사용자 계정 이름)</span><span class="sxs-lookup"><span data-stu-id="7b0c3-142">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="7b0c3-143">문자열</span><span class="sxs-lookup"><span data-stu-id="7b0c3-143">string</span></span> | <span data-ttu-id="7b0c3-144">계정의 SID(보안 식별자)입니다.</span><span class="sxs-lookup"><span data-stu-id="7b0c3-144">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="7b0c3-145">문자열</span><span class="sxs-lookup"><span data-stu-id="7b0c3-145">string</span></span> | <span data-ttu-id="7b0c3-146">Azure Active Directory에서 계정의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="7b0c3-146">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="7b0c3-147">문자열</span><span class="sxs-lookup"><span data-stu-id="7b0c3-147">string</span></span> | <span data-ttu-id="7b0c3-148">주소부에 표시된 계정 사용자의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7b0c3-148">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="7b0c3-149">일반적으로 지정한 이름이나 이름, 중간 시작, 성 또는 성의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="7b0c3-149">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="7b0c3-150">문자열</span><span class="sxs-lookup"><span data-stu-id="7b0c3-150">string</span></span> | <span data-ttu-id="7b0c3-151">장치의 FQDN(FQDN)</span><span class="sxs-lookup"><span data-stu-id="7b0c3-151">Fully qualified domain name (FQDN) of the device</span></span> |
| `IPAddress` | <span data-ttu-id="7b0c3-152">문자열</span><span class="sxs-lookup"><span data-stu-id="7b0c3-152">string</span></span> | <span data-ttu-id="7b0c3-153">통신 중 장치에 할당된 IP 주소</span><span class="sxs-lookup"><span data-stu-id="7b0c3-153">IP address assigned to the device during communication</span></span> |
| `Port` | <span data-ttu-id="7b0c3-154">문자열</span><span class="sxs-lookup"><span data-stu-id="7b0c3-154">string</span></span> | <span data-ttu-id="7b0c3-155">통신 중에 사용되는 TCP 포트</span><span class="sxs-lookup"><span data-stu-id="7b0c3-155">TCP port used during communication</span></span> |
| `Location` | <span data-ttu-id="7b0c3-156">문자열</span><span class="sxs-lookup"><span data-stu-id="7b0c3-156">string</span></span> | <span data-ttu-id="7b0c3-157">이벤트와 관련된 도시, 국가 또는 기타 지리적 위치</span><span class="sxs-lookup"><span data-stu-id="7b0c3-157">City, country, or other geographic location associated with the event</span></span> |
| `ISP` | <span data-ttu-id="7b0c3-158">문자열</span><span class="sxs-lookup"><span data-stu-id="7b0c3-158">string</span></span> | <span data-ttu-id="7b0c3-159">IP 주소와 연결된 인터넷 서비스 공급자</span><span class="sxs-lookup"><span data-stu-id="7b0c3-159">Internet service provider associated with the IP address</span></span> |
| `ReportId` | <span data-ttu-id="7b0c3-160">long</span><span class="sxs-lookup"><span data-stu-id="7b0c3-160">long</span></span> | <span data-ttu-id="7b0c3-161">이벤트의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="7b0c3-161">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="7b0c3-162">문자열</span><span class="sxs-lookup"><span data-stu-id="7b0c3-162">string</span></span> | <span data-ttu-id="7b0c3-163">엔터티 또는 이벤트에 대한 추가 정보</span><span class="sxs-lookup"><span data-stu-id="7b0c3-163">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="7b0c3-164">관련 항목</span><span class="sxs-lookup"><span data-stu-id="7b0c3-164">Related topics</span></span>
- [<span data-ttu-id="7b0c3-165">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="7b0c3-165">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="7b0c3-166">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="7b0c3-166">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="7b0c3-167">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="7b0c3-167">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="7b0c3-168">장치, 전자 메일, 앱 및 ID를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="7b0c3-168">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="7b0c3-169">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="7b0c3-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="7b0c3-170">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="7b0c3-170">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
