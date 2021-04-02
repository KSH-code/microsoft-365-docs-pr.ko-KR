---
title: 고급 헌팅chema의 AppFileEvents 테이블
description: 고급 헌팅 계획의 AppFileEvents 표에서 클라우드 앱 및 서비스와 관련된 파일 관련 이벤트에 대해 자세히 알아보시고
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 위협 방지, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, schema 참조, kusto, 표, 열, 데이터 형식, 설명, AppFileEvents, Cloud App Security, MCAS
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
ms.openlocfilehash: b8b3b34e1b8535772d19f8ddd9f52c5c0a89292b
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499344"
---
# <a name="appfileevents"></a><span data-ttu-id="65305-104">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="65305-104">AppFileEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="65305-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="65305-105">**Applies to:**</span></span>
- <span data-ttu-id="65305-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="65305-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="65305-107">고급 헌팅 계획의 표에는 Microsoft Cloud App Security에서 모니터링하는 클라우드 앱 및 서비스의 파일 관련 활동에 대한 `AppFileEvents` 정보가 포함되어 있습니다. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="65305-107">The `AppFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file-related activities in cloud apps and services monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="65305-108">이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="65305-108">Use this reference to construct queries that return information from this table.</span></span>

>[!WARNING]
><span data-ttu-id="65305-109">이 테이블은 곧 사용 중지될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="65305-109">This table will be retired soon.</span></span> <span data-ttu-id="65305-110">2021년 3월 7일 현재 테이블은 더 이상 `AppFileEvents` 기록되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="65305-110">As of March 7, 2021, the `AppFileEvents` table is no longer logging records.</span></span> <span data-ttu-id="65305-111">클라우드 서비스에서 파일 관련 활동을 찾은 사용자는 클라우드 서비스에서 해당 날짜 이상을 찾기 위해 [CloudAppEvents](advanced-hunting-cloudappevents-table.md) 테이블을 대신 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65305-111">Users hunting through file-related activities in cloud services on and beyond the said date should use the [CloudAppEvents](advanced-hunting-cloudappevents-table.md) table instead.</span></span> <br><br><span data-ttu-id="65305-112">테이블을 계속 사용하는 쿼리 및 사용자 지정 검색 규칙을 검색하고 테이블을 사용하여 `AppFileEvents` 편집해야 `CloudAppEvents` 합니다.</span><span class="sxs-lookup"><span data-stu-id="65305-112">Make sure to search for queries and custom detection rules that still use the `AppFileEvents` table and edit them to use the `CloudAppEvents` table.</span></span> <span data-ttu-id="65305-113">영향을 받는 쿼리를 변환하는 방법에 대한 자세한 지침은 [Microsoft 365 Defender](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857)고급 헌팅을 사용하여 클라우드 앱 활동에서 헌트에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65305-113">More guidance about converting affected queries can be found in [Hunt across cloud app activities with Microsoft 365 Defender advanced hunting](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857).</span></span>


<span data-ttu-id="65305-114">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="65305-114">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="65305-115">열 이름</span><span class="sxs-lookup"><span data-stu-id="65305-115">Column name</span></span> | <span data-ttu-id="65305-116">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="65305-116">Data type</span></span> | <span data-ttu-id="65305-117">설명</span><span class="sxs-lookup"><span data-stu-id="65305-117">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="65305-118">datetime</span><span class="sxs-lookup"><span data-stu-id="65305-118">datetime</span></span> | <span data-ttu-id="65305-119">이벤트가 기록된 날짜와 시간</span><span class="sxs-lookup"><span data-stu-id="65305-119">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="65305-120">문자열</span><span class="sxs-lookup"><span data-stu-id="65305-120">string</span></span> | <span data-ttu-id="65305-121">이벤트를 트리거한 활동의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="65305-121">Type of activity that triggered the event.</span></span> <span data-ttu-id="65305-122">자세한 내용은 포털 내 [Schema 참조를](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="65305-122">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="65305-123">문자열</span><span class="sxs-lookup"><span data-stu-id="65305-123">string</span></span> | <span data-ttu-id="65305-124">기록된 작업을 수행한 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="65305-124">Application that performed the recorded action</span></span> |
| `FileName` | <span data-ttu-id="65305-125">문자열</span><span class="sxs-lookup"><span data-stu-id="65305-125">string</span></span> | <span data-ttu-id="65305-126">기록된 조치가 적용된 파일의 이름</span><span class="sxs-lookup"><span data-stu-id="65305-126">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="65305-127">문자열</span><span class="sxs-lookup"><span data-stu-id="65305-127">string</span></span> | <span data-ttu-id="65305-128">기록된 작업이 적용된 파일이 들어 있는 폴더</span><span class="sxs-lookup"><span data-stu-id="65305-128">Folder containing the file that the recorded action was applied to</span></span> |
| `PreviousFileName` | <span data-ttu-id="65305-129">문자열</span><span class="sxs-lookup"><span data-stu-id="65305-129">string</span></span> | <span data-ttu-id="65305-130">작업의 결과로 이름이 변경된 파일의 원래 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="65305-130">Original name of the file that was renamed as a result of the action</span></span> |
| `PreviousFolderPath` | <span data-ttu-id="65305-131">문자열</span><span class="sxs-lookup"><span data-stu-id="65305-131">string</span></span> | <span data-ttu-id="65305-132">기록된 작업이 적용되기 전 파일이 들어 있는 원본 폴더</span><span class="sxs-lookup"><span data-stu-id="65305-132">Original folder containing the file before the recorded action was applied</span></span> |
| `Protocol` | <span data-ttu-id="65305-133">문자열</span><span class="sxs-lookup"><span data-stu-id="65305-133">string</span></span> | <span data-ttu-id="65305-134">사용된 네트워크 프로토콜</span><span class="sxs-lookup"><span data-stu-id="65305-134">Network protocol used</span></span> |
| `AccountName` | <span data-ttu-id="65305-135">문자열</span><span class="sxs-lookup"><span data-stu-id="65305-135">string</span></span> | <span data-ttu-id="65305-136">계정의 사용자 이름</span><span class="sxs-lookup"><span data-stu-id="65305-136">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="65305-137">문자열</span><span class="sxs-lookup"><span data-stu-id="65305-137">string</span></span> | <span data-ttu-id="65305-138">계정의 도메인</span><span class="sxs-lookup"><span data-stu-id="65305-138">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="65305-139">문자열</span><span class="sxs-lookup"><span data-stu-id="65305-139">string</span></span> | <span data-ttu-id="65305-140">계정의 SID(보안 식별자)입니다.</span><span class="sxs-lookup"><span data-stu-id="65305-140">Security Identifier (SID) of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="65305-141">문자열</span><span class="sxs-lookup"><span data-stu-id="65305-141">string</span></span> | <span data-ttu-id="65305-142">계정의 UPN(사용자 계정 이름)</span><span class="sxs-lookup"><span data-stu-id="65305-142">User principal name (UPN) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="65305-143">문자열</span><span class="sxs-lookup"><span data-stu-id="65305-143">string</span></span> | <span data-ttu-id="65305-144">Azure AD에서 계정의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="65305-144">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="65305-145">문자열</span><span class="sxs-lookup"><span data-stu-id="65305-145">string</span></span> | <span data-ttu-id="65305-146">주소부에 표시된 계정 사용자의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="65305-146">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="65305-147">일반적으로 지정한 이름이나 이름, 중간 시작, 성 또는 성의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="65305-147">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="65305-148">문자열</span><span class="sxs-lookup"><span data-stu-id="65305-148">string</span></span> | <span data-ttu-id="65305-149">장치의 FQDN(FQDN)</span><span class="sxs-lookup"><span data-stu-id="65305-149">Fully qualified domain name (FQDN) of the device</span></span> |
| `DeviceType` | <span data-ttu-id="65305-150">문자열</span><span class="sxs-lookup"><span data-stu-id="65305-150">string</span></span> | <span data-ttu-id="65305-151">디바이스 유형</span><span class="sxs-lookup"><span data-stu-id="65305-151">Type of device</span></span> | 
| `OSPlatform` | <span data-ttu-id="65305-152">문자열</span><span class="sxs-lookup"><span data-stu-id="65305-152">string</span></span> | <span data-ttu-id="65305-153">디바이스에서 실행되는 운영 체제의 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="65305-153">Platform of the operating system running on the device.</span></span> <span data-ttu-id="65305-154">이는 Windows 10 및 Windows 7과 같이 동일한 제품군 내의 변형을 포함하여 특정 운영 체제를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="65305-154">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="65305-155">문자열</span><span class="sxs-lookup"><span data-stu-id="65305-155">string</span></span> | <span data-ttu-id="65305-156">끝점에 할당되어 관련 네트워크 통신 중에 사용되는 IP 주소</span><span class="sxs-lookup"><span data-stu-id="65305-156">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Port` | <span data-ttu-id="65305-157">문자열</span><span class="sxs-lookup"><span data-stu-id="65305-157">string</span></span> | <span data-ttu-id="65305-158">통신 중에 사용되는 TCP 포트</span><span class="sxs-lookup"><span data-stu-id="65305-158">TCP port used during communication</span></span>  |
| `DestinationDeviceName` | <span data-ttu-id="65305-159">문자열</span><span class="sxs-lookup"><span data-stu-id="65305-159">string</span></span> | <span data-ttu-id="65305-160">기록된 작업을 처리한 서버 응용 프로그램을 실행하는 장치의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="65305-160">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="65305-161">문자열</span><span class="sxs-lookup"><span data-stu-id="65305-161">string</span></span> | <span data-ttu-id="65305-162">기록된 작업을 처리한 서버 응용 프로그램을 실행하는 장치의 IP 주소</span><span class="sxs-lookup"><span data-stu-id="65305-162">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="65305-163">문자열</span><span class="sxs-lookup"><span data-stu-id="65305-163">string</span></span> | <span data-ttu-id="65305-164">관련 네트워크 통신의 대상 포트</span><span class="sxs-lookup"><span data-stu-id="65305-164">Destination port of related network communications</span></span> |
| `Location` | <span data-ttu-id="65305-165">문자열</span><span class="sxs-lookup"><span data-stu-id="65305-165">string</span></span> | <span data-ttu-id="65305-166">이벤트와 관련된 도시, 국가 또는 기타 지리적 위치</span><span class="sxs-lookup"><span data-stu-id="65305-166">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="65305-167">문자열</span><span class="sxs-lookup"><span data-stu-id="65305-167">string</span></span> | <span data-ttu-id="65305-168">끝점 IP 주소와 연결된 ISP(인터넷 서비스 공급자)</span><span class="sxs-lookup"><span data-stu-id="65305-168">Internet service provider (ISP) associated with the endpoint IP address</span></span> |
| `ReportId` | <span data-ttu-id="65305-169">long</span><span class="sxs-lookup"><span data-stu-id="65305-169">long</span></span> | <span data-ttu-id="65305-170">이벤트의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="65305-170">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="65305-171">문자열</span><span class="sxs-lookup"><span data-stu-id="65305-171">string</span></span> | <span data-ttu-id="65305-172">엔터티 또는 이벤트에 대한 추가 정보</span><span class="sxs-lookup"><span data-stu-id="65305-172">Additional information about the entity or event</span></span> |

>[!TIP]
> <span data-ttu-id="65305-173">테이블에서 지원하는 이벤트 유형(값)에 대한 자세한 내용은 보안 센터에서 사용할 수 있는 기본 제공 `ActionType` Schema 참조를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="65305-173">For detailed information about the events types (`ActionType` values) supported by a table, use the built-in schema reference available in the security center.</span></span>


## <a name="related-topics"></a><span data-ttu-id="65305-174">관련 항목</span><span class="sxs-lookup"><span data-stu-id="65305-174">Related topics</span></span>
- [<span data-ttu-id="65305-175">지능형 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="65305-175">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="65305-176">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="65305-176">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="65305-177">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="65305-177">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="65305-178">장치, 전자 메일, 앱 및 ID를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="65305-178">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="65305-179">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="65305-179">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="65305-180">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="65305-180">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
