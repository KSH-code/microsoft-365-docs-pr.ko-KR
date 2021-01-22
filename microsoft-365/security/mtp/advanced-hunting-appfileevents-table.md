---
title: 고급 헌팅chema의 AppFileEvents 테이블
description: 고급 헌팅 계획의 AppFileEvents 표에서 클라우드 앱 및 서비스와 관련된 파일 관련 이벤트에 대해 자세히 알아보기
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 위협 방지, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, schema reference, kusto, table, column, data type, description, AppFileEvents, Cloud App Security, MCAS
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
ms.openlocfilehash: 59e9affc53398f2a1b06fbab9774e4b53e146425
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932877"
---
# <a name="appfileevents"></a><span data-ttu-id="d6a39-104">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="d6a39-104">AppFileEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d6a39-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="d6a39-105">**Applies to:**</span></span>
- <span data-ttu-id="d6a39-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d6a39-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="d6a39-107">고급 헌팅 계획의 표에는 Microsoft Cloud App Security에서 모니터링하는 클라우드 앱 및 서비스의 파일 관련 활동에 대한 `AppFileEvents` 정보가 포함되어 있습니다. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="d6a39-107">The `AppFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file-related activities in cloud apps and services monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="d6a39-108">이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d6a39-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="d6a39-109">테이블에서 지원하는 이벤트 유형(값)에 대한 자세한 내용은 보안 센터에서 사용할 수 있는 기본 제공 `ActionType` [schema 참조를](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d6a39-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="d6a39-110">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d6a39-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="d6a39-111">열 이름</span><span class="sxs-lookup"><span data-stu-id="d6a39-111">Column name</span></span> | <span data-ttu-id="d6a39-112">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d6a39-112">Data type</span></span> | <span data-ttu-id="d6a39-113">설명</span><span class="sxs-lookup"><span data-stu-id="d6a39-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="d6a39-114">datetime</span><span class="sxs-lookup"><span data-stu-id="d6a39-114">datetime</span></span> | <span data-ttu-id="d6a39-115">이벤트가 기록된 날짜와 시간</span><span class="sxs-lookup"><span data-stu-id="d6a39-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="d6a39-116">문자열</span><span class="sxs-lookup"><span data-stu-id="d6a39-116">string</span></span> | <span data-ttu-id="d6a39-117">이벤트를 트리거한 활동의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="d6a39-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="d6a39-118">자세한 내용은 포털 [내 Schema 참조를](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="d6a39-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="d6a39-119">문자열</span><span class="sxs-lookup"><span data-stu-id="d6a39-119">string</span></span> | <span data-ttu-id="d6a39-120">기록된 작업을 수행한 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="d6a39-120">Application that performed the recorded action</span></span> |
| `FileName` | <span data-ttu-id="d6a39-121">문자열</span><span class="sxs-lookup"><span data-stu-id="d6a39-121">string</span></span> | <span data-ttu-id="d6a39-122">기록된 조치가 적용된 파일의 이름</span><span class="sxs-lookup"><span data-stu-id="d6a39-122">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="d6a39-123">문자열</span><span class="sxs-lookup"><span data-stu-id="d6a39-123">string</span></span> | <span data-ttu-id="d6a39-124">기록된 작업이 적용된 파일이 들어 있는 폴더</span><span class="sxs-lookup"><span data-stu-id="d6a39-124">Folder containing the file that the recorded action was applied to</span></span> |
| `PreviousFileName` | <span data-ttu-id="d6a39-125">문자열</span><span class="sxs-lookup"><span data-stu-id="d6a39-125">string</span></span> | <span data-ttu-id="d6a39-126">작업의 결과로 이름이 변경된 파일의 원래 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d6a39-126">Original name of the file that was renamed as a result of the action</span></span> |
| `PreviousFolderPath` | <span data-ttu-id="d6a39-127">문자열</span><span class="sxs-lookup"><span data-stu-id="d6a39-127">string</span></span> | <span data-ttu-id="d6a39-128">기록된 작업이 적용되기 전 파일이 들어 있는 원본 폴더</span><span class="sxs-lookup"><span data-stu-id="d6a39-128">Original folder containing the file before the recorded action was applied</span></span> |
| `Protocol` | <span data-ttu-id="d6a39-129">문자열</span><span class="sxs-lookup"><span data-stu-id="d6a39-129">string</span></span> | <span data-ttu-id="d6a39-130">사용되는 네트워크 프로토콜</span><span class="sxs-lookup"><span data-stu-id="d6a39-130">Network protocol used</span></span> |
| `AccountName` | <span data-ttu-id="d6a39-131">문자열</span><span class="sxs-lookup"><span data-stu-id="d6a39-131">string</span></span> | <span data-ttu-id="d6a39-132">계정의 사용자 이름</span><span class="sxs-lookup"><span data-stu-id="d6a39-132">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="d6a39-133">문자열</span><span class="sxs-lookup"><span data-stu-id="d6a39-133">string</span></span> | <span data-ttu-id="d6a39-134">계정의 도메인</span><span class="sxs-lookup"><span data-stu-id="d6a39-134">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="d6a39-135">문자열</span><span class="sxs-lookup"><span data-stu-id="d6a39-135">string</span></span> | <span data-ttu-id="d6a39-136">계정의 UPN(사용자 계정 이름)</span><span class="sxs-lookup"><span data-stu-id="d6a39-136">User principal name (UPN) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="d6a39-137">문자열</span><span class="sxs-lookup"><span data-stu-id="d6a39-137">string</span></span> | <span data-ttu-id="d6a39-138">Azure AD에서 계정의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="d6a39-138">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="d6a39-139">문자열</span><span class="sxs-lookup"><span data-stu-id="d6a39-139">string</span></span> | <span data-ttu-id="d6a39-140">주소부에 표시된 계정 사용자의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d6a39-140">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="d6a39-141">일반적으로 지정한 이름이나 이름, 중간 초기화 및 성 또는 성의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="d6a39-141">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="d6a39-142">문자열</span><span class="sxs-lookup"><span data-stu-id="d6a39-142">string</span></span> | <span data-ttu-id="d6a39-143">장치의 FQDN(FQDN)</span><span class="sxs-lookup"><span data-stu-id="d6a39-143">Fully qualified domain name (FQDN) of the device</span></span> |
| `DeviceType` | <span data-ttu-id="d6a39-144">문자열</span><span class="sxs-lookup"><span data-stu-id="d6a39-144">string</span></span> | <span data-ttu-id="d6a39-145">디바이스 유형</span><span class="sxs-lookup"><span data-stu-id="d6a39-145">Type of device</span></span> | 
| `OSPlatform` | <span data-ttu-id="d6a39-146">문자열</span><span class="sxs-lookup"><span data-stu-id="d6a39-146">string</span></span> | <span data-ttu-id="d6a39-147">디바이스에서 실행되는 운영 체제의 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="d6a39-147">Platform of the operating system running on the device.</span></span> <span data-ttu-id="d6a39-148">이는 Windows 10 및 Windows 7과 같이 동일한 제품군 내의 변형을 포함하여 특정 운영 체제를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d6a39-148">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="d6a39-149">문자열</span><span class="sxs-lookup"><span data-stu-id="d6a39-149">string</span></span> | <span data-ttu-id="d6a39-150">끝점에 할당되어 관련 네트워크 통신 중에 사용되는 IP 주소</span><span class="sxs-lookup"><span data-stu-id="d6a39-150">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="d6a39-151">문자열</span><span class="sxs-lookup"><span data-stu-id="d6a39-151">string</span></span> | <span data-ttu-id="d6a39-152">기록된 작업을 처리한 서버 응용 프로그램을 실행하는 장치의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d6a39-152">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="d6a39-153">문자열</span><span class="sxs-lookup"><span data-stu-id="d6a39-153">string</span></span> | <span data-ttu-id="d6a39-154">기록된 작업을 처리한 서버 응용 프로그램을 실행하는 장치의 IP 주소</span><span class="sxs-lookup"><span data-stu-id="d6a39-154">IP address of the device running the server application that processed the recorded action</span></span> |
| `Location` | <span data-ttu-id="d6a39-155">문자열</span><span class="sxs-lookup"><span data-stu-id="d6a39-155">string</span></span> | <span data-ttu-id="d6a39-156">이벤트와 관련된 도시, 국가 또는 기타 지리적 위치</span><span class="sxs-lookup"><span data-stu-id="d6a39-156">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="d6a39-157">문자열</span><span class="sxs-lookup"><span data-stu-id="d6a39-157">string</span></span> | <span data-ttu-id="d6a39-158">끝점 IP 주소와 연결된 ISP(인터넷 서비스 공급자)</span><span class="sxs-lookup"><span data-stu-id="d6a39-158">Internet service provider (ISP) associated with the endpoint IP address</span></span> |
| `ReportId` | <span data-ttu-id="d6a39-159">long</span><span class="sxs-lookup"><span data-stu-id="d6a39-159">long</span></span> | <span data-ttu-id="d6a39-160">이벤트의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="d6a39-160">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="d6a39-161">문자열</span><span class="sxs-lookup"><span data-stu-id="d6a39-161">string</span></span> | <span data-ttu-id="d6a39-162">엔터티 또는 이벤트에 대한 추가 정보</span><span class="sxs-lookup"><span data-stu-id="d6a39-162">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="d6a39-163">관련 항목</span><span class="sxs-lookup"><span data-stu-id="d6a39-163">Related topics</span></span>
- [<span data-ttu-id="d6a39-164">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="d6a39-164">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d6a39-165">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="d6a39-165">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d6a39-166">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="d6a39-166">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="d6a39-167">장치, 전자 메일, 앱 및 ID를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="d6a39-167">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="d6a39-168">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="d6a39-168">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="d6a39-169">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="d6a39-169">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
