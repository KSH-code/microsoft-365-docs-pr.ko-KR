---
title: 고급 헌팅chema의 DeviceRegistryEvents 테이블
description: 고급 헌팅 키의 DeviceRegistryEvents 테이블에서 쿼리할 수 있는 레지스트리 이벤트에 대해 자세히
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 위협 방지, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, schema reference, kusto, table, column, data type, registryevents, registry, registry, DeviceRegistryEvents, key, subkey, value
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
ms.openlocfilehash: 376e54fb4bf5f07a1c821ff436ddc8ec7dd25812
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931113"
---
# <a name="deviceregistryevents"></a><span data-ttu-id="e05b7-104">DeviceRegistryEvents</span><span class="sxs-lookup"><span data-stu-id="e05b7-104">DeviceRegistryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e05b7-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="e05b7-105">**Applies to:**</span></span>
- <span data-ttu-id="e05b7-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e05b7-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="e05b7-107">고급 `DeviceRegistryEvents` 헌팅 [키의](advanced-hunting-overview.md) 표에는 레지스트리 항목 생성 및 수정에 대한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e05b7-107">The `DeviceRegistryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about the creation and modification of registry entries.</span></span> <span data-ttu-id="e05b7-108">이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e05b7-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="e05b7-109">테이블에서 지원하는 이벤트 유형(값)에 대한 자세한 내용은 보안 센터에서 사용할 수 있는 기본 제공 `ActionType` [Schema 참조를](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e05b7-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="e05b7-110">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e05b7-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="e05b7-111">열 이름</span><span class="sxs-lookup"><span data-stu-id="e05b7-111">Column name</span></span> | <span data-ttu-id="e05b7-112">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="e05b7-112">Data type</span></span> | <span data-ttu-id="e05b7-113">설명</span><span class="sxs-lookup"><span data-stu-id="e05b7-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="e05b7-114">datetime</span><span class="sxs-lookup"><span data-stu-id="e05b7-114">datetime</span></span> | <span data-ttu-id="e05b7-115">이벤트가 기록된 날짜와 시간</span><span class="sxs-lookup"><span data-stu-id="e05b7-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="e05b7-116">문자열</span><span class="sxs-lookup"><span data-stu-id="e05b7-116">string</span></span> | <span data-ttu-id="e05b7-117">서비스에서 시스템의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="e05b7-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="e05b7-118">문자열</span><span class="sxs-lookup"><span data-stu-id="e05b7-118">string</span></span> | <span data-ttu-id="e05b7-119">컴퓨터의 FQDN(정규화된 도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="e05b7-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ActionType` | <span data-ttu-id="e05b7-120">문자열</span><span class="sxs-lookup"><span data-stu-id="e05b7-120">string</span></span> | <span data-ttu-id="e05b7-121">이벤트를 트리거한 활동의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="e05b7-121">Type of activity that triggered the event.</span></span> <span data-ttu-id="e05b7-122">자세한 내용은 포털 [내 Schema 참조를](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="e05b7-122">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `RegistryKey` | <span data-ttu-id="e05b7-123">문자열</span><span class="sxs-lookup"><span data-stu-id="e05b7-123">string</span></span> | <span data-ttu-id="e05b7-124">기록된 작업이 적용된 레지스트리 키</span><span class="sxs-lookup"><span data-stu-id="e05b7-124">Registry key that the recorded action was applied to</span></span> |
| `RegistryValueType` | <span data-ttu-id="e05b7-125">문자열</span><span class="sxs-lookup"><span data-stu-id="e05b7-125">string</span></span> | <span data-ttu-id="e05b7-126">기록된 작업이 적용된 레지스트리 값의 데이터 형식(예: 이진 또는 문자열)</span><span class="sxs-lookup"><span data-stu-id="e05b7-126">Data type, such as binary or string, of the registry value that the recorded action was applied to</span></span> |
| `RegistryValueName` | <span data-ttu-id="e05b7-127">문자열</span><span class="sxs-lookup"><span data-stu-id="e05b7-127">string</span></span> | <span data-ttu-id="e05b7-128">기록된 작업이 적용된 레지스트리 값의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e05b7-128">Name of the registry value that the recorded action was applied to</span></span> |
| `RegistryValueData` | <span data-ttu-id="e05b7-129">문자열</span><span class="sxs-lookup"><span data-stu-id="e05b7-129">string</span></span> | <span data-ttu-id="e05b7-130">기록된 작업이 적용된 레지스트리 값의 데이터</span><span class="sxs-lookup"><span data-stu-id="e05b7-130">Data of the registry value that the recorded action was applied to</span></span> |
| `PreviousRegistryValueName` | <span data-ttu-id="e05b7-131">문자열</span><span class="sxs-lookup"><span data-stu-id="e05b7-131">string</span></span> | <span data-ttu-id="e05b7-132">수정되기 전의 레지스트리 값의 원래 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e05b7-132">Original name of the registry value before it was modified</span></span> |
| `PreviousRegistryValueData` | <span data-ttu-id="e05b7-133">문자열</span><span class="sxs-lookup"><span data-stu-id="e05b7-133">string</span></span> | <span data-ttu-id="e05b7-134">레지스트리 값을 수정하기 전의 원래 데이터</span><span class="sxs-lookup"><span data-stu-id="e05b7-134">Original data of the registry value before it was modified</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="e05b7-135">문자열</span><span class="sxs-lookup"><span data-stu-id="e05b7-135">string</span></span> | <span data-ttu-id="e05b7-136">이벤트를 담당하는 프로세스를 시작한 계정의 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="e05b7-136">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="e05b7-137">문자열</span><span class="sxs-lookup"><span data-stu-id="e05b7-137">string</span></span> | <span data-ttu-id="e05b7-138">이벤트를 담당하는 프로세스를 시작한 계정의 사용자 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e05b7-138">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="e05b7-139">문자열</span><span class="sxs-lookup"><span data-stu-id="e05b7-139">string</span></span> | <span data-ttu-id="e05b7-140">이벤트를 담당하는 프로세스를 시작한 계정의 SID(보안 식별자)입니다.</span><span class="sxs-lookup"><span data-stu-id="e05b7-140">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="e05b7-141">문자열</span><span class="sxs-lookup"><span data-stu-id="e05b7-141">string</span></span> | <span data-ttu-id="e05b7-142">이벤트를 시작한 프로세스의 SHA-1(이미지 파일)</span><span class="sxs-lookup"><span data-stu-id="e05b7-142">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessSHA256` | <span data-ttu-id="e05b7-143">문자열</span><span class="sxs-lookup"><span data-stu-id="e05b7-143">string</span></span> | <span data-ttu-id="e05b7-144">이벤트를 시작한 프로세스(이미지 파일)의 SHA-256입니다.</span><span class="sxs-lookup"><span data-stu-id="e05b7-144">SHA-256 of the process (image file) that initiated the event.</span></span> <span data-ttu-id="e05b7-145">일반적으로이 필드는 채워지지 않습니다. 가능한 경우 SHA1 열을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e05b7-145">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="e05b7-146">문자열</span><span class="sxs-lookup"><span data-stu-id="e05b7-146">string</span></span> | <span data-ttu-id="e05b7-147">이벤트를 시작한 프로세스(이미지 파일)의 MD5 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="e05b7-147">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="e05b7-148">문자열</span><span class="sxs-lookup"><span data-stu-id="e05b7-148">string</span></span> | <span data-ttu-id="e05b7-149">이벤트를 시작한 프로세스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e05b7-149">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="e05b7-150">int</span><span class="sxs-lookup"><span data-stu-id="e05b7-150">int</span></span> | <span data-ttu-id="e05b7-151">이벤트를 시작한 프로세스의 PID(프로세스 ID)입니다.</span><span class="sxs-lookup"><span data-stu-id="e05b7-151">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="e05b7-152">문자열</span><span class="sxs-lookup"><span data-stu-id="e05b7-152">string</span></span> | <span data-ttu-id="e05b7-153">이벤트를 시작한 프로세스를 실행하는 데 사용되는 명령줄</span><span class="sxs-lookup"><span data-stu-id="e05b7-153">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="e05b7-154">datetime</span><span class="sxs-lookup"><span data-stu-id="e05b7-154">datetime</span></span> | <span data-ttu-id="e05b7-155">이벤트를 시작한 프로세스가 시작된 날짜 및 시간</span><span class="sxs-lookup"><span data-stu-id="e05b7-155">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="e05b7-156">문자열</span><span class="sxs-lookup"><span data-stu-id="e05b7-156">string</span></span> | <span data-ttu-id="e05b7-157">이벤트를 시작한 프로세스(이미지 파일)가 들어 있는 폴더</span><span class="sxs-lookup"><span data-stu-id="e05b7-157">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="e05b7-158">int</span><span class="sxs-lookup"><span data-stu-id="e05b7-158">int</span></span> | <span data-ttu-id="e05b7-159">이벤트를 담당하는 프로세스를 시작한 상위 프로세스의 PID(프로세스 ID)입니다.</span><span class="sxs-lookup"><span data-stu-id="e05b7-159">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="e05b7-160">문자열</span><span class="sxs-lookup"><span data-stu-id="e05b7-160">string</span></span> | <span data-ttu-id="e05b7-161">이벤트를 담당하는 프로세스를 시작한 상위 프로세스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e05b7-161">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="e05b7-162">datetime</span><span class="sxs-lookup"><span data-stu-id="e05b7-162">datetime</span></span> | <span data-ttu-id="e05b7-163">이벤트를 담당하는 프로세스의 부모가 시작된 날짜 및 시간</span><span class="sxs-lookup"><span data-stu-id="e05b7-163">Date and time when the parent of the process responsible for the event was started</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="e05b7-164">문자열</span><span class="sxs-lookup"><span data-stu-id="e05b7-164">string</span></span> | <span data-ttu-id="e05b7-165">이벤트를 시작한 프로세스의 무결성 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="e05b7-165">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="e05b7-166">Windows는 인터넷 다운로드에서 시작된 경우와 같은 특정 특성을 기반으로 프로세스에 무결성 수준을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="e05b7-166">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="e05b7-167">이러한 무결성 수준은 리소스에 대한 사용 권한에 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e05b7-167">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="e05b7-168">문자열</span><span class="sxs-lookup"><span data-stu-id="e05b7-168">string</span></span> | <span data-ttu-id="e05b7-169">이벤트를 시작한 프로세스에 적용된 UAC(사용자 액세스 제어) 권한 상승의 유무를 나타내는 토큰 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="e05b7-169">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `ReportId` | <span data-ttu-id="e05b7-170">long</span><span class="sxs-lookup"><span data-stu-id="e05b7-170">long</span></span> | <span data-ttu-id="e05b7-171">반복 카운터를 기반으로 하는 이벤트 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="e05b7-171">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="e05b7-172">고유한 이벤트를 식별하려면 이 열을 DeviceName 및 타임스탬프 열과 함께 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e05b7-172">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="e05b7-173">문자열</span><span class="sxs-lookup"><span data-stu-id="e05b7-173">string</span></span> | <span data-ttu-id="e05b7-174">Application Guard에서 브라우저 활동을 격리하기 위해 사용하는 가상화된 컨테이너의 식별자</span><span class="sxs-lookup"><span data-stu-id="e05b7-174">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="e05b7-175">관련 항목</span><span class="sxs-lookup"><span data-stu-id="e05b7-175">Related topics</span></span>
- [<span data-ttu-id="e05b7-176">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="e05b7-176">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e05b7-177">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="e05b7-177">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e05b7-178">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="e05b7-178">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="e05b7-179">장치, 전자 메일, 앱 및 ID를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="e05b7-179">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="e05b7-180">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="e05b7-180">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="e05b7-181">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="e05b7-181">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
