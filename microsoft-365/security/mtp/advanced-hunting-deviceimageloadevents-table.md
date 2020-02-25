---
title: 고급 구하기 스키마의 DeviceImageLoadEvents 테이블
description: 고급 구하기 스키마의 DeviceImageLoadEvents 테이블에 있는 DLL 로드 이벤트에 대해 자세히 알아보기
keywords: 고급 구하기, 위협 검색, 사이버 위협 사냥, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 스키마 참조, kusto, table, column, data type, description, imageloadevents, DeviceImageLoadEvents, DLL 로드, 라이브러리, 파일 이미지
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
ms.openlocfilehash: e3f51cfbe19a7b487f7382f0d2534b4a5efaab95
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42235057"
---
# <a name="deviceimageloadevents"></a><span data-ttu-id="c0262-104">DeviceImageLoadEvents</span><span class="sxs-lookup"><span data-stu-id="c0262-104">DeviceImageLoadEvents</span></span>

<span data-ttu-id="c0262-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="c0262-105">**Applies to:**</span></span>
- <span data-ttu-id="c0262-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="c0262-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="c0262-107">`DeviceImageLoadEvents` [고급 구하기](advanced-hunting-overview.md) 스키마의 표에는 DLL 로드 이벤트에 대 한 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0262-107">The `DeviceImageLoadEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about DLL loading events.</span></span> <span data-ttu-id="c0262-108">이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c0262-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="c0262-109">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c0262-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="c0262-110">열 이름</span><span class="sxs-lookup"><span data-stu-id="c0262-110">Column name</span></span> | <span data-ttu-id="c0262-111">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c0262-111">Data type</span></span> | <span data-ttu-id="c0262-112">설명</span><span class="sxs-lookup"><span data-stu-id="c0262-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="c0262-113">datetime</span><span class="sxs-lookup"><span data-stu-id="c0262-113">datetime</span></span> | <span data-ttu-id="c0262-114">이벤트가 기록된 날짜와 시간</span><span class="sxs-lookup"><span data-stu-id="c0262-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="c0262-115">문자열</span><span class="sxs-lookup"><span data-stu-id="c0262-115">string</span></span> | <span data-ttu-id="c0262-116">서비스에서 시스템의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="c0262-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="c0262-117">문자열</span><span class="sxs-lookup"><span data-stu-id="c0262-117">string</span></span> | <span data-ttu-id="c0262-118">컴퓨터의 FQDN(정규화된 도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="c0262-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ActionType` | <span data-ttu-id="c0262-119">문자열</span><span class="sxs-lookup"><span data-stu-id="c0262-119">string</span></span> | <span data-ttu-id="c0262-120">이벤트를 트리거한 작업의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="c0262-120">Type of activity that triggered the event</span></span> |
| `FileName` | <span data-ttu-id="c0262-121">문자열</span><span class="sxs-lookup"><span data-stu-id="c0262-121">string</span></span> | <span data-ttu-id="c0262-122">기록된 조치가 적용된 파일의 이름</span><span class="sxs-lookup"><span data-stu-id="c0262-122">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="c0262-123">문자열</span><span class="sxs-lookup"><span data-stu-id="c0262-123">string</span></span> | <span data-ttu-id="c0262-124">기록 된 작업이 적용 된 파일을 포함 하는 폴더</span><span class="sxs-lookup"><span data-stu-id="c0262-124">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="c0262-125">문자열</span><span class="sxs-lookup"><span data-stu-id="c0262-125">string</span></span> | <span data-ttu-id="c0262-126">기록된 조치가 적용된 파일의 SHA-1</span><span class="sxs-lookup"><span data-stu-id="c0262-126">SHA-1 of the file that the recorded action was applied to</span></span> |
| `MD5` | <span data-ttu-id="c0262-127">문자열</span><span class="sxs-lookup"><span data-stu-id="c0262-127">string</span></span> | <span data-ttu-id="c0262-128">기록 된 작업이 적용 된 파일의 MD5 해시</span><span class="sxs-lookup"><span data-stu-id="c0262-128">MD5 hash of the file that the recorded action was applied to</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="c0262-129">문자열</span><span class="sxs-lookup"><span data-stu-id="c0262-129">string</span></span> | <span data-ttu-id="c0262-130">이벤트를 담당 하는 프로세스를 실행 한 계정의 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="c0262-130">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="c0262-131">문자열</span><span class="sxs-lookup"><span data-stu-id="c0262-131">string</span></span> | <span data-ttu-id="c0262-132">이벤트를 담당 하는 프로세스를 실행 한 계정의 사용자 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c0262-132">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="c0262-133">문자열</span><span class="sxs-lookup"><span data-stu-id="c0262-133">string</span></span> | <span data-ttu-id="c0262-134">이벤트를 담당 하는 프로세스를 실행 한 계정의 SID (보안 식별자)입니다.</span><span class="sxs-lookup"><span data-stu-id="c0262-134">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="c0262-135">문자열</span><span class="sxs-lookup"><span data-stu-id="c0262-135">string</span></span> | <span data-ttu-id="c0262-136">이벤트를 시작한 프로세스의 무결성 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="c0262-136">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="c0262-137">Windows에서는 인터넷 다운로드에서 시작 된 경우와 같이 특정 특성에 따라 프로세스에 무결성 수준을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0262-137">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="c0262-138">이러한 무결성 수준은 리소스에 대 한 사용 권한에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c0262-138">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="c0262-139">문자열</span><span class="sxs-lookup"><span data-stu-id="c0262-139">string</span></span> | <span data-ttu-id="c0262-140">이벤트를 시작한 프로세스에 UAC (사용자 액세스 제어) 권한 상승이 적용 되었는지 여부를 나타내는 토큰 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="c0262-140">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="c0262-141">문자열</span><span class="sxs-lookup"><span data-stu-id="c0262-141">string</span></span> | <span data-ttu-id="c0262-142">이벤트를 시작한 프로세스 (이미지 파일)의 SHA-1</span><span class="sxs-lookup"><span data-stu-id="c0262-142">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="c0262-143">문자열</span><span class="sxs-lookup"><span data-stu-id="c0262-143">string</span></span> | <span data-ttu-id="c0262-144">이벤트를 시작한 프로세스 (이미지 파일)의 MD5 해시</span><span class="sxs-lookup"><span data-stu-id="c0262-144">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="c0262-145">문자열</span><span class="sxs-lookup"><span data-stu-id="c0262-145">string</span></span> | <span data-ttu-id="c0262-146">이벤트를 시작한 프로세스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c0262-146">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="c0262-147">int</span><span class="sxs-lookup"><span data-stu-id="c0262-147">int</span></span> | <span data-ttu-id="c0262-148">이벤트를 시작한 프로세스의 PID (프로세스 ID)</span><span class="sxs-lookup"><span data-stu-id="c0262-148">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="c0262-149">문자열</span><span class="sxs-lookup"><span data-stu-id="c0262-149">string</span></span> | <span data-ttu-id="c0262-150">이벤트를 시작한 프로세스를 실행 하는 데 사용 되는 명령줄입니다.</span><span class="sxs-lookup"><span data-stu-id="c0262-150">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="c0262-151">datetime</span><span class="sxs-lookup"><span data-stu-id="c0262-151">datetime</span></span> | <span data-ttu-id="c0262-152">이벤트를 시작한 프로세스를 시작한 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="c0262-152">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="c0262-153">문자열</span><span class="sxs-lookup"><span data-stu-id="c0262-153">string</span></span> | <span data-ttu-id="c0262-154">이벤트를 시작한 프로세스 (이미지 파일)가 들어 있는 폴더</span><span class="sxs-lookup"><span data-stu-id="c0262-154">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="c0262-155">int</span><span class="sxs-lookup"><span data-stu-id="c0262-155">int</span></span> | <span data-ttu-id="c0262-156">이벤트를 담당 하는 프로세스를 생성 한 상위 프로세스의 PID (프로세스 ID)입니다.</span><span class="sxs-lookup"><span data-stu-id="c0262-156">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="c0262-157">문자열</span><span class="sxs-lookup"><span data-stu-id="c0262-157">string</span></span> | <span data-ttu-id="c0262-158">이벤트를 담당 하는 프로세스를 생성 한 상위 프로세스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c0262-158">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="c0262-159">datetime</span><span class="sxs-lookup"><span data-stu-id="c0262-159">datetime</span></span> | <span data-ttu-id="c0262-160">이벤트를 담당 하는 프로세스의 부모를 시작한 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="c0262-160">Date and time when the parent of the process responsible for the event was started</span></span> |
| `ReportId` | <span data-ttu-id="c0262-161">long</span><span class="sxs-lookup"><span data-stu-id="c0262-161">long</span></span> | <span data-ttu-id="c0262-162">반복 카운터를 기반으로 하는 이벤트 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="c0262-162">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="c0262-163">고유 이벤트를 식별 하려면이 열을 장치 이름 및 타임 스탬프 열과 함께 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0262-163">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="c0262-164">문자열</span><span class="sxs-lookup"><span data-stu-id="c0262-164">string</span></span> | <span data-ttu-id="c0262-165">응용 프로그램 가드가 브라우저 활동을 격리 하는 데 사용 하는 가상화 된 컨테이너의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="c0262-165">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="c0262-166">관련 항목</span><span class="sxs-lookup"><span data-stu-id="c0262-166">Related topics</span></span>
- [<span data-ttu-id="c0262-167">사전 대응식 위협 탐지</span><span class="sxs-lookup"><span data-stu-id="c0262-167">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c0262-168">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="c0262-168">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c0262-169">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="c0262-169">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="c0262-170">여러 장치 및 전자 메일에서 위협을 탐지</span><span class="sxs-lookup"><span data-stu-id="c0262-170">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="c0262-171">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="c0262-171">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="c0262-172">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="c0262-172">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
