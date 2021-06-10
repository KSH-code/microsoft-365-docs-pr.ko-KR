---
title: 고급 헌팅Chema의 IdentityDirectoryEvents 테이블
description: 고급 헌팅 구조의 IdentityDirectoryEvents 테이블에서 도메인 컨트롤러 및 Active Directory 이벤트에 대해 자세히 알아보십시오.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 365 Defender, microsoft 365, m365, 검색, 쿼리, 원격 분석, schema reference, kusto, table, column, data type, description, IdentityDirectoryEvents, domain controller, Active Directory, Microsoft Defender for Identity, ID
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: b42ff09f1e363f115ecc06c361c8386b328b0bcb
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933004"
---
# <a name="identitydirectoryevents"></a><span data-ttu-id="666ca-104">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="666ca-104">IdentityDirectoryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="666ca-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="666ca-105">**Applies to:**</span></span>
- <span data-ttu-id="666ca-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="666ca-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="666ca-107">고급 헌팅 계획의 표에는 AD(Active Directory)를 실행하는 사내 도메인 컨트롤러와 관련된 `IdentityDirectoryEvents` 이벤트가 포함되어 [](advanced-hunting-overview.md) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="666ca-107">The `IdentityDirectoryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="666ca-108">이 표에서는 암호 변경, 암호 만료 및 UPN(사용자 계정 이름) 변경과 같은 다양한 ID 관련 이벤트를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="666ca-108">This table captures various identity-related events, like password changes, password expiration, and user principal name (UPN) changes.</span></span> <span data-ttu-id="666ca-109">또한 작업 일정 및 PowerShell 활동과 같은 도메인 컨트롤러의 시스템 이벤트를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="666ca-109">It also captures system events on the domain controller, like scheduling of tasks and PowerShell activity.</span></span> <span data-ttu-id="666ca-110">이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="666ca-110">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="666ca-111">테이블에서 지원하는 이벤트 유형(값)에 대한 자세한 내용은 보안 센터에서 사용할 수 있는 기본 제공 `ActionType` Schema 참조를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="666ca-111">For detailed information about the events types (`ActionType` values) supported by a table, use the built-in schema reference available in the security center.</span></span>

<span data-ttu-id="666ca-112">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="666ca-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="666ca-113">열 이름</span><span class="sxs-lookup"><span data-stu-id="666ca-113">Column name</span></span> | <span data-ttu-id="666ca-114">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="666ca-114">Data type</span></span> | <span data-ttu-id="666ca-115">설명</span><span class="sxs-lookup"><span data-stu-id="666ca-115">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="666ca-116">datetime</span><span class="sxs-lookup"><span data-stu-id="666ca-116">datetime</span></span> | <span data-ttu-id="666ca-117">이벤트가 기록된 날짜와 시간</span><span class="sxs-lookup"><span data-stu-id="666ca-117">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="666ca-118">문자열</span><span class="sxs-lookup"><span data-stu-id="666ca-118">string</span></span> | <span data-ttu-id="666ca-119">이벤트를 트리거한 활동의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="666ca-119">Type of activity that triggered the event.</span></span> <span data-ttu-id="666ca-120">자세한 내용은 포털 내 [Schema 참조를](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="666ca-120">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="666ca-121">문자열</span><span class="sxs-lookup"><span data-stu-id="666ca-121">string</span></span> | <span data-ttu-id="666ca-122">기록된 작업을 수행한 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="666ca-122">Application that performed the recorded action</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="666ca-123">문자열</span><span class="sxs-lookup"><span data-stu-id="666ca-123">string</span></span> | <span data-ttu-id="666ca-124">기록된 작업이 적용된 계정의 UPN(사용자 계정 이름)</span><span class="sxs-lookup"><span data-stu-id="666ca-124">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="666ca-125">문자열</span><span class="sxs-lookup"><span data-stu-id="666ca-125">string</span></span> | <span data-ttu-id="666ca-126">기록된 작업이 적용된 계정의 표시 이름</span><span class="sxs-lookup"><span data-stu-id="666ca-126">Display name of the account that the recorded action was applied to</span></span> |
| `TargetDeviceName` | <span data-ttu-id="666ca-127">문자열</span><span class="sxs-lookup"><span data-stu-id="666ca-127">string</span></span> | <span data-ttu-id="666ca-128">기록된 작업이 적용된 장치의 FQDN(FQDN)</span><span class="sxs-lookup"><span data-stu-id="666ca-128">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="666ca-129">문자열</span><span class="sxs-lookup"><span data-stu-id="666ca-129">string</span></span> | <span data-ttu-id="666ca-130">기록된 작업을 처리한 서버 응용 프로그램을 실행하는 장치의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="666ca-130">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="666ca-131">문자열</span><span class="sxs-lookup"><span data-stu-id="666ca-131">string</span></span> | <span data-ttu-id="666ca-132">기록된 작업을 처리한 서버 응용 프로그램을 실행하는 장치의 IP 주소</span><span class="sxs-lookup"><span data-stu-id="666ca-132">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="666ca-133">문자열</span><span class="sxs-lookup"><span data-stu-id="666ca-133">string</span></span> | <span data-ttu-id="666ca-134">활동의 대상 포트</span><span class="sxs-lookup"><span data-stu-id="666ca-134">Destination port of the activity</span></span> |
| `Protocol` | <span data-ttu-id="666ca-135">문자열</span><span class="sxs-lookup"><span data-stu-id="666ca-135">string</span></span> | <span data-ttu-id="666ca-136">통신 중에 사용되는 프로토콜</span><span class="sxs-lookup"><span data-stu-id="666ca-136">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="666ca-137">문자열</span><span class="sxs-lookup"><span data-stu-id="666ca-137">string</span></span> | <span data-ttu-id="666ca-138">계정의 사용자 이름</span><span class="sxs-lookup"><span data-stu-id="666ca-138">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="666ca-139">문자열</span><span class="sxs-lookup"><span data-stu-id="666ca-139">string</span></span> | <span data-ttu-id="666ca-140">계정의 도메인</span><span class="sxs-lookup"><span data-stu-id="666ca-140">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="666ca-141">문자열</span><span class="sxs-lookup"><span data-stu-id="666ca-141">string</span></span> | <span data-ttu-id="666ca-142">계정의 UPN(사용자 계정 이름)</span><span class="sxs-lookup"><span data-stu-id="666ca-142">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="666ca-143">문자열</span><span class="sxs-lookup"><span data-stu-id="666ca-143">string</span></span> | <span data-ttu-id="666ca-144">계정의 SID(보안 식별자)입니다.</span><span class="sxs-lookup"><span data-stu-id="666ca-144">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="666ca-145">문자열</span><span class="sxs-lookup"><span data-stu-id="666ca-145">string</span></span> | <span data-ttu-id="666ca-146">계정의 고유 식별자입니다Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="666ca-146">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="666ca-147">문자열</span><span class="sxs-lookup"><span data-stu-id="666ca-147">string</span></span> | <span data-ttu-id="666ca-148">주소부에 표시된 계정 사용자의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="666ca-148">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="666ca-149">일반적으로 지정한 이름이나 이름, 중간 시작, 성 또는 성의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="666ca-149">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="666ca-150">문자열</span><span class="sxs-lookup"><span data-stu-id="666ca-150">string</span></span> | <span data-ttu-id="666ca-151">장치의 FQDN(FQDN)</span><span class="sxs-lookup"><span data-stu-id="666ca-151">Fully qualified domain name (FQDN) of the device</span></span> |
| `IPAddress` | <span data-ttu-id="666ca-152">문자열</span><span class="sxs-lookup"><span data-stu-id="666ca-152">string</span></span> | <span data-ttu-id="666ca-153">통신 중 장치에 할당된 IP 주소</span><span class="sxs-lookup"><span data-stu-id="666ca-153">IP address assigned to the device during communication</span></span> |
| `Port` | <span data-ttu-id="666ca-154">문자열</span><span class="sxs-lookup"><span data-stu-id="666ca-154">string</span></span> | <span data-ttu-id="666ca-155">통신 중에 사용되는 TCP 포트</span><span class="sxs-lookup"><span data-stu-id="666ca-155">TCP port used during communication</span></span> |
| `Location` | <span data-ttu-id="666ca-156">문자열</span><span class="sxs-lookup"><span data-stu-id="666ca-156">string</span></span> | <span data-ttu-id="666ca-157">이벤트와 관련된 도시, 국가 또는 기타 지리적 위치</span><span class="sxs-lookup"><span data-stu-id="666ca-157">City, country, or other geographic location associated with the event</span></span> |
| `ISP` | <span data-ttu-id="666ca-158">문자열</span><span class="sxs-lookup"><span data-stu-id="666ca-158">string</span></span> | <span data-ttu-id="666ca-159">IP 주소와 연결된 인터넷 서비스 공급자</span><span class="sxs-lookup"><span data-stu-id="666ca-159">Internet service provider associated with the IP address</span></span> |
| `ReportId` | <span data-ttu-id="666ca-160">long</span><span class="sxs-lookup"><span data-stu-id="666ca-160">long</span></span> | <span data-ttu-id="666ca-161">이벤트의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="666ca-161">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="666ca-162">문자열</span><span class="sxs-lookup"><span data-stu-id="666ca-162">string</span></span> | <span data-ttu-id="666ca-163">엔터티 또는 이벤트에 대한 추가 정보</span><span class="sxs-lookup"><span data-stu-id="666ca-163">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="666ca-164">관련 항목</span><span class="sxs-lookup"><span data-stu-id="666ca-164">Related topics</span></span>
- [<span data-ttu-id="666ca-165">지능형 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="666ca-165">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="666ca-166">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="666ca-166">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="666ca-167">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="666ca-167">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="666ca-168">장치, 전자 메일, 앱 및 ID를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="666ca-168">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="666ca-169">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="666ca-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="666ca-170">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="666ca-170">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
