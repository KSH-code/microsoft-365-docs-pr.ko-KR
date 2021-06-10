---
title: 고급 헌팅Chema의 CloudAppEvents 테이블
description: 고급 헌팅 스위마의 CloudAppEvents 표에 있는 클라우드 앱 및 서비스의 이벤트에 대해 자세히 알아보기
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 365 Defender, microsoft 365, m365, 검색, 쿼리, 원격 분석, 스마마 참조, kusto, 표, 열, 데이터 형식, 설명, CloudAppEvents, Cloud App Security, MCAS
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
ms.openlocfilehash: 17f424d368c0df2f07cda41917f005e4163e5750
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935872"
---
# <a name="cloudappevents"></a><span data-ttu-id="e4628-104">CloudAppEvents</span><span class="sxs-lookup"><span data-stu-id="e4628-104">CloudAppEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e4628-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="e4628-105">**Applies to:**</span></span>
- <span data-ttu-id="e4628-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e4628-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="e4628-107">고급 `CloudAppEvents` 헌팅 [계획의](advanced-hunting-overview.md) 표에는 다양한 클라우드 앱 및 서비스에서 지원되는 활동에 대한 정보가 Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="e4628-107">The `CloudAppEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about activities in various cloud apps and services covered by Microsoft Cloud App Security.</span></span> <span data-ttu-id="e4628-108">전체 목록을 위해 를 다루는 [앱 및 서비스로 이동하세요.](#apps-and-services-covered)</span><span class="sxs-lookup"><span data-stu-id="e4628-108">For a complete list, jump to [Apps and services covered](#apps-and-services-covered).</span></span> <span data-ttu-id="e4628-109">이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e4628-109">Use this reference to construct queries that return information from this table.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="e4628-110">이 표에는 표에서 사용할 수 있는 정보가 `AppFileEvents` 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4628-110">This table includes information that used to be available in the `AppFileEvents` table.</span></span> <span data-ttu-id="e4628-111">2021년 3월 7일 이후 클라우드 서비스에서 파일 관련 활동을 찾은 사용자는 대신 이 표를 사용해야 `CloudAppEvents` 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4628-111">Starting March 7, 2021, users hunting through file-related activities in cloud services on and beyond this date should use the `CloudAppEvents` table instead.</span></span> <br><br><span data-ttu-id="e4628-112">테이블을 계속 사용하는 쿼리 및 사용자 지정 검색 규칙을 검색하고 테이블을 사용하여 `AppFileEvents` 편집해야 `CloudAppEvents` 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4628-112">Make sure to search for queries and custom detection rules that still use the `AppFileEvents` table and edit them to use the `CloudAppEvents` table.</span></span> <span data-ttu-id="e4628-113">영향을 받는 쿼리 변환에 대한 자세한 지침은 Defender 고급 헌팅을 사용하여 클라우드 앱 활동에서 [헌트에서 Microsoft 365 있습니다.](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857)</span><span class="sxs-lookup"><span data-stu-id="e4628-113">More guidance about converting affected queries can be found in [Hunt across cloud app activities with Microsoft 365 Defender advanced hunting](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857).</span></span>


