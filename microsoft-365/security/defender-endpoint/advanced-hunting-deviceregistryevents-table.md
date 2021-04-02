---
title: 고급 헌팅 스위마의 DeviceRegistryEvents 테이블
description: 고급 헌팅 키의 DeviceRegistryEvents 테이블에서 쿼리할 수 있는 레지스트리 이벤트에 대해 자세히 알아보시다.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, 검색, 쿼리, 원격 분석, schema 참조, kusto, 표, 열, 데이터 형식, deviceregistryevents, 레지스트리, 키, 하위 키, 값, RegistryEvents
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 31fe2bb882bc59eb516773c0c319b1f25f56a95e
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498764"
---
# <a name="deviceregistryevents"></a><span data-ttu-id="1c704-104">DeviceRegistryEvents</span><span class="sxs-lookup"><span data-stu-id="1c704-104">DeviceRegistryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1c704-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="1c704-105">**Applies to:**</span></span>
- [<span data-ttu-id="1c704-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1c704-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="1c704-107">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="1c704-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1c704-108">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="1c704-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="1c704-109">고급 `DeviceRegistryEvents` 헌팅 [키마의](advanced-hunting-overview.md) 표에는 레지스트리 항목 만들기 및 수정에 대한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c704-109">The `DeviceRegistryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about the creation and modification of registry entries.</span></span> <span data-ttu-id="1c704-110">이 참조를 사용하여 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="1c704-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="1c704-111">고급 헌팅 스마의 다른 표에 대한 자세한 내용은 고급 헌팅 스마 [참조 를 참조하세요.](advanced-hunting-schema-reference.md)</span><span class="sxs-lookup"><span data-stu-id="1c704-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="1c704-112">열 이름</span><span class="sxs-lookup"><span data-stu-id="1c704-112">Column name</span></span> | <span data-ttu-id="1c704-113">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="1c704-113">Data type</span></span> | <span data-ttu-id="1c704-114">설명</span><span class="sxs-lookup"><span data-stu-id="1c704-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="1c704-115">datetime</span><span class="sxs-lookup"><span data-stu-id="1c704-115">datetime</span></span> | <span data-ttu-id="1c704-116">이벤트가 기록된 날짜와 시간</span><span class="sxs-lookup"><span data-stu-id="1c704-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="1c704-117">문자열</span><span class="sxs-lookup"><span data-stu-id="1c704-117">string</span></span> | <span data-ttu-id="1c704-118">서비스에서 디바이스의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="1c704-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="1c704-119">문자열</span><span class="sxs-lookup"><span data-stu-id="1c704-119">string</span></span> | <span data-ttu-id="1c704-120">장치의 FQDN(FQDN)</span><span class="sxs-lookup"><span data-stu-id="1c704-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `ActionType` | <span data-ttu-id="1c704-121">문자열</span><span class="sxs-lookup"><span data-stu-id="1c704-121">string</span></span> | <span data-ttu-id="1c704-122">이벤트를 트리거한 활동 유형</span><span class="sxs-lookup"><span data-stu-id="1c704-122">Type of activity that triggered the event</span></span> |
| `RegistryKey` | <span data-ttu-id="1c704-123">문자열</span><span class="sxs-lookup"><span data-stu-id="1c704-123">string</span></span> | <span data-ttu-id="1c704-124">기록된 작업이 적용된 레지스트리 키</span><span class="sxs-lookup"><span data-stu-id="1c704-124">Registry key that the recorded action was applied to</span></span> |
| `RegistryValueType` | <span data-ttu-id="1c704-125">문자열</span><span class="sxs-lookup"><span data-stu-id="1c704-125">string</span></span> | <span data-ttu-id="1c704-126">기록된 작업이 적용된 레지스트리 값의 데이터 형식(예: 이진 또는 문자열)</span><span class="sxs-lookup"><span data-stu-id="1c704-126">Data type, such as binary or string, of the registry value that the recorded action was applied to</span></span> |
| `RegistryValueName` | <span data-ttu-id="1c704-127">문자열</span><span class="sxs-lookup"><span data-stu-id="1c704-127">string</span></span> | <span data-ttu-id="1c704-128">기록된 작업이 적용된 레지스트리 값의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1c704-128">Name of the registry value that the recorded action was applied to</span></span> |
| `RegistryValueData` | <span data-ttu-id="1c704-129">문자열</span><span class="sxs-lookup"><span data-stu-id="1c704-129">string</span></span> | <span data-ttu-id="1c704-130">기록된 작업이 적용된 레지스트리 값의 데이터</span><span class="sxs-lookup"><span data-stu-id="1c704-130">Data of the registry value that the recorded action was applied to</span></span> |
| `PreviousRegistryValueName` | <span data-ttu-id="1c704-131">문자열</span><span class="sxs-lookup"><span data-stu-id="1c704-131">string</span></span> | <span data-ttu-id="1c704-132">수정되기 전의 레지스트리 값의 원래 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1c704-132">Original name of the registry value before it was modified</span></span> |
| `PreviousRegistryValueData` | <span data-ttu-id="1c704-133">문자열</span><span class="sxs-lookup"><span data-stu-id="1c704-133">string</span></span> | <span data-ttu-id="1c704-134">레지스트리 값을 수정하기 전의 원래 데이터</span><span class="sxs-lookup"><span data-stu-id="1c704-134">Original data of the registry value before it was modified</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="1c704-135">문자열</span><span class="sxs-lookup"><span data-stu-id="1c704-135">string</span></span> | <span data-ttu-id="1c704-136">이벤트를 담당하는 프로세스를 시작한 계정의 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="1c704-136">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="1c704-137">문자열</span><span class="sxs-lookup"><span data-stu-id="1c704-137">string</span></span> | <span data-ttu-id="1c704-138">이벤트를 담당하는 프로세스를 시작한 계정의 사용자 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1c704-138">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="1c704-139">문자열</span><span class="sxs-lookup"><span data-stu-id="1c704-139">string</span></span> | <span data-ttu-id="1c704-140">이벤트를 담당하는 프로세스를 시작한 계정의 SID(보안 식별자)입니다.</span><span class="sxs-lookup"><span data-stu-id="1c704-140">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="1c704-141">문자열</span><span class="sxs-lookup"><span data-stu-id="1c704-141">string</span></span> | <span data-ttu-id="1c704-142">이벤트를 시작한 프로세스(이미지 파일)의 SHA-1</span><span class="sxs-lookup"><span data-stu-id="1c704-142">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="1c704-143">문자열</span><span class="sxs-lookup"><span data-stu-id="1c704-143">string</span></span> | <span data-ttu-id="1c704-144">이벤트를 시작한 프로세스(이미지 파일)의 MD5 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="1c704-144">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="1c704-145">문자열</span><span class="sxs-lookup"><span data-stu-id="1c704-145">string</span></span> | <span data-ttu-id="1c704-146">이벤트를 시작한 프로세스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1c704-146">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="1c704-147">int</span><span class="sxs-lookup"><span data-stu-id="1c704-147">int</span></span> | <span data-ttu-id="1c704-148">이벤트를 시작한 프로세스의 PID(프로세스 ID)입니다.</span><span class="sxs-lookup"><span data-stu-id="1c704-148">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="1c704-149">문자열</span><span class="sxs-lookup"><span data-stu-id="1c704-149">string</span></span> | <span data-ttu-id="1c704-150">이벤트를 시작한 프로세스를 실행하는 데 사용되는 명령줄</span><span class="sxs-lookup"><span data-stu-id="1c704-150">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="1c704-151">datetime</span><span class="sxs-lookup"><span data-stu-id="1c704-151">datetime</span></span> | <span data-ttu-id="1c704-152">이벤트를 시작한 프로세스가 시작된 날짜 및 시간</span><span class="sxs-lookup"><span data-stu-id="1c704-152">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="1c704-153">문자열</span><span class="sxs-lookup"><span data-stu-id="1c704-153">string</span></span> | <span data-ttu-id="1c704-154">이벤트를 시작한 프로세스(이미지 파일)가 포함된 폴더</span><span class="sxs-lookup"><span data-stu-id="1c704-154">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="1c704-155">int</span><span class="sxs-lookup"><span data-stu-id="1c704-155">int</span></span> | <span data-ttu-id="1c704-156">이벤트를 담당하는 프로세스를 시작한 상위 프로세스의 PID(프로세스 ID)입니다.</span><span class="sxs-lookup"><span data-stu-id="1c704-156">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="1c704-157">문자열</span><span class="sxs-lookup"><span data-stu-id="1c704-157">string</span></span> | <span data-ttu-id="1c704-158">이벤트를 담당하는 프로세스를 시작한 상위 프로세스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1c704-158">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="1c704-159">datetime</span><span class="sxs-lookup"><span data-stu-id="1c704-159">datetime</span></span> | <span data-ttu-id="1c704-160">이벤트를 담당하는 프로세스의 부모가 시작된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="1c704-160">Date and time when the parent of the process responsible for the event was started</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="1c704-161">문자열</span><span class="sxs-lookup"><span data-stu-id="1c704-161">string</span></span> | <span data-ttu-id="1c704-162">이벤트를 시작한 프로세스의 무결성 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="1c704-162">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="1c704-163">Windows는 인터넷 다운로드에서 시작된 경우와 같이 특정 특성을 기반으로 프로세스에 무결성 수준을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="1c704-163">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="1c704-164">이러한 무결성 수준은 리소스에 대한 사용 권한에 영향을 미치기</span><span class="sxs-lookup"><span data-stu-id="1c704-164">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="1c704-165">문자열</span><span class="sxs-lookup"><span data-stu-id="1c704-165">string</span></span> | <span data-ttu-id="1c704-166">이벤트를 시작한 프로세스에 적용되는 UAC(사용자 액세스 제어) 권한 상승의 유무를 나타내는 토큰 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="1c704-166">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `ReportId` | <span data-ttu-id="1c704-167">long</span><span class="sxs-lookup"><span data-stu-id="1c704-167">long</span></span> | <span data-ttu-id="1c704-168">반복 카운터를 기반으로 하는 이벤트 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="1c704-168">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="1c704-169">고유한 이벤트를 식별하려면 이 열을 및 열과 `DeviceName` 함께 `Timestamp` 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c704-169">To identify unique events, this column must be used in conjunction with the `DeviceName` and `Timestamp` columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="1c704-170">문자열</span><span class="sxs-lookup"><span data-stu-id="1c704-170">string</span></span> | <span data-ttu-id="1c704-171">Application Guard에서 브라우저 활동을 격리하기 위해 사용하는 가상화된 컨테이너의 식별자</span><span class="sxs-lookup"><span data-stu-id="1c704-171">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="1c704-172">관련 항목</span><span class="sxs-lookup"><span data-stu-id="1c704-172">Related topics</span></span>
- [<span data-ttu-id="1c704-173">지능형 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="1c704-173">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="1c704-174">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="1c704-174">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="1c704-175">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="1c704-175">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
