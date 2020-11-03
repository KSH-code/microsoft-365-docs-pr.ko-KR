---
title: 고급 구하기 스키마의 AppFileEvents 테이블
description: 고급 구하기 스키마의 AppFileEvents 테이블에 있는 클라우드 앱 및 서비스와 연결 된 파일 관련 이벤트에 대해 자세히 알아봅니다.
keywords: 고급 구하기, 위협 검색, 사이버 위협 검색, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 스키마 참조, kusto, table, column, data type, description, AppFileEvents, Cloud App Security, MCAS
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
ms.openlocfilehash: 1a7f523e96c0a46c29098f7e5bb2fbb83a4db4bb
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847659"
---
# <a name="appfileevents"></a><span data-ttu-id="6f705-104">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="6f705-104">AppFileEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6f705-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="6f705-105">**Applies to:**</span></span>
- <span data-ttu-id="6f705-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6f705-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="6f705-107">`AppFileEvents` [고급 구하기](advanced-hunting-overview.md) 스키마의 표에는 Microsoft cloud App Security에서 모니터링 하는 클라우드 앱 및 서비스의 파일 관련 작업에 대 한 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f705-107">The `AppFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file-related activities in cloud apps and services monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="6f705-108">이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="6f705-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="6f705-109">테이블에서 지 원하는 이벤트 유형 (값)에 대 한 자세한 내용은 `ActionType` 보안 센터에서 사용할 수 있는 [기본 제공 스키마 참조](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 를 사용 하십시오.</span><span class="sxs-lookup"><span data-stu-id="6f705-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="6f705-110">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6f705-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="6f705-111">열 이름</span><span class="sxs-lookup"><span data-stu-id="6f705-111">Column name</span></span> | <span data-ttu-id="6f705-112">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="6f705-112">Data type</span></span> | <span data-ttu-id="6f705-113">설명</span><span class="sxs-lookup"><span data-stu-id="6f705-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="6f705-114">datetime</span><span class="sxs-lookup"><span data-stu-id="6f705-114">datetime</span></span> | <span data-ttu-id="6f705-115">이벤트가 기록된 날짜와 시간</span><span class="sxs-lookup"><span data-stu-id="6f705-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="6f705-116">문자열</span><span class="sxs-lookup"><span data-stu-id="6f705-116">string</span></span> | <span data-ttu-id="6f705-117">이벤트를 트리거한 작업의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="6f705-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="6f705-118">자세한 내용은 [portal 스키마 참조](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6f705-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="6f705-119">문자열</span><span class="sxs-lookup"><span data-stu-id="6f705-119">string</span></span> | <span data-ttu-id="6f705-120">기록 된 작업을 수행한 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="6f705-120">Application that performed the recorded action</span></span> |
| `FileName` | <span data-ttu-id="6f705-121">문자열</span><span class="sxs-lookup"><span data-stu-id="6f705-121">string</span></span> | <span data-ttu-id="6f705-122">기록된 조치가 적용된 파일의 이름</span><span class="sxs-lookup"><span data-stu-id="6f705-122">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="6f705-123">문자열</span><span class="sxs-lookup"><span data-stu-id="6f705-123">string</span></span> | <span data-ttu-id="6f705-124">기록 된 작업이 적용 된 파일을 포함 하는 폴더</span><span class="sxs-lookup"><span data-stu-id="6f705-124">Folder containing the file that the recorded action was applied to</span></span> |
| `PreviousFileName` | <span data-ttu-id="6f705-125">문자열</span><span class="sxs-lookup"><span data-stu-id="6f705-125">string</span></span> | <span data-ttu-id="6f705-126">동작의 결과로 이름이 바뀐 파일의 원래 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6f705-126">Original name of the file that was renamed as a result of the action</span></span> |
| `PreviousFolderPath` | <span data-ttu-id="6f705-127">문자열</span><span class="sxs-lookup"><span data-stu-id="6f705-127">string</span></span> | <span data-ttu-id="6f705-128">기록 된 작업을 적용 하기 전의 파일을 포함 하는 원래 폴더</span><span class="sxs-lookup"><span data-stu-id="6f705-128">Original folder containing the file before the recorded action was applied</span></span> |
| `Protocol` | <span data-ttu-id="6f705-129">문자열</span><span class="sxs-lookup"><span data-stu-id="6f705-129">string</span></span> | <span data-ttu-id="6f705-130">사용 되는 네트워크 프로토콜</span><span class="sxs-lookup"><span data-stu-id="6f705-130">Network protocol used</span></span> |
| `AccountName` | <span data-ttu-id="6f705-131">문자열</span><span class="sxs-lookup"><span data-stu-id="6f705-131">string</span></span> | <span data-ttu-id="6f705-132">계정의 사용자 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6f705-132">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="6f705-133">문자열</span><span class="sxs-lookup"><span data-stu-id="6f705-133">string</span></span> | <span data-ttu-id="6f705-134">계정의 도메인</span><span class="sxs-lookup"><span data-stu-id="6f705-134">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="6f705-135">문자열</span><span class="sxs-lookup"><span data-stu-id="6f705-135">string</span></span> | <span data-ttu-id="6f705-136">계정의 UPN (사용자 계정 이름)</span><span class="sxs-lookup"><span data-stu-id="6f705-136">User principal name (UPN) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="6f705-137">문자열</span><span class="sxs-lookup"><span data-stu-id="6f705-137">string</span></span> | <span data-ttu-id="6f705-138">Azure AD의 계정에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="6f705-138">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="6f705-139">문자열</span><span class="sxs-lookup"><span data-stu-id="6f705-139">string</span></span> | <span data-ttu-id="6f705-140">주소록에 표시 되는 계정 사용자의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6f705-140">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="6f705-141">일반적으로 주어진 이름이 나 이름, 중간 시작, 성 또는 성의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="6f705-141">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="6f705-142">문자열</span><span class="sxs-lookup"><span data-stu-id="6f705-142">string</span></span> | <span data-ttu-id="6f705-143">장치의 FQDN (정규화 된 도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="6f705-143">Fully qualified domain name (FQDN) of the device</span></span> |
| `DeviceType` | <span data-ttu-id="6f705-144">문자열</span><span class="sxs-lookup"><span data-stu-id="6f705-144">string</span></span> | <span data-ttu-id="6f705-145">장치 유형</span><span class="sxs-lookup"><span data-stu-id="6f705-145">Type of device</span></span> | 
| `OSPlatform` | <span data-ttu-id="6f705-146">문자열</span><span class="sxs-lookup"><span data-stu-id="6f705-146">string</span></span> | <span data-ttu-id="6f705-147">장치에서 실행 되는 운영 체제의 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="6f705-147">Platform of the operating system running on the device.</span></span> <span data-ttu-id="6f705-148">이는 Windows 10 및 Windows 7과 같이 동일한 제품군 내의 변형을 포함하여 특정 운영 체제를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6f705-148">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="6f705-149">문자열</span><span class="sxs-lookup"><span data-stu-id="6f705-149">string</span></span> | <span data-ttu-id="6f705-150">끝점에 할당 되 고 관련 네트워크 통신 중에 사용 되는 IP 주소</span><span class="sxs-lookup"><span data-stu-id="6f705-150">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="6f705-151">문자열</span><span class="sxs-lookup"><span data-stu-id="6f705-151">string</span></span> | <span data-ttu-id="6f705-152">기록 된 작업을 처리 한 서버 응용 프로그램을 실행 하는 장치의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6f705-152">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="6f705-153">문자열</span><span class="sxs-lookup"><span data-stu-id="6f705-153">string</span></span> | <span data-ttu-id="6f705-154">기록 된 작업을 처리 한 서버 응용 프로그램을 실행 하는 장치의 IP 주소</span><span class="sxs-lookup"><span data-stu-id="6f705-154">IP address of the device running the server application that processed the recorded action</span></span> |
| `Location` | <span data-ttu-id="6f705-155">문자열</span><span class="sxs-lookup"><span data-stu-id="6f705-155">string</span></span> | <span data-ttu-id="6f705-156">이벤트와 관련 된 구/군/시, 국가 또는 기타 지리적 위치</span><span class="sxs-lookup"><span data-stu-id="6f705-156">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="6f705-157">문자열</span><span class="sxs-lookup"><span data-stu-id="6f705-157">string</span></span> | <span data-ttu-id="6f705-158">끝점 IP 주소와 연결 된 ISP (인터넷 서비스 공급자)</span><span class="sxs-lookup"><span data-stu-id="6f705-158">Internet service provider (ISP) associated with the endpoint IP address</span></span> |
| `ReportId` | <span data-ttu-id="6f705-159">long</span><span class="sxs-lookup"><span data-stu-id="6f705-159">long</span></span> | <span data-ttu-id="6f705-160">이벤트에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="6f705-160">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="6f705-161">문자열</span><span class="sxs-lookup"><span data-stu-id="6f705-161">string</span></span> | <span data-ttu-id="6f705-162">엔터티 또는 이벤트에 대 한 추가 정보</span><span class="sxs-lookup"><span data-stu-id="6f705-162">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="6f705-163">관련 항목</span><span class="sxs-lookup"><span data-stu-id="6f705-163">Related topics</span></span>
- [<span data-ttu-id="6f705-164">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="6f705-164">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6f705-165">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="6f705-165">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="6f705-166">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="6f705-166">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="6f705-167">기기, 전자 메일, 앱 및 ID를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="6f705-167">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="6f705-168">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="6f705-168">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="6f705-169">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="6f705-169">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
