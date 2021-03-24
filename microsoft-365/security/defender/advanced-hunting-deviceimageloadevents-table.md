---
title: 고급 헌팅chema의 DeviceImageLoadEvents 테이블
description: 고급 헌팅 스위마의 DeviceImageLoadEvents 테이블에서 DLL 로딩 이벤트에 대해 자세히 알아보시고
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: c2cc0fe7746c7574b427e3f546050ab4756fb525
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071567"
---
# <a name="deviceimageloadevents"></a><span data-ttu-id="5c555-104">DeviceImageLoadEvents</span><span class="sxs-lookup"><span data-stu-id="5c555-104">DeviceImageLoadEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="5c555-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="5c555-105">**Applies to:**</span></span>
- <span data-ttu-id="5c555-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5c555-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="5c555-107">고급 `DeviceImageLoadEvents` 헌팅 [일정의](advanced-hunting-overview.md) 표에는 DLL 로드 이벤트에 대한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c555-107">The `DeviceImageLoadEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about DLL loading events.</span></span> <span data-ttu-id="5c555-108">이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="5c555-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="5c555-109">테이블에서 지원하는 이벤트 유형(값)에 대한 자세한 내용은 보안 센터에서 사용할 수 있는 기본 제공 `ActionType` Schema 참조를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5c555-109">For detailed information about the events types (`ActionType` values) supported by a table, use the built-in schema reference available in the security center.</span></span>

<span data-ttu-id="5c555-110">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5c555-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="5c555-111">열 이름</span><span class="sxs-lookup"><span data-stu-id="5c555-111">Column name</span></span> | <span data-ttu-id="5c555-112">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="5c555-112">Data type</span></span> | <span data-ttu-id="5c555-113">설명</span><span class="sxs-lookup"><span data-stu-id="5c555-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="5c555-114">datetime</span><span class="sxs-lookup"><span data-stu-id="5c555-114">datetime</span></span> | <span data-ttu-id="5c555-115">이벤트가 기록된 날짜와 시간</span><span class="sxs-lookup"><span data-stu-id="5c555-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="5c555-116">문자열</span><span class="sxs-lookup"><span data-stu-id="5c555-116">string</span></span> | <span data-ttu-id="5c555-117">서비스에서 시스템의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="5c555-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="5c555-118">문자열</span><span class="sxs-lookup"><span data-stu-id="5c555-118">string</span></span> | <span data-ttu-id="5c555-119">컴퓨터의 FQDN(정규화된 도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="5c555-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ActionType` | <span data-ttu-id="5c555-120">문자열</span><span class="sxs-lookup"><span data-stu-id="5c555-120">string</span></span> | <span data-ttu-id="5c555-121">이벤트를 트리거한 활동의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="5c555-121">Type of activity that triggered the event.</span></span> <span data-ttu-id="5c555-122">자세한 내용은 포털 내 [Schema 참조를](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="5c555-122">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `FileName` | <span data-ttu-id="5c555-123">문자열</span><span class="sxs-lookup"><span data-stu-id="5c555-123">string</span></span> | <span data-ttu-id="5c555-124">기록된 조치가 적용된 파일의 이름</span><span class="sxs-lookup"><span data-stu-id="5c555-124">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="5c555-125">문자열</span><span class="sxs-lookup"><span data-stu-id="5c555-125">string</span></span> | <span data-ttu-id="5c555-126">기록된 작업이 적용된 파일이 들어 있는 폴더</span><span class="sxs-lookup"><span data-stu-id="5c555-126">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="5c555-127">문자열</span><span class="sxs-lookup"><span data-stu-id="5c555-127">string</span></span> | <span data-ttu-id="5c555-128">기록된 조치가 적용된 파일의 SHA-1</span><span class="sxs-lookup"><span data-stu-id="5c555-128">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="5c555-129">문자열</span><span class="sxs-lookup"><span data-stu-id="5c555-129">string</span></span> | <span data-ttu-id="5c555-130">기록된 조치가 적용된 파일의 SHA-256</span><span class="sxs-lookup"><span data-stu-id="5c555-130">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="5c555-131">일반적으로이 필드는 채워지지 않습니다. 가능한 경우 SHA1 열을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5c555-131">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `MD5` | <span data-ttu-id="5c555-132">문자열</span><span class="sxs-lookup"><span data-stu-id="5c555-132">string</span></span> | <span data-ttu-id="5c555-133">기록된 작업이 적용된 파일의 MD5 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="5c555-133">MD5 hash of the file that the recorded action was applied to</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="5c555-134">문자열</span><span class="sxs-lookup"><span data-stu-id="5c555-134">string</span></span> | <span data-ttu-id="5c555-135">이벤트를 담당하는 프로세스를 시작한 계정의 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="5c555-135">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="5c555-136">문자열</span><span class="sxs-lookup"><span data-stu-id="5c555-136">string</span></span> | <span data-ttu-id="5c555-137">이벤트를 담당하는 프로세스를 시작한 계정의 사용자 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5c555-137">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="5c555-138">문자열</span><span class="sxs-lookup"><span data-stu-id="5c555-138">string</span></span> | <span data-ttu-id="5c555-139">이벤트를 담당하는 프로세스를 시작한 계정의 SID(보안 식별자)입니다.</span><span class="sxs-lookup"><span data-stu-id="5c555-139">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountUpn` | <span data-ttu-id="5c555-140">문자열</span><span class="sxs-lookup"><span data-stu-id="5c555-140">string</span></span> | <span data-ttu-id="5c555-141">이벤트를 담당하는 프로세스를 시작한 계정의 UPN(사용자 계정 이름)입니다.</span><span class="sxs-lookup"><span data-stu-id="5c555-141">User principal name (UPN) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountObjectId` | <span data-ttu-id="5c555-142">문자열</span><span class="sxs-lookup"><span data-stu-id="5c555-142">string</span></span> | <span data-ttu-id="5c555-143">이벤트를 담당하는 프로세스를 시작한 사용자 계정의 Azure AD 개체 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5c555-143">Azure AD object ID of the user account that ran the process responsible for the event</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="5c555-144">문자열</span><span class="sxs-lookup"><span data-stu-id="5c555-144">string</span></span> | <span data-ttu-id="5c555-145">이벤트를 시작한 프로세스의 무결성 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="5c555-145">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="5c555-146">Windows는 인터넷 다운로드에서 시작된 경우와 같이 특정 특성을 기반으로 프로세스에 무결성 수준을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="5c555-146">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="5c555-147">이러한 무결성 수준은 리소스에 대한 사용 권한에 영향을 미치기</span><span class="sxs-lookup"><span data-stu-id="5c555-147">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="5c555-148">문자열</span><span class="sxs-lookup"><span data-stu-id="5c555-148">string</span></span> | <span data-ttu-id="5c555-149">이벤트를 시작한 프로세스에 적용되는 UAC(사용자 액세스 제어) 권한 상승의 유무를 나타내는 토큰 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5c555-149">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="5c555-150">문자열</span><span class="sxs-lookup"><span data-stu-id="5c555-150">string</span></span> | <span data-ttu-id="5c555-151">이벤트를 시작한 프로세스(이미지 파일)의 SHA-1</span><span class="sxs-lookup"><span data-stu-id="5c555-151">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessSHA256` | <span data-ttu-id="5c555-152">문자열</span><span class="sxs-lookup"><span data-stu-id="5c555-152">string</span></span> | <span data-ttu-id="5c555-153">이벤트를 시작한 프로세스(이미지 파일)의 SHA-256입니다.</span><span class="sxs-lookup"><span data-stu-id="5c555-153">SHA-256 of the process (image file) that initiated the event.</span></span> <span data-ttu-id="5c555-154">일반적으로이 필드는 채워지지 않습니다. 가능한 경우 SHA1 열을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5c555-154">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="5c555-155">문자열</span><span class="sxs-lookup"><span data-stu-id="5c555-155">string</span></span> | <span data-ttu-id="5c555-156">이벤트를 시작한 프로세스(이미지 파일)의 MD5 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="5c555-156">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="5c555-157">문자열</span><span class="sxs-lookup"><span data-stu-id="5c555-157">string</span></span> | <span data-ttu-id="5c555-158">이벤트를 시작한 프로세스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5c555-158">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="5c555-159">int</span><span class="sxs-lookup"><span data-stu-id="5c555-159">int</span></span> | <span data-ttu-id="5c555-160">이벤트를 시작한 프로세스의 PID(프로세스 ID)입니다.</span><span class="sxs-lookup"><span data-stu-id="5c555-160">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="5c555-161">문자열</span><span class="sxs-lookup"><span data-stu-id="5c555-161">string</span></span> | <span data-ttu-id="5c555-162">이벤트를 시작한 프로세스를 실행하는 데 사용되는 명령줄</span><span class="sxs-lookup"><span data-stu-id="5c555-162">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="5c555-163">datetime</span><span class="sxs-lookup"><span data-stu-id="5c555-163">datetime</span></span> | <span data-ttu-id="5c555-164">이벤트를 시작한 프로세스가 시작된 날짜 및 시간</span><span class="sxs-lookup"><span data-stu-id="5c555-164">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="5c555-165">문자열</span><span class="sxs-lookup"><span data-stu-id="5c555-165">string</span></span> | <span data-ttu-id="5c555-166">이벤트를 시작한 프로세스(이미지 파일)가 포함된 폴더</span><span class="sxs-lookup"><span data-stu-id="5c555-166">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="5c555-167">int</span><span class="sxs-lookup"><span data-stu-id="5c555-167">int</span></span> | <span data-ttu-id="5c555-168">이벤트를 담당하는 프로세스를 시작한 상위 프로세스의 PID(프로세스 ID)입니다.</span><span class="sxs-lookup"><span data-stu-id="5c555-168">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="5c555-169">문자열</span><span class="sxs-lookup"><span data-stu-id="5c555-169">string</span></span> | <span data-ttu-id="5c555-170">이벤트를 담당하는 프로세스를 시작한 상위 프로세스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5c555-170">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="5c555-171">datetime</span><span class="sxs-lookup"><span data-stu-id="5c555-171">datetime</span></span> | <span data-ttu-id="5c555-172">이벤트를 담당하는 프로세스의 부모가 시작된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="5c555-172">Date and time when the parent of the process responsible for the event was started</span></span> |
| `ReportId` | <span data-ttu-id="5c555-173">long</span><span class="sxs-lookup"><span data-stu-id="5c555-173">long</span></span> | <span data-ttu-id="5c555-174">반복 카운터를 기반으로 하는 이벤트 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="5c555-174">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="5c555-175">고유한 이벤트를 식별하려면 이 열을 DeviceName 및 Timestamp 열과 함께 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c555-175">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="5c555-176">문자열</span><span class="sxs-lookup"><span data-stu-id="5c555-176">string</span></span> | <span data-ttu-id="5c555-177">Application Guard에서 브라우저 활동을 격리하기 위해 사용하는 가상화된 컨테이너의 식별자</span><span class="sxs-lookup"><span data-stu-id="5c555-177">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |
| `InitiatingProcessFileSize` | <span data-ttu-id="5c555-178">long</span><span class="sxs-lookup"><span data-stu-id="5c555-178">long</span></span> | <span data-ttu-id="5c555-179">이벤트를 담당하는 프로세스를 시작한 파일의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="5c555-179">Size of the file that ran the process responsible for the event</span></span> |
| `FileSize` | <span data-ttu-id="5c555-180">long</span><span class="sxs-lookup"><span data-stu-id="5c555-180">long</span></span> | <span data-ttu-id="5c555-181">파일 크기(bytes)입니다.</span><span class="sxs-lookup"><span data-stu-id="5c555-181">Size of the file in bytes</span></span> |

## <a name="related-topics"></a><span data-ttu-id="5c555-182">관련 항목</span><span class="sxs-lookup"><span data-stu-id="5c555-182">Related topics</span></span>
- [<span data-ttu-id="5c555-183">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="5c555-183">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="5c555-184">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="5c555-184">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="5c555-185">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="5c555-185">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="5c555-186">장치, 전자 메일, 앱 및 ID를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="5c555-186">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="5c555-187">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="5c555-187">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="5c555-188">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="5c555-188">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
