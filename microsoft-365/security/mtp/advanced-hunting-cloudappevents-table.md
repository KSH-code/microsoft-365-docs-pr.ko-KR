---
title: 고급 구하기 스키마의 CloudAppEvents 테이블
description: 고급 구하기 스키마의 CloudAppEvents 테이블에 있는 클라우드 앱 및 서비스의 이벤트에 대해 자세히 알아보기
keywords: 고급 구하기, 위협 검색, 사이버 위협 검색, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 스키마 참조, kusto, table, column, data type, description, CloudAppEvents, Cloud App Security, MCAS
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
ms.openlocfilehash: 3cb4498e5db6a7752e99b8c677bc8936d2c975ef
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087773"
---
# <a name="cloudappevents"></a><span data-ttu-id="b5edd-104">CloudAppEvents</span><span class="sxs-lookup"><span data-stu-id="b5edd-104">CloudAppEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b5edd-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="b5edd-105">**Applies to:**</span></span>
- <span data-ttu-id="b5edd-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b5edd-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="b5edd-107">현재 미리 보기에서 사용할 수 있는 `CloudAppEvents` [고급 구하기](advanced-hunting-overview.md) 스키마의 표에는 특히 Microsoft 팀 및 Exchange Online과 같은 다양 한 클라우드 앱 및 서비스의 활동에 대 한 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5edd-107">Currently available in preview, the `CloudAppEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about activities in various cloud apps and services, specifically Microsoft Teams and Exchange Online.</span></span> <span data-ttu-id="b5edd-108">이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b5edd-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="b5edd-109">이 테이블은 Microsoft Cloud App Security에서 모니터링 하는 활동을 더 포함 하기 위해 확장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5edd-109">This table will expand to include more activities monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="b5edd-110">최종적으로이 테이블에는 [Appfileevents](advanced-hunting-appfileevents-table.md) 테이블에 현재 저장 된 파일 활동이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5edd-110">Eventually, this table will include file activity currently stored in the [AppFileEvents](advanced-hunting-appfileevents-table.md) table.</span></span> <span data-ttu-id="b5edd-111">Microsoft는이 표로의 데이터 이동에 대 한 추가 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5edd-111">Microsoft will provide additional guidance as more data moves to this table.</span></span>

<span data-ttu-id="b5edd-112">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b5edd-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="b5edd-113">열 이름</span><span class="sxs-lookup"><span data-stu-id="b5edd-113">Column name</span></span> | <span data-ttu-id="b5edd-114">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b5edd-114">Data type</span></span> | <span data-ttu-id="b5edd-115">설명</span><span class="sxs-lookup"><span data-stu-id="b5edd-115">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="b5edd-116">datetime</span><span class="sxs-lookup"><span data-stu-id="b5edd-116">datetime</span></span> | <span data-ttu-id="b5edd-117">이벤트가 기록된 날짜와 시간</span><span class="sxs-lookup"><span data-stu-id="b5edd-117">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="b5edd-118">문자열</span><span class="sxs-lookup"><span data-stu-id="b5edd-118">string</span></span> | <span data-ttu-id="b5edd-119">이벤트를 트리거한 작업의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="b5edd-119">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="b5edd-120">문자열</span><span class="sxs-lookup"><span data-stu-id="b5edd-120">string</span></span> | <span data-ttu-id="b5edd-121">기록 된 작업을 수행한 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="b5edd-121">Application that performed the recorded action</span></span> |
| `ApplicationId` | <span data-ttu-id="b5edd-122">문자열</span><span class="sxs-lookup"><span data-stu-id="b5edd-122">string</span></span> | <span data-ttu-id="b5edd-123">응용 프로그램의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="b5edd-123">Unique identifier for the application</span></span> |
| `AccountObjectId` | <span data-ttu-id="b5edd-124">문자열</span><span class="sxs-lookup"><span data-stu-id="b5edd-124">string</span></span> | <span data-ttu-id="b5edd-125">Azure Active Directory의 계정에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="b5edd-125">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="b5edd-126">문자열</span><span class="sxs-lookup"><span data-stu-id="b5edd-126">string</span></span> | <span data-ttu-id="b5edd-127">주소록에 표시 되는 계정 사용자의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b5edd-127">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="b5edd-128">일반적으로 주어진 이름이 나 이름, 중간 시작, 성 또는 성의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="b5edd-128">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `IsAdminOperation` | <span data-ttu-id="b5edd-129">문자열</span><span class="sxs-lookup"><span data-stu-id="b5edd-129">string</span></span> | <span data-ttu-id="b5edd-130">관리자가 활동을 수행 했는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b5edd-130">Indicates whether the activity was performed by an administrator</span></span> |
| `DeviceType` | <span data-ttu-id="b5edd-131">문자열</span><span class="sxs-lookup"><span data-stu-id="b5edd-131">string</span></span> | <span data-ttu-id="b5edd-132">용도 및 기능을 기반으로 하는 장치 유형 (예: "네트워크 장치", "워크스테이션", "서버", "모바일", "게임 콘솔" 또는 "프린터")</span><span class="sxs-lookup"><span data-stu-id="b5edd-132">Type of device based on purpose and functionality, such as "Network device", "Workstation", "Server", "Mobile", "Gaming console", or "Printer"</span></span> | 
| `OSPlatform` | <span data-ttu-id="b5edd-133">문자열</span><span class="sxs-lookup"><span data-stu-id="b5edd-133">string</span></span> | <span data-ttu-id="b5edd-134">장치에서 실행 되는 운영 체제의 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="b5edd-134">Platform of the operating system running on the device.</span></span> <span data-ttu-id="b5edd-135">이 열은 Windows 10 및 Windows 7과 같은 같은 제품군 내의 변형을 비롯 하 여 특정 운영 체제를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b5edd-135">This column indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="b5edd-136">문자열</span><span class="sxs-lookup"><span data-stu-id="b5edd-136">string</span></span> | <span data-ttu-id="b5edd-137">끝점에 할당 되 고 관련 네트워크 통신 중에 사용 되는 IP 주소</span><span class="sxs-lookup"><span data-stu-id="b5edd-137">IP address assigned to the endpoint and used during related network communications</span></span> |
| `IsAnonymousProxy` | <span data-ttu-id="b5edd-138">문자열</span><span class="sxs-lookup"><span data-stu-id="b5edd-138">string</span></span> | <span data-ttu-id="b5edd-139">IP 주소가 알려진 익명 프록시에 속하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b5edd-139">Indicates whether the IP address belongs to a known anonymous proxy</span></span> |
| `CountryCode` | <span data-ttu-id="b5edd-140">문자열</span><span class="sxs-lookup"><span data-stu-id="b5edd-140">string</span></span> | <span data-ttu-id="b5edd-141">클라이언트 IP 주소가 geolocated 국가를 나타내는 두 문자로 된 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="b5edd-141">Two-letter code indicating the country where the client IP address is geolocated</span></span> |
| `City` | <span data-ttu-id="b5edd-142">문자열</span><span class="sxs-lookup"><span data-stu-id="b5edd-142">string</span></span> | <span data-ttu-id="b5edd-143">클라이언트 IP 주소가 geolocated 구/군/시</span><span class="sxs-lookup"><span data-stu-id="b5edd-143">City where the client IP address is geolocated</span></span> |
| `Isp` | <span data-ttu-id="b5edd-144">문자열</span><span class="sxs-lookup"><span data-stu-id="b5edd-144">string</span></span> | <span data-ttu-id="b5edd-145">IP 주소와 연결 된 ISP (인터넷 서비스 공급자)</span><span class="sxs-lookup"><span data-stu-id="b5edd-145">Internet service provider (ISP) associated with the IP address</span></span> |
| `UserAgent` | <span data-ttu-id="b5edd-146">문자열</span><span class="sxs-lookup"><span data-stu-id="b5edd-146">string</span></span> | <span data-ttu-id="b5edd-147">웹 브라우저나 다른 클라이언트 응용 프로그램의 사용자 에이전트 정보</span><span class="sxs-lookup"><span data-stu-id="b5edd-147">User agent information from the web browser or other client application</span></span> |
| `ActivityType` | <span data-ttu-id="b5edd-148">문자열</span><span class="sxs-lookup"><span data-stu-id="b5edd-148">string</span></span> | <span data-ttu-id="b5edd-149">이벤트를 트리거한 작업의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="b5edd-149">Type of activity that triggered the event</span></span> |
| `ActivityObjects` | <span data-ttu-id="b5edd-150">문자열</span><span class="sxs-lookup"><span data-stu-id="b5edd-150">string</span></span> | <span data-ttu-id="b5edd-151">기록 된 활동에 포함 된 파일 또는 폴더 등의 개체 목록</span><span class="sxs-lookup"><span data-stu-id="b5edd-151">List of objects, such as files or folders, that were involved in the recorded activity</span></span> |
| `ObjectName` | <span data-ttu-id="b5edd-152">문자열</span><span class="sxs-lookup"><span data-stu-id="b5edd-152">string</span></span> | <span data-ttu-id="b5edd-153">기록 된 작업이 적용 된 개체의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b5edd-153">Name of the object that the recorded action was applied to</span></span> |
| `ObjectType` | <span data-ttu-id="b5edd-154">문자열</span><span class="sxs-lookup"><span data-stu-id="b5edd-154">string</span></span> | <span data-ttu-id="b5edd-155">기록 된 작업이 적용 된 파일 또는 폴더와 같은 개체의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="b5edd-155">Type of object, such as a file or a folder, that the recorded action was applied to</span></span> |
| `ObjectId` | <span data-ttu-id="b5edd-156">문자열</span><span class="sxs-lookup"><span data-stu-id="b5edd-156">string</span></span> | <span data-ttu-id="b5edd-157">기록 된 작업이 적용 된 개체의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="b5edd-157">Unique identifier of the object that the recorded action was applied to</span></span> |
| `ReportId` | <span data-ttu-id="b5edd-158">문자열</span><span class="sxs-lookup"><span data-stu-id="b5edd-158">string</span></span> | <span data-ttu-id="b5edd-159">이벤트에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="b5edd-159">Unique identifier for the event</span></span> |
| `RawEventData` | <span data-ttu-id="b5edd-160">문자열</span><span class="sxs-lookup"><span data-stu-id="b5edd-160">string</span></span> | <span data-ttu-id="b5edd-161">소스 응용 프로그램 또는 서비스의 원시 이벤트 정보 (JSON 형식)</span><span class="sxs-lookup"><span data-stu-id="b5edd-161">Raw event information from the source application or service in JSON format</span></span> |
| `AdditionalFields` | <span data-ttu-id="b5edd-162">문자열</span><span class="sxs-lookup"><span data-stu-id="b5edd-162">string</span></span> | <span data-ttu-id="b5edd-163">엔터티 또는 이벤트에 대 한 추가 정보</span><span class="sxs-lookup"><span data-stu-id="b5edd-163">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="b5edd-164">관련 항목</span><span class="sxs-lookup"><span data-stu-id="b5edd-164">Related topics</span></span>
- [<span data-ttu-id="b5edd-165">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="b5edd-165">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b5edd-166">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="b5edd-166">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b5edd-167">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="b5edd-167">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="b5edd-168">기기, 전자 메일, 앱 및 ID를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="b5edd-168">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="b5edd-169">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="b5edd-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="b5edd-170">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="b5edd-170">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
