---
title: 고급 헌팅chema의 DeviceNetworkEvents 테이블
description: 고급 헌팅chema의 DeviceNetworkEvents 표에서 쿼리할 수 있는 네트워크 연결 이벤트에 대해 자세히
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 위협 방지, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, schema reference, kusto, table, column, data type, devicenetworkevents, NetworkCommunicationEvents, network connection, remote ip, local ip
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
ms.openlocfilehash: 0ed696f36737a4102895369e1254b4215cad4def
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931221"
---
# <a name="devicenetworkevents"></a><span data-ttu-id="a6c3b-104">DeviceNetworkEvents</span><span class="sxs-lookup"><span data-stu-id="a6c3b-104">DeviceNetworkEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a6c3b-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="a6c3b-105">**Applies to:**</span></span>
- <span data-ttu-id="a6c3b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a6c3b-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="a6c3b-107">고급 `DeviceNetworkEvents` 헌팅 [계획의](advanced-hunting-overview.md) 표에는 네트워크 연결 및 관련 이벤트에 대한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6c3b-107">The `DeviceNetworkEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about network connections and related events.</span></span> <span data-ttu-id="a6c3b-108">이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a6c3b-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="a6c3b-109">테이블에서 지원하는 이벤트 유형(값)에 대한 자세한 내용은 보안 센터에서 사용할 수 있는 기본 제공 `ActionType` [schema 참조를](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a6c3b-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="a6c3b-110">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a6c3b-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="a6c3b-111">열 이름</span><span class="sxs-lookup"><span data-stu-id="a6c3b-111">Column name</span></span> | <span data-ttu-id="a6c3b-112">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="a6c3b-112">Data type</span></span> | <span data-ttu-id="a6c3b-113">설명</span><span class="sxs-lookup"><span data-stu-id="a6c3b-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="a6c3b-114">datetime</span><span class="sxs-lookup"><span data-stu-id="a6c3b-114">datetime</span></span> | <span data-ttu-id="a6c3b-115">이벤트가 기록된 날짜와 시간</span><span class="sxs-lookup"><span data-stu-id="a6c3b-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="a6c3b-116">문자열</span><span class="sxs-lookup"><span data-stu-id="a6c3b-116">string</span></span> | <span data-ttu-id="a6c3b-117">서비스에서 시스템의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="a6c3b-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="a6c3b-118">문자열</span><span class="sxs-lookup"><span data-stu-id="a6c3b-118">string</span></span> | <span data-ttu-id="a6c3b-119">컴퓨터의 FQDN(정규화된 도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="a6c3b-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ActionType` | <span data-ttu-id="a6c3b-120">문자열</span><span class="sxs-lookup"><span data-stu-id="a6c3b-120">string</span></span> | <span data-ttu-id="a6c3b-121">이벤트를 트리거한 활동의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="a6c3b-121">Type of activity that triggered the event.</span></span> <span data-ttu-id="a6c3b-122">자세한 내용은 포털 [내 Schema 참조를](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="a6c3b-122">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `RemoteIP` | <span data-ttu-id="a6c3b-123">문자열</span><span class="sxs-lookup"><span data-stu-id="a6c3b-123">string</span></span> | <span data-ttu-id="a6c3b-124">연결된 IP 주소</span><span class="sxs-lookup"><span data-stu-id="a6c3b-124">IP address that was being connected to</span></span> |
| `RemotePort` | <span data-ttu-id="a6c3b-125">int</span><span class="sxs-lookup"><span data-stu-id="a6c3b-125">int</span></span> | <span data-ttu-id="a6c3b-126">연결되고 있는 원격 장치의 TCP 포트</span><span class="sxs-lookup"><span data-stu-id="a6c3b-126">TCP port on the remote device that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="a6c3b-127">문자열</span><span class="sxs-lookup"><span data-stu-id="a6c3b-127">string</span></span> | <span data-ttu-id="a6c3b-128">연결된 URL 또는 FQDN(정규화된 도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="a6c3b-128">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `LocalIP` | <span data-ttu-id="a6c3b-129">문자열</span><span class="sxs-lookup"><span data-stu-id="a6c3b-129">string</span></span> | <span data-ttu-id="a6c3b-130">통신 중에 사용되는 로컬 컴퓨터로 할당된 IP 주소</span><span class="sxs-lookup"><span data-stu-id="a6c3b-130">IP address assigned to the local machine used during communication</span></span> |
| `LocalPort` | <span data-ttu-id="a6c3b-131">int</span><span class="sxs-lookup"><span data-stu-id="a6c3b-131">int</span></span> | <span data-ttu-id="a6c3b-132">통신 중에 사용되는 로컬 컴퓨터의 TCP 포트</span><span class="sxs-lookup"><span data-stu-id="a6c3b-132">TCP port on the local machine used during communication</span></span> |
| `Protocol` | <span data-ttu-id="a6c3b-133">문자열</span><span class="sxs-lookup"><span data-stu-id="a6c3b-133">string</span></span> | <span data-ttu-id="a6c3b-134">통신 중에 사용되는 프로토콜</span><span class="sxs-lookup"><span data-stu-id="a6c3b-134">Protocol used during the communication</span></span> |
| `LocalIPType` | <span data-ttu-id="a6c3b-135">문자열</span><span class="sxs-lookup"><span data-stu-id="a6c3b-135">string</span></span> | <span data-ttu-id="a6c3b-136">IP 주소 유형(예: Public, Private, Reserved, Loopback, Teredo, FourToSixMapping 및 Broadcast)</span><span class="sxs-lookup"><span data-stu-id="a6c3b-136">Type of IP address, for example Public, Private, Reserved, Loopback, Teredo, FourToSixMapping, and Broadcast</span></span> |
| `RemoteIPType` | <span data-ttu-id="a6c3b-137">문자열</span><span class="sxs-lookup"><span data-stu-id="a6c3b-137">string</span></span> | <span data-ttu-id="a6c3b-138">IP 주소 유형(예: Public, Private, Reserved, Loopback, Teredo, FourToSixMapping 및 Broadcast)</span><span class="sxs-lookup"><span data-stu-id="a6c3b-138">Type of IP address, for example Public, Private, Reserved, Loopback, Teredo, FourToSixMapping, and Broadcast</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="a6c3b-139">문자열</span><span class="sxs-lookup"><span data-stu-id="a6c3b-139">string</span></span> | <span data-ttu-id="a6c3b-140">이벤트를 시작한 프로세스의 SHA-1(이미지 파일)</span><span class="sxs-lookup"><span data-stu-id="a6c3b-140">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessSHA256` | <span data-ttu-id="a6c3b-141">문자열</span><span class="sxs-lookup"><span data-stu-id="a6c3b-141">string</span></span> | <span data-ttu-id="a6c3b-142">이벤트를 시작한 프로세스(이미지 파일)의 SHA-256입니다.</span><span class="sxs-lookup"><span data-stu-id="a6c3b-142">SHA-256 of the process (image file) that initiated the event.</span></span> <span data-ttu-id="a6c3b-143">일반적으로이 필드는 채워지지 않습니다. 가능한 경우 SHA1 열을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a6c3b-143">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="a6c3b-144">문자열</span><span class="sxs-lookup"><span data-stu-id="a6c3b-144">string</span></span> | <span data-ttu-id="a6c3b-145">이벤트를 시작한 프로세스(이미지 파일)의 MD5 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="a6c3b-145">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="a6c3b-146">문자열</span><span class="sxs-lookup"><span data-stu-id="a6c3b-146">string</span></span> | <span data-ttu-id="a6c3b-147">이벤트를 시작한 프로세스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a6c3b-147">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="a6c3b-148">int</span><span class="sxs-lookup"><span data-stu-id="a6c3b-148">int</span></span> | <span data-ttu-id="a6c3b-149">이벤트를 시작한 프로세스의 PID(프로세스 ID)입니다.</span><span class="sxs-lookup"><span data-stu-id="a6c3b-149">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="a6c3b-150">문자열</span><span class="sxs-lookup"><span data-stu-id="a6c3b-150">string</span></span> | <span data-ttu-id="a6c3b-151">이벤트를 시작한 프로세스를 실행하는 데 사용되는 명령줄</span><span class="sxs-lookup"><span data-stu-id="a6c3b-151">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="a6c3b-152">datetime</span><span class="sxs-lookup"><span data-stu-id="a6c3b-152">datetime</span></span> | <span data-ttu-id="a6c3b-153">이벤트를 시작한 프로세스가 시작된 날짜 및 시간</span><span class="sxs-lookup"><span data-stu-id="a6c3b-153">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="a6c3b-154">문자열</span><span class="sxs-lookup"><span data-stu-id="a6c3b-154">string</span></span> | <span data-ttu-id="a6c3b-155">이벤트를 시작한 프로세스(이미지 파일)가 들어 있는 폴더</span><span class="sxs-lookup"><span data-stu-id="a6c3b-155">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="a6c3b-156">문자열</span><span class="sxs-lookup"><span data-stu-id="a6c3b-156">string</span></span> | <span data-ttu-id="a6c3b-157">이벤트를 담당하는 프로세스를 시작한 상위 프로세스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a6c3b-157">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="a6c3b-158">int</span><span class="sxs-lookup"><span data-stu-id="a6c3b-158">int</span></span> | <span data-ttu-id="a6c3b-159">이벤트를 담당하는 프로세스를 시작한 상위 프로세스의 PID(프로세스 ID)입니다.</span><span class="sxs-lookup"><span data-stu-id="a6c3b-159">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="a6c3b-160">datetime</span><span class="sxs-lookup"><span data-stu-id="a6c3b-160">datetime</span></span> | <span data-ttu-id="a6c3b-161">이벤트를 담당하는 프로세스의 상위 프로세스가 시작된 날짜 및 시간</span><span class="sxs-lookup"><span data-stu-id="a6c3b-161">Date and time when the parent of the process responsible for the event was started</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="a6c3b-162">문자열</span><span class="sxs-lookup"><span data-stu-id="a6c3b-162">string</span></span> | <span data-ttu-id="a6c3b-163">이벤트를 담당하는 프로세스를 시작한 계정의 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="a6c3b-163">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="a6c3b-164">문자열</span><span class="sxs-lookup"><span data-stu-id="a6c3b-164">string</span></span> | <span data-ttu-id="a6c3b-165">이벤트를 담당하는 프로세스를 시작한 계정의 사용자 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a6c3b-165">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="a6c3b-166">문자열</span><span class="sxs-lookup"><span data-stu-id="a6c3b-166">string</span></span> | <span data-ttu-id="a6c3b-167">이벤트를 담당하는 프로세스를 시작한 계정의 SID(보안 식별자)입니다.</span><span class="sxs-lookup"><span data-stu-id="a6c3b-167">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="a6c3b-168">문자열</span><span class="sxs-lookup"><span data-stu-id="a6c3b-168">string</span></span> | <span data-ttu-id="a6c3b-169">이벤트를 시작한 프로세스의 무결성 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="a6c3b-169">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="a6c3b-170">Windows는 인터넷 다운로드에서 시작된 경우와 같은 특정 특성을 기반으로 프로세스에 무결성 수준을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="a6c3b-170">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="a6c3b-171">이러한 무결성 수준은 리소스에 대한 사용 권한에 영향을 미치기</span><span class="sxs-lookup"><span data-stu-id="a6c3b-171">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="a6c3b-172">문자열</span><span class="sxs-lookup"><span data-stu-id="a6c3b-172">string</span></span> | <span data-ttu-id="a6c3b-173">이벤트를 시작한 프로세스에 적용된 UAC(사용자 액세스 제어) 권한 상승의 유무를 나타내는 토큰 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a6c3b-173">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `ReportId` | <span data-ttu-id="a6c3b-174">long</span><span class="sxs-lookup"><span data-stu-id="a6c3b-174">long</span></span> | <span data-ttu-id="a6c3b-175">반복 카운터를 기반으로 하는 이벤트 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="a6c3b-175">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="a6c3b-176">고유한 이벤트를 식별하려면 이 열을 DeviceName 및 타임스탬프 열과 함께 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6c3b-176">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="a6c3b-177">문자열</span><span class="sxs-lookup"><span data-stu-id="a6c3b-177">string</span></span> | <span data-ttu-id="a6c3b-178">Application Guard에서 브라우저 활동을 격리하기 위해 사용하는 가상화된 컨테이너의 식별자</span><span class="sxs-lookup"><span data-stu-id="a6c3b-178">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="a6c3b-179">관련 항목</span><span class="sxs-lookup"><span data-stu-id="a6c3b-179">Related topics</span></span>
- [<span data-ttu-id="a6c3b-180">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="a6c3b-180">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a6c3b-181">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="a6c3b-181">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="a6c3b-182">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="a6c3b-182">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="a6c3b-183">장치, 전자 메일, 앱 및 ID를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="a6c3b-183">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="a6c3b-184">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="a6c3b-184">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="a6c3b-185">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="a6c3b-185">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
