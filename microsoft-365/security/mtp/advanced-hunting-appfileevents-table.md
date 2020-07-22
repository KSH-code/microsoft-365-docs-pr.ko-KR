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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 663dc2a3de676fa2daeab3d9621254e956d42fc4
ms.sourcegitcommit: b4119682bd3c036289e851fff56fde869c816479
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/22/2020
ms.locfileid: "45204758"
---
# <a name="appfileevents"></a><span data-ttu-id="4adeb-104">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="4adeb-104">AppFileEvents</span></span>

<span data-ttu-id="4adeb-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="4adeb-105">**Applies to:**</span></span>
- <span data-ttu-id="4adeb-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="4adeb-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="4adeb-107">`AppFileEvents` [고급 구하기](advanced-hunting-overview.md) 스키마의 표에는 Microsoft cloud App Security에서 모니터링 하는 클라우드 앱 및 서비스의 파일 관련 작업에 대 한 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4adeb-107">The `AppFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file-related activities in cloud apps and services monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="4adeb-108">이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="4adeb-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="4adeb-109">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4adeb-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="4adeb-110">열 이름</span><span class="sxs-lookup"><span data-stu-id="4adeb-110">Column name</span></span> | <span data-ttu-id="4adeb-111">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4adeb-111">Data type</span></span> | <span data-ttu-id="4adeb-112">설명</span><span class="sxs-lookup"><span data-stu-id="4adeb-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="4adeb-113">datetime</span><span class="sxs-lookup"><span data-stu-id="4adeb-113">datetime</span></span> | <span data-ttu-id="4adeb-114">이벤트가 기록된 날짜와 시간</span><span class="sxs-lookup"><span data-stu-id="4adeb-114">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="4adeb-115">문자열</span><span class="sxs-lookup"><span data-stu-id="4adeb-115">string</span></span> | <span data-ttu-id="4adeb-116">이벤트를 트리거한 작업의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="4adeb-116">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="4adeb-117">문자열</span><span class="sxs-lookup"><span data-stu-id="4adeb-117">string</span></span> | <span data-ttu-id="4adeb-118">기록 된 작업을 수행한 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="4adeb-118">Application that performed the recorded action</span></span> |
| `FileName` | <span data-ttu-id="4adeb-119">문자열</span><span class="sxs-lookup"><span data-stu-id="4adeb-119">string</span></span> | <span data-ttu-id="4adeb-120">기록된 조치가 적용된 파일의 이름</span><span class="sxs-lookup"><span data-stu-id="4adeb-120">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="4adeb-121">문자열</span><span class="sxs-lookup"><span data-stu-id="4adeb-121">string</span></span> | <span data-ttu-id="4adeb-122">기록 된 작업이 적용 된 파일을 포함 하는 폴더</span><span class="sxs-lookup"><span data-stu-id="4adeb-122">Folder containing the file that the recorded action was applied to</span></span> |
| `PreviousFileName` | <span data-ttu-id="4adeb-123">문자열</span><span class="sxs-lookup"><span data-stu-id="4adeb-123">string</span></span> | <span data-ttu-id="4adeb-124">동작의 결과로 이름이 바뀐 파일의 원래 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4adeb-124">Original name of the file that was renamed as a result of the action</span></span> |
| `PreviousFolderPath` | <span data-ttu-id="4adeb-125">문자열</span><span class="sxs-lookup"><span data-stu-id="4adeb-125">string</span></span> | <span data-ttu-id="4adeb-126">기록 된 작업을 적용 하기 전의 파일을 포함 하는 원래 폴더</span><span class="sxs-lookup"><span data-stu-id="4adeb-126">Original folder containing the file before the recorded action was applied</span></span> |
| `Protocol` | <span data-ttu-id="4adeb-127">문자열</span><span class="sxs-lookup"><span data-stu-id="4adeb-127">string</span></span> | <span data-ttu-id="4adeb-128">사용 되는 네트워크 프로토콜</span><span class="sxs-lookup"><span data-stu-id="4adeb-128">Network protocol used</span></span> |
| `AccountName` | <span data-ttu-id="4adeb-129">문자열</span><span class="sxs-lookup"><span data-stu-id="4adeb-129">string</span></span> | <span data-ttu-id="4adeb-130">계정의 사용자 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4adeb-130">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="4adeb-131">문자열</span><span class="sxs-lookup"><span data-stu-id="4adeb-131">string</span></span> | <span data-ttu-id="4adeb-132">계정의 도메인</span><span class="sxs-lookup"><span data-stu-id="4adeb-132">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="4adeb-133">문자열</span><span class="sxs-lookup"><span data-stu-id="4adeb-133">string</span></span> | <span data-ttu-id="4adeb-134">계정의 UPN (사용자 계정 이름)</span><span class="sxs-lookup"><span data-stu-id="4adeb-134">User principal name (UPN) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="4adeb-135">문자열</span><span class="sxs-lookup"><span data-stu-id="4adeb-135">string</span></span> | <span data-ttu-id="4adeb-136">Azure AD의 계정에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="4adeb-136">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="4adeb-137">문자열</span><span class="sxs-lookup"><span data-stu-id="4adeb-137">string</span></span> | <span data-ttu-id="4adeb-138">주소록에 표시 되는 계정 사용자의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4adeb-138">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="4adeb-139">일반적으로 주어진 이름이 나 이름, 중간 시작, 성 또는 성의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="4adeb-139">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="4adeb-140">문자열</span><span class="sxs-lookup"><span data-stu-id="4adeb-140">string</span></span> | <span data-ttu-id="4adeb-141">장치의 FQDN (정규화 된 도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="4adeb-141">Fully qualified domain name (FQDN) of the device</span></span> |
| `DeviceType` | <span data-ttu-id="4adeb-142">문자열</span><span class="sxs-lookup"><span data-stu-id="4adeb-142">string</span></span> | <span data-ttu-id="4adeb-143">장치 유형</span><span class="sxs-lookup"><span data-stu-id="4adeb-143">Type of device</span></span> | 
| `OSPlatform` | <span data-ttu-id="4adeb-144">문자열</span><span class="sxs-lookup"><span data-stu-id="4adeb-144">string</span></span> | <span data-ttu-id="4adeb-145">장치에서 실행 되는 운영 체제의 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="4adeb-145">Platform of the operating system running on the device.</span></span> <span data-ttu-id="4adeb-146">이는 Windows 10 및 Windows 7과 같이 동일한 제품군 내의 변형을 포함하여 특정 운영 체제를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4adeb-146">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="4adeb-147">문자열</span><span class="sxs-lookup"><span data-stu-id="4adeb-147">string</span></span> | <span data-ttu-id="4adeb-148">끝점에 할당 되 고 관련 네트워크 통신 중에 사용 되는 IP 주소</span><span class="sxs-lookup"><span data-stu-id="4adeb-148">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="4adeb-149">문자열</span><span class="sxs-lookup"><span data-stu-id="4adeb-149">string</span></span> | <span data-ttu-id="4adeb-150">기록 된 작업을 처리 한 서버 응용 프로그램을 실행 하는 장치의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4adeb-150">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="4adeb-151">문자열</span><span class="sxs-lookup"><span data-stu-id="4adeb-151">string</span></span> | <span data-ttu-id="4adeb-152">기록 된 작업을 처리 한 서버 응용 프로그램을 실행 하는 장치의 IP 주소</span><span class="sxs-lookup"><span data-stu-id="4adeb-152">IP address of the device running the server application that processed the recorded action</span></span> |
| `Location` | <span data-ttu-id="4adeb-153">문자열</span><span class="sxs-lookup"><span data-stu-id="4adeb-153">string</span></span> | <span data-ttu-id="4adeb-154">이벤트와 관련 된 구/군/시, 국가 또는 기타 지리적 위치</span><span class="sxs-lookup"><span data-stu-id="4adeb-154">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="4adeb-155">문자열</span><span class="sxs-lookup"><span data-stu-id="4adeb-155">string</span></span> | <span data-ttu-id="4adeb-156">끝점 IP 주소와 연결 된 ISP (인터넷 서비스 공급자)</span><span class="sxs-lookup"><span data-stu-id="4adeb-156">Internet service provider (ISP) associated with the endpoint IP address</span></span> |
| `ReportId` | <span data-ttu-id="4adeb-157">long</span><span class="sxs-lookup"><span data-stu-id="4adeb-157">long</span></span> | <span data-ttu-id="4adeb-158">이벤트에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="4adeb-158">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="4adeb-159">문자열</span><span class="sxs-lookup"><span data-stu-id="4adeb-159">string</span></span> | <span data-ttu-id="4adeb-160">엔터티 또는 이벤트에 대 한 추가 정보</span><span class="sxs-lookup"><span data-stu-id="4adeb-160">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="4adeb-161">관련 항목</span><span class="sxs-lookup"><span data-stu-id="4adeb-161">Related topics</span></span>
- [<span data-ttu-id="4adeb-162">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="4adeb-162">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="4adeb-163">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="4adeb-163">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="4adeb-164">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="4adeb-164">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="4adeb-165">여러 장치 및 전자 메일에서 위협을 탐지</span><span class="sxs-lookup"><span data-stu-id="4adeb-165">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="4adeb-166">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="4adeb-166">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="4adeb-167">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="4adeb-167">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