<span data-ttu-id="e4628-114">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e4628-114">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="e4628-115">열 이름</span><span class="sxs-lookup"><span data-stu-id="e4628-115">Column name</span></span> | <span data-ttu-id="e4628-116">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="e4628-116">Data type</span></span> | <span data-ttu-id="e4628-117">설명</span><span class="sxs-lookup"><span data-stu-id="e4628-117">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="e4628-118">datetime</span><span class="sxs-lookup"><span data-stu-id="e4628-118">datetime</span></span> | <span data-ttu-id="e4628-119">이벤트가 기록된 날짜와 시간</span><span class="sxs-lookup"><span data-stu-id="e4628-119">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="e4628-120">문자열</span><span class="sxs-lookup"><span data-stu-id="e4628-120">string</span></span> | <span data-ttu-id="e4628-121">이벤트를 트리거한 활동 유형</span><span class="sxs-lookup"><span data-stu-id="e4628-121">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="e4628-122">문자열</span><span class="sxs-lookup"><span data-stu-id="e4628-122">string</span></span> | <span data-ttu-id="e4628-123">기록된 작업을 수행한 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="e4628-123">Application that performed the recorded action</span></span> |
| `ApplicationId` | <span data-ttu-id="e4628-124">문자열</span><span class="sxs-lookup"><span data-stu-id="e4628-124">string</span></span> | <span data-ttu-id="e4628-125">응용 프로그램의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="e4628-125">Unique identifier for the application</span></span> |
| `AccountObjectId` | <span data-ttu-id="e4628-126">문자열</span><span class="sxs-lookup"><span data-stu-id="e4628-126">string</span></span> | <span data-ttu-id="e4628-127">계정의 고유 식별자입니다Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="e4628-127">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="e4628-128">문자열</span><span class="sxs-lookup"><span data-stu-id="e4628-128">string</span></span> | <span data-ttu-id="e4628-129">주소부에 표시된 계정 사용자의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e4628-129">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="e4628-130">일반적으로 지정한 이름이나 이름, 중간 시작, 성 또는 성의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="e4628-130">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `IsAdminOperation` | <span data-ttu-id="e4628-131">문자열</span><span class="sxs-lookup"><span data-stu-id="e4628-131">string</span></span> | <span data-ttu-id="e4628-132">관리자가 활동을 수행한지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e4628-132">Indicates whether the activity was performed by an administrator</span></span> |
| `DeviceType` | <span data-ttu-id="e4628-133">문자열</span><span class="sxs-lookup"><span data-stu-id="e4628-133">string</span></span> | <span data-ttu-id="e4628-134">"네트워크 장치", "Workstation", "Server", "모바일", "게임 콘솔" 또는 "프린터" 등의 목적 및 기능에 기반한 디바이스 유형</span><span class="sxs-lookup"><span data-stu-id="e4628-134">Type of device based on purpose and functionality, such as "Network device", "Workstation", "Server", "Mobile", "Gaming console", or "Printer"</span></span> | 
| `OSPlatform` | <span data-ttu-id="e4628-135">문자열</span><span class="sxs-lookup"><span data-stu-id="e4628-135">string</span></span> | <span data-ttu-id="e4628-136">디바이스에서 실행되는 운영 체제의 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="e4628-136">Platform of the operating system running on the device.</span></span> <span data-ttu-id="e4628-137">이 열은 Windows 10 및 Windows 같은 패밀리 내의 변형을 포함하여 특정 운영 체제를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e4628-137">This column indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="e4628-138">문자열</span><span class="sxs-lookup"><span data-stu-id="e4628-138">string</span></span> | <span data-ttu-id="e4628-139">끝점에 할당되어 관련 네트워크 통신 중에 사용되는 IP 주소</span><span class="sxs-lookup"><span data-stu-id="e4628-139">IP address assigned to the endpoint and used during related network communications</span></span> |
| `IsAnonymousProxy` | <span data-ttu-id="e4628-140">문자열</span><span class="sxs-lookup"><span data-stu-id="e4628-140">string</span></span> | <span data-ttu-id="e4628-141">IP 주소가 알려진 익명 프록시에 속하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e4628-141">Indicates whether the IP address belongs to a known anonymous proxy</span></span> |
| `CountryCode` | <span data-ttu-id="e4628-142">문자열</span><span class="sxs-lookup"><span data-stu-id="e4628-142">string</span></span> | <span data-ttu-id="e4628-143">클라이언트 IP 주소가 지리적으로 위치가 지정되는 국가를 나타내는 두 글자 코드</span><span class="sxs-lookup"><span data-stu-id="e4628-143">Two-letter code indicating the country where the client IP address is geolocated</span></span> |
| `City` | <span data-ttu-id="e4628-144">문자열</span><span class="sxs-lookup"><span data-stu-id="e4628-144">string</span></span> | <span data-ttu-id="e4628-145">클라이언트 IP 주소가 지리적으로 위치가 지정되는 구</span><span class="sxs-lookup"><span data-stu-id="e4628-145">City where the client IP address is geolocated</span></span> |
| `Isp` | <span data-ttu-id="e4628-146">문자열</span><span class="sxs-lookup"><span data-stu-id="e4628-146">string</span></span> | <span data-ttu-id="e4628-147">IP 주소와 연결된 ISP(인터넷 서비스 공급자)</span><span class="sxs-lookup"><span data-stu-id="e4628-147">Internet service provider (ISP) associated with the IP address</span></span> |
| `UserAgent` | <span data-ttu-id="e4628-148">문자열</span><span class="sxs-lookup"><span data-stu-id="e4628-148">string</span></span> | <span data-ttu-id="e4628-149">웹 브라우저 또는 기타 클라이언트 응용 프로그램의 사용자 에이전트 정보</span><span class="sxs-lookup"><span data-stu-id="e4628-149">User agent information from the web browser or other client application</span></span> |
| `ActivityType` | <span data-ttu-id="e4628-150">문자열</span><span class="sxs-lookup"><span data-stu-id="e4628-150">string</span></span> | <span data-ttu-id="e4628-151">이벤트를 트리거한 활동 유형</span><span class="sxs-lookup"><span data-stu-id="e4628-151">Type of activity that triggered the event</span></span> |
| `ActivityObjects` | <span data-ttu-id="e4628-152">문자열</span><span class="sxs-lookup"><span data-stu-id="e4628-152">string</span></span> | <span data-ttu-id="e4628-153">기록된 활동에 관련된 파일 또는 폴더와 같은 개체 목록</span><span class="sxs-lookup"><span data-stu-id="e4628-153">List of objects, such as files or folders, that were involved in the recorded activity</span></span> |
| `ObjectName` | <span data-ttu-id="e4628-154">문자열</span><span class="sxs-lookup"><span data-stu-id="e4628-154">string</span></span> | <span data-ttu-id="e4628-155">기록된 동작이 적용된 개체의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e4628-155">Name of the object that the recorded action was applied to</span></span> |
| `ObjectType` | <span data-ttu-id="e4628-156">문자열</span><span class="sxs-lookup"><span data-stu-id="e4628-156">string</span></span> | <span data-ttu-id="e4628-157">기록된 작업이 적용된 개체 유형(예: 파일 또는 폴더)입니다.</span><span class="sxs-lookup"><span data-stu-id="e4628-157">Type of object, such as a file or a folder, that the recorded action was applied to</span></span> |
| `ObjectId` | <span data-ttu-id="e4628-158">문자열</span><span class="sxs-lookup"><span data-stu-id="e4628-158">string</span></span> | <span data-ttu-id="e4628-159">기록된 작업이 적용된 개체의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="e4628-159">Unique identifier of the object that the recorded action was applied to</span></span> |
| `ReportId` | <span data-ttu-id="e4628-160">문자열</span><span class="sxs-lookup"><span data-stu-id="e4628-160">string</span></span> | <span data-ttu-id="e4628-161">이벤트의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="e4628-161">Unique identifier for the event</span></span> |
| `RawEventData` | <span data-ttu-id="e4628-162">문자열</span><span class="sxs-lookup"><span data-stu-id="e4628-162">string</span></span> | <span data-ttu-id="e4628-163">원본 응용 프로그램 또는 서비스의 원시 이벤트 정보(JSON 형식)</span><span class="sxs-lookup"><span data-stu-id="e4628-163">Raw event information from the source application or service in JSON format</span></span> |
| `AdditionalFields` | <span data-ttu-id="e4628-164">문자열</span><span class="sxs-lookup"><span data-stu-id="e4628-164">string</span></span> | <span data-ttu-id="e4628-165">엔터티 또는 이벤트에 대한 추가 정보</span><span class="sxs-lookup"><span data-stu-id="e4628-165">Additional information about the entity or event</span></span> |

