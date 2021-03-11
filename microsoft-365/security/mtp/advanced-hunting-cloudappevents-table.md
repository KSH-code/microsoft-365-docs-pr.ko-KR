---
title: 고급 헌팅Chema의 CloudAppEvents 테이블
description: 고급 헌팅 스위마의 CloudAppEvents 표에 있는 클라우드 앱 및 서비스의 이벤트에 대해 자세히 알아보기
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 위협 방지, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 스마 참조, kusto, 표, 열, 데이터 형식, 설명, CloudAppEvents, Cloud App Security, MCAS
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
ms.openlocfilehash: a8ba1f94bc704a5fe99d54b77aa6570c5e43d3f7
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712489"
---
# <a name="cloudappevents"></a><span data-ttu-id="50ab1-104">CloudAppEvents</span><span class="sxs-lookup"><span data-stu-id="50ab1-104">CloudAppEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="50ab1-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="50ab1-105">**Applies to:**</span></span>
- <span data-ttu-id="50ab1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="50ab1-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="50ab1-107">고급 헌팅 계획의 표에는 Microsoft Cloud App Security( 특히 `CloudAppEvents` Dropbox, Exchange Online, OneDrive, Microsoft Teams 및 SharePoint)에서 다루는 다양한 클라우드 앱 및 서비스의 활동에 대한 정보가 포함되어 있습니다. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="50ab1-107">The `CloudAppEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about activities in various cloud apps and services covered by Microsoft Cloud App Security, specifically Dropbox, Exchange Online, OneDrive, Microsoft Teams, and SharePoint.</span></span> <span data-ttu-id="50ab1-108">이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="50ab1-108">Use this reference to construct queries that return information from this table.</span></span>

>[!IMPORTANT]
><span data-ttu-id="50ab1-109">이 표에는 표에서 사용할 수 있는 정보가 `AppFileEvents` 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50ab1-109">This table includes information that used to be available in the `AppFileEvents` table.</span></span> <span data-ttu-id="50ab1-110">2021년 3월 7일 이후 클라우드 서비스에서 파일 관련 활동을 찾은 사용자는 대신 이 표를 사용해야 `CloudAppEvents` 합니다.</span><span class="sxs-lookup"><span data-stu-id="50ab1-110">Starting March 7, 2021, users hunting through file-related activities in cloud services on and beyond this date should use the `CloudAppEvents` table instead.</span></span> <br><br><span data-ttu-id="50ab1-111">테이블을 계속 사용하는 쿼리 및 사용자 지정 검색 규칙을 검색하고 테이블을 사용하여 `AppFileEvents` 편집해야 `CloudAppEvents` 합니다.</span><span class="sxs-lookup"><span data-stu-id="50ab1-111">Make sure to search for queries and custom detection rules that still use the `AppFileEvents` table and edit them to use the `CloudAppEvents` table.</span></span> <span data-ttu-id="50ab1-112">영향을 받는 쿼리를 변환하는 방법에 대한 자세한 지침은 [Microsoft 365 Defender](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857)고급 헌팅을 사용하여 클라우드 앱 활동에서 헌트에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50ab1-112">More guidance about converting affected queries can be found in [Hunt across cloud app activities with Microsoft 365 Defender advanced hunting](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857).</span></span>


<span data-ttu-id="50ab1-113">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="50ab1-113">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="50ab1-114">열 이름</span><span class="sxs-lookup"><span data-stu-id="50ab1-114">Column name</span></span> | <span data-ttu-id="50ab1-115">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="50ab1-115">Data type</span></span> | <span data-ttu-id="50ab1-116">설명</span><span class="sxs-lookup"><span data-stu-id="50ab1-116">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="50ab1-117">datetime</span><span class="sxs-lookup"><span data-stu-id="50ab1-117">datetime</span></span> | <span data-ttu-id="50ab1-118">이벤트가 기록된 날짜와 시간</span><span class="sxs-lookup"><span data-stu-id="50ab1-118">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="50ab1-119">문자열</span><span class="sxs-lookup"><span data-stu-id="50ab1-119">string</span></span> | <span data-ttu-id="50ab1-120">이벤트를 트리거한 활동 유형</span><span class="sxs-lookup"><span data-stu-id="50ab1-120">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="50ab1-121">문자열</span><span class="sxs-lookup"><span data-stu-id="50ab1-121">string</span></span> | <span data-ttu-id="50ab1-122">기록된 작업을 수행한 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="50ab1-122">Application that performed the recorded action</span></span> |
| `ApplicationId` | <span data-ttu-id="50ab1-123">문자열</span><span class="sxs-lookup"><span data-stu-id="50ab1-123">string</span></span> | <span data-ttu-id="50ab1-124">응용 프로그램의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="50ab1-124">Unique identifier for the application</span></span> |
| `AccountObjectId` | <span data-ttu-id="50ab1-125">문자열</span><span class="sxs-lookup"><span data-stu-id="50ab1-125">string</span></span> | <span data-ttu-id="50ab1-126">Azure Active Directory에서 계정의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="50ab1-126">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="50ab1-127">문자열</span><span class="sxs-lookup"><span data-stu-id="50ab1-127">string</span></span> | <span data-ttu-id="50ab1-128">주소부에 표시된 계정 사용자의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="50ab1-128">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="50ab1-129">일반적으로 지정한 이름이나 이름, 중간 시작, 성 또는 성의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="50ab1-129">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `IsAdminOperation` | <span data-ttu-id="50ab1-130">문자열</span><span class="sxs-lookup"><span data-stu-id="50ab1-130">string</span></span> | <span data-ttu-id="50ab1-131">관리자가 활동을 수행한지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="50ab1-131">Indicates whether the activity was performed by an administrator</span></span> |
| `DeviceType` | <span data-ttu-id="50ab1-132">문자열</span><span class="sxs-lookup"><span data-stu-id="50ab1-132">string</span></span> | <span data-ttu-id="50ab1-133">"네트워크 장치", "Workstation", "Server", "모바일", "게임 콘솔" 또는 "프린터" 등의 목적 및 기능에 기반한 디바이스 유형</span><span class="sxs-lookup"><span data-stu-id="50ab1-133">Type of device based on purpose and functionality, such as "Network device", "Workstation", "Server", "Mobile", "Gaming console", or "Printer"</span></span> | 
| `OSPlatform` | <span data-ttu-id="50ab1-134">문자열</span><span class="sxs-lookup"><span data-stu-id="50ab1-134">string</span></span> | <span data-ttu-id="50ab1-135">디바이스에서 실행되는 운영 체제의 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="50ab1-135">Platform of the operating system running on the device.</span></span> <span data-ttu-id="50ab1-136">이 열은 Windows 10 및 Windows 7과 같은 동일한 패밀리 내의 변형을 포함하여 특정 운영 체제를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="50ab1-136">This column indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="50ab1-137">문자열</span><span class="sxs-lookup"><span data-stu-id="50ab1-137">string</span></span> | <span data-ttu-id="50ab1-138">끝점에 할당되어 관련 네트워크 통신 중에 사용되는 IP 주소</span><span class="sxs-lookup"><span data-stu-id="50ab1-138">IP address assigned to the endpoint and used during related network communications</span></span> |
| `IsAnonymousProxy` | <span data-ttu-id="50ab1-139">문자열</span><span class="sxs-lookup"><span data-stu-id="50ab1-139">string</span></span> | <span data-ttu-id="50ab1-140">IP 주소가 알려진 익명 프록시에 속하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="50ab1-140">Indicates whether the IP address belongs to a known anonymous proxy</span></span> |
| `CountryCode` | <span data-ttu-id="50ab1-141">문자열</span><span class="sxs-lookup"><span data-stu-id="50ab1-141">string</span></span> | <span data-ttu-id="50ab1-142">클라이언트 IP 주소가 지리적으로 위치가 지정되는 국가를 나타내는 두 글자 코드</span><span class="sxs-lookup"><span data-stu-id="50ab1-142">Two-letter code indicating the country where the client IP address is geolocated</span></span> |
| `City` | <span data-ttu-id="50ab1-143">문자열</span><span class="sxs-lookup"><span data-stu-id="50ab1-143">string</span></span> | <span data-ttu-id="50ab1-144">클라이언트 IP 주소가 지리적으로 위치가 지정되는 구</span><span class="sxs-lookup"><span data-stu-id="50ab1-144">City where the client IP address is geolocated</span></span> |
| `Isp` | <span data-ttu-id="50ab1-145">문자열</span><span class="sxs-lookup"><span data-stu-id="50ab1-145">string</span></span> | <span data-ttu-id="50ab1-146">IP 주소와 연결된 ISP(인터넷 서비스 공급자)</span><span class="sxs-lookup"><span data-stu-id="50ab1-146">Internet service provider (ISP) associated with the IP address</span></span> |
| `UserAgent` | <span data-ttu-id="50ab1-147">문자열</span><span class="sxs-lookup"><span data-stu-id="50ab1-147">string</span></span> | <span data-ttu-id="50ab1-148">웹 브라우저 또는 기타 클라이언트 응용 프로그램의 사용자 에이전트 정보</span><span class="sxs-lookup"><span data-stu-id="50ab1-148">User agent information from the web browser or other client application</span></span> |
| `ActivityType` | <span data-ttu-id="50ab1-149">문자열</span><span class="sxs-lookup"><span data-stu-id="50ab1-149">string</span></span> | <span data-ttu-id="50ab1-150">이벤트를 트리거한 활동 유형</span><span class="sxs-lookup"><span data-stu-id="50ab1-150">Type of activity that triggered the event</span></span> |
| `ActivityObjects` | <span data-ttu-id="50ab1-151">문자열</span><span class="sxs-lookup"><span data-stu-id="50ab1-151">string</span></span> | <span data-ttu-id="50ab1-152">기록된 활동에 관련된 파일 또는 폴더와 같은 개체 목록</span><span class="sxs-lookup"><span data-stu-id="50ab1-152">List of objects, such as files or folders, that were involved in the recorded activity</span></span> |
| `ObjectName` | <span data-ttu-id="50ab1-153">문자열</span><span class="sxs-lookup"><span data-stu-id="50ab1-153">string</span></span> | <span data-ttu-id="50ab1-154">기록된 동작이 적용된 개체의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="50ab1-154">Name of the object that the recorded action was applied to</span></span> |
| `ObjectType` | <span data-ttu-id="50ab1-155">문자열</span><span class="sxs-lookup"><span data-stu-id="50ab1-155">string</span></span> | <span data-ttu-id="50ab1-156">기록된 작업이 적용된 개체 유형(예: 파일 또는 폴더)입니다.</span><span class="sxs-lookup"><span data-stu-id="50ab1-156">Type of object, such as a file or a folder, that the recorded action was applied to</span></span> |
| `ObjectId` | <span data-ttu-id="50ab1-157">문자열</span><span class="sxs-lookup"><span data-stu-id="50ab1-157">string</span></span> | <span data-ttu-id="50ab1-158">기록된 작업이 적용된 개체의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="50ab1-158">Unique identifier of the object that the recorded action was applied to</span></span> |
| `ReportId` | <span data-ttu-id="50ab1-159">문자열</span><span class="sxs-lookup"><span data-stu-id="50ab1-159">string</span></span> | <span data-ttu-id="50ab1-160">이벤트의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="50ab1-160">Unique identifier for the event</span></span> |
| `RawEventData` | <span data-ttu-id="50ab1-161">문자열</span><span class="sxs-lookup"><span data-stu-id="50ab1-161">string</span></span> | <span data-ttu-id="50ab1-162">원본 응용 프로그램 또는 서비스의 원시 이벤트 정보(JSON 형식)</span><span class="sxs-lookup"><span data-stu-id="50ab1-162">Raw event information from the source application or service in JSON format</span></span> |
| `AdditionalFields` | <span data-ttu-id="50ab1-163">문자열</span><span class="sxs-lookup"><span data-stu-id="50ab1-163">string</span></span> | <span data-ttu-id="50ab1-164">엔터티 또는 이벤트에 대한 추가 정보</span><span class="sxs-lookup"><span data-stu-id="50ab1-164">Additional information about the entity or event</span></span> |


## <a name="related-topics"></a><span data-ttu-id="50ab1-165">관련 항목</span><span class="sxs-lookup"><span data-stu-id="50ab1-165">Related topics</span></span>
- [<span data-ttu-id="50ab1-166">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="50ab1-166">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="50ab1-167">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="50ab1-167">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="50ab1-168">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="50ab1-168">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="50ab1-169">장치, 전자 메일, 앱 및 ID를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="50ab1-169">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="50ab1-170">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="50ab1-170">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="50ab1-171">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="50ab1-171">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
