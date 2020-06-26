---
title: 고급 구하기 스키마의 DeviceRegistryEvents 테이블
description: 고급 구하기 스키마의 DeviceRegistryEvents 테이블에서 쿼리할 수 있는 레지스트리 이벤트에 대해 자세히 알아봅니다.
keywords: 고급 구하기, 위협 검색, 사이버 위협 사냥, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 스키마 참조, kusto, table, registryevents, registry, DeviceRegistryEvents, key, subkey, 값
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
ms.openlocfilehash: 35544866b9ebad94b14300b3734ddb2335fd657e
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899008"
---
# <a name="deviceregistryevents"></a><span data-ttu-id="4e846-104">DeviceRegistryEvents</span><span class="sxs-lookup"><span data-stu-id="4e846-104">DeviceRegistryEvents</span></span>

<span data-ttu-id="4e846-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="4e846-105">**Applies to:**</span></span>
- <span data-ttu-id="4e846-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="4e846-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="4e846-107">`DeviceRegistryEvents` [고급 구하기](advanced-hunting-overview.md) 스키마의 표에는 레지스트리 항목 만들기 및 수정에 대 한 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e846-107">The `DeviceRegistryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about the creation and modification of registry entries.</span></span> <span data-ttu-id="4e846-108">이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="4e846-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="4e846-109">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4e846-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="4e846-110">열 이름</span><span class="sxs-lookup"><span data-stu-id="4e846-110">Column name</span></span> | <span data-ttu-id="4e846-111">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4e846-111">Data type</span></span> | <span data-ttu-id="4e846-112">설명</span><span class="sxs-lookup"><span data-stu-id="4e846-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="4e846-113">datetime</span><span class="sxs-lookup"><span data-stu-id="4e846-113">datetime</span></span> | <span data-ttu-id="4e846-114">이벤트가 기록된 날짜와 시간</span><span class="sxs-lookup"><span data-stu-id="4e846-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="4e846-115">문자열</span><span class="sxs-lookup"><span data-stu-id="4e846-115">string</span></span> | <span data-ttu-id="4e846-116">서비스에서 시스템의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="4e846-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="4e846-117">문자열</span><span class="sxs-lookup"><span data-stu-id="4e846-117">string</span></span> | <span data-ttu-id="4e846-118">컴퓨터의 FQDN(정규화된 도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="4e846-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ActionType` | <span data-ttu-id="4e846-119">문자열</span><span class="sxs-lookup"><span data-stu-id="4e846-119">string</span></span> | <span data-ttu-id="4e846-120">이벤트를 트리거한 작업의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="4e846-120">Type of activity that triggered the event</span></span> |
| `RegistryKey` | <span data-ttu-id="4e846-121">문자열</span><span class="sxs-lookup"><span data-stu-id="4e846-121">string</span></span> | <span data-ttu-id="4e846-122">기록 된 작업이 적용 된 레지스트리 키</span><span class="sxs-lookup"><span data-stu-id="4e846-122">Registry key that the recorded action was applied to</span></span> |
| `RegistryValueType` | <span data-ttu-id="4e846-123">문자열</span><span class="sxs-lookup"><span data-stu-id="4e846-123">string</span></span> | <span data-ttu-id="4e846-124">기록 된 작업이 적용 된 레지스트리 값의 데이터 형식 (예: binary 또는 string)입니다.</span><span class="sxs-lookup"><span data-stu-id="4e846-124">Data type, such as binary or string, of the registry value that the recorded action was applied to</span></span> |
| `RegistryValueName` | <span data-ttu-id="4e846-125">문자열</span><span class="sxs-lookup"><span data-stu-id="4e846-125">string</span></span> | <span data-ttu-id="4e846-126">기록 된 작업이 적용 된 레지스트리 값의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4e846-126">Name of the registry value that the recorded action was applied to</span></span> |
| `RegistryValueData` | <span data-ttu-id="4e846-127">문자열</span><span class="sxs-lookup"><span data-stu-id="4e846-127">string</span></span> | <span data-ttu-id="4e846-128">기록 된 작업이 적용 된 레지스트리 값의 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="4e846-128">Data of the registry value that the recorded action was applied to</span></span> |
| `PreviousRegistryValueName` | <span data-ttu-id="4e846-129">문자열</span><span class="sxs-lookup"><span data-stu-id="4e846-129">string</span></span> | <span data-ttu-id="4e846-130">수정 되기 전의 레지스트리 값의 원래 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4e846-130">Original name of the registry value before it was modified</span></span> |
| `PreviousRegistryValueData` | <span data-ttu-id="4e846-131">문자열</span><span class="sxs-lookup"><span data-stu-id="4e846-131">string</span></span> | <span data-ttu-id="4e846-132">수정 되기 전의 레지스트리 값에 대 한 원본 데이터</span><span class="sxs-lookup"><span data-stu-id="4e846-132">Original data of the registry value before it was modified</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="4e846-133">문자열</span><span class="sxs-lookup"><span data-stu-id="4e846-133">string</span></span> | <span data-ttu-id="4e846-134">이벤트를 담당 하는 프로세스를 실행 한 계정의 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="4e846-134">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="4e846-135">문자열</span><span class="sxs-lookup"><span data-stu-id="4e846-135">string</span></span> | <span data-ttu-id="4e846-136">이벤트를 담당 하는 프로세스를 실행 한 계정의 사용자 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4e846-136">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="4e846-137">문자열</span><span class="sxs-lookup"><span data-stu-id="4e846-137">string</span></span> | <span data-ttu-id="4e846-138">이벤트를 담당 하는 프로세스를 실행 한 계정의 SID (보안 식별자)입니다.</span><span class="sxs-lookup"><span data-stu-id="4e846-138">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="4e846-139">문자열</span><span class="sxs-lookup"><span data-stu-id="4e846-139">string</span></span> | <span data-ttu-id="4e846-140">이벤트를 시작한 프로세스 (이미지 파일)의 SHA-1</span><span class="sxs-lookup"><span data-stu-id="4e846-140">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessSHA256` | <span data-ttu-id="4e846-141">문자열</span><span class="sxs-lookup"><span data-stu-id="4e846-141">string</span></span> | <span data-ttu-id="4e846-142">이벤트를 시작한 프로세스 (이미지 파일)의 SHA-256입니다.</span><span class="sxs-lookup"><span data-stu-id="4e846-142">SHA-256 of the process (image file) that initiated the event.</span></span> <span data-ttu-id="4e846-143">일반적으로이 필드는 채워지지 않습니다. 가능한 경우 SHA1 열을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4e846-143">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="4e846-144">문자열</span><span class="sxs-lookup"><span data-stu-id="4e846-144">string</span></span> | <span data-ttu-id="4e846-145">이벤트를 시작한 프로세스 (이미지 파일)의 MD5 해시</span><span class="sxs-lookup"><span data-stu-id="4e846-145">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="4e846-146">문자열</span><span class="sxs-lookup"><span data-stu-id="4e846-146">string</span></span> | <span data-ttu-id="4e846-147">이벤트를 시작한 프로세스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4e846-147">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="4e846-148">int</span><span class="sxs-lookup"><span data-stu-id="4e846-148">int</span></span> | <span data-ttu-id="4e846-149">이벤트를 시작한 프로세스의 PID (프로세스 ID)</span><span class="sxs-lookup"><span data-stu-id="4e846-149">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="4e846-150">문자열</span><span class="sxs-lookup"><span data-stu-id="4e846-150">string</span></span> | <span data-ttu-id="4e846-151">이벤트를 시작한 프로세스를 실행 하는 데 사용 되는 명령줄입니다.</span><span class="sxs-lookup"><span data-stu-id="4e846-151">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="4e846-152">datetime</span><span class="sxs-lookup"><span data-stu-id="4e846-152">datetime</span></span> | <span data-ttu-id="4e846-153">이벤트를 시작한 프로세스를 시작한 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="4e846-153">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="4e846-154">문자열</span><span class="sxs-lookup"><span data-stu-id="4e846-154">string</span></span> | <span data-ttu-id="4e846-155">이벤트를 시작한 프로세스 (이미지 파일)가 들어 있는 폴더</span><span class="sxs-lookup"><span data-stu-id="4e846-155">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="4e846-156">int</span><span class="sxs-lookup"><span data-stu-id="4e846-156">int</span></span> | <span data-ttu-id="4e846-157">이벤트를 담당 하는 프로세스를 생성 한 상위 프로세스의 PID (프로세스 ID)입니다.</span><span class="sxs-lookup"><span data-stu-id="4e846-157">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="4e846-158">문자열</span><span class="sxs-lookup"><span data-stu-id="4e846-158">string</span></span> | <span data-ttu-id="4e846-159">이벤트를 담당 하는 프로세스를 생성 한 상위 프로세스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4e846-159">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="4e846-160">datetime</span><span class="sxs-lookup"><span data-stu-id="4e846-160">datetime</span></span> | <span data-ttu-id="4e846-161">이벤트를 담당 하는 프로세스의 부모를 시작한 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="4e846-161">Date and time when the parent of the process responsible for the event was started</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="4e846-162">문자열</span><span class="sxs-lookup"><span data-stu-id="4e846-162">string</span></span> | <span data-ttu-id="4e846-163">이벤트를 시작한 프로세스의 무결성 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="4e846-163">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="4e846-164">Windows에서는 인터넷 다운로드에서 시작 된 경우와 같이 특정 특성에 따라 프로세스에 무결성 수준을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e846-164">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="4e846-165">이러한 무결성 수준은 리소스에 대 한 사용 권한에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4e846-165">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="4e846-166">문자열</span><span class="sxs-lookup"><span data-stu-id="4e846-166">string</span></span> | <span data-ttu-id="4e846-167">이벤트를 시작한 프로세스에 UAC (사용자 액세스 제어) 권한 상승이 적용 되었는지 여부를 나타내는 토큰 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="4e846-167">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `ReportId` | <span data-ttu-id="4e846-168">long</span><span class="sxs-lookup"><span data-stu-id="4e846-168">long</span></span> | <span data-ttu-id="4e846-169">반복 카운터를 기반으로 하는 이벤트 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="4e846-169">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="4e846-170">고유 이벤트를 식별 하려면이 열을 장치 이름 및 타임 스탬프 열과 함께 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e846-170">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="4e846-171">문자열</span><span class="sxs-lookup"><span data-stu-id="4e846-171">string</span></span> | <span data-ttu-id="4e846-172">응용 프로그램 가드가 브라우저 활동을 격리 하는 데 사용 하는 가상화 된 컨테이너의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="4e846-172">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="4e846-173">관련 항목</span><span class="sxs-lookup"><span data-stu-id="4e846-173">Related topics</span></span>
- [<span data-ttu-id="4e846-174">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="4e846-174">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="4e846-175">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="4e846-175">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="4e846-176">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="4e846-176">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="4e846-177">여러 장치 및 전자 메일에서 위협을 탐지</span><span class="sxs-lookup"><span data-stu-id="4e846-177">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="4e846-178">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="4e846-178">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="4e846-179">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="4e846-179">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