## <a name="apps-and-services-covered"></a><span data-ttu-id="e4628-166">적용된 앱 및 서비스</span><span class="sxs-lookup"><span data-stu-id="e4628-166">Apps and services covered</span></span>

- <span data-ttu-id="e4628-167">Dropbox</span><span class="sxs-lookup"><span data-stu-id="e4628-167">Dropbox</span></span>
- <span data-ttu-id="e4628-168">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="e4628-168">Dynamics 365</span></span>
- <span data-ttu-id="e4628-169">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e4628-169">Exchange Online</span></span>
- <span data-ttu-id="e4628-170">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e4628-170">Microsoft Teams</span></span>
- <span data-ttu-id="e4628-171">비즈니스용 OneDrive</span><span class="sxs-lookup"><span data-stu-id="e4628-171">OneDrive for Business</span></span>
- <span data-ttu-id="e4628-172">Power Automate</span><span class="sxs-lookup"><span data-stu-id="e4628-172">Power Automate</span></span>
- <span data-ttu-id="e4628-173">Power BI</span><span class="sxs-lookup"><span data-stu-id="e4628-173">Power BI</span></span>
- <span data-ttu-id="e4628-174">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e4628-174">SharePoint Online</span></span>
- <span data-ttu-id="e4628-175">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="e4628-175">Skype for Business</span></span>
- <span data-ttu-id="e4628-176">Office 365</span><span class="sxs-lookup"><span data-stu-id="e4628-176">Office 365</span></span>
- <span data-ttu-id="e4628-177">Yammer</span><span class="sxs-lookup"><span data-stu-id="e4628-177">Yammer</span></span> 

## <a name="related-topics"></a><span data-ttu-id="e4628-178">관련 항목</span><span class="sxs-lookup"><span data-stu-id="e4628-178">Related topics</span></span>
- [<span data-ttu-id="e4628-179">지능형 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="e4628-179">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e4628-180">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="e4628-180">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e4628-181">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="e4628-181">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="e4628-182">장치, 전자 메일, 앱 및 ID를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="e4628-182">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="e4628-183">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="e4628-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="e4628-184">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="e4628-184">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
