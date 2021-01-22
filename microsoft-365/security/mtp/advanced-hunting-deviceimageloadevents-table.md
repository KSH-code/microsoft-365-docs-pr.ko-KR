---
title: 고급 헌팅chema의 DeviceImageLoadEvents 테이블
description: 고급 헌팅 schema의 DeviceImageLoadEvents 표에서 DLL 로드 이벤트에 대해 자세히
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 위협 방지, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, schema reference, kusto, table, column, data type, description, imageloadevents, DeviceImageLoadEvents, DLL loading, library, file image
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
ms.openlocfilehash: 924d465d90086bcfffe29660b7f281ff3d5b07aa
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931293"
---
# <a name="deviceimageloadevents"></a><span data-ttu-id="649d0-104">DeviceImageLoadEvents</span><span class="sxs-lookup"><span data-stu-id="649d0-104">DeviceImageLoadEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="649d0-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="649d0-105">**Applies to:**</span></span>
- <span data-ttu-id="649d0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="649d0-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="649d0-107">고급 `DeviceImageLoadEvents` [헌팅계의](advanced-hunting-overview.md) 표에는 DLL 로드 이벤트에 대한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="649d0-107">The `DeviceImageLoadEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about DLL loading events.</span></span> <span data-ttu-id="649d0-108">이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="649d0-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="649d0-109">테이블에서 지원하는 이벤트 유형(값)에 대한 자세한 내용은 보안 센터에서 사용할 수 있는 기본 제공 `ActionType` [Schema 참조를](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="649d0-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="649d0-110">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="649d0-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="649d0-111">열 이름</span><span class="sxs-lookup"><span data-stu-id="649d0-111">Column name</span></span> | <span data-ttu-id="649d0-112">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="649d0-112">Data type</span></span> | <span data-ttu-id="649d0-113">설명</span><span class="sxs-lookup"><span data-stu-id="649d0-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="649d0-114">datetime</span><span class="sxs-lookup"><span data-stu-id="649d0-114">datetime</span></span> | <span data-ttu-id="649d0-115">이벤트가 기록된 날짜와 시간</span><span class="sxs-lookup"><span data-stu-id="649d0-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="649d0-116">문자열</span><span class="sxs-lookup"><span data-stu-id="649d0-116">string</span></span> | <span data-ttu-id="649d0-117">서비스에서 시스템의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="649d0-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="649d0-118">문자열</span><span class="sxs-lookup"><span data-stu-id="649d0-118">string</span></span> | <span data-ttu-id="649d0-119">컴퓨터의 FQDN(정규화된 도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="649d0-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ActionType` | <span data-ttu-id="649d0-120">문자열</span><span class="sxs-lookup"><span data-stu-id="649d0-120">string</span></span> | <span data-ttu-id="649d0-121">이벤트를 트리거한 활동의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="649d0-121">Type of activity that triggered the event.</span></span> <span data-ttu-id="649d0-122">자세한 내용은 포털 [내 Schema 참조를](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="649d0-122">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `FileName` | <span data-ttu-id="649d0-123">문자열</span><span class="sxs-lookup"><span data-stu-id="649d0-123">string</span></span> | <span data-ttu-id="649d0-124">기록된 조치가 적용된 파일의 이름</span><span class="sxs-lookup"><span data-stu-id="649d0-124">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="649d0-125">문자열</span><span class="sxs-lookup"><span data-stu-id="649d0-125">string</span></span> | <span data-ttu-id="649d0-126">기록된 작업이 적용된 파일이 들어 있는 폴더</span><span class="sxs-lookup"><span data-stu-id="649d0-126">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="649d0-127">문자열</span><span class="sxs-lookup"><span data-stu-id="649d0-127">string</span></span> | <span data-ttu-id="649d0-128">기록된 조치가 적용된 파일의 SHA-1</span><span class="sxs-lookup"><span data-stu-id="649d0-128">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="649d0-129">문자열</span><span class="sxs-lookup"><span data-stu-id="649d0-129">string</span></span> | <span data-ttu-id="649d0-130">기록된 조치가 적용된 파일의 SHA-256</span><span class="sxs-lookup"><span data-stu-id="649d0-130">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="649d0-131">일반적으로이 필드는 채워지지 않습니다. 가능한 경우 SHA1 열을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="649d0-131">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `MD5` | <span data-ttu-id="649d0-132">문자열</span><span class="sxs-lookup"><span data-stu-id="649d0-132">string</span></span> | <span data-ttu-id="649d0-133">기록된 작업이 적용된 파일의 MD5 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="649d0-133">MD5 hash of the file that the recorded action was applied to</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="649d0-134">문자열</span><span class="sxs-lookup"><span data-stu-id="649d0-134">string</span></span> | <span data-ttu-id="649d0-135">이벤트를 담당하는 프로세스를 시작한 계정의 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="649d0-135">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="649d0-136">문자열</span><span class="sxs-lookup"><span data-stu-id="649d0-136">string</span></span> | <span data-ttu-id="649d0-137">이벤트를 담당하는 프로세스를 시작한 계정의 사용자 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="649d0-137">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="649d0-138">문자열</span><span class="sxs-lookup"><span data-stu-id="649d0-138">string</span></span> | <span data-ttu-id="649d0-139">이벤트를 담당하는 프로세스를 시작한 계정의 SID(보안 식별자)입니다.</span><span class="sxs-lookup"><span data-stu-id="649d0-139">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="649d0-140">문자열</span><span class="sxs-lookup"><span data-stu-id="649d0-140">string</span></span> | <span data-ttu-id="649d0-141">이벤트를 시작한 프로세스의 무결성 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="649d0-141">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="649d0-142">Windows는 인터넷 다운로드에서 시작된 경우와 같은 특정 특성을 기반으로 프로세스에 무결성 수준을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="649d0-142">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="649d0-143">이러한 무결성 수준은 리소스에 대한 사용 권한에 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="649d0-143">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="649d0-144">문자열</span><span class="sxs-lookup"><span data-stu-id="649d0-144">string</span></span> | <span data-ttu-id="649d0-145">이벤트를 시작한 프로세스에 적용된 UAC(사용자 액세스 제어) 권한 상승의 유무를 나타내는 토큰 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="649d0-145">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="649d0-146">문자열</span><span class="sxs-lookup"><span data-stu-id="649d0-146">string</span></span> | <span data-ttu-id="649d0-147">이벤트를 시작한 프로세스의 SHA-1(이미지 파일)</span><span class="sxs-lookup"><span data-stu-id="649d0-147">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessSHA256` | <span data-ttu-id="649d0-148">문자열</span><span class="sxs-lookup"><span data-stu-id="649d0-148">string</span></span> | <span data-ttu-id="649d0-149">이벤트를 시작한 프로세스(이미지 파일)의 SHA-256입니다.</span><span class="sxs-lookup"><span data-stu-id="649d0-149">SHA-256 of the process (image file) that initiated the event.</span></span> <span data-ttu-id="649d0-150">일반적으로이 필드는 채워지지 않습니다. 가능한 경우 SHA1 열을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="649d0-150">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="649d0-151">문자열</span><span class="sxs-lookup"><span data-stu-id="649d0-151">string</span></span> | <span data-ttu-id="649d0-152">이벤트를 시작한 프로세스의 MD5 해시(이미지 파일)</span><span class="sxs-lookup"><span data-stu-id="649d0-152">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="649d0-153">문자열</span><span class="sxs-lookup"><span data-stu-id="649d0-153">string</span></span> | <span data-ttu-id="649d0-154">이벤트를 시작한 프로세스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="649d0-154">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="649d0-155">int</span><span class="sxs-lookup"><span data-stu-id="649d0-155">int</span></span> | <span data-ttu-id="649d0-156">이벤트를 시작한 프로세스의 PID(프로세스 ID)입니다.</span><span class="sxs-lookup"><span data-stu-id="649d0-156">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="649d0-157">문자열</span><span class="sxs-lookup"><span data-stu-id="649d0-157">string</span></span> | <span data-ttu-id="649d0-158">이벤트를 시작한 프로세스를 실행하는 데 사용되는 명령줄</span><span class="sxs-lookup"><span data-stu-id="649d0-158">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="649d0-159">datetime</span><span class="sxs-lookup"><span data-stu-id="649d0-159">datetime</span></span> | <span data-ttu-id="649d0-160">이벤트를 시작한 프로세스가 시작된 날짜 및 시간</span><span class="sxs-lookup"><span data-stu-id="649d0-160">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="649d0-161">문자열</span><span class="sxs-lookup"><span data-stu-id="649d0-161">string</span></span> | <span data-ttu-id="649d0-162">이벤트를 시작한 프로세스(이미지 파일)가 들어 있는 폴더</span><span class="sxs-lookup"><span data-stu-id="649d0-162">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="649d0-163">int</span><span class="sxs-lookup"><span data-stu-id="649d0-163">int</span></span> | <span data-ttu-id="649d0-164">이벤트를 담당하는 프로세스를 시작한 상위 프로세스의 PID(프로세스 ID)입니다.</span><span class="sxs-lookup"><span data-stu-id="649d0-164">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="649d0-165">문자열</span><span class="sxs-lookup"><span data-stu-id="649d0-165">string</span></span> | <span data-ttu-id="649d0-166">이벤트를 담당하는 프로세스를 시작한 상위 프로세스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="649d0-166">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="649d0-167">datetime</span><span class="sxs-lookup"><span data-stu-id="649d0-167">datetime</span></span> | <span data-ttu-id="649d0-168">이벤트를 담당하는 프로세스의 부모가 시작된 날짜 및 시간</span><span class="sxs-lookup"><span data-stu-id="649d0-168">Date and time when the parent of the process responsible for the event was started</span></span> |
| `ReportId` | <span data-ttu-id="649d0-169">long</span><span class="sxs-lookup"><span data-stu-id="649d0-169">long</span></span> | <span data-ttu-id="649d0-170">반복 카운터를 기반으로 하는 이벤트 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="649d0-170">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="649d0-171">고유한 이벤트를 식별하려면 이 열을 DeviceName 및 타임스탬프 열과 함께 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="649d0-171">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="649d0-172">문자열</span><span class="sxs-lookup"><span data-stu-id="649d0-172">string</span></span> | <span data-ttu-id="649d0-173">Application Guard에서 브라우저 활동을 격리하기 위해 사용하는 가상화된 컨테이너의 식별자</span><span class="sxs-lookup"><span data-stu-id="649d0-173">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="649d0-174">관련 항목</span><span class="sxs-lookup"><span data-stu-id="649d0-174">Related topics</span></span>
- [<span data-ttu-id="649d0-175">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="649d0-175">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="649d0-176">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="649d0-176">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="649d0-177">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="649d0-177">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="649d0-178">장치, 전자 메일, 앱 및 ID를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="649d0-178">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="649d0-179">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="649d0-179">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="649d0-180">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="649d0-180">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
